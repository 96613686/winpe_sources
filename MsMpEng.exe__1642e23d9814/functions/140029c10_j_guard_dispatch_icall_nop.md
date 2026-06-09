# j__guard_dispatch_icall_nop

- ea: `0x140029c10`
- end: `0x140029c16`
- name: `j__guard_dispatch_icall_nop`
- size: `6`
- prototype: ``
- caller_count: `18`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1400149b0`
- `0x140014b04`
- `0x140015fe4`
- `0x140017b04`
- `0x140017cb0`
- `0x140018424`
- `0x14001845c`
- `0x1400184d0`
- `0x1400186a4`
- `0x140018a90`
- `0x140018db4`
- `0x140019128`
- `0x14001cf28`
- `0x14001cf84`
- `0x14001d07c`
- `0x14001d170`
- `0x14001f038`
- `0x14001f0b8`

## callees

- `0x140029bd0`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall j__guard_dispatch_icall_nop()
{
  __int64 (__fastcall *v0)(); // rax

  return v0();
}

```

## disassembly

```asm
0x140029c10  jmp     cs:__guard_dispatch_icall_fptr
```
