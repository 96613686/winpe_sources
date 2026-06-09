# __scrt_initialize_thread_safe_statics

- ea: `0x180088700`
- end: `0x1800887d0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800865ac`
- `0x18008677c`
- `0x180086968`
- `0x180088700`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180088750`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180088763`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180088750`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180088763`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180088723`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180088738`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180088723`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180088738`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180088716`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180088716`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008878f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008878f`

## string_xrefs

- `0x18008871c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180088731`: `kernel32.dll`

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
    qword_1800FBD28 = (__int64)ProcAddress;
    qword_1800FBD30 = (__int64)v2;
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
0x180088700  mov     [rsp+arg_0], rbx
0x180088705  push    rdi
0x180088706  sub     rsp, 20h
0x18008870a  mov     edx, 0FA0h; dwSpinCount
0x18008870f  lea     rcx, CriticalSection; lpCriticalSection
0x180088716  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18008871c  lea     rcx, aApiMsWinCoreSy_2; "api-ms-win-core-synch-l1-2-0.dll"
0x180088723  call    cs:__imp_GetModuleHandleW
0x180088729  mov     rbx, rax
0x18008872c  test    rax, rax
0x18008872f  jnz     short loc_180088746
0x180088731  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180088738  call    cs:__imp_GetModuleHandleW
0x18008873e  mov     rbx, rax
0x180088741  test    rax, rax
0x180088744  jz      short loc_1800887C5
0x180088746  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x18008874d  mov     rcx, rbx; hModule
0x180088750  call    cs:__imp_GetProcAddress
0x180088756  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18008875d  mov     rcx, rbx; hModule
0x180088760  mov     rdi, rax
0x180088763  call    cs:__imp_GetProcAddress
0x180088769  test    rdi, rdi
0x18008876c  jz      short loc_180088783
0x18008876e  test    rax, rax
0x180088771  jz      short loc_180088783
0x180088773  mov     cs:qword_1800FBD28, rdi
0x18008877a  mov     cs:qword_1800FBD30, rax
0x180088781  jmp     short loc_1800887A1
0x180088783  xor     r9d, r9d; lpName
0x180088786  xor     r8d, r8d; bInitialState
0x180088789  xor     ecx, ecx; lpEventAttributes
0x18008878b  lea     edx, [r9+1]; bManualReset
0x18008878f  call    cs:__imp_CreateEventW
0x180088795  mov     cs:hHandle, rax
0x18008879c  test    rax, rax
0x18008879f  jz      short loc_1800887C5
0x1800887a1  xor     ecx, ecx
0x1800887a3  call    __scrt_initialize_onexit_tables
0x1800887a8  test    al, al
0x1800887aa  jz      short loc_1800887C5
0x1800887ac  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1800887b3  call    atexit
0x1800887b8  mov     rbx, [rsp+28h+arg_0]
0x1800887bd  xor     eax, eax
0x1800887bf  add     rsp, 20h
0x1800887c3  pop     rdi
0x1800887c4  retn
0x1800887c5  mov     ecx, 7
0x1800887ca  call    __scrt_fastfail
```
