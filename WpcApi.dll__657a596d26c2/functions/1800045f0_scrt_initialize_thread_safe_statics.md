# __scrt_initialize_thread_safe_statics

- ea: `0x1800045f0`
- end: `0x1800046c0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800034e8`
- `0x1800036b8`
- `0x180003834`
- `0x1800045f0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004613`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004628`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004613`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004628`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004640`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004653`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004640`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004653`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004606`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004606`
- `KERNEL32!CreateEventW` at `0x18000467f`
- `KERNEL32!CreateEventW` at `0x18000467f`

## string_xrefs

- `0x18000460c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180004621`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_18004A470, 0xFA0u);
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
    qword_18004A498 = (__int64)ProcAddress;
    qword_18004A4A0 = (__int64)v2;
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
0x1800045f0  mov     [rsp+arg_0], rbx
0x1800045f5  push    rdi
0x1800045f6  sub     rsp, 20h
0x1800045fa  mov     edx, 0FA0h; dwSpinCount
0x1800045ff  lea     rcx, stru_18004A470; lpCriticalSection
0x180004606  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000460c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180004613  call    cs:__imp_GetModuleHandleW
0x180004619  mov     rbx, rax
0x18000461c  test    rax, rax
0x18000461f  jnz     short loc_180004636
0x180004621  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x180004628  call    cs:__imp_GetModuleHandleW
0x18000462e  mov     rbx, rax
0x180004631  test    rax, rax
0x180004634  jz      short loc_1800046B5
0x180004636  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18000463d  mov     rcx, rbx; hModule
0x180004640  call    cs:__imp_GetProcAddress
0x180004646  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000464d  mov     rcx, rbx; hModule
0x180004650  mov     rdi, rax
0x180004653  call    cs:__imp_GetProcAddress
0x180004659  test    rdi, rdi
0x18000465c  jz      short loc_180004673
0x18000465e  test    rax, rax
0x180004661  jz      short loc_180004673
0x180004663  mov     cs:qword_18004A498, rdi
0x18000466a  mov     cs:qword_18004A4A0, rax
0x180004671  jmp     short loc_180004691
0x180004673  xor     r9d, r9d; lpName
0x180004676  xor     r8d, r8d; bInitialState
0x180004679  xor     ecx, ecx; lpEventAttributes
0x18000467b  lea     edx, [r9+1]; bManualReset
0x18000467f  call    cs:__imp_CreateEventW
0x180004685  mov     cs:hHandle, rax
0x18000468c  test    rax, rax
0x18000468f  jz      short loc_1800046B5
0x180004691  xor     ecx, ecx
0x180004693  call    __scrt_initialize_onexit_tables
0x180004698  test    al, al
0x18000469a  jz      short loc_1800046B5
0x18000469c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1800046a3  call    atexit
0x1800046a8  mov     rbx, [rsp+28h+arg_0]
0x1800046ad  xor     eax, eax
0x1800046af  add     rsp, 20h
0x1800046b3  pop     rdi
0x1800046b4  retn
0x1800046b5  mov     ecx, 7
0x1800046ba  call    __scrt_fastfail
```
