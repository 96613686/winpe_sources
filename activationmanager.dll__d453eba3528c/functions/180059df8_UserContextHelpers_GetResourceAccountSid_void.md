# UserContextHelpers::GetResourceAccountSid(void)

- ea: `0x180059df8`
- end: `0x18005a028`
- name: `?GetResourceAccountSid@UserContextHelpers@@AEAAJXZ`
- size: `560`
- prototype: `__int64 __fastcall(UserContextHelpers *__hidden this)`
- caller_count: `4`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000dca0`
- `0x18000e018`
- `0x180011ad0`
- `0x180029270`

## callees

- `0x18000b5c0`
- `0x180027c60`
- `0x180036ad4`
- `0x180038c70`
- `0x18003ab00`
- `0x180044408`
- `0x180059cd8`
- `0x180059df8`
- `0x18005a258`
- `0x18007bd70`
- `0x18007bddc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180059ec5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180059f34`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180059ec5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180059f34`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180059e72`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180059e72`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180059fb0`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180059fb0`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180059e0b`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180059e0b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180059f88`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180059f88`

## pseudocode

```c
__int64 __fastcall UserContextHelpers::GetResourceAccountSid(UserContextHelpers *this)
{
  char *v1; // rsi
  __int64 v2; // rdx
  __int64 v3; // rcx
  LSTATUS PersistedRegistryLocationAlloc; // eax
  unsigned int LastError; // ebx
  __int64 v6; // rdx
  const WCHAR *v7; // rbx
  LSTATUS v8; // eax
  LSTATUS v9; // edi
  BOOL v10; // ebx
  const char *v11; // r9
  __int64 v12; // rdx
  int phkResult; // [rsp+20h] [rbp-38h]
  int phkResulta; // [rsp+20h] [rbp-38h]
  LPCWSTR lpSubKey; // [rsp+30h] [rbp-28h] BYREF
  PSID *p_pSourceSid; // [rsp+38h] [rbp-20h] BYREF
  PSID Sid; // [rsp+40h] [rbp-18h] BYREF
  char v19; // [rsp+48h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+20h]
  DWORD cbData; // [rsp+80h] [rbp+28h] BYREF
  LPBYTE lpData; // [rsp+88h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+90h] [rbp+38h] BYREF
  PSID pSourceSid; // [rsp+98h] [rbp+40h] BYREF

  v1 = (char *)this + 4;
  if ( !IsValidSid((char *)this + 4) )
  {
    hKey = 0;
    lpSubKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &lpSubKey,
      0);
    PersistedRegistryLocationAlloc = GetPersistedRegistryLocationAlloc(v3, v2, &lpSubKey);
    LastError = PersistedRegistryLocationAlloc;
    if ( PersistedRegistryLocationAlloc < 0 )
    {
      v6 = 258;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v6,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\usercontexthelpers.cpp",
        (const char *)(unsigned int)PersistedRegistryLocationAlloc,
        phkResult);
LABEL_19:
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpSubKey);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return LastError;
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    PersistedRegistryLocationAlloc = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x2001Fu, &hKey);
    LastError = PersistedRegistryLocationAlloc;
    if ( PersistedRegistryLocationAlloc < 0 )
    {
      v6 = 259;
      goto LABEL_6;
    }
    cbData = 0;
    PersistedRegistryLocationAlloc = RegQueryValueExW(hKey, L"SID", 0, 0, 0, &cbData);
    LastError = PersistedRegistryLocationAlloc;
    if ( PersistedRegistryLocationAlloc < 0 )
    {
      v6 = 262;
      goto LABEL_6;
    }
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &lpData,
      0,
      (unsigned __int64)cbData >> 1);
    v7 = (const WCHAR *)lpData;
    if ( !lpData )
    {
      LastError = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x109,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\usercontexthelpers.cpp",
        (const char *)0x8007000ELL,
        phkResult);
LABEL_18:
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpData);
      goto LABEL_19;
    }
    v8 = RegQueryValueExW(hKey, L"SID", 0, 0, lpData, &cbData);
    v9 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10A,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\usercontexthelpers.cpp",
        (const char *)(unsigned int)v8,
        phkResulta);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpData);
      LastError = v9;
      goto LABEL_19;
    }
    pSourceSid = 0;
    p_pSourceSid = &pSourceSid;
    Sid = 0;
    v19 = 1;
    v10 = ConvertStringSidToSidW(v7, &Sid);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&p_pSourceSid);
    if ( !v10 )
    {
      v12 = 269;
LABEL_17:
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v12,
                    (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\usercontexthelpers.cpp",
                    v11);
      wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pSourceSid);
      goto LABEL_18;
    }
    if ( !CopySid(0x44u, v1, pSourceSid) )
    {
      v12 = 270;
      goto LABEL_17;
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pSourceSid);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpData);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpSubKey);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  }
  return 0;
}

```

## disassembly

```asm
0x180059df8  push    rbp
0x180059dfa  push    rbx
0x180059dfb  push    rsi
0x180059dfc  push    rdi
0x180059dfd  mov     rbp, rsp
0x180059e00  sub     rsp, 58h
0x180059e04  lea     rsi, [rcx+4]
0x180059e08  mov     rcx, rsi; pSid
0x180059e0b  call    cs:__imp_IsValidSid
0x180059e11  test    eax, eax
0x180059e13  jnz     loc_18005A01D
0x180059e19  xor     edx, edx
0x180059e1b  mov     [rbp+hKey], 0
0x180059e23  lea     rcx, [rbp+lpSubKey]
0x180059e27  mov     [rbp+lpSubKey], 0
0x180059e2f  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180059e34  lea     r8, [rbp+lpSubKey]
0x180059e38  call    GetPersistedRegistryLocationAlloc
0x180059e3d  mov     ebx, eax
0x180059e3f  test    eax, eax
0x180059e41  jns     short loc_180059E4A
0x180059e43  mov     edx, 102h
0x180059e48  jmp     short loc_180059E83
0x180059e4a  xor     edx, edx
0x180059e4c  lea     rcx, [rbp+hKey]
0x180059e50  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180059e55  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180059e59  lea     rax, [rbp+hKey]
0x180059e5d  mov     r9d, 2001Fh; samDesired
0x180059e63  mov     [rsp+58h+phkResult], rax; int
0x180059e68  xor     r8d, r8d; ulOptions
0x180059e6b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180059e72  call    cs:__imp_RegOpenKeyExW
0x180059e78  mov     ebx, eax
0x180059e7a  test    eax, eax
0x180059e7c  jns     short loc_180059E9B
0x180059e7e  mov     edx, 103h; void *
0x180059e83  mov     rcx, [rbp+20h]; this
0x180059e87  lea     r8, aOnecoreuapBase_30; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180059e8e  mov     r9d, eax; char *
0x180059e91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059e96  jmp     loc_180059FE3
0x180059e9b  mov     rcx, [rbp+hKey]; hKey
0x180059e9f  lea     rax, [rbp+cbData]
0x180059ea3  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180059ea8  lea     rdx, aSid; "SID"
0x180059eaf  xor     r9d, r9d; lpType
0x180059eb2  mov     [rsp+58h+phkResult], 0; int
0x180059ebb  xor     r8d, r8d; lpReserved
0x180059ebe  mov     [rbp+cbData], 0
0x180059ec5  call    cs:__imp_RegQueryValueExW
0x180059ecb  mov     ebx, eax
0x180059ecd  test    eax, eax
0x180059ecf  jns     short loc_180059ED8
0x180059ed1  mov     edx, 106h
0x180059ed6  jmp     short loc_180059E83
0x180059ed8  mov     r8d, [rbp+cbData]
0x180059edc  lea     rcx, [rbp+lpData]
0x180059ee0  shr     r8, 1
0x180059ee3  xor     edx, edx
0x180059ee5  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180059eea  mov     rbx, [rbp+lpData]
0x180059eee  test    rbx, rbx
0x180059ef1  jnz     short loc_180059F15
0x180059ef3  mov     rcx, [rbp+20h]; this
0x180059ef7  lea     r8, aOnecoreuapBase_30; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180059efe  mov     ebx, 8007000Eh
0x180059f03  mov     edx, 109h; void *
0x180059f08  mov     r9d, ebx; char *
0x180059f0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059f10  jmp     loc_180059FDA
0x180059f15  mov     rcx, [rbp+hKey]; hKey
0x180059f19  lea     rax, [rbp+cbData]
0x180059f1d  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180059f22  lea     rdx, aSid; "SID"
0x180059f29  xor     r9d, r9d; lpType
0x180059f2c  mov     [rsp+58h+phkResult], rbx; int
0x180059f31  xor     r8d, r8d; lpReserved
0x180059f34  call    cs:__imp_RegQueryValueExW
0x180059f3a  mov     edi, eax
0x180059f3c  test    eax, eax
0x180059f3e  jns     short loc_180059F65
0x180059f40  mov     rcx, [rbp+20h]; this
0x180059f44  lea     r8, aOnecoreuapBase_30; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180059f4b  mov     r9d, eax; char *
0x180059f4e  mov     edx, 10Ah; void *
0x180059f53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059f58  lea     rcx, [rbp+lpData]
0x180059f5c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180059f61  mov     ebx, edi
0x180059f63  jmp     short loc_180059FE3
0x180059f65  lea     rax, [rbp+pSourceSid]
0x180059f69  mov     [rbp+pSourceSid], 0
0x180059f71  lea     rdx, [rbp+Sid]; Sid
0x180059f75  mov     [rbp+var_20], rax
0x180059f79  mov     rcx, rbx; StringSid
0x180059f7c  mov     [rbp+Sid], 0
0x180059f84  mov     [rbp+var_10], 1
0x180059f88  call    cs:__imp_ConvertStringSidToSidW
0x180059f8e  lea     rcx, [rbp+var_20]
0x180059f92  mov     ebx, eax
0x180059f94  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x180059f99  test    ebx, ebx
0x180059f9b  jnz     short loc_180059FA4
0x180059f9d  mov     edx, 10Dh
0x180059fa2  jmp     short loc_180059FBF
0x180059fa4  mov     r8, [rbp+pSourceSid]; pSourceSid
0x180059fa8  mov     rdx, rsi; pDestinationSid
0x180059fab  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x180059fb0  call    cs:__imp_CopySid
0x180059fb6  test    eax, eax
0x180059fb8  jnz     short loc_180059FF9
0x180059fba  mov     edx, 10Eh; void *
0x180059fbf  mov     rcx, [rbp+20h]; this
0x180059fc3  lea     r8, aOnecoreuapBase_30; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180059fca  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180059fcf  lea     rcx, [rbp+pSourceSid]
0x180059fd3  mov     ebx, eax
0x180059fd5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180059fda  lea     rcx, [rbp+lpData]
0x180059fde  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180059fe3  lea     rcx, [rbp+lpSubKey]
0x180059fe7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180059fec  lea     rcx, [rbp+hKey]
0x180059ff0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180059ff5  mov     eax, ebx
0x180059ff7  jmp     short loc_18005A01F
0x180059ff9  lea     rcx, [rbp+pSourceSid]
0x180059ffd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18005a002  lea     rcx, [rbp+lpData]
0x18005a006  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18005a00b  lea     rcx, [rbp+lpSubKey]
0x18005a00f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18005a014  lea     rcx, [rbp+hKey]
0x18005a018  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005a01d  xor     eax, eax
0x18005a01f  add     rsp, 58h
0x18005a023  pop     rdi
0x18005a024  pop     rsi
0x18005a025  pop     rbx
0x18005a026  pop     rbp
0x18005a027  retn
```
