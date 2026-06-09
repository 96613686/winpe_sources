# _GetProviderCookies

- ea: `0x18001e210`
- end: `0x18001e427`
- name: `_GetProviderCookies`
- size: `535`
- prototype: `HRESULT __fastcall(void *clientTokenHandle, HKEY__ *providerKey, unsigned int *cookieCount, _AUTH_COOKIE_ENTRY **cookieEntry)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001de7c`

## callees

- `0x1800045c0`
- `0x180004f00`
- `0x18001e064`
- `0x18001e210`
- `0x18001e54c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001e36e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001e36e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e3cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e407`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e3cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e407`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e27c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e2af`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e39e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e27c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e2af`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e39e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e317`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e317`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e3f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e3f8`

## pseudocode

```c
__int64 __fastcall GetProviderCookies(
        void *clientTokenHandle,
        HKEY providerKey,
        unsigned int *cookieCount,
        _AUTH_COOKIE_ENTRY **cookieEntry)
{
  unsigned int v4; // r13d
  DWORD v5; // esi
  wchar_t *v9; // r14
  int AuthBrokerClientAppContainerStringInfo; // ebx
  LSTATUS v11; // ebx
  LSTATUS v12; // eax
  LSTATUS v13; // eax
  LSTATUS v14; // eax
  int v15; // eax
  unsigned int v16; // edi
  wchar_t *providerCookieSubKeyNameLength; // [rsp+40h] [rbp-20h] BYREF
  HKEY__ *containerKey; // [rsp+48h] [rbp-18h] BYREF
  HKEY__ *cookieKey; // [rsp+50h] [rbp-10h] BYREF
  unsigned int providerCookieCount; // [rsp+A0h] [rbp+40h] BYREF
  unsigned int maxProviderCookieSubKeyNameLength; // [rsp+B0h] [rbp+50h] BYREF

  v4 = *cookieCount;
  v5 = 0;
  containerKey = 0;
  providerCookieCount = 0;
  maxProviderCookieSubKeyNameLength = 0;
  v9 = 0;
  if ( clientTokenHandle )
  {
    providerCookieSubKeyNameLength = 0;
    AuthBrokerClientAppContainerStringInfo = GetAuthBrokerClientAppContainerStringInfo(
                                               0,
                                               clientTokenHandle,
                                               &providerCookieSubKeyNameLength);
    if ( AuthBrokerClientAppContainerStringInfo < 0 )
      goto $Exit_22;
    v11 = RegOpenKeyExW(providerKey, providerCookieSubKeyNameLength, 0, 0x20019u, &containerKey);
    FreeAuthBrokerClientAppContainerString(ClientAppContainerHostSidInfo, providerCookieSubKeyNameLength);
    if ( !v11 )
      goto LABEL_9;
  }
  v12 = RegOpenKeyExW(providerKey, L"Default", 0, 0x20019u, &containerKey);
  AuthBrokerClientAppContainerStringInfo = v12;
  if ( v12 )
  {
    if ( v12 == 2 )
    {
      AuthBrokerClientAppContainerStringInfo = 0;
    }
    else if ( v12 > 0 )
    {
      AuthBrokerClientAppContainerStringInfo = (unsigned __int16)v12 | 0x80070000;
    }
  }
  else
  {
LABEL_9:
    AuthBrokerClientAppContainerStringInfo = GetSubKeyInfo(
                                               containerKey,
                                               &providerCookieCount,
                                               &maxProviderCookieSubKeyNameLength);
    if ( AuthBrokerClientAppContainerStringInfo >= 0 && providerCookieCount && maxProviderCookieSubKeyNameLength )
    {
      v9 = (wchar_t *)LocalAlloc(0x40u, 2LL * (maxProviderCookieSubKeyNameLength + 1));
      if ( v9 )
      {
        AuthBrokerClientAppContainerStringInfo = 0;
        while ( v5 < providerCookieCount )
        {
          LODWORD(providerCookieSubKeyNameLength) = maxProviderCookieSubKeyNameLength + 1;
          cookieKey = 0;
          v13 = RegEnumKeyExW(containerKey, v5, v9, (LPDWORD)&providerCookieSubKeyNameLength, 0, 0, 0, 0);
          if ( v13 )
          {
            if ( v13 > 0 )
              AuthBrokerClientAppContainerStringInfo = (unsigned __int16)v13 | 0x80070000;
            else
              AuthBrokerClientAppContainerStringInfo = v13;
            break;
          }
          if ( (_DWORD)providerCookieSubKeyNameLength && *v9 )
          {
            v14 = RegOpenKeyExW(containerKey, v9, 0, 0x20019u, &cookieKey);
            if ( v14 )
            {
              if ( v14 > 0 )
                AuthBrokerClientAppContainerStringInfo = (unsigned __int16)v14 | 0x80070000;
              else
                AuthBrokerClientAppContainerStringInfo = v14;
            }
            else
            {
              v15 = AddProviderCookie(cookieKey, cookieCount, cookieEntry);
              if ( v15 < 0 )
                AuthBrokerClientAppContainerStringInfo = v15;
              RegCloseKey(cookieKey);
            }
          }
          ++v5;
        }
      }
      else
      {
        AuthBrokerClientAppContainerStringInfo = -2147024882;
      }
    }
  }
$Exit_22:
  v16 = 0;
  if ( *cookieCount <= v4 )
    v16 = AuthBrokerClientAppContainerStringInfo;
  LocalFree(v9);
  if ( containerKey )
    RegCloseKey(containerKey);
  return v16;
}

```

## disassembly

```asm
0x18001e210  mov     [rsp-38h+arg_8], rbx
0x18001e215  push    rbp
0x18001e216  push    rsi
0x18001e217  push    rdi
0x18001e218  push    r12
0x18001e21a  push    r13
0x18001e21c  push    r14
0x18001e21e  push    r15
0x18001e220  mov     rbp, rsp
0x18001e223  sub     rsp, 60h
0x18001e227  mov     r13d, [cookieCount]
0x18001e22a  xor     esi, esi
0x18001e22c  mov     [rbp+containerKey], rsi
0x18001e230  mov     r12, cookieEntry
0x18001e233  mov     [rbp+providerCookieCount], esi
0x18001e236  mov     r15, cookieCount
0x18001e239  mov     [rbp+maxProviderCookieSubKeyNameLength], esi
0x18001e23c  mov     rdi, providerKey
0x18001e23f  mov     r14d, esi
0x18001e242  test    clientTokenHandle, clientTokenHandle
0x18001e245  jz      short loc_18001E293
0x18001e247  mov     providerKey, clientTokenHandle; clientTokenHandle
0x18001e24a  mov     [rbp+providerCookieSubKeyNameLength], rsi
0x18001e24e  xor     ecx, ecx; infoType
0x18001e250  lea     cookieCount, [rbp+providerCookieSubKeyNameLength]; string
0x18001e254  call    ?GetAuthBrokerClientAppContainerStringInfo@@YAJW4ClientAppContainerStringInfoType@@PEAXPEAPEAG@Z; GetAuthBrokerClientAppContainerStringInfo(ClientAppContainerStringInfoType,void *,ushort * *)
0x18001e259  mov     ebx, eax
0x18001e25b  test    eax, eax
0x18001e25d  js      $Exit_22
0x18001e263  mov     providerKey, [rbp+providerCookieSubKeyNameLength]; lpSubKey
0x18001e267  lea     rax, [rbp+containerKey]
0x18001e26b  mov     r9d, 20019h; samDesired
0x18001e271  mov     [rsp+60h+phkResult], rax; phkResult
0x18001e276  xor     r8d, r8d; ulOptions
0x18001e279  mov     clientTokenHandle, rdi; hKey
0x18001e27c  call    cs:__imp_RegOpenKeyExW
0x18001e282  mov     providerKey, [rbp+providerCookieSubKeyNameLength]; string
0x18001e286  xor     ecx, ecx; infoType
0x18001e288  mov     ebx, eax
0x18001e28a  call    ?FreeAuthBrokerClientAppContainerString@@YAXW4ClientAppContainerStringInfoType@@PEAG@Z; FreeAuthBrokerClientAppContainerString(ClientAppContainerStringInfoType,ushort *)
0x18001e28f  test    ebx, ebx
0x18001e291  jz      short loc_18001E2DD
0x18001e293  lea     rax, [rbp+containerKey]
0x18001e297  mov     r9d, 20019h; samDesired
0x18001e29d  xor     r8d, r8d; ulOptions
0x18001e2a0  mov     [rsp+60h+phkResult], rax; phkResult
0x18001e2a5  lea     providerKey, aDefault; "Default"
0x18001e2ac  mov     clientTokenHandle, rdi; hKey
0x18001e2af  call    cs:__imp_RegOpenKeyExW
0x18001e2b5  mov     ebx, eax
0x18001e2b7  test    eax, eax
0x18001e2b9  jz      short loc_18001E2DD
0x18001e2bb  cmp     eax, 2
0x18001e2be  jnz     short loc_18001E2C7
0x18001e2c0  mov     ebx, esi
0x18001e2c2  jmp     $Exit_22
0x18001e2c7  test    eax, eax
0x18001e2c9  jle     $Exit_22
0x18001e2cf  movzx   ebx, ax
0x18001e2d2  or      ebx, 80070000h
0x18001e2d8  jmp     $Exit_22
0x18001e2dd  mov     clientTokenHandle, [rbp+containerKey]; key
0x18001e2e1  lea     cookieCount, [rbp+maxProviderCookieSubKeyNameLength]; maxSubKeyNameLength
0x18001e2e5  lea     providerKey, [rbp+providerCookieCount]; subKeyCount
0x18001e2e9  call    _GetSubKeyInfo
0x18001e2ee  mov     ebx, eax
0x18001e2f0  test    eax, eax
0x18001e2f2  js      $Exit_22
0x18001e2f8  cmp     [rbp+providerCookieCount], esi
0x18001e2fb  jz      $Exit_22
0x18001e301  mov     eax, [rbp+maxProviderCookieSubKeyNameLength]
0x18001e304  test    eax, eax
0x18001e306  jz      $Exit_22
0x18001e30c  lea     edx, [rax+1]
0x18001e30f  mov     ecx, 40h ; '@'; uFlags
0x18001e314  add     providerKey, providerKey; uBytes
0x18001e317  call    cs:__imp_LocalAlloc
0x18001e31d  mov     r14, rax
0x18001e320  test    rax, rax
0x18001e323  jnz     short loc_18001E32F
0x18001e325  mov     ebx, 8007000Eh
0x18001e32a  jmp     $Exit_22
0x18001e32f  mov     ebx, esi
0x18001e331  mov     edi, 80070000h
0x18001e336  cmp     esi, [rbp+providerCookieCount]
0x18001e339  jnb     loc_18001E3EB
0x18001e33f  mov     eax, [rbp+maxProviderCookieSubKeyNameLength]
0x18001e342  lea     cookieEntry, [rbp+providerCookieSubKeyNameLength]; lpcchName
0x18001e346  mov     clientTokenHandle, [rbp+containerKey]; hKey
0x18001e34a  inc     eax
0x18001e34c  mov     dword ptr [rbp+providerCookieSubKeyNameLength], eax
0x18001e34f  mov     cookieCount, r14; lpName
0x18001e352  xor     eax, eax
0x18001e354  mov     edx, esi; dwIndex
0x18001e356  mov     [rsp+60h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18001e35b  mov     [rsp+60h+lpcchClass], rax; lpcchClass
0x18001e360  mov     [rsp+60h+lpClass], rax; lpClass
0x18001e365  mov     [rsp+60h+phkResult], rax; lpReserved
0x18001e36a  mov     [rbp+cookieKey], rax
0x18001e36e  call    cs:__imp_RegEnumKeyExW
0x18001e374  xor     ecx, ecx
0x18001e376  test    eax, eax
0x18001e378  jnz     short loc_18001E3DA
0x18001e37a  cmp     dword ptr [rbp+providerCookieSubKeyNameLength], ecx
0x18001e37d  jz      short loc_18001E3D3
0x18001e37f  cmp     [r14], cx
0x18001e383  jz      short loc_18001E3D3
0x18001e385  mov     clientTokenHandle, [rbp+containerKey]; hKey
0x18001e389  lea     rax, [rbp+cookieKey]
0x18001e38d  mov     r9d, 20019h; samDesired
0x18001e393  mov     [rsp+60h+phkResult], rax; phkResult
0x18001e398  xor     r8d, r8d; ulOptions
0x18001e39b  mov     providerKey, r14; lpSubKey
0x18001e39e  call    cs:__imp_RegOpenKeyExW
0x18001e3a4  test    eax, eax
0x18001e3a6  jz      short loc_18001E3B5
0x18001e3a8  jg      short loc_18001E3AE
0x18001e3aa  mov     ebx, eax
0x18001e3ac  jmp     short loc_18001E3D3
0x18001e3ae  movzx   ebx, ax
0x18001e3b1  or      ebx, edi
0x18001e3b3  jmp     short loc_18001E3D3
0x18001e3b5  mov     clientTokenHandle, [rbp+cookieKey]; cookieKey
0x18001e3b9  mov     cookieCount, r12; cookieEntry
0x18001e3bc  mov     providerKey, r15; cookieCount
0x18001e3bf  call    _AddProviderCookie
0x18001e3c4  mov     clientTokenHandle, [rbp+cookieKey]; hKey
0x18001e3c8  test    eax, eax
0x18001e3ca  cmovs   ebx, eax
0x18001e3cd  call    cs:__imp_RegCloseKey
0x18001e3d3  inc     esi
0x18001e3d5  jmp     loc_18001E336
0x18001e3da  xor     esi, esi
0x18001e3dc  test    eax, eax
0x18001e3de  jg      short loc_18001E3E4
0x18001e3e0  mov     ebx, eax
0x18001e3e2  jmp     short $Exit_22
0x18001e3e4  movzx   ebx, ax
0x18001e3e7  or      ebx, edi
0x18001e3e9  jmp     short $Exit_22
0x18001e3eb  xor     esi, esi
0x18001e3ed  cmp     [r15], r13d
0x18001e3f0  mov     edi, esi
0x18001e3f2  mov     clientTokenHandle, r14; hMem
0x18001e3f5  cmovbe  edi, ebx
0x18001e3f8  call    cs:__imp_LocalFree
0x18001e3fe  mov     clientTokenHandle, [rbp+containerKey]; hKey
0x18001e402  test    clientTokenHandle, clientTokenHandle
0x18001e405  jz      short loc_18001E40D
0x18001e407  call    cs:__imp_RegCloseKey
0x18001e40d  mov     rbx, [rsp+60h+arg_8]
0x18001e415  mov     eax, edi
0x18001e417  add     rsp, 60h
0x18001e41b  pop     r15
0x18001e41d  pop     r14
0x18001e41f  pop     r13
0x18001e421  pop     r12
0x18001e423  pop     rdi
0x18001e424  pop     rsi
0x18001e425  pop     rbp
0x18001e426  retn
```
