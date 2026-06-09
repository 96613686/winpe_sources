# BfsAdjustRegistryKeySecurity

- ea: `0x14000e6f0`
- end: `0x14000e9cf`
- name: `BfsAdjustRegistryKeySecurity`
- size: `735`
- prototype: `__int64 __fastcall(HANDLE Handle, unsigned __int8 *, ACCESS_MASK AccessMask)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14000f100`

## callees

- `0x140001008`
- `0x140004614`
- `0x14000e6f0`
- `0x14000f770`
- `0x1400130e8`
- `0x140013860`

## import_xrefs

- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14000e848`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14000e848`
- `ntoskrnl!ZwQuerySecurityObject` at `0x14000e74e`
- `ntoskrnl!ZwQuerySecurityObject` at `0x14000e7ef`
- `ntoskrnl!ZwQuerySecurityObject` at `0x14000e74e`
- `ntoskrnl!ZwQuerySecurityObject` at `0x14000e7ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e988`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e999`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e988`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e999`
- `ntoskrnl!ExAllocatePool2` at `0x14000e7ab`
- `ntoskrnl!ExAllocatePool2` at `0x14000e8ba`
- `ntoskrnl!ExAllocatePool2` at `0x14000e7ab`
- `ntoskrnl!ExAllocatePool2` at `0x14000e8ba`

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
0x14000e6f0  mov     [rsp-8+arg_10], rbx
0x14000e6f5  push    rbp
0x14000e6f6  push    rsi
0x14000e6f7  push    rdi
0x14000e6f8  push    r12
0x14000e6fa  push    r13
0x14000e6fc  push    r14
0x14000e6fe  push    r15
0x14000e700  lea     rbp, [rsp-27h]
0x14000e705  sub     rsp, 90h
0x14000e70c  mov     rax, cs:__security_cookie
0x14000e713  xor     rax, rsp
0x14000e716  mov     [rbp+57h+var_38], rax
0x14000e71a  xor     edi, edi
0x14000e71c  lea     rax, [rbp+57h+var_7B+3]
0x14000e720  mov     r13d, r8d
0x14000e723  mov     [rbp+57h+Dacl], rdi
0x14000e727  mov     r12, rdx
0x14000e72a  mov     byte ptr [rbp+57h+var_7B+1], dil
0x14000e72e  xor     r9d, r9d; Length
0x14000e731  mov     [rbp+57h+DaclPresent], dil
0x14000e735  lea     r15d, [rdi+4]
0x14000e739  mov     dword ptr [rbp+57h+var_7B+3], edi
0x14000e73c  mov     edx, r15d; SecurityInformation
0x14000e73f  mov     byte ptr [rbp+57h+var_7B], dil
0x14000e743  xor     r8d, r8d; SecurityDescriptor
0x14000e746  mov     [rsp+0C0h+LengthNeeded], rax; int
0x14000e74b  mov     rsi, rcx
0x14000e74e  call    cs:__imp_ZwQuerySecurityObject
0x14000e755  nop     dword ptr [rax+rax+00h]
0x14000e75a  mov     ebx, eax
0x14000e75c  cmp     eax, 0C0000023h
0x14000e761  jz      short loc_14000E79B
0x14000e763  mov     ecx, cs:dword_140019000; int
0x14000e769  cmp     ecx, 3
0x14000e76c  jbe     loc_14000E9A5
0x14000e772  mov     [rbp+57h+var_80], eax
0x14000e775  lea     rax, [rbp+57h+var_80]
0x14000e779  mov     [rbp+57h+var_40], r15
0x14000e77d  mov     [rbp+57h+var_48], rax
0x14000e781  lea     rdx, byte_140016D91; int
0x14000e788  lea     rax, [rbp+57h+var_68]
0x14000e78c  mov     [rsp+0C0h+var_98], rax; PEVENT_DATA_DESCRIPTOR
0x14000e791  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000e796  jmp     loc_14000E9A5
0x14000e79b  mov     ebx, dword ptr [rbp+57h+var_7B+3]
0x14000e79e  mov     ecx, 100h
0x14000e7a3  mov     edx, ebx
0x14000e7a5  mov     r8d, 44736642h
0x14000e7ab  call    cs:__imp_ExAllocatePool2
0x14000e7b2  nop     dword ptr [rax+rax+00h]
0x14000e7b7  mov     r14, rax
0x14000e7ba  test    rax, rax
0x14000e7bd  jnz     short loc_14000E7DA
0x14000e7bf  mov     eax, cs:dword_140019000
0x14000e7c5  mov     ecx, 0C0000017h
0x14000e7ca  mov     ebx, ecx
0x14000e7cc  cmp     eax, 3
0x14000e7cf  jbe     loc_14000E9A5
0x14000e7d5  mov     [rbp+57h+var_80], ecx
0x14000e7d8  jmp     short loc_14000E775
0x14000e7da  lea     rax, [rbp+57h+var_7B+3]
0x14000e7de  mov     r9d, ebx; Length
0x14000e7e1  mov     r8, r14; SecurityDescriptor
0x14000e7e4  mov     [rsp+0C0h+LengthNeeded], rax; int
0x14000e7e9  mov     edx, r15d; SecurityInformation
0x14000e7ec  mov     rcx, rsi; Handle
0x14000e7ef  call    cs:__imp_ZwQuerySecurityObject
0x14000e7f6  nop     dword ptr [rax+rax+00h]
0x14000e7fb  mov     ebx, eax
0x14000e7fd  test    eax, eax
0x14000e7ff  jns     short loc_14000E839
0x14000e801  mov     eax, cs:dword_140019000
0x14000e807  cmp     eax, 3
0x14000e80a  jbe     loc_14000E994
0x14000e810  mov     [rbp+57h+var_80], ebx
0x14000e813  mov     [rbp+57h+var_40], r15
0x14000e817  lea     rax, [rbp+57h+var_80]
0x14000e81b  mov     [rbp+57h+var_48], rax
0x14000e81f  lea     rdx, byte_140016D91; int
0x14000e826  lea     rax, [rbp+57h+var_68]
0x14000e82a  mov     [rsp+0C0h+var_98], rax; PEVENT_DATA_DESCRIPTOR
0x14000e82f  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000e834  jmp     loc_14000E994
0x14000e839  lea     r9, [rbp+57h+var_7B+1]; DaclDefaulted
0x14000e83d  mov     rcx, r14; SecurityDescriptor
0x14000e840  lea     r8, [rbp+57h+Dacl]; Dacl
0x14000e844  lea     rdx, [rbp+57h+DaclPresent]; DaclPresent
0x14000e848  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x14000e84f  nop     dword ptr [rax+rax+00h]
0x14000e854  mov     ebx, eax
0x14000e856  test    eax, eax
0x14000e858  js      short loc_14000E801
0x14000e85a  cmp     [rbp+57h+DaclPresent], dil
0x14000e85e  jz      loc_14000E994
0x14000e864  mov     rcx, [rbp+57h+Dacl]; Acl
0x14000e868  lea     rax, [rbp+57h+var_7B]
0x14000e86c  mov     [rsp+0C0h+var_98], rax; __int64
0x14000e871  mov     r9d, r13d
0x14000e874  xor     r8d, r8d
0x14000e877  mov     [rsp+0C0h+LengthNeeded], r12; Sid1
0x14000e87c  xor     edx, edx
0x14000e87e  call    BfsVerifyAce
0x14000e883  mov     ebx, eax
0x14000e885  test    eax, eax
0x14000e887  js      loc_14000E801
0x14000e88d  cmp     byte ptr [rbp+57h+var_7B], dil
0x14000e891  jnz     loc_14000E994
0x14000e897  movzx   edx, byte ptr [r12+1]
0x14000e89d  mov     r8d, 41736642h
0x14000e8a3  mov     rax, [rbp+57h+Dacl]
0x14000e8a7  movzx   ecx, word ptr [rax+2]
0x14000e8ab  add     ecx, 10h
0x14000e8ae  lea     r15d, [rcx+rdx*4]
0x14000e8b2  mov     ecx, 100h
0x14000e8b7  mov     edx, r15d
0x14000e8ba  call    cs:__imp_ExAllocatePool2
0x14000e8c1  nop     dword ptr [rax+rax+00h]
0x14000e8c6  mov     rdi, rax
0x14000e8c9  test    rax, rax
0x14000e8cc  jnz     short loc_14000E8F4
0x14000e8ce  mov     eax, cs:dword_140019000
0x14000e8d4  mov     ecx, 0C0000017h
0x14000e8d9  mov     ebx, ecx
0x14000e8db  cmp     eax, 3
0x14000e8de  jbe     loc_14000E994
0x14000e8e4  mov     [rbp+57h+var_80], ecx
0x14000e8e7  mov     [rbp+57h+var_40], 4
0x14000e8ef  jmp     loc_14000E817
0x14000e8f4  mov     rdx, [rbp+57h+Dacl]; Acl
0x14000e8f8  mov     r9d, r15d; AclLength
0x14000e8fb  mov     [rsp+0C0h+var_90], 0; char
0x14000e900  mov     r8, rdi; Dacl
0x14000e903  mov     dword ptr [rsp+0C0h+var_98], r13d; AccessMask
0x14000e908  mov     rcx, rsi; Handle
0x14000e90b  mov     [rsp+0C0h+LengthNeeded], r12; PSID
0x14000e910  call    BfsUpdateSecurityDescriptor
0x14000e915  mov     ebx, eax
0x14000e917  test    eax, eax
0x14000e919  js      short loc_14000E950
0x14000e91b  mov     rcx, rsi; KeyHandle
0x14000e91e  call    BfsRemoveKeyValues
0x14000e923  mov     ebx, eax
0x14000e925  test    eax, eax
0x14000e927  js      short loc_14000E950
0x14000e929  mov     rdx, [rbp+57h+Dacl]; Acl
0x14000e92d  mov     r9d, r15d; AclLength
0x14000e930  mov     [rsp+0C0h+var_90], 1; char
0x14000e935  mov     r8, rdi; Dacl
0x14000e938  mov     dword ptr [rsp+0C0h+var_98], r13d; AccessMask
0x14000e93d  mov     rcx, rsi; Handle
0x14000e940  mov     [rsp+0C0h+LengthNeeded], r12; int
0x14000e945  call    BfsUpdateSecurityDescriptor
0x14000e94a  mov     ebx, eax
0x14000e94c  test    eax, eax
0x14000e94e  jns     short loc_14000E983
0x14000e950  mov     eax, cs:dword_140019000
0x14000e956  cmp     eax, 3
0x14000e959  jbe     short loc_14000E983
0x14000e95b  lea     rax, [rbp+57h+var_80]
0x14000e95f  mov     [rbp+57h+var_48], rax
0x14000e963  lea     rax, [rbp+57h+var_68]
0x14000e967  mov     [rsp+0C0h+var_98], rax; PEVENT_DATA_DESCRIPTOR
0x14000e96c  lea     rdx, byte_140016D91; int
0x14000e973  mov     [rbp+57h+var_80], ebx
0x14000e976  mov     [rbp+57h+var_40], 4
0x14000e97e  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000e983  xor     edx, edx; Tag
0x14000e985  mov     rcx, rdi; P
0x14000e988  call    cs:__imp_ExFreePoolWithTag
0x14000e98f  nop     dword ptr [rax+rax+00h]
0x14000e994  xor     edx, edx; Tag
0x14000e996  mov     rcx, r14; P
0x14000e999  call    cs:__imp_ExFreePoolWithTag
0x14000e9a0  nop     dword ptr [rax+rax+00h]
0x14000e9a5  mov     eax, ebx
0x14000e9a7  mov     rcx, [rbp+57h+var_38]
0x14000e9ab  xor     rcx, rsp; StackCookie
0x14000e9ae  call    __security_check_cookie
0x14000e9b3  mov     rbx, [rsp+0C0h+arg_10]
0x14000e9bb  add     rsp, 90h
0x14000e9c2  pop     r15
0x14000e9c4  pop     r14
0x14000e9c6  pop     r13
0x14000e9c8  pop     r12
0x14000e9ca  pop     rdi
0x14000e9cb  pop     rsi
0x14000e9cc  pop     rbp
0x14000e9cd  retn
```
