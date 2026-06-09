# TOKEN_ENTRY::GetImpersonationToken(void)

- ea: `0x180001da0`
- end: `0x180002005`
- name: `?GetImpersonationToken@TOKEN_ENTRY@@UEAAPEAXXZ`
- size: `613`
- prototype: `void *__fastcall(TOKEN_ENTRY *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001da0`
- `0x180005b70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001ea2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001f04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001faa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001ea2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001f04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001faa`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180001e94`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180001eed`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180001e94`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180001eed`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180001f6f`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180001f97`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180001f6f`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180001f97`
- `iisutil!?WriteUnlock@CSmallSpinLock@@QEAAXXZ` at `0x180001def`
- `iisutil!?WriteUnlock@CSmallSpinLock@@QEAAXXZ` at `0x180001def`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180001eb6`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180001eb6`
- `iisutil!DisableTokenBackupPrivilege` at `0x180001de0`
- `iisutil!DisableTokenBackupPrivilege` at `0x180001de0`
- `iisutil!PuDbgPrint` at `0x180001f35`
- `iisutil!PuDbgPrint` at `0x180001fdb`
- `iisutil!PuDbgPrint` at `0x180001f35`
- `iisutil!PuDbgPrint` at `0x180001fdb`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180001e54`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180001ec9`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180001e54`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180001ec9`
- `iisutil!?WriteLock@CSmallSpinLock@@QEAAXXZ` at `0x180001e30`
- `iisutil!?WriteLock@CSmallSpinLock@@QEAAXXZ` at `0x180001e30`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180001e62`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180001e62`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180001ff2`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180001ff2`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180001e49`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180001e49`

## string_xrefs

- `0x180001f1c`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`
- `0x180001fc2`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`
- `0x180001f23`: `Failed to get primary token security descriptor, GetLastError = %lx\n`
- `0x180001f11`: `TOKEN_ENTRY::GetImpersonationToken`
- `0x180001fb7`: `TOKEN_ENTRY::GetImpersonationToken`
- `0x180001fc9`: `DuplicateTokenEx failed, GetLastError = %lx\n`

## pseudocode

```c
void *__fastcall TOKEN_ENTRY::GetImpersonationToken(TOKEN_ENTRY *this)
{
  void **phNewToken; // rbx
  void *Ptr; // r14
  void *v5; // rcx
  DWORD LastError; // eax
  void *v7; // rcx
  DWORD v8; // eax
  DWORD nLengthNeeded; // [rsp+30h] [rbp-78h] BYREF
  _SECURITY_ATTRIBUTES TokenAttributes; // [rsp+38h] [rbp-70h] BYREF
  _BYTE v11[48]; // [rsp+50h] [rbp-58h] BYREF

  phNewToken = (void **)((char *)this + 16);
  if ( !*((_QWORD *)this + 2) )
  {
    CSmallSpinLock::WriteLock((TOKEN_ENTRY *)((char *)this + 248));
    if ( *phNewToken )
      goto LABEL_5;
    BUFFER::BUFFER((BUFFER *)v11);
    Ptr = BUFFER::QueryPtr((BUFFER *)v11);
    nLengthNeeded = BUFFER::QuerySize((BUFFER *)v11);
    v5 = (void *)*((_QWORD *)this + 3);
    memset(&TokenAttributes, 0, sizeof(TokenAttributes));
    if ( !GetKernelObjectSecurity(v5, 4u, Ptr, nLengthNeeded, &nLengthNeeded) )
    {
      if ( GetLastError() != 122 )
        goto LABEL_12;
      if ( !BUFFER::Resize((BUFFER *)v11, nLengthNeeded) )
      {
LABEL_20:
        BUFFER::~BUFFER((BUFFER *)v11);
LABEL_5:
        CSmallSpinLock::WriteUnlock((TOKEN_ENTRY *)((char *)this + 248));
        if ( !*phNewToken )
          return *phNewToken;
        goto LABEL_2;
      }
      Ptr = BUFFER::QueryPtr((BUFFER *)v11);
      if ( !GetKernelObjectSecurity(*((HANDLE *)this + 3), 4u, Ptr, nLengthNeeded, &nLengthNeeded) )
      {
LABEL_12:
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
        goto LABEL_20;
      }
    }
    v7 = (void *)*((_QWORD *)this + 3);
    TokenAttributes.nLength = 24;
    TokenAttributes.lpSecurityDescriptor = Ptr;
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
    goto LABEL_20;
  }
LABEL_2:
  if ( !*((_DWORD *)this + 29) && !_InterlockedExchange((volatile __int32 *)this + 29, 1) )
    DisableTokenBackupPrivilege(*phNewToken);
  return *phNewToken;
}

```

## disassembly

```asm
0x180001da0  push    rbx
0x180001da2  push    rsi
0x180001da3  push    rdi
0x180001da4  sub     rsp, 90h
0x180001dab  mov     rax, cs:__security_cookie
0x180001db2  xor     rax, rsp
0x180001db5  mov     [rsp+0A8h+var_28], rax
0x180001dbd  cmp     qword ptr [rcx+10h], 0
0x180001dc2  lea     rbx, [rcx+10h]
0x180001dc6  mov     rdi, rcx
0x180001dc9  mov     esi, 1
0x180001dce  jz      short loc_180001E21
0x180001dd0  cmp     dword ptr [rdi+74h], 0
0x180001dd4  jnz     short loc_180001E03
0x180001dd6  xchg    esi, [rdi+74h]
0x180001dd9  test    esi, esi
0x180001ddb  jnz     short loc_180001E03
0x180001ddd  mov     rcx, [rbx]
0x180001de0  call    cs:__imp_?DisableTokenBackupPrivilege@@YAXPEAX@Z; DisableTokenBackupPrivilege(void *)
0x180001de6  jmp     short loc_180001E03
0x180001de8  lea     rcx, [rdi+0F8h]
0x180001def  call    cs:__imp_?WriteUnlock@CSmallSpinLock@@QEAAXXZ; CSmallSpinLock::WriteUnlock(void)
0x180001df5  cmp     qword ptr [rbx], 0
0x180001df9  mov     rbp, [rsp+0A8h+arg_8]
0x180001e01  jnz     short loc_180001DD0
0x180001e03  mov     rax, [rbx]
0x180001e06  mov     rcx, [rsp+0A8h+var_28]
0x180001e0e  xor     rcx, rsp; StackCookie
0x180001e11  call    __security_check_cookie
0x180001e16  add     rsp, 90h
0x180001e1d  pop     rdi
0x180001e1e  pop     rsi
0x180001e1f  pop     rbx
0x180001e20  retn
0x180001e21  add     rcx, 0F8h
0x180001e28  mov     [rsp+0A8h+arg_8], rbp
0x180001e30  call    cs:__imp_?WriteLock@CSmallSpinLock@@QEAAXXZ; CSmallSpinLock::WriteLock(void)
0x180001e36  cmp     qword ptr [rbx], 0
0x180001e3a  jnz     short loc_180001DE8
0x180001e3c  lea     rcx, [rsp+0A8h+var_58]
0x180001e41  mov     [rsp+0A8h+arg_10], r14
0x180001e49  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x180001e4f  lea     rcx, [rsp+0A8h+var_58]
0x180001e54  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180001e5a  lea     rcx, [rsp+0A8h+var_58]
0x180001e5f  mov     r14, rax
0x180001e62  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180001e68  xor     ecx, ecx
0x180001e6a  xorps   xmm0, xmm0
0x180001e6d  mov     r9d, eax; nLength
0x180001e70  mov     [rsp+0A8h+nLengthNeeded], eax
0x180001e74  mov     qword ptr [rsp+0A8h+TokenAttributes.bInheritHandle], rcx
0x180001e79  mov     r8, r14; pSecurityDescriptor
0x180001e7c  lea     rcx, [rsp+0A8h+nLengthNeeded]
0x180001e81  mov     edx, 4; RequestedInformation
0x180001e86  mov     [rsp+0A8h+lpnLengthNeeded], rcx; lpnLengthNeeded
0x180001e8b  mov     rcx, [rdi+18h]; Handle
0x180001e8f  movups  xmmword ptr [rsp+0A8h+TokenAttributes.nLength], xmm0
0x180001e94  call    cs:__imp_GetKernelObjectSecurity
0x180001e9a  test    eax, eax
0x180001e9c  jnz     loc_180001F40
0x180001ea2  call    cs:__imp_GetLastError
0x180001ea8  cmp     eax, 7Ah ; 'z'
0x180001eab  jnz     short loc_180001EF7
0x180001ead  mov     edx, [rsp+0A8h+nLengthNeeded]
0x180001eb1  lea     rcx, [rsp+0A8h+var_58]
0x180001eb6  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180001ebc  test    al, al
0x180001ebe  jz      loc_180001FED
0x180001ec4  lea     rcx, [rsp+0A8h+var_58]
0x180001ec9  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180001ecf  mov     r9d, [rsp+0A8h+nLengthNeeded]; nLength
0x180001ed4  mov     edx, 4; RequestedInformation
0x180001ed9  mov     rcx, [rdi+18h]; Handle
0x180001edd  mov     r14, rax
0x180001ee0  lea     rax, [rsp+0A8h+nLengthNeeded]
0x180001ee5  mov     r8, r14; pSecurityDescriptor
0x180001ee8  mov     [rsp+0A8h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180001eed  call    cs:__imp_GetKernelObjectSecurity
0x180001ef3  test    eax, eax
0x180001ef5  jnz     short loc_180001F40
0x180001ef7  test    byte ptr cs:g_dwDebugFlags, 3
0x180001efe  jz      loc_180001FED
0x180001f04  call    cs:__imp_GetLastError
0x180001f0a  mov     rcx, cs:g_pDebug
0x180001f11  lea     r9, aTokenEntryGeti; "TOKEN_ENTRY::GetImpersonationToken"
0x180001f18  mov     dword ptr [rsp+0A8h+phNewToken], eax
0x180001f1c  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180001f23  lea     rax, aFailedToGetPri; "Failed to get primary token security de"...
0x180001f2a  mov     r8d, 447h
0x180001f30  mov     [rsp+0A8h+lpnLengthNeeded], rax
0x180001f35  call    cs:__imp_PuDbgPrint
0x180001f3b  jmp     loc_180001FED
0x180001f40  mov     rcx, [rdi+18h]; hExistingToken
0x180001f44  lea     r8, [rsp+0A8h+TokenAttributes]; lpTokenAttributes
0x180001f49  mov     [rsp+0A8h+phNewToken], rbx; phNewToken
0x180001f4e  mov     r9d, 3; ImpersonationLevel
0x180001f54  xor     edx, edx; dwDesiredAccess
0x180001f56  mov     dword ptr [rsp+0A8h+lpnLengthNeeded], 2; TokenType
0x180001f5e  mov     [rsp+0A8h+TokenAttributes.nLength], 18h
0x180001f66  mov     [rsp+0A8h+TokenAttributes.lpSecurityDescriptor], r14
0x180001f6b  mov     [rsp+0A8h+TokenAttributes.bInheritHandle], esi
0x180001f6f  call    cs:__imp_DuplicateTokenEx
0x180001f75  test    eax, eax
0x180001f77  jnz     short loc_180001FE1
0x180001f79  mov     rcx, [rdi+18h]; hExistingToken
0x180001f7d  lea     r8, [rsp+0A8h+TokenAttributes]; lpTokenAttributes
0x180001f82  mov     [rsp+0A8h+phNewToken], rbx; phNewToken
0x180001f87  mov     r9d, 2; ImpersonationLevel
0x180001f8d  xor     edx, edx; dwDesiredAccess
0x180001f8f  mov     dword ptr [rsp+0A8h+lpnLengthNeeded], 2; TokenType
0x180001f97  call    cs:__imp_DuplicateTokenEx
0x180001f9d  test    eax, eax
0x180001f9f  jnz     short loc_180001FE1
0x180001fa1  test    byte ptr cs:g_dwDebugFlags, 3
0x180001fa8  jz      short loc_180001FE1
0x180001faa  call    cs:__imp_GetLastError
0x180001fb0  mov     rcx, cs:g_pDebug
0x180001fb7  lea     r9, aTokenEntryGeti; "TOKEN_ENTRY::GetImpersonationToken"
0x180001fbe  mov     dword ptr [rsp+0A8h+phNewToken], eax
0x180001fc2  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180001fc9  lea     rax, aDuplicatetoken; "DuplicateTokenEx failed, GetLastError ="...
0x180001fd0  mov     r8d, 464h
0x180001fd6  mov     [rsp+0A8h+lpnLengthNeeded], rax
0x180001fdb  call    cs:__imp_PuDbgPrint
0x180001fe1  cmp     qword ptr [rbx], 0
0x180001fe5  jz      short loc_180001FED
0x180001fe7  or      [rdi+104h], esi
0x180001fed  lea     rcx, [rsp+0A8h+var_58]
0x180001ff2  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180001ff8  mov     r14, [rsp+0A8h+arg_10]
0x180002000  jmp     loc_180001DE8
```
