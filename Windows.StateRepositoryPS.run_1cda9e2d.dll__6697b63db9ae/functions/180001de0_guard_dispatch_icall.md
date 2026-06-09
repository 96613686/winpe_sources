# _guard_dispatch_icall

- ea: `0x180001de0`
- end: `0x180001de6`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180002010`

## callees

- `0x180001e00`

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
0x180001de0  jmp     cs:__guard_dispatch_icall_fptr
```
