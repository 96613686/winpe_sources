# System.Xml.Serialization.XmlSerializationWriterCodeGen::WriteText

- ea: `0xa1800`
- end: `0xa18c1`
- name: `System.Xml.Serialization.XmlSerializationWriterCodeGen::WriteText`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0xa0d00`

## callees

- `0x62370`
- `0x68470`
- `0x684b0`
- `0x68600`
- `0x68c50`
- `0x72c10`
- `0x86170`
- `0x9dae0`
- `0x9db30`
- `0xa1800`

## string_xrefs

- `0xa18b0`: `XmlInternalError`
- `0xa181f`: `WriteValue(`
- `0xa18a5`: `.WriteTo(Writer);`

## pseudocode

```c

```

## disassembly

```asm
0xa1800  ldarg.2
0xa1801  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa1806  isinst   System.Xml.Serialization.PrimitiveMapping
0xa180b  brfalse.s loc_A1869
0xa180d  ldarg.2
0xa180e  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa1813  castclass System.Xml.Serialization.PrimitiveMapping
0xa1818  stloc.0
0xa1819  ldarg.0
0xa181a  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa181f  ldstr    aWritevalue// "WriteValue("
0xa1824  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0xa1829  ldarg.2
0xa182a  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa182f  isinst   System.Xml.Serialization.EnumMapping
0xa1834  brfalse.s loc_A184A
0xa1836  ldarg.0
0xa1837  ldarg.2
0xa1838  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa183d  castclass System.Xml.Serialization.EnumMapping
0xa1842  ldarg.1
0xa1843  call     instance void System.Xml.Serialization.XmlSerializationWriterCodeGen::WriteEnumValue(class System.Xml.Serialization.EnumMapping mapping, string source)
0xa1848  br.s     loc_A1858
0xa184a  ldarg.0
0xa184b  ldloc.0
0xa184c  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa1851  ldarg.1
0xa1852  ldc.i4.0
0xa1853  call     instance void System.Xml.Serialization.XmlSerializationWriterCodeGen::WritePrimitiveValue(class System.Xml.Serialization.TypeDesc typeDesc, string source, bool isElement)
0xa1858  ldarg.0
0xa1859  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa185e  ldstr    asc_133068// ");"
0xa1863  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0xa1868  ret
0xa1869  ldarg.2
0xa186a  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa186f  isinst   System.Xml.Serialization.SpecialMapping
0xa1874  brfalse.s loc_A18C0
0xa1876  ldarg.2
0xa1877  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0xa187c  castclass System.Xml.Serialization.SpecialMapping
0xa1881  stloc.1
0xa1882  ldloc.1
0xa1883  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0xa1888  callvirt instance valuetype System.Xml.Serialization.TypeKind System.Xml.Serialization.TypeDesc::get_Kind()
0xa188d  stloc.2
0xa188e  ldloc.2
0xa188f  ldc.i4.s 9
0xa1891  bne.un.s loc_A18B0
0xa1893  ldarg.0
0xa1894  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa1899  ldarg.1
0xa189a  callvirt instance void System.Xml.Serialization.IndentedWriter::Write(string s)
0xa189f  ldarg.0
0xa18a0  call     instance class System.Xml.Serialization.IndentedWriter System.Xml.Serialization.XmlSerializationCodeGen::get_Writer()
0xa18a5  ldstr    aWritetoWriter// ".WriteTo(Writer);"
0xa18aa  callvirt instance void System.Xml.Serialization.IndentedWriter::WriteLine(string s)
0xa18af  ret
0xa18b0  ldstr    aXmlinternalerr// "XmlInternalError"
0xa18b5  call     string System.Xml.Res::GetString(string name)
0xa18ba  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xa18bf  throw
0xa18c0  ret
```
