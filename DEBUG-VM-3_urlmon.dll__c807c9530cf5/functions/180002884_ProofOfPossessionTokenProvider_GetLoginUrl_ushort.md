# ProofOfPossessionTokenProvider::GetLoginUrl(ushort * *)

- ea: `0x180002884`
- end: `0x180002b2c`
- name: `?GetLoginUrl@ProofOfPossessionTokenProvider@@YAJPEAPEAG@Z`
- size: `680`
- prototype: `__int64 __fastcall(unsigned __int16 **this, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180002f20`
- `0x180003a14`

## callees

- `0x180002884`
- `0x180004dd0`
- `0x180073844`
- `0x18008b74c`
- `0x18009a6a0`
- `0x18009ba00`
- `0x18011a7c4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000295d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000295d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002907`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002907`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002932`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002932`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800029d0`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180002a6b`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800029d0`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180002a6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800028ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002a25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800028ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002a25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002978`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002ab5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002978`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002ab5`

## string_xrefs

- `0x180002991`: `onecoreuap\inetcore\lib\proofofpossessiontokenprovider\proofofpossessiontokenprovider.cxx`
- `0x1800029f6`: `onecoreuap\inetcore\lib\proofofpossessiontokenprovider\proofofpossessiontokenprovider.cxx`
- `0x180002a3b`: `onecoreuap\inetcore\lib\proofofpossessiontokenprovider\proofofpossessiontokenprovider.cxx`
- `0x180002a9e`: `onecoreuap\inetcore\lib\proofofpossessiontokenprovider\proofofpossessiontokenprovider.cxx`
- `0x180002aec`: `onecoreuap\inetcore\lib\proofofpossessiontokenprovider\proofofpossessiontokenprovider.cxx`

## pseudocode

```c
__int64 __fastcall ProofOfPossessionTokenProvider::GetLoginUrl(unsigned __int16 **this, unsigned __int16 **a2)
{
  signed int v3; // edi
  unsigned __int16 *v4; // rax
  unsigned __int16 *v5; // rsi
  BYTE *v6; // rbx
  LSTATUS v7; // eax
  LSTATUS v8; // eax
  __int64 v10; // rcx
  unsigned int PersistedRegistryLocationW; // ebx
  __int64 v12; // rdx
  HKEY v13; // rax
  const char *v14; // r9
  HKEY v15; // rbx
  int v16; // eax
  __int64 v17; // rcx
  int v18; // esi
  bool v19; // sf
  bool v20; // sf
  int TokenProviderLoginUrls; // eax
  int phkResult; // [rsp+20h] [rbp-10h]
  int phkResulta; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  DWORD cbData; // [rsp+58h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+30h] BYREF

  if ( (unsigned int)IsInternetExplorerApp() )
  {
    v3 = -2147024809;
    if ( this )
    {
      *this = 0;
      cbData = 4168;
      v4 = (unsigned __int16 *)CoTaskMemAlloc(0x104Cu);
      v5 = v4;
      if ( v4 )
      {
        v6 = (BYTE *)v4;
        hKey = 0;
        v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\IdentityCRL", 0, 0x101u, &hKey);
        v3 = v7;
        if ( v7 )
        {
          if ( v7 > 0 )
            v3 = (unsigned __int16)v7 | 0x80070000;
        }
        else
        {
          v8 = RegQueryValueExW(hKey, L"LoginUrl", 0, 0, v6, &cbData);
          v3 = v8;
          if ( v8 )
          {
            if ( v8 > 0 )
              v3 = (unsigned __int16)v8 | 0x80070000;
          }
          else
          {
            *(_DWORD *)&v6[2 * ((unsigned __int64)cbData >> 1)] = 0;
            v6 = 0;
            *this = v5;
          }
          RegCloseKey(hKey);
        }
        if ( v6 )
          CoTaskMemFree(v6);
        if ( v3 < 0 )
          goto LABEL_17;
        return 0;
      }
      v3 = -2147024882;
    }
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFB,
      (unsigned int)"onecoreuap\\inetcore\\lib\\proofofpossessiontokenprovider\\proofofpossessiontokenprovider.cxx",
      (const char *)(unsigned int)v3,
      phkResult);
    return (unsigned int)v3;
  }
  cbData = 0;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(L"IdentityCRL", L"Software\\Microsoft\\IdentityCRL", 0, 0);
  if ( PersistedRegistryLocationW != 234 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v10);
    if ( PersistedRegistryLocationW )
    {
      if ( (int)PersistedRegistryLocationW > 0 )
        PersistedRegistryLocationW = (unsigned __int16)PersistedRegistryLocationW | 0x80070000;
      v12 = 269;
    }
    else
    {
      PersistedRegistryLocationW = -2147418113;
      v12 = 268;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\inetcore\\lib\\proofofpossessiontokenprovider\\proofofpossessiontokenprovider.cxx",
      (const char *)PersistedRegistryLocationW,
      (int)&cbData);
    return PersistedRegistryLocationW;
  }
  v13 = (HKEY)CoTaskMemAlloc(cbData);
  hKey = v13;
  v15 = v13;
  if ( !v13 )
    wil::details::in1diag3::_FailFast_NullAlloc(
      retaddr,
      (void *)0x112,
      (unsigned int)"onecoreuap\\inetcore\\lib\\proofofpossessiontokenprovider\\proofofpossessiontokenprovider.cxx",
      v14);
  v16 = GetPersistedRegistryLocationW(L"IdentityCRL", L"Software\\Microsoft\\IdentityCRL", v13, cbData);
  v18 = (unsigned __int16)v16;
  v3 = v16;
  v19 = v16 < 0;
  if ( v16 > 0 )
    v19 = 1;
  if ( v19 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v17);
  v20 = v3 < 0;
  if ( v3 > 0 )
  {
    v3 = v18 | 0x80070000;
    v20 = 1;
  }
  if ( v20 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11E,
      (unsigned int)"onecoreuap\\inetcore\\lib\\proofofpossessiontokenprovider\\proofofpossessiontokenprovider.cxx",
      (const char *)(unsigned int)v3,
      0);
    CoTaskMemFree(v15);
    return (unsigned int)v3;
  }
  TokenProviderLoginUrls = GetTokenProviderLoginUrls(HKEY_LOCAL_MACHINE, (LPCWSTR)v15, L"LoginUrl", this, 0);
  PersistedRegistryLocationW = TokenProviderLoginUrls;
  if ( TokenProviderLoginUrls < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x120,
      (unsigned int)"onecoreuap\\inetcore\\lib\\proofofpossessiontokenprovider\\proofofpossessiontokenprovider.cxx",
      (const char *)(unsigned int)TokenProviderLoginUrls,
      phkResulta);
    wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(&hKey);
    return PersistedRegistryLocationW;
  }
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(&hKey);
  return 0;
}

```

## disassembly

```asm
0x180002884  mov     [rsp-18h+arg_0], rbx
0x180002889  mov     [rsp-18h+arg_18], rsi
0x18000288e  push    rbp
0x18000288f  push    rdi
0x180002890  push    r14
0x180002892  mov     rbp, rsp
0x180002895  sub     rsp, 30h
0x180002899  mov     r14, rcx
0x18000289c  call    ?IsInternetExplorerApp@@YAHXZ; IsInternetExplorerApp(void)
0x1800028a1  test    eax, eax
0x1800028a3  jz      loc_1800029AC
0x1800028a9  mov     edi, 80070057h
0x1800028ae  test    r14, r14
0x1800028b1  jz      loc_18000298D
0x1800028b7  mov     ecx, 104Ch; cb
0x1800028bc  mov     qword ptr [r14], 0
0x1800028c3  mov     [rbp+cbData], 1048h
0x1800028ca  call    cs:__imp_CoTaskMemAlloc
0x1800028d0  mov     rsi, rax
0x1800028d3  test    rax, rax
0x1800028d6  jz      loc_180002988
0x1800028dc  mov     rbx, rax
0x1800028df  mov     [rbp+hKey], 0
0x1800028e7  lea     rax, [rbp+hKey]
0x1800028eb  mov     r9d, 101h; samDesired
0x1800028f1  xor     r8d, r8d; ulOptions
0x1800028f4  mov     [rsp+30h+phkResult], rax; phkResult
0x1800028f9  lea     rdx, SubKey; "Software\\Microsoft\\IdentityCRL"
0x180002900  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180002907  call    cs:__imp_RegOpenKeyExW
0x18000290d  mov     edi, eax
0x18000290f  test    eax, eax
0x180002911  jnz     short loc_180002965
0x180002913  mov     rcx, [rbp+hKey]; hKey
0x180002917  lea     rax, [rbp+cbData]
0x18000291b  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180002920  lea     rdx, ValueName; "LoginUrl"
0x180002927  xor     r9d, r9d; lpType
0x18000292a  mov     [rsp+30h+phkResult], rbx; lpData
0x18000292f  xor     r8d, r8d; lpReserved
0x180002932  call    cs:__imp_RegQueryValueExW
0x180002938  mov     edi, eax
0x18000293a  test    eax, eax
0x18000293c  jnz     short loc_18000294E
0x18000293e  mov     ecx, [rbp+cbData]
0x180002941  shr     rcx, 1
0x180002944  mov     [rbx+rcx*2], eax
0x180002947  xor     ebx, ebx
0x180002949  mov     [r14], rsi
0x18000294c  jmp     short loc_180002959
0x18000294e  jle     short loc_180002959
0x180002950  movzx   edi, ax
0x180002953  or      edi, 80070000h
0x180002959  mov     rcx, [rbp+hKey]; hKey
0x18000295d  call    cs:__imp_RegCloseKey
0x180002963  jmp     short loc_180002970
0x180002965  jle     short loc_180002970
0x180002967  movzx   edi, ax
0x18000296a  or      edi, 80070000h
0x180002970  test    rbx, rbx
0x180002973  jz      short loc_18000297E
0x180002975  mov     rcx, rbx; pv
0x180002978  call    cs:__imp_CoTaskMemFree
0x18000297e  test    edi, edi
0x180002980  jns     loc_180002B17
0x180002986  jmp     short loc_18000298D
0x180002988  mov     edi, 8007000Eh
0x18000298d  mov     rcx, [rbp+18h]; this
0x180002991  lea     r8, aOnecoreuapInet_36; "onecoreuap\\inetcore\\lib\\proofofposse"...
0x180002998  mov     r9d, edi; char *
0x18000299b  mov     edx, 0FBh; void *
0x1800029a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800029a5  mov     eax, edi
0x1800029a7  jmp     loc_180002B19
0x1800029ac  lea     rax, [rbp+cbData]
0x1800029b0  mov     [rbp+cbData], 0
0x1800029b7  xor     r9d, r9d
0x1800029ba  mov     [rsp+30h+phkResult], rax; int
0x1800029bf  xor     r8d, r8d
0x1800029c2  lea     rdx, SubKey; "Software\\Microsoft\\IdentityCRL"
0x1800029c9  lea     rcx, aIdentitycrl; "IdentityCRL"
0x1800029d0  call    cs:__imp_GetPersistedRegistryLocationW
0x1800029d6  mov     ebx, eax
0x1800029d8  cmp     eax, 0EAh
0x1800029dd  jz      short loc_180002A22
0x1800029df  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800029e4  test    ebx, ebx
0x1800029e6  jnz     short loc_180002A0C
0x1800029e8  mov     ebx, 8000FFFFh
0x1800029ed  mov     edx, 10Ch; void *
0x1800029f2  mov     rcx, [rbp+18h]; this
0x1800029f6  lea     r8, aOnecoreuapInet_36; "onecoreuap\\inetcore\\lib\\proofofposse"...
0x1800029fd  mov     r9d, ebx; char *
0x180002a00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002a05  mov     eax, ebx
0x180002a07  jmp     loc_180002B19
0x180002a0c  jle     short loc_180002A17
0x180002a0e  movzx   ebx, bx
0x180002a11  or      ebx, 80070000h
0x180002a17  test    ebx, ebx
0x180002a19  jns     short loc_180002A05
0x180002a1b  mov     edx, 10Dh
0x180002a20  jmp     short loc_1800029F2
0x180002a22  mov     ecx, [rbp+cbData]; cb
0x180002a25  call    cs:__imp_CoTaskMemAlloc
0x180002a2b  mov     [rbp+hKey], rax
0x180002a2f  mov     rbx, rax
0x180002a32  test    rax, rax
0x180002a35  jnz     short loc_180002A4D
0x180002a37  mov     rcx, [rbp+18h]; this
0x180002a3b  lea     r8, aOnecoreuapInet_36; "onecoreuap\\inetcore\\lib\\proofofposse"...
0x180002a42  mov     edx, 112h; void *
0x180002a47  call    ?_FailFast_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_NullAlloc(void *,uint,char const *)
0x180002a4d  mov     r9d, [rbp+cbData]
0x180002a51  lea     rdx, SubKey; "Software\\Microsoft\\IdentityCRL"
0x180002a58  mov     r8, rbx
0x180002a5b  mov     [rsp+30h+phkResult], 0; int
0x180002a64  lea     rcx, aIdentitycrl; "IdentityCRL"
0x180002a6b  call    cs:__imp_GetPersistedRegistryLocationW
0x180002a71  movzx   esi, ax
0x180002a74  mov     edi, eax
0x180002a76  test    eax, eax
0x180002a78  jle     short loc_180002A83
0x180002a7a  mov     eax, esi
0x180002a7c  or      eax, 80070000h
0x180002a81  test    eax, eax
0x180002a83  jns     short loc_180002A8A
0x180002a85  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180002a8a  test    edi, edi
0x180002a8c  jle     short loc_180002A98
0x180002a8e  mov     edi, esi
0x180002a90  or      edi, 80070000h
0x180002a96  test    edi, edi
0x180002a98  jns     short loc_180002AC0
0x180002a9a  mov     rcx, [rbp+18h]; this
0x180002a9e  lea     r8, aOnecoreuapInet_36; "onecoreuap\\inetcore\\lib\\proofofposse"...
0x180002aa5  mov     r9d, edi; char *
0x180002aa8  mov     edx, 11Eh; void *
0x180002aad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002ab2  mov     rcx, rbx; pv
0x180002ab5  call    cs:__imp_CoTaskMemFree
0x180002abb  jmp     loc_1800029A5
0x180002ac0  mov     r9, r14; unsigned __int16 **
0x180002ac3  mov     [rsp+30h+phkResult], 0; int
0x180002acc  lea     r8, ValueName; "LoginUrl"
0x180002ad3  mov     rdx, rbx; lpSubKey
0x180002ad6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180002add  call    ?GetTokenProviderLoginUrls@@YAJPEAUHKEY__@@PEBG1PEAPEAGPEA_K@Z; GetTokenProviderLoginUrls(HKEY__ *,ushort const *,ushort const *,ushort * *,unsigned __int64 *)
0x180002ae2  mov     ebx, eax
0x180002ae4  test    eax, eax
0x180002ae6  jns     short loc_180002B0E
0x180002ae8  mov     rcx, [rbp+18h]; this
0x180002aec  lea     r8, aOnecoreuapInet_36; "onecoreuap\\inetcore\\lib\\proofofposse"...
0x180002af3  mov     r9d, eax; char *
0x180002af6  mov     edx, 120h; void *
0x180002afb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002b00  lea     rcx, [rbp+hKey]
0x180002b04  call    ??1?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(void)
0x180002b09  jmp     loc_180002A05
0x180002b0e  lea     rcx, [rbp+hKey]
0x180002b12  call    ??1?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(void)
0x180002b17  xor     eax, eax
0x180002b19  mov     rbx, [rsp+30h+arg_0]
0x180002b1e  mov     rsi, [rsp+30h+arg_18]
0x180002b23  add     rsp, 30h
0x180002b27  pop     r14
0x180002b29  pop     rdi
0x180002b2a  pop     rbp
0x180002b2b  retn
```
