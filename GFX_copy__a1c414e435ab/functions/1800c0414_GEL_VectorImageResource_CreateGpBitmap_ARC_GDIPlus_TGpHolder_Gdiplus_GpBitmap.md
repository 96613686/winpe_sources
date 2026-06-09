# GEL::VectorImageResource::CreateGpBitmap(ARC::GDIPlus::TGpHolder<Gdiplus::GpBitmap> &)

- ea: `0x1800c0414`
- end: `0x1800c0547`
- name: `?CreateGpBitmap@VectorImageResource@GEL@@QEBAXAEAV?$TGpHolder@VGpBitmap@Gdiplus@@@GDIPlus@ARC@@@Z`
- size: `307`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800c02a0`

## callees

- `0x18005f898`
- `0x180060f10`
- `0x180062394`
- `0x180064d9c`
- `0x1800c0414`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800c04c5`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800c04c5`
- `gdiplus!GdipGetImagePixelFormat` at `0x1800c043f`
- `gdiplus!GdipGetImagePixelFormat` at `0x1800c043f`
- `gdiplus!GdipDrawImageRectI` at `0x1800c0519`
- `gdiplus!GdipDrawImageRectI` at `0x1800c0519`
- `gdiplus!GdipGetImageGraphicsContext` at `0x1800c04d3`
- `gdiplus!GdipGetImageGraphicsContext` at `0x1800c04d3`
- `gdiplus!GdipSetInterpolationMode` at `0x1800c04ef`
- `gdiplus!GdipSetInterpolationMode` at `0x1800c04ef`
- `gdiplus!GdipDeleteGraphics` at `0x1800c0536`
- `gdiplus!GdipDeleteGraphics` at `0x1800c0536`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x1800c04a3`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x1800c04a3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall GEL::VectorImageResource::CreateGpBitmap(__int64 a1, _QWORD *a2)
{
  unsigned int ImagePixelFormat; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rbx
  __int64 v8; // rax
  int v9; // r14d
  unsigned int BitmapFromScan0; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  unsigned int ImageGraphicsContext; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  unsigned int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // r8
  unsigned int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // r8
  unsigned int v22; // [rsp+60h] [rbp+30h] BYREF
  __int64 v23; // [rsp+70h] [rbp+40h] BYREF
  __int64 v24; // [rsp+78h] [rbp+48h] BYREF

  ARC::GDIPlus::TGpHolder<Gdiplus::GpBitmap>::Empty(a2);
  v22 = 0;
  ImagePixelFormat = GdipGetImagePixelFormat(*(_QWORD *)(a1 + 8), &v22);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(ImagePixelFormat, v5, v6, 39081315);
  if ( v22 == 8207 )
    v22 = 2498570;
  v7 = *(_QWORD *)GEL::VectorImageResource::GetSize(a1, &v24);
  v24 = v7;
  v23 = 0;
  v8 = ARC::GDIPlus::TGpHolder<Gdiplus::Matrix>::operator&(a2);
  v9 = HIDWORD(v24);
  BitmapFromScan0 = GdipCreateBitmapFromScan0((unsigned int)v7, HIDWORD(v24), 0, v22, 0, v8);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(BitmapFromScan0, v11, v12, 39081344);
  if ( v23 )
    CrashWithRecovery(0x1E55E058u, 0);
  ImageGraphicsContext = GdipGetImageGraphicsContext(*a2, &v23);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(ImageGraphicsContext, v14, v15, 39081345);
  v16 = GdipSetInterpolationMode(v23, 5);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(v16, v17, v18, 39081346);
  v19 = GdipDrawImageRectI(v23, *(_QWORD *)(a1 + 8), 0, 0, v7, v9);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(v19, v20, v21, 39081347);
  if ( v23 )
    GdipDeleteGraphics();
}

```

## disassembly

```asm
0x1800c0414  push    rbp
0x1800c0416  push    rbx
0x1800c0417  push    rsi
0x1800c0418  push    rdi
0x1800c0419  push    r14
0x1800c041b  mov     rbp, rsp
0x1800c041e  sub     rsp, 30h
0x1800c0422  mov     rdi, rdx
0x1800c0425  mov     rsi, rcx
0x1800c0428  mov     rcx, rdx
0x1800c042b  call    ?Empty@?$TGpHolder@VGpBitmap@Gdiplus@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGpHolder<Gdiplus::GpBitmap>::Empty(void)
0x1800c0430  mov     [rbp+arg_0], 0
0x1800c0437  lea     rdx, [rbp+arg_0]
0x1800c043b  mov     rcx, [rsi+8]
0x1800c043f  call    cs:__imp_GdipGetImagePixelFormat
0x1800c0445  mov     r9d, 2545563h
0x1800c044b  mov     ecx, eax
0x1800c044d  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800c0452  cmp     [rbp+arg_0], 200Fh
0x1800c0459  jnz     short loc_1800C0462
0x1800c045b  mov     [rbp+arg_0], 26200Ah
0x1800c0462  lea     rdx, [rbp+arg_18]
0x1800c0466  mov     rcx, rsi
0x1800c0469  call    ?GetSize@VectorImageResource@GEL@@UEBA?AU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@XZ; GEL::VectorImageResource::GetSize(void)
0x1800c046e  mov     rbx, [rax]
0x1800c0471  mov     [rbp+arg_18], rbx
0x1800c0475  mov     [rbp+arg_10], 0
0x1800c047d  mov     rcx, rdi
0x1800c0480  call    ??I?$TGpHolder@VMatrix@Gdiplus@@@GDIPlus@ARC@@QEAAPEAPEAVMatrix@Gdiplus@@XZ; ARC::GDIPlus::TGpHolder<Gdiplus::Matrix>::operator&(void)
0x1800c0485  mov     [rsp+30h+var_8], rax
0x1800c048a  mov     [rsp+30h+var_10], 0
0x1800c0493  mov     r9d, [rbp+arg_0]
0x1800c0497  xor     r8d, r8d
0x1800c049a  mov     r14d, dword ptr [rbp+arg_18+4]
0x1800c049e  mov     edx, r14d
0x1800c04a1  mov     ecx, ebx
0x1800c04a3  call    cs:__imp_GdipCreateBitmapFromScan0
0x1800c04a9  mov     r9d, 2545580h
0x1800c04af  mov     ecx, eax
0x1800c04b1  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800c04b6  nop
0x1800c04b7  cmp     [rbp+arg_10], 0
0x1800c04bc  jz      short loc_1800C04CC
0x1800c04be  xor     edx, edx
0x1800c04c0  mov     ecx, 1E55E058h
0x1800c04c5  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800c04cb  nop
0x1800c04cc  lea     rdx, [rbp+arg_10]
0x1800c04d0  mov     rcx, [rdi]
0x1800c04d3  call    cs:__imp_GdipGetImageGraphicsContext
0x1800c04d9  mov     r9d, 2545581h
0x1800c04df  mov     ecx, eax
0x1800c04e1  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800c04e6  mov     edx, 5
0x1800c04eb  mov     rcx, [rbp+arg_10]
0x1800c04ef  call    cs:__imp_GdipSetInterpolationMode
0x1800c04f5  mov     r9d, 2545582h
0x1800c04fb  mov     ecx, eax
0x1800c04fd  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800c0502  mov     dword ptr [rsp+30h+var_8], r14d
0x1800c0507  mov     dword ptr [rsp+30h+var_10], ebx
0x1800c050b  xor     r9d, r9d
0x1800c050e  xor     r8d, r8d
0x1800c0511  mov     rdx, [rsi+8]
0x1800c0515  mov     rcx, [rbp+arg_10]
0x1800c0519  call    cs:__imp_GdipDrawImageRectI
0x1800c051f  mov     r9d, 2545583h
0x1800c0525  mov     ecx, eax
0x1800c0527  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800c052c  nop
0x1800c052d  mov     rcx, [rbp+arg_10]
0x1800c0531  test    rcx, rcx
0x1800c0534  jz      short loc_1800C053C
0x1800c0536  call    cs:__imp_GdipDeleteGraphics
0x1800c053c  add     rsp, 30h
0x1800c0540  pop     r14
0x1800c0542  pop     rdi
0x1800c0543  pop     rsi
0x1800c0544  pop     rbx
0x1800c0545  pop     rbp
0x1800c0546  retn
```
