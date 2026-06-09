# wil::details::functor_wrapper_void__lambda_ce3718dc83b7418c8c606f4b3eec2356___::Run

- ea: `0x14000c340`
- end: `0x14000c4c4`
- name: `wil::details::functor_wrapper_void__lambda_ce3718dc83b7418c8c606f4b3eec2356___::Run`
- size: `388`
- prototype: `__int64 __fastcall(CExec *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140002310`
- `0x140007a0c`
- `0x140008418`
- `0x1400093d4`
- `0x140009490`
- `0x14000c340`
- `0x14000d338`
- `0x14000e828`
- `0x140018bc4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c3a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c3e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c3a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c3e5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14000c393`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14000c3db`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14000c393`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14000c3db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14000c37f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14000c3c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14000c37f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14000c3c8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14000c3ed`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14000c3ed`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x14000c3b6`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x14000c3b6`
- `api-ms-win-core-shutdown-l1-1-0!InitiateSystemShutdownExW` at `0x14000c43e`
- `api-ms-win-core-shutdown-l1-1-0!InitiateSystemShutdownExW` at `0x14000c43e`

## string_xrefs

- `0x14000c3fe`: `onecore\vm\common\vml\VmSecurity.h`
- `0x14000c492`: `onecore\vm\common\vml\VmSecurity.h`
- `0x14000c4a4`: `onecore\vm\common\vml\VmSecurity.h`
- `0x14000c46e`: `onecore\vm\compute\service\cexec\service\cexecrequestserver.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::functor_wrapper_void__lambda_ce3718dc83b7418c8c606f4b3eec2356___::Run(CExec *a1)
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  const char *v3; // r9
  HANDLE v4; // rax
  DWORD v5; // ebx
  unsigned int v6; // eax
  const char *v7; // r9
  const char *v8; // r9
  BOOL bRebootAfterShutdown; // [rsp+20h] [rbp-30h]
  void *TokenHandle[2]; // [rsp+30h] [rbp-20h] BYREF
  __int64 v12; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]

  CExec::NotifyAndWaitForShutdown(a1);
  TokenHandle[1] = 0;
  v12 = 0;
  TokenHandle[0] = (void *)19;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x28u, 0, &TokenHandle[1]) )
  {
    LastError = GetLastError();
    if ( LastError != 1008 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1DD7,
        (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
        (const char *)LastError,
        bRebootAfterShutdown);
    if ( !ImpersonateSelf(SecurityImpersonation) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x1DDA,
        (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
        v3);
    v4 = GetCurrentThread();
    if ( !OpenThreadToken(v4, 0x28u, 0, &TokenHandle[1]) )
    {
      v5 = GetLastError();
      v6 = RevertToSelf();
      if ( (unsigned __int8)wil::verify_bool<int,0>(v6) )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x1DDF,
          (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
          (const char *)v5,
          bRebootAfterShutdown);
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x1DDE,
        (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
        v7);
    }
    BYTE4(v12) = 1;
  }
  LODWORD(v12) = Vml::VmAccessToken::EnablePrivilege(
                   (Vml::VmAccessToken *)&TokenHandle[1],
                   (const struct _LUID *)TokenHandle,
                   1);
  if ( !InitiateSystemShutdownExW(0, 0, 0, 1, 0, 0x80000000) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xCF,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\service\\cexecrequestserver.cpp",
      v8);
  Vml::TemporaryPrivilege::~TemporaryPrivilege((Vml::TemporaryPrivilege *)TokenHandle);
  return 0;
}

```

## disassembly

```asm
0x14000c340  mov     [rsp-8+arg_0], rbx
0x14000c345  push    rbp
0x14000c346  mov     rbp, rsp
0x14000c349  sub     rsp, 50h
0x14000c34d  mov     rax, cs:__security_cookie
0x14000c354  xor     rax, rsp
0x14000c357  mov     [rbp+var_8], rax
0x14000c35b  call    ?NotifyAndWaitForShutdown@CExec@@YA_NXZ; CExec::NotifyAndWaitForShutdown(void)
0x14000c360  xorps   xmm0, xmm0
0x14000c363  xor     eax, eax
0x14000c365  movups  xmmword ptr [rbp+TokenHandle], xmm0
0x14000c369  mov     [rbp+var_10], rax
0x14000c36d  mov     [rbp+TokenHandle+8], rax
0x14000c371  mov     dword ptr [rbp+var_10], eax
0x14000c374  mov     byte ptr [rbp+var_10+4], al
0x14000c377  mov     [rbp+TokenHandle], 13h
0x14000c37f  call    cs:__imp_GetCurrentThread
0x14000c385  lea     r9, [rbp+TokenHandle+8]; TokenHandle
0x14000c389  xor     r8d, r8d; OpenAsSelf
0x14000c38c  lea     edx, [r8+28h]; DesiredAccess
0x14000c390  mov     rcx, rax; ThreadHandle
0x14000c393  call    cs:__imp_OpenThreadToken
0x14000c399  mov     ebx, 1
0x14000c39e  test    eax, eax
0x14000c3a0  jnz     short loc_14000C411
0x14000c3a2  call    cs:__imp_GetLastError
0x14000c3a8  cmp     eax, 3F0h
0x14000c3ad  jnz     loc_14000C48B
0x14000c3b3  lea     ecx, [rbx+1]; ImpersonationLevel
0x14000c3b6  call    cs:__imp_ImpersonateSelf
0x14000c3bc  mov     rcx, [rbp+8]; this
0x14000c3c0  test    eax, eax
0x14000c3c2  jz      loc_14000C4A4
0x14000c3c8  call    cs:__imp_GetCurrentThread
0x14000c3ce  lea     r9, [rbp+TokenHandle+8]; TokenHandle
0x14000c3d2  xor     r8d, r8d; OpenAsSelf
0x14000c3d5  lea     edx, [rbx+27h]; DesiredAccess
0x14000c3d8  mov     rcx, rax; ThreadHandle
0x14000c3db  call    cs:__imp_OpenThreadToken
0x14000c3e1  test    eax, eax
0x14000c3e3  jnz     short loc_14000C40E
0x14000c3e5  call    cs:__imp_GetLastError
0x14000c3eb  mov     ebx, eax
0x14000c3ed  call    cs:__imp_RevertToSelf
0x14000c3f3  mov     ecx, eax
0x14000c3f5  call    ??$verify_bool@H$0A@@wil@@YA_NH@Z; wil::verify_bool<int,0>(int)
0x14000c3fa  mov     rcx, [rbp+8]; this
0x14000c3fe  lea     r8, aOnecoreVmCommo_2; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x14000c405  test    al, al
0x14000c407  jz      short loc_14000C480
0x14000c409  jmp     loc_14000C4B6
0x14000c40e  mov     byte ptr [rbp+var_10+4], bl
0x14000c411  mov     r8d, ebx; int
0x14000c414  lea     rdx, [rbp+TokenHandle]; struct _LUID *
0x14000c418  lea     rcx, [rbp+TokenHandle+8]; this
0x14000c41c  call    ?EnablePrivilege@VmAccessToken@Vml@@QEAAHAEBU_LUID@@H@Z; Vml::VmAccessToken::EnablePrivilege(_LUID const &,int)
0x14000c421  mov     dword ptr [rbp+var_10], eax
0x14000c424  mov     [rsp+50h+dwReason], 80000000h; dwReason
0x14000c42c  mov     [rsp+50h+bRebootAfterShutdown], 0; bRebootAfterShutdown
0x14000c434  mov     r9d, ebx; bForceAppsClosed
0x14000c437  xor     r8d, r8d; dwTimeout
0x14000c43a  xor     edx, edx; lpMessage
0x14000c43c  xor     ecx, ecx; lpMachineName
0x14000c43e  call    cs:__imp_InitiateSystemShutdownExW
0x14000c444  mov     rcx, [rbp+8]; this
0x14000c448  test    eax, eax
0x14000c44a  jz      short loc_14000C46E
0x14000c44c  lea     rcx, [rbp+TokenHandle]; this
0x14000c450  call    ??1TemporaryPrivilege@Vml@@QEAA@XZ; Vml::TemporaryPrivilege::~TemporaryPrivilege(void)
0x14000c455  xor     eax, eax
0x14000c457  mov     rcx, [rbp+var_8]
0x14000c45b  xor     rcx, rsp; StackCookie
0x14000c45e  call    __security_check_cookie
0x14000c463  mov     rbx, [rsp+50h+arg_0]
0x14000c468  add     rsp, 50h
0x14000c46c  pop     rbp
0x14000c46d  retn
0x14000c46e  lea     r8, aOnecoreVmCompu_0; "onecore\\vm\\compute\\service\\cexec\\s"...
0x14000c475  mov     edx, 0CFh; void *
0x14000c47a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14000c480  mov     edx, 1DDEh; void *
0x14000c485  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14000c48b  mov     rcx, [rbp+8]; this
0x14000c48f  mov     r9d, eax; char *
0x14000c492  lea     r8, aOnecoreVmCommo_2; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x14000c499  mov     edx, 1DD7h; void *
0x14000c49e  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x14000c4a4  lea     r8, aOnecoreVmCommo_2; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x14000c4ab  mov     edx, 1DDAh; void *
0x14000c4b0  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14000c4b6  mov     r9d, ebx; char *
0x14000c4b9  mov     edx, 1DDFh; void *
0x14000c4be  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
