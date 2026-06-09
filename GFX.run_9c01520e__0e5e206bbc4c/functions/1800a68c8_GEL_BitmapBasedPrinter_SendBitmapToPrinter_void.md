# GEL::BitmapBasedPrinter::SendBitmapToPrinter(void)

- ea: `0x1800a68c8`
- end: `0x1800a6e7f`
- name: `?SendBitmapToPrinter@BitmapBasedPrinter@GEL@@IEAAXXZ`
- size: `1463`
- prototype: `void __fastcall(GEL::BitmapBasedPrinter *__hidden this)`
- caller_count: `2`
- callee_count: `14`
- tags: ``

## callers

- `0x1800a44b0`
- `0x1800a4d60`

## callees

- `0x18002fc50`
- `0x18006e438`
- `0x180072d00`
- `0x18007efec`
- `0x18007f754`
- `0x1800817d4`
- `0x180082268`
- `0x1800828c8`
- `0x1800a4550`
- `0x1800a66b0`
- `0x1800a67a8`
- `0x1800a6848`
- `0x1800a68c8`
- `0x1800cf658`

## import_xrefs

- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1800a6937`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1800a6937`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800a6e2c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800a6e2c`
- `GDI32!SetROP2` at `0x1800a69ac`
- `GDI32!SetROP2` at `0x1800a69ac`
- `gdiplus!GdipDeleteRegion` at `0x1800a6def`
- `gdiplus!GdipDeleteRegion` at `0x1800a6def`
- `gdiplus!GdipCreateRegion` at `0x1800a6cb7`
- `gdiplus!GdipCreateRegion` at `0x1800a6cb7`
- `gdiplus!GdipGetClip` at `0x1800a6cd1`
- `gdiplus!GdipGetClip` at `0x1800a6cd1`
- `gdiplus!GdipDrawImageRectRect` at `0x1800a6db9`
- `gdiplus!GdipDrawImageRectRect` at `0x1800a6db9`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall GEL::BitmapBasedPrinter::SendBitmapToPrinter(GEL::BitmapBasedPrinter *this)
{
  GEL::BitmapBasedPrinter *v1; // rsi
  int v2; // edi
  int v3; // r15d
  int v4; // ebx
  int v5; // r12d
  int v6; // r13d
  int v7; // r12d
  int v8; // r15d
  unsigned __int64 *PixelBounds; // rax
  unsigned __int64 v10; // r9
  unsigned __int64 v11; // r10
  int v12; // eax
  int v13; // ecx
  int v14; // edx
  int v15; // r8d
  unsigned __int64 v16; // r9
  unsigned __int64 v17; // r10
  int v18; // eax
  char *v19; // rcx
  int v20; // esi
  int v21; // ebx
  int v22; // r14d
  int v23; // edi
  __int64 v24; // rax
  __int64 v25; // rcx
  double v26; // xmm7_8
  double v27; // xmm6_8
  double v28; // xmm8_8
  double *v29; // rax
  double v30; // xmm4_8
  double v31; // xmm5_8
  double v32; // xmm0_8
  double v33; // xmm8_8
  float *v34; // rcx
  double *v35; // rax
  __int64 v36; // rdx
  GEL::GraphicsSurface *v37; // rax
  struct Gdiplus::GpGraphics *GpGraphics; // rbx
  unsigned int v39; // eax
  __int64 v40; // rdx
  __int64 v41; // r8
  unsigned int Clip; // eax
  __int64 v43; // rdx
  __int64 v44; // r8
  unsigned int v45; // eax
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 v48; // rdx
  __int128 v49; // [rsp+78h] [rbp-90h]
  char *i; // [rsp+78h] [rbp-90h]
  __int128 v51; // [rsp+88h] [rbp-80h] BYREF
  double v52; // [rsp+98h] [rbp-70h]
  double v53; // [rsp+A0h] [rbp-68h]
  __int64 v54; // [rsp+A8h] [rbp-60h] BYREF
  struct Gdiplus::GpGraphics *v55; // [rsp+B0h] [rbp-58h]
  char v56[8]; // [rsp+B8h] [rbp-50h] BYREF
  float v57[4]; // [rsp+C0h] [rbp-48h]
  float v58[4]; // [rsp+D0h] [rbp-38h] BYREF
  double v59[5]; // [rsp+E0h] [rbp-28h] BYREF
  _BYTE v60[16]; // [rsp+108h] [rbp+0h] BYREF
  _OWORD v61[2]; // [rsp+118h] [rbp+10h] BYREF
  _BYTE v62[32]; // [rsp+138h] [rbp+30h] BYREF
  char v63[168]; // [rsp+158h] [rbp+50h] BYREF
  int v65; // [rsp+250h] [rbp+148h] BYREF
  int v66; // [rsp+258h] [rbp+150h] BYREF
  char v67; // [rsp+260h] [rbp+158h] BYREF

  v1 = this;
  if ( *((_DWORD *)this + 128) )
  {
    if ( *((_BYTE *)this + 586) )
    {
      MsoShipAssertTagProc(2926288);
    }
    else
    {
      CodeMarker(1538);
      v59[4] = 0.0;
      v2 = *(_DWORD *)sub_1800A6848(&v65);
      v3 = *((_DWORD *)v1 + 125);
      v4 = *(_DWORD *)sub_1800A6848(&v66);
      v5 = *((_DWORD *)v1 + 124);
      v6 = *(_DWORD *)sub_1800A6848(&v67);
      v66 = *(_DWORD *)sub_1800A6848(v56);
      v7 = v5 - v4;
      v8 = v3 - v2;
      SetROP2(*((HDC *)v1 + 35), 13);
      PixelBounds = (unsigned __int64 *)GEL::Printer::GetPixelBounds(v1, v61);
      v49 = *(_OWORD *)((char *)v1 + 324);
      v10 = *PixelBounds;
      v11 = PixelBounds[1];
      if ( (int)*PixelBounds > (int)v11 || SHIDWORD(v10) > SHIDWORD(v11) )
      {
        v14 = 1;
        v15 = 1;
        v49 = 0x100000001uLL;
        v12 = 0;
        v13 = 0;
      }
      else
      {
        v12 = HIDWORD(*(_OWORD *)((char *)v1 + 324));
        v13 = *(_QWORD *)((char *)v1 + 332);
        v14 = HIDWORD(*(_QWORD *)((char *)v1 + 324));
        v15 = *(_OWORD *)((char *)v1 + 324);
      }
      if ( v15 <= v13 && v14 <= v12 )
      {
        if ( (int)v10 > v15 )
          v15 = v10;
        LODWORD(v49) = v15;
        if ( (int)v11 < v13 )
          v13 = v11;
        DWORD2(v49) = v13;
        v16 = HIDWORD(v10);
        if ( (int)v16 > v14 )
          v14 = v16;
        DWORD1(v49) = v14;
        v17 = HIDWORD(v11);
        if ( (int)v17 < v12 )
          v12 = v17;
        HIDWORD(v49) = v12;
      }
      v61[0] = v49;
      v18 = 0;
      v65 = 0;
      if ( *((int *)v1 + 128) > 0 )
      {
        v19 = (char *)v1 + 520;
        for ( i = (char *)v1 + 520; ; v19 = i )
        {
          v51 = *(_OWORD *)std::vector<Math::TRect<Math::TUnits<int,Math::DevicePixels>>>::operator[](v19, v18);
          if ( v66 > v7 || v6 > v8 )
          {
            v22 = 1;
            v23 = 1;
            v51 = 0x100000001uLL;
            v20 = 0;
            v21 = 0;
          }
          else
          {
            v20 = HIDWORD(v51);
            v21 = DWORD2(v51);
            v22 = DWORD1(v51);
            v23 = v51;
          }
          if ( v23 <= v21 && v22 <= v20 )
          {
            if ( v66 > v23 )
              v23 = v66;
            LODWORD(v51) = v23;
            if ( v7 < v21 )
              v21 = v7;
            DWORD2(v51) = v21;
            if ( v6 > v22 )
              v22 = v6;
            DWORD1(v51) = v22;
            if ( v8 < v20 )
              v20 = v8;
            HIDWORD(v51) = v20;
          }
          v24 = 0;
          v25 = 4;
          do
          {
            v57[v24] = (float)*(int *)((char *)&v51 + v24 * 4);
            ++v24;
            --v25;
          }
          while ( v25 );
          v26 = (double)-*(_DWORD *)sub_1800A6848(&v67);
          v27 = (double)-*(_DWORD *)sub_1800A6848(v56);
          GEL::BitmapBasedPrinter::GetScalingFactor(this, v60);
          v28 = (double)*((int *)this + 82);
          *(double *)&v51 = v57[0] + v27;
          *((double *)&v51 + 1) = v57[1] + v26;
          v52 = v57[2] + v27;
          v53 = v57[3] + v26;
          v29 = (double *)Math::operator*<Math::TUnits<double,Math::DevicePixels>,double,Math::TUnits<double,Math::DevicePixels>>(
                            v63,
                            &v51,
                            v60);
          v30 = v28 + v29[3];
          v32 = v31 + v29[2];
          v33 = v28 + v29[1];
          v59[0] = v31 + *v29;
          v59[1] = v33;
          v59[2] = v32;
          v59[3] = v30;
          v34 = v58;
          v35 = v59;
          v36 = 4;
          do
          {
            *v34++ = *v35++;
            --v36;
          }
          while ( v36 );
          if ( v23 >= v21 || v22 >= v20 || v58[0] >= v58[2] || v58[1] >= v58[3] )
          {
            v1 = this;
          }
          else
          {
            v1 = this;
            v37 = (GEL::GraphicsSurface *)Mso::TCntPtr<IWICImagingFactory>::operator->((char *)this + 312);
            GpGraphics = GEL::GraphicsSurface::GetGpGraphics(v37);
            v54 = 0;
            v55 = GpGraphics;
            GEL::GDIPixelModeRestorer::GDIPixelModeRestorer((GEL::GDIPixelModeRestorer *)v59, GpGraphics);
            if ( v54 )
            {
              CrashWithRecovery(0x1E55E058u, 0);
              break;
            }
            v39 = GdipCreateRegion(&v54);
            Gfx::GdipStatus_ThrowOnFailureMessageTag(v39, v40, v41, 39081176);
            Clip = GdipGetClip(GpGraphics, v54);
            Gfx::GdipStatus_ThrowOnFailureMessageTag(Clip, v43, v44, 39081177);
            GEL::GDIPixelModeRestorer::~GDIPixelModeRestorer((GEL::GDIPixelModeRestorer *)v59);
            GEL::GDIPixelModeRestorer::GDIPixelModeRestorer((GEL::GDIPixelModeRestorer *)v62, GpGraphics);
            GEL::Printer::SetClipToBounds(GpGraphics, v61);
            v45 = GdipDrawImageRectRect(GpGraphics, *((_QWORD *)this + 60));
            Gfx::GdipStatus_ThrowOnFailureMessageTag(v45, v46, v47, 38869196);
            GEL::GDIPixelModeRestorer::~GDIPixelModeRestorer((GEL::GDIPixelModeRestorer *)v62);
            GEL::GDIClip::Unapply((GEL::GDIClip *)&v54, v55);
            if ( v54 )
            {
              GdipDeleteRegion(v54, v48);
              v54 = 0;
            }
          }
          v18 = v65 + 1;
          v65 = v18;
          if ( v18 >= *((_DWORD *)v1 + 128) )
            break;
        }
      }
      *((_DWORD *)v1 + 128) = 0;
      CodeMarker(1539);
    }
  }
}

```

## disassembly

```asm
0x1800a68c8  mov     rax, rsp
0x1800a68cb  mov     [rax+8], rcx
0x1800a68cf  push    rbp
0x1800a68d0  push    rbx
0x1800a68d1  push    rsi
0x1800a68d2  push    rdi
0x1800a68d3  push    r12
0x1800a68d5  push    r13
0x1800a68d7  push    r14
0x1800a68d9  push    r15
0x1800a68db  lea     rbp, [rax-138h]
0x1800a68e2  sub     rsp, 1F8h
0x1800a68e9  movaps  xmmword ptr [rax-58h], xmm6
0x1800a68ed  movaps  xmmword ptr [rax-68h], xmm7
0x1800a68f1  movaps  xmmword ptr [rax-78h], xmm8
0x1800a68f6  movaps  xmmword ptr [rax-88h], xmm10
0x1800a68fe  movaps  xmmword ptr [rax-98h], xmm12
0x1800a6906  movaps  xmmword ptr [rax-0A8h], xmm13
0x1800a690e  movaps  xmmword ptr [rax-0B8h], xmm14
0x1800a6916  mov     rsi, rcx
0x1800a6919  xor     r14d, r14d
0x1800a691c  cmp     [rcx+200h], r14d
0x1800a6923  jz      loc_1800A6E44
0x1800a6929  cmp     [rcx+24Ah], r14b
0x1800a6930  jz      short loc_1800A6942
0x1800a6932  mov     ecx, 2CA6D0h
0x1800a6937  call    cs:__imp_MsoShipAssertTagProc
0x1800a693d  jmp     loc_1800A6E44
0x1800a6942  mov     ecx, 602h
0x1800a6947  call    CodeMarker
0x1800a694c  mov     [rbp+130h+var_138], r14
0x1800a6950  lea     rcx, [rbp+130h+arg_8]
0x1800a6957  call    sub_1800A6848
0x1800a695c  mov     edi, [rax]
0x1800a695e  mov     r15d, [rsi+1F4h]
0x1800a6965  lea     rcx, [rbp+130h+arg_10]
0x1800a696c  call    sub_1800A6848
0x1800a6971  mov     ebx, [rax]
0x1800a6973  mov     r12d, [rsi+1F0h]
0x1800a697a  lea     rcx, [rbp+130h+arg_18]
0x1800a6981  call    sub_1800A6848
0x1800a6986  mov     r13d, [rax]
0x1800a6989  lea     rcx, [rbp+130h+var_180]
0x1800a698d  call    sub_1800A6848
0x1800a6992  mov     eax, [rax]
0x1800a6994  mov     [rbp+130h+arg_10], eax
0x1800a699a  sub     r12d, ebx
0x1800a699d  sub     r15d, edi
0x1800a69a0  mov     edx, 0Dh; rop2
0x1800a69a5  mov     rcx, [rsi+118h]; hdc
0x1800a69ac  call    cs:__imp_SetROP2
0x1800a69b2  lea     rdx, [rbp+130h+var_120]
0x1800a69b6  mov     rcx, rsi
0x1800a69b9  call    ?GetPixelBounds@Printer@GEL@@UEBA?AV?$TConvertibleRectPx@H@Gfx@@XZ; GEL::Printer::GetPixelBounds(void)
0x1800a69be  movups  xmm0, xmmword ptr [rsi+144h]
0x1800a69c5  movdqu  [rsp+230h+var_1C8+8], xmm0
0x1800a69cb  mov     r9, [rax]
0x1800a69ce  mov     r10, [rax+8]
0x1800a69d2  cmp     r9d, r10d
0x1800a69d5  jg      short loc_1800A69FC
0x1800a69d7  mov     rcx, r10
0x1800a69da  shr     rcx, 20h
0x1800a69de  mov     rax, r9
0x1800a69e1  shr     rax, 20h
0x1800a69e5  cmp     eax, ecx
0x1800a69e7  jg      short loc_1800A69FC
0x1800a69e9  mov     eax, [rsp+230h+var_1B4]
0x1800a69ed  mov     ecx, [rsp+230h+var_1B8]
0x1800a69f1  mov     edx, dword ptr [rsp+230h+var_1C8+0Ch]
0x1800a69f5  mov     r8d, dword ptr [rsp+230h+var_1C8+8]
0x1800a69fa  jmp     short loc_1800A6A1A
0x1800a69fc  mov     edx, 1
0x1800a6a01  mov     dword ptr [rsp+230h+var_1C8+0Ch], edx
0x1800a6a05  mov     r8d, edx
0x1800a6a08  mov     dword ptr [rsp+230h+var_1C8+8], edx
0x1800a6a0c  mov     eax, r14d
0x1800a6a0f  mov     [rsp+230h+var_1B4], eax
0x1800a6a13  mov     ecx, r14d
0x1800a6a16  mov     [rsp+230h+var_1B8], ecx
0x1800a6a1a  cmp     r8d, ecx
0x1800a6a1d  jg      short loc_1800A6A58
0x1800a6a1f  cmp     edx, eax
0x1800a6a21  jg      short loc_1800A6A58
0x1800a6a23  cmp     r9d, r8d
0x1800a6a26  cmovg   r8d, r9d
0x1800a6a2a  mov     dword ptr [rsp+230h+var_1C8+8], r8d
0x1800a6a2f  cmp     r10d, ecx
0x1800a6a32  cmovl   ecx, r10d
0x1800a6a36  mov     [rsp+230h+var_1B8], ecx
0x1800a6a3a  shr     r9, 20h
0x1800a6a3e  cmp     r9d, edx
0x1800a6a41  cmovg   edx, r9d
0x1800a6a45  mov     dword ptr [rsp+230h+var_1C8+0Ch], edx
0x1800a6a49  shr     r10, 20h
0x1800a6a4d  cmp     r10d, eax
0x1800a6a50  cmovl   eax, r10d
0x1800a6a54  mov     [rsp+230h+var_1B4], eax
0x1800a6a58  movaps  xmm0, [rsp+230h+var_1C8+8]
0x1800a6a5d  movdqa  [rbp+130h+var_120], xmm0
0x1800a6a62  mov     eax, r14d
0x1800a6a65  mov     [rbp+130h+arg_8], eax
0x1800a6a6b  cmp     [rsi+200h], r14d
0x1800a6a72  jle     loc_1800A6E33
0x1800a6a78  lea     rcx, [rsi+208h]
0x1800a6a7f  mov     qword ptr [rsp+230h+var_1C8+8], rcx
0x1800a6a84  movsd   xmm14, cs:__real@c7efffffe0000000
0x1800a6a8d  movsxd  rdx, eax
0x1800a6a90  call    ??A?$vector@U?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@V?$allocator@U?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@@std@@@std@@QEBAAEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@_K@Z; std::vector<Math::TRect<Math::TUnits<int,Math::DevicePixels>>>::operator[](unsigned __int64)
0x1800a6a95  movups  xmm0, xmmword ptr [rax]
0x1800a6a98  movdqu  [rbp+130h+var_1B0], xmm0
0x1800a6a9d  mov     eax, [rbp+130h+arg_10]
0x1800a6aa3  cmp     eax, r12d
0x1800a6aa6  jg      short loc_1800A6ABC
0x1800a6aa8  cmp     r13d, r15d
0x1800a6aab  jg      short loc_1800A6ABC
0x1800a6aad  mov     esi, dword ptr [rbp+130h+var_1B0+0Ch]
0x1800a6ab0  mov     ebx, dword ptr [rbp+130h+var_1B0+8]
0x1800a6ab3  mov     r14d, dword ptr [rbp+130h+var_1B0+4]
0x1800a6ab7  mov     edi, dword ptr [rbp+130h+var_1B0]
0x1800a6aba  jmp     short loc_1800A6AD7
0x1800a6abc  mov     r14d, 1
0x1800a6ac2  mov     dword ptr [rbp+130h+var_1B0+4], r14d
0x1800a6ac6  mov     edi, r14d
0x1800a6ac9  mov     dword ptr [rbp+130h+var_1B0], r14d
0x1800a6acd  xor     esi, esi
0x1800a6acf  mov     dword ptr [rbp+130h+var_1B0+0Ch], esi
0x1800a6ad2  xor     ebx, ebx
0x1800a6ad4  mov     dword ptr [rbp+130h+var_1B0+8], ebx
0x1800a6ad7  cmp     edi, ebx
0x1800a6ad9  jg      short loc_1800A6B07
0x1800a6adb  cmp     r14d, esi
0x1800a6ade  jg      short loc_1800A6B07
0x1800a6ae0  cmp     eax, edi
0x1800a6ae2  cmovg   edi, eax
0x1800a6ae5  mov     dword ptr [rbp+130h+var_1B0], edi
0x1800a6ae8  cmp     r12d, ebx
0x1800a6aeb  cmovl   ebx, r12d
0x1800a6aef  mov     dword ptr [rbp+130h+var_1B0+8], ebx
0x1800a6af2  cmp     r13d, r14d
0x1800a6af5  cmovg   r14d, r13d
0x1800a6af9  mov     dword ptr [rbp+130h+var_1B0+4], r14d
0x1800a6afd  cmp     r15d, esi
0x1800a6b00  cmovl   esi, r15d
0x1800a6b04  mov     dword ptr [rbp+130h+var_1B0+0Ch], esi
0x1800a6b07  movaps  xmm0, [rbp+130h+var_1B0]
0x1800a6b0b  movdqa  [rbp+130h+var_1B0], xmm0
0x1800a6b10  xor     eax, eax
0x1800a6b12  lea     ecx, [rax+4]
0x1800a6b15  movd    xmm0, dword ptr [rbp+rax+130h+var_1B0]
0x1800a6b1b  cvtdq2ps xmm0, xmm0
0x1800a6b1e  movss   [rbp+rax+130h+var_178], xmm0
0x1800a6b24  lea     rax, [rax+4]
0x1800a6b28  sub     rcx, 1
0x1800a6b2c  jnz     short loc_1800A6B15
0x1800a6b2e  lea     rcx, [rbp+130h+arg_18]
0x1800a6b35  call    sub_1800A6848
0x1800a6b3a  mov     ecx, [rax]
0x1800a6b3c  neg     ecx
0x1800a6b3e  movd    xmm7, ecx
0x1800a6b42  cvtdq2pd xmm7, xmm7
0x1800a6b46  lea     rcx, [rbp+130h+var_180]
0x1800a6b4a  call    sub_1800A6848
0x1800a6b4f  mov     ecx, [rax]
0x1800a6b51  neg     ecx
0x1800a6b53  movd    xmm6, ecx
0x1800a6b57  cvtdq2pd xmm6, xmm6
0x1800a6b5b  lea     rdx, [rbp+130h+var_130]
0x1800a6b5f  mov     rcx, [rbp+130h+arg_0]
0x1800a6b66  call    ?GetScalingFactor@BitmapBasedPrinter@GEL@@UEBA?AU?$TScaling2@N@Math@@XZ; GEL::BitmapBasedPrinter::GetScalingFactor(void)
0x1800a6b6b  mov     rax, [rbp+130h+arg_0]
0x1800a6b72  movd    xmm8, dword ptr [rax+148h]
0x1800a6b7b  cvtdq2pd xmm8, xmm8
0x1800a6b80  movd    xmm5, dword ptr [rax+144h]
0x1800a6b88  cvtdq2pd xmm5, xmm5
0x1800a6b8c  movss   xmm3, [rbp+130h+var_16C]
0x1800a6b91  cvtps2pd xmm3, xmm3
0x1800a6b94  addsd   xmm3, xmm7
0x1800a6b98  movss   xmm10, [rbp+130h+var_170]
0x1800a6b9e  cvtps2pd xmm2, xmm10
0x1800a6ba2  addsd   xmm2, xmm6
0x1800a6ba6  movss   xmm12, [rbp+130h+var_174]
0x1800a6bac  cvtps2pd xmm1, xmm12
0x1800a6bb0  addsd   xmm1, xmm7
0x1800a6bb4  movss   xmm13, [rbp+130h+var_178]
0x1800a6bba  cvtps2pd xmm0, xmm13
0x1800a6bbe  addsd   xmm0, xmm6
0x1800a6bc2  movsd   qword ptr [rbp+130h+var_1B0], xmm0
0x1800a6bc7  movsd   qword ptr [rbp+130h+var_1B0+8], xmm1
0x1800a6bcc  movsd   [rbp+130h+var_1A0], xmm2
0x1800a6bd1  movsd   [rbp+130h+var_198], xmm3
0x1800a6bd6  lea     r8, [rbp+130h+var_130]
0x1800a6bda  lea     rdx, [rbp+130h+var_1B0]
0x1800a6bde  lea     rcx, [rbp+130h+var_E0]
0x1800a6be2  call    ??$?DV?$TUnits@NUDevicePixels@Math@@@Math@@NV01@@Math@@YA?AU?$TRect@V?$TUnits@NUDevicePixels@Math@@@Math@@@0@AEBU10@AEBU?$TScaling2@N@0@@Z; Math::operator*<Math::TUnits<double,Math::DevicePixels>,double,Math::TUnits<double,Math::DevicePixels>>(Math::TRect<Math::TUnits<double,Math::DevicePixels>> const &,Math::TScaling2<double> const &)
0x1800a6be7  movaps  xmm4, xmm8
0x1800a6beb  addsd   xmm4, qword ptr [rax+18h]
0x1800a6bf0  movaps  xmm0, xmm5
0x1800a6bf3  addsd   xmm0, qword ptr [rax+10h]
0x1800a6bf8  addsd   xmm8, qword ptr [rax+8]
0x1800a6bfe  addsd   xmm5, qword ptr [rax]
0x1800a6c02  movsd   [rbp+130h+var_158], xmm5
0x1800a6c07  movsd   [rbp+130h+var_150], xmm8
0x1800a6c0d  movsd   [rbp+130h+var_148], xmm0
0x1800a6c12  movsd   [rbp+130h+var_140], xmm4
0x1800a6c17  lea     rcx, [rbp+130h+var_168]
0x1800a6c1b  lea     rax, [rbp+130h+var_158]
0x1800a6c1f  mov     edx, 4
0x1800a6c24  movsd   xmm0, qword ptr [rax]
0x1800a6c28  cvtpd2ps xmm1, xmm0
0x1800a6c2c  movss   dword ptr [rcx], xmm1
0x1800a6c30  add     rax, 8
0x1800a6c34  add     rcx, 4
0x1800a6c38  sub     rdx, 1
0x1800a6c3c  jnz     short loc_1800A6C24
0x1800a6c3e  cmp     edi, ebx
0x1800a6c40  jge     loc_1800A6DFB
0x1800a6c46  cmp     r14d, esi
0x1800a6c49  jge     loc_1800A6DFB
0x1800a6c4f  movss   xmm7, [rbp+130h+var_168]
0x1800a6c54  movss   xmm6, [rbp+130h+var_160]
0x1800a6c59  comiss  xmm7, xmm6
0x1800a6c5c  jnb     loc_1800A6DFB
0x1800a6c62  movss   xmm8, [rbp+130h+var_164]
0x1800a6c68  comiss  xmm8, [rbp+130h+var_15C]
0x1800a6c6d  jnb     loc_1800A6DFB
0x1800a6c73  mov     rsi, [rbp+130h+arg_0]
0x1800a6c7a  lea     rcx, [rsi+138h]
0x1800a6c81  call    ??C?$TCntPtr@UIWICImagingFactory@@@Mso@@QEBAPEAUIWICImagingFactory@@XZ; Mso::TCntPtr<IWICImagingFactory>::operator->(void)
0x1800a6c86  mov     rcx, rax; this
0x1800a6c89  call    ?GetGpGraphics@GraphicsSurface@GEL@@QEAAAEAVGpGraphics@Gdiplus@@XZ; GEL::GraphicsSurface::GetGpGraphics(void)
0x1800a6c8e  mov     rbx, rax
0x1800a6c91  xor     r14d, r14d
0x1800a6c94  mov     [rbp+130h+var_190], r14
0x1800a6c98  mov     [rbp+130h+var_188], rax
0x1800a6c9c  mov     rdx, rax; struct Gdiplus::GpGraphics *
0x1800a6c9f  lea     rcx, [rbp+130h+var_158]; this
0x1800a6ca3  call    ??0GDIPixelModeRestorer@GEL@@QEAA@AEAVGpGraphics@Gdiplus@@@Z; GEL::GDIPixelModeRestorer::GDIPixelModeRestorer(Gdiplus::GpGraphics &)
0x1800a6ca8  nop
0x1800a6ca9  cmp     [rbp+130h+var_190], r14
0x1800a6cad  jnz     loc_1800A6E25
0x1800a6cb3  lea     rcx, [rbp+130h+var_190]
0x1800a6cb7  call    cs:__imp_GdipCreateRegion
0x1800a6cbd  mov     r9d, 25454D8h
0x1800a6cc3  mov     ecx, eax
0x1800a6cc5  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800a6cca  mov     rdx, [rbp+130h+var_190]
0x1800a6cce  mov     rcx, rbx
0x1800a6cd1  call    cs:__imp_GdipGetClip
0x1800a6cd7  mov     r9d, 25454D9h
0x1800a6cdd  mov     ecx, eax
0x1800a6cdf  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800a6ce4  nop
0x1800a6ce5  lea     rcx, [rbp+130h+var_158]; this
0x1800a6ce9  call    ??1GDIPixelModeRestorer@GEL@@QEAA@XZ; GEL::GDIPixelModeRestorer::~GDIPixelModeRestorer(void)
0x1800a6cee  mov     rdx, rbx; struct Gdiplus::GpGraphics *
0x1800a6cf1  lea     rcx, [rbp+130h+var_100]; this
0x1800a6cf5  call    ??0GDIPixelModeRestorer@GEL@@QEAA@AEAVGpGraphics@Gdiplus@@@Z; GEL::GDIPixelModeRestorer::GDIPixelModeRestorer(Gdiplus::GpGraphics &)
0x1800a6cfa  lea     rdx, [rbp+130h+var_120]
0x1800a6cfe  mov     rcx, rbx
0x1800a6d01  call    ?SetClipToBounds@Printer@GEL@@KAXPEAVGpGraphics@Gdiplus@@AEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@@Z; GEL::Printer::SetClipToBounds(Gdiplus::GpGraphics *,Math::TRect<Math::TUnits<int,Math::DevicePixels>> const &)
0x1800a6d06  comiss  xmm13, xmm10
0x1800a6d0a  ja      short loc_1800A6D1F
0x1800a6d0c  comiss  xmm12, [rbp+130h+var_16C]
0x1800a6d11  ja      short loc_1800A6D1F
0x1800a6d13  movss   xmm1, [rbp+130h+var_16C]
0x1800a6d18  subss   xmm1, xmm12
0x1800a6d1d  jmp     short loc_1800A6D22
0x1800a6d1f  xorps   xmm1, xmm1
0x1800a6d22  comiss  xmm13, xmm10
0x1800a6d26  ja      short loc_1800A6D36
0x1800a6d28  comiss  xmm12, [rbp+130h+var_16C]
0x1800a6d2d  ja      short loc_1800A6D36
0x1800a6d2f  subss   xmm10, xmm13
0x1800a6d34  jmp     short loc_1800A6D3A
0x1800a6d36  xorps   xmm10, xmm10
0x1800a6d3a  comiss  xmm7, xmm6
0x1800a6d3d  ja      short loc_1800A6D52
0x1800a6d3f  comiss  xmm8, [rbp+130h+var_15C]
0x1800a6d44  ja      short loc_1800A6D52
0x1800a6d46  movss   xmm0, [rbp+130h+var_15C]
0x1800a6d4b  subss   xmm0, xmm8
0x1800a6d50  jmp     short loc_1800A6D55
0x1800a6d52  xorps   xmm0, xmm0
0x1800a6d55  comiss  xmm7, xmm6
0x1800a6d58  ja      short loc_1800A6D67
0x1800a6d5a  comiss  xmm8, [rbp+130h+var_15C]
0x1800a6d5f  ja      short loc_1800A6D67
0x1800a6d61  subss   xmm6, xmm7
0x1800a6d65  jmp     short loc_1800A6D6A
0x1800a6d67  xorps   xmm6, xmm6
0x1800a6d6a  mov     qword ptr [rsp+230h+var_1C8], r14
0x1800a6d6f  mov     [rsp+230h+var_1D0], r14
0x1800a6d74  mov     [rsp+230h+var_1D8], r14
0x1800a6d79  mov     dword ptr [rsp+230h+var_1E0], 2
0x1800a6d81  movss   [rsp+230h+var_1E8], xmm1
0x1800a6d87  movss   [rsp+230h+var_1F0], xmm10
0x1800a6d8e  movss   [rsp+230h+var_1F8], xmm12
0x1800a6d95  movss   [rsp+230h+var_200], xmm13
0x1800a6d9c  movss   [rsp+230h+var_208], xmm0
0x1800a6da2  movss   [rsp+230h+var_210], xmm6
  ... truncated ...
```
