# Gfx::TSpriteUpdate<Gfx::GpImageSpriteStorage,ARC::ConstPixelMap>::Update(Gfx::ITarget::Transaction const &,ARC::ConstPixelMap const &,Math::TVector2<Math::TUnits<float,Math::TUnitsRatioTag<Math::DevicePixels,Math::Inches>>> const &,bool)

- ea: `0x1800beb40`
- end: `0x1800becbb`
- name: `?Update@?$TSpriteUpdate@VGpImageSpriteStorage@Gfx@@VConstPixelMap@ARC@@@Gfx@@QEAAXAEBVTransaction@ITarget@2@AEBVConstPixelMap@ARC@@AEBU?$TVector2@V?$TUnits@MU?$TUnitsRatioTag@UDevicePixels@Math@@UInches@2@@Math@@@Math@@@Math@@_N@Z`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1800bea6c`

## callees

- `0x180055860`
- `0x180062394`
- `0x180064d9c`
- `0x1800b9d00`
- `0x1800ba3e0`
- `0x1800beb40`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800beb8d`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800beb8d`
- `gdiplus!GdipBitmapSetResolution` at `0x1800bec65`
- `gdiplus!GdipBitmapSetResolution` at `0x1800bec65`
- `gdiplus!GdipBitmapUnlockBits` at `0x1800bebce`
- `gdiplus!GdipBitmapUnlockBits` at `0x1800bebce`
- `gdiplus!GdipBitmapLockBits` at `0x1800bec99`
- `gdiplus!GdipBitmapLockBits` at `0x1800bec99`
- `gdiplus!GdipDisposeImage` at `0x1800bec07`
- `gdiplus!GdipDisposeImage` at `0x1800bec07`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x1800bec45`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x1800bec45`

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
0x1800beb40  mov     rax, rsp
0x1800beb43  mov     [rax+8], rbx
0x1800beb47  mov     [rax+18h], rsi
0x1800beb4b  mov     [rax+20h], rdi
0x1800beb4f  mov     [rax+10h], rdx
0x1800beb53  push    rbp
0x1800beb54  push    r14
0x1800beb56  push    r15
0x1800beb58  mov     rbp, rsp
0x1800beb5b  sub     rsp, 50h
0x1800beb5f  mov     rbx, r9
0x1800beb62  mov     rdi, r8
0x1800beb65  mov     r15, rcx
0x1800beb68  mov     [rbp+arg_8], 0
0x1800beb70  mov     ecx, [r8+14h]
0x1800beb74  call    ?SurfaceFormatToGDIPlusPixelFormat@Gfx@@YAHW4SurfaceFormat@ARC@@@Z; Gfx::SurfaceFormatToGDIPlusPixelFormat(ARC::SurfaceFormat)
0x1800beb79  mov     esi, eax
0x1800beb7b  cmp     [rbp+arg_8], 0
0x1800beb80  jz      loc_1800BEC27
0x1800beb86  xor     edx, edx
0x1800beb88  mov     ecx, 1E55E058h
0x1800beb8d  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800beb93  nop
0x1800beb94  cmp     ebx, [rdi+0Ch]
0x1800beb97  jnb     short loc_1800BEBC6
0x1800beb99  mov     ecx, [rdi+14h]
0x1800beb9c  call    ?GetBytesPerPixelForSurfaceFormat@ARC@@YA_KW4SurfaceFormat@1@@Z; ARC::GetBytesPerPixelForSurfaceFormat(ARC::SurfaceFormat)
0x1800beba1  mov     r8d, [rdi+8]
0x1800beba5  imul    r8, rax; Size
0x1800beba9  mov     rdx, rsi; Src
0x1800bebac  mov     rcx, r14; void *
0x1800bebaf  call    memcpy_0
0x1800bebb4  movsxd  rax, dword ptr [rdi+10h]
0x1800bebb8  add     rsi, rax
0x1800bebbb  movsxd  rax, dword ptr [rbp+var_20+8]
0x1800bebbf  add     r14, rax
0x1800bebc2  inc     ebx
0x1800bebc4  jmp     short loc_1800BEB94
0x1800bebc6  lea     rdx, [rbp+var_20]
0x1800bebca  mov     rcx, [rbp+arg_8]
0x1800bebce  call    cs:__imp_GdipBitmapUnlockBits
0x1800bebd4  mov     r9d, 251965Ch
0x1800bebda  mov     ecx, eax
0x1800bebdc  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800bebe1  mov     rdi, [rbp+arg_8]
0x1800bebe5  mov     [rbp+arg_8], 0
0x1800bebed  mov     rbx, [r15+10h]
0x1800bebf1  lea     rcx, [rbx+18h]
0x1800bebf5  call    ?Empty@?$TGpHolder@VGpBitmap@Gdiplus@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGpHolder<Gdiplus::GpBitmap>::Empty(void)
0x1800bebfa  mov     [rbx+18h], rdi
0x1800bebfe  mov     rcx, [rbp+arg_8]
0x1800bec02  test    rcx, rcx
0x1800bec05  jz      short loc_1800BEC0D
0x1800bec07  call    cs:__imp_GdipDisposeImage
0x1800bec0d  lea     r11, [rsp+50h+var_s0]
0x1800bec12  mov     rbx, [r11+20h]
0x1800bec16  mov     rsi, [r11+30h]
0x1800bec1a  mov     rdi, [r11+38h]
0x1800bec1e  mov     rsp, r11
0x1800bec21  pop     r15
0x1800bec23  pop     r14
0x1800bec25  pop     rbp
0x1800bec26  retn
0x1800bec27  lea     rax, [rbp+arg_8]
0x1800bec2b  mov     [rsp+50h+var_28], rax
0x1800bec30  mov     [rsp+50h+var_30], 0
0x1800bec39  mov     r9d, esi
0x1800bec3c  xor     r8d, r8d
0x1800bec3f  mov     edx, [rdi+0Ch]
0x1800bec42  mov     ecx, [rdi+8]
0x1800bec45  call    cs:__imp_GdipCreateBitmapFromScan0
0x1800bec4b  mov     r9d, 2519659h
0x1800bec51  mov     ecx, eax
0x1800bec53  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800bec58  movss   xmm2, dword ptr [rbx+4]
0x1800bec5d  movss   xmm1, dword ptr [rbx]
0x1800bec61  mov     rcx, [rbp+arg_8]
0x1800bec65  call    cs:__imp_GdipBitmapSetResolution
0x1800bec6b  mov     r9d, 251965Ah
0x1800bec71  mov     ecx, eax
0x1800bec73  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800bec78  xorps   xmm0, xmm0
0x1800bec7b  movups  [rbp+var_20], xmm0
0x1800bec7f  movups  [rbp+var_10], xmm0
0x1800bec83  lea     rax, [rbp+var_20]
0x1800bec87  mov     [rsp+50h+var_30], rax
0x1800bec8c  mov     r9d, esi
0x1800bec8f  xor     edx, edx
0x1800bec91  lea     r8d, [rdx+1]
0x1800bec95  mov     rcx, [rbp+arg_8]
0x1800bec99  call    cs:__imp_GdipBitmapLockBits
0x1800bec9f  mov     r9d, 251965Bh
0x1800beca5  mov     ecx, eax
0x1800beca7  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800becac  mov     rsi, [rdi]
0x1800becaf  mov     r14, qword ptr [rbp+var_10]
0x1800becb3  xor     ebx, ebx
0x1800becb5  jmp     loc_1800BEB94
```
