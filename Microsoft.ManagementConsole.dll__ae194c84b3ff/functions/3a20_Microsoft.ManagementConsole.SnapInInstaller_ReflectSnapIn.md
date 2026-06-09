# Microsoft.ManagementConsole.SnapInInstaller::ReflectSnapIn

- ea: `0x3a20`
- end: `0x3a9a`
- name: `Microsoft.ManagementConsole.SnapInInstaller::ReflectSnapIn`
- size: `122`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x39b0`
- `0x3a00`

## callees

- `0x3a20`
- `0x3ae0`

## pseudocode

```c

```

## disassembly

```asm
0x3a20  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x3a25  stloc.0
0x3a26  ldarg.0
0x3a27  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3a2c  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetAssembly(class [mscorlib]System.Type)
0x3a31  stloc.1
0x3a32  ldloc.1
0x3a33  callvirt instance class [mscorlib]System.Type[] [mscorlib]System.Reflection.Assembly::GetTypes()
0x3a38  stloc.s  5
0x3a3a  ldc.i4.0
0x3a3b  stloc.s  6
0x3a3d  br.s     loc_3A7C
0x3a3f  ldloc.s  5
0x3a41  ldloc.s  6
0x3a43  ldelem.ref
0x3a44  stloc.2
0x3a45  ldloc.2
0x3a46  ldtoken  Microsoft.ManagementConsole.SnapInSettingsAttribute
0x3a4b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3a50  ldc.i4.0
0x3a51  callvirt instance object[] [mscorlib]System.Reflection.MemberInfo::GetCustomAttributes(class [mscorlib]System.Type, bool)
0x3a56  stloc.3
0x3a57  ldloc.3
0x3a58  ldlen
0x3a59  conv.i4
0x3a5a  ldc.i4.0
0x3a5b  ble.s    loc_3A76
0x3a5d  ldloc.2
0x3a5e  call     class [MMCFxCommon]Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo Microsoft.ManagementConsole.SnapInRegistration::LoadFromType(class [mscorlib]System.Type type)
0x3a63  stloc.s  4
0x3a65  ldloc.s  4
0x3a67  brfalse.s loc_3A76
0x3a69  ldloc.0
0x3a6a  ldloc.2
0x3a6b  call     class [MMCFxCommon]Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo Microsoft.ManagementConsole.SnapInRegistration::LoadFromType(class [mscorlib]System.Type type)
0x3a70  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x3a75  pop
0x3a76  ldloc.s  6
0x3a78  ldc.i4.1
0x3a79  add
0x3a7a  stloc.s  6
0x3a7c  ldloc.s  6
0x3a7e  ldloc.s  5
0x3a80  ldlen
0x3a81  conv.i4
0x3a82  blt.s    loc_3A3F
0x3a84  ldloc.0
0x3a85  ldtoken  [MMCFxCommon]Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo
0x3a8a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3a8f  callvirt instance class [mscorlib]System.Array [mscorlib]System.Collections.ArrayList::ToArray(class [mscorlib]System.Type)
0x3a94  castclass class [MMCFxCommon]Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo[]
0x3a99  ret
```
