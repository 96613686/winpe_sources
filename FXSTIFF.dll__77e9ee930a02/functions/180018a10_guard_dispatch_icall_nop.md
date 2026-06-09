# _guard_dispatch_icall_nop

- ea: `0x180018a10`
- end: `0x180018a12`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001290`
- `0x180001504`
- `0x18000191c`
- `0x180018a40`
- `0x180018ad0`

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
0x180018a10  jmp     rax
```
