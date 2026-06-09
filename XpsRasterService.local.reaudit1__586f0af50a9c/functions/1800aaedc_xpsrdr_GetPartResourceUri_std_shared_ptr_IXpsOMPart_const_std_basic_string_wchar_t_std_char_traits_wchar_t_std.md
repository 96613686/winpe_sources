# xpsrdr::GetPartResourceUri(std::shared_ptr<IXpsOMPart> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x1800aaedc`
- end: `0x1800aafe4`
- name: `?GetPartResourceUri@xpsrdr@@YAXAEBV?$shared_ptr@UIXpsOMPart@@@std@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@@Z`
- size: `264`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800b9850`
- `0x1800bad68`
- `0x1800bdc84`

## callees

- `0x1800a2c1c`
- `0x1800a5230`
- `0x1800a97d0`
- `0x1800aaedc`
- `0x1800abb48`
- `0x1800abb60`
- `0x1800b20e8`
- `0x1800c3010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall xpsrdr::GetPartResourceUri(__int64 **a1, __int64 a2)
{
  __int64 *v3; // rcx
  __int64 v4; // rax
  int v5; // ebx
  int v6; // edx
  const char *v7; // r8
  int v8; // r9d
  __int64 v9; // rax
  int v10; // esi
  xpsrdr **v11; // rdi
  xpsrdr *v12; // rbx
  int v13; // edx
  const char *v14; // r8
  int v15; // r9d
  __int64 v16; // rax
  __int64 v17; // rcx
  xpsrdr *v18; // [rsp+20h] [rbp-30h] BYREF
  xpsrdr **v19; // [rsp+28h] [rbp-28h]
  std::_Ref_count_base **v20; // [rsp+30h] [rbp-20h]
  std::_Ref_count_base *v21[2]; // [rsp+38h] [rbp-18h] BYREF
  xpsrdr *v22; // [rsp+70h] [rbp+20h] BYREF
  __int64 v23; // [rsp+80h] [rbp+30h] BYREF

  *(_OWORD *)v21 = 0;
  LODWORD(v22) = 0;
  v3 = *a1;
  v4 = *v3;
  v18 = 0;
  v19 = &v22;
  v20 = v21;
  v5 = (*(__int64 (__fastcall **)(__int64 *, xpsrdr **))(v4 + 24))(v3, &v18);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v18);
  if ( (int)v22 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v22, v6, v7, v8);
  if ( v5 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v5, v6, v7, v8);
  v23 = 0;
  v9 = *(_QWORD *)v21[0];
  v18 = 0;
  v19 = (xpsrdr **)&v23;
  v10 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, xpsrdr **))(v9 + 56))(v21[0], &v18);
  v11 = v19;
  v12 = v18;
  Holder<wchar_t *,close_funct<void (*)(wchar_t *),&void SysFreeString(wchar_t *)>,invalid_const<wchar_t *,0>>::reset(v19);
  *v11 = v12;
  if ( v10 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v10, v13, v14, v15);
  v16 = std::_WChar_traits<wchar_t>::length(v23);
  std::wstring::_Assign<wchar_t>(a2, v17, v16);
  Holder<wchar_t *,close_funct<void (*)(wchar_t *),&void SysFreeString(wchar_t *)>,invalid_const<wchar_t *,0>>::reset(&v23);
  if ( v21[1] )
    std::_Ref_count_base::_Decref(v21[1]);
}

```

## disassembly

```asm
0x1800aaedc  mov     [rsp-18h+arg_8], rbx
0x1800aaee1  mov     [rsp-18h+arg_18], rsi
0x1800aaee6  push    rbp
0x1800aaee7  push    rdi
0x1800aaee8  push    r14
0x1800aaeea  mov     rbp, rsp
0x1800aaeed  sub     rsp, 50h
0x1800aaef1  mov     r14, rdx
0x1800aaef4  xorps   xmm0, xmm0
0x1800aaef7  movdqu  xmmword ptr [rbp+var_18], xmm0
0x1800aaefc  mov     dword ptr [rbp+arg_0], 0
0x1800aaf03  mov     rcx, [rcx]
0x1800aaf06  mov     rax, [rcx]
0x1800aaf09  mov     [rbp+var_30], 0
0x1800aaf11  lea     rdx, [rbp+arg_0]
0x1800aaf15  mov     [rbp+var_28], rdx
0x1800aaf19  lea     rdx, [rbp+var_18]
0x1800aaf1d  mov     [rbp+var_20], rdx
0x1800aaf21  lea     rdx, [rbp+var_30]
0x1800aaf25  mov     rax, [rax+18h]
0x1800aaf29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aaf2e  mov     ebx, eax
0x1800aaf30  lea     rcx, [rbp+var_30]
0x1800aaf34  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800aaf39  mov     ecx, dword ptr [rbp+arg_0]; this
0x1800aaf3c  test    ecx, ecx
0x1800aaf3e  jns     short loc_1800AAF46
0x1800aaf40  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800aaf46  test    ebx, ebx
0x1800aaf48  jns     short loc_1800AAF52
0x1800aaf4a  mov     ecx, ebx; this
0x1800aaf4c  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800aaf52  mov     [rbp+arg_10], 0
0x1800aaf5a  mov     rcx, [rbp+var_18]
0x1800aaf5e  mov     rax, [rcx]
0x1800aaf61  mov     [rbp+var_30], 0
0x1800aaf69  lea     rdx, [rbp+arg_10]
0x1800aaf6d  mov     [rbp+var_28], rdx
0x1800aaf71  lea     rdx, [rbp+var_30]
0x1800aaf75  mov     rax, [rax+38h]
0x1800aaf79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aaf7e  mov     esi, eax
0x1800aaf80  mov     rdi, [rbp+var_28]
0x1800aaf84  mov     rbx, [rbp+var_30]
0x1800aaf88  mov     rcx, rdi
0x1800aaf8b  call    ?reset@?$Holder@PEA_WU?$close_funct@P6AXPEA_W@Z$1?SysFreeString@@YAX0@Z@@U?$invalid_const@PEA_W$0A@@@@@QEAAXXZ; Holder<wchar_t *,close_funct<void (*)(wchar_t *),&SysFreeString(wchar_t *)>,invalid_const<wchar_t *,0>>::reset(void)
0x1800aaf90  mov     [rdi], rbx
0x1800aaf93  test    esi, esi
0x1800aaf95  jns     short loc_1800AAF9F
0x1800aaf97  mov     ecx, esi; this
0x1800aaf99  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800aaf9f  mov     rcx, [rbp+arg_10]
0x1800aafa3  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1800aafa8  mov     r8, rax
0x1800aafab  mov     rdx, rcx
0x1800aafae  mov     rcx, r14
0x1800aafb1  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x1800aafb6  nop
0x1800aafb7  lea     rcx, [rbp+arg_10]
0x1800aafbb  call    ?reset@?$Holder@PEA_WU?$close_funct@P6AXPEA_W@Z$1?SysFreeString@@YAX0@Z@@U?$invalid_const@PEA_W$0A@@@@@QEAAXXZ; Holder<wchar_t *,close_funct<void (*)(wchar_t *),&SysFreeString(wchar_t *)>,invalid_const<wchar_t *,0>>::reset(void)
0x1800aafc0  nop
0x1800aafc1  mov     rcx, [rbp+var_18+8]; this
0x1800aafc5  test    rcx, rcx
0x1800aafc8  jz      short loc_1800AAFCF
0x1800aafca  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800aafcf  lea     r11, [rsp+50h+var_s0]
0x1800aafd4  mov     rbx, [r11+28h]
0x1800aafd8  mov     rsi, [r11+38h]
0x1800aafdc  mov     rsp, r11
0x1800aafdf  pop     r14
0x1800aafe1  pop     rdi
0x1800aafe2  pop     rbp
0x1800aafe3  retn
```
