# CWinTaskHandler::CreateWorkerThread(IUnknown *)

- ea: `0x1800049c4`
- end: `0x180004b18`
- name: `?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180009530`

## callees

- `0x1800049c4`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180004acc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180004acc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180004a15`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180004a15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a7f`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180004b00`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180004b00`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180004a6a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180004a6a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004ab5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004ab5`

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
0x1800049c4  mov     [rsp+arg_0], rbx
0x1800049c9  mov     [rsp+arg_8], rsi
0x1800049ce  push    rdi
0x1800049cf  sub     rsp, 30h
0x1800049d3  mov     rax, [rdx]
0x1800049d6  lea     rsi, [rcx+30h]
0x1800049da  mov     r9, rdx
0x1800049dd  mov     rdi, rcx
0x1800049e0  mov     r8, rsi
0x1800049e3  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x1800049ea  mov     rcx, r9
0x1800049ed  mov     rax, [rax]
0x1800049f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049f5  mov     ebx, eax
0x1800049f7  test    eax, eax
0x1800049f9  js      loc_180004AA3
0x1800049ff  cmp     dword ptr [rdi+10h], 0
0x180004a03  jz      short loc_180004A3C
0x180004a05  lea     r8, [rdi+18h]; phModule
0x180004a09  mov     ecx, 4; dwFlags
0x180004a0e  lea     rdx, cs:180000000h; lpModuleName
0x180004a15  call    cs:__imp_GetModuleHandleExW
0x180004a1b  test    eax, eax
0x180004a1d  jz      short loc_180004A23
0x180004a1f  xor     ebx, ebx
0x180004a21  jmp     short loc_180004A3C
0x180004a23  call    cs:__imp_GetLastError
0x180004a29  mov     ebx, eax
0x180004a2b  test    eax, eax
0x180004a2d  jle     short loc_180004A38
0x180004a2f  movzx   ebx, ax
0x180004a32  or      ebx, 80070000h
0x180004a38  test    ebx, ebx
0x180004a3a  js      short loc_180004AA7
0x180004a3c  mov     rax, [rdi]
0x180004a3f  mov     rcx, rdi
0x180004a42  mov     rax, [rax+8]
0x180004a46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a4b  mov     r9, rdi; lpParameter
0x180004a4e  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x180004a57  lea     r8, ?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z; lpStartAddress
0x180004a5e  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x180004a66  xor     edx, edx; dwStackSize
0x180004a68  xor     ecx, ecx; lpThreadAttributes
0x180004a6a  call    cs:__imp_CreateThread
0x180004a70  mov     [rdi+28h], rax
0x180004a74  inc     rax
0x180004a77  test    rax, 0FFFFFFFFFFFFFFFEh
0x180004a7d  jnz     short loc_180004AA3
0x180004a7f  call    cs:__imp_GetLastError
0x180004a85  mov     ebx, eax
0x180004a87  test    eax, eax
0x180004a89  jle     short loc_180004A94
0x180004a8b  movzx   ebx, ax
0x180004a8e  or      ebx, 80070000h
0x180004a94  mov     rax, [rdi]
0x180004a97  mov     rcx, rdi
0x180004a9a  mov     rax, [rax+10h]
0x180004a9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004aa3  test    ebx, ebx
0x180004aa5  jns     short loc_180004AF7
0x180004aa7  mov     rcx, [rdi+28h]; hObject
0x180004aab  lea     rax, [rcx-1]
0x180004aaf  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180004ab3  ja      short loc_180004AC3
0x180004ab5  call    cs:__imp_CloseHandle
0x180004abb  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x180004ac3  mov     rcx, [rdi+18h]; hLibModule
0x180004ac7  test    rcx, rcx
0x180004aca  jz      short loc_180004ADA
0x180004acc  call    cs:__imp_FreeLibrary
0x180004ad2  mov     qword ptr [rdi+18h], 0
0x180004ada  mov     rcx, [rsi]
0x180004add  test    rcx, rcx
0x180004ae0  jz      short loc_180004B06
0x180004ae2  mov     rax, [rcx]
0x180004ae5  mov     rax, [rax+10h]
0x180004ae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004aee  mov     qword ptr [rsi], 0
0x180004af5  jmp     short loc_180004B06
0x180004af7  lock or [rsp+38h+var_38], 0
0x180004afc  mov     rcx, [rdi+28h]; hThread
0x180004b00  call    cs:__imp_ResumeThread
0x180004b06  mov     rsi, [rsp+38h+arg_8]
0x180004b0b  mov     eax, ebx
0x180004b0d  mov     rbx, [rsp+38h+arg_0]
0x180004b12  add     rsp, 30h
0x180004b16  pop     rdi
0x180004b17  retn
```
