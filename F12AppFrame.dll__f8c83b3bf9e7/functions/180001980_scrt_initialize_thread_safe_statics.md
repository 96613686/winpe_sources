# __scrt_initialize_thread_safe_statics

- ea: `0x180001980`
- end: `0x180001a50`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001980`
- `0x180001e4c`
- `0x18000201c`
- `0x18000219c`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x180001a0f`
- `KERNEL32!CreateEventW` at `0x180001a0f`
- `KERNEL32!GetProcAddress` at `0x1800019d0`
- `KERNEL32!GetProcAddress` at `0x1800019e3`
- `KERNEL32!GetProcAddress` at `0x1800019d0`
- `KERNEL32!GetProcAddress` at `0x1800019e3`
- `KERNEL32!GetModuleHandleW` at `0x1800019a3`
- `KERNEL32!GetModuleHandleW` at `0x1800019b8`
- `KERNEL32!GetModuleHandleW` at `0x1800019a3`
- `KERNEL32!GetModuleHandleW` at `0x1800019b8`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180001996`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180001996`

## string_xrefs

- `0x18000199c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800019b1`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&CriticalSection, 0xFA0u);
  ModuleHandleW = GetModuleHandleW(L"api-ms-win-core-synch-l1-2-0.dll");
  if ( !ModuleHandleW )
  {
    ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
    if ( !ModuleHandleW )
      goto LABEL_9;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "SleepConditionVariableCS");
  v2 = GetProcAddress(ModuleHandleW, "WakeAllConditionVariable");
  if ( ProcAddress && v2 )
  {
    qword_180050450 = (__int64)ProcAddress;
    qword_180050458 = (__int64)v2;
  }
  else
  {
    hHandle = CreateEventW(0, 1, 0, 0);
    if ( !hHandle )
      goto LABEL_9;
  }
  if ( !(unsigned __int8)_scrt_initialize_onexit_tables(0) )
LABEL_9:
    _scrt_fastfail(7);
  atexit(_scrt_uninitialize_thread_safe_statics);
  return 0;
}

```

## disassembly

```asm
0x180001980  mov     [rsp+arg_0], rbx
0x180001985  push    rdi
0x180001986  sub     rsp, 20h
0x18000198a  mov     edx, 0FA0h; dwSpinCount
0x18000198f  lea     rcx, CriticalSection; lpCriticalSection
0x180001996  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000199c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x1800019a3  call    cs:__imp_GetModuleHandleW
0x1800019a9  mov     rbx, rax
0x1800019ac  test    rax, rax
0x1800019af  jnz     short loc_1800019C6
0x1800019b1  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x1800019b8  call    cs:__imp_GetModuleHandleW
0x1800019be  mov     rbx, rax
0x1800019c1  test    rax, rax
0x1800019c4  jz      short loc_180001A45
0x1800019c6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x1800019cd  mov     rcx, rbx; hModule
0x1800019d0  call    cs:__imp_GetProcAddress
0x1800019d6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800019dd  mov     rcx, rbx; hModule
0x1800019e0  mov     rdi, rax
0x1800019e3  call    cs:__imp_GetProcAddress
0x1800019e9  test    rdi, rdi
0x1800019ec  jz      short loc_180001A03
0x1800019ee  test    rax, rax
0x1800019f1  jz      short loc_180001A03
0x1800019f3  mov     cs:qword_180050450, rdi
0x1800019fa  mov     cs:qword_180050458, rax
0x180001a01  jmp     short loc_180001A21
0x180001a03  xor     r9d, r9d; lpName
0x180001a06  xor     r8d, r8d; bInitialState
0x180001a09  xor     ecx, ecx; lpEventAttributes
0x180001a0b  lea     edx, [r9+1]; bManualReset
0x180001a0f  call    cs:__imp_CreateEventW
0x180001a15  mov     cs:hHandle, rax
0x180001a1c  test    rax, rax
0x180001a1f  jz      short loc_180001A45
0x180001a21  xor     ecx, ecx
0x180001a23  call    __scrt_initialize_onexit_tables
0x180001a28  test    al, al
0x180001a2a  jz      short loc_180001A45
0x180001a2c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180001a33  call    atexit
0x180001a38  mov     rbx, [rsp+28h+arg_0]
0x180001a3d  xor     eax, eax
0x180001a3f  add     rsp, 20h
0x180001a43  pop     rdi
0x180001a44  retn
0x180001a45  mov     ecx, 7
0x180001a4a  call    __scrt_fastfail
```
