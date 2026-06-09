# Windows::UI::Composition::CompositionAnimationGroup::PlayAnimations(Windows::UI::Composition::CompositionObject *,Windows::UI::Composition::AnimationValueData const *,Windows::UI::Composition::AnimationValueSynchronizationBehavior,bool *,std::vector<Windows::UI::Composition::CompositionPropertyAnimator *,std::allocator<Windows::UI::Composition::CompositionPropertyAnimator *>> *)

- ea: `0x180072668`
- end: `0x180072b10`
- name: `?PlayAnimations@CompositionAnimationGroup@Composition@UI@Windows@@QEAAJPEAVCompositionObject@234@PEBUAnimationValueData@234@W4AnimationValueSynchronizationBehavior@234@PEA_NPEAV?$vector@PEAVCompositionPropertyAnimator@Composition@UI@Windows@@V?$allocator@PEAVCompositionPropertyAnimator@Composition@UI@Windows@@@std@@@std@@@Z`
- size: `1192`
- prototype: ``
- caller_count: `3`
- callee_count: `20`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180072b50`
- `0x180074ab8`
- `0x1800ebe2c`

## callees

- `0x1800092fc`
- `0x18000a68c`
- `0x18000aca4`
- `0x18000bc00`
- `0x18000f810`
- `0x18001358c`
- `0x18005143c`
- `0x180072668`
- `0x180074480`
- `0x1800744bc`
- `0x1800751ec`
- `0x1800752c8`
- `0x1800755d8`
- `0x18008e2b8`
- `0x1800add48`
- `0x1800ec48c`
- `0x1801409cc`
- `0x180140a04`
- `0x180141000`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072735`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800727d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072914`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072ab7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072735`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800727d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072914`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072ab7`

## string_xrefs

- `0x180072884`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositionanimationgroup.cpp`
- `0x180072aa3`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositionanimationgroup.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::CompositionAnimationGroup::PlayAnimations(
        __int64 a1,
        HSTRING a2,
        struct Windows::UI::Composition::CompositionAnimation *a3,
        int a4,
        _BYTE *a5,
        __int64 a6)
{
  char v6; // r15
  __int64 **i; // rbx
  Microsoft::WRL2::NestableRuntimeClass *v10; // rbx
  _QWORD *v11; // r14
  unsigned int v12; // r13d
  __int64 v13; // rdi
  __int64 v14; // rsi
  __int64 v15; // r12
  HSTRING v16; // r8
  __int64 (__fastcall *v17)(HSTRING, Microsoft::WRL::Wrappers::Details *, __int64, __int64); // rbx
  int v18; // ebx
  Microsoft::WRL2::NestableRuntimeClass *v19; // rcx
  int v21; // esi
  HSTRING v22; // rcx
  __int64 v23; // rdx
  Microsoft::WRL2::NestableRuntimeClass *v24; // rcx
  Microsoft::WRL2::NestableRuntimeClass *v25; // rax
  Microsoft::WRL2::NestableRuntimeClass **v26; // rdx
  __int64 v27; // rax
  __int64 v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // rdx
  int v31; // [rsp+28h] [rbp-C9h]
  Microsoft::WRL2::NestableRuntimeClass **v32; // [rsp+28h] [rbp-C9h]
  bool *v33; // [rsp+30h] [rbp-C1h]
  Microsoft::WRL::Wrappers::Details *string; // [rsp+38h] [rbp-B9h] BYREF
  HSTRING string_8[2]; // [rsp+40h] [rbp-B1h] BYREF
  HSTRING v36; // [rsp+50h] [rbp-A1h]
  Microsoft::WRL2::NestableRuntimeClass *v37[2]; // [rsp+58h] [rbp-99h] BYREF
  __int64 *v38; // [rsp+68h] [rbp-89h] BYREF
  _BYTE v39[64]; // [rsp+70h] [rbp-81h] BYREF
  _BYTE v40[136]; // [rsp+B0h] [rbp-41h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+140h] [rbp+4Fh]
  Microsoft::WRL2::NestableRuntimeClass *v42; // [rsp+148h] [rbp+57h] BYREF
  HSTRING v43; // [rsp+150h] [rbp+5Fh]
  struct Windows::UI::Composition::CompositionAnimation *v44; // [rsp+158h] [rbp+67h]
  int v45; // [rsp+160h] [rbp+6Fh]

  v45 = a4;
  v44 = a3;
  v43 = a2;
  v6 = 0;
  v36 = 0;
  *(_OWORD *)string_8 = 0;
  *a5 = 0;
  for ( i = *(__int64 ***)(a1 + 184); i; i = (__int64 **)*i )
  {
    Windows::UI::Composition::CompositionAnimation::TryPopulateAnimationObjectParametersInfo(
      (Windows::UI::Composition::CompositionAnimation *)i[2],
      0);
    if ( -858993459 * (unsigned int)((i[2][42] - i[2][41]) >> 3) )
    {
      v27 = std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>(v40);
      v38 = i[2];
      std::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>(
        v39,
        v27);
      if ( string_8[1] == v36 )
      {
        ____Emplace_reallocate_U__pair_PEAVCompositionAnimation_Composition_UI_Windows__V__unordered_map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__UParameterOverrideEntry_Composition_UI_Windows__U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__UParameterOverrideEntry_Composition_UI_Windows___std___2__std___std_____vector_U__pair_PEAVCompositionAnimation_Composition_UI_Windows__V__unordered_map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__UParameterOverrideEntry_Composition_UI_Windows__U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__UParameterOverrideEntry_Composition_UI_Windows___std___2__std___std__V__allocator_U__pair_PEAVCompositionAnimation_Composition_UI_Windows__V__unordered_map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__UParameterOverrideEntry_Composition_UI_Windows__U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__UParameterOverrideEntry_Composition_UI_Windows___std___2__std___std___2__std__AEAAPEAU__pair_PEAVCompositionAnimation_Composition_UI_Windows__V__unordered_map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__UParameterOverrideEntry_Composition_UI_Windows__U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__UParameterOverrideEntry_Composition_UI_Windows___std___2__std___1_QEAU21___QEAU21__Z(
          string_8,
          string_8[1],
          &v38);
      }
      else
      {
        v28 = (__int64)(string_8[1] + 2);
        *(_QWORD *)string_8[1] = v38;
        std::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>(
          v28,
          v39);
        string_8[1] += 18;
      }
      std::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>::~_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>(v39);
      std::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>::~_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>(v40);
    }
  }
  v10 = (Microsoft::WRL2::NestableRuntimeClass *)string_8[0];
  if ( string_8[0] == string_8[1] )
    goto LABEL_4;
  v21 = *(_DWORD *)(a1 + 200);
  gsl::details::extent_type<-1>::extent_type<-1>(
    v37,
    0x8E38E38E38E38E39uLL * (((char *)string_8[1] - (char *)string_8[0]) >> 3));
  if ( v37[0] == (Microsoft::WRL2::NestableRuntimeClass *)-1LL || !v10 && v37[0] )
  {
    ((void (*)(void))`gsl::details::get_terminate_handler'::`2'::handler)();
    __debugbreak();
  }
  v37[1] = v10;
  Windows::UI::Composition::AnimationHelper::ResolvePropertiesWithoutIAnimationObjectTarget_Callback(v37, a2);
  if ( v21 == *(_DWORD *)(a1 + 200) )
  {
LABEL_4:
    v11 = *(_QWORD **)(a1 + 184);
    v12 = 0;
    v13 = a6;
    while ( 1 )
    {
      if ( !v11 )
      {
        if ( string_8[0] )
        {
          std::_Destroy_range<std::allocator<std::pair<Windows::UI::Composition::CompositionAnimation *,std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>>>>(
            string_8[0],
            string_8[1]);
          std::_Deallocate<16>(string_8[0], 8 * (((char *)v36 - (char *)string_8[0]) >> 3));
        }
        return 0;
      }
      v14 = v11[2];
      v37[0] = 0;
      v15 = 0;
      if ( -858993459 * (unsigned int)((__int64)(*(_QWORD *)(v14 + 336) - *(_QWORD *)(v14 + 328)) >> 3) )
      {
        v29 = v12++;
        v15 = std::vector<std::pair<Windows::UI::Composition::CompositionAnimation *,std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>>>::at(
                string_8,
                v29)
            + 8;
      }
      string = 0;
      WindowsDeleteString(0);
      string = 0;
      Windows::UI::Composition::CompositionAnimation::GetTarget(
        (Windows::UI::Composition::CompositionAnimation *)v14,
        (HSTRING *)&string);
      if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(string, 0, v16) )
        break;
      LOBYTE(v42) = 0;
      if ( v44 )
      {
        v18 = Windows::UI::Composition::AnimationHelper::SetFinalValueParameter(
                string,
                v43,
                (struct Windows::UI::Composition::CompositionObject *)v14,
                v44,
                (const struct Windows::UI::Composition::AnimationValueData *)&v42,
                v33);
        if ( v18 < 0 )
        {
          v30 = 268;
          goto LABEL_47;
        }
        v6 = (char)v42;
      }
      if ( v45 )
        *(_DWORD *)(v14 + 312) = v45;
      v17 = *(__int64 (__fastcall **)(HSTRING, Microsoft::WRL::Wrappers::Details *, __int64, __int64))(*(_QWORD *)v43 + 152LL);
      Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(v37);
      v32 = v37;
      v18 = v17(v43, string, v14, v15);
      if ( v18 < 0 )
      {
        v30 = 286;
LABEL_47:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v30,
          (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositionanimationgroup.cpp",
          (const char *)(unsigned int)v18,
          (int)v32);
        WindowsDeleteString((HSTRING)string);
        string = 0;
        Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(v37);
        goto LABEL_32;
      }
      if ( v13 )
      {
        v25 = v37[0];
        v26 = *(Microsoft::WRL2::NestableRuntimeClass ***)(v13 + 8);
        v37[0] = 0;
        v42 = v25;
        if ( v26 == *(Microsoft::WRL2::NestableRuntimeClass ***)(v13 + 16) )
        {
          std::vector<DirectComposition::CCompositionTextureBinding *>::_Emplace_reallocate<DirectComposition::CCompositionTextureBinding *>(
            v13,
            v26,
            &v42);
        }
        else
        {
          *v26 = v25;
          *(_QWORD *)(v13 + 8) += 8LL;
        }
      }
      if ( v6 )
        *a5 = 1;
      WindowsDeleteString((HSTRING)string);
      v19 = v37[0];
      v6 = 0;
      string = 0;
      if ( v37[0] )
      {
        v37[0] = 0;
        Microsoft::WRL2::NestableRuntimeClass::InternalRelease(v19);
      }
      v11 = (_QWORD *)*v11;
    }
    v18 = Windows::UI::Composition::ReturnHrMsgInvalidArgument();
    WindowsDeleteString((HSTRING)string);
    v24 = v37[0];
    string = 0;
    if ( v37[0] )
    {
      v37[0] = 0;
      Microsoft::WRL2::NestableRuntimeClass::InternalRelease(v24);
    }
LABEL_32:
    if ( !string_8[0] )
      return (unsigned int)v18;
    std::_Destroy_range<std::allocator<std::pair<Windows::UI::Composition::CompositionAnimation *,std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>>>>(
      string_8[0],
      string_8[1]);
    v22 = string_8[0];
    v23 = ((char *)v36 - (char *)string_8[0]) >> 3;
    goto LABEL_42;
  }
  v18 = -2147483636;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xE1,
    (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositionanimationgroup.cpp",
    (const char *)0x8000000CLL,
    v31);
  if ( string_8[0] )
  {
    std::_Destroy_range<std::allocator<std::pair<Windows::UI::Composition::CompositionAnimation *,std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>>>>(
      string_8[0],
      string_8[1]);
    v22 = string_8[0];
    v23 = ((char *)v36 - (char *)string_8[0]) >> 3;
LABEL_42:
    std::_Deallocate<16>(v22, 8 * v23);
  }
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x180072668  mov     rax, rsp
0x18007266b  mov     [rax+20h], r9d
0x18007266f  mov     [rax+18h], r8
0x180072673  mov     [rax+10h], rdx
0x180072677  push    rbp
0x180072678  push    rbx
0x180072679  push    rsi
0x18007267a  push    rdi
0x18007267b  push    r12
0x18007267d  push    r13
0x18007267f  push    r14
0x180072681  push    r15
0x180072683  lea     rbp, [rax-4Fh]
0x180072687  sub     rsp, 0F8h
0x18007268e  mov     rax, [rbp+47h+arg_20]
0x180072692  xor     r15d, r15d
0x180072695  xorps   xmm0, xmm0
0x180072698  mov     [rsp+130h+var_E8], r15
0x18007269d  mov     r14, rdx
0x1800726a0  mov     rdi, rcx
0x1800726a3  movdqu  xmmword ptr [rsp+130h+string+8], xmm0
0x1800726a9  mov     [rax], r15b
0x1800726ac  mov     rsi, 0CCCCCCCCCCCCCCCDh
0x1800726b6  mov     rbx, [rcx+0B8h]
0x1800726bd  test    rbx, rbx
0x1800726c0  jnz     loc_1800728D3
0x1800726c6  mov     rdx, [rsp+130h+var_F0]
0x1800726cb  mov     r12, 8E38E38E38E38E39h
0x1800726d5  mov     rbx, [rsp+130h+string+8]
0x1800726da  cmp     rbx, rdx
0x1800726dd  jnz     loc_180072825
0x1800726e3  mov     r14, [rdi+0B8h]
0x1800726ea  mov     r13d, r15d
0x1800726ed  mov     rdi, [rbp+47h+arg_28]
0x1800726f1  test    r14, r14
0x1800726f4  jz      loc_180072801
0x1800726fa  mov     rsi, [r14+10h]
0x1800726fe  mov     rcx, 0CCCCCCCCCCCCCCCDh
0x180072708  mov     [rsp+130h+var_E0], r15
0x18007270d  mov     r12, r15
0x180072710  mov     rax, [rsi+150h]
0x180072717  sub     rax, [rsi+148h]
0x18007271e  sar     rax, 3
0x180072722  imul    rax, rcx
0x180072726  test    eax, eax
0x180072728  jnz     loc_180072A3A
0x18007272e  xor     ecx, ecx; string
0x180072730  mov     [rsp+130h+string], r15
0x180072735  call    cs:__imp_WindowsDeleteString
0x18007273b  lea     rdx, [rsp+130h+string]; HSTRING *
0x180072740  mov     [rsp+130h+string], r15
0x180072745  mov     rcx, rsi; this
0x180072748  call    ?GetTarget@CompositionAnimation@Composition@UI@Windows@@QEAAXPEAPEAUHSTRING__@@@Z; Windows::UI::Composition::CompositionAnimation::GetTarget(HSTRING__ * *)
0x18007274d  mov     rcx, [rsp+130h+string]; this
0x180072752  xor     edx, edx; HSTRING
0x180072754  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x180072759  test    eax, eax
0x18007275b  jz      loc_180072908
0x180072761  mov     rax, [rbp+47h+arg_10]
0x180072765  mov     byte ptr [rbp+47h+arg_0], r15b
0x180072769  test    rax, rax
0x18007276c  jnz     loc_180072A53
0x180072772  mov     eax, [rbp+47h+arg_18]
0x180072775  test    eax, eax
0x180072777  jnz     loc_180072A83
0x18007277d  mov     rax, [rbp+47h+arg_8]
0x180072781  lea     rcx, [rsp+130h+var_E0]; void *
0x180072786  mov     rax, [rax]
0x180072789  mov     rbx, [rax+98h]
0x180072790  call    ?InternalUnlock@?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(void)
0x180072795  mov     rdx, [rsp+130h+string]
0x18007279a  lea     rax, [rsp+130h+var_E0]
0x18007279f  mov     rcx, [rbp+47h+arg_8]
0x1800727a3  mov     r9, r12
0x1800727a6  mov     [rsp+20h], rax; int
0x1800727ab  mov     r8, rsi
0x1800727ae  mov     rax, rbx
0x1800727b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800727b6  mov     ebx, eax
0x1800727b8  test    eax, eax
0x1800727ba  js      loc_180072A9A
0x1800727c0  test    rdi, rdi
0x1800727c3  jnz     loc_180072948
0x1800727c9  test    r15b, r15b
0x1800727cc  jnz     loc_180072A8E
0x1800727d2  mov     rcx, [rsp+130h+string]; string
0x1800727d7  call    cs:__imp_WindowsDeleteString
0x1800727dd  mov     rcx, [rsp+130h+var_E0]; this
0x1800727e2  xor     r15d, r15d
0x1800727e5  mov     [rsp+130h+string], r15
0x1800727ea  test    rcx, rcx
0x1800727ed  jz      short loc_1800727F9
0x1800727ef  mov     [rsp+130h+var_E0], r15
0x1800727f4  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x1800727f9  mov     r14, [r14]
0x1800727fc  jmp     loc_1800726F1
0x180072801  mov     rcx, [rsp+130h+string+8]
0x180072806  test    rcx, rcx
0x180072809  jnz     loc_180072AD5
0x18007280f  xor     eax, eax
0x180072811  add     rsp, 0F8h
0x180072818  pop     r15
0x18007281a  pop     r14
0x18007281c  pop     r13
0x18007281e  pop     r12
0x180072820  pop     rdi
0x180072821  pop     rsi
0x180072822  pop     rbx
0x180072823  pop     rbp
0x180072824  retn
0x180072825  mov     esi, [rdi+0C8h]
0x18007282b  lea     rcx, [rsp+130h+var_E0]
0x180072830  sub     rdx, rbx
0x180072833  sar     rdx, 3
0x180072837  imul    rdx, r12
0x18007283b  call    ??0?$extent_type@$0?0@details@gsl@@QEAA@_K@Z; gsl::details::extent_type<-1>::extent_type<-1>(unsigned __int64)
0x180072840  mov     rax, [rsp+130h+var_E0]
0x180072845  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180072849  jz      loc_180072A2D
0x18007284f  test    rbx, rbx
0x180072852  jnz     short loc_18007285D
0x180072854  test    rax, rax
0x180072857  jnz     loc_180072A2D
0x18007285d  mov     rdx, r14
0x180072860  mov     [rsp+130h+var_E0], rax
0x180072865  lea     rcx, [rsp+130h+var_E0]
0x18007286a  mov     [rsp+130h+var_D8], rbx
0x18007286f  call    ?ResolvePropertiesWithoutIAnimationObjectTarget_Callback@AnimationHelper@Composition@UI@Windows@@YAJV?$span@U?$pair@PEAVCompositionAnimation@Composition@UI@Windows@@V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@@std@@$0?0@gsl@@PEAVCompositionObject@234@@Z; Windows::UI::Composition::AnimationHelper::ResolvePropertiesWithoutIAnimationObjectTarget_Callback(gsl::span<std::pair<Windows::UI::Composition::CompositionAnimation *,std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>>,-1>,Windows::UI::Composition::CompositionObject *)
0x180072874  cmp     esi, [rdi+0C8h]
0x18007287a  jz      loc_1800726E3
0x180072880  mov     rcx, [rbp+4Fh]; this
0x180072884  lea     r8, aOnecoreuapWind_213; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x18007288b  mov     ebx, 8000000Ch
0x180072890  mov     edx, 0E1h; void *
0x180072895  mov     r9d, ebx; char *
0x180072898  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007289d  mov     rcx, [rsp+130h+string+8]
0x1800728a2  test    rcx, rcx
0x1800728a5  jz      loc_180072941
0x1800728ab  mov     rdx, [rsp+130h+var_F0]
0x1800728b0  call    ??$_Destroy_range@V?$allocator@U?$pair@PEAVCompositionAnimation@Composition@UI@Windows@@V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@@std@@@std@@@std@@YAXPEAU?$pair@PEAVCompositionAnimation@Composition@UI@Windows@@V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@@0@QEAU10@AEAV?$allocator@U?$pair@PEAVCompositionAnimation@Composition@UI@Windows@@V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::pair<Windows::UI::Composition::CompositionAnimation *,std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>>>>(std::pair<Windows::UI::Composition::CompositionAnimation *,std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>> *,std::pair<Windows::UI::Composition::CompositionAnimation *,std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>> * const,std::allocator<std::pair<Windows::UI::Composition::CompositionAnimation *,std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>>> &)
0x1800728b5  mov     rcx, [rsp+130h+string+8]
0x1800728ba  mov     rdx, [rsp+130h+var_E8]
0x1800728bf  sub     rdx, rcx
0x1800728c2  sar     rdx, 3
0x1800728c6  imul    rdx, r12
0x1800728ca  lea     rdx, [rdx+rdx*8]
0x1800728ce  jmp     loc_180072A1F
0x1800728d3  mov     rcx, [rbx+10h]; this
0x1800728d7  xor     edx, edx; bool
0x1800728d9  call    ?TryPopulateAnimationObjectParametersInfo@CompositionAnimation@Composition@UI@Windows@@QEAAX_N@Z; Windows::UI::Composition::CompositionAnimation::TryPopulateAnimationObjectParametersInfo(bool)
0x1800728de  mov     rax, [rbx+10h]
0x1800728e2  mov     rcx, [rax+150h]
0x1800728e9  sub     rcx, [rax+148h]
0x1800728f0  sar     rcx, 3
0x1800728f4  imul    rcx, rsi
0x1800728f8  test    ecx, ecx
0x1800728fa  jnz     loc_180072982
0x180072900  mov     rbx, [rbx]
0x180072903  jmp     loc_1800726BD
0x180072908  call    ?ReturnHrMsgInvalidArgument@Composition@UI@Windows@@YAJW4ApiError@123@@Z; Windows::UI::Composition::ReturnHrMsgInvalidArgument(Windows::UI::Composition::ApiError)
0x18007290d  mov     rcx, [rsp+130h+string]; string
0x180072912  mov     ebx, eax
0x180072914  call    cs:__imp_WindowsDeleteString
0x18007291a  mov     rcx, [rsp+130h+var_E0]; this
0x18007291f  mov     [rsp+130h+string], r15
0x180072924  test    rcx, rcx
0x180072927  jz      short loc_180072933
0x180072929  mov     [rsp+130h+var_E0], r15
0x18007292e  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x180072933  mov     rcx, [rsp+130h+string+8]
0x180072938  test    rcx, rcx
0x18007293b  jnz     loc_1800729F2
0x180072941  mov     eax, ebx
0x180072943  jmp     loc_180072811
0x180072948  mov     rax, [rsp+130h+var_E0]
0x18007294d  mov     rdx, [rdi+8]
0x180072951  mov     [rsp+130h+var_E0], 0
0x18007295a  mov     [rbp+47h+arg_0], rax
0x18007295e  cmp     rdx, [rdi+10h]
0x180072962  jz      short loc_180072971
0x180072964  mov     [rdx], rax
0x180072967  add     qword ptr [rdi+8], 8
0x18007296c  jmp     loc_1800727C9
0x180072971  lea     r8, [rbp+47h+arg_0]
0x180072975  mov     rcx, rdi
0x180072978  call    ??$_Emplace_reallocate@PEAVCCompositionTextureBinding@DirectComposition@@@?$vector@PEAVCCompositionTextureBinding@DirectComposition@@V?$allocator@PEAVCCompositionTextureBinding@DirectComposition@@@std@@@std@@AEAAPEAPEAVCCompositionTextureBinding@DirectComposition@@QEAPEAV23@$$QEAPEAV23@@Z; std::vector<DirectComposition::CCompositionTextureBinding *>::_Emplace_reallocate<DirectComposition::CCompositionTextureBinding *>(DirectComposition::CCompositionTextureBinding * * const,DirectComposition::CCompositionTextureBinding * &&)
0x18007297d  jmp     loc_1800727C9
0x180072982  lea     rcx, [rbp+47h+var_88]
0x180072986  call    ??0?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@QEAA@XZ; std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>(void)
0x18007298b  mov     rcx, [rbx+10h]
0x18007298f  mov     rdx, rax
0x180072992  mov     [rsp+130h+var_D0], rcx
0x180072997  lea     rcx, [rsp+68h]
0x18007299c  call    ??0?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@$0A@@std@@@std@@IEAA@$$QEAV01@@Z; std::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>(std::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>> &&)
0x1800729a1  mov     rdx, [rsp+130h+var_F0]
0x1800729a6  cmp     rdx, [rsp+130h+var_E8]
0x1800729ab  jz      short loc_1800729E1
0x1800729ad  mov     rax, [rsp+130h+var_D0]
0x1800729b2  lea     rcx, [rdx+8]
0x1800729b6  mov     [rdx], rax
0x1800729b9  lea     rdx, [rsp+68h]
0x1800729be  call    ??0?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@$0A@@std@@@std@@IEAA@$$QEAV01@@Z; std::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>(std::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>> &&)
0x1800729c3  add     [rsp+130h+var_F0], 48h ; 'H'
0x1800729c9  lea     rcx, [rsp+68h]
0x1800729ce  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>::~_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>(void)
0x1800729d3  lea     rcx, [rbp+47h+var_88]
0x1800729d7  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>::~_Hash<std::_Umap_traits<std::wstring,Windows::UI::Composition::ParameterOverrideEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::UI::Composition::ParameterOverrideEntry>>,0>>(void)
0x1800729dc  jmp     loc_180072900
0x1800729e1  lea     r8, [rsp+130h+var_D0]
0x1800729e6  lea     rcx, [rsp+130h+string+8]
0x1800729eb  call    ??$_Emplace_reallocate@U?$pair@PEAVCompositionAnimation@Composition@UI@Windows@@V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@@std@@@?$vector@U?$pair@PEAVCompositionAnimation@Composition@UI@Windows@@V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@@std@@V?$allocator@U?$pair@PEAVCompositionAnimation@Composition@UI@Windows@@V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@@std@@@2@@std@@AEAAPEAU?$pair@PEAVCompositionAnimation@Composition@UI@Windows@@V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@@1@QEAU21@$$QEAU21@@Z
0x1800729f0  jmp     short loc_1800729C9
0x1800729f2  mov     rdx, [rsp+130h+var_F0]
0x1800729f7  call    ??$_Destroy_range@V?$allocator@U?$pair@PEAVCompositionAnimation@Composition@UI@Windows@@V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@@std@@@std@@@std@@YAXPEAU?$pair@PEAVCompositionAnimation@Composition@UI@Windows@@V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@@0@QEAU10@AEAV?$allocator@U?$pair@PEAVCompositionAnimation@Composition@UI@Windows@@V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::pair<Windows::UI::Composition::CompositionAnimation *,std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>>>>(std::pair<Windows::UI::Composition::CompositionAnimation *,std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>> *,std::pair<Windows::UI::Composition::CompositionAnimation *,std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>> * const,std::allocator<std::pair<Windows::UI::Composition::CompositionAnimation *,std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>>> &)
0x1800729fc  mov     rcx, [rsp+130h+string+8]
0x180072a01  mov     rdx, 8E38E38E38E38E39h
0x180072a0b  mov     rax, [rsp+130h+var_E8]
0x180072a10  sub     rax, rcx
0x180072a13  sar     rax, 3
0x180072a17  imul    rax, rdx
0x180072a1b  lea     rdx, [rax+rax*8]
0x180072a1f  shl     rdx, 3
0x180072a23  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180072a28  jmp     loc_180072941
0x180072a2d  mov     rax, cs:?handler@?1??get_terminate_handler@details@gsl@@YAAEAP6AXXZXZ@4P6AXXZEA; void (*`gsl::details::get_terminate_handler(void)'::`2'::handler)(void)
0x180072a34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072a39  int     3; Trap to Debugger
0x180072a3a  mov     edx, r13d
0x180072a3d  lea     rcx, [rsp+130h+string+8]
0x180072a42  inc     r13d
0x180072a45  call    ?at@?$vector@U?$pair@PEAVCompositionAnimation@Composition@UI@Windows@@V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@@std@@V?$allocator@U?$pair@PEAVCompositionAnimation@Composition@UI@Windows@@V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@@std@@@2@@std@@QEAAAEAU?$pair@PEAVCompositionAnimation@Composition@UI@Windows@@V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@@2@_K@Z; std::vector<std::pair<Windows::UI::Composition::CompositionAnimation *,std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>>>::at(unsigned __int64)
0x180072a4a  lea     r12, [rax+8]
0x180072a4e  jmp     loc_18007272E
0x180072a53  mov     rdx, [rbp+47h+arg_8]; HSTRING
0x180072a57  lea     rcx, [rbp+47h+arg_0]
0x180072a5b  mov     [rsp+20h], rcx; struct Windows::UI::Composition::AnimationValueData *
0x180072a60  mov     r9, rax; struct Windows::UI::Composition::CompositionAnimation *
0x180072a63  mov     rcx, [rsp+130h+string]; this
0x180072a68  mov     r8, rsi; struct Windows::UI::Composition::CompositionObject *
0x180072a6b  call    ?SetFinalValueParameter@AnimationHelper@Composition@UI@Windows@@YAJPEAUHSTRING__@@PEAVCompositionObject@234@PEAVCompositionAnimation@234@PEBUAnimationValueData@234@PEA_N@Z; Windows::UI::Composition::AnimationHelper::SetFinalValueParameter(HSTRING__ *,Windows::UI::Composition::CompositionObject *,Windows::UI::Composition::CompositionAnimation *,Windows::UI::Composition::AnimationValueData const *,bool *)
0x180072a70  mov     ebx, eax
0x180072a72  test    eax, eax
0x180072a74  js      loc_18017F3FE
0x180072a7a  mov     r15b, byte ptr [rbp+47h+arg_0]
0x180072a7e  jmp     loc_180072772
0x180072a83  mov     [rsi+138h], eax
0x180072a89  jmp     loc_18007277D
0x180072a8e  mov     rax, [rbp+47h+arg_20]
0x180072a92  mov     byte ptr [rax], 1
0x180072a95  jmp     loc_1800727D2
0x180072a9a  mov     edx, 11Eh; void *
0x180072a9f  mov     rcx, [rbp+4Fh]; this
0x180072aa3  lea     r8, aOnecoreuapWind_213; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x180072aaa  mov     r9d, ebx; char *
0x180072aad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072ab2  mov     rcx, [rsp+130h+string]; string
0x180072ab7  call    cs:__imp_WindowsDeleteString
0x180072abd  lea     rcx, [rsp+130h+var_E0]; void *
0x180072ac2  mov     [rsp+130h+string], 0
0x180072acb  call    ?InternalUnlock@?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(void)
0x180072ad0  jmp     loc_180072933
0x180072ad5  mov     rdx, [rsp+130h+var_F0]
0x180072ada  call    ??$_Destroy_range@V?$allocator@U?$pair@PEAVCompositionAnimation@Composition@UI@Windows@@V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@@std@@@std@@@std@@YAXPEAU?$pair@PEAVCompositionAnimation@Composition@UI@Windows@@V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@@0@QEAU10@AEAV?$allocator@U?$pair@PEAVCompositionAnimation@Composition@UI@Windows@@V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::pair<Windows::UI::Composition::CompositionAnimation *,std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>>>>(std::pair<Windows::UI::Composition::CompositionAnimation *,std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>> *,std::pair<Windows::UI::Composition::CompositionAnimation *,std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>> * const,std::allocator<std::pair<Windows::UI::Composition::CompositionAnimation *,std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry>>> &)
0x180072adf  mov     rcx, [rsp+130h+string+8]
0x180072ae4  mov     rdx, 8E38E38E38E38E39h
0x180072aee  mov     rax, [rsp+130h+var_E8]
0x180072af3  sub     rax, rcx
0x180072af6  sar     rax, 3
0x180072afa  imul    rax, rdx
0x180072afe  lea     rdx, [rax+rax*8]
0x180072b02  shl     rdx, 3
0x180072b06  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180072b0b  jmp     loc_18007280F
0x18017f3fe  mov     edx, 10Ch
0x18017f403  jmp     loc_180072A9F
```
