# TOKEN_ENTRY::GetPrimaryToken(void)

- ea: `0x180004750`
- end: `0x18000483d`
- name: `?GetPrimaryToken@TOKEN_ENTRY@@UEAAPEAXXZ`
- size: `237`
- prototype: `void *__fastcall(TOKEN_ENTRY *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004750`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800047dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800047dd`
- `iisutil!PuDbgPrint` at `0x18000480e`
- `iisutil!PuDbgPrint` at `0x18000480e`
- `iisutil!?WriteUnlock@CSmallSpinLock@@QEAAXXZ` at `0x180004824`
- `iisutil!?WriteUnlock@CSmallSpinLock@@QEAAXXZ` at `0x180004824`
- `iisutil!?WriteLock@CSmallSpinLock@@QEAAXXZ` at `0x18000477a`
- `iisutil!?WriteLock@CSmallSpinLock@@QEAAXXZ` at `0x18000477a`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800047a6`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800047ca`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800047a6`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800047ca`

## string_xrefs

- `0x1800047f5`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`
- `0x1800047fc`: `DuplicateTokenEx failed, GetLastError = %lx\n`
- `0x1800047ea`: `TOKEN_ENTRY::GetPrimaryToken`

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
0x180004750  mov     [rsp+arg_0], rbx
0x180004755  mov     [rsp+arg_8], rsi
0x18000475a  push    rdi
0x18000475b  sub     rsp, 30h
0x18000475f  lea     rbx, [rcx+18h]
0x180004763  mov     rdi, rcx
0x180004766  cmp     qword ptr [rbx], 0
0x18000476a  jnz     loc_18000482A
0x180004770  lea     rsi, [rcx+0F8h]
0x180004777  mov     rcx, rsi
0x18000477a  call    cs:__imp_?WriteLock@CSmallSpinLock@@QEAAXXZ; CSmallSpinLock::WriteLock(void)
0x180004780  cmp     qword ptr [rbx], 0
0x180004784  jnz     loc_180004821
0x18000478a  mov     rcx, [rdi+10h]; hExistingToken
0x18000478e  mov     r9d, 3; ImpersonationLevel
0x180004794  mov     [rsp+38h+phNewToken], rbx; phNewToken
0x180004799  xor     r8d, r8d; lpTokenAttributes
0x18000479c  xor     edx, edx; dwDesiredAccess
0x18000479e  mov     [rsp+38h+TokenType], 1; TokenType
0x1800047a6  call    cs:__imp_DuplicateTokenEx
0x1800047ac  test    eax, eax
0x1800047ae  jnz     short loc_180004814
0x1800047b0  mov     rcx, [rdi+10h]; hExistingToken
0x1800047b4  lea     r9d, [rax+2]; ImpersonationLevel
0x1800047b8  mov     [rsp+38h+phNewToken], rbx; phNewToken
0x1800047bd  xor     r8d, r8d; lpTokenAttributes
0x1800047c0  xor     edx, edx; dwDesiredAccess
0x1800047c2  mov     [rsp+38h+TokenType], 1; TokenType
0x1800047ca  call    cs:__imp_DuplicateTokenEx
0x1800047d0  test    eax, eax
0x1800047d2  jnz     short loc_180004814
0x1800047d4  test    byte ptr cs:g_dwDebugFlags, 3
0x1800047db  jz      short loc_180004814
0x1800047dd  call    cs:__imp_GetLastError
0x1800047e3  mov     rcx, cs:g_pDebug
0x1800047ea  lea     r9, aTokenEntryGetp; "TOKEN_ENTRY::GetPrimaryToken"
0x1800047f1  mov     dword ptr [rsp+38h+phNewToken], eax
0x1800047f5  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800047fc  lea     rax, aDuplicatetoken; "DuplicateTokenEx failed, GetLastError ="...
0x180004803  mov     r8d, 4AFh
0x180004809  mov     qword ptr [rsp+38h+TokenType], rax
0x18000480e  call    cs:__imp_PuDbgPrint
0x180004814  cmp     qword ptr [rbx], 0
0x180004818  jz      short loc_180004821
0x18000481a  or      dword ptr [rdi+104h], 2
0x180004821  mov     rcx, rsi
0x180004824  call    cs:__imp_?WriteUnlock@CSmallSpinLock@@QEAAXXZ; CSmallSpinLock::WriteUnlock(void)
0x18000482a  mov     rax, [rbx]
0x18000482d  mov     rbx, [rsp+38h+arg_0]
0x180004832  mov     rsi, [rsp+38h+arg_8]
0x180004837  add     rsp, 30h
0x18000483b  pop     rdi
0x18000483c  retn
```
