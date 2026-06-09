# TOKEN_ENTRY::GetImpersonationToken(void)

- ea: `0x180005730`
- end: `0x180005957`
- name: `?GetImpersonationToken@TOKEN_ENTRY@@UEAAPEAXXZ`
- size: `551`
- prototype: `void *__fastcall(TOKEN_ENTRY *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180005730`
- `0x180006dd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800057d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005826`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800058c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800057d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005826`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800058c6`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000590d`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000590d`
- `iisutil!PuDbgPrint` at `0x180005857`
- `iisutil!PuDbgPrint` at `0x1800058f7`
- `iisutil!PuDbgPrint` at `0x180005857`
- `iisutil!PuDbgPrint` at `0x1800058f7`
- `iisutil!DisableTokenBackupPrivilege` at `0x180005932`
- `iisutil!DisableTokenBackupPrivilege` at `0x180005932`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800057e6`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800057e6`
- `iisutil!?WriteUnlock@CSmallSpinLock@@QEAAXXZ` at `0x180005916`
- `iisutil!?WriteUnlock@CSmallSpinLock@@QEAAXXZ` at `0x180005916`
- `iisutil!?WriteLock@CSmallSpinLock@@QEAAXXZ` at `0x180005773`
- `iisutil!?WriteLock@CSmallSpinLock@@QEAAXXZ` at `0x180005773`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x1800057c6`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x18000580f`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x1800057c6`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x18000580f`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180005892`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800058b3`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180005892`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800058b3`

## string_xrefs

- `0x18000583e`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`
- `0x1800058de`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`
- `0x180005845`: `Failed to get primary token security descriptor, GetLastError = %lx\n`
- `0x180005833`: `TOKEN_ENTRY::GetImpersonationToken`
- `0x1800058d3`: `TOKEN_ENTRY::GetImpersonationToken`
- `0x1800058e5`: `DuplicateTokenEx failed, GetLastError = %lx\n`

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
0x180005730  push    rbp
0x180005732  push    rbx
0x180005733  push    rsi
0x180005734  push    rdi
0x180005735  push    r14
0x180005737  push    r15
0x180005739  lea     rbp, [rsp-2Fh]
0x18000573e  sub     rsp, 98h
0x180005745  mov     rax, cs:__security_cookie
0x18000574c  xor     rax, rsp
0x18000574f  mov     [rbp+57h+var_40], rax
0x180005753  lea     rdi, [rcx+10h]
0x180005757  mov     rbx, rcx
0x18000575a  cmp     qword ptr [rdi], 0
0x18000575e  mov     esi, 1
0x180005763  jnz     loc_180005922
0x180005769  lea     r15, [rcx+0F8h]
0x180005770  mov     rcx, r15
0x180005773  call    cs:__imp_?WriteLock@CSmallSpinLock@@QEAAXXZ; CSmallSpinLock::WriteLock(void)
0x180005779  cmp     qword ptr [rdi], 0
0x18000577d  jnz     loc_180005913
0x180005783  mov     rcx, [rbx+18h]; Handle
0x180005787  lea     r9d, [rsi+1Fh]; nLength
0x18000578b  lea     rax, [rbp+57h+pSecurityDescriptor]
0x18000578f  mov     [rbp+57h+pSecurityDescriptor], 0
0x180005797  mov     [rbp+57h+var_50], rax
0x18000579b  lea     r8, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18000579f  xor     eax, eax
0x1800057a1  mov     [rbp+57h+var_48], r9d
0x1800057a5  mov     qword ptr [rbp+57h+TokenAttributes.bInheritHandle], rax
0x1800057a9  lea     edx, [rsi+3]; RequestedInformation
0x1800057ac  lea     rax, [rbp+57h+nLengthNeeded]
0x1800057b0  mov     [rbp+57h+var_44], 100h
0x1800057b6  xorps   xmm0, xmm0
0x1800057b9  mov     [rsp+0C0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x1800057be  mov     [rbp+57h+nLengthNeeded], r9d
0x1800057c2  movups  xmmword ptr [rbp+57h+TokenAttributes.nLength], xmm0
0x1800057c6  call    cs:__imp_GetKernelObjectSecurity
0x1800057cc  test    eax, eax
0x1800057ce  jnz     loc_180005862
0x1800057d4  call    cs:__imp_GetLastError
0x1800057da  cmp     eax, 7Ah ; 'z'
0x1800057dd  jnz     short loc_180005819
0x1800057df  mov     edx, [rbp+57h+nLengthNeeded]
0x1800057e2  lea     rcx, [rbp+57h+pSecurityDescriptor]
0x1800057e6  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800057ec  test    al, al
0x1800057ee  jz      loc_180005909
0x1800057f4  mov     r14, [rbp+57h+var_50]
0x1800057f8  lea     rax, [rbp+57h+nLengthNeeded]
0x1800057fc  mov     r9d, [rbp+57h+nLengthNeeded]; nLength
0x180005800  lea     edx, [rsi+3]; RequestedInformation
0x180005803  mov     rcx, [rbx+18h]; Handle
0x180005807  mov     r8, r14; pSecurityDescriptor
0x18000580a  mov     [rsp+0C0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18000580f  call    cs:__imp_GetKernelObjectSecurity
0x180005815  test    eax, eax
0x180005817  jnz     short loc_180005866
0x180005819  test    byte ptr cs:g_dwDebugFlags, 3
0x180005820  jz      loc_180005909
0x180005826  call    cs:__imp_GetLastError
0x18000582c  mov     rcx, cs:g_pDebug
0x180005833  lea     r9, aTokenEntryGeti; "TOKEN_ENTRY::GetImpersonationToken"
0x18000583a  mov     dword ptr [rsp+0C0h+phNewToken], eax
0x18000583e  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180005845  lea     rax, aFailedToGetPri; "Failed to get primary token security de"...
0x18000584c  mov     r8d, 447h
0x180005852  mov     [rsp+0C0h+lpnLengthNeeded], rax
0x180005857  call    cs:__imp_PuDbgPrint
0x18000585d  jmp     loc_180005909
0x180005862  lea     r14, [rbp+57h+pSecurityDescriptor]
0x180005866  mov     rcx, [rbx+18h]; hExistingToken
0x18000586a  lea     r8, [rbp+57h+TokenAttributes]; lpTokenAttributes
0x18000586e  mov     [rbp+57h+TokenAttributes.lpSecurityDescriptor], r14
0x180005872  xor     edx, edx; dwDesiredAccess
0x180005874  mov     r14d, 2
0x18000587a  mov     [rsp+0C0h+phNewToken], rdi; phNewToken
0x18000587f  mov     [rbp+57h+TokenAttributes.nLength], 18h
0x180005886  mov     [rbp+57h+TokenAttributes.bInheritHandle], esi
0x180005889  mov     dword ptr [rsp+0C0h+lpnLengthNeeded], r14d; TokenType
0x18000588e  lea     r9d, [r14+1]; ImpersonationLevel
0x180005892  call    cs:__imp_DuplicateTokenEx
0x180005898  test    eax, eax
0x18000589a  jnz     short loc_1800058FD
0x18000589c  mov     rcx, [rbx+18h]; hExistingToken
0x1800058a0  lea     r8, [rbp+57h+TokenAttributes]; lpTokenAttributes
0x1800058a4  mov     [rsp+0C0h+phNewToken], rdi; phNewToken
0x1800058a9  mov     r9d, r14d; ImpersonationLevel
0x1800058ac  xor     edx, edx; dwDesiredAccess
0x1800058ae  mov     dword ptr [rsp+0C0h+lpnLengthNeeded], r14d; TokenType
0x1800058b3  call    cs:__imp_DuplicateTokenEx
0x1800058b9  test    eax, eax
0x1800058bb  jnz     short loc_1800058FD
0x1800058bd  test    byte ptr cs:g_dwDebugFlags, 3
0x1800058c4  jz      short loc_1800058FD
0x1800058c6  call    cs:__imp_GetLastError
0x1800058cc  mov     rcx, cs:g_pDebug
0x1800058d3  lea     r9, aTokenEntryGeti; "TOKEN_ENTRY::GetImpersonationToken"
0x1800058da  mov     dword ptr [rsp+0C0h+phNewToken], eax
0x1800058de  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800058e5  lea     rax, aDuplicatetoken; "DuplicateTokenEx failed, GetLastError ="...
0x1800058ec  mov     r8d, 464h
0x1800058f2  mov     [rsp+0C0h+lpnLengthNeeded], rax
0x1800058f7  call    cs:__imp_PuDbgPrint
0x1800058fd  cmp     qword ptr [rdi], 0
0x180005901  jz      short loc_180005909
0x180005903  or      [rbx+104h], esi
0x180005909  lea     rcx, [rbp+57h+pSecurityDescriptor]
0x18000590d  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180005913  mov     rcx, r15
0x180005916  call    cs:__imp_?WriteUnlock@CSmallSpinLock@@QEAAXXZ; CSmallSpinLock::WriteUnlock(void)
0x18000591c  cmp     qword ptr [rdi], 0
0x180005920  jz      short loc_180005938
0x180005922  cmp     dword ptr [rbx+74h], 0
0x180005926  jnz     short loc_180005938
0x180005928  xchg    esi, [rbx+74h]
0x18000592b  test    esi, esi
0x18000592d  jnz     short loc_180005938
0x18000592f  mov     rcx, [rdi]
0x180005932  call    cs:__imp_?DisableTokenBackupPrivilege@@YAXPEAX@Z; DisableTokenBackupPrivilege(void *)
0x180005938  mov     rax, [rdi]
0x18000593b  mov     rcx, [rbp+57h+var_40]
0x18000593f  xor     rcx, rsp; StackCookie
0x180005942  call    __security_check_cookie
0x180005947  add     rsp, 98h
0x18000594e  pop     r15
0x180005950  pop     r14
0x180005952  pop     rdi
0x180005953  pop     rsi
0x180005954  pop     rbx
0x180005955  pop     rbp
0x180005956  retn
```
