# Microsoft.ManagementConsole.SnapInInstaller::Install

- ea: `0x39b0`
- end: `0x39de`
- name: `Microsoft.ManagementConsole.SnapInInstaller::Install`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x39b0`
- `0x3a20`

## pseudocode

```c

```

## disassembly

```asm
0x39b0  ldarg.0
0x39b1  call     instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo[] Microsoft.ManagementConsole.SnapInInstaller::ReflectSnapIn()
0x39b6  stloc.0
0x39b7  ldloc.0
0x39b8  ldlen
0x39b9  conv.i4
0x39ba  brfalse.s loc_39D6
0x39bc  ldloc.0
0x39bd  stloc.2
0x39be  ldc.i4.0
0x39bf  stloc.3
0x39c0  br.s     loc_39D0
0x39c2  ldloc.2
0x39c3  ldloc.3
0x39c4  ldelem.ref
0x39c5  stloc.1
0x39c6  ldloc.1
0x39c7  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::WriteToStore()
0x39cc  ldloc.3
0x39cd  ldc.i4.1
0x39ce  add
0x39cf  stloc.3
0x39d0  ldloc.3
0x39d1  ldloc.2
0x39d2  ldlen
0x39d3  conv.i4
0x39d4  blt.s    loc_39C2
0x39d6  ldarg.0
0x39d7  ldarg.1
0x39d8  call     instance void [System.Configuration.Install]System.Configuration.Install.Installer::Install(class [mscorlib]System.Collections.IDictionary)
0x39dd  ret
```
