# xpsrdr::CreateD2D1StrokeStyle(xpsrdr::RenderState &,std::shared_ptr<IXpsOMPath> const &)

- ea: `0x1800b692c`
- end: `0x1800b6d3f`
- name: `?CreateD2D1StrokeStyle@xpsrdr@@YA?AV?$shared_ptr@UID2D1StrokeStyle1@@@std@@AEAURenderState@1@AEBV?$shared_ptr@UIXpsOMPath@@@3@@Z`
- size: `1043`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1800b0710`

## callees

- `0x180003180`
- `0x1800a2c1c`
- `0x1800a5230`
- `0x1800a9714`
- `0x1800ad2c4`
- `0x1800b20e8`
- `0x1800b6770`
- `0x1800b681c`
- `0x1800b692c`
- `0x1800b6d48`
- `0x1800b6d88`
- `0x1800c3010`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall xpsrdr::CreateD2D1StrokeStyle(_QWORD *a1, __int64 a2, __int64 **a3)
{
  __int64 *v6; // rcx
  __int64 v7; // rax
  int v8; // edi
  int v9; // edx
  const char *v10; // r8
  int v11; // r9d
  int v12; // eax
  int v13; // edx
  const char *v14; // r8
  int v15; // r9d
  float v16; // xmm6_4
  unsigned __int64 i; // rdi
  int v18; // eax
  int v19; // edx
  const char *v20; // r8
  int v21; // r9d
  float v22; // xmm6_4
  int v23; // eax
  int v24; // edx
  const char *v25; // r8
  int v26; // r9d
  int v27; // eax
  int v28; // edx
  const char *v29; // r8
  int v30; // r9d
  int v31; // eax
  int v32; // edx
  const char *v33; // r8
  int v34; // r9d
  int v35; // eax
  enum __MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0007 v36; // edx
  const char *v37; // r8
  int v38; // r9d
  int v39; // eax
  int v40; // edx
  const char *v41; // r8
  int v42; // r9d
  int v43; // eax
  int v44; // edx
  const char *v45; // r8
  int v46; // r9d
  int v47; // eax
  int v48; // edx
  const char *v49; // r8
  int v50; // r9d
  int v51; // r15d
  float v52; // xmm7_4
  bool v53; // bl
  __m64 *v54; // rax
  float *v55; // rax
  enum __MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0007 v56; // edx
  int v57; // r14d
  int v58; // xmm6_4
  enum D2D1_LINE_JOIN v59; // esi
  enum __MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0005 v60; // edx
  enum D2D1_CAP_STYLE v61; // edi
  enum __MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0005 v62; // edx
  enum D2D1_CAP_STYLE v63; // ebx
  enum __MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0005 v64; // edx
  __int64 v65; // rcx
  __int64 (__fastcall *v66)(__int64, _DWORD *, __int64, _QWORD, __m128d *); // r10
  __int64 v67; // r8
  int v68; // ebx
  int v69; // edx
  const char *v70; // r8
  int v71; // r9d
  __int64 v73; // [rsp+38h] [rbp-A9h] BYREF
  xpsrdr *v74; // [rsp+40h] [rbp-A1h] BYREF
  unsigned int v75; // [rsp+48h] [rbp-99h] BYREF
  float v76; // [rsp+4Ch] [rbp-95h] BYREF
  float v77; // [rsp+50h] [rbp-91h] BYREF
  int v78; // [rsp+54h] [rbp-8Dh] BYREF
  unsigned int v79; // [rsp+58h] [rbp-89h] BYREF
  unsigned int v80; // [rsp+5Ch] [rbp-85h] BYREF
  unsigned int v81; // [rsp+60h] [rbp-81h] BYREF
  int v82; // [rsp+64h] [rbp-7Dh]
  __m128d v83; // [rsp+68h] [rbp-79h] BYREF
  __m128d v84; // [rsp+78h] [rbp-69h]
  std::_Ref_count_base *v85[2]; // [rsp+88h] [rbp-59h] BYREF
  __int128 v86; // [rsp+98h] [rbp-49h] BYREF
  __int64 v87; // [rsp+A8h] [rbp-39h]
  _QWORD *v88; // [rsp+B0h] [rbp-31h]
  _DWORD v89[8]; // [rsp+B8h] [rbp-29h] BYREF

  v88 = a1;
  v82 = 0;
  *(_OWORD *)v85 = 0;
  LODWORD(v74) = 0;
  v6 = *a3;
  v7 = **a3;
  v83.m128d_f64[0] = 0.0;
  *(_QWORD *)&v83.m128d_f64[1] = &v74;
  *(_QWORD *)&v84.m128d_f64[0] = v85;
  v8 = (*(__int64 (__fastcall **)(__int64 *, __m128d *))(v7 + 368))(v6, &v83);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v83);
  if ( (int)v74 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v74, v9, v10, v11);
  if ( v8 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v8, v9, v10, v11);
  LODWORD(v73) = 0;
  v12 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, __int64 *))(*(_QWORD *)v85[0] + 24LL))(v85[0], &v73);
  if ( v12 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v12, v13, v14, v15);
  v86 = 0;
  v87 = 0;
  std::vector<float>::_Construct_n<>(&v86, (unsigned int)(2 * v73));
  v16 = 0.0;
  for ( i = 0; i < (unsigned int)v73; ++i )
  {
    v74 = 0;
    v18 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD, xpsrdr **))(*(_QWORD *)v85[0] + 32LL))(
            v85[0],
            (unsigned int)i,
            &v74);
    if ( v18 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v18, v19, v20, v21);
    v22 = *(float *)&v74 + v16;
    *(_DWORD *)(v86 + 8 * i) = (_DWORD)v74;
    v16 = v22 + *((float *)&v74 + 1);
    *(_DWORD *)(v86 + 8 * i + 4) = HIDWORD(v74);
  }
  v81 = 0;
  v23 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(**a3 + 408))(*a3, &v81);
  if ( v23 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v23, v24, v25, v26);
  v80 = 0;
  v27 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(**a3 + 424))(*a3, &v80);
  if ( v27 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v27, v28, v29, v30);
  v79 = 0;
  v31 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(**a3 + 376))(*a3, &v79);
  if ( v31 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v31, v32, v33, v34);
  v75 = 0;
  v35 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(**a3 + 440))(*a3, &v75);
  if ( v35 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v35, v36, v37, v38);
  v78 = 0;
  if ( xpsrdr::D2D1MapLineJoin((xpsrdr *)v75, v36) == D2D1_LINE_JOIN_MITER )
  {
    v39 = (*(__int64 (__fastcall **)(__int64 *, int *))(**a3 + 456))(*a3, &v78);
    if ( v39 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v39, v40, v41, v42);
  }
  v76 = 0.0;
  v43 = (*(__int64 (__fastcall **)(__int64 *, float *))(**a3 + 392))(*a3, &v76);
  if ( v43 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v43, v44, v45, v46);
  v77 = 0.0;
  v47 = (*(__int64 (__fastcall **)(__int64 *, float *))(**a3 + 472))(*a3, &v77);
  if ( v47 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v47, v48, v49, v50);
  v51 = 0;
  v52 = v76;
  v53 = COERCE_FLOAT(LODWORD(v16) ^ _xmm) > v76;
  v54 = (__m64 *)std::stack<D2D_MATRIX_3X2_F>::top(a2 + 488);
  v83 = _mm_cvtps_pd((__m64)v54->m64_u64);
  v84 = _mm_cvtps_pd(v54[1]);
  v55 = (float *)xpsrdr::ScaleCalculator::operator()((xpsrdr::ScaleCalculator *)&v83);
  if ( v53 && (float)*(int *)(a2 + 532) > (float)(v77 * *v55) )
  {
    LOBYTE(v51) = *(_DWORD *)(a2 + 532) <= 1;
    ++v51;
  }
  *a1 = 0;
  a1[1] = 0;
  v82 = 1;
  v57 = (_DWORD)v73 != 0 ? 5 : 0;
  v58 = v78;
  v59 = xpsrdr::D2D1MapLineJoin((xpsrdr *)v75, v56);
  v61 = xpsrdr::D2D1MapLineCap((xpsrdr *)v79, v60);
  v63 = xpsrdr::D2D1MapLineCap((xpsrdr *)v80, v62);
  v89[0] = xpsrdr::D2D1MapLineCap((xpsrdr *)v81, v64);
  v89[1] = v63;
  v89[2] = v61;
  v89[3] = v59;
  v89[4] = v58;
  v89[5] = v57;
  *(float *)&v89[6] = v52;
  v89[7] = v51;
  LODWORD(v74) = 0;
  v65 = *(_QWORD *)(a2 + 16);
  v66 = *(__int64 (__fastcall **)(__int64, _DWORD *, __int64, _QWORD, __m128d *))(*(_QWORD *)v65 + 144LL);
  v83.m128d_f64[0] = 0.0;
  *(_QWORD *)&v83.m128d_f64[1] = &v74;
  *(_QWORD *)&v84.m128d_f64[0] = a1;
  v67 = 0;
  if ( v57 == 5 )
    v67 = v86;
  v68 = v66(v65, v89, v67, (unsigned int)(2 * v73), &v83);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v83);
  if ( (int)v74 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v74, v69, v70, v71);
  if ( v68 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v68, v69, v70, v71);
  std::vector<float>::_Tidy(&v86);
  if ( v85[1] )
    std::_Ref_count_base::_Decref(v85[1]);
  return a1;
}

```

## disassembly

```asm
0x1800b692c  mov     rax, rsp
0x1800b692f  mov     [rax+20h], rbx
0x1800b6933  push    rbp
0x1800b6934  push    rsi
0x1800b6935  push    rdi
0x1800b6936  push    r12
0x1800b6938  push    r13
0x1800b693a  push    r14
0x1800b693c  push    r15
0x1800b693e  lea     rbp, [rax-5Fh]
0x1800b6942  sub     rsp, 100h
0x1800b6949  movaps  xmmword ptr [rax-48h], xmm6
0x1800b694d  movaps  xmmword ptr [rax-58h], xmm7
0x1800b6951  mov     rax, cs:__security_cookie
0x1800b6958  xor     rax, rsp
0x1800b695b  mov     [rbp+57h+var_60], rax
0x1800b695f  mov     rbx, r8
0x1800b6962  mov     r13, rdx
0x1800b6965  mov     r12, rcx
0x1800b6968  mov     [rbp+57h+var_88], rcx
0x1800b696c  xor     esi, esi
0x1800b696e  mov     dword ptr [rbp+57h+var_D8+4], esi
0x1800b6971  xorps   xmm0, xmm0
0x1800b6974  movdqu  xmmword ptr [rbp+57h+var_B0], xmm0
0x1800b6979  mov     dword ptr [rsp+130h+var_F8], esi
0x1800b697d  mov     rcx, [r8]
0x1800b6980  mov     rax, [rcx]
0x1800b6983  mov     qword ptr [rbp+57h+var_D0], rsi
0x1800b6987  lea     rdx, [rsp+130h+var_F8]
0x1800b698c  mov     qword ptr [rbp+57h+var_D0+8], rdx
0x1800b6990  lea     rdx, [rbp+57h+var_B0]
0x1800b6994  mov     qword ptr [rbp+57h+var_C0], rdx
0x1800b6998  lea     rdx, [rbp+57h+var_D0]
0x1800b699c  mov     rax, [rax+170h]
0x1800b69a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b69a8  mov     edi, eax
0x1800b69aa  lea     rcx, [rbp+57h+var_D0]
0x1800b69ae  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800b69b3  mov     ecx, dword ptr [rsp+130h+var_F8]; this
0x1800b69b7  test    ecx, ecx
0x1800b69b9  jns     short loc_1800B69C1
0x1800b69bb  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b69c1  test    edi, edi
0x1800b69c3  jns     short loc_1800B69CD
0x1800b69c5  mov     ecx, edi; this
0x1800b69c7  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b69cd  mov     dword ptr [rsp+130h+var_100], esi
0x1800b69d1  mov     rcx, [rbp+57h+var_B0]
0x1800b69d5  mov     rax, [rcx]
0x1800b69d8  lea     rdx, [rsp+130h+var_100]
0x1800b69dd  mov     rax, [rax+18h]
0x1800b69e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b69e6  test    eax, eax
0x1800b69e8  jns     short loc_1800B69F2
0x1800b69ea  mov     ecx, eax; this
0x1800b69ec  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b69f2  xorps   xmm0, xmm0
0x1800b69f5  movdqu  [rbp+57h+var_A0], xmm0
0x1800b69fa  mov     [rbp+57h+var_90], rsi
0x1800b69fe  mov     eax, dword ptr [rsp+130h+var_100]
0x1800b6a02  lea     edx, [rax+rax]
0x1800b6a05  lea     rcx, [rbp+57h+var_A0]
0x1800b6a09  call    ??$_Construct_n@$$V@?$vector@MV?$allocator@M@std@@@std@@AEAAX_K@Z; std::vector<float>::_Construct_n<>(unsigned __int64)
0x1800b6a0e  nop
0x1800b6a0f  xorps   xmm6, xmm6
0x1800b6a12  mov     rdi, rsi
0x1800b6a15  mov     eax, dword ptr [rsp+130h+var_100]
0x1800b6a19  cmp     rdi, rax
0x1800b6a1c  jnb     short loc_1800B6A7A
0x1800b6a1e  xor     eax, eax
0x1800b6a20  mov     [rsp+130h+var_F8], rax
0x1800b6a25  mov     rcx, [rbp+57h+var_B0]
0x1800b6a29  mov     rax, [rcx]
0x1800b6a2c  mov     edx, edi
0x1800b6a2e  lea     r8, [rsp+130h+var_F8]
0x1800b6a33  mov     rax, [rax+20h]
0x1800b6a37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6a3c  test    eax, eax
0x1800b6a3e  js      short loc_1800B6A72
0x1800b6a40  movss   xmm1, dword ptr [rsp+130h+var_F8]
0x1800b6a46  movaps  xmm0, xmm1
0x1800b6a49  addss   xmm0, xmm6
0x1800b6a4d  movaps  xmm6, xmm0
0x1800b6a50  mov     rax, qword ptr [rbp+57h+var_A0]
0x1800b6a54  movss   dword ptr [rax+rdi*8], xmm1
0x1800b6a59  movss   xmm0, dword ptr [rsp+130h+var_F8+4]
0x1800b6a5f  addss   xmm6, xmm0
0x1800b6a63  mov     rax, qword ptr [rbp+57h+var_A0]
0x1800b6a67  movss   dword ptr [rax+rdi*8+4], xmm0
0x1800b6a6d  inc     rdi
0x1800b6a70  jmp     short loc_1800B6A15
0x1800b6a72  mov     ecx, eax; this
0x1800b6a74  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b6a7a  mov     dword ptr [rsp+130h+var_D8], esi
0x1800b6a7e  mov     rcx, [rbx]
0x1800b6a81  mov     rax, [rcx]
0x1800b6a84  lea     rdx, [rsp+130h+var_D8]
0x1800b6a89  mov     rax, [rax+198h]
0x1800b6a90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6a95  test    eax, eax
0x1800b6a97  jns     short loc_1800B6AA1
0x1800b6a99  mov     ecx, eax; this
0x1800b6a9b  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b6aa1  mov     dword ptr [rsp+130h+var_E0+4], esi
0x1800b6aa5  mov     rcx, [rbx]
0x1800b6aa8  mov     rax, [rcx]
0x1800b6aab  lea     rdx, [rsp+130h+var_E0+4]
0x1800b6ab0  mov     rax, [rax+1A8h]
0x1800b6ab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6abc  test    eax, eax
0x1800b6abe  jns     short loc_1800B6AC8
0x1800b6ac0  mov     ecx, eax; this
0x1800b6ac2  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b6ac8  mov     dword ptr [rsp+130h+var_E0], esi
0x1800b6acc  mov     rcx, [rbx]
0x1800b6acf  mov     rax, [rcx]
0x1800b6ad2  lea     rdx, [rsp+130h+var_E0]
0x1800b6ad7  mov     rax, [rax+178h]
0x1800b6ade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6ae3  test    eax, eax
0x1800b6ae5  jns     short loc_1800B6AEF
0x1800b6ae7  mov     ecx, eax; this
0x1800b6ae9  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b6aef  mov     dword ptr [rsp+130h+var_F0], esi
0x1800b6af3  mov     rcx, [rbx]
0x1800b6af6  mov     rax, [rcx]
0x1800b6af9  lea     rdx, [rsp+130h+var_F0]
0x1800b6afe  mov     rax, [rax+1B8h]
0x1800b6b05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6b0a  test    eax, eax
0x1800b6b0c  jns     short loc_1800B6B16
0x1800b6b0e  mov     ecx, eax; this
0x1800b6b10  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b6b16  mov     [rsp+130h+var_E4], 0
0x1800b6b1e  mov     ecx, dword ptr [rsp+130h+var_F0]; this
0x1800b6b22  call    ?D2D1MapLineJoin@xpsrdr@@YA?AW4D2D1_LINE_JOIN@@W4__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0007@@@Z; xpsrdr::D2D1MapLineJoin(__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0007)
0x1800b6b27  test    eax, eax
0x1800b6b29  jnz     short loc_1800B6B4E
0x1800b6b2b  mov     rcx, [rbx]
0x1800b6b2e  mov     rax, [rcx]
0x1800b6b31  lea     rdx, [rsp+130h+var_E4]
0x1800b6b36  mov     rax, [rax+1C8h]
0x1800b6b3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6b42  test    eax, eax
0x1800b6b44  jns     short loc_1800B6B4E
0x1800b6b46  mov     ecx, eax; this
0x1800b6b48  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b6b4e  mov     dword ptr [rsp+130h+var_F0+4], 0
0x1800b6b56  mov     rcx, [rbx]
0x1800b6b59  mov     rax, [rcx]
0x1800b6b5c  lea     rdx, [rsp+130h+var_F0+4]
0x1800b6b61  mov     rax, [rax+188h]
0x1800b6b68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6b6d  test    eax, eax
0x1800b6b6f  jns     short loc_1800B6B79
0x1800b6b71  mov     ecx, eax; this
0x1800b6b73  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b6b79  mov     [rsp+130h+var_E8], 0
0x1800b6b81  mov     rcx, [rbx]
0x1800b6b84  mov     rax, [rcx]
0x1800b6b87  lea     rdx, [rsp+130h+var_E8]
0x1800b6b8c  mov     rax, [rax+1D8h]
0x1800b6b93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6b98  test    eax, eax
0x1800b6b9a  jns     short loc_1800B6BA4
0x1800b6b9c  mov     ecx, eax; this
0x1800b6b9e  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b6ba4  mov     r15d, esi
0x1800b6ba7  xorps   xmm6, cs:__xmm@80000000800000008000000080000000
0x1800b6bae  movss   xmm7, dword ptr [rsp+130h+var_F0+4]
0x1800b6bb4  comiss  xmm6, xmm7
0x1800b6bb7  setnbe  bl
0x1800b6bba  lea     rcx, [r13+1E8h]
0x1800b6bc1  call    ?top@?$stack@UD2D_MATRIX_3X2_F@@V?$deque@UD2D_MATRIX_3X2_F@@V?$allocator@UD2D_MATRIX_3X2_F@@@std@@@std@@@std@@QEAAAEAUD2D_MATRIX_3X2_F@@XZ; std::stack<D2D_MATRIX_3X2_F>::top(void)
0x1800b6bc6  cvtps2pd xmm0, qword ptr [rax]
0x1800b6bc9  movups  [rbp+57h+var_D0], xmm0
0x1800b6bcd  cvtps2pd xmm0, qword ptr [rax+8]
0x1800b6bd1  movups  [rbp+57h+var_C0], xmm0
0x1800b6bd5  lea     rdx, [rsp+130h+var_F8]
0x1800b6bda  lea     rcx, [rbp+57h+var_D0]; this
0x1800b6bde  call    ??RScaleCalculator@xpsrdr@@QEBA?AUMinMaxScaling@1@XZ; xpsrdr::ScaleCalculator::operator()(void)
0x1800b6be3  test    bl, bl
0x1800b6be5  jz      short loc_1800B6C0E
0x1800b6be7  mov     ecx, [r13+214h]
0x1800b6bee  movss   xmm1, [rsp+130h+var_E8]
0x1800b6bf4  mulss   xmm1, dword ptr [rax]
0x1800b6bf8  movd    xmm0, ecx
0x1800b6bfc  cvtdq2ps xmm0, xmm0
0x1800b6bff  comiss  xmm0, xmm1
0x1800b6c02  jbe     short loc_1800B6C0E
0x1800b6c04  cmp     ecx, 1
0x1800b6c07  setle   r15b
0x1800b6c0b  inc     r15d
0x1800b6c0e  mov     [r12], rsi
0x1800b6c12  mov     [r12+8], rsi
0x1800b6c17  mov     dword ptr [rbp+57h+var_D8+4], 1
0x1800b6c1e  mov     eax, dword ptr [rsp+130h+var_100]
0x1800b6c22  neg     eax
0x1800b6c24  sbb     r14d, r14d
0x1800b6c27  and     r14d, 5
0x1800b6c2b  movss   xmm6, [rsp+130h+var_E4]
0x1800b6c31  mov     ecx, dword ptr [rsp+130h+var_F0]; this
0x1800b6c35  call    ?D2D1MapLineJoin@xpsrdr@@YA?AW4D2D1_LINE_JOIN@@W4__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0007@@@Z; xpsrdr::D2D1MapLineJoin(__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0007)
0x1800b6c3a  mov     esi, eax
0x1800b6c3c  mov     ecx, dword ptr [rsp+130h+var_E0]; this
0x1800b6c40  call    ?D2D1MapLineCap@xpsrdr@@YA?AW4D2D1_CAP_STYLE@@W4__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0005@@@Z; xpsrdr::D2D1MapLineCap(__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0005)
0x1800b6c45  mov     edi, eax
0x1800b6c47  mov     ecx, dword ptr [rsp+130h+var_E0+4]; this
0x1800b6c4b  call    ?D2D1MapLineCap@xpsrdr@@YA?AW4D2D1_CAP_STYLE@@W4__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0005@@@Z; xpsrdr::D2D1MapLineCap(__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0005)
0x1800b6c50  mov     ebx, eax
0x1800b6c52  mov     ecx, dword ptr [rsp+130h+var_D8]; this
0x1800b6c56  call    ?D2D1MapLineCap@xpsrdr@@YA?AW4D2D1_CAP_STYLE@@W4__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0005@@@Z; xpsrdr::D2D1MapLineCap(__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0005)
0x1800b6c5b  mov     [rbp+57h+var_80], eax
0x1800b6c5e  mov     [rbp+57h+var_7C], ebx
0x1800b6c61  mov     [rbp+57h+var_78], edi
0x1800b6c64  mov     [rbp+57h+var_74], esi
0x1800b6c67  movss   [rbp+57h+var_70], xmm6
0x1800b6c6c  mov     [rbp+57h+var_6C], r14d
0x1800b6c70  movss   [rbp+57h+var_68], xmm7
0x1800b6c75  mov     [rbp+57h+var_64], r15d
0x1800b6c79  mov     dword ptr [rsp+130h+var_F8], 0
0x1800b6c81  mov     rcx, [r13+10h]
0x1800b6c85  mov     rax, [rcx]
0x1800b6c88  mov     r10, [rax+90h]
0x1800b6c8f  mov     qword ptr [rbp+57h+var_D0], 0
0x1800b6c97  lea     rax, [rsp+130h+var_F8]
0x1800b6c9c  mov     qword ptr [rbp+57h+var_D0+8], rax
0x1800b6ca0  mov     qword ptr [rbp+57h+var_C0], r12
0x1800b6ca4  mov     eax, dword ptr [rsp+130h+var_100]
0x1800b6ca8  lea     r9d, [rax+rax]
0x1800b6cac  xor     r8d, r8d
0x1800b6caf  cmp     r14d, 5
0x1800b6cb3  cmovz   r8, qword ptr [rbp+57h+var_A0]
0x1800b6cb8  lea     rax, [rbp+57h+var_D0]
0x1800b6cbc  mov     [rsp+130h+var_110], rax
0x1800b6cc1  lea     rdx, [rbp+57h+var_80]
0x1800b6cc5  mov     rax, r10
0x1800b6cc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6ccd  mov     ebx, eax
0x1800b6ccf  lea     rcx, [rbp+57h+var_D0]
0x1800b6cd3  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800b6cd8  mov     ecx, dword ptr [rsp+130h+var_F8]; this
0x1800b6cdc  test    ecx, ecx
0x1800b6cde  jns     short loc_1800B6CE6
0x1800b6ce0  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b6ce6  test    ebx, ebx
0x1800b6ce8  jns     short loc_1800B6CF2
0x1800b6cea  mov     ecx, ebx; this
0x1800b6cec  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b6cf2  lea     rcx, [rbp+57h+var_A0]
0x1800b6cf6  call    ?_Tidy@?$vector@MV?$allocator@M@std@@@std@@AEAAXXZ; std::vector<float>::_Tidy(void)
0x1800b6cfb  nop
0x1800b6cfc  mov     rcx, [rbp+57h+var_B0+8]; this
0x1800b6d00  test    rcx, rcx
0x1800b6d03  jz      short loc_1800B6D0A
0x1800b6d05  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800b6d0a  mov     rax, r12
0x1800b6d0d  mov     rcx, [rbp+57h+var_60]
0x1800b6d11  xor     rcx, rsp; StackCookie
0x1800b6d14  call    __security_check_cookie
0x1800b6d19  lea     r11, [rsp+130h+var_30]
0x1800b6d21  mov     rbx, [r11+58h]
0x1800b6d25  movaps  xmm6, xmmword ptr [r11-10h]
0x1800b6d2a  movaps  xmm7, xmmword ptr [r11-20h]
0x1800b6d2f  mov     rsp, r11
0x1800b6d32  pop     r15
0x1800b6d34  pop     r14
0x1800b6d36  pop     r13
0x1800b6d38  pop     r12
0x1800b6d3a  pop     rdi
0x1800b6d3b  pop     rsi
0x1800b6d3c  pop     rbp
0x1800b6d3d  retn
```
