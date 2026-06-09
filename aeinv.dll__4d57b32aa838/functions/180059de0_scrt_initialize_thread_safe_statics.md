# __scrt_initialize_thread_safe_statics

- ea: `0x180059de0`
- end: `0x180059eb0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180059b00`
- `0x180059cd0`
- `0x180059de0`
- `0x18005a4c0`

## import_xrefs

- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180059df6`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180059df6`
- `KERNEL32!CreateEventW` at `0x180059e6f`
- `KERNEL32!CreateEventW` at `0x180059e6f`
- `KERNEL32!GetModuleHandleW` at `0x180059e03`
- `KERNEL32!GetModuleHandleW` at `0x180059e18`
- `KERNEL32!GetModuleHandleW` at `0x180059e03`
- `KERNEL32!GetModuleHandleW` at `0x180059e18`
- `KERNEL32!GetProcAddress` at `0x180059e30`
- `KERNEL32!GetProcAddress` at `0x180059e43`
- `KERNEL32!GetProcAddress` at `0x180059e30`
- `KERNEL32!GetProcAddress` at `0x180059e43`

## string_xrefs

- `0x180059e11`: `kernel32.dll`
- `0x180059dfc`: `api-ms-win-core-synch-l1-2-0.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_180181CE8, 0xFA0u);
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
    qword_180181D10 = (__int64)ProcAddress;
    qword_180181D18 = (__int64)v2;
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
0x180059de0  mov     [rsp+arg_0], rbx
0x180059de5  push    rdi
0x180059de6  sub     rsp, 20h
0x180059dea  mov     edx, 0FA0h; dwSpinCount
0x180059def  lea     rcx, stru_180181CE8; lpCriticalSection
0x180059df6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180059dfc  lea     rcx, aApiMsWinCoreSy; "api-ms-win-core-synch-l1-2-0.dll"
0x180059e03  call    cs:__imp_GetModuleHandleW
0x180059e09  mov     rbx, rax
0x180059e0c  test    rax, rax
0x180059e0f  jnz     short loc_180059E26
0x180059e11  lea     rcx, aKernel32Dll_1; "kernel32.dll"
0x180059e18  call    cs:__imp_GetModuleHandleW
0x180059e1e  mov     rbx, rax
0x180059e21  test    rax, rax
0x180059e24  jz      short loc_180059EA5
0x180059e26  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x180059e2d  mov     rcx, rbx; hModule
0x180059e30  call    cs:__imp_GetProcAddress
0x180059e36  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180059e3d  mov     rcx, rbx; hModule
0x180059e40  mov     rdi, rax
0x180059e43  call    cs:__imp_GetProcAddress
0x180059e49  test    rdi, rdi
0x180059e4c  jz      short loc_180059E63
0x180059e4e  test    rax, rax
0x180059e51  jz      short loc_180059E63
0x180059e53  mov     cs:qword_180181D10, rdi
0x180059e5a  mov     cs:qword_180181D18, rax
0x180059e61  jmp     short loc_180059E81
0x180059e63  xor     r9d, r9d; lpName
0x180059e66  xor     r8d, r8d; bInitialState
0x180059e69  xor     ecx, ecx; lpEventAttributes
0x180059e6b  lea     edx, [r9+1]; bManualReset
0x180059e6f  call    cs:__imp_CreateEventW
0x180059e75  mov     cs:hHandle, rax
0x180059e7c  test    rax, rax
0x180059e7f  jz      short loc_180059EA5
0x180059e81  xor     ecx, ecx
0x180059e83  call    __scrt_initialize_onexit_tables
0x180059e88  test    al, al
0x180059e8a  jz      short loc_180059EA5
0x180059e8c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180059e93  call    atexit
0x180059e98  mov     rbx, [rsp+28h+arg_0]
0x180059e9d  xor     eax, eax
0x180059e9f  add     rsp, 20h
0x180059ea3  pop     rdi
0x180059ea4  retn
0x180059ea5  mov     ecx, 7
0x180059eaa  call    __scrt_fastfail
```
