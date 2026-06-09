# __scrt_initialize_thread_safe_statics(void)

- ea: `0x140024ec0`
- end: `0x140024f90`
- name: `?__scrt_initialize_thread_safe_statics@@YAHXZ`
- size: `208`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x14001c570`
- `0x14001c9c8`
- `0x14001cb78`
- `0x140024ec0`

## import_xrefs

- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x140024ed6`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x140024ed6`
- `KERNEL32!GetProcAddress` at `0x140024f10`
- `KERNEL32!GetProcAddress` at `0x140024f23`
- `KERNEL32!GetProcAddress` at `0x140024f10`
- `KERNEL32!GetProcAddress` at `0x140024f23`
- `KERNEL32!GetModuleHandleW` at `0x140024ee3`
- `KERNEL32!GetModuleHandleW` at `0x140024ef8`
- `KERNEL32!GetModuleHandleW` at `0x140024ee3`
- `KERNEL32!GetModuleHandleW` at `0x140024ef8`
- `KERNEL32!CreateEventW` at `0x140024f4f`
- `KERNEL32!CreateEventW` at `0x140024f4f`

## string_xrefs

- `0x140024edc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x140024ef1`: `kernel32.dll`

## pseudocode

```c
__int64 __scrt_initialize_thread_safe_statics(void)
{
  HMODULE ModuleHandleW; // rbx
  BOOL (__stdcall *SleepConditionVariableCS)(PCONDITION_VARIABLE, PCRITICAL_SECTION, DWORD); // rdi
  void (__stdcall *WakeAllConditionVariable)(PCONDITION_VARIABLE); // rax

  InitializeCriticalSectionAndSpinCount(&CriticalSection, 0xFA0u);
  ModuleHandleW = GetModuleHandleW(L"api-ms-win-core-synch-l1-2-0.dll");
  if ( !ModuleHandleW )
  {
    ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
    if ( !ModuleHandleW )
      goto LABEL_9;
  }
  SleepConditionVariableCS = (BOOL (__stdcall *)(PCONDITION_VARIABLE, PCRITICAL_SECTION, DWORD))GetProcAddress(
                                                                                                  ModuleHandleW,
                                                                                                  "SleepConditionVariableCS");
  WakeAllConditionVariable = (void (__stdcall *)(PCONDITION_VARIABLE))GetProcAddress(
                                                                        ModuleHandleW,
                                                                        "WakeAllConditionVariable");
  if ( SleepConditionVariableCS && WakeAllConditionVariable )
  {
    qword_1400D7C48 = (__int64)SleepConditionVariableCS;
    qword_1400D7C50 = (__int64)WakeAllConditionVariable;
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
    sub_14001C570(7);
    __debugbreak();
  }
  atexit(__scrt_uninitialize_thread_safe_statics);
  return 0;
}

```

## disassembly

```asm
0x140024ec0  mov     [rsp+arg_0], rbx
0x140024ec5  push    rdi
0x140024ec6  sub     rsp, 20h
0x140024eca  mov     edx, 0FA0h; dwSpinCount
0x140024ecf  lea     rcx, CriticalSection; lpCriticalSection
0x140024ed6  call    cs:InitializeCriticalSectionAndSpinCount
0x140024edc  lea     rcx, aApiMsWinCoreSy
0x140024ee3  call    cs:GetModuleHandleW
0x140024ee9  mov     rbx, rax
0x140024eec  test    rax, rax
0x140024eef  jnz     short loc_140024F06
0x140024ef1  lea     rcx, aKernel32Dll_0
0x140024ef8  call    cs:GetModuleHandleW
0x140024efe  mov     rbx, rax
0x140024f01  test    rax, rax
0x140024f04  jz      short loc_140024F85
0x140024f06  lea     rdx, aSleepcondition
0x140024f0d  mov     rcx, rbx; hModule
0x140024f10  call    cs:GetProcAddress
0x140024f16  lea     rdx, aWakeallconditi
0x140024f1d  mov     rcx, rbx; hModule
0x140024f20  mov     rdi, rax
0x140024f23  call    cs:GetProcAddress
0x140024f29  test    rdi, rdi
0x140024f2c  jz      short loc_140024F43
0x140024f2e  test    rax, rax
0x140024f31  jz      short loc_140024F43
0x140024f33  mov     cs:qword_1400D7C48, rdi
0x140024f3a  mov     cs:qword_1400D7C50, rax
0x140024f41  jmp     short loc_140024F61
0x140024f43  xor     r9d, r9d; lpName
0x140024f46  xor     r8d, r8d; bInitialState
0x140024f49  xor     ecx, ecx; lpEventAttributes
0x140024f4b  lea     edx, [r9+1]; bManualReset
0x140024f4f  call    cs:CreateEventW
0x140024f55  mov     cs:hHandle, rax
0x140024f5c  test    rax, rax
0x140024f5f  jz      short loc_140024F85
0x140024f61  xor     ecx, ecx
0x140024f63  call    __scrt_initialize_onexit_tables
0x140024f68  test    al, al
0x140024f6a  jz      short loc_140024F85
0x140024f6c  lea     rcx, ?__scrt_uninitialize_thread_safe_statics@@YAXXZ; void (__cdecl *)()
0x140024f73  call    atexit
0x140024f78  mov     rbx, [rsp+28h+arg_0]
0x140024f7d  xor     eax, eax
0x140024f7f  add     rsp, 20h
0x140024f83  pop     rdi
0x140024f84  retn
0x140024f85  mov     ecx, 7
0x140024f8a  call    sub_14001C570
0x140024f8f  int     3; Trap to Debugger
```
