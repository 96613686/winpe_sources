# CLockHost::OnBioFeedbackUpdate(Windows::Internal::UI::Logon::CredProvData::BioFeedbackState,HSTRING__ *,HSTRING__ *)

- ea: `0x18002aca0`
- end: `0x18002b1ed`
- name: `?OnBioFeedbackUpdate@CLockHost@@UEAAJW4BioFeedbackState@CredProvData@Logon@UI@Internal@Windows@@PEAUHSTRING__@@1@Z`
- size: `1357`
- prototype: `int __high(enum Windows::Internal::UI::Logon::CredProvData::BioFeedbackState, HSTRING, HSTRING)`
- caller_count: `0`
- callee_count: `28`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000cd1c`
- `0x18000df10`
- `0x180017dec`
- `0x18001c56c`
- `0x18001c860`
- `0x18001d850`
- `0x18001db70`
- `0x18001f3a0`
- `0x18002a060`
- `0x18002a228`
- `0x18002a8e8`
- `0x18002aca0`
- `0x18002b1f4`
- `0x18002fe2c`
- `0x1800342ac`
- `0x18003db60`
- `0x180046f10`
- `0x18004ee30`
- `0x18005b3e4`
- `0x18005d488`
- `0x180061ebc`
- `0x180062d84`
- `0x18006c000`
- `0x18006cad0`
- `0x18006f0d8`
- `0x180087778`
- `0x18009b790`
- `0x18009d010`

## import_xrefs

- `KERNEL32!DeleteTimerQueueTimer` at `0x18002af5c`
- `KERNEL32!DeleteTimerQueueTimer` at `0x18002af5c`
- `KERNEL32!ReleaseSRWLockShared` at `0x18002add8`
- `KERNEL32!ReleaseSRWLockShared` at `0x18002add8`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002b15e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002b15e`
- `KERNEL32!AcquireSRWLockShared` at `0x18002adc0`
- `KERNEL32!AcquireSRWLockShared` at `0x18002adc0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002ae37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002aea5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002ae37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002aea5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ae54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002aec2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ae54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002aec2`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18002af46`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18002af46`

## string_xrefs

- `0x18002acfd`: `CLockHost_OnBioFeedbackUpdate_Activity`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CLockHost::OnBioFeedbackUpdate(RTL_SRWLOCK *a1, int a2, HSTRING a3, HSTRING a4)
{
  void *v8; // rdi
  HRESULT v9; // eax
  int v10; // ebx
  HSTRING v11; // rcx
  HSTRING v12; // rax
  HSTRING v13; // rbx
  HRESULT v14; // eax
  unsigned int v15; // esi
  HSTRING v16; // rcx
  unsigned int v17; // edx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v21; // rcx
  struct IUnknown **v22; // rax
  char v23; // di
  int v24[2]; // [rsp+20h] [rbp-E0h] BYREF
  HSTRING newString; // [rsp+28h] [rbp-D8h] BYREF
  void *v26; // [rsp+30h] [rbp-D0h] BYREF
  struct _GUID Buf1; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE Timer; // [rsp+48h] [rbp-B8h]
  __int64 v29; // [rsp+50h] [rbp-B0h] BYREF
  int v30; // [rsp+58h] [rbp-A8h]
  void *v31; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING v32; // [rsp+68h] [rbp-98h] BYREF
  void **v33; // [rsp+70h] [rbp-90h] BYREF
  int v34; // [rsp+78h] [rbp-88h] BYREF
  char v35; // [rsp+7Ch] [rbp-84h]
  int v36; // [rsp+A0h] [rbp-60h] BYREF
  const char *v37; // [rsp+A8h] [rbp-58h]
  __int64 v38; // [rsp+B0h] [rbp-50h]
  char v39; // [rsp+B8h] [rbp-48h]
  int v40; // [rsp+C0h] [rbp-40h]
  _BYTE v41[152]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v42; // [rsp+160h] [rbp+60h]
  int v43; // [rsp+170h] [rbp+70h]
  __int64 v44; // [rsp+178h] [rbp+78h]
  int *v45; // [rsp+180h] [rbp+80h]
  _DWORD *v46; // [rsp+188h] [rbp+88h] BYREF
  _BYTE v47[48]; // [rsp+190h] [rbp+90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]

  v33 = &wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::`vftable';
  v34 = 0;
  v35 = 0;
  v39 = 0;
  v36 = 0;
  v37 = "CLockHost_OnBioFeedbackUpdate_Activity";
  v38 = 0;
  v40 = 0;
  v42 = 0;
  memset_0(v41, 0, sizeof(v41));
  v43 = 1;
  v44 = 0;
  v45 = &v34;
  v46 = 0;
  wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(
    (wil::details::ThreadFailureCallbackHolder *)v47,
    (struct wil::details::IFailureCallback *)&v33,
    (struct wil::CallContextInfo *)&v36,
    0);
  v33 = &LogonControllerTelemetry::CLockHost_OnBioFeedbackUpdate_Activity::`vftable';
  Buf1 = *GetFirstRunTelemetryCorrelationId(&Buf1);
  if ( memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
    wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(
      &v33,
      &Buf1);
  LogonControllerTelemetry::CLockHost_OnBioFeedbackUpdate_Activity::StartActivity((LogonControllerTelemetry::CLockHost_OnBioFeedbackUpdate_Activity *)&v33);
  *(_QWORD *)v24 = 0;
  AcquireSRWLockShared(a1 + 7);
  if ( a1[8].Ptr )
  {
    v22 = (struct IUnknown **)IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ILockScreenDirectorPrivate>>(v24);
    if ( a1[8].Ptr )
      Microsoft::WRL::AgileRef::CopyTo(
        (Microsoft::WRL::AgileRef *)&a1[8],
        &GUID_d72586df_0aac_4c94_9370_9863360cdb6b,
        v22);
    else
      *v22 = 0;
  }
  if ( a1 != (RTL_SRWLOCK *)-56LL )
    ReleaseSRWLockShared(a1 + 7);
  if ( !*(_QWORD *)v24 )
    goto LABEL_23;
  v8 = operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
  if ( v8 )
  {
    *((_QWORD *)v8 + 1) = 0;
    *(_QWORD *)v8 = &CRefCountedObject<Windows::Internal::String>::`vftable';
    *((_DWORD *)v8 + 4) = 0;
  }
  else
  {
    v8 = 0;
  }
  v26 = v8;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v26);
  newString = 0;
  v9 = WindowsDuplicateString(a3, &newString);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x261,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockhost.cpp",
      (const char *)(unsigned int)v9,
      v24[0]);
    Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v26);
    v19 = *(_QWORD *)v24;
    if ( *(_QWORD *)v24 )
    {
      *(_QWORD *)v24 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    v33 = &LogonControllerTelemetry::CLockHost_OnBioFeedbackUpdate_Activity::`vftable';
    if ( !v46 )
      goto LABEL_28;
    wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(&v33, &Buf1);
    if ( v46 && *v46 == 1 )
    {
      v23 = 1;
    }
    else
    {
      v23 = 0;
      wil::details::shared_object<wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LogonControllerLogger,_TlgReflectorTag_Param0IsProviderType>>::reset(&v46);
    }
    if ( *(_QWORD *)&Buf1.Data1 )
      ReleaseSRWLockExclusive(*(PSRWLOCK *)&Buf1.Data1);
    if ( v23 )
    {
LABEL_28:
      if ( *v45 == 1 )
      {
        wil::ActivityBase<LogonControllerLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LogonControllerLogger,_TlgReflectorTag_Param0IsProviderType>::SetUnhandledException();
        wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(&v33);
      }
    }
    goto LABEL_30;
  }
  v11 = (HSTRING)*((_QWORD *)v8 + 1);
  *((_QWORD *)v8 + 1) = newString;
  WindowsDeleteString(v11);
  v12 = (HSTRING)operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
  v13 = v12;
  if ( v12 )
  {
    *((_QWORD *)v12 + 1) = 0;
    *(_QWORD *)v12 = &CRefCountedObject<Windows::Internal::String>::`vftable';
    *((_DWORD *)v12 + 4) = 0;
  }
  else
  {
    v13 = 0;
  }
  newString = v13;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&newString);
  *(_QWORD *)&Buf1.Data1 = 0;
  v14 = WindowsDuplicateString(a4, (HSTRING *)&Buf1);
  v15 = v14;
  if ( v14 >= 0 )
  {
    v16 = (HSTRING)*((_QWORD *)v13 + 1);
    *((_QWORD *)v13 + 1) = *(_QWORD *)&Buf1.Data1;
    WindowsDeleteString(v16);
    v29 = *(_QWORD *)v24;
    if ( *(_QWORD *)v24 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v24 + 8LL))(*(_QWORD *)v24);
    v30 = a2;
    v31 = v8;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v31);
    v32 = v13;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v32);
    if ( (unsigned int)IsDebuggerPresent(a1[11].Ptr) )
    {
      v10 = CCLambdaAdapter_long____cdecl___void____1_::Adapt__lambda_9ce5d24c9eef2ab8a85362b2f456ee0e___(&v29);
    }
    else
    {
      CRPCTimeout::CRPCTimeout(&Buf1, v17);
      v10 = CCLambdaAdapter_long____cdecl___void____1_::Adapt__lambda_9ce5d24c9eef2ab8a85362b2f456ee0e___(&v29);
      if ( v10 < 0 && LOBYTE(Buf1.Data2) )
        v10 = -2147417825;
      if ( *(int *)Buf1.Data4 >= 0 )
      {
        *(_DWORD *)Buf1.Data4 = -2147467259;
        CoDisableCallCancellation(0);
        if ( Timer )
          DeleteTimerQueueTimer(0, Timer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      }
    }
    lambda_9ce5d24c9eef2ab8a85362b2f456ee0e_::__lambda_9ce5d24c9eef2ab8a85362b2f456ee0e_(&v29);
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x26D,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockhost.cpp",
        (const char *)(unsigned int)v10,
        v24[0]);
      Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&newString);
      Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v26);
      v21 = *(_QWORD *)v24;
      if ( *(_QWORD *)v24 )
      {
        *(_QWORD *)v24 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      }
      v33 = &LogonControllerTelemetry::CLockHost_OnBioFeedbackUpdate_Activity::`vftable';
      wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v33);
      goto LABEL_30;
    }
    Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&newString);
    Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v26);
    v18 = *(_QWORD *)v24;
    if ( *(_QWORD *)v24 )
    {
      *(_QWORD *)v24 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
LABEL_23:
    wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v33, 0);
    v33 = &LogonControllerTelemetry::CLockHost_OnBioFeedbackUpdate_Activity::`vftable';
    wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v33);
    v10 = 0;
LABEL_30:
    wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v33);
    return (unsigned int)v10;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x263,
    (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockhost.cpp",
    (const char *)(unsigned int)v14,
    v24[0]);
  Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&newString);
  Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v26);
  Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(v24);
  LogonControllerTelemetry::CLockHost_OnBioFeedbackUpdate_Activity::~CLockHost_OnBioFeedbackUpdate_Activity((LogonControllerTelemetry::CLockHost_OnBioFeedbackUpdate_Activity *)&v33);
  return v15;
}

```

## disassembly

```asm
0x18002aca0  mov     [rsp-8+arg_8], rbx
0x18002aca5  push    rbp
0x18002aca6  push    rsi
0x18002aca7  push    rdi
0x18002aca8  push    r12
0x18002acaa  push    r13
0x18002acac  push    r14
0x18002acae  push    r15
0x18002acb0  lea     rbp, [rsp-0D0h]
0x18002acb8  sub     rsp, 1D0h
0x18002acbf  mov     rax, cs:__security_cookie
0x18002acc6  xor     rax, rsp
0x18002acc9  mov     [rbp+100h+var_40], rax
0x18002acd0  mov     r15, r9
0x18002acd3  mov     rsi, r8
0x18002acd6  mov     r12d, edx
0x18002acd9  mov     r14, rcx
0x18002acdc  lea     rax, ??_7?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@6B@; const wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::`vftable'
0x18002ace3  mov     [rsp+200h+var_190], rax
0x18002ace8  xor     r13d, r13d
0x18002aceb  mov     [rsp+200h+var_188], r13d
0x18002acf0  mov     [rsp+200h+var_184], r13b
0x18002acf5  mov     [rbp+100h+var_148], r13b
0x18002acf9  mov     [rbp+100h+var_160], r13d
0x18002acfd  lea     rax, aClockhostOnbio; "CLockHost_OnBioFeedbackUpdate_Activity"
0x18002ad04  mov     [rbp+100h+var_158], rax
0x18002ad08  mov     [rbp+100h+var_150], r13
0x18002ad0c  mov     [rbp+100h+var_140], r13d
0x18002ad10  xorps   xmm0, xmm0
0x18002ad13  movdqa  [rbp+100h+var_A0], xmm0
0x18002ad18  xor     edx, edx; Val
0x18002ad1a  mov     r8d, 98h; Size
0x18002ad20  lea     rcx, [rbp+100h+var_138]; void *
0x18002ad24  call    memset_0
0x18002ad29  nop
0x18002ad2a  mov     [rbp+100h+var_90], 1
0x18002ad31  xor     eax, eax
0x18002ad33  mov     [rbp+100h+var_88], rax
0x18002ad37  lea     rax, [rsp+200h+var_188]
0x18002ad3c  mov     [rbp+100h+var_80], rax
0x18002ad43  mov     [rbp+100h+var_78], r13
0x18002ad4a  xor     r9d, r9d; bool
0x18002ad4d  lea     r8, [rbp+100h+var_160]; struct wil::CallContextInfo *
0x18002ad51  lea     rdx, [rsp+200h+var_190]; struct wil::details::IFailureCallback *
0x18002ad56  lea     rcx, [rbp+100h+var_70]; this
0x18002ad5d  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x18002ad62  nop
0x18002ad63  lea     rax, ??_7CLockHost_OnBioFeedbackUpdate_Activity@LogonControllerTelemetry@@6B@; const LogonControllerTelemetry::CLockHost_OnBioFeedbackUpdate_Activity::`vftable'
0x18002ad6a  mov     [rsp+200h+var_190], rax
0x18002ad6f  lea     rcx, [rsp+200h+Buf1]; retstr
0x18002ad74  call    ?GetFirstRunTelemetryCorrelationId@@YA?AU_GUID@@XZ; GetFirstRunTelemetryCorrelationId(void)
0x18002ad79  movups  xmm0, xmmword ptr [rax]
0x18002ad7c  movdqu  [rsp+200h+Buf1], xmm0
0x18002ad82  lea     r8d, [r13+10h]; Size
0x18002ad86  lea     rdx, GUID_NULL; Buf2
0x18002ad8d  lea     rcx, [rsp+200h+Buf1]; Buf1
0x18002ad92  call    memcmp_0
0x18002ad97  test    eax, eax
0x18002ad99  jz      short loc_18002ADAA
0x18002ad9b  lea     rdx, [rsp+200h+Buf1]
0x18002ada0  lea     rcx, [rsp+200h+var_190]
0x18002ada5  call    ?SetRelatedActivityId@?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXAEBU_GUID@@@Z; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(_GUID const &)
0x18002adaa  lea     rcx, [rsp+200h+var_190]; this
0x18002adaf  call    ?StartActivity@CLockHost_OnBioFeedbackUpdate_Activity@LogonControllerTelemetry@@QEAAXXZ; LogonControllerTelemetry::CLockHost_OnBioFeedbackUpdate_Activity::StartActivity(void)
0x18002adb4  mov     qword ptr [rsp+200h+var_1E0], r13; int
0x18002adb9  lea     rbx, [r14+38h]
0x18002adbd  mov     rcx, rbx; SRWLock
0x18002adc0  call    cs:__imp_AcquireSRWLockShared
0x18002adc6  cmp     [r14+40h], r13
0x18002adca  jnz     loc_18002B0D6
0x18002add0  test    rbx, rbx
0x18002add3  jz      short loc_18002ADDE
0x18002add5  mov     rcx, rbx; SRWLock
0x18002add8  call    cs:__imp_ReleaseSRWLockShared
0x18002adde  mov     rcx, qword ptr [rsp+200h+var_1E0]
0x18002ade3  test    rcx, rcx
0x18002ade6  jz      loc_18002AFA3
0x18002adec  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002adf3  mov     ecx, 18h; unsigned __int64
0x18002adf8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002adfd  mov     rdi, rax
0x18002ae00  lea     rax, ??_7?$CRefCountedObject@VString@Internal@Windows@@@@6B@; const CRefCountedObject<Windows::Internal::String>::`vftable'
0x18002ae07  test    rdi, rdi
0x18002ae0a  jz      loc_18002AFCA
0x18002ae10  mov     [rdi+8], r13
0x18002ae14  mov     [rdi], rax
0x18002ae17  mov     [rdi+10h], r13d
0x18002ae1b  mov     [rsp+200h+var_1D0], rdi
0x18002ae20  lea     rcx, [rsp+200h+var_1D0]
0x18002ae25  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18002ae2a  mov     [rsp+200h+newString], r13
0x18002ae2f  lea     rdx, [rsp+200h+newString]; newString
0x18002ae34  mov     rcx, rsi; string
0x18002ae37  call    cs:__imp_WindowsDuplicateString
0x18002ae3d  mov     ebx, eax
0x18002ae3f  test    eax, eax
0x18002ae41  js      loc_18002AFD2
0x18002ae47  mov     rcx, [rdi+8]; string
0x18002ae4b  mov     rax, [rsp+200h+newString]
0x18002ae50  mov     [rdi+8], rax
0x18002ae54  call    cs:__imp_WindowsDeleteString
0x18002ae5a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002ae61  mov     ecx, 18h; unsigned __int64
0x18002ae66  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002ae6b  mov     rbx, rax
0x18002ae6e  test    rax, rax
0x18002ae71  jz      loc_18002B10F
0x18002ae77  mov     [rax+8], r13
0x18002ae7b  lea     rax, ??_7?$CRefCountedObject@VString@Internal@Windows@@@@6B@; const CRefCountedObject<Windows::Internal::String>::`vftable'
0x18002ae82  mov     [rbx], rax
0x18002ae85  mov     [rbx+10h], r13d
0x18002ae89  mov     [rsp+200h+newString], rbx
0x18002ae8e  lea     rcx, [rsp+200h+newString]
0x18002ae93  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18002ae98  mov     qword ptr [rsp+200h+Buf1], r13
0x18002ae9d  lea     rdx, [rsp+200h+Buf1]; newString
0x18002aea2  mov     rcx, r15; string
0x18002aea5  call    cs:__imp_WindowsDuplicateString
0x18002aeab  mov     esi, eax
0x18002aead  test    eax, eax
0x18002aeaf  js      loc_18002B166
0x18002aeb5  mov     rcx, [rbx+8]; string
0x18002aeb9  mov     rax, qword ptr [rsp+200h+Buf1]
0x18002aebe  mov     [rbx+8], rax
0x18002aec2  call    cs:__imp_WindowsDeleteString
0x18002aec8  mov     rcx, qword ptr [rsp+200h+var_1E0]
0x18002aecd  mov     [rsp+200h+var_1B0], rcx
0x18002aed2  test    rcx, rcx
0x18002aed5  jz      short loc_18002AEE3
0x18002aed7  mov     rax, [rcx]
0x18002aeda  mov     rax, [rax+8]
0x18002aede  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aee3  mov     [rsp+200h+var_1A8], r12d
0x18002aee8  mov     [rsp+200h+var_1A0], rdi
0x18002aeed  lea     rcx, [rsp+200h+var_1A0]
0x18002aef2  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18002aef7  mov     [rsp+200h+var_198], rbx
0x18002aefc  lea     rcx, [rsp+200h+var_198]
0x18002af01  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18002af06  mov     rcx, [r14+58h]; hProcess
0x18002af0a  call    ?IsDebuggerPresent@@YAHPEAX@Z; IsDebuggerPresent(void *)
0x18002af0f  test    eax, eax
0x18002af11  jnz     loc_18002B0FE
0x18002af17  lea     rcx, [rsp+200h+Buf1]; Parameter
0x18002af1c  call    ??0CRPCTimeout@@QEAA@K@Z; CRPCTimeout::CRPCTimeout(ulong)
0x18002af21  lea     rcx, [rsp+200h+var_1B0]
0x18002af26  call    CCLambdaAdapter_long____cdecl___void____1___Adapt__lambda_9ce5d24c9eef2ab8a85362b2f456ee0e___
0x18002af2b  mov     ebx, eax
0x18002af2d  test    eax, eax
0x18002af2f  js      loc_18002B117
0x18002af35  cmp     dword ptr [rsp+200h+Buf1+8], r13d
0x18002af3a  jl      short loc_18002AF62
0x18002af3c  mov     dword ptr [rsp+200h+Buf1+8], 80004005h
0x18002af44  xor     ecx, ecx; pReserved
0x18002af46  call    cs:__imp_CoDisableCallCancellation
0x18002af4c  mov     rdx, [rsp+200h+Timer]; Timer
0x18002af51  test    rdx, rdx
0x18002af54  jz      short loc_18002AF62
0x18002af56  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18002af5a  xor     ecx, ecx; TimerQueue
0x18002af5c  call    cs:__imp_DeleteTimerQueueTimer
0x18002af62  lea     rcx, [rsp+200h+var_1B0]
0x18002af67  call    _lambda_9ce5d24c9eef2ab8a85362b2f456ee0e_____lambda_9ce5d24c9eef2ab8a85362b2f456ee0e_
0x18002af6c  test    ebx, ebx
0x18002af6e  js      loc_18002B071
0x18002af74  lea     rcx, [rsp+200h+newString]
0x18002af79  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x18002af7e  lea     rcx, [rsp+200h+var_1D0]
0x18002af83  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x18002af88  mov     rcx, qword ptr [rsp+200h+var_1E0]
0x18002af8d  test    rcx, rcx
0x18002af90  jz      short loc_18002AFA3
0x18002af92  mov     qword ptr [rsp+200h+var_1E0], r13
0x18002af97  mov     rax, [rcx]
0x18002af9a  mov     rax, [rax+10h]
0x18002af9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002afa3  xor     edx, edx
0x18002afa5  lea     rcx, [rsp+200h+var_190]
0x18002afaa  call    ?Stop@?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18002afaf  lea     rax, ??_7CLockHost_OnBioFeedbackUpdate_Activity@LogonControllerTelemetry@@6B@; const LogonControllerTelemetry::CLockHost_OnBioFeedbackUpdate_Activity::`vftable'
0x18002afb6  mov     [rsp+200h+var_190], rax
0x18002afbb  lea     rcx, [rsp+200h+var_190]
0x18002afc0  call    ?Destroy@?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18002afc5  mov     ebx, r13d
0x18002afc8  jmp     short loc_18002B03B
0x18002afca  mov     rdi, r13
0x18002afcd  jmp     loc_18002AE1B
0x18002afd2  mov     rcx, [rbp+108h]; this
0x18002afd9  mov     r9d, eax; char *
0x18002afdc  lea     r8, aPcshellShellAu_7; "pcshell\\shell\\auth\\authux\\controlle"...
0x18002afe3  mov     edx, 261h; void *
0x18002afe8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002afed  lea     rcx, [rsp+200h+var_1D0]
0x18002aff2  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x18002aff7  mov     rcx, qword ptr [rsp+200h+var_1E0]
0x18002affc  test    rcx, rcx
0x18002afff  jz      short loc_18002B012
0x18002b001  mov     qword ptr [rsp+200h+var_1E0], r13
0x18002b006  mov     rax, [rcx]
0x18002b009  mov     rax, [rax+10h]
0x18002b00d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b012  lea     rax, ??_7CLockHost_OnBioFeedbackUpdate_Activity@LogonControllerTelemetry@@6B@; const LogonControllerTelemetry::CLockHost_OnBioFeedbackUpdate_Activity::`vftable'
0x18002b019  mov     [rsp+200h+var_190], rax
0x18002b01e  cmp     [rbp+100h+var_78], r13
0x18002b025  jnz     loc_18002B1B0
0x18002b02b  mov     rcx, [rbp+100h+var_80]
0x18002b032  cmp     dword ptr [rcx], 1
0x18002b035  jz      loc_18002B131
0x18002b03b  lea     rcx, [rsp+200h+var_190]
0x18002b040  call    ??1?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18002b045  mov     eax, ebx
0x18002b047  mov     rcx, [rbp+100h+var_40]
0x18002b04e  xor     rcx, rsp; StackCookie
0x18002b051  call    __security_check_cookie
0x18002b056  mov     rbx, [rsp+200h+arg_8]
0x18002b05e  add     rsp, 1D0h
0x18002b065  pop     r15
0x18002b067  pop     r14
0x18002b069  pop     r13
0x18002b06b  pop     r12
0x18002b06d  pop     rdi
0x18002b06e  pop     rsi
0x18002b06f  pop     rbp
0x18002b070  retn
0x18002b071  mov     rcx, [rbp+108h]; this
0x18002b078  mov     r9d, ebx; char *
0x18002b07b  lea     r8, aPcshellShellAu_7; "pcshell\\shell\\auth\\authux\\controlle"...
0x18002b082  mov     edx, 26Dh; void *
0x18002b087  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b08c  lea     rcx, [rsp+200h+newString]
0x18002b091  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x18002b096  lea     rcx, [rsp+200h+var_1D0]
0x18002b09b  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x18002b0a0  mov     rcx, qword ptr [rsp+200h+var_1E0]
0x18002b0a5  test    rcx, rcx
0x18002b0a8  jz      short loc_18002B0BB
0x18002b0aa  mov     qword ptr [rsp+200h+var_1E0], r13
0x18002b0af  mov     rax, [rcx]
0x18002b0b2  mov     rax, [rax+10h]
0x18002b0b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b0bb  lea     rax, ??_7CLockHost_OnBioFeedbackUpdate_Activity@LogonControllerTelemetry@@6B@; const LogonControllerTelemetry::CLockHost_OnBioFeedbackUpdate_Activity::`vftable'
0x18002b0c2  mov     [rsp+200h+var_190], rax
0x18002b0c7  lea     rcx, [rsp+200h+var_190]
0x18002b0cc  call    ?Destroy@?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18002b0d1  jmp     loc_18002B03B
0x18002b0d6  lea     rcx, [rsp+200h+var_1E0]
0x18002b0db  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UILockScreenDirectorPrivate@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UILockScreenDirectorPrivate@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ILockScreenDirectorPrivate>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ILockScreenDirectorPrivate>>)
0x18002b0e0  cmp     [r14+40h], r13
0x18002b0e4  jz      short loc_18002B129
0x18002b0e6  mov     r8, rax; struct IUnknown **
0x18002b0e9  lea     rdx, _GUID_d72586df_0aac_4c94_9370_9863360cdb6b; struct _GUID *
0x18002b0f0  lea     rcx, [r14+40h]; this
0x18002b0f4  call    ?CopyTo@AgileRef@WRL@Microsoft@@QEBAJAEBU_GUID@@PEAPEAUIUnknown@@@Z; Microsoft::WRL::AgileRef::CopyTo(_GUID const &,IUnknown * *)
0x18002b0f9  jmp     loc_18002ADD0
0x18002b0fe  lea     rcx, [rsp+200h+var_1B0]
0x18002b103  call    CCLambdaAdapter_long____cdecl___void____1___Adapt__lambda_9ce5d24c9eef2ab8a85362b2f456ee0e___
0x18002b108  mov     ebx, eax
0x18002b10a  jmp     loc_18002AF62
0x18002b10f  mov     rbx, r13
0x18002b112  jmp     loc_18002AE89
0x18002b117  mov     eax, 8001011Fh
0x18002b11c  cmp     byte ptr [rsp+200h+Buf1+4], r13b
0x18002b121  cmovnz  ebx, eax
0x18002b124  jmp     loc_18002AF35
0x18002b129  mov     [rax], r13
0x18002b12c  jmp     loc_18002ADD0
0x18002b131  call    ?SetUnhandledException@?$ActivityData@VLogonControllerLogger@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VLogonControllerLogger@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAJXZ; wil::ActivityBase<LogonControllerLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LogonControllerLogger,_TlgReflectorTag_Param0IsProviderType>::SetUnhandledException(void)
0x18002b136  nop
0x18002b137  lea     rcx, [rsp+200h+var_190]
0x18002b13c  call    ?ReportStopActivity@?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x18002b141  jmp     loc_18002B03B
0x18002b146  test    dil, dil
0x18002b149  jz      loc_18002B03B
0x18002b14f  jmp     loc_18002B02B
0x18002b154  mov     rcx, qword ptr [rsp+200h+Buf1]; SRWLock
0x18002b159  test    rcx, rcx
0x18002b15c  jz      short loc_18002B146
0x18002b15e  call    cs:__imp_ReleaseSRWLockExclusive
0x18002b164  jmp     short loc_18002B146
0x18002b166  mov     rcx, [rbp+108h]; this
0x18002b16d  mov     r9d, esi; char *
0x18002b170  lea     r8, aPcshellShellAu_7; "pcshell\\shell\\auth\\authux\\controlle"...
0x18002b177  mov     edx, 263h; void *
0x18002b17c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b181  lea     rcx, [rsp+200h+newString]
0x18002b186  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x18002b18b  lea     rcx, [rsp+200h+var_1D0]
0x18002b190  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x18002b195  lea     rcx, [rsp+200h+var_1E0]
0x18002b19a  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18002b19f  lea     rcx, [rsp+200h+var_190]; this
0x18002b1a4  call    ??1CLockHost_OnBioFeedbackUpdate_Activity@LogonControllerTelemetry@@QEAA@XZ; LogonControllerTelemetry::CLockHost_OnBioFeedbackUpdate_Activity::~CLockHost_OnBioFeedbackUpdate_Activity(void)
0x18002b1a9  mov     eax, esi
0x18002b1ab  jmp     loc_18002B047
0x18002b1b0  lea     rdx, [rsp+200h+Buf1]
0x18002b1b5  lea     rcx, [rsp+200h+var_190]
0x18002b1ba  call    ?LockExclusive@?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002b1bf  mov     rax, [rbp+100h+var_78]
0x18002b1c6  test    rax, rax
0x18002b1c9  jz      short loc_18002B1D8
  ... truncated ...
```
