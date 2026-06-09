# System.Printing.PrintSystemObject::Dispose

- ea: `0xa980`
- end: `0xa99c`
- name: `System.Printing.PrintSystemObject::Dispose`
- size: `28`
- prototype: ``
- caller_count: `36`
- callee_count: `3`
- tags: ``

## callers

- `0xa9a0`
- `0xa9b0`
- `0xace0`
- `0xae40`
- `0xafa0`
- `0xd960`
- `0xd9f0`
- `0xda80`
- `0xdaf0`
- `0xdb60`
- `0xdbd0`
- `0xdc40`
- `0xdcb0`
- `0xdd10`
- `0xdd70`
- `0x11d80`
- `0x11dd0`
- `0x11e10`
- `0x11e60`
- `0x11ea0`
- `0x11ee0`
- `0x11f20`
- `0x11f60`
- `0x11fa0`
- `0x13590`
- `0x135e0`
- `0x13640`
- `0x136a0`
- `0x13700`
- `0x13750`
- `0x137b0`
- `0x17380`
- `0x173e0`
- `0x17460`
- `0x175e0`
- `0x17690`

## callees

- `0xa6e0`
- `0xa800`
- `0xa980`

## pseudocode

```c

```

## disassembly

```asm
0xa980  ldarg.1
0xa981  brfalse.s loc_A98B
0xa983  ldarg.0
0xa984  call     instance void System.Printing.PrintSystemObject::~PrintSystemObject()
0xa989  br.s     loc_A99B
0xa98b  nop
0xa98c  ldarg.0
0xa98d  call     instance void System.Printing.PrintSystemObject::!PrintSystemObject()
0xa992  leave.s  loc_A99B
0xa994  ldarg.0
0xa995  call     instance void [mscorlib]System.Object::Finalize()
0xa99a  endfinally
0xa99b  ret
```
