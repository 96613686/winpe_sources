# WinHttpSession::Initialize(void)

- ea: `0x1800985e4`
- end: `0x1800986f6`
- name: `?Initialize@WinHttpSession@@QEAAJXZ`
- size: `274`
- prototype: `__int64 __fastcall(WinHttpSession *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180097cb8`

## callees

- `0x18008aa28`
- `0x18008aa9c`
- `0x18008c230`
- `0x1800985e4`
- `0x1800a3124`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098651`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098651`
- `WINHTTP!WinHttpOpen` at `0x180098642`
- `WINHTTP!WinHttpOpen` at `0x180098642`

## string_xrefs

- `0x180098675`: `EventWriteWinhttpInitializationFailureEvent`
- `0x18009867c`: `Logger::WriteWinhttpInitializationFailureEvent`
- `0x180098699`: `%s: WinHttpOpen failed with error code: 0x%08x`
- `0x1800986ce`: `%s: Winhttp initialized. User agent: %s. Access type: %lu. Proxy name: %s. Proxy bypass address list: %s. Flags: %lu.`
- `0x180098607`: `ReadBoolOption`

## pseudocode

```c
__int64 __fastcall WinHttpSession::Initialize(WinHttpSession *this)
{
  int v2; // eax
  BOOL v3; // eax
  DWORD v4; // edi
  HINTERNET v5; // rax
  int v6; // edx
  int v7; // ecx
  DWORD LastError; // ebx
  int v9; // r8d
  unsigned int v10; // eax
  int dwFlags; // [rsp+20h] [rbp-28h]
  int v13; // [rsp+30h] [rbp-18h]
  bool v14; // [rsp+50h] [rbp+8h] BYREF

  v14 = 1;
  v2 = ReadBoolOption((const unsigned __int16 *)this, &v14);
  if ( v2 < 0 )
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"IsSkipProxyDetectionEnabled",
      L"ReadBoolOption",
      (unsigned int)v2);
  v3 = v14;
  *((_DWORD *)this + 4) = v14;
  v4 = v3 ? 4 : 0;
  v5 = WinHttpOpen(0, v4, 0, 0, 0x10000000u);
  *((_QWORD *)this + 1) = v5;
  if ( v5 )
  {
    v13 = 0x10000000;
    Logger::TraceVerbose(
      L"%s: Winhttp initialized. User agent: %s. Access type: %lu. Proxy name: %s. Proxy bypass address list: %s. Flags: %lu.",
      L"WinHttpSession::Initialize",
      0,
      v4,
      0,
      0,
      v13);
    return 0;
  }
  else
  {
    LastError = GetLastError();
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
    {
      v10 = McTemplateU0zqzzqq_EventWriteTransfer(v7, v6, v9, v4, dwFlags);
      if ( v10 )
        Logger::TraceError(
          L"%s: %s failed with win32 error code: 0x%08x.",
          L"Logger::WriteWinhttpInitializationFailureEvent",
          L"EventWriteWinhttpInitializationFailureEvent",
          v10);
    }
    Logger::TraceError(L"%s: WinHttpOpen failed with error code: 0x%08x", L"WinHttpSession::Initialize", LastError);
    if ( (int)LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    return LastError;
  }
}

```

## disassembly

```asm
0x1800985e4  mov     [rsp+arg_8], rbx
0x1800985e9  push    rdi
0x1800985ea  sub     rsp, 40h
0x1800985ee  lea     rdx, [rsp+48h+arg_0]; bool *
0x1800985f3  mov     [rsp+48h+arg_0], 1
0x1800985f8  mov     rbx, rcx
0x1800985fb  call    ?ReadBoolOption@@YAJPEBGPEA_N@Z; ReadBoolOption(ushort const *,bool *)
0x180098600  test    eax, eax
0x180098602  jns     short loc_180098621
0x180098604  mov     r9d, eax
0x180098607  lea     r8, aReadbooloption; "ReadBoolOption"
0x18009860e  lea     rdx, aIsskipproxydet; "IsSkipProxyDetectionEnabled"
0x180098615  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18009861c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180098621  movzx   eax, [rsp+48h+arg_0]
0x180098626  mov     [rbx+10h], eax
0x180098629  neg     eax
0x18009862b  mov     [rsp+48h+dwFlags], 10000000h; dwFlags
0x180098633  sbb     edi, edi
0x180098635  xor     r9d, r9d; pszProxyBypassW
0x180098638  and     edi, 4
0x18009863b  xor     r8d, r8d; pszProxyW
0x18009863e  mov     edx, edi; dwAccessType
0x180098640  xor     ecx, ecx; pszAgentW
0x180098642  call    cs:__imp_WinHttpOpen
0x180098648  mov     [rbx+8], rax
0x18009864c  test    rax, rax
0x18009864f  jnz     short loc_1800986B6
0x180098651  call    cs:__imp_GetLastError
0x180098657  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x18009865e  mov     ebx, eax
0x180098660  jz      short loc_18009868F
0x180098662  mov     r9d, edi
0x180098665  mov     [rsp+48h+var_10], eax
0x180098669  call    McTemplateU0zqzzqq_EventWriteTransfer
0x18009866e  test    eax, eax
0x180098670  jz      short loc_18009868F
0x180098672  mov     r9d, eax
0x180098675  lea     r8, aEventwritewinh_7; "EventWriteWinhttpInitializationFailureE"...
0x18009867c  lea     rdx, aLoggerWritewin_8; "Logger::WriteWinhttpInitializationFailu"...
0x180098683  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18009868a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18009868f  mov     r8d, ebx
0x180098692  lea     rdx, aWinhttpsession; "WinHttpSession::Initialize"
0x180098699  lea     rcx, aSWinhttpopenFa; "%s: WinHttpOpen failed with error code:"...
0x1800986a0  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800986a5  test    ebx, ebx
0x1800986a7  jle     short loc_1800986B2
0x1800986a9  movzx   ebx, bx
0x1800986ac  or      ebx, 80070000h
0x1800986b2  mov     eax, ebx
0x1800986b4  jmp     short loc_1800986EB
0x1800986b6  mov     [rsp+48h+var_18], 10000000h
0x1800986be  lea     rdx, aWinhttpsession; "WinHttpSession::Initialize"
0x1800986c5  mov     [rsp+48h+var_20], 0
0x1800986ce  lea     rcx, aSWinhttpInitia; "%s: Winhttp initialized. User agent: %s"...
0x1800986d5  mov     r9d, edi
0x1800986d8  mov     qword ptr [rsp+48h+dwFlags], 0
0x1800986e1  xor     r8d, r8d
0x1800986e4  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800986e9  xor     eax, eax
0x1800986eb  mov     rbx, [rsp+48h+arg_8]
0x1800986f0  add     rsp, 40h
0x1800986f4  pop     rdi
0x1800986f5  retn
```
