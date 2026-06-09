# RSWPTraceInternal::get_TraceConfig

- ea: `0x16b80`
- end: `0x16bc7`
- name: `RSWPTraceInternal::get_TraceConfig`
- size: `71`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x16bd0`
- `0x16c20`

## callees

- `0xd150`
- `0xd1a0`
- `0x16b80`
- `0x181f0`

## pseudocode

```c

```

## disassembly

```asm
0x16b80  newobj   instance void <>c__DisplayClass60_0::.ctor()
0x16b85  stloc.0
0x16b86  ldloc.0
0x16b87  ldarg.0
0x16b88  stfld    class RSWPTraceInternal <>c__DisplayClass60_0::<>4__this
0x16b8d  ldarg.0
0x16b8e  ldfld    class RSTraceConfig RSWPTraceInternal::m_config
0x16b93  brtrue.s loc_16BC0
0x16b95  ldloc.0
0x16b96  ldnull
0x16b97  stfld    class RSTraceConfig <>c__DisplayClass60_0::config
0x16b9c  ldloc.0
0x16b9d  ldnull
0x16b9e  stfld    string <>c__DisplayClass60_0::configFileName
0x16ba3  ldloc.0
0x16ba4  ldftn    instance void <>c__DisplayClass60_0::<get_TraceConfig>b__0()
0x16baa  newobj   instance void Microsoft.ReportingServices.Diagnostics.ContextBody::.ctor(object object, native int method)
0x16baf  call     void Microsoft.ReportingServices.Diagnostics.RevertImpersonationContext::Run(class Microsoft.ReportingServices.Diagnostics.ContextBody callback)
0x16bb4  ldarg.0
0x16bb5  ldloc.0
0x16bb6  ldfld    class RSTraceConfig <>c__DisplayClass60_0::config
0x16bbb  stfld    class RSTraceConfig RSWPTraceInternal::m_config
0x16bc0  ldarg.0
0x16bc1  ldfld    class RSTraceConfig RSWPTraceInternal::m_config
0x16bc6  ret
```
