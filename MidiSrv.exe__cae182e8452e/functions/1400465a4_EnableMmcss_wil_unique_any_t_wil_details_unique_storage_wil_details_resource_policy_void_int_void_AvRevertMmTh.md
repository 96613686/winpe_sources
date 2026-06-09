# EnableMmcss(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&AvRevertMmThreadCharacteristics(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,ulong &)

- ea: `0x1400465a4`
- end: `0x1400466f5`
- name: `?EnableMmcss@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?AvRevertMmThreadCharacteristics@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEAK@Z`
- size: `337`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1400152d0`
- `0x140046bf0`

## callees

- `0x14000a6b4`
- `0x1400465a4`
- `0x140046b90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400465f0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14004662f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14004669b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400465f0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14004662f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14004669b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400465dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004661c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004664e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046688`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400465dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004661c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004664e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046688`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400466d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400466d4`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x1400466ba`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x1400466ce`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x1400466ba`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x1400466ce`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1400466e2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1400466e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400466ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400466c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400466ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400466c0`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x1400465e8`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x140046627`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x140046693`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x1400465e8`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x140046627`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x140046693`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x1400465cc`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x14004660b`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x1400465cc`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x14004660b`
- `AVRT!AvSetMmThreadPriority` at `0x140046640`
- `AVRT!AvSetMmThreadPriority` at `0x140046640`

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
0x1400465a4  push    rbx
0x1400465a6  push    rbp
0x1400465a7  push    rsi
0x1400465a8  push    rdi
0x1400465a9  push    r14; int
0x1400465ab  sub     rsp, 20h
0x1400465af  mov     r14, rdx
0x1400465b2  mov     rsi, rcx
0x1400465b5  call    ?MMCSSUseEnabled@CMidiXProc@@SA_NXZ; CMidiXProc::MMCSSUseEnabled(void)
0x1400465ba  test    al, al
0x1400465bc  jz      loc_1400466AC
0x1400465c2  mov     rdx, r14; TaskIndex
0x1400465c5  lea     rcx, TaskName; "Pro Audio"
0x1400465cc  call    cs:__imp_AvSetMmThreadCharacteristicsW
0x1400465d2  mov     rbp, [rsi]
0x1400465d5  mov     rdi, rax
0x1400465d8  test    rbp, rbp
0x1400465db  jz      short loc_1400465F6
0x1400465dd  call    cs:__imp_GetLastError
0x1400465e3  mov     rcx, rbp; AvrtHandle
0x1400465e6  mov     ebx, eax
0x1400465e8  call    cs:__imp_AvRevertMmThreadCharacteristics
0x1400465ee  mov     ecx, ebx; dwErrCode
0x1400465f0  call    cs:__imp_SetLastError
0x1400465f6  mov     [rsi], rdi
0x1400465f9  test    rdi, rdi
0x1400465fc  jnz     short loc_140046638
0x1400465fe  mov     rdx, r14; TaskIndex
0x140046601  mov     [r14], edi
0x140046604  lea     rcx, TaskName; "Pro Audio"
0x14004660b  call    cs:__imp_AvSetMmThreadCharacteristicsW
0x140046611  mov     rbp, [rsi]
0x140046614  mov     rdi, rax
0x140046617  test    rbp, rbp
0x14004661a  jz      short loc_140046635
0x14004661c  call    cs:__imp_GetLastError
0x140046622  mov     rcx, rbp; AvrtHandle
0x140046625  mov     ebx, eax
0x140046627  call    cs:__imp_AvRevertMmThreadCharacteristics
0x14004662d  mov     ecx, ebx; dwErrCode
0x14004662f  call    cs:__imp_SetLastError
0x140046635  mov     [rsi], rdi
0x140046638  mov     edx, 1; Priority
0x14004663d  mov     rcx, rdi; AvrtHandle
0x140046640  call    cs:__imp_AvSetMmThreadPriority
0x140046646  test    eax, eax
0x140046648  jnz     loc_1400466E8
0x14004664e  call    cs:__imp_GetLastError
0x140046654  mov     edi, eax
0x140046656  test    eax, eax
0x140046658  jle     short loc_140046663
0x14004665a  movzx   edi, ax
0x14004665d  or      edi, 80070000h
0x140046663  test    edi, edi
0x140046665  jns     short loc_140046680
0x140046667  mov     rcx, [rsp+48h]; this
0x14004666c  lea     r8, aAvcoreMidi2Lib_0; "avcore\\midi2\\libs\\midixproc\\midixpr"...
0x140046673  mov     r9d, edi; char *
0x140046676  mov     edx, 0CEh; void *
0x14004667b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140046680  mov     rbp, [rsi]
0x140046683  test    rbp, rbp
0x140046686  jz      short loc_1400466A1
0x140046688  call    cs:__imp_GetLastError
0x14004668e  mov     rcx, rbp; AvrtHandle
0x140046691  mov     ebx, eax
0x140046693  call    cs:__imp_AvRevertMmThreadCharacteristics
0x140046699  mov     ecx, ebx; dwErrCode
0x14004669b  call    cs:__imp_SetLastError
0x1400466a1  mov     qword ptr [rsi], 0
0x1400466a8  mov     eax, edi
0x1400466aa  jmp     short loc_1400466EA
0x1400466ac  call    cs:__imp_GetCurrentProcess
0x1400466b2  mov     rcx, rax; hProcess
0x1400466b5  mov     edx, 80h; dwPriorityClass
0x1400466ba  call    cs:__imp_SetPriorityClass
0x1400466c0  call    cs:__imp_GetCurrentProcess
0x1400466c6  mov     rcx, rax; hProcess
0x1400466c9  mov     edx, 100h; dwPriorityClass
0x1400466ce  call    cs:__imp_SetPriorityClass
0x1400466d4  call    cs:__imp_GetCurrentThread
0x1400466da  mov     rcx, rax; hThread
0x1400466dd  mov     edx, 0Fh; nPriority
0x1400466e2  call    cs:__imp_SetThreadPriority
0x1400466e8  xor     eax, eax
0x1400466ea  add     rsp, 20h
0x1400466ee  pop     r14
0x1400466f0  pop     rdi
0x1400466f1  pop     rsi
0x1400466f2  pop     rbp
0x1400466f3  pop     rbx
0x1400466f4  retn
```
