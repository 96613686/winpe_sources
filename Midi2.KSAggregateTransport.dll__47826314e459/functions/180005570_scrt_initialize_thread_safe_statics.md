# __scrt_initialize_thread_safe_statics

- ea: `0x180005570`
- end: `0x180005640`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180005340`
- `0x180005510`
- `0x180005570`
- `0x180005c80`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005593`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800055a8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005593`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800055a8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800055c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800055d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800055c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800055d3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800055ff`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800055ff`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180005586`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180005586`

## string_xrefs

- `0x18000558c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800055a1`: `kernel32.dll`

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
    qword_180096A18 = (__int64)ProcAddress;
    qword_180096A20 = (__int64)v2;
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
0x180005570  mov     [rsp+arg_0], rbx
0x180005575  push    rdi
0x180005576  sub     rsp, 20h
0x18000557a  mov     edx, 0FA0h; dwSpinCount
0x18000557f  lea     rcx, CriticalSection; lpCriticalSection
0x180005586  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000558c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180005593  call    cs:__imp_GetModuleHandleW
0x180005599  mov     rbx, rax
0x18000559c  test    rax, rax
0x18000559f  jnz     short loc_1800055B6
0x1800055a1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800055a8  call    cs:__imp_GetModuleHandleW
0x1800055ae  mov     rbx, rax
0x1800055b1  test    rax, rax
0x1800055b4  jz      short loc_180005635
0x1800055b6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x1800055bd  mov     rcx, rbx; hModule
0x1800055c0  call    cs:__imp_GetProcAddress
0x1800055c6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800055cd  mov     rcx, rbx; hModule
0x1800055d0  mov     rdi, rax
0x1800055d3  call    cs:__imp_GetProcAddress
0x1800055d9  test    rdi, rdi
0x1800055dc  jz      short loc_1800055F3
0x1800055de  test    rax, rax
0x1800055e1  jz      short loc_1800055F3
0x1800055e3  mov     cs:qword_180096A18, rdi
0x1800055ea  mov     cs:qword_180096A20, rax
0x1800055f1  jmp     short loc_180005611
0x1800055f3  xor     r9d, r9d; lpName
0x1800055f6  xor     r8d, r8d; bInitialState
0x1800055f9  xor     ecx, ecx; lpEventAttributes
0x1800055fb  lea     edx, [r9+1]; bManualReset
0x1800055ff  call    cs:__imp_CreateEventW
0x180005605  mov     cs:hHandle, rax
0x18000560c  test    rax, rax
0x18000560f  jz      short loc_180005635
0x180005611  xor     ecx, ecx
0x180005613  call    __scrt_initialize_onexit_tables
0x180005618  test    al, al
0x18000561a  jz      short loc_180005635
0x18000561c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180005623  call    atexit
0x180005628  mov     rbx, [rsp+28h+arg_0]
0x18000562d  xor     eax, eax
0x18000562f  add     rsp, 20h
0x180005633  pop     rdi
0x180005634  retn
0x180005635  mov     ecx, 7
0x18000563a  call    __scrt_fastfail
```
