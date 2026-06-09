# EnableMmcss(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&AvRevertMmThreadCharacteristics(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,ulong &)

- ea: `0x18003c790`
- end: `0x18003c8e1`
- name: `?EnableMmcss@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?AvRevertMmThreadCharacteristics@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEAK@Z`
- size: `337`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180028b30`
- `0x18003cdd0`

## callees

- `0x18000a814`
- `0x18003c790`
- `0x18003cd70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c7dc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c81b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c887`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c7dc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c81b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c887`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c7c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c808`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c83a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c874`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c7c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c808`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c83a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c874`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18003c8ce`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18003c8ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003c898`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003c8ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003c898`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003c8ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003c8c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003c8c0`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x18003c8a6`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x18003c8ba`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x18003c8a6`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x18003c8ba`
- `AVRT!AvSetMmThreadPriority` at `0x18003c82c`
- `AVRT!AvSetMmThreadPriority` at `0x18003c82c`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x18003c7d4`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x18003c813`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x18003c87f`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x18003c7d4`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x18003c813`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x18003c87f`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x18003c7b8`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x18003c7f7`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x18003c7b8`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x18003c7f7`

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
0x18003c790  push    rbx
0x18003c792  push    rbp
0x18003c793  push    rsi
0x18003c794  push    rdi
0x18003c795  push    r14; int
0x18003c797  sub     rsp, 20h
0x18003c79b  mov     r14, rdx
0x18003c79e  mov     rsi, rcx
0x18003c7a1  call    ?MMCSSUseEnabled@CMidiXProc@@SA_NXZ; CMidiXProc::MMCSSUseEnabled(void)
0x18003c7a6  test    al, al
0x18003c7a8  jz      loc_18003C898
0x18003c7ae  mov     rdx, r14; TaskIndex
0x18003c7b1  lea     rcx, TaskName; "Pro Audio"
0x18003c7b8  call    cs:__imp_AvSetMmThreadCharacteristicsW
0x18003c7be  mov     rbp, [rsi]
0x18003c7c1  mov     rdi, rax
0x18003c7c4  test    rbp, rbp
0x18003c7c7  jz      short loc_18003C7E2
0x18003c7c9  call    cs:__imp_GetLastError
0x18003c7cf  mov     rcx, rbp; AvrtHandle
0x18003c7d2  mov     ebx, eax
0x18003c7d4  call    cs:__imp_AvRevertMmThreadCharacteristics
0x18003c7da  mov     ecx, ebx; dwErrCode
0x18003c7dc  call    cs:__imp_SetLastError
0x18003c7e2  mov     [rsi], rdi
0x18003c7e5  test    rdi, rdi
0x18003c7e8  jnz     short loc_18003C824
0x18003c7ea  mov     rdx, r14; TaskIndex
0x18003c7ed  mov     [r14], edi
0x18003c7f0  lea     rcx, TaskName; "Pro Audio"
0x18003c7f7  call    cs:__imp_AvSetMmThreadCharacteristicsW
0x18003c7fd  mov     rbp, [rsi]
0x18003c800  mov     rdi, rax
0x18003c803  test    rbp, rbp
0x18003c806  jz      short loc_18003C821
0x18003c808  call    cs:__imp_GetLastError
0x18003c80e  mov     rcx, rbp; AvrtHandle
0x18003c811  mov     ebx, eax
0x18003c813  call    cs:__imp_AvRevertMmThreadCharacteristics
0x18003c819  mov     ecx, ebx; dwErrCode
0x18003c81b  call    cs:__imp_SetLastError
0x18003c821  mov     [rsi], rdi
0x18003c824  mov     edx, 1; Priority
0x18003c829  mov     rcx, rdi; AvrtHandle
0x18003c82c  call    cs:__imp_AvSetMmThreadPriority
0x18003c832  test    eax, eax
0x18003c834  jnz     loc_18003C8D4
0x18003c83a  call    cs:__imp_GetLastError
0x18003c840  mov     edi, eax
0x18003c842  test    eax, eax
0x18003c844  jle     short loc_18003C84F
0x18003c846  movzx   edi, ax
0x18003c849  or      edi, 80070000h
0x18003c84f  test    edi, edi
0x18003c851  jns     short loc_18003C86C
0x18003c853  mov     rcx, [rsp+48h]; this
0x18003c858  lea     r8, aAvcoreMidi2Lib_3; "avcore\\midi2\\libs\\midixproc\\midixpr"...
0x18003c85f  mov     r9d, edi; char *
0x18003c862  mov     edx, 0CEh; void *
0x18003c867  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c86c  mov     rbp, [rsi]
0x18003c86f  test    rbp, rbp
0x18003c872  jz      short loc_18003C88D
0x18003c874  call    cs:__imp_GetLastError
0x18003c87a  mov     rcx, rbp; AvrtHandle
0x18003c87d  mov     ebx, eax
0x18003c87f  call    cs:__imp_AvRevertMmThreadCharacteristics
0x18003c885  mov     ecx, ebx; dwErrCode
0x18003c887  call    cs:__imp_SetLastError
0x18003c88d  mov     qword ptr [rsi], 0
0x18003c894  mov     eax, edi
0x18003c896  jmp     short loc_18003C8D6
0x18003c898  call    cs:__imp_GetCurrentProcess
0x18003c89e  mov     rcx, rax; hProcess
0x18003c8a1  mov     edx, 80h; dwPriorityClass
0x18003c8a6  call    cs:__imp_SetPriorityClass
0x18003c8ac  call    cs:__imp_GetCurrentProcess
0x18003c8b2  mov     rcx, rax; hProcess
0x18003c8b5  mov     edx, 100h; dwPriorityClass
0x18003c8ba  call    cs:__imp_SetPriorityClass
0x18003c8c0  call    cs:__imp_GetCurrentThread
0x18003c8c6  mov     rcx, rax; hThread
0x18003c8c9  mov     edx, 0Fh; nPriority
0x18003c8ce  call    cs:__imp_SetThreadPriority
0x18003c8d4  xor     eax, eax
0x18003c8d6  add     rsp, 20h
0x18003c8da  pop     r14
0x18003c8dc  pop     rdi
0x18003c8dd  pop     rsi
0x18003c8de  pop     rbp
0x18003c8df  pop     rbx
0x18003c8e0  retn
```
