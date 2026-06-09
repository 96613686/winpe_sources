# GEL::VectorImageResource::CreateGpBitmap(ARC::GDIPlus::TGpHolder<Gdiplus::GpBitmap> &)

- ea: `0x180167d14`
- end: `0x180167e47`
- name: `?CreateGpBitmap@VectorImageResource@GEL@@QEBAXAEAV?$TGpHolder@VGpBitmap@Gdiplus@@@GDIPlus@ARC@@@Z`
- size: `307`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180167ba0`

## callees

- `0x18007f754`
- `0x18007faf8`
- `0x180080960`
- `0x180082aac`
- `0x180167d14`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180167dc5`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180167dc5`
- `gdiplus!GdipGetImagePixelFormat` at `0x180167d3f`
- `gdiplus!GdipGetImagePixelFormat` at `0x180167d3f`
- `gdiplus!GdipDrawImageRectI` at `0x180167e19`
- `gdiplus!GdipDrawImageRectI` at `0x180167e19`
- `gdiplus!GdipGetImageGraphicsContext` at `0x180167dd3`
- `gdiplus!GdipGetImageGraphicsContext` at `0x180167dd3`
- `gdiplus!GdipSetInterpolationMode` at `0x180167def`
- `gdiplus!GdipSetInterpolationMode` at `0x180167def`
- `gdiplus!GdipDeleteGraphics` at `0x180167e36`
- `gdiplus!GdipDeleteGraphics` at `0x180167e36`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x180167da3`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x180167da3`

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
0x180167d14  push    rbp
0x180167d16  push    rbx
0x180167d17  push    rsi
0x180167d18  push    rdi
0x180167d19  push    r14
0x180167d1b  mov     rbp, rsp
0x180167d1e  sub     rsp, 30h
0x180167d22  mov     rdi, rdx
0x180167d25  mov     rsi, rcx
0x180167d28  mov     rcx, rdx
0x180167d2b  call    ?Empty@?$TGpHolder@VGpBitmap@Gdiplus@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGpHolder<Gdiplus::GpBitmap>::Empty(void)
0x180167d30  mov     [rbp+arg_0], 0
0x180167d37  lea     rdx, [rbp+arg_0]
0x180167d3b  mov     rcx, [rsi+8]
0x180167d3f  call    cs:__imp_GdipGetImagePixelFormat
0x180167d45  mov     r9d, 2545563h
0x180167d4b  mov     ecx, eax
0x180167d4d  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180167d52  cmp     [rbp+arg_0], 200Fh
0x180167d59  jnz     short loc_180167D62
0x180167d5b  mov     [rbp+arg_0], 26200Ah
0x180167d62  lea     rdx, [rbp+arg_18]
0x180167d66  mov     rcx, rsi
0x180167d69  call    ?GetSize@VectorImageResource@GEL@@UEBA?AU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@XZ; GEL::VectorImageResource::GetSize(void)
0x180167d6e  mov     rbx, [rax]
0x180167d71  mov     [rbp+arg_18], rbx
0x180167d75  mov     [rbp+arg_10], 0
0x180167d7d  mov     rcx, rdi
0x180167d80  call    ??I?$TGpHolder@VMatrix@Gdiplus@@@GDIPlus@ARC@@QEAAPEAPEAVMatrix@Gdiplus@@XZ; ARC::GDIPlus::TGpHolder<Gdiplus::Matrix>::operator&(void)
0x180167d85  mov     [rsp+30h+var_8], rax
0x180167d8a  mov     [rsp+30h+var_10], 0
0x180167d93  mov     r9d, [rbp+arg_0]
0x180167d97  xor     r8d, r8d
0x180167d9a  mov     r14d, dword ptr [rbp+arg_18+4]
0x180167d9e  mov     edx, r14d
0x180167da1  mov     ecx, ebx
0x180167da3  call    cs:__imp_GdipCreateBitmapFromScan0
0x180167da9  mov     r9d, 2545580h
0x180167daf  mov     ecx, eax
0x180167db1  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180167db6  nop
0x180167db7  cmp     [rbp+arg_10], 0
0x180167dbc  jz      short loc_180167DCC
0x180167dbe  xor     edx, edx
0x180167dc0  mov     ecx, 1E55E058h
0x180167dc5  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180167dcb  nop
0x180167dcc  lea     rdx, [rbp+arg_10]
0x180167dd0  mov     rcx, [rdi]
0x180167dd3  call    cs:__imp_GdipGetImageGraphicsContext
0x180167dd9  mov     r9d, 2545581h
0x180167ddf  mov     ecx, eax
0x180167de1  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180167de6  mov     edx, 5
0x180167deb  mov     rcx, [rbp+arg_10]
0x180167def  call    cs:__imp_GdipSetInterpolationMode
0x180167df5  mov     r9d, 2545582h
0x180167dfb  mov     ecx, eax
0x180167dfd  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180167e02  mov     dword ptr [rsp+30h+var_8], r14d
0x180167e07  mov     dword ptr [rsp+30h+var_10], ebx
0x180167e0b  xor     r9d, r9d
0x180167e0e  xor     r8d, r8d
0x180167e11  mov     rdx, [rsi+8]
0x180167e15  mov     rcx, [rbp+arg_10]
0x180167e19  call    cs:__imp_GdipDrawImageRectI
0x180167e1f  mov     r9d, 2545583h
0x180167e25  mov     ecx, eax
0x180167e27  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180167e2c  nop
0x180167e2d  mov     rcx, [rbp+arg_10]
0x180167e31  test    rcx, rcx
0x180167e34  jz      short loc_180167E3C
0x180167e36  call    cs:__imp_GdipDeleteGraphics
0x180167e3c  add     rsp, 30h
0x180167e40  pop     r14
0x180167e42  pop     rdi
0x180167e43  pop     rsi
0x180167e44  pop     rbx
0x180167e45  pop     rbp
0x180167e46  retn
```
