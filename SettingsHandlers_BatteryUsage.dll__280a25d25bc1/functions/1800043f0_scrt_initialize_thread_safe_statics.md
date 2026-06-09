# __scrt_initialize_thread_safe_statics

- ea: `0x1800043f0`
- end: `0x1800044c0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180002bc8`
- `0x180002d98`
- `0x180002ed0`
- `0x1800043f0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004413`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004428`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004413`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004428`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004440`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004453`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004440`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004453`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000447f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000447f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004406`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004406`

## string_xrefs

- `0x18000440c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180004421`: `kernel32.dll`

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
    qword_180079630 = (__int64)ProcAddress;
    qword_180079638 = (__int64)v2;
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
0x1800043f0  mov     [rsp+arg_0], rbx
0x1800043f5  push    rdi
0x1800043f6  sub     rsp, 20h
0x1800043fa  mov     edx, 0FA0h; dwSpinCount
0x1800043ff  lea     rcx, CriticalSection; lpCriticalSection
0x180004406  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000440c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180004413  call    cs:__imp_GetModuleHandleW
0x180004419  mov     rbx, rax
0x18000441c  test    rax, rax
0x18000441f  jnz     short loc_180004436
0x180004421  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180004428  call    cs:__imp_GetModuleHandleW
0x18000442e  mov     rbx, rax
0x180004431  test    rax, rax
0x180004434  jz      short loc_1800044B5
0x180004436  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18000443d  mov     rcx, rbx; hModule
0x180004440  call    cs:__imp_GetProcAddress
0x180004446  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000444d  mov     rcx, rbx; hModule
0x180004450  mov     rdi, rax
0x180004453  call    cs:__imp_GetProcAddress
0x180004459  test    rdi, rdi
0x18000445c  jz      short loc_180004473
0x18000445e  test    rax, rax
0x180004461  jz      short loc_180004473
0x180004463  mov     cs:qword_180079630, rdi
0x18000446a  mov     cs:qword_180079638, rax
0x180004471  jmp     short loc_180004491
0x180004473  xor     r9d, r9d; lpName
0x180004476  xor     r8d, r8d; bInitialState
0x180004479  xor     ecx, ecx; lpEventAttributes
0x18000447b  lea     edx, [r9+1]; bManualReset
0x18000447f  call    cs:__imp_CreateEventW
0x180004485  mov     cs:hHandle, rax
0x18000448c  test    rax, rax
0x18000448f  jz      short loc_1800044B5
0x180004491  xor     ecx, ecx
0x180004493  call    __scrt_initialize_onexit_tables
0x180004498  test    al, al
0x18000449a  jz      short loc_1800044B5
0x18000449c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1800044a3  call    atexit
0x1800044a8  mov     rbx, [rsp+28h+arg_0]
0x1800044ad  xor     eax, eax
0x1800044af  add     rsp, 20h
0x1800044b3  pop     rdi
0x1800044b4  retn
0x1800044b5  mov     ecx, 7
0x1800044ba  call    __scrt_fastfail
```
