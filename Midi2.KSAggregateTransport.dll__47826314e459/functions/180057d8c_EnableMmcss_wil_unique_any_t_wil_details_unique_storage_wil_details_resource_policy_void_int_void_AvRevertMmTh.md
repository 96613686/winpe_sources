# EnableMmcss(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&AvRevertMmThreadCharacteristics(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,ulong &)

- ea: `0x180057d8c`
- end: `0x180057edd`
- name: `?EnableMmcss@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?AvRevertMmThreadCharacteristics@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEAK@Z`
- size: `337`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180049670`
- `0x1800583d0`

## callees

- `0x18000b394`
- `0x180057d8c`
- `0x18005836c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180057dd8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180057e17`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180057e83`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180057dd8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180057e17`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180057e83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057dc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057e04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057e36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057e70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057dc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057e04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057e36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057e70`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180057eca`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180057eca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180057e94`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180057ea8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180057e94`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180057ea8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180057ebc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180057ebc`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x180057ea2`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x180057eb6`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x180057ea2`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x180057eb6`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x180057db4`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x180057df3`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x180057db4`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x180057df3`
- `AVRT!AvSetMmThreadPriority` at `0x180057e28`
- `AVRT!AvSetMmThreadPriority` at `0x180057e28`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x180057dd0`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x180057e0f`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x180057e7b`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x180057dd0`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x180057e0f`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x180057e7b`

## pseudocode

```c
__int64 __fastcall EnableMmcss(void **a1, DWORD *a2)
{
  HANDLE v4; // rax
  void *v5; // rbp
  void *v6; // rdi
  DWORD LastError; // ebx
  HANDLE v8; // rax
  void *v9; // rbp
  DWORD v10; // ebx
  signed int v11; // eax
  unsigned int v12; // edi
  void *v13; // rbp
  DWORD v14; // ebx
  HANDLE CurrentProcess; // rax
  HANDLE v17; // rax
  HANDLE CurrentThread; // rax
  int v19; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( !CMidiXProc::MMCSSUseEnabled() )
  {
    CurrentProcess = GetCurrentProcess();
    SetPriorityClass(CurrentProcess, 0x80u);
    v17 = GetCurrentProcess();
    SetPriorityClass(v17, 0x100u);
    CurrentThread = GetCurrentThread();
    SetThreadPriority(CurrentThread, 15);
    return 0;
  }
  v4 = AvSetMmThreadCharacteristicsW(L"Pro Audio", a2);
  v5 = *a1;
  v6 = v4;
  if ( *a1 )
  {
    LastError = GetLastError();
    AvRevertMmThreadCharacteristics(v5);
    SetLastError(LastError);
  }
  *a1 = v6;
  if ( !v6 )
  {
    *a2 = 0;
    v8 = AvSetMmThreadCharacteristicsW(L"Pro Audio", a2);
    v9 = *a1;
    v6 = v8;
    if ( *a1 )
    {
      v10 = GetLastError();
      AvRevertMmThreadCharacteristics(v9);
      SetLastError(v10);
    }
    *a1 = v6;
  }
  if ( AvSetMmThreadPriority(v6, AVRT_PRIORITY_HIGH) )
    return 0;
  v11 = GetLastError();
  v12 = v11;
  if ( v11 > 0 )
    v12 = (unsigned __int16)v11 | 0x80070000;
  if ( (v12 & 0x80000000) != 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCE,
      (unsigned int)"avcore\\midi2\\libs\\midixproc\\midixproc.cpp",
      (const char *)v12,
      v19);
  v13 = *a1;
  if ( *a1 )
  {
    v14 = GetLastError();
    AvRevertMmThreadCharacteristics(v13);
    SetLastError(v14);
  }
  *a1 = 0;
  return v12;
}

```

## disassembly

```asm
0x180057d8c  push    rbx
0x180057d8e  push    rbp
0x180057d8f  push    rsi
0x180057d90  push    rdi
0x180057d91  push    r14; int
0x180057d93  sub     rsp, 20h
0x180057d97  mov     r14, rdx
0x180057d9a  mov     rsi, rcx
0x180057d9d  call    ?MMCSSUseEnabled@CMidiXProc@@SA_NXZ; CMidiXProc::MMCSSUseEnabled(void)
0x180057da2  test    al, al
0x180057da4  jz      loc_180057E94
0x180057daa  mov     rdx, r14; TaskIndex
0x180057dad  lea     rcx, TaskName; "Pro Audio"
0x180057db4  call    cs:__imp_AvSetMmThreadCharacteristicsW
0x180057dba  mov     rbp, [rsi]
0x180057dbd  mov     rdi, rax
0x180057dc0  test    rbp, rbp
0x180057dc3  jz      short loc_180057DDE
0x180057dc5  call    cs:__imp_GetLastError
0x180057dcb  mov     rcx, rbp; AvrtHandle
0x180057dce  mov     ebx, eax
0x180057dd0  call    cs:__imp_AvRevertMmThreadCharacteristics
0x180057dd6  mov     ecx, ebx; dwErrCode
0x180057dd8  call    cs:__imp_SetLastError
0x180057dde  mov     [rsi], rdi
0x180057de1  test    rdi, rdi
0x180057de4  jnz     short loc_180057E20
0x180057de6  mov     rdx, r14; TaskIndex
0x180057de9  mov     [r14], edi
0x180057dec  lea     rcx, TaskName; "Pro Audio"
0x180057df3  call    cs:__imp_AvSetMmThreadCharacteristicsW
0x180057df9  mov     rbp, [rsi]
0x180057dfc  mov     rdi, rax
0x180057dff  test    rbp, rbp
0x180057e02  jz      short loc_180057E1D
0x180057e04  call    cs:__imp_GetLastError
0x180057e0a  mov     rcx, rbp; AvrtHandle
0x180057e0d  mov     ebx, eax
0x180057e0f  call    cs:__imp_AvRevertMmThreadCharacteristics
0x180057e15  mov     ecx, ebx; dwErrCode
0x180057e17  call    cs:__imp_SetLastError
0x180057e1d  mov     [rsi], rdi
0x180057e20  mov     edx, 1; Priority
0x180057e25  mov     rcx, rdi; AvrtHandle
0x180057e28  call    cs:__imp_AvSetMmThreadPriority
0x180057e2e  test    eax, eax
0x180057e30  jnz     loc_180057ED0
0x180057e36  call    cs:__imp_GetLastError
0x180057e3c  mov     edi, eax
0x180057e3e  test    eax, eax
0x180057e40  jle     short loc_180057E4B
0x180057e42  movzx   edi, ax
0x180057e45  or      edi, 80070000h
0x180057e4b  test    edi, edi
0x180057e4d  jns     short loc_180057E68
0x180057e4f  mov     rcx, [rsp+48h]; this
0x180057e54  lea     r8, aAvcoreMidi2Lib_3; "avcore\\midi2\\libs\\midixproc\\midixpr"...
0x180057e5b  mov     r9d, edi; char *
0x180057e5e  mov     edx, 0CEh; void *
0x180057e63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180057e68  mov     rbp, [rsi]
0x180057e6b  test    rbp, rbp
0x180057e6e  jz      short loc_180057E89
0x180057e70  call    cs:__imp_GetLastError
0x180057e76  mov     rcx, rbp; AvrtHandle
0x180057e79  mov     ebx, eax
0x180057e7b  call    cs:__imp_AvRevertMmThreadCharacteristics
0x180057e81  mov     ecx, ebx; dwErrCode
0x180057e83  call    cs:__imp_SetLastError
0x180057e89  mov     qword ptr [rsi], 0
0x180057e90  mov     eax, edi
0x180057e92  jmp     short loc_180057ED2
0x180057e94  call    cs:__imp_GetCurrentProcess
0x180057e9a  mov     rcx, rax; hProcess
0x180057e9d  mov     edx, 80h; dwPriorityClass
0x180057ea2  call    cs:__imp_SetPriorityClass
0x180057ea8  call    cs:__imp_GetCurrentProcess
0x180057eae  mov     rcx, rax; hProcess
0x180057eb1  mov     edx, 100h; dwPriorityClass
0x180057eb6  call    cs:__imp_SetPriorityClass
0x180057ebc  call    cs:__imp_GetCurrentThread
0x180057ec2  mov     rcx, rax; hThread
0x180057ec5  mov     edx, 0Fh; nPriority
0x180057eca  call    cs:__imp_SetThreadPriority
0x180057ed0  xor     eax, eax
0x180057ed2  add     rsp, 20h
0x180057ed6  pop     r14
0x180057ed8  pop     rdi
0x180057ed9  pop     rsi
0x180057eda  pop     rbp
0x180057edb  pop     rbx
0x180057edc  retn
```
