# xpsrdr::CreateSolidColorBrush(xpsrdr::RenderState &,std::shared_ptr<IXpsOMBrush> const &,float *)

- ea: `0x1800b54c4`
- end: `0x1800b5673`
- name: `?CreateSolidColorBrush@xpsrdr@@YA?AV?$shared_ptr@UID2D1Brush@@@std@@AEAURenderState@1@AEBV?$shared_ptr@UIXpsOMBrush@@@3@PEAM@Z`
- size: `431`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800b3ecc`

## callees

- `0x180003180`
- `0x1800a2c1c`
- `0x1800a5230`
- `0x1800b20e8`
- `0x1800b540c`
- `0x1800b54c4`
- `0x1800b9aec`
- `0x1800c3010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall xpsrdr::CreateSolidColorBrush(__int64 a1, __int64 a2, _QWORD *a3, __int64 a4)
{
  __int64 (__fastcall ***v8)(_QWORD, GUID *, __int64 *); // rcx
  __int64 (__fastcall **v9)(_QWORD, GUID *, __int64 *); // rax
  int v10; // ebx
  int v11; // edx
  const char *v12; // r8
  int v13; // r9d
  int v14; // eax
  int v15; // edx
  const char *v16; // r8
  int v17; // r9d
  __int64 v18; // rax
  int v19; // ebx
  int v20; // edx
  const char *v21; // r8
  int v22; // r9d
  xpsrdr *v24; // [rsp+20h] [rbp-79h] BYREF
  __int64 v25; // [rsp+28h] [rbp-71h] BYREF
  __int64 v26; // [rsp+30h] [rbp-69h] BYREF
  xpsrdr **v27; // [rsp+38h] [rbp-61h]
  std::_Ref_count_base **v28; // [rsp+40h] [rbp-59h]
  std::_Ref_count_base *v29[2]; // [rsp+50h] [rbp-49h] BYREF
  std::_Ref_count_base *v30[2]; // [rsp+60h] [rbp-39h] BYREF
  __m128 v31; // [rsp+70h] [rbp-29h] BYREF
  _OWORD v32[3]; // [rsp+80h] [rbp-19h] BYREF

  v25 = a1;
  ++*(_DWORD *)(*(_QWORD *)(a2 + 544) + 32LL);
  *(_OWORD *)v30 = 0;
  LODWORD(v24) = 0;
  v8 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*a3;
  v9 = *(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*a3;
  v26 = 0;
  v27 = &v24;
  v28 = v30;
  v10 = (*v9)(v8, &GUID_a06f9f05_3be9_4763_98a8_094fc672e488, &v26);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v26);
  if ( (int)v24 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v24, v11, v12, v13);
  if ( v10 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v10, v11, v12, v13);
  LODWORD(v25) = 0;
  v14 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a3 + 40LL))(*a3, &v25);
  if ( v14 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v14, v15, v16, v17);
  memset(v32, 0, 44);
  *(_OWORD *)v29 = 0;
  LODWORD(v24) = 0;
  v18 = *(_QWORD *)v30[0];
  v26 = 0;
  v27 = &v24;
  v28 = v29;
  v19 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _OWORD *, __int64 *))(v18 + 56))(v30[0], v32, &v26);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v26);
  if ( (int)v24 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v24, v20, v21, v22);
  if ( v19 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v19, v20, v21, v22);
  v31 = (__m128)_mm_loadu_si128((const __m128i *)xpsrdr::GetD2D1Color(&v26, a2, v32, v29));
  v31.m128_f32[3] = _mm_shuffle_ps(v31, v31, 255).m128_f32[0] * *(float *)&v25;
  xpsrdr::CreateSolidColorBrush(a1, a2, &v31, a4);
  if ( v29[1] )
    std::_Ref_count_base::_Decref(v29[1]);
  if ( v30[1] )
    std::_Ref_count_base::_Decref(v30[1]);
  return a1;
}

```

## disassembly

```asm
0x1800b54c4  push    rbp
0x1800b54c6  push    rbx
0x1800b54c7  push    rsi
0x1800b54c8  push    rdi
0x1800b54c9  push    r14
0x1800b54cb  push    r15
0x1800b54cd  lea     rbp, [rsp-2Fh]
0x1800b54d2  sub     rsp, 0C8h
0x1800b54d9  mov     rax, cs:__security_cookie
0x1800b54e0  xor     rax, rsp
0x1800b54e3  mov     [rbp+57h+var_40], rax
0x1800b54e7  mov     r15, r9
0x1800b54ea  mov     r14, r8
0x1800b54ed  mov     rsi, rdx
0x1800b54f0  mov     rdi, rcx
0x1800b54f3  mov     [rbp+57h+var_C8], rcx
0x1800b54f7  mov     rax, [rdx+220h]
0x1800b54fe  inc     dword ptr [rax+20h]
0x1800b5501  xorps   xmm0, xmm0
0x1800b5504  movdqu  xmmword ptr [rbp+57h+var_90], xmm0
0x1800b5509  mov     dword ptr [rbp+57h+var_D0], 0
0x1800b5510  mov     rcx, [r8]
0x1800b5513  mov     rax, [rcx]
0x1800b5516  mov     [rbp+57h+var_C0], 0
0x1800b551e  lea     rdx, [rbp+57h+var_D0]
0x1800b5522  mov     [rbp+57h+var_B8], rdx
0x1800b5526  lea     rdx, [rbp+57h+var_90]
0x1800b552a  mov     [rbp+57h+var_B0], rdx
0x1800b552e  lea     r8, [rbp+57h+var_C0]
0x1800b5532  lea     rdx, _GUID_a06f9f05_3be9_4763_98a8_094fc672e488
0x1800b5539  mov     rax, [rax]
0x1800b553c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5541  mov     ebx, eax
0x1800b5543  lea     rcx, [rbp+57h+var_C0]
0x1800b5547  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800b554c  mov     ecx, dword ptr [rbp+57h+var_D0]; this
0x1800b554f  test    ecx, ecx
0x1800b5551  jns     short loc_1800B5559
0x1800b5553  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b5559  test    ebx, ebx
0x1800b555b  jns     short loc_1800B5565
0x1800b555d  mov     ecx, ebx; this
0x1800b555f  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b5565  mov     dword ptr [rbp+57h+var_C8], 0
0x1800b556c  mov     rcx, [r14]
0x1800b556f  mov     rax, [rcx]
0x1800b5572  lea     rdx, [rbp+57h+var_C8]
0x1800b5576  mov     rax, [rax+28h]
0x1800b557a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b557f  test    eax, eax
0x1800b5581  jns     short loc_1800B558B
0x1800b5583  mov     ecx, eax; this
0x1800b5585  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b558b  xorps   xmm0, xmm0
0x1800b558e  movups  [rbp+57h+var_70], xmm0
0x1800b5592  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x1800b5596  movups  xmmword ptr [rbp+57h+var_60+0Ch], xmm0
0x1800b559a  movdqu  xmmword ptr [rbp+57h+var_A0], xmm0
0x1800b559f  mov     dword ptr [rbp+57h+var_D0], 0
0x1800b55a6  mov     rcx, [rbp+57h+var_90]
0x1800b55aa  mov     rax, [rcx]
0x1800b55ad  mov     [rbp+57h+var_C0], 0
0x1800b55b5  lea     rdx, [rbp+57h+var_D0]
0x1800b55b9  mov     [rbp+57h+var_B8], rdx
0x1800b55bd  lea     rdx, [rbp+57h+var_A0]
0x1800b55c1  mov     [rbp+57h+var_B0], rdx
0x1800b55c5  lea     r8, [rbp+57h+var_C0]
0x1800b55c9  lea     rdx, [rbp+57h+var_70]
0x1800b55cd  mov     rax, [rax+38h]
0x1800b55d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b55d6  mov     ebx, eax
0x1800b55d8  lea     rcx, [rbp+57h+var_C0]
0x1800b55dc  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800b55e1  mov     ecx, dword ptr [rbp+57h+var_D0]; this
0x1800b55e4  test    ecx, ecx
0x1800b55e6  jns     short loc_1800B55EE
0x1800b55e8  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b55ee  test    ebx, ebx
0x1800b55f0  jns     short loc_1800B55FA
0x1800b55f2  mov     ecx, ebx; this
0x1800b55f4  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b55fa  lea     r9, [rbp+57h+var_A0]
0x1800b55fe  lea     r8, [rbp+57h+var_70]
0x1800b5602  mov     rdx, rsi
0x1800b5605  lea     rcx, [rbp+57h+var_C0]
0x1800b5609  call    ?GetD2D1Color@xpsrdr@@YA?AU_D3DCOLORVALUE@@AEAURenderState@1@AEBU__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0024@@AEBV?$shared_ptr@UIXpsOMColorProfileResource@@@std@@@Z; xpsrdr::GetD2D1Color(xpsrdr::RenderState &,__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0024 const &,std::shared_ptr<IXpsOMColorProfileResource> const &)
0x1800b560e  movdqu  xmm0, xmmword ptr [rax]
0x1800b5612  movups  [rbp+57h+var_80], xmm0
0x1800b5616  shufps  xmm0, xmm0, 0FFh
0x1800b561a  mulss   xmm0, dword ptr [rbp+57h+var_C8]
0x1800b561f  movss   dword ptr [rbp+57h+var_80+0Ch], xmm0
0x1800b5624  mov     r9, r15
0x1800b5627  lea     r8, [rbp+57h+var_80]
0x1800b562b  mov     rdx, rsi
0x1800b562e  mov     rcx, rdi
0x1800b5631  call    ?CreateSolidColorBrush@xpsrdr@@YA?AV?$shared_ptr@UID2D1Brush@@@std@@AEAURenderState@1@AEBU_D3DCOLORVALUE@@PEAM@Z; xpsrdr::CreateSolidColorBrush(xpsrdr::RenderState &,_D3DCOLORVALUE const &,float *)
0x1800b5636  nop
0x1800b5637  mov     rcx, [rbp+57h+var_A0+8]; this
0x1800b563b  test    rcx, rcx
0x1800b563e  jz      short loc_1800B5646
0x1800b5640  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800b5645  nop
0x1800b5646  mov     rcx, [rbp+57h+var_90+8]; this
0x1800b564a  test    rcx, rcx
0x1800b564d  jz      short loc_1800B5654
0x1800b564f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800b5654  mov     rax, rdi
0x1800b5657  mov     rcx, [rbp+57h+var_40]
0x1800b565b  xor     rcx, rsp; StackCookie
0x1800b565e  call    __security_check_cookie
0x1800b5663  add     rsp, 0C8h
0x1800b566a  pop     r15
0x1800b566c  pop     r14
0x1800b566e  pop     rdi
0x1800b566f  pop     rsi
0x1800b5670  pop     rbx
0x1800b5671  pop     rbp
0x1800b5672  retn
```
