# System.Printing.PrintSystemJobInfo::VerifyAccess

- ea: `0x18950`
- end: `0x1896f`
- name: `System.Printing.PrintSystemJobInfo::VerifyAccess`
- size: `31`
- prototype: ``
- caller_count: `49`
- callee_count: `3`
- tags: ``

## callers

- `0x17770`
- `0x177e0`
- `0x17850`
- `0x178c0`
- `0x17940`
- `0x17950`
- `0x17960`
- `0x179b0`
- `0x179c0`
- `0x17a00`
- `0x17a10`
- `0x17a60`
- `0x17ab0`
- `0x17ac0`
- `0x17b10`
- `0x17b20`
- `0x17b70`
- `0x17b80`
- `0x17bd0`
- `0x17be0`
- `0x17c30`
- `0x17c40`
- `0x17c90`
- `0x17cb0`
- `0x17d00`
- `0x17d10`
- `0x17d20`
- `0x17d30`
- `0x17d40`
- `0x17d50`
- `0x17d60`
- `0x17d70`
- `0x17d80`
- `0x17d90`
- `0x17da0`
- `0x17db0`
- `0x17dc0`
- `0x17dd0`
- `0x17de0`
- `0x17df0`
- `0x17e00`
- `0x17e10`
- `0x17e20`
- `0x17e30`
- `0x17e40`
- `0x17e50`
- `0x17e70`
- `0x17e80`
- `0x17e90`

## callees

- `0xac10`
- `0xac20`
- `0x18950`

## pseudocode

```c

```

## disassembly

```asm
0x18950  ldarg.0
0x18951  ldfld    class System.Printing.PrintSystemDispatcherObject System.Printing.PrintSystemJobInfo::accessVerifier
0x18956  brtrue.s loc_18963
0x18958  ldarg.0
0x18959  newobj   instance void System.Printing.PrintSystemDispatcherObject::.ctor()
0x1895e  stfld    class System.Printing.PrintSystemDispatcherObject System.Printing.PrintSystemJobInfo::accessVerifier
0x18963  ldarg.0
0x18964  ldfld    class System.Printing.PrintSystemDispatcherObject System.Printing.PrintSystemJobInfo::accessVerifier
0x18969  call     instance void System.Printing.PrintSystemDispatcherObject::VerifyThreadLocality()
0x1896e  ret
```
