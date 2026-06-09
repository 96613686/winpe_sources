# EnableVolumeCompression

- ea: `0x180004b50`
- end: `0x180004be7`
- name: `EnableVolumeCompression`
- size: `151`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180004b50`

## import_xrefs

- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180004bc1`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180004bc1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180004b85`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180004b85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004bcf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004bcf`

## pseudocode

```c
bool __fastcall EnableVolumeCompression(const WCHAR *a1, __int16 a2)
{
  bool v2; // bl
  HANDLE FileW; // rdi
  DWORD BytesReturned; // [rsp+50h] [rbp+8h] BYREF
  __int16 InBuffer; // [rsp+58h] [rbp+10h] BYREF

  InBuffer = a2;
  v2 = 0;
  if ( *a1 )
  {
    FileW = CreateFileW(a1, 3u, 3u, 0, 3u, 0x2000000u, 0);
    if ( FileW != (HANDLE)-1LL )
    {
      BytesReturned = 0;
      v2 = DeviceIoControl(FileW, 0x9C040u, &InBuffer, 2u, 0, 0, &BytesReturned, 0);
      CloseHandle(FileW);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180004b50  mov     rax, rsp
0x180004b53  mov     [rax+18h], rbx
0x180004b57  mov     [rax+20h], rsi
0x180004b5b  mov     [rax+10h], dx
0x180004b5f  push    rdi
0x180004b60  sub     rsp, 40h
0x180004b64  xor     esi, esi
0x180004b66  mov     bl, sil
0x180004b69  cmp     [rcx], si
0x180004b6c  jz      short loc_180004BD5
0x180004b6e  lea     edx, [rsi+3]; dwDesiredAccess
0x180004b71  mov     [rax-18h], rsi
0x180004b75  mov     dword ptr [rax-20h], 2000000h
0x180004b7c  mov     r8d, edx; dwShareMode
0x180004b7f  xor     r9d, r9d; lpSecurityAttributes
0x180004b82  mov     [rax-28h], edx
0x180004b85  call    cs:__imp_CreateFileW
0x180004b8b  mov     rdi, rax
0x180004b8e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180004b92  jz      short loc_180004BD5
0x180004b94  mov     [rsp+48h+lpOverlapped], rsi; lpOverlapped
0x180004b99  lea     rax, [rsp+48h+BytesReturned]
0x180004b9e  mov     [rsp+48h+lpBytesReturned], rax; lpBytesReturned
0x180004ba3  lea     r9d, [rsi+2]; nInBufferSize
0x180004ba7  mov     [rsp+48h+nOutBufferSize], esi; nOutBufferSize
0x180004bab  lea     r8, [rsp+48h+InBuffer]; lpInBuffer
0x180004bb0  mov     edx, 9C040h; dwIoControlCode
0x180004bb5  mov     [rsp+48h+lpOutBuffer], rsi; lpOutBuffer
0x180004bba  mov     rcx, rdi; hDevice
0x180004bbd  mov     [rsp+48h+BytesReturned], esi
0x180004bc1  call    cs:__imp_DeviceIoControl
0x180004bc7  test    eax, eax
0x180004bc9  mov     rcx, rdi; hObject
0x180004bcc  setnz   bl
0x180004bcf  call    cs:__imp_CloseHandle
0x180004bd5  mov     rsi, [rsp+48h+arg_18]
0x180004bda  mov     al, bl
0x180004bdc  mov     rbx, [rsp+48h+arg_10]
0x180004be1  add     rsp, 40h
0x180004be5  pop     rdi
0x180004be6  retn
```
