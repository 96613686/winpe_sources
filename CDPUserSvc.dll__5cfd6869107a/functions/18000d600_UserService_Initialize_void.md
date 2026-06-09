# UserService::Initialize(void)

- ea: `0x18000d600`
- end: `0x18000d732`
- name: `?Initialize@UserService@@UEAAJXZ`
- size: `306`
- prototype: `__int64 __fastcall(UserService *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task`

## callees

- `0x180004a58`
- `0x180004a98`
- `0x180005028`
- `0x18000d288`
- `0x18000d600`
- `0x180025598`
- `0x1800258d8`
- `0x1800263a8`
- `0x18002c570`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000d65f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000d65f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d6f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d6f1`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000d6e7`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000d6e7`

## string_xrefs

- `0x18000d67f`: `{"text":"Failed to initialize service. hr = 0x%8X"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UserService::Initialize(UserService *this)
{
  int v2; // eax
  unsigned int v3; // ebx
  signed int LastError; // eax
  unsigned int v6; // [rsp+20h] [rbp-50h] BYREF
  HMODULE phModule; // [rsp+28h] [rbp-48h] BYREF
  _QWORD *v8; // [rsp+30h] [rbp-40h] BYREF
  _QWORD v9[2]; // [rsp+38h] [rbp-38h] BYREF
  _BYTE v10[32]; // [rsp+48h] [rbp-28h] BYREF

  CheckForDebugger();
  v6 = 0;
  phModule = 0;
  v9[0] = &phModule;
  v9[1] = &v6;
  v8 = v9;
  if ( !GetModuleHandleExW(4u, (LPCWSTR)UserService::RegisterCallbackThunk, &phModule) )
    goto LABEL_6;
  v2 = UserService::Start(this);
  v6 = v2;
  if ( v2 >= 0 )
  {
    v3 = -2147418113;
    if ( !*((_QWORD *)this + 3)
      || (v3 = 0,
          *((_DWORD *)this + 18) = 193,
          *((_DWORD *)this + 17) = 4,
          *((_DWORD *)this + 19) = 0,
          *((_DWORD *)this + 22) = 0,
          *((_DWORD *)this + 21) = 0,
          SetServiceStatus(*((SERVICE_STATUS_HANDLE *)this + 3), (LPSERVICE_STATUS)((char *)this + 64))) )
    {
LABEL_8:
      v6 = v3;
      goto LABEL_9;
    }
LABEL_6:
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_8;
  }
  cdp::detail::StringFormat(v10, "{\"text\":\"Failed to initialize service. hr = 0x%8X\"}", v2);
  shared::LogMessage(1, v10);
  std::string::_Tidy_deallocate(v10);
  *((_DWORD *)this + 30) = 1;
  NTUserService::SignalServiceStop(this);
  v3 = v6;
LABEL_9:
  ScopeWarden__lambda_c9b9a365f923257490a2dd6af2563e58___::_ScopeWarden__lambda_c9b9a365f923257490a2dd6af2563e58___(&v8);
  return v3;
}

```

## disassembly

```asm
0x18000d600  mov     [rsp-8+arg_8], rbx
0x18000d605  mov     [rsp-8+arg_10], rdi
0x18000d60a  push    rbp
0x18000d60b  mov     rbp, rsp
0x18000d60e  sub     rsp, 70h
0x18000d612  mov     rax, cs:__security_cookie
0x18000d619  xor     rax, rsp
0x18000d61c  mov     [rbp+var_8], rax
0x18000d620  mov     rdi, rcx
0x18000d623  call    ?CheckForDebugger@@YAXXZ; CheckForDebugger(void)
0x18000d628  mov     [rbp+var_50], 0
0x18000d62f  mov     [rbp+phModule], 0
0x18000d637  lea     rax, [rbp+phModule]
0x18000d63b  mov     [rbp+var_38], rax
0x18000d63f  lea     rax, [rbp+var_50]
0x18000d643  mov     [rbp+var_30], rax
0x18000d647  lea     rax, [rbp+var_38]
0x18000d64b  mov     [rbp+var_40], rax
0x18000d64f  lea     r8, [rbp+phModule]; phModule
0x18000d653  lea     rdx, ?RegisterCallbackThunk@UserService@@CAJPEAUtagComCallData@@@Z; lpModuleName
0x18000d65a  mov     ecx, 4; dwFlags
0x18000d65f  call    cs:__imp_GetModuleHandleExW
0x18000d665  test    eax, eax
0x18000d667  jz      loc_18000D6F1
0x18000d66d  mov     rcx, rdi; this
0x18000d670  call    ?Start@UserService@@QEAAJXZ; UserService::Start(void)
0x18000d675  mov     [rbp+var_50], eax
0x18000d678  test    eax, eax
0x18000d67a  jns     short loc_18000D6BA
0x18000d67c  mov     r8d, eax
0x18000d67f  lea     rdx, aTextFailedToIn; "{\"text\":\"Failed to initialize servic"...
0x18000d686  lea     rcx, [rbp+var_28]
0x18000d68a  call    ?StringFormat@detail@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDZZ; cdp::detail::StringFormat(char const *,...)
0x18000d68f  nop
0x18000d690  lea     rdx, [rbp+var_28]
0x18000d694  mov     ebx, 1
0x18000d699  mov     ecx, ebx
0x18000d69b  call    ?LogMessage@shared@@YAXW4CDPLogLevel@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; shared::LogMessage(CDPLogLevel,std::string &)
0x18000d6a0  nop
0x18000d6a1  lea     rcx, [rbp+var_28]
0x18000d6a5  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18000d6aa  mov     [rdi+78h], ebx
0x18000d6ad  mov     rcx, rdi; this
0x18000d6b0  call    ?SignalServiceStop@NTUserService@@QEBAXXZ; NTUserService::SignalServiceStop(void)
0x18000d6b5  mov     ebx, [rbp+var_50]
0x18000d6b8  jmp     short loc_18000D709
0x18000d6ba  mov     ebx, 8000FFFFh
0x18000d6bf  cmp     qword ptr [rdi+18h], 0
0x18000d6c4  jz      short loc_18000D706
0x18000d6c6  xor     ebx, ebx
0x18000d6c8  lea     rdx, [rdi+40h]; lpServiceStatus
0x18000d6cc  mov     dword ptr [rdi+48h], 0C1h
0x18000d6d3  mov     dword ptr [rdi+44h], 4
0x18000d6da  mov     [rdi+4Ch], ebx
0x18000d6dd  mov     [rdi+58h], ebx
0x18000d6e0  mov     [rdx+14h], ebx
0x18000d6e3  mov     rcx, [rdi+18h]; hServiceStatus
0x18000d6e7  call    cs:__imp_SetServiceStatus
0x18000d6ed  test    eax, eax
0x18000d6ef  jnz     short loc_18000D706
0x18000d6f1  call    cs:__imp_GetLastError
0x18000d6f7  test    eax, eax
0x18000d6f9  mov     ebx, eax
0x18000d6fb  jle     short loc_18000D706
0x18000d6fd  movzx   ebx, ax
0x18000d700  or      ebx, 80070000h
0x18000d706  mov     [rbp+var_50], ebx
0x18000d709  lea     rcx, [rbp+var_40]
0x18000d70d  call    ScopeWarden__lambda_c9b9a365f923257490a2dd6af2563e58______ScopeWarden__lambda_c9b9a365f923257490a2dd6af2563e58___
0x18000d712  mov     eax, ebx
0x18000d714  mov     rcx, [rbp+var_8]
0x18000d718  xor     rcx, rsp; StackCookie
0x18000d71b  call    __security_check_cookie
0x18000d720  lea     r11, [rsp+70h+var_s0]
0x18000d725  mov     rbx, [r11+18h]
0x18000d729  mov     rdi, [r11+20h]
0x18000d72d  mov     rsp, r11
0x18000d730  pop     rbp
0x18000d731  retn
```
