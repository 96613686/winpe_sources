# CSusSecurityChecker::InitTrustedSids(void)

- ea: `0x18000e754`
- end: `0x18000e832`
- name: `?InitTrustedSids@CSusSecurityChecker@@AEAAJXZ`
- size: `222`
- prototype: `__int64 __fastcall(CSusSecurityChecker *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000e684`
- `0x180018124`

## callees

- `0x180002214`
- `0x18000e754`
- `0x180061960`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000e7a1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000e7a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e7f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e819`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e7f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e819`

## string_xrefs

- `0x18000e800`: `C:\__w\1\s\src\Client\lib\util\SecurityChecker.cpp`

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
0x18000e754  mov     [rsp+arg_8], rbx
0x18000e759  mov     [rsp+arg_10], rbp
0x18000e75e  mov     [rsp+arg_18], rsi
0x18000e763  push    rdi
0x18000e764  sub     rsp, 30h
0x18000e768  mov     rax, cs:__security_cookie
0x18000e76f  xor     rax, rsp
0x18000e772  mov     [rsp+38h+var_10], rax
0x18000e777  xor     edi, edi
0x18000e779  lea     rbx, ?c_rgszTrustedSids@CSusSecurityChecker@@0QBQEB_WB; wchar_t const * const near * const CSusSecurityChecker::c_rgszTrustedSids
0x18000e780  mov     rbp, rcx
0x18000e783  mov     rsi, rcx
0x18000e786  sub     rbp, rbx
0x18000e789  cmp     qword ptr [rbx+rbp], 0
0x18000e78e  jnz     short loc_18000E7BD
0x18000e790  mov     rcx, [rbx]; StringSid
0x18000e793  lea     rdx, [rsp+38h+Sid]; Sid
0x18000e798  mov     [rsp+38h+Sid], 0
0x18000e7a1  call    cs:__imp_ConvertStringSidToSidW
0x18000e7a7  test    eax, eax
0x18000e7a9  jz      short loc_18000E7FB
0x18000e7ab  mov     rcx, [rsp+38h+Sid]
0x18000e7b0  xor     eax, eax
0x18000e7b2  movsxd  rdx, edi
0x18000e7b5  lock cmpxchg [rsi+rdx*8], rcx
0x18000e7bb  jnz     short loc_18000E7EE
0x18000e7bd  inc     edi
0x18000e7bf  add     rbx, 8
0x18000e7c3  cmp     edi, 5
0x18000e7c6  jl      short loc_18000E789
0x18000e7c8  xor     edi, edi
0x18000e7ca  mov     eax, edi
0x18000e7cc  mov     rcx, [rsp+38h+var_10]
0x18000e7d1  xor     rcx, rsp; StackCookie
0x18000e7d4  call    __security_check_cookie
0x18000e7d9  mov     rbx, [rsp+38h+arg_8]
0x18000e7de  mov     rbp, [rsp+38h+arg_10]
0x18000e7e3  mov     rsi, [rsp+38h+arg_18]
0x18000e7e8  add     rsp, 30h
0x18000e7ec  pop     rdi
0x18000e7ed  retn
0x18000e7ee  mov     rcx, [rsp+38h+Sid]; hMem
0x18000e7f3  call    cs:__imp_LocalFree
0x18000e7f9  jmp     short loc_18000E7C8
0x18000e7fb  mov     rcx, [rsp+38h]; this
0x18000e800  lea     r8, aCW1SSrcClientL_28; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000e807  mov     edx, 147h; void *
0x18000e80c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000e811  mov     edi, eax
0x18000e813  xor     ebx, ebx
0x18000e815  mov     rcx, [rsi+rbx*8]; hMem
0x18000e819  call    cs:__imp_LocalFree
0x18000e81f  mov     qword ptr [rsi+rbx*8], 0
0x18000e827  inc     rbx
0x18000e82a  cmp     rbx, 5
0x18000e82e  jl      short loc_18000E815
0x18000e830  jmp     short loc_18000E7CA
```
