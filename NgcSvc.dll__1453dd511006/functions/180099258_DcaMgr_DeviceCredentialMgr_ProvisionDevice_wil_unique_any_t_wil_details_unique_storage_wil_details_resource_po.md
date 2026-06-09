# DcaMgr::DeviceCredentialMgr::ProvisionDevice(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,ushort const *)

- ea: `0x180099258`
- end: `0x180099693`
- name: `?ProvisionDevice@DeviceCredentialMgr@DcaMgr@@QEAAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z`
- size: `1083`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, HKEY *, const WCHAR *)`
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18005ab00`

## callees

- `0x18000782c`
- `0x180007964`
- `0x1800281e0`
- `0x180028d18`
- `0x180031184`
- `0x180032c20`
- `0x180038764`
- `0x180047228`
- `0x180048304`
- `0x180053144`
- `0x180054bd8`
- `0x1800555d8`
- `0x1800596ec`
- `0x180097c6c`
- `0x180097cb4`
- `0x180097cd8`
- `0x180097cfc`
- `0x180098914`
- `0x180099258`
- `0x18009abe4`
- `0x18009b38c`
- `0x1800a14c0`
- `0x1800a6340`
- `0x1800a6b34`
- `0x1800a73c4`
- `0x1800a7400`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800992c4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800992c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800995e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800995e4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009938f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009938f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800994ed`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800994ed`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180099496`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180099496`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180099532`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180099532`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800993ce`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800993ce`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180099307`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180099307`
- `USERENV!DeleteProfileW` at `0x1800995da`
- `USERENV!DeleteProfileW` at `0x1800995da`

## string_xrefs

- `0x180099297`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x180099320`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x1800993ab`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x1800993e1`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x18009943a`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x180099543`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x18009956c`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x1800995af`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`

## pseudocode

```c
__int64 __fastcall DcaMgr::DeviceCredentialMgr::ProvisionDevice(RTL_SRWLOCK *this, HKEY *a2, const WCHAR *a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  char v9; // di
  BOOL v10; // ebx
  const char *v11; // r9
  unsigned int v12; // ebx
  int v13; // eax
  unsigned __int64 v14; // r9
  __int64 v15; // rdx
  int updated; // eax
  DcaMgr::DeviceCredentialMgr *v17; // rcx
  unsigned int v18; // eax
  wil::details::in1diag3 *v19; // rcx
  unsigned int v20; // eax
  unsigned int v21; // ebx
  int LocalAccountSidFromName; // eax
  signed int LastError; // eax
  const struct _tlgProvider_t *v24; // rax
  int v25; // r10d
  int dwOptions; // [rsp+20h] [rbp-99h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-99h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-99h]
  int dwOptionsc; // [rsp+20h] [rbp-99h]
  const char *samDesired; // [rsp+28h] [rbp-91h]
  char v31; // [rsp+50h] [rbp-69h] BYREF
  int pvData; // [rsp+54h] [rbp-65h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-61h] BYREF
  struct PackageUtil *v34; // [rsp+60h] [rbp-59h] BYREF
  HKEY *p_hKey; // [rsp+68h] [rbp-51h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+70h] [rbp-49h] BYREF
  char v37; // [rsp+78h] [rbp-41h]
  DWORD pcbData; // [rsp+80h] [rbp-39h] BYREF
  LPCWSTR lpSidString; // [rsp+88h] [rbp-31h] BYREF
  void *v40; // [rsp+90h] [rbp-29h] BYREF
  void *p_lpSidString; // [rsp+98h] [rbp-21h] BYREF
  struct PackageUtil *v42; // [rsp+A0h] [rbp-19h] BYREF
  char v43; // [rsp+A8h] [rbp-11h]
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+B0h] [rbp-9h] BYREF
  RTL_SRWLOCK *v45; // [rsp+C8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]
  unsigned int v47; // [rsp+138h] [rbp+7Fh] BYREF

  LOBYTE(v47) = 0;
  v6 = IsFirstlogonAllowed(&v47);
  v7 = v6;
  if ( v6 >= 0 )
  {
    if ( !(_BYTE)v47 )
      return 0;
    AcquireSRWLockExclusive(this + 16);
    v45 = this + 16;
    *(_QWORD *)&SecurityAttributes.nLength = 24;
    SecurityAttributes.lpSecurityDescriptor = 0;
    *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
    v40 = 0;
    p_hKey = (HKEY *)&v40;
    SecurityDescriptor = 0;
    v9 = 1;
    v37 = 1;
    v10 = ConvertStringSecurityDescriptorToSecurityDescriptorW(
            L"D:P(A;CI;KR;;;AU)(A;CI;KA;;;SY)",
            1u,
            &SecurityDescriptor,
            0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&p_hKey);
    if ( v10 )
    {
      SecurityAttributes.lpSecurityDescriptor = v40;
      hKey = 0;
      p_hKey = &hKey;
      SecurityDescriptor = 0;
      v37 = 1;
      v12 = RegCreateKeyExW(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\SecondaryAuthFactor\\Applications",
              0,
              0,
              0,
              0xF003Fu,
              &SecurityAttributes,
              (PHKEY)&SecurityDescriptor,
              0);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
      if ( v12 )
      {
        v7 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x943,
               (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
               (const char *)v12,
               dwOptionsa);
      }
      else
      {
        v13 = RoInitialize(1);
        v7 = v13;
        if ( v13 >= 0 )
        {
          v31 = 1;
          p_hKey = (HKEY *)&v31;
          LOWORD(SecurityDescriptor) = 256;
          v34 = 0;
          p_lpSidString = &v34;
          v42 = 0;
          v43 = 1;
          v7 = PackageUtil::CreateInstance(&v42);
          wil::details::out_param_t<wistd::unique_ptr<PackageUtil,wistd::default_delete<PackageUtil>>>::~out_param_t<wistd::unique_ptr<PackageUtil,wistd::default_delete<PackageUtil>>>(&p_lpSidString);
          if ( (v7 & 0x80000000) == 0 )
          {
            updated = DcaMgr::DeviceCredentialMgr::UpdatePackageData((const WCHAR *)this, v34, hKey, *a2, a3, 1);
            v7 = updated;
            if ( updated >= 0 )
            {
              RegFlushKey(hKey);
              DcaMgr::DeviceCredentialMgr::EnableDeploymentTask(v17);
              wistd::unique_ptr<PackageUtil,wistd::default_delete<PackageUtil>>::reset(&v34, 0);
              wil::details::ScopeExitFnGuard__lambda_d8173cb92363fa7c66c11fc7ee07aa30___::operator()(&p_hKey);
              pvData = 0;
              pcbData = 4;
              if ( RegGetValueW(
                     HKEY_LOCAL_MACHINE,
                     L"Software\\Microsoft\\Windows\\CurrentVersion\\SecondaryAuthFactor",
                     L"AccountMigration",
                     0x10u,
                     0,
                     &pvData,
                     &pcbData) )
              {
                pvData = 0;
              }
              if ( (unsigned __int8)IsLocalAccountEnabled() || !pvData )
              {
                pvData = 1;
                v18 = RegSetKeyValueW(
                        HKEY_LOCAL_MACHINE,
                        L"Software\\Microsoft\\Windows\\CurrentVersion\\SecondaryAuthFactor",
                        L"AccountMigration",
                        4u,
                        &pvData,
                        4u);
                v19 = retaddr;
                if ( v18 )
                  wil::details::in1diag3::_Log_Win32(
                    retaddr,
                    (void *)0x981,
                    (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
                    (const char *)v18,
                    dwOptionsb);
                v20 = DisableLocalAccount(v19);
                wil::details::in1diag3::Log_IfFailedMsg(
                  retaddr,
                  (void *)0x985,
                  (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
                  (const char *)v20,
                  (int)"DisableDefaultAccount",
                  samDesired);
                v21 = 0;
                lpSidString = 0;
                p_lpSidString = &lpSidString;
                v42 = 0;
                v43 = 1;
                LocalAccountSidFromName = GetLocalAccountSidFromName(L"DefaultAccount");
                if ( LocalAccountSidFromName < 0 )
                {
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0x98B,
                    (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
                    (const char *)(unsigned int)LocalAccountSidFromName,
                    dwOptionsc);
                  v9 = 0;
                }
                wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_lpSidString);
                if ( v9 )
                {
                  if ( !DeleteProfileW(lpSidString, 0, 0) )
                  {
                    LastError = GetLastError();
                    v21 = LastError;
                    if ( LastError > 0 )
                      v21 = (unsigned __int16)LastError | 0x80070000;
                  }
                }
                v24 = DevCredSvcTraceLoggingProvider::Provider();
                if ( *(_DWORD *)v24 > 4u )
                {
                  if ( (unsigned __int8)tlgKeywordOn(v24, 0x400000000000LL) )
                  {
                    v47 = v21;
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                      v25,
                      (unsigned int)&byte_18010864F,
                      0,
                      0,
                      (__int64)&v47);
                  }
                }
                wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpSidString);
              }
              wistd::unique_ptr<PackageUtil,wistd::default_delete<PackageUtil>>::reset(&v34, 0);
              wil::details::ScopeExitFnGuard__lambda_d8173cb92363fa7c66c11fc7ee07aa30___::operator()(&p_hKey);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
              v7 = 0;
              goto LABEL_34;
            }
            v14 = (unsigned int)updated;
            v15 = 2393;
          }
          else
          {
            v14 = v7;
            v15 = 2387;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v15,
            (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
            (const char *)v14,
            dwOptionsa);
          wistd::unique_ptr<PackageUtil,wistd::default_delete<PackageUtil>>::reset(&v34, 0);
          wil::details::ScopeExitFnGuard__lambda_d8173cb92363fa7c66c11fc7ee07aa30___::operator()(&p_hKey);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x945,
            (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
            (const char *)(unsigned int)v13,
            dwOptionsa);
        }
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    }
    else
    {
      v7 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x936,
             (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
             v11);
    }
LABEL_34:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v40);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v45);
    return v7;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x92B,
    (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
    (const char *)(unsigned int)v6,
    dwOptions);
  return v7;
}

```

## disassembly

```asm
0x180099258  push    rbp
0x18009925a  push    rbx
0x18009925b  push    rsi
0x18009925c  push    rdi
0x18009925d  push    r12
0x18009925f  push    r13
0x180099261  push    r14
0x180099263  push    r15
0x180099265  lea     rbp, [rsp-1Fh]
0x18009926a  sub     rsp, 0D8h
0x180099271  mov     r14, r8
0x180099274  mov     r15, rdx
0x180099277  mov     rsi, rcx
0x18009927a  xor     r12d, r12d
0x18009927d  mov     byte ptr [rbp+57h+arg_18], r12b
0x180099281  lea     rcx, [rbp+57h+arg_18]
0x180099285  call    IsFirstlogonAllowed
0x18009928a  mov     ebx, eax
0x18009928c  test    eax, eax
0x18009928e  jns     short loc_1800992AD
0x180099290  mov     rcx, [rbp+5Fh]; this
0x180099294  mov     r9d, eax; char *
0x180099297  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x18009929e  mov     edx, 92Bh; void *
0x1800992a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800992a8  jmp     loc_18009967D
0x1800992ad  cmp     byte ptr [rbp+57h+arg_18], r12b
0x1800992b1  jnz     short loc_1800992BA
0x1800992b3  xor     eax, eax
0x1800992b5  jmp     loc_18009967F
0x1800992ba  lea     rbx, [rsi+80h]
0x1800992c1  mov     rcx, rbx; SRWLock
0x1800992c4  call    cs:__imp_AcquireSRWLockExclusive
0x1800992ca  mov     [rbp+57h+var_48], rbx
0x1800992ce  mov     qword ptr [rbp+57h+SecurityAttributes.nLength], 18h
0x1800992d6  mov     [rbp+57h+SecurityAttributes.lpSecurityDescriptor], r12
0x1800992da  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], r12
0x1800992de  mov     [rbp+57h+var_80], r12
0x1800992e2  lea     rax, [rbp+57h+var_80]
0x1800992e6  mov     [rbp+57h+var_A8], rax
0x1800992ea  mov     [rbp+57h+SecurityDescriptor], r12
0x1800992ee  mov     edi, 1
0x1800992f3  mov     [rbp+57h+var_98], dil
0x1800992f7  xor     r9d, r9d; SecurityDescriptorSize
0x1800992fa  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1800992fe  mov     edx, edi; StringSDRevision
0x180099300  lea     rcx, aDPACiKrAuACiKa; "D:P(A;CI;KR;;;AU)(A;CI;KA;;;SY)"
0x180099307  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18009930d  mov     ebx, eax
0x18009930f  lea     rcx, [rbp+57h+var_A8]
0x180099313  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x180099318  test    ebx, ebx
0x18009931a  jnz     short loc_180099338
0x18009931c  mov     rcx, [rbp+5Fh]; this
0x180099320  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x180099327  mov     edx, 936h; void *
0x18009932c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180099331  mov     ebx, eax
0x180099333  jmp     loc_18009966A
0x180099338  mov     rax, [rbp+57h+var_80]
0x18009933c  mov     [rbp+57h+SecurityAttributes.lpSecurityDescriptor], rax
0x180099340  mov     [rbp+57h+hKey], r12
0x180099344  lea     rax, [rbp+57h+hKey]
0x180099348  mov     [rbp+57h+var_A8], rax
0x18009934c  mov     [rbp+57h+SecurityDescriptor], r12
0x180099350  mov     [rbp+57h+var_98], dil
0x180099354  mov     [rsp+110h+lpdwDisposition], r12; lpdwDisposition
0x180099359  lea     rax, [rbp+57h+SecurityDescriptor]
0x18009935d  mov     [rsp+110h+phkResult], rax; phkResult
0x180099362  lea     rax, [rbp+57h+SecurityAttributes]
0x180099366  mov     [rsp+110h+lpSecurityAttributes], rax; lpSecurityAttributes
0x18009936b  mov     [rsp+110h+samDesired], 0F003Fh; samDesired
0x180099373  mov     [rsp+110h+dwOptions], r12d; int
0x180099378  xor     r9d, r9d; lpClass
0x18009937b  xor     r8d, r8d; Reserved
0x18009937e  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180099385  mov     r13, 0FFFFFFFF80000002h
0x18009938c  mov     rcx, r13; hKey
0x18009938f  call    cs:__imp_RegCreateKeyExW
0x180099395  mov     ebx, eax
0x180099397  lea     rcx, [rbp+57h+var_A8]
0x18009939b  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800993a0  test    ebx, ebx
0x1800993a2  jz      short loc_1800993CC
0x1800993a4  mov     rcx, [rbp+5Fh]; this
0x1800993a8  mov     r9d, ebx; char *
0x1800993ab  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x1800993b2  mov     edx, 943h; void *
0x1800993b7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800993bc  mov     ebx, eax
0x1800993be  lea     rcx, [rbp+57h+hKey]
0x1800993c2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800993c7  jmp     loc_18009966A
0x1800993cc  mov     ecx, edi
0x1800993ce  call    cs:__imp_RoInitialize
0x1800993d4  mov     ebx, eax
0x1800993d6  test    eax, eax
0x1800993d8  jns     short loc_1800993F4
0x1800993da  mov     rcx, [rbp+5Fh]; this
0x1800993de  mov     r9d, eax; char *
0x1800993e1  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x1800993e8  mov     edx, 945h; void *
0x1800993ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800993f2  jmp     short loc_1800993BE
0x1800993f4  mov     [rbp+57h+var_C0], dil
0x1800993f8  lea     rax, [rbp+57h+var_C0]
0x1800993fc  mov     [rbp+57h+var_A8], rax
0x180099400  mov     word ptr [rbp+57h+SecurityDescriptor], 100h
0x180099406  mov     [rbp+57h+var_B0], r12
0x18009940a  lea     rax, [rbp+57h+var_B0]
0x18009940e  mov     [rbp+57h+var_78], rax
0x180099412  mov     [rbp+57h+var_70], r12
0x180099416  mov     [rbp+57h+var_68], dil
0x18009941a  lea     rcx, [rbp+57h+var_70]; struct PackageUtil **
0x18009941e  call    ?CreateInstance@PackageUtil@@SAJPEAPEAV1@@Z; PackageUtil::CreateInstance(PackageUtil * *)
0x180099423  mov     ebx, eax
0x180099425  lea     rcx, [rbp+57h+var_78]
0x180099429  call    ??1?$out_param_t@V?$unique_ptr@VPackageUtil@@U?$default_delete@VPackageUtil@@@wistd@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<PackageUtil,wistd::default_delete<PackageUtil>>>::~out_param_t<wistd::unique_ptr<PackageUtil,wistd::default_delete<PackageUtil>>>(void)
0x18009942e  test    ebx, ebx
0x180099430  jns     short loc_180099465
0x180099432  mov     r9d, ebx; char *
0x180099435  mov     edx, 953h; void *
0x18009943a  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x180099441  mov     rcx, [rbp+5Fh]; this
0x180099445  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009944a  nop
0x18009944b  xor     edx, edx
0x18009944d  lea     rcx, [rbp+57h+var_B0]
0x180099451  call    ?reset@?$unique_ptr@VPackageUtil@@U?$default_delete@VPackageUtil@@@wistd@@@wistd@@QEAAXPEAVPackageUtil@@@Z; wistd::unique_ptr<PackageUtil,wistd::default_delete<PackageUtil>>::reset(PackageUtil *)
0x180099456  nop
0x180099457  lea     rcx, [rbp+57h+var_A8]
0x18009945b  call    wil__details__ScopeExitFnGuard__lambda_d8173cb92363fa7c66c11fc7ee07aa30_____operator__
0x180099460  jmp     loc_1800993BE
0x180099465  mov     byte ptr [rsp+110h+samDesired], dil; bool
0x18009946a  mov     qword ptr [rsp+110h+dwOptions], r14; unsigned __int16 *
0x18009946f  mov     r9, [r15]; HKEY
0x180099472  mov     r8, [rbp+57h+hKey]; HKEY
0x180099476  mov     rdx, [rbp+57h+var_B0]; struct PackageUtil *
0x18009947a  mov     rcx, rsi; this
0x18009947d  call    ?UpdatePackageData@DeviceCredentialMgr@DcaMgr@@AEAAJPEAVPackageUtil@@PEAUHKEY__@@1PEBG_N@Z; DcaMgr::DeviceCredentialMgr::UpdatePackageData(PackageUtil *,HKEY__ *,HKEY__ *,ushort const *,bool)
0x180099482  mov     ebx, eax
0x180099484  test    eax, eax
0x180099486  jns     short loc_180099492
0x180099488  mov     r9d, eax
0x18009948b  mov     edx, 959h
0x180099490  jmp     short loc_18009943A
0x180099492  mov     rcx, [rbp+57h+hKey]; hKey
0x180099496  call    cs:__imp_RegFlushKey
0x18009949c  call    ?EnableDeploymentTask@DeviceCredentialMgr@DcaMgr@@AEAAJXZ; DcaMgr::DeviceCredentialMgr::EnableDeploymentTask(void)
0x1800994a1  xor     edx, edx
0x1800994a3  lea     rcx, [rbp+57h+var_B0]
0x1800994a7  call    ?reset@?$unique_ptr@VPackageUtil@@U?$default_delete@VPackageUtil@@@wistd@@@wistd@@QEAAXPEAVPackageUtil@@@Z; wistd::unique_ptr<PackageUtil,wistd::default_delete<PackageUtil>>::reset(PackageUtil *)
0x1800994ac  lea     rcx, [rbp+57h+var_A8]
0x1800994b0  call    wil__details__ScopeExitFnGuard__lambda_d8173cb92363fa7c66c11fc7ee07aa30_____operator__
0x1800994b5  mov     [rbp+57h+pvData], r12d
0x1800994b9  mov     esi, 4
0x1800994be  mov     [rbp+57h+pcbData], esi
0x1800994c1  lea     rax, [rbp+57h+pcbData]
0x1800994c5  mov     [rsp+110h+lpSecurityAttributes], rax; pcbData
0x1800994ca  lea     rax, [rbp+57h+pvData]
0x1800994ce  mov     qword ptr [rsp+110h+samDesired], rax; pvData
0x1800994d3  mov     qword ptr [rsp+110h+dwOptions], r12; pdwType
0x1800994d8  lea     r9d, [rsi+0Ch]; dwFlags
0x1800994dc  lea     r8, aAccountmigrati; "AccountMigration"
0x1800994e3  lea     rdx, aSoftwareMicros_14; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800994ea  mov     rcx, r13; hkey
0x1800994ed  call    cs:__imp_RegGetValueW
0x1800994f3  test    eax, eax
0x1800994f5  jz      short loc_1800994FB
0x1800994f7  mov     [rbp+57h+pvData], r12d
0x1800994fb  call    IsLocalAccountEnabled
0x180099500  test    al, al
0x180099502  jnz     short loc_18009950E
0x180099504  cmp     [rbp+57h+pvData], r12d
0x180099508  jnz     loc_180099648
0x18009950e  mov     [rbp+57h+pvData], edi
0x180099511  mov     [rsp+110h+samDesired], esi; char *
0x180099515  lea     rax, [rbp+57h+pvData]
0x180099519  mov     qword ptr [rsp+110h+dwOptions], rax; unsigned int
0x18009951e  mov     r9d, esi; dwType
0x180099521  lea     r8, aAccountmigrati; "AccountMigration"
0x180099528  lea     rdx, aSoftwareMicros_14; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18009952f  mov     rcx, r13; hKey
0x180099532  call    cs:__imp_RegSetKeyValueW
0x180099538  mov     rcx, [rbp+5Fh]; this
0x18009953c  test    eax, eax
0x18009953e  jz      short loc_180099554
0x180099540  mov     r9d, eax; char *
0x180099543  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x18009954a  mov     edx, 981h; void *
0x18009954f  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180099554  call    DisableLocalAccount
0x180099559  mov     rcx, [rbp+5Fh]; this
0x18009955d  lea     rdx, aDisabledefault; "DisableDefaultAccount"
0x180099564  mov     qword ptr [rsp+110h+dwOptions], rdx; int
0x180099569  mov     r9d, eax; char *
0x18009956c  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x180099573  mov     edx, 985h; void *
0x180099578  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18009957d  mov     ebx, r12d
0x180099580  mov     [rbp+57h+lpSidString], r12
0x180099584  lea     rax, [rbp+57h+lpSidString]
0x180099588  mov     [rbp+57h+var_78], rax
0x18009958c  mov     [rbp+57h+var_70], r12
0x180099590  mov     [rbp+57h+var_68], dil
0x180099594  lea     rdx, [rbp+57h+var_70]
0x180099598  lea     rcx, aDefaultaccount; "DefaultAccount"
0x18009959f  call    GetLocalAccountSidFromName
0x1800995a4  mov     rcx, [rbp+5Fh]; this
0x1800995a8  test    eax, eax
0x1800995aa  jns     short loc_1800995C3
0x1800995ac  mov     r9d, eax; char *
0x1800995af  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x1800995b6  mov     edx, 98Bh; void *
0x1800995bb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800995c0  mov     dil, r12b
0x1800995c3  lea     rcx, [rbp+57h+var_78]
0x1800995c7  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x1800995cc  test    dil, dil
0x1800995cf  jz      short loc_1800995F9
0x1800995d1  xor     r8d, r8d; lpComputerName
0x1800995d4  xor     edx, edx; lpProfilePath
0x1800995d6  mov     rcx, [rbp+57h+lpSidString]; lpSidString
0x1800995da  call    cs:__imp_DeleteProfileW
0x1800995e0  test    eax, eax
0x1800995e2  jnz     short loc_1800995F9
0x1800995e4  call    cs:__imp_GetLastError
0x1800995ea  mov     ebx, eax
0x1800995ec  test    eax, eax
0x1800995ee  jle     short loc_1800995F9
0x1800995f0  movzx   ebx, ax
0x1800995f3  or      ebx, 80070000h
0x1800995f9  call    ?Provider@DevCredSvcTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; DevCredSvcTraceLoggingProvider::Provider(void)
0x1800995fe  mov     r10, rax
0x180099601  mov     ecx, [rax]
0x180099603  cmp     ecx, esi
0x180099605  jbe     short loc_18009963E
0x180099607  mov     rdx, 400000000000h
0x180099611  mov     rcx, rax
0x180099614  call    _tlgKeywordOn
0x180099619  test    al, al
0x18009961b  jz      short loc_18009963E
0x18009961d  mov     [rbp+57h+arg_18], ebx
0x180099620  lea     rax, [rbp+57h+arg_18]
0x180099624  mov     qword ptr [rsp+110h+dwOptions], rax
0x180099629  xor     r9d, r9d
0x18009962c  xor     r8d, r8d
0x18009962f  lea     rdx, byte_18010864F
0x180099636  mov     rcx, r10
0x180099639  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18009963e  lea     rcx, [rbp+57h+lpSidString]; void *
0x180099642  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180099647  nop
0x180099648  xor     edx, edx
0x18009964a  lea     rcx, [rbp+57h+var_B0]
0x18009964e  call    ?reset@?$unique_ptr@VPackageUtil@@U?$default_delete@VPackageUtil@@@wistd@@@wistd@@QEAAXPEAVPackageUtil@@@Z; wistd::unique_ptr<PackageUtil,wistd::default_delete<PackageUtil>>::reset(PackageUtil *)
0x180099653  nop
0x180099654  lea     rcx, [rbp+57h+var_A8]
0x180099658  call    wil__details__ScopeExitFnGuard__lambda_d8173cb92363fa7c66c11fc7ee07aa30_____operator__
0x18009965d  nop
0x18009965e  lea     rcx, [rbp+57h+hKey]
0x180099662  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180099667  mov     ebx, r12d
0x18009966a  lea     rcx, [rbp+57h+var_80]; void *
0x18009966e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180099673  nop
0x180099674  lea     rcx, [rbp+57h+var_48]
0x180099678  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18009967d  mov     eax, ebx
0x18009967f  add     rsp, 0D8h
0x180099686  pop     r15
0x180099688  pop     r14
0x18009968a  pop     r13
0x18009968c  pop     r12
0x18009968e  pop     rdi
0x18009968f  pop     rsi
0x180099690  pop     rbx
0x180099691  pop     rbp
0x180099692  retn
```
