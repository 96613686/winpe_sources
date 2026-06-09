# __scrt_initialize_thread_safe_statics

- ea: `0x180006d60`
- end: `0x180006e30`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800050ac`
- `0x18000527c`
- `0x180005420`
- `0x180006d60`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006db0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006dc3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006db0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006dc3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006d83`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006d98`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006d83`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006d98`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180006def`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180006def`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180006d76`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180006d76`

## string_xrefs

- `0x180006d7c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180006d91`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_18011A790, 0xFA0u);
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
    qword_18011A7B8 = (__int64)ProcAddress;
    qword_18011A7C0 = (__int64)v2;
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
0x180006d60  mov     [rsp+arg_0], rbx
0x180006d65  push    rdi
0x180006d66  sub     rsp, 20h
0x180006d6a  mov     edx, 0FA0h; dwSpinCount
0x180006d6f  lea     rcx, stru_18011A790; lpCriticalSection
0x180006d76  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180006d7c  lea     rcx, aApiMsWinCoreSy_4; "api-ms-win-core-synch-l1-2-0.dll"
0x180006d83  call    cs:__imp_GetModuleHandleW
0x180006d89  mov     rbx, rax
0x180006d8c  test    rax, rax
0x180006d8f  jnz     short loc_180006DA6
0x180006d91  lea     rcx, SourceString; "kernel32.dll"
0x180006d98  call    cs:__imp_GetModuleHandleW
0x180006d9e  mov     rbx, rax
0x180006da1  test    rax, rax
0x180006da4  jz      short loc_180006E25
0x180006da6  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x180006dad  mov     rcx, rbx; hModule
0x180006db0  call    cs:__imp_GetProcAddress
0x180006db6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180006dbd  mov     rcx, rbx; hModule
0x180006dc0  mov     rdi, rax
0x180006dc3  call    cs:__imp_GetProcAddress
0x180006dc9  test    rdi, rdi
0x180006dcc  jz      short loc_180006DE3
0x180006dce  test    rax, rax
0x180006dd1  jz      short loc_180006DE3
0x180006dd3  mov     cs:qword_18011A7B8, rdi
0x180006dda  mov     cs:qword_18011A7C0, rax
0x180006de1  jmp     short loc_180006E01
0x180006de3  xor     r9d, r9d; lpName
0x180006de6  xor     r8d, r8d; bInitialState
0x180006de9  xor     ecx, ecx; lpEventAttributes
0x180006deb  lea     edx, [r9+1]; bManualReset
0x180006def  call    cs:__imp_CreateEventW
0x180006df5  mov     cs:hHandle, rax
0x180006dfc  test    rax, rax
0x180006dff  jz      short loc_180006E25
0x180006e01  xor     ecx, ecx
0x180006e03  call    __scrt_initialize_onexit_tables
0x180006e08  test    al, al
0x180006e0a  jz      short loc_180006E25
0x180006e0c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180006e13  call    atexit
0x180006e18  mov     rbx, [rsp+28h+arg_0]
0x180006e1d  xor     eax, eax
0x180006e1f  add     rsp, 20h
0x180006e23  pop     rdi
0x180006e24  retn
0x180006e25  mov     ecx, 7
0x180006e2a  call    __scrt_fastfail
```
