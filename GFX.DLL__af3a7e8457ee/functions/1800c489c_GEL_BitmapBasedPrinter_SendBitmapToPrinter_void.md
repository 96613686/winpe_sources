# GEL::BitmapBasedPrinter::SendBitmapToPrinter(void)

- ea: `0x1800c489c`
- end: `0x1800c4e50`
- name: `?SendBitmapToPrinter@BitmapBasedPrinter@GEL@@IEAAXXZ`
- size: `1460`
- prototype: `void __fastcall(GEL::BitmapBasedPrinter *__hidden this)`
- caller_count: `2`
- callee_count: `14`
- tags: ``

## callers

- `0x1800c26d0`
- `0x1800c5080`

## callees

- `0x18002f5d0`
- `0x18005f210`
- `0x180060884`
- `0x180061c38`
- `0x180062394`
- `0x180064bb8`
- `0x180064e30`
- `0x180069b94`
- `0x1800c0f60`
- `0x1800c21c4`
- `0x1800c4740`
- `0x1800c4838`
- `0x1800c489c`
- `0x1800d12d8`

## import_xrefs

- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1800c490b`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1800c490b`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800c4dfd`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800c4dfd`
- `GDI32!SetROP2` at `0x1800c4980`
- `GDI32!SetROP2` at `0x1800c4980`
- `gdiplus!GdipDeleteRegion` at `0x1800c4dc0`
- `gdiplus!GdipDeleteRegion` at `0x1800c4dc0`
- `gdiplus!GdipCreateRegion` at `0x1800c4c8b`
- `gdiplus!GdipCreateRegion` at `0x1800c4c8b`
- `gdiplus!GdipGetClip` at `0x1800c4ca5`
- `gdiplus!GdipGetClip` at `0x1800c4ca5`
- `gdiplus!GdipDrawImageRectRect` at `0x1800c4d8d`
- `gdiplus!GdipDrawImageRectRect` at `0x1800c4d8d`

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
      v2 = *(_DWORD *)sub_1800C21C4(&v65);
      v3 = *((_DWORD *)v1 + 125);
      v4 = *(_DWORD *)sub_1800C21C4(&v66);
      v5 = *((_DWORD *)v1 + 124);
      v6 = *(_DWORD *)sub_1800C21C4(&v67);
      v66 = *(_DWORD *)sub_1800C21C4(v56);
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
          v26 = (double)-*(_DWORD *)sub_1800C21C4(&v67);
          v27 = (double)-*(_DWORD *)sub_1800C21C4(v56);
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
0x1800c489c  mov     rax, rsp
0x1800c489f  mov     [rax+8], rcx
0x1800c48a3  push    rbp
0x1800c48a4  push    rbx
0x1800c48a5  push    rsi
0x1800c48a6  push    rdi
0x1800c48a7  push    r12
0x1800c48a9  push    r13
0x1800c48ab  push    r14
0x1800c48ad  push    r15
0x1800c48af  lea     rbp, [rax-138h]
0x1800c48b6  sub     rsp, 1F8h
0x1800c48bd  movaps  xmmword ptr [rax-58h], xmm6
0x1800c48c1  movaps  xmmword ptr [rax-68h], xmm7
0x1800c48c5  movaps  xmmword ptr [rax-78h], xmm8
0x1800c48ca  movaps  xmmword ptr [rax-88h], xmm10
0x1800c48d2  movaps  xmmword ptr [rax-98h], xmm12
0x1800c48da  movaps  xmmword ptr [rax-0A8h], xmm13
0x1800c48e2  movaps  xmmword ptr [rax-0B8h], xmm14
0x1800c48ea  mov     rsi, rcx
0x1800c48ed  xor     r14d, r14d
0x1800c48f0  cmp     [rcx+200h], r14d
0x1800c48f7  jz      loc_1800C4E15
0x1800c48fd  cmp     [rcx+24Ah], r14b
0x1800c4904  jz      short loc_1800C4916
0x1800c4906  mov     ecx, 2CA6D0h
0x1800c490b  call    cs:__imp_MsoShipAssertTagProc
0x1800c4911  jmp     loc_1800C4E15
0x1800c4916  mov     ecx, 602h
0x1800c491b  call    CodeMarker
0x1800c4920  mov     [rbp+130h+var_138], r14
0x1800c4924  lea     rcx, [rbp+130h+arg_8]
0x1800c492b  call    sub_1800C21C4
0x1800c4930  mov     edi, [rax]
0x1800c4932  mov     r15d, [rsi+1F4h]
0x1800c4939  lea     rcx, [rbp+130h+arg_10]
0x1800c4940  call    sub_1800C21C4
0x1800c4945  mov     ebx, [rax]
0x1800c4947  mov     r12d, [rsi+1F0h]
0x1800c494e  lea     rcx, [rbp+130h+arg_18]
0x1800c4955  call    sub_1800C21C4
0x1800c495a  mov     r13d, [rax]
0x1800c495d  lea     rcx, [rbp+130h+var_180]
0x1800c4961  call    sub_1800C21C4
0x1800c4966  mov     eax, [rax]
0x1800c4968  mov     [rbp+130h+arg_10], eax
0x1800c496e  sub     r12d, ebx
0x1800c4971  sub     r15d, edi
0x1800c4974  mov     edx, 0Dh; rop2
0x1800c4979  mov     rcx, [rsi+118h]; hdc
0x1800c4980  call    cs:__imp_SetROP2
0x1800c4986  lea     rdx, [rbp+130h+var_120]
0x1800c498a  mov     rcx, rsi
0x1800c498d  call    ?GetPixelBounds@Printer@GEL@@UEBA?AV?$TConvertibleRectPx@H@Gfx@@XZ; GEL::Printer::GetPixelBounds(void)
0x1800c4992  movups  xmm0, xmmword ptr [rsi+144h]
0x1800c4999  movdqu  [rsp+230h+var_1C8+8], xmm0
0x1800c499f  mov     r9, [rax]
0x1800c49a2  mov     r10, [rax+8]
0x1800c49a6  cmp     r9d, r10d
0x1800c49a9  jg      short loc_1800C49D0
0x1800c49ab  mov     rcx, r10
0x1800c49ae  shr     rcx, 20h
0x1800c49b2  mov     rax, r9
0x1800c49b5  shr     rax, 20h
0x1800c49b9  cmp     eax, ecx
0x1800c49bb  jg      short loc_1800C49D0
0x1800c49bd  mov     eax, [rsp+230h+var_1B4]
0x1800c49c1  mov     ecx, [rsp+230h+var_1B8]
0x1800c49c5  mov     edx, dword ptr [rsp+230h+var_1C8+0Ch]
0x1800c49c9  mov     r8d, dword ptr [rsp+230h+var_1C8+8]
0x1800c49ce  jmp     short loc_1800C49EE
0x1800c49d0  mov     edx, 1
0x1800c49d5  mov     dword ptr [rsp+230h+var_1C8+0Ch], edx
0x1800c49d9  mov     r8d, edx
0x1800c49dc  mov     dword ptr [rsp+230h+var_1C8+8], edx
0x1800c49e0  mov     eax, r14d
0x1800c49e3  mov     [rsp+230h+var_1B4], eax
0x1800c49e7  mov     ecx, r14d
0x1800c49ea  mov     [rsp+230h+var_1B8], ecx
0x1800c49ee  cmp     r8d, ecx
0x1800c49f1  jg      short loc_1800C4A2C
0x1800c49f3  cmp     edx, eax
0x1800c49f5  jg      short loc_1800C4A2C
0x1800c49f7  cmp     r9d, r8d
0x1800c49fa  cmovg   r8d, r9d
0x1800c49fe  mov     dword ptr [rsp+230h+var_1C8+8], r8d
0x1800c4a03  cmp     r10d, ecx
0x1800c4a06  cmovl   ecx, r10d
0x1800c4a0a  mov     [rsp+230h+var_1B8], ecx
0x1800c4a0e  shr     r9, 20h
0x1800c4a12  cmp     r9d, edx
0x1800c4a15  cmovg   edx, r9d
0x1800c4a19  mov     dword ptr [rsp+230h+var_1C8+0Ch], edx
0x1800c4a1d  shr     r10, 20h
0x1800c4a21  cmp     r10d, eax
0x1800c4a24  cmovl   eax, r10d
0x1800c4a28  mov     [rsp+230h+var_1B4], eax
0x1800c4a2c  movaps  xmm0, [rsp+230h+var_1C8+8]
0x1800c4a31  movdqa  [rbp+130h+var_120], xmm0
0x1800c4a36  mov     eax, r14d
0x1800c4a39  mov     [rbp+130h+arg_8], eax
0x1800c4a3f  cmp     [rsi+200h], r14d
0x1800c4a46  jle     loc_1800C4E04
0x1800c4a4c  lea     rcx, [rsi+208h]
0x1800c4a53  mov     qword ptr [rsp+230h+var_1C8+8], rcx
0x1800c4a58  movsd   xmm14, cs:__real@c7efffffe0000000
0x1800c4a61  movsxd  rdx, eax
0x1800c4a64  call    ??A?$vector@U?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@V?$allocator@U?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@@std@@@std@@QEBAAEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@_K@Z; std::vector<Math::TRect<Math::TUnits<int,Math::DevicePixels>>>::operator[](unsigned __int64)
0x1800c4a69  movups  xmm0, xmmword ptr [rax]
0x1800c4a6c  movdqu  [rbp+130h+var_1B0], xmm0
0x1800c4a71  mov     eax, [rbp+130h+arg_10]
0x1800c4a77  cmp     eax, r12d
0x1800c4a7a  jg      short loc_1800C4A90
0x1800c4a7c  cmp     r13d, r15d
0x1800c4a7f  jg      short loc_1800C4A90
0x1800c4a81  mov     esi, dword ptr [rbp+130h+var_1B0+0Ch]
0x1800c4a84  mov     ebx, dword ptr [rbp+130h+var_1B0+8]
0x1800c4a87  mov     r14d, dword ptr [rbp+130h+var_1B0+4]
0x1800c4a8b  mov     edi, dword ptr [rbp+130h+var_1B0]
0x1800c4a8e  jmp     short loc_1800C4AAB
0x1800c4a90  mov     r14d, 1
0x1800c4a96  mov     dword ptr [rbp+130h+var_1B0+4], r14d
0x1800c4a9a  mov     edi, r14d
0x1800c4a9d  mov     dword ptr [rbp+130h+var_1B0], r14d
0x1800c4aa1  xor     esi, esi
0x1800c4aa3  mov     dword ptr [rbp+130h+var_1B0+0Ch], esi
0x1800c4aa6  xor     ebx, ebx
0x1800c4aa8  mov     dword ptr [rbp+130h+var_1B0+8], ebx
0x1800c4aab  cmp     edi, ebx
0x1800c4aad  jg      short loc_1800C4ADB
0x1800c4aaf  cmp     r14d, esi
0x1800c4ab2  jg      short loc_1800C4ADB
0x1800c4ab4  cmp     eax, edi
0x1800c4ab6  cmovg   edi, eax
0x1800c4ab9  mov     dword ptr [rbp+130h+var_1B0], edi
0x1800c4abc  cmp     r12d, ebx
0x1800c4abf  cmovl   ebx, r12d
0x1800c4ac3  mov     dword ptr [rbp+130h+var_1B0+8], ebx
0x1800c4ac6  cmp     r13d, r14d
0x1800c4ac9  cmovg   r14d, r13d
0x1800c4acd  mov     dword ptr [rbp+130h+var_1B0+4], r14d
0x1800c4ad1  cmp     r15d, esi
0x1800c4ad4  cmovl   esi, r15d
0x1800c4ad8  mov     dword ptr [rbp+130h+var_1B0+0Ch], esi
0x1800c4adb  movaps  xmm0, [rbp+130h+var_1B0]
0x1800c4adf  movdqa  [rbp+130h+var_1B0], xmm0
0x1800c4ae4  xor     eax, eax
0x1800c4ae6  lea     ecx, [rax+4]
0x1800c4ae9  movd    xmm0, dword ptr [rbp+rax+130h+var_1B0]
0x1800c4aef  cvtdq2ps xmm0, xmm0
0x1800c4af2  movss   [rbp+rax+130h+var_178], xmm0
0x1800c4af8  lea     rax, [rax+4]
0x1800c4afc  sub     rcx, 1
0x1800c4b00  jnz     short loc_1800C4AE9
0x1800c4b02  lea     rcx, [rbp+130h+arg_18]
0x1800c4b09  call    sub_1800C21C4
0x1800c4b0e  mov     ecx, [rax]
0x1800c4b10  neg     ecx
0x1800c4b12  movd    xmm7, ecx
0x1800c4b16  cvtdq2pd xmm7, xmm7
0x1800c4b1a  lea     rcx, [rbp+130h+var_180]
0x1800c4b1e  call    sub_1800C21C4
0x1800c4b23  mov     ecx, [rax]
0x1800c4b25  neg     ecx
0x1800c4b27  movd    xmm6, ecx
0x1800c4b2b  cvtdq2pd xmm6, xmm6
0x1800c4b2f  lea     rdx, [rbp+130h+var_130]
0x1800c4b33  mov     rcx, [rbp+130h+arg_0]
0x1800c4b3a  call    ?GetScalingFactor@BitmapBasedPrinter@GEL@@UEBA?AU?$TScaling2@N@Math@@XZ; GEL::BitmapBasedPrinter::GetScalingFactor(void)
0x1800c4b3f  mov     rax, [rbp+130h+arg_0]
0x1800c4b46  movd    xmm8, dword ptr [rax+148h]
0x1800c4b4f  cvtdq2pd xmm8, xmm8
0x1800c4b54  movd    xmm5, dword ptr [rax+144h]
0x1800c4b5c  cvtdq2pd xmm5, xmm5
0x1800c4b60  movss   xmm3, [rbp+130h+var_16C]
0x1800c4b65  cvtps2pd xmm3, xmm3
0x1800c4b68  addsd   xmm3, xmm7
0x1800c4b6c  movss   xmm10, [rbp+130h+var_170]
0x1800c4b72  cvtps2pd xmm2, xmm10
0x1800c4b76  addsd   xmm2, xmm6
0x1800c4b7a  movss   xmm12, [rbp+130h+var_174]
0x1800c4b80  cvtps2pd xmm1, xmm12
0x1800c4b84  addsd   xmm1, xmm7
0x1800c4b88  movss   xmm13, [rbp+130h+var_178]
0x1800c4b8e  cvtps2pd xmm0, xmm13
0x1800c4b92  addsd   xmm0, xmm6
0x1800c4b96  movsd   qword ptr [rbp+130h+var_1B0], xmm0
0x1800c4b9b  movsd   qword ptr [rbp+130h+var_1B0+8], xmm1
0x1800c4ba0  movsd   [rbp+130h+var_1A0], xmm2
0x1800c4ba5  movsd   [rbp+130h+var_198], xmm3
0x1800c4baa  lea     r8, [rbp+130h+var_130]
0x1800c4bae  lea     rdx, [rbp+130h+var_1B0]
0x1800c4bb2  lea     rcx, [rbp+130h+var_E0]
0x1800c4bb6  call    ??$?DV?$TUnits@NUDevicePixels@Math@@@Math@@NV01@@Math@@YA?AU?$TRect@V?$TUnits@NUDevicePixels@Math@@@Math@@@0@AEBU10@AEBU?$TScaling2@N@0@@Z; Math::operator*<Math::TUnits<double,Math::DevicePixels>,double,Math::TUnits<double,Math::DevicePixels>>(Math::TRect<Math::TUnits<double,Math::DevicePixels>> const &,Math::TScaling2<double> const &)
0x1800c4bbb  movaps  xmm4, xmm8
0x1800c4bbf  addsd   xmm4, qword ptr [rax+18h]
0x1800c4bc4  movaps  xmm0, xmm5
0x1800c4bc7  addsd   xmm0, qword ptr [rax+10h]
0x1800c4bcc  addsd   xmm8, qword ptr [rax+8]
0x1800c4bd2  addsd   xmm5, qword ptr [rax]
0x1800c4bd6  movsd   [rbp+130h+var_158], xmm5
0x1800c4bdb  movsd   [rbp+130h+var_150], xmm8
0x1800c4be1  movsd   [rbp+130h+var_148], xmm0
0x1800c4be6  movsd   [rbp+130h+var_140], xmm4
0x1800c4beb  lea     rcx, [rbp+130h+var_168]
0x1800c4bef  lea     rax, [rbp+130h+var_158]
0x1800c4bf3  mov     edx, 4
0x1800c4bf8  movsd   xmm0, qword ptr [rax]
0x1800c4bfc  cvtpd2ps xmm1, xmm0
0x1800c4c00  movss   dword ptr [rcx], xmm1
0x1800c4c04  add     rax, 8
0x1800c4c08  add     rcx, 4
0x1800c4c0c  sub     rdx, 1
0x1800c4c10  jnz     short loc_1800C4BF8
0x1800c4c12  cmp     edi, ebx
0x1800c4c14  jge     loc_1800C4DCC
0x1800c4c1a  cmp     r14d, esi
0x1800c4c1d  jge     loc_1800C4DCC
0x1800c4c23  movss   xmm7, [rbp+130h+var_168]
0x1800c4c28  movss   xmm6, [rbp+130h+var_160]
0x1800c4c2d  comiss  xmm7, xmm6
0x1800c4c30  jnb     loc_1800C4DCC
0x1800c4c36  movss   xmm8, [rbp+130h+var_164]
0x1800c4c3c  comiss  xmm8, [rbp+130h+var_15C]
0x1800c4c41  jnb     loc_1800C4DCC
0x1800c4c47  mov     rsi, [rbp+130h+arg_0]
0x1800c4c4e  lea     rcx, [rsi+138h]
0x1800c4c55  call    ??C?$TCntPtr@UIWICImagingFactory@@@Mso@@QEBAPEAUIWICImagingFactory@@XZ; Mso::TCntPtr<IWICImagingFactory>::operator->(void)
0x1800c4c5a  mov     rcx, rax; this
0x1800c4c5d  call    ?GetGpGraphics@GraphicsSurface@GEL@@QEAAAEAVGpGraphics@Gdiplus@@XZ; GEL::GraphicsSurface::GetGpGraphics(void)
0x1800c4c62  mov     rbx, rax
0x1800c4c65  xor     r14d, r14d
0x1800c4c68  mov     [rbp+130h+var_190], r14
0x1800c4c6c  mov     [rbp+130h+var_188], rax
0x1800c4c70  mov     rdx, rax; struct Gdiplus::GpGraphics *
0x1800c4c73  lea     rcx, [rbp+130h+var_158]; this
0x1800c4c77  call    ??0GDIPixelModeRestorer@GEL@@QEAA@AEAVGpGraphics@Gdiplus@@@Z; GEL::GDIPixelModeRestorer::GDIPixelModeRestorer(Gdiplus::GpGraphics &)
0x1800c4c7c  nop
0x1800c4c7d  cmp     [rbp+130h+var_190], r14
0x1800c4c81  jnz     loc_1800C4DF6
0x1800c4c87  lea     rcx, [rbp+130h+var_190]
0x1800c4c8b  call    cs:__imp_GdipCreateRegion
0x1800c4c91  mov     r9d, 25454D8h
0x1800c4c97  mov     ecx, eax
0x1800c4c99  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800c4c9e  mov     rdx, [rbp+130h+var_190]
0x1800c4ca2  mov     rcx, rbx
0x1800c4ca5  call    cs:__imp_GdipGetClip
0x1800c4cab  mov     r9d, 25454D9h
0x1800c4cb1  mov     ecx, eax
0x1800c4cb3  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800c4cb8  nop
0x1800c4cb9  lea     rcx, [rbp+130h+var_158]; this
0x1800c4cbd  call    ??1GDIPixelModeRestorer@GEL@@QEAA@XZ; GEL::GDIPixelModeRestorer::~GDIPixelModeRestorer(void)
0x1800c4cc2  mov     rdx, rbx; struct Gdiplus::GpGraphics *
0x1800c4cc5  lea     rcx, [rbp+130h+var_100]; this
0x1800c4cc9  call    ??0GDIPixelModeRestorer@GEL@@QEAA@AEAVGpGraphics@Gdiplus@@@Z; GEL::GDIPixelModeRestorer::GDIPixelModeRestorer(Gdiplus::GpGraphics &)
0x1800c4cce  lea     rdx, [rbp+130h+var_120]
0x1800c4cd2  mov     rcx, rbx
0x1800c4cd5  call    ?SetClipToBounds@Printer@GEL@@KAXPEAVGpGraphics@Gdiplus@@AEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@@Z; GEL::Printer::SetClipToBounds(Gdiplus::GpGraphics *,Math::TRect<Math::TUnits<int,Math::DevicePixels>> const &)
0x1800c4cda  comiss  xmm13, xmm10
0x1800c4cde  ja      short loc_1800C4CF3
0x1800c4ce0  comiss  xmm12, [rbp+130h+var_16C]
0x1800c4ce5  ja      short loc_1800C4CF3
0x1800c4ce7  movss   xmm1, [rbp+130h+var_16C]
0x1800c4cec  subss   xmm1, xmm12
0x1800c4cf1  jmp     short loc_1800C4CF6
0x1800c4cf3  xorps   xmm1, xmm1
0x1800c4cf6  comiss  xmm13, xmm10
0x1800c4cfa  ja      short loc_1800C4D0A
0x1800c4cfc  comiss  xmm12, [rbp+130h+var_16C]
0x1800c4d01  ja      short loc_1800C4D0A
0x1800c4d03  subss   xmm10, xmm13
0x1800c4d08  jmp     short loc_1800C4D0E
0x1800c4d0a  xorps   xmm10, xmm10
0x1800c4d0e  comiss  xmm7, xmm6
0x1800c4d11  ja      short loc_1800C4D26
0x1800c4d13  comiss  xmm8, [rbp+130h+var_15C]
0x1800c4d18  ja      short loc_1800C4D26
0x1800c4d1a  movss   xmm0, [rbp+130h+var_15C]
0x1800c4d1f  subss   xmm0, xmm8
0x1800c4d24  jmp     short loc_1800C4D29
0x1800c4d26  xorps   xmm0, xmm0
0x1800c4d29  comiss  xmm7, xmm6
0x1800c4d2c  ja      short loc_1800C4D3B
0x1800c4d2e  comiss  xmm8, [rbp+130h+var_15C]
0x1800c4d33  ja      short loc_1800C4D3B
0x1800c4d35  subss   xmm6, xmm7
0x1800c4d39  jmp     short loc_1800C4D3E
0x1800c4d3b  xorps   xmm6, xmm6
0x1800c4d3e  mov     qword ptr [rsp+230h+var_1C8], r14
0x1800c4d43  mov     [rsp+230h+var_1D0], r14
0x1800c4d48  mov     [rsp+230h+var_1D8], r14
0x1800c4d4d  mov     dword ptr [rsp+230h+var_1E0], 2
0x1800c4d55  movss   [rsp+230h+var_1E8], xmm1
0x1800c4d5b  movss   [rsp+230h+var_1F0], xmm10
0x1800c4d62  movss   [rsp+230h+var_1F8], xmm12
0x1800c4d69  movss   [rsp+230h+var_200], xmm13
0x1800c4d70  movss   [rsp+230h+var_208], xmm0
0x1800c4d76  movss   [rsp+230h+var_210], xmm6
  ... truncated ...
```
