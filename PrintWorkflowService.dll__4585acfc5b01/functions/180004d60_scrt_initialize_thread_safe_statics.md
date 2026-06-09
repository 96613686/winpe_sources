# __scrt_initialize_thread_safe_statics

- ea: `0x180004d60`
- end: `0x180004e30`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180003fc4`
- `0x180004194`
- `0x1800046f0`
- `0x180004d60`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004db0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004dc3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004db0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004dc3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004d83`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004d98`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004d83`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004d98`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004def`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004def`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004d76`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004d76`

## string_xrefs

- `0x180004d7c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180004d91`: `kernel32.dll`

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
    qword_180083A60 = (__int64)ProcAddress;
    qword_180083A68 = (__int64)v2;
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
0x180004d60  mov     [rsp+arg_0], rbx
0x180004d65  push    rdi
0x180004d66  sub     rsp, 20h
0x180004d6a  mov     edx, 0FA0h; dwSpinCount
0x180004d6f  lea     rcx, CriticalSection; lpCriticalSection
0x180004d76  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180004d7c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180004d83  call    cs:__imp_GetModuleHandleW
0x180004d89  mov     rbx, rax
0x180004d8c  test    rax, rax
0x180004d8f  jnz     short loc_180004DA6
0x180004d91  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180004d98  call    cs:__imp_GetModuleHandleW
0x180004d9e  mov     rbx, rax
0x180004da1  test    rax, rax
0x180004da4  jz      short loc_180004E25
0x180004da6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x180004dad  mov     rcx, rbx; hModule
0x180004db0  call    cs:__imp_GetProcAddress
0x180004db6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180004dbd  mov     rcx, rbx; hModule
0x180004dc0  mov     rdi, rax
0x180004dc3  call    cs:__imp_GetProcAddress
0x180004dc9  test    rdi, rdi
0x180004dcc  jz      short loc_180004DE3
0x180004dce  test    rax, rax
0x180004dd1  jz      short loc_180004DE3
0x180004dd3  mov     cs:qword_180083A60, rdi
0x180004dda  mov     cs:qword_180083A68, rax
0x180004de1  jmp     short loc_180004E01
0x180004de3  xor     r9d, r9d; lpName
0x180004de6  xor     r8d, r8d; bInitialState
0x180004de9  xor     ecx, ecx; lpEventAttributes
0x180004deb  lea     edx, [r9+1]; bManualReset
0x180004def  call    cs:__imp_CreateEventW
0x180004df5  mov     cs:hHandle, rax
0x180004dfc  test    rax, rax
0x180004dff  jz      short loc_180004E25
0x180004e01  xor     ecx, ecx
0x180004e03  call    __scrt_initialize_onexit_tables
0x180004e08  test    al, al
0x180004e0a  jz      short loc_180004E25
0x180004e0c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180004e13  call    atexit
0x180004e18  mov     rbx, [rsp+28h+arg_0]
0x180004e1d  xor     eax, eax
0x180004e1f  add     rsp, 20h
0x180004e23  pop     rdi
0x180004e24  retn
0x180004e25  mov     ecx, 7
0x180004e2a  call    __scrt_fastfail
```
