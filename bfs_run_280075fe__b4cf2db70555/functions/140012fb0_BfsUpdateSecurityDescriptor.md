# BfsUpdateSecurityDescriptor

- ea: `0x140012fb0`
- end: `0x140013183`
- name: `BfsUpdateSecurityDescriptor`
- size: `467`
- prototype: `__int64 __fastcall(HANDLE Handle, PACL Acl, PACL Dacl, ULONG AclLength, PSID, ACCESS_MASK AccessMask, char)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14000e560`

## callees

- `0x140001008`
- `0x140012fb0`
- `0x140013730`

## import_xrefs

- `ntoskrnl!ZwSetSecurityObject` at `0x14001314c`
- `ntoskrnl!ZwSetSecurityObject` at `0x14001314c`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14001312c`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14001312c`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140013109`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140013109`
- `ntoskrnl!RtlAddAce` at `0x1400130f1`
- `ntoskrnl!RtlAddAce` at `0x1400130f1`
- `ntoskrnl!RtlGetAcesBufferSize` at `0x1400130c6`
- `ntoskrnl!RtlGetAcesBufferSize` at `0x1400130c6`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140013070`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140013070`
- `ntoskrnl!RtlCreateAcl` at `0x14001300a`
- `ntoskrnl!RtlCreateAcl` at `0x14001300a`
- `ntoskrnl!RtlGetAce` at `0x1400130ad`
- `ntoskrnl!RtlGetAce` at `0x1400130ad`
- `ntoskrnl!RtlAddAccessDeniedAceEx` at `0x14001307e`
- `ntoskrnl!RtlAddAccessDeniedAceEx` at `0x14001307e`

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
0x140012fb0  push    rbp
0x140012fb2  push    rbx
0x140012fb3  push    rsi
0x140012fb4  push    rdi
0x140012fb5  push    r14
0x140012fb7  push    r15
0x140012fb9  lea     rbp, [rsp-17h]
0x140012fbe  sub     rsp, 0B8h
0x140012fc5  mov     rax, cs:__security_cookie
0x140012fcc  xor     rax, rsp
0x140012fcf  mov     [rbp+3Fh+var_40], rax
0x140012fd3  mov     r14, [rbp+3Fh+arg_20]
0x140012fd7  mov     rdi, r8
0x140012fda  movzx   r8d, byte ptr [rdx]; AclRevision
0x140012fde  xorps   xmm0, xmm0
0x140012fe1  mov     rsi, rdx
0x140012fe4  mov     [rbp+3Fh+AceListLength], 0
0x140012feb  mov     r15, rcx
0x140012fee  mov     [rbp+3Fh+Ace], 0
0x140012ff6  xor     eax, eax
0x140012ff8  mov     edx, r9d; AclLength
0x140012ffb  mov     rcx, rdi; Acl
0x140012ffe  mov     [rbp+3Fh+var_78], rax
0x140013002  movups  [rbp+3Fh+SecurityDescriptor], xmm0
0x140013006  movups  [rbp+3Fh+var_88], xmm0
0x14001300a  call    cs:__imp_RtlCreateAcl
0x140013011  nop     dword ptr [rax+rax+00h]
0x140013016  mov     ebx, eax
0x140013018  test    eax, eax
0x14001301a  jns     short loc_140013058
0x14001301c  mov     ecx, cs:dword_140019000; int
0x140013022  cmp     ecx, 3
0x140013025  jbe     loc_140013164
0x14001302b  mov     [rbp+3Fh+var_B0], eax
0x14001302e  lea     rax, [rbp+3Fh+var_B0]
0x140013032  mov     [rbp+3Fh+var_48], 4
0x14001303a  mov     [rbp+3Fh+var_50], rax
0x14001303e  lea     rdx, byte_140016D91; int
0x140013045  lea     rax, [rbp+3Fh+var_70]
0x140013049  mov     [rsp+0E0h+var_B8], rax; PEVENT_DATA_DESCRIPTOR
0x14001304e  call    _tlgWriteTransfer_EtwWriteTransfer
0x140013053  jmp     loc_140013164
0x140013058  movzx   edx, byte ptr [rdi]; Revision
0x14001305b  xor     r8d, r8d; Flags
0x14001305e  mov     rcx, rdi; Acl
0x140013061  mov     r9d, [rbp+3Fh+AccessMask]; AccessMask
0x140013065  mov     [rsp+0E0h+Sid], r14; Sid
0x14001306a  cmp     [rbp+3Fh+arg_30], r8b
0x14001306e  jz      short loc_14001307E
0x140013070  call    cs:__imp_RtlAddAccessAllowedAceEx
0x140013077  nop     dword ptr [rax+rax+00h]
0x14001307c  jmp     short loc_14001308A
0x14001307e  call    cs:__imp_RtlAddAccessDeniedAceEx
0x140013085  nop     dword ptr [rax+rax+00h]
0x14001308a  mov     ebx, eax
0x14001308c  test    eax, eax
0x14001308e  jns     short loc_1400130A4
0x140013090  mov     eax, cs:dword_140019000
0x140013096  cmp     eax, 3
0x140013099  jbe     loc_140013164
0x14001309f  mov     [rbp+3Fh+var_B0], ebx
0x1400130a2  jmp     short loc_14001302E
0x1400130a4  lea     r8, [rbp+3Fh+Ace]; Ace
0x1400130a8  xor     edx, edx; AceIndex
0x1400130aa  mov     rcx, rsi; Acl
0x1400130ad  call    cs:__imp_RtlGetAce
0x1400130b4  nop     dword ptr [rax+rax+00h]
0x1400130b9  mov     ebx, eax
0x1400130bb  test    eax, eax
0x1400130bd  js      short loc_140013090
0x1400130bf  lea     rdx, [rbp+3Fh+AceListLength]
0x1400130c3  mov     rcx, rsi
0x1400130c6  call    cs:__imp_RtlGetAcesBufferSize
0x1400130cd  nop     dword ptr [rax+rax+00h]
0x1400130d2  mov     ebx, eax
0x1400130d4  test    eax, eax
0x1400130d6  js      short loc_140013090
0x1400130d8  mov     eax, [rbp+3Fh+AceListLength]
0x1400130db  mov     esi, 1
0x1400130e0  mov     r9, [rbp+3Fh+Ace]; AceList
0x1400130e4  mov     r8d, esi; StartingAceIndex
0x1400130e7  mov     rcx, rdi; Acl
0x1400130ea  mov     dword ptr [rsp+0E0h+Sid], eax; AceListLength
0x1400130ee  lea     edx, [rsi+1]; AceRevision
0x1400130f1  call    cs:__imp_RtlAddAce
0x1400130f8  nop     dword ptr [rax+rax+00h]
0x1400130fd  mov     ebx, eax
0x1400130ff  test    eax, eax
0x140013101  js      short loc_140013090
0x140013103  mov     edx, esi; Revision
0x140013105  lea     rcx, [rbp+3Fh+SecurityDescriptor]; SecurityDescriptor
0x140013109  call    cs:__imp_RtlCreateSecurityDescriptor
0x140013110  nop     dword ptr [rax+rax+00h]
0x140013115  mov     ebx, eax
0x140013117  test    eax, eax
0x140013119  js      loc_140013090
0x14001311f  xor     r9d, r9d; DaclDefaulted
0x140013122  lea     rcx, [rbp+3Fh+SecurityDescriptor]; SecurityDescriptor
0x140013126  mov     r8, rdi; Dacl
0x140013129  mov     dl, sil; DaclPresent
0x14001312c  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140013133  nop     dword ptr [rax+rax+00h]
0x140013138  mov     ebx, eax
0x14001313a  test    eax, eax
0x14001313c  js      loc_140013090
0x140013142  lea     r8, [rbp+3Fh+SecurityDescriptor]; SecurityDescriptor
0x140013146  mov     rcx, r15; Handle
0x140013149  lea     edx, [rsi+3]; SecurityInformation
0x14001314c  call    cs:__imp_ZwSetSecurityObject
0x140013153  nop     dword ptr [rax+rax+00h]
0x140013158  mov     ebx, eax
0x14001315a  test    eax, eax
0x14001315c  js      loc_140013090
0x140013162  xor     ebx, ebx
0x140013164  mov     eax, ebx
0x140013166  mov     rcx, [rbp+3Fh+var_40]
0x14001316a  xor     rcx, rsp; StackCookie
0x14001316d  call    __security_check_cookie
0x140013172  add     rsp, 0B8h
0x140013179  pop     r15
0x14001317b  pop     r14
0x14001317d  pop     rdi
0x14001317e  pop     rsi
0x14001317f  pop     rbx
0x140013180  pop     rbp
0x140013181  retn
```
