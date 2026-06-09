# __scrt_initialize_thread_safe_statics

- ea: `0x180007690`
- end: `0x180007760`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180007690`
- `0x180007bd0`
- `0x180007da0`
- `0x180008314`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800076e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800076f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800076e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800076f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800076b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800076c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800076b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800076c8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800076a6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800076a6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000771f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000771f`

## string_xrefs

- `0x1800076ac`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800076c1`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_180095428, 0xFA0u);
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
    qword_180095450 = (__int64)ProcAddress;
    qword_180095458 = (__int64)v2;
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
0x180007690  mov     [rsp+arg_0], rbx
0x180007695  push    rdi
0x180007696  sub     rsp, 20h
0x18000769a  mov     edx, 0FA0h; dwSpinCount
0x18000769f  lea     rcx, stru_180095428; lpCriticalSection
0x1800076a6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800076ac  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x1800076b3  call    cs:__imp_GetModuleHandleW
0x1800076b9  mov     rbx, rax
0x1800076bc  test    rax, rax
0x1800076bf  jnz     short loc_1800076D6
0x1800076c1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800076c8  call    cs:__imp_GetModuleHandleW
0x1800076ce  mov     rbx, rax
0x1800076d1  test    rax, rax
0x1800076d4  jz      short loc_180007755
0x1800076d6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x1800076dd  mov     rcx, rbx; hModule
0x1800076e0  call    cs:__imp_GetProcAddress
0x1800076e6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800076ed  mov     rcx, rbx; hModule
0x1800076f0  mov     rdi, rax
0x1800076f3  call    cs:__imp_GetProcAddress
0x1800076f9  test    rdi, rdi
0x1800076fc  jz      short loc_180007713
0x1800076fe  test    rax, rax
0x180007701  jz      short loc_180007713
0x180007703  mov     cs:qword_180095450, rdi
0x18000770a  mov     cs:qword_180095458, rax
0x180007711  jmp     short loc_180007731
0x180007713  xor     r9d, r9d; lpName
0x180007716  xor     r8d, r8d; bInitialState
0x180007719  xor     ecx, ecx; lpEventAttributes
0x18000771b  lea     edx, [r9+1]; bManualReset
0x18000771f  call    cs:__imp_CreateEventW
0x180007725  mov     cs:hHandle, rax
0x18000772c  test    rax, rax
0x18000772f  jz      short loc_180007755
0x180007731  xor     ecx, ecx
0x180007733  call    __scrt_initialize_onexit_tables
0x180007738  test    al, al
0x18000773a  jz      short loc_180007755
0x18000773c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180007743  call    atexit
0x180007748  mov     rbx, [rsp+28h+arg_0]
0x18000774d  xor     eax, eax
0x18000774f  add     rsp, 20h
0x180007753  pop     rdi
0x180007754  retn
0x180007755  mov     ecx, 7
0x18000775a  call    __scrt_fastfail
```
