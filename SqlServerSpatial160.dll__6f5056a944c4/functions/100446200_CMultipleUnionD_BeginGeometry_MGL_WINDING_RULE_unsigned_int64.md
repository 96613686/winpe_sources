# CMultipleUnionD::BeginGeometry(MGL_WINDING_RULE,unsigned __int64)

- ea: `0x100446200`
- end: `0x100446487`
- name: `?BeginGeometry@CMultipleUnionD@@UEAAJW4MGL_WINDING_RULE@@_K@Z`
- size: `647`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1004033b0`
- `0x100432b80`
- `0x100446200`

## import_xrefs

- `api-ms-win-crt-math-l1-1-0!_finite` at `0x1004463ad`
- `api-ms-win-crt-math-l1-1-0!_finite` at `0x1004463ad`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004462a3`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004462a3`

## string_xrefs

- `0x10044628d`: `sql\ntdbms\msql\sysclrtypes\spatial\libraries\dll\Allocator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMultipleUnionD::BeginGeometry(__int64 a1, unsigned int a2, __int64 a3)
{
  struct CGeometrySinkD *v6; // rsi
  void (__fastcall ***v7)(_QWORD, __int64); // rcx
  double *v8; // rdi
  CStructuredOutlineModule *v9; // rax
  __int64 result; // rax
  double v11; // xmm8_8
  __int64 v12; // rdi
  double v13; // xmm6_8
  __int64 v14; // rax
  __int128 v15; // [rsp+38h] [rbp-60h] BYREF
  __int128 v16; // [rsp+48h] [rbp-50h]
  int v17; // [rsp+A0h] [rbp+8h] BYREF
  CStructuredOutlineModule *v18; // [rsp+B8h] [rbp+20h]

  if ( !*(_QWORD *)(a1 + 96) || (v6 = (struct CGeometrySinkD *)(a1 + 72), *(_QWORD *)(a1 + 56) != a1 + 72) )
  {
    result = 2147549183LL;
LABEL_30:
    _mm_lfence();
    return result;
  }
  v7 = *(void (__fastcall ****)(_QWORD, __int64))(a1 + 64);
  if ( v7 )
    (**v7)(v7, 1);
  v8 = 0;
  *(_QWORD *)(a1 + 64) = 0;
  if ( !*(_BYTE *)(a1 + 104) || *(_BYTE *)(a1 + 106) )
  {
    *(_QWORD *)(a1 + 56) = v6;
LABEL_26:
    v14 = *(_QWORD *)(a1 + 112);
    if ( v14 )
      *(_QWORD *)(a1 + 88) = *(_QWORD *)(v14 + 8);
    result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**(_QWORD **)(a1 + 56) + 24LL))(
               *(_QWORD *)(a1 + 56),
               a2,
               a3);
    goto LABEL_30;
  }
  if ( g_SOSHost )
    v9 = (CStructuredOutlineModule *)(*(__int64 (__fastcall **)(_QWORD, __int64, const char *, __int64))(*g_SOSMemObj + 120LL))(
                                       g_SOSMemObj,
                                       1024,
                                       "sql\\ntdbms\\msql\\sysclrtypes\\spatial\\libraries\\dll\\Allocator.cpp",
                                       26);
  else
    v9 = (CStructuredOutlineModule *)malloc(0x400u);
  v18 = v9;
  if ( v9 )
    v8 = (double *)CStructuredOutlineModule::CStructuredOutlineModule(
                     v9,
                     v6,
                     *(const struct C2DMetadataResolver **)(a1 + 112),
                     0,
                     *(_BYTE *)(a1 + 120));
  *(_QWORD *)(a1 + 64) = v8;
  if ( !v8 )
    return 2147942414LL;
  *(_QWORD *)(a1 + 56) = v8 + 109;
  result = CWorkspaceTransform::SetWithScaleFactor(v8 + 1, a1 + 8);
  if ( (int)result < 0 )
    goto LABEL_30;
  v8[111] = fmin(v8[11], v8[12]);
  _mm_lfence();
  v11 = *(double *)(a1 + 48);
  v12 = *(_QWORD *)(a1 + 64);
  if ( *(double *)(a1 + 8) > *(double *)(a1 + 16) || *(double *)(a1 + 24) > *(double *)(a1 + 32) )
  {
    v15 = _xmm;
    v16 = _xmm;
  }
  else
  {
    v15 = *(_OWORD *)(a1 + 8);
    v16 = *(_OWORD *)(a1 + 24);
  }
  result = CWorkspaceTransform::SetWithScaleFactor(v12 + 8, &v15);
  _mm_lfence();
  if ( (int)result >= 0 )
  {
    v13 = fmax(*((double *)&v15 + 1) - *(double *)&v15, *((double *)&v16 + 1) - *(double *)&v16);
    if ( !_finite(v13) )
      v13 = DOUBLE_1_0;
    *(double *)(*(_QWORD *)(v12 + 104) + 496LL) = fmax(*(double *)(v12 + 40), *(double *)(v12 + 48))
                                                * fmax(v11, v13 * 3.0e-12);
    *(_QWORD *)(v12 + 16) = *(_QWORD *)(v12 + 104);
    _mm_lfence();
    v17 = 3;
    result = (*(__int64 (__fastcall **)(_QWORD, __int64, int *))(**(_QWORD **)(a1 + 64) + 8LL))(
               *(_QWORD *)(a1 + 64),
               1,
               &v17);
    if ( (int)result < 0 )
      goto LABEL_30;
    if ( *(_BYTE *)(a1 + 120) )
    {
      _mm_lfence();
      *(_QWORD *)(*(_QWORD *)(a1 + 64) + 1000LL) = *(_QWORD *)(*(_QWORD *)(a1 + 112) + 8LL);
    }
    goto LABEL_26;
  }
  return result;
}

```

## disassembly

```asm
0x100446200  mov     rax, rsp
0x100446203  push    rsi
0x100446204  push    rdi
0x100446205  push    r14
0x100446207  sub     rsp, 80h
0x10044620e  mov     qword ptr [rax-68h], 0FFFFFFFFFFFFFFFEh
0x100446216  mov     [rax+10h], rbx
0x10044621a  mov     [rax+18h], rbp
0x10044621e  movaps  xmmword ptr [rax-28h], xmm6
0x100446222  movaps  xmmword ptr [rax-38h], xmm8
0x100446227  mov     rbp, r8
0x10044622a  mov     r14d, edx
0x10044622d  mov     rbx, rcx
0x100446230  cmp     qword ptr [rcx+60h], 0
0x100446235  jz      loc_10044645D
0x10044623b  lea     rsi, [rcx+48h]
0x10044623f  cmp     [rcx+38h], rsi
0x100446243  jnz     loc_10044645D
0x100446249  mov     rcx, [rcx+40h]
0x10044624d  test    rcx, rcx
0x100446250  jz      short loc_10044625C
0x100446252  mov     rax, [rcx]
0x100446255  mov     edx, 1
0x10044625a  call    qword ptr [rax]
0x10044625c  xor     edi, edi
0x10044625e  mov     [rbx+40h], rdi
0x100446262  cmp     [rbx+68h], dil
0x100446266  jz      loc_100446436
0x10044626c  cmp     [rbx+6Ah], dil
0x100446270  jnz     loc_100446436
0x100446276  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, rdi; SOS_AutoHost g_SOSHost
0x10044627d  jz      short loc_10044629E
0x10044627f  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A; SOS_AutoMemObj g_SOSMemObj
0x100446286  mov     rax, [rcx]
0x100446289  lea     r9d, [rdi+1Ah]
0x10044628d  lea     r8, aSqlNtdbmsMsqlS; "sql\\ntdbms\\msql\\sysclrtypes\\spatial"...
0x100446294  mov     edx, 400h
0x100446299  call    qword ptr [rax+78h]
0x10044629c  jmp     short loc_1004462A9
0x10044629e  mov     ecx, 400h; Size
0x1004462a3  call    cs:__imp_malloc
0x1004462a9  mov     rcx, rax; this
0x1004462ac  mov     [rsp+98h+arg_18], rax
0x1004462b4  test    rax, rax
0x1004462b7  jz      short loc_1004462D3
0x1004462b9  movzx   eax, byte ptr [rbx+78h]
0x1004462bd  mov     [rsp+98h+var_78], al; bool
0x1004462c1  xor     r9d, r9d; bool
0x1004462c4  mov     r8, [rbx+70h]; struct C2DMetadataResolver *
0x1004462c8  mov     rdx, rsi; struct CGeometrySinkD *
0x1004462cb  call    ??0CStructuredOutlineModule@@QEAA@PEAVCGeometrySinkD@@PEBVC2DMetadataResolver@@_N2@Z; CStructuredOutlineModule::CStructuredOutlineModule(CGeometrySinkD *,C2DMetadataResolver const *,bool,bool)
0x1004462d0  mov     rdi, rax
0x1004462d3  mov     [rbx+40h], rdi
0x1004462d7  test    rdi, rdi
0x1004462da  jnz     short loc_1004462E6
0x1004462dc  mov     eax, 8007000Eh
0x1004462e1  jmp     loc_100446465
0x1004462e6  lea     rax, [rdi+368h]
0x1004462ed  mov     [rbx+38h], rax
0x1004462f1  lea     rcx, [rdi+8]
0x1004462f5  movsd   xmm2, cs:__real@3ff0000000000000
0x1004462fd  lea     rdx, [rbx+8]
0x100446301  call    ?SetWithScaleFactor@CWorkspaceTransform@@QEAAJAEBV?$CMglRect@N@@N@Z; CWorkspaceTransform::SetWithScaleFactor(CMglRect<double> const &,double)
0x100446306  test    eax, eax
0x100446308  js      loc_100446462
0x10044630e  movsd   xmm0, qword ptr [rdi+58h]
0x100446313  minsd   xmm0, qword ptr [rdi+60h]
0x100446318  movsd   qword ptr [rdi+378h], xmm0
0x100446320  lfence
0x100446323  movsd   xmm8, qword ptr [rbx+30h]
0x100446329  mov     rdi, [rbx+40h]
0x10044632d  movsd   xmm0, qword ptr [rbx+8]
0x100446332  comisd  xmm0, qword ptr [rbx+10h]
0x100446337  ja      short loc_100446359
0x100446339  movsd   xmm0, qword ptr [rbx+18h]
0x10044633e  comisd  xmm0, qword ptr [rbx+20h]
0x100446343  ja      short loc_100446359
0x100446345  movups  xmm0, xmmword ptr [rbx+8]
0x100446349  movups  [rsp+98h+var_60], xmm0
0x10044634e  movups  xmm1, xmmword ptr [rbx+18h]
0x100446352  movups  [rsp+98h+var_50], xmm1
0x100446357  jmp     short loc_10044636D
0x100446359  movaps  xmm0, cs:__xmm@3ff00000000000000000000000000000
0x100446360  movups  [rsp+98h+var_60], xmm0
0x100446365  movaps  xmm1, xmm0
0x100446368  movups  [rsp+98h+var_50], xmm0
0x10044636d  lea     rcx, [rdi+8]
0x100446371  movsd   xmm2, cs:__real@3ff0000000000000
0x100446379  lea     rdx, [rsp+98h+var_60]
0x10044637e  call    ?SetWithScaleFactor@CWorkspaceTransform@@QEAAJAEBV?$CMglRect@N@@N@Z; CWorkspaceTransform::SetWithScaleFactor(CMglRect<double> const &,double)
0x100446383  lfence
0x100446386  test    eax, eax
0x100446388  js      loc_100446465
0x10044638e  movsd   xmm6, qword ptr [rsp+98h+var_60+8]
0x100446394  subsd   xmm6, qword ptr [rsp+98h+var_60]
0x10044639a  movsd   xmm0, qword ptr [rsp+98h+var_50+8]
0x1004463a0  subsd   xmm0, qword ptr [rsp+98h+var_50]
0x1004463a6  maxsd   xmm6, xmm0
0x1004463aa  movaps  xmm0, xmm6; X
0x1004463ad  call    cs:__imp__finite
0x1004463b3  test    eax, eax
0x1004463b5  jnz     short loc_1004463BF
0x1004463b7  movsd   xmm6, cs:__real@3ff0000000000000
0x1004463bf  mulsd   xmm6, cs:__real@3d8a636641c4df1a
0x1004463c7  maxsd   xmm8, xmm6
0x1004463cc  movsd   xmm0, qword ptr [rdi+28h]
0x1004463d1  maxsd   xmm0, qword ptr [rdi+30h]
0x1004463d6  mulsd   xmm0, xmm8
0x1004463db  mov     rax, [rdi+68h]
0x1004463df  movsd   qword ptr [rax+1F0h], xmm0
0x1004463e7  mov     rax, [rdi+68h]
0x1004463eb  mov     [rdi+10h], rax
0x1004463ef  lfence
0x1004463f2  mov     [rsp+98h+arg_0], 3
0x1004463fd  mov     rcx, [rbx+40h]
0x100446401  mov     rax, [rcx]
0x100446404  lea     r8, [rsp+98h+arg_0]
0x10044640c  mov     edx, 1
0x100446411  call    qword ptr [rax+8]
0x100446414  test    eax, eax
0x100446416  js      short loc_100446462
0x100446418  cmp     byte ptr [rbx+78h], 0
0x10044641c  jz      short loc_10044643A
0x10044641e  lfence
0x100446421  mov     rax, [rbx+70h]
0x100446425  mov     rcx, [rbx+40h]
0x100446429  mov     rax, [rax+8]
0x10044642d  mov     [rcx+3E8h], rax
0x100446434  jmp     short loc_10044643A
0x100446436  mov     [rbx+38h], rsi
0x10044643a  mov     rax, [rbx+70h]
0x10044643e  test    rax, rax
0x100446441  jz      short loc_10044644B
0x100446443  mov     rax, [rax+8]
0x100446447  mov     [rbx+58h], rax
0x10044644b  mov     rcx, [rbx+38h]
0x10044644f  mov     rax, [rcx]
0x100446452  mov     r8, rbp
0x100446455  mov     edx, r14d
0x100446458  call    qword ptr [rax+18h]
0x10044645b  jmp     short loc_100446462
0x10044645d  mov     eax, 8000FFFFh
0x100446462  lfence
0x100446465  lea     r11, [rsp+98h+var_18]
0x10044646d  mov     rbx, [r11+28h]
0x100446471  mov     rbp, [r11+30h]
0x100446475  movaps  xmm6, [rsp+98h+var_28]
0x10044647a  movaps  xmm8, xmmword ptr [r11-20h]
0x10044647f  mov     rsp, r11
0x100446482  pop     r14
0x100446484  pop     rdi
0x100446485  pop     rsi
0x100446486  retn
```
