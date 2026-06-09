# CWinTaskHandler::CreateWorkerThread(IUnknown *)

- ea: `0x180003fe4`
- end: `0x180004138`
- name: `?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x1800066b0`

## callees

- `0x180003fe4`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800040ec`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800040ec`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180004035`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180004035`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004043`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000409f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004043`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000409f`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000408a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000408a`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180004120`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180004120`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800040d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800040d5`

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
0x180003fe4  mov     [rsp+arg_0], rbx
0x180003fe9  mov     [rsp+arg_8], rsi
0x180003fee  push    rdi
0x180003fef  sub     rsp, 30h
0x180003ff3  mov     rax, [rdx]
0x180003ff6  lea     rsi, [rcx+30h]
0x180003ffa  mov     r9, rdx
0x180003ffd  mov     rdi, rcx
0x180004000  mov     r8, rsi
0x180004003  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x18000400a  mov     rcx, r9
0x18000400d  mov     rax, [rax]
0x180004010  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004015  mov     ebx, eax
0x180004017  test    eax, eax
0x180004019  js      loc_1800040C3
0x18000401f  cmp     dword ptr [rdi+10h], 0
0x180004023  jz      short loc_18000405C
0x180004025  lea     r8, [rdi+18h]; phModule
0x180004029  mov     ecx, 4; dwFlags
0x18000402e  lea     rdx, __ImageBase; lpModuleName
0x180004035  call    cs:__imp_GetModuleHandleExW
0x18000403b  test    eax, eax
0x18000403d  jz      short loc_180004043
0x18000403f  xor     ebx, ebx
0x180004041  jmp     short loc_18000405C
0x180004043  call    cs:__imp_GetLastError
0x180004049  mov     ebx, eax
0x18000404b  test    eax, eax
0x18000404d  jle     short loc_180004058
0x18000404f  movzx   ebx, ax
0x180004052  or      ebx, 80070000h
0x180004058  test    ebx, ebx
0x18000405a  js      short loc_1800040C7
0x18000405c  mov     rax, [rdi]
0x18000405f  mov     rcx, rdi
0x180004062  mov     rax, [rax+8]
0x180004066  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000406b  mov     r9, rdi; lpParameter
0x18000406e  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x180004077  lea     r8, ?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z; lpStartAddress
0x18000407e  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x180004086  xor     edx, edx; dwStackSize
0x180004088  xor     ecx, ecx; lpThreadAttributes
0x18000408a  call    cs:__imp_CreateThread
0x180004090  mov     [rdi+28h], rax
0x180004094  inc     rax
0x180004097  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000409d  jnz     short loc_1800040C3
0x18000409f  call    cs:__imp_GetLastError
0x1800040a5  mov     ebx, eax
0x1800040a7  test    eax, eax
0x1800040a9  jle     short loc_1800040B4
0x1800040ab  movzx   ebx, ax
0x1800040ae  or      ebx, 80070000h
0x1800040b4  mov     rax, [rdi]
0x1800040b7  mov     rcx, rdi
0x1800040ba  mov     rax, [rax+10h]
0x1800040be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040c3  test    ebx, ebx
0x1800040c5  jns     short loc_180004117
0x1800040c7  mov     rcx, [rdi+28h]; hObject
0x1800040cb  lea     rax, [rcx-1]
0x1800040cf  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800040d3  ja      short loc_1800040E3
0x1800040d5  call    cs:__imp_CloseHandle
0x1800040db  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x1800040e3  mov     rcx, [rdi+18h]; hLibModule
0x1800040e7  test    rcx, rcx
0x1800040ea  jz      short loc_1800040FA
0x1800040ec  call    cs:__imp_FreeLibrary
0x1800040f2  mov     qword ptr [rdi+18h], 0
0x1800040fa  mov     rcx, [rsi]
0x1800040fd  test    rcx, rcx
0x180004100  jz      short loc_180004126
0x180004102  mov     rax, [rcx]
0x180004105  mov     rax, [rax+10h]
0x180004109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000410e  mov     qword ptr [rsi], 0
0x180004115  jmp     short loc_180004126
0x180004117  lock or [rsp+38h+var_38], 0
0x18000411c  mov     rcx, [rdi+28h]; hThread
0x180004120  call    cs:__imp_ResumeThread
0x180004126  mov     rsi, [rsp+38h+arg_8]
0x18000412b  mov     eax, ebx
0x18000412d  mov     rbx, [rsp+38h+arg_0]
0x180004132  add     rsp, 30h
0x180004136  pop     rdi
0x180004137  retn
```
