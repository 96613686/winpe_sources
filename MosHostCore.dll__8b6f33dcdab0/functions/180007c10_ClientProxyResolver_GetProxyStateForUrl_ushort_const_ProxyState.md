# ClientProxyResolver::GetProxyStateForUrl(ushort const *,ProxyState *)

- ea: `0x180007c10`
- end: `0x180007e96`
- name: `?GetProxyStateForUrl@ClientProxyResolver@@UEAAJPEBGPEAW4ProxyState@@@Z`
- size: `646`
- prototype: `__int64 __fastcall(ClientProxyResolver *this, const unsigned __int16 *, enum ProxyState *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180007ab4`
- `0x180007c10`
- `0x180007fb8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007dc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007dc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e1b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180007c85`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180007c85`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x180007d06`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x180007d06`
- `WINHTTP!WinHttpOpen` at `0x180007db2`
- `WINHTTP!WinHttpOpen` at `0x180007db2`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x180007e04`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x180007e04`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180007e5e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180007e68`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180007e72`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180007e5e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180007e68`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180007e72`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180007cf5`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180007cf5`
- `ZTrace_Maps!ZTraceHelper` at `0x180007cd6`
- `ZTrace_Maps!ZTraceHelper` at `0x180007cd6`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180007d54`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180007dec`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180007d54`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180007dec`

## string_xrefs

- `0x180007cb7`: `Can't impersonate. Error: 0x%08X`
- `0x180007ccd`: `Impersonator<struct ImpersonatorLoggedOnUserTraits>::Impersonator`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ClientProxyResolver::GetProxyStateForUrl(
        ClientProxyResolver *this,
        const unsigned __int16 *a2,
        enum ProxyState *a3)
{
  unsigned int v6; // ebx
  void **v7; // rcx
  char *v8; // rcx
  signed int LastError; // eax
  unsigned int v10; // eax
  BOOL fAutoDetect; // eax
  signed int v12; // eax
  void *v13; // rax
  signed int v14; // eax
  int v15; // r8d
  WINHTTP_PROXY_INFO pProxyInfo; // [rsp+30h] [rbp-29h] BYREF
  WINHTTP_CURRENT_USER_IE_PROXY_CONFIG pProxyConfig; // [rsp+48h] [rbp-11h] BYREF
  WINHTTP_AUTOPROXY_OPTIONS pAutoProxyOptions; // [rsp+68h] [rbp+Fh] BYREF
  int v20; // [rsp+C0h] [rbp+67h] BYREF
  void *v21; // [rsp+D0h] [rbp+77h] BYREF

  v6 = 0;
  memset(&pProxyConfig, 0, sizeof(pProxyConfig));
  memset(&pAutoProxyOptions, 0, sizeof(pAutoProxyOptions));
  memset(&pProxyInfo, 0, sizeof(pProxyInfo));
  *(_DWORD *)a3 = -1;
  v7 = (void **)*((_QWORD *)this + 2);
  if ( v7 )
  {
    v8 = (char *)*v7;
    if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v20 = -2147024875;
      if ( ImpersonateLoggedOnUser(v8) )
      {
        LastError = 0;
        v20 = 0;
      }
      else
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v20 = LastError;
        if ( LastError < 0 )
        {
          ZTraceHelper(
            0,
            "Impersonator<struct ImpersonatorLoggedOnUserTraits>::Impersonator",
            21,
            &v20,
            "Can't impersonate. Error: 0x%08X",
            LastError);
          LastError = v20;
        }
      }
      if ( LastError < 0 )
      {
        v10 = ZTraceReportPropagation(LastError, "ClientProxyResolver::GetProxyStateForUrl", 56, this);
LABEL_11:
        v6 = v10;
LABEL_43:
        Impersonator<ImpersonatorLoggedOnUserTraits>::Revert(&v20);
        goto LABEL_44;
      }
      if ( WinHttpGetIEProxyConfigForCurrentUser(&pProxyConfig) )
      {
        fAutoDetect = pProxyConfig.fAutoDetect;
      }
      else
      {
        if ( GetLastError() != 2 )
        {
          v12 = GetLastError();
          if ( v12 )
          {
            if ( v12 > 0 )
              v12 = (unsigned __int16)v12 | 0x80070000;
          }
          else
          {
            v12 = -2143748092;
          }
          v10 = ZTraceReportOrigination(v12, "ClientProxyResolver::GetProxyStateForUrl", 64, this);
          goto LABEL_11;
        }
        fAutoDetect = 1;
        pProxyConfig.fAutoDetect = 1;
      }
      if ( pProxyConfig.lpszProxy )
      {
        *(_DWORD *)a3 = 1;
        goto LABEL_43;
      }
      if ( fAutoDetect )
      {
        pAutoProxyOptions.dwFlags = 1;
        pAutoProxyOptions.dwAutoDetectFlags = 3;
      }
      else
      {
        if ( !pProxyConfig.lpszAutoConfigUrl )
          goto LABEL_43;
        pAutoProxyOptions.dwFlags = 2;
        pAutoProxyOptions.lpszAutoConfigUrl = pProxyConfig.lpszAutoConfigUrl;
      }
      pAutoProxyOptions.fAutoLogonIfChallenged = 1;
      v13 = WinHttpOpen(L"MAPS_PROXY_RESOLUTION", 0, 0, 0, 0);
      v21 = v13;
      if ( v13 )
      {
        if ( WinHttpGetProxyForUrl(v13, a2, &pAutoProxyOptions, &pProxyInfo) || GetLastError() == 12180 )
        {
          *(_DWORD *)a3 = pProxyInfo.lpszProxy != 0;
          goto LABEL_42;
        }
        v14 = GetLastError();
        if ( v14 )
        {
          if ( v14 > 0 )
            v14 = (unsigned __int16)v14 | 0x80070000;
        }
        else
        {
          v14 = -2143748092;
        }
        v15 = 109;
      }
      else
      {
        v14 = GetLastError();
        if ( v14 )
        {
          if ( v14 > 0 )
            v14 = (unsigned __int16)v14 | 0x80070000;
        }
        else
        {
          v14 = -2143748092;
        }
        v15 = 97;
      }
      v6 = ZTraceReportOrigination(v14, "ClientProxyResolver::GetProxyStateForUrl", v15, this);
LABEL_42:
      wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v21);
      goto LABEL_43;
    }
  }
LABEL_44:
  GlobalFree(pProxyConfig.lpszAutoConfigUrl);
  GlobalFree(pProxyConfig.lpszProxy);
  GlobalFree(pProxyConfig.lpszProxyBypass);
  return v6;
}

```

## disassembly

```asm
0x180007c10  mov     [rsp-8+arg_8], rbx
0x180007c15  mov     [rsp-8+arg_18], rsi
0x180007c1a  push    rbp
0x180007c1b  push    rdi
0x180007c1c  push    r12
0x180007c1e  push    r13
0x180007c20  push    r14
0x180007c22  lea     rbp, [rsp-37h]
0x180007c27  sub     rsp, 90h
0x180007c2e  mov     rdi, r8
0x180007c31  mov     r14, rdx
0x180007c34  mov     rsi, rcx
0x180007c37  xor     ebx, ebx
0x180007c39  xorps   xmm0, xmm0
0x180007c3c  movups  xmmword ptr [rbp+57h+pProxyConfig.fAutoDetect], xmm0
0x180007c40  movups  xmmword ptr [rbp+57h+pProxyConfig.lpszProxy], xmm0
0x180007c44  xorps   xmm1, xmm1
0x180007c47  movups  xmmword ptr [rbp+57h+pAutoProxyOptions.dwFlags], xmm1
0x180007c4b  movups  xmmword ptr [rbp+57h+pAutoProxyOptions.lpvReserved], xmm1
0x180007c4f  xor     eax, eax
0x180007c51  movups  xmmword ptr [rbp+57h+pProxyInfo.dwAccessType], xmm0
0x180007c55  mov     [rbp+57h+pProxyInfo.lpszProxyBypass], rax
0x180007c59  mov     dword ptr [r8], 0FFFFFFFFh
0x180007c60  mov     rcx, [rcx+10h]
0x180007c64  test    rcx, rcx
0x180007c67  jz      loc_180007E5A
0x180007c6d  mov     rcx, [rcx]; hToken
0x180007c70  lea     rax, [rcx-1]
0x180007c74  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180007c78  ja      loc_180007E5A
0x180007c7e  mov     [rbp+57h+arg_0], 80070015h
0x180007c85  call    cs:__imp_ImpersonateLoggedOnUser
0x180007c8b  mov     r13d, 80070000h
0x180007c91  test    eax, eax
0x180007c93  jz      short loc_180007C9C
0x180007c95  xor     eax, eax
0x180007c97  mov     [rbp+57h+arg_0], eax
0x180007c9a  jmp     short loc_180007CDF
0x180007c9c  call    cs:__imp_GetLastError
0x180007ca2  test    eax, eax
0x180007ca4  jle     short loc_180007CAC
0x180007ca6  movzx   eax, ax
0x180007ca9  or      eax, r13d
0x180007cac  mov     [rbp+57h+arg_0], eax
0x180007caf  test    eax, eax
0x180007cb1  jns     short loc_180007CDF
0x180007cb3  mov     [rsp+0B0h+var_88], eax
0x180007cb7  lea     rax, aCanTImpersonat; "Can't impersonate. Error: 0x%08X"
0x180007cbe  mov     qword ptr [rsp+0B0h+dwFlags], rax
0x180007cc3  lea     r9, [rbp+57h+arg_0]
0x180007cc7  mov     r8d, 15h
0x180007ccd  lea     rdx, aImpersonatorSt_0; "Impersonator<struct ImpersonatorLoggedO"...
0x180007cd4  xor     ecx, ecx
0x180007cd6  call    cs:__imp_?ZTraceHelper@@YAXW4ZTraceLevel@@PEBDHPEBX1ZZ; ZTraceHelper(ZTraceLevel,char const *,int,void const *,char const *,...)
0x180007cdc  mov     eax, [rbp+57h+arg_0]
0x180007cdf  test    eax, eax
0x180007ce1  jns     short loc_180007D02
0x180007ce3  mov     r9, rsi
0x180007ce6  mov     r8d, 38h ; '8'
0x180007cec  lea     rdx, aClientproxyres; "ClientProxyResolver::GetProxyStateForUr"...
0x180007cf3  mov     ecx, eax
0x180007cf5  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x180007cfb  mov     ebx, eax
0x180007cfd  jmp     loc_180007E51
0x180007d02  lea     rcx, [rbp+57h+pProxyConfig]; pProxyConfig
0x180007d06  call    cs:__imp_WinHttpGetIEProxyConfigForCurrentUser
0x180007d0c  mov     r12d, 1
0x180007d12  test    eax, eax
0x180007d14  jnz     short loc_180007D5C
0x180007d16  call    cs:__imp_GetLastError
0x180007d1c  cmp     eax, 2
0x180007d1f  jnz     short loc_180007D29
0x180007d21  mov     eax, r12d
0x180007d24  mov     [rbp+57h+pProxyConfig.fAutoDetect], eax
0x180007d27  jmp     short loc_180007D5F
0x180007d29  call    cs:__imp_GetLastError
0x180007d2f  test    eax, eax
0x180007d31  jz      short loc_180007D3D
0x180007d33  jle     short loc_180007D42
0x180007d35  movzx   eax, ax
0x180007d38  or      eax, r13d
0x180007d3b  jmp     short loc_180007D42
0x180007d3d  mov     eax, 80390004h
0x180007d42  mov     r9, rsi
0x180007d45  mov     r8d, 40h ; '@'
0x180007d4b  lea     rdx, aClientproxyres; "ClientProxyResolver::GetProxyStateForUr"...
0x180007d52  mov     ecx, eax
0x180007d54  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x180007d5a  jmp     short loc_180007CFB
0x180007d5c  mov     eax, [rbp+57h+pProxyConfig.fAutoDetect]
0x180007d5f  cmp     [rbp+57h+pProxyConfig.lpszProxy], 0
0x180007d64  jz      short loc_180007D6E
0x180007d66  mov     [rdi], r12d
0x180007d69  jmp     loc_180007E51
0x180007d6e  test    eax, eax
0x180007d70  jz      short loc_180007D7F
0x180007d72  mov     [rbp+57h+pAutoProxyOptions.dwFlags], r12d
0x180007d76  mov     [rbp+57h+pAutoProxyOptions.dwAutoDetectFlags], 3
0x180007d7d  jmp     short loc_180007D97
0x180007d7f  mov     rax, [rbp+57h+pProxyConfig.lpszAutoConfigUrl]
0x180007d83  test    rax, rax
0x180007d86  jz      loc_180007E51
0x180007d8c  mov     [rbp+57h+pAutoProxyOptions.dwFlags], 2
0x180007d93  mov     [rbp+57h+pAutoProxyOptions.lpszAutoConfigUrl], rax
0x180007d97  mov     [rbp+57h+pAutoProxyOptions.fAutoLogonIfChallenged], r12d
0x180007d9b  mov     [rsp+0B0h+dwFlags], 0; dwFlags
0x180007da3  xor     r9d, r9d; pszProxyBypassW
0x180007da6  xor     r8d, r8d; pszProxyW
0x180007da9  xor     edx, edx; dwAccessType
0x180007dab  lea     rcx, pszAgentW; "MAPS_PROXY_RESOLUTION"
0x180007db2  call    cs:__imp_WinHttpOpen
0x180007db8  mov     [rbp+57h+arg_10], rax
0x180007dbc  test    rax, rax
0x180007dbf  jnz     short loc_180007DF6
0x180007dc1  call    cs:__imp_GetLastError
0x180007dc7  test    eax, eax
0x180007dc9  jz      short loc_180007DD5
0x180007dcb  jle     short loc_180007DDA
0x180007dcd  movzx   eax, ax
0x180007dd0  or      eax, r13d
0x180007dd3  jmp     short loc_180007DDA
0x180007dd5  mov     eax, 80390004h
0x180007dda  mov     r8d, 61h ; 'a'
0x180007de0  mov     r9, rsi
0x180007de3  lea     rdx, aClientproxyres; "ClientProxyResolver::GetProxyStateForUr"...
0x180007dea  mov     ecx, eax
0x180007dec  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x180007df2  mov     ebx, eax
0x180007df4  jmp     short loc_180007E47
0x180007df6  lea     r9, [rbp+57h+pProxyInfo]; pProxyInfo
0x180007dfa  lea     r8, [rbp+57h+pAutoProxyOptions]; pAutoProxyOptions
0x180007dfe  mov     rdx, r14; lpcwszUrl
0x180007e01  mov     rcx, rax; hSession
0x180007e04  call    cs:__imp_WinHttpGetProxyForUrl
0x180007e0a  test    eax, eax
0x180007e0c  jnz     short loc_180007E3C
0x180007e0e  call    cs:__imp_GetLastError
0x180007e14  cmp     eax, 2F94h
0x180007e19  jz      short loc_180007E3C
0x180007e1b  call    cs:__imp_GetLastError
0x180007e21  test    eax, eax
0x180007e23  jz      short loc_180007E2F
0x180007e25  jle     short loc_180007E34
0x180007e27  movzx   eax, ax
0x180007e2a  or      eax, r13d
0x180007e2d  jmp     short loc_180007E34
0x180007e2f  mov     eax, 80390004h
0x180007e34  mov     r8d, 6Dh ; 'm'
0x180007e3a  jmp     short loc_180007DE0
0x180007e3c  xor     eax, eax
0x180007e3e  cmp     [rbp+57h+pProxyInfo.lpszProxy], rax
0x180007e42  setnz   al
0x180007e45  mov     [rdi], eax
0x180007e47  lea     rcx, [rbp+57h+arg_10]
0x180007e4b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?WinHttpCloseHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180007e50  nop
0x180007e51  lea     rcx, [rbp+57h+arg_0]
0x180007e55  call    ?Revert@?$Impersonator@UImpersonatorLoggedOnUserTraits@@@@QEAAXXZ; Impersonator<ImpersonatorLoggedOnUserTraits>::Revert(void)
0x180007e5a  mov     rcx, [rbp+57h+pProxyConfig.lpszAutoConfigUrl]; hMem
0x180007e5e  call    cs:__imp_GlobalFree
0x180007e64  mov     rcx, [rbp+57h+pProxyConfig.lpszProxy]; hMem
0x180007e68  call    cs:__imp_GlobalFree
0x180007e6e  mov     rcx, [rbp+57h+pProxyConfig.lpszProxyBypass]; hMem
0x180007e72  call    cs:__imp_GlobalFree
0x180007e78  mov     eax, ebx
0x180007e7a  lea     r11, [rsp+0B0h+var_20]
0x180007e82  mov     rbx, [r11+38h]
0x180007e86  mov     rsi, [r11+48h]
0x180007e8a  mov     rsp, r11
0x180007e8d  pop     r14
0x180007e8f  pop     r13
0x180007e91  pop     r12
0x180007e93  pop     rdi
0x180007e94  pop     rbp
0x180007e95  retn
```
