# __scrt_initialize_thread_safe_statics

- ea: `0x1801359e0`
- end: `0x180135ab0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180134d50`
- `0x180134f20`
- `0x180135084`
- `0x1801359e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180135a30`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180135a43`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180135a30`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180135a43`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180135a03`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180135a18`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180135a03`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180135a18`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1801359f6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1801359f6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180135a6f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180135a6f`

## string_xrefs

- `0x1801359fc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180135a11`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_180228AD0, 0xFA0u);
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
    qword_180228AF8 = (__int64)ProcAddress;
    qword_180228B00 = (__int64)v2;
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
0x1801359e0  mov     [rsp+arg_0], rbx
0x1801359e5  push    rdi
0x1801359e6  sub     rsp, 20h
0x1801359ea  mov     edx, 0FA0h; dwSpinCount
0x1801359ef  lea     rcx, stru_180228AD0; lpCriticalSection
0x1801359f6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1801359fc  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180135a03  call    cs:__imp_GetModuleHandleW
0x180135a09  mov     rbx, rax
0x180135a0c  test    rax, rax
0x180135a0f  jnz     short loc_180135A26
0x180135a11  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180135a18  call    cs:__imp_GetModuleHandleW
0x180135a1e  mov     rbx, rax
0x180135a21  test    rax, rax
0x180135a24  jz      short loc_180135AA5
0x180135a26  lea     rdx, ProcName; "SleepConditionVariableCS"
0x180135a2d  mov     rcx, rbx; hModule
0x180135a30  call    cs:__imp_GetProcAddress
0x180135a36  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180135a3d  mov     rcx, rbx; hModule
0x180135a40  mov     rdi, rax
0x180135a43  call    cs:__imp_GetProcAddress
0x180135a49  test    rdi, rdi
0x180135a4c  jz      short loc_180135A63
0x180135a4e  test    rax, rax
0x180135a51  jz      short loc_180135A63
0x180135a53  mov     cs:qword_180228AF8, rdi
0x180135a5a  mov     cs:qword_180228B00, rax
0x180135a61  jmp     short loc_180135A81
0x180135a63  xor     r9d, r9d; lpName
0x180135a66  xor     r8d, r8d; bInitialState
0x180135a69  xor     ecx, ecx; lpEventAttributes
0x180135a6b  lea     edx, [r9+1]; bManualReset
0x180135a6f  call    cs:__imp_CreateEventW
0x180135a75  mov     cs:hHandle, rax
0x180135a7c  test    rax, rax
0x180135a7f  jz      short loc_180135AA5
0x180135a81  xor     ecx, ecx
0x180135a83  call    __scrt_initialize_onexit_tables
0x180135a88  test    al, al
0x180135a8a  jz      short loc_180135AA5
0x180135a8c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180135a93  call    atexit
0x180135a98  mov     rbx, [rsp+28h+arg_0]
0x180135a9d  xor     eax, eax
0x180135a9f  add     rsp, 20h
0x180135aa3  pop     rdi
0x180135aa4  retn
0x180135aa5  mov     ecx, 7
0x180135aaa  call    __scrt_fastfail
```
