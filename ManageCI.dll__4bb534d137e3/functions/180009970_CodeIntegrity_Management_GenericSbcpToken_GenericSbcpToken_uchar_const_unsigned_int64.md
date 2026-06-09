# CodeIntegrity::Management::GenericSbcpToken::GenericSbcpToken(uchar const *,unsigned __int64)

- ea: `0x180009970`
- end: `0x1800099f2`
- name: `??0GenericSbcpToken@Management@CodeIntegrity@@QEAA@PEBE_K@Z`
- size: `130`
- prototype: `CodeIntegrity::Management::GenericSbcpToken *__fastcall(CodeIntegrity::Management::GenericSbcpToken *this, const unsigned __int8 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180009490`

## callees

- `0x180009970`
- `0x18000df40`
- `0x1800109b4`
- `0x180016588`
- `0x180016958`
- `0x180016b24`

## pseudocode

```c
CodeIntegrity::Management::GenericSbcpToken *__fastcall CodeIntegrity::Management::GenericSbcpToken::GenericSbcpToken(
        CodeIntegrity::Management::GenericSbcpToken *this,
        const unsigned __int8 *a2)
{
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // rdx

  *(_QWORD *)this = &CodeIntegrity::Management::detail::SbcpTokenView::`vftable';
  *((_WORD *)this + 4) = 0;
  *((_QWORD *)this + 2) = 0;
  std::wstring::wstring((char *)this + 24, a2);
  std::wstring::wstring((char *)this + 56, v3);
  std::vector<unsigned char>::vector<unsigned char>((char *)this + 88, v5, v5 + v4);
  std::vector<unsigned char>::vector<unsigned char>((char *)this + 112, 0);
  CodeIntegrity::Management::detail::SbcpTokenView::CheckSignature(this);
  if ( !*((_WORD *)this + 4) )
    CodeIntegrity::Management::detail::SbcpTokenView::ParseSbcpToken(this);
  *(_QWORD *)this = &CodeIntegrity::Management::GenericSbcpToken::`vftable';
  return this;
}

```

## disassembly

```asm
0x180009970  mov     [rsp+arg_8], rbx
0x180009975  mov     [rsp+arg_0], rcx
0x18000997a  push    rdi
0x18000997b  sub     rsp, 20h
0x18000997f  mov     rbx, rcx
0x180009982  lea     rax, ??_7SbcpTokenView@detail@Management@CodeIntegrity@@6B@; const CodeIntegrity::Management::detail::SbcpTokenView::`vftable'
0x180009989  mov     [rcx], rax
0x18000998c  xor     edi, edi
0x18000998e  mov     [rcx+8], di
0x180009992  mov     [rcx+10h], rdi
0x180009996  add     rcx, 18h
0x18000999a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000999f  nop
0x1800099a0  lea     rcx, [rbx+38h]
0x1800099a4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800099a9  nop
0x1800099aa  add     r8, rdx
0x1800099ad  lea     rcx, [rbx+58h]
0x1800099b1  call    ??$?0PEBE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@PEBE0AEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(uchar const *,uchar const *,std::allocator<uchar> const &)
0x1800099b6  nop
0x1800099b7  lea     rcx, [rbx+70h]
0x1800099bb  xor     edx, edx
0x1800099bd  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x1800099c2  nop
0x1800099c3  mov     rcx, rbx; this
0x1800099c6  call    ?CheckSignature@SbcpTokenView@detail@Management@CodeIntegrity@@AEAAXXZ; CodeIntegrity::Management::detail::SbcpTokenView::CheckSignature(void)
0x1800099cb  cmp     [rbx+8], di
0x1800099cf  jnz     short loc_1800099DA
0x1800099d1  mov     rcx, rbx; this
0x1800099d4  call    ?ParseSbcpToken@SbcpTokenView@detail@Management@CodeIntegrity@@AEAAXXZ; CodeIntegrity::Management::detail::SbcpTokenView::ParseSbcpToken(void)
0x1800099d9  nop
0x1800099da  lea     rax, ??_7GenericSbcpToken@Management@CodeIntegrity@@6B@; const CodeIntegrity::Management::GenericSbcpToken::`vftable'
0x1800099e1  mov     [rbx], rax
0x1800099e4  mov     rax, rbx
0x1800099e7  mov     rbx, [rsp+28h+arg_8]
0x1800099ec  add     rsp, 20h
0x1800099f0  pop     rdi
0x1800099f1  retn
```
