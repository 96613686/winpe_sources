# SendRequestWithAuthRetry(void *,wchar_t const *,void *,void *,wchar_t const *,ulong,void *,ulong,ulong,void *)

- ea: `0x140039278`
- end: `0x140039695`
- name: `?SendRequestWithAuthRetry@@YAJPEAXPEB_W001K0KK0@Z`
- size: `1053`
- prototype: `int(void *, const wchar_t *, void *, void *, const wchar_t *, unsigned int, void *, unsigned int, unsigned int, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140031d1c`

## callees

- `0x1400154b4`
- `0x140039190`
- `0x140039278`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140039309`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003935f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400395af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140039669`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140039309`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003935f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400395af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140039669`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1400392da`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1400392da`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14003965f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14003965f`
- `WINHTTP!WinHttpQueryHeaders` at `0x140039497`
- `WINHTTP!WinHttpQueryHeaders` at `0x140039497`
- `WINHTTP!WinHttpReceiveResponse` at `0x140039469`
- `WINHTTP!WinHttpReceiveResponse` at `0x140039469`
- `WINHTTP!WinHttpQueryAuthSchemes` at `0x140039544`
- `WINHTTP!WinHttpQueryAuthSchemes` at `0x140039544`
- `WINHTTP!WinHttpSendRequest` at `0x140039434`
- `WINHTTP!WinHttpSendRequest` at `0x140039434`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x1400392ff`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x1400392ff`
- `WINHTTP!WinHttpSetOption` at `0x140039355`
- `WINHTTP!WinHttpSetOption` at `0x1400393cf`
- `WINHTTP!WinHttpSetOption` at `0x140039355`
- `WINHTTP!WinHttpSetOption` at `0x1400393cf`

## string_xrefs

- `0x1400393f7`: `Sending request to %ws. ImpersonatedAsUser : %ws`
- `0x140039568`: `Will impersonate the next time. Status code was %d, AuthSchemes to use: 0x%lx`
- `0x14003958d`: `Send succeeded. Impersonate flags: %lu`

## pseudocode

```c
__int64 __fastcall SendRequestWithAuthRetry(
        void *a1,
        const wchar_t *a2,
        void *a3,
        void *a4,
        const wchar_t *lpszHeaders,
        DWORD dwHeadersLength)
{
  bool v7; // r14
  BOOL v8; // eax
  signed int LastError; // eax
  signed int v10; // ebx
  int v11; // edi
  signed int v12; // eax
  int v13; // eax
  int v14; // ecx
  __int64 *v15; // r8
  unsigned int v16; // ecx
  __int64 *v17; // rdx
  unsigned int v18; // eax
  __int64 *v19; // rdx
  DWORD dwOptionalLength[2]; // [rsp+20h] [rbp-40h]
  int v22; // [rsp+40h] [rbp-20h] BYREF
  int Buffer; // [rsp+44h] [rbp-1Ch] BYREF
  DWORD dwBufferLength; // [rsp+48h] [rbp-18h] BYREF
  DWORD dwSupportedSchemes; // [rsp+4Ch] [rbp-14h] BYREF
  DWORD pdwAuthTarget; // [rsp+50h] [rbp-10h] BYREF
  DWORD dwFirstScheme; // [rsp+54h] [rbp-Ch] BYREF

  v22 = 0;
  dwSupportedSchemes = 0;
  v7 = 0;
  if ( !a2 || !a3 || !a4 )
  {
    v10 = -2147024809;
    goto LABEL_46;
  }
  if ( a1 && (v8 = ImpersonateLoggedOnUser(a1), v7 = v8, !v8)
    || lpszHeaders && !WinHttpAddRequestHeaders(a4, lpszHeaders, dwHeadersLength, 0xA0000000) )
  {
    LastError = GetLastError();
LABEL_9:
    v10 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v10 = LastError;
    if ( v10 >= 0 )
      v10 = -2147418113;
    goto LABEL_46;
  }
  v11 = 0;
  while ( 1 )
  {
    dwBufferLength = 4;
    Buffer = 2;
    v22 = 0;
    if ( !WinHttpSetOption(a4, 0x4Du, &Buffer, 4u) )
      goto LABEL_16;
    WUTrace(0, 0, 32, 5, 0, L"Sending request to %ws using proxy.");
    if ( v11 )
    {
      dwBufferLength = 4;
      Buffer = (v11 & 2) != 0;
      if ( !WinHttpSetOption(a4, 0x4Du, &Buffer, 4u) )
        goto LABEL_16;
      WUTrace(0, 0, 32, 5, 0, L"Sending request to %ws. ImpersonatedAsUser : %ws");
    }
    if ( !WinHttpSendRequest(a4, 0, 0, 0, 0, 0, 0)
      || (WUTrace(0, 0, 32, 5, 0, L"Waiting for response."), !WinHttpReceiveResponse(a4, 0))
      || (dwBufferLength = 4, !WinHttpQueryHeaders(a4, 0x20000013u, 0, &v22, &dwBufferLength, 0)) )
    {
LABEL_16:
      v12 = GetLastError();
      v10 = (unsigned __int16)v12 | 0x80070000;
      if ( v12 <= 0 )
        v10 = v12;
      v13 = v22;
      if ( v10 >= 0 )
        v10 = -2147418113;
      goto LABEL_32;
    }
    v13 = v22;
    if ( v22 != 200 && v22 != 206 )
    {
      WUTrace(0, 0, 32, 4, 0, L"StatusCode for transaction returned from WinHttpQueryHeaders is %lu");
      LogExtendedWinHttpErrorMessage(a4);
      v13 = v22;
    }
    v10 = 0;
    if ( v13 == 401 )
      goto LABEL_34;
    if ( v13 != 407 )
    {
      WUTrace(0, 0, 32, 5, 0, L"Send succeeded. Impersonate flags: %lu");
      goto LABEL_45;
    }
LABEL_32:
    if ( v13 != 401 && v13 != 407 )
      goto LABEL_45;
LABEL_34:
    v14 = v11;
    if ( v13 == 401 )
      v11 |= 2u;
    if ( v13 == 407 )
      v11 |= 1u;
    if ( v14 == v11 )
      break;
    dwFirstScheme = 0;
    pdwAuthTarget = 0;
    if ( !WinHttpQueryAuthSchemes(a4, &dwSupportedSchemes, &dwFirstScheme, &pdwAuthTarget) )
    {
      LastError = GetLastError();
      goto LABEL_9;
    }
    WUTrace(0, 0, 32, 4, 0, L"Will impersonate the next time. Status code was %d, AuthSchemes to use: 0x%lx");
  }
  v10 = -2145107945;
  if ( v13 == 407 )
    v10 = -2145107941;
LABEL_45:
  if ( v10 < 0 )
  {
LABEL_46:
    dwOptionalLength[0] = v10;
    WUTrace(0, 0, 32, 5, *(_QWORD *)dwOptionalLength, L"SendRequestWithAuthRetry failed for <%ws>");
    v15 = &qword_14006DB68;
    v16 = 0;
    v17 = &qword_14006DB68;
    while ( 1 )
    {
      v18 = *(unsigned __int16 *)v17 | 0x80070000;
      if ( *(int *)v17 <= 0 )
        v18 = *(_DWORD *)v17;
      if ( v18 == v10 )
        break;
      ++v16;
      ++v17;
      if ( v16 )
      {
        v15 = qword_14006DB70;
        v16 = 0;
        v19 = qword_14006DB70;
        while ( (*(_DWORD *)v19 | 0x80190000) != v10 )
        {
          ++v16;
          ++v19;
          if ( v16 >= 0xF )
            goto LABEL_57;
        }
        break;
      }
    }
    v10 = HIDWORD(v15[v16]);
  }
LABEL_57:
  if ( v7 && !RevertToSelf() )
    GetLastError();
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140039278  mov     [rsp-38h+arg_10], rbx
0x14003927d  push    rbp
0x14003927e  push    rsi
0x14003927f  push    rdi
0x140039280  push    r12
0x140039282  push    r13
0x140039284  push    r14
0x140039286  push    r15
0x140039288  mov     rbp, rsp
0x14003928b  sub     rsp, 60h
0x14003928f  mov     rax, cs:__security_cookie
0x140039296  xor     rax, rsp
0x140039299  mov     [rbp+var_8], rax
0x14003929d  mov     rbx, [rbp+lpszHeaders]
0x1400392a1  xor     r13d, r13d
0x1400392a4  mov     [rbp+var_20], r13d
0x1400392a8  mov     rsi, r9
0x1400392ab  mov     [rbp+dwSupportedSchemes], r13d
0x1400392af  mov     r12, rdx
0x1400392b2  mov     r14b, r13b
0x1400392b5  mov     edi, 80070000h
0x1400392ba  test    rdx, rdx
0x1400392bd  jz      loc_14003964B
0x1400392c3  test    r8, r8
0x1400392c6  jz      loc_14003964B
0x1400392cc  test    r9, r9
0x1400392cf  jz      loc_14003964B
0x1400392d5  test    rcx, rcx
0x1400392d8  jz      short loc_1400392EA
0x1400392da  call    cs:__imp_ImpersonateLoggedOnUser
0x1400392e0  test    eax, eax
0x1400392e2  setnz   r14b
0x1400392e6  test    eax, eax
0x1400392e8  jz      short loc_140039309
0x1400392ea  test    rbx, rbx
0x1400392ed  jz      short loc_14003932A
0x1400392ef  mov     r8d, [rbp+dwHeadersLength]; dwHeadersLength
0x1400392f3  mov     r9d, 0A0000000h; dwModifiers
0x1400392f9  mov     rdx, rbx; lpszHeaders
0x1400392fc  mov     rcx, rsi; hRequest
0x1400392ff  call    cs:__imp_WinHttpAddRequestHeaders
0x140039305  test    eax, eax
0x140039307  jnz     short loc_14003932A
0x140039309  call    cs:__imp_GetLastError
0x14003930f  mov     r15d, 8000FFFFh
0x140039315  movzx   ebx, ax
0x140039318  or      ebx, edi
0x14003931a  test    eax, eax
0x14003931c  cmovle  ebx, eax
0x14003931f  test    ebx, ebx
0x140039321  cmovns  ebx, r15d
0x140039325  jmp     loc_1400395D9
0x14003932a  mov     edi, r13d
0x14003932d  mov     ebx, 4
0x140039332  mov     r15d, 8000FFFFh
0x140039338  mov     r9d, ebx; dwBufferLength
0x14003933b  mov     [rbp+dwBufferLength], ebx
0x14003933e  lea     r8, [rbp+Buffer]; lpBuffer
0x140039342  mov     [rbp+Buffer], 2
0x140039349  mov     edx, 4Dh ; 'M'; dwOption
0x14003934e  mov     [rbp+var_20], r13d
0x140039352  mov     rcx, rsi; hInternet
0x140039355  call    cs:__imp_WinHttpSetOption
0x14003935b  test    eax, eax
0x14003935d  jnz     short loc_140039381
0x14003935f  call    cs:__imp_GetLastError
0x140039365  movzx   ebx, ax
0x140039368  or      ebx, 80070000h
0x14003936e  test    eax, eax
0x140039370  cmovle  ebx, eax
0x140039373  mov     eax, [rbp+var_20]
0x140039376  test    ebx, ebx
0x140039378  cmovns  ebx, r15d
0x14003937c  jmp     loc_1400394FB
0x140039381  xor     edx, edx
0x140039383  mov     [rsp+60h+dwContext], r12
0x140039388  lea     rax, aSendingRequest_0; "Sending request to %ws using proxy."
0x14003938f  xor     ecx, ecx
0x140039391  mov     qword ptr [rsp+60h+dwTotalLength], rax
0x140039396  mov     qword ptr [rsp+60h+dwOptionalLength], r13
0x14003939b  lea     r9d, [rdx+5]
0x14003939f  lea     r8d, [rdx+20h]
0x1400393a3  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1400393a8  test    edi, edi
0x1400393aa  jz      short loc_14003941A
0x1400393ac  mov     [rbp+Buffer], r13d
0x1400393b0  mov     [rbp+dwBufferLength], ebx
0x1400393b3  test    dil, 2
0x1400393b7  jz      short loc_1400393C0
0x1400393b9  mov     [rbp+Buffer], 1
0x1400393c0  mov     r9d, ebx; dwBufferLength
0x1400393c3  lea     r8, [rbp+Buffer]; lpBuffer
0x1400393c7  mov     edx, 4Dh ; 'M'; dwOption
0x1400393cc  mov     rcx, rsi; hInternet
0x1400393cf  call    cs:__imp_WinHttpSetOption
0x1400393d5  test    eax, eax
0x1400393d7  jz      short loc_14003935F
0x1400393d9  test    r14b, r14b
0x1400393dc  lea     rcx, aTrue_0; "TRUE"
0x1400393e3  lea     rax, aFalse_0; "FALSE"
0x1400393ea  cmovnz  rax, rcx
0x1400393ee  xor     edx, edx
0x1400393f0  mov     [rsp+60h+var_28], rax
0x1400393f5  xor     ecx, ecx
0x1400393f7  lea     rax, aSendingRequest; "Sending request to %ws. ImpersonatedAsU"...
0x1400393fe  mov     [rsp+60h+dwContext], r12
0x140039403  mov     qword ptr [rsp+60h+dwTotalLength], rax
0x140039408  lea     r9d, [rdx+5]
0x14003940c  mov     qword ptr [rsp+60h+dwOptionalLength], r13
0x140039411  lea     r8d, [rdx+20h]
0x140039415  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14003941a  mov     [rsp+60h+dwContext], r13; dwContext
0x14003941f  xor     r9d, r9d; lpOptional
0x140039422  mov     [rsp+60h+dwTotalLength], r13d; dwTotalLength
0x140039427  xor     r8d, r8d; dwHeadersLength
0x14003942a  xor     edx, edx; lpszHeaders
0x14003942c  mov     [rsp+60h+dwOptionalLength], r13d; dwOptionalLength
0x140039431  mov     rcx, rsi; hRequest
0x140039434  call    cs:__imp_WinHttpSendRequest
0x14003943a  test    eax, eax
0x14003943c  jz      loc_14003935F
0x140039442  xor     edx, edx
0x140039444  lea     rax, aWaitingForResp; "Waiting for response."
0x14003944b  mov     qword ptr [rsp+60h+dwTotalLength], rax
0x140039450  xor     ecx, ecx
0x140039452  mov     qword ptr [rsp+60h+dwOptionalLength], r13
0x140039457  lea     r9d, [rdx+5]
0x14003945b  lea     r8d, [rdx+20h]
0x14003945f  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140039464  xor     edx, edx; lpReserved
0x140039466  mov     rcx, rsi; hRequest
0x140039469  call    cs:__imp_WinHttpReceiveResponse
0x14003946f  test    eax, eax
0x140039471  jz      loc_14003935F
0x140039477  lea     rax, [rbp+dwBufferLength]
0x14003947b  mov     qword ptr [rsp+60h+dwTotalLength], r13; lpdwIndex
0x140039480  lea     r9, [rbp+var_20]; lpBuffer
0x140039484  mov     qword ptr [rsp+60h+dwOptionalLength], rax; lpdwBufferLength
0x140039489  xor     r8d, r8d; pwszName
0x14003948c  mov     [rbp+dwBufferLength], ebx
0x14003948f  mov     edx, 20000013h; dwInfoLevel
0x140039494  mov     rcx, rsi; hRequest
0x140039497  call    cs:__imp_WinHttpQueryHeaders
0x14003949d  test    eax, eax
0x14003949f  jz      loc_14003935F
0x1400394a5  mov     eax, [rbp+var_20]
0x1400394a8  cmp     eax, 0C8h
0x1400394ad  jz      short loc_1400394E6
0x1400394af  cmp     eax, 0CEh
0x1400394b4  jz      short loc_1400394E6
0x1400394b6  mov     dword ptr [rsp+60h+dwContext], eax
0x1400394ba  xor     edx, edx
0x1400394bc  lea     rax, aStatuscodeForT; "StatusCode for transaction returned fro"...
0x1400394c3  mov     r9d, ebx
0x1400394c6  mov     qword ptr [rsp+60h+dwTotalLength], rax
0x1400394cb  xor     ecx, ecx
0x1400394cd  mov     qword ptr [rsp+60h+dwOptionalLength], r13
0x1400394d2  lea     r8d, [rdx+20h]
0x1400394d6  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1400394db  mov     rcx, rsi; hRequest
0x1400394de  call    LogExtendedWinHttpErrorMessage
0x1400394e3  mov     eax, [rbp+var_20]
0x1400394e6  mov     ebx, r13d
0x1400394e9  cmp     eax, 191h
0x1400394ee  jz      short loc_14003950D
0x1400394f0  cmp     eax, 197h
0x1400394f5  jnz     loc_140039587
0x1400394fb  cmp     eax, 191h
0x140039500  jz      short loc_14003950D
0x140039502  cmp     eax, 197h
0x140039507  jnz     loc_1400395CC
0x14003950d  mov     ecx, edi
0x14003950f  cmp     eax, 191h
0x140039514  jnz     short loc_140039519
0x140039516  or      edi, 2
0x140039519  mov     edx, 197h
0x14003951e  cmp     eax, edx
0x140039520  jnz     short loc_140039525
0x140039522  or      edi, 1
0x140039525  cmp     ecx, edi
0x140039527  jz      loc_1400395BF
0x14003952d  lea     r9, [rbp+pdwAuthTarget]; pdwAuthTarget
0x140039531  mov     [rbp+dwFirstScheme], r13d
0x140039535  lea     r8, [rbp+dwFirstScheme]; lpdwFirstScheme
0x140039539  mov     [rbp+pdwAuthTarget], r13d
0x14003953d  lea     rdx, [rbp+dwSupportedSchemes]; lpdwSupportedSchemes
0x140039541  mov     rcx, rsi; hRequest
0x140039544  call    cs:__imp_WinHttpQueryAuthSchemes
0x14003954a  test    eax, eax
0x14003954c  jz      short loc_1400395AF
0x14003954e  mov     eax, [rbp+dwSupportedSchemes]
0x140039551  mov     ebx, 4
0x140039556  mov     dword ptr [rsp+60h+var_28], eax
0x14003955a  mov     r9d, ebx
0x14003955d  mov     eax, [rbp+var_20]
0x140039560  xor     edx, edx
0x140039562  mov     dword ptr [rsp+60h+dwContext], eax
0x140039566  xor     ecx, ecx
0x140039568  lea     rax, aWillImpersonat; "Will impersonate the next time. Status "...
0x14003956f  mov     qword ptr [rsp+60h+dwTotalLength], rax
0x140039574  lea     r8d, [rbx+1Ch]
0x140039578  mov     qword ptr [rsp+60h+dwOptionalLength], r13
0x14003957d  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140039582  jmp     loc_140039338
0x140039587  xor     edx, edx
0x140039589  mov     dword ptr [rsp+60h+dwContext], edi
0x14003958d  lea     rax, aSendSucceededI; "Send succeeded. Impersonate flags: %lu"
0x140039594  xor     ecx, ecx
0x140039596  mov     qword ptr [rsp+60h+dwTotalLength], rax
0x14003959b  mov     qword ptr [rsp+60h+dwOptionalLength], r13
0x1400395a0  lea     r9d, [rdx+5]
0x1400395a4  lea     r8d, [rdx+20h]
0x1400395a8  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1400395ad  jmp     short loc_1400395CC
0x1400395af  call    cs:__imp_GetLastError
0x1400395b5  mov     edi, 80070000h
0x1400395ba  jmp     loc_140039315
0x1400395bf  mov     ebx, 80244017h
0x1400395c4  cmp     eax, edx
0x1400395c6  lea     ecx, [rbx+4]
0x1400395c9  cmovz   ebx, ecx
0x1400395cc  test    ebx, ebx
0x1400395ce  jns     loc_14003965A
0x1400395d4  mov     edi, 80070000h
0x1400395d9  xor     edx, edx
0x1400395db  mov     [rsp+60h+dwContext], r12
0x1400395e0  lea     rax, aSendrequestwit; "SendRequestWithAuthRetry failed for <%w"...
0x1400395e7  xor     ecx, ecx
0x1400395e9  mov     qword ptr [rsp+60h+dwTotalLength], rax
0x1400395ee  mov     [rsp+60h+dwOptionalLength], ebx
0x1400395f2  lea     r9d, [rdx+5]
0x1400395f6  lea     r8d, [rdx+20h]
0x1400395fa  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1400395ff  lea     r8, qword_14006DB68
0x140039606  mov     ecx, r13d
0x140039609  mov     rdx, r8
0x14003960c  movzx   eax, word ptr [rdx]
0x14003960f  or      eax, edi
0x140039611  cmp     [rdx], r13d
0x140039614  cmovle  eax, [rdx]
0x140039617  cmp     eax, ebx
0x140039619  jz      short loc_140039652
0x14003961b  inc     ecx
0x14003961d  add     rdx, 8
0x140039621  cmp     ecx, 1
0x140039624  jb      short loc_14003960C
0x140039626  lea     r8, qword_14006DB70
0x14003962d  mov     ecx, r13d
0x140039630  mov     rdx, r8
0x140039633  mov     eax, [rdx]
0x140039635  or      eax, 80190000h
0x14003963a  cmp     eax, ebx
0x14003963c  jz      short loc_140039652
0x14003963e  inc     ecx
0x140039640  add     rdx, 8
0x140039644  cmp     ecx, 0Fh
0x140039647  jb      short loc_140039633
0x140039649  jmp     short loc_14003965A
0x14003964b  mov     ebx, 80070057h
0x140039650  jmp     short loc_1400395D9
0x140039652  movsxd  rax, ecx
0x140039655  mov     ebx, [r8+rax*8+4]
0x14003965a  test    r14b, r14b
0x14003965d  jz      short loc_14003966F
0x14003965f  call    cs:__imp_RevertToSelf
0x140039665  test    eax, eax
0x140039667  jnz     short loc_14003966F
0x140039669  call    cs:__imp_GetLastError
0x14003966f  mov     eax, ebx
0x140039671  mov     rcx, [rbp+var_8]
0x140039675  xor     rcx, rsp; StackCookie
0x140039678  call    __security_check_cookie
0x14003967d  mov     rbx, [rsp+60h+arg_10]
0x140039685  add     rsp, 60h
0x140039689  pop     r15
0x14003968b  pop     r14
0x14003968d  pop     r13
0x14003968f  pop     r12
0x140039691  pop     rdi
0x140039692  pop     rsi
0x140039693  pop     rbp
0x140039694  retn
```
