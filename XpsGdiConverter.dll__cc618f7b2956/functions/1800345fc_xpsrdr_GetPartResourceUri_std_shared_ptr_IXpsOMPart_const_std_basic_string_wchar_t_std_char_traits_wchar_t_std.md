# xpsrdr::GetPartResourceUri(std::shared_ptr<IXpsOMPart> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x1800345fc`
- end: `0x1800346f9`
- name: `?GetPartResourceUri@xpsrdr@@YAXAEBV?$shared_ptr@UIXpsOMPart@@@std@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@@Z`
- size: `253`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001ec70`
- `0x180035fa4`
- `0x18003edd0`
- `0x1800432dc`

## callees

- `0x18000e15c`
- `0x18000e4c4`
- `0x180011b0c`
- `0x18002c810`
- `0x1800345fc`
- `0x180034ec8`
- `0x180037278`
- `0x18004a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
double __fastcall xpsrdr::GetPartResourceUri(__int64 a1, __int64 a2)
{
  __int64 **v3; // r8
  __int64 *v4; // rcx
  __int64 v5; // rax
  int v6; // ebx
  int v7; // edx
  const char *v8; // r8
  int v9; // r9d
  __int64 v10; // rax
  int v11; // esi
  xpsrdr **v12; // rdi
  xpsrdr *v13; // rbx
  int v14; // edx
  const char *v15; // r8
  int v16; // r9d
  xpsrdr *v18; // [rsp+20h] [rbp-30h] BYREF
  xpsrdr **v19; // [rsp+28h] [rbp-28h]
  _QWORD *v20; // [rsp+30h] [rbp-20h]
  _QWORD v21[3]; // [rsp+38h] [rbp-18h] BYREF
  xpsrdr *v22; // [rsp+70h] [rbp+20h] BYREF
  __int64 v23; // [rsp+80h] [rbp+30h] BYREF

  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v21);
  LODWORD(v22) = 0;
  v4 = *v3;
  v5 = **v3;
  v18 = 0;
  v19 = &v22;
  v20 = v21;
  v6 = (*(__int64 (__fastcall **)(__int64 *, xpsrdr **))(v5 + 24))(v4, &v18);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v18);
  if ( (int)v22 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v22, v7, v8, v9);
  if ( v6 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v6, v7, v8, v9);
  v23 = 0;
  v10 = *(_QWORD *)v21[0];
  v18 = 0;
  v19 = (xpsrdr **)&v23;
  v11 = (*(__int64 (__fastcall **)(_QWORD, xpsrdr **))(v10 + 56))(v21[0], &v18);
  v12 = v19;
  v13 = v18;
  Holder<wchar_t *,close_funct<void (*)(wchar_t *),&void SysFreeString(wchar_t *)>,invalid_const<wchar_t *,0>>::reset(v19);
  *v12 = v13;
  if ( v11 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v11, v14, v15, v16);
  std::wstring::assign(a2, v23);
  Holder<wchar_t *,close_funct<void (*)(wchar_t *),&void SysFreeString(wchar_t *)>,invalid_const<wchar_t *,0>>::reset(&v23);
  return std::_Ptr_base<ID2D1RenderTarget>::_Decref(v21);
}

```

## disassembly

```asm
0x1800345fc  mov     [rsp-18h+arg_8], rbx
0x180034601  mov     [rsp-18h+arg_18], rsi
0x180034606  push    rbp
0x180034607  push    rdi
0x180034608  push    r14
0x18003460a  mov     rbp, rsp
0x18003460d  sub     rsp, 50h
0x180034611  mov     r14, rdx
0x180034614  mov     r8, rcx
0x180034617  lea     rcx, [rbp+var_18]
0x18003461b  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180034620  nop
0x180034621  mov     dword ptr [rbp+arg_0], 0
0x180034628  mov     rcx, [r8]
0x18003462b  mov     rax, [rcx]
0x18003462e  mov     [rbp+var_30], 0
0x180034636  lea     rdx, [rbp+arg_0]
0x18003463a  mov     [rbp+var_28], rdx
0x18003463e  lea     rdx, [rbp+var_18]
0x180034642  mov     [rbp+var_20], rdx
0x180034646  lea     rdx, [rbp+var_30]
0x18003464a  mov     rax, [rax+18h]
0x18003464e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034653  mov     ebx, eax
0x180034655  lea     rcx, [rbp+var_30]
0x180034659  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18003465e  mov     ecx, dword ptr [rbp+arg_0]; this
0x180034661  test    ecx, ecx
0x180034663  jns     short loc_18003466B
0x180034665  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003466b  test    ebx, ebx
0x18003466d  jns     short loc_180034677
0x18003466f  mov     ecx, ebx; this
0x180034671  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180034677  mov     [rbp+arg_10], 0
0x18003467f  mov     rcx, [rbp+var_18]
0x180034683  mov     rax, [rcx]
0x180034686  mov     [rbp+var_30], 0
0x18003468e  lea     rdx, [rbp+arg_10]
0x180034692  mov     [rbp+var_28], rdx
0x180034696  lea     rdx, [rbp+var_30]
0x18003469a  mov     rax, [rax+38h]
0x18003469e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800346a3  mov     esi, eax
0x1800346a5  mov     rdi, [rbp+var_28]
0x1800346a9  mov     rbx, [rbp+var_30]
0x1800346ad  mov     rcx, rdi
0x1800346b0  call    ?reset@?$Holder@PEA_WU?$close_funct@P6AXPEA_W@Z$1?SysFreeString@@YAX0@Z@@U?$invalid_const@PEA_W$0A@@@@@QEAAXXZ; Holder<wchar_t *,close_funct<void (*)(wchar_t *),&SysFreeString(wchar_t *)>,invalid_const<wchar_t *,0>>::reset(void)
0x1800346b5  mov     [rdi], rbx
0x1800346b8  test    esi, esi
0x1800346ba  jns     short loc_1800346C4
0x1800346bc  mov     ecx, esi; this
0x1800346be  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800346c4  mov     rdx, [rbp+arg_10]
0x1800346c8  mov     rcx, r14
0x1800346cb  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x1800346d0  nop
0x1800346d1  lea     rcx, [rbp+arg_10]
0x1800346d5  call    ?reset@?$Holder@PEA_WU?$close_funct@P6AXPEA_W@Z$1?SysFreeString@@YAX0@Z@@U?$invalid_const@PEA_W$0A@@@@@QEAAXXZ; Holder<wchar_t *,close_funct<void (*)(wchar_t *),&SysFreeString(wchar_t *)>,invalid_const<wchar_t *,0>>::reset(void)
0x1800346da  nop
0x1800346db  lea     rcx, [rbp+var_18]
0x1800346df  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x1800346e4  lea     r11, [rsp+50h+var_s0]
0x1800346e9  mov     rbx, [r11+28h]
0x1800346ed  mov     rsi, [r11+38h]
0x1800346f1  mov     rsp, r11
0x1800346f4  pop     r14
0x1800346f6  pop     rdi
0x1800346f7  pop     rbp
0x1800346f8  retn
```
