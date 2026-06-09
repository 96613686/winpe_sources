# BfsVerifyVolumeRootDescriptor

- ea: `0x14001e1a0`
- end: `0x14001e648`
- name: `BfsVerifyVolumeRootDescriptor`
- size: `1192`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14001f078`

## callees

- `0x140001008`
- `0x140004614`
- `0x140013860`
- `0x14001e1a0`

## import_xrefs

- `ntoskrnl!ZwSetSecurityObject` at `0x14001e5ae`
- `ntoskrnl!ZwSetSecurityObject` at `0x14001e5ae`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14001e591`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14001e591`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14001e573`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14001e573`
- `ntoskrnl!RtlAddAce` at `0x14001e558`
- `ntoskrnl!RtlAddAce` at `0x14001e558`
- `ntoskrnl!RtlGetAcesBufferSize` at `0x14001e529`
- `ntoskrnl!RtlGetAcesBufferSize` at `0x14001e529`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x14001e4e7`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x14001e4e7`
- `ntoskrnl!RtlCreateAcl` at `0x14001e4ac`
- `ntoskrnl!RtlCreateAcl` at `0x14001e4ac`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14001e3ca`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14001e3ca`
- `ntoskrnl!ZwQuerySecurityObject` at `0x14001e2e4`
- `ntoskrnl!ZwQuerySecurityObject` at `0x14001e36c`
- `ntoskrnl!ZwQuerySecurityObject` at `0x14001e2e4`
- `ntoskrnl!ZwQuerySecurityObject` at `0x14001e36c`
- `ntoskrnl!ZwOpenFile` at `0x14001e279`
- `ntoskrnl!ZwOpenFile` at `0x14001e279`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001e224`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001e224`
- `ntoskrnl!RtlGetAce` at `0x14001e509`
- `ntoskrnl!RtlGetAce` at `0x14001e509`
- `ntoskrnl!ZwClose` at `0x14001e61d`
- `ntoskrnl!ZwClose` at `0x14001e61d`
- `ntoskrnl!SeExports` at `0x14001e3f5`
- `ntoskrnl!SeExports` at `0x14001e43a`
- `ntoskrnl!SeExports` at `0x14001e4c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e5f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e607`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e5f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e607`
- `ntoskrnl!ExAllocatePool2` at `0x14001e325`
- `ntoskrnl!ExAllocatePool2` at `0x14001e46b`
- `ntoskrnl!ExAllocatePool2` at `0x14001e325`
- `ntoskrnl!ExAllocatePool2` at `0x14001e46b`

## pseudocode

```c
__int64 BfsVerifyVolumeRootDescriptor()
{
  NTSTATUS v0; // eax
  int v1; // r8d
  int v2; // r9d
  int DaclSecurityDescriptor; // ebx
  int v4; // ecx
  ULONG v5; // ebx
  void *Pool2; // r14
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  ULONG v10; // ebx
  struct _ACL *v11; // rsi
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  int ShareAccess; // [rsp+20h] [rbp-E0h]
  int ShareAccessa; // [rsp+20h] [rbp-E0h]
  int v18; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int8 DaclPresent; // [rsp+34h] [rbp-CCh] BYREF
  __int16 v20; // [rsp+35h] [rbp-CBh] BYREF
  ULONG v21; // [rsp+38h] [rbp-C8h] BYREF
  PACL Dacl; // [rsp+40h] [rbp-C0h] BYREF
  ULONG AceListLength; // [rsp+48h] [rbp-B8h] BYREF
  void *FileHandle; // [rsp+50h] [rbp-B0h] BYREF
  PVOID Ace; // [rsp+58h] [rbp-A8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-70h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v29; // [rsp+C0h] [rbp-40h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C8h] [rbp-38h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v31; // [rsp+D8h] [rbp-28h] BYREF
  int *v32; // [rsp+F8h] [rbp-8h]
  __int64 v33; // [rsp+100h] [rbp+0h]

  AceListLength = 0;
  v20 = 0;
  Dacl = 0;
  DaclPresent = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  Ace = 0;
  v21 = 0;
  IoStatusBlock = 0;
  v29 = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  FileHandle = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\BootDevice\\");
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 512;
  v0 = ZwOpenFile(&FileHandle, 0x60000u, &ObjectAttributes, &IoStatusBlock, 7u, 0x21u);
  DaclSecurityDescriptor = v0;
  if ( v0 < 0 )
  {
    v4 = dword_140019000;
    if ( (unsigned int)dword_140019000 <= 3 )
      goto LABEL_36;
    v18 = v0;
    v33 = 4;
    goto LABEL_4;
  }
  DaclSecurityDescriptor = ZwQuerySecurityObject(FileHandle, 4u, 0, 0, &v21);
  if ( DaclSecurityDescriptor != -1073741789 )
  {
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v18 = DaclSecurityDescriptor;
LABEL_8:
      v33 = 4;
LABEL_4:
      v32 = &v18;
      tlgWriteTransfer_EtwWriteTransfer(v4, (int)&byte_140016D91, v1, v2, ShareAccess, &v31);
      goto LABEL_36;
    }
    goto LABEL_36;
  }
  v5 = v21;
  Pool2 = (void *)ExAllocatePool2(256, v21, 1148413506);
  if ( Pool2 )
  {
    DaclSecurityDescriptor = ZwQuerySecurityObject(FileHandle, 4u, Pool2, v5, &v21);
    if ( DaclSecurityDescriptor < 0 )
      goto LABEL_13;
    DaclSecurityDescriptor = RtlGetDaclSecurityDescriptor(Pool2, &DaclPresent, &Dacl, (PBOOLEAN)&v20 + 1);
    if ( DaclSecurityDescriptor < 0 )
      goto LABEL_13;
    if ( !DaclPresent || !Dacl )
      goto LABEL_35;
    DaclSecurityDescriptor = BfsVerifyAce(
                               Dacl,
                               0,
                               0,
                               1048737,
                               *(PSID *)&SeExports[1].SeAssignPrimaryTokenPrivilege,
                               &v20);
    if ( DaclSecurityDescriptor < 0 )
    {
LABEL_13:
      if ( (unsigned int)dword_140019000 > 3 )
      {
        v18 = DaclSecurityDescriptor;
LABEL_15:
        v33 = 4;
        v32 = &v18;
        tlgWriteTransfer_EtwWriteTransfer(v7, (int)&byte_140016D91, v8, v9, ShareAccessa, &v31);
      }
    }
    else if ( !(_BYTE)v20 )
    {
      v10 = Dacl->AclSize + 16 + 4 * *(unsigned __int8 *)(*(_QWORD *)&SeExports[1].SeAssignPrimaryTokenPrivilege + 1LL);
      v11 = (struct _ACL *)ExAllocatePool2(256, v10, 1098081858);
      if ( v11 )
      {
        DaclSecurityDescriptor = RtlCreateAcl(v11, v10, Dacl->AclRevision);
        if ( DaclSecurityDescriptor < 0
          || (DaclSecurityDescriptor = RtlAddAccessAllowedAceEx(
                                         v11,
                                         v11->AclRevision,
                                         0,
                                         0x1000A1u,
                                         *(PSID *)&SeExports[1].SeAssignPrimaryTokenPrivilege),
              DaclSecurityDescriptor < 0)
          || (DaclSecurityDescriptor = RtlGetAce(Dacl, 0, &Ace), DaclSecurityDescriptor < 0)
          || (DaclSecurityDescriptor = RtlGetAcesBufferSize(Dacl, &AceListLength), DaclSecurityDescriptor < 0)
          || (DaclSecurityDescriptor = RtlAddAce(v11, 2u, 1u, Ace, AceListLength), DaclSecurityDescriptor < 0)
          || (DaclSecurityDescriptor = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u), DaclSecurityDescriptor < 0)
          || (DaclSecurityDescriptor = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v11, 0),
              DaclSecurityDescriptor < 0)
          || (DaclSecurityDescriptor = ZwSetSecurityObject(FileHandle, 4u, SecurityDescriptor),
              DaclSecurityDescriptor < 0) )
        {
          if ( (unsigned int)dword_140019000 > 3 )
          {
            v32 = &v18;
            v18 = DaclSecurityDescriptor;
            v33 = 4;
            tlgWriteTransfer_EtwWriteTransfer(v12, (int)&byte_140016D91, v13, v14, ShareAccessa, &v31);
          }
        }
        ExFreePoolWithTag(v11, 0);
        goto LABEL_35;
      }
      v7 = -1073741801;
      DaclSecurityDescriptor = -1073741801;
      if ( (unsigned int)dword_140019000 > 3 )
      {
        v18 = -1073741801;
        goto LABEL_15;
      }
    }
LABEL_35:
    ExFreePoolWithTag(Pool2, 0);
    goto LABEL_36;
  }
  v4 = -1073741801;
  DaclSecurityDescriptor = -1073741801;
  if ( (unsigned int)dword_140019000 > 3 )
  {
    v18 = -1073741801;
    goto LABEL_8;
  }
LABEL_36:
  if ( FileHandle )
    ZwClose(FileHandle);
  return (unsigned int)DaclSecurityDescriptor;
}

```

## disassembly

```asm
0x14001e1a0  push    rbp
0x14001e1a2  push    rbx
0x14001e1a3  push    rsi
0x14001e1a4  push    rdi
0x14001e1a5  push    r14
0x14001e1a7  push    r15
0x14001e1a9  lea     rbp, [rsp-18h]
0x14001e1ae  sub     rsp, 118h
0x14001e1b5  mov     rax, cs:__security_cookie
0x14001e1bc  xor     rax, rsp
0x14001e1bf  mov     [rbp+40h+var_38], rax
0x14001e1c3  xor     r15d, r15d
0x14001e1c6  lea     rdx, aDeviceBootdevi; "\\Device\\BootDevice\\"
0x14001e1cd  xorps   xmm0, xmm0
0x14001e1d0  mov     [rsp+140h+AceListLength], r15d
0x14001e1d5  xorps   xmm1, xmm1
0x14001e1d8  mov     byte ptr [rsp+140h+var_10B], r15b
0x14001e1dd  xor     eax, eax
0x14001e1df  mov     [rsp+140h+Dacl], r15
0x14001e1e4  movups  xmmword ptr [rsp+140h+ObjectAttributes.ObjectName], xmm0
0x14001e1e9  lea     rcx, [rbp+40h+DestinationString]; DestinationString
0x14001e1ed  mov     [rsp+140h+DaclPresent], r15b
0x14001e1f2  movups  xmmword ptr [rsp+140h+ObjectAttributes+1Ch], xmm0
0x14001e1f7  mov     byte ptr [rsp+140h+var_10B+1], r15b
0x14001e1fc  mov     [rsp+140h+Ace], r15
0x14001e201  mov     dword ptr [rsp+140h+var_10B+3], r15d
0x14001e206  movups  xmmword ptr [rbp+40h+IoStatusBlock], xmm0
0x14001e20a  mov     [rbp+40h+var_80], rax
0x14001e20e  movups  [rbp+40h+SecurityDescriptor], xmm1
0x14001e212  mov     [rsp+140h+FileHandle], r15
0x14001e217  movups  [rbp+40h+var_90], xmm1
0x14001e21b  movups  xmmword ptr [rsp+140h+ObjectAttributes.Length], xmm0
0x14001e220  movups  xmmword ptr [rbp+40h+DestinationString.Length], xmm0
0x14001e224  call    cs:__imp_RtlInitUnicodeString
0x14001e22b  nop     dword ptr [rax+rax+00h]
0x14001e230  lea     rax, [rbp+40h+DestinationString]
0x14001e234  mov     [rsp+140h+OpenOptions], 21h ; '!'; OpenOptions
0x14001e23c  xorps   xmm0, xmm0
0x14001e23f  mov     [rsp+140h+ObjectAttributes.ObjectName], rax
0x14001e244  lea     r9, [rbp+40h+IoStatusBlock]; IoStatusBlock
0x14001e248  mov     [rsp+140h+ObjectAttributes.Length], 30h ; '0'
0x14001e250  lea     r8, [rsp+140h+ObjectAttributes]; ObjectAttributes
0x14001e255  mov     [rsp+140h+ObjectAttributes.RootDirectory], r15
0x14001e25a  mov     edx, 60000h; DesiredAccess
0x14001e25f  mov     [rsp+140h+ObjectAttributes.Attributes], 200h
0x14001e267  lea     rcx, [rsp+140h+FileHandle]; FileHandle
0x14001e26c  mov     [rsp+140h+ShareAccess], 7; int
0x14001e274  movdqu  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001e279  call    cs:__imp_ZwOpenFile
0x14001e280  nop     dword ptr [rax+rax+00h]
0x14001e285  mov     ebx, eax
0x14001e287  test    eax, eax
0x14001e289  jns     short loc_14001E2C9
0x14001e28b  mov     ecx, cs:dword_140019000; int
0x14001e291  cmp     ecx, 3
0x14001e294  jbe     loc_14001E613
0x14001e29a  mov     [rsp+140h+var_110], eax
0x14001e29e  mov     [rbp+40h+var_40], 4
0x14001e2a6  lea     rax, [rsp+140h+var_110]
0x14001e2ab  mov     [rbp+40h+var_48], rax
0x14001e2af  lea     rdx, byte_140016D91; int
0x14001e2b6  lea     rax, [rbp+40h+var_68]
0x14001e2ba  mov     qword ptr [rsp+140h+OpenOptions], rax; PEVENT_DATA_DESCRIPTOR
0x14001e2bf  call    _tlgWriteTransfer_EtwWriteTransfer
0x14001e2c4  jmp     loc_14001E613
0x14001e2c9  mov     rcx, [rsp+140h+FileHandle]; Handle
0x14001e2ce  lea     rax, [rsp+140h+var_10B+3]
0x14001e2d3  xor     r9d, r9d; Length
0x14001e2d6  mov     qword ptr [rsp+140h+ShareAccess], rax; LengthNeeded
0x14001e2db  xor     r8d, r8d; SecurityDescriptor
0x14001e2de  lea     edi, [r9+4]
0x14001e2e2  mov     edx, edi; SecurityInformation
0x14001e2e4  call    cs:__imp_ZwQuerySecurityObject
0x14001e2eb  nop     dword ptr [rax+rax+00h]
0x14001e2f0  mov     ebx, eax
0x14001e2f2  cmp     eax, 0C0000023h
0x14001e2f7  jz      short loc_14001E312
0x14001e2f9  mov     eax, cs:dword_140019000
0x14001e2ff  cmp     eax, 3
0x14001e302  jbe     loc_14001E613
0x14001e308  mov     [rsp+140h+var_110], ebx
0x14001e30c  mov     [rbp+40h+var_40], rdi
0x14001e310  jmp     short loc_14001E2A6
0x14001e312  mov     ebx, dword ptr [rsp+140h+var_10B+3]
0x14001e316  mov     esi, 100h
0x14001e31b  mov     edx, ebx
0x14001e31d  mov     ecx, esi
0x14001e31f  mov     r8d, 44736642h
0x14001e325  call    cs:__imp_ExAllocatePool2
0x14001e32c  nop     dword ptr [rax+rax+00h]
0x14001e331  mov     r14, rax
0x14001e334  test    rax, rax
0x14001e337  jnz     short loc_14001E355
0x14001e339  mov     eax, cs:dword_140019000
0x14001e33f  mov     ecx, 0C0000017h
0x14001e344  mov     ebx, ecx
0x14001e346  cmp     eax, 3
0x14001e349  jbe     loc_14001E613
0x14001e34f  mov     [rsp+140h+var_110], ecx
0x14001e353  jmp     short loc_14001E30C
0x14001e355  mov     rcx, [rsp+140h+FileHandle]; Handle
0x14001e35a  lea     rax, [rsp+140h+var_10B+3]
0x14001e35f  mov     r9d, ebx; Length
0x14001e362  mov     qword ptr [rsp+140h+ShareAccess], rax; int
0x14001e367  mov     r8, r14; SecurityDescriptor
0x14001e36a  mov     edx, edi; SecurityInformation
0x14001e36c  call    cs:__imp_ZwQuerySecurityObject
0x14001e373  nop     dword ptr [rax+rax+00h]
0x14001e378  mov     ebx, eax
0x14001e37a  test    eax, eax
0x14001e37c  jns     short loc_14001E3B8
0x14001e37e  mov     eax, cs:dword_140019000
0x14001e384  cmp     eax, 3
0x14001e387  jbe     loc_14001E602
0x14001e38d  mov     [rsp+140h+var_110], ebx
0x14001e391  lea     rax, [rsp+140h+var_110]
0x14001e396  mov     [rbp+40h+var_40], rdi
0x14001e39a  mov     [rbp+40h+var_48], rax
0x14001e39e  lea     rdx, byte_140016D91; int
0x14001e3a5  lea     rax, [rbp+40h+var_68]
0x14001e3a9  mov     qword ptr [rsp+140h+OpenOptions], rax; PEVENT_DATA_DESCRIPTOR
0x14001e3ae  call    _tlgWriteTransfer_EtwWriteTransfer
0x14001e3b3  jmp     loc_14001E602
0x14001e3b8  lea     r9, [rsp+140h+var_10B+1]; DaclDefaulted
0x14001e3bd  mov     rcx, r14; SecurityDescriptor
0x14001e3c0  lea     r8, [rsp+140h+Dacl]; Dacl
0x14001e3c5  lea     rdx, [rsp+140h+DaclPresent]; DaclPresent
0x14001e3ca  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x14001e3d1  nop     dword ptr [rax+rax+00h]
0x14001e3d6  mov     ebx, eax
0x14001e3d8  test    eax, eax
0x14001e3da  js      short loc_14001E37E
0x14001e3dc  cmp     [rsp+140h+DaclPresent], r15b
0x14001e3e1  jz      loc_14001E602
0x14001e3e7  mov     rcx, [rsp+140h+Dacl]; Acl
0x14001e3ec  test    rcx, rcx
0x14001e3ef  jz      loc_14001E602
0x14001e3f5  mov     rax, cs:__imp_SeExports
0x14001e3fc  lea     rdx, [rsp+140h+var_10B]
0x14001e401  mov     qword ptr [rsp+140h+OpenOptions], rdx; __int64
0x14001e406  mov     r9d, 1000A1h
0x14001e40c  xor     r8d, r8d
0x14001e40f  xor     edx, edx
0x14001e411  mov     rax, [rax]
0x14001e414  mov     rax, [rax+238h]
0x14001e41b  mov     qword ptr [rsp+140h+ShareAccess], rax; Sid1
0x14001e420  call    BfsVerifyAce
0x14001e425  mov     ebx, eax
0x14001e427  test    eax, eax
0x14001e429  js      loc_14001E37E
0x14001e42f  cmp     byte ptr [rsp+140h+var_10B], r15b
0x14001e434  jnz     loc_14001E602
0x14001e43a  mov     rax, cs:__imp_SeExports
0x14001e441  mov     rcx, rsi
0x14001e444  mov     rdx, [rax]
0x14001e447  mov     rax, [rdx+238h]
0x14001e44e  movzx   r8d, byte ptr [rax+1]
0x14001e453  mov     rax, [rsp+140h+Dacl]
0x14001e458  movzx   edx, word ptr [rax+2]
0x14001e45c  add     edx, 10h
0x14001e45f  lea     ebx, [rdx+r8*4]
0x14001e463  mov     r8d, 41736642h
0x14001e469  mov     edx, ebx
0x14001e46b  call    cs:__imp_ExAllocatePool2
0x14001e472  nop     dword ptr [rax+rax+00h]
0x14001e477  mov     rsi, rax
0x14001e47a  test    rax, rax
0x14001e47d  jnz     short loc_14001E49E
0x14001e47f  mov     eax, cs:dword_140019000
0x14001e485  mov     ecx, 0C0000017h
0x14001e48a  mov     ebx, ecx
0x14001e48c  cmp     eax, 3
0x14001e48f  jbe     loc_14001E602
0x14001e495  mov     [rsp+140h+var_110], ecx
0x14001e499  jmp     loc_14001E391
0x14001e49e  mov     rax, [rsp+140h+Dacl]
0x14001e4a3  mov     edx, ebx; AclLength
0x14001e4a5  mov     rcx, rsi; Acl
0x14001e4a8  movzx   r8d, byte ptr [rax]; AclRevision
0x14001e4ac  call    cs:__imp_RtlCreateAcl
0x14001e4b3  nop     dword ptr [rax+rax+00h]
0x14001e4b8  mov     ebx, eax
0x14001e4ba  test    eax, eax
0x14001e4bc  js      loc_14001E5C0
0x14001e4c2  mov     rax, cs:__imp_SeExports
0x14001e4c9  mov     r9d, 1000A1h; AccessMask
0x14001e4cf  movzx   edx, byte ptr [rsi]; AceRevision
0x14001e4d2  xor     r8d, r8d; AceFlags
0x14001e4d5  mov     rcx, rsi; Acl
0x14001e4d8  mov     rax, [rax]
0x14001e4db  mov     rax, [rax+238h]
0x14001e4e2  mov     qword ptr [rsp+140h+ShareAccess], rax; Sid
0x14001e4e7  call    cs:__imp_RtlAddAccessAllowedAceEx
0x14001e4ee  nop     dword ptr [rax+rax+00h]
0x14001e4f3  mov     ebx, eax
0x14001e4f5  test    eax, eax
0x14001e4f7  js      loc_14001E5C0
0x14001e4fd  mov     rcx, [rsp+140h+Dacl]; Acl
0x14001e502  lea     r8, [rsp+140h+Ace]; Ace
0x14001e507  xor     edx, edx; AceIndex
0x14001e509  call    cs:__imp_RtlGetAce
0x14001e510  nop     dword ptr [rax+rax+00h]
0x14001e515  mov     ebx, eax
0x14001e517  test    eax, eax
0x14001e519  js      loc_14001E5C0
0x14001e51f  mov     rcx, [rsp+140h+Dacl]
0x14001e524  lea     rdx, [rsp+140h+AceListLength]
0x14001e529  call    cs:__imp_RtlGetAcesBufferSize
0x14001e530  nop     dword ptr [rax+rax+00h]
0x14001e535  mov     ebx, eax
0x14001e537  test    eax, eax
0x14001e539  js      loc_14001E5C0
0x14001e53f  mov     eax, [rsp+140h+AceListLength]
0x14001e543  mov     edx, 2; AceRevision
0x14001e548  mov     r9, [rsp+140h+Ace]; AceList
0x14001e54d  mov     rcx, rsi; Acl
0x14001e550  mov     [rsp+140h+ShareAccess], eax; int
0x14001e554  lea     r8d, [rdx-1]; StartingAceIndex
0x14001e558  call    cs:__imp_RtlAddAce
0x14001e55f  nop     dword ptr [rax+rax+00h]
0x14001e564  mov     ebx, eax
0x14001e566  test    eax, eax
0x14001e568  js      short loc_14001E5C0
0x14001e56a  mov     edx, 1; Revision
0x14001e56f  lea     rcx, [rbp+40h+SecurityDescriptor]; SecurityDescriptor
0x14001e573  call    cs:__imp_RtlCreateSecurityDescriptor
0x14001e57a  nop     dword ptr [rax+rax+00h]
0x14001e57f  mov     ebx, eax
0x14001e581  test    eax, eax
0x14001e583  js      short loc_14001E5C0
0x14001e585  xor     r9d, r9d; DaclDefaulted
0x14001e588  lea     rcx, [rbp+40h+SecurityDescriptor]; SecurityDescriptor
0x14001e58c  mov     r8, rsi; Dacl
0x14001e58f  mov     dl, 1; DaclPresent
0x14001e591  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14001e598  nop     dword ptr [rax+rax+00h]
0x14001e59d  mov     ebx, eax
0x14001e59f  test    eax, eax
0x14001e5a1  js      short loc_14001E5C0
0x14001e5a3  mov     rcx, [rsp+140h+FileHandle]; Handle
0x14001e5a8  lea     r8, [rbp+40h+SecurityDescriptor]; SecurityDescriptor
0x14001e5ac  mov     edx, edi; SecurityInformation
0x14001e5ae  call    cs:__imp_ZwSetSecurityObject
0x14001e5b5  nop     dword ptr [rax+rax+00h]
0x14001e5ba  mov     ebx, eax
0x14001e5bc  test    eax, eax
0x14001e5be  jns     short loc_14001E5F1
0x14001e5c0  mov     eax, cs:dword_140019000
0x14001e5c6  cmp     eax, 3
0x14001e5c9  jbe     short loc_14001E5F1
0x14001e5cb  lea     rax, [rsp+140h+var_110]
0x14001e5d0  mov     [rbp+40h+var_48], rax
0x14001e5d4  lea     rax, [rbp+40h+var_68]
0x14001e5d8  mov     qword ptr [rsp+140h+OpenOptions], rax; PEVENT_DATA_DESCRIPTOR
0x14001e5dd  lea     rdx, byte_140016D91; int
0x14001e5e4  mov     [rsp+140h+var_110], ebx
0x14001e5e8  mov     [rbp+40h+var_40], rdi
0x14001e5ec  call    _tlgWriteTransfer_EtwWriteTransfer
0x14001e5f1  xor     edx, edx; Tag
0x14001e5f3  mov     rcx, rsi; P
0x14001e5f6  call    cs:__imp_ExFreePoolWithTag
0x14001e5fd  nop     dword ptr [rax+rax+00h]
0x14001e602  xor     edx, edx; Tag
0x14001e604  mov     rcx, r14; P
0x14001e607  call    cs:__imp_ExFreePoolWithTag
0x14001e60e  nop     dword ptr [rax+rax+00h]
0x14001e613  mov     rcx, [rsp+140h+FileHandle]; Handle
0x14001e618  test    rcx, rcx
0x14001e61b  jz      short loc_14001E629
0x14001e61d  call    cs:__imp_ZwClose
0x14001e624  nop     dword ptr [rax+rax+00h]
0x14001e629  mov     eax, ebx
0x14001e62b  mov     rcx, [rbp+40h+var_38]
0x14001e62f  xor     rcx, rsp; StackCookie
0x14001e632  call    __security_check_cookie
0x14001e637  add     rsp, 118h
0x14001e63e  pop     r15
0x14001e640  pop     r14
0x14001e642  pop     rdi
0x14001e643  pop     rsi
0x14001e644  pop     rbx
0x14001e645  pop     rbp
0x14001e646  retn
```
