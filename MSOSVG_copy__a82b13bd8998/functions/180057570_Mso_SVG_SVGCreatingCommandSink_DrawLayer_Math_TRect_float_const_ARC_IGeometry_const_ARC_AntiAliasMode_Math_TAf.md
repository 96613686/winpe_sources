# Mso::SVG::SVGCreatingCommandSink::DrawLayer(Math::TRect<float> const &,ARC::IGeometry const *,ARC::AntiAliasMode,Math::TAffine3x3<float> const *,float,ARC::IBrush const *,ARC::ILayer &,ARC::ICommandList &,bool)

- ea: `0x180057570`
- end: `0x180057855`
- name: `?DrawLayer@SVGCreatingCommandSink@SVG@Mso@@UEAAXAEBU?$TRect@M@Math@@PEBUIGeometry@ARC@@W4AntiAliasMode@7@PEBU?$TAffine3x3@M@5@MPEBUIBrush@7@AEAUILayer@7@AEAUICommandList@7@_N@Z`
- size: `741`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18004f700`
- `0x180057570`
- `0x180058808`
- `0x18013d700`
- `0x18013f810`

## import_xrefs

- `gfx!?Create@IRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@@Z` at `0x1800576ad`
- `gfx!?Create@IRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@@Z` at `0x1800576ad`
- `gfx!??0PathBuilder@GEL@@QEAA@XZ` at `0x1800575f9`
- `gfx!??0PathBuilder@GEL@@QEAA@XZ` at `0x1800575f9`
- `gfx!??1PathBuilder@GEL@@QEAA@XZ` at `0x18005767a`
- `gfx!??1PathBuilder@GEL@@QEAA@XZ` at `0x18005767a`
- `gfx!?Finish@PathBuilder@GEL@@QEAA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@W4FillMode@Path@Graphics@Mso@@@Z` at `0x180057630`
- `gfx!?Finish@PathBuilder@GEL@@QEAA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@W4FillMode@Path@Graphics@Mso@@@Z` at `0x180057630`

## string_xrefs

- `0x18005783e`: `Unsupported command list that doesn't support streaming`

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
0x180057570  mov     [rsp-8+arg_18], r9d
0x180057575  push    rbp
0x180057576  push    rbx
0x180057577  push    rsi
0x180057578  push    rdi
0x180057579  push    r14
0x18005757b  lea     rbp, [rsp-7]
0x180057580  sub     rsp, 0D0h
0x180057587  mov     rax, cs:__security_cookie
0x18005758e  xor     rax, rsp
0x180057591  mov     [rbp+27h+var_30], rax
0x180057595  mov     rdi, rdx
0x180057598  mov     r14, rcx
0x18005759b  mov     [rsp+0F0h+var_B8], r8
0x1800575a0  mov     rax, [rbp+27h+arg_20]
0x1800575a4  mov     [rsp+0F0h+var_B0], rax
0x1800575a9  mov     rsi, [rbp+27h+arg_40]
0x1800575ad  mov     rax, [rsi]
0x1800575b0  mov     rcx, rsi
0x1800575b3  mov     rax, [rax+48h]
0x1800575b7  call    cs:__guard_dispatch_icall_fptr
0x1800575bd  test    al, al
0x1800575bf  jz      loc_18005783E
0x1800575c5  mov     [rsp+0F0h+var_C0], 0
0x1800575ce  cmp     [rsp+0F0h+var_B8], 0
0x1800575d4  jz      loc_180057685
0x1800575da  lea     rax, ??_7SVGGeometrySink@SVG@Mso@@6B@; const Mso::SVG::SVGGeometrySink::`vftable'
0x1800575e1  mov     [rbp+27h+var_A0], rax
0x1800575e5  mov     [rbp+27h+var_98], 0
0x1800575ed  mov     [rbp+27h+var_90], 0
0x1800575f5  lea     rcx, [rbp+27h+var_88]
0x1800575f9  call    cs:__imp_??0PathBuilder@GEL@@QEAA@XZ; GEL::PathBuilder::PathBuilder(void)
0x1800575ff  mov     [rbp+27h+var_48], 0
0x180057606  mov     rcx, [rsp+0F0h+var_B8]
0x18005760b  mov     rax, [rcx]
0x18005760e  xorps   xmm3, xmm3
0x180057611  mov     r8, [rsp+0F0h+var_B0]
0x180057616  lea     rdx, [rbp+27h+var_A0]
0x18005761a  mov     rax, [rax+38h]
0x18005761e  call    cs:__guard_dispatch_icall_fptr
0x180057624  mov     r8d, [rbp+27h+var_48]
0x180057628  lea     rdx, [rbp+27h+var_40]
0x18005762c  lea     rcx, [rbp+27h+var_88]
0x180057630  call    cs:__imp_?Finish@PathBuilder@GEL@@QEAA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@W4FillMode@Path@Graphics@Mso@@@Z; GEL::PathBuilder::Finish(Mso::Graphics::Path::FillMode)
0x180057636  mov     rbx, [rbp+27h+var_40]
0x18005763a  xor     ecx, ecx
0x18005763c  mov     [rbp+27h+var_40], rcx
0x180057640  mov     rdx, [rsp+0F0h+var_C0]
0x180057645  test    rdx, rdx
0x180057648  jz      short loc_18005765E
0x18005764a  mov     rax, [rdx]
0x18005764d  mov     rcx, rdx
0x180057650  mov     rax, [rax+8]
0x180057654  call    cs:__guard_dispatch_icall_fptr
0x18005765a  mov     rcx, [rbp+27h+var_40]
0x18005765e  mov     [rsp+0F0h+var_C0], rbx
0x180057663  test    rcx, rcx
0x180057666  jz      short loc_180057676
0x180057668  mov     rax, [rcx]
0x18005766b  mov     rax, [rax+8]
0x18005766f  call    cs:__guard_dispatch_icall_fptr
0x180057675  nop
0x180057676  lea     rcx, [rbp+27h+var_88]
0x18005767a  call    cs:__imp_??1PathBuilder@GEL@@QEAA@XZ; GEL::PathBuilder::~PathBuilder(void)
0x180057680  jmp     loc_1800577A6
0x180057685  lea     rax, [rbp+27h+var_A0]
0x180057689  mov     rcx, rdi
0x18005768c  mov     edx, 2
0x180057691  cvtps2pd xmm0, qword ptr [rcx]
0x180057694  movups  xmmword ptr [rax], xmm0
0x180057697  lea     rcx, [rcx+8]
0x18005769b  lea     rax, [rax+10h]
0x18005769f  sub     rdx, 1
0x1800576a3  jnz     short loc_180057691
0x1800576a5  lea     rdx, [rbp+27h+var_A0]
0x1800576a9  lea     rcx, [rbp+27h+var_40]
0x1800576ad  call    cs:__imp_?Create@IRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@@Z; GEL::IRectanglePath::Create(Math::TRect<double> const &)
0x1800576b3  mov     rbx, [rax]
0x1800576b6  mov     qword ptr [rax], 0
0x1800576bd  mov     rcx, [rsp+0F0h+var_C0]
0x1800576c2  test    rcx, rcx
0x1800576c5  jz      short loc_1800576D4
0x1800576c7  mov     rax, [rcx]
0x1800576ca  mov     rax, [rax+8]
0x1800576ce  call    cs:__guard_dispatch_icall_fptr
0x1800576d4  mov     [rsp+0F0h+var_C0], rbx
0x1800576d9  mov     rcx, [rbp+27h+var_40]
0x1800576dd  test    rcx, rcx
0x1800576e0  jz      short loc_1800576F4
0x1800576e2  mov     rax, [rcx]
0x1800576e5  mov     rax, [rax+8]
0x1800576e9  call    cs:__guard_dispatch_icall_fptr
0x1800576ef  mov     rbx, [rsp+0F0h+var_C0]
0x1800576f4  mov     rcx, [rsp+0F0h+var_B0]
0x1800576f9  test    rcx, rcx
0x1800576fc  jz      loc_1800577A6
0x180057702  mov     rax, [rbx]
0x180057705  movss   xmm0, dword ptr [rcx]
0x180057709  cvtps2pd xmm0, xmm0
0x18005770c  movsd   [rbp+27h+var_A0], xmm0
0x180057711  movss   xmm1, dword ptr [rcx+4]
0x180057716  cvtps2pd xmm1, xmm1
0x180057719  movsd   [rbp+27h+var_98], xmm1
0x18005771e  movss   xmm0, dword ptr [rcx+8]
0x180057723  cvtps2pd xmm0, xmm0
0x180057726  movsd   [rbp+27h+var_90], xmm0
0x18005772b  movss   xmm1, dword ptr [rcx+0Ch]
0x180057730  cvtps2pd xmm1, xmm1
0x180057733  movsd   [rbp+27h+var_88], xmm1
0x180057738  movss   xmm0, dword ptr [rcx+10h]
0x18005773d  cvtps2pd xmm0, xmm0
0x180057740  movsd   [rbp+27h+var_80], xmm0
0x180057745  movss   xmm1, dword ptr [rcx+14h]
0x18005774a  cvtps2pd xmm1, xmm1
0x18005774d  movsd   [rbp+27h+var_78], xmm1
0x180057752  lea     r8, [rbp+27h+var_A0]
0x180057756  lea     rdx, [rbp+27h+var_40]
0x18005775a  mov     rcx, rbx
0x18005775d  mov     rax, [rax+80h]
0x180057764  call    cs:__guard_dispatch_icall_fptr
0x18005776a  mov     rbx, [rax]
0x18005776d  mov     qword ptr [rax], 0
0x180057774  mov     rcx, [rsp+0F0h+var_C0]
0x180057779  test    rcx, rcx
0x18005777c  jz      short loc_18005778B
0x18005777e  mov     rax, [rcx]
0x180057781  mov     rax, [rax+8]
0x180057785  call    cs:__guard_dispatch_icall_fptr
0x18005778b  mov     [rsp+0F0h+var_C0], rbx
0x180057790  mov     rcx, [rbp+27h+var_40]
0x180057794  test    rcx, rcx
0x180057797  jz      short loc_1800577A6
0x180057799  mov     rax, [rcx]
0x18005779c  mov     rax, [rax+8]
0x1800577a0  call    cs:__guard_dispatch_icall_fptr
0x1800577a6  mov     [rbp+27h+var_A0], r14
0x1800577aa  mov     [rbp+27h+var_98], rsi
0x1800577ae  lea     rax, [rsp+0F0h+var_C0]
0x1800577b3  mov     [rbp+27h+var_90], rax
0x1800577b7  mov     rax, [rbp+27h+arg_38]
0x1800577bb  mov     [rbp+27h+var_88], rax
0x1800577bf  mov     [rbp+27h+var_80], rdi
0x1800577c3  lea     rax, [rsp+0F0h+var_B8]
0x1800577c8  mov     [rbp+27h+var_78], rax
0x1800577cc  lea     rax, [rbp+27h+arg_18]
0x1800577d0  mov     [rbp+27h+var_70], rax
0x1800577d4  lea     rax, [rsp+0F0h+var_B0]
0x1800577d9  mov     [rbp+27h+var_68], rax
0x1800577dd  lea     rax, [rbp+27h+arg_28]
0x1800577e1  mov     [rbp+27h+var_60], rax
0x1800577e5  lea     rax, [rbp+27h+arg_30]
0x1800577e9  mov     [rbp+27h+var_58], rax
0x1800577ed  lea     rax, off_180149CB8
0x1800577f4  mov     [rbp+27h+var_40], rax
0x1800577f8  lea     rax, [rbp+27h+var_A0]
0x1800577fc  mov     [rbp+27h+var_38], rax
0x180057800  lea     rdx, [rbp+27h+var_40]
0x180057804  mov     rcx, r14
0x180057807  call    ?OnCurrentContainer@SVGCreatingCommandSink@SVG@Mso@@AEAAXAEBV?$FunctorRefThrow@$$A6AXAEAUISVGContainer@SVG@Mso@@@Z@3@@Z; Mso::SVG::SVGCreatingCommandSink::OnCurrentContainer(Mso::FunctorRefThrow<void (Mso::SVG::ISVGContainer &)> const &)
0x18005780c  nop
0x18005780d  mov     rcx, [rsp+0F0h+var_C0]
0x180057812  test    rcx, rcx
0x180057815  jz      short loc_180057824
0x180057817  mov     rax, [rcx]
0x18005781a  mov     rax, [rax+8]
0x18005781e  call    cs:__guard_dispatch_icall_fptr
0x180057824  mov     rcx, [rbp+27h+var_30]
0x180057828  xor     rcx, rsp; StackCookie
0x18005782b  call    __security_check_cookie
0x180057830  add     rsp, 0D0h
0x180057837  pop     r14
0x180057839  pop     rdi
0x18005783a  pop     rsi
0x18005783b  pop     rbx
0x18005783c  pop     rbp
0x18005783d  retn
0x18005783e  lea     r8, aUnsupportedCom_0; "Unsupported command list that doesn't s"...
0x180057845  mov     edx, 37h ; '7'
0x18005784a  mov     ecx, 24210C0h
0x18005784f  call    ?ThrowTag@OExceptionLog@@YAXKW4exceptionType@et@@PEB_WW4Category@Logging@Mso@@W4Severity@56@@Z; OExceptionLog::ThrowTag(ulong,et::exceptionType,wchar_t const *,Mso::Logging::Category,Mso::Logging::Severity)
```
