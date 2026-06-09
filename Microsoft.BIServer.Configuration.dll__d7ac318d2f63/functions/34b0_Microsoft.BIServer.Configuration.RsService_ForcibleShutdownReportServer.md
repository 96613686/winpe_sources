# Microsoft.BIServer.Configuration.RsService::ForcibleShutdownReportServer

- ea: `0x34b0`
- end: `0x34f3`
- name: `Microsoft.BIServer.Configuration.RsService::ForcibleShutdownReportServer`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x3360`

## callees

- `0x34a0`
- `0x34b0`

## pseudocode

```c

```

## disassembly

```asm
0x34b0  ldarg.0
0x34b1  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System]System.Diagnostics.Process> Microsoft.BIServer.Configuration.RsService::GetProcesses()
0x34b6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System]System.Diagnostics.Process>::GetEnumerator()
0x34bb  stloc.0
0x34bc  br.s     loc_34DE
0x34be  ldloc.0
0x34bf  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System]System.Diagnostics.Process>::get_Current()
0x34c4  stloc.1
0x34c5  ldloc.1
0x34c6  callvirt instance void [System]System.Diagnostics.Process::Kill()
0x34cb  leave.s  loc_34DE
0x34cd  ldstr    aExceptionEncou_0// "Exception encountered killing report se"...
0x34d2  call     T0x2B000015
0x34d7  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Fatal(class [mscorlib]System.Exception, string, object[])
0x34dc  leave.s  loc_34DE
0x34de  ldloc.0
0x34df  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x34e4  brtrue.s loc_34BE
0x34e6  leave.s  loc_34F2
0x34e8  ldloc.0
0x34e9  brfalse.s loc_34F1
0x34eb  ldloc.0
0x34ec  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x34f1  endfinally
0x34f2  ret
```
