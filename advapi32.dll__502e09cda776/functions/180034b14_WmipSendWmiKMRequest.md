# WmipSendWmiKMRequest

- ea: `0x180034b14`
- end: `0x180034d14`
- name: `WmipSendWmiKMRequest`
- size: `512`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18003b840`
- `0x1800658f0`
- `0x180065e20`
- `0x180066230`
- `0x180066450`
- `0x1800666a0`
- `0x1800669d0`
- `0x180066c20`
- `0x180067000`
- `0x180067290`
- `0x180068330`
- `0x180069628`
- `0x180069a20`

## callees

- `0x180034b14`
- `0x1800386a4`

## import_xrefs

- `ntdll!NtDeviceIoControlFile` at `0x180034be2`
- `ntdll!NtDeviceIoControlFile` at `0x180034be2`
- `ntdll!NtWaitForSingleObject` at `0x180034cde`
- `ntdll!NtWaitForSingleObject` at `0x180034cde`
- `ntdll!RtlSetLastWin32Error` at `0x180034c26`
- `ntdll!RtlSetLastWin32Error` at `0x180034c26`
- `ntdll!RtlLeaveCriticalSection` at `0x180034b6b`
- `ntdll!RtlLeaveCriticalSection` at `0x180034c91`
- `ntdll!RtlLeaveCriticalSection` at `0x180034b6b`
- `ntdll!RtlLeaveCriticalSection` at `0x180034c91`
- `ntdll!RtlEnterCriticalSection` at `0x180034b48`
- `ntdll!RtlEnterCriticalSection` at `0x180034b48`
- `ntdll!RtlNtStatusToDosError` at `0x180034c16`
- `ntdll!RtlNtStatusToDosError` at `0x180034c9f`
- `ntdll!RtlNtStatusToDosError` at `0x180034c16`
- `ntdll!RtlNtStatusToDosError` at `0x180034c9f`
- `KERNEL32!GetLastError` at `0x180034cad`
- `KERNEL32!GetLastError` at `0x180034cad`
- `KERNEL32!CreateEventW` at `0x180034b81`
- `KERNEL32!CreateEventW` at `0x180034b81`
- `KERNEL32!CloseHandle` at `0x180034c3e`
- `KERNEL32!CloseHandle` at `0x180034c3e`

## pseudocode

```c
ULONG __fastcall WmipSendWmiKMRequest(
        __int64 a1,
        ULONG a2,
        void *a3,
        ULONG a4,
        PVOID OutputBuffer,
        ULONG OutputBufferLength,
        _DWORD *a7)
{
  ULONG IoControlCode; // edi
  HANDLE EventW; // rax
  HANDLE v11; // rsi
  NTSTATUS Status; // eax
  int Information; // edx
  ULONG v14; // edi
  NTSTATUS v16; // ebx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-28h] BYREF
  HANDLE hObject[2]; // [rsp+60h] [rbp-18h]

  IoControlCode = a2;
  IoStatusBlock = 0;
  *(_OWORD *)hObject = 0;
  RtlEnterCriticalSection(&PMCritSect);
  if ( !WmipKMHandle )
  {
    v16 = WmipOpenWmiDevice();
    if ( (v16 & 0xC0000000) == 0xC0000000 )
    {
      WmipKMHandle = 0;
      RtlLeaveCriticalSection(&PMCritSect);
      return RtlNtStatusToDosError(v16);
    }
  }
  RtlLeaveCriticalSection(&PMCritSect);
  EventW = CreateEventW(0, 0, 0, 0);
  hObject[1] = EventW;
  if ( !EventW )
    return GetLastError();
  v11 = WmipKMHandle;
  while ( 1 )
  {
    IoStatusBlock.Pointer = (PVOID)259;
    Status = NtDeviceIoControlFile(
               v11,
               EventW,
               0,
               0,
               &IoStatusBlock,
               IoControlCode,
               a3,
               a4,
               OutputBuffer,
               OutputBufferLength);
    Information = IoStatusBlock.Information;
    if ( (Status & 0xC0000000) != 0xC0000000 && a7 )
      *a7 = IoStatusBlock.Information;
    if ( Status != 259 )
      break;
    Status = IoStatusBlock.Status;
    if ( IoStatusBlock.Status != 259 )
    {
      if ( a7 )
        *a7 = Information;
      break;
    }
    Status = NtWaitForSingleObject(hObject[1], 0, 0);
    if ( !Status )
    {
      if ( a7 )
        *a7 = IoStatusBlock.Information;
      Status = IoStatusBlock.Status;
      break;
    }
LABEL_7:
    v14 = RtlNtStatusToDosError(Status);
    RtlSetLastWin32Error(v14);
    if ( v14 != 4203 )
      goto LABEL_8;
    EventW = hObject[1];
    IoControlCode = a2;
  }
  if ( Status )
    goto LABEL_7;
  v14 = 0;
LABEL_8:
  CloseHandle(hObject[1]);
  return v14;
}

```

## disassembly

```asm
0x180034b14  mov     [rsp-40h+arg_8], edx
0x180034b18  push    rbp
0x180034b19  push    rbx
0x180034b1a  push    rsi
0x180034b1b  push    rdi
0x180034b1c  push    r12
0x180034b1e  push    r13
0x180034b20  push    r14
0x180034b22  push    r15
0x180034b24  mov     rbp, rsp
0x180034b27  sub     rsp, 78h
0x180034b2b  xorps   xmm0, xmm0
0x180034b2e  lea     rsi, PMCritSect
0x180034b35  mov     rcx, rsi; CriticalSection
0x180034b38  mov     r12d, r9d
0x180034b3b  mov     r13, r8
0x180034b3e  mov     edi, edx
0x180034b40  movups  xmmword ptr [rbp+var_28], xmm0
0x180034b44  movups  xmmword ptr [rbp+hObject], xmm0
0x180034b48  call    cs:__imp_RtlEnterCriticalSection
0x180034b4f  nop     dword ptr [rax+rax+00h]
0x180034b54  cmp     cs:WmipKMHandle, 0
0x180034b5c  mov     r14d, 0C0000000h
0x180034b62  jz      loc_180034C6E
0x180034b68  mov     rcx, rsi; CriticalSection
0x180034b6b  call    cs:__imp_RtlLeaveCriticalSection
0x180034b72  nop     dword ptr [rax+rax+00h]
0x180034b77  xor     r9d, r9d; lpName
0x180034b7a  xor     r8d, r8d; bInitialState
0x180034b7d  xor     edx, edx; bManualReset
0x180034b7f  xor     ecx, ecx; lpEventAttributes
0x180034b81  call    cs:__imp_CreateEventW
0x180034b88  nop     dword ptr [rax+rax+00h]
0x180034b8d  mov     [rbp+hObject+8], rax
0x180034b91  test    rax, rax
0x180034b94  jz      loc_180034CAD
0x180034b9a  mov     rsi, cs:WmipKMHandle
0x180034ba1  mov     rbx, [rbp+arg_30]
0x180034ba5  mov     r14d, [rbp+arg_28]
0x180034ba9  mov     r15, [rbp+arg_20]
0x180034bad  mov     [rsp+78h+OutputBufferLength], r14d; OutputBufferLength
0x180034bb2  lea     rcx, [rbp+var_28]
0x180034bb6  mov     [rsp+78h+OutputBuffer], r15; OutputBuffer
0x180034bbb  xor     r9d, r9d; ApcContext
0x180034bbe  mov     [rsp+78h+InputBufferLength], r12d; InputBufferLength
0x180034bc3  xor     r8d, r8d; ApcRoutine
0x180034bc6  mov     [rsp+78h+InputBuffer], r13; InputBuffer
0x180034bcb  mov     rdx, rax; Event
0x180034bce  mov     [rsp+78h+IoControlCode], edi; IoControlCode
0x180034bd2  mov     [rsp+78h+IoStatusBlock], rcx; IoStatusBlock
0x180034bd7  mov     rcx, rsi; FileHandle
0x180034bda  mov     qword ptr [rbp+var_28], 103h
0x180034be2  call    cs:__imp_NtDeviceIoControlFile
0x180034be9  nop     dword ptr [rax+rax+00h]
0x180034bee  mov     edx, dword ptr [rbp+var_28.Information]
0x180034bf1  mov     r8d, 0C0000000h
0x180034bf7  mov     ecx, eax
0x180034bf9  and     ecx, r8d
0x180034bfc  cmp     ecx, r8d
0x180034bff  jnz     loc_180034CBB
0x180034c05  cmp     eax, 103h
0x180034c0a  jz      loc_180034CCB
0x180034c10  test    eax, eax
0x180034c12  jz      short loc_180034C5E
0x180034c14  mov     ecx, eax; Status
0x180034c16  call    cs:__imp_RtlNtStatusToDosError
0x180034c1d  nop     dword ptr [rax+rax+00h]
0x180034c22  mov     ecx, eax; LastError
0x180034c24  mov     edi, eax
0x180034c26  call    cs:__imp_RtlSetLastWin32Error
0x180034c2d  nop     dword ptr [rax+rax+00h]
0x180034c32  cmp     edi, 106Bh
0x180034c38  jz      short loc_180034C62
0x180034c3a  mov     rcx, [rbp+hObject+8]; hObject
0x180034c3e  call    cs:__imp_CloseHandle
0x180034c45  nop     dword ptr [rax+rax+00h]
0x180034c4a  mov     eax, edi
0x180034c4c  add     rsp, 78h
0x180034c50  pop     r15
0x180034c52  pop     r14
0x180034c54  pop     r13
0x180034c56  pop     r12
0x180034c58  pop     rdi
0x180034c59  pop     rsi
0x180034c5a  pop     rbx
0x180034c5b  pop     rbp
0x180034c5c  retn
0x180034c5e  xor     edi, edi
0x180034c60  jmp     short loc_180034C3A
0x180034c62  mov     rax, [rbp+hObject+8]
0x180034c66  mov     edi, [rbp+arg_8]
0x180034c69  jmp     loc_180034BAD
0x180034c6e  call    WmipOpenWmiDevice
0x180034c73  mov     edx, eax
0x180034c75  mov     ebx, eax
0x180034c77  and     edx, r14d
0x180034c7a  cmp     edx, r14d
0x180034c7d  jnz     loc_180034B68
0x180034c83  mov     rcx, rsi; CriticalSection
0x180034c86  mov     cs:WmipKMHandle, 0
0x180034c91  call    cs:__imp_RtlLeaveCriticalSection
0x180034c98  nop     dword ptr [rax+rax+00h]
0x180034c9d  mov     ecx, ebx; Status
0x180034c9f  call    cs:__imp_RtlNtStatusToDosError
0x180034ca6  nop     dword ptr [rax+rax+00h]
0x180034cab  jmp     short loc_180034C4C
0x180034cad  call    cs:__imp_GetLastError
0x180034cb4  nop     dword ptr [rax+rax+00h]
0x180034cb9  jmp     short loc_180034C4C
0x180034cbb  test    rbx, rbx
0x180034cbe  jz      loc_180034C05
0x180034cc4  mov     [rbx], edx
0x180034cc6  jmp     loc_180034C05
0x180034ccb  mov     eax, dword ptr [rbp+var_28]
0x180034cce  cmp     eax, 103h
0x180034cd3  jnz     short loc_180034D04
0x180034cd5  mov     rcx, [rbp+hObject+8]; Handle
0x180034cd9  xor     r8d, r8d; Timeout
0x180034cdc  xor     edx, edx; Alertable
0x180034cde  call    cs:__imp_NtWaitForSingleObject
0x180034ce5  nop     dword ptr [rax+rax+00h]
0x180034cea  test    eax, eax
0x180034cec  jnz     loc_180034C14
0x180034cf2  test    rbx, rbx
0x180034cf5  jz      short loc_180034CFC
0x180034cf7  mov     eax, dword ptr [rbp+var_28.Information]
0x180034cfa  mov     [rbx], eax
0x180034cfc  mov     eax, dword ptr [rbp+var_28]
0x180034cff  jmp     loc_180034C10
0x180034d04  test    rbx, rbx
0x180034d07  jz      loc_180034C10
0x180034d0d  mov     [rbx], edx
0x180034d0f  jmp     loc_180034C10
```
