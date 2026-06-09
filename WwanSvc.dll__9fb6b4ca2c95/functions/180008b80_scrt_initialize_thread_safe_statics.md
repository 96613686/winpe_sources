# __scrt_initialize_thread_safe_statics

- ea: `0x180008b80`
- end: `0x180008c50`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18000888c`
- `0x180008a5c`
- `0x180008b80`
- `0x180009250`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008bd0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008be3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008bd0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008be3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008ba3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008bb8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008ba3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008bb8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180008c0f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180008c0f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180008b96`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180008b96`

## string_xrefs

- `0x180008b9c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180008bb1`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_1801520B0, 0xFA0u);
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
    qword_1801520D8 = (__int64)ProcAddress;
    qword_1801520E0 = (__int64)v2;
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
0x180008b80  mov     [rsp+arg_0], rbx
0x180008b85  push    rdi
0x180008b86  sub     rsp, 20h
0x180008b8a  mov     edx, 0FA0h; dwSpinCount
0x180008b8f  lea     rcx, stru_1801520B0; lpCriticalSection
0x180008b96  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180008b9c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180008ba3  call    cs:__imp_GetModuleHandleW
0x180008ba9  mov     rbx, rax
0x180008bac  test    rax, rax
0x180008baf  jnz     short loc_180008BC6
0x180008bb1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180008bb8  call    cs:__imp_GetModuleHandleW
0x180008bbe  mov     rbx, rax
0x180008bc1  test    rax, rax
0x180008bc4  jz      short loc_180008C45
0x180008bc6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x180008bcd  mov     rcx, rbx; hModule
0x180008bd0  call    cs:__imp_GetProcAddress
0x180008bd6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180008bdd  mov     rcx, rbx; hModule
0x180008be0  mov     rdi, rax
0x180008be3  call    cs:__imp_GetProcAddress
0x180008be9  test    rdi, rdi
0x180008bec  jz      short loc_180008C03
0x180008bee  test    rax, rax
0x180008bf1  jz      short loc_180008C03
0x180008bf3  mov     cs:qword_1801520D8, rdi
0x180008bfa  mov     cs:qword_1801520E0, rax
0x180008c01  jmp     short loc_180008C21
0x180008c03  xor     r9d, r9d; lpName
0x180008c06  xor     r8d, r8d; bInitialState
0x180008c09  xor     ecx, ecx; lpEventAttributes
0x180008c0b  lea     edx, [r9+1]; bManualReset
0x180008c0f  call    cs:__imp_CreateEventW
0x180008c15  mov     cs:hHandle, rax
0x180008c1c  test    rax, rax
0x180008c1f  jz      short loc_180008C45
0x180008c21  xor     ecx, ecx
0x180008c23  call    __scrt_initialize_onexit_tables
0x180008c28  test    al, al
0x180008c2a  jz      short loc_180008C45
0x180008c2c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180008c33  call    atexit
0x180008c38  mov     rbx, [rsp+28h+arg_0]
0x180008c3d  xor     eax, eax
0x180008c3f  add     rsp, 20h
0x180008c43  pop     rdi
0x180008c44  retn
0x180008c45  mov     ecx, 7
0x180008c4a  call    __scrt_fastfail
```
