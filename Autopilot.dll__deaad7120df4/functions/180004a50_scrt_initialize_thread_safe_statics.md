# __scrt_initialize_thread_safe_statics

- ea: `0x180004a50`
- end: `0x180004b20`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180004818`
- `0x1800049e8`
- `0x180004a50`
- `0x180004e5c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004a73`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004a88`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004a73`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004a88`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004aa0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004ab3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004aa0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004ab3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004adf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004adf`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004a66`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004a66`

## string_xrefs

- `0x180004a6c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180004a81`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_180043A28, 0xFA0u);
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
    qword_180043A50 = (__int64)ProcAddress;
    qword_180043A58 = (__int64)v2;
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
0x180004a50  mov     [rsp+arg_0], rbx
0x180004a55  push    rdi
0x180004a56  sub     rsp, 20h
0x180004a5a  mov     edx, 0FA0h; dwSpinCount
0x180004a5f  lea     rcx, stru_180043A28; lpCriticalSection
0x180004a66  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180004a6c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180004a73  call    cs:__imp_GetModuleHandleW
0x180004a79  mov     rbx, rax
0x180004a7c  test    rax, rax
0x180004a7f  jnz     short loc_180004A96
0x180004a81  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180004a88  call    cs:__imp_GetModuleHandleW
0x180004a8e  mov     rbx, rax
0x180004a91  test    rax, rax
0x180004a94  jz      short loc_180004B15
0x180004a96  lea     rdx, ProcName; "SleepConditionVariableCS"
0x180004a9d  mov     rcx, rbx; hModule
0x180004aa0  call    cs:__imp_GetProcAddress
0x180004aa6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180004aad  mov     rcx, rbx; hModule
0x180004ab0  mov     rdi, rax
0x180004ab3  call    cs:__imp_GetProcAddress
0x180004ab9  test    rdi, rdi
0x180004abc  jz      short loc_180004AD3
0x180004abe  test    rax, rax
0x180004ac1  jz      short loc_180004AD3
0x180004ac3  mov     cs:qword_180043A50, rdi
0x180004aca  mov     cs:qword_180043A58, rax
0x180004ad1  jmp     short loc_180004AF1
0x180004ad3  xor     r9d, r9d; lpName
0x180004ad6  xor     r8d, r8d; bInitialState
0x180004ad9  xor     ecx, ecx; lpEventAttributes
0x180004adb  lea     edx, [r9+1]; bManualReset
0x180004adf  call    cs:__imp_CreateEventW
0x180004ae5  mov     cs:hHandle, rax
0x180004aec  test    rax, rax
0x180004aef  jz      short loc_180004B15
0x180004af1  xor     ecx, ecx
0x180004af3  call    __scrt_initialize_onexit_tables
0x180004af8  test    al, al
0x180004afa  jz      short loc_180004B15
0x180004afc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180004b03  call    atexit
0x180004b08  mov     rbx, [rsp+28h+arg_0]
0x180004b0d  xor     eax, eax
0x180004b0f  add     rsp, 20h
0x180004b13  pop     rdi
0x180004b14  retn
0x180004b15  mov     ecx, 7
0x180004b1a  call    __scrt_fastfail
```
