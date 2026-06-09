# PCLmWriter::InvalidObjectException::InvalidObjectException(long)

- ea: `0x180018950`
- end: `0x1800189bd`
- name: `??0InvalidObjectException@PCLmWriter@@QEAA@J@Z`
- size: `109`
- prototype: `__int64 __fastcall(PCLmWriter::InvalidObjectException *__hidden this, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800189c4`

## callees

- `0x1800015f0`
- `0x18000f3e0`
- `0x180010718`
- `0x180011600`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
PCLmWriter::InvalidObjectException *__fastcall PCLmWriter::InvalidObjectException::InvalidObjectException(
        PCLmWriter::InvalidObjectException *this)
{
  _BYTE v3[32]; // [rsp+30h] [rbp-38h] BYREF

  std::string::string(v3, "Name is invalid");
  PCLmWriter::Exception::Exception(this, (__int64)v3, 0x80048001);
  std::string::_Tidy_deallocate(v3);
  *(_QWORD *)this = &PCLmWriter::InvalidObjectException::`vftable';
  return this;
}

```

## disassembly

```asm
0x180018950  push    rbx
0x180018952  sub     rsp, 60h
0x180018956  mov     rax, cs:__security_cookie
0x18001895d  xor     rax, rsp
0x180018960  mov     [rsp+68h+var_18], rax
0x180018965  mov     rbx, rcx
0x180018968  mov     [rsp+68h+var_48], rcx
0x18001896d  lea     rdx, aNameIsInvalid; "Name is invalid"
0x180018974  lea     rcx, [rsp+68h+var_38]
0x180018979  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18001897e  nop
0x18001897f  mov     r8d, 80048001h
0x180018985  lea     rdx, [rsp+68h+var_38]
0x18001898a  mov     rcx, rbx; this
0x18001898d  call    ??0Exception@PCLmWriter@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@J@Z; PCLmWriter::Exception::Exception(std::string const &,long)
0x180018992  nop
0x180018993  lea     rcx, [rsp+68h+var_38]
0x180018998  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18001899d  lea     rax, ??_7InvalidObjectException@PCLmWriter@@6B@; const PCLmWriter::InvalidObjectException::`vftable'
0x1800189a4  mov     [rbx], rax
0x1800189a7  mov     rax, rbx
0x1800189aa  mov     rcx, [rsp+68h+var_18]
0x1800189af  xor     rcx, rsp; StackCookie
0x1800189b2  call    __security_check_cookie
0x1800189b7  add     rsp, 60h
0x1800189bb  pop     rbx
0x1800189bc  retn
```
