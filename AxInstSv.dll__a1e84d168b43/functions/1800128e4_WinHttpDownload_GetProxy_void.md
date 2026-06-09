# WinHttpDownload::GetProxy(void)

- ea: `0x1800128e4`
- end: `0x180012c1b`
- name: `?GetProxy@WinHttpDownload@@AEAAJXZ`
- size: `823`
- prototype: `__int64 __fastcall(WinHttpDownload *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180012244`

## callees

- `0x18000725c`
- `0x1800128e4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180012958`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180012ade`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180012b65`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180012be3`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180012bf2`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180012c01`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180012958`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180012ade`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180012b65`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180012be3`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180012bf2`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180012c01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012bc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012bc5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180012a1c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180012a1c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001296b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001296b`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x180012919`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x180012919`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x180012a13`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x180012a13`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x18001297d`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x18001297d`

## string_xrefs

- `0x18001292f`: `WinHttpGetDefaultProxyConfiguration Succeeded`
- `0x180012b7c`: `Proxy Settings Proxy: %s | Bypass: %s | AccessType: %d`

## pseudocode

```c
__int64 __fastcall WinHttpDownload::GetProxy(WinHttpDownload *this)
{
  WINHTTP_PROXY_INFO *v1; // r13
  HGLOBAL *v3; // rdi
  unsigned int v4; // ebx
  int v5; // r14d
  BOOL ProxyForUrl; // r12d
  DWORD dwFlags; // eax
  const wchar_t *v8; // rax
  unsigned __int16 *v9; // rcx
  int v10; // edx
  int v11; // r8d
  unsigned __int16 *v12; // rcx
  int v13; // edx
  int v14; // r8d
  const wchar_t *v15; // rdx
  const wchar_t *v16; // r12
  unsigned __int16 *v17; // rcx
  int v18; // r8d
  int v19; // r9d
  unsigned __int16 *v20; // rcx
  int v21; // r8d
  int v22; // r9d
  __int64 v23; // rax
  signed int LastError; // eax
  WINHTTP_CURRENT_USER_IE_PROXY_CONFIG pProxyConfig; // [rsp+40h] [rbp-40h] BYREF
  WINHTTP_AUTOPROXY_OPTIONS pAutoProxyOptions; // [rsp+60h] [rbp-20h] BYREF

  v1 = (WINHTTP_PROXY_INFO *)((char *)this + 88);
  memset(&pAutoProxyOptions, 0, sizeof(pAutoProxyOptions));
  memset(&pProxyConfig, 0, sizeof(pProxyConfig));
  WinHttpGetDefaultProxyConfiguration((WINHTTP_PROXY_INFO *)((char *)this + 88));
  v3 = (HGLOBAL *)((char *)this + 104);
  if ( *((_QWORD *)this + 12) )
  {
    AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 2u, 4u, L"WinHttpGetDefaultProxyConfiguration Succeeded");
    v4 = 0;
LABEL_18:
    if ( pProxyConfig.lpszProxy )
    {
      *((_QWORD *)this + 12) = pProxyConfig.lpszProxy;
      *v3 = pProxyConfig.lpszProxyBypass;
      v1->dwAccessType = 3;
      pProxyConfig.lpszProxy = 0;
      pProxyConfig.lpszProxyBypass = 0;
    }
LABEL_20:
    v8 = (const wchar_t *)*((_QWORD *)this + 12);
    if ( v8 )
    {
      v9 = (unsigned __int16 *)*((_QWORD *)this + 12);
      do
      {
        v10 = *(unsigned __int16 *)((char *)v9 + (char *)asc_180021280 - (char *)v8);
        v11 = *v9 - v10;
        if ( v11 )
          break;
        ++v9;
      }
      while ( v10 );
      if ( v11 )
      {
        v12 = (unsigned __int16 *)*((_QWORD *)this + 12);
        do
        {
          v13 = *(unsigned __int16 *)((char *)v12 + (char *)asc_180021278 - (char *)v8);
          v14 = *v12 - v13;
          if ( v14 )
            break;
          ++v12;
        }
        while ( v13 );
        if ( v14 )
        {
LABEL_31:
          v15 = (const wchar_t *)*v3;
          v16 = L"(none)";
          if ( *v3 )
          {
            v17 = (unsigned __int16 *)*v3;
            do
            {
              v18 = *(unsigned __int16 *)((char *)v17 + (char *)asc_180021280 - (char *)v15);
              v19 = *v17 - v18;
              if ( v19 )
                break;
              ++v17;
            }
            while ( v18 );
            if ( v19 )
            {
              v20 = (unsigned __int16 *)*v3;
              do
              {
                v21 = *(unsigned __int16 *)((char *)v20 + (char *)asc_180021278 - (char *)v15);
                v22 = *v20 - v21;
                if ( v22 )
                  break;
                ++v20;
              }
              while ( v21 );
              if ( v22 )
                goto LABEL_42;
            }
            AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 2u, 4u, L"suppressing invalid bypass string %S", *v3);
            GlobalFree(*v3);
            v8 = (const wchar_t *)*((_QWORD *)this + 12);
            *v3 = 0;
          }
          v15 = L"(none)";
LABEL_42:
          if ( v8 )
            v16 = v8;
          AxISEvents::DebugMsg(
            (AxISEvents *)&qword_180021AD8,
            2u,
            4u,
            L"Proxy Settings Proxy: %s | Bypass: %s | AccessType: %d",
            v16,
            v15,
            *((_DWORD *)this + 22));
          v23 = *((_QWORD *)this + 12);
          if ( v23 )
          {
            *((_DWORD *)this + 28) = 1;
            v4 = 0;
            *((_QWORD *)this + 15) = v23;
          }
          goto LABEL_48;
        }
      }
      AxISEvents::DebugMsg(
        (AxISEvents *)&qword_180021AD8,
        2u,
        4u,
        L"suppressing invalid proxy string %S",
        *((_QWORD *)this + 12));
      GlobalFree(*((HGLOBAL *)this + 12));
      *((_QWORD *)this + 12) = 0;
    }
    v8 = 0;
    goto LABEL_31;
  }
  if ( *v3 )
  {
    GlobalFree(*v3);
    *v3 = 0;
  }
  if ( SetThreadToken(0, *((HANDLE *)this + 1)) )
  {
    if ( WinHttpGetIEProxyConfigForCurrentUser(&pProxyConfig) )
    {
      v5 = 0;
      ProxyForUrl = 0;
      if ( pProxyConfig.fAutoDetect )
      {
        AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 2u, 4u, L"IE specifies auto-detect");
        dwFlags = 1;
        pAutoProxyOptions.dwFlags = 1;
        pAutoProxyOptions.dwAutoDetectFlags = 3;
        v5 = 1;
      }
      else
      {
        dwFlags = pAutoProxyOptions.dwFlags;
      }
      if ( pProxyConfig.lpszAutoConfigUrl )
      {
        pAutoProxyOptions.lpszAutoConfigUrl = pProxyConfig.lpszAutoConfigUrl;
        pAutoProxyOptions.dwFlags = dwFlags | 2;
        v5 = 1;
      }
      pAutoProxyOptions.fAutoLogonIfChallenged = 1;
      if ( !v5 )
      {
LABEL_16:
        RevertToSelf();
        v4 = 0;
        if ( v5 && ProxyForUrl )
          goto LABEL_20;
        goto LABEL_18;
      }
    }
    else
    {
      v5 = 1;
      pAutoProxyOptions.fAutoLogonIfChallenged = 1;
    }
    AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 2u, 4u, L"Performing auto proxy detection");
    ProxyForUrl = WinHttpGetProxyForUrl(*((HINTERNET *)this + 7), *((LPCWSTR *)this + 2), &pAutoProxyOptions, v1);
    goto LABEL_16;
  }
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
    v4 = (unsigned __int16)LastError | 0x80070000;
LABEL_48:
  if ( pProxyConfig.lpszProxy )
    GlobalFree(pProxyConfig.lpszProxy);
  if ( pProxyConfig.lpszProxyBypass )
    GlobalFree(pProxyConfig.lpszProxyBypass);
  if ( pProxyConfig.lpszAutoConfigUrl )
    GlobalFree(pProxyConfig.lpszAutoConfigUrl);
  return v4;
}

```

## disassembly

```asm
0x1800128e4  push    rbp
0x1800128e6  push    rbx
0x1800128e7  push    rsi
0x1800128e8  push    rdi
0x1800128e9  push    r12
0x1800128eb  push    r13
0x1800128ed  push    r14
0x1800128ef  mov     rbp, rsp
0x1800128f2  sub     rsp, 80h
0x1800128f9  xorps   xmm0, xmm0
0x1800128fc  lea     r13, [rcx+58h]
0x180012900  xorps   xmm1, xmm1
0x180012903  mov     rsi, rcx
0x180012906  mov     rcx, r13; pProxyInfo
0x180012909  movups  xmmword ptr [rbp+pAutoProxyOptions.dwFlags], xmm0
0x18001290d  movups  xmmword ptr [rbp+pAutoProxyOptions.lpvReserved], xmm0
0x180012911  movups  xmmword ptr [rbp+pProxyConfig.fAutoDetect], xmm1
0x180012915  movups  xmmword ptr [rbp+pProxyConfig.lpszProxy], xmm1
0x180012919  call    cs:__imp_WinHttpGetDefaultProxyConfiguration
0x18001291f  cmp     qword ptr [rsi+60h], 0
0x180012924  lea     rdi, [rsi+68h]
0x180012928  mov     ebx, 1
0x18001292d  jz      short loc_180012950
0x18001292f  lea     r9, aWinhttpgetdefa_0; "WinHttpGetDefaultProxyConfiguration Suc"...
0x180012936  lea     edx, [rbx+1]; unsigned int
0x180012939  lea     r8d, [rbx+3]; unsigned __int8
0x18001293d  lea     rcx, qword_180021AD8; this
0x180012944  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x180012949  xor     ebx, ebx
0x18001294b  jmp     loc_180012A2E
0x180012950  mov     rcx, [rdi]; hMem
0x180012953  test    rcx, rcx
0x180012956  jz      short loc_180012965
0x180012958  call    cs:__imp_GlobalFree
0x18001295e  mov     qword ptr [rdi], 0
0x180012965  mov     rdx, [rsi+8]; Token
0x180012969  xor     ecx, ecx; Thread
0x18001296b  call    cs:__imp_SetThreadToken
0x180012971  test    eax, eax
0x180012973  jz      loc_180012BC5
0x180012979  lea     rcx, [rbp+pProxyConfig]; pProxyConfig
0x18001297d  call    cs:__imp_WinHttpGetIEProxyConfigForCurrentUser
0x180012983  test    eax, eax
0x180012985  jz      short loc_1800129E2
0x180012987  xor     r14d, r14d
0x18001298a  xor     r12d, r12d
0x18001298d  cmp     [rbp+pProxyConfig.fAutoDetect], r12d
0x180012991  jz      short loc_1800129BF
0x180012993  lea     r9, aIeSpecifiesAut; "IE specifies auto-detect"
0x18001299a  lea     edx, [r14+2]; unsigned int
0x18001299e  lea     r8d, [r14+4]; unsigned __int8
0x1800129a2  lea     rcx, qword_180021AD8; this
0x1800129a9  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x1800129ae  mov     eax, ebx
0x1800129b0  mov     [rbp+pAutoProxyOptions.dwFlags], ebx
0x1800129b3  mov     [rbp+pAutoProxyOptions.dwAutoDetectFlags], 3
0x1800129ba  mov     r14d, ebx
0x1800129bd  jmp     short loc_1800129C2
0x1800129bf  mov     eax, [rbp+pAutoProxyOptions.dwFlags]
0x1800129c2  mov     rcx, [rbp+pProxyConfig.lpszAutoConfigUrl]
0x1800129c6  test    rcx, rcx
0x1800129c9  jz      short loc_1800129D8
0x1800129cb  or      eax, 2
0x1800129ce  mov     [rbp+pAutoProxyOptions.lpszAutoConfigUrl], rcx
0x1800129d2  mov     [rbp+pAutoProxyOptions.dwFlags], eax
0x1800129d5  mov     r14d, ebx
0x1800129d8  mov     [rbp+pAutoProxyOptions.fAutoLogonIfChallenged], ebx
0x1800129db  test    r14d, r14d
0x1800129de  jz      short loc_180012A1C
0x1800129e0  jmp     short loc_1800129E8
0x1800129e2  mov     r14d, ebx
0x1800129e5  mov     [rbp+pAutoProxyOptions.fAutoLogonIfChallenged], ebx
0x1800129e8  mov     edx, 2; unsigned int
0x1800129ed  lea     r9, aPerformingAuto; "Performing auto proxy detection"
0x1800129f4  lea     rcx, qword_180021AD8; this
0x1800129fb  lea     r8d, [rdx+2]; unsigned __int8
0x1800129ff  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x180012a04  mov     rdx, [rsi+10h]; lpcwszUrl
0x180012a08  lea     r8, [rbp+pAutoProxyOptions]; pAutoProxyOptions
0x180012a0c  mov     rcx, [rsi+38h]; hSession
0x180012a10  mov     r9, r13; pProxyInfo
0x180012a13  call    cs:__imp_WinHttpGetProxyForUrl
0x180012a19  mov     r12d, eax
0x180012a1c  call    cs:__imp_RevertToSelf
0x180012a22  xor     ebx, ebx
0x180012a24  test    r14d, r14d
0x180012a27  jz      short loc_180012A2E
0x180012a29  test    r12d, r12d
0x180012a2c  jnz     short loc_180012A5A
0x180012a2e  mov     rax, [rbp+pProxyConfig.lpszProxy]
0x180012a32  test    rax, rax
0x180012a35  jz      short loc_180012A5A
0x180012a37  mov     [rsi+60h], rax
0x180012a3b  mov     rax, [rbp+pProxyConfig.lpszProxyBypass]
0x180012a3f  mov     [rdi], rax
0x180012a42  mov     dword ptr [r13+0], 3
0x180012a4a  mov     [rbp+pProxyConfig.lpszProxy], 0
0x180012a52  mov     [rbp+pProxyConfig.lpszProxyBypass], 0
0x180012a5a  mov     rax, [rsi+60h]
0x180012a5e  lea     r14, asc_180021280; ":"
0x180012a65  lea     r13, asc_180021278; "::"
0x180012a6c  test    rax, rax
0x180012a6f  jz      short loc_180012AEC
0x180012a71  mov     r9, r14
0x180012a74  mov     rcx, rax
0x180012a77  sub     r9, rax
0x180012a7a  movzx   r8d, word ptr [rcx]
0x180012a7e  movzx   edx, word ptr [rcx+r9]
0x180012a83  sub     r8d, edx
0x180012a86  jnz     short loc_180012A90
0x180012a88  add     rcx, 2
0x180012a8c  test    edx, edx
0x180012a8e  jnz     short loc_180012A7A
0x180012a90  test    r8d, r8d
0x180012a93  jz      short loc_180012AB9
0x180012a95  mov     r9, r13
0x180012a98  mov     rcx, rax
0x180012a9b  sub     r9, rax
0x180012a9e  movzx   r8d, word ptr [rcx]
0x180012aa2  movzx   edx, word ptr [rcx+r9]
0x180012aa7  sub     r8d, edx
0x180012aaa  jnz     short loc_180012AB4
0x180012aac  add     rcx, 2
0x180012ab0  test    edx, edx
0x180012ab2  jnz     short loc_180012A9E
0x180012ab4  test    r8d, r8d
0x180012ab7  jnz     short loc_180012AEE
0x180012ab9  mov     edx, 2; unsigned int
0x180012abe  mov     [rsp+80h+var_60], rax
0x180012ac3  lea     r9, aSuppressingInv_0; "suppressing invalid proxy string %S"
0x180012aca  lea     rcx, qword_180021AD8; this
0x180012ad1  lea     r8d, [rdx+2]; unsigned __int8
0x180012ad5  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x180012ada  mov     rcx, [rsi+60h]; hMem
0x180012ade  call    cs:__imp_GlobalFree
0x180012ae4  mov     qword ptr [rsi+60h], 0
0x180012aec  xor     eax, eax
0x180012aee  mov     rdx, [rdi]
0x180012af1  lea     r12, aNone; "(none)"
0x180012af8  test    rdx, rdx
0x180012afb  jz      short loc_180012B76
0x180012afd  mov     rcx, rdx
0x180012b00  sub     r14, rdx
0x180012b03  movzx   r9d, word ptr [rcx]
0x180012b07  movzx   r8d, word ptr [rcx+r14]
0x180012b0c  sub     r9d, r8d
0x180012b0f  jnz     short loc_180012B1A
0x180012b11  add     rcx, 2
0x180012b15  test    r8d, r8d
0x180012b18  jnz     short loc_180012B03
0x180012b1a  test    r9d, r9d
0x180012b1d  jz      short loc_180012B41
0x180012b1f  mov     rcx, rdx
0x180012b22  sub     r13, rdx
0x180012b25  movzx   r9d, word ptr [rcx]
0x180012b29  movzx   r8d, word ptr [rcx+r13]
0x180012b2e  sub     r9d, r8d
0x180012b31  jnz     short loc_180012B3C
0x180012b33  add     rcx, 2
0x180012b37  test    r8d, r8d
0x180012b3a  jnz     short loc_180012B25
0x180012b3c  test    r9d, r9d
0x180012b3f  jnz     short loc_180012B79
0x180012b41  mov     [rsp+80h+var_60], rdx
0x180012b46  lea     r9, aSuppressingInv; "suppressing invalid bypass string %S"
0x180012b4d  mov     edx, 2; unsigned int
0x180012b52  lea     rcx, qword_180021AD8; this
0x180012b59  lea     r8d, [rdx+2]; unsigned __int8
0x180012b5d  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x180012b62  mov     rcx, [rdi]; hMem
0x180012b65  call    cs:__imp_GlobalFree
0x180012b6b  mov     rax, [rsi+60h]
0x180012b6f  mov     qword ptr [rdi], 0
0x180012b76  mov     rdx, r12
0x180012b79  mov     ecx, [rsi+58h]
0x180012b7c  lea     r9, aProxySettingsP; "Proxy Settings Proxy: %s | Bypass: %s |"...
0x180012b83  mov     [rsp+80h+var_50], ecx
0x180012b87  test    rax, rax
0x180012b8a  mov     [rsp+80h+var_58], rdx
0x180012b8f  lea     rcx, qword_180021AD8; this
0x180012b96  mov     edx, 2; unsigned int
0x180012b9b  cmovnz  r12, rax
0x180012b9f  mov     [rsp+80h+var_60], r12
0x180012ba4  lea     r8d, [rdx+2]; unsigned __int8
0x180012ba8  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x180012bad  mov     rax, [rsi+60h]
0x180012bb1  test    rax, rax
0x180012bb4  jz      short loc_180012BDA
0x180012bb6  mov     dword ptr [rsi+70h], 1
0x180012bbd  xor     ebx, ebx
0x180012bbf  mov     [rsi+78h], rax
0x180012bc3  jmp     short loc_180012BDA
0x180012bc5  call    cs:__imp_GetLastError
0x180012bcb  mov     ebx, eax
0x180012bcd  test    eax, eax
0x180012bcf  jle     short loc_180012BDA
0x180012bd1  movzx   ebx, ax
0x180012bd4  or      ebx, 80070000h
0x180012bda  mov     rcx, [rbp+pProxyConfig.lpszProxy]; hMem
0x180012bde  test    rcx, rcx
0x180012be1  jz      short loc_180012BE9
0x180012be3  call    cs:__imp_GlobalFree
0x180012be9  mov     rcx, [rbp+pProxyConfig.lpszProxyBypass]; hMem
0x180012bed  test    rcx, rcx
0x180012bf0  jz      short loc_180012BF8
0x180012bf2  call    cs:__imp_GlobalFree
0x180012bf8  mov     rcx, [rbp+pProxyConfig.lpszAutoConfigUrl]; hMem
0x180012bfc  test    rcx, rcx
0x180012bff  jz      short loc_180012C07
0x180012c01  call    cs:__imp_GlobalFree
0x180012c07  mov     eax, ebx
0x180012c09  add     rsp, 80h
0x180012c10  pop     r14
0x180012c12  pop     r13
0x180012c14  pop     r12
0x180012c16  pop     rdi
0x180012c17  pop     rsi
0x180012c18  pop     rbx
0x180012c19  pop     rbp
0x180012c1a  retn
```
