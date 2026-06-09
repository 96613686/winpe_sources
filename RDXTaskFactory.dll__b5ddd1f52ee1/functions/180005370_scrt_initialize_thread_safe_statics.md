# __scrt_initialize_thread_safe_statics

- ea: `0x180005370`
- end: `0x180005440`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800035b4`
- `0x180003784`
- `0x1800038f4`
- `0x180005370`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800053c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800053d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800053c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800053d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005393`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800053a8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005393`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800053a8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800053ff`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800053ff`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180005386`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180005386`

## string_xrefs

- `0x18000538c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800053a1`: `kernel32.dll`

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
    qword_18006DDB8 = (__int64)ProcAddress;
    qword_18006DDC0 = (__int64)v2;
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
0x180005370  mov     [rsp+arg_0], rbx
0x180005375  push    rdi
0x180005376  sub     rsp, 20h
0x18000537a  mov     edx, 0FA0h; dwSpinCount
0x18000537f  lea     rcx, CriticalSection; lpCriticalSection
0x180005386  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000538c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180005393  call    cs:__imp_GetModuleHandleW
0x180005399  mov     rbx, rax
0x18000539c  test    rax, rax
0x18000539f  jnz     short loc_1800053B6
0x1800053a1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800053a8  call    cs:__imp_GetModuleHandleW
0x1800053ae  mov     rbx, rax
0x1800053b1  test    rax, rax
0x1800053b4  jz      short loc_180005435
0x1800053b6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x1800053bd  mov     rcx, rbx; hModule
0x1800053c0  call    cs:__imp_GetProcAddress
0x1800053c6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800053cd  mov     rcx, rbx; hModule
0x1800053d0  mov     rdi, rax
0x1800053d3  call    cs:__imp_GetProcAddress
0x1800053d9  test    rdi, rdi
0x1800053dc  jz      short loc_1800053F3
0x1800053de  test    rax, rax
0x1800053e1  jz      short loc_1800053F3
0x1800053e3  mov     cs:qword_18006DDB8, rdi
0x1800053ea  mov     cs:qword_18006DDC0, rax
0x1800053f1  jmp     short loc_180005411
0x1800053f3  xor     r9d, r9d; lpName
0x1800053f6  xor     r8d, r8d; bInitialState
0x1800053f9  xor     ecx, ecx; lpEventAttributes
0x1800053fb  lea     edx, [r9+1]; bManualReset
0x1800053ff  call    cs:__imp_CreateEventW
0x180005405  mov     cs:hHandle, rax
0x18000540c  test    rax, rax
0x18000540f  jz      short loc_180005435
0x180005411  xor     ecx, ecx
0x180005413  call    __scrt_initialize_onexit_tables
0x180005418  test    al, al
0x18000541a  jz      short loc_180005435
0x18000541c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180005423  call    atexit
0x180005428  mov     rbx, [rsp+28h+arg_0]
0x18000542d  xor     eax, eax
0x18000542f  add     rsp, 20h
0x180005433  pop     rdi
0x180005434  retn
0x180005435  mov     ecx, 7
0x18000543a  call    __scrt_fastfail
```
