# __scrt_initialize_thread_safe_statics

- ea: `0x180046b80`
- end: `0x180046c50`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180043ee0`
- `0x1800440b0`
- `0x180044224`
- `0x180046b80`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180046ba3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180046bb8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180046ba3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180046bb8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180046bd0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180046be3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180046bd0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180046be3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180046b96`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180046b96`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180046c0f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180046c0f`

## string_xrefs

- `0x180046b9c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180046bb1`: `kernel32.dll`

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
    qword_180091A20 = (__int64)ProcAddress;
    qword_180091A28 = (__int64)v2;
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
0x180046b80  mov     [rsp+arg_0], rbx
0x180046b85  push    rdi
0x180046b86  sub     rsp, 20h
0x180046b8a  mov     edx, 0FA0h; dwSpinCount
0x180046b8f  lea     rcx, CriticalSection; lpCriticalSection
0x180046b96  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180046b9c  lea     rcx, aApiMsWinCoreSy_2; "api-ms-win-core-synch-l1-2-0.dll"
0x180046ba3  call    cs:__imp_GetModuleHandleW
0x180046ba9  mov     rbx, rax
0x180046bac  test    rax, rax
0x180046baf  jnz     short loc_180046BC6
0x180046bb1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180046bb8  call    cs:__imp_GetModuleHandleW
0x180046bbe  mov     rbx, rax
0x180046bc1  test    rax, rax
0x180046bc4  jz      short loc_180046C45
0x180046bc6  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x180046bcd  mov     rcx, rbx; hModule
0x180046bd0  call    cs:__imp_GetProcAddress
0x180046bd6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180046bdd  mov     rcx, rbx; hModule
0x180046be0  mov     rdi, rax
0x180046be3  call    cs:__imp_GetProcAddress
0x180046be9  test    rdi, rdi
0x180046bec  jz      short loc_180046C03
0x180046bee  test    rax, rax
0x180046bf1  jz      short loc_180046C03
0x180046bf3  mov     cs:qword_180091A20, rdi
0x180046bfa  mov     cs:qword_180091A28, rax
0x180046c01  jmp     short loc_180046C21
0x180046c03  xor     r9d, r9d; lpName
0x180046c06  xor     r8d, r8d; bInitialState
0x180046c09  xor     ecx, ecx; lpEventAttributes
0x180046c0b  lea     edx, [r9+1]; bManualReset
0x180046c0f  call    cs:__imp_CreateEventW
0x180046c15  mov     cs:hHandle, rax
0x180046c1c  test    rax, rax
0x180046c1f  jz      short loc_180046C45
0x180046c21  xor     ecx, ecx
0x180046c23  call    __scrt_initialize_onexit_tables
0x180046c28  test    al, al
0x180046c2a  jz      short loc_180046C45
0x180046c2c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180046c33  call    atexit
0x180046c38  mov     rbx, [rsp+28h+arg_0]
0x180046c3d  xor     eax, eax
0x180046c3f  add     rsp, 20h
0x180046c43  pop     rdi
0x180046c44  retn
0x180046c45  mov     ecx, 7
0x180046c4a  call    __scrt_fastfail
```
