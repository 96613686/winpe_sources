# BfsCreatePolicyStorageDescriptor

- ea: `0x140012bf4`
- end: `0x140012fa8`
- name: `BfsCreatePolicyStorageDescriptor`
- size: `948`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14001f078`

## callees

- `0x140001008`
- `0x140012bf4`
- `0x140013730`

## import_xrefs

- `ntoskrnl!RtlLengthSid` at `0x140012cc8`
- `ntoskrnl!RtlLengthSid` at `0x140012ce8`
- `ntoskrnl!RtlLengthSid` at `0x140012e52`
- `ntoskrnl!RtlLengthSid` at `0x140012cc8`
- `ntoskrnl!RtlLengthSid` at `0x140012ce8`
- `ntoskrnl!RtlLengthSid` at `0x140012e52`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140012e2b`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140012e2b`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140012c25`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140012c25`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140012dd1`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140012e0a`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140012dd1`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140012e0a`
- `ntoskrnl!RtlCreateAcl` at `0x140012d8f`
- `ntoskrnl!RtlCreateAcl` at `0x140012ebf`
- `ntoskrnl!RtlCreateAcl` at `0x140012d8f`
- `ntoskrnl!RtlCreateAcl` at `0x140012ebf`
- `ntoskrnl!SeExports` at `0x140012c51`
- `ntoskrnl!SeExports` at `0x140012c7a`
- `ntoskrnl!SeExports` at `0x140012cb7`
- `ntoskrnl!SeExports` at `0x140012cd4`
- `ntoskrnl!SeExports` at `0x140012da5`
- `ntoskrnl!SeExports` at `0x140012de7`
- `ntoskrnl!SeExports` at `0x140012e41`
- `ntoskrnl!SeExports` at `0x140012ed1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012f5f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012f75`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012f5f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012f75`
- `ntoskrnl!ExAllocatePool2` at `0x140012d08`
- `ntoskrnl!ExAllocatePool2` at `0x140012e6e`
- `ntoskrnl!ExAllocatePool2` at `0x140012d08`
- `ntoskrnl!ExAllocatePool2` at `0x140012e6e`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x140012c68`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x140012c68`
- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x140012c91`
- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x140012c91`
- `ntoskrnl!RtlSetControlSecurityDescriptor` at `0x140012d6d`
- `ntoskrnl!RtlSetControlSecurityDescriptor` at `0x140012d6d`
- `ntoskrnl!RtlAddMandatoryAce` at `0x140012ef8`
- `ntoskrnl!RtlAddMandatoryAce` at `0x140012ef8`
- `ntoskrnl!RtlSetSaclSecurityDescriptor` at `0x140012f15`
- `ntoskrnl!RtlSetSaclSecurityDescriptor` at `0x140012f15`

## pseudocode

```c
__int64 __fastcall BfsCreatePolicyStorageDescriptor(PSECURITY_DESCRIPTOR SecurityDescriptor, unsigned __int8 a2)
{
  ULONG v2; // r12d
  NTSTATUS v4; // eax
  int v5; // r8d
  int v6; // r9d
  NTSTATUS Acl; // ebx
  int v8; // ecx
  ULONG v9; // r15d
  ULONG v10; // r15d
  struct _ACL *Pool2; // r14
  struct _ACL *v12; // rdi
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  __int64 v16; // rbx
  struct _ACL *v17; // rax
  int Sid; // [rsp+20h] [rbp-50h]
  PSID LabelSid; // [rsp+28h] [rbp-48h]
  int v21; // [rsp+30h] [rbp-40h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v22; // [rsp+38h] [rbp-38h] BYREF
  int *v23; // [rsp+58h] [rbp-18h]
  __int64 v24; // [rsp+60h] [rbp-10h]

  v2 = a2;
  v4 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  Acl = v4;
  if ( v4 < 0 )
  {
    v8 = dword_140019000;
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v21 = v4;
LABEL_11:
      v24 = 4;
      v23 = &v21;
      tlgWriteTransfer_EtwWriteTransfer(v8, (int)&byte_140016D91, v5, v6, Sid, &v22);
      return (unsigned int)Acl;
    }
    return (unsigned int)Acl;
  }
  Acl = RtlSetOwnerSecurityDescriptor(SecurityDescriptor, SeExports->SeLocalSystemSid, 0);
  if ( Acl >= 0 )
  {
    Acl = RtlSetGroupSecurityDescriptor(SecurityDescriptor, SeExports->SeLocalSystemSid, 0);
    if ( Acl >= 0 )
    {
      v9 = RtlLengthSid(SeExports->SeTrustedInstallerSid);
      v10 = RtlLengthSid(SeExports->SeLocalSystemSid) + 24 + v9;
      Pool2 = (struct _ACL *)ExAllocatePool2(256, v10, 1098081858);
      if ( !Pool2 )
      {
        Acl = -1073741801;
        if ( (unsigned int)dword_140019000 > 3 )
        {
          v21 = -1073741801;
          goto LABEL_11;
        }
        return (unsigned int)Acl;
      }
      v12 = 0;
      Acl = RtlSetControlSecurityDescriptor(SecurityDescriptor, 0x3000u, 0x3000u);
      if ( Acl >= 0 )
      {
        Acl = RtlCreateAcl(Pool2, v10, 2u);
        if ( Acl >= 0 )
        {
          Acl = RtlAddAccessAllowedAceEx(Pool2, Pool2->AclRevision, v2, 0x1F01FFu, SeExports->SeTrustedInstallerSid);
          if ( Acl >= 0 )
          {
            Acl = RtlAddAccessAllowedAceEx(Pool2, Pool2->AclRevision, v2, 0x1F01FFu, SeExports->SeLocalSystemSid);
            if ( Acl >= 0 )
            {
              Acl = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, Pool2, 0);
              if ( Acl >= 0 )
              {
                v16 = RtlLengthSid(SeExports->SeHighMandatorySid) + 16;
                v17 = (struct _ACL *)ExAllocatePool2(256, v16, 1098081858);
                v12 = v17;
                if ( !v17 )
                {
                  v13 = dword_140019000;
                  Acl = -1073741801;
                  if ( (unsigned int)dword_140019000 <= 3 )
                    goto LABEL_26;
                  v21 = -1073741801;
                  v23 = &v21;
                  goto LABEL_25;
                }
                Acl = RtlCreateAcl(v17, v16, 2u);
                if ( Acl >= 0 )
                {
                  LODWORD(LabelSid) = 7;
                  Acl = RtlAddMandatoryAce(v12, 2u, v2, (ULONG)SeExports->SeHighMandatorySid, 0x11u, LabelSid);
                  if ( Acl >= 0 )
                  {
                    Acl = RtlSetSaclSecurityDescriptor(SecurityDescriptor, 1u, v12, 0);
                    if ( Acl >= 0 )
                      return (unsigned int)Acl;
                  }
                }
              }
            }
          }
        }
      }
      if ( (unsigned int)dword_140019000 <= 3 )
        goto LABEL_26;
      v23 = &v21;
      v21 = Acl;
LABEL_25:
      v24 = 4;
      tlgWriteTransfer_EtwWriteTransfer(v13, (int)&byte_140016D91, v14, v15, Sid, &v22);
LABEL_26:
      ExFreePoolWithTag(Pool2, 0);
      if ( v12 )
        ExFreePoolWithTag(v12, 0);
      return (unsigned int)Acl;
    }
  }
  if ( (unsigned int)dword_140019000 > 3 )
  {
    v21 = Acl;
    goto LABEL_11;
  }
  return (unsigned int)Acl;
}

```

## disassembly

```asm
0x140012bf4  mov     [rsp-38h+arg_10], rbx
0x140012bf9  push    rbp
0x140012bfa  push    rsi
0x140012bfb  push    rdi
0x140012bfc  push    r12
0x140012bfe  push    r13
0x140012c00  push    r14
0x140012c02  push    r15
0x140012c04  mov     rbp, rsp
0x140012c07  sub     rsp, 70h
0x140012c0b  mov     rax, cs:__security_cookie
0x140012c12  xor     rax, rsp
0x140012c15  mov     [rbp+var_8], rax
0x140012c19  movzx   r12d, dl
0x140012c1d  mov     rsi, rcx
0x140012c20  mov     edx, 1; Revision
0x140012c25  call    cs:__imp_RtlCreateSecurityDescriptor
0x140012c2c  nop     dword ptr [rax+rax+00h]
0x140012c31  xor     r13d, r13d
0x140012c34  mov     ebx, eax
0x140012c36  test    eax, eax
0x140012c38  jns     short loc_140012C51
0x140012c3a  mov     ecx, cs:dword_140019000
0x140012c40  cmp     ecx, 3
0x140012c43  jbe     loc_140012F81
0x140012c49  mov     [rbp+var_40], eax
0x140012c4c  jmp     loc_140012D35
0x140012c51  mov     rax, cs:__imp_SeExports
0x140012c58  xor     r8d, r8d; OwnerDefaulted
0x140012c5b  mov     rcx, rsi; SecurityDescriptor
0x140012c5e  mov     rdx, [rax]
0x140012c61  mov     rdx, [rdx+108h]; Owner
0x140012c68  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x140012c6f  nop     dword ptr [rax+rax+00h]
0x140012c74  mov     ebx, eax
0x140012c76  test    eax, eax
0x140012c78  js      short loc_140012CA3
0x140012c7a  mov     rax, cs:__imp_SeExports
0x140012c81  xor     r8d, r8d; GroupDefaulted
0x140012c84  mov     rcx, rsi; SecurityDescriptor
0x140012c87  mov     rdx, [rax]
0x140012c8a  mov     rdx, [rdx+108h]; Group
0x140012c91  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x140012c98  nop     dword ptr [rax+rax+00h]
0x140012c9d  mov     ebx, eax
0x140012c9f  test    eax, eax
0x140012ca1  jns     short loc_140012CB7
0x140012ca3  mov     eax, cs:dword_140019000
0x140012ca9  cmp     eax, 3
0x140012cac  jbe     loc_140012F81
0x140012cb2  mov     [rbp+var_40], ebx
0x140012cb5  jmp     short loc_140012D35
0x140012cb7  mov     rax, cs:__imp_SeExports
0x140012cbe  mov     rcx, [rax]
0x140012cc1  mov     rcx, [rcx+220h]; Sid
0x140012cc8  call    cs:__imp_RtlLengthSid
0x140012ccf  nop     dword ptr [rax+rax+00h]
0x140012cd4  mov     rcx, cs:__imp_SeExports
0x140012cdb  mov     r15d, eax
0x140012cde  mov     rcx, [rcx]
0x140012ce1  mov     rcx, [rcx+108h]; Sid
0x140012ce8  call    cs:__imp_RtlLengthSid
0x140012cef  nop     dword ptr [rax+rax+00h]
0x140012cf4  mov     ecx, 100h
0x140012cf9  mov     r8d, 41736642h
0x140012cff  add     eax, 18h
0x140012d02  add     r15d, eax
0x140012d05  mov     edx, r15d
0x140012d08  call    cs:__imp_ExAllocatePool2
0x140012d0f  nop     dword ptr [rax+rax+00h]
0x140012d14  mov     r14, rax
0x140012d17  test    rax, rax
0x140012d1a  jnz     short loc_140012D5F
0x140012d1c  mov     eax, cs:dword_140019000
0x140012d22  mov     edx, 0C0000017h
0x140012d27  mov     ebx, edx
0x140012d29  cmp     eax, 3
0x140012d2c  jbe     loc_140012F81
0x140012d32  mov     [rbp+var_40], edx
0x140012d35  lea     rax, [rbp+var_40]
0x140012d39  mov     [rbp+var_10], 4
0x140012d41  mov     [rbp+var_18], rax
0x140012d45  lea     rdx, byte_140016D91; int
0x140012d4c  lea     rax, [rbp+var_38]
0x140012d50  mov     [rsp+70h+LabelSid], rax; PEVENT_DATA_DESCRIPTOR
0x140012d55  call    _tlgWriteTransfer_EtwWriteTransfer
0x140012d5a  jmp     loc_140012F81
0x140012d5f  mov     edx, 3000h; ControlBitsOfInterest
0x140012d64  mov     rcx, rsi; SecurityDescriptor
0x140012d67  mov     r8d, edx; ControlBitsToSet
0x140012d6a  mov     rdi, r13
0x140012d6d  call    cs:__imp_RtlSetControlSecurityDescriptor
0x140012d74  nop     dword ptr [rax+rax+00h]
0x140012d79  mov     ebx, eax
0x140012d7b  test    eax, eax
0x140012d7d  js      loc_140012F27
0x140012d83  mov     r8d, 2; AclRevision
0x140012d89  mov     edx, r15d; AclLength
0x140012d8c  mov     rcx, r14; Acl
0x140012d8f  call    cs:__imp_RtlCreateAcl
0x140012d96  nop     dword ptr [rax+rax+00h]
0x140012d9b  mov     ebx, eax
0x140012d9d  test    eax, eax
0x140012d9f  js      loc_140012F27
0x140012da5  mov     rax, cs:__imp_SeExports
0x140012dac  mov     r15d, r12d
0x140012daf  movzx   edx, byte ptr [r14]; AceRevision
0x140012db3  mov     r12d, 1F01FFh
0x140012db9  mov     r9d, r12d; AccessMask
0x140012dbc  mov     r8d, r15d; AceFlags
0x140012dbf  mov     rcx, r14; Acl
0x140012dc2  mov     rax, [rax]
0x140012dc5  mov     rax, [rax+220h]
0x140012dcc  mov     [rsp+70h+Sid], rax; Sid
0x140012dd1  call    cs:__imp_RtlAddAccessAllowedAceEx
0x140012dd8  nop     dword ptr [rax+rax+00h]
0x140012ddd  mov     ebx, eax
0x140012ddf  test    eax, eax
0x140012de1  js      loc_140012F27
0x140012de7  mov     rax, cs:__imp_SeExports
0x140012dee  mov     r9d, r12d; AccessMask
0x140012df1  movzx   edx, byte ptr [r14]; AceRevision
0x140012df5  mov     r8d, r15d; AceFlags
0x140012df8  mov     rcx, r14; Acl
0x140012dfb  mov     rax, [rax]
0x140012dfe  mov     rax, [rax+108h]
0x140012e05  mov     [rsp+70h+Sid], rax; Sid
0x140012e0a  call    cs:__imp_RtlAddAccessAllowedAceEx
0x140012e11  nop     dword ptr [rax+rax+00h]
0x140012e16  mov     ebx, eax
0x140012e18  test    eax, eax
0x140012e1a  js      loc_140012F27
0x140012e20  xor     r9d, r9d; DaclDefaulted
0x140012e23  mov     r8, r14; Dacl
0x140012e26  mov     dl, 1; DaclPresent
0x140012e28  mov     rcx, rsi; SecurityDescriptor
0x140012e2b  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140012e32  nop     dword ptr [rax+rax+00h]
0x140012e37  mov     ebx, eax
0x140012e39  test    eax, eax
0x140012e3b  js      loc_140012F27
0x140012e41  mov     rax, cs:__imp_SeExports
0x140012e48  mov     rcx, [rax]
0x140012e4b  mov     rcx, [rcx+1F0h]; Sid
0x140012e52  call    cs:__imp_RtlLengthSid
0x140012e59  nop     dword ptr [rax+rax+00h]
0x140012e5e  mov     ecx, 100h
0x140012e63  mov     r8d, 41736642h
0x140012e69  lea     ebx, [rax+10h]
0x140012e6c  mov     edx, ebx
0x140012e6e  call    cs:__imp_ExAllocatePool2
0x140012e75  nop     dword ptr [rax+rax+00h]
0x140012e7a  mov     rdi, rax
0x140012e7d  test    rax, rax
0x140012e80  jnz     short loc_140012EB1
0x140012e82  mov     ecx, cs:dword_140019000
0x140012e88  mov     edx, 0C0000017h
0x140012e8d  mov     ebx, edx
0x140012e8f  cmp     ecx, 3
0x140012e92  jbe     loc_140012F5A
0x140012e98  lea     rax, [rbp+var_40]
0x140012e9c  mov     [rbp+var_40], edx
0x140012e9f  mov     [rbp+var_18], rax
0x140012ea3  lea     rax, [rbp+var_38]
0x140012ea7  mov     [rsp+70h+LabelSid], rax
0x140012eac  jmp     loc_140012F46
0x140012eb1  mov     r12d, 2
0x140012eb7  mov     edx, ebx; AclLength
0x140012eb9  mov     r8d, r12d; AclRevision
0x140012ebc  mov     rcx, rdi; Acl
0x140012ebf  call    cs:__imp_RtlCreateAcl
0x140012ec6  nop     dword ptr [rax+rax+00h]
0x140012ecb  mov     ebx, eax
0x140012ecd  test    eax, eax
0x140012ecf  js      short loc_140012F27
0x140012ed1  mov     rax, cs:__imp_SeExports
0x140012ed8  mov     r8d, r15d; Flags
0x140012edb  mov     dword ptr [rsp+70h+LabelSid], 7; LabelSid
0x140012ee3  mov     edx, r12d; Revision
0x140012ee6  mov     rcx, rdi; Acl
0x140012ee9  mov     byte ptr [rsp+70h+Sid], 11h; int
0x140012eee  mov     r9, [rax]
0x140012ef1  mov     r9, [r9+1F0h]; MandatoryFlags
0x140012ef8  call    cs:__imp_RtlAddMandatoryAce
0x140012eff  nop     dword ptr [rax+rax+00h]
0x140012f04  mov     ebx, eax
0x140012f06  test    eax, eax
0x140012f08  js      short loc_140012F27
0x140012f0a  xor     r9d, r9d; SaclDefaulted
0x140012f0d  mov     r8, rdi; Sacl
0x140012f10  mov     dl, 1; SaclPresent
0x140012f12  mov     rcx, rsi; SecurityDescriptor
0x140012f15  call    cs:__imp_RtlSetSaclSecurityDescriptor
0x140012f1c  nop     dword ptr [rax+rax+00h]
0x140012f21  mov     ebx, eax
0x140012f23  test    eax, eax
0x140012f25  jns     short loc_140012F81
0x140012f27  mov     eax, cs:dword_140019000
0x140012f2d  cmp     eax, 3
0x140012f30  jbe     short loc_140012F5A
0x140012f32  lea     rax, [rbp+var_40]
0x140012f36  mov     [rbp+var_18], rax
0x140012f3a  lea     rax, [rbp+var_38]
0x140012f3e  mov     [rsp+70h+LabelSid], rax; PEVENT_DATA_DESCRIPTOR
0x140012f43  mov     [rbp+var_40], ebx
0x140012f46  lea     rdx, byte_140016D91; int
0x140012f4d  mov     [rbp+var_10], 4
0x140012f55  call    _tlgWriteTransfer_EtwWriteTransfer
0x140012f5a  xor     edx, edx; Tag
0x140012f5c  mov     rcx, r14; P
0x140012f5f  call    cs:__imp_ExFreePoolWithTag
0x140012f66  nop     dword ptr [rax+rax+00h]
0x140012f6b  test    rdi, rdi
0x140012f6e  jz      short loc_140012F81
0x140012f70  xor     edx, edx; Tag
0x140012f72  mov     rcx, rdi; P
0x140012f75  call    cs:__imp_ExFreePoolWithTag
0x140012f7c  nop     dword ptr [rax+rax+00h]
0x140012f81  mov     eax, ebx
0x140012f83  mov     rcx, [rbp+var_8]
0x140012f87  xor     rcx, rsp; StackCookie
0x140012f8a  call    __security_check_cookie
0x140012f8f  mov     rbx, [rsp+70h+arg_10]
0x140012f97  add     rsp, 70h
0x140012f9b  pop     r15
0x140012f9d  pop     r14
0x140012f9f  pop     r13
0x140012fa1  pop     r12
0x140012fa3  pop     rdi
0x140012fa4  pop     rsi
0x140012fa5  pop     rbp
0x140012fa6  retn
```
