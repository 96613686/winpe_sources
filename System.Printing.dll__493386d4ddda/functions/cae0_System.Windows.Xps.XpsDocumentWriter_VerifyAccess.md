# System.Windows.Xps.XpsDocumentWriter::VerifyAccess

- ea: `0xcae0`
- end: `0xcaff`
- name: `System.Windows.Xps.XpsDocumentWriter::VerifyAccess`
- size: `31`
- prototype: ``
- caller_count: `37`
- callee_count: `3`
- tags: ``

## callers

- `0xb4e0`
- `0xb510`
- `0xb530`
- `0xb560`
- `0xb580`
- `0xb5b0`
- `0xb5d0`
- `0xb600`
- `0xb620`
- `0xb650`
- `0xb670`
- `0xb730`
- `0xb740`
- `0xb760`
- `0xb780`
- `0xb7c0`
- `0xb7f0`
- `0xb810`
- `0xb830`
- `0xb870`
- `0xb8a0`
- `0xb8c0`
- `0xb8e0`
- `0xb920`
- `0xb950`
- `0xb970`
- `0xb990`
- `0xb9d0`
- `0xba00`
- `0xba20`
- `0xba40`
- `0xba80`
- `0xbab0`
- `0xbb20`
- `0xbb30`
- `0xbc20`
- `0xbc90`

## callees

- `0xac10`
- `0xac20`
- `0xcae0`

## pseudocode

```c

```

## disassembly

```asm
0xcae0  ldarg.0
0xcae1  ldfld    class System.Printing.PrintSystemDispatcherObject System.Windows.Xps.XpsDocumentWriter::accessVerifier
0xcae6  brtrue.s loc_CAF3
0xcae8  ldarg.0
0xcae9  newobj   instance void System.Printing.PrintSystemDispatcherObject::.ctor()
0xcaee  stfld    class System.Printing.PrintSystemDispatcherObject System.Windows.Xps.XpsDocumentWriter::accessVerifier
0xcaf3  ldarg.0
0xcaf4  ldfld    class System.Printing.PrintSystemDispatcherObject System.Windows.Xps.XpsDocumentWriter::accessVerifier
0xcaf9  call     instance void System.Printing.PrintSystemDispatcherObject::VerifyThreadLocality()
0xcafe  ret
```
