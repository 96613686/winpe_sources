# Mso::SVG::SVGCreatingCommandSink::DrawLayer(Math::TRect<float> const &,ARC::IGeometry const *,ARC::AntiAliasMode,Math::TAffine3x3<float> const *,float,ARC::IBrush const *,ARC::ILayer &,ARC::ICommandList &,bool)

- ea: `0x180057550`
- end: `0x180057835`
- name: `?DrawLayer@SVGCreatingCommandSink@SVG@Mso@@UEAAXAEBU?$TRect@M@Math@@PEBUIGeometry@ARC@@W4AntiAliasMode@7@PEBU?$TAffine3x3@M@5@MPEBUIBrush@7@AEAUILayer@7@AEAUICommandList@7@_N@Z`
- size: `741`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18004f6e0`
- `0x180057550`
- `0x1800587e8`
- `0x18013d650`
- `0x18013f760`

## import_xrefs

- `gfx!?Create@IRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@@Z` at `0x18005768d`
- `gfx!?Create@IRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@@Z` at `0x18005768d`
- `gfx!??0PathBuilder@GEL@@QEAA@XZ` at `0x1800575d9`
- `gfx!??0PathBuilder@GEL@@QEAA@XZ` at `0x1800575d9`
- `gfx!??1PathBuilder@GEL@@QEAA@XZ` at `0x18005765a`
- `gfx!??1PathBuilder@GEL@@QEAA@XZ` at `0x18005765a`
- `gfx!?Finish@PathBuilder@GEL@@QEAA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@W4FillMode@Path@Graphics@Mso@@@Z` at `0x180057610`
- `gfx!?Finish@PathBuilder@GEL@@QEAA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@W4FillMode@Path@Graphics@Mso@@@Z` at `0x180057610`

## string_xrefs

- `0x18005781e`: `Unsupported command list that doesn't support streaming`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Mso::SVG::SVGCreatingCommandSink::DrawLayer(
        __int64 a1,
        __m64 *a2,
        __int64 a3,
        int a4,
        float *a5,
        char a6,
        char a7,
        double a8,
        __int64 a9)
{
  __int64 v11; // rsi
  _QWORD *v12; // rbx
  __m128d *v13; // rax
  __m64 *v14; // rcx
  __int64 v15; // rdx
  _QWORD **v16; // rax
  _QWORD *v17; // rbx
  __int64 v18; // rax
  _QWORD *v19; // rax
  _QWORD *v20; // rbx
  __int64 result; // rax
  _QWORD *v22; // [rsp+30h] [rbp-99h] BYREF
  __int64 v23; // [rsp+38h] [rbp-91h] BYREF
  float *v24; // [rsp+40h] [rbp-89h] BYREF
  double v25; // [rsp+50h] [rbp-79h] BYREF
  double v26; // [rsp+58h] [rbp-71h]
  double v27; // [rsp+60h] [rbp-69h]
  double v28; // [rsp+68h] [rbp-61h] BYREF
  double v29; // [rsp+70h] [rbp-59h]
  double v30; // [rsp+78h] [rbp-51h]
  int *v31; // [rsp+80h] [rbp-49h]
  float **v32; // [rsp+88h] [rbp-41h]
  char *v33; // [rsp+90h] [rbp-39h]
  char *v34; // [rsp+98h] [rbp-31h]
  unsigned int v35; // [rsp+A8h] [rbp-21h]
  _QWORD v36[2]; // [rsp+B0h] [rbp-19h] BYREF
  int v37; // [rsp+118h] [rbp+4Fh] BYREF

  v37 = a4;
  v23 = a3;
  v24 = a5;
  v11 = a9;
  if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a9 + 72LL))(a9) )
    OExceptionLog::ThrowTag(37884096, 55, L"Unsupported command list that doesn't support streaming");
  v22 = 0;
  if ( v23 )
  {
    v25 = COERCE_DOUBLE(&Mso::SVG::SVGGeometrySink::`vftable');
    v26 = 0.0;
    v27 = 0.0;
    GEL::PathBuilder::PathBuilder((GEL::PathBuilder *)&v28);
    v35 = 0;
    (*(void (__fastcall **)(__int64, double *, float *))(*(_QWORD *)v23 + 56LL))(v23, &v25, v24);
    GEL::PathBuilder::Finish(&v28, v36, v35);
    v12 = (_QWORD *)v36[0];
    v36[0] = 0;
    v22 = v12;
    GEL::PathBuilder::~PathBuilder((GEL::PathBuilder *)&v28);
  }
  else
  {
    v13 = (__m128d *)&v25;
    v14 = a2;
    v15 = 2;
    do
    {
      *v13 = _mm_cvtps_pd((__m64)v14->m64_u64);
      ++v14;
      ++v13;
      --v15;
    }
    while ( v15 );
    v16 = (_QWORD **)GEL::IRectanglePath::Create(v36, &v25);
    v17 = *v16;
    *v16 = 0;
    if ( v22 )
      (*(void (__fastcall **)(_QWORD *))(*v22 + 8LL))(v22);
    v22 = v17;
    if ( v36[0] )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v36[0] + 8LL))(v36[0]);
      v17 = v22;
    }
    if ( v24 )
    {
      v18 = *v17;
      v25 = *v24;
      v26 = v24[1];
      v27 = v24[2];
      v28 = v24[3];
      v29 = v24[4];
      v30 = v24[5];
      v19 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD *, _QWORD *, double *))(v18 + 128))(v17, v36, &v25);
      v20 = (_QWORD *)*v19;
      *v19 = 0;
      if ( v22 )
        (*(void (__fastcall **)(_QWORD *))(*v22 + 8LL))(v22);
      v22 = v20;
      if ( v36[0] )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v36[0] + 8LL))(v36[0]);
    }
  }
  v25 = *(double *)&a1;
  v26 = *(double *)&v11;
  v27 = COERCE_DOUBLE(&v22);
  v28 = a8;
  v29 = *(double *)&a2;
  v30 = COERCE_DOUBLE(&v23);
  v31 = &v37;
  v32 = &v24;
  v33 = &a6;
  v34 = &a7;
  v36[0] = off_180149CB8;
  v36[1] = &v25;
  result = Mso::SVG::SVGCreatingCommandSink::OnCurrentContainer(a1, v36);
  if ( v22 )
    return (*(__int64 (__fastcall **)(_QWORD *))(*v22 + 8LL))(v22);
  return result;
}

```

## disassembly

```asm
0x180057550  mov     [rsp-8+arg_18], r9d
0x180057555  push    rbp
0x180057556  push    rbx
0x180057557  push    rsi
0x180057558  push    rdi
0x180057559  push    r14
0x18005755b  lea     rbp, [rsp-7]
0x180057560  sub     rsp, 0D0h
0x180057567  mov     rax, cs:__security_cookie
0x18005756e  xor     rax, rsp
0x180057571  mov     [rbp+27h+var_30], rax
0x180057575  mov     rdi, rdx
0x180057578  mov     r14, rcx
0x18005757b  mov     [rsp+0F0h+var_B8], r8
0x180057580  mov     rax, [rbp+27h+arg_20]
0x180057584  mov     [rsp+0F0h+var_B0], rax
0x180057589  mov     rsi, [rbp+27h+arg_40]
0x18005758d  mov     rax, [rsi]
0x180057590  mov     rcx, rsi
0x180057593  mov     rax, [rax+48h]
0x180057597  call    cs:__guard_dispatch_icall_fptr
0x18005759d  test    al, al
0x18005759f  jz      loc_18005781E
0x1800575a5  mov     [rsp+0F0h+var_C0], 0
0x1800575ae  cmp     [rsp+0F0h+var_B8], 0
0x1800575b4  jz      loc_180057665
0x1800575ba  lea     rax, ??_7SVGGeometrySink@SVG@Mso@@6B@; const Mso::SVG::SVGGeometrySink::`vftable'
0x1800575c1  mov     [rbp+27h+var_A0], rax
0x1800575c5  mov     [rbp+27h+var_98], 0
0x1800575cd  mov     [rbp+27h+var_90], 0
0x1800575d5  lea     rcx, [rbp+27h+var_88]
0x1800575d9  call    cs:__imp_??0PathBuilder@GEL@@QEAA@XZ; GEL::PathBuilder::PathBuilder(void)
0x1800575df  mov     [rbp+27h+var_48], 0
0x1800575e6  mov     rcx, [rsp+0F0h+var_B8]
0x1800575eb  mov     rax, [rcx]
0x1800575ee  xorps   xmm3, xmm3
0x1800575f1  mov     r8, [rsp+0F0h+var_B0]
0x1800575f6  lea     rdx, [rbp+27h+var_A0]
0x1800575fa  mov     rax, [rax+38h]
0x1800575fe  call    cs:__guard_dispatch_icall_fptr
0x180057604  mov     r8d, [rbp+27h+var_48]
0x180057608  lea     rdx, [rbp+27h+var_40]
0x18005760c  lea     rcx, [rbp+27h+var_88]
0x180057610  call    cs:__imp_?Finish@PathBuilder@GEL@@QEAA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@W4FillMode@Path@Graphics@Mso@@@Z; GEL::PathBuilder::Finish(Mso::Graphics::Path::FillMode)
0x180057616  mov     rbx, [rbp+27h+var_40]
0x18005761a  xor     ecx, ecx
0x18005761c  mov     [rbp+27h+var_40], rcx
0x180057620  mov     rdx, [rsp+0F0h+var_C0]
0x180057625  test    rdx, rdx
0x180057628  jz      short loc_18005763E
0x18005762a  mov     rax, [rdx]
0x18005762d  mov     rcx, rdx
0x180057630  mov     rax, [rax+8]
0x180057634  call    cs:__guard_dispatch_icall_fptr
0x18005763a  mov     rcx, [rbp+27h+var_40]
0x18005763e  mov     [rsp+0F0h+var_C0], rbx
0x180057643  test    rcx, rcx
0x180057646  jz      short loc_180057656
0x180057648  mov     rax, [rcx]
0x18005764b  mov     rax, [rax+8]
0x18005764f  call    cs:__guard_dispatch_icall_fptr
0x180057655  nop
0x180057656  lea     rcx, [rbp+27h+var_88]
0x18005765a  call    cs:__imp_??1PathBuilder@GEL@@QEAA@XZ; GEL::PathBuilder::~PathBuilder(void)
0x180057660  jmp     loc_180057786
0x180057665  lea     rax, [rbp+27h+var_A0]
0x180057669  mov     rcx, rdi
0x18005766c  mov     edx, 2
0x180057671  cvtps2pd xmm0, qword ptr [rcx]
0x180057674  movups  xmmword ptr [rax], xmm0
0x180057677  lea     rcx, [rcx+8]
0x18005767b  lea     rax, [rax+10h]
0x18005767f  sub     rdx, 1
0x180057683  jnz     short loc_180057671
0x180057685  lea     rdx, [rbp+27h+var_A0]
0x180057689  lea     rcx, [rbp+27h+var_40]
0x18005768d  call    cs:__imp_?Create@IRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@@Z; GEL::IRectanglePath::Create(Math::TRect<double> const &)
0x180057693  mov     rbx, [rax]
0x180057696  mov     qword ptr [rax], 0
0x18005769d  mov     rcx, [rsp+0F0h+var_C0]
0x1800576a2  test    rcx, rcx
0x1800576a5  jz      short loc_1800576B4
0x1800576a7  mov     rax, [rcx]
0x1800576aa  mov     rax, [rax+8]
0x1800576ae  call    cs:__guard_dispatch_icall_fptr
0x1800576b4  mov     [rsp+0F0h+var_C0], rbx
0x1800576b9  mov     rcx, [rbp+27h+var_40]
0x1800576bd  test    rcx, rcx
0x1800576c0  jz      short loc_1800576D4
0x1800576c2  mov     rax, [rcx]
0x1800576c5  mov     rax, [rax+8]
0x1800576c9  call    cs:__guard_dispatch_icall_fptr
0x1800576cf  mov     rbx, [rsp+0F0h+var_C0]
0x1800576d4  mov     rcx, [rsp+0F0h+var_B0]
0x1800576d9  test    rcx, rcx
0x1800576dc  jz      loc_180057786
0x1800576e2  mov     rax, [rbx]
0x1800576e5  movss   xmm0, dword ptr [rcx]
0x1800576e9  cvtps2pd xmm0, xmm0
0x1800576ec  movsd   [rbp+27h+var_A0], xmm0
0x1800576f1  movss   xmm1, dword ptr [rcx+4]
0x1800576f6  cvtps2pd xmm1, xmm1
0x1800576f9  movsd   [rbp+27h+var_98], xmm1
0x1800576fe  movss   xmm0, dword ptr [rcx+8]
0x180057703  cvtps2pd xmm0, xmm0
0x180057706  movsd   [rbp+27h+var_90], xmm0
0x18005770b  movss   xmm1, dword ptr [rcx+0Ch]
0x180057710  cvtps2pd xmm1, xmm1
0x180057713  movsd   [rbp+27h+var_88], xmm1
0x180057718  movss   xmm0, dword ptr [rcx+10h]
0x18005771d  cvtps2pd xmm0, xmm0
0x180057720  movsd   [rbp+27h+var_80], xmm0
0x180057725  movss   xmm1, dword ptr [rcx+14h]
0x18005772a  cvtps2pd xmm1, xmm1
0x18005772d  movsd   [rbp+27h+var_78], xmm1
0x180057732  lea     r8, [rbp+27h+var_A0]
0x180057736  lea     rdx, [rbp+27h+var_40]
0x18005773a  mov     rcx, rbx
0x18005773d  mov     rax, [rax+80h]
0x180057744  call    cs:__guard_dispatch_icall_fptr
0x18005774a  mov     rbx, [rax]
0x18005774d  mov     qword ptr [rax], 0
0x180057754  mov     rcx, [rsp+0F0h+var_C0]
0x180057759  test    rcx, rcx
0x18005775c  jz      short loc_18005776B
0x18005775e  mov     rax, [rcx]
0x180057761  mov     rax, [rax+8]
0x180057765  call    cs:__guard_dispatch_icall_fptr
0x18005776b  mov     [rsp+0F0h+var_C0], rbx
0x180057770  mov     rcx, [rbp+27h+var_40]
0x180057774  test    rcx, rcx
0x180057777  jz      short loc_180057786
0x180057779  mov     rax, [rcx]
0x18005777c  mov     rax, [rax+8]
0x180057780  call    cs:__guard_dispatch_icall_fptr
0x180057786  mov     [rbp+27h+var_A0], r14
0x18005778a  mov     [rbp+27h+var_98], rsi
0x18005778e  lea     rax, [rsp+0F0h+var_C0]
0x180057793  mov     [rbp+27h+var_90], rax
0x180057797  mov     rax, [rbp+27h+arg_38]
0x18005779b  mov     [rbp+27h+var_88], rax
0x18005779f  mov     [rbp+27h+var_80], rdi
0x1800577a3  lea     rax, [rsp+0F0h+var_B8]
0x1800577a8  mov     [rbp+27h+var_78], rax
0x1800577ac  lea     rax, [rbp+27h+arg_18]
0x1800577b0  mov     [rbp+27h+var_70], rax
0x1800577b4  lea     rax, [rsp+0F0h+var_B0]
0x1800577b9  mov     [rbp+27h+var_68], rax
0x1800577bd  lea     rax, [rbp+27h+arg_28]
0x1800577c1  mov     [rbp+27h+var_60], rax
0x1800577c5  lea     rax, [rbp+27h+arg_30]
0x1800577c9  mov     [rbp+27h+var_58], rax
0x1800577cd  lea     rax, off_180149CB8
0x1800577d4  mov     [rbp+27h+var_40], rax
0x1800577d8  lea     rax, [rbp+27h+var_A0]
0x1800577dc  mov     [rbp+27h+var_38], rax
0x1800577e0  lea     rdx, [rbp+27h+var_40]
0x1800577e4  mov     rcx, r14
0x1800577e7  call    ?OnCurrentContainer@SVGCreatingCommandSink@SVG@Mso@@AEAAXAEBV?$FunctorRefThrow@$$A6AXAEAUISVGContainer@SVG@Mso@@@Z@3@@Z; Mso::SVG::SVGCreatingCommandSink::OnCurrentContainer(Mso::FunctorRefThrow<void (Mso::SVG::ISVGContainer &)> const &)
0x1800577ec  nop
0x1800577ed  mov     rcx, [rsp+0F0h+var_C0]
0x1800577f2  test    rcx, rcx
0x1800577f5  jz      short loc_180057804
0x1800577f7  mov     rax, [rcx]
0x1800577fa  mov     rax, [rax+8]
0x1800577fe  call    cs:__guard_dispatch_icall_fptr
0x180057804  mov     rcx, [rbp+27h+var_30]
0x180057808  xor     rcx, rsp; StackCookie
0x18005780b  call    __security_check_cookie
0x180057810  add     rsp, 0D0h
0x180057817  pop     r14
0x180057819  pop     rdi
0x18005781a  pop     rsi
0x18005781b  pop     rbx
0x18005781c  pop     rbp
0x18005781d  retn
0x18005781e  lea     r8, aUnsupportedCom_0; "Unsupported command list that doesn't s"...
0x180057825  mov     edx, 37h ; '7'
0x18005782a  mov     ecx, 24210C0h
0x18005782f  call    ?ThrowTag@OExceptionLog@@YAXKW4exceptionType@et@@PEB_WW4Category@Logging@Mso@@W4Severity@56@@Z; OExceptionLog::ThrowTag(ulong,et::exceptionType,wchar_t const *,Mso::Logging::Category,Mso::Logging::Severity)
```
