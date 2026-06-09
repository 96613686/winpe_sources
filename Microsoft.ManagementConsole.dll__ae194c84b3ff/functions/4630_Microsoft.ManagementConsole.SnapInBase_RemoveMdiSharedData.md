# Microsoft.ManagementConsole.SnapInBase::RemoveMdiSharedData

- ea: `0x4630`
- end: `0x464a`
- name: `Microsoft.ManagementConsole.SnapInBase::RemoveMdiSharedData`
- size: `26`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4430`

## callees

- `0x4630`

## pseudocode

```c

```

## disassembly

```asm
0x4630  ldarg.0
0x4631  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ManagementConsole.SnapInBase::_mdiSharedData
0x4636  brfalse.s loc_4649
0x4638  ldarg.0
0x4639  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ManagementConsole.SnapInBase::_mdiSharedData
0x463e  ldarg.1
0x463f  box      [mscorlib]System.Int32
0x4644  callvirt instance void [mscorlib]System.Collections.Hashtable::Remove(object)
0x4649  ret
```
