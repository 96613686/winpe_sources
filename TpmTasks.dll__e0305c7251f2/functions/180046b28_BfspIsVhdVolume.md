# BfspIsVhdVolume

- ea: `0x180046b28`
- end: `0x180046ccc`
- name: `BfspIsVhdVolume`
- size: `420`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, loader_planting`

## callers

- `0x18004f970`

## callees

- `0x1800078b0`
- `0x180046b28`

## import_xrefs

- `ntdll!NtOpenFile` at `0x180046bcf`
- `ntdll!NtOpenFile` at `0x180046bcf`
- `ntdll!NtWaitForSingleObject` at `0x180046c6a`
- `ntdll!NtWaitForSingleObject` at `0x180046c6a`
- `ntdll!NtCreateEvent` at `0x180046bf4`
- `ntdll!NtCreateEvent` at `0x180046bf4`
- `ntdll!NtClose` at `0x180046c8e`
- `ntdll!NtClose` at `0x180046c9e`
- `ntdll!NtClose` at `0x180046c8e`
- `ntdll!NtClose` at `0x180046c9e`
- `ntdll!NtDeviceIoControlFile` at `0x180046c51`
- `ntdll!NtDeviceIoControlFile` at `0x180046c51`
- `ntdll!RtlInitUnicodeString` at `0x180046b7e`
- `ntdll!RtlInitUnicodeString` at `0x180046b7e`

## pseudocode

```c
bool __fastcall BfspIsVhdVolume(PCWSTR SourceString)
{
  NTSTATUS Status; // ebx
  int InputBuffer; // [rsp+50h] [rbp-B0h] BYREF
  void *EventHandle; // [rsp+58h] [rbp-A8h] BYREF
  void *FileHandle; // [rsp+60h] [rbp-A0h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+68h] [rbp-98h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-88h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE OutputBuffer[528]; // [rsp+C0h] [rbp-40h] BYREF

  InputBuffer = 0;
  FileHandle = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  EventHandle = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  IoStatusBlock = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  Status = NtOpenFile(&FileHandle, 0xC0000000, &ObjectAttributes, &IoStatusBlock, 3u, 0);
  if ( Status >= 0 )
  {
    Status = NtCreateEvent(&EventHandle, 0x1F0003u, 0, NotificationEvent, 0);
    if ( Status >= 0 )
    {
      InputBuffer = 1;
      Status = NtDeviceIoControlFile(
                 FileHandle,
                 EventHandle,
                 0,
                 0,
                 &IoStatusBlock,
                 0x2D5928u,
                 &InputBuffer,
                 4u,
                 OutputBuffer,
                 0x208u);
      if ( Status == 259 )
      {
        Status = NtWaitForSingleObject(EventHandle, 0, 0);
        if ( Status >= 0 )
          Status = IoStatusBlock.Status;
      }
      if ( Status == -1073741789 )
        Status = 0;
    }
  }
  if ( FileHandle )
    NtClose(FileHandle);
  if ( EventHandle )
    NtClose(EventHandle);
  return Status >= 0;
}

```

## disassembly

```asm
0x180046b28  mov     [rsp-8+arg_8], rbx
0x180046b2d  push    rbp
0x180046b2e  lea     rbp, [rsp-1E0h]
0x180046b36  sub     rsp, 2E0h
0x180046b3d  mov     rax, cs:__security_cookie
0x180046b44  xor     rax, rsp
0x180046b47  mov     [rbp+1E0h+var_10], rax
0x180046b4e  xorps   xmm0, xmm0
0x180046b51  xor     eax, eax
0x180046b53  mov     rdx, rcx; SourceString
0x180046b56  mov     [rsp+2E0h+var_290], eax
0x180046b5a  movups  xmmword ptr [rbp+1E0h+ObjectAttributes.ObjectName], xmm0
0x180046b5e  lea     rcx, [rbp+1E0h+DestinationString]; DestinationString
0x180046b62  mov     [rsp+2E0h+FileHandle], rax
0x180046b67  movups  xmmword ptr [rbp+1E0h+ObjectAttributes+1Ch], xmm0
0x180046b6b  mov     [rsp+2E0h+EventHandle], rax
0x180046b70  movups  xmmword ptr [rsp+2E0h+ObjectAttributes.Length], xmm0
0x180046b75  movups  xmmword ptr [rsp+2E0h+IoStatusBlock], xmm0
0x180046b7a  movups  xmmword ptr [rbp+1E0h+DestinationString.Length], xmm0
0x180046b7e  call    cs:__imp_RtlInitUnicodeString
0x180046b84  lea     rax, [rbp+1E0h+DestinationString]
0x180046b88  mov     [rsp+2E0h+OpenOptions], 0; OpenOptions
0x180046b90  xorps   xmm0, xmm0
0x180046b93  mov     [rbp+1E0h+ObjectAttributes.ObjectName], rax
0x180046b97  lea     r9, [rsp+2E0h+IoStatusBlock]; IoStatusBlock
0x180046b9c  mov     [rsp+2E0h+ObjectAttributes.Length], 30h ; '0'
0x180046ba4  lea     r8, [rsp+2E0h+ObjectAttributes]; ObjectAttributes
0x180046ba9  mov     [rbp+1E0h+ObjectAttributes.RootDirectory], 0
0x180046bb1  mov     edx, 0C0000000h; DesiredAccess
0x180046bb6  mov     [rbp+1E0h+ObjectAttributes.Attributes], 40h ; '@'
0x180046bbd  lea     rcx, [rsp+2E0h+FileHandle]; FileHandle
0x180046bc2  mov     [rsp+2E0h+ShareAccess], 3; ShareAccess
0x180046bca  movdqu  xmmword ptr [rbp+1E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180046bcf  call    cs:__imp_NtOpenFile
0x180046bd5  mov     ebx, eax
0x180046bd7  test    eax, eax
0x180046bd9  js      loc_180046C84
0x180046bdf  xor     r9d, r9d; EventType
0x180046be2  mov     byte ptr [rsp+2E0h+ShareAccess], 0; InitialState
0x180046be7  xor     r8d, r8d; ObjectAttributes
0x180046bea  lea     rcx, [rsp+2E0h+EventHandle]; EventHandle
0x180046bef  mov     edx, 1F0003h; DesiredAccess
0x180046bf4  call    cs:__imp_NtCreateEvent
0x180046bfa  mov     ebx, eax
0x180046bfc  test    eax, eax
0x180046bfe  js      loc_180046C84
0x180046c04  mov     rdx, [rsp+2E0h+EventHandle]; Event
0x180046c09  lea     rax, [rbp+1E0h+var_220]
0x180046c0d  mov     rcx, [rsp+2E0h+FileHandle]; FileHandle
0x180046c12  xor     r9d, r9d; ApcContext
0x180046c15  mov     [rsp+2E0h+OutputBufferLength], 208h; OutputBufferLength
0x180046c1d  xor     r8d, r8d; ApcRoutine
0x180046c20  mov     [rsp+2E0h+OutputBuffer], rax; OutputBuffer
0x180046c25  lea     rax, [rsp+2E0h+var_290]
0x180046c2a  mov     [rsp+2E0h+InputBufferLength], 4; InputBufferLength
0x180046c32  mov     [rsp+2E0h+InputBuffer], rax; InputBuffer
0x180046c37  lea     rax, [rsp+2E0h+IoStatusBlock]
0x180046c3c  mov     [rsp+2E0h+OpenOptions], 2D5928h; IoControlCode
0x180046c44  mov     qword ptr [rsp+2E0h+ShareAccess], rax; IoStatusBlock
0x180046c49  mov     [rsp+2E0h+var_290], 1
0x180046c51  call    cs:__imp_NtDeviceIoControlFile
0x180046c57  mov     ebx, eax
0x180046c59  cmp     eax, 103h
0x180046c5e  jnz     short loc_180046C79
0x180046c60  mov     rcx, [rsp+2E0h+EventHandle]; Handle
0x180046c65  xor     r8d, r8d; Timeout
0x180046c68  xor     edx, edx; Alertable
0x180046c6a  call    cs:__imp_NtWaitForSingleObject
0x180046c70  test    eax, eax
0x180046c72  mov     ebx, eax
0x180046c74  cmovns  ebx, dword ptr [rsp+2E0h+IoStatusBlock]
0x180046c79  xor     eax, eax
0x180046c7b  cmp     ebx, 0C0000023h
0x180046c81  cmovz   ebx, eax
0x180046c84  mov     rcx, [rsp+2E0h+FileHandle]; Handle
0x180046c89  test    rcx, rcx
0x180046c8c  jz      short loc_180046C94
0x180046c8e  call    cs:__imp_NtClose
0x180046c94  mov     rcx, [rsp+2E0h+EventHandle]; Handle
0x180046c99  test    rcx, rcx
0x180046c9c  jz      short loc_180046CA4
0x180046c9e  call    cs:__imp_NtClose
0x180046ca4  shr     ebx, 1Fh
0x180046ca7  xor     bl, 1
0x180046caa  mov     al, bl
0x180046cac  mov     rcx, [rbp+1E0h+var_10]
0x180046cb3  xor     rcx, rsp; StackCookie
0x180046cb6  call    __security_check_cookie
0x180046cbb  mov     rbx, [rsp+2E0h+arg_8]
0x180046cc3  add     rsp, 2E0h
0x180046cca  pop     rbp
0x180046ccb  retn
```
