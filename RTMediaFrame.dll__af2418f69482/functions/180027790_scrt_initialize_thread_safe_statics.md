# __scrt_initialize_thread_safe_statics

- ea: `0x180027790`
- end: `0x180027860`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180026bdc`
- `0x180026dac`
- `0x180026f54`
- `0x180027790`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800277e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800277f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800277e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800277f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800277b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800277c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800277b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800277c8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800277a6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800277a6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002781f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002781f`

## string_xrefs

- `0x1800277ac`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800277c1`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_180071C18, 0xFA0u);
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
    qword_180071C40 = (__int64)ProcAddress;
    qword_180071C48 = (__int64)v2;
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
0x180027790  mov     [rsp+arg_0], rbx
0x180027795  push    rdi
0x180027796  sub     rsp, 20h
0x18002779a  mov     edx, 0FA0h; dwSpinCount
0x18002779f  lea     rcx, stru_180071C18; lpCriticalSection
0x1800277a6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800277ac  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x1800277b3  call    cs:__imp_GetModuleHandleW
0x1800277b9  mov     rbx, rax
0x1800277bc  test    rax, rax
0x1800277bf  jnz     short loc_1800277D6
0x1800277c1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800277c8  call    cs:__imp_GetModuleHandleW
0x1800277ce  mov     rbx, rax
0x1800277d1  test    rax, rax
0x1800277d4  jz      short loc_180027855
0x1800277d6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x1800277dd  mov     rcx, rbx; hModule
0x1800277e0  call    cs:__imp_GetProcAddress
0x1800277e6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800277ed  mov     rcx, rbx; hModule
0x1800277f0  mov     rdi, rax
0x1800277f3  call    cs:__imp_GetProcAddress
0x1800277f9  test    rdi, rdi
0x1800277fc  jz      short loc_180027813
0x1800277fe  test    rax, rax
0x180027801  jz      short loc_180027813
0x180027803  mov     cs:qword_180071C40, rdi
0x18002780a  mov     cs:qword_180071C48, rax
0x180027811  jmp     short loc_180027831
0x180027813  xor     r9d, r9d; lpName
0x180027816  xor     r8d, r8d; bInitialState
0x180027819  xor     ecx, ecx; lpEventAttributes
0x18002781b  lea     edx, [r9+1]; bManualReset
0x18002781f  call    cs:__imp_CreateEventW
0x180027825  mov     cs:hHandle, rax
0x18002782c  test    rax, rax
0x18002782f  jz      short loc_180027855
0x180027831  xor     ecx, ecx
0x180027833  call    __scrt_initialize_onexit_tables
0x180027838  test    al, al
0x18002783a  jz      short loc_180027855
0x18002783c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180027843  call    atexit
0x180027848  mov     rbx, [rsp+28h+arg_0]
0x18002784d  xor     eax, eax
0x18002784f  add     rsp, 20h
0x180027853  pop     rdi
0x180027854  retn
0x180027855  mov     ecx, 7
0x18002785a  call    __scrt_fastfail
```
