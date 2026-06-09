# Mso::SVG::FeBlendRenderer::ApplyBinaryFilter(GEL::IEffect const &,GEL::IEffect const &,Mso::SVG::StyleResolveChain const &,GEL::Rect const &,Mso::SVG::PrimitiveUnitResolver const &)

- ea: `0x1800fae30`
- end: `0x1800faf69`
- name: `?ApplyBinaryFilter@FeBlendRenderer@SVG@Mso@@UEBA?AV?$TCntPtr@$$CBUIEffect@GEL@@@Ofc@@AEBUIEffect@GEL@@0AEBVStyleResolveChain@23@AEBURect@7@AEBVPrimitiveUnitResolver@23@@Z`
- size: `313`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800fae30`
- `0x1800fbda0`
- `0x1800fbee0`
- `0x18013e010`
- `0x18013f760`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800faf62`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800faf62`
- `gfx!?Create@IEffectComposite@GEL@@SA?AV?$TCntPtr@UIEffectComposite@GEL@@@Ofc@@AEBUIEffect@2@0W4CompositeType@2@NNNNW4ColorSpace@2@@Z` at `0x1800faf0c`
- `gfx!?Create@IEffectComposite@GEL@@SA?AV?$TCntPtr@UIEffectComposite@GEL@@@Ofc@@AEBUIEffect@2@0W4CompositeType@2@NNNNW4ColorSpace@2@@Z` at `0x1800faf0c`
- `gfx!?Create@IEffectBlend@GEL@@SA?AV?$TCntPtr@UIEffectBlend@GEL@@@Ofc@@AEBUIEffect@2@0W4BlendMode@2@W4ColorSpace@2@@Z` at `0x1800faf18`
- `gfx!?Create@IEffectBlend@GEL@@SA?AV?$TCntPtr@UIEffectBlend@GEL@@@Ofc@@AEBUIEffect@2@0W4BlendMode@2@W4ColorSpace@2@@Z` at `0x1800faf18`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Mso::SVG::FeBlendRenderer::ApplyBinaryFilter(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5)
{
  _QWORD *v8; // rbx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int16 *v11; // rcx
  __int64 v12; // rax
  _QWORD *v13; // rax
  __int64 v15; // [rsp+70h] [rbp+8h] BYREF

  v8 = *(_QWORD **)(a1 + 16);
  if ( !v8 )
  {
    CrashWithRecovery(0x1E3C3843u, 0);
    JUMPOUT(0x1800FAF68LL);
  }
  _castguard_slow_path_check_user_handled(*v8, 9176, 2760);
  _castguard_slow_path_check_user_handled(*v8, 10280, 0);
  v9 = a5[1];
  v10 = *(_QWORD *)(v9 + 16);
  if ( v10 )
  {
    v11 = (__int16 *)(v10 + 1320);
  }
  else
  {
    v11 = &Mso::SVG::StyleMetaData<1>::initial;
    if ( *(_QWORD *)(v9 + 8) )
      v11 = (__int16 *)&Mso::SVG::StyleMetaData<1>::inherit;
  }
  if ( !*((_BYTE *)v11 + 1) )
  {
    if ( *a5 )
      v12 = Mso::SVG::StyleResolveChain::Get<1>();
    else
      v12 = Mso::SVG::StyleResolveChain::GetNormal<1>(a5, *(_QWORD *)(v9 + 8));
    v11 = (__int16 *)v12;
  }
  if ( *((_BYTE *)v8 + 488) == 5 )
    v13 = (_QWORD *)GEL::IEffectComposite::Create(&v15, a3, a4, 0, 0, 0, 0, 0, *(_BYTE *)v11);
  else
    v13 = (_QWORD *)GEL::IEffectBlend::Create(&v15, a3, a4);
  *a2 = *v13;
  *v13 = 0;
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
  return a2;
}

```

## disassembly

```asm
0x1800fae30  mov     [rsp+arg_8], rbx
0x1800fae35  mov     [rsp+arg_10], rbp
0x1800fae3a  mov     [rsp+arg_18], rsi
0x1800fae3f  push    rdi
0x1800fae40  sub     rsp, 60h
0x1800fae44  mov     rsi, r9
0x1800fae47  mov     rbp, r8
0x1800fae4a  mov     rdi, rdx
0x1800fae4d  mov     rbx, [rcx+10h]
0x1800fae51  test    rbx, rbx
0x1800fae54  jz      loc_1800FAF5B
0x1800fae5a  mov     edx, 23D8h
0x1800fae5f  mov     r8d, 0AC8h
0x1800fae65  mov     rcx, [rbx]
0x1800fae68  call    __castguard_slow_path_check_user_handled
0x1800fae6d  test    rbx, rbx
0x1800fae70  jz      short loc_1800FAE82
0x1800fae72  xor     r8d, r8d
0x1800fae75  mov     edx, 2828h
0x1800fae7a  mov     rcx, [rbx]
0x1800fae7d  call    __castguard_slow_path_check_user_handled
0x1800fae82  mov     r8, [rsp+68h+arg_20]
0x1800fae8a  mov     rdx, [r8+8]
0x1800fae8e  mov     rcx, [rdx+10h]
0x1800fae92  test    rcx, rcx
0x1800fae95  jz      short loc_1800FAEA0
0x1800fae97  add     rcx, 528h
0x1800fae9e  jmp     short loc_1800FAEB5
0x1800faea0  cmp     qword ptr [rdx+8], 0
0x1800faea5  lea     rcx, ?initial@?$StyleMetaData@$00@SVG@Mso@@2V?$optional@W4ColorSpace@GEL@@@std@@B; std::optional<GEL::ColorSpace> const Mso::SVG::StyleMetaData<1>::initial
0x1800faeac  jz      short loc_1800FAEB5
0x1800faeae  lea     rcx, ?inherit@?$StyleMetaData@$00@SVG@Mso@@2V?$optional@W4ColorSpace@GEL@@@std@@B; std::optional<GEL::ColorSpace> const Mso::SVG::StyleMetaData<1>::inherit
0x1800faeb5  mov     eax, 8
0x1800faeba  cmp     byte ptr [rcx+1], 0
0x1800faebe  jnz     short loc_1800FAEDE
0x1800faec0  mov     rcx, [r8]
0x1800faec3  test    rcx, rcx
0x1800faec6  jz      short loc_1800FAECF
0x1800faec8  call    ??$Get@$00@StyleResolveChain@SVG@Mso@@QEBAAEBW4ColorSpace@GEL@@XZ; Mso::SVG::StyleResolveChain::Get<1>(void)
0x1800faecd  jmp     short loc_1800FAEDB
0x1800faecf  mov     rdx, [rax+rdx]
0x1800faed3  mov     rcx, r8
0x1800faed6  call    ??$GetNormal@$00@StyleResolveChain@SVG@Mso@@AEBAAEBW4ColorSpace@GEL@@AEBVStyle@12@@Z; Mso::SVG::StyleResolveChain::GetNormal<1>(Mso::SVG::Style const &)
0x1800faedb  mov     rcx, rax
0x1800faede  mov     al, [rcx]
0x1800faee0  mov     r9b, [rbx+1E8h]
0x1800faee7  mov     r8, rsi
0x1800faeea  mov     rdx, rbp
0x1800faeed  lea     rcx, [rsp+68h+arg_0]
0x1800faef2  cmp     r9b, 5
0x1800faef6  jnz     short loc_1800FAF14
0x1800faef8  mov     [rsp+68h+var_28], al
0x1800faefc  xorps   xmm0, xmm0
0x1800faeff  movups  [rsp+68h+var_38], xmm0
0x1800faf04  movups  [rsp+68h+var_48], xmm0
0x1800faf09  xor     r9d, r9d
0x1800faf0c  call    cs:__imp_?Create@IEffectComposite@GEL@@SA?AV?$TCntPtr@UIEffectComposite@GEL@@@Ofc@@AEBUIEffect@2@0W4CompositeType@2@NNNNW4ColorSpace@2@@Z; GEL::IEffectComposite::Create(GEL::IEffect const &,GEL::IEffect const &,GEL::CompositeType,double,double,double,double,GEL::ColorSpace)
0x1800faf12  jmp     short loc_1800FAF1E
0x1800faf14  mov     byte ptr [rsp+68h+var_48], al
0x1800faf18  call    cs:__imp_?Create@IEffectBlend@GEL@@SA?AV?$TCntPtr@UIEffectBlend@GEL@@@Ofc@@AEBUIEffect@2@0W4BlendMode@2@W4ColorSpace@2@@Z; GEL::IEffectBlend::Create(GEL::IEffect const &,GEL::IEffect const &,GEL::BlendMode,GEL::ColorSpace)
0x1800faf1e  mov     rcx, [rax]
0x1800faf21  mov     [rdi], rcx
0x1800faf24  mov     qword ptr [rax], 0
0x1800faf2b  mov     rcx, [rsp+68h+arg_0]
0x1800faf30  test    rcx, rcx
0x1800faf33  jz      short loc_1800FAF42
0x1800faf35  mov     rax, [rcx]
0x1800faf38  mov     rax, [rax+8]
0x1800faf3c  call    cs:__guard_dispatch_icall_fptr
0x1800faf42  mov     rax, rdi
0x1800faf45  lea     r11, [rsp+68h+var_8]
0x1800faf4a  mov     rbx, [r11+18h]
0x1800faf4e  mov     rbp, [r11+20h]
0x1800faf52  mov     rsi, [r11+28h]
0x1800faf56  mov     rsp, r11
0x1800faf59  pop     rdi
0x1800faf5a  retn
0x1800faf5b  xor     edx, edx
0x1800faf5d  mov     ecx, 1E3C3843h
0x1800faf62  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
