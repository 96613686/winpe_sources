# Microsoft.BIServer.HostingEnvironment.SafeTokenHandle::ReleaseHandle

- ea: `0x1fb0`
- end: `0x1fbc`
- name: `Microsoft.BIServer.HostingEnvironment.SafeTokenHandle::ReleaseHandle`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1fa0`

## pseudocode

```c

```

## disassembly

```asm
0x1fb0  ldarg.0
0x1fb1  ldfld    native int [mscorlib]System.Runtime.InteropServices.SafeHandle::handle
0x1fb6  call     bool Microsoft.BIServer.HostingEnvironment.SafeTokenHandle::CloseHandle([hasfieldmarshal] native int)
0x1fbb  ret
```
