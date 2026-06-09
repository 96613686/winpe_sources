# WinSAT::StorageDevice::CalculateSizeOfDisk(void)

- ea: `0x140060790`
- end: `0x140060880`
- name: `?CalculateSizeOfDisk@StorageDevice@WinSAT@@AEAA_NXZ`
- size: `240`
- prototype: `bool __fastcall(WinSAT::StorageDevice *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140061494`

## callees

- `0x140060790`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x14006080e`
- `KERNEL32!DeviceIoControl` at `0x14006080e`
- `KERNEL32!CloseHandle` at `0x140060866`
- `KERNEL32!CloseHandle` at `0x140060866`
- `KERNEL32!GetLastError` at `0x140060822`
- `KERNEL32!GetLastError` at `0x140060822`
- `KERNEL32!CreateEventW` at `0x1400607cd`
- `KERNEL32!CreateEventW` at `0x1400607cd`
- `KERNEL32!GetOverlappedResult` at `0x140060851`
- `KERNEL32!GetOverlappedResult` at `0x140060851`
- `KERNEL32!WaitForSingleObject` at `0x140060838`
- `KERNEL32!WaitForSingleObject` at `0x140060838`

## pseudocode

```c
char __fastcall WinSAT::StorageDevice::CalculateSizeOfDisk(WinSAT::StorageDevice *this)
{
  char v2; // bl
  struct _OVERLAPPED Overlapped; // [rsp+40h] [rbp-20h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+78h] [rbp+18h] BYREF
  __int64 OutBuffer; // [rsp+80h] [rbp+20h] BYREF

  OutBuffer = 0;
  NumberOfBytesTransferred = 0;
  memset(&Overlapped, 0, 24);
  v2 = 1;
  Overlapped.hEvent = CreateEventW(0, 1, 0, 0);
  if ( Overlapped.hEvent
    && (DeviceIoControl(*((HANDLE *)this + 9), 0x7405Cu, 0, 0, &OutBuffer, 8u, 0, &Overlapped)
     || GetLastError() == 997
     && !WaitForSingleObject(Overlapped.hEvent, 0x1388u)
     && GetOverlappedResult(*((HANDLE *)this + 9), &Overlapped, &NumberOfBytesTransferred, 0)) )
  {
    *((_QWORD *)this + 5) = OutBuffer;
  }
  else
  {
    v2 = 0;
  }
  if ( Overlapped.hEvent )
    CloseHandle(Overlapped.hEvent);
  return v2;
}

```

## disassembly

```asm
0x140060790  mov     [rsp-8+arg_0], rbx
0x140060795  mov     [rsp-8+arg_18], rdi
0x14006079a  push    rbp
0x14006079b  mov     rbp, rsp
0x14006079e  sub     rsp, 60h
0x1400607a2  xorps   xmm0, xmm0
0x1400607a5  mov     [rbp+OutBuffer], 0
0x1400607ad  xor     r9d, r9d; lpName
0x1400607b0  mov     [rbp+NumberOfBytesTransferred], 0
0x1400607b7  mov     rdi, rcx
0x1400607ba  xor     r8d, r8d; bInitialState
0x1400607bd  xor     ecx, ecx; lpEventAttributes
0x1400607bf  movups  xmmword ptr [rbp+Overlapped.Internal], xmm0
0x1400607c3  lea     ebx, [r9+1]
0x1400607c7  mov     edx, ebx; bManualReset
0x1400607c9  movups  xmmword ptr [rbp+Overlapped.10h], xmm0
0x1400607cd  call    cs:__imp_CreateEventW
0x1400607d3  mov     [rbp+Overlapped.hEvent], rax
0x1400607d7  test    rax, rax
0x1400607da  jz      short loc_14006085B
0x1400607dc  mov     rcx, [rdi+48h]; hDevice
0x1400607e0  lea     rax, [rbp+Overlapped]
0x1400607e4  mov     [rsp+60h+lpOverlapped], rax; lpOverlapped
0x1400607e9  xor     r9d, r9d; nInBufferSize
0x1400607ec  mov     [rsp+60h+lpBytesReturned], 0; lpBytesReturned
0x1400607f5  lea     rax, [rbp+OutBuffer]
0x1400607f9  mov     [rsp+60h+nOutBufferSize], 8; nOutBufferSize
0x140060801  xor     r8d, r8d; lpInBuffer
0x140060804  mov     edx, 7405Ch; dwIoControlCode
0x140060809  mov     [rsp+60h+lpOutBuffer], rax; lpOutBuffer
0x14006080e  call    cs:__imp_DeviceIoControl
0x140060814  test    eax, eax
0x140060816  jz      short loc_140060822
0x140060818  mov     rax, [rbp+OutBuffer]
0x14006081c  mov     [rdi+28h], rax
0x140060820  jmp     short loc_14006085D
0x140060822  call    cs:__imp_GetLastError
0x140060828  cmp     eax, 3E5h
0x14006082d  jnz     short loc_14006085B
0x14006082f  mov     rcx, [rbp+Overlapped.hEvent]; hHandle
0x140060833  mov     edx, 1388h; dwMilliseconds
0x140060838  call    cs:__imp_WaitForSingleObject
0x14006083e  test    eax, eax
0x140060840  jnz     short loc_14006085B
0x140060842  mov     rcx, [rdi+48h]; hFile
0x140060846  lea     r8, [rbp+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x14006084a  xor     r9d, r9d; bWait
0x14006084d  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x140060851  call    cs:__imp_GetOverlappedResult
0x140060857  test    eax, eax
0x140060859  jnz     short loc_140060818
0x14006085b  xor     bl, bl
0x14006085d  mov     rcx, [rbp+Overlapped.hEvent]; hObject
0x140060861  test    rcx, rcx
0x140060864  jz      short loc_14006086C
0x140060866  call    cs:__imp_CloseHandle
0x14006086c  lea     r11, [rsp+60h+var_s0]
0x140060871  mov     al, bl
0x140060873  mov     rbx, [r11+10h]
0x140060877  mov     rdi, [r11+28h]
0x14006087b  mov     rsp, r11
0x14006087e  pop     rbp
0x14006087f  retn
```
