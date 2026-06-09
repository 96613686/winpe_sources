# Windows::UI::Composition::CompositionAnimationGroup::StartAnimationGroupWithIAnimationObject(Windows::UI::Composition::IAnimationObject *,std::vector<Windows::UI::Composition::CompositionPropertyAnimator *,std::allocator<Windows::UI::Composition::CompositionPropertyAnimator *>> *)

- ea: `0x1800ebe2c`
- end: `0x1800ec485`
- name: `?StartAnimationGroupWithIAnimationObject@CompositionAnimationGroup@Composition@UI@Windows@@QEAAJPEAUIAnimationObject@234@PEAV?$vector@PEAVCompositionPropertyAnimator@Composition@UI@Windows@@V?$allocator@PEAVCompositionPropertyAnimator@Composition@UI@Windows@@@std@@@std@@@Z`
- size: `1625`
- prototype: ``
- caller_count: `2`
- callee_count: `28`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18008e4b4`
- `0x180117970`

## callees

- `0x1800092fc`
- `0x18000a68c`
- `0x18000aca4`
- `0x18000bc00`
- `0x18001358c`
- `0x180033bb4`
- `0x180048980`
- `0x18005143c`
- `0x180072668`
- `0x180074480`
- `0x1800751ec`
- `0x1800752c8`
- `0x180075980`
- `0x180076d4c`
- `0x180077e2c`
- `0x1800781f0`
- `0x18008e2b8`
- `0x1800a45ac`
- `0x1800bc75c`
- `0x1800dee2c`
- `0x1800ebe2c`
- `0x1800ec48c`
- `0x1800f6f10`
- `0x1801409cc`
- `0x180140a04`
- `0x180140bf0`
- `0x180141000`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ec260`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ec260`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ebf28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ebffd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec02b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec0a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ebf28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ebffd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec02b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec0a5`

## string_xrefs

- `0x1800ebecb`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositionanimationgroup.cpp`
- `0x1800ec012`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositionanimationgroup.cpp`
- `0x1800ec1bd`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositionanimationgroup.cpp`
- `0x1800ec362`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositionanimationgroup.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::CompositionAnimationGroup::StartAnimationGroupWithIAnimationObject(
        __int64 a1,
        struct IUnknown *a2,
        __int64 a3)
{
  struct Microsoft::WRL2::ContextSession *v6; // rcx
  int v7; // eax
  unsigned int v8; // ebx
  int v9; // eax
  _QWORD *v10; // rbx
  Windows::UI::Composition::CompositionAnimation *v11; // rsi
  HSTRING v12; // rdx
  int v13; // eax
  unsigned int v14; // edi
  __int64 v15; // rax
  __int64 v16; // rcx
  char *v17; // rbx
  __int64 v18; // rdi
  __int64 v19; // rsi
  __int64 v20; // rax
  int v21; // eax
  __int64 v22; // r9
  __int64 v23; // rdx
  __int64 v24; // rbx
  int v25; // ecx
  _QWORD *v26; // rax
  int v27; // edx
  __int64 v28; // rax
  unsigned __int64 v29; // rbx
  __int64 v30; // rax
  __int64 v31; // r14
  PCWSTR StringRawBuffer; // rax
  __int64 v33; // rbx
  _QWORD *v34; // rsi
  __int64 v35; // rdi
  __int64 (__fastcall *v36)(__int64, _QWORD, _QWORD, __int64); // rbx
  int v37; // eax
  __int64 v38; // rax
  _QWORD *v39; // rdx
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  __int128 v43; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v44; // [rsp+40h] [rbp-C0h]
  HSTRING string; // [rsp+48h] [rbp-B8h] BYREF
  int v46; // [rsp+50h] [rbp-B0h]
  int v47; // [rsp+54h] [rbp-ACh] BYREF
  struct Microsoft::WRL2::ContextRuntimeClass *v48; // [rsp+58h] [rbp-A8h] BYREF
  int v49[2]; // [rsp+60h] [rbp-A0h] BYREF
  char *v50[2]; // [rsp+68h] [rbp-98h] BYREF
  char *v51; // [rsp+78h] [rbp-88h]
  _QWORD v52[2]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v53[2]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v54[2]; // [rsp+A0h] [rbp-60h] BYREF
  Windows::UI::Composition::CompositionAnimation *v55; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v56[64]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v57[32]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v58[64]; // [rsp+118h] [rbp+18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v48 = 0;
  Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(&v48);
  v6 = *(struct Microsoft::WRL2::ContextSession **)(a1 + 24);
  v48 = 0;
  if ( (int)Microsoft::WRL2::ContextRuntimeClass::ValidateInterface(
              v6,
              a2,
              (const struct Microsoft::WRL2::NestableRuntimeClass::InterfaceType *)&Windows::UI::Composition::CompositionObject::s_InterfaceType,
              &v48) >= 0 )
  {
    v7 = Windows::UI::Composition::CompositionAnimationGroup::PlayAnimations(a1, (_DWORD)v48, 0, 0, (__int64)&v47, a3);
    v8 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x166,
        (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositionanimationgroup.cpp",
        (const char *)(unsigned int)v7,
        v42);
      goto LABEL_46;
    }
    goto LABEL_50;
  }
  v9 = *(_DWORD *)(a1 + 200);
  v10 = *(_QWORD **)(a1 + 184);
  v43 = 0;
  v46 = v9;
  *(_OWORD *)v50 = 0;
  v44 = 0;
  v51 = 0;
  while ( v10 )
  {
    v11 = (Windows::UI::Composition::CompositionAnimation *)v10[2];
    string = 0;
    WindowsDeleteString(0);
    string = 0;
    Windows::UI::Composition::CompositionAnimation::GetTarget(v11, &string);
    if ( !string )
    {
      v8 = Windows::UI::Composition::ReturnHrMsgInvalidArgument();
      WindowsDeleteString(string);
      string = 0;
      std::vector<Microsoft::WRL::Wrappers::HString>::_Tidy(v50);
      if ( !(_QWORD)v43 )
        goto LABEL_46;
      goto LABEL_45;
    }
    v13 = Windows::UI::Composition::AnimationHelper::IAnimationObjectPropertyNameCheck(
            (Windows::UI::Composition::AnimationHelper *)string,
            v12);
    v14 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x188,
        (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositionanimationgroup.cpp",
        (const char *)(unsigned int)v13,
        v41);
      WindowsDeleteString(string);
      string = 0;
      std::vector<Microsoft::WRL::Wrappers::HString>::_Tidy(v50);
      if ( (_QWORD)v43 )
      {
        std::_Destroy_range<std::allocator<std::pair<Windows::UI::Composition::CompositionAnimation *,std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>>>>(
          v43,
          *((_QWORD *)&v43 + 1));
        std::_Deallocate<16>(v43, 8 * ((v44 - (__int64)v43) >> 3));
        v44 = 0;
        v43 = 0;
      }
      v8 = v14;
      goto LABEL_46;
    }
    Windows::UI::Composition::CompositionAnimation::TryPopulateAnimationObjectParametersInfo(v11, 1);
    if ( v50[1] == v51 )
    {
      std::vector<Microsoft::WRL::Wrappers::HString>::_Emplace_reallocate<Microsoft::WRL::Wrappers::HString>(
        v50,
        v50[1],
        &string);
    }
    else
    {
      *(_QWORD *)v50[1] = string;
      v50[1] += 8;
      string = 0;
    }
    v15 = std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>(v58);
    v55 = v11;
    std::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>(
      v56,
      v15);
    if ( *((_QWORD *)&v43 + 1) == v44 )
    {
      ____Emplace_reallocate_U__pair_PEAVCompositionAnimation_Composition_UI_Windows__V__unordered_map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__UParameterOverrideEntry_Composition_UI_Windows__U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__UParameterOverrideEntry_Composition_UI_Windows___std___2__std___std_____vector_U__pair_PEAVCompositionAnimation_Composition_UI_Windows__V__unordered_map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__UParameterOverrideEntry_Composition_UI_Windows__U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__UParameterOverrideEntry_Composition_UI_Windows___std___2__std___std__V__allocator_U__pair_PEAVCompositionAnimation_Composition_UI_Windows__V__unordered_map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__UParameterOverrideEntry_Composition_UI_Windows__U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__UParameterOverrideEntry_Composition_UI_Windows___std___2__std___std___2__std__AEAAPEAU__pair_PEAVCompositionAnimation_Composition_UI_Windows__V__unordered_map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__UParameterOverrideEntry_Composition_UI_Windows__U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__UParameterOverrideEntry_Composition_UI_Windows___std___2__std___1_QEAU21___QEAU21__Z(
        &v43,
        *((_QWORD *)&v43 + 1),
        &v55);
    }
    else
    {
      v16 = *((_QWORD *)&v43 + 1) + 8LL;
      **((_QWORD **)&v43 + 1) = v55;
      std::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>(
        v16,
        v56);
      *((_QWORD *)&v43 + 1) += 72LL;
    }
    std::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>::~_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>(v56);
    std::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>::~_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>(v58);
    WindowsDeleteString(string);
    v10 = (_QWORD *)*v10;
  }
  v17 = v50[0];
  gsl::details::extent_type<-1>::extent_type<-1>(v52, (v50[1] - v50[0]) >> 3);
  v18 = v52[0];
  if ( v52[0] == -1
    || !v17 && v52[0]
    || (v19 = v43,
        gsl::details::extent_type<-1>::extent_type<-1>(
          v52,
          0x8E38E38E38E38E39uLL * ((__int64)(*((_QWORD *)&v43 + 1) - v43) >> 3)),
        v20 = v52[0],
        v52[0] == -1)
    || !v19 && v52[0] )
  {
    ((void (*)(void))`gsl::details::get_terminate_handler'::`2'::handler)();
  }
  v52[0] = v18;
  v52[1] = v17;
  v54[0] = v20;
  v54[1] = v19;
  v21 = Windows::UI::Composition::AnimationHelper::ResolvePropertiesWithIAnimationObjectTarget_Callback(v54, a2, v52);
  v8 = v21;
  if ( v21 >= 0 )
  {
    if ( v46 == *(_DWORD *)(a1 + 200) )
    {
      v24 = *(_QWORD *)(a1 + 184);
      v25 = 0;
      v54[0] = v24;
      while ( 1 )
      {
        v26 = *(_QWORD **)(a1 + 184);
        v27 = 0;
        v46 = v25;
        while ( v26 )
        {
          v26 = (_QWORD *)*v26;
          ++v27;
        }
        if ( v25 >= v27 )
          break;
        *(_QWORD *)v49 = 0;
        v28 = *(_QWORD *)(v24 + 16);
        v29 = v25;
        v53[0] = 0;
        v52[0] = v28;
        v30 = std::vector<std::pair<Windows::UI::Composition::CompositionAnimation *,std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>>>::at(
                &v43,
                v25);
        if ( (v50[1] - v50[0]) >> 3 <= v29 )
          std::_Dwm_Xlength_error(v50[0]);
        v31 = v30 + 8;
        StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)&v50[0][8 * v29], 0);
        std::wstring::wstring(v57, StringRawBuffer);
        std::wstring::wstring(v58, L"this.target");
        v33 = std::unordered_map<std::wstring,Windows::UI::Composition::RedirectedPropertyInfo>::at(v31, v58);
        std::wstring::_Tidy_deallocate(v58);
        v34 = (_QWORD *)std::unordered_map<std::wstring,Windows::UI::Composition::RedirectedPropertyInfo>::at(
                          v33 + 8,
                          v57);
        Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionObject>::operator=(v53, v34[2]);
        v35 = v53[0];
        v36 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64))(*(_QWORD *)v53[0] + 152LL);
        Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(v49);
        v37 = v36(v35, *v34, v52[0], v31);
        v8 = v37;
        if ( v37 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1B7,
            (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositionanimationgroup.cpp",
            (const char *)(unsigned int)v37,
            (int)v49);
          std::wstring::_Tidy_deallocate(v57);
          Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(v53);
          Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(v49);
          goto LABEL_44;
        }
        if ( a3 )
        {
          v38 = *(_QWORD *)v49;
          v39 = *(_QWORD **)(a3 + 8);
          *(_QWORD *)v49 = 0;
          v52[0] = v38;
          if ( v39 == *(_QWORD **)(a3 + 16) )
          {
            std::vector<DirectComposition::CCompositionTextureBinding *>::_Emplace_reallocate<DirectComposition::CCompositionTextureBinding *>(
              a3,
              v39,
              v52);
          }
          else
          {
            *v39 = v38;
            *(_QWORD *)(a3 + 8) += 8LL;
          }
        }
        v24 = *(_QWORD *)v54[0];
        v54[0] = *(_QWORD *)v54[0];
        std::wstring::_Tidy_deallocate(v57);
        Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(v53);
        Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(v49);
        v25 = v46 + 1;
      }
      std::vector<Microsoft::WRL::Wrappers::HString>::_Tidy(v50);
      if ( (_QWORD)v43 )
      {
        std::_Destroy_range<std::allocator<std::pair<Windows::UI::Composition::CompositionAnimation *,std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>>>>(
          v43,
          *((_QWORD *)&v43 + 1));
        std::_Deallocate<16>(v43, 8 * ((v44 - (__int64)v43) >> 3));
        v44 = 0;
        v43 = 0;
      }
LABEL_50:
      Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(&v48);
      return 0;
    }
    v8 = -2147483636;
    v23 = 410;
    v22 = 2147483660LL;
  }
  else
  {
    v22 = (unsigned int)v21;
    v23 = 405;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v23,
    (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositionanimationgroup.cpp",
    (const char *)v22,
    v41);
LABEL_44:
  std::vector<Microsoft::WRL::Wrappers::HString>::_Tidy(v50);
  if ( (_QWORD)v43 )
  {
LABEL_45:
    std::_Destroy_range<std::allocator<std::pair<Windows::UI::Composition::CompositionAnimation *,std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>>>>(
      v43,
      *((_QWORD *)&v43 + 1));
    std::_Deallocate<16>(v43, 8 * ((v44 - (__int64)v43) >> 3));
    v44 = 0;
    v43 = 0;
  }
LABEL_46:
  Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(&v48);
  return v8;
}

```

## disassembly

```asm
0x1800ebe2c  mov     [rsp-8+arg_18], rbx
0x1800ebe31  push    rbp
0x1800ebe32  push    rsi
0x1800ebe33  push    rdi
0x1800ebe34  push    r12
0x1800ebe36  push    r13
0x1800ebe38  push    r14
0x1800ebe3a  push    r15
0x1800ebe3c  lea     rbp, [rsp-60h]
0x1800ebe41  sub     rsp, 160h
0x1800ebe48  mov     rax, cs:__security_cookie
0x1800ebe4f  xor     rax, rsp
0x1800ebe52  mov     [rbp+90h+var_38], rax
0x1800ebe56  mov     r12, rcx
0x1800ebe59  xor     r15d, r15d
0x1800ebe5c  lea     rcx, [rsp+190h+var_138]; void *
0x1800ebe61  mov     [rsp+190h+var_138], r15
0x1800ebe66  mov     r13, r8
0x1800ebe69  mov     r14, rdx
0x1800ebe6c  call    ?InternalUnlock@?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(void)
0x1800ebe71  mov     rcx, [r12+18h]; struct Microsoft::WRL2::ContextSession *
0x1800ebe76  lea     r9, [rsp+190h+var_138]; struct Microsoft::WRL2::ContextRuntimeClass **
0x1800ebe7b  lea     r8, ?s_InterfaceType@CompositionObject@Composition@UI@Windows@@2UInterfaceType@NestableRuntimeClass@WRL2@Microsoft@@B; struct Microsoft::WRL2::NestableRuntimeClass::InterfaceType *
0x1800ebe82  mov     [rsp+190h+var_138], r15
0x1800ebe87  mov     rdx, r14; struct IUnknown *
0x1800ebe8a  call    ?ValidateInterface@ContextRuntimeClass@WRL2@Microsoft@@KAJPEAVContextSession@23@PEAUIUnknown@@PEBUInterfaceType@NestableRuntimeClass@23@PEAPEAV123@@Z; Microsoft::WRL2::ContextRuntimeClass::ValidateInterface(Microsoft::WRL2::ContextSession *,IUnknown *,Microsoft::WRL2::NestableRuntimeClass::InterfaceType const *,Microsoft::WRL2::ContextRuntimeClass * *)
0x1800ebe8f  mov     rdx, [rsp+190h+var_138]
0x1800ebe94  mov     [rsp+190h+var_138], rdx
0x1800ebe99  test    eax, eax
0x1800ebe9b  js      short loc_1800EBEE4
0x1800ebe9d  lea     rax, [rsp+190h+var_13C]
0x1800ebea2  mov     [rsp+190h+var_168], r13
0x1800ebea7  xor     r9d, r9d
0x1800ebeaa  mov     qword ptr [rsp+190h+var_170], rax; int
0x1800ebeaf  xor     r8d, r8d
0x1800ebeb2  mov     rcx, r12
0x1800ebeb5  call    ?PlayAnimations@CompositionAnimationGroup@Composition@UI@Windows@@QEAAJPEAVCompositionObject@234@PEBUAnimationValueData@234@W4AnimationValueSynchronizationBehavior@234@PEA_NPEAV?$vector@PEAVCompositionPropertyAnimator@Composition@UI@Windows@@V?$allocator@PEAVCompositionPropertyAnimator@Composition@UI@Windows@@@std@@@std@@@Z; Windows::UI::Composition::CompositionAnimationGroup::PlayAnimations(Windows::UI::Composition::CompositionObject *,Windows::UI::Composition::AnimationValueData const *,Windows::UI::Composition::AnimationValueSynchronizationBehavior,bool *,std::vector<Windows::UI::Composition::CompositionPropertyAnimator *> *)
0x1800ebeba  mov     ebx, eax
0x1800ebebc  test    eax, eax
0x1800ebebe  jns     loc_1800EC467
0x1800ebec4  mov     rcx, [rbp+98h]; this
0x1800ebecb  lea     r8, aOnecoreuapWind_213; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x1800ebed2  mov     r9d, eax; char *
0x1800ebed5  mov     edx, 166h; void *
0x1800ebeda  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ebedf  jmp     loc_1800EC3E0
0x1800ebee4  mov     eax, [r12+0C8h]
0x1800ebeec  xorps   xmm0, xmm0
0x1800ebeef  mov     rbx, [r12+0B8h]
0x1800ebef7  xorps   xmm1, xmm1
0x1800ebefa  movdqu  [rsp+190h+var_160], xmm0
0x1800ebf00  mov     [rsp+190h+var_140], eax
0x1800ebf04  movdqu  xmmword ptr [rsp+190h+var_128], xmm1
0x1800ebf0a  mov     [rsp+190h+var_150], r15
0x1800ebf0f  mov     [rsp+190h+var_118], r15
0x1800ebf14  test    rbx, rbx
0x1800ebf17  jz      loc_1800EC10C
0x1800ebf1d  mov     rsi, [rbx+10h]
0x1800ebf21  xor     ecx, ecx; string
0x1800ebf23  mov     [rsp+190h+string], r15
0x1800ebf28  call    cs:__imp_WindowsDeleteString
0x1800ebf2e  lea     rdx, [rsp+190h+string]; HSTRING *
0x1800ebf33  mov     [rsp+190h+string], r15
0x1800ebf38  mov     rcx, rsi; this
0x1800ebf3b  call    ?GetTarget@CompositionAnimation@Composition@UI@Windows@@QEAAXPEAPEAUHSTRING__@@@Z; Windows::UI::Composition::CompositionAnimation::GetTarget(HSTRING__ * *)
0x1800ebf40  mov     rcx, [rsp+190h+string]; this
0x1800ebf45  test    rcx, rcx
0x1800ebf48  jz      loc_1800EC099
0x1800ebf4e  call    ?IAnimationObjectPropertyNameCheck@AnimationHelper@Composition@UI@Windows@@YAJPEAUHSTRING__@@@Z; Windows::UI::Composition::AnimationHelper::IAnimationObjectPropertyNameCheck(HSTRING__ *)
0x1800ebf53  mov     edi, eax
0x1800ebf55  test    eax, eax
0x1800ebf57  js      loc_1800EC00B
0x1800ebf5d  mov     dl, 1; bool
0x1800ebf5f  mov     rcx, rsi; this
0x1800ebf62  call    ?TryPopulateAnimationObjectParametersInfo@CompositionAnimation@Composition@UI@Windows@@QEAAX_N@Z; Windows::UI::Composition::CompositionAnimation::TryPopulateAnimationObjectParametersInfo(bool)
0x1800ebf67  mov     rdx, [rsp+190h+var_128+8]
0x1800ebf6c  cmp     rdx, [rsp+190h+var_118]
0x1800ebf71  jz      short loc_1800EBF88
0x1800ebf73  mov     rax, [rsp+190h+string]
0x1800ebf78  mov     [rdx], rax
0x1800ebf7b  add     [rsp+190h+var_128+8], 8
0x1800ebf81  mov     [rsp+190h+string], r15
0x1800ebf86  jmp     short loc_1800EBF97
0x1800ebf88  lea     r8, [rsp+190h+string]
0x1800ebf8d  lea     rcx, [rsp+190h+var_128]
0x1800ebf92  call    ??$_Emplace_reallocate@VHString@Wrappers@WRL@Microsoft@@@?$vector@VHString@Wrappers@WRL@Microsoft@@V?$allocator@VHString@Wrappers@WRL@Microsoft@@@std@@@std@@AEAAPEAVHString@Wrappers@WRL@Microsoft@@QEAV2345@$$QEAV2345@@Z; std::vector<Microsoft::WRL::Wrappers::HString>::_Emplace_reallocate<Microsoft::WRL::Wrappers::HString>(Microsoft::WRL::Wrappers::HString * const,Microsoft::WRL::Wrappers::HString &&)
0x1800ebf97  lea     rcx, [rbp+90h+var_78]
0x1800ebf9b  call    ??0?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@QEAA@XZ; std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>(void)
0x1800ebfa0  mov     rdx, rax
0x1800ebfa3  mov     [rbp+90h+var_E0], rsi
0x1800ebfa7  lea     rcx, [rbp+90h+var_D8]
0x1800ebfab  call    ??0?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@$0A@@std@@@std@@IEAA@$$QEAV01@@Z; std::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>(std::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>> &&)
0x1800ebfb0  mov     rdx, qword ptr [rsp+190h+var_160+8]
0x1800ebfb5  cmp     rdx, [rsp+190h+var_150]
0x1800ebfba  jz      short loc_1800EBFD8
0x1800ebfbc  mov     rax, [rbp+90h+var_E0]
0x1800ebfc0  lea     rcx, [rdx+8]
0x1800ebfc4  mov     [rdx], rax
0x1800ebfc7  lea     rdx, [rbp+90h+var_D8]
0x1800ebfcb  call    ??0?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@$0A@@std@@@std@@IEAA@$$QEAV01@@Z; std::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>(std::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>> &&)
0x1800ebfd0  add     qword ptr [rsp+190h+var_160+8], 48h ; 'H'
0x1800ebfd6  jmp     short loc_1800EBFE6
0x1800ebfd8  lea     r8, [rbp+90h+var_E0]
0x1800ebfdc  lea     rcx, [rsp+190h+var_160]
0x1800ebfe1  call    ??$_Emplace_reallocate@U?$pair@PEAVCompositionAnimation@Composition@UI@Windows@@V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@@std@@@?$vector@U?$pair@PEAVCompositionAnimation@Composition@UI@Windows@@V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@@std@@V?$allocator@U?$pair@PEAVCompositionAnimation@Composition@UI@Windows@@V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@@std@@@2@@std@@AEAAPEAU?$pair@PEAVCompositionAnimation@Composition@UI@Windows@@V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@@1@QEAU21@$$QEAU21@@Z
0x1800ebfe6  lea     rcx, [rbp+90h+var_D8]
0x1800ebfea  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>::~_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>(void)
0x1800ebfef  lea     rcx, [rbp+90h+var_78]
0x1800ebff3  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>::~_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>(void)
0x1800ebff8  mov     rcx, [rsp+190h+string]; string
0x1800ebffd  call    cs:__imp_WindowsDeleteString
0x1800ec003  mov     rbx, [rbx]
0x1800ec006  jmp     loc_1800EBF14
0x1800ec00b  mov     rcx, [rbp+98h]; this
0x1800ec012  lea     r8, aOnecoreuapWind_213; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x1800ec019  mov     r9d, edi; char *
0x1800ec01c  mov     edx, 188h; void *
0x1800ec021  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ec026  mov     rcx, [rsp+190h+string]; string
0x1800ec02b  call    cs:__imp_WindowsDeleteString
0x1800ec031  lea     rcx, [rsp+190h+var_128]
0x1800ec036  mov     [rsp+190h+string], r15
0x1800ec03b  call    ?_Tidy@?$vector@VHString@Wrappers@WRL@Microsoft@@V?$allocator@VHString@Wrappers@WRL@Microsoft@@@std@@@std@@AEAAXXZ; std::vector<Microsoft::WRL::Wrappers::HString>::_Tidy(void)
0x1800ec040  mov     rcx, qword ptr [rsp+190h+var_160]
0x1800ec045  test    rcx, rcx
0x1800ec048  jz      short loc_1800EC092
0x1800ec04a  mov     rdx, qword ptr [rsp+190h+var_160+8]
0x1800ec04f  call    ??$_Destroy_range@V?$allocator@U?$pair@PEAVCompositionAnimation@Composition@UI@Windows@@V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@@std@@@std@@@std@@YAXPEAU?$pair@PEAVCompositionAnimation@Composition@UI@Windows@@V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@@0@QEAU10@AEAV?$allocator@U?$pair@PEAVCompositionAnimation@Composition@UI@Windows@@V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::pair<Windows::UI::Composition::CompositionAnimation *,std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>>>>(std::pair<Windows::UI::Composition::CompositionAnimation *,std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>> *,std::pair<Windows::UI::Composition::CompositionAnimation *,std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>> * const,std::allocator<std::pair<Windows::UI::Composition::CompositionAnimation *,std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>>> &)
0x1800ec054  mov     rcx, qword ptr [rsp+190h+var_160]
0x1800ec059  mov     r15, 8E38E38E38E38E39h
0x1800ec063  mov     rax, [rsp+190h+var_150]
0x1800ec068  sub     rax, rcx
0x1800ec06b  sar     rax, 3
0x1800ec06f  imul    rax, r15
0x1800ec073  lea     rdx, [rax+rax*8]
0x1800ec077  shl     rdx, 3
0x1800ec07b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800ec080  xorps   xmm0, xmm0
0x1800ec083  mov     [rsp+190h+var_150], 0
0x1800ec08c  movdqu  [rsp+190h+var_160], xmm0
0x1800ec092  mov     ebx, edi
0x1800ec094  jmp     loc_1800EC3E0
0x1800ec099  call    ?ReturnHrMsgInvalidArgument@Composition@UI@Windows@@YAJW4ApiError@123@@Z; Windows::UI::Composition::ReturnHrMsgInvalidArgument(Windows::UI::Composition::ApiError)
0x1800ec09e  mov     rcx, [rsp+190h+string]; string
0x1800ec0a3  mov     ebx, eax
0x1800ec0a5  call    cs:__imp_WindowsDeleteString
0x1800ec0ab  lea     rcx, [rsp+190h+var_128]
0x1800ec0b0  mov     [rsp+190h+string], r15
0x1800ec0b5  call    ?_Tidy@?$vector@VHString@Wrappers@WRL@Microsoft@@V?$allocator@VHString@Wrappers@WRL@Microsoft@@@std@@@std@@AEAAXXZ; std::vector<Microsoft::WRL::Wrappers::HString>::_Tidy(void)
0x1800ec0ba  mov     rcx, qword ptr [rsp+190h+var_160]
0x1800ec0bf  test    rcx, rcx
0x1800ec0c2  jz      loc_1800EC3E0
0x1800ec0c8  mov     rdx, qword ptr [rsp+190h+var_160+8]
0x1800ec0cd  call    ??$_Destroy_range@V?$allocator@U?$pair@PEAVCompositionAnimation@Composition@UI@Windows@@V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@@std@@@std@@@std@@YAXPEAU?$pair@PEAVCompositionAnimation@Composition@UI@Windows@@V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@@0@QEAU10@AEAV?$allocator@U?$pair@PEAVCompositionAnimation@Composition@UI@Windows@@V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::pair<Windows::UI::Composition::CompositionAnimation *,std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>>>>(std::pair<Windows::UI::Composition::CompositionAnimation *,std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>> *,std::pair<Windows::UI::Composition::CompositionAnimation *,std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>> * const,std::allocator<std::pair<Windows::UI::Composition::CompositionAnimation *,std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>>> &)
0x1800ec0d2  mov     rcx, qword ptr [rsp+190h+var_160]
0x1800ec0d7  mov     r15, 8E38E38E38E38E39h
0x1800ec0e1  mov     rdx, [rsp+190h+var_150]
0x1800ec0e6  sub     rdx, rcx
0x1800ec0e9  sar     rdx, 3
0x1800ec0ed  imul    rdx, r15
0x1800ec0f1  lea     rdx, [rdx+rdx*8]
0x1800ec0f5  shl     rdx, 3
0x1800ec0f9  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800ec0fe  mov     [rsp+190h+var_150], 0
0x1800ec107  jmp     loc_1800EC3D7
0x1800ec10c  mov     rbx, [rsp+190h+var_128]
0x1800ec111  lea     rcx, [rbp+90h+var_110]
0x1800ec115  mov     rdx, [rsp+190h+var_128+8]
0x1800ec11a  sub     rdx, rbx
0x1800ec11d  sar     rdx, 3
0x1800ec121  call    ??0?$extent_type@$0?0@details@gsl@@QEAA@_K@Z; gsl::details::extent_type<-1>::extent_type<-1>(unsigned __int64)
0x1800ec126  mov     rdi, [rbp+90h+var_110]
0x1800ec12a  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800ec12e  jz      loc_1800EC478
0x1800ec134  test    rbx, rbx
0x1800ec137  jnz     short loc_1800EC142
0x1800ec139  test    rdi, rdi
0x1800ec13c  jnz     loc_1800EC478
0x1800ec142  mov     rsi, qword ptr [rsp+190h+var_160]
0x1800ec147  lea     rcx, [rbp+90h+var_110]
0x1800ec14b  mov     rdx, qword ptr [rsp+190h+var_160+8]
0x1800ec150  mov     r15, 8E38E38E38E38E39h
0x1800ec15a  sub     rdx, rsi
0x1800ec15d  sar     rdx, 3
0x1800ec161  imul    rdx, r15
0x1800ec165  call    ??0?$extent_type@$0?0@details@gsl@@QEAA@_K@Z; gsl::details::extent_type<-1>::extent_type<-1>(unsigned __int64)
0x1800ec16a  mov     rax, [rbp+90h+var_110]
0x1800ec16e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800ec172  jz      loc_1800EC478
0x1800ec178  test    rsi, rsi
0x1800ec17b  jnz     short loc_1800EC186
0x1800ec17d  test    rax, rax
0x1800ec180  jnz     loc_1800EC478
0x1800ec186  lea     r8, [rbp+90h+var_110]
0x1800ec18a  mov     [rbp+90h+var_110], rdi
0x1800ec18e  mov     rdx, r14
0x1800ec191  mov     [rbp+90h+var_108], rbx
0x1800ec195  lea     rcx, [rbp+90h+var_F0]
0x1800ec199  mov     [rbp+90h+var_F0], rax
0x1800ec19d  mov     [rbp+90h+var_E8], rsi
0x1800ec1a1  call    ?ResolvePropertiesWithIAnimationObjectTarget_Callback@AnimationHelper@Composition@UI@Windows@@YAJV?$span@U?$pair@PEAVCompositionAnimation@Composition@UI@Windows@@V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@@std@@$0?0@gsl@@PEAUIAnimationObject@234@V?$span@VHString@Wrappers@WRL@Microsoft@@$0?0@6@@Z; Windows::UI::Composition::AnimationHelper::ResolvePropertiesWithIAnimationObjectTarget_Callback(gsl::span<std::pair<Windows::UI::Composition::CompositionAnimation *,std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>>,-1>,Windows::UI::Composition::IAnimationObject *,gsl::span<Microsoft::WRL::Wrappers::HString,-1>)
0x1800ec1a6  xor     edi, edi
0x1800ec1a8  mov     ebx, eax
0x1800ec1aa  test    eax, eax
0x1800ec1ac  jns     short loc_1800EC1CE
0x1800ec1ae  mov     r9d, eax; char *
0x1800ec1b1  mov     edx, 195h; void *
0x1800ec1b6  mov     rcx, [rbp+98h]; this
0x1800ec1bd  lea     r8, aOnecoreuapWind_213; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x1800ec1c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ec1c9  jmp     loc_1800EC392
0x1800ec1ce  mov     eax, [rsp+190h+var_140]
0x1800ec1d2  cmp     eax, [r12+0C8h]
0x1800ec1da  jz      short loc_1800EC1EB
0x1800ec1dc  mov     ebx, 8000000Ch
0x1800ec1e1  mov     edx, 19Ah
0x1800ec1e6  mov     r9d, ebx
0x1800ec1e9  jmp     short loc_1800EC1B6
0x1800ec1eb  mov     rbx, [r12+0B8h]
0x1800ec1f3  mov     ecx, edi
0x1800ec1f5  mov     [rbp+90h+var_F0], rbx
0x1800ec1f9  mov     rax, [r12+0B8h]
0x1800ec201  mov     edx, edi
0x1800ec203  mov     [rsp+190h+var_140], ecx
0x1800ec207  jmp     short loc_1800EC20E
0x1800ec209  mov     rax, [rax]
0x1800ec20c  inc     edx
0x1800ec20e  test    rax, rax
0x1800ec211  jnz     short loc_1800EC209
0x1800ec213  cmp     ecx, edx
0x1800ec215  jge     loc_1800EC419
0x1800ec21b  mov     qword ptr [rsp+190h+var_130], rdi
0x1800ec220  mov     rax, [rbx+10h]
0x1800ec224  movsxd  rbx, ecx
0x1800ec227  lea     rcx, [rsp+190h+var_160]
0x1800ec22c  mov     rdx, rbx
0x1800ec22f  mov     [rbp+90h+var_100], rdi
0x1800ec233  mov     [rbp+90h+var_110], rax
0x1800ec237  call    ?at@?$vector@U?$pair@PEAVCompositionAnimation@Composition@UI@Windows@@V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@@std@@V?$allocator@U?$pair@PEAVCompositionAnimation@Composition@UI@Windows@@V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@@std@@@2@@std@@QEAAAEAU?$pair@PEAVCompositionAnimation@Composition@UI@Windows@@V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@@2@_K@Z; std::vector<std::pair<Windows::UI::Composition::CompositionAnimation *,std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>>>::at(unsigned __int64)
0x1800ec23c  mov     rcx, [rsp+190h+var_128]; char *
0x1800ec241  mov     rdx, [rsp+190h+var_128+8]
0x1800ec246  sub     rdx, rcx
0x1800ec249  sar     rdx, 3
0x1800ec24d  cmp     rdx, rbx
0x1800ec250  jbe     loc_1800EC413
0x1800ec256  mov     rcx, [rcx+rbx*8]; string
0x1800ec25a  lea     r14, [rax+8]
0x1800ec25e  xor     edx, edx; length
0x1800ec260  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ec266  mov     rdx, rax
0x1800ec269  lea     rcx, [rbp+90h+var_98]
0x1800ec26d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800ec272  lea     rdx, aThisTarget; "this.target"
0x1800ec279  lea     rcx, [rbp+90h+var_78]
0x1800ec27d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800ec282  lea     rdx, [rbp+90h+var_78]
0x1800ec286  mov     rcx, r14
0x1800ec289  call    ?at@?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@URedirectedPropertyInfo@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@URedirectedPropertyInfo@Composition@UI@Windows@@@std@@@2@@std@@QEBAAEBURedirectedPropertyInfo@Composition@UI@Windows@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::unordered_map<std::wstring,Windows::UI::Composition::RedirectedPropertyInfo>::at(std::wstring const &)
0x1800ec28e  lea     rcx, [rbp+90h+var_78]
0x1800ec292  mov     rbx, rax
0x1800ec295  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ec29a  lea     rcx, [rbx+8]
0x1800ec29e  lea     rdx, [rbp+90h+var_98]
0x1800ec2a2  call    ?at@?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@URedirectedPropertyInfo@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@URedirectedPropertyInfo@Composition@UI@Windows@@@std@@@2@@std@@QEBAAEBURedirectedPropertyInfo@Composition@UI@Windows@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::unordered_map<std::wstring,Windows::UI::Composition::RedirectedPropertyInfo>::at(std::wstring const &)
0x1800ec2a7  lea     rcx, [rbp+90h+var_100]
0x1800ec2ab  mov     rsi, rax
0x1800ec2ae  mov     rdx, [rax+10h]
0x1800ec2b2  call    ??4?$RefPtr@VCompositionObject@Composition@UI@Windows@@@WRL2@Microsoft@@QEAAAEAV012@PEAVCompositionObject@Composition@UI@Windows@@@Z; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionObject>::operator=(Windows::UI::Composition::CompositionObject *)
0x1800ec2b7  mov     rdi, [rbp+90h+var_100]
0x1800ec2bb  lea     rcx, [rsp+190h+var_130]; void *
0x1800ec2c0  mov     rdx, [rdi]
0x1800ec2c3  mov     rbx, [rdx+98h]
0x1800ec2ca  call    ?InternalUnlock@?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(void)
0x1800ec2cf  mov     r8, [rbp+90h+var_110]
0x1800ec2d3  lea     rax, [rsp+190h+var_130]
0x1800ec2d8  mov     rdx, [rsi]
0x1800ec2db  mov     r9, r14
0x1800ec2de  mov     qword ptr [rsp+190h+var_170], rax; int
0x1800ec2e3  mov     rcx, rdi
0x1800ec2e6  mov     rax, rbx
0x1800ec2e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec2ee  xor     edi, edi
0x1800ec2f0  mov     ebx, eax
0x1800ec2f2  test    eax, eax
0x1800ec2f4  js      short loc_1800EC35B
0x1800ec2f6  test    r13, r13
0x1800ec2f9  jz      short loc_1800EC329
0x1800ec2fb  mov     rax, qword ptr [rsp+190h+var_130]
0x1800ec300  mov     rdx, [r13+8]
0x1800ec304  mov     qword ptr [rsp+190h+var_130], rdi
0x1800ec309  mov     [rbp+90h+var_110], rax
0x1800ec30d  cmp     rdx, [r13+10h]
0x1800ec311  jz      short loc_1800EC31D
0x1800ec313  mov     [rdx], rax
0x1800ec316  add     qword ptr [r13+8], 8
0x1800ec31b  jmp     short loc_1800EC329
0x1800ec31d  lea     r8, [rbp+90h+var_110]
0x1800ec321  mov     rcx, r13
0x1800ec324  call    ??$_Emplace_reallocate@PEAVCCompositionTextureBinding@DirectComposition@@@?$vector@PEAVCCompositionTextureBinding@DirectComposition@@V?$allocator@PEAVCCompositionTextureBinding@DirectComposition@@@std@@@std@@AEAAPEAPEAVCCompositionTextureBinding@DirectComposition@@QEAPEAV23@$$QEAPEAV23@@Z; std::vector<DirectComposition::CCompositionTextureBinding *>::_Emplace_reallocate<DirectComposition::CCompositionTextureBinding *>(DirectComposition::CCompositionTextureBinding * * const,DirectComposition::CCompositionTextureBinding * &&)
0x1800ec329  mov     rbx, [rbp+90h+var_F0]
  ... truncated ...
```
