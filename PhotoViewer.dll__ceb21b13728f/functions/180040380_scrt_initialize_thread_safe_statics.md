# __scrt_initialize_thread_safe_statics

- ea: `0x180040380`
- end: `0x180040450`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18003fadc`
- `0x18003fcac`
- `0x18003fde4`
- `0x180040380`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1800403a3`
- `KERNEL32!GetModuleHandleW` at `0x1800403b8`
- `KERNEL32!GetModuleHandleW` at `0x1800403a3`
- `KERNEL32!GetModuleHandleW` at `0x1800403b8`
- `KERNEL32!GetProcAddress` at `0x1800403d0`
- `KERNEL32!GetProcAddress` at `0x1800403e3`
- `KERNEL32!GetProcAddress` at `0x1800403d0`
- `KERNEL32!GetProcAddress` at `0x1800403e3`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180040396`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180040396`
- `KERNEL32!CreateEventW` at `0x18004040f`
- `KERNEL32!CreateEventW` at `0x18004040f`

## string_xrefs

- `0x18004039c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800403b1`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_1800A3C30, 0xFA0u);
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
    qword_1800A3C58 = (__int64)ProcAddress;
    qword_1800A3C60 = (__int64)v2;
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
0x180040380  mov     [rsp+arg_0], rbx
0x180040385  push    rdi
0x180040386  sub     rsp, 20h
0x18004038a  mov     edx, 0FA0h; dwSpinCount
0x18004038f  lea     rcx, stru_1800A3C30; lpCriticalSection
0x180040396  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18004039c  lea     rcx, aApiMsWinCoreSy; "api-ms-win-core-synch-l1-2-0.dll"
0x1800403a3  call    cs:__imp_GetModuleHandleW
0x1800403a9  mov     rbx, rax
0x1800403ac  test    rax, rax
0x1800403af  jnz     short loc_1800403C6
0x1800403b1  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x1800403b8  call    cs:__imp_GetModuleHandleW
0x1800403be  mov     rbx, rax
0x1800403c1  test    rax, rax
0x1800403c4  jz      short loc_180040445
0x1800403c6  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x1800403cd  mov     rcx, rbx; hModule
0x1800403d0  call    cs:__imp_GetProcAddress
0x1800403d6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800403dd  mov     rcx, rbx; hModule
0x1800403e0  mov     rdi, rax
0x1800403e3  call    cs:__imp_GetProcAddress
0x1800403e9  test    rdi, rdi
0x1800403ec  jz      short loc_180040403
0x1800403ee  test    rax, rax
0x1800403f1  jz      short loc_180040403
0x1800403f3  mov     cs:qword_1800A3C58, rdi
0x1800403fa  mov     cs:qword_1800A3C60, rax
0x180040401  jmp     short loc_180040421
0x180040403  xor     r9d, r9d; lpName
0x180040406  xor     r8d, r8d; bInitialState
0x180040409  xor     ecx, ecx; lpEventAttributes
0x18004040b  lea     edx, [r9+1]; bManualReset
0x18004040f  call    cs:__imp_CreateEventW
0x180040415  mov     cs:hHandle, rax
0x18004041c  test    rax, rax
0x18004041f  jz      short loc_180040445
0x180040421  xor     ecx, ecx
0x180040423  call    __scrt_initialize_onexit_tables
0x180040428  test    al, al
0x18004042a  jz      short loc_180040445
0x18004042c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180040433  call    atexit
0x180040438  mov     rbx, [rsp+28h+arg_0]
0x18004043d  xor     eax, eax
0x18004043f  add     rsp, 20h
0x180040443  pop     rdi
0x180040444  retn
0x180040445  mov     ecx, 7
0x18004044a  call    __scrt_fastfail
```
