# BfsUpdateUserPolicyDirectorySecurity

- ea: `0x14000accc`
- end: `0x14000af3a`
- name: `BfsUpdateUserPolicyDirectorySecurity`
- size: `622`
- prototype: `__int64 __fastcall(HANDLE Handle, PUNICODE_STRING FileName)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14000aa50`

## callees

- `0x140001008`
- `0x14000accc`
- `0x140013730`
- `0x140013b40`

## import_xrefs

- `ntoskrnl!ZwQueryDirectoryFile` at `0x14000adb7`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x14000adb7`
- `ntoskrnl!ZwSetSecurityObject` at `0x14000ae46`
- `ntoskrnl!ZwSetSecurityObject` at `0x14000aedf`
- `ntoskrnl!ZwSetSecurityObject` at `0x14000ae46`
- `ntoskrnl!ZwSetSecurityObject` at `0x14000aedf`
- `ntoskrnl!ZwOpenFile` at `0x14000ae24`
- `ntoskrnl!ZwOpenFile` at `0x14000ae24`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000add5`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000add5`
- `ntoskrnl!ZwClose` at `0x14000ae5c`
- `ntoskrnl!ZwClose` at `0x14000af07`
- `ntoskrnl!ZwClose` at `0x14000ae5c`
- `ntoskrnl!ZwClose` at `0x14000af07`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000aef2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000aef2`
- `ntoskrnl!ExAllocatePool2` at `0x14000ad29`
- `ntoskrnl!ExAllocatePool2` at `0x14000ad29`

## pseudocode

```c
__int64 __fastcall BfsUpdateUserPolicyDirectorySecurity(HANDLE Handle, PUNICODE_STRING FileName)
{
  int v4; // ecx
  WCHAR *FileInformation; // rdi
  int v6; // r8d
  int v7; // r9d
  NTSTATUS v8; // ebx
  BOOLEAN RestartScan; // al
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  int IoStatusBlock; // [rsp+20h] [rbp-99h]
  int IoStatusBlocka; // [rsp+20h] [rbp-99h]
  int v16; // [rsp+60h] [rbp-59h] BYREF
  void *FileHandle; // [rsp+68h] [rbp-51h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-49h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-19h] BYREF
  struct _IO_STATUS_BLOCK v20; // [rsp+B0h] [rbp-9h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v21; // [rsp+C0h] [rbp+7h] BYREF
  int *v22; // [rsp+E0h] [rbp+27h]
  __int64 v23; // [rsp+E8h] [rbp+2Fh]

  FileHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  v20 = 0;
  FileInformation = (WCHAR *)ExAllocatePool2(256, 272, 1316185666);
  if ( !FileInformation )
  {
    v8 = -1073741801;
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v16 = -1073741801;
      v22 = &v16;
      v23 = 4;
      tlgWriteTransfer_EtwWriteTransfer(v4, (int)&byte_140016D91, v6, v7, IoStatusBlock, &v21);
    }
    goto LABEL_17;
  }
  for ( RestartScan = 1; ; RestartScan = 0 )
  {
    v8 = ZwQueryDirectoryFile(
           Handle,
           0,
           0,
           0,
           &v20,
           FileInformation,
           0x110u,
           FileNamesInformation,
           1u,
           FileName,
           RestartScan);
    if ( v8 < 0 )
      goto LABEL_9;
    RtlInitUnicodeString(&DestinationString, FileInformation + 6);
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = Handle;
    ObjectAttributes.Attributes = 512;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v8 = ZwOpenFile(&FileHandle, 0x1F01FFu, &ObjectAttributes, &v20, 3u, 0x60u);
    if ( v8 < 0 )
      break;
    v8 = ZwSetSecurityObject(FileHandle, 0x17u, gBfsPolicyStorageFileDescriptor);
    if ( v8 < 0 )
      break;
    ZwClose(FileHandle);
    FileHandle = 0;
LABEL_9:
    memset(FileInformation, 0, 0x110u);
    if ( v8 < 0 )
    {
      if ( v8 == -1073741809 || v8 == -2147483642 )
        v8 = ZwSetSecurityObject(Handle, 0x17u, gBfsPolicyStorageDirectoryDescriptor);
      goto LABEL_16;
    }
  }
  if ( (unsigned int)dword_140019000 > 3 )
  {
    v16 = v8;
    v22 = &v16;
    v23 = 4;
    tlgWriteTransfer_EtwWriteTransfer(v10, (int)&byte_140016D91, v11, v12, IoStatusBlocka, &v21);
  }
LABEL_16:
  ExFreePoolWithTag(FileInformation, 0);
LABEL_17:
  if ( FileHandle )
    ZwClose(FileHandle);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14000accc  mov     [rsp-8+arg_10], rbx
0x14000acd1  mov     [rsp-8+arg_18], rsi
0x14000acd6  push    rbp
0x14000acd7  push    rdi
0x14000acd8  push    r14
0x14000acda  lea     rbp, [rsp-47h]
0x14000acdf  sub     rsp, 100h
0x14000ace6  mov     rax, cs:__security_cookie
0x14000aced  xor     rax, rsp
0x14000acf0  mov     [rbp+57h+var_20], rax
0x14000acf4  xorps   xmm0, xmm0
0x14000acf7  mov     [rbp+57h+FileHandle], 0
0x14000acff  mov     r14, rdx
0x14000ad02  mov     rsi, rcx
0x14000ad05  mov     edx, 110h
0x14000ad0a  xor     eax, eax
0x14000ad0c  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14000ad10  mov     r8d, 4E736642h
0x14000ad16  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14000ad1a  lea     ecx, [rdx-10h]
0x14000ad1d  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14000ad21  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x14000ad25  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x14000ad29  call    cs:__imp_ExAllocatePool2
0x14000ad30  nop     dword ptr [rax+rax+00h]
0x14000ad35  mov     rdi, rax
0x14000ad38  test    rax, rax
0x14000ad3b  jnz     short loc_14000AD7E
0x14000ad3d  mov     eax, cs:dword_140019000
0x14000ad43  mov     ebx, 0C0000017h
0x14000ad48  cmp     eax, 3
0x14000ad4b  jbe     loc_14000AEFE
0x14000ad51  lea     rax, [rbp+57h+var_B0]
0x14000ad55  mov     [rbp+57h+var_B0], ebx
0x14000ad58  mov     [rbp+57h+var_30], rax
0x14000ad5c  lea     rdx, byte_140016D91; int
0x14000ad63  lea     rax, [rbp+57h+var_50]
0x14000ad67  mov     [rbp+57h+var_28], 4
0x14000ad6f  mov     [rsp+110h+FileInformation], rax; PEVENT_DATA_DESCRIPTOR
0x14000ad74  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000ad79  jmp     loc_14000AEFE
0x14000ad7e  mov     al, 1
0x14000ad80  mov     [rsp+110h+RestartScan], al; RestartScan
0x14000ad84  xor     r9d, r9d; ApcContext
0x14000ad87  mov     [rsp+110h+FileName], r14; FileName
0x14000ad8c  lea     rax, [rbp+57h+var_60]
0x14000ad90  mov     [rsp+110h+ReturnSingleEntry], 1; ReturnSingleEntry
0x14000ad95  xor     r8d, r8d; ApcRoutine
0x14000ad98  mov     [rsp+110h+FileInformationClass], 0Ch; FileInformationClass
0x14000ada0  xor     edx, edx; Event
0x14000ada2  mov     [rsp+110h+Length], 110h; Length
0x14000adaa  mov     rcx, rsi; FileHandle
0x14000adad  mov     [rsp+110h+FileInformation], rdi; FileInformation
0x14000adb2  mov     [rsp+110h+IoStatusBlock], rax; IoStatusBlock
0x14000adb7  call    cs:__imp_ZwQueryDirectoryFile
0x14000adbe  nop     dword ptr [rax+rax+00h]
0x14000adc3  mov     ebx, eax
0x14000adc5  test    eax, eax
0x14000adc7  js      loc_14000AE70
0x14000adcd  lea     rdx, [rdi+0Ch]; SourceString
0x14000add1  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14000add5  call    cs:__imp_RtlInitUnicodeString
0x14000addc  nop     dword ptr [rax+rax+00h]
0x14000ade1  lea     rax, [rbp+57h+DestinationString]
0x14000ade5  mov     dword ptr [rsp+110h+FileInformation], 60h ; '`'; OpenOptions
0x14000aded  xorps   xmm0, xmm0
0x14000adf0  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14000adf4  lea     r9, [rbp+57h+var_60]; IoStatusBlock
0x14000adf8  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14000adff  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14000ae03  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x14000ae07  mov     edx, 1F01FFh; DesiredAccess
0x14000ae0c  mov     [rbp+57h+ObjectAttributes.Attributes], 200h
0x14000ae13  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x14000ae17  mov     dword ptr [rsp+110h+IoStatusBlock], 3; int
0x14000ae1f  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000ae24  call    cs:__imp_ZwOpenFile
0x14000ae2b  nop     dword ptr [rax+rax+00h]
0x14000ae30  mov     ebx, eax
0x14000ae32  test    eax, eax
0x14000ae34  js      short loc_14000AE8B
0x14000ae36  mov     rcx, [rbp+57h+FileHandle]; Handle
0x14000ae3a  lea     r8, gBfsPolicyStorageFileDescriptor; SecurityDescriptor
0x14000ae41  mov     edx, 17h; SecurityInformation
0x14000ae46  call    cs:__imp_ZwSetSecurityObject
0x14000ae4d  nop     dword ptr [rax+rax+00h]
0x14000ae52  mov     ebx, eax
0x14000ae54  test    eax, eax
0x14000ae56  js      short loc_14000AE8B
0x14000ae58  mov     rcx, [rbp+57h+FileHandle]; Handle
0x14000ae5c  call    cs:__imp_ZwClose
0x14000ae63  nop     dword ptr [rax+rax+00h]
0x14000ae68  mov     [rbp+57h+FileHandle], 0
0x14000ae70  xor     edx, edx; Val
0x14000ae72  mov     r8d, 110h; Size
0x14000ae78  mov     rcx, rdi; void *
0x14000ae7b  call    memset
0x14000ae80  test    ebx, ebx
0x14000ae82  js      short loc_14000AEC0
0x14000ae84  xor     al, al
0x14000ae86  jmp     loc_14000AD80
0x14000ae8b  mov     eax, cs:dword_140019000
0x14000ae91  cmp     eax, 3
0x14000ae94  jbe     short loc_14000AEED
0x14000ae96  lea     rax, [rbp+57h+var_B0]
0x14000ae9a  mov     [rbp+57h+var_B0], ebx
0x14000ae9d  mov     [rbp+57h+var_30], rax
0x14000aea1  lea     rdx, byte_140016D91; int
0x14000aea8  lea     rax, [rbp+57h+var_50]
0x14000aeac  mov     [rbp+57h+var_28], 4
0x14000aeb4  mov     [rsp+110h+FileInformation], rax; PEVENT_DATA_DESCRIPTOR
0x14000aeb9  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000aebe  jmp     short loc_14000AEED
0x14000aec0  cmp     ebx, 0C000000Fh
0x14000aec6  jz      short loc_14000AED0
0x14000aec8  cmp     ebx, 80000006h
0x14000aece  jnz     short loc_14000AEED
0x14000aed0  lea     r8, gBfsPolicyStorageDirectoryDescriptor; SecurityDescriptor
0x14000aed7  mov     edx, 17h; SecurityInformation
0x14000aedc  mov     rcx, rsi; Handle
0x14000aedf  call    cs:__imp_ZwSetSecurityObject
0x14000aee6  nop     dword ptr [rax+rax+00h]
0x14000aeeb  mov     ebx, eax
0x14000aeed  xor     edx, edx; Tag
0x14000aeef  mov     rcx, rdi; P
0x14000aef2  call    cs:__imp_ExFreePoolWithTag
0x14000aef9  nop     dword ptr [rax+rax+00h]
0x14000aefe  mov     rcx, [rbp+57h+FileHandle]; Handle
0x14000af02  test    rcx, rcx
0x14000af05  jz      short loc_14000AF13
0x14000af07  call    cs:__imp_ZwClose
0x14000af0e  nop     dword ptr [rax+rax+00h]
0x14000af13  mov     eax, ebx
0x14000af15  mov     rcx, [rbp+57h+var_20]
0x14000af19  xor     rcx, rsp; StackCookie
0x14000af1c  call    __security_check_cookie
0x14000af21  lea     r11, [rsp+110h+var_10]
0x14000af29  mov     rbx, [r11+30h]
0x14000af2d  mov     rsi, [r11+38h]
0x14000af31  mov     rsp, r11
0x14000af34  pop     r14
0x14000af36  pop     rdi
0x14000af37  pop     rbp
0x14000af38  retn
```
