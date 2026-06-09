# Gfx::TSpriteUpdate<Gfx::GpImageSpriteStorage,ARC::IPlatformPixelMapSurface>::Update(Gfx::ITarget::Transaction const &,ARC::IPlatformPixelMapSurface &,bool)

- ea: `0x1800e2e5c`
- end: `0x1800e3068`
- name: `?Update@?$TSpriteUpdate@VGpImageSpriteStorage@Gfx@@UIPlatformPixelMapSurface@ARC@@@Gfx@@QEAAXAEBVTransaction@ITarget@2@AEAUIPlatformPixelMapSurface@ARC@@_N@Z`
- size: `524`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x180167ac0`
- `0x18017fab0`

## callees

- `0x180056300`
- `0x180057e70`
- `0x18007f754`
- `0x180082aac`
- `0x1800e2e5c`
- `0x1800e3068`
- `0x1800e318c`
- `0x1800e3420`
- `0x1800e34f0`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800e2ee3`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800e2ee3`
- `gdiplus!GdipBitmapSetResolution` at `0x1800e2f2d`
- `gdiplus!GdipBitmapSetResolution` at `0x1800e2f2d`
- `gdiplus!GdipBitmapUnlockBits` at `0x1800e2fc4`
- `gdiplus!GdipBitmapUnlockBits` at `0x1800e2fc4`
- `gdiplus!GdipBitmapLockBits` at `0x1800e2f61`
- `gdiplus!GdipBitmapLockBits` at `0x1800e2f61`
- `gdiplus!GdipDisposeImage` at `0x1800e300e`
- `gdiplus!GdipDisposeImage` at `0x1800e300e`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x1800e2f03`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x1800e2f03`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Gfx::TSpriteUpdate<Gfx::GpImageSpriteStorage,ARC::IPlatformPixelMapSurface>::Update(
        __int64 a1,
        __int64 a2,
        const struct ARC::IPlatformPixelMapSurface *a3)
{
  unsigned int v5; // r12d
  __int64 v6; // rdi
  unsigned int v7; // esi
  unsigned int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  char v11; // r9
  unsigned int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  unsigned int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r15
  char *v19; // rsi
  char *v20; // r14
  int i; // ebx
  __int64 BytesPerPixelForSurfaceFormat; // rax
  unsigned int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // rdi
  __int64 v27; // rbx
  __int64 result; // rax
  _QWORD v29[3]; // [rsp+40h] [rbp-39h] BYREF
  int v30; // [rsp+58h] [rbp-21h]
  __int16 v31; // [rsp+5Ch] [rbp-1Dh]
  __int128 v32; // [rsp+60h] [rbp-19h] BYREF
  void *v33[2]; // [rsp+70h] [rbp-9h]
  void *Src; // [rsp+80h] [rbp+7h] BYREF
  int v35; // [rsp+90h] [rbp+17h]
  __int64 v36; // [rsp+98h] [rbp+1Fh]
  __int64 v37; // [rsp+E8h] [rbp+6Fh] BYREF
  int v38; // [rsp+F0h] [rbp+77h] BYREF

  v37 = 0;
  v5 = (*(__int64 (__fastcall **)(const struct ARC::IPlatformPixelMapSurface *))(*(_QWORD *)a3 + 56LL))(a3);
  v6 = *(_QWORD *)(*(__int64 (__fastcall **)(const struct ARC::IPlatformPixelMapSurface *, _QWORD *))(*(_QWORD *)a3 + 24LL))(
                    a3,
                    v29);
  v29[0] = v6;
  (*(void (__fastcall **)(const struct ARC::IPlatformPixelMapSurface *, int *))(*(_QWORD *)a3 + 32LL))(a3, &v38);
  v7 = Gfx::SurfaceFormatToGDIPlusPixelFormat(v5);
  if ( v37 )
    CrashWithRecovery(0x1E55E058u, 0);
  v8 = GdipCreateBitmapFromScan0((unsigned int)v6, HIDWORD(v29[0]), 0, v7, 0, &v37);
  if ( v8 == 2 )
  {
    v29[1] = &Mso::Logging::StructuredObject<unsigned int,1>::`vftable';
    v29[2] = L"GdipStatus";
    v30 = 3;
    v31 = 0;
    OExceptionLog::ThrowTagVariableArguments<Mso::Logging::StructuredObject<unsigned int,1>>(558458782, v9, 3, v11);
  }
  Gfx::GdipStatus_ThrowOnFailureMessageTag(v8, v9, v10, 38901341);
  v12 = GdipBitmapSetResolution(v37);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(v12, v13, v14, 38901342);
  v32 = 0;
  *(_OWORD *)v33 = 0;
  v15 = GdipBitmapLockBits(v37, 0, 1, v7, &v32);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(v15, v16, v17, 38901343);
  ARC::IPlatformPixelMapSurface::ReadLock::ReadLock((ARC::IPlatformPixelMapSurface::ReadLock *)&Src, a3);
  v18 = v35;
  v19 = (char *)Src;
  v20 = (char *)v33[0];
  for ( i = 0; i < SHIDWORD(v29[0]); ++i )
  {
    BytesPerPixelForSurfaceFormat = ARC::GetBytesPerPixelForSurfaceFormat(v5);
    memcpy_0(v20, v19, BytesPerPixelForSurfaceFormat * (int)v6);
    v19 += v18;
    v20 += SDWORD2(v32);
  }
  v23 = GdipBitmapUnlockBits(v37, &v32);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(v23, v24, v25, 38901344);
  v26 = v37;
  v37 = 0;
  v27 = *(_QWORD *)(a1 + 16);
  ARC::GDIPlus::TGpHolder<Gdiplus::GpBitmap>::Empty(v27 + 24);
  *(_QWORD *)(v27 + 24) = v26;
  result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v36 + 8LL))(v36);
  if ( v37 )
    return GdipDisposeImage();
  return result;
}

```

## disassembly

```asm
0x1800e2e5c  mov     [rsp-8+arg_0], rbx
0x1800e2e61  mov     [rsp-8+arg_8], rdx
0x1800e2e66  push    rbp
0x1800e2e67  push    rsi
0x1800e2e68  push    rdi
0x1800e2e69  push    r12
0x1800e2e6b  push    r13
0x1800e2e6d  push    r14
0x1800e2e6f  push    r15
0x1800e2e71  lea     rbp, [rsp-27h]
0x1800e2e76  sub     rsp, 0A0h
0x1800e2e7d  mov     rbx, r8
0x1800e2e80  mov     r13, rcx
0x1800e2e83  xor     r14d, r14d
0x1800e2e86  mov     [rbp+57h+arg_8], r14
0x1800e2e8a  mov     rax, [r8]
0x1800e2e8d  mov     rcx, r8
0x1800e2e90  mov     rax, [rax+38h]
0x1800e2e94  call    cs:__guard_dispatch_icall_fptr
0x1800e2e9a  mov     r12d, eax
0x1800e2e9d  mov     rdx, [rbx]
0x1800e2ea0  mov     rax, [rdx+18h]
0x1800e2ea4  lea     rdx, [rbp+57h+var_90]
0x1800e2ea8  mov     rcx, rbx
0x1800e2eab  call    cs:__guard_dispatch_icall_fptr
0x1800e2eb1  mov     rdi, [rax]
0x1800e2eb4  mov     [rbp+57h+var_90], rdi
0x1800e2eb8  mov     rcx, [rbx]
0x1800e2ebb  mov     rax, [rcx+20h]
0x1800e2ebf  lea     rdx, [rbp+57h+arg_10]
0x1800e2ec3  mov     rcx, rbx
0x1800e2ec6  call    cs:__guard_dispatch_icall_fptr
0x1800e2ecc  mov     ecx, r12d
0x1800e2ecf  call    ?SurfaceFormatToGDIPlusPixelFormat@Gfx@@YAHW4SurfaceFormat@ARC@@@Z; Gfx::SurfaceFormatToGDIPlusPixelFormat(ARC::SurfaceFormat)
0x1800e2ed4  mov     esi, eax
0x1800e2ed6  cmp     [rbp+57h+arg_8], r14
0x1800e2eda  jz      short loc_1800E2EEA
0x1800e2edc  xor     edx, edx
0x1800e2ede  mov     ecx, 1E55E058h
0x1800e2ee3  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800e2ee9  nop
0x1800e2eea  lea     rax, [rbp+57h+arg_8]
0x1800e2eee  mov     [rsp+0D0h+var_A8], rax
0x1800e2ef3  mov     [rsp+0D0h+var_B0], r14
0x1800e2ef8  mov     r9d, esi
0x1800e2efb  xor     r8d, r8d
0x1800e2efe  mov     edx, dword ptr [rbp+57h+var_90+4]
0x1800e2f01  mov     ecx, edi
0x1800e2f03  call    cs:__imp_GdipCreateBitmapFromScan0
0x1800e2f09  cmp     eax, 2
0x1800e2f0c  jz      loc_1800E302F
0x1800e2f12  mov     r9d, 251965Dh
0x1800e2f18  mov     ecx, eax
0x1800e2f1a  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800e2f1f  movss   xmm2, [rbp+57h+arg_14]
0x1800e2f24  movss   xmm1, [rbp+57h+arg_10]
0x1800e2f29  mov     rcx, [rbp+57h+arg_8]
0x1800e2f2d  call    cs:__imp_GdipBitmapSetResolution
0x1800e2f33  mov     r9d, 251965Eh
0x1800e2f39  mov     ecx, eax
0x1800e2f3b  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800e2f40  xorps   xmm0, xmm0
0x1800e2f43  movups  [rbp+57h+var_70], xmm0
0x1800e2f47  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x1800e2f4b  lea     rax, [rbp+57h+var_70]
0x1800e2f4f  mov     [rsp+0D0h+var_B0], rax
0x1800e2f54  mov     r9d, esi
0x1800e2f57  xor     edx, edx
0x1800e2f59  lea     r8d, [rdx+1]
0x1800e2f5d  mov     rcx, [rbp+57h+arg_8]
0x1800e2f61  call    cs:__imp_GdipBitmapLockBits
0x1800e2f67  mov     r9d, 251965Fh
0x1800e2f6d  mov     ecx, eax
0x1800e2f6f  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800e2f74  mov     rdx, rbx; struct ARC::IPlatformPixelMapSurface *
0x1800e2f77  lea     rcx, [rbp+57h+Src]; this
0x1800e2f7b  call    ??0ReadLock@IPlatformPixelMapSurface@ARC@@QEAA@AEBU12@@Z; ARC::IPlatformPixelMapSurface::ReadLock::ReadLock(ARC::IPlatformPixelMapSurface const &)
0x1800e2f80  nop
0x1800e2f81  movsxd  r15, [rbp+57h+var_40]
0x1800e2f85  mov     rsi, [rbp+57h+Src]
0x1800e2f89  mov     r14, [rbp+57h+var_60]
0x1800e2f8d  xor     ebx, ebx
0x1800e2f8f  cmp     ebx, dword ptr [rbp+57h+var_90+4]
0x1800e2f92  jge     short loc_1800E2FBC
0x1800e2f94  mov     ecx, r12d
0x1800e2f97  call    ?GetBytesPerPixelForSurfaceFormat@ARC@@YA_KW4SurfaceFormat@1@@Z; ARC::GetBytesPerPixelForSurfaceFormat(ARC::SurfaceFormat)
0x1800e2f9c  movsxd  r8, edi
0x1800e2f9f  imul    r8, rax; Size
0x1800e2fa3  mov     rdx, rsi; Src
0x1800e2fa6  mov     rcx, r14; void *
0x1800e2fa9  call    memcpy_0
0x1800e2fae  add     rsi, r15
0x1800e2fb1  movsxd  rax, dword ptr [rbp+57h+var_70+8]
0x1800e2fb5  add     r14, rax
0x1800e2fb8  inc     ebx
0x1800e2fba  jmp     short loc_1800E2F8F
0x1800e2fbc  lea     rdx, [rbp+57h+var_70]
0x1800e2fc0  mov     rcx, [rbp+57h+arg_8]
0x1800e2fc4  call    cs:__imp_GdipBitmapUnlockBits
0x1800e2fca  mov     r9d, 2519660h
0x1800e2fd0  mov     ecx, eax
0x1800e2fd2  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800e2fd7  mov     rdi, [rbp+57h+arg_8]
0x1800e2fdb  mov     [rbp+57h+arg_8], 0
0x1800e2fe3  mov     rbx, [r13+10h]
0x1800e2fe7  lea     rcx, [rbx+18h]
0x1800e2feb  call    ?Empty@?$TGpHolder@VGpBitmap@Gdiplus@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGpHolder<Gdiplus::GpBitmap>::Empty(void)
0x1800e2ff0  mov     [rbx+18h], rdi
0x1800e2ff4  mov     rcx, [rbp+57h+var_38]
0x1800e2ff8  mov     rax, [rcx]
0x1800e2ffb  mov     rax, [rax+8]
0x1800e2fff  call    cs:__guard_dispatch_icall_fptr
0x1800e3005  mov     rcx, [rbp+57h+arg_8]
0x1800e3009  test    rcx, rcx
0x1800e300c  jz      short loc_1800E3014
0x1800e300e  call    cs:__imp_GdipDisposeImage
0x1800e3014  mov     rbx, [rsp+0D0h+arg_0]
0x1800e301c  add     rsp, 0A0h
0x1800e3023  pop     r15
0x1800e3025  pop     r14
0x1800e3027  pop     r13
0x1800e3029  pop     r12
0x1800e302b  pop     rdi
0x1800e302c  pop     rsi
0x1800e302d  pop     rbp
0x1800e302e  retn
0x1800e302f  lea     rax, ??_7?$StructuredObject@I$00@Logging@Mso@@6B@; const Mso::Logging::StructuredObject<uint,1>::`vftable'
0x1800e3036  mov     [rbp+57h+var_88], rax
0x1800e303a  lea     rax, aGdipstatus; "GdipStatus"
0x1800e3041  mov     [rbp+57h+var_80], rax
0x1800e3045  mov     r8d, 3
0x1800e304b  mov     [rbp+57h+var_78], r8d
0x1800e304f  mov     [rbp+57h+var_74], r14w
0x1800e3054  lea     rax, [rbp+57h+var_88]
0x1800e3058  mov     [rsp+0D0h+var_A0], rax
0x1800e305d  mov     ecx, 2149679Eh
0x1800e3062  call    ??$ThrowTagVariableArguments@U?$StructuredObject@I$00@Logging@Mso@@@OExceptionLog@@YAXKW4exceptionType@et@@JPEB_WW4Category@Logging@Mso@@W4Severity@45@$$QEAU?$StructuredObject@I$00@45@@Z; OExceptionLog::ThrowTagVariableArguments<Mso::Logging::StructuredObject<uint,1>>(ulong,et::exceptionType,long,wchar_t const *,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::StructuredObject<uint,1> &&)
```
