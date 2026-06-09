# EnableMmcss(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&AvRevertMmThreadCharacteristics(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,ulong &)

- ea: `0x18000d8b0`
- end: `0x18000da01`
- name: `?EnableMmcss@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?AvRevertMmThreadCharacteristics@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEAK@Z`
- size: `337`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000f4e0`

## callees

- `0x180007e24`
- `0x18000d8b0`
- `0x18000f438`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d8fc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d93b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d9a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d8fc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d93b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d9a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d8e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d928`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d95a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d994`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d8e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d928`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d95a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d994`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000d9ee`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000d9ee`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x18000d9c6`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x18000d9da`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x18000d9c6`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x18000d9da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000d9e0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000d9e0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000d9b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000d9cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000d9b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000d9cc`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x18000d8d8`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x18000d917`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x18000d8d8`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x18000d917`
- `AVRT!AvSetMmThreadPriority` at `0x18000d94c`
- `AVRT!AvSetMmThreadPriority` at `0x18000d94c`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x18000d8f4`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x18000d933`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x18000d99f`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x18000d8f4`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x18000d933`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x18000d99f`

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
0x18000d8b0  push    rbx
0x18000d8b2  push    rbp
0x18000d8b3  push    rsi
0x18000d8b4  push    rdi
0x18000d8b5  push    r14; int
0x18000d8b7  sub     rsp, 20h
0x18000d8bb  mov     r14, rdx
0x18000d8be  mov     rsi, rcx
0x18000d8c1  call    ?MMCSSUseEnabled@CMidiXProc@@SA_NXZ; CMidiXProc::MMCSSUseEnabled(void)
0x18000d8c6  test    al, al
0x18000d8c8  jz      loc_18000D9B8
0x18000d8ce  mov     rdx, r14; TaskIndex
0x18000d8d1  lea     rcx, TaskName; "Pro Audio"
0x18000d8d8  call    cs:__imp_AvSetMmThreadCharacteristicsW
0x18000d8de  mov     rbp, [rsi]
0x18000d8e1  mov     rdi, rax
0x18000d8e4  test    rbp, rbp
0x18000d8e7  jz      short loc_18000D902
0x18000d8e9  call    cs:__imp_GetLastError
0x18000d8ef  mov     rcx, rbp; AvrtHandle
0x18000d8f2  mov     ebx, eax
0x18000d8f4  call    cs:__imp_AvRevertMmThreadCharacteristics
0x18000d8fa  mov     ecx, ebx; dwErrCode
0x18000d8fc  call    cs:__imp_SetLastError
0x18000d902  mov     [rsi], rdi
0x18000d905  test    rdi, rdi
0x18000d908  jnz     short loc_18000D944
0x18000d90a  mov     rdx, r14; TaskIndex
0x18000d90d  mov     [r14], edi
0x18000d910  lea     rcx, TaskName; "Pro Audio"
0x18000d917  call    cs:__imp_AvSetMmThreadCharacteristicsW
0x18000d91d  mov     rbp, [rsi]
0x18000d920  mov     rdi, rax
0x18000d923  test    rbp, rbp
0x18000d926  jz      short loc_18000D941
0x18000d928  call    cs:__imp_GetLastError
0x18000d92e  mov     rcx, rbp; AvrtHandle
0x18000d931  mov     ebx, eax
0x18000d933  call    cs:__imp_AvRevertMmThreadCharacteristics
0x18000d939  mov     ecx, ebx; dwErrCode
0x18000d93b  call    cs:__imp_SetLastError
0x18000d941  mov     [rsi], rdi
0x18000d944  mov     edx, 1; Priority
0x18000d949  mov     rcx, rdi; AvrtHandle
0x18000d94c  call    cs:__imp_AvSetMmThreadPriority
0x18000d952  test    eax, eax
0x18000d954  jnz     loc_18000D9F4
0x18000d95a  call    cs:__imp_GetLastError
0x18000d960  mov     edi, eax
0x18000d962  test    eax, eax
0x18000d964  jle     short loc_18000D96F
0x18000d966  movzx   edi, ax
0x18000d969  or      edi, 80070000h
0x18000d96f  test    edi, edi
0x18000d971  jns     short loc_18000D98C
0x18000d973  mov     rcx, [rsp+48h]; this
0x18000d978  lea     r8, aAvcoreMidi2Lib_0; "avcore\\midi2\\libs\\midixproc\\midixpr"...
0x18000d97f  mov     r9d, edi; char *
0x18000d982  mov     edx, 0CEh; void *
0x18000d987  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d98c  mov     rbp, [rsi]
0x18000d98f  test    rbp, rbp
0x18000d992  jz      short loc_18000D9AD
0x18000d994  call    cs:__imp_GetLastError
0x18000d99a  mov     rcx, rbp; AvrtHandle
0x18000d99d  mov     ebx, eax
0x18000d99f  call    cs:__imp_AvRevertMmThreadCharacteristics
0x18000d9a5  mov     ecx, ebx; dwErrCode
0x18000d9a7  call    cs:__imp_SetLastError
0x18000d9ad  mov     qword ptr [rsi], 0
0x18000d9b4  mov     eax, edi
0x18000d9b6  jmp     short loc_18000D9F6
0x18000d9b8  call    cs:__imp_GetCurrentProcess
0x18000d9be  mov     rcx, rax; hProcess
0x18000d9c1  mov     edx, 80h; dwPriorityClass
0x18000d9c6  call    cs:__imp_SetPriorityClass
0x18000d9cc  call    cs:__imp_GetCurrentProcess
0x18000d9d2  mov     rcx, rax; hProcess
0x18000d9d5  mov     edx, 100h; dwPriorityClass
0x18000d9da  call    cs:__imp_SetPriorityClass
0x18000d9e0  call    cs:__imp_GetCurrentThread
0x18000d9e6  mov     rcx, rax; hThread
0x18000d9e9  mov     edx, 0Fh; nPriority
0x18000d9ee  call    cs:__imp_SetThreadPriority
0x18000d9f4  xor     eax, eax
0x18000d9f6  add     rsp, 20h
0x18000d9fa  pop     r14
0x18000d9fc  pop     rdi
0x18000d9fd  pop     rsi
0x18000d9fe  pop     rbp
0x18000d9ff  pop     rbx
0x18000da00  retn
```
