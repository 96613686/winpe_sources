# __scrt_initialize_thread_safe_statics

- ea: `0x140003630`
- end: `0x140003700`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x140002b84`
- `0x140002d54`
- `0x140002f10`
- `0x140003630`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140003653`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140003668`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140003653`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140003668`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140003680`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140003693`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140003680`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140003693`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x140003646`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x140003646`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400036bf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400036bf`

## string_xrefs

- `0x14000364c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x140003661`: `kernel32.dll`

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
    qword_1400255B0 = (__int64)ProcAddress;
    qword_1400255B8 = (__int64)v2;
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
0x140003630  mov     [rsp+arg_0], rbx
0x140003635  push    rdi
0x140003636  sub     rsp, 20h
0x14000363a  mov     edx, 0FA0h; dwSpinCount
0x14000363f  lea     rcx, CriticalSection; lpCriticalSection
0x140003646  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x14000364c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x140003653  call    cs:__imp_GetModuleHandleW
0x140003659  mov     rbx, rax
0x14000365c  test    rax, rax
0x14000365f  jnz     short loc_140003676
0x140003661  lea     rcx, aKernel32Dll; "kernel32.dll"
0x140003668  call    cs:__imp_GetModuleHandleW
0x14000366e  mov     rbx, rax
0x140003671  test    rax, rax
0x140003674  jz      short loc_1400036F5
0x140003676  lea     rdx, ProcName; "SleepConditionVariableCS"
0x14000367d  mov     rcx, rbx; hModule
0x140003680  call    cs:__imp_GetProcAddress
0x140003686  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x14000368d  mov     rcx, rbx; hModule
0x140003690  mov     rdi, rax
0x140003693  call    cs:__imp_GetProcAddress
0x140003699  test    rdi, rdi
0x14000369c  jz      short loc_1400036B3
0x14000369e  test    rax, rax
0x1400036a1  jz      short loc_1400036B3
0x1400036a3  mov     cs:qword_1400255B0, rdi
0x1400036aa  mov     cs:qword_1400255B8, rax
0x1400036b1  jmp     short loc_1400036D1
0x1400036b3  xor     r9d, r9d; lpName
0x1400036b6  xor     r8d, r8d; bInitialState
0x1400036b9  xor     ecx, ecx; lpEventAttributes
0x1400036bb  lea     edx, [r9+1]; bManualReset
0x1400036bf  call    cs:__imp_CreateEventW
0x1400036c5  mov     cs:hHandle, rax
0x1400036cc  test    rax, rax
0x1400036cf  jz      short loc_1400036F5
0x1400036d1  xor     ecx, ecx
0x1400036d3  call    __scrt_initialize_onexit_tables
0x1400036d8  test    al, al
0x1400036da  jz      short loc_1400036F5
0x1400036dc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1400036e3  call    atexit
0x1400036e8  mov     rbx, [rsp+28h+arg_0]
0x1400036ed  xor     eax, eax
0x1400036ef  add     rsp, 20h
0x1400036f3  pop     rdi
0x1400036f4  retn
0x1400036f5  mov     ecx, 7
0x1400036fa  call    __scrt_fastfail
```
