# CWinTaskHandler::CreateWorkerThread(IUnknown *)

- ea: `0x180006674`
- end: `0x1800067c8`
- name: `?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18000b590`

## callees

- `0x180006674`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800067b0`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800067b0`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000671a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000671a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000677c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000677c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800066c5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800066c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800066d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000672f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800066d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000672f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006765`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006765`

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
0x180006674  mov     [rsp+arg_0], rbx
0x180006679  mov     [rsp+arg_8], rsi
0x18000667e  push    rdi
0x18000667f  sub     rsp, 30h
0x180006683  mov     rax, [rdx]
0x180006686  lea     rsi, [rcx+30h]
0x18000668a  mov     r9, rdx
0x18000668d  mov     rdi, rcx
0x180006690  mov     r8, rsi
0x180006693  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x18000669a  mov     rcx, r9
0x18000669d  mov     rax, [rax]
0x1800066a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066a5  mov     ebx, eax
0x1800066a7  test    eax, eax
0x1800066a9  js      loc_180006753
0x1800066af  cmp     dword ptr [rdi+10h], 0
0x1800066b3  jz      short loc_1800066EC
0x1800066b5  lea     r8, [rdi+18h]; phModule
0x1800066b9  mov     ecx, 4; dwFlags
0x1800066be  lea     rdx, __ImageBase; lpModuleName
0x1800066c5  call    cs:__imp_GetModuleHandleExW
0x1800066cb  test    eax, eax
0x1800066cd  jz      short loc_1800066D3
0x1800066cf  xor     ebx, ebx
0x1800066d1  jmp     short loc_1800066EC
0x1800066d3  call    cs:__imp_GetLastError
0x1800066d9  mov     ebx, eax
0x1800066db  test    eax, eax
0x1800066dd  jle     short loc_1800066E8
0x1800066df  movzx   ebx, ax
0x1800066e2  or      ebx, 80070000h
0x1800066e8  test    ebx, ebx
0x1800066ea  js      short loc_180006757
0x1800066ec  mov     rax, [rdi]
0x1800066ef  mov     rcx, rdi
0x1800066f2  mov     rax, [rax+8]
0x1800066f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066fb  mov     r9, rdi; lpParameter
0x1800066fe  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x180006707  lea     r8, ?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z; lpStartAddress
0x18000670e  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x180006716  xor     edx, edx; dwStackSize
0x180006718  xor     ecx, ecx; lpThreadAttributes
0x18000671a  call    cs:__imp_CreateThread
0x180006720  mov     [rdi+28h], rax
0x180006724  inc     rax
0x180006727  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000672d  jnz     short loc_180006753
0x18000672f  call    cs:__imp_GetLastError
0x180006735  mov     ebx, eax
0x180006737  test    eax, eax
0x180006739  jle     short loc_180006744
0x18000673b  movzx   ebx, ax
0x18000673e  or      ebx, 80070000h
0x180006744  mov     rax, [rdi]
0x180006747  mov     rcx, rdi
0x18000674a  mov     rax, [rax+10h]
0x18000674e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006753  test    ebx, ebx
0x180006755  jns     short loc_1800067A7
0x180006757  mov     rcx, [rdi+28h]; hObject
0x18000675b  lea     rax, [rcx-1]
0x18000675f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180006763  ja      short loc_180006773
0x180006765  call    cs:__imp_CloseHandle
0x18000676b  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x180006773  mov     rcx, [rdi+18h]; hLibModule
0x180006777  test    rcx, rcx
0x18000677a  jz      short loc_18000678A
0x18000677c  call    cs:__imp_FreeLibrary
0x180006782  mov     qword ptr [rdi+18h], 0
0x18000678a  mov     rcx, [rsi]
0x18000678d  test    rcx, rcx
0x180006790  jz      short loc_1800067B6
0x180006792  mov     rax, [rcx]
0x180006795  mov     rax, [rax+10h]
0x180006799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000679e  mov     qword ptr [rsi], 0
0x1800067a5  jmp     short loc_1800067B6
0x1800067a7  lock or [rsp+38h+var_38], 0
0x1800067ac  mov     rcx, [rdi+28h]; hThread
0x1800067b0  call    cs:__imp_ResumeThread
0x1800067b6  mov     rsi, [rsp+38h+arg_8]
0x1800067bb  mov     eax, ebx
0x1800067bd  mov     rbx, [rsp+38h+arg_0]
0x1800067c2  add     rsp, 30h
0x1800067c6  pop     rdi
0x1800067c7  retn
```
