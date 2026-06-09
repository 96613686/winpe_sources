# __scrt_initialize_thread_safe_statics

- ea: `0x140133aa0`
- end: `0x140133b70`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x140132ac0`
- `0x140132c90`
- `0x140132eb0`
- `0x140133aa0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140133ac3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140133ad8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140133ac3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140133ad8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140133af0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140133b03`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140133af0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140133b03`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140133b2f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140133b2f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x140133ab6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x140133ab6`

## string_xrefs

- `0x140133abc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x140133ad1`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_1403B7568, 0xFA0u);
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
    qword_1403B7590 = (__int64)ProcAddress;
    qword_1403B7598 = (__int64)v2;
  }
  else
  {
    hEvent = CreateEventW(0, 1, 0, 0);
    if ( !hEvent )
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
0x140133aa0  mov     [rsp+arg_0], rbx
0x140133aa5  push    rdi
0x140133aa6  sub     rsp, 20h
0x140133aaa  mov     edx, 0FA0h; dwSpinCount
0x140133aaf  lea     rcx, stru_1403B7568; lpCriticalSection
0x140133ab6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x140133abc  lea     rcx, aApiMsWinCoreSy_6; "api-ms-win-core-synch-l1-2-0.dll"
0x140133ac3  call    cs:__imp_GetModuleHandleW
0x140133ac9  mov     rbx, rax
0x140133acc  test    rax, rax
0x140133acf  jnz     short loc_140133AE6
0x140133ad1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x140133ad8  call    cs:__imp_GetModuleHandleW
0x140133ade  mov     rbx, rax
0x140133ae1  test    rax, rax
0x140133ae4  jz      short loc_140133B65
0x140133ae6  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x140133aed  mov     rcx, rbx; hModule
0x140133af0  call    cs:__imp_GetProcAddress
0x140133af6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x140133afd  mov     rcx, rbx; hModule
0x140133b00  mov     rdi, rax
0x140133b03  call    cs:__imp_GetProcAddress
0x140133b09  test    rdi, rdi
0x140133b0c  jz      short loc_140133B23
0x140133b0e  test    rax, rax
0x140133b11  jz      short loc_140133B23
0x140133b13  mov     cs:qword_1403B7590, rdi
0x140133b1a  mov     cs:qword_1403B7598, rax
0x140133b21  jmp     short loc_140133B41
0x140133b23  xor     r9d, r9d; lpName
0x140133b26  xor     r8d, r8d; bInitialState
0x140133b29  xor     ecx, ecx; lpEventAttributes
0x140133b2b  lea     edx, [r9+1]; bManualReset
0x140133b2f  call    cs:__imp_CreateEventW
0x140133b35  mov     cs:hEvent, rax
0x140133b3c  test    rax, rax
0x140133b3f  jz      short loc_140133B65
0x140133b41  xor     ecx, ecx
0x140133b43  call    __scrt_initialize_onexit_tables
0x140133b48  test    al, al
0x140133b4a  jz      short loc_140133B65
0x140133b4c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x140133b53  call    atexit
0x140133b58  mov     rbx, [rsp+28h+arg_0]
0x140133b5d  xor     eax, eax
0x140133b5f  add     rsp, 20h
0x140133b63  pop     rdi
0x140133b64  retn
0x140133b65  mov     ecx, 7
0x140133b6a  call    __scrt_fastfail
```
