# CWinTaskHandler::CreateWorkerThread(IUnknown *)

- ea: `0x180004444`
- end: `0x180004598`
- name: `?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x1800092e0`

## callees

- `0x180004444`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000454c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000454c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180004495`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180004495`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800044a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800044ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800044a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800044ff`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800044ea`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800044ea`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180004580`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180004580`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004535`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004535`

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
    Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)CWinTaskHandler::WorkerThreadProc, this, 4u, 0);
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
0x180004444  mov     [rsp+arg_0], rbx
0x180004449  mov     [rsp+arg_8], rsi
0x18000444e  push    rdi
0x18000444f  sub     rsp, 30h
0x180004453  mov     rax, [rdx]
0x180004456  lea     rsi, [rcx+30h]
0x18000445a  mov     r9, rdx
0x18000445d  mov     rdi, rcx
0x180004460  mov     r8, rsi
0x180004463  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x18000446a  mov     rcx, r9
0x18000446d  mov     rax, [rax]
0x180004470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004475  mov     ebx, eax
0x180004477  test    eax, eax
0x180004479  js      loc_180004523
0x18000447f  cmp     dword ptr [rdi+10h], 0
0x180004483  jz      short loc_1800044BC
0x180004485  lea     r8, [rdi+18h]; phModule
0x180004489  mov     ecx, 4; dwFlags
0x18000448e  lea     rdx, cs:180000000h; lpModuleName
0x180004495  call    cs:__imp_GetModuleHandleExW
0x18000449b  test    eax, eax
0x18000449d  jz      short loc_1800044A3
0x18000449f  xor     ebx, ebx
0x1800044a1  jmp     short loc_1800044BC
0x1800044a3  call    cs:__imp_GetLastError
0x1800044a9  mov     ebx, eax
0x1800044ab  test    eax, eax
0x1800044ad  jle     short loc_1800044B8
0x1800044af  movzx   ebx, ax
0x1800044b2  or      ebx, 80070000h
0x1800044b8  test    ebx, ebx
0x1800044ba  js      short loc_180004527
0x1800044bc  mov     rax, [rdi]
0x1800044bf  mov     rcx, rdi
0x1800044c2  mov     rax, [rax+8]
0x1800044c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044cb  mov     r9, rdi; lpParameter
0x1800044ce  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x1800044d7  lea     r8, ?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z; lpStartAddress
0x1800044de  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x1800044e6  xor     edx, edx; dwStackSize
0x1800044e8  xor     ecx, ecx; lpThreadAttributes
0x1800044ea  call    cs:__imp_CreateThread
0x1800044f0  mov     [rdi+28h], rax
0x1800044f4  inc     rax
0x1800044f7  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800044fd  jnz     short loc_180004523
0x1800044ff  call    cs:__imp_GetLastError
0x180004505  mov     ebx, eax
0x180004507  test    eax, eax
0x180004509  jle     short loc_180004514
0x18000450b  movzx   ebx, ax
0x18000450e  or      ebx, 80070000h
0x180004514  mov     rax, [rdi]
0x180004517  mov     rcx, rdi
0x18000451a  mov     rax, [rax+10h]
0x18000451e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004523  test    ebx, ebx
0x180004525  jns     short loc_180004577
0x180004527  mov     rcx, [rdi+28h]; hObject
0x18000452b  lea     rax, [rcx-1]
0x18000452f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180004533  ja      short loc_180004543
0x180004535  call    cs:__imp_CloseHandle
0x18000453b  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x180004543  mov     rcx, [rdi+18h]; hLibModule
0x180004547  test    rcx, rcx
0x18000454a  jz      short loc_18000455A
0x18000454c  call    cs:__imp_FreeLibrary
0x180004552  mov     qword ptr [rdi+18h], 0
0x18000455a  mov     rcx, [rsi]
0x18000455d  test    rcx, rcx
0x180004560  jz      short loc_180004586
0x180004562  mov     rax, [rcx]
0x180004565  mov     rax, [rax+10h]
0x180004569  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000456e  mov     qword ptr [rsi], 0
0x180004575  jmp     short loc_180004586
0x180004577  lock or [rsp+38h+var_38], 0
0x18000457c  mov     rcx, [rdi+28h]; hThread
0x180004580  call    cs:__imp_ResumeThread
0x180004586  mov     rsi, [rsp+38h+arg_8]
0x18000458b  mov     eax, ebx
0x18000458d  mov     rbx, [rsp+38h+arg_0]
0x180004592  add     rsp, 30h
0x180004596  pop     rdi
0x180004597  retn
```
