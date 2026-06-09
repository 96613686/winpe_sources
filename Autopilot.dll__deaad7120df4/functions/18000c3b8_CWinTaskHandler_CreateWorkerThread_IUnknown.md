# CWinTaskHandler::CreateWorkerThread(IUnknown *)

- ea: `0x18000c3b8`
- end: `0x18000c537`
- name: `?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z`
- size: `383`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180011060`

## callees

- `0x18000c3b8`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000c409`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000c409`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000c4de`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000c4de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c41d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c485`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c41d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c485`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000c46a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000c46a`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18000c518`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18000c518`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c4c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c4c1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18000c3b8  mov     [rsp+arg_0], rbx
0x18000c3bd  mov     [rsp+arg_8], rsi
0x18000c3c2  push    rdi
0x18000c3c3  sub     rsp, 30h
0x18000c3c7  mov     rax, [rdx]
0x18000c3ca  lea     rsi, [rcx+30h]
0x18000c3ce  mov     r9, rdx
0x18000c3d1  mov     rdi, rcx
0x18000c3d4  mov     r8, rsi
0x18000c3d7  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x18000c3de  mov     rcx, r9
0x18000c3e1  mov     rax, [rax]
0x18000c3e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3e9  mov     ebx, eax
0x18000c3eb  test    eax, eax
0x18000c3ed  js      loc_18000C4AF
0x18000c3f3  cmp     dword ptr [rdi+10h], 0
0x18000c3f7  jz      short loc_18000C43C
0x18000c3f9  lea     r8, [rdi+18h]; phModule
0x18000c3fd  mov     ecx, 4; dwFlags
0x18000c402  lea     rdx, __ImageBase; lpModuleName
0x18000c409  call    cs:__imp_GetModuleHandleExW
0x18000c410  nop     dword ptr [rax+rax+00h]
0x18000c415  test    eax, eax
0x18000c417  jz      short loc_18000C41D
0x18000c419  xor     ebx, ebx
0x18000c41b  jmp     short loc_18000C43C
0x18000c41d  call    cs:__imp_GetLastError
0x18000c424  nop     dword ptr [rax+rax+00h]
0x18000c429  mov     ebx, eax
0x18000c42b  test    eax, eax
0x18000c42d  jle     short loc_18000C438
0x18000c42f  movzx   ebx, ax
0x18000c432  or      ebx, 80070000h
0x18000c438  test    ebx, ebx
0x18000c43a  js      short loc_18000C4B3
0x18000c43c  mov     rax, [rdi]
0x18000c43f  mov     rcx, rdi
0x18000c442  mov     rax, [rax+8]
0x18000c446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c44b  mov     r9, rdi; lpParameter
0x18000c44e  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x18000c457  lea     r8, ?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z; lpStartAddress
0x18000c45e  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x18000c466  xor     edx, edx; dwStackSize
0x18000c468  xor     ecx, ecx; lpThreadAttributes
0x18000c46a  call    cs:__imp_CreateThread
0x18000c471  nop     dword ptr [rax+rax+00h]
0x18000c476  mov     [rdi+28h], rax
0x18000c47a  inc     rax
0x18000c47d  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000c483  jnz     short loc_18000C4AF
0x18000c485  call    cs:__imp_GetLastError
0x18000c48c  nop     dword ptr [rax+rax+00h]
0x18000c491  mov     ebx, eax
0x18000c493  test    eax, eax
0x18000c495  jle     short loc_18000C4A0
0x18000c497  movzx   ebx, ax
0x18000c49a  or      ebx, 80070000h
0x18000c4a0  mov     rax, [rdi]
0x18000c4a3  mov     rcx, rdi
0x18000c4a6  mov     rax, [rax+10h]
0x18000c4aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4af  test    ebx, ebx
0x18000c4b1  jns     short loc_18000C50F
0x18000c4b3  mov     rcx, [rdi+28h]; hObject
0x18000c4b7  lea     rax, [rcx-1]
0x18000c4bb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000c4bf  ja      short loc_18000C4D5
0x18000c4c1  call    cs:__imp_CloseHandle
0x18000c4c8  nop     dword ptr [rax+rax+00h]
0x18000c4cd  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x18000c4d5  mov     rcx, [rdi+18h]; hLibModule
0x18000c4d9  test    rcx, rcx
0x18000c4dc  jz      short loc_18000C4F2
0x18000c4de  call    cs:__imp_FreeLibrary
0x18000c4e5  nop     dword ptr [rax+rax+00h]
0x18000c4ea  mov     qword ptr [rdi+18h], 0
0x18000c4f2  mov     rcx, [rsi]
0x18000c4f5  test    rcx, rcx
0x18000c4f8  jz      short loc_18000C524
0x18000c4fa  mov     rax, [rcx]
0x18000c4fd  mov     rax, [rax+10h]
0x18000c501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c506  mov     qword ptr [rsi], 0
0x18000c50d  jmp     short loc_18000C524
0x18000c50f  lock or [rsp+38h+var_38], 0
0x18000c514  mov     rcx, [rdi+28h]; hThread
0x18000c518  call    cs:__imp_ResumeThread
0x18000c51f  nop     dword ptr [rax+rax+00h]
0x18000c524  mov     rsi, [rsp+38h+arg_8]
0x18000c529  mov     eax, ebx
0x18000c52b  mov     rbx, [rsp+38h+arg_0]
0x18000c530  add     rsp, 30h
0x18000c534  pop     rdi
0x18000c535  retn
```
