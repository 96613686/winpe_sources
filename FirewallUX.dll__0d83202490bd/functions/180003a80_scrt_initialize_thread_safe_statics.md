# __scrt_initialize_thread_safe_statics

- ea: `0x180003a80`
- end: `0x180003b50`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180002408`
- `0x1800025d8`
- `0x180002754`
- `0x180003a80`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003aa3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003ab8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003aa3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003ab8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003ad0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003ae3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003ad0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003ae3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180003a96`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180003a96`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180003b0f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180003b0f`

## string_xrefs

- `0x180003a9c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180003ab1`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_18003BDA0, 0xFA0u);
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
    qword_18003BDC8 = (__int64)ProcAddress;
    qword_18003BDD0 = (__int64)v2;
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
0x180003a80  mov     [rsp+arg_0], rbx
0x180003a85  push    rdi
0x180003a86  sub     rsp, 20h
0x180003a8a  mov     edx, 0FA0h; dwSpinCount
0x180003a8f  lea     rcx, stru_18003BDA0; lpCriticalSection
0x180003a96  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180003a9c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180003aa3  call    cs:__imp_GetModuleHandleW
0x180003aa9  mov     rbx, rax
0x180003aac  test    rax, rax
0x180003aaf  jnz     short loc_180003AC6
0x180003ab1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180003ab8  call    cs:__imp_GetModuleHandleW
0x180003abe  mov     rbx, rax
0x180003ac1  test    rax, rax
0x180003ac4  jz      short loc_180003B45
0x180003ac6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x180003acd  mov     rcx, rbx; hModule
0x180003ad0  call    cs:__imp_GetProcAddress
0x180003ad6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180003add  mov     rcx, rbx; hModule
0x180003ae0  mov     rdi, rax
0x180003ae3  call    cs:__imp_GetProcAddress
0x180003ae9  test    rdi, rdi
0x180003aec  jz      short loc_180003B03
0x180003aee  test    rax, rax
0x180003af1  jz      short loc_180003B03
0x180003af3  mov     cs:qword_18003BDC8, rdi
0x180003afa  mov     cs:qword_18003BDD0, rax
0x180003b01  jmp     short loc_180003B21
0x180003b03  xor     r9d, r9d; lpName
0x180003b06  xor     r8d, r8d; bInitialState
0x180003b09  xor     ecx, ecx; lpEventAttributes
0x180003b0b  lea     edx, [r9+1]; bManualReset
0x180003b0f  call    cs:__imp_CreateEventW
0x180003b15  mov     cs:hHandle, rax
0x180003b1c  test    rax, rax
0x180003b1f  jz      short loc_180003B45
0x180003b21  xor     ecx, ecx
0x180003b23  call    __scrt_initialize_onexit_tables
0x180003b28  test    al, al
0x180003b2a  jz      short loc_180003B45
0x180003b2c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180003b33  call    atexit
0x180003b38  mov     rbx, [rsp+28h+arg_0]
0x180003b3d  xor     eax, eax
0x180003b3f  add     rsp, 20h
0x180003b43  pop     rdi
0x180003b44  retn
0x180003b45  mov     ecx, 7
0x180003b4a  call    __scrt_fastfail
```
