# Microsoft.BIServer.Management.WebApi.DatabaseUpgrade.DatabaseUpdateRulesEngine::StringOrNull

- ea: `0x6c0`
- end: `0x6d0`
- name: `Microsoft.BIServer.Management.WebApi.DatabaseUpgrade.DatabaseUpdateRulesEngine::StringOrNull`
- size: `16`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x600`
- `0x660`

## callees

- `0x6c0`

## pseudocode

```c

```

## disassembly

```asm
0x6c0  ldarg.0
0x6c1  brtrue.s loc_6C9
0x6c3  ldstr    aNull// "NULL"
0x6c8  ret
0x6c9  ldarg.0
0x6ca  callvirt instance string [mscorlib]System.Object::ToString()
0x6cf  ret
```
