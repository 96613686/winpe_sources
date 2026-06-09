# CWSConnection::Initialize(WS_REPORT_TYPE,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x18012521c`
- end: `0x1801255d2`
- name: `?Initialize@CWSConnection@@QEAAJW4WS_REPORT_TYPE@@PEBG111@Z`
- size: `950`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x18011de80`
- `0x18011f4d0`

## callees

- `0x18001be08`
- `0x18004cac4`
- `0x18009688c`
- `0x1800a98c0`
- `0x1800aa5ac`
- `0x18012521c`
- `0x180125608`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18012555c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18012555c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801252c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801252fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012536f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801254ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801252c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801252fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012536f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801254ea`
- `WINHTTP!WinHttpSetStatusCallback` at `0x180125542`
- `WINHTTP!WinHttpSetStatusCallback` at `0x180125542`
- `WINHTTP!WinHttpOpen` at `0x1801252b7`
- `WINHTTP!WinHttpOpen` at `0x1801252b7`
- `WINHTTP!WinHttpCrackUrl` at `0x18012540a`
- `WINHTTP!WinHttpCrackUrl` at `0x18012540a`
- `WINHTTP!WinHttpConnect` at `0x18012544c`
- `WINHTTP!WinHttpConnect` at `0x18012544c`
- `WINHTTP!WinHttpOpenRequest` at `0x1801254db`
- `WINHTTP!WinHttpOpenRequest` at `0x1801254db`
- `WINHTTP!WinHttpSetOption` at `0x1801252f3`
- `WINHTTP!WinHttpSetOption` at `0x180125365`
- `WINHTTP!WinHttpSetOption` at `0x18012547e`
- `WINHTTP!WinHttpSetOption` at `0x1801252f3`
- `WINHTTP!WinHttpSetOption` at `0x180125365`
- `WINHTTP!WinHttpSetOption` at `0x18012547e`

## string_xrefs

- `0x180125331`: `onecoreuap\drivers\mobilepc\location\product\core\webserviceproxy\wsconn.cpp`

## pseudocode

```c
__int64 __fastcall CWSConnection::Initialize(__int64 a1, int a2, const WCHAR *a3, const WCHAR *a4)
{
  signed int inited; // ebx
  void *v9; // rax
  signed int v10; // eax
  signed int v11; // eax
  __int64 v12; // rdx
  void *v13; // rcx
  signed int v14; // eax
  __int64 v15; // rdx
  void *v16; // rax
  DWORD v17; // eax
  void *v18; // rax
  signed int LastError; // eax
  int v20; // edx
  int v21; // ecx
  HANDLE EventW; // rax
  LPCWSTR *ppwszAcceptTypes; // [rsp+28h] [rbp-D8h]
  DWORD v25; // [rsp+30h] [rbp-D0h]
  $BC2FB811D417144E831EE3AEA4A279C8 v26; // [rsp+40h] [rbp-C0h] BYREF
  $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+B0h] [rbp-50h] BYREF
  int Buffer; // [rsp+120h] [rbp+20h] BYREF
  int v29; // [rsp+124h] [rbp+24h] BYREF
  int v30; // [rsp+128h] [rbp+28h] BYREF
  WCHAR pswzServerName[264]; // [rsp+130h] [rbp+30h] BYREF
  WCHAR pwszObjectName[264]; // [rsp+340h] [rbp+240h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+598h] [rbp+498h]

  inited = 0;
  memset_0(&UrlComponents, 0, sizeof(UrlComponents));
  Buffer = 150000;
  if ( *(_QWORD *)(a1 + 16) || *(_QWORD *)(a1 + 24) || *(_QWORD *)(a1 + 32) )
    return (unsigned int)inited;
  *(_DWORD *)(a1 + 164) = a2;
  v9 = WinHttpOpen(L"LFSVC", 4u, 0, 0, 0x10000000u);
  *(_QWORD *)(a1 + 16) = v9;
  if ( !v9 )
    goto LABEL_5;
  if ( WinHttpSetOption(v9, 2u, &Buffer, 4u) )
  {
    v13 = *(void **)(a1 + 16);
    v29 = 256;
    if ( WinHttpSetOption(v13, 0xC1u, &v29, 4u) )
    {
      memset_0(&v26, 0, sizeof(v26));
      v15 = -1;
      UrlComponents = v26;
      UrlComponents.dwStructSize = 104;
      UrlComponents.dwHostNameLength = 1;
      UrlComponents.dwUrlPathLength = 1;
      do
        ++v15;
      while ( a3[v15] );
      if ( !WinHttpCrackUrl(a3, v15, 0, &UrlComponents) )
        goto LABEL_5;
      inited = StringCchCopyNW(
                 pswzServerName,
                 0x104u,
                 (const unsigned __int16 *)UrlComponents.lpszHostName,
                 UrlComponents.dwHostNameLength);
      if ( inited < 0 )
        return (unsigned int)inited;
      v16 = WinHttpConnect(*(HINTERNET *)(a1 + 16), pswzServerName, UrlComponents.nPort, 0);
      *(_QWORD *)(a1 + 24) = v16;
      if ( !v16 )
        goto LABEL_5;
      if ( *(_DWORD *)(a1 + 164) != 7 )
      {
        v30 = 3;
        if ( !WinHttpSetOption(v16, 0x76u, &v30, 4u) )
          goto LABEL_5;
      }
      inited = StringCchCopyNW(
                 pwszObjectName,
                 0x104u,
                 (const unsigned __int16 *)UrlComponents.lpszUrlPath,
                 UrlComponents.dwUrlPathLength);
      if ( inited < 0 )
        return (unsigned int)inited;
      v17 = 0;
      if ( UrlComponents.nScheme == INTERNET_SCHEME_GOPHER )
        v17 = 0x800000;
      v18 = WinHttpOpenRequest(*(HINTERNET *)(a1 + 24), a4, pwszObjectName, 0, 0, 0, v17);
      *(_QWORD *)(a1 + 32) = v18;
      if ( !v18 )
      {
        LastError = GetLastError();
        inited = LastError;
        if ( LastError > 0 )
          inited = (unsigned __int16)LastError | 0x80070000;
        if ( (byte_1801E39C3 & 2) != 0 )
          McTemplateU0dqdqd_EventWriteTransfer(v21, v20, *(_DWORD *)(a1 + 156), *(_DWORD *)(a1 + 160), 0, 1, inited);
        return (unsigned int)inited;
      }
      if ( WinHttpSetStatusCallback(v18, CWSConnection::AsyncRequestCallback, 0x97E0000u, 0) == (WINHTTP_STATUS_CALLBACK)-1LL )
      {
LABEL_5:
        v10 = GetLastError();
        inited = v10;
        if ( v10 > 0 )
          return (unsigned __int16)v10 | 0x80070000;
        return (unsigned int)inited;
      }
      EventW = CreateEventW(0, 0, 0, 0);
      *(_QWORD *)(a1 + 88) = EventW;
      if ( EventW )
      {
        inited = CWSConnection::InternalInitCallbackEvents((CWSConnection *)a1);
        if ( inited >= 0 )
        {
          *(_QWORD *)(*(_QWORD *)(a1 + 80) + 56LL) = *(_QWORD *)(a1 + 32);
          *(_DWORD *)(*(_QWORD *)(a1 + 80) + 64LL) = *(_DWORD *)(a1 + 156);
          *(_DWORD *)(*(_QWORD *)(a1 + 80) + 68LL) = *(_DWORD *)(a1 + 160);
        }
      }
      else
      {
        return (unsigned int)-2147024890;
      }
    }
    else
    {
      v14 = GetLastError();
      inited = v14;
      if ( v14 > 0 )
        inited = (unsigned __int16)v14 | 0x80070000;
      if ( inited < 0 )
      {
        v12 = 182;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v11 = GetLastError();
    inited = v11;
    if ( v11 > 0 )
      inited = (unsigned __int16)v11 | 0x80070000;
    if ( inited < 0 )
    {
      v12 = 172;
LABEL_12:
      LODWORD(ppwszAcceptTypes) = inited;
      wil::details::in1diag5::_Log_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\webserviceproxy\\wsconn.cpp",
        "CWSConnection::Initialize",
        "HRESULT_FROM_WIN32(GetLastError())",
        (const char *)ppwszAcceptTypes,
        v25);
    }
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18012521c  mov     [rsp-8+arg_8], rbx
0x180125221  push    rbp
0x180125222  push    rsi
0x180125223  push    rdi
0x180125224  push    r12
0x180125226  push    r13
0x180125228  push    r14
0x18012522a  push    r15
0x18012522c  lea     rbp, [rsp-460h]
0x180125234  sub     rsp, 560h
0x18012523b  mov     rax, cs:__security_cookie
0x180125242  xor     rax, rsp
0x180125245  mov     [rbp+490h+var_40], rax
0x18012524c  xor     r12d, r12d
0x18012524f  mov     r14, r8
0x180125252  mov     esi, edx
0x180125254  mov     rdi, rcx
0x180125257  xor     edx, edx; Val
0x180125259  lea     rcx, [rbp+490h+UrlComponents]; void *
0x18012525d  mov     r15, r9
0x180125260  mov     ebx, r12d
0x180125263  lea     r13d, [r12+68h]
0x180125268  mov     r8d, r13d; Size
0x18012526b  call    memset_0
0x180125270  mov     [rbp+490h+Buffer], 249F0h
0x180125277  cmp     [rdi+10h], r12
0x18012527b  jnz     loc_1801255A6
0x180125281  cmp     [rdi+18h], r12
0x180125285  jnz     loc_1801255A6
0x18012528b  cmp     [rdi+20h], r12
0x18012528f  jnz     loc_1801255A6
0x180125295  mov     [rdi+0A4h], esi
0x18012529b  lea     rcx, pszAgentW; "LFSVC"
0x1801252a2  lea     esi, [r12+4]
0x1801252a7  mov     [rsp+590h+dwFlags], 10000000h; dwFlags
0x1801252af  mov     edx, esi; dwAccessType
0x1801252b1  xor     r9d, r9d; pszProxyBypassW
0x1801252b4  xor     r8d, r8d; pszProxyW
0x1801252b7  call    cs:__imp_WinHttpOpen
0x1801252bd  mov     [rdi+10h], rax
0x1801252c1  test    rax, rax
0x1801252c4  jnz     short loc_1801252E4
0x1801252c6  call    cs:__imp_GetLastError
0x1801252cc  mov     ebx, eax
0x1801252ce  test    eax, eax
0x1801252d0  jle     loc_1801255A6
0x1801252d6  movzx   ebx, ax
0x1801252d9  or      ebx, 80070000h
0x1801252df  jmp     loc_1801255A6
0x1801252e4  mov     r9d, esi; dwBufferLength
0x1801252e7  lea     r8, [rbp+490h+Buffer]; lpBuffer
0x1801252eb  mov     edx, 2; dwOption
0x1801252f0  mov     rcx, rax; hInternet
0x1801252f3  call    cs:__imp_WinHttpSetOption
0x1801252f9  test    eax, eax
0x1801252fb  jnz     short loc_18012534E
0x1801252fd  call    cs:__imp_GetLastError
0x180125303  mov     ebx, eax
0x180125305  test    eax, eax
0x180125307  jle     short loc_180125312
0x180125309  movzx   ebx, ax
0x18012530c  or      ebx, 80070000h
0x180125312  test    ebx, ebx
0x180125314  jns     loc_1801255A6
0x18012531a  mov     edx, 0ACh; void *
0x18012531f  mov     rcx, [rbp+498h]; this
0x180125326  lea     rax, aHresultFromWin; "HRESULT_FROM_WIN32(GetLastError())"
0x18012532d  mov     dword ptr [rsp+590h+ppwszAcceptTypes], ebx; char *
0x180125331  lea     r8, aOnecoreuapDriv_7; "onecoreuap\\drivers\\mobilepc\\location"...
0x180125338  lea     r9, aCwsconnectionI; "CWSConnection::Initialize"
0x18012533f  mov     qword ptr [rsp+590h+dwFlags], rax; char *
0x180125344  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x180125349  jmp     loc_1801255A6
0x18012534e  mov     rcx, [rdi+10h]; hInternet
0x180125352  lea     r8, [rbp+490h+var_46C]; lpBuffer
0x180125356  mov     r9d, esi; dwBufferLength
0x180125359  mov     [rbp+490h+var_46C], 100h
0x180125360  mov     edx, 0C1h; dwOption
0x180125365  call    cs:__imp_WinHttpSetOption
0x18012536b  test    eax, eax
0x18012536d  jnz     short loc_180125393
0x18012536f  call    cs:__imp_GetLastError
0x180125375  mov     ebx, eax
0x180125377  test    eax, eax
0x180125379  jle     short loc_180125384
0x18012537b  movzx   ebx, ax
0x18012537e  or      ebx, 80070000h
0x180125384  test    ebx, ebx
0x180125386  jns     loc_1801255A6
0x18012538c  mov     edx, 0B6h
0x180125391  jmp     short loc_18012531F
0x180125393  mov     r8, r13; Size
0x180125396  lea     rcx, [rsp+590h+var_550]; void *
0x18012539b  xor     edx, edx; Val
0x18012539d  call    memset_0
0x1801253a2  movups  xmm0, [rsp+590h+var_550]
0x1801253a7  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1801253ab  movups  xmm1, [rsp+590h+var_540]
0x1801253b0  movaps  xmmword ptr [rbp+490h+UrlComponents.dwStructSize], xmm0
0x1801253b4  movups  xmm0, [rsp+590h+var_530]
0x1801253b9  mov     [rbp+490h+UrlComponents.dwStructSize], r13d
0x1801253bd  mov     r13d, 1
0x1801253c3  movaps  xmmword ptr [rbp+490h+UrlComponents.dwSchemeLength], xmm1
0x1801253c7  movups  xmm1, [rsp+590h+var_520]
0x1801253cc  movaps  xmmword ptr [rbp+490h+UrlComponents.dwHostNameLength], xmm0
0x1801253d0  movups  xmm0, [rbp+490h+var_510]
0x1801253d4  mov     [rbp+490h+UrlComponents.dwHostNameLength], r13d
0x1801253d8  movaps  xmmword ptr [rbp+490h+UrlComponents.dwUserNameLength], xmm1
0x1801253dc  movups  xmm1, [rbp+490h+var_500]
0x1801253e0  movaps  xmmword ptr [rbp+490h+UrlComponents.dwPasswordLength], xmm0
0x1801253e4  movsd   xmm0, [rbp+490h+var_4F0]
0x1801253e9  movaps  xmmword ptr [rbp+490h+UrlComponents.dwUrlPathLength], xmm1
0x1801253ed  movsd   qword ptr [rbp+490h+UrlComponents.dwExtraInfoLength], xmm0
0x1801253f2  mov     [rbp+490h+UrlComponents.dwUrlPathLength], r13d
0x1801253f6  inc     rdx; dwUrlLength
0x1801253f9  cmp     [r14+rdx*2], r12w
0x1801253fe  jnz     short loc_1801253F6
0x180125400  lea     r9, [rbp+490h+UrlComponents]; lpUrlComponents
0x180125404  xor     r8d, r8d; dwFlags
0x180125407  mov     rcx, r14; pwszUrl
0x18012540a  call    cs:__imp_WinHttpCrackUrl
0x180125410  test    eax, eax
0x180125412  jz      loc_1801252C6
0x180125418  mov     r9d, [rbp+490h+UrlComponents.dwHostNameLength]; unsigned __int64
0x18012541c  lea     rcx, [rbp+490h+pswzServerName]; unsigned __int16 *
0x180125420  mov     r8, [rbp+490h+UrlComponents.lpszHostName]; unsigned __int16 *
0x180125424  mov     r14d, 104h
0x18012542a  mov     edx, r14d; unsigned __int64
0x18012542d  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180125432  mov     ebx, eax
0x180125434  test    eax, eax
0x180125436  js      loc_1801255A6
0x18012543c  movzx   r8d, [rbp+490h+UrlComponents.nPort]; nServerPort
0x180125441  lea     rdx, [rbp+490h+pswzServerName]; pswzServerName
0x180125445  mov     rcx, [rdi+10h]; hSession
0x180125449  xor     r9d, r9d; dwReserved
0x18012544c  call    cs:__imp_WinHttpConnect
0x180125452  mov     [rdi+18h], rax
0x180125456  test    rax, rax
0x180125459  jz      loc_1801252C6
0x18012545f  cmp     dword ptr [rdi+0A4h], 7
0x180125466  jz      short loc_18012548C
0x180125468  mov     r9d, esi; dwBufferLength
0x18012546b  mov     [rbp+490h+var_468], 3
0x180125472  lea     r8, [rbp+490h+var_468]; lpBuffer
0x180125476  mov     edx, 76h ; 'v'; dwOption
0x18012547b  mov     rcx, rax; hInternet
0x18012547e  call    cs:__imp_WinHttpSetOption
0x180125484  test    eax, eax
0x180125486  jz      loc_1801252C6
0x18012548c  mov     r9d, [rbp+490h+UrlComponents.dwUrlPathLength]; unsigned __int64
0x180125490  lea     rcx, [rbp+490h+pwszObjectName]; unsigned __int16 *
0x180125497  mov     r8, [rbp+490h+UrlComponents.lpszUrlPath]; unsigned __int16 *
0x18012549b  mov     rdx, r14; unsigned __int64
0x18012549e  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1801254a3  mov     ebx, eax
0x1801254a5  test    eax, eax
0x1801254a7  js      loc_1801255A6
0x1801254ad  cmp     [rbp+490h+UrlComponents.nScheme], 2
0x1801254b1  lea     r8, [rbp+490h+pwszObjectName]; pwszObjectName
0x1801254b8  mov     eax, r12d
0x1801254bb  mov     ecx, 800000h
0x1801254c0  cmovz   eax, ecx
0x1801254c3  mov     rdx, r15; pwszVerb
0x1801254c6  mov     rcx, [rdi+18h]; hConnect
0x1801254ca  xor     r9d, r9d; pwszVersion
0x1801254cd  mov     [rsp+590h+var_560], eax; dwFlags
0x1801254d1  mov     [rsp+590h+ppwszAcceptTypes], r12; ppwszAcceptTypes
0x1801254d6  mov     qword ptr [rsp+590h+dwFlags], r12; pwszReferrer
0x1801254db  call    cs:__imp_WinHttpOpenRequest
0x1801254e1  mov     [rdi+20h], rax
0x1801254e5  test    rax, rax
0x1801254e8  jnz     short loc_18012552F
0x1801254ea  call    cs:__imp_GetLastError
0x1801254f0  mov     ebx, eax
0x1801254f2  test    eax, eax
0x1801254f4  jle     short loc_1801254FF
0x1801254f6  movzx   ebx, ax
0x1801254f9  or      ebx, 80070000h
0x1801254ff  test    cs:byte_1801E39C3, 2
0x180125506  jz      loc_1801255A6
0x18012550c  mov     r9d, [rdi+0A0h]
0x180125513  mov     r8d, [rdi+9Ch]
0x18012551a  mov     [rsp+590h+var_560], ebx
0x18012551e  mov     dword ptr [rsp+590h+ppwszAcceptTypes], r13d
0x180125523  mov     [rsp+590h+dwFlags], r12d
0x180125528  call    McTemplateU0dqdqd_EventWriteTransfer
0x18012552d  jmp     short loc_1801255A6
0x18012552f  xor     r9d, r9d; dwReserved
0x180125532  lea     rdx, ?AsyncRequestCallback@CWSConnection@@SAXPEAX_KK0K@Z; lpfnInternetCallback
0x180125539  mov     r8d, 97E0000h; dwNotificationFlags
0x18012553f  mov     rcx, rax; hInternet
0x180125542  call    cs:__imp_WinHttpSetStatusCallback
0x180125548  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18012554c  jz      loc_1801252C6
0x180125552  xor     r9d, r9d; lpName
0x180125555  xor     r8d, r8d; bInitialState
0x180125558  xor     edx, edx; bManualReset
0x18012555a  xor     ecx, ecx; lpEventAttributes
0x18012555c  call    cs:__imp_CreateEventW
0x180125562  mov     [rdi+58h], rax
0x180125566  test    rax, rax
0x180125569  jnz     short loc_180125572
0x18012556b  mov     ebx, 80070006h
0x180125570  jmp     short loc_1801255A6
0x180125572  mov     rcx, rdi; this
0x180125575  call    ?InternalInitCallbackEvents@CWSConnection@@AEAAJXZ; CWSConnection::InternalInitCallbackEvents(void)
0x18012557a  mov     ebx, eax
0x18012557c  test    eax, eax
0x18012557e  js      short loc_1801255A6
0x180125580  mov     rcx, [rdi+50h]
0x180125584  mov     rax, [rdi+20h]
0x180125588  mov     [rcx+38h], rax
0x18012558c  mov     rcx, [rdi+50h]
0x180125590  mov     eax, [rdi+9Ch]
0x180125596  mov     [rcx+40h], eax
0x180125599  mov     rcx, [rdi+50h]
0x18012559d  mov     eax, [rdi+0A0h]
0x1801255a3  mov     [rcx+44h], eax
0x1801255a6  mov     eax, ebx
0x1801255a8  mov     rcx, [rbp+490h+var_40]
0x1801255af  xor     rcx, rsp; StackCookie
0x1801255b2  call    __security_check_cookie
0x1801255b7  mov     rbx, [rsp+590h+arg_8]
0x1801255bf  add     rsp, 560h
0x1801255c6  pop     r15
0x1801255c8  pop     r14
0x1801255ca  pop     r13
0x1801255cc  pop     r12
0x1801255ce  pop     rdi
0x1801255cf  pop     rsi
0x1801255d0  pop     rbp
0x1801255d1  retn
```
