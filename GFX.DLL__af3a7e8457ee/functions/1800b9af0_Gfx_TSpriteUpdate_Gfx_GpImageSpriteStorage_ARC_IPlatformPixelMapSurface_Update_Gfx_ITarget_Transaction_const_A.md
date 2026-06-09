# Gfx::TSpriteUpdate<Gfx::GpImageSpriteStorage,ARC::IPlatformPixelMapSurface>::Update(Gfx::ITarget::Transaction const &,ARC::IPlatformPixelMapSurface &,bool)

- ea: `0x1800b9af0`
- end: `0x1800b9cfc`
- name: `?Update@?$TSpriteUpdate@VGpImageSpriteStorage@Gfx@@UIPlatformPixelMapSurface@ARC@@@Gfx@@QEAAXAEBVTransaction@ITarget@2@AEAUIPlatformPixelMapSurface@ARC@@_N@Z`
- size: `524`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x180164100`
- `0x18017b480`

## callees

- `0x180055860`
- `0x1800573f0`
- `0x180062394`
- `0x180064d9c`
- `0x180091bd0`
- `0x1800b9af0`
- `0x1800b9d00`
- `0x1800ba3e0`
- `0x18017d458`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800b9b77`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800b9b77`
- `gdiplus!GdipBitmapSetResolution` at `0x1800b9bc1`
- `gdiplus!GdipBitmapSetResolution` at `0x1800b9bc1`
- `gdiplus!GdipBitmapUnlockBits` at `0x1800b9c58`
- `gdiplus!GdipBitmapUnlockBits` at `0x1800b9c58`
- `gdiplus!GdipBitmapLockBits` at `0x1800b9bf5`
- `gdiplus!GdipBitmapLockBits` at `0x1800b9bf5`
- `gdiplus!GdipDisposeImage` at `0x1800b9ca2`
- `gdiplus!GdipDisposeImage` at `0x1800b9ca2`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x1800b9b97`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x1800b9b97`

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
0x1800b9af0  mov     [rsp-8+arg_0], rbx
0x1800b9af5  mov     [rsp-8+arg_8], rdx
0x1800b9afa  push    rbp
0x1800b9afb  push    rsi
0x1800b9afc  push    rdi
0x1800b9afd  push    r12
0x1800b9aff  push    r13
0x1800b9b01  push    r14
0x1800b9b03  push    r15
0x1800b9b05  lea     rbp, [rsp-27h]
0x1800b9b0a  sub     rsp, 0A0h
0x1800b9b11  mov     rbx, r8
0x1800b9b14  mov     r13, rcx
0x1800b9b17  xor     r14d, r14d
0x1800b9b1a  mov     [rbp+57h+arg_8], r14
0x1800b9b1e  mov     rax, [r8]
0x1800b9b21  mov     rcx, r8
0x1800b9b24  mov     rax, [rax+38h]
0x1800b9b28  call    cs:__guard_dispatch_icall_fptr
0x1800b9b2e  mov     r12d, eax
0x1800b9b31  mov     rdx, [rbx]
0x1800b9b34  mov     rax, [rdx+18h]
0x1800b9b38  lea     rdx, [rbp+57h+var_90]
0x1800b9b3c  mov     rcx, rbx
0x1800b9b3f  call    cs:__guard_dispatch_icall_fptr
0x1800b9b45  mov     rdi, [rax]
0x1800b9b48  mov     [rbp+57h+var_90], rdi
0x1800b9b4c  mov     rcx, [rbx]
0x1800b9b4f  mov     rax, [rcx+20h]
0x1800b9b53  lea     rdx, [rbp+57h+arg_10]
0x1800b9b57  mov     rcx, rbx
0x1800b9b5a  call    cs:__guard_dispatch_icall_fptr
0x1800b9b60  mov     ecx, r12d
0x1800b9b63  call    ?SurfaceFormatToGDIPlusPixelFormat@Gfx@@YAHW4SurfaceFormat@ARC@@@Z; Gfx::SurfaceFormatToGDIPlusPixelFormat(ARC::SurfaceFormat)
0x1800b9b68  mov     esi, eax
0x1800b9b6a  cmp     [rbp+57h+arg_8], r14
0x1800b9b6e  jz      short loc_1800B9B7E
0x1800b9b70  xor     edx, edx
0x1800b9b72  mov     ecx, 1E55E058h
0x1800b9b77  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800b9b7d  nop
0x1800b9b7e  lea     rax, [rbp+57h+arg_8]
0x1800b9b82  mov     [rsp+0D0h+var_A8], rax
0x1800b9b87  mov     [rsp+0D0h+var_B0], r14
0x1800b9b8c  mov     r9d, esi
0x1800b9b8f  xor     r8d, r8d
0x1800b9b92  mov     edx, dword ptr [rbp+57h+var_90+4]
0x1800b9b95  mov     ecx, edi
0x1800b9b97  call    cs:__imp_GdipCreateBitmapFromScan0
0x1800b9b9d  cmp     eax, 2
0x1800b9ba0  jz      loc_1800B9CC3
0x1800b9ba6  mov     r9d, 251965Dh
0x1800b9bac  mov     ecx, eax
0x1800b9bae  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800b9bb3  movss   xmm2, [rbp+57h+arg_14]
0x1800b9bb8  movss   xmm1, [rbp+57h+arg_10]
0x1800b9bbd  mov     rcx, [rbp+57h+arg_8]
0x1800b9bc1  call    cs:__imp_GdipBitmapSetResolution
0x1800b9bc7  mov     r9d, 251965Eh
0x1800b9bcd  mov     ecx, eax
0x1800b9bcf  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800b9bd4  xorps   xmm0, xmm0
0x1800b9bd7  movups  [rbp+57h+var_70], xmm0
0x1800b9bdb  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x1800b9bdf  lea     rax, [rbp+57h+var_70]
0x1800b9be3  mov     [rsp+0D0h+var_B0], rax
0x1800b9be8  mov     r9d, esi
0x1800b9beb  xor     edx, edx
0x1800b9bed  lea     r8d, [rdx+1]
0x1800b9bf1  mov     rcx, [rbp+57h+arg_8]
0x1800b9bf5  call    cs:__imp_GdipBitmapLockBits
0x1800b9bfb  mov     r9d, 251965Fh
0x1800b9c01  mov     ecx, eax
0x1800b9c03  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800b9c08  mov     rdx, rbx; struct ARC::IPlatformPixelMapSurface *
0x1800b9c0b  lea     rcx, [rbp+57h+Src]; this
0x1800b9c0f  call    ??0ReadLock@IPlatformPixelMapSurface@ARC@@QEAA@AEBU12@@Z; ARC::IPlatformPixelMapSurface::ReadLock::ReadLock(ARC::IPlatformPixelMapSurface const &)
0x1800b9c14  nop
0x1800b9c15  movsxd  r15, [rbp+57h+var_40]
0x1800b9c19  mov     rsi, [rbp+57h+Src]
0x1800b9c1d  mov     r14, [rbp+57h+var_60]
0x1800b9c21  xor     ebx, ebx
0x1800b9c23  cmp     ebx, dword ptr [rbp+57h+var_90+4]
0x1800b9c26  jge     short loc_1800B9C50
0x1800b9c28  mov     ecx, r12d
0x1800b9c2b  call    ?GetBytesPerPixelForSurfaceFormat@ARC@@YA_KW4SurfaceFormat@1@@Z; ARC::GetBytesPerPixelForSurfaceFormat(ARC::SurfaceFormat)
0x1800b9c30  movsxd  r8, edi
0x1800b9c33  imul    r8, rax; Size
0x1800b9c37  mov     rdx, rsi; Src
0x1800b9c3a  mov     rcx, r14; void *
0x1800b9c3d  call    memcpy_0
0x1800b9c42  add     rsi, r15
0x1800b9c45  movsxd  rax, dword ptr [rbp+57h+var_70+8]
0x1800b9c49  add     r14, rax
0x1800b9c4c  inc     ebx
0x1800b9c4e  jmp     short loc_1800B9C23
0x1800b9c50  lea     rdx, [rbp+57h+var_70]
0x1800b9c54  mov     rcx, [rbp+57h+arg_8]
0x1800b9c58  call    cs:__imp_GdipBitmapUnlockBits
0x1800b9c5e  mov     r9d, 2519660h
0x1800b9c64  mov     ecx, eax
0x1800b9c66  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800b9c6b  mov     rdi, [rbp+57h+arg_8]
0x1800b9c6f  mov     [rbp+57h+arg_8], 0
0x1800b9c77  mov     rbx, [r13+10h]
0x1800b9c7b  lea     rcx, [rbx+18h]
0x1800b9c7f  call    ?Empty@?$TGpHolder@VGpBitmap@Gdiplus@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGpHolder<Gdiplus::GpBitmap>::Empty(void)
0x1800b9c84  mov     [rbx+18h], rdi
0x1800b9c88  mov     rcx, [rbp+57h+var_38]
0x1800b9c8c  mov     rax, [rcx]
0x1800b9c8f  mov     rax, [rax+8]
0x1800b9c93  call    cs:__guard_dispatch_icall_fptr
0x1800b9c99  mov     rcx, [rbp+57h+arg_8]
0x1800b9c9d  test    rcx, rcx
0x1800b9ca0  jz      short loc_1800B9CA8
0x1800b9ca2  call    cs:__imp_GdipDisposeImage
0x1800b9ca8  mov     rbx, [rsp+0D0h+arg_0]
0x1800b9cb0  add     rsp, 0A0h
0x1800b9cb7  pop     r15
0x1800b9cb9  pop     r14
0x1800b9cbb  pop     r13
0x1800b9cbd  pop     r12
0x1800b9cbf  pop     rdi
0x1800b9cc0  pop     rsi
0x1800b9cc1  pop     rbp
0x1800b9cc2  retn
0x1800b9cc3  lea     rax, ??_7?$StructuredObject@I$00@Logging@Mso@@6B@; const Mso::Logging::StructuredObject<uint,1>::`vftable'
0x1800b9cca  mov     [rbp+57h+var_88], rax
0x1800b9cce  lea     rax, aGdipstatus; "GdipStatus"
0x1800b9cd5  mov     [rbp+57h+var_80], rax
0x1800b9cd9  mov     r8d, 3
0x1800b9cdf  mov     [rbp+57h+var_78], r8d
0x1800b9ce3  mov     [rbp+57h+var_74], r14w
0x1800b9ce8  lea     rax, [rbp+57h+var_88]
0x1800b9cec  mov     [rsp+0D0h+var_A0], rax
0x1800b9cf1  mov     ecx, 2149679Eh
0x1800b9cf6  call    ??$ThrowTagVariableArguments@U?$StructuredObject@I$00@Logging@Mso@@@OExceptionLog@@YAXKW4exceptionType@et@@JPEB_WW4Category@Logging@Mso@@W4Severity@45@$$QEAU?$StructuredObject@I$00@45@@Z; OExceptionLog::ThrowTagVariableArguments<Mso::Logging::StructuredObject<uint,1>>(ulong,et::exceptionType,long,wchar_t const *,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::StructuredObject<uint,1> &&)
```
