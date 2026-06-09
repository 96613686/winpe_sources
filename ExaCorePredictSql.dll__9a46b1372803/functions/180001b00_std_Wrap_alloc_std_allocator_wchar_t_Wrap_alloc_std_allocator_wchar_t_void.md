# std::_Wrap_alloc<std::allocator<wchar_t>>::_Wrap_alloc<std::allocator<wchar_t>>(void)

- ea: `0x180001b00`
- end: `0x180001b04`
- name: `??0?$_Wrap_alloc@V?$allocator@_W@std@@@std@@QEAA@XZ`
- size: `4`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180001000`
- `0x1800011a0`

## pseudocode

```c
__int64 __fastcall std::_Wrap_alloc<std::allocator<wchar_t>>::_Wrap_alloc<std::allocator<wchar_t>>(__int64 a1)
{
  return a1;
}

```

## disassembly

```asm
0x180001b00  mov     rax, rcx
0x180001b03  retn
```
