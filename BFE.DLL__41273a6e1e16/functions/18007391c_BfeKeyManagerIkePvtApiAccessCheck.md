# BfeKeyManagerIkePvtApiAccessCheck

- ea: `0x18007391c`
- end: `0x180073a00`
- name: `BfeKeyManagerIkePvtApiAccessCheck`
- size: `228`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180065330`
- `0x180065420`

## callees

- `0x180012d8c`
- `0x1800197d0`
- `0x180038a20`
- `0x18005aa60`
- `0x18007391c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007398e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007398e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800739c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800739c5`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x18007397e`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x18007397e`

## string_xrefs

- `0x18007399d`: `PrivilegeCheck`
- `0x1800739b2`: `BfeKeyManagerIkePvtApiAccessCheck`
- `0x1800739d6`: `BfeKeyManagerIkePvtApiAccessCheck`

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
0x18007391c  mov     [rsp-8+arg_8], rbx
0x180073921  push    rbp
0x180073922  mov     rbp, rsp
0x180073925  sub     rsp, 50h
0x180073929  mov     rax, cs:__security_cookie
0x180073930  xor     rax, rsp
0x180073933  mov     [rbp+var_8], rax
0x180073937  xor     eax, eax
0x180073939  mov     [rbp+ClientToken], 0
0x180073941  xorps   xmm0, xmm0
0x180073944  mov     [rbp+RequiredPrivileges.Privilege.Attributes], eax
0x180073947  lea     rdx, [rbp+ClientToken]
0x18007394b  mov     [rbp+pfResult], eax
0x18007394e  movups  xmmword ptr [rbp+RequiredPrivileges.PrivilegeCount], xmm0
0x180073952  call    BfeRpcGetAccessTokenFromClientBinding
0x180073957  mov     rbx, rax
0x18007395a  test    rax, rax
0x18007395d  jnz     short loc_1800739D6
0x18007395f  mov     rcx, [rbp+ClientToken]; ClientToken
0x180073963  lea     r8, [rbp+pfResult]; pfResult
0x180073967  lea     rdx, [rbp+RequiredPrivileges]; RequiredPrivileges
0x18007396b  mov     qword ptr [rbp+RequiredPrivileges.PrivilegeCount], 1
0x180073973  mov     qword ptr [rbp+RequiredPrivileges.Privilege.Luid.HighPart], rax
0x180073977  mov     [rbp+RequiredPrivileges.Privilege.Luid.LowPart], 7
0x18007397e  call    cs:__imp_PrivilegeCheck
0x180073985  nop     dword ptr [rax+rax+00h]
0x18007398a  test    eax, eax
0x18007398c  jnz     short loc_1800739A6
0x18007398e  call    cs:__imp_GetLastError
0x180073995  nop     dword ptr [rax+rax+00h]
0x18007399a  mov     r8d, eax
0x18007399d  lea     rdx, aPrivilegecheck; "PrivilegeCheck"
0x1800739a4  jmp     short loc_1800739B9
0x1800739a6  cmp     [rbp+pfResult], 0
0x1800739aa  jnz     short loc_1800739C1
0x1800739ac  mov     r8d, 522h
0x1800739b2  lea     rdx, aBfekeymanageri_0; "BfeKeyManagerIkePvtApiAccessCheck"
0x1800739b9  call    WfpReportSysErrorAsWinError
0x1800739be  mov     rbx, rax
0x1800739c1  mov     rcx, [rbp+ClientToken]; hObject
0x1800739c5  call    cs:__imp_CloseHandle
0x1800739cc  nop     dword ptr [rax+rax+00h]
0x1800739d1  test    rbx, rbx
0x1800739d4  jz      short loc_1800739E5
0x1800739d6  lea     rdx, aBfekeymanageri_0; "BfeKeyManagerIkePvtApiAccessCheck"
0x1800739dd  mov     rcx, rbx
0x1800739e0  call    WfpReportError
0x1800739e5  mov     rax, rbx
0x1800739e8  mov     rcx, [rbp+var_8]
0x1800739ec  xor     rcx, rsp; StackCookie
0x1800739ef  call    __security_check_cookie
0x1800739f4  mov     rbx, [rsp+50h+arg_8]
0x1800739f9  add     rsp, 50h
0x1800739fd  pop     rbp
0x1800739fe  retn
```
