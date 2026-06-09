# Mso::SVG::FeConvolveMatrixRenderer::ApplyUnaryFilter(GEL::IEffect const &,Mso::SVG::StyleResolveChain const &,GEL::Rect const &,Mso::SVG::PrimitiveUnitResolver const &,GEL::IColorResolver const *)

- ea: `0x1800fac80`
- end: `0x1800fae48`
- name: `?ApplyUnaryFilter@FeConvolveMatrixRenderer@SVG@Mso@@UEBA?AV?$TCntPtr@$$CBUIEffect@GEL@@@Ofc@@AEBUIEffect@GEL@@AEBVStyleResolveChain@23@AEBURect@7@AEBVPrimitiveUnitResolver@23@PEBUIColorResolver@7@@Z`
- size: `456`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64, __int64, int, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800fac80`
- `0x18013e0c0`
- `0x18013f810`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fae41`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fae41`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800fae33`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800fae33`
- `gfx!?Create@IEffectConvolve@GEL@@SA?AV?$TCntPtr@UIEffectConvolve@GEL@@@Ofc@@AEBUIEffect@2@PEBMAEBU?$TSize@I@Math@@MMAEBU?$TVector2@H@7@_NW4EdgeMode@12@PEBU?$TVector2@N@7@@Z` at `0x1800faddb`
- `gfx!?Create@IEffectConvolve@GEL@@SA?AV?$TCntPtr@UIEffectConvolve@GEL@@@Ofc@@AEBUIEffect@2@PEBMAEBU?$TSize@I@Math@@MMAEBU?$TVector2@H@7@_NW4EdgeMode@12@PEBU?$TVector2@N@7@@Z` at `0x1800faddb`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
    JUMPOUT(0x1800FAE47LL);
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
0x1800fac80  mov     [rsp-8+arg_8], rbx
0x1800fac85  mov     [rsp-8+arg_10], rsi
0x1800fac8a  mov     [rsp-8+arg_18], rdi
0x1800fac8f  push    rbp
0x1800fac90  mov     rbp, rsp
0x1800fac93  sub     rsp, 80h
0x1800fac9a  mov     rsi, r8
0x1800fac9d  mov     rdi, rdx
0x1800faca0  mov     rbx, [rcx+10h]
0x1800faca4  test    rbx, rbx
0x1800faca7  jz      loc_1800FAE3A
0x1800facad  mov     edx, 23D8h
0x1800facb2  mov     r8d, 0AC8h
0x1800facb8  mov     rcx, [rbx]
0x1800facbb  call    __castguard_slow_path_check_user_handled
0x1800facc0  test    rbx, rbx
0x1800facc3  jz      short loc_1800FACD5
0x1800facc5  xor     r8d, r8d
0x1800facc8  mov     edx, 2770h
0x1800faccd  mov     rcx, [rbx]
0x1800facd0  call    __castguard_slow_path_check_user_handled
0x1800facd5  mov     r10d, [rbx+1E8h]
0x1800facdc  mov     r11d, [rbx+1ECh]
0x1800face3  movups  xmm0, xmmword ptr [rbx+1F8h]
0x1800facea  movdqu  xmmword ptr [rbp+var_18], xmm0
0x1800facef  mov     rax, [rbp+arg_28]
0x1800facf3  movsd   xmm2, [rbp+var_18]
0x1800facf8  cmp     dword ptr [rax+20h], 1
0x1800facfc  jnz     short loc_1800FAD2A
0x1800facfe  movsd   xmm0, qword ptr [rax+10h]
0x1800fad03  subsd   xmm0, qword ptr [rax]
0x1800fad07  mulsd   xmm2, xmm0
0x1800fad0b  movsd   [rbp+var_18], xmm2
0x1800fad10  movsd   xmm1, qword ptr [rax+18h]
0x1800fad15  subsd   xmm1, qword ptr [rax+8]
0x1800fad1a  movsd   xmm0, [rbp+var_18+8]
0x1800fad1f  mulsd   xmm0, xmm1
0x1800fad23  movsd   [rbp+var_18+8], xmm0
0x1800fad28  jmp     short loc_1800FAD2F
0x1800fad2a  movsd   xmm0, [rbp+var_18+8]
0x1800fad2f  xorps   xmm1, xmm1
0x1800fad32  comisd  xmm2, xmm1
0x1800fad36  jbe     short loc_1800FAD44
0x1800fad38  comisd  xmm0, xmm1
0x1800fad3c  jbe     short loc_1800FAD44
0x1800fad3e  lea     rcx, [rbp+var_18]
0x1800fad42  jmp     short loc_1800FAD46
0x1800fad44  xor     ecx, ecx
0x1800fad46  mov     r8d, [rbx+20Ch]
0x1800fad4d  mov     r9b, [rbx+208h]
0x1800fad54  cmp     byte ptr [rbx+224h], 0
0x1800fad5b  jz      loc_1800FAE20
0x1800fad61  mov     edx, [rbx+220h]
0x1800fad67  cmp     byte ptr [rbx+21Ch], 0
0x1800fad6e  jz      loc_1800FAE20
0x1800fad74  mov     eax, [rbx+218h]
0x1800fad7a  mov     [rbp+arg_0], eax
0x1800fad7d  mov     [rbp+arg_4], edx
0x1800fad80  movss   xmm0, dword ptr [rbx+1F0h]
0x1800fad88  cmp     byte ptr [rbx+214h], 0
0x1800fad8f  jz      loc_1800FAE20
0x1800fad95  mov     [rbp+var_2C], r10d
0x1800fad99  mov     [rbp+var_28], r11d
0x1800fad9d  mov     [rsp+80h+var_38], rcx
0x1800fada2  mov     [rsp+80h+var_40], r8d
0x1800fada7  mov     [rsp+80h+var_48], r9b
0x1800fadac  lea     rax, [rbp+arg_0]
0x1800fadb0  mov     [rsp+80h+var_50], rax
0x1800fadb5  movss   [rsp+80h+var_58], xmm0
0x1800fadbb  movss   xmm0, dword ptr [rbx+210h]
0x1800fadc3  movss   dword ptr [rsp+80h+Reserved], xmm0
0x1800fadc9  lea     r9, [rbp+var_2C]
0x1800fadcd  mov     r8, [rbx+228h]
0x1800fadd4  mov     rdx, rsi
0x1800fadd7  lea     rcx, [rbp+var_20]
0x1800faddb  call    cs:__imp_?Create@IEffectConvolve@GEL@@SA?AV?$TCntPtr@UIEffectConvolve@GEL@@@Ofc@@AEBUIEffect@2@PEBMAEBU?$TSize@I@Math@@MMAEBU?$TVector2@H@7@_NW4EdgeMode@12@PEBU?$TVector2@N@7@@Z; GEL::IEffectConvolve::Create(GEL::IEffect const &,float const *,Math::TSize<uint> const &,float,float,Math::TVector2<int> const &,bool,GEL::IEffectConvolve::EdgeMode,Math::TVector2<double> const *)
0x1800fade1  mov     rcx, [rax]
0x1800fade4  mov     qword ptr [rax], 0
0x1800fadeb  mov     [rdi], rcx
0x1800fadee  mov     rcx, [rbp+var_20]
0x1800fadf2  test    rcx, rcx
0x1800fadf5  jz      short loc_1800FAE04
0x1800fadf7  mov     rax, [rcx]
0x1800fadfa  mov     rax, [rax+8]
0x1800fadfe  call    cs:__guard_dispatch_icall_fptr
0x1800fae04  mov     rax, rdi
0x1800fae07  lea     r11, [rsp+80h+var_s0]
0x1800fae0f  mov     rbx, [r11+18h]
0x1800fae13  mov     rsi, [r11+20h]
0x1800fae17  mov     rdi, [r11+28h]
0x1800fae1b  mov     rsp, r11
0x1800fae1e  pop     rbp
0x1800fae1f  retn
0x1800fae20  mov     [rsp+80h+Reserved], 0; Reserved
0x1800fae29  xor     r9d, r9d; LineNo
0x1800fae2c  xor     r8d, r8d; FileName
0x1800fae2f  xor     edx, edx; FunctionName
0x1800fae31  xor     ecx, ecx; Expression
0x1800fae33  call    cs:__imp__invoke_watson
0x1800fae3a  xor     edx, edx
0x1800fae3c  mov     ecx, 1E3C3843h
0x1800fae41  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
