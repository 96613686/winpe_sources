# CWinTaskHandler::CreateWorkerThread(IUnknown *)

- ea: `0x18000e9a0`
- end: `0x18000eb5b`
- name: `?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z`
- size: `443`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x18000ff70`

## callees

- `0x18000e9a0`
- `0x180012f10`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000eb0f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000eb0f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000ea58`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000ea58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eac2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eac2`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18000eb43`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18000eb43`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000eaad`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000eaad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000eaf8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000eaf8`

## string_xrefs

- `0x18000e9fe`: `CWinTaskHandler::CreateWorkerThread`
- `0x18000ea16`: `onecore\internal\admin\inc\WinTask.h`

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
  signed __int32 v11[8]; // [rsp+0h] [rbp-58h] BYREF

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
          -1,
          L"Assert (%s): %s",
          0,
          0,
          L"((HANDLE)(LONG_PTR)-1) == m_hModule",
          L"Failed");
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
0x18000e9a0  mov     [rsp+arg_0], rbx
0x18000e9a5  mov     [rsp+arg_8], rsi
0x18000e9aa  push    rdi
0x18000e9ab  sub     rsp, 50h
0x18000e9af  mov     rax, [rdx]
0x18000e9b2  lea     rsi, [rcx+30h]
0x18000e9b6  mov     r9, rdx
0x18000e9b9  mov     rdi, rcx
0x18000e9bc  mov     r8, rsi
0x18000e9bf  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x18000e9c6  mov     rcx, r9
0x18000e9c9  mov     rax, [rax]
0x18000e9cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9d1  mov     ebx, eax
0x18000e9d3  test    eax, eax
0x18000e9d5  js      loc_18000EAE6
0x18000e9db  cmp     dword ptr [rdi+10h], 0
0x18000e9df  jz      loc_18000EA7F
0x18000e9e5  cmp     qword ptr [rdi+18h], 0FFFFFFFFFFFFFFFFh
0x18000e9ea  jz      short loc_18000EA48
0x18000e9ec  lea     rax, aFailed; "Failed"
0x18000e9f3  mov     r8d, 241h; unsigned int
0x18000e9f9  mov     [rsp+58h+var_10], rax
0x18000e9fe  lea     r9, aCwintaskhandle_3; "CWinTaskHandler::CreateWorkerThread"
0x18000ea05  lea     rax, aHandleLongPtr1; "((HANDLE)(LONG_PTR)-1) == m_hModule"
0x18000ea0c  mov     ecx, 1; unsigned int
0x18000ea11  mov     [rsp+58h+var_18], rax
0x18000ea16  lea     rdx, aOnecoreInterna_2; "onecore\\internal\\admin\\inc\\WinTask."...
0x18000ea1d  mov     [rsp+58h+var_20], 0; unsigned __int16 *
0x18000ea26  lea     rax, aAssertSS; "Assert (%s): %s"
0x18000ea2d  mov     [rsp+58h+var_28], 0; char *
0x18000ea36  mov     [rsp+58h+lpThreadId], rax; unsigned __int16 *
0x18000ea3b  mov     [rsp+58h+dwCreationFlags], 0FFFFFFFFh; int
0x18000ea43  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x18000ea48  lea     r8, [rdi+18h]; phModule
0x18000ea4c  mov     ecx, 4; dwFlags
0x18000ea51  lea     rdx, __ImageBase; lpModuleName
0x18000ea58  call    cs:__imp_GetModuleHandleExW
0x18000ea5e  test    eax, eax
0x18000ea60  jz      short loc_18000EA66
0x18000ea62  xor     ebx, ebx
0x18000ea64  jmp     short loc_18000EA7F
0x18000ea66  call    cs:__imp_GetLastError
0x18000ea6c  mov     ebx, eax
0x18000ea6e  test    eax, eax
0x18000ea70  jle     short loc_18000EA7B
0x18000ea72  movzx   ebx, ax
0x18000ea75  or      ebx, 80070000h
0x18000ea7b  test    ebx, ebx
0x18000ea7d  js      short loc_18000EAEA
0x18000ea7f  mov     rax, [rdi]
0x18000ea82  mov     rcx, rdi
0x18000ea85  mov     rax, [rax+8]
0x18000ea89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea8e  mov     r9, rdi; lpParameter
0x18000ea91  mov     [rsp+58h+lpThreadId], 0; lpThreadId
0x18000ea9a  lea     r8, ?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z; lpStartAddress
0x18000eaa1  mov     [rsp+58h+dwCreationFlags], 4; dwCreationFlags
0x18000eaa9  xor     edx, edx; dwStackSize
0x18000eaab  xor     ecx, ecx; lpThreadAttributes
0x18000eaad  call    cs:__imp_CreateThread
0x18000eab3  mov     [rdi+28h], rax
0x18000eab7  inc     rax
0x18000eaba  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000eac0  jnz     short loc_18000EAE6
0x18000eac2  call    cs:__imp_GetLastError
0x18000eac8  mov     ebx, eax
0x18000eaca  test    eax, eax
0x18000eacc  jle     short loc_18000EAD7
0x18000eace  movzx   ebx, ax
0x18000ead1  or      ebx, 80070000h
0x18000ead7  mov     rax, [rdi]
0x18000eada  mov     rcx, rdi
0x18000eadd  mov     rax, [rax+10h]
0x18000eae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eae6  test    ebx, ebx
0x18000eae8  jns     short loc_18000EB3A
0x18000eaea  mov     rcx, [rdi+28h]; hObject
0x18000eaee  lea     rax, [rcx-1]
0x18000eaf2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000eaf6  ja      short loc_18000EB06
0x18000eaf8  call    cs:__imp_CloseHandle
0x18000eafe  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x18000eb06  mov     rcx, [rdi+18h]; hLibModule
0x18000eb0a  test    rcx, rcx
0x18000eb0d  jz      short loc_18000EB1D
0x18000eb0f  call    cs:__imp_FreeLibrary
0x18000eb15  mov     qword ptr [rdi+18h], 0
0x18000eb1d  mov     rcx, [rsi]
0x18000eb20  test    rcx, rcx
0x18000eb23  jz      short loc_18000EB49
0x18000eb25  mov     rax, [rcx]
0x18000eb28  mov     rax, [rax+10h]
0x18000eb2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb31  mov     qword ptr [rsi], 0
0x18000eb38  jmp     short loc_18000EB49
0x18000eb3a  lock or [rsp+58h+var_58], 0
0x18000eb3f  mov     rcx, [rdi+28h]; hThread
0x18000eb43  call    cs:__imp_ResumeThread
0x18000eb49  mov     rsi, [rsp+58h+arg_8]
0x18000eb4e  mov     eax, ebx
0x18000eb50  mov     rbx, [rsp+58h+arg_0]
0x18000eb55  add     rsp, 50h
0x18000eb59  pop     rdi
0x18000eb5a  retn
```
