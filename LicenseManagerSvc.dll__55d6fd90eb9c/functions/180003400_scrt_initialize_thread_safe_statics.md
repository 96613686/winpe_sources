# __scrt_initialize_thread_safe_statics

- ea: `0x180003400`
- end: `0x1800034d0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180003400`
- `0x180003870`
- `0x180003a40`
- `0x180003bc4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003450`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003463`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003450`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003463`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003423`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003438`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003423`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003438`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180003416`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180003416`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000348f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000348f`

## string_xrefs

- `0x18000341c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180003431`: `kernel32.dll`

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
    qword_180021650 = (__int64)ProcAddress;
    qword_180021658 = (__int64)v2;
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
0x180003400  mov     [rsp+arg_0], rbx
0x180003405  push    rdi
0x180003406  sub     rsp, 20h
0x18000340a  mov     edx, 0FA0h; dwSpinCount
0x18000340f  lea     rcx, CriticalSection; lpCriticalSection
0x180003416  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000341c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180003423  call    cs:__imp_GetModuleHandleW
0x180003429  mov     rbx, rax
0x18000342c  test    rax, rax
0x18000342f  jnz     short loc_180003446
0x180003431  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180003438  call    cs:__imp_GetModuleHandleW
0x18000343e  mov     rbx, rax
0x180003441  test    rax, rax
0x180003444  jz      short loc_1800034C5
0x180003446  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18000344d  mov     rcx, rbx; hModule
0x180003450  call    cs:__imp_GetProcAddress
0x180003456  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000345d  mov     rcx, rbx; hModule
0x180003460  mov     rdi, rax
0x180003463  call    cs:__imp_GetProcAddress
0x180003469  test    rdi, rdi
0x18000346c  jz      short loc_180003483
0x18000346e  test    rax, rax
0x180003471  jz      short loc_180003483
0x180003473  mov     cs:qword_180021650, rdi
0x18000347a  mov     cs:qword_180021658, rax
0x180003481  jmp     short loc_1800034A1
0x180003483  xor     r9d, r9d; lpName
0x180003486  xor     r8d, r8d; bInitialState
0x180003489  xor     ecx, ecx; lpEventAttributes
0x18000348b  lea     edx, [r9+1]; bManualReset
0x18000348f  call    cs:__imp_CreateEventW
0x180003495  mov     cs:hHandle, rax
0x18000349c  test    rax, rax
0x18000349f  jz      short loc_1800034C5
0x1800034a1  xor     ecx, ecx
0x1800034a3  call    __scrt_initialize_onexit_tables
0x1800034a8  test    al, al
0x1800034aa  jz      short loc_1800034C5
0x1800034ac  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1800034b3  call    atexit
0x1800034b8  mov     rbx, [rsp+28h+arg_0]
0x1800034bd  xor     eax, eax
0x1800034bf  add     rsp, 20h
0x1800034c3  pop     rdi
0x1800034c4  retn
0x1800034c5  mov     ecx, 7
0x1800034ca  call    __scrt_fastfail
```
