# ConstrainedImpersonateLoggedOnUser::Impersonate(void)

- ea: `0x18004215c`
- end: `0x1800421d4`
- name: `?Impersonate@ConstrainedImpersonateLoggedOnUser@@QEAAJXZ`
- size: `120`
- prototype: `__int64 __fastcall(ConstrainedImpersonateLoggedOnUser *this)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003ceb8`
- `0x180043ddc`

## callees

- `0x180010b64`
- `0x180010b84`
- `0x18003da90`
- `0x18004215c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800421a4`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800421a4`

## string_xrefs

- `0x180042179`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\ConstrainedImpersonationUtil.h`
- `0x1800421b3`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\ConstrainedImpersonationUtil.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
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
      (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\ConstrainedImpersonationUtil.h",
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
                 (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\ConstrainedImpersonationUtil.h",
                 v6);
      *(_BYTE *)this = 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18004215c  mov     [rsp+arg_0], rbx
0x180042161  push    rdi; int
0x180042162  sub     rsp, 20h
0x180042166  mov     rbx, rcx
0x180042169  call    ?GenerateImpersonationToken@ConstrainedImpersonateLoggedOnUser@@AEAAJXZ; ConstrainedImpersonateLoggedOnUser::GenerateImpersonationToken(void)
0x18004216e  mov     edi, eax
0x180042170  test    eax, eax
0x180042172  jns     short loc_180042191
0x180042174  mov     rcx, [rsp+28h]; this
0x180042179  lea     r8, aOnecoreInterna_0; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x180042180  mov     r9d, eax; char *
0x180042183  mov     edx, 37h ; '7'; void *
0x180042188  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004218d  mov     eax, edi
0x18004218f  jmp     short loc_1800421C9
0x180042191  cmp     byte ptr [rbx], 0
0x180042194  jnz     short loc_1800421C7
0x180042196  mov     rcx, [rbx+8]; hToken
0x18004219a  lea     rax, [rcx-1]
0x18004219e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800421a2  ja      short loc_1800421C7
0x1800421a4  call    cs:__imp_ImpersonateLoggedOnUser
0x1800421aa  test    eax, eax
0x1800421ac  jnz     short loc_1800421C4
0x1800421ae  mov     rcx, [rsp+28h]; this
0x1800421b3  lea     r8, aOnecoreInterna_0; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x1800421ba  lea     edx, [rax+3Dh]; void *
0x1800421bd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800421c2  jmp     short loc_1800421C9
0x1800421c4  mov     byte ptr [rbx], 1
0x1800421c7  xor     eax, eax
0x1800421c9  mov     rbx, [rsp+28h+arg_0]
0x1800421ce  add     rsp, 20h
0x1800421d2  pop     rdi
0x1800421d3  retn
```
