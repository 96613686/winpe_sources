# CWinTaskHandler::CreateWorkerThread(IUnknown *)

- ea: `0x180002d18`
- end: `0x180002e6c`
- name: `?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x1800036c0`

## callees

- `0x180002d18`
- `0x180006010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180002d77`
- `KERNEL32!GetLastError` at `0x180002dd3`
- `KERNEL32!GetLastError` at `0x180002d77`
- `KERNEL32!GetLastError` at `0x180002dd3`
- `KERNEL32!CloseHandle` at `0x180002e09`
- `KERNEL32!CloseHandle` at `0x180002e09`
- `KERNEL32!GetModuleHandleExW` at `0x180002d69`
- `KERNEL32!GetModuleHandleExW` at `0x180002d69`
- `KERNEL32!ResumeThread` at `0x180002e54`
- `KERNEL32!ResumeThread` at `0x180002e54`
- `KERNEL32!CreateThread` at `0x180002dbe`
- `KERNEL32!CreateThread` at `0x180002dbe`
- `KERNEL32!FreeLibrary` at `0x180002e20`
- `KERNEL32!FreeLibrary` at `0x180002e20`

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
0x180002d18  mov     [rsp+arg_0], rbx
0x180002d1d  mov     [rsp+arg_8], rsi
0x180002d22  push    rdi
0x180002d23  sub     rsp, 30h
0x180002d27  mov     rax, [rdx]
0x180002d2a  lea     rsi, [rcx+30h]
0x180002d2e  mov     r9, rdx
0x180002d31  mov     rdi, rcx
0x180002d34  mov     r8, rsi
0x180002d37  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x180002d3e  mov     rcx, r9
0x180002d41  mov     rax, [rax]
0x180002d44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d49  mov     ebx, eax
0x180002d4b  test    eax, eax
0x180002d4d  js      loc_180002DF7
0x180002d53  cmp     dword ptr [rdi+10h], 0
0x180002d57  jz      short loc_180002D90
0x180002d59  lea     r8, [rdi+18h]; phModule
0x180002d5d  mov     ecx, 4; dwFlags
0x180002d62  lea     rdx, cs:180000000h; lpModuleName
0x180002d69  call    cs:__imp_GetModuleHandleExW
0x180002d6f  test    eax, eax
0x180002d71  jz      short loc_180002D77
0x180002d73  xor     ebx, ebx
0x180002d75  jmp     short loc_180002D90
0x180002d77  call    cs:__imp_GetLastError
0x180002d7d  mov     ebx, eax
0x180002d7f  test    eax, eax
0x180002d81  jle     short loc_180002D8C
0x180002d83  movzx   ebx, ax
0x180002d86  or      ebx, 80070000h
0x180002d8c  test    ebx, ebx
0x180002d8e  js      short loc_180002DFB
0x180002d90  mov     rax, [rdi]
0x180002d93  mov     rcx, rdi
0x180002d96  mov     rax, [rax+8]
0x180002d9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d9f  mov     r9, rdi; lpParameter
0x180002da2  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x180002dab  lea     r8, ?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z; lpStartAddress
0x180002db2  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x180002dba  xor     edx, edx; dwStackSize
0x180002dbc  xor     ecx, ecx; lpThreadAttributes
0x180002dbe  call    cs:__imp_CreateThread
0x180002dc4  mov     [rdi+28h], rax
0x180002dc8  inc     rax
0x180002dcb  test    rax, 0FFFFFFFFFFFFFFFEh
0x180002dd1  jnz     short loc_180002DF7
0x180002dd3  call    cs:__imp_GetLastError
0x180002dd9  mov     ebx, eax
0x180002ddb  test    eax, eax
0x180002ddd  jle     short loc_180002DE8
0x180002ddf  movzx   ebx, ax
0x180002de2  or      ebx, 80070000h
0x180002de8  mov     rax, [rdi]
0x180002deb  mov     rcx, rdi
0x180002dee  mov     rax, [rax+10h]
0x180002df2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002df7  test    ebx, ebx
0x180002df9  jns     short loc_180002E4B
0x180002dfb  mov     rcx, [rdi+28h]; hObject
0x180002dff  lea     rax, [rcx-1]
0x180002e03  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180002e07  ja      short loc_180002E17
0x180002e09  call    cs:__imp_CloseHandle
0x180002e0f  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x180002e17  mov     rcx, [rdi+18h]; hLibModule
0x180002e1b  test    rcx, rcx
0x180002e1e  jz      short loc_180002E2E
0x180002e20  call    cs:__imp_FreeLibrary
0x180002e26  mov     qword ptr [rdi+18h], 0
0x180002e2e  mov     rcx, [rsi]
0x180002e31  test    rcx, rcx
0x180002e34  jz      short loc_180002E5A
0x180002e36  mov     rax, [rcx]
0x180002e39  mov     rax, [rax+10h]
0x180002e3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e42  mov     qword ptr [rsi], 0
0x180002e49  jmp     short loc_180002E5A
0x180002e4b  lock or [rsp+38h+var_38], 0
0x180002e50  mov     rcx, [rdi+28h]; hThread
0x180002e54  call    cs:__imp_ResumeThread
0x180002e5a  mov     rsi, [rsp+38h+arg_8]
0x180002e5f  mov     eax, ebx
0x180002e61  mov     rbx, [rsp+38h+arg_0]
0x180002e66  add     rsp, 30h
0x180002e6a  pop     rdi
0x180002e6b  retn
```
