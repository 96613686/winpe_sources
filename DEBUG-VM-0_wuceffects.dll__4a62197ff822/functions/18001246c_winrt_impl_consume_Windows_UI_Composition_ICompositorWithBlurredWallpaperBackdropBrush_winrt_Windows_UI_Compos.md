# winrt::impl::consume_Windows_UI_Composition_ICompositorWithBlurredWallpaperBackdropBrush<winrt::Windows::UI::Composition::Compositor>::TryCreateBlurredWallpaperBackdropBrush(void)

- ea: `0x18001246c`
- end: `0x180012538`
- name: `?TryCreateBlurredWallpaperBackdropBrush@?$consume_Windows_UI_Composition_ICompositorWithBlurredWallpaperBackdropBrush@UCompositor@Composition@UI@Windows@winrt@@@impl@winrt@@QEBA@XZ`
- size: `204`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180010c58`

## callees

- `0x180012040`
- `0x18001246c`
- `0x18002ad8c`
- `0x18002e010`

## string_xrefs

- `0x180012499`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\windows.ui.composition.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall winrt::impl::consume_Windows_UI_Composition_ICompositorWithBlurredWallpaperBackdropBrush<winrt::Windows::UI::Composition::Compositor>::TryCreateBlurredWallpaperBackdropBrush(
        __int64 *a1,
        _QWORD *a2)
{
  __int64 v3; // rcx
  int v4; // eax
  int v5; // eax
  int v7; // [rsp+28h] [rbp-18h] BYREF
  const char *v8; // [rsp+30h] [rbp-10h]
  __int64 v9; // [rsp+38h] [rbp-8h]
  __int64 v10; // [rsp+50h] [rbp+10h] BYREF
  __int64 v11; // [rsp+60h] [rbp+20h] BYREF

  v11 = 0;
  v3 = *a1;
  if ( v3 )
  {
    v10 = 0;
    v4 = (**(__int64 (__fastcall ***)(__int64, void *, __int64 *))v3)(
           v3,
           &winrt::impl::guid_v<winrt::Windows::UI::Composition::ICompositorWithBlurredWallpaperBackdropBrush>,
           &v10);
    v3 = v10;
  }
  else
  {
    v4 = 0;
    v10 = 0;
  }
  v7 = 8898;
  v8 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\windows.ui.composition.h";
  v9 = 0;
  if ( v4 < 0 )
    winrt::throw_hresult((unsigned int)v4, &v7);
  v7 = 8900;
  v8 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\windows.ui.composition.h";
  v9 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v3 + 48LL))(v3, &v11);
  if ( v5 < 0 )
    winrt::throw_hresult((unsigned int)v5, &v7);
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v10);
  *a2 = v11;
  return a2;
}

```

## disassembly

```asm
0x18001246c  mov     [rsp-8+arg_8], rbx
0x180012471  push    rbp
0x180012472  mov     rbp, rsp
0x180012475  sub     rsp, 40h
0x180012479  mov     rbx, rdx
0x18001247c  mov     [rbp+arg_10], 0
0x180012484  mov     rcx, [rcx]
0x180012487  test    rcx, rcx
0x18001248a  jnz     short loc_1800124F5
0x18001248c  xor     eax, eax
0x18001248e  mov     [rbp+arg_0], rax
0x180012492  mov     [rbp+var_18], 22C2h
0x180012499  lea     rdx, aOnecoreuapInte; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x1800124a0  mov     [rbp+var_10], rdx
0x1800124a4  mov     [rbp+var_8], 0
0x1800124ac  test    eax, eax
0x1800124ae  js      short loc_180012520
0x1800124b0  mov     [rbp+var_18], 22C4h
0x1800124b7  mov     [rbp+var_10], rdx
0x1800124bb  mov     [rbp+var_8], 0
0x1800124c3  mov     rax, [rcx]
0x1800124c6  lea     rdx, [rbp+arg_10]
0x1800124ca  mov     rax, [rax+30h]
0x1800124ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124d3  test    eax, eax
0x1800124d5  js      short loc_18001252C
0x1800124d7  lea     rcx, [rbp+arg_0]
0x1800124db  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800124e0  mov     rax, [rbp+arg_10]
0x1800124e4  mov     [rbx], rax
0x1800124e7  mov     rax, rbx
0x1800124ea  mov     rbx, [rsp+40h+arg_8]
0x1800124ef  add     rsp, 40h
0x1800124f3  pop     rbp
0x1800124f4  retn
0x1800124f5  mov     [rbp+arg_0], 0
0x1800124fd  mov     rax, [rcx]
0x180012500  lea     r8, [rbp+arg_0]
0x180012504  lea     rdx, ??$guid_v@UICompositorWithBlurredWallpaperBackdropBrush@Composition@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Composition::ICompositorWithBlurredWallpaperBackdropBrush>
0x18001250b  mov     rax, [rax]
0x18001250e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012513  mov     rcx, [rbp+arg_0]
0x180012517  mov     [rbp+arg_0], rcx
0x18001251b  jmp     loc_180012492
0x180012520  lea     rdx, [rbp+var_18]
0x180012524  mov     ecx, eax
0x180012526  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001252c  lea     rdx, [rbp+var_18]
0x180012530  mov     ecx, eax
0x180012532  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
