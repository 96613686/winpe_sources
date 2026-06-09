# TOKEN_ENTRY::GetPrimaryToken(void)

- ea: `0x180005260`
- end: `0x18000534d`
- name: `?GetPrimaryToken@TOKEN_ENTRY@@UEAAPEAXXZ`
- size: `237`
- prototype: `void *__fastcall(TOKEN_ENTRY *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180005260`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800052ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800052ed`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800052b6`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800052da`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800052b6`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800052da`
- `iisutil!?WriteUnlock@CSmallSpinLock@@QEAAXXZ` at `0x180005334`
- `iisutil!?WriteUnlock@CSmallSpinLock@@QEAAXXZ` at `0x180005334`
- `iisutil!PuDbgPrint` at `0x18000531e`
- `iisutil!PuDbgPrint` at `0x18000531e`
- `iisutil!?WriteLock@CSmallSpinLock@@QEAAXXZ` at `0x18000528a`
- `iisutil!?WriteLock@CSmallSpinLock@@QEAAXXZ` at `0x18000528a`

## string_xrefs

- `0x180005305`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`
- `0x18000530c`: `DuplicateTokenEx failed, GetLastError = %lx\n`
- `0x1800052fa`: `TOKEN_ENTRY::GetPrimaryToken`

## pseudocode

```c
void *__fastcall TOKEN_ENTRY::GetPrimaryToken(HANDLE *this)
{
  void **phNewToken; // rbx
  CSmallSpinLock *v3; // rsi
  DWORD LastError; // eax

  phNewToken = this + 3;
  if ( !this[3] )
  {
    v3 = (CSmallSpinLock *)(this + 31);
    CSmallSpinLock::WriteLock((CSmallSpinLock *)(this + 31));
    if ( !*phNewToken )
    {
      if ( !DuplicateTokenEx(this[2], 0, 0, SecurityDelegation, TokenPrimary, phNewToken)
        && !DuplicateTokenEx(this[2], 0, 0, SecurityImpersonation, TokenPrimary, phNewToken)
        && (g_dwDebugFlags & 3) != 0 )
      {
        LastError = GetLastError();
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\common\\iislogon_lib\\iislogon.cxx",
          1199,
          "TOKEN_ENTRY::GetPrimaryToken",
          "DuplicateTokenEx failed, GetLastError = %lx\n",
          LastError);
      }
      if ( *phNewToken )
        *((_DWORD *)this + 65) |= 2u;
    }
    CSmallSpinLock::WriteUnlock(v3);
  }
  return *phNewToken;
}

```

## disassembly

```asm
0x180005260  mov     [rsp+arg_0], rbx
0x180005265  mov     [rsp+arg_8], rsi
0x18000526a  push    rdi
0x18000526b  sub     rsp, 30h
0x18000526f  lea     rbx, [rcx+18h]
0x180005273  mov     rdi, rcx
0x180005276  cmp     qword ptr [rbx], 0
0x18000527a  jnz     loc_18000533A
0x180005280  lea     rsi, [rcx+0F8h]
0x180005287  mov     rcx, rsi
0x18000528a  call    cs:__imp_?WriteLock@CSmallSpinLock@@QEAAXXZ; CSmallSpinLock::WriteLock(void)
0x180005290  cmp     qword ptr [rbx], 0
0x180005294  jnz     loc_180005331
0x18000529a  mov     rcx, [rdi+10h]; hExistingToken
0x18000529e  mov     r9d, 3; ImpersonationLevel
0x1800052a4  mov     [rsp+38h+phNewToken], rbx; phNewToken
0x1800052a9  xor     r8d, r8d; lpTokenAttributes
0x1800052ac  xor     edx, edx; dwDesiredAccess
0x1800052ae  mov     [rsp+38h+TokenType], 1; TokenType
0x1800052b6  call    cs:__imp_DuplicateTokenEx
0x1800052bc  test    eax, eax
0x1800052be  jnz     short loc_180005324
0x1800052c0  mov     rcx, [rdi+10h]; hExistingToken
0x1800052c4  lea     r9d, [rax+2]; ImpersonationLevel
0x1800052c8  mov     [rsp+38h+phNewToken], rbx; phNewToken
0x1800052cd  xor     r8d, r8d; lpTokenAttributes
0x1800052d0  xor     edx, edx; dwDesiredAccess
0x1800052d2  mov     [rsp+38h+TokenType], 1; TokenType
0x1800052da  call    cs:__imp_DuplicateTokenEx
0x1800052e0  test    eax, eax
0x1800052e2  jnz     short loc_180005324
0x1800052e4  test    byte ptr cs:g_dwDebugFlags, 3
0x1800052eb  jz      short loc_180005324
0x1800052ed  call    cs:__imp_GetLastError
0x1800052f3  mov     rcx, cs:g_pDebug
0x1800052fa  lea     r9, aTokenEntryGetp; "TOKEN_ENTRY::GetPrimaryToken"
0x180005301  mov     dword ptr [rsp+38h+phNewToken], eax
0x180005305  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000530c  lea     rax, aDuplicatetoken; "DuplicateTokenEx failed, GetLastError ="...
0x180005313  mov     r8d, 4AFh
0x180005319  mov     qword ptr [rsp+38h+TokenType], rax
0x18000531e  call    cs:__imp_PuDbgPrint
0x180005324  cmp     qword ptr [rbx], 0
0x180005328  jz      short loc_180005331
0x18000532a  or      dword ptr [rdi+104h], 2
0x180005331  mov     rcx, rsi
0x180005334  call    cs:__imp_?WriteUnlock@CSmallSpinLock@@QEAAXXZ; CSmallSpinLock::WriteUnlock(void)
0x18000533a  mov     rax, [rbx]
0x18000533d  mov     rbx, [rsp+38h+arg_0]
0x180005342  mov     rsi, [rsp+38h+arg_8]
0x180005347  add     rsp, 30h
0x18000534b  pop     rdi
0x18000534c  retn
```
