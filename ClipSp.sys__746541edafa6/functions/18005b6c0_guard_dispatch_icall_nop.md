# _guard_dispatch_icall_nop

- ea: `0x18005b6c0`
- end: `0x18005b6c2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `16`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1800332d0`
- `0x180033894`
- `0x18003391c`
- `0x180033a00`
- `0x18005b6f0`
- `0x1800e6010`
- `0x1800e83c4`
- `0x1800e92f8`
- `0x1800e9950`
- `0x1800ec4b0`
- `0x1800ec820`
- `0x1800f1760`
- `0x1800f2130`
- `0x1800f2210`
- `0x1800f3ae0`
- `0x18010a230`

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
0x18005b6c0  jmp     rax
```
