# Microsoft.BIServer.Configuration.ConfigReader::TryGetInt

- ea: `0x17e0`
- end: `0x1817`
- name: `Microsoft.BIServer.Configuration.ConfigReader::TryGetInt`
- size: `55`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1760`
- `0x17c0`

## callees

- `0x17e0`
- `0x7840`

## pseudocode

```c

```

## disassembly

```asm
0x17e0  ldarg.s  4
0x17e2  ldloca.s 0
0x17e4  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0x17e9  brtrue.s loc_17FC
0x17eb  ldstr    aSetting0HasAnI// "Setting {0} has an invalid value."
0x17f0  ldarg.1
0x17f1  call     string [mscorlib]System.String::Format(string, object)
0x17f6  newobj   instance void InvalidSettingValue::.ctor(string message)
0x17fb  throw
0x17fc  ldloc.0
0x17fd  ldarg.2
0x17fe  blt.s    loc_1804
0x1800  ldloc.0
0x1801  ldarg.3
0x1802  ble.s    loc_1815
0x1804  ldstr    aSetting0HasAVa// "Setting {0} has a value out of the allo"...
0x1809  ldarg.1
0x180a  call     string [mscorlib]System.String::Format(string, object)
0x180f  newobj   instance void InvalidSettingValue::.ctor(string message)
0x1814  throw
0x1815  ldloc.0
0x1816  ret
```
