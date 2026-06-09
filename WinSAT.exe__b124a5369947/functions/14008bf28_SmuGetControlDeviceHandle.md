# SmuGetControlDeviceHandle

- ea: `0x14008bf28`
- end: `0x14008bfe8`
- name: `SmuGetControlDeviceHandle`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140012984`

## callees

- `0x14008bf28`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x14008bf65`
- `ntdll!RtlInitUnicodeString` at `0x14008bf65`
- `ntdll!NtOpenFile` at `0x14008bfb2`
- `ntdll!NtOpenFile` at `0x14008bfb2`
- `ntdll!RtlNtStatusToDosError` at `0x14008bfc0`
- `ntdll!RtlNtStatusToDosError` at `0x14008bfc0`

## pseudocode

```c
__int64 SmuGetControlDeviceHandle()
{
  int v0; // eax
  unsigned int v1; // ebx
  _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-50h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  void *FileHandle; // [rsp+90h] [rbp+10h] BYREF

  FileHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\RdyBoost");
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v0 = NtOpenFile(&FileHandle, 0x12019Fu, &ObjectAttributes, &IoStatusBlock, 7u, 0x20u);
  v1 = v0;
  if ( v0 >= 0 )
  {
    v1 = 0;
    s_EMDControlHandle = FileHandle;
  }
  else
  {
    RtlNtStatusToDosError(v0);
  }
  return v1;
}

```

## disassembly

```asm
0x14008bf28  mov     [rsp-8+arg_8], rbx
0x14008bf2d  mov     [rsp-8+FileHandle], rcx
0x14008bf32  push    rbp
0x14008bf33  mov     rbp, rsp
0x14008bf36  sub     rsp, 80h
0x14008bf3d  xorps   xmm0, xmm0
0x14008bf40  lea     rdx, SourceString; "\\Device\\RdyBoost"
0x14008bf47  xor     eax, eax
0x14008bf49  lea     rcx, [rbp+DestinationString]; DestinationString
0x14008bf4d  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14008bf51  mov     [rbp+FileHandle], rax
0x14008bf55  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14008bf59  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14008bf5d  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14008bf61  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x14008bf65  call    cs:__imp_RtlInitUnicodeString
0x14008bf6b  lea     rax, [rbp+DestinationString]
0x14008bf6f  mov     [rsp+80h+OpenOptions], 20h ; ' '; OpenOptions
0x14008bf77  xorps   xmm0, xmm0
0x14008bf7a  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14008bf7e  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x14008bf82  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14008bf89  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14008bf8d  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14008bf95  mov     edx, 12019Fh; DesiredAccess
0x14008bf9a  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x14008bfa1  lea     rcx, [rbp+FileHandle]; FileHandle
0x14008bfa5  mov     [rsp+80h+ShareAccess], 7; ShareAccess
0x14008bfad  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14008bfb2  call    cs:__imp_NtOpenFile
0x14008bfb8  mov     ebx, eax
0x14008bfba  test    eax, eax
0x14008bfbc  jns     short loc_14008BFC8
0x14008bfbe  mov     ecx, eax; Status
0x14008bfc0  call    cs:__imp_RtlNtStatusToDosError
0x14008bfc6  jmp     short loc_14008BFD5
0x14008bfc8  mov     rax, [rbp+FileHandle]
0x14008bfcc  xor     ebx, ebx
0x14008bfce  mov     cs:?s_EMDControlHandle@@3PEAXEA, rax; void * s_EMDControlHandle
0x14008bfd5  mov     eax, ebx
0x14008bfd7  mov     rbx, [rsp+80h+arg_8]
0x14008bfdf  add     rsp, 80h
0x14008bfe6  pop     rbp
0x14008bfe7  retn
```
