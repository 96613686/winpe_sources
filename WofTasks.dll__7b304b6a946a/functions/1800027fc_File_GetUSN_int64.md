# File::GetUSN(__int64 *)

- ea: `0x1800027fc`
- end: `0x1800028cf`
- name: `?GetUSN@File@@QEAAJPEA_J@Z`
- size: `211`
- prototype: `__int64 __fastcall(HANDLE *this, __int64 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001e9c`
- `0x18000228c`

## callees

- `0x1800027fc`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800028b7`
- `KERNEL32!HeapFree` at `0x1800028b7`
- `KERNEL32!HeapAlloc` at `0x18000282a`
- `KERNEL32!HeapAlloc` at `0x18000282a`
- `KERNEL32!GetProcessHeap` at `0x180002819`
- `KERNEL32!GetProcessHeap` at `0x1800028a9`
- `KERNEL32!GetProcessHeap` at `0x180002819`
- `KERNEL32!GetProcessHeap` at `0x1800028a9`
- `KERNEL32!DeviceIoControl` at `0x18000286d`
- `KERNEL32!DeviceIoControl` at `0x18000286d`
- `KERNEL32!GetLastError` at `0x180002877`
- `KERNEL32!GetLastError` at `0x180002877`

## pseudocode

```c
__int64 __fastcall File::GetUSN(HANDLE *this, __int64 *a2)
{
  HANDLE ProcessHeap; // rax
  _QWORD *lpOutBuffer; // rdi
  unsigned int v6; // ebx
  signed int LastError; // eax
  HANDLE v8; // rax
  DWORD BytesReturned; // [rsp+60h] [rbp+18h] BYREF

  BytesReturned = 0;
  ProcessHeap = GetProcessHeap();
  lpOutBuffer = HeapAlloc(ProcessHeap, 0, 0x250u);
  if ( lpOutBuffer )
  {
    if ( DeviceIoControl(*this, 0x900EBu, 0, 0, lpOutBuffer, 0x250u, &BytesReturned, 0) )
    {
      v6 = 0;
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( v6 )
        goto LABEL_12;
    }
    if ( BytesReturned >= 0x40 )
      *a2 = lpOutBuffer[3];
    else
      v6 = -2147418113;
LABEL_12:
    v8 = GetProcessHeap();
    HeapFree(v8, 0, lpOutBuffer);
    return v6;
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x1800027fc  mov     [rsp+arg_0], rbx
0x180002801  mov     [rsp+arg_8], rsi
0x180002806  push    rdi
0x180002807  sub     rsp, 40h
0x18000280b  mov     rsi, rdx
0x18000280e  mov     [rsp+48h+BytesReturned], 0
0x180002816  mov     rbx, rcx
0x180002819  call    cs:__imp_GetProcessHeap
0x18000281f  xor     edx, edx; dwFlags
0x180002821  mov     r8d, 250h; dwBytes
0x180002827  mov     rcx, rax; hHeap
0x18000282a  call    cs:__imp_HeapAlloc
0x180002830  mov     rdi, rax
0x180002833  test    rax, rax
0x180002836  jnz     short loc_18000283F
0x180002838  mov     ebx, 8007000Eh
0x18000283d  jmp     short loc_1800028BD
0x18000283f  mov     rcx, [rbx]; hDevice
0x180002842  lea     rax, [rsp+48h+BytesReturned]
0x180002847  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x180002850  xor     r9d, r9d; nInBufferSize
0x180002853  mov     [rsp+48h+lpBytesReturned], rax; lpBytesReturned
0x180002858  xor     r8d, r8d; lpInBuffer
0x18000285b  mov     [rsp+48h+nOutBufferSize], 250h; nOutBufferSize
0x180002863  mov     edx, 900EBh; dwIoControlCode
0x180002868  mov     [rsp+48h+lpOutBuffer], rdi; lpOutBuffer
0x18000286d  call    cs:__imp_DeviceIoControl
0x180002873  test    eax, eax
0x180002875  jnz     short loc_180002892
0x180002877  call    cs:__imp_GetLastError
0x18000287d  mov     ebx, eax
0x18000287f  test    eax, eax
0x180002881  jle     short loc_18000288C
0x180002883  movzx   ebx, ax
0x180002886  or      ebx, 80070000h
0x18000288c  test    ebx, ebx
0x18000288e  jnz     short loc_1800028A9
0x180002890  jmp     short loc_180002894
0x180002892  xor     ebx, ebx
0x180002894  cmp     [rsp+48h+BytesReturned], 40h ; '@'
0x180002899  jnb     short loc_1800028A2
0x18000289b  mov     ebx, 8000FFFFh
0x1800028a0  jmp     short loc_1800028A9
0x1800028a2  mov     rcx, [rdi+18h]
0x1800028a6  mov     [rsi], rcx
0x1800028a9  call    cs:__imp_GetProcessHeap
0x1800028af  mov     r8, rdi; lpMem
0x1800028b2  xor     edx, edx; dwFlags
0x1800028b4  mov     rcx, rax; hHeap
0x1800028b7  call    cs:__imp_HeapFree
0x1800028bd  mov     rsi, [rsp+48h+arg_8]
0x1800028c2  mov     eax, ebx
0x1800028c4  mov     rbx, [rsp+48h+arg_0]
0x1800028c9  add     rsp, 40h
0x1800028cd  pop     rdi
0x1800028ce  retn
```
