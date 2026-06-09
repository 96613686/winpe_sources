# __scrt_initialize_thread_safe_statics

- ea: `0x18000d3d0`
- end: `0x18000d4a0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800097d8`
- `0x1800099a8`
- `0x180009b48`
- `0x18000d3d0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d420`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d433`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d420`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d433`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d3f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d408`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d3f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d408`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000d3e6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000d3e6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000d45f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000d45f`

## string_xrefs

- `0x18000d3ec`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x18000d401`: `kernel32.dll`

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
    qword_1801667D0 = (__int64)ProcAddress;
    qword_1801667D8 = (__int64)v2;
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
0x18000d3d0  mov     [rsp+arg_0], rbx
0x18000d3d5  push    rdi
0x18000d3d6  sub     rsp, 20h
0x18000d3da  mov     edx, 0FA0h; dwSpinCount
0x18000d3df  lea     rcx, CriticalSection; lpCriticalSection
0x18000d3e6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000d3ec  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x18000d3f3  call    cs:__imp_GetModuleHandleW
0x18000d3f9  mov     rbx, rax
0x18000d3fc  test    rax, rax
0x18000d3ff  jnz     short loc_18000D416
0x18000d401  lea     rcx, aKernel32Dll; "kernel32.dll"
0x18000d408  call    cs:__imp_GetModuleHandleW
0x18000d40e  mov     rbx, rax
0x18000d411  test    rax, rax
0x18000d414  jz      short loc_18000D495
0x18000d416  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18000d41d  mov     rcx, rbx; hModule
0x18000d420  call    cs:__imp_GetProcAddress
0x18000d426  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000d42d  mov     rcx, rbx; hModule
0x18000d430  mov     rdi, rax
0x18000d433  call    cs:__imp_GetProcAddress
0x18000d439  test    rdi, rdi
0x18000d43c  jz      short loc_18000D453
0x18000d43e  test    rax, rax
0x18000d441  jz      short loc_18000D453
0x18000d443  mov     cs:qword_1801667D0, rdi
0x18000d44a  mov     cs:qword_1801667D8, rax
0x18000d451  jmp     short loc_18000D471
0x18000d453  xor     r9d, r9d; lpName
0x18000d456  xor     r8d, r8d; bInitialState
0x18000d459  xor     ecx, ecx; lpEventAttributes
0x18000d45b  lea     edx, [r9+1]; bManualReset
0x18000d45f  call    cs:__imp_CreateEventW
0x18000d465  mov     cs:hHandle, rax
0x18000d46c  test    rax, rax
0x18000d46f  jz      short loc_18000D495
0x18000d471  xor     ecx, ecx
0x18000d473  call    __scrt_initialize_onexit_tables
0x18000d478  test    al, al
0x18000d47a  jz      short loc_18000D495
0x18000d47c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x18000d483  call    atexit
0x18000d488  mov     rbx, [rsp+28h+arg_0]
0x18000d48d  xor     eax, eax
0x18000d48f  add     rsp, 20h
0x18000d493  pop     rdi
0x18000d494  retn
0x18000d495  mov     ecx, 7
0x18000d49a  call    __scrt_fastfail
```
