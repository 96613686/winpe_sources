# GEL::ConvertGDIPathToGELPath(Gdiplus::GpPath const &)

- ea: `0x1800809b0`
- end: `0x180080d53`
- name: `?ConvertGDIPathToGELPath@GEL@@YA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBVGpPath@Gdiplus@@@Z`
- size: `931`
- prototype: ``
- caller_count: `3`
- callee_count: `15`
- tags: `file_ops`

## callers

- `0x180159af0`
- `0x1801cdb70`
- `0x1801cdb90`

## callees

- `0x180020198`
- `0x180020da0`
- `0x180020f90`
- `0x180021400`
- `0x18003c2b0`
- `0x180057e70`
- `0x180077210`
- `0x180077310`
- `0x18007f754`
- `0x1800809b0`
- `0x180090490`
- `0x180092a58`
- `0x1800c5cf0`
- `0x1800dd460`
- `0x1801002e4`

## import_xrefs

- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180080d42`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180080d42`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180080b94`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180080bad`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180080bbc`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180080b94`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180080bad`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180080bbc`
- `gdiplus!GdipGetPathPoints` at `0x180080aa4`
- `gdiplus!GdipGetPathPoints` at `0x180080aa4`
- `gdiplus!GdipGetPathTypes` at `0x180080a75`
- `gdiplus!GdipGetPathTypes` at `0x180080a75`
- `gdiplus!GdipGetPointCount` at `0x180080a2e`
- `gdiplus!GdipGetPointCount` at `0x180080a2e`
- `gdiplus!GdipGetPathFillMode` at `0x180080a0e`
- `gdiplus!GdipGetPathFillMode` at `0x180080a0e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GEL::ConvertGDIPathToGELPath(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int PathFillMode; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  unsigned int PointCount; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  unsigned __int64 v11; // rdx
  Mso::Memory *v12; // rbx
  unsigned int PathTypes; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  unsigned int PathPoints; // eax
  __int64 v17; // rdx
  __int64 v18; // r8
  char v19; // al
  signed int v20; // r8d
  signed int v21; // edx
  Mso::Memory *v22; // r14
  char *v23; // r13
  float *v24; // rsi
  float *v25; // r15
  float *v26; // r12
  __int64 v27; // rsi
  void *v28; // rdx
  void *v29; // rdx
  __m64 *v31; // rax
  signed int v32; // [rsp+20h] [rbp-89h] BYREF
  unsigned int v33; // [rsp+24h] [rbp-85h] BYREF
  void *v34; // [rsp+28h] [rbp-81h] BYREF
  __int128 v35; // [rsp+30h] [rbp-79h] BYREF
  int v36; // [rsp+40h] [rbp-69h]
  unsigned int v37; // [rsp+44h] [rbp-65h]
  Mso::Memory *v38; // [rsp+48h] [rbp-61h]
  int v39; // [rsp+50h] [rbp-59h]
  unsigned int v40; // [rsp+54h] [rbp-55h]
  __int64 v41; // [rsp+58h] [rbp-51h] BYREF
  int v42; // [rsp+60h] [rbp-49h]
  unsigned int v43; // [rsp+64h] [rbp-45h]
  __int16 v44; // [rsp+68h] [rbp-41h]
  Mso::Memory *v45; // [rsp+78h] [rbp-31h]
  double v46[2]; // [rsp+80h] [rbp-29h] BYREF
  double v47[2]; // [rsp+90h] [rbp-19h] BYREF
  double v48[2]; // [rsp+A0h] [rbp-9h] BYREF
  double v49[2]; // [rsp+B0h] [rbp+7h] BYREF
  __m128d v50; // [rsp+C0h] [rbp+17h] BYREF
  int v52; // [rsp+120h] [rbp+77h]
  signed int v53; // [rsp+128h] [rbp+7Fh]

  v35 = 0;
  v36 = 0;
  v37 = 0x80000000;
  v38 = 0;
  v39 = 0;
  v40 = 0x80000000;
  v41 = 0;
  v42 = 0;
  v43 = 0x80000000;
  v44 = 0;
  v33 = 0;
  PathFillMode = GdipGetPathFillMode(a2, &v33, a3, a4);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(PathFillMode, v6, v7, 39081153);
  v32 = 0;
  PointCount = GdipGetPointCount(a2, &v32);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(PointCount, v9, v10, 39081154);
  if ( v32 <= 0 )
  {
    v27 = a1;
    GEL::IEmptyPath::Create(a1);
  }
  else
  {
    v45 = 0;
    v12 = (Mso::Memory *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)(unsigned int)v32, v11, v32);
    v45 = v12;
    PathTypes = GdipGetPathTypes(a2, v12, (unsigned int)v32);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(PathTypes, v14, v15, 39081155);
    Ofc::TArrOwnerPtr<Gdiplus::PointF>::TArrOwnerPtr<Gdiplus::PointF>(&v34);
    PathPoints = GdipGetPathPoints(a2, v34, (unsigned int)v32);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(PathPoints, v17, v18, 39081156);
    v19 = 1;
    v20 = 0;
    v53 = 0;
    v21 = 3;
    v52 = 3;
    v22 = v12;
    v23 = (char *)v12 - 1;
    v24 = (float *)v34;
    v25 = (float *)((char *)v34 + 8);
    v26 = (float *)((char *)v34 + 16);
    while ( v20 < v32 )
    {
      if ( v19 && (*(_BYTE *)v22 & 7) != 0 )
      {
        Ofc::CInvalidParamException::ThrowTag(0x281642u);
        __debugbreak();
      }
      if ( (*(_BYTE *)v22 & 7) != 0 )
      {
        if ( (*(_BYTE *)v22 & 7) == 1 )
        {
          v49[0] = *v24;
          v49[1] = v24[1];
          GEL::PathBuilder::LineTo(&v35, v49);
          v20 = ++v53;
          v21 = ++v52;
          v22 = (Mso::Memory *)((char *)v22 + 1);
          v26 += 2;
          v25 += 2;
          v24 += 2;
          ++v23;
        }
        else
        {
          if ( (*(_BYTE *)v22 & 7) != 3 )
          {
            MsoShipAssertTagProc(2627141);
            Ofc::CInvalidParamException::ThrowTag(0x281646u);
            __debugbreak();
          }
          if ( v21 > v32 )
          {
            GEL::FailureException::ThrowTag(0x85829Fu);
            __debugbreak();
          }
          v46[0] = *v26;
          v46[1] = v26[1];
          v47[0] = *v25;
          v47[1] = v25[1];
          v48[0] = *v24;
          v48[1] = v24[1];
          GEL::PathBuilder::BezierTo(&v35, v48, v47, v46);
          v20 = v53 + 3;
          v53 += 3;
          v21 = v52 + 3;
          v52 += 3;
          v22 = (Mso::Memory *)((char *)v22 + 3);
          v26 += 6;
          v25 += 6;
          v24 += 6;
          v23 += 3;
        }
      }
      else
      {
        if ( v36 )
        {
          GEL::PathBuilder::EndFigure(&v35, 0);
          v21 = v52;
          v20 = v53;
        }
        v31 = (__m64 *)v24;
        v53 = v20 + 1;
        v52 = v21 + 1;
        v22 = (Mso::Memory *)((char *)v22 + 1);
        v26 += 2;
        v25 += 2;
        v24 += 2;
        ++v23;
        v50 = _mm_cvtps_pd((__m64)v31->m64_u64);
        GEL::PathBuilder::BeginFigure(&v35, &v50);
        v21 = v52;
        v20 = v53;
      }
      if ( *v23 < 0 )
      {
        GEL::PathBuilder::EndFigure(&v35, 1);
        v21 = v52;
        v20 = v53;
        v19 = 1;
      }
      else
      {
        v19 = 0;
      }
    }
    if ( v36 )
      GEL::PathBuilder::EndFigure(&v35, 0);
    v27 = a1;
    GEL::PathBuilder::Finish(&v35, a1, v33);
    operator delete(v34);
    if ( v12 )
      Mso::Memory::Free(v12, v28);
  }
  Ofc::TArray<Ofc::TCntPtr<GEL::IEffect const>>::~TArray<Ofc::TCntPtr<GEL::IEffect const>>(&v41);
  if ( v38 )
    Mso::Memory::Free(v38, v29);
  if ( *((_QWORD *)&v35 + 1) )
    Mso::Memory::Free(*((Mso::Memory **)&v35 + 1), v29);
  if ( (_QWORD)v35 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v35 + 8LL))(v35);
  return v27;
}

```

## disassembly

```asm
0x1800809b0  mov     [rsp-8+arg_0], rcx
0x1800809b5  push    rbp
0x1800809b6  push    rbx
0x1800809b7  push    rsi
0x1800809b8  push    r12
0x1800809ba  push    r13
0x1800809bc  push    r14
0x1800809be  push    r15
0x1800809c0  lea     rbp, [rsp-27h]
0x1800809c5  sub     rsp, 0D0h
0x1800809cc  mov     rsi, rdx
0x1800809cf  xor     r14d, r14d
0x1800809d2  xorps   xmm0, xmm0
0x1800809d5  movdqa  [rbp+57h+var_D0], xmm0
0x1800809da  mov     [rbp+57h+var_C0], r14d
0x1800809de  mov     eax, 80000000h
0x1800809e3  mov     [rbp+57h+var_BC], eax
0x1800809e6  mov     [rbp+57h+var_B8], r14
0x1800809ea  mov     [rbp+57h+var_B0], r14d
0x1800809ee  mov     [rbp+57h+var_AC], eax
0x1800809f1  mov     [rbp+57h+var_A8], r14
0x1800809f5  mov     [rbp+57h+var_A0], r14d
0x1800809f9  mov     [rbp+57h+var_9C], eax
0x1800809fc  mov     [rbp+57h+var_98], r14w
0x180080a01  mov     dword ptr [rsp+100h+var_E0+4], r14d
0x180080a06  lea     rdx, [rsp+100h+var_E0+4]
0x180080a0b  mov     rcx, rsi
0x180080a0e  call    cs:__imp_GdipGetPathFillMode
0x180080a14  mov     r9d, 25454C1h
0x180080a1a  mov     ecx, eax
0x180080a1c  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180080a21  mov     dword ptr [rsp+100h+var_E0], r14d
0x180080a26  lea     rdx, [rsp+100h+var_E0]
0x180080a2b  mov     rcx, rsi
0x180080a2e  call    cs:__imp_GdipGetPointCount
0x180080a34  mov     r9d, 25454C2h
0x180080a3a  mov     ecx, eax
0x180080a3c  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180080a41  mov     r8d, dword ptr [rsp+100h+var_E0]; unsigned int
0x180080a46  test    r8d, r8d
0x180080a49  jle     loc_180080BEE
0x180080a4f  mov     ebx, r14d
0x180080a52  mov     [rbp+57h+var_88], rbx
0x180080a56  test    r8d, r8d
0x180080a59  jz      short loc_180080A6F
0x180080a5b  mov     ecx, r8d; this
0x180080a5e  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x180080a63  mov     rbx, rax
0x180080a66  mov     [rbp+57h+var_88], rax
0x180080a6a  mov     r8d, dword ptr [rsp+100h+var_E0]
0x180080a6f  mov     rdx, rbx
0x180080a72  mov     rcx, rsi
0x180080a75  call    cs:__imp_GdipGetPathTypes
0x180080a7b  mov     r9d, 25454C3h
0x180080a81  mov     ecx, eax
0x180080a83  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180080a88  mov     edx, dword ptr [rsp+100h+var_E0]
0x180080a8c  lea     rcx, [rsp+100h+var_D8]
0x180080a91  call    ??0?$TArrOwnerPtr@VPointF@Gdiplus@@@Ofc@@QEAA@K@Z; Ofc::TArrOwnerPtr<Gdiplus::PointF>::TArrOwnerPtr<Gdiplus::PointF>(ulong)
0x180080a96  nop
0x180080a97  mov     r8d, dword ptr [rsp+100h+var_E0]
0x180080a9c  mov     rdx, [rsp+100h+var_D8]
0x180080aa1  mov     rcx, rsi
0x180080aa4  call    cs:__imp_GdipGetPathPoints
0x180080aaa  mov     r9d, 25454C4h
0x180080ab0  mov     ecx, eax
0x180080ab2  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180080ab7  mov     al, 1
0x180080ab9  mov     r8d, r14d
0x180080abc  mov     [rbp+57h+arg_18], r14d
0x180080ac0  mov     edx, 3
0x180080ac5  mov     [rbp+57h+arg_10], edx
0x180080ac8  mov     r14, rbx
0x180080acb  lea     r13, [rbx-1]
0x180080acf  mov     rsi, [rsp+100h+var_D8]
0x180080ad4  lea     r15, [rsi+8]
0x180080ad8  lea     r12, [rsi+10h]
0x180080adc  cmp     r8d, dword ptr [rsp+100h+var_E0]
0x180080ae1  jge     short loc_180080B5B
0x180080ae3  test    al, al
0x180080ae5  jnz     loc_180080C76
0x180080aeb  movzx   ecx, byte ptr [r14]
0x180080aef  and     ecx, 7
0x180080af2  jz      loc_180080BFC
0x180080af8  sub     ecx, 1
0x180080afb  jnz     loc_180080C8B
0x180080b01  movss   xmm0, dword ptr [rsi]
0x180080b05  cvtps2pd xmm0, xmm0
0x180080b08  movsd   [rbp+57h+var_50], xmm0
0x180080b0d  movss   xmm1, dword ptr [rsi+4]
0x180080b12  cvtps2pd xmm1, xmm1
0x180080b15  movsd   [rbp+57h+var_48], xmm1
0x180080b1a  lea     rdx, [rbp+57h+var_50]
0x180080b1e  lea     rcx, [rbp+57h+var_D0]
0x180080b22  call    ?LineTo@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TPoint2@N@Math@@@Z; GEL::PathBuilder::LineTo(Math::TPoint2<double> const &)
0x180080b27  mov     r8d, [rbp+57h+arg_18]
0x180080b2b  inc     r8d
0x180080b2e  mov     [rbp+57h+arg_18], r8d
0x180080b32  mov     edx, [rbp+57h+arg_10]
0x180080b35  inc     edx
0x180080b37  mov     [rbp+57h+arg_10], edx
0x180080b3a  inc     r14
0x180080b3d  add     r12, 8
0x180080b41  add     r15, 8
0x180080b45  add     rsi, 8
0x180080b49  inc     r13
0x180080b4c  cmp     byte ptr [r13+0], 0
0x180080b51  jl      loc_180080C55
0x180080b57  xor     al, al
0x180080b59  jmp     short loc_180080ADC
0x180080b5b  cmp     [rbp+57h+var_C0], 0
0x180080b5f  jz      short loc_180080B6C
0x180080b61  xor     edx, edx
0x180080b63  lea     rcx, [rbp+57h+var_D0]
0x180080b67  call    ?EndFigure@PathBuilder@GEL@@QEAAAEAV12@W4FigureEnd@Path@Graphics@Mso@@@Z; GEL::PathBuilder::EndFigure(Mso::Graphics::Path::FigureEnd)
0x180080b6c  mov     r8d, dword ptr [rsp+100h+var_E0+4]
0x180080b71  mov     rsi, [rbp+57h+arg_0]
0x180080b75  mov     rdx, rsi
0x180080b78  lea     rcx, [rbp+57h+var_D0]
0x180080b7c  call    ?Finish@PathBuilder@GEL@@QEAA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@W4FillMode@Path@Graphics@Mso@@@Z; GEL::PathBuilder::Finish(Mso::Graphics::Path::FillMode)
0x180080b81  nop
0x180080b82  mov     rcx, [rsp+100h+var_D8]; void *
0x180080b87  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180080b8c  test    rbx, rbx
0x180080b8f  jz      short loc_180080B9B
0x180080b91  mov     rcx, rbx
0x180080b94  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x180080b9a  nop
0x180080b9b  lea     rcx, [rbp+57h+var_A8]
0x180080b9f  call    ??1?$TArray@V?$TCntPtr@$$CBUIEffect@GEL@@@Ofc@@@Ofc@@QEAA@XZ; Ofc::TArray<Ofc::TCntPtr<GEL::IEffect const>>::~TArray<Ofc::TCntPtr<GEL::IEffect const>>(void)
0x180080ba4  mov     rcx, [rbp+57h+var_B8]
0x180080ba8  test    rcx, rcx
0x180080bab  jz      short loc_180080BB3
0x180080bad  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x180080bb3  mov     rcx, qword ptr [rbp+57h+var_D0+8]
0x180080bb7  test    rcx, rcx
0x180080bba  jz      short loc_180080BC2
0x180080bbc  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x180080bc2  mov     rcx, qword ptr [rbp+57h+var_D0]
0x180080bc6  test    rcx, rcx
0x180080bc9  jz      short loc_180080BD8
0x180080bcb  mov     rax, [rcx]
0x180080bce  mov     rax, [rax+8]
0x180080bd2  call    cs:__guard_dispatch_icall_fptr
0x180080bd8  mov     rax, rsi
0x180080bdb  add     rsp, 0D0h
0x180080be2  pop     r15
0x180080be4  pop     r14
0x180080be6  pop     r13
0x180080be8  pop     r12
0x180080bea  pop     rsi
0x180080beb  pop     rbx
0x180080bec  pop     rbp
0x180080bed  retn
0x180080bee  mov     rsi, [rbp+57h+arg_0]
0x180080bf2  mov     rcx, rsi
0x180080bf5  call    ?Create@IEmptyPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@XZ; GEL::IEmptyPath::Create(void)
0x180080bfa  jmp     short loc_180080B9B
0x180080bfc  cmp     [rbp+57h+var_C0], 0
0x180080c00  jz      short loc_180080C14
0x180080c02  xor     edx, edx
0x180080c04  lea     rcx, [rbp+57h+var_D0]
0x180080c08  call    ?EndFigure@PathBuilder@GEL@@QEAAAEAV12@W4FigureEnd@Path@Graphics@Mso@@@Z; GEL::PathBuilder::EndFigure(Mso::Graphics::Path::FigureEnd)
0x180080c0d  mov     edx, [rbp+57h+arg_10]
0x180080c10  mov     r8d, [rbp+57h+arg_18]
0x180080c14  mov     rax, rsi
0x180080c17  inc     r8d
0x180080c1a  mov     [rbp+57h+arg_18], r8d
0x180080c1e  inc     edx
0x180080c20  mov     [rbp+57h+arg_10], edx
0x180080c23  inc     r14
0x180080c26  add     r12, 8
0x180080c2a  add     r15, 8
0x180080c2e  add     rsi, 8
0x180080c32  inc     r13
0x180080c35  cvtps2pd xmm0, qword ptr [rax]
0x180080c38  movups  [rbp+57h+var_40], xmm0
0x180080c3c  lea     rdx, [rbp+57h+var_40]
0x180080c40  lea     rcx, [rbp+57h+var_D0]
0x180080c44  call    ?BeginFigure@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TPoint2@N@Math@@@Z; GEL::PathBuilder::BeginFigure(Math::TPoint2<double> const &)
0x180080c49  mov     edx, [rbp+57h+arg_10]
0x180080c4c  mov     r8d, [rbp+57h+arg_18]
0x180080c50  jmp     loc_180080B4C
0x180080c55  mov     [rbp+57h+arg_8], 1
0x180080c59  mov     edx, 1
0x180080c5e  lea     rcx, [rbp+57h+var_D0]
0x180080c62  call    ?EndFigure@PathBuilder@GEL@@QEAAAEAV12@W4FigureEnd@Path@Graphics@Mso@@@Z; GEL::PathBuilder::EndFigure(Mso::Graphics::Path::FigureEnd)
0x180080c67  mov     edx, [rbp+57h+arg_10]
0x180080c6a  mov     r8d, [rbp+57h+arg_18]
0x180080c6e  mov     al, [rbp+57h+arg_8]
0x180080c71  jmp     loc_180080ADC
0x180080c76  test    byte ptr [r14], 7
0x180080c7a  jz      loc_180080AEB
0x180080c80  mov     ecx, 281642h; unsigned int
0x180080c85  call    ?ThrowTag@CInvalidParamException@Ofc@@SAXK@Z; Ofc::CInvalidParamException::ThrowTag(ulong)
0x180080c8a  int     3; Trap to Debugger
0x180080c8b  cmp     ecx, 2
0x180080c8e  jnz     loc_180080D3D
0x180080c94  cmp     edx, dword ptr [rsp+100h+var_E0]
0x180080c98  jg      loc_180080D32
0x180080c9e  movss   xmm0, dword ptr [r12]
0x180080ca4  cvtps2pd xmm0, xmm0
0x180080ca7  movsd   [rbp+57h+var_80], xmm0
0x180080cac  movss   xmm1, dword ptr [r12+4]
0x180080cb3  cvtps2pd xmm1, xmm1
0x180080cb6  movsd   [rbp+57h+var_78], xmm1
0x180080cbb  movss   xmm0, dword ptr [r15]
0x180080cc0  cvtps2pd xmm0, xmm0
0x180080cc3  movsd   [rbp+57h+var_70], xmm0
0x180080cc8  movss   xmm1, dword ptr [r15+4]
0x180080cce  cvtps2pd xmm1, xmm1
0x180080cd1  movsd   [rbp+57h+var_68], xmm1
0x180080cd6  movss   xmm0, dword ptr [rsi]
0x180080cda  cvtps2pd xmm0, xmm0
0x180080cdd  movsd   [rbp+57h+var_60], xmm0
0x180080ce2  movss   xmm1, dword ptr [rsi+4]
0x180080ce7  cvtps2pd xmm1, xmm1
0x180080cea  movsd   [rbp+57h+var_58], xmm1
0x180080cef  lea     r9, [rbp+57h+var_80]
0x180080cf3  lea     r8, [rbp+57h+var_70]
0x180080cf7  lea     rdx, [rbp+57h+var_60]
0x180080cfb  lea     rcx, [rbp+57h+var_D0]
0x180080cff  call    ?BezierTo@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TPoint2@N@Math@@00@Z; GEL::PathBuilder::BezierTo(Math::TPoint2<double> const &,Math::TPoint2<double> const &,Math::TPoint2<double> const &)
0x180080d04  mov     r8d, [rbp+57h+arg_18]
0x180080d08  add     r8d, 3
0x180080d0c  mov     [rbp+57h+arg_18], r8d
0x180080d10  mov     edx, [rbp+57h+arg_10]
0x180080d13  add     edx, 3
0x180080d16  mov     [rbp+57h+arg_10], edx
0x180080d19  add     r14, 3
0x180080d1d  add     r12, 18h
0x180080d21  add     r15, 18h
0x180080d25  add     rsi, 18h
0x180080d29  add     r13, 3
0x180080d2d  jmp     loc_180080B4C
0x180080d32  mov     ecx, 85829Fh; unsigned int
0x180080d37  call    ?ThrowTag@FailureException@GEL@@SAXK@Z; GEL::FailureException::ThrowTag(ulong)
0x180080d3c  int     3; Trap to Debugger
0x180080d3d  mov     ecx, 281645h
0x180080d42  call    cs:__imp_MsoShipAssertTagProc
0x180080d48  mov     ecx, 281646h; unsigned int
0x180080d4d  call    ?ThrowTag@CInvalidParamException@Ofc@@SAXK@Z; Ofc::CInvalidParamException::ThrowTag(ulong)
0x180080d52  int     3; Trap to Debugger
```
