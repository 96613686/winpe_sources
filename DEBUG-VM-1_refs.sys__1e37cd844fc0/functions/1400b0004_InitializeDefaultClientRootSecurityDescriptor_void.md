# InitializeDefaultClientRootSecurityDescriptor(void)

- ea: `0x1400b0004`
- end: `0x1400b05d2`
- name: `?InitializeDefaultClientRootSecurityDescriptor@@YAXXZ`
- size: `1486`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14034f36c`

## callees

- `0x1400862c0`
- `0x1400b0004`
- `0x1400d0fd8`
- `0x1401f3fc0`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x1400b05a1`
- `ntoskrnl!ExRaiseStatus` at `0x1400b05a1`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400b0098`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400b0098`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400b04c5`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1401f5ca9`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400b04c5`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1401f5ca9`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400b0468`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400b0468`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400b00b4`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400b012a`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400b018c`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400b01ee`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400b00b4`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400b012a`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400b018c`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400b01ee`
- `ntoskrnl!RtlInitializeSid` at `0x1400b00f0`
- `ntoskrnl!RtlInitializeSid` at `0x1400b0166`
- `ntoskrnl!RtlInitializeSid` at `0x1400b01c8`
- `ntoskrnl!RtlInitializeSid` at `0x1400b022a`
- `ntoskrnl!RtlInitializeSid` at `0x1400b00f0`
- `ntoskrnl!RtlInitializeSid` at `0x1400b0166`
- `ntoskrnl!RtlInitializeSid` at `0x1400b01c8`
- `ntoskrnl!RtlInitializeSid` at `0x1400b022a`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b0101`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b0115`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b0177`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b01d9`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b023b`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b024f`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b0101`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b0115`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b0177`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b01d9`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b023b`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b024f`
- `ntoskrnl!RtlCreateAcl` at `0x1400b02b0`
- `ntoskrnl!RtlCreateAcl` at `0x1400b02b0`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400b0425`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400b0425`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400b044c`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400b044c`
- `ntoskrnl!SeAssignSecurity` at `0x1400b0493`
- `ntoskrnl!SeAssignSecurity` at `0x1400b0493`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1400b04b0`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1400b04b0`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400b02e1`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400b0310`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400b0341`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400b0370`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400b03a1`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400b03d0`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400b0401`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400b02e1`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400b0310`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400b0341`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400b0370`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400b03a1`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400b03d0`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400b0401`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b04db`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b04f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b0502`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b0513`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b0524`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b0535`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f5cc1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f5cd9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f5cf1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f5d09`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f5d21`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f5d39`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b04db`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b04f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b0502`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b0513`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b0524`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b0535`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f5cc1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f5cd9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f5cf1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f5d09`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f5d21`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f5d39`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b0081`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b00ce`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b0144`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b01a6`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b0208`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b0291`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b0081`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b00ce`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b0144`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b01a6`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b0208`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b0291`

## pseudocode

```c
void InitializeDefaultClientRootSecurityDescriptor(void)
{
  struct _SECURITY_SUBJECT_CONTEXT *PoolWithTag; // rsi
  ULONG v1; // eax
  unsigned __int8 *Sid; // r13
  ULONG v3; // eax
  unsigned __int8 *v4; // r15
  ULONG v5; // eax
  unsigned __int8 *v6; // r12
  ULONG v7; // eax
  unsigned __int8 *v8; // r14
  ULONG v9; // ebx
  struct _ACL *v10; // rdi
  int Acl; // ebx
  POOL_TYPE PoolType; // ebx
  struct _GENERIC_MAPPING *GenericMapping; // rax
  _OWORD SecurityDescriptor[2]; // [rsp+78h] [rbp-70h] BYREF
  __int64 v15; // [rsp+98h] [rbp-50h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+A0h] [rbp-48h] BYREF

  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v15 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
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
  RtlInitializeSid(v6, &IdentifierAuthority, 1u);
  *RtlSubAuthoritySid(v6, 0) = 11;
  v7 = RtlLengthRequiredSid(2u);
  v8 = (unsigned __int8 *)ExAllocatePoolWithTag((POOL_TYPE)(::PoolType | 0x10), v7, 0x4A666552u);
  RtlInitializeSid(v8, &IdentifierAuthority, 2u);
  *RtlSubAuthoritySid(v8, 0) = 32;
  *RtlSubAuthoritySid(v8, 1u) = 545;
  v9 = 4 * (Sid[1] + v4[1] + v6[1] + v8[1]) + 176;
  v10 = (struct _ACL *)ExAllocatePoolWithTag((POOL_TYPE)(::PoolType | 0x10), v9, 0x4A666552u);
  Acl = RtlCreateAcl(v10, v9, 2u);
  if ( Acl >= 0 )
  {
    Acl = RtlAddAccessAllowedAceEx(v10, 2u, 3u, 0x10000000u, Sid);
    if ( Acl >= 0 )
    {
      Acl = RtlAddAccessAllowedAceEx(v10, 2u, 0, 0x10000000u, v4);
      if ( Acl >= 0 )
      {
        Acl = RtlAddAccessAllowedAceEx(v10, 2u, 0xBu, 0x10000000u, v4);
        if ( Acl >= 0 )
        {
          Acl = RtlAddAccessAllowedAceEx(v10, 2u, 0, 0xE0010000, v6);
          if ( Acl >= 0 )
          {
            Acl = RtlAddAccessAllowedAceEx(v10, 2u, 0xBu, 0xE0010000, v6);
            if ( Acl >= 0 )
            {
              Acl = RtlAddAccessAllowedAceEx(v10, 2u, 0, 0xA0000000, v8);
              if ( Acl >= 0 )
              {
                Acl = RtlAddAccessAllowedAceEx(v10, 2u, 0xBu, 0xA0000000, v8);
                if ( Acl >= 0 )
                {
                  Acl = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
                  if ( Acl >= 0 )
                  {
                    Acl = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v10, 0);
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
  if ( v10 )
    ExFreePoolWithTag(v10, 0);
  ExFreePoolWithTag(Sid, 0);
  ExFreePoolWithTag(v4, 0);
  ExFreePoolWithTag(v6, 0);
  ExFreePoolWithTag(v8, 0);
  if ( Acl < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        22,
        &WPP_823e6dba7932309d1ad2e841189c99ac_Traceguids,
        (unsigned int)Acl);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(Acl, 0, "NtfsInit.c", 0x1833u);
    ExRaiseStatus(Acl);
  }
}

```

## disassembly

```asm
0x1400b0004  mov     r11, rsp
0x1400b0007  push    rbx
0x1400b0008  push    rsi
0x1400b0009  push    rdi
0x1400b000a  push    r12
0x1400b000c  push    r13
0x1400b000e  push    r14
0x1400b0010  push    r15
0x1400b0012  sub     rsp, 0B0h
0x1400b0019  mov     rax, cs:__security_cookie
0x1400b0020  xor     rax, rsp
0x1400b0023  mov     [rsp+0E8h+var_40], rax
0x1400b002b  xor     ecx, ecx
0x1400b002d  mov     [rsp+0E8h+var_A0], rcx
0x1400b0032  mov     [rsp+0E8h+var_A8], cl
0x1400b0036  mov     [rsp+0E8h+var_98], rcx
0x1400b003b  mov     [rsp+0E8h+var_90], rcx
0x1400b0040  mov     [rsp+0E8h+var_88], rcx
0x1400b0045  mov     [r11-80h], rcx
0x1400b0049  mov     [r11-78h], rcx
0x1400b004d  xorps   xmm0, xmm0
0x1400b0050  xor     eax, eax
0x1400b0052  movups  [rsp+0E8h+SecurityDescriptor], xmm0
0x1400b0057  movups  xmmword ptr [r11-60h], xmm0
0x1400b005c  mov     [r11-50h], rax
0x1400b0060  mov     [r11-48h], ecx
0x1400b0064  mov     word ptr [r11-44h], 500h
0x1400b006b  mov     ecx, cs:PoolType
0x1400b0071  or      ecx, 10h; PoolType
0x1400b0074  mov     edi, 4A666552h
0x1400b0079  mov     r8d, edi; Tag
0x1400b007c  lea     ebx, [rax+20h]
0x1400b007f  mov     edx, ebx; NumberOfBytes
0x1400b0081  call    cs:__imp_ExAllocatePoolWithTag
0x1400b0088  nop     dword ptr [rax+rax+00h]
0x1400b008d  mov     rsi, rax
0x1400b0090  mov     [rsp+0E8h+var_A0], rax
0x1400b0095  mov     rcx, rax; SubjectContext
0x1400b0098  call    cs:__imp_SeCaptureSubjectContext
0x1400b009f  nop     dword ptr [rax+rax+00h]
0x1400b00a4  lea     r12d, [rbx-1Fh]
0x1400b00a8  mov     [rsp+0E8h+var_A8], r12b
0x1400b00ad  lea     r14d, [rbx-1Eh]
0x1400b00b1  mov     ecx, r14d; SubAuthorityCount
0x1400b00b4  call    cs:__imp_RtlLengthRequiredSid
0x1400b00bb  nop     dword ptr [rax+rax+00h]
0x1400b00c0  mov     edx, eax; NumberOfBytes
0x1400b00c2  mov     ecx, cs:PoolType
0x1400b00c8  or      ecx, 10h; PoolType
0x1400b00cb  mov     r8d, edi; Tag
0x1400b00ce  call    cs:__imp_ExAllocatePoolWithTag
0x1400b00d5  nop     dword ptr [rax+rax+00h]
0x1400b00da  mov     r13, rax
0x1400b00dd  mov     [rsp+0E8h+var_90], rax
0x1400b00e2  mov     r8b, r14b; SubAuthorityCount
0x1400b00e5  lea     rdx, [rsp+0E8h+IdentifierAuthority]; IdentifierAuthority
0x1400b00ed  mov     rcx, rax; Sid
0x1400b00f0  call    cs:__imp_RtlInitializeSid
0x1400b00f7  nop     dword ptr [rax+rax+00h]
0x1400b00fc  xor     edx, edx; SubAuthority
0x1400b00fe  mov     rcx, r13; Sid
0x1400b0101  call    cs:__imp_RtlSubAuthoritySid
0x1400b0108  nop     dword ptr [rax+rax+00h]
0x1400b010d  mov     [rax], ebx
0x1400b010f  mov     edx, r12d; SubAuthority
0x1400b0112  mov     rcx, r13; Sid
0x1400b0115  call    cs:__imp_RtlSubAuthoritySid
0x1400b011c  nop     dword ptr [rax+rax+00h]
0x1400b0121  mov     dword ptr [rax], 220h
0x1400b0127  mov     ecx, r12d; SubAuthorityCount
0x1400b012a  call    cs:__imp_RtlLengthRequiredSid
0x1400b0131  nop     dword ptr [rax+rax+00h]
0x1400b0136  mov     edx, eax; NumberOfBytes
0x1400b0138  mov     ecx, cs:PoolType
0x1400b013e  or      ecx, 10h; PoolType
0x1400b0141  mov     r8d, edi; Tag
0x1400b0144  call    cs:__imp_ExAllocatePoolWithTag
0x1400b014b  nop     dword ptr [rax+rax+00h]
0x1400b0150  mov     r15, rax
0x1400b0153  mov     [rsp+0E8h+var_88], rax
0x1400b0158  mov     r8b, r12b; SubAuthorityCount
0x1400b015b  lea     rdx, [rsp+0E8h+IdentifierAuthority]; IdentifierAuthority
0x1400b0163  mov     rcx, rax; Sid
0x1400b0166  call    cs:__imp_RtlInitializeSid
0x1400b016d  nop     dword ptr [rax+rax+00h]
0x1400b0172  xor     edx, edx; SubAuthority
0x1400b0174  mov     rcx, r15; Sid
0x1400b0177  call    cs:__imp_RtlSubAuthoritySid
0x1400b017e  nop     dword ptr [rax+rax+00h]
0x1400b0183  mov     dword ptr [rax], 12h
0x1400b0189  mov     ecx, r12d; SubAuthorityCount
0x1400b018c  call    cs:__imp_RtlLengthRequiredSid
0x1400b0193  nop     dword ptr [rax+rax+00h]
0x1400b0198  mov     edx, eax; NumberOfBytes
0x1400b019a  mov     ecx, cs:PoolType
0x1400b01a0  or      ecx, 10h; PoolType
0x1400b01a3  mov     r8d, edi; Tag
0x1400b01a6  call    cs:__imp_ExAllocatePoolWithTag
0x1400b01ad  nop     dword ptr [rax+rax+00h]
0x1400b01b2  mov     r12, rax
0x1400b01b5  mov     [rsp+0E8h+var_80], rax
0x1400b01ba  mov     r8b, 1; SubAuthorityCount
0x1400b01bd  lea     rdx, [rsp+0E8h+IdentifierAuthority]; IdentifierAuthority
0x1400b01c5  mov     rcx, rax; Sid
0x1400b01c8  call    cs:__imp_RtlInitializeSid
0x1400b01cf  nop     dword ptr [rax+rax+00h]
0x1400b01d4  xor     edx, edx; SubAuthority
0x1400b01d6  mov     rcx, r12; Sid
0x1400b01d9  call    cs:__imp_RtlSubAuthoritySid
0x1400b01e0  nop     dword ptr [rax+rax+00h]
0x1400b01e5  mov     dword ptr [rax], 0Bh
0x1400b01eb  mov     ecx, r14d; SubAuthorityCount
0x1400b01ee  call    cs:__imp_RtlLengthRequiredSid
0x1400b01f5  nop     dword ptr [rax+rax+00h]
0x1400b01fa  mov     edx, eax; NumberOfBytes
0x1400b01fc  mov     ecx, cs:PoolType
0x1400b0202  or      ecx, 10h; PoolType
0x1400b0205  mov     r8d, edi; Tag
0x1400b0208  call    cs:__imp_ExAllocatePoolWithTag
0x1400b020f  nop     dword ptr [rax+rax+00h]
0x1400b0214  mov     r14, rax
0x1400b0217  mov     [rsp+0E8h+var_78], rax
0x1400b021c  mov     r8b, 2; SubAuthorityCount
0x1400b021f  lea     rdx, [rsp+0E8h+IdentifierAuthority]; IdentifierAuthority
0x1400b0227  mov     rcx, rax; Sid
0x1400b022a  call    cs:__imp_RtlInitializeSid
0x1400b0231  nop     dword ptr [rax+rax+00h]
0x1400b0236  xor     edx, edx; SubAuthority
0x1400b0238  mov     rcx, r14; Sid
0x1400b023b  call    cs:__imp_RtlSubAuthoritySid
0x1400b0242  nop     dword ptr [rax+rax+00h]
0x1400b0247  mov     [rax], ebx
0x1400b0249  lea     edx, [rbx-1Fh]; SubAuthority
0x1400b024c  mov     rcx, r14; Sid
0x1400b024f  call    cs:__imp_RtlSubAuthoritySid
0x1400b0256  nop     dword ptr [rax+rax+00h]
0x1400b025b  mov     dword ptr [rax], 221h
0x1400b0261  movzx   ecx, byte ptr [r14+1]
0x1400b0266  movzx   eax, byte ptr [r12+1]
0x1400b026c  add     ecx, eax
0x1400b026e  movzx   eax, byte ptr [r15+1]
0x1400b0273  add     ecx, eax
0x1400b0275  movzx   eax, byte ptr [r13+1]
0x1400b027a  add     ecx, eax
0x1400b027c  lea     ebx, ds:0B0h[rcx*4]
0x1400b0283  mov     edx, ebx; NumberOfBytes
0x1400b0285  mov     ecx, cs:PoolType
0x1400b028b  or      ecx, 10h; PoolType
0x1400b028e  mov     r8d, edi; Tag
0x1400b0291  call    cs:__imp_ExAllocatePoolWithTag
0x1400b0298  nop     dword ptr [rax+rax+00h]
0x1400b029d  mov     rdi, rax
0x1400b02a0  mov     [rsp+0E8h+var_98], rax
0x1400b02a5  mov     r8d, 2; AclRevision
0x1400b02ab  mov     edx, ebx; AclLength
0x1400b02ad  mov     rcx, rax; Acl
0x1400b02b0  call    cs:__imp_RtlCreateAcl
0x1400b02b7  nop     dword ptr [rax+rax+00h]
0x1400b02bc  mov     ebx, eax
0x1400b02be  mov     [rsp+0E8h+var_A4], eax
0x1400b02c2  test    eax, eax
0x1400b02c4  js      loc_1400B04C2
0x1400b02ca  mov     [rsp+0E8h+Sid], r13; Sid
0x1400b02cf  mov     edx, 2; AceRevision
0x1400b02d4  mov     r9d, 10000000h; AccessMask
0x1400b02da  lea     r8d, [rdx+1]; AceFlags
0x1400b02de  mov     rcx, rdi; Acl
0x1400b02e1  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1400b02e8  nop     dword ptr [rax+rax+00h]
0x1400b02ed  mov     ebx, eax
0x1400b02ef  mov     [rsp+0E8h+var_A4], eax
0x1400b02f3  test    eax, eax
0x1400b02f5  js      loc_1400B04C2
0x1400b02fb  mov     [rsp+0E8h+Sid], r15; Sid
0x1400b0300  mov     r9d, 10000000h; AccessMask
0x1400b0306  xor     r8d, r8d; AceFlags
0x1400b0309  lea     edx, [r8+2]; AceRevision
0x1400b030d  mov     rcx, rdi; Acl
0x1400b0310  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1400b0317  nop     dword ptr [rax+rax+00h]
0x1400b031c  mov     ebx, eax
0x1400b031e  mov     [rsp+0E8h+var_A4], eax
0x1400b0322  test    eax, eax
0x1400b0324  js      loc_1400B04C2
0x1400b032a  mov     [rsp+0E8h+Sid], r15; Sid
0x1400b032f  mov     edx, 2; AceRevision
0x1400b0334  mov     r9d, 10000000h; AccessMask
0x1400b033a  lea     r8d, [rdx+9]; AceFlags
0x1400b033e  mov     rcx, rdi; Acl
0x1400b0341  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1400b0348  nop     dword ptr [rax+rax+00h]
0x1400b034d  mov     ebx, eax
0x1400b034f  mov     [rsp+0E8h+var_A4], eax
0x1400b0353  test    eax, eax
0x1400b0355  js      loc_1400B04C2
0x1400b035b  mov     [rsp+0E8h+Sid], r12; Sid
0x1400b0360  mov     r9d, 0E0010000h; AccessMask
0x1400b0366  xor     r8d, r8d; AceFlags
0x1400b0369  lea     edx, [r8+2]; AceRevision
0x1400b036d  mov     rcx, rdi; Acl
0x1400b0370  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1400b0377  nop     dword ptr [rax+rax+00h]
0x1400b037c  mov     ebx, eax
0x1400b037e  mov     [rsp+0E8h+var_A4], eax
0x1400b0382  test    eax, eax
0x1400b0384  js      loc_1400B04C2
0x1400b038a  mov     [rsp+0E8h+Sid], r12; Sid
0x1400b038f  mov     edx, 2; AceRevision
0x1400b0394  mov     r9d, 0E0010000h; AccessMask
0x1400b039a  lea     r8d, [rdx+9]; AceFlags
0x1400b039e  mov     rcx, rdi; Acl
0x1400b03a1  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1400b03a8  nop     dword ptr [rax+rax+00h]
0x1400b03ad  mov     ebx, eax
0x1400b03af  mov     [rsp+0E8h+var_A4], eax
0x1400b03b3  test    eax, eax
0x1400b03b5  js      loc_1400B04C2
0x1400b03bb  mov     [rsp+0E8h+Sid], r14; Sid
0x1400b03c0  mov     r9d, 0A0000000h; AccessMask
0x1400b03c6  xor     r8d, r8d; AceFlags
0x1400b03c9  lea     edx, [r8+2]; AceRevision
0x1400b03cd  mov     rcx, rdi; Acl
0x1400b03d0  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1400b03d7  nop     dword ptr [rax+rax+00h]
0x1400b03dc  mov     ebx, eax
0x1400b03de  mov     [rsp+0E8h+var_A4], eax
0x1400b03e2  test    eax, eax
0x1400b03e4  js      loc_1400B04C2
0x1400b03ea  mov     [rsp+0E8h+Sid], r14; Sid
0x1400b03ef  mov     edx, 2; AceRevision
0x1400b03f4  mov     r9d, 0A0000000h; AccessMask
0x1400b03fa  lea     r8d, [rdx+9]; AceFlags
0x1400b03fe  mov     rcx, rdi; Acl
0x1400b0401  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1400b0408  nop     dword ptr [rax+rax+00h]
0x1400b040d  mov     ebx, eax
0x1400b040f  mov     [rsp+0E8h+var_A4], eax
0x1400b0413  test    eax, eax
0x1400b0415  js      loc_1400B04C2
0x1400b041b  mov     edx, 1; Revision
0x1400b0420  lea     rcx, [rsp+0E8h+SecurityDescriptor]; SecurityDescriptor
0x1400b0425  call    cs:__imp_RtlCreateSecurityDescriptor
0x1400b042c  nop     dword ptr [rax+rax+00h]
0x1400b0431  mov     ebx, eax
0x1400b0433  mov     [rsp+0E8h+var_A4], eax
0x1400b0437  test    eax, eax
0x1400b0439  js      loc_1400B04C2
0x1400b043f  xor     r9d, r9d; DaclDefaulted
0x1400b0442  mov     r8, rdi; Dacl
0x1400b0445  mov     dl, 1; DaclPresent
0x1400b0447  lea     rcx, [rsp+0E8h+SecurityDescriptor]; SecurityDescriptor
0x1400b044c  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1400b0453  nop     dword ptr [rax+rax+00h]
0x1400b0458  mov     ebx, eax
0x1400b045a  mov     [rsp+0E8h+var_A4], eax
0x1400b045e  test    eax, eax
0x1400b0460  js      short loc_1400B04C2
0x1400b0462  mov     ebx, cs:PoolType
0x1400b0468  call    cs:__imp_IoGetFileObjectGenericMapping
0x1400b046f  nop     dword ptr [rax+rax+00h]
0x1400b0474  mov     [rsp+0E8h+PoolType], ebx; PoolType
0x1400b0478  mov     [rsp+0E8h+GenericMapping], rax; GenericMapping
0x1400b047d  mov     [rsp+0E8h+Sid], rsi; SubjectContext
0x1400b0482  xor     r9d, r9d; IsDirectoryObject
0x1400b0485  lea     r8, ModificationDescriptor; NewDescriptor
0x1400b048c  lea     rdx, [rsp+0E8h+SecurityDescriptor]; ExplicitDescriptor
0x1400b0491  xor     ecx, ecx; ParentDescriptor
0x1400b0493  call    cs:__imp_SeAssignSecurity
0x1400b049a  nop     dword ptr [rax+rax+00h]
0x1400b049f  mov     ebx, eax
0x1400b04a1  mov     [rsp+0E8h+var_A4], eax
0x1400b04a5  test    eax, eax
0x1400b04a7  js      short loc_1400B04C2
0x1400b04a9  mov     rcx, cs:ModificationDescriptor; SecurityDescriptor
0x1400b04b0  call    cs:__imp_RtlLengthSecurityDescriptor
0x1400b04b7  nop     dword ptr [rax+rax+00h]
0x1400b04bc  mov     cs:dword_1402682C8, eax
0x1400b04c2  mov     rcx, rsi; SubjectContext
0x1400b04c5  call    cs:__imp_SeReleaseSubjectContext
0x1400b04cc  nop     dword ptr [rax+rax+00h]
0x1400b04d1  test    rsi, rsi
0x1400b04d4  jz      short loc_1400B04E7
0x1400b04d6  xor     edx, edx; Tag
0x1400b04d8  mov     rcx, rsi; P
0x1400b04db  call    cs:__imp_ExFreePoolWithTag
0x1400b04e2  nop     dword ptr [rax+rax+00h]
0x1400b04e7  test    rdi, rdi
0x1400b04ea  jz      short loc_1400B04FD
0x1400b04ec  xor     edx, edx; Tag
0x1400b04ee  mov     rcx, rdi; P
0x1400b04f1  call    cs:__imp_ExFreePoolWithTag
0x1400b04f8  nop     dword ptr [rax+rax+00h]
0x1400b04fd  xor     edx, edx; Tag
0x1400b04ff  mov     rcx, r13; P
0x1400b0502  call    cs:__imp_ExFreePoolWithTag
0x1400b0509  nop     dword ptr [rax+rax+00h]
0x1400b050e  xor     edx, edx; Tag
0x1400b0510  mov     rcx, r15; P
0x1400b0513  call    cs:__imp_ExFreePoolWithTag
0x1400b051a  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
