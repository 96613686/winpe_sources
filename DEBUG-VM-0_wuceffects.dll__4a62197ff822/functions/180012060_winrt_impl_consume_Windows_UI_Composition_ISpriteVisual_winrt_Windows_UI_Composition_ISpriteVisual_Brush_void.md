# winrt::impl::consume_Windows_UI_Composition_ISpriteVisual<winrt::Windows::UI::Composition::ISpriteVisual>::Brush(void)

- ea: `0x180012060`
- end: `0x1800120c3`
- name: `?Brush@?$consume_Windows_UI_Composition_ISpriteVisual@UISpriteVisual@Composition@UI@Windows@winrt@@@impl@winrt@@QEBA@XZ`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180011590`

## callees

- `0x180012060`
- `0x18002ad8c`
- `0x18002e010`

## string_xrefs

- `0x18001206b`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\windows.ui.composition.h`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::consume_Windows_UI_Composition_ISpriteVisual<winrt::Windows::UI::Composition::ISpriteVisual>::Brush(
        __int64 **a1,
        _QWORD *a2)
{
  __int64 *v2; // rcx
  __int64 v4; // rax
  int v5; // eax
  int v7; // [rsp+28h] [rbp-20h] BYREF
  const char *v8; // [rsp+30h] [rbp-18h]
  __int64 v9; // [rsp+38h] [rbp-10h]
  __int64 v10; // [rsp+50h] [rbp+8h] BYREF

  v2 = *a1;
  v7 = 12253;
  v8 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\windows.ui.composition.h";
  v10 = 0;
  v4 = *v2;
  v9 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v4 + 48))(v2, &v10);
  if ( v5 < 0 )
    winrt::throw_hresult((unsigned int)v5, &v7);
  *a2 = v10;
  return a2;
}

```

## disassembly

```asm
0x180012060  mov     r11, rsp
0x180012063  push    rbx
0x180012064  sub     rsp, 40h
0x180012068  mov     rcx, [rcx]
0x18001206b  lea     rax, aOnecoreuapInte; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180012072  mov     [rsp+48h+var_20], 2FDDh
0x18001207a  mov     rbx, rdx
0x18001207d  mov     [r11-18h], rax
0x180012081  lea     rdx, [r11+8]
0x180012085  mov     qword ptr [r11+8], 0
0x18001208d  mov     rax, [rcx]
0x180012090  mov     qword ptr [r11-10h], 0
0x180012098  mov     rax, [rax+30h]
0x18001209c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120a1  test    eax, eax
0x1800120a3  js      short loc_1800120B6
0x1800120a5  mov     rax, [rsp+48h+arg_0]
0x1800120aa  mov     [rbx], rax
0x1800120ad  mov     rax, rbx
0x1800120b0  add     rsp, 40h
0x1800120b4  pop     rbx
0x1800120b5  retn
0x1800120b6  lea     rdx, [rsp+48h+var_20]
0x1800120bb  mov     ecx, eax
0x1800120bd  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
