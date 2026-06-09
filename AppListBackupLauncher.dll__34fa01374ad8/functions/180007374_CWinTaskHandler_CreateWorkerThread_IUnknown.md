# CWinTaskHandler::CreateWorkerThread(IUnknown *)

- ea: `0x180007374`
- end: `0x1800074c8`
- name: `?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18000cbc0`

## callees

- `0x180007374`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000747c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000747c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800073c5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800073c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800073d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000742f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800073d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000742f`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800074b0`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800074b0`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000741a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000741a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007465`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007465`

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
0x180007374  mov     [rsp+arg_0], rbx
0x180007379  mov     [rsp+arg_8], rsi
0x18000737e  push    rdi
0x18000737f  sub     rsp, 30h
0x180007383  mov     rax, [rdx]
0x180007386  lea     rsi, [rcx+30h]
0x18000738a  mov     r9, rdx
0x18000738d  mov     rdi, rcx
0x180007390  mov     r8, rsi
0x180007393  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x18000739a  mov     rcx, r9
0x18000739d  mov     rax, [rax]
0x1800073a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073a5  mov     ebx, eax
0x1800073a7  test    eax, eax
0x1800073a9  js      loc_180007453
0x1800073af  cmp     dword ptr [rdi+10h], 0
0x1800073b3  jz      short loc_1800073EC
0x1800073b5  lea     r8, [rdi+18h]; phModule
0x1800073b9  mov     ecx, 4; dwFlags
0x1800073be  lea     rdx, cs:180000000h; lpModuleName
0x1800073c5  call    cs:__imp_GetModuleHandleExW
0x1800073cb  test    eax, eax
0x1800073cd  jz      short loc_1800073D3
0x1800073cf  xor     ebx, ebx
0x1800073d1  jmp     short loc_1800073EC
0x1800073d3  call    cs:__imp_GetLastError
0x1800073d9  mov     ebx, eax
0x1800073db  test    eax, eax
0x1800073dd  jle     short loc_1800073E8
0x1800073df  movzx   ebx, ax
0x1800073e2  or      ebx, 80070000h
0x1800073e8  test    ebx, ebx
0x1800073ea  js      short loc_180007457
0x1800073ec  mov     rax, [rdi]
0x1800073ef  mov     rcx, rdi
0x1800073f2  mov     rax, [rax+8]
0x1800073f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073fb  mov     r9, rdi; lpParameter
0x1800073fe  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x180007407  lea     r8, ?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z; lpStartAddress
0x18000740e  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x180007416  xor     edx, edx; dwStackSize
0x180007418  xor     ecx, ecx; lpThreadAttributes
0x18000741a  call    cs:__imp_CreateThread
0x180007420  mov     [rdi+28h], rax
0x180007424  inc     rax
0x180007427  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000742d  jnz     short loc_180007453
0x18000742f  call    cs:__imp_GetLastError
0x180007435  mov     ebx, eax
0x180007437  test    eax, eax
0x180007439  jle     short loc_180007444
0x18000743b  movzx   ebx, ax
0x18000743e  or      ebx, 80070000h
0x180007444  mov     rax, [rdi]
0x180007447  mov     rcx, rdi
0x18000744a  mov     rax, [rax+10h]
0x18000744e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007453  test    ebx, ebx
0x180007455  jns     short loc_1800074A7
0x180007457  mov     rcx, [rdi+28h]; hObject
0x18000745b  lea     rax, [rcx-1]
0x18000745f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180007463  ja      short loc_180007473
0x180007465  call    cs:__imp_CloseHandle
0x18000746b  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x180007473  mov     rcx, [rdi+18h]; hLibModule
0x180007477  test    rcx, rcx
0x18000747a  jz      short loc_18000748A
0x18000747c  call    cs:__imp_FreeLibrary
0x180007482  mov     qword ptr [rdi+18h], 0
0x18000748a  mov     rcx, [rsi]
0x18000748d  test    rcx, rcx
0x180007490  jz      short loc_1800074B6
0x180007492  mov     rax, [rcx]
0x180007495  mov     rax, [rax+10h]
0x180007499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000749e  mov     qword ptr [rsi], 0
0x1800074a5  jmp     short loc_1800074B6
0x1800074a7  lock or [rsp+38h+var_38], 0
0x1800074ac  mov     rcx, [rdi+28h]; hThread
0x1800074b0  call    cs:__imp_ResumeThread
0x1800074b6  mov     rsi, [rsp+38h+arg_8]
0x1800074bb  mov     eax, ebx
0x1800074bd  mov     rbx, [rsp+38h+arg_0]
0x1800074c2  add     rsp, 30h
0x1800074c6  pop     rdi
0x1800074c7  retn
```
