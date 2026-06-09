# __scrt_initialize_thread_safe_statics

- ea: `0x180007a80`
- end: `0x180007b50`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180007850`
- `0x180007a20`
- `0x180007a80`
- `0x180008200`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007aa3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007ab8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007aa3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007ab8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007ad0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007ae3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007ad0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007ae3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180007b0f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180007b0f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180007a96`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180007a96`

## string_xrefs

- `0x180007a9c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180007ab1`: `kernel32.dll`

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
    qword_1800C89D0 = (__int64)ProcAddress;
    qword_1800C89D8 = (__int64)v2;
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
0x180007a80  mov     [rsp+arg_0], rbx
0x180007a85  push    rdi
0x180007a86  sub     rsp, 20h
0x180007a8a  mov     edx, 0FA0h; dwSpinCount
0x180007a8f  lea     rcx, CriticalSection; lpCriticalSection
0x180007a96  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180007a9c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180007aa3  call    cs:__imp_GetModuleHandleW
0x180007aa9  mov     rbx, rax
0x180007aac  test    rax, rax
0x180007aaf  jnz     short loc_180007AC6
0x180007ab1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180007ab8  call    cs:__imp_GetModuleHandleW
0x180007abe  mov     rbx, rax
0x180007ac1  test    rax, rax
0x180007ac4  jz      short loc_180007B45
0x180007ac6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x180007acd  mov     rcx, rbx; hModule
0x180007ad0  call    cs:__imp_GetProcAddress
0x180007ad6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180007add  mov     rcx, rbx; hModule
0x180007ae0  mov     rdi, rax
0x180007ae3  call    cs:__imp_GetProcAddress
0x180007ae9  test    rdi, rdi
0x180007aec  jz      short loc_180007B03
0x180007aee  test    rax, rax
0x180007af1  jz      short loc_180007B03
0x180007af3  mov     cs:qword_1800C89D0, rdi
0x180007afa  mov     cs:qword_1800C89D8, rax
0x180007b01  jmp     short loc_180007B21
0x180007b03  xor     r9d, r9d; lpName
0x180007b06  xor     r8d, r8d; bInitialState
0x180007b09  xor     ecx, ecx; lpEventAttributes
0x180007b0b  lea     edx, [r9+1]; bManualReset
0x180007b0f  call    cs:__imp_CreateEventW
0x180007b15  mov     cs:hHandle, rax
0x180007b1c  test    rax, rax
0x180007b1f  jz      short loc_180007B45
0x180007b21  xor     ecx, ecx
0x180007b23  call    __scrt_initialize_onexit_tables
0x180007b28  test    al, al
0x180007b2a  jz      short loc_180007B45
0x180007b2c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180007b33  call    atexit
0x180007b38  mov     rbx, [rsp+28h+arg_0]
0x180007b3d  xor     eax, eax
0x180007b3f  add     rsp, 20h
0x180007b43  pop     rdi
0x180007b44  retn
0x180007b45  mov     ecx, 7
0x180007b4a  call    __scrt_fastfail
```
