# Gfx::TSpriteUpdate<Gfx::GpImageSpriteStorage,ARC::ConstPixelMap>::Update(Gfx::ITarget::Transaction const &,ARC::ConstPixelMap const &,Math::TVector2<Math::TUnits<float,Math::TUnitsRatioTag<Math::DevicePixels,Math::Inches>>> const &,bool)

- ea: `0x1800e3670`
- end: `0x1800e37eb`
- name: `?Update@?$TSpriteUpdate@VGpImageSpriteStorage@Gfx@@VConstPixelMap@ARC@@@Gfx@@QEAAXAEBVTransaction@ITarget@2@AEBVConstPixelMap@ARC@@AEBU?$TVector2@V?$TUnits@MU?$TUnitsRatioTag@UDevicePixels@Math@@UInches@2@@Math@@@Math@@@Math@@_N@Z`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180153340`

## callees

- `0x180056300`
- `0x18007f754`
- `0x180082aac`
- `0x1800e3068`
- `0x1800e318c`
- `0x1800e3670`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800e36bd`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800e36bd`
- `gdiplus!GdipBitmapSetResolution` at `0x1800e3795`
- `gdiplus!GdipBitmapSetResolution` at `0x1800e3795`
- `gdiplus!GdipBitmapUnlockBits` at `0x1800e36fe`
- `gdiplus!GdipBitmapUnlockBits` at `0x1800e36fe`
- `gdiplus!GdipBitmapLockBits` at `0x1800e37c9`
- `gdiplus!GdipBitmapLockBits` at `0x1800e37c9`
- `gdiplus!GdipDisposeImage` at `0x1800e3737`
- `gdiplus!GdipDisposeImage` at `0x1800e3737`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x1800e3775`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x1800e3775`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Gfx::TSpriteUpdate<Gfx::GpImageSpriteStorage,ARC::ConstPixelMap>::Update(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4)
{
  char *v4; // r14
  unsigned __int64 v8; // rsi
  __int64 BytesPerPixelForSurfaceFormat; // rax
  unsigned int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rdi
  __int64 v14; // rbx
  __int64 result; // rax
  unsigned int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // r8
  unsigned int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // r8
  unsigned int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // r8
  __int128 v25; // [rsp+30h] [rbp-20h] BYREF
  __int128 v26; // [rsp+40h] [rbp-10h]
  __int64 v27; // [rsp+78h] [rbp+28h] BYREF

  v27 = 0;
  v8 = (unsigned int)Gfx::SurfaceFormatToGDIPlusPixelFormat(*(unsigned int *)(a3 + 20));
  if ( v27 )
  {
    CrashWithRecovery(0x1E55E058u, 0);
  }
  else
  {
    v16 = GdipCreateBitmapFromScan0(*(unsigned int *)(a3 + 8), *(unsigned int *)(a3 + 12), 0, (unsigned int)v8, 0, &v27);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(v16, v17, v18, 38901337);
    v19 = GdipBitmapSetResolution(v27);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(v19, v20, v21, 38901338);
    v25 = 0;
    v26 = 0;
    v22 = GdipBitmapLockBits(v27, 0, 1, (unsigned int)v8, &v25);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(v22, v23, v24, 38901339);
    v8 = *(_QWORD *)a3;
    v4 = (char *)v26;
    a4 = 0;
  }
  while ( a4 < *(_DWORD *)(a3 + 12) )
  {
    BytesPerPixelForSurfaceFormat = ARC::GetBytesPerPixelForSurfaceFormat(*(unsigned int *)(a3 + 20));
    memcpy_0(v4, (const void *)v8, BytesPerPixelForSurfaceFormat * *(unsigned int *)(a3 + 8));
    v8 += *(int *)(a3 + 16);
    v4 += SDWORD2(v25);
    ++a4;
  }
  v10 = GdipBitmapUnlockBits(v27, &v25);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(v10, v11, v12, 38901340);
  v13 = v27;
  v27 = 0;
  v14 = *(_QWORD *)(a1 + 16);
  result = ARC::GDIPlus::TGpHolder<Gdiplus::GpBitmap>::Empty(v14 + 24);
  *(_QWORD *)(v14 + 24) = v13;
  if ( v27 )
    return GdipDisposeImage();
  return result;
}

```

## disassembly

```asm
0x1800e3670  mov     rax, rsp
0x1800e3673  mov     [rax+8], rbx
0x1800e3677  mov     [rax+18h], rsi
0x1800e367b  mov     [rax+20h], rdi
0x1800e367f  mov     [rax+10h], rdx
0x1800e3683  push    rbp
0x1800e3684  push    r14
0x1800e3686  push    r15
0x1800e3688  mov     rbp, rsp
0x1800e368b  sub     rsp, 50h
0x1800e368f  mov     rbx, r9
0x1800e3692  mov     rdi, r8
0x1800e3695  mov     r15, rcx
0x1800e3698  mov     [rbp+arg_8], 0
0x1800e36a0  mov     ecx, [r8+14h]
0x1800e36a4  call    ?SurfaceFormatToGDIPlusPixelFormat@Gfx@@YAHW4SurfaceFormat@ARC@@@Z; Gfx::SurfaceFormatToGDIPlusPixelFormat(ARC::SurfaceFormat)
0x1800e36a9  mov     esi, eax
0x1800e36ab  cmp     [rbp+arg_8], 0
0x1800e36b0  jz      loc_1800E3757
0x1800e36b6  xor     edx, edx
0x1800e36b8  mov     ecx, 1E55E058h
0x1800e36bd  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800e36c3  nop
0x1800e36c4  cmp     ebx, [rdi+0Ch]
0x1800e36c7  jnb     short loc_1800E36F6
0x1800e36c9  mov     ecx, [rdi+14h]
0x1800e36cc  call    ?GetBytesPerPixelForSurfaceFormat@ARC@@YA_KW4SurfaceFormat@1@@Z; ARC::GetBytesPerPixelForSurfaceFormat(ARC::SurfaceFormat)
0x1800e36d1  mov     r8d, [rdi+8]
0x1800e36d5  imul    r8, rax; Size
0x1800e36d9  mov     rdx, rsi; Src
0x1800e36dc  mov     rcx, r14; void *
0x1800e36df  call    memcpy_0
0x1800e36e4  movsxd  rax, dword ptr [rdi+10h]
0x1800e36e8  add     rsi, rax
0x1800e36eb  movsxd  rax, dword ptr [rbp+var_20+8]
0x1800e36ef  add     r14, rax
0x1800e36f2  inc     ebx
0x1800e36f4  jmp     short loc_1800E36C4
0x1800e36f6  lea     rdx, [rbp+var_20]
0x1800e36fa  mov     rcx, [rbp+arg_8]
0x1800e36fe  call    cs:__imp_GdipBitmapUnlockBits
0x1800e3704  mov     r9d, 251965Ch
0x1800e370a  mov     ecx, eax
0x1800e370c  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800e3711  mov     rdi, [rbp+arg_8]
0x1800e3715  mov     [rbp+arg_8], 0
0x1800e371d  mov     rbx, [r15+10h]
0x1800e3721  lea     rcx, [rbx+18h]
0x1800e3725  call    ?Empty@?$TGpHolder@VGpBitmap@Gdiplus@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGpHolder<Gdiplus::GpBitmap>::Empty(void)
0x1800e372a  mov     [rbx+18h], rdi
0x1800e372e  mov     rcx, [rbp+arg_8]
0x1800e3732  test    rcx, rcx
0x1800e3735  jz      short loc_1800E373D
0x1800e3737  call    cs:__imp_GdipDisposeImage
0x1800e373d  lea     r11, [rsp+50h+var_s0]
0x1800e3742  mov     rbx, [r11+20h]
0x1800e3746  mov     rsi, [r11+30h]
0x1800e374a  mov     rdi, [r11+38h]
0x1800e374e  mov     rsp, r11
0x1800e3751  pop     r15
0x1800e3753  pop     r14
0x1800e3755  pop     rbp
0x1800e3756  retn
0x1800e3757  lea     rax, [rbp+arg_8]
0x1800e375b  mov     [rsp+50h+var_28], rax
0x1800e3760  mov     [rsp+50h+var_30], 0
0x1800e3769  mov     r9d, esi
0x1800e376c  xor     r8d, r8d
0x1800e376f  mov     edx, [rdi+0Ch]
0x1800e3772  mov     ecx, [rdi+8]
0x1800e3775  call    cs:__imp_GdipCreateBitmapFromScan0
0x1800e377b  mov     r9d, 2519659h
0x1800e3781  mov     ecx, eax
0x1800e3783  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800e3788  movss   xmm2, dword ptr [rbx+4]
0x1800e378d  movss   xmm1, dword ptr [rbx]
0x1800e3791  mov     rcx, [rbp+arg_8]
0x1800e3795  call    cs:__imp_GdipBitmapSetResolution
0x1800e379b  mov     r9d, 251965Ah
0x1800e37a1  mov     ecx, eax
0x1800e37a3  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800e37a8  xorps   xmm0, xmm0
0x1800e37ab  movups  [rbp+var_20], xmm0
0x1800e37af  movups  [rbp+var_10], xmm0
0x1800e37b3  lea     rax, [rbp+var_20]
0x1800e37b7  mov     [rsp+50h+var_30], rax
0x1800e37bc  mov     r9d, esi
0x1800e37bf  xor     edx, edx
0x1800e37c1  lea     r8d, [rdx+1]
0x1800e37c5  mov     rcx, [rbp+arg_8]
0x1800e37c9  call    cs:__imp_GdipBitmapLockBits
0x1800e37cf  mov     r9d, 251965Bh
0x1800e37d5  mov     ecx, eax
0x1800e37d7  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800e37dc  mov     rsi, [rdi]
0x1800e37df  mov     r14, qword ptr [rbp+var_10]
0x1800e37e3  xor     ebx, ebx
0x1800e37e5  jmp     loc_1800E36C4
```
