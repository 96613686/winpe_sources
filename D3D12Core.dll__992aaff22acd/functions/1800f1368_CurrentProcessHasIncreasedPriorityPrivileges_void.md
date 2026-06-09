# CurrentProcessHasIncreasedPriorityPrivileges(void)

- ea: `0x1800f1368`
- end: `0x1800f141d`
- name: `?CurrentProcessHasIncreasedPriorityPrivileges@@YA_NXZ`
- size: `181`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006be20`

## callees

- `0x1800718ac`
- `0x1800bb480`
- `0x1800f1368`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800f1389`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800f1389`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800f1399`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800f1399`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x1800f13eb`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x1800f13eb`
- `api-ms-win-security-lsalookup-ansi-l2-1-0!LookupPrivilegeValueA` at `0x1800f13bb`
- `api-ms-win-security-lsalookup-ansi-l2-1-0!LookupPrivilegeValueA` at `0x1800f13bb`

## string_xrefs

- `0x1800f13ab`: `SeIncreaseBasePriorityPrivilege`

## pseudocode

```c
bool CurrentProcessHasIncreasedPriorityPrivileges(void)
{
  bool v0; // bl
  HANDLE CurrentProcess; // rax
  WINBOOL pfResult; // [rsp+20h] [rbp-40h] BYREF
  void *TokenHandle; // [rsp+28h] [rbp-38h] BYREF
  struct _LUID Luid; // [rsp+30h] [rbp-30h] BYREF
  DWORD v6; // [rsp+38h] [rbp-28h]
  _PRIVILEGE_SET RequiredPrivileges; // [rsp+40h] [rbp-20h] BYREF

  v0 = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    Luid = 0;
    v6 = 2;
    if ( LookupPrivilegeValueA(0, "SeIncreaseBasePriorityPrivilege", &Luid) )
    {
      RequiredPrivileges.PrivilegeCount = 1;
      RequiredPrivileges.Control = 1;
      RequiredPrivileges.Privilege[0].Luid = Luid;
      RequiredPrivileges.Privilege[0].Attributes = v6;
      pfResult = 0;
      if ( PrivilegeCheck(TokenHandle, &RequiredPrivileges, &pfResult) )
        v0 = pfResult != 0;
    }
  }
  SafeHANDLE::Close((SafeHANDLE *)&TokenHandle);
  return v0;
}

```

## disassembly

```asm
0x1800f1368  mov     [rsp-8+arg_0], rbx
0x1800f136d  push    rbp
0x1800f136e  mov     rbp, rsp
0x1800f1371  sub     rsp, 60h
0x1800f1375  mov     rax, cs:__security_cookie
0x1800f137c  xor     rax, rsp
0x1800f137f  mov     [rbp+var_8], rax
0x1800f1383  xor     ebx, ebx
0x1800f1385  mov     [rbp+TokenHandle], rbx
0x1800f1389  call    cs:__imp_GetCurrentProcess
0x1800f138f  mov     rcx, rax; ProcessHandle
0x1800f1392  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800f1396  lea     edx, [rbx+8]; DesiredAccess
0x1800f1399  call    cs:__imp_OpenProcessToken
0x1800f139f  test    eax, eax
0x1800f13a1  jz      short loc_1800F13FB
0x1800f13a3  lea     r8, [rbp+Luid]; lpLuid
0x1800f13a7  mov     qword ptr [rbp+Luid.LowPart], rbx
0x1800f13ab  lea     rdx, Name; "SeIncreaseBasePriorityPrivilege"
0x1800f13b2  mov     [rbp+var_28], 2
0x1800f13b9  xor     ecx, ecx; lpSystemName
0x1800f13bb  call    cs:__imp_LookupPrivilegeValueA
0x1800f13c1  test    eax, eax
0x1800f13c3  jz      short loc_1800F13FB
0x1800f13c5  mov     rcx, [rbp+TokenHandle]; ClientToken
0x1800f13c9  lea     eax, [rbx+1]
0x1800f13cc  mov     [rbp+RequiredPrivileges.PrivilegeCount], eax
0x1800f13cf  lea     r8, [rbp+pfResult]; pfResult
0x1800f13d3  mov     [rbp+RequiredPrivileges.Control], eax
0x1800f13d6  lea     rdx, [rbp+RequiredPrivileges]; RequiredPrivileges
0x1800f13da  mov     rax, qword ptr [rbp+Luid.LowPart]
0x1800f13de  mov     qword ptr [rbp+RequiredPrivileges.Privilege.Luid.LowPart], rax
0x1800f13e2  mov     eax, [rbp+var_28]
0x1800f13e5  mov     [rbp+RequiredPrivileges.Privilege.Attributes], eax
0x1800f13e8  mov     [rbp+pfResult], ebx
0x1800f13eb  call    cs:__imp_PrivilegeCheck
0x1800f13f1  test    eax, eax
0x1800f13f3  jz      short loc_1800F13FB
0x1800f13f5  cmp     [rbp+pfResult], ebx
0x1800f13f8  setnz   bl
0x1800f13fb  lea     rcx, [rbp+TokenHandle]; this
0x1800f13ff  call    ?Close@SafeHANDLE@@QEAAXXZ; SafeHANDLE::Close(void)
0x1800f1404  mov     al, bl
0x1800f1406  mov     rcx, [rbp+var_8]
0x1800f140a  xor     rcx, rsp; StackCookie
0x1800f140d  call    __security_check_cookie
0x1800f1412  mov     rbx, [rsp+60h+arg_0]
0x1800f1417  add     rsp, 60h
0x1800f141b  pop     rbp
0x1800f141c  retn
```
