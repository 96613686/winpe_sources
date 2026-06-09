# __scrt_initialize_thread_safe_statics(void)

- ea: `0x1005a1a80`
- end: `0x1005a1bdd`
- name: `?__scrt_initialize_thread_safe_statics@@YAHXZ`
- size: `349`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1005a13d8`
- `0x1005a1610`
- `0x1005a1a80`
- `0x1005a1fec`
- `0x1005a77b0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1005a1ae6`
- `KERNEL32!GetProcAddress` at `0x1005a1afa`
- `KERNEL32!GetProcAddress` at `0x1005a1b0e`
- `KERNEL32!GetProcAddress` at `0x1005a1ae6`
- `KERNEL32!GetProcAddress` at `0x1005a1afa`
- `KERNEL32!GetProcAddress` at `0x1005a1b0e`
- `KERNEL32!CreateEventW` at `0x1005a1ba7`
- `KERNEL32!CreateEventW` at `0x1005a1ba7`
- `KERNEL32!GetModuleHandleW` at `0x1005a1ab3`
- `KERNEL32!GetModuleHandleW` at `0x1005a1ac9`
- `KERNEL32!GetModuleHandleW` at `0x1005a1ab3`
- `KERNEL32!GetModuleHandleW` at `0x1005a1ac9`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x1005a1aa5`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x1005a1aa5`

## string_xrefs

- `0x1005a1aac`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1005a1ac2`: `kernel32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __scrt_initialize_thread_safe_statics(void)
{
  HMODULE ModuleHandleW; // rbx
  void (__stdcall *InitializeConditionVariable)(PCONDITION_VARIABLE); // rsi
  BOOL (__stdcall *SleepConditionVariableCS)(PCONDITION_VARIABLE, PCRITICAL_SECTION, DWORD); // rdi
  void (__stdcall *WakeAllConditionVariable)(PCONDITION_VARIABLE); // rax
  void (__stdcall *v4)(PCONDITION_VARIABLE); // rbx

  InitializeCriticalSectionAndSpinCount(&stru_1006A46C8, 0xFA0u);
  ModuleHandleW = GetModuleHandleW(L"api-ms-win-core-synch-l1-2-0.dll");
  if ( !ModuleHandleW )
  {
    ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
    if ( !ModuleHandleW )
    {
LABEL_13:
      _scrt_fastfail(7);
      JUMPOUT(0x1005A1BDDLL);
    }
  }
  InitializeConditionVariable = (void (__stdcall *)(PCONDITION_VARIABLE))GetProcAddress(
                                                                           ModuleHandleW,
                                                                           "InitializeConditionVariable");
  SleepConditionVariableCS = (BOOL (__stdcall *)(PCONDITION_VARIABLE, PCRITICAL_SECTION, DWORD))GetProcAddress(
                                                                                                  ModuleHandleW,
                                                                                                  "SleepConditionVariableCS");
  WakeAllConditionVariable = (void (__stdcall *)(PCONDITION_VARIABLE))GetProcAddress(
                                                                        ModuleHandleW,
                                                                        "WakeAllConditionVariable");
  v4 = WakeAllConditionVariable;
  if ( InitializeConditionVariable && SleepConditionVariableCS && WakeAllConditionVariable )
  {
    hObject = 0;
    ((void (__fastcall *)(void *))InitializeConditionVariable)(&unk_1006A46F0);
    qword_1006A4700 = __ROR8__(SleepConditionVariableCS, 64 - ((unsigned __int8)_security_cookie & 0x3Fu))
                    ^ _security_cookie;
    qword_1006A4708 = __ROR8__(v4, 64 - ((unsigned __int8)_security_cookie & 0x3Fu)) ^ _security_cookie;
  }
  else
  {
    hObject = CreateEventW(0, 1, 0, 0);
    if ( !hObject )
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
  atexit(__scrt_uninitialize_thread_safe_statics);
  return 0;
}

```

## disassembly

```asm
0x1005a1a80  push    rdi
0x1005a1a82  sub     rsp, 30h
0x1005a1a86  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1005a1a8f  mov     [rsp+38h+arg_0], rbx
0x1005a1a94  mov     [rsp+38h+arg_8], rsi
0x1005a1a99  mov     edx, 0FA0h; dwSpinCount
0x1005a1a9e  lea     rcx, stru_1006A46C8; lpCriticalSection
0x1005a1aa5  call    cs:InitializeCriticalSectionAndSpinCount
0x1005a1aab  nop
0x1005a1aac  lea     rcx, aApiMsWinCoreSy
0x1005a1ab3  call    cs:GetModuleHandleW
0x1005a1ab9  nop
0x1005a1aba  mov     rbx, rax
0x1005a1abd  test    rax, rax
0x1005a1ac0  jnz     short loc_1005A1ADC
0x1005a1ac2  lea     rcx, ModuleName
0x1005a1ac9  call    cs:GetModuleHandleW
0x1005a1acf  nop
0x1005a1ad0  mov     rbx, rax
0x1005a1ad3  test    rax, rax
0x1005a1ad6  jz      loc_1005A1BD2
0x1005a1adc  lea     rdx, aInitializecond
0x1005a1ae3  mov     rcx, rbx; hModule
0x1005a1ae6  call    cs:GetProcAddress
0x1005a1aec  nop
0x1005a1aed  mov     rsi, rax
0x1005a1af0  lea     rdx, aSleepcondition
0x1005a1af7  mov     rcx, rbx; hModule
0x1005a1afa  call    cs:GetProcAddress
0x1005a1b00  nop
0x1005a1b01  mov     rdi, rax
0x1005a1b04  lea     rdx, aWakeallconditi
0x1005a1b0b  mov     rcx, rbx; hModule
0x1005a1b0e  call    cs:GetProcAddress
0x1005a1b14  nop
0x1005a1b15  mov     rbx, rax
0x1005a1b18  test    rsi, rsi
0x1005a1b1b  jz      short loc_1005A1B9B
0x1005a1b1d  test    rdi, rdi
0x1005a1b20  jz      short loc_1005A1B9B
0x1005a1b22  test    rax, rax
0x1005a1b25  jz      short loc_1005A1B9B
0x1005a1b27  and     cs:hObject, 0
0x1005a1b2f  lea     rcx, unk_1006A46F0
0x1005a1b36  mov     rax, rsi
0x1005a1b39  call    cs:__guard_dispatch_icall_fptr
0x1005a1b3f  nop
0x1005a1b40  mov     rdx, cs:__security_cookie
0x1005a1b47  mov     eax, edx
0x1005a1b49  and     eax, 3Fh
0x1005a1b4c  mov     ecx, 40h ; '@'
0x1005a1b51  sub     ecx, eax
0x1005a1b53  ror     rdi, cl
0x1005a1b56  mov     rax, rdx
0x1005a1b59  xor     rax, rdi
0x1005a1b5c  mov     cs:qword_1006A4700, rax
0x1005a1b63  ror     rbx, cl
0x1005a1b66  xor     rdx, rbx
0x1005a1b69  mov     cs:qword_1006A4708, rdx
0x1005a1b70  xor     ecx, ecx
0x1005a1b72  call    __scrt_initialize_onexit_tables
0x1005a1b77  nop
0x1005a1b78  test    al, al
0x1005a1b7a  jz      short loc_1005A1BBC
0x1005a1b7c  lea     rcx, ?__scrt_uninitialize_thread_safe_statics@@YAXXZ; void (__cdecl *)()
0x1005a1b83  call    atexit
0x1005a1b88  nop
0x1005a1b89  xor     eax, eax
0x1005a1b8b  mov     rbx, [rsp+38h+arg_0]
0x1005a1b90  mov     rsi, [rsp+38h+arg_8]
0x1005a1b95  add     rsp, 30h
0x1005a1b99  pop     rdi
0x1005a1b9a  retn
0x1005a1b9b  xor     r9d, r9d; lpName
0x1005a1b9e  xor     r8d, r8d; bInitialState
0x1005a1ba1  lea     edx, [r9+1]; bManualReset
0x1005a1ba5  xor     ecx, ecx; lpEventAttributes
0x1005a1ba7  call    cs:CreateEventW
0x1005a1bad  nop
0x1005a1bae  mov     cs:hObject, rax
0x1005a1bb5  test    rax, rax
0x1005a1bb8  jz      short loc_1005A1BC7
0x1005a1bba  jmp     short loc_1005A1B70
0x1005a1bbc  mov     ecx, 7
0x1005a1bc1  call    __scrt_fastfail
0x1005a1bc6  nop
0x1005a1bc7  mov     ecx, 7
0x1005a1bcc  call    __scrt_fastfail
0x1005a1bd1  nop
0x1005a1bd2  mov     ecx, 7
0x1005a1bd7  call    __scrt_fastfail
0x1005a1bdc  nop
```
