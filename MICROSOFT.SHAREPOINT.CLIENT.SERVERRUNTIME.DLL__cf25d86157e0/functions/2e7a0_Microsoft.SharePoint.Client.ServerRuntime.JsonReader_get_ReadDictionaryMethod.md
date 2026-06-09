# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::get_ReadDictionaryMethod

- ea: `0x2e7a0`
- end: `0x2e7f9`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::get_ReadDictionaryMethod`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2e680`

## callees

- `0x2e7a0`

## string_xrefs

- `0x2e7cf`: `ReadDictionary`

## pseudocode

```c

```

## disassembly

```asm
0x2e7a0  ldsfld   class [mscorlib]System.Reflection.MethodInfo Microsoft.SharePoint.Client.ServerRuntime.JsonReader::s_readDictionaryMethod
0x2e7a5  stloc.0
0x2e7a6  ldloc.0
0x2e7a7  ldnull
0x2e7a8  call     bool [mscorlib]System.Reflection.MethodInfo::op_Equality(class [mscorlib]System.Reflection.MethodInfo, class [mscorlib]System.Reflection.MethodInfo)
0x2e7ad  brfalse.s loc_2E7F7
0x2e7af  ldtoken  Microsoft.SharePoint.Client.ServerRuntime.JsonReader
0x2e7b4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2e7b9  ldc.i4.s 0x14
0x2e7bb  callvirt instance class [mscorlib]System.Reflection.MethodInfo[] [mscorlib]System.Type::GetMethods(valuetype [mscorlib]System.Reflection.BindingFlags)
0x2e7c0  stloc.2
0x2e7c1  ldc.i4.0
0x2e7c2  stloc.3
0x2e7c3  br.s     loc_2E7EB
0x2e7c5  ldloc.2
0x2e7c6  ldloc.3
0x2e7c7  ldelem.ref
0x2e7c8  stloc.1
0x2e7c9  ldloc.1
0x2e7ca  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x2e7cf  ldstr    aReaddictionary// "ReadDictionary"
0x2e7d4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2e7d9  brfalse.s loc_2E7E7
0x2e7db  ldloc.1
0x2e7dc  callvirt instance bool [mscorlib]System.Reflection.MethodBase::get_IsGenericMethod()
0x2e7e1  brfalse.s loc_2E7E7
0x2e7e3  ldloc.1
0x2e7e4  stloc.0
0x2e7e5  br.s     loc_2E7F1
0x2e7e7  ldloc.3
0x2e7e8  ldc.i4.1
0x2e7e9  add
0x2e7ea  stloc.3
0x2e7eb  ldloc.3
0x2e7ec  ldloc.2
0x2e7ed  ldlen
0x2e7ee  conv.i4
0x2e7ef  blt.s    loc_2E7C5
0x2e7f1  ldloc.0
0x2e7f2  stsfld   class [mscorlib]System.Reflection.MethodInfo Microsoft.SharePoint.Client.ServerRuntime.JsonReader::s_readDictionaryMethod
0x2e7f7  ldloc.0
0x2e7f8  ret
```
