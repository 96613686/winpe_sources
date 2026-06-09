# _guard_dispatch_icall_nop

- ea: `0x18000d340`
- end: `0x18000d342`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180009bc0`
- `0x180009e34`
- `0x18000a058`
- `0x18000d370`
- `0x18000d400`

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
0x18000d340  jmp     rax
```
