# DcaMgr::DeviceCredential::Deprovision(ushort const *)

- ea: `0x180054074`
- end: `0x1800542f8`
- name: `?Deprovision@DeviceCredential@DcaMgr@@SAJPEBG@Z`
- size: `644`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `4`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18004fe40`
- `0x180053ed0`
- `0x18009f170`
- `0x1800a2220`

## callees

- `0x18000782c`
- `0x18000926c`
- `0x1800281e0`
- `0x1800323d0`
- `0x180032c20`
- `0x18004b7c4`
- `0x1800535f4`
- `0x180054074`
- `0x18005b9e0`
- `0x180097c6c`
- `0x180097cb4`
- `0x1800a41ac`
- `0x1800a6d30`
- `0x1800a7b74`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800540f3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180054139`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800540f3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180054139`

## string_xrefs

- `0x180054099`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x18005418d`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x18005421d`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x1800542e4`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall DcaMgr::DeviceCredential::Deprovision(LPCWSTR lpSubKey)
{
  int v2; // eax
  int UserSidAndPackageInfoFromToken; // ebx
  int v4; // ecx
  const unsigned __int16 *v5; // r9
  unsigned __int64 v6; // r9
  __int64 v7; // rdx
  int v8; // eax
  RTL_SRWLOCK *v9; // rax
  int v10; // eax
  bool v12; // sf
  int phkResult; // [rsp+20h] [rbp-50h]
  int phkResulta; // [rsp+20h] [rbp-50h]
  HKEY hkey; // [rsp+30h] [rbp-40h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-38h] BYREF
  void *p_hKey; // [rsp+40h] [rbp-30h] BYREF
  HKEY v18; // [rsp+48h] [rbp-28h] BYREF
  char v19; // [rsp+50h] [rbp-20h]
  unsigned __int16 **v20; // [rsp+58h] [rbp-18h] BYREF
  WCHAR *v21; // [rsp+60h] [rbp-10h] BYREF
  char v22; // [rsp+68h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  HANDLE TokenHandle; // [rsp+98h] [rbp+28h] BYREF
  unsigned __int16 *v25; // [rsp+A0h] [rbp+30h] BYREF
  HKEY v26; // [rsp+A8h] [rbp+38h] BYREF

  v2 = ValidateInputString(lpSubKey, 40);
  UserSidAndPackageInfoFromToken = v2;
  if ( v2 >= 0 )
  {
    hKey = 0;
    hkey = 0;
    p_hKey = &hKey;
    v18 = 0;
    v19 = 1;
    UserSidAndPackageInfoFromToken = RegOpenKeyExW(
                                       HKEY_LOCAL_MACHINE,
                                       L"Software\\Microsoft\\Windows\\CurrentVersion\\SecondaryAuthFactor\\Devices",
                                       0,
                                       0xF003Fu,
                                       &v18);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
    if ( UserSidAndPackageInfoFromToken
      || (p_hKey = &hkey,
          v18 = 0,
          v19 = 1,
          UserSidAndPackageInfoFromToken = RegOpenKeyExW(hKey, lpSubKey, 0, 0xF003Fu, &v18),
          wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey),
          UserSidAndPackageInfoFromToken) )
    {
      if ( UserSidAndPackageInfoFromToken != 2 )
      {
        v12 = UserSidAndPackageInfoFromToken < 0;
        if ( UserSidAndPackageInfoFromToken > 0 )
        {
          UserSidAndPackageInfoFromToken = (unsigned __int16)UserSidAndPackageInfoFromToken | 0x80070000;
          v12 = UserSidAndPackageInfoFromToken < 0;
        }
        if ( v12 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x653,
            (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
            (const char *)(unsigned int)UserSidAndPackageInfoFromToken,
            phkResulta);
        goto LABEL_17;
      }
    }
    else
    {
      TokenHandle = 0;
      p_hKey = &TokenHandle;
      v18 = 0;
      v19 = 1;
      UserSidAndPackageInfoFromToken = OpenCallerImpersonationToken(v4, (HANDLE *)&v18);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&p_hKey);
      if ( UserSidAndPackageInfoFromToken < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x65C,
          (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
          (const char *)(unsigned int)UserSidAndPackageInfoFromToken,
          phkResulta);
LABEL_7:
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
LABEL_17:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return (unsigned int)UserSidAndPackageInfoFromToken;
      }
      v26 = 0;
      v25 = 0;
      v20 = &v25;
      v21 = 0;
      v22 = 1;
      p_hKey = &v26;
      v18 = 0;
      v19 = 1;
      UserSidAndPackageInfoFromToken = GetUserSidAndPackageInfoFromToken(TokenHandle, &v18, &v21, 0);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_hKey);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v20);
      if ( UserSidAndPackageInfoFromToken < 0 )
      {
        v6 = (unsigned int)UserSidAndPackageInfoFromToken;
        v7 = 1635;
LABEL_10:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v7,
          (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
          (const char *)v6,
          phkResulta);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v25);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v26);
        goto LABEL_7;
      }
      v8 = DcaMgr::ValidateOwnership(hkey, v26, v25, v5);
      UserSidAndPackageInfoFromToken = v8;
      if ( v8 < 0 )
      {
        v6 = (unsigned int)v8;
        v7 = 1640;
        goto LABEL_10;
      }
      v9 = (RTL_SRWLOCK *)DcaMgr::DeviceCredentialMgr::Instance();
      v10 = DcaMgr::DeviceCredentialMgr::DeprovisionDevice(v9, &hKey, &hkey, lpSubKey);
      UserSidAndPackageInfoFromToken = v10;
      if ( v10 < 0 )
      {
        v6 = (unsigned int)v10;
        v7 = 1645;
        goto LABEL_10;
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v25);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v26);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    }
    UserSidAndPackageInfoFromToken = 0;
    goto LABEL_17;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x63B,
    (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
    (const char *)(unsigned int)v2,
    phkResult);
  return (unsigned int)UserSidAndPackageInfoFromToken;
}

```

## disassembly

```asm
0x180054074  push    rbp
0x180054076  push    rbx
0x180054077  push    rdi
0x180054078  mov     rbp, rsp
0x18005407b  sub     rsp, 70h
0x18005407f  mov     rdi, rcx
0x180054082  mov     edx, 28h ; '('
0x180054087  call    ValidateInputString
0x18005408c  mov     ebx, eax
0x18005408e  test    eax, eax
0x180054090  jns     short loc_1800540AF
0x180054092  mov     rcx, [rbp+18h]; this
0x180054096  mov     r9d, eax; char *
0x180054099  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\devicecredential"...
0x1800540a0  mov     edx, 63Bh; void *
0x1800540a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800540aa  jmp     loc_1800542BD
0x1800540af  mov     [rbp+hKey], 0
0x1800540b7  mov     [rbp+hkey], 0
0x1800540bf  lea     rax, [rbp+hKey]
0x1800540c3  mov     [rbp+var_30], rax
0x1800540c7  mov     [rbp+var_28], 0
0x1800540cf  mov     [rbp+var_20], 1
0x1800540d3  lea     rax, [rbp+var_28]
0x1800540d7  mov     qword ptr [rsp+70h+phkResult], rax; int
0x1800540dc  mov     r9d, 0F003Fh; samDesired
0x1800540e2  xor     r8d, r8d; ulOptions
0x1800540e5  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800540ec  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800540f3  call    cs:__imp_RegOpenKeyExW
0x1800540f9  mov     ebx, eax
0x1800540fb  lea     rcx, [rbp+var_30]
0x1800540ff  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180054104  test    ebx, ebx
0x180054106  jnz     loc_1800542C7
0x18005410c  lea     rax, [rbp+hkey]
0x180054110  mov     [rbp+var_30], rax
0x180054114  mov     [rbp+var_28], 0
0x18005411c  mov     [rbp+var_20], 1
0x180054120  lea     rax, [rbp+var_28]
0x180054124  mov     qword ptr [rsp+70h+phkResult], rax; int
0x180054129  mov     r9d, 0F003Fh; samDesired
0x18005412f  xor     r8d, r8d; ulOptions
0x180054132  mov     rdx, rdi; lpSubKey
0x180054135  mov     rcx, [rbp+hKey]; hKey
0x180054139  call    cs:__imp_RegOpenKeyExW
0x18005413f  mov     ebx, eax
0x180054141  lea     rcx, [rbp+var_30]
0x180054145  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18005414a  test    ebx, ebx
0x18005414c  jnz     loc_1800542C7
0x180054152  mov     [rbp+TokenHandle], 0
0x18005415a  lea     rax, [rbp+TokenHandle]
0x18005415e  mov     [rbp+var_30], rax
0x180054162  mov     [rbp+var_28], 0
0x18005416a  mov     [rbp+var_20], 1
0x18005416e  lea     rdx, [rbp+var_28]
0x180054172  call    OpenCallerImpersonationToken
0x180054177  mov     ebx, eax
0x180054179  lea     rcx, [rbp+var_30]
0x18005417d  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x180054182  test    ebx, ebx
0x180054184  jns     short loc_1800541AD
0x180054186  mov     rcx, [rbp+18h]; this
0x18005418a  mov     r9d, ebx; char *
0x18005418d  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\devicecredential"...
0x180054194  mov     edx, 65Ch; void *
0x180054199  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005419e  nop
0x18005419f  lea     rcx, [rbp+TokenHandle]
0x1800541a3  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800541a8  jmp     loc_1800542AA
0x1800541ad  mov     [rbp+arg_18], 0
0x1800541b5  mov     [rbp+arg_10], 0
0x1800541bd  lea     rax, [rbp+arg_10]
0x1800541c1  mov     [rbp+var_18], rax
0x1800541c5  mov     [rbp+var_10], 0
0x1800541cd  mov     [rbp+var_8], 1
0x1800541d1  lea     rax, [rbp+arg_18]
0x1800541d5  mov     [rbp+var_30], rax
0x1800541d9  mov     [rbp+var_28], 0
0x1800541e1  mov     [rbp+var_20], 1
0x1800541e5  xor     r9d, r9d
0x1800541e8  lea     r8, [rbp+var_10]
0x1800541ec  lea     rdx, [rbp+var_28]
0x1800541f0  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800541f4  call    GetUserSidAndPackageInfoFromToken
0x1800541f9  mov     ebx, eax
0x1800541fb  lea     rcx, [rbp+var_30]
0x1800541ff  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180054204  lea     rcx, [rbp+var_18]
0x180054208  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18005420d  test    ebx, ebx
0x18005420f  jns     short loc_180054242
0x180054211  mov     r9d, ebx; char *
0x180054214  mov     edx, 663h; void *
0x180054219  mov     rcx, [rbp+18h]; this
0x18005421d  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\devicecredential"...
0x180054224  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054229  nop
0x18005422a  lea     rcx, [rbp+arg_10]; void *
0x18005422e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180054233  nop
0x180054234  lea     rcx, [rbp+arg_18]; void *
0x180054238  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18005423d  jmp     loc_18005419F
0x180054242  mov     r8, [rbp+arg_10]; unsigned __int16 *
0x180054246  mov     rdx, [rbp+arg_18]; HKEY
0x18005424a  mov     rcx, [rbp+hkey]; hkey
0x18005424e  call    ?ValidateOwnership@DcaMgr@@YAJPEAUHKEY__@@PEBG1@Z; DcaMgr::ValidateOwnership(HKEY__ *,ushort const *,ushort const *)
0x180054253  mov     ebx, eax
0x180054255  test    eax, eax
0x180054257  jns     short loc_180054263
0x180054259  mov     r9d, eax
0x18005425c  mov     edx, 668h
0x180054261  jmp     short loc_180054219
0x180054263  call    ?Instance@DeviceCredentialMgr@DcaMgr@@SAAEAV12@XZ; DcaMgr::DeviceCredentialMgr::Instance(void)
0x180054268  mov     r9, rdi
0x18005426b  lea     r8, [rbp+hkey]
0x18005426f  lea     rdx, [rbp+hKey]
0x180054273  mov     rcx, rax
0x180054276  call    ?DeprovisionDevice@DeviceCredentialMgr@DcaMgr@@QEAAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@0PEBG@Z; DcaMgr::DeviceCredentialMgr::DeprovisionDevice(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,ushort const *)
0x18005427b  mov     ebx, eax
0x18005427d  test    eax, eax
0x18005427f  jns     short loc_18005428B
0x180054281  mov     r9d, eax
0x180054284  mov     edx, 66Dh
0x180054289  jmp     short loc_180054219
0x18005428b  lea     rcx, [rbp+arg_10]; void *
0x18005428f  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180054294  nop
0x180054295  lea     rcx, [rbp+arg_18]; void *
0x180054299  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18005429e  nop
0x18005429f  lea     rcx, [rbp+TokenHandle]
0x1800542a3  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800542a8  xor     ebx, ebx
0x1800542aa  lea     rcx, [rbp+hkey]
0x1800542ae  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800542b3  nop
0x1800542b4  lea     rcx, [rbp+hKey]
0x1800542b8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800542bd  mov     eax, ebx
0x1800542bf  add     rsp, 70h
0x1800542c3  pop     rdi
0x1800542c4  pop     rbx
0x1800542c5  pop     rbp
0x1800542c6  retn
0x1800542c7  cmp     ebx, 2
0x1800542ca  jz      short loc_1800542A8
0x1800542cc  test    ebx, ebx
0x1800542ce  jle     short loc_1800542DB
0x1800542d0  movzx   ebx, bx
0x1800542d3  or      ebx, 80070000h
0x1800542d9  test    ebx, ebx
0x1800542db  jns     short loc_1800542AA
0x1800542dd  mov     rcx, [rbp+18h]; this
0x1800542e1  mov     r9d, ebx; char *
0x1800542e4  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\devicecredential"...
0x1800542eb  mov     edx, 653h; void *
0x1800542f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800542f5  jmp     short loc_1800542AA
```
