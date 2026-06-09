# __scrt_initialize_thread_safe_statics

- ea: `0x18000d490`
- end: `0x18000d560`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18000d270`
- `0x18000d420`
- `0x18000d490`
- `0x18000dc48`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000d4e0`
- `KERNEL32!GetProcAddress` at `0x18000d4f3`
- `KERNEL32!GetProcAddress` at `0x18000d4e0`
- `KERNEL32!GetProcAddress` at `0x18000d4f3`
- `KERNEL32!GetModuleHandleW` at `0x18000d4b3`
- `KERNEL32!GetModuleHandleW` at `0x18000d4c8`
- `KERNEL32!GetModuleHandleW` at `0x18000d4b3`
- `KERNEL32!GetModuleHandleW` at `0x18000d4c8`
- `KERNEL32!CreateEventW` at `0x18000d51f`
- `KERNEL32!CreateEventW` at `0x18000d51f`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x18000d4a6`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x18000d4a6`

## string_xrefs

- `0x18000d4ac`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x18000d4c1`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_1800188E8, 0xFA0u);
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
    qword_180018910 = (__int64)ProcAddress;
    qword_180018918 = (__int64)v2;
  }
  else
  {
    hHandle = CreateEventW(0, 1, 0, 0);
    if ( !hHandle )
      goto LABEL_9;
  }
  if ( !(unsigned __int8)_scrt_initialize_onexit_tables(0) )
  {
LABEL_9:
    _scrt_fastfail(7);
    __debugbreak();
  }
  atexit(_scrt_uninitialize_thread_safe_statics);
  return 0;
}

```

## disassembly

```asm
0x18000d490  mov     [rsp+arg_0], rbx
0x18000d495  push    rdi
0x18000d496  sub     rsp, 20h
0x18000d49a  mov     edx, 0FA0h; dwSpinCount
0x18000d49f  lea     rcx, stru_1800188E8; lpCriticalSection
0x18000d4a6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000d4ac  lea     rcx, aApiMsWinCoreSy
0x18000d4b3  call    cs:__imp_GetModuleHandleW
0x18000d4b9  mov     rbx, rax
0x18000d4bc  test    rax, rax
0x18000d4bf  jnz     short loc_18000D4D6
0x18000d4c1  lea     rcx, aKernel32Dll_0
0x18000d4c8  call    cs:__imp_GetModuleHandleW
0x18000d4ce  mov     rbx, rax
0x18000d4d1  test    rax, rax
0x18000d4d4  jz      short loc_18000D555
0x18000d4d6  lea     rdx, aSleepcondition
0x18000d4dd  mov     rcx, rbx; hModule
0x18000d4e0  call    cs:__imp_GetProcAddress
0x18000d4e6  lea     rdx, aWakeallconditi
0x18000d4ed  mov     rcx, rbx; hModule
0x18000d4f0  mov     rdi, rax
0x18000d4f3  call    cs:__imp_GetProcAddress
0x18000d4f9  test    rdi, rdi
0x18000d4fc  jz      short loc_18000D513
0x18000d4fe  test    rax, rax
0x18000d501  jz      short loc_18000D513
0x18000d503  mov     cs:qword_180018910, rdi
0x18000d50a  mov     cs:qword_180018918, rax
0x18000d511  jmp     short loc_18000D531
0x18000d513  xor     r9d, r9d; lpName
0x18000d516  xor     r8d, r8d; bInitialState
0x18000d519  xor     ecx, ecx; lpEventAttributes
0x18000d51b  lea     edx, [r9+1]; bManualReset
0x18000d51f  call    cs:__imp_CreateEventW
0x18000d525  mov     cs:hHandle, rax
0x18000d52c  test    rax, rax
0x18000d52f  jz      short loc_18000D555
0x18000d531  xor     ecx, ecx
0x18000d533  call    __scrt_initialize_onexit_tables
0x18000d538  test    al, al
0x18000d53a  jz      short loc_18000D555
0x18000d53c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x18000d543  call    atexit
0x18000d548  mov     rbx, [rsp+28h+arg_0]
0x18000d54d  xor     eax, eax
0x18000d54f  add     rsp, 20h
0x18000d553  pop     rdi
0x18000d554  retn
0x18000d555  mov     ecx, 7
0x18000d55a  call    __scrt_fastfail
0x18000d55f  int     3; Trap to Debugger
```
