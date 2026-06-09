# xpsrdr::CreateD2D1StrokeStyle(xpsrdr::RenderState &,std::shared_ptr<IXpsOMPath> const &)

- ea: `0x18003f5ec`
- end: `0x18003fa71`
- name: `?CreateD2D1StrokeStyle@xpsrdr@@YA?AV?$shared_ptr@UID2D1StrokeStyle1@@@std@@AEAURenderState@1@AEBV?$shared_ptr@UIXpsOMPath@@@3@@Z`
- size: `1157`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18002b6f4`
- `0x18003a18c`

## callees

- `0x180008830`
- `0x18000e4c4`
- `0x180011b2c`
- `0x180011d1c`
- `0x180024390`
- `0x180024f28`
- `0x180037278`
- `0x1800372e4`
- `0x18003f5ec`
- `0x18003fa78`
- `0x18003fab8`
- `0x18004a010`

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
  unsigned __int64 v17; // rsi
  int i; // edi
  int v19; // eax
  int v20; // edx
  const char *v21; // r8
  int v22; // r9d
  float v23; // xmm6_4
  int v24; // eax
  int v25; // edx
  const char *v26; // r8
  int v27; // r9d
  int v28; // eax
  int v29; // edx
  const char *v30; // r8
  int v31; // r9d
  int v32; // eax
  int v33; // edx
  const char *v34; // r8
  int v35; // r9d
  int v36; // eax
  enum __MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0007 v37; // edx
  const char *v38; // r8
  int v39; // r9d
  int v40; // eax
  int v41; // edx
  const char *v42; // r8
  int v43; // r9d
  int v44; // eax
  int v45; // edx
  const char *v46; // r8
  int v47; // r9d
  int v48; // eax
  int v49; // edx
  const char *v50; // r8
  int v51; // r9d
  int v52; // esi
  float v53; // xmm7_4
  bool v54; // bl
  __m64 *v55; // rcx
  float *v56; // rax
  enum __MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0007 v57; // edx
  int v58; // r15d
  int v59; // xmm6_4
  const char *v60; // rdx
  int v61; // r8d
  enum D2D1_LINE_JOIN v62; // r12d
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
  int v79; // [rsp+58h] [rbp-89h] BYREF
  unsigned int v80; // [rsp+5Ch] [rbp-85h] BYREF
  unsigned int v81; // [rsp+60h] [rbp-81h] BYREF
  int v82; // [rsp+64h] [rbp-7Dh]
  __m128d v83; // [rsp+68h] [rbp-79h] BYREF
  __m128d v84; // [rsp+78h] [rbp-69h]
  std::_Ref_count_base *v85[2]; // [rsp+88h] [rbp-59h] BYREF
  _QWORD v86[4]; // [rsp+98h] [rbp-49h] BYREF
  _DWORD v87[8]; // [rsp+B8h] [rbp-29h] BYREF

  v86[3] = a1;
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
  std::vector<float>::vector<float>(v86, (unsigned int)(2 * v73));
  v16 = 0.0;
  v17 = 0;
  for ( i = 1; v17 < (unsigned int)v73; *(_DWORD *)(v86[0] + 8 * v17++ + 4) = HIDWORD(v74) )
  {
    v74 = 0;
    v19 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD, xpsrdr **))(*(_QWORD *)v85[0] + 32LL))(
            v85[0],
            (unsigned int)v17,
            &v74);
    if ( v19 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v19, v20, v21, v22);
    v23 = *(float *)&v74 + v16;
    *(_DWORD *)(v86[0] + 8 * v17) = (_DWORD)v74;
    v16 = v23 + *((float *)&v74 + 1);
  }
  v81 = 0;
  v24 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(**a3 + 408))(*a3, &v81);
  if ( v24 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v24, v25, v26, v27);
  v80 = 0;
  v28 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(**a3 + 424))(*a3, &v80);
  if ( v28 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v28, v29, v30, v31);
  v79 = 0;
  v32 = (*(__int64 (__fastcall **)(__int64 *, int *))(**a3 + 376))(*a3, &v79);
  if ( v32 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v32, v33, v34, v35);
  v75 = 0;
  v36 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(**a3 + 440))(*a3, &v75);
  if ( v36 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v36, v37, v38, v39);
  v78 = 0;
  if ( xpsrdr::D2D1MapLineJoin((xpsrdr *)v75, v37) == D2D1_LINE_JOIN_MITER )
  {
    v40 = (*(__int64 (__fastcall **)(__int64 *, int *))(**a3 + 456))(*a3, &v78);
    if ( v40 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v40, v41, v42, v43);
  }
  v76 = 0.0;
  v44 = (*(__int64 (__fastcall **)(__int64 *, float *))(**a3 + 392))(*a3, &v76);
  if ( v44 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v44, v45, v46, v47);
  v77 = 0.0;
  v48 = (*(__int64 (__fastcall **)(__int64 *, float *))(**a3 + 472))(*a3, &v77);
  if ( v48 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v48, v49, v50, v51);
  v52 = 0;
  v53 = v76;
  v54 = COERCE_FLOAT(LODWORD(v16) ^ _xmm) > v76;
  v55 = *(__m64 **)(*(_QWORD *)(a2 + 496)
                  + 8 * ((*(_QWORD *)(a2 + 504) - 1LL) & (*(_QWORD *)(a2 + 520) - 1LL + *(_QWORD *)(a2 + 512))));
  v83 = _mm_cvtps_pd((__m64)v55->m64_u64);
  v84 = _mm_cvtps_pd(v55[1]);
  v56 = (float *)xpsrdr::ScaleCalculator::operator()((xpsrdr::ScaleCalculator *)&v83);
  if ( v54 && (float)*(int *)(a2 + 532) > (float)(v77 * *v56) )
  {
    LOBYTE(v52) = *(_DWORD *)(a2 + 532) <= 1;
    ++v52;
  }
  *a1 = 0;
  a1[1] = 0;
  v82 = 1;
  v58 = (_DWORD)v73 != 0 ? 5 : 0;
  v59 = v78;
  v62 = xpsrdr::D2D1MapLineJoin((xpsrdr *)v75, v57);
  if ( v79 == 1 )
  {
    i = 0;
  }
  else if ( v79 == 2 )
  {
    i = 2;
  }
  else if ( v79 != 3 )
  {
    if ( v79 != 4 )
      xpsrdr::ThrowLogicException((xpsrdr *)(unsigned int)(v79 - 3), v60, v61);
    i = 3;
  }
  v63 = xpsrdr::D2D1MapLineCap((xpsrdr *)v80, (enum __MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0005)v60);
  v87[0] = xpsrdr::D2D1MapLineCap((xpsrdr *)v81, v64);
  v87[1] = v63;
  v87[2] = i;
  v87[3] = v62;
  v87[4] = v59;
  v87[5] = v58;
  *(float *)&v87[6] = v53;
  v87[7] = v52;
  LODWORD(v74) = 0;
  v65 = *(_QWORD *)(a2 + 16);
  v66 = *(__int64 (__fastcall **)(__int64, _DWORD *, __int64, _QWORD, __m128d *))(*(_QWORD *)v65 + 144LL);
  v83.m128d_f64[0] = 0.0;
  *(_QWORD *)&v83.m128d_f64[1] = &v74;
  *(_QWORD *)&v84.m128d_f64[0] = a1;
  v67 = 0;
  if ( v58 == 5 )
    v67 = v86[0];
  v68 = v66(v65, v87, v67, (unsigned int)(2 * v73), &v83);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v83);
  if ( (int)v74 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v74, v69, v70, v71);
  if ( v68 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v68, v69, v70, v71);
  std::vector<tagRGBQUAD>::_Tidy(v86);
  if ( v85[1] )
    std::_Ref_count_base::_Decref(v85[1]);
  return a1;
}

```

## disassembly

```asm
0x18003f5ec  mov     rax, rsp
0x18003f5ef  mov     [rax+20h], rbx
0x18003f5f3  push    rbp
0x18003f5f4  push    rsi
0x18003f5f5  push    rdi
0x18003f5f6  push    r12
0x18003f5f8  push    r13
0x18003f5fa  push    r14
0x18003f5fc  push    r15
0x18003f5fe  lea     rbp, [rax-5Fh]
0x18003f602  sub     rsp, 100h
0x18003f609  movaps  xmmword ptr [rax-48h], xmm6
0x18003f60d  movaps  xmmword ptr [rax-58h], xmm7
0x18003f611  mov     rax, cs:__security_cookie
0x18003f618  xor     rax, rsp
0x18003f61b  mov     [rbp+57h+var_60], rax
0x18003f61f  mov     rbx, r8
0x18003f622  mov     r13, rdx
0x18003f625  mov     r14, rcx
0x18003f628  mov     [rbp+57h+var_88], rcx
0x18003f62c  xor     r15d, r15d
0x18003f62f  mov     [rbp+57h+var_D4], r15d
0x18003f633  xorps   xmm0, xmm0
0x18003f636  movdqu  xmmword ptr [rbp+57h+var_B0], xmm0
0x18003f63b  mov     dword ptr [rsp+130h+var_F8], r15d
0x18003f640  mov     rcx, [r8]
0x18003f643  mov     rax, [rcx]
0x18003f646  mov     qword ptr [rbp+57h+var_D0], r15
0x18003f64a  lea     rdx, [rsp+130h+var_F8]
0x18003f64f  mov     qword ptr [rbp+57h+var_D0+8], rdx
0x18003f653  lea     rdx, [rbp+57h+var_B0]
0x18003f657  mov     qword ptr [rbp+57h+var_C0], rdx
0x18003f65b  lea     rdx, [rbp+57h+var_D0]
0x18003f65f  mov     rax, [rax+170h]
0x18003f666  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f66b  mov     edi, eax
0x18003f66d  lea     rcx, [rbp+57h+var_D0]
0x18003f671  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18003f676  mov     ecx, dword ptr [rsp+130h+var_F8]; this
0x18003f67a  test    ecx, ecx
0x18003f67c  js      loc_18003FA0F
0x18003f682  test    edi, edi
0x18003f684  js      loc_18003FA15
0x18003f68a  mov     dword ptr [rsp+130h+var_100], r15d
0x18003f68f  mov     rcx, [rbp+57h+var_B0]
0x18003f693  mov     rax, [rcx]
0x18003f696  lea     rdx, [rsp+130h+var_100]
0x18003f69b  mov     rax, [rax+18h]
0x18003f69f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f6a4  test    eax, eax
0x18003f6a6  js      loc_18003FA1D
0x18003f6ac  mov     eax, dword ptr [rsp+130h+var_100]
0x18003f6b0  lea     edx, [rax+rax]
0x18003f6b3  lea     rcx, [rbp+57h+var_A0]
0x18003f6b7  call    ??0?$vector@MV?$allocator@M@std@@@std@@QEAA@_KAEBV?$allocator@M@1@@Z; std::vector<float>::vector<float>(unsigned __int64,std::allocator<float> const &)
0x18003f6bc  nop
0x18003f6bd  xorps   xmm6, xmm6
0x18003f6c0  mov     esi, r15d
0x18003f6c3  lea     edi, [r15+1]
0x18003f6c7  cmp     dword ptr [rsp+130h+var_100], r15d
0x18003f6cc  jbe     short loc_18003F72D
0x18003f6ce  xor     eax, eax
0x18003f6d0  mov     [rsp+130h+var_F8], rax
0x18003f6d5  mov     rcx, [rbp+57h+var_B0]
0x18003f6d9  mov     rax, [rcx]
0x18003f6dc  mov     edx, esi
0x18003f6de  lea     r8, [rsp+130h+var_F8]
0x18003f6e3  mov     rax, [rax+20h]
0x18003f6e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f6ec  test    eax, eax
0x18003f6ee  js      loc_18003FA2D
0x18003f6f4  movss   xmm1, dword ptr [rsp+130h+var_F8]
0x18003f6fa  movaps  xmm0, xmm1
0x18003f6fd  addss   xmm0, xmm6
0x18003f701  movaps  xmm6, xmm0
0x18003f704  mov     rax, [rbp+57h+var_A0]
0x18003f708  movss   dword ptr [rax+rsi*8], xmm1
0x18003f70d  movss   xmm0, dword ptr [rsp+130h+var_F8+4]
0x18003f713  addss   xmm6, xmm0
0x18003f717  mov     rax, [rbp+57h+var_A0]
0x18003f71b  movss   dword ptr [rax+rsi*8+4], xmm0
0x18003f721  add     rsi, rdi
0x18003f724  mov     eax, dword ptr [rsp+130h+var_100]
0x18003f728  cmp     rsi, rax
0x18003f72b  jb      short loc_18003F6CE
0x18003f72d  mov     dword ptr [rsp+130h+var_DC+4], r15d
0x18003f732  mov     rcx, [rbx]
0x18003f735  mov     rax, [rcx]
0x18003f738  lea     rdx, [rsp+130h+var_DC+4]
0x18003f73d  mov     rax, [rax+198h]
0x18003f744  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f749  test    eax, eax
0x18003f74b  js      loc_18003FA25
0x18003f751  mov     dword ptr [rsp+130h+var_DC], r15d
0x18003f756  mov     rcx, [rbx]
0x18003f759  mov     rax, [rcx]
0x18003f75c  lea     rdx, [rsp+130h+var_DC]
0x18003f761  mov     rax, [rax+1A8h]
0x18003f768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f76d  test    eax, eax
0x18003f76f  js      loc_18003FA35
0x18003f775  mov     [rsp+130h+var_E0], r15d
0x18003f77a  mov     rcx, [rbx]
0x18003f77d  mov     rax, [rcx]
0x18003f780  lea     rdx, [rsp+130h+var_E0]
0x18003f785  mov     rax, [rax+178h]
0x18003f78c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f791  test    eax, eax
0x18003f793  js      loc_18003FA3D
0x18003f799  mov     dword ptr [rsp+130h+var_F0], r15d
0x18003f79e  mov     rcx, [rbx]
0x18003f7a1  mov     rax, [rcx]
0x18003f7a4  lea     rdx, [rsp+130h+var_F0]
0x18003f7a9  mov     rax, [rax+1B8h]
0x18003f7b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f7b5  test    eax, eax
0x18003f7b7  js      loc_18003FA45
0x18003f7bd  mov     [rsp+130h+var_E4], 0
0x18003f7c5  mov     ecx, dword ptr [rsp+130h+var_F0]; this
0x18003f7c9  call    ?D2D1MapLineJoin@xpsrdr@@YA?AW4D2D1_LINE_JOIN@@W4__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0007@@@Z; xpsrdr::D2D1MapLineJoin(__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0007)
0x18003f7ce  test    eax, eax
0x18003f7d0  jnz     short loc_18003F7F1
0x18003f7d2  mov     rcx, [rbx]
0x18003f7d5  mov     rax, [rcx]
0x18003f7d8  lea     rdx, [rsp+130h+var_E4]
0x18003f7dd  mov     rax, [rax+1C8h]
0x18003f7e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f7e9  test    eax, eax
0x18003f7eb  js      loc_18003FA4D
0x18003f7f1  mov     dword ptr [rsp+130h+var_F0+4], 0
0x18003f7f9  mov     rcx, [rbx]
0x18003f7fc  mov     rax, [rcx]
0x18003f7ff  lea     rdx, [rsp+130h+var_F0+4]
0x18003f804  mov     rax, [rax+188h]
0x18003f80b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f810  test    eax, eax
0x18003f812  js      loc_18003FA55
0x18003f818  mov     [rsp+130h+var_E8], 0
0x18003f820  mov     rcx, [rbx]
0x18003f823  mov     rax, [rcx]
0x18003f826  lea     rdx, [rsp+130h+var_E8]
0x18003f82b  mov     rax, [rax+1D8h]
0x18003f832  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f837  test    eax, eax
0x18003f839  js      loc_18003FA5D
0x18003f83f  mov     esi, r15d
0x18003f842  xorps   xmm6, cs:__xmm@80000000800000008000000080000000
0x18003f849  movss   xmm7, dword ptr [rsp+130h+var_F0+4]
0x18003f84f  comiss  xmm6, xmm7
0x18003f852  setnbe  bl
0x18003f855  mov     rcx, [r13+208h]
0x18003f85c  mov     rdx, [r13+200h]
0x18003f863  dec     rcx
0x18003f866  add     rdx, rcx
0x18003f869  mov     rax, [r13+1F8h]
0x18003f870  sub     rax, rdi
0x18003f873  and     rdx, rax
0x18003f876  mov     rax, [r13+1F0h]
0x18003f87d  mov     rcx, [rax+rdx*8]
0x18003f881  cvtps2pd xmm0, qword ptr [rcx]
0x18003f884  movups  [rbp+57h+var_D0], xmm0
0x18003f888  cvtps2pd xmm0, qword ptr [rcx+8]
0x18003f88c  movups  [rbp+57h+var_C0], xmm0
0x18003f890  lea     rdx, [rsp+130h+var_F8]
0x18003f895  lea     rcx, [rbp+57h+var_D0]; this
0x18003f899  call    ??RScaleCalculator@xpsrdr@@QEBA?AUMinMaxScaling@1@XZ; xpsrdr::ScaleCalculator::operator()(void)
0x18003f89e  test    bl, bl
0x18003f8a0  jz      short loc_18003F8C7
0x18003f8a2  mov     ecx, [r13+214h]
0x18003f8a9  movss   xmm1, [rsp+130h+var_E8]
0x18003f8af  mulss   xmm1, dword ptr [rax]
0x18003f8b3  movd    xmm0, ecx
0x18003f8b7  cvtdq2ps xmm0, xmm0
0x18003f8ba  comiss  xmm0, xmm1
0x18003f8bd  jbe     short loc_18003F8C7
0x18003f8bf  cmp     ecx, edi
0x18003f8c1  setle   sil
0x18003f8c5  add     esi, edi
0x18003f8c7  mov     [r14], r15
0x18003f8ca  mov     [r14+8], r15
0x18003f8ce  mov     [rbp+57h+var_D4], edi
0x18003f8d1  mov     eax, dword ptr [rsp+130h+var_100]
0x18003f8d5  neg     eax
0x18003f8d7  sbb     r15d, r15d
0x18003f8da  and     r15d, 5
0x18003f8de  movss   xmm6, [rsp+130h+var_E4]
0x18003f8e4  mov     ecx, dword ptr [rsp+130h+var_F0]; this
0x18003f8e8  call    ?D2D1MapLineJoin@xpsrdr@@YA?AW4D2D1_LINE_JOIN@@W4__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0007@@@Z; xpsrdr::D2D1MapLineJoin(__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0007)
0x18003f8ed  mov     r12d, eax
0x18003f8f0  mov     ecx, [rsp+130h+var_E0]
0x18003f8f4  sub     ecx, 1
0x18003f8f7  jz      short loc_18003F918
0x18003f8f9  sub     ecx, 1
0x18003f8fc  jz      short loc_18003F911
0x18003f8fe  sub     ecx, 1; this
0x18003f901  jz      short loc_18003F91A
0x18003f903  cmp     ecx, 1
0x18003f906  jnz     loc_18003FA65
0x18003f90c  lea     edi, [rcx+2]
0x18003f90f  jmp     short loc_18003F91A
0x18003f911  mov     edi, 2
0x18003f916  jmp     short loc_18003F91A
0x18003f918  xor     edi, edi
0x18003f91a  mov     ecx, dword ptr [rsp+130h+var_DC]; this
0x18003f91e  call    ?D2D1MapLineCap@xpsrdr@@YA?AW4D2D1_CAP_STYLE@@W4__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0005@@@Z; xpsrdr::D2D1MapLineCap(__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0005)
0x18003f923  mov     ebx, eax
0x18003f925  mov     ecx, dword ptr [rsp+130h+var_DC+4]; this
0x18003f929  call    ?D2D1MapLineCap@xpsrdr@@YA?AW4D2D1_CAP_STYLE@@W4__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0005@@@Z; xpsrdr::D2D1MapLineCap(__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0005)
0x18003f92e  mov     [rbp+57h+var_80], eax
0x18003f931  mov     [rbp+57h+var_7C], ebx
0x18003f934  mov     [rbp+57h+var_78], edi
0x18003f937  mov     [rbp+57h+var_74], r12d
0x18003f93b  movss   [rbp+57h+var_70], xmm6
0x18003f940  mov     [rbp+57h+var_6C], r15d
0x18003f944  movss   [rbp+57h+var_68], xmm7
0x18003f949  mov     [rbp+57h+var_64], esi
0x18003f94c  mov     dword ptr [rsp+130h+var_F8], 0
0x18003f954  mov     rcx, [r13+10h]
0x18003f958  mov     rax, [rcx]
0x18003f95b  mov     r10, [rax+90h]
0x18003f962  mov     qword ptr [rbp+57h+var_D0], 0
0x18003f96a  lea     rax, [rsp+130h+var_F8]
0x18003f96f  mov     qword ptr [rbp+57h+var_D0+8], rax
0x18003f973  mov     qword ptr [rbp+57h+var_C0], r14
0x18003f977  mov     eax, dword ptr [rsp+130h+var_100]
0x18003f97b  lea     r9d, [rax+rax]
0x18003f97f  xor     r8d, r8d
0x18003f982  cmp     r15d, 5
0x18003f986  cmovz   r8, [rbp+57h+var_A0]
0x18003f98b  lea     rax, [rbp+57h+var_D0]
0x18003f98f  mov     [rsp+130h+var_110], rax
0x18003f994  lea     rdx, [rbp+57h+var_80]
0x18003f998  mov     rax, r10
0x18003f99b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f9a0  mov     ebx, eax
0x18003f9a2  lea     rcx, [rbp+57h+var_D0]
0x18003f9a6  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18003f9ab  mov     ecx, dword ptr [rsp+130h+var_F8]; this
0x18003f9af  test    ecx, ecx
0x18003f9b1  js      loc_18003FA6B
0x18003f9b7  test    ebx, ebx
0x18003f9b9  js      short loc_18003FA07
0x18003f9bb  lea     rcx, [rbp+57h+var_A0]
0x18003f9bf  call    ?_Tidy@?$vector@UtagRGBQUAD@@V?$allocator@UtagRGBQUAD@@@std@@@std@@AEAAXXZ; std::vector<tagRGBQUAD>::_Tidy(void)
0x18003f9c4  nop
0x18003f9c5  mov     rcx, [rbp+57h+var_B0+8]; this
0x18003f9c9  test    rcx, rcx
0x18003f9cc  jz      short loc_18003F9D3
0x18003f9ce  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003f9d3  mov     rax, r14
0x18003f9d6  mov     rcx, [rbp+57h+var_60]
0x18003f9da  xor     rcx, rsp; StackCookie
0x18003f9dd  call    __security_check_cookie
0x18003f9e2  lea     r11, [rsp+130h+var_30]
0x18003f9ea  mov     rbx, [r11+58h]
0x18003f9ee  movaps  xmm6, xmmword ptr [r11-10h]
0x18003f9f3  movaps  xmm7, xmmword ptr [r11-20h]
0x18003f9f8  mov     rsp, r11
0x18003f9fb  pop     r15
0x18003f9fd  pop     r14
0x18003f9ff  pop     r13
0x18003fa01  pop     r12
0x18003fa03  pop     rdi
0x18003fa04  pop     rsi
0x18003fa05  pop     rbp
0x18003fa06  retn
0x18003fa07  mov     ecx, ebx; this
0x18003fa09  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003fa0f  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003fa15  mov     ecx, edi; this
0x18003fa17  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003fa1d  mov     ecx, eax; this
0x18003fa1f  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003fa25  mov     ecx, eax; this
0x18003fa27  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003fa2d  mov     ecx, eax; this
0x18003fa2f  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003fa35  mov     ecx, eax; this
0x18003fa37  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003fa3d  mov     ecx, eax; this
0x18003fa3f  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003fa45  mov     ecx, eax; this
0x18003fa47  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003fa4d  mov     ecx, eax; this
0x18003fa4f  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003fa55  mov     ecx, eax; this
0x18003fa57  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003fa5d  mov     ecx, eax; this
0x18003fa5f  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003fa65  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
0x18003fa6b  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
```
