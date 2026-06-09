# __scrt_initialize_thread_safe_statics

- ea: `0x1800043d0`
- end: `0x1800044a0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180003a94`
- `0x180003c64`
- `0x180003dd4`
- `0x1800043d0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1800043f3`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180004408`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1800043f3`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180004408`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180004420`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180004433`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180004420`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180004433`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000445f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000445f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800043e6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800043e6`

## string_xrefs

- `0x1800043ec`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180004401`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_18004C5C8, 0xFA0u);
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
    qword_18004C5F0 = (__int64)ProcAddress;
    qword_18004C5F8 = (__int64)v2;
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
0x1800043d0  mov     [rsp+arg_0], rbx
0x1800043d5  push    rdi
0x1800043d6  sub     rsp, 20h
0x1800043da  mov     edx, 0FA0h; dwSpinCount
0x1800043df  lea     rcx, stru_18004C5C8; lpCriticalSection
0x1800043e6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800043ec  lea     rcx, aApiMsWinCoreSy_2; "api-ms-win-core-synch-l1-2-0.dll"
0x1800043f3  call    cs:__imp_GetModuleHandleW
0x1800043f9  mov     rbx, rax
0x1800043fc  test    rax, rax
0x1800043ff  jnz     short loc_180004416
0x180004401  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180004408  call    cs:__imp_GetModuleHandleW
0x18000440e  mov     rbx, rax
0x180004411  test    rax, rax
0x180004414  jz      short loc_180004495
0x180004416  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x18000441d  mov     rcx, rbx; hModule
0x180004420  call    cs:__imp_GetProcAddress
0x180004426  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000442d  mov     rcx, rbx; hModule
0x180004430  mov     rdi, rax
0x180004433  call    cs:__imp_GetProcAddress
0x180004439  test    rdi, rdi
0x18000443c  jz      short loc_180004453
0x18000443e  test    rax, rax
0x180004441  jz      short loc_180004453
0x180004443  mov     cs:qword_18004C5F0, rdi
0x18000444a  mov     cs:qword_18004C5F8, rax
0x180004451  jmp     short loc_180004471
0x180004453  xor     r9d, r9d; lpName
0x180004456  xor     r8d, r8d; bInitialState
0x180004459  xor     ecx, ecx; lpEventAttributes
0x18000445b  lea     edx, [r9+1]; bManualReset
0x18000445f  call    cs:__imp_CreateEventW
0x180004465  mov     cs:hObject, rax
0x18000446c  test    rax, rax
0x18000446f  jz      short loc_180004495
0x180004471  xor     ecx, ecx
0x180004473  call    __scrt_initialize_onexit_tables
0x180004478  test    al, al
0x18000447a  jz      short loc_180004495
0x18000447c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180004483  call    atexit
0x180004488  mov     rbx, [rsp+28h+arg_0]
0x18000448d  xor     eax, eax
0x18000448f  add     rsp, 20h
0x180004493  pop     rdi
0x180004494  retn
0x180004495  mov     ecx, 7
0x18000449a  call    __scrt_fastfail
```
