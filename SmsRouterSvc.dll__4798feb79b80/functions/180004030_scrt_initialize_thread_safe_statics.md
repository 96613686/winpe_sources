# __scrt_initialize_thread_safe_statics

- ea: `0x180004030`
- end: `0x180004100`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180003d60`
- `0x180003f30`
- `0x180004030`
- `0x180004728`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004053`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004068`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004053`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004068`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004080`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004093`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004080`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004093`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800040bf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800040bf`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004046`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004046`

## string_xrefs

- `0x18000404c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180004061`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_18008CCB0, 0xFA0u);
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
    qword_18008CCD8 = (__int64)ProcAddress;
    qword_18008CCE0 = (__int64)v2;
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
0x180004030  mov     [rsp+arg_0], rbx
0x180004035  push    rdi
0x180004036  sub     rsp, 20h
0x18000403a  mov     edx, 0FA0h; dwSpinCount
0x18000403f  lea     rcx, stru_18008CCB0; lpCriticalSection
0x180004046  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000404c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180004053  call    cs:__imp_GetModuleHandleW
0x180004059  mov     rbx, rax
0x18000405c  test    rax, rax
0x18000405f  jnz     short loc_180004076
0x180004061  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180004068  call    cs:__imp_GetModuleHandleW
0x18000406e  mov     rbx, rax
0x180004071  test    rax, rax
0x180004074  jz      short loc_1800040F5
0x180004076  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18000407d  mov     rcx, rbx; hModule
0x180004080  call    cs:__imp_GetProcAddress
0x180004086  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000408d  mov     rcx, rbx; hModule
0x180004090  mov     rdi, rax
0x180004093  call    cs:__imp_GetProcAddress
0x180004099  test    rdi, rdi
0x18000409c  jz      short loc_1800040B3
0x18000409e  test    rax, rax
0x1800040a1  jz      short loc_1800040B3
0x1800040a3  mov     cs:qword_18008CCD8, rdi
0x1800040aa  mov     cs:qword_18008CCE0, rax
0x1800040b1  jmp     short loc_1800040D1
0x1800040b3  xor     r9d, r9d; lpName
0x1800040b6  xor     r8d, r8d; bInitialState
0x1800040b9  xor     ecx, ecx; lpEventAttributes
0x1800040bb  lea     edx, [r9+1]; bManualReset
0x1800040bf  call    cs:__imp_CreateEventW
0x1800040c5  mov     cs:hHandle, rax
0x1800040cc  test    rax, rax
0x1800040cf  jz      short loc_1800040F5
0x1800040d1  xor     ecx, ecx
0x1800040d3  call    __scrt_initialize_onexit_tables
0x1800040d8  test    al, al
0x1800040da  jz      short loc_1800040F5
0x1800040dc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1800040e3  call    atexit
0x1800040e8  mov     rbx, [rsp+28h+arg_0]
0x1800040ed  xor     eax, eax
0x1800040ef  add     rsp, 20h
0x1800040f3  pop     rdi
0x1800040f4  retn
0x1800040f5  mov     ecx, 7
0x1800040fa  call    __scrt_fastfail
```
