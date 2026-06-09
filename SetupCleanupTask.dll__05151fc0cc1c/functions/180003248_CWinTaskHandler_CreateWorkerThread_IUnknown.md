# CWinTaskHandler::CreateWorkerThread(IUnknown *)

- ea: `0x180003248`
- end: `0x18000339c`
- name: `?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180003760`

## callees

- `0x180003248`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180003350`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180003350`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180003299`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180003299`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800032ee`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800032ee`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180003384`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180003384`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800032a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003303`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800032a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003303`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003339`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003339`

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
0x180003248  mov     [rsp+arg_0], rbx
0x18000324d  mov     [rsp+arg_8], rsi
0x180003252  push    rdi
0x180003253  sub     rsp, 30h
0x180003257  mov     rax, [rdx]
0x18000325a  lea     rsi, [rcx+30h]
0x18000325e  mov     r9, rdx
0x180003261  mov     rdi, rcx
0x180003264  mov     r8, rsi
0x180003267  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x18000326e  mov     rcx, r9
0x180003271  mov     rax, [rax]
0x180003274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003279  mov     ebx, eax
0x18000327b  test    eax, eax
0x18000327d  js      loc_180003327
0x180003283  cmp     dword ptr [rdi+10h], 0
0x180003287  jz      short loc_1800032C0
0x180003289  lea     r8, [rdi+18h]; phModule
0x18000328d  mov     ecx, 4; dwFlags
0x180003292  lea     rdx, cs:180000000h; lpModuleName
0x180003299  call    cs:__imp_GetModuleHandleExW
0x18000329f  test    eax, eax
0x1800032a1  jz      short loc_1800032A7
0x1800032a3  xor     ebx, ebx
0x1800032a5  jmp     short loc_1800032C0
0x1800032a7  call    cs:__imp_GetLastError
0x1800032ad  mov     ebx, eax
0x1800032af  test    eax, eax
0x1800032b1  jle     short loc_1800032BC
0x1800032b3  movzx   ebx, ax
0x1800032b6  or      ebx, 80070000h
0x1800032bc  test    ebx, ebx
0x1800032be  js      short loc_18000332B
0x1800032c0  mov     rax, [rdi]
0x1800032c3  mov     rcx, rdi
0x1800032c6  mov     rax, [rax+8]
0x1800032ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032cf  mov     r9, rdi; lpParameter
0x1800032d2  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x1800032db  lea     r8, ?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z; lpStartAddress
0x1800032e2  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x1800032ea  xor     edx, edx; dwStackSize
0x1800032ec  xor     ecx, ecx; lpThreadAttributes
0x1800032ee  call    cs:__imp_CreateThread
0x1800032f4  mov     [rdi+28h], rax
0x1800032f8  inc     rax
0x1800032fb  test    rax, 0FFFFFFFFFFFFFFFEh
0x180003301  jnz     short loc_180003327
0x180003303  call    cs:__imp_GetLastError
0x180003309  mov     ebx, eax
0x18000330b  test    eax, eax
0x18000330d  jle     short loc_180003318
0x18000330f  movzx   ebx, ax
0x180003312  or      ebx, 80070000h
0x180003318  mov     rax, [rdi]
0x18000331b  mov     rcx, rdi
0x18000331e  mov     rax, [rax+10h]
0x180003322  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003327  test    ebx, ebx
0x180003329  jns     short loc_18000337B
0x18000332b  mov     rcx, [rdi+28h]; hObject
0x18000332f  lea     rax, [rcx-1]
0x180003333  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180003337  ja      short loc_180003347
0x180003339  call    cs:__imp_CloseHandle
0x18000333f  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x180003347  mov     rcx, [rdi+18h]; hLibModule
0x18000334b  test    rcx, rcx
0x18000334e  jz      short loc_18000335E
0x180003350  call    cs:__imp_FreeLibrary
0x180003356  mov     qword ptr [rdi+18h], 0
0x18000335e  mov     rcx, [rsi]
0x180003361  test    rcx, rcx
0x180003364  jz      short loc_18000338A
0x180003366  mov     rax, [rcx]
0x180003369  mov     rax, [rax+10h]
0x18000336d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003372  mov     qword ptr [rsi], 0
0x180003379  jmp     short loc_18000338A
0x18000337b  lock or [rsp+38h+var_38], 0
0x180003380  mov     rcx, [rdi+28h]; hThread
0x180003384  call    cs:__imp_ResumeThread
0x18000338a  mov     rsi, [rsp+38h+arg_8]
0x18000338f  mov     eax, ebx
0x180003391  mov     rbx, [rsp+38h+arg_0]
0x180003396  add     rsp, 30h
0x18000339a  pop     rdi
0x18000339b  retn
```
