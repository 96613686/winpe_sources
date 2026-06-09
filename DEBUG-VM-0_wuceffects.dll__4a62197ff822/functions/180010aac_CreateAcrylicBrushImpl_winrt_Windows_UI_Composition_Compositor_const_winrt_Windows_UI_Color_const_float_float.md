# CreateAcrylicBrushImpl(winrt::Windows::UI::Composition::Compositor const &,winrt::Windows::UI::Color const &,float,float)

- ea: `0x180010aac`
- end: `0x180010c2a`
- name: `?CreateAcrylicBrushImpl@@YA?AUCompositionBrush@Composition@UI@Windows@winrt@@AEBUCompositor@2345@AEBUColor@345@MM@Z`
- size: `382`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800134f0`

## callees

- `0x180010aac`
- `0x180010ecc`
- `0x180012040`
- `0x1800120cc`
- `0x1800123fc`
- `0x18001e110`
- `0x18002ad8c`
- `0x18002e010`

## string_xrefs

- `0x180010b65`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\windows.ui.composition.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall CreateAcrylicBrushImpl(_QWORD *a1, __int64 a2, unsigned int *a3)
{
  void (__fastcall ***v5)(_QWORD, void *, __int64 *); // rcx
  __int64 v6; // r8
  __int64 v7; // rbx
  void (__fastcall ***v8)(_QWORD, void *, __int64 *); // rdi
  int v9; // eax
  __int64 v11; // [rsp+20h] [rbp-41h] BYREF
  __int64 v12; // [rsp+28h] [rbp-39h] BYREF
  __int64 v13; // [rsp+30h] [rbp-31h] BYREF
  __int64 v14; // [rsp+38h] [rbp-29h] BYREF
  _QWORD v15[3]; // [rsp+40h] [rbp-21h] BYREF
  _DWORD v16[4]; // [rsp+58h] [rbp-9h] BYREF
  const wchar_t *v17; // [rsp+68h] [rbp+7h]
  int v18; // [rsp+70h] [rbp+Fh] BYREF
  const char *v19; // [rsp+78h] [rbp+17h]
  __int64 v20; // [rsp+80h] [rbp+1Fh]

  CreateBackdropEffectGraph(&v14, a3);
  winrt::impl::consume_Windows_UI_Composition_ICompositor<winrt::Windows::UI::Composition::ICompositor>::CreateEffectFactory(
    a2,
    &v13,
    &v14);
  winrt::impl::consume_Windows_UI_Composition_ICompositionEffectFactory<winrt::Windows::UI::Composition::ICompositionEffectFactory>::CreateBrush(
    &v13,
    v15);
  v5 = *(void (__fastcall ****)(_QWORD, void *, __int64 *))winrt::impl::consume_Windows_UI_Composition_ICompositor3<winrt::Windows::UI::Composition::Compositor>::CreateHostBackdropBrush(
                                                             a2,
                                                             &v12);
  if ( v5 )
  {
    v11 = 0;
    (**v5)(v5, &winrt::impl::guid_v<winrt::Windows::UI::Composition::ICompositionBrush>, &v11);
    v6 = v11;
    v7 = v11;
  }
  else
  {
    v6 = 0;
    v7 = 0;
  }
  v11 = v6;
  v16[0] = 1;
  v16[1] = 8;
  v17 = L"Backdrop";
  v15[2] = v16;
  v8 = (void (__fastcall ***)(_QWORD, void *, __int64 *))v15[0];
  v18 = 1972;
  v19 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\windows.ui.composition.h";
  v20 = 0;
  v9 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *))(*(_QWORD *)v15[0] + 56LL))(v15[0], v16);
  if ( v9 < 0 )
    winrt::throw_hresult((unsigned int)v9, &v18);
  if ( v7 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v11);
  if ( v12 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v12);
  v12 = 0;
  (**v8)(v8, &winrt::impl::guid_v<winrt::Windows::UI::Composition::ICompositionBrush>, &v12);
  *a1 = v12;
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v15);
  if ( v13 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v13);
  if ( v14 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v14);
  return a1;
}

```

## disassembly

```asm
0x180010aac  push    rbp
0x180010aae  push    rbx
0x180010aaf  push    rsi
0x180010ab0  push    rdi
0x180010ab1  lea     rbp, [rsp-37h]
0x180010ab6  sub     rsp, 98h
0x180010abd  movaps  xmm2, xmm3
0x180010ac0  mov     rbx, rdx
0x180010ac3  mov     rsi, rcx
0x180010ac6  movss   xmm3, [rbp+4Fh+arg_20]
0x180010acb  mov     rdx, r8
0x180010ace  lea     rcx, [rbp+4Fh+var_78]
0x180010ad2  call    ?CreateBackdropEffectGraph@@YA?AUIGraphicsEffect@Effects@Graphics@Windows@winrt@@AEBUColor@UI@45@MM@Z; CreateBackdropEffectGraph(winrt::Windows::UI::Color const &,float,float)
0x180010ad7  nop
0x180010ad8  lea     r8, [rbp+4Fh+var_78]
0x180010adc  lea     rdx, [rbp+4Fh+var_80]
0x180010ae0  mov     rcx, rbx
0x180010ae3  call    ?CreateEffectFactory@?$consume_Windows_UI_Composition_ICompositor@UICompositor@Composition@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBUIGraphicsEffect@Effects@Graphics@Windows@3@@Z; winrt::impl::consume_Windows_UI_Composition_ICompositor<winrt::Windows::UI::Composition::ICompositor>::CreateEffectFactory(winrt::Windows::Graphics::Effects::IGraphicsEffect const &)
0x180010ae8  nop
0x180010ae9  lea     rdx, [rbp+4Fh+var_70]
0x180010aed  lea     rcx, [rbp+4Fh+var_80]
0x180010af1  call    ?CreateBrush@?$consume_Windows_UI_Composition_ICompositionEffectFactory@UICompositionEffectFactory@Composition@UI@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_UI_Composition_ICompositionEffectFactory<winrt::Windows::UI::Composition::ICompositionEffectFactory>::CreateBrush(void)
0x180010af6  nop
0x180010af7  lea     rdx, [rbp+4Fh+var_88]
0x180010afb  mov     rcx, rbx
0x180010afe  call    ?CreateHostBackdropBrush@?$consume_Windows_UI_Composition_ICompositor3@UCompositor@Composition@UI@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_UI_Composition_ICompositor3<winrt::Windows::UI::Composition::Compositor>::CreateHostBackdropBrush(void)
0x180010b03  nop
0x180010b04  mov     rcx, [rax]
0x180010b07  test    rcx, rcx
0x180010b0a  jz      loc_180010C14
0x180010b10  mov     [rbp+4Fh+var_90], 0
0x180010b18  mov     rax, [rcx]
0x180010b1b  lea     r8, [rbp+4Fh+var_90]
0x180010b1f  lea     rdx, ??$guid_v@UICompositionBrush@Composition@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Composition::ICompositionBrush>
0x180010b26  mov     rax, [rax]
0x180010b29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b2e  mov     r8, [rbp+4Fh+var_90]
0x180010b32  mov     rbx, r8
0x180010b35  mov     [rbp+4Fh+var_90], r8
0x180010b39  mov     [rbp+4Fh+var_58], 1
0x180010b40  mov     [rbp+4Fh+var_54], 8
0x180010b47  lea     rax, aBackdrop; "Backdrop"
0x180010b4e  mov     [rbp+4Fh+var_48], rax
0x180010b52  lea     rax, [rbp+4Fh+var_58]
0x180010b56  mov     [rbp+4Fh+var_60], rax
0x180010b5a  mov     rdi, [rbp+4Fh+var_70]
0x180010b5e  mov     [rbp+4Fh+var_40], 7B4h
0x180010b65  lea     rax, aOnecoreuapInte; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180010b6c  mov     [rbp+4Fh+var_38], rax
0x180010b70  mov     [rbp+4Fh+var_30], 0
0x180010b78  mov     rax, [rdi]
0x180010b7b  lea     rdx, [rbp+4Fh+var_58]
0x180010b7f  mov     rcx, rdi
0x180010b82  mov     rax, [rax+38h]
0x180010b86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b8b  test    eax, eax
0x180010b8d  js      loc_180010C1E
0x180010b93  test    rbx, rbx
0x180010b96  jz      short loc_180010BA2
0x180010b98  lea     rcx, [rbp+4Fh+var_90]
0x180010b9c  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180010ba1  nop
0x180010ba2  cmp     [rbp+4Fh+var_88], 0
0x180010ba7  jz      short loc_180010BB2
0x180010ba9  lea     rcx, [rbp+4Fh+var_88]
0x180010bad  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180010bb2  mov     [rbp+4Fh+var_88], 0
0x180010bba  mov     rax, [rdi]
0x180010bbd  lea     r8, [rbp+4Fh+var_88]
0x180010bc1  lea     rdx, ??$guid_v@UICompositionBrush@Composition@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Composition::ICompositionBrush>
0x180010bc8  mov     rcx, rdi
0x180010bcb  mov     rax, [rax]
0x180010bce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010bd3  mov     rax, [rbp+4Fh+var_88]
0x180010bd7  mov     [rsi], rax
0x180010bda  lea     rcx, [rbp+4Fh+var_70]
0x180010bde  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180010be3  nop
0x180010be4  cmp     [rbp+4Fh+var_80], 0
0x180010be9  jz      short loc_180010BF5
0x180010beb  lea     rcx, [rbp+4Fh+var_80]
0x180010bef  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180010bf4  nop
0x180010bf5  cmp     [rbp+4Fh+var_78], 0
0x180010bfa  jz      short loc_180010C05
0x180010bfc  lea     rcx, [rbp+4Fh+var_78]
0x180010c00  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180010c05  mov     rax, rsi
0x180010c08  add     rsp, 98h
0x180010c0f  pop     rdi
0x180010c10  pop     rsi
0x180010c11  pop     rbx
0x180010c12  pop     rbp
0x180010c13  retn
0x180010c14  xor     r8d, r8d
0x180010c17  xor     ebx, ebx
0x180010c19  jmp     loc_180010B35
0x180010c1e  lea     rdx, [rbp+4Fh+var_40]
0x180010c22  mov     ecx, eax
0x180010c24  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
