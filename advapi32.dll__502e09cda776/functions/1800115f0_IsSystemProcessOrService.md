# IsSystemProcessOrService

- ea: `0x1800115f0`
- end: `0x1800117c0`
- name: `IsSystemProcessOrService`
- size: `464`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000fc88`
- `0x180010910`
- `0x1800156e8`

## callees

- `0x1800115f0`
- `0x1800720b0`

## import_xrefs

- `ntdll!NtOpenThreadToken` at `0x180011759`
- `ntdll!NtOpenThreadToken` at `0x180011759`
- `ntdll!NtOpenProcessToken` at `0x18001177c`
- `ntdll!NtOpenProcessToken` at `0x18001177c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180011664`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180011664`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800116bd`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800116bd`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180011728`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180011728`
- `KERNEL32!CloseHandle` at `0x18001170a`
- `KERNEL32!CloseHandle` at `0x1800117a2`
- `KERNEL32!CloseHandle` at `0x18001170a`
- `KERNEL32!CloseHandle` at `0x1800117a2`

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
         qword_180088788,
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
0x1800115f0  mov     [rsp-8+arg_8], rbx
0x1800115f5  mov     [rsp-8+arg_10], rdi
0x1800115fa  push    rbp
0x1800115fb  lea     rbp, [rsp-57h]
0x180011600  sub     rsp, 90h
0x180011607  mov     rax, cs:__security_cookie
0x18001160e  xor     rax, rsp
0x180011611  mov     [rbp+57h+var_10], rax
0x180011615  xor     edi, edi
0x180011617  mov     [rbp+57h+ClientToken], rcx
0x18001161b  xor     eax, eax
0x18001161d  mov     [rbp+57h+var_50], edi
0x180011620  mov     [rbp+57h+var_3C], edi
0x180011623  xorps   xmm0, xmm0
0x180011626  mov     [rbp+57h+hObject], rdi
0x18001162a  mov     [rbp+57h+TokenInformation], edi
0x18001162d  mov     [rbp+57h+PrivilegeSet.Privilege.Attributes], eax
0x180011630  mov     [rbp+57h+var_34], 14h
0x180011637  mov     [rbp+57h+var_38], edi
0x18001163a  movups  xmmword ptr [rbp+57h+PrivilegeSet.PrivilegeCount], xmm0
0x18001163e  test    rcx, rcx
0x180011641  jz      loc_180011744
0x180011647  mov     ebx, 1
0x18001164c  lea     rax, [rbp+57h+var_3C]
0x180011650  mov     r9d, 4; TokenInformationLength
0x180011656  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18001165a  mov     [rsp+90h+ReturnLength], rax; ReturnLength
0x18001165f  mov     edx, 8; TokenInformationClass
0x180011664  call    cs:__imp_GetTokenInformation
0x18001166b  nop     dword ptr [rax+rax+00h]
0x180011670  mov     [rbp+57h+var_50], eax
0x180011673  test    eax, eax
0x180011675  jz      short loc_1800116D2
0x180011677  cmp     [rbp+57h+TokenInformation], 2
0x18001167b  jnz     loc_18001171B
0x180011681  mov     rdx, [rbp+57h+ClientToken]; ClientToken
0x180011685  lea     rax, [rbp+57h+var_50]
0x180011689  mov     r8d, 1; DesiredAccess
0x18001168f  mov     [rsp+90h+AccessStatus], rax; AccessStatus
0x180011694  lea     r9, GenericMapping; GenericMapping
0x18001169b  lea     rax, [rbp+57h+var_38]
0x18001169f  mov     [rsp+90h+GrantedAccess], rax; GrantedAccess
0x1800116a4  lea     rcx, qword_180088788; pSecurityDescriptor
0x1800116ab  lea     rax, [rbp+57h+var_34]
0x1800116af  mov     [rsp+90h+PrivilegeSetLength], rax; PrivilegeSetLength
0x1800116b4  lea     rax, [rbp+57h+PrivilegeSet]
0x1800116b8  mov     [rsp+90h+ReturnLength], rax; PrivilegeSet
0x1800116bd  call    cs:__imp_AccessCheck
0x1800116c4  nop     dword ptr [rax+rax+00h]
0x1800116c9  test    eax, eax
0x1800116cb  jnz     short loc_180011705
0x1800116cd  mov     eax, edi
0x1800116cf  mov     [rbp+57h+var_50], eax
0x1800116d2  mov     rcx, [rbp+57h+hObject]; hObject
0x1800116d6  test    rcx, rcx
0x1800116d9  jnz     short loc_18001170A
0x1800116db  test    ebx, ebx
0x1800116dd  jz      loc_180011795
0x1800116e3  mov     rcx, [rbp+57h+var_10]
0x1800116e7  xor     rcx, rsp; StackCookie
0x1800116ea  call    __security_check_cookie
0x1800116ef  lea     r11, [rsp+90h+var_s0]
0x1800116f7  mov     rbx, [r11+18h]
0x1800116fb  mov     rdi, [r11+20h]
0x1800116ff  mov     rsp, r11
0x180011702  pop     rbp
0x180011703  retn
0x180011705  mov     eax, [rbp+57h+var_50]
0x180011708  jmp     short loc_1800116D2
0x18001170a  call    cs:__imp_CloseHandle
0x180011711  nop     dword ptr [rax+rax+00h]
0x180011716  mov     eax, [rbp+57h+var_50]
0x180011719  jmp     short loc_1800116DB
0x18001171b  mov     rcx, [rbp+57h+ClientToken]; ExistingTokenHandle
0x18001171f  lea     r8, [rbp+57h+hObject]; DuplicateTokenHandle
0x180011723  mov     edx, 2; ImpersonationLevel
0x180011728  call    cs:__imp_DuplicateToken
0x18001172f  nop     dword ptr [rax+rax+00h]
0x180011734  mov     [rbp+57h+var_50], eax
0x180011737  test    eax, eax
0x180011739  jz      short loc_1800116D2
0x18001173b  mov     rdx, [rbp+57h+hObject]
0x18001173f  jmp     loc_180011685
0x180011744  lea     r9, [rbp+57h+ClientToken]; TokenHandle
0x180011748  mov     r8b, 1; OpenAsSelf
0x18001174b  mov     edx, 2000Ah; DesiredAccess
0x180011750  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180011757  mov     ebx, edi
0x180011759  call    cs:__imp_NtOpenThreadToken
0x180011760  nop     dword ptr [rax+rax+00h]
0x180011765  cmp     eax, 0C000007Ch
0x18001176a  jnz     short loc_180011788
0x18001176c  lea     r8, [rbp+57h+ClientToken]; TokenHandle
0x180011770  mov     edx, 2000Ah; DesiredAccess
0x180011775  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18001177c  call    cs:__imp_NtOpenProcessToken
0x180011783  nop     dword ptr [rax+rax+00h]
0x180011788  test    eax, eax
0x18001178a  js      short loc_1800117B6
0x18001178c  mov     rcx, [rbp+57h+ClientToken]
0x180011790  jmp     loc_18001164C
0x180011795  mov     rcx, [rbp+57h+ClientToken]; hObject
0x180011799  test    rcx, rcx
0x18001179c  jz      loc_1800116E3
0x1800117a2  call    cs:__imp_CloseHandle
0x1800117a9  nop     dword ptr [rax+rax+00h]
0x1800117ae  mov     eax, [rbp+57h+var_50]
0x1800117b1  jmp     loc_1800116E3
0x1800117b6  mov     eax, edi
0x1800117b8  mov     [rbp+57h+var_50], eax
0x1800117bb  jmp     loc_1800116D2
```
