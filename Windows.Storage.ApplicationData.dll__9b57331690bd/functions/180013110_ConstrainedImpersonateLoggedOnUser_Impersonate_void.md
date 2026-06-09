# ConstrainedImpersonateLoggedOnUser::Impersonate(void)

- ea: `0x180013110`
- end: `0x180013194`
- name: `?Impersonate@ConstrainedImpersonateLoggedOnUser@@QEAAJXZ`
- size: `132`
- prototype: `HRESULT __fastcall(ConstrainedImpersonateLoggedOnUser *this)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012d50`
- `0x18002491c`
- `0x180029440`
- `0x180035c28`

## callees

- `0x180013110`
- `0x18001319c`
- `0x180021efc`
- `0x180022528`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180013148`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180013148`

## string_xrefs

- `0x180013157`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\ConstrainedImpersonationUtil.h`
- `0x180013177`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\ConstrainedImpersonationUtil.h`

## pseudocode

```c
HRESULT __fastcall ConstrainedImpersonateLoggedOnUser::Impersonate(ConstrainedImpersonateLoggedOnUser *this)
{
  HRESULT ImpersonationToken; // eax
  HRESULT v3; // edi
  char *m_ptr; // rcx
  void *retaddr; // [rsp+28h] [rbp+0h]

  ImpersonationToken = ConstrainedImpersonateLoggedOnUser::GenerateImpersonationToken(this);
  v3 = ImpersonationToken;
  if ( ImpersonationToken < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x37u,
      "OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\ConstrainedImpersonationUtil.h",
      ImpersonationToken);
    return v3;
  }
  else
  {
    if ( this->m_impersonating )
      return 0;
    m_ptr = (char *)this->m_userTokenHandle.m_ptr;
    if ( (unsigned __int64)(m_ptr - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      return 0;
    if ( ImpersonateLoggedOnUser(m_ptr) )
    {
      this->m_impersonating = 1;
      return 0;
    }
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             0x3Du,
             "OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\ConstrainedImpersonationUtil.h");
  }
}

```

## disassembly

```asm
0x180013110  mov     [rsp+arg_0], rbx
0x180013115  push    rdi
0x180013116  sub     rsp, 20h
0x18001311a  mov     rbx, this
0x18001311d  call    ?GenerateImpersonationToken@ConstrainedImpersonateLoggedOnUser@@AEAAJXZ; ConstrainedImpersonateLoggedOnUser::GenerateImpersonationToken(void)
0x180013122  mov     edi, eax
0x180013124  test    eax, eax
0x180013126  js      short loc_180013172
0x180013128  cmp     byte ptr [rbx], 0
0x18001312b  jnz     short loc_18001313B
0x18001312d  mov     this, [rbx+8]; hToken
0x180013131  lea     rax, [this-1]
0x180013135  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180013139  jbe     short loc_180013148
0x18001313b  xor     eax, eax
0x18001313d  mov     rbx, [rsp+28h+arg_0]
0x180013142  add     rsp, 20h
0x180013146  pop     rdi
0x180013147  retn
0x180013148  call    cs:__imp_ImpersonateLoggedOnUser
0x18001314e  test    eax, eax
0x180013150  jnz     short loc_18001318F
0x180013152  mov     this, [rsp+28h]
0x180013157  lea     r8, aOnecoreInterna_0; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x18001315e  mov     edx, 3Dh ; '='
0x180013163  mov     rbx, [rsp+28h+arg_0]
0x180013168  add     rsp, 20h
0x18001316c  pop     rdi
0x18001316d  jmp     ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180013172  mov     this, [rsp+28h]; callerReturnAddress
0x180013177  lea     r8, aOnecoreInterna_0; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x18001317e  mov     r9d, edi; hr
0x180013181  mov     edx, 37h ; '7'; lineNumber
0x180013186  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001318b  mov     eax, edi
0x18001318d  jmp     short loc_18001313D
0x18001318f  mov     byte ptr [rbx], 1
0x180013192  jmp     short loc_18001313B
```
