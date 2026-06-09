# std::_Generic_error_category::~_Generic_error_category(void)

- ea: `0x1800063a4`
- end: `0x1800063b4`
- name: `??1_Generic_error_category@std@@UEAA@XZ`
- size: `16`
- prototype: `void __fastcall(std::_Generic_error_category *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18000c6d8`
- `0x18000c6fc`
- `0x18000c720`

## pseudocode

```c
void __fastcall std::_Generic_error_category::~_Generic_error_category(std::_Generic_error_category *this)
{
  *(_QWORD *)this = &std::error_category::`vftable';
}

```

## disassembly

```asm
0x1800063a4  mov     [rsp+arg_0], rcx
0x1800063a9  lea     rax, ??_7error_category@std@@6B@; const std::error_category::`vftable'
0x1800063b0  mov     [rcx], rax
0x1800063b3  retn
```
