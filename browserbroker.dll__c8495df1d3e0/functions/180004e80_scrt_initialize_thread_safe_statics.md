# __scrt_initialize_thread_safe_statics

- ea: `0x180004e80`
- end: `0x180004f50`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180002f3c`
- `0x18000310c`
- `0x1800032b8`
- `0x180004e80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004f0f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004f0f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004e96`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004e96`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004ed0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004ee3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004ed0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004ee3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004ea3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004eb8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004ea3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004eb8`

## string_xrefs

- `0x180004e9c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180004eb1`: `kernel32.dll`

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
    qword_18003FA20 = (__int64)ProcAddress;
    qword_18003FA28 = (__int64)v2;
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
0x180004e80  mov     [rsp+arg_0], rbx
0x180004e85  push    rdi
0x180004e86  sub     rsp, 20h
0x180004e8a  mov     edx, 0FA0h; dwSpinCount
0x180004e8f  lea     rcx, CriticalSection; lpCriticalSection
0x180004e96  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180004e9c  lea     rcx, aApiMsWinCoreSy_3; "api-ms-win-core-synch-l1-2-0.dll"
0x180004ea3  call    cs:__imp_GetModuleHandleW
0x180004ea9  mov     rbx, rax
0x180004eac  test    rax, rax
0x180004eaf  jnz     short loc_180004EC6
0x180004eb1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180004eb8  call    cs:__imp_GetModuleHandleW
0x180004ebe  mov     rbx, rax
0x180004ec1  test    rax, rax
0x180004ec4  jz      short loc_180004F45
0x180004ec6  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x180004ecd  mov     rcx, rbx; hModule
0x180004ed0  call    cs:__imp_GetProcAddress
0x180004ed6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180004edd  mov     rcx, rbx; hModule
0x180004ee0  mov     rdi, rax
0x180004ee3  call    cs:__imp_GetProcAddress
0x180004ee9  test    rdi, rdi
0x180004eec  jz      short loc_180004F03
0x180004eee  test    rax, rax
0x180004ef1  jz      short loc_180004F03
0x180004ef3  mov     cs:qword_18003FA20, rdi
0x180004efa  mov     cs:qword_18003FA28, rax
0x180004f01  jmp     short loc_180004F21
0x180004f03  xor     r9d, r9d; lpName
0x180004f06  xor     r8d, r8d; bInitialState
0x180004f09  xor     ecx, ecx; lpEventAttributes
0x180004f0b  lea     edx, [r9+1]; bManualReset
0x180004f0f  call    cs:__imp_CreateEventW
0x180004f15  mov     cs:hObject, rax
0x180004f1c  test    rax, rax
0x180004f1f  jz      short loc_180004F45
0x180004f21  xor     ecx, ecx
0x180004f23  call    __scrt_initialize_onexit_tables
0x180004f28  test    al, al
0x180004f2a  jz      short loc_180004F45
0x180004f2c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180004f33  call    atexit
0x180004f38  mov     rbx, [rsp+28h+arg_0]
0x180004f3d  xor     eax, eax
0x180004f3f  add     rsp, 20h
0x180004f43  pop     rdi
0x180004f44  retn
0x180004f45  mov     ecx, 7
0x180004f4a  call    __scrt_fastfail
```
