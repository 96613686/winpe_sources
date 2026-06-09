# CWinTaskHandler::CreateWorkerThread(IUnknown *)

- ea: `0x18000dab4`
- end: `0x18000dc08`
- name: `?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18000dec0`

## callees

- `0x18000dab4`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000dbbc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000dbbc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000db05`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000db05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000db13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000db6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000db13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000db6f`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000db5a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000db5a`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18000dbf0`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18000dbf0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dba5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dba5`

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
0x18000dab4  mov     [rsp+arg_0], rbx
0x18000dab9  mov     [rsp+arg_8], rsi
0x18000dabe  push    rdi
0x18000dabf  sub     rsp, 30h
0x18000dac3  mov     rax, [rdx]
0x18000dac6  lea     rsi, [rcx+30h]
0x18000daca  mov     r9, rdx
0x18000dacd  mov     rdi, rcx
0x18000dad0  mov     r8, rsi
0x18000dad3  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x18000dada  mov     rcx, r9
0x18000dadd  mov     rax, [rax]
0x18000dae0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dae5  mov     ebx, eax
0x18000dae7  test    eax, eax
0x18000dae9  js      loc_18000DB93
0x18000daef  cmp     dword ptr [rdi+10h], 0
0x18000daf3  jz      short loc_18000DB2C
0x18000daf5  lea     r8, [rdi+18h]; phModule
0x18000daf9  mov     ecx, 4; dwFlags
0x18000dafe  lea     rdx, cs:180000000h; lpModuleName
0x18000db05  call    cs:__imp_GetModuleHandleExW
0x18000db0b  test    eax, eax
0x18000db0d  jz      short loc_18000DB13
0x18000db0f  xor     ebx, ebx
0x18000db11  jmp     short loc_18000DB2C
0x18000db13  call    cs:__imp_GetLastError
0x18000db19  mov     ebx, eax
0x18000db1b  test    eax, eax
0x18000db1d  jle     short loc_18000DB28
0x18000db1f  movzx   ebx, ax
0x18000db22  or      ebx, 80070000h
0x18000db28  test    ebx, ebx
0x18000db2a  js      short loc_18000DB97
0x18000db2c  mov     rax, [rdi]
0x18000db2f  mov     rcx, rdi
0x18000db32  mov     rax, [rax+8]
0x18000db36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db3b  mov     r9, rdi; lpParameter
0x18000db3e  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x18000db47  lea     r8, ?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z; lpStartAddress
0x18000db4e  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x18000db56  xor     edx, edx; dwStackSize
0x18000db58  xor     ecx, ecx; lpThreadAttributes
0x18000db5a  call    cs:__imp_CreateThread
0x18000db60  mov     [rdi+28h], rax
0x18000db64  inc     rax
0x18000db67  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000db6d  jnz     short loc_18000DB93
0x18000db6f  call    cs:__imp_GetLastError
0x18000db75  mov     ebx, eax
0x18000db77  test    eax, eax
0x18000db79  jle     short loc_18000DB84
0x18000db7b  movzx   ebx, ax
0x18000db7e  or      ebx, 80070000h
0x18000db84  mov     rax, [rdi]
0x18000db87  mov     rcx, rdi
0x18000db8a  mov     rax, [rax+10h]
0x18000db8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db93  test    ebx, ebx
0x18000db95  jns     short loc_18000DBE7
0x18000db97  mov     rcx, [rdi+28h]; hObject
0x18000db9b  lea     rax, [rcx-1]
0x18000db9f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000dba3  ja      short loc_18000DBB3
0x18000dba5  call    cs:__imp_CloseHandle
0x18000dbab  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x18000dbb3  mov     rcx, [rdi+18h]; hLibModule
0x18000dbb7  test    rcx, rcx
0x18000dbba  jz      short loc_18000DBCA
0x18000dbbc  call    cs:__imp_FreeLibrary
0x18000dbc2  mov     qword ptr [rdi+18h], 0
0x18000dbca  mov     rcx, [rsi]
0x18000dbcd  test    rcx, rcx
0x18000dbd0  jz      short loc_18000DBF6
0x18000dbd2  mov     rax, [rcx]
0x18000dbd5  mov     rax, [rax+10h]
0x18000dbd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbde  mov     qword ptr [rsi], 0
0x18000dbe5  jmp     short loc_18000DBF6
0x18000dbe7  lock or [rsp+38h+var_38], 0
0x18000dbec  mov     rcx, [rdi+28h]; hThread
0x18000dbf0  call    cs:__imp_ResumeThread
0x18000dbf6  mov     rsi, [rsp+38h+arg_8]
0x18000dbfb  mov     eax, ebx
0x18000dbfd  mov     rbx, [rsp+38h+arg_0]
0x18000dc02  add     rsp, 30h
0x18000dc06  pop     rdi
0x18000dc07  retn
```
