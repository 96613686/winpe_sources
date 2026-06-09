# _guard_dispatch_icall

- ea: `0x140001a70`
- end: `0x140001a76`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140003010`
- `0x14000a84c`
- `0x14000aa30`
- `0x14000aad0`
- `0x14000ab5c`

## callees

- `0x140001aa0`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall guard_dispatch_icall()
{
  __int64 (*v0)(void); // rax

  return v0();
}

```

## disassembly

```asm
0x140001a70  jmp     cs:__guard_dispatch_icall_fptr
```
