# __scrt_initialize_thread_safe_statics

- ea: `0x18002cb20`
- end: `0x18002cbf0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18002c8f0`
- `0x18002cac0`
- `0x18002cb20`
- `0x18002d294`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002cb70`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002cb83`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002cb70`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002cb83`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002cb43`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002cb58`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002cb43`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002cb58`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18002cb36`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18002cb36`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002cbaf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002cbaf`

## string_xrefs

- `0x18002cb3c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x18002cb51`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_1800C0628, 0xFA0u);
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
    qword_1800C0650 = (__int64)ProcAddress;
    qword_1800C0658 = (__int64)v2;
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
0x18002cb20  mov     [rsp+arg_0], rbx
0x18002cb25  push    rdi
0x18002cb26  sub     rsp, 20h
0x18002cb2a  mov     edx, 0FA0h; dwSpinCount
0x18002cb2f  lea     rcx, stru_1800C0628; lpCriticalSection
0x18002cb36  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18002cb3c  lea     rcx, aApiMsWinCoreSy_3; "api-ms-win-core-synch-l1-2-0.dll"
0x18002cb43  call    cs:__imp_GetModuleHandleW
0x18002cb49  mov     rbx, rax
0x18002cb4c  test    rax, rax
0x18002cb4f  jnz     short loc_18002CB66
0x18002cb51  lea     rcx, aKernel32Dll; "kernel32.dll"
0x18002cb58  call    cs:__imp_GetModuleHandleW
0x18002cb5e  mov     rbx, rax
0x18002cb61  test    rax, rax
0x18002cb64  jz      short loc_18002CBE5
0x18002cb66  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x18002cb6d  mov     rcx, rbx; hModule
0x18002cb70  call    cs:__imp_GetProcAddress
0x18002cb76  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18002cb7d  mov     rcx, rbx; hModule
0x18002cb80  mov     rdi, rax
0x18002cb83  call    cs:__imp_GetProcAddress
0x18002cb89  test    rdi, rdi
0x18002cb8c  jz      short loc_18002CBA3
0x18002cb8e  test    rax, rax
0x18002cb91  jz      short loc_18002CBA3
0x18002cb93  mov     cs:qword_1800C0650, rdi
0x18002cb9a  mov     cs:qword_1800C0658, rax
0x18002cba1  jmp     short loc_18002CBC1
0x18002cba3  xor     r9d, r9d; lpName
0x18002cba6  xor     r8d, r8d; bInitialState
0x18002cba9  xor     ecx, ecx; lpEventAttributes
0x18002cbab  lea     edx, [r9+1]; bManualReset
0x18002cbaf  call    cs:__imp_CreateEventW
0x18002cbb5  mov     cs:hHandle, rax
0x18002cbbc  test    rax, rax
0x18002cbbf  jz      short loc_18002CBE5
0x18002cbc1  xor     ecx, ecx
0x18002cbc3  call    __scrt_initialize_onexit_tables
0x18002cbc8  test    al, al
0x18002cbca  jz      short loc_18002CBE5
0x18002cbcc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x18002cbd3  call    atexit
0x18002cbd8  mov     rbx, [rsp+28h+arg_0]
0x18002cbdd  xor     eax, eax
0x18002cbdf  add     rsp, 20h
0x18002cbe3  pop     rdi
0x18002cbe4  retn
0x18002cbe5  mov     ecx, 7
0x18002cbea  call    __scrt_fastfail
```
