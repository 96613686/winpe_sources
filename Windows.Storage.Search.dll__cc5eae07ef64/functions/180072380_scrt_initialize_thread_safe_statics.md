# __scrt_initialize_thread_safe_statics

- ea: `0x180072380`
- end: `0x180072450`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800720a0`
- `0x180072270`
- `0x180072380`
- `0x180072ae4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800723d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800723e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800723d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800723e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800723a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800723b8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800723a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800723b8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180072396`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180072396`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007240f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007240f`

## string_xrefs

- `0x18007239c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800723b1`: `kernel32.dll`

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
    qword_18011DDD0 = (__int64)ProcAddress;
    qword_18011DDD8 = (__int64)v2;
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
0x180072380  mov     [rsp+arg_0], rbx
0x180072385  push    rdi
0x180072386  sub     rsp, 20h
0x18007238a  mov     edx, 0FA0h; dwSpinCount
0x18007238f  lea     rcx, CriticalSection; lpCriticalSection
0x180072396  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18007239c  lea     rcx, aApiMsWinCoreSy_4; "api-ms-win-core-synch-l1-2-0.dll"
0x1800723a3  call    cs:__imp_GetModuleHandleW
0x1800723a9  mov     rbx, rax
0x1800723ac  test    rax, rax
0x1800723af  jnz     short loc_1800723C6
0x1800723b1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800723b8  call    cs:__imp_GetModuleHandleW
0x1800723be  mov     rbx, rax
0x1800723c1  test    rax, rax
0x1800723c4  jz      short loc_180072445
0x1800723c6  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x1800723cd  mov     rcx, rbx; hModule
0x1800723d0  call    cs:__imp_GetProcAddress
0x1800723d6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800723dd  mov     rcx, rbx; hModule
0x1800723e0  mov     rdi, rax
0x1800723e3  call    cs:__imp_GetProcAddress
0x1800723e9  test    rdi, rdi
0x1800723ec  jz      short loc_180072403
0x1800723ee  test    rax, rax
0x1800723f1  jz      short loc_180072403
0x1800723f3  mov     cs:qword_18011DDD0, rdi
0x1800723fa  mov     cs:qword_18011DDD8, rax
0x180072401  jmp     short loc_180072421
0x180072403  xor     r9d, r9d; lpName
0x180072406  xor     r8d, r8d; bInitialState
0x180072409  xor     ecx, ecx; lpEventAttributes
0x18007240b  lea     edx, [r9+1]; bManualReset
0x18007240f  call    cs:__imp_CreateEventW
0x180072415  mov     cs:hHandle, rax
0x18007241c  test    rax, rax
0x18007241f  jz      short loc_180072445
0x180072421  xor     ecx, ecx
0x180072423  call    __scrt_initialize_onexit_tables
0x180072428  test    al, al
0x18007242a  jz      short loc_180072445
0x18007242c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180072433  call    atexit
0x180072438  mov     rbx, [rsp+28h+arg_0]
0x18007243d  xor     eax, eax
0x18007243f  add     rsp, 20h
0x180072443  pop     rdi
0x180072444  retn
0x180072445  mov     ecx, 7
0x18007244a  call    __scrt_fastfail
```
