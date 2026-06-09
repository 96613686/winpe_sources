# AlpcSection::SendXvmmDisconnect(unsigned __int64)

- ea: `0x18002b108`
- end: `0x18002b230`
- name: `?SendXvmmDisconnect@AlpcSection@@CAJ_K@Z`
- size: `296`
- prototype: `__int64 __fastcall(unsigned __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180024d9c`
- `0x180028eb0`
- `0x18002b288`

## callees

- `0x18002b108`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002b149`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002b149`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b203`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b216`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b203`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b216`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b15e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b1d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b15e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b1d7`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002b1c7`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002b1c7`

## pseudocode

```c
__int64 __fastcall AlpcSection::SendXvmmDisconnect(__int64 a1)
{
  HANDLE FileW; // rbx
  signed int LastError; // eax
  signed int v3; // ecx
  __int64 result; // rax
  signed int v5; // eax
  unsigned int v6; // edi
  __int64 InBuffer; // [rsp+50h] [rbp+8h] BYREF
  DWORD BytesReturned; // [rsp+58h] [rbp+10h] BYREF

  InBuffer = a1;
  if ( !a1 )
    return 0;
  FileW = CreateFileW(L"\\\\.\\XVmCtrl", 0xC0000000, 3u, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    result = 2147549183LL;
    if ( v3 < 0 )
      return (unsigned int)v3;
    return result;
  }
  BytesReturned = 0;
  if ( DeviceIoControl(FileW, 0x150274u, &InBuffer, 8u, 0, 0, &BytesReturned, 0)
    || (v5 = GetLastError(), v6 = v5, v5 == 1168)
    || v5 == -1070268398 )
  {
    CloseHandle(FileW);
    return 0;
  }
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  CloseHandle(FileW);
  return v6;
}

```

## disassembly

```asm
0x18002b108  mov     rax, rsp
0x18002b10b  mov     [rax+18h], rbx
0x18002b10f  mov     [rax+8], rcx
0x18002b113  push    rdi
0x18002b114  sub     rsp, 40h
0x18002b118  test    rcx, rcx
0x18002b11b  jz      loc_18002B222
0x18002b121  mov     qword ptr [rax-18h], 0
0x18002b129  lea     rcx, aXvmctrl; "\\\\.\\XVmCtrl"
0x18002b130  mov     r8d, 3; dwShareMode
0x18002b136  mov     dword ptr [rax-20h], 0
0x18002b13d  xor     r9d, r9d; lpSecurityAttributes
0x18002b140  mov     [rax-28h], r8d
0x18002b144  mov     edx, 0C0000000h; dwDesiredAccess
0x18002b149  call    cs:__imp_CreateFileW
0x18002b150  nop     dword ptr [rax+rax+00h]
0x18002b155  mov     rbx, rax
0x18002b158  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002b15c  jnz     short loc_18002B188
0x18002b15e  call    cs:__imp_GetLastError
0x18002b165  nop     dword ptr [rax+rax+00h]
0x18002b16a  mov     ecx, eax
0x18002b16c  test    eax, eax
0x18002b16e  jle     short loc_18002B179
0x18002b170  movzx   ecx, ax
0x18002b173  or      ecx, 80070000h
0x18002b179  test    ecx, ecx
0x18002b17b  mov     eax, 8000FFFFh
0x18002b180  cmovs   eax, ecx
0x18002b183  jmp     loc_18002B224
0x18002b188  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x18002b191  lea     rax, [rsp+48h+BytesReturned]
0x18002b196  mov     [rsp+48h+lpBytesReturned], rax; lpBytesReturned
0x18002b19b  lea     r8, [rsp+48h+InBuffer]; lpInBuffer
0x18002b1a0  mov     [rsp+48h+nOutBufferSize], 0; nOutBufferSize
0x18002b1a8  mov     r9d, 8; nInBufferSize
0x18002b1ae  mov     edx, 150274h; dwIoControlCode
0x18002b1b3  mov     [rsp+48h+lpOutBuffer], 0; lpOutBuffer
0x18002b1bc  mov     rcx, rbx; hDevice
0x18002b1bf  mov     [rsp+48h+BytesReturned], 0
0x18002b1c7  call    cs:__imp_DeviceIoControl
0x18002b1ce  nop     dword ptr [rax+rax+00h]
0x18002b1d3  test    eax, eax
0x18002b1d5  jnz     short loc_18002B213
0x18002b1d7  call    cs:__imp_GetLastError
0x18002b1de  nop     dword ptr [rax+rax+00h]
0x18002b1e3  mov     edi, eax
0x18002b1e5  cmp     eax, 490h
0x18002b1ea  jz      short loc_18002B213
0x18002b1ec  cmp     eax, 0C0350012h
0x18002b1f1  jz      short loc_18002B213
0x18002b1f3  test    eax, eax
0x18002b1f5  jle     short loc_18002B200
0x18002b1f7  movzx   edi, ax
0x18002b1fa  or      edi, 80070000h
0x18002b200  mov     rcx, rbx; hObject
0x18002b203  call    cs:__imp_CloseHandle
0x18002b20a  nop     dword ptr [rax+rax+00h]
0x18002b20f  mov     eax, edi
0x18002b211  jmp     short loc_18002B224
0x18002b213  mov     rcx, rbx; hObject
0x18002b216  call    cs:__imp_CloseHandle
0x18002b21d  nop     dword ptr [rax+rax+00h]
0x18002b222  xor     eax, eax
0x18002b224  mov     rbx, [rsp+48h+arg_10]
0x18002b229  add     rsp, 40h
0x18002b22d  pop     rdi
0x18002b22e  retn
```
