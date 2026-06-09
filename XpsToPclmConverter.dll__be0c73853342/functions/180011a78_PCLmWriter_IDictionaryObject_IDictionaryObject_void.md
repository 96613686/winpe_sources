# PCLmWriter::IDictionaryObject::~IDictionaryObject(void)

- ea: `0x180011a78`
- end: `0x180011a83`
- name: `??1IDictionaryObject@PCLmWriter@@UEAA@XZ`
- size: `11`
- prototype: `void __fastcall(PCLmWriter::IDictionaryObject *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18001d50a`
- `0x18001d5c6`
- `0x18001de94`
- `0x18001dece`

## pseudocode

```c
void __fastcall PCLmWriter::IDictionaryObject::~IDictionaryObject(PCLmWriter::IDictionaryObject *this)
{
  *(_QWORD *)this = &PCLmWriter::IObject::`vftable';
}

```

## disassembly

```asm
0x180011a78  lea     rax, ??_7IObject@PCLmWriter@@6B@; const PCLmWriter::IObject::`vftable'
0x180011a7f  mov     [rcx], rax
0x180011a82  retn
```
