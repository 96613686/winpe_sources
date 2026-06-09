# __scrt_initialize_thread_safe_statics

- ea: `0x18030cc00`
- end: `0x18030cd5d`
- name: `__scrt_initialize_thread_safe_statics`
- size: `349`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18030c9c8`
- `0x18030cbe0`
- `0x18030cc00`
- `0x18030d4c8`
- `0x180358070`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18030cc66`
- `KERNEL32!GetProcAddress` at `0x18030cc7a`
- `KERNEL32!GetProcAddress` at `0x18030cc8e`
- `KERNEL32!GetProcAddress` at `0x18030cc66`
- `KERNEL32!GetProcAddress` at `0x18030cc7a`
- `KERNEL32!GetProcAddress` at `0x18030cc8e`
- `KERNEL32!GetModuleHandleW` at `0x18030cc33`
- `KERNEL32!GetModuleHandleW` at `0x18030cc49`
- `KERNEL32!GetModuleHandleW` at `0x18030cc33`
- `KERNEL32!GetModuleHandleW` at `0x18030cc49`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x18030cc25`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x18030cc25`
- `KERNEL32!CreateEventW` at `0x18030cd27`
- `KERNEL32!CreateEventW` at `0x18030cd27`

## string_xrefs

- `0x18030cc42`: `kernel32.dll`
- `0x18030cc2c`: `api-ms-win-core-synch-l1-2-0.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rsi
  FARPROC v2; // rdi
  FARPROC v3; // rax
  FARPROC v4; // rbx

  InitializeCriticalSectionAndSpinCount(&stru_1804C68E8, 0xFA0u);
  ModuleHandleW = GetModuleHandleW(L"api-ms-win-core-synch-l1-2-0.dll");
  if ( !ModuleHandleW )
  {
    ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
    if ( !ModuleHandleW )
    {
LABEL_13:
      _scrt_fastfail(7);
      JUMPOUT(0x18030CD5DLL);
    }
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "InitializeConditionVariable");
  v2 = GetProcAddress(ModuleHandleW, "SleepConditionVariableCS");
  v3 = GetProcAddress(ModuleHandleW, "WakeAllConditionVariable");
  v4 = v3;
  if ( ProcAddress && v2 && v3 )
  {
    hHandle = 0;
    ((void (__fastcall *)(__int64 *))ProcAddress)(&qword_1804C6910);
    qword_1804C6920 = __ROR8__(v2, 64 - ((unsigned __int8)_security_cookie & 0x3Fu)) ^ _security_cookie;
    qword_1804C6928 = __ROR8__(v4, 64 - ((unsigned __int8)_security_cookie & 0x3Fu)) ^ _security_cookie;
  }
  else
  {
    hHandle = CreateEventW(0, 1, 0, 0);
    if ( !hHandle )
    {
LABEL_12:
      _scrt_fastfail(7);
      goto LABEL_13;
    }
  }
  if ( !(unsigned __int8)_scrt_initialize_onexit_tables(0) )
  {
    _scrt_fastfail(7);
    goto LABEL_12;
  }
  atexit(_scrt_uninitialize_thread_safe_statics);
  return 0;
}

```

## disassembly

```asm
0x18030cc00  push    rdi
0x18030cc02  sub     rsp, 30h
0x18030cc06  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18030cc0f  mov     [rsp+38h+arg_0], rbx
0x18030cc14  mov     [rsp+38h+arg_8], rsi
0x18030cc19  mov     edx, 0FA0h; dwSpinCount
0x18030cc1e  lea     rcx, stru_1804C68E8; lpCriticalSection
0x18030cc25  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18030cc2b  nop
0x18030cc2c  lea     rcx, aApiMsWinCoreSy_1
0x18030cc33  call    cs:__imp_GetModuleHandleW
0x18030cc39  nop
0x18030cc3a  mov     rbx, rax
0x18030cc3d  test    rax, rax
0x18030cc40  jnz     short loc_18030CC5C
0x18030cc42  lea     rcx, aKernel32Dll_0
0x18030cc49  call    cs:__imp_GetModuleHandleW
0x18030cc4f  nop
0x18030cc50  mov     rbx, rax
0x18030cc53  test    rax, rax
0x18030cc56  jz      loc_18030CD52
0x18030cc5c  lea     rdx, aInitializecond
0x18030cc63  mov     rcx, rbx; hModule
0x18030cc66  call    cs:__imp_GetProcAddress
0x18030cc6c  nop
0x18030cc6d  mov     rsi, rax
0x18030cc70  lea     rdx, aSleepcondition
0x18030cc77  mov     rcx, rbx; hModule
0x18030cc7a  call    cs:__imp_GetProcAddress
0x18030cc80  nop
0x18030cc81  mov     rdi, rax
0x18030cc84  lea     rdx, aWakeallconditi
0x18030cc8b  mov     rcx, rbx; hModule
0x18030cc8e  call    cs:__imp_GetProcAddress
0x18030cc94  nop
0x18030cc95  mov     rbx, rax
0x18030cc98  test    rsi, rsi
0x18030cc9b  jz      short loc_18030CD1B
0x18030cc9d  test    rdi, rdi
0x18030cca0  jz      short loc_18030CD1B
0x18030cca2  test    rax, rax
0x18030cca5  jz      short loc_18030CD1B
0x18030cca7  and     cs:hHandle, 0
0x18030ccaf  lea     rcx, qword_1804C6910
0x18030ccb6  mov     rax, rsi
0x18030ccb9  call    cs:__guard_dispatch_icall_fptr
0x18030ccbf  nop
0x18030ccc0  mov     rdx, cs:__security_cookie
0x18030ccc7  mov     eax, edx
0x18030ccc9  and     eax, 3Fh
0x18030cccc  mov     ecx, 40h ; '@'
0x18030ccd1  sub     ecx, eax
0x18030ccd3  ror     rdi, cl
0x18030ccd6  mov     rax, rdx
0x18030ccd9  xor     rax, rdi
0x18030ccdc  mov     cs:qword_1804C6920, rax
0x18030cce3  ror     rbx, cl
0x18030cce6  xor     rdx, rbx
0x18030cce9  mov     cs:qword_1804C6928, rdx
0x18030ccf0  xor     ecx, ecx
0x18030ccf2  call    __scrt_initialize_onexit_tables
0x18030ccf7  nop
0x18030ccf8  test    al, al
0x18030ccfa  jz      short loc_18030CD3C
0x18030ccfc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x18030cd03  call    atexit
0x18030cd08  nop
0x18030cd09  xor     eax, eax
0x18030cd0b  mov     rbx, [rsp+38h+arg_0]
0x18030cd10  mov     rsi, [rsp+38h+arg_8]
0x18030cd15  add     rsp, 30h
0x18030cd19  pop     rdi
0x18030cd1a  retn
0x18030cd1b  xor     r9d, r9d; lpName
0x18030cd1e  xor     r8d, r8d; bInitialState
0x18030cd21  lea     edx, [r9+1]; bManualReset
0x18030cd25  xor     ecx, ecx; lpEventAttributes
0x18030cd27  call    cs:__imp_CreateEventW
0x18030cd2d  nop
0x18030cd2e  mov     cs:hHandle, rax
0x18030cd35  test    rax, rax
0x18030cd38  jz      short loc_18030CD47
0x18030cd3a  jmp     short loc_18030CCF0
0x18030cd3c  mov     ecx, 7
0x18030cd41  call    __scrt_fastfail
0x18030cd46  nop
0x18030cd47  mov     ecx, 7
0x18030cd4c  call    __scrt_fastfail
0x18030cd51  nop
0x18030cd52  mov     ecx, 7
0x18030cd57  call    __scrt_fastfail
0x18030cd5c  nop
```
