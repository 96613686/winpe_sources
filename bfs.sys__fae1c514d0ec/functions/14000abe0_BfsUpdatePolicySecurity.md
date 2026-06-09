# BfsUpdatePolicySecurity

- ea: `0x14000abe0`
- end: `0x14000ae53`
- name: `BfsUpdatePolicySecurity`
- size: `627`
- prototype: `__int64 __fastcall(HANDLE Handle)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14001f078`

## callees

- `0x140001008`
- `0x14000abe0`
- `0x14000ae5c`
- `0x140013860`
- `0x140013c80`

## import_xrefs

- `ntoskrnl!ZwQueryDirectoryFile` at `0x14000ace3`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x14000ace3`
- `ntoskrnl!ZwSetSecurityObject` at `0x14000ae03`
- `ntoskrnl!ZwSetSecurityObject` at `0x14000ae03`
- `ntoskrnl!ZwOpenFile` at `0x14000ad51`
- `ntoskrnl!ZwOpenFile` at `0x14000ad51`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000ac34`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000ad01`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000ac34`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000ad01`
- `ntoskrnl!ZwClose` at `0x14000ad7d`
- `ntoskrnl!ZwClose` at `0x14000ae2c`
- `ntoskrnl!ZwClose` at `0x14000ad7d`
- `ntoskrnl!ZwClose` at `0x14000ae2c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ae16`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ae16`
- `ntoskrnl!ExAllocatePool2` at `0x14000ac4e`
- `ntoskrnl!ExAllocatePool2` at `0x14000ac4e`

## pseudocode

```c
__int64 __fastcall BfsUpdatePolicySecurity(HANDLE Handle)
{
  int v2; // ecx
  WCHAR *FileInformation; // rdi
  int v4; // r8d
  int v5; // r9d
  NTSTATUS updated; // ebx
  BOOLEAN RestartScan; // al
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  int IoStatusBlock; // [rsp+20h] [rbp-E0h]
  int IoStatusBlocka; // [rsp+20h] [rbp-E0h]
  int v14; // [rsp+60h] [rbp-A0h] BYREF
  void *FileHandle; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-90h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING v18; // [rsp+B0h] [rbp-50h] BYREF
  struct _IO_STATUS_BLOCK v19; // [rsp+C0h] [rbp-40h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v20; // [rsp+D0h] [rbp-30h] BYREF
  int *v21; // [rsp+F0h] [rbp-10h]
  __int64 v22; // [rsp+F8h] [rbp-8h]

  FileHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  v18 = 0;
  v19 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"S-1-*");
  FileInformation = (WCHAR *)ExAllocatePool2(256, 272, 1316185666);
  if ( !FileInformation )
  {
    updated = -1073741801;
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v14 = -1073741801;
      v21 = &v14;
      v22 = 4;
      tlgWriteTransfer_EtwWriteTransfer(v2, (int)&byte_140016D91, v4, v5, IoStatusBlock, &v20);
    }
    goto LABEL_17;
  }
  for ( RestartScan = 1; ; RestartScan = 0 )
  {
    updated = ZwQueryDirectoryFile(
                Handle,
                0,
                0,
                0,
                &v19,
                FileInformation,
                0x110u,
                FileNamesInformation,
                1u,
                &DestinationString,
                RestartScan);
    if ( updated < 0 )
      goto LABEL_9;
    RtlInitUnicodeString(&v18, FileInformation + 6);
    ObjectAttributes.ObjectName = &v18;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = Handle;
    ObjectAttributes.Attributes = 512;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    updated = ZwOpenFile(&FileHandle, 0x1F01FFu, &ObjectAttributes, &v19, 3u, 0x21u);
    if ( updated < 0 )
      break;
    updated = BfsUpdateUserPolicyDirectorySecurity(FileHandle, &DestinationString);
    if ( updated < 0 )
      break;
    ZwClose(FileHandle);
    FileHandle = 0;
LABEL_9:
    memset(FileInformation, 0, 0x110u);
    if ( updated < 0 )
    {
      if ( updated == -1073741809 || updated == -2147483642 )
        updated = ZwSetSecurityObject(Handle, 0x17u, gBfsPolicyStorageDirectoryDescriptor);
      goto LABEL_16;
    }
  }
  if ( (unsigned int)dword_140019000 > 3 )
  {
    v14 = updated;
    v21 = &v14;
    v22 = 4;
    tlgWriteTransfer_EtwWriteTransfer(v8, (int)&byte_140016D91, v9, v10, IoStatusBlocka, &v20);
  }
LABEL_16:
  ExFreePoolWithTag(FileInformation, 0);
LABEL_17:
  if ( FileHandle )
    ZwClose(FileHandle);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x14000abe0  push    rbp
0x14000abe2  push    rbx
0x14000abe3  push    rsi
0x14000abe4  push    rdi
0x14000abe5  lea     rbp, [rsp-18h]
0x14000abea  sub     rsp, 118h
0x14000abf1  mov     rax, cs:__security_cookie
0x14000abf8  xor     rax, rsp
0x14000abfb  mov     [rbp+30h+var_30], rax
0x14000abff  xorps   xmm0, xmm0
0x14000ac02  lea     rdx, aS1; "S-1-*"
0x14000ac09  mov     rsi, rcx
0x14000ac0c  xor     eax, eax
0x14000ac0e  xorps   xmm1, xmm1
0x14000ac11  mov     [rsp+130h+FileHandle], rax
0x14000ac16  movups  xmmword ptr [rbp+30h+ObjectAttributes.ObjectName], xmm0
0x14000ac1a  lea     rcx, [rsp+130h+DestinationString]; DestinationString
0x14000ac1f  movups  xmmword ptr [rbp+30h+ObjectAttributes+1Ch], xmm0
0x14000ac23  movups  xmmword ptr [rbp+30h+ObjectAttributes.Length], xmm0
0x14000ac27  movups  xmmword ptr [rbp+30h+var_80.Length], xmm0
0x14000ac2b  movups  xmmword ptr [rbp+30h+var_70], xmm0
0x14000ac2f  movups  xmmword ptr [rsp+130h+DestinationString.Length], xmm1
0x14000ac34  call    cs:__imp_RtlInitUnicodeString
0x14000ac3b  nop     dword ptr [rax+rax+00h]
0x14000ac40  mov     edx, 110h
0x14000ac45  mov     r8d, 4E736642h
0x14000ac4b  lea     ecx, [rdx-10h]
0x14000ac4e  call    cs:__imp_ExAllocatePool2
0x14000ac55  nop     dword ptr [rax+rax+00h]
0x14000ac5a  mov     rdi, rax
0x14000ac5d  test    rax, rax
0x14000ac60  jnz     short loc_14000ACA5
0x14000ac62  mov     eax, cs:dword_140019000
0x14000ac68  mov     ebx, 0C0000017h
0x14000ac6d  cmp     eax, 3
0x14000ac70  jbe     loc_14000AE22
0x14000ac76  lea     rax, [rsp+130h+var_D0]
0x14000ac7b  mov     [rsp+130h+var_D0], ebx
0x14000ac7f  mov     [rbp+30h+var_40], rax
0x14000ac83  lea     rdx, byte_140016D91; int
0x14000ac8a  lea     rax, [rbp+30h+var_60]
0x14000ac8e  mov     [rbp+30h+var_38], 4
0x14000ac96  mov     [rsp+130h+FileInformation], rax; PEVENT_DATA_DESCRIPTOR
0x14000ac9b  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000aca0  jmp     loc_14000AE22
0x14000aca5  mov     al, 1
0x14000aca7  mov     [rsp+130h+RestartScan], al; RestartScan
0x14000acab  xor     r9d, r9d; ApcContext
0x14000acae  lea     rax, [rsp+130h+DestinationString]
0x14000acb3  xor     r8d, r8d; ApcRoutine
0x14000acb6  mov     [rsp+130h+FileName], rax; FileName
0x14000acbb  xor     edx, edx; Event
0x14000acbd  mov     [rsp+130h+ReturnSingleEntry], 1; ReturnSingleEntry
0x14000acc2  lea     rax, [rbp+30h+var_70]
0x14000acc6  mov     [rsp+130h+FileInformationClass], 0Ch; FileInformationClass
0x14000acce  mov     rcx, rsi; FileHandle
0x14000acd1  mov     [rsp+130h+Length], 110h; Length
0x14000acd9  mov     [rsp+130h+FileInformation], rdi; FileInformation
0x14000acde  mov     [rsp+130h+IoStatusBlock], rax; IoStatusBlock
0x14000ace3  call    cs:__imp_ZwQueryDirectoryFile
0x14000acea  nop     dword ptr [rax+rax+00h]
0x14000acef  mov     ebx, eax
0x14000acf1  test    eax, eax
0x14000acf3  js      loc_14000AD92
0x14000acf9  lea     rdx, [rdi+0Ch]; SourceString
0x14000acfd  lea     rcx, [rbp+30h+var_80]; DestinationString
0x14000ad01  call    cs:__imp_RtlInitUnicodeString
0x14000ad08  nop     dword ptr [rax+rax+00h]
0x14000ad0d  lea     rax, [rbp+30h+var_80]
0x14000ad11  mov     dword ptr [rsp+130h+FileInformation], 21h ; '!'; OpenOptions
0x14000ad19  xorps   xmm0, xmm0
0x14000ad1c  mov     [rbp+30h+ObjectAttributes.ObjectName], rax
0x14000ad20  lea     r9, [rbp+30h+var_70]; IoStatusBlock
0x14000ad24  mov     [rbp+30h+ObjectAttributes.Length], 30h ; '0'
0x14000ad2b  lea     r8, [rbp+30h+ObjectAttributes]; ObjectAttributes
0x14000ad2f  mov     [rbp+30h+ObjectAttributes.RootDirectory], rsi
0x14000ad33  mov     edx, 1F01FFh; DesiredAccess
0x14000ad38  mov     [rbp+30h+ObjectAttributes.Attributes], 200h
0x14000ad3f  lea     rcx, [rsp+130h+FileHandle]; FileHandle
0x14000ad44  mov     dword ptr [rsp+130h+IoStatusBlock], 3; int
0x14000ad4c  movdqu  xmmword ptr [rbp+30h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000ad51  call    cs:__imp_ZwOpenFile
0x14000ad58  nop     dword ptr [rax+rax+00h]
0x14000ad5d  mov     ebx, eax
0x14000ad5f  test    eax, eax
0x14000ad61  js      short loc_14000ADAD
0x14000ad63  mov     rcx, [rsp+130h+FileHandle]; Handle
0x14000ad68  lea     rdx, [rsp+130h+DestinationString]; FileName
0x14000ad6d  call    BfsUpdateUserPolicyDirectorySecurity
0x14000ad72  mov     ebx, eax
0x14000ad74  test    eax, eax
0x14000ad76  js      short loc_14000ADAD
0x14000ad78  mov     rcx, [rsp+130h+FileHandle]; Handle
0x14000ad7d  call    cs:__imp_ZwClose
0x14000ad84  nop     dword ptr [rax+rax+00h]
0x14000ad89  mov     [rsp+130h+FileHandle], 0
0x14000ad92  xor     edx, edx; Val
0x14000ad94  mov     r8d, 110h; Size
0x14000ad9a  mov     rcx, rdi; void *
0x14000ad9d  call    memset
0x14000ada2  test    ebx, ebx
0x14000ada4  js      short loc_14000ADE4
0x14000ada6  xor     al, al
0x14000ada8  jmp     loc_14000ACA7
0x14000adad  mov     eax, cs:dword_140019000
0x14000adb3  cmp     eax, 3
0x14000adb6  jbe     short loc_14000AE11
0x14000adb8  lea     rax, [rsp+130h+var_D0]
0x14000adbd  mov     [rsp+130h+var_D0], ebx
0x14000adc1  mov     [rbp+30h+var_40], rax
0x14000adc5  lea     rdx, byte_140016D91; int
0x14000adcc  lea     rax, [rbp+30h+var_60]
0x14000add0  mov     [rbp+30h+var_38], 4
0x14000add8  mov     [rsp+130h+FileInformation], rax; PEVENT_DATA_DESCRIPTOR
0x14000addd  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000ade2  jmp     short loc_14000AE11
0x14000ade4  cmp     ebx, 0C000000Fh
0x14000adea  jz      short loc_14000ADF4
0x14000adec  cmp     ebx, 80000006h
0x14000adf2  jnz     short loc_14000AE11
0x14000adf4  lea     r8, gBfsPolicyStorageDirectoryDescriptor; SecurityDescriptor
0x14000adfb  mov     edx, 17h; SecurityInformation
0x14000ae00  mov     rcx, rsi; Handle
0x14000ae03  call    cs:__imp_ZwSetSecurityObject
0x14000ae0a  nop     dword ptr [rax+rax+00h]
0x14000ae0f  mov     ebx, eax
0x14000ae11  xor     edx, edx; Tag
0x14000ae13  mov     rcx, rdi; P
0x14000ae16  call    cs:__imp_ExFreePoolWithTag
0x14000ae1d  nop     dword ptr [rax+rax+00h]
0x14000ae22  mov     rcx, [rsp+130h+FileHandle]; Handle
0x14000ae27  test    rcx, rcx
0x14000ae2a  jz      short loc_14000AE38
0x14000ae2c  call    cs:__imp_ZwClose
0x14000ae33  nop     dword ptr [rax+rax+00h]
0x14000ae38  mov     eax, ebx
0x14000ae3a  mov     rcx, [rbp+30h+var_30]
0x14000ae3e  xor     rcx, rsp; StackCookie
0x14000ae41  call    __security_check_cookie
0x14000ae46  add     rsp, 118h
0x14000ae4d  pop     rdi
0x14000ae4e  pop     rsi
0x14000ae4f  pop     rbx
0x14000ae50  pop     rbp
0x14000ae51  retn
```
