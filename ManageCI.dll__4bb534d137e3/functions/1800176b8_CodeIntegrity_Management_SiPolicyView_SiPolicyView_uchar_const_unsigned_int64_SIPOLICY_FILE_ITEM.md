# CodeIntegrity::Management::SiPolicyView::SiPolicyView(uchar const *,unsigned __int64,_SIPOLICY_FILE_ITEM *)

- ea: `0x1800176b8`
- end: `0x1800177f9`
- name: `??0SiPolicyView@Management@CodeIntegrity@@QEAA@PEBE_KPEAU_SIPOLICY_FILE_ITEM@@@Z`
- size: `321`
- prototype: `CodeIntegrity::Management::SiPolicyView *__fastcall(CodeIntegrity::Management::SiPolicyView *this, const unsigned __int8 *, unsigned int, struct _SIPOLICY_FILE_ITEM *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180009eb0`

## callees

- `0x18000d450`
- `0x18000d470`
- `0x18000df40`
- `0x1800109d8`
- `0x180011514`
- `0x180015ef0`
- `0x1800176b8`
- `0x180017928`
- `0x180025f64`

## string_xrefs

- `0x1800177d2`: `onecore\base\ci\management\dll\sipolicyview.cpp`
- `0x1800177e7`: `onecore\base\ci\management\dll\sipolicyview.cpp`

## pseudocode

```c
CodeIntegrity::Management::SiPolicyView *__fastcall CodeIntegrity::Management::SiPolicyView::SiPolicyView(
        CodeIntegrity::Management::SiPolicyView *this,
        const unsigned __int8 *a2,
        unsigned int a3,
        struct _SIPOLICY_FILE_ITEM *a4)
{
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v10; // eax
  int v12; // [rsp+20h] [rbp-38h]
  int v13[2]; // [rsp+30h] [rbp-28h] BYREF
  void *v14; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

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
  *(_QWORD *)v13 = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void SIPolicyUninitialize(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    v13,
    0);
  LOBYTE(v8) = 1;
  LOBYTE(v9) = 1;
  v10 = SIPolicyParsePolicyFormat(v9, v8, a2, a3, v13);
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x6C,
      (unsigned int)"onecore\\base\\ci\\management\\dll\\sipolicyview.cpp",
      (const char *)(unsigned int)v10,
      v12);
  if ( !*(_QWORD *)v13 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x6E,
      (unsigned int)"onecore\\base\\ci\\management\\dll\\sipolicyview.cpp",
      (const char *)0x80070006LL,
      v12);
  v14 = *(void **)v13;
  CodeIntegrity::Management::SiPolicyView::construct(this, &v14);
  *((_BYTE *)this + 91) = *((_BYTE *)a4 + 16) != 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void SIPolicyUninitialize(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void SIPolicyUninitialize(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v13);
  return this;
}

```

## disassembly

```asm
0x1800176b8  mov     [rsp+arg_8], rbx
0x1800176bd  mov     [rsp+arg_10], rbp
0x1800176c2  mov     [rsp+arg_0], rcx
0x1800176c7  push    rsi
0x1800176c8  push    rdi
0x1800176c9  push    r14
0x1800176cb  sub     rsp, 40h
0x1800176cf  mov     rbp, r9
0x1800176d2  mov     rbx, r8
0x1800176d5  mov     rdi, rdx
0x1800176d8  mov     rsi, rcx
0x1800176db  xor     r14d, r14d
0x1800176de  mov     [rcx], r14
0x1800176e1  mov     [rcx+8], r14
0x1800176e5  mov     [rcx+10h], r14
0x1800176e9  add     rcx, 18h
0x1800176ed  lea     rdx, dword_18002EDD4
0x1800176f4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800176f9  nop
0x1800176fa  lea     rcx, [rsi+38h]
0x1800176fe  lea     rdx, dword_18002EDD4
0x180017705  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001770a  nop
0x18001770b  mov     [rsi+58h], r14d
0x18001770f  mov     [rsi+5Ch], r14w
0x180017714  mov     [rsi+60h], r14
0x180017718  mov     [rsi+68h], r14
0x18001771c  mov     [rsi+70h], r14
0x180017720  mov     [rsi+78h], r14
0x180017724  lea     rcx, [rsi+80h]
0x18001772b  xor     edx, edx
0x18001772d  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x180017732  nop
0x180017733  mov     [rsi+98h], r14
0x18001773a  mov     [rsi+0A0h], r14
0x180017741  mov     [rsi+0A8h], r14
0x180017748  mov     qword ptr [rsp+58h+var_28], r14
0x18001774d  xor     edx, edx
0x18001774f  lea     rcx, [rsp+58h+var_28]
0x180017754  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyUninitialize@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyUninitialize(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180017759  mov     r9d, ebx
0x18001775c  lea     rax, [rsp+58h+var_28]
0x180017761  mov     qword ptr [rsp+58h+var_38], rax; int
0x180017766  mov     r8, rdi
0x180017769  mov     dl, 1
0x18001776b  mov     cl, dl
0x18001776d  call    SIPolicyParsePolicyFormat
0x180017772  mov     rcx, [rsp+58h]; this
0x180017777  test    eax, eax
0x180017779  js      short loc_1800177E4
0x18001777b  mov     rax, qword ptr [rsp+58h+var_28]
0x180017780  test    rax, rax
0x180017783  setz    dl
0x180017786  mov     rcx, [rsp+58h]; this
0x18001778b  test    dl, dl
0x18001778d  jnz     short loc_1800177CC
0x18001778f  mov     [rsp+58h+var_20], rax
0x180017794  lea     rdx, [rsp+58h+var_20]; void **
0x180017799  mov     rcx, rsi; this
0x18001779c  call    ?construct@SiPolicyView@Management@CodeIntegrity@@AEAAXAEBQEAX@Z; CodeIntegrity::Management::SiPolicyView::construct(void * const &)
0x1800177a1  cmp     [rbp+10h], r14b
0x1800177a5  setnz   al
0x1800177a8  mov     [rsi+5Bh], al
0x1800177ab  lea     rcx, [rsp+58h+var_28]
0x1800177b0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyUninitialize@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyUninitialize(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyUninitialize(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800177b5  nop
0x1800177b6  mov     rax, rsi
0x1800177b9  mov     rbx, [rsp+58h+arg_8]
0x1800177be  mov     rbp, [rsp+58h+arg_10]
0x1800177c3  add     rsp, 40h
0x1800177c7  pop     r14
0x1800177c9  pop     rdi
0x1800177ca  pop     rsi
0x1800177cb  retn
0x1800177cc  mov     r9d, 80070006h; char *
0x1800177d2  lea     r8, aOnecoreBaseCiM_7; "onecore\\base\\ci\\management\\dll\\sip"...
0x1800177d9  mov     edx, 6Eh ; 'n'; void *
0x1800177de  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800177e4  mov     r9d, eax; char *
0x1800177e7  lea     r8, aOnecoreBaseCiM_7; "onecore\\base\\ci\\management\\dll\\sip"...
0x1800177ee  mov     edx, 6Ch ; 'l'; void *
0x1800177f3  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
```
