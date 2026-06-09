# MetafileRecorder::EndRecording(void)

- ea: `0x18009d950`
- end: `0x18009dd7d`
- name: `?EndRecording@MetafileRecorder@@UEAAXXZ`
- size: `1069`
- prototype: `void __fastcall(MetafileRecorder *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update`

## callees

- `0x18004396c`
- `0x18009cfa4`
- `0x18009d950`
- `0x18009de34`
- `0x1800fe680`
- `0x1800fefe0`
- `0x1800ff04c`
- `0x180169010`

## import_xrefs

- `GDI32!GetEnhMetaFileHeader` at `0x18009dac8`
- `GDI32!GetEnhMetaFileHeader` at `0x18009dac8`
- `GDI32!CloseEnhMetaFile` at `0x18009d9fb`
- `GDI32!CloseEnhMetaFile` at `0x18009da96`
- `GDI32!CloseEnhMetaFile` at `0x18009d9fb`
- `GDI32!CloseEnhMetaFile` at `0x18009da96`
- `GDI32!DeleteEnhMetaFile` at `0x18009da9f`
- `GDI32!DeleteEnhMetaFile` at `0x18009dd3b`
- `GDI32!DeleteEnhMetaFile` at `0x18009da9f`
- `GDI32!DeleteEnhMetaFile` at `0x18009dd3b`
- `GDI32!EnumEnhMetaFile` at `0x18009dd2e`
- `GDI32!EnumEnhMetaFile` at `0x18009dd2e`

## pseudocode

```c
void __fastcall MetafileRecorder::EndRecording(MetafileRecorder *this)
{
  int v1; // r14d
  char *v2; // rbx
  __int64 v4; // rcx
  HENHMETAFILE v5; // rsi
  HENHMETAFILE v6; // rcx
  __int64 v7; // r15
  bool v8; // r12
  int v9; // edx
  float v10; // xmm2_4
  float v11; // xmm1_4
  __m128 v12; // xmm7
  __m128 v13; // xmm6
  __m128 v14; // xmm8
  __m128 v15; // xmm1
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // r12d
  int v21; // r15d
  int v22; // esi
  int v23; // eax
  void *v24; // r9
  struct tagENHMETAHEADER EnhMetaHeader; // [rsp+38h] [rbp-69h] BYREF

  v1 = 0;
  v2 = (char *)this + 32;
  if ( *((_DWORD *)this + 2) != 1666338097 || *(_DWORD *)(*(_QWORD *)v2 + 176LL) != 2 )
  {
    v6 = CloseEnhMetaFile(*((HDC *)this + 9));
LABEL_9:
    DeleteEnhMetaFile(v6);
    goto LABEL_7;
  }
  v4 = *((_QWORD *)this + 3);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 144LL))(v4);
    if ( *((_DWORD *)this + 15) )
    {
      v20 = RasterizerCeiling(*((float *)this + 11));
      v21 = RasterizerCeiling(*((float *)this + 12));
      v22 = RasterizerCeiling(*((float *)this + 13));
      v23 = RasterizerCeiling(*((float *)this + 14));
      if ( v22 > v20 && v23 > v21 )
        GpGraphics::NoOpPatBlt(*(GpGraphics **)(*(_QWORD *)v2 + 208LL), v20, v21, v22 - v20, v23 - v21);
    }
    (*(void (__fastcall **)(MetafileRecorder *))(*(_QWORD *)this + 416LL))(this);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 144LL))(*((_QWORD *)this + 3));
  }
  v5 = CloseEnhMetaFile(*((HDC *)this + 9));
  if ( !v5 )
    goto LABEL_7;
  memset_0(&EnhMetaHeader, 0, 0x58u);
  if ( !GetEnhMetaFileHeader(v5, 0x58u, &EnhMetaHeader)
    || !(unsigned int)EmfHeaderIsValid((struct ENHMETAHEADER3 *)&EnhMetaHeader) )
  {
    v6 = v5;
    goto LABEL_9;
  }
  v7 = *(_QWORD *)v2;
  v8 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
  v9 = *(_DWORD *)(*(_QWORD *)v2 + 44LL);
  *(_QWORD *)(v7 + 184) = v5;
  *(_DWORD *)(*(_QWORD *)v2 + 224LL) = *((_DWORD *)this + 17);
  v10 = *(float *)(v7 + 48) / 2540.0;
  *(_DWORD *)(v7 + 44) = v9;
  *(_OWORD *)(v7 + 72) = *(_OWORD *)&EnhMetaHeader.iType;
  *(_OWORD *)(v7 + 88) = *(_OWORD *)&EnhMetaHeader.rclBounds.right;
  *(_OWORD *)(v7 + 104) = *(_OWORD *)&EnhMetaHeader.rclFrame.right;
  *(_OWORD *)(v7 + 120) = *(_OWORD *)&EnhMetaHeader.nBytes;
  *(_OWORD *)(v7 + 136) = *(_OWORD *)&EnhMetaHeader.offDescription;
  *(SIZEL *)(v7 + 152) = EnhMetaHeader.szlMillimeters;
  v11 = *(float *)(v7 + 52) / 2540.0;
  *(_DWORD *)(v7 + 36) = EnhMetaHeader.nBytes;
  v12 = (__m128)COERCE_UNSIGNED_INT((float)(EnhMetaHeader.rclFrame.right - EnhMetaHeader.rclFrame.left));
  v13 = (__m128)COERCE_UNSIGNED_INT((float)(EnhMetaHeader.rclFrame.bottom - EnhMetaHeader.rclFrame.top));
  v12.m128_f32[0] = (float)(v12.m128_f32[0] * v10) + 1.0;
  v14 = (__m128)COERCE_UNSIGNED_INT((float)EnhMetaHeader.rclFrame.top);
  v13.m128_f32[0] = (float)(v13.m128_f32[0] * v11) + 1.0;
  v14.m128_f32[0] = v14.m128_f32[0] * v11;
  v15 = (__m128)COERCE_UNSIGNED_INT((float)EnhMetaHeader.rclFrame.left);
  v15.m128_f32[0] = (float)(v15.m128_f32[0] * v10) + 0.5;
  if ( v8 )
    v16 = (int)_mm_round_ss(v15, v15, 9).m128_f32[0];
  else
    v16 = (int)floor(v15.m128_f32[0]);
  *(_DWORD *)(v7 + 56) = v16;
  v14.m128_f32[0] = v14.m128_f32[0] + 0.5;
  if ( v8 )
    v17 = (int)_mm_round_ss(v14, v14, 9).m128_f32[0];
  else
    v17 = (int)floor(v14.m128_f32[0]);
  *(_DWORD *)(v7 + 60) = v17;
  v12.m128_f32[0] = v12.m128_f32[0] + 0.5;
  if ( v8 )
    v18 = (int)_mm_round_ss(v12, v12, 9).m128_f32[0];
  else
    v18 = (int)floor(v12.m128_f32[0]);
  *(_DWORD *)(v7 + 64) = v18;
  v13.m128_f32[0] = v13.m128_f32[0] + 0.5;
  if ( v8 )
    v19 = (int)_mm_round_ss(v13, v13, 9).m128_f32[0];
  else
    v19 = (int)floor(v13.m128_f32[0]);
  *(_DWORD *)(v7 + 68) = v19;
  if ( !*(_QWORD *)(*(_QWORD *)v2 + 192LL) )
  {
    v24 = *(void **)(*(_QWORD *)v2 + 200LL);
    if ( v24 )
    {
      if ( !EnumEnhMetaFile(0, v5, EnumEmfToStream, v24, 0) )
      {
        DeleteEnhMetaFile(v5);
        *(_QWORD *)(*(_QWORD *)v2 + 184LL) = 0;
        goto LABEL_7;
      }
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)v2 + 200LL) + 16LL))(*(_QWORD *)(*(_QWORD *)v2 + 200LL));
      *(_QWORD *)(*(_QWORD *)v2 + 200LL) = 0;
    }
  }
  v1 = 3;
LABEL_7:
  *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v2 + 208LL) + 56LL) = 0;
  *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v2 + 208LL) + 8LL) = 1279869254;
  *(_QWORD *)(*(_QWORD *)v2 + 208LL) = 0;
  *(_DWORD *)(*(_QWORD *)v2 + 176LL) = v1;
  (**(void (__fastcall ***)(MetafileRecorder *, __int64))this)(this, 1);
}

```

## disassembly

```asm
0x18009d950  mov     rax, rsp
0x18009d953  mov     [rax+10h], rbx
0x18009d957  mov     [rax+18h], rsi
0x18009d95b  push    rbp
0x18009d95c  push    rdi
0x18009d95d  push    r12
0x18009d95f  push    r14
0x18009d961  push    r15
0x18009d963  lea     rbp, [rax-5Fh]
0x18009d967  sub     rsp, 0D0h
0x18009d96e  movaps  xmmword ptr [rax-38h], xmm6
0x18009d972  movaps  xmmword ptr [rax-48h], xmm7
0x18009d976  movaps  xmmword ptr [rax-58h], xmm8
0x18009d97b  mov     rax, cs:__security_cookie
0x18009d982  xor     rax, rsp
0x18009d985  mov     qword ptr [rbp+57h+EnhMetaHeader.bOpenGL], rax
0x18009d989  xor     r14d, r14d
0x18009d98c  lea     rbx, [rcx+20h]
0x18009d990  cmp     dword ptr [rcx+8], 63524D31h
0x18009d997  mov     rdi, rcx
0x18009d99a  jnz     loc_18009DA92
0x18009d9a0  mov     rax, [rbx]
0x18009d9a3  cmp     dword ptr [rax+0B0h], 2
0x18009d9aa  jnz     loc_18009DA92
0x18009d9b0  mov     rcx, [rcx+18h]
0x18009d9b4  test    rcx, rcx
0x18009d9b7  jz      short loc_18009D9F7
0x18009d9b9  mov     rax, [rcx]
0x18009d9bc  mov     rax, [rax+90h]
0x18009d9c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d9c8  cmp     [rdi+3Ch], r14d
0x18009d9cc  jnz     loc_18009DC5B
0x18009d9d2  mov     rax, [rdi]
0x18009d9d5  mov     rcx, rdi
0x18009d9d8  mov     rax, [rax+1A0h]
0x18009d9df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d9e4  mov     rcx, [rdi+18h]
0x18009d9e8  mov     rax, [rcx]
0x18009d9eb  mov     rax, [rax+90h]
0x18009d9f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d9f7  mov     rcx, [rdi+48h]; hdc
0x18009d9fb  call    cs:__imp_CloseEnhMetaFile
0x18009da01  mov     rsi, rax
0x18009da04  test    rax, rax
0x18009da07  jnz     loc_18009DAAA
0x18009da0d  mov     rax, [rbx]
0x18009da10  mov     rcx, rdi
0x18009da13  mov     rdx, [rax+0D0h]
0x18009da1a  mov     qword ptr [rdx+38h], 0
0x18009da22  mov     rax, [rbx]
0x18009da25  mov     rdx, [rax+0D0h]
0x18009da2c  mov     dword ptr [rdx+8], 4C494146h
0x18009da33  mov     edx, 1
0x18009da38  mov     rax, [rbx]
0x18009da3b  mov     qword ptr [rax+0D0h], 0
0x18009da46  mov     rax, [rbx]
0x18009da49  mov     [rax+0B0h], r14d
0x18009da50  mov     rax, [rdi]
0x18009da53  mov     rax, [rax]
0x18009da56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009da5b  mov     rcx, qword ptr [rbp+57h+EnhMetaHeader.bOpenGL]
0x18009da5f  xor     rcx, rsp; StackCookie
0x18009da62  call    __security_check_cookie
0x18009da67  lea     r11, [rsp+0F0h+var_20]
0x18009da6f  mov     rbx, [r11+38h]
0x18009da73  mov     rsi, [r11+40h]
0x18009da77  movaps  xmm6, xmmword ptr [r11-10h]
0x18009da7c  movaps  xmm7, xmmword ptr [r11-20h]
0x18009da81  movaps  xmm8, xmmword ptr [r11-30h]
0x18009da86  mov     rsp, r11
0x18009da89  pop     r15
0x18009da8b  pop     r14
0x18009da8d  pop     r12
0x18009da8f  pop     rdi
0x18009da90  pop     rbp
0x18009da91  retn
0x18009da92  mov     rcx, [rcx+48h]; hdc
0x18009da96  call    cs:__imp_CloseEnhMetaFile
0x18009da9c  mov     rcx, rax; hmf
0x18009da9f  call    cs:__imp_DeleteEnhMetaFile
0x18009daa5  jmp     loc_18009DA0D
0x18009daaa  mov     r15d, 58h ; 'X'
0x18009dab0  lea     rcx, [rbp+57h+EnhMetaHeader]; void *
0x18009dab4  mov     r8d, r15d; Size
0x18009dab7  xor     edx, edx; Val
0x18009dab9  call    memset_0
0x18009dabe  lea     r8, [rbp+57h+EnhMetaHeader]; lpEnhMetaHeader
0x18009dac2  mov     edx, r15d; nSize
0x18009dac5  mov     rcx, rsi; hemf
0x18009dac8  call    cs:__imp_GetEnhMetaFileHeader
0x18009dace  test    eax, eax
0x18009dad0  jz      loc_18009DD75
0x18009dad6  lea     rcx, [rbp+57h+EnhMetaHeader]; struct ENHMETAHEADER3 *
0x18009dada  call    ?EmfHeaderIsValid@@YAHAEAUENHMETAHEADER3@@@Z; EmfHeaderIsValid(ENHMETAHEADER3 &)
0x18009dadf  test    eax, eax
0x18009dae1  jz      loc_18009DD75
0x18009dae7  mov     r15, [rbx]
0x18009daea  mov     r12b, cs:?Feature_GdiPlusOptimizations_Misc_IsEnabled@@3_NA; bool Feature_GdiPlusOptimizations_Misc_IsEnabled
0x18009daf1  mov     edx, [r15+2Ch]
0x18009daf5  mov     [r15+0B8h], rsi
0x18009dafc  mov     eax, [rdi+44h]
0x18009daff  mov     rcx, [rbx]
0x18009db02  mov     [rcx+0E0h], eax
0x18009db08  movss   xmm2, dword ptr [r15+30h]
0x18009db0e  divss   xmm2, cs:__real@451ec000
0x18009db16  mov     [r15+2Ch], edx
0x18009db1a  movups  xmm0, xmmword ptr [rbp+57h+EnhMetaHeader.iType]
0x18009db1e  movups  xmmword ptr [r15+48h], xmm0
0x18009db23  movups  xmm1, xmmword ptr [rbp+57h+EnhMetaHeader.rclBounds.right]
0x18009db27  movups  xmmword ptr [r15+58h], xmm1
0x18009db2c  movups  xmm0, xmmword ptr [rbp+57h+EnhMetaHeader.rclFrame.right]
0x18009db30  movups  xmmword ptr [r15+68h], xmm0
0x18009db35  movups  xmm1, xmmword ptr [rbp+57h+EnhMetaHeader.nBytes]
0x18009db39  movups  xmmword ptr [r15+78h], xmm1
0x18009db3e  movups  xmm0, xmmword ptr [rbp+57h+EnhMetaHeader.offDescription]
0x18009db42  movups  xmmword ptr [r15+88h], xmm0
0x18009db4a  movsd   xmm1, qword ptr [rbp+57h+EnhMetaHeader.szlMillimeters.cx]
0x18009db4f  movsd   qword ptr [r15+98h], xmm1
0x18009db58  movss   xmm1, dword ptr [r15+34h]
0x18009db5e  divss   xmm1, cs:__real@451ec000
0x18009db66  mov     eax, [rbp+57h+EnhMetaHeader.nBytes]
0x18009db69  mov     [r15+24h], eax
0x18009db6d  mov     eax, [rbp+57h+EnhMetaHeader.rclFrame.right]
0x18009db70  sub     eax, [rbp+57h+EnhMetaHeader.rclFrame.left]
0x18009db73  movd    xmm8, [rbp+57h+EnhMetaHeader.rclFrame.top]
0x18009db79  movd    xmm7, eax
0x18009db7d  mov     eax, [rbp+57h+EnhMetaHeader.rclFrame.bottom]
0x18009db80  sub     eax, [rbp+57h+EnhMetaHeader.rclFrame.top]
0x18009db83  cvtdq2ps xmm7, xmm7
0x18009db86  movd    xmm6, eax
0x18009db8a  mulss   xmm7, xmm2
0x18009db8e  cvtdq2ps xmm6, xmm6
0x18009db91  addss   xmm7, cs:__real@3f800000
0x18009db99  mulss   xmm6, xmm1
0x18009db9d  cvtdq2ps xmm8, xmm8
0x18009dba1  addss   xmm6, cs:__real@3f800000
0x18009dba9  mulss   xmm8, xmm1
0x18009dbae  movd    xmm1, [rbp+57h+EnhMetaHeader.rclFrame.left]
0x18009dbb3  cvtdq2ps xmm1, xmm1
0x18009dbb6  mulss   xmm1, xmm2
0x18009dbba  addss   xmm1, cs:__real@3f000000
0x18009dbc2  test    r12b, r12b
0x18009dbc5  jnz     loc_18009DCC4
0x18009dbcb  cvtps2pd xmm0, xmm1; X
0x18009dbce  call    floor
0x18009dbd3  cvttsd2si eax, xmm0
0x18009dbd7  mov     [r15+38h], eax
0x18009dbdb  addss   xmm8, cs:__real@3f000000
0x18009dbe4  test    r12b, r12b
0x18009dbe7  jnz     loc_18009DCD6
0x18009dbed  cvtps2pd xmm0, xmm8; X
0x18009dbf1  call    floor
0x18009dbf6  cvttsd2si eax, xmm0
0x18009dbfa  mov     [r15+3Ch], eax
0x18009dbfe  addss   xmm7, cs:__real@3f000000
0x18009dc06  test    r12b, r12b
0x18009dc09  jnz     loc_18009DCE9
0x18009dc0f  cvtps2pd xmm0, xmm7; X
0x18009dc12  call    floor
0x18009dc17  cvttsd2si eax, xmm0
0x18009dc1b  mov     [r15+40h], eax
0x18009dc1f  addss   xmm6, cs:__real@3f000000
0x18009dc27  test    r12b, r12b
0x18009dc2a  jnz     loc_18009DCFB
0x18009dc30  cvtps2pd xmm0, xmm6; X
0x18009dc33  call    floor
0x18009dc38  cvttsd2si eax, xmm0
0x18009dc3c  mov     [r15+44h], eax
0x18009dc40  mov     rax, [rbx]
0x18009dc43  cmp     [rax+0C0h], r14
0x18009dc4a  jz      loc_18009DD0D
0x18009dc50  mov     r14d, 3
0x18009dc56  jmp     loc_18009DA0D
0x18009dc5b  movss   xmm0, dword ptr [rdi+2Ch]; float
0x18009dc60  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x18009dc65  movss   xmm0, dword ptr [rdi+30h]; float
0x18009dc6a  mov     r12d, eax
0x18009dc6d  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x18009dc72  movss   xmm0, dword ptr [rdi+34h]; float
0x18009dc77  mov     r15d, eax
0x18009dc7a  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x18009dc7f  movss   xmm0, dword ptr [rdi+38h]; float
0x18009dc84  mov     esi, eax
0x18009dc86  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x18009dc8b  cmp     esi, r12d
0x18009dc8e  jle     loc_18009D9D2
0x18009dc94  cmp     eax, r15d
0x18009dc97  jle     loc_18009D9D2
0x18009dc9d  mov     rcx, [rbx]
0x18009dca0  sub     esi, r12d
0x18009dca3  sub     eax, r15d
0x18009dca6  mov     r9d, esi; int
0x18009dca9  mov     r8d, r15d; int
0x18009dcac  mov     dword ptr [rsp+0F0h+lpRect], eax; int
0x18009dcb0  mov     edx, r12d; int
0x18009dcb3  mov     rcx, [rcx+0D0h]; this
0x18009dcba  call    ?NoOpPatBlt@GpGraphics@@IEAAXHHHH@Z; GpGraphics::NoOpPatBlt(int,int,int,int)
0x18009dcbf  jmp     loc_18009D9D2
0x18009dcc4  movaps  xmm0, xmm1
0x18009dcc7  roundss xmm0, xmm0, 9
0x18009dccd  cvttss2si eax, xmm0
0x18009dcd1  jmp     loc_18009DBD7
0x18009dcd6  movaps  xmm0, xmm8
0x18009dcda  roundss xmm0, xmm0, 9
0x18009dce0  cvttss2si eax, xmm0
0x18009dce4  jmp     loc_18009DBFA
0x18009dce9  movaps  xmm0, xmm7
0x18009dcec  roundss xmm0, xmm0, 9
0x18009dcf2  cvttss2si eax, xmm0
0x18009dcf6  jmp     loc_18009DC1B
0x18009dcfb  movaps  xmm0, xmm6
0x18009dcfe  roundss xmm0, xmm0, 9
0x18009dd04  cvttss2si eax, xmm0
0x18009dd08  jmp     loc_18009DC3C
0x18009dd0d  mov     r9, [rax+0C8h]; param
0x18009dd14  test    r9, r9
0x18009dd17  jz      loc_18009DC50
0x18009dd1d  lea     r8, EnumEmfToStream; proc
0x18009dd24  mov     [rsp+0F0h+lpRect], r14; lpRect
0x18009dd29  mov     rdx, rsi; hmf
0x18009dd2c  xor     ecx, ecx; hdc
0x18009dd2e  call    cs:__imp_EnumEnhMetaFile
0x18009dd34  test    eax, eax
0x18009dd36  jnz     short loc_18009DD50
0x18009dd38  mov     rcx, rsi; hmf
0x18009dd3b  call    cs:__imp_DeleteEnhMetaFile
0x18009dd41  mov     rax, [rbx]
0x18009dd44  mov     [rax+0B8h], r14
0x18009dd4b  jmp     loc_18009DA0D
0x18009dd50  mov     rax, [rbx]
0x18009dd53  mov     rcx, [rax+0C8h]
0x18009dd5a  mov     rax, [rcx]
0x18009dd5d  mov     rax, [rax+10h]
0x18009dd61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009dd66  mov     rax, [rbx]
0x18009dd69  mov     [rax+0C8h], r14
0x18009dd70  jmp     loc_18009DC50
0x18009dd75  mov     rcx, rsi
0x18009dd78  jmp     loc_18009DA9F
```
