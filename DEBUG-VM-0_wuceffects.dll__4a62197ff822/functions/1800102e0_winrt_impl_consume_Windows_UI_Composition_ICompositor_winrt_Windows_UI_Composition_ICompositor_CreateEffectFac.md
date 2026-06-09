# winrt::impl::consume_Windows_UI_Composition_ICompositor<winrt::Windows::UI::Composition::ICompositor>::CreateEffectFactory(winrt::Windows::Graphics::Effects::IGraphicsEffect const &,winrt::param::iterable<winrt::hstring> const &)

- ea: `0x1800102e0`
- end: `0x180010351`
- name: `?CreateEffectFactory@?$consume_Windows_UI_Composition_ICompositor@UICompositor@Composition@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBUIGraphicsEffect@Effects@Graphics@Windows@3@AEBU?$iterable@Uhstring@winrt@@@param@3@@Z`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180010480`

## callees

- `0x1800102e0`
- `0x18002ad8c`
- `0x18002e010`

## string_xrefs

- `0x1800102e9`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\windows.ui.composition.h`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::consume_Windows_UI_Composition_ICompositor<winrt::Windows::UI::Composition::ICompositor>::CreateEffectFactory(
        __int64 **a1,
        _QWORD *a2,
        __int64 *a3,
        __int64 *a4)
{
  __int64 *v4; // rcx
  __int64 v7; // rax
  __int64 v8; // r8
  __int64 v9; // rdx
  int v10; // eax
  int v12; // [rsp+38h] [rbp-20h] BYREF
  const char *v13; // [rsp+40h] [rbp-18h]
  __int64 v14; // [rsp+48h] [rbp-10h]
  __int64 v15; // [rsp+60h] [rbp+8h] BYREF

  v4 = *a1;
  v13 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\windows.ui.composition.h";
  v15 = 0;
  v12 = 7631;
  v7 = *v4;
  v8 = *a4;
  v9 = *a3;
  v14 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, __int64 *))(v7 + 96))(v4, v9, v8, &v15);
  if ( v10 < 0 )
    winrt::throw_hresult((unsigned int)v10, &v12);
  *a2 = v15;
  return a2;
}

```

## disassembly

```asm
0x1800102e0  push    rbx
0x1800102e2  sub     rsp, 50h
0x1800102e6  mov     rcx, [rcx]
0x1800102e9  lea     rax, aOnecoreuapInte; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x1800102f0  mov     [rsp+58h+var_18], rax
0x1800102f5  mov     r10, r9
0x1800102f8  mov     r11, r8
0x1800102fb  mov     [rsp+58h+arg_0], 0
0x180010304  mov     rbx, rdx
0x180010307  mov     [rsp+58h+var_20], 1DCFh
0x18001030f  mov     rax, [rcx]
0x180010312  lea     r9, [rsp+58h+arg_0]
0x180010317  mov     r8, [r10]
0x18001031a  mov     rdx, [r11]
0x18001031d  mov     [rsp+58h+var_10], 0
0x180010326  mov     rax, [rax+60h]
0x18001032a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001032f  test    eax, eax
0x180010331  js      short loc_180010344
0x180010333  mov     rax, [rsp+58h+arg_0]
0x180010338  mov     [rbx], rax
0x18001033b  mov     rax, rbx
0x18001033e  add     rsp, 50h
0x180010342  pop     rbx
0x180010343  retn
0x180010344  lea     rdx, [rsp+58h+var_20]
0x180010349  mov     ecx, eax
0x18001034b  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
