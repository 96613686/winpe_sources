# Microsoft.ManagementConsole.Internal.ClassLibraryServices::OnAssemblyResolve

- ea: `0x7e50`
- end: `0x7e96`
- name: `Microsoft.ManagementConsole.Internal.ClassLibraryServices::OnAssemblyResolve`
- size: `70`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x7e50`

## pseudocode

```c

```

## disassembly

```asm
0x7e50  ldnull
0x7e51  stloc.0
0x7e52  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0x7e57  stloc.1
0x7e58  ldarg.1
0x7e59  callvirt instance string [mscorlib]System.ResolveEventArgs::get_Name()
0x7e5e  ldloc.1
0x7e5f  callvirt instance string [mscorlib]System.Reflection.Assembly::get_FullName()
0x7e64  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7e69  brfalse.s loc_7E6F
0x7e6b  ldloc.1
0x7e6c  stloc.0
0x7e6d  br.s     loc_7E94
0x7e6f  ldtoken  [MMCFxCommon]Microsoft.ManagementConsole.Internal.IClassLibraryServices
0x7e74  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7e79  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x7e7e  stloc.2
0x7e7f  ldarg.1
0x7e80  callvirt instance string [mscorlib]System.ResolveEventArgs::get_Name()
0x7e85  ldloc.2
0x7e86  callvirt instance string [mscorlib]System.Reflection.Assembly::get_FullName()
0x7e8b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7e90  brfalse.s loc_7E94
0x7e92  ldloc.2
0x7e93  stloc.0
0x7e94  ldloc.0
0x7e95  ret
```
