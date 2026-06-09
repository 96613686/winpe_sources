# __scrt_initialize_thread_safe_statics

- ea: `0x180022360`
- end: `0x180022430`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180021d24`
- `0x180021ef4`
- `0x180021f24`
- `0x180022360`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800223b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800223c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800223b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800223c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180022383`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180022398`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180022383`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180022398`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800223ef`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800223ef`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180022376`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180022376`

## string_xrefs

- `0x18002237c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180022391`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_180040230, 0xFA0u);
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
    qword_180040258 = (__int64)ProcAddress;
    qword_180040260 = (__int64)v2;
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
0x180022360  mov     [rsp+arg_0], rbx
0x180022365  push    rdi
0x180022366  sub     rsp, 20h
0x18002236a  mov     edx, 0FA0h; dwSpinCount
0x18002236f  lea     rcx, stru_180040230; lpCriticalSection
0x180022376  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18002237c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180022383  call    cs:__imp_GetModuleHandleW
0x180022389  mov     rbx, rax
0x18002238c  test    rax, rax
0x18002238f  jnz     short loc_1800223A6
0x180022391  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180022398  call    cs:__imp_GetModuleHandleW
0x18002239e  mov     rbx, rax
0x1800223a1  test    rax, rax
0x1800223a4  jz      short loc_180022425
0x1800223a6  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x1800223ad  mov     rcx, rbx; hModule
0x1800223b0  call    cs:__imp_GetProcAddress
0x1800223b6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800223bd  mov     rcx, rbx; hModule
0x1800223c0  mov     rdi, rax
0x1800223c3  call    cs:__imp_GetProcAddress
0x1800223c9  test    rdi, rdi
0x1800223cc  jz      short loc_1800223E3
0x1800223ce  test    rax, rax
0x1800223d1  jz      short loc_1800223E3
0x1800223d3  mov     cs:qword_180040258, rdi
0x1800223da  mov     cs:qword_180040260, rax
0x1800223e1  jmp     short loc_180022401
0x1800223e3  xor     r9d, r9d; lpName
0x1800223e6  xor     r8d, r8d; bInitialState
0x1800223e9  xor     ecx, ecx; lpEventAttributes
0x1800223eb  lea     edx, [r9+1]; bManualReset
0x1800223ef  call    cs:__imp_CreateEventW
0x1800223f5  mov     cs:hHandle, rax
0x1800223fc  test    rax, rax
0x1800223ff  jz      short loc_180022425
0x180022401  xor     ecx, ecx
0x180022403  call    __scrt_initialize_onexit_tables
0x180022408  test    al, al
0x18002240a  jz      short loc_180022425
0x18002240c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180022413  call    atexit
0x180022418  mov     rbx, [rsp+28h+arg_0]
0x18002241d  xor     eax, eax
0x18002241f  add     rsp, 20h
0x180022423  pop     rdi
0x180022424  retn
0x180022425  mov     ecx, 7
0x18002242a  call    __scrt_fastfail
```
