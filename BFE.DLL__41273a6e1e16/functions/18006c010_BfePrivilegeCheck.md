# BfePrivilegeCheck

- ea: `0x18006c010`
- end: `0x18006c0fa`
- name: `BfePrivilegeCheck`
- size: `234`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006fd10`

## callees

- `0x180012d8c`
- `0x1800197d0`
- `0x1800335d0`
- `0x180035900`
- `0x180037954`
- `0x18005aa60`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c097`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c097`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x18006c087`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x18006c087`

## string_xrefs

- `0x18006c0a6`: `PrivilegeCheck`
- `0x18006c0bb`: `BfePrivilegeCheck`
- `0x18006c0cf`: `BfePrivilegeCheck`

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
0x18006c010  mov     [rsp+arg_0], rbx
0x18006c015  push    rdi
0x18006c016  sub     rsp, 50h
0x18006c01a  mov     rax, cs:__security_cookie
0x18006c021  xor     rax, rsp
0x18006c024  mov     [rsp+58h+var_18], rax
0x18006c029  xor     eax, eax
0x18006c02b  xorps   xmm0, xmm0
0x18006c02e  movups  xmmword ptr [rsp+58h+RequiredPrivileges.PrivilegeCount], xmm0
0x18006c033  mov     [rsp+58h+RequiredPrivileges.Privilege.Attributes], eax
0x18006c037  xor     ebx, ebx
0x18006c039  mov     [rsp+58h+pfResult], eax
0x18006c03d  call    BfeSessionGetToken
0x18006c042  mov     rdi, rax
0x18006c045  test    rax, rax
0x18006c048  jz      loc_18006C0DE
0x18006c04e  call    BfeSessionIsKernelMode
0x18006c053  test    eax, eax
0x18006c055  jnz     loc_18006C0DE
0x18006c05b  call    BfeCallBypassAccessChecks
0x18006c060  test    eax, eax
0x18006c062  jnz     short loc_18006C0DE
0x18006c064  lea     r8, [rsp+58h+pfResult]; pfResult
0x18006c069  mov     qword ptr [rsp+58h+RequiredPrivileges.PrivilegeCount], 1
0x18006c072  lea     rdx, [rsp+58h+RequiredPrivileges]; RequiredPrivileges
0x18006c077  mov     qword ptr [rsp+58h+RequiredPrivileges.Privilege.Luid.HighPart], rbx
0x18006c07c  mov     rcx, rdi; ClientToken
0x18006c07f  mov     [rsp+58h+RequiredPrivileges.Privilege.Luid.LowPart], 7
0x18006c087  call    cs:__imp_PrivilegeCheck
0x18006c08e  nop     dword ptr [rax+rax+00h]
0x18006c093  test    eax, eax
0x18006c095  jnz     short loc_18006C0AF
0x18006c097  call    cs:__imp_GetLastError
0x18006c09e  nop     dword ptr [rax+rax+00h]
0x18006c0a3  mov     r8d, eax
0x18006c0a6  lea     rdx, aPrivilegecheck; "PrivilegeCheck"
0x18006c0ad  jmp     short loc_18006C0C2
0x18006c0af  cmp     [rsp+58h+pfResult], ebx
0x18006c0b3  jnz     short loc_18006C0DE
0x18006c0b5  mov     r8d, 522h
0x18006c0bb  lea     rdx, aBfeprivilegech; "BfePrivilegeCheck"
0x18006c0c2  call    WfpReportSysErrorAsWinError
0x18006c0c7  mov     rbx, rax
0x18006c0ca  test    rax, rax
0x18006c0cd  jz      short loc_18006C0DE
0x18006c0cf  lea     rdx, aBfeprivilegech; "BfePrivilegeCheck"
0x18006c0d6  mov     rcx, rax
0x18006c0d9  call    WfpReportError
0x18006c0de  mov     rax, rbx
0x18006c0e1  mov     rcx, [rsp+58h+var_18]
0x18006c0e6  xor     rcx, rsp; StackCookie
0x18006c0e9  call    __security_check_cookie
0x18006c0ee  mov     rbx, [rsp+58h+arg_0]
0x18006c0f3  add     rsp, 50h
0x18006c0f7  pop     rdi
0x18006c0f8  retn
```
