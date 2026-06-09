# DcaMgr::DeviceCredential::SetDeviceOpaqueBlob(ushort const *,uchar const *,ulong)

- ea: `0x1800a3edc`
- end: `0x1800a41a3`
- name: `?SetDeviceOpaqueBlob@DeviceCredential@DcaMgr@@SAJPEBGPEBEK@Z`
- size: `711`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, const unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18009fd80`

## callees

- `0x18000782c`
- `0x18000926c`
- `0x1800281e0`
- `0x1800323d0`
- `0x180032c20`
- `0x180048304`
- `0x1800535f4`
- `0x180069998`
- `0x180069c28`
- `0x180097c6c`
- `0x180097cb4`
- `0x180098cfc`
- `0x1800a3edc`
- `0x1800a41ac`
- `0x1800a6408`
- `0x1800a6d30`
- `0x1800a7b74`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800a4133`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800a4133`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a4109`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a4109`

## string_xrefs

- `0x1800a3f62`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x1800a3fab`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x1800a402d`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x1800a40b6`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x1800a4117`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x1800a4182`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`

## pseudocode

```c
__int64 __fastcall DcaMgr::DeviceCredential::SetDeviceOpaqueBlob(LPCWSTR lpSubKey, const unsigned __int8 *a2, int a3)
{
  int UserSidAndPackageInfoFromToken; // ebx
  HKEY *v7; // r8
  __int64 v8; // rdx
  int v9; // ecx
  const unsigned __int16 *v10; // r9
  unsigned __int64 v11; // r9
  __int64 v12; // rdx
  int v13; // eax
  int v14; // ecx
  __int64 v15; // rcx
  BYTE *v16; // rdx
  unsigned int v17; // eax
  __int64 v18; // rcx
  BYTE *v19; // rdx
  int lpData; // [rsp+20h] [rbp-49h]
  int lpDataa; // [rsp+20h] [rbp-49h]
  unsigned int lpDatab; // [rsp+20h] [rbp-49h]
  BYTE *v24; // [rsp+30h] [rbp-39h] BYREF
  HANDLE TokenHandle; // [rsp+38h] [rbp-31h] BYREF
  unsigned __int16 *v26; // [rsp+40h] [rbp-29h] BYREF
  HKEY v27; // [rsp+48h] [rbp-21h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-19h] BYREF
  void *p_hKey; // [rsp+58h] [rbp-11h] BYREF
  unsigned __int16 v30[4]; // [rsp+60h] [rbp-9h] BYREF
  char v31; // [rsp+68h] [rbp-1h]
  void *v32; // [rsp+70h] [rbp+7h] BYREF
  WCHAR *v33; // [rsp+78h] [rbp+Fh] BYREF
  char v34; // [rsp+80h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  DWORD cbData; // [rsp+E8h] [rbp+7Fh] BYREF

  UserSidAndPackageInfoFromToken = ValidateInputString(lpSubKey, 40);
  if ( UserSidAndPackageInfoFromToken < 0 )
  {
    v8 = 1495;
LABEL_27:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
      (const char *)(unsigned int)UserSidAndPackageInfoFromToken,
      lpData);
    return (unsigned int)UserSidAndPackageInfoFromToken;
  }
  if ( !a2 || (unsigned int)(a3 - 1) > 0xFFF )
  {
    UserSidAndPackageInfoFromToken = -2147024809;
    v8 = 1499;
    goto LABEL_27;
  }
  hKey = 0;
  p_hKey = &hKey;
  *(_QWORD *)v30 = 0;
  v31 = 1;
  UserSidAndPackageInfoFromToken = DcaMgr::OpenDeviceRegKey(lpSubKey, v30, v7);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
  if ( UserSidAndPackageInfoFromToken >= 0 )
  {
    TokenHandle = 0;
    p_hKey = &TokenHandle;
    *(_QWORD *)v30 = 0;
    v31 = 1;
    UserSidAndPackageInfoFromToken = OpenCallerImpersonationToken(v9, (HANDLE *)v30);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&p_hKey);
    if ( UserSidAndPackageInfoFromToken < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5E3,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
        (const char *)(unsigned int)UserSidAndPackageInfoFromToken,
        lpData);
LABEL_9:
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      goto LABEL_25;
    }
    v32 = &v26;
    v27 = 0;
    p_hKey = &v27;
    v26 = 0;
    v33 = 0;
    v34 = 1;
    *(_QWORD *)v30 = 0;
    v31 = 1;
    UserSidAndPackageInfoFromToken = GetUserSidAndPackageInfoFromToken(TokenHandle, v30, &v33, 0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_hKey);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v32);
    if ( UserSidAndPackageInfoFromToken >= 0 )
    {
      v13 = DcaMgr::ValidateOwnership(hKey, v27, v26, v10);
      UserSidAndPackageInfoFromToken = v13;
      if ( v13 >= 0 )
      {
        v24 = 0;
        v32 = &v24;
        cbData = 0;
        v33 = 0;
        LOBYTE(v14) = 1;
        v34 = 1;
        UserSidAndPackageInfoFromToken = DpapiProtectUnprotect(
                                           v14,
                                           (_DWORD)a2,
                                           a3,
                                           (unsigned int)&v33,
                                           (__int64)&cbData);
        wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>(&v32);
        if ( UserSidAndPackageInfoFromToken >= 0 )
        {
          v17 = RegSetValueExW(hKey, L"OpaqueBlob", 0, 3u, v24, cbData);
          if ( !v17 )
          {
            RegFlushKey(hKey);
            v19 = v24;
            v24 = 0;
            if ( v19 )
              wil::hlocal_secure_deleter::operator()<unsigned char>(v18, v19);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v26);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v27);
            wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
            UserSidAndPackageInfoFromToken = 0;
            goto LABEL_25;
          }
          UserSidAndPackageInfoFromToken = wil::details::in1diag3::Return_Win32(
                                             retaddr,
                                             (void *)0x600,
                                             (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\device"
                                                           "credentialclass.cpp",
                                             (const char *)v17,
                                             lpDatab);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5F8,
            (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
            (const char *)(unsigned int)UserSidAndPackageInfoFromToken,
            lpDataa);
        }
        v16 = v24;
        v24 = 0;
        if ( v16 )
          wil::hlocal_secure_deleter::operator()<unsigned char>(v15, v16);
        goto LABEL_13;
      }
      v11 = (unsigned int)v13;
      v12 = 1519;
    }
    else
    {
      v11 = (unsigned int)UserSidAndPackageInfoFromToken;
      v12 = 1514;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
      (const char *)v11,
      lpData);
LABEL_13:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v26);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v27);
    goto LABEL_9;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5DE,
    (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
    (const char *)(unsigned int)UserSidAndPackageInfoFromToken,
    lpData);
LABEL_25:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)UserSidAndPackageInfoFromToken;
}

```

## disassembly

```asm
0x1800a3edc  push    rbp
0x1800a3ede  push    rbx
0x1800a3edf  push    rsi
0x1800a3ee0  push    rdi
0x1800a3ee1  push    r14
0x1800a3ee3  push    r15
0x1800a3ee5  lea     rbp, [rsp-2Fh]
0x1800a3eea  sub     rsp, 98h
0x1800a3ef1  mov     rsi, rdx
0x1800a3ef4  mov     r14d, r8d
0x1800a3ef7  mov     edx, 28h ; '('
0x1800a3efc  mov     rdi, rcx
0x1800a3eff  call    ValidateInputString
0x1800a3f04  xor     r15d, r15d
0x1800a3f07  mov     ebx, eax
0x1800a3f09  test    eax, eax
0x1800a3f0b  jns     short loc_1800A3F17
0x1800a3f0d  mov     edx, 5D7h
0x1800a3f12  jmp     loc_1800A417E
0x1800a3f17  test    rsi, rsi
0x1800a3f1a  jz      loc_1800A4174
0x1800a3f20  lea     eax, [r14-1]
0x1800a3f24  cmp     eax, 0FFFh
0x1800a3f29  ja      loc_1800A4174
0x1800a3f2f  lea     rax, [rbp+57h+hKey]
0x1800a3f33  mov     [rbp+57h+hKey], r15
0x1800a3f37  lea     rdx, [rbp+57h+var_60]; unsigned __int16 *
0x1800a3f3b  mov     [rbp+57h+var_68], rax
0x1800a3f3f  mov     rcx, rdi; lpSubKey
0x1800a3f42  mov     qword ptr [rbp+57h+var_60], r15
0x1800a3f46  mov     [rbp+57h+var_58], 1
0x1800a3f4a  call    ?OpenDeviceRegKey@DcaMgr@@YAJPEBGPEAPEAUHKEY__@@@Z; DcaMgr::OpenDeviceRegKey(ushort const *,HKEY__ * *)
0x1800a3f4f  lea     rcx, [rbp+57h+var_68]
0x1800a3f53  mov     ebx, eax
0x1800a3f55  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800a3f5a  test    ebx, ebx
0x1800a3f5c  jns     short loc_1800A3F7B
0x1800a3f5e  mov     rcx, [rbp+5Fh]; this
0x1800a3f62  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\devicecredential"...
0x1800a3f69  mov     r9d, ebx; char *
0x1800a3f6c  mov     edx, 5DEh; void *
0x1800a3f71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3f76  jmp     loc_1800A4169
0x1800a3f7b  lea     rax, [rbp+57h+TokenHandle]
0x1800a3f7f  mov     [rbp+57h+TokenHandle], r15
0x1800a3f83  lea     rdx, [rbp+57h+var_60]
0x1800a3f87  mov     [rbp+57h+var_68], rax
0x1800a3f8b  mov     qword ptr [rbp+57h+var_60], r15
0x1800a3f8f  mov     [rbp+57h+var_58], 1
0x1800a3f93  call    OpenCallerImpersonationToken
0x1800a3f98  lea     rcx, [rbp+57h+var_68]
0x1800a3f9c  mov     ebx, eax
0x1800a3f9e  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x1800a3fa3  test    ebx, ebx
0x1800a3fa5  jns     short loc_1800A3FCD
0x1800a3fa7  mov     rcx, [rbp+5Fh]; this
0x1800a3fab  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\devicecredential"...
0x1800a3fb2  mov     r9d, ebx; char *
0x1800a3fb5  mov     edx, 5E3h; void *
0x1800a3fba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3fbf  lea     rcx, [rbp+57h+TokenHandle]
0x1800a3fc3  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800a3fc8  jmp     loc_1800A4169
0x1800a3fcd  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800a3fd1  lea     rax, [rbp+57h+var_80]
0x1800a3fd5  mov     [rbp+57h+var_50], rax
0x1800a3fd9  lea     r8, [rbp+57h+var_48]
0x1800a3fdd  lea     rax, [rbp+57h+var_78]
0x1800a3fe1  mov     [rbp+57h+var_78], r15
0x1800a3fe5  xor     r9d, r9d
0x1800a3fe8  mov     [rbp+57h+var_68], rax
0x1800a3fec  lea     rdx, [rbp+57h+var_60]
0x1800a3ff0  mov     [rbp+57h+var_80], r15
0x1800a3ff4  mov     [rbp+57h+var_48], r15
0x1800a3ff8  mov     [rbp+57h+var_40], 1
0x1800a3ffc  mov     qword ptr [rbp+57h+var_60], r15
0x1800a4000  mov     [rbp+57h+var_58], 1
0x1800a4004  call    GetUserSidAndPackageInfoFromToken
0x1800a4009  lea     rcx, [rbp+57h+var_68]
0x1800a400d  mov     ebx, eax
0x1800a400f  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x1800a4014  lea     rcx, [rbp+57h+var_50]
0x1800a4018  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x1800a401d  test    ebx, ebx
0x1800a401f  jns     short loc_1800A4050
0x1800a4021  mov     r9d, ebx; char *
0x1800a4024  mov     edx, 5EAh; void *
0x1800a4029  mov     rcx, [rbp+5Fh]; this
0x1800a402d  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\devicecredential"...
0x1800a4034  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a4039  lea     rcx, [rbp+57h+var_80]; void *
0x1800a403d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800a4042  lea     rcx, [rbp+57h+var_78]; void *
0x1800a4046  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800a404b  jmp     loc_1800A3FBF
0x1800a4050  mov     r8, [rbp+57h+var_80]; unsigned __int16 *
0x1800a4054  mov     rdx, [rbp+57h+var_78]; HKEY
0x1800a4058  mov     rcx, [rbp+57h+hKey]; hkey
0x1800a405c  call    ?ValidateOwnership@DcaMgr@@YAJPEAUHKEY__@@PEBG1@Z; DcaMgr::ValidateOwnership(HKEY__ *,ushort const *,ushort const *)
0x1800a4061  mov     ebx, eax
0x1800a4063  test    eax, eax
0x1800a4065  jns     short loc_1800A4071
0x1800a4067  mov     r9d, eax
0x1800a406a  mov     edx, 5EFh
0x1800a406f  jmp     short loc_1800A4029
0x1800a4071  lea     rax, [rbp+57h+var_90]
0x1800a4075  mov     [rbp+57h+var_90], r15
0x1800a4079  mov     [rbp+57h+var_50], rax
0x1800a407d  lea     r9, [rbp+57h+var_48]
0x1800a4081  lea     rax, [rbp+57h+arg_18]
0x1800a4085  mov     [rbp+57h+arg_18], r15d
0x1800a4089  mov     r8d, r14d
0x1800a408c  mov     [rsp+0C0h+lpData], rax; int
0x1800a4091  mov     rdx, rsi
0x1800a4094  mov     [rbp+57h+var_48], r15
0x1800a4098  mov     cl, 1
0x1800a409a  mov     [rbp+57h+var_40], 1
0x1800a409e  call    DpapiProtectUnprotect
0x1800a40a3  lea     rcx, [rbp+57h+var_50]
0x1800a40a7  mov     ebx, eax
0x1800a40a9  call    ??1?$out_param_t@V?$unique_ptr@EUhlocal_secure_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>(void)
0x1800a40ae  test    ebx, ebx
0x1800a40b0  jns     short loc_1800A40E5
0x1800a40b2  mov     rcx, [rbp+5Fh]; this
0x1800a40b6  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\devicecredential"...
0x1800a40bd  mov     r9d, ebx; char *
0x1800a40c0  mov     edx, 5F8h; void *
0x1800a40c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a40ca  mov     rdx, [rbp+57h+var_90]
0x1800a40ce  mov     [rbp+57h+var_90], r15
0x1800a40d2  test    rdx, rdx
0x1800a40d5  jz      loc_1800A4039
0x1800a40db  call    ??$?RE@hlocal_secure_deleter@wil@@QEBAXPEAE@Z; wil::hlocal_secure_deleter::operator()<uchar>(uchar *)
0x1800a40e0  jmp     loc_1800A4039
0x1800a40e5  mov     rdx, [rbp+57h+var_90]
0x1800a40e9  mov     r9d, 3; dwType
0x1800a40ef  mov     eax, [rbp+57h+arg_18]
0x1800a40f2  xor     r8d, r8d; Reserved
0x1800a40f5  mov     rcx, [rbp+57h+hKey]; hKey
0x1800a40f9  mov     [rsp+0C0h+cbData], eax; cbData
0x1800a40fd  mov     [rsp+0C0h+lpData], rdx; unsigned int
0x1800a4102  lea     rdx, aOpaqueblob; "OpaqueBlob"
0x1800a4109  call    cs:__imp_RegSetValueExW
0x1800a410f  test    eax, eax
0x1800a4111  jz      short loc_1800A412F
0x1800a4113  mov     rcx, [rbp+5Fh]; this
0x1800a4117  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\devicecredential"...
0x1800a411e  mov     r9d, eax; char *
0x1800a4121  mov     edx, 600h; void *
0x1800a4126  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a412b  mov     ebx, eax
0x1800a412d  jmp     short loc_1800A40CA
0x1800a412f  mov     rcx, [rbp+57h+hKey]; hKey
0x1800a4133  call    cs:__imp_RegFlushKey
0x1800a4139  mov     rdx, [rbp+57h+var_90]
0x1800a413d  mov     [rbp+57h+var_90], r15
0x1800a4141  test    rdx, rdx
0x1800a4144  jz      short loc_1800A414B
0x1800a4146  call    ??$?RE@hlocal_secure_deleter@wil@@QEBAXPEAE@Z; wil::hlocal_secure_deleter::operator()<uchar>(uchar *)
0x1800a414b  lea     rcx, [rbp+57h+var_80]; void *
0x1800a414f  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800a4154  lea     rcx, [rbp+57h+var_78]; void *
0x1800a4158  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800a415d  lea     rcx, [rbp+57h+TokenHandle]
0x1800a4161  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800a4166  mov     ebx, r15d
0x1800a4169  lea     rcx, [rbp+57h+hKey]
0x1800a416d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a4172  jmp     short loc_1800A4191
0x1800a4174  mov     ebx, 80070057h
0x1800a4179  mov     edx, 5DBh; void *
0x1800a417e  mov     rcx, [rbp+5Fh]; this
0x1800a4182  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\devicecredential"...
0x1800a4189  mov     r9d, ebx; char *
0x1800a418c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a4191  mov     eax, ebx
0x1800a4193  add     rsp, 98h
0x1800a419a  pop     r15
0x1800a419c  pop     r14
0x1800a419e  pop     rdi
0x1800a419f  pop     rsi
0x1800a41a0  pop     rbx
0x1800a41a1  pop     rbp
0x1800a41a2  retn
```
