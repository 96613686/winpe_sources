# xpsrdr::CreateSolidColorBrush(xpsrdr::RenderState &,std::shared_ptr<IXpsOMBrush> const &,float *)

- ea: `0x1800416a8`
- end: `0x180041854`
- name: `?CreateSolidColorBrush@xpsrdr@@YA?AV?$shared_ptr@UID2D1Brush@@@std@@AEAURenderState@1@AEBV?$shared_ptr@UIXpsOMBrush@@@3@PEAM@Z`
- size: `428`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180040014`

## callees

- `0x180008830`
- `0x18000e15c`
- `0x18000e4c4`
- `0x180011b0c`
- `0x180036250`
- `0x180037278`
- `0x1800415dc`
- `0x1800416a8`
- `0x18004a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall xpsrdr::CreateSolidColorBrush(__int64 a1, __int64 a2, _QWORD *a3, __int64 a4)
{
  _QWORD **v8; // r8
  __int64 (__fastcall ***v9)(_QWORD, GUID *, __int64 *); // rcx
  __int64 (__fastcall **v10)(_QWORD, GUID *, __int64 *); // rax
  int v11; // ebx
  int v12; // edx
  const char *v13; // r8
  int v14; // r9d
  int v15; // eax
  int v16; // edx
  const char *v17; // r8
  int v18; // r9d
  __int64 v19; // rax
  int v20; // ebx
  int v21; // edx
  const char *v22; // r8
  int v23; // r9d
  xpsrdr *v25; // [rsp+20h] [rbp-79h] BYREF
  __int64 v26; // [rsp+28h] [rbp-71h] BYREF
  __int64 v27; // [rsp+30h] [rbp-69h] BYREF
  xpsrdr **v28; // [rsp+38h] [rbp-61h]
  _BYTE *v29; // [rsp+40h] [rbp-59h]
  _BYTE v30[16]; // [rsp+50h] [rbp-49h] BYREF
  _QWORD v31[2]; // [rsp+60h] [rbp-39h] BYREF
  __m128 v32; // [rsp+70h] [rbp-29h] BYREF
  _OWORD v33[3]; // [rsp+80h] [rbp-19h] BYREF

  v26 = a1;
  ++*(_DWORD *)(*(_QWORD *)(a2 + 544) + 32LL);
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v31);
  LODWORD(v25) = 0;
  v9 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v8;
  v10 = (__int64 (__fastcall **)(_QWORD, GUID *, __int64 *))**v8;
  v27 = 0;
  v28 = &v25;
  v29 = v31;
  v11 = (*v10)(v9, &GUID_a06f9f05_3be9_4763_98a8_094fc672e488, &v27);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v27);
  if ( (int)v25 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v25, v12, v13, v14);
  if ( v11 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v11, v12, v13, v14);
  LODWORD(v26) = 0;
  v15 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a3 + 40LL))(*a3, &v26);
  if ( v15 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v15, v16, v17, v18);
  memset(v33, 0, 44);
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v30);
  LODWORD(v25) = 0;
  v19 = *(_QWORD *)v31[0];
  v27 = 0;
  v28 = &v25;
  v29 = v30;
  v20 = (*(__int64 (__fastcall **)(_QWORD, _OWORD *, __int64 *))(v19 + 56))(v31[0], v33, &v27);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v27);
  if ( (int)v25 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v25, v21, v22, v23);
  if ( v20 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v20, v21, v22, v23);
  v32 = (__m128)_mm_loadu_si128((const __m128i *)xpsrdr::GetD2D1Color(&v27, a2, v33, v30));
  v32.m128_f32[3] = _mm_shuffle_ps(v32, v32, 255).m128_f32[0] * *(float *)&v26;
  xpsrdr::CreateSolidColorBrush(a1, a2, &v32, a4);
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(v30);
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(v31);
  return a1;
}

```

## disassembly

```asm
0x1800416a8  push    rbp
0x1800416aa  push    rbx
0x1800416ab  push    rsi
0x1800416ac  push    rdi
0x1800416ad  push    r14
0x1800416af  push    r15
0x1800416b1  lea     rbp, [rsp-2Fh]
0x1800416b6  sub     rsp, 0C8h
0x1800416bd  mov     rax, cs:__security_cookie
0x1800416c4  xor     rax, rsp
0x1800416c7  mov     [rbp+57h+var_40], rax
0x1800416cb  mov     r15, r9
0x1800416ce  mov     r14, r8
0x1800416d1  mov     rsi, rdx
0x1800416d4  mov     rdi, rcx
0x1800416d7  mov     [rbp+57h+var_C8], rcx
0x1800416db  mov     rax, [rdx+220h]
0x1800416e2  inc     dword ptr [rax+20h]
0x1800416e5  lea     rcx, [rbp+57h+var_90]
0x1800416e9  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x1800416ee  nop
0x1800416ef  mov     dword ptr [rbp+57h+var_D0], 0
0x1800416f6  mov     rcx, [r8]
0x1800416f9  mov     rax, [rcx]
0x1800416fc  mov     [rbp+57h+var_C0], 0
0x180041704  lea     rdx, [rbp+57h+var_D0]
0x180041708  mov     [rbp+57h+var_B8], rdx
0x18004170c  lea     rdx, [rbp+57h+var_90]
0x180041710  mov     [rbp+57h+var_B0], rdx
0x180041714  lea     r8, [rbp+57h+var_C0]
0x180041718  lea     rdx, _GUID_a06f9f05_3be9_4763_98a8_094fc672e488
0x18004171f  mov     rax, [rax]
0x180041722  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041727  mov     ebx, eax
0x180041729  lea     rcx, [rbp+57h+var_C0]
0x18004172d  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180041732  mov     ecx, dword ptr [rbp+57h+var_D0]; this
0x180041735  test    ecx, ecx
0x180041737  jns     short loc_18004173F
0x180041739  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18004173f  test    ebx, ebx
0x180041741  jns     short loc_18004174B
0x180041743  mov     ecx, ebx; this
0x180041745  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18004174b  mov     dword ptr [rbp+57h+var_C8], 0
0x180041752  mov     rcx, [r14]
0x180041755  mov     rax, [rcx]
0x180041758  lea     rdx, [rbp+57h+var_C8]
0x18004175c  mov     rax, [rax+28h]
0x180041760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041765  test    eax, eax
0x180041767  jns     short loc_180041771
0x180041769  mov     ecx, eax; this
0x18004176b  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180041771  xorps   xmm0, xmm0
0x180041774  movups  [rbp+57h+var_70], xmm0
0x180041778  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x18004177c  movups  xmmword ptr [rbp+57h+var_60+0Ch], xmm0
0x180041780  lea     rcx, [rbp+57h+var_A0]
0x180041784  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180041789  nop
0x18004178a  mov     dword ptr [rbp+57h+var_D0], 0
0x180041791  mov     rcx, [rbp+57h+var_90]
0x180041795  mov     rax, [rcx]
0x180041798  mov     [rbp+57h+var_C0], 0
0x1800417a0  lea     rdx, [rbp+57h+var_D0]
0x1800417a4  mov     [rbp+57h+var_B8], rdx
0x1800417a8  lea     rdx, [rbp+57h+var_A0]
0x1800417ac  mov     [rbp+57h+var_B0], rdx
0x1800417b0  lea     r8, [rbp+57h+var_C0]
0x1800417b4  lea     rdx, [rbp+57h+var_70]
0x1800417b8  mov     rax, [rax+38h]
0x1800417bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800417c1  mov     ebx, eax
0x1800417c3  lea     rcx, [rbp+57h+var_C0]
0x1800417c7  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800417cc  mov     ecx, dword ptr [rbp+57h+var_D0]; this
0x1800417cf  test    ecx, ecx
0x1800417d1  jns     short loc_1800417D9
0x1800417d3  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800417d9  test    ebx, ebx
0x1800417db  jns     short loc_1800417E5
0x1800417dd  mov     ecx, ebx; this
0x1800417df  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800417e5  lea     r9, [rbp+57h+var_A0]
0x1800417e9  lea     r8, [rbp+57h+var_70]
0x1800417ed  mov     rdx, rsi
0x1800417f0  lea     rcx, [rbp+57h+var_C0]
0x1800417f4  call    ?GetD2D1Color@xpsrdr@@YA?AU_D3DCOLORVALUE@@AEAURenderState@1@AEBU__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0024@@AEBV?$shared_ptr@UIXpsOMColorProfileResource@@@std@@@Z; xpsrdr::GetD2D1Color(xpsrdr::RenderState &,__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0024 const &,std::shared_ptr<IXpsOMColorProfileResource> const &)
0x1800417f9  movdqu  xmm0, xmmword ptr [rax]
0x1800417fd  movups  [rbp+57h+var_80], xmm0
0x180041801  shufps  xmm0, xmm0, 0FFh
0x180041805  mulss   xmm0, dword ptr [rbp+57h+var_C8]
0x18004180a  movss   dword ptr [rbp+57h+var_80+0Ch], xmm0
0x18004180f  mov     r9, r15
0x180041812  lea     r8, [rbp+57h+var_80]
0x180041816  mov     rdx, rsi
0x180041819  mov     rcx, rdi
0x18004181c  call    ?CreateSolidColorBrush@xpsrdr@@YA?AV?$shared_ptr@UID2D1Brush@@@std@@AEAURenderState@1@AEBU_D3DCOLORVALUE@@PEAM@Z; xpsrdr::CreateSolidColorBrush(xpsrdr::RenderState &,_D3DCOLORVALUE const &,float *)
0x180041821  nop
0x180041822  lea     rcx, [rbp+57h+var_A0]
0x180041826  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x18004182b  nop
0x18004182c  lea     rcx, [rbp+57h+var_90]
0x180041830  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180041835  mov     rax, rdi
0x180041838  mov     rcx, [rbp+57h+var_40]
0x18004183c  xor     rcx, rsp; StackCookie
0x18004183f  call    __security_check_cookie
0x180041844  add     rsp, 0C8h
0x18004184b  pop     r15
0x18004184d  pop     r14
0x18004184f  pop     rdi
0x180041850  pop     rsi
0x180041851  pop     rbx
0x180041852  pop     rbp
0x180041853  retn
```
