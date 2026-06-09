# __scrt_initialize_thread_safe_statics

- ea: `0x1400019e0`
- end: `0x140001ab0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x140001744`
- `0x140001914`
- `0x1400019e0`
- `0x140001e00`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140001a30`
- `KERNEL32!GetProcAddress` at `0x140001a43`
- `KERNEL32!GetProcAddress` at `0x140001a30`
- `KERNEL32!GetProcAddress` at `0x140001a43`
- `KERNEL32!GetModuleHandleW` at `0x140001a03`
- `KERNEL32!GetModuleHandleW` at `0x140001a18`
- `KERNEL32!GetModuleHandleW` at `0x140001a03`
- `KERNEL32!GetModuleHandleW` at `0x140001a18`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1400019f6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1400019f6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140001a6f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140001a6f`

## string_xrefs

- `0x1400019fc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x140001a11`: `kernel32.dll`

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
    qword_14001A470 = (__int64)ProcAddress;
    qword_14001A478 = (__int64)v2;
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
0x1400019e0  mov     [rsp+arg_0], rbx
0x1400019e5  push    rdi
0x1400019e6  sub     rsp, 20h
0x1400019ea  mov     edx, 0FA0h; dwSpinCount
0x1400019ef  lea     rcx, CriticalSection; lpCriticalSection
0x1400019f6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1400019fc  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x140001a03  call    cs:__imp_GetModuleHandleW
0x140001a09  mov     rbx, rax
0x140001a0c  test    rax, rax
0x140001a0f  jnz     short loc_140001A26
0x140001a11  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x140001a18  call    cs:__imp_GetModuleHandleW
0x140001a1e  mov     rbx, rax
0x140001a21  test    rax, rax
0x140001a24  jz      short loc_140001AA5
0x140001a26  lea     rdx, ProcName; "SleepConditionVariableCS"
0x140001a2d  mov     rcx, rbx; hModule
0x140001a30  call    cs:__imp_GetProcAddress
0x140001a36  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x140001a3d  mov     rcx, rbx; hModule
0x140001a40  mov     rdi, rax
0x140001a43  call    cs:__imp_GetProcAddress
0x140001a49  test    rdi, rdi
0x140001a4c  jz      short loc_140001A63
0x140001a4e  test    rax, rax
0x140001a51  jz      short loc_140001A63
0x140001a53  mov     cs:qword_14001A470, rdi
0x140001a5a  mov     cs:qword_14001A478, rax
0x140001a61  jmp     short loc_140001A81
0x140001a63  xor     r9d, r9d; lpName
0x140001a66  xor     r8d, r8d; bInitialState
0x140001a69  xor     ecx, ecx; lpEventAttributes
0x140001a6b  lea     edx, [r9+1]; bManualReset
0x140001a6f  call    cs:__imp_CreateEventW
0x140001a75  mov     cs:hHandle, rax
0x140001a7c  test    rax, rax
0x140001a7f  jz      short loc_140001AA5
0x140001a81  xor     ecx, ecx
0x140001a83  call    __scrt_initialize_onexit_tables
0x140001a88  test    al, al
0x140001a8a  jz      short loc_140001AA5
0x140001a8c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x140001a93  call    atexit
0x140001a98  mov     rbx, [rsp+28h+arg_0]
0x140001a9d  xor     eax, eax
0x140001a9f  add     rsp, 20h
0x140001aa3  pop     rdi
0x140001aa4  retn
0x140001aa5  mov     ecx, 7
0x140001aaa  call    __scrt_fastfail
```
