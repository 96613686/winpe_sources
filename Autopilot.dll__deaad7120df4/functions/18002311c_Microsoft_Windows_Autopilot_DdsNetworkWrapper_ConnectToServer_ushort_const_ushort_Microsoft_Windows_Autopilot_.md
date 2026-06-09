# Microsoft::Windows::Autopilot::DdsNetworkWrapper::ConnectToServer(ushort const *,ushort,Microsoft::Windows::Autopilot::DdsNetworkWrapper::TimeoutOverride const * const)

- ea: `0x18002311c`
- end: `0x1800232d4`
- name: `?ConnectToServer@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEBGGQEBUTimeoutOverride@1234@@Z`
- size: `440`
- prototype: `__int64 __fastcall(Microsoft::Windows::Autopilot::DdsNetworkWrapper *this, const unsigned __int16 *, INTERNET_PORT, const struct Microsoft::Windows::Autopilot::DdsNetworkWrapper::TimeoutOverride *const)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180024878`

## callees

- `0x1800045d0`
- `0x180010744`
- `0x180010764`
- `0x180011220`
- `0x18002311c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800231de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023252`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800231de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023252`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800231fd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023271`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800231fd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023271`
- `WINHTTP!WinHttpCloseHandle` at `0x1800231ef`
- `WINHTTP!WinHttpCloseHandle` at `0x180023263`
- `WINHTTP!WinHttpCloseHandle` at `0x1800231ef`
- `WINHTTP!WinHttpCloseHandle` at `0x180023263`
- `WINHTTP!WinHttpConnect` at `0x18002323a`
- `WINHTTP!WinHttpConnect` at `0x18002323a`
- `WINHTTP!WinHttpOpen` at `0x1800231c6`
- `WINHTTP!WinHttpOpen` at `0x1800231c6`

## string_xrefs

- `0x180023197`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18002321a`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180023290`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::DdsNetworkWrapper::ConnectToServer(
        Microsoft::Windows::Autopilot::DdsNetworkWrapper *this,
        const unsigned __int16 *a2,
        INTERNET_PORT a3,
        const struct Microsoft::Windows::Autopilot::DdsNetworkWrapper::TimeoutOverride *const a4)
{
  int v7; // eax
  unsigned int v8; // ebx
  const char *v9; // r9
  __int64 result; // rax
  void *v11; // rsi
  const char *v12; // r9
  void *v13; // r14
  DWORD LastError; // ebx
  HINTERNET v15; // r14
  void *v16; // rsi
  DWORD v17; // ebx
  WCHAR pszAgentW[104]; // [rsp+50h] [rbp-108h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+0h]

  v7 = StringCchPrintfW(pszAgentW, 0x64u, L"%s.%s.%s.%s", L"Autopilot");
  v8 = v7;
  if ( v7 >= 0 )
  {
    v11 = WinHttpOpen(pszAgentW, 4u, 0, 0, 0);
    v13 = (void *)*((_QWORD *)this + 8);
    if ( v13 )
    {
      LastError = GetLastError();
      WinHttpCloseHandle(v13);
      SetLastError(LastError);
    }
    *((_QWORD *)this + 8) = v11;
    if ( v11 )
    {
      v15 = WinHttpConnect(v11, a2, a3, 0);
      v16 = (void *)*((_QWORD *)this + 9);
      if ( v16 )
      {
        v17 = GetLastError();
        WinHttpCloseHandle(v16);
        SetLastError(v17);
      }
      *((_QWORD *)this + 9) = v15;
      if ( *((_QWORD *)this + 8) )
        result = 0;
      else
        result = wil::details::in1diag3::Return_GetLastError(
                   retaddr,
                   (void *)0x1A2,
                   (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
                   v9);
    }
    else
    {
      result = wil::details::in1diag3::Return_GetLastError(
                 retaddr,
                 (void *)0x191,
                 (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
                 v12);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x189,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
      (const char *)(unsigned int)v7,
      (int)L"10");
    result = v8;
  }
  while ( 2 )
  {
    try
    {
    }
    catch ( ... )
    {
      result = (unsigned int)wil::details::in1diag3::Return_CaughtException(
                               retaddr,
                               (void *)0x1A6,
                               (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
                               v9);
      continue;
    }
    break;
  }
  return result;
}

```

## disassembly

```asm
0x18002311c  mov     [rsp+arg_18], rbx
0x180023121  push    rsi
0x180023122  push    rdi
0x180023123  push    r12
0x180023125  push    r14
0x180023127  push    r15
0x180023129  sub     rsp, 130h
0x180023130  mov     rax, cs:__security_cookie
0x180023137  xor     rax, rsp
0x18002313a  mov     [rsp+158h+var_38], rax
0x180023142  movzx   r12d, r8w
0x180023146  mov     r15, rdx
0x180023149  mov     rdi, rcx
0x18002314c  lea     rax, a1; "1"
0x180023153  mov     [rsp+158h+var_128], rax
0x180023158  mov     [rsp+158h+var_130], rax
0x18002315d  lea     rax, a10; "10"
0x180023164  mov     qword ptr [rsp+158h+dwFlags], rax; int
0x180023169  lea     r9, aAutopilot; "Autopilot"
0x180023170  lea     r8, aSSSS; "%s.%s.%s.%s"
0x180023177  mov     edx, 64h ; 'd'; unsigned __int64
0x18002317c  lea     rcx, [rsp+158h+pszAgentW]; unsigned __int16 *
0x180023181  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180023186  mov     ebx, eax
0x180023188  test    eax, eax
0x18002318a  jns     short loc_1800231AF
0x18002318c  mov     rcx, [rsp+158h]; this
0x180023194  mov     r9d, eax; char *
0x180023197  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x18002319e  mov     edx, 189h; void *
0x1800231a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800231a8  mov     eax, ebx
0x1800231aa  jmp     loc_1800232AB
0x1800231af  mov     [rsp+158h+dwFlags], 0; dwFlags
0x1800231b7  xor     r9d, r9d; pszProxyBypassW
0x1800231ba  xor     r8d, r8d; pszProxyW
0x1800231bd  lea     edx, [r9+4]; dwAccessType
0x1800231c1  lea     rcx, [rsp+158h+pszAgentW]; pszAgentW
0x1800231c6  call    cs:__imp_WinHttpOpen
0x1800231cd  nop     dword ptr [rax+rax+00h]
0x1800231d2  mov     rsi, rax
0x1800231d5  mov     r14, [rdi+40h]
0x1800231d9  test    r14, r14
0x1800231dc  jz      short loc_180023209
0x1800231de  call    cs:__imp_GetLastError
0x1800231e5  nop     dword ptr [rax+rax+00h]
0x1800231ea  mov     ebx, eax
0x1800231ec  mov     rcx, r14; hInternet
0x1800231ef  call    cs:__imp_WinHttpCloseHandle
0x1800231f6  nop     dword ptr [rax+rax+00h]
0x1800231fb  mov     ecx, ebx; dwErrCode
0x1800231fd  call    cs:__imp_SetLastError
0x180023204  nop     dword ptr [rax+rax+00h]
0x180023209  mov     [rdi+40h], rsi
0x18002320d  test    rsi, rsi
0x180023210  jnz     short loc_18002322D
0x180023212  mov     rcx, [rsp+158h]; this
0x18002321a  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x180023221  mov     edx, 191h; void *
0x180023226  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002322b  jmp     short loc_1800232AB
0x18002322d  xor     r9d, r9d; dwReserved
0x180023230  movzx   r8d, r12w; nServerPort
0x180023234  mov     rdx, r15; pswzServerName
0x180023237  mov     rcx, rsi; hSession
0x18002323a  call    cs:__imp_WinHttpConnect
0x180023241  nop     dword ptr [rax+rax+00h]
0x180023246  mov     r14, rax
0x180023249  mov     rsi, [rdi+48h]
0x18002324d  test    rsi, rsi
0x180023250  jz      short loc_18002327D
0x180023252  call    cs:__imp_GetLastError
0x180023259  nop     dword ptr [rax+rax+00h]
0x18002325e  mov     ebx, eax
0x180023260  mov     rcx, rsi; hInternet
0x180023263  call    cs:__imp_WinHttpCloseHandle
0x18002326a  nop     dword ptr [rax+rax+00h]
0x18002326f  mov     ecx, ebx; dwErrCode
0x180023271  call    cs:__imp_SetLastError
0x180023278  nop     dword ptr [rax+rax+00h]
0x18002327d  mov     [rdi+48h], r14
0x180023281  cmp     qword ptr [rdi+40h], 0
0x180023286  jnz     short loc_1800232A3
0x180023288  mov     rcx, [rsp+158h]; this
0x180023290  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x180023297  mov     edx, 1A2h; void *
0x18002329c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800232a1  jmp     short loc_1800232AB
0x1800232a3  xor     eax, eax
0x1800232a5  jmp     short loc_1800232AB
0x1800232a7  mov     eax, [rsp+158h+var_118]
0x1800232ab  mov     rcx, [rsp+158h+var_38]
0x1800232b3  xor     rcx, rsp; StackCookie
0x1800232b6  call    __security_check_cookie
0x1800232bb  mov     rbx, [rsp+158h+arg_18]
0x1800232c3  add     rsp, 130h
0x1800232ca  pop     r15
0x1800232cc  pop     r14
0x1800232ce  pop     r12
0x1800232d0  pop     rdi
0x1800232d1  pop     rsi
0x1800232d2  retn
```
