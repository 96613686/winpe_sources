# __scrt_initialize_thread_safe_statics

- ea: `0x180001be0`
- end: `0x180001cb0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001970`
- `0x180001b40`
- `0x180001be0`
- `0x180001fac`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180001c03`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180001c18`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180001c03`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180001c18`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001c30`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001c43`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001c30`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001c43`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180001bf6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180001bf6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180001c6f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180001c6f`

## string_xrefs

- `0x180001bfc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180001c11`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_1800445A8, 0xFA0u);
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
    qword_1800445D0 = (__int64)ProcAddress;
    qword_1800445D8 = (__int64)v2;
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
0x180001be0  mov     [rsp+arg_0], rbx
0x180001be5  push    rdi
0x180001be6  sub     rsp, 20h
0x180001bea  mov     edx, 0FA0h; dwSpinCount
0x180001bef  lea     rcx, stru_1800445A8; lpCriticalSection
0x180001bf6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180001bfc  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180001c03  call    cs:__imp_GetModuleHandleW
0x180001c09  mov     rbx, rax
0x180001c0c  test    rax, rax
0x180001c0f  jnz     short loc_180001C26
0x180001c11  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180001c18  call    cs:__imp_GetModuleHandleW
0x180001c1e  mov     rbx, rax
0x180001c21  test    rax, rax
0x180001c24  jz      short loc_180001CA5
0x180001c26  lea     rdx, ProcName; "SleepConditionVariableCS"
0x180001c2d  mov     rcx, rbx; hModule
0x180001c30  call    cs:__imp_GetProcAddress
0x180001c36  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180001c3d  mov     rcx, rbx; hModule
0x180001c40  mov     rdi, rax
0x180001c43  call    cs:__imp_GetProcAddress
0x180001c49  test    rdi, rdi
0x180001c4c  jz      short loc_180001C63
0x180001c4e  test    rax, rax
0x180001c51  jz      short loc_180001C63
0x180001c53  mov     cs:qword_1800445D0, rdi
0x180001c5a  mov     cs:qword_1800445D8, rax
0x180001c61  jmp     short loc_180001C81
0x180001c63  xor     r9d, r9d; lpName
0x180001c66  xor     r8d, r8d; bInitialState
0x180001c69  xor     ecx, ecx; lpEventAttributes
0x180001c6b  lea     edx, [r9+1]; bManualReset
0x180001c6f  call    cs:__imp_CreateEventW
0x180001c75  mov     cs:hHandle, rax
0x180001c7c  test    rax, rax
0x180001c7f  jz      short loc_180001CA5
0x180001c81  xor     ecx, ecx
0x180001c83  call    __scrt_initialize_onexit_tables
0x180001c88  test    al, al
0x180001c8a  jz      short loc_180001CA5
0x180001c8c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180001c93  call    atexit
0x180001c98  mov     rbx, [rsp+28h+arg_0]
0x180001c9d  xor     eax, eax
0x180001c9f  add     rsp, 20h
0x180001ca3  pop     rdi
0x180001ca4  retn
0x180001ca5  mov     ecx, 7
0x180001caa  call    __scrt_fastfail
```
