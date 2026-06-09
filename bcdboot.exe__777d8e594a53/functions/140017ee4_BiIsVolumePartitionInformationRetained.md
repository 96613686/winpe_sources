# BiIsVolumePartitionInformationRetained

- ea: `0x140017ee4`
- end: `0x140017ff0`
- name: `BiIsVolumePartitionInformationRetained`
- size: `268`
- prototype: `bool __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140015cd8`

## callees

- `0x140017ee4`

## import_xrefs

- `ntdll!ZwDeviceIoControlFile` at `0x140017fc0`
- `ntdll!ZwDeviceIoControlFile` at `0x140017fc0`
- `ntdll!ZwClose` at `0x140017fd7`
- `ntdll!ZwClose` at `0x140017fd7`
- `ntdll!RtlInitUnicodeString` at `0x140017f1d`
- `ntdll!RtlInitUnicodeString` at `0x140017f1d`
- `ntdll!ZwOpenFile` at `0x140017f6e`
- `ntdll!ZwOpenFile` at `0x140017f6e`

## pseudocode

```c
bool __fastcall BiIsVolumePartitionInformationRetained(PCWSTR SourceString)
{
  NTSTATUS v1; // ebx
  bool v2; // bl
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp+7h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp+17h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp+27h] BYREF
  void *FileHandle; // [rsp+B8h] [rbp+6Fh] BYREF

  FileHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  IoStatusBlock = 0;
  v1 = ZwOpenFile(&FileHandle, 0x80100000, &ObjectAttributes, &IoStatusBlock, 3u, 0x20u);
  if ( v1 >= 0 )
  {
    IoStatusBlock = 0;
    v1 = ZwDeviceIoControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x560028u, 0, 0, 0, 0);
  }
  v2 = v1 >= 0;
  if ( FileHandle )
    ZwClose(FileHandle);
  return v2;
}

```

## disassembly

```asm
0x140017ee4  mov     [rsp-8+arg_0], rbx
0x140017ee9  push    rbp
0x140017eea  lea     rbp, [rsp-57h]
0x140017eef  sub     rsp, 0A0h
0x140017ef6  xorps   xmm0, xmm0
0x140017ef9  xor     eax, eax
0x140017efb  xorps   xmm1, xmm1
0x140017efe  mov     [rbp+57h+FileHandle], rax
0x140017f02  mov     rdx, rcx; SourceString
0x140017f05  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140017f09  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140017f0d  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x140017f11  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140017f15  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140017f19  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x140017f1d  call    cs:__imp_RtlInitUnicodeString
0x140017f23  xorps   xmm0, xmm0
0x140017f26  mov     [rsp+0A0h+OpenOptions], 20h ; ' '; OpenOptions
0x140017f2e  lea     rax, [rbp+57h+DestinationString]
0x140017f32  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140017f39  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140017f3d  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140017f41  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140017f45  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140017f4d  mov     edx, 80100000h; DesiredAccess
0x140017f52  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x140017f59  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x140017f5d  mov     [rsp+0A0h+ShareAccess], 3; ShareAccess
0x140017f65  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140017f6a  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140017f6e  call    cs:__imp_ZwOpenFile
0x140017f74  mov     ebx, eax
0x140017f76  test    eax, eax
0x140017f78  js      short loc_140017FC8
0x140017f7a  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140017f7e  lea     rax, [rbp+57h+IoStatusBlock]
0x140017f82  mov     [rsp+0A0h+OutputBufferLength], 0; OutputBufferLength
0x140017f8a  xorps   xmm0, xmm0
0x140017f8d  mov     [rsp+0A0h+OutputBuffer], 0; OutputBuffer
0x140017f96  xor     r9d, r9d; ApcContext
0x140017f99  mov     [rsp+0A0h+InputBufferLength], 0; InputBufferLength
0x140017fa1  xor     r8d, r8d; ApcRoutine
0x140017fa4  mov     [rsp+0A0h+InputBuffer], 0; InputBuffer
0x140017fad  xor     edx, edx; Event
0x140017faf  mov     [rsp+0A0h+OpenOptions], 560028h; IoControlCode
0x140017fb7  mov     qword ptr [rsp+0A0h+ShareAccess], rax; IoStatusBlock
0x140017fbc  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140017fc0  call    cs:__imp_ZwDeviceIoControlFile
0x140017fc6  mov     ebx, eax
0x140017fc8  mov     rcx, [rbp+57h+FileHandle]; Handle
0x140017fcc  shr     ebx, 1Fh
0x140017fcf  xor     bl, 1
0x140017fd2  test    rcx, rcx
0x140017fd5  jz      short loc_140017FDD
0x140017fd7  call    cs:__imp_ZwClose
0x140017fdd  mov     al, bl
0x140017fdf  mov     rbx, [rsp+0A0h+arg_0]
0x140017fe7  add     rsp, 0A0h
0x140017fee  pop     rbp
0x140017fef  retn
```
