# Microsoft.BIServer.Configuration.WMI.WmiProvider::UnEscapeInstanceName

- ea: `0x59d0`
- end: `0x5a2d`
- name: `Microsoft.BIServer.Configuration.WMI.WmiProvider::UnEscapeInstanceName`
- size: `93`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x5820`
- `0x58d0`

## callees

- `0x59d0`

## pseudocode

```c

```

## disassembly

```asm
0x59d0  ldarg.0
0x59d1  stloc.0
0x59d2  ldarg.0
0x59d3  ldstr    aRs// "RS_"
0x59d8  ldc.i4.5
0x59d9  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x59de  brfalse.s loc_5A2B
0x59e0  ldarg.0
0x59e1  ldc.i4.0
0x59e2  ldc.i4.3
0x59e3  callvirt instance string [mscorlib]System.String::Remove(int32, int32)
0x59e8  stloc.0
0x59e9  ldstr    a24// "_24"
0x59ee  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string)
0x59f3  ldloc.0
0x59f4  ldstr    asc_94A2// "$"
0x59f9  callvirt instance string [System]System.Text.RegularExpressions.Regex::Replace(string, string)
0x59fe  stloc.0
0x59ff  ldstr    a23// "_23"
0x5a04  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string)
0x5a09  ldloc.0
0x5a0a  ldstr    asc_B40E// "#"
0x5a0f  callvirt instance string [System]System.Text.RegularExpressions.Regex::Replace(string, string)
0x5a14  stloc.0
0x5a15  ldstr    a5f// "_5f"
0x5a1a  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string)
0x5a1f  ldloc.0
0x5a20  ldstr    asc_B40A// "_"
0x5a25  callvirt instance string [System]System.Text.RegularExpressions.Regex::Replace(string, string)
0x5a2a  stloc.0
0x5a2b  ldloc.0
0x5a2c  ret
```
