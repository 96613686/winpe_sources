# PackageSid::PackageSidToPackageCapabilitySid(void * const,void * *)

- ea: `0x18005e98c`
- end: `0x18005eabd`
- name: `?PackageSidToPackageCapabilitySid@PackageSid@@SAJQEAXPEAPEAX@Z`
- size: `305`
- prototype: `__int64 __fastcall(PSID pSid, PSID *Sid)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18005d624`
- `0x18005fc34`
- `0x1800a8144`
- `0x1801f3b54`

## callees

- `0x18005e98c`
- `0x1800f0260`

## import_xrefs

- `ntdll!RtlValidSid` at `0x18005e9c2`
- `ntdll!RtlValidSid` at `0x18005e9c2`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18005ea75`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18005ea75`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18005e9e8`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18005e9f7`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18005ea06`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18005ea14`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18005ea22`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18005ea30`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18005ea40`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18005e9e8`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18005e9f7`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18005ea06`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18005ea14`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18005ea22`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18005ea30`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18005ea40`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18005e9d3`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18005e9d3`

## pseudocode

```c
__int64 __fastcall PackageSid::PackageSidToPackageCapabilitySid(PSID pSid, PSID *Sid)
{
  ULONG SubAuthority7; // r15d
  ULONG SubAuthority6; // r14d
  ULONG SubAuthority5; // ebp
  ULONG SubAuthority4; // esi
  ULONG SubAuthority3; // edi
  ULONG SubAuthority2; // ebx
  ULONG *SidSubAuthority; // rax
  NTSTATUS v11; // edx
  __int64 result; // rax
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+60h] [rbp-48h] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 3840;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  if ( !RtlValidSid(pSid) )
    return 2147942487LL;
  if ( *GetSidSubAuthorityCount(pSid) != 8 )
    return 2147549183LL;
  SubAuthority7 = *GetSidSubAuthority(pSid, 7u);
  SubAuthority6 = *GetSidSubAuthority(pSid, 6u);
  SubAuthority5 = *GetSidSubAuthority(pSid, 5u);
  SubAuthority4 = *GetSidSubAuthority(pSid, 4u);
  SubAuthority3 = *GetSidSubAuthority(pSid, 3u);
  SubAuthority2 = *GetSidSubAuthority(pSid, 2u);
  SidSubAuthority = GetSidSubAuthority(pSid, 1u);
  v11 = RtlAllocateAndInitializeSid(
          &IdentifierAuthority,
          8u,
          3u,
          *SidSubAuthority,
          SubAuthority2,
          SubAuthority3,
          SubAuthority4,
          SubAuthority5,
          SubAuthority6,
          SubAuthority7,
          Sid);
  result = 0;
  if ( v11 < 0 )
    return v11 | 0x10000000u;
  return result;
}

```

## disassembly

```asm
0x18005e98c  mov     [rsp+arg_10], rbx
0x18005e991  push    rbp
0x18005e992  push    rsi
0x18005e993  push    rdi
0x18005e994  push    r12
0x18005e996  push    r13
0x18005e998  push    r14
0x18005e99a  push    r15
0x18005e99c  sub     rsp, 70h
0x18005e9a0  mov     rax, cs:__security_cookie
0x18005e9a7  xor     rax, rsp
0x18005e9aa  mov     [rsp+0A8h+var_40], rax
0x18005e9af  xor     ebx, ebx
0x18005e9b1  mov     word ptr [rsp+0A8h+IdentifierAuthority.Value+4], 0F00h
0x18005e9b8  mov     dword ptr [rsp+0A8h+IdentifierAuthority.Value], ebx
0x18005e9bc  mov     r13, rdx
0x18005e9bf  mov     r12, rcx
0x18005e9c2  call    cs:__imp_RtlValidSid
0x18005e9c8  test    al, al
0x18005e9ca  jz      loc_18005EAAF
0x18005e9d0  mov     rcx, r12; pSid
0x18005e9d3  call    cs:__imp_GetSidSubAuthorityCount
0x18005e9d9  cmp     byte ptr [rax], 8
0x18005e9dc  jnz     loc_18005EAB6
0x18005e9e2  lea     edx, [rbx+7]; nSubAuthority
0x18005e9e5  mov     rcx, r12; pSid
0x18005e9e8  call    cs:__imp_GetSidSubAuthority
0x18005e9ee  lea     edx, [rbx+6]; nSubAuthority
0x18005e9f1  mov     rcx, r12; pSid
0x18005e9f4  mov     r15d, [rax]
0x18005e9f7  call    cs:__imp_GetSidSubAuthority
0x18005e9fd  lea     edx, [rbx+5]; nSubAuthority
0x18005ea00  mov     rcx, r12; pSid
0x18005ea03  mov     r14d, [rax]
0x18005ea06  call    cs:__imp_GetSidSubAuthority
0x18005ea0c  lea     edx, [rbx+4]; nSubAuthority
0x18005ea0f  mov     rcx, r12; pSid
0x18005ea12  mov     ebp, [rax]
0x18005ea14  call    cs:__imp_GetSidSubAuthority
0x18005ea1a  lea     edx, [rbx+3]; nSubAuthority
0x18005ea1d  mov     rcx, r12; pSid
0x18005ea20  mov     esi, [rax]
0x18005ea22  call    cs:__imp_GetSidSubAuthority
0x18005ea28  lea     edx, [rbx+2]; nSubAuthority
0x18005ea2b  mov     rcx, r12; pSid
0x18005ea2e  mov     edi, [rax]
0x18005ea30  call    cs:__imp_GetSidSubAuthority
0x18005ea36  mov     edx, 1; nSubAuthority
0x18005ea3b  mov     rcx, r12; pSid
0x18005ea3e  mov     ebx, [rax]
0x18005ea40  call    cs:__imp_GetSidSubAuthority
0x18005ea46  mov     [rsp+0A8h+Sid], r13; Sid
0x18005ea4b  lea     rcx, [rsp+0A8h+IdentifierAuthority]; IdentifierAuthority
0x18005ea50  mov     [rsp+0A8h+SubAuthority7], r15d; SubAuthority7
0x18005ea55  mov     r8d, 3; SubAuthority0
0x18005ea5b  mov     [rsp+0A8h+SubAuthority6], r14d; SubAuthority6
0x18005ea60  mov     dl, 8; SubAuthorityCount
0x18005ea62  mov     r9d, [rax]; SubAuthority1
0x18005ea65  mov     [rsp+0A8h+SubAuthority5], ebp; SubAuthority5
0x18005ea69  mov     [rsp+0A8h+SubAuthority4], esi; SubAuthority4
0x18005ea6d  mov     [rsp+0A8h+SubAuthority3], edi; SubAuthority3
0x18005ea71  mov     [rsp+0A8h+SubAuthority2], ebx; SubAuthority2
0x18005ea75  call    cs:__imp_RtlAllocateAndInitializeSid
0x18005ea7b  mov     ecx, eax
0x18005ea7d  mov     edx, eax
0x18005ea7f  bts     ecx, 1Ch
0x18005ea83  xor     eax, eax
0x18005ea85  test    edx, edx
0x18005ea87  cmovs   eax, ecx
0x18005ea8a  mov     rcx, [rsp+0A8h+var_40]
0x18005ea8f  xor     rcx, rsp; StackCookie
0x18005ea92  call    __security_check_cookie
0x18005ea97  mov     rbx, [rsp+0A8h+arg_10]
0x18005ea9f  add     rsp, 70h
0x18005eaa3  pop     r15
0x18005eaa5  pop     r14
0x18005eaa7  pop     r13
0x18005eaa9  pop     r12
0x18005eaab  pop     rdi
0x18005eaac  pop     rsi
0x18005eaad  pop     rbp
0x18005eaae  retn
0x18005eaaf  mov     eax, 80070057h
0x18005eab4  jmp     short loc_18005EA8A
0x18005eab6  mov     eax, 8000FFFFh
0x18005eabb  jmp     short loc_18005EA8A
```
