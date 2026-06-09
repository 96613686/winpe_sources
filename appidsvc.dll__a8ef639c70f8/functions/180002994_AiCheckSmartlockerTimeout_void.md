# AiCheckSmartlockerTimeout(void)

- ea: `0x180002994`
- end: `0x180002c2d`
- name: `?AiCheckSmartlockerTimeout@@YAXXZ`
- size: `665`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180003c80`

## callees

- `0x180002994`
- `0x18000880c`
- `0x180008bcc`
- `0x18000c0e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002b61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002b8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002bfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002b61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002b8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002bfd`
- `ntdll!RtlFreeHeap` at `0x180002a3a`
- `ntdll!RtlFreeHeap` at `0x180002ab0`
- `ntdll!RtlFreeHeap` at `0x180002a3a`
- `ntdll!RtlFreeHeap` at `0x180002ab0`
- `ntdll!NtQueryValueKey` at `0x180002a6d`
- `ntdll!NtQueryValueKey` at `0x180002a6d`
- `ntdll!NtClose` at `0x180002abf`
- `ntdll!NtClose` at `0x180002b41`
- `ntdll!NtClose` at `0x180002abf`
- `ntdll!NtClose` at `0x180002b41`
- `ntdll!NtSetValueKey` at `0x180002b32`
- `ntdll!NtSetValueKey` at `0x180002b32`
- `ntdll!NtQuerySystemTime` at `0x180002ad1`
- `ntdll!NtQuerySystemTime` at `0x180002ad1`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180002c06`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180002c0f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180002c06`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180002c0f`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180002b7c`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180002b7c`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180002b53`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180002b53`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180002be0`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180002be0`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180002bf3`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180002bf3`

## string_xrefs

- `0x1800029be`: `\REGISTRY\MACHINE\System\CurrentControlSet\Control\AppID\Configuration\SMARTLOCKER`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall AiCheckSmartlockerTimeout(__int64 a1)
{
  union _LARGE_INTEGER v1; // rsi
  __int64 v2; // rbx
  NTSTATUS v3; // edi
  ULONG Length; // edi
  NTSTATUS v5; // eax
  __int64 v6; // rcx
  SC_HANDLE v7; // rax
  SC_HANDLE v8; // rdi
  SC_HANDLE v9; // rax
  SC_HANDLE v10; // rbx
  HANDLE KeyHandle; // [rsp+60h] [rbp-39h] BYREF
  ULONG Data[2]; // [rsp+68h] [rbp-31h] BYREF
  union _LARGE_INTEGER SystemTime; // [rsp+70h] [rbp-29h] BYREF
  struct _UNICODE_STRING v14; // [rsp+78h] [rbp-21h] BYREF
  _UNICODE_STRING ValueName; // [rsp+88h] [rbp-11h] BYREF
  struct _UNICODE_STRING v16; // [rsp+98h] [rbp-1h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+A8h] [rbp+Fh] BYREF

  *(_QWORD *)&v14.Length = 10879140;
  *(_QWORD *)&ValueName.Length = 1048590;
  v14.Buffer = L"\\REGISTRY\\MACHINE\\System\\CurrentControlSet\\Control\\AppID\\Configuration\\SMARTLOCKER";
  *(_QWORD *)&v16.Length = 1048590;
  ValueName.Buffer = L"TIMEOUT";
  Data[0] = 48;
  v16.Buffer = L"ENABLED";
  v1.QuadPart = 0;
  SystemTime.QuadPart = 0;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  KeyHandle = 0;
  v2 = 0;
  v3 = AiRegOpenKey(a1, &v14, 0x20019u, &KeyHandle);
  if ( v3 >= 0 )
  {
    do
    {
      Length = Data[0];
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)v2);
      v2 = AiAlloc(Length);
      if ( !v2 )
      {
        v3 = -1073741801;
        goto LABEL_10;
      }
      v5 = NtQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, (PVOID)v2, Length, Data);
      v3 = v5;
    }
    while ( v5 == -2147483643 );
    if ( v5 >= 0 )
    {
      if ( *(_DWORD *)(v2 + 4) == 11 && *(_DWORD *)(v2 + 8) == 8 )
        v1 = *(union _LARGE_INTEGER *)(v2 + 12);
      else
        v3 = -1073741788;
    }
  }
LABEL_10:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)v2);
  if ( KeyHandle )
    NtClose(KeyHandle);
  if ( v3 >= 0 && NtQuerySystemTime(&SystemTime) >= 0 && v1.QuadPart < (unsigned __int64)SystemTime.QuadPart )
  {
    *(_QWORD *)Data = 0;
    KeyHandle = 0;
    if ( AiRegOpenKey(v6, &v14, 0x20006u, &KeyHandle) >= 0 )
      NtSetValueKey(KeyHandle, &v16, 0, 0xBu, Data, 8u);
    if ( KeyHandle )
      NtClose(KeyHandle);
    v7 = OpenSCManagerW(0, 0, 1u);
    v8 = v7;
    if ( v7 )
    {
      v9 = OpenServiceW(v7, L"applockerfltr", 0x32u);
      v10 = v9;
      if ( v9 )
      {
        if ( !ChangeServiceConfigW(v9, 0xFFFFFFFF, 3u, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0)
          || !ControlService(v10, 1u, &ServiceStatus) )
        {
          GetLastError();
        }
        CloseServiceHandle(v10);
      }
      else
      {
        GetLastError();
      }
      CloseServiceHandle(v8);
    }
    else
    {
      GetLastError();
    }
  }
}

```

## disassembly

```asm
0x180002994  push    rbp
0x180002996  push    rbx
0x180002997  push    rsi
0x180002998  push    rdi
0x180002999  lea     rbp, [rsp-3Fh]
0x18000299e  sub     rsp, 0D8h
0x1800029a5  mov     rax, cs:__security_cookie
0x1800029ac  xor     rax, rsp
0x1800029af  mov     [rbp+57h+var_28], rax
0x1800029b3  xorps   xmm0, xmm0
0x1800029b6  mov     [rbp+57h+var_78], 0A600A4h
0x1800029be  lea     rax, aRegistryMachin; "\\REGISTRY\\MACHINE\\System\\CurrentCon"...
0x1800029c5  mov     qword ptr [rbp+57h+ValueName.Length], 10000Eh
0x1800029cd  mov     [rbp+57h+var_70], rax
0x1800029d1  lea     r9, [rbp+57h+KeyHandle]
0x1800029d5  lea     rax, aTimeout; "TIMEOUT"
0x1800029dc  mov     qword ptr [rbp+57h+var_58.Length], 10000Eh
0x1800029e4  mov     [rbp+57h+ValueName.Buffer], rax
0x1800029e8  lea     rdx, [rbp+57h+var_78]
0x1800029ec  lea     rax, aEnabled; "ENABLED"
0x1800029f3  mov     [rbp+57h+Data], 30h ; '0'
0x1800029fa  mov     [rbp+57h+var_58.Buffer], rax
0x1800029fe  xor     esi, esi
0x180002a00  xor     eax, eax
0x180002a02  mov     qword ptr [rbp+57h+SystemTime], rsi
0x180002a06  movups  xmmword ptr [rbp+57h+ServiceStatus.dwServiceType], xmm0
0x180002a0a  mov     r8d, 20019h
0x180002a10  mov     [rbp+57h+KeyHandle], rax
0x180002a14  movups  xmmword ptr [rbp+57h+ServiceStatus.dwWin32ExitCode], xmm0
0x180002a18  xor     ebx, ebx
0x180002a1a  call    AiRegOpenKey
0x180002a1f  mov     edi, eax
0x180002a21  test    eax, eax
0x180002a23  js      short loc_180002A9E
0x180002a25  mov     rcx, gs:60h
0x180002a2e  mov     r8, rbx; P
0x180002a31  mov     edi, [rbp+57h+Data]
0x180002a34  xor     edx, edx; Flags
0x180002a36  mov     rcx, [rcx+30h]; HeapHandle
0x180002a3a  call    cs:__imp_RtlFreeHeap
0x180002a40  mov     ecx, edi
0x180002a42  call    AiAlloc
0x180002a47  mov     rbx, rax
0x180002a4a  test    rax, rax
0x180002a4d  jz      short loc_180002A99
0x180002a4f  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180002a53  lea     rax, [rbp+57h+Data]
0x180002a57  mov     [rsp+0F0h+ResultLength], rax; ResultLength
0x180002a5c  lea     rdx, [rbp+57h+ValueName]; ValueName
0x180002a60  mov     r9, rbx; KeyValueInformation
0x180002a63  mov     [rsp+0F0h+Length], edi; Length
0x180002a67  mov     r8d, 2; KeyValueInformationClass
0x180002a6d  call    cs:__imp_NtQueryValueKey
0x180002a73  mov     edi, eax
0x180002a75  cmp     eax, 80000005h
0x180002a7a  jz      short loc_180002A25
0x180002a7c  test    eax, eax
0x180002a7e  js      short loc_180002A9E
0x180002a80  cmp     dword ptr [rbx+4], 0Bh
0x180002a84  jnz     short loc_180002A92
0x180002a86  cmp     dword ptr [rbx+8], 8
0x180002a8a  jnz     short loc_180002A92
0x180002a8c  mov     rsi, [rbx+0Ch]
0x180002a90  jmp     short loc_180002A9E
0x180002a92  mov     edi, 0C0000024h
0x180002a97  jmp     short loc_180002A9E
0x180002a99  mov     edi, 0C0000017h
0x180002a9e  mov     rcx, gs:60h
0x180002aa7  mov     r8, rbx; P
0x180002aaa  xor     edx, edx; Flags
0x180002aac  mov     rcx, [rcx+30h]; HeapHandle
0x180002ab0  call    cs:__imp_RtlFreeHeap
0x180002ab6  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x180002aba  test    rcx, rcx
0x180002abd  jz      short loc_180002AC5
0x180002abf  call    cs:__imp_NtClose
0x180002ac5  test    edi, edi
0x180002ac7  js      loc_180002C15
0x180002acd  lea     rcx, [rbp+57h+SystemTime]; SystemTime
0x180002ad1  call    cs:__imp_NtQuerySystemTime
0x180002ad7  test    eax, eax
0x180002ad9  js      loc_180002C15
0x180002adf  cmp     rsi, qword ptr [rbp+57h+SystemTime]
0x180002ae3  jnb     loc_180002C15
0x180002ae9  lea     r9, [rbp+57h+KeyHandle]
0x180002aed  mov     qword ptr [rbp+57h+Data], 0
0x180002af5  mov     r8d, 20006h
0x180002afb  mov     [rbp+57h+KeyHandle], 0
0x180002b03  lea     rdx, [rbp+57h+var_78]
0x180002b07  call    AiRegOpenKey
0x180002b0c  test    eax, eax
0x180002b0e  js      short loc_180002B38
0x180002b10  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180002b14  lea     rax, [rbp+57h+Data]
0x180002b18  mov     dword ptr [rsp+0F0h+ResultLength], 8; DataSize
0x180002b20  lea     rdx, [rbp+57h+var_58]; ValueName
0x180002b24  mov     r9d, 0Bh; Type
0x180002b2a  mov     qword ptr [rsp+0F0h+Length], rax; Data
0x180002b2f  xor     r8d, r8d; TitleIndex
0x180002b32  call    cs:__imp_NtSetValueKey
0x180002b38  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x180002b3c  test    rcx, rcx
0x180002b3f  jz      short loc_180002B47
0x180002b41  call    cs:__imp_NtClose
0x180002b47  mov     esi, 1
0x180002b4c  xor     edx, edx; lpDatabaseName
0x180002b4e  mov     r8d, esi; dwDesiredAccess
0x180002b51  xor     ecx, ecx; lpMachineName
0x180002b53  call    cs:__imp_OpenSCManagerW
0x180002b59  mov     rdi, rax
0x180002b5c  test    rax, rax
0x180002b5f  jnz     short loc_180002B6C
0x180002b61  call    cs:__imp_GetLastError
0x180002b67  jmp     loc_180002C15
0x180002b6c  mov     r8d, 32h ; '2'; dwDesiredAccess
0x180002b72  lea     rdx, ServiceName; "applockerfltr"
0x180002b79  mov     rcx, rdi; hSCManager
0x180002b7c  call    cs:__imp_OpenServiceW
0x180002b82  mov     rbx, rax
0x180002b85  test    rax, rax
0x180002b88  jnz     short loc_180002B92
0x180002b8a  call    cs:__imp_GetLastError
0x180002b90  jmp     short loc_180002C0C
0x180002b92  mov     [rsp+0F0h+lpDisplayName], 0; lpDisplayName
0x180002b9b  or      edx, 0FFFFFFFFh; dwServiceType
0x180002b9e  mov     [rsp+0F0h+lpPassword], 0; lpPassword
0x180002ba7  mov     r9d, edx; dwErrorControl
0x180002baa  mov     [rsp+0F0h+lpServiceStartName], 0; lpServiceStartName
0x180002bb3  mov     r8d, 3; dwStartType
0x180002bb9  mov     [rsp+0F0h+lpDependencies], 0; lpDependencies
0x180002bc2  mov     rcx, rbx; hService
0x180002bc5  mov     [rsp+0F0h+lpdwTagId], 0; lpdwTagId
0x180002bce  mov     [rsp+0F0h+ResultLength], 0; lpLoadOrderGroup
0x180002bd7  mov     qword ptr [rsp+0F0h+Length], 0; lpBinaryPathName
0x180002be0  call    cs:__imp_ChangeServiceConfigW
0x180002be6  test    eax, eax
0x180002be8  jz      short loc_180002BFD
0x180002bea  lea     r8, [rbp+57h+ServiceStatus]; lpServiceStatus
0x180002bee  mov     edx, esi; dwControl
0x180002bf0  mov     rcx, rbx; hService
0x180002bf3  call    cs:__imp_ControlService
0x180002bf9  test    eax, eax
0x180002bfb  jnz     short loc_180002C03
0x180002bfd  call    cs:__imp_GetLastError
0x180002c03  mov     rcx, rbx; hSCObject
0x180002c06  call    cs:__imp_CloseServiceHandle
0x180002c0c  mov     rcx, rdi; hSCObject
0x180002c0f  call    cs:__imp_CloseServiceHandle
0x180002c15  mov     rcx, [rbp+57h+var_28]
0x180002c19  xor     rcx, rsp; StackCookie
0x180002c1c  call    __security_check_cookie
0x180002c21  add     rsp, 0D8h
0x180002c28  pop     rdi
0x180002c29  pop     rsi
0x180002c2a  pop     rbx
0x180002c2b  pop     rbp
0x180002c2c  retn
```
