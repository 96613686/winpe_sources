# BfsAdjustRegistryKeySecurity

- ea: `0x14000e560`
- end: `0x14000e83f`
- name: `BfsAdjustRegistryKeySecurity`
- size: `735`
- prototype: `__int64 __fastcall(HANDLE Handle, PSID, ACCESS_MASK AccessMask)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14000ef70`

## callees

- `0x140001008`
- `0x1400044e4`
- `0x14000e560`
- `0x14000f5cc`
- `0x140012fb0`
- `0x140013730`

## import_xrefs

- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14000e6b8`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14000e6b8`
- `ntoskrnl!ZwQuerySecurityObject` at `0x14000e5be`
- `ntoskrnl!ZwQuerySecurityObject` at `0x14000e65f`
- `ntoskrnl!ZwQuerySecurityObject` at `0x14000e5be`
- `ntoskrnl!ZwQuerySecurityObject` at `0x14000e65f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e7f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e809`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e7f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e809`
- `ntoskrnl!ExAllocatePool2` at `0x14000e61b`
- `ntoskrnl!ExAllocatePool2` at `0x14000e72a`
- `ntoskrnl!ExAllocatePool2` at `0x14000e61b`
- `ntoskrnl!ExAllocatePool2` at `0x14000e72a`

## pseudocode

```c
__int64 __fastcall BfsAdjustRegistryKeySecurity(HANDLE Handle, unsigned __int8 *a2, ACCESS_MASK AccessMask)
{
  NTSTATUS v6; // eax
  int v7; // r8d
  int v8; // r9d
  NTSTATUS DaclSecurityDescriptor; // ebx
  int v10; // ecx
  ULONG v11; // ebx
  void *Pool2; // r14
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  ULONG v16; // r15d
  struct _ACL *v17; // rax
  struct _ACL *v18; // rdi
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  int LengthNeeded; // [rsp+20h] [rbp-49h]
  int LengthNeededa; // [rsp+20h] [rbp-49h]
  int LengthNeededb; // [rsp+20h] [rbp-49h]
  int v26; // [rsp+40h] [rbp-29h] BYREF
  unsigned __int8 DaclPresent; // [rsp+44h] [rbp-25h] BYREF
  __int16 v28; // [rsp+45h] [rbp-24h] BYREF
  ULONG v29; // [rsp+48h] [rbp-21h] BYREF
  PACL Dacl; // [rsp+50h] [rbp-19h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v31; // [rsp+58h] [rbp-11h] BYREF
  int *v32; // [rsp+78h] [rbp+Fh]
  __int64 v33; // [rsp+80h] [rbp+17h]

  Dacl = 0;
  DaclPresent = 0;
  v29 = 0;
  v28 = 0;
  v6 = ZwQuerySecurityObject(Handle, 4u, 0, 0, &v29);
  DaclSecurityDescriptor = v6;
  if ( v6 == -1073741789 )
  {
    v11 = v29;
    Pool2 = (void *)ExAllocatePool2(256, v29, 1148413506);
    if ( !Pool2 )
    {
      v10 = -1073741801;
      DaclSecurityDescriptor = -1073741801;
      if ( (unsigned int)dword_140019000 <= 3 )
        return (unsigned int)DaclSecurityDescriptor;
      v26 = -1073741801;
      goto LABEL_4;
    }
    DaclSecurityDescriptor = ZwQuerySecurityObject(Handle, 4u, Pool2, v11, &v29);
    if ( DaclSecurityDescriptor < 0 )
      goto LABEL_9;
    DaclSecurityDescriptor = RtlGetDaclSecurityDescriptor(Pool2, &DaclPresent, &Dacl, (PBOOLEAN)&v28 + 1);
    if ( DaclSecurityDescriptor < 0 )
      goto LABEL_9;
    if ( !DaclPresent )
      goto LABEL_25;
    DaclSecurityDescriptor = BfsVerifyAce(Dacl, a2, (__int64)&v28);
    if ( DaclSecurityDescriptor < 0 )
    {
LABEL_9:
      if ( (unsigned int)dword_140019000 > 3 )
      {
        v26 = DaclSecurityDescriptor;
        v33 = 4;
LABEL_11:
        v32 = &v26;
        tlgWriteTransfer_EtwWriteTransfer(v13, (int)&byte_140016D91, v14, v15, LengthNeededa, &v31);
      }
    }
    else if ( !(_BYTE)v28 )
    {
      v16 = Dacl->AclSize + 16 + 4 * a2[1];
      v17 = (struct _ACL *)ExAllocatePool2(256, v16, 1098081858);
      v18 = v17;
      if ( v17 )
      {
        DaclSecurityDescriptor = BfsUpdateSecurityDescriptor(Handle, Dacl, v17, v16, a2, AccessMask, 0);
        if ( DaclSecurityDescriptor < 0
          || (DaclSecurityDescriptor = BfsRemoveKeyValues(Handle), DaclSecurityDescriptor < 0)
          || (DaclSecurityDescriptor = BfsUpdateSecurityDescriptor(Handle, Dacl, v18, v16, a2, AccessMask, 1),
              DaclSecurityDescriptor < 0) )
        {
          if ( (unsigned int)dword_140019000 > 3 )
          {
            v32 = &v26;
            v26 = DaclSecurityDescriptor;
            v33 = 4;
            tlgWriteTransfer_EtwWriteTransfer(v19, (int)&byte_140016D91, v20, v21, LengthNeededb, &v31);
          }
        }
        ExFreePoolWithTag(v18, 0);
        goto LABEL_25;
      }
      v13 = -1073741801;
      DaclSecurityDescriptor = -1073741801;
      if ( (unsigned int)dword_140019000 > 3 )
      {
        v26 = -1073741801;
        v33 = 4;
        goto LABEL_11;
      }
    }
LABEL_25:
    ExFreePoolWithTag(Pool2, 0);
    return (unsigned int)DaclSecurityDescriptor;
  }
  v10 = dword_140019000;
  if ( (unsigned int)dword_140019000 > 3 )
  {
    v26 = v6;
LABEL_4:
    v33 = 4;
    v32 = &v26;
    tlgWriteTransfer_EtwWriteTransfer(v10, (int)&byte_140016D91, v7, v8, LengthNeeded, &v31);
  }
  return (unsigned int)DaclSecurityDescriptor;
}

```

## disassembly

```asm
0x14000e560  mov     [rsp-8+arg_10], rbx
0x14000e565  push    rbp
0x14000e566  push    rsi
0x14000e567  push    rdi
0x14000e568  push    r12
0x14000e56a  push    r13
0x14000e56c  push    r14
0x14000e56e  push    r15
0x14000e570  lea     rbp, [rsp-27h]
0x14000e575  sub     rsp, 90h
0x14000e57c  mov     rax, cs:__security_cookie
0x14000e583  xor     rax, rsp
0x14000e586  mov     [rbp+57h+var_38], rax
0x14000e58a  xor     edi, edi
0x14000e58c  lea     rax, [rbp+57h+var_7B+3]
0x14000e590  mov     r13d, r8d
0x14000e593  mov     [rbp+57h+Dacl], rdi
0x14000e597  mov     r12, rdx
0x14000e59a  mov     byte ptr [rbp+57h+var_7B+1], dil
0x14000e59e  xor     r9d, r9d; Length
0x14000e5a1  mov     [rbp+57h+DaclPresent], dil
0x14000e5a5  lea     r15d, [rdi+4]
0x14000e5a9  mov     dword ptr [rbp+57h+var_7B+3], edi
0x14000e5ac  mov     edx, r15d; SecurityInformation
0x14000e5af  mov     byte ptr [rbp+57h+var_7B], dil
0x14000e5b3  xor     r8d, r8d; SecurityDescriptor
0x14000e5b6  mov     [rsp+0C0h+LengthNeeded], rax; int
0x14000e5bb  mov     rsi, rcx
0x14000e5be  call    cs:__imp_ZwQuerySecurityObject
0x14000e5c5  nop     dword ptr [rax+rax+00h]
0x14000e5ca  mov     ebx, eax
0x14000e5cc  cmp     eax, 0C0000023h
0x14000e5d1  jz      short loc_14000E60B
0x14000e5d3  mov     ecx, cs:dword_140019000; int
0x14000e5d9  cmp     ecx, 3
0x14000e5dc  jbe     loc_14000E815
0x14000e5e2  mov     [rbp+57h+var_80], eax
0x14000e5e5  lea     rax, [rbp+57h+var_80]
0x14000e5e9  mov     [rbp+57h+var_40], r15
0x14000e5ed  mov     [rbp+57h+var_48], rax
0x14000e5f1  lea     rdx, byte_140016D91; int
0x14000e5f8  lea     rax, [rbp+57h+var_68]
0x14000e5fc  mov     [rsp+0C0h+var_98], rax; PEVENT_DATA_DESCRIPTOR
0x14000e601  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000e606  jmp     loc_14000E815
0x14000e60b  mov     ebx, dword ptr [rbp+57h+var_7B+3]
0x14000e60e  mov     ecx, 100h
0x14000e613  mov     edx, ebx
0x14000e615  mov     r8d, 44736642h
0x14000e61b  call    cs:__imp_ExAllocatePool2
0x14000e622  nop     dword ptr [rax+rax+00h]
0x14000e627  mov     r14, rax
0x14000e62a  test    rax, rax
0x14000e62d  jnz     short loc_14000E64A
0x14000e62f  mov     eax, cs:dword_140019000
0x14000e635  mov     ecx, 0C0000017h
0x14000e63a  mov     ebx, ecx
0x14000e63c  cmp     eax, 3
0x14000e63f  jbe     loc_14000E815
0x14000e645  mov     [rbp+57h+var_80], ecx
0x14000e648  jmp     short loc_14000E5E5
0x14000e64a  lea     rax, [rbp+57h+var_7B+3]
0x14000e64e  mov     r9d, ebx; Length
0x14000e651  mov     r8, r14; SecurityDescriptor
0x14000e654  mov     [rsp+0C0h+LengthNeeded], rax; int
0x14000e659  mov     edx, r15d; SecurityInformation
0x14000e65c  mov     rcx, rsi; Handle
0x14000e65f  call    cs:__imp_ZwQuerySecurityObject
0x14000e666  nop     dword ptr [rax+rax+00h]
0x14000e66b  mov     ebx, eax
0x14000e66d  test    eax, eax
0x14000e66f  jns     short loc_14000E6A9
0x14000e671  mov     eax, cs:dword_140019000
0x14000e677  cmp     eax, 3
0x14000e67a  jbe     loc_14000E804
0x14000e680  mov     [rbp+57h+var_80], ebx
0x14000e683  mov     [rbp+57h+var_40], r15
0x14000e687  lea     rax, [rbp+57h+var_80]
0x14000e68b  mov     [rbp+57h+var_48], rax
0x14000e68f  lea     rdx, byte_140016D91; int
0x14000e696  lea     rax, [rbp+57h+var_68]
0x14000e69a  mov     [rsp+0C0h+var_98], rax; PEVENT_DATA_DESCRIPTOR
0x14000e69f  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000e6a4  jmp     loc_14000E804
0x14000e6a9  lea     r9, [rbp+57h+var_7B+1]; DaclDefaulted
0x14000e6ad  mov     rcx, r14; SecurityDescriptor
0x14000e6b0  lea     r8, [rbp+57h+Dacl]; Dacl
0x14000e6b4  lea     rdx, [rbp+57h+DaclPresent]; DaclPresent
0x14000e6b8  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x14000e6bf  nop     dword ptr [rax+rax+00h]
0x14000e6c4  mov     ebx, eax
0x14000e6c6  test    eax, eax
0x14000e6c8  js      short loc_14000E671
0x14000e6ca  cmp     [rbp+57h+DaclPresent], dil
0x14000e6ce  jz      loc_14000E804
0x14000e6d4  mov     rcx, [rbp+57h+Dacl]; Acl
0x14000e6d8  lea     rax, [rbp+57h+var_7B]
0x14000e6dc  mov     [rsp+0C0h+var_98], rax; __int64
0x14000e6e1  mov     r9d, r13d
0x14000e6e4  xor     r8d, r8d
0x14000e6e7  mov     [rsp+0C0h+LengthNeeded], r12; Sid1
0x14000e6ec  xor     edx, edx
0x14000e6ee  call    BfsVerifyAce
0x14000e6f3  mov     ebx, eax
0x14000e6f5  test    eax, eax
0x14000e6f7  js      loc_14000E671
0x14000e6fd  cmp     byte ptr [rbp+57h+var_7B], dil
0x14000e701  jnz     loc_14000E804
0x14000e707  movzx   edx, byte ptr [r12+1]
0x14000e70d  mov     r8d, 41736642h
0x14000e713  mov     rax, [rbp+57h+Dacl]
0x14000e717  movzx   ecx, word ptr [rax+2]
0x14000e71b  add     ecx, 10h
0x14000e71e  lea     r15d, [rcx+rdx*4]
0x14000e722  mov     ecx, 100h
0x14000e727  mov     edx, r15d
0x14000e72a  call    cs:__imp_ExAllocatePool2
0x14000e731  nop     dword ptr [rax+rax+00h]
0x14000e736  mov     rdi, rax
0x14000e739  test    rax, rax
0x14000e73c  jnz     short loc_14000E764
0x14000e73e  mov     eax, cs:dword_140019000
0x14000e744  mov     ecx, 0C0000017h
0x14000e749  mov     ebx, ecx
0x14000e74b  cmp     eax, 3
0x14000e74e  jbe     loc_14000E804
0x14000e754  mov     [rbp+57h+var_80], ecx
0x14000e757  mov     [rbp+57h+var_40], 4
0x14000e75f  jmp     loc_14000E687
0x14000e764  mov     rdx, [rbp+57h+Dacl]; Acl
0x14000e768  mov     r9d, r15d; AclLength
0x14000e76b  mov     [rsp+0C0h+var_90], 0; char
0x14000e770  mov     r8, rdi; Dacl
0x14000e773  mov     dword ptr [rsp+0C0h+var_98], r13d; AccessMask
0x14000e778  mov     rcx, rsi; Handle
0x14000e77b  mov     [rsp+0C0h+LengthNeeded], r12; PSID
0x14000e780  call    BfsUpdateSecurityDescriptor
0x14000e785  mov     ebx, eax
0x14000e787  test    eax, eax
0x14000e789  js      short loc_14000E7C0
0x14000e78b  mov     rcx, rsi; KeyHandle
0x14000e78e  call    BfsRemoveKeyValues
0x14000e793  mov     ebx, eax
0x14000e795  test    eax, eax
0x14000e797  js      short loc_14000E7C0
0x14000e799  mov     rdx, [rbp+57h+Dacl]; Acl
0x14000e79d  mov     r9d, r15d; AclLength
0x14000e7a0  mov     [rsp+0C0h+var_90], 1; char
0x14000e7a5  mov     r8, rdi; Dacl
0x14000e7a8  mov     dword ptr [rsp+0C0h+var_98], r13d; AccessMask
0x14000e7ad  mov     rcx, rsi; Handle
0x14000e7b0  mov     [rsp+0C0h+LengthNeeded], r12; int
0x14000e7b5  call    BfsUpdateSecurityDescriptor
0x14000e7ba  mov     ebx, eax
0x14000e7bc  test    eax, eax
0x14000e7be  jns     short loc_14000E7F3
0x14000e7c0  mov     eax, cs:dword_140019000
0x14000e7c6  cmp     eax, 3
0x14000e7c9  jbe     short loc_14000E7F3
0x14000e7cb  lea     rax, [rbp+57h+var_80]
0x14000e7cf  mov     [rbp+57h+var_48], rax
0x14000e7d3  lea     rax, [rbp+57h+var_68]
0x14000e7d7  mov     [rsp+0C0h+var_98], rax; PEVENT_DATA_DESCRIPTOR
0x14000e7dc  lea     rdx, byte_140016D91; int
0x14000e7e3  mov     [rbp+57h+var_80], ebx
0x14000e7e6  mov     [rbp+57h+var_40], 4
0x14000e7ee  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000e7f3  xor     edx, edx; Tag
0x14000e7f5  mov     rcx, rdi; P
0x14000e7f8  call    cs:__imp_ExFreePoolWithTag
0x14000e7ff  nop     dword ptr [rax+rax+00h]
0x14000e804  xor     edx, edx; Tag
0x14000e806  mov     rcx, r14; P
0x14000e809  call    cs:__imp_ExFreePoolWithTag
0x14000e810  nop     dword ptr [rax+rax+00h]
0x14000e815  mov     eax, ebx
0x14000e817  mov     rcx, [rbp+57h+var_38]
0x14000e81b  xor     rcx, rsp; StackCookie
0x14000e81e  call    __security_check_cookie
0x14000e823  mov     rbx, [rsp+0C0h+arg_10]
0x14000e82b  add     rsp, 90h
0x14000e832  pop     r15
0x14000e834  pop     r14
0x14000e836  pop     r13
0x14000e838  pop     r12
0x14000e83a  pop     rdi
0x14000e83b  pop     rsi
0x14000e83c  pop     rbp
0x14000e83d  retn
```
