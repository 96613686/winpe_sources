# BiGetDriveLayoutInformation

- ea: `0x1400170dc`
- end: `0x1400171ac`
- name: `BiGetDriveLayoutInformation`
- size: `208`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140016784`
- `0x140016fe4`

## callees

- `0x1400170dc`
- `0x140017ff8`

## import_xrefs

- `ntdll!ZwClose` at `0x14001718f`
- `ntdll!ZwClose` at `0x14001718f`
- `ntdll!RtlInitUnicodeString` at `0x14001711b`
- `ntdll!RtlInitUnicodeString` at `0x14001711b`
- `ntdll!ZwOpenFile` at `0x14001716c`
- `ntdll!ZwOpenFile` at `0x14001716c`

## pseudocode

```c
__int64 __fastcall BiGetDriveLayoutInformation(PCWSTR SourceString)
{
  NTSTATUS DriveLayoutIoctl; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-50h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  void *FileHandle; // [rsp+A0h] [rbp+20h] BYREF

  FileHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  IoStatusBlock = 0;
  DriveLayoutIoctl = ZwOpenFile(&FileHandle, 0x80100000, &ObjectAttributes, &IoStatusBlock, 3u, 0x20u);
  if ( DriveLayoutIoctl >= 0 )
    DriveLayoutIoctl = BiIssueGetDriveLayoutIoctl(FileHandle);
  if ( FileHandle )
    ZwClose(FileHandle);
  return (unsigned int)DriveLayoutIoctl;
}

```

## disassembly

```asm
0x1400170dc  mov     [rsp-8+arg_0], rbx
0x1400170e1  mov     [rsp-8+arg_8], rdi
0x1400170e6  push    rbp
0x1400170e7  mov     rbp, rsp
0x1400170ea  sub     rsp, 80h
0x1400170f1  xorps   xmm0, xmm0
0x1400170f4  mov     rdi, rdx
0x1400170f7  mov     rdx, rcx; SourceString
0x1400170fa  xor     eax, eax
0x1400170fc  xorps   xmm1, xmm1
0x1400170ff  mov     [rbp+FileHandle], rax
0x140017103  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140017107  lea     rcx, [rbp+DestinationString]; DestinationString
0x14001710b  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14001710f  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140017113  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x140017117  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x14001711b  call    cs:__imp_RtlInitUnicodeString
0x140017121  xorps   xmm0, xmm0
0x140017124  mov     [rsp+80h+OpenOptions], 20h ; ' '; OpenOptions
0x14001712c  lea     rax, [rbp+DestinationString]
0x140017130  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140017137  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x14001713b  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14001713f  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140017143  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14001714b  mov     edx, 80100000h; DesiredAccess
0x140017150  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x140017157  lea     rcx, [rbp+FileHandle]; FileHandle
0x14001715b  mov     [rsp+80h+ShareAccess], 3; ShareAccess
0x140017163  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140017168  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x14001716c  call    cs:__imp_ZwOpenFile
0x140017172  mov     ebx, eax
0x140017174  test    eax, eax
0x140017176  js      short loc_140017186
0x140017178  mov     rcx, [rbp+FileHandle]; FileHandle
0x14001717c  mov     rdx, rdi
0x14001717f  call    BiIssueGetDriveLayoutIoctl
0x140017184  mov     ebx, eax
0x140017186  mov     rcx, [rbp+FileHandle]; Handle
0x14001718a  test    rcx, rcx
0x14001718d  jz      short loc_140017195
0x14001718f  call    cs:__imp_ZwClose
0x140017195  lea     r11, [rsp+80h+var_s0]
0x14001719d  mov     eax, ebx
0x14001719f  mov     rbx, [r11+10h]
0x1400171a3  mov     rdi, [r11+18h]
0x1400171a7  mov     rsp, r11
0x1400171aa  pop     rbp
0x1400171ab  retn
```
