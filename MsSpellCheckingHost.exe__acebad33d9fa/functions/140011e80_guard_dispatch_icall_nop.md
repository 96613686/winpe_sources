# _guard_dispatch_icall_nop

- ea: `0x140011e80`
- end: `0x140011e82`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x140001958`
- `0x140001c28`
- `0x140011e50`
- `0x140011eb0`

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
0x140011e80  jmp     rax
```
