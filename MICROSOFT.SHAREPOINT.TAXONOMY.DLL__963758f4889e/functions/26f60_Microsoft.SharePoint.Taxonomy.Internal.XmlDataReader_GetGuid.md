# Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetGuid

- ea: `0x26f60`
- end: `0x26fca`
- name: `Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetGuid`
- size: `106`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x27070`
- `0x34000`
- `0x342e0`
- `0x34520`

## callees

- `0x26f60`
- `0x27260`
- `0x2ad40`

## string_xrefs

- `0x26f7d`: `ErrorXmlAttributeInvalidCastGuid`
- `0x26fa3`: `ErrorXmlAttributeInvalidCastGuid`

## pseudocode

```c

```

## disassembly

```asm
0x26f60  ldarg.0
0x26f61  call     instance void Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::Validate()
0x26f66  ldarg.0
0x26f67  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::attributes
0x26f6c  ldarg.1
0x26f6d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x26f72  stloc.0
0x26f73  ldloc.0
0x26f74  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x26f79  stloc.1
0x26f7a  leave.s  loc_26FC8
0x26f7c  stloc.2
0x26f7d  ldstr    aErrorxmlattrib_1// "ErrorXmlAttributeInvalidCastGuid"
0x26f82  ldc.i4.2
0x26f83  newarr   [mscorlib]System.Object
0x26f88  stloc.s  4
0x26f8a  ldloc.s  4
0x26f8c  ldc.i4.0
0x26f8d  ldloc.0
0x26f8e  stelem.ref
0x26f8f  ldloc.s  4
0x26f91  ldc.i4.1
0x26f92  ldarg.1
0x26f93  stelem.ref
0x26f94  ldloc.s  4
0x26f96  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x26f9b  ldloc.2
0x26f9c  newobj   instance void [mscorlib]System.InvalidCastException::.ctor(string, class [mscorlib]System.Exception)
0x26fa1  throw
0x26fa2  stloc.3
0x26fa3  ldstr    aErrorxmlattrib_1// "ErrorXmlAttributeInvalidCastGuid"
0x26fa8  ldc.i4.2
0x26fa9  newarr   [mscorlib]System.Object
0x26fae  stloc.s  5
0x26fb0  ldloc.s  5
0x26fb2  ldc.i4.0
0x26fb3  ldloc.0
0x26fb4  stelem.ref
0x26fb5  ldloc.s  5
0x26fb7  ldc.i4.1
0x26fb8  ldarg.1
0x26fb9  stelem.ref
0x26fba  ldloc.s  5
0x26fbc  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x26fc1  ldloc.3
0x26fc2  newobj   instance void [mscorlib]System.InvalidCastException::.ctor(string, class [mscorlib]System.Exception)
0x26fc7  throw
0x26fc8  ldloc.1
0x26fc9  ret
```
