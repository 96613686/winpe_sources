# CollectDBUpdateDeviceAttributes(int *,int *,ushort * *,_SYSTEMTIME *)

- ea: `0x18003b72c`
- end: `0x18003b99a`
- name: `?CollectDBUpdateDeviceAttributes@@YAJPEAH0PEAPEAGPEAU_SYSTEMTIME@@@Z`
- size: `622`
- prototype: `int(int *, int *, unsigned __int16 **, struct _SYSTEMTIME *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001e5d0`

## callees

- `0x1800078b0`
- `0x18000e48c`
- `0x18001a42c`
- `0x1800243e8`
- `0x18003b594`
- `0x18003b72c`
- `0x18003bb14`
- `0x18003c028`
- `0x18003c0b8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18003b877`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18003b877`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b944`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b944`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003b80a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003b91d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003b80a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003b91d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003b84c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003b84c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18003b788`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18003b788`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18003b796`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18003b796`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18003b93a`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18003b93a`

## string_xrefs

- `0x18003b7ff`: `CanAttemptUpdateAfter`
- `0x18003b841`: `CanAttemptUpdateAfter`
- `0x18003b912`: `CanAttemptUpdateAfter`
- `0x18003b7b8`: `DeviceAttributes registry doesn't exist, creating it`
- `0x18003b886`: `Still under DBUPDATE_CAN_ATTEMPT_AFTER_TIME window`
- `0x18003b8c7`: `Some Attribute(s) changed, advancing CanAttemptAfter by 7 days`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CollectDBUpdateDeviceAttributes(int *a1, int *a2, unsigned __int16 **a3, struct _SYSTEMTIME *a4)
{
  __int64 v8; // rcx
  __int64 v9; // rcx
  int v10; // eax
  signed int v11; // ebx
  unsigned __int64 v12; // r9
  __int64 v13; // rdx
  LSTATUS v14; // eax
  LSTATUS v15; // eax
  int v16; // eax
  int v17; // eax
  LSTATUS v18; // eax
  signed int LastError; // eax
  int lpData; // [rsp+20h] [rbp-58h]
  HKEY hKey; // [rsp+30h] [rbp-48h] BYREF
  int v23; // [rsp+38h] [rbp-40h] BYREF
  DWORD cbData; // [rsp+3Ch] [rbp-3Ch] BYREF
  struct _FILETIME FileTime; // [rsp+40h] [rbp-38h] BYREF
  BYTE Data[8]; // [rsp+48h] [rbp-30h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+50h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+30h]

  v23 = 1;
  hKey = 0;
  *(_QWORD *)Data = 0;
  SystemTime = 0;
  FileTime = 0;
  cbData = 8;
  GetSystemTime(&SystemTime);
  SystemTimeToFileTime(&SystemTime, &FileTime);
  if ( (unsigned int)wil::reg::open_unique_key_nothrow(
                       v8,
                       L"SYSTEM\\CurrentControlSet\\Control\\SecureBoot\\Servicing\\DeviceAttributes",
                       &hKey,
                       1) == -2147024894 )
  {
    *a1 = 1;
    SBServicingLogMessage((wchar_t *)L"DeviceAttributes registry doesn't exist, creating it");
    v10 = wil::reg::create_unique_key_nothrow(
            v9,
            L"SYSTEM\\CurrentControlSet\\Control\\SecureBoot\\Servicing\\DeviceAttributes",
            &hKey);
    v11 = v10;
    if ( v10 < 0 )
    {
      v12 = (unsigned int)v10;
      v13 = 381;
LABEL_27:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecore\\base\\secureboot\\servicing\\lib\\sbsattributes.cpp",
        (const char *)v12,
        lpData);
      goto LABEL_28;
    }
  }
  v14 = RegQueryValueExW(hKey, L"CanAttemptUpdateAfter", 0, 0, Data, &cbData);
  v11 = v14;
  if ( v14 > 0 )
    v11 = (unsigned __int16)v14 | 0x80070000;
  if ( v11 == -2147024894 )
  {
    v15 = RegSetValueExW(hKey, L"CanAttemptUpdateAfter", 0, 3u, (const BYTE *)&FileTime, 8u);
    v11 = v15;
    if ( v15 > 0 )
      v11 = (unsigned __int16)v15 | 0x80070000;
  }
  if ( v11 < 0 )
  {
    v13 = 408;
LABEL_26:
    v12 = (unsigned int)v11;
    goto LABEL_27;
  }
  if ( CompareFileTime(&FileTime, (const FILETIME *)Data) < 0 || *a1 )
  {
    SBServicingLogMessage((wchar_t *)L"Still under DBUPDATE_CAN_ATTEMPT_AFTER_TIME window");
    *a2 = 1;
  }
  v16 = CompareAndSaveDeviceAttributes((__int64)&hKey, &v23, a3);
  v11 = v16;
  if ( v16 < 0 )
  {
    v12 = (unsigned int)v16;
    v13 = 426;
    goto LABEL_27;
  }
  if ( !v23 )
  {
    *a1 = 1;
    SBServicingLogMessage((wchar_t *)L"Some Attribute(s) changed, advancing CanAttemptAfter by 7 days");
    v17 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))AdvanceDBUpdateCanAttemptAfterIntoRegistry)(
            &hKey,
            FileTime,
            6048000000000LL);
    v11 = v17;
    if ( v17 < 0 )
    {
      v12 = (unsigned int)v17;
      v13 = 439;
      goto LABEL_27;
    }
  }
  v18 = RegQueryValueExW(hKey, L"CanAttemptUpdateAfter", 0, 0, Data, &cbData);
  v11 = v18;
  if ( v18 < 0 )
  {
    v12 = (unsigned int)v18;
    v13 = 443;
    goto LABEL_27;
  }
  if ( !FileTimeToSystemTime((const FILETIME *)Data, a4) )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    if ( v11 < 0 )
    {
      v13 = 444;
      goto LABEL_26;
    }
  }
LABEL_28:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18003b72c  push    rbp
0x18003b72e  push    rbx
0x18003b72f  push    rsi
0x18003b730  push    rdi
0x18003b731  push    r14
0x18003b733  push    r15
0x18003b735  mov     rbp, rsp
0x18003b738  sub     rsp, 78h
0x18003b73c  mov     rax, cs:__security_cookie
0x18003b743  xor     rax, rsp
0x18003b746  mov     [rbp+var_18], rax
0x18003b74a  mov     r15, r9
0x18003b74d  mov     r14, r8
0x18003b750  mov     rsi, rdx
0x18003b753  mov     rdi, rcx
0x18003b756  mov     ebx, 1
0x18003b75b  mov     [rbp+var_40], ebx
0x18003b75e  mov     [rbp+hKey], 0
0x18003b766  mov     qword ptr [rbp+Data], 0
0x18003b76e  xorps   xmm0, xmm0
0x18003b771  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x18003b775  mov     qword ptr [rbp+FileTime.dwLowDateTime], 0
0x18003b77d  mov     [rbp+cbData], 8
0x18003b784  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x18003b788  call    cs:__imp_GetSystemTime
0x18003b78e  lea     rdx, [rbp+FileTime]; lpFileTime
0x18003b792  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x18003b796  call    cs:__imp_SystemTimeToFileTime
0x18003b79c  mov     r9d, ebx
0x18003b79f  lea     r8, [rbp+hKey]
0x18003b7a3  lea     rdx, psz1; "SYSTEM\\CurrentControlSet\\Control\\Sec"...
0x18003b7aa  call    ?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x18003b7af  cmp     eax, 80070002h
0x18003b7b4  jnz     short loc_18003B7E7
0x18003b7b6  mov     [rdi], ebx
0x18003b7b8  lea     rcx, aDeviceattribut; "DeviceAttributes registry doesn't exist"...
0x18003b7bf  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003b7c4  lea     r8, [rbp+hKey]
0x18003b7c8  lea     rdx, psz1; "SYSTEM\\CurrentControlSet\\Control\\Sec"...
0x18003b7cf  call    ?create_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::create_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x18003b7d4  mov     ebx, eax
0x18003b7d6  test    eax, eax
0x18003b7d8  jns     short loc_18003B7E7
0x18003b7da  mov     r9d, eax
0x18003b7dd  mov     edx, 17Dh
0x18003b7e2  jmp     loc_18003B965
0x18003b7e7  lea     rax, [rbp+cbData]
0x18003b7eb  mov     [rsp+78h+lpcbData], rax; lpcbData
0x18003b7f0  lea     rax, [rbp+Data]
0x18003b7f4  mov     [rsp+78h+lpData], rax; lpData
0x18003b7f9  xor     r9d, r9d; lpType
0x18003b7fc  xor     r8d, r8d; lpReserved
0x18003b7ff  lea     rdx, aCanattemptupda; "CanAttemptUpdateAfter"
0x18003b806  mov     rcx, [rbp+hKey]; hKey
0x18003b80a  call    cs:__imp_RegQueryValueExW
0x18003b810  mov     ebx, eax
0x18003b812  test    eax, eax
0x18003b814  jle     short loc_18003B81F
0x18003b816  movzx   ebx, ax
0x18003b819  or      ebx, 80070000h
0x18003b81f  cmp     ebx, 80070002h
0x18003b825  jnz     short loc_18003B861
0x18003b827  mov     dword ptr [rsp+78h+lpcbData], 8; cbData
0x18003b82f  lea     rax, [rbp+FileTime]
0x18003b833  mov     [rsp+78h+lpData], rax; lpData
0x18003b838  mov     r9d, 3; dwType
0x18003b83e  xor     r8d, r8d; Reserved
0x18003b841  lea     rdx, aCanattemptupda; "CanAttemptUpdateAfter"
0x18003b848  mov     rcx, [rbp+hKey]; hKey
0x18003b84c  call    cs:__imp_RegSetValueExW
0x18003b852  mov     ebx, eax
0x18003b854  test    eax, eax
0x18003b856  jle     short loc_18003B861
0x18003b858  movzx   ebx, ax
0x18003b85b  or      ebx, 80070000h
0x18003b861  test    ebx, ebx
0x18003b863  jns     short loc_18003B86F
0x18003b865  mov     edx, 198h
0x18003b86a  jmp     loc_18003B962
0x18003b86f  lea     rdx, [rbp+Data]; lpFileTime2
0x18003b873  lea     rcx, [rbp+FileTime]; lpFileTime1
0x18003b877  call    cs:__imp_CompareFileTime
0x18003b87d  test    eax, eax
0x18003b87f  js      short loc_18003B886
0x18003b881  cmp     dword ptr [rdi], 0
0x18003b884  jz      short loc_18003B898
0x18003b886  lea     rcx, aStillUnderDbup; "Still under DBUPDATE_CAN_ATTEMPT_AFTER_"...
0x18003b88d  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003b892  mov     dword ptr [rsi], 1
0x18003b898  mov     r8, r14
0x18003b89b  lea     rdx, [rbp+var_40]
0x18003b89f  lea     rcx, [rbp+hKey]
0x18003b8a3  call    ?CompareAndSaveDeviceAttributes@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAHPEAPEAG@Z; CompareAndSaveDeviceAttributes(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,int *,ushort * *)
0x18003b8a8  mov     ebx, eax
0x18003b8aa  test    eax, eax
0x18003b8ac  jns     short loc_18003B8BB
0x18003b8ae  mov     r9d, eax
0x18003b8b1  mov     edx, 1AAh
0x18003b8b6  jmp     loc_18003B965
0x18003b8bb  cmp     [rbp+var_40], 0
0x18003b8bf  jnz     short loc_18003B8FA
0x18003b8c1  mov     dword ptr [rdi], 1
0x18003b8c7  lea     rcx, aSomeAttributeS; "Some Attribute(s) changed, advancing Ca"...
0x18003b8ce  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003b8d3  mov     r8, 58028E44000h
0x18003b8dd  mov     rdx, qword ptr [rbp+FileTime.dwLowDateTime]
0x18003b8e1  lea     rcx, [rbp+hKey]
0x18003b8e5  call    ?AdvanceDBUpdateCanAttemptAfterIntoRegistry@@YAJAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@U_FILETIME@@_K@Z; AdvanceDBUpdateCanAttemptAfterIntoRegistry(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,_FILETIME,unsigned __int64)
0x18003b8ea  mov     ebx, eax
0x18003b8ec  test    eax, eax
0x18003b8ee  jns     short loc_18003B8FA
0x18003b8f0  mov     r9d, eax
0x18003b8f3  mov     edx, 1B7h
0x18003b8f8  jmp     short loc_18003B965
0x18003b8fa  lea     rax, [rbp+cbData]
0x18003b8fe  mov     [rsp+78h+lpcbData], rax; lpcbData
0x18003b903  lea     rax, [rbp+Data]
0x18003b907  mov     [rsp+78h+lpData], rax; int
0x18003b90c  xor     r9d, r9d; lpType
0x18003b90f  xor     r8d, r8d; lpReserved
0x18003b912  lea     rdx, aCanattemptupda; "CanAttemptUpdateAfter"
0x18003b919  mov     rcx, [rbp+hKey]; hKey
0x18003b91d  call    cs:__imp_RegQueryValueExW
0x18003b923  mov     ebx, eax
0x18003b925  test    eax, eax
0x18003b927  jns     short loc_18003B933
0x18003b929  mov     r9d, eax
0x18003b92c  mov     edx, 1BBh
0x18003b931  jmp     short loc_18003B965
0x18003b933  mov     rdx, r15; lpSystemTime
0x18003b936  lea     rcx, [rbp+Data]; lpFileTime
0x18003b93a  call    cs:__imp_FileTimeToSystemTime
0x18003b940  test    eax, eax
0x18003b942  jnz     short loc_18003B976
0x18003b944  call    cs:__imp_GetLastError
0x18003b94a  mov     ebx, eax
0x18003b94c  test    eax, eax
0x18003b94e  jle     short loc_18003B959
0x18003b950  movzx   ebx, ax
0x18003b953  or      ebx, 80070000h
0x18003b959  test    ebx, ebx
0x18003b95b  jns     short loc_18003B976
0x18003b95d  mov     edx, 1BCh; void *
0x18003b962  mov     r9d, ebx; char *
0x18003b965  lea     r8, aOnecoreBaseSec_5; "onecore\\base\\secureboot\\servicing\\l"...
0x18003b96c  mov     rcx, [rbp+30h]; this
0x18003b970  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b975  nop
0x18003b976  lea     rcx, [rbp+hKey]
0x18003b97a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003b97f  mov     eax, ebx
0x18003b981  mov     rcx, [rbp+var_18]
0x18003b985  xor     rcx, rsp; StackCookie
0x18003b988  call    __security_check_cookie
0x18003b98d  add     rsp, 78h
0x18003b991  pop     r15
0x18003b993  pop     r14
0x18003b995  pop     rdi
0x18003b996  pop     rsi
0x18003b997  pop     rbx
0x18003b998  pop     rbp
0x18003b999  retn
```
