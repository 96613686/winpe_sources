# __scrt_initialize_thread_safe_statics

- ea: `0x1800046d0`
- end: `0x1800047a0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800044a0`
- `0x180004670`
- `0x1800046d0`
- `0x180004df4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800046f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004708`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800046f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004708`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004720`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004733`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004720`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004733`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800046e6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800046e6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000475f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000475f`

## string_xrefs

- `0x1800046ec`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180004701`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&CriticalSection, 0xFA0u);
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
    qword_18005F8D0 = (__int64)ProcAddress;
    qword_18005F8D8 = (__int64)v2;
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
0x1800046d0  mov     [rsp+arg_0], rbx
0x1800046d5  push    rdi
0x1800046d6  sub     rsp, 20h
0x1800046da  mov     edx, 0FA0h; dwSpinCount
0x1800046df  lea     rcx, CriticalSection; lpCriticalSection
0x1800046e6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800046ec  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x1800046f3  call    cs:__imp_GetModuleHandleW
0x1800046f9  mov     rbx, rax
0x1800046fc  test    rax, rax
0x1800046ff  jnz     short loc_180004716
0x180004701  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180004708  call    cs:__imp_GetModuleHandleW
0x18000470e  mov     rbx, rax
0x180004711  test    rax, rax
0x180004714  jz      short loc_180004795
0x180004716  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18000471d  mov     rcx, rbx; hModule
0x180004720  call    cs:__imp_GetProcAddress
0x180004726  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000472d  mov     rcx, rbx; hModule
0x180004730  mov     rdi, rax
0x180004733  call    cs:__imp_GetProcAddress
0x180004739  test    rdi, rdi
0x18000473c  jz      short loc_180004753
0x18000473e  test    rax, rax
0x180004741  jz      short loc_180004753
0x180004743  mov     cs:qword_18005F8D0, rdi
0x18000474a  mov     cs:qword_18005F8D8, rax
0x180004751  jmp     short loc_180004771
0x180004753  xor     r9d, r9d; lpName
0x180004756  xor     r8d, r8d; bInitialState
0x180004759  xor     ecx, ecx; lpEventAttributes
0x18000475b  lea     edx, [r9+1]; bManualReset
0x18000475f  call    cs:__imp_CreateEventW
0x180004765  mov     cs:hHandle, rax
0x18000476c  test    rax, rax
0x18000476f  jz      short loc_180004795
0x180004771  xor     ecx, ecx
0x180004773  call    __scrt_initialize_onexit_tables
0x180004778  test    al, al
0x18000477a  jz      short loc_180004795
0x18000477c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180004783  call    atexit
0x180004788  mov     rbx, [rsp+28h+arg_0]
0x18000478d  xor     eax, eax
0x18000478f  add     rsp, 20h
0x180004793  pop     rdi
0x180004794  retn
0x180004795  mov     ecx, 7
0x18000479a  call    __scrt_fastfail
```
