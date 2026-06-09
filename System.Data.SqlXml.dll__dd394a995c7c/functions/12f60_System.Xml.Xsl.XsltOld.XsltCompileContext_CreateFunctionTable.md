# System.Xml.Xsl.XsltOld.XsltCompileContext::CreateFunctionTable

- ea: `0x12f60`
- end: `0x12ffa`
- name: `System.Xml.Xsl.XsltOld.XsltCompileContext::CreateFunctionTable`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x13000`

## callees

- `0x555d0`
- `0x55600`
- `0x55650`
- `0x556b0`
- `0x55700`
- `0x55750`
- `0x557a0`
- `0x55830`
- `0x559d0`

## string_xrefs

- `0x12f79`: `unparsed-entity-uri`

## pseudocode

```c

```

## disassembly

```asm
0x12f60  ldc.i4.s 0xA
0x12f62  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor(int32)
0x12f67  stloc.0
0x12f68  ldloc.0
0x12f69  ldstr    aCurrent// "current"
0x12f6e  newobj   instance void FuncCurrent::.ctor()
0x12f73  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x12f78  ldloc.0
0x12f79  ldstr    aUnparsedEntity// "unparsed-entity-uri"
0x12f7e  newobj   instance void FuncUnEntityUri::.ctor()
0x12f83  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x12f88  ldloc.0
0x12f89  ldstr    aGenerateId// "generate-id"
0x12f8e  newobj   instance void FuncGenerateId::.ctor()
0x12f93  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x12f98  ldloc.0
0x12f99  ldstr    aSystemProperty// "system-property"
0x12f9e  newobj   instance void FuncSystemProp::.ctor()
0x12fa3  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x12fa8  ldloc.0
0x12fa9  ldstr    aElementAvailab// "element-available"
0x12fae  newobj   instance void FuncElementAvailable::.ctor()
0x12fb3  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x12fb8  ldloc.0
0x12fb9  ldstr    aFunctionAvaila// "function-available"
0x12fbe  newobj   instance void FuncFunctionAvailable::.ctor()
0x12fc3  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x12fc8  ldloc.0
0x12fc9  ldstr    aDocument// "document"
0x12fce  newobj   instance void FuncDocument::.ctor()
0x12fd3  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x12fd8  ldloc.0
0x12fd9  ldstr    aKey// "key"
0x12fde  newobj   instance void FuncKey::.ctor()
0x12fe3  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x12fe8  ldloc.0
0x12fe9  ldstr    aFormatNumber// "format-number"
0x12fee  newobj   instance void FuncFormatNumber::.ctor()
0x12ff3  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x12ff8  ldloc.0
0x12ff9  ret
```
