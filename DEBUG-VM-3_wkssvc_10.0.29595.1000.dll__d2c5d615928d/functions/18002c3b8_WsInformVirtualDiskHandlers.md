# WsInformVirtualDiskHandlers

- ea: `0x18002c3b8`
- end: `0x18002c4c8`
- name: `WsInformVirtualDiskHandlers`
- size: `272`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x18002c59c`

## callees

- `0x18002c3b8`

## import_xrefs

- `ntdll!DbgPrint` at `0x18002c4a5`
- `ntdll!DbgPrint` at `0x18002c4a5`
- `ntdll!NtDeviceIoControlFile` at `0x18002c47b`
- `ntdll!NtDeviceIoControlFile` at `0x18002c47b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002c48e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002c48e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002c3dd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002c3dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c4ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c4b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c4ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c4b7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002c41a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002c41a`

## pseudocode

```c
int WsInformVirtualDiskHandlers()
{
  HANDLE EventW; // rax
  void *v1; // rbx
  HANDLE FileW; // rax
  void *v3; // rdi
  NTSTATUS Status; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-18h] BYREF
  __int64 InputBuffer; // [rsp+70h] [rbp+8h] BYREF

  InputBuffer = 0;
  IoStatusBlock = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  v1 = EventW;
  if ( EventW )
  {
    FileW = CreateFileW(L"\\\\.\\VDRVROOT", 0xC0000000, 3u, 0, 3u, 0x40000000u, 0);
    v3 = FileW;
    if ( FileW != (HANDLE)-1LL )
    {
      InputBuffer = 0x100000001LL;
      Status = NtDeviceIoControlFile(FileW, v1, 0, 0, &IoStatusBlock, 0x2D9938u, &InputBuffer, 8u, 0, 0);
      if ( Status == 259 )
      {
        WaitForSingleObject(v1, 0xFFFFFFFF);
        Status = IoStatusBlock.Status;
      }
      if ( Status < 0 )
        DbgPrint("WKSSVC IOCTL to vdrvroot returned 0x%lx\n", Status);
      CloseHandle(v3);
    }
    LODWORD(EventW) = CloseHandle(v1);
  }
  return (int)EventW;
}

```

## disassembly

```asm
0x18002c3b8  mov     [rsp+arg_8], rbx
0x18002c3bd  push    rdi
0x18002c3be  sub     rsp, 60h
0x18002c3c2  xorps   xmm0, xmm0
0x18002c3c5  mov     [rsp+68h+InputBuffer], 0
0x18002c3ce  xor     r9d, r9d; lpName
0x18002c3d1  xor     r8d, r8d; bInitialState
0x18002c3d4  xor     edx, edx; bManualReset
0x18002c3d6  xor     ecx, ecx; lpEventAttributes
0x18002c3d8  movups  xmmword ptr [rsp+68h+IoStatusBlock], xmm0
0x18002c3dd  call    cs:__imp_CreateEventW
0x18002c3e3  mov     rbx, rax
0x18002c3e6  test    rax, rax
0x18002c3e9  jz      loc_18002C4BD
0x18002c3ef  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18002c3f8  lea     rcx, FileName; "\\\\.\\VDRVROOT"
0x18002c3ff  mov     r8d, 3; dwShareMode
0x18002c405  mov     [rsp+68h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x18002c40d  xor     r9d, r9d; lpSecurityAttributes
0x18002c410  mov     [rsp+68h+dwCreationDisposition], r8d; dwCreationDisposition
0x18002c415  mov     edx, 0C0000000h; dwDesiredAccess
0x18002c41a  call    cs:__imp_CreateFileW
0x18002c420  mov     rdi, rax
0x18002c423  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002c427  jz      loc_18002C4B4
0x18002c42d  mov     [rsp+68h+OutputBufferLength], 0; OutputBufferLength
0x18002c435  mov     eax, 1
0x18002c43a  mov     [rsp+68h+OutputBuffer], 0; OutputBuffer
0x18002c443  xor     r9d, r9d; ApcContext
0x18002c446  mov     dword ptr [rsp+68h+InputBuffer], eax
0x18002c44a  xor     r8d, r8d; ApcRoutine
0x18002c44d  mov     dword ptr [rsp+68h+InputBuffer+4], eax
0x18002c451  mov     rdx, rbx; Event
0x18002c454  mov     [rsp+68h+InputBufferLength], 8; InputBufferLength
0x18002c45c  lea     rax, [rsp+68h+InputBuffer]
0x18002c461  mov     [rsp+68h+hTemplateFile], rax; InputBuffer
0x18002c466  mov     rcx, rdi; FileHandle
0x18002c469  lea     rax, [rsp+68h+IoStatusBlock]
0x18002c46e  mov     [rsp+68h+dwFlagsAndAttributes], 2D9938h; IoControlCode
0x18002c476  mov     qword ptr [rsp+68h+dwCreationDisposition], rax; IoStatusBlock
0x18002c47b  call    cs:__imp_NtDeviceIoControlFile
0x18002c481  cmp     eax, 103h
0x18002c486  jnz     short loc_18002C498
0x18002c488  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002c48b  mov     rcx, rbx; hHandle
0x18002c48e  call    cs:__imp_WaitForSingleObject
0x18002c494  mov     eax, dword ptr [rsp+68h+IoStatusBlock]
0x18002c498  test    eax, eax
0x18002c49a  jns     short loc_18002C4AB
0x18002c49c  mov     edx, eax
0x18002c49e  lea     rcx, aWkssvcIoctlToV; "WKSSVC IOCTL to vdrvroot returned 0x%lx"...
0x18002c4a5  call    cs:__imp_DbgPrint
0x18002c4ab  mov     rcx, rdi; hObject
0x18002c4ae  call    cs:__imp_CloseHandle
0x18002c4b4  mov     rcx, rbx; hObject
0x18002c4b7  call    cs:__imp_CloseHandle
0x18002c4bd  mov     rbx, [rsp+68h+arg_8]
0x18002c4c2  add     rsp, 60h
0x18002c4c6  pop     rdi
0x18002c4c7  retn
```
