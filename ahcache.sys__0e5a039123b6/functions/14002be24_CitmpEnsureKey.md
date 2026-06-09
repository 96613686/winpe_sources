# CitmpEnsureKey

- ea: `0x14002be24`
- end: `0x14002c117`
- name: `CitmpEnsureKey`
- size: `755`
- prototype: `__int64 __fastcall(void **, const WCHAR *, char)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x14002c120`
- `0x14002c4a4`

## callees

- `0x14002be24`
- `0x14003e364`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002c0d7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002c0d7`
- `ntoskrnl!SeExports` at `0x14002bec1`
- `ntoskrnl!SeExports` at `0x14002bf6a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002bfec`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002bfec`
- `ntoskrnl!ZwClose` at `0x14002c0ec`
- `ntoskrnl!ZwClose` at `0x14002c0ec`
- `ntoskrnl!ZwCreateKey` at `0x14002c04c`
- `ntoskrnl!ZwCreateKey` at `0x14002c04c`
- `ntoskrnl!ExAllocatePool2` at `0x14002beee`
- `ntoskrnl!ExAllocatePool2` at `0x14002beee`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14002be8a`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14002be8a`
- `ntoskrnl!RtlLengthSid` at `0x14002bed2`
- `ntoskrnl!RtlLengthSid` at `0x14002bed2`
- `ntoskrnl!RtlCreateAcl` at `0x14002bf33`
- `ntoskrnl!RtlCreateAcl` at `0x14002bf33`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14002bf89`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14002bf89`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14002bfb7`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14002bfb7`
- `ntoskrnl!ZwSetSecurityObject` at `0x14002c098`
- `ntoskrnl!ZwSetSecurityObject` at `0x14002c098`

## string_xrefs

- `0x14002c05e`: `Failed to create key [%x]`
- `0x14002be9c`: `Failed to create descriptor [%x]`
- `0x14002bf45`: `Failed to create acl [%x]`
- `0x14002bf9b`: `Failed to add access [%x]`
- `0x14002bfc9`: `Failed to set access [%x]`
- `0x14002c0aa`: `Failed to set key security [%x]`

## pseudocode

```c
__int64 __fastcall CitmpEnsureKey(void **a1, const WCHAR *a2, char a3)
{
  NTSTATUS v6; // eax
  unsigned int v7; // ebx
  ULONG v8; // ebx
  struct _ACL *Pool2; // rax
  struct _ACL *v10; // rdi
  NTSTATUS Acl; // eax
  const char *v12; // r9
  __int64 v13; // r8
  _OWORD *v14; // rbx
  NTSTATUS v15; // eax
  const char *v16; // r9
  __int64 v17; // r8
  PUNICODE_STRING Class; // [rsp+20h] [rbp-59h]
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-39h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+50h] [rbp-29h] BYREF
  __int64 v22; // [rsp+70h] [rbp-9h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-1h] BYREF
  ULONG Disposition; // [rsp+F0h] [rbp+77h] BYREF
  void *KeyHandle; // [rsp+F8h] [rbp+7Fh] BYREF

  v22 = 0;
  KeyHandle = 0;
  Disposition = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  if ( !a3 )
  {
    v14 = 0;
    v10 = 0;
    goto LABEL_15;
  }
  v6 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  v7 = v6;
  if ( v6 < 0 )
  {
    AslLogCallPrintf(1, "CitmpEnsureKey", 690, "Failed to create descriptor [%x]", v6);
    goto LABEL_25;
  }
  v8 = RtlLengthSid(SeExports->SeLocalSystemSid) + 20;
  Pool2 = (struct _ACL *)ExAllocatePool2(256, v8, 1836345667);
  v10 = Pool2;
  if ( !Pool2 )
  {
    v7 = -1073741670;
    AslLogCallPrintf(1, "CitmpEnsureKey", 698, "Out of memory");
    goto LABEL_25;
  }
  Acl = RtlCreateAcl(Pool2, v8, 2u);
  v7 = Acl;
  if ( Acl >= 0 )
  {
    Acl = RtlAddAccessAllowedAce(v10, 2u, 0xF003Fu, SeExports->SeLocalSystemSid);
    v7 = Acl;
    if ( Acl < 0 )
    {
      v12 = "Failed to add access [%x]";
      v13 = 713;
      goto LABEL_8;
    }
    Acl = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v10, 0);
    v7 = Acl;
    if ( Acl < 0 )
    {
      v12 = "Failed to set access [%x]";
      v13 = 719;
      goto LABEL_8;
    }
    v14 = SecurityDescriptor;
LABEL_15:
    RtlInitUnicodeString(&DestinationString, a2);
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.SecurityDescriptor = v14;
    ObjectAttributes.SecurityQualityOfService = 0;
    v15 = ZwCreateKey(&KeyHandle, 0xF003Fu, &ObjectAttributes, 0, 0, 0, &Disposition);
    v7 = v15;
    if ( v15 >= 0 )
    {
      if ( Disposition == 1 || !a3 || (v15 = ZwSetSecurityObject(KeyHandle, 4u, SecurityDescriptor), v7 = v15, v15 >= 0) )
      {
        v7 = 0;
        *a1 = KeyHandle;
        KeyHandle = 0;
LABEL_23:
        if ( !v10 )
          goto LABEL_25;
        goto LABEL_24;
      }
      v16 = "Failed to set key security [%x]";
      v17 = 758;
    }
    else
    {
      v16 = "Failed to create key [%x]";
      v17 = 745;
    }
    LODWORD(Class) = v15;
    AslLogCallPrintf(1, "CitmpEnsureKey", v17, v16, Class);
    goto LABEL_23;
  }
  v12 = "Failed to create acl [%x]";
  v13 = 704;
LABEL_8:
  AslLogCallPrintf(1, "CitmpEnsureKey", v13, v12, Acl);
LABEL_24:
  ExFreePoolWithTag(v10, 0x6D746943u);
LABEL_25:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return v7;
}

```

## disassembly

```asm
0x14002be24  mov     [rsp-8+arg_0], rbx
0x14002be29  mov     [rsp-8+arg_8], rsi
0x14002be2e  push    rbp
0x14002be2f  push    rdi
0x14002be30  push    r13
0x14002be32  push    r14
0x14002be34  push    r15
0x14002be36  lea     rbp, [rsp-37h]
0x14002be3b  sub     rsp, 0B0h
0x14002be42  xor     eax, eax
0x14002be44  xorps   xmm0, xmm0
0x14002be47  mov     [rbp+57h+var_60], rax
0x14002be4b  xorps   xmm1, xmm1
0x14002be4e  mov     [rbp+57h+KeyHandle], rax
0x14002be52  mov     sil, r8b
0x14002be55  mov     [rbp+57h+arg_10], eax
0x14002be58  mov     r15, rdx
0x14002be5b  lea     r13d, [rax+1]
0x14002be5f  mov     r14, rcx
0x14002be62  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14002be66  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x14002be6a  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x14002be6e  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x14002be72  movups  [rbp+57h+SecurityDescriptor], xmm0
0x14002be76  movups  [rbp+57h+var_70], xmm0
0x14002be7a  test    r8b, r8b
0x14002be7d  jz      loc_14002BFE1
0x14002be83  mov     edx, r13d; Revision
0x14002be86  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x14002be8a  call    cs:__imp_RtlCreateSecurityDescriptor
0x14002be91  nop     dword ptr [rax+rax+00h]
0x14002be96  mov     ebx, eax
0x14002be98  test    eax, eax
0x14002be9a  jns     short loc_14002BEC1
0x14002be9c  lea     r9, aFailedToCreate_15; "Failed to create descriptor [%x]"
0x14002bea3  mov     dword ptr [rsp+0D0h+Class], eax
0x14002bea7  mov     r8d, 2B2h
0x14002bead  lea     rdx, aCitmpensurekey; "CitmpEnsureKey"
0x14002beb4  mov     ecx, r13d
0x14002beb7  call    AslLogCallPrintf
0x14002bebc  jmp     loc_14002C0E3
0x14002bec1  mov     rax, cs:__imp_SeExports
0x14002bec8  mov     rcx, [rax]
0x14002becb  mov     rcx, [rcx+108h]; Sid
0x14002bed2  call    cs:__imp_RtlLengthSid
0x14002bed9  nop     dword ptr [rax+rax+00h]
0x14002bede  mov     ecx, 100h
0x14002bee3  mov     r8d, 6D746943h
0x14002bee9  lea     ebx, [rax+14h]
0x14002beec  mov     edx, ebx
0x14002beee  call    cs:__imp_ExAllocatePool2
0x14002bef5  nop     dword ptr [rax+rax+00h]
0x14002befa  mov     rdi, rax
0x14002befd  test    rax, rax
0x14002bf00  jnz     short loc_14002BF28
0x14002bf02  lea     r9, aOutOfMemory; "Out of memory"
0x14002bf09  mov     r8d, 2BAh
0x14002bf0f  lea     rdx, aCitmpensurekey; "CitmpEnsureKey"
0x14002bf16  mov     ecx, r13d
0x14002bf19  mov     ebx, 0C000009Ah
0x14002bf1e  call    AslLogCallPrintf
0x14002bf23  jmp     loc_14002C0E3
0x14002bf28  mov     r8d, 2; AclRevision
0x14002bf2e  mov     edx, ebx; AclLength
0x14002bf30  mov     rcx, rdi; Acl
0x14002bf33  call    cs:__imp_RtlCreateAcl
0x14002bf3a  nop     dword ptr [rax+rax+00h]
0x14002bf3f  mov     ebx, eax
0x14002bf41  test    eax, eax
0x14002bf43  jns     short loc_14002BF6A
0x14002bf45  lea     r9, aFailedToCreate_8; "Failed to create acl [%x]"
0x14002bf4c  mov     r8d, 2C0h
0x14002bf52  lea     rdx, aCitmpensurekey; "CitmpEnsureKey"
0x14002bf59  mov     dword ptr [rsp+0D0h+Class], eax
0x14002bf5d  mov     ecx, r13d
0x14002bf60  call    AslLogCallPrintf
0x14002bf65  jmp     loc_14002C0CF
0x14002bf6a  mov     rax, cs:__imp_SeExports
0x14002bf71  mov     edx, 2; AceRevision
0x14002bf76  mov     r8d, 0F003Fh; AccessMask
0x14002bf7c  mov     rcx, rdi; Acl
0x14002bf7f  mov     r9, [rax]
0x14002bf82  mov     r9, [r9+108h]; Sid
0x14002bf89  call    cs:__imp_RtlAddAccessAllowedAce
0x14002bf90  nop     dword ptr [rax+rax+00h]
0x14002bf95  mov     ebx, eax
0x14002bf97  test    eax, eax
0x14002bf99  jns     short loc_14002BFAA
0x14002bf9b  lea     r9, aFailedToAddAcc; "Failed to add access [%x]"
0x14002bfa2  mov     r8d, 2C9h
0x14002bfa8  jmp     short loc_14002BF52
0x14002bfaa  xor     r9d, r9d; DaclDefaulted
0x14002bfad  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x14002bfb1  mov     r8, rdi; Dacl
0x14002bfb4  mov     dl, r13b; DaclPresent
0x14002bfb7  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14002bfbe  nop     dword ptr [rax+rax+00h]
0x14002bfc3  mov     ebx, eax
0x14002bfc5  test    eax, eax
0x14002bfc7  jns     short loc_14002BFDB
0x14002bfc9  lea     r9, aFailedToSetAcc; "Failed to set access [%x]"
0x14002bfd0  mov     r8d, 2CFh
0x14002bfd6  jmp     loc_14002BF52
0x14002bfdb  lea     rbx, [rbp+57h+SecurityDescriptor]
0x14002bfdf  jmp     short loc_14002BFE5
0x14002bfe1  xor     ebx, ebx
0x14002bfe3  xor     edi, edi
0x14002bfe5  mov     rdx, r15; SourceString
0x14002bfe8  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14002bfec  call    cs:__imp_RtlInitUnicodeString
0x14002bff3  nop     dword ptr [rax+rax+00h]
0x14002bff8  lea     rax, [rbp+57h+DestinationString]
0x14002bffc  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14002c003  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14002c007  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14002c00b  lea     rax, [rbp+57h+arg_10]
0x14002c00f  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14002c017  mov     [rsp+0D0h+Disposition], rax; Disposition
0x14002c01c  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14002c020  mov     [rsp+0D0h+CreateOptions], 0; CreateOptions
0x14002c028  xor     r9d, r9d; TitleIndex
0x14002c02b  mov     edx, 0F003Fh; DesiredAccess
0x14002c030  mov     [rsp+0D0h+Class], 0; Class
0x14002c039  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14002c040  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], rbx
0x14002c044  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], 0
0x14002c04c  call    cs:__imp_ZwCreateKey
0x14002c053  nop     dword ptr [rax+rax+00h]
0x14002c058  mov     ebx, eax
0x14002c05a  test    eax, eax
0x14002c05c  jns     short loc_14002C080
0x14002c05e  lea     r9, aFailedToCreate_4; "Failed to create key [%x]"
0x14002c065  mov     r8d, 2E9h
0x14002c06b  lea     rdx, aCitmpensurekey; "CitmpEnsureKey"
0x14002c072  mov     dword ptr [rsp+0D0h+Class], eax
0x14002c076  mov     ecx, r13d
0x14002c079  call    AslLogCallPrintf
0x14002c07e  jmp     short loc_14002C0CA
0x14002c080  cmp     [rbp+57h+arg_10], r13d
0x14002c084  jz      short loc_14002C0B9
0x14002c086  test    sil, sil
0x14002c089  jz      short loc_14002C0B9
0x14002c08b  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x14002c08f  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x14002c093  mov     edx, 4; SecurityInformation
0x14002c098  call    cs:__imp_ZwSetSecurityObject
0x14002c09f  nop     dword ptr [rax+rax+00h]
0x14002c0a4  mov     ebx, eax
0x14002c0a6  test    eax, eax
0x14002c0a8  jns     short loc_14002C0B9
0x14002c0aa  lea     r9, aFailedToSetKey; "Failed to set key security [%x]"
0x14002c0b1  mov     r8d, 2F6h
0x14002c0b7  jmp     short loc_14002C06B
0x14002c0b9  mov     rax, [rbp+57h+KeyHandle]
0x14002c0bd  xor     ebx, ebx
0x14002c0bf  mov     [r14], rax
0x14002c0c2  mov     [rbp+57h+KeyHandle], 0
0x14002c0ca  test    rdi, rdi
0x14002c0cd  jz      short loc_14002C0E3
0x14002c0cf  mov     edx, 6D746943h; Tag
0x14002c0d4  mov     rcx, rdi; P
0x14002c0d7  call    cs:__imp_ExFreePoolWithTag
0x14002c0de  nop     dword ptr [rax+rax+00h]
0x14002c0e3  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x14002c0e7  test    rcx, rcx
0x14002c0ea  jz      short loc_14002C0F8
0x14002c0ec  call    cs:__imp_ZwClose
0x14002c0f3  nop     dword ptr [rax+rax+00h]
0x14002c0f8  lea     r11, [rsp+0D0h+var_20]
0x14002c100  mov     eax, ebx
0x14002c102  mov     rbx, [r11+30h]
0x14002c106  mov     rsi, [r11+38h]
0x14002c10a  mov     rsp, r11
0x14002c10d  pop     r15
0x14002c10f  pop     r14
0x14002c111  pop     r13
0x14002c113  pop     rdi
0x14002c114  pop     rbp
0x14002c115  retn
```
