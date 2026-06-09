# ConvertSocketAddrToStringW(sockaddr const *,int,ushort *,IRequestContext *)

- ea: `0x1800a8e00`
- end: `0x1800a8feb`
- name: `?ConvertSocketAddrToStringW@@YAHPEBUsockaddr@@HPEAGPEAVIRequestContext@@@Z`
- size: `491`
- prototype: `__int64 __fastcall(SOCKADDR *pSockaddr, socklen_t SockaddrLength, LPWSTR lpWideCharStr, struct IRequestContext *)`
- caller_count: `6`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x18008d4c4`
- `0x1800a843c`
- `0x1800a88ec`
- `0x18013be60`
- `0x18016c4a8`
- `0x1801781d4`

## callees

- `0x180005d10`
- `0x1800a8e00`
- `0x1801123a8`
- `0x1801ba152`
- `0x1801ba1b0`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a8f46`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a8f46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a8fc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a8fc5`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800a8ebf`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800a8ebf`
- `WS2_32!getnameinfo` at `0x1800a8e91`
- `WS2_32!getnameinfo` at `0x1800a8e91`
- `WS2_32!__imp_WSAStartup` at `0x1800a8e5a`
- `WS2_32!__imp_WSAStartup` at `0x1800a8e5a`
- `WS2_32!__imp_WSACleanup` at `0x1800a8ecd`
- `WS2_32!__imp_WSACleanup` at `0x1800a8fba`
- `WS2_32!__imp_WSACleanup` at `0x1800a8ecd`
- `WS2_32!__imp_WSACleanup` at `0x1800a8fba`

## pseudocode

```c
__int64 __fastcall ConvertSocketAddrToStringW(
        SOCKADDR *pSockaddr,
        socklen_t SockaddrLength,
        LPWSTR lpWideCharStr,
        struct IRequestContext *a4)
{
  unsigned int v8; // eax
  DWORD LastError; // edi
  const unsigned __int16 *v11; // r8
  __int64 v12; // rdx
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  struct WSAData WSAData; // [rsp+40h] [rbp-228h] BYREF
  CHAR pNodeBuffer[80]; // [rsp+1E0h] [rbp-88h] BYREF

  if ( pSockaddr )
  {
    if ( lpWideCharStr )
    {
      memset_0(&WSAData, 0, sizeof(WSAData));
      v8 = WSAStartup(0x202u, &WSAData);
      LastError = v8;
      if ( v8 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_06af4c8933ac363c12ded1360bf8d182_Traceguids, v8);
        goto LABEL_11;
      }
      LastError = getnameinfo(pSockaddr, SockaddrLength, pNodeBuffer, 0x41u, 0, 0, 2);
      if ( LastError )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 )
          goto LABEL_21;
        v14 = 37;
      }
      else
      {
        if ( MultiByteToWideChar(3u, 0, pNodeBuffer, 65, lpWideCharStr, 65) )
        {
          WSACleanup();
          return LastError + 1;
        }
        LastError = GetLastError();
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
          goto LABEL_21;
        v14 = 38;
      }
      WPP_SF_d(v13[2], v14, &WPP_06af4c8933ac363c12ded1360bf8d182_Traceguids, LastError);
LABEL_21:
      WSACleanup();
LABEL_11:
      if ( a4 )
        (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a4 + 72LL))(a4, LastError);
      SetLastError(LastError);
      return 0;
    }
    v11 = L"1209";
    v12 = 1209;
  }
  else
  {
    v11 = L"1208";
    v12 = 1208;
  }
  WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmanutils.cpp", v12, v11, 0x54Fu, a4);
  return 0;
}

```

## disassembly

```asm
0x1800a8e00  push    rbx
0x1800a8e02  push    rbp
0x1800a8e03  push    rsi
0x1800a8e04  push    rdi
0x1800a8e05  push    r14
0x1800a8e07  sub     rsp, 240h
0x1800a8e0e  mov     rax, cs:__security_cookie
0x1800a8e15  xor     rax, rsp
0x1800a8e18  mov     [rsp+268h+var_38], rax
0x1800a8e20  mov     rbx, r9
0x1800a8e23  mov     rsi, r8
0x1800a8e26  mov     r14d, edx
0x1800a8e29  mov     rbp, rcx
0x1800a8e2c  test    rcx, rcx
0x1800a8e2f  jz      loc_1800A8F4E
0x1800a8e35  test    r8, r8
0x1800a8e38  jz      loc_1800A8EF4
0x1800a8e3e  xor     edx, edx; Val
0x1800a8e40  lea     rcx, [rsp+268h+WSAData]; void *
0x1800a8e45  mov     r8d, 198h; Size
0x1800a8e4b  call    memset_0
0x1800a8e50  mov     ecx, 202h; wVersionRequested
0x1800a8e55  lea     rdx, [rsp+268h+WSAData]; lpWSAData
0x1800a8e5a  call    cs:__imp_WSAStartup
0x1800a8e60  mov     edi, eax
0x1800a8e62  test    eax, eax
0x1800a8e64  jnz     loc_1800A8F1B
0x1800a8e6a  mov     [rsp+268h+Flags], 2; Flags
0x1800a8e72  lea     r9d, [rax+41h]; NodeBufferSize
0x1800a8e76  mov     [rsp+268h+ServiceBufferSize], eax; ServiceBufferSize
0x1800a8e7a  lea     r8, [rsp+268h+pNodeBuffer]; pNodeBuffer
0x1800a8e82  mov     edx, r14d; SockaddrLength
0x1800a8e85  mov     [rsp+268h+pServiceBuffer], 0; pServiceBuffer
0x1800a8e8e  mov     rcx, rbp; pSockaddr
0x1800a8e91  call    cs:__imp_getnameinfo
0x1800a8e97  mov     edi, eax
0x1800a8e99  test    eax, eax
0x1800a8e9b  jnz     loc_1800A8F7F
0x1800a8ea1  mov     [rsp+268h+ServiceBufferSize], 41h ; 'A'; cchWideChar
0x1800a8ea9  lea     r9d, [rax+41h]; cbMultiByte
0x1800a8ead  lea     r8, [rsp+268h+pNodeBuffer]; lpMultiByteStr
0x1800a8eb5  mov     [rsp+268h+pServiceBuffer], rsi; lpWideCharStr
0x1800a8eba  xor     edx, edx; dwFlags
0x1800a8ebc  lea     ecx, [rax+3]; CodePage
0x1800a8ebf  call    cs:__imp_MultiByteToWideChar
0x1800a8ec5  test    eax, eax
0x1800a8ec7  jz      loc_1800A8FC5
0x1800a8ecd  call    cs:__imp_WSACleanup
0x1800a8ed3  lea     eax, [rdi+1]
0x1800a8ed6  mov     rcx, [rsp+268h+var_38]
0x1800a8ede  xor     rcx, rsp; StackCookie
0x1800a8ee1  call    __security_check_cookie
0x1800a8ee6  add     rsp, 240h
0x1800a8eed  pop     r14
0x1800a8eef  pop     rdi
0x1800a8ef0  pop     rsi
0x1800a8ef1  pop     rbp
0x1800a8ef2  pop     rbx
0x1800a8ef3  retn
0x1800a8ef4  lea     r8, a1209; "1209"
0x1800a8efb  mov     edx, 4B9h; unsigned int
0x1800a8f00  mov     r9d, 54Fh; unsigned int
0x1800a8f06  mov     [rsp+268h+pServiceBuffer], rbx; struct IRequestContext *
0x1800a8f0b  lea     rcx, aOnecoreAdminWm_90; "onecore\\admin\\wmi\\wmx\\stdlib\\wsman"...
0x1800a8f12  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1800a8f17  xor     eax, eax
0x1800a8f19  jmp     short loc_1800A8ED6
0x1800a8f1b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a8f22  lea     rdx, WPP_GLOBAL_Control
0x1800a8f29  cmp     rcx, rdx
0x1800a8f2c  jnz     short loc_1800A8F5C
0x1800a8f2e  test    rbx, rbx
0x1800a8f31  jz      short loc_1800A8F44
0x1800a8f33  mov     rax, [rbx]
0x1800a8f36  mov     edx, edi
0x1800a8f38  mov     rcx, rbx
0x1800a8f3b  mov     rax, [rax+48h]
0x1800a8f3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8f44  mov     ecx, edi; dwErrCode
0x1800a8f46  call    cs:__imp_SetLastError
0x1800a8f4c  jmp     short loc_1800A8F17
0x1800a8f4e  lea     r8, a1208; "1208"
0x1800a8f55  mov     edx, 4B8h
0x1800a8f5a  jmp     short loc_1800A8F00
0x1800a8f5c  test    dword ptr [rcx+1Ch], 800h
0x1800a8f63  jz      short loc_1800A8F2E
0x1800a8f65  mov     rcx, [rcx+10h]
0x1800a8f69  lea     r8, WPP_06af4c8933ac363c12ded1360bf8d182_Traceguids
0x1800a8f70  mov     edx, 24h ; '$'
0x1800a8f75  mov     r9d, edi
0x1800a8f78  call    WPP_SF_d
0x1800a8f7d  jmp     short loc_1800A8F2E
0x1800a8f7f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a8f86  lea     rdx, WPP_GLOBAL_Control
0x1800a8f8d  cmp     rcx, rdx
0x1800a8f90  jz      short loc_1800A8FBA
0x1800a8f92  test    dword ptr [rcx+1Ch], 800h
0x1800a8f99  jz      short loc_1800A8FBA
0x1800a8f9b  mov     edx, 25h ; '%'
0x1800a8fa0  jmp     short loc_1800A8FA7
0x1800a8fa2  mov     edx, 26h ; '&'
0x1800a8fa7  mov     rcx, [rcx+10h]
0x1800a8fab  lea     r8, WPP_06af4c8933ac363c12ded1360bf8d182_Traceguids
0x1800a8fb2  mov     r9d, edi
0x1800a8fb5  call    WPP_SF_d
0x1800a8fba  call    cs:__imp_WSACleanup
0x1800a8fc0  jmp     loc_1800A8F2E
0x1800a8fc5  call    cs:__imp_GetLastError
0x1800a8fcb  mov     edi, eax
0x1800a8fcd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a8fd4  lea     rdx, WPP_GLOBAL_Control
0x1800a8fdb  cmp     rcx, rdx
0x1800a8fde  jz      short loc_1800A8FBA
0x1800a8fe0  test    dword ptr [rcx+1Ch], 200h
0x1800a8fe7  jz      short loc_1800A8FBA
0x1800a8fe9  jmp     short loc_1800A8FA2
```
