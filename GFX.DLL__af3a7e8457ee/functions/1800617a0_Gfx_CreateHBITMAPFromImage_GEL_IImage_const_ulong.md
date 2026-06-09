# Gfx::CreateHBITMAPFromImage(GEL::IImage const &,ulong)

- ea: `0x1800617a0`
- end: `0x180061894`
- name: `?CreateHBITMAPFromImage@Gfx@@YAPEAUHBITMAP__@@AEBUIImage@GEL@@K@Z`
- size: `244`
- prototype: `HBITMAP __fastcall(Gfx *__hidden this, const struct GEL::IImage *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800d0510`

## callees

- `0x1800573f0`
- `0x1800617a0`
- `0x180062394`
- `0x180062490`
- `0x1800626b0`
- `0x1800dc27c`

## import_xrefs

- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18006186a`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180061883`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18006186a`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180061883`
- `gdiplus!GdipCreateHBITMAPFromBitmap` at `0x180061835`
- `gdiplus!GdipCreateHBITMAPFromBitmap` at `0x180061835`
- `gdiplus!GdipGetImageType` at `0x1800617e6`
- `gdiplus!GdipGetImageType` at `0x1800617e6`

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
0x1800617a0  mov     [rsp+arg_8], rbx
0x1800617a5  push    rdi
0x1800617a6  sub     rsp, 40h
0x1800617aa  mov     edi, edx
0x1800617ac  mov     rbx, rcx
0x1800617af  mov     rax, [rcx]
0x1800617b2  mov     rax, [rax+58h]
0x1800617b6  call    cs:__guard_dispatch_icall_fptr
0x1800617bc  test    al, al
0x1800617be  jz      loc_180061865
0x1800617c4  mov     r8b, 1; unsigned __int8
0x1800617c7  mov     rdx, rbx; struct GEL::IImage *
0x1800617ca  lea     rcx, [rsp+48h+var_28]; this
0x1800617cf  call    ??0GpImageLock@IImage@GEL@@QEAA@AEBU12@E@Z; GEL::IImage::GpImageLock::GpImageLock(GEL::IImage const &,uchar)
0x1800617d4  mov     [rsp+48h+arg_0], 0
0x1800617dc  lea     rdx, [rsp+48h+arg_0]
0x1800617e1  mov     rcx, [rsp+48h+var_10]
0x1800617e6  call    cs:__imp_GdipGetImageType
0x1800617ec  mov     r9d, 2512023h
0x1800617f2  mov     ecx, eax
0x1800617f4  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800617f9  cmp     [rsp+48h+arg_0], 1
0x1800617fe  jnz     short loc_18006187E
0x180061800  mov     [rsp+48h+arg_10], 0
0x180061809  movzx   ecx, di
0x18006180c  movzx   r8d, dil
0x180061810  mov     edx, 0FFFFFF00h
0x180061815  or      r8d, edx
0x180061818  shl     r8d, 10h
0x18006181c  shr     edi, 10h
0x18006181f  movzx   eax, dil
0x180061823  or      r8d, eax
0x180061826  and     ecx, edx
0x180061828  or      r8d, ecx
0x18006182b  lea     rdx, [rsp+48h+arg_10]
0x180061830  mov     rcx, [rsp+48h+var_10]
0x180061835  call    cs:__imp_GdipCreateHBITMAPFromBitmap
0x18006183b  mov     r9d, 1E60834Ch
0x180061841  mov     ecx, eax
0x180061843  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180061848  mov     rbx, [rsp+48h+arg_10]
0x18006184d  lea     rcx, [rsp+48h+var_28]; this
0x180061852  call    ??1GpImageLock@IImage@GEL@@QEAA@XZ; GEL::IImage::GpImageLock::~GpImageLock(void)
0x180061857  mov     rax, rbx
0x18006185a  mov     rbx, [rsp+48h+arg_8]
0x18006185f  add     rsp, 40h
0x180061863  pop     rdi
0x180061864  retn
0x180061865  mov     ecx, 1789285h
0x18006186a  call    cs:__imp_MsoShipAssertTagProc
0x180061870  mov     ecx, 45F192h; unsigned int
0x180061875  call    ?ThrowTag@CInvalidParamException@Ofc@@SAXK@Z; Ofc::CInvalidParamException::ThrowTag(ulong)
0x18006187a  nop
0x18006187b  jmp     short $+2
0x18006187d  nop
0x18006187e  mov     ecx, 1789286h
0x180061883  call    cs:__imp_MsoShipAssertTagProc
0x180061889  mov     ecx, 45F193h; unsigned int
0x18006188e  call    ?ThrowTag@CInvalidParamException@Ofc@@SAXK@Z; Ofc::CInvalidParamException::ThrowTag(ulong)
0x180061893  int     3; Trap to Debugger
```
