# __scrt_initialize_thread_safe_statics

- ea: `0x18006f230`
- end: `0x18006f300`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18006c2f8`
- `0x18006c4c8`
- `0x18006c600`
- `0x18006f230`

## import_xrefs

- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x18006f246`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x18006f246`
- `KERNEL32!CreateEventW` at `0x18006f2bf`
- `KERNEL32!CreateEventW` at `0x18006f2bf`
- `KERNEL32!GetProcAddress` at `0x18006f280`
- `KERNEL32!GetProcAddress` at `0x18006f293`
- `KERNEL32!GetProcAddress` at `0x18006f280`
- `KERNEL32!GetProcAddress` at `0x18006f293`
- `KERNEL32!GetModuleHandleW` at `0x18006f253`
- `KERNEL32!GetModuleHandleW` at `0x18006f268`
- `KERNEL32!GetModuleHandleW` at `0x18006f253`
- `KERNEL32!GetModuleHandleW` at `0x18006f268`

## string_xrefs

- `0x18006f24c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x18006f261`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_1800D3898, 0xFA0u);
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
    qword_1800D38C0 = (__int64)ProcAddress;
    qword_1800D38C8 = (__int64)v2;
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
0x18006f230  mov     [rsp+arg_0], rbx
0x18006f235  push    rdi
0x18006f236  sub     rsp, 20h
0x18006f23a  mov     edx, 0FA0h; dwSpinCount
0x18006f23f  lea     rcx, stru_1800D3898; lpCriticalSection
0x18006f246  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18006f24c  lea     rcx, aApiMsWinCoreSy; "api-ms-win-core-synch-l1-2-0.dll"
0x18006f253  call    cs:__imp_GetModuleHandleW
0x18006f259  mov     rbx, rax
0x18006f25c  test    rax, rax
0x18006f25f  jnz     short loc_18006F276
0x18006f261  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x18006f268  call    cs:__imp_GetModuleHandleW
0x18006f26e  mov     rbx, rax
0x18006f271  test    rax, rax
0x18006f274  jz      short loc_18006F2F5
0x18006f276  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x18006f27d  mov     rcx, rbx; hModule
0x18006f280  call    cs:__imp_GetProcAddress
0x18006f286  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18006f28d  mov     rcx, rbx; hModule
0x18006f290  mov     rdi, rax
0x18006f293  call    cs:__imp_GetProcAddress
0x18006f299  test    rdi, rdi
0x18006f29c  jz      short loc_18006F2B3
0x18006f29e  test    rax, rax
0x18006f2a1  jz      short loc_18006F2B3
0x18006f2a3  mov     cs:qword_1800D38C0, rdi
0x18006f2aa  mov     cs:qword_1800D38C8, rax
0x18006f2b1  jmp     short loc_18006F2D1
0x18006f2b3  xor     r9d, r9d; lpName
0x18006f2b6  xor     r8d, r8d; bInitialState
0x18006f2b9  xor     ecx, ecx; lpEventAttributes
0x18006f2bb  lea     edx, [r9+1]; bManualReset
0x18006f2bf  call    cs:__imp_CreateEventW
0x18006f2c5  mov     cs:hHandle, rax
0x18006f2cc  test    rax, rax
0x18006f2cf  jz      short loc_18006F2F5
0x18006f2d1  xor     ecx, ecx
0x18006f2d3  call    __scrt_initialize_onexit_tables
0x18006f2d8  test    al, al
0x18006f2da  jz      short loc_18006F2F5
0x18006f2dc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x18006f2e3  call    atexit
0x18006f2e8  mov     rbx, [rsp+28h+arg_0]
0x18006f2ed  xor     eax, eax
0x18006f2ef  add     rsp, 20h
0x18006f2f3  pop     rdi
0x18006f2f4  retn
0x18006f2f5  mov     ecx, 7
0x18006f2fa  call    __scrt_fastfail
```
