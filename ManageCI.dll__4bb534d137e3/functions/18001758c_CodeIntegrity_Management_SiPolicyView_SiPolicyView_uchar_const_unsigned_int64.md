# CodeIntegrity::Management::SiPolicyView::SiPolicyView(uchar const *,unsigned __int64)

- ea: `0x18001758c`
- end: `0x1800176b2`
- name: `??0SiPolicyView@Management@CodeIntegrity@@QEAA@PEBE_K@Z`
- size: `294`
- prototype: `CodeIntegrity::Management::SiPolicyView *__fastcall(CodeIntegrity::Management::SiPolicyView *this, const unsigned __int8 *, unsigned int)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180012280`
- `0x1800123e0`

## callees

- `0x18000d450`
- `0x18000d470`
- `0x18000df40`
- `0x1800109d8`
- `0x180011514`
- `0x180015ef0`
- `0x18001758c`
- `0x180017928`
- `0x180025f64`

## string_xrefs

- `0x18001768b`: `onecore\base\ci\management\dll\sipolicyview.cpp`
- `0x1800176a0`: `onecore\base\ci\management\dll\sipolicyview.cpp`

## pseudocode

```c
CodeIntegrity::Management::SiPolicyView *__fastcall CodeIntegrity::Management::SiPolicyView::SiPolicyView(
        CodeIntegrity::Management::SiPolicyView *this,
        const unsigned __int8 *a2,
        unsigned int a3)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  int v8; // eax
  int v10; // [rsp+20h] [rbp-38h]
  void *v11; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  void *v13; // [rsp+78h] [rbp+20h] BYREF

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  std::wstring::wstring((__int64)this + 24, (__int64)&dword_18002EDD4);
  std::wstring::wstring((__int64)this + 56, (__int64)&dword_18002EDD4);
  *((_DWORD *)this + 22) = 0;
  *((_WORD *)this + 46) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  std::vector<unsigned char>::vector<unsigned char>((char *)this + 128, 0);
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 21) = 0;
  v13 = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void SIPolicyUninitialize(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &v13,
    0);
  LOBYTE(v6) = 1;
  LOBYTE(v7) = 1;
  v8 = SIPolicyParsePolicyFormat(v7, v6, a2, a3, &v13);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x4B,
      (unsigned int)"onecore\\base\\ci\\management\\dll\\sipolicyview.cpp",
      (const char *)(unsigned int)v8,
      v10);
  if ( !v13 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x4D,
      (unsigned int)"onecore\\base\\ci\\management\\dll\\sipolicyview.cpp",
      (const char *)0x80070006LL,
      v10);
  v11 = v13;
  CodeIntegrity::Management::SiPolicyView::construct(this, &v11);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void SIPolicyUninitialize(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void SIPolicyUninitialize(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v13);
  return this;
}

```

## disassembly

```asm
0x18001758c  mov     [rsp+arg_8], rbx
0x180017591  mov     [rsp+arg_0], rcx
0x180017596  push    rbp
0x180017597  push    rsi
0x180017598  push    rdi
0x180017599  sub     rsp, 40h
0x18001759d  mov     rbx, r8
0x1800175a0  mov     rdi, rdx
0x1800175a3  mov     rsi, rcx
0x1800175a6  xor     ebp, ebp
0x1800175a8  mov     [rcx], rbp
0x1800175ab  mov     [rcx+8], rbp
0x1800175af  mov     [rcx+10h], rbp
0x1800175b3  add     rcx, 18h
0x1800175b7  lea     rdx, dword_18002EDD4
0x1800175be  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800175c3  nop
0x1800175c4  lea     rcx, [rsi+38h]
0x1800175c8  lea     rdx, dword_18002EDD4
0x1800175cf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800175d4  nop
0x1800175d5  mov     [rsi+58h], ebp
0x1800175d8  mov     [rsi+5Ch], bp
0x1800175dc  mov     [rsi+60h], rbp
0x1800175e0  mov     [rsi+68h], rbp
0x1800175e4  mov     [rsi+70h], rbp
0x1800175e8  mov     [rsi+78h], rbp
0x1800175ec  lea     rcx, [rsi+80h]
0x1800175f3  xor     edx, edx
0x1800175f5  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x1800175fa  nop
0x1800175fb  mov     [rsi+98h], rbp
0x180017602  mov     [rsi+0A0h], rbp
0x180017609  mov     [rsi+0A8h], rbp
0x180017610  mov     [rsp+58h+arg_18], rbp
0x180017615  xor     edx, edx
0x180017617  lea     rcx, [rsp+58h+arg_18]
0x18001761c  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyUninitialize@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyUninitialize(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180017621  mov     r9d, ebx
0x180017624  lea     rax, [rsp+58h+arg_18]
0x180017629  mov     qword ptr [rsp+58h+var_38], rax; int
0x18001762e  mov     r8, rdi
0x180017631  mov     dl, 1
0x180017633  mov     cl, dl
0x180017635  call    SIPolicyParsePolicyFormat
0x18001763a  mov     rcx, [rsp+58h]; this
0x18001763f  test    eax, eax
0x180017641  js      short loc_18001769D
0x180017643  mov     rax, [rsp+58h+arg_18]
0x180017648  test    rax, rax
0x18001764b  setz    dl
0x18001764e  mov     rcx, [rsp+58h]; this
0x180017653  test    dl, dl
0x180017655  jnz     short loc_180017685
0x180017657  mov     [rsp+58h+var_28], rax
0x18001765c  lea     rdx, [rsp+58h+var_28]; void **
0x180017661  mov     rcx, rsi; this
0x180017664  call    ?construct@SiPolicyView@Management@CodeIntegrity@@AEAAXAEBQEAX@Z; CodeIntegrity::Management::SiPolicyView::construct(void * const &)
0x180017669  nop
0x18001766a  lea     rcx, [rsp+58h+arg_18]
0x18001766f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyUninitialize@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyUninitialize(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyUninitialize(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180017674  nop
0x180017675  mov     rax, rsi
0x180017678  mov     rbx, [rsp+58h+arg_8]
0x18001767d  add     rsp, 40h
0x180017681  pop     rdi
0x180017682  pop     rsi
0x180017683  pop     rbp
0x180017684  retn
0x180017685  mov     r9d, 80070006h; char *
0x18001768b  lea     r8, aOnecoreBaseCiM_7; "onecore\\base\\ci\\management\\dll\\sip"...
0x180017692  mov     edx, 4Dh ; 'M'; void *
0x180017697  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001769d  mov     r9d, eax; char *
0x1800176a0  lea     r8, aOnecoreBaseCiM_7; "onecore\\base\\ci\\management\\dll\\sip"...
0x1800176a7  mov     edx, 4Bh ; 'K'; void *
0x1800176ac  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
```
