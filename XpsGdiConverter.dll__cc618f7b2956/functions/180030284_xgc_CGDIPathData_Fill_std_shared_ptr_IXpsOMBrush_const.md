# xgc::CGDIPathData::Fill(std::shared_ptr<IXpsOMBrush> const &)

- ea: `0x180030284`
- end: `0x1800304c0`
- name: `?Fill@CGDIPathData@xgc@@QEBAXAEBV?$shared_ptr@UIXpsOMBrush@@@std@@@Z`
- size: `572`
- prototype: `__int64 __fastcall(xgc::CGDIPathData *this)`
- caller_count: `3`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180027dfc`
- `0x180028338`
- `0x18002bcf0`

## callees

- `0x18000d428`
- `0x18000e15c`
- `0x18000e4c4`
- `0x180011b0c`
- `0x18002e684`
- `0x18002f6e8`
- `0x1800300b8`
- `0x180030284`
- `0x180037278`
- `0x1800372e4`
- `0x18004a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
double __fastcall xgc::CGDIPathData::Fill(
        xgc::CGDIPathData *this,
        __int64 (__fastcall ****a2)(__int64, GUID *, __int64 *),
        __int64 a3,
        float a4)
{
  int v6; // eax
  const char *v7; // rdx
  const char *v8; // r8
  int v9; // r9d
  xpsrdr *v10; // rcx
  __int64 (__fastcall ***v11)(__int64, GUID *, __int64 *); // rcx
  __int64 (__fastcall **v12)(__int64, GUID *, __int64 *); // rax
  int v13; // edi
  int v14; // edx
  const char *v15; // r8
  int v16; // r9d
  double result; // xmm0_8
  __int64 (__fastcall ***v18)(__int64, GUID *, __int64 *); // rcx
  __int64 (__fastcall **v19)(__int64, GUID *, __int64 *); // rax
  int v20; // edi
  int v21; // edx
  const char *v22; // r8
  int v23; // r9d
  __int64 (__fastcall ***v24)(__int64, GUID *, __int64 *); // rcx
  __int64 (__fastcall **v25)(__int64, GUID *, __int64 *); // rax
  int v26; // edi
  int v27; // edx
  const char *v28; // r8
  int v29; // r9d
  __int64 *v30[2]; // [rsp+20h] [rbp-30h] BYREF
  __int64 v31; // [rsp+30h] [rbp-20h] BYREF
  xpsrdr **v32; // [rsp+38h] [rbp-18h]
  __int64 **v33; // [rsp+40h] [rbp-10h]
  unsigned int v34; // [rsp+60h] [rbp+10h] BYREF
  xpsrdr *v35; // [rsp+70h] [rbp+20h] BYREF

  if ( (unsigned __int64)((__int64)(*((_QWORD *)this + 6) - *((_QWORD *)this + 5)) >> 3) >= 2 )
  {
    v34 = 0;
    v6 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 *), unsigned int *))(**a2)[4])(
           *a2,
           &v34);
    if ( v6 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v6, (int)v7, v8, v9);
    if ( v34 == 6 )
    {
      std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v30);
      LODWORD(v35) = 0;
      v24 = *a2;
      v25 = **a2;
      v31 = 0;
      v32 = &v35;
      v33 = v30;
      v26 = (*v25)((__int64)v24, &GUID_a06f9f05_3be9_4763_98a8_094fc672e488, &v31);
      detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v31);
      if ( (int)v35 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v35, v27, v28, v29);
      if ( v26 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v26, v27, v28, v29);
      xgc::CGDIPathData::Fill((__int64)this, (__int64)v30);
      return std::_Ptr_base<ID2D1RenderTarget>::_Decref(v30);
    }
    else if ( v34 == 7 )
    {
      std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v30);
      LODWORD(v35) = 0;
      v18 = *a2;
      v19 = **a2;
      v31 = 0;
      v32 = &v35;
      v33 = v30;
      v20 = (*v19)((__int64)v18, &GUID_3df0b466_d382_49ef_8550_dd94c80242e4, &v31);
      detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v31);
      if ( (int)v35 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v35, v21, v22, v23);
      if ( v20 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v20, v21, v22, v23);
      xgc::CGDIPathData::Fill(this, v30);
      return std::_Ptr_base<ID2D1RenderTarget>::_Decref(v30);
    }
    else
    {
      if ( v34 - 8 >= 2 )
      {
        v10 = (xpsrdr *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 11, WPP_00624022ad39391a483a764a1c0090f0_Traceguids, v34);
        xpsrdr::ThrowLogicException(v10, v7, (int)v8);
      }
      std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v30);
      LODWORD(v35) = 0;
      v11 = *a2;
      v12 = **a2;
      v31 = 0;
      v32 = &v35;
      v33 = v30;
      v13 = (*v12)((__int64)v11, &GUID_edb59622_61a2_42c3_bace_acf2286c06bf, &v31);
      detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v31);
      if ( (int)v35 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v35, v14, v15, v16);
      if ( v13 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v13, v14, v15, v16);
      xgc::CGDIPathData::Fill(this, v30, (__int64)v15, a4);
      return std::_Ptr_base<ID2D1RenderTarget>::_Decref(v30);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180030284  mov     [rsp-8+arg_8], rbx
0x180030289  mov     [rsp-8+arg_18], rdi
0x18003028e  push    rbp
0x18003028f  mov     rbp, rsp
0x180030292  sub     rsp, 50h
0x180030296  mov     rdi, rdx
0x180030299  mov     rbx, rcx
0x18003029c  mov     rax, [rcx+30h]
0x1800302a0  sub     rax, [rcx+28h]
0x1800302a4  sar     rax, 3
0x1800302a8  cmp     rax, 2
0x1800302ac  jb      loc_1800304B0
0x1800302b2  mov     [rbp+arg_0], 0
0x1800302b9  mov     rcx, [rdx]
0x1800302bc  mov     rax, [rcx]
0x1800302bf  lea     rdx, [rbp+arg_0]
0x1800302c3  mov     rax, [rax+20h]
0x1800302c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800302cc  test    eax, eax
0x1800302ce  jns     short loc_1800302D8
0x1800302d0  mov     ecx, eax; this
0x1800302d2  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800302d8  mov     r9d, [rbp+arg_0]
0x1800302dc  mov     ecx, r9d
0x1800302df  sub     ecx, 6
0x1800302e2  jz      loc_180030434
0x1800302e8  sub     ecx, 1
0x1800302eb  jz      loc_1800303B6
0x1800302f1  sub     ecx, 1
0x1800302f4  jz      short loc_180030335
0x1800302f6  cmp     ecx, 1
0x1800302f9  jz      short loc_180030335
0x1800302fb  lea     rax, WPP_GLOBAL_Control
0x180030302  mov     rcx, cs:WPP_GLOBAL_Control
0x180030309  cmp     rcx, rax
0x18003030c  jz      short loc_18003032F
0x18003030e  test    byte ptr [rcx+0E4h], 1
0x180030315  jz      short loc_18003032F
0x180030317  mov     edx, 0Bh
0x18003031c  lea     r8, WPP_00624022ad39391a483a764a1c0090f0_Traceguids
0x180030323  mov     rcx, [rcx+0D8h]
0x18003032a  call    WPP_SF_d
0x18003032f  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
0x180030335  lea     rcx, [rbp+var_30]
0x180030339  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18003033e  nop
0x18003033f  mov     dword ptr [rbp+arg_10], 0
0x180030346  mov     rcx, [rdi]
0x180030349  mov     rax, [rcx]
0x18003034c  mov     [rbp+var_20], 0
0x180030354  lea     rdx, [rbp+arg_10]
0x180030358  mov     [rbp+var_18], rdx
0x18003035c  lea     rdx, [rbp+var_30]
0x180030360  mov     [rbp+var_10], rdx
0x180030364  lea     r8, [rbp+var_20]
0x180030368  lea     rdx, _GUID_edb59622_61a2_42c3_bace_acf2286c06bf
0x18003036f  mov     rax, [rax]
0x180030372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030377  mov     edi, eax
0x180030379  lea     rcx, [rbp+var_20]
0x18003037d  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180030382  mov     ecx, dword ptr [rbp+arg_10]; this
0x180030385  test    ecx, ecx
0x180030387  jns     short loc_18003038F
0x180030389  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003038f  test    edi, edi
0x180030391  jns     short loc_18003039B
0x180030393  mov     ecx, edi; this
0x180030395  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003039b  lea     rdx, [rbp+var_30]
0x18003039f  mov     rcx, rbx; this
0x1800303a2  call    ?Fill@CGDIPathData@xgc@@AEBAXAEBV?$shared_ptr@UIXpsOMGradientBrush@@@std@@@Z; xgc::CGDIPathData::Fill(std::shared_ptr<IXpsOMGradientBrush> const &)
0x1800303a7  nop
0x1800303a8  lea     rcx, [rbp+var_30]
0x1800303ac  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x1800303b1  jmp     loc_1800304B0
0x1800303b6  lea     rcx, [rbp+var_30]
0x1800303ba  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x1800303bf  nop
0x1800303c0  mov     dword ptr [rbp+arg_10], 0
0x1800303c7  mov     rcx, [rdi]
0x1800303ca  mov     rax, [rcx]
0x1800303cd  mov     [rbp+var_20], 0
0x1800303d5  lea     rdx, [rbp+arg_10]
0x1800303d9  mov     [rbp+var_18], rdx
0x1800303dd  lea     rdx, [rbp+var_30]
0x1800303e1  mov     [rbp+var_10], rdx
0x1800303e5  lea     r8, [rbp+var_20]
0x1800303e9  lea     rdx, _GUID_3df0b466_d382_49ef_8550_dd94c80242e4
0x1800303f0  mov     rax, [rax]
0x1800303f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800303f8  mov     edi, eax
0x1800303fa  lea     rcx, [rbp+var_20]
0x1800303fe  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180030403  mov     ecx, dword ptr [rbp+arg_10]; this
0x180030406  test    ecx, ecx
0x180030408  jns     short loc_180030410
0x18003040a  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180030410  test    edi, edi
0x180030412  jns     short loc_18003041C
0x180030414  mov     ecx, edi; this
0x180030416  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003041c  lea     rdx, [rbp+var_30]
0x180030420  mov     rcx, rbx; this
0x180030423  call    ?Fill@CGDIPathData@xgc@@AEBAXAEBV?$shared_ptr@UIXpsOMImageBrush@@@std@@@Z; xgc::CGDIPathData::Fill(std::shared_ptr<IXpsOMImageBrush> const &)
0x180030428  nop
0x180030429  lea     rcx, [rbp+var_30]
0x18003042d  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180030432  jmp     short loc_1800304B0
0x180030434  lea     rcx, [rbp+var_30]
0x180030438  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18003043d  nop
0x18003043e  mov     dword ptr [rbp+arg_10], 0
0x180030445  mov     rcx, [rdi]
0x180030448  mov     rax, [rcx]
0x18003044b  mov     [rbp+var_20], 0
0x180030453  lea     rdx, [rbp+arg_10]
0x180030457  mov     [rbp+var_18], rdx
0x18003045b  lea     rdx, [rbp+var_30]
0x18003045f  mov     [rbp+var_10], rdx
0x180030463  lea     r8, [rbp+var_20]
0x180030467  lea     rdx, _GUID_a06f9f05_3be9_4763_98a8_094fc672e488
0x18003046e  mov     rax, [rax]
0x180030471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030476  mov     edi, eax
0x180030478  lea     rcx, [rbp+var_20]
0x18003047c  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180030481  mov     ecx, dword ptr [rbp+arg_10]; this
0x180030484  test    ecx, ecx
0x180030486  jns     short loc_18003048E
0x180030488  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003048e  test    edi, edi
0x180030490  jns     short loc_18003049A
0x180030492  mov     ecx, edi; this
0x180030494  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003049a  lea     rdx, [rbp+var_30]
0x18003049e  mov     rcx, rbx
0x1800304a1  call    ?Fill@CGDIPathData@xgc@@AEBAXAEBV?$shared_ptr@UIXpsOMSolidColorBrush@@@std@@@Z; xgc::CGDIPathData::Fill(std::shared_ptr<IXpsOMSolidColorBrush> const &)
0x1800304a6  nop
0x1800304a7  lea     rcx, [rbp+var_30]
0x1800304ab  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x1800304b0  mov     rbx, [rsp+50h+arg_8]
0x1800304b5  mov     rdi, [rsp+50h+arg_18]
0x1800304ba  add     rsp, 50h
0x1800304be  pop     rbp
0x1800304bf  retn
```
