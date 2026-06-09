# Mso::SVG::ClipPathRenderer::ComputePath(Mso::SVG::StyleResolveChain const &,GEL::Rect const *)

- ea: `0x180102630`
- end: `0x1801028cf`
- name: `?ComputePath@ClipPathRenderer@SVG@Mso@@QEAA?AV?$TCntPtr@$$CBUIPath@GEL@@@3@AEBVStyleResolveChain@23@PEBURect@GEL@@@Z`
- size: `671`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180041c38`

## callees

- `0x18004f518`
- `0x180102630`
- `0x180103fb8`
- `0x180104044`
- `0x18013e010`
- `0x18013f738`
- `0x18013f760`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801028ba`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801028c8`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801028ba`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801028c8`
- `gfx!?Create@ITransformedPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBUIPath@2@AEBU?$TAffine3x3@N@Math@@@Z` at `0x1801027c5`
- `gfx!?Create@ITransformedPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBUIPath@2@AEBU?$TAffine3x3@N@Math@@@Z` at `0x1801027fd`
- `gfx!?Create@ITransformedPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBUIPath@2@AEBU?$TAffine3x3@N@Math@@@Z` at `0x1801027c5`
- `gfx!?Create@ITransformedPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBUIPath@2@AEBU?$TAffine3x3@N@Math@@@Z` at `0x1801027fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall Mso::SVG::ClipPathRenderer::ComputePath(__int64 a1, _QWORD *a2, __int64 a3, double *a4)
{
  _BYTE *v8; // rdi
  int v9; // r12d
  __m128i *p_si128; // rbx
  __int64 v11; // rax
  __int64 v12; // rbx
  __int64 v13; // rcx
  __int64 *v14; // rax
  __int64 v15; // rcx
  double v16; // xmm4_8
  double v17; // xmm2_8
  double v18; // xmm3_8
  __int64 *v19; // rax
  __int64 v20; // rdi
  __int64 v21; // rsi
  __int64 *v22; // rax
  __int64 v23; // rax
  __int64 v24; // r14
  _QWORD v26[2]; // [rsp+38h] [rbp-49h] BYREF
  _QWORD v27[3]; // [rsp+48h] [rbp-39h] BYREF
  double v28; // [rsp+60h] [rbp-21h] BYREF
  __int128 v29; // [rsp+68h] [rbp-19h]
  double v30; // [rsp+78h] [rbp-9h]
  double v31; // [rsp+80h] [rbp-1h]
  double v32; // [rsp+88h] [rbp+7h]
  __int64 v33; // [rsp+90h] [rbp+Fh]
  __m128i si128; // [rsp+98h] [rbp+17h] BYREF
  double v35; // [rsp+A8h] [rbp+27h]
  __int64 v36; // [rsp+E8h] [rbp+67h] BYREF

  v8 = *(_BYTE **)(a1 + 16);
  if ( !v8 )
  {
LABEL_31:
    CrashWithRecovery(0x1E3C3843u, 0);
    JUMPOUT(0x1801028CELL);
  }
  _castguard_slow_path_check_user_handled(*(_QWORD *)v8, 6992, 0);
  v9 = *((_DWORD *)v8 + 80);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v35 = sqrt_0(1.0);
  if ( v9 )
    p_si128 = &si128;
  else
    p_si128 = *(__m128i **)(a3 + 16);
  v11 = (*(__int64 (__fastcall **)(_BYTE *))(*(_QWORD *)v8 + 104LL))(v8);
  v27[0] = 0;
  v27[1] = v11;
  v27[2] = p_si128;
  Mso::SVG::PathCacher::GetCached(a1 + 88, &v36, v27);
  v12 = v36;
  if ( v36 )
    goto LABEL_10;
  v13 = *(_QWORD *)(a1 + 32);
  if ( !v13 )
  {
    CrashWithRecovery(0x1E3C3840u, 0);
    goto LABEL_31;
  }
  v14 = (__int64 *)(*(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD *, _QWORD))(*(_QWORD *)v13 + 24LL))(
                     v13,
                     v26,
                     v27,
                     0);
  v12 = *v14;
  *v14 = 0;
  v36 = v12;
  v15 = v26[0];
  if ( v26[0] )
  {
    v26[0] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
  }
  Mso::SVG::PathCacher::Cache(a1 + 88, v12, v27, 3);
LABEL_10:
  v33 = 0;
  if ( v9 == 1 )
  {
    v16 = a4[1];
    v17 = a4[3] - v16;
    v18 = *a4;
    v28 = a4[2] - *a4;
    v29 = 0;
    v30 = v17;
    v31 = v18 + 0.0;
    v32 = v16 + 0.0;
    if ( v8[64] )
      Math::operator*=<double,double,0>(&v28, a1 + 40);
    v19 = (__int64 *)GEL::ITransformedPath::Create(v26, v12, &v28);
    v20 = *v19;
    *v19 = 0;
    if ( v26[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v26[0] + 8LL))(v26[0]);
    v21 = v20;
LABEL_19:
    v23 = v20;
    v24 = v20;
    goto LABEL_23;
  }
  if ( v8[64] )
  {
    v22 = (__int64 *)GEL::ITransformedPath::Create(v26, v12, a1 + 40);
    v20 = *v22;
    v21 = *v22;
    *v22 = 0;
    if ( v26[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v26[0] + 8LL))(v26[0]);
    goto LABEL_19;
  }
  if ( v12 )
    (**(void (__fastcall ***)(__int64))v12)(v12);
  v20 = v12;
  v21 = v12;
  v23 = v12;
  v24 = v12;
LABEL_23:
  *a2 = v20;
  if ( v21 )
  {
    (**(void (__fastcall ***)(__int64))v20)(v20);
    v23 = v24;
  }
  if ( v23 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 8LL))(v20);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
  return a2;
}

```

## disassembly

```asm
0x180102630  mov     rax, rsp
0x180102633  mov     [rax+10h], rbx
0x180102637  mov     [rax+18h], rsi
0x18010263b  mov     [rax+20h], rdi
0x18010263f  push    rbp
0x180102640  push    r12
0x180102642  push    r13
0x180102644  push    r14
0x180102646  push    r15
0x180102648  lea     rbp, [rax-5Fh]
0x18010264c  sub     rsp, 0B0h
0x180102653  mov     r14, r9
0x180102656  mov     rbx, r8
0x180102659  mov     r15, rdx
0x18010265c  mov     rsi, rcx
0x18010265f  mov     rdi, [rcx+10h]
0x180102663  test    rdi, rdi
0x180102666  jz      loc_1801028C1
0x18010266c  xor     r8d, r8d
0x18010266f  mov     edx, 1B50h
0x180102674  mov     rcx, [rdi]
0x180102677  call    __castguard_slow_path_check_user_handled
0x18010267c  mov     r12d, [rdi+140h]
0x180102683  movdqa  xmm0, cs:__xmm@3ff00000000000003ff0000000000000
0x18010268b  movups  [rbp+57h+var_40], xmm0
0x18010268f  movsd   xmm0, cs:__real@3ff0000000000000; X
0x180102697  call    sqrt_0
0x18010269c  movsd   [rbp+57h+var_30], xmm0
0x1801026a1  test    r12d, r12d
0x1801026a4  jnz     short loc_1801026AC
0x1801026a6  mov     rbx, [rbx+10h]
0x1801026aa  jmp     short loc_1801026B0
0x1801026ac  lea     rbx, [rbp+57h+var_40]
0x1801026b0  mov     rax, [rdi]
0x1801026b3  mov     rcx, rdi
0x1801026b6  mov     rax, [rax+68h]
0x1801026ba  call    cs:__guard_dispatch_icall_fptr
0x1801026c0  mov     [rbp+57h+var_90], 0
0x1801026c8  mov     [rbp+57h+var_88], rax
0x1801026cc  mov     [rbp+57h+var_80], rbx
0x1801026d0  lea     r8, [rbp+57h+var_90]
0x1801026d4  lea     rdx, [rbp+57h+arg_0]
0x1801026d8  lea     rcx, [rsi+58h]
0x1801026dc  call    ?GetCached@PathCacher@SVG@Mso@@QEBA?AV?$TCntPtr@$$CBUIPath@GEL@@@3@AEBVStyleResolveChain@23@@Z; Mso::SVG::PathCacher::GetCached(Mso::SVG::StyleResolveChain const &)
0x1801026e1  mov     rbx, [rbp+57h+arg_0]
0x1801026e5  test    rbx, rbx
0x1801026e8  jnz     short loc_180102751
0x1801026ea  mov     rcx, [rsi+20h]
0x1801026ee  test    rcx, rcx
0x1801026f1  jz      loc_1801028B3
0x1801026f7  mov     rax, [rcx]
0x1801026fa  xor     r9d, r9d
0x1801026fd  lea     r8, [rbp+57h+var_90]
0x180102701  lea     rdx, [rbp+57h+var_A0]
0x180102705  mov     rax, [rax+18h]
0x180102709  call    cs:__guard_dispatch_icall_fptr
0x18010270f  mov     rbx, [rax]
0x180102712  mov     qword ptr [rax], 0
0x180102719  mov     [rbp+57h+arg_0], rbx
0x18010271d  mov     rcx, [rbp+57h+var_A0]
0x180102721  test    rcx, rcx
0x180102724  jz      short loc_18010273B
0x180102726  mov     [rbp+57h+var_A0], 0
0x18010272e  mov     rax, [rcx]
0x180102731  mov     rax, [rax+8]
0x180102735  call    cs:__guard_dispatch_icall_fptr
0x18010273b  mov     r9d, 3
0x180102741  lea     r8, [rbp+57h+var_90]
0x180102745  mov     rdx, rbx
0x180102748  lea     rcx, [rsi+58h]
0x18010274c  call    ?Cache@PathCacher@SVG@Mso@@QEAAXAEBUIPath@GEL@@AEBVStyleResolveChain@23@W4PathDependencyFlags@123@@Z; Mso::SVG::PathCacher::Cache(GEL::IPath const &,Mso::SVG::StyleResolveChain const &,Mso::SVG::PathCacher::PathDependencyFlags)
0x180102751  xor     r13d, r13d
0x180102754  mov     [rbp+57h+var_48], r13
0x180102758  cmp     r12d, 1
0x18010275c  jnz     loc_1801027EC
0x180102762  movsd   xmm4, qword ptr [r14+8]
0x180102768  movsd   xmm2, qword ptr [r14+18h]
0x18010276e  subsd   xmm2, xmm4
0x180102772  movsd   xmm3, qword ptr [r14]
0x180102777  movsd   xmm0, qword ptr [r14+10h]
0x18010277d  subsd   xmm0, xmm3
0x180102781  movsd   [rbp+57h+var_78], xmm0
0x180102786  xorps   xmm1, xmm1
0x180102789  movups  [rbp+57h+var_70], xmm1
0x18010278d  movsd   [rbp+57h+var_60], xmm2
0x180102792  xorps   xmm0, xmm0
0x180102795  addsd   xmm3, xmm0
0x180102799  movsd   [rbp+57h+var_58], xmm3
0x18010279e  addsd   xmm4, xmm0
0x1801027a2  movsd   [rbp+57h+var_50], xmm4
0x1801027a7  cmp     [rdi+40h], r13b
0x1801027ab  jz      short loc_1801027BA
0x1801027ad  lea     rdx, [rsi+28h]
0x1801027b1  lea     rcx, [rbp+57h+var_78]
0x1801027b5  call    ??$?XNN$0A@@Math@@YAAEAU?$TAffine3x3@N@0@AEAU10@AEBU10@@Z; Math::operator*=<double,double,0>(Math::TAffine3x3<double> &,Math::TAffine3x3<double> const &)
0x1801027ba  lea     r8, [rbp+57h+var_78]
0x1801027be  mov     rdx, rbx
0x1801027c1  lea     rcx, [rbp+57h+var_A0]
0x1801027c5  call    cs:__imp_?Create@ITransformedPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBUIPath@2@AEBU?$TAffine3x3@N@Math@@@Z; GEL::ITransformedPath::Create(GEL::IPath const &,Math::TAffine3x3<double> const &)
0x1801027cb  mov     rdi, [rax]
0x1801027ce  mov     [rax], r13
0x1801027d1  mov     rcx, [rbp+57h+var_A0]
0x1801027d5  test    rcx, rcx
0x1801027d8  jz      short loc_1801027E7
0x1801027da  mov     rax, [rcx]
0x1801027dd  mov     rax, [rax+8]
0x1801027e1  call    cs:__guard_dispatch_icall_fptr
0x1801027e7  mov     rsi, rdi
0x1801027ea  jmp     short loc_180102822
0x1801027ec  cmp     [rdi+40h], r13b
0x1801027f0  jz      short loc_18010282A
0x1801027f2  lea     r8, [rsi+28h]
0x1801027f6  mov     rdx, rbx
0x1801027f9  lea     rcx, [rbp+57h+var_A0]
0x1801027fd  call    cs:__imp_?Create@ITransformedPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBUIPath@2@AEBU?$TAffine3x3@N@Math@@@Z; GEL::ITransformedPath::Create(GEL::IPath const &,Math::TAffine3x3<double> const &)
0x180102803  mov     rdi, [rax]
0x180102806  mov     rsi, rdi
0x180102809  mov     [rax], r13
0x18010280c  mov     rcx, [rbp+57h+var_A0]
0x180102810  test    rcx, rcx
0x180102813  jz      short loc_180102822
0x180102815  mov     rax, [rcx]
0x180102818  mov     rax, [rax+8]
0x18010281c  call    cs:__guard_dispatch_icall_fptr
0x180102822  mov     rax, rdi
0x180102825  mov     r14, rdi
0x180102828  jmp     short loc_18010284A
0x18010282a  test    rbx, rbx
0x18010282d  jz      short loc_18010283E
0x18010282f  mov     rax, [rbx]
0x180102832  mov     rcx, rbx
0x180102835  mov     rax, [rax]
0x180102838  call    cs:__guard_dispatch_icall_fptr
0x18010283e  mov     rdi, rbx
0x180102841  mov     rsi, rbx
0x180102844  mov     rax, rbx
0x180102847  mov     r14, rbx
0x18010284a  mov     [r15], rdi
0x18010284d  test    rsi, rsi
0x180102850  jz      short loc_180102864
0x180102852  mov     rax, [rdi]
0x180102855  mov     rcx, rdi
0x180102858  mov     rax, [rax]
0x18010285b  call    cs:__guard_dispatch_icall_fptr
0x180102861  mov     rax, r14
0x180102864  test    rax, rax
0x180102867  jz      short loc_18010287A
0x180102869  mov     rax, [rdi]
0x18010286c  mov     rcx, rdi
0x18010286f  mov     rax, [rax+8]
0x180102873  call    cs:__guard_dispatch_icall_fptr
0x180102879  nop
0x18010287a  test    rbx, rbx
0x18010287d  jz      short loc_18010288F
0x18010287f  mov     rax, [rbx]
0x180102882  mov     rcx, rbx
0x180102885  mov     rax, [rax+8]
0x180102889  call    cs:__guard_dispatch_icall_fptr
0x18010288f  mov     rax, r15
0x180102892  lea     r11, [rsp+0D0h+var_20]
0x18010289a  mov     rbx, [r11+38h]
0x18010289e  mov     rsi, [r11+40h]
0x1801028a2  mov     rdi, [r11+48h]
0x1801028a6  mov     rsp, r11
0x1801028a9  pop     r15
0x1801028ab  pop     r14
0x1801028ad  pop     r13
0x1801028af  pop     r12
0x1801028b1  pop     rbp
0x1801028b2  retn
0x1801028b3  xor     edx, edx
0x1801028b5  mov     ecx, 1E3C3840h
0x1801028ba  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1801028c0  nop
0x1801028c1  xor     edx, edx
0x1801028c3  mov     ecx, 1E3C3843h
0x1801028c8  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
