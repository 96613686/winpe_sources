# System.Printing.PrintServer::VerifyAccess

- ea: `0x13460`
- end: `0x1347f`
- name: `System.Printing.PrintServer::VerifyAccess`
- size: `31`
- prototype: ``
- caller_count: `39`
- callee_count: `3`
- tags: ``

## callers

- `0x11fe0`
- `0x12000`
- `0x12020`
- `0x12040`
- `0x12080`
- `0x12090`
- `0x120a0`
- `0x120b0`
- `0x120d0`
- `0x120f0`
- `0x12100`
- `0x12120`
- `0x12140`
- `0x12170`
- `0x121b0`
- `0x121f0`
- `0x12240`
- `0x12280`
- `0x122c0`
- `0x12300`
- `0x12340`
- `0x12380`
- `0x123c0`
- `0x12400`
- `0x12440`
- `0x12480`
- `0x124c0`
- `0x12500`
- `0x12540`
- `0x12580`
- `0x125c0`
- `0x12600`
- `0x12640`
- `0x12680`
- `0x126c0`
- `0x12700`
- `0x12740`
- `0x12780`
- `0x127c0`

## callees

- `0xac10`
- `0xac20`
- `0x13460`

## pseudocode

```c

```

## disassembly

```asm
0x13460  ldarg.0
0x13461  ldfld    class System.Printing.PrintSystemDispatcherObject System.Printing.PrintServer::accessVerifier
0x13466  brtrue.s loc_13473
0x13468  ldarg.0
0x13469  newobj   instance void System.Printing.PrintSystemDispatcherObject::.ctor()
0x1346e  stfld    class System.Printing.PrintSystemDispatcherObject System.Printing.PrintServer::accessVerifier
0x13473  ldarg.0
0x13474  ldfld    class System.Printing.PrintSystemDispatcherObject System.Printing.PrintServer::accessVerifier
0x13479  call     instance void System.Printing.PrintSystemDispatcherObject::VerifyThreadLocality()
0x1347e  ret
```
