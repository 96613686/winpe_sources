# Microsoft::Windows::Autopilot::DdsNetworkWrapper::ConnectToServer(ushort const *,ushort,Microsoft::Windows::Autopilot::DdsNetworkWrapper::TimeoutOverride const * const)

- ea: `0x18002264c`
- end: `0x1800227d4`
- name: `?ConnectToServer@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEBGGQEBUTimeoutOverride@1234@@Z`
- size: `392`
- prototype: `int(Microsoft::Windows::Autopilot::DdsNetworkWrapper *__hidden this, const unsigned __int16 *, unsigned __int16, const struct Microsoft::Windows::Autopilot::DdsNetworkWrapper::TimeoutOverride *const)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180023cb0`

## callees

- `0x1800045b0`
- `0x1800105d4`
- `0x1800105f4`
- `0x180011224`
- `0x18002264c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022708`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022764`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022708`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022764`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002271b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022777`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002271b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022777`
- `WINHTTP!WinHttpCloseHandle` at `0x180022713`
- `WINHTTP!WinHttpCloseHandle` at `0x18002276f`
- `WINHTTP!WinHttpCloseHandle` at `0x180022713`
- `WINHTTP!WinHttpCloseHandle` at `0x18002276f`
- `WINHTTP!WinHttpConnect` at `0x180022752`
- `WINHTTP!WinHttpConnect` at `0x180022752`
- `WINHTTP!WinHttpOpen` at `0x1800226f6`
- `WINHTTP!WinHttpOpen` at `0x1800226f6`

## string_xrefs

- `0x1800226c7`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180022732`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180022790`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`

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
0x18002264c  mov     [rsp+arg_18], rbx
0x180022651  push    rsi
0x180022652  push    rdi
0x180022653  push    r12
0x180022655  push    r14
0x180022657  push    r15
0x180022659  sub     rsp, 130h
0x180022660  mov     rax, cs:__security_cookie
0x180022667  xor     rax, rsp
0x18002266a  mov     [rsp+158h+var_38], rax
0x180022672  movzx   r12d, r8w
0x180022676  mov     r15, rdx
0x180022679  mov     rdi, rcx
0x18002267c  lea     rax, a1; "1"
0x180022683  mov     [rsp+158h+var_128], rax
0x180022688  mov     [rsp+158h+var_130], rax
0x18002268d  lea     rax, a10; "10"
0x180022694  mov     qword ptr [rsp+158h+dwFlags], rax; int
0x180022699  lea     r9, aAutopilot; "Autopilot"
0x1800226a0  lea     r8, aSSSS; "%s.%s.%s.%s"
0x1800226a7  mov     edx, 64h ; 'd'; unsigned __int64
0x1800226ac  lea     rcx, [rsp+158h+pszAgentW]; unsigned __int16 *
0x1800226b1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800226b6  mov     ebx, eax
0x1800226b8  test    eax, eax
0x1800226ba  jns     short loc_1800226DF
0x1800226bc  mov     rcx, [rsp+158h]; this
0x1800226c4  mov     r9d, eax; char *
0x1800226c7  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800226ce  mov     edx, 189h; void *
0x1800226d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800226d8  mov     eax, ebx
0x1800226da  jmp     loc_1800227AB
0x1800226df  mov     [rsp+158h+dwFlags], 0; dwFlags
0x1800226e7  xor     r9d, r9d; pszProxyBypassW
0x1800226ea  xor     r8d, r8d; pszProxyW
0x1800226ed  lea     edx, [r9+4]; dwAccessType
0x1800226f1  lea     rcx, [rsp+158h+pszAgentW]; pszAgentW
0x1800226f6  call    cs:__imp_WinHttpOpen
0x1800226fc  mov     rsi, rax
0x1800226ff  mov     r14, [rdi+40h]
0x180022703  test    r14, r14
0x180022706  jz      short loc_180022721
0x180022708  call    cs:__imp_GetLastError
0x18002270e  mov     ebx, eax
0x180022710  mov     rcx, r14; hInternet
0x180022713  call    cs:__imp_WinHttpCloseHandle
0x180022719  mov     ecx, ebx; dwErrCode
0x18002271b  call    cs:__imp_SetLastError
0x180022721  mov     [rdi+40h], rsi
0x180022725  test    rsi, rsi
0x180022728  jnz     short loc_180022745
0x18002272a  mov     rcx, [rsp+158h]; this
0x180022732  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x180022739  mov     edx, 191h; void *
0x18002273e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180022743  jmp     short loc_1800227AB
0x180022745  xor     r9d, r9d; dwReserved
0x180022748  movzx   r8d, r12w; nServerPort
0x18002274c  mov     rdx, r15; pswzServerName
0x18002274f  mov     rcx, rsi; hSession
0x180022752  call    cs:__imp_WinHttpConnect
0x180022758  mov     r14, rax
0x18002275b  mov     rsi, [rdi+48h]
0x18002275f  test    rsi, rsi
0x180022762  jz      short loc_18002277D
0x180022764  call    cs:__imp_GetLastError
0x18002276a  mov     ebx, eax
0x18002276c  mov     rcx, rsi; hInternet
0x18002276f  call    cs:__imp_WinHttpCloseHandle
0x180022775  mov     ecx, ebx; dwErrCode
0x180022777  call    cs:__imp_SetLastError
0x18002277d  mov     [rdi+48h], r14
0x180022781  cmp     qword ptr [rdi+40h], 0
0x180022786  jnz     short loc_1800227A3
0x180022788  mov     rcx, [rsp+158h]; this
0x180022790  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x180022797  mov     edx, 1A2h; void *
0x18002279c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800227a1  jmp     short loc_1800227AB
0x1800227a3  xor     eax, eax
0x1800227a5  jmp     short loc_1800227AB
0x1800227a7  mov     eax, [rsp+158h+var_118]
0x1800227ab  mov     rcx, [rsp+158h+var_38]
0x1800227b3  xor     rcx, rsp; StackCookie
0x1800227b6  call    __security_check_cookie
0x1800227bb  mov     rbx, [rsp+158h+arg_18]
0x1800227c3  add     rsp, 130h
0x1800227ca  pop     r15
0x1800227cc  pop     r14
0x1800227ce  pop     r12
0x1800227d0  pop     rdi
0x1800227d1  pop     rsi
0x1800227d2  retn
```
