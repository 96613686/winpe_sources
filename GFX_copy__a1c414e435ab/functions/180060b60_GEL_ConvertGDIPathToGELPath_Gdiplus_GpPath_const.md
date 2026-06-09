# GEL::ConvertGDIPathToGELPath(Gdiplus::GpPath const &)

- ea: `0x180060b60`
- end: `0x180060f0c`
- name: `?ConvertGDIPathToGELPath@GEL@@YA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBVGpPath@Gdiplus@@@Z`
- size: `940`
- prototype: ``
- caller_count: `3`
- callee_count: `15`
- tags: `file_ops`

## callers

- `0x1801590e0`
- `0x1801c8ed0`
- `0x1801c8ef0`

## callees

- `0x18001ffb4`
- `0x1800206f0`
- `0x1800207c0`
- `0x180020e70`
- `0x180038220`
- `0x1800573f0`
- `0x180060b60`
- `0x180062394`
- `0x1800786fc`
- `0x18007a4f0`
- `0x18007a5e0`
- `0x18009d5c0`
- `0x1800a9b44`
- `0x1800dc27c`
- `0x1800e7690`

## import_xrefs

- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180060efb`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180060efb`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180060d3d`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180060d56`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180060d65`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180060d3d`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180060d56`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180060d65`
- `gdiplus!GdipGetPathPoints` at `0x180060c54`
- `gdiplus!GdipGetPathPoints` at `0x180060c54`
- `gdiplus!GdipGetPathTypes` at `0x180060c25`
- `gdiplus!GdipGetPathTypes` at `0x180060c25`
- `gdiplus!GdipGetPointCount` at `0x180060bde`
- `gdiplus!GdipGetPointCount` at `0x180060bde`
- `gdiplus!GdipGetPathFillMode` at `0x180060bbe`
- `gdiplus!GdipGetPathFillMode` at `0x180060bbe`

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
0x180060b60  mov     [rsp-8+arg_0], rcx
0x180060b65  push    rbp
0x180060b66  push    rbx
0x180060b67  push    rsi
0x180060b68  push    r12
0x180060b6a  push    r13
0x180060b6c  push    r14
0x180060b6e  push    r15
0x180060b70  lea     rbp, [rsp-27h]
0x180060b75  sub     rsp, 0D0h
0x180060b7c  mov     rsi, rdx
0x180060b7f  xor     r14d, r14d
0x180060b82  xorps   xmm0, xmm0
0x180060b85  movdqa  [rbp+57h+var_D0], xmm0
0x180060b8a  mov     [rbp+57h+var_C0], r14d
0x180060b8e  mov     eax, 80000000h
0x180060b93  mov     [rbp+57h+var_BC], eax
0x180060b96  mov     [rbp+57h+var_B8], r14
0x180060b9a  mov     [rbp+57h+var_B0], r14d
0x180060b9e  mov     [rbp+57h+var_AC], eax
0x180060ba1  mov     [rbp+57h+var_A8], r14
0x180060ba5  mov     [rbp+57h+var_A0], r14d
0x180060ba9  mov     [rbp+57h+var_9C], eax
0x180060bac  mov     [rbp+57h+var_98], r14w
0x180060bb1  mov     dword ptr [rsp+100h+var_E0+4], r14d
0x180060bb6  lea     rdx, [rsp+100h+var_E0+4]
0x180060bbb  mov     rcx, rsi
0x180060bbe  call    cs:__imp_GdipGetPathFillMode
0x180060bc4  mov     r9d, 25454C1h
0x180060bca  mov     ecx, eax
0x180060bcc  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180060bd1  mov     dword ptr [rsp+100h+var_E0], r14d
0x180060bd6  lea     rdx, [rsp+100h+var_E0]
0x180060bdb  mov     rcx, rsi
0x180060bde  call    cs:__imp_GdipGetPointCount
0x180060be4  mov     r9d, 25454C2h
0x180060bea  mov     ecx, eax
0x180060bec  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180060bf1  mov     r8d, dword ptr [rsp+100h+var_E0]; unsigned int
0x180060bf6  test    r8d, r8d
0x180060bf9  jle     loc_180060D97
0x180060bff  mov     ebx, r14d
0x180060c02  mov     [rbp+57h+var_88], rbx
0x180060c06  test    r8d, r8d
0x180060c09  jz      short loc_180060C1F
0x180060c0b  mov     ecx, r8d; this
0x180060c0e  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x180060c13  mov     rbx, rax
0x180060c16  mov     [rbp+57h+var_88], rax
0x180060c1a  mov     r8d, dword ptr [rsp+100h+var_E0]
0x180060c1f  mov     rdx, rbx
0x180060c22  mov     rcx, rsi
0x180060c25  call    cs:__imp_GdipGetPathTypes
0x180060c2b  mov     r9d, 25454C3h
0x180060c31  mov     ecx, eax
0x180060c33  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180060c38  mov     edx, dword ptr [rsp+100h+var_E0]
0x180060c3c  lea     rcx, [rsp+100h+var_D8]
0x180060c41  call    ??0?$TArrOwnerPtr@VPointF@Gdiplus@@@Ofc@@QEAA@K@Z; Ofc::TArrOwnerPtr<Gdiplus::PointF>::TArrOwnerPtr<Gdiplus::PointF>(ulong)
0x180060c46  nop
0x180060c47  mov     r8d, dword ptr [rsp+100h+var_E0]
0x180060c4c  mov     rdx, [rsp+100h+var_D8]
0x180060c51  mov     rcx, rsi
0x180060c54  call    cs:__imp_GdipGetPathPoints
0x180060c5a  mov     r9d, 25454C4h
0x180060c60  mov     ecx, eax
0x180060c62  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180060c67  mov     al, 1
0x180060c69  mov     r8d, r14d
0x180060c6c  mov     [rbp+57h+arg_18], r14d
0x180060c70  mov     edx, 3
0x180060c75  mov     [rbp+57h+arg_10], edx
0x180060c78  mov     r14, rbx
0x180060c7b  lea     r13, [rbx-1]
0x180060c7f  mov     rsi, [rsp+100h+var_D8]
0x180060c84  lea     r15, [rsi+8]
0x180060c88  lea     r12, [rsi+10h]
0x180060c8c  cmp     r8d, dword ptr [rsp+100h+var_E0]
0x180060c91  jge     short loc_180060D0B
0x180060c93  test    al, al
0x180060c95  jnz     loc_180060E2F
0x180060c9b  movzx   ecx, byte ptr [r14]
0x180060c9f  and     ecx, 7
0x180060ca2  jz      loc_180060DB5
0x180060ca8  sub     ecx, 1
0x180060cab  jnz     loc_180060E44
0x180060cb1  movss   xmm0, dword ptr [rsi]
0x180060cb5  cvtps2pd xmm0, xmm0
0x180060cb8  movsd   [rbp+57h+var_50], xmm0
0x180060cbd  movss   xmm1, dword ptr [rsi+4]
0x180060cc2  cvtps2pd xmm1, xmm1
0x180060cc5  movsd   [rbp+57h+var_48], xmm1
0x180060cca  lea     rdx, [rbp+57h+var_50]
0x180060cce  lea     rcx, [rbp+57h+var_D0]
0x180060cd2  call    ?LineTo@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TPoint2@N@Math@@@Z; GEL::PathBuilder::LineTo(Math::TPoint2<double> const &)
0x180060cd7  mov     r8d, [rbp+57h+arg_18]
0x180060cdb  inc     r8d
0x180060cde  mov     [rbp+57h+arg_18], r8d
0x180060ce2  mov     edx, [rbp+57h+arg_10]
0x180060ce5  inc     edx
0x180060ce7  mov     [rbp+57h+arg_10], edx
0x180060cea  inc     r14
0x180060ced  add     r12, 8
0x180060cf1  add     r15, 8
0x180060cf5  add     rsi, 8
0x180060cf9  inc     r13
0x180060cfc  cmp     byte ptr [r13+0], 0
0x180060d01  jl      loc_180060E0E
0x180060d07  xor     al, al
0x180060d09  jmp     short loc_180060C8C
0x180060d0b  cmp     [rbp+57h+var_C0], 0
0x180060d0f  jnz     loc_180060DA5
0x180060d15  mov     r8d, dword ptr [rsp+100h+var_E0+4]
0x180060d1a  mov     rsi, [rbp+57h+arg_0]
0x180060d1e  mov     rdx, rsi
0x180060d21  lea     rcx, [rbp+57h+var_D0]
0x180060d25  call    ?Finish@PathBuilder@GEL@@QEAA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@W4FillMode@Path@Graphics@Mso@@@Z; GEL::PathBuilder::Finish(Mso::Graphics::Path::FillMode)
0x180060d2a  nop
0x180060d2b  mov     rcx, [rsp+100h+var_D8]; void *
0x180060d30  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180060d35  test    rbx, rbx
0x180060d38  jz      short loc_180060D44
0x180060d3a  mov     rcx, rbx
0x180060d3d  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x180060d43  nop
0x180060d44  lea     rcx, [rbp+57h+var_A8]
0x180060d48  call    ??1?$TArray@V?$TCntPtr@$$CBUIEffect@GEL@@@Ofc@@@Ofc@@QEAA@XZ; Ofc::TArray<Ofc::TCntPtr<GEL::IEffect const>>::~TArray<Ofc::TCntPtr<GEL::IEffect const>>(void)
0x180060d4d  mov     rcx, [rbp+57h+var_B8]
0x180060d51  test    rcx, rcx
0x180060d54  jz      short loc_180060D5C
0x180060d56  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x180060d5c  mov     rcx, qword ptr [rbp+57h+var_D0+8]
0x180060d60  test    rcx, rcx
0x180060d63  jz      short loc_180060D6B
0x180060d65  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x180060d6b  mov     rcx, qword ptr [rbp+57h+var_D0]
0x180060d6f  test    rcx, rcx
0x180060d72  jz      short loc_180060D81
0x180060d74  mov     rax, [rcx]
0x180060d77  mov     rax, [rax+8]
0x180060d7b  call    cs:__guard_dispatch_icall_fptr
0x180060d81  mov     rax, rsi
0x180060d84  add     rsp, 0D0h
0x180060d8b  pop     r15
0x180060d8d  pop     r14
0x180060d8f  pop     r13
0x180060d91  pop     r12
0x180060d93  pop     rsi
0x180060d94  pop     rbx
0x180060d95  pop     rbp
0x180060d96  retn
0x180060d97  mov     rsi, [rbp+57h+arg_0]
0x180060d9b  mov     rcx, rsi
0x180060d9e  call    ?Create@IEmptyPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@XZ; GEL::IEmptyPath::Create(void)
0x180060da3  jmp     short loc_180060D44
0x180060da5  xor     edx, edx
0x180060da7  lea     rcx, [rbp+57h+var_D0]
0x180060dab  call    ?EndFigure@PathBuilder@GEL@@QEAAAEAV12@W4FigureEnd@Path@Graphics@Mso@@@Z; GEL::PathBuilder::EndFigure(Mso::Graphics::Path::FigureEnd)
0x180060db0  jmp     loc_180060D15
0x180060db5  cmp     [rbp+57h+var_C0], 0
0x180060db9  jz      short loc_180060DCD
0x180060dbb  xor     edx, edx
0x180060dbd  lea     rcx, [rbp+57h+var_D0]
0x180060dc1  call    ?EndFigure@PathBuilder@GEL@@QEAAAEAV12@W4FigureEnd@Path@Graphics@Mso@@@Z; GEL::PathBuilder::EndFigure(Mso::Graphics::Path::FigureEnd)
0x180060dc6  mov     edx, [rbp+57h+arg_10]
0x180060dc9  mov     r8d, [rbp+57h+arg_18]
0x180060dcd  mov     rax, rsi
0x180060dd0  inc     r8d
0x180060dd3  mov     [rbp+57h+arg_18], r8d
0x180060dd7  inc     edx
0x180060dd9  mov     [rbp+57h+arg_10], edx
0x180060ddc  inc     r14
0x180060ddf  add     r12, 8
0x180060de3  add     r15, 8
0x180060de7  add     rsi, 8
0x180060deb  inc     r13
0x180060dee  cvtps2pd xmm0, qword ptr [rax]
0x180060df1  movups  [rbp+57h+var_40], xmm0
0x180060df5  lea     rdx, [rbp+57h+var_40]
0x180060df9  lea     rcx, [rbp+57h+var_D0]
0x180060dfd  call    ?BeginFigure@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TPoint2@N@Math@@@Z; GEL::PathBuilder::BeginFigure(Math::TPoint2<double> const &)
0x180060e02  mov     edx, [rbp+57h+arg_10]
0x180060e05  mov     r8d, [rbp+57h+arg_18]
0x180060e09  jmp     loc_180060CFC
0x180060e0e  mov     [rbp+57h+arg_8], 1
0x180060e12  mov     edx, 1
0x180060e17  lea     rcx, [rbp+57h+var_D0]
0x180060e1b  call    ?EndFigure@PathBuilder@GEL@@QEAAAEAV12@W4FigureEnd@Path@Graphics@Mso@@@Z; GEL::PathBuilder::EndFigure(Mso::Graphics::Path::FigureEnd)
0x180060e20  mov     edx, [rbp+57h+arg_10]
0x180060e23  mov     r8d, [rbp+57h+arg_18]
0x180060e27  mov     al, [rbp+57h+arg_8]
0x180060e2a  jmp     loc_180060C8C
0x180060e2f  test    byte ptr [r14], 7
0x180060e33  jz      loc_180060C9B
0x180060e39  mov     ecx, 281642h; unsigned int
0x180060e3e  call    ?ThrowTag@CInvalidParamException@Ofc@@SAXK@Z; Ofc::CInvalidParamException::ThrowTag(ulong)
0x180060e43  int     3; Trap to Debugger
0x180060e44  cmp     ecx, 2
0x180060e47  jnz     loc_180060EF6
0x180060e4d  cmp     edx, dword ptr [rsp+100h+var_E0]
0x180060e51  jg      loc_180060EEB
0x180060e57  movss   xmm0, dword ptr [r12]
0x180060e5d  cvtps2pd xmm0, xmm0
0x180060e60  movsd   [rbp+57h+var_80], xmm0
0x180060e65  movss   xmm1, dword ptr [r12+4]
0x180060e6c  cvtps2pd xmm1, xmm1
0x180060e6f  movsd   [rbp+57h+var_78], xmm1
0x180060e74  movss   xmm0, dword ptr [r15]
0x180060e79  cvtps2pd xmm0, xmm0
0x180060e7c  movsd   [rbp+57h+var_70], xmm0
0x180060e81  movss   xmm1, dword ptr [r15+4]
0x180060e87  cvtps2pd xmm1, xmm1
0x180060e8a  movsd   [rbp+57h+var_68], xmm1
0x180060e8f  movss   xmm0, dword ptr [rsi]
0x180060e93  cvtps2pd xmm0, xmm0
0x180060e96  movsd   [rbp+57h+var_60], xmm0
0x180060e9b  movss   xmm1, dword ptr [rsi+4]
0x180060ea0  cvtps2pd xmm1, xmm1
0x180060ea3  movsd   [rbp+57h+var_58], xmm1
0x180060ea8  lea     r9, [rbp+57h+var_80]
0x180060eac  lea     r8, [rbp+57h+var_70]
0x180060eb0  lea     rdx, [rbp+57h+var_60]
0x180060eb4  lea     rcx, [rbp+57h+var_D0]
0x180060eb8  call    ?BezierTo@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TPoint2@N@Math@@00@Z; GEL::PathBuilder::BezierTo(Math::TPoint2<double> const &,Math::TPoint2<double> const &,Math::TPoint2<double> const &)
0x180060ebd  mov     r8d, [rbp+57h+arg_18]
0x180060ec1  add     r8d, 3
0x180060ec5  mov     [rbp+57h+arg_18], r8d
0x180060ec9  mov     edx, [rbp+57h+arg_10]
0x180060ecc  add     edx, 3
0x180060ecf  mov     [rbp+57h+arg_10], edx
0x180060ed2  add     r14, 3
0x180060ed6  add     r12, 18h
0x180060eda  add     r15, 18h
0x180060ede  add     rsi, 18h
0x180060ee2  add     r13, 3
0x180060ee6  jmp     loc_180060CFC
0x180060eeb  mov     ecx, 85829Fh; unsigned int
0x180060ef0  call    ?ThrowTag@FailureException@GEL@@SAXK@Z; GEL::FailureException::ThrowTag(ulong)
0x180060ef5  int     3; Trap to Debugger
0x180060ef6  mov     ecx, 281645h
0x180060efb  call    cs:__imp_MsoShipAssertTagProc
0x180060f01  mov     ecx, 281646h; unsigned int
0x180060f06  call    ?ThrowTag@CInvalidParamException@Ofc@@SAXK@Z; Ofc::CInvalidParamException::ThrowTag(ulong)
0x180060f0b  int     3; Trap to Debugger
```
