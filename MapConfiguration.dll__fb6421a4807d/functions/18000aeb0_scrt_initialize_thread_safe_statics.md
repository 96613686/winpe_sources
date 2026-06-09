# __scrt_initialize_thread_safe_statics

- ea: `0x18000aeb0`
- end: `0x18000af80`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180009798`
- `0x180009968`
- `0x180009b08`
- `0x18000aeb0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000af00`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000af13`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000af00`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000af13`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000aed3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000aee8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000aed3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000aee8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000af3f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000af3f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000aec6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000aec6`

## string_xrefs

- `0x18000aecc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x18000aee1`: `kernel32.dll`

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
    qword_18007B560 = (__int64)ProcAddress;
    qword_18007B568 = (__int64)v2;
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
0x18000aeb0  mov     [rsp+arg_0], rbx
0x18000aeb5  push    rdi
0x18000aeb6  sub     rsp, 20h
0x18000aeba  mov     edx, 0FA0h; dwSpinCount
0x18000aebf  lea     rcx, CriticalSection; lpCriticalSection
0x18000aec6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000aecc  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x18000aed3  call    cs:__imp_GetModuleHandleW
0x18000aed9  mov     rbx, rax
0x18000aedc  test    rax, rax
0x18000aedf  jnz     short loc_18000AEF6
0x18000aee1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x18000aee8  call    cs:__imp_GetModuleHandleW
0x18000aeee  mov     rbx, rax
0x18000aef1  test    rax, rax
0x18000aef4  jz      short loc_18000AF75
0x18000aef6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18000aefd  mov     rcx, rbx; hModule
0x18000af00  call    cs:__imp_GetProcAddress
0x18000af06  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000af0d  mov     rcx, rbx; hModule
0x18000af10  mov     rdi, rax
0x18000af13  call    cs:__imp_GetProcAddress
0x18000af19  test    rdi, rdi
0x18000af1c  jz      short loc_18000AF33
0x18000af1e  test    rax, rax
0x18000af21  jz      short loc_18000AF33
0x18000af23  mov     cs:qword_18007B560, rdi
0x18000af2a  mov     cs:qword_18007B568, rax
0x18000af31  jmp     short loc_18000AF51
0x18000af33  xor     r9d, r9d; lpName
0x18000af36  xor     r8d, r8d; bInitialState
0x18000af39  xor     ecx, ecx; lpEventAttributes
0x18000af3b  lea     edx, [r9+1]; bManualReset
0x18000af3f  call    cs:__imp_CreateEventW
0x18000af45  mov     cs:hHandle, rax
0x18000af4c  test    rax, rax
0x18000af4f  jz      short loc_18000AF75
0x18000af51  xor     ecx, ecx
0x18000af53  call    __scrt_initialize_onexit_tables
0x18000af58  test    al, al
0x18000af5a  jz      short loc_18000AF75
0x18000af5c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x18000af63  call    atexit
0x18000af68  mov     rbx, [rsp+28h+arg_0]
0x18000af6d  xor     eax, eax
0x18000af6f  add     rsp, 20h
0x18000af73  pop     rdi
0x18000af74  retn
0x18000af75  mov     ecx, 7
0x18000af7a  call    __scrt_fastfail
```
