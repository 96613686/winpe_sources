# CWinTaskHandler::CreateWorkerThread(IUnknown *)

- ea: `0x180002664`
- end: `0x180002805`
- name: `?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z`
- size: `417`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x180002d40`

## callees

- `0x180001fd8`
- `0x180002664`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002710`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000276c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002710`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000276c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800027b9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800027b9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180002702`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180002702`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800027a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800027a2`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800027ed`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800027ed`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180002757`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180002757`

## string_xrefs

- `0x1800026c2`: `CWinTaskHandler::CreateWorkerThread`
- `0x1800026da`: `onecore\internal\admin\inc\WinTask.h`

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
  signed __int32 v11[8]; // [rsp+0h] [rbp-48h] BYREF

  v2 = (_QWORD *)((char *)this + 48);
  v4 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, char *))a2->lpVtbl->QueryInterface)(
         a2,
         &GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a,
         (char *)this + 48);
  if ( v4 >= 0 )
  {
    if ( *((_DWORD *)this + 4) )
    {
      if ( *((_QWORD *)this + 3) != -1 )
        LogMessage(
          1u,
          "onecore\\internal\\admin\\inc\\WinTask.h",
          0x241u,
          "CWinTaskHandler::CreateWorkerThread",
          L"Assert (%s): %s",
          L"((HANDLE)(LONG_PTR)-1) == m_hModule",
          L"Failed");
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
          goto LABEL_15;
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
LABEL_15:
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
0x180002664  mov     [rsp+arg_0], rbx
0x180002669  mov     [rsp+arg_8], rsi
0x18000266e  push    rdi
0x18000266f  sub     rsp, 40h
0x180002673  mov     rax, [rdx]
0x180002676  lea     rsi, [rcx+30h]
0x18000267a  mov     r9, rdx
0x18000267d  mov     rdi, rcx
0x180002680  mov     r8, rsi
0x180002683  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x18000268a  mov     rcx, r9
0x18000268d  mov     rax, [rax]
0x180002690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002695  mov     ebx, eax
0x180002697  test    eax, eax
0x180002699  js      loc_180002790
0x18000269f  cmp     dword ptr [rdi+10h], 0
0x1800026a3  jz      loc_180002729
0x1800026a9  cmp     qword ptr [rdi+18h], 0FFFFFFFFFFFFFFFFh
0x1800026ae  jz      short loc_1800026F2
0x1800026b0  lea     rax, aFailed; "Failed"
0x1800026b7  mov     r8d, 241h; unsigned int
0x1800026bd  mov     [rsp+48h+var_18], rax
0x1800026c2  lea     r9, aCwintaskhandle_3; "CWinTaskHandler::CreateWorkerThread"
0x1800026c9  lea     rax, aHandleLongPtr1; "((HANDLE)(LONG_PTR)-1) == m_hModule"
0x1800026d0  mov     ecx, 1; unsigned int
0x1800026d5  mov     [rsp+48h+lpThreadId], rax
0x1800026da  lea     rdx, aOnecoreInterna; "onecore\\internal\\admin\\inc\\WinTask."...
0x1800026e1  lea     rax, aAssertSS; "Assert (%s): %s"
0x1800026e8  mov     qword ptr [rsp+48h+dwCreationFlags], rax; unsigned __int16 *
0x1800026ed  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x1800026f2  lea     r8, [rdi+18h]; phModule
0x1800026f6  mov     ecx, 4; dwFlags
0x1800026fb  lea     rdx, cs:180000000h; lpModuleName
0x180002702  call    cs:__imp_GetModuleHandleExW
0x180002708  test    eax, eax
0x18000270a  jz      short loc_180002710
0x18000270c  xor     ebx, ebx
0x18000270e  jmp     short loc_180002729
0x180002710  call    cs:__imp_GetLastError
0x180002716  mov     ebx, eax
0x180002718  test    eax, eax
0x18000271a  jle     short loc_180002725
0x18000271c  movzx   ebx, ax
0x18000271f  or      ebx, 80070000h
0x180002725  test    ebx, ebx
0x180002727  js      short loc_180002794
0x180002729  mov     rax, [rdi]
0x18000272c  mov     rcx, rdi
0x18000272f  mov     rax, [rax+8]
0x180002733  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002738  mov     r9, rdi; lpParameter
0x18000273b  mov     [rsp+48h+lpThreadId], 0; lpThreadId
0x180002744  lea     r8, ?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z; lpStartAddress
0x18000274b  mov     [rsp+48h+dwCreationFlags], 4; dwCreationFlags
0x180002753  xor     edx, edx; dwStackSize
0x180002755  xor     ecx, ecx; lpThreadAttributes
0x180002757  call    cs:__imp_CreateThread
0x18000275d  mov     [rdi+28h], rax
0x180002761  inc     rax
0x180002764  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000276a  jnz     short loc_180002790
0x18000276c  call    cs:__imp_GetLastError
0x180002772  mov     ebx, eax
0x180002774  test    eax, eax
0x180002776  jle     short loc_180002781
0x180002778  movzx   ebx, ax
0x18000277b  or      ebx, 80070000h
0x180002781  mov     rax, [rdi]
0x180002784  mov     rcx, rdi
0x180002787  mov     rax, [rax+10h]
0x18000278b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002790  test    ebx, ebx
0x180002792  jns     short loc_1800027E4
0x180002794  mov     rcx, [rdi+28h]; hObject
0x180002798  lea     rax, [rcx-1]
0x18000279c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800027a0  ja      short loc_1800027B0
0x1800027a2  call    cs:__imp_CloseHandle
0x1800027a8  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x1800027b0  mov     rcx, [rdi+18h]; hLibModule
0x1800027b4  test    rcx, rcx
0x1800027b7  jz      short loc_1800027C7
0x1800027b9  call    cs:__imp_FreeLibrary
0x1800027bf  mov     qword ptr [rdi+18h], 0
0x1800027c7  mov     rcx, [rsi]
0x1800027ca  test    rcx, rcx
0x1800027cd  jz      short loc_1800027F3
0x1800027cf  mov     rax, [rcx]
0x1800027d2  mov     rax, [rax+10h]
0x1800027d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027db  mov     qword ptr [rsi], 0
0x1800027e2  jmp     short loc_1800027F3
0x1800027e4  lock or [rsp+48h+var_48], 0
0x1800027e9  mov     rcx, [rdi+28h]; hThread
0x1800027ed  call    cs:__imp_ResumeThread
0x1800027f3  mov     rsi, [rsp+48h+arg_8]
0x1800027f8  mov     eax, ebx
0x1800027fa  mov     rbx, [rsp+48h+arg_0]
0x1800027ff  add     rsp, 40h
0x180002803  pop     rdi
0x180002804  retn
```
