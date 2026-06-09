# __scrt_initialize_thread_safe_statics

- ea: `0x1800097c0`
- end: `0x180009890`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180008a54`
- `0x180008c24`
- `0x1800090e0`
- `0x1800097c0`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x18000984f`
- `KERNEL32!CreateEventW` at `0x18000984f`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x1800097d6`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x1800097d6`
- `KERNEL32!GetModuleHandleW` at `0x1800097e3`
- `KERNEL32!GetModuleHandleW` at `0x1800097f8`
- `KERNEL32!GetModuleHandleW` at `0x1800097e3`
- `KERNEL32!GetModuleHandleW` at `0x1800097f8`
- `KERNEL32!GetProcAddress` at `0x180009810`
- `KERNEL32!GetProcAddress` at `0x180009823`
- `KERNEL32!GetProcAddress` at `0x180009810`
- `KERNEL32!GetProcAddress` at `0x180009823`

## string_xrefs

- `0x1800097dc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800097f1`: `kernel32.dll`

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
    qword_1800574B0 = (__int64)ProcAddress;
    qword_1800574B8 = (__int64)v2;
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
0x1800097c0  mov     [rsp+arg_0], rbx
0x1800097c5  push    rdi
0x1800097c6  sub     rsp, 20h
0x1800097ca  mov     edx, 0FA0h; dwSpinCount
0x1800097cf  lea     rcx, CriticalSection; lpCriticalSection
0x1800097d6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800097dc  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x1800097e3  call    cs:__imp_GetModuleHandleW
0x1800097e9  mov     rbx, rax
0x1800097ec  test    rax, rax
0x1800097ef  jnz     short loc_180009806
0x1800097f1  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x1800097f8  call    cs:__imp_GetModuleHandleW
0x1800097fe  mov     rbx, rax
0x180009801  test    rax, rax
0x180009804  jz      short loc_180009885
0x180009806  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18000980d  mov     rcx, rbx; hModule
0x180009810  call    cs:__imp_GetProcAddress
0x180009816  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000981d  mov     rcx, rbx; hModule
0x180009820  mov     rdi, rax
0x180009823  call    cs:__imp_GetProcAddress
0x180009829  test    rdi, rdi
0x18000982c  jz      short loc_180009843
0x18000982e  test    rax, rax
0x180009831  jz      short loc_180009843
0x180009833  mov     cs:qword_1800574B0, rdi
0x18000983a  mov     cs:qword_1800574B8, rax
0x180009841  jmp     short loc_180009861
0x180009843  xor     r9d, r9d; lpName
0x180009846  xor     r8d, r8d; bInitialState
0x180009849  xor     ecx, ecx; lpEventAttributes
0x18000984b  lea     edx, [r9+1]; bManualReset
0x18000984f  call    cs:__imp_CreateEventW
0x180009855  mov     cs:hHandle, rax
0x18000985c  test    rax, rax
0x18000985f  jz      short loc_180009885
0x180009861  xor     ecx, ecx
0x180009863  call    __scrt_initialize_onexit_tables
0x180009868  test    al, al
0x18000986a  jz      short loc_180009885
0x18000986c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180009873  call    atexit
0x180009878  mov     rbx, [rsp+28h+arg_0]
0x18000987d  xor     eax, eax
0x18000987f  add     rsp, 20h
0x180009883  pop     rdi
0x180009884  retn
0x180009885  mov     ecx, 7
0x18000988a  call    __scrt_fastfail
```
