# TOKEN_ENTRY::GetPrimaryToken(void)

- ea: `0x1800059e0`
- end: `0x180005acd`
- name: `?GetPrimaryToken@TOKEN_ENTRY@@UEAAPEAXXZ`
- size: `237`
- prototype: `void *__fastcall(TOKEN_ENTRY *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800059e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a6d`
- `iisutil!PuDbgPrint` at `0x180005a9e`
- `iisutil!PuDbgPrint` at `0x180005a9e`
- `iisutil!?WriteUnlock@CSmallSpinLock@@QEAAXXZ` at `0x180005ab4`
- `iisutil!?WriteUnlock@CSmallSpinLock@@QEAAXXZ` at `0x180005ab4`
- `iisutil!?WriteLock@CSmallSpinLock@@QEAAXXZ` at `0x180005a0a`
- `iisutil!?WriteLock@CSmallSpinLock@@QEAAXXZ` at `0x180005a0a`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180005a36`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180005a5a`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180005a36`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180005a5a`

## string_xrefs

- `0x180005a85`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`
- `0x180005a8c`: `DuplicateTokenEx failed, GetLastError = %lx\n`
- `0x180005a7a`: `TOKEN_ENTRY::GetPrimaryToken`

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
0x1800059e0  mov     [rsp+arg_0], rbx
0x1800059e5  mov     [rsp+arg_8], rsi
0x1800059ea  push    rdi
0x1800059eb  sub     rsp, 30h
0x1800059ef  lea     rbx, [rcx+18h]
0x1800059f3  mov     rdi, rcx
0x1800059f6  cmp     qword ptr [rbx], 0
0x1800059fa  jnz     loc_180005ABA
0x180005a00  lea     rsi, [rcx+0F8h]
0x180005a07  mov     rcx, rsi
0x180005a0a  call    cs:__imp_?WriteLock@CSmallSpinLock@@QEAAXXZ; CSmallSpinLock::WriteLock(void)
0x180005a10  cmp     qword ptr [rbx], 0
0x180005a14  jnz     loc_180005AB1
0x180005a1a  mov     rcx, [rdi+10h]; hExistingToken
0x180005a1e  mov     r9d, 3; ImpersonationLevel
0x180005a24  mov     [rsp+38h+phNewToken], rbx; phNewToken
0x180005a29  xor     r8d, r8d; lpTokenAttributes
0x180005a2c  xor     edx, edx; dwDesiredAccess
0x180005a2e  mov     [rsp+38h+TokenType], 1; TokenType
0x180005a36  call    cs:__imp_DuplicateTokenEx
0x180005a3c  test    eax, eax
0x180005a3e  jnz     short loc_180005AA4
0x180005a40  mov     rcx, [rdi+10h]; hExistingToken
0x180005a44  lea     r9d, [rax+2]; ImpersonationLevel
0x180005a48  mov     [rsp+38h+phNewToken], rbx; phNewToken
0x180005a4d  xor     r8d, r8d; lpTokenAttributes
0x180005a50  xor     edx, edx; dwDesiredAccess
0x180005a52  mov     [rsp+38h+TokenType], 1; TokenType
0x180005a5a  call    cs:__imp_DuplicateTokenEx
0x180005a60  test    eax, eax
0x180005a62  jnz     short loc_180005AA4
0x180005a64  test    byte ptr cs:g_dwDebugFlags, 3
0x180005a6b  jz      short loc_180005AA4
0x180005a6d  call    cs:__imp_GetLastError
0x180005a73  mov     rcx, cs:g_pDebug
0x180005a7a  lea     r9, aTokenEntryGetp; "TOKEN_ENTRY::GetPrimaryToken"
0x180005a81  mov     dword ptr [rsp+38h+phNewToken], eax
0x180005a85  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180005a8c  lea     rax, aDuplicatetoken; "DuplicateTokenEx failed, GetLastError ="...
0x180005a93  mov     r8d, 4AFh
0x180005a99  mov     qword ptr [rsp+38h+TokenType], rax
0x180005a9e  call    cs:__imp_PuDbgPrint
0x180005aa4  cmp     qword ptr [rbx], 0
0x180005aa8  jz      short loc_180005AB1
0x180005aaa  or      dword ptr [rdi+104h], 2
0x180005ab1  mov     rcx, rsi
0x180005ab4  call    cs:__imp_?WriteUnlock@CSmallSpinLock@@QEAAXXZ; CSmallSpinLock::WriteUnlock(void)
0x180005aba  mov     rax, [rbx]
0x180005abd  mov     rbx, [rsp+38h+arg_0]
0x180005ac2  mov     rsi, [rsp+38h+arg_8]
0x180005ac7  add     rsp, 30h
0x180005acb  pop     rdi
0x180005acc  retn
```
