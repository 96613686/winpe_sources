# CWinTaskHandler::CreateWorkerThread(IUnknown *)

- ea: `0x180035254`
- end: `0x1800353a8`
- name: `?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x1800354a0`

## callees

- `0x180035254`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800352a5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800352a5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003535c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003535c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800352b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003530f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800352b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003530f`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800352fa`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800352fa`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180035390`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180035390`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035345`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035345`

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
0x180035254  mov     [rsp+arg_0], rbx
0x180035259  mov     [rsp+arg_8], rsi
0x18003525e  push    rdi
0x18003525f  sub     rsp, 30h
0x180035263  mov     rax, [rdx]
0x180035266  lea     rsi, [rcx+30h]
0x18003526a  mov     r9, rdx
0x18003526d  mov     rdi, rcx
0x180035270  mov     r8, rsi
0x180035273  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x18003527a  mov     rcx, r9
0x18003527d  mov     rax, [rax]
0x180035280  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035285  mov     ebx, eax
0x180035287  test    eax, eax
0x180035289  js      loc_180035333
0x18003528f  cmp     dword ptr [rdi+10h], 0
0x180035293  jz      short loc_1800352CC
0x180035295  lea     r8, [rdi+18h]; phModule
0x180035299  mov     ecx, 4; dwFlags
0x18003529e  lea     rdx, __ImageBase; lpModuleName
0x1800352a5  call    cs:__imp_GetModuleHandleExW
0x1800352ab  test    eax, eax
0x1800352ad  jz      short loc_1800352B3
0x1800352af  xor     ebx, ebx
0x1800352b1  jmp     short loc_1800352CC
0x1800352b3  call    cs:__imp_GetLastError
0x1800352b9  mov     ebx, eax
0x1800352bb  test    eax, eax
0x1800352bd  jle     short loc_1800352C8
0x1800352bf  movzx   ebx, ax
0x1800352c2  or      ebx, 80070000h
0x1800352c8  test    ebx, ebx
0x1800352ca  js      short loc_180035337
0x1800352cc  mov     rax, [rdi]
0x1800352cf  mov     rcx, rdi
0x1800352d2  mov     rax, [rax+8]
0x1800352d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800352db  mov     r9, rdi; lpParameter
0x1800352de  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x1800352e7  lea     r8, ?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z; lpStartAddress
0x1800352ee  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x1800352f6  xor     edx, edx; dwStackSize
0x1800352f8  xor     ecx, ecx; lpThreadAttributes
0x1800352fa  call    cs:__imp_CreateThread
0x180035300  mov     [rdi+28h], rax
0x180035304  inc     rax
0x180035307  test    rax, 0FFFFFFFFFFFFFFFEh
0x18003530d  jnz     short loc_180035333
0x18003530f  call    cs:__imp_GetLastError
0x180035315  mov     ebx, eax
0x180035317  test    eax, eax
0x180035319  jle     short loc_180035324
0x18003531b  movzx   ebx, ax
0x18003531e  or      ebx, 80070000h
0x180035324  mov     rax, [rdi]
0x180035327  mov     rcx, rdi
0x18003532a  mov     rax, [rax+10h]
0x18003532e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035333  test    ebx, ebx
0x180035335  jns     short loc_180035387
0x180035337  mov     rcx, [rdi+28h]; hObject
0x18003533b  lea     rax, [rcx-1]
0x18003533f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180035343  ja      short loc_180035353
0x180035345  call    cs:__imp_CloseHandle
0x18003534b  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x180035353  mov     rcx, [rdi+18h]; hLibModule
0x180035357  test    rcx, rcx
0x18003535a  jz      short loc_18003536A
0x18003535c  call    cs:__imp_FreeLibrary
0x180035362  mov     qword ptr [rdi+18h], 0
0x18003536a  mov     rcx, [rsi]
0x18003536d  test    rcx, rcx
0x180035370  jz      short loc_180035396
0x180035372  mov     rax, [rcx]
0x180035375  mov     rax, [rax+10h]
0x180035379  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003537e  mov     qword ptr [rsi], 0
0x180035385  jmp     short loc_180035396
0x180035387  lock or [rsp+38h+var_38], 0
0x18003538c  mov     rcx, [rdi+28h]; hThread
0x180035390  call    cs:__imp_ResumeThread
0x180035396  mov     rsi, [rsp+38h+arg_8]
0x18003539b  mov     eax, ebx
0x18003539d  mov     rbx, [rsp+38h+arg_0]
0x1800353a2  add     rsp, 30h
0x1800353a6  pop     rdi
0x1800353a7  retn
```
