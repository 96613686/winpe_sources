# CreateEffect<Microsoft::Internal::UI::Composition::Effects::CrossFadeEffect,winrt::Microsoft::Internal::UI::Composition::Effects::CrossFadeEffect>(void)

- ea: `0x180013664`
- end: `0x1800136c7`
- name: `??$CreateEffect@VCrossFadeEffect@Effects@Composition@UI@Internal@Microsoft@@U123456winrt@@@@YA?AUCrossFadeEffect@Effects@Composition@UI@Internal@Microsoft@winrt@@XZ`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180010480`

## callees

- `0x1800129c8`
- `0x180013664`
- `0x1800136d0`
- `0x18001374c`
- `0x18001eaa0`

## string_xrefs

- `0x18001368c`: `onecoreuap\windows\dwm\effects\compiler\global\materialbrushfactory.cpp`

## pseudocode

```c
__int64 __fastcall CreateEffect<Microsoft::Internal::UI::Composition::Effects::CrossFadeEffect,winrt::Microsoft::Internal::UI::Composition::Effects::CrossFadeEffect>(
        __int64 a1)
{
  int v2; // eax
  int v4; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v6; // [rsp+48h] [rbp+10h] BYREF

  v6 = 0;
  v2 = Microsoft::WRL::Details::MakeAndInitialize<Microsoft::Internal::UI::Composition::Effects::CrossFadeEffect,Microsoft::Internal::UI::Composition::Effects::CrossFadeEffect,>(&v6);
  if ( v2 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1D,
      (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\global\\materialbrushfactory.cpp",
      (const char *)(unsigned int)v2,
      v4);
  winrt::impl::as<winrt::Microsoft::Internal::UI::Composition::Effects::CrossFadeEffect,Microsoft::Internal::UI::Composition::Effects::CrossFadeEffect,0>(
    a1,
    v6);
  if ( v6 )
    winrt::com_ptr<Microsoft::Internal::UI::Composition::Effects::CrossFadeEffect>::unconditional_release_ref(&v6);
  return a1;
}

```

## disassembly

```asm
0x180013664  push    rdi
0x180013666  sub     rsp, 30h
0x18001366a  mov     rdi, rcx
0x18001366d  mov     [rsp+38h+arg_8], 0
0x180013676  lea     rcx, [rsp+38h+arg_8]
0x18001367b  call    ??$MakeAndInitialize@VCrossFadeEffect@Effects@Composition@UI@Internal@Microsoft@@V123456@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCrossFadeEffect@Effects@Composition@UI@Internal@2@@Z; Microsoft::WRL::Details::MakeAndInitialize<Microsoft::Internal::UI::Composition::Effects::CrossFadeEffect,Microsoft::Internal::UI::Composition::Effects::CrossFadeEffect,>(Microsoft::Internal::UI::Composition::Effects::CrossFadeEffect * *)
0x180013680  mov     rcx, [rsp+38h]; this
0x180013685  test    eax, eax
0x180013687  jns     short loc_18001369E
0x180013689  mov     r9d, eax; char *
0x18001368c  lea     r8, aOnecoreuapWind_2; "onecoreuap\\windows\\dwm\\effects\\comp"...
0x180013693  mov     edx, 1Dh; void *
0x180013698  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001369e  mov     rdx, [rsp+38h+arg_8]
0x1800136a3  mov     rcx, rdi
0x1800136a6  call    ??$as@UCrossFadeEffect@Effects@Composition@UI@Internal@Microsoft@winrt@@V123456@$0A@@impl@winrt@@YA?AUCrossFadeEffect@Effects@Composition@UI@Internal@Microsoft@1@PEAV234567@@Z; winrt::impl::as<winrt::Microsoft::Internal::UI::Composition::Effects::CrossFadeEffect,Microsoft::Internal::UI::Composition::Effects::CrossFadeEffect,0>(Microsoft::Internal::UI::Composition::Effects::CrossFadeEffect *)
0x1800136ab  nop
0x1800136ac  cmp     [rsp+38h+arg_8], 0
0x1800136b2  jz      short loc_1800136BE
0x1800136b4  lea     rcx, [rsp+38h+arg_8]
0x1800136b9  call    ?unconditional_release_ref@?$com_ptr@VCrossFadeEffect@Effects@Composition@UI@Internal@Microsoft@@@winrt@@AEAAXXZ; winrt::com_ptr<Microsoft::Internal::UI::Composition::Effects::CrossFadeEffect>::unconditional_release_ref(void)
0x1800136be  mov     rax, rdi
0x1800136c1  add     rsp, 30h
0x1800136c5  pop     rdi
0x1800136c6  retn
```
