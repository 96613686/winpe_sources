# __scrt_initialize_thread_safe_statics

- ea: `0x18005f660`
- end: `0x18005f730`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18005dd44`
- `0x18005df14`
- `0x18005e204`
- `0x18005f660`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005f6b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005f6c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005f6b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005f6c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005f683`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005f698`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005f683`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005f698`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005f6ef`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005f6ef`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18005f676`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18005f676`

## string_xrefs

- `0x18005f67c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x18005f691`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_1800B0DB0, 0xFA0u);
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
    qword_1800B0DD8 = (__int64)ProcAddress;
    qword_1800B0DE0 = (__int64)v2;
  }
  else
  {
    hObject = CreateEventW(0, 1, 0, 0);
    if ( !hObject )
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
0x18005f660  mov     [rsp+arg_0], rbx
0x18005f665  push    rdi
0x18005f666  sub     rsp, 20h
0x18005f66a  mov     edx, 0FA0h; dwSpinCount
0x18005f66f  lea     rcx, stru_1800B0DB0; lpCriticalSection
0x18005f676  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18005f67c  lea     rcx, aApiMsWinCoreSy_2; "api-ms-win-core-synch-l1-2-0.dll"
0x18005f683  call    cs:__imp_GetModuleHandleW
0x18005f689  mov     rbx, rax
0x18005f68c  test    rax, rax
0x18005f68f  jnz     short loc_18005F6A6
0x18005f691  lea     rcx, aKernel32Dll; "kernel32.dll"
0x18005f698  call    cs:__imp_GetModuleHandleW
0x18005f69e  mov     rbx, rax
0x18005f6a1  test    rax, rax
0x18005f6a4  jz      short loc_18005F725
0x18005f6a6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18005f6ad  mov     rcx, rbx; hModule
0x18005f6b0  call    cs:__imp_GetProcAddress
0x18005f6b6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18005f6bd  mov     rcx, rbx; hModule
0x18005f6c0  mov     rdi, rax
0x18005f6c3  call    cs:__imp_GetProcAddress
0x18005f6c9  test    rdi, rdi
0x18005f6cc  jz      short loc_18005F6E3
0x18005f6ce  test    rax, rax
0x18005f6d1  jz      short loc_18005F6E3
0x18005f6d3  mov     cs:qword_1800B0DD8, rdi
0x18005f6da  mov     cs:qword_1800B0DE0, rax
0x18005f6e1  jmp     short loc_18005F701
0x18005f6e3  xor     r9d, r9d; lpName
0x18005f6e6  xor     r8d, r8d; bInitialState
0x18005f6e9  xor     ecx, ecx; lpEventAttributes
0x18005f6eb  lea     edx, [r9+1]; bManualReset
0x18005f6ef  call    cs:__imp_CreateEventW
0x18005f6f5  mov     cs:hObject, rax
0x18005f6fc  test    rax, rax
0x18005f6ff  jz      short loc_18005F725
0x18005f701  xor     ecx, ecx
0x18005f703  call    __scrt_initialize_onexit_tables
0x18005f708  test    al, al
0x18005f70a  jz      short loc_18005F725
0x18005f70c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x18005f713  call    atexit
0x18005f718  mov     rbx, [rsp+28h+arg_0]
0x18005f71d  xor     eax, eax
0x18005f71f  add     rsp, 20h
0x18005f723  pop     rdi
0x18005f724  retn
0x18005f725  mov     ecx, 7
0x18005f72a  call    __scrt_fastfail
```
