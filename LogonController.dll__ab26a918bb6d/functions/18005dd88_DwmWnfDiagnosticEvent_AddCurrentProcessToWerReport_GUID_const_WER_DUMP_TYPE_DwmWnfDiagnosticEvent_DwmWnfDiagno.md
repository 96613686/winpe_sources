# DwmWnfDiagnosticEvent::AddCurrentProcessToWerReport(_GUID const &,_WER_DUMP_TYPE,DwmWnfDiagnosticEvent::DwmWnfDiagnosticEventDumpMetadata const &)

- ea: `0x18005dd88`
- end: `0x18005e026`
- name: `?AddCurrentProcessToWerReport@DwmWnfDiagnosticEvent@@YAJAEBU_GUID@@W4_WER_DUMP_TYPE@@AEBUDwmWnfDiagnosticEventDumpMetadata@1@@Z`
- size: `670`
- prototype: `__int64 __fastcall(IID *rclsid, const struct _GUID *, enum _WER_DUMP_TYPE, const struct DwmWnfDiagnosticEvent::DwmWnfDiagnosticEventDumpMetadata *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180084fe0`

## callees

- `0x180008094`
- `0x180011050`
- `0x1800325c0`
- `0x18005d488`
- `0x18005dd88`
- `0x18005e02c`
- `0x18006c000`
- `0x18006cad0`
- `0x180084e88`

## import_xrefs

- `KERNEL32!WerRegisterCustomMetadata` at `0x18005df26`
- `KERNEL32!WerRegisterCustomMetadata` at `0x18005df26`
- `KERNEL32!WerUnregisterCustomMetadata` at `0x18005df97`
- `KERNEL32!WerUnregisterCustomMetadata` at `0x18005dfc8`
- `KERNEL32!WerUnregisterCustomMetadata` at `0x18005df97`
- `KERNEL32!WerUnregisterCustomMetadata` at `0x18005dfc8`
- `KERNEL32!GetCurrentProcess` at `0x18005de5d`
- `KERNEL32!GetCurrentProcess` at `0x18005de5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005df0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005dff7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005df0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005dff7`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18005ded7`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18005ded7`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportAddDump` at `0x18005de8e`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportAddDump` at `0x18005de8e`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportCreate` at `0x18005de4a`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportCreate` at `0x18005de4a`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSubmit` at `0x18005df6d`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSubmit` at `0x18005df6d`

## pseudocode

```c
__int64 __fastcall DwmWnfDiagnosticEvent::AddCurrentProcessToWerReport(
        IID *rclsid,
        const struct _GUID *a2,
        __int64 a3,
        const struct DwmWnfDiagnosticEvent::DwmWnfDiagnosticEventDumpMetadata *a4)
{
  int v6; // ebx
  __int64 v7; // rdx
  HRESULT v8; // eax
  __int64 v9; // rdx
  HANDLE CurrentProcess; // rax
  HRESULT v11; // eax
  __int64 v12; // rdx
  HRESULT v13; // eax
  HRESULT v14; // eax
  HRESULT v15; // eax
  int pExceptionParam; // [rsp+20h] [rbp-E0h]
  int pExceptionParama; // [rsp+20h] [rbp-E0h]
  LPOLESTR lpsz; // [rsp+40h] [rbp-C0h] BYREF
  HREPORT phReportHandle; // [rsp+48h] [rbp-B8h] BYREF
  _WER_SUBMIT_RESULT pSubmitResult; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v22[3]; // [rsp+58h] [rbp-A8h] BYREF
  _WER_REPORT_INFORMATION pReportInformation; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+948h] [rbp+848h]

  memset_0(&pReportInformation, 0, sizeof(pReportInformation));
  pReportInformation.dwSize = 2208;
  v6 = StringCchCopyW(pReportInformation.wzFriendlyEventName, 0x80u, L"Black Screen - User Reported");
  if ( v6 >= 0 )
  {
    v6 = StringCchCopyW(
           pReportInformation.wzDescription,
           0x200u,
           L"The user has invoked the Black Screen Diagnostics Tool to generate this report");
    if ( v6 < 0 )
    {
      v7 = 105;
      goto LABEL_3;
    }
    phReportHandle = 0;
    v8 = WerReportCreate(L"WindowsBlackScreenDiagnosticsV1", WerReportCritical, &pReportInformation, &phReportHandle);
    v6 = v8;
    if ( v8 < 0 )
    {
      v9 = 109;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"onecoreuap\\internal\\windows\\inc\\DwmWnfDumpRequestListener.h",
        (const char *)(unsigned int)v8,
        pExceptionParam);
LABEL_26:
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long WerReportCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long WerReportCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phReportHandle);
      return (unsigned int)v6;
    }
    CurrentProcess = GetCurrentProcess();
    v8 = WerReportAddDump(phReportHandle, CurrentProcess, 0, WerDumpTypeHeapDump, 0, 0, 0);
    v6 = v8;
    if ( v8 < 0 )
    {
      v9 = 113;
      goto LABEL_10;
    }
    lpsz = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &lpsz,
      0);
    v11 = StringFromCLSID(rclsid, &lpsz);
    v6 = v11;
    if ( v11 >= 0 )
    {
      v11 = WerRegisterCustomMetadata(L"BlackScreenInstanceGuid", lpsz);
      v6 = v11;
      if ( v11 >= 0 )
      {
        v22[1] = a3;
        v22[0] = &phReportHandle;
        _lambda_868f43637e8409a46b7fdcb03681968d_::operator()(v22);
        pSubmitResult = WerCustomAction|WerReportFailed;
        v13 = WerReportSubmit(phReportHandle, WerConsentNotAsked, 4u, &pSubmitResult);
        v6 = v13;
        if ( v13 >= 0 )
        {
          v15 = WerUnregisterCustomMetadata(L"BlackScreenInstanceGuid");
          if ( v15 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x7C,
              (unsigned int)"onecoreuap\\internal\\windows\\inc\\DwmWnfDumpRequestListener.h",
              (const char *)(unsigned int)v15,
              pExceptionParam);
          if ( lpsz )
            CoTaskMemFree(lpsz);
          v6 = 0;
          goto LABEL_26;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x9D,
          (unsigned int)"onecoreuap\\internal\\windows\\inc\\DwmWnfDumpRequestListener.h",
          (const char *)(unsigned int)v13,
          pExceptionParam);
        v14 = WerUnregisterCustomMetadata(L"BlackScreenInstanceGuid");
        if ( v14 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x7C,
            (unsigned int)"onecoreuap\\internal\\windows\\inc\\DwmWnfDumpRequestListener.h",
            (const char *)(unsigned int)v14,
            pExceptionParama);
        goto LABEL_14;
      }
      v12 = 119;
    }
    else
    {
      v12 = 117;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\internal\\windows\\inc\\DwmWnfDumpRequestListener.h",
      (const char *)(unsigned int)v11,
      pExceptionParam);
LABEL_14:
    if ( lpsz )
      CoTaskMemFree(lpsz);
    goto LABEL_26;
  }
  v7 = 100;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"onecoreuap\\internal\\windows\\inc\\DwmWnfDumpRequestListener.h",
    (const char *)(unsigned int)v6,
    pExceptionParam);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18005dd88  push    rbp
0x18005dd8a  push    rbx
0x18005dd8b  push    rsi
0x18005dd8c  push    rdi
0x18005dd8d  lea     rbp, [rsp-828h]
0x18005dd95  sub     rsp, 928h
0x18005dd9c  mov     rax, cs:__security_cookie
0x18005dda3  xor     rax, rsp
0x18005dda6  mov     [rbp+840h+var_30], rax
0x18005ddad  mov     rsi, r8
0x18005ddb0  mov     rdi, rcx
0x18005ddb3  mov     ebx, 8A0h
0x18005ddb8  lea     rcx, [rsp+940h+pReportInformation]; void *
0x18005ddbd  mov     r8d, ebx; Size
0x18005ddc0  xor     edx, edx; Val
0x18005ddc2  call    memset_0
0x18005ddc7  lea     r8, aBlackScreenUse; "Black Screen - User Reported"
0x18005ddce  mov     [rsp+940h+pReportInformation.dwSize], ebx
0x18005ddd2  mov     edx, 80h; unsigned __int64
0x18005ddd7  lea     rcx, [rbp+840h+pReportInformation.wzFriendlyEventName]; unsigned __int16 *
0x18005dddb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005dde0  mov     ebx, eax
0x18005dde2  test    eax, eax
0x18005dde4  jns     short loc_18005DE06
0x18005dde6  mov     edx, 64h ; 'd'; void *
0x18005ddeb  mov     rcx, [rbp+848h]; this
0x18005ddf2  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\windows\\inc\\Dwm"...
0x18005ddf9  mov     r9d, ebx; char *
0x18005ddfc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005de01  jmp     loc_18005E009
0x18005de06  lea     r8, aTheUserHasInvo; "The user has invoked the Black Screen D"...
0x18005de0d  mov     edx, 200h; unsigned __int64
0x18005de12  lea     rcx, [rbp+840h+pReportInformation.wzDescription]; unsigned __int16 *
0x18005de19  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005de1e  mov     ebx, eax
0x18005de20  test    eax, eax
0x18005de22  jns     short loc_18005DE2B
0x18005de24  mov     edx, 69h ; 'i'
0x18005de29  jmp     short loc_18005DDEB
0x18005de2b  lea     r9, [rsp+940h+phReportHandle]; phReportHandle
0x18005de30  mov     [rsp+940h+phReportHandle], 0
0x18005de39  lea     r8, [rsp+940h+pReportInformation]; pReportInformation
0x18005de3e  mov     edx, 1; repType
0x18005de43  lea     rcx, pwzEventType; "WindowsBlackScreenDiagnosticsV1"
0x18005de4a  call    cs:__imp_WerReportCreate
0x18005de50  mov     ebx, eax
0x18005de52  test    eax, eax
0x18005de54  jns     short loc_18005DE5D
0x18005de56  mov     edx, 6Dh ; 'm'
0x18005de5b  jmp     short loc_18005DE9F
0x18005de5d  call    cs:__imp_GetCurrentProcess
0x18005de63  mov     rcx, [rsp+940h+phReportHandle]; hReportHandle
0x18005de68  mov     r9d, 3; dumpType
0x18005de6e  mov     [rsp+940h+dwFlags], 0; dwFlags
0x18005de76  mov     rdx, rax; hProcess
0x18005de79  mov     [rsp+940h+pDumpCustomOptions], 0; pDumpCustomOptions
0x18005de82  xor     r8d, r8d; hThread
0x18005de85  mov     [rsp+940h+pExceptionParam], 0; int
0x18005de8e  call    cs:__imp_WerReportAddDump
0x18005de94  mov     ebx, eax
0x18005de96  test    eax, eax
0x18005de98  jns     short loc_18005DEBA
0x18005de9a  mov     edx, 71h ; 'q'; void *
0x18005de9f  mov     rcx, [rbp+848h]; this
0x18005dea6  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\windows\\inc\\Dwm"...
0x18005dead  mov     r9d, eax; char *
0x18005deb0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005deb5  jmp     loc_18005DFFF
0x18005deba  xor     edx, edx
0x18005debc  mov     [rsp+940h+lpsz], 0
0x18005dec5  lea     rcx, [rsp+940h+lpsz]
0x18005deca  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18005decf  lea     rdx, [rsp+940h+lpsz]; lplpsz
0x18005ded4  mov     rcx, rdi; rclsid
0x18005ded7  call    cs:__imp_StringFromCLSID
0x18005dedd  mov     ebx, eax
0x18005dedf  test    eax, eax
0x18005dee1  jns     short loc_18005DF17
0x18005dee3  mov     edx, 75h ; 'u'; void *
0x18005dee8  mov     rcx, [rbp+848h]; this
0x18005deef  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\windows\\inc\\Dwm"...
0x18005def6  mov     r9d, eax; char *
0x18005def9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005defe  mov     rcx, [rsp+940h+lpsz]; pv
0x18005df03  test    rcx, rcx
0x18005df06  jz      loc_18005DFFF
0x18005df0c  call    cs:__imp_CoTaskMemFree
0x18005df12  jmp     loc_18005DFFF
0x18005df17  mov     rdx, [rsp+940h+lpsz]; value
0x18005df1c  lea     rdi, key; "BlackScreenInstanceGuid"
0x18005df23  mov     rcx, rdi; key
0x18005df26  call    cs:__imp_WerRegisterCustomMetadata
0x18005df2c  mov     ebx, eax
0x18005df2e  test    eax, eax
0x18005df30  jns     short loc_18005DF39
0x18005df32  mov     edx, 77h ; 'w'
0x18005df37  jmp     short loc_18005DEE8
0x18005df39  lea     rax, [rsp+940h+phReportHandle]
0x18005df3e  mov     [rsp+940h+var_8E0], rsi
0x18005df43  lea     rcx, [rsp+940h+var_8E8]
0x18005df48  mov     [rsp+940h+var_8E8], rax
0x18005df4d  call    ??R_lambda_868f43637e8409a46b7fdcb03681968d_@@QEBAJXZ; _lambda_868f43637e8409a46b7fdcb03681968d_::operator()(void)
0x18005df52  mov     rcx, [rsp+940h+phReportHandle]; hReportHandle
0x18005df57  lea     r9, [rsp+940h+pSubmitResult]; pSubmitResult
0x18005df5c  mov     edx, 1; consent
0x18005df61  mov     [rsp+940h+pSubmitResult], 0Dh
0x18005df69  lea     r8d, [rdx+3]; dwFlags
0x18005df6d  call    cs:__imp_WerReportSubmit
0x18005df73  mov     ebx, eax
0x18005df75  test    eax, eax
0x18005df77  jns     short loc_18005DFC5
0x18005df79  mov     rcx, [rbp+848h]; this
0x18005df80  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\windows\\inc\\Dwm"...
0x18005df87  mov     r9d, eax; char *
0x18005df8a  mov     edx, 9Dh; void *
0x18005df8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005df94  mov     rcx, rdi; key
0x18005df97  call    cs:__imp_WerUnregisterCustomMetadata
0x18005df9d  test    eax, eax
0x18005df9f  jns     loc_18005DEFE
0x18005dfa5  mov     rcx, [rbp+848h]; this
0x18005dfac  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\windows\\inc\\Dwm"...
0x18005dfb3  mov     r9d, eax; char *
0x18005dfb6  mov     edx, 7Ch ; '|'; void *
0x18005dfbb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005dfc0  jmp     loc_18005DEFE
0x18005dfc5  mov     rcx, rdi; key
0x18005dfc8  call    cs:__imp_WerUnregisterCustomMetadata
0x18005dfce  test    eax, eax
0x18005dfd0  jns     short loc_18005DFED
0x18005dfd2  mov     rcx, [rbp+848h]; this
0x18005dfd9  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\windows\\inc\\Dwm"...
0x18005dfe0  mov     r9d, eax; char *
0x18005dfe3  mov     edx, 7Ch ; '|'; void *
0x18005dfe8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005dfed  mov     rcx, [rsp+940h+lpsz]; pv
0x18005dff2  test    rcx, rcx
0x18005dff5  jz      short loc_18005DFFD
0x18005dff7  call    cs:__imp_CoTaskMemFree
0x18005dffd  xor     ebx, ebx
0x18005dfff  lea     rcx, [rsp+940h+phReportHandle]
0x18005e004  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?WerReportCloseHandle@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&WerReportCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&WerReportCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18005e009  mov     eax, ebx
0x18005e00b  mov     rcx, [rbp+840h+var_30]
0x18005e012  xor     rcx, rsp; StackCookie
0x18005e015  call    __security_check_cookie
0x18005e01a  add     rsp, 928h
0x18005e021  pop     rdi
0x18005e022  pop     rsi
0x18005e023  pop     rbx
0x18005e024  pop     rbp
0x18005e025  retn
```
