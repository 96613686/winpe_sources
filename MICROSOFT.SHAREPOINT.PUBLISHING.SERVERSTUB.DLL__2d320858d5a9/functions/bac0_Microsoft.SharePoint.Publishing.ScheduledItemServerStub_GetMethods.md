# Microsoft.SharePoint.Publishing.ScheduledItemServerStub::GetMethods

- ea: `0xbac0`
- end: `0xbad8`
- name: `Microsoft.SharePoint.Publishing.ScheduledItemServerStub::GetMethods`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xbed0`

## callees

- `0x21940`

## pseudocode

```c

```

## disassembly

```asm
0xbac0  ldc.i4.s 0xFE
0xbac2  newobj   instance void <GetMethods>d__2::.ctor(int32 <>1__state)
0xbac7  stloc.0
0xbac8  ldloc.0
0xbac9  ldarg.0
0xbaca  stfld    class Microsoft.SharePoint.Publishing.ScheduledItemServerStub <GetMethods>d__2::<>4__this
0xbacf  ldloc.0
0xbad0  ldarg.1
0xbad1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__2::<>3__proxyContext
0xbad6  ldloc.0
0xbad7  ret
```
