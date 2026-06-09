# BfsUpdatePolicySecurity

- ea: `0x14000aa50`
- end: `0x14000acc3`
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
- `0x14000aa50`
- `0x14000accc`
- `0x140013730`
- `0x140013b40`

## import_xrefs

- `ntoskrnl!ZwQueryDirectoryFile` at `0x14000ab53`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x14000ab53`
- `ntoskrnl!ZwSetSecurityObject` at `0x14000ac73`
- `ntoskrnl!ZwSetSecurityObject` at `0x14000ac73`
- `ntoskrnl!ZwOpenFile` at `0x14000abc1`
- `ntoskrnl!ZwOpenFile` at `0x14000abc1`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000aaa4`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000ab71`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000aaa4`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000ab71`
- `ntoskrnl!ZwClose` at `0x14000abed`
- `ntoskrnl!ZwClose` at `0x14000ac9c`
- `ntoskrnl!ZwClose` at `0x14000abed`
- `ntoskrnl!ZwClose` at `0x14000ac9c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ac86`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ac86`
- `ntoskrnl!ExAllocatePool2` at `0x14000aabe`
- `ntoskrnl!ExAllocatePool2` at `0x14000aabe`

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
0x14000aa50  push    rbp
0x14000aa52  push    rbx
0x14000aa53  push    rsi
0x14000aa54  push    rdi
0x14000aa55  lea     rbp, [rsp-18h]
0x14000aa5a  sub     rsp, 118h
0x14000aa61  mov     rax, cs:__security_cookie
0x14000aa68  xor     rax, rsp
0x14000aa6b  mov     [rbp+30h+var_30], rax
0x14000aa6f  xorps   xmm0, xmm0
0x14000aa72  lea     rdx, aS1; "S-1-*"
0x14000aa79  mov     rsi, rcx
0x14000aa7c  xor     eax, eax
0x14000aa7e  xorps   xmm1, xmm1
0x14000aa81  mov     [rsp+130h+FileHandle], rax
0x14000aa86  movups  xmmword ptr [rbp+30h+ObjectAttributes.ObjectName], xmm0
0x14000aa8a  lea     rcx, [rsp+130h+DestinationString]; DestinationString
0x14000aa8f  movups  xmmword ptr [rbp+30h+ObjectAttributes+1Ch], xmm0
0x14000aa93  movups  xmmword ptr [rbp+30h+ObjectAttributes.Length], xmm0
0x14000aa97  movups  xmmword ptr [rbp+30h+var_80.Length], xmm0
0x14000aa9b  movups  xmmword ptr [rbp+30h+var_70], xmm0
0x14000aa9f  movups  xmmword ptr [rsp+130h+DestinationString.Length], xmm1
0x14000aaa4  call    cs:__imp_RtlInitUnicodeString
0x14000aaab  nop     dword ptr [rax+rax+00h]
0x14000aab0  mov     edx, 110h
0x14000aab5  mov     r8d, 4E736642h
0x14000aabb  lea     ecx, [rdx-10h]
0x14000aabe  call    cs:__imp_ExAllocatePool2
0x14000aac5  nop     dword ptr [rax+rax+00h]
0x14000aaca  mov     rdi, rax
0x14000aacd  test    rax, rax
0x14000aad0  jnz     short loc_14000AB15
0x14000aad2  mov     eax, cs:dword_140019000
0x14000aad8  mov     ebx, 0C0000017h
0x14000aadd  cmp     eax, 3
0x14000aae0  jbe     loc_14000AC92
0x14000aae6  lea     rax, [rsp+130h+var_D0]
0x14000aaeb  mov     [rsp+130h+var_D0], ebx
0x14000aaef  mov     [rbp+30h+var_40], rax
0x14000aaf3  lea     rdx, byte_140016D91; int
0x14000aafa  lea     rax, [rbp+30h+var_60]
0x14000aafe  mov     [rbp+30h+var_38], 4
0x14000ab06  mov     [rsp+130h+FileInformation], rax; PEVENT_DATA_DESCRIPTOR
0x14000ab0b  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000ab10  jmp     loc_14000AC92
0x14000ab15  mov     al, 1
0x14000ab17  mov     [rsp+130h+RestartScan], al; RestartScan
0x14000ab1b  xor     r9d, r9d; ApcContext
0x14000ab1e  lea     rax, [rsp+130h+DestinationString]
0x14000ab23  xor     r8d, r8d; ApcRoutine
0x14000ab26  mov     [rsp+130h+FileName], rax; FileName
0x14000ab2b  xor     edx, edx; Event
0x14000ab2d  mov     [rsp+130h+ReturnSingleEntry], 1; ReturnSingleEntry
0x14000ab32  lea     rax, [rbp+30h+var_70]
0x14000ab36  mov     [rsp+130h+FileInformationClass], 0Ch; FileInformationClass
0x14000ab3e  mov     rcx, rsi; FileHandle
0x14000ab41  mov     [rsp+130h+Length], 110h; Length
0x14000ab49  mov     [rsp+130h+FileInformation], rdi; FileInformation
0x14000ab4e  mov     [rsp+130h+IoStatusBlock], rax; IoStatusBlock
0x14000ab53  call    cs:__imp_ZwQueryDirectoryFile
0x14000ab5a  nop     dword ptr [rax+rax+00h]
0x14000ab5f  mov     ebx, eax
0x14000ab61  test    eax, eax
0x14000ab63  js      loc_14000AC02
0x14000ab69  lea     rdx, [rdi+0Ch]; SourceString
0x14000ab6d  lea     rcx, [rbp+30h+var_80]; DestinationString
0x14000ab71  call    cs:__imp_RtlInitUnicodeString
0x14000ab78  nop     dword ptr [rax+rax+00h]
0x14000ab7d  lea     rax, [rbp+30h+var_80]
0x14000ab81  mov     dword ptr [rsp+130h+FileInformation], 21h ; '!'; OpenOptions
0x14000ab89  xorps   xmm0, xmm0
0x14000ab8c  mov     [rbp+30h+ObjectAttributes.ObjectName], rax
0x14000ab90  lea     r9, [rbp+30h+var_70]; IoStatusBlock
0x14000ab94  mov     [rbp+30h+ObjectAttributes.Length], 30h ; '0'
0x14000ab9b  lea     r8, [rbp+30h+ObjectAttributes]; ObjectAttributes
0x14000ab9f  mov     [rbp+30h+ObjectAttributes.RootDirectory], rsi
0x14000aba3  mov     edx, 1F01FFh; DesiredAccess
0x14000aba8  mov     [rbp+30h+ObjectAttributes.Attributes], 200h
0x14000abaf  lea     rcx, [rsp+130h+FileHandle]; FileHandle
0x14000abb4  mov     dword ptr [rsp+130h+IoStatusBlock], 3; int
0x14000abbc  movdqu  xmmword ptr [rbp+30h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000abc1  call    cs:__imp_ZwOpenFile
0x14000abc8  nop     dword ptr [rax+rax+00h]
0x14000abcd  mov     ebx, eax
0x14000abcf  test    eax, eax
0x14000abd1  js      short loc_14000AC1D
0x14000abd3  mov     rcx, [rsp+130h+FileHandle]; Handle
0x14000abd8  lea     rdx, [rsp+130h+DestinationString]; FileName
0x14000abdd  call    BfsUpdateUserPolicyDirectorySecurity
0x14000abe2  mov     ebx, eax
0x14000abe4  test    eax, eax
0x14000abe6  js      short loc_14000AC1D
0x14000abe8  mov     rcx, [rsp+130h+FileHandle]; Handle
0x14000abed  call    cs:__imp_ZwClose
0x14000abf4  nop     dword ptr [rax+rax+00h]
0x14000abf9  mov     [rsp+130h+FileHandle], 0
0x14000ac02  xor     edx, edx; Val
0x14000ac04  mov     r8d, 110h; Size
0x14000ac0a  mov     rcx, rdi; void *
0x14000ac0d  call    memset
0x14000ac12  test    ebx, ebx
0x14000ac14  js      short loc_14000AC54
0x14000ac16  xor     al, al
0x14000ac18  jmp     loc_14000AB17
0x14000ac1d  mov     eax, cs:dword_140019000
0x14000ac23  cmp     eax, 3
0x14000ac26  jbe     short loc_14000AC81
0x14000ac28  lea     rax, [rsp+130h+var_D0]
0x14000ac2d  mov     [rsp+130h+var_D0], ebx
0x14000ac31  mov     [rbp+30h+var_40], rax
0x14000ac35  lea     rdx, byte_140016D91; int
0x14000ac3c  lea     rax, [rbp+30h+var_60]
0x14000ac40  mov     [rbp+30h+var_38], 4
0x14000ac48  mov     [rsp+130h+FileInformation], rax; PEVENT_DATA_DESCRIPTOR
0x14000ac4d  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000ac52  jmp     short loc_14000AC81
0x14000ac54  cmp     ebx, 0C000000Fh
0x14000ac5a  jz      short loc_14000AC64
0x14000ac5c  cmp     ebx, 80000006h
0x14000ac62  jnz     short loc_14000AC81
0x14000ac64  lea     r8, gBfsPolicyStorageDirectoryDescriptor; SecurityDescriptor
0x14000ac6b  mov     edx, 17h; SecurityInformation
0x14000ac70  mov     rcx, rsi; Handle
0x14000ac73  call    cs:__imp_ZwSetSecurityObject
0x14000ac7a  nop     dword ptr [rax+rax+00h]
0x14000ac7f  mov     ebx, eax
0x14000ac81  xor     edx, edx; Tag
0x14000ac83  mov     rcx, rdi; P
0x14000ac86  call    cs:__imp_ExFreePoolWithTag
0x14000ac8d  nop     dword ptr [rax+rax+00h]
0x14000ac92  mov     rcx, [rsp+130h+FileHandle]; Handle
0x14000ac97  test    rcx, rcx
0x14000ac9a  jz      short loc_14000ACA8
0x14000ac9c  call    cs:__imp_ZwClose
0x14000aca3  nop     dword ptr [rax+rax+00h]
0x14000aca8  mov     eax, ebx
0x14000acaa  mov     rcx, [rbp+30h+var_30]
0x14000acae  xor     rcx, rsp; StackCookie
0x14000acb1  call    __security_check_cookie
0x14000acb6  add     rsp, 118h
0x14000acbd  pop     rdi
0x14000acbe  pop     rsi
0x14000acbf  pop     rbx
0x14000acc0  pop     rbp
0x14000acc1  retn
```
