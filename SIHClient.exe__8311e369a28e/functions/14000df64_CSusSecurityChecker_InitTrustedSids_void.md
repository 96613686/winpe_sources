# CSusSecurityChecker::InitTrustedSids(void)

- ea: `0x14000df64`
- end: `0x14000e042`
- name: `?InitTrustedSids@CSusSecurityChecker@@AEAAJXZ`
- size: `222`
- prototype: `__int64 __fastcall(CSusSecurityChecker *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140003ee0`

## callees

- `0x140008e08`
- `0x14000df64`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x14000dfb1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x14000dfb1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000e003`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000e029`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000e003`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000e029`

## string_xrefs

- `0x14000e010`: `C:\__w\1\s\src\Client\lib\util\SecurityChecker.cpp`

## pseudocode

```c
__int64 __fastcall CSusSecurityChecker::InitTrustedSids(CSusSecurityChecker *this)
{
  int v1; // edi
  const WCHAR **v2; // rbx
  __int64 v4; // rbp
  const WCHAR *v5; // rcx
  const char *v6; // r9
  unsigned int LastError; // edi
  __int64 i; // rbx
  PSID Sid; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v1 = 0;
  v2 = (const WCHAR **)&CSusSecurityChecker::c_rgszTrustedSids;
  v4 = this - (CSusSecurityChecker *)&CSusSecurityChecker::c_rgszTrustedSids;
  while ( 1 )
  {
    if ( *(const WCHAR **)((char *)v2 + v4) )
      goto LABEL_5;
    v5 = *v2;
    Sid = 0;
    if ( !ConvertStringSidToSidW(v5, &Sid) )
      break;
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + v1, (signed __int64)Sid, 0) )
    {
      LocalFree(Sid);
      return 0;
    }
LABEL_5:
    ++v1;
    ++v2;
    if ( v1 >= 5 )
      return 0;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x147,
                (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SecurityChecker.cpp",
                v6);
  for ( i = 0; i < 5; ++i )
  {
    LocalFree(*((HLOCAL *)this + i));
    *((_QWORD *)this + i) = 0;
  }
  return LastError;
}

```

## disassembly

```asm
0x14000df64  mov     [rsp+arg_8], rbx
0x14000df69  mov     [rsp+arg_10], rbp
0x14000df6e  mov     [rsp+arg_18], rsi
0x14000df73  push    rdi
0x14000df74  sub     rsp, 30h
0x14000df78  mov     rax, cs:__security_cookie
0x14000df7f  xor     rax, rsp
0x14000df82  mov     [rsp+38h+var_10], rax
0x14000df87  xor     edi, edi
0x14000df89  lea     rbx, ?c_rgszTrustedSids@CSusSecurityChecker@@0QBQEB_WB; wchar_t const * const near * const CSusSecurityChecker::c_rgszTrustedSids
0x14000df90  mov     rbp, rcx
0x14000df93  mov     rsi, rcx
0x14000df96  sub     rbp, rbx
0x14000df99  cmp     qword ptr [rbx+rbp], 0
0x14000df9e  jnz     short loc_14000DFCD
0x14000dfa0  mov     rcx, [rbx]; StringSid
0x14000dfa3  lea     rdx, [rsp+38h+Sid]; Sid
0x14000dfa8  mov     [rsp+38h+Sid], 0
0x14000dfb1  call    cs:__imp_ConvertStringSidToSidW
0x14000dfb7  test    eax, eax
0x14000dfb9  jz      short loc_14000E00B
0x14000dfbb  mov     rcx, [rsp+38h+Sid]
0x14000dfc0  xor     eax, eax
0x14000dfc2  movsxd  rdx, edi
0x14000dfc5  lock cmpxchg [rsi+rdx*8], rcx
0x14000dfcb  jnz     short loc_14000DFFE
0x14000dfcd  inc     edi
0x14000dfcf  add     rbx, 8
0x14000dfd3  cmp     edi, 5
0x14000dfd6  jl      short loc_14000DF99
0x14000dfd8  xor     edi, edi
0x14000dfda  mov     eax, edi
0x14000dfdc  mov     rcx, [rsp+38h+var_10]
0x14000dfe1  xor     rcx, rsp; StackCookie
0x14000dfe4  call    __security_check_cookie
0x14000dfe9  mov     rbx, [rsp+38h+arg_8]
0x14000dfee  mov     rbp, [rsp+38h+arg_10]
0x14000dff3  mov     rsi, [rsp+38h+arg_18]
0x14000dff8  add     rsp, 30h
0x14000dffc  pop     rdi
0x14000dffd  retn
0x14000dffe  mov     rcx, [rsp+38h+Sid]; hMem
0x14000e003  call    cs:__imp_LocalFree
0x14000e009  jmp     short loc_14000DFD8
0x14000e00b  mov     rcx, [rsp+38h]; this
0x14000e010  lea     r8, aCW1SSrcClientL_34; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14000e017  mov     edx, 147h; void *
0x14000e01c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000e021  mov     edi, eax
0x14000e023  xor     ebx, ebx
0x14000e025  mov     rcx, [rsi+rbx*8]; hMem
0x14000e029  call    cs:__imp_LocalFree
0x14000e02f  mov     qword ptr [rsi+rbx*8], 0
0x14000e037  inc     rbx
0x14000e03a  cmp     rbx, 5
0x14000e03e  jl      short loc_14000E025
0x14000e040  jmp     short loc_14000DFDA
```
