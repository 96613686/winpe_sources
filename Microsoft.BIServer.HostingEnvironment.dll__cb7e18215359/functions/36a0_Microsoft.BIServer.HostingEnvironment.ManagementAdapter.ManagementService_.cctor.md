# Microsoft.BIServer.HostingEnvironment.ManagementAdapter.ManagementService::.cctor

- ea: `0x36a0`
- end: `0x36ad`
- name: `Microsoft.BIServer.HostingEnvironment.ManagementAdapter.ManagementService::.cctor`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x36a0  ldc.i4.1
0x36a1  ldc.i4.1
0x36a2  newobj   instance void [mscorlib]System.Threading.SemaphoreSlim::.ctor(int32, int32)
0x36a7  stsfld   class [mscorlib]System.Threading.SemaphoreSlim Microsoft.BIServer.HostingEnvironment.ManagementAdapter.ManagementService::_cryptoSemaphore
0x36ac  ret
```
