# _guard_dispatch_icall

- ea: `0x140004c70`
- end: `0x140004c76`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `20`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140001348`
- `0x140001990`
- `0x140002740`
- `0x140002e0c`
- `0x140003140`
- `0x140003304`
- `0x1400036f0`
- `0x140003e14`
- `0x140003f70`
- `0x140004060`
- `0x140004220`
- `0x140004438`
- `0x1400045c4`
- `0x140007080`
- `0x140011264`
- `0x140011748`
- `0x1400117f0`
- `0x1400118b8`
- `0x140011a00`
- `0x140026120`

## callees

- `0x140004c10`

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
0x140004c70  jmp     cs:__guard_dispatch_icall_fptr
```
