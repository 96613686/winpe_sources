# xpsrdr::CreateRectGeometry(xpsrdr::RenderState &,D2D_RECT_F const &)

- ea: `0x180033a70`
- end: `0x180033c80`
- name: `?CreateRectGeometry@xpsrdr@@YA?AV?$shared_ptr@UID2D1Geometry@@@std@@AEAURenderState@1@AEBUD2D_RECT_F@@@Z`
- size: `528`
- prototype: ``
- caller_count: `6`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800109e0`
- `0x180018a70`
- `0x180018c90`
- `0x180029334`
- `0x18003ac3c`
- `0x180044d08`

## callees

- `0x18000d7f8`
- `0x18000e130`
- `0x18000e15c`
- `0x18000e4c4`
- `0x180011b0c`
- `0x180033a70`
- `0x180037278`
- `0x18004a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall xpsrdr::CreateRectGeometry(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rdx
  __int64 *v6; // rcx
  __int64 v7; // rax
  int v8; // edi
  int v9; // edx
  const char *v10; // r8
  int v11; // r9d
  __int64 v12; // rax
  int v13; // edi
  int v14; // edx
  const char *v15; // r8
  int v16; // r9d
  __int64 v17; // rax
  __int64 v18; // rax
  int v19; // eax
  int v20; // edx
  const char *v21; // r8
  int v22; // r9d
  _QWORD v24[2]; // [rsp+28h] [rbp-38h] BYREF
  _QWORD v25[2]; // [rsp+38h] [rbp-28h] BYREF
  __int64 v26; // [rsp+48h] [rbp-18h] BYREF
  xpsrdr **v27; // [rsp+50h] [rbp-10h]
  _QWORD *v28; // [rsp+58h] [rbp-8h]
  xpsrdr *v29; // [rsp+88h] [rbp+28h] BYREF
  unsigned __int64 v30; // [rsp+98h] [rbp+38h] BYREF

  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v25);
  LODWORD(v29) = 0;
  v6 = *(__int64 **)(v5 + 16);
  v7 = *v6;
  v26 = 0;
  v27 = &v29;
  v28 = v25;
  v8 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v7 + 80))(v6, &v26);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v26);
  if ( (int)v29 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v29, v9, v10, v11);
  if ( v8 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v8, v9, v10, v11);
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v24);
  LODWORD(v29) = 0;
  v12 = *(_QWORD *)v25[0];
  v26 = 0;
  v27 = &v29;
  v28 = v24;
  v13 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(v12 + 136))(v25[0], &v26);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v26);
  if ( (int)v29 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v29, v14, v15, v16);
  if ( v13 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v13, v14, v15, v16);
  (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v24[0] + 24LL))(v24[0], 1);
  v30 = *(_QWORD *)a3;
  v17 = *(_QWORD *)v24[0];
  v30 = _mm_unpacklo_ps((__m128)(unsigned int)v30, (__m128)HIDWORD(v30)).m128_u64[0];
  (*(void (__fastcall **)(_QWORD, unsigned __int64, _QWORD))(v17 + 40))(v24[0], v30, 0);
  LODWORD(v30) = *(_DWORD *)(a3 + 8);
  HIDWORD(v30) = *(_DWORD *)(a3 + 4);
  (*(void (__fastcall **)(_QWORD, unsigned __int64 *, __int64))(*(_QWORD *)v24[0] + 48LL))(v24[0], &v30, 1);
  v30 = *(_QWORD *)(a3 + 8);
  (*(void (__fastcall **)(_QWORD, unsigned __int64 *, __int64))(*(_QWORD *)v24[0] + 48LL))(v24[0], &v30, 1);
  LODWORD(v30) = *(_DWORD *)a3;
  HIDWORD(v30) = *(_DWORD *)(a3 + 12);
  (*(void (__fastcall **)(_QWORD, unsigned __int64 *, __int64))(*(_QWORD *)v24[0] + 48LL))(v24[0], &v30, 1);
  v18 = std::shared_ptr<IDWriteFactory>::operator-><IDWriteFactory,0>((__int64)v24);
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v18 + 64LL))(v18, 1);
  v19 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v24[0] + 72LL))(v24[0]);
  if ( v19 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v19, v20, v21, v22);
  std::shared_ptr<IWICBitmapSource>::shared_ptr<IWICBitmapSource>(a1, v25);
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(v24);
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(v25);
  return a1;
}

```

## disassembly

```asm
0x180033a70  mov     [rsp-18h+arg_0], rbx
0x180033a75  push    rbp
0x180033a76  push    rsi
0x180033a77  push    rdi
0x180033a78  mov     rbp, rsp
0x180033a7b  sub     rsp, 60h
0x180033a7f  mov     rsi, r8
0x180033a82  mov     rbx, rcx
0x180033a85  lea     rcx, [rbp+var_28]
0x180033a89  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180033a8e  nop
0x180033a8f  mov     dword ptr [rbp+arg_8], 0
0x180033a96  mov     rcx, [rdx+10h]
0x180033a9a  mov     rax, [rcx]
0x180033a9d  mov     [rbp+var_18], 0
0x180033aa5  lea     rdx, [rbp+arg_8]
0x180033aa9  mov     [rbp+var_10], rdx
0x180033aad  lea     rdx, [rbp+var_28]
0x180033ab1  mov     [rbp+var_8], rdx
0x180033ab5  lea     rdx, [rbp+var_18]
0x180033ab9  mov     rax, [rax+50h]
0x180033abd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033ac2  mov     edi, eax
0x180033ac4  lea     rcx, [rbp+var_18]
0x180033ac8  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180033acd  mov     ecx, dword ptr [rbp+arg_8]; this
0x180033ad0  test    ecx, ecx
0x180033ad2  jns     short loc_180033ADA
0x180033ad4  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180033ada  test    edi, edi
0x180033adc  jns     short loc_180033AE6
0x180033ade  mov     ecx, edi; this
0x180033ae0  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180033ae6  lea     rcx, [rbp+var_38]
0x180033aea  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180033aef  nop
0x180033af0  mov     dword ptr [rbp+arg_8], 0
0x180033af7  mov     rcx, [rbp+var_28]
0x180033afb  mov     rax, [rcx]
0x180033afe  mov     [rbp+var_18], 0
0x180033b06  lea     rdx, [rbp+arg_8]
0x180033b0a  mov     [rbp+var_10], rdx
0x180033b0e  lea     rdx, [rbp+var_38]
0x180033b12  mov     [rbp+var_8], rdx
0x180033b16  lea     rdx, [rbp+var_18]
0x180033b1a  mov     rax, [rax+88h]
0x180033b21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033b26  mov     edi, eax
0x180033b28  lea     rcx, [rbp+var_18]
0x180033b2c  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180033b31  mov     ecx, dword ptr [rbp+arg_8]; this
0x180033b34  test    ecx, ecx
0x180033b36  jns     short loc_180033B3E
0x180033b38  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180033b3e  test    edi, edi
0x180033b40  jns     short loc_180033B4A
0x180033b42  mov     ecx, edi; this
0x180033b44  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180033b4a  mov     rcx, [rbp+var_38]
0x180033b4e  mov     rax, [rcx]
0x180033b51  mov     edi, 1
0x180033b56  mov     edx, edi
0x180033b58  mov     rax, [rax+18h]
0x180033b5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033b61  movss   xmm1, dword ptr [rsi]
0x180033b65  movss   dword ptr [rbp+arg_18], xmm1
0x180033b6a  movss   xmm0, dword ptr [rsi+4]
0x180033b6f  movss   dword ptr [rbp+arg_18+4], xmm0
0x180033b74  mov     rcx, [rbp+var_38]
0x180033b78  mov     rax, [rcx]
0x180033b7b  xor     r8d, r8d
0x180033b7e  unpcklps xmm1, xmm0
0x180033b81  movsd   [rbp+arg_18], xmm1
0x180033b86  movq    rdx, xmm1
0x180033b8b  mov     rax, [rax+28h]
0x180033b8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033b94  movss   xmm0, dword ptr [rsi+8]
0x180033b99  movss   dword ptr [rbp+arg_18], xmm0
0x180033b9e  movss   xmm1, dword ptr [rsi+4]
0x180033ba3  movss   dword ptr [rbp+arg_18+4], xmm1
0x180033ba8  mov     rcx, [rbp+var_38]
0x180033bac  mov     rax, [rcx]
0x180033baf  mov     r8d, edi
0x180033bb2  lea     rdx, [rbp+arg_18]
0x180033bb6  mov     rax, [rax+30h]
0x180033bba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033bbf  movss   xmm0, dword ptr [rsi+8]
0x180033bc4  movss   dword ptr [rbp+arg_18], xmm0
0x180033bc9  movss   xmm1, dword ptr [rsi+0Ch]
0x180033bce  movss   dword ptr [rbp+arg_18+4], xmm1
0x180033bd3  mov     rcx, [rbp+var_38]
0x180033bd7  mov     rax, [rcx]
0x180033bda  mov     r8d, edi
0x180033bdd  lea     rdx, [rbp+arg_18]
0x180033be1  mov     rax, [rax+30h]
0x180033be5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033bea  movss   xmm0, dword ptr [rsi]
0x180033bee  movss   dword ptr [rbp+arg_18], xmm0
0x180033bf3  movss   xmm1, dword ptr [rsi+0Ch]
0x180033bf8  movss   dword ptr [rbp+arg_18+4], xmm1
0x180033bfd  mov     rcx, [rbp+var_38]
0x180033c01  mov     rax, [rcx]
0x180033c04  mov     r8d, edi
0x180033c07  lea     rdx, [rbp+arg_18]
0x180033c0b  mov     rax, [rax+30h]
0x180033c0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033c14  lea     rcx, [rbp+var_38]
0x180033c18  call    ??$?CUIDWriteFactory@@$0A@@?$shared_ptr@UIDWriteFactory@@@std@@QEBAPEAUIDWriteFactory@@XZ; std::shared_ptr<IDWriteFactory>::operator-><IDWriteFactory,0>(void)
0x180033c1d  mov     r8, rax
0x180033c20  mov     rcx, [rax]
0x180033c23  mov     rax, [rcx+40h]
0x180033c27  mov     edx, edi
0x180033c29  mov     rcx, r8
0x180033c2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033c31  mov     rcx, [rbp+var_38]
0x180033c35  mov     rax, [rcx]
0x180033c38  mov     rax, [rax+48h]
0x180033c3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033c41  test    eax, eax
0x180033c43  jns     short loc_180033C4D
0x180033c45  mov     ecx, eax; this
0x180033c47  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180033c4d  lea     rdx, [rbp+var_28]
0x180033c51  mov     rcx, rbx
0x180033c54  call    ??$?0UIWICColorTransform@@$0A@@?$shared_ptr@UIWICBitmapSource@@@std@@QEAA@$$QEAV?$shared_ptr@UIWICColorTransform@@@1@@Z; std::shared_ptr<IWICBitmapSource>::shared_ptr<IWICBitmapSource>(std::shared_ptr<IWICColorTransform> &&)
0x180033c59  nop
0x180033c5a  lea     rcx, [rbp+var_38]
0x180033c5e  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180033c63  nop
0x180033c64  lea     rcx, [rbp+var_28]
0x180033c68  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180033c6d  mov     rax, rbx
0x180033c70  mov     rbx, [rsp+60h+arg_0]
0x180033c78  add     rsp, 60h
0x180033c7c  pop     rdi
0x180033c7d  pop     rsi
0x180033c7e  pop     rbp
0x180033c7f  retn
```
