# CodeIntegrity::Management::AuthorizationToken::AuthorizationToken(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,uchar const *,unsigned __int64)

- ea: `0x1800184d8`
- end: `0x1800185a0`
- name: `??0AuthorizationToken@Management@CodeIntegrity@@AEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0PEBE_K@Z`
- size: `200`
- prototype: `CodeIntegrity::Management::detail::SbcpTokenView *__fastcall(CodeIntegrity::Management::detail::SbcpTokenView *this, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018834`

## callees

- `0x180004e34`
- `0x18000df40`
- `0x180010cdc`
- `0x180016588`
- `0x180016958`
- `0x180016b24`
- `0x1800184d8`

## pseudocode

```c
CodeIntegrity::Management::detail::SbcpTokenView *__fastcall CodeIntegrity::Management::AuthorizationToken::AuthorizationToken(
        CodeIntegrity::Management::detail::SbcpTokenView *this,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  *(_QWORD *)this = &CodeIntegrity::Management::detail::SbcpTokenView::`vftable';
  *((_WORD *)this + 4) = 0;
  *((_QWORD *)this + 2) = 0;
  std::wstring::wstring((char *)this + 24);
  std::wstring::wstring((char *)this + 56);
  std::vector<unsigned char>::vector<unsigned char>((char *)this + 88, a4, a4 + a5);
  std::vector<unsigned char>::vector<unsigned char>((char *)this + 112, 0);
  CodeIntegrity::Management::detail::SbcpTokenView::CheckSignature(this);
  if ( !*((_WORD *)this + 4) )
    CodeIntegrity::Management::detail::SbcpTokenView::ParseSbcpToken(this);
  *(_QWORD *)this = &CodeIntegrity::Management::AuthorizationToken::`vftable';
  std::vector<_GUID>::vector<_GUID>((char *)this + 136);
  std::vector<_GUID>::vector<_GUID>((char *)this + 160);
  std::vector<_GUID>::vector<_GUID>((char *)this + 184);
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_BYTE *)this + 224) = 2;
  return this;
}

```

## disassembly

```asm
0x1800184d8  mov     [rsp+arg_0], rcx
0x1800184dd  push    rbx
0x1800184de  push    rbp
0x1800184df  push    rsi
0x1800184e0  push    rdi
0x1800184e1  sub     rsp, 28h
0x1800184e5  mov     rdi, r9
0x1800184e8  mov     rbx, r8
0x1800184eb  mov     rsi, rcx
0x1800184ee  lea     rax, ??_7SbcpTokenView@detail@Management@CodeIntegrity@@6B@; const CodeIntegrity::Management::detail::SbcpTokenView::`vftable'
0x1800184f5  mov     [rcx], rax
0x1800184f8  xor     ebp, ebp
0x1800184fa  mov     [rcx+8], bp
0x1800184fe  mov     [rcx+10h], rbp
0x180018502  add     rcx, 18h
0x180018506  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001850b  nop
0x18001850c  lea     rcx, [rsi+38h]
0x180018510  mov     rdx, rbx
0x180018513  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180018518  nop
0x180018519  mov     r8, [rsp+48h+arg_20]
0x18001851e  add     r8, rdi
0x180018521  lea     rcx, [rsi+58h]
0x180018525  mov     rdx, rdi
0x180018528  call    ??$?0PEBE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@PEBE0AEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(uchar const *,uchar const *,std::allocator<uchar> const &)
0x18001852d  nop
0x18001852e  lea     rcx, [rsi+70h]
0x180018532  xor     edx, edx
0x180018534  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x180018539  nop
0x18001853a  mov     rcx, rsi; this
0x18001853d  call    ?CheckSignature@SbcpTokenView@detail@Management@CodeIntegrity@@AEAAXXZ; CodeIntegrity::Management::detail::SbcpTokenView::CheckSignature(void)
0x180018542  cmp     [rsi+8], bp
0x180018546  jnz     short loc_180018551
0x180018548  mov     rcx, rsi; this
0x18001854b  call    ?ParseSbcpToken@SbcpTokenView@detail@Management@CodeIntegrity@@AEAAXXZ; CodeIntegrity::Management::detail::SbcpTokenView::ParseSbcpToken(void)
0x180018550  nop
0x180018551  lea     rax, ??_7AuthorizationToken@Management@CodeIntegrity@@6B@; const CodeIntegrity::Management::AuthorizationToken::`vftable'
0x180018558  mov     [rsi], rax
0x18001855b  lea     rcx, [rsi+88h]
0x180018562  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x180018567  lea     rcx, [rsi+0A0h]
0x18001856e  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x180018573  lea     rcx, [rsi+0B8h]
0x18001857a  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x18001857f  mov     [rsi+0D0h], rbp
0x180018586  mov     [rsi+0D8h], rbp
0x18001858d  mov     byte ptr [rsi+0E0h], 2
0x180018594  mov     rax, rsi
0x180018597  add     rsp, 28h
0x18001859b  pop     rdi
0x18001859c  pop     rsi
0x18001859d  pop     rbp
0x18001859e  pop     rbx
0x18001859f  retn
```
