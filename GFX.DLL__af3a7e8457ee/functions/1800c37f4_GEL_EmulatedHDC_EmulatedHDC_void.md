# GEL::EmulatedHDC::~EmulatedHDC(void)

- ea: `0x1800c37f4`
- end: `0x1800c39a2`
- name: `??1EmulatedHDC@GEL@@UEAA@XZ`
- size: `430`
- prototype: `void __fastcall(GEL::EmulatedHDC *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800c37c0`

## callees

- `0x1800573f0`
- `0x180060884`
- `0x180061c38`
- `0x180062394`
- `0x1800c37f4`
- `0x1800c3c50`
- `0x1800c3fd8`
- `0x1800c4e50`

## import_xrefs

- `GDI32!RestoreDC` at `0x1800c3908`
- `GDI32!RestoreDC` at `0x1800c3908`
- `GDI32!GetClipRgn` at `0x1800c382e`
- `GDI32!GetClipRgn` at `0x1800c382e`
- `GDI32!CreateRectRgn` at `0x1800c3819`
- `GDI32!CreateRectRgn` at `0x1800c3819`
- `GDI32!DeleteObject` at `0x1800c388d`
- `GDI32!DeleteObject` at `0x1800c388d`
- `gdiplus!GdipResetClip` at `0x1800c38da`
- `gdiplus!GdipResetClip` at `0x1800c38da`
- `gdiplus!GdipDeleteRegion` at `0x1800c3957`
- `gdiplus!GdipDeleteRegion` at `0x1800c3957`
- `gdiplus!GdipSetClipRegion` at `0x1800c3939`
- `gdiplus!GdipSetClipRegion` at `0x1800c3939`
- `gdiplus!GdipReleaseDC` at `0x1800c3850`
- `gdiplus!GdipReleaseDC` at `0x1800c3850`

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
0x1800c37f4  mov     [rsp+arg_18], rbx
0x1800c37f9  push    rsi
0x1800c37fa  push    r14
0x1800c37fc  push    r15
0x1800c37fe  sub     rsp, 40h
0x1800c3802  mov     rsi, rcx
0x1800c3805  lea     rax, ??_7EmulatedHDC@GEL@@6B@; const GEL::EmulatedHDC::`vftable'
0x1800c380c  mov     [rcx], rax
0x1800c380f  xor     r9d, r9d; y2
0x1800c3812  xor     r8d, r8d; x2
0x1800c3815  xor     edx, edx; y1
0x1800c3817  xor     ecx, ecx; x1
0x1800c3819  call    cs:__imp_CreateRectRgn
0x1800c381f  mov     rbx, rax
0x1800c3822  mov     [rsp+58h+arg_10], rax
0x1800c3827  mov     rdx, rax; hrgn
0x1800c382a  mov     rcx, [rsi+20h]; hdc
0x1800c382e  call    cs:__imp_GetClipRgn
0x1800c3834  mov     r15d, eax
0x1800c3837  mov     edx, [rsi+3Ch]; nSavedDC
0x1800c383a  test    edx, edx
0x1800c383c  jnz     loc_1800C38FA
0x1800c3842  cmp     byte ptr [rsi+28h], 0
0x1800c3846  jnz     short loc_1800C38A3
0x1800c3848  mov     rdx, [rsi+20h]
0x1800c384c  mov     rcx, [rsi+18h]
0x1800c3850  call    cs:__imp_GdipReleaseDC
0x1800c3856  lea     r14, [rsi+10h]
0x1800c385a  mov     rax, [r14]
0x1800c385d  mov     rcx, [rax+10h]
0x1800c3861  mov     rax, [rcx]
0x1800c3864  mov     rax, [rax+270h]
0x1800c386b  call    cs:__guard_dispatch_icall_fptr
0x1800c3871  cmp     byte ptr [rax+0D8h], 0
0x1800c3878  jnz     loc_1800C395F
0x1800c387e  mov     rax, [r14]
0x1800c3881  mov     byte ptr [rax+30h], 0
0x1800c3885  test    rbx, rbx
0x1800c3888  jz      short loc_1800C3894
0x1800c388a  mov     rcx, rbx; ho
0x1800c388d  call    cs:__imp_DeleteObject
0x1800c3893  nop
0x1800c3894  mov     rbx, [rsp+58h+arg_18]
0x1800c3899  add     rsp, 40h
0x1800c389d  pop     r15
0x1800c389f  pop     r14
0x1800c38a1  pop     rsi
0x1800c38a2  retn
0x1800c38a3  lea     r14, [rsi+10h]
0x1800c38a7  mov     [rsp+58h+arg_8], r14
0x1800c38ac  mov     rax, [r14]
0x1800c38af  mov     rcx, [rax+10h]; this
0x1800c38b3  call    ?EndMetafile@BitmapBasedPrinter@GEL@@QEAAXXZ; GEL::BitmapBasedPrinter::EndMetafile(void)
0x1800c38b8  mov     rcx, [r14]; this
0x1800c38bb  call    ?GetEmulatedGpGraphics@Scene@GEL@@QEAAPEAVGpGraphics@Gdiplus@@XZ; GEL::Scene::GetEmulatedGpGraphics(void)
0x1800c38c0  mov     rsi, rax
0x1800c38c3  mov     rdx, rax; struct Gdiplus::GpGraphics *
0x1800c38c6  lea     rcx, [rsp+58h+var_38]; this
0x1800c38cb  call    ??0GDIPixelModeRestorer@GEL@@QEAA@AEAVGpGraphics@Gdiplus@@@Z; GEL::GDIPixelModeRestorer::GDIPixelModeRestorer(Gdiplus::GpGraphics &)
0x1800c38d0  nop
0x1800c38d1  cmp     r15d, 1
0x1800c38d5  jz      short loc_1800C3913
0x1800c38d7  mov     rcx, rsi
0x1800c38da  call    cs:__imp_GdipResetClip
0x1800c38e0  mov     r9d, 251201Eh
0x1800c38e6  mov     ecx, eax
0x1800c38e8  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800c38ed  nop
0x1800c38ee  lea     rcx, [rsp+58h+var_38]; this
0x1800c38f3  call    ??1GDIPixelModeRestorer@GEL@@QEAA@XZ; GEL::GDIPixelModeRestorer::~GDIPixelModeRestorer(void)
0x1800c38f8  jmp     short loc_1800C387E
0x1800c38fa  cmp     byte ptr [rsi+29h], 0
0x1800c38fe  jnz     loc_1800C3842
0x1800c3904  mov     rcx, [rsi+20h]; hdc
0x1800c3908  call    cs:__imp_RestoreDC
0x1800c390e  jmp     loc_1800C3842
0x1800c3913  test    rbx, rbx
0x1800c3916  jz      short loc_1800C38D7
0x1800c3918  mov     [rsp+58h+arg_0], 0
0x1800c3921  lea     rdx, [rsp+58h+arg_0]
0x1800c3926  mov     rcx, rbx
0x1800c3929  call    ?HRGNToGpRegion@Gfx@@YAXPEAUHRGN__@@AEAV?$TGpHolder@VGpRegion@Gdiplus@@@GDIPlus@ARC@@@Z; Gfx::HRGNToGpRegion(HRGN__ *,ARC::GDIPlus::TGpHolder<Gdiplus::GpRegion> &)
0x1800c392e  xor     r8d, r8d
0x1800c3931  mov     rdx, [rsp+58h+arg_0]
0x1800c3936  mov     rcx, rsi
0x1800c3939  call    cs:__imp_GdipSetClipRegion
0x1800c393f  mov     r9d, 251201Dh
0x1800c3945  mov     ecx, eax
0x1800c3947  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800c394c  nop
0x1800c394d  mov     rcx, [rsp+58h+arg_0]
0x1800c3952  test    rcx, rcx
0x1800c3955  jz      short loc_1800C38EE
0x1800c3957  call    cs:__imp_GdipDeleteRegion
0x1800c395d  jmp     short loc_1800C38EE
0x1800c395f  mov     rax, [r14]
0x1800c3962  mov     rcx, [rax+10h]
0x1800c3966  mov     rax, [rcx]
0x1800c3969  mov     rax, [rax+270h]
0x1800c3970  call    cs:__guard_dispatch_icall_fptr
0x1800c3976  mov     r8, rax
0x1800c3979  mov     rcx, [rax]
0x1800c397c  mov     rax, [rcx+58h]
0x1800c3980  lea     rdx, [rsi+2Ch]
0x1800c3984  mov     rcx, r8
0x1800c3987  call    cs:__guard_dispatch_icall_fptr
0x1800c398d  jmp     loc_1800C387E
0x1800c3992  mov     r14, [rsp+58h+arg_8]
0x1800c3997  mov     rbx, [rsp+58h+arg_10]
0x1800c399c  jmp     loc_1800C387E
```
