# __scrt_initialize_thread_safe_statics

- ea: `0x18005cee0`
- end: `0x18005cfb0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18005b14c`
- `0x18005b31c`
- `0x18005b4e8`
- `0x18005cee0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005cf30`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005cf43`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005cf30`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005cf43`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005cf03`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005cf18`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005cf03`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005cf18`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18005cef6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18005cef6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005cf6f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005cf6f`

## string_xrefs

- `0x18005cefc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x18005cf11`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_1800D1C58, 0xFA0u);
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
    qword_1800D1C80 = (__int64)ProcAddress;
    qword_1800D1C88 = (__int64)v2;
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
0x18005cee0  mov     [rsp+arg_0], rbx
0x18005cee5  push    rdi
0x18005cee6  sub     rsp, 20h
0x18005ceea  mov     edx, 0FA0h; dwSpinCount
0x18005ceef  lea     rcx, stru_1800D1C58; lpCriticalSection
0x18005cef6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18005cefc  lea     rcx, aApiMsWinCoreSy_4; "api-ms-win-core-synch-l1-2-0.dll"
0x18005cf03  call    cs:__imp_GetModuleHandleW
0x18005cf09  mov     rbx, rax
0x18005cf0c  test    rax, rax
0x18005cf0f  jnz     short loc_18005CF26
0x18005cf11  lea     rcx, aKernel32Dll; "kernel32.dll"
0x18005cf18  call    cs:__imp_GetModuleHandleW
0x18005cf1e  mov     rbx, rax
0x18005cf21  test    rax, rax
0x18005cf24  jz      short loc_18005CFA5
0x18005cf26  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x18005cf2d  mov     rcx, rbx; hModule
0x18005cf30  call    cs:__imp_GetProcAddress
0x18005cf36  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18005cf3d  mov     rcx, rbx; hModule
0x18005cf40  mov     rdi, rax
0x18005cf43  call    cs:__imp_GetProcAddress
0x18005cf49  test    rdi, rdi
0x18005cf4c  jz      short loc_18005CF63
0x18005cf4e  test    rax, rax
0x18005cf51  jz      short loc_18005CF63
0x18005cf53  mov     cs:qword_1800D1C80, rdi
0x18005cf5a  mov     cs:qword_1800D1C88, rax
0x18005cf61  jmp     short loc_18005CF81
0x18005cf63  xor     r9d, r9d; lpName
0x18005cf66  xor     r8d, r8d; bInitialState
0x18005cf69  xor     ecx, ecx; lpEventAttributes
0x18005cf6b  lea     edx, [r9+1]; bManualReset
0x18005cf6f  call    cs:__imp_CreateEventW
0x18005cf75  mov     cs:hHandle, rax
0x18005cf7c  test    rax, rax
0x18005cf7f  jz      short loc_18005CFA5
0x18005cf81  xor     ecx, ecx
0x18005cf83  call    __scrt_initialize_onexit_tables
0x18005cf88  test    al, al
0x18005cf8a  jz      short loc_18005CFA5
0x18005cf8c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x18005cf93  call    atexit
0x18005cf98  mov     rbx, [rsp+28h+arg_0]
0x18005cf9d  xor     eax, eax
0x18005cf9f  add     rsp, 20h
0x18005cfa3  pop     rdi
0x18005cfa4  retn
0x18005cfa5  mov     ecx, 7
0x18005cfaa  call    __scrt_fastfail
```
