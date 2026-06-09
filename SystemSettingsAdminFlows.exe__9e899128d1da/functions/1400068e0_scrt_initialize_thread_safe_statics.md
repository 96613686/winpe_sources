# __scrt_initialize_thread_safe_statics

- ea: `0x1400068e0`
- end: `0x1400069b0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x140004538`
- `0x140004708`
- `0x140004848`
- `0x1400068e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140006903`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140006918`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140006903`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140006918`
- `KERNEL32!GetProcAddress` at `0x140006930`
- `KERNEL32!GetProcAddress` at `0x140006943`
- `KERNEL32!GetProcAddress` at `0x140006930`
- `KERNEL32!GetProcAddress` at `0x140006943`
- `KERNEL32!CreateEventW` at `0x14000696f`
- `KERNEL32!CreateEventW` at `0x14000696f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1400068f6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1400068f6`

## string_xrefs

- `0x1400068fc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x140006911`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_1400AB888, 0xFA0u);
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
    qword_1400AB8B0 = (__int64)ProcAddress;
    qword_1400AB8B8 = (__int64)v2;
  }
  else
  {
    hObject = CreateEventW(0, 1, 0, 0);
    if ( !hObject )
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
0x1400068e0  mov     [rsp+arg_0], rbx
0x1400068e5  push    rdi
0x1400068e6  sub     rsp, 20h
0x1400068ea  mov     edx, 0FA0h; dwSpinCount
0x1400068ef  lea     rcx, stru_1400AB888; lpCriticalSection
0x1400068f6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1400068fc  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x140006903  call    cs:__imp_GetModuleHandleW
0x140006909  mov     rbx, rax
0x14000690c  test    rax, rax
0x14000690f  jnz     short loc_140006926
0x140006911  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x140006918  call    cs:__imp_GetModuleHandleW
0x14000691e  mov     rbx, rax
0x140006921  test    rax, rax
0x140006924  jz      short loc_1400069A5
0x140006926  lea     rdx, ProcName; "SleepConditionVariableCS"
0x14000692d  mov     rcx, rbx; hModule
0x140006930  call    cs:__imp_GetProcAddress
0x140006936  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x14000693d  mov     rcx, rbx; hModule
0x140006940  mov     rdi, rax
0x140006943  call    cs:__imp_GetProcAddress
0x140006949  test    rdi, rdi
0x14000694c  jz      short loc_140006963
0x14000694e  test    rax, rax
0x140006951  jz      short loc_140006963
0x140006953  mov     cs:qword_1400AB8B0, rdi
0x14000695a  mov     cs:qword_1400AB8B8, rax
0x140006961  jmp     short loc_140006981
0x140006963  xor     r9d, r9d; lpName
0x140006966  xor     r8d, r8d; bInitialState
0x140006969  xor     ecx, ecx; lpEventAttributes
0x14000696b  lea     edx, [r9+1]; bManualReset
0x14000696f  call    cs:__imp_CreateEventW
0x140006975  mov     cs:hObject, rax
0x14000697c  test    rax, rax
0x14000697f  jz      short loc_1400069A5
0x140006981  xor     ecx, ecx
0x140006983  call    __scrt_initialize_onexit_tables
0x140006988  test    al, al
0x14000698a  jz      short loc_1400069A5
0x14000698c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x140006993  call    atexit
0x140006998  mov     rbx, [rsp+28h+arg_0]
0x14000699d  xor     eax, eax
0x14000699f  add     rsp, 20h
0x1400069a3  pop     rdi
0x1400069a4  retn
0x1400069a5  mov     ecx, 7
0x1400069aa  call    __scrt_fastfail
```
