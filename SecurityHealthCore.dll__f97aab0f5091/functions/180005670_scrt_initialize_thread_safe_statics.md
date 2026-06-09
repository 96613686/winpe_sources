# __scrt_initialize_thread_safe_statics

- ea: `0x180005670`
- end: `0x180005740`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800048f0`
- `0x180004ac0`
- `0x180004cf4`
- `0x180005670`

## import_xrefs

- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180005686`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180005686`
- `KERNEL32!GetProcAddress` at `0x1800056c0`
- `KERNEL32!GetProcAddress` at `0x1800056d3`
- `KERNEL32!GetProcAddress` at `0x1800056c0`
- `KERNEL32!GetProcAddress` at `0x1800056d3`
- `KERNEL32!GetModuleHandleW` at `0x180005693`
- `KERNEL32!GetModuleHandleW` at `0x1800056a8`
- `KERNEL32!GetModuleHandleW` at `0x180005693`
- `KERNEL32!GetModuleHandleW` at `0x1800056a8`
- `KERNEL32!CreateEventW` at `0x1800056ff`
- `KERNEL32!CreateEventW` at `0x1800056ff`

## string_xrefs

- `0x18000568c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800056a1`: `kernel32.dll`

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
    qword_180139A98 = (__int64)ProcAddress;
    qword_180139AA0 = (__int64)v2;
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
0x180005670  mov     [rsp+arg_0], rbx
0x180005675  push    rdi
0x180005676  sub     rsp, 20h
0x18000567a  mov     edx, 0FA0h; dwSpinCount
0x18000567f  lea     rcx, CriticalSection; lpCriticalSection
0x180005686  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000568c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180005693  call    cs:__imp_GetModuleHandleW
0x180005699  mov     rbx, rax
0x18000569c  test    rax, rax
0x18000569f  jnz     short loc_1800056B6
0x1800056a1  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x1800056a8  call    cs:__imp_GetModuleHandleW
0x1800056ae  mov     rbx, rax
0x1800056b1  test    rax, rax
0x1800056b4  jz      short loc_180005735
0x1800056b6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x1800056bd  mov     rcx, rbx; hModule
0x1800056c0  call    cs:__imp_GetProcAddress
0x1800056c6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800056cd  mov     rcx, rbx; hModule
0x1800056d0  mov     rdi, rax
0x1800056d3  call    cs:__imp_GetProcAddress
0x1800056d9  test    rdi, rdi
0x1800056dc  jz      short loc_1800056F3
0x1800056de  test    rax, rax
0x1800056e1  jz      short loc_1800056F3
0x1800056e3  mov     cs:qword_180139A98, rdi
0x1800056ea  mov     cs:qword_180139AA0, rax
0x1800056f1  jmp     short loc_180005711
0x1800056f3  xor     r9d, r9d; lpName
0x1800056f6  xor     r8d, r8d; bInitialState
0x1800056f9  xor     ecx, ecx; lpEventAttributes
0x1800056fb  lea     edx, [r9+1]; bManualReset
0x1800056ff  call    cs:__imp_CreateEventW
0x180005705  mov     cs:hObject, rax
0x18000570c  test    rax, rax
0x18000570f  jz      short loc_180005735
0x180005711  xor     ecx, ecx
0x180005713  call    __scrt_initialize_onexit_tables
0x180005718  test    al, al
0x18000571a  jz      short loc_180005735
0x18000571c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180005723  call    atexit
0x180005728  mov     rbx, [rsp+28h+arg_0]
0x18000572d  xor     eax, eax
0x18000572f  add     rsp, 20h
0x180005733  pop     rdi
0x180005734  retn
0x180005735  mov     ecx, 7
0x18000573a  call    __scrt_fastfail
```
