# GEL::GDIPathResource::HitTest(GEL::Point const &,Math::TAffine3x3<double> const &,double,float const *)

- ea: `0x1801c9260`
- end: `0x1801c9488`
- name: `?HitTest@GDIPathResource@GEL@@UEBA_NAEBUPoint@2@AEBU?$TAffine3x3@N@Math@@NPEBM@Z`
- size: `552`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18004f2a0`
- `0x180060904`
- `0x180061f98`
- `0x180062394`
- `0x1801c9260`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801c92b4`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801c92b4`
- `gdiplus!GdipIsVisiblePathPoint` at `0x1801c939f`
- `gdiplus!GdipIsVisiblePathPoint` at `0x1801c93e5`
- `gdiplus!GdipIsVisiblePathPoint` at `0x1801c939f`
- `gdiplus!GdipIsVisiblePathPoint` at `0x1801c93e5`
- `gdiplus!GdipWidenPath` at `0x1801c9371`
- `gdiplus!GdipWidenPath` at `0x1801c9371`
- `gdiplus!GdipFlattenPath` at `0x1801c92e6`
- `gdiplus!GdipFlattenPath` at `0x1801c92e6`
- `gdiplus!GdipDeletePen` at `0x1801c945d`
- `gdiplus!GdipDeletePen` at `0x1801c945d`
- `gdiplus!GdipCreatePen1` at `0x1801c934b`
- `gdiplus!GdipCreatePen1` at `0x1801c934b`
- `gdiplus!GdipClonePath` at `0x1801c92c3`
- `gdiplus!GdipClonePath` at `0x1801c92c3`
- `gdiplus!GdipDeletePath` at `0x1801c9406`
- `gdiplus!GdipDeletePath` at `0x1801c942f`
- `gdiplus!GdipDeletePath` at `0x1801c947d`
- `gdiplus!GdipDeletePath` at `0x1801c9406`
- `gdiplus!GdipDeletePath` at `0x1801c942f`
- `gdiplus!GdipDeletePath` at `0x1801c947d`

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
0x1801c9260  mov     rax, rsp
0x1801c9263  mov     [rax+10h], rbx
0x1801c9267  mov     [rax+18h], rsi
0x1801c926b  mov     [rax+20h], rdi
0x1801c926f  push    rbp
0x1801c9270  mov     rbp, rsp
0x1801c9273  sub     rsp, 70h
0x1801c9277  movaps  xmmword ptr [rax-18h], xmm6
0x1801c927b  movaps  xmm6, xmm3
0x1801c927e  mov     rbx, r8
0x1801c9281  mov     rdi, rdx
0x1801c9284  mov     rsi, rcx
0x1801c9287  cmp     qword ptr [rcx+28h], 0
0x1801c928c  jz      loc_1801C9435
0x1801c9292  mov     [rbp+var_38], 0
0x1801c929a  mov     rdx, rbx
0x1801c929d  lea     rcx, [rbp+var_20]
0x1801c92a1  call    ??$?0U?$TAffine3x3@N@Math@@$0A@@GpMatrixHolder@Gfx@@QEAA@AEBU?$TAffine3x3@N@Math@@@Z; Gfx::GpMatrixHolder::GpMatrixHolder(Math::TAffine3x3<double> const &)
0x1801c92a6  cmp     [rbp+var_38], 0
0x1801c92ab  jz      short loc_1801C92BB
0x1801c92ad  xor     edx, edx
0x1801c92af  mov     ecx, 1E55E058h
0x1801c92b4  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1801c92ba  nop
0x1801c92bb  lea     rdx, [rbp+var_38]
0x1801c92bf  mov     rcx, [rsi+28h]
0x1801c92c3  call    cs:__imp_GdipClonePath
0x1801c92c9  mov     r9d, 25454CCh
0x1801c92cf  mov     ecx, eax
0x1801c92d1  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1801c92d6  movss   xmm2, cs:__real@3f800000
0x1801c92de  mov     rdx, [rbp+var_20]
0x1801c92e2  mov     rcx, [rbp+var_38]
0x1801c92e6  call    cs:__imp_GdipFlattenPath
0x1801c92ec  mov     r9d, 25454CDh
0x1801c92f2  mov     ecx, eax
0x1801c92f4  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1801c92f9  mov     rax, [rbp+arg_20]
0x1801c92fd  test    rax, rax
0x1801c9300  jz      loc_1801C93BD
0x1801c9306  movss   xmm1, dword ptr [rax]
0x1801c930a  cvtps2pd xmm1, xmm1
0x1801c930d  mov     r8, rbx
0x1801c9310  lea     rcx, [rbp+var_30]
0x1801c9314  call    ?ScaleRadius@GEL@@YA?AUVector@1@NAEBU?$TAffine3x3@N@Math@@@Z; GEL::ScaleRadius(double,Math::TAffine3x3<double> const &)
0x1801c9319  movsd   xmm0, [rbp+var_30]
0x1801c931e  maxsd   xmm0, [rbp+var_28]
0x1801c9323  addsd   xmm6, xmm0
0x1801c9327  movsd   xmm0, cs:__real@4014000000000000
0x1801c932f  maxsd   xmm0, xmm6
0x1801c9333  mov     [rbp+var_30], 0
0x1801c933b  cvtpd2ps xmm1, xmm0
0x1801c933f  lea     r9, [rbp+var_30]
0x1801c9343  xor     r8d, r8d
0x1801c9346  mov     ecx, 0FF00FFFFh
0x1801c934b  call    cs:__imp_GdipCreatePen1
0x1801c9351  mov     r9d, 248C08Bh
0x1801c9357  mov     ecx, eax
0x1801c9359  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1801c935e  movss   xmm3, cs:__real@3f800000
0x1801c9366  xor     r8d, r8d
0x1801c9369  mov     rdx, [rbp+var_30]
0x1801c936d  mov     rcx, [rbp+var_38]
0x1801c9371  call    cs:__imp_GdipWidenPath
0x1801c9377  mov     [rbp+var_40], 0
0x1801c937e  movsd   xmm2, qword ptr [rdi+8]
0x1801c9383  cvtpd2ps xmm2, xmm2
0x1801c9387  movsd   xmm1, qword ptr [rdi]
0x1801c938b  cvtpd2ps xmm1, xmm1
0x1801c938f  lea     rax, [rbp+var_40]
0x1801c9393  mov     [rsp+70h+var_50], rax
0x1801c9398  xor     r9d, r9d
0x1801c939b  mov     rcx, [rbp+var_38]
0x1801c939f  call    cs:__imp_GdipIsVisiblePathPoint
0x1801c93a5  test    eax, eax
0x1801c93a7  jnz     loc_1801C9452
0x1801c93ad  cmp     [rbp+var_40], eax
0x1801c93b0  jz      loc_1801C9452
0x1801c93b6  mov     bl, 1
0x1801c93b8  jmp     loc_1801C9454
0x1801c93bd  mov     [rbp+arg_0], 0
0x1801c93c4  movsd   xmm2, qword ptr [rdi+8]
0x1801c93c9  cvtpd2ps xmm2, xmm2
0x1801c93cd  movsd   xmm1, qword ptr [rdi]
0x1801c93d1  cvtpd2ps xmm1, xmm1
0x1801c93d5  lea     rax, [rbp+arg_0]
0x1801c93d9  mov     [rsp+70h+var_50], rax
0x1801c93de  xor     r9d, r9d
0x1801c93e1  mov     rcx, [rbp+var_38]
0x1801c93e5  call    cs:__imp_GdipIsVisiblePathPoint
0x1801c93eb  test    eax, eax
0x1801c93ed  jnz     short loc_1801C9410
0x1801c93ef  cmp     [rbp+arg_0], eax
0x1801c93f2  jz      short loc_1801C9410
0x1801c93f4  lea     rcx, [rbp+var_20]
0x1801c93f8  call    ?Empty@?$TGpHolder@VMatrix@Gdiplus@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGpHolder<Gdiplus::Matrix>::Empty(void)
0x1801c93fd  mov     rcx, [rbp+var_38]
0x1801c9401  test    rcx, rcx
0x1801c9404  jz      short loc_1801C940C
0x1801c9406  call    cs:__imp_GdipDeletePath
0x1801c940c  mov     al, 1
0x1801c940e  jmp     short loc_1801C9437
0x1801c9410  xorps   xmm0, xmm0
0x1801c9413  comisd  xmm0, xmm6
0x1801c9417  jb      loc_1801C9327
0x1801c941d  lea     rcx, [rbp+var_20]
0x1801c9421  call    ?Empty@?$TGpHolder@VMatrix@Gdiplus@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGpHolder<Gdiplus::Matrix>::Empty(void)
0x1801c9426  mov     rcx, [rbp+var_38]
0x1801c942a  test    rcx, rcx
0x1801c942d  jz      short loc_1801C9435
0x1801c942f  call    cs:__imp_GdipDeletePath
0x1801c9435  xor     al, al
0x1801c9437  lea     r11, [rsp+70h+var_s0]
0x1801c943c  mov     rbx, [r11+18h]
0x1801c9440  mov     rsi, [r11+20h]
0x1801c9444  mov     rdi, [r11+28h]
0x1801c9448  movaps  xmm6, [rsp+70h+var_10]
0x1801c944d  mov     rsp, r11
0x1801c9450  pop     rbp
0x1801c9451  retn
0x1801c9452  xor     bl, bl
0x1801c9454  mov     rcx, [rbp+var_30]
0x1801c9458  test    rcx, rcx
0x1801c945b  jz      short loc_1801C946B
0x1801c945d  call    cs:__imp_GdipDeletePen
0x1801c9463  mov     [rbp+var_30], 0
0x1801c946b  lea     rcx, [rbp+var_20]
0x1801c946f  call    ?Empty@?$TGpHolder@VMatrix@Gdiplus@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGpHolder<Gdiplus::Matrix>::Empty(void)
0x1801c9474  mov     rcx, [rbp+var_38]
0x1801c9478  test    rcx, rcx
0x1801c947b  jz      short loc_1801C9483
0x1801c947d  call    cs:__imp_GdipDeletePath
0x1801c9483  mov     al, bl
0x1801c9485  jmp     short loc_1801C9437
```
