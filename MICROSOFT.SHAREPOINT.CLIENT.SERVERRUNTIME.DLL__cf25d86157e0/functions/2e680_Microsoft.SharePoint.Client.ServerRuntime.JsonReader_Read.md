# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::Read

- ea: `0x2e680`
- end: `0x2e7a0`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::Read`
- size: `288`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x2e680`
- `0x2e7a0`
- `0x2e8e0`
- `0x30040`
- `0x304f0`

## string_xrefs

- `0x2e6ca`: `ReadArray`

## pseudocode

```c

```

## disassembly

```asm
0x2e680  ldtoken  mvar<u1>
0x2e685  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2e68a  stloc.0
0x2e68b  ldloc.0
0x2e68c  call     class ReadObjectHandler ReadObjectHandlers::GetReadObjectHandler(class [mscorlib]System.Type type)
0x2e691  stloc.1
0x2e692  ldloc.1
0x2e693  brfalse.s loc_2E6A2
0x2e695  ldloc.1
0x2e696  ldarg.0
0x2e697  callvirt instance object ReadObjectHandler::Invoke(class Microsoft.SharePoint.Client.ServerRuntime.JsonReader reader)
0x2e69c  unbox.any mvar<u1>
0x2e6a1  ret
0x2e6a2  ldloc.0
0x2e6a3  callvirt instance bool [mscorlib]System.Type::get_IsEnum()
0x2e6a8  brfalse.s loc_2E6B1
0x2e6aa  ldarg.0
0x2e6ab  call     T0x2B000043
0x2e6b0  ret
0x2e6b1  ldloc.0
0x2e6b2  callvirt instance bool [mscorlib]System.Type::get_IsArray()
0x2e6b7  brfalse.s loc_2E6F9
0x2e6b9  ldloc.0
0x2e6ba  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::GetElementType()
0x2e6bf  stloc.2
0x2e6c0  ldtoken  Microsoft.SharePoint.Client.ServerRuntime.JsonReader
0x2e6c5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2e6ca  ldstr    aReadarray// "ReadArray"
0x2e6cf  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string)
0x2e6d4  stloc.3
0x2e6d5  ldloc.3
0x2e6d6  ldc.i4.1
0x2e6d7  newarr   [mscorlib]System.Type
0x2e6dc  stloc.s  6
0x2e6de  ldloc.s  6
0x2e6e0  ldc.i4.0
0x2e6e1  ldloc.2
0x2e6e2  stelem.ref
0x2e6e3  ldloc.s  6
0x2e6e5  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Reflection.MethodInfo::MakeGenericMethod(class [mscorlib]System.Type[])
0x2e6ea  stloc.3
0x2e6eb  ldloc.3
0x2e6ec  ldarg.0
0x2e6ed  ldnull
0x2e6ee  callvirt instance object [mscorlib]System.Reflection.MethodBase::Invoke(object, object[])
0x2e6f3  unbox.any mvar<u1>
0x2e6f8  ret
0x2e6f9  ldloc.0
0x2e6fa  callvirt instance bool [mscorlib]System.Type::get_IsGenericType()
0x2e6ff  brfalse  loc_2E78A
0x2e704  ldloc.0
0x2e705  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::GetGenericTypeDefinition()
0x2e70a  ldtoken  class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>
0x2e70f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2e714  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::GetGenericTypeDefinition()
0x2e719  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2e71e  brtrue.s loc_2E73C
0x2e720  ldloc.0
0x2e721  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::GetGenericTypeDefinition()
0x2e726  ldtoken  class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>
0x2e72b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2e730  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::GetGenericTypeDefinition()
0x2e735  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2e73a  brfalse.s loc_2E78A
0x2e73c  ldloc.0
0x2e73d  callvirt instance class [mscorlib]System.Type[] [mscorlib]System.Type::GetGenericArguments()
0x2e742  ldc.i4.0
0x2e743  ldelem.ref
0x2e744  ldtoken  [mscorlib]System.String
0x2e749  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2e74e  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2e753  brfalse.s loc_2E78A
0x2e755  ldloc.0
0x2e756  callvirt instance class [mscorlib]System.Type[] [mscorlib]System.Type::GetGenericArguments()
0x2e75b  ldc.i4.1
0x2e75c  ldelem.ref
0x2e75d  stloc.s  4
0x2e75f  call     class [mscorlib]System.Reflection.MethodInfo Microsoft.SharePoint.Client.ServerRuntime.JsonReader::get_ReadDictionaryMethod()
0x2e764  ldc.i4.1
0x2e765  newarr   [mscorlib]System.Type
0x2e76a  stloc.s  7
0x2e76c  ldloc.s  7
0x2e76e  ldc.i4.0
0x2e76f  ldloc.s  4
0x2e771  stelem.ref
0x2e772  ldloc.s  7
0x2e774  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Reflection.MethodInfo::MakeGenericMethod(class [mscorlib]System.Type[])
0x2e779  stloc.s  5
0x2e77b  ldloc.s  5
0x2e77d  ldarg.0
0x2e77e  ldnull
0x2e77f  callvirt instance object [mscorlib]System.Reflection.MethodBase::Invoke(object, object[])
0x2e784  unbox.any mvar<u1>
0x2e789  ret
0x2e78a  ldarg.0
0x2e78b  ldtoken  mvar<u1>
0x2e790  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2e795  call     instance object Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadObject(class [mscorlib]System.Type fallbackType)
0x2e79a  unbox.any mvar<u1>
0x2e79f  ret
```
