# _guard_dispatch_icall

- ea: `0x180002f30`
- end: `0x180002f52`
- name: `_guard_dispatch_icall`
- size: `34`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180004010`

## callees

- `0x180002f30`

## pseudocode

```c
__int64 __fastcall guard_dispatch_icall()
{
  __int64 (*v0)(void); // rax

  return v0();
}

```

## disassembly

```asm
0x180002f30  jmp     cs:__guard_dispatch_icall_fptr
0x180002f50  jmp     rax
```
