# __scrt_initialize_thread_safe_statics

- ea: `0x18000cd30`
- end: `0x18000ce00`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18000c990`
- `0x18000cb60`
- `0x18000cd30`
- `0x18000d3f4`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x18000cdbf`
- `KERNEL32!CreateEventW` at `0x18000cdbf`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x18000cd46`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x18000cd46`
- `KERNEL32!GetModuleHandleW` at `0x18000cd53`
- `KERNEL32!GetModuleHandleW` at `0x18000cd68`
- `KERNEL32!GetModuleHandleW` at `0x18000cd53`
- `KERNEL32!GetModuleHandleW` at `0x18000cd68`
- `KERNEL32!GetProcAddress` at `0x18000cd80`
- `KERNEL32!GetProcAddress` at `0x18000cd93`
- `KERNEL32!GetProcAddress` at `0x18000cd80`
- `KERNEL32!GetProcAddress` at `0x18000cd93`

## string_xrefs

- `0x18000cd4c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x18000cd61`: `kernel32.dll`

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
    qword_18017AE50 = (__int64)ProcAddress;
    qword_18017AE58 = (__int64)v2;
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
0x18000cd30  mov     [rsp+arg_0], rbx
0x18000cd35  push    rdi
0x18000cd36  sub     rsp, 20h
0x18000cd3a  mov     edx, 0FA0h; dwSpinCount
0x18000cd3f  lea     rcx, CriticalSection; lpCriticalSection
0x18000cd46  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000cd4c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x18000cd53  call    cs:__imp_GetModuleHandleW
0x18000cd59  mov     rbx, rax
0x18000cd5c  test    rax, rax
0x18000cd5f  jnz     short loc_18000CD76
0x18000cd61  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x18000cd68  call    cs:__imp_GetModuleHandleW
0x18000cd6e  mov     rbx, rax
0x18000cd71  test    rax, rax
0x18000cd74  jz      short loc_18000CDF5
0x18000cd76  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18000cd7d  mov     rcx, rbx; hModule
0x18000cd80  call    cs:__imp_GetProcAddress
0x18000cd86  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000cd8d  mov     rcx, rbx; hModule
0x18000cd90  mov     rdi, rax
0x18000cd93  call    cs:__imp_GetProcAddress
0x18000cd99  test    rdi, rdi
0x18000cd9c  jz      short loc_18000CDB3
0x18000cd9e  test    rax, rax
0x18000cda1  jz      short loc_18000CDB3
0x18000cda3  mov     cs:qword_18017AE50, rdi
0x18000cdaa  mov     cs:qword_18017AE58, rax
0x18000cdb1  jmp     short loc_18000CDD1
0x18000cdb3  xor     r9d, r9d; lpName
0x18000cdb6  xor     r8d, r8d; bInitialState
0x18000cdb9  xor     ecx, ecx; lpEventAttributes
0x18000cdbb  lea     edx, [r9+1]; bManualReset
0x18000cdbf  call    cs:__imp_CreateEventW
0x18000cdc5  mov     cs:hHandle, rax
0x18000cdcc  test    rax, rax
0x18000cdcf  jz      short loc_18000CDF5
0x18000cdd1  xor     ecx, ecx
0x18000cdd3  call    __scrt_initialize_onexit_tables
0x18000cdd8  test    al, al
0x18000cdda  jz      short loc_18000CDF5
0x18000cddc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x18000cde3  call    atexit
0x18000cde8  mov     rbx, [rsp+28h+arg_0]
0x18000cded  xor     eax, eax
0x18000cdef  add     rsp, 20h
0x18000cdf3  pop     rdi
0x18000cdf4  retn
0x18000cdf5  mov     ecx, 7
0x18000cdfa  call    __scrt_fastfail
```
