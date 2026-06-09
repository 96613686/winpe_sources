# CrossFadeToNewBrush

- ea: `0x180011590`
- end: `0x180012038`
- name: `CrossFadeToNewBrush`
- size: `2728`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x180006410`
- `0x180011590`
- `0x180012040`
- `0x180012060`
- `0x1800120cc`
- `0x180012138`
- `0x1800121a4`
- `0x1800121f4`
- `0x180012268`
- `0x1800122d4`
- `0x180012324`
- `0x18001e040`
- `0x18001f058`
- `0x18002ad8c`
- `0x18002e010`

## string_xrefs

- `0x1800116e5`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\windows.ui.composition.h`
- `0x180011ce0`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\windows.ui.composition.h`
- `0x180011ec5`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\windows.ui.composition.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall CrossFadeToNewBrush(__int64 a1, const char *a2, __int64 a3, unsigned int a4)
{
  __int64 v4; // r12
  _QWORD *v8; // r13
  __int64 v9; // r14
  __int64 v10; // rdi
  __int64 v11; // rdi
  _QWORD *v12; // rdx
  int v13; // eax
  _QWORD *v14; // rcx
  int v15; // eax
  int v16; // eax
  int v17; // eax
  _QWORD *v18; // rbx
  int v19; // eax
  _QWORD *v20; // rbx
  int v21; // eax
  int v22; // eax
  _QWORD *v23; // rcx
  int v24; // eax
  __int64 v25; // rax
  char v26; // bl
  _QWORD *v27; // rdx
  int v28; // eax
  _QWORD *v29; // rcx
  int v30; // eax
  _QWORD *v31; // rdx
  _QWORD *v32; // rbx
  int v33; // eax
  __int64 *v34; // rbx
  _QWORD *v35; // rdx
  int v36; // eax
  _QWORD *v37; // rcx
  int v38; // eax
  int v39; // eax
  __int64 *v40; // rax
  __int64 *v41; // rbx
  int v42; // eax
  const char *v43; // r9
  __int64 result; // rax
  __int64 v45; // rcx
  const char *v46; // rcx
  int v47; // eax
  int v48; // eax
  __int64 v49; // [rsp+30h] [rbp-B8h] BYREF
  const char *v50; // [rsp+38h] [rbp-B0h]
  __int64 v51; // [rsp+40h] [rbp-A8h]
  __int64 (__fastcall ***v52)(_QWORD, void *, _QWORD **); // [rsp+48h] [rbp-A0h] BYREF
  _QWORD *v53; // [rsp+50h] [rbp-98h] BYREF
  _QWORD v54[2]; // [rsp+58h] [rbp-90h] BYREF
  const wchar_t *v55; // [rsp+68h] [rbp-80h]
  __int64 v56; // [rsp+70h] [rbp-78h] BYREF
  __int64 v57; // [rsp+78h] [rbp-70h] BYREF
  __int64 *v58; // [rsp+80h] [rbp-68h] BYREF
  __int64 v59; // [rsp+88h] [rbp-60h] BYREF
  __int64 v60; // [rsp+90h] [rbp-58h] BYREF
  __int64 v61; // [rsp+98h] [rbp-50h] BYREF
  void (__fastcall ***v62)(_QWORD, void *, _QWORD **); // [rsp+A0h] [rbp-48h] BYREF
  __int64 v63; // [rsp+A8h] [rbp-40h] BYREF
  _QWORD v64[2]; // [rsp+B0h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]
  _QWORD *v66; // [rsp+F0h] [rbp+8h] BYREF

  v4 = a4;
  v8 = 0;
  v9 = 0;
  v60 = 0;
  v10 = 0;
  if ( a1 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
    v9 = a1;
    v60 = a1;
    v10 = a1;
  }
  try
  {
    winrt::impl::consume_Windows_UI_Composition_ISpriteVisual<winrt::Windows::UI::Composition::ISpriteVisual>::Brush();
    if ( a2 )
    {
      (*(void (__fastcall **)(const char *))(*(_QWORD *)a2 + 8LL))(a2);
      v64[0] = a2;
      if ( v52 )
      {
        v11 = 0;
        v63 = 0;
        if ( a3 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)a3 + 8LL))(a3);
          v11 = a3;
          v63 = a3;
        }
        winrt::impl::consume_Windows_UI_Composition_ICompositionObject<winrt::Windows::UI::Composition::CompositionBrush>::Compositor(
          &v52,
          &v59);
        winrt::impl::consume_Windows_UI_Composition_ICompositionEffectFactory<winrt::Windows::UI::Composition::ICompositionEffectFactory>::CreateBrush(
          &v63,
          &v56);
        v54[0] = 0x900000001LL;
        v55 = L"Crossfade";
        v12 = v54;
        v53 = v54;
        v66 = 0;
        if ( v56 )
        {
          v13 = (**(__int64 (__fastcall ***)(__int64, void *, _QWORD **))v56)(
                  v56,
                  &winrt::impl::guid_v<winrt::Windows::UI::Composition::ICompositionObject2>,
                  &v66);
          v14 = v66;
          v12 = v53;
        }
        else
        {
          v13 = 0;
          v14 = 0;
        }
        LODWORD(v49) = 4475;
        v50 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\windows.ui.composition.h";
        v51 = 0;
        if ( v13 < 0 )
          winrt::throw_hresult((unsigned int)v13, &v49);
        LODWORD(v49) = 4477;
        v50 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\windows.ui.composition.h";
        v51 = 0;
        v15 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD *))(*v14 + 56LL))(v14, v12);
        if ( v15 < 0 )
          winrt::throw_hresult((unsigned int)v15, &v49);
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v66);
        v54[0] = 0x700000001LL;
        v55 = L"source1";
        v53 = v54;
        LODWORD(v49) = 1972;
        v50 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\windows.ui.composition.h";
        v51 = 0;
        v16 = (*(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD))(*(_QWORD *)v56 + 56LL))(v56, v54, v52);
        if ( v16 < 0 )
          winrt::throw_hresult((unsigned int)v16, &v49);
        v54[0] = 0x700000001LL;
        v55 = L"source2";
        v53 = v54;
        LODWORD(v49) = 1972;
        v50 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\windows.ui.composition.h";
        v51 = 0;
        v17 = (*(__int64 (__fastcall **)(__int64, _QWORD *, const char *))(*(_QWORD *)v56 + 56LL))(v56, v54, a2);
        if ( v17 < 0 )
          winrt::throw_hresult((unsigned int)v17, &v49);
        winrt::impl::consume_Windows_UI_Composition_ICompositor<winrt::Windows::UI::Composition::ICompositor>::CreateScalarKeyFrameAnimation(
          &v59,
          &v57);
        winrt::impl::consume_Windows_UI_Composition_ICompositor<winrt::Windows::UI::Composition::ICompositor>::CreateLinearEasingFunction(
          &v59,
          &v62);
        v66 = 0;
        if ( v62 )
        {
          (**v62)(v62, &winrt::impl::guid_v<winrt::Windows::UI::Composition::ICompositionEasingFunction>, &v66);
          v18 = v66;
        }
        else
        {
          v18 = 0;
        }
        LODWORD(v49) = 11316;
        v50 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\windows.ui.composition.h";
        v51 = 0;
        v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v57 + 56LL))(v57);
        if ( v19 < 0 )
          winrt::throw_hresult((unsigned int)v19, &v49);
        if ( v18 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v66);
        v66 = 0;
        if ( v62 )
        {
          (**v62)(v62, &winrt::impl::guid_v<winrt::Windows::UI::Composition::ICompositionEasingFunction>, &v66);
          v20 = v66;
        }
        else
        {
          v20 = 0;
        }
        LODWORD(v49) = 11316;
        v50 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\windows.ui.composition.h";
        v51 = 0;
        v21 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v57 + 56LL))(v57);
        if ( v21 < 0 )
          winrt::throw_hresult((unsigned int)v21, &v49);
        if ( v20 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v66);
        v66 = 0;
        if ( v57 )
        {
          v22 = (**(__int64 (__fastcall ***)(__int64, void *, _QWORD **))v57)(
                  v57,
                  &winrt::impl::guid_v<winrt::Windows::UI::Composition::IKeyFrameAnimation>,
                  &v66);
          v23 = v66;
        }
        else
        {
          v22 = 0;
          v23 = 0;
        }
        LODWORD(v49) = 10157;
        v50 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\windows.ui.composition.h";
        v51 = 0;
        if ( v22 < 0 )
          winrt::throw_hresult((unsigned int)v22, &v49);
        LODWORD(v49) = 10159;
        v50 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\windows.ui.composition.h";
        v51 = 0;
        v24 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v23 + 72LL))(v23, 10000 * v4);
        if ( v24 < 0 )
          winrt::throw_hresult((unsigned int)v24, &v49);
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v66);
        v25 = winrt::impl::consume_Windows_UI_Composition_ICompositionObject2<winrt::Windows::UI::Composition::CompositionBrush>::Comment(
                &v52,
                &v66);
        v26 = winrt::operator==(v25);
        winrt::handle_type<winrt::impl::hstring_traits>::close(&v66);
        if ( v26 )
        {
          v54[0] = 0x1000000001LL;
          v55 = L"Crossfade.Weight";
          v27 = v54;
          v53 = v54;
          v66 = 0;
          if ( v52 )
          {
            v28 = (**v52)(v52, &winrt::impl::guid_v<winrt::Windows::UI::Composition::ICompositionObject>, &v66);
            v29 = v66;
            v27 = v53;
          }
          else
          {
            v28 = 0;
            v29 = 0;
          }
          LODWORD(v49) = 4441;
          v50 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\windows.ui.composition.h";
          v51 = 0;
          if ( v28 < 0 )
            winrt::throw_hresult((unsigned int)v28, &v49);
          LODWORD(v49) = 4443;
          v50 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\windows.ui.composition.h";
          v51 = 0;
          v30 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD *))(*v29 + 80LL))(v29, v27);
          if ( v30 < 0 )
            winrt::throw_hresult((unsigned int)v30, &v49);
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v66);
        }
        if ( v56 )
        {
          v66 = 0;
          (**(void (__fastcall ***)(__int64, void *, _QWORD **))v56)(
            v56,
            &winrt::impl::guid_v<winrt::Windows::UI::Composition::ICompositionBrush>,
            &v66);
          v31 = v66;
          v32 = v66;
        }
        else
        {
          v31 = 0;
          v32 = 0;
        }
        v66 = v31;
        LODWORD(v49) = 12270;
        v50 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\windows.ui.composition.h";
        v51 = 0;
        v33 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 56LL))(v9);
        if ( v33 < 0 )
          winrt::throw_hresult((unsigned int)v33, &v49);
        if ( v32 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v66);
        LODWORD(v66) = 1;
        winrt::impl::consume_Windows_UI_Composition_ICompositor<winrt::Windows::UI::Composition::ICompositor>::CreateScopedBatch(
          &v59,
          &v61,
          &v66);
        if ( v57 )
        {
          v66 = 0;
          (**(void (__fastcall ***)(__int64, void *, _QWORD **))v57)(
            v57,
            &winrt::impl::guid_v<winrt::Windows::UI::Composition::ICompositionAnimation>,
            &v66);
          v34 = v66;
          v8 = v66;
        }
        else
        {
          v34 = 0;
        }
        v58 = v34;
        v54[0] = 0x1000000001LL;
        v55 = L"Crossfade.Weight";
        v35 = v54;
        v53 = v54;
        v66 = 0;
        if ( v56 )
        {
          v36 = (**(__int64 (__fastcall ***)(__int64, void *, _QWORD **))v56)(
                  v56,
                  &winrt::impl::guid_v<winrt::Windows::UI::Composition::ICompositionObject>,
                  &v66);
          v37 = v66;
          v35 = v53;
        }
        else
        {
          v36 = 0;
          v37 = 0;
        }
        LODWORD(v49) = 4425;
        v50 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\windows.ui.composition.h";
        v51 = 0;
        if ( v36 < 0 )
          winrt::throw_hresult((unsigned int)v36, &v49);
        LODWORD(v49) = 4427;
        v50 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\windows.ui.composition.h";
        v51 = 0;
        v38 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD *, __int64 *))(*v37 + 72LL))(v37, v35, v34);
        if ( v38 < 0 )
          winrt::throw_hresult((unsigned int)v38, &v49);
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v66);
        if ( v8 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v58);
        LODWORD(v49) = 5786;
        v50 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\windows.ui.composition.h";
        v51 = 0;
        v39 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v61 + 64LL))(v61);
        if ( v39 < 0 )
          winrt::throw_hresult((unsigned int)v39, &v49);
        v49 = v9;
        if ( v9 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
        v50 = a2;
        (*(void (__fastcall **)(const char *))(*(_QWORD *)a2 + 8LL))(a2);
        v58 = &v49;
        v40 = (__int64 *)operator new(0x20u);
        v41 = v40;
        if ( v40 )
        {
          *((_DWORD *)v40 + 2) = 1;
          v45 = v49;
          v49 = 0;
          v40[2] = v45;
          v46 = v50;
          v50 = 0;
          v40[3] = (__int64)v46;
          _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
          *v40 = (__int64)off_18002F2E8;
        }
        else
        {
          v41 = 0;
        }
        v58 = v41;
        CrossFadeToNewBrush_::_3_::_lambda_1_::__lambda_1_((winrt::Windows::UI::Composition::ICompositionEffectFactory *)&v49);
        v66 = 0;
        LODWORD(v53) = 5835;
        v54[0] = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\windows.ui.composition.h";
        v54[1] = 0;
        v47 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD **))(*(_QWORD *)v61 + 88LL))(v61, v41, &v66);
        if ( v47 < 0 )
          winrt::throw_hresult((unsigned int)v47, &v53);
        if ( v41 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v58);
        if ( v61 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v61);
        if ( v62 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v62);
        if ( v57 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v57);
        if ( v56 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v56);
        if ( v59 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v59);
        if ( v11 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v63);
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v64);
        if ( v52 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v52);
        if ( v9 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v60);
        return 0;
      }
      LODWORD(v49) = 12270;
      v50 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\windows.ui.composition.h";
      v51 = 0;
      v48 = (*(__int64 (__fastcall **)(__int64, const char *))(*(_QWORD *)v10 + 56LL))(v10, a2);
      if ( v48 < 0 )
        winrt::throw_hresult((unsigned int)v48, &v49);
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v64);
    }
    else
    {
      v66 = 0;
      LODWORD(v49) = 12270;
      v50 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\windows.ui.composition.h";
      v51 = 0;
      v42 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v10 + 56LL))(v10, 0);
      if ( v42 < 0 )
        winrt::throw_hresult((unsigned int)v42, &v49);
      if ( v52 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v52);
    }
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v60);
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(v66) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x124,
                     (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\global\\materialbrushfactory.cpp",
                     v43);
    return (unsigned int)v66;
  }
  return result;
}

```

## disassembly

```asm
0x180011590  mov     rax, rsp
0x180011593  mov     [rax+10h], rbx
0x180011597  mov     [rax+18h], rsi
0x18001159b  push    rdi
0x18001159c  push    r12
0x18001159e  push    r13
0x1800115a0  push    r14
0x1800115a2  push    r15
0x1800115a4  sub     rsp, 0C0h
0x1800115ab  mov     r12d, r9d
0x1800115ae  mov     rsi, r8
0x1800115b1  mov     r15, rdx
0x1800115b4  mov     rbx, rcx
0x1800115b7  xor     r13d, r13d
0x1800115ba  mov     r14d, r13d
0x1800115bd  mov     [rax-58h], r13
0x1800115c1  mov     edi, r13d
0x1800115c4  test    rcx, rcx
0x1800115c7  jz      short loc_1800115E3
0x1800115c9  mov     rax, [rcx]
0x1800115cc  mov     rax, [rax+8]
0x1800115d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115d5  mov     r14, rbx
0x1800115d8  mov     [rsp+0E8h+var_58], rbx
0x1800115e0  mov     rdi, rbx
0x1800115e3  lea     rdx, [rsp+0E8h+var_A0]
0x1800115e8  lea     rcx, [rsp+0E8h+var_58]
0x1800115f0  call    ?Brush@?$consume_Windows_UI_Composition_ISpriteVisual@UISpriteVisual@Composition@UI@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_UI_Composition_ISpriteVisual<winrt::Windows::UI::Composition::ISpriteVisual>::Brush(void)
0x1800115f5  nop
0x1800115f6  test    r15, r15
0x1800115f9  jz      loc_180011CD0
0x1800115ff  mov     rax, [r15]
0x180011602  mov     rcx, r15
0x180011605  mov     rax, [rax+8]
0x180011609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001160e  mov     [rsp+0E8h+var_38], r15
0x180011616  cmp     [rsp+0E8h+var_A0], r13
0x18001161b  jz      loc_180011EBD
0x180011621  mov     rdi, r13
0x180011624  mov     [rsp+0E8h+var_40], r13
0x18001162c  test    rsi, rsi
0x18001162f  jz      short loc_18001164B
0x180011631  mov     rax, [rsi]
0x180011634  mov     rcx, rsi
0x180011637  mov     rax, [rax+8]
0x18001163b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011640  mov     rdi, rsi
0x180011643  mov     [rsp+0E8h+var_40], rsi
0x18001164b  lea     rdx, [rsp+0E8h+var_60]
0x180011653  lea     rcx, [rsp+0E8h+var_A0]
0x180011658  call    ?Compositor@?$consume_Windows_UI_Composition_ICompositionObject@UCompositionBrush@Composition@UI@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_UI_Composition_ICompositionObject<winrt::Windows::UI::Composition::CompositionBrush>::Compositor(void)
0x18001165d  nop
0x18001165e  lea     rdx, [rsp+0E8h+var_78]
0x180011663  lea     rcx, [rsp+0E8h+var_40]
0x18001166b  call    ?CreateBrush@?$consume_Windows_UI_Composition_ICompositionEffectFactory@UICompositionEffectFactory@Composition@UI@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_UI_Composition_ICompositionEffectFactory<winrt::Windows::UI::Composition::ICompositionEffectFactory>::CreateBrush(void)
0x180011670  nop
0x180011671  mov     ebx, 1
0x180011676  mov     dword ptr [rsp+0E8h+var_90], ebx
0x18001167a  mov     dword ptr [rsp+0E8h+var_90+4], 9
0x180011682  lea     rax, S2; "Crossfade"
0x180011689  mov     [rsp+0E8h+var_80], rax
0x18001168e  lea     rdx, [rsp+0E8h+var_90]
0x180011693  mov     [rsp+0E8h+var_98], rdx
0x180011698  mov     rcx, [rsp+0E8h+var_78]
0x18001169d  mov     [rsp+0E8h+arg_0], r13
0x1800116a5  test    rcx, rcx
0x1800116a8  jz      loc_180011E9C
0x1800116ae  mov     rax, [rcx]
0x1800116b1  lea     r8, [rsp+0E8h+arg_0]
0x1800116b9  lea     rdx, ??$guid_v@UICompositionObject2@Composition@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Composition::ICompositionObject2>
0x1800116c0  mov     rax, [rax]
0x1800116c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116c8  mov     rcx, [rsp+0E8h+arg_0]
0x1800116d0  mov     [rsp+0E8h+arg_0], rcx
0x1800116d8  mov     rdx, [rsp+0E8h+var_98]
0x1800116dd  mov     dword ptr [rsp+0E8h+var_B8], 117Bh
0x1800116e5  lea     rsi, aOnecoreuapInte; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x1800116ec  mov     [rsp+0E8h+var_B0], rsi
0x1800116f1  mov     [rsp+0E8h+var_A8], r13
0x1800116f6  test    eax, eax
0x1800116f8  js      loc_180011F3A
0x1800116fe  mov     dword ptr [rsp+0E8h+var_B8], 117Dh
0x180011706  mov     [rsp+0E8h+var_B0], rsi
0x18001170b  mov     [rsp+0E8h+var_A8], r13
0x180011710  mov     rax, [rcx]
0x180011713  mov     rax, [rax+38h]
0x180011717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001171c  test    eax, eax
0x18001171e  js      loc_180011F46
0x180011724  lea     rcx, [rsp+0E8h+arg_0]
0x18001172c  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180011731  mov     dword ptr [rsp+0E8h+var_90], ebx
0x180011735  mov     dword ptr [rsp+0E8h+var_90+4], 7
0x18001173d  lea     rax, aSource1; "source1"
0x180011744  mov     [rsp+0E8h+var_80], rax
0x180011749  lea     rax, [rsp+0E8h+var_90]
0x18001174e  mov     [rsp+0E8h+var_98], rax
0x180011753  mov     rcx, [rsp+0E8h+var_78]
0x180011758  mov     dword ptr [rsp+0E8h+var_B8], 7B4h
0x180011760  mov     [rsp+0E8h+var_B0], rsi
0x180011765  mov     [rsp+0E8h+var_A8], r13
0x18001176a  mov     rax, [rcx]
0x18001176d  mov     r8, [rsp+0E8h+var_A0]
0x180011772  lea     rdx, [rsp+0E8h+var_90]
0x180011777  mov     rax, [rax+38h]
0x18001177b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011780  test    eax, eax
0x180011782  js      loc_180011F53
0x180011788  mov     dword ptr [rsp+0E8h+var_90], ebx
0x18001178c  mov     dword ptr [rsp+0E8h+var_90+4], 7
0x180011794  lea     rax, aSource2; "source2"
0x18001179b  mov     [rsp+0E8h+var_80], rax
0x1800117a0  lea     rax, [rsp+0E8h+var_90]
0x1800117a5  mov     [rsp+0E8h+var_98], rax
0x1800117aa  mov     rcx, [rsp+0E8h+var_78]
0x1800117af  mov     dword ptr [rsp+0E8h+var_B8], 7B4h
0x1800117b7  mov     [rsp+0E8h+var_B0], rsi
0x1800117bc  mov     [rsp+0E8h+var_A8], r13
0x1800117c1  mov     rax, [rcx]
0x1800117c4  mov     r8, r15
0x1800117c7  lea     rdx, [rsp+0E8h+var_90]
0x1800117cc  mov     rax, [rax+38h]
0x1800117d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800117d5  test    eax, eax
0x1800117d7  js      loc_180011F5F
0x1800117dd  lea     rdx, [rsp+0E8h+var_70]
0x1800117e2  lea     rcx, [rsp+0E8h+var_60]
0x1800117ea  call    ?CreateScalarKeyFrameAnimation@?$consume_Windows_UI_Composition_ICompositor@UICompositor@Composition@UI@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_UI_Composition_ICompositor<winrt::Windows::UI::Composition::ICompositor>::CreateScalarKeyFrameAnimation(void)
0x1800117ef  nop
0x1800117f0  lea     rdx, [rsp+0E8h+var_48]
0x1800117f8  lea     rcx, [rsp+0E8h+var_60]
0x180011800  call    ?CreateLinearEasingFunction@?$consume_Windows_UI_Composition_ICompositor@UICompositor@Composition@UI@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_UI_Composition_ICompositor<winrt::Windows::UI::Composition::ICompositor>::CreateLinearEasingFunction(void)
0x180011805  nop
0x180011806  mov     rcx, [rsp+0E8h+var_48]
0x18001180e  mov     [rsp+0E8h+arg_0], r13
0x180011816  test    rcx, rcx
0x180011819  jz      loc_180011F6C
0x18001181f  mov     rax, [rcx]
0x180011822  lea     r8, [rsp+0E8h+arg_0]
0x18001182a  lea     rdx, ??$guid_v@UICompositionEasingFunction@Composition@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Composition::ICompositionEasingFunction>
0x180011831  mov     rax, [rax]
0x180011834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011839  mov     r9, [rsp+0E8h+arg_0]
0x180011841  mov     [rsp+0E8h+arg_0], r9
0x180011849  mov     rbx, r9
0x18001184c  mov     rcx, [rsp+0E8h+var_70]
0x180011851  mov     dword ptr [rsp+0E8h+var_B8], 2C34h
0x180011859  mov     [rsp+0E8h+var_B0], rsi
0x18001185e  mov     [rsp+0E8h+var_A8], r13
0x180011863  mov     rax, [rcx]
0x180011866  xorps   xmm2, xmm2
0x180011869  xorps   xmm1, xmm1
0x18001186c  mov     rax, [rax+38h]
0x180011870  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011875  test    eax, eax
0x180011877  js      loc_180011F77
0x18001187d  test    rbx, rbx
0x180011880  jz      short loc_18001188F
0x180011882  lea     rcx, [rsp+0E8h+arg_0]
0x18001188a  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001188f  mov     rcx, [rsp+0E8h+var_48]
0x180011897  mov     [rsp+0E8h+arg_0], r13
0x18001189f  test    rcx, rcx
0x1800118a2  jz      loc_180011F84
0x1800118a8  mov     rax, [rcx]
0x1800118ab  lea     r8, [rsp+0E8h+arg_0]
0x1800118b3  lea     rdx, ??$guid_v@UICompositionEasingFunction@Composition@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Composition::ICompositionEasingFunction>
0x1800118ba  mov     rax, [rax]
0x1800118bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118c2  mov     r9, [rsp+0E8h+arg_0]
0x1800118ca  mov     [rsp+0E8h+arg_0], r9
0x1800118d2  mov     rbx, r9
0x1800118d5  mov     rcx, [rsp+0E8h+var_70]
0x1800118da  mov     dword ptr [rsp+0E8h+var_B8], 2C34h
0x1800118e2  mov     [rsp+0E8h+var_B0], rsi
0x1800118e7  mov     [rsp+0E8h+var_A8], r13
0x1800118ec  mov     rax, [rcx]
0x1800118ef  movss   xmm1, cs:__real@3f800000
0x1800118f7  movaps  xmm2, xmm1
0x1800118fa  mov     rax, [rax+38h]
0x1800118fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011903  test    eax, eax
0x180011905  js      loc_180011F8F
0x18001190b  test    rbx, rbx
0x18001190e  jz      short loc_18001191D
0x180011910  lea     rcx, [rsp+0E8h+arg_0]
0x180011918  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001191d  mov     rcx, [rsp+0E8h+var_70]
0x180011922  mov     [rsp+0E8h+arg_0], r13
0x18001192a  test    rcx, rcx
0x18001192d  jz      loc_180011F9C
0x180011933  mov     rax, [rcx]
0x180011936  lea     r8, [rsp+0E8h+arg_0]
0x18001193e  lea     rdx, ??$guid_v@UIKeyFrameAnimation@Composition@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Composition::IKeyFrameAnimation>
0x180011945  mov     rax, [rax]
0x180011948  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001194d  mov     rcx, [rsp+0E8h+arg_0]
0x180011955  mov     [rsp+0E8h+arg_0], rcx
0x18001195d  mov     dword ptr [rsp+0E8h+var_B8], 27ADh
0x180011965  mov     [rsp+0E8h+var_B0], rsi
0x18001196a  mov     [rsp+0E8h+var_A8], r13
0x18001196f  test    eax, eax
0x180011971  js      loc_180011FA7
0x180011977  mov     dword ptr [rsp+0E8h+var_B8], 27AFh
0x18001197f  mov     [rsp+0E8h+var_B0], rsi
0x180011984  mov     [rsp+0E8h+var_A8], r13
0x180011989  mov     r8, [rcx]
0x18001198c  imul    rdx, r12, 2710h
0x180011993  mov     rax, [r8+48h]
0x180011997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001199c  test    eax, eax
0x18001199e  js      loc_180011FB3
0x1800119a4  lea     rcx, [rsp+0E8h+arg_0]
0x1800119ac  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800119b1  lea     rdx, [rsp+0E8h+arg_0]
0x1800119b9  lea     rcx, [rsp+0E8h+var_A0]
0x1800119be  call    ?Comment@?$consume_Windows_UI_Composition_ICompositionObject2@UCompositionBrush@Composition@UI@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_UI_Composition_ICompositionObject2<winrt::Windows::UI::Composition::CompositionBrush>::Comment(void)
0x1800119c3  mov     rcx, rax
0x1800119c6  call    ??8winrt@@YA_NAEBUhstring@0@PEBG@Z; winrt::operator==(winrt::hstring const &,ushort const *)
0x1800119cb  mov     bl, al
0x1800119cd  lea     rcx, [rsp+0E8h+arg_0]
0x1800119d5  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800119da  lea     r12, aCrossfadeWeigh; "Crossfade.Weight"
0x1800119e1  test    bl, bl
0x1800119e3  jz      loc_180011A9A
0x1800119e9  mov     dword ptr [rsp+0E8h+var_90], 1
0x1800119f1  mov     dword ptr [rsp+0E8h+var_90+4], 10h
0x1800119f9  mov     [rsp+0E8h+var_80], r12
0x1800119fe  lea     rdx, [rsp+0E8h+var_90]
0x180011a03  mov     [rsp+0E8h+var_98], rdx
0x180011a08  mov     rcx, [rsp+0E8h+var_A0]
0x180011a0d  mov     [rsp+0E8h+arg_0], r13
0x180011a15  test    rcx, rcx
0x180011a18  jz      loc_180011EB2
0x180011a1e  mov     rax, [rcx]
0x180011a21  lea     r8, [rsp+0E8h+arg_0]
0x180011a29  lea     rdx, ??$guid_v@UICompositionObject@Composition@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Composition::ICompositionObject>
0x180011a30  mov     rax, [rax]
0x180011a33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a38  mov     rcx, [rsp+0E8h+arg_0]
0x180011a40  mov     [rsp+0E8h+arg_0], rcx
0x180011a48  mov     rdx, [rsp+0E8h+var_98]
0x180011a4d  mov     dword ptr [rsp+0E8h+var_B8], 1159h
0x180011a55  mov     [rsp+0E8h+var_B0], rsi
0x180011a5a  mov     [rsp+0E8h+var_A8], r13
0x180011a5f  test    eax, eax
0x180011a61  js      loc_180011FC0
0x180011a67  mov     dword ptr [rsp+0E8h+var_B8], 115Bh
0x180011a6f  mov     [rsp+0E8h+var_B0], rsi
0x180011a74  mov     [rsp+0E8h+var_A8], r13
0x180011a79  mov     rax, [rcx]
0x180011a7c  mov     rax, [rax+50h]
0x180011a80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a85  test    eax, eax
0x180011a87  js      loc_180011FCC
0x180011a8d  lea     rcx, [rsp+0E8h+arg_0]
0x180011a95  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180011a9a  mov     rcx, [rsp+0E8h+var_78]
0x180011a9f  test    rcx, rcx
0x180011aa2  jz      loc_180011FD9
0x180011aa8  mov     [rsp+0E8h+arg_0], r13
0x180011ab0  mov     rax, [rcx]
0x180011ab3  lea     r8, [rsp+0E8h+arg_0]
0x180011abb  lea     rdx, ??$guid_v@UICompositionBrush@Composition@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Composition::ICompositionBrush>
0x180011ac2  mov     rax, [rax]
0x180011ac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011aca  mov     rdx, [rsp+0E8h+arg_0]
0x180011ad2  mov     rbx, rdx
0x180011ad5  mov     [rsp+0E8h+arg_0], rdx
0x180011add  mov     dword ptr [rsp+0E8h+var_B8], 2FEEh
0x180011ae5  mov     [rsp+0E8h+var_B0], rsi
0x180011aea  mov     [rsp+0E8h+var_A8], r13
0x180011aef  mov     rax, [r14]
0x180011af2  mov     rcx, r14
0x180011af5  mov     rax, [rax+38h]
0x180011af9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011afe  test    eax, eax
0x180011b00  js      loc_180011FE4
0x180011b06  test    rbx, rbx
0x180011b09  jz      short loc_180011B18
0x180011b0b  lea     rcx, [rsp+0E8h+arg_0]
0x180011b13  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180011b18  mov     dword ptr [rsp+0E8h+arg_0], 1
0x180011b23  lea     r8, [rsp+0E8h+arg_0]
0x180011b2b  lea     rdx, [rsp+0E8h+var_50]
0x180011b33  lea     rcx, [rsp+0E8h+var_60]
0x180011b3b  call    ?CreateScopedBatch@?$consume_Windows_UI_Composition_ICompositor@UICompositor@Composition@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBW4CompositionBatchTypes@Composition@UI@Windows@3@@Z; winrt::impl::consume_Windows_UI_Composition_ICompositor<winrt::Windows::UI::Composition::ICompositor>::CreateScopedBatch(winrt::Windows::UI::Composition::CompositionBatchTypes const &)
0x180011b40  nop
0x180011b41  mov     rcx, [rsp+0E8h+var_70]
0x180011b46  test    rcx, rcx
0x180011b49  jz      loc_180011FF1
0x180011b4f  mov     [rsp+0E8h+arg_0], r13
0x180011b57  mov     rax, [rcx]
0x180011b5a  lea     r8, [rsp+0E8h+arg_0]
0x180011b62  lea     rdx, ??$guid_v@UICompositionAnimation@Composition@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Composition::ICompositionAnimation>
0x180011b69  mov     rax, [rax]
0x180011b6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b71  mov     rbx, [rsp+0E8h+arg_0]
0x180011b79  mov     r13, rbx
0x180011b7c  mov     [rsp+0E8h+var_68], rbx
  ... truncated ...
```
