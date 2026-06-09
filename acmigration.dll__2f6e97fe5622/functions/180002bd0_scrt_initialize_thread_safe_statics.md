# __scrt_initialize_thread_safe_statics

- ea: `0x180002bd0`
- end: `0x180002ca0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001ed0`
- `0x1800020a0`
- `0x1800022cc`
- `0x180002bd0`

## import_xrefs

- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180002be6`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180002be6`
- `KERNEL32!CreateEventW` at `0x180002c5f`
- `KERNEL32!CreateEventW` at `0x180002c5f`
- `KERNEL32!GetModuleHandleW` at `0x180002bf3`
- `KERNEL32!GetModuleHandleW` at `0x180002c08`
- `KERNEL32!GetModuleHandleW` at `0x180002bf3`
- `KERNEL32!GetModuleHandleW` at `0x180002c08`
- `KERNEL32!GetProcAddress` at `0x180002c20`
- `KERNEL32!GetProcAddress` at `0x180002c33`
- `KERNEL32!GetProcAddress` at `0x180002c20`
- `KERNEL32!GetProcAddress` at `0x180002c33`

## string_xrefs

- `0x180002bec`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180002c01`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_1800975C8, 0xFA0u);
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
    qword_1800975F0 = (__int64)ProcAddress;
    qword_1800975F8 = (__int64)v2;
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
0x180002bd0  mov     [rsp+arg_0], rbx
0x180002bd5  push    rdi
0x180002bd6  sub     rsp, 20h
0x180002bda  mov     edx, 0FA0h; dwSpinCount
0x180002bdf  lea     rcx, stru_1800975C8; lpCriticalSection
0x180002be6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180002bec  lea     rcx, aApiMsWinCoreSy; "api-ms-win-core-synch-l1-2-0.dll"
0x180002bf3  call    cs:__imp_GetModuleHandleW
0x180002bf9  mov     rbx, rax
0x180002bfc  test    rax, rax
0x180002bff  jnz     short loc_180002C16
0x180002c01  lea     rcx, SourceString; "kernel32.dll"
0x180002c08  call    cs:__imp_GetModuleHandleW
0x180002c0e  mov     rbx, rax
0x180002c11  test    rax, rax
0x180002c14  jz      short loc_180002C95
0x180002c16  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x180002c1d  mov     rcx, rbx; hModule
0x180002c20  call    cs:__imp_GetProcAddress
0x180002c26  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180002c2d  mov     rcx, rbx; hModule
0x180002c30  mov     rdi, rax
0x180002c33  call    cs:__imp_GetProcAddress
0x180002c39  test    rdi, rdi
0x180002c3c  jz      short loc_180002C53
0x180002c3e  test    rax, rax
0x180002c41  jz      short loc_180002C53
0x180002c43  mov     cs:qword_1800975F0, rdi
0x180002c4a  mov     cs:qword_1800975F8, rax
0x180002c51  jmp     short loc_180002C71
0x180002c53  xor     r9d, r9d; lpName
0x180002c56  xor     r8d, r8d; bInitialState
0x180002c59  xor     ecx, ecx; lpEventAttributes
0x180002c5b  lea     edx, [r9+1]; bManualReset
0x180002c5f  call    cs:__imp_CreateEventW
0x180002c65  mov     cs:hHandle, rax
0x180002c6c  test    rax, rax
0x180002c6f  jz      short loc_180002C95
0x180002c71  xor     ecx, ecx
0x180002c73  call    __scrt_initialize_onexit_tables
0x180002c78  test    al, al
0x180002c7a  jz      short loc_180002C95
0x180002c7c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180002c83  call    atexit
0x180002c88  mov     rbx, [rsp+28h+arg_0]
0x180002c8d  xor     eax, eax
0x180002c8f  add     rsp, 20h
0x180002c93  pop     rdi
0x180002c94  retn
0x180002c95  mov     ecx, 7
0x180002c9a  call    __scrt_fastfail
```
