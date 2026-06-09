# Mso::SVG::FeMorphologyRenderer::ApplyUnaryFilter(GEL::IEffect const &,Mso::SVG::StyleResolveChain const &,GEL::Rect const &,Mso::SVG::PrimitiveUnitResolver const &,GEL::IColorResolver const *)

- ea: `0x1800fb4c0`
- end: `0x1800fb5f9`
- name: `?ApplyUnaryFilter@FeMorphologyRenderer@SVG@Mso@@UEBA?AV?$TCntPtr@$$CBUIEffect@GEL@@@Ofc@@AEBUIEffect@GEL@@AEBVStyleResolveChain@23@AEBURect@7@AEBVPrimitiveUnitResolver@23@PEBUIColorResolver@7@@Z`
- size: `313`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64, __int64, int, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800fb4c0`
- `0x18013e0c0`
- `0x18013f810`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fb5f2`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fb5f2`
- `api-ms-win-crt-math-l1-1-0!round` at `0x1800fb56c`
- `api-ms-win-crt-math-l1-1-0!round` at `0x1800fb578`
- `api-ms-win-crt-math-l1-1-0!round` at `0x1800fb56c`
- `api-ms-win-crt-math-l1-1-0!round` at `0x1800fb578`
- `gfx!?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ` at `0x1800fb53b`
- `gfx!?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ` at `0x1800fb53b`
- `gfx!?Create@IEffectMorphology@GEL@@SA?AV?$TCntPtr@UIEffectMorphology@GEL@@@Ofc@@AEBUIEffect@2@AEBU?$TVector2@I@Math@@W4Operator@12@@Z` at `0x1800fb5a4`
- `gfx!?Create@IEffectMorphology@GEL@@SA?AV?$TCntPtr@UIEffectMorphology@GEL@@@Ofc@@AEBUIEffect@2@AEBU?$TVector2@I@Math@@W4Operator@12@@Z` at `0x1800fb5a4`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
_QWORD *__fastcall Mso::SVG::FeMorphologyRenderer::ApplyUnaryFilter(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6)
{
  double *v8; // rbx
  double v9; // xmm7_8
  double v10; // xmm0_8
  _QWORD *v11; // rax
  double v12; // xmm6_8
  __int64 v14; // [rsp+28h] [rbp-30h] BYREF
  int v15; // [rsp+60h] [rbp+8h] BYREF
  int v16; // [rsp+64h] [rbp+Ch]

  v8 = *(double **)(a1 + 16);
  if ( !v8 )
  {
    CrashWithRecovery(0x1E3C3843u, 0);
    JUMPOUT(0x1800FB5F8LL);
  }
  _castguard_slow_path_check_user_handled(*(_QWORD *)v8, 9176, 2760);
  _castguard_slow_path_check_user_handled(*(_QWORD *)v8, 11200, 0);
  v9 = v8[61];
  if ( v9 == 0.0 || (v10 = v8[62], v10 == 0.0) )
  {
    v11 = (_QWORD *)GEL::IEffectContainer::Create(&v14);
  }
  else
  {
    if ( *(_DWORD *)(a6 + 32) == 1 )
    {
      v9 = v9 * (*(double *)(a6 + 16) - *(double *)a6);
      v10 = v10 * (*(double *)(a6 + 24) - *(double *)(a6 + 8));
    }
    v12 = round(v10);
    v15 = (int)round(v9);
    v16 = (int)v12;
    v11 = (_QWORD *)GEL::IEffectMorphology::Create(&v14, a3, &v15, *((unsigned int *)v8 + 126));
  }
  *a2 = *v11;
  *v11 = 0;
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
  return a2;
}

```

## disassembly

```asm
0x1800fb4c0  mov     rax, rsp
0x1800fb4c3  mov     [rax+10h], rbx
0x1800fb4c7  mov     [rax+18h], rsi
0x1800fb4cb  push    rdi
0x1800fb4cc  sub     rsp, 50h
0x1800fb4d0  movaps  xmmword ptr [rax-18h], xmm6
0x1800fb4d4  movaps  xmmword ptr [rax-28h], xmm7
0x1800fb4d8  mov     rsi, r8
0x1800fb4db  mov     rdi, rdx
0x1800fb4de  mov     rbx, [rcx+10h]
0x1800fb4e2  test    rbx, rbx
0x1800fb4e5  jz      loc_1800FB5EB
0x1800fb4eb  mov     edx, 23D8h
0x1800fb4f0  mov     r8d, 0AC8h
0x1800fb4f6  mov     rcx, [rbx]
0x1800fb4f9  call    __castguard_slow_path_check_user_handled
0x1800fb4fe  test    rbx, rbx
0x1800fb501  jz      short loc_1800FB513
0x1800fb503  xor     r8d, r8d
0x1800fb506  mov     edx, 2BC0h
0x1800fb50b  mov     rcx, [rbx]
0x1800fb50e  call    __castguard_slow_path_check_user_handled
0x1800fb513  movsd   xmm7, qword ptr [rbx+1E8h]
0x1800fb51b  xorps   xmm1, xmm1
0x1800fb51e  ucomisd xmm7, xmm1
0x1800fb522  jp      short loc_1800FB526
0x1800fb524  jz      short loc_1800FB536
0x1800fb526  movsd   xmm0, qword ptr [rbx+1F0h]
0x1800fb52e  ucomisd xmm0, xmm1
0x1800fb532  jp      short loc_1800FB543
0x1800fb534  jnz     short loc_1800FB543
0x1800fb536  lea     rcx, [rsp+58h+var_30]
0x1800fb53b  call    cs:__imp_?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ; GEL::IEffectContainer::Create(void)
0x1800fb541  jmp     short loc_1800FB5AA
0x1800fb543  mov     rax, [rsp+58h+arg_28]
0x1800fb54b  cmp     dword ptr [rax+20h], 1
0x1800fb54f  jnz     short loc_1800FB56C
0x1800fb551  movsd   xmm1, qword ptr [rax+10h]
0x1800fb556  subsd   xmm1, qword ptr [rax]
0x1800fb55a  mulsd   xmm7, xmm1
0x1800fb55e  movsd   xmm2, qword ptr [rax+18h]
0x1800fb563  subsd   xmm2, qword ptr [rax+8]
0x1800fb568  mulsd   xmm0, xmm2; X
0x1800fb56c  call    cs:__imp_round
0x1800fb572  movaps  xmm6, xmm0
0x1800fb575  movaps  xmm0, xmm7; X
0x1800fb578  call    cs:__imp_round
0x1800fb57e  cvttsd2si rax, xmm0
0x1800fb583  mov     [rsp+58h+arg_0], eax
0x1800fb587  cvttsd2si rax, xmm6
0x1800fb58c  mov     [rsp+58h+arg_4], eax
0x1800fb590  mov     r9d, [rbx+1F8h]
0x1800fb597  lea     r8, [rsp+58h+arg_0]
0x1800fb59c  mov     rdx, rsi
0x1800fb59f  lea     rcx, [rsp+58h+var_30]
0x1800fb5a4  call    cs:__imp_?Create@IEffectMorphology@GEL@@SA?AV?$TCntPtr@UIEffectMorphology@GEL@@@Ofc@@AEBUIEffect@2@AEBU?$TVector2@I@Math@@W4Operator@12@@Z; GEL::IEffectMorphology::Create(GEL::IEffect const &,Math::TVector2<uint> const &,GEL::IEffectMorphology::Operator)
0x1800fb5aa  mov     rcx, [rax]
0x1800fb5ad  mov     [rdi], rcx
0x1800fb5b0  mov     qword ptr [rax], 0
0x1800fb5b7  mov     rcx, [rsp+58h+var_30]
0x1800fb5bc  test    rcx, rcx
0x1800fb5bf  jz      short loc_1800FB5CE
0x1800fb5c1  mov     rax, [rcx]
0x1800fb5c4  mov     rax, [rax+8]
0x1800fb5c8  call    cs:__guard_dispatch_icall_fptr
0x1800fb5ce  mov     rax, rdi
0x1800fb5d1  mov     rbx, [rsp+58h+arg_8]
0x1800fb5d6  mov     rsi, [rsp+58h+arg_10]
0x1800fb5db  movaps  xmm6, [rsp+58h+var_18]
0x1800fb5e0  movaps  xmm7, [rsp+58h+var_28]
0x1800fb5e5  add     rsp, 50h
0x1800fb5e9  pop     rdi
0x1800fb5ea  retn
0x1800fb5eb  xor     edx, edx
0x1800fb5ed  mov     ecx, 1E3C3843h
0x1800fb5f2  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
