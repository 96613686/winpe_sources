# _guard_dispatch_icall

- ea: `0x140007d40`
- end: `0x140007d46`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `33`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1400010d0`
- `0x140001328`
- `0x1400013e8`
- `0x1400014cc`
- `0x1400015cc`
- `0x1400016fc`
- `0x1400017e0`
- `0x1400018ec`
- `0x1400019c0`
- `0x140001ab8`
- `0x140001f44`
- `0x140002330`
- `0x1400024c0`
- `0x140002568`
- `0x14000295c`
- `0x140002b64`
- `0x140003428`
- `0x14000359c`
- `0x14000366c`
- `0x140003a34`
- `0x140003b54`
- `0x140003c44`
- `0x140004234`
- `0x140004340`
- `0x140007790`
- `0x140009010`
- `0x14001bda0`
- `0x14001c0a4`
- `0x14001c16c`
- `0x14001c2c0`
- `0x14001c560`
- `0x14001cf90`
- `0x140020078`

## callees

- `0x140007d70`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall guard_dispatch_icall()
{
  __int64 (__fastcall *v0)(); // rax

  return v0();
}

```

## disassembly

```asm
0x140007d40  jmp     cs:__guard_dispatch_icall_fptr
```
