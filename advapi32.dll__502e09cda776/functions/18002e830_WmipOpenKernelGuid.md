# WmipOpenKernelGuid

- ea: `0x18002e830`
- end: `0x18002ea69`
- name: `WmipOpenKernelGuid`
- size: `569`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18002e410`
- `0x180069300`

## callees

- `0x18002e830`
- `0x18002ea70`
- `0x1800386a4`
- `0x1800720b0`

## import_xrefs

- `ntdll!NtDeviceIoControlFile` at `0x18002e970`
- `ntdll!NtDeviceIoControlFile` at `0x18002e970`
- `ntdll!NtWaitForSingleObject` at `0x18002ea4c`
- `ntdll!NtWaitForSingleObject` at `0x18002ea4c`
- `ntdll!RtlSetLastWin32Error` at `0x18002e99d`
- `ntdll!RtlSetLastWin32Error` at `0x18002e99d`
- `ntdll!RtlLeaveCriticalSection` at `0x18002e8f1`
- `ntdll!RtlLeaveCriticalSection` at `0x18002ea07`
- `ntdll!RtlLeaveCriticalSection` at `0x18002e8f1`
- `ntdll!RtlLeaveCriticalSection` at `0x18002ea07`
- `ntdll!RtlEnterCriticalSection` at `0x18002e8d4`
- `ntdll!RtlEnterCriticalSection` at `0x18002e8d4`
- `ntdll!RtlNtStatusToDosError` at `0x18002e98d`
- `ntdll!RtlNtStatusToDosError` at `0x18002ea15`
- `ntdll!RtlNtStatusToDosError` at `0x18002e98d`
- `ntdll!RtlNtStatusToDosError` at `0x18002ea15`
- `KERNEL32!GetLastError` at `0x18002ea23`
- `KERNEL32!GetLastError` at `0x18002ea23`
- `KERNEL32!CreateEventW` at `0x18002e907`
- `KERNEL32!CreateEventW` at `0x18002e907`
- `KERNEL32!CloseHandle` at `0x18002e9b6`
- `KERNEL32!CloseHandle` at `0x18002e9b6`

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
0x18002e830  push    rbp
0x18002e832  push    rbx
0x18002e833  push    rsi
0x18002e834  push    rdi
0x18002e835  push    r14
0x18002e837  lea     rbp, [rsp-40h]
0x18002e83c  sub     rsp, 140h
0x18002e843  mov     rax, cs:__security_cookie
0x18002e84a  xor     rax, rsp
0x18002e84d  mov     [rbp+60h+var_30], rax
0x18002e851  xorps   xmm0, xmm0
0x18002e854  xor     eax, eax
0x18002e856  mov     [rbp+60h+var_E0], rax
0x18002e85a  mov     r14d, r9d
0x18002e85d  lea     rax, [rbp+60h+var_90]
0x18002e861  mov     rsi, r8
0x18002e864  movups  xmmword ptr [rbp+60h+var_B8], xmm0
0x18002e868  lea     r9, [rbp+60h+var_D8]
0x18002e86c  mov     [rsp+160h+IoStatusBlock], rax
0x18002e871  lea     r8, [rbp+60h+var_C8]
0x18002e875  mov     edi, edx
0x18002e877  movups  [rsp+160h+var_F0], xmm0
0x18002e87c  movups  [rbp+60h+var_D8], xmm0
0x18002e880  movups  [rbp+60h+var_C8], xmm0
0x18002e884  movups  xmmword ptr [rbp+60h+var_B8+0Ch], xmm0
0x18002e888  call    WmipBuildGuidObjectAttributes
0x18002e88d  mov     ebx, eax
0x18002e88f  test    eax, eax
0x18002e891  jz      short loc_18002E8B0
0x18002e893  mov     eax, ebx
0x18002e895  mov     rcx, [rbp+60h+var_30]
0x18002e899  xor     rcx, rsp; StackCookie
0x18002e89c  call    __security_check_cookie
0x18002e8a1  add     rsp, 140h
0x18002e8a8  pop     r14
0x18002e8aa  pop     rdi
0x18002e8ab  pop     rsi
0x18002e8ac  pop     rbx
0x18002e8ad  pop     rbp
0x18002e8ae  retn
0x18002e8b0  xorps   xmm0, xmm0
0x18002e8b3  mov     dword ptr [rsp+160h+var_F0+8], edi
0x18002e8b7  lea     rax, [rbp+60h+var_C8]
0x18002e8bb  lea     rdi, PMCritSect
0x18002e8c2  mov     qword ptr [rsp+160h+var_F0], rax
0x18002e8c7  mov     rcx, rdi; CriticalSection
0x18002e8ca  movups  xmmword ptr [rsp+160h+var_110], xmm0
0x18002e8cf  movups  xmmword ptr [rsp+160h+hObject], xmm0
0x18002e8d4  call    cs:__imp_RtlEnterCriticalSection
0x18002e8db  nop     dword ptr [rax+rax+00h]
0x18002e8e0  cmp     cs:WmipKMHandle, 0
0x18002e8e8  jz      loc_18002E9E1
0x18002e8ee  mov     rcx, rdi; CriticalSection
0x18002e8f1  call    cs:__imp_RtlLeaveCriticalSection
0x18002e8f8  nop     dword ptr [rax+rax+00h]
0x18002e8fd  xor     r9d, r9d; lpName
0x18002e900  xor     r8d, r8d; bInitialState
0x18002e903  xor     edx, edx; bManualReset
0x18002e905  xor     ecx, ecx; lpEventAttributes
0x18002e907  call    cs:__imp_CreateEventW
0x18002e90e  nop     dword ptr [rax+rax+00h]
0x18002e913  mov     [rsp+160h+hObject+8], rax
0x18002e918  test    rax, rax
0x18002e91b  jz      loc_18002EA23
0x18002e921  mov     rdi, cs:WmipKMHandle
0x18002e928  mov     [rsp+160h+OutputBufferLength], 18h; OutputBufferLength
0x18002e930  lea     rcx, [rsp+160h+var_F0]
0x18002e935  mov     [rsp+160h+OutputBuffer], rcx; OutputBuffer
0x18002e93a  xor     r9d, r9d; ApcContext
0x18002e93d  mov     [rsp+160h+InputBufferLength], 18h; InputBufferLength
0x18002e945  lea     rcx, [rsp+160h+var_F0]
0x18002e94a  mov     [rsp+160h+InputBuffer], rcx; InputBuffer
0x18002e94f  xor     r8d, r8d; ApcRoutine
0x18002e952  lea     rcx, [rsp+160h+var_110]
0x18002e957  mov     [rsp+160h+IoControlCode], r14d; IoControlCode
0x18002e95c  mov     [rsp+160h+IoStatusBlock], rcx; IoStatusBlock
0x18002e961  mov     rdx, rax; Event
0x18002e964  mov     rcx, rdi; FileHandle
0x18002e967  mov     qword ptr [rsp+160h+var_110], 103h
0x18002e970  call    cs:__imp_NtDeviceIoControlFile
0x18002e977  nop     dword ptr [rax+rax+00h]
0x18002e97c  cmp     eax, 103h
0x18002e981  jz      loc_18002EA33
0x18002e987  test    eax, eax
0x18002e989  jz      short loc_18002E9D3
0x18002e98b  mov     ecx, eax; Status
0x18002e98d  call    cs:__imp_RtlNtStatusToDosError
0x18002e994  nop     dword ptr [rax+rax+00h]
0x18002e999  mov     ecx, eax; LastError
0x18002e99b  mov     ebx, eax
0x18002e99d  call    cs:__imp_RtlSetLastWin32Error
0x18002e9a4  nop     dword ptr [rax+rax+00h]
0x18002e9a9  cmp     ebx, 106Bh
0x18002e9af  jz      short loc_18002E9D7
0x18002e9b1  mov     rcx, [rsp+160h+hObject+8]; hObject
0x18002e9b6  call    cs:__imp_CloseHandle
0x18002e9bd  nop     dword ptr [rax+rax+00h]
0x18002e9c2  xor     eax, eax
0x18002e9c4  test    ebx, ebx
0x18002e9c6  cmovz   rax, [rbp+60h+var_E0]
0x18002e9cb  mov     [rsi], rax
0x18002e9ce  jmp     loc_18002E893
0x18002e9d3  xor     ebx, ebx
0x18002e9d5  jmp     short loc_18002E9B1
0x18002e9d7  mov     rax, [rsp+160h+hObject+8]
0x18002e9dc  jmp     loc_18002E928
0x18002e9e1  call    WmipOpenWmiDevice
0x18002e9e6  mov     edx, eax
0x18002e9e8  mov     ebx, eax
0x18002e9ea  mov     eax, 0C0000000h
0x18002e9ef  and     edx, eax
0x18002e9f1  cmp     edx, eax
0x18002e9f3  jnz     loc_18002E8EE
0x18002e9f9  mov     rcx, rdi; CriticalSection
0x18002e9fc  mov     cs:WmipKMHandle, 0
0x18002ea07  call    cs:__imp_RtlLeaveCriticalSection
0x18002ea0e  nop     dword ptr [rax+rax+00h]
0x18002ea13  mov     ecx, ebx; Status
0x18002ea15  call    cs:__imp_RtlNtStatusToDosError
0x18002ea1c  nop     dword ptr [rax+rax+00h]
0x18002ea21  jmp     short loc_18002EA2F
0x18002ea23  call    cs:__imp_GetLastError
0x18002ea2a  nop     dword ptr [rax+rax+00h]
0x18002ea2f  mov     ebx, eax
0x18002ea31  jmp     short loc_18002E9C2
0x18002ea33  mov     eax, dword ptr [rsp+160h+var_110]
0x18002ea37  cmp     eax, 103h
0x18002ea3c  jnz     loc_18002E987
0x18002ea42  mov     rcx, [rsp+160h+hObject+8]; Handle
0x18002ea47  xor     r8d, r8d; Timeout
0x18002ea4a  xor     edx, edx; Alertable
0x18002ea4c  call    cs:__imp_NtWaitForSingleObject
0x18002ea53  nop     dword ptr [rax+rax+00h]
0x18002ea58  test    eax, eax
0x18002ea5a  jnz     loc_18002E98B
0x18002ea60  mov     eax, dword ptr [rsp+160h+var_110]
0x18002ea64  jmp     loc_18002E987
```
