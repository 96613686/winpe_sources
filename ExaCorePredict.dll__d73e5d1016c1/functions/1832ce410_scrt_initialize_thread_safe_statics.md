# __scrt_initialize_thread_safe_statics

- ea: `0x1832ce410`
- end: `0x1832ce52e`
- name: `__scrt_initialize_thread_safe_statics`
- size: `286`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1832ce040`
- `0x1832ce410`
- `0x1832ceb10`
- `0x1832cf6f0`
- `0x1832dbefc`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1832ce456`
- `KERNEL32!GetProcAddress` at `0x1832ce469`
- `KERNEL32!GetProcAddress` at `0x1832ce47c`
- `KERNEL32!GetProcAddress` at `0x1832ce456`
- `KERNEL32!GetProcAddress` at `0x1832ce469`
- `KERNEL32!GetProcAddress` at `0x1832ce47c`
- `KERNEL32!GetModuleHandleW` at `0x1832ce43a`
- `KERNEL32!GetModuleHandleW` at `0x1832ce43a`
- `KERNEL32!CreateEventW` at `0x1832ce504`
- `KERNEL32!CreateEventW` at `0x1832ce504`

## string_xrefs

- `0x1832ce433`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rax
  HMODULE v1; // rbx
  FARPROC ProcAddress; // rsi
  FARPROC v3; // rdi
  FARPROC v4; // rax
  FARPROC v5; // rbx

  _vcrt_InitializeCriticalSectionEx_0(&stru_18371FB58, 4000, 0);
  ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
  v1 = ModuleHandleW;
  if ( !ModuleHandleW )
  {
    _scrt_fastfail(7);
    __debugbreak();
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "InitializeConditionVariable");
  v3 = GetProcAddress(v1, "SleepConditionVariableCS");
  v4 = GetProcAddress(v1, "WakeAllConditionVariable");
  v5 = v4;
  if ( ProcAddress && v3 && v4 )
  {
    hHandle = 0;
    ((void (__fastcall *)(void *))ProcAddress)(&unk_18371FB80);
    qword_18371FB90 = _security_cookie ^ __ROR8__(v3, 64 - ((unsigned __int8)_security_cookie & 0x3Fu));
    qword_18371FB98 = _security_cookie ^ __ROR8__(v5, 64 - ((unsigned __int8)_security_cookie & 0x3Fu));
  }
  else
  {
    hHandle = CreateEventW(0, 1, 0, 0);
    if ( !hHandle )
    {
      _scrt_fastfail(7);
      JUMPOUT(0x1832CE52DLL);
    }
  }
  atexit(_scrt_uninitialize_thread_safe_statics);
  return 0;
}

```

## disassembly

```asm
0x1832ce410  mov     [rsp+arg_0], rbx
0x1832ce415  mov     [rsp+arg_8], rsi
0x1832ce41a  push    rdi
0x1832ce41b  sub     rsp, 20h
0x1832ce41f  xor     r8d, r8d
0x1832ce422  lea     rcx, stru_18371FB58
0x1832ce429  mov     edx, 0FA0h
0x1832ce42e  call    __vcrt_InitializeCriticalSectionEx_0
0x1832ce433  lea     rcx, aKernel32Dll_0
0x1832ce43a  call    cs:__imp_GetModuleHandleW
0x1832ce440  mov     rbx, rax
0x1832ce443  test    rax, rax
0x1832ce446  jz      loc_1832CE518
0x1832ce44c  lea     rdx, aInitializecond
0x1832ce453  mov     rcx, rax; hModule
0x1832ce456  call    cs:__imp_GetProcAddress
0x1832ce45c  lea     rdx, aSleepcondition
0x1832ce463  mov     rcx, rbx; hModule
0x1832ce466  mov     rsi, rax
0x1832ce469  call    cs:__imp_GetProcAddress
0x1832ce46f  lea     rdx, aWakeallconditi
0x1832ce476  mov     rcx, rbx; hModule
0x1832ce479  mov     rdi, rax
0x1832ce47c  call    cs:__imp_GetProcAddress
0x1832ce482  mov     rbx, rax
0x1832ce485  test    rsi, rsi
0x1832ce488  jz      short loc_1832CE4F8
0x1832ce48a  test    rdi, rdi
0x1832ce48d  jz      short loc_1832CE4F8
0x1832ce48f  test    rax, rax
0x1832ce492  jz      short loc_1832CE4F8
0x1832ce494  and     cs:hHandle, 0
0x1832ce49c  mov     rcx, rsi; Target
0x1832ce49f  call    _guard_check_icall
0x1832ce4a4  lea     rcx, unk_18371FB80
0x1832ce4ab  call    rsi
0x1832ce4ad  mov     rdx, cs:__security_cookie
0x1832ce4b4  mov     ecx, 40h ; '@'
0x1832ce4b9  mov     eax, edx
0x1832ce4bb  and     eax, 3Fh
0x1832ce4be  sub     ecx, eax
0x1832ce4c0  ror     rdi, cl
0x1832ce4c3  xor     rdi, rdx
0x1832ce4c6  ror     rbx, cl
0x1832ce4c9  xor     rbx, rdx
0x1832ce4cc  mov     cs:qword_18371FB90, rdi
0x1832ce4d3  mov     cs:qword_18371FB98, rbx
0x1832ce4da  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1832ce4e1  call    atexit
0x1832ce4e6  mov     rbx, [rsp+28h+arg_0]
0x1832ce4eb  xor     eax, eax
0x1832ce4ed  mov     rsi, [rsp+28h+arg_8]
0x1832ce4f2  add     rsp, 20h
0x1832ce4f6  pop     rdi
0x1832ce4f7  retn
0x1832ce4f8  xor     r9d, r9d; lpName
0x1832ce4fb  xor     r8d, r8d; bInitialState
0x1832ce4fe  xor     ecx, ecx; lpEventAttributes
0x1832ce500  lea     edx, [r9+1]; bManualReset
0x1832ce504  call    cs:__imp_CreateEventW
0x1832ce50a  mov     cs:hHandle, rax
0x1832ce511  test    rax, rax
0x1832ce514  jnz     short loc_1832CE4DA
0x1832ce516  jmp     short loc_1832CE523
0x1832ce518  mov     ecx, 7
0x1832ce51d  call    __scrt_fastfail
0x1832ce522  int     3; Trap to Debugger
0x1832ce523  mov     ecx, 7
0x1832ce528  call    __scrt_fastfail
```
