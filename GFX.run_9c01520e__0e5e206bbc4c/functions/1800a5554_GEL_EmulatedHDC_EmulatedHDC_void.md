# GEL::EmulatedHDC::~EmulatedHDC(void)

- ea: `0x1800a5554`
- end: `0x1800a5702`
- name: `??1EmulatedHDC@GEL@@UEAA@XZ`
- size: `430`
- prototype: `void __fastcall(GEL::EmulatedHDC *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800a5520`

## callees

- `0x180057e70`
- `0x18007efec`
- `0x18007f754`
- `0x1800817d4`
- `0x180083630`
- `0x1800a5554`
- `0x1800a5704`
- `0x1800a71c4`

## import_xrefs

- `GDI32!RestoreDC` at `0x1800a5668`
- `GDI32!RestoreDC` at `0x1800a5668`
- `GDI32!GetClipRgn` at `0x1800a558e`
- `GDI32!GetClipRgn` at `0x1800a558e`
- `GDI32!CreateRectRgn` at `0x1800a5579`
- `GDI32!CreateRectRgn` at `0x1800a5579`
- `GDI32!DeleteObject` at `0x1800a55ed`
- `GDI32!DeleteObject` at `0x1800a55ed`
- `gdiplus!GdipResetClip` at `0x1800a563a`
- `gdiplus!GdipResetClip` at `0x1800a563a`
- `gdiplus!GdipDeleteRegion` at `0x1800a56b7`
- `gdiplus!GdipDeleteRegion` at `0x1800a56b7`
- `gdiplus!GdipSetClipRegion` at `0x1800a5699`
- `gdiplus!GdipSetClipRegion` at `0x1800a5699`
- `gdiplus!GdipReleaseDC` at `0x1800a55b0`
- `gdiplus!GdipReleaseDC` at `0x1800a55b0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
void __fastcall GEL::EmulatedHDC::~EmulatedHDC(GEL::EmulatedHDC *this)
{
  HRGN RectRgn; // rbx
  int ClipRgn; // r15d
  int v4; // edx
  char *v5; // r14
  struct Gdiplus::GpGraphics *EmulatedGpGraphics; // rsi
  unsigned int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  unsigned int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // rax
  _BYTE v15[56]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v16; // [rsp+60h] [rbp+8h] BYREF
  char *v17; // [rsp+68h] [rbp+10h]
  HRGN v18; // [rsp+70h] [rbp+18h]

  *(_QWORD *)this = &GEL::EmulatedHDC::`vftable';
  RectRgn = CreateRectRgn(0, 0, 0, 0);
  v18 = RectRgn;
  ClipRgn = GetClipRgn(*((HDC *)this + 4), RectRgn);
  v4 = *((_DWORD *)this + 15);
  if ( v4 && !*((_BYTE *)this + 41) )
    RestoreDC(*((HDC *)this + 4), v4);
  if ( *((_BYTE *)this + 40) )
  {
    v5 = (char *)this + 16;
    v17 = (char *)this + 16;
    GEL::BitmapBasedPrinter::EndMetafile(*(GEL::BitmapBasedPrinter **)(*((_QWORD *)this + 2) + 16LL));
    EmulatedGpGraphics = GEL::Scene::GetEmulatedGpGraphics(*((GEL::Scene **)this + 2));
    GEL::GDIPixelModeRestorer::GDIPixelModeRestorer((GEL::GDIPixelModeRestorer *)v15, EmulatedGpGraphics);
    if ( ClipRgn == 1 && RectRgn )
    {
      v16 = 0;
      Gfx::HRGNToGpRegion(RectRgn, &v16);
      v10 = GdipSetClipRegion(EmulatedGpGraphics, v16, 0);
      Gfx::GdipStatus_ThrowOnFailureMessageTag(v10, v11, v12, 38871069);
      if ( v16 )
        GdipDeleteRegion(v16, v13);
    }
    else
    {
      v7 = GdipResetClip(EmulatedGpGraphics);
      Gfx::GdipStatus_ThrowOnFailureMessageTag(v7, v8, v9, 38871070);
    }
    GEL::GDIPixelModeRestorer::~GDIPixelModeRestorer((GEL::GDIPixelModeRestorer *)v15);
  }
  else
  {
    GdipReleaseDC(*((_QWORD *)this + 3), *((_QWORD *)this + 4));
    v5 = (char *)this + 16;
    if ( *(_BYTE *)((*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 2) + 16LL) + 624LL))(*(_QWORD *)(*((_QWORD *)this + 2) + 16LL))
                  + 216) )
    {
      v14 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)v5 + 16LL) + 624LL))(*(_QWORD *)(*(_QWORD *)v5 + 16LL));
      (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v14 + 88LL))(v14, (char *)this + 44);
    }
  }
  *(_BYTE *)(*(_QWORD *)v5 + 48LL) = 0;
  if ( RectRgn )
    DeleteObject(RectRgn);
}

```

## disassembly

```asm
0x1800a5554  mov     [rsp+arg_18], rbx
0x1800a5559  push    rsi
0x1800a555a  push    r14
0x1800a555c  push    r15
0x1800a555e  sub     rsp, 40h
0x1800a5562  mov     rsi, rcx
0x1800a5565  lea     rax, ??_7EmulatedHDC@GEL@@6B@; const GEL::EmulatedHDC::`vftable'
0x1800a556c  mov     [rcx], rax
0x1800a556f  xor     r9d, r9d; y2
0x1800a5572  xor     r8d, r8d; x2
0x1800a5575  xor     edx, edx; y1
0x1800a5577  xor     ecx, ecx; x1
0x1800a5579  call    cs:__imp_CreateRectRgn
0x1800a557f  mov     rbx, rax
0x1800a5582  mov     [rsp+58h+arg_10], rax
0x1800a5587  mov     rdx, rax; hrgn
0x1800a558a  mov     rcx, [rsi+20h]; hdc
0x1800a558e  call    cs:__imp_GetClipRgn
0x1800a5594  mov     r15d, eax
0x1800a5597  mov     edx, [rsi+3Ch]; nSavedDC
0x1800a559a  test    edx, edx
0x1800a559c  jnz     loc_1800A565A
0x1800a55a2  cmp     byte ptr [rsi+28h], 0
0x1800a55a6  jnz     short loc_1800A5603
0x1800a55a8  mov     rdx, [rsi+20h]
0x1800a55ac  mov     rcx, [rsi+18h]
0x1800a55b0  call    cs:__imp_GdipReleaseDC
0x1800a55b6  lea     r14, [rsi+10h]
0x1800a55ba  mov     rax, [r14]
0x1800a55bd  mov     rcx, [rax+10h]
0x1800a55c1  mov     rax, [rcx]
0x1800a55c4  mov     rax, [rax+270h]
0x1800a55cb  call    cs:__guard_dispatch_icall_fptr
0x1800a55d1  cmp     byte ptr [rax+0D8h], 0
0x1800a55d8  jnz     loc_1800A56BF
0x1800a55de  mov     rax, [r14]
0x1800a55e1  mov     byte ptr [rax+30h], 0
0x1800a55e5  test    rbx, rbx
0x1800a55e8  jz      short loc_1800A55F4
0x1800a55ea  mov     rcx, rbx; ho
0x1800a55ed  call    cs:__imp_DeleteObject
0x1800a55f3  nop
0x1800a55f4  mov     rbx, [rsp+58h+arg_18]
0x1800a55f9  add     rsp, 40h
0x1800a55fd  pop     r15
0x1800a55ff  pop     r14
0x1800a5601  pop     rsi
0x1800a5602  retn
0x1800a5603  lea     r14, [rsi+10h]
0x1800a5607  mov     [rsp+58h+arg_8], r14
0x1800a560c  mov     rax, [r14]
0x1800a560f  mov     rcx, [rax+10h]; this
0x1800a5613  call    ?EndMetafile@BitmapBasedPrinter@GEL@@QEAAXXZ; GEL::BitmapBasedPrinter::EndMetafile(void)
0x1800a5618  mov     rcx, [r14]; this
0x1800a561b  call    ?GetEmulatedGpGraphics@Scene@GEL@@QEAAPEAVGpGraphics@Gdiplus@@XZ; GEL::Scene::GetEmulatedGpGraphics(void)
0x1800a5620  mov     rsi, rax
0x1800a5623  mov     rdx, rax; struct Gdiplus::GpGraphics *
0x1800a5626  lea     rcx, [rsp+58h+var_38]; this
0x1800a562b  call    ??0GDIPixelModeRestorer@GEL@@QEAA@AEAVGpGraphics@Gdiplus@@@Z; GEL::GDIPixelModeRestorer::GDIPixelModeRestorer(Gdiplus::GpGraphics &)
0x1800a5630  nop
0x1800a5631  cmp     r15d, 1
0x1800a5635  jz      short loc_1800A5673
0x1800a5637  mov     rcx, rsi
0x1800a563a  call    cs:__imp_GdipResetClip
0x1800a5640  mov     r9d, 251201Eh
0x1800a5646  mov     ecx, eax
0x1800a5648  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800a564d  nop
0x1800a564e  lea     rcx, [rsp+58h+var_38]; this
0x1800a5653  call    ??1GDIPixelModeRestorer@GEL@@QEAA@XZ; GEL::GDIPixelModeRestorer::~GDIPixelModeRestorer(void)
0x1800a5658  jmp     short loc_1800A55DE
0x1800a565a  cmp     byte ptr [rsi+29h], 0
0x1800a565e  jnz     loc_1800A55A2
0x1800a5664  mov     rcx, [rsi+20h]; hdc
0x1800a5668  call    cs:__imp_RestoreDC
0x1800a566e  jmp     loc_1800A55A2
0x1800a5673  test    rbx, rbx
0x1800a5676  jz      short loc_1800A5637
0x1800a5678  mov     [rsp+58h+arg_0], 0
0x1800a5681  lea     rdx, [rsp+58h+arg_0]
0x1800a5686  mov     rcx, rbx
0x1800a5689  call    ?HRGNToGpRegion@Gfx@@YAXPEAUHRGN__@@AEAV?$TGpHolder@VGpRegion@Gdiplus@@@GDIPlus@ARC@@@Z; Gfx::HRGNToGpRegion(HRGN__ *,ARC::GDIPlus::TGpHolder<Gdiplus::GpRegion> &)
0x1800a568e  xor     r8d, r8d
0x1800a5691  mov     rdx, [rsp+58h+arg_0]
0x1800a5696  mov     rcx, rsi
0x1800a5699  call    cs:__imp_GdipSetClipRegion
0x1800a569f  mov     r9d, 251201Dh
0x1800a56a5  mov     ecx, eax
0x1800a56a7  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800a56ac  nop
0x1800a56ad  mov     rcx, [rsp+58h+arg_0]
0x1800a56b2  test    rcx, rcx
0x1800a56b5  jz      short loc_1800A564E
0x1800a56b7  call    cs:__imp_GdipDeleteRegion
0x1800a56bd  jmp     short loc_1800A564E
0x1800a56bf  mov     rax, [r14]
0x1800a56c2  mov     rcx, [rax+10h]
0x1800a56c6  mov     rax, [rcx]
0x1800a56c9  mov     rax, [rax+270h]
0x1800a56d0  call    cs:__guard_dispatch_icall_fptr
0x1800a56d6  mov     r8, rax
0x1800a56d9  mov     rcx, [rax]
0x1800a56dc  mov     rax, [rcx+58h]
0x1800a56e0  lea     rdx, [rsi+2Ch]
0x1800a56e4  mov     rcx, r8
0x1800a56e7  call    cs:__guard_dispatch_icall_fptr
0x1800a56ed  jmp     loc_1800A55DE
0x1800a56f2  mov     r14, [rsp+58h+arg_8]
0x1800a56f7  mov     rbx, [rsp+58h+arg_10]
0x1800a56fc  jmp     loc_1800A55DE
```
