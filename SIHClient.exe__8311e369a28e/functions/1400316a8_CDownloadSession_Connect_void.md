# CDownloadSession::Connect(void)

- ea: `0x1400316a8`
- end: `0x1400318ef`
- name: `?Connect@CDownloadSession@@AEAAJXZ`
- size: `583`
- prototype: `__int64 __fastcall(CDownloadSession *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x14003115c`

## callees

- `0x14000ce30`
- `0x1400154b4`
- `0x140030898`
- `0x14003097c`
- `0x1400316a8`
- `0x14003be88`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400316f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140031760`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400317a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140031810`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140031834`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400318bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400316f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140031760`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400317a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140031810`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140031834`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400318bf`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1400316e6`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1400316e6`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1400318b5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1400318b5`
- `WINHTTP!WinHttpCloseHandle` at `0x140031857`
- `WINHTTP!WinHttpCloseHandle` at `0x140031875`
- `WINHTTP!WinHttpCloseHandle` at `0x140031857`
- `WINHTTP!WinHttpCloseHandle` at `0x140031875`
- `WINHTTP!WinHttpSetTimeouts` at `0x140031806`
- `WINHTTP!WinHttpSetTimeouts` at `0x140031806`
- `WINHTTP!WinHttpOpen` at `0x140031752`
- `WINHTTP!WinHttpOpen` at `0x140031752`
- `WINHTTP!WinHttpSetOption` at `0x140031792`
- `WINHTTP!WinHttpSetOption` at `0x140031792`
- `WINHTTP!WinHttpConnect` at `0x140031825`
- `WINHTTP!WinHttpConnect` at `0x140031825`

## string_xrefs

- `0x140031720`: `Windows-Update-Agent/1507.2603.28012.0 Client-Protocol/2.90`

## pseudocode

```c
__int64 __fastcall CDownloadSession::Connect(CDownloadSession *this)
{
  WCHAR *v1; // rbx
  void *v3; // rcx
  bool v4; // r15
  BOOL v5; // eax
  signed int LastError; // eax
  signed int v7; // edi
  void *v8; // rax
  signed int v9; // eax
  WinHttpLogger *v10; // r12
  signed int v11; // eax
  signed int v12; // ecx
  HINTERNET v13; // rax
  void *v14; // rcx
  __int64 dwFlags; // [rsp+20h] [rbp-48h]
  LPCWSTR pszAgentW; // [rsp+30h] [rbp-38h] BYREF
  int Buffer; // [rsp+38h] [rbp-30h] BYREF

  v1 = 0;
  v3 = (void *)*((_QWORD *)this + 15);
  v4 = 0;
  pszAgentW = 0;
  if ( v3 )
  {
    v5 = ImpersonateLoggedOnUser(v3);
    v4 = v5;
    if ( !v5 )
    {
      LastError = GetLastError();
      v7 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v7 = LastError;
      if ( v7 >= 0 )
        v7 = -2147418113;
      goto LABEL_31;
    }
  }
  v7 = ConvertAnsiToWide_Alloc("Windows-Update-Agent/1507.2603.28012.0 Client-Protocol/2.90", (wchar_t **)&pszAgentW);
  if ( v7 < 0 )
  {
    v1 = (WCHAR *)pszAgentW;
    goto LABEL_31;
  }
  v1 = (WCHAR *)pszAgentW;
  v8 = WinHttpOpen(pszAgentW, 4u, 0, 0, 0);
  *(_QWORD *)this = v8;
  if ( !v8 )
  {
    v9 = GetLastError();
    v10 = (CDownloadSession *)((char *)this + 128);
LABEL_22:
    v14 = (void *)*((_QWORD *)this + 1);
    v7 = (unsigned __int16)v9 | 0x80070000;
    if ( v9 <= 0 )
      v7 = v9;
    if ( v7 >= 0 )
      v7 = -2147418113;
    if ( v14 )
      WinHttpCloseHandle(v14);
    *((_QWORD *)this + 1) = 0;
    WinHttpLogger::Reset(v10);
    if ( *(_QWORD *)this )
      WinHttpCloseHandle(*(HINTERNET *)this);
    *(_QWORD *)this = 0;
    LODWORD(dwFlags) = v7;
    WUTrace(0, 0, 32, 3, dwFlags, L"WinHttp: Connect");
    goto LABEL_31;
  }
  Buffer = -2;
  if ( !WinHttpSetOption(v8, 0x49u, &Buffer, 4u) )
  {
    v11 = GetLastError();
    v12 = (unsigned __int16)v11 | 0x80070000;
    if ( v11 <= 0 )
      v12 = v11;
    if ( v12 >= 0 )
      v12 = -2147418113;
    LODWORD(dwFlags) = v12;
    WUTrace(
      0,
      0,
      32,
      3,
      dwFlags,
      L"Failed to set WinHttp max connections per server. We might go out with multiple TCP connections");
  }
  v10 = (CDownloadSession *)((char *)this + 128);
  WinHttpLogger::Initialize((CDownloadSession *)((char *)this + 128), *(void **)this, *((const wchar_t **)this + 4));
  if ( !WinHttpSetTimeouts(*(HINTERNET *)this, 0, 120000, 120000, 120000) )
    GetLastError();
  v13 = WinHttpConnect(*(HINTERNET *)this, *((LPCWSTR *)this + 4), *((_WORD *)this + 24), 0);
  *((_QWORD *)this + 1) = v13;
  if ( !v13 )
  {
    v9 = GetLastError();
    goto LABEL_22;
  }
LABEL_31:
  if ( v1 )
    SusFree(v1);
  if ( v4 && !RevertToSelf() )
    GetLastError();
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400316a8  mov     [rsp+arg_8], rbx
0x1400316ad  mov     [rsp+arg_10], rsi
0x1400316b2  mov     [rsp+arg_18], rdi
0x1400316b7  push    r12
0x1400316b9  push    r14
0x1400316bb  push    r15
0x1400316bd  sub     rsp, 50h
0x1400316c1  mov     rax, cs:__security_cookie
0x1400316c8  xor     rax, rsp
0x1400316cb  mov     [rsp+68h+var_28], rax
0x1400316d0  xor     ebx, ebx
0x1400316d2  mov     rsi, rcx
0x1400316d5  mov     rcx, [rcx+78h]; hToken
0x1400316d9  xor     r15b, r15b
0x1400316dc  mov     [rsp+68h+pszAgentW], rbx
0x1400316e1  test    rcx, rcx
0x1400316e4  jz      short loc_14003171B
0x1400316e6  call    cs:__imp_ImpersonateLoggedOnUser
0x1400316ec  test    eax, eax
0x1400316ee  setnz   r15b
0x1400316f2  test    eax, eax
0x1400316f4  jnz     short loc_14003171B
0x1400316f6  call    cs:__imp_GetLastError
0x1400316fc  movzx   edi, ax
0x1400316ff  mov     r14d, 8000FFFFh
0x140031705  or      edi, 80070000h
0x14003170b  test    eax, eax
0x14003170d  cmovle  edi, eax
0x140031710  test    edi, edi
0x140031712  cmovns  edi, r14d
0x140031716  jmp     loc_1400318A3
0x14003171b  lea     rdx, [rsp+68h+pszAgentW]; wchar_t **
0x140031720  lea     rcx, MultiByteStr; "Windows-Update-Agent/1507.2603.28012.0 "...
0x140031727  call    ?ConvertAnsiToWide_Alloc@@YAJPEBDPEAPEA_W@Z; ConvertAnsiToWide_Alloc(char const *,wchar_t * *)
0x14003172c  mov     edi, eax
0x14003172e  test    eax, eax
0x140031730  jns     short loc_14003173C
0x140031732  mov     rbx, [rsp+68h+pszAgentW]
0x140031737  jmp     loc_1400318A3
0x14003173c  xor     r9d, r9d; pszProxyBypassW
0x14003173f  mov     dword ptr [rsp+68h+dwFlags], ebx; dwFlags
0x140031743  mov     rbx, [rsp+68h+pszAgentW]
0x140031748  xor     r8d, r8d; pszProxyW
0x14003174b  mov     rcx, rbx; pszAgentW
0x14003174e  lea     edx, [r9+4]; dwAccessType
0x140031752  call    cs:__imp_WinHttpOpen
0x140031758  mov     [rsi], rax
0x14003175b  test    rax, rax
0x14003175e  jnz     short loc_140031778
0x140031760  call    cs:__imp_GetLastError
0x140031766  mov     r14d, 8000FFFFh
0x14003176c  lea     r12, [rsi+80h]
0x140031773  jmp     loc_14003183A
0x140031778  mov     r9d, 4; dwBufferLength
0x14003177e  mov     [rsp+68h+Buffer], 0FFFFFFFEh
0x140031786  lea     r8, [rsp+68h+Buffer]; lpBuffer
0x14003178b  mov     rcx, rax; hInternet
0x14003178e  lea     edx, [r9+45h]; dwOption
0x140031792  call    cs:__imp_WinHttpSetOption
0x140031798  mov     r14d, 8000FFFFh
0x14003179e  test    eax, eax
0x1400317a0  jnz     short loc_1400317DD
0x1400317a2  call    cs:__imp_GetLastError
0x1400317a8  movzx   ecx, ax
0x1400317ab  or      ecx, 80070000h
0x1400317b1  test    eax, eax
0x1400317b3  cmovle  ecx, eax
0x1400317b6  lea     rax, aFailedToSetWin; "Failed to set WinHttp max connections p"...
0x1400317bd  test    ecx, ecx
0x1400317bf  mov     [rsp+68h+var_40], rax
0x1400317c4  cmovns  ecx, r14d
0x1400317c8  xor     edx, edx
0x1400317ca  mov     dword ptr [rsp+68h+dwFlags], ecx
0x1400317ce  xor     ecx, ecx
0x1400317d0  lea     r9d, [rdx+3]
0x1400317d4  lea     r8d, [rdx+20h]
0x1400317d8  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1400317dd  mov     r8, [rsi+20h]; wchar_t *
0x1400317e1  lea     r12, [rsi+80h]
0x1400317e8  mov     rdx, [rsi]; void *
0x1400317eb  mov     rcx, r12; this
0x1400317ee  call    ?Initialize@WinHttpLogger@@QEAAJPEAXPEB_W@Z; WinHttpLogger::Initialize(void *,wchar_t const *)
0x1400317f3  mov     rcx, [rsi]; hInternet
0x1400317f6  mov     r8d, 1D4C0h; nConnectTimeout
0x1400317fc  mov     r9d, r8d; nSendTimeout
0x1400317ff  mov     dword ptr [rsp+68h+dwFlags], r8d; nReceiveTimeout
0x140031804  xor     edx, edx; nResolveTimeout
0x140031806  call    cs:__imp_WinHttpSetTimeouts
0x14003180c  test    eax, eax
0x14003180e  jnz     short loc_140031816
0x140031810  call    cs:__imp_GetLastError
0x140031816  movzx   r8d, word ptr [rsi+30h]; nServerPort
0x14003181b  xor     r9d, r9d; dwReserved
0x14003181e  mov     rdx, [rsi+20h]; pswzServerName
0x140031822  mov     rcx, [rsi]; hSession
0x140031825  call    cs:__imp_WinHttpConnect
0x14003182b  mov     [rsi+8], rax
0x14003182f  test    rax, rax
0x140031832  jnz     short loc_1400318A3
0x140031834  call    cs:__imp_GetLastError
0x14003183a  mov     rcx, [rsi+8]; hInternet
0x14003183e  movzx   edi, ax
0x140031841  or      edi, 80070000h
0x140031847  test    eax, eax
0x140031849  cmovle  edi, eax
0x14003184c  test    edi, edi
0x14003184e  cmovns  edi, r14d
0x140031852  test    rcx, rcx
0x140031855  jz      short loc_14003185D
0x140031857  call    cs:__imp_WinHttpCloseHandle
0x14003185d  mov     rcx, r12; this
0x140031860  mov     qword ptr [rsi+8], 0
0x140031868  call    ?Reset@WinHttpLogger@@QEAAXXZ; WinHttpLogger::Reset(void)
0x14003186d  mov     rcx, [rsi]; hInternet
0x140031870  test    rcx, rcx
0x140031873  jz      short loc_14003187B
0x140031875  call    cs:__imp_WinHttpCloseHandle
0x14003187b  xor     edx, edx
0x14003187d  mov     qword ptr [rsi], 0
0x140031884  lea     rax, aWinhttpConnect; "WinHttp: Connect"
0x14003188b  xor     ecx, ecx
0x14003188d  mov     [rsp+68h+var_40], rax
0x140031892  mov     dword ptr [rsp+68h+dwFlags], edi
0x140031896  lea     r9d, [rdx+3]
0x14003189a  lea     r8d, [rdx+20h]
0x14003189e  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1400318a3  test    rbx, rbx
0x1400318a6  jz      short loc_1400318B0
0x1400318a8  mov     rcx, rbx; lpMem
0x1400318ab  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1400318b0  test    r15b, r15b
0x1400318b3  jz      short loc_1400318C5
0x1400318b5  call    cs:__imp_RevertToSelf
0x1400318bb  test    eax, eax
0x1400318bd  jnz     short loc_1400318C5
0x1400318bf  call    cs:__imp_GetLastError
0x1400318c5  mov     eax, edi
0x1400318c7  mov     rcx, [rsp+68h+var_28]
0x1400318cc  xor     rcx, rsp; StackCookie
0x1400318cf  call    __security_check_cookie
0x1400318d4  lea     r11, [rsp+68h+var_18]
0x1400318d9  mov     rbx, [r11+28h]
0x1400318dd  mov     rsi, [r11+30h]
0x1400318e1  mov     rdi, [r11+38h]
0x1400318e5  mov     rsp, r11
0x1400318e8  pop     r15
0x1400318ea  pop     r14
0x1400318ec  pop     r12
0x1400318ee  retn
```
