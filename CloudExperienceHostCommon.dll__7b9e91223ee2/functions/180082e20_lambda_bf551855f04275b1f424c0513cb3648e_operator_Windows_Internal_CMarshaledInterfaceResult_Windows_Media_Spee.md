# _lambda_bf551855f04275b1f424c0513cb3648e_::operator()(Windows::Internal::CMarshaledInterfaceResult<Windows::Media::SpeechRecognition::ISpeechRecognitionResult> &)

- ea: `0x180082e20`
- end: `0x180083521`
- name: `??R_lambda_bf551855f04275b1f424c0513cb3648e_@@QEAAJAEAV?$CMarshaledInterfaceResult@UISpeechRecognitionResult@SpeechRecognition@Media@Windows@@@Internal@Windows@@@Z`
- size: `1793`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800940a0`

## callees

- `0x180005174`
- `0x18000f9e4`
- `0x180010318`
- `0x180010460`
- `0x180010c8c`
- `0x180011e9c`
- `0x180012488`
- `0x180017c54`
- `0x180017cf8`
- `0x180017f4c`
- `0x18001a540`
- `0x18001b004`
- `0x18001dc28`
- `0x1800227ac`
- `0x18007f0e8`
- `0x180080f48`
- `0x1800829d4`
- `0x180082e20`
- `0x1800927b4`
- `0x1800942e4`
- `0x1800945a8`
- `0x180094788`
- `0x1800dc010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180083262`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180083262`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800832c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800833f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800832c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800833f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180083023`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800832f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180083023`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800832f6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180083160`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18008336d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180083160`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18008336d`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18008311a`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18008311a`

## string_xrefs

- `0x180083492`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x1800834bb`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x1800834f9`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall _lambda_bf551855f04275b1f424c0513cb3648e_::operator()(__int64 *a1, __int64 a2)
{
  unsigned int v3; // r13d
  void *v4; // rdx
  __int64 *v5; // rcx
  __int64 v6; // rax
  int v7; // eax
  int v8; // eax
  void *v9; // rdx
  char v10; // r8
  __int64 v11; // rax
  int v12; // eax
  int v13; // eax
  HRESULT v14; // eax
  unsigned int v15; // esi
  int v16; // eax
  __int64 *v17; // rcx
  __int64 v18; // rax
  int v19; // eax
  __int64 v20; // rbx
  int v21; // r13d
  int v22; // eax
  __int64 v23; // r15
  __int64 v24; // rdi
  struct _RTL_CRITICAL_SECTION *v25; // rbx
  __int64 v26; // rbx
  __int64 (__fastcall *v27)(__int64, HSTRING *); // rbx
  int v28; // eax
  int v29; // eax
  int lpdwindex; // [rsp+20h] [rbp-248h]
  int lpdwindexa; // [rsp+20h] [rbp-248h]
  char v33; // [rsp+30h] [rbp-238h] BYREF
  char v34; // [rsp+31h] [rbp-237h] BYREF
  char v35; // [rsp+32h] [rbp-236h] BYREF
  __int64 v36; // [rsp+38h] [rbp-230h] BYREF
  int v37; // [rsp+40h] [rbp-228h]
  struct _RTL_CRITICAL_SECTION *v38; // [rsp+48h] [rbp-220h] BYREF
  UINT32 v39; // [rsp+50h] [rbp-218h] BYREF
  __int64 v40; // [rsp+58h] [rbp-210h] BYREF
  UINT32 length; // [rsp+60h] [rbp-208h] BYREF
  HSTRING string[2]; // [rsp+68h] [rbp-200h] BYREF
  wil::details *v43; // [rsp+78h] [rbp-1F0h] BYREF
  wil::details *v44; // [rsp+80h] [rbp-1E8h] BYREF
  _QWORD v45[2]; // [rsp+88h] [rbp-1E0h] BYREF
  DWORD dwindex; // [rsp+98h] [rbp-1D0h] BYREF
  DWORD TickCount; // [rsp+9Ch] [rbp-1CCh]
  __int64 v48; // [rsp+A0h] [rbp-1C8h]
  HANDLE pHandles[2]; // [rsp+A8h] [rbp-1C0h] BYREF
  _QWORD v50[3]; // [rsp+B8h] [rbp-1B0h] BYREF
  char v51; // [rsp+D0h] [rbp-198h]
  void **v52; // [rsp+E0h] [rbp-188h] BYREF
  int v53; // [rsp+E8h] [rbp-180h] BYREF
  char v54; // [rsp+ECh] [rbp-17Ch]
  int v55; // [rsp+110h] [rbp-158h] BYREF
  const char *v56; // [rsp+118h] [rbp-150h]
  __int64 v57; // [rsp+120h] [rbp-148h]
  char v58; // [rsp+128h] [rbp-140h]
  int v59; // [rsp+130h] [rbp-138h]
  _BYTE v60[168]; // [rsp+138h] [rbp-130h] BYREF
  int v61; // [rsp+1E0h] [rbp-88h]
  __int64 v62; // [rsp+1E8h] [rbp-80h]
  int *v63; // [rsp+1F0h] [rbp-78h]
  __int64 v64; // [rsp+1F8h] [rbp-70h]
  __int64 v65; // [rsp+200h] [rbp-68h]
  void ***v66; // [rsp+208h] [rbp-60h]
  __int64 v67; // [rsp+210h] [rbp-58h]
  int v68; // [rsp+218h] [rbp-50h]
  int *v69; // [rsp+220h] [rbp-48h]
  char v70; // [rsp+228h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  v48 = a2;
  v3 = 0;
  LODWORD(v38) = 0;
  v53 = 0;
  v54 = 0;
  v58 = 0;
  v55 = 0;
  v56 = "SpeechRecoActivity";
  v57 = 0;
  v59 = 0;
  *(_OWORD *)&v60[152] = 0;
  memset_0(v60, 0, 0x98u);
  try
  {
    v61 = 1;
    v62 = 0;
    v63 = &v53;
    v64 = 0;
    v65 = 0;
    v66 = &v52;
    v67 = 0;
    v68 = 0;
    v69 = &v55;
    v70 = 0;
    v52 = &CloudExperienceHostSpeechTelemetry::SpeechRecoActivity::`vftable';
    v37 = 2;
    v34 = 0;
    LODWORD(v38) = 1;
    ____0W4EventOptions_wil____V___unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
      &v44,
      &v38);
    if ( *((_DWORD *)a1 + 8) )
    {
      CloudExperienceHostSpeechTelemetry::SpeechRecoActivity::StartActivity((CloudExperienceHostSpeechTelemetry::SpeechRecoActivity *)&v52);
      v36 = 0;
      v5 = (__int64 *)a1[3];
      v6 = *v5;
      v36 = 0;
      v7 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v6 + 80))(v5, &v36);
      if ( v7 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x26A,
          (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
          (const char *)(unsigned int)v7,
          lpdwindex);
      v45[0] = &v44;
      v45[1] = &v34;
      v8 = wil::details::RunWhenComplete<Microsoft::WRL::FtmBase,Windows::Foundation::IAsyncOperation<Windows::Media::SpeechRecognition::SpeechRecognitionCompilationResult *> *,_lambda_7e7f6ecefc30c60d55f0b7b31107a615_>(
             v36,
             v45);
      if ( v8 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x6BB,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
          (const char *)(unsigned int)v8,
          lpdwindex);
      wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v36);
    }
    else
    {
      wil::details::SetEvent(v44, v4);
    }
    v33 = 0;
    LODWORD(v38) = 1;
    ____0W4EventOptions_wil____V___unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
      &v43,
      &v38);
    length = 0;
    WindowsGetStringRawBuffer((HSTRING)a1[1], &length);
    if ( length )
    {
      wil::GetActivationFactory<CloudExperienceHostAPI::Speech::ISpeechSynthesisStatics>(
        (const WCHAR *)v45,
        (__int64)v9,
        v10);
      v36 = 0;
      v11 = *(_QWORD *)v45[0];
      v36 = 0;
      v12 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *))(v11 + 48))(v45[0], a1[1], &v36);
      if ( v12 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x283,
          (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
          (const char *)(unsigned int)v12,
          lpdwindex);
      string[0] = (HSTRING)&v43;
      string[1] = (HSTRING)&v33;
      v13 = wil::details::RunWhenComplete<Microsoft::WRL::FtmBase,Windows::Foundation::IAsyncOperationWithProgress<bool,double> *,_lambda_826daee88777eed0908553c3a88e2bef_>(
              v36,
              string);
      if ( v13 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x6C1,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
          (const char *)(unsigned int)v13,
          lpdwindex);
      wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v36);
      wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(v45);
    }
    else
    {
      v33 = 1;
      wil::details::SetEvent(v43, v9);
    }
    pHandles[0] = v44;
    pHandles[1] = v43;
    dwindex = 0;
    v14 = CoWaitForMultipleHandles(9u, 0xFFFFFFFF, 2u, pHandles, &dwindex);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x28F,
        (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
        (const char *)(unsigned int)v14,
        lpdwindexa);
    v15 = 2;
    if ( !v33 )
      v15 = 1;
    v37 = v15;
    if ( v34 && v33 )
    {
      CloudExperienceHostAPI::Speech::SpeechRecognition::PlayCortanaSound(0x44Du);
      TickCount = GetTickCount();
      v16 = CloudExperienceHostAPI::Speech::PublishSpeechControllerState(5, 0);
      if ( v16 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x299,
          (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
          (const char *)(unsigned int)v16,
          lpdwindexa);
      v35 = 0;
      string[0] = 0;
      v39 = 0;
      v50[0] = string;
      v50[1] = &v39;
      v50[2] = &v35;
      v51 = 1;
      while ( 1 )
      {
        v40 = 0;
        v17 = (__int64 *)a1[3];
        v18 = *v17;
        v40 = 0;
        v19 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v18 + 88))(v17, &v40);
        if ( v19 < 0 )
          break;
        v20 = v40;
        v45[0] = 0;
        v21 = v3 | 2;
        LODWORD(v38) = v21;
        v22 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Media::SpeechRecognition::SpeechRecognitionResult *> *>(v40);
        if ( v22 >= 0 )
          v22 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v20 + 64LL))(v20, v45);
        if ( v22 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x71B,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
            (const char *)(unsigned int)v22,
            lpdwindexa);
        LODWORD(v38) = v21 & 0xFFFFFFFD;
        v3 = v21 & 0xFFFFFFFC | 1;
        v23 = v45[0];
        v45[0] = 0;
        v36 = v23;
        v24 = *a1;
        v25 = (struct _RTL_CRITICAL_SECTION *)(*a1 + 104);
        EnterCriticalSection(v25);
        v38 = v25;
        v26 = *(_QWORD *)(v24 + 144);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v38);
        if ( a1[3] != v26 )
        {
          v15 = 4;
          v37 = 4;
          v35 = 1;
          wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v36);
          wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v40);
          goto LABEL_37;
        }
        v39 = 0;
        v27 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v23 + 56LL);
        WindowsDeleteString(string[0]);
        string[0] = 0;
        v28 = v27(v23, string);
        if ( v28 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2B7,
            (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
            (const char *)(unsigned int)v28,
            lpdwindexa);
        WindowsGetStringRawBuffer(string[0], &v39);
        if ( v39 )
        {
          LODWORD(v38) = 3;
          v29 = (*(__int64 (__fastcall **)(__int64, struct _RTL_CRITICAL_SECTION **))(*(_QWORD *)v23 + 64LL))(v23, &v38);
          if ( v29 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x2BC,
              (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
              (const char *)(unsigned int)v29,
              lpdwindexa);
          if ( (unsigned int)v38 <= 1 )
          {
            v15 = 0;
            v37 = 0;
            v36 = 0;
            Windows::Internal::CMarshaledInterfaceResult<Windows::Media::SpeechRecognition::ISpeechRecognitionResult>::Set(
              v48,
              v23);
LABEL_31:
            wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v36);
            goto LABEL_36;
          }
        }
        else if ( GetTickCount() - TickCount > *((_DWORD *)a1 + 9) )
        {
          v15 = 3;
          v37 = 3;
          goto LABEL_31;
        }
        wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v36);
        wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v40);
      }
      wil::details::in1diag3::Log_IfFailedWithExpected(
        retaddr,
        (void *)0x2D4,
        (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
        (const char *)(unsigned int)v19,
        1,
        0x800700E8);
LABEL_36:
      wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v40);
LABEL_37:
      v51 = 0;
      _lambda_1ad195b25b3bb78211fce0f7ed41c828_::operator()(v50);
      WindowsDeleteString(string[0]);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v43);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v44);
  }
  catch ( ... )
  {
    v15 = v37;
  }
  if ( *v63 == 1 )
    CloudExperienceHostSpeechTelemetry::SpeechRecoActivity::Stop(&v52, v15);
  CloudExperienceHostSpeechTelemetry::SpeechRecoActivity::~SpeechRecoActivity((CloudExperienceHostSpeechTelemetry::SpeechRecoActivity *)&v52);
  return 0;
}

```

## disassembly

```asm
0x180082e20  mov     r11, rsp
0x180082e23  mov     [r11+18h], rbx
0x180082e27  mov     [r11+20h], rsi
0x180082e2b  push    rdi
0x180082e2c  push    r12
0x180082e2e  push    r13
0x180082e30  push    r14
0x180082e32  push    r15
0x180082e34  sub     rsp, 240h
0x180082e3b  mov     rax, cs:__security_cookie
0x180082e42  xor     rax, rsp
0x180082e45  mov     [rsp+268h+var_38], rax
0x180082e4d  mov     [rsp+268h+var_1C8], rdx
0x180082e55  mov     r12, rcx
0x180082e58  xor     edi, edi
0x180082e5a  mov     r13d, edi
0x180082e5d  mov     dword ptr [rsp+268h+var_220], edi
0x180082e61  mov     [rsp+268h+var_180], edi
0x180082e68  mov     [rsp+268h+var_17C], dil
0x180082e70  mov     [rsp+268h+var_140], dil
0x180082e78  mov     [rsp+268h+var_158], edi
0x180082e7f  lea     rax, aSpeechrecoacti; "SpeechRecoActivity"
0x180082e86  mov     [r11-150h], rax
0x180082e8d  mov     [r11-148h], rdi
0x180082e94  mov     [rsp+268h+var_138], edi
0x180082e9b  xorps   xmm0, xmm0
0x180082e9e  movdqa  [rsp+268h+var_98], xmm0
0x180082ea7  xor     edx, edx; Val
0x180082ea9  mov     r8d, 98h; Size
0x180082eaf  lea     rcx, [r11-130h]; void *
0x180082eb6  call    memset_0
0x180082ebb  lea     r14d, [rdi+1]
0x180082ebf  mov     [rsp+268h+var_88], r14d
0x180082ec7  xor     eax, eax
0x180082ec9  mov     [rsp+268h+var_80], rax
0x180082ed1  lea     rax, [rsp+268h+var_180]
0x180082ed9  mov     [rsp+268h+var_78], rax
0x180082ee1  mov     [rsp+268h+var_70], rdi
0x180082ee9  mov     [rsp+268h+var_68], rdi
0x180082ef1  lea     rax, [rsp+268h+var_188]
0x180082ef9  mov     [rsp+268h+var_60], rax
0x180082f01  mov     [rsp+268h+var_58], rdi
0x180082f09  mov     [rsp+268h+var_50], edi
0x180082f10  lea     rax, [rsp+268h+var_158]
0x180082f18  mov     [rsp+268h+var_48], rax
0x180082f20  mov     [rsp+268h+var_40], dil
0x180082f28  lea     rax, ??_7SpeechRecoActivity@CloudExperienceHostSpeechTelemetry@@6B@; const CloudExperienceHostSpeechTelemetry::SpeechRecoActivity::`vftable'
0x180082f2f  mov     [rsp+268h+var_188], rax
0x180082f37  mov     [rsp+268h+var_228], 2
0x180082f3f  mov     [rsp+268h+var_237], dil
0x180082f44  mov     dword ptr [rsp+268h+var_220], r14d
0x180082f49  lea     rdx, [rsp+268h+var_220]
0x180082f4e  lea     rcx, [rsp+268h+var_1E8]
0x180082f56  call    ??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x180082f5b  nop
0x180082f5c  cmp     [r12+20h], edi
0x180082f61  jnz     short loc_180082F75
0x180082f63  mov     rcx, [rsp+268h+var_1E8]; this
0x180082f6b  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x180082f70  jmp     loc_180082FFB
0x180082f75  lea     rcx, [rsp+268h+var_188]; this
0x180082f7d  call    ?StartActivity@SpeechRecoActivity@CloudExperienceHostSpeechTelemetry@@QEAAXXZ; CloudExperienceHostSpeechTelemetry::SpeechRecoActivity::StartActivity(void)
0x180082f82  mov     [rsp+268h+var_230], rdi
0x180082f87  mov     rcx, [r12+18h]
0x180082f8c  mov     rax, [rcx]
0x180082f8f  mov     [rsp+268h+var_230], rdi
0x180082f94  lea     rdx, [rsp+268h+var_230]
0x180082f99  mov     rax, [rax+50h]
0x180082f9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082fa2  mov     rcx, [rsp+268h]; this
0x180082faa  test    eax, eax
0x180082fac  js      loc_18008347B
0x180082fb2  lea     rax, [rsp+268h+var_1E8]
0x180082fba  mov     [rsp+268h+var_1E0], rax
0x180082fc2  lea     rax, [rsp+268h+var_237]
0x180082fc7  mov     [rsp+268h+var_1D8], rax
0x180082fcf  lea     rdx, [rsp+268h+var_1E0]
0x180082fd7  mov     rcx, [rsp+268h+var_230]
0x180082fdc  call    ??$RunWhenComplete@VFtmBase@WRL@Microsoft@@PEAU?$IAsyncOperation@PEAVSpeechRecognitionCompilationResult@SpeechRecognition@Media@Windows@@@Foundation@Windows@@V_lambda_7e7f6ecefc30c60d55f0b7b31107a615_@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVSpeechRecognitionCompilationResult@SpeechRecognition@Media@Windows@@@Foundation@Windows@@$$QEAV_lambda_7e7f6ecefc30c60d55f0b7b31107a615_@@@Z; wil::details::RunWhenComplete<Microsoft::WRL::FtmBase,Windows::Foundation::IAsyncOperation<Windows::Media::SpeechRecognition::SpeechRecognitionCompilationResult *> *,_lambda_7e7f6ecefc30c60d55f0b7b31107a615_>(Windows::Foundation::IAsyncOperation<Windows::Media::SpeechRecognition::SpeechRecognitionCompilationResult *> *,_lambda_7e7f6ecefc30c60d55f0b7b31107a615_ &&)
0x180082fe1  mov     rcx, [rsp+268h]; this
0x180082fe9  test    eax, eax
0x180082feb  js      loc_18008348F
0x180082ff1  lea     rcx, [rsp+268h+var_230]
0x180082ff6  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVLaunchUriResult@System@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(void)
0x180082ffb  mov     [rsp+268h+var_238], dil
0x180083000  mov     dword ptr [rsp+268h+var_220], r14d
0x180083005  lea     rdx, [rsp+268h+var_220]
0x18008300a  lea     rcx, [rsp+268h+var_1F0]
0x18008300f  call    ??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x180083014  nop
0x180083015  mov     [rsp+268h+length], edi
0x180083019  lea     rdx, [rsp+268h+length]; length
0x18008301e  mov     rcx, [r12+8]; string
0x180083023  call    cs:__imp_WindowsGetStringRawBuffer
0x180083029  cmp     [rsp+268h+length], edi
0x18008302d  jnz     short loc_180083043
0x18008302f  mov     [rsp+268h+var_238], r14b
0x180083034  mov     rcx, [rsp+268h+var_1F0]; this
0x180083039  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x18008303e  jmp     loc_1800830D4
0x180083043  lea     rcx, [rsp+268h+var_1E0]
0x18008304b  call    ??$GetActivationFactory@UISpeechSynthesisStatics@Speech@CloudExperienceHostAPI@@@wil@@YA?AV?$com_ptr_t@UISpeechSynthesisStatics@Speech@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<CloudExperienceHostAPI::Speech::ISpeechSynthesisStatics>(ushort const *)
0x180083050  nop
0x180083051  mov     [rsp+268h+var_230], rdi
0x180083056  mov     rcx, [rsp+268h+var_1E0]
0x18008305e  mov     rax, [rcx]
0x180083061  mov     [rsp+268h+var_230], rdi
0x180083066  lea     r8, [rsp+268h+var_230]
0x18008306b  mov     rdx, [r12+8]
0x180083070  mov     rax, [rax+30h]
0x180083074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083079  mov     rcx, [rsp+268h]; this
0x180083081  test    eax, eax
0x180083083  js      loc_1800834A4
0x180083089  lea     rax, [rsp+268h+var_1F0]
0x18008308e  mov     [rsp+268h+string], rax
0x180083093  lea     rax, [rsp+268h+var_238]
0x180083098  mov     [rsp+268h+var_1F8], rax
0x18008309d  lea     rdx, [rsp+268h+string]
0x1800830a2  mov     rcx, [rsp+268h+var_230]
0x1800830a7  call    ??$RunWhenComplete@VFtmBase@WRL@Microsoft@@PEAU?$IAsyncOperationWithProgress@_NN@Foundation@Windows@@V_lambda_826daee88777eed0908553c3a88e2bef_@@@details@wil@@YAJPEAU?$IAsyncOperationWithProgress@_NN@Foundation@Windows@@$$QEAV_lambda_826daee88777eed0908553c3a88e2bef_@@@Z; wil::details::RunWhenComplete<Microsoft::WRL::FtmBase,Windows::Foundation::IAsyncOperationWithProgress<bool,double> *,_lambda_826daee88777eed0908553c3a88e2bef_>(Windows::Foundation::IAsyncOperationWithProgress<bool,double> *,_lambda_826daee88777eed0908553c3a88e2bef_ &&)
0x1800830ac  mov     rcx, [rsp+268h]; this
0x1800830b4  test    eax, eax
0x1800830b6  js      loc_1800834B8
0x1800830bc  lea     rcx, [rsp+268h+var_230]
0x1800830c1  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVLaunchUriResult@System@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(void)
0x1800830c6  nop
0x1800830c7  lea     rcx, [rsp+268h+var_1E0]
0x1800830cf  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVLaunchUriResult@System@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(void)
0x1800830d4  mov     rax, [rsp+268h+var_1E8]
0x1800830dc  mov     [rsp+268h+pHandles], rax
0x1800830e4  mov     rax, [rsp+268h+var_1F0]
0x1800830e9  mov     [rsp+268h+var_1B8], rax
0x1800830f1  mov     [rsp+268h+dwindex], edi
0x1800830f8  lea     rax, [rsp+268h+dwindex]
0x180083100  mov     [rsp+268h+lpdwindex], rax; int
0x180083105  lea     r9, [rsp+268h+pHandles]; pHandles
0x18008310d  mov     r8d, 2; cHandles
0x180083113  or      edx, 0FFFFFFFFh; dwTimeout
0x180083116  lea     ecx, [r8+7]; dwFlags
0x18008311a  call    cs:__imp_CoWaitForMultipleHandles
0x180083120  mov     rcx, [rsp+268h]; this
0x180083128  test    eax, eax
0x18008312a  js      loc_1800834CD
0x180083130  mov     esi, 2
0x180083135  mov     al, [rsp+268h+var_238]
0x180083139  test    al, al
0x18008313b  cmovz   esi, r14d
0x18008313f  mov     [rsp+268h+var_228], esi
0x180083143  cmp     [rsp+268h+var_237], dil
0x180083148  jz      loc_1800833FD
0x18008314e  test    al, al
0x180083150  jz      loc_1800833FD
0x180083156  mov     ecx, 44Dh; unsigned int
0x18008315b  call    ?PlayCortanaSound@SpeechRecognition@Speech@CloudExperienceHostAPI@@CAXI@Z; CloudExperienceHostAPI::Speech::SpeechRecognition::PlayCortanaSound(uint)
0x180083160  call    cs:__imp_GetTickCount
0x180083166  mov     [rsp+268h+var_1CC], eax
0x18008316d  xor     edx, edx
0x18008316f  lea     ecx, [rdx+5]
0x180083172  call    ?PublishSpeechControllerState@Speech@CloudExperienceHostAPI@@YAJW4SpeechControllerState@12@PEBG@Z; CloudExperienceHostAPI::Speech::PublishSpeechControllerState(CloudExperienceHostAPI::Speech::SpeechControllerState,ushort const *)
0x180083177  mov     rcx, [rsp+268h]; this
0x18008317f  test    eax, eax
0x180083181  js      loc_1800834E1
0x180083187  mov     [rsp+268h+var_236], dil
0x18008318c  mov     [rsp+268h+string], rdi
0x180083191  mov     [rsp+268h+var_218], edi
0x180083195  lea     rax, [rsp+268h+string]
0x18008319a  mov     [rsp+268h+var_1B0], rax
0x1800831a2  lea     rax, [rsp+268h+var_218]
0x1800831a7  mov     [rsp+268h+var_1A8], rax
0x1800831af  lea     rax, [rsp+268h+var_236]
0x1800831b4  mov     [rsp+268h+var_1A0], rax
0x1800831bc  mov     [rsp+268h+var_198], r14b
0x1800831c4  mov     [rsp+268h+var_210], rdi
0x1800831c9  mov     rcx, [r12+18h]
0x1800831ce  mov     rax, [rcx]
0x1800831d1  mov     [rsp+268h+var_210], rdi
0x1800831d6  lea     rdx, [rsp+268h+var_210]
0x1800831db  mov     rax, [rax+58h]
0x1800831df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800831e4  test    eax, eax
0x1800831e6  js      loc_1800833A6
0x1800831ec  mov     rbx, [rsp+268h+var_210]
0x1800831f1  mov     [rsp+268h+var_1E0], rdi
0x1800831f9  or      r13d, 2
0x1800831fd  mov     dword ptr [rsp+268h+var_220], r13d
0x180083202  mov     rcx, rbx
0x180083205  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVSpeechRecognitionResult@SpeechRecognition@Media@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVSpeechRecognitionResult@SpeechRecognition@Media@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Media::SpeechRecognition::SpeechRecognitionResult *> *>(Windows::Foundation::IAsyncOperation<Windows::Media::SpeechRecognition::SpeechRecognitionResult *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x18008320a  test    eax, eax
0x18008320c  js      short loc_180083226
0x18008320e  mov     rax, [rbx]
0x180083211  lea     rdx, [rsp+268h+var_1E0]
0x180083219  mov     rcx, rbx
0x18008321c  mov     rax, [rax+40h]
0x180083220  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083225  nop
0x180083226  mov     rcx, [rsp+268h]; this
0x18008322e  test    eax, eax
0x180083230  js      loc_1800834F6
0x180083236  and     r13d, 0FFFFFFFDh
0x18008323a  mov     dword ptr [rsp+268h+var_220], r13d
0x18008323f  or      r13d, r14d
0x180083242  mov     r15, [rsp+268h+var_1E0]
0x18008324a  mov     [rsp+268h+var_1E0], rdi
0x180083252  mov     [rsp+268h+var_230], r15
0x180083257  mov     rdi, [r12]
0x18008325b  lea     rbx, [rdi+68h]
0x18008325f  mov     rcx, rbx; lpCriticalSection
0x180083262  call    cs:__imp_EnterCriticalSection
0x180083268  mov     [rsp+268h+var_220], rbx
0x18008326d  mov     rbx, [rdi+90h]
0x180083274  lea     rcx, [rsp+268h+var_220]
0x180083279  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18008327e  cmp     [r12+18h], rbx
0x180083283  jz      short loc_1800832AF
0x180083285  mov     esi, 4
0x18008328a  mov     [rsp+268h+var_228], esi
0x18008328e  mov     [rsp+268h+var_236], r14b
0x180083293  lea     rcx, [rsp+268h+var_230]
0x180083298  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVLaunchUriResult@System@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(void)
0x18008329d  nop
0x18008329e  lea     rcx, [rsp+268h+var_210]
0x1800832a3  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVLaunchUriResult@System@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(void)
0x1800832a8  xor     edi, edi
0x1800832aa  jmp     loc_1800833DB
0x1800832af  xor     edi, edi
0x1800832b1  mov     [rsp+268h+var_218], edi
0x1800832b5  mov     rax, [r15]
0x1800832b8  mov     rbx, [rax+38h]
0x1800832bc  mov     rcx, [rsp+268h+string]; string
0x1800832c1  call    cs:__imp_WindowsDeleteString
0x1800832c7  mov     [rsp+268h+string], rdi
0x1800832cc  lea     rdx, [rsp+268h+string]
0x1800832d1  mov     rcx, r15
0x1800832d4  mov     rax, rbx
0x1800832d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800832dc  mov     rcx, [rsp+268h]; this
0x1800832e4  test    eax, eax
0x1800832e6  js      loc_18008350B
0x1800832ec  lea     rdx, [rsp+268h+var_218]; length
0x1800832f1  mov     rcx, [rsp+268h+string]; string
0x1800832f6  call    cs:__imp_WindowsGetStringRawBuffer
0x1800832fc  cmp     [rsp+268h+var_218], edi
0x180083300  jbe     short loc_18008336D
0x180083302  mov     dword ptr [rsp+268h+var_220], 3
0x18008330a  mov     rax, [r15]
0x18008330d  lea     rdx, [rsp+268h+var_220]
0x180083312  mov     rcx, r15
0x180083315  mov     rax, [rax+40h]
0x180083319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008331e  mov     rcx, [rsp+268h]; this
0x180083326  test    eax, eax
0x180083328  jns     short loc_18008333E
0x18008332a  mov     r9d, eax; char *
0x18008332d  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\cloudexperiencehost"...
0x180083334  mov     edx, 2BCh; void *
0x180083339  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008333e  cmp     dword ptr [rsp+268h+var_220], r14d
0x180083343  ja      short loc_18008338C
0x180083345  mov     esi, edi
0x180083347  mov     [rsp+268h+var_228], edi
0x18008334b  mov     [rsp+268h+var_230], rdi
0x180083350  mov     rdx, r15
0x180083353  mov     rcx, [rsp+268h+var_1C8]
0x18008335b  call    ?Set@?$CMarshaledInterfaceResult@UISpeechRecognitionResult@SpeechRecognition@Media@Windows@@@Internal@Windows@@QEAAJPEAUISpeechRecognitionResult@SpeechRecognition@Media@3@@Z; Windows::Internal::CMarshaledInterfaceResult<Windows::Media::SpeechRecognition::ISpeechRecognitionResult>::Set(Windows::Media::SpeechRecognition::ISpeechRecognitionResult *)
0x180083360  nop
0x180083361  lea     rcx, [rsp+268h+var_230]
0x180083366  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVLaunchUriResult@System@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(void)
0x18008336b  jmp     short loc_1800833D0
0x18008336d  call    cs:__imp_GetTickCount
0x180083373  sub     eax, [rsp+268h+var_1CC]
0x18008337a  cmp     eax, [r12+24h]
0x18008337f  jbe     short loc_18008338C
0x180083381  mov     esi, 3
0x180083386  mov     [rsp+268h+var_228], esi
0x18008338a  jmp     short loc_180083361
0x18008338c  lea     rcx, [rsp+268h+var_230]
0x180083391  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVLaunchUriResult@System@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(void)
0x180083396  nop
0x180083397  lea     rcx, [rsp+268h+var_210]
0x18008339c  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVLaunchUriResult@System@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(void)
0x1800833a1  jmp     loc_1800831C4
0x1800833a6  mov     rcx, [rsp+268h]; this
0x1800833ae  mov     [rsp+268h+var_240], 800700E8h; unsigned int
0x1800833b6  mov     dword ptr [rsp+268h+lpdwindex], r14d; int
0x1800833bb  mov     r9d, eax; char *
0x1800833be  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\cloudexperiencehost"...
0x1800833c5  mov     edx, 2D4h; void *
0x1800833ca  call    ?Log_IfFailedWithExpected@in1diag3@details@wil@@YAJPEAXIPEBDJIZZ; wil::details::in1diag3::Log_IfFailedWithExpected(void *,uint,char const *,long,uint,...)
0x1800833cf  nop
0x1800833d0  lea     rcx, [rsp+268h+var_210]
0x1800833d5  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVLaunchUriResult@System@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(void)
0x1800833da  nop
0x1800833db  mov     [rsp+268h+var_198], dil
0x1800833e3  lea     rcx, [rsp+268h+var_1B0]
0x1800833eb  call    ??R_lambda_1ad195b25b3bb78211fce0f7ed41c828_@@QEBA@XZ; _lambda_1ad195b25b3bb78211fce0f7ed41c828_::operator()(void)
0x1800833f0  nop
0x1800833f1  mov     rcx, [rsp+268h+string]; string
0x1800833f6  call    cs:__imp_WindowsDeleteString
0x1800833fc  nop
  ... truncated ...
```
