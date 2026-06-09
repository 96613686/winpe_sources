# GpMetafile::InitForRecording(HDC__ *,EmfType,RectF const *,MetafileFrameUnit,ushort const *,GpMetafile *)

- ea: `0x18009c2a8`
- end: `0x18009c6db`
- name: `?InitForRecording@GpMetafile@@IEAAHPEAUHDC__@@W4EmfType@@PEBVRectF@@W4MetafileFrameUnit@@PEBGPEAV1@@Z`
- size: `1075`
- prototype: `int __high(HDC, enum EmfType, const struct RectF *, enum MetafileFrameUnit, const unsigned __int16 *, struct GpMetafile *)`
- caller_count: `3`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x18009aba0`
- `0x18011cbb0`
- `0x18011cc60`

## callees

- `0x18002739c`
- `0x18009c2a8`
- `0x18009c9c8`
- `0x18009cc6c`
- `0x18009d608`
- `0x1800fe680`
- `0x1800fefe0`
- `0x180169010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009c48d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009c48d`
- `GDI32!CreateEnhMetaFileW` at `0x18009c34e`
- `GDI32!CreateEnhMetaFileW` at `0x18009c34e`
- `GDI32!CloseEnhMetaFile` at `0x18009c49f`
- `GDI32!CloseEnhMetaFile` at `0x18009c49f`
- `GDI32!DeleteEnhMetaFile` at `0x18009c4a8`
- `GDI32!DeleteEnhMetaFile` at `0x18009c4a8`
- `GDI32!GetDeviceCaps` at `0x18009c368`
- `GDI32!GetDeviceCaps` at `0x18009c379`
- `GDI32!GetDeviceCaps` at `0x18009c38e`
- `GDI32!GetDeviceCaps` at `0x18009c3a0`
- `GDI32!GetDeviceCaps` at `0x18009c368`
- `GDI32!GetDeviceCaps` at `0x18009c379`
- `GDI32!GetDeviceCaps` at `0x18009c38e`
- `GDI32!GetDeviceCaps` at `0x18009c3a0`

## pseudocode

```c
__int64 __fastcall GpMetafile::InitForRecording(
        __int64 a1,
        HDC a2,
        unsigned int a3,
        float *a4,
        int a5,
        __int64 a6,
        __int64 a7)
{
  const RECT *v7; // r14
  HDC EnhMetaFileW; // rax
  HDC v12; // rdi
  int DeviceCaps; // r13d
  unsigned int v14; // r15d
  int v15; // r12d
  int v16; // ebx
  int v17; // eax
  float v18; // xmm5_4
  float v19; // xmm6_4
  float v20; // xmm5_4
  float v21; // xmm6_4
  LPVOID v22; // rax
  HENHMETAFILE v23; // rax
  __m128 v25; // xmm7
  bool v26; // di
  __m128 v27; // xmm1
  int v28; // r12d
  __m128 v29; // xmm6
  __m128 v30; // xmm1
  int v31; // r15d
  int v32; // r14d
  int v33; // eax
  __int64 v34; // r12
  bool v35; // zf
  unsigned int v36; // r14d
  __int64 v37; // rax
  __int64 v38; // rbx
  __int64 v39; // rax
  unsigned int v40; // edx
  GpGraphics *v41; // rcx
  __int64 v42; // [rsp+58h] [rbp-61h] BYREF
  float v43; // [rsp+60h] [rbp-59h]
  float v44; // [rsp+64h] [rbp-55h]
  unsigned int v45; // [rsp+68h] [rbp-51h]
  _DWORD v46[2]; // [rsp+70h] [rbp-49h] BYREF
  __int64 v47; // [rsp+78h] [rbp-41h]
  __int128 v48; // [rsp+80h] [rbp-39h] BYREF

  v7 = 0;
  v45 = a3;
  v47 = a7;
  v48 = 0;
  if ( a4 )
  {
    if ( a4[2] < 0.0 || a4[3] < 0.0 )
      return 0;
    if ( a5 == 7 )
    {
      v25 = (__m128)*(unsigned int *)a4;
      v26 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
      v27 = v25;
      v27.m128_f32[0] = v25.m128_f32[0] + 0.5;
      if ( Feature_GdiPlusOptimizations_Misc_IsEnabled )
        v28 = (int)_mm_round_ss(v27, v27, 9).m128_f32[0];
      else
        v28 = (int)floor(v27.m128_f32[0]);
      v29 = (__m128)*((unsigned int *)a4 + 1);
      LODWORD(v48) = v28;
      v30 = v29;
      v30.m128_f32[0] = v29.m128_f32[0] + 0.5;
      if ( v26 )
        v31 = (int)_mm_round_ss(v30, v30, 9).m128_f32[0];
      else
        v31 = (int)floor(v30.m128_f32[0]);
      DWORD1(v48) = v31;
      v25.m128_f32[0] = (float)(v25.m128_f32[0] + a4[2]) + 0.5;
      if ( v26 )
        v32 = (int)_mm_round_ss(v25, v25, 9).m128_f32[0];
      else
        v32 = (int)floor(v25.m128_f32[0]);
      DWORD2(v48) = v32;
      v29.m128_f32[0] = (float)(v29.m128_f32[0] + a4[3]) + 0.5;
      if ( v26 )
        v33 = (int)_mm_round_ss(v29, v29, 9).m128_f32[0];
      else
        v33 = (int)floor(v29.m128_f32[0]);
      HIDWORD(v48) = v33;
      if ( v28 > v32 || v31 > v33 )
        return 0;
    }
    else if ( !(unsigned int)GetFrameRectInMM100Units(a2) )
    {
      return 0;
    }
    v7 = (const RECT *)&v48;
  }
  EnhMetaFileW = CreateEnhMetaFileW(a2, *(LPCWSTR *)(a1 + 192), v7, 0);
  v12 = EnhMetaFileW;
  if ( !EnhMetaFileW )
    return 0;
  DeviceCaps = GetDeviceCaps(EnhMetaFileW, 8);
  v14 = 4;
  v15 = GetDeviceCaps(v12, 10);
  v16 = GetDeviceCaps(v12, 4);
  v46[0] = v16;
  v17 = GetDeviceCaps(v12, 6);
  v46[1] = v17;
  if ( DeviceCaps <= 0 || v15 <= 0 || v16 <= 0 || v17 <= 0 )
    goto LABEL_15;
  v18 = (float)DeviceCaps / (float)v16;
  *(float *)(a1 + 48) = v18 * 25.4;
  v19 = (float)v15 / (float)v17;
  *(float *)(a1 + 52) = v19 * 25.4;
  if ( v7 )
  {
    v20 = v18 * 0.0099999998;
    v21 = v19 * 0.0099999998;
    *(float *)&v42 = (float)(int)v48 * v20;
    *((float *)&v42 + 1) = (float)SDWORD1(v48) * v21;
    v43 = (float)(DWORD2(v48) - v48) * v20;
    v44 = (float)(HIDWORD(v48) - DWORD1(v48)) * v21;
  }
  else
  {
    v42 = 0;
    v43 = (float)DeviceCaps - 1.0;
    v44 = (float)v15 - 1.0;
  }
  v22 = HeapAlloc(GpRuntime::GpMemHeap, 0, 0x6D8u);
  if ( !v22 )
    goto LABEL_15;
  v34 = v47;
  v35 = v7 == 0;
  v36 = v45;
  v37 = MetafileRecorder::MetafileRecorder(v22, a1, v45, v12, !v35, v46, &v42);
  v38 = v37;
  if ( !v37 )
    goto LABEL_15;
  if ( *(_DWORD *)(v37 + 8) != 1666338097 )
  {
    (**(void (__fastcall ***)(__int64, __int64))v37)(v37, 1);
    goto LABEL_15;
  }
  if ( !v34 )
    v14 = v36;
  v39 = GpGraphics::GetForMetafile(v37, v14, v12);
  *(_QWORD *)(a1 + 208) = v39;
  if ( !v39 )
  {
    (**(void (__fastcall ***)(__int64, __int64))v38)(v38, 1);
LABEL_15:
    v23 = CloseEnhMetaFile(v12);
    DeleteEnhMetaFile(v23);
    return 0;
  }
  if ( *(_DWORD *)(v39 + 8) != 1634879281 )
  {
    *(_DWORD *)(v38 + 8) = 1279869254;
    v41 = *(GpGraphics **)(a1 + 208);
    if ( v41 )
      GpGraphics::`scalar deleting destructor'(v41, v40);
    *(_QWORD *)(a1 + 208) = 0;
    goto LABEL_15;
  }
  return 1;
}

```

## disassembly

```asm
0x18009c2a8  mov     rax, rsp
0x18009c2ab  push    rbp
0x18009c2ac  push    rbx
0x18009c2ad  push    rsi
0x18009c2ae  push    rdi
0x18009c2af  push    r12
0x18009c2b1  push    r13
0x18009c2b3  push    r14
0x18009c2b5  push    r15
0x18009c2b7  lea     rbp, [rax-47h]
0x18009c2bb  sub     rsp, 0B8h
0x18009c2c2  movaps  xmmword ptr [rax-58h], xmm6
0x18009c2c6  movaps  xmmword ptr [rax-68h], xmm7
0x18009c2ca  mov     rax, cs:__security_cookie
0x18009c2d1  xor     rax, rsp
0x18009c2d4  mov     [rbp+3Fh+var_68], rax
0x18009c2d8  mov     rax, [rbp+3Fh+arg_30]
0x18009c2dc  xor     r14d, r14d
0x18009c2df  mov     [rbp+3Fh+var_90], r8d
0x18009c2e3  xorps   xmm0, xmm0
0x18009c2e6  mov     [rbp+3Fh+var_80], rax
0x18009c2ea  mov     rbx, r9
0x18009c2ed  mov     r13, rdx
0x18009c2f0  mov     rsi, rcx
0x18009c2f3  xorps   xmm1, xmm1
0x18009c2f6  movups  [rbp+3Fh+var_78], xmm0
0x18009c2fa  test    r9, r9
0x18009c2fd  jz      short loc_18009C33E
0x18009c2ff  comiss  xmm1, dword ptr [r9+8]
0x18009c304  ja      loc_18009C4AE
0x18009c30a  comiss  xmm1, dword ptr [r9+0Ch]
0x18009c30f  ja      loc_18009C4AE
0x18009c315  mov     r8d, [rbp+3Fh+arg_20]
0x18009c319  cmp     r8d, 7
0x18009c31d  jz      loc_18009C505
0x18009c323  lea     r9, [rbp+3Fh+var_78]
0x18009c327  mov     rdx, rbx
0x18009c32a  mov     rcx, r13; hdc
0x18009c32d  call    GetFrameRectInMM100Units
0x18009c332  test    eax, eax
0x18009c334  jz      loc_18009C4AE
0x18009c33a  lea     r14, [rbp+3Fh+var_78]
0x18009c33e  mov     rdx, [rsi+0C0h]; lpFilename
0x18009c345  xor     r9d, r9d; lpDesc
0x18009c348  mov     r8, r14; lprc
0x18009c34b  mov     rcx, r13; hdc
0x18009c34e  call    cs:__imp_CreateEnhMetaFileW
0x18009c354  mov     rdi, rax
0x18009c357  test    rax, rax
0x18009c35a  jz      loc_18009C4AE
0x18009c360  mov     edx, 8; index
0x18009c365  mov     rcx, rax; hdc
0x18009c368  call    cs:__imp_GetDeviceCaps
0x18009c36e  mov     edx, 0Ah; index
0x18009c373  mov     rcx, rdi; hdc
0x18009c376  mov     r13d, eax
0x18009c379  call    cs:__imp_GetDeviceCaps
0x18009c37f  mov     r15d, 4
0x18009c385  mov     rcx, rdi; hdc
0x18009c388  mov     edx, r15d; index
0x18009c38b  mov     r12d, eax
0x18009c38e  call    cs:__imp_GetDeviceCaps
0x18009c394  lea     edx, [r15+2]; index
0x18009c398  mov     rcx, rdi; hdc
0x18009c39b  mov     ebx, eax
0x18009c39d  mov     [rbp+3Fh+var_88], eax
0x18009c3a0  call    cs:__imp_GetDeviceCaps
0x18009c3a6  mov     [rbp+3Fh+var_84], eax
0x18009c3a9  test    r13d, r13d
0x18009c3ac  jle     loc_18009C49C
0x18009c3b2  test    r12d, r12d
0x18009c3b5  jle     loc_18009C49C
0x18009c3bb  test    ebx, ebx
0x18009c3bd  jle     loc_18009C49C
0x18009c3c3  test    eax, eax
0x18009c3c5  jle     loc_18009C49C
0x18009c3cb  movd    xmm3, r13d
0x18009c3d0  movd    xmm0, ebx
0x18009c3d4  movd    xmm4, r12d
0x18009c3d9  cvtdq2ps xmm0, xmm0
0x18009c3dc  cvtdq2ps xmm3, xmm3
0x18009c3df  cvtdq2ps xmm4, xmm4
0x18009c3e2  movaps  xmm5, xmm3
0x18009c3e5  movaps  xmm6, xmm4
0x18009c3e8  divss   xmm5, xmm0
0x18009c3ec  movd    xmm0, eax
0x18009c3f0  movaps  xmm1, xmm5
0x18009c3f3  mulss   xmm1, cs:__real@41cb3333
0x18009c3fb  cvtdq2ps xmm0, xmm0
0x18009c3fe  movss   dword ptr [rsi+30h], xmm1
0x18009c403  divss   xmm6, xmm0
0x18009c407  movaps  xmm0, xmm6
0x18009c40a  mulss   xmm0, cs:__real@41cb3333
0x18009c412  movss   dword ptr [rsi+34h], xmm0
0x18009c417  test    r14, r14
0x18009c41a  jz      loc_18009C4DE
0x18009c420  mulss   xmm5, cs:__real@3c23d70a
0x18009c428  mov     eax, dword ptr [rbp+3Fh+var_78+8]
0x18009c42b  sub     eax, dword ptr [rbp+3Fh+var_78]
0x18009c42e  movd    xmm0, dword ptr [rbp+3Fh+var_78]
0x18009c433  mulss   xmm6, cs:__real@3c23d70a
0x18009c43b  movd    xmm1, dword ptr [rbp+3Fh+var_78+4]
0x18009c440  cvtdq2ps xmm0, xmm0
0x18009c443  cvtdq2ps xmm1, xmm1
0x18009c446  mulss   xmm0, xmm5
0x18009c44a  mulss   xmm1, xmm6
0x18009c44e  movss   dword ptr [rbp+3Fh+var_A0], xmm0
0x18009c453  movd    xmm0, eax
0x18009c457  mov     eax, dword ptr [rbp+3Fh+var_78+0Ch]
0x18009c45a  sub     eax, dword ptr [rbp+3Fh+var_78+4]
0x18009c45d  cvtdq2ps xmm0, xmm0
0x18009c460  movss   dword ptr [rbp+3Fh+var_A0+4], xmm1
0x18009c465  mulss   xmm0, xmm5
0x18009c469  movss   [rbp+3Fh+var_98], xmm0
0x18009c46e  movd    xmm0, eax
0x18009c472  cvtdq2ps xmm0, xmm0
0x18009c475  mulss   xmm0, xmm6
0x18009c479  movss   [rbp+3Fh+var_94], xmm0
0x18009c47e  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x18009c485  xor     edx, edx; dwFlags
0x18009c487  mov     r8d, 6D8h; dwBytes
0x18009c48d  call    cs:__imp_HeapAlloc
0x18009c493  test    rax, rax
0x18009c496  jnz     loc_18009C5C3
0x18009c49c  mov     rcx, rdi; hdc
0x18009c49f  call    cs:__imp_CloseEnhMetaFile
0x18009c4a5  mov     rcx, rax; hmf
0x18009c4a8  call    cs:__imp_DeleteEnhMetaFile
0x18009c4ae  xor     eax, eax
0x18009c4b0  mov     rcx, [rbp+3Fh+var_68]
0x18009c4b4  xor     rcx, rsp; StackCookie
0x18009c4b7  call    __security_check_cookie
0x18009c4bc  lea     r11, [rsp+0F0h+var_38]
0x18009c4c4  movaps  xmm6, xmmword ptr [r11-18h]
0x18009c4c9  movaps  xmm7, xmmword ptr [r11-28h]
0x18009c4ce  mov     rsp, r11
0x18009c4d1  pop     r15
0x18009c4d3  pop     r14
0x18009c4d5  pop     r13
0x18009c4d7  pop     r12
0x18009c4d9  pop     rdi
0x18009c4da  pop     rsi
0x18009c4db  pop     rbx
0x18009c4dc  pop     rbp
0x18009c4dd  retn
0x18009c4de  subss   xmm3, cs:__real@3f800000
0x18009c4e6  subss   xmm4, cs:__real@3f800000
0x18009c4ee  mov     [rbp+3Fh+var_A0], 0
0x18009c4f6  movss   [rbp+3Fh+var_98], xmm3
0x18009c4fb  movss   [rbp+3Fh+var_94], xmm4
0x18009c500  jmp     loc_18009C47E
0x18009c505  movss   xmm7, dword ptr [r9]
0x18009c50a  mov     dil, cs:?Feature_GdiPlusOptimizations_Misc_IsEnabled@@3_NA; bool Feature_GdiPlusOptimizations_Misc_IsEnabled
0x18009c511  movaps  xmm1, xmm7
0x18009c514  addss   xmm1, cs:__real@3f000000
0x18009c51c  test    dil, dil
0x18009c51f  jnz     loc_18009C668
0x18009c525  cvtps2pd xmm0, xmm1; X
0x18009c528  call    floor
0x18009c52d  cvttsd2si r12d, xmm0
0x18009c532  movss   xmm6, dword ptr [rbx+4]
0x18009c537  mov     dword ptr [rbp+3Fh+var_78], r12d
0x18009c53b  movaps  xmm1, xmm6
0x18009c53e  addss   xmm1, cs:__real@3f000000
0x18009c546  test    dil, dil
0x18009c549  jnz     loc_18009C67B
0x18009c54f  cvtps2pd xmm0, xmm1; X
0x18009c552  call    floor
0x18009c557  cvttsd2si r15d, xmm0
0x18009c55c  mov     dword ptr [rbp+3Fh+var_78+4], r15d
0x18009c560  addss   xmm7, dword ptr [rbx+8]
0x18009c565  addss   xmm7, cs:__real@3f000000
0x18009c56d  test    dil, dil
0x18009c570  jnz     loc_18009C68E
0x18009c576  cvtps2pd xmm0, xmm7; X
0x18009c579  call    floor
0x18009c57e  cvttsd2si r14d, xmm0
0x18009c583  mov     dword ptr [rbp+3Fh+var_78+8], r14d
0x18009c587  addss   xmm6, dword ptr [rbx+0Ch]
0x18009c58c  addss   xmm6, cs:__real@3f000000
0x18009c594  test    dil, dil
0x18009c597  jnz     loc_18009C6A1
0x18009c59d  cvtps2pd xmm0, xmm6; X
0x18009c5a0  call    floor
0x18009c5a5  cvttsd2si eax, xmm0
0x18009c5a9  mov     dword ptr [rbp+3Fh+var_78+0Ch], eax
0x18009c5ac  cmp     r12d, r14d
0x18009c5af  jg      loc_18009C4AE
0x18009c5b5  cmp     r15d, eax
0x18009c5b8  jg      loc_18009C4AE
0x18009c5be  jmp     loc_18009C33A
0x18009c5c3  mov     r12, [rbp+3Fh+var_80]
0x18009c5c7  lea     rdx, [rbp+3Fh+var_A0]
0x18009c5cb  xor     ecx, ecx
0x18009c5cd  mov     [rsp+0F0h+var_B0], r12
0x18009c5d2  mov     [rsp+0F0h+var_C0], rdx
0x18009c5d7  test    r14, r14
0x18009c5da  mov     r14d, [rbp+3Fh+var_90]
0x18009c5de  lea     rdx, [rbp+3Fh+var_88]
0x18009c5e2  setnz   cl
0x18009c5e5  mov     [rsp+0F0h+var_C8], rdx
0x18009c5ea  mov     dword ptr [rsp+0F0h+var_D0], ecx
0x18009c5ee  mov     r9, rdi
0x18009c5f1  mov     rcx, rax
0x18009c5f4  mov     r8d, r14d
0x18009c5f7  mov     rdx, rsi
0x18009c5fa  call    ??0MetafileRecorder@@QEAA@PEAVGpMetafile@@W4EmfType@@PEAUHDC__@@HAEAUtagSIZE@@AEAVRectF@@K0@Z; MetafileRecorder::MetafileRecorder(GpMetafile *,EmfType,HDC__ *,int,tagSIZE &,RectF &,ulong,GpMetafile *)
0x18009c5ff  mov     rbx, rax
0x18009c602  test    rax, rax
0x18009c605  jz      loc_18009C49C
0x18009c60b  cmp     dword ptr [rax+8], 63524D31h
0x18009c612  jnz     short loc_18009C648
0x18009c614  test    r12, r12
0x18009c617  mov     r8, rdi
0x18009c61a  mov     rcx, rax
0x18009c61d  cmovz   r15d, r14d
0x18009c621  mov     edx, r15d
0x18009c624  call    ?GetForMetafile@GpGraphics@@KAPEAV1@PEAVIMetafileRecord@@W4EmfType@@PEAUHDC__@@@Z; GpGraphics::GetForMetafile(IMetafileRecord *,EmfType,HDC__ *)
0x18009c629  mov     [rsi+0D0h], rax
0x18009c630  test    rax, rax
0x18009c633  jz      short loc_18009C660
0x18009c635  cmp     dword ptr [rax+8], 61724731h
0x18009c63c  jnz     short loc_18009C6B3
0x18009c63e  mov     eax, 1
0x18009c643  jmp     loc_18009C4B0
0x18009c648  mov     rcx, [rax]
0x18009c64b  mov     rax, [rcx]
0x18009c64e  mov     edx, 1
0x18009c653  mov     rcx, rbx
0x18009c656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c65b  jmp     loc_18009C49C
0x18009c660  mov     rax, [rbx]
0x18009c663  mov     rax, [rax]
0x18009c666  jmp     short loc_18009C64E
0x18009c668  movaps  xmm0, xmm1
0x18009c66b  roundss xmm0, xmm0, 9
0x18009c671  cvttss2si r12d, xmm0
0x18009c676  jmp     loc_18009C532
0x18009c67b  movaps  xmm0, xmm1
0x18009c67e  roundss xmm0, xmm0, 9
0x18009c684  cvttss2si r15d, xmm0
0x18009c689  jmp     loc_18009C55C
0x18009c68e  movaps  xmm0, xmm7
0x18009c691  roundss xmm0, xmm0, 9
0x18009c697  cvttss2si r14d, xmm0
0x18009c69c  jmp     loc_18009C583
0x18009c6a1  movaps  xmm0, xmm6
0x18009c6a4  roundss xmm0, xmm0, 9
0x18009c6aa  cvttss2si eax, xmm0
0x18009c6ae  jmp     loc_18009C5A9
0x18009c6b3  mov     dword ptr [rbx+8], 4C494146h
0x18009c6ba  mov     rcx, [rsi+0D0h]; this
0x18009c6c1  test    rcx, rcx
0x18009c6c4  jz      short loc_18009C6CB
0x18009c6c6  call    ??_GGpGraphics@@QEAAPEAXI@Z; GpGraphics::`scalar deleting destructor'(uint)
0x18009c6cb  mov     qword ptr [rsi+0D0h], 0
0x18009c6d6  jmp     loc_18009C49C
```
