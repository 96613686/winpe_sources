# CWinTaskHandler::CreateWorkerThread(IUnknown *)

- ea: `0x180004274`
- end: `0x1800043c8`
- name: `?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180007bb0`

## callees

- `0x180004274`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800042c5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800042c5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000437c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000437c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000432f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000432f`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800043b0`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800043b0`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000431a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000431a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004365`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004365`

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
0x180004274  mov     [rsp+arg_0], rbx
0x180004279  mov     [rsp+arg_8], rsi
0x18000427e  push    rdi
0x18000427f  sub     rsp, 30h
0x180004283  mov     rax, [rdx]
0x180004286  lea     rsi, [rcx+30h]
0x18000428a  mov     r9, rdx
0x18000428d  mov     rdi, rcx
0x180004290  mov     r8, rsi
0x180004293  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x18000429a  mov     rcx, r9
0x18000429d  mov     rax, [rax]
0x1800042a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042a5  mov     ebx, eax
0x1800042a7  test    eax, eax
0x1800042a9  js      loc_180004353
0x1800042af  cmp     dword ptr [rdi+10h], 0
0x1800042b3  jz      short loc_1800042EC
0x1800042b5  lea     r8, [rdi+18h]; phModule
0x1800042b9  mov     ecx, 4; dwFlags
0x1800042be  lea     rdx, cs:180000000h; lpModuleName
0x1800042c5  call    cs:__imp_GetModuleHandleExW
0x1800042cb  test    eax, eax
0x1800042cd  jz      short loc_1800042D3
0x1800042cf  xor     ebx, ebx
0x1800042d1  jmp     short loc_1800042EC
0x1800042d3  call    cs:__imp_GetLastError
0x1800042d9  mov     ebx, eax
0x1800042db  test    eax, eax
0x1800042dd  jle     short loc_1800042E8
0x1800042df  movzx   ebx, ax
0x1800042e2  or      ebx, 80070000h
0x1800042e8  test    ebx, ebx
0x1800042ea  js      short loc_180004357
0x1800042ec  mov     rax, [rdi]
0x1800042ef  mov     rcx, rdi
0x1800042f2  mov     rax, [rax+8]
0x1800042f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042fb  mov     r9, rdi; lpParameter
0x1800042fe  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x180004307  lea     r8, ?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z; lpStartAddress
0x18000430e  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x180004316  xor     edx, edx; dwStackSize
0x180004318  xor     ecx, ecx; lpThreadAttributes
0x18000431a  call    cs:__imp_CreateThread
0x180004320  mov     [rdi+28h], rax
0x180004324  inc     rax
0x180004327  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000432d  jnz     short loc_180004353
0x18000432f  call    cs:__imp_GetLastError
0x180004335  mov     ebx, eax
0x180004337  test    eax, eax
0x180004339  jle     short loc_180004344
0x18000433b  movzx   ebx, ax
0x18000433e  or      ebx, 80070000h
0x180004344  mov     rax, [rdi]
0x180004347  mov     rcx, rdi
0x18000434a  mov     rax, [rax+10h]
0x18000434e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004353  test    ebx, ebx
0x180004355  jns     short loc_1800043A7
0x180004357  mov     rcx, [rdi+28h]; hObject
0x18000435b  lea     rax, [rcx-1]
0x18000435f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180004363  ja      short loc_180004373
0x180004365  call    cs:__imp_CloseHandle
0x18000436b  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x180004373  mov     rcx, [rdi+18h]; hLibModule
0x180004377  test    rcx, rcx
0x18000437a  jz      short loc_18000438A
0x18000437c  call    cs:__imp_FreeLibrary
0x180004382  mov     qword ptr [rdi+18h], 0
0x18000438a  mov     rcx, [rsi]
0x18000438d  test    rcx, rcx
0x180004390  jz      short loc_1800043B6
0x180004392  mov     rax, [rcx]
0x180004395  mov     rax, [rax+10h]
0x180004399  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000439e  mov     qword ptr [rsi], 0
0x1800043a5  jmp     short loc_1800043B6
0x1800043a7  lock or [rsp+38h+var_38], 0
0x1800043ac  mov     rcx, [rdi+28h]; hThread
0x1800043b0  call    cs:__imp_ResumeThread
0x1800043b6  mov     rsi, [rsp+38h+arg_8]
0x1800043bb  mov     eax, ebx
0x1800043bd  mov     rbx, [rsp+38h+arg_0]
0x1800043c2  add     rsp, 30h
0x1800043c6  pop     rdi
0x1800043c7  retn
```
