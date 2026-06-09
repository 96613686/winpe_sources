# CWinTaskHandler::CreateWorkerThread(IUnknown *)

- ea: `0x180010004`
- end: `0x180010158`
- name: `?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18001bc60`

## callees

- `0x180010004`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001010c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001010c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180010055`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180010055`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010063`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800100bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010063`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800100bf`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800100aa`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800100aa`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180010140`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180010140`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800100f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800100f5`

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
0x180010004  mov     [rsp+arg_0], rbx
0x180010009  mov     [rsp+arg_8], rsi
0x18001000e  push    rdi
0x18001000f  sub     rsp, 30h
0x180010013  mov     rax, [rdx]
0x180010016  lea     rsi, [rcx+30h]
0x18001001a  mov     r9, rdx
0x18001001d  mov     rdi, rcx
0x180010020  mov     r8, rsi
0x180010023  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x18001002a  mov     rcx, r9
0x18001002d  mov     rax, [rax]
0x180010030  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010035  mov     ebx, eax
0x180010037  test    eax, eax
0x180010039  js      loc_1800100E3
0x18001003f  cmp     dword ptr [rdi+10h], 0
0x180010043  jz      short loc_18001007C
0x180010045  lea     r8, [rdi+18h]; phModule
0x180010049  mov     ecx, 4; dwFlags
0x18001004e  lea     rdx, __ImageBase; lpModuleName
0x180010055  call    cs:__imp_GetModuleHandleExW
0x18001005b  test    eax, eax
0x18001005d  jz      short loc_180010063
0x18001005f  xor     ebx, ebx
0x180010061  jmp     short loc_18001007C
0x180010063  call    cs:__imp_GetLastError
0x180010069  mov     ebx, eax
0x18001006b  test    eax, eax
0x18001006d  jle     short loc_180010078
0x18001006f  movzx   ebx, ax
0x180010072  or      ebx, 80070000h
0x180010078  test    ebx, ebx
0x18001007a  js      short loc_1800100E7
0x18001007c  mov     rax, [rdi]
0x18001007f  mov     rcx, rdi
0x180010082  mov     rax, [rax+8]
0x180010086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001008b  mov     r9, rdi; lpParameter
0x18001008e  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x180010097  lea     r8, ?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z; lpStartAddress
0x18001009e  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x1800100a6  xor     edx, edx; dwStackSize
0x1800100a8  xor     ecx, ecx; lpThreadAttributes
0x1800100aa  call    cs:__imp_CreateThread
0x1800100b0  mov     [rdi+28h], rax
0x1800100b4  inc     rax
0x1800100b7  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800100bd  jnz     short loc_1800100E3
0x1800100bf  call    cs:__imp_GetLastError
0x1800100c5  mov     ebx, eax
0x1800100c7  test    eax, eax
0x1800100c9  jle     short loc_1800100D4
0x1800100cb  movzx   ebx, ax
0x1800100ce  or      ebx, 80070000h
0x1800100d4  mov     rax, [rdi]
0x1800100d7  mov     rcx, rdi
0x1800100da  mov     rax, [rax+10h]
0x1800100de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100e3  test    ebx, ebx
0x1800100e5  jns     short loc_180010137
0x1800100e7  mov     rcx, [rdi+28h]; hObject
0x1800100eb  lea     rax, [rcx-1]
0x1800100ef  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800100f3  ja      short loc_180010103
0x1800100f5  call    cs:__imp_CloseHandle
0x1800100fb  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x180010103  mov     rcx, [rdi+18h]; hLibModule
0x180010107  test    rcx, rcx
0x18001010a  jz      short loc_18001011A
0x18001010c  call    cs:__imp_FreeLibrary
0x180010112  mov     qword ptr [rdi+18h], 0
0x18001011a  mov     rcx, [rsi]
0x18001011d  test    rcx, rcx
0x180010120  jz      short loc_180010146
0x180010122  mov     rax, [rcx]
0x180010125  mov     rax, [rax+10h]
0x180010129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001012e  mov     qword ptr [rsi], 0
0x180010135  jmp     short loc_180010146
0x180010137  lock or [rsp+38h+var_38], 0
0x18001013c  mov     rcx, [rdi+28h]; hThread
0x180010140  call    cs:__imp_ResumeThread
0x180010146  mov     rsi, [rsp+38h+arg_8]
0x18001014b  mov     eax, ebx
0x18001014d  mov     rbx, [rsp+38h+arg_0]
0x180010152  add     rsp, 30h
0x180010156  pop     rdi
0x180010157  retn
```
