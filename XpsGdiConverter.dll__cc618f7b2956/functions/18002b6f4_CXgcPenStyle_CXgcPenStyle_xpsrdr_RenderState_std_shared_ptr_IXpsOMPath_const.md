# CXgcPenStyle::CXgcPenStyle(xpsrdr::RenderState &,std::shared_ptr<IXpsOMPath> const &)

- ea: `0x18002b6f4`
- end: `0x18002b973`
- name: `??0CXgcPenStyle@@QEAA@AEAURenderState@xpsrdr@@AEBV?$shared_ptr@UIXpsOMPath@@@std@@@Z`
- size: `639`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18002b9f4`

## callees

- `0x180009334`
- `0x18000da08`
- `0x18000e0d8`
- `0x18000e15c`
- `0x18000e174`
- `0x18000e4c4`
- `0x180011b0c`
- `0x18002b6f4`
- `0x18002ba80`
- `0x180037278`
- `0x18003f5ec`
- `0x18004a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CXgcPenStyle::CXgcPenStyle(__int64 a1, __int64 a2, __int64 **a3)
{
  _QWORD *v5; // r14
  _QWORD *v6; // rcx
  _QWORD *v7; // r8
  __int64 **v8; // r8
  __int64 v9; // r9
  int v10; // eax
  int v11; // edx
  const char *v12; // r8
  int v13; // r9d
  int v14; // eax
  int v15; // edx
  const char *v16; // r8
  int v17; // r9d
  int v18; // eax
  int v19; // edx
  const char *v20; // r8
  int v21; // r9d
  int v22; // eax
  int v23; // edx
  const char *v24; // r8
  int v25; // r9d
  int v26; // eax
  int v27; // edx
  const char *v28; // r8
  int v29; // r9d
  int v30; // eax
  int v31; // edx
  const char *v32; // r8
  int v33; // r9d
  float *v34; // rsi
  int v35; // eax
  int v36; // edx
  const char *v37; // r8
  int v38; // r9d
  __int64 *v39; // rcx
  __int64 v40; // rax
  int v41; // edi
  int v42; // edx
  const char *v43; // r8
  int v44; // r9d
  int v45; // eax
  int v46; // edx
  const char *v47; // r8
  int v48; // r9d
  float v49; // xmm6_4
  unsigned __int64 i; // rdi
  int v51; // eax
  int v52; // edx
  const char *v53; // r8
  int v54; // r9d
  bool v55; // al
  float v56; // xmm0_4
  _QWORD v58[2]; // [rsp+20h] [rbp-40h] BYREF
  _QWORD v59[4]; // [rsp+30h] [rbp-30h] BYREF
  unsigned int v60; // [rsp+A0h] [rbp+40h] BYREF
  xpsrdr *v61; // [rsp+A8h] [rbp+48h] BYREF

  v5 = (_QWORD *)(a1 + 32);
  std::vector<CCoordinate>::vector<CCoordinate>(a1 + 32, a2);
  std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(a1 + 64);
  std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(v6, v7);
  xpsrdr::CreateD2D1StrokeStyle((_QWORD *)(a1 + 80), v9, v8);
  v10 = (*(__int64 (__fastcall **)(__int64 *, __int64))(**a3 + 376))(*a3, a1);
  if ( v10 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v10, v11, v12, v13);
  v14 = (*(__int64 (__fastcall **)(__int64 *, __int64))(**a3 + 408))(*a3, a1 + 4);
  if ( v14 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v14, v15, v16, v17);
  v18 = (*(__int64 (__fastcall **)(__int64 *, __int64))(**a3 + 424))(*a3, a1 + 8);
  if ( v18 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v18, v19, v20, v21);
  v22 = (*(__int64 (__fastcall **)(__int64 *, __int64))(**a3 + 440))(*a3, a1 + 12);
  if ( v22 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v22, v23, v24, v25);
  v26 = (*(__int64 (__fastcall **)(__int64 *, __int64))(**a3 + 472))(*a3, a1 + 16);
  if ( v26 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v26, v27, v28, v29);
  v30 = (*(__int64 (__fastcall **)(__int64 *, __int64))(**a3 + 456))(*a3, a1 + 20);
  if ( v30 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v30, v31, v32, v33);
  v34 = (float *)(a1 + 24);
  v35 = (*(__int64 (__fastcall **)(__int64 *, __int64))(**a3 + 392))(*a3, a1 + 24);
  if ( v35 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v35, v36, v37, v38);
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v58);
  LODWORD(v61) = 0;
  v39 = *a3;
  v40 = **a3;
  v59[0] = 0;
  v59[1] = &v61;
  v59[2] = v58;
  v41 = (*(__int64 (__fastcall **)(__int64 *, _QWORD *))(v40 + 368))(v39, v59);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v59);
  if ( (int)v61 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v61, v42, v43, v44);
  if ( v41 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v41, v42, v43, v44);
  v60 = 0;
  v45 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(*(_QWORD *)v58[0] + 24LL))(v58[0], &v60);
  if ( v45 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v45, v46, v47, v48);
  std::vector<float>::resize(v5, 2 * v60);
  v49 = 0.0;
  for ( i = 0; i < v60; ++i )
  {
    v61 = 0;
    v51 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, xpsrdr **))(*(_QWORD *)v58[0] + 32LL))(
            v58[0],
            (unsigned int)i,
            &v61);
    if ( v51 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v51, v52, v53, v54);
    *(_QWORD *)(*v5 + 8 * i) = v61;
    v49 = (float)(*(float *)&v61 + v49) + *((float *)&v61 + 1);
  }
  v55 = COERCE_FLOAT(LODWORD(v49) ^ _xmm) > *v34;
  *(_BYTE *)(a1 + 56) = v55;
  if ( v55 )
  {
    v56 = o_fmodf_0();
    if ( v56 != 0.0 )
      *v34 = v56 + *v34;
  }
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(v58);
  return a1;
}

```

## disassembly

```asm
0x18002b6f4  mov     [rsp-28h+arg_0], rcx
0x18002b6f9  push    rbp
0x18002b6fa  push    rbx
0x18002b6fb  push    rsi
0x18002b6fc  push    rdi
0x18002b6fd  push    r14
0x18002b6ff  mov     rbp, rsp
0x18002b702  sub     rsp, 60h
0x18002b706  movaps  [rsp+60h+var_10], xmm6
0x18002b70b  mov     rdi, r8
0x18002b70e  mov     r9, rdx
0x18002b711  mov     rbx, rcx
0x18002b714  lea     r14, [rcx+20h]
0x18002b718  mov     rcx, r14
0x18002b71b  call    ??0?$vector@UCCoordinate@@V?$allocator@UCCoordinate@@@std@@@std@@QEAA@XZ; std::vector<CCoordinate>::vector<CCoordinate>(void)
0x18002b720  nop
0x18002b721  lea     rcx, [rbx+40h]
0x18002b725  call    ??0?$_Ptr_base@UID3D11DeviceContext@@@std@@IEAA@XZ; std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(void)
0x18002b72a  mov     rdx, r8
0x18002b72d  call    ??$_Copy_construct_from@UIWICImagingFactory@@@?$_Ptr_base@UIWICImagingFactory@@@std@@IEAAXAEBV?$shared_ptr@UIWICImagingFactory@@@1@@Z; std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(std::shared_ptr<IWICImagingFactory> const &)
0x18002b732  nop
0x18002b733  lea     rcx, [rbx+50h]
0x18002b737  mov     rdx, r9
0x18002b73a  call    ?CreateD2D1StrokeStyle@xpsrdr@@YA?AV?$shared_ptr@UID2D1StrokeStyle1@@@std@@AEAURenderState@1@AEBV?$shared_ptr@UIXpsOMPath@@@3@@Z; xpsrdr::CreateD2D1StrokeStyle(xpsrdr::RenderState &,std::shared_ptr<IXpsOMPath> const &)
0x18002b73f  nop
0x18002b740  mov     rcx, [rdi]
0x18002b743  mov     rax, [rcx]
0x18002b746  mov     rdx, rbx
0x18002b749  mov     rax, [rax+178h]
0x18002b750  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b755  test    eax, eax
0x18002b757  jns     short loc_18002B761
0x18002b759  mov     ecx, eax; this
0x18002b75b  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002b761  mov     rcx, [rdi]
0x18002b764  mov     rax, [rcx]
0x18002b767  lea     rdx, [rbx+4]
0x18002b76b  mov     rax, [rax+198h]
0x18002b772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b777  test    eax, eax
0x18002b779  jns     short loc_18002B783
0x18002b77b  mov     ecx, eax; this
0x18002b77d  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002b783  mov     rcx, [rdi]
0x18002b786  mov     rax, [rcx]
0x18002b789  lea     rdx, [rbx+8]
0x18002b78d  mov     rax, [rax+1A8h]
0x18002b794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b799  test    eax, eax
0x18002b79b  jns     short loc_18002B7A5
0x18002b79d  mov     ecx, eax; this
0x18002b79f  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002b7a5  mov     rcx, [rdi]
0x18002b7a8  mov     rax, [rcx]
0x18002b7ab  lea     rdx, [rbx+0Ch]
0x18002b7af  mov     rax, [rax+1B8h]
0x18002b7b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b7bb  test    eax, eax
0x18002b7bd  jns     short loc_18002B7C7
0x18002b7bf  mov     ecx, eax; this
0x18002b7c1  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002b7c7  mov     rcx, [rdi]
0x18002b7ca  mov     rax, [rcx]
0x18002b7cd  lea     rdx, [rbx+10h]
0x18002b7d1  mov     rax, [rax+1D8h]
0x18002b7d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b7dd  test    eax, eax
0x18002b7df  jns     short loc_18002B7E9
0x18002b7e1  mov     ecx, eax; this
0x18002b7e3  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002b7e9  mov     rcx, [rdi]
0x18002b7ec  mov     rax, [rcx]
0x18002b7ef  lea     rdx, [rbx+14h]
0x18002b7f3  mov     rax, [rax+1C8h]
0x18002b7fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b7ff  test    eax, eax
0x18002b801  jns     short loc_18002B80B
0x18002b803  mov     ecx, eax; this
0x18002b805  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002b80b  mov     rcx, [rdi]
0x18002b80e  lea     rsi, [rbx+18h]
0x18002b812  mov     rax, [rcx]
0x18002b815  mov     rdx, rsi
0x18002b818  mov     rax, [rax+188h]
0x18002b81f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b824  test    eax, eax
0x18002b826  jns     short loc_18002B830
0x18002b828  mov     ecx, eax; this
0x18002b82a  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002b830  lea     rcx, [rbp+var_40]
0x18002b834  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18002b839  nop
0x18002b83a  mov     dword ptr [rbp+arg_18], 0
0x18002b841  mov     rcx, [rdi]
0x18002b844  mov     rax, [rcx]
0x18002b847  mov     [rbp+var_30], 0
0x18002b84f  lea     rdx, [rbp+arg_18]
0x18002b853  mov     [rbp+var_28], rdx
0x18002b857  lea     rdx, [rbp+var_40]
0x18002b85b  mov     [rbp+var_20], rdx
0x18002b85f  lea     rdx, [rbp+var_30]
0x18002b863  mov     rax, [rax+170h]
0x18002b86a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b86f  mov     edi, eax
0x18002b871  lea     rcx, [rbp+var_30]
0x18002b875  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18002b87a  mov     ecx, dword ptr [rbp+arg_18]; this
0x18002b87d  test    ecx, ecx
0x18002b87f  jns     short loc_18002B887
0x18002b881  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002b887  test    edi, edi
0x18002b889  jns     short loc_18002B893
0x18002b88b  mov     ecx, edi; this
0x18002b88d  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002b893  mov     [rbp+arg_10], 0
0x18002b89a  mov     rcx, [rbp+var_40]
0x18002b89e  mov     rax, [rcx]
0x18002b8a1  lea     rdx, [rbp+arg_10]
0x18002b8a5  mov     rax, [rax+18h]
0x18002b8a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b8ae  test    eax, eax
0x18002b8b0  jns     short loc_18002B8BA
0x18002b8b2  mov     ecx, eax; this
0x18002b8b4  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002b8ba  mov     eax, [rbp+arg_10]
0x18002b8bd  lea     edx, [rax+rax]
0x18002b8c0  mov     rcx, r14
0x18002b8c3  call    ?resize@?$vector@MV?$allocator@M@std@@@std@@QEAAX_K@Z; std::vector<float>::resize(unsigned __int64)
0x18002b8c8  xorps   xmm6, xmm6
0x18002b8cb  xor     edi, edi
0x18002b8cd  mov     eax, [rbp+arg_10]
0x18002b8d0  cmp     rdi, rax
0x18002b8d3  jnb     short loc_18002B920
0x18002b8d5  xor     eax, eax
0x18002b8d7  mov     [rbp+arg_18], rax
0x18002b8db  mov     rcx, [rbp+var_40]
0x18002b8df  mov     rax, [rcx]
0x18002b8e2  mov     edx, edi
0x18002b8e4  lea     r8, [rbp+arg_18]
0x18002b8e8  mov     rax, [rax+20h]
0x18002b8ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b8f1  test    eax, eax
0x18002b8f3  js      short loc_18002B918
0x18002b8f5  mov     rax, [r14]
0x18002b8f8  movsd   xmm0, [rbp+arg_18]
0x18002b8fd  movsd   qword ptr [rax+rdi*8], xmm0
0x18002b902  movss   xmm1, dword ptr [rbp+arg_18]
0x18002b907  addss   xmm1, xmm6
0x18002b90b  movaps  xmm6, xmm1
0x18002b90e  addss   xmm6, dword ptr [rbp+arg_18+4]
0x18002b913  inc     rdi
0x18002b916  jmp     short loc_18002B8CD
0x18002b918  mov     ecx, eax; this
0x18002b91a  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002b920  movaps  xmm0, xmm6
0x18002b923  xorps   xmm0, cs:__xmm@80000000800000008000000080000000
0x18002b92a  comiss  xmm0, dword ptr [rsi]
0x18002b92d  setnbe  al
0x18002b930  mov     [rbx+38h], al
0x18002b933  test    al, al
0x18002b935  jz      short loc_18002B956
0x18002b937  movaps  xmm1, xmm6
0x18002b93a  movss   xmm0, dword ptr [rsi]
0x18002b93e  call    _o_fmodf_0
0x18002b943  ucomiss xmm0, cs:__real@00000000
0x18002b94a  jp      short loc_18002B94E
0x18002b94c  jz      short loc_18002B956
0x18002b94e  addss   xmm0, dword ptr [rsi]
0x18002b952  movss   dword ptr [rsi], xmm0
0x18002b956  lea     rcx, [rbp+var_40]
0x18002b95a  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x18002b95f  nop
0x18002b960  mov     rax, rbx
0x18002b963  movaps  xmm6, [rsp+60h+var_10]
0x18002b968  add     rsp, 60h
0x18002b96c  pop     r14
0x18002b96e  pop     rdi
0x18002b96f  pop     rsi
0x18002b970  pop     rbx
0x18002b971  pop     rbp
0x18002b972  retn
```
