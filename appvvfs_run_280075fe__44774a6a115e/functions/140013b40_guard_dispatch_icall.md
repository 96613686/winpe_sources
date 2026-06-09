# _guard_dispatch_icall

- ea: `0x140013b40`
- end: `0x140013b46`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1400090c8`
- `0x140011a64`
- `0x140012548`
- `0x140016010`
- `0x140024610`
- `0x140024690`
- `0x140025204`

## callees

- `0x140013b70`

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
0x140013b40  jmp     cs:__guard_dispatch_icall_fptr
```
