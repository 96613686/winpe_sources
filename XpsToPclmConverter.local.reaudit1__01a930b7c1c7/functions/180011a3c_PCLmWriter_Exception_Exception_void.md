# PCLmWriter::Exception::~Exception(void)

- ea: `0x180011a3c`
- end: `0x180011a70`
- name: `??1Exception@PCLmWriter@@UEAA@XZ`
- size: `52`
- prototype: `void __fastcall(PCLmWriter::Exception *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180012140`
- `0x180014910`

## callees

- `0x180002042`
- `0x180010718`

## pseudocode

```c
void __fastcall PCLmWriter::Exception::~Exception(PCLmWriter::Exception *this)
{
  *(_QWORD *)this = &PCLmWriter::Exception::`vftable';
  std::string::_Tidy_deallocate((char *)this + 32);
  *(_QWORD *)this = &std::exception::`vftable';
  o___std_exception_destroy_0((char *)this + 8);
}

```

## disassembly

```asm
0x180011a3c  push    rbx
0x180011a3e  sub     rsp, 20h
0x180011a42  lea     rax, ??_7Exception@PCLmWriter@@6B@; const PCLmWriter::Exception::`vftable'
0x180011a49  mov     rbx, rcx
0x180011a4c  mov     [rcx], rax
0x180011a4f  add     rcx, 20h ; ' '
0x180011a53  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180011a58  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x180011a5f  lea     rcx, [rbx+8]
0x180011a63  mov     [rbx], rax
0x180011a66  add     rsp, 20h
0x180011a6a  pop     rbx
0x180011a6b  jmp     _o___std_exception_destroy_0
```
