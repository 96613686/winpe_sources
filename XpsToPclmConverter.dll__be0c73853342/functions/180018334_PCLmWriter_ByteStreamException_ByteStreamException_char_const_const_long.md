# PCLmWriter::ByteStreamException::ByteStreamException(char const * const &,long)

- ea: `0x180018334`
- end: `0x1800183a9`
- name: `??0ByteStreamException@PCLmWriter@@QEAA@AEBQEBDJ@Z`
- size: `117`
- prototype: `__int64 __fastcall(PCLmWriter::ByteStreamException *__hidden this, const char *const *, int)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x1800184a0`
- `0x18001a2b0`
- `0x18001a7d0`
- `0x18001a854`

## callees

- `0x1800015f0`
- `0x18000f3e0`
- `0x180010718`
- `0x180011600`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
PCLmWriter::ByteStreamException *__fastcall PCLmWriter::ByteStreamException::ByteStreamException(
        PCLmWriter::ByteStreamException *this,
        const char *const *a2,
        unsigned int a3)
{
  _BYTE v6[32]; // [rsp+30h] [rbp-38h] BYREF

  std::string::string(v6, *a2);
  PCLmWriter::Exception::Exception(this, (__int64)v6, a3);
  std::string::_Tidy_deallocate(v6);
  *(_QWORD *)this = &PCLmWriter::ByteStreamException::`vftable';
  return this;
}

```

## disassembly

```asm
0x180018334  mov     [rsp+arg_18], rbx
0x180018339  push    rdi
0x18001833a  sub     rsp, 60h
0x18001833e  mov     rax, cs:__security_cookie
0x180018345  xor     rax, rsp
0x180018348  mov     [rsp+68h+var_18], rax
0x18001834d  mov     ebx, r8d
0x180018350  mov     rdi, rcx
0x180018353  mov     [rsp+68h+var_48], rcx
0x180018358  mov     rdx, [rdx]
0x18001835b  lea     rcx, [rsp+68h+var_38]
0x180018360  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180018365  nop
0x180018366  mov     r8d, ebx
0x180018369  lea     rdx, [rsp+68h+var_38]
0x18001836e  mov     rcx, rdi; this
0x180018371  call    ??0Exception@PCLmWriter@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@J@Z; PCLmWriter::Exception::Exception(std::string const &,long)
0x180018376  nop
0x180018377  lea     rcx, [rsp+68h+var_38]
0x18001837c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180018381  lea     rax, ??_7ByteStreamException@PCLmWriter@@6B@; const PCLmWriter::ByteStreamException::`vftable'
0x180018388  mov     [rdi], rax
0x18001838b  mov     rax, rdi
0x18001838e  mov     rcx, [rsp+68h+var_18]
0x180018393  xor     rcx, rsp; StackCookie
0x180018396  call    __security_check_cookie
0x18001839b  mov     rbx, [rsp+68h+arg_18]
0x1800183a3  add     rsp, 60h
0x1800183a7  pop     rdi
0x1800183a8  retn
```
