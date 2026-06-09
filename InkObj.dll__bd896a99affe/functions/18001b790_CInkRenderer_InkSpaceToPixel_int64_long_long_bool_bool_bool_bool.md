# CInkRenderer::InkSpaceToPixel(__int64,long *,long *,bool,bool,bool,bool)

- ea: `0x18001b790`
- end: `0x18001bbe7`
- name: `?InkSpaceToPixel@CInkRenderer@@QEAAJ_JPEAJ1_N222@Z`
- size: `1111`
- prototype: `int(CInkRenderer *__hidden this, __int64, int *, int *, bool, bool, bool, bool)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001b760`
- `0x1800b88b0`
- `0x1800b98d0`

## callees

- `0x18001b790`
- `0x180104f30`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b8b1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b8fc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001bbd7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b8b1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b8fc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001bbd7`
- `GDI32!CombineTransform` at `0x18001b9df`
- `GDI32!CombineTransform` at `0x18001b9f4`
- `GDI32!CombineTransform` at `0x18001b9df`
- `GDI32!CombineTransform` at `0x18001b9f4`
- `GDI32!GetDeviceCaps` at `0x18001b911`
- `GDI32!GetDeviceCaps` at `0x18001b92b`
- `GDI32!GetDeviceCaps` at `0x18001b911`
- `GDI32!GetDeviceCaps` at `0x18001b92b`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18001b816`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18001b816`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CInkRenderer::InkSpaceToPixel(
        CInkRenderer *this,
        HDC a2,
        int *a3,
        DWORD *a4,
        bool a5,
        bool a6,
        bool a7,
        bool a8)
{
  HANDLE *v12; // rdx
  HANDLE *v13; // rdi
  int v14; // r13d
  signed int v15; // esi
  int DeviceCaps; // ebx
  int v18; // eax
  float v19; // xmm1_4
  FLOAT v20; // xmm0_4
  float eM22; // xmm6_4
  float eM11; // xmm3_4
  float eM12; // xmm5_4
  float eM21; // xmm4_4
  float v25; // xmm2_4
  float eDx; // xmm8_4
  float eDy; // xmm7_4
  float v28; // xmm2_4
  float v29; // xmm1_4
  double v30; // xmm0_8
  double v31; // xmm0_8
  float v32; // xmm2_4
  double v33; // xmm0_8
  double v34; // xmm0_8
  DWORD dwindex; // [rsp+30h] [rbp-108h] BYREF
  HANDLE *v36; // [rsp+38h] [rbp-100h]
  HANDLE *v37; // [rsp+40h] [rbp-F8h]
  _XFORM xfOut; // [rsp+48h] [rbp-F0h] BYREF
  XFORM xf2; // [rsp+60h] [rbp-D8h] BYREF
  XFORM v40; // [rsp+78h] [rbp-C0h] BYREF
  XFORM xf1; // [rsp+90h] [rbp-A8h] BYREF

  v12 = (HANDLE *)((char *)this + 24);
  if ( !this )
    v12 = 0;
  v37 = v12;
  dwindex = 0;
  v13 = v12 + 1;
  v36 = v12 + 1;
  CoWaitForMultipleHandles(0, 0xFFFFFFFF, 1u, v12 + 1, &dwindex);
  if ( !a2 )
  {
    ReleaseMutex(*v13);
    return 2147942487LL;
  }
  if ( !a3 || !a4 )
  {
    ReleaseMutex(*v13);
    return 2147500035LL;
  }
  try
  {
    v14 = *a3;
    dwindex = *a4;
    memset(&xf2, 0, sizeof(xf2));
    memset(&xf1, 0, sizeof(xf1));
    memset(&xfOut, 0, sizeof(xfOut));
    v15 = (*(__int64 (__fastcall **)(_QWORD, XFORM *))(**((_QWORD **)this + 6) + 216LL))(*((_QWORD *)this + 6), &xf2);
    if ( v15 >= 0 )
      v15 = (*(__int64 (__fastcall **)(_QWORD, XFORM *))(**((_QWORD **)this + 7) + 216LL))(*((_QWORD *)this + 7), &xf1);
    if ( v15 < 0 )
      goto LABEL_42;
    DeviceCaps = GetDeviceCaps(a2, 88);
    if ( !DeviceCaps )
      DeviceCaps = 96;
    v18 = GetDeviceCaps(a2, 90);
    if ( !v18 )
      v18 = 96;
    v19 = (double)DeviceCaps / 2540.0;
    v20 = 1.0 / (float)(1.0 / v19);
    v40.eM11 = v20;
    *(_QWORD *)&v40.eM12 = 0;
    v40.eM22 = 1.0 / (float)(1.0 / (float)((double)v18 / 2540.0));
    *(_QWORD *)&v40.eDx = 0;
    if ( a6 )
    {
      CombineTransform(&xfOut, &xf1, &xf2);
    }
    else if ( a5 )
    {
      xfOut = xf2;
    }
    else
    {
      *(__m128i *)&xfOut.eM11 = _mm_load_si128((const __m128i *)&_xmm);
      *(_QWORD *)&xfOut.eDx = 0;
    }
    CombineTransform(&xfOut, &xfOut, &v40);
    eM22 = xfOut.eM22;
    eM11 = xfOut.eM11;
    eM12 = xfOut.eM12;
    eM21 = xfOut.eM21;
    if ( !a8 )
    {
      eDy = xfOut.eDy;
      eDx = xfOut.eDx;
LABEL_23:
      if ( !a7 )
      {
        eDy = 0.0;
        eDx = 0.0;
      }
      v28 = (float)(int)dwindex;
      v29 = (float)((float)((float)(int)dwindex * eM21) + (float)((float)v14 * eM11)) + eDx;
      v30 = v29;
      if ( v29 < 0.0 )
        v31 = v30 - 0.5;
      else
        v31 = v30 + 0.5;
      *a3 = (int)v31;
      v32 = (float)((float)(v28 * eM22) + (float)((float)v14 * eM12)) + eDy;
      v33 = v32;
      if ( v32 < 0.0 )
        v34 = v33 - 0.5;
      else
        v34 = v33 + 0.5;
      *a4 = (int)v34;
      goto LABEL_42;
    }
    v25 = (float)(xfOut.eM22 * xfOut.eM11) - (float)(xfOut.eM12 * xfOut.eM21);
    if ( v25 >= 0.000000001 || v25 <= -0.000000001 )
    {
      v15 = 0;
      eDx = (float)((float)(xfOut.eM21 * xfOut.eDy) - (float)(xfOut.eDx * xfOut.eM22)) / v25;
      eDy = (float)((float)(xfOut.eDx * xfOut.eM12) - (float)(xfOut.eM11 * xfOut.eDy)) / v25;
      eM11 = xfOut.eM22 / v25;
      eM12 = COERCE_FLOAT(LODWORD(xfOut.eM12) ^ _xmm) / v25;
      eM21 = COERCE_FLOAT(LODWORD(xfOut.eM21) ^ _xmm) / v25;
      eM22 = xfOut.eM11 / v25;
    }
    else
    {
      v15 = -2147467259;
      eDy = xfOut.eDy;
      eDx = xfOut.eDx;
    }
    if ( v15 >= 0 )
      goto LABEL_23;
  }
  catch ( ... )
  {
    dwindex = ReportWispException();
    v15 = dwindex;
    v13 = v36;
  }
LABEL_42:
  ReleaseMutex(*v13);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18001b790  mov     rax, rsp
0x18001b793  push    rbx
0x18001b794  push    rsi
0x18001b795  push    rdi
0x18001b796  push    r12
0x18001b798  push    r13
0x18001b79a  push    r14
0x18001b79c  push    r15
0x18001b79e  sub     rsp, 100h
0x18001b7a5  movaps  xmmword ptr [rax-48h], xmm6
0x18001b7a9  movaps  xmmword ptr [rax-58h], xmm7
0x18001b7ad  movaps  xmmword ptr [rax-68h], xmm8
0x18001b7b2  movaps  xmmword ptr [rax-78h], xmm9
0x18001b7b7  movaps  xmmword ptr [rax-88h], xmm10
0x18001b7bf  mov     rax, cs:__security_cookie
0x18001b7c6  xor     rax, rsp
0x18001b7c9  mov     [rsp+138h+var_90], rax
0x18001b7d1  mov     r15, r9
0x18001b7d4  mov     r12, r8
0x18001b7d7  mov     r14, rdx
0x18001b7da  mov     rbx, rcx
0x18001b7dd  lea     rdx, [rcx+18h]
0x18001b7e1  xor     eax, eax
0x18001b7e3  test    rcx, rcx
0x18001b7e6  cmovz   rdx, rax
0x18001b7ea  mov     [rsp+138h+var_F8], rdx
0x18001b7ef  mov     [rsp+138h+dwindex], eax
0x18001b7f3  lea     rdi, [rdx+8]
0x18001b7f7  mov     [rsp+138h+var_100], rdi
0x18001b7fc  lea     rax, [rsp+138h+dwindex]
0x18001b801  mov     [rsp+138h+lpdwindex], rax; lpdwindex
0x18001b806  mov     r9, rdi; pHandles
0x18001b809  mov     edx, 0FFFFFFFFh; dwTimeout
0x18001b80e  xor     ecx, ecx; dwFlags
0x18001b810  mov     r8d, 1; cHandles
0x18001b816  call    cs:__imp_CoWaitForMultipleHandles
0x18001b81c  nop
0x18001b81d  test    r14, r14
0x18001b820  jz      loc_18001B8F9
0x18001b826  test    r12, r12
0x18001b829  jz      loc_18001BBD4
0x18001b82f  test    r15, r15
0x18001b832  jz      loc_18001BBD4
0x18001b838  mov     r13d, [r12]
0x18001b83c  mov     eax, [r15]
0x18001b83f  mov     [rsp+138h+dwindex], eax
0x18001b843  xorps   xmm0, xmm0
0x18001b846  xor     eax, eax
0x18001b848  movups  xmmword ptr [rsp+138h+xf2.eM11], xmm0
0x18001b84d  mov     qword ptr [rsp+138h+xf2.eDx], rax
0x18001b852  xorps   xmm1, xmm1
0x18001b855  movups  xmmword ptr [rsp+138h+xf1.eM11], xmm1
0x18001b85d  mov     qword ptr [rsp+138h+xf1.eDx], rax
0x18001b865  movups  xmmword ptr [rsp+138h+xfOut.eM11], xmm0
0x18001b86a  mov     qword ptr [rsp+138h+xfOut.eDx], rax
0x18001b86f  mov     rcx, [rbx+30h]
0x18001b873  mov     rax, [rcx]
0x18001b876  lea     rdx, [rsp+138h+xf2]
0x18001b87b  mov     rax, [rax+0D8h]
0x18001b882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b887  mov     esi, eax
0x18001b889  test    eax, eax
0x18001b88b  js      short loc_18001B8AA
0x18001b88d  mov     rcx, [rbx+38h]
0x18001b891  mov     rax, [rcx]
0x18001b894  lea     rdx, [rsp+138h+xf1]
0x18001b89c  mov     rax, [rax+0D8h]
0x18001b8a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b8a8  mov     esi, eax
0x18001b8aa  test    esi, esi
0x18001b8ac  jns     short loc_18001B909
0x18001b8ae  mov     rcx, [rdi]; hMutex
0x18001b8b1  call    cs:__imp_ReleaseMutex
0x18001b8b7  mov     eax, esi
0x18001b8b9  mov     rcx, [rsp+138h+var_90]
0x18001b8c1  xor     rcx, rsp; StackCookie
0x18001b8c4  call    __security_check_cookie
0x18001b8c9  lea     r11, [rsp+138h+var_38]
0x18001b8d1  movaps  xmm6, xmmword ptr [r11-10h]
0x18001b8d6  movaps  xmm7, xmmword ptr [r11-20h]
0x18001b8db  movaps  xmm8, xmmword ptr [r11-30h]
0x18001b8e0  movaps  xmm9, xmmword ptr [r11-40h]
0x18001b8e5  movaps  xmm10, xmmword ptr [r11-50h]
0x18001b8ea  mov     rsp, r11
0x18001b8ed  pop     r15
0x18001b8ef  pop     r14
0x18001b8f1  pop     r13
0x18001b8f3  pop     r12
0x18001b8f5  pop     rdi
0x18001b8f6  pop     rsi
0x18001b8f7  pop     rbx
0x18001b8f8  retn
0x18001b8f9  mov     rcx, [rdi]; hMutex
0x18001b8fc  call    cs:__imp_ReleaseMutex
0x18001b902  mov     eax, 80070057h
0x18001b907  jmp     short loc_18001B8B9
0x18001b909  mov     edx, 58h ; 'X'; index
0x18001b90e  mov     rcx, r14; hdc
0x18001b911  call    cs:__imp_GetDeviceCaps
0x18001b917  mov     ebx, eax
0x18001b919  mov     eax, 60h ; '`'
0x18001b91e  test    ebx, ebx
0x18001b920  cmovz   ebx, eax
0x18001b923  mov     edx, 5Ah ; 'Z'; index
0x18001b928  mov     rcx, r14; hdc
0x18001b92b  call    cs:__imp_GetDeviceCaps
0x18001b931  test    eax, eax
0x18001b933  mov     ecx, 60h ; '`'
0x18001b938  cmovz   eax, ecx
0x18001b93b  movd    xmm0, ebx
0x18001b93f  cvtdq2pd xmm0, xmm0
0x18001b943  divsd   xmm0, cs:__real@40a3d80000000000
0x18001b94b  cvtpd2ps xmm1, xmm0
0x18001b94f  movss   xmm5, cs:__real@3f800000
0x18001b957  movaps  xmm0, xmm5
0x18001b95a  divss   xmm0, xmm1
0x18001b95e  cvtps2pd xmm2, xmm0
0x18001b961  movsd   xmm4, cs:__real@3ff0000000000000
0x18001b969  movaps  xmm1, xmm4
0x18001b96c  divsd   xmm1, xmm2
0x18001b970  cvtpd2ps xmm0, xmm1
0x18001b974  movss   [rsp+138h+var_C0.eM11], xmm0
0x18001b97a  xorps   xmm10, xmm10
0x18001b97e  mov     qword ptr [rsp+138h+var_C0.eM12], 0
0x18001b987  movd    xmm0, eax
0x18001b98b  cvtdq2pd xmm0, xmm0
0x18001b98f  divsd   xmm0, cs:__real@40a3d80000000000
0x18001b997  cvtpd2ps xmm1, xmm0
0x18001b99b  divss   xmm5, xmm1
0x18001b99f  cvtps2pd xmm0, xmm5
0x18001b9a2  divsd   xmm4, xmm0
0x18001b9a6  cvtpd2ps xmm0, xmm4
0x18001b9aa  movss   [rsp+138h+var_C0.eM22], xmm0
0x18001b9b3  mov     qword ptr [rsp+138h+var_C0.eDx], 0
0x18001b9bf  cmp     [rsp+138h+arg_28], 0
0x18001b9c7  jz      loc_18001BB43
0x18001b9cd  lea     r8, [rsp+138h+xf2]; lpxf2
0x18001b9d2  lea     rdx, [rsp+138h+xf1]; lpxf1
0x18001b9da  lea     rcx, [rsp+138h+xfOut]; lpxfOut
0x18001b9df  call    cs:__imp_CombineTransform
0x18001b9e5  lea     r8, [rsp+138h+var_C0]; lpxf2
0x18001b9ea  lea     rdx, [rsp+138h+xfOut]; lpxf1
0x18001b9ef  lea     rcx, [rsp+138h+xfOut]; lpxfOut
0x18001b9f4  call    cs:__imp_CombineTransform
0x18001b9fa  movss   xmm6, [rsp+138h+xfOut.eM22]
0x18001ba00  movss   xmm3, [rsp+138h+xfOut.eM11]
0x18001ba06  movss   xmm5, [rsp+138h+xfOut.eM12]
0x18001ba0c  movss   xmm4, [rsp+138h+xfOut.eM21]
0x18001ba12  cmp     [rsp+138h+arg_38], 0
0x18001ba1a  jz      loc_18001BBB4
0x18001ba20  movaps  xmm2, xmm6
0x18001ba23  mulss   xmm2, xmm3
0x18001ba27  movaps  xmm0, xmm5
0x18001ba2a  mulss   xmm0, xmm4
0x18001ba2e  subss   xmm2, xmm0
0x18001ba32  cvtps2pd xmm1, xmm2
0x18001ba35  movsd   xmm0, cs:__real@3e112e0be826d695
0x18001ba3d  comisd  xmm0, xmm1
0x18001ba41  ja      loc_18001BB8F
0x18001ba47  xor     esi, esi
0x18001ba49  movss   xmm7, [rsp+138h+xfOut.eDx]
0x18001ba4f  movaps  xmm8, xmm4
0x18001ba53  mulss   xmm8, [rsp+138h+xfOut.eDy]
0x18001ba5a  movaps  xmm0, xmm7
0x18001ba5d  mulss   xmm0, xmm6
0x18001ba61  subss   xmm8, xmm0
0x18001ba66  divss   xmm8, xmm2
0x18001ba6b  mulss   xmm7, xmm5
0x18001ba6f  movaps  xmm0, xmm3
0x18001ba72  mulss   xmm0, [rsp+138h+xfOut.eDy]
0x18001ba78  subss   xmm7, xmm0
0x18001ba7c  divss   xmm7, xmm2
0x18001ba80  divss   xmm3, xmm2
0x18001ba84  movaps  xmm1, xmm3
0x18001ba87  movaps  xmm3, xmm6
0x18001ba8a  divss   xmm3, xmm2
0x18001ba8e  xorps   xmm5, cs:__xmm@80000000800000008000000080000000
0x18001ba95  divss   xmm5, xmm2
0x18001ba99  xorps   xmm4, cs:__xmm@80000000800000008000000080000000
0x18001baa0  divss   xmm4, xmm2
0x18001baa4  movaps  xmm6, xmm1
0x18001baa7  test    esi, esi
0x18001baa9  js      loc_18001B8AE
0x18001baaf  cmp     [rsp+138h+arg_30], 0
0x18001bab7  jz      short loc_18001BB37
0x18001bab9  movd    xmm9, r13d
0x18001babe  cvtdq2ps xmm9, xmm9
0x18001bac2  movd    xmm2, [rsp+138h+dwindex]
0x18001bac8  cvtdq2ps xmm2, xmm2
0x18001bacb  movaps  xmm1, xmm2
0x18001bace  mulss   xmm1, xmm4
0x18001bad2  movaps  xmm0, xmm9
0x18001bad6  mulss   xmm0, xmm3
0x18001bada  addss   xmm1, xmm0
0x18001bade  addss   xmm1, xmm8
0x18001bae3  cvtps2pd xmm0, xmm1
0x18001bae6  comiss  xmm1, xmm10
0x18001baea  movsd   xmm1, cs:__real@3fe0000000000000
0x18001baf2  jb      short loc_18001BB2B
0x18001baf4  addsd   xmm0, xmm1
0x18001baf8  cvttsd2si eax, xmm0
0x18001bafc  mov     [r12], eax
0x18001bb00  mulss   xmm2, xmm6
0x18001bb04  mulss   xmm9, xmm5
0x18001bb09  addss   xmm2, xmm9
0x18001bb0e  addss   xmm2, xmm7
0x18001bb12  cvtps2pd xmm0, xmm2
0x18001bb15  comiss  xmm2, xmm10
0x18001bb19  jb      short loc_18001BB31
0x18001bb1b  addsd   xmm0, xmm1
0x18001bb1f  cvttsd2si eax, xmm0
0x18001bb23  mov     [r15], eax
0x18001bb26  jmp     loc_18001B8AE
0x18001bb2b  subsd   xmm0, xmm1
0x18001bb2f  jmp     short loc_18001BAF8
0x18001bb31  subsd   xmm0, xmm1
0x18001bb35  jmp     short loc_18001BB1F
0x18001bb37  xorps   xmm7, xmm7
0x18001bb3a  xorps   xmm8, xmm8
0x18001bb3e  jmp     loc_18001BAB9
0x18001bb43  cmp     [rsp+138h+arg_20], 0
0x18001bb4b  jz      short loc_18001BB74
0x18001bb4d  movups  xmm0, xmmword ptr [rsp+138h+xf2.eM11]
0x18001bb52  movups  xmmword ptr [rsp+138h+xfOut.eM11], xmm0
0x18001bb57  movss   xmm0, [rsp+138h+xf2.eDx]
0x18001bb5d  movss   [rsp+138h+xfOut.eDx], xmm0
0x18001bb63  movss   xmm1, [rsp+138h+xf2.eDy]
0x18001bb69  movss   [rsp+138h+xfOut.eDy], xmm1
0x18001bb6f  jmp     loc_18001B9E5
0x18001bb74  movdqa  xmm0, cs:__xmm@3f80000000000000000000003f800000
0x18001bb7c  movups  xmmword ptr [rsp+138h+xfOut.eM11], xmm0
0x18001bb81  mov     qword ptr [rsp+138h+xfOut.eDx], 0
0x18001bb8a  jmp     loc_18001B9E5
0x18001bb8f  comisd  xmm1, cs:__real@be112e0be826d695
0x18001bb97  jbe     loc_18001BA47
0x18001bb9d  mov     esi, 80004005h
0x18001bba2  movss   xmm7, [rsp+138h+xfOut.eDy]
0x18001bba8  movss   xmm8, [rsp+138h+xfOut.eDx]
0x18001bbaf  jmp     loc_18001BAA7
0x18001bbb4  movss   xmm7, [rsp+138h+xfOut.eDy]
0x18001bbba  movss   xmm8, [rsp+138h+xfOut.eDx]
0x18001bbc1  jmp     loc_18001BAAF
0x18001bbc6  mov     esi, [rsp+138h+dwindex]
0x18001bbca  mov     rdi, [rsp+138h+var_100]
0x18001bbcf  jmp     loc_18001B8AE
0x18001bbd4  mov     rcx, [rdi]; hMutex
0x18001bbd7  call    cs:__imp_ReleaseMutex
0x18001bbdd  mov     eax, 80004003h
0x18001bbe2  jmp     loc_18001B8B9
```
