# LaunchBioEnrollmentProtocolHandler::Execute(void)

- ea: `0x18001bfb0`
- end: `0x18001c2b0`
- name: `?Execute@LaunchBioEnrollmentProtocolHandler@@UEAAJXZ`
- size: `768`
- prototype: `__int64 __fastcall(LaunchBioEnrollmentProtocolHandler *__hidden this)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003390`
- `0x1800056d5`
- `0x180008bbc`
- `0x18000aa7c`
- `0x18000e330`
- `0x18001bb2c`
- `0x18001bf68`
- `0x18001bfb0`
- `0x18001c904`
- `0x180032664`
- `0x180050010`

## import_xrefs

- `SHCORE!IUnknown_QueryService` at `0x18001c176`
- `SHCORE!IUnknown_QueryService` at `0x18001c176`
- `combase!__imp_CoAllowSetForegroundWindow` at `0x18001c146`
- `combase!__imp_CoAllowSetForegroundWindow` at `0x18001c146`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001c01e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001c059`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001c01e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001c059`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18001c0c3`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18001c0c3`
- `USER32!GetActiveWindow` at `0x18001c1d9`
- `USER32!GetActiveWindow` at `0x18001c1d9`

## string_xrefs

- `0x18001c04f`: `Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`
- `0x18001c00d`: `OSDATA\Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`
- `0x18001c12a`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\launchbioenrollmentprotocolhandler.cpp`
- `0x18001c1b1`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\launchbioenrollmentprotocolhandler.cpp`
- `0x18001c22c`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\launchbioenrollmentprotocolhandler.cpp`
- `0x18001c0a2`: `Windows.Internal.UI.BioEnrollment.Broker.BioEnrollmentBroker`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall LaunchBioEnrollmentProtocolHandler::Execute(LaunchBioEnrollmentProtocolHandler *this)
{
  RetailDemoUtil *v2; // rcx
  unsigned int FirstSupportedBiometricTypeToDemo; // eax
  unsigned int v4; // edi
  int v5; // ebx
  IUnknown **v6; // rax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // r8
  int v10; // eax
  __int64 v11; // r9
  __int64 v12; // rdx
  struct IUnknownVtbl *lpVtbl; // rax
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rdx
  int pdwType; // [rsp+20h] [rbp-39h]
  IUnknown *pvData; // [rsp+40h] [rbp-19h] BYREF
  DWORD pcbData; // [rsp+48h] [rbp-11h] BYREF
  void *ppvOut; // [rsp+50h] [rbp-9h] BYREF
  int v23[2]; // [rsp+58h] [rbp-1h] BYREF
  IUnknown *pUnk; // [rsp+60h] [rbp+7h] BYREF
  HWND ActiveWindow; // [rsp+68h] [rbp+Fh] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp+17h] BYREF
  __int64 v27; // [rsp+88h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  LODWORD(pvData) = 0;
  pcbData = 4;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"OSDATA\\Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
         L"Enabled",
         0x10010u,
         0,
         &pvData,
         &pcbData) )
  {
    pcbData = 4;
    RegGetValueW(
      HKEY_LOCAL_MACHINE,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
      L"Enabled",
      0x20010010u,
      0,
      &pvData,
      &pcbData);
  }
  if ( !(_DWORD)pvData )
    return 2147500033LL;
  FirstSupportedBiometricTypeToDemo = RetailDemoUtil::GetFirstSupportedBiometricTypeToDemo(v2);
  switch ( FirstSupportedBiometricTypeToDemo )
  {
    case 2u:
      v4 = 0;
LABEL_10:
      pUnk = 0;
      v27 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Internal.UI.BioEnrollment.Broker.BioEnrollmentBroker",
        0x3Du,
        0x3Cu);
      pUnk = 0;
      pvData = 0;
      v5 = RoActivateInstance(v27, &pvData);
      if ( v5 >= 0 )
      {
        if ( !memcmp_0(&GUID_5c449d8a_2923_5867_8434_94f2141ff091, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
        {
          pUnk = pvData;
        }
        else
        {
          v5 = ((__int64 (__fastcall *)(IUnknown *, GUID *, IUnknown **))pvData->lpVtbl->QueryInterface)(
                 pvData,
                 &GUID_5c449d8a_2923_5867_8434_94f2141ff091,
                 &pUnk);
          ((void (__fastcall *)(IUnknown *))pvData->lpVtbl->Release)(pvData);
        }
      }
      if ( v5 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x33,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\launchbioenrollmentprotocolhandler.cpp",
          (const char *)(unsigned int)v5,
          pdwType);
LABEL_30:
        wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(&pUnk);
        return (unsigned int)v5;
      }
      CoAllowSetForegroundWindow(pUnk, 0);
      ActiveWindow = 0;
      ppvOut = 0;
      v6 = (IUnknown **)CWRLObjectWithGITSite::SiteUnk((char *)this + 8, &pvData);
      v7 = (unsigned int)IUnknown_QueryService(
                           *v6,
                           (const GUID *const)&SID_LaunchSourceViewSizePreference,
                           &GUID_e5aa01f7_1fb8_4830_8720_4e6734cbd5f3,
                           &ppvOut) >> 31;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pvData, v8, v9);
      if ( (unsigned __int8)v7 != 1
        && (v10 = (*(__int64 (__fastcall **)(void *, HWND *))(*(_QWORD *)ppvOut + 24LL))(ppvOut, &ActiveWindow),
            v5 = v10,
            v10 < 0) )
      {
        v11 = (unsigned int)v10;
        v12 = 59;
      }
      else
      {
        if ( ActiveWindow || (ActiveWindow = GetActiveWindow()) != 0 )
        {
          *(_QWORD *)v23 = 0;
          lpVtbl = pUnk->lpVtbl;
          *(_QWORD *)v23 = 0;
          v14 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, __int64))lpVtbl[2].QueryInterface)(pUnk, v4, 2);
          v5 = v14;
          if ( v14 >= 0 )
          {
            v14 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Internal::UI::BioEnrollment::DataModel::EnrollmentReturnResult>,Windows::Foundation::IAsyncOperation<enum Windows::Internal::UI::BioEnrollment::DataModel::EnrollmentReturnResult>>(
                    *(int (__fastcall ****)(_QWORD, GUID *, __int64 *))v23,
                    v15,
                    v16);
            v5 = v14;
            if ( v14 >= 0 )
            {
              wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(v23);
              wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(&ppvOut);
              v5 = 0;
              goto LABEL_30;
            }
            v17 = 71;
          }
          else
          {
            v17 = 70;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v17,
            (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\launchbioenrollmentprotocolhandler.cpp",
            (const char *)(unsigned int)v14,
            (int)v23);
          wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(v23);
          goto LABEL_20;
        }
        v5 = -2147467259;
        v11 = 2147500037LL;
        v12 = 67;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\launchbioenrollmentprotocolhandler.cpp",
        (const char *)v11,
        pdwType);
LABEL_20:
      wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(&ppvOut);
      goto LABEL_30;
    case 8u:
      v4 = 1;
      goto LABEL_10;
    case 0x10u:
      v4 = 2;
      goto LABEL_10;
  }
  return 2147500033LL;
}

```

## disassembly

```asm
0x18001bfb0  mov     [rsp-8+arg_8], rbx
0x18001bfb5  mov     [rsp-8+arg_10], rsi
0x18001bfba  push    rbp
0x18001bfbb  push    rdi
0x18001bfbc  push    r14
0x18001bfbe  lea     rbp, [rsp-47h]
0x18001bfc3  sub     rsp, 0A0h
0x18001bfca  mov     rax, cs:__security_cookie
0x18001bfd1  xor     rax, rsp
0x18001bfd4  mov     [rbp+57h+var_20], rax
0x18001bfd8  mov     rsi, rcx
0x18001bfdb  xor     r14d, r14d
0x18001bfde  mov     dword ptr [rbp+57h+var_70], r14d
0x18001bfe2  lea     ebx, [r14+4]
0x18001bfe6  mov     [rbp+57h+var_68], ebx
0x18001bfe9  lea     rax, [rbp+57h+var_68]
0x18001bfed  mov     [rsp+0B0h+pcbData], rax; pcbData
0x18001bff2  lea     rax, [rbp+57h+var_70]
0x18001bff6  mov     [rsp+0B0h+pvData], rax; pvData
0x18001bffb  mov     [rsp+0B0h+pdwType], r14; pdwType
0x18001c000  mov     r9d, 10010h; dwFlags
0x18001c006  lea     r8, ?c_retailDemoValueEnabled@@3QBGB; "Enabled"
0x18001c00d  lea     rdx, SubKey; "OSDATA\\Software\\Microsoft\\Windows\\C"...
0x18001c014  mov     rdi, 0FFFFFFFF80000002h
0x18001c01b  mov     rcx, rdi; hkey
0x18001c01e  call    cs:__imp_RegGetValueW
0x18001c024  test    eax, eax
0x18001c026  jz      short loc_18001C05F
0x18001c028  mov     [rbp+57h+var_68], ebx
0x18001c02b  lea     rax, [rbp+57h+var_68]
0x18001c02f  mov     [rsp+0B0h+pcbData], rax; pcbData
0x18001c034  lea     rax, [rbp+57h+var_70]
0x18001c038  mov     [rsp+0B0h+pvData], rax; pvData
0x18001c03d  mov     [rsp+0B0h+pdwType], r14; int
0x18001c042  mov     r9d, 20010010h; dwFlags
0x18001c048  lea     r8, ?c_retailDemoValueEnabled@@3QBGB; "Enabled"
0x18001c04f  lea     rdx, ?c_retailDemoKeyOobeWrite@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001c056  mov     rcx, rdi; hkey
0x18001c059  call    cs:__imp_RegGetValueW
0x18001c05f  cmp     dword ptr [rbp+57h+var_70], r14d
0x18001c063  jz      loc_18001C287
0x18001c069  call    ?GetFirstSupportedBiometricTypeToDemo@RetailDemoUtil@@YAIXZ; RetailDemoUtil::GetFirstSupportedBiometricTypeToDemo(void)
0x18001c06e  cmp     eax, 2
0x18001c071  jz      short loc_18001C08D
0x18001c073  cmp     eax, 8
0x18001c076  jz      short loc_18001C086
0x18001c078  cmp     eax, 10h
0x18001c07b  jnz     loc_18001C287
0x18001c081  lea     edi, [rax-0Eh]
0x18001c084  jmp     short loc_18001C090
0x18001c086  mov     edi, 1
0x18001c08b  jmp     short loc_18001C090
0x18001c08d  mov     edi, r14d
0x18001c090  mov     [rbp+57h+pUnk], r14
0x18001c094  mov     [rbp+57h+var_28], r14
0x18001c098  mov     r9d, 3Ch ; '<'; unsigned int
0x18001c09e  lea     r8d, [r9+1]; unsigned int
0x18001c0a2  lea     rdx, ?RuntimeClass_Windows_Internal_UI_BioEnrollment_Broker_BioEnrollmentBroker@@3QBGB; "Windows.Internal.UI.BioEnrollment.Broke"...
0x18001c0a9  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18001c0ad  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001c0b2  nop
0x18001c0b3  mov     [rbp+57h+pUnk], r14
0x18001c0b7  mov     [rbp+57h+var_70], r14
0x18001c0bb  lea     rdx, [rbp+57h+var_70]
0x18001c0bf  mov     rcx, [rbp+57h+var_28]
0x18001c0c3  call    cs:__imp_RoActivateInstance
0x18001c0c9  mov     ebx, eax
0x18001c0cb  test    eax, eax
0x18001c0cd  js      short loc_18001C11F
0x18001c0cf  mov     r8d, 10h; Size
0x18001c0d5  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x18001c0dc  lea     rcx, _GUID_5c449d8a_2923_5867_8434_94f2141ff091; Buf1
0x18001c0e3  call    memcmp_0
0x18001c0e8  mov     rcx, [rbp+57h+var_70]
0x18001c0ec  test    eax, eax
0x18001c0ee  jnz     short loc_18001C0F6
0x18001c0f0  mov     [rbp+57h+pUnk], rcx
0x18001c0f4  jmp     short loc_18001C11F
0x18001c0f6  mov     rax, [rcx]
0x18001c0f9  lea     r8, [rbp+57h+pUnk]
0x18001c0fd  lea     rdx, _GUID_5c449d8a_2923_5867_8434_94f2141ff091
0x18001c104  mov     rax, [rax]
0x18001c107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c10c  mov     ebx, eax
0x18001c10e  mov     rcx, [rbp+57h+var_70]
0x18001c112  mov     rax, [rcx]
0x18001c115  mov     rax, [rax+10h]
0x18001c119  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c11e  nop
0x18001c11f  test    ebx, ebx
0x18001c121  jns     short loc_18001C140
0x18001c123  mov     rcx, [rbp+5Fh]; this
0x18001c127  mov     r9d, ebx; char *
0x18001c12a  lea     r8, aPcshellShellRe_19; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18001c131  mov     edx, 33h ; '3'; void *
0x18001c136  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c13b  jmp     loc_18001C27A
0x18001c140  xor     edx, edx; lpvReserved
0x18001c142  mov     rcx, [rbp+57h+pUnk]; pUnk
0x18001c146  call    cs:__imp_CoAllowSetForegroundWindow
0x18001c14c  mov     [rbp+57h+var_48], r14
0x18001c150  mov     [rbp+57h+ppvOut], r14
0x18001c154  lea     rcx, [rsi+8]
0x18001c158  lea     rdx, [rbp+57h+var_70]
0x18001c15c  call    ?SiteUnk@CWRLObjectWithGITSite@@IEAA?AV?$ComPtr@UIUnknown@@@WRL@Microsoft@@XZ; CWRLObjectWithGITSite::SiteUnk(void)
0x18001c161  lea     r9, [rbp+57h+ppvOut]; ppvOut
0x18001c165  lea     r8, _GUID_e5aa01f7_1fb8_4830_8720_4e6734cbd5f3; riid
0x18001c16c  lea     rdx, SID_LaunchSourceViewSizePreference; guidService
0x18001c173  mov     rcx, [rax]; punk
0x18001c176  call    cs:__imp_IUnknown_QueryService
0x18001c17c  mov     ebx, eax
0x18001c17e  shr     ebx, 1Fh
0x18001c181  lea     rcx, [rbp+57h+var_70]
0x18001c185  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c18a  xor     bl, 1
0x18001c18d  jz      short loc_18001C1D0
0x18001c18f  mov     rcx, [rbp+57h+ppvOut]
0x18001c193  mov     rax, [rcx]
0x18001c196  lea     rdx, [rbp+57h+var_48]
0x18001c19a  mov     rax, [rax+18h]
0x18001c19e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c1a3  mov     ebx, eax
0x18001c1a5  test    eax, eax
0x18001c1a7  jns     short loc_18001C1D0
0x18001c1a9  mov     r9d, eax; char *
0x18001c1ac  mov     edx, 3Bh ; ';'; void *
0x18001c1b1  lea     r8, aPcshellShellRe_19; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18001c1b8  mov     rcx, [rbp+5Fh]; this
0x18001c1bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c1c1  nop
0x18001c1c2  lea     rcx, [rbp+57h+ppvOut]
0x18001c1c6  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x18001c1cb  jmp     loc_18001C27A
0x18001c1d0  mov     r9, [rbp+57h+var_48]
0x18001c1d4  test    r9, r9
0x18001c1d7  jnz     short loc_18001C1F8
0x18001c1d9  call    cs:__imp_GetActiveWindow
0x18001c1df  mov     r9, rax
0x18001c1e2  mov     [rbp+57h+var_48], rax
0x18001c1e6  test    rax, rax
0x18001c1e9  jnz     short loc_18001C1F8
0x18001c1eb  mov     ebx, 80004005h
0x18001c1f0  mov     r9d, ebx
0x18001c1f3  lea     edx, [rax+43h]
0x18001c1f6  jmp     short loc_18001C1B1
0x18001c1f8  mov     qword ptr [rbp+57h+var_58], r14
0x18001c1fc  mov     rcx, [rbp+57h+pUnk]
0x18001c200  mov     rax, [rcx]
0x18001c203  mov     qword ptr [rbp+57h+var_58], r14
0x18001c207  lea     r10, [rbp+57h+var_58]
0x18001c20b  mov     [rsp+0B0h+pdwType], r10; int
0x18001c210  mov     r8d, 2
0x18001c216  mov     edx, edi
0x18001c218  mov     rax, [rax+30h]
0x18001c21c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c221  mov     ebx, eax
0x18001c223  test    eax, eax
0x18001c225  jns     short loc_18001C24E
0x18001c227  mov     edx, 46h ; 'F'; void *
0x18001c22c  lea     r8, aPcshellShellRe_19; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18001c233  mov     r9d, eax; char *
0x18001c236  mov     rcx, [rbp+5Fh]; this
0x18001c23a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c23f  nop
0x18001c240  lea     rcx, [rbp+57h+var_58]
0x18001c244  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x18001c249  jmp     loc_18001C1C2
0x18001c24e  mov     rcx, qword ptr [rbp+57h+var_58]
0x18001c252  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@W4EnrollmentReturnResult@DataModel@BioEnrollment@UI@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@W4EnrollmentReturnResult@DataModel@BioEnrollment@UI@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@W4EnrollmentReturnResult@DataModel@BioEnrollment@UI@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::UI::BioEnrollment::DataModel::EnrollmentReturnResult>,Windows::Foundation::IAsyncOperation<Windows::Internal::UI::BioEnrollment::DataModel::EnrollmentReturnResult>>(Windows::Foundation::IAsyncOperation<Windows::Internal::UI::BioEnrollment::DataModel::EnrollmentReturnResult> *,tagCOWAIT_FLAGS,void *)
0x18001c257  mov     ebx, eax
0x18001c259  test    eax, eax
0x18001c25b  jns     short loc_18001C264
0x18001c25d  mov     edx, 47h ; 'G'
0x18001c262  jmp     short loc_18001C22C
0x18001c264  lea     rcx, [rbp+57h+var_58]
0x18001c268  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x18001c26d  nop
0x18001c26e  lea     rcx, [rbp+57h+ppvOut]
0x18001c272  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x18001c277  mov     ebx, r14d
0x18001c27a  lea     rcx, [rbp+57h+pUnk]
0x18001c27e  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x18001c283  mov     eax, ebx
0x18001c285  jmp     short loc_18001C28C
0x18001c287  mov     eax, 80004001h
0x18001c28c  mov     rcx, [rbp+57h+var_20]
0x18001c290  xor     rcx, rsp; StackCookie
0x18001c293  call    __security_check_cookie
0x18001c298  lea     r11, [rsp+0B0h+var_10]
0x18001c2a0  mov     rbx, [r11+28h]
0x18001c2a4  mov     rsi, [r11+30h]
0x18001c2a8  mov     rsp, r11
0x18001c2ab  pop     r14
0x18001c2ad  pop     rdi
0x18001c2ae  pop     rbp
0x18001c2af  retn
```
