# DcaMgr::DeviceCredentialMgr::DeprovisionDevice(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,ushort const *)

- ea: `0x18005b9e0`
- end: `0x18005bce2`
- name: `?DeprovisionDevice@DeviceCredentialMgr@DcaMgr@@QEAAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@0PEBG@Z`
- size: `770`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180054074`

## callees

- `0x18000782c`
- `0x1800281e0`
- `0x180031184`
- `0x180032b6c`
- `0x180032c20`
- `0x180047228`
- `0x180048304`
- `0x1800596ec`
- `0x18005b9e0`
- `0x18005bce8`
- `0x18005be60`
- `0x180097c6c`
- `0x180097cb4`
- `0x180098960`
- `0x1800a5d30`
- `0x1800a73c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005ba70`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005ba70`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005bae7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005bbeb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005bae7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005bbeb`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18005bc4e`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18005bcad`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18005bc4e`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18005bcad`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18005bc2c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18005bc88`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18005bc2c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18005bc88`

## string_xrefs

- `0x18005ba3a`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`

## pseudocode

```c
__int64 __fastcall DcaMgr::DeviceCredentialMgr::DeprovisionDevice(RTL_SRWLOCK *a1, HKEY *a2, HKEY *a3, const WCHAR *a4)
{
  HKEY v8; // rcx
  int RegStringValue; // ebx
  int v10; // eax
  int v11; // eax
  int v12; // ebx
  LSTATUS v13; // ebx
  HKEY v14; // rcx
  int v15; // eax
  char v16; // bl
  const char *v17; // rbx
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-50h]
  PCWSTR SourceString; // [rsp+30h] [rbp-40h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-38h] BYREF
  unsigned __int16 *v25; // [rsp+40h] [rbp-30h] BYREF
  RTL_SRWLOCK *v26; // [rsp+48h] [rbp-28h] BYREF
  void *p_hKey; // [rsp+50h] [rbp-20h] BYREF
  HKEY v28; // [rsp+58h] [rbp-18h] BYREF
  char v29; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  HKEY v31; // [rsp+B0h] [rbp+40h] BYREF
  LPCWSTR lpSubKey; // [rsp+C0h] [rbp+50h] BYREF

  v29 = 1;
  p_hKey = &v25;
  v8 = *a3;
  v25 = 0;
  v28 = 0;
  RegStringValue = ReadRegStringValue(v8, 0, L"TpmHmacKeyName");
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_hKey);
  if ( RegStringValue >= 0 )
  {
    v10 = DcaMgr::DeviceCredentialTpmHmac::DeprovisionHmacKey(v25);
    if ( v10 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x8E8,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
        (const char *)(unsigned int)v10,
        phkResult);
  }
  AcquireSRWLockExclusive(a1 + 16);
  v26 = a1 + 16;
  LOBYTE(v31) = 0;
  v11 = IsFirstlogonAllowed(&v31);
  v12 = v11;
  if ( v11 >= 0 )
  {
    if ( (_BYTE)v31 )
    {
      hKey = 0;
      p_hKey = &hKey;
      v28 = 0;
      v29 = 1;
      v13 = RegOpenKeyExW(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\SecondaryAuthFactor\\Applications",
              0,
              0xF003Fu,
              &v28);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
      if ( !v13 )
      {
        v14 = *a3;
        p_hKey = &SourceString;
        SourceString = 0;
        v28 = 0;
        v29 = 1;
        v15 = ReadRegStringValue(v14, 0, L"PackageFullName");
        if ( v15 >= 0 )
        {
          v16 = 1;
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x900,
            (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
            (const char *)(unsigned int)v15,
            phkResult);
          v16 = 0;
        }
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_hKey);
        if ( v16 )
        {
          p_hKey = &lpSubKey;
          lpSubKey = 0;
          v28 = 0;
          v29 = 1;
          v12 = ConvertPackageFullNameToHashString(SourceString);
          wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_hKey);
          if ( v12 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x905,
              (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
              (const char *)(unsigned int)v12,
              phkResult);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpSubKey);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&SourceString);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
            goto LABEL_24;
          }
          v17 = (const char *)lpSubKey;
          p_hKey = &v31;
          v31 = 0;
          v28 = 0;
          v29 = 1;
          v18 = RegOpenKeyExW(hKey, lpSubKey, 0, 0xF003Fu, &v28);
          LODWORD(v17) = wil::details::in1diag3::Log_IfWin32ErrorMsg(
                           retaddr,
                           (void *)0x90F,
                           (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
                           (const char *)v18,
                           (unsigned int)"PackageNameHash=%ws",
                           v17);
          wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
          if ( !(_DWORD)v17 )
          {
            v19 = RegDeleteTreeW(v31, a4);
            if ( v19 )
              wil::details::in1diag3::_Log_Win32(
                retaddr,
                (void *)0x913,
                (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
                (const char *)v19,
                phkResult);
            RegFlushKey(v31);
          }
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v31);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpSubKey);
        }
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&SourceString);
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      a3,
      0);
    v20 = RegDeleteTreeW(*a2, a4);
    if ( v20 )
    {
      v12 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x91D,
              (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
              (const char *)v20,
              phkResult);
    }
    else
    {
      RegFlushKey(*a2);
      v12 = 0;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8EE,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
      (const char *)(unsigned int)v11,
      phkResult);
  }
LABEL_24:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v26);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v25);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18005b9e0  mov     [rsp-38h+arg_8], rbx
0x18005b9e5  push    rbp
0x18005b9e6  push    rsi
0x18005b9e7  push    rdi
0x18005b9e8  push    r12
0x18005b9ea  push    r13
0x18005b9ec  push    r14
0x18005b9ee  push    r15
0x18005b9f0  mov     rbp, rsp
0x18005b9f3  sub     rsp, 70h
0x18005b9f7  mov     rdi, r8
0x18005b9fa  mov     [rbp+var_10], 1
0x18005b9fe  mov     r14, r9
0x18005ba01  lea     rax, [rbp+var_30]
0x18005ba05  mov     rsi, rdx
0x18005ba08  mov     [rbp+var_20], rax
0x18005ba0c  mov     r15, rcx
0x18005ba0f  lea     r9, [rbp+var_18]
0x18005ba13  mov     rcx, [rdi]; hkey
0x18005ba16  lea     r8, aTpmhmackeyname; "TpmHmacKeyName"
0x18005ba1d  xor     r12d, r12d
0x18005ba20  xor     edx, edx; lpSubKey
0x18005ba22  mov     [rbp+var_30], r12
0x18005ba26  mov     [rbp+var_18], r12
0x18005ba2a  call    ReadRegStringValue
0x18005ba2f  lea     rcx, [rbp+var_20]
0x18005ba33  mov     ebx, eax
0x18005ba35  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18005ba3a  lea     r13, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x18005ba41  test    ebx, ebx
0x18005ba43  js      short loc_18005BA66
0x18005ba45  mov     rcx, [rbp+var_30]; unsigned __int16 *
0x18005ba49  call    ?DeprovisionHmacKey@DeviceCredentialTpmHmac@DcaMgr@@SAJPEBG@Z; DcaMgr::DeviceCredentialTpmHmac::DeprovisionHmacKey(ushort const *)
0x18005ba4e  test    eax, eax
0x18005ba50  jns     short loc_18005BA66
0x18005ba52  mov     rcx, [rbp+38h]; this
0x18005ba56  mov     r9d, eax; char *
0x18005ba59  mov     r8, r13; unsigned int
0x18005ba5c  mov     edx, 8E8h; void *
0x18005ba61  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005ba66  lea     rbx, [r15+80h]
0x18005ba6d  mov     rcx, rbx; SRWLock
0x18005ba70  call    cs:__imp_AcquireSRWLockExclusive
0x18005ba76  lea     rcx, [rbp+arg_0]
0x18005ba7a  mov     [rbp+var_28], rbx
0x18005ba7e  mov     byte ptr [rbp+arg_0], r12b
0x18005ba82  call    IsFirstlogonAllowed
0x18005ba87  mov     ebx, eax
0x18005ba89  test    eax, eax
0x18005ba8b  jns     short loc_18005BAA6
0x18005ba8d  mov     rcx, [rbp+38h]; this
0x18005ba91  mov     r9d, eax; char *
0x18005ba94  mov     r8, r13; unsigned int
0x18005ba97  mov     edx, 8EEh; void *
0x18005ba9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005baa1  jmp     loc_18005BCB6
0x18005baa6  cmp     byte ptr [rbp+arg_0], r12b
0x18005baaa  jz      loc_18005BC78
0x18005bab0  lea     rax, [rbp+hKey]
0x18005bab4  mov     [rbp+hKey], r12
0x18005bab8  mov     [rbp+var_20], rax
0x18005babc  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18005bac3  lea     rax, [rbp+var_18]
0x18005bac7  mov     [rbp+var_18], r12
0x18005bacb  mov     r15d, 0F003Fh
0x18005bad1  mov     [rsp+70h+phkResult], rax; int
0x18005bad6  mov     r9d, r15d; samDesired
0x18005bad9  mov     [rbp+var_10], 1
0x18005badd  xor     r8d, r8d; ulOptions
0x18005bae0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005bae7  call    cs:__imp_RegOpenKeyExW
0x18005baed  lea     rcx, [rbp+var_20]
0x18005baf1  mov     ebx, eax
0x18005baf3  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18005baf8  test    ebx, ebx
0x18005bafa  jnz     loc_18005BC6F
0x18005bb00  mov     rcx, [rdi]; hkey
0x18005bb03  lea     rax, [rbp+SourceString]
0x18005bb07  lea     r9, [rbp+var_18]
0x18005bb0b  mov     [rbp+var_20], rax
0x18005bb0f  lea     r8, aPackagefullnam; "PackageFullName"
0x18005bb16  mov     [rbp+SourceString], r12
0x18005bb1a  xor     edx, edx; lpSubKey
0x18005bb1c  mov     [rbp+var_18], r12
0x18005bb20  mov     [rbp+var_10], 1
0x18005bb24  call    ReadRegStringValue
0x18005bb29  test    eax, eax
0x18005bb2b  jns     short loc_18005BB46
0x18005bb2d  mov     rcx, [rbp+38h]; this
0x18005bb31  mov     r9d, eax; char *
0x18005bb34  mov     r8, r13; unsigned int
0x18005bb37  mov     edx, 900h; void *
0x18005bb3c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005bb41  mov     bl, r12b
0x18005bb44  jmp     short loc_18005BB48
0x18005bb46  mov     bl, 1
0x18005bb48  lea     rcx, [rbp+var_20]
0x18005bb4c  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18005bb51  test    bl, bl
0x18005bb53  jz      loc_18005BC66
0x18005bb59  mov     rcx, [rbp+SourceString]; SourceString
0x18005bb5d  lea     rax, [rbp+lpSubKey]
0x18005bb61  lea     rdx, [rbp+var_18]
0x18005bb65  mov     [rbp+var_20], rax
0x18005bb69  mov     [rbp+lpSubKey], r12
0x18005bb6d  mov     [rbp+var_18], r12
0x18005bb71  mov     [rbp+var_10], 1
0x18005bb75  call    ConvertPackageFullNameToHashString
0x18005bb7a  lea     rcx, [rbp+var_20]
0x18005bb7e  mov     ebx, eax
0x18005bb80  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18005bb85  test    ebx, ebx
0x18005bb87  jns     short loc_18005BBBD
0x18005bb89  mov     rcx, [rbp+38h]; this
0x18005bb8d  mov     r9d, ebx; char *
0x18005bb90  mov     r8, r13; unsigned int
0x18005bb93  mov     edx, 905h; void *
0x18005bb98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005bb9d  lea     rcx, [rbp+lpSubKey]; void *
0x18005bba1  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18005bba6  lea     rcx, [rbp+SourceString]; void *
0x18005bbaa  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18005bbaf  lea     rcx, [rbp+hKey]
0x18005bbb3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005bbb8  jmp     loc_18005BCB6
0x18005bbbd  mov     rbx, [rbp+lpSubKey]
0x18005bbc1  lea     rax, [rbp+arg_0]
0x18005bbc5  mov     rcx, [rbp+hKey]; hKey
0x18005bbc9  mov     r9d, r15d; samDesired
0x18005bbcc  mov     [rbp+var_20], rax
0x18005bbd0  xor     r8d, r8d; ulOptions
0x18005bbd3  lea     rax, [rbp+var_18]
0x18005bbd7  mov     [rbp+arg_0], r12
0x18005bbdb  mov     rdx, rbx; lpSubKey
0x18005bbde  mov     [rsp+70h+phkResult], rax; phkResult
0x18005bbe3  mov     [rbp+var_18], r12
0x18005bbe7  mov     [rbp+var_10], 1
0x18005bbeb  call    cs:__imp_RegOpenKeyExW
0x18005bbf1  mov     rcx, [rbp+38h]; this
0x18005bbf5  lea     rdx, aPackagenamehas; "PackageNameHash=%ws"
0x18005bbfc  mov     [rsp+70h+var_48], rbx; char *
0x18005bc01  mov     r9d, eax; char *
0x18005bc04  mov     [rsp+70h+phkResult], rdx; unsigned int
0x18005bc09  mov     r8, r13; unsigned int
0x18005bc0c  mov     edx, 90Fh; void *
0x18005bc11  call    ?Log_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18005bc16  lea     rcx, [rbp+var_20]
0x18005bc1a  mov     ebx, eax
0x18005bc1c  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18005bc21  test    ebx, ebx
0x18005bc23  jnz     short loc_18005BC54
0x18005bc25  mov     rcx, [rbp+arg_0]; hKey
0x18005bc29  mov     rdx, r14; lpSubKey
0x18005bc2c  call    cs:__imp_RegDeleteTreeW
0x18005bc32  test    eax, eax
0x18005bc34  jz      short loc_18005BC4A
0x18005bc36  mov     rcx, [rbp+38h]; this
0x18005bc3a  mov     r9d, eax; char *
0x18005bc3d  mov     r8, r13; unsigned int
0x18005bc40  mov     edx, 913h; void *
0x18005bc45  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18005bc4a  mov     rcx, [rbp+arg_0]; hKey
0x18005bc4e  call    cs:__imp_RegFlushKey
0x18005bc54  lea     rcx, [rbp+arg_0]
0x18005bc58  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005bc5d  lea     rcx, [rbp+lpSubKey]; void *
0x18005bc61  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18005bc66  lea     rcx, [rbp+SourceString]; void *
0x18005bc6a  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18005bc6f  lea     rcx, [rbp+hKey]
0x18005bc73  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005bc78  xor     edx, edx
0x18005bc7a  mov     rcx, rdi
0x18005bc7d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18005bc82  mov     rcx, [rsi]; hKey
0x18005bc85  mov     rdx, r14; lpSubKey
0x18005bc88  call    cs:__imp_RegDeleteTreeW
0x18005bc8e  test    eax, eax
0x18005bc90  jz      short loc_18005BCAA
0x18005bc92  mov     rcx, [rbp+38h]; this
0x18005bc96  mov     r9d, eax; char *
0x18005bc99  mov     r8, r13; unsigned int
0x18005bc9c  mov     edx, 91Dh; void *
0x18005bca1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005bca6  mov     ebx, eax
0x18005bca8  jmp     short loc_18005BCB6
0x18005bcaa  mov     rcx, [rsi]; hKey
0x18005bcad  call    cs:__imp_RegFlushKey
0x18005bcb3  mov     ebx, r12d
0x18005bcb6  lea     rcx, [rbp+var_28]
0x18005bcba  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18005bcbf  lea     rcx, [rbp+var_30]; void *
0x18005bcc3  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18005bcc8  mov     eax, ebx
0x18005bcca  mov     rbx, [rsp+70h+arg_8]
0x18005bcd2  add     rsp, 70h
0x18005bcd6  pop     r15
0x18005bcd8  pop     r14
0x18005bcda  pop     r13
0x18005bcdc  pop     r12
0x18005bcde  pop     rdi
0x18005bcdf  pop     rsi
0x18005bce0  pop     rbp
0x18005bce1  retn
```
