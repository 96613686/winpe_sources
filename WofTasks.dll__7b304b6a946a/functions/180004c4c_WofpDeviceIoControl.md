# WofpDeviceIoControl

- ea: `0x180004c4c`
- end: `0x180004c9d`
- name: `WofpDeviceIoControl`
- size: `81`
- prototype: `signed int __fastcall(void *, DWORD, void *, DWORD, LPVOID lpOutBuffer, DWORD nOutBufferSize, LPDWORD lpBytesReturned)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800040a8`
- `0x180004788`
- `0x180004af4`

## callees

- `0x180004c4c`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x180004c78`
- `KERNEL32!DeviceIoControl` at `0x180004c78`
- `KERNEL32!GetLastError` at `0x180004c86`
- `KERNEL32!GetLastError` at `0x180004c86`

## pseudocode

```c
signed int __fastcall WofpDeviceIoControl(
        void *a1,
        DWORD a2,
        void *a3,
        DWORD a4,
        LPVOID lpOutBuffer,
        DWORD nOutBufferSize,
        LPDWORD lpBytesReturned)
{
  signed int result; // eax

  if ( DeviceIoControl(a1, a2, a3, a4, lpOutBuffer, nOutBufferSize, lpBytesReturned, 0) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180004c4c  sub     rsp, 48h
0x180004c50  mov     rax, [rsp+48h+arg_30]
0x180004c58  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x180004c61  mov     [rsp+48h+lpBytesReturned], rax; lpBytesReturned
0x180004c66  mov     eax, [rsp+48h+arg_28]
0x180004c6a  mov     [rsp+48h+nOutBufferSize], eax; nOutBufferSize
0x180004c6e  mov     rax, [rsp+48h+arg_20]
0x180004c73  mov     [rsp+48h+lpOutBuffer], rax; lpOutBuffer
0x180004c78  call    cs:__imp_DeviceIoControl
0x180004c7e  test    eax, eax
0x180004c80  jz      short loc_180004C86
0x180004c82  xor     eax, eax
0x180004c84  jmp     short loc_180004C98
0x180004c86  call    cs:__imp_GetLastError
0x180004c8c  test    eax, eax
0x180004c8e  jle     short loc_180004C98
0x180004c90  movzx   eax, ax
0x180004c93  or      eax, 80070000h
0x180004c98  add     rsp, 48h
0x180004c9c  retn
```
