# __scrt_initialize_thread_safe_statics

- ea: `0x1800035f0`
- end: `0x1800036c0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800035f0`
- `0x180003c20`
- `0x180003dd0`
- `0x180003df8`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x18000367f`
- `KERNEL32!CreateEventW` at `0x18000367f`
- `KERNEL32!GetModuleHandleW` at `0x180003613`
- `KERNEL32!GetModuleHandleW` at `0x180003628`
- `KERNEL32!GetModuleHandleW` at `0x180003613`
- `KERNEL32!GetModuleHandleW` at `0x180003628`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180003606`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180003606`
- `KERNEL32!GetProcAddress` at `0x180003640`
- `KERNEL32!GetProcAddress` at `0x180003653`
- `KERNEL32!GetProcAddress` at `0x180003640`
- `KERNEL32!GetProcAddress` at `0x180003653`

## string_xrefs

- `0x180003621`: `kernel32.dll`
- `0x18000360c`: `api-ms-win-core-synch-l1-2-0.dll`

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
    qword_180007218 = (__int64)ProcAddress;
    qword_180007220 = (__int64)v2;
  }
  else
  {
    hHandle = CreateEventW(0, 1, 0, 0);
    if ( !hHandle )
      goto LABEL_9;
  }
  if ( !(unsigned __int8)_scrt_initialize_onexit_tables(0) )
  {
LABEL_9:
    _scrt_fastfail(7);
    __debugbreak();
  }
  atexit(_scrt_uninitialize_thread_safe_statics);
  return 0;
}

```

## disassembly

```asm
0x1800035f0  mov     [rsp+arg_0], rbx
0x1800035f5  push    rdi
0x1800035f6  sub     rsp, 20h
0x1800035fa  mov     edx, 0FA0h; dwSpinCount
0x1800035ff  lea     rcx, CriticalSection; lpCriticalSection
0x180003606  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000360c  lea     rcx, ModuleName
0x180003613  call    cs:__imp_GetModuleHandleW
0x180003619  mov     rbx, rax
0x18000361c  test    rax, rax
0x18000361f  jnz     short loc_180003636
0x180003621  lea     rcx, aKernel32Dll_0
0x180003628  call    cs:__imp_GetModuleHandleW
0x18000362e  mov     rbx, rax
0x180003631  test    rax, rax
0x180003634  jz      short loc_1800036B5
0x180003636  lea     rdx, ProcName
0x18000363d  mov     rcx, rbx; hModule
0x180003640  call    cs:__imp_GetProcAddress
0x180003646  lea     rdx, aWakeallconditi
0x18000364d  mov     rcx, rbx; hModule
0x180003650  mov     rdi, rax
0x180003653  call    cs:__imp_GetProcAddress
0x180003659  test    rdi, rdi
0x18000365c  jz      short loc_180003673
0x18000365e  test    rax, rax
0x180003661  jz      short loc_180003673
0x180003663  mov     cs:qword_180007218, rdi
0x18000366a  mov     cs:qword_180007220, rax
0x180003671  jmp     short loc_180003691
0x180003673  xor     r9d, r9d; lpName
0x180003676  xor     r8d, r8d; bInitialState
0x180003679  xor     ecx, ecx; lpEventAttributes
0x18000367b  lea     edx, [r9+1]; bManualReset
0x18000367f  call    cs:__imp_CreateEventW
0x180003685  mov     cs:hHandle, rax
0x18000368c  test    rax, rax
0x18000368f  jz      short loc_1800036B5
0x180003691  xor     ecx, ecx
0x180003693  call    __scrt_initialize_onexit_tables
0x180003698  test    al, al
0x18000369a  jz      short loc_1800036B5
0x18000369c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1800036a3  call    atexit
0x1800036a8  mov     rbx, [rsp+28h+arg_0]
0x1800036ad  xor     eax, eax
0x1800036af  add     rsp, 20h
0x1800036b3  pop     rdi
0x1800036b4  retn
0x1800036b5  mov     ecx, 7
0x1800036ba  call    __scrt_fastfail
0x1800036bf  int     3; Trap to Debugger
```
