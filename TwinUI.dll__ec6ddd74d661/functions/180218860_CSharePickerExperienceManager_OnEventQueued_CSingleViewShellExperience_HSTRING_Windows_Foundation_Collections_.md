# CSharePickerExperienceManager::OnEventQueued(CSingleViewShellExperience *,HSTRING__ *,Windows::Foundation::Collections::IPropertySet *)

- ea: `0x180218860`
- end: `0x180218e3c`
- name: `?OnEventQueued@CSharePickerExperienceManager@@MEAAJPEAVCSingleViewShellExperience@@PEAUHSTRING__@@PEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `1500`
- prototype: `int(CSharePickerExperienceManager *__hidden this, struct CSingleViewShellExperience *, HSTRING, struct Windows::Foundation::Collections::IPropertySet *)`
- caller_count: `0`
- callee_count: `22`
- tags: `broker_com_uri`

## callees

- `0x180009dfc`
- `0x18001481c`
- `0x180017808`
- `0x1800378dc`
- `0x180053740`
- `0x18006f0ec`
- `0x180100604`
- `0x180132b2c`
- `0x180142e10`
- `0x1802066a4`
- `0x180214a68`
- `0x180215074`
- `0x1802156d8`
- `0x180215748`
- `0x180215cf4`
- `0x180218860`
- `0x18021b03c`
- `0x18021b370`
- `0x18021d388`
- `0x18021daac`
- `0x18021db2c`
- `0x18021e66c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180218afe`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180218afe`
- `USER32!GetLastActivePopup` at `0x18021890a`
- `USER32!GetLastActivePopup` at `0x18021890a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180218968`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802189c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180218a7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180218b1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180218968`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802189c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180218a7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180218b1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802189f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180218aef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802189f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180218aef`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetForegroundWindow` at `0x180218919`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetForegroundWindow` at `0x180218919`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowTextW` at `0x180218a0b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowTextW` at `0x180218a0b`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CSharePickerExperienceManager::OnEventQueued(
        HWND *this,
        ExperienceManagerUtils **a2,
        Microsoft::WRL::Wrappers::Details *a3,
        struct Windows::Foundation::Collections::IPropertySet *a4)
{
  __int64 v8; // rax
  HSTRING v9; // r8
  int PropVal; // ebx
  __int64 v11; // rdx
  __int64 v13; // rax
  HSTRING v14; // r8
  HWND LastActivePopup; // rax
  __int64 v16; // rax
  HSTRING v17; // r8
  __int64 v18; // rax
  int v19; // eax
  HSTRING v20; // r8
  struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *v21; // rdx
  HWND v22; // rbx
  const WCHAR *v23; // rax
  const char *v24; // r9
  __int64 v25; // rax
  HSTRING v26; // r8
  __int64 v27; // rax
  int v28; // eax
  HSTRING v29; // r8
  PCWSTR StringRawBuffer; // rax
  __int64 v31; // rax
  HSTRING v32; // r8
  __int64 v33; // rax
  HSTRING v34; // r8
  __int64 v35; // rax
  HSTRING v36; // r8
  HSTRING v37; // rbx
  int v38; // eax
  unsigned __int64 v39; // r9
  __int64 v40; // rdx
  int v41; // eax
  HSTRING v42; // rbx
  int v43; // eax
  int v44; // eax
  HSTRING string; // [rsp+20h] [rbp-69h] BYREF
  struct Windows::Foundation::IPropertyValue *v46; // [rsp+28h] [rbp-61h] BYREF
  _QWORD v47[2]; // [rsp+30h] [rbp-59h] BYREF
  _BYTE v48[56]; // [rsp+40h] [rbp-49h] BYREF
  __int64 v49; // [rsp+78h] [rbp-11h] BYREF
  _BYTE v50[32]; // [rsp+80h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v8 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v50, off_1803F9A68);
  if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v8 + 24), v9) )
  {
    v13 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v50, off_1803F9A10);
    if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v13 + 24), v14) )
    {
      LastActivePopup = GetLastActivePopup(this[5]);
      SetForegroundWindow(LastActivePopup);
      goto LABEL_22;
    }
    v16 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v50, off_1803F9A18);
    if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v16 + 24), v17) )
    {
      v25 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v50, off_1803F9A28);
      if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v25 + 24), v26) )
        goto LABEL_22;
      v46 = a4;
      Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v46);
      WindowsDeleteString(0);
      string = 0;
      v27 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v50, off_1803F9A30);
      v28 = Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<HSTRING__ *>(
              (Windows::Internal::ShellHelpers::PropertySetHelper *)&v46,
              *(HSTRING *)(v27 + 24));
      PropVal = v28;
      if ( v28 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3A8,
          (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\sharepickerexperiencemanager.cpp",
          (const char *)(unsigned int)v28,
          (int)string);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
        goto LABEL_11;
      }
      if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                           (Microsoft::WRL::Wrappers::Details *)string,
                           0,
                           v29) )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        this[5] = (HWND)(int)_o__wtoi(StringRawBuffer);
      }
    }
    else
    {
      v46 = a4;
      Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v46);
      WindowsDeleteString(0);
      string = 0;
      v18 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v50, off_1803F9A20);
      v19 = Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<HSTRING__ *>(
              (Windows::Internal::ShellHelpers::PropertySetHelper *)&v46,
              *(HSTRING *)(v18 + 24));
      PropVal = v19;
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x39D,
          (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\sharepickerexperiencemanager.cpp",
          (const char *)(unsigned int)v19,
          (int)string);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
LABEL_11:
        WindowsDeleteString(string);
        return (unsigned int)PropVal;
      }
      if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                           (Microsoft::WRL::Wrappers::Details *)string,
                           0,
                           v20) )
      {
        v22 = ExperienceManagerUtils::WindowFromViewWrapper(a2[3], v21);
        v23 = WindowsGetStringRawBuffer(string, 0);
        if ( !SetWindowTextW(v22, v23) )
          wil::details::in1diag3::_Log_GetLastError(
            retaddr,
            (void *)0x3A1,
            (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\sharepickerexperiencemanager.cpp",
            v24);
      }
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
    WindowsDeleteString(string);
    goto LABEL_22;
  }
  PropVal = CSharePickerExperienceManager::TryDismissShareExperience((CSharePickerExperienceManager *)(this - 7));
  if ( PropVal < 0 )
  {
    v11 = 915;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\sharepickerexperiencemanager.cpp",
      (const char *)(unsigned int)PropVal,
      (int)string);
    return (unsigned int)PropVal;
  }
LABEL_22:
  v31 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v50, &off_1803F9A70);
  if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v31 + 24), v32) )
  {
    PropVal = CSharePickerExperienceManager::TryDismissShareExperience((CSharePickerExperienceManager *)(this - 7));
    if ( PropVal < 0 )
    {
      v11 = 945;
      goto LABEL_4;
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DSSTest>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DSSTest>::GetImpl'::`2'::impl) )
  {
    v33 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v50, off_1803F9A38);
    if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v33 + 24), v34) )
    {
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAI>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CAI>::GetImpl'::`2'::impl) )
        return 0;
      v35 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v50, off_1803F9A48);
      if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v35 + 24), v36) )
        return 0;
      tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>>((struct wil::details::IFailureCallback *)v48);
      if ( (unsigned __int8)tip2::details::shared_data<1,0,0>::is_running(v49 + 8) )
      {
        tip2::test_data_control<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>::test_data_control<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>(
          &v46,
          &v49);
        *((_BYTE *)v46 + 272) = 1;
        tip2::test_data_control<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>::~test_data_control<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>(&v46);
      }
      v47[0] = 0;
      string = (HSTRING)a4;
      Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&string);
      v37 = *(HSTRING *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(v50, off_1803F9A40) + 24);
      v47[0] = 0;
      v46 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
      PropVal = Windows::Internal::ShellHelpers::PropertySetHelper::GetPropVal(
                  (Windows::Internal::ShellHelpers::PropertySetHelper *)&string,
                  v37,
                  &v46);
      if ( PropVal >= 0 )
      {
        v38 =  Windows::Foundation::IPropertyValue::`vcall'{192,{flat}}(v46, v47);
        PropVal = v38;
        if ( v38 >= 0 )
          PropVal = 0;
        else
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2F,
            (unsigned int)"onecore\\internal\\shell\\inc\\PropertySetHelpers.h",
            (const char *)(unsigned int)v38,
            (int)string);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
      if ( PropVal < 0 )
      {
        v39 = (unsigned int)PropVal;
        v40 = 972;
LABEL_50:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v40,
          (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\sharepickerexperiencemanager.cpp",
          (const char *)v39,
          (int)string);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
        tip2::test_watcher<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>::~test_watcher<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>(v48);
        return (unsigned int)PropVal;
      }
      v41 = CSharePickerExperienceManager::ResizeWindowWithScaling(this - 7, v47[0]);
      PropVal = v41;
      if ( v41 < 0 )
      {
        v39 = (unsigned int)v41;
        v40 = 973;
        goto LABEL_50;
      }
    }
    else
    {
      tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>>((struct wil::details::IFailureCallback *)v48);
      if ( (unsigned __int8)tip2::details::shared_data<1,0,0>::is_running(v49 + 8) )
      {
        tip2::test_data_control<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>::test_data_control<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>(
          &v46,
          &v49);
        *((_BYTE *)v46 + 272) = 1;
        tip2::test_data_control<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>::~test_data_control<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>(&v46);
      }
      v47[0] = 0;
      string = (HSTRING)a4;
      Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&string);
      v42 = *(HSTRING *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(v50, off_1803F9A40) + 24);
      v47[0] = 0;
      v46 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
      PropVal = Windows::Internal::ShellHelpers::PropertySetHelper::GetPropVal(
                  (Windows::Internal::ShellHelpers::PropertySetHelper *)&string,
                  v42,
                  &v46);
      if ( PropVal >= 0 )
      {
        v43 =  Windows::Foundation::IPropertyValue::`vcall'{192,{flat}}(v46, v47);
        PropVal = v43;
        if ( v43 >= 0 )
          PropVal = 0;
        else
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2F,
            (unsigned int)"onecore\\internal\\shell\\inc\\PropertySetHelpers.h",
            (const char *)(unsigned int)v43,
            (int)string);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
      if ( PropVal < 0 )
      {
        v39 = (unsigned int)PropVal;
        v40 = 958;
        goto LABEL_50;
      }
      v44 = CSharePickerExperienceManager::ResizeWindow(this - 7, v47[0]);
      PropVal = v44;
      if ( v44 < 0 )
      {
        v39 = (unsigned int)v44;
        v40 = 959;
        goto LABEL_50;
      }
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
    tip2::test_watcher<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>::~test_watcher<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>(v48);
  }
  return 0;
}

```

## disassembly

```asm
0x180218860  push    rbp
0x180218862  push    rbx
0x180218863  push    rsi
0x180218864  push    rdi
0x180218865  push    r13
0x180218867  push    r14
0x180218869  push    r15
0x18021886b  lea     rbp, [rsp-27h]
0x180218870  sub     rsp, 0B0h
0x180218877  mov     rax, cs:__security_cookie
0x18021887e  xor     rax, rsp
0x180218881  mov     [rbp+57h+var_40], rax
0x180218885  mov     r15, r9
0x180218888  mov     rsi, r8
0x18021888b  mov     r14, rdx
0x18021888e  mov     rdi, rcx
0x180218891  lea     rdx, off_1803F9A68; "DestroyPicker"
0x180218898  lea     rcx, [rbp+57h+var_60]
0x18021889c  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1802188a1  mov     rdx, [rax+18h]; HSTRING
0x1802188a5  mov     rcx, rsi; this
0x1802188a8  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x1802188ad  lea     r13, aShellTwinuiExp_4; "shell\\twinui\\experiencemanagers\\lib"...
0x1802188b4  test    eax, eax
0x1802188b6  jnz     short loc_1802188E6
0x1802188b8  lea     rcx, [rdi-38h]; this
0x1802188bc  call    ?TryDismissShareExperience@CSharePickerExperienceManager@@AEAAJXZ; CSharePickerExperienceManager::TryDismissShareExperience(void)
0x1802188c1  mov     ebx, eax
0x1802188c3  test    eax, eax
0x1802188c5  jns     loc_180218B2B
0x1802188cb  mov     edx, 393h; void *
0x1802188d0  mov     r8, r13; unsigned int
0x1802188d3  mov     r9d, ebx; char *
0x1802188d6  mov     rcx, [rbp+5Fh]; this
0x1802188da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802188df  mov     eax, ebx
0x1802188e1  jmp     loc_180218E1D
0x1802188e6  lea     rdx, off_1803F9A10; "SetSourceAppAsForegroundWindow"
0x1802188ed  lea     rcx, [rbp+57h+var_60]
0x1802188f1  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1802188f6  mov     rdx, [rax+18h]; HSTRING
0x1802188fa  mov     rcx, rsi; this
0x1802188fd  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x180218902  test    eax, eax
0x180218904  jnz     short loc_18021892A
0x180218906  mov     rcx, [rdi+28h]; hWnd
0x18021890a  call    cs:__imp_GetLastActivePopup
0x180218911  nop     dword ptr [rax+rax+00h]
0x180218916  mov     rcx, rax; hWnd
0x180218919  call    cs:__imp_SetForegroundWindow
0x180218920  nop     dword ptr [rax+rax+00h]
0x180218925  jmp     loc_180218B2B
0x18021892a  lea     rdx, off_1803F9A18; "SharePickerExperienceWindowTitle"
0x180218931  lea     rcx, [rbp+57h+var_60]
0x180218935  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18021893a  mov     rdx, [rax+18h]; HSTRING
0x18021893e  mov     rcx, rsi; this
0x180218941  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x180218946  test    eax, eax
0x180218948  jnz     loc_180218A3C
0x18021894e  mov     [rbp+57h+string], 0
0x180218956  mov     [rbp+57h+var_B8], r15
0x18021895a  lea     rcx, [rbp+57h+var_B8]
0x18021895e  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180218963  nop
0x180218964  mov     rcx, [rbp+57h+string]; string
0x180218968  call    cs:__imp_WindowsDeleteString
0x18021896f  nop     dword ptr [rax+rax+00h]
0x180218974  mov     [rbp+57h+string], 0
0x18021897c  lea     rdx, off_1803F9A20; "TitleParam"
0x180218983  lea     rcx, [rbp+57h+var_60]
0x180218987  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18021898c  nop
0x18021898d  lea     r9, [rbp+57h+string]
0x180218991  mov     rdx, [rax+18h]; HSTRING
0x180218995  lea     rcx, [rbp+57h+var_B8]; this
0x180218999  call    ??$GetValue@PEAUHSTRING__@@@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValue@Foundation@3@EAAJPEAPEAU4@@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<HSTRING__ *>(HSTRING__ *,long (Windows::Foundation::IPropertyValue::*)(HSTRING__ * *),HSTRING__ * *)
0x18021899e  mov     ebx, eax
0x1802189a0  test    eax, eax
0x1802189a2  jns     short loc_1802189D8
0x1802189a4  mov     rcx, [rbp+5Fh]; this
0x1802189a8  mov     r9d, eax; char *
0x1802189ab  mov     r8, r13; unsigned int
0x1802189ae  mov     edx, 39Dh; void *
0x1802189b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802189b8  nop
0x1802189b9  lea     rcx, [rbp+57h+var_B8]
0x1802189bd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802189c2  nop
0x1802189c3  mov     rcx, [rbp+57h+string]; string
0x1802189c7  call    cs:__imp_WindowsDeleteString
0x1802189ce  nop     dword ptr [rax+rax+00h]
0x1802189d3  jmp     loc_1802188DF
0x1802189d8  xor     edx, edx; HSTRING
0x1802189da  mov     rcx, [rbp+57h+string]; this
0x1802189de  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x1802189e3  test    eax, eax
0x1802189e5  jz      short loc_180218A2D
0x1802189e7  mov     rcx, [r14+18h]; this
0x1802189eb  call    ?WindowFromViewWrapper@ExperienceManagerUtils@@YAPEAUHWND__@@PEAUIViewWrapper@ViewManagerInterop@Shell@Internal@Windows@@@Z; ExperienceManagerUtils::WindowFromViewWrapper(Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *)
0x1802189f0  mov     rbx, rax
0x1802189f3  xor     edx, edx; length
0x1802189f5  mov     rcx, [rbp+57h+string]; string
0x1802189f9  call    cs:__imp_WindowsGetStringRawBuffer
0x180218a00  nop     dword ptr [rax+rax+00h]
0x180218a05  mov     rdx, rax; lpString
0x180218a08  mov     rcx, rbx; hWnd
0x180218a0b  call    cs:__imp_SetWindowTextW
0x180218a12  nop     dword ptr [rax+rax+00h]
0x180218a17  mov     rcx, [rbp+5Fh]; this
0x180218a1b  test    eax, eax
0x180218a1d  jnz     short loc_180218A2D
0x180218a1f  mov     r8, r13; unsigned int
0x180218a22  mov     edx, 3A1h; void *
0x180218a27  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180218a2c  nop
0x180218a2d  lea     rcx, [rbp+57h+var_B8]
0x180218a31  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180218a36  nop
0x180218a37  jmp     loc_180218B1B
0x180218a3c  lea     rdx, off_1803F9A28; "UpdateParentWindow"
0x180218a43  lea     rcx, [rbp+57h+var_60]
0x180218a47  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180218a4c  mov     rdx, [rax+18h]; HSTRING
0x180218a50  mov     rcx, rsi; this
0x180218a53  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x180218a58  test    eax, eax
0x180218a5a  jnz     loc_180218B2B
0x180218a60  mov     [rbp+57h+string], 0
0x180218a68  mov     [rbp+57h+var_B8], r15
0x180218a6c  lea     rcx, [rbp+57h+var_B8]
0x180218a70  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180218a75  nop
0x180218a76  mov     rcx, [rbp+57h+string]; string
0x180218a7a  call    cs:__imp_WindowsDeleteString
0x180218a81  nop     dword ptr [rax+rax+00h]
0x180218a86  mov     [rbp+57h+string], 0
0x180218a8e  lea     rdx, off_1803F9A30; "ParentWindowId"
0x180218a95  lea     rcx, [rbp+57h+var_60]
0x180218a99  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180218a9e  nop
0x180218a9f  lea     r9, [rbp+57h+string]
0x180218aa3  mov     rdx, [rax+18h]; HSTRING
0x180218aa7  lea     rcx, [rbp+57h+var_B8]; this
0x180218aab  call    ??$GetValue@PEAUHSTRING__@@@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValue@Foundation@3@EAAJPEAPEAU4@@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<HSTRING__ *>(HSTRING__ *,long (Windows::Foundation::IPropertyValue::*)(HSTRING__ * *),HSTRING__ * *)
0x180218ab0  mov     ebx, eax
0x180218ab2  test    eax, eax
0x180218ab4  jns     short loc_180218ADA
0x180218ab6  mov     rcx, [rbp+5Fh]; this
0x180218aba  mov     r9d, eax; char *
0x180218abd  mov     r8, r13; unsigned int
0x180218ac0  mov     edx, 3A8h; void *
0x180218ac5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180218aca  nop
0x180218acb  lea     rcx, [rbp+57h+var_B8]
0x180218acf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180218ad4  nop
0x180218ad5  jmp     loc_1802189C3
0x180218ada  xor     edx, edx; HSTRING
0x180218adc  mov     rcx, [rbp+57h+string]; this
0x180218ae0  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x180218ae5  test    eax, eax
0x180218ae7  jz      short loc_180218B11
0x180218ae9  xor     edx, edx; length
0x180218aeb  mov     rcx, [rbp+57h+string]; string
0x180218aef  call    cs:__imp_WindowsGetStringRawBuffer
0x180218af6  nop     dword ptr [rax+rax+00h]
0x180218afb  mov     rcx, rax
0x180218afe  call    cs:__imp__o__wtoi
0x180218b05  nop     dword ptr [rax+rax+00h]
0x180218b0a  movsxd  rcx, eax
0x180218b0d  mov     [rdi+28h], rcx
0x180218b11  lea     rcx, [rbp+57h+var_B8]
0x180218b15  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180218b1a  nop
0x180218b1b  mov     rcx, [rbp+57h+string]; string
0x180218b1f  call    cs:__imp_WindowsDeleteString
0x180218b26  nop     dword ptr [rax+rax+00h]
0x180218b2b  lea     rdx, off_1803F9A70; "DestroyFrame"
0x180218b32  lea     rcx, [rbp+57h+var_60]
0x180218b36  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180218b3b  mov     rdx, [rax+18h]; HSTRING
0x180218b3f  mov     rcx, rsi; this
0x180218b42  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x180218b47  test    eax, eax
0x180218b49  jnz     short loc_180218B64
0x180218b4b  lea     rcx, [rdi-38h]; this
0x180218b4f  call    ?TryDismissShareExperience@CSharePickerExperienceManager@@AEAAJXZ; CSharePickerExperienceManager::TryDismissShareExperience(void)
0x180218b54  mov     ebx, eax
0x180218b56  test    eax, eax
0x180218b58  jns     short loc_180218B64
0x180218b5a  mov     edx, 3B1h
0x180218b5f  jmp     loc_1802188D0
0x180218b64  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DSSTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DSSTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DSSTest> `wil::Feature<__WilFeatureTraits_Feature_DSSTest>::GetImpl(void)'::`2'::impl
0x180218b6b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DSSTest@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DSSTest>::__private_IsEnabled(void)
0x180218b70  test    al, al
0x180218b72  jz      loc_180218E1B
0x180218b78  lea     rdx, off_1803F9A38; "ResizeWindow"
0x180218b7f  lea     rcx, [rbp+57h+var_60]
0x180218b83  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180218b88  mov     rdx, [rax+18h]; HSTRING
0x180218b8c  mov     rcx, rsi; this
0x180218b8f  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x180218b94  test    eax, eax
0x180218b96  jz      loc_180218CF1
0x180218b9c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CAI@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CAI@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAI> `wil::Feature<__WilFeatureTraits_Feature_CAI>::GetImpl(void)'::`2'::impl
0x180218ba3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CAI@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAI>::__private_IsEnabled(void)
0x180218ba8  test    al, al
0x180218baa  jz      loc_180218E1B
0x180218bb0  lea     rdx, off_1803F9A48; "ResizeWindowWithScaling"
0x180218bb7  lea     rcx, [rbp+57h+var_60]
0x180218bbb  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180218bc0  mov     rdx, [rax+18h]; HSTRING
0x180218bc4  mov     rcx, rsi; this
0x180218bc7  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x180218bcc  test    eax, eax
0x180218bce  jnz     loc_180218E1B
0x180218bd4  lea     rcx, [rbp+57h+var_A0]; struct wil::details::IFailureCallback *
0x180218bd8  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_ShareSheetResizeTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x180218bdd  nop
0x180218bde  mov     rcx, [rbp+57h+var_68]
0x180218be2  add     rcx, 8
0x180218be6  call    ?is_running@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::is_running(void)
0x180218beb  test    al, al
0x180218bed  jz      short loc_180218C10
0x180218bef  lea     rdx, [rbp+57h+var_68]
0x180218bf3  lea     rcx, [rbp+57h+var_B8]
0x180218bf7  call    ??0?$test_data_control@V?$merged_data@U_tip_ShareSheetResizeTest@@U1@@details@tip2@@@tip2@@IEAA@AEBV?$com_ptr_t@V?$merged_data@U_tip_ShareSheetResizeTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_data_control<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>::test_data_control<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>(wil::com_ptr_t<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>,wil::err_returncode_policy> const &)
0x180218bfc  mov     rax, [rbp+57h+var_B8]
0x180218c00  mov     byte ptr [rax+110h], 1
0x180218c07  lea     rcx, [rbp+57h+var_B8]
0x180218c0b  call    ??1?$test_data_control@V?$merged_data@U_tip_ShareSheetResizeTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>::~test_data_control<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>(void)
0x180218c10  xor     eax, eax
0x180218c12  mov     [rbp+57h+var_B0], rax
0x180218c16  mov     [rbp+57h+string], r15
0x180218c1a  lea     rcx, [rbp+57h+string]
0x180218c1e  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180218c23  nop
0x180218c24  lea     rdx, off_1803F9A40; "ResizeWindowSize"
0x180218c2b  lea     rcx, [rbp+57h+var_60]
0x180218c2f  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180218c34  nop
0x180218c35  mov     rbx, [rax+18h]
0x180218c39  xor     eax, eax
0x180218c3b  mov     [rbp+57h+var_B0], rax
0x180218c3f  mov     [rbp+57h+var_B8], rax
0x180218c43  lea     rcx, [rbp+57h+var_B8]
0x180218c47  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180218c4c  lea     r8, [rbp+57h+var_B8]; struct Windows::Foundation::IPropertyValue **
0x180218c50  mov     rdx, rbx; HSTRING
0x180218c53  lea     rcx, [rbp+57h+string]; this
0x180218c57  call    ?GetPropVal@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@PEAPEAUIPropertyValue@Foundation@4@@Z; Windows::Internal::ShellHelpers::PropertySetHelper::GetPropVal(HSTRING__ *,Windows::Foundation::IPropertyValue * *)
0x180218c5c  mov     ebx, eax
0x180218c5e  test    eax, eax
0x180218c60  jns     short loc_180218C64
0x180218c62  jmp     short loc_180218C93
0x180218c64  lea     rdx, [rbp+57h+var_B0]
0x180218c68  mov     rcx, [rbp+57h+var_B8]
0x180218c6c  call    ??_9IPropertyValue@Foundation@Windows@@$BMA@AA; [thunk]: Windows::Foundation::IPropertyValue::`vcall'{192,{flat}}
0x180218c71  mov     ebx, eax
0x180218c73  test    eax, eax
0x180218c75  jns     short loc_180218C91
0x180218c77  mov     rcx, [rbp+5Fh]; this
0x180218c7b  mov     r9d, eax; char *
0x180218c7e  lea     r8, aOnecoreInterna_14; "onecore\\internal\\shell\\inc\\Property"...
0x180218c85  mov     edx, 2Fh ; '/'; void *
0x180218c8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180218c8f  jmp     short loc_180218C62
0x180218c91  xor     ebx, ebx
0x180218c93  lea     rcx, [rbp+57h+var_B8]
0x180218c97  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180218c9c  nop
0x180218c9d  test    ebx, ebx
0x180218c9f  jns     short loc_180218CAB
0x180218ca1  mov     r9d, ebx
0x180218ca4  mov     edx, 3CCh
0x180218ca9  jmp     short loc_180218CC6
0x180218cab  lea     rcx, [rdi-38h]
0x180218caf  mov     rdx, [rbp+57h+var_B0]
0x180218cb3  call    ?ResizeWindowWithScaling@CSharePickerExperienceManager@@AEAAJUSize@Foundation@Windows@@@Z; CSharePickerExperienceManager::ResizeWindowWithScaling(Windows::Foundation::Size)
0x180218cb8  mov     ebx, eax
0x180218cba  test    eax, eax
0x180218cbc  jns     short loc_180218CE2
0x180218cbe  mov     r9d, eax; char *
0x180218cc1  mov     edx, 3CDh; void *
0x180218cc6  mov     r8, r13; unsigned int
0x180218cc9  mov     rcx, [rbp+5Fh]; this
0x180218ccd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180218cd2  nop
0x180218cd3  lea     rcx, [rbp+57h+string]
0x180218cd7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180218cdc  nop
0x180218cdd  jmp     loc_180218DFA
0x180218ce2  lea     rcx, [rbp+57h+string]
0x180218ce6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180218ceb  nop
0x180218cec  jmp     loc_180218E12
0x180218cf1  lea     rcx, [rbp+57h+var_A0]; struct wil::details::IFailureCallback *
0x180218cf5  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_ShareSheetResizeTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x180218cfa  nop
  ... truncated ...
```
