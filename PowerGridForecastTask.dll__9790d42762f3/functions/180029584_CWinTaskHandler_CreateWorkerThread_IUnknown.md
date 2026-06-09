# CWinTaskHandler::CreateWorkerThread(IUnknown *)

- ea: `0x180029584`
- end: `0x1800296d8`
- name: `?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18002e720`

## callees

- `0x180029584`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029675`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029675`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002968c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002968c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800295d5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800295d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800295e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002963f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800295e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002963f`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002962a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002962a`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800296c0`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800296c0`

## pseudocode

```c
__int64 __fastcall CWinTaskHandler::CreateWorkerThread(CWinTaskHandler *this, struct IUnknown *a2)
{
  _QWORD *v2; // rsi
  signed int v4; // ebx
  signed int LastError; // eax
  HANDLE Thread; // rax
  signed int v7; // eax
  char *v8; // rcx
  HMODULE v9; // rcx
  signed __int32 v11[8]; // [rsp+0h] [rbp-38h] BYREF

  v2 = (_QWORD *)((char *)this + 48);
  v4 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, char *))a2->lpVtbl->QueryInterface)(
         a2,
         &GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a,
         (char *)this + 48);
  if ( v4 >= 0 )
  {
    if ( *((_DWORD *)this + 4) )
    {
      if ( GetModuleHandleExW(4u, (LPCWSTR)0x180000000LL, (HMODULE *)this + 3) )
      {
        v4 = 0;
      }
      else
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
        if ( v4 < 0 )
          goto LABEL_13;
      }
    }
    (*(void (__fastcall **)(CWinTaskHandler *))(*(_QWORD *)this + 8LL))(this);
    Thread = CreateThread(0, 0, CWinTaskHandler::WorkerThreadProc, this, 4u, 0);
    *((_QWORD *)this + 5) = Thread;
    if ( (((unsigned __int64)Thread + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      v7 = GetLastError();
      v4 = v7;
      if ( v7 > 0 )
        v4 = (unsigned __int16)v7 | 0x80070000;
      (*(void (__fastcall **)(CWinTaskHandler *))(*(_QWORD *)this + 16LL))(this);
    }
  }
  if ( v4 >= 0 )
  {
    _InterlockedOr(v11, 0);
    ResumeThread(*((HANDLE *)this + 5));
    return (unsigned int)v4;
  }
LABEL_13:
  v8 = (char *)*((_QWORD *)this + 5);
  if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v8);
    *((_QWORD *)this + 5) = -1;
  }
  v9 = (HMODULE)*((_QWORD *)this + 3);
  if ( v9 )
  {
    FreeLibrary(v9);
    *((_QWORD *)this + 3) = 0;
  }
  if ( *v2 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 16LL))(*v2);
    *v2 = 0;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180029584  mov     [rsp+arg_0], rbx
0x180029589  mov     [rsp+arg_8], rsi
0x18002958e  push    rdi
0x18002958f  sub     rsp, 30h
0x180029593  mov     rax, [rdx]
0x180029596  lea     rsi, [rcx+30h]
0x18002959a  mov     r9, rdx
0x18002959d  mov     rdi, rcx
0x1800295a0  mov     r8, rsi
0x1800295a3  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x1800295aa  mov     rcx, r9
0x1800295ad  mov     rax, [rax]
0x1800295b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800295b5  mov     ebx, eax
0x1800295b7  test    eax, eax
0x1800295b9  js      loc_180029663
0x1800295bf  cmp     dword ptr [rdi+10h], 0
0x1800295c3  jz      short loc_1800295FC
0x1800295c5  lea     r8, [rdi+18h]; phModule
0x1800295c9  mov     ecx, 4; dwFlags
0x1800295ce  lea     rdx, cs:180000000h; lpModuleName
0x1800295d5  call    cs:__imp_GetModuleHandleExW
0x1800295db  test    eax, eax
0x1800295dd  jz      short loc_1800295E3
0x1800295df  xor     ebx, ebx
0x1800295e1  jmp     short loc_1800295FC
0x1800295e3  call    cs:__imp_GetLastError
0x1800295e9  mov     ebx, eax
0x1800295eb  test    eax, eax
0x1800295ed  jle     short loc_1800295F8
0x1800295ef  movzx   ebx, ax
0x1800295f2  or      ebx, 80070000h
0x1800295f8  test    ebx, ebx
0x1800295fa  js      short loc_180029667
0x1800295fc  mov     rax, [rdi]
0x1800295ff  mov     rcx, rdi
0x180029602  mov     rax, [rax+8]
0x180029606  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002960b  mov     r9, rdi; lpParameter
0x18002960e  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x180029617  lea     r8, ?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z; lpStartAddress
0x18002961e  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x180029626  xor     edx, edx; dwStackSize
0x180029628  xor     ecx, ecx; lpThreadAttributes
0x18002962a  call    cs:__imp_CreateThread
0x180029630  mov     [rdi+28h], rax
0x180029634  inc     rax
0x180029637  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002963d  jnz     short loc_180029663
0x18002963f  call    cs:__imp_GetLastError
0x180029645  mov     ebx, eax
0x180029647  test    eax, eax
0x180029649  jle     short loc_180029654
0x18002964b  movzx   ebx, ax
0x18002964e  or      ebx, 80070000h
0x180029654  mov     rax, [rdi]
0x180029657  mov     rcx, rdi
0x18002965a  mov     rax, [rax+10h]
0x18002965e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029663  test    ebx, ebx
0x180029665  jns     short loc_1800296B7
0x180029667  mov     rcx, [rdi+28h]; hObject
0x18002966b  lea     rax, [rcx-1]
0x18002966f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180029673  ja      short loc_180029683
0x180029675  call    cs:__imp_CloseHandle
0x18002967b  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x180029683  mov     rcx, [rdi+18h]; hLibModule
0x180029687  test    rcx, rcx
0x18002968a  jz      short loc_18002969A
0x18002968c  call    cs:__imp_FreeLibrary
0x180029692  mov     qword ptr [rdi+18h], 0
0x18002969a  mov     rcx, [rsi]
0x18002969d  test    rcx, rcx
0x1800296a0  jz      short loc_1800296C6
0x1800296a2  mov     rax, [rcx]
0x1800296a5  mov     rax, [rax+10h]
0x1800296a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800296ae  mov     qword ptr [rsi], 0
0x1800296b5  jmp     short loc_1800296C6
0x1800296b7  lock or [rsp+38h+var_38], 0
0x1800296bc  mov     rcx, [rdi+28h]; hThread
0x1800296c0  call    cs:__imp_ResumeThread
0x1800296c6  mov     rsi, [rsp+38h+arg_8]
0x1800296cb  mov     eax, ebx
0x1800296cd  mov     rbx, [rsp+38h+arg_0]
0x1800296d2  add     rsp, 30h
0x1800296d6  pop     rdi
0x1800296d7  retn
```
