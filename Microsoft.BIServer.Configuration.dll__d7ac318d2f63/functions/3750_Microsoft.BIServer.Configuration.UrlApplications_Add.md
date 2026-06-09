# Microsoft.BIServer.Configuration.UrlApplications::Add

- ea: `0x3750`
- end: `0x3785`
- name: `Microsoft.BIServer.Configuration.UrlApplications::Add`
- size: `53`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x3990`
- `0x39c0`

## callees

- `0x3750`
- `0x3790`

## pseudocode

```c

```

## disassembly

```asm
0x3750  ldarg.1
0x3751  dup
0x3752  brtrue.s loc_375A
0x3754  pop
0x3755  call     T0x2B000011
0x375a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.BIServer.Configuration.Application>::GetEnumerator()
0x375f  stloc.0
0x3760  br.s     loc_3770
0x3762  ldloc.0
0x3763  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.BIServer.Configuration.Application>::get_Current()
0x3768  stloc.1
0x3769  ldarg.0
0x376a  ldloc.1
0x376b  call     instance void Microsoft.BIServer.Configuration.UrlApplications::Add(class Microsoft.BIServer.Configuration.Application app)
0x3770  ldloc.0
0x3771  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3776  brtrue.s loc_3762
0x3778  leave.s  loc_3784
0x377a  ldloc.0
0x377b  brfalse.s loc_3783
0x377d  ldloc.0
0x377e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3783  endfinally
0x3784  ret
```
