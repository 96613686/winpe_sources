# __scrt_initialize_thread_safe_statics

- ea: `0x180004e20`
- end: `0x180004ef0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180003680`
- `0x180003850`
- `0x180003d30`
- `0x180004e20`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004e43`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004e58`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004e43`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004e58`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004e70`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004e83`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004e70`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004e83`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004eaf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004eaf`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004e36`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004e36`

## string_xrefs

- `0x180004e3c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180004e51`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_1801598E8, 0xFA0u);
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
    qword_180159910 = (__int64)ProcAddress;
    qword_180159918 = (__int64)v2;
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
0x180004e20  mov     [rsp+arg_0], rbx
0x180004e25  push    rdi
0x180004e26  sub     rsp, 20h
0x180004e2a  mov     edx, 0FA0h; dwSpinCount
0x180004e2f  lea     rcx, stru_1801598E8; lpCriticalSection
0x180004e36  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180004e3c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180004e43  call    cs:__imp_GetModuleHandleW
0x180004e49  mov     rbx, rax
0x180004e4c  test    rax, rax
0x180004e4f  jnz     short loc_180004E66
0x180004e51  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180004e58  call    cs:__imp_GetModuleHandleW
0x180004e5e  mov     rbx, rax
0x180004e61  test    rax, rax
0x180004e64  jz      short loc_180004EE5
0x180004e66  lea     rdx, ProcName; "SleepConditionVariableCS"
0x180004e6d  mov     rcx, rbx; hModule
0x180004e70  call    cs:__imp_GetProcAddress
0x180004e76  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180004e7d  mov     rcx, rbx; hModule
0x180004e80  mov     rdi, rax
0x180004e83  call    cs:__imp_GetProcAddress
0x180004e89  test    rdi, rdi
0x180004e8c  jz      short loc_180004EA3
0x180004e8e  test    rax, rax
0x180004e91  jz      short loc_180004EA3
0x180004e93  mov     cs:qword_180159910, rdi
0x180004e9a  mov     cs:qword_180159918, rax
0x180004ea1  jmp     short loc_180004EC1
0x180004ea3  xor     r9d, r9d; lpName
0x180004ea6  xor     r8d, r8d; bInitialState
0x180004ea9  xor     ecx, ecx; lpEventAttributes
0x180004eab  lea     edx, [r9+1]; bManualReset
0x180004eaf  call    cs:__imp_CreateEventW
0x180004eb5  mov     cs:hHandle, rax
0x180004ebc  test    rax, rax
0x180004ebf  jz      short loc_180004EE5
0x180004ec1  xor     ecx, ecx
0x180004ec3  call    __scrt_initialize_onexit_tables
0x180004ec8  test    al, al
0x180004eca  jz      short loc_180004EE5
0x180004ecc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180004ed3  call    atexit
0x180004ed8  mov     rbx, [rsp+28h+arg_0]
0x180004edd  xor     eax, eax
0x180004edf  add     rsp, 20h
0x180004ee3  pop     rdi
0x180004ee4  retn
0x180004ee5  mov     ecx, 7
0x180004eea  call    __scrt_fastfail
```
