# GEL::GDITech::FillPathWithSolidBrush(Gdiplus::GpGraphics &,Gdiplus::GpSolidFill const *,Gdiplus::GpPath const *,Math::TRect<double> const &,GEL::CropInfo const *)

- ea: `0x180060330`
- end: `0x180060545`
- name: `?FillPathWithSolidBrush@GDITech@GEL@@CAXAEAVGpGraphics@Gdiplus@@PEBVGpSolidFill@4@PEBVGpPath@4@AEBU?$TRect@N@Math@@PEBUCropInfo@2@@Z`
- size: `533`
- prototype: `__int64 __usercall@<rax>(struct Gdiplus::GpGraphics *@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800602a0`

## callees

- `0x180024f30`
- `0x180024f60`
- `0x18005f210`
- `0x180060330`
- `0x180060884`
- `0x180061c38`
- `0x180062394`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800603d9`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800603d9`
- `gdiplus!GdipDeleteRegion` at `0x180060539`
- `gdiplus!GdipDeleteRegion` at `0x180060539`
- `gdiplus!GdipCreateRegion` at `0x1800603e5`
- `gdiplus!GdipCreateRegion` at `0x1800603e5`
- `gdiplus!GdipGetClip` at `0x180060400`
- `gdiplus!GdipGetClip` at `0x180060400`
- `gdiplus!GdipSetClipPath` at `0x18006042a`
- `gdiplus!GdipSetClipPath` at `0x18006042a`
- `gdiplus!GdipFillPath` at `0x180060377`
- `gdiplus!GdipFillPath` at `0x180060377`
- `gdiplus!GdipFillRectangle` at `0x180060516`
- `gdiplus!GdipFillRectangle` at `0x180060516`

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
0x180060330  mov     rax, rsp
0x180060333  mov     [rax+8], rbx
0x180060337  mov     [rax+10h], rbp
0x18006033b  mov     [rax+18h], rsi
0x18006033f  mov     [rax+20h], rdi
0x180060343  push    r14
0x180060345  sub     rsp, 0A0h
0x18006034c  movaps  xmmword ptr [rax-18h], xmm6
0x180060350  movaps  xmmword ptr [rax-28h], xmm7
0x180060354  movaps  xmmword ptr [rax-38h], xmm9
0x180060359  movaps  xmmword ptr [rax-48h], xmm10
0x18006035e  mov     r14, r9
0x180060361  mov     rsi, r8
0x180060364  mov     rbp, rdx
0x180060367  mov     rbx, rcx
0x18006036a  mov     rdi, [rsp+0A8h+arg_20]
0x180060372  test    rdi, rdi
0x180060375  jnz     short loc_1800603AF
0x180060377  call    cs:__imp_GdipFillPath
0x18006037d  lea     r11, [rsp+0A8h+var_8]
0x180060385  mov     rbx, [r11+10h]
0x180060389  mov     rbp, [r11+18h]
0x18006038d  mov     rsi, [r11+20h]
0x180060391  mov     rdi, [r11+28h]
0x180060395  movaps  xmm6, xmmword ptr [r11-10h]
0x18006039a  movaps  xmm7, xmmword ptr [r11-20h]
0x18006039f  movaps  xmm9, xmmword ptr [r11-30h]
0x1800603a4  movaps  xmm10, xmmword ptr [r11-40h]
0x1800603a9  mov     rsp, r11
0x1800603ac  pop     r14
0x1800603ae  retn
0x1800603af  mov     [rsp+0A8h+var_78], 0
0x1800603b8  mov     [rsp+0A8h+var_70], rbx
0x1800603bd  mov     rdx, rbx; struct Gdiplus::GpGraphics *
0x1800603c0  lea     rcx, [rsp+0A8h+var_68]; this
0x1800603c5  call    ??0GDIPixelModeRestorer@GEL@@QEAA@AEAVGpGraphics@Gdiplus@@@Z; GEL::GDIPixelModeRestorer::GDIPixelModeRestorer(Gdiplus::GpGraphics &)
0x1800603ca  cmp     [rsp+0A8h+var_78], 0
0x1800603d0  jz      short loc_1800603E0
0x1800603d2  xor     edx, edx
0x1800603d4  mov     ecx, 1E55E058h
0x1800603d9  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800603df  nop
0x1800603e0  lea     rcx, [rsp+0A8h+var_78]
0x1800603e5  call    cs:__imp_GdipCreateRegion
0x1800603eb  mov     r9d, 25454D8h
0x1800603f1  mov     ecx, eax
0x1800603f3  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800603f8  mov     rdx, [rsp+0A8h+var_78]
0x1800603fd  mov     rcx, rbx
0x180060400  call    cs:__imp_GdipGetClip
0x180060406  mov     r9d, 25454D9h
0x18006040c  mov     ecx, eax
0x18006040e  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180060413  nop
0x180060414  lea     rcx, [rsp+0A8h+var_68]; this
0x180060419  call    ??1GDIPixelModeRestorer@GEL@@QEAA@XZ; GEL::GDIPixelModeRestorer::~GDIPixelModeRestorer(void)
0x18006041e  mov     r8d, 1
0x180060424  mov     rdx, rsi
0x180060427  mov     rcx, rbx
0x18006042a  call    cs:__imp_GdipSetClipPath
0x180060430  mov     rcx, r14
0x180060433  call    ?GetWidth@?$TRect@N@Math@@QEBANXZ; Math::TRect<double>::GetWidth(void)
0x180060438  movaps  xmm10, xmm0
0x18006043c  mulsd   xmm10, qword ptr [rdi]
0x180060441  addsd   xmm10, qword ptr [r14]
0x180060446  call    ?GetHeight@?$TRect@N@Math@@QEBANXZ; Math::TRect<double>::GetHeight(void)
0x18006044b  movaps  xmm7, xmm0
0x18006044e  mulsd   xmm7, qword ptr [rdi+8]
0x180060453  addsd   xmm7, qword ptr [r14+8]
0x180060459  movsd   xmm9, qword ptr [r14+10h]
0x18006045f  call    ?GetWidth@?$TRect@N@Math@@QEBANXZ; Math::TRect<double>::GetWidth(void)
0x180060464  mulsd   xmm0, qword ptr [rdi+10h]
0x180060469  movaps  xmm4, xmm9
0x18006046d  subsd   xmm4, xmm0
0x180060471  movsd   xmm6, qword ptr [r14+18h]
0x180060477  call    ?GetHeight@?$TRect@N@Math@@QEBANXZ; Math::TRect<double>::GetHeight(void)
0x18006047c  mulsd   xmm0, qword ptr [rdi+18h]
0x180060481  movaps  xmm3, xmm6
0x180060484  subsd   xmm3, xmm0
0x180060488  call    ?GetWidth@?$TRect@N@Math@@QEBANXZ; Math::TRect<double>::GetWidth(void)
0x18006048d  movaps  xmm5, xmm0
0x180060490  subsd   xmm4, xmm10
0x180060495  divsd   xmm5, xmm4
0x180060499  call    ?GetHeight@?$TRect@N@Math@@QEBANXZ; Math::TRect<double>::GetHeight(void)
0x18006049e  subsd   xmm3, xmm7
0x1800604a2  divsd   xmm0, xmm3
0x1800604a6  movsd   xmm4, qword ptr [r14]
0x1800604ab  subsd   xmm4, xmm10
0x1800604b0  mulsd   xmm4, xmm5
0x1800604b4  addsd   xmm4, qword ptr [r14]
0x1800604b9  movsd   xmm2, qword ptr [r14+8]
0x1800604bf  subsd   xmm2, xmm7
0x1800604c3  mulsd   xmm2, xmm0
0x1800604c7  addsd   xmm2, qword ptr [r14+8]
0x1800604cd  subsd   xmm6, xmm7
0x1800604d1  mulsd   xmm6, xmm0
0x1800604d5  addsd   xmm6, qword ptr [r14+8]
0x1800604db  subsd   xmm6, xmm2
0x1800604df  cvtpd2ps xmm1, xmm6
0x1800604e3  subsd   xmm9, xmm10
0x1800604e8  mulsd   xmm9, xmm5
0x1800604ed  addsd   xmm9, qword ptr [r14]
0x1800604f2  subsd   xmm9, xmm4
0x1800604f7  cvtpd2ps xmm0, xmm9
0x1800604fc  cvtpd2ps xmm3, xmm2
0x180060500  cvtpd2ps xmm2, xmm4
0x180060504  movss   [rsp+0A8h+var_80], xmm1
0x18006050a  movss   [rsp+0A8h+var_88], xmm0
0x180060510  mov     rdx, rbp
0x180060513  mov     rcx, rbx
0x180060516  call    cs:__imp_GdipFillRectangle
0x18006051c  mov     rdx, [rsp+0A8h+var_70]; struct Gdiplus::GpGraphics *
0x180060521  lea     rcx, [rsp+0A8h+var_78]; this
0x180060526  call    ?Unapply@GDIClip@GEL@@QEAAXAEAVGpGraphics@Gdiplus@@@Z; GEL::GDIClip::Unapply(Gdiplus::GpGraphics &)
0x18006052b  mov     rcx, [rsp+0A8h+var_78]
0x180060530  test    rcx, rcx
0x180060533  jz      loc_18006037D
0x180060539  call    cs:__imp_GdipDeleteRegion
0x18006053f  jmp     loc_18006037D
```
