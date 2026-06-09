# System.Printing.PrintSystemDispatcherObject::VerifyThreadLocality

- ea: `0xac20`
- end: `0xac27`
- name: `System.Printing.PrintSystemDispatcherObject::VerifyThreadLocality`
- size: `7`
- prototype: ``
- caller_count: `13`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0xadf0`
- `0xaf50`
- `0xb0b0`
- `0xb160`
- `0xb2c0`
- `0xcae0`
- `0xd680`
- `0x110d0`
- `0x11d00`
- `0x13460`
- `0x13e10`
- `0x18950`
- `0x18ab0`

## pseudocode

```c

```

## disassembly

```asm
0xac20  ldarg.0
0xac21  call     instance void [WindowsBase]System.Windows.Threading.DispatcherObject::VerifyAccess()
0xac26  ret
```
