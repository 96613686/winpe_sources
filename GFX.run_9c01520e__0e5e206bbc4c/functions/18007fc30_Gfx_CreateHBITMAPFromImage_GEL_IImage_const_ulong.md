# Gfx::CreateHBITMAPFromImage(GEL::IImage const &,ulong)

- ea: `0x18007fc30`
- end: `0x18007fd24`
- name: `?CreateHBITMAPFromImage@Gfx@@YAPEAUHBITMAP__@@AEBUIImage@GEL@@K@Z`
- size: `244`
- prototype: `HBITMAP __fastcall(Gfx *__hidden this, const struct GEL::IImage *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800ce890`

## callees

- `0x180057e70`
- `0x18007f754`
- `0x18007f850`
- `0x18007fa70`
- `0x18007fc30`
- `0x180090490`

## import_xrefs

- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18007fcfa`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18007fd13`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18007fcfa`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18007fd13`
- `gdiplus!GdipCreateHBITMAPFromBitmap` at `0x18007fcc5`
- `gdiplus!GdipCreateHBITMAPFromBitmap` at `0x18007fcc5`
- `gdiplus!GdipGetImageType` at `0x18007fc76`
- `gdiplus!GdipGetImageType` at `0x18007fc76`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Gfx::CreateHBITMAPFromImage(Gfx *this, const struct GEL::IImage *a2)
{
  int v2; // edi
  unsigned int ImageType; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  unsigned int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rbx
  _BYTE v12[24]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v13; // [rsp+38h] [rbp-10h]
  int v14; // [rsp+50h] [rbp+8h] BYREF
  __int64 v15; // [rsp+60h] [rbp+18h] BYREF

  v2 = (int)a2;
  if ( !(*(unsigned __int8 (__fastcall **)(Gfx *))(*(_QWORD *)this + 88LL))(this) )
  {
    MsoShipAssertTagProc(24679045);
    Ofc::CInvalidParamException::ThrowTag(0x45F192u);
LABEL_5:
    MsoShipAssertTagProc(24679046);
    Ofc::CInvalidParamException::ThrowTag(0x45F193u);
    __debugbreak();
  }
  GEL::IImage::GpImageLock::GpImageLock((GEL::IImage::GpImageLock *)v12, this, 1u);
  v14 = 0;
  ImageType = GdipGetImageType(v13, &v14);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(ImageType, v5, v6, 38871075);
  if ( v14 != 1 )
    goto LABEL_5;
  v15 = 0;
  v7 = GdipCreateHBITMAPFromBitmap(v13, &v15, v2 & 0xFF00 | BYTE2(v2) | (((unsigned __int8)v2 | 0xFFFFFF00) << 16));
  Gfx::GdipStatus_ThrowOnFailureMessageTag(v7, v8, v9, 509641548);
  v10 = v15;
  GEL::IImage::GpImageLock::~GpImageLock((GEL::IImage::GpImageLock *)v12);
  return v10;
}

```

## disassembly

```asm
0x18007fc30  mov     [rsp+arg_8], rbx
0x18007fc35  push    rdi
0x18007fc36  sub     rsp, 40h
0x18007fc3a  mov     edi, edx
0x18007fc3c  mov     rbx, rcx
0x18007fc3f  mov     rax, [rcx]
0x18007fc42  mov     rax, [rax+58h]
0x18007fc46  call    cs:__guard_dispatch_icall_fptr
0x18007fc4c  test    al, al
0x18007fc4e  jz      loc_18007FCF5
0x18007fc54  mov     r8b, 1; unsigned __int8
0x18007fc57  mov     rdx, rbx; struct GEL::IImage *
0x18007fc5a  lea     rcx, [rsp+48h+var_28]; this
0x18007fc5f  call    ??0GpImageLock@IImage@GEL@@QEAA@AEBU12@E@Z; GEL::IImage::GpImageLock::GpImageLock(GEL::IImage const &,uchar)
0x18007fc64  mov     [rsp+48h+arg_0], 0
0x18007fc6c  lea     rdx, [rsp+48h+arg_0]
0x18007fc71  mov     rcx, [rsp+48h+var_10]
0x18007fc76  call    cs:__imp_GdipGetImageType
0x18007fc7c  mov     r9d, 2512023h
0x18007fc82  mov     ecx, eax
0x18007fc84  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18007fc89  cmp     [rsp+48h+arg_0], 1
0x18007fc8e  jnz     short loc_18007FD0E
0x18007fc90  mov     [rsp+48h+arg_10], 0
0x18007fc99  movzx   ecx, di
0x18007fc9c  movzx   r8d, dil
0x18007fca0  mov     edx, 0FFFFFF00h
0x18007fca5  or      r8d, edx
0x18007fca8  shl     r8d, 10h
0x18007fcac  shr     edi, 10h
0x18007fcaf  movzx   eax, dil
0x18007fcb3  or      r8d, eax
0x18007fcb6  and     ecx, edx
0x18007fcb8  or      r8d, ecx
0x18007fcbb  lea     rdx, [rsp+48h+arg_10]
0x18007fcc0  mov     rcx, [rsp+48h+var_10]
0x18007fcc5  call    cs:__imp_GdipCreateHBITMAPFromBitmap
0x18007fccb  mov     r9d, 1E60834Ch
0x18007fcd1  mov     ecx, eax
0x18007fcd3  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18007fcd8  mov     rbx, [rsp+48h+arg_10]
0x18007fcdd  lea     rcx, [rsp+48h+var_28]; this
0x18007fce2  call    ??1GpImageLock@IImage@GEL@@QEAA@XZ; GEL::IImage::GpImageLock::~GpImageLock(void)
0x18007fce7  mov     rax, rbx
0x18007fcea  mov     rbx, [rsp+48h+arg_8]
0x18007fcef  add     rsp, 40h
0x18007fcf3  pop     rdi
0x18007fcf4  retn
0x18007fcf5  mov     ecx, 1789285h
0x18007fcfa  call    cs:__imp_MsoShipAssertTagProc
0x18007fd00  mov     ecx, 45F192h; unsigned int
0x18007fd05  call    ?ThrowTag@CInvalidParamException@Ofc@@SAXK@Z; Ofc::CInvalidParamException::ThrowTag(ulong)
0x18007fd0a  nop
0x18007fd0b  jmp     short $+2
0x18007fd0d  nop
0x18007fd0e  mov     ecx, 1789286h
0x18007fd13  call    cs:__imp_MsoShipAssertTagProc
0x18007fd19  mov     ecx, 45F193h; unsigned int
0x18007fd1e  call    ?ThrowTag@CInvalidParamException@Ofc@@SAXK@Z; Ofc::CInvalidParamException::ThrowTag(ulong)
0x18007fd23  int     3; Trap to Debugger
```
