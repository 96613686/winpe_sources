# CWinTaskHandler::CreateWorkerThread(IUnknown *)

- ea: `0x18000c3b4`
- end: `0x18000c508`
- name: `?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180011070`

## callees

- `0x18000c3b4`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000c405`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000c405`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000c4bc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000c4bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c413`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c46f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c413`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c46f`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000c45a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000c45a`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18000c4f0`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18000c4f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c4a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c4a5`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
      if ( GetModuleHandleExW(4u, &_ImageBase, (HMODULE *)this + 3) )
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
0x18000c3b4  mov     [rsp+arg_0], rbx
0x18000c3b9  mov     [rsp+arg_8], rsi
0x18000c3be  push    rdi
0x18000c3bf  sub     rsp, 30h
0x18000c3c3  mov     rax, [rdx]
0x18000c3c6  lea     rsi, [rcx+30h]
0x18000c3ca  mov     r9, rdx
0x18000c3cd  mov     rdi, rcx
0x18000c3d0  mov     r8, rsi
0x18000c3d3  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x18000c3da  mov     rcx, r9
0x18000c3dd  mov     rax, [rax]
0x18000c3e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3e5  mov     ebx, eax
0x18000c3e7  test    eax, eax
0x18000c3e9  js      loc_18000C493
0x18000c3ef  cmp     dword ptr [rdi+10h], 0
0x18000c3f3  jz      short loc_18000C42C
0x18000c3f5  lea     r8, [rdi+18h]; phModule
0x18000c3f9  mov     ecx, 4; dwFlags
0x18000c3fe  lea     rdx, __ImageBase; lpModuleName
0x18000c405  call    cs:__imp_GetModuleHandleExW
0x18000c40b  test    eax, eax
0x18000c40d  jz      short loc_18000C413
0x18000c40f  xor     ebx, ebx
0x18000c411  jmp     short loc_18000C42C
0x18000c413  call    cs:__imp_GetLastError
0x18000c419  mov     ebx, eax
0x18000c41b  test    eax, eax
0x18000c41d  jle     short loc_18000C428
0x18000c41f  movzx   ebx, ax
0x18000c422  or      ebx, 80070000h
0x18000c428  test    ebx, ebx
0x18000c42a  js      short loc_18000C497
0x18000c42c  mov     rax, [rdi]
0x18000c42f  mov     rcx, rdi
0x18000c432  mov     rax, [rax+8]
0x18000c436  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c43b  mov     r9, rdi; lpParameter
0x18000c43e  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x18000c447  lea     r8, ?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z; lpStartAddress
0x18000c44e  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x18000c456  xor     edx, edx; dwStackSize
0x18000c458  xor     ecx, ecx; lpThreadAttributes
0x18000c45a  call    cs:__imp_CreateThread
0x18000c460  mov     [rdi+28h], rax
0x18000c464  inc     rax
0x18000c467  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000c46d  jnz     short loc_18000C493
0x18000c46f  call    cs:__imp_GetLastError
0x18000c475  mov     ebx, eax
0x18000c477  test    eax, eax
0x18000c479  jle     short loc_18000C484
0x18000c47b  movzx   ebx, ax
0x18000c47e  or      ebx, 80070000h
0x18000c484  mov     rax, [rdi]
0x18000c487  mov     rcx, rdi
0x18000c48a  mov     rax, [rax+10h]
0x18000c48e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c493  test    ebx, ebx
0x18000c495  jns     short loc_18000C4E7
0x18000c497  mov     rcx, [rdi+28h]; hObject
0x18000c49b  lea     rax, [rcx-1]
0x18000c49f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000c4a3  ja      short loc_18000C4B3
0x18000c4a5  call    cs:__imp_CloseHandle
0x18000c4ab  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x18000c4b3  mov     rcx, [rdi+18h]; hLibModule
0x18000c4b7  test    rcx, rcx
0x18000c4ba  jz      short loc_18000C4CA
0x18000c4bc  call    cs:__imp_FreeLibrary
0x18000c4c2  mov     qword ptr [rdi+18h], 0
0x18000c4ca  mov     rcx, [rsi]
0x18000c4cd  test    rcx, rcx
0x18000c4d0  jz      short loc_18000C4F6
0x18000c4d2  mov     rax, [rcx]
0x18000c4d5  mov     rax, [rax+10h]
0x18000c4d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4de  mov     qword ptr [rsi], 0
0x18000c4e5  jmp     short loc_18000C4F6
0x18000c4e7  lock or [rsp+38h+var_38], 0
0x18000c4ec  mov     rcx, [rdi+28h]; hThread
0x18000c4f0  call    cs:__imp_ResumeThread
0x18000c4f6  mov     rsi, [rsp+38h+arg_8]
0x18000c4fb  mov     eax, ebx
0x18000c4fd  mov     rbx, [rsp+38h+arg_0]
0x18000c502  add     rsp, 30h
0x18000c506  pop     rdi
0x18000c507  retn
```
