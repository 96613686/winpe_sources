# DcaMgr::DeviceCredentialMgr::CheckIfUserSessionIsRequired(bool *)

- ea: `0x1800547f0`
- end: `0x180054bd0`
- name: `?CheckIfUserSessionIsRequired@DeviceCredentialMgr@DcaMgr@@QEAAJPEA_N@Z`
- size: `992`
- prototype: `__int64 __fastcall(DcaMgr::DeviceCredentialMgr *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18009e870`

## callees

- `0x18000782c`
- `0x18000926c`
- `0x1800281e0`
- `0x180028200`
- `0x1800323d0`
- `0x180032c20`
- `0x180047228`
- `0x180048304`
- `0x1800531ac`
- `0x1800535f4`
- `0x1800547f0`
- `0x180054bd8`
- `0x1800596ec`
- `0x180097cb4`
- `0x180098960`
- `0x1800a73c4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800548ee`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180054a63`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800548ee`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180054a63`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180054acb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180054acb`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180054a0f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180054a0f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180054982`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180054982`

## string_xrefs

- `0x18005482e`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x18005489a`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x180054928`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x180054993`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x180054a20`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x180054a81`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x180054adc`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x180054b23`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x180054b9c`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DcaMgr::DeviceCredentialMgr::CheckIfUserSessionIsRequired(
        DcaMgr::DeviceCredentialMgr *this,
        bool *a2)
{
  int v3; // eax
  int v4; // ecx
  int v5; // ebx
  __int64 v7; // rdx
  bool v8; // sf
  unsigned int v9; // eax
  const char *v10; // r9
  DWORD v11; // eax
  DcaMgr::DeviceCredentialMgr *v12; // rcx
  WCHAR *v13; // rbx
  char v14; // r14
  DWORD i; // esi
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // edi
  unsigned int v19; // eax
  int v20; // eax
  int v21; // ebx
  bool v22; // dl
  int phkResult; // [rsp+20h] [rbp-59h]
  int phkResulta; // [rsp+20h] [rbp-59h]
  unsigned int phkResultb; // [rsp+20h] [rbp-59h]
  unsigned int phkResultc; // [rsp+20h] [rbp-59h]
  BYTE Data[8]; // [rsp+60h] [rbp-19h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-11h] BYREF
  void *v29; // [rsp+70h] [rbp-9h] BYREF
  HKEY v30; // [rsp+78h] [rbp-1h] BYREF
  LPWSTR lpName; // [rsp+80h] [rbp+7h] BYREF
  void *p_hKey; // [rsp+88h] [rbp+Fh] BYREF
  HKEY v33; // [rsp+90h] [rbp+17h] BYREF
  char v34; // [rsp+98h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  DcaMgr::DeviceCredentialMgr *cchName; // [rsp+E0h] [rbp+67h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+E8h] [rbp+6Fh] BYREF
  DWORD cSubKeys; // [rsp+F0h] [rbp+77h] BYREF
  DWORD cbData; // [rsp+F8h] [rbp+7Fh] BYREF

  cchName = this;
  *a2 = 0;
  LOBYTE(cchName) = 0;
  v3 = IsFirstlogonAllowed(&cchName);
  v5 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x869,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
      (const char *)(unsigned int)v3,
      phkResult);
    return (unsigned int)v5;
  }
  if ( (_BYTE)cchName )
  {
    v29 = 0;
    p_hKey = &v29;
    v33 = 0;
    v34 = 1;
    v5 = OpenCallerImpersonationToken(v4, (HANDLE *)&v33);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&p_hKey);
    if ( v5 < 0 )
    {
      v7 = 2159;
LABEL_9:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v7,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
        (const char *)(unsigned int)v5,
        phkResult);
LABEL_42:
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v29);
      return (unsigned int)v5;
    }
    if ( !DcaMgr::DeviceCredentialMgr::HasAdminPermission(v29) )
    {
      v5 = -2147024891;
      v7 = 2162;
      goto LABEL_9;
    }
    *(_DWORD *)Data = 0;
    cbData = 0;
    hKey = 0;
    p_hKey = &hKey;
    v33 = 0;
    v34 = 1;
    v5 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\SecondaryAuthFactor\\Applications",
           0,
           0x20019u,
           &v33);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
    if ( v5 )
    {
      if ( v5 != 2 )
      {
        v8 = v5 < 0;
        if ( v5 > 0 )
        {
          v5 = (unsigned __int16)v5 | 0x80070000;
          v8 = v5 < 0;
        }
        if ( v8 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x883,
            (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
            (const char *)(unsigned int)v5,
            phkResulta);
        goto LABEL_41;
      }
      goto LABEL_38;
    }
    cSubKeys = 0;
    cbMaxSubKeyLen = 0;
    v9 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    if ( v9 )
    {
      v5 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x897,
             (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
             (const char *)v9,
             phkResultb);
LABEL_41:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      goto LABEL_42;
    }
    v11 = ++cbMaxSubKeyLen;
    if ( cSubKeys )
    {
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &lpName,
        0,
        v11,
        v10);
      v13 = lpName;
      if ( !lpName )
      {
        v5 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x89C,
          (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
          (const char *)0x8007000ELL,
          phkResultb);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpName);
        goto LABEL_41;
      }
      v14 = 0;
      for ( i = 0; i < cSubKeys; ++i )
      {
        LODWORD(cchName) = cbMaxSubKeyLen;
        v16 = RegEnumKeyExW(hKey, i, v13, (LPDWORD)&cchName, 0, 0, 0, 0);
        if ( v16 )
        {
          wil::details::in1diag3::_Log_Win32(
            retaddr,
            (void *)0x8A9,
            (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
            (const char *)v16,
            phkResultc);
        }
        else
        {
          v30 = 0;
          p_hKey = &v30;
          v33 = 0;
          v34 = 1;
          v17 = RegOpenKeyExW(hKey, v13, 0, 0x20019u, &v33);
          v18 = wil::details::in1diag3::Log_IfWin32ErrorMsg(
                  retaddr,
                  (void *)0x8B6,
                  (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
                  (const char *)v17,
                  (unsigned int)"PackageNameHash=%ws",
                  (const char *)v13);
          wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
          if ( !v18 )
          {
            cbData = 4;
            v19 = RegQueryValueExW(v30, L"DeploymentFlag", 0, 0, Data, &cbData);
            if ( v19 )
            {
              wil::details::in1diag3::_Log_Win32(
                retaddr,
                (void *)0x8C2,
                (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
                (const char *)v19,
                phkResultb);
            }
            else if ( *(_DWORD *)Data )
            {
              v14 = 1;
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v30);
              break;
            }
          }
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v30);
        }
      }
      v20 = DcaMgr::DeviceCredentialMgr::EnableDeploymentTask(v12);
      v21 = v20;
      if ( v20 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x8CA,
          (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
          (const char *)(unsigned int)v20,
          phkResultb);
      v22 = 0;
      if ( v21 >= 0 )
        v22 = v14;
      if ( v22 )
      {
        *a2 = v22;
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpName);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        v5 = 0;
        goto LABEL_42;
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpName);
    }
LABEL_38:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v29);
  }
  return 0;
}

```

## disassembly

```asm
0x1800547f0  mov     [rsp-8+cchName], rcx
0x1800547f5  push    rbp
0x1800547f6  push    rbx
0x1800547f7  push    rsi
0x1800547f8  push    rdi
0x1800547f9  push    r12
0x1800547fb  push    r14
0x1800547fd  push    r15
0x1800547ff  lea     rbp, [rsp-27h]
0x180054804  sub     rsp, 0A0h
0x18005480b  mov     r15, rdx
0x18005480e  xor     r12d, r12d
0x180054811  mov     [rdx], r12b
0x180054814  mov     byte ptr [rbp+57h+cchName], r12b
0x180054818  lea     rcx, [rbp+57h+cchName]
0x18005481c  call    IsFirstlogonAllowed
0x180054821  mov     ebx, eax
0x180054823  test    eax, eax
0x180054825  jns     short loc_180054846
0x180054827  mov     rcx, [rbp+5Fh]; this
0x18005482b  mov     r9d, eax; char *
0x18005482e  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x180054835  mov     edx, 869h; void *
0x18005483a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005483f  mov     eax, ebx
0x180054841  jmp     loc_180054B7E
0x180054846  cmp     byte ptr [rbp+57h+cchName], r12b
0x18005484a  jz      loc_180054B7C
0x180054850  mov     [rbp+57h+var_60], r12
0x180054854  lea     rax, [rbp+57h+var_60]
0x180054858  mov     [rbp+57h+var_48], rax
0x18005485c  mov     [rbp+57h+var_40], r12
0x180054860  mov     [rbp+57h+var_38], 1
0x180054864  lea     rdx, [rbp+57h+var_40]
0x180054868  call    OpenCallerImpersonationToken
0x18005486d  mov     ebx, eax
0x18005486f  lea     rcx, [rbp+57h+var_48]
0x180054873  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x180054878  test    ebx, ebx
0x18005487a  jns     short loc_180054883
0x18005487c  mov     edx, 86Fh
0x180054881  jmp     short loc_18005489A
0x180054883  mov     rcx, [rbp+57h+var_60]; void *
0x180054887  call    ?HasAdminPermission@DeviceCredentialMgr@DcaMgr@@CA_NPEAX@Z; DcaMgr::DeviceCredentialMgr::HasAdminPermission(void *)
0x18005488c  test    al, al
0x18005488e  jnz     short loc_1800548B2
0x180054890  mov     ebx, 80070005h
0x180054895  mov     edx, 872h; void *
0x18005489a  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x1800548a1  mov     r9d, ebx; char *
0x1800548a4  mov     rcx, [rbp+5Fh]; this
0x1800548a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800548ad  jmp     loc_180054BC2
0x1800548b2  mov     dword ptr [rbp+57h+Data], r12d
0x1800548b6  mov     [rbp+57h+cbData], r12d
0x1800548ba  mov     [rbp+57h+hKey], r12
0x1800548be  lea     rax, [rbp+57h+hKey]
0x1800548c2  mov     [rbp+57h+var_48], rax
0x1800548c6  mov     [rbp+57h+var_40], r12
0x1800548ca  mov     [rbp+57h+var_38], 1
0x1800548ce  lea     rax, [rbp+57h+var_40]
0x1800548d2  mov     [rsp+0D0h+phkResult], rax; int
0x1800548d7  mov     r9d, 20019h; samDesired
0x1800548dd  xor     r8d, r8d; ulOptions
0x1800548e0  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800548e7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800548ee  call    cs:__imp_RegOpenKeyExW
0x1800548f4  mov     ebx, eax
0x1800548f6  lea     rcx, [rbp+57h+var_48]
0x1800548fa  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800548ff  test    ebx, ebx
0x180054901  jz      short loc_18005493E
0x180054903  cmp     ebx, 2
0x180054906  jz      loc_180054B69
0x18005490c  test    ebx, ebx
0x18005490e  jle     short loc_18005491B
0x180054910  movzx   ebx, bx
0x180054913  or      ebx, 80070000h
0x180054919  test    ebx, ebx
0x18005491b  jns     loc_180054BB8
0x180054921  mov     rcx, [rbp+5Fh]; this
0x180054925  mov     r9d, ebx; char *
0x180054928  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x18005492f  mov     edx, 883h; void *
0x180054934  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054939  jmp     loc_180054BB8
0x18005493e  mov     [rbp+57h+cSubKeys], r12d
0x180054942  mov     [rbp+57h+cbMaxSubKeyLen], r12d
0x180054946  mov     [rsp+0D0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18005494b  mov     [rsp+0D0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x180054950  mov     [rsp+0D0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x180054955  mov     [rsp+0D0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x18005495a  mov     [rsp+0D0h+lpcValues], r12; lpcValues
0x18005495f  mov     [rsp+0D0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x180054964  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x180054968  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18005496d  lea     rax, [rbp+57h+cSubKeys]
0x180054971  mov     [rsp+0D0h+phkResult], rax; int
0x180054976  xor     r9d, r9d; lpReserved
0x180054979  xor     r8d, r8d; lpcchClass
0x18005497c  xor     edx, edx; lpClass
0x18005497e  mov     rcx, [rbp+57h+hKey]; hKey
0x180054982  call    cs:__imp_RegQueryInfoKeyW
0x180054988  test    eax, eax
0x18005498a  jz      short loc_1800549AB
0x18005498c  mov     rcx, [rbp+5Fh]; this
0x180054990  mov     r9d, eax; char *
0x180054993  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x18005499a  mov     edx, 897h; void *
0x18005499f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800549a4  mov     ebx, eax
0x1800549a6  jmp     loc_180054BB8
0x1800549ab  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x1800549ae  inc     eax
0x1800549b0  mov     [rbp+57h+cbMaxSubKeyLen], eax
0x1800549b3  cmp     [rbp+57h+cSubKeys], r12d
0x1800549b7  jz      loc_180054B69
0x1800549bd  mov     r8d, eax
0x1800549c0  xor     edx, edx
0x1800549c2  lea     rcx, [rbp+57h+lpName]
0x1800549c6  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800549cb  nop
0x1800549cc  mov     rbx, [rbp+57h+lpName]
0x1800549d0  test    rbx, rbx
0x1800549d3  jz      loc_180054B90
0x1800549d9  mov     r14b, r12b
0x1800549dc  mov     esi, r12d
0x1800549df  cmp     esi, [rbp+57h+cSubKeys]
0x1800549e2  jnb     loc_180054B11
0x1800549e8  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x1800549eb  mov     dword ptr [rbp+57h+cchName], eax
0x1800549ee  mov     [rsp+0D0h+lpcValues], r12; lpftLastWriteTime
0x1800549f3  mov     [rsp+0D0h+lpcbMaxClassLen], r12; lpcchClass
0x1800549f8  mov     [rsp+0D0h+lpcbMaxSubKeyLen], r12; lpClass
0x1800549fd  mov     [rsp+0D0h+phkResult], r12; unsigned int
0x180054a02  lea     r9, [rbp+57h+cchName]; lpcchName
0x180054a06  mov     r8, rbx; lpName
0x180054a09  mov     edx, esi; dwIndex
0x180054a0b  mov     rcx, [rbp+57h+hKey]; hKey
0x180054a0f  call    cs:__imp_RegEnumKeyExW
0x180054a15  mov     rcx, [rbp+5Fh]; this
0x180054a19  test    eax, eax
0x180054a1b  jz      short loc_180054A36
0x180054a1d  mov     r9d, eax; char *
0x180054a20  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x180054a27  mov     edx, 8A9h; void *
0x180054a2c  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180054a31  jmp     loc_180054AFE
0x180054a36  mov     [rbp+57h+var_58], r12
0x180054a3a  lea     rax, [rbp+57h+var_58]
0x180054a3e  mov     [rbp+57h+var_48], rax
0x180054a42  mov     [rbp+57h+var_40], r12
0x180054a46  mov     [rbp+57h+var_38], 1
0x180054a4a  lea     rax, [rbp+57h+var_40]
0x180054a4e  mov     [rsp+0D0h+phkResult], rax; phkResult
0x180054a53  mov     r9d, 20019h; samDesired
0x180054a59  xor     r8d, r8d; ulOptions
0x180054a5c  mov     rdx, rbx; lpSubKey
0x180054a5f  mov     rcx, [rbp+57h+hKey]; hKey
0x180054a63  call    cs:__imp_RegOpenKeyExW
0x180054a69  mov     rcx, [rbp+5Fh]; this
0x180054a6d  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rbx; char *
0x180054a72  lea     rdx, aPackagenamehas; "PackageNameHash=%ws"
0x180054a79  mov     [rsp+0D0h+phkResult], rdx; unsigned int
0x180054a7e  mov     r9d, eax; char *
0x180054a81  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x180054a88  mov     edx, 8B6h; void *
0x180054a8d  call    ?Log_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x180054a92  mov     edi, eax
0x180054a94  lea     rcx, [rbp+57h+var_48]
0x180054a98  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180054a9d  test    edi, edi
0x180054a9f  jnz     short loc_180054AF5
0x180054aa1  mov     [rbp+57h+cbData], 4
0x180054aa8  lea     rax, [rbp+57h+cbData]
0x180054aac  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax; lpcbData
0x180054ab1  lea     rax, [rbp+57h+Data]
0x180054ab5  mov     [rsp+0D0h+phkResult], rax; int
0x180054aba  xor     r9d, r9d; lpType
0x180054abd  xor     r8d, r8d; lpReserved
0x180054ac0  lea     rdx, aDeploymentflag; "DeploymentFlag"
0x180054ac7  mov     rcx, [rbp+57h+var_58]; hKey
0x180054acb  call    cs:__imp_RegQueryValueExW
0x180054ad1  mov     rcx, [rbp+5Fh]; this
0x180054ad5  test    eax, eax
0x180054ad7  jz      short loc_180054AEF
0x180054ad9  mov     r9d, eax; char *
0x180054adc  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x180054ae3  mov     edx, 8C2h; void *
0x180054ae8  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180054aed  jmp     short loc_180054AF5
0x180054aef  cmp     dword ptr [rbp+57h+Data], r12d
0x180054af3  jnz     short loc_180054B05
0x180054af5  lea     rcx, [rbp+57h+var_58]
0x180054af9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180054afe  inc     esi
0x180054b00  jmp     loc_1800549DF
0x180054b05  mov     r14b, 1
0x180054b08  lea     rcx, [rbp+57h+var_58]
0x180054b0c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180054b11  call    ?EnableDeploymentTask@DeviceCredentialMgr@DcaMgr@@AEAAJXZ; DcaMgr::DeviceCredentialMgr::EnableDeploymentTask(void)
0x180054b16  mov     ebx, eax
0x180054b18  mov     rcx, [rbp+5Fh]; this
0x180054b1c  test    eax, eax
0x180054b1e  jns     short loc_180054B34
0x180054b20  mov     r9d, eax; char *
0x180054b23  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x180054b2a  mov     edx, 8CAh; void *
0x180054b2f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180054b34  mov     edx, r12d
0x180054b37  movzx   ecx, r14b
0x180054b3b  test    ebx, ebx
0x180054b3d  cmovns  edx, ecx
0x180054b40  test    dl, dl
0x180054b42  jz      short loc_180054B5F
0x180054b44  mov     [r15], dl
0x180054b47  lea     rcx, [rbp+57h+lpName]; void *
0x180054b4b  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180054b50  nop
0x180054b51  lea     rcx, [rbp+57h+hKey]
0x180054b55  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180054b5a  mov     ebx, r12d
0x180054b5d  jmp     short loc_180054BC2
0x180054b5f  lea     rcx, [rbp+57h+lpName]; void *
0x180054b63  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180054b68  nop
0x180054b69  lea     rcx, [rbp+57h+hKey]
0x180054b6d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180054b72  nop
0x180054b73  lea     rcx, [rbp+57h+var_60]
0x180054b77  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180054b7c  xor     eax, eax
0x180054b7e  add     rsp, 0A0h
0x180054b85  pop     r15
0x180054b87  pop     r14
0x180054b89  pop     r12
0x180054b8b  pop     rdi
0x180054b8c  pop     rsi
0x180054b8d  pop     rbx
0x180054b8e  pop     rbp
0x180054b8f  retn
0x180054b90  mov     rcx, [rbp+5Fh]; this
0x180054b94  mov     ebx, 8007000Eh
0x180054b99  mov     r9d, ebx; char *
0x180054b9c  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x180054ba3  mov     edx, 89Ch; void *
0x180054ba8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054bad  nop
0x180054bae  lea     rcx, [rbp+57h+lpName]; void *
0x180054bb2  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180054bb7  nop
0x180054bb8  lea     rcx, [rbp+57h+hKey]
0x180054bbc  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180054bc1  nop
0x180054bc2  lea     rcx, [rbp+57h+var_60]
0x180054bc6  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180054bcb  jmp     loc_18005483F
```
