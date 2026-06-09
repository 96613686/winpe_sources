# __scrt_initialize_thread_safe_statics

- ea: `0x180003650`
- end: `0x180003720`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800026dc`
- `0x1800028ac`
- `0x180002a54`
- `0x180003650`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003673`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003688`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003673`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003688`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800036a0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800036b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800036a0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800036b3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800036df`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800036df`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180003666`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180003666`

## string_xrefs

- `0x18000366c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180003681`: `kernel32.dll`

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
    qword_18015F838 = (__int64)ProcAddress;
    qword_18015F840 = (__int64)v2;
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
0x180003650  mov     [rsp+arg_0], rbx
0x180003655  push    rdi
0x180003656  sub     rsp, 20h
0x18000365a  mov     edx, 0FA0h; dwSpinCount
0x18000365f  lea     rcx, CriticalSection; lpCriticalSection
0x180003666  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000366c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180003673  call    cs:__imp_GetModuleHandleW
0x180003679  mov     rbx, rax
0x18000367c  test    rax, rax
0x18000367f  jnz     short loc_180003696
0x180003681  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180003688  call    cs:__imp_GetModuleHandleW
0x18000368e  mov     rbx, rax
0x180003691  test    rax, rax
0x180003694  jz      short loc_180003715
0x180003696  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18000369d  mov     rcx, rbx; hModule
0x1800036a0  call    cs:__imp_GetProcAddress
0x1800036a6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800036ad  mov     rcx, rbx; hModule
0x1800036b0  mov     rdi, rax
0x1800036b3  call    cs:__imp_GetProcAddress
0x1800036b9  test    rdi, rdi
0x1800036bc  jz      short loc_1800036D3
0x1800036be  test    rax, rax
0x1800036c1  jz      short loc_1800036D3
0x1800036c3  mov     cs:qword_18015F838, rdi
0x1800036ca  mov     cs:qword_18015F840, rax
0x1800036d1  jmp     short loc_1800036F1
0x1800036d3  xor     r9d, r9d; lpName
0x1800036d6  xor     r8d, r8d; bInitialState
0x1800036d9  xor     ecx, ecx; lpEventAttributes
0x1800036db  lea     edx, [r9+1]; bManualReset
0x1800036df  call    cs:__imp_CreateEventW
0x1800036e5  mov     cs:hHandle, rax
0x1800036ec  test    rax, rax
0x1800036ef  jz      short loc_180003715
0x1800036f1  xor     ecx, ecx
0x1800036f3  call    __scrt_initialize_onexit_tables
0x1800036f8  test    al, al
0x1800036fa  jz      short loc_180003715
0x1800036fc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180003703  call    atexit
0x180003708  mov     rbx, [rsp+28h+arg_0]
0x18000370d  xor     eax, eax
0x18000370f  add     rsp, 20h
0x180003713  pop     rdi
0x180003714  retn
0x180003715  mov     ecx, 7
0x18000371a  call    __scrt_fastfail
```
