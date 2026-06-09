# CWinTaskHandler::CreateWorkerThread(IUnknown *)

- ea: `0x180021678`
- end: `0x1800217cc`
- name: `?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180021ae0`

## callees

- `0x180021678`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800216c9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800216c9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180021780`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180021780`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800216d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021733`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800216d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021733`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800217b4`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800217b4`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002171e`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002171e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021769`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021769`

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
0x180021678  mov     [rsp+arg_0], rbx
0x18002167d  mov     [rsp+arg_8], rsi
0x180021682  push    rdi
0x180021683  sub     rsp, 30h
0x180021687  mov     rax, [rdx]
0x18002168a  lea     rsi, [rcx+30h]
0x18002168e  mov     r9, rdx
0x180021691  mov     rdi, rcx
0x180021694  mov     r8, rsi
0x180021697  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x18002169e  mov     rcx, r9
0x1800216a1  mov     rax, [rax]
0x1800216a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800216a9  mov     ebx, eax
0x1800216ab  test    eax, eax
0x1800216ad  js      loc_180021757
0x1800216b3  cmp     dword ptr [rdi+10h], 0
0x1800216b7  jz      short loc_1800216F0
0x1800216b9  lea     r8, [rdi+18h]; phModule
0x1800216bd  mov     ecx, 4; dwFlags
0x1800216c2  lea     rdx, __ImageBase; lpModuleName
0x1800216c9  call    cs:__imp_GetModuleHandleExW
0x1800216cf  test    eax, eax
0x1800216d1  jz      short loc_1800216D7
0x1800216d3  xor     ebx, ebx
0x1800216d5  jmp     short loc_1800216F0
0x1800216d7  call    cs:__imp_GetLastError
0x1800216dd  mov     ebx, eax
0x1800216df  test    eax, eax
0x1800216e1  jle     short loc_1800216EC
0x1800216e3  movzx   ebx, ax
0x1800216e6  or      ebx, 80070000h
0x1800216ec  test    ebx, ebx
0x1800216ee  js      short loc_18002175B
0x1800216f0  mov     rax, [rdi]
0x1800216f3  mov     rcx, rdi
0x1800216f6  mov     rax, [rax+8]
0x1800216fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800216ff  mov     r9, rdi; lpParameter
0x180021702  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x18002170b  lea     r8, ?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z; lpStartAddress
0x180021712  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x18002171a  xor     edx, edx; dwStackSize
0x18002171c  xor     ecx, ecx; lpThreadAttributes
0x18002171e  call    cs:__imp_CreateThread
0x180021724  mov     [rdi+28h], rax
0x180021728  inc     rax
0x18002172b  test    rax, 0FFFFFFFFFFFFFFFEh
0x180021731  jnz     short loc_180021757
0x180021733  call    cs:__imp_GetLastError
0x180021739  mov     ebx, eax
0x18002173b  test    eax, eax
0x18002173d  jle     short loc_180021748
0x18002173f  movzx   ebx, ax
0x180021742  or      ebx, 80070000h
0x180021748  mov     rax, [rdi]
0x18002174b  mov     rcx, rdi
0x18002174e  mov     rax, [rax+10h]
0x180021752  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021757  test    ebx, ebx
0x180021759  jns     short loc_1800217AB
0x18002175b  mov     rcx, [rdi+28h]; hObject
0x18002175f  lea     rax, [rcx-1]
0x180021763  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180021767  ja      short loc_180021777
0x180021769  call    cs:__imp_CloseHandle
0x18002176f  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x180021777  mov     rcx, [rdi+18h]; hLibModule
0x18002177b  test    rcx, rcx
0x18002177e  jz      short loc_18002178E
0x180021780  call    cs:__imp_FreeLibrary
0x180021786  mov     qword ptr [rdi+18h], 0
0x18002178e  mov     rcx, [rsi]
0x180021791  test    rcx, rcx
0x180021794  jz      short loc_1800217BA
0x180021796  mov     rax, [rcx]
0x180021799  mov     rax, [rax+10h]
0x18002179d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800217a2  mov     qword ptr [rsi], 0
0x1800217a9  jmp     short loc_1800217BA
0x1800217ab  lock or [rsp+38h+var_38], 0
0x1800217b0  mov     rcx, [rdi+28h]; hThread
0x1800217b4  call    cs:__imp_ResumeThread
0x1800217ba  mov     rsi, [rsp+38h+arg_8]
0x1800217bf  mov     eax, ebx
0x1800217c1  mov     rbx, [rsp+38h+arg_0]
0x1800217c6  add     rsp, 30h
0x1800217ca  pop     rdi
0x1800217cb  retn
```
