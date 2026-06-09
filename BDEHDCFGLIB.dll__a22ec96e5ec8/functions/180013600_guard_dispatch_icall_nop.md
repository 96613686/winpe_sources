# _guard_dispatch_icall_nop

- ea: `0x180013600`
- end: `0x180013602`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001130`
- `0x1800013a4`
- `0x180001b10`
- `0x180013630`
- `0x1800136c0`

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
0x180013600  jmp     rax
```
