# SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::GetCurrentUserSid(void * *)

- ea: `0x18004884c`
- end: `0x180048963`
- name: `?GetCurrentUserSid@BackgroundCapabilitySingleton@BatteryUsageHandlers@SystemSettings@@AEAAJPEAPEAX@Z`
- size: `279`
- prototype: `int(SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton *__hidden this, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004896c`

## callees

- `0x1800028d0`
- `0x18000a13c`
- `0x180047fcc`
- `0x18004884c`
- `0x180048d80`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180048897`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180048897`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004887e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004887e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800488ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800488ad`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800488bd`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800488bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004893a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004893a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800488f3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800488f3`

## pseudocode

```c
__int64 __fastcall SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::GetCurrentUserSid(
        SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton *this,
        void **a2)
{
  HANDLE CurrentThread; // rax
  __int64 result; // rax
  HANDLE CurrentProcess; // rax
  SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton *v6; // rcx
  int Error; // eax
  unsigned int v8; // ebx
  int ReturnLength; // [rsp+20h] [rbp-98h]
  void *TokenHandle; // [rsp+30h] [rbp-88h] BYREF
  DWORD v11; // [rsp+38h] [rbp-80h] BYREF
  void *TokenInformation; // [rsp+40h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  TokenHandle = 0;
  *a2 = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    result = ResultFromKnownLastError();
    if ( (_DWORD)result != -2147023888 )
      goto LABEL_5;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
      result = ResultFromKnownLastError();
LABEL_5:
      if ( (int)result < 0 )
        return result;
    }
  }
  v11 = 88;
  if ( GetTokenInformation(TokenHandle, TokenUser, &TokenInformation, 0x58u, &v11)
    || (Error = ResultFromKnownLastError(), v8 = Error, Error >= 0) )
  {
    v8 = SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::AllocAndCopySid(v6, TokenInformation, a2);
    CloseHandle(TokenHandle);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF5,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\backgroundcapabilitysingleton.cpp",
      (const char *)(unsigned int)Error,
      ReturnLength);
  }
  return v8;
}

```

## disassembly

```asm
0x18004884c  mov     [rsp+arg_0], rbx
0x180048851  push    rdi
0x180048852  sub     rsp, 0B0h
0x180048859  mov     rax, cs:__security_cookie
0x180048860  xor     rax, rsp
0x180048863  mov     [rsp+0B8h+var_18], rax
0x18004886b  mov     rdi, rdx
0x18004886e  mov     [rsp+0B8h+TokenHandle], 0
0x180048877  mov     qword ptr [rdx], 0
0x18004887e  call    cs:__imp_GetCurrentThread
0x180048884  mov     ebx, 8
0x180048889  lea     r9, [rsp+0B8h+TokenHandle]; TokenHandle
0x18004888e  mov     rcx, rax; ThreadHandle
0x180048891  mov     edx, ebx; DesiredAccess
0x180048893  lea     r8d, [rbx-7]; OpenAsSelf
0x180048897  call    cs:__imp_OpenThreadToken
0x18004889d  test    eax, eax
0x18004889f  jnz     short loc_1800488D0
0x1800488a1  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800488a6  cmp     eax, 800703F0h
0x1800488ab  jnz     short loc_1800488CC
0x1800488ad  call    cs:__imp_GetCurrentProcess
0x1800488b3  lea     r8, [rsp+0B8h+TokenHandle]; TokenHandle
0x1800488b8  mov     edx, ebx; DesiredAccess
0x1800488ba  mov     rcx, rax; ProcessHandle
0x1800488bd  call    cs:__imp_OpenProcessToken
0x1800488c3  test    eax, eax
0x1800488c5  jnz     short loc_1800488D0
0x1800488c7  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800488cc  test    eax, eax
0x1800488ce  js      short loc_180048942
0x1800488d0  mov     rcx, [rsp+0B8h+TokenHandle]; TokenHandle
0x1800488d5  lea     rax, [rsp+0B8h+var_80]
0x1800488da  mov     r9d, 58h ; 'X'; TokenInformationLength
0x1800488e0  mov     qword ptr [rsp+0B8h+ReturnLength], rax; int
0x1800488e5  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x1800488ea  mov     [rsp+0B8h+var_80], r9d
0x1800488ef  lea     edx, [r9-57h]; TokenInformationClass
0x1800488f3  call    cs:__imp_GetTokenInformation
0x1800488f9  test    eax, eax
0x1800488fb  jnz     short loc_180048926
0x1800488fd  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180048902  mov     ebx, eax
0x180048904  test    eax, eax
0x180048906  jns     short loc_180048926
0x180048908  mov     rcx, [rsp+0B8h]; this
0x180048910  lea     r8, aOnecoreuapShel_12; "onecoreuap\\shell\\coresettinghandlers"...
0x180048917  mov     r9d, eax; char *
0x18004891a  mov     edx, 0F5h; void *
0x18004891f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048924  jmp     short loc_180048940
0x180048926  mov     rdx, [rsp+0B8h+TokenInformation]; void *
0x18004892b  mov     r8, rdi; void **
0x18004892e  call    ?AllocAndCopySid@BackgroundCapabilitySingleton@BatteryUsageHandlers@SystemSettings@@AEAAJPEAXPEAPEAX@Z; SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::AllocAndCopySid(void *,void * *)
0x180048933  mov     rcx, [rsp+0B8h+TokenHandle]; hObject
0x180048938  mov     ebx, eax
0x18004893a  call    cs:__imp_CloseHandle
0x180048940  mov     eax, ebx
0x180048942  mov     rcx, [rsp+0B8h+var_18]
0x18004894a  xor     rcx, rsp; StackCookie
0x18004894d  call    __security_check_cookie
0x180048952  mov     rbx, [rsp+0B8h+arg_0]
0x18004895a  add     rsp, 0B0h
0x180048961  pop     rdi
0x180048962  retn
```
