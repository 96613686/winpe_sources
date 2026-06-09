# _anonymous_namespace_::QueryIsAdministrator

- ea: `0x180031fe4`
- end: `0x180032239`
- name: `_anonymous_namespace_::QueryIsAdministrator`
- size: `597`
- prototype: `__int64 __fastcall(HANDLE ClientToken)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003223c`
- `0x180032470`
- `0x1800344b0`

## callees

- `0x180031fe4`
- `0x180049b50`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180032072`
- `KERNEL32!GetLastError` at `0x1800320bd`
- `KERNEL32!GetLastError` at `0x1800321de`
- `KERNEL32!GetLastError` at `0x180032072`
- `KERNEL32!GetLastError` at `0x1800320bd`
- `KERNEL32!GetLastError` at `0x1800321de`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x18003217f`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x18003217f`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x180032172`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x180032172`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x18003215e`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x18003215e`
- `ADVAPI32!AddAccessAllowedAce` at `0x18003212d`
- `ADVAPI32!AddAccessAllowedAce` at `0x18003212d`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180032068`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180032068`
- `ADVAPI32!GetLengthSid` at `0x1800320da`
- `ADVAPI32!GetLengthSid` at `0x1800320da`
- `ADVAPI32!AccessCheck` at `0x1800321d4`
- `ADVAPI32!AccessCheck` at `0x1800321d4`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180032146`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180032146`
- `ADVAPI32!InitializeAcl` at `0x18003210b`
- `ADVAPI32!InitializeAcl` at `0x18003210b`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x1800320b3`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x1800320b3`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180032200`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180032209`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180032200`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180032209`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180032091`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800320e7`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180032091`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800320e7`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::QueryIsAdministrator(HANDLE ClientToken)
{
  __int64 result; // rax
  signed int v3; // ecx
  void *v4; // rax
  void *v5; // rbx
  unsigned int v6; // esi
  signed int v7; // eax
  DWORD v8; // r14d
  ACL *v9; // rax
  ACL *v10; // rdi
  signed int LastError; // eax
  PSID pGroup; // [rsp+60h] [rbp-19h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+68h] [rbp-11h] BYREF
  BOOL AccessStatus; // [rsp+70h] [rbp-9h] BYREF
  DWORD PrivilegeSetLength; // [rsp+74h] [rbp-5h] BYREF
  GENERIC_MAPPING GenericMapping; // [rsp+78h] [rbp-1h] BYREF
  DWORD GrantedAccess; // [rsp+88h] [rbp+Fh] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+90h] [rbp+17h] BYREF

  if ( !ClientToken )
    return 2147942487LL;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &pGroup) )
  {
    v4 = malloc(0x28u);
    v5 = v4;
    if ( v4 )
    {
      if ( InitializeSecurityDescriptor(v4, 1u) )
      {
        v8 = GetLengthSid(pGroup) + 16;
        v9 = (ACL *)malloc(v8);
        v10 = v9;
        if ( v9 )
        {
          if ( InitializeAcl(v9, v8, 2u)
            && AddAccessAllowedAce(v10, 2u, 3u, pGroup)
            && SetSecurityDescriptorDacl(v5, 1, v10, 0)
            && SetSecurityDescriptorGroup(v5, pGroup, 0)
            && SetSecurityDescriptorOwner(v5, pGroup, 0)
            && IsValidSecurityDescriptor(v5)
            && (GenericMapping.GenericRead = 1,
                *(_QWORD *)&GenericMapping.GenericWrite = 2,
                GenericMapping.GenericAll = 3,
                PrivilegeSetLength = 20,
                AccessStatus = 0,
                AccessCheck(
                  v5,
                  ClientToken,
                  3u,
                  &GenericMapping,
                  &PrivilegeSet,
                  &PrivilegeSetLength,
                  &GrantedAccess,
                  &AccessStatus)) )
          {
            v6 = !AccessStatus;
          }
          else
          {
            LastError = GetLastError();
            v6 = (unsigned __int16)LastError | 0x80070000;
            if ( LastError <= 0 )
              v6 = LastError;
          }
        }
        else
        {
          v6 = -2147024882;
        }
        free(v10);
      }
      else
      {
        v7 = GetLastError();
        v6 = (unsigned __int16)v7 | 0x80070000;
        if ( v7 <= 0 )
          v6 = v7;
      }
    }
    else
    {
      v6 = -2147024882;
    }
    free(v5);
    return v6;
  }
  else
  {
    v3 = GetLastError();
    result = (unsigned __int16)v3 | 0x80070000;
    if ( v3 <= 0 )
      return (unsigned int)v3;
  }
  return result;
}

```

## disassembly

```asm
0x180031fe4  mov     [rsp-8+arg_8], rbx
0x180031fe9  mov     [rsp-8+arg_10], rsi
0x180031fee  push    rbp
0x180031fef  push    rdi
0x180031ff0  push    r12
0x180031ff2  push    r14
0x180031ff4  push    r15
0x180031ff6  lea     rbp, [rsp-37h]
0x180031ffb  sub     rsp, 0B0h
0x180032002  mov     rax, cs:__security_cookie
0x180032009  xor     rax, rsp
0x18003200c  mov     [rbp+57h+var_28], rax
0x180032010  xor     r12d, r12d
0x180032013  mov     r15, rcx
0x180032016  test    rcx, rcx
0x180032019  jnz     short loc_180032025
0x18003201b  mov     eax, 80070057h
0x180032020  jmp     loc_180032211
0x180032025  lea     rax, [rbp+57h+pGroup]
0x180032029  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r12d
0x18003202d  mov     [rsp+0D0h+pSid], rax; pSid
0x180032032  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180032036  mov     [rsp+0D0h+nSubAuthority7], r12d; nSubAuthority7
0x18003203b  mov     r9d, 220h; nSubAuthority1
0x180032041  mov     [rsp+0D0h+nSubAuthority6], r12d; nSubAuthority6
0x180032046  mov     r8d, 20h ; ' '; nSubAuthority0
0x18003204c  mov     [rsp+0D0h+nSubAuthority5], r12d; nSubAuthority5
0x180032051  mov     dl, 2; nSubAuthorityCount
0x180032053  mov     [rsp+0D0h+nSubAuthority4], r12d; nSubAuthority4
0x180032058  mov     [rsp+0D0h+nSubAuthority3], r12d; nSubAuthority3
0x18003205d  mov     [rsp+0D0h+nSubAuthority2], r12d; nSubAuthority2
0x180032062  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180032068  call    cs:__imp_AllocateAndInitializeSid
0x18003206e  test    eax, eax
0x180032070  jnz     short loc_18003208C
0x180032072  call    cs:__imp_GetLastError
0x180032078  mov     ecx, eax
0x18003207a  movzx   eax, ax
0x18003207d  or      eax, 80070000h
0x180032082  test    ecx, ecx
0x180032084  cmovle  eax, ecx
0x180032087  jmp     loc_180032211
0x18003208c  mov     ecx, 28h ; '('; Size
0x180032091  call    cs:__imp_malloc
0x180032097  mov     rbx, rax
0x18003209a  test    rax, rax
0x18003209d  jnz     short loc_1800320A9
0x18003209f  mov     esi, 8007000Eh
0x1800320a4  jmp     loc_180032206
0x1800320a9  mov     esi, 1
0x1800320ae  mov     rcx, rbx; pSecurityDescriptor
0x1800320b1  mov     edx, esi; dwRevision
0x1800320b3  call    cs:__imp_InitializeSecurityDescriptor
0x1800320b9  test    eax, eax
0x1800320bb  jnz     short loc_1800320D6
0x1800320bd  call    cs:__imp_GetLastError
0x1800320c3  movzx   esi, ax
0x1800320c6  or      esi, 80070000h
0x1800320cc  test    eax, eax
0x1800320ce  cmovle  esi, eax
0x1800320d1  jmp     loc_180032206
0x1800320d6  mov     rcx, [rbp+57h+pGroup]; pSid
0x1800320da  call    cs:__imp_GetLengthSid
0x1800320e0  lea     r14d, [rax+10h]
0x1800320e4  mov     ecx, r14d; Size
0x1800320e7  call    cs:__imp_malloc
0x1800320ed  mov     rdi, rax
0x1800320f0  test    rax, rax
0x1800320f3  jnz     short loc_1800320FF
0x1800320f5  mov     esi, 8007000Eh
0x1800320fa  jmp     loc_1800321FD
0x1800320ff  mov     r8d, 2; dwAclRevision
0x180032105  mov     edx, r14d; nAclLength
0x180032108  mov     rcx, rdi; pAcl
0x18003210b  call    cs:__imp_InitializeAcl
0x180032111  test    eax, eax
0x180032113  jz      loc_1800321DE
0x180032119  mov     r9, [rbp+57h+pGroup]; pSid
0x18003211d  mov     r14d, 3
0x180032123  mov     r8d, r14d; AccessMask
0x180032126  mov     rcx, rdi; pAcl
0x180032129  lea     edx, [r14-1]; dwAceRevision
0x18003212d  call    cs:__imp_AddAccessAllowedAce
0x180032133  test    eax, eax
0x180032135  jz      loc_1800321DE
0x18003213b  xor     r9d, r9d; bDaclDefaulted
0x18003213e  mov     r8, rdi; pDacl
0x180032141  mov     edx, esi; bDaclPresent
0x180032143  mov     rcx, rbx; pSecurityDescriptor
0x180032146  call    cs:__imp_SetSecurityDescriptorDacl
0x18003214c  test    eax, eax
0x18003214e  jz      loc_1800321DE
0x180032154  mov     rdx, [rbp+57h+pGroup]; pGroup
0x180032158  xor     r8d, r8d; bGroupDefaulted
0x18003215b  mov     rcx, rbx; pSecurityDescriptor
0x18003215e  call    cs:__imp_SetSecurityDescriptorGroup
0x180032164  test    eax, eax
0x180032166  jz      short loc_1800321DE
0x180032168  mov     rdx, [rbp+57h+pGroup]; pOwner
0x18003216c  xor     r8d, r8d; bOwnerDefaulted
0x18003216f  mov     rcx, rbx; pSecurityDescriptor
0x180032172  call    cs:__imp_SetSecurityDescriptorOwner
0x180032178  test    eax, eax
0x18003217a  jz      short loc_1800321DE
0x18003217c  mov     rcx, rbx; pSecurityDescriptor
0x18003217f  call    cs:__imp_IsValidSecurityDescriptor
0x180032185  test    eax, eax
0x180032187  jz      short loc_1800321DE
0x180032189  lea     rax, [rbp+57h+AccessStatus]
0x18003218d  mov     [rbp+57h+GenericMapping.GenericRead], esi
0x180032190  mov     qword ptr [rsp+0D0h+nSubAuthority5], rax; AccessStatus
0x180032195  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x180032199  lea     rax, [rbp+57h+GrantedAccess]
0x18003219d  mov     qword ptr [rbp+57h+GenericMapping.GenericWrite], 2
0x1800321a5  mov     qword ptr [rsp+0D0h+nSubAuthority4], rax; GrantedAccess
0x1800321aa  mov     r8d, r14d; DesiredAccess
0x1800321ad  lea     rax, [rbp+57h+PrivilegeSetLength]
0x1800321b1  mov     [rbp+57h+GenericMapping.GenericAll], r14d
0x1800321b5  mov     qword ptr [rsp+0D0h+nSubAuthority3], rax; PrivilegeSetLength
0x1800321ba  mov     rdx, r15; ClientToken
0x1800321bd  lea     rax, [rbp+57h+PrivilegeSet]
0x1800321c1  mov     [rbp+57h+PrivilegeSetLength], 14h
0x1800321c8  mov     rcx, rbx; pSecurityDescriptor
0x1800321cb  mov     qword ptr [rsp+0D0h+nSubAuthority2], rax; PrivilegeSet
0x1800321d0  mov     [rbp+57h+AccessStatus], r12d
0x1800321d4  call    cs:__imp_AccessCheck
0x1800321da  test    eax, eax
0x1800321dc  jnz     short loc_1800321F4
0x1800321de  call    cs:__imp_GetLastError
0x1800321e4  movzx   esi, ax
0x1800321e7  or      esi, 80070000h
0x1800321ed  test    eax, eax
0x1800321ef  cmovle  esi, eax
0x1800321f2  jmp     short loc_1800321FD
0x1800321f4  cmp     [rbp+57h+AccessStatus], r12d
0x1800321f8  jz      short loc_1800321FD
0x1800321fa  mov     esi, r12d
0x1800321fd  mov     rcx, rdi; Block
0x180032200  call    cs:__imp_free
0x180032206  mov     rcx, rbx; Block
0x180032209  call    cs:__imp_free
0x18003220f  mov     eax, esi
0x180032211  mov     rcx, [rbp+57h+var_28]
0x180032215  xor     rcx, rsp; StackCookie
0x180032218  call    __security_check_cookie
0x18003221d  lea     r11, [rsp+0D0h+var_20]
0x180032225  mov     rbx, [r11+38h]
0x180032229  mov     rsi, [r11+40h]
0x18003222d  mov     rsp, r11
0x180032230  pop     r15
0x180032232  pop     r14
0x180032234  pop     r12
0x180032236  pop     rdi
0x180032237  pop     rbp
0x180032238  retn
```
