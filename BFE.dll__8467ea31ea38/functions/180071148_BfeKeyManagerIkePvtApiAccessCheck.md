# BfeKeyManagerIkePvtApiAccessCheck

- ea: `0x180071148`
- end: `0x180071219`
- name: `BfeKeyManagerIkePvtApiAccessCheck`
- size: `209`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180062fe0`
- `0x1800630d0`

## callees

- `0x18001236c`
- `0x180018b74`
- `0x180039e30`
- `0x180058b30`
- `0x180071148`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800711b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800711b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800711e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800711e5`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x1800711aa`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x1800711aa`

## string_xrefs

- `0x1800711bd`: `PrivilegeCheck`
- `0x1800711d2`: `BfeKeyManagerIkePvtApiAccessCheck`
- `0x1800711f0`: `BfeKeyManagerIkePvtApiAccessCheck`

## pseudocode

```c
__int64 __fastcall BfeKeyManagerIkePvtApiAccessCheck(void *a1)
{
  __int64 AccessTokenFromClientBinding; // rbx
  __int64 v2; // rcx
  __int64 LastError; // r8
  const char *v4; // rdx
  HANDLE ClientToken; // [rsp+20h] [rbp-30h] BYREF
  WINBOOL pfResult; // [rsp+28h] [rbp-28h] BYREF
  struct _PRIVILEGE_SET RequiredPrivileges; // [rsp+30h] [rbp-20h] BYREF

  ClientToken = 0;
  pfResult = 0;
  memset(&RequiredPrivileges, 0, sizeof(RequiredPrivileges));
  AccessTokenFromClientBinding = BfeRpcGetAccessTokenFromClientBinding(a1, &ClientToken);
  if ( AccessTokenFromClientBinding )
    goto LABEL_8;
  *(_QWORD *)&RequiredPrivileges.PrivilegeCount = 1;
  *(_QWORD *)&RequiredPrivileges.Privilege[0].Luid.HighPart = 0;
  RequiredPrivileges.Privilege[0].Luid.LowPart = 7;
  if ( PrivilegeCheck(ClientToken, &RequiredPrivileges, &pfResult) )
  {
    if ( pfResult )
      goto LABEL_7;
    LastError = 1314;
    v4 = "BfeKeyManagerIkePvtApiAccessCheck";
  }
  else
  {
    LastError = GetLastError();
    v4 = "PrivilegeCheck";
  }
  AccessTokenFromClientBinding = WfpReportSysErrorAsWinError(v2, v4, LastError);
LABEL_7:
  CloseHandle(ClientToken);
  if ( AccessTokenFromClientBinding )
LABEL_8:
    WfpReportError(AccessTokenFromClientBinding, "BfeKeyManagerIkePvtApiAccessCheck");
  return AccessTokenFromClientBinding;
}

```

## disassembly

```asm
0x180071148  mov     [rsp-8+arg_8], rbx
0x18007114d  push    rbp
0x18007114e  mov     rbp, rsp
0x180071151  sub     rsp, 50h
0x180071155  mov     rax, cs:__security_cookie
0x18007115c  xor     rax, rsp
0x18007115f  mov     [rbp+var_8], rax
0x180071163  xor     eax, eax
0x180071165  mov     [rbp+ClientToken], 0
0x18007116d  xorps   xmm0, xmm0
0x180071170  mov     [rbp+RequiredPrivileges.Privilege.Attributes], eax
0x180071173  lea     rdx, [rbp+ClientToken]
0x180071177  mov     [rbp+pfResult], eax
0x18007117a  movups  xmmword ptr [rbp+RequiredPrivileges.PrivilegeCount], xmm0
0x18007117e  call    BfeRpcGetAccessTokenFromClientBinding
0x180071183  mov     rbx, rax
0x180071186  test    rax, rax
0x180071189  jnz     short loc_1800711F0
0x18007118b  mov     rcx, [rbp+ClientToken]; ClientToken
0x18007118f  lea     r8, [rbp+pfResult]; pfResult
0x180071193  lea     rdx, [rbp+RequiredPrivileges]; RequiredPrivileges
0x180071197  mov     qword ptr [rbp+RequiredPrivileges.PrivilegeCount], 1
0x18007119f  mov     qword ptr [rbp+RequiredPrivileges.Privilege.Luid.HighPart], rax
0x1800711a3  mov     [rbp+RequiredPrivileges.Privilege.Luid.LowPart], 7
0x1800711aa  call    cs:__imp_PrivilegeCheck
0x1800711b0  test    eax, eax
0x1800711b2  jnz     short loc_1800711C6
0x1800711b4  call    cs:__imp_GetLastError
0x1800711ba  mov     r8d, eax
0x1800711bd  lea     rdx, aPrivilegecheck; "PrivilegeCheck"
0x1800711c4  jmp     short loc_1800711D9
0x1800711c6  cmp     [rbp+pfResult], 0
0x1800711ca  jnz     short loc_1800711E1
0x1800711cc  mov     r8d, 522h
0x1800711d2  lea     rdx, aBfekeymanageri_0; "BfeKeyManagerIkePvtApiAccessCheck"
0x1800711d9  call    WfpReportSysErrorAsWinError
0x1800711de  mov     rbx, rax
0x1800711e1  mov     rcx, [rbp+ClientToken]; hObject
0x1800711e5  call    cs:__imp_CloseHandle
0x1800711eb  test    rbx, rbx
0x1800711ee  jz      short loc_1800711FF
0x1800711f0  lea     rdx, aBfekeymanageri_0; "BfeKeyManagerIkePvtApiAccessCheck"
0x1800711f7  mov     rcx, rbx
0x1800711fa  call    WfpReportError
0x1800711ff  mov     rax, rbx
0x180071202  mov     rcx, [rbp+var_8]
0x180071206  xor     rcx, rsp; StackCookie
0x180071209  call    __security_check_cookie
0x18007120e  mov     rbx, [rsp+50h+arg_8]
0x180071213  add     rsp, 50h
0x180071217  pop     rbp
0x180071218  retn
```
