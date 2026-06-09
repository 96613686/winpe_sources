# _anonymous_namespace_::IdentityFromSid

- ea: `0x18007610c`
- end: `0x180076195`
- name: `_anonymous_namespace_::IdentityFromSid`
- size: `137`
- prototype: `__int64 __fastcall(PSID pSid)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180075bc4`
- `0x180075d58`

## callees

- `0x18000d60c`
- `0x18000d62c`
- `0x18007610c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18007615a`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18007615a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18007617f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18007617f`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18007611c`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18007611c`

## string_xrefs

- `0x18007612b`: `onecore\ds\security\ngc\utils\bio\lib\bioutils.cpp`
- `0x180076169`: `onecore\ds\security\ngc\utils\bio\lib\bioutils.cpp`

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
0x18007610c  mov     [rsp+arg_0], rbx
0x180076111  push    rdi; int
0x180076112  sub     rsp, 20h
0x180076116  mov     rbx, rdx
0x180076119  mov     rdi, rcx
0x18007611c  call    cs:__imp_IsValidSid
0x180076122  test    eax, eax
0x180076124  jnz     short loc_180076148
0x180076126  mov     rcx, [rsp+28h]; this
0x18007612b  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\ngc\\utils\\bio"...
0x180076132  mov     ebx, 80070057h
0x180076137  mov     edx, 180h; void *
0x18007613c  mov     r9d, ebx; char *
0x18007613f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076144  mov     eax, ebx
0x180076146  jmp     short loc_18007618A
0x180076148  lea     rdx, [rbx+8]; pDestinationSid
0x18007614c  mov     dword ptr [rbx], 3
0x180076152  mov     r8, rdi; pSourceSid
0x180076155  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x18007615a  call    cs:__imp_CopySid
0x180076160  test    eax, eax
0x180076162  jnz     short loc_18007617C
0x180076164  mov     rcx, [rsp+28h]; this
0x180076169  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\ngc\\utils\\bio"...
0x180076170  mov     edx, 183h; void *
0x180076175  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18007617a  jmp     short loc_18007618A
0x18007617c  mov     rcx, rdi; pSid
0x18007617f  call    cs:__imp_GetLengthSid
0x180076185  mov     [rbx+4], eax
0x180076188  xor     eax, eax
0x18007618a  mov     rbx, [rsp+28h+arg_0]
0x18007618f  add     rsp, 20h
0x180076193  pop     rdi
0x180076194  retn
```
