# System.Xml.Serialization.TempAssembly::ValidateEncodingStyle

- ea: `0x66ac0`
- end: `0x66b59`
- name: `System.Xml.Serialization.TempAssembly::ValidateEncodingStyle`
- size: `153`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x66b80`
- `0x66ca0`

## callees

- `0x622f0`
- `0x66ac0`
- `0x1226d0`

## string_xrefs

- `0x66ae0`: `http://schemas.xmlsoap.org/soap/encoding/`
- `0x66b0a`: `http://schemas.xmlsoap.org/soap/encoding/`
- `0x66b50`: `http://schemas.xmlsoap.org/soap/encoding/`
- `0x66af9`: `XmlInvalidEncoding3`
- `0x66b23`: `XmlInvalidEncodingNotEncoded1`

## pseudocode

```c

```

## disassembly

```asm
0x66ac0  ldarg.1
0x66ac1  brfalse.s loc_66B3D
0x66ac3  ldarg.1
0x66ac4  callvirt instance int32 [mscorlib]System.String::get_Length()
0x66ac9  ldc.i4.0
0x66aca  ble.s    loc_66B3D
0x66acc  ldarg.0
0x66acd  ldfld    class TempMethodDictionary System.Xml.Serialization.TempAssembly::methods
0x66ad2  ldarg.2
0x66ad3  callvirt instance class TempMethod TempMethodDictionary::get_Item(string key)
0x66ad8  ldfld    bool TempMethod::isSoap
0x66add  brfalse.s loc_66B23
0x66adf  ldarg.1
0x66ae0  ldstr    aHttpSchemasXml// "http://schemas.xmlsoap.org/soap/encodin"...
0x66ae5  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x66aea  brfalse.s loc_66B57
0x66aec  ldarg.1
0x66aed  ldstr    aHttpWwwW3Org20_2// "http://www.w3.org/2003/05/soap-encoding"
0x66af2  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x66af7  brfalse.s loc_66B57
0x66af9  ldstr    aXmlinvalidenco// "XmlInvalidEncoding3"
0x66afe  ldc.i4.3
0x66aff  newarr   [mscorlib]System.Object
0x66b04  dup
0x66b05  ldc.i4.0
0x66b06  ldarg.1
0x66b07  stelem.ref
0x66b08  dup
0x66b09  ldc.i4.1
0x66b0a  ldstr    aHttpSchemasXml// "http://schemas.xmlsoap.org/soap/encodin"...
0x66b0f  stelem.ref
0x66b10  dup
0x66b11  ldc.i4.2
0x66b12  ldstr    aHttpWwwW3Org20_2// "http://www.w3.org/2003/05/soap-encoding"
0x66b17  stelem.ref
0x66b18  call     string System.Xml.Res::GetString(string name, object[] args)
0x66b1d  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x66b22  throw
0x66b23  ldstr    aXmlinvalidenco_0// "XmlInvalidEncodingNotEncoded1"
0x66b28  ldc.i4.1
0x66b29  newarr   [mscorlib]System.Object
0x66b2e  dup
0x66b2f  ldc.i4.0
0x66b30  ldarg.1
0x66b31  stelem.ref
0x66b32  call     string System.Xml.Res::GetString(string name, object[] args)
0x66b37  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x66b3c  throw
0x66b3d  ldarg.0
0x66b3e  ldfld    class TempMethodDictionary System.Xml.Serialization.TempAssembly::methods
0x66b43  ldarg.2
0x66b44  callvirt instance class TempMethod TempMethodDictionary::get_Item(string key)
0x66b49  ldfld    bool TempMethod::isSoap
0x66b4e  brfalse.s loc_66B57
0x66b50  ldstr    aHttpSchemasXml// "http://schemas.xmlsoap.org/soap/encodin"...
0x66b55  starg.s  1
0x66b57  ldarg.1
0x66b58  ret
```
