# CloudExperienceHostAPI::Speech::SpeechRecognition::PromptForCommandsAsync(HSTRING__ *,Windows::Foundation::Collections::IIterable<Windows::Media::SpeechRecognition::ISpeechRecognitionConstraint *> *,Windows::Foundation::IAsyncOperation<Windows::Media::SpeechRecognition::SpeechRecognitionResult *> * *)

- ea: `0x180011640`
- end: `0x180011cf6`
- name: `?PromptForCommandsAsync@SpeechRecognition@Speech@CloudExperienceHostAPI@@UEAAJPEAUHSTRING__@@PEAU?$IIterable@PEAUISpeechRecognitionConstraint@SpeechRecognition@Media@Windows@@@Collections@Foundation@Windows@@PEAPEAU?$IAsyncOperation@PEAVSpeechRecognitionResult@SpeechRecognition@Media@Windows@@@78@@Z`
- size: `1718`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800924a0`

## callees

- `0x180003a70`
- `0x180005174`
- `0x18000fa5c`
- `0x180010c8c`
- `0x180010cb0`
- `0x180011640`
- `0x180012288`
- `0x180012488`
- `0x1800124a8`
- `0x180017ae8`
- `0x180019e80`
- `0x18001a540`
- `0x18001b004`
- `0x180080be0`
- `0x180080c44`
- `0x18008124c`
- `0x180081420`
- `0x180081e8c`
- `0x18008217c`
- `0x180082ad8`
- `0x1800dc010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011691`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011691`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800117f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001196a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011c60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800117f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001196a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011c60`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180011714`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001177b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180011879`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180011714`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001177b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180011879`

## string_xrefs

- `0x180011ac1`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x180011b61`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
__int64 __fastcall CloudExperienceHostAPI::Speech::SpeechRecognition::PromptForCommandsAsync(
        __int64 a1,
        HSTRING a2,
        __int64 a3,
        _QWORD *a4)
{
  _QWORD *v4; // r14
  __int64 v7; // rcx
  char v8; // al
  int ActivationFactory; // eax
  int v10; // eax
  __int64 v11; // rax
  int v12; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, _QWORD, HSTRING *); // rbx
  int v15; // eax
  int v16; // eax
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // rbx
  __int64 (__fastcall *v20)(__int64, _QWORD, __int64); // rdi
  __int64 v21; // rcx
  int v22; // eax
  int v23; // r13d
  __int64 v24; // rbx
  __int64 v25; // rdi
  __int64 *v26; // rcx
  __int64 v27; // rax
  int v28; // eax
  int v29; // eax
  int v30; // eax
  __int64 v31; // rdi
  __int64 (__fastcall *v32)(__int64, _QWORD **); // rbx
  int v33; // eax
  _QWORD *v34; // rbx
  int v35; // eax
  int v36; // eax
  __int64 v37; // r8
  int v38; // eax
  const char *v39; // r9
  __int64 result; // rax
  int v41; // eax
  int v42; // eax
  int v43; // [rsp+20h] [rbp-508h]
  int v44; // [rsp+20h] [rbp-508h]
  int v45; // [rsp+20h] [rbp-508h]
  char v46[8]; // [rsp+30h] [rbp-4F8h] BYREF
  HSTRING string; // [rsp+38h] [rbp-4F0h] BYREF
  __int64 v48; // [rsp+40h] [rbp-4E8h] BYREF
  __int64 v49; // [rsp+48h] [rbp-4E0h] BYREF
  int v50[2]; // [rsp+50h] [rbp-4D8h] BYREF
  _BYTE v51[12]; // [rsp+58h] [rbp-4D0h] BYREF
  _QWORD *v52; // [rsp+68h] [rbp-4C0h] BYREF
  __int64 *v53; // [rsp+70h] [rbp-4B8h] BYREF
  __int64 v54; // [rsp+78h] [rbp-4B0h] BYREF
  HSTRING newString; // [rsp+80h] [rbp-4A8h] BYREF
  char v56; // [rsp+88h] [rbp-4A0h]
  HSTRING v57; // [rsp+90h] [rbp-498h] BYREF
  __int64 v58; // [rsp+98h] [rbp-490h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-488h] BYREF
  __int64 v60; // [rsp+B8h] [rbp-470h]
  _DWORD v61[260]; // [rsp+D0h] [rbp-458h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+528h] [rbp+0h]

  v4 = a4;
  v54 = a1;
  v57 = a2;
  *(_QWORD *)v51 = a4;
  *a4 = 0;
  CloudExperienceHostAPI::Speech::SpeechRecognition::Stop((CloudExperienceHostAPI::Speech::SpeechRecognition *)a1);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 96));
  v58 = a1 + 96;
  memset_0(v61, 0, 0x404u);
  v8 = wil::try_wnf_query<CloudExperienceHostAPI::Speech::SpeechControllerStateInfo>(v7, v61);
  try
  {
    if ( v8 && v61[0] )
    {
      v49 = 0;
      v60 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Media.SpeechRecognition.SpeechRecognizer",
        0x31u,
        0x30u);
      ActivationFactory = RoGetActivationFactory(v60, &GUID_60c488dd_7fb8_4033_ac70_d046f64818e1, &v49);
      try
      {
        if ( ActivationFactory < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x22F,
            (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
            (const char *)(unsigned int)ActivationFactory,
            v44);
        v53 = 0;
        v60 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.Globalization.ApplicationLanguages",
          0x2Bu,
          0x2Au);
        v10 = RoGetActivationFactory(v60, &GUID_75b40847_0a4c_4a92_9565_fd63c95f7aed, &v53);
        if ( v10 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x231,
            (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
            (const char *)(unsigned int)v10,
            v44);
        v48 = 0;
        v11 = *v53;
        v48 = 0;
        v12 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v11 + 64))(v53, &v48);
        if ( v12 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x233,
            (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
            (const char *)(unsigned int)v12,
            v44);
        string = 0;
        v13 = v48;
        v14 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v48 + 48LL);
        WindowsDeleteString(0);
        string = 0;
        v15 = v14(v13, 0, &string);
        if ( v15 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x235,
            (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
            (const char *)(unsigned int)v15,
            v44);
        newString = 0;
        v60 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.Globalization.Language",
          0x1Fu,
          0x1Eu);
        v16 = RoGetActivationFactory(v60, &GUID_9b0252ac_0c27_44f8_b792_9793fb66c63e, &newString);
        if ( v16 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x237,
            (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
            (const char *)(unsigned int)v16,
            v44);
        *(_QWORD *)v50 = 0;
        v17 = *(_QWORD *)newString;
        *(_QWORD *)v50 = 0;
        v18 = (*(__int64 (__fastcall **)(HSTRING, HSTRING, int *))(v17 + 48))(newString, string, v50);
        if ( v18 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x239,
            (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
            (const char *)(unsigned int)v18,
            v44);
        v19 = v49;
        v20 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v49 + 48LL);
        v21 = *(_QWORD *)(a1 + 136);
        *(_QWORD *)(a1 + 136) = 0;
        if ( v21 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        v22 = v20(v19, *(_QWORD *)v50, a1 + 136);
        if ( v22 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x23A,
            (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
            (const char *)(unsigned int)v22,
            v44);
        wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(v50);
        wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&newString);
        WindowsDeleteString(string);
        string = 0;
        wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v48);
        wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v53);
        wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v49);
      }
      catch ( ... )
      {
        v42 = CloudExperienceHostAPI::Speech::PublishSpeechControllerState(0, 0);
        if ( v42 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x240,
            (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
            (const char *)(unsigned int)v42,
            v43);
        v4 = *(_QWORD **)v51;
        goto LABEL_46;
      }
      v23 = 0;
      v50[0] = 0;
      v48 = 0;
      v24 = v54;
      v25 = v54 - 8;
      v49 = v54 - 8;
      v26 = *(__int64 **)(v54 - 8 + 144);
      v27 = *v26;
      v48 = 0;
      v28 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v27 + 56))(v26, &v48);
      if ( v28 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x248,
          (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
          (const char *)(unsigned int)v28,
          v44);
      if ( a3 )
      {
        wil::iterable_range<Windows::Media::SpeechRecognition::ISpeechRecognitionConstraint *,wil::err_exception_policy>::iterable_iterator::iterable_iterator(
          v51,
          a3);
        hstringHeader.Reserved.Reserved1 = 0;
        *(_DWORD *)&hstringHeader.Reserved.Reserved2[8] = -1;
        *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = 0;
        v29 = *(_DWORD *)&v51[8];
        while ( v29 != -1 )
        {
          v31 = *(_QWORD *)v51;
          v32 = *(__int64 (__fastcall **)(__int64, _QWORD **))(**(_QWORD **)v51 + 48LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
          v33 = v32(v31, &v52);
          if ( v33 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1CBE,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
              (const char *)(unsigned int)v33,
              v44);
          v34 = v52;
          v53 = v52;
          if ( v52 )
            (*(void (__fastcall **)(_QWORD *))(*v52 + 8LL))(v52);
          v35 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v48 + 104LL))(v48, v34);
          if ( v35 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x24E,
              (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
              (const char *)(unsigned int)v35,
              v44);
          v50[0] = ++v23;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
          v46[0] = 0;
          v36 = (*(__int64 (__fastcall **)(_QWORD, char *))(**(_QWORD **)v51 + 64LL))(*(_QWORD *)v51, v46);
          if ( v36 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1CBE,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
              (const char *)(unsigned int)v36,
              v44);
          if ( v46[0] )
            v29 = *(_DWORD *)&v51[8] + 1;
          else
            v29 = -1;
          *(_DWORD *)&v51[8] = v29;
          v25 = v49;
        }
        wil::iterable_range<Windows::Media::SpeechRecognition::ISpeechRecognitionConstraint *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(&hstringHeader);
        wil::iterable_range<Windows::Media::SpeechRecognition::ISpeechRecognitionConstraint *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(v51);
        v24 = v54;
      }
      newString = 0;
      v56 = 0;
      v30 = Microsoft::WRL::Wrappers::HString::Set(&newString, &v57);
      if ( v30 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x255,
          (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
          (const char *)(unsigned int)v30,
          v44);
      wil::com_ptr_t<IUtilElevatedManager,wil::err_returncode_policy>::com_ptr_t<IUtilElevatedManager,wil::err_returncode_policy>(
        &v49,
        a1 + 136);
      LODWORD(string) = *(_DWORD *)(v24 + 72);
      wil::com_ptr_t<CloudExperienceHostAPI::Speech::SpeechRecognitionController,wil::err_exception_policy>::com_ptr_t<CloudExperienceHostAPI::Speech::SpeechRecognitionController,wil::err_exception_policy>(
        &v54,
        v25);
      _lambda_bf551855f04275b1f424c0513cb3648e_::_lambda_bf551855f04275b1f424c0513cb3648e_(
        (unsigned int)&hstringHeader,
        (unsigned int)&v54,
        (unsigned int)&newString,
        (unsigned int)&v49,
        (__int64)v50,
        (__int64)&string);
      *(_DWORD *)v51 = 3;
      *(_QWORD *)&v51[4] = 128;
      v38 = Windows::Internal::MakeAsyncOperation<Windows::Internal::CMarshaledInterfaceResult<Windows::Media::SpeechRecognition::ISpeechRecognitionResult>,Windows::Media::SpeechRecognition::SpeechRecognitionResult *,Windows::Internal::ComTaskPoolHandler,_lambda_bf551855f04275b1f424c0513cb3648e_ &>(
              v51,
              v4,
              v37,
              &hstringHeader);
      if ( v38 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2E6,
          (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
          (const char *)(unsigned int)v38,
          v45);
      _lambda_bf551855f04275b1f424c0513cb3648e_::~_lambda_bf551855f04275b1f424c0513cb3648e_((_lambda_bf551855f04275b1f424c0513cb3648e_ *)&hstringHeader);
      wil::com_ptr_t<CloudExperienceHostAPI::Speech::SpeechRecognitionController,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::Speech::SpeechRecognitionController,wil::err_exception_policy>(&v54);
      wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v49);
      WindowsDeleteString(newString);
      newString = 0;
      wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v48);
    }
    else
    {
LABEL_46:
      *(_DWORD *)v51 = 3;
      *(_QWORD *)&v51[4] = 128;
      v41 = Windows::Internal::MakeAsyncOperation<Windows::Internal::CMarshaledInterfaceResult<Windows::Media::SpeechRecognition::ISpeechRecognitionResult>,Windows::Media::SpeechRecognition::SpeechRecognitionResult *,Windows::Internal::ComTaskPoolHandler,_lambda_0f4c4091f09829f6e62a5cab34ef2fb0_>(
              v51,
              v4);
      if ( v41 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2EA,
          (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
          (const char *)(unsigned int)v41,
          v44);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v58);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x2EE,
                           (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
                           v39);
  }
  return result;
}

```

## disassembly

```asm
0x180011640  push    rbx
0x180011642  push    rsi
0x180011643  push    rdi
0x180011644  push    r12
0x180011646  push    r13
0x180011648  push    r14
0x18001164a  push    r15
0x18001164c  sub     rsp, 4F0h
0x180011653  mov     rax, cs:__security_cookie
0x18001165a  xor     rax, rsp
0x18001165d  mov     [rsp+528h+var_48], rax
0x180011665  mov     r14, r9
0x180011668  mov     r12, r8
0x18001166b  mov     r15, rcx
0x18001166e  mov     [rsp+528h+var_4B0], rcx
0x180011673  mov     [rsp+528h+var_498], rdx
0x18001167b  mov     [rsp+528h+var_4D0], r9
0x180011680  xor     esi, esi
0x180011682  mov     [r9], rsi
0x180011685  call    ?Stop@SpeechRecognition@Speech@CloudExperienceHostAPI@@UEAAJXZ; CloudExperienceHostAPI::Speech::SpeechRecognition::Stop(void)
0x18001168a  lea     rbx, [r15+60h]
0x18001168e  mov     rcx, rbx; lpCriticalSection
0x180011691  call    cs:__imp_EnterCriticalSection
0x180011697  mov     [rsp+528h+var_490], rbx
0x18001169f  xor     edx, edx; Val
0x1800116a1  mov     r8d, 404h; Size
0x1800116a7  lea     rcx, [rsp+528h+var_458]; void *
0x1800116af  call    memset_0
0x1800116b4  lea     rdx, [rsp+528h+var_458]
0x1800116bc  call    ??$try_wnf_query@USpeechControllerStateInfo@Speech@CloudExperienceHostAPI@@@wil@@YA_NAEBU_WNF_STATE_NAME@@PEAUSpeechControllerStateInfo@Speech@CloudExperienceHostAPI@@PEAUWNF_CHANGE_STAMP_STRUCT@0@@Z; wil::try_wnf_query<CloudExperienceHostAPI::Speech::SpeechControllerStateInfo>(_WNF_STATE_NAME const &,CloudExperienceHostAPI::Speech::SpeechControllerStateInfo *,wil::WNF_CHANGE_STAMP_STRUCT *)
0x1800116c1  test    al, al
0x1800116c3  jz      loc_180011CB6
0x1800116c9  cmp     [rsp+528h+var_458], esi
0x1800116d0  jz      loc_180011CB6
0x1800116d6  mov     [rsp+528h+var_4E0], rsi
0x1800116db  mov     [rsp+528h+var_470], rsi
0x1800116e3  lea     r9d, [rsi+30h]; unsigned int
0x1800116e7  lea     r8d, [rsi+31h]; unsigned int
0x1800116eb  lea     rdx, ?RuntimeClass_Windows_Media_SpeechRecognition_SpeechRecognizer@@3QBGB; "Windows.Media.SpeechRecognition.SpeechR"...
0x1800116f2  lea     rcx, [rsp+528h+hstringHeader]; hstringHeader
0x1800116fa  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800116ff  nop
0x180011700  lea     r8, [rsp+528h+var_4E0]
0x180011705  lea     rdx, _GUID_60c488dd_7fb8_4033_ac70_d046f64818e1
0x18001170c  mov     rcx, [rsp+528h+var_470]
0x180011714  call    cs:__imp_RoGetActivationFactory
0x18001171a  mov     rcx, [rsp+528h]; this
0x180011722  test    eax, eax
0x180011724  jns     short loc_18001173B
0x180011726  mov     r9d, eax; char *
0x180011729  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\cloudexperiencehost"...
0x180011730  mov     edx, 22Fh; void *
0x180011735  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001173b  mov     [rsp+528h+var_4B8], rsi
0x180011740  mov     [rsp+528h+var_470], rsi
0x180011748  mov     r9d, 2Ah ; '*'; unsigned int
0x18001174e  lea     r8d, [r9+1]; unsigned int
0x180011752  lea     rdx, ?RuntimeClass_Windows_Globalization_ApplicationLanguages@@3QBGB; "Windows.Globalization.ApplicationLangua"...
0x180011759  lea     rcx, [rsp+528h+hstringHeader]; hstringHeader
0x180011761  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180011766  nop
0x180011767  lea     r8, [rsp+528h+var_4B8]
0x18001176c  lea     rdx, _GUID_75b40847_0a4c_4a92_9565_fd63c95f7aed
0x180011773  mov     rcx, [rsp+528h+var_470]
0x18001177b  call    cs:__imp_RoGetActivationFactory
0x180011781  mov     rcx, [rsp+528h]; this
0x180011789  test    eax, eax
0x18001178b  jns     short loc_1800117A2
0x18001178d  mov     r9d, eax; char *
0x180011790  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\cloudexperiencehost"...
0x180011797  mov     edx, 231h; void *
0x18001179c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800117a2  mov     [rsp+528h+var_4E8], rsi
0x1800117a7  mov     rcx, [rsp+528h+var_4B8]
0x1800117ac  mov     rax, [rcx]
0x1800117af  mov     [rsp+528h+var_4E8], rsi
0x1800117b4  lea     rdx, [rsp+528h+var_4E8]
0x1800117b9  mov     rax, [rax+40h]
0x1800117bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800117c2  mov     rcx, [rsp+528h]; this
0x1800117ca  test    eax, eax
0x1800117cc  jns     short loc_1800117E2
0x1800117ce  mov     r9d, eax; char *
0x1800117d1  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\cloudexperiencehost"...
0x1800117d8  mov     edx, 233h; void *
0x1800117dd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800117e2  mov     [rsp+528h+string], rsi
0x1800117e7  mov     rdi, [rsp+528h+var_4E8]
0x1800117ec  mov     rax, [rdi]
0x1800117ef  mov     rbx, [rax+30h]
0x1800117f3  xor     ecx, ecx; string
0x1800117f5  call    cs:__imp_WindowsDeleteString
0x1800117fb  mov     [rsp+528h+string], rsi
0x180011800  lea     r8, [rsp+528h+string]
0x180011805  xor     edx, edx
0x180011807  mov     rcx, rdi
0x18001180a  mov     rax, rbx
0x18001180d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011812  mov     rcx, [rsp+528h]; this
0x18001181a  test    eax, eax
0x18001181c  jns     short loc_180011833
0x18001181e  mov     r9d, eax; char *
0x180011821  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\cloudexperiencehost"...
0x180011828  mov     edx, 235h; void *
0x18001182d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180011833  mov     [rsp+528h+newString], rsi
0x18001183b  mov     [rsp+528h+var_470], rsi
0x180011843  mov     r9d, 1Eh; unsigned int
0x180011849  lea     r8d, [r9+1]; unsigned int
0x18001184d  lea     rdx, ?RuntimeClass_Windows_Globalization_Language@@3QBGB; "Windows.Globalization.Language"
0x180011854  lea     rcx, [rsp+528h+hstringHeader]; hstringHeader
0x18001185c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180011861  nop
0x180011862  lea     r8, [rsp+528h+newString]
0x18001186a  lea     rdx, _GUID_9b0252ac_0c27_44f8_b792_9793fb66c63e
0x180011871  mov     rcx, [rsp+528h+var_470]
0x180011879  call    cs:__imp_RoGetActivationFactory
0x18001187f  mov     rcx, [rsp+528h]; this
0x180011887  test    eax, eax
0x180011889  jns     short loc_1800118A0
0x18001188b  mov     r9d, eax; char *
0x18001188e  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\cloudexperiencehost"...
0x180011895  mov     edx, 237h; void *
0x18001189a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800118a0  mov     qword ptr [rsp+528h+var_4D8], rsi
0x1800118a5  mov     rcx, [rsp+528h+newString]
0x1800118ad  mov     rax, [rcx]
0x1800118b0  mov     qword ptr [rsp+528h+var_4D8], rsi
0x1800118b5  lea     r8, [rsp+528h+var_4D8]
0x1800118ba  mov     rdx, [rsp+528h+string]
0x1800118bf  mov     rax, [rax+30h]
0x1800118c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118c8  mov     rcx, [rsp+528h]; this
0x1800118d0  test    eax, eax
0x1800118d2  jns     short loc_1800118E8
0x1800118d4  mov     r9d, eax; char *
0x1800118d7  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\cloudexperiencehost"...
0x1800118de  mov     edx, 239h; void *
0x1800118e3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800118e8  mov     rbx, [rsp+528h+var_4E0]
0x1800118ed  mov     rax, [rbx]
0x1800118f0  mov     rdi, [rax+30h]
0x1800118f4  mov     rcx, [r15+88h]
0x1800118fb  mov     [r15+88h], rsi
0x180011902  test    rcx, rcx
0x180011905  jz      short loc_180011914
0x180011907  mov     rdx, [rcx]
0x18001190a  mov     rax, [rdx+10h]
0x18001190e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011913  nop
0x180011914  lea     r8, [r15+88h]
0x18001191b  mov     rdx, qword ptr [rsp+528h+var_4D8]
0x180011920  mov     rcx, rbx
0x180011923  mov     rax, rdi
0x180011926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001192b  mov     rcx, [rsp+528h]; this
0x180011933  test    eax, eax
0x180011935  jns     short loc_18001194C
0x180011937  mov     r9d, eax; char *
0x18001193a  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\cloudexperiencehost"...
0x180011941  mov     edx, 23Ah; void *
0x180011946  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001194c  lea     rcx, [rsp+528h+var_4D8]
0x180011951  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVLaunchUriResult@System@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(void)
0x180011956  nop
0x180011957  lea     rcx, [rsp+528h+newString]
0x18001195f  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVLaunchUriResult@System@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(void)
0x180011964  nop
0x180011965  mov     rcx, [rsp+528h+string]; string
0x18001196a  call    cs:__imp_WindowsDeleteString
0x180011970  mov     [rsp+528h+string], rsi
0x180011975  lea     rcx, [rsp+528h+var_4E8]
0x18001197a  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVLaunchUriResult@System@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(void)
0x18001197f  nop
0x180011980  lea     rcx, [rsp+528h+var_4B8]
0x180011985  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVLaunchUriResult@System@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(void)
0x18001198a  nop
0x18001198b  lea     rcx, [rsp+528h+var_4E0]
0x180011990  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVLaunchUriResult@System@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(void)
0x180011995  nop
0x180011996  mov     r13d, esi
0x180011999  mov     [rsp+528h+var_4D8], esi
0x18001199d  mov     [rsp+528h+var_4E8], rsi
0x1800119a2  mov     rbx, [rsp+528h+var_4B0]
0x1800119a7  lea     rdi, [rbx-8]
0x1800119ab  mov     [rsp+528h+var_4E0], rdi
0x1800119b0  mov     rcx, [rdi+90h]
0x1800119b7  mov     rax, [rcx]
0x1800119ba  mov     [rsp+528h+var_4E8], rsi
0x1800119bf  lea     rdx, [rsp+528h+var_4E8]
0x1800119c4  mov     rax, [rax+38h]
0x1800119c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119cd  mov     rcx, [rsp+528h]; this
0x1800119d5  test    eax, eax
0x1800119d7  jns     short loc_1800119ED
0x1800119d9  mov     r9d, eax; char *
0x1800119dc  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\cloudexperiencehost"...
0x1800119e3  mov     edx, 248h; void *
0x1800119e8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800119ed  test    r12, r12
0x1800119f0  jz      short loc_180011A42
0x1800119f2  mov     rdx, r12
0x1800119f5  lea     rcx, [rsp+528h+var_4D0]
0x1800119fa  call    ??0iterable_iterator@?$iterable_range@PEAUISpeechRecognitionConstraint@SpeechRecognition@Media@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAU?$IIterable@PEAUISpeechRecognitionConstraint@SpeechRecognition@Media@Windows@@@Collections@Foundation@Windows@@@Z; wil::iterable_range<Windows::Media::SpeechRecognition::ISpeechRecognitionConstraint *,wil::err_exception_policy>::iterable_iterator::iterable_iterator(Windows::Foundation::Collections::IIterable<Windows::Media::SpeechRecognition::ISpeechRecognitionConstraint *> *)
0x1800119ff  nop
0x180011a00  mov     qword ptr [rsp+528h+hstringHeader.Reserved], rsi
0x180011a08  or      r12d, 0FFFFFFFFh
0x180011a0c  mov     dword ptr [rsp+528h+hstringHeader.Reserved+8], r12d
0x180011a14  mov     qword ptr [rsp+528h+hstringHeader.Reserved+10h], rsi
0x180011a1c  mov     eax, [rsp+528h+var_4C8]
0x180011a20  cmp     eax, r12d
0x180011a23  jnz     short loc_180011A8C
0x180011a25  lea     rcx, [rsp+528h+hstringHeader]
0x180011a2d  call    ??1iterable_iterator@?$iterable_range@PEAUISpeechRecognitionConstraint@SpeechRecognition@Media@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::iterable_range<Windows::Media::SpeechRecognition::ISpeechRecognitionConstraint *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(void)
0x180011a32  nop
0x180011a33  lea     rcx, [rsp+528h+var_4D0]
0x180011a38  call    ??1iterable_iterator@?$iterable_range@PEAUISpeechRecognitionConstraint@SpeechRecognition@Media@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::iterable_range<Windows::Media::SpeechRecognition::ISpeechRecognitionConstraint *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(void)
0x180011a3d  mov     rbx, [rsp+528h+var_4B0]
0x180011a42  mov     [rsp+528h+newString], rsi
0x180011a4a  mov     [rsp+528h+var_4A0], sil
0x180011a52  lea     rdx, [rsp+528h+var_498]; HSTRING *
0x180011a5a  lea     rcx, [rsp+528h+newString]; newString
0x180011a62  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180011a67  mov     rcx, [rsp+528h]; this
0x180011a6f  test    eax, eax
0x180011a71  jns     loc_180011B92
0x180011a77  mov     r9d, eax; char *
0x180011a7a  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\cloudexperiencehost"...
0x180011a81  mov     edx, 255h; void *
0x180011a86  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180011a8c  mov     rdi, [rsp+528h+var_4D0]
0x180011a91  mov     rax, [rdi]
0x180011a94  mov     rbx, [rax+30h]
0x180011a98  lea     rcx, [rsp+528h+var_4C0]
0x180011a9d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180011aa2  lea     rdx, [rsp+528h+var_4C0]
0x180011aa7  mov     rcx, rdi
0x180011aaa  mov     rax, rbx
0x180011aad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ab2  mov     rcx, [rsp+528h]; this
0x180011aba  test    eax, eax
0x180011abc  jns     short loc_180011AD2
0x180011abe  mov     r9d, eax; char *
0x180011ac1  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180011ac8  mov     edx, 1CBEh; void *
0x180011acd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180011ad2  mov     rbx, [rsp+528h+var_4C0]
0x180011ad7  mov     [rsp+528h+var_4B8], rbx
0x180011adc  test    rbx, rbx
0x180011adf  jz      short loc_180011AF1
0x180011ae1  mov     rax, [rbx]
0x180011ae4  mov     rcx, rbx
0x180011ae7  mov     rax, [rax+8]
0x180011aeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011af0  nop
0x180011af1  mov     rcx, [rsp+528h+var_4E8]
0x180011af6  mov     rax, [rcx]
0x180011af9  mov     rdx, rbx
0x180011afc  mov     rax, [rax+68h]
0x180011b00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b05  mov     rcx, [rsp+528h]; this
0x180011b0d  test    eax, eax
0x180011b0f  jns     short loc_180011B25
0x180011b11  mov     r9d, eax; char *
0x180011b14  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\cloudexperiencehost"...
0x180011b1b  mov     edx, 24Eh; void *
0x180011b20  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180011b25  inc     r13d
0x180011b28  mov     [rsp+528h+var_4D8], r13d
0x180011b2d  lea     rcx, [rsp+528h+var_4B8]
0x180011b32  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180011b37  mov     [rsp+528h+var_4F8], sil
0x180011b3c  mov     rcx, [rsp+528h+var_4D0]
0x180011b41  mov     rax, [rcx]
0x180011b44  lea     rdx, [rsp+528h+var_4F8]
0x180011b49  mov     rax, [rax+40h]
0x180011b4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b52  mov     rcx, [rsp+528h]; this
0x180011b5a  test    eax, eax
0x180011b5c  jns     short loc_180011B72
0x180011b5e  mov     r9d, eax; char *
0x180011b61  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180011b68  mov     edx, 1CBEh; void *
0x180011b6d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180011b72  cmp     [rsp+528h+var_4F8], sil
0x180011b77  jz      short loc_180011B81
0x180011b79  mov     eax, [rsp+528h+var_4C8]
0x180011b7d  inc     eax
0x180011b7f  jmp     short loc_180011B84
0x180011b81  mov     eax, r12d
0x180011b84  mov     [rsp+528h+var_4C8], eax
0x180011b88  mov     rdi, [rsp+528h+var_4E0]
0x180011b8d  jmp     loc_180011A20
0x180011b92  lea     rdx, [r15+88h]
0x180011b99  lea     rcx, [rsp+528h+var_4E0]
0x180011b9e  call    ??0?$com_ptr_t@UIUtilElevatedManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@AEBV01@@Z; wil::com_ptr_t<IUtilElevatedManager,wil::err_returncode_policy>::com_ptr_t<IUtilElevatedManager,wil::err_returncode_policy>(wil::com_ptr_t<IUtilElevatedManager,wil::err_returncode_policy> const &)
0x180011ba3  nop
0x180011ba4  mov     eax, [rbx+48h]
0x180011ba7  mov     dword ptr [rsp+528h+string], eax
0x180011bab  mov     rdx, rdi
  ... truncated ...
```
