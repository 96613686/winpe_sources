# BfsVerifyPolicySecurity

- ea: `0x14000af40`
- end: `0x14000b2d7`
- name: `BfsVerifyPolicySecurity`
- size: `919`
- prototype: `__int64 __fastcall(HANDLE Handle)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14001f078`

## callees

- `0x140001008`
- `0x1400044e4`
- `0x14000af40`
- `0x140013730`

## import_xrefs

- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x14000b0b3`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x14000b0b3`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x14000b10c`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x14000b10c`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x14000b239`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x14000b239`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14000b16d`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14000b16d`
- `ntoskrnl!ZwQuerySecurityObject` at `0x14000afb5`
- `ntoskrnl!ZwQuerySecurityObject` at `0x14000b05a`
- `ntoskrnl!ZwQuerySecurityObject` at `0x14000afb5`
- `ntoskrnl!ZwQuerySecurityObject` at `0x14000b05a`
- `ntoskrnl!RtlEqualSid` at `0x14000b0ed`
- `ntoskrnl!RtlEqualSid` at `0x14000b14a`
- `ntoskrnl!RtlEqualSid` at `0x14000b0ed`
- `ntoskrnl!RtlEqualSid` at `0x14000b14a`
- `ntoskrnl!SeExports` at `0x14000b0dc`
- `ntoskrnl!SeExports` at `0x14000b139`
- `ntoskrnl!SeExports` at `0x14000b1a5`
- `ntoskrnl!SeExports` at `0x14000b1ea`
- `ntoskrnl!SeExports` at `0x14000b25e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b2a5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b2a5`
- `ntoskrnl!ExAllocatePool2` at `0x14000b016`
- `ntoskrnl!ExAllocatePool2` at `0x14000b016`

## pseudocode

```c
__int64 __fastcall BfsVerifyPolicySecurity(HANDLE Handle, _BYTE *a2)
{
  NTSTATUS v4; // eax
  int v5; // r8d
  int v6; // r9d
  NTSTATUS OwnerSecurityDescriptor; // ebx
  int v8; // ecx
  ULONG v9; // ebx
  void *Pool2; // rdi
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  int LengthNeeded; // [rsp+20h] [rbp-49h]
  int LengthNeededa; // [rsp+20h] [rbp-49h]
  _BYTE v17[4]; // [rsp+30h] [rbp-39h] BYREF
  int v18; // [rsp+34h] [rbp-35h] BYREF
  unsigned __int8 OwnerDefaulted; // [rsp+38h] [rbp-31h] BYREF
  unsigned __int8 GroupDefaulted; // [rsp+39h] [rbp-30h] BYREF
  unsigned __int8 DaclPresent; // [rsp+3Ah] [rbp-2Fh] BYREF
  unsigned __int8 SaclPresent; // [rsp+3Bh] [rbp-2Eh] BYREF
  unsigned __int8 DaclDefaulted; // [rsp+3Ch] [rbp-2Dh] BYREF
  unsigned __int8 SaclDefaulted[3]; // [rsp+3Dh] [rbp-2Ch] BYREF
  ULONG Length; // [rsp+40h] [rbp-29h] BYREF
  PACL Dacl; // [rsp+48h] [rbp-21h] BYREF
  PSID Owner; // [rsp+50h] [rbp-19h] BYREF
  PSID Group; // [rsp+58h] [rbp-11h] BYREF
  PACL Sacl; // [rsp+60h] [rbp-9h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v30; // [rsp+68h] [rbp-1h] BYREF
  int *v31; // [rsp+88h] [rbp+1Fh]
  __int64 v32; // [rsp+90h] [rbp+27h]

  *a2 = 1;
  v17[0] = 0;
  Dacl = 0;
  DaclDefaulted = 0;
  DaclPresent = 0;
  Group = 0;
  GroupDefaulted = 0;
  Length = 0;
  Owner = 0;
  OwnerDefaulted = 0;
  Sacl = 0;
  SaclDefaulted[0] = 0;
  SaclPresent = 0;
  v4 = ZwQuerySecurityObject(Handle, 0x1Fu, 0, 0, &Length);
  OwnerSecurityDescriptor = v4;
  if ( v4 == -1073741789 )
  {
    v9 = Length;
    Pool2 = (void *)ExAllocatePool2(256, Length, 1148413506);
    if ( !Pool2 )
    {
      OwnerSecurityDescriptor = -1073741801;
      if ( (unsigned int)dword_140019000 <= 3 )
        return (unsigned int)OwnerSecurityDescriptor;
      v18 = -1073741801;
      goto LABEL_4;
    }
    OwnerSecurityDescriptor = ZwQuerySecurityObject(Handle, 0x1Fu, Pool2, v9, &Length);
    if ( OwnerSecurityDescriptor < 0 )
      goto LABEL_9;
    OwnerSecurityDescriptor = RtlGetOwnerSecurityDescriptor(Pool2, &Owner, &OwnerDefaulted);
    if ( OwnerSecurityDescriptor < 0 )
      goto LABEL_9;
    if ( Owner && OwnerDefaulted != 1 && RtlEqualSid(Owner, SeExports->SeLocalSystemSid) )
    {
      OwnerSecurityDescriptor = RtlGetGroupSecurityDescriptor(Pool2, &Group, &GroupDefaulted);
      if ( OwnerSecurityDescriptor < 0 )
        goto LABEL_9;
      if ( Group && GroupDefaulted != 1 && RtlEqualSid(Group, SeExports->SeLocalSystemSid) )
      {
        OwnerSecurityDescriptor = RtlGetDaclSecurityDescriptor(Pool2, &DaclPresent, &Dacl, &DaclDefaulted);
        if ( OwnerSecurityDescriptor < 0 )
          goto LABEL_9;
        if ( DaclPresent && Dacl && Dacl->AceCount == 2 )
        {
          OwnerSecurityDescriptor = BfsVerifyAce(Dacl, SeExports->SeTrustedInstallerSid, (__int64)v17);
          if ( OwnerSecurityDescriptor < 0 )
            goto LABEL_9;
          if ( v17[0] )
          {
            OwnerSecurityDescriptor = BfsVerifyAce(Dacl, SeExports->SeLocalSystemSid, (__int64)v17);
            if ( OwnerSecurityDescriptor < 0 )
              goto LABEL_9;
            if ( v17[0] )
            {
              OwnerSecurityDescriptor = RtlGetSaclSecurityDescriptor(Pool2, &SaclPresent, &Sacl, SaclDefaulted);
              if ( OwnerSecurityDescriptor < 0 )
                goto LABEL_9;
              if ( SaclPresent && Sacl )
              {
                OwnerSecurityDescriptor = BfsVerifyAce(Sacl, SeExports->SeHighMandatorySid, (__int64)v17);
                if ( OwnerSecurityDescriptor >= 0 )
                {
                  if ( v17[0] )
                    *a2 = 0;
                  goto LABEL_33;
                }
LABEL_9:
                if ( (unsigned int)dword_140019000 > 3 )
                {
                  v18 = OwnerSecurityDescriptor;
                  v31 = &v18;
                  v32 = 4;
                  tlgWriteTransfer_EtwWriteTransfer(v11, (int)&byte_140016D91, v12, v13, LengthNeededa, &v30);
                }
              }
            }
          }
        }
      }
    }
LABEL_33:
    ExFreePoolWithTag(Pool2, 0);
    return (unsigned int)OwnerSecurityDescriptor;
  }
  v8 = dword_140019000;
  if ( (unsigned int)dword_140019000 > 3 )
  {
    v18 = v4;
LABEL_4:
    v32 = 4;
    v31 = &v18;
    tlgWriteTransfer_EtwWriteTransfer(v8, (int)&byte_140016D91, v5, v6, LengthNeeded, &v30);
  }
  return (unsigned int)OwnerSecurityDescriptor;
}

```

## disassembly

```asm
0x14000af40  mov     [rsp-8+arg_10], rbx
0x14000af45  push    rbp
0x14000af46  push    rsi
0x14000af47  push    rdi
0x14000af48  push    r14
0x14000af4a  push    r15
0x14000af4c  lea     rbp, [rsp-37h]
0x14000af51  sub     rsp, 0A0h
0x14000af58  mov     rax, cs:__security_cookie
0x14000af5f  xor     rax, rsp
0x14000af62  mov     [rbp+57h+var_28], rax
0x14000af66  xor     r15d, r15d
0x14000af69  mov     byte ptr [rdx], 1
0x14000af6c  mov     r14, rdx
0x14000af6f  mov     byte ptr [rbp+57h+var_90], r15b
0x14000af73  lea     rax, [rbp+57h+Length]
0x14000af77  mov     [rbp+57h+Dacl], r15
0x14000af7b  xor     r9d, r9d; Length
0x14000af7e  mov     [rbp+57h+DaclDefaulted], r15b
0x14000af82  lea     edx, [r15+1Fh]; SecurityInformation
0x14000af86  mov     [rbp+57h+DaclPresent], r15b
0x14000af8a  xor     r8d, r8d; SecurityDescriptor
0x14000af8d  mov     [rbp+57h+Group], r15
0x14000af91  mov     rsi, rcx
0x14000af94  mov     [rbp+57h+GroupDefaulted], r15b
0x14000af98  mov     [rbp+57h+Length], r15d
0x14000af9c  mov     [rbp+57h+Owner], r15
0x14000afa0  mov     [rbp+57h+OwnerDefaulted], r15b
0x14000afa4  mov     [rbp+57h+Sacl], r15
0x14000afa8  mov     [rbp+57h+SaclDefaulted], r15b
0x14000afac  mov     [rbp+57h+SaclPresent], r15b
0x14000afb0  mov     [rsp+0C0h+LengthNeeded], rax; int
0x14000afb5  call    cs:__imp_ZwQuerySecurityObject
0x14000afbc  nop     dword ptr [rax+rax+00h]
0x14000afc1  mov     ebx, eax
0x14000afc3  cmp     eax, 0C0000023h
0x14000afc8  jz      short loc_14000B006
0x14000afca  mov     ecx, cs:dword_140019000; int
0x14000afd0  cmp     ecx, 3
0x14000afd3  jbe     loc_14000B2B1
0x14000afd9  mov     dword ptr [rbp+57h+var_90+4], eax
0x14000afdc  lea     rax, [rbp+57h+var_90+4]
0x14000afe0  mov     [rbp+57h+var_30], 4
0x14000afe8  mov     [rbp+57h+var_38], rax
0x14000afec  lea     rdx, byte_140016D91; int
0x14000aff3  lea     rax, [rbp+57h+var_58]
0x14000aff7  mov     [rsp+0C0h+var_98], rax; PEVENT_DATA_DESCRIPTOR
0x14000affc  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000b001  jmp     loc_14000B2B1
0x14000b006  mov     ebx, [rbp+57h+Length]
0x14000b009  mov     ecx, 100h
0x14000b00e  mov     edx, ebx
0x14000b010  mov     r8d, 44736642h
0x14000b016  call    cs:__imp_ExAllocatePool2
0x14000b01d  nop     dword ptr [rax+rax+00h]
0x14000b022  mov     rdi, rax
0x14000b025  test    rax, rax
0x14000b028  jnz     short loc_14000B043
0x14000b02a  mov     eax, cs:dword_140019000
0x14000b030  mov     ebx, 0C0000017h
0x14000b035  cmp     eax, 3
0x14000b038  jbe     loc_14000B2B1
0x14000b03e  mov     dword ptr [rbp+57h+var_90+4], ebx
0x14000b041  jmp     short loc_14000AFDC
0x14000b043  lea     rax, [rbp+57h+Length]
0x14000b047  mov     r9d, ebx; Length
0x14000b04a  mov     r8, rdi; SecurityDescriptor
0x14000b04d  mov     [rsp+0C0h+LengthNeeded], rax; int
0x14000b052  mov     edx, 1Fh; SecurityInformation
0x14000b057  mov     rcx, rsi; Handle
0x14000b05a  call    cs:__imp_ZwQuerySecurityObject
0x14000b061  nop     dword ptr [rax+rax+00h]
0x14000b066  mov     ebx, eax
0x14000b068  test    eax, eax
0x14000b06a  jns     short loc_14000B0A8
0x14000b06c  mov     eax, cs:dword_140019000
0x14000b072  cmp     eax, 3
0x14000b075  jbe     loc_14000B2A0
0x14000b07b  lea     rax, [rbp+57h+var_90+4]
0x14000b07f  mov     dword ptr [rbp+57h+var_90+4], ebx
0x14000b082  mov     [rbp+57h+var_38], rax
0x14000b086  lea     rdx, byte_140016D91; int
0x14000b08d  lea     rax, [rbp+57h+var_58]
0x14000b091  mov     [rbp+57h+var_30], 4
0x14000b099  mov     [rsp+0C0h+var_98], rax; PEVENT_DATA_DESCRIPTOR
0x14000b09e  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000b0a3  jmp     loc_14000B2A0
0x14000b0a8  lea     r8, [rbp+57h+OwnerDefaulted]; OwnerDefaulted
0x14000b0ac  mov     rcx, rdi; SecurityDescriptor
0x14000b0af  lea     rdx, [rbp+57h+Owner]; Owner
0x14000b0b3  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x14000b0ba  nop     dword ptr [rax+rax+00h]
0x14000b0bf  mov     ebx, eax
0x14000b0c1  test    eax, eax
0x14000b0c3  js      short loc_14000B06C
0x14000b0c5  mov     rcx, [rbp+57h+Owner]; Sid1
0x14000b0c9  test    rcx, rcx
0x14000b0cc  jz      loc_14000B2A0
0x14000b0d2  cmp     [rbp+57h+OwnerDefaulted], 1
0x14000b0d6  jz      loc_14000B2A0
0x14000b0dc  mov     rax, cs:__imp_SeExports
0x14000b0e3  mov     rdx, [rax]
0x14000b0e6  mov     rdx, [rdx+108h]; Sid2
0x14000b0ed  call    cs:__imp_RtlEqualSid
0x14000b0f4  nop     dword ptr [rax+rax+00h]
0x14000b0f9  test    al, al
0x14000b0fb  jz      loc_14000B2A0
0x14000b101  lea     r8, [rbp+57h+GroupDefaulted]; GroupDefaulted
0x14000b105  mov     rcx, rdi; SecurityDescriptor
0x14000b108  lea     rdx, [rbp+57h+Group]; Group
0x14000b10c  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x14000b113  nop     dword ptr [rax+rax+00h]
0x14000b118  mov     ebx, eax
0x14000b11a  test    eax, eax
0x14000b11c  js      loc_14000B06C
0x14000b122  mov     rcx, [rbp+57h+Group]; Sid1
0x14000b126  test    rcx, rcx
0x14000b129  jz      loc_14000B2A0
0x14000b12f  cmp     [rbp+57h+GroupDefaulted], 1
0x14000b133  jz      loc_14000B2A0
0x14000b139  mov     rax, cs:__imp_SeExports
0x14000b140  mov     rdx, [rax]
0x14000b143  mov     rdx, [rdx+108h]; Sid2
0x14000b14a  call    cs:__imp_RtlEqualSid
0x14000b151  nop     dword ptr [rax+rax+00h]
0x14000b156  test    al, al
0x14000b158  jz      loc_14000B2A0
0x14000b15e  lea     r9, [rbp+57h+DaclDefaulted]; DaclDefaulted
0x14000b162  mov     rcx, rdi; SecurityDescriptor
0x14000b165  lea     r8, [rbp+57h+Dacl]; Dacl
0x14000b169  lea     rdx, [rbp+57h+DaclPresent]; DaclPresent
0x14000b16d  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x14000b174  nop     dword ptr [rax+rax+00h]
0x14000b179  mov     ebx, eax
0x14000b17b  test    eax, eax
0x14000b17d  js      loc_14000B06C
0x14000b183  cmp     [rbp+57h+DaclPresent], r15b
0x14000b187  jz      loc_14000B2A0
0x14000b18d  mov     rcx, [rbp+57h+Dacl]; Acl
0x14000b191  test    rcx, rcx
0x14000b194  jz      loc_14000B2A0
0x14000b19a  cmp     word ptr [rcx+4], 2
0x14000b19f  jnz     loc_14000B2A0
0x14000b1a5  mov     rax, cs:__imp_SeExports
0x14000b1ac  lea     rdx, [rbp+57h+var_90]
0x14000b1b0  mov     [rsp+0C0h+var_98], rdx; __int64
0x14000b1b5  mov     esi, 1F01FFh
0x14000b1ba  mov     r9d, esi
0x14000b1bd  mov     r8b, 3
0x14000b1c0  xor     edx, edx
0x14000b1c2  mov     rax, [rax]
0x14000b1c5  mov     rax, [rax+220h]
0x14000b1cc  mov     [rsp+0C0h+LengthNeeded], rax; Sid1
0x14000b1d1  call    BfsVerifyAce
0x14000b1d6  mov     ebx, eax
0x14000b1d8  test    eax, eax
0x14000b1da  js      loc_14000B06C
0x14000b1e0  cmp     byte ptr [rbp+57h+var_90], r15b
0x14000b1e4  jz      loc_14000B2A0
0x14000b1ea  mov     rax, cs:__imp_SeExports
0x14000b1f1  lea     rcx, [rbp+57h+var_90]
0x14000b1f5  mov     [rsp+0C0h+var_98], rcx; __int64
0x14000b1fa  mov     r9d, esi
0x14000b1fd  mov     rcx, [rbp+57h+Dacl]; Acl
0x14000b201  mov     r8b, 3
0x14000b204  xor     edx, edx
0x14000b206  mov     rax, [rax]
0x14000b209  mov     rax, [rax+108h]
0x14000b210  mov     [rsp+0C0h+LengthNeeded], rax; Sid1
0x14000b215  call    BfsVerifyAce
0x14000b21a  mov     ebx, eax
0x14000b21c  test    eax, eax
0x14000b21e  js      loc_14000B06C
0x14000b224  cmp     byte ptr [rbp+57h+var_90], r15b
0x14000b228  jz      short loc_14000B2A0
0x14000b22a  lea     r9, [rbp+57h+SaclDefaulted]; SaclDefaulted
0x14000b22e  mov     rcx, rdi; SecurityDescriptor
0x14000b231  lea     r8, [rbp+57h+Sacl]; Sacl
0x14000b235  lea     rdx, [rbp+57h+SaclPresent]; SaclPresent
0x14000b239  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x14000b240  nop     dword ptr [rax+rax+00h]
0x14000b245  mov     ebx, eax
0x14000b247  test    eax, eax
0x14000b249  js      loc_14000B06C
0x14000b24f  cmp     [rbp+57h+SaclPresent], r15b
0x14000b253  jz      short loc_14000B2A0
0x14000b255  mov     rcx, [rbp+57h+Sacl]; Acl
0x14000b259  test    rcx, rcx
0x14000b25c  jz      short loc_14000B2A0
0x14000b25e  mov     rax, cs:__imp_SeExports
0x14000b265  lea     rdx, [rbp+57h+var_90]
0x14000b269  mov     [rsp+0C0h+var_98], rdx; __int64
0x14000b26e  mov     r9d, 7
0x14000b274  mov     r8b, 3
0x14000b277  mov     dl, 11h
0x14000b279  mov     rax, [rax]
0x14000b27c  mov     rax, [rax+1F0h]
0x14000b283  mov     [rsp+0C0h+LengthNeeded], rax; Sid1
0x14000b288  call    BfsVerifyAce
0x14000b28d  mov     ebx, eax
0x14000b28f  test    eax, eax
0x14000b291  js      loc_14000B06C
0x14000b297  cmp     byte ptr [rbp+57h+var_90], r15b
0x14000b29b  jz      short loc_14000B2A0
0x14000b29d  mov     [r14], r15b
0x14000b2a0  xor     edx, edx; Tag
0x14000b2a2  mov     rcx, rdi; P
0x14000b2a5  call    cs:__imp_ExFreePoolWithTag
0x14000b2ac  nop     dword ptr [rax+rax+00h]
0x14000b2b1  mov     eax, ebx
0x14000b2b3  mov     rcx, [rbp+57h+var_28]
0x14000b2b7  xor     rcx, rsp; StackCookie
0x14000b2ba  call    __security_check_cookie
0x14000b2bf  mov     rbx, [rsp+0C0h+arg_10]
0x14000b2c7  add     rsp, 0A0h
0x14000b2ce  pop     r15
0x14000b2d0  pop     r14
0x14000b2d2  pop     rdi
0x14000b2d3  pop     rsi
0x14000b2d4  pop     rbp
0x14000b2d5  retn
```
