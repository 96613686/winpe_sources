# __scrt_initialize_thread_safe_statics

- ea: `0x18000d840`
- end: `0x18000d910`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180002960`
- `0x180002b30`
- `0x180002ca4`
- `0x18000d840`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d863`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d878`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d863`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d878`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d890`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d8a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d890`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d8a3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000d856`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000d856`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000d8cf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000d8cf`

## string_xrefs

- `0x18000d85c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x18000d871`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_180066088, 0xFA0u);
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
    qword_1800660B0 = (__int64)ProcAddress;
    qword_1800660B8 = (__int64)v2;
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
0x18000d840  mov     [rsp+arg_0], rbx
0x18000d845  push    rdi
0x18000d846  sub     rsp, 20h
0x18000d84a  mov     edx, 0FA0h; dwSpinCount
0x18000d84f  lea     rcx, stru_180066088; lpCriticalSection
0x18000d856  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000d85c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x18000d863  call    cs:__imp_GetModuleHandleW
0x18000d869  mov     rbx, rax
0x18000d86c  test    rax, rax
0x18000d86f  jnz     short loc_18000D886
0x18000d871  lea     rcx, aKernel32Dll; "kernel32.dll"
0x18000d878  call    cs:__imp_GetModuleHandleW
0x18000d87e  mov     rbx, rax
0x18000d881  test    rax, rax
0x18000d884  jz      short loc_18000D905
0x18000d886  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18000d88d  mov     rcx, rbx; hModule
0x18000d890  call    cs:__imp_GetProcAddress
0x18000d896  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000d89d  mov     rcx, rbx; hModule
0x18000d8a0  mov     rdi, rax
0x18000d8a3  call    cs:__imp_GetProcAddress
0x18000d8a9  test    rdi, rdi
0x18000d8ac  jz      short loc_18000D8C3
0x18000d8ae  test    rax, rax
0x18000d8b1  jz      short loc_18000D8C3
0x18000d8b3  mov     cs:qword_1800660B0, rdi
0x18000d8ba  mov     cs:qword_1800660B8, rax
0x18000d8c1  jmp     short loc_18000D8E1
0x18000d8c3  xor     r9d, r9d; lpName
0x18000d8c6  xor     r8d, r8d; bInitialState
0x18000d8c9  xor     ecx, ecx; lpEventAttributes
0x18000d8cb  lea     edx, [r9+1]; bManualReset
0x18000d8cf  call    cs:__imp_CreateEventW
0x18000d8d5  mov     cs:hHandle, rax
0x18000d8dc  test    rax, rax
0x18000d8df  jz      short loc_18000D905
0x18000d8e1  xor     ecx, ecx
0x18000d8e3  call    __scrt_initialize_onexit_tables
0x18000d8e8  test    al, al
0x18000d8ea  jz      short loc_18000D905
0x18000d8ec  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x18000d8f3  call    atexit
0x18000d8f8  mov     rbx, [rsp+28h+arg_0]
0x18000d8fd  xor     eax, eax
0x18000d8ff  add     rsp, 20h
0x18000d903  pop     rdi
0x18000d904  retn
0x18000d905  mov     ecx, 7
0x18000d90a  call    __scrt_fastfail
```
