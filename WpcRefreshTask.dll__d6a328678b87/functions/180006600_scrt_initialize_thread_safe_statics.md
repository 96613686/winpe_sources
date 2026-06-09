# __scrt_initialize_thread_safe_statics

- ea: `0x180006600`
- end: `0x1800066d0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180006308`
- `0x1800064d8`
- `0x180006600`
- `0x1800069c8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006650`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006663`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006650`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006663`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006623`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006638`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006623`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006638`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000668f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000668f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180006616`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180006616`

## string_xrefs

- `0x18000661c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180006631`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_180107248, 0xFA0u);
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
    qword_180107270 = (__int64)ProcAddress;
    qword_180107278 = (__int64)v2;
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
0x180006600  mov     [rsp+arg_0], rbx
0x180006605  push    rdi
0x180006606  sub     rsp, 20h
0x18000660a  mov     edx, 0FA0h; dwSpinCount
0x18000660f  lea     rcx, stru_180107248; lpCriticalSection
0x180006616  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000661c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180006623  call    cs:__imp_GetModuleHandleW
0x180006629  mov     rbx, rax
0x18000662c  test    rax, rax
0x18000662f  jnz     short loc_180006646
0x180006631  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180006638  call    cs:__imp_GetModuleHandleW
0x18000663e  mov     rbx, rax
0x180006641  test    rax, rax
0x180006644  jz      short loc_1800066C5
0x180006646  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18000664d  mov     rcx, rbx; hModule
0x180006650  call    cs:__imp_GetProcAddress
0x180006656  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000665d  mov     rcx, rbx; hModule
0x180006660  mov     rdi, rax
0x180006663  call    cs:__imp_GetProcAddress
0x180006669  test    rdi, rdi
0x18000666c  jz      short loc_180006683
0x18000666e  test    rax, rax
0x180006671  jz      short loc_180006683
0x180006673  mov     cs:qword_180107270, rdi
0x18000667a  mov     cs:qword_180107278, rax
0x180006681  jmp     short loc_1800066A1
0x180006683  xor     r9d, r9d; lpName
0x180006686  xor     r8d, r8d; bInitialState
0x180006689  xor     ecx, ecx; lpEventAttributes
0x18000668b  lea     edx, [r9+1]; bManualReset
0x18000668f  call    cs:__imp_CreateEventW
0x180006695  mov     cs:hHandle, rax
0x18000669c  test    rax, rax
0x18000669f  jz      short loc_1800066C5
0x1800066a1  xor     ecx, ecx
0x1800066a3  call    __scrt_initialize_onexit_tables
0x1800066a8  test    al, al
0x1800066aa  jz      short loc_1800066C5
0x1800066ac  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1800066b3  call    atexit
0x1800066b8  mov     rbx, [rsp+28h+arg_0]
0x1800066bd  xor     eax, eax
0x1800066bf  add     rsp, 20h
0x1800066c3  pop     rdi
0x1800066c4  retn
0x1800066c5  mov     ecx, 7
0x1800066ca  call    __scrt_fastfail
```
