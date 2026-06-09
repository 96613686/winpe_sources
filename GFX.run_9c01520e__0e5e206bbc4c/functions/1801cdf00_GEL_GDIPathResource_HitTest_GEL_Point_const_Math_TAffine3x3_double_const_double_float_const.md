# GEL::GDIPathResource::HitTest(GEL::Point const &,Math::TAffine3x3<double> const &,double,float const *)

- ea: `0x1801cdf00`
- end: `0x1801ce128`
- name: `?HitTest@GDIPathResource@GEL@@UEBA_NAEBUPoint@2@AEBU?$TAffine3x3@N@Math@@NPEBM@Z`
- size: `552`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180050af0`
- `0x18007f348`
- `0x18007f754`
- `0x180081854`
- `0x1801cdf00`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801cdf54`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801cdf54`
- `gdiplus!GdipIsVisiblePathPoint` at `0x1801ce03f`
- `gdiplus!GdipIsVisiblePathPoint` at `0x1801ce085`
- `gdiplus!GdipIsVisiblePathPoint` at `0x1801ce03f`
- `gdiplus!GdipIsVisiblePathPoint` at `0x1801ce085`
- `gdiplus!GdipWidenPath` at `0x1801ce011`
- `gdiplus!GdipWidenPath` at `0x1801ce011`
- `gdiplus!GdipFlattenPath` at `0x1801cdf86`
- `gdiplus!GdipFlattenPath` at `0x1801cdf86`
- `gdiplus!GdipDeletePen` at `0x1801ce0fd`
- `gdiplus!GdipDeletePen` at `0x1801ce0fd`
- `gdiplus!GdipCreatePen1` at `0x1801cdfeb`
- `gdiplus!GdipCreatePen1` at `0x1801cdfeb`
- `gdiplus!GdipClonePath` at `0x1801cdf63`
- `gdiplus!GdipClonePath` at `0x1801cdf63`
- `gdiplus!GdipDeletePath` at `0x1801ce0a6`
- `gdiplus!GdipDeletePath` at `0x1801ce0cf`
- `gdiplus!GdipDeletePath` at `0x1801ce11d`
- `gdiplus!GdipDeletePath` at `0x1801ce0a6`
- `gdiplus!GdipDeletePath` at `0x1801ce0cf`
- `gdiplus!GdipDeletePath` at `0x1801ce11d`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
char __fastcall GEL::GDIPathResource::HitTest(__int64 a1, __int64 a2, __int64 a3, double a4, __int64 a5)
{
  unsigned int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  unsigned int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rdx
  unsigned int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rdx
  __int64 v20; // r8
  bool v21; // bl
  int v23; // [rsp+30h] [rbp-40h] BYREF
  __int64 v24; // [rsp+38h] [rbp-38h] BYREF
  __int64 v25; // [rsp+40h] [rbp-30h] BYREF
  _QWORD v26[2]; // [rsp+50h] [rbp-20h] BYREF
  int v27; // [rsp+80h] [rbp+10h] BYREF

  if ( !*(_QWORD *)(a1 + 40) )
    return 0;
  v24 = 0;
  Gfx::GpMatrixHolder::GpMatrixHolder(v26, a3);
  v7 = GdipClonePath(*(_QWORD *)(a1 + 40), &v24);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(v7, v8, v9, 39081164);
  v10 = GdipFlattenPath(v24, v26[0]);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(v10, v11, v12, 39081165);
  if ( a5 )
  {
    GEL::ScaleRadius(&v25, v13, a3);
    goto LABEL_4;
  }
  v27 = 0;
  if ( (unsigned int)GdipIsVisiblePathPoint(v24, v13, v14, 0, &v27) || !v27 )
  {
    if ( a4 > 0.0 )
    {
LABEL_4:
      v25 = 0;
      v16 = GdipCreatePen1(4278255615LL, v15, 0, &v25);
      Gfx::GdipStatus_ThrowOnFailureMessageTag(v16, v17, v18, 38322315);
      GdipWidenPath(v24, v25, 0);
      v23 = 0;
      v21 = !(unsigned int)GdipIsVisiblePathPoint(v24, v19, v20, 0, &v23) && v23;
      if ( v25 )
      {
        GdipDeletePen();
        v25 = 0;
      }
      ARC::GDIPlus::TGpHolder<Gdiplus::Matrix>::Empty(v26);
      if ( v24 )
        GdipDeletePath();
      return v21;
    }
    ARC::GDIPlus::TGpHolder<Gdiplus::Matrix>::Empty(v26);
    if ( v24 )
      GdipDeletePath();
    return 0;
  }
  ARC::GDIPlus::TGpHolder<Gdiplus::Matrix>::Empty(v26);
  if ( v24 )
    GdipDeletePath();
  return 1;
}

```

## disassembly

```asm
0x1801cdf00  mov     rax, rsp
0x1801cdf03  mov     [rax+10h], rbx
0x1801cdf07  mov     [rax+18h], rsi
0x1801cdf0b  mov     [rax+20h], rdi
0x1801cdf0f  push    rbp
0x1801cdf10  mov     rbp, rsp
0x1801cdf13  sub     rsp, 70h
0x1801cdf17  movaps  xmmword ptr [rax-18h], xmm6
0x1801cdf1b  movaps  xmm6, xmm3
0x1801cdf1e  mov     rbx, r8
0x1801cdf21  mov     rdi, rdx
0x1801cdf24  mov     rsi, rcx
0x1801cdf27  cmp     qword ptr [rcx+28h], 0
0x1801cdf2c  jz      loc_1801CE0D5
0x1801cdf32  mov     [rbp+var_38], 0
0x1801cdf3a  mov     rdx, rbx
0x1801cdf3d  lea     rcx, [rbp+var_20]
0x1801cdf41  call    ??$?0U?$TAffine3x3@N@Math@@$0A@@GpMatrixHolder@Gfx@@QEAA@AEBU?$TAffine3x3@N@Math@@@Z; Gfx::GpMatrixHolder::GpMatrixHolder(Math::TAffine3x3<double> const &)
0x1801cdf46  cmp     [rbp+var_38], 0
0x1801cdf4b  jz      short loc_1801CDF5B
0x1801cdf4d  xor     edx, edx
0x1801cdf4f  mov     ecx, 1E55E058h
0x1801cdf54  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1801cdf5a  nop
0x1801cdf5b  lea     rdx, [rbp+var_38]
0x1801cdf5f  mov     rcx, [rsi+28h]
0x1801cdf63  call    cs:__imp_GdipClonePath
0x1801cdf69  mov     r9d, 25454CCh
0x1801cdf6f  mov     ecx, eax
0x1801cdf71  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1801cdf76  movss   xmm2, cs:__real@3f800000
0x1801cdf7e  mov     rdx, [rbp+var_20]
0x1801cdf82  mov     rcx, [rbp+var_38]
0x1801cdf86  call    cs:__imp_GdipFlattenPath
0x1801cdf8c  mov     r9d, 25454CDh
0x1801cdf92  mov     ecx, eax
0x1801cdf94  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1801cdf99  mov     rax, [rbp+arg_20]
0x1801cdf9d  test    rax, rax
0x1801cdfa0  jz      loc_1801CE05D
0x1801cdfa6  movss   xmm1, dword ptr [rax]
0x1801cdfaa  cvtps2pd xmm1, xmm1
0x1801cdfad  mov     r8, rbx
0x1801cdfb0  lea     rcx, [rbp+var_30]
0x1801cdfb4  call    ?ScaleRadius@GEL@@YA?AUVector@1@NAEBU?$TAffine3x3@N@Math@@@Z; GEL::ScaleRadius(double,Math::TAffine3x3<double> const &)
0x1801cdfb9  movsd   xmm0, [rbp+var_30]
0x1801cdfbe  maxsd   xmm0, [rbp+var_28]
0x1801cdfc3  addsd   xmm6, xmm0
0x1801cdfc7  movsd   xmm0, cs:__real@4014000000000000
0x1801cdfcf  maxsd   xmm0, xmm6
0x1801cdfd3  mov     [rbp+var_30], 0
0x1801cdfdb  cvtpd2ps xmm1, xmm0
0x1801cdfdf  lea     r9, [rbp+var_30]
0x1801cdfe3  xor     r8d, r8d
0x1801cdfe6  mov     ecx, 0FF00FFFFh
0x1801cdfeb  call    cs:__imp_GdipCreatePen1
0x1801cdff1  mov     r9d, 248C08Bh
0x1801cdff7  mov     ecx, eax
0x1801cdff9  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1801cdffe  movss   xmm3, cs:__real@3f800000
0x1801ce006  xor     r8d, r8d
0x1801ce009  mov     rdx, [rbp+var_30]
0x1801ce00d  mov     rcx, [rbp+var_38]
0x1801ce011  call    cs:__imp_GdipWidenPath
0x1801ce017  mov     [rbp+var_40], 0
0x1801ce01e  movsd   xmm2, qword ptr [rdi+8]
0x1801ce023  cvtpd2ps xmm2, xmm2
0x1801ce027  movsd   xmm1, qword ptr [rdi]
0x1801ce02b  cvtpd2ps xmm1, xmm1
0x1801ce02f  lea     rax, [rbp+var_40]
0x1801ce033  mov     [rsp+70h+var_50], rax
0x1801ce038  xor     r9d, r9d
0x1801ce03b  mov     rcx, [rbp+var_38]
0x1801ce03f  call    cs:__imp_GdipIsVisiblePathPoint
0x1801ce045  test    eax, eax
0x1801ce047  jnz     loc_1801CE0F2
0x1801ce04d  cmp     [rbp+var_40], eax
0x1801ce050  jz      loc_1801CE0F2
0x1801ce056  mov     bl, 1
0x1801ce058  jmp     loc_1801CE0F4
0x1801ce05d  mov     [rbp+arg_0], 0
0x1801ce064  movsd   xmm2, qword ptr [rdi+8]
0x1801ce069  cvtpd2ps xmm2, xmm2
0x1801ce06d  movsd   xmm1, qword ptr [rdi]
0x1801ce071  cvtpd2ps xmm1, xmm1
0x1801ce075  lea     rax, [rbp+arg_0]
0x1801ce079  mov     [rsp+70h+var_50], rax
0x1801ce07e  xor     r9d, r9d
0x1801ce081  mov     rcx, [rbp+var_38]
0x1801ce085  call    cs:__imp_GdipIsVisiblePathPoint
0x1801ce08b  test    eax, eax
0x1801ce08d  jnz     short loc_1801CE0B0
0x1801ce08f  cmp     [rbp+arg_0], eax
0x1801ce092  jz      short loc_1801CE0B0
0x1801ce094  lea     rcx, [rbp+var_20]
0x1801ce098  call    ?Empty@?$TGpHolder@VMatrix@Gdiplus@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGpHolder<Gdiplus::Matrix>::Empty(void)
0x1801ce09d  mov     rcx, [rbp+var_38]
0x1801ce0a1  test    rcx, rcx
0x1801ce0a4  jz      short loc_1801CE0AC
0x1801ce0a6  call    cs:__imp_GdipDeletePath
0x1801ce0ac  mov     al, 1
0x1801ce0ae  jmp     short loc_1801CE0D7
0x1801ce0b0  xorps   xmm0, xmm0
0x1801ce0b3  comisd  xmm0, xmm6
0x1801ce0b7  jb      loc_1801CDFC7
0x1801ce0bd  lea     rcx, [rbp+var_20]
0x1801ce0c1  call    ?Empty@?$TGpHolder@VMatrix@Gdiplus@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGpHolder<Gdiplus::Matrix>::Empty(void)
0x1801ce0c6  mov     rcx, [rbp+var_38]
0x1801ce0ca  test    rcx, rcx
0x1801ce0cd  jz      short loc_1801CE0D5
0x1801ce0cf  call    cs:__imp_GdipDeletePath
0x1801ce0d5  xor     al, al
0x1801ce0d7  lea     r11, [rsp+70h+var_s0]
0x1801ce0dc  mov     rbx, [r11+18h]
0x1801ce0e0  mov     rsi, [r11+20h]
0x1801ce0e4  mov     rdi, [r11+28h]
0x1801ce0e8  movaps  xmm6, [rsp+70h+var_10]
0x1801ce0ed  mov     rsp, r11
0x1801ce0f0  pop     rbp
0x1801ce0f1  retn
0x1801ce0f2  xor     bl, bl
0x1801ce0f4  mov     rcx, [rbp+var_30]
0x1801ce0f8  test    rcx, rcx
0x1801ce0fb  jz      short loc_1801CE10B
0x1801ce0fd  call    cs:__imp_GdipDeletePen
0x1801ce103  mov     [rbp+var_30], 0
0x1801ce10b  lea     rcx, [rbp+var_20]
0x1801ce10f  call    ?Empty@?$TGpHolder@VMatrix@Gdiplus@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGpHolder<Gdiplus::Matrix>::Empty(void)
0x1801ce114  mov     rcx, [rbp+var_38]
0x1801ce118  test    rcx, rcx
0x1801ce11b  jz      short loc_1801CE123
0x1801ce11d  call    cs:__imp_GdipDeletePath
0x1801ce123  mov     al, bl
0x1801ce125  jmp     short loc_1801CE0D7
```
