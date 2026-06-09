# winrt::impl::consume_Windows_UI_Composition_ICompositionEffectSourceParameterFactory<winrt::Windows::UI::Composition::ICompositionEffectSourceParameterFactory>::Create(winrt::param::hstring const &)

- ea: `0x18001b260`
- end: `0x18001b2c9`
- name: `?Create@?$consume_Windows_UI_Composition_ICompositionEffectSourceParameterFactory@UICompositionEffectSourceParameterFactory@Composition@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001e9f4`

## callees

- `0x18001b260`
- `0x18002ad8c`
- `0x18002e010`

## string_xrefs

- `0x18001b26b`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\windows.ui.composition.h`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::consume_Windows_UI_Composition_ICompositionEffectSourceParameterFactory<winrt::Windows::UI::Composition::ICompositionEffectSourceParameterFactory>::Create(
        __int64 **a1,
        _QWORD *a2,
        __int64 *a3)
{
  __int64 *v3; // rcx
  __int64 v5; // rax
  __int64 v6; // rdx
  int v7; // eax
  int v9; // [rsp+28h] [rbp-20h] BYREF
  const char *v10; // [rsp+30h] [rbp-18h]
  __int64 v11; // [rsp+38h] [rbp-10h]
  __int64 v12; // [rsp+50h] [rbp+8h] BYREF

  v3 = *a1;
  v9 = 2061;
  v10 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\windows.ui.composition.h";
  v12 = 0;
  v5 = *v3;
  v6 = *a3;
  v11 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(v5 + 48))(v3, v6, &v12);
  if ( v7 < 0 )
    winrt::throw_hresult((unsigned int)v7, &v9);
  *a2 = v12;
  return a2;
}

```

## disassembly

```asm
0x18001b260  mov     r11, rsp
0x18001b263  push    rbx
0x18001b264  sub     rsp, 40h
0x18001b268  mov     rcx, [rcx]
0x18001b26b  lea     rax, aOnecoreuapInte; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18001b272  mov     r9, r8
0x18001b275  mov     [rsp+48h+var_20], 80Dh
0x18001b27d  mov     [r11-18h], rax
0x18001b281  lea     r8, [r11+8]
0x18001b285  mov     qword ptr [r11+8], 0
0x18001b28d  mov     rbx, rdx
0x18001b290  mov     rax, [rcx]
0x18001b293  mov     rdx, [r9]
0x18001b296  mov     qword ptr [r11-10h], 0
0x18001b29e  mov     rax, [rax+30h]
0x18001b2a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b2a7  test    eax, eax
0x18001b2a9  js      short loc_18001B2BC
0x18001b2ab  mov     rax, [rsp+48h+arg_0]
0x18001b2b0  mov     [rbx], rax
0x18001b2b3  mov     rax, rbx
0x18001b2b6  add     rsp, 40h
0x18001b2ba  pop     rbx
0x18001b2bb  retn
0x18001b2bc  lea     rdx, [rsp+48h+var_20]
0x18001b2c1  mov     ecx, eax
0x18001b2c3  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
