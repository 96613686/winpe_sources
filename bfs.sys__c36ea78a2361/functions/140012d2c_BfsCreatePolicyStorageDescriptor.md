# BfsCreatePolicyStorageDescriptor

- ea: `0x140012d2c`
- end: `0x1400130e0`
- name: `BfsCreatePolicyStorageDescriptor`
- size: `948`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor, unsigned __int8)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14001f078`

## callees

- `0x140001008`
- `0x140012d2c`
- `0x140013860`

## import_xrefs

- `ntoskrnl!RtlLengthSid` at `0x140012e00`
- `ntoskrnl!RtlLengthSid` at `0x140012e20`
- `ntoskrnl!RtlLengthSid` at `0x140012f8a`
- `ntoskrnl!RtlLengthSid` at `0x140012e00`
- `ntoskrnl!RtlLengthSid` at `0x140012e20`
- `ntoskrnl!RtlLengthSid` at `0x140012f8a`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140012f63`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140012f63`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140012d5d`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140012d5d`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140012f09`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140012f42`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140012f09`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140012f42`
- `ntoskrnl!RtlCreateAcl` at `0x140012ec7`
- `ntoskrnl!RtlCreateAcl` at `0x140012ff7`
- `ntoskrnl!RtlCreateAcl` at `0x140012ec7`
- `ntoskrnl!RtlCreateAcl` at `0x140012ff7`
- `ntoskrnl!SeExports` at `0x140012d89`
- `ntoskrnl!SeExports` at `0x140012db2`
- `ntoskrnl!SeExports` at `0x140012def`
- `ntoskrnl!SeExports` at `0x140012e0c`
- `ntoskrnl!SeExports` at `0x140012edd`
- `ntoskrnl!SeExports` at `0x140012f1f`
- `ntoskrnl!SeExports` at `0x140012f79`
- `ntoskrnl!SeExports` at `0x140013009`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013097`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400130ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013097`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400130ad`
- `ntoskrnl!ExAllocatePool2` at `0x140012e40`
- `ntoskrnl!ExAllocatePool2` at `0x140012fa6`
- `ntoskrnl!ExAllocatePool2` at `0x140012e40`
- `ntoskrnl!ExAllocatePool2` at `0x140012fa6`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x140012da0`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x140012da0`
- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x140012dc9`
- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x140012dc9`
- `ntoskrnl!RtlSetControlSecurityDescriptor` at `0x140012ea5`
- `ntoskrnl!RtlSetControlSecurityDescriptor` at `0x140012ea5`
- `ntoskrnl!RtlAddMandatoryAce` at `0x140013030`
- `ntoskrnl!RtlAddMandatoryAce` at `0x140013030`
- `ntoskrnl!RtlSetSaclSecurityDescriptor` at `0x14001304d`
- `ntoskrnl!RtlSetSaclSecurityDescriptor` at `0x14001304d`

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
  ULONG v16; // ebx
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
0x140012d2c  mov     [rsp-38h+arg_10], rbx
0x140012d31  push    rbp
0x140012d32  push    rsi
0x140012d33  push    rdi
0x140012d34  push    r12
0x140012d36  push    r13
0x140012d38  push    r14
0x140012d3a  push    r15
0x140012d3c  mov     rbp, rsp
0x140012d3f  sub     rsp, 70h
0x140012d43  mov     rax, cs:__security_cookie
0x140012d4a  xor     rax, rsp
0x140012d4d  mov     [rbp+var_8], rax
0x140012d51  movzx   r12d, dl
0x140012d55  mov     rsi, rcx
0x140012d58  mov     edx, 1; Revision
0x140012d5d  call    cs:__imp_RtlCreateSecurityDescriptor
0x140012d64  nop     dword ptr [rax+rax+00h]
0x140012d69  xor     r13d, r13d
0x140012d6c  mov     ebx, eax
0x140012d6e  test    eax, eax
0x140012d70  jns     short loc_140012D89
0x140012d72  mov     ecx, cs:dword_140019000
0x140012d78  cmp     ecx, 3
0x140012d7b  jbe     loc_1400130B9
0x140012d81  mov     [rbp+var_40], eax
0x140012d84  jmp     loc_140012E6D
0x140012d89  mov     rax, cs:__imp_SeExports
0x140012d90  xor     r8d, r8d; OwnerDefaulted
0x140012d93  mov     rcx, rsi; SecurityDescriptor
0x140012d96  mov     rdx, [rax]
0x140012d99  mov     rdx, [rdx+108h]; Owner
0x140012da0  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x140012da7  nop     dword ptr [rax+rax+00h]
0x140012dac  mov     ebx, eax
0x140012dae  test    eax, eax
0x140012db0  js      short loc_140012DDB
0x140012db2  mov     rax, cs:__imp_SeExports
0x140012db9  xor     r8d, r8d; GroupDefaulted
0x140012dbc  mov     rcx, rsi; SecurityDescriptor
0x140012dbf  mov     rdx, [rax]
0x140012dc2  mov     rdx, [rdx+108h]; Group
0x140012dc9  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x140012dd0  nop     dword ptr [rax+rax+00h]
0x140012dd5  mov     ebx, eax
0x140012dd7  test    eax, eax
0x140012dd9  jns     short loc_140012DEF
0x140012ddb  mov     eax, cs:dword_140019000
0x140012de1  cmp     eax, 3
0x140012de4  jbe     loc_1400130B9
0x140012dea  mov     [rbp+var_40], ebx
0x140012ded  jmp     short loc_140012E6D
0x140012def  mov     rax, cs:__imp_SeExports
0x140012df6  mov     rcx, [rax]
0x140012df9  mov     rcx, [rcx+220h]; Sid
0x140012e00  call    cs:__imp_RtlLengthSid
0x140012e07  nop     dword ptr [rax+rax+00h]
0x140012e0c  mov     rcx, cs:__imp_SeExports
0x140012e13  mov     r15d, eax
0x140012e16  mov     rcx, [rcx]
0x140012e19  mov     rcx, [rcx+108h]; Sid
0x140012e20  call    cs:__imp_RtlLengthSid
0x140012e27  nop     dword ptr [rax+rax+00h]
0x140012e2c  mov     ecx, 100h
0x140012e31  mov     r8d, 41736642h
0x140012e37  add     eax, 18h
0x140012e3a  add     r15d, eax
0x140012e3d  mov     edx, r15d
0x140012e40  call    cs:__imp_ExAllocatePool2
0x140012e47  nop     dword ptr [rax+rax+00h]
0x140012e4c  mov     r14, rax
0x140012e4f  test    rax, rax
0x140012e52  jnz     short loc_140012E97
0x140012e54  mov     eax, cs:dword_140019000
0x140012e5a  mov     edx, 0C0000017h
0x140012e5f  mov     ebx, edx
0x140012e61  cmp     eax, 3
0x140012e64  jbe     loc_1400130B9
0x140012e6a  mov     [rbp+var_40], edx
0x140012e6d  lea     rax, [rbp+var_40]
0x140012e71  mov     [rbp+var_10], 4
0x140012e79  mov     [rbp+var_18], rax
0x140012e7d  lea     rdx, byte_140016D91; int
0x140012e84  lea     rax, [rbp+var_38]
0x140012e88  mov     [rsp+70h+LabelSid], rax; PEVENT_DATA_DESCRIPTOR
0x140012e8d  call    _tlgWriteTransfer_EtwWriteTransfer
0x140012e92  jmp     loc_1400130B9
0x140012e97  mov     edx, 3000h; ControlBitsOfInterest
0x140012e9c  mov     rcx, rsi; SecurityDescriptor
0x140012e9f  mov     r8d, edx; ControlBitsToSet
0x140012ea2  mov     rdi, r13
0x140012ea5  call    cs:__imp_RtlSetControlSecurityDescriptor
0x140012eac  nop     dword ptr [rax+rax+00h]
0x140012eb1  mov     ebx, eax
0x140012eb3  test    eax, eax
0x140012eb5  js      loc_14001305F
0x140012ebb  mov     r8d, 2; AclRevision
0x140012ec1  mov     edx, r15d; AclLength
0x140012ec4  mov     rcx, r14; Acl
0x140012ec7  call    cs:__imp_RtlCreateAcl
0x140012ece  nop     dword ptr [rax+rax+00h]
0x140012ed3  mov     ebx, eax
0x140012ed5  test    eax, eax
0x140012ed7  js      loc_14001305F
0x140012edd  mov     rax, cs:__imp_SeExports
0x140012ee4  mov     r15d, r12d
0x140012ee7  movzx   edx, byte ptr [r14]; AceRevision
0x140012eeb  mov     r12d, 1F01FFh
0x140012ef1  mov     r9d, r12d; AccessMask
0x140012ef4  mov     r8d, r15d; AceFlags
0x140012ef7  mov     rcx, r14; Acl
0x140012efa  mov     rax, [rax]
0x140012efd  mov     rax, [rax+220h]
0x140012f04  mov     [rsp+70h+Sid], rax; Sid
0x140012f09  call    cs:__imp_RtlAddAccessAllowedAceEx
0x140012f10  nop     dword ptr [rax+rax+00h]
0x140012f15  mov     ebx, eax
0x140012f17  test    eax, eax
0x140012f19  js      loc_14001305F
0x140012f1f  mov     rax, cs:__imp_SeExports
0x140012f26  mov     r9d, r12d; AccessMask
0x140012f29  movzx   edx, byte ptr [r14]; AceRevision
0x140012f2d  mov     r8d, r15d; AceFlags
0x140012f30  mov     rcx, r14; Acl
0x140012f33  mov     rax, [rax]
0x140012f36  mov     rax, [rax+108h]
0x140012f3d  mov     [rsp+70h+Sid], rax; Sid
0x140012f42  call    cs:__imp_RtlAddAccessAllowedAceEx
0x140012f49  nop     dword ptr [rax+rax+00h]
0x140012f4e  mov     ebx, eax
0x140012f50  test    eax, eax
0x140012f52  js      loc_14001305F
0x140012f58  xor     r9d, r9d; DaclDefaulted
0x140012f5b  mov     r8, r14; Dacl
0x140012f5e  mov     dl, 1; DaclPresent
0x140012f60  mov     rcx, rsi; SecurityDescriptor
0x140012f63  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140012f6a  nop     dword ptr [rax+rax+00h]
0x140012f6f  mov     ebx, eax
0x140012f71  test    eax, eax
0x140012f73  js      loc_14001305F
0x140012f79  mov     rax, cs:__imp_SeExports
0x140012f80  mov     rcx, [rax]
0x140012f83  mov     rcx, [rcx+1F0h]; Sid
0x140012f8a  call    cs:__imp_RtlLengthSid
0x140012f91  nop     dword ptr [rax+rax+00h]
0x140012f96  mov     ecx, 100h
0x140012f9b  mov     r8d, 41736642h
0x140012fa1  lea     ebx, [rax+10h]
0x140012fa4  mov     edx, ebx
0x140012fa6  call    cs:__imp_ExAllocatePool2
0x140012fad  nop     dword ptr [rax+rax+00h]
0x140012fb2  mov     rdi, rax
0x140012fb5  test    rax, rax
0x140012fb8  jnz     short loc_140012FE9
0x140012fba  mov     ecx, cs:dword_140019000
0x140012fc0  mov     edx, 0C0000017h
0x140012fc5  mov     ebx, edx
0x140012fc7  cmp     ecx, 3
0x140012fca  jbe     loc_140013092
0x140012fd0  lea     rax, [rbp+var_40]
0x140012fd4  mov     [rbp+var_40], edx
0x140012fd7  mov     [rbp+var_18], rax
0x140012fdb  lea     rax, [rbp+var_38]
0x140012fdf  mov     [rsp+70h+LabelSid], rax
0x140012fe4  jmp     loc_14001307E
0x140012fe9  mov     r12d, 2
0x140012fef  mov     edx, ebx; AclLength
0x140012ff1  mov     r8d, r12d; AclRevision
0x140012ff4  mov     rcx, rdi; Acl
0x140012ff7  call    cs:__imp_RtlCreateAcl
0x140012ffe  nop     dword ptr [rax+rax+00h]
0x140013003  mov     ebx, eax
0x140013005  test    eax, eax
0x140013007  js      short loc_14001305F
0x140013009  mov     rax, cs:__imp_SeExports
0x140013010  mov     r8d, r15d; Flags
0x140013013  mov     dword ptr [rsp+70h+LabelSid], 7; LabelSid
0x14001301b  mov     edx, r12d; Revision
0x14001301e  mov     rcx, rdi; Acl
0x140013021  mov     byte ptr [rsp+70h+Sid], 11h; int
0x140013026  mov     r9, [rax]
0x140013029  mov     r9, [r9+1F0h]; MandatoryFlags
0x140013030  call    cs:__imp_RtlAddMandatoryAce
0x140013037  nop     dword ptr [rax+rax+00h]
0x14001303c  mov     ebx, eax
0x14001303e  test    eax, eax
0x140013040  js      short loc_14001305F
0x140013042  xor     r9d, r9d; SaclDefaulted
0x140013045  mov     r8, rdi; Sacl
0x140013048  mov     dl, 1; SaclPresent
0x14001304a  mov     rcx, rsi; SecurityDescriptor
0x14001304d  call    cs:__imp_RtlSetSaclSecurityDescriptor
0x140013054  nop     dword ptr [rax+rax+00h]
0x140013059  mov     ebx, eax
0x14001305b  test    eax, eax
0x14001305d  jns     short loc_1400130B9
0x14001305f  mov     eax, cs:dword_140019000
0x140013065  cmp     eax, 3
0x140013068  jbe     short loc_140013092
0x14001306a  lea     rax, [rbp+var_40]
0x14001306e  mov     [rbp+var_18], rax
0x140013072  lea     rax, [rbp+var_38]
0x140013076  mov     [rsp+70h+LabelSid], rax; PEVENT_DATA_DESCRIPTOR
0x14001307b  mov     [rbp+var_40], ebx
0x14001307e  lea     rdx, byte_140016D91; int
0x140013085  mov     [rbp+var_10], 4
0x14001308d  call    _tlgWriteTransfer_EtwWriteTransfer
0x140013092  xor     edx, edx; Tag
0x140013094  mov     rcx, r14; P
0x140013097  call    cs:__imp_ExFreePoolWithTag
0x14001309e  nop     dword ptr [rax+rax+00h]
0x1400130a3  test    rdi, rdi
0x1400130a6  jz      short loc_1400130B9
0x1400130a8  xor     edx, edx; Tag
0x1400130aa  mov     rcx, rdi; P
0x1400130ad  call    cs:__imp_ExFreePoolWithTag
0x1400130b4  nop     dword ptr [rax+rax+00h]
0x1400130b9  mov     eax, ebx
0x1400130bb  mov     rcx, [rbp+var_8]
0x1400130bf  xor     rcx, rsp; StackCookie
0x1400130c2  call    __security_check_cookie
0x1400130c7  mov     rbx, [rsp+70h+arg_10]
0x1400130cf  add     rsp, 70h
0x1400130d3  pop     r15
0x1400130d5  pop     r14
0x1400130d7  pop     r13
0x1400130d9  pop     r12
0x1400130db  pop     rdi
0x1400130dc  pop     rsi
0x1400130dd  pop     rbp
0x1400130de  retn
```
