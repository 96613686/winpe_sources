# Microsoft.ManagementConsole.SnapInInstaller::RemoveAssemblySnapInsFromRegistry

- ea: `0x3a00`
- end: `0x3a20`
- name: `Microsoft.ManagementConsole.SnapInInstaller::RemoveAssemblySnapInsFromRegistry`
- size: `32`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x39e0`
- `0x39f0`

## callees

- `0x3a00`
- `0x3a20`

## pseudocode

```c

```

## disassembly

```asm
0x3a00  ldarg.0
0x3a01  call     instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo[] Microsoft.ManagementConsole.SnapInInstaller::ReflectSnapIn()
0x3a06  stloc.1
0x3a07  ldc.i4.0
0x3a08  stloc.2
0x3a09  br.s     loc_3A19
0x3a0b  ldloc.1
0x3a0c  ldloc.2
0x3a0d  ldelem.ref
0x3a0e  stloc.0
0x3a0f  ldloc.0
0x3a10  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::RemoveFromStore()
0x3a15  ldloc.2
0x3a16  ldc.i4.1
0x3a17  add
0x3a18  stloc.2
0x3a19  ldloc.2
0x3a1a  ldloc.1
0x3a1b  ldlen
0x3a1c  conv.i4
0x3a1d  blt.s    loc_3A0B
0x3a1f  ret
```
