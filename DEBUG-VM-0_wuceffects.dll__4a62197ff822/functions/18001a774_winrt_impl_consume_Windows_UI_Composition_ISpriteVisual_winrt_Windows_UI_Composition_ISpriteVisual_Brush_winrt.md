# winrt::impl::consume_Windows_UI_Composition_ISpriteVisual<winrt::Windows::UI::Composition::ISpriteVisual>::Brush(winrt::Windows::UI::Composition::CompositionBrush const &)

- ea: `0x18001a774`
- end: `0x18001a7bd`
- name: `?Brush@?$consume_Windows_UI_Composition_ISpriteVisual@UISpriteVisual@Composition@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBUCompositionBrush@Composition@UI@Windows@3@@Z`
- size: `73`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001a750`

## callees

- `0x18001a774`
- `0x18002ad8c`
- `0x18002e010`

## string_xrefs

- `0x18001a77b`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\windows.ui.composition.h`

## pseudocode

```c
__int64 __fastcall winrt::impl::consume_Windows_UI_Composition_ISpriteVisual<winrt::Windows::UI::Composition::ISpriteVisual>::Brush(
        __int64 **a1,
        __int64 *a2)
{
  __int64 *v2; // rcx
  __int64 v3; // rdx
  __int64 v4; // rax
  __int64 result; // rax
  int v6; // [rsp+20h] [rbp-28h] BYREF
  const char *v7; // [rsp+28h] [rbp-20h]
  __int64 v8; // [rsp+30h] [rbp-18h]

  v2 = *a1;
  v3 = *a2;
  v7 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\windows.ui.composition.h";
  v6 = 12270;
  v4 = *v2;
  v8 = 0;
  result = (*(__int64 (__fastcall **)(__int64 *, __int64))(v4 + 56))(v2, v3);
  if ( (int)result < 0 )
    winrt::throw_hresult((unsigned int)result, &v6);
  return result;
}

```

## disassembly

```asm
0x18001a774  sub     rsp, 48h
0x18001a778  mov     rcx, [rcx]
0x18001a77b  lea     rax, aOnecoreuapInte; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18001a782  mov     rdx, [rdx]
0x18001a785  mov     [rsp+48h+var_20], rax
0x18001a78a  mov     [rsp+48h+var_28], 2FEEh
0x18001a792  mov     rax, [rcx]
0x18001a795  mov     [rsp+48h+var_18], 0
0x18001a79e  mov     rax, [rax+38h]
0x18001a7a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a7a7  test    eax, eax
0x18001a7a9  js      short loc_18001A7B0
0x18001a7ab  add     rsp, 48h
0x18001a7af  retn
0x18001a7b0  lea     rdx, [rsp+48h+var_28]
0x18001a7b5  mov     ecx, eax
0x18001a7b7  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
