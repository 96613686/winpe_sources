# GEL::GDITech::FillPathWithSolidBrush(Gdiplus::GpGraphics &,Gdiplus::GpSolidFill const *,Gdiplus::GpPath const *,Math::TRect<double> const &,GEL::CropInfo const *)

- ea: `0x18006dd80`
- end: `0x18006df95`
- name: `?FillPathWithSolidBrush@GDITech@GEL@@CAXAEAVGpGraphics@Gdiplus@@PEBVGpSolidFill@4@PEBVGpPath@4@AEBU?$TRect@N@Math@@PEBUCropInfo@2@@Z`
- size: `533`
- prototype: `__int64 __usercall@<rax>(struct Gdiplus::GpGraphics *@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18006dcf0`

## callees

- `0x180025200`
- `0x180025360`
- `0x18006dd80`
- `0x18007efec`
- `0x18007f754`
- `0x1800817d4`
- `0x180082268`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18006de29`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18006de29`
- `gdiplus!GdipDeleteRegion` at `0x18006df89`
- `gdiplus!GdipDeleteRegion` at `0x18006df89`
- `gdiplus!GdipCreateRegion` at `0x18006de35`
- `gdiplus!GdipCreateRegion` at `0x18006de35`
- `gdiplus!GdipGetClip` at `0x18006de50`
- `gdiplus!GdipGetClip` at `0x18006de50`
- `gdiplus!GdipSetClipPath` at `0x18006de7a`
- `gdiplus!GdipSetClipPath` at `0x18006de7a`
- `gdiplus!GdipFillPath` at `0x18006ddc7`
- `gdiplus!GdipFillPath` at `0x18006ddc7`
- `gdiplus!GdipFillRectangle` at `0x18006df66`
- `gdiplus!GdipFillRectangle` at `0x18006df66`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall GEL::GDITech::FillPathWithSolidBrush(
        struct Gdiplus::GpGraphics *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  unsigned int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  unsigned int Clip; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // [rsp+30h] [rbp-78h] BYREF
  struct Gdiplus::GpGraphics *v28; // [rsp+38h] [rbp-70h]
  _BYTE v29[96]; // [rsp+40h] [rbp-68h] BYREF

  if ( a5 )
  {
    v27 = 0;
    v28 = a1;
    GEL::GDIPixelModeRestorer::GDIPixelModeRestorer((GEL::GDIPixelModeRestorer *)v29, a1);
    v9 = GdipCreateRegion(&v27);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(v9, v10, v11, 39081176);
    Clip = GdipGetClip(a1, v27);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(Clip, v13, v14, 39081177);
    GEL::GDIPixelModeRestorer::~GDIPixelModeRestorer((GEL::GDIPixelModeRestorer *)v29);
    GdipSetClipPath(a1, a3, 1);
    Math::TRect<double>::GetWidth(a4, v15);
    Math::TRect<double>::GetHeight(v17, v16);
    Math::TRect<double>::GetWidth(v19, v18);
    Math::TRect<double>::GetHeight(v21, v20);
    Math::TRect<double>::GetWidth(v23, v22);
    Math::TRect<double>::GetHeight(v25, v24);
    GdipFillRectangle(a1, a2);
    GEL::GDIClip::Unapply((GEL::GDIClip *)&v27, v28);
    if ( v27 )
      GdipDeleteRegion(v27, v26);
  }
  else
  {
    GdipFillPath(a1, a2, a3);
  }
}

```

## disassembly

```asm
0x18006dd80  mov     rax, rsp
0x18006dd83  mov     [rax+8], rbx
0x18006dd87  mov     [rax+10h], rbp
0x18006dd8b  mov     [rax+18h], rsi
0x18006dd8f  mov     [rax+20h], rdi
0x18006dd93  push    r14
0x18006dd95  sub     rsp, 0A0h
0x18006dd9c  movaps  xmmword ptr [rax-18h], xmm6
0x18006dda0  movaps  xmmword ptr [rax-28h], xmm7
0x18006dda4  movaps  xmmword ptr [rax-38h], xmm9
0x18006dda9  movaps  xmmword ptr [rax-48h], xmm10
0x18006ddae  mov     r14, r9
0x18006ddb1  mov     rsi, r8
0x18006ddb4  mov     rbp, rdx
0x18006ddb7  mov     rbx, rcx
0x18006ddba  mov     rdi, [rsp+0A8h+arg_20]
0x18006ddc2  test    rdi, rdi
0x18006ddc5  jnz     short loc_18006DDFF
0x18006ddc7  call    cs:__imp_GdipFillPath
0x18006ddcd  lea     r11, [rsp+0A8h+var_8]
0x18006ddd5  mov     rbx, [r11+10h]
0x18006ddd9  mov     rbp, [r11+18h]
0x18006dddd  mov     rsi, [r11+20h]
0x18006dde1  mov     rdi, [r11+28h]
0x18006dde5  movaps  xmm6, xmmword ptr [r11-10h]
0x18006ddea  movaps  xmm7, xmmword ptr [r11-20h]
0x18006ddef  movaps  xmm9, xmmword ptr [r11-30h]
0x18006ddf4  movaps  xmm10, xmmword ptr [r11-40h]
0x18006ddf9  mov     rsp, r11
0x18006ddfc  pop     r14
0x18006ddfe  retn
0x18006ddff  mov     [rsp+0A8h+var_78], 0
0x18006de08  mov     [rsp+0A8h+var_70], rbx
0x18006de0d  mov     rdx, rbx; struct Gdiplus::GpGraphics *
0x18006de10  lea     rcx, [rsp+0A8h+var_68]; this
0x18006de15  call    ??0GDIPixelModeRestorer@GEL@@QEAA@AEAVGpGraphics@Gdiplus@@@Z; GEL::GDIPixelModeRestorer::GDIPixelModeRestorer(Gdiplus::GpGraphics &)
0x18006de1a  cmp     [rsp+0A8h+var_78], 0
0x18006de20  jz      short loc_18006DE30
0x18006de22  xor     edx, edx
0x18006de24  mov     ecx, 1E55E058h
0x18006de29  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18006de2f  nop
0x18006de30  lea     rcx, [rsp+0A8h+var_78]
0x18006de35  call    cs:__imp_GdipCreateRegion
0x18006de3b  mov     r9d, 25454D8h
0x18006de41  mov     ecx, eax
0x18006de43  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18006de48  mov     rdx, [rsp+0A8h+var_78]
0x18006de4d  mov     rcx, rbx
0x18006de50  call    cs:__imp_GdipGetClip
0x18006de56  mov     r9d, 25454D9h
0x18006de5c  mov     ecx, eax
0x18006de5e  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18006de63  nop
0x18006de64  lea     rcx, [rsp+0A8h+var_68]; this
0x18006de69  call    ??1GDIPixelModeRestorer@GEL@@QEAA@XZ; GEL::GDIPixelModeRestorer::~GDIPixelModeRestorer(void)
0x18006de6e  mov     r8d, 1
0x18006de74  mov     rdx, rsi
0x18006de77  mov     rcx, rbx
0x18006de7a  call    cs:__imp_GdipSetClipPath
0x18006de80  mov     rcx, r14
0x18006de83  call    ?GetWidth@?$TRect@N@Math@@QEBANXZ; Math::TRect<double>::GetWidth(void)
0x18006de88  movaps  xmm10, xmm0
0x18006de8c  mulsd   xmm10, qword ptr [rdi]
0x18006de91  addsd   xmm10, qword ptr [r14]
0x18006de96  call    ?GetHeight@?$TRect@N@Math@@QEBANXZ; Math::TRect<double>::GetHeight(void)
0x18006de9b  movaps  xmm7, xmm0
0x18006de9e  mulsd   xmm7, qword ptr [rdi+8]
0x18006dea3  addsd   xmm7, qword ptr [r14+8]
0x18006dea9  movsd   xmm9, qword ptr [r14+10h]
0x18006deaf  call    ?GetWidth@?$TRect@N@Math@@QEBANXZ; Math::TRect<double>::GetWidth(void)
0x18006deb4  mulsd   xmm0, qword ptr [rdi+10h]
0x18006deb9  movaps  xmm4, xmm9
0x18006debd  subsd   xmm4, xmm0
0x18006dec1  movsd   xmm6, qword ptr [r14+18h]
0x18006dec7  call    ?GetHeight@?$TRect@N@Math@@QEBANXZ; Math::TRect<double>::GetHeight(void)
0x18006decc  mulsd   xmm0, qword ptr [rdi+18h]
0x18006ded1  movaps  xmm3, xmm6
0x18006ded4  subsd   xmm3, xmm0
0x18006ded8  call    ?GetWidth@?$TRect@N@Math@@QEBANXZ; Math::TRect<double>::GetWidth(void)
0x18006dedd  movaps  xmm5, xmm0
0x18006dee0  subsd   xmm4, xmm10
0x18006dee5  divsd   xmm5, xmm4
0x18006dee9  call    ?GetHeight@?$TRect@N@Math@@QEBANXZ; Math::TRect<double>::GetHeight(void)
0x18006deee  subsd   xmm3, xmm7
0x18006def2  divsd   xmm0, xmm3
0x18006def6  movsd   xmm4, qword ptr [r14]
0x18006defb  subsd   xmm4, xmm10
0x18006df00  mulsd   xmm4, xmm5
0x18006df04  addsd   xmm4, qword ptr [r14]
0x18006df09  movsd   xmm2, qword ptr [r14+8]
0x18006df0f  subsd   xmm2, xmm7
0x18006df13  mulsd   xmm2, xmm0
0x18006df17  addsd   xmm2, qword ptr [r14+8]
0x18006df1d  subsd   xmm6, xmm7
0x18006df21  mulsd   xmm6, xmm0
0x18006df25  addsd   xmm6, qword ptr [r14+8]
0x18006df2b  subsd   xmm6, xmm2
0x18006df2f  cvtpd2ps xmm1, xmm6
0x18006df33  subsd   xmm9, xmm10
0x18006df38  mulsd   xmm9, xmm5
0x18006df3d  addsd   xmm9, qword ptr [r14]
0x18006df42  subsd   xmm9, xmm4
0x18006df47  cvtpd2ps xmm0, xmm9
0x18006df4c  cvtpd2ps xmm3, xmm2
0x18006df50  cvtpd2ps xmm2, xmm4
0x18006df54  movss   [rsp+0A8h+var_80], xmm1
0x18006df5a  movss   [rsp+0A8h+var_88], xmm0
0x18006df60  mov     rdx, rbp
0x18006df63  mov     rcx, rbx
0x18006df66  call    cs:__imp_GdipFillRectangle
0x18006df6c  mov     rdx, [rsp+0A8h+var_70]; struct Gdiplus::GpGraphics *
0x18006df71  lea     rcx, [rsp+0A8h+var_78]; this
0x18006df76  call    ?Unapply@GDIClip@GEL@@QEAAXAEAVGpGraphics@Gdiplus@@@Z; GEL::GDIClip::Unapply(Gdiplus::GpGraphics &)
0x18006df7b  mov     rcx, [rsp+0A8h+var_78]
0x18006df80  test    rcx, rcx
0x18006df83  jz      loc_18006DDCD
0x18006df89  call    cs:__imp_GdipDeleteRegion
0x18006df8f  jmp     loc_18006DDCD
```
