# __scrt_initialize_thread_safe_statics

- ea: `0x180008c50`
- end: `0x180008d20`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180002a84`
- `0x180002c54`
- `0x180002ef8`
- `0x180008c50`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008ca0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008cb3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008ca0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008cb3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008c73`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008c88`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008c73`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008c88`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180008cdf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180008cdf`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180008c66`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180008c66`

## string_xrefs

- `0x180008c81`: `kernel32.dll`
- `0x180008c6c`: `api-ms-win-core-synch-l1-2-0.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_18003D0D8, 0xFA0u);
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
    qword_18003D100 = (__int64)ProcAddress;
    qword_18003D108 = (__int64)v2;
    goto LABEL_7;
  }
  hObject = CreateEventW(0, 1, 0, 0);
  if ( !hObject )
  {
LABEL_9:
    _scrt_fastfail(7);
    JUMPOUT(0x180008D1FLL);
  }
LABEL_7:
  if ( !(unsigned __int8)_scrt_initialize_onexit_tables(0) )
    goto LABEL_9;
  atexit(_scrt_uninitialize_thread_safe_statics);
  return 0;
}

```

## disassembly

```asm
0x180008c50  mov     [rsp+arg_0], rbx
0x180008c55  push    rdi
0x180008c56  sub     rsp, 20h
0x180008c5a  mov     edx, 0FA0h; dwSpinCount
0x180008c5f  lea     rcx, stru_18003D0D8; lpCriticalSection
0x180008c66  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180008c6c  lea     rcx, ModuleName
0x180008c73  call    cs:__imp_GetModuleHandleW
0x180008c79  mov     rbx, rax
0x180008c7c  test    rax, rax
0x180008c7f  jnz     short loc_180008C96
0x180008c81  lea     rcx, aKernel32Dll
0x180008c88  call    cs:__imp_GetModuleHandleW
0x180008c8e  mov     rbx, rax
0x180008c91  test    rax, rax
0x180008c94  jz      short loc_180008D15
0x180008c96  lea     rdx, ProcName
0x180008c9d  mov     rcx, rbx; hModule
0x180008ca0  call    cs:__imp_GetProcAddress
0x180008ca6  lea     rdx, aWakeallconditi
0x180008cad  mov     rcx, rbx; hModule
0x180008cb0  mov     rdi, rax
0x180008cb3  call    cs:__imp_GetProcAddress
0x180008cb9  test    rdi, rdi
0x180008cbc  jz      short loc_180008CD3
0x180008cbe  test    rax, rax
0x180008cc1  jz      short loc_180008CD3
0x180008cc3  mov     cs:qword_18003D100, rdi
0x180008cca  mov     cs:qword_18003D108, rax
0x180008cd1  jmp     short loc_180008CF1
0x180008cd3  xor     r9d, r9d; lpName
0x180008cd6  xor     r8d, r8d; bInitialState
0x180008cd9  xor     ecx, ecx; lpEventAttributes
0x180008cdb  lea     edx, [r9+1]; bManualReset
0x180008cdf  call    cs:__imp_CreateEventW
0x180008ce5  mov     cs:hObject, rax
0x180008cec  test    rax, rax
0x180008cef  jz      short loc_180008D15
0x180008cf1  xor     ecx, ecx
0x180008cf3  call    __scrt_initialize_onexit_tables
0x180008cf8  test    al, al
0x180008cfa  jz      short loc_180008D15
0x180008cfc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180008d03  call    atexit
0x180008d08  mov     rbx, [rsp+28h+arg_0]
0x180008d0d  xor     eax, eax
0x180008d0f  add     rsp, 20h
0x180008d13  pop     rdi
0x180008d14  retn
0x180008d15  mov     ecx, 7
0x180008d1a  call    __scrt_fastfail
```
