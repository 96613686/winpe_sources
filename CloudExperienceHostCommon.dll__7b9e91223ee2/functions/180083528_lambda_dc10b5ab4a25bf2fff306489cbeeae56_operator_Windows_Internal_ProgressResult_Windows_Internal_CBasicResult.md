# _lambda_dc10b5ab4a25bf2fff306489cbeeae56_::operator()(Windows::Internal::ProgressResult<Windows::Internal::CBasicResult<uchar,0>,double> &)

- ea: `0x180083528`
- end: `0x180084119`
- name: `??R_lambda_dc10b5ab4a25bf2fff306489cbeeae56_@@QEBAJAEAV?$ProgressResult@V?$CBasicResult@E$0A@@Internal@Windows@@N@Internal@Windows@@@Z`
- size: `3057`
- prototype: ``
- caller_count: `1`
- callee_count: `31`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800940e0`

## callees

- `0x180003a70`
- `0x180005174`
- `0x18000f974`
- `0x180010810`
- `0x180010c8c`
- `0x180011e9c`
- `0x1800128a4`
- `0x180012d2c`
- `0x1800173c0`
- `0x180017ae8`
- `0x180017ee4`
- `0x180019e80`
- `0x18001a540`
- `0x18001b004`
- `0x180021170`
- `0x180022790`
- `0x1800227ac`
- `0x1800227dc`
- `0x18002327c`
- `0x180076d34`
- `0x18007978c`
- `0x18007f118`
- `0x18007fe3c`
- `0x180081088`
- `0x18008124c`
- `0x1800813b4`
- `0x180082154`
- `0x180082820`
- `0x180083528`
- `0x180095838`
- `0x1800dc010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800839c9`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800839c9`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180083dbf`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180083dbf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180083870`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180083998`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180083870`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180083998`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180083568`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800838c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180083568`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800838c1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180083689`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800836b1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180083689`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800836b1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800837ff`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180083b33`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800837ff`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180083b33`

## string_xrefs

- `0x18008401d`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18008405c`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x180084008`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x180083724`: `<speak version="1.0" xmlns="http://www.w3.org/2001/10/synthesis" xmlns:mstts="http://www.w3.org/2001/mstts" xmlns:emo="http://www.w3.org/2009/10/emotionml" xml:lang="%ls"><voice gender="female"><mstts:prompt domain="VoiceAssistant"/><emo:emotion><emo:category name="Calm" value="1.0"/>%ls</emo:emotion></voice></speak>`
- `0x18008360e`: `<?xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=34 #try_helpers=1
__int64 __fastcall _lambda_dc10b5ab4a25bf2fff306489cbeeae56_::operator()(_QWORD *a1, __int64 a2)
{
  char *StringRawBuffer; // rax
  __int64 v5; // rdi
  const char *v6; // r9
  unsigned int v7; // r8d
  const char *v8; // r9
  const WCHAR *v9; // rbx
  __int64 v10; // rcx
  char v11; // bl
  int v12; // eax
  _OWORD *v13; // rax
  const wchar_t *v14; // rcx
  __int64 v15; // rdx
  int ActivationFactory; // eax
  const WCHAR *v17; // rbx
  __int64 (__fastcall *v18)(const WCHAR *, _QWORD **); // rdi
  _QWORD *v19; // rcx
  int v20; // eax
  _QWORD *v21; // rdi
  __int64 (__fastcall *v22)(_QWORD *, _QWORD, HSTRING *); // rbx
  int v23; // eax
  LPCWCH v24; // rbx
  PCWSTR v25; // rax
  int v26; // eax
  int v27; // eax
  char v28; // r8
  __int64 v29; // rbx
  __int64 (__fastcall *v30)(__int64, PVOID, __int64 *); // rdi
  __int64 v31; // rcx
  HSTRING_HEADER *v32; // rax
  int v33; // eax
  wchar_t *v34; // rax
  char v35; // r8
  int v36; // eax
  _WORD *v37; // r11
  __int64 v38; // rbx
  __int64 (__fastcall *v39)(__int64, PVOID, __int64 *); // rdi
  __int64 v40; // rcx
  HSTRING_HEADER *v41; // rax
  int v42; // eax
  __int64 v43; // rbx
  int v44; // eax
  const WCHAR *v45; // rcx
  int v46; // eax
  int v47; // eax
  __int64 v48; // rdi
  __int64 (__fastcall *v49)(__int64, __int64, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  int v50; // eax
  int v51; // eax
  int v52; // eax
  __int64 *v53; // rax
  HANDLE *v54; // rax
  HANDLE v55; // rbx
  int v56; // eax
  int v57; // eax
  int v58; // eax
  int v59; // eax
  void *v60; // rcx
  DWORD v61; // eax
  const char *v62; // r9
  int v63; // eax
  int v64; // eax
  int v65; // eax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-7A8h]
  BOOL bIgnoreCasea; // [rsp+20h] [rbp-7A8h]
  HSTRING string; // [rsp+30h] [rbp-798h] BYREF
  const WCHAR *v70; // [rsp+38h] [rbp-790h] BYREF
  LPCWCH lpString1; // [rsp+40h] [rbp-788h] BYREF
  __int64 v72; // [rsp+48h] [rbp-780h] BYREF
  _QWORD *v73; // [rsp+50h] [rbp-778h] BYREF
  const WCHAR *Reserved1; // [rsp+58h] [rbp-770h] BYREF
  __int64 (__fastcall ***v75)(_QWORD, GUID *, __int64 *); // [rsp+60h] [rbp-768h] BYREF
  __int64 v76; // [rsp+68h] [rbp-760h] BYREF
  __int64 v77; // [rsp+70h] [rbp-758h] BYREF
  __int64 v78; // [rsp+78h] [rbp-750h] BYREF
  __int64 v79; // [rsp+80h] [rbp-748h] BYREF
  __int64 v80; // [rsp+88h] [rbp-740h] BYREF
  __int64 v81; // [rsp+90h] [rbp-738h] BYREF
  HANDLE Handles[3]; // [rsp+98h] [rbp-730h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+B0h] [rbp-718h] BYREF
  __int64 v84; // [rsp+C8h] [rbp-700h]
  HSTRING_HEADER v85; // [rsp+D0h] [rbp-6F8h] BYREF
  unsigned __int16 v86[520]; // [rsp+F0h] [rbp-6D8h] BYREF
  WCHAR v87[8]; // [rsp+500h] [rbp-2C8h] BYREF
  WCHAR String2[8]; // [rsp+510h] [rbp-2B8h] BYREF
  _BYTE v89[640]; // [rsp+520h] [rbp-2A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+7C8h] [rbp+0h]

  LODWORD(string) = 0;
  *(_BYTE *)(a2 + 24) = 0;
  StringRawBuffer = (char *)WindowsGetStringRawBuffer((HSTRING)a1[1], 0);
  v5 = -1;
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &lpString1,
    StringRawBuffer,
    0xFFFFFFFFFFFFFFFFuLL,
    v6);
  LODWORD(string) = 2;
  v9 = lpString1;
  if ( !lpString1 )
    wil::details::in1diag3::_Throw_NullAlloc(retaddr, (void *)0xFF8, v7, v8);
  if ( *((_BYTE *)a1 + 24) )
  {
    do
      ++v5;
    while ( lpString1[v5] );
    if ( v5 )
    {
      if ( *((_BYTE *)a1 + 25) )
      {
        memset_0(v86, 0, 0x404u);
        if ( !*(_BYTE *)(*a1 + 104LL)
          || !(unsigned __int8)wil::try_wnf_query<CloudExperienceHostAPI::Speech::SpeechControllerStateInfo>(v10, v86)
          || !*(_DWORD *)v86 )
        {
LABEL_67:
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpString1);
          return 0;
        }
        v9 = lpString1;
      }
      wcscpy(String2, L"<?xml");
      wcscpy(v87, L"<speak");
      memset_0(v86, 0, 0x400u);
      if ( CompareStringOrdinal(v9, 5, String2, 5, 1) == 2
        || (v11 = 0, CompareStringOrdinal(lpString1, 6, v87, 6, 1) == 2) )
      {
        v11 = 1;
      }
      v72 = 0;
      v77 = 0;
      v84 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Media.SpeechSynthesis.SpeechSynthesizer",
        0x30u,
        0x2Fu);
      v12 = Windows::Foundation::ActivateInstance<Windows::Media::SpeechSynthesis::ISpeechSynthesizer>(v84, &v77);
      if ( v12 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xCD,
          (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
          (const char *)(unsigned int)v12,
          bIgnoreCase);
      if ( v11 )
      {
        v34 = wcsrchr(lpString1, 0x3Eu);
        if ( v34 && *v34 == 62 )
        {
          v36 = StringCchCopyW(v86, 0x200u, v34 + 1);
          if ( v36 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xE5,
              (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
              (const char *)(unsigned int)v36,
              bIgnoreCase);
          *v37 = 0;
        }
        v38 = v77;
        v39 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v77 + 56LL);
        v40 = v72;
        v72 = 0;
        if ( v40 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
        Reserved1 = lpString1;
        v41 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v85, &Reserved1, v35);
        v42 = v39(v38, v41[1].Reserved.Reserved1, &v72);
        if ( v42 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xE8,
            (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
            (const char *)(unsigned int)v42,
            bIgnoreCase);
      }
      else
      {
        v13 = v89;
        v14 = L"<speak version=\"1.0\" xmlns=\"http://www.w3.org/2001/10/synthesis\" xmlns:mstts=\"http://www.w3.org/2001/"
               "mstts\" xmlns:emo=\"http://www.w3.org/2009/10/emotionml\" xml:lang=\"%ls\"><voice gender=\"female\"><mstt"
               "s:prompt domain=\"VoiceAssistant\"/><emo:emotion><emo:category name=\"Calm\" value=\"1.0\"/>%ls</emo:emot"
               "ion></voice></speak>";
        v15 = 4;
        do
        {
          *v13 = *(_OWORD *)v14;
          v13[1] = *((_OWORD *)v14 + 1);
          v13[2] = *((_OWORD *)v14 + 2);
          v13[3] = *((_OWORD *)v14 + 3);
          v13[4] = *((_OWORD *)v14 + 4);
          v13[5] = *((_OWORD *)v14 + 5);
          v13[6] = *((_OWORD *)v14 + 6);
          v13[7] = *((_OWORD *)v14 + 7);
          v13 += 8;
          v14 += 64;
          --v15;
        }
        while ( v15 );
        *v13 = *(_OWORD *)v14;
        v13[1] = *((_OWORD *)v14 + 1);
        v13[2] = *((_OWORD *)v14 + 2);
        v13[3] = *((_OWORD *)v14 + 3);
        v13[4] = *((_OWORD *)v14 + 4);
        v13[5] = *((_OWORD *)v14 + 5);
        v13[6] = *((_OWORD *)v14 + 6);
        *(_OWORD *)((char *)v13 + 110) = *(_OWORD *)(v14 + 55);
        v73 = 0;
        v70 = 0;
        v84 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.Globalization.ApplicationLanguages",
          0x2Bu,
          0x2Au);
        ActivationFactory = RoGetActivationFactory(v84, &GUID_75b40847_0a4c_4a92_9565_fd63c95f7aed, &v70);
        if ( ActivationFactory < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xD5,
            (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
            (const char *)(unsigned int)ActivationFactory,
            bIgnoreCase);
        v17 = v70;
        v18 = *(__int64 (__fastcall **)(const WCHAR *, _QWORD **))(*(_QWORD *)v70 + 64LL);
        v19 = v73;
        v73 = 0;
        if ( v19 )
          (*(void (__fastcall **)(_QWORD *, _QWORD))(*v19 + 16LL))(v19, *v19);
        v20 = v18(v17, &v73);
        if ( v20 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xD6,
            (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
            (const char *)(unsigned int)v20,
            bIgnoreCase);
        string = 0;
        v21 = v73;
        v22 = *(__int64 (__fastcall **)(_QWORD *, _QWORD, HSTRING *))(*v73 + 48LL);
        WindowsDeleteString(0);
        string = 0;
        v23 = v22(v21, 0, &string);
        if ( v23 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xD8,
            (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
            (const char *)(unsigned int)v23,
            bIgnoreCase);
        memset(&hstringHeader, 0, sizeof(hstringHeader));
        v24 = lpString1;
        v25 = WindowsGetStringRawBuffer(string, 0);
        v26 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
                &hstringHeader,
                v89,
                v25,
                v24);
        if ( v26 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xDA,
            (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
            (const char *)(unsigned int)v26,
            bIgnoreCase);
        v27 = StringCchCopyW(v86, 0x200u, lpString1);
        if ( v27 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xDB,
            (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
            (const char *)(unsigned int)v27,
            bIgnoreCase);
        v29 = v77;
        v30 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v77 + 56LL);
        v31 = v72;
        v72 = 0;
        if ( v31 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
        Reserved1 = (const WCHAR *)hstringHeader.Reserved.Reserved1;
        v32 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v85, &Reserved1, v28);
        v33 = v30(v29, v32[1].Reserved.Reserved1, &v72);
        if ( v33 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xDC,
            (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
            (const char *)(unsigned int)v33,
            bIgnoreCase);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&hstringHeader);
        WindowsDeleteString(string);
        string = 0;
        wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v73);
        wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v70);
      }
      v43 = v72;
      v70 = 0;
      LODWORD(string) = 9;
      v44 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Media::SpeechSynthesis::SpeechSynthesisStream *> *>(v72);
      if ( v44 >= 0 )
        v44 = (*(__int64 (__fastcall **)(__int64, const WCHAR **))(*(_QWORD *)v43 + 64LL))(v43, &v70);
      if ( v44 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x71B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
          (const char *)(unsigned int)v44,
          bIgnoreCase);
      v45 = v70;
      v70 = 0;
      Reserved1 = v45;
      v76 = 0;
      v46 = (**(__int64 (__fastcall ***)(const WCHAR *, GUID *, __int64 *))v45)(
              v45,
              &GUID_905a0fe1_bc53_11df_8c49_001e4fc686da,
              &v76);
      if ( v46 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1CBE,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
          (const char *)(unsigned int)v46,
          bIgnoreCase);
      v80 = 0;
      v84 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Media.Core.MediaSource",
        0x1Fu,
        0x1Eu);
      v47 = RoGetActivationFactory(v84, &GUID_f77d6fa4_4652_410e_b1d8_e9a5e245a45c, &v80);
      if ( v47 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xF0,
          (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
          (const char *)(unsigned int)v47,
          bIgnoreCase);
      v75 = 0;
      v48 = v80;
      v49 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v80 + 88LL);
      v75 = 0;
      v84 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, &dword_1800F98D4, 1u, 0);
      v50 = v49(v48, v76, v84, &v75);
      if ( v50 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xF2,
          (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
          (const char *)(unsigned int)v50,
          bIgnoreCase);
      v79 = 0;
      v51 = (**v75)(v75, &GUID_ef9dc2bc_9317_4696_b051_2bad643177b5, &v79);
      if ( v51 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1CBE,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
          (const char *)(unsigned int)v51,
          bIgnoreCase);
      wil::com_ptr_t<Windows::Media::Playback::IMediaPlayer,wil::err_exception_policy>::query<Windows::Media::Playback::IMediaPlayerSource2>(
        *a1 + 88LL,
        &v81);
      v52 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v81 + 56LL))(v81, v79);
      if ( v52 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xF5,
          (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
          (const char *)(unsigned int)v52,
          bIgnoreCase);
      *(_OWORD *)&hstringHeader.Reserved.Reserved1 = 0;
      _create___event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(&hstringHeader);
      v78 = 0;
      wil::com_ptr_t<CloudExperienceHostAPI::Speech::SpeechRecognitionController,wil::err_exception_policy>::com_ptr_t<CloudExperienceHostAPI::Speech::SpeechRecognitionController,wil::err_exception_policy>(
        &v73,
        *a1);
      v53 = (__int64 *)_lambda_750db03d640fe090669ecc2ddd66e60c_::_lambda_750db03d640fe090669ecc2ddd66e60c_(
                         &v85,
                         &v73,
                         &hstringHeader,
                         &v78);
      v54 = (HANDLE *)Microsoft::WRL::Details::Make<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::Media::Playback::MediaPlayer *,Windows::Media::Playback::IMediaPlayer *>,IInspectable *>::*)(Windows::Media::Playback::IMediaPlayer *,IInspectable *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::Media::Playback::MediaPlayer *,IInspectable *>,_lambda_750db03d640fe090669ecc2ddd66e60c_,-1,Windows::Media::Playback::IMediaPlayer *,IInspectable *>,_lambda_750db03d640fe090669ecc2ddd66e60c_>(
                        &v70,
                        v53);
      v55 = *v54;
      Handles[2] = *v54;
      *v54 = 0;
      if ( v70 )
      {
        v70 = 0;
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IElevationBrokerContext>::Release();
      }
      _lambda_750db03d640fe090669ecc2ddd66e60c_::~_lambda_750db03d640fe090669ecc2ddd66e60c_((_lambda_750db03d640fe090669ecc2ddd66e60c_ *)&v85);
      v56 = (*(__int64 (__fastcall **)(_QWORD, HANDLE, __int64 *))(**(_QWORD **)(*a1 + 88LL) + 216LL))(
              *(_QWORD *)(*a1 + 88LL),
              v55,
              &v78);
      if ( v56 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x106,
          (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
          (const char *)(unsigned int)v56,
          bIgnoreCase);
      (**(void (__fastcall ***)(__int64))a2)(a2);
      v57 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v76 + 88LL))(v76, 0);
      if ( v57 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x10C,
          (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
          (const char *)(unsigned int)v57,
          bIgnoreCase);
      v58 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*a1 + 88LL) + 360LL))(*(_QWORD *)(*a1 + 88LL));
      if ( v58 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x10D,
          (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
          (const char *)(unsigned int)v58,
          bIgnoreCase);
      v59 = CloudExperienceHostAPI::Speech::PublishSpeechControllerState(3, v86);
      if ( v59 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x10E,
          (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
          (const char *)(unsigned int)v59,
          bIgnoreCase);
      LODWORD(string) = 1;
      wil::wnf_publish<int>(retaddr, &string);
      BYTE1(string) = 1;
      Handles[0] = *(HANDLE *)(*a1 + 96LL);
      if ( hstringHeader.Reserved.Reserved1 )
        v60 = *(void **)hstringHeader.Reserved.Reserved1;
      else
        v60 = 0;
      Handles[1] = v60;
      v61 = WaitForMultipleObjectsEx(2u, Handles, 0, 0xEA60u, 0);
      if ( v61 )
      {
        if ( v61 == 1 )
        {
          *(_BYTE *)(a2 + 24) = 1;
LABEL_58:
          v63 = CloudExperienceHostAPI::Speech::PublishSpeechControllerState(4, 0);
          if ( v63 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x112,
              (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
              (const char *)(unsigned int)v63,
              bIgnoreCasea);
          LODWORD(string) = 0;
          wil::wnf_publish<int>(retaddr, &string);
          if ( v55 )
            (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v55 + 16LL))(v55);
          wil::com_ptr_t<CloudExperienceHostAPI::Speech::SpeechRecognitionController,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::Speech::SpeechRecognitionController,wil::err_exception_policy>(&v73);
          __1__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEAA_XZ(&hstringHeader);
          wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v81);
          wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v79);
          wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v75);
          wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v80);
          wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v76);
          wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&Reserved1);
          wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v77);
          wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v72);
          goto LABEL_67;
        }
        if ( v61 != 258 )
        {
          if ( v61 == -1 )
            wil::details::in1diag3::Throw_GetLastError(
              retaddr,
              (void *)0x11C,
              (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
              v62);
          goto LABEL_58;
        }
      }
      v64 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(*a1 + 88LL) + 224LL))(
              *(_QWORD *)(*a1 + 88LL),
              v78);
      if ( v64 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x121,
          (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
          (const char *)(unsigned int)v64,
          bIgnoreCasea);
      v65 = CloudExperienceHostAPI::Speech::SpeechSynthesis::StopVoice((CloudExperienceHostAPI::Speech::SpeechSynthesis *)*a1);
      if ( v65 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x122,
          (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
          (const char *)(unsigned int)v65,
          bIgnoreCasea);
      goto LABEL_58;
    }
  }
  *(_BYTE *)(a2 + 24) = 1;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpString1);
  return 0;
}

```

## disassembly

```asm
0x180083528  mov     [rsp+arg_10], rbx
0x18008352d  mov     [rsp+arg_18], rsi
0x180083532  push    rdi
0x180083533  push    r12
0x180083535  push    r15
0x180083537  sub     rsp, 7B0h
0x18008353e  mov     rax, cs:__security_cookie
0x180083545  xor     rax, rsp
0x180083548  mov     [rsp+7C8h+var_28], rax
0x180083550  mov     r15, rdx
0x180083553  mov     rsi, rcx
0x180083556  xor     r12d, r12d
0x180083559  mov     dword ptr [rsp+7C8h+string], r12d
0x18008355e  mov     [rdx+18h], r12b
0x180083562  xor     edx, edx; length
0x180083564  mov     rcx, [rcx+8]; string
0x180083568  call    cs:__imp_WindowsGetStringRawBuffer
0x18008356e  nop
0x18008356f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180083573  mov     r8, rdi
0x180083576  mov     rdx, rax
0x180083579  lea     rcx, [rsp+7C8h+lpString1]
0x18008357e  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180083583  mov     dword ptr [rsp+7C8h+string], 2
0x18008358b  mov     rcx, [rsp+7C8h]; this
0x180083593  mov     rbx, [rsp+7C8h+lpString1]
0x180083598  test    rbx, rbx
0x18008359b  jz      loc_180083F3E
0x1800835a1  cmp     [rsi+18h], r12b
0x1800835a5  jz      loc_180083F2B
0x1800835ab  inc     rdi
0x1800835ae  cmp     [rbx+rdi*2], r12w
0x1800835b3  jnz     short loc_1800835AB
0x1800835b5  test    rdi, rdi
0x1800835b8  jz      loc_180083F2B
0x1800835be  cmp     [rsi+19h], r12b
0x1800835c2  jz      short loc_18008360E
0x1800835c4  xor     edx, edx; Val
0x1800835c6  mov     r8d, 404h; Size
0x1800835cc  lea     rcx, [rsp+7C8h+var_6D8]; void *
0x1800835d4  call    memset_0
0x1800835d9  mov     rax, [rsi]
0x1800835dc  cmp     [rax+68h], r12b
0x1800835e0  jz      loc_180083EF5
0x1800835e6  lea     rdx, [rsp+7C8h+var_6D8]
0x1800835ee  call    ??$try_wnf_query@USpeechControllerStateInfo@Speech@CloudExperienceHostAPI@@@wil@@YA_NAEBU_WNF_STATE_NAME@@PEAUSpeechControllerStateInfo@Speech@CloudExperienceHostAPI@@PEAUWNF_CHANGE_STAMP_STRUCT@0@@Z; wil::try_wnf_query<CloudExperienceHostAPI::Speech::SpeechControllerStateInfo>(_WNF_STATE_NAME const &,CloudExperienceHostAPI::Speech::SpeechControllerStateInfo *,wil::WNF_CHANGE_STAMP_STRUCT *)
0x1800835f3  test    al, al
0x1800835f5  jz      loc_180083EF5
0x1800835fb  cmp     dword ptr [rsp+7C8h+var_6D8], r12d
0x180083603  jz      loc_180083EF5
0x180083609  mov     rbx, [rsp+7C8h+lpString1]
0x18008360e  movsd   xmm0, qword ptr cs:aXml; "<?xml"
0x180083616  movsd   qword ptr [rsp+7C8h+String2], xmm0
0x18008361f  mov     eax, dword ptr cs:aXml+8; "l"
0x180083625  mov     [rsp+7C8h+var_2B0], eax
0x18008362c  movsd   xmm0, qword ptr cs:aSpeak; "<speak"
0x180083634  movsd   qword ptr [rsp+7C8h+var_2C8], xmm0
0x18008363d  mov     eax, dword ptr cs:aSpeak+8; "ak"
0x180083643  mov     [rsp+7C8h+var_2C0], eax
0x18008364a  movzx   eax, word ptr cs:aSpeak+0Ch; ""
0x180083651  mov     [rsp+7C8h+var_2BC], ax
0x180083659  xor     edx, edx; Val
0x18008365b  mov     r8d, 400h; Size
0x180083661  lea     rcx, [rsp+7C8h+var_6D8]; void *
0x180083669  call    memset_0
0x18008366e  mov     [rsp+7C8h+bIgnoreCase], 1; bIgnoreCase
0x180083676  mov     edx, 5; cchCount1
0x18008367b  mov     r9d, edx; cchCount2
0x18008367e  lea     r8, [rsp+7C8h+String2]; lpString2
0x180083686  mov     rcx, rbx; lpString1
0x180083689  call    cs:__imp_CompareStringOrdinal
0x18008368f  cmp     eax, 2
0x180083692  jz      short loc_1800836BF
0x180083694  mov     [rsp+7C8h+bIgnoreCase], 1; int
0x18008369c  mov     edx, 6; cchCount1
0x1800836a1  mov     r9d, edx; cchCount2
0x1800836a4  lea     r8, [rsp+7C8h+var_2C8]; lpString2
0x1800836ac  mov     rcx, [rsp+7C8h+lpString1]; lpString1
0x1800836b1  call    cs:__imp_CompareStringOrdinal
0x1800836b7  cmp     eax, 2
0x1800836ba  mov     bl, r12b
0x1800836bd  jnz     short loc_1800836C1
0x1800836bf  mov     bl, 1
0x1800836c1  mov     [rsp+7C8h+var_780], r12
0x1800836c6  mov     [rsp+7C8h+var_758], r12
0x1800836cb  mov     [rsp+7C8h+var_700], r12
0x1800836d3  mov     r9d, 2Fh ; '/'; unsigned int
0x1800836d9  lea     r8d, [r9+1]; unsigned int
0x1800836dd  lea     rdx, ?RuntimeClass_Windows_Media_SpeechSynthesis_SpeechSynthesizer@@3QBGB; "Windows.Media.SpeechSynthesis.SpeechSyn"...
0x1800836e4  lea     rcx, [rsp+7C8h+hstringHeader]; hstringHeader
0x1800836ec  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800836f1  nop
0x1800836f2  lea     rdx, [rsp+7C8h+var_758]
0x1800836f7  mov     rcx, [rsp+7C8h+var_700]
0x1800836ff  call    ??$ActivateInstance@UISpeechSynthesizer@SpeechSynthesis@Media@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUISpeechSynthesizer@SpeechSynthesis@Media@1@@Z; Windows::Foundation::ActivateInstance<Windows::Media::SpeechSynthesis::ISpeechSynthesizer>(HSTRING__ *,Windows::Media::SpeechSynthesis::ISpeechSynthesizer * *)
0x180083704  mov     rcx, [rsp+7C8h]; this
0x18008370c  test    eax, eax
0x18008370e  js      loc_180083F49
0x180083714  test    bl, bl
0x180083716  jnz     loc_1800839BD
0x18008371c  lea     rax, [rsp+7C8h+var_2A8]
0x180083724  lea     rcx, aSpeakVersion10; "<speak version=\"1.0\" xmlns=\"http://w"...
0x18008372b  mov     edx, 4
0x180083730  lea     r8d, [rdx+7Ch]
0x180083734  movups  xmm0, xmmword ptr [rcx]
0x180083737  movups  xmmword ptr [rax], xmm0
0x18008373a  movups  xmm1, xmmword ptr [rcx+10h]
0x18008373e  movups  xmmword ptr [rax+10h], xmm1
0x180083742  movups  xmm0, xmmword ptr [rcx+20h]
0x180083746  movups  xmmword ptr [rax+20h], xmm0
0x18008374a  movups  xmm1, xmmword ptr [rcx+30h]
0x18008374e  movups  xmmword ptr [rax+30h], xmm1
0x180083752  movups  xmm0, xmmword ptr [rcx+40h]
0x180083756  movups  xmmword ptr [rax+40h], xmm0
0x18008375a  movups  xmm1, xmmword ptr [rcx+50h]
0x18008375e  movups  xmmword ptr [rax+50h], xmm1
0x180083762  movups  xmm0, xmmword ptr [rcx+60h]
0x180083766  movups  xmmword ptr [rax+60h], xmm0
0x18008376a  movups  xmm1, xmmword ptr [rcx+70h]
0x18008376e  movups  xmmword ptr [rax+70h], xmm1
0x180083772  add     rax, r8
0x180083775  add     rcx, r8
0x180083778  sub     rdx, 1
0x18008377c  jnz     short loc_180083734
0x18008377e  movups  xmm0, xmmword ptr [rcx]
0x180083781  movups  xmmword ptr [rax], xmm0
0x180083784  movups  xmm1, xmmword ptr [rcx+10h]
0x180083788  movups  xmmword ptr [rax+10h], xmm1
0x18008378c  movups  xmm0, xmmword ptr [rcx+20h]
0x180083790  movups  xmmword ptr [rax+20h], xmm0
0x180083794  movups  xmm1, xmmword ptr [rcx+30h]
0x180083798  movups  xmmword ptr [rax+30h], xmm1
0x18008379c  movups  xmm0, xmmword ptr [rcx+40h]
0x1800837a0  movups  xmmword ptr [rax+40h], xmm0
0x1800837a4  movups  xmm1, xmmword ptr [rcx+50h]
0x1800837a8  movups  xmmword ptr [rax+50h], xmm1
0x1800837ac  movups  xmm0, xmmword ptr [rcx+60h]
0x1800837b0  movups  xmmword ptr [rax+60h], xmm0
0x1800837b4  movups  xmm1, xmmword ptr [rcx+6Eh]
0x1800837b8  movups  xmmword ptr [rax+6Eh], xmm1
0x1800837bc  mov     [rsp+7C8h+var_778], r12
0x1800837c1  mov     [rsp+7C8h+var_790], r12
0x1800837c6  mov     [rsp+7C8h+var_700], r12
0x1800837ce  lea     r9d, [rdx+2Ah]; unsigned int
0x1800837d2  lea     r8d, [rdx+2Bh]; unsigned int
0x1800837d6  lea     rdx, ?RuntimeClass_Windows_Globalization_ApplicationLanguages@@3QBGB; "Windows.Globalization.ApplicationLangua"...
0x1800837dd  lea     rcx, [rsp+7C8h+hstringHeader]; hstringHeader
0x1800837e5  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800837ea  nop
0x1800837eb  lea     r8, [rsp+7C8h+var_790]
0x1800837f0  lea     rdx, _GUID_75b40847_0a4c_4a92_9565_fd63c95f7aed
0x1800837f7  mov     rcx, [rsp+7C8h+var_700]
0x1800837ff  call    cs:__imp_RoGetActivationFactory
0x180083805  mov     rcx, [rsp+7C8h]; this
0x18008380d  test    eax, eax
0x18008380f  js      loc_180083F5E
0x180083815  mov     rbx, [rsp+7C8h+var_790]
0x18008381a  mov     rax, [rbx]
0x18008381d  mov     rdi, [rax+40h]
0x180083821  mov     rcx, [rsp+7C8h+var_778]
0x180083826  mov     [rsp+7C8h+var_778], r12
0x18008382b  test    rcx, rcx
0x18008382e  jz      short loc_18008383D
0x180083830  mov     rdx, [rcx]
0x180083833  mov     rax, [rdx+10h]
0x180083837  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008383c  nop
0x18008383d  lea     rdx, [rsp+7C8h+var_778]
0x180083842  mov     rcx, rbx
0x180083845  mov     rax, rdi
0x180083848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008384d  mov     rcx, [rsp+7C8h]; this
0x180083855  test    eax, eax
0x180083857  js      loc_180083F73
0x18008385d  mov     [rsp+7C8h+string], r12
0x180083862  mov     rdi, [rsp+7C8h+var_778]
0x180083867  mov     rax, [rdi]
0x18008386a  mov     rbx, [rax+30h]
0x18008386e  xor     ecx, ecx; string
0x180083870  call    cs:__imp_WindowsDeleteString
0x180083876  mov     [rsp+7C8h+string], r12
0x18008387b  lea     r8, [rsp+7C8h+string]
0x180083880  xor     edx, edx
0x180083882  mov     rcx, rdi
0x180083885  mov     rax, rbx
0x180083888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008388d  mov     rcx, [rsp+7C8h]; this
0x180083895  test    eax, eax
0x180083897  js      loc_180083F88
0x18008389d  mov     qword ptr [rsp+7C8h+hstringHeader.Reserved], r12
0x1800838a5  mov     qword ptr [rsp+7C8h+hstringHeader.Reserved+8], r12
0x1800838ad  mov     qword ptr [rsp+7C8h+hstringHeader.Reserved+10h], r12
0x1800838b5  mov     rbx, [rsp+7C8h+lpString1]
0x1800838ba  xor     edx, edx; length
0x1800838bc  mov     rcx, [rsp+7C8h+string]; string
0x1800838c1  call    cs:__imp_WindowsGetStringRawBuffer
0x1800838c7  mov     r9, rbx
0x1800838ca  mov     r8, rax
0x1800838cd  lea     rdx, [rsp+7C8h+var_2A8]
0x1800838d5  lea     rcx, [rsp+7C8h+hstringHeader]
0x1800838dd  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800838e2  mov     rcx, [rsp+7C8h]; this
0x1800838ea  test    eax, eax
0x1800838ec  js      loc_180083F9D
0x1800838f2  mov     r8, [rsp+7C8h+lpString1]; unsigned __int16 *
0x1800838f7  mov     edx, 200h; unsigned __int64
0x1800838fc  lea     rcx, [rsp+7C8h+var_6D8]; unsigned __int16 *
0x180083904  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180083909  mov     rcx, [rsp+7C8h]; this
0x180083911  test    eax, eax
0x180083913  js      loc_180083FB1
0x180083919  mov     rbx, [rsp+7C8h+var_758]
0x18008391e  mov     rax, [rbx]
0x180083921  mov     rdi, [rax+38h]
0x180083925  mov     rcx, [rsp+7C8h+var_780]
0x18008392a  mov     [rsp+7C8h+var_780], r12
0x18008392f  test    rcx, rcx
0x180083932  jz      short loc_180083941
0x180083934  mov     rax, [rcx]
0x180083937  mov     rax, [rax+10h]
0x18008393b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083940  nop
0x180083941  mov     rdx, qword ptr [rsp+7C8h+hstringHeader.Reserved]
0x180083949  mov     [rsp+7C8h+var_770], rdx
0x18008394e  lea     rdx, [rsp+7C8h+var_770]
0x180083953  lea     rcx, [rsp+7C8h+var_6F8]
0x18008395b  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180083960  nop
0x180083961  lea     r8, [rsp+7C8h+var_780]
0x180083966  mov     rdx, [rax+18h]
0x18008396a  mov     rcx, rbx
0x18008396d  mov     rax, rdi
0x180083970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083975  mov     rcx, [rsp+7C8h]; this
0x18008397d  test    eax, eax
0x18008397f  js      loc_180083FC6
0x180083985  lea     rcx, [rsp+7C8h+hstringHeader]
0x18008398d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180083992  nop
0x180083993  mov     rcx, [rsp+7C8h+string]; string
0x180083998  call    cs:__imp_WindowsDeleteString
0x18008399e  mov     [rsp+7C8h+string], r12
0x1800839a3  lea     rcx, [rsp+7C8h+var_778]
0x1800839a8  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVLaunchUriResult@System@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(void)
0x1800839ad  nop
0x1800839ae  lea     rcx, [rsp+7C8h+var_790]
0x1800839b3  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVLaunchUriResult@System@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(void)
0x1800839b8  jmp     loc_180083A6F
0x1800839bd  mov     ebx, 3Eh ; '>'
0x1800839c2  mov     edx, ebx; Ch
0x1800839c4  mov     rcx, [rsp+7C8h+lpString1]; Str
0x1800839c9  call    cs:__imp_wcsrchr
0x1800839cf  test    rax, rax
0x1800839d2  jz      short loc_180083A06
0x1800839d4  cmp     [rax], bx
0x1800839d7  jnz     short loc_180083A06
0x1800839d9  lea     r11, [rax+2]
0x1800839dd  mov     r8, r11; unsigned __int16 *
0x1800839e0  mov     edx, 200h; unsigned __int64
0x1800839e5  lea     rcx, [rsp+7C8h+var_6D8]; unsigned __int16 *
0x1800839ed  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800839f2  mov     rcx, [rsp+7C8h]; this
0x1800839fa  test    eax, eax
0x1800839fc  js      loc_180083FDB
0x180083a02  mov     [r11], r12w
0x180083a06  mov     rbx, [rsp+7C8h+var_758]
0x180083a0b  mov     rax, [rbx]
0x180083a0e  mov     rdi, [rax+38h]
0x180083a12  mov     rcx, [rsp+7C8h+var_780]
0x180083a17  mov     [rsp+7C8h+var_780], r12
0x180083a1c  test    rcx, rcx
0x180083a1f  jz      short loc_180083A2E
0x180083a21  mov     rax, [rcx]
0x180083a24  mov     rax, [rax+10h]
0x180083a28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083a2d  nop
0x180083a2e  mov     rdx, [rsp+7C8h+lpString1]
0x180083a33  mov     [rsp+7C8h+var_770], rdx
0x180083a38  lea     rdx, [rsp+7C8h+var_770]
0x180083a3d  lea     rcx, [rsp+7C8h+var_6F8]
0x180083a45  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180083a4a  nop
0x180083a4b  lea     r8, [rsp+7C8h+var_780]
0x180083a50  mov     rdx, [rax+18h]
0x180083a54  mov     rcx, rbx
0x180083a57  mov     rax, rdi
0x180083a5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083a5f  mov     rcx, [rsp+7C8h]; this
0x180083a67  test    eax, eax
0x180083a69  js      loc_180083FF0
0x180083a6f  mov     rbx, [rsp+7C8h+var_780]
0x180083a74  mov     [rsp+7C8h+var_790], r12
0x180083a79  mov     dword ptr [rsp+7C8h+string], 9
0x180083a81  mov     rcx, rbx
0x180083a84  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVSpeechSynthesisStream@SpeechSynthesis@Media@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVSpeechSynthesisStream@SpeechSynthesis@Media@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Media::SpeechSynthesis::SpeechSynthesisStream *> *>(Windows::Foundation::IAsyncOperation<Windows::Media::SpeechSynthesis::SpeechSynthesisStream *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x180083a89  test    eax, eax
0x180083a8b  js      short loc_180083AA2
0x180083a8d  mov     rax, [rbx]
0x180083a90  lea     rdx, [rsp+7C8h+var_790]
0x180083a95  mov     rcx, rbx
  ... truncated ...
```
