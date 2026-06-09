# CInkRenderer::_InkSpaceToPixelFromPoints(__int64,tagVARIANT *,bool,bool,bool,bool)

- ea: `0x1800b9920`
- end: `0x1800b9cd4`
- name: `?_InkSpaceToPixelFromPoints@CInkRenderer@@QEAAJ_JPEAUtagVARIANT@@_N222@Z`
- size: `948`
- prototype: `int(CInkRenderer *__hidden this, __int64, struct tagVARIANT *, bool, bool, bool, bool)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800b88e0`
- `0x1800b91b0`

## callees

- `0x18000a730`
- `0x1800211c0`
- `0x180026ce8`
- `0x180039098`
- `0x1800b8bc8`
- `0x1800b9920`
- `0x180104f30`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800b999c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800b9c8b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800b9c98`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800b999c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800b9c8b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800b9c98`
- `GDI32!CombineTransform` at `0x1800b9af9`
- `GDI32!CombineTransform` at `0x1800b9b11`
- `GDI32!CombineTransform` at `0x1800b9af9`
- `GDI32!CombineTransform` at `0x1800b9b11`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800b998d`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800b998d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CInkRenderer::_InkSpaceToPixelFromPoints(
        CInkRenderer *this,
        HDC a2,
        XFORM *a3,
        __int64 a4,
        bool a5,
        bool a6,
        bool a7)
{
  HANDLE *v10; // rdi
  signed int v12; // ebx
  unsigned __int8 *v13; // rsi
  DWORD v14; // r14d
  float eM11; // xmm5_4
  float eM21; // xmm6_4
  float v17; // xmm4_4
  FLOAT v18; // xmm2_4
  FLOAT v19; // xmm3_4
  FLOAT v20; // xmm1_4
  int *v21; // rcx
  float v22; // xmm3_4
  float eDy; // xmm2_4
  int v24; // eax
  _DWORD *v25; // rcx
  float v26; // xmm4_4
  int v27; // eax
  __int64 v28; // rcx
  int v29; // edx
  DWORD dwindex; // [rsp+30h] [rbp-108h] BYREF
  unsigned __int8 *v31; // [rsp+38h] [rbp-100h] BYREF
  HANDLE *v32; // [rsp+40h] [rbp-F8h]
  unsigned __int64 v33; // [rsp+48h] [rbp-F0h]
  struct tagXFORM v34; // [rsp+50h] [rbp-E8h] BYREF
  struct _XFORM xfOut; // [rsp+68h] [rbp-D0h] BYREF
  XFORM xf1; // [rsp+80h] [rbp-B8h] BYREF
  XFORM xf2; // [rsp+A0h] [rbp-98h] BYREF
  XFORM v38; // [rsp+B8h] [rbp-80h] BYREF

  v33 = ((unsigned __int64)this + 24) & -(__int64)(this != 0);
  dwindex = 0;
  v10 = (HANDLE *)(v33 + 8);
  CoWaitForMultipleHandles(0, 0xFFFFFFFF, 1u, (LPHANDLE)(v33 + 8), &dwindex);
  if ( !a2 )
    goto LABEL_2;
  v32 = v10;
  if ( a3 )
  {
    xf1 = *a3;
    if ( IsBadIntegerPointArrayType((struct tagVARIANT *)&xf1) )
    {
LABEL_2:
      ReleaseMutex(*v10);
      return 2147942487LL;
    }
    v31 = 0;
    dwindex = 0;
    v12 = AccessVariantData((struct tagVARIANT *)a3, &v31, &dwindex, 0, 0, 0);
    if ( v12 >= 0 )
    {
      try
      {
        v13 = v31;
        if ( (dwindex & 7) != 0 || dwindex && !v31 )
        {
          v12 = -2147024809;
        }
        else
        {
          v14 = dwindex >> 3;
          memset(&xf2, 0, sizeof(xf2));
          memset(&xf1, 0, sizeof(xf1));
          *(__m128i *)&xfOut.eM11 = _mm_load_si128((const __m128i *)&_xmm);
          *(_QWORD *)&xfOut.eDx = 0;
          v12 = (*(__int64 (__fastcall **)(_QWORD, XFORM *))(**((_QWORD **)this + 6) + 216LL))(
                  *((_QWORD *)this + 6),
                  &xf2);
          if ( v12 >= 0 )
            v12 = (*(__int64 (__fastcall **)(_QWORD, XFORM *))(**((_QWORD **)this + 7) + 216LL))(
                    *((_QWORD *)this + 7),
                    &xf1);
          if ( v12 >= 0 )
          {
            v38 = *(XFORM *)GetHiMetricToPixelXForm(&v34, a2);
            CombineTransform(&xfOut, &xf1, &xf2);
            CombineTransform(&xfOut, &xfOut, &v38);
            eM11 = xfOut.eM11;
            eM21 = xfOut.eM21;
            if ( !a7 )
              goto LABEL_19;
            v17 = (float)(xfOut.eM22 * xfOut.eM11) - (float)(xfOut.eM21 * xfOut.eM12);
            if ( v17 >= 0.000000001 || v17 <= -0.000000001 )
            {
              v12 = 0;
              v18 = (float)((float)(xfOut.eDy * xfOut.eM21) - (float)(xfOut.eDx * xfOut.eM22)) / v17;
              v19 = (float)((float)(xfOut.eDx * xfOut.eM12) - (float)(xfOut.eDy * xfOut.eM11)) / v17;
              v20 = xfOut.eM11 / v17;
              eM11 = xfOut.eM22 / v17;
              xfOut.eM11 = xfOut.eM22 / v17;
              xfOut.eM12 = COERCE_FLOAT(LODWORD(xfOut.eM12) ^ _xmm) / v17;
              eM21 = COERCE_FLOAT(LODWORD(xfOut.eM21) ^ _xmm) / v17;
              xfOut.eM21 = eM21;
              xfOut.eM22 = v20;
              xfOut.eDx = v18;
              xfOut.eDy = v19;
            }
            else
            {
              v12 = -2147467259;
            }
            if ( v12 >= 0 )
            {
LABEL_19:
              v21 = (int *)v13;
              if ( v14 )
              {
                while ( 1 )
                {
                  v22 = (float)*v21;
                  eDy = xfOut.eDy;
                  v24 = RoundToNearestLong((float)((float)((float)v21[1] * eM21) + (float)(v22 * eM11)) + xfOut.eDx);
                  *v25 = v24;
                  v27 = RoundToNearestLong((float)((float)(v26 * xfOut.eM22) + (float)(v22 * xfOut.eM12)) + eDy);
                  *(_DWORD *)(v28 + 4) = v27;
                  v21 = (int *)(v28 + 8);
                  if ( v29 + 1 >= v14 )
                    break;
                  eM21 = xfOut.eM21;
                  eM11 = xfOut.eM11;
                }
              }
            }
          }
        }
        UnaccessVariantData((const struct tagVARIANT *)a3, v13);
      }
      catch ( ... )
      {
        dwindex = ReportWispException();
        v12 = dwindex;
        v10 = v32;
      }
    }
    ReleaseMutex(*v10);
    return (unsigned int)v12;
  }
  else
  {
    ReleaseMutex(*v10);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x1800b9920  mov     rax, rsp
0x1800b9923  push    rbx
0x1800b9924  push    rsi
0x1800b9925  push    rdi
0x1800b9926  push    r12
0x1800b9928  push    r13
0x1800b992a  push    r14
0x1800b992c  push    r15
0x1800b992e  sub     rsp, 100h
0x1800b9935  movaps  xmmword ptr [rax-48h], xmm6
0x1800b9939  movaps  xmmword ptr [rax-58h], xmm7
0x1800b993d  mov     rax, cs:__security_cookie
0x1800b9944  xor     rax, rsp
0x1800b9947  mov     [rsp+138h+var_68], rax
0x1800b994f  mov     r15, r8
0x1800b9952  mov     r12, rdx
0x1800b9955  mov     r13, rcx
0x1800b9958  mov     rax, rcx
0x1800b995b  lea     rdx, [rcx+18h]
0x1800b995f  neg     rax
0x1800b9962  sbb     r8, r8
0x1800b9965  and     r8, rdx
0x1800b9968  mov     [rsp+138h+var_F0], r8
0x1800b996d  xor     esi, esi
0x1800b996f  mov     [rsp+138h+dwindex], esi
0x1800b9973  lea     rdi, [r8+8]
0x1800b9977  lea     rax, [rsp+138h+dwindex]
0x1800b997c  mov     [rsp+138h+lpdwindex], rax; lpdwindex
0x1800b9981  mov     r9, rdi; pHandles
0x1800b9984  lea     r8d, [rsi+1]; cHandles
0x1800b9988  or      edx, 0FFFFFFFFh; dwTimeout
0x1800b998b  xor     ecx, ecx; dwFlags
0x1800b998d  call    cs:__imp_CoWaitForMultipleHandles
0x1800b9993  nop
0x1800b9994  test    r12, r12
0x1800b9997  jnz     short loc_1800B99AC
0x1800b9999  mov     rcx, [rdi]; hMutex
0x1800b999c  call    cs:__imp_ReleaseMutex
0x1800b99a2  mov     eax, 80070057h
0x1800b99a7  jmp     loc_1800B9CA3
0x1800b99ac  mov     [rsp+138h+var_F8], rdi
0x1800b99b1  test    r15, r15
0x1800b99b4  jz      loc_1800B9C95
0x1800b99ba  movups  xmm0, xmmword ptr [r15]
0x1800b99be  movaps  xmmword ptr [rsp+138h+xf1.eM11], xmm0
0x1800b99c6  movsd   xmm1, qword ptr [r15+10h]
0x1800b99cc  movsd   qword ptr [rsp+138h+xf1.eDx], xmm1
0x1800b99d5  lea     rcx, [rsp+138h+xf1]; struct tagVARIANT
0x1800b99dd  call    ?IsBadIntegerPointArrayType@@YA_NUtagVARIANT@@@Z; IsBadIntegerPointArrayType(tagVARIANT)
0x1800b99e2  test    al, al
0x1800b99e4  jnz     short loc_1800B9999
0x1800b99e6  mov     [rsp+138h+var_100], rsi
0x1800b99eb  mov     [rsp+138h+dwindex], esi
0x1800b99ef  mov     [rsp+138h+var_110], rsi; unsigned __int16 *
0x1800b99f4  mov     [rsp+138h+lpdwindex], rsi; bool *
0x1800b99f9  xor     r9d, r9d; unsigned int *
0x1800b99fc  lea     r8, [rsp+138h+dwindex]; unsigned int *
0x1800b9a01  lea     rdx, [rsp+138h+var_100]; unsigned __int8 **
0x1800b9a06  mov     rcx, r15; struct tagVARIANT *
0x1800b9a09  call    ?AccessVariantData@@YAJPEBUtagVARIANT@@PEAPEAEPEAK2PEA_NPEAG@Z; AccessVariantData(tagVARIANT const *,uchar * *,ulong *,ulong *,bool *,ushort *)
0x1800b9a0e  mov     ebx, eax
0x1800b9a10  test    eax, eax
0x1800b9a12  js      loc_1800B9C7D
0x1800b9a18  mov     r14d, [rsp+138h+dwindex]
0x1800b9a1d  mov     rsi, [rsp+138h+var_100]
0x1800b9a22  test    r14b, 7
0x1800b9a26  jnz     loc_1800B9C6C
0x1800b9a2c  test    r14d, r14d
0x1800b9a2f  jz      short loc_1800B9A3A
0x1800b9a31  test    rsi, rsi
0x1800b9a34  jz      loc_1800B9C6C
0x1800b9a3a  shr     r14d, 3
0x1800b9a3e  xorps   xmm0, xmm0
0x1800b9a41  xor     eax, eax
0x1800b9a43  movups  xmmword ptr [rsp+138h+xf2.eM11], xmm0
0x1800b9a4b  mov     qword ptr [rsp+138h+xf2.eDx], rax
0x1800b9a53  xorps   xmm1, xmm1
0x1800b9a56  movups  xmmword ptr [rsp+138h+xf1.eM11], xmm1
0x1800b9a5e  mov     qword ptr [rsp+138h+xf1.eDx], rax
0x1800b9a66  movdqa  xmm0, cs:__xmm@3f80000000000000000000003f800000
0x1800b9a6e  movups  xmmword ptr [rsp+138h+xfOut.eM11], xmm0
0x1800b9a73  mov     qword ptr [rsp+138h+xfOut.eDx], rax
0x1800b9a78  mov     rcx, [r13+30h]
0x1800b9a7c  mov     rax, [rcx]
0x1800b9a7f  lea     rdx, [rsp+138h+xf2]
0x1800b9a87  mov     rax, [rax+0D8h]
0x1800b9a8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9a93  mov     ebx, eax
0x1800b9a95  test    eax, eax
0x1800b9a97  js      short loc_1800B9AB6
0x1800b9a99  mov     rcx, [r13+38h]
0x1800b9a9d  mov     rax, [rcx]
0x1800b9aa0  lea     rdx, [rsp+138h+xf1]
0x1800b9aa8  mov     rax, [rax+0D8h]
0x1800b9aaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9ab4  mov     ebx, eax
0x1800b9ab6  test    ebx, ebx
0x1800b9ab8  js      loc_1800B9C71
0x1800b9abe  mov     rdx, r12; HDC
0x1800b9ac1  lea     rcx, [rsp+138h+var_E8]; retstr
0x1800b9ac6  call    ?GetHiMetricToPixelXForm@@YA?AUtagXFORM@@PEAUHDC__@@@Z; GetHiMetricToPixelXForm(HDC__ *)
0x1800b9acb  movups  xmm0, xmmword ptr [rax]
0x1800b9ace  movups  xmmword ptr [rsp+138h+var_80.eM11], xmm0
0x1800b9ad6  movsd   xmm1, qword ptr [rax+10h]
0x1800b9adb  movsd   qword ptr [rsp+138h+var_80.eDx], xmm1
0x1800b9ae4  lea     r8, [rsp+138h+xf2]; lpxf2
0x1800b9aec  lea     rdx, [rsp+138h+xf1]; lpxf1
0x1800b9af4  lea     rcx, [rsp+138h+xfOut]; lpxfOut
0x1800b9af9  call    cs:__imp_CombineTransform
0x1800b9aff  lea     r8, [rsp+138h+var_80]; lpxf2
0x1800b9b07  lea     rdx, [rsp+138h+xfOut]; lpxf1
0x1800b9b0c  lea     rcx, [rsp+138h+xfOut]; lpxfOut
0x1800b9b11  call    cs:__imp_CombineTransform
0x1800b9b17  movss   xmm5, [rsp+138h+xfOut.eM11]
0x1800b9b1d  movss   xmm6, [rsp+138h+xfOut.eM21]
0x1800b9b23  cmp     [rsp+138h+arg_30], 0
0x1800b9b2b  jz      loc_1800B9BF6
0x1800b9b31  movss   xmm4, [rsp+138h+xfOut.eM22]
0x1800b9b37  mulss   xmm4, xmm5
0x1800b9b3b  movaps  xmm0, xmm6
0x1800b9b3e  movss   xmm7, [rsp+138h+xfOut.eM12]
0x1800b9b44  mulss   xmm0, xmm7
0x1800b9b48  subss   xmm4, xmm0
0x1800b9b4c  cvtps2pd xmm1, xmm4
0x1800b9b4f  movsd   xmm0, cs:__real@3e112e0be826d695
0x1800b9b57  comisd  xmm0, xmm1
0x1800b9b5b  jbe     short loc_1800B9B71
0x1800b9b5d  comisd  xmm1, cs:__real@be112e0be826d695
0x1800b9b65  jbe     short loc_1800B9B71
0x1800b9b67  mov     ebx, 80004005h
0x1800b9b6c  jmp     loc_1800B9BF2
0x1800b9b71  xor     ebx, ebx
0x1800b9b73  movss   xmm3, [rsp+138h+xfOut.eDx]
0x1800b9b79  movss   xmm1, [rsp+138h+xfOut.eDy]
0x1800b9b7f  movaps  xmm2, xmm1
0x1800b9b82  mulss   xmm2, xmm6
0x1800b9b86  movaps  xmm0, xmm3
0x1800b9b89  mulss   xmm0, [rsp+138h+xfOut.eM22]
0x1800b9b8f  subss   xmm2, xmm0
0x1800b9b93  divss   xmm2, xmm4
0x1800b9b97  mulss   xmm3, xmm7
0x1800b9b9b  mulss   xmm1, xmm5
0x1800b9b9f  subss   xmm3, xmm1
0x1800b9ba3  divss   xmm3, xmm4
0x1800b9ba7  divss   xmm5, xmm4
0x1800b9bab  movaps  xmm1, xmm5
0x1800b9bae  movss   xmm5, [rsp+138h+xfOut.eM22]
0x1800b9bb4  divss   xmm5, xmm4
0x1800b9bb8  movss   [rsp+138h+xfOut.eM11], xmm5
0x1800b9bbe  xorps   xmm7, cs:__xmm@80000000800000008000000080000000
0x1800b9bc5  divss   xmm7, xmm4
0x1800b9bc9  movss   [rsp+138h+xfOut.eM12], xmm7
0x1800b9bcf  xorps   xmm6, cs:__xmm@80000000800000008000000080000000
0x1800b9bd6  divss   xmm6, xmm4
0x1800b9bda  movss   [rsp+138h+xfOut.eM21], xmm6
0x1800b9be0  movss   [rsp+138h+xfOut.eM22], xmm1
0x1800b9be6  movss   [rsp+138h+xfOut.eDx], xmm2
0x1800b9bec  movss   [rsp+138h+xfOut.eDy], xmm3
0x1800b9bf2  test    ebx, ebx
0x1800b9bf4  js      short loc_1800B9C71
0x1800b9bf6  mov     rcx, rsi
0x1800b9bf9  xor     edx, edx
0x1800b9bfb  test    r14d, r14d
0x1800b9bfe  jz      short loc_1800B9C71
0x1800b9c00  movd    xmm3, dword ptr [rcx]
0x1800b9c04  cvtdq2ps xmm3, xmm3
0x1800b9c07  movd    xmm4, dword ptr [rcx+4]
0x1800b9c0c  cvtdq2ps xmm4, xmm4
0x1800b9c0f  movss   xmm2, [rsp+138h+xfOut.eDy]
0x1800b9c15  movaps  xmm0, xmm4
0x1800b9c18  mulss   xmm0, xmm6
0x1800b9c1c  movaps  xmm1, xmm3
0x1800b9c1f  mulss   xmm1, xmm5
0x1800b9c23  addss   xmm0, xmm1
0x1800b9c27  addss   xmm0, [rsp+138h+xfOut.eDx]; float
0x1800b9c2d  call    ?RoundToNearestLong@@YAJM@Z; RoundToNearestLong(float)
0x1800b9c32  mov     [rcx], eax
0x1800b9c34  mulss   xmm4, [rsp+138h+xfOut.eM22]
0x1800b9c3a  mulss   xmm3, [rsp+138h+xfOut.eM12]
0x1800b9c40  addss   xmm4, xmm3
0x1800b9c44  addss   xmm4, xmm2
0x1800b9c48  movaps  xmm0, xmm4; float
0x1800b9c4b  call    ?RoundToNearestLong@@YAJM@Z; RoundToNearestLong(float)
0x1800b9c50  mov     [rcx+4], eax
0x1800b9c53  inc     edx
0x1800b9c55  add     rcx, 8
0x1800b9c59  cmp     edx, r14d
0x1800b9c5c  jnb     short loc_1800B9C71
0x1800b9c5e  movss   xmm6, [rsp+138h+xfOut.eM21]
0x1800b9c64  movss   xmm5, [rsp+138h+xfOut.eM11]
0x1800b9c6a  jmp     short loc_1800B9C00
0x1800b9c6c  mov     ebx, 80070057h
0x1800b9c71  mov     rdx, rsi; unsigned __int8 *
0x1800b9c74  mov     rcx, r15; struct tagVARIANT *
0x1800b9c77  call    ?UnaccessVariantData@@YAXPEBUtagVARIANT@@PEAE@Z; UnaccessVariantData(tagVARIANT const *,uchar *)
0x1800b9c7c  nop
0x1800b9c7d  jmp     short loc_1800B9C88
0x1800b9c7f  mov     ebx, [rsp+138h+dwindex]
0x1800b9c83  mov     rdi, [rsp+138h+var_F8]
0x1800b9c88  mov     rcx, [rdi]; hMutex
0x1800b9c8b  call    cs:__imp_ReleaseMutex
0x1800b9c91  mov     eax, ebx
0x1800b9c93  jmp     short loc_1800B9CA3
0x1800b9c95  mov     rcx, [rdi]; hMutex
0x1800b9c98  call    cs:__imp_ReleaseMutex
0x1800b9c9e  mov     eax, 80004003h
0x1800b9ca3  mov     rcx, [rsp+138h+var_68]
0x1800b9cab  xor     rcx, rsp; StackCookie
0x1800b9cae  call    __security_check_cookie
0x1800b9cb3  lea     r11, [rsp+138h+var_38]
0x1800b9cbb  movaps  xmm6, xmmword ptr [r11-10h]
0x1800b9cc0  movaps  xmm7, xmmword ptr [r11-20h]
0x1800b9cc5  mov     rsp, r11
0x1800b9cc8  pop     r15
0x1800b9cca  pop     r14
0x1800b9ccc  pop     r13
0x1800b9cce  pop     r12
0x1800b9cd0  pop     rdi
0x1800b9cd1  pop     rsi
0x1800b9cd2  pop     rbx
0x1800b9cd3  retn
```
