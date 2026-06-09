# CWinTaskHandler::CreateWorkerThread(IUnknown *)

- ea: `0x180005354`
- end: `0x1800054a8`
- name: `?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180009e20`

## callees

- `0x180005354`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180005490`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180005490`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800053fa`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800053fa`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000545c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000545c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800053a5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800053a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000540f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000540f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005445`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005445`

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
0x180005354  mov     [rsp+arg_0], rbx
0x180005359  mov     [rsp+arg_8], rsi
0x18000535e  push    rdi
0x18000535f  sub     rsp, 30h
0x180005363  mov     rax, [rdx]
0x180005366  lea     rsi, [rcx+30h]
0x18000536a  mov     r9, rdx
0x18000536d  mov     rdi, rcx
0x180005370  mov     r8, rsi
0x180005373  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x18000537a  mov     rcx, r9
0x18000537d  mov     rax, [rax]
0x180005380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005385  mov     ebx, eax
0x180005387  test    eax, eax
0x180005389  js      loc_180005433
0x18000538f  cmp     dword ptr [rdi+10h], 0
0x180005393  jz      short loc_1800053CC
0x180005395  lea     r8, [rdi+18h]; phModule
0x180005399  mov     ecx, 4; dwFlags
0x18000539e  lea     rdx, __ImageBase; lpModuleName
0x1800053a5  call    cs:__imp_GetModuleHandleExW
0x1800053ab  test    eax, eax
0x1800053ad  jz      short loc_1800053B3
0x1800053af  xor     ebx, ebx
0x1800053b1  jmp     short loc_1800053CC
0x1800053b3  call    cs:__imp_GetLastError
0x1800053b9  mov     ebx, eax
0x1800053bb  test    eax, eax
0x1800053bd  jle     short loc_1800053C8
0x1800053bf  movzx   ebx, ax
0x1800053c2  or      ebx, 80070000h
0x1800053c8  test    ebx, ebx
0x1800053ca  js      short loc_180005437
0x1800053cc  mov     rax, [rdi]
0x1800053cf  mov     rcx, rdi
0x1800053d2  mov     rax, [rax+8]
0x1800053d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053db  mov     r9, rdi; lpParameter
0x1800053de  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x1800053e7  lea     r8, ?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z; lpStartAddress
0x1800053ee  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x1800053f6  xor     edx, edx; dwStackSize
0x1800053f8  xor     ecx, ecx; lpThreadAttributes
0x1800053fa  call    cs:__imp_CreateThread
0x180005400  mov     [rdi+28h], rax
0x180005404  inc     rax
0x180005407  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000540d  jnz     short loc_180005433
0x18000540f  call    cs:__imp_GetLastError
0x180005415  mov     ebx, eax
0x180005417  test    eax, eax
0x180005419  jle     short loc_180005424
0x18000541b  movzx   ebx, ax
0x18000541e  or      ebx, 80070000h
0x180005424  mov     rax, [rdi]
0x180005427  mov     rcx, rdi
0x18000542a  mov     rax, [rax+10h]
0x18000542e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005433  test    ebx, ebx
0x180005435  jns     short loc_180005487
0x180005437  mov     rcx, [rdi+28h]; hObject
0x18000543b  lea     rax, [rcx-1]
0x18000543f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180005443  ja      short loc_180005453
0x180005445  call    cs:__imp_CloseHandle
0x18000544b  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x180005453  mov     rcx, [rdi+18h]; hLibModule
0x180005457  test    rcx, rcx
0x18000545a  jz      short loc_18000546A
0x18000545c  call    cs:__imp_FreeLibrary
0x180005462  mov     qword ptr [rdi+18h], 0
0x18000546a  mov     rcx, [rsi]
0x18000546d  test    rcx, rcx
0x180005470  jz      short loc_180005496
0x180005472  mov     rax, [rcx]
0x180005475  mov     rax, [rax+10h]
0x180005479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000547e  mov     qword ptr [rsi], 0
0x180005485  jmp     short loc_180005496
0x180005487  lock or [rsp+38h+var_38], 0
0x18000548c  mov     rcx, [rdi+28h]; hThread
0x180005490  call    cs:__imp_ResumeThread
0x180005496  mov     rsi, [rsp+38h+arg_8]
0x18000549b  mov     eax, ebx
0x18000549d  mov     rbx, [rsp+38h+arg_0]
0x1800054a2  add     rsp, 30h
0x1800054a6  pop     rdi
0x1800054a7  retn
```
