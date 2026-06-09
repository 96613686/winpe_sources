# WmipSendWmiKMRequest

- ea: `0x180031730`
- end: `0x1800318ed`
- name: `WmipSendWmiKMRequest`
- size: `445`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180037740`
- `0x1800596b0`
- `0x180059b90`
- `0x180059f40`
- `0x18005a130`
- `0x18005a350`
- `0x18005a630`
- `0x18005a840`
- `0x18005abf0`
- `0x18005ae40`
- `0x18005bdf8`
- `0x18005cf44`
- `0x18005d314`

## callees

- `0x180031730`
- `0x180034ab0`

## import_xrefs

- `ntdll!NtDeviceIoControlFile` at `0x1800317ec`
- `ntdll!NtDeviceIoControlFile` at `0x1800317ec`
- `ntdll!NtWaitForSingleObject` at `0x1800318bd`
- `ntdll!NtWaitForSingleObject` at `0x1800318bd`
- `ntdll!RtlSetLastWin32Error` at `0x180031824`
- `ntdll!RtlSetLastWin32Error` at `0x180031824`
- `ntdll!RtlLeaveCriticalSection` at `0x180031781`
- `ntdll!RtlLeaveCriticalSection` at `0x180031882`
- `ntdll!RtlLeaveCriticalSection` at `0x180031781`
- `ntdll!RtlLeaveCriticalSection` at `0x180031882`
- `ntdll!RtlEnterCriticalSection` at `0x180031764`
- `ntdll!RtlEnterCriticalSection` at `0x180031764`
- `ntdll!RtlNtStatusToDosError` at `0x18003181a`
- `ntdll!RtlNtStatusToDosError` at `0x18003188a`
- `ntdll!RtlNtStatusToDosError` at `0x18003181a`
- `ntdll!RtlNtStatusToDosError` at `0x18003188a`
- `KERNEL32!GetLastError` at `0x180031892`
- `KERNEL32!GetLastError` at `0x180031892`
- `KERNEL32!CreateEventW` at `0x180031791`
- `KERNEL32!CreateEventW` at `0x180031791`
- `KERNEL32!CloseHandle` at `0x180031836`
- `KERNEL32!CloseHandle` at `0x180031836`

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
0x180031730  mov     [rsp-40h+arg_8], edx
0x180031734  push    rbp
0x180031735  push    rbx
0x180031736  push    rsi
0x180031737  push    rdi
0x180031738  push    r12
0x18003173a  push    r13
0x18003173c  push    r14
0x18003173e  push    r15
0x180031740  mov     rbp, rsp
0x180031743  sub     rsp, 78h
0x180031747  xorps   xmm0, xmm0
0x18003174a  lea     rsi, PMCritSect
0x180031751  mov     rcx, rsi; CriticalSection
0x180031754  mov     r12d, r9d
0x180031757  mov     r13, r8
0x18003175a  mov     edi, edx
0x18003175c  movups  xmmword ptr [rbp+var_28], xmm0
0x180031760  movups  xmmword ptr [rbp+hObject], xmm0
0x180031764  call    cs:__imp_RtlEnterCriticalSection
0x18003176a  cmp     cs:WmipKMHandle, 0
0x180031772  mov     r14d, 0C0000000h
0x180031778  jz      loc_18003185F
0x18003177e  mov     rcx, rsi; CriticalSection
0x180031781  call    cs:__imp_RtlLeaveCriticalSection
0x180031787  xor     r9d, r9d; lpName
0x18003178a  xor     r8d, r8d; bInitialState
0x18003178d  xor     edx, edx; bManualReset
0x18003178f  xor     ecx, ecx; lpEventAttributes
0x180031791  call    cs:__imp_CreateEventW
0x180031797  mov     [rbp+hObject+8], rax
0x18003179b  test    rax, rax
0x18003179e  jz      loc_180031892
0x1800317a4  mov     rsi, cs:WmipKMHandle
0x1800317ab  mov     rbx, [rbp+arg_30]
0x1800317af  mov     r14d, [rbp+arg_28]
0x1800317b3  mov     r15, [rbp+arg_20]
0x1800317b7  mov     [rsp+78h+OutputBufferLength], r14d; OutputBufferLength
0x1800317bc  lea     rcx, [rbp+var_28]
0x1800317c0  mov     [rsp+78h+OutputBuffer], r15; OutputBuffer
0x1800317c5  xor     r9d, r9d; ApcContext
0x1800317c8  mov     [rsp+78h+InputBufferLength], r12d; InputBufferLength
0x1800317cd  xor     r8d, r8d; ApcRoutine
0x1800317d0  mov     [rsp+78h+InputBuffer], r13; InputBuffer
0x1800317d5  mov     rdx, rax; Event
0x1800317d8  mov     [rsp+78h+IoControlCode], edi; IoControlCode
0x1800317dc  mov     [rsp+78h+IoStatusBlock], rcx; IoStatusBlock
0x1800317e1  mov     rcx, rsi; FileHandle
0x1800317e4  mov     qword ptr [rbp+var_28], 103h
0x1800317ec  call    cs:__imp_NtDeviceIoControlFile
0x1800317f2  mov     edx, dword ptr [rbp+var_28.Information]
0x1800317f5  mov     r8d, 0C0000000h
0x1800317fb  mov     ecx, eax
0x1800317fd  and     ecx, r8d
0x180031800  cmp     ecx, r8d
0x180031803  jnz     loc_18003189A
0x180031809  cmp     eax, 103h
0x18003180e  jz      loc_1800318AA
0x180031814  test    eax, eax
0x180031816  jz      short loc_18003184F
0x180031818  mov     ecx, eax; Status
0x18003181a  call    cs:__imp_RtlNtStatusToDosError
0x180031820  mov     ecx, eax; LastError
0x180031822  mov     edi, eax
0x180031824  call    cs:__imp_RtlSetLastWin32Error
0x18003182a  cmp     edi, 106Bh
0x180031830  jz      short loc_180031853
0x180031832  mov     rcx, [rbp+hObject+8]; hObject
0x180031836  call    cs:__imp_CloseHandle
0x18003183c  mov     eax, edi
0x18003183e  add     rsp, 78h
0x180031842  pop     r15
0x180031844  pop     r14
0x180031846  pop     r13
0x180031848  pop     r12
0x18003184a  pop     rdi
0x18003184b  pop     rsi
0x18003184c  pop     rbx
0x18003184d  pop     rbp
0x18003184e  retn
0x18003184f  xor     edi, edi
0x180031851  jmp     short loc_180031832
0x180031853  mov     rax, [rbp+hObject+8]
0x180031857  mov     edi, [rbp+arg_8]
0x18003185a  jmp     loc_1800317B7
0x18003185f  call    WmipOpenWmiDevice
0x180031864  mov     edx, eax
0x180031866  mov     ebx, eax
0x180031868  and     edx, r14d
0x18003186b  cmp     edx, r14d
0x18003186e  jnz     loc_18003177E
0x180031874  mov     rcx, rsi; CriticalSection
0x180031877  mov     cs:WmipKMHandle, 0
0x180031882  call    cs:__imp_RtlLeaveCriticalSection
0x180031888  mov     ecx, ebx; Status
0x18003188a  call    cs:__imp_RtlNtStatusToDosError
0x180031890  jmp     short loc_18003183E
0x180031892  call    cs:__imp_GetLastError
0x180031898  jmp     short loc_18003183E
0x18003189a  test    rbx, rbx
0x18003189d  jz      loc_180031809
0x1800318a3  mov     [rbx], edx
0x1800318a5  jmp     loc_180031809
0x1800318aa  mov     eax, dword ptr [rbp+var_28]
0x1800318ad  cmp     eax, 103h
0x1800318b2  jnz     short loc_1800318DD
0x1800318b4  mov     rcx, [rbp+hObject+8]; Handle
0x1800318b8  xor     r8d, r8d; Timeout
0x1800318bb  xor     edx, edx; Alertable
0x1800318bd  call    cs:__imp_NtWaitForSingleObject
0x1800318c3  test    eax, eax
0x1800318c5  jnz     loc_180031818
0x1800318cb  test    rbx, rbx
0x1800318ce  jz      short loc_1800318D5
0x1800318d0  mov     eax, dword ptr [rbp+var_28.Information]
0x1800318d3  mov     [rbx], eax
0x1800318d5  mov     eax, dword ptr [rbp+var_28]
0x1800318d8  jmp     loc_180031814
0x1800318dd  test    rbx, rbx
0x1800318e0  jz      loc_180031814
0x1800318e6  mov     [rbx], edx
0x1800318e8  jmp     loc_180031814
```
