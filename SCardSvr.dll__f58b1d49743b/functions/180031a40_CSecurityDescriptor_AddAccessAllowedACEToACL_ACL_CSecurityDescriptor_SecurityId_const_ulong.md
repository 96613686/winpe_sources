# CSecurityDescriptor::AddAccessAllowedACEToACL(_ACL * *,CSecurityDescriptor::SecurityId const *,ulong)

- ea: `0x180031a40`
- end: `0x180031bd1`
- name: `?AddAccessAllowedACEToACL@CSecurityDescriptor@@SAJPEAPEAU_ACL@@PEBUSecurityId@1@K@Z`
- size: `401`
- prototype: `int __fastcall(struct _ACL **, struct _SID_IDENTIFIER_AUTHORITY *, DWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180031bd8`

## callees

- `0x180023168`
- `0x180023174`
- `0x180031a40`
- `0x180031c40`
- `0x1800326d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031ab3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031ab3`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x180031aa1`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x180031aa1`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180031b53`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180031b53`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180031a78`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180031a78`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180031ade`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180031ade`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180031b1c`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180031b1c`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180031b8a`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180031b8a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180031b25`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180031b25`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180031af0`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180031af0`

## pseudocode

```c
int __fastcall CSecurityDescriptor::AddAccessAllowedACEToACL(
        struct _ACL **a1,
        struct _SID_IDENTIFIER_AUTHORITY *a2,
        DWORD a3)
{
  struct _ACL *v3; // r14
  UCHAR v5; // cl
  DWORD SidLengthRequired; // eax
  void *v9; // rax
  void *v10; // rdi
  int result; // eax
  __int64 i; // rbp
  DWORD v13; // ebx
  PDWORD SidSubAuthority; // rax
  bool v15; // zf
  DWORD LengthSid; // eax
  signed int v17; // ebx
  struct _ACL *v18; // rax
  struct _ACL *v19; // rsi
  int v20; // ebx
  BOOL v21; // eax
  struct _ACL *v22; // rcx
  __int64 pAclInformation; // [rsp+20h] [rbp-58h] BYREF
  int v24; // [rsp+28h] [rbp-50h]

  v3 = *a1;
  pAclInformation = 0;
  v5 = a2[1].Value[2];
  v24 = 0;
  SidLengthRequired = GetSidLengthRequired(v5);
  v9 = operator new[](SidLengthRequired);
  v10 = v9;
  if ( !v9 )
    return -2147024882;
  if ( InitializeSid(v9, a2, a2[1].Value[2]) )
  {
    for ( i = 0; (unsigned int)i < *(_DWORD *)&a2[1].Value[2]; *SidSubAuthority = v13 )
    {
      v13 = *(_DWORD *)&a2[2].Value[4 * i];
      SidSubAuthority = GetSidSubAuthority(v10, i);
      i = (unsigned int)(i + 1);
    }
    if ( IsValidSid(v10) )
    {
      v15 = *a1 == 0;
      HIDWORD(pAclInformation) = 0;
      if ( !v15 )
        GetAclInformation(v3, &pAclInformation, 0xCu, AclSizeInformation);
      LengthSid = GetLengthSid(v10);
      v17 = LengthSid + HIDWORD(pAclInformation) + 16;
      v18 = (struct _ACL *)operator new[](v17);
      v19 = v18;
      if ( !v18 )
      {
        v20 = -2147024882;
LABEL_22:
        operator delete[](v10);
        return v20;
      }
      v21 = InitializeAcl(v18, v17, 2u);
      v22 = v19;
      if ( v21 )
      {
        v20 = CSecurityDescriptor::CopyACL(v19, v3);
        if ( v20 < 0 )
        {
          operator delete[](v19);
          goto LABEL_22;
        }
        if ( AddAccessAllowedAce(v19, 2u, a3, v10) )
        {
          *a1 = v19;
          if ( v3 )
            operator delete[](v3);
          v20 = 0;
          goto LABEL_22;
        }
        v22 = v19;
      }
      operator delete[](v22);
    }
  }
  operator delete[](v10);
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180031a40  push    rbx
0x180031a42  push    rbp
0x180031a43  push    rsi
0x180031a44  push    rdi
0x180031a45  push    r12
0x180031a47  push    r14
0x180031a49  push    r15
0x180031a4b  sub     rsp, 40h
0x180031a4f  mov     rax, cs:__security_cookie
0x180031a56  xor     rax, rsp
0x180031a59  mov     [rsp+78h+var_48], rax
0x180031a5e  mov     r14, [rcx]
0x180031a61  xor     eax, eax
0x180031a63  mov     r15, rcx
0x180031a66  mov     [rsp+78h+pAclInformation], rax
0x180031a6b  mov     cl, [rdx+8]; nSubAuthorityCount
0x180031a6e  mov     r12d, r8d
0x180031a71  mov     [rsp+78h+var_50], eax
0x180031a75  mov     rsi, rdx
0x180031a78  call    cs:__imp_GetSidLengthRequired
0x180031a7e  mov     ecx, eax; unsigned __int64
0x180031a80  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180031a85  mov     rdi, rax
0x180031a88  test    rax, rax
0x180031a8b  jnz     short loc_180031A97
0x180031a8d  mov     eax, 8007000Eh
0x180031a92  jmp     loc_180031BB5
0x180031a97  mov     r8b, [rsi+8]; nSubAuthorityCount
0x180031a9b  mov     rdx, rsi; pIdentifierAuthority
0x180031a9e  mov     rcx, rdi; Sid
0x180031aa1  call    cs:__imp_InitializeSid
0x180031aa7  test    eax, eax
0x180031aa9  jnz     short loc_180031ACE
0x180031aab  mov     rcx, rdi; Block
0x180031aae  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180031ab3  call    cs:__imp_GetLastError
0x180031ab9  test    eax, eax
0x180031abb  jle     loc_180031BB5
0x180031ac1  movzx   eax, ax
0x180031ac4  or      eax, 80070000h
0x180031ac9  jmp     loc_180031BB5
0x180031ace  xor     ebp, ebp
0x180031ad0  cmp     [rsi+8], ebp
0x180031ad3  jbe     short loc_180031AED
0x180031ad5  mov     ebx, [rsi+rbp*4+0Ch]
0x180031ad9  mov     edx, ebp; nSubAuthority
0x180031adb  mov     rcx, rdi; pSid
0x180031ade  call    cs:__imp_GetSidSubAuthority
0x180031ae4  inc     ebp
0x180031ae6  mov     [rax], ebx
0x180031ae8  cmp     ebp, [rsi+8]
0x180031aeb  jb      short loc_180031AD5
0x180031aed  mov     rcx, rdi; pSid
0x180031af0  call    cs:__imp_IsValidSid
0x180031af6  test    eax, eax
0x180031af8  jz      short loc_180031AAB
0x180031afa  cmp     qword ptr [r15], 0
0x180031afe  mov     ebp, 2
0x180031b03  mov     dword ptr [rsp+78h+pAclInformation+4], 0
0x180031b0b  jz      short loc_180031B22
0x180031b0d  mov     r9d, ebp; dwAclInformationClass
0x180031b10  lea     r8d, [rbp+0Ah]; nAclInformationLength
0x180031b14  lea     rdx, [rsp+78h+pAclInformation]; pAclInformation
0x180031b19  mov     rcx, r14; pAcl
0x180031b1c  call    cs:__imp_GetAclInformation
0x180031b22  mov     rcx, rdi; pSid
0x180031b25  call    cs:__imp_GetLengthSid
0x180031b2b  mov     ebx, dword ptr [rsp+78h+pAclInformation+4]
0x180031b2f  add     ebx, 10h
0x180031b32  add     ebx, eax
0x180031b34  movsxd  rcx, ebx; unsigned __int64
0x180031b37  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180031b3c  mov     rsi, rax
0x180031b3f  test    rax, rax
0x180031b42  jnz     short loc_180031B4B
0x180031b44  mov     ebx, 8007000Eh
0x180031b49  jmp     short loc_180031BAB
0x180031b4b  mov     r8d, ebp; dwAclRevision
0x180031b4e  mov     edx, ebx; nAclLength
0x180031b50  mov     rcx, rsi; pAcl
0x180031b53  call    cs:__imp_InitializeAcl
0x180031b59  mov     rcx, rsi; pAcl
0x180031b5c  test    eax, eax
0x180031b5e  jnz     short loc_180031B6A
0x180031b60  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180031b65  jmp     loc_180031AAB
0x180031b6a  mov     rdx, r14; PACL
0x180031b6d  call    ?CopyACL@CSecurityDescriptor@@SAJPEAU_ACL@@0@Z; CSecurityDescriptor::CopyACL(_ACL *,_ACL *)
0x180031b72  mov     ebx, eax
0x180031b74  mov     rcx, rsi; pAcl
0x180031b77  test    eax, eax
0x180031b79  jns     short loc_180031B82
0x180031b7b  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180031b80  jmp     short loc_180031BAB
0x180031b82  mov     r9, rdi; pSid
0x180031b85  mov     r8d, r12d; AccessMask
0x180031b88  mov     edx, ebp; dwAceRevision
0x180031b8a  call    cs:__imp_AddAccessAllowedAce
0x180031b90  test    eax, eax
0x180031b92  jnz     short loc_180031B99
0x180031b94  mov     rcx, rsi
0x180031b97  jmp     short loc_180031B60
0x180031b99  mov     [r15], rsi
0x180031b9c  test    r14, r14
0x180031b9f  jz      short loc_180031BA9
0x180031ba1  mov     rcx, r14; Block
0x180031ba4  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180031ba9  xor     ebx, ebx
0x180031bab  mov     rcx, rdi; Block
0x180031bae  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180031bb3  mov     eax, ebx
0x180031bb5  mov     rcx, [rsp+78h+var_48]
0x180031bba  xor     rcx, rsp; StackCookie
0x180031bbd  call    __security_check_cookie
0x180031bc2  add     rsp, 40h
0x180031bc6  pop     r15
0x180031bc8  pop     r14
0x180031bca  pop     r12
0x180031bcc  pop     rdi
0x180031bcd  pop     rsi
0x180031bce  pop     rbp
0x180031bcf  pop     rbx
0x180031bd0  retn
```
