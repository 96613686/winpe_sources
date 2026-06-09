# CWinTaskHandler::CreateWorkerThread(IUnknown *)

- ea: `0x1800175e8`
- end: `0x18001773c`
- name: `?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18001b2b0`

## callees

- `0x1800175e8`
- `0x18012d010`

## import_xrefs

- `KERNEL32!ResumeThread` at `0x180017724`
- `KERNEL32!ResumeThread` at `0x180017724`
- `KERNEL32!FreeLibrary` at `0x1800176f0`
- `KERNEL32!FreeLibrary` at `0x1800176f0`
- `KERNEL32!CreateThread` at `0x18001768e`
- `KERNEL32!CreateThread` at `0x18001768e`
- `KERNEL32!CloseHandle` at `0x1800176d9`
- `KERNEL32!CloseHandle` at `0x1800176d9`
- `KERNEL32!GetLastError` at `0x180017647`
- `KERNEL32!GetLastError` at `0x1800176a3`
- `KERNEL32!GetLastError` at `0x180017647`
- `KERNEL32!GetLastError` at `0x1800176a3`
- `KERNEL32!GetModuleHandleExW` at `0x180017639`
- `KERNEL32!GetModuleHandleExW` at `0x180017639`

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
0x1800175e8  mov     [rsp+arg_0], rbx
0x1800175ed  mov     [rsp+arg_8], rsi
0x1800175f2  push    rdi
0x1800175f3  sub     rsp, 30h
0x1800175f7  mov     rax, [rdx]
0x1800175fa  lea     rsi, [rcx+30h]
0x1800175fe  mov     r9, rdx
0x180017601  mov     rdi, rcx
0x180017604  mov     r8, rsi
0x180017607  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x18001760e  mov     rcx, r9
0x180017611  mov     rax, [rax]
0x180017614  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017619  mov     ebx, eax
0x18001761b  test    eax, eax
0x18001761d  js      loc_1800176C7
0x180017623  cmp     dword ptr [rdi+10h], 0
0x180017627  jz      short loc_180017660
0x180017629  lea     r8, [rdi+18h]; phModule
0x18001762d  mov     ecx, 4; dwFlags
0x180017632  lea     rdx, __ImageBase; lpModuleName
0x180017639  call    cs:__imp_GetModuleHandleExW
0x18001763f  test    eax, eax
0x180017641  jz      short loc_180017647
0x180017643  xor     ebx, ebx
0x180017645  jmp     short loc_180017660
0x180017647  call    cs:__imp_GetLastError
0x18001764d  mov     ebx, eax
0x18001764f  test    eax, eax
0x180017651  jle     short loc_18001765C
0x180017653  movzx   ebx, ax
0x180017656  or      ebx, 80070000h
0x18001765c  test    ebx, ebx
0x18001765e  js      short loc_1800176CB
0x180017660  mov     rax, [rdi]
0x180017663  mov     rcx, rdi
0x180017666  mov     rax, [rax+8]
0x18001766a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001766f  mov     r9, rdi; lpParameter
0x180017672  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x18001767b  lea     r8, ?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z; lpStartAddress
0x180017682  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x18001768a  xor     edx, edx; dwStackSize
0x18001768c  xor     ecx, ecx; lpThreadAttributes
0x18001768e  call    cs:__imp_CreateThread
0x180017694  mov     [rdi+28h], rax
0x180017698  inc     rax
0x18001769b  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800176a1  jnz     short loc_1800176C7
0x1800176a3  call    cs:__imp_GetLastError
0x1800176a9  mov     ebx, eax
0x1800176ab  test    eax, eax
0x1800176ad  jle     short loc_1800176B8
0x1800176af  movzx   ebx, ax
0x1800176b2  or      ebx, 80070000h
0x1800176b8  mov     rax, [rdi]
0x1800176bb  mov     rcx, rdi
0x1800176be  mov     rax, [rax+10h]
0x1800176c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800176c7  test    ebx, ebx
0x1800176c9  jns     short loc_18001771B
0x1800176cb  mov     rcx, [rdi+28h]; hObject
0x1800176cf  lea     rax, [rcx-1]
0x1800176d3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800176d7  ja      short loc_1800176E7
0x1800176d9  call    cs:__imp_CloseHandle
0x1800176df  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x1800176e7  mov     rcx, [rdi+18h]; hLibModule
0x1800176eb  test    rcx, rcx
0x1800176ee  jz      short loc_1800176FE
0x1800176f0  call    cs:__imp_FreeLibrary
0x1800176f6  mov     qword ptr [rdi+18h], 0
0x1800176fe  mov     rcx, [rsi]
0x180017701  test    rcx, rcx
0x180017704  jz      short loc_18001772A
0x180017706  mov     rax, [rcx]
0x180017709  mov     rax, [rax+10h]
0x18001770d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017712  mov     qword ptr [rsi], 0
0x180017719  jmp     short loc_18001772A
0x18001771b  lock or [rsp+38h+var_38], 0
0x180017720  mov     rcx, [rdi+28h]; hThread
0x180017724  call    cs:__imp_ResumeThread
0x18001772a  mov     rsi, [rsp+38h+arg_8]
0x18001772f  mov     eax, ebx
0x180017731  mov     rbx, [rsp+38h+arg_0]
0x180017736  add     rsp, 30h
0x18001773a  pop     rdi
0x18001773b  retn
```
