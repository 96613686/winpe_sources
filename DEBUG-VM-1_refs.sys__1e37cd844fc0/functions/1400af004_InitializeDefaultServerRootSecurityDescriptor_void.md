# InitializeDefaultServerRootSecurityDescriptor(void)

- ea: `0x1400af004`
- end: `0x1400af67d`
- name: `?InitializeDefaultServerRootSecurityDescriptor@@YAXXZ`
- size: `1657`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14034f36c`

## callees

- `0x1400862c0`
- `0x1400af004`
- `0x1400d0fd8`
- `0x1401f3fc0`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x1400af64c`
- `ntoskrnl!ExRaiseStatus` at `0x1400af64c`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400af0be`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400af0be`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400af55d`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1401f5bb8`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400af55d`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1401f5bb8`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400af4fd`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400af4fd`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400af0d2`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400af148`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400af1aa`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400af209`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400af282`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400af0d2`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400af148`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400af1aa`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400af209`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400af282`
- `ntoskrnl!RtlInitializeSid` at `0x1400af10e`
- `ntoskrnl!RtlInitializeSid` at `0x1400af184`
- `ntoskrnl!RtlInitializeSid` at `0x1400af1e6`
- `ntoskrnl!RtlInitializeSid` at `0x1400af245`
- `ntoskrnl!RtlInitializeSid` at `0x1400af2be`
- `ntoskrnl!RtlInitializeSid` at `0x1400af10e`
- `ntoskrnl!RtlInitializeSid` at `0x1400af184`
- `ntoskrnl!RtlInitializeSid` at `0x1400af1e6`
- `ntoskrnl!RtlInitializeSid` at `0x1400af245`
- `ntoskrnl!RtlInitializeSid` at `0x1400af2be`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400af11f`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400af133`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400af195`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400af1f7`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400af256`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400af26e`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400af2cf`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400af11f`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400af133`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400af195`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400af1f7`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400af256`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400af26e`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400af2cf`
- `ntoskrnl!RtlCreateAcl` at `0x1400af336`
- `ntoskrnl!RtlCreateAcl` at `0x1400af336`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400af4b7`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400af4b7`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400af4e1`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400af4e1`
- `ntoskrnl!SeAssignSecurity` at `0x1400af52b`
- `ntoskrnl!SeAssignSecurity` at `0x1400af52b`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1400af548`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1400af548`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400af367`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400af398`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400af3c9`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400af3fa`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400af42a`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400af45a`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400af490`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400af367`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400af398`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400af3c9`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400af3fa`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400af42a`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400af45a`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400af490`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400af573`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400af589`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400af59a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400af5ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400af5bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400af5cf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400af5e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f5bd0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f5be8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f5c00`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f5c18`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f5c30`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f5c48`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f5c60`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400af573`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400af589`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400af59a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400af5ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400af5bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400af5cf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400af5e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f5bd0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f5be8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f5c00`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f5c18`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f5c30`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f5c48`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f5c60`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400af0a7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400af0ec`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400af162`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400af1c4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400af223`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400af29c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400af317`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400af0a7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400af0ec`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400af162`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400af1c4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400af223`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400af29c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400af317`

## pseudocode

```c
void InitializeDefaultServerRootSecurityDescriptor(void)
{
  struct _SECURITY_SUBJECT_CONTEXT *PoolWithTag; // rsi
  ULONG v1; // eax
  unsigned __int8 *Sid; // r15
  ULONG v3; // eax
  unsigned __int8 *v4; // r12
  ULONG v5; // eax
  unsigned __int8 *v6; // r13
  ULONG v7; // eax
  unsigned __int8 *v8; // r14
  ULONG v9; // eax
  ULONG v10; // ebx
  struct _ACL *v11; // rdi
  int Acl; // ebx
  POOL_TYPE PoolType; // ebx
  struct _GENERIC_MAPPING *GenericMapping; // rax
  unsigned __int8 *P; // [rsp+48h] [rbp-C0h]
  _OWORD SecurityDescriptor[2]; // [rsp+80h] [rbp-88h] BYREF
  __int64 v17; // [rsp+A0h] [rbp-68h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+A8h] [rbp-60h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v19; // [rsp+B0h] [rbp-58h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v20; // [rsp+B8h] [rbp-50h] BYREF

  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v17 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)v19.Value = 0;
  *(_WORD *)&v19.Value[4] = 768;
  *(_DWORD *)v20.Value = 0;
  *(_WORD *)&v20.Value[4] = 256;
  PoolWithTag = (struct _SECURITY_SUBJECT_CONTEXT *)ExAllocatePoolWithTag(
                                                      (POOL_TYPE)(::PoolType | 0x10),
                                                      0x20u,
                                                      0x4A666552u);
  SeCaptureSubjectContext(PoolWithTag);
  v1 = RtlLengthRequiredSid(2u);
  Sid = (unsigned __int8 *)ExAllocatePoolWithTag((POOL_TYPE)(::PoolType | 0x10), v1, 0x4A666552u);
  RtlInitializeSid(Sid, &IdentifierAuthority, 2u);
  *RtlSubAuthoritySid(Sid, 0) = 32;
  *RtlSubAuthoritySid(Sid, 1u) = 544;
  v3 = RtlLengthRequiredSid(1u);
  v4 = (unsigned __int8 *)ExAllocatePoolWithTag((POOL_TYPE)(::PoolType | 0x10), v3, 0x4A666552u);
  RtlInitializeSid(v4, &IdentifierAuthority, 1u);
  *RtlSubAuthoritySid(v4, 0) = 18;
  v5 = RtlLengthRequiredSid(1u);
  v6 = (unsigned __int8 *)ExAllocatePoolWithTag((POOL_TYPE)(::PoolType | 0x10), v5, 0x4A666552u);
  RtlInitializeSid(v6, &v19, 1u);
  *RtlSubAuthoritySid(v6, 0) = 0;
  v7 = RtlLengthRequiredSid(2u);
  v8 = (unsigned __int8 *)ExAllocatePoolWithTag((POOL_TYPE)(::PoolType | 0x10), v7, 0x4A666552u);
  RtlInitializeSid(v8, &IdentifierAuthority, 2u);
  *RtlSubAuthoritySid(v8, 0) = 32;
  *RtlSubAuthoritySid(v8, 1u) = 545;
  v9 = RtlLengthRequiredSid(1u);
  P = (unsigned __int8 *)ExAllocatePoolWithTag((POOL_TYPE)(::PoolType | 0x10), v9, 0x4A666552u);
  RtlInitializeSid(P, &v20, 1u);
  *RtlSubAuthoritySid(P, 0) = 0;
  v10 = 4 * (Sid[1] + v4[1] + v6[1] + v8[1] + P[1]) + 232;
  v11 = (struct _ACL *)ExAllocatePoolWithTag((POOL_TYPE)(::PoolType | 0x10), v10, 0x4A666552u);
  Acl = RtlCreateAcl(v11, v10, 2u);
  if ( Acl >= 0 )
  {
    Acl = RtlAddAccessAllowedAceEx(v11, 2u, 3u, 0x10000000u, Sid);
    if ( Acl >= 0 )
    {
      Acl = RtlAddAccessAllowedAceEx(v11, 2u, 3u, 0x10000000u, v4);
      if ( Acl >= 0 )
      {
        Acl = RtlAddAccessAllowedAceEx(v11, 2u, 0xBu, 0x10000000u, v6);
        if ( Acl >= 0 )
        {
          Acl = RtlAddAccessAllowedAceEx(v11, 2u, 3u, 0x80100020, v8);
          if ( Acl >= 0 )
          {
            Acl = RtlAddAccessAllowedAceEx(v11, 2u, 2u, 4u, v8);
            if ( Acl >= 0 )
            {
              Acl = RtlAddAccessAllowedAceEx(v11, 2u, 3u, 2u, v8);
              if ( Acl >= 0 )
              {
                Acl = RtlAddAccessAllowedAceEx(v11, 2u, 3u, 0x80100020, P);
                if ( Acl >= 0 )
                {
                  Acl = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
                  if ( Acl >= 0 )
                  {
                    Acl = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v11, 0);
                    if ( Acl >= 0 )
                    {
                      PoolType = ::PoolType;
                      GenericMapping = IoGetFileObjectGenericMapping();
                      Acl = SeAssignSecurity(
                              0,
                              SecurityDescriptor,
                              &ModificationDescriptor,
                              0,
                              PoolWithTag,
                              GenericMapping,
                              PoolType);
                      if ( Acl >= 0 )
                        dword_1402682C8 = RtlLengthSecurityDescriptor(ModificationDescriptor);
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  SeReleaseSubjectContext(PoolWithTag);
  if ( PoolWithTag )
    ExFreePoolWithTag(PoolWithTag, 0);
  if ( v11 )
    ExFreePoolWithTag(v11, 0);
  ExFreePoolWithTag(Sid, 0);
  ExFreePoolWithTag(v4, 0);
  ExFreePoolWithTag(v6, 0);
  ExFreePoolWithTag(P, 0);
  ExFreePoolWithTag(v8, 0);
  if ( Acl < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        23,
        &WPP_823e6dba7932309d1ad2e841189c99ac_Traceguids,
        (unsigned int)Acl);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(Acl, 0, "NtfsInit.c", 0x1907u);
    ExRaiseStatus(Acl);
  }
}

```

## disassembly

```asm
0x1400af004  mov     r11, rsp
0x1400af007  push    rbx
0x1400af008  push    rsi
0x1400af009  push    rdi
0x1400af00a  push    r12
0x1400af00c  push    r13
0x1400af00e  push    r14
0x1400af010  push    r15
0x1400af012  sub     rsp, 0D0h
0x1400af019  mov     rax, cs:__security_cookie
0x1400af020  xor     rax, rsp
0x1400af023  mov     [rsp+108h+var_48], rax
0x1400af02b  xor     r14d, r14d
0x1400af02e  mov     [rsp+108h+var_B8], r14
0x1400af033  mov     [rsp+108h+var_C8], r14b
0x1400af038  mov     [rsp+108h+var_B0], r14
0x1400af03d  mov     [rsp+108h+var_A8], r14
0x1400af042  mov     [rsp+108h+var_A0], r14
0x1400af047  mov     [rsp+108h+var_98], r14
0x1400af04c  mov     [rsp+108h+var_90], r14
0x1400af051  mov     [rsp+108h+P], r14
0x1400af056  xorps   xmm0, xmm0
0x1400af059  xor     eax, eax
0x1400af05b  movups  [rsp+108h+SecurityDescriptor], xmm0
0x1400af063  movups  xmmword ptr [r11-78h], xmm0
0x1400af068  mov     [r11-68h], rax
0x1400af06c  mov     [r11-60h], r14d
0x1400af070  mov     word ptr [r11-5Ch], 500h
0x1400af077  mov     [r11-58h], r14d
0x1400af07b  mov     word ptr [r11-54h], 300h
0x1400af082  mov     [r11-50h], r14d
0x1400af086  mov     word ptr [r11-4Ch], 100h
0x1400af08d  lea     r13d, [r14+1]
0x1400af091  mov     ecx, cs:PoolType
0x1400af097  or      ecx, 10h; PoolType
0x1400af09a  mov     edi, 4A666552h
0x1400af09f  mov     r8d, edi; Tag
0x1400af0a2  lea     ebx, [rax+20h]
0x1400af0a5  mov     edx, ebx; NumberOfBytes
0x1400af0a7  call    cs:__imp_ExAllocatePoolWithTag
0x1400af0ae  nop     dword ptr [rax+rax+00h]
0x1400af0b3  mov     rsi, rax
0x1400af0b6  mov     [rsp+108h+var_B8], rax
0x1400af0bb  mov     rcx, rax; SubjectContext
0x1400af0be  call    cs:__imp_SeCaptureSubjectContext
0x1400af0c5  nop     dword ptr [rax+rax+00h]
0x1400af0ca  mov     [rsp+108h+var_C8], r13b
0x1400af0cf  lea     ecx, [rbx-1Eh]; SubAuthorityCount
0x1400af0d2  call    cs:__imp_RtlLengthRequiredSid
0x1400af0d9  nop     dword ptr [rax+rax+00h]
0x1400af0de  mov     edx, eax; NumberOfBytes
0x1400af0e0  mov     ecx, cs:PoolType
0x1400af0e6  or      ecx, 10h; PoolType
0x1400af0e9  mov     r8d, edi; Tag
0x1400af0ec  call    cs:__imp_ExAllocatePoolWithTag
0x1400af0f3  nop     dword ptr [rax+rax+00h]
0x1400af0f8  mov     r15, rax
0x1400af0fb  mov     [rsp+108h+var_A8], rax
0x1400af100  mov     r8b, 2; SubAuthorityCount
0x1400af103  lea     rdx, [rsp+108h+IdentifierAuthority]; IdentifierAuthority
0x1400af10b  mov     rcx, rax; Sid
0x1400af10e  call    cs:__imp_RtlInitializeSid
0x1400af115  nop     dword ptr [rax+rax+00h]
0x1400af11a  xor     edx, edx; SubAuthority
0x1400af11c  mov     rcx, r15; Sid
0x1400af11f  call    cs:__imp_RtlSubAuthoritySid
0x1400af126  nop     dword ptr [rax+rax+00h]
0x1400af12b  mov     [rax], ebx
0x1400af12d  mov     edx, r13d; SubAuthority
0x1400af130  mov     rcx, r15; Sid
0x1400af133  call    cs:__imp_RtlSubAuthoritySid
0x1400af13a  nop     dword ptr [rax+rax+00h]
0x1400af13f  mov     dword ptr [rax], 220h
0x1400af145  mov     ecx, r13d; SubAuthorityCount
0x1400af148  call    cs:__imp_RtlLengthRequiredSid
0x1400af14f  nop     dword ptr [rax+rax+00h]
0x1400af154  mov     edx, eax; NumberOfBytes
0x1400af156  mov     ecx, cs:PoolType
0x1400af15c  or      ecx, 10h; PoolType
0x1400af15f  mov     r8d, edi; Tag
0x1400af162  call    cs:__imp_ExAllocatePoolWithTag
0x1400af169  nop     dword ptr [rax+rax+00h]
0x1400af16e  mov     r12, rax
0x1400af171  mov     [rsp+108h+var_A0], rax
0x1400af176  mov     r8b, r13b; SubAuthorityCount
0x1400af179  lea     rdx, [rsp+108h+IdentifierAuthority]; IdentifierAuthority
0x1400af181  mov     rcx, rax; Sid
0x1400af184  call    cs:__imp_RtlInitializeSid
0x1400af18b  nop     dword ptr [rax+rax+00h]
0x1400af190  xor     edx, edx; SubAuthority
0x1400af192  mov     rcx, r12; Sid
0x1400af195  call    cs:__imp_RtlSubAuthoritySid
0x1400af19c  nop     dword ptr [rax+rax+00h]
0x1400af1a1  mov     dword ptr [rax], 12h
0x1400af1a7  mov     ecx, r13d; SubAuthorityCount
0x1400af1aa  call    cs:__imp_RtlLengthRequiredSid
0x1400af1b1  nop     dword ptr [rax+rax+00h]
0x1400af1b6  mov     edx, eax; NumberOfBytes
0x1400af1b8  mov     ecx, cs:PoolType
0x1400af1be  or      ecx, 10h; PoolType
0x1400af1c1  mov     r8d, edi; Tag
0x1400af1c4  call    cs:__imp_ExAllocatePoolWithTag
0x1400af1cb  nop     dword ptr [rax+rax+00h]
0x1400af1d0  mov     r13, rax
0x1400af1d3  mov     [rsp+108h+var_98], rax
0x1400af1d8  mov     r8b, 1; SubAuthorityCount
0x1400af1db  lea     rdx, [rsp+108h+var_58]; IdentifierAuthority
0x1400af1e3  mov     rcx, rax; Sid
0x1400af1e6  call    cs:__imp_RtlInitializeSid
0x1400af1ed  nop     dword ptr [rax+rax+00h]
0x1400af1f2  xor     edx, edx; SubAuthority
0x1400af1f4  mov     rcx, r13; Sid
0x1400af1f7  call    cs:__imp_RtlSubAuthoritySid
0x1400af1fe  nop     dword ptr [rax+rax+00h]
0x1400af203  mov     [rax], r14d
0x1400af206  lea     ecx, [rbx-1Eh]; SubAuthorityCount
0x1400af209  call    cs:__imp_RtlLengthRequiredSid
0x1400af210  nop     dword ptr [rax+rax+00h]
0x1400af215  mov     edx, eax; NumberOfBytes
0x1400af217  mov     ecx, cs:PoolType
0x1400af21d  or      ecx, 10h; PoolType
0x1400af220  mov     r8d, edi; Tag
0x1400af223  call    cs:__imp_ExAllocatePoolWithTag
0x1400af22a  nop     dword ptr [rax+rax+00h]
0x1400af22f  mov     r14, rax
0x1400af232  mov     [rsp+108h+var_90], rax
0x1400af237  mov     r8b, 2; SubAuthorityCount
0x1400af23a  lea     rdx, [rsp+108h+IdentifierAuthority]; IdentifierAuthority
0x1400af242  mov     rcx, rax; Sid
0x1400af245  call    cs:__imp_RtlInitializeSid
0x1400af24c  nop     dword ptr [rax+rax+00h]
0x1400af251  xor     edx, edx; SubAuthority
0x1400af253  mov     rcx, r14; Sid
0x1400af256  call    cs:__imp_RtlSubAuthoritySid
0x1400af25d  nop     dword ptr [rax+rax+00h]
0x1400af262  mov     [rax], ebx
0x1400af264  mov     ebx, 1
0x1400af269  mov     edx, ebx; SubAuthority
0x1400af26b  mov     rcx, r14; Sid
0x1400af26e  call    cs:__imp_RtlSubAuthoritySid
0x1400af275  nop     dword ptr [rax+rax+00h]
0x1400af27a  mov     dword ptr [rax], 221h
0x1400af280  mov     ecx, ebx; SubAuthorityCount
0x1400af282  call    cs:__imp_RtlLengthRequiredSid
0x1400af289  nop     dword ptr [rax+rax+00h]
0x1400af28e  mov     edx, eax; NumberOfBytes
0x1400af290  mov     ecx, cs:PoolType
0x1400af296  or      ecx, 10h; PoolType
0x1400af299  mov     r8d, edi; Tag
0x1400af29c  call    cs:__imp_ExAllocatePoolWithTag
0x1400af2a3  nop     dword ptr [rax+rax+00h]
0x1400af2a8  mov     rbx, rax
0x1400af2ab  mov     [rsp+108h+P], rax
0x1400af2b0  mov     r8b, 1; SubAuthorityCount
0x1400af2b3  lea     rdx, [rsp+108h+var_50]; IdentifierAuthority
0x1400af2bb  mov     rcx, rax; Sid
0x1400af2be  call    cs:__imp_RtlInitializeSid
0x1400af2c5  nop     dword ptr [rax+rax+00h]
0x1400af2ca  xor     edx, edx; SubAuthority
0x1400af2cc  mov     rcx, rbx; Sid
0x1400af2cf  call    cs:__imp_RtlSubAuthoritySid
0x1400af2d6  nop     dword ptr [rax+rax+00h]
0x1400af2db  mov     dword ptr [rax], 0
0x1400af2e1  movzx   ebx, byte ptr [rbx+1]
0x1400af2e5  movzx   ecx, byte ptr [r14+1]
0x1400af2ea  add     ebx, ecx
0x1400af2ec  movzx   ecx, byte ptr [r13+1]
0x1400af2f1  add     ebx, ecx
0x1400af2f3  movzx   eax, byte ptr [r12+1]
0x1400af2f9  add     ebx, eax
0x1400af2fb  movzx   eax, byte ptr [r15+1]
0x1400af300  add     ebx, eax
0x1400af302  lea     ebx, ds:0E8h[rbx*4]
0x1400af309  mov     edx, ebx; NumberOfBytes
0x1400af30b  mov     ecx, cs:PoolType
0x1400af311  or      ecx, 10h; PoolType
0x1400af314  mov     r8d, edi; Tag
0x1400af317  call    cs:__imp_ExAllocatePoolWithTag
0x1400af31e  nop     dword ptr [rax+rax+00h]
0x1400af323  mov     rdi, rax
0x1400af326  mov     [rsp+108h+var_B0], rax
0x1400af32b  mov     r8d, 2; AclRevision
0x1400af331  mov     edx, ebx; AclLength
0x1400af333  mov     rcx, rax; Acl
0x1400af336  call    cs:__imp_RtlCreateAcl
0x1400af33d  nop     dword ptr [rax+rax+00h]
0x1400af342  mov     ebx, eax
0x1400af344  mov     [rsp+108h+var_C4], eax
0x1400af348  test    eax, eax
0x1400af34a  js      loc_1400AF55A
0x1400af350  mov     [rsp+108h+Sid], r15; Sid
0x1400af355  mov     edx, 2; AceRevision
0x1400af35a  mov     r9d, 10000000h; AccessMask
0x1400af360  lea     r8d, [rdx+1]; AceFlags
0x1400af364  mov     rcx, rdi; Acl
0x1400af367  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1400af36e  nop     dword ptr [rax+rax+00h]
0x1400af373  mov     ebx, eax
0x1400af375  mov     [rsp+108h+var_C4], eax
0x1400af379  test    eax, eax
0x1400af37b  js      loc_1400AF55A
0x1400af381  mov     [rsp+108h+Sid], r12; Sid
0x1400af386  mov     edx, 2; AceRevision
0x1400af38b  mov     r9d, 10000000h; AccessMask
0x1400af391  lea     r8d, [rdx+1]; AceFlags
0x1400af395  mov     rcx, rdi; Acl
0x1400af398  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1400af39f  nop     dword ptr [rax+rax+00h]
0x1400af3a4  mov     ebx, eax
0x1400af3a6  mov     [rsp+108h+var_C4], eax
0x1400af3aa  test    eax, eax
0x1400af3ac  js      loc_1400AF55A
0x1400af3b2  mov     [rsp+108h+Sid], r13; Sid
0x1400af3b7  mov     edx, 2; AceRevision
0x1400af3bc  mov     r9d, 10000000h; AccessMask
0x1400af3c2  lea     r8d, [rdx+9]; AceFlags
0x1400af3c6  mov     rcx, rdi; Acl
0x1400af3c9  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1400af3d0  nop     dword ptr [rax+rax+00h]
0x1400af3d5  mov     ebx, eax
0x1400af3d7  mov     [rsp+108h+var_C4], eax
0x1400af3db  test    eax, eax
0x1400af3dd  js      loc_1400AF55A
0x1400af3e3  mov     [rsp+108h+Sid], r14; Sid
0x1400af3e8  mov     edx, 2; AceRevision
0x1400af3ed  mov     r9d, 80100020h; AccessMask
0x1400af3f3  lea     r8d, [rdx+1]; AceFlags
0x1400af3f7  mov     rcx, rdi; Acl
0x1400af3fa  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1400af401  nop     dword ptr [rax+rax+00h]
0x1400af406  mov     ebx, eax
0x1400af408  mov     [rsp+108h+var_C4], eax
0x1400af40c  test    eax, eax
0x1400af40e  js      loc_1400AF55A
0x1400af414  mov     [rsp+108h+Sid], r14; Sid
0x1400af419  mov     eax, 2
0x1400af41e  lea     r9d, [rax+2]; AccessMask
0x1400af422  mov     r8d, eax; AceFlags
0x1400af425  mov     edx, eax; AceRevision
0x1400af427  mov     rcx, rdi; Acl
0x1400af42a  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1400af431  nop     dword ptr [rax+rax+00h]
0x1400af436  mov     ebx, eax
0x1400af438  mov     [rsp+108h+var_C4], eax
0x1400af43c  test    eax, eax
0x1400af43e  js      loc_1400AF55A
0x1400af444  mov     [rsp+108h+Sid], r14; Sid
0x1400af449  mov     eax, 2
0x1400af44e  mov     r9d, eax; AccessMask
0x1400af451  lea     r8d, [rax+1]; AceFlags
0x1400af455  mov     edx, eax; AceRevision
0x1400af457  mov     rcx, rdi; Acl
0x1400af45a  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1400af461  nop     dword ptr [rax+rax+00h]
0x1400af466  mov     ebx, eax
0x1400af468  mov     [rsp+108h+var_C4], eax
0x1400af46c  test    eax, eax
0x1400af46e  js      loc_1400AF55A
0x1400af474  mov     rax, [rsp+108h+P]
0x1400af479  mov     [rsp+108h+Sid], rax; Sid
0x1400af47e  mov     edx, 2; AceRevision
0x1400af483  mov     r9d, 80100020h; AccessMask
0x1400af489  lea     r8d, [rdx+1]; AceFlags
0x1400af48d  mov     rcx, rdi; Acl
0x1400af490  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1400af497  nop     dword ptr [rax+rax+00h]
0x1400af49c  mov     ebx, eax
0x1400af49e  mov     [rsp+108h+var_C4], eax
0x1400af4a2  test    eax, eax
0x1400af4a4  js      loc_1400AF55A
0x1400af4aa  mov     edx, 1; Revision
0x1400af4af  lea     rcx, [rsp+108h+SecurityDescriptor]; SecurityDescriptor
0x1400af4b7  call    cs:__imp_RtlCreateSecurityDescriptor
0x1400af4be  nop     dword ptr [rax+rax+00h]
0x1400af4c3  mov     ebx, eax
0x1400af4c5  mov     [rsp+108h+var_C4], eax
0x1400af4c9  test    eax, eax
0x1400af4cb  js      loc_1400AF55A
0x1400af4d1  xor     r9d, r9d; DaclDefaulted
0x1400af4d4  mov     r8, rdi; Dacl
0x1400af4d7  mov     dl, 1; DaclPresent
0x1400af4d9  lea     rcx, [rsp+108h+SecurityDescriptor]; SecurityDescriptor
0x1400af4e1  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1400af4e8  nop     dword ptr [rax+rax+00h]
0x1400af4ed  mov     ebx, eax
0x1400af4ef  mov     [rsp+108h+var_C4], eax
0x1400af4f3  test    eax, eax
0x1400af4f5  js      short loc_1400AF55A
0x1400af4f7  mov     ebx, cs:PoolType
0x1400af4fd  call    cs:__imp_IoGetFileObjectGenericMapping
0x1400af504  nop     dword ptr [rax+rax+00h]
0x1400af509  mov     [rsp+108h+PoolType], ebx; PoolType
0x1400af50d  mov     [rsp+108h+GenericMapping], rax; GenericMapping
0x1400af512  mov     [rsp+108h+Sid], rsi; SubjectContext
0x1400af517  xor     r9d, r9d; IsDirectoryObject
0x1400af51a  lea     r8, ModificationDescriptor; NewDescriptor
0x1400af521  lea     rdx, [rsp+108h+SecurityDescriptor]; ExplicitDescriptor
0x1400af529  xor     ecx, ecx; ParentDescriptor
0x1400af52b  call    cs:__imp_SeAssignSecurity
0x1400af532  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
