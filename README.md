
import 'package:flutter/material.dart';
	void main() => runApp(App());
	

	class App extends StatelessWidget {
	  Widget build(BuildContext context) {
	    return MaterialApp(
	      title: 'Flutter penyimpanan Pinjam buku',
	      home: Scaffold(
	        appBar: AppBar(
	          title: Text(‘Rivani margaretta -6SIA),
	        ),
	        body: Pinjambuku(),
	      ),
	    );
	  }
	}
	

	class DataPinjambuku{
	  String namamhs;
	  String nrmmhs;
	  String jdlbuku;
	  String  jmlhbuku;
	  
	  
	  DataPinjambuku({this.namamhs, this.nirmmhs, this.jdlbuku, this.jmlhbuku});
	  
	}
	

	// class Pinjam buku
	class Pinjambuku extends StatefulWidget {
	  _MyappState createState() => _MyappState();
	}
	

	class _MyappState extends State<Pinjam buku> {
	  //deklarasi variabel
	  final txtnamamhs = TextEditingController();
	  final txtnirmmhs = TextEditingController();
	  final txtjdlbuku = TextEditingController();
	  final txtjmlhbuku = TextEditingController();
	  
	

	  List<Widget> data = [];
	

	  onTambah() {
	    setState(() {
	      data.add(ListTile(
	        leading: Text(txtjdlbuku.text),
	        title: Text(txtnamamhs.text),
	        subtitle: Text(txtnirmmhs.text),
	        trailing: Text(txtjmlhbuku.text),
	      ));
	      txtnamamhs.clear();
	      txtnirmmhs.clear();
	      txtjdlbuku.clear();
	      txtJmlhbuku.clear();
	    });
	  }
	

	  Widget build(BuildContext context) {
	    return ListView(
	      children: <Widget>[
	        new Container(
	          padding: EdgeInsets.all(10.0),
	          child: Column(
	            mainAxisAlignment: MainAxisAlignment.spaceEvenly,
	            children: <Widget>[
	               TextField(
	                controller: txtNama,
	                decoration: InputDecoration(hintText: 'Nama Mahasiswa'),
	              ),
	              TextField(
	                controller: txtnirmmhs,
	                decoration: InputDecoration(hintText: 'NIrm mahasiswa'),
	              ),
	              TextField(
	                controller: txtjdlbuku,
	                decoration: InputDecoration(hintText: 'Jdlbuku'),
	              ),
	              TextField(
	                controller: txtJmlhbuku,
	                decoration: InputDecoration(hintText: ‘Jmlhbuku'),
	              ),
	              Divider(height: 3.0),
	              ElevatedButton(child: Text("Simpan"), onPressed: onTambah),
	            ],
	          ),
	        ),
	        new Column(
	          children: data,
	        )
	      ],
	    );
	  }
	}

