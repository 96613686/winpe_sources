# BfsUpdateSecurityDescriptor

- ea: `0x1400130e8`
- end: `0x1400132bb`
- name: `BfsUpdateSecurityDescriptor`
- size: `467`
- prototype: `__int64 __fastcall(HANDLE Handle, PACL Acl, PACL Dacl, ULONG AclLength, PSID, ACCESS_MASK AccessMask, char)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14000e6f0`

## callees

- `0x140001008`
- `0x1400130e8`
- `0x140013860`

## import_xrefs

- `ntoskrnl!ZwSetSecurityObject` at `0x140013284`
- `ntoskrnl!ZwSetSecurityObject` at `0x140013284`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140013264`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140013264`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140013241`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140013241`
- `ntoskrnl!RtlAddAce` at `0x140013229`
- `ntoskrnl!RtlAddAce` at `0x140013229`
- `ntoskrnl!RtlGetAcesBufferSize` at `0x1400131fe`
- `ntoskrnl!RtlGetAcesBufferSize` at `0x1400131fe`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400131a8`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400131a8`
- `ntoskrnl!RtlCreateAcl` at `0x140013142`
- `ntoskrnl!RtlCreateAcl` at `0x140013142`
- `ntoskrnl!RtlGetAce` at `0x1400131e5`
- `ntoskrnl!RtlGetAce` at `0x1400131e5`
- `ntoskrnl!RtlAddAccessDeniedAceEx` at `0x1400131b6`
- `ntoskrnl!RtlAddAccessDeniedAceEx` at `0x1400131b6`

## pseudocode

```c
__int64 __fastcall BfsUpdateSecurityDescriptor(
        HANDLE Handle,
        PACL Acl,
        PACL Dacl,
        ULONG AclLength,
        PSID a5,
        ACCESS_MASK AccessMask,
        char a7)
{
  ULONG AclRevision; // r8d
  NTSTATUS v11; // eax
  int v12; // r8d
  int v13; // r9d
  NTSTATUS AcesBufferSize; // ebx
  int v15; // ecx
  ULONG v16; // edx
  NTSTATUS v17; // eax
  int Sid; // [rsp+20h] [rbp-81h]
  NTSTATUS v20; // [rsp+30h] [rbp-71h] BYREF
  PVOID Ace; // [rsp+38h] [rbp-69h] BYREF
  ULONG AceListLength; // [rsp+40h] [rbp-61h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+48h] [rbp-59h] BYREF
  __int64 v24; // [rsp+68h] [rbp-39h]
  struct _EVENT_DATA_DESCRIPTOR v25; // [rsp+70h] [rbp-31h] BYREF
  NTSTATUS *v26; // [rsp+90h] [rbp-11h]
  __int64 v27; // [rsp+98h] [rbp-9h]

  AclRevision = Acl->AclRevision;
  AceListLength = 0;
  Ace = 0;
  v24 = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v11 = RtlCreateAcl(Dacl, AclLength, AclRevision);
  AcesBufferSize = v11;
  if ( v11 >= 0 )
  {
    v16 = Dacl->AclRevision;
    if ( a7 )
      v17 = RtlAddAccessAllowedAceEx(Dacl, v16, 0, AccessMask, a5);
    else
      v17 = RtlAddAccessDeniedAceEx(Dacl, v16, 0, AccessMask, a5);
    AcesBufferSize = v17;
    if ( v17 >= 0 )
    {
      AcesBufferSize = RtlGetAce(Acl, 0, &Ace);
      if ( AcesBufferSize >= 0 )
      {
        AcesBufferSize = RtlGetAcesBufferSize(Acl, &AceListLength);
        if ( AcesBufferSize >= 0 )
        {
          AcesBufferSize = RtlAddAce(Dacl, 2u, 1u, Ace, AceListLength);
          if ( AcesBufferSize >= 0 )
          {
            AcesBufferSize = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
            if ( AcesBufferSize >= 0 )
            {
              AcesBufferSize = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, Dacl, 0);
              if ( AcesBufferSize >= 0 )
              {
                AcesBufferSize = ZwSetSecurityObject(Handle, 4u, SecurityDescriptor);
                if ( AcesBufferSize >= 0 )
                  return 0;
              }
            }
          }
        }
      }
    }
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v20 = AcesBufferSize;
      goto LABEL_4;
    }
  }
  else
  {
    v15 = dword_140019000;
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v20 = v11;
LABEL_4:
      v27 = 4;
      v26 = &v20;
      tlgWriteTransfer_EtwWriteTransfer(v15, (int)&byte_140016D91, v12, v13, Sid, &v25);
    }
  }
  return (unsigned int)AcesBufferSize;
}

```

## disassembly

```asm
0x1400130e8  push    rbp
0x1400130ea  push    rbx
0x1400130eb  push    rsi
0x1400130ec  push    rdi
0x1400130ed  push    r14
0x1400130ef  push    r15
0x1400130f1  lea     rbp, [rsp-17h]
0x1400130f6  sub     rsp, 0B8h
0x1400130fd  mov     rax, cs:__security_cookie
0x140013104  xor     rax, rsp
0x140013107  mov     [rbp+3Fh+var_40], rax
0x14001310b  mov     r14, [rbp+3Fh+arg_20]
0x14001310f  mov     rdi, r8
0x140013112  movzx   r8d, byte ptr [rdx]; AclRevision
0x140013116  xorps   xmm0, xmm0
0x140013119  mov     rsi, rdx
0x14001311c  mov     [rbp+3Fh+AceListLength], 0
0x140013123  mov     r15, rcx
0x140013126  mov     [rbp+3Fh+Ace], 0
0x14001312e  xor     eax, eax
0x140013130  mov     edx, r9d; AclLength
0x140013133  mov     rcx, rdi; Acl
0x140013136  mov     [rbp+3Fh+var_78], rax
0x14001313a  movups  [rbp+3Fh+SecurityDescriptor], xmm0
0x14001313e  movups  [rbp+3Fh+var_88], xmm0
0x140013142  call    cs:__imp_RtlCreateAcl
0x140013149  nop     dword ptr [rax+rax+00h]
0x14001314e  mov     ebx, eax
0x140013150  test    eax, eax
0x140013152  jns     short loc_140013190
0x140013154  mov     ecx, cs:dword_140019000; int
0x14001315a  cmp     ecx, 3
0x14001315d  jbe     loc_14001329C
0x140013163  mov     [rbp+3Fh+var_B0], eax
0x140013166  lea     rax, [rbp+3Fh+var_B0]
0x14001316a  mov     [rbp+3Fh+var_48], 4
0x140013172  mov     [rbp+3Fh+var_50], rax
0x140013176  lea     rdx, byte_140016D91; int
0x14001317d  lea     rax, [rbp+3Fh+var_70]
0x140013181  mov     [rsp+0E0h+var_B8], rax; PEVENT_DATA_DESCRIPTOR
0x140013186  call    _tlgWriteTransfer_EtwWriteTransfer
0x14001318b  jmp     loc_14001329C
0x140013190  movzx   edx, byte ptr [rdi]; Revision
0x140013193  xor     r8d, r8d; Flags
0x140013196  mov     rcx, rdi; Acl
0x140013199  mov     r9d, [rbp+3Fh+AccessMask]; AccessMask
0x14001319d  mov     [rsp+0E0h+Sid], r14; Sid
0x1400131a2  cmp     [rbp+3Fh+arg_30], r8b
0x1400131a6  jz      short loc_1400131B6
0x1400131a8  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1400131af  nop     dword ptr [rax+rax+00h]
0x1400131b4  jmp     short loc_1400131C2
0x1400131b6  call    cs:__imp_RtlAddAccessDeniedAceEx
0x1400131bd  nop     dword ptr [rax+rax+00h]
0x1400131c2  mov     ebx, eax
0x1400131c4  test    eax, eax
0x1400131c6  jns     short loc_1400131DC
0x1400131c8  mov     eax, cs:dword_140019000
0x1400131ce  cmp     eax, 3
0x1400131d1  jbe     loc_14001329C
0x1400131d7  mov     [rbp+3Fh+var_B0], ebx
0x1400131da  jmp     short loc_140013166
0x1400131dc  lea     r8, [rbp+3Fh+Ace]; Ace
0x1400131e0  xor     edx, edx; AceIndex
0x1400131e2  mov     rcx, rsi; Acl
0x1400131e5  call    cs:__imp_RtlGetAce
0x1400131ec  nop     dword ptr [rax+rax+00h]
0x1400131f1  mov     ebx, eax
0x1400131f3  test    eax, eax
0x1400131f5  js      short loc_1400131C8
0x1400131f7  lea     rdx, [rbp+3Fh+AceListLength]
0x1400131fb  mov     rcx, rsi
0x1400131fe  call    cs:__imp_RtlGetAcesBufferSize
0x140013205  nop     dword ptr [rax+rax+00h]
0x14001320a  mov     ebx, eax
0x14001320c  test    eax, eax
0x14001320e  js      short loc_1400131C8
0x140013210  mov     eax, [rbp+3Fh+AceListLength]
0x140013213  mov     esi, 1
0x140013218  mov     r9, [rbp+3Fh+Ace]; AceList
0x14001321c  mov     r8d, esi; StartingAceIndex
0x14001321f  mov     rcx, rdi; Acl
0x140013222  mov     dword ptr [rsp+0E0h+Sid], eax; AceListLength
0x140013226  lea     edx, [rsi+1]; AceRevision
0x140013229  call    cs:__imp_RtlAddAce
0x140013230  nop     dword ptr [rax+rax+00h]
0x140013235  mov     ebx, eax
0x140013237  test    eax, eax
0x140013239  js      short loc_1400131C8
0x14001323b  mov     edx, esi; Revision
0x14001323d  lea     rcx, [rbp+3Fh+SecurityDescriptor]; SecurityDescriptor
0x140013241  call    cs:__imp_RtlCreateSecurityDescriptor
0x140013248  nop     dword ptr [rax+rax+00h]
0x14001324d  mov     ebx, eax
0x14001324f  test    eax, eax
0x140013251  js      loc_1400131C8
0x140013257  xor     r9d, r9d; DaclDefaulted
0x14001325a  lea     rcx, [rbp+3Fh+SecurityDescriptor]; SecurityDescriptor
0x14001325e  mov     r8, rdi; Dacl
0x140013261  mov     dl, sil; DaclPresent
0x140013264  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14001326b  nop     dword ptr [rax+rax+00h]
0x140013270  mov     ebx, eax
0x140013272  test    eax, eax
0x140013274  js      loc_1400131C8
0x14001327a  lea     r8, [rbp+3Fh+SecurityDescriptor]; SecurityDescriptor
0x14001327e  mov     rcx, r15; Handle
0x140013281  lea     edx, [rsi+3]; SecurityInformation
0x140013284  call    cs:__imp_ZwSetSecurityObject
0x14001328b  nop     dword ptr [rax+rax+00h]
0x140013290  mov     ebx, eax
0x140013292  test    eax, eax
0x140013294  js      loc_1400131C8
0x14001329a  xor     ebx, ebx
0x14001329c  mov     eax, ebx
0x14001329e  mov     rcx, [rbp+3Fh+var_40]
0x1400132a2  xor     rcx, rsp; StackCookie
0x1400132a5  call    __security_check_cookie
0x1400132aa  add     rsp, 0B8h
0x1400132b1  pop     r15
0x1400132b3  pop     r14
0x1400132b5  pop     rdi
0x1400132b6  pop     rsi
0x1400132b7  pop     rbx
0x1400132b8  pop     rbp
0x1400132b9  retn
```
