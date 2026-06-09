# winrt::impl::consume_Windows_UI_Composition_ICompositionEffectFactory<winrt::Windows::UI::Composition::ICompositionEffectFactory>::CreateBrush(void)

- ea: `0x1800120cc`
- end: `0x18001212f`
- name: `?CreateBrush@?$consume_Windows_UI_Composition_ICompositionEffectFactory@UICompositionEffectFactory@Composition@UI@Windows@winrt@@@impl@winrt@@QEBA@XZ`
- size: `99`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180010aac`
- `0x180010c58`
- `0x180011590`

## callees

- `0x1800120cc`
- `0x18002ad8c`
- `0x18002e010`

## string_xrefs

- `0x1800120d7`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\windows.ui.composition.h`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::consume_Windows_UI_Composition_ICompositionEffectFactory<winrt::Windows::UI::Composition::ICompositionEffectFactory>::CreateBrush(
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
  v7 = 1989;
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
0x1800120cc  mov     r11, rsp
0x1800120cf  push    rbx
0x1800120d0  sub     rsp, 40h
0x1800120d4  mov     rcx, [rcx]
0x1800120d7  lea     rax, aOnecoreuapInte; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x1800120de  mov     [rsp+48h+var_20], 7C5h
0x1800120e6  mov     rbx, rdx
0x1800120e9  mov     [r11-18h], rax
0x1800120ed  lea     rdx, [r11+8]
0x1800120f1  mov     qword ptr [r11+8], 0
0x1800120f9  mov     rax, [rcx]
0x1800120fc  mov     qword ptr [r11-10h], 0
0x180012104  mov     rax, [rax+30h]
0x180012108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001210d  test    eax, eax
0x18001210f  js      short loc_180012122
0x180012111  mov     rax, [rsp+48h+arg_0]
0x180012116  mov     [rbx], rax
0x180012119  mov     rax, rbx
0x18001211c  add     rsp, 40h
0x180012120  pop     rbx
0x180012121  retn
0x180012122  lea     rdx, [rsp+48h+var_20]
0x180012127  mov     ecx, eax
0x180012129  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
