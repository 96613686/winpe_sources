# std::error_category::~error_category(void)

- ea: `0x1800063e0`
- end: `0x1800063eb`
- name: `??1error_category@std@@UEAA@XZ`
- size: `11`
- prototype: `void __fastcall(std::error_category *__hidden this)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x18000c6b4`
- `0x18000c6c6`
- `0x18000c6ea`
- `0x18000c70e`
- `0x18000c732`

## pseudocode

```c
void __fastcall std::error_category::~error_category(std::error_category *this)
{
  *(_QWORD *)this = &std::error_category::`vftable';
}

```

## disassembly

```asm
0x1800063e0  lea     rax, ??_7error_category@std@@6B@; const std::error_category::`vftable'
0x1800063e7  mov     [rcx], rax
0x1800063ea  retn
```
