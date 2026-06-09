# GEL::VectorImageResource::ProcessMetafile(void)

- ea: `0x1800e3da4`
- end: `0x1800e4037`
- name: `?ProcessMetafile@VectorImageResource@GEL@@AEAAXXZ`
- size: `659`
- prototype: `void __fastcall(GEL::VectorImageResource *__hidden this)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800e39c8`
- `0x18016e9ac`
- `0x1801d00d4`

## callees

- `0x1800565ba`
- `0x18007f754`
- `0x180082aac`
- `0x1800b9f54`
- `0x1800e3da4`
- `0x1800e46f4`
- `0x1800e4758`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800e400a`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800e400a`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x1800e4028`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x1800e4028`
- `GDI32!DeleteDC` at `0x1800e3fda`
- `GDI32!DeleteDC` at `0x1800e3fda`
- `GDI32!CreateCompatibleDC` at `0x1800e3e05`
- `GDI32!CreateCompatibleDC` at `0x1800e3e05`
- `gdiplus!GdipGetImageType` at `0x1800e3de1`
- `gdiplus!GdipGetImageType` at `0x1800e3de1`
- `gdiplus!GdipConvertToEmfPlus` at `0x1800e3ef4`
- `gdiplus!GdipConvertToEmfPlus` at `0x1800e3ef4`
- `gdiplus!GdipGetMetafileHeaderFromMetafile` at `0x1800e3fb6`
- `gdiplus!GdipGetMetafileHeaderFromMetafile` at `0x1800e3fb6`
- `gdiplus!GdipEnumerateMetafileDestPoint` at `0x1800e3e79`
- `gdiplus!GdipEnumerateMetafileDestPoint` at `0x1800e3f67`
- `gdiplus!GdipEnumerateMetafileDestPoint` at `0x1800e3e79`
- `gdiplus!GdipEnumerateMetafileDestPoint` at `0x1800e3f67`
- `gdiplus!GdipDeleteGraphics` at `0x1800e3fed`
- `gdiplus!GdipDeleteGraphics` at `0x1800e3fed`
- `gdiplus!GdipCreateFromHDC` at `0x1800e3e2a`
- `gdiplus!GdipCreateFromHDC` at `0x1800e3e2a`
- `gdiplus!GdipDisposeImage` at `0x1800e3f2b`
- `gdiplus!GdipDisposeImage` at `0x1800e3f2b`
- `gdiplus!GdipSetSmoothingMode` at `0x1800e3ea9`
- `gdiplus!GdipSetSmoothingMode` at `0x1800e3ea9`

## string_xrefs

- `0x1800e4011`: `VectorImageResource::ProcessMetafile: unable to access metafile header`

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

  if ( *((_BYTE *)this + 106)
    || (v26 = 0, v2 = (__int64 *)((char *)this + 8), GdipGetImageType(*((_QWORD *)this + 1), &v26), v26 != 2) )
  {
    *((_DWORD *)this + 25) = 0;
    return;
  }
  v28 = 0;
  v3 = *v2;
  v16 = 0;
  CompatibleDC = CreateCompatibleDC(0);
  v5 = CompatibleDC;
  v15 = CompatibleDC;
  if ( v28 )
  {
    CrashWithRecovery(0x1E55E058u, 0);
    goto LABEL_18;
  }
  v6 = GdipCreateFromHDC(CompatibleDC, &v28);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(v6, v7, v8, 39081291);
  v12 = 0;
  v13[0] = 0;
  v13[1] = 0x2000;
  v14 = 0;
  GdipEnumerateMetafileDestPoint(v28, v3, &v12, &GEL::VectorImageResource::AnalyzeMetafileForSpecialROPs, v13, 0);
  *((_DWORD *)this + 25) = v13[0];
  if ( (unsigned __int8)sub_1800E46F4(v28, v3) )
  {
    v9 = GdipSetSmoothingMode(v28, 4);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(v9, v10, v11, 39081292);
    v29 = 0;
    v27 = 7;
    if ( !(unsigned int)GdipConvertToEmfPlus(v28, v3, &v27, 4, 0, &v29) )
    {
      if ( !v29 )
        goto LABEL_10;
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
LABEL_10:
  GEL::MetafileContent::MetafileContent((GEL::MetafileContent *)v17);
  GdipEnumerateMetafileDestPoint(v28, v3, &v12, sub_180105350, v17, 0);
  *((_BYTE *)this + 104) = v22;
  *((_BYTE *)this + 105) = v21;
  *((_BYTE *)this + 41) = v23;
  *((float *)this + 23) = fminf(1.0, v19);
  *((float *)this + 24) = fminf(1.0, v20);
  memset_0(v24, 0, 0x8Cu);
  if ( (unsigned int)GdipGetMetafileHeaderFromMetafile(v3, v24) )
  {
LABEL_18:
    Mso::Logging::MsoSendTraceTag(
      7955415,
      144,
      15,
      L"VectorImageResource::ProcessMetafile: unable to access metafile header");
    goto LABEL_12;
  }
  *((_QWORD *)this + 9) = v25;
LABEL_12:
  std::vector<GEL::AnimatableProgressHolder *>::~vector<GEL::AnimatableProgressHolder *>(v18);
  if ( v5 )
    DeleteDC(v5);
  if ( v28 )
    GdipDeleteGraphics();
}

```

## disassembly

```asm
0x1800e3da4  push    rbp
0x1800e3da6  push    rbx
0x1800e3da7  push    rsi
0x1800e3da8  push    rdi
0x1800e3da9  push    r12
0x1800e3dab  push    r14
0x1800e3dad  lea     rbp, [rsp-88h]
0x1800e3db5  sub     rsp, 188h
0x1800e3dbc  mov     rbx, rcx
0x1800e3dbf  xor     r12d, r12d
0x1800e3dc2  cmp     [rcx+6Ah], r12b
0x1800e3dc6  jnz     loc_1800E4030
0x1800e3dcc  mov     [rbp+0B0h+arg_0], r12d
0x1800e3dd3  lea     rdi, [rcx+8]
0x1800e3dd7  lea     rdx, [rbp+0B0h+arg_0]
0x1800e3dde  mov     rcx, [rdi]
0x1800e3de1  call    cs:__imp_GdipGetImageType
0x1800e3de7  cmp     [rbp+0B0h+arg_0], 2
0x1800e3dee  jnz     loc_1800E4030
0x1800e3df4  mov     [rbp+0B0h+arg_10], r12
0x1800e3dfb  mov     rsi, [rdi]
0x1800e3dfe  mov     [rsp+1B0h+var_160], r12
0x1800e3e03  xor     ecx, ecx; hdc
0x1800e3e05  call    cs:__imp_CreateCompatibleDC
0x1800e3e0b  mov     r14, rax
0x1800e3e0e  mov     [rsp+1B0h+var_168], rax
0x1800e3e13  cmp     [rbp+0B0h+arg_10], r12
0x1800e3e1a  jnz     loc_1800E4003
0x1800e3e20  lea     rdx, [rbp+0B0h+arg_10]
0x1800e3e27  mov     rcx, rax
0x1800e3e2a  call    cs:__imp_GdipCreateFromHDC
0x1800e3e30  mov     r9d, 254554Bh
0x1800e3e36  mov     ecx, eax
0x1800e3e38  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800e3e3d  mov     [rsp+1B0h+var_180], r12
0x1800e3e42  mov     [rsp+1B0h+var_178], r12d
0x1800e3e47  mov     [rsp+1B0h+var_174], 2000h
0x1800e3e4f  mov     [rsp+1B0h+var_170], r12b
0x1800e3e54  mov     [rsp+1B0h+var_188], r12
0x1800e3e59  lea     rax, [rsp+1B0h+var_178]
0x1800e3e5e  mov     [rsp+1B0h+var_190], rax
0x1800e3e63  lea     r9, ?AnalyzeMetafileForSpecialROPs@VectorImageResource@GEL@@CAHW4EmfPlusRecordType@Gdiplus@@IIPEBEPEAX@Z; GEL::VectorImageResource::AnalyzeMetafileForSpecialROPs(Gdiplus::EmfPlusRecordType,uint,uint,uchar const *,void *)
0x1800e3e6a  lea     r8, [rsp+1B0h+var_180]
0x1800e3e6f  mov     rdx, rsi
0x1800e3e72  mov     rcx, [rbp+0B0h+arg_10]
0x1800e3e79  call    cs:__imp_GdipEnumerateMetafileDestPoint
0x1800e3e7f  mov     eax, [rsp+1B0h+var_178]
0x1800e3e83  mov     [rbx+64h], eax
0x1800e3e86  mov     rdx, rsi
0x1800e3e89  mov     rcx, [rbp+0B0h+arg_10]
0x1800e3e90  call    sub_1800E46F4
0x1800e3e95  test    al, al
0x1800e3e97  jz      loc_1800E3F38
0x1800e3e9d  lea     edx, [r12+4]
0x1800e3ea2  mov     rcx, [rbp+0B0h+arg_10]
0x1800e3ea9  call    cs:__imp_GdipSetSmoothingMode
0x1800e3eaf  mov     r9d, 254554Ch
0x1800e3eb5  mov     ecx, eax
0x1800e3eb7  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800e3ebc  mov     [rbp+0B0h+arg_18], r12
0x1800e3ec3  mov     [rbp+0B0h+arg_8], 7
0x1800e3ecd  lea     rax, [rbp+0B0h+arg_18]
0x1800e3ed4  mov     [rsp+1B0h+var_188], rax
0x1800e3ed9  mov     [rsp+1B0h+var_190], r12
0x1800e3ede  lea     r9d, [r12+4]
0x1800e3ee3  lea     r8, [rbp+0B0h+arg_8]
0x1800e3eea  mov     rdx, rsi
0x1800e3eed  mov     rcx, [rbp+0B0h+arg_10]
0x1800e3ef4  call    cs:__imp_GdipConvertToEmfPlus
0x1800e3efa  test    eax, eax
0x1800e3efc  jnz     short loc_1800E3F1F
0x1800e3efe  mov     rax, [rbp+0B0h+arg_18]
0x1800e3f05  test    rax, rax
0x1800e3f08  jz      short loc_1800E3F38
0x1800e3f0a  mov     rsi, rax
0x1800e3f0d  mov     [rbp+0B0h+arg_18], r12
0x1800e3f14  mov     rcx, rdi
0x1800e3f17  call    ?Empty@?$TGpHolder@VGpBitmap@Gdiplus@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGpHolder<Gdiplus::GpBitmap>::Empty(void)
0x1800e3f1c  mov     [rdi], rsi
0x1800e3f1f  mov     rcx, [rbp+0B0h+arg_18]
0x1800e3f26  test    rcx, rcx
0x1800e3f29  jz      short loc_1800E3F38
0x1800e3f2b  call    cs:__imp_GdipDisposeImage
0x1800e3f31  mov     [rbp+0B0h+arg_18], r12
0x1800e3f38  lea     rcx, [rsp+1B0h+var_150]; this
0x1800e3f3d  call    ??0MetafileContent@GEL@@QEAA@XZ; GEL::MetafileContent::MetafileContent(void)
0x1800e3f42  mov     [rsp+1B0h+var_188], r12
0x1800e3f47  lea     rax, [rsp+1B0h+var_150]
0x1800e3f4c  mov     [rsp+1B0h+var_190], rax
0x1800e3f51  lea     r9, sub_180105350
0x1800e3f58  lea     r8, [rsp+1B0h+var_180]
0x1800e3f5d  mov     rdx, rsi
0x1800e3f60  mov     rcx, [rbp+0B0h+arg_10]
0x1800e3f67  call    cs:__imp_GdipEnumerateMetafileDestPoint
0x1800e3f6d  mov     al, [rbp+0B0h+var_C6]
0x1800e3f70  mov     [rbx+68h], al
0x1800e3f73  mov     al, [rbp+0B0h+var_C7]
0x1800e3f76  mov     [rbx+69h], al
0x1800e3f79  mov     al, [rbp+0B0h+var_C2]
0x1800e3f7c  mov     [rbx+29h], al
0x1800e3f7f  movss   xmm1, cs:__real@3f800000
0x1800e3f87  movaps  xmm0, xmm1
0x1800e3f8a  minss   xmm0, [rbp+0B0h+var_100]
0x1800e3f8f  movss   dword ptr [rbx+5Ch], xmm0
0x1800e3f94  minss   xmm1, [rbp+0B0h+var_FC]
0x1800e3f99  movss   dword ptr [rbx+60h], xmm1
0x1800e3f9e  xor     edx, edx; Val
0x1800e3fa0  mov     r8d, 8Ch; Size
0x1800e3fa6  lea     rcx, [rbp+0B0h+var_C0]; void *
0x1800e3faa  call    memset_0
0x1800e3faf  lea     rdx, [rbp+0B0h+var_C0]
0x1800e3fb3  mov     rcx, rsi
0x1800e3fb6  call    cs:__imp_GdipGetMetafileHeaderFromMetafile
0x1800e3fbc  test    eax, eax
0x1800e3fbe  jnz     short loc_1800E4011
0x1800e3fc0  mov     eax, [rbp+0B0h+var_BC]
0x1800e3fc3  mov     [rbx+48h], rax
0x1800e3fc7  lea     rcx, [rsp+1B0h+var_148]
0x1800e3fcc  call    ??1?$vector@PEAVAnimatableProgressHolder@GEL@@V?$allocator@PEAVAnimatableProgressHolder@GEL@@@std@@@std@@QEAA@XZ; std::vector<GEL::AnimatableProgressHolder *>::~vector<GEL::AnimatableProgressHolder *>(void)
0x1800e3fd1  nop
0x1800e3fd2  test    r14, r14
0x1800e3fd5  jz      short loc_1800E3FE1
0x1800e3fd7  mov     rcx, r14; hdc
0x1800e3fda  call    cs:__imp_DeleteDC
0x1800e3fe0  nop
0x1800e3fe1  mov     rcx, [rbp+0B0h+arg_10]
0x1800e3fe8  test    rcx, rcx
0x1800e3feb  jz      short loc_1800E3FF3
0x1800e3fed  call    cs:__imp_GdipDeleteGraphics
0x1800e3ff3  add     rsp, 188h
0x1800e3ffa  pop     r14
0x1800e3ffc  pop     r12
0x1800e3ffe  pop     rdi
0x1800e3fff  pop     rsi
0x1800e4000  pop     rbx
0x1800e4001  pop     rbp
0x1800e4002  retn
0x1800e4003  xor     edx, edx
0x1800e4005  mov     ecx, 1E55E058h
0x1800e400a  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800e4010  nop
0x1800e4011  lea     r9, aVectorimageres_2; "VectorImageResource::ProcessMetafile: u"...
0x1800e4018  mov     edx, 90h
0x1800e401d  mov     ecx, 7963D7h
0x1800e4022  mov     r8d, 0Fh
0x1800e4028  call    cs:__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z; Mso::Logging::MsoSendTraceTag(ulong,Mso::Logging::Category,Mso::Logging::Severity,wchar_t const *)
0x1800e402e  jmp     short loc_1800E3FC7
0x1800e4030  mov     [rbx+64h], r12d
0x1800e4034  jmp     short loc_1800E3FF3
```
