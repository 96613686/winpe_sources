# GpGraphics::InheritAppClippingAndTransform(HDC__ *)

- ea: `0x1800427c0`
- end: `0x180042bc9`
- name: `?InheritAppClippingAndTransform@GpGraphics@@IEAA?AW4Status@@PEAUHDC__@@@Z`
- size: `1033`
- prototype: `enum Status __high(HDC)`
- caller_count: `4`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180006e54`
- `0x180007120`
- `0x180007a18`
- `0x180042348`

## callees

- `0x1800067bc`
- `0x18001ec80`
- `0x18001ffcc`
- `0x1800202a0`
- `0x1800427c0`
- `0x1800439bc`
- `0x180044a70`
- `0x180046f9c`
- `0x18005b2a0`
- `0x18005dc40`
- `0x1800c8304`
- `0x1800fe680`
- `0x180169010`

## import_xrefs

- `GDI32!DeleteObject` at `0x180042bbe`
- `GDI32!DeleteObject` at `0x180042bbe`
- `GDI32!GetViewportOrgEx` at `0x1800429fd`
- `GDI32!GetViewportOrgEx` at `0x1800429fd`
- `GDI32!GetRegionData` at `0x180042961`
- `GDI32!GetRegionData` at `0x180042b2a`
- `GDI32!GetRegionData` at `0x180042b63`
- `GDI32!GetRegionData` at `0x180042961`
- `GDI32!GetRegionData` at `0x180042b2a`
- `GDI32!GetRegionData` at `0x180042b63`
- `GDI32!ScaleRgn` at `0x180042ba4`
- `GDI32!ScaleRgn` at `0x180042ba4`
- `GDI32!GetRandomRgn` at `0x18004292d`
- `GDI32!GetRandomRgn` at `0x18004292d`
- `GDI32!LPtoDP` at `0x180042834`
- `GDI32!LPtoDP` at `0x180042834`

## pseudocode

```c
__int64 __fastcall GpGraphics::InheritAppClippingAndTransform(__int64 a1, HDC a2)
{
  PointF *v3; // rdi
  __int64 v5; // rsi
  LONG y; // edx
  __int64 v7; // rcx
  float x; // xmm0_4
  float v9; // xmm4_4
  int v10; // eax
  float v11; // xmm4_4
  float v12; // xmm5_4
  float v13; // xmm2_4
  float v14; // xmm1_4
  int v15; // eax
  __int64 v16; // rcx
  HRGN CachedGdiRegion; // rax
  HRGN v18; // rdi
  unsigned int v19; // r14d
  signed int RegionData; // eax
  _RGNDATA *p_RgnData; // rsi
  __int64 v22; // rcx
  LONG v23; // esi
  LONG v24; // r15d
  __int64 result; // rax
  __int64 v26; // rcx
  signed int v27; // eax
  DWORD v28; // r14d
  struct _RGNDATA *v29; // rax
  __int64 v30; // rax
  struct tagPOINT point; // [rsp+20h] [rbp-E0h] BYREF
  __m128i si128; // [rsp+28h] [rbp-D8h] BYREF
  struct tagPOINT pt[2]; // [rsp+38h] [rbp-C8h] BYREF
  int v34; // [rsp+48h] [rbp-B8h]
  int v35; // [rsp+4Ch] [rbp-B4h]
  float v36[8]; // [rsp+50h] [rbp-B0h] BYREF
  _RGNDATA RgnData; // [rsp+70h] [rbp-90h] BYREF

  v3 = (PointF *)v36;
  v5 = 3;
  do
  {
    PointF::PointF(v3);
    v3 = (PointF *)((char *)v3 + 8);
    --v5;
  }
  while ( v5 );
  v34 = 0;
  v35 = 0x2000;
  *(__m128i *)&pt[0].x = _mm_load_si128((const __m128i *)&_xmm);
  if ( !LPtoDP(a2, pt, 3) )
    return 1;
  y = pt[0].y;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  if ( pt[0].x == v34 && pt[0].y == pt[1].y )
  {
    v7 = *(_QWORD *)(a1 + 136) + 192LL;
    x = (float)pt[0].x;
    v9 = (float)(pt[1].x - pt[0].x);
    v10 = v35 - pt[0].y;
    *(_QWORD *)(v7 + 20) = 0;
    v11 = v9 + x;
    v12 = (float)v10 + (float)y;
    v13 = (float)(v11 - x) * 0.00012207031;
    *(float *)(v7 + 16) = v13;
    v14 = (float)(v12 - (float)y) * 0.00012207031;
    *(float *)(v7 + 28) = v14;
    *(float *)(v7 + 32) = v11 - (float)(v13 * 8192.0);
    *(float *)(v7 + 36) = v12 - (float)(v14 * 8192.0);
    v15 = GpMatrix::ComputeComplexity((GpMatrix *)v7);
    *(_DWORD *)(v16 + 40) = v15;
  }
  else
  {
    v26 = *(_QWORD *)(a1 + 136) + 192LL;
    v36[0] = (float)pt[0].x;
    v36[1] = (float)pt[0].y;
    v36[2] = (float)pt[1].x;
    v36[3] = (float)pt[1].y;
    v36[4] = (float)v34;
    v36[5] = (float)v35;
    result = GpMatrix::InferAffineMatrix(v26, v36, &si128);
    if ( (_DWORD)result )
      return result;
  }
  DpContext::UpdateWorldToDeviceMatrix(*(DpContext **)(a1 + 136));
  CachedGdiRegion = GetCachedGdiRegion();
  v18 = CachedGdiRegion;
  if ( !CachedGdiRegion )
    return 3;
  v19 = 0;
  if ( GetRandomRgn(a2, CachedGdiRegion, 1) != 1 )
    goto LABEL_16;
  if ( *(int *)(*(_QWORD *)(a1 + 136) + 776LL) <= 1 || (unsigned int)ScaleRgn(a2, v18) )
  {
    RegionData = GetRegionData(v18, 0x400u, &RgnData);
    p_RgnData = &RgnData;
    if ( RegionData >= 1 && (unsigned int)RegionData <= 0x400 )
      goto LABEL_12;
    v27 = GetRegionData(v18, 0, 0);
    v28 = v27;
    if ( v27 <= 1 )
      goto LABEL_12;
    v29 = (struct _RGNDATA *)GpMallocEx(v27, 0);
    p_RgnData = v29;
    if ( v29 )
    {
      v29->rdh.nCount = 0;
      GetRegionData(v18, v28, v29);
LABEL_12:
      if ( (unsigned int)DpRegion::Set(*(_QWORD *)(a1 + 136) + 408LL, p_RgnData->Buffer, p_RgnData->rdh.nCount)
        || (unsigned int)DpRegion::And(*(_QWORD *)(a1 + 136) + 408LL, a1 + 928) )
      {
        DpRegion::Set(*(_QWORD *)(a1 + 136) + 408LL, a1 + 928, 0);
      }
      v19 = DpRegion::And(*(_QWORD *)(a1 + 136) + 304LL, *(_QWORD *)(a1 + 136) + 408LL);
      if ( p_RgnData != &RgnData )
        GpFree(p_RgnData);
      goto LABEL_16;
    }
    return 3;
  }
  v19 = 1;
LABEL_16:
  point = 0;
  GetViewportOrgEx(a2, &point);
  v22 = *(_QWORD *)(a1 + 56);
  v23 = point.y;
  v24 = point.x;
  if ( v22 )
  {
    v30 = *(_QWORD *)(a1 + 136);
    if ( point.x != *(_DWORD *)(v30 + 36) || point.y != *(_DWORD *)(v30 + 40) )
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v22 + 384LL))(
        v22,
        (unsigned int)point.x,
        (unsigned int)point.y);
  }
  *(_DWORD *)(*(_QWORD *)(a1 + 136) + 36LL) = v24;
  *(_DWORD *)(*(_QWORD *)(a1 + 136) + 40LL) = v23;
  if ( _InterlockedCompareExchange64((volatile signed __int64 *)&Globals::CachedGdiRegion, (signed __int64)v18, 0) )
    DeleteObject(v18);
  return v19;
}

```

## disassembly

```asm
0x1800427c0  mov     [rsp-8+arg_10], rbx
0x1800427c5  push    rbp
0x1800427c6  push    rsi
0x1800427c7  push    rdi
0x1800427c8  push    r14
0x1800427ca  push    r15
0x1800427cc  lea     rbp, [rsp-380h]
0x1800427d4  sub     rsp, 480h
0x1800427db  mov     rax, cs:__security_cookie
0x1800427e2  xor     rax, rsp
0x1800427e5  mov     [rbp+3A0h+var_30], rax
0x1800427ec  mov     r15, rdx
0x1800427ef  lea     rdi, [rsp+4A0h+var_450]
0x1800427f4  mov     rbx, rcx
0x1800427f7  mov     esi, 3
0x1800427fc  mov     rcx, rdi; this
0x1800427ff  call    ??0PointF@@QEAA@XZ; PointF::PointF(void)
0x180042804  add     rdi, 8
0x180042808  sub     rsi, 1
0x18004280c  jnz     short loc_1800427FC
0x18004280e  movdqa  xmm0, cs:__xmm@00000000000020000000000000000000
0x180042816  lea     r8d, [rsi+3]; c
0x18004281a  lea     rdx, [rsp+4A0h+pt]; lppt
0x18004281f  mov     [rsp+4A0h+var_458], esi
0x180042823  mov     rcx, r15; hdc
0x180042826  mov     [rsp+4A0h+var_454], 2000h
0x18004282e  movdqu  xmmword ptr [rsp+4A0h+pt.x], xmm0
0x180042834  call    cs:__imp_LPtoDP
0x18004283a  test    eax, eax
0x18004283c  jz      loc_180042A68
0x180042842  movdqa  xmm0, cs:__xmm@46000000460000000000000000000000
0x18004284a  mov     r8d, [rsp+4A0h+pt.x]
0x18004284f  mov     edx, [rsp+4A0h+pt.y]
0x180042853  movups  [rsp+4A0h+var_478], xmm0
0x180042858  cmp     r8d, [rsp+4A0h+var_458]
0x18004285d  jnz     loc_180042AA1
0x180042863  cmp     edx, [rsp+4A0h+pt.y+8]
0x180042867  jnz     loc_180042AA1
0x18004286d  mov     eax, [rsp+4A0h+pt.x+8]
0x180042871  mov     rcx, [rbx+88h]
0x180042878  sub     eax, r8d
0x18004287b  add     rcx, 0C0h; this
0x180042882  movd    xmm0, r8d
0x180042887  cvtdq2ps xmm0, xmm0
0x18004288a  movd    xmm4, eax
0x18004288e  mov     eax, [rsp+4A0h+var_454]
0x180042892  cvtdq2ps xmm4, xmm4
0x180042895  sub     eax, edx
0x180042897  mov     [rcx+14h], rsi
0x18004289b  movd    xmm3, edx
0x18004289f  cvtdq2ps xmm3, xmm3
0x1800428a2  addss   xmm4, xmm0
0x1800428a6  movd    xmm5, eax
0x1800428aa  cvtdq2ps xmm5, xmm5
0x1800428ad  movaps  xmm2, xmm4
0x1800428b0  addss   xmm5, xmm3
0x1800428b4  subss   xmm2, xmm0
0x1800428b8  movaps  xmm1, xmm5
0x1800428bb  mulss   xmm2, cs:__real@39000000
0x1800428c3  subss   xmm1, xmm3
0x1800428c7  movss   dword ptr [rcx+10h], xmm2
0x1800428cc  mulss   xmm1, cs:__real@39000000
0x1800428d4  mulss   xmm2, cs:__real@46000000
0x1800428dc  movss   dword ptr [rcx+1Ch], xmm1
0x1800428e1  mulss   xmm1, cs:__real@46000000
0x1800428e9  subss   xmm4, xmm2
0x1800428ed  subss   xmm5, xmm1
0x1800428f1  movss   dword ptr [rcx+20h], xmm4
0x1800428f6  movss   dword ptr [rcx+24h], xmm5
0x1800428fb  call    ?ComputeComplexity@GpMatrix@@IEBAHXZ; GpMatrix::ComputeComplexity(void)
0x180042900  mov     [rcx+28h], eax
0x180042903  mov     rcx, [rbx+88h]; this
0x18004290a  call    ?UpdateWorldToDeviceMatrix@DpContext@@QEAAXXZ; DpContext::UpdateWorldToDeviceMatrix(void)
0x18004290f  call    ?GetCachedGdiRegion@@YAPEAUHRGN__@@XZ; GetCachedGdiRegion(void)
0x180042914  mov     rdi, rax
0x180042917  test    rax, rax
0x18004291a  jz      loc_180042A9A
0x180042920  xor     r14d, r14d
0x180042923  mov     rdx, rax; hrgn
0x180042926  mov     rcx, r15; hdc
0x180042929  lea     r8d, [r14+1]; i
0x18004292d  call    cs:__imp_GetRandomRgn
0x180042933  cmp     eax, 1
0x180042936  jnz     loc_1800429EC
0x18004293c  mov     rax, [rbx+88h]
0x180042943  cmp     dword ptr [rax+308h], 1
0x18004294a  jg      loc_180042B9E
0x180042950  mov     r14d, 400h
0x180042956  lea     r8, [rsp+4A0h+RgnData]; lpRgnData
0x18004295b  mov     edx, r14d; nCount
0x18004295e  mov     rcx, rdi; hrgn
0x180042961  call    cs:__imp_GetRegionData
0x180042967  lea     rsi, [rsp+4A0h+RgnData]
0x18004296c  cmp     eax, 1
0x18004296f  jl      loc_180042B22
0x180042975  cmp     eax, r14d
0x180042978  ja      loc_180042B22
0x18004297e  mov     rcx, [rbx+88h]
0x180042985  lea     rdx, [rsi+20h]
0x180042989  mov     r8d, [rsi+8]
0x18004298d  mov     r14d, 198h
0x180042993  add     rcx, r14
0x180042996  call    ?Set@DpRegion@@QEAA?AW4Status@@PEBUtagRECT@@H@Z; DpRegion::Set(tagRECT const *,int)
0x18004299b  test    eax, eax
0x18004299d  jnz     loc_180042A7C
0x1800429a3  mov     rcx, [rbx+88h]
0x1800429aa  lea     rdx, [rbx+3A0h]
0x1800429b1  add     rcx, r14
0x1800429b4  call    ?And@DpRegion@@QEAA?AW4Status@@PEBV1@@Z; DpRegion::And(DpRegion const *)
0x1800429b9  test    eax, eax
0x1800429bb  jnz     loc_180042A7C
0x1800429c1  mov     rcx, [rbx+88h]
0x1800429c8  lea     rdx, [rcx+198h]
0x1800429cf  add     rcx, 130h
0x1800429d6  call    ?And@DpRegion@@QEAA?AW4Status@@PEBV1@@Z; DpRegion::And(DpRegion const *)
0x1800429db  mov     r14d, eax
0x1800429de  lea     rax, [rsp+4A0h+RgnData]
0x1800429e3  cmp     rsi, rax
0x1800429e6  jnz     loc_180042A6F
0x1800429ec  lea     rdx, [rsp+4A0h+point]; lppoint
0x1800429f1  mov     qword ptr [rsp+4A0h+point.x], 0
0x1800429fa  mov     rcx, r15; hdc
0x1800429fd  call    cs:__imp_GetViewportOrgEx
0x180042a03  mov     rcx, [rbx+38h]
0x180042a07  mov     esi, [rsp+4A0h+point.y]
0x180042a0b  mov     r15d, [rsp+4A0h+point.x]
0x180042a10  test    rcx, rcx
0x180042a13  jnz     loc_180042B6E
0x180042a19  mov     rax, [rbx+88h]
0x180042a20  mov     [rax+24h], r15d
0x180042a24  mov     rax, [rbx+88h]
0x180042a2b  mov     [rax+28h], esi
0x180042a2e  xor     eax, eax
0x180042a30  lock cmpxchg cs:?CachedGdiRegion@Globals@@3PEAUHRGN__@@EA, rdi; HRGN__ * Globals::CachedGdiRegion
0x180042a39  jnz     loc_180042BBB
0x180042a3f  mov     eax, r14d
0x180042a42  mov     rcx, [rbp+3A0h+var_30]
0x180042a49  xor     rcx, rsp; StackCookie
0x180042a4c  call    __security_check_cookie
0x180042a51  mov     rbx, [rsp+4A0h+arg_10]
0x180042a59  add     rsp, 480h
0x180042a60  pop     r15
0x180042a62  pop     r14
0x180042a64  pop     rdi
0x180042a65  pop     rsi
0x180042a66  pop     rbp
0x180042a67  retn
0x180042a68  mov     eax, 1
0x180042a6d  jmp     short loc_180042A42
0x180042a6f  mov     rcx, rsi
0x180042a72  call    GpFree
0x180042a77  jmp     loc_1800429EC
0x180042a7c  mov     rcx, [rbx+88h]
0x180042a83  lea     rdx, [rbx+3A0h]
0x180042a8a  add     rcx, r14
0x180042a8d  xor     r8d, r8d
0x180042a90  call    ?Set@DpRegion@@QEAA?AW4Status@@PEBV1@H@Z; DpRegion::Set(DpRegion const *,int)
0x180042a95  jmp     loc_1800429C1
0x180042a9a  mov     eax, 3
0x180042a9f  jmp     short loc_180042A42
0x180042aa1  mov     rcx, [rbx+88h]
0x180042aa8  movd    xmm0, r8d
0x180042aad  add     rcx, 0C0h
0x180042ab4  cvtdq2ps xmm0, xmm0
0x180042ab7  lea     r8, [rsp+4A0h+var_478]
0x180042abc  movd    xmm1, edx
0x180042ac0  lea     rdx, [rsp+4A0h+var_450]
0x180042ac5  cvtdq2ps xmm1, xmm1
0x180042ac8  movss   [rsp+4A0h+var_450], xmm0
0x180042ace  movd    xmm0, [rsp+4A0h+pt.x+8]
0x180042ad4  movss   [rsp+4A0h+var_44C], xmm1
0x180042ada  movd    xmm1, [rsp+4A0h+pt.y+8]
0x180042ae0  cvtdq2ps xmm0, xmm0
0x180042ae3  cvtdq2ps xmm1, xmm1
0x180042ae6  movss   [rsp+4A0h+var_448], xmm0
0x180042aec  movd    xmm0, [rsp+4A0h+var_458]
0x180042af2  movss   [rsp+4A0h+var_444], xmm1
0x180042af8  movd    xmm1, [rsp+4A0h+var_454]
0x180042afe  cvtdq2ps xmm0, xmm0
0x180042b01  cvtdq2ps xmm1, xmm1
0x180042b04  movss   [rsp+4A0h+var_440], xmm0
0x180042b0a  movss   [rsp+4A0h+var_43C], xmm1
0x180042b10  call    ?InferAffineMatrix@GpMatrix@@QEAA?AW4Status@@PEBVPointF@@AEBVRectF@@@Z; GpMatrix::InferAffineMatrix(PointF const *,RectF const &)
0x180042b15  test    eax, eax
0x180042b17  jnz     loc_180042A42
0x180042b1d  jmp     loc_180042903
0x180042b22  xor     r8d, r8d; lpRgnData
0x180042b25  xor     edx, edx; nCount
0x180042b27  mov     rcx, rdi; hrgn
0x180042b2a  call    cs:__imp_GetRegionData
0x180042b30  movsxd  r14, eax
0x180042b33  cmp     r14d, 1
0x180042b37  jle     loc_18004297E
0x180042b3d  mov     rcx, r14
0x180042b40  xor     edx, edx
0x180042b42  call    GpMallocEx
0x180042b47  mov     rsi, rax
0x180042b4a  test    rax, rax
0x180042b4d  jz      loc_180042A9A
0x180042b53  mov     r8, rax; lpRgnData
0x180042b56  mov     dword ptr [rax+8], 0
0x180042b5d  mov     edx, r14d; nCount
0x180042b60  mov     rcx, rdi; hrgn
0x180042b63  call    cs:__imp_GetRegionData
0x180042b69  jmp     loc_18004297E
0x180042b6e  mov     rax, [rbx+88h]
0x180042b75  cmp     r15d, [rax+24h]
0x180042b79  jnz     short loc_180042B84
0x180042b7b  cmp     esi, [rax+28h]
0x180042b7e  jz      loc_180042A19
0x180042b84  mov     rax, [rcx]
0x180042b87  mov     r8d, esi
0x180042b8a  mov     edx, r15d
0x180042b8d  mov     rax, [rax+180h]
0x180042b94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042b99  jmp     loc_180042A19
0x180042b9e  mov     rdx, rdi
0x180042ba1  mov     rcx, r15
0x180042ba4  call    cs:__imp_ScaleRgn
0x180042baa  test    eax, eax
0x180042bac  jnz     loc_180042950
0x180042bb2  lea     r14d, [rax+1]
0x180042bb6  jmp     loc_1800429EC
0x180042bbb  mov     rcx, rdi; ho
0x180042bbe  call    cs:__imp_DeleteObject
0x180042bc4  jmp     loc_180042A3F
```
