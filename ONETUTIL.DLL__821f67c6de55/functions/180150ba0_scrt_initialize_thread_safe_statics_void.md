# __scrt_initialize_thread_safe_statics(void)

- ea: `0x180150ba0`
- end: `0x180150ceb`
- name: `?__scrt_initialize_thread_safe_statics@@YAHXZ`
- size: `331`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180150ba0`
- `0x1801510b4`
- `0x1801512d0`
- `0x180151330`
- `0x180151514`
- `0x180151702`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x180150c98`
- `KERNEL32!CreateEventW` at `0x180150c98`
- `KERNEL32!GetModuleHandleW` at `0x180150bca`
- `KERNEL32!GetModuleHandleW` at `0x180150bdf`
- `KERNEL32!GetModuleHandleW` at `0x180150bca`
- `KERNEL32!GetModuleHandleW` at `0x180150bdf`
- `KERNEL32!GetProcAddress` at `0x180150bfb`
- `KERNEL32!GetProcAddress` at `0x180150c0e`
- `KERNEL32!GetProcAddress` at `0x180150c21`
- `KERNEL32!GetProcAddress` at `0x180150bfb`
- `KERNEL32!GetProcAddress` at `0x180150c0e`
- `KERNEL32!GetProcAddress` at `0x180150c21`

## string_xrefs

- `0x180150bc3`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180150bd8`: `kernel32.dll`

## pseudocode

```c
__int64 __scrt_initialize_thread_safe_statics(void)
{
  HMODULE ModuleHandleW; // rbx
  void (__stdcall *InitializeConditionVariable)(PCONDITION_VARIABLE); // rsi
  BOOL (__stdcall *SleepConditionVariableCS)(PCONDITION_VARIABLE, PCRITICAL_SECTION, DWORD); // rdi
  void (__stdcall *WakeAllConditionVariable)(PCONDITION_VARIABLE); // rax
  void (__stdcall *v4)(PCONDITION_VARIABLE); // rbx

  _vcrt_InitializeCriticalSectionEx(&stru_1802AF2A0, 4000, 0);
  ModuleHandleW = GetModuleHandleW(L"api-ms-win-core-synch-l1-2-0.dll");
  if ( !ModuleHandleW )
  {
    ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
    if ( !ModuleHandleW )
    {
      _scrt_fastfail(7);
      __debugbreak();
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
    ((void (__fastcall *)(__int64 *))InitializeConditionVariable)(&qword_1802AF2C8);
    qword_1802AF2D8 = _security_cookie
                    ^ __ROR8__(SleepConditionVariableCS, 64 - ((unsigned __int8)_security_cookie & 0x3Fu));
    qword_1802AF2E0 = _security_cookie ^ __ROR8__(v4, 64 - ((unsigned __int8)_security_cookie & 0x3Fu));
  }
  else
  {
    hObject = CreateEventW(0, 1, 0, 0);
    if ( !hObject )
    {
      _scrt_fastfail(7);
      JUMPOUT(0x180150CEALL);
    }
  }
  if ( !(unsigned __int8)_scrt_initialize_onexit_tables(0) )
  {
    _scrt_fastfail(7);
    __debugbreak();
  }
  atexit(__scrt_uninitialize_thread_safe_statics);
  return 0;
}

```

## disassembly

```asm
0x180150ba0  mov     [rsp+arg_0], rbx
0x180150ba5  mov     [rsp+arg_8], rsi
0x180150baa  push    rdi
0x180150bab  sub     rsp, 20h
0x180150baf  xor     r8d, r8d
0x180150bb2  lea     rcx, stru_1802AF2A0
0x180150bb9  mov     edx, 0FA0h
0x180150bbe  call    __vcrt_InitializeCriticalSectionEx
0x180150bc3  lea     rcx, aApiMsWinCoreSy
0x180150bca  call    cs:GetModuleHandleW
0x180150bd0  mov     rbx, rax
0x180150bd3  test    rax, rax
0x180150bd6  jnz     short loc_180150BF1
0x180150bd8  lea     rcx, aKernel32Dll_0
0x180150bdf  call    cs:GetModuleHandleW
0x180150be5  mov     rbx, rax
0x180150be8  test    rax, rax
0x180150beb  jz      loc_180150CCA
0x180150bf1  lea     rdx, aInitializecond
0x180150bf8  mov     rcx, rbx; hModule
0x180150bfb  call    cs:GetProcAddress
0x180150c01  lea     rdx, aSleepcondition
0x180150c08  mov     rcx, rbx; hModule
0x180150c0b  mov     rsi, rax
0x180150c0e  call    cs:GetProcAddress
0x180150c14  lea     rdx, aWakeallconditi
0x180150c1b  mov     rcx, rbx; hModule
0x180150c1e  mov     rdi, rax
0x180150c21  call    cs:GetProcAddress
0x180150c27  mov     rbx, rax
0x180150c2a  test    rsi, rsi
0x180150c2d  jz      short loc_180150C8C
0x180150c2f  test    rdi, rdi
0x180150c32  jz      short loc_180150C8C
0x180150c34  test    rax, rax
0x180150c37  jz      short loc_180150C8C
0x180150c39  and     cs:hObject, 0
0x180150c41  mov     rcx, rsi; this
0x180150c44  call    j_?writeBase64Buf@Vbase64Ostream@@MEAAXD@Z
0x180150c49  lea     rcx, qword_1802AF2C8
0x180150c50  call    rsi
0x180150c52  mov     rdx, cs:__security_cookie
0x180150c59  mov     ecx, 40h ; '@'
0x180150c5e  mov     eax, edx
0x180150c60  and     eax, 3Fh
0x180150c63  sub     ecx, eax
0x180150c65  ror     rdi, cl
0x180150c68  xor     rdi, rdx
0x180150c6b  ror     rbx, cl
0x180150c6e  xor     rbx, rdx
0x180150c71  mov     cs:qword_1802AF2D8, rdi
0x180150c78  mov     cs:qword_1802AF2E0, rbx
0x180150c7f  xor     ecx, ecx
0x180150c81  call    __scrt_initialize_onexit_tables
0x180150c86  test    al, al
0x180150c88  jz      short loc_180150CD5
0x180150c8a  jmp     short loc_180150CAC
0x180150c8c  xor     r9d, r9d; lpName
0x180150c8f  xor     r8d, r8d; bInitialState
0x180150c92  xor     ecx, ecx; lpEventAttributes
0x180150c94  lea     edx, [r9+1]; bManualReset
0x180150c98  call    cs:CreateEventW
0x180150c9e  mov     cs:hObject, rax
0x180150ca5  test    rax, rax
0x180150ca8  jz      short loc_180150CE0
0x180150caa  jmp     short loc_180150C7F
0x180150cac  lea     rcx, ?__scrt_uninitialize_thread_safe_statics@@YAXXZ; void (__cdecl *)()
0x180150cb3  call    atexit
0x180150cb8  mov     rbx, [rsp+28h+arg_0]
0x180150cbd  xor     eax, eax
0x180150cbf  mov     rsi, [rsp+28h+arg_8]
0x180150cc4  add     rsp, 20h
0x180150cc8  pop     rdi
0x180150cc9  retn
0x180150cca  mov     ecx, 7
0x180150ccf  call    __scrt_fastfail
0x180150cd4  int     3; Trap to Debugger
0x180150cd5  mov     ecx, 7
0x180150cda  call    __scrt_fastfail
0x180150cdf  int     3; Trap to Debugger
0x180150ce0  mov     ecx, 7
0x180150ce5  call    __scrt_fastfail
```
