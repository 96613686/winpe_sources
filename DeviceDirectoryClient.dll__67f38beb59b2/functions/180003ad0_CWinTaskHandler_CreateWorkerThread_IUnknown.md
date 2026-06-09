# CWinTaskHandler::CreateWorkerThread(IUnknown *)

- ea: `0x180003ad0`
- end: `0x180003c24`
- name: `?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180004550`

## callees

- `0x180003ad0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180003b21`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180003b21`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180003bd8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180003bd8`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180003c0c`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180003c0c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180003b76`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180003b76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003bc1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003bc1`

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
0x180003ad0  mov     [rsp+arg_0], rbx
0x180003ad5  mov     [rsp+arg_8], rsi
0x180003ada  push    rdi
0x180003adb  sub     rsp, 30h
0x180003adf  mov     rax, [rdx]
0x180003ae2  lea     rsi, [rcx+30h]
0x180003ae6  mov     r9, rdx
0x180003ae9  mov     rdi, rcx
0x180003aec  mov     r8, rsi
0x180003aef  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x180003af6  mov     rcx, r9
0x180003af9  mov     rax, [rax]
0x180003afc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b01  mov     ebx, eax
0x180003b03  test    eax, eax
0x180003b05  js      loc_180003BAF
0x180003b0b  cmp     dword ptr [rdi+10h], 0
0x180003b0f  jz      short loc_180003B48
0x180003b11  lea     r8, [rdi+18h]; phModule
0x180003b15  mov     ecx, 4; dwFlags
0x180003b1a  lea     rdx, __ImageBase; lpModuleName
0x180003b21  call    cs:__imp_GetModuleHandleExW
0x180003b27  test    eax, eax
0x180003b29  jz      short loc_180003B2F
0x180003b2b  xor     ebx, ebx
0x180003b2d  jmp     short loc_180003B48
0x180003b2f  call    cs:__imp_GetLastError
0x180003b35  mov     ebx, eax
0x180003b37  test    eax, eax
0x180003b39  jle     short loc_180003B44
0x180003b3b  movzx   ebx, ax
0x180003b3e  or      ebx, 80070000h
0x180003b44  test    ebx, ebx
0x180003b46  js      short loc_180003BB3
0x180003b48  mov     rax, [rdi]
0x180003b4b  mov     rcx, rdi
0x180003b4e  mov     rax, [rax+8]
0x180003b52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b57  mov     r9, rdi; lpParameter
0x180003b5a  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x180003b63  lea     r8, ?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z; lpStartAddress
0x180003b6a  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x180003b72  xor     edx, edx; dwStackSize
0x180003b74  xor     ecx, ecx; lpThreadAttributes
0x180003b76  call    cs:__imp_CreateThread
0x180003b7c  mov     [rdi+28h], rax
0x180003b80  inc     rax
0x180003b83  test    rax, 0FFFFFFFFFFFFFFFEh
0x180003b89  jnz     short loc_180003BAF
0x180003b8b  call    cs:__imp_GetLastError
0x180003b91  mov     ebx, eax
0x180003b93  test    eax, eax
0x180003b95  jle     short loc_180003BA0
0x180003b97  movzx   ebx, ax
0x180003b9a  or      ebx, 80070000h
0x180003ba0  mov     rax, [rdi]
0x180003ba3  mov     rcx, rdi
0x180003ba6  mov     rax, [rax+10h]
0x180003baa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003baf  test    ebx, ebx
0x180003bb1  jns     short loc_180003C03
0x180003bb3  mov     rcx, [rdi+28h]; hObject
0x180003bb7  lea     rax, [rcx-1]
0x180003bbb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180003bbf  ja      short loc_180003BCF
0x180003bc1  call    cs:__imp_CloseHandle
0x180003bc7  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x180003bcf  mov     rcx, [rdi+18h]; hLibModule
0x180003bd3  test    rcx, rcx
0x180003bd6  jz      short loc_180003BE6
0x180003bd8  call    cs:__imp_FreeLibrary
0x180003bde  mov     qword ptr [rdi+18h], 0
0x180003be6  mov     rcx, [rsi]
0x180003be9  test    rcx, rcx
0x180003bec  jz      short loc_180003C12
0x180003bee  mov     rax, [rcx]
0x180003bf1  mov     rax, [rax+10h]
0x180003bf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bfa  mov     qword ptr [rsi], 0
0x180003c01  jmp     short loc_180003C12
0x180003c03  lock or [rsp+38h+var_38], 0
0x180003c08  mov     rcx, [rdi+28h]; hThread
0x180003c0c  call    cs:__imp_ResumeThread
0x180003c12  mov     rsi, [rsp+38h+arg_8]
0x180003c17  mov     eax, ebx
0x180003c19  mov     rbx, [rsp+38h+arg_0]
0x180003c1e  add     rsp, 30h
0x180003c22  pop     rdi
0x180003c23  retn
```
