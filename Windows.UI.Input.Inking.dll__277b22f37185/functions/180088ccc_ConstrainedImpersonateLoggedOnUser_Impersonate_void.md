# ConstrainedImpersonateLoggedOnUser::Impersonate(void)

- ea: `0x180088ccc`
- end: `0x180088d44`
- name: `?Impersonate@ConstrainedImpersonateLoggedOnUser@@QEAAJXZ`
- size: `120`
- prototype: `int(ConstrainedImpersonateLoggedOnUser *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800874ec`
- `0x18008760c`
- `0x1800890a0`

## callees

- `0x18001330c`
- `0x18001332c`
- `0x1800882b4`
- `0x180088ccc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180088d14`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180088d14`

## string_xrefs

- `0x180088ce9`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\constrainedimpersonationutil.h`
- `0x180088d23`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\constrainedimpersonationutil.h`

## pseudocode

```c
__int64 __fastcall ConstrainedImpersonateLoggedOnUser::Impersonate(ConstrainedImpersonateLoggedOnUser *this)
{
  int ImpersonationToken; // eax
  unsigned int v3; // edi
  char *v5; // rcx
  const char *v6; // r9
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  ImpersonationToken = ConstrainedImpersonateLoggedOnUser::GenerateImpersonationToken(this);
  v3 = ImpersonationToken;
  if ( ImpersonationToken < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x37,
      (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\constrainedimpersonationutil.h",
      (const char *)(unsigned int)ImpersonationToken,
      v7);
    return v3;
  }
  if ( !*(_BYTE *)this )
  {
    v5 = (char *)*((_QWORD *)this + 1);
    if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      if ( !ImpersonateLoggedOnUser(v5) )
        return wil::details::in1diag3::Return_GetLastError(
                 retaddr,
                 (void *)0x3D,
                 (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\constrainedimpersonationutil.h",
                 v6);
      *(_BYTE *)this = 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180088ccc  mov     [rsp+arg_0], rbx
0x180088cd1  push    rdi; int
0x180088cd2  sub     rsp, 20h
0x180088cd6  mov     rbx, rcx
0x180088cd9  call    ?GenerateImpersonationToken@ConstrainedImpersonateLoggedOnUser@@AEAAJXZ; ConstrainedImpersonateLoggedOnUser::GenerateImpersonationToken(void)
0x180088cde  mov     edi, eax
0x180088ce0  test    eax, eax
0x180088ce2  jns     short loc_180088D01
0x180088ce4  mov     rcx, [rsp+28h]; this
0x180088ce9  lea     r8, aOnecoreInterna_2; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x180088cf0  mov     r9d, eax; char *
0x180088cf3  mov     edx, 37h ; '7'; void *
0x180088cf8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180088cfd  mov     eax, edi
0x180088cff  jmp     short loc_180088D39
0x180088d01  cmp     byte ptr [rbx], 0
0x180088d04  jnz     short loc_180088D37
0x180088d06  mov     rcx, [rbx+8]; hToken
0x180088d0a  lea     rax, [rcx-1]
0x180088d0e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180088d12  ja      short loc_180088D37
0x180088d14  call    cs:__imp_ImpersonateLoggedOnUser
0x180088d1a  test    eax, eax
0x180088d1c  jnz     short loc_180088D34
0x180088d1e  mov     rcx, [rsp+28h]; this
0x180088d23  lea     r8, aOnecoreInterna_2; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x180088d2a  lea     edx, [rax+3Dh]; void *
0x180088d2d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180088d32  jmp     short loc_180088D39
0x180088d34  mov     byte ptr [rbx], 1
0x180088d37  xor     eax, eax
0x180088d39  mov     rbx, [rsp+28h+arg_0]
0x180088d3e  add     rsp, 20h
0x180088d42  pop     rdi
0x180088d43  retn
```
