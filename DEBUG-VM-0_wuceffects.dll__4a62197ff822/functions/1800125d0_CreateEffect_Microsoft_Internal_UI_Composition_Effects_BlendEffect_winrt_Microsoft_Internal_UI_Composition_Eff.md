# CreateEffect<Microsoft::Internal::UI::Composition::Effects::BlendEffect,winrt::Microsoft::Internal::UI::Composition::Effects::BlendEffect>(void)

- ea: `0x1800125d0`
- end: `0x180012633`
- name: `??$CreateEffect@VBlendEffect@Effects@Composition@UI@Internal@Microsoft@@U123456winrt@@@@YA?AUBlendEffect@Effects@Composition@UI@Internal@Microsoft@winrt@@XZ`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180010ecc`

## callees

- `0x1800125d0`
- `0x18001263c`
- `0x180012654`
- `0x1800126d8`
- `0x18001eaa0`

## string_xrefs

- `0x1800125f8`: `onecoreuap\windows\dwm\effects\compiler\global\materialbrushfactory.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CreateEffect<Microsoft::Internal::UI::Composition::Effects::BlendEffect,winrt::Microsoft::Internal::UI::Composition::Effects::BlendEffect>(
        __int64 a1)
{
  int v2; // eax
  int v4; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v6; // [rsp+48h] [rbp+10h] BYREF

  v6 = 0;
  v2 = Microsoft::WRL::Details::MakeAndInitialize<Microsoft::Internal::UI::Composition::Effects::BlendEffect,Microsoft::Internal::UI::Composition::Effects::BlendEffect,>(&v6);
  if ( v2 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1D,
      (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\global\\materialbrushfactory.cpp",
      (const char *)(unsigned int)v2,
      v4);
  winrt::impl::as<winrt::Microsoft::Internal::UI::Composition::Effects::BlendEffect,Microsoft::Internal::UI::Composition::Effects::BlendEffect,0>(
    a1,
    v6);
  if ( v6 )
    winrt::com_ptr<Microsoft::Internal::UI::Composition::Effects::BlendEffect>::unconditional_release_ref(&v6);
  return a1;
}

```

## disassembly

```asm
0x1800125d0  push    rdi
0x1800125d2  sub     rsp, 30h
0x1800125d6  mov     rdi, rcx
0x1800125d9  mov     [rsp+38h+arg_8], 0
0x1800125e2  lea     rcx, [rsp+38h+arg_8]
0x1800125e7  call    ??$MakeAndInitialize@VBlendEffect@Effects@Composition@UI@Internal@Microsoft@@V123456@$$V@Details@WRL@Microsoft@@YAJPEAPEAVBlendEffect@Effects@Composition@UI@Internal@2@@Z; Microsoft::WRL::Details::MakeAndInitialize<Microsoft::Internal::UI::Composition::Effects::BlendEffect,Microsoft::Internal::UI::Composition::Effects::BlendEffect,>(Microsoft::Internal::UI::Composition::Effects::BlendEffect * *)
0x1800125ec  mov     rcx, [rsp+38h]; this
0x1800125f1  test    eax, eax
0x1800125f3  jns     short loc_18001260A
0x1800125f5  mov     r9d, eax; char *
0x1800125f8  lea     r8, aOnecoreuapWind_2; "onecoreuap\\windows\\dwm\\effects\\comp"...
0x1800125ff  mov     edx, 1Dh; void *
0x180012604  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001260a  mov     rdx, [rsp+38h+arg_8]
0x18001260f  mov     rcx, rdi
0x180012612  call    ??$as@UBlendEffect@Effects@Composition@UI@Internal@Microsoft@winrt@@V123456@$0A@@impl@winrt@@YA?AUBlendEffect@Effects@Composition@UI@Internal@Microsoft@1@PEAV234567@@Z; winrt::impl::as<winrt::Microsoft::Internal::UI::Composition::Effects::BlendEffect,Microsoft::Internal::UI::Composition::Effects::BlendEffect,0>(Microsoft::Internal::UI::Composition::Effects::BlendEffect *)
0x180012617  nop
0x180012618  cmp     [rsp+38h+arg_8], 0
0x18001261e  jz      short loc_18001262A
0x180012620  lea     rcx, [rsp+38h+arg_8]
0x180012625  call    ?unconditional_release_ref@?$com_ptr@VBlendEffect@Effects@Composition@UI@Internal@Microsoft@@@winrt@@AEAAXXZ; winrt::com_ptr<Microsoft::Internal::UI::Composition::Effects::BlendEffect>::unconditional_release_ref(void)
0x18001262a  mov     rax, rdi
0x18001262d  add     rsp, 30h
0x180012631  pop     rdi
0x180012632  retn
```
