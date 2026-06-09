# Mso::SVG::FeConvolveMatrixRenderer::ApplyUnaryFilter(GEL::IEffect const &,Mso::SVG::StyleResolveChain const &,GEL::Rect const &,Mso::SVG::PrimitiveUnitResolver const &,GEL::IColorResolver const *)

- ea: `0x1800fac60`
- end: `0x1800fae28`
- name: `?ApplyUnaryFilter@FeConvolveMatrixRenderer@SVG@Mso@@UEBA?AV?$TCntPtr@$$CBUIEffect@GEL@@@Ofc@@AEBUIEffect@GEL@@AEBVStyleResolveChain@23@AEBURect@7@AEBVPrimitiveUnitResolver@23@PEBUIColorResolver@7@@Z`
- size: `456`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800fac60`
- `0x18013e010`
- `0x18013f760`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fae21`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fae21`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800fae13`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800fae13`
- `gfx!?Create@IEffectConvolve@GEL@@SA?AV?$TCntPtr@UIEffectConvolve@GEL@@@Ofc@@AEBUIEffect@2@PEBMAEBU?$TSize@I@Math@@MMAEBU?$TVector2@H@7@_NW4EdgeMode@12@PEBU?$TVector2@N@7@@Z` at `0x1800fadbb`
- `gfx!?Create@IEffectConvolve@GEL@@SA?AV?$TCntPtr@UIEffectConvolve@GEL@@@Ofc@@AEBUIEffect@2@PEBMAEBU?$TSize@I@Math@@MMAEBU?$TVector2@H@7@_NW4EdgeMode@12@PEBU?$TVector2@N@7@@Z` at `0x1800fadbb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Mso::SVG::FeConvolveMatrixRenderer::ApplyUnaryFilter(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6)
{
  _QWORD *v8; // rbx
  int v9; // r10d
  int v10; // r11d
  double v11; // xmm2_8
  double v12; // xmm0_8
  double *v13; // rcx
  int v14; // r8d
  char v15; // r9
  int v16; // edx
  int v17; // xmm0_4
  __int64 *v18; // rax
  __int64 v19; // rcx
  _DWORD v21[3]; // [rsp+54h] [rbp-2Ch] BYREF
  __int64 v22; // [rsp+60h] [rbp-20h] BYREF
  double v23[3]; // [rsp+68h] [rbp-18h] BYREF
  int v24; // [rsp+90h] [rbp+10h] BYREF
  int v25; // [rsp+94h] [rbp+14h]

  v8 = *(_QWORD **)(a1 + 16);
  if ( !v8 )
  {
    CrashWithRecovery(0x1E3C3843u, 0);
    JUMPOUT(0x1800FAE27LL);
  }
  _castguard_slow_path_check_user_handled(*v8, 9176, 2760);
  _castguard_slow_path_check_user_handled(*v8, 10096, 0);
  v9 = *((_DWORD *)v8 + 122);
  v10 = *((_DWORD *)v8 + 123);
  *(_OWORD *)v23 = *(_OWORD *)(v8 + 63);
  v11 = v23[0];
  if ( *(_DWORD *)(a6 + 32) == 1 )
  {
    v11 = v23[0] * (*(double *)(a6 + 16) - *(double *)a6);
    v23[0] = v11;
    v12 = v23[1] * (*(double *)(a6 + 24) - *(double *)(a6 + 8));
    v23[1] = v12;
  }
  else
  {
    v12 = v23[1];
  }
  if ( v11 <= 0.0 || v12 <= 0.0 )
    v13 = 0;
  else
    v13 = v23;
  v14 = *((_DWORD *)v8 + 131);
  v15 = *((_BYTE *)v8 + 520);
  if ( !*((_BYTE *)v8 + 548)
    || (v16 = *((_DWORD *)v8 + 136), !*((_BYTE *)v8 + 540))
    || (v24 = *((_DWORD *)v8 + 134), v25 = v16, v17 = *((_DWORD *)v8 + 124), !*((_BYTE *)v8 + 532)) )
  {
    _invoke_watson(0, 0, 0, 0, 0);
  }
  v21[0] = v9;
  v21[1] = v10;
  v18 = (__int64 *)GEL::IEffectConvolve::Create(&v22, a3, v8[69], v21, *((_DWORD *)v8 + 132), v17, &v24, v15, v14, v13);
  v19 = *v18;
  *v18 = 0;
  *a2 = v19;
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 8LL))(v22);
  return a2;
}

```

## disassembly

```asm
0x1800fac60  mov     [rsp-8+arg_8], rbx
0x1800fac65  mov     [rsp-8+arg_10], rsi
0x1800fac6a  mov     [rsp-8+arg_18], rdi
0x1800fac6f  push    rbp
0x1800fac70  mov     rbp, rsp
0x1800fac73  sub     rsp, 80h
0x1800fac7a  mov     rsi, r8
0x1800fac7d  mov     rdi, rdx
0x1800fac80  mov     rbx, [rcx+10h]
0x1800fac84  test    rbx, rbx
0x1800fac87  jz      loc_1800FAE1A
0x1800fac8d  mov     edx, 23D8h
0x1800fac92  mov     r8d, 0AC8h
0x1800fac98  mov     rcx, [rbx]
0x1800fac9b  call    __castguard_slow_path_check_user_handled
0x1800faca0  test    rbx, rbx
0x1800faca3  jz      short loc_1800FACB5
0x1800faca5  xor     r8d, r8d
0x1800faca8  mov     edx, 2770h
0x1800facad  mov     rcx, [rbx]
0x1800facb0  call    __castguard_slow_path_check_user_handled
0x1800facb5  mov     r10d, [rbx+1E8h]
0x1800facbc  mov     r11d, [rbx+1ECh]
0x1800facc3  movups  xmm0, xmmword ptr [rbx+1F8h]
0x1800facca  movdqu  xmmword ptr [rbp+var_18], xmm0
0x1800faccf  mov     rax, [rbp+arg_28]
0x1800facd3  movsd   xmm2, [rbp+var_18]
0x1800facd8  cmp     dword ptr [rax+20h], 1
0x1800facdc  jnz     short loc_1800FAD0A
0x1800facde  movsd   xmm0, qword ptr [rax+10h]
0x1800face3  subsd   xmm0, qword ptr [rax]
0x1800face7  mulsd   xmm2, xmm0
0x1800faceb  movsd   [rbp+var_18], xmm2
0x1800facf0  movsd   xmm1, qword ptr [rax+18h]
0x1800facf5  subsd   xmm1, qword ptr [rax+8]
0x1800facfa  movsd   xmm0, [rbp+var_18+8]
0x1800facff  mulsd   xmm0, xmm1
0x1800fad03  movsd   [rbp+var_18+8], xmm0
0x1800fad08  jmp     short loc_1800FAD0F
0x1800fad0a  movsd   xmm0, [rbp+var_18+8]
0x1800fad0f  xorps   xmm1, xmm1
0x1800fad12  comisd  xmm2, xmm1
0x1800fad16  jbe     short loc_1800FAD24
0x1800fad18  comisd  xmm0, xmm1
0x1800fad1c  jbe     short loc_1800FAD24
0x1800fad1e  lea     rcx, [rbp+var_18]
0x1800fad22  jmp     short loc_1800FAD26
0x1800fad24  xor     ecx, ecx
0x1800fad26  mov     r8d, [rbx+20Ch]
0x1800fad2d  mov     r9b, [rbx+208h]
0x1800fad34  cmp     byte ptr [rbx+224h], 0
0x1800fad3b  jz      loc_1800FAE00
0x1800fad41  mov     edx, [rbx+220h]
0x1800fad47  cmp     byte ptr [rbx+21Ch], 0
0x1800fad4e  jz      loc_1800FAE00
0x1800fad54  mov     eax, [rbx+218h]
0x1800fad5a  mov     [rbp+arg_0], eax
0x1800fad5d  mov     [rbp+arg_4], edx
0x1800fad60  movss   xmm0, dword ptr [rbx+1F0h]
0x1800fad68  cmp     byte ptr [rbx+214h], 0
0x1800fad6f  jz      loc_1800FAE00
0x1800fad75  mov     [rbp+var_2C], r10d
0x1800fad79  mov     [rbp+var_28], r11d
0x1800fad7d  mov     [rsp+80h+var_38], rcx
0x1800fad82  mov     [rsp+80h+var_40], r8d
0x1800fad87  mov     [rsp+80h+var_48], r9b
0x1800fad8c  lea     rax, [rbp+arg_0]
0x1800fad90  mov     [rsp+80h+var_50], rax
0x1800fad95  movss   [rsp+80h+var_58], xmm0
0x1800fad9b  movss   xmm0, dword ptr [rbx+210h]
0x1800fada3  movss   dword ptr [rsp+80h+Reserved], xmm0
0x1800fada9  lea     r9, [rbp+var_2C]
0x1800fadad  mov     r8, [rbx+228h]
0x1800fadb4  mov     rdx, rsi
0x1800fadb7  lea     rcx, [rbp+var_20]
0x1800fadbb  call    cs:__imp_?Create@IEffectConvolve@GEL@@SA?AV?$TCntPtr@UIEffectConvolve@GEL@@@Ofc@@AEBUIEffect@2@PEBMAEBU?$TSize@I@Math@@MMAEBU?$TVector2@H@7@_NW4EdgeMode@12@PEBU?$TVector2@N@7@@Z; GEL::IEffectConvolve::Create(GEL::IEffect const &,float const *,Math::TSize<uint> const &,float,float,Math::TVector2<int> const &,bool,GEL::IEffectConvolve::EdgeMode,Math::TVector2<double> const *)
0x1800fadc1  mov     rcx, [rax]
0x1800fadc4  mov     qword ptr [rax], 0
0x1800fadcb  mov     [rdi], rcx
0x1800fadce  mov     rcx, [rbp+var_20]
0x1800fadd2  test    rcx, rcx
0x1800fadd5  jz      short loc_1800FADE4
0x1800fadd7  mov     rax, [rcx]
0x1800fadda  mov     rax, [rax+8]
0x1800fadde  call    cs:__guard_dispatch_icall_fptr
0x1800fade4  mov     rax, rdi
0x1800fade7  lea     r11, [rsp+80h+var_s0]
0x1800fadef  mov     rbx, [r11+18h]
0x1800fadf3  mov     rsi, [r11+20h]
0x1800fadf7  mov     rdi, [r11+28h]
0x1800fadfb  mov     rsp, r11
0x1800fadfe  pop     rbp
0x1800fadff  retn
0x1800fae00  mov     [rsp+80h+Reserved], 0; Reserved
0x1800fae09  xor     r9d, r9d; LineNo
0x1800fae0c  xor     r8d, r8d; FileName
0x1800fae0f  xor     edx, edx; FunctionName
0x1800fae11  xor     ecx, ecx; Expression
0x1800fae13  call    cs:__imp__invoke_watson
0x1800fae1a  xor     edx, edx
0x1800fae1c  mov     ecx, 1E3C3843h
0x1800fae21  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
