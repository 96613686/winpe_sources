# Microsoft.VisualStudio.Setup.Services.RpcServiceFacade::Dispose

- ea: `0x1bc0`
- end: `0x1bce`
- name: `Microsoft.VisualStudio.Setup.Services.RpcServiceFacade::Dispose`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1bd0`

## pseudocode

```c

```

## disassembly

```asm
0x1bc0  ldarg.0
0x1bc1  ldc.i4.1
0x1bc2  call     instance void Microsoft.VisualStudio.Setup.Services.RpcServiceFacade::Dispose(bool disposing)
0x1bc7  ldarg.0
0x1bc8  call     void [mscorlib]System.GC::SuppressFinalize(object)
0x1bcd  ret
```
