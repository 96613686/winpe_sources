# GEL::VectorImageResource::ProcessMetafile(void)

- ea: `0x1800a4e54`
- end: `0x1800a50f3`
- name: `?ProcessMetafile@VectorImageResource@GEL@@AEAAXXZ`
- size: `671`
- prototype: `void __fastcall(GEL::VectorImageResource *__hidden this)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800a4908`
- `0x1800a4a78`
- `0x1801cb554`

## callees

- `0x180055b26`
- `0x180062394`
- `0x180064d9c`
- `0x1800a4e54`
- `0x1800a57a4`
- `0x1800a5808`
- `0x1800a5888`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800a4ecf`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800a4ecf`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x1800a4fee`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x1800a4fee`
- `GDI32!DeleteDC` at `0x1800a4fae`
- `GDI32!DeleteDC` at `0x1800a4fae`
- `GDI32!CreateCompatibleDC` at `0x1800a4ead`
- `GDI32!CreateCompatibleDC` at `0x1800a4ead`
- `gdiplus!GdipGetImageType` at `0x1800a4e8d`
- `gdiplus!GdipGetImageType` at `0x1800a4e8d`
- `gdiplus!GdipConvertToEmfPlus` at `0x1800a50cf`
- `gdiplus!GdipConvertToEmfPlus` at `0x1800a50cf`
- `gdiplus!GdipGetMetafileHeaderFromMetafile` at `0x1800a4f8b`
- `gdiplus!GdipGetMetafileHeaderFromMetafile` at `0x1800a4f8b`
- `gdiplus!GdipEnumerateMetafileDestPoint` at `0x1800a4f3c`
- `gdiplus!GdipEnumerateMetafileDestPoint` at `0x1800a5053`
- `gdiplus!GdipEnumerateMetafileDestPoint` at `0x1800a4f3c`
- `gdiplus!GdipEnumerateMetafileDestPoint` at `0x1800a5053`
- `gdiplus!GdipDeleteGraphics` at `0x1800a4fc1`
- `gdiplus!GdipDeleteGraphics` at `0x1800a4fc1`
- `gdiplus!GdipCreateFromHDC` at `0x1800a5000`
- `gdiplus!GdipCreateFromHDC` at `0x1800a5000`
- `gdiplus!GdipDisposeImage` at `0x1800a4f00`
- `gdiplus!GdipDisposeImage` at `0x1800a4f00`
- `gdiplus!GdipSetSmoothingMode` at `0x1800a5083`
- `gdiplus!GdipSetSmoothingMode` at `0x1800a5083`

## string_xrefs

- `0x1800a4fd7`: `VectorImageResource::ProcessMetafile: unable to access metafile header`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall GEL::VectorImageResource::ProcessMetafile(GEL::VectorImageResource *this)
{
  __int64 *v2; // rdi
  __int64 v3; // rsi
  HDC CompatibleDC; // rax
  HDC v5; // r14
  unsigned int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  unsigned int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // [rsp+30h] [rbp-D0h] BYREF
  _DWORD v13[2]; // [rsp+38h] [rbp-C8h] BYREF
  char v14; // [rsp+40h] [rbp-C0h]
  HDC v15; // [rsp+48h] [rbp-B8h]
  __int64 v16; // [rsp+50h] [rbp-B0h]
  _BYTE v17[8]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v18[72]; // [rsp+68h] [rbp-98h] BYREF
  float v19; // [rsp+B0h] [rbp-50h]
  float v20; // [rsp+B4h] [rbp-4Ch]
  char v21; // [rsp+E9h] [rbp-17h]
  char v22; // [rsp+EAh] [rbp-16h]
  char v23; // [rsp+EEh] [rbp-12h]
  _BYTE v24[4]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned int v25; // [rsp+F4h] [rbp-Ch]
  int v26; // [rsp+1C0h] [rbp+C0h] BYREF
  int v27; // [rsp+1C8h] [rbp+C8h] BYREF
  __int64 v28; // [rsp+1D0h] [rbp+D0h] BYREF
  __int64 v29; // [rsp+1D8h] [rbp+D8h] BYREF

  if ( *((_BYTE *)this + 106) )
    goto LABEL_5;
  v26 = 0;
  v2 = (__int64 *)((char *)this + 8);
  GdipGetImageType(*((_QWORD *)this + 1), &v26);
  if ( v26 != 2 )
    goto LABEL_5;
  v28 = 0;
  v3 = *v2;
  v16 = 0;
  CompatibleDC = CreateCompatibleDC(0);
  v5 = CompatibleDC;
  v15 = CompatibleDC;
  if ( v28 )
  {
    CrashWithRecovery(0x1E55E058u, 0);
LABEL_5:
    *((_DWORD *)this + 25) = 0;
    return;
  }
  v6 = GdipCreateFromHDC(CompatibleDC, &v28);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(v6, v7, v8, 39081291);
  v12 = 0;
  v13[0] = 0;
  v13[1] = 0x2000;
  v14 = 0;
  GdipEnumerateMetafileDestPoint(v28, v3, &v12, &GEL::VectorImageResource::AnalyzeMetafileForSpecialROPs, v13, 0);
  *((_DWORD *)this + 25) = v13[0];
  if ( (unsigned __int8)sub_1800A57A4(v28, v3) )
  {
    v9 = GdipSetSmoothingMode(v28, 4);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(v9, v10, v11, 39081292);
    v29 = 0;
    v27 = 7;
    if ( !(unsigned int)GdipConvertToEmfPlus(v28, v3, &v27, 4, 0, &v29) )
    {
      if ( !v29 )
        goto LABEL_9;
      v3 = v29;
      v29 = 0;
      ARC::GDIPlus::TGpHolder<Gdiplus::GpBitmap>::Empty(v2);
      *v2 = v3;
    }
    if ( v29 )
    {
      GdipDisposeImage();
      v29 = 0;
    }
  }
LABEL_9:
  GEL::MetafileContent::MetafileContent((GEL::MetafileContent *)v17);
  GdipEnumerateMetafileDestPoint(v28, v3, &v12, sub_1800A69F0, v17, 0);
  *((_BYTE *)this + 104) = v22;
  *((_BYTE *)this + 105) = v21;
  *((_BYTE *)this + 41) = v23;
  *((float *)this + 23) = fminf(1.0, v19);
  *((float *)this + 24) = fminf(1.0, v20);
  memset_0(v24, 0, 0x8Cu);
  if ( (unsigned int)GdipGetMetafileHeaderFromMetafile(v3, v24) )
    Mso::Logging::MsoSendTraceTag(
      7955415,
      144,
      15,
      L"VectorImageResource::ProcessMetafile: unable to access metafile header");
  else
    *((_QWORD *)this + 9) = v25;
  std::vector<GEL::AnimatableProgressHolder *>::~vector<GEL::AnimatableProgressHolder *>(v18);
  if ( v5 )
    DeleteDC(v5);
  if ( v28 )
    GdipDeleteGraphics();
}

```

## disassembly

```asm
0x1800a4e54  push    rbp
0x1800a4e56  push    rbx
0x1800a4e57  push    rsi
0x1800a4e58  push    rdi
0x1800a4e59  push    r12
0x1800a4e5b  push    r14
0x1800a4e5d  lea     rbp, [rsp-88h]
0x1800a4e65  sub     rsp, 188h
0x1800a4e6c  mov     rbx, rcx
0x1800a4e6f  xor     r12d, r12d
0x1800a4e72  cmp     [rcx+6Ah], r12b
0x1800a4e76  jnz     short loc_1800A4ED6
0x1800a4e78  mov     [rbp+0B0h+arg_0], r12d
0x1800a4e7f  lea     rdi, [rcx+8]
0x1800a4e83  lea     rdx, [rbp+0B0h+arg_0]
0x1800a4e8a  mov     rcx, [rdi]
0x1800a4e8d  call    cs:__imp_GdipGetImageType
0x1800a4e93  cmp     [rbp+0B0h+arg_0], 2
0x1800a4e9a  jnz     short loc_1800A4ED6
0x1800a4e9c  mov     [rbp+0B0h+arg_10], r12
0x1800a4ea3  mov     rsi, [rdi]
0x1800a4ea6  mov     [rsp+1B0h+var_160], r12
0x1800a4eab  xor     ecx, ecx; hdc
0x1800a4ead  call    cs:__imp_CreateCompatibleDC
0x1800a4eb3  mov     r14, rax
0x1800a4eb6  mov     [rsp+1B0h+var_168], rax
0x1800a4ebb  cmp     [rbp+0B0h+arg_10], r12
0x1800a4ec2  jz      loc_1800A4FF6
0x1800a4ec8  xor     edx, edx
0x1800a4eca  mov     ecx, 1E55E058h
0x1800a4ecf  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800a4ed5  nop
0x1800a4ed6  mov     [rbx+64h], r12d
0x1800a4eda  jmp     loc_1800A4FC7
0x1800a4edf  mov     rsi, rax
0x1800a4ee2  mov     [rbp+0B0h+arg_18], r12
0x1800a4ee9  mov     rcx, rdi
0x1800a4eec  call    ?Empty@?$TGpHolder@VGpBitmap@Gdiplus@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGpHolder<Gdiplus::GpBitmap>::Empty(void)
0x1800a4ef1  mov     [rdi], rsi
0x1800a4ef4  mov     rcx, [rbp+0B0h+arg_18]
0x1800a4efb  test    rcx, rcx
0x1800a4efe  jz      short loc_1800A4F0D
0x1800a4f00  call    cs:__imp_GdipDisposeImage
0x1800a4f06  mov     [rbp+0B0h+arg_18], r12
0x1800a4f0d  lea     rcx, [rsp+1B0h+var_150]; this
0x1800a4f12  call    ??0MetafileContent@GEL@@QEAA@XZ; GEL::MetafileContent::MetafileContent(void)
0x1800a4f17  mov     [rsp+1B0h+var_188], r12
0x1800a4f1c  lea     rax, [rsp+1B0h+var_150]
0x1800a4f21  mov     [rsp+1B0h+var_190], rax
0x1800a4f26  lea     r9, sub_1800A69F0
0x1800a4f2d  lea     r8, [rsp+1B0h+var_180]
0x1800a4f32  mov     rdx, rsi
0x1800a4f35  mov     rcx, [rbp+0B0h+arg_10]
0x1800a4f3c  call    cs:__imp_GdipEnumerateMetafileDestPoint
0x1800a4f42  mov     al, [rbp+0B0h+var_C6]
0x1800a4f45  mov     [rbx+68h], al
0x1800a4f48  mov     al, [rbp+0B0h+var_C7]
0x1800a4f4b  mov     [rbx+69h], al
0x1800a4f4e  mov     al, [rbp+0B0h+var_C2]
0x1800a4f51  mov     [rbx+29h], al
0x1800a4f54  movss   xmm1, cs:__real@3f800000
0x1800a4f5c  movaps  xmm0, xmm1
0x1800a4f5f  minss   xmm0, [rbp+0B0h+var_100]
0x1800a4f64  movss   dword ptr [rbx+5Ch], xmm0
0x1800a4f69  minss   xmm1, [rbp+0B0h+var_FC]
0x1800a4f6e  movss   dword ptr [rbx+60h], xmm1
0x1800a4f73  xor     edx, edx; Val
0x1800a4f75  mov     r8d, 8Ch; Size
0x1800a4f7b  lea     rcx, [rbp+0B0h+var_C0]; void *
0x1800a4f7f  call    memset_0
0x1800a4f84  lea     rdx, [rbp+0B0h+var_C0]
0x1800a4f88  mov     rcx, rsi
0x1800a4f8b  call    cs:__imp_GdipGetMetafileHeaderFromMetafile
0x1800a4f91  test    eax, eax
0x1800a4f93  jnz     short loc_1800A4FD7
0x1800a4f95  mov     eax, [rbp+0B0h+var_BC]
0x1800a4f98  mov     [rbx+48h], rax
0x1800a4f9c  lea     rcx, [rsp+1B0h+var_148]
0x1800a4fa1  call    ??1?$vector@PEAVAnimatableProgressHolder@GEL@@V?$allocator@PEAVAnimatableProgressHolder@GEL@@@std@@@std@@QEAA@XZ; std::vector<GEL::AnimatableProgressHolder *>::~vector<GEL::AnimatableProgressHolder *>(void)
0x1800a4fa6  test    r14, r14
0x1800a4fa9  jz      short loc_1800A4FB5
0x1800a4fab  mov     rcx, r14; hdc
0x1800a4fae  call    cs:__imp_DeleteDC
0x1800a4fb4  nop
0x1800a4fb5  mov     rcx, [rbp+0B0h+arg_10]
0x1800a4fbc  test    rcx, rcx
0x1800a4fbf  jz      short loc_1800A4FC7
0x1800a4fc1  call    cs:__imp_GdipDeleteGraphics
0x1800a4fc7  add     rsp, 188h
0x1800a4fce  pop     r14
0x1800a4fd0  pop     r12
0x1800a4fd2  pop     rdi
0x1800a4fd3  pop     rsi
0x1800a4fd4  pop     rbx
0x1800a4fd5  pop     rbp
0x1800a4fd6  retn
0x1800a4fd7  lea     r9, aVectorimageres_2; "VectorImageResource::ProcessMetafile: u"...
0x1800a4fde  mov     edx, 90h
0x1800a4fe3  mov     ecx, 7963D7h
0x1800a4fe8  mov     r8d, 0Fh
0x1800a4fee  call    cs:__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z; Mso::Logging::MsoSendTraceTag(ulong,Mso::Logging::Category,Mso::Logging::Severity,wchar_t const *)
0x1800a4ff4  jmp     short loc_1800A4F9C
0x1800a4ff6  lea     rdx, [rbp+0B0h+arg_10]
0x1800a4ffd  mov     rcx, r14
0x1800a5000  call    cs:__imp_GdipCreateFromHDC
0x1800a5006  mov     r9d, 254554Bh
0x1800a500c  mov     ecx, eax
0x1800a500e  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800a5013  mov     [rsp+1B0h+var_180], 0
0x1800a501c  mov     [rsp+1B0h+var_178], r12d
0x1800a5021  mov     [rsp+1B0h+var_174], 2000h
0x1800a5029  mov     [rsp+1B0h+var_170], r12b
0x1800a502e  mov     [rsp+1B0h+var_188], r12
0x1800a5033  lea     rax, [rsp+1B0h+var_178]
0x1800a5038  mov     [rsp+1B0h+var_190], rax
0x1800a503d  lea     r9, ?AnalyzeMetafileForSpecialROPs@VectorImageResource@GEL@@CAHW4EmfPlusRecordType@Gdiplus@@IIPEBEPEAX@Z; GEL::VectorImageResource::AnalyzeMetafileForSpecialROPs(Gdiplus::EmfPlusRecordType,uint,uint,uchar const *,void *)
0x1800a5044  lea     r8, [rsp+1B0h+var_180]
0x1800a5049  mov     rdx, rsi
0x1800a504c  mov     rcx, [rbp+0B0h+arg_10]
0x1800a5053  call    cs:__imp_GdipEnumerateMetafileDestPoint
0x1800a5059  mov     eax, [rsp+1B0h+var_178]
0x1800a505d  mov     [rbx+64h], eax
0x1800a5060  mov     rdx, rsi
0x1800a5063  mov     rcx, [rbp+0B0h+arg_10]
0x1800a506a  call    sub_1800A57A4
0x1800a506f  test    al, al
0x1800a5071  jz      loc_1800A4F0D
0x1800a5077  mov     edx, 4
0x1800a507c  mov     rcx, [rbp+0B0h+arg_10]
0x1800a5083  call    cs:__imp_GdipSetSmoothingMode
0x1800a5089  mov     r9d, 254554Ch
0x1800a508f  mov     ecx, eax
0x1800a5091  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800a5096  mov     [rbp+0B0h+arg_18], r12
0x1800a509d  mov     [rbp+0B0h+arg_8], 7
0x1800a50a7  lea     rax, [rbp+0B0h+arg_18]
0x1800a50ae  mov     [rsp+1B0h+var_188], rax
0x1800a50b3  mov     [rsp+1B0h+var_190], r12
0x1800a50b8  mov     r9d, 4
0x1800a50be  lea     r8, [rbp+0B0h+arg_8]
0x1800a50c5  mov     rdx, rsi
0x1800a50c8  mov     rcx, [rbp+0B0h+arg_10]
0x1800a50cf  call    cs:__imp_GdipConvertToEmfPlus
0x1800a50d5  test    eax, eax
0x1800a50d7  jnz     loc_1800A4EF4
0x1800a50dd  mov     rax, [rbp+0B0h+arg_18]
0x1800a50e4  test    rax, rax
0x1800a50e7  jnz     loc_1800A4EDF
0x1800a50ed  jmp     loc_1800A4F0D
```
