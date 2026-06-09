# CWinTaskHandler::CreateWorkerThread(IUnknown *)

- ea: `0x180003d68`
- end: `0x180003ebc`
- name: `?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180006800`

## callees

- `0x180003d68`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003e59`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003e59`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180003e70`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180003e70`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180003db9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180003db9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003dc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003dc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e23`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180003ea4`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180003ea4`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180003e0e`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180003e0e`

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
0x180003d68  mov     [rsp+arg_0], rbx
0x180003d6d  mov     [rsp+arg_8], rsi
0x180003d72  push    rdi
0x180003d73  sub     rsp, 30h
0x180003d77  mov     rax, [rdx]
0x180003d7a  lea     rsi, [rcx+30h]
0x180003d7e  mov     r9, rdx
0x180003d81  mov     rdi, rcx
0x180003d84  mov     r8, rsi
0x180003d87  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x180003d8e  mov     rcx, r9
0x180003d91  mov     rax, [rax]
0x180003d94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d99  mov     ebx, eax
0x180003d9b  test    eax, eax
0x180003d9d  js      loc_180003E47
0x180003da3  cmp     dword ptr [rdi+10h], 0
0x180003da7  jz      short loc_180003DE0
0x180003da9  lea     r8, [rdi+18h]; phModule
0x180003dad  mov     ecx, 4; dwFlags
0x180003db2  lea     rdx, cs:180000000h; lpModuleName
0x180003db9  call    cs:__imp_GetModuleHandleExW
0x180003dbf  test    eax, eax
0x180003dc1  jz      short loc_180003DC7
0x180003dc3  xor     ebx, ebx
0x180003dc5  jmp     short loc_180003DE0
0x180003dc7  call    cs:__imp_GetLastError
0x180003dcd  mov     ebx, eax
0x180003dcf  test    eax, eax
0x180003dd1  jle     short loc_180003DDC
0x180003dd3  movzx   ebx, ax
0x180003dd6  or      ebx, 80070000h
0x180003ddc  test    ebx, ebx
0x180003dde  js      short loc_180003E4B
0x180003de0  mov     rax, [rdi]
0x180003de3  mov     rcx, rdi
0x180003de6  mov     rax, [rax+8]
0x180003dea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003def  mov     r9, rdi; lpParameter
0x180003df2  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x180003dfb  lea     r8, ?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z; lpStartAddress
0x180003e02  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x180003e0a  xor     edx, edx; dwStackSize
0x180003e0c  xor     ecx, ecx; lpThreadAttributes
0x180003e0e  call    cs:__imp_CreateThread
0x180003e14  mov     [rdi+28h], rax
0x180003e18  inc     rax
0x180003e1b  test    rax, 0FFFFFFFFFFFFFFFEh
0x180003e21  jnz     short loc_180003E47
0x180003e23  call    cs:__imp_GetLastError
0x180003e29  mov     ebx, eax
0x180003e2b  test    eax, eax
0x180003e2d  jle     short loc_180003E38
0x180003e2f  movzx   ebx, ax
0x180003e32  or      ebx, 80070000h
0x180003e38  mov     rax, [rdi]
0x180003e3b  mov     rcx, rdi
0x180003e3e  mov     rax, [rax+10h]
0x180003e42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e47  test    ebx, ebx
0x180003e49  jns     short loc_180003E9B
0x180003e4b  mov     rcx, [rdi+28h]; hObject
0x180003e4f  lea     rax, [rcx-1]
0x180003e53  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180003e57  ja      short loc_180003E67
0x180003e59  call    cs:__imp_CloseHandle
0x180003e5f  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x180003e67  mov     rcx, [rdi+18h]; hLibModule
0x180003e6b  test    rcx, rcx
0x180003e6e  jz      short loc_180003E7E
0x180003e70  call    cs:__imp_FreeLibrary
0x180003e76  mov     qword ptr [rdi+18h], 0
0x180003e7e  mov     rcx, [rsi]
0x180003e81  test    rcx, rcx
0x180003e84  jz      short loc_180003EAA
0x180003e86  mov     rax, [rcx]
0x180003e89  mov     rax, [rax+10h]
0x180003e8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e92  mov     qword ptr [rsi], 0
0x180003e99  jmp     short loc_180003EAA
0x180003e9b  lock or [rsp+38h+var_38], 0
0x180003ea0  mov     rcx, [rdi+28h]; hThread
0x180003ea4  call    cs:__imp_ResumeThread
0x180003eaa  mov     rsi, [rsp+38h+arg_8]
0x180003eaf  mov     eax, ebx
0x180003eb1  mov     rbx, [rsp+38h+arg_0]
0x180003eb6  add     rsp, 30h
0x180003eba  pop     rdi
0x180003ebb  retn
```
