# __scrt_initialize_thread_safe_statics

- ea: `0x180001960`
- end: `0x180001a30`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001768`
- `0x180001938`
- `0x180001960`
- `0x180001d08`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180001983`
- `KERNEL32!GetModuleHandleW` at `0x180001998`
- `KERNEL32!GetModuleHandleW` at `0x180001983`
- `KERNEL32!GetModuleHandleW` at `0x180001998`
- `KERNEL32!CreateEventW` at `0x1800019ef`
- `KERNEL32!CreateEventW` at `0x1800019ef`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180001976`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180001976`
- `KERNEL32!GetProcAddress` at `0x1800019b0`
- `KERNEL32!GetProcAddress` at `0x1800019c3`
- `KERNEL32!GetProcAddress` at `0x1800019b0`
- `KERNEL32!GetProcAddress` at `0x1800019c3`

## string_xrefs

- `0x18000197c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180001991`: `kernel32.dll`

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
    qword_18000D270 = (__int64)ProcAddress;
    qword_18000D278 = (__int64)v2;
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
0x180001960  mov     [rsp+arg_0], rbx
0x180001965  push    rdi
0x180001966  sub     rsp, 20h
0x18000196a  mov     edx, 0FA0h; dwSpinCount
0x18000196f  lea     rcx, CriticalSection; lpCriticalSection
0x180001976  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000197c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180001983  call    cs:__imp_GetModuleHandleW
0x180001989  mov     rbx, rax
0x18000198c  test    rax, rax
0x18000198f  jnz     short loc_1800019A6
0x180001991  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x180001998  call    cs:__imp_GetModuleHandleW
0x18000199e  mov     rbx, rax
0x1800019a1  test    rax, rax
0x1800019a4  jz      short loc_180001A25
0x1800019a6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x1800019ad  mov     rcx, rbx; hModule
0x1800019b0  call    cs:__imp_GetProcAddress
0x1800019b6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800019bd  mov     rcx, rbx; hModule
0x1800019c0  mov     rdi, rax
0x1800019c3  call    cs:__imp_GetProcAddress
0x1800019c9  test    rdi, rdi
0x1800019cc  jz      short loc_1800019E3
0x1800019ce  test    rax, rax
0x1800019d1  jz      short loc_1800019E3
0x1800019d3  mov     cs:qword_18000D270, rdi
0x1800019da  mov     cs:qword_18000D278, rax
0x1800019e1  jmp     short loc_180001A01
0x1800019e3  xor     r9d, r9d; lpName
0x1800019e6  xor     r8d, r8d; bInitialState
0x1800019e9  xor     ecx, ecx; lpEventAttributes
0x1800019eb  lea     edx, [r9+1]; bManualReset
0x1800019ef  call    cs:__imp_CreateEventW
0x1800019f5  mov     cs:hHandle, rax
0x1800019fc  test    rax, rax
0x1800019ff  jz      short loc_180001A25
0x180001a01  xor     ecx, ecx
0x180001a03  call    __scrt_initialize_onexit_tables
0x180001a08  test    al, al
0x180001a0a  jz      short loc_180001A25
0x180001a0c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180001a13  call    atexit
0x180001a18  mov     rbx, [rsp+28h+arg_0]
0x180001a1d  xor     eax, eax
0x180001a1f  add     rsp, 20h
0x180001a23  pop     rdi
0x180001a24  retn
0x180001a25  mov     ecx, 7
0x180001a2a  call    __scrt_fastfail
```
