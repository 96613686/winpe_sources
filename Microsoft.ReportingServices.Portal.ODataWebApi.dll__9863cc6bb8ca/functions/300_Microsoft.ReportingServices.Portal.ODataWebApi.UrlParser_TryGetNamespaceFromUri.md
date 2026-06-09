# Microsoft.ReportingServices.Portal.ODataWebApi.UrlParser::TryGetNamespaceFromUri

- ea: `0x300`
- end: `0x352`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.UrlParser::TryGetNamespaceFromUri`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xa0`

## callees

- `0x300`

## pseudocode

```c

```

## disassembly

```asm
0x300  ldarg.1
0x301  ldnull
0x302  stind.ref
0x303  ldc.i4.3
0x304  ldarg.0
0x305  callvirt instance string[] [System]System.Uri::get_Segments()
0x30a  ldlen
0x30b  conv.i4
0x30c  bge.s    loc_350
0x30e  ldarg.0
0x30f  callvirt instance string[] [System]System.Uri::get_Segments()
0x314  ldc.i4.3
0x315  ldelem.ref
0x316  stloc.0
0x317  ldc.i4.4
0x318  newarr   [mscorlib]System.Char
0x31d  dup
0x31e  ldtoken  int64 <PrivateImplementationDetails>::'3C9C3BB8C8E60141DC812B161971B93C052C882C'
0x323  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::InitializeArray(class [mscorlib]System.Array, valuetype [mscorlib]System.RuntimeFieldHandle)
0x328  stloc.1
0x329  ldloc.0
0x32a  ldloc.1
0x32b  ldc.i4.1
0x32c  callvirt instance string[] [mscorlib]System.String::Split(char[], valuetype [mscorlib]System.StringSplitOptions)
0x331  ldc.i4.0
0x332  ldelem.ref
0x333  ldloca.s 2
0x335  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0x33a  brfalse.s loc_350
0x33c  ldarg.1
0x33d  ldstr    aV// "V"
0x342  ldloc.2
0x343  box      [mscorlib]System.Int32
0x348  call     string [mscorlib]System.String::Concat(object, object)
0x34d  stind.ref
0x34e  ldc.i4.1
0x34f  ret
0x350  ldc.i4.0
0x351  ret
```
