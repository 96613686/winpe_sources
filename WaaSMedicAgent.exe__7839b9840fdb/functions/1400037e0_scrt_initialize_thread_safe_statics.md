# __scrt_initialize_thread_safe_statics

- ea: `0x1400037e0`
- end: `0x1400038b0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x140002be8`
- `0x140002db8`
- `0x140002fe8`
- `0x1400037e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140003830`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140003843`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140003830`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140003843`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140003803`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140003818`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140003803`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140003818`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1400037f6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1400037f6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000386f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000386f`

## string_xrefs

- `0x1400037fc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x140003811`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_1400204A8, 0xFA0u);
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
    qword_1400204D0 = (__int64)ProcAddress;
    qword_1400204D8 = (__int64)v2;
  }
  else
  {
    hObject = CreateEventW(0, 1, 0, 0);
    if ( !hObject )
      goto LABEL_9;
  }
  if ( !(unsigned __int8)_scrt_initialize_onexit_tables(0) )
LABEL_9:
    _scrt_fastfail(7u);
  atexit(_scrt_uninitialize_thread_safe_statics);
  return 0;
}

```

## disassembly

```asm
0x1400037e0  mov     [rsp+arg_0], rbx
0x1400037e5  push    rdi
0x1400037e6  sub     rsp, 20h
0x1400037ea  mov     edx, 0FA0h; dwSpinCount
0x1400037ef  lea     rcx, stru_1400204A8; lpCriticalSection
0x1400037f6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1400037fc  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x140003803  call    cs:__imp_GetModuleHandleW
0x140003809  mov     rbx, rax
0x14000380c  test    rax, rax
0x14000380f  jnz     short loc_140003826
0x140003811  lea     rcx, aKernel32Dll; "kernel32.dll"
0x140003818  call    cs:__imp_GetModuleHandleW
0x14000381e  mov     rbx, rax
0x140003821  test    rax, rax
0x140003824  jz      short loc_1400038A5
0x140003826  lea     rdx, ProcName; "SleepConditionVariableCS"
0x14000382d  mov     rcx, rbx; hModule
0x140003830  call    cs:__imp_GetProcAddress
0x140003836  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x14000383d  mov     rcx, rbx; hModule
0x140003840  mov     rdi, rax
0x140003843  call    cs:__imp_GetProcAddress
0x140003849  test    rdi, rdi
0x14000384c  jz      short loc_140003863
0x14000384e  test    rax, rax
0x140003851  jz      short loc_140003863
0x140003853  mov     cs:qword_1400204D0, rdi
0x14000385a  mov     cs:qword_1400204D8, rax
0x140003861  jmp     short loc_140003881
0x140003863  xor     r9d, r9d; lpName
0x140003866  xor     r8d, r8d; bInitialState
0x140003869  xor     ecx, ecx; lpEventAttributes
0x14000386b  lea     edx, [r9+1]; bManualReset
0x14000386f  call    cs:__imp_CreateEventW
0x140003875  mov     cs:hObject, rax
0x14000387c  test    rax, rax
0x14000387f  jz      short loc_1400038A5
0x140003881  xor     ecx, ecx
0x140003883  call    __scrt_initialize_onexit_tables
0x140003888  test    al, al
0x14000388a  jz      short loc_1400038A5
0x14000388c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x140003893  call    atexit
0x140003898  mov     rbx, [rsp+28h+arg_0]
0x14000389d  xor     eax, eax
0x14000389f  add     rsp, 20h
0x1400038a3  pop     rdi
0x1400038a4  retn
0x1400038a5  mov     ecx, 7
0x1400038aa  call    __scrt_fastfail
```
