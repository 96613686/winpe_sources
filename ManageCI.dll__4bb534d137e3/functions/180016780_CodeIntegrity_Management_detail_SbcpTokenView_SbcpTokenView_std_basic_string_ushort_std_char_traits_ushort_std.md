# CodeIntegrity::Management::detail::SbcpTokenView::SbcpTokenView(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x180016780`
- end: `0x1800167fb`
- name: `??0SbcpTokenView@detail@Management@CodeIntegrity@@IEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEBV?$vector@EV?$allocator@E@std@@@5@@Z`
- size: `123`
- prototype: `CodeIntegrity::Management::detail::SbcpTokenView *__fastcall(CodeIntegrity::Management::detail::SbcpTokenView *this, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800185a8`
- `0x180018774`

## callees

- `0x180004e34`
- `0x180010ca4`
- `0x180010cdc`
- `0x180016780`
- `0x180016958`
- `0x180016b24`

## pseudocode

```c
CodeIntegrity::Management::detail::SbcpTokenView *__fastcall CodeIntegrity::Management::detail::SbcpTokenView::SbcpTokenView(
        CodeIntegrity::Management::detail::SbcpTokenView *this,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  *(_QWORD *)this = &CodeIntegrity::Management::detail::SbcpTokenView::`vftable';
  *((_WORD *)this + 4) = 0;
  *((_QWORD *)this + 2) = 0;
  std::wstring::wstring((char *)this + 24);
  std::wstring::wstring((char *)this + 56);
  std::vector<unsigned char>::vector<unsigned char>((char *)this + 88, a4);
  std::vector<_GUID>::vector<_GUID>((char *)this + 112);
  CodeIntegrity::Management::detail::SbcpTokenView::CheckSignature(this);
  if ( !*((_WORD *)this + 4) )
    CodeIntegrity::Management::detail::SbcpTokenView::ParseSbcpToken(this);
  return this;
}

```

## disassembly

```asm
0x180016780  mov     [rsp+arg_0], rcx
0x180016785  push    rbx
0x180016786  push    rbp
0x180016787  push    rsi
0x180016788  push    rdi
0x180016789  sub     rsp, 28h
0x18001678d  mov     rdi, r9
0x180016790  mov     rbx, r8
0x180016793  mov     rsi, rcx
0x180016796  lea     rax, ??_7SbcpTokenView@detail@Management@CodeIntegrity@@6B@; const CodeIntegrity::Management::detail::SbcpTokenView::`vftable'
0x18001679d  mov     [rcx], rax
0x1800167a0  xor     ebp, ebp
0x1800167a2  mov     [rcx+8], bp
0x1800167a6  mov     [rcx+10h], rbp
0x1800167aa  add     rcx, 18h
0x1800167ae  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800167b3  nop
0x1800167b4  lea     rcx, [rsi+38h]
0x1800167b8  mov     rdx, rbx
0x1800167bb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800167c0  nop
0x1800167c1  lea     rcx, [rsi+58h]
0x1800167c5  mov     rdx, rdi
0x1800167c8  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@AEBV01@@Z; std::vector<uchar>::vector<uchar>(std::vector<uchar> const &)
0x1800167cd  nop
0x1800167ce  lea     rcx, [rsi+70h]
0x1800167d2  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x1800167d7  nop
0x1800167d8  mov     rcx, rsi; this
0x1800167db  call    ?CheckSignature@SbcpTokenView@detail@Management@CodeIntegrity@@AEAAXXZ; CodeIntegrity::Management::detail::SbcpTokenView::CheckSignature(void)
0x1800167e0  cmp     [rsi+8], bp
0x1800167e4  jnz     short loc_1800167EF
0x1800167e6  mov     rcx, rsi; this
0x1800167e9  call    ?ParseSbcpToken@SbcpTokenView@detail@Management@CodeIntegrity@@AEAAXXZ; CodeIntegrity::Management::detail::SbcpTokenView::ParseSbcpToken(void)
0x1800167ee  nop
0x1800167ef  mov     rax, rsi
0x1800167f2  add     rsp, 28h
0x1800167f6  pop     rdi
0x1800167f7  pop     rsi
0x1800167f8  pop     rbp
0x1800167f9  pop     rbx
0x1800167fa  retn
```
