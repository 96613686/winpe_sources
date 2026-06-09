# System.Xml.Serialization.XmlSerializationReader::ParseArrayType

- ea: `0x8a740`
- end: `0x8a937`
- name: `System.Xml.Serialization.XmlSerializationReader::ParseArrayType`
- size: `503`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x8a660`
- `0x8b640`

## callees

- `0x622f0`
- `0x62370`
- `0x8a740`
- `0x8ae20`

## string_xrefs

- `0x8a7ce`: `XmlInvalidArrayDimentions`
- `0x8a8c1`: `XmlInvalidArrayDimentions`
- `0x8a743`: `XmlMissingArrayType`
- `0x8a76a`: `XmlEmptyArrayType`
- `0x8a7ac`: `XmlInvalidArraySyntax`
- `0x8a8ec`: `XmlInvalidArraySyntax`
- `0x8a805`: `XmlMismatchedArrayBrackets`
- `0x8a8a5`: `XmlMismatchedArrayBrackets`
- `0x8a867`: `XmlInvalidArrayLength`

## pseudocode

```c

```

## disassembly

```asm
0x8a740  ldarg.1
0x8a741  brtrue.s loc_8A762
0x8a743  ldstr    aXmlmissingarra// "XmlMissingArrayType"
0x8a748  ldc.i4.1
0x8a749  newarr   [mscorlib]System.Object
0x8a74e  dup
0x8a74f  ldc.i4.0
0x8a750  ldarg.0
0x8a751  call     instance string System.Xml.Serialization.XmlSerializationReader::CurrentTag()
0x8a756  stelem.ref
0x8a757  call     string System.Xml.Res::GetString(string name, object[] args)
0x8a75c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x8a761  throw
0x8a762  ldarg.1
0x8a763  callvirt instance int32 [mscorlib]System.String::get_Length()
0x8a768  brtrue.s loc_8A78E
0x8a76a  ldstr    aXmlemptyarrayt// "XmlEmptyArrayType"
0x8a76f  ldc.i4.1
0x8a770  newarr   [mscorlib]System.Object
0x8a775  dup
0x8a776  ldc.i4.0
0x8a777  ldarg.0
0x8a778  call     instance string System.Xml.Serialization.XmlSerializationReader::CurrentTag()
0x8a77d  stelem.ref
0x8a77e  call     string System.Xml.Res::GetString(string name, object[] args)
0x8a783  ldstr    aValue// "value"
0x8a788  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x8a78d  throw
0x8a78e  ldarg.1
0x8a78f  callvirt instance char[] [mscorlib]System.String::ToCharArray()
0x8a794  stloc.0
0x8a795  ldloc.0
0x8a796  ldlen
0x8a797  conv.i4
0x8a798  stloc.1
0x8a799  ldloca.s 2
0x8a79b  initobj  SoapArrayInfo
0x8a7a1  ldloc.1
0x8a7a2  ldc.i4.1
0x8a7a3  sub
0x8a7a4  stloc.3
0x8a7a5  ldloc.0
0x8a7a6  ldloc.3
0x8a7a7  ldelem.u2
0x8a7a8  ldc.i4.s 0x5D
0x8a7aa  beq.s    loc_8A7C1
0x8a7ac  ldstr    aXmlinvalidarra_3// "XmlInvalidArraySyntax"
0x8a7b1  call     string System.Xml.Res::GetString(string name)
0x8a7b6  ldstr    aValue// "value"
0x8a7bb  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x8a7c0  throw
0x8a7c1  ldloc.3
0x8a7c2  ldc.i4.1
0x8a7c3  sub
0x8a7c4  stloc.3
0x8a7c5  br.s     loc_8A7F6
0x8a7c7  ldloc.0
0x8a7c8  ldloc.3
0x8a7c9  ldelem.u2
0x8a7ca  ldc.i4.s 0x2C
0x8a7cc  bne.un.s loc_8A7F2
0x8a7ce  ldstr    aXmlinvalidarra_0// "XmlInvalidArrayDimentions"
0x8a7d3  ldc.i4.1
0x8a7d4  newarr   [mscorlib]System.Object
0x8a7d9  dup
0x8a7da  ldc.i4.0
0x8a7db  ldarg.0
0x8a7dc  call     instance string System.Xml.Serialization.XmlSerializationReader::CurrentTag()
0x8a7e1  stelem.ref
0x8a7e2  call     string System.Xml.Res::GetString(string name, object[] args)
0x8a7e7  ldstr    aValue// "value"
0x8a7ec  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x8a7f1  throw
0x8a7f2  ldloc.3
0x8a7f3  ldc.i4.1
0x8a7f4  sub
0x8a7f5  stloc.3
0x8a7f6  ldloc.3
0x8a7f7  ldc.i4.m1
0x8a7f8  beq.s    loc_8A801
0x8a7fa  ldloc.0
0x8a7fb  ldloc.3
0x8a7fc  ldelem.u2
0x8a7fd  ldc.i4.s 0x5B
0x8a7ff  bne.un.s loc_8A7C7
0x8a801  ldloc.3
0x8a802  ldc.i4.m1
0x8a803  bne.un.s loc_8A81A
0x8a805  ldstr    aXmlmismatcheda// "XmlMismatchedArrayBrackets"
0x8a80a  call     string System.Xml.Res::GetString(string name)
0x8a80f  ldstr    aValue// "value"
0x8a814  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x8a819  throw
0x8a81a  ldloc.1
0x8a81b  ldloc.3
0x8a81c  sub
0x8a81d  ldc.i4.2
0x8a81e  sub
0x8a81f  stloc.s  4
0x8a821  ldloc.s  4
0x8a823  ldc.i4.0
0x8a824  ble.s    loc_8A887
0x8a826  ldloc.0
0x8a827  ldloc.3
0x8a828  ldc.i4.1
0x8a829  add
0x8a82a  ldloc.s  4
0x8a82c  newobj   instance void [mscorlib]System.String::.ctor(char[], int32, int32)
0x8a831  stloc.s  5
0x8a833  ldloca.s 2
0x8a835  ldloc.s  5
0x8a837  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8a83c  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x8a841  stfld    int32 SoapArrayInfo::length
0x8a846  leave.s  loc_8A88F
0x8a848  stloc.s  6
0x8a84a  ldloc.s  6
0x8a84c  isinst   [mscorlib]System.Threading.ThreadAbortException
0x8a851  brtrue.s loc_8A865
0x8a853  ldloc.s  6
0x8a855  isinst   [mscorlib]System.StackOverflowException
0x8a85a  brtrue.s loc_8A865
0x8a85c  ldloc.s  6
0x8a85e  isinst   [mscorlib]System.OutOfMemoryException
0x8a863  brfalse.s loc_8A867
0x8a865  rethrow
0x8a867  ldstr    aXmlinvalidarra_4// "XmlInvalidArrayLength"
0x8a86c  ldc.i4.1
0x8a86d  newarr   [mscorlib]System.Object
0x8a872  dup
0x8a873  ldc.i4.0
0x8a874  ldloc.s  5
0x8a876  stelem.ref
0x8a877  call     string System.Xml.Res::GetString(string name, object[] args)
0x8a87c  ldstr    aValue// "value"
0x8a881  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x8a886  throw
0x8a887  ldloca.s 2
0x8a889  ldc.i4.m1
0x8a88a  stfld    int32 SoapArrayInfo::length
0x8a88f  ldloc.3
0x8a890  ldc.i4.1
0x8a891  sub
0x8a892  stloc.3
0x8a893  ldloca.s 2
0x8a895  ldc.i4.0
0x8a896  stfld    int32 SoapArrayInfo::jaggedDimensions
0x8a89b  br.s     loc_8A911
0x8a89d  ldloc.3
0x8a89e  ldc.i4.1
0x8a89f  sub
0x8a8a0  stloc.3
0x8a8a1  ldloc.3
0x8a8a2  ldc.i4.0
0x8a8a3  bge.s    loc_8A8BA
0x8a8a5  ldstr    aXmlmismatcheda// "XmlMismatchedArrayBrackets"
0x8a8aa  call     string System.Xml.Res::GetString(string name)
0x8a8af  ldstr    aValue// "value"
0x8a8b4  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x8a8b9  throw
0x8a8ba  ldloc.0
0x8a8bb  ldloc.3
0x8a8bc  ldelem.u2
0x8a8bd  ldc.i4.s 0x2C
0x8a8bf  bne.un.s loc_8A8E5
0x8a8c1  ldstr    aXmlinvalidarra_0// "XmlInvalidArrayDimentions"
0x8a8c6  ldc.i4.1
0x8a8c7  newarr   [mscorlib]System.Object
0x8a8cc  dup
0x8a8cd  ldc.i4.0
0x8a8ce  ldarg.0
0x8a8cf  call     instance string System.Xml.Serialization.XmlSerializationReader::CurrentTag()
0x8a8d4  stelem.ref
0x8a8d5  call     string System.Xml.Res::GetString(string name, object[] args)
0x8a8da  ldstr    aValue// "value"
0x8a8df  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x8a8e4  throw
0x8a8e5  ldloc.0
0x8a8e6  ldloc.3
0x8a8e7  ldelem.u2
0x8a8e8  ldc.i4.s 0x5B
0x8a8ea  beq.s    loc_8A901
0x8a8ec  ldstr    aXmlinvalidarra_3// "XmlInvalidArraySyntax"
0x8a8f1  call     string System.Xml.Res::GetString(string name)
0x8a8f6  ldstr    aValue// "value"
0x8a8fb  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x8a900  throw
0x8a901  ldloc.3
0x8a902  ldc.i4.1
0x8a903  sub
0x8a904  stloc.3
0x8a905  ldloca.s 2
0x8a907  ldflda   int32 SoapArrayInfo::jaggedDimensions
0x8a90c  dup
0x8a90d  ldind.i4
0x8a90e  ldc.i4.1
0x8a90f  add
0x8a910  stind.i4
0x8a911  ldloc.3
0x8a912  ldc.i4.m1
0x8a913  beq.s    loc_8A91C
0x8a915  ldloc.0
0x8a916  ldloc.3
0x8a917  ldelem.u2
0x8a918  ldc.i4.s 0x5D
0x8a91a  beq.s    loc_8A89D
0x8a91c  ldloca.s 2
0x8a91e  ldc.i4.1
0x8a91f  stfld    int32 SoapArrayInfo::dimensions
0x8a924  ldloca.s 2
0x8a926  ldloc.0
0x8a927  ldc.i4.0
0x8a928  ldloc.3
0x8a929  ldc.i4.1
0x8a92a  add
0x8a92b  newobj   instance void [mscorlib]System.String::.ctor(char[], int32, int32)
0x8a930  stfld    string SoapArrayInfo::qname
0x8a935  ldloc.2
0x8a936  ret
```
