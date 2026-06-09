# CWinTaskHandler::CreateWorkerThread(IUnknown *)

- ea: `0x180003cc4`
- end: `0x180003e18`
- name: `?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x1800050f0`

## callees

- `0x180003cc4`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180003dcc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180003dcc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180003d15`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180003d15`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180003d6a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180003d6a`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180003e00`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180003e00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003db5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003db5`

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
0x180003cc4  mov     [rsp+arg_0], rbx
0x180003cc9  mov     [rsp+arg_8], rsi
0x180003cce  push    rdi
0x180003ccf  sub     rsp, 30h
0x180003cd3  mov     rax, [rdx]
0x180003cd6  lea     rsi, [rcx+30h]
0x180003cda  mov     r9, rdx
0x180003cdd  mov     rdi, rcx
0x180003ce0  mov     r8, rsi
0x180003ce3  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x180003cea  mov     rcx, r9
0x180003ced  mov     rax, [rax]
0x180003cf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cf5  mov     ebx, eax
0x180003cf7  test    eax, eax
0x180003cf9  js      loc_180003DA3
0x180003cff  cmp     dword ptr [rdi+10h], 0
0x180003d03  jz      short loc_180003D3C
0x180003d05  lea     r8, [rdi+18h]; phModule
0x180003d09  mov     ecx, 4; dwFlags
0x180003d0e  lea     rdx, cs:180000000h; lpModuleName
0x180003d15  call    cs:__imp_GetModuleHandleExW
0x180003d1b  test    eax, eax
0x180003d1d  jz      short loc_180003D23
0x180003d1f  xor     ebx, ebx
0x180003d21  jmp     short loc_180003D3C
0x180003d23  call    cs:__imp_GetLastError
0x180003d29  mov     ebx, eax
0x180003d2b  test    eax, eax
0x180003d2d  jle     short loc_180003D38
0x180003d2f  movzx   ebx, ax
0x180003d32  or      ebx, 80070000h
0x180003d38  test    ebx, ebx
0x180003d3a  js      short loc_180003DA7
0x180003d3c  mov     rax, [rdi]
0x180003d3f  mov     rcx, rdi
0x180003d42  mov     rax, [rax+8]
0x180003d46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d4b  mov     r9, rdi; lpParameter
0x180003d4e  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x180003d57  lea     r8, ?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z; lpStartAddress
0x180003d5e  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x180003d66  xor     edx, edx; dwStackSize
0x180003d68  xor     ecx, ecx; lpThreadAttributes
0x180003d6a  call    cs:__imp_CreateThread
0x180003d70  mov     [rdi+28h], rax
0x180003d74  inc     rax
0x180003d77  test    rax, 0FFFFFFFFFFFFFFFEh
0x180003d7d  jnz     short loc_180003DA3
0x180003d7f  call    cs:__imp_GetLastError
0x180003d85  mov     ebx, eax
0x180003d87  test    eax, eax
0x180003d89  jle     short loc_180003D94
0x180003d8b  movzx   ebx, ax
0x180003d8e  or      ebx, 80070000h
0x180003d94  mov     rax, [rdi]
0x180003d97  mov     rcx, rdi
0x180003d9a  mov     rax, [rax+10h]
0x180003d9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003da3  test    ebx, ebx
0x180003da5  jns     short loc_180003DF7
0x180003da7  mov     rcx, [rdi+28h]; hObject
0x180003dab  lea     rax, [rcx-1]
0x180003daf  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180003db3  ja      short loc_180003DC3
0x180003db5  call    cs:__imp_CloseHandle
0x180003dbb  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x180003dc3  mov     rcx, [rdi+18h]; hLibModule
0x180003dc7  test    rcx, rcx
0x180003dca  jz      short loc_180003DDA
0x180003dcc  call    cs:__imp_FreeLibrary
0x180003dd2  mov     qword ptr [rdi+18h], 0
0x180003dda  mov     rcx, [rsi]
0x180003ddd  test    rcx, rcx
0x180003de0  jz      short loc_180003E06
0x180003de2  mov     rax, [rcx]
0x180003de5  mov     rax, [rax+10h]
0x180003de9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003dee  mov     qword ptr [rsi], 0
0x180003df5  jmp     short loc_180003E06
0x180003df7  lock or [rsp+38h+var_38], 0
0x180003dfc  mov     rcx, [rdi+28h]; hThread
0x180003e00  call    cs:__imp_ResumeThread
0x180003e06  mov     rsi, [rsp+38h+arg_8]
0x180003e0b  mov     eax, ebx
0x180003e0d  mov     rbx, [rsp+38h+arg_0]
0x180003e12  add     rsp, 30h
0x180003e16  pop     rdi
0x180003e17  retn
```
