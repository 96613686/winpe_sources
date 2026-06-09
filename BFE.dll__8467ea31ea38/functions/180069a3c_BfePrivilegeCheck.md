# BfePrivilegeCheck

- ea: `0x180069a3c`
- end: `0x180069b15`
- name: `BfePrivilegeCheck`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006d624`

## callees

- `0x18001236c`
- `0x180018b74`
- `0x180035810`
- `0x180037750`
- `0x1800390dc`
- `0x180058b30`
- `0x180069a3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069ab9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069ab9`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x180069aaf`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x180069aaf`

## string_xrefs

- `0x180069ac2`: `PrivilegeCheck`
- `0x180069ad7`: `BfePrivilegeCheck`
- `0x180069aeb`: `BfePrivilegeCheck`

## pseudocode

```c
__int64 BfePrivilegeCheck()
{
  __int64 v0; // rbx
  void *Token; // rdi
  __int64 v2; // rcx
  __int64 LastError; // r8
  const char *v4; // rdx
  __int64 v5; // rax
  WINBOOL pfResult; // [rsp+20h] [rbp-38h] BYREF
  _PRIVILEGE_SET RequiredPrivileges; // [rsp+28h] [rbp-30h] BYREF

  memset(&RequiredPrivileges, 0, sizeof(RequiredPrivileges));
  v0 = 0;
  pfResult = 0;
  Token = (void *)BfeSessionGetToken();
  if ( Token && !(unsigned int)BfeSessionIsKernelMode() && !(unsigned int)BfeCallBypassAccessChecks() )
  {
    *(_QWORD *)&RequiredPrivileges.PrivilegeCount = 1;
    *(_QWORD *)&RequiredPrivileges.Privilege[0].Luid.HighPart = 0;
    RequiredPrivileges.Privilege[0].Luid.LowPart = 7;
    if ( PrivilegeCheck(Token, &RequiredPrivileges, &pfResult) )
    {
      if ( pfResult )
        return v0;
      LastError = 1314;
      v4 = "BfePrivilegeCheck";
    }
    else
    {
      LastError = GetLastError();
      v4 = "PrivilegeCheck";
    }
    v5 = WfpReportSysErrorAsWinError(v2, v4, LastError);
    v0 = v5;
    if ( v5 )
      WfpReportError(v5, "BfePrivilegeCheck");
  }
  return v0;
}

```

## disassembly

```asm
0x180069a3c  mov     [rsp+arg_0], rbx
0x180069a41  push    rdi
0x180069a42  sub     rsp, 50h
0x180069a46  mov     rax, cs:__security_cookie
0x180069a4d  xor     rax, rsp
0x180069a50  mov     [rsp+58h+var_18], rax
0x180069a55  xor     eax, eax
0x180069a57  xorps   xmm0, xmm0
0x180069a5a  movups  xmmword ptr [rsp+58h+RequiredPrivileges.PrivilegeCount], xmm0
0x180069a5f  mov     [rsp+58h+RequiredPrivileges.Privilege.Attributes], eax
0x180069a63  xor     ebx, ebx
0x180069a65  mov     [rsp+58h+pfResult], eax
0x180069a69  call    BfeSessionGetToken
0x180069a6e  mov     rdi, rax
0x180069a71  test    rax, rax
0x180069a74  jz      loc_180069AFA
0x180069a7a  call    BfeSessionIsKernelMode
0x180069a7f  test    eax, eax
0x180069a81  jnz     short loc_180069AFA
0x180069a83  call    BfeCallBypassAccessChecks
0x180069a88  test    eax, eax
0x180069a8a  jnz     short loc_180069AFA
0x180069a8c  lea     r8, [rsp+58h+pfResult]; pfResult
0x180069a91  mov     qword ptr [rsp+58h+RequiredPrivileges.PrivilegeCount], 1
0x180069a9a  lea     rdx, [rsp+58h+RequiredPrivileges]; RequiredPrivileges
0x180069a9f  mov     qword ptr [rsp+58h+RequiredPrivileges.Privilege.Luid.HighPart], rbx
0x180069aa4  mov     rcx, rdi; ClientToken
0x180069aa7  mov     [rsp+58h+RequiredPrivileges.Privilege.Luid.LowPart], 7
0x180069aaf  call    cs:__imp_PrivilegeCheck
0x180069ab5  test    eax, eax
0x180069ab7  jnz     short loc_180069ACB
0x180069ab9  call    cs:__imp_GetLastError
0x180069abf  mov     r8d, eax
0x180069ac2  lea     rdx, aPrivilegecheck; "PrivilegeCheck"
0x180069ac9  jmp     short loc_180069ADE
0x180069acb  cmp     [rsp+58h+pfResult], ebx
0x180069acf  jnz     short loc_180069AFA
0x180069ad1  mov     r8d, 522h
0x180069ad7  lea     rdx, aBfeprivilegech; "BfePrivilegeCheck"
0x180069ade  call    WfpReportSysErrorAsWinError
0x180069ae3  mov     rbx, rax
0x180069ae6  test    rax, rax
0x180069ae9  jz      short loc_180069AFA
0x180069aeb  lea     rdx, aBfeprivilegech; "BfePrivilegeCheck"
0x180069af2  mov     rcx, rax
0x180069af5  call    WfpReportError
0x180069afa  mov     rax, rbx
0x180069afd  mov     rcx, [rsp+58h+var_18]
0x180069b02  xor     rcx, rsp; StackCookie
0x180069b05  call    __security_check_cookie
0x180069b0a  mov     rbx, [rsp+58h+arg_0]
0x180069b0f  add     rsp, 50h
0x180069b13  pop     rdi
0x180069b14  retn
```
