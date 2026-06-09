# BrokerAuthenticateCOMCaller(ulong *,ushort const * *,ulong *)

- ea: `0x18000e4b8`
- end: `0x18000e6ff`
- name: `?BrokerAuthenticateCOMCaller@@YAJPEAKPEAPEBG0@Z`
- size: `583`
- prototype: `__int64 __fastcall(unsigned int *, const unsigned __int16 **, unsigned int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180008060`
- `0x18000bdf0`
- `0x18000e428`

## callees

- `0x180002ce0`
- `0x18000e4b8`
- `0x18000e748`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18000e669`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18000e676`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18000e669`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18000e676`
- `iertutil!__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z` at `0x18000e64d`
- `iertutil!__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z` at `0x18000e65b`
- `iertutil!__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z` at `0x18000e64d`
- `iertutil!__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z` at `0x18000e65b`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18000e5da`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18000e5da`
- `ntdll!RtlQueryPackageClaims` at `0x18000e592`
- `ntdll!RtlQueryPackageClaims` at `0x18000e592`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e6c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e6c2`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000e509`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000e509`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000e545`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000e545`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e6ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e6ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000e522`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000e522`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000e537`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000e537`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000e607`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000e607`
- `edgeIso!__imp_?IsoGetTokenIsoIntegrity@@YAJPEAX_N1PEBG2PEAW4_IsoIntegrity@@@Z` at `0x18000e698`
- `edgeIso!__imp_?IsoGetTokenIsoIntegrity@@YAJPEAX_N1PEBG2PEAW4_IsoIntegrity@@@Z` at `0x18000e698`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall BrokerAuthenticateCOMCaller(unsigned int *a1, const unsigned __int16 **a2, unsigned int *a3)
{
  HRESULT TokenIsoIntegrity; // ebx
  HANDLE CurrentThread; // rax
  unsigned __int64 v8; // r15
  __int64 i; // rbx
  const unsigned __int16 *String; // rsi
  const unsigned __int16 *v11; // rdi
  char Bool; // bl
  char v13; // al
  signed int LastError; // eax
  int v16; // [rsp+40h] [rbp-C0h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v18; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszStr2[128]; // [rsp+60h] [rbp-A0h] BYREF

  if ( a1 )
    *a1 = 255;
  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  TokenIsoIntegrity = CoImpersonateClient();
  if ( TokenIsoIntegrity >= 0 )
  {
    TokenHandle = 0;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
    {
      TokenIsoIntegrity = CoRevertToSelf();
      if ( TokenIsoIntegrity >= 0 )
      {
        v18 = 254;
        if ( (int)RtlQueryPackageClaims(TokenHandle, 0, 0, pszStr2, &v18, 0, 0, 0) >= 0 && v18 <= 0x7FFFFFFF )
        {
          v8 = (unsigned __int64)(int)v18 >> 1;
          for ( i = 0; (unsigned int)i < 3; i = (unsigned int)(i + 1) )
          {
            if ( !StrCmpNICW((LPCWSTR)*(&g_SpartanPackageDescriptor + 3 * i + 1), pszStr2, v8)
              && *((_DWORD *)&g_SpartanPackageDescriptor + 6 * i) == (_DWORD)i )
            {
              if ( g_dwBrowserBrokerTls == -1 )
              {
                TokenIsoIntegrity = -2147467259;
              }
              else
              {
                TlsSetValue(g_dwBrowserBrokerTls, (LPVOID)(unsigned int)(i + 1));
                if ( a1 )
                  *a1 = i;
                if ( a2 )
                  *a2 = (const unsigned __int16 *)*(&g_SpartanPackageDescriptor + 3 * i + 2);
                TokenIsoIntegrity = 0;
                if ( a3 )
                {
                  if ( BrokerThread_GetBrokerInstance() )
                  {
                    v16 = 0;
                    String = (const unsigned __int16 *)IEConfiguration_GetString(268435507);
                    v11 = (const unsigned __int16 *)IEConfiguration_GetString(268435506);
                    Bool = IEConfiguration_GetBool(268435520);
                    v13 = IEConfiguration_GetBool(268435519);
                    TokenIsoIntegrity = IsoGetTokenIsoIntegrity(
                                          TokenHandle,
                                          v13,
                                          Bool,
                                          v11,
                                          String,
                                          (enum _IsoIntegrity *)&v16);
                    if ( TokenIsoIntegrity >= 0 )
                      *a3 = v16 & 0x7F;
                  }
                  else
                  {
                    TokenIsoIntegrity = -2147418113;
                  }
                }
              }
              goto LABEL_29;
            }
          }
        }
        TokenIsoIntegrity = -2147024891;
      }
LABEL_29:
      CloseHandle(TokenHandle);
    }
    else
    {
      LastError = GetLastError();
      TokenIsoIntegrity = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  return (unsigned int)TokenIsoIntegrity;
}

```

## disassembly

```asm
0x18000e4b8  push    rbp
0x18000e4ba  push    rbx
0x18000e4bb  push    rsi
0x18000e4bc  push    rdi
0x18000e4bd  push    r12
0x18000e4bf  push    r14
0x18000e4c1  push    r15
0x18000e4c3  lea     rbp, [rsp-70h]
0x18000e4c8  sub     rsp, 170h
0x18000e4cf  mov     rax, cs:__security_cookie
0x18000e4d6  xor     rax, rsp
0x18000e4d9  mov     [rbp+0A0h+var_40], rax
0x18000e4dd  mov     r14, r8
0x18000e4e0  mov     rdi, rdx
0x18000e4e3  mov     rsi, rcx
0x18000e4e6  test    rcx, rcx
0x18000e4e9  jz      short loc_18000E4F1
0x18000e4eb  mov     dword ptr [rcx], 0FFh
0x18000e4f1  test    rdi, rdi
0x18000e4f4  jz      short loc_18000E4FD
0x18000e4f6  mov     qword ptr [rdx], 0
0x18000e4fd  test    r14, r14
0x18000e500  jz      short loc_18000E509
0x18000e502  mov     dword ptr [r8], 0
0x18000e509  call    cs:__imp_CoImpersonateClient
0x18000e50f  mov     ebx, eax
0x18000e511  test    eax, eax
0x18000e513  js      loc_18000E6DF
0x18000e519  mov     [rsp+1A0h+TokenHandle], 0
0x18000e522  call    cs:__imp_GetCurrentThread
0x18000e528  xor     r8d, r8d; OpenAsSelf
0x18000e52b  lea     r9, [rsp+1A0h+TokenHandle]; TokenHandle
0x18000e530  mov     rcx, rax; ThreadHandle
0x18000e533  lea     edx, [r8+8]; DesiredAccess
0x18000e537  call    cs:__imp_OpenThreadToken
0x18000e53d  test    eax, eax
0x18000e53f  jz      loc_18000E6CA
0x18000e545  call    cs:__imp_CoRevertToSelf
0x18000e54b  mov     ebx, eax
0x18000e54d  test    eax, eax
0x18000e54f  js      loc_18000E6BD
0x18000e555  mov     rcx, [rsp+1A0h+TokenHandle]
0x18000e55a  lea     rax, [rsp+1A0h+var_150]
0x18000e55f  mov     [rsp+1A0h+var_168], 0
0x18000e568  lea     r9, [rsp+1A0h+pszStr2]
0x18000e56d  mov     [rsp+1A0h+var_170], 0
0x18000e576  xor     r8d, r8d
0x18000e579  mov     [rsp+1A0h+var_178], 0
0x18000e582  xor     edx, edx
0x18000e584  mov     [rsp+1A0h+var_180], rax
0x18000e589  mov     [rsp+1A0h+var_150], 0FEh
0x18000e592  call    cs:__imp_RtlQueryPackageClaims
0x18000e598  test    eax, eax
0x18000e59a  js      loc_18000E6B8
0x18000e5a0  cmp     [rsp+1A0h+var_150], 7FFFFFFFh
0x18000e5a9  ja      loc_18000E6B8
0x18000e5af  movsxd  r15, dword ptr [rsp+1A0h+var_150]
0x18000e5b4  shr     r15, 1
0x18000e5b7  xor     ebx, ebx
0x18000e5b9  cmp     ebx, 3
0x18000e5bc  jnb     loc_18000E6B8
0x18000e5c2  lea     rax, ?g_SpartanPackageDescriptor@@3PAUSpartanPackageDescription@@A; SpartanPackageDescription near * g_SpartanPackageDescriptor
0x18000e5c9  mov     r8d, r15d; nChar
0x18000e5cc  lea     r12, [rbx+rbx*2]
0x18000e5d0  mov     rcx, [rax+r12*8+8]; pszStr1
0x18000e5d5  lea     rdx, [rsp+1A0h+pszStr2]; pszStr2
0x18000e5da  call    cs:__imp_StrCmpNICW
0x18000e5e0  test    eax, eax
0x18000e5e2  jnz     short loc_18000E5F1
0x18000e5e4  lea     rax, ?g_SpartanPackageDescriptor@@3PAUSpartanPackageDescription@@A; SpartanPackageDescription near * g_SpartanPackageDescriptor
0x18000e5eb  cmp     [rax+r12*8], ebx
0x18000e5ef  jz      short loc_18000E5F5
0x18000e5f1  inc     ebx
0x18000e5f3  jmp     short loc_18000E5B9
0x18000e5f5  mov     ecx, cs:?g_dwBrowserBrokerTls@@3KA; dwTlsIndex
0x18000e5fb  cmp     ecx, 0FFFFFFFFh
0x18000e5fe  jz      loc_18000E6B1
0x18000e604  lea     edx, [rbx+1]; lpTlsValue
0x18000e607  call    cs:__imp_TlsSetValue
0x18000e60d  test    rsi, rsi
0x18000e610  jz      short loc_18000E614
0x18000e612  mov     [rsi], ebx
0x18000e614  test    rdi, rdi
0x18000e617  jz      short loc_18000E628
0x18000e619  lea     rax, ?g_SpartanPackageDescriptor@@3PAUSpartanPackageDescription@@A; SpartanPackageDescription near * g_SpartanPackageDescriptor
0x18000e620  mov     rax, [rax+r12*8+10h]
0x18000e625  mov     [rdi], rax
0x18000e628  xor     ebx, ebx
0x18000e62a  test    r14, r14
0x18000e62d  jz      loc_18000E6BD
0x18000e633  call    ?BrokerThread_GetBrokerInstance@@YAPEAVCBrowserBrokerInstance@@XZ; BrokerThread_GetBrokerInstance(void)
0x18000e638  test    rax, rax
0x18000e63b  jnz     short loc_18000E644
0x18000e63d  mov     ebx, 8000FFFFh
0x18000e642  jmp     short loc_18000E6BD
0x18000e644  mov     ecx, 10000033h
0x18000e649  mov     [rsp+1A0h+var_160], ebx
0x18000e64d  call    cs:__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z; IEConfiguration_GetString(IEConfigurationID)
0x18000e653  mov     ecx, 10000032h
0x18000e658  mov     rsi, rax
0x18000e65b  call    cs:__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z; IEConfiguration_GetString(IEConfigurationID)
0x18000e661  mov     ecx, 10000040h
0x18000e666  mov     rdi, rax
0x18000e669  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18000e66f  mov     ecx, 1000003Fh
0x18000e674  mov     bl, al
0x18000e676  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18000e67c  lea     rcx, [rsp+1A0h+var_160]
0x18000e681  mov     r9, rdi
0x18000e684  mov     [rsp+1A0h+var_178], rcx
0x18000e689  mov     r8b, bl
0x18000e68c  mov     rcx, [rsp+1A0h+TokenHandle]
0x18000e691  mov     dl, al
0x18000e693  mov     [rsp+1A0h+var_180], rsi
0x18000e698  call    cs:__imp_?IsoGetTokenIsoIntegrity@@YAJPEAX_N1PEBG2PEAW4_IsoIntegrity@@@Z; IsoGetTokenIsoIntegrity(void *,bool,bool,ushort const *,ushort const *,_IsoIntegrity *)
0x18000e69e  mov     ebx, eax
0x18000e6a0  test    eax, eax
0x18000e6a2  js      short loc_18000E6BD
0x18000e6a4  movzx   eax, byte ptr [rsp+1A0h+var_160]
0x18000e6a9  and     eax, 7Fh
0x18000e6ac  mov     [r14], eax
0x18000e6af  jmp     short loc_18000E6BD
0x18000e6b1  mov     ebx, 80004005h
0x18000e6b6  jmp     short loc_18000E6BD
0x18000e6b8  mov     ebx, 80070005h
0x18000e6bd  mov     rcx, [rsp+1A0h+TokenHandle]; hObject
0x18000e6c2  call    cs:__imp_CloseHandle
0x18000e6c8  jmp     short loc_18000E6DF
0x18000e6ca  call    cs:__imp_GetLastError
0x18000e6d0  mov     ebx, eax
0x18000e6d2  test    eax, eax
0x18000e6d4  jle     short loc_18000E6DF
0x18000e6d6  movzx   ebx, ax
0x18000e6d9  or      ebx, 80070000h
0x18000e6df  mov     eax, ebx
0x18000e6e1  mov     rcx, [rbp+0A0h+var_40]
0x18000e6e5  xor     rcx, rsp; StackCookie
0x18000e6e8  call    __security_check_cookie
0x18000e6ed  add     rsp, 170h
0x18000e6f4  pop     r15
0x18000e6f6  pop     r14
0x18000e6f8  pop     r12
0x18000e6fa  pop     rdi
0x18000e6fb  pop     rsi
0x18000e6fc  pop     rbx
0x18000e6fd  pop     rbp
0x18000e6fe  retn
```
