# BfspIsVhdVolume

- ea: `0x140002f14`
- end: `0x1400030b8`
- name: `BfspIsVhdVolume`
- size: `420`
- prototype: `bool __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, loader_planting`

## callers

- `0x140006cd8`

## callees

- `0x140002f14`
- `0x140026650`

## import_xrefs

- `ntdll!NtOpenFile` at `0x140002fbb`
- `ntdll!NtOpenFile` at `0x140002fbb`
- `ntdll!NtWaitForSingleObject` at `0x140003056`
- `ntdll!NtWaitForSingleObject` at `0x140003056`
- `ntdll!NtCreateEvent` at `0x140002fe0`
- `ntdll!NtCreateEvent` at `0x140002fe0`
- `ntdll!NtClose` at `0x14000307a`
- `ntdll!NtClose` at `0x14000308a`
- `ntdll!NtClose` at `0x14000307a`
- `ntdll!NtClose` at `0x14000308a`
- `ntdll!NtDeviceIoControlFile` at `0x14000303d`
- `ntdll!NtDeviceIoControlFile` at `0x14000303d`
- `ntdll!RtlInitUnicodeString` at `0x140002f6a`
- `ntdll!RtlInitUnicodeString` at `0x140002f6a`

## pseudocode

```c
bool __fastcall BfspIsVhdVolume(PCWSTR SourceString)
{
  NTSTATUS Status; // ebx
  int InputBuffer; // [rsp+50h] [rbp-B0h] BYREF
  void *EventHandle; // [rsp+58h] [rbp-A8h] BYREF
  void *FileHandle; // [rsp+60h] [rbp-A0h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+68h] [rbp-98h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-88h] BYREF
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
0x140002f14  mov     [rsp-8+arg_8], rbx
0x140002f19  push    rbp
0x140002f1a  lea     rbp, [rsp-1E0h]
0x140002f22  sub     rsp, 2E0h
0x140002f29  mov     rax, cs:__security_cookie
0x140002f30  xor     rax, rsp
0x140002f33  mov     [rbp+1E0h+var_10], rax
0x140002f3a  xorps   xmm0, xmm0
0x140002f3d  xor     eax, eax
0x140002f3f  mov     rdx, rcx; SourceString
0x140002f42  mov     [rsp+2E0h+var_290], eax
0x140002f46  movups  xmmword ptr [rbp+1E0h+ObjectAttributes.ObjectName], xmm0
0x140002f4a  lea     rcx, [rbp+1E0h+DestinationString]; DestinationString
0x140002f4e  mov     [rsp+2E0h+FileHandle], rax
0x140002f53  movups  xmmword ptr [rbp+1E0h+ObjectAttributes+1Ch], xmm0
0x140002f57  mov     [rsp+2E0h+EventHandle], rax
0x140002f5c  movups  xmmword ptr [rsp+2E0h+ObjectAttributes.Length], xmm0
0x140002f61  movups  xmmword ptr [rsp+2E0h+IoStatusBlock], xmm0
0x140002f66  movups  xmmword ptr [rbp+1E0h+DestinationString.Length], xmm0
0x140002f6a  call    cs:__imp_RtlInitUnicodeString
0x140002f70  lea     rax, [rbp+1E0h+DestinationString]
0x140002f74  mov     [rsp+2E0h+OpenOptions], 0; OpenOptions
0x140002f7c  xorps   xmm0, xmm0
0x140002f7f  mov     [rbp+1E0h+ObjectAttributes.ObjectName], rax
0x140002f83  lea     r9, [rsp+2E0h+IoStatusBlock]; IoStatusBlock
0x140002f88  mov     [rsp+2E0h+ObjectAttributes.Length], 30h ; '0'
0x140002f90  lea     r8, [rsp+2E0h+ObjectAttributes]; ObjectAttributes
0x140002f95  mov     [rbp+1E0h+ObjectAttributes.RootDirectory], 0
0x140002f9d  mov     edx, 0C0000000h; DesiredAccess
0x140002fa2  mov     [rbp+1E0h+ObjectAttributes.Attributes], 40h ; '@'
0x140002fa9  lea     rcx, [rsp+2E0h+FileHandle]; FileHandle
0x140002fae  mov     [rsp+2E0h+ShareAccess], 3; ShareAccess
0x140002fb6  movdqu  xmmword ptr [rbp+1E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x140002fbb  call    cs:__imp_NtOpenFile
0x140002fc1  mov     ebx, eax
0x140002fc3  test    eax, eax
0x140002fc5  js      loc_140003070
0x140002fcb  xor     r9d, r9d; EventType
0x140002fce  mov     byte ptr [rsp+2E0h+ShareAccess], 0; InitialState
0x140002fd3  xor     r8d, r8d; ObjectAttributes
0x140002fd6  lea     rcx, [rsp+2E0h+EventHandle]; EventHandle
0x140002fdb  mov     edx, 1F0003h; DesiredAccess
0x140002fe0  call    cs:__imp_NtCreateEvent
0x140002fe6  mov     ebx, eax
0x140002fe8  test    eax, eax
0x140002fea  js      loc_140003070
0x140002ff0  mov     rdx, [rsp+2E0h+EventHandle]; Event
0x140002ff5  lea     rax, [rbp+1E0h+var_220]
0x140002ff9  mov     rcx, [rsp+2E0h+FileHandle]; FileHandle
0x140002ffe  xor     r9d, r9d; ApcContext
0x140003001  mov     [rsp+2E0h+OutputBufferLength], 208h; OutputBufferLength
0x140003009  xor     r8d, r8d; ApcRoutine
0x14000300c  mov     [rsp+2E0h+OutputBuffer], rax; OutputBuffer
0x140003011  lea     rax, [rsp+2E0h+var_290]
0x140003016  mov     [rsp+2E0h+InputBufferLength], 4; InputBufferLength
0x14000301e  mov     [rsp+2E0h+InputBuffer], rax; InputBuffer
0x140003023  lea     rax, [rsp+2E0h+IoStatusBlock]
0x140003028  mov     [rsp+2E0h+OpenOptions], 2D5928h; IoControlCode
0x140003030  mov     qword ptr [rsp+2E0h+ShareAccess], rax; IoStatusBlock
0x140003035  mov     [rsp+2E0h+var_290], 1
0x14000303d  call    cs:__imp_NtDeviceIoControlFile
0x140003043  mov     ebx, eax
0x140003045  cmp     eax, 103h
0x14000304a  jnz     short loc_140003065
0x14000304c  mov     rcx, [rsp+2E0h+EventHandle]; Handle
0x140003051  xor     r8d, r8d; Timeout
0x140003054  xor     edx, edx; Alertable
0x140003056  call    cs:__imp_NtWaitForSingleObject
0x14000305c  test    eax, eax
0x14000305e  mov     ebx, eax
0x140003060  cmovns  ebx, dword ptr [rsp+2E0h+IoStatusBlock]
0x140003065  xor     eax, eax
0x140003067  cmp     ebx, 0C0000023h
0x14000306d  cmovz   ebx, eax
0x140003070  mov     rcx, [rsp+2E0h+FileHandle]; Handle
0x140003075  test    rcx, rcx
0x140003078  jz      short loc_140003080
0x14000307a  call    cs:__imp_NtClose
0x140003080  mov     rcx, [rsp+2E0h+EventHandle]; Handle
0x140003085  test    rcx, rcx
0x140003088  jz      short loc_140003090
0x14000308a  call    cs:__imp_NtClose
0x140003090  shr     ebx, 1Fh
0x140003093  xor     bl, 1
0x140003096  mov     al, bl
0x140003098  mov     rcx, [rbp+1E0h+var_10]
0x14000309f  xor     rcx, rsp; StackCookie
0x1400030a2  call    __security_check_cookie
0x1400030a7  mov     rbx, [rsp+2E0h+arg_8]
0x1400030af  add     rsp, 2E0h
0x1400030b6  pop     rbp
0x1400030b7  retn
```
