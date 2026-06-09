# _anonymous_namespace_::IdentityFromSid

- ea: `0x180057d74`
- end: `0x180057e10`
- name: `_anonymous_namespace_::IdentityFromSid`
- size: `156`
- prototype: `__int64 __fastcall(PSID pSid)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180057524`
- `0x180057aa4`

## callees

- `0x180022e68`
- `0x180023278`
- `0x180057d74`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180057df3`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180057df3`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180057dc8`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180057dc8`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180057d84`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180057d84`

## string_xrefs

- `0x180057d99`: `onecore\ds\security\ngc\utils\bio\lib\bioutils.cpp`
- `0x180057ddd`: `onecore\ds\security\ngc\utils\bio\lib\bioutils.cpp`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::IdentityFromSid(PSID pSid, _DWORD *a2)
{
  const char *v5; // r9
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( IsValidSid(pSid) )
  {
    *a2 = 3;
    if ( CopySid(0x44u, a2 + 2, pSid) )
    {
      a2[1] = GetLengthSid(pSid);
      return 0;
    }
    else
    {
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x183,
               (unsigned int)"onecore\\ds\\security\\ngc\\utils\\bio\\lib\\bioutils.cpp",
               v5);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x180,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\bio\\lib\\bioutils.cpp",
      (const char *)0x80070057LL,
      v6);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180057d74  mov     [rsp+arg_0], rbx
0x180057d79  push    rdi; int
0x180057d7a  sub     rsp, 20h
0x180057d7e  mov     rbx, rdx
0x180057d81  mov     rdi, rcx
0x180057d84  call    cs:__imp_IsValidSid
0x180057d8b  nop     dword ptr [rax+rax+00h]
0x180057d90  test    eax, eax
0x180057d92  jnz     short loc_180057DB6
0x180057d94  mov     rcx, [rsp+28h]; this
0x180057d99  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\ngc\\utils\\bio"...
0x180057da0  mov     ebx, 80070057h
0x180057da5  mov     edx, 180h; void *
0x180057daa  mov     r9d, ebx; char *
0x180057dad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180057db2  mov     eax, ebx
0x180057db4  jmp     short loc_180057E04
0x180057db6  lea     rdx, [rbx+8]; pDestinationSid
0x180057dba  mov     dword ptr [rbx], 3
0x180057dc0  mov     r8, rdi; pSourceSid
0x180057dc3  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x180057dc8  call    cs:__imp_CopySid
0x180057dcf  nop     dword ptr [rax+rax+00h]
0x180057dd4  test    eax, eax
0x180057dd6  jnz     short loc_180057DF0
0x180057dd8  mov     rcx, [rsp+28h]; this
0x180057ddd  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\ngc\\utils\\bio"...
0x180057de4  mov     edx, 183h; void *
0x180057de9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180057dee  jmp     short loc_180057E04
0x180057df0  mov     rcx, rdi; pSid
0x180057df3  call    cs:__imp_GetLengthSid
0x180057dfa  nop     dword ptr [rax+rax+00h]
0x180057dff  mov     [rbx+4], eax
0x180057e02  xor     eax, eax
0x180057e04  mov     rbx, [rsp+28h+arg_0]
0x180057e09  add     rsp, 20h
0x180057e0d  pop     rdi
0x180057e0e  retn
```
