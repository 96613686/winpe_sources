# Mso::SVG::FeComponentTransferRenderer::ApplyUnaryFilter(GEL::IEffect const &,Mso::SVG::StyleResolveChain const &,GEL::Rect const &,Mso::SVG::PrimitiveUnitResolver const &,GEL::IColorResolver const *)

- ea: `0x1800fa920`
- end: `0x1800fab44`
- name: `?ApplyUnaryFilter@FeComponentTransferRenderer@SVG@Mso@@UEBA?AV?$TCntPtr@$$CBUIEffect@GEL@@@Ofc@@AEBUIEffect@GEL@@AEBVStyleResolveChain@23@AEBURect@7@AEBVPrimitiveUnitResolver@23@PEBUIColorResolver@7@@Z`
- size: `548`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800fa808`
- `0x1800fa920`
- `0x1800fbdc0`
- `0x1800fbf00`
- `0x18013e0c0`
- `0x18013f810`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fab05`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fab13`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fab21`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fab2f`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fab3d`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fab05`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fab13`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fab21`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fab2f`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fab3d`
- `gfx!?Create@IEffectComponentTransfer@GEL@@SA?AV?$TCntPtr@UIEffectComponentTransfer@GEL@@@Ofc@@AEBUIEffect@2@AEBUITransferFunction@2@111W4ColorSpace@2@@Z` at `0x1800faa77`
- `gfx!?Create@IEffectComponentTransfer@GEL@@SA?AV?$TCntPtr@UIEffectComponentTransfer@GEL@@@Ofc@@AEBUIEffect@2@AEBUITransferFunction@2@111W4ColorSpace@2@@Z` at `0x1800faa77`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall Mso::SVG::FeComponentTransferRenderer::ApplyUnaryFilter(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        _QWORD *a4)
{
  _QWORD *v7; // r14
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int16 *v10; // rcx
  __int64 v11; // rax
  char v12; // bp
  __int64 v13; // rbx
  __int64 v14; // rdi
  __int64 v15; // rsi
  __int64 v16; // r14
  __int64 v17; // rbx
  __int64 v18; // rdi
  __int64 v19; // rsi
  __int64 *v20; // rax
  __int64 v21; // rcx
  __int64 v23; // [rsp+48h] [rbp-50h] BYREF
  __int64 v24; // [rsp+50h] [rbp-48h] BYREF
  __int64 v25; // [rsp+58h] [rbp-40h] BYREF
  __int64 v26; // [rsp+60h] [rbp-38h] BYREF
  __int64 v27; // [rsp+A0h] [rbp+8h] BYREF

  v7 = *(_QWORD **)(a1 + 16);
  if ( !v7 )
    goto LABEL_21;
  _castguard_slow_path_check_user_handled(*v7, 9176, 2760);
  _castguard_slow_path_check_user_handled(*v7, 9728, 0);
  v8 = a4[1];
  v9 = *(_QWORD *)(v8 + 16);
  if ( v9 )
  {
    v10 = (__int16 *)(v9 + 1320);
  }
  else
  {
    v10 = &Mso::SVG::StyleMetaData<1>::initial;
    if ( *(_QWORD *)(v8 + 8) )
      v10 = (__int16 *)&Mso::SVG::StyleMetaData<1>::inherit;
  }
  if ( !*((_BYTE *)v10 + 1) )
  {
    if ( *a4 )
      v11 = Mso::SVG::StyleResolveChain::Get<1>();
    else
      v11 = Mso::SVG::StyleResolveChain::GetNormal<1>(a4, *(_QWORD *)(v8 + 8));
    v10 = (__int16 *)v11;
  }
  v12 = *(_BYTE *)v10;
  v13 = v7[63];
  v14 = v7[64];
  v15 = v7[65];
  sub_1800FA808(&v25, v7[62]);
  sub_1800FA808(&v24, v13);
  sub_1800FA808(&v23, v14);
  sub_1800FA808(&v27, v15);
  v16 = v27;
  if ( !v27 )
    goto LABEL_22;
  v17 = v23;
  if ( !v23 )
  {
LABEL_23:
    CrashWithRecovery(0x1E3C3843u, 0);
    goto LABEL_24;
  }
  v18 = v24;
  if ( !v24 )
  {
LABEL_24:
    CrashWithRecovery(0x1E3C3843u, 0);
    JUMPOUT(0x1800FAB43LL);
  }
  v19 = v25;
  if ( !v25 )
  {
    CrashWithRecovery(0x1E3C3843u, 0);
LABEL_21:
    CrashWithRecovery(0x1E3C3843u, 0);
LABEL_22:
    CrashWithRecovery(0x1E3C3843u, 0);
    goto LABEL_23;
  }
  v20 = (__int64 *)GEL::IEffectComponentTransfer::Create(&v26, a3, v25, v24, v23, v27, v12);
  v21 = *v20;
  *v20 = 0;
  *a2 = v21;
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 8LL))(v26);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 8LL))(v18);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 8LL))(v19);
  return a2;
}

```

## disassembly

```asm
0x1800fa920  mov     [rsp+arg_8], rbx
0x1800fa925  mov     [rsp+arg_10], rbp
0x1800fa92a  push    rsi
0x1800fa92b  push    rdi
0x1800fa92c  push    r12
0x1800fa92e  push    r14
0x1800fa930  push    r15
0x1800fa932  sub     rsp, 70h
0x1800fa936  mov     rbx, r9
0x1800fa939  mov     r12, r8
0x1800fa93c  mov     r15, rdx
0x1800fa93f  mov     r14, [rcx+10h]
0x1800fa943  test    r14, r14
0x1800fa946  jz      loc_1800FAB0C
0x1800fa94c  mov     edx, 23D8h
0x1800fa951  mov     r8d, 0AC8h
0x1800fa957  mov     rcx, [r14]
0x1800fa95a  call    __castguard_slow_path_check_user_handled
0x1800fa95f  test    r14, r14
0x1800fa962  jz      short loc_1800FA974
0x1800fa964  xor     r8d, r8d
0x1800fa967  mov     edx, 2600h
0x1800fa96c  mov     rcx, [r14]
0x1800fa96f  call    __castguard_slow_path_check_user_handled
0x1800fa974  mov     rdx, [rbx+8]
0x1800fa978  mov     rcx, [rdx+10h]
0x1800fa97c  test    rcx, rcx
0x1800fa97f  jz      short loc_1800FA98A
0x1800fa981  add     rcx, 528h
0x1800fa988  jmp     short loc_1800FA99F
0x1800fa98a  cmp     qword ptr [rdx+8], 0
0x1800fa98f  lea     rcx, ?initial@?$StyleMetaData@$00@SVG@Mso@@2V?$optional@W4ColorSpace@GEL@@@std@@B; std::optional<GEL::ColorSpace> const Mso::SVG::StyleMetaData<1>::initial
0x1800fa996  jz      short loc_1800FA99F
0x1800fa998  lea     rcx, ?inherit@?$StyleMetaData@$00@SVG@Mso@@2V?$optional@W4ColorSpace@GEL@@@std@@B; std::optional<GEL::ColorSpace> const Mso::SVG::StyleMetaData<1>::inherit
0x1800fa99f  mov     eax, 8
0x1800fa9a4  cmp     byte ptr [rcx+1], 0
0x1800fa9a8  jnz     short loc_1800FA9C8
0x1800fa9aa  mov     rcx, [rbx]
0x1800fa9ad  test    rcx, rcx
0x1800fa9b0  jz      short loc_1800FA9B9
0x1800fa9b2  call    ??$Get@$00@StyleResolveChain@SVG@Mso@@QEBAAEBW4ColorSpace@GEL@@XZ; Mso::SVG::StyleResolveChain::Get<1>(void)
0x1800fa9b7  jmp     short loc_1800FA9C5
0x1800fa9b9  mov     rdx, [rax+rdx]
0x1800fa9bd  mov     rcx, rbx
0x1800fa9c0  call    ??$GetNormal@$00@StyleResolveChain@SVG@Mso@@AEBAAEBW4ColorSpace@GEL@@AEBVStyle@12@@Z; Mso::SVG::StyleResolveChain::GetNormal<1>(Mso::SVG::Style const &)
0x1800fa9c5  mov     rcx, rax
0x1800fa9c8  mov     bpl, [rcx]
0x1800fa9cb  mov     rbx, [r14+1F8h]
0x1800fa9d2  mov     rdi, [r14+200h]
0x1800fa9d9  mov     rsi, [r14+208h]
0x1800fa9e0  mov     rdx, [r14+1F0h]
0x1800fa9e7  lea     rcx, [rsp+98h+var_40]
0x1800fa9ec  call    sub_1800FA808
0x1800fa9f1  nop
0x1800fa9f2  mov     rdx, rbx
0x1800fa9f5  lea     rcx, [rsp+98h+var_48]
0x1800fa9fa  call    sub_1800FA808
0x1800fa9ff  nop
0x1800faa00  mov     rdx, rdi
0x1800faa03  lea     rcx, [rsp+98h+var_50]
0x1800faa08  call    sub_1800FA808
0x1800faa0d  nop
0x1800faa0e  mov     rdx, rsi
0x1800faa11  lea     rcx, [rsp+98h+arg_0]
0x1800faa19  call    sub_1800FA808
0x1800faa1e  nop
0x1800faa1f  mov     r14, [rsp+98h+arg_0]
0x1800faa27  test    r14, r14
0x1800faa2a  jz      loc_1800FAB1A
0x1800faa30  mov     rbx, [rsp+98h+var_50]
0x1800faa35  test    rbx, rbx
0x1800faa38  jz      loc_1800FAB28
0x1800faa3e  mov     rdi, [rsp+98h+var_48]
0x1800faa43  test    rdi, rdi
0x1800faa46  jz      loc_1800FAB36
0x1800faa4c  mov     rsi, [rsp+98h+var_40]
0x1800faa51  test    rsi, rsi
0x1800faa54  jz      loc_1800FAAFE
0x1800faa5a  mov     [rsp+98h+var_68], bpl
0x1800faa5f  mov     [rsp+98h+var_70], r14
0x1800faa64  mov     [rsp+98h+var_78], rbx
0x1800faa69  mov     r9, rdi
0x1800faa6c  mov     r8, rsi
0x1800faa6f  mov     rdx, r12
0x1800faa72  lea     rcx, [rsp+98h+var_38]
0x1800faa77  call    cs:__imp_?Create@IEffectComponentTransfer@GEL@@SA?AV?$TCntPtr@UIEffectComponentTransfer@GEL@@@Ofc@@AEBUIEffect@2@AEBUITransferFunction@2@111W4ColorSpace@2@@Z; GEL::IEffectComponentTransfer::Create(GEL::IEffect const &,GEL::ITransferFunction const &,GEL::ITransferFunction const &,GEL::ITransferFunction const &,GEL::ITransferFunction const &,GEL::ColorSpace)
0x1800faa7d  mov     rcx, [rax]
0x1800faa80  mov     qword ptr [rax], 0
0x1800faa87  mov     [r15], rcx
0x1800faa8a  mov     rcx, [rsp+98h+var_38]
0x1800faa8f  test    rcx, rcx
0x1800faa92  jz      short loc_1800FAAA2
0x1800faa94  mov     rax, [rcx]
0x1800faa97  mov     rax, [rax+8]
0x1800faa9b  call    cs:__guard_dispatch_icall_fptr
0x1800faaa1  nop
0x1800faaa2  mov     rax, [r14]
0x1800faaa5  mov     rcx, r14
0x1800faaa8  mov     rax, [rax+8]
0x1800faaac  call    cs:__guard_dispatch_icall_fptr
0x1800faab2  mov     rax, [rbx]
0x1800faab5  mov     rcx, rbx
0x1800faab8  mov     rax, [rax+8]
0x1800faabc  call    cs:__guard_dispatch_icall_fptr
0x1800faac2  mov     rax, [rdi]
0x1800faac5  mov     rcx, rdi
0x1800faac8  mov     rax, [rax+8]
0x1800faacc  call    cs:__guard_dispatch_icall_fptr
0x1800faad2  mov     rax, [rsi]
0x1800faad5  mov     rcx, rsi
0x1800faad8  mov     rax, [rax+8]
0x1800faadc  call    cs:__guard_dispatch_icall_fptr
0x1800faae2  mov     rax, r15
0x1800faae5  lea     r11, [rsp+98h+var_28]
0x1800faaea  mov     rbx, [r11+38h]
0x1800faaee  mov     rbp, [r11+40h]
0x1800faaf2  mov     rsp, r11
0x1800faaf5  pop     r15
0x1800faaf7  pop     r14
0x1800faaf9  pop     r12
0x1800faafb  pop     rdi
0x1800faafc  pop     rsi
0x1800faafd  retn
0x1800faafe  xor     edx, edx
0x1800fab00  mov     ecx, 1E3C3843h
0x1800fab05  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800fab0b  nop
0x1800fab0c  xor     edx, edx
0x1800fab0e  mov     ecx, 1E3C3843h
0x1800fab13  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800fab19  nop
0x1800fab1a  xor     edx, edx
0x1800fab1c  mov     ecx, 1E3C3843h
0x1800fab21  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800fab27  nop
0x1800fab28  xor     edx, edx
0x1800fab2a  mov     ecx, 1E3C3843h
0x1800fab2f  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800fab35  nop
0x1800fab36  xor     edx, edx
0x1800fab38  mov     ecx, 1E3C3843h
0x1800fab3d  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
