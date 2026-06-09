# GetImpersonatedUsername(void)

- ea: `0x18000eb74`
- end: `0x18000ed47`
- name: `?GetImpersonatedUsername@@YAPEAGXZ`
- size: `467`
- prototype: `unsigned __int16 *(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x18000b0d0`

## callees

- `0x18000257c`
- `0x18000a25c`
- `0x18000a320`
- `0x18000eb74`
- `0x18000eddc`
- `0x18000fbf2`
- `0x18000fc30`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x18000ebc9`
- `KERNEL32!GetCurrentThread` at `0x18000ebc9`
- `KERNEL32!CloseHandle` at `0x18000ec1a`
- `KERNEL32!CloseHandle` at `0x18000ed0d`
- `KERNEL32!CloseHandle` at `0x18000ec1a`
- `KERNEL32!CloseHandle` at `0x18000ed0d`
- `KERNEL32!GetLastError` at `0x18000ed02`
- `KERNEL32!GetLastError` at `0x18000ed02`
- `ADVAPI32!GetTokenInformation` at `0x18000ec07`
- `ADVAPI32!GetTokenInformation` at `0x18000ec07`
- `ADVAPI32!LookupAccountSidW` at `0x18000ec53`
- `ADVAPI32!LookupAccountSidW` at `0x18000ec53`
- `ADVAPI32!OpenThreadToken` at `0x18000ebde`
- `ADVAPI32!OpenThreadToken` at `0x18000ebde`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
unsigned __int16 *GetImpersonatedUsername(void)
{
  HANDLE CurrentThread; // rax
  __int64 v1; // rax
  __int64 v2; // rsi
  unsigned __int64 v3; // rbx
  unsigned __int16 *TestMemory; // rdi
  int pExceptionObject; // [rsp+40h] [rbp-C0h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-B8h] BYREF
  DWORD ReturnLength; // [rsp+50h] [rbp-B0h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+54h] [rbp-ACh] BYREF
  DWORD cchReferencedDomainName; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cchName; // [rsp+5Ch] [rbp-A4h] BYREF
  PSID TokenInformation[64]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR ReferencedDomainName[512]; // [rsp+260h] [rbp+160h] BYREF
  WCHAR Name[512]; // [rsp+660h] [rbp+560h] BYREF

  TokenHandle = 0;
  memset_0(TokenInformation, 0, sizeof(TokenInformation));
  ReturnLength = 0;
  cchName = 512;
  cchReferencedDomainName = 512;
  peUse = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
  {
    pExceptionObject = 3;
    throw (TestException *)&pExceptionObject;
  }
  if ( !GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x200u, &ReturnLength) )
  {
    GetLastError();
    CloseHandle(TokenHandle);
    pExceptionObject = 3;
    throw (TestException *)&pExceptionObject;
  }
  CloseHandle(TokenHandle);
  if ( !LookupAccountSidW(
          0,
          TokenInformation[0],
          Name,
          &cchName,
          ReferencedDomainName,
          &cchReferencedDomainName,
          &peUse) )
  {
    pExceptionObject = 3;
    throw (TestException *)&pExceptionObject;
  }
  v1 = -1;
  v2 = -1;
  do
    ++v2;
  while ( ReferencedDomainName[v2] );
  do
    ++v1;
  while ( Name[v1] );
  v3 = v2 + v1 + 2;
  TestMemory = (unsigned __int16 *)AllocateTestMemory(2 * v3);
  StringCchCopyW(TestMemory, v3, ReferencedDomainName);
  *(_DWORD *)&TestMemory[v2] = 92;
  StringCchCatW(TestMemory, v3, Name);
  return TestMemory;
}

```

## disassembly

```asm
0x18000eb74  push    rbp
0x18000eb76  push    rbx
0x18000eb77  push    rsi
0x18000eb78  push    rdi
0x18000eb79  push    r14
0x18000eb7b  lea     rbp, [rsp-970h]
0x18000eb83  sub     rsp, 0A70h
0x18000eb8a  mov     rax, cs:__security_cookie
0x18000eb91  xor     rax, rsp
0x18000eb94  mov     [rbp+990h+var_30], rax
0x18000eb9b  mov     ebx, 200h
0x18000eba0  lea     rcx, [rsp+0A90h+TokenInformation]; void *
0x18000eba5  xor     r14d, r14d
0x18000eba8  mov     r8d, ebx; Size
0x18000ebab  xor     edx, edx; Val
0x18000ebad  mov     [rsp+0A90h+TokenHandle], r14
0x18000ebb2  call    memset_0
0x18000ebb7  mov     [rsp+0A90h+var_A40], r14d
0x18000ebbc  mov     [rsp+0A90h+cchName], ebx
0x18000ebc0  mov     [rsp+0A90h+var_A38], ebx
0x18000ebc4  mov     [rsp+0A90h+var_A3C], r14d
0x18000ebc9  call    cs:__imp_GetCurrentThread
0x18000ebcf  lea     r9, [rsp+0A90h+TokenHandle]; TokenHandle
0x18000ebd4  xor     r8d, r8d; OpenAsSelf
0x18000ebd7  mov     rcx, rax; ThreadHandle
0x18000ebda  lea     edx, [r14+8]; DesiredAccess
0x18000ebde  call    cs:__imp_OpenThreadToken
0x18000ebe4  test    eax, eax
0x18000ebe6  jz      loc_18000ECE8
0x18000ebec  mov     rcx, [rsp+0A90h+TokenHandle]; TokenHandle
0x18000ebf1  lea     rax, [rsp+0A90h+var_A40]
0x18000ebf6  mov     r9d, ebx; TokenInformationLength
0x18000ebf9  mov     [rsp+0A90h+ReturnLength], rax; ReturnLength
0x18000ebfe  lea     r8, [rsp+0A90h+TokenInformation]; TokenInformation
0x18000ec03  lea     edx, [r14+1]; TokenInformationClass
0x18000ec07  call    cs:__imp_GetTokenInformation
0x18000ec0d  test    eax, eax
0x18000ec0f  jz      loc_18000ED02
0x18000ec15  mov     rcx, [rsp+0A90h+TokenHandle]; hObject
0x18000ec1a  call    cs:__imp_CloseHandle
0x18000ec20  mov     rdx, [rsp+0A90h+TokenInformation]; Sid
0x18000ec25  lea     rax, [rsp+0A90h+var_A3C]
0x18000ec2a  mov     [rsp+0A90h+peUse], rax; peUse
0x18000ec2f  lea     r9, [rsp+0A90h+cchName]; cchName
0x18000ec34  lea     rax, [rsp+0A90h+var_A38]
0x18000ec39  xor     ecx, ecx; lpSystemName
0x18000ec3b  mov     [rsp+0A90h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18000ec40  lea     r8, [rbp+990h+Name]; Name
0x18000ec47  lea     rax, [rbp+990h+ReferencedDomainName]
0x18000ec4e  mov     [rsp+0A90h+ReturnLength], rax; ReferencedDomainName
0x18000ec53  call    cs:__imp_LookupAccountSidW
0x18000ec59  test    eax, eax
0x18000ec5b  jz      loc_18000ED2D
0x18000ec61  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000ec65  lea     rcx, [rbp+990h+ReferencedDomainName]
0x18000ec6c  mov     rsi, rax
0x18000ec6f  inc     rsi
0x18000ec72  cmp     [rcx+rsi*2], r14w
0x18000ec77  jnz     short loc_18000EC6F
0x18000ec79  lea     rcx, [rbp+990h+Name]
0x18000ec80  inc     rax
0x18000ec83  cmp     [rcx+rax*2], r14w
0x18000ec88  jnz     short loc_18000EC80
0x18000ec8a  lea     rbx, [rax+2]
0x18000ec8e  add     rbx, rsi
0x18000ec91  lea     rcx, [rbx+rbx]; unsigned __int64
0x18000ec95  call    ?AllocateTestMemory@@YAPEAX_K@Z; AllocateTestMemory(unsigned __int64)
0x18000ec9a  lea     r8, [rbp+990h+ReferencedDomainName]; unsigned __int16 *
0x18000eca1  mov     rdx, rbx; unsigned __int64
0x18000eca4  mov     rcx, rax; unsigned __int16 *
0x18000eca7  mov     rdi, rax
0x18000ecaa  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ecaf  lea     r8, [rbp+990h+Name]; unsigned __int16 *
0x18000ecb6  mov     dword ptr [rdi+rsi*2], 5Ch ; '\'
0x18000ecbd  mov     rdx, rbx; unsigned __int64
0x18000ecc0  mov     rcx, rdi; unsigned __int16 *
0x18000ecc3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ecc8  mov     rax, rdi
0x18000eccb  mov     rcx, [rbp+990h+var_30]
0x18000ecd2  xor     rcx, rsp; StackCookie
0x18000ecd5  call    __security_check_cookie
0x18000ecda  add     rsp, 0A70h
0x18000ece1  pop     r14
0x18000ece3  pop     rdi
0x18000ece4  pop     rsi
0x18000ece5  pop     rbx
0x18000ece6  pop     rbp
0x18000ece7  retn
0x18000ece8  lea     rdx, _TI1?AW4TestException@@; pThrowInfo
0x18000ecef  mov     [rsp+0A90h+pExceptionObject], 3
0x18000ecf7  lea     rcx, [rsp+0A90h+pExceptionObject]; pExceptionObject
0x18000ecfc  call    _CxxThrowException_0
0x18000ed02  call    cs:__imp_GetLastError
0x18000ed08  mov     rcx, [rsp+0A90h+TokenHandle]; hObject
0x18000ed0d  call    cs:__imp_CloseHandle
0x18000ed13  lea     rdx, _TI1?AW4TestException@@; pThrowInfo
0x18000ed1a  mov     [rsp+0A90h+pExceptionObject], 3
0x18000ed22  lea     rcx, [rsp+0A90h+pExceptionObject]; pExceptionObject
0x18000ed27  call    _CxxThrowException_0
0x18000ed2d  lea     rdx, _TI1?AW4TestException@@; pThrowInfo
0x18000ed34  mov     [rsp+0A90h+pExceptionObject], 3
0x18000ed3c  lea     rcx, [rsp+0A90h+pExceptionObject]; pExceptionObject
0x18000ed41  call    _CxxThrowException_0
```
