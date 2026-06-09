# WmipOpenKernelGuid

- ea: `0x18002b4e0`
- end: `0x18002b6d6`
- name: `WmipOpenKernelGuid`
- size: `502`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18002b120`
- `0x18005cc64`

## callees

- `0x18002b4e0`
- `0x18002b6dc`
- `0x180034ab0`
- `0x180065090`

## import_xrefs

- `ntdll!NtDeviceIoControlFile` at `0x18002b60d`
- `ntdll!NtDeviceIoControlFile` at `0x18002b60d`
- `ntdll!NtWaitForSingleObject` at `0x18002b6bf`
- `ntdll!NtWaitForSingleObject` at `0x18002b6bf`
- `ntdll!RtlSetLastWin32Error` at `0x18002b62e`
- `ntdll!RtlSetLastWin32Error` at `0x18002b62e`
- `ntdll!RtlLeaveCriticalSection` at `0x18002b59a`
- `ntdll!RtlLeaveCriticalSection` at `0x18002b68c`
- `ntdll!RtlLeaveCriticalSection` at `0x18002b59a`
- `ntdll!RtlLeaveCriticalSection` at `0x18002b68c`
- `ntdll!RtlEnterCriticalSection` at `0x18002b583`
- `ntdll!RtlEnterCriticalSection` at `0x18002b583`
- `ntdll!RtlNtStatusToDosError` at `0x18002b624`
- `ntdll!RtlNtStatusToDosError` at `0x18002b694`
- `ntdll!RtlNtStatusToDosError` at `0x18002b624`
- `ntdll!RtlNtStatusToDosError` at `0x18002b694`
- `KERNEL32!GetLastError` at `0x18002b69c`
- `KERNEL32!GetLastError` at `0x18002b69c`
- `KERNEL32!CreateEventW` at `0x18002b5aa`
- `KERNEL32!CreateEventW` at `0x18002b5aa`
- `KERNEL32!CloseHandle` at `0x18002b641`
- `KERNEL32!CloseHandle` at `0x18002b641`

## pseudocode

```c
__int64 __fastcall WmipOpenKernelGuid(__int64 a1, __int64 a2, _QWORD *a3, ULONG a4)
{
  int v6; // edi
  ULONG v7; // ebx
  HANDLE EventW; // rax
  HANDLE v10; // rdi
  NTSTATUS Status; // eax
  __int64 v12; // rax
  NTSTATUS v13; // ebx
  ULONG LastError; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE hObject[2]; // [rsp+60h] [rbp-A0h]
  __int128 InputBuffer; // [rsp+70h] [rbp-90h] BYREF
  __int64 v18; // [rsp+80h] [rbp-80h]
  __int128 v19; // [rsp+88h] [rbp-78h] BYREF
  _OWORD v20[3]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v21[96]; // [rsp+D0h] [rbp-30h] BYREF

  v18 = 0;
  v6 = a2;
  InputBuffer = 0;
  v19 = 0;
  memset(v20, 0, 44);
  v7 = WmipBuildGuidObjectAttributes(a1, a2, v20, &v19, v21);
  if ( v7 )
    return v7;
  DWORD2(InputBuffer) = v6;
  *(_QWORD *)&InputBuffer = v20;
  IoStatusBlock = 0;
  *(_OWORD *)hObject = 0;
  RtlEnterCriticalSection(&PMCritSect);
  if ( !WmipKMHandle )
  {
    v13 = WmipOpenWmiDevice();
    if ( (v13 & 0xC0000000) == 0xC0000000 )
    {
      WmipKMHandle = 0;
      RtlLeaveCriticalSection(&PMCritSect);
      LastError = RtlNtStatusToDosError(v13);
LABEL_18:
      v7 = LastError;
      goto LABEL_10;
    }
  }
  RtlLeaveCriticalSection(&PMCritSect);
  EventW = CreateEventW(0, 0, 0, 0);
  hObject[1] = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    goto LABEL_18;
  }
  v10 = WmipKMHandle;
  while ( 1 )
  {
    IoStatusBlock.Pointer = (PVOID)259;
    Status = NtDeviceIoControlFile(v10, EventW, 0, 0, &IoStatusBlock, a4, &InputBuffer, 0x18u, &InputBuffer, 0x18u);
    if ( Status != 259 )
      break;
    Status = IoStatusBlock.Status;
    if ( IoStatusBlock.Status != 259 )
      break;
    Status = NtWaitForSingleObject(hObject[1], 0, 0);
    if ( !Status )
    {
      Status = IoStatusBlock.Status;
      break;
    }
LABEL_8:
    v7 = RtlNtStatusToDosError(Status);
    RtlSetLastWin32Error(v7);
    if ( v7 != 4203 )
      goto LABEL_9;
    EventW = hObject[1];
  }
  if ( Status )
    goto LABEL_8;
  v7 = 0;
LABEL_9:
  CloseHandle(hObject[1]);
LABEL_10:
  v12 = 0;
  if ( !v7 )
    v12 = v18;
  *a3 = v12;
  return v7;
}

```

## disassembly

```asm
0x18002b4e0  push    rbp
0x18002b4e2  push    rbx
0x18002b4e3  push    rsi
0x18002b4e4  push    rdi
0x18002b4e5  push    r14
0x18002b4e7  lea     rbp, [rsp-40h]
0x18002b4ec  sub     rsp, 140h
0x18002b4f3  mov     rax, cs:__security_cookie
0x18002b4fa  xor     rax, rsp
0x18002b4fd  mov     [rbp+60h+var_30], rax
0x18002b501  xorps   xmm0, xmm0
0x18002b504  xor     eax, eax
0x18002b506  mov     [rbp+60h+var_E0], rax
0x18002b50a  mov     r14d, r9d
0x18002b50d  lea     rax, [rbp+60h+var_90]
0x18002b511  mov     rsi, r8
0x18002b514  movups  xmmword ptr [rbp+60h+var_B8], xmm0
0x18002b518  lea     r9, [rbp+60h+var_D8]
0x18002b51c  mov     [rsp+160h+IoStatusBlock], rax
0x18002b521  lea     r8, [rbp+60h+var_C8]
0x18002b525  mov     edi, edx
0x18002b527  movups  [rsp+160h+var_F0], xmm0
0x18002b52c  movups  [rbp+60h+var_D8], xmm0
0x18002b530  movups  [rbp+60h+var_C8], xmm0
0x18002b534  movups  xmmword ptr [rbp+60h+var_B8+0Ch], xmm0
0x18002b538  call    WmipBuildGuidObjectAttributes
0x18002b53d  mov     ebx, eax
0x18002b53f  test    eax, eax
0x18002b541  jz      short loc_18002B55F
0x18002b543  mov     eax, ebx
0x18002b545  mov     rcx, [rbp+60h+var_30]
0x18002b549  xor     rcx, rsp; StackCookie
0x18002b54c  call    __security_check_cookie
0x18002b551  add     rsp, 140h
0x18002b558  pop     r14
0x18002b55a  pop     rdi
0x18002b55b  pop     rsi
0x18002b55c  pop     rbx
0x18002b55d  pop     rbp
0x18002b55e  retn
0x18002b55f  xorps   xmm0, xmm0
0x18002b562  mov     dword ptr [rsp+160h+var_F0+8], edi
0x18002b566  lea     rax, [rbp+60h+var_C8]
0x18002b56a  lea     rdi, PMCritSect
0x18002b571  mov     qword ptr [rsp+160h+var_F0], rax
0x18002b576  mov     rcx, rdi; CriticalSection
0x18002b579  movups  xmmword ptr [rsp+160h+var_110], xmm0
0x18002b57e  movups  xmmword ptr [rsp+160h+hObject], xmm0
0x18002b583  call    cs:__imp_RtlEnterCriticalSection
0x18002b589  cmp     cs:WmipKMHandle, 0
0x18002b591  jz      loc_18002B666
0x18002b597  mov     rcx, rdi; CriticalSection
0x18002b59a  call    cs:__imp_RtlLeaveCriticalSection
0x18002b5a0  xor     r9d, r9d; lpName
0x18002b5a3  xor     r8d, r8d; bInitialState
0x18002b5a6  xor     edx, edx; bManualReset
0x18002b5a8  xor     ecx, ecx; lpEventAttributes
0x18002b5aa  call    cs:__imp_CreateEventW
0x18002b5b0  mov     [rsp+160h+hObject+8], rax
0x18002b5b5  test    rax, rax
0x18002b5b8  jz      loc_18002B69C
0x18002b5be  mov     rdi, cs:WmipKMHandle
0x18002b5c5  mov     [rsp+160h+OutputBufferLength], 18h; OutputBufferLength
0x18002b5cd  lea     rcx, [rsp+160h+var_F0]
0x18002b5d2  mov     [rsp+160h+OutputBuffer], rcx; OutputBuffer
0x18002b5d7  xor     r9d, r9d; ApcContext
0x18002b5da  mov     [rsp+160h+InputBufferLength], 18h; InputBufferLength
0x18002b5e2  lea     rcx, [rsp+160h+var_F0]
0x18002b5e7  mov     [rsp+160h+InputBuffer], rcx; InputBuffer
0x18002b5ec  xor     r8d, r8d; ApcRoutine
0x18002b5ef  lea     rcx, [rsp+160h+var_110]
0x18002b5f4  mov     [rsp+160h+IoControlCode], r14d; IoControlCode
0x18002b5f9  mov     [rsp+160h+IoStatusBlock], rcx; IoStatusBlock
0x18002b5fe  mov     rdx, rax; Event
0x18002b601  mov     rcx, rdi; FileHandle
0x18002b604  mov     qword ptr [rsp+160h+var_110], 103h
0x18002b60d  call    cs:__imp_NtDeviceIoControlFile
0x18002b613  cmp     eax, 103h
0x18002b618  jz      loc_18002B6A6
0x18002b61e  test    eax, eax
0x18002b620  jz      short loc_18002B658
0x18002b622  mov     ecx, eax; Status
0x18002b624  call    cs:__imp_RtlNtStatusToDosError
0x18002b62a  mov     ecx, eax; LastError
0x18002b62c  mov     ebx, eax
0x18002b62e  call    cs:__imp_RtlSetLastWin32Error
0x18002b634  cmp     ebx, 106Bh
0x18002b63a  jz      short loc_18002B65C
0x18002b63c  mov     rcx, [rsp+160h+hObject+8]; hObject
0x18002b641  call    cs:__imp_CloseHandle
0x18002b647  xor     eax, eax
0x18002b649  test    ebx, ebx
0x18002b64b  cmovz   rax, [rbp+60h+var_E0]
0x18002b650  mov     [rsi], rax
0x18002b653  jmp     loc_18002B543
0x18002b658  xor     ebx, ebx
0x18002b65a  jmp     short loc_18002B63C
0x18002b65c  mov     rax, [rsp+160h+hObject+8]
0x18002b661  jmp     loc_18002B5C5
0x18002b666  call    WmipOpenWmiDevice
0x18002b66b  mov     edx, eax
0x18002b66d  mov     ebx, eax
0x18002b66f  mov     eax, 0C0000000h
0x18002b674  and     edx, eax
0x18002b676  cmp     edx, eax
0x18002b678  jnz     loc_18002B597
0x18002b67e  mov     rcx, rdi; CriticalSection
0x18002b681  mov     cs:WmipKMHandle, 0
0x18002b68c  call    cs:__imp_RtlLeaveCriticalSection
0x18002b692  mov     ecx, ebx; Status
0x18002b694  call    cs:__imp_RtlNtStatusToDosError
0x18002b69a  jmp     short loc_18002B6A2
0x18002b69c  call    cs:__imp_GetLastError
0x18002b6a2  mov     ebx, eax
0x18002b6a4  jmp     short loc_18002B647
0x18002b6a6  mov     eax, dword ptr [rsp+160h+var_110]
0x18002b6aa  cmp     eax, 103h
0x18002b6af  jnz     loc_18002B61E
0x18002b6b5  mov     rcx, [rsp+160h+hObject+8]; Handle
0x18002b6ba  xor     r8d, r8d; Timeout
0x18002b6bd  xor     edx, edx; Alertable
0x18002b6bf  call    cs:__imp_NtWaitForSingleObject
0x18002b6c5  test    eax, eax
0x18002b6c7  jnz     loc_18002B622
0x18002b6cd  mov     eax, dword ptr [rsp+160h+var_110]
0x18002b6d1  jmp     loc_18002B61E
```
