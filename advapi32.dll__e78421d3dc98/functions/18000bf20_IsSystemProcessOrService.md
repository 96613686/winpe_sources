# IsSystemProcessOrService

- ea: `0x18000bf20`
- end: `0x18000c0c5`
- name: `IsSystemProcessOrService`
- size: `421`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000a78c`
- `0x18000b340`
- `0x1800103f4`

## callees

- `0x18000bf20`
- `0x180065090`

## import_xrefs

- `ntdll!NtOpenThreadToken` at `0x18000c070`
- `ntdll!NtOpenThreadToken` at `0x18000c070`
- `ntdll!NtOpenProcessToken` at `0x18000c08d`
- `ntdll!NtOpenProcessToken` at `0x18000c08d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000bf94`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000bf94`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18000bfe7`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18000bfe7`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18000c045`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18000c045`
- `KERNEL32!CloseHandle` at `0x18000c02d`
- `KERNEL32!CloseHandle` at `0x18000c0ad`
- `KERNEL32!CloseHandle` at `0x18000c02d`
- `KERNEL32!CloseHandle` at `0x18000c0ad`

## pseudocode

```c
BOOL __fastcall IsSystemProcessOrService(HANDLE a1)
{
  int v1; // ebx
  BOOL result; // eax
  HANDLE v3; // rdx
  NTSTATUS v4; // eax
  BOOL AccessStatus; // [rsp+40h] [rbp+7h] BYREF
  HANDLE ClientToken; // [rsp+48h] [rbp+Fh] BYREF
  int TokenInformation; // [rsp+50h] [rbp+17h] BYREF
  DWORD ReturnLength; // [rsp+54h] [rbp+1Bh] BYREF
  DWORD GrantedAccess; // [rsp+58h] [rbp+1Fh] BYREF
  DWORD PrivilegeSetLength; // [rsp+5Ch] [rbp+23h] BYREF
  HANDLE hObject; // [rsp+60h] [rbp+27h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+68h] [rbp+2Fh] BYREF

  ClientToken = a1;
  AccessStatus = 0;
  ReturnLength = 0;
  hObject = 0;
  TokenInformation = 0;
  PrivilegeSetLength = 20;
  GrantedAccess = 0;
  memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
  if ( a1 )
  {
    v1 = 1;
  }
  else
  {
    v1 = 0;
    v4 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x2000Au, 1u, &ClientToken);
    if ( v4 == -1073741700 )
      v4 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0x2000Au, &ClientToken);
    if ( v4 < 0 )
    {
      result = 0;
      AccessStatus = 0;
      goto LABEL_8;
    }
    a1 = ClientToken;
  }
  result = GetTokenInformation(a1, TokenType, &TokenInformation, 4u, &ReturnLength);
  AccessStatus = result;
  if ( !result )
    goto LABEL_8;
  if ( TokenInformation == 2 )
  {
    v3 = ClientToken;
  }
  else
  {
    result = DuplicateToken(ClientToken, SecurityImpersonation, &hObject);
    AccessStatus = result;
    if ( !result )
      goto LABEL_8;
    v3 = hObject;
  }
  if ( AccessCheck(
         qword_18007A5F8,
         v3,
         1u,
         (PGENERIC_MAPPING)&GenericMapping,
         &PrivilegeSet,
         &PrivilegeSetLength,
         &GrantedAccess,
         &AccessStatus) )
  {
    result = AccessStatus;
  }
  else
  {
    result = 0;
    AccessStatus = 0;
  }
LABEL_8:
  if ( hObject )
  {
    CloseHandle(hObject);
    result = AccessStatus;
  }
  if ( !v1 )
  {
    if ( ClientToken )
    {
      CloseHandle(ClientToken);
      return AccessStatus;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000bf20  mov     [rsp-8+arg_8], rbx
0x18000bf25  mov     [rsp-8+arg_10], rdi
0x18000bf2a  push    rbp
0x18000bf2b  lea     rbp, [rsp-57h]
0x18000bf30  sub     rsp, 90h
0x18000bf37  mov     rax, cs:__security_cookie
0x18000bf3e  xor     rax, rsp
0x18000bf41  mov     [rbp+57h+var_10], rax
0x18000bf45  xor     edi, edi
0x18000bf47  mov     [rbp+57h+ClientToken], rcx
0x18000bf4b  xor     eax, eax
0x18000bf4d  mov     [rbp+57h+var_50], edi
0x18000bf50  mov     [rbp+57h+var_3C], edi
0x18000bf53  xorps   xmm0, xmm0
0x18000bf56  mov     [rbp+57h+hObject], rdi
0x18000bf5a  mov     [rbp+57h+TokenInformation], edi
0x18000bf5d  mov     [rbp+57h+PrivilegeSet.Privilege.Attributes], eax
0x18000bf60  mov     [rbp+57h+var_34], 14h
0x18000bf67  mov     [rbp+57h+var_38], edi
0x18000bf6a  movups  xmmword ptr [rbp+57h+PrivilegeSet.PrivilegeCount], xmm0
0x18000bf6e  test    rcx, rcx
0x18000bf71  jz      loc_18000C05B
0x18000bf77  mov     ebx, 1
0x18000bf7c  lea     rax, [rbp+57h+var_3C]
0x18000bf80  mov     r9d, 4; TokenInformationLength
0x18000bf86  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18000bf8a  mov     [rsp+90h+ReturnLength], rax; ReturnLength
0x18000bf8f  mov     edx, 8; TokenInformationClass
0x18000bf94  call    cs:__imp_GetTokenInformation
0x18000bf9a  mov     [rbp+57h+var_50], eax
0x18000bf9d  test    eax, eax
0x18000bf9f  jz      short loc_18000BFF6
0x18000bfa1  cmp     [rbp+57h+TokenInformation], 2
0x18000bfa5  jnz     loc_18000C038
0x18000bfab  mov     rdx, [rbp+57h+ClientToken]; ClientToken
0x18000bfaf  lea     rax, [rbp+57h+var_50]
0x18000bfb3  mov     r8d, 1; DesiredAccess
0x18000bfb9  mov     [rsp+90h+AccessStatus], rax; AccessStatus
0x18000bfbe  lea     r9, GenericMapping; GenericMapping
0x18000bfc5  lea     rax, [rbp+57h+var_38]
0x18000bfc9  mov     [rsp+90h+GrantedAccess], rax; GrantedAccess
0x18000bfce  lea     rcx, qword_18007A5F8; pSecurityDescriptor
0x18000bfd5  lea     rax, [rbp+57h+var_34]
0x18000bfd9  mov     [rsp+90h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18000bfde  lea     rax, [rbp+57h+PrivilegeSet]
0x18000bfe2  mov     [rsp+90h+ReturnLength], rax; PrivilegeSet
0x18000bfe7  call    cs:__imp_AccessCheck
0x18000bfed  test    eax, eax
0x18000bfef  jnz     short loc_18000C028
0x18000bff1  mov     eax, edi
0x18000bff3  mov     [rbp+57h+var_50], eax
0x18000bff6  mov     rcx, [rbp+57h+hObject]; hObject
0x18000bffa  test    rcx, rcx
0x18000bffd  jnz     short loc_18000C02D
0x18000bfff  test    ebx, ebx
0x18000c001  jz      loc_18000C0A0
0x18000c007  mov     rcx, [rbp+57h+var_10]
0x18000c00b  xor     rcx, rsp; StackCookie
0x18000c00e  call    __security_check_cookie
0x18000c013  lea     r11, [rsp+90h+var_s0]
0x18000c01b  mov     rbx, [r11+18h]
0x18000c01f  mov     rdi, [r11+20h]
0x18000c023  mov     rsp, r11
0x18000c026  pop     rbp
0x18000c027  retn
0x18000c028  mov     eax, [rbp+57h+var_50]
0x18000c02b  jmp     short loc_18000BFF6
0x18000c02d  call    cs:__imp_CloseHandle
0x18000c033  mov     eax, [rbp+57h+var_50]
0x18000c036  jmp     short loc_18000BFFF
0x18000c038  mov     rcx, [rbp+57h+ClientToken]; ExistingTokenHandle
0x18000c03c  lea     r8, [rbp+57h+hObject]; DuplicateTokenHandle
0x18000c040  mov     edx, 2; ImpersonationLevel
0x18000c045  call    cs:__imp_DuplicateToken
0x18000c04b  mov     [rbp+57h+var_50], eax
0x18000c04e  test    eax, eax
0x18000c050  jz      short loc_18000BFF6
0x18000c052  mov     rdx, [rbp+57h+hObject]
0x18000c056  jmp     loc_18000BFAF
0x18000c05b  lea     r9, [rbp+57h+ClientToken]; TokenHandle
0x18000c05f  mov     r8b, 1; OpenAsSelf
0x18000c062  mov     edx, 2000Ah; DesiredAccess
0x18000c067  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18000c06e  mov     ebx, edi
0x18000c070  call    cs:__imp_NtOpenThreadToken
0x18000c076  cmp     eax, 0C000007Ch
0x18000c07b  jnz     short loc_18000C093
0x18000c07d  lea     r8, [rbp+57h+ClientToken]; TokenHandle
0x18000c081  mov     edx, 2000Ah; DesiredAccess
0x18000c086  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18000c08d  call    cs:__imp_NtOpenProcessToken
0x18000c093  test    eax, eax
0x18000c095  js      short loc_18000C0BB
0x18000c097  mov     rcx, [rbp+57h+ClientToken]
0x18000c09b  jmp     loc_18000BF7C
0x18000c0a0  mov     rcx, [rbp+57h+ClientToken]; hObject
0x18000c0a4  test    rcx, rcx
0x18000c0a7  jz      loc_18000C007
0x18000c0ad  call    cs:__imp_CloseHandle
0x18000c0b3  mov     eax, [rbp+57h+var_50]
0x18000c0b6  jmp     loc_18000C007
0x18000c0bb  mov     eax, edi
0x18000c0bd  mov     [rbp+57h+var_50], eax
0x18000c0c0  jmp     loc_18000BFF6
```
