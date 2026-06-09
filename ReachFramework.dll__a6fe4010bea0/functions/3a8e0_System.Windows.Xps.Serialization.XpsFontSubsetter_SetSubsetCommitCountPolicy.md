# System.Windows.Xps.Serialization.XpsFontSubsetter::SetSubsetCommitCountPolicy

- ea: `0x3a8e0`
- end: `0x3a919`
- name: `System.Windows.Xps.Serialization.XpsFontSubsetter::SetSubsetCommitCountPolicy`
- size: `57`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x27250`
- `0x29230`

## callees

- `0x1ef70`
- `0x3a8e0`

## string_xrefs

- `0x3a901`: `ReachPackaging_CommitCountPolicyLessThan1`

## pseudocode

```c

```

## disassembly

```asm
0x3a8e0  ldarg.0
0x3a8e1  ldfld    valuetype System.Windows.Xps.Serialization.FontSubsetterCommitPolicies System.Windows.Xps.Serialization.XpsFontSubsetter::_commitPolicy
0x3a8e6  ldc.i4.3
0x3a8e7  bne.un.s loc_3A8FD
0x3a8e9  ldarg.1
0x3a8ea  ldc.i4.1
0x3a8eb  beq.s    loc_3A8FD
0x3a8ed  ldstr    aReachpackaging_37// "ReachPackaging_SequenceCntMustBe1"
0x3a8f2  call     string System.Windows.Xps.SR::Get(string id)
0x3a8f7  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x3a8fc  throw
0x3a8fd  ldarg.1
0x3a8fe  ldc.i4.1
0x3a8ff  bge.s    loc_3A911
0x3a901  ldstr    aReachpackaging_38// "ReachPackaging_CommitCountPolicyLessTha"...
0x3a906  call     string System.Windows.Xps.SR::Get(string id)
0x3a90b  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x3a910  throw
0x3a911  ldarg.0
0x3a912  ldarg.1
0x3a913  stfld    int32 System.Windows.Xps.Serialization.XpsFontSubsetter::_commitCountPolicy
0x3a918  ret
```
