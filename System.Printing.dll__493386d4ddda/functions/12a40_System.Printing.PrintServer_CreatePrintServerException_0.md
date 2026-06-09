# System.Printing.PrintServer::CreatePrintServerException_0

- ea: `0x12a40`
- end: `0x12a4e`
- name: `System.Printing.PrintServer::CreatePrintServerException_0`
- size: `14`
- prototype: ``
- caller_count: `28`
- callee_count: `1`
- tags: ``

## callers

- `0xdef0`
- `0xe0b0`
- `0xe120`
- `0xe1d0`
- `0x11af0`
- `0x11b80`
- `0x12140`
- `0x12170`
- `0x12600`
- `0x12680`
- `0x12810`
- `0x13070`
- `0x13280`
- `0x13590`
- `0x135e0`
- `0x13640`
- `0x136a0`
- `0x13700`
- `0x13750`
- `0x137b0`
- `0x138a0`
- `0x138d0`
- `0x13900`
- `0x13930`
- `0x13960`
- `0x13990`
- `0x13c20`
- `0x13d00`

## callees

- `0x12800`

## pseudocode

```c

```

## disassembly

```asm
0x12a40  ldarg.1
0x12a41  ldarg.2
0x12a42  ldarg.0
0x12a43  callvirt instance string System.Printing.PrintServer::get_Name()
0x12a48  newobj   instance void [ReachFramework]System.Printing.PrintServerException::.ctor(int32, string, string)
0x12a4d  ret
```
