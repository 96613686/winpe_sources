# __scrt_initialize_thread_safe_statics

- ea: `0x140003110`
- end: `0x1400031e0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x140002484`
- `0x140002654`
- `0x1400027b8`
- `0x140003110`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x140003160`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x140003173`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x140003160`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x140003173`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x140003133`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x140003148`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x140003133`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x140003148`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x140003126`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x140003126`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000319f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000319f`

## string_xrefs

- `0x14000312c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x140003141`: `kernel32.dll`

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
    qword_14003F3B0 = (__int64)ProcAddress;
    qword_14003F3B8 = (__int64)v2;
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
0x140003110  mov     [rsp+arg_0], rbx
0x140003115  push    rdi
0x140003116  sub     rsp, 20h
0x14000311a  mov     edx, 0FA0h; dwSpinCount
0x14000311f  lea     rcx, CriticalSection; lpCriticalSection
0x140003126  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x14000312c  lea     rcx, aApiMsWinCoreSy_3; "api-ms-win-core-synch-l1-2-0.dll"
0x140003133  call    cs:__imp_GetModuleHandleW
0x140003139  mov     rbx, rax
0x14000313c  test    rax, rax
0x14000313f  jnz     short loc_140003156
0x140003141  lea     rcx, aKernel32Dll; "kernel32.dll"
0x140003148  call    cs:__imp_GetModuleHandleW
0x14000314e  mov     rbx, rax
0x140003151  test    rax, rax
0x140003154  jz      short loc_1400031D5
0x140003156  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x14000315d  mov     rcx, rbx; hModule
0x140003160  call    cs:__imp_GetProcAddress
0x140003166  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x14000316d  mov     rcx, rbx; hModule
0x140003170  mov     rdi, rax
0x140003173  call    cs:__imp_GetProcAddress
0x140003179  test    rdi, rdi
0x14000317c  jz      short loc_140003193
0x14000317e  test    rax, rax
0x140003181  jz      short loc_140003193
0x140003183  mov     cs:qword_14003F3B0, rdi
0x14000318a  mov     cs:qword_14003F3B8, rax
0x140003191  jmp     short loc_1400031B1
0x140003193  xor     r9d, r9d; lpName
0x140003196  xor     r8d, r8d; bInitialState
0x140003199  xor     ecx, ecx; lpEventAttributes
0x14000319b  lea     edx, [r9+1]; bManualReset
0x14000319f  call    cs:__imp_CreateEventW
0x1400031a5  mov     cs:hHandle, rax
0x1400031ac  test    rax, rax
0x1400031af  jz      short loc_1400031D5
0x1400031b1  xor     ecx, ecx
0x1400031b3  call    __scrt_initialize_onexit_tables
0x1400031b8  test    al, al
0x1400031ba  jz      short loc_1400031D5
0x1400031bc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1400031c3  call    atexit
0x1400031c8  mov     rbx, [rsp+28h+arg_0]
0x1400031cd  xor     eax, eax
0x1400031cf  add     rsp, 20h
0x1400031d3  pop     rdi
0x1400031d4  retn
0x1400031d5  mov     ecx, 7
0x1400031da  call    __scrt_fastfail
```
