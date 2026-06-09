# Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::ProcessCounters(void)

- ea: `0x18002b798`
- end: `0x18002b90f`
- name: `??0ProcessCounters@StandardCollector@DiagnosticsHub@Microsoft@@QEAA@XZ`
- size: `375`
- prototype: `__int64 __fastcall(Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180013908`

## callees

- `0x1800084d0`
- `0x18002b798`
- `0x180049b50`
- `0x18004a03c`
- `0x18004a088`

## import_xrefs

- `KERNEL32!GetSystemInfo` at `0x18002b8e6`
- `KERNEL32!GetSystemInfo` at `0x18002b8e6`
- `KERNEL32!LoadLibraryExW` at `0x18002b893`
- `KERNEL32!LoadLibraryExW` at `0x18002b893`
- `KERNEL32!InitializeCriticalSection` at `0x18002b7f3`
- `KERNEL32!InitializeCriticalSection` at `0x18002b83a`
- `KERNEL32!InitializeCriticalSection` at `0x18002b7f3`
- `KERNEL32!InitializeCriticalSection` at `0x18002b83a`
- `KERNEL32!GetLastError` at `0x18002b8c1`
- `KERNEL32!GetLastError` at `0x18002b8c1`
- `KERNEL32!GetProcAddress` at `0x18002b8af`
- `KERNEL32!GetProcAddress` at `0x18002b8af`

## string_xrefs

- `0x18002b88c`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters *__fastcall Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::ProcessCounters(
        Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters *this)
{
  _QWORD *v2; // rax
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  _SYSTEM_INFO SystemInfo; // [rsp+40h] [rbp-48h] BYREF

  *(_DWORD *)this = -1;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_BYTE *)this + 24) = 0;
  DiagHubCommon::HubTask<long,0>::HubTask<long,0>((char *)this + 32);
  *((_OWORD *)this + 9) = 0;
  *((_OWORD *)this + 10) = 0;
  *((_QWORD *)this + 22) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
  `eh vector constructor iterator'(
    (char *)this + 184,
    0x48u,
    4u,
    (void (*)(void *))Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::CounterData::CounterData,
    (void (*)(void *))Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::CounterData::~CounterData);
  *(_OWORD *)((char *)this + 472) = 0;
  *(_OWORD *)((char *)this + 488) = 0;
  *((_QWORD *)this + 63) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 472));
  *((_QWORD *)this + 64) = 0;
  *((_QWORD *)this + 65) = 0;
  v2 = operator new(0x20u);
  *v2 = v2;
  v2[1] = v2;
  *((_QWORD *)this + 64) = v2;
  *((_QWORD *)this + 66) = 0;
  *((_DWORD *)this + 134) = 0;
  Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
  *((_QWORD *)this + 68) = Library;
  if ( !Library
    || (ProcAddress = GetProcAddress(Library, "NtQuerySystemInformation"), (*((_QWORD *)this + 66) = ProcAddress) == 0) )
  {
    *((_DWORD *)this + 134) = GetLastError();
  }
  *((_DWORD *)this + 138) = 0;
  *((_DWORD *)this + 139) = 100;
  GetSystemInfo(&SystemInfo);
  *((_DWORD *)this + 138) = SystemInfo.dwNumberOfProcessors;
  return this;
}

```

## disassembly

```asm
0x18002b798  push    rbx
0x18002b79a  sub     rsp, 80h
0x18002b7a1  mov     rax, cs:__security_cookie
0x18002b7a8  xor     rax, rsp
0x18002b7ab  mov     [rsp+88h+var_18], rax
0x18002b7b0  mov     rbx, rcx
0x18002b7b3  mov     [rsp+88h+var_58], rcx
0x18002b7b8  mov     dword ptr [rcx], 0FFFFFFFFh
0x18002b7be  mov     qword ptr [rcx+8], 0
0x18002b7c6  mov     qword ptr [rcx+10h], 0
0x18002b7ce  mov     byte ptr [rcx+18h], 0
0x18002b7d2  add     rcx, 20h ; ' '
0x18002b7d6  call    ??0?$HubTask@J$0A@@DiagHubCommon@@QEAA@XZ; DiagHubCommon::HubTask<long,0>::HubTask<long,0>(void)
0x18002b7db  nop
0x18002b7dc  lea     rcx, [rbx+90h]; lpCriticalSection
0x18002b7e3  xorps   xmm0, xmm0
0x18002b7e6  xor     eax, eax
0x18002b7e8  movups  xmmword ptr [rcx], xmm0
0x18002b7eb  movups  xmmword ptr [rcx+10h], xmm0
0x18002b7ef  mov     [rcx+20h], rax
0x18002b7f3  call    cs:__imp_InitializeCriticalSection
0x18002b7f9  nop
0x18002b7fa  lea     rcx, [rbx+0B8h]; void *
0x18002b801  lea     rax, ??1CounterData@ProcessCounters@StandardCollector@DiagnosticsHub@Microsoft@@QEAA@XZ; Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::CounterData::~CounterData(void)
0x18002b808  mov     [rsp+88h+var_68], rax; void (*)(void *)
0x18002b80d  lea     r9, ??0CounterData@ProcessCounters@StandardCollector@DiagnosticsHub@Microsoft@@QEAA@XZ; void (*)(void *)
0x18002b814  mov     edx, 48h ; 'H'; unsigned __int64
0x18002b819  lea     r8d, [rdx-44h]; unsigned __int64
0x18002b81d  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18002b822  nop
0x18002b823  lea     rcx, [rbx+1D8h]; lpCriticalSection
0x18002b82a  xorps   xmm0, xmm0
0x18002b82d  xor     eax, eax
0x18002b82f  movups  xmmword ptr [rcx], xmm0
0x18002b832  movups  xmmword ptr [rcx+10h], xmm0
0x18002b836  mov     [rcx+20h], rax
0x18002b83a  call    cs:__imp_InitializeCriticalSection
0x18002b840  nop
0x18002b841  mov     qword ptr [rbx+200h], 0
0x18002b84c  mov     qword ptr [rbx+208h], 0
0x18002b857  mov     ecx, 20h ; ' '; Size
0x18002b85c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002b861  mov     [rax], rax
0x18002b864  mov     [rax+8], rax
0x18002b868  mov     [rbx+200h], rax
0x18002b86f  mov     qword ptr [rbx+210h], 0
0x18002b87a  mov     dword ptr [rbx+218h], 0
0x18002b884  xor     edx, edx; hFile
0x18002b886  mov     r8d, 800h; dwFlags
0x18002b88c  lea     rcx, aNtdllDll; "ntdll.dll"
0x18002b893  call    cs:__imp_LoadLibraryExW
0x18002b899  mov     [rbx+220h], rax
0x18002b8a0  test    rax, rax
0x18002b8a3  jz      short loc_18002B8C1
0x18002b8a5  lea     rdx, aNtquerysystemi; "NtQuerySystemInformation"
0x18002b8ac  mov     rcx, rax; hModule
0x18002b8af  call    cs:__imp_GetProcAddress
0x18002b8b5  mov     [rbx+210h], rax
0x18002b8bc  test    rax, rax
0x18002b8bf  jnz     short loc_18002B8CD
0x18002b8c1  call    cs:__imp_GetLastError
0x18002b8c7  mov     [rbx+218h], eax
0x18002b8cd  mov     dword ptr [rbx+228h], 0
0x18002b8d7  mov     dword ptr [rbx+22Ch], 64h ; 'd'
0x18002b8e1  lea     rcx, [rsp+88h+SystemInfo]; lpSystemInfo
0x18002b8e6  call    cs:__imp_GetSystemInfo
0x18002b8ec  mov     ecx, [rsp+88h+SystemInfo.dwNumberOfProcessors]
0x18002b8f0  mov     [rbx+228h], ecx
0x18002b8f6  mov     rax, rbx
0x18002b8f9  mov     rcx, [rsp+88h+var_18]
0x18002b8fe  xor     rcx, rsp; StackCookie
0x18002b901  call    __security_check_cookie
0x18002b906  add     rsp, 80h
0x18002b90d  pop     rbx
0x18002b90e  retn
```
