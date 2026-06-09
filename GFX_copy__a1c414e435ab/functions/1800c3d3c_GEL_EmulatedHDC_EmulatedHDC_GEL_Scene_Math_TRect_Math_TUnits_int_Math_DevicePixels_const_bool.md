# GEL::EmulatedHDC::EmulatedHDC(GEL::Scene &,Math::TRect<Math::TUnits<int,Math::DevicePixels>> const &,bool)

- ea: `0x1800c3d3c`
- end: `0x1800c3f85`
- name: `??0EmulatedHDC@GEL@@QEAA@AEAVScene@1@AEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@_N@Z`
- size: `585`
- prototype: `__int64 __fastcall(GEL::EmulatedHDC *this)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x1800c2fdc`

## callees

- `0x1800573f0`
- `0x1800588a4`
- `0x180062394`
- `0x180064bb8`
- `0x180076dfc`
- `0x1800a9b44`
- `0x1800c32b0`
- `0x1800c3d3c`
- `0x1800c3f90`
- `0x1800c3fd8`
- `0x1800c52b0`
- `0x1800c5f50`
- `0x1801828e0`

## import_xrefs

- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1800c3f30`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1800c3f30`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800c3f4c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800c3f4c`
- `GDI32!DeleteObject` at `0x1800c3e75`
- `GDI32!DeleteObject` at `0x1800c3e75`
- `gdiplus!GdipGetRegionHRgn` at `0x1800c3dfa`
- `gdiplus!GdipGetRegionHRgn` at `0x1800c3dfa`
- `gdiplus!GdipDeleteRegion` at `0x1800c3e5e`
- `gdiplus!GdipDeleteRegion` at `0x1800c3e5e`
- `gdiplus!GdipCreateRegion` at `0x1800c3db4`
- `gdiplus!GdipCreateRegion` at `0x1800c3db4`
- `gdiplus!GdipGetClip` at `0x1800c3dcf`
- `gdiplus!GdipGetClip` at `0x1800c3dcf`
- `gdiplus!GdipGetDC` at `0x1800c3e31`
- `gdiplus!GdipGetDC` at `0x1800c3e31`

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
0x1800c3d3c  mov     [rsp-18h+arg_10], rbx
0x1800c3d41  mov     [rsp-18h+arg_18], rsi
0x1800c3d46  push    rbp
0x1800c3d47  push    rdi
0x1800c3d48  push    r14
0x1800c3d4a  mov     rbp, rsp
0x1800c3d4d  sub     rsp, 20h
0x1800c3d51  mov     bl, r9b
0x1800c3d54  mov     rdi, r8
0x1800c3d57  mov     r14, rdx
0x1800c3d5a  mov     rsi, rcx
0x1800c3d5d  call    ??$?0$$V@?$RefCountedObject@UIEmulatedHDC@GEL@@$$V@Mso@@IEAA@XZ; Mso::RefCountedObject<GEL::IEmulatedHDC,>::RefCountedObject<GEL::IEmulatedHDC,>(void)
0x1800c3d62  lea     rcx, ??_7EmulatedHDC@GEL@@6B@; const GEL::EmulatedHDC::`vftable'
0x1800c3d69  mov     [rsi], rcx
0x1800c3d6c  mov     [rsi+10h], rdx
0x1800c3d70  mov     rcx, rdx; this
0x1800c3d73  call    ?GetEmulatedGpGraphics@Scene@GEL@@QEAAPEAVGpGraphics@Gdiplus@@XZ; GEL::Scene::GetEmulatedGpGraphics(void)
0x1800c3d78  mov     [rsi+18h], rax
0x1800c3d7c  mov     byte ptr [rsi+28h], 0
0x1800c3d80  mov     [rsi+29h], bl
0x1800c3d83  movups  xmm0, xmmword ptr [rdi]
0x1800c3d86  movdqu  xmmword ptr [rsi+2Ch], xmm0
0x1800c3d8b  mov     dword ptr [rsi+3Ch], 0
0x1800c3d92  mov     rax, [rsi+10h]
0x1800c3d96  cmp     byte ptr [rax+30h], 0
0x1800c3d9a  jnz     loc_1800C3F2B
0x1800c3da0  mov     [rbp+ho], 0
0x1800c3da8  mov     [rbp+arg_0], 0
0x1800c3db0  lea     rcx, [rbp+arg_0]
0x1800c3db4  call    cs:__imp_GdipCreateRegion
0x1800c3dba  mov     r9d, 2512019h
0x1800c3dc0  mov     ecx, eax
0x1800c3dc2  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800c3dc7  mov     rdx, [rbp+arg_0]
0x1800c3dcb  mov     rcx, [rsi+18h]
0x1800c3dcf  call    cs:__imp_GdipGetClip
0x1800c3dd5  mov     r9d, 251201Ah
0x1800c3ddb  mov     ecx, eax
0x1800c3ddd  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800c3de2  nop
0x1800c3de3  cmp     [rbp+ho], 0
0x1800c3de8  jnz     loc_1800C3F45
0x1800c3dee  lea     r8, [rbp+ho]
0x1800c3df2  mov     rdx, [rsi+18h]
0x1800c3df6  mov     rcx, [rbp+arg_0]
0x1800c3dfa  call    cs:__imp_GdipGetRegionHRgn
0x1800c3e00  mov     r9d, 251201Bh
0x1800c3e06  mov     ecx, eax
0x1800c3e08  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800c3e0d  mov     rax, [rsi+10h]
0x1800c3e11  mov     rcx, [rax+10h]
0x1800c3e15  mov     rax, [rcx]
0x1800c3e18  mov     rax, [rax+1D0h]
0x1800c3e1f  call    cs:__guard_dispatch_icall_fptr
0x1800c3e25  cmp     al, 3
0x1800c3e27  jz      short loc_1800C3E91
0x1800c3e29  lea     rdx, [rsi+20h]
0x1800c3e2d  mov     rcx, [rsi+18h]
0x1800c3e31  call    cs:__imp_GdipGetDC
0x1800c3e37  mov     r9d, 251201Ch
0x1800c3e3d  mov     ecx, eax
0x1800c3e3f  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800c3e44  mov     rdx, [rbp+ho]; HRGN
0x1800c3e48  mov     rcx, rsi; this
0x1800c3e4b  call    ?ApplyClipToHDC@EmulatedHDC@GEL@@AEAAXPEAUHRGN__@@@Z; GEL::EmulatedHDC::ApplyClipToHDC(HRGN__ *)
0x1800c3e50  mov     byte ptr [r14+30h], 1
0x1800c3e55  mov     rcx, [rbp+arg_0]
0x1800c3e59  test    rcx, rcx
0x1800c3e5c  jz      short loc_1800C3E6C
0x1800c3e5e  call    cs:__imp_GdipDeleteRegion
0x1800c3e64  mov     [rbp+arg_0], 0
0x1800c3e6c  mov     rcx, [rbp+ho]; ho
0x1800c3e70  test    rcx, rcx
0x1800c3e73  jz      short loc_1800C3E7B
0x1800c3e75  call    cs:__imp_DeleteObject
0x1800c3e7b  mov     rax, rsi
0x1800c3e7e  mov     rbx, [rsp+20h+arg_10]
0x1800c3e83  mov     rsi, [rsp+20h+arg_18]
0x1800c3e88  add     rsp, 20h
0x1800c3e8c  pop     r14
0x1800c3e8e  pop     rdi
0x1800c3e8f  pop     rbp
0x1800c3e90  retn
0x1800c3e91  mov     rax, [rsi+10h]
0x1800c3e95  mov     rbx, [rax+10h]
0x1800c3e99  mov     rax, [rbx]
0x1800c3e9c  mov     rcx, rbx
0x1800c3e9f  mov     rax, [rax+3A0h]
0x1800c3ea6  call    cs:__guard_dispatch_icall_fptr
0x1800c3eac  mov     rcx, rax; this
0x1800c3eaf  call    ?GetGpGraphics@GraphicsSurface@GEL@@QEAAAEAVGpGraphics@Gdiplus@@XZ; GEL::GraphicsSurface::GetGpGraphics(void)
0x1800c3eb4  mov     [rsi+18h], rax
0x1800c3eb8  mov     rax, [rbx]
0x1800c3ebb  mov     rcx, rbx
0x1800c3ebe  mov     rax, [rax+308h]
0x1800c3ec5  call    cs:__guard_dispatch_icall_fptr
0x1800c3ecb  test    al, al
0x1800c3ecd  jz      loc_1800C3E29
0x1800c3ed3  mov     rax, [rbx]
0x1800c3ed6  mov     rcx, rbx
0x1800c3ed9  mov     rax, [rax+328h]
0x1800c3ee0  call    cs:__guard_dispatch_icall_fptr
0x1800c3ee6  test    al, al
0x1800c3ee8  jz      loc_1800C3E29
0x1800c3eee  xor     r8d, r8d
0x1800c3ef1  mov     edx, 5F78h
0x1800c3ef6  mov     rcx, [rbx]
0x1800c3ef9  call    __castguard_slow_path_check_user_handled
0x1800c3efe  mov     rcx, rbx; this
0x1800c3f01  call    ?EnsureMetafileGraphicsSurface@BitmapBasedPrinter@GEL@@IEAAAEAVGraphicsSurface@2@XZ; GEL::BitmapBasedPrinter::EnsureMetafileGraphicsSurface(void)
0x1800c3f06  mov     rcx, rax; this
0x1800c3f09  call    ?GetGpGraphics@GraphicsSurface@GEL@@QEAAAEAVGpGraphics@Gdiplus@@XZ; GEL::GraphicsSurface::GetGpGraphics(void)
0x1800c3f0e  mov     [rsi+18h], rax
0x1800c3f12  cmp     qword ptr [rbx+230h], 0
0x1800c3f1a  jz      short loc_1800C3F53
0x1800c3f1c  mov     ecx, 1706288h; unsigned int
0x1800c3f21  call    ?ThrowTag@FailureException@GEL@@SAXK@Z; GEL::FailureException::ThrowTag(ulong)
0x1800c3f26  nop
0x1800c3f27  jmp     short loc_1800C3F2A
0x1800c3f2a  nop
0x1800c3f2b  mov     ecx, 2A05C8h
0x1800c3f30  call    cs:__imp_MsoShipAssertTagProc
0x1800c3f36  mov     ecx, 2A05C9h; unsigned int
0x1800c3f3b  call    ?ThrowTag@CInvalidOperationException@Ofc@@SAXK@Z; Ofc::CInvalidOperationException::ThrowTag(ulong)
0x1800c3f40  nop
0x1800c3f41  jmp     short loc_1800C3F44
0x1800c3f44  nop
0x1800c3f45  xor     edx, edx
0x1800c3f47  mov     ecx, 1E3CF50Bh
0x1800c3f4c  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800c3f52  nop
0x1800c3f53  mov     rcx, rbx; this
0x1800c3f56  call    ?StartMetafile@BitmapBasedPrinter@GEL@@QEAAPEAUHDC__@@XZ; GEL::BitmapBasedPrinter::StartMetafile(void)
0x1800c3f5b  mov     [rsi+20h], rax
0x1800c3f5f  test    rax, rax
0x1800c3f62  jnz     short loc_1800C3F6F
0x1800c3f64  mov     ecx, 1706289h; unsigned int
0x1800c3f69  call    ?ThrowTag@CLastErrorException@Ofc@@SAXK@Z; Ofc::CLastErrorException::ThrowTag(ulong)
0x1800c3f6e  int     3; Trap to Debugger
0x1800c3f6f  mov     rdx, [rbp+ho]; HRGN
0x1800c3f73  mov     rcx, rsi; this
0x1800c3f76  call    ?ApplyClipToHDC@EmulatedHDC@GEL@@AEAAXPEAUHRGN__@@@Z; GEL::EmulatedHDC::ApplyClipToHDC(HRGN__ *)
0x1800c3f7b  mov     byte ptr [rsi+28h], 1
0x1800c3f7f  jmp     loc_1800C3E55
```
