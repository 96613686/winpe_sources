# _guard_dispatch_icall_nop

- ea: `0x18000fca0`
- end: `0x18000fca2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001be0`
- `0x180001e54`
- `0x18000247c`
- `0x18000fc70`
- `0x18000fcd0`

## pseudocode

```c
__int64 __fastcall guard_dispatch_icall_nop()
{
  __int64 (*v0)(void); // rax

  return v0();
}

```

## disassembly

```asm
0x18000fca0  jmp     rax
```
