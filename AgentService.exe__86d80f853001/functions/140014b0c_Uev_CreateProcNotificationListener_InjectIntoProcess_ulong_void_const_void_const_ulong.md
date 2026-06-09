# Uev::CreateProcNotificationListener::InjectIntoProcess(ulong,void * const,void * const,ulong)

- ea: `0x140014b0c`
- end: `0x140014d98`
- name: `?InjectIntoProcess@CreateProcNotificationListener@Uev@@AEAAXKQEAX0K@Z`
- size: `652`
- prototype: `void __fastcall(Uev::CreateProcNotificationListener *this, unsigned int, void *const, void *const, unsigned int TokenInformation)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140015630`

## callees

- `0x140003e50`
- `0x140004ab4`
- `0x14000ac88`
- `0x14000acc4`
- `0x14000d1d8`
- `0x14000d260`
- `0x14000d2d8`
- `0x1400131ec`
- `0x140014b0c`
- `0x140015224`

## import_xrefs

- `ADVAPI32!DuplicateTokenEx` at `0x140014bec`
- `ADVAPI32!DuplicateTokenEx` at `0x140014bec`
- `ADVAPI32!SetTokenInformation` at `0x140014c20`
- `ADVAPI32!SetTokenInformation` at `0x140014c20`
- `KERNEL32!GetLastError` at `0x140014c52`
- `KERNEL32!GetLastError` at `0x140014c61`
- `KERNEL32!GetLastError` at `0x140014cad`
- `KERNEL32!GetLastError` at `0x140014c52`
- `KERNEL32!GetLastError` at `0x140014c61`
- `KERNEL32!GetLastError` at `0x140014cad`
- `KERNEL32!IsWow64Process` at `0x140014b6f`
- `KERNEL32!IsWow64Process` at `0x140014b6f`

## string_xrefs

- `0x140014d5e`: `Attempting to assign an already-valid handle.`
- `0x140014cf2`: `Attempting to use an invalid handle.`
- `0x140014d25`: `Attempting to use an invalid handle.`
- `0x140014b4d`: `AgentService.CreateProcNotificationListener::GetInjectionExePaths: Entry`
- `0x140014b87`: `AgentService.CreateProcNotificationListener::GetInjectionExePaths: x86 executables`
- `0x140014b95`: `AgentService.CreateProcNotificationListener::GetInjectionExePaths: x64 executables`
- `0x140014cb6`: `AgentService.CreateProcNotificationListener::GetInjectionExePaths: Failed to determine if process is running under WoW64`
- `0x140014ba6`: `AgentService.CreateProcNotificationListener::GetInjectionExePaths: Exit`
- `0x140014b40`: `AgentService.CreateProcNotificationListener::InjectIntoProcess: Entry`
- `0x140014c58`: `AgentService.CreateProcNotificationListener::InjectIntoProcess: Failed to set session id in token, error = 0x%X`
- `0x140014c67`: `AgentService.CreateProcNotificationListener::InjectIntoProcess: Failed to get primary token for MavInject, error = 0x%X`
- `0x140014c76`: `AgentService.CreateProcNotificationListener::InjectIntoProcess: Exit`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall Uev::CreateProcNotificationListener::InjectIntoProcess(
        Uev::CreateProcNotificationListener *this,
        unsigned int a2,
        void *const a3,
        void *const a4,
        unsigned int TokenInformation)
{
  const wchar_t *v9; // rcx
  __int64 v10; // rbx
  wchar_t *v11; // rcx
  DWORD LastError; // ebx
  _BYTE v13[48]; // [rsp+30h] [rbp-1A8h] BYREF
  _BYTE v14[64]; // [rsp+60h] [rbp-178h] BYREF
  _BYTE v15[64]; // [rsp+A0h] [rbp-138h] BYREF
  _BYTE v16[64]; // [rsp+E0h] [rbp-F8h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+120h] [rbp-B8h] BYREF
  BOOL Wow64Process; // [rsp+190h] [rbp-48h] BYREF
  HANDLE TokenHandle; // [rsp+198h] [rbp-40h] BYREF

  TokenHandle = (HANDLE)-1LL;
  DbgTrace<5>(L"AgentService.CreateProcNotificationListener::InjectIntoProcess: Entry");
  DbgTrace<5>(L"AgentService.CreateProcNotificationListener::GetInjectionExePaths: Entry");
  Wow64Process = 0;
  if ( !IsWow64Process(a3, &Wow64Process) )
  {
    LastError = GetLastError();
    std::wstring::wstring(
      v13,
      L"AgentService.CreateProcNotificationListener::GetInjectionExePaths: Failed to determine if process is running under WoW64");
    Uev::SystemException::SystemException(pExceptionObject, v13, LastError);
    throw (Uev::SystemException *)pExceptionObject;
  }
  if ( Wow64Process )
  {
    v9 = L"AgentService.CreateProcNotificationListener::GetInjectionExePaths: x86 executables";
    v10 = 160;
  }
  else
  {
    v9 = L"AgentService.CreateProcNotificationListener::GetInjectionExePaths: x64 executables";
    v10 = 224;
  }
  DbgTrace<5>(v9);
  DbgTrace<5>(L"AgentService.CreateProcNotificationListener::GetInjectionExePaths: Exit");
  if ( (((unsigned __int64)TokenHandle + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    std::wstring::wstring(v13, L"Attempting to assign an already-valid handle.");
    Uev::SmartHandleException::SmartHandleException(v16, v13);
    throw (Uev::SmartHandleException *)v16;
  }
  if ( !DuplicateTokenEx(a4, 0x2000000u, 0, SecurityIdentification, TokenPrimary, &TokenHandle) )
  {
    GetLastError();
    v11 = (wchar_t *)L"AgentService.CreateProcNotificationListener::InjectIntoProcess: Failed to get primary token for Mav"
                      "Inject, error = 0x%X";
    goto LABEL_13;
  }
  if ( (((unsigned __int64)TokenHandle + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    std::wstring::wstring(v13, L"Attempting to use an invalid handle.");
    Uev::SmartHandleException::SmartHandleException(v14, v13);
    throw (Uev::SmartHandleException *)v14;
  }
  if ( !SetTokenInformation(TokenHandle, TokenSessionId, &TokenInformation, 4u) )
  {
    GetLastError();
    v11 = L"AgentService.CreateProcNotificationListener::InjectIntoProcess: Failed to set session id in token, error = 0x%X";
LABEL_13:
    DbgTraceFrmtErr<long>(v11);
    goto LABEL_14;
  }
  if ( (((unsigned __int64)TokenHandle + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    std::wstring::wstring(v13, L"Attempting to use an invalid handle.");
    Uev::SmartHandleException::SmartHandleException(v15, v13);
    throw (Uev::SmartHandleException *)v15;
  }
  Uev::CreateProcNotificationListener::LaunchAndWaitForInjectionProcess(
    this,
    a2,
    (Uev::CreateProcNotificationListener *)((char *)this + v10),
    TokenHandle);
LABEL_14:
  DbgTrace<5>(L"AgentService.CreateProcNotificationListener::InjectIntoProcess: Exit");
  Uev::SmartHandle<void *,&void Uev::CloseHandleWrapper(void *),-1>::~SmartHandle<void *,&void Uev::CloseHandleWrapper(void *),-1>(&TokenHandle);
}

```

## disassembly

```asm
0x140014b0c  mov     r11, rsp
0x140014b0f  push    rbx
0x140014b10  push    rsi
0x140014b11  push    rdi
0x140014b12  push    r14
0x140014b14  sub     rsp, 1B8h
0x140014b1b  mov     rax, cs:__security_cookie
0x140014b22  xor     rax, rsp
0x140014b25  mov     [rsp+1D8h+var_38], rax
0x140014b2d  mov     r14, r9
0x140014b30  mov     rbx, r8
0x140014b33  mov     esi, edx
0x140014b35  mov     rdi, rcx
0x140014b38  mov     qword ptr [r11-40h], 0FFFFFFFFFFFFFFFFh
0x140014b40  lea     rcx, aAgentserviceCr_4; "AgentService.CreateProcNotificationList"...
0x140014b47  call    ??$DbgTrace@$04@@YAXPEB_W@Z; DbgTrace<5>(wchar_t const *)
0x140014b4c  nop
0x140014b4d  lea     rcx, aAgentserviceCr_23; "AgentService.CreateProcNotificationList"...
0x140014b54  call    ??$DbgTrace@$04@@YAXPEB_W@Z; DbgTrace<5>(wchar_t const *)
0x140014b59  mov     [rsp+1D8h+Wow64Process], 0
0x140014b64  lea     rdx, [rsp+1D8h+Wow64Process]; Wow64Process
0x140014b6c  mov     rcx, rbx; hProcess
0x140014b6f  call    cs:__imp_IsWow64Process
0x140014b75  test    eax, eax
0x140014b77  jz      loc_140014CAD
0x140014b7d  cmp     [rsp+1D8h+Wow64Process], 0
0x140014b85  jz      short loc_140014B95
0x140014b87  lea     rcx, aAgentserviceCr_14; "AgentService.CreateProcNotificationList"...
0x140014b8e  mov     ebx, 0A0h
0x140014b93  jmp     short loc_140014BA1
0x140014b95  lea     rcx, aAgentserviceCr_11; "AgentService.CreateProcNotificationList"...
0x140014b9c  mov     ebx, 0E0h
0x140014ba1  call    ??$DbgTrace@$04@@YAXPEB_W@Z; DbgTrace<5>(wchar_t const *)
0x140014ba6  lea     rcx, aAgentserviceCr_26; "AgentService.CreateProcNotificationList"...
0x140014bad  call    ??$DbgTrace@$04@@YAXPEB_W@Z; DbgTrace<5>(wchar_t const *)
0x140014bb2  mov     rax, [rsp+1D8h+TokenHandle]
0x140014bba  inc     rax
0x140014bbd  test    rax, 0FFFFFFFFFFFFFFFEh
0x140014bc3  jnz     loc_140014D5E
0x140014bc9  lea     rax, [rsp+1D8h+TokenHandle]
0x140014bd1  mov     [rsp+1D8h+phNewToken], rax; phNewToken
0x140014bd6  mov     r9d, 1; ImpersonationLevel
0x140014bdc  mov     [rsp+1D8h+TokenType], r9d; TokenType
0x140014be1  xor     r8d, r8d; lpTokenAttributes
0x140014be4  mov     edx, 2000000h; dwDesiredAccess
0x140014be9  mov     rcx, r14; hExistingToken
0x140014bec  call    cs:__imp_DuplicateTokenEx
0x140014bf2  test    eax, eax
0x140014bf4  jz      short loc_140014C61
0x140014bf6  mov     rcx, [rsp+1D8h+TokenHandle]; TokenHandle
0x140014bfe  lea     rax, [rcx+1]
0x140014c02  test    rax, 0FFFFFFFFFFFFFFFEh
0x140014c08  jz      loc_140014CF2
0x140014c0e  mov     r9d, 4; TokenInformationLength
0x140014c14  lea     r8, [rsp+1D8h+TokenInformation]; TokenInformation
0x140014c1c  lea     edx, [r9+8]; TokenInformationClass
0x140014c20  call    cs:__imp_SetTokenInformation
0x140014c26  test    eax, eax
0x140014c28  jz      short loc_140014C52
0x140014c2a  mov     r9, [rsp+1D8h+TokenHandle]; void *
0x140014c32  lea     rax, [r9+1]
0x140014c36  test    rax, 0FFFFFFFFFFFFFFFEh
0x140014c3c  jz      loc_140014D25
0x140014c42  lea     r8, [rdi+rbx]; struct Uev::ExePaths *
0x140014c46  mov     edx, esi; unsigned int
0x140014c48  mov     rcx, rdi; this
0x140014c4b  call    ?LaunchAndWaitForInjectionProcess@CreateProcNotificationListener@Uev@@AEAAXKAEBVExePaths@2@QEAX@Z; Uev::CreateProcNotificationListener::LaunchAndWaitForInjectionProcess(ulong,Uev::ExePaths const &,void * const)
0x140014c50  jmp     short loc_140014C76
0x140014c52  call    cs:__imp_GetLastError
0x140014c58  lea     rcx, aAgentserviceCr_7; "AgentService.CreateProcNotificationList"...
0x140014c5f  jmp     short loc_140014C6E
0x140014c61  call    cs:__imp_GetLastError
0x140014c67  lea     rcx, aAgentserviceCr_27; "AgentService.CreateProcNotificationList"...
0x140014c6e  mov     edx, eax
0x140014c70  call    ??$DbgTraceFrmtErr@J@@YAXPEB_WJ@Z; DbgTraceFrmtErr<long>(wchar_t const *,long)
0x140014c75  nop
0x140014c76  lea     rcx, aAgentserviceCr_18; "AgentService.CreateProcNotificationList"...
0x140014c7d  call    ??$DbgTrace@$04@@YAXPEB_W@Z; DbgTrace<5>(wchar_t const *)
0x140014c82  nop
0x140014c83  lea     rcx, [rsp+1D8h+TokenHandle]
0x140014c8b  call    ??1?$SmartHandle@PEAX$1?CloseHandleWrapper@Uev@@YAXPEAX@Z$0?0@Uev@@QEAA@XZ; Uev::SmartHandle<void *,&Uev::CloseHandleWrapper(void *),-1>::~SmartHandle<void *,&Uev::CloseHandleWrapper(void *),-1>(void)
0x140014c90  mov     rcx, [rsp+1D8h+var_38]
0x140014c98  xor     rcx, rsp; StackCookie
0x140014c9b  call    __security_check_cookie
0x140014ca0  add     rsp, 1B8h
0x140014ca7  pop     r14
0x140014ca9  pop     rdi
0x140014caa  pop     rsi
0x140014cab  pop     rbx
0x140014cac  retn
0x140014cad  call    cs:__imp_GetLastError
0x140014cb3  nop
0x140014cb4  mov     ebx, eax
0x140014cb6  lea     rdx, aAgentserviceCr_32; "AgentService.CreateProcNotificationList"...
0x140014cbd  lea     rcx, [rsp+1D8h+var_1A8]
0x140014cc2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x140014cc7  nop
0x140014cc8  mov     r8d, ebx
0x140014ccb  lea     rdx, [rsp+1D8h+var_1A8]
0x140014cd0  lea     rcx, [rsp+1D8h+pExceptionObject]
0x140014cd8  call    ??0SystemException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@Z; Uev::SystemException::SystemException(std::wstring const &,ulong)
0x140014cdd  lea     rdx, _TI3?AVSystemException@Uev@@; pThrowInfo
0x140014ce4  lea     rcx, [rsp+1D8h+pExceptionObject]; pExceptionObject
0x140014cec  call    _CxxThrowException_0
0x140014cf2  lea     rdx, aAttemptingToUs; "Attempting to use an invalid handle."
0x140014cf9  lea     rcx, [rsp+1D8h+var_1A8]
0x140014cfe  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x140014d03  nop
0x140014d04  lea     rdx, [rsp+1D8h+var_1A8]
0x140014d09  lea     rcx, [rsp+1D8h+var_178]
0x140014d0e  call    ??0SmartHandleException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::SmartHandleException::SmartHandleException(std::wstring const &)
0x140014d13  lea     rdx, _TI3?AVSmartHandleException@Uev@@; pThrowInfo
0x140014d1a  lea     rcx, [rsp+1D8h+var_178]; pExceptionObject
0x140014d1f  call    _CxxThrowException_0
0x140014d25  lea     rdx, aAttemptingToUs; "Attempting to use an invalid handle."
0x140014d2c  lea     rcx, [rsp+1D8h+var_1A8]
0x140014d31  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x140014d36  nop
0x140014d37  lea     rdx, [rsp+1D8h+var_1A8]
0x140014d3c  lea     rcx, [rsp+1D8h+var_138]
0x140014d44  call    ??0SmartHandleException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::SmartHandleException::SmartHandleException(std::wstring const &)
0x140014d49  lea     rdx, _TI3?AVSmartHandleException@Uev@@; pThrowInfo
0x140014d50  lea     rcx, [rsp+1D8h+var_138]; pExceptionObject
0x140014d58  call    _CxxThrowException_0
0x140014d5e  lea     rdx, aAttemptingToAs; "Attempting to assign an already-valid h"...
0x140014d65  lea     rcx, [rsp+1D8h+var_1A8]
0x140014d6a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x140014d6f  nop
0x140014d70  lea     rdx, [rsp+1D8h+var_1A8]
0x140014d75  lea     rcx, [rsp+1D8h+var_F8]
0x140014d7d  call    ??0SmartHandleException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::SmartHandleException::SmartHandleException(std::wstring const &)
0x140014d82  lea     rdx, _TI3?AVSmartHandleException@Uev@@; pThrowInfo
0x140014d89  lea     rcx, [rsp+1D8h+var_F8]; pExceptionObject
0x140014d91  call    _CxxThrowException_0
```
