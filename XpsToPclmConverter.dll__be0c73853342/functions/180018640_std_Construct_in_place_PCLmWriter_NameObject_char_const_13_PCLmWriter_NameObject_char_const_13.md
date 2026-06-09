# std::_Construct_in_place<PCLmWriter::NameObject,char const (&)[13]>(PCLmWriter::NameObject &,char const (&)[13])

- ea: `0x180018640`
- end: `0x180018694`
- name: `??$_Construct_in_place@VNameObject@PCLmWriter@@AEAY0N@$$CBD@std@@YAXAEAVNameObject@PCLmWriter@@AEAY0N@$$CBD@Z`
- size: `84`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800199e0`

## callees

- `0x1800015f0`
- `0x18000f3e0`
- `0x180010718`
- `0x1800189c4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::_Construct_in_place<PCLmWriter::NameObject,char const (&)[13]>(__int64 a1, __int64 a2)
{
  _BYTE v4[32]; // [rsp+20h] [rbp-38h] BYREF

  std::string::string(v4, a2);
  PCLmWriter::NameObject::NameObject(a1, (__int64)v4, 0, 0);
  return std::string::_Tidy_deallocate(v4);
}

```

## disassembly

```asm
0x180018640  push    rbx
0x180018642  sub     rsp, 50h
0x180018646  mov     rax, cs:__security_cookie
0x18001864d  xor     rax, rsp
0x180018650  mov     [rsp+58h+var_18], rax
0x180018655  mov     rbx, rcx
0x180018658  lea     rcx, [rsp+58h+var_38]
0x18001865d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180018662  nop
0x180018663  xor     r9d, r9d
0x180018666  xor     r8d, r8d
0x180018669  lea     rdx, [rsp+58h+var_38]
0x18001866e  mov     rcx, rbx
0x180018671  call    ??0NameObject@PCLmWriter@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@II@Z; PCLmWriter::NameObject::NameObject(std::string const &,uint,uint)
0x180018676  nop
0x180018677  lea     rcx, [rsp+58h+var_38]
0x18001867c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180018681  mov     rcx, [rsp+58h+var_18]
0x180018686  xor     rcx, rsp; StackCookie
0x180018689  call    __security_check_cookie
0x18001868e  add     rsp, 50h
0x180018692  pop     rbx
0x180018693  retn
```
