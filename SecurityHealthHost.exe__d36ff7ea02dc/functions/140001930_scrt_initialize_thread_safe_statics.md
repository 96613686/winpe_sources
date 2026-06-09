# __scrt_initialize_thread_safe_statics

- ea: `0x140001930`
- end: `0x140001a00`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x140001710`
- `0x1400018e0`
- `0x140001930`
- `0x140001f84`

## import_xrefs

- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x140001946`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x140001946`
- `KERNEL32!CreateEventW` at `0x1400019bf`
- `KERNEL32!CreateEventW` at `0x1400019bf`
- `KERNEL32!GetModuleHandleW` at `0x140001953`
- `KERNEL32!GetModuleHandleW` at `0x140001968`
- `KERNEL32!GetModuleHandleW` at `0x140001953`
- `KERNEL32!GetModuleHandleW` at `0x140001968`
- `KERNEL32!GetProcAddress` at `0x140001980`
- `KERNEL32!GetProcAddress` at `0x140001993`
- `KERNEL32!GetProcAddress` at `0x140001980`
- `KERNEL32!GetProcAddress` at `0x140001993`

## string_xrefs

- `0x14000194c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x140001961`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_140018C60, 0xFA0u);
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
    qword_140018C88 = (__int64)ProcAddress;
    qword_140018C90 = (__int64)v2;
  }
  else
  {
    hHandle = CreateEventW(0, 1, 0, 0);
    if ( !hHandle )
      goto LABEL_9;
  }
  if ( !(unsigned __int8)_scrt_initialize_onexit_tables(0) )
LABEL_9:
    _scrt_fastfail(7u);
  atexit(_scrt_uninitialize_thread_safe_statics);
  return 0;
}

```

## disassembly

```asm
0x140001930  mov     [rsp+arg_0], rbx
0x140001935  push    rdi
0x140001936  sub     rsp, 20h
0x14000193a  mov     edx, 0FA0h; dwSpinCount
0x14000193f  lea     rcx, stru_140018C60; lpCriticalSection
0x140001946  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x14000194c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x140001953  call    cs:__imp_GetModuleHandleW
0x140001959  mov     rbx, rax
0x14000195c  test    rax, rax
0x14000195f  jnz     short loc_140001976
0x140001961  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x140001968  call    cs:__imp_GetModuleHandleW
0x14000196e  mov     rbx, rax
0x140001971  test    rax, rax
0x140001974  jz      short loc_1400019F5
0x140001976  lea     rdx, ProcName; "SleepConditionVariableCS"
0x14000197d  mov     rcx, rbx; hModule
0x140001980  call    cs:__imp_GetProcAddress
0x140001986  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x14000198d  mov     rcx, rbx; hModule
0x140001990  mov     rdi, rax
0x140001993  call    cs:__imp_GetProcAddress
0x140001999  test    rdi, rdi
0x14000199c  jz      short loc_1400019B3
0x14000199e  test    rax, rax
0x1400019a1  jz      short loc_1400019B3
0x1400019a3  mov     cs:qword_140018C88, rdi
0x1400019aa  mov     cs:qword_140018C90, rax
0x1400019b1  jmp     short loc_1400019D1
0x1400019b3  xor     r9d, r9d; lpName
0x1400019b6  xor     r8d, r8d; bInitialState
0x1400019b9  xor     ecx, ecx; lpEventAttributes
0x1400019bb  lea     edx, [r9+1]; bManualReset
0x1400019bf  call    cs:__imp_CreateEventW
0x1400019c5  mov     cs:hHandle, rax
0x1400019cc  test    rax, rax
0x1400019cf  jz      short loc_1400019F5
0x1400019d1  xor     ecx, ecx
0x1400019d3  call    __scrt_initialize_onexit_tables
0x1400019d8  test    al, al
0x1400019da  jz      short loc_1400019F5
0x1400019dc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1400019e3  call    atexit
0x1400019e8  mov     rbx, [rsp+28h+arg_0]
0x1400019ed  xor     eax, eax
0x1400019ef  add     rsp, 20h
0x1400019f3  pop     rdi
0x1400019f4  retn
0x1400019f5  mov     ecx, 7
0x1400019fa  call    __scrt_fastfail
```
