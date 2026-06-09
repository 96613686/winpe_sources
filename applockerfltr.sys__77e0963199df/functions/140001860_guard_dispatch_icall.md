# _guard_dispatch_icall

- ea: `0x140001860`
- end: `0x140001866`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140001044`
- `0x14000118c`
- `0x140002010`
- `0x1400078f0`
- `0x140008078`

## callees

- `0x140001890`

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
0x140001860  jmp     cs:__guard_dispatch_icall_fptr
```
