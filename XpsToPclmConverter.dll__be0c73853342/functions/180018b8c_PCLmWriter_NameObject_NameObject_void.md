# PCLmWriter::NameObject::~NameObject(void)

- ea: `0x180018b8c`
- end: `0x180018bae`
- name: `??1NameObject@PCLmWriter@@UEAA@XZ`
- size: `34`
- prototype: `void __fastcall(PCLmWriter::NameObject *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180018d40`
- `0x180018fb0`
- `0x180019db0`
- `0x18001dfe6`
- `0x18001e075`

## callees

- `0x180010718`

## pseudocode

```c
void __fastcall PCLmWriter::NameObject::~NameObject(PCLmWriter::NameObject *this)
{
  std::string::_Tidy_deallocate((char *)this + 24);
  *(_QWORD *)this = &PCLmWriter::IObject::`vftable';
}

```

## disassembly

```asm
0x180018b8c  push    rbx
0x180018b8e  sub     rsp, 20h
0x180018b92  mov     rbx, rcx
0x180018b95  add     rcx, 18h
0x180018b99  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180018b9e  lea     rax, ??_7IObject@PCLmWriter@@6B@; const PCLmWriter::IObject::`vftable'
0x180018ba5  mov     [rbx], rax
0x180018ba8  add     rsp, 20h
0x180018bac  pop     rbx
0x180018bad  retn
```
