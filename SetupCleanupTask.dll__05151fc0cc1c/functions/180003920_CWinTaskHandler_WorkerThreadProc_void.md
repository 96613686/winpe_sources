# CWinTaskHandler::WorkerThreadProc(void *)

- ea: `0x180003920`
- end: `0x18000398b`
- name: `?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z`
- size: `107`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180003920`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180003979`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180003979`

## pseudocode

```c
__int64 __fastcall CWinTaskHandler::WorkerThreadProc(_DWORD *Parameter)
{
  int v2; // ebp
  HMODULE v3; // rsi
  __int64 v4; // rdi

  v2 = Parameter[4];
  v3 = 0;
  v4 = (*(unsigned int (__fastcall **)(_DWORD *))(*(_QWORD *)Parameter + 64LL))(Parameter);
  (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)Parameter + 6) + 32LL))(*((_QWORD *)Parameter + 6), v4);
  if ( v2 )
  {
    v3 = (HMODULE)*((_QWORD *)Parameter + 3);
    *((_QWORD *)Parameter + 3) = 0;
  }
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)Parameter + 16LL))(Parameter);
  if ( v2 )
    FreeLibraryAndExitThread(v3, v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180003920  push    rbx
0x180003922  push    rbp
0x180003923  push    rsi
0x180003924  push    rdi
0x180003925  sub     rsp, 28h
0x180003929  mov     rax, [rcx]
0x18000392c  mov     rbx, rcx
0x18000392f  mov     ebp, [rcx+10h]
0x180003932  xor     esi, esi
0x180003934  mov     rax, [rax+40h]
0x180003938  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000393d  mov     rcx, [rbx+30h]
0x180003941  mov     edi, eax
0x180003943  mov     rdx, [rcx]
0x180003946  mov     rax, [rdx+20h]
0x18000394a  mov     edx, edi
0x18000394c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003951  test    ebp, ebp
0x180003953  jz      short loc_180003961
0x180003955  mov     rsi, [rbx+18h]
0x180003959  mov     qword ptr [rbx+18h], 0
0x180003961  mov     rax, [rbx]
0x180003964  mov     rcx, rbx
0x180003967  mov     rax, [rax+10h]
0x18000396b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003970  test    ebp, ebp
0x180003972  jz      short loc_180003980
0x180003974  mov     edx, edi; dwExitCode
0x180003976  mov     rcx, rsi; hLibModule
0x180003979  call    cs:__imp_FreeLibraryAndExitThread
0x18000397f  int     3; Trap to Debugger
0x180003980  mov     eax, edi
0x180003982  add     rsp, 28h
0x180003986  pop     rdi
0x180003987  pop     rsi
0x180003988  pop     rbp
0x180003989  pop     rbx
0x18000398a  retn
```
