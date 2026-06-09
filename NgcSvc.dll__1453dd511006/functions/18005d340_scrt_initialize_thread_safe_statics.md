# __scrt_initialize_thread_safe_statics

- ea: `0x18005d340`
- end: `0x18005d410`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18005d0c0`
- `0x18005d290`
- `0x18005d340`
- `0x18005da64`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005d390`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005d3a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005d390`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005d3a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005d363`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005d378`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005d363`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005d378`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18005d356`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18005d356`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005d3cf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005d3cf`

## string_xrefs

- `0x18005d35c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x18005d371`: `kernel32.dll`

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
    qword_180122A90 = (__int64)ProcAddress;
    qword_180122A98 = (__int64)v2;
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
0x18005d340  mov     [rsp+arg_0], rbx
0x18005d345  push    rdi
0x18005d346  sub     rsp, 20h
0x18005d34a  mov     edx, 0FA0h; dwSpinCount
0x18005d34f  lea     rcx, CriticalSection; lpCriticalSection
0x18005d356  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18005d35c  lea     rcx, aApiMsWinCoreSy_3; "api-ms-win-core-synch-l1-2-0.dll"
0x18005d363  call    cs:__imp_GetModuleHandleW
0x18005d369  mov     rbx, rax
0x18005d36c  test    rax, rax
0x18005d36f  jnz     short loc_18005D386
0x18005d371  lea     rcx, aKernel32Dll; "kernel32.dll"
0x18005d378  call    cs:__imp_GetModuleHandleW
0x18005d37e  mov     rbx, rax
0x18005d381  test    rax, rax
0x18005d384  jz      short loc_18005D405
0x18005d386  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x18005d38d  mov     rcx, rbx; hModule
0x18005d390  call    cs:__imp_GetProcAddress
0x18005d396  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18005d39d  mov     rcx, rbx; hModule
0x18005d3a0  mov     rdi, rax
0x18005d3a3  call    cs:__imp_GetProcAddress
0x18005d3a9  test    rdi, rdi
0x18005d3ac  jz      short loc_18005D3C3
0x18005d3ae  test    rax, rax
0x18005d3b1  jz      short loc_18005D3C3
0x18005d3b3  mov     cs:qword_180122A90, rdi
0x18005d3ba  mov     cs:qword_180122A98, rax
0x18005d3c1  jmp     short loc_18005D3E1
0x18005d3c3  xor     r9d, r9d; lpName
0x18005d3c6  xor     r8d, r8d; bInitialState
0x18005d3c9  xor     ecx, ecx; lpEventAttributes
0x18005d3cb  lea     edx, [r9+1]; bManualReset
0x18005d3cf  call    cs:__imp_CreateEventW
0x18005d3d5  mov     cs:hHandle, rax
0x18005d3dc  test    rax, rax
0x18005d3df  jz      short loc_18005D405
0x18005d3e1  xor     ecx, ecx
0x18005d3e3  call    __scrt_initialize_onexit_tables
0x18005d3e8  test    al, al
0x18005d3ea  jz      short loc_18005D405
0x18005d3ec  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x18005d3f3  call    atexit
0x18005d3f8  mov     rbx, [rsp+28h+arg_0]
0x18005d3fd  xor     eax, eax
0x18005d3ff  add     rsp, 20h
0x18005d403  pop     rdi
0x18005d404  retn
0x18005d405  mov     ecx, 7
0x18005d40a  call    __scrt_fastfail
```
