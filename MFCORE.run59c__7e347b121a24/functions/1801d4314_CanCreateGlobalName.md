# CanCreateGlobalName

- ea: `0x1801d4314`
- end: `0x1801d4605`
- name: `CanCreateGlobalName`
- size: `753`
- prototype: `__int64 __fastcall(LPBOOL pfResult)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800b7a98`

## callees

- `0x1800402c0`
- `0x1800ec0e0`
- `0x1801d4314`
- `0x180258480`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801d4391`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801d444b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801d451a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801d4391`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801d444b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801d451a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1801d437d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1801d437d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801d4365`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801d4365`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801d45da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801d45da`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x1801d4506`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x1801d4506`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x1801d4437`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x1801d4437`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801d43bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801d4476`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801d4549`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801d43bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801d4476`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801d4549`

## string_xrefs

- `0x1801d45ad`: `CanCreateGlobalName`
- `0x1801d4430`: `SeCreateGlobalPrivilege`

## pseudocode

```c
__int64 __fastcall CanCreateGlobalName(LPBOOL pfResult)
{
  signed int v1; // ebx
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 *v7; // rcx
  CallStackTracing *v8; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  int v10; // r8d
  signed int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  signed int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  void *TokenHandle; // [rsp+20h] [rbp-30h] BYREF
  _LUID Luid; // [rsp+28h] [rbp-28h] BYREF
  _PRIVILEGE_SET RequiredPrivileges; // [rsp+30h] [rbp-20h] BYREF

  v1 = 0;
  TokenHandle = 0;
  Luid = 0;
  memset(&RequiredPrivileges, 0, sizeof(RequiredPrivileges));
  if ( dword_1803CCE30 != -1 )
  {
    *pfResult = dword_1803CCE30;
    goto LABEL_43;
  }
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
    if ( v1 < 0 )
    {
      v7 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v5, v6);
        CallStackTracing::s_wpInstance = v8;
        if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
        {
          v7 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v7 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( !*((_BYTE *)v7 + 8) )
        goto LABEL_40;
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( *((_DWORD *)ThreadRelativeContext + 499) == v1 )
        goto LABEL_40;
      v10 = 43;
      goto LABEL_39;
    }
  }
  if ( !LookupPrivilegeValueW(0, L"SeCreateGlobalPrivilege", &Luid) )
  {
    v11 = GetLastError();
    v1 = v11;
    if ( v11 > 0 )
      v1 = (unsigned __int16)v11 | 0x80070000;
    if ( v1 < 0 )
    {
      v14 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13);
        CallStackTracing::s_wpInstance = v15;
        if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
        {
          v14 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v14 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( !*((_BYTE *)v14 + 8) )
        goto LABEL_40;
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
      if ( *((_DWORD *)ThreadRelativeContext + 499) == v1 )
        goto LABEL_40;
      v10 = 48;
      goto LABEL_39;
    }
  }
  RequiredPrivileges.Privilege[0].Luid = Luid;
  *(_QWORD *)&RequiredPrivileges.PrivilegeCount = 1;
  RequiredPrivileges.Privilege[0].Attributes = 0;
  if ( PrivilegeCheck(TokenHandle, &RequiredPrivileges, pfResult) )
    goto LABEL_42;
  v16 = GetLastError();
  v1 = v16;
  if ( v16 > 0 )
    v1 = (unsigned __int16)v16 | 0x80070000;
  if ( v1 >= 0 )
  {
LABEL_42:
    dword_1803CCE30 = *pfResult;
    goto LABEL_43;
  }
  v19 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17, v18);
    CallStackTracing::s_wpInstance = v20;
    if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
    {
      v19 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v19 = &qword_1803CE250;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
    }
  }
  if ( *((_BYTE *)v19 + 8) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
    if ( *((_DWORD *)ThreadRelativeContext + 499) != v1 )
    {
      v10 = 58;
LABEL_39:
      CallStackContext::TraceFailure(ThreadRelativeContext, "CanCreateGlobalName", v10, v1);
    }
  }
LABEL_40:
  if ( pfResult )
    *pfResult = 0;
LABEL_43:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x1801d4314  mov     [rsp-8+arg_8], rbx
0x1801d4319  mov     [rsp-8+arg_10], rdi
0x1801d431e  push    rbp
0x1801d431f  mov     rbp, rsp
0x1801d4322  sub     rsp, 50h
0x1801d4326  mov     rax, cs:__security_cookie
0x1801d432d  xor     rax, rsp
0x1801d4330  mov     [rbp+var_8], rax
0x1801d4334  xor     eax, eax
0x1801d4336  xor     ebx, ebx
0x1801d4338  mov     [rbp+RequiredPrivileges.Privilege.Attributes], eax
0x1801d433b  xorps   xmm0, xmm0
0x1801d433e  mov     eax, cs:dword_1803CCE30
0x1801d4344  mov     rdi, rcx
0x1801d4347  mov     [rbp+TokenHandle], rbx
0x1801d434b  mov     qword ptr [rbp+Luid.LowPart], rbx
0x1801d434f  movups  xmmword ptr [rbp+RequiredPrivileges.PrivilegeCount], xmm0
0x1801d4353  cmp     eax, 0FFFFFFFFh
0x1801d4356  jz      short loc_1801D4365
0x1801d4358  mov     eax, cs:dword_1803CCE30
0x1801d435e  mov     [rcx], eax
0x1801d4360  jmp     loc_1801D45D1
0x1801d4365  call    cs:__imp_GetCurrentProcess
0x1801d436c  nop     dword ptr [rax+rax+00h]
0x1801d4371  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1801d4375  mov     edx, 8; DesiredAccess
0x1801d437a  mov     rcx, rax; ProcessHandle
0x1801d437d  call    cs:__imp_OpenProcessToken
0x1801d4384  nop     dword ptr [rax+rax+00h]
0x1801d4389  test    eax, eax
0x1801d438b  jnz     loc_1801D442A
0x1801d4391  call    cs:__imp_GetLastError
0x1801d4398  nop     dword ptr [rax+rax+00h]
0x1801d439d  mov     ebx, eax
0x1801d439f  test    eax, eax
0x1801d43a1  jle     short loc_1801D43AC
0x1801d43a3  movzx   ebx, ax
0x1801d43a6  or      ebx, 80070000h
0x1801d43ac  test    ebx, ebx
0x1801d43ae  jns     short loc_1801D442A
0x1801d43b0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801d43b7  test    rcx, rcx
0x1801d43ba  jnz     short loc_1801D4404
0x1801d43bc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801d43c3  nop     dword ptr [rax+rax+00h]
0x1801d43c8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801d43cf  mov     rcx, rax
0x1801d43d2  test    rax, rax
0x1801d43d5  jz      short loc_1801D43F6
0x1801d43d7  mov     rax, [rax]
0x1801d43da  mov     edx, 7F0h
0x1801d43df  mov     rax, [rax+8]
0x1801d43e3  call    cs:__guard_dispatch_icall_fptr
0x1801d43e9  test    eax, eax
0x1801d43eb  jz      short loc_1801D43F6
0x1801d43ed  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801d43f4  jmp     short loc_1801D4404
0x1801d43f6  lea     rcx, qword_1803CE250; this
0x1801d43fd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801d4404  cmp     byte ptr [rcx+8], 0
0x1801d4408  jz      loc_1801D45BC
0x1801d440e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801d4413  cmp     [rax+7CCh], ebx
0x1801d4419  jz      loc_1801D45BC
0x1801d441f  mov     r8d, 2Bh ; '+'
0x1801d4425  jmp     loc_1801D45AA
0x1801d442a  lea     r8, [rbp+Luid]; lpLuid
0x1801d442e  xor     ecx, ecx; lpSystemName
0x1801d4430  lea     rdx, aSecreateglobal; "SeCreateGlobalPrivilege"
0x1801d4437  call    cs:__imp_LookupPrivilegeValueW
0x1801d443e  nop     dword ptr [rax+rax+00h]
0x1801d4443  test    eax, eax
0x1801d4445  jnz     loc_1801D44E4
0x1801d444b  call    cs:__imp_GetLastError
0x1801d4452  nop     dword ptr [rax+rax+00h]
0x1801d4457  mov     ebx, eax
0x1801d4459  test    eax, eax
0x1801d445b  jle     short loc_1801D4466
0x1801d445d  movzx   ebx, ax
0x1801d4460  or      ebx, 80070000h
0x1801d4466  test    ebx, ebx
0x1801d4468  jns     short loc_1801D44E4
0x1801d446a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801d4471  test    rcx, rcx
0x1801d4474  jnz     short loc_1801D44BE
0x1801d4476  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801d447d  nop     dword ptr [rax+rax+00h]
0x1801d4482  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801d4489  mov     rcx, rax
0x1801d448c  test    rax, rax
0x1801d448f  jz      short loc_1801D44B0
0x1801d4491  mov     rax, [rax]
0x1801d4494  mov     edx, 7F0h
0x1801d4499  mov     rax, [rax+8]
0x1801d449d  call    cs:__guard_dispatch_icall_fptr
0x1801d44a3  test    eax, eax
0x1801d44a5  jz      short loc_1801D44B0
0x1801d44a7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801d44ae  jmp     short loc_1801D44BE
0x1801d44b0  lea     rcx, qword_1803CE250; this
0x1801d44b7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801d44be  cmp     byte ptr [rcx+8], 0
0x1801d44c2  jz      loc_1801D45BC
0x1801d44c8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801d44cd  cmp     [rax+7CCh], ebx
0x1801d44d3  jz      loc_1801D45BC
0x1801d44d9  mov     r8d, 30h ; '0'
0x1801d44df  jmp     loc_1801D45AA
0x1801d44e4  mov     rax, qword ptr [rbp+Luid.LowPart]
0x1801d44e8  lea     rdx, [rbp+RequiredPrivileges]; RequiredPrivileges
0x1801d44ec  mov     rcx, [rbp+TokenHandle]; ClientToken
0x1801d44f0  mov     r8, rdi; pfResult
0x1801d44f3  mov     qword ptr [rbp+RequiredPrivileges.Privilege.Luid.LowPart], rax
0x1801d44f7  mov     qword ptr [rbp+RequiredPrivileges.PrivilegeCount], 1
0x1801d44ff  mov     [rbp+RequiredPrivileges.Privilege.Attributes], 0
0x1801d4506  call    cs:__imp_PrivilegeCheck
0x1801d450d  nop     dword ptr [rax+rax+00h]
0x1801d4512  test    eax, eax
0x1801d4514  jnz     loc_1801D45C9
0x1801d451a  call    cs:__imp_GetLastError
0x1801d4521  nop     dword ptr [rax+rax+00h]
0x1801d4526  mov     ebx, eax
0x1801d4528  test    eax, eax
0x1801d452a  jle     short loc_1801D4535
0x1801d452c  movzx   ebx, ax
0x1801d452f  or      ebx, 80070000h
0x1801d4535  test    ebx, ebx
0x1801d4537  jns     loc_1801D45C9
0x1801d453d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801d4544  test    rcx, rcx
0x1801d4547  jnz     short loc_1801D4591
0x1801d4549  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801d4550  nop     dword ptr [rax+rax+00h]
0x1801d4555  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801d455c  mov     rcx, rax
0x1801d455f  test    rax, rax
0x1801d4562  jz      short loc_1801D4583
0x1801d4564  mov     rax, [rax]
0x1801d4567  mov     edx, 7F0h
0x1801d456c  mov     rax, [rax+8]
0x1801d4570  call    cs:__guard_dispatch_icall_fptr
0x1801d4576  test    eax, eax
0x1801d4578  jz      short loc_1801D4583
0x1801d457a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801d4581  jmp     short loc_1801D4591
0x1801d4583  lea     rcx, qword_1803CE250; this
0x1801d458a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801d4591  cmp     byte ptr [rcx+8], 0
0x1801d4595  jz      short loc_1801D45BC
0x1801d4597  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801d459c  cmp     [rax+7CCh], ebx
0x1801d45a2  jz      short loc_1801D45BC
0x1801d45a4  mov     r8d, 3Ah ; ':'; int
0x1801d45aa  mov     r9d, ebx; int
0x1801d45ad  lea     rdx, aCancreategloba; "CanCreateGlobalName"
0x1801d45b4  mov     rcx, rax; this
0x1801d45b7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801d45bc  test    rdi, rdi
0x1801d45bf  jz      short loc_1801D45D1
0x1801d45c1  mov     dword ptr [rdi], 0
0x1801d45c7  jmp     short loc_1801D45D1
0x1801d45c9  mov     ecx, [rdi]
0x1801d45cb  mov     cs:dword_1803CCE30, ecx
0x1801d45d1  mov     rcx, [rbp+TokenHandle]; hObject
0x1801d45d5  test    rcx, rcx
0x1801d45d8  jz      short loc_1801D45E6
0x1801d45da  call    cs:__imp_CloseHandle
0x1801d45e1  nop     dword ptr [rax+rax+00h]
0x1801d45e6  mov     eax, ebx
0x1801d45e8  mov     rcx, [rbp+var_8]
0x1801d45ec  xor     rcx, rsp; StackCookie
0x1801d45ef  call    __security_check_cookie
0x1801d45f4  mov     rbx, [rsp+50h+arg_8]
0x1801d45f9  mov     rdi, [rsp+50h+arg_10]
0x1801d45fe  add     rsp, 50h
0x1801d4602  pop     rbp
0x1801d4603  retn
```
