# __scrt_initialize_thread_safe_statics

- ea: `0x180003210`
- end: `0x1800032e0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180002630`
- `0x180002800`
- `0x1800029ec`
- `0x180003210`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003260`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003273`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003260`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003273`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003233`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003248`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003233`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003248`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000329f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000329f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180003226`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180003226`

## string_xrefs

- `0x18000322c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180003241`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_180059C18, 0xFA0u);
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
    qword_180059C40 = (__int64)ProcAddress;
    qword_180059C48 = (__int64)v2;
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
0x180003210  mov     [rsp+arg_0], rbx
0x180003215  push    rdi
0x180003216  sub     rsp, 20h
0x18000321a  mov     edx, 0FA0h; dwSpinCount
0x18000321f  lea     rcx, stru_180059C18; lpCriticalSection
0x180003226  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000322c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180003233  call    cs:__imp_GetModuleHandleW
0x180003239  mov     rbx, rax
0x18000323c  test    rax, rax
0x18000323f  jnz     short loc_180003256
0x180003241  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180003248  call    cs:__imp_GetModuleHandleW
0x18000324e  mov     rbx, rax
0x180003251  test    rax, rax
0x180003254  jz      short loc_1800032D5
0x180003256  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18000325d  mov     rcx, rbx; hModule
0x180003260  call    cs:__imp_GetProcAddress
0x180003266  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000326d  mov     rcx, rbx; hModule
0x180003270  mov     rdi, rax
0x180003273  call    cs:__imp_GetProcAddress
0x180003279  test    rdi, rdi
0x18000327c  jz      short loc_180003293
0x18000327e  test    rax, rax
0x180003281  jz      short loc_180003293
0x180003283  mov     cs:qword_180059C40, rdi
0x18000328a  mov     cs:qword_180059C48, rax
0x180003291  jmp     short loc_1800032B1
0x180003293  xor     r9d, r9d; lpName
0x180003296  xor     r8d, r8d; bInitialState
0x180003299  xor     ecx, ecx; lpEventAttributes
0x18000329b  lea     edx, [r9+1]; bManualReset
0x18000329f  call    cs:__imp_CreateEventW
0x1800032a5  mov     cs:hHandle, rax
0x1800032ac  test    rax, rax
0x1800032af  jz      short loc_1800032D5
0x1800032b1  xor     ecx, ecx
0x1800032b3  call    __scrt_initialize_onexit_tables
0x1800032b8  test    al, al
0x1800032ba  jz      short loc_1800032D5
0x1800032bc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1800032c3  call    atexit
0x1800032c8  mov     rbx, [rsp+28h+arg_0]
0x1800032cd  xor     eax, eax
0x1800032cf  add     rsp, 20h
0x1800032d3  pop     rdi
0x1800032d4  retn
0x1800032d5  mov     ecx, 7
0x1800032da  call    __scrt_fastfail
```
