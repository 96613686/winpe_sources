# Wns::GetUserIdForCaller(void)

- ea: `0x18000c410`
- end: `0x18000c702`
- name: `?GetUserIdForCaller@Wns@@YA_KXZ`
- size: `754`
- prototype: `unsigned __int64 __fastcall(Wns *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800074f0`
- `0x18002e2c8`

## callees

- `0x18000aee0`
- `0x18000c410`
- `0x1800202bc`
- `0x180021048`
- `0x1800238d0`
- `0x180026200`
- `0x180026d3c`
- `0x180031da0`
- `0x180031dc4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c677`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c677`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c474`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c5cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c664`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c474`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c5cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c664`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000c452`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000c452`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000c4a7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000c4a7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000c46a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000c46a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000c495`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000c495`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c66f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c6f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c66f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c6f7`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000c4c3`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000c4c3`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000c435`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000c435`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x18000c58a`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x18000c58a`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18000c572`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18000c572`
- `ntdll!RtlInitializeSidEx` at `0x18000c505`
- `ntdll!RtlInitializeSidEx` at `0x18000c505`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000c522`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000c5ee`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000c522`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000c5ee`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000c627`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000c627`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18000c647`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18000c647`

## string_xrefs

- `0x18000c5b3`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnusermgrutil.cpp`
- `0x18000c691`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnusermgrutil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
unsigned __int64 __fastcall Wns::GetUserIdForCaller(Wns *this)
{
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  signed int v3; // ebx
  HANDLE CurrentProcess; // rax
  const char *v5; // r9
  void *v6; // rbx
  int v7; // eax
  void *v8; // rdx
  unsigned int v9; // r8d
  unsigned __int64 UserIdForContext; // rbx
  bool v12; // di
  unsigned int v13; // r8d
  const char *v14; // r9
  unsigned int v15; // r8d
  const char *v16; // r9
  unsigned int v17; // r8d
  const char *v18; // r9
  unsigned int v19; // r8d
  const char *v20; // r9
  WINBOOL IsMember; // [rsp+20h] [rbp-49h] BYREF
  void *TokenHandle; // [rsp+28h] [rbp-41h] BYREF
  int v23; // [rsp+30h] [rbp-39h] BYREF
  DWORD cbSid; // [rsp+34h] [rbp-35h] BYREF
  __int16 v25; // [rsp+38h] [rbp-31h]
  _OWORD SidToCheck[4]; // [rsp+40h] [rbp-29h] BYREF
  int v27; // [rsp+80h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  CoImpersonateClient();
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    goto LABEL_6;
  LastError = GetLastError();
  v3 = LastError;
  if ( LastError > 0 )
    v3 = (unsigned __int16)LastError | 0x80070000;
  if ( v3 == -2147023888 || v3 >= 0 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
      v3 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x25,
             (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnusermgrutil.cpp",
             v5);
      goto LABEL_7;
    }
LABEL_6:
    v3 = 0;
    goto LABEL_7;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1F,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnusermgrutil.cpp",
    (const char *)(unsigned int)v3,
    IsMember);
LABEL_7:
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x47,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\mux\\wpnutils.cpp",
      (const char *)(unsigned int)v3,
      IsMember);
  CoRevertToSelf();
  v6 = TokenHandle;
  memset(SidToCheck, 0, sizeof(SidToCheck));
  v27 = 0;
  cbSid = 0;
  v25 = 1280;
  IsMember = 0;
  v7 = RtlInitializeSidEx(SidToCheck, &cbSid, 1, 18);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(retaddr, v8, v9, (const char *)(unsigned int)v7, IsMember);
  if ( !CheckTokenMembership(v6, SidToCheck, &IsMember) )
  {
    if ( GetLastError() != 1309 )
      wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x69, v13, v14);
    if ( !CheckTokenMembership(0, SidToCheck, &IsMember) )
      wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x6B, v15, v16);
  }
  if ( IsMember )
    goto LABEL_11;
  IsMember = 0;
  RtlGetDeviceFamilyInfoEnum(0, &IsMember, 0);
  v12 = (unsigned int)(IsMember - 7) <= 1;
  if ( (unsigned __int8)RtlIsMultiUsersInSessionSku() || v12 )
  {
    cbSid = 68;
    v23 = 0;
    if ( !CreateWellKnownSid(WinAccountProtectedUsersSid|WinCreatorGroupSid, 0, SidToCheck, &cbSid) )
      wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x93, v17, v18);
    if ( !(unsigned int)CheckTokenMembershipEx(v6, SidToCheck, 0, &v23) )
      wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x95, v19, v20);
    if ( v23 == 1 )
      goto LABEL_11;
  }
  if ( !(unsigned __int8)IsUMgrQueryUserContextPresent() )
LABEL_11:
    UserIdForContext = 0;
  else
    UserIdForContext = GetUserIdForContext(v6);
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return UserIdForContext;
}

```

## disassembly

```asm
0x18000c410  push    rbp
0x18000c412  push    rbx
0x18000c413  push    rsi
0x18000c414  push    rdi
0x18000c415  lea     rbp, [rsp-3Fh]
0x18000c41a  sub     rsp, 0A8h
0x18000c421  mov     rax, cs:__security_cookie
0x18000c428  xor     rax, rsp
0x18000c42b  mov     [rbp+57h+var_28], rax
0x18000c42f  xor     esi, esi
0x18000c431  mov     [rbp+57h+TokenHandle], rsi
0x18000c435  call    cs:__imp_CoImpersonateClient
0x18000c43b  nop
0x18000c43c  mov     rdi, [rbp+57h+TokenHandle]
0x18000c440  lea     rax, [rdi-1]
0x18000c444  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000c448  jbe     loc_18000C664
0x18000c44e  mov     [rbp+57h+TokenHandle], rsi
0x18000c452  call    cs:__imp_GetCurrentThread
0x18000c458  mov     rcx, rax; ThreadHandle
0x18000c45b  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18000c45f  mov     edx, 8; DesiredAccess
0x18000c464  mov     r8d, 1; OpenAsSelf
0x18000c46a  call    cs:__imp_OpenThreadToken
0x18000c470  test    eax, eax
0x18000c472  jnz     short loc_18000C4B5
0x18000c474  call    cs:__imp_GetLastError
0x18000c47a  mov     ebx, eax
0x18000c47c  test    eax, eax
0x18000c47e  jle     short loc_18000C489
0x18000c480  movzx   ebx, ax
0x18000c483  or      ebx, 80070000h
0x18000c489  cmp     ebx, 800703F0h
0x18000c48f  jnz     loc_18000C682
0x18000c495  call    cs:__imp_GetCurrentProcess
0x18000c49b  mov     rcx, rax; ProcessHandle
0x18000c49e  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x18000c4a2  mov     edx, 8; DesiredAccess
0x18000c4a7  call    cs:__imp_OpenProcessToken
0x18000c4ad  test    eax, eax
0x18000c4af  jz      loc_18000C5AF
0x18000c4b5  mov     ebx, esi
0x18000c4b7  mov     rcx, [rbp+5Fh]; this
0x18000c4bb  test    ebx, ebx
0x18000c4bd  js      loc_18000C6A7
0x18000c4c3  call    cs:__imp_CoRevertToSelf
0x18000c4c9  mov     rbx, [rbp+57h+TokenHandle]
0x18000c4cd  xorps   xmm0, xmm0
0x18000c4d0  xor     eax, eax
0x18000c4d2  movups  [rbp+57h+SidToCheck], xmm0
0x18000c4d6  movups  [rbp+57h+var_70], xmm0
0x18000c4da  movups  [rbp+57h+var_60], xmm0
0x18000c4de  movups  [rbp+57h+var_50], xmm0
0x18000c4e2  mov     [rbp+57h+var_40], eax
0x18000c4e5  mov     [rbp+57h+cbSid], eax
0x18000c4e8  mov     [rbp+57h+var_88], 500h
0x18000c4ee  mov     [rbp+57h+IsMember], esi
0x18000c4f1  mov     r9d, 12h
0x18000c4f7  mov     r8d, 1
0x18000c4fd  lea     rdx, [rbp+57h+cbSid]
0x18000c501  lea     rcx, [rbp+57h+SidToCheck]
0x18000c505  call    cs:__imp_RtlInitializeSidEx
0x18000c50b  mov     rcx, [rbp+5Fh]; this
0x18000c50f  test    eax, eax
0x18000c511  js      loc_18000C6BC
0x18000c517  lea     r8, [rbp+57h+IsMember]; IsMember
0x18000c51b  lea     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x18000c51f  mov     rcx, rbx; TokenHandle
0x18000c522  call    cs:__imp_CheckTokenMembership
0x18000c528  test    eax, eax
0x18000c52a  jz      loc_18000C5CB
0x18000c530  cmp     [rbp+57h+IsMember], 0
0x18000c534  jz      short loc_18000C566
0x18000c536  mov     rbx, rsi
0x18000c539  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18000c53d  lea     rax, [rcx-1]
0x18000c541  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000c545  jbe     loc_18000C6F7
0x18000c54b  mov     rax, rbx
0x18000c54e  mov     rcx, [rbp+57h+var_28]
0x18000c552  xor     rcx, rsp; StackCookie
0x18000c555  call    __security_check_cookie
0x18000c55a  add     rsp, 0A8h
0x18000c561  pop     rdi
0x18000c562  pop     rsi
0x18000c563  pop     rbx
0x18000c564  pop     rbp
0x18000c565  retn
0x18000c566  mov     [rbp+57h+IsMember], esi
0x18000c569  xor     r8d, r8d
0x18000c56c  lea     rdx, [rbp+57h+IsMember]
0x18000c570  xor     ecx, ecx
0x18000c572  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18000c578  mov     eax, [rbp+57h+IsMember]
0x18000c57b  add     eax, 0FFFFFFF9h
0x18000c57e  cmp     eax, 1
0x18000c581  ja      loc_18000C6D3
0x18000c587  mov     dil, 1
0x18000c58a  call    cs:__imp_RtlIsMultiUsersInSessionSku
0x18000c590  test    al, al
0x18000c592  jnz     short loc_18000C60A
0x18000c594  test    dil, dil
0x18000c597  jnz     short loc_18000C60A
0x18000c599  call    IsUMgrQueryUserContextPresent
0x18000c59e  test    al, al
0x18000c5a0  jz      short loc_18000C536
0x18000c5a2  mov     rcx, rbx; void *
0x18000c5a5  call    ?GetUserIdForContext@@YA_KPEAX@Z; GetUserIdForContext(void *)
0x18000c5aa  mov     rbx, rax
0x18000c5ad  jmp     short loc_18000C539
0x18000c5af  mov     rcx, [rbp+5Fh]; this
0x18000c5b3  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000c5ba  mov     edx, 25h ; '%'; void *
0x18000c5bf  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c5c4  mov     ebx, eax
0x18000c5c6  jmp     loc_18000C4B7
0x18000c5cb  mov     rdi, [rbp+5Fh]
0x18000c5cf  call    cs:__imp_GetLastError
0x18000c5d5  cmp     eax, 51Dh
0x18000c5da  jnz     loc_18000C6C5
0x18000c5e0  mov     rdi, [rbp+5Fh]
0x18000c5e4  lea     r8, [rbp+57h+IsMember]; IsMember
0x18000c5e8  lea     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x18000c5ec  xor     ecx, ecx; TokenHandle
0x18000c5ee  call    cs:__imp_CheckTokenMembership
0x18000c5f4  test    eax, eax
0x18000c5f6  jnz     loc_18000C530
0x18000c5fc  mov     edx, 6Bh ; 'k'; void *
0x18000c601  mov     rcx, rdi; this
0x18000c604  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000c60a  mov     [rbp+57h+cbSid], 44h ; 'D'
0x18000c611  mov     [rbp+57h+var_90], esi
0x18000c614  mov     rdi, [rbp+5Fh]
0x18000c618  lea     r9, [rbp+57h+cbSid]; cbSid
0x18000c61c  lea     r8, [rbp+57h+SidToCheck]; pSid
0x18000c620  xor     edx, edx; DomainSid
0x18000c622  mov     ecx, 6Fh ; 'o'; WellKnownSidType
0x18000c627  call    cs:__imp_CreateWellKnownSid
0x18000c62d  test    eax, eax
0x18000c62f  jz      loc_18000C6DB
0x18000c635  mov     rdi, [rbp+5Fh]
0x18000c639  lea     r9, [rbp+57h+var_90]
0x18000c63d  xor     r8d, r8d
0x18000c640  lea     rdx, [rbp+57h+SidToCheck]
0x18000c644  mov     rcx, rbx
0x18000c647  call    cs:__imp_CheckTokenMembershipEx
0x18000c64d  test    eax, eax
0x18000c64f  jz      loc_18000C6E9
0x18000c655  cmp     [rbp+57h+var_90], 1
0x18000c659  jz      loc_18000C536
0x18000c65f  jmp     loc_18000C599
0x18000c664  call    cs:__imp_GetLastError
0x18000c66a  mov     ebx, eax
0x18000c66c  mov     rcx, rdi; hObject
0x18000c66f  call    cs:__imp_CloseHandle
0x18000c675  mov     ecx, ebx; dwErrCode
0x18000c677  call    cs:__imp_SetLastError
0x18000c67d  jmp     loc_18000C44E
0x18000c682  test    ebx, ebx
0x18000c684  jns     loc_18000C495
0x18000c68a  mov     rcx, [rbp+5Fh]; this
0x18000c68e  mov     r9d, ebx; char *
0x18000c691  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000c698  mov     edx, 1Fh; void *
0x18000c69d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c6a2  jmp     loc_18000C4B7
0x18000c6a7  mov     r9d, ebx; char *
0x18000c6aa  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000c6b1  mov     edx, 47h ; 'G'; void *
0x18000c6b6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000c6bc  mov     r9d, eax; char *
0x18000c6bf  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18000c6c5  mov     edx, 69h ; 'i'; void *
0x18000c6ca  mov     rcx, rdi; this
0x18000c6cd  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000c6d3  xor     dil, dil
0x18000c6d6  jmp     loc_18000C58A
0x18000c6db  mov     edx, 93h; void *
0x18000c6e0  mov     rcx, rdi; this
0x18000c6e3  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000c6e9  mov     edx, 95h; void *
0x18000c6ee  mov     rcx, rdi; this
0x18000c6f1  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000c6f7  call    cs:__imp_CloseHandle
0x18000c6fd  jmp     loc_18000C54B
```
