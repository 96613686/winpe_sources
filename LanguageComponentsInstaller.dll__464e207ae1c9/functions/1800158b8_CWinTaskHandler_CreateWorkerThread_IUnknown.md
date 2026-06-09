# CWinTaskHandler::CreateWorkerThread(IUnknown *)

- ea: `0x1800158b8`
- end: `0x180015a0c`
- name: `?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18001c000`

## callees

- `0x1800158b8`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800159c0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800159c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180015909`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180015909`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015917`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015973`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015917`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015973`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001595e`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001595e`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800159f4`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800159f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800159a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800159a9`

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
0x1800158b8  mov     [rsp+arg_0], rbx
0x1800158bd  mov     [rsp+arg_8], rsi
0x1800158c2  push    rdi
0x1800158c3  sub     rsp, 30h
0x1800158c7  mov     rax, [rdx]
0x1800158ca  lea     rsi, [rcx+30h]
0x1800158ce  mov     r9, rdx
0x1800158d1  mov     rdi, rcx
0x1800158d4  mov     r8, rsi
0x1800158d7  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x1800158de  mov     rcx, r9
0x1800158e1  mov     rax, [rax]
0x1800158e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158e9  mov     ebx, eax
0x1800158eb  test    eax, eax
0x1800158ed  js      loc_180015997
0x1800158f3  cmp     dword ptr [rdi+10h], 0
0x1800158f7  jz      short loc_180015930
0x1800158f9  lea     r8, [rdi+18h]; phModule
0x1800158fd  mov     ecx, 4; dwFlags
0x180015902  lea     rdx, __ImageBase; lpModuleName
0x180015909  call    cs:__imp_GetModuleHandleExW
0x18001590f  test    eax, eax
0x180015911  jz      short loc_180015917
0x180015913  xor     ebx, ebx
0x180015915  jmp     short loc_180015930
0x180015917  call    cs:__imp_GetLastError
0x18001591d  mov     ebx, eax
0x18001591f  test    eax, eax
0x180015921  jle     short loc_18001592C
0x180015923  movzx   ebx, ax
0x180015926  or      ebx, 80070000h
0x18001592c  test    ebx, ebx
0x18001592e  js      short loc_18001599B
0x180015930  mov     rax, [rdi]
0x180015933  mov     rcx, rdi
0x180015936  mov     rax, [rax+8]
0x18001593a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001593f  mov     r9, rdi; lpParameter
0x180015942  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x18001594b  lea     r8, ?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z; lpStartAddress
0x180015952  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x18001595a  xor     edx, edx; dwStackSize
0x18001595c  xor     ecx, ecx; lpThreadAttributes
0x18001595e  call    cs:__imp_CreateThread
0x180015964  mov     [rdi+28h], rax
0x180015968  inc     rax
0x18001596b  test    rax, 0FFFFFFFFFFFFFFFEh
0x180015971  jnz     short loc_180015997
0x180015973  call    cs:__imp_GetLastError
0x180015979  mov     ebx, eax
0x18001597b  test    eax, eax
0x18001597d  jle     short loc_180015988
0x18001597f  movzx   ebx, ax
0x180015982  or      ebx, 80070000h
0x180015988  mov     rax, [rdi]
0x18001598b  mov     rcx, rdi
0x18001598e  mov     rax, [rax+10h]
0x180015992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015997  test    ebx, ebx
0x180015999  jns     short loc_1800159EB
0x18001599b  mov     rcx, [rdi+28h]; hObject
0x18001599f  lea     rax, [rcx-1]
0x1800159a3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800159a7  ja      short loc_1800159B7
0x1800159a9  call    cs:__imp_CloseHandle
0x1800159af  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x1800159b7  mov     rcx, [rdi+18h]; hLibModule
0x1800159bb  test    rcx, rcx
0x1800159be  jz      short loc_1800159CE
0x1800159c0  call    cs:__imp_FreeLibrary
0x1800159c6  mov     qword ptr [rdi+18h], 0
0x1800159ce  mov     rcx, [rsi]
0x1800159d1  test    rcx, rcx
0x1800159d4  jz      short loc_1800159FA
0x1800159d6  mov     rax, [rcx]
0x1800159d9  mov     rax, [rax+10h]
0x1800159dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159e2  mov     qword ptr [rsi], 0
0x1800159e9  jmp     short loc_1800159FA
0x1800159eb  lock or [rsp+38h+var_38], 0
0x1800159f0  mov     rcx, [rdi+28h]; hThread
0x1800159f4  call    cs:__imp_ResumeThread
0x1800159fa  mov     rsi, [rsp+38h+arg_8]
0x1800159ff  mov     eax, ebx
0x180015a01  mov     rbx, [rsp+38h+arg_0]
0x180015a06  add     rsp, 30h
0x180015a0a  pop     rdi
0x180015a0b  retn
```
