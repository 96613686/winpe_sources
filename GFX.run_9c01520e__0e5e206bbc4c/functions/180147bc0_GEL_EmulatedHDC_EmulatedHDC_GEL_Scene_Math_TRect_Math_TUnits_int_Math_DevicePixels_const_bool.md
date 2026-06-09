# GEL::EmulatedHDC::EmulatedHDC(GEL::Scene &,Math::TRect<Math::TUnits<int,Math::DevicePixels>> const &,bool)

- ea: `0x180147bc0`
- end: `0x180147e09`
- name: `??0EmulatedHDC@GEL@@QEAA@AEAVScene@1@AEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@_N@Z`
- size: `585`
- prototype: `__int64 __fastcall(GEL::EmulatedHDC *this)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x180147b1c`

## callees

- `0x180057e70`
- `0x18007376c`
- `0x18007f754`
- `0x1800828c8`
- `0x180083630`
- `0x180087c94`
- `0x1800a4278`
- `0x1800a578c`
- `0x1800cb9c0`
- `0x1800dd460`
- `0x180147bc0`
- `0x180147e0c`
- `0x180186470`

## import_xrefs

- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180147db4`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180147db4`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180147dd0`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180147dd0`
- `GDI32!DeleteObject` at `0x180147cf9`
- `GDI32!DeleteObject` at `0x180147cf9`
- `gdiplus!GdipGetRegionHRgn` at `0x180147c7e`
- `gdiplus!GdipGetRegionHRgn` at `0x180147c7e`
- `gdiplus!GdipDeleteRegion` at `0x180147ce2`
- `gdiplus!GdipDeleteRegion` at `0x180147ce2`
- `gdiplus!GdipCreateRegion` at `0x180147c38`
- `gdiplus!GdipCreateRegion` at `0x180147c38`
- `gdiplus!GdipGetClip` at `0x180147c53`
- `gdiplus!GdipGetClip` at `0x180147c53`
- `gdiplus!GdipGetDC` at `0x180147cb5`
- `gdiplus!GdipGetDC` at `0x180147cb5`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
GEL::EmulatedHDC *__fastcall GEL::EmulatedHDC::EmulatedHDC(GEL::EmulatedHDC *this, __int64 a2, _OWORD *a3, char a4)
{
  GEL::BitmapBasedPrinter *v4; // rbx
  GEL::Scene *v8; // rdx
  unsigned int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  unsigned int Clip; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  unsigned int RegionHRgn; // eax
  __int64 v16; // rdx
  __int64 v17; // r8
  unsigned int DC; // eax
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rdx
  GEL::GraphicsSurface *v23; // rax
  GEL::GraphicsSurface *v24; // rax
  HDC started; // rax
  __int64 v26; // [rsp+40h] [rbp+20h] BYREF
  HGDIOBJ ho; // [rsp+48h] [rbp+28h] BYREF

  LOBYTE(v4) = a4;
  Mso::RefCountedObject<GEL::IEmulatedHDC,>::RefCountedObject<GEL::IEmulatedHDC,>();
  *(_QWORD *)this = &GEL::EmulatedHDC::`vftable';
  *((_QWORD *)this + 2) = v8;
  *((_QWORD *)this + 3) = GEL::Scene::GetEmulatedGpGraphics(v8);
  *((_BYTE *)this + 40) = 0;
  *((_BYTE *)this + 41) = (_BYTE)v4;
  *(_OWORD *)((char *)this + 44) = *a3;
  *((_DWORD *)this + 15) = 0;
  if ( *(_BYTE *)(*((_QWORD *)this + 2) + 48LL) )
    goto LABEL_14;
  ho = 0;
  v26 = 0;
  v9 = GdipCreateRegion(&v26);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(v9, v10, v11, 38871065);
  Clip = GdipGetClip(*((_QWORD *)this + 3), v26);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(Clip, v13, v14, 38871066);
  if ( ho )
  {
LABEL_15:
    CrashWithRecovery(0x1E3CF50Bu, 0);
    goto LABEL_16;
  }
  RegionHRgn = GdipGetRegionHRgn(v26, *((_QWORD *)this + 3), &ho);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(RegionHRgn, v16, v17, 38871067);
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 2) + 16LL) + 464LL))(*(_QWORD *)(*((_QWORD *)this + 2) + 16LL)) != 3
    || (v4 = *(GEL::BitmapBasedPrinter **)(*((_QWORD *)this + 2) + 16LL),
        v23 = (GEL::GraphicsSurface *)(*(__int64 (__fastcall **)(GEL::BitmapBasedPrinter *))(*(_QWORD *)v4 + 928LL))(v4),
        *((_QWORD *)this + 3) = GEL::GraphicsSurface::GetGpGraphics(v23),
        !(*(unsigned __int8 (__fastcall **)(GEL::BitmapBasedPrinter *))(*(_QWORD *)v4 + 776LL))(v4))
    || !(*(unsigned __int8 (__fastcall **)(GEL::BitmapBasedPrinter *))(*(_QWORD *)v4 + 808LL))(v4) )
  {
    DC = GdipGetDC(*((_QWORD *)this + 3), (char *)this + 32);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(DC, v19, v20, 38871068);
    GEL::EmulatedHDC::ApplyClipToHDC(this, (HRGN)ho);
    *(_BYTE *)(a2 + 48) = 1;
    goto LABEL_5;
  }
  _castguard_slow_path_check_user_handled(*(_QWORD *)v4, 24440, 0);
  v24 = GEL::BitmapBasedPrinter::EnsureMetafileGraphicsSurface(v4);
  *((_QWORD *)this + 3) = GEL::GraphicsSurface::GetGpGraphics(v24);
  if ( *((_QWORD *)v4 + 70) )
  {
    GEL::FailureException::ThrowTag(0x1706288u);
LABEL_14:
    MsoShipAssertTagProc(2753992);
    Ofc::CInvalidOperationException::ThrowTag(0x2A05C9u);
    goto LABEL_15;
  }
LABEL_16:
  started = GEL::BitmapBasedPrinter::StartMetafile(v4);
  *((_QWORD *)this + 4) = started;
  if ( !started )
  {
    Ofc::CLastErrorException::ThrowTag(0x1706289u);
    __debugbreak();
  }
  GEL::EmulatedHDC::ApplyClipToHDC(this, (HRGN)ho);
  *((_BYTE *)this + 40) = 1;
LABEL_5:
  if ( v26 )
  {
    GdipDeleteRegion(v26, v21);
    v26 = 0;
  }
  if ( ho )
    DeleteObject(ho);
  return this;
}

```

## disassembly

```asm
0x180147bc0  mov     [rsp-18h+arg_10], rbx
0x180147bc5  mov     [rsp-18h+arg_18], rsi
0x180147bca  push    rbp
0x180147bcb  push    rdi
0x180147bcc  push    r14
0x180147bce  mov     rbp, rsp
0x180147bd1  sub     rsp, 20h
0x180147bd5  mov     bl, r9b
0x180147bd8  mov     rdi, r8
0x180147bdb  mov     r14, rdx
0x180147bde  mov     rsi, rcx
0x180147be1  call    ??$?0$$V@?$RefCountedObject@UIEmulatedHDC@GEL@@$$V@Mso@@IEAA@XZ; Mso::RefCountedObject<GEL::IEmulatedHDC,>::RefCountedObject<GEL::IEmulatedHDC,>(void)
0x180147be6  lea     rcx, ??_7EmulatedHDC@GEL@@6B@; const GEL::EmulatedHDC::`vftable'
0x180147bed  mov     [rsi], rcx
0x180147bf0  mov     [rsi+10h], rdx
0x180147bf4  mov     rcx, rdx; this
0x180147bf7  call    ?GetEmulatedGpGraphics@Scene@GEL@@QEAAPEAVGpGraphics@Gdiplus@@XZ; GEL::Scene::GetEmulatedGpGraphics(void)
0x180147bfc  mov     [rsi+18h], rax
0x180147c00  mov     byte ptr [rsi+28h], 0
0x180147c04  mov     [rsi+29h], bl
0x180147c07  movups  xmm0, xmmword ptr [rdi]
0x180147c0a  movdqu  xmmword ptr [rsi+2Ch], xmm0
0x180147c0f  mov     dword ptr [rsi+3Ch], 0
0x180147c16  mov     rax, [rsi+10h]
0x180147c1a  cmp     byte ptr [rax+30h], 0
0x180147c1e  jnz     loc_180147DAF
0x180147c24  mov     [rbp+ho], 0
0x180147c2c  mov     [rbp+arg_0], 0
0x180147c34  lea     rcx, [rbp+arg_0]
0x180147c38  call    cs:__imp_GdipCreateRegion
0x180147c3e  mov     r9d, 2512019h
0x180147c44  mov     ecx, eax
0x180147c46  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180147c4b  mov     rdx, [rbp+arg_0]
0x180147c4f  mov     rcx, [rsi+18h]
0x180147c53  call    cs:__imp_GdipGetClip
0x180147c59  mov     r9d, 251201Ah
0x180147c5f  mov     ecx, eax
0x180147c61  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180147c66  nop
0x180147c67  cmp     [rbp+ho], 0
0x180147c6c  jnz     loc_180147DC9
0x180147c72  lea     r8, [rbp+ho]
0x180147c76  mov     rdx, [rsi+18h]
0x180147c7a  mov     rcx, [rbp+arg_0]
0x180147c7e  call    cs:__imp_GdipGetRegionHRgn
0x180147c84  mov     r9d, 251201Bh
0x180147c8a  mov     ecx, eax
0x180147c8c  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180147c91  mov     rax, [rsi+10h]
0x180147c95  mov     rcx, [rax+10h]
0x180147c99  mov     rax, [rcx]
0x180147c9c  mov     rax, [rax+1D0h]
0x180147ca3  call    cs:__guard_dispatch_icall_fptr
0x180147ca9  cmp     al, 3
0x180147cab  jz      short loc_180147D15
0x180147cad  lea     rdx, [rsi+20h]
0x180147cb1  mov     rcx, [rsi+18h]
0x180147cb5  call    cs:__imp_GdipGetDC
0x180147cbb  mov     r9d, 251201Ch
0x180147cc1  mov     ecx, eax
0x180147cc3  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180147cc8  mov     rdx, [rbp+ho]; HRGN
0x180147ccc  mov     rcx, rsi; this
0x180147ccf  call    ?ApplyClipToHDC@EmulatedHDC@GEL@@AEAAXPEAUHRGN__@@@Z; GEL::EmulatedHDC::ApplyClipToHDC(HRGN__ *)
0x180147cd4  mov     byte ptr [r14+30h], 1
0x180147cd9  mov     rcx, [rbp+arg_0]
0x180147cdd  test    rcx, rcx
0x180147ce0  jz      short loc_180147CF0
0x180147ce2  call    cs:__imp_GdipDeleteRegion
0x180147ce8  mov     [rbp+arg_0], 0
0x180147cf0  mov     rcx, [rbp+ho]; ho
0x180147cf4  test    rcx, rcx
0x180147cf7  jz      short loc_180147CFF
0x180147cf9  call    cs:__imp_DeleteObject
0x180147cff  mov     rax, rsi
0x180147d02  mov     rbx, [rsp+20h+arg_10]
0x180147d07  mov     rsi, [rsp+20h+arg_18]
0x180147d0c  add     rsp, 20h
0x180147d10  pop     r14
0x180147d12  pop     rdi
0x180147d13  pop     rbp
0x180147d14  retn
0x180147d15  mov     rax, [rsi+10h]
0x180147d19  mov     rbx, [rax+10h]
0x180147d1d  mov     rax, [rbx]
0x180147d20  mov     rcx, rbx
0x180147d23  mov     rax, [rax+3A0h]
0x180147d2a  call    cs:__guard_dispatch_icall_fptr
0x180147d30  mov     rcx, rax; this
0x180147d33  call    ?GetGpGraphics@GraphicsSurface@GEL@@QEAAAEAVGpGraphics@Gdiplus@@XZ; GEL::GraphicsSurface::GetGpGraphics(void)
0x180147d38  mov     [rsi+18h], rax
0x180147d3c  mov     rax, [rbx]
0x180147d3f  mov     rcx, rbx
0x180147d42  mov     rax, [rax+308h]
0x180147d49  call    cs:__guard_dispatch_icall_fptr
0x180147d4f  test    al, al
0x180147d51  jz      loc_180147CAD
0x180147d57  mov     rax, [rbx]
0x180147d5a  mov     rcx, rbx
0x180147d5d  mov     rax, [rax+328h]
0x180147d64  call    cs:__guard_dispatch_icall_fptr
0x180147d6a  test    al, al
0x180147d6c  jz      loc_180147CAD
0x180147d72  xor     r8d, r8d
0x180147d75  mov     edx, 5F78h
0x180147d7a  mov     rcx, [rbx]
0x180147d7d  call    __castguard_slow_path_check_user_handled
0x180147d82  mov     rcx, rbx; this
0x180147d85  call    ?EnsureMetafileGraphicsSurface@BitmapBasedPrinter@GEL@@IEAAAEAVGraphicsSurface@2@XZ; GEL::BitmapBasedPrinter::EnsureMetafileGraphicsSurface(void)
0x180147d8a  mov     rcx, rax; this
0x180147d8d  call    ?GetGpGraphics@GraphicsSurface@GEL@@QEAAAEAVGpGraphics@Gdiplus@@XZ; GEL::GraphicsSurface::GetGpGraphics(void)
0x180147d92  mov     [rsi+18h], rax
0x180147d96  cmp     qword ptr [rbx+230h], 0
0x180147d9e  jz      short loc_180147DD7
0x180147da0  mov     ecx, 1706288h; unsigned int
0x180147da5  call    ?ThrowTag@FailureException@GEL@@SAXK@Z; GEL::FailureException::ThrowTag(ulong)
0x180147daa  nop
0x180147dab  jmp     short loc_180147DAE
0x180147dae  nop
0x180147daf  mov     ecx, 2A05C8h
0x180147db4  call    cs:__imp_MsoShipAssertTagProc
0x180147dba  mov     ecx, 2A05C9h; unsigned int
0x180147dbf  call    ?ThrowTag@CInvalidOperationException@Ofc@@SAXK@Z; Ofc::CInvalidOperationException::ThrowTag(ulong)
0x180147dc4  nop
0x180147dc5  jmp     short loc_180147DC8
0x180147dc8  nop
0x180147dc9  xor     edx, edx
0x180147dcb  mov     ecx, 1E3CF50Bh
0x180147dd0  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180147dd6  nop
0x180147dd7  mov     rcx, rbx; this
0x180147dda  call    ?StartMetafile@BitmapBasedPrinter@GEL@@QEAAPEAUHDC__@@XZ; GEL::BitmapBasedPrinter::StartMetafile(void)
0x180147ddf  mov     [rsi+20h], rax
0x180147de3  test    rax, rax
0x180147de6  jnz     short loc_180147DF3
0x180147de8  mov     ecx, 1706289h; unsigned int
0x180147ded  call    ?ThrowTag@CLastErrorException@Ofc@@SAXK@Z; Ofc::CLastErrorException::ThrowTag(ulong)
0x180147df2  int     3; Trap to Debugger
0x180147df3  mov     rdx, [rbp+ho]; HRGN
0x180147df7  mov     rcx, rsi; this
0x180147dfa  call    ?ApplyClipToHDC@EmulatedHDC@GEL@@AEAAXPEAUHRGN__@@@Z; GEL::EmulatedHDC::ApplyClipToHDC(HRGN__ *)
0x180147dff  mov     byte ptr [rsi+28h], 1
0x180147e03  jmp     loc_180147CD9
```
