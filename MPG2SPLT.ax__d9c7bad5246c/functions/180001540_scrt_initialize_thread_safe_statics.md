# __scrt_initialize_thread_safe_statics

- ea: `0x180001540`
- end: `0x180001610`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001540`
- `0x180001858`
- `0x180001a28`
- `0x180001a58`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180001563`
- `KERNEL32!GetModuleHandleW` at `0x180001578`
- `KERNEL32!GetModuleHandleW` at `0x180001563`
- `KERNEL32!GetModuleHandleW` at `0x180001578`
- `KERNEL32!GetProcAddress` at `0x180001590`
- `KERNEL32!GetProcAddress` at `0x1800015a3`
- `KERNEL32!GetProcAddress` at `0x180001590`
- `KERNEL32!GetProcAddress` at `0x1800015a3`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180001556`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180001556`
- `KERNEL32!CreateEventW` at `0x1800015cf`
- `KERNEL32!CreateEventW` at `0x1800015cf`

## string_xrefs

- `0x18000155c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180001571`: `kernel32.dll`

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
    qword_18003E390 = (__int64)ProcAddress;
    qword_18003E398 = (__int64)v2;
  }
  else
  {
    hObject = CreateEventW(0, 1, 0, 0);
    if ( !hObject )
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
0x180001540  mov     [rsp+arg_0], rbx
0x180001545  push    rdi
0x180001546  sub     rsp, 20h
0x18000154a  mov     edx, 0FA0h; dwSpinCount
0x18000154f  lea     rcx, CriticalSection; lpCriticalSection
0x180001556  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000155c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180001563  call    cs:__imp_GetModuleHandleW
0x180001569  mov     rbx, rax
0x18000156c  test    rax, rax
0x18000156f  jnz     short loc_180001586
0x180001571  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x180001578  call    cs:__imp_GetModuleHandleW
0x18000157e  mov     rbx, rax
0x180001581  test    rax, rax
0x180001584  jz      short loc_180001605
0x180001586  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18000158d  mov     rcx, rbx; hModule
0x180001590  call    cs:__imp_GetProcAddress
0x180001596  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000159d  mov     rcx, rbx; hModule
0x1800015a0  mov     rdi, rax
0x1800015a3  call    cs:__imp_GetProcAddress
0x1800015a9  test    rdi, rdi
0x1800015ac  jz      short loc_1800015C3
0x1800015ae  test    rax, rax
0x1800015b1  jz      short loc_1800015C3
0x1800015b3  mov     cs:qword_18003E390, rdi
0x1800015ba  mov     cs:qword_18003E398, rax
0x1800015c1  jmp     short loc_1800015E1
0x1800015c3  xor     r9d, r9d; lpName
0x1800015c6  xor     r8d, r8d; bInitialState
0x1800015c9  xor     ecx, ecx; lpEventAttributes
0x1800015cb  lea     edx, [r9+1]; bManualReset
0x1800015cf  call    cs:__imp_CreateEventW
0x1800015d5  mov     cs:hObject, rax
0x1800015dc  test    rax, rax
0x1800015df  jz      short loc_180001605
0x1800015e1  xor     ecx, ecx
0x1800015e3  call    __scrt_initialize_onexit_tables
0x1800015e8  test    al, al
0x1800015ea  jz      short loc_180001605
0x1800015ec  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1800015f3  call    atexit
0x1800015f8  mov     rbx, [rsp+28h+arg_0]
0x1800015fd  xor     eax, eax
0x1800015ff  add     rsp, 20h
0x180001603  pop     rdi
0x180001604  retn
0x180001605  mov     ecx, 7
0x18000160a  call    __scrt_fastfail
```
