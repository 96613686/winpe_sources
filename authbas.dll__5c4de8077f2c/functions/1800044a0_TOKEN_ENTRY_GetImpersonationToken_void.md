# TOKEN_ENTRY::GetImpersonationToken(void)

- ea: `0x1800044a0`
- end: `0x1800046c7`
- name: `?GetImpersonationToken@TOKEN_ENTRY@@UEAAPEAXXZ`
- size: `551`
- prototype: `void *__fastcall(TOKEN_ENTRY *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800044a0`
- `0x180005b30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004544`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004596`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004636`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004544`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004596`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004636`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000467d`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000467d`
- `iisutil!PuDbgPrint` at `0x1800045c7`
- `iisutil!PuDbgPrint` at `0x180004667`
- `iisutil!PuDbgPrint` at `0x1800045c7`
- `iisutil!PuDbgPrint` at `0x180004667`
- `iisutil!DisableTokenBackupPrivilege` at `0x1800046a2`
- `iisutil!DisableTokenBackupPrivilege` at `0x1800046a2`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180004556`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180004556`
- `iisutil!?WriteUnlock@CSmallSpinLock@@QEAAXXZ` at `0x180004686`
- `iisutil!?WriteUnlock@CSmallSpinLock@@QEAAXXZ` at `0x180004686`
- `iisutil!?WriteLock@CSmallSpinLock@@QEAAXXZ` at `0x1800044e3`
- `iisutil!?WriteLock@CSmallSpinLock@@QEAAXXZ` at `0x1800044e3`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180004602`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180004623`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180004602`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180004623`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180004536`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x18000457f`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180004536`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x18000457f`

## string_xrefs

- `0x1800045ae`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`
- `0x18000464e`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`
- `0x1800045b5`: `Failed to get primary token security descriptor, GetLastError = %lx\n`
- `0x1800045a3`: `TOKEN_ENTRY::GetImpersonationToken`
- `0x180004643`: `TOKEN_ENTRY::GetImpersonationToken`
- `0x180004655`: `DuplicateTokenEx failed, GetLastError = %lx\n`

## pseudocode

```c
void *__fastcall TOKEN_ENTRY::GetImpersonationToken(TOKEN_ENTRY *this)
{
  void **phNewToken; // rdi
  CSmallSpinLock *v3; // r15
  void *v4; // rcx
  _QWORD *v5; // r14
  DWORD LastError; // eax
  void *v7; // rcx
  DWORD v8; // eax
  DWORD nLengthNeeded; // [rsp+30h] [rbp-39h] BYREF
  _SECURITY_ATTRIBUTES TokenAttributes; // [rsp+38h] [rbp-31h] BYREF
  _QWORD pSecurityDescriptor[4]; // [rsp+50h] [rbp-19h] BYREF
  PSECURITY_DESCRIPTOR v13; // [rsp+70h] [rbp+7h]
  int v14; // [rsp+78h] [rbp+Fh]
  __int16 v15; // [rsp+7Ch] [rbp+13h]

  phNewToken = (void **)((char *)this + 16);
  if ( !*((_QWORD *)this + 2) )
  {
    v3 = (TOKEN_ENTRY *)((char *)this + 248);
    CSmallSpinLock::WriteLock((TOKEN_ENTRY *)((char *)this + 248));
    if ( *phNewToken )
      goto LABEL_17;
    v4 = (void *)*((_QWORD *)this + 3);
    pSecurityDescriptor[0] = 0;
    v13 = pSecurityDescriptor;
    v14 = 32;
    v15 = 256;
    nLengthNeeded = 32;
    memset(&TokenAttributes, 0, sizeof(TokenAttributes));
    if ( GetKernelObjectSecurity(v4, 4u, pSecurityDescriptor, 0x20u, &nLengthNeeded) )
    {
      v5 = pSecurityDescriptor;
    }
    else
    {
      if ( GetLastError() != 122 )
        goto LABEL_7;
      if ( !BUFFER::Resize((BUFFER *)pSecurityDescriptor, nLengthNeeded) )
      {
LABEL_16:
        BUFFER::~BUFFER((BUFFER *)pSecurityDescriptor);
LABEL_17:
        CSmallSpinLock::WriteUnlock(v3);
        if ( !*phNewToken )
          return *phNewToken;
        goto LABEL_18;
      }
      v5 = v13;
      if ( !GetKernelObjectSecurity(*((HANDLE *)this + 3), 4u, v13, nLengthNeeded, &nLengthNeeded) )
      {
LABEL_7:
        if ( (g_dwDebugFlags & 3) != 0 )
        {
          LastError = GetLastError();
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\common\\iislogon_lib\\iislogon.cxx",
            1095,
            "TOKEN_ENTRY::GetImpersonationToken",
            "Failed to get primary token security descriptor, GetLastError = %lx\n",
            LastError);
        }
        goto LABEL_16;
      }
    }
    v7 = (void *)*((_QWORD *)this + 3);
    TokenAttributes.lpSecurityDescriptor = v5;
    TokenAttributes.nLength = 24;
    TokenAttributes.bInheritHandle = 1;
    if ( !DuplicateTokenEx(v7, 0, &TokenAttributes, SecurityDelegation, TokenImpersonation, phNewToken)
      && !DuplicateTokenEx(
            *((HANDLE *)this + 3),
            0,
            &TokenAttributes,
            SecurityImpersonation,
            TokenImpersonation,
            phNewToken)
      && (g_dwDebugFlags & 3) != 0 )
    {
      v8 = GetLastError();
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\common\\iislogon_lib\\iislogon.cxx",
        1124,
        "TOKEN_ENTRY::GetImpersonationToken",
        "DuplicateTokenEx failed, GetLastError = %lx\n",
        v8);
    }
    if ( *phNewToken )
      *((_DWORD *)this + 65) |= 1u;
    goto LABEL_16;
  }
LABEL_18:
  if ( !*((_DWORD *)this + 29) && !_InterlockedExchange((volatile __int32 *)this + 29, 1) )
    DisableTokenBackupPrivilege(*phNewToken);
  return *phNewToken;
}

```

## disassembly

```asm
0x1800044a0  push    rbp
0x1800044a2  push    rbx
0x1800044a3  push    rsi
0x1800044a4  push    rdi
0x1800044a5  push    r14
0x1800044a7  push    r15
0x1800044a9  lea     rbp, [rsp-2Fh]
0x1800044ae  sub     rsp, 98h
0x1800044b5  mov     rax, cs:__security_cookie
0x1800044bc  xor     rax, rsp
0x1800044bf  mov     [rbp+57h+var_40], rax
0x1800044c3  lea     rdi, [rcx+10h]
0x1800044c7  mov     rbx, rcx
0x1800044ca  cmp     qword ptr [rdi], 0
0x1800044ce  mov     esi, 1
0x1800044d3  jnz     loc_180004692
0x1800044d9  lea     r15, [rcx+0F8h]
0x1800044e0  mov     rcx, r15
0x1800044e3  call    cs:__imp_?WriteLock@CSmallSpinLock@@QEAAXXZ; CSmallSpinLock::WriteLock(void)
0x1800044e9  cmp     qword ptr [rdi], 0
0x1800044ed  jnz     loc_180004683
0x1800044f3  mov     rcx, [rbx+18h]; Handle
0x1800044f7  lea     r9d, [rsi+1Fh]; nLength
0x1800044fb  lea     rax, [rbp+57h+pSecurityDescriptor]
0x1800044ff  mov     [rbp+57h+pSecurityDescriptor], 0
0x180004507  mov     [rbp+57h+var_50], rax
0x18000450b  lea     r8, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18000450f  xor     eax, eax
0x180004511  mov     [rbp+57h+var_48], r9d
0x180004515  mov     qword ptr [rbp+57h+TokenAttributes.bInheritHandle], rax
0x180004519  lea     edx, [rsi+3]; RequestedInformation
0x18000451c  lea     rax, [rbp+57h+nLengthNeeded]
0x180004520  mov     [rbp+57h+var_44], 100h
0x180004526  xorps   xmm0, xmm0
0x180004529  mov     [rsp+0C0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18000452e  mov     [rbp+57h+nLengthNeeded], r9d
0x180004532  movups  xmmword ptr [rbp+57h+TokenAttributes.nLength], xmm0
0x180004536  call    cs:__imp_GetKernelObjectSecurity
0x18000453c  test    eax, eax
0x18000453e  jnz     loc_1800045D2
0x180004544  call    cs:__imp_GetLastError
0x18000454a  cmp     eax, 7Ah ; 'z'
0x18000454d  jnz     short loc_180004589
0x18000454f  mov     edx, [rbp+57h+nLengthNeeded]
0x180004552  lea     rcx, [rbp+57h+pSecurityDescriptor]
0x180004556  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18000455c  test    al, al
0x18000455e  jz      loc_180004679
0x180004564  mov     r14, [rbp+57h+var_50]
0x180004568  lea     rax, [rbp+57h+nLengthNeeded]
0x18000456c  mov     r9d, [rbp+57h+nLengthNeeded]; nLength
0x180004570  lea     edx, [rsi+3]; RequestedInformation
0x180004573  mov     rcx, [rbx+18h]; Handle
0x180004577  mov     r8, r14; pSecurityDescriptor
0x18000457a  mov     [rsp+0C0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18000457f  call    cs:__imp_GetKernelObjectSecurity
0x180004585  test    eax, eax
0x180004587  jnz     short loc_1800045D6
0x180004589  test    byte ptr cs:g_dwDebugFlags, 3
0x180004590  jz      loc_180004679
0x180004596  call    cs:__imp_GetLastError
0x18000459c  mov     rcx, cs:g_pDebug
0x1800045a3  lea     r9, aTokenEntryGeti; "TOKEN_ENTRY::GetImpersonationToken"
0x1800045aa  mov     dword ptr [rsp+0C0h+phNewToken], eax
0x1800045ae  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800045b5  lea     rax, aFailedToGetPri; "Failed to get primary token security de"...
0x1800045bc  mov     r8d, 447h
0x1800045c2  mov     [rsp+0C0h+lpnLengthNeeded], rax
0x1800045c7  call    cs:__imp_PuDbgPrint
0x1800045cd  jmp     loc_180004679
0x1800045d2  lea     r14, [rbp+57h+pSecurityDescriptor]
0x1800045d6  mov     rcx, [rbx+18h]; hExistingToken
0x1800045da  lea     r8, [rbp+57h+TokenAttributes]; lpTokenAttributes
0x1800045de  mov     [rbp+57h+TokenAttributes.lpSecurityDescriptor], r14
0x1800045e2  xor     edx, edx; dwDesiredAccess
0x1800045e4  mov     r14d, 2
0x1800045ea  mov     [rsp+0C0h+phNewToken], rdi; phNewToken
0x1800045ef  mov     [rbp+57h+TokenAttributes.nLength], 18h
0x1800045f6  mov     [rbp+57h+TokenAttributes.bInheritHandle], esi
0x1800045f9  mov     dword ptr [rsp+0C0h+lpnLengthNeeded], r14d; TokenType
0x1800045fe  lea     r9d, [r14+1]; ImpersonationLevel
0x180004602  call    cs:__imp_DuplicateTokenEx
0x180004608  test    eax, eax
0x18000460a  jnz     short loc_18000466D
0x18000460c  mov     rcx, [rbx+18h]; hExistingToken
0x180004610  lea     r8, [rbp+57h+TokenAttributes]; lpTokenAttributes
0x180004614  mov     [rsp+0C0h+phNewToken], rdi; phNewToken
0x180004619  mov     r9d, r14d; ImpersonationLevel
0x18000461c  xor     edx, edx; dwDesiredAccess
0x18000461e  mov     dword ptr [rsp+0C0h+lpnLengthNeeded], r14d; TokenType
0x180004623  call    cs:__imp_DuplicateTokenEx
0x180004629  test    eax, eax
0x18000462b  jnz     short loc_18000466D
0x18000462d  test    byte ptr cs:g_dwDebugFlags, 3
0x180004634  jz      short loc_18000466D
0x180004636  call    cs:__imp_GetLastError
0x18000463c  mov     rcx, cs:g_pDebug
0x180004643  lea     r9, aTokenEntryGeti; "TOKEN_ENTRY::GetImpersonationToken"
0x18000464a  mov     dword ptr [rsp+0C0h+phNewToken], eax
0x18000464e  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180004655  lea     rax, aDuplicatetoken; "DuplicateTokenEx failed, GetLastError ="...
0x18000465c  mov     r8d, 464h
0x180004662  mov     [rsp+0C0h+lpnLengthNeeded], rax
0x180004667  call    cs:__imp_PuDbgPrint
0x18000466d  cmp     qword ptr [rdi], 0
0x180004671  jz      short loc_180004679
0x180004673  or      [rbx+104h], esi
0x180004679  lea     rcx, [rbp+57h+pSecurityDescriptor]
0x18000467d  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180004683  mov     rcx, r15
0x180004686  call    cs:__imp_?WriteUnlock@CSmallSpinLock@@QEAAXXZ; CSmallSpinLock::WriteUnlock(void)
0x18000468c  cmp     qword ptr [rdi], 0
0x180004690  jz      short loc_1800046A8
0x180004692  cmp     dword ptr [rbx+74h], 0
0x180004696  jnz     short loc_1800046A8
0x180004698  xchg    esi, [rbx+74h]
0x18000469b  test    esi, esi
0x18000469d  jnz     short loc_1800046A8
0x18000469f  mov     rcx, [rdi]
0x1800046a2  call    cs:__imp_?DisableTokenBackupPrivilege@@YAXPEAX@Z; DisableTokenBackupPrivilege(void *)
0x1800046a8  mov     rax, [rdi]
0x1800046ab  mov     rcx, [rbp+57h+var_40]
0x1800046af  xor     rcx, rsp; StackCookie
0x1800046b2  call    __security_check_cookie
0x1800046b7  add     rsp, 98h
0x1800046be  pop     r15
0x1800046c0  pop     r14
0x1800046c2  pop     rdi
0x1800046c3  pop     rsi
0x1800046c4  pop     rbx
0x1800046c5  pop     rbp
0x1800046c6  retn
```
