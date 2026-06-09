# CWinTaskHandler::CreateWorkerThread(IUnknown *)

- ea: `0x1800023c4`
- end: `0x180002518`
- name: `?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180002ab0`

## callees

- `0x1800023c4`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800024cc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800024cc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180002415`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180002415`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002423`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000247f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002423`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000247f`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000246a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000246a`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180002500`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180002500`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800024b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800024b5`

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
0x1800023c4  mov     [rsp+arg_0], rbx
0x1800023c9  mov     [rsp+arg_8], rsi
0x1800023ce  push    rdi
0x1800023cf  sub     rsp, 30h
0x1800023d3  mov     rax, [rdx]
0x1800023d6  lea     rsi, [rcx+30h]
0x1800023da  mov     r9, rdx
0x1800023dd  mov     rdi, rcx
0x1800023e0  mov     r8, rsi
0x1800023e3  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x1800023ea  mov     rcx, r9
0x1800023ed  mov     rax, [rax]
0x1800023f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023f5  mov     ebx, eax
0x1800023f7  test    eax, eax
0x1800023f9  js      loc_1800024A3
0x1800023ff  cmp     dword ptr [rdi+10h], 0
0x180002403  jz      short loc_18000243C
0x180002405  lea     r8, [rdi+18h]; phModule
0x180002409  mov     ecx, 4; dwFlags
0x18000240e  lea     rdx, cs:180000000h; lpModuleName
0x180002415  call    cs:__imp_GetModuleHandleExW
0x18000241b  test    eax, eax
0x18000241d  jz      short loc_180002423
0x18000241f  xor     ebx, ebx
0x180002421  jmp     short loc_18000243C
0x180002423  call    cs:__imp_GetLastError
0x180002429  mov     ebx, eax
0x18000242b  test    eax, eax
0x18000242d  jle     short loc_180002438
0x18000242f  movzx   ebx, ax
0x180002432  or      ebx, 80070000h
0x180002438  test    ebx, ebx
0x18000243a  js      short loc_1800024A7
0x18000243c  mov     rax, [rdi]
0x18000243f  mov     rcx, rdi
0x180002442  mov     rax, [rax+8]
0x180002446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000244b  mov     r9, rdi; lpParameter
0x18000244e  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x180002457  lea     r8, ?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z; lpStartAddress
0x18000245e  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x180002466  xor     edx, edx; dwStackSize
0x180002468  xor     ecx, ecx; lpThreadAttributes
0x18000246a  call    cs:__imp_CreateThread
0x180002470  mov     [rdi+28h], rax
0x180002474  inc     rax
0x180002477  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000247d  jnz     short loc_1800024A3
0x18000247f  call    cs:__imp_GetLastError
0x180002485  mov     ebx, eax
0x180002487  test    eax, eax
0x180002489  jle     short loc_180002494
0x18000248b  movzx   ebx, ax
0x18000248e  or      ebx, 80070000h
0x180002494  mov     rax, [rdi]
0x180002497  mov     rcx, rdi
0x18000249a  mov     rax, [rax+10h]
0x18000249e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024a3  test    ebx, ebx
0x1800024a5  jns     short loc_1800024F7
0x1800024a7  mov     rcx, [rdi+28h]; hObject
0x1800024ab  lea     rax, [rcx-1]
0x1800024af  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800024b3  ja      short loc_1800024C3
0x1800024b5  call    cs:__imp_CloseHandle
0x1800024bb  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x1800024c3  mov     rcx, [rdi+18h]; hLibModule
0x1800024c7  test    rcx, rcx
0x1800024ca  jz      short loc_1800024DA
0x1800024cc  call    cs:__imp_FreeLibrary
0x1800024d2  mov     qword ptr [rdi+18h], 0
0x1800024da  mov     rcx, [rsi]
0x1800024dd  test    rcx, rcx
0x1800024e0  jz      short loc_180002506
0x1800024e2  mov     rax, [rcx]
0x1800024e5  mov     rax, [rax+10h]
0x1800024e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024ee  mov     qword ptr [rsi], 0
0x1800024f5  jmp     short loc_180002506
0x1800024f7  lock or [rsp+38h+var_38], 0
0x1800024fc  mov     rcx, [rdi+28h]; hThread
0x180002500  call    cs:__imp_ResumeThread
0x180002506  mov     rsi, [rsp+38h+arg_8]
0x18000250b  mov     eax, ebx
0x18000250d  mov     rbx, [rsp+38h+arg_0]
0x180002512  add     rsp, 30h
0x180002516  pop     rdi
0x180002517  retn
```
