# __scrt_initialize_thread_safe_statics

- ea: `0x140003040`
- end: `0x140003110`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1400023b4`
- `0x140002584`
- `0x1400026dc`
- `0x140003040`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x140003090`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1400030a3`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x140003090`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1400030a3`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x140003063`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x140003078`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x140003063`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x140003078`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400030cf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400030cf`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x140003056`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x140003056`

## string_xrefs

- `0x14000305c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x140003071`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_140052288, 0xFA0u);
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
    qword_1400522B0 = (__int64)ProcAddress;
    qword_1400522B8 = (__int64)v2;
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
0x140003040  mov     [rsp+arg_0], rbx
0x140003045  push    rdi
0x140003046  sub     rsp, 20h
0x14000304a  mov     edx, 0FA0h; dwSpinCount
0x14000304f  lea     rcx, stru_140052288; lpCriticalSection
0x140003056  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x14000305c  lea     rcx, aApiMsWinCoreSy_3; "api-ms-win-core-synch-l1-2-0.dll"
0x140003063  call    cs:__imp_GetModuleHandleW
0x140003069  mov     rbx, rax
0x14000306c  test    rax, rax
0x14000306f  jnz     short loc_140003086
0x140003071  lea     rcx, aKernel32Dll; "kernel32.dll"
0x140003078  call    cs:__imp_GetModuleHandleW
0x14000307e  mov     rbx, rax
0x140003081  test    rax, rax
0x140003084  jz      short loc_140003105
0x140003086  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x14000308d  mov     rcx, rbx; hModule
0x140003090  call    cs:__imp_GetProcAddress
0x140003096  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x14000309d  mov     rcx, rbx; hModule
0x1400030a0  mov     rdi, rax
0x1400030a3  call    cs:__imp_GetProcAddress
0x1400030a9  test    rdi, rdi
0x1400030ac  jz      short loc_1400030C3
0x1400030ae  test    rax, rax
0x1400030b1  jz      short loc_1400030C3
0x1400030b3  mov     cs:qword_1400522B0, rdi
0x1400030ba  mov     cs:qword_1400522B8, rax
0x1400030c1  jmp     short loc_1400030E1
0x1400030c3  xor     r9d, r9d; lpName
0x1400030c6  xor     r8d, r8d; bInitialState
0x1400030c9  xor     ecx, ecx; lpEventAttributes
0x1400030cb  lea     edx, [r9+1]; bManualReset
0x1400030cf  call    cs:__imp_CreateEventW
0x1400030d5  mov     cs:hHandle, rax
0x1400030dc  test    rax, rax
0x1400030df  jz      short loc_140003105
0x1400030e1  xor     ecx, ecx
0x1400030e3  call    __scrt_initialize_onexit_tables
0x1400030e8  test    al, al
0x1400030ea  jz      short loc_140003105
0x1400030ec  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1400030f3  call    atexit
0x1400030f8  mov     rbx, [rsp+28h+arg_0]
0x1400030fd  xor     eax, eax
0x1400030ff  add     rsp, 20h
0x140003103  pop     rdi
0x140003104  retn
0x140003105  mov     ecx, 7
0x14000310a  call    __scrt_fastfail
```
