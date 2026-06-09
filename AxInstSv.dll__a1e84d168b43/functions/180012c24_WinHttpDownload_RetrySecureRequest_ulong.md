# WinHttpDownload::RetrySecureRequest(ulong *)

- ea: `0x180012c24`
- end: `0x180012f96`
- name: `?RetrySecureRequest@WinHttpDownload@@AEAAJPEAK@Z`
- size: `882`
- prototype: `__int64 __fastcall(WinHttpDownload *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012408`

## callees

- `0x18000725c`
- `0x18001221c`
- `0x180012244`
- `0x180012c24`
- `0x1800131a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012c7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012cff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012c7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012cff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f68`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180012f7d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180012f7d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180012cf5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180012cf5`
- `WINHTTP!WinHttpReceiveResponse` at `0x180012ea3`
- `WINHTTP!WinHttpReceiveResponse` at `0x180012ea3`
- `WINHTTP!WinHttpSendRequest` at `0x180012e8f`
- `WINHTTP!WinHttpSendRequest` at `0x180012e8f`
- `WINHTTP!WinHttpQueryAuthSchemes` at `0x180012c71`
- `WINHTTP!WinHttpQueryAuthSchemes` at `0x180012f0d`
- `WINHTTP!WinHttpQueryAuthSchemes` at `0x180012c71`
- `WINHTTP!WinHttpQueryAuthSchemes` at `0x180012f0d`
- `WINHTTP!WinHttpSetCredentials` at `0x180012e13`
- `WINHTTP!WinHttpSetCredentials` at `0x180012e5c`
- `WINHTTP!WinHttpSetCredentials` at `0x180012e13`
- `WINHTTP!WinHttpSetCredentials` at `0x180012e5c`
- `WINHTTP!WinHttpSetOption` at `0x180012de6`
- `WINHTTP!WinHttpSetOption` at `0x180012de6`
- `WINHTTP!WinHttpCloseHandle` at `0x180012cbf`
- `WINHTTP!WinHttpCloseHandle` at `0x180012cd2`
- `WINHTTP!WinHttpCloseHandle` at `0x180012ce5`
- `WINHTTP!WinHttpCloseHandle` at `0x180012cbf`
- `WINHTTP!WinHttpCloseHandle` at `0x180012cd2`
- `WINHTTP!WinHttpCloseHandle` at `0x180012ce5`
- `WINHTTP!WinHttpQueryHeaders` at `0x180012ed9`
- `WINHTTP!WinHttpQueryHeaders` at `0x180012ed9`

## string_xrefs

- `0x180012d14`: `RetrySecureRequest: SetThreadToken Failed , error %x`
- `0x180012d34`: `Could not create a new WinHTTP session during retry, error %x`

## pseudocode

```c
__int64 __fastcall WinHttpDownload::RetrySecureRequest(WinHttpDownload *this, unsigned int *a2)
{
  unsigned int *v2; // r14
  void *v4; // rcx
  signed int LastError; // eax
  unsigned int v6; // ebx
  unsigned __int16 *v7; // r9
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  signed int v11; // eax
  int HTTPSession; // eax
  __int64 v13; // rax
  __int64 v14; // xmm1_8
  DWORD v15; // r15d
  DWORD v16; // r13d
  unsigned int v17; // r12d
  DWORD v18; // ecx
  unsigned int v19; // eax
  DWORD v20; // r14d
  void *v21; // rcx
  signed int v22; // eax
  signed int v23; // eax
  LPCWSTR pwszPassword; // [rsp+20h] [rbp-48h]
  DWORD dwFirstScheme; // [rsp+40h] [rbp-28h] BYREF
  DWORD Buffer; // [rsp+44h] [rbp-24h] BYREF
  __int128 v28; // [rsp+48h] [rbp-20h] BYREF
  __int64 v29; // [rsp+58h] [rbp-10h]
  DWORD dwSupportedSchemes; // [rsp+B0h] [rbp+48h] BYREF
  LPVOID lpBuffer; // [rsp+B8h] [rbp+50h]
  DWORD pdwAuthTarget; // [rsp+C0h] [rbp+58h] BYREF
  DWORD dwBufferLength; // [rsp+C8h] [rbp+60h] BYREF

  lpBuffer = a2;
  dwBufferLength = 4;
  v2 = a2;
  dwSupportedSchemes = 0;
  dwFirstScheme = 0;
  v4 = (void *)*((_QWORD *)this + 9);
  pdwAuthTarget = 0;
  v29 = 0;
  v28 = 0;
  if ( !WinHttpQueryAuthSchemes(v4, &dwSupportedSchemes, &dwFirstScheme, &pdwAuthTarget) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    v7 = L"RetrySecureRequest: WinHttpQueryAuthSchemes Failed , error %x";
LABEL_5:
    AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 2u, 2u, v7, v6);
    return v6;
  }
  v8 = (void *)*((_QWORD *)this + 9);
  if ( v8 )
  {
    WinHttpCloseHandle(v8);
    *((_QWORD *)this + 9) = 0;
  }
  v9 = (void *)*((_QWORD *)this + 8);
  if ( v9 )
  {
    WinHttpCloseHandle(v9);
    *((_QWORD *)this + 8) = 0;
  }
  v10 = (void *)*((_QWORD *)this + 7);
  if ( v10 )
  {
    WinHttpCloseHandle(v10);
    *((_QWORD *)this + 7) = 0;
  }
  if ( !SetThreadToken(0, *((HANDLE *)this + 1)) )
  {
    v11 = GetLastError();
    v6 = v11;
    if ( v11 > 0 )
      v6 = (unsigned __int16)v11 | 0x80070000;
    v7 = L"RetrySecureRequest: SetThreadToken Failed , error %x";
    goto LABEL_5;
  }
  HTTPSession = WinHttpDownload::CreateHTTPSession(this, 0);
  v6 = HTTPSession;
  if ( HTTPSession >= 0 )
  {
    if ( !*((_DWORD *)this + 28)
      || (v13 = *((_QWORD *)this + 15)) == 0
      || (v14 = *((_QWORD *)this + 13),
          *(_QWORD *)&v28 = *((_QWORD *)this + 11),
          *((_QWORD *)&v28 + 1) = v13,
          v29 = v14,
          v6 = WinHttpDownload::SetProxy(this, (struct _WINHTTP_PROXY_INFO *)&v28),
          (v6 & 0x80000000) == 0) )
    {
      v15 = 0;
      v16 = 0;
      v17 = 0;
      while ( 1 )
      {
        v18 = 1;
        if ( v15 )
          break;
        if ( *v2 == 401 )
        {
          v19 = WinHttpDownload::ChooseAuthScheme((WinHttpDownload *)1, dwSupportedSchemes);
          v20 = v19;
          if ( !v19 )
            goto LABEL_31;
          if ( (v19 == 16 || v19 == 2)
            && (Buffer = v18, !WinHttpSetOption(*((HINTERNET *)this + 9), 0x4Du, &Buffer, 4u))
            || !WinHttpSetCredentials(*((HINTERNET *)this + 9), pdwAuthTarget, v20, 0, 0, 0) )
          {
LABEL_48:
            v23 = GetLastError();
            v6 = v23;
            if ( v23 > 0 )
              v6 = (unsigned __int16)v23 | 0x80070000;
            break;
          }
          v18 = 1;
          if ( v17 == 401 )
LABEL_31:
            v15 = v18;
          v2 = (unsigned int *)lpBuffer;
        }
        else if ( *v2 == 407 )
        {
          v16 = WinHttpDownload::ChooseAuthScheme((WinHttpDownload *)1, dwSupportedSchemes);
          if ( v17 == 407 )
            v15 = v18;
        }
        v17 = *v2;
        if ( v16 && !WinHttpSetCredentials(*((HINTERNET *)this + 9), v18, v16, 0, 0, 0) )
          goto LABEL_48;
        if ( !WinHttpSendRequest(*((HINTERNET *)this + 9), 0, 0, 0, 0, 0, 0) )
          goto LABEL_48;
        if ( !WinHttpReceiveResponse(*((HINTERNET *)this + 9), 0) )
          goto LABEL_48;
        v21 = (void *)*((_QWORD *)this + 9);
        dwBufferLength = 4;
        if ( !WinHttpQueryHeaders(v21, 0x20000013u, 0, v2, &dwBufferLength, 0) )
          goto LABEL_48;
        if ( *v2 != 401 && *v2 != 407 )
          break;
        if ( !WinHttpQueryAuthSchemes(*((HINTERNET *)this + 9), &dwSupportedSchemes, &dwFirstScheme, &pdwAuthTarget) )
        {
          v22 = GetLastError();
          v6 = v22;
          if ( v22 > 0 )
            v6 = (unsigned __int16)v22 | 0x80070000;
          LODWORD(pwszPassword) = v6;
          AxISEvents::DebugMsg(
            (AxISEvents *)&qword_180021AD8,
            2u,
            2u,
            L"RetrySecureRequest: WinHttpQueryAuthSchemes Failed , error %x",
            pwszPassword);
          break;
        }
      }
    }
  }
  else
  {
    AxISEvents::DebugMsg(
      (AxISEvents *)&qword_180021AD8,
      2u,
      2u,
      L"Could not create a new WinHTTP session during retry, error %x",
      HTTPSession);
  }
  RevertToSelf();
  return v6;
}

```

## disassembly

```asm
0x180012c24  mov     [rsp-40h+lpBuffer], rdx
0x180012c29  push    rbp
0x180012c2a  push    rbx
0x180012c2b  push    rsi
0x180012c2c  push    rdi
0x180012c2d  push    r12
0x180012c2f  push    r13
0x180012c31  push    r14
0x180012c33  push    r15
0x180012c35  mov     rbp, rsp
0x180012c38  sub     rsp, 68h
0x180012c3c  xor     esi, esi
0x180012c3e  mov     [rbp+dwBufferLength], 4
0x180012c45  mov     r14, rdx
0x180012c48  mov     [rbp+dwSupportedSchemes], esi
0x180012c4b  mov     rdi, rcx
0x180012c4e  mov     [rbp+dwFirstScheme], esi
0x180012c51  mov     rcx, [rcx+48h]; hRequest
0x180012c55  lea     rdx, [rbp+dwSupportedSchemes]; lpdwSupportedSchemes
0x180012c59  xorps   xmm0, xmm0
0x180012c5c  mov     [rbp+pdwAuthTarget], esi
0x180012c5f  xor     eax, eax
0x180012c61  lea     r9, [rbp+pdwAuthTarget]; pdwAuthTarget
0x180012c65  lea     r8, [rbp+dwFirstScheme]; lpdwFirstScheme
0x180012c69  mov     [rbp+var_10], rax
0x180012c6d  movups  [rbp+var_20], xmm0
0x180012c71  call    cs:__imp_WinHttpQueryAuthSchemes
0x180012c77  test    eax, eax
0x180012c79  jnz     short loc_180012CB6
0x180012c7b  call    cs:__imp_GetLastError
0x180012c81  mov     ebx, eax
0x180012c83  test    eax, eax
0x180012c85  jle     short loc_180012C90
0x180012c87  movzx   ebx, ax
0x180012c8a  or      ebx, 80070000h
0x180012c90  lea     r9, aRetrysecurereq_0; "RetrySecureRequest: WinHttpQueryAuthSch"...
0x180012c97  mov     esi, 2
0x180012c9c  mov     dword ptr [rsp+68h+pwszPassword], ebx
0x180012ca0  mov     r8d, esi; unsigned __int8
0x180012ca3  lea     rcx, qword_180021AD8; this
0x180012caa  mov     edx, esi; unsigned int
0x180012cac  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x180012cb1  jmp     loc_180012F83
0x180012cb6  mov     rcx, [rdi+48h]; hInternet
0x180012cba  test    rcx, rcx
0x180012cbd  jz      short loc_180012CC9
0x180012cbf  call    cs:__imp_WinHttpCloseHandle
0x180012cc5  mov     [rdi+48h], rsi
0x180012cc9  mov     rcx, [rdi+40h]; hInternet
0x180012ccd  test    rcx, rcx
0x180012cd0  jz      short loc_180012CDC
0x180012cd2  call    cs:__imp_WinHttpCloseHandle
0x180012cd8  mov     [rdi+40h], rsi
0x180012cdc  mov     rcx, [rdi+38h]; hInternet
0x180012ce0  test    rcx, rcx
0x180012ce3  jz      short loc_180012CEF
0x180012ce5  call    cs:__imp_WinHttpCloseHandle
0x180012ceb  mov     [rdi+38h], rsi
0x180012cef  mov     rdx, [rdi+8]; Token
0x180012cf3  xor     ecx, ecx; Thread
0x180012cf5  call    cs:__imp_SetThreadToken
0x180012cfb  test    eax, eax
0x180012cfd  jnz     short loc_180012D20
0x180012cff  call    cs:__imp_GetLastError
0x180012d05  mov     ebx, eax
0x180012d07  test    eax, eax
0x180012d09  jle     short loc_180012D14
0x180012d0b  movzx   ebx, ax
0x180012d0e  or      ebx, 80070000h
0x180012d14  lea     r9, aRetrysecurereq; "RetrySecureRequest: SetThreadToken Fail"...
0x180012d1b  jmp     loc_180012C97
0x180012d20  xor     edx, edx; int
0x180012d22  mov     rcx, rdi; this
0x180012d25  call    ?CreateHTTPSession@WinHttpDownload@@AEAAJH@Z; WinHttpDownload::CreateHTTPSession(int)
0x180012d2a  mov     ebx, eax
0x180012d2c  test    eax, eax
0x180012d2e  jns     short loc_180012D56
0x180012d30  mov     dword ptr [rsp+68h+pwszPassword], eax
0x180012d34  lea     r9, aCouldNotCreate; "Could not create a new WinHTTP session "...
0x180012d3b  mov     esi, 2
0x180012d40  mov     r8d, esi; unsigned __int8
0x180012d43  lea     rcx, qword_180021AD8; this
0x180012d4a  mov     edx, esi; unsigned int
0x180012d4c  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x180012d51  jmp     loc_180012F7D
0x180012d56  cmp     [rdi+70h], esi
0x180012d59  jz      short loc_180012D90
0x180012d5b  mov     rax, [rdi+78h]
0x180012d5f  test    rax, rax
0x180012d62  jz      short loc_180012D90
0x180012d64  movups  xmm0, xmmword ptr [rdi+58h]
0x180012d68  lea     rdx, [rbp+var_20]; struct _WINHTTP_PROXY_INFO *
0x180012d6c  mov     rcx, rdi; this
0x180012d6f  movsd   xmm1, qword ptr [rdi+68h]
0x180012d74  movups  [rbp+var_20], xmm0
0x180012d78  mov     qword ptr [rbp+var_20+8], rax
0x180012d7c  movsd   [rbp+var_10], xmm1
0x180012d81  call    ?SetProxy@WinHttpDownload@@AEAAJPEAU_WINHTTP_PROXY_INFO@@@Z; WinHttpDownload::SetProxy(_WINHTTP_PROXY_INFO *)
0x180012d86  mov     ebx, eax
0x180012d88  test    eax, eax
0x180012d8a  js      loc_180012F7D
0x180012d90  mov     r15d, esi
0x180012d93  mov     r13d, esi
0x180012d96  mov     r12d, esi
0x180012d99  mov     esi, 2
0x180012d9e  mov     ecx, 1; this
0x180012da3  test    r15d, r15d
0x180012da6  jnz     loc_180012F7D
0x180012dac  cmp     dword ptr [r14], 191h
0x180012db3  jnz     loc_180012F40
0x180012db9  mov     edx, [rbp+dwSupportedSchemes]; unsigned int
0x180012dbc  call    ?ChooseAuthScheme@WinHttpDownload@@AEAAKK@Z; WinHttpDownload::ChooseAuthScheme(ulong)
0x180012dc1  mov     r14d, eax
0x180012dc4  test    eax, eax
0x180012dc6  jz      short loc_180012E2F
0x180012dc8  cmp     eax, 10h
0x180012dcb  jz      short loc_180012DD1
0x180012dcd  cmp     eax, esi
0x180012dcf  jnz     short loc_180012DF4
0x180012dd1  mov     r9d, 4; dwBufferLength
0x180012dd7  mov     [rbp+Buffer], ecx
0x180012dda  mov     rcx, [rdi+48h]; hInternet
0x180012dde  lea     r8, [rbp+Buffer]; lpBuffer
0x180012de2  lea     edx, [r9+49h]; dwOption
0x180012de6  call    cs:__imp_WinHttpSetOption
0x180012dec  test    eax, eax
0x180012dee  jz      loc_180012F68
0x180012df4  mov     edx, [rbp+pdwAuthTarget]; AuthTargets
0x180012df7  xor     r9d, r9d; pwszUserName
0x180012dfa  mov     rcx, [rdi+48h]; hRequest
0x180012dfe  mov     r8d, r14d; AuthScheme
0x180012e01  mov     [rsp+68h+pAuthParams], 0; pAuthParams
0x180012e0a  mov     [rsp+68h+pwszPassword], 0; pwszPassword
0x180012e13  call    cs:__imp_WinHttpSetCredentials
0x180012e19  test    eax, eax
0x180012e1b  jz      loc_180012F68
0x180012e21  mov     ecx, 1
0x180012e26  cmp     r12d, 191h
0x180012e2d  jnz     short loc_180012E32
0x180012e2f  mov     r15d, ecx
0x180012e32  mov     r14, [rbp+lpBuffer]
0x180012e36  mov     r12d, [r14]
0x180012e39  test    r13d, r13d
0x180012e3c  jz      short loc_180012E6A
0x180012e3e  mov     edx, ecx; AuthTargets
0x180012e40  mov     [rsp+68h+pAuthParams], 0; pAuthParams
0x180012e49  mov     rcx, [rdi+48h]; hRequest
0x180012e4d  xor     r9d, r9d; pwszUserName
0x180012e50  mov     r8d, r13d; AuthScheme
0x180012e53  mov     [rsp+68h+pwszPassword], 0; pwszPassword
0x180012e5c  call    cs:__imp_WinHttpSetCredentials
0x180012e62  test    eax, eax
0x180012e64  jz      loc_180012F68
0x180012e6a  mov     rcx, [rdi+48h]; hRequest
0x180012e6e  xor     r9d, r9d; lpOptional
0x180012e71  mov     [rsp+68h+dwContext], 0; dwContext
0x180012e7a  xor     r8d, r8d; dwHeadersLength
0x180012e7d  mov     dword ptr [rsp+68h+pAuthParams], 0; dwTotalLength
0x180012e85  xor     edx, edx; lpszHeaders
0x180012e87  mov     dword ptr [rsp+68h+pwszPassword], 0; dwOptionalLength
0x180012e8f  call    cs:__imp_WinHttpSendRequest
0x180012e95  test    eax, eax
0x180012e97  jz      loc_180012F68
0x180012e9d  mov     rcx, [rdi+48h]; hRequest
0x180012ea1  xor     edx, edx; lpReserved
0x180012ea3  call    cs:__imp_WinHttpReceiveResponse
0x180012ea9  test    eax, eax
0x180012eab  jz      loc_180012F68
0x180012eb1  mov     rcx, [rdi+48h]; hRequest
0x180012eb5  lea     rax, [rbp+dwBufferLength]
0x180012eb9  mov     [rsp+68h+pAuthParams], 0; lpdwIndex
0x180012ec2  mov     r9, r14; lpBuffer
0x180012ec5  xor     r8d, r8d; pwszName
0x180012ec8  mov     [rsp+68h+pwszPassword], rax; lpdwBufferLength
0x180012ecd  mov     edx, 20000013h; dwInfoLevel
0x180012ed2  mov     [rbp+dwBufferLength], 4
0x180012ed9  call    cs:__imp_WinHttpQueryHeaders
0x180012edf  test    eax, eax
0x180012ee1  jz      loc_180012F68
0x180012ee7  cmp     dword ptr [r14], 191h
0x180012eee  jz      short loc_180012EFD
0x180012ef0  cmp     dword ptr [r14], 197h
0x180012ef7  jnz     loc_180012F7D
0x180012efd  mov     rcx, [rdi+48h]; hRequest
0x180012f01  lea     r9, [rbp+pdwAuthTarget]; pdwAuthTarget
0x180012f05  lea     r8, [rbp+dwFirstScheme]; lpdwFirstScheme
0x180012f09  lea     rdx, [rbp+dwSupportedSchemes]; lpdwSupportedSchemes
0x180012f0d  call    cs:__imp_WinHttpQueryAuthSchemes
0x180012f13  test    eax, eax
0x180012f15  jnz     loc_180012D9E
0x180012f1b  call    cs:__imp_GetLastError
0x180012f21  mov     ebx, eax
0x180012f23  test    eax, eax
0x180012f25  jle     short loc_180012F30
0x180012f27  movzx   ebx, ax
0x180012f2a  or      ebx, 80070000h
0x180012f30  mov     dword ptr [rsp+68h+pwszPassword], ebx
0x180012f34  lea     r9, aRetrysecurereq_0; "RetrySecureRequest: WinHttpQueryAuthSch"...
0x180012f3b  jmp     loc_180012D40
0x180012f40  cmp     dword ptr [r14], 197h
0x180012f47  jnz     loc_180012E36
0x180012f4d  mov     edx, [rbp+dwSupportedSchemes]; unsigned int
0x180012f50  call    ?ChooseAuthScheme@WinHttpDownload@@AEAAKK@Z; WinHttpDownload::ChooseAuthScheme(ulong)
0x180012f55  cmp     r12d, 197h
0x180012f5c  mov     r13d, eax
0x180012f5f  cmovz   r15d, ecx
0x180012f63  jmp     loc_180012E36
0x180012f68  call    cs:__imp_GetLastError
0x180012f6e  mov     ebx, eax
0x180012f70  test    eax, eax
0x180012f72  jle     short loc_180012F7D
0x180012f74  movzx   ebx, ax
0x180012f77  or      ebx, 80070000h
0x180012f7d  call    cs:__imp_RevertToSelf
0x180012f83  mov     eax, ebx
0x180012f85  add     rsp, 68h
0x180012f89  pop     r15
0x180012f8b  pop     r14
0x180012f8d  pop     r13
0x180012f8f  pop     r12
0x180012f91  pop     rdi
0x180012f92  pop     rsi
0x180012f93  pop     rbx
0x180012f94  pop     rbp
0x180012f95  retn
```
