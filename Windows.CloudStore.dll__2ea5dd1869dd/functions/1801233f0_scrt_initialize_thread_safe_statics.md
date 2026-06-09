# __scrt_initialize_thread_safe_statics

- ea: `0x1801233f0`
- end: `0x1801234c0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180120498`
- `0x180120668`
- `0x1801207a0`
- `0x1801233f0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180123413`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180123428`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180123413`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180123428`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180123440`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180123453`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180123440`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180123453`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180123406`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180123406`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18012347f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18012347f`

## string_xrefs

- `0x18012340c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180123421`: `kernel32.dll`

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
    qword_180282180 = (__int64)ProcAddress;
    qword_180282188 = (__int64)v2;
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
0x1801233f0  mov     [rsp+arg_0], rbx
0x1801233f5  push    rdi
0x1801233f6  sub     rsp, 20h
0x1801233fa  mov     edx, 0FA0h; dwSpinCount
0x1801233ff  lea     rcx, CriticalSection; lpCriticalSection
0x180123406  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18012340c  lea     rcx, aApiMsWinCoreSy_3; "api-ms-win-core-synch-l1-2-0.dll"
0x180123413  call    cs:__imp_GetModuleHandleW
0x180123419  mov     rbx, rax
0x18012341c  test    rax, rax
0x18012341f  jnz     short loc_180123436
0x180123421  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180123428  call    cs:__imp_GetModuleHandleW
0x18012342e  mov     rbx, rax
0x180123431  test    rax, rax
0x180123434  jz      short loc_1801234B5
0x180123436  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x18012343d  mov     rcx, rbx; hModule
0x180123440  call    cs:__imp_GetProcAddress
0x180123446  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18012344d  mov     rcx, rbx; hModule
0x180123450  mov     rdi, rax
0x180123453  call    cs:__imp_GetProcAddress
0x180123459  test    rdi, rdi
0x18012345c  jz      short loc_180123473
0x18012345e  test    rax, rax
0x180123461  jz      short loc_180123473
0x180123463  mov     cs:qword_180282180, rdi
0x18012346a  mov     cs:qword_180282188, rax
0x180123471  jmp     short loc_180123491
0x180123473  xor     r9d, r9d; lpName
0x180123476  xor     r8d, r8d; bInitialState
0x180123479  xor     ecx, ecx; lpEventAttributes
0x18012347b  lea     edx, [r9+1]; bManualReset
0x18012347f  call    cs:__imp_CreateEventW
0x180123485  mov     cs:hHandle, rax
0x18012348c  test    rax, rax
0x18012348f  jz      short loc_1801234B5
0x180123491  xor     ecx, ecx
0x180123493  call    __scrt_initialize_onexit_tables
0x180123498  test    al, al
0x18012349a  jz      short loc_1801234B5
0x18012349c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1801234a3  call    atexit
0x1801234a8  mov     rbx, [rsp+28h+arg_0]
0x1801234ad  xor     eax, eax
0x1801234af  add     rsp, 20h
0x1801234b3  pop     rdi
0x1801234b4  retn
0x1801234b5  mov     ecx, 7
0x1801234ba  call    __scrt_fastfail
```
