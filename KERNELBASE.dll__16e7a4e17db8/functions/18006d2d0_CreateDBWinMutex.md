# CreateDBWinMutex

- ea: `0x18006d2d0`
- end: `0x18006d723`
- name: `CreateDBWinMutex`
- size: `1107`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800c0160`

## callees

- `0x1800134a0`
- `0x18006d2d0`
- `0x18006d730`
- `0x18006d950`
- `0x18006e3f0`
- `0x180188f10`
- `0x180197010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18006d5f1`
- `ntdll!RtlInitUnicodeString` at `0x18006d5f1`
- `ntdll!RtlSetLastWin32Error` at `0x18006d676`
- `ntdll!RtlSetLastWin32Error` at `0x18006d676`
- `ntdll!RtlFreeSid` at `0x18006d69a`
- `ntdll!RtlFreeSid` at `0x18006d6aa`
- `ntdll!RtlFreeSid` at `0x18006d6ba`
- `ntdll!RtlFreeSid` at `0x18006d6ca`
- `ntdll!RtlFreeSid` at `0x18006d69a`
- `ntdll!RtlFreeSid` at `0x18006d6aa`
- `ntdll!RtlFreeSid` at `0x18006d6ba`
- `ntdll!RtlFreeSid` at `0x18006d6ca`
- `ntdll!RtlCreateAcl` at `0x18006d4c1`
- `ntdll!RtlCreateAcl` at `0x18006d57a`
- `ntdll!RtlCreateAcl` at `0x18006d4c1`
- `ntdll!RtlCreateAcl` at `0x18006d57a`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18006d461`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18006d461`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18006d53e`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18006d53e`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18006d37b`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18006d3c3`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18006d405`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18006d44a`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18006d37b`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18006d3c3`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18006d405`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18006d44a`
- `ntdll!RtlLengthSid` at `0x18006d47c`
- `ntdll!RtlLengthSid` at `0x18006d489`
- `ntdll!RtlLengthSid` at `0x18006d496`
- `ntdll!RtlLengthSid` at `0x18006d551`
- `ntdll!RtlLengthSid` at `0x18006d47c`
- `ntdll!RtlLengthSid` at `0x18006d489`
- `ntdll!RtlLengthSid` at `0x18006d496`
- `ntdll!RtlLengthSid` at `0x18006d551`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x18006d5bf`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x18006d5bf`
- `ntdll!RtlAddAccessAllowedAce` at `0x18006d4e2`
- `ntdll!RtlAddAccessAllowedAce` at `0x18006d503`
- `ntdll!RtlAddAccessAllowedAce` at `0x18006d524`
- `ntdll!RtlAddAccessAllowedAce` at `0x18006d4e2`
- `ntdll!RtlAddAccessAllowedAce` at `0x18006d503`
- `ntdll!RtlAddAccessAllowedAce` at `0x18006d524`
- `ntdll!RtlAddMandatoryAce` at `0x18006d5a5`
- `ntdll!RtlAddMandatoryAce` at `0x18006d5a5`
- `ntdll!NtCreateMutant` at `0x18006d65b`
- `ntdll!NtCreateMutant` at `0x18006d65b`

## pseudocode

```c
HANDLE CreateDBWinMutex()
{
  ACL *v0; // rdi
  ACL *v1; // rbx
  HANDLE v2; // r14
  ULONG v3; // esi
  ULONG v4; // esi
  ULONG v5; // esi
  ACL *v6; // rax
  SIZE_T v7; // rsi
  ACL *v8; // rax
  NTSTATUS NamedObjectDirectory; // eax
  ULONG v10; // ecx
  void *SubAuthority3; // [rsp+30h] [rbp-D8h]
  PSID Sid; // [rsp+68h] [rbp-A0h] BYREF
  PSID v14; // [rsp+70h] [rbp-98h] BYREF
  PSID v15; // [rsp+78h] [rbp-90h] BYREF
  PSID v16; // [rsp+80h] [rbp-88h] BYREF
  void *v17; // [rsp+88h] [rbp-80h] BYREF
  HANDLE MutantHandle; // [rsp+90h] [rbp-78h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-70h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+C8h] [rbp-40h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v22; // [rsp+F8h] [rbp-10h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+100h] [rbp-8h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v24; // [rsp+108h] [rbp+0h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v25; // [rsp+110h] [rbp+8h] BYREF

  v22 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_DWORD *)v24.Value = 0;
  *(_DWORD *)v25.Value = 0;
  v0 = 0;
  v1 = 0;
  v2 = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *(_WORD *)&v24.Value[4] = 256;
  *(_WORD *)&v25.Value[4] = 4096;
  Sid = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  if ( RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &Sid) >= 0
    && RtlAllocateAndInitializeSid(&IdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &v14) >= 0
    && RtlAllocateAndInitializeSid(&v24, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &v15) >= 0
    && RtlAllocateAndInitializeSid(&v25, 1u, 0x1000u, 0, 0, 0, 0, 0, 0, 0, &v16) >= 0
    && RtlCreateSecurityDescriptor(SecurityDescriptor, 1u) >= 0 )
  {
    v3 = RtlLengthSid(v15);
    v4 = RtlLengthSid(v14) + v3;
    v5 = RtlLengthSid(Sid) + 32 + v4;
    v6 = (ACL *)GlobalAlloc(0, v5);
    v0 = v6;
    if ( v6 )
    {
      if ( RtlCreateAcl(v6, v5, 2u) >= 0
        && RtlAddAccessAllowedAce(v0, 2u, 0x120001u, v15) >= 0
        && RtlAddAccessAllowedAce(v0, 2u, 0x1F0001u, Sid) >= 0
        && RtlAddAccessAllowedAce(v0, 2u, 0x1F0001u, v14) >= 0
        && RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v0, 0) >= 0 )
      {
        v7 = RtlLengthSid(v16) + 16;
        v8 = (ACL *)GlobalAlloc(0, v7);
        v1 = v8;
        if ( v8 )
        {
          if ( RtlCreateAcl(v8, v7, 2u) >= 0 )
          {
            LODWORD(SubAuthority3) = 1;
            if ( RtlAddMandatoryAce(v1, 2u, 0, (ULONG)v16, 0x11u, SubAuthority3) >= 0
              && RtlSetSaclSecurityDescriptor(SecurityDescriptor, 1u, v1, 0) >= 0 )
            {
              MutantHandle = 0;
              memset(&ObjectAttributes, 0, 44);
              DestinationString = 0;
              RtlInitUnicodeString(&DestinationString, L"DBWinMutex");
              v17 = 0;
              NamedObjectDirectory = BaseGetNamedObjectDirectory(&v17);
              if ( NamedObjectDirectory < 0 )
                goto LABEL_37;
              ObjectAttributes.RootDirectory = v17;
              ObjectAttributes.ObjectName = &DestinationString;
              ObjectAttributes.SecurityDescriptor = SecurityDescriptor;
              ObjectAttributes.Length = 48;
              ObjectAttributes.Attributes = 128;
              ObjectAttributes.SecurityQualityOfService = 0;
              if ( pfnAdjustObjectAttributesForPrivateNamespace )
                pfnAdjustObjectAttributesForPrivateNamespace(&ObjectAttributes);
              NamedObjectDirectory = NtCreateMutant(&MutantHandle, 0x2120001u, &ObjectAttributes, 0);
              if ( NamedObjectDirectory < 0 )
              {
LABEL_37:
                BaseSetLastNTError((unsigned int)NamedObjectDirectory);
              }
              else
              {
                if ( NamedObjectDirectory == 0x40000000 )
                  v10 = 183;
                else
                  v10 = 0;
                RtlSetLastWin32Error(v10);
                v2 = MutantHandle;
              }
            }
          }
        }
      }
    }
  }
  if ( Sid )
    RtlFreeSid(Sid);
  if ( v14 )
    RtlFreeSid(v14);
  if ( v15 )
    RtlFreeSid(v15);
  if ( v16 )
    RtlFreeSid(v16);
  if ( v0 )
    GlobalFree(v0);
  if ( v1 )
    GlobalFree(v1);
  return v2;
}

```

## disassembly

```asm
0x18006d2d0  mov     r11, rsp
0x18006d2d3  push    rbp
0x18006d2d4  push    rbx
0x18006d2d5  push    r14
0x18006d2d7  lea     rbp, [r11-38h]
0x18006d2db  sub     rsp, 120h
0x18006d2e2  mov     rax, cs:__security_cookie
0x18006d2e9  xor     rax, rsp
0x18006d2ec  mov     [rbp+30h+var_20], rax
0x18006d2f0  xor     eax, eax
0x18006d2f2  mov     [r11+10h], rdi
0x18006d2f6  xorps   xmm0, xmm0
0x18006d2f9  mov     [rbp+30h+var_40], rax
0x18006d2fd  mov     dword ptr [rbp+30h+IdentifierAuthority.Value], eax
0x18006d300  lea     rcx, [rbp+30h+IdentifierAuthority]; IdentifierAuthority
0x18006d304  mov     dword ptr [rbp+30h+var_30.Value], eax
0x18006d307  xor     r9d, r9d; SubAuthority1
0x18006d30a  mov     dword ptr [rbp+30h+var_28.Value], eax
0x18006d30d  mov     r8d, 12h; SubAuthority0
0x18006d313  lea     rax, [rsp+130h+Sid]
0x18006d318  mov     [r11+18h], r15
0x18006d31c  xor     r15d, r15d
0x18006d31f  mov     [rsp+50h], rax; Sid
0x18006d324  mov     [rsp+130h+SubAuthority7], r15d; SubAuthority7
0x18006d329  mov     dl, 1; SubAuthorityCount
0x18006d32b  mov     [rsp+130h+SubAuthority6], r15d; SubAuthority6
0x18006d330  mov     edi, r15d
0x18006d333  mov     [rsp+130h+SubAuthority5], r15d; SubAuthority5
0x18006d338  mov     ebx, r15d
0x18006d33b  mov     [rsp+130h+SubAuthority4], r15d; SubAuthority4
0x18006d340  mov     r14d, r15d
0x18006d343  mov     dword ptr [rsp+130h+SubAuthority3], r15d; SubAuthority3
0x18006d348  mov     [rsp+130h+SubAuthority2], r15d; SubAuthority2
0x18006d34d  movups  [rbp+30h+SecurityDescriptor], xmm0
0x18006d351  mov     word ptr [rbp+30h+IdentifierAuthority.Value+4], 500h
0x18006d357  movups  [rbp+30h+var_50], xmm0
0x18006d35b  mov     word ptr [rbp+30h+var_30.Value+4], 100h
0x18006d361  mov     word ptr [rbp+30h+var_28.Value+4], 1000h
0x18006d367  mov     [rsp+130h+Sid], r15
0x18006d36c  mov     [rsp+130h+var_C8], r15
0x18006d371  mov     [rsp+130h+var_C0], r15
0x18006d376  mov     [rsp+130h+var_B8], r15
0x18006d37b  call    cs:__imp_RtlAllocateAndInitializeSid
0x18006d381  test    eax, eax
0x18006d383  js      loc_18006D688
0x18006d389  lea     rax, [rsp+130h+var_C8]
0x18006d38e  mov     r9d, 220h; SubAuthority1
0x18006d394  mov     [rsp+50h], rax; Sid
0x18006d399  lea     rcx, [rbp+30h+IdentifierAuthority]; IdentifierAuthority
0x18006d39d  mov     [rsp+130h+SubAuthority7], r15d; SubAuthority7
0x18006d3a2  mov     r8d, 20h ; ' '; SubAuthority0
0x18006d3a8  mov     [rsp+130h+SubAuthority6], r15d; SubAuthority6
0x18006d3ad  mov     dl, 2; SubAuthorityCount
0x18006d3af  mov     [rsp+130h+SubAuthority5], r15d; SubAuthority5
0x18006d3b4  mov     [rsp+130h+SubAuthority4], r15d; SubAuthority4
0x18006d3b9  mov     dword ptr [rsp+130h+SubAuthority3], r15d; SubAuthority3
0x18006d3be  mov     [rsp+130h+SubAuthority2], r15d; SubAuthority2
0x18006d3c3  call    cs:__imp_RtlAllocateAndInitializeSid
0x18006d3c9  test    eax, eax
0x18006d3cb  js      loc_18006D688
0x18006d3d1  lea     rax, [rsp+130h+var_C0]
0x18006d3d6  xor     r9d, r9d; SubAuthority1
0x18006d3d9  mov     [rsp+50h], rax; Sid
0x18006d3de  lea     rcx, [rbp+30h+var_30]; IdentifierAuthority
0x18006d3e2  mov     [rsp+130h+SubAuthority7], r15d; SubAuthority7
0x18006d3e7  xor     r8d, r8d; SubAuthority0
0x18006d3ea  mov     [rsp+130h+SubAuthority6], r15d; SubAuthority6
0x18006d3ef  mov     dl, 1; SubAuthorityCount
0x18006d3f1  mov     [rsp+130h+SubAuthority5], r15d; SubAuthority5
0x18006d3f6  mov     [rsp+130h+SubAuthority4], r15d; SubAuthority4
0x18006d3fb  mov     dword ptr [rsp+130h+SubAuthority3], r15d; SubAuthority3
0x18006d400  mov     [rsp+130h+SubAuthority2], r15d; SubAuthority2
0x18006d405  call    cs:__imp_RtlAllocateAndInitializeSid
0x18006d40b  test    eax, eax
0x18006d40d  js      loc_18006D688
0x18006d413  lea     rax, [rsp+130h+var_B8]
0x18006d418  xor     r9d, r9d; SubAuthority1
0x18006d41b  mov     [rsp+50h], rax; Sid
0x18006d420  lea     rcx, [rbp+30h+var_28]; IdentifierAuthority
0x18006d424  mov     [rsp+130h+SubAuthority7], r15d; SubAuthority7
0x18006d429  mov     r8d, 1000h; SubAuthority0
0x18006d42f  mov     [rsp+130h+SubAuthority6], r15d; SubAuthority6
0x18006d434  mov     dl, 1; SubAuthorityCount
0x18006d436  mov     [rsp+130h+SubAuthority5], r15d; SubAuthority5
0x18006d43b  mov     [rsp+130h+SubAuthority4], r15d; SubAuthority4
0x18006d440  mov     dword ptr [rsp+130h+SubAuthority3], r15d; SubAuthority3
0x18006d445  mov     [rsp+130h+SubAuthority2], r15d; SubAuthority2
0x18006d44a  call    cs:__imp_RtlAllocateAndInitializeSid
0x18006d450  test    eax, eax
0x18006d452  js      loc_18006D688
0x18006d458  mov     edx, 1; Revision
0x18006d45d  lea     rcx, [rbp+30h+SecurityDescriptor]; SecurityDescriptor
0x18006d461  call    cs:__imp_RtlCreateSecurityDescriptor
0x18006d467  test    eax, eax
0x18006d469  js      loc_18006D688
0x18006d46f  mov     rcx, [rsp+130h+var_C0]; Sid
0x18006d474  mov     [rsp+130h+arg_0], rsi
0x18006d47c  call    cs:__imp_RtlLengthSid
0x18006d482  mov     rcx, [rsp+130h+var_C8]; Sid
0x18006d487  mov     esi, eax
0x18006d489  call    cs:__imp_RtlLengthSid
0x18006d48f  mov     rcx, [rsp+130h+Sid]; Sid
0x18006d494  add     esi, eax
0x18006d496  call    cs:__imp_RtlLengthSid
0x18006d49c  add     eax, 20h ; ' '
0x18006d49f  xor     ecx, ecx; uFlags
0x18006d4a1  add     esi, eax
0x18006d4a3  mov     edx, esi; dwBytes
0x18006d4a5  call    GlobalAlloc
0x18006d4aa  mov     rdi, rax
0x18006d4ad  test    rax, rax
0x18006d4b0  jz      loc_18006D680
0x18006d4b6  mov     r8d, 2; AclRevision
0x18006d4bc  mov     edx, esi; AclSize
0x18006d4be  mov     rcx, rax; Acl
0x18006d4c1  call    cs:__imp_RtlCreateAcl
0x18006d4c7  test    eax, eax
0x18006d4c9  js      loc_18006D680
0x18006d4cf  mov     r9, [rsp+130h+var_C0]; Sid
0x18006d4d4  mov     edx, 2; Revision
0x18006d4d9  mov     r8d, 120001h; AccessMask
0x18006d4df  mov     rcx, rdi; Acl
0x18006d4e2  call    cs:__imp_RtlAddAccessAllowedAce
0x18006d4e8  test    eax, eax
0x18006d4ea  js      loc_18006D680
0x18006d4f0  mov     r9, [rsp+130h+Sid]; Sid
0x18006d4f5  mov     edx, 2; Revision
0x18006d4fa  mov     r8d, 1F0001h; AccessMask
0x18006d500  mov     rcx, rdi; Acl
0x18006d503  call    cs:__imp_RtlAddAccessAllowedAce
0x18006d509  test    eax, eax
0x18006d50b  js      loc_18006D680
0x18006d511  mov     r9, [rsp+130h+var_C8]; Sid
0x18006d516  mov     edx, 2; Revision
0x18006d51b  mov     r8d, 1F0001h; AccessMask
0x18006d521  mov     rcx, rdi; Acl
0x18006d524  call    cs:__imp_RtlAddAccessAllowedAce
0x18006d52a  test    eax, eax
0x18006d52c  js      loc_18006D680
0x18006d532  xor     r9d, r9d; DaclDefaulted
0x18006d535  lea     rcx, [rbp+30h+SecurityDescriptor]; SecurityDescriptor
0x18006d539  mov     r8, rdi; Dacl
0x18006d53c  mov     dl, 1; DaclPresent
0x18006d53e  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x18006d544  test    eax, eax
0x18006d546  js      loc_18006D680
0x18006d54c  mov     rcx, [rsp+130h+var_B8]; Sid
0x18006d551  call    cs:__imp_RtlLengthSid
0x18006d557  xor     ecx, ecx; uFlags
0x18006d559  lea     esi, [rax+10h]
0x18006d55c  mov     edx, esi; dwBytes
0x18006d55e  call    GlobalAlloc
0x18006d563  mov     rbx, rax
0x18006d566  test    rax, rax
0x18006d569  jz      loc_18006D680
0x18006d56f  mov     r8d, 2; AclRevision
0x18006d575  mov     edx, esi; AclSize
0x18006d577  mov     rcx, rax; Acl
0x18006d57a  call    cs:__imp_RtlCreateAcl
0x18006d580  test    eax, eax
0x18006d582  js      loc_18006D680
0x18006d588  mov     r9, [rsp+130h+var_B8]; MandatoryFlags
0x18006d58d  xor     r8d, r8d; Flags
0x18006d590  mov     dword ptr [rsp+130h+SubAuthority3], 1; LabelSid
0x18006d598  mov     edx, 2; Revision
0x18006d59d  mov     rcx, rbx; Acl
0x18006d5a0  mov     byte ptr [rsp+130h+SubAuthority2], 11h; AceType
0x18006d5a5  call    cs:__imp_RtlAddMandatoryAce
0x18006d5ab  test    eax, eax
0x18006d5ad  js      loc_18006D680
0x18006d5b3  xor     r9d, r9d; SaclDefaulted
0x18006d5b6  lea     rcx, [rbp+30h+SecurityDescriptor]; SecurityDescriptor
0x18006d5ba  mov     r8, rbx; Sacl
0x18006d5bd  mov     dl, 1; SaclPresent
0x18006d5bf  call    cs:__imp_RtlSetSaclSecurityDescriptor
0x18006d5c5  test    eax, eax
0x18006d5c7  js      loc_18006D680
0x18006d5cd  xorps   xmm0, xmm0
0x18006d5d0  mov     [rbp+30h+MutantHandle], r15
0x18006d5d4  movups  xmmword ptr [rbp+30h+ObjectAttributes.ObjectName], xmm0
0x18006d5d8  xor     eax, eax
0x18006d5da  lea     rdx, aDbwinmutex; "DBWinMutex"
0x18006d5e1  lea     rcx, [rbp+30h+DestinationString]; DestinationString
0x18006d5e5  movups  xmmword ptr [rbp+30h+ObjectAttributes+1Ch], xmm0
0x18006d5e9  movups  xmmword ptr [rbp+30h+ObjectAttributes.Length], xmm0
0x18006d5ed  movups  xmmword ptr [rbp+30h+DestinationString.Length], xmm0
0x18006d5f1  call    cs:__imp_RtlInitUnicodeString
0x18006d5f7  lea     rcx, [rbp+30h+var_B0]
0x18006d5fb  mov     [rbp+30h+var_B0], r15
0x18006d5ff  call    BaseGetNamedObjectDirectory
0x18006d604  test    eax, eax
0x18006d606  js      loc_18006D717
0x18006d60c  mov     rax, [rbp+30h+var_B0]
0x18006d610  mov     [rbp+30h+ObjectAttributes.RootDirectory], rax
0x18006d614  lea     rax, [rbp+30h+DestinationString]
0x18006d618  mov     [rbp+30h+ObjectAttributes.ObjectName], rax
0x18006d61c  lea     rax, [rbp+30h+SecurityDescriptor]
0x18006d620  mov     [rbp+30h+ObjectAttributes.SecurityDescriptor], rax
0x18006d624  mov     rax, cs:pfnAdjustObjectAttributesForPrivateNamespace
0x18006d62b  mov     [rbp+30h+ObjectAttributes.Length], 30h ; '0'
0x18006d632  mov     [rbp+30h+ObjectAttributes.Attributes], 80h
0x18006d639  mov     [rbp+30h+ObjectAttributes.SecurityQualityOfService], r15
0x18006d63d  test    rax, rax
0x18006d640  jz      short loc_18006D64B
0x18006d642  lea     rcx, [rbp+30h+ObjectAttributes]
0x18006d646  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d64b  lea     r8, [rbp+30h+ObjectAttributes]; ObjectAttributes
0x18006d64f  xor     r9d, r9d; InitialOwner
0x18006d652  mov     edx, 2120001h; DesiredAccess
0x18006d657  lea     rcx, [rbp+30h+MutantHandle]; MutantHandle
0x18006d65b  call    cs:__imp_NtCreateMutant
0x18006d661  test    eax, eax
0x18006d663  js      loc_18006D717
0x18006d669  cmp     eax, 40000000h
0x18006d66e  jz      loc_18006D70D
0x18006d674  xor     ecx, ecx; LastError
0x18006d676  call    cs:__imp_RtlSetLastWin32Error
0x18006d67c  mov     r14, [rbp+30h+MutantHandle]
0x18006d680  mov     rsi, [rsp+130h+arg_0]
0x18006d688  mov     rcx, [rsp+130h+Sid]; Sid
0x18006d68d  mov     r15, [rsp+130h+arg_10]
0x18006d695  test    rcx, rcx
0x18006d698  jz      short loc_18006D6A0
0x18006d69a  call    cs:__imp_RtlFreeSid
0x18006d6a0  mov     rcx, [rsp+130h+var_C8]; Sid
0x18006d6a5  test    rcx, rcx
0x18006d6a8  jz      short loc_18006D6B0
0x18006d6aa  call    cs:__imp_RtlFreeSid
0x18006d6b0  mov     rcx, [rsp+130h+var_C0]; Sid
0x18006d6b5  test    rcx, rcx
0x18006d6b8  jz      short loc_18006D6C0
0x18006d6ba  call    cs:__imp_RtlFreeSid
0x18006d6c0  mov     rcx, [rsp+130h+var_B8]; Sid
0x18006d6c5  test    rcx, rcx
0x18006d6c8  jz      short loc_18006D6D0
0x18006d6ca  call    cs:__imp_RtlFreeSid
0x18006d6d0  test    rdi, rdi
0x18006d6d3  jz      short loc_18006D6DD
0x18006d6d5  mov     rcx, rdi; hMem
0x18006d6d8  call    GlobalFree
0x18006d6dd  mov     rdi, [rsp+130h+arg_8]
0x18006d6e5  test    rbx, rbx
0x18006d6e8  jz      short loc_18006D6F2
0x18006d6ea  mov     rcx, rbx; hMem
0x18006d6ed  call    GlobalFree
0x18006d6f2  mov     rax, r14
0x18006d6f5  mov     rcx, [rbp+30h+var_20]
0x18006d6f9  xor     rcx, rsp; StackCookie
0x18006d6fc  call    __security_check_cookie
0x18006d701  add     rsp, 120h
0x18006d708  pop     r14
0x18006d70a  pop     rbx
0x18006d70b  pop     rbp
0x18006d70c  retn
0x18006d70d  mov     ecx, 0B7h
0x18006d712  jmp     loc_18006D676
0x18006d717  mov     ecx, eax
0x18006d719  call    BaseSetLastNTError
0x18006d71e  jmp     loc_18006D680
```
