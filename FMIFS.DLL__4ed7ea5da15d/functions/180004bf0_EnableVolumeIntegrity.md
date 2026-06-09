# EnableVolumeIntegrity

- ea: `0x180004bf0`
- end: `0x180004c94`
- name: `EnableVolumeIntegrity`
- size: `164`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180004bf0`

## import_xrefs

- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180004c6e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180004c6e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180004c2a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180004c2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004c7c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004c7c`

## pseudocode

```c
bool __fastcall EnableVolumeIntegrity(const WCHAR *a1)
{
  bool v1; // bl
  HANDLE FileW; // rdi
  DWORD BytesReturned; // [rsp+50h] [rbp+8h] BYREF
  __int64 InBuffer; // [rsp+58h] [rbp+10h] BYREF

  InBuffer = 0;
  v1 = 0;
  if ( a1 )
  {
    if ( *a1 )
    {
      FileW = CreateFileW(a1, 3u, 3u, 0, 3u, 0x2000000u, 0);
      if ( FileW != (HANDLE)-1LL )
      {
        LOWORD(InBuffer) = 2;
        BytesReturned = 0;
        v1 = DeviceIoControl(FileW, 0x9C280u, &InBuffer, 8u, 0, 0, &BytesReturned, 0);
        CloseHandle(FileW);
      }
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180004bf0  mov     rax, rsp
0x180004bf3  mov     [rax+18h], rbx
0x180004bf7  mov     [rax+20h], rsi
0x180004bfb  push    rdi
0x180004bfc  sub     rsp, 40h
0x180004c00  xor     esi, esi
0x180004c02  mov     [rax+10h], rsi
0x180004c06  mov     bl, sil
0x180004c09  test    rcx, rcx
0x180004c0c  jz      short loc_180004C82
0x180004c0e  cmp     [rcx], si
0x180004c11  jz      short loc_180004C82
0x180004c13  lea     edx, [rsi+3]; dwDesiredAccess
0x180004c16  mov     [rax-18h], rsi
0x180004c1a  mov     dword ptr [rax-20h], 2000000h
0x180004c21  mov     r8d, edx; dwShareMode
0x180004c24  xor     r9d, r9d; lpSecurityAttributes
0x180004c27  mov     [rax-28h], edx
0x180004c2a  call    cs:__imp_CreateFileW
0x180004c30  mov     rdi, rax
0x180004c33  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180004c37  jz      short loc_180004C82
0x180004c39  mov     [rsp+48h+lpOverlapped], rsi; lpOverlapped
0x180004c3e  lea     eax, [rsi+2]
0x180004c41  mov     word ptr [rsp+48h+InBuffer], ax
0x180004c46  lea     r9d, [rsi+8]; nInBufferSize
0x180004c4a  lea     rax, [rsp+48h+BytesReturned]
0x180004c4f  mov     [rsp+48h+BytesReturned], esi
0x180004c53  mov     [rsp+48h+lpBytesReturned], rax; lpBytesReturned
0x180004c58  lea     r8, [rsp+48h+InBuffer]; lpInBuffer
0x180004c5d  mov     [rsp+48h+nOutBufferSize], esi; nOutBufferSize
0x180004c61  mov     edx, 9C280h; dwIoControlCode
0x180004c66  mov     rcx, rdi; hDevice
0x180004c69  mov     [rsp+48h+lpOutBuffer], rsi; lpOutBuffer
0x180004c6e  call    cs:__imp_DeviceIoControl
0x180004c74  test    eax, eax
0x180004c76  mov     rcx, rdi; hObject
0x180004c79  setnz   bl
0x180004c7c  call    cs:__imp_CloseHandle
0x180004c82  mov     rsi, [rsp+48h+arg_18]
0x180004c87  mov     al, bl
0x180004c89  mov     rbx, [rsp+48h+arg_10]
0x180004c8e  add     rsp, 40h
0x180004c92  pop     rdi
0x180004c93  retn
```
