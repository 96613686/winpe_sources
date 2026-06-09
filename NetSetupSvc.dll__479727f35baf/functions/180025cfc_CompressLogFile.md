# CompressLogFile

- ea: `0x180025cfc`
- end: `0x180025dab`
- name: `CompressLogFile`
- size: `175`
- prototype: `int __fastcall(const WCHAR *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180025ad4`

## callees

- `0x1800027c0`
- `0x180025cfc`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025d92`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025d92`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180025d31`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180025d31`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180025d89`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180025d89`

## pseudocode

```c
int __fastcall CompressLogFile(const WCHAR *a1)
{
  HANDLE FileW; // rax
  void *v2; // rbx
  __int16 InBuffer[2]; // [rsp+40h] [rbp-18h] BYREF
  DWORD BytesReturned; // [rsp+44h] [rbp-14h] BYREF

  FileW = CreateFileW(a1, 3u, 3u, 0, 3u, 0, 0);
  v2 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    BytesReturned = 0;
    InBuffer[0] = 1;
    DeviceIoControl(FileW, 0x9C040u, InBuffer, 2u, 0, 0, &BytesReturned, 0);
    LODWORD(FileW) = CloseHandle(v2);
  }
  return (int)FileW;
}

```

## disassembly

```asm
0x180025cfc  push    rbx
0x180025cfe  sub     rsp, 50h
0x180025d02  mov     rax, cs:__security_cookie
0x180025d09  xor     rax, rsp
0x180025d0c  mov     [rsp+58h+var_10], rax
0x180025d11  mov     edx, 3; dwDesiredAccess
0x180025d16  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x180025d1f  mov     r8d, edx; dwShareMode
0x180025d22  mov     [rsp+58h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180025d2a  xor     r9d, r9d; lpSecurityAttributes
0x180025d2d  mov     [rsp+58h+dwCreationDisposition], edx; dwCreationDisposition
0x180025d31  call    cs:__imp_CreateFileW
0x180025d37  mov     rbx, rax
0x180025d3a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180025d3e  jz      short loc_180025D98
0x180025d40  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x180025d49  lea     r8, [rsp+58h+InBuffer]; lpInBuffer
0x180025d4e  mov     eax, 1
0x180025d53  mov     [rsp+58h+BytesReturned], 0
0x180025d5b  mov     [rsp+58h+InBuffer], ax
0x180025d60  mov     r9d, 2; nInBufferSize
0x180025d66  lea     rax, [rsp+58h+BytesReturned]
0x180025d6b  mov     edx, 9C040h; dwIoControlCode
0x180025d70  mov     [rsp+58h+hTemplateFile], rax; lpBytesReturned
0x180025d75  mov     rcx, rbx; hDevice
0x180025d78  mov     [rsp+58h+dwFlagsAndAttributes], 0; nOutBufferSize
0x180025d80  mov     qword ptr [rsp+58h+dwCreationDisposition], 0; lpOutBuffer
0x180025d89  call    cs:__imp_DeviceIoControl
0x180025d8f  mov     rcx, rbx; hObject
0x180025d92  call    cs:__imp_CloseHandle
0x180025d98  mov     rcx, [rsp+58h+var_10]
0x180025d9d  xor     rcx, rsp; StackCookie
0x180025da0  call    __security_check_cookie
0x180025da5  add     rsp, 50h
0x180025da9  pop     rbx
0x180025daa  retn
```
