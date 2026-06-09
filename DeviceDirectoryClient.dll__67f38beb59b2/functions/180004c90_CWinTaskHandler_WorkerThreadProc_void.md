# CWinTaskHandler::WorkerThreadProc(void *)

- ea: `0x180004c90`
- end: `0x180004cfb`
- name: `?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z`
- size: `107`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180004c90`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180004ce9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180004ce9`

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
0x180004c90  push    rbx
0x180004c92  push    rbp
0x180004c93  push    rsi
0x180004c94  push    rdi
0x180004c95  sub     rsp, 28h
0x180004c99  mov     rax, [rcx]
0x180004c9c  mov     rbx, rcx
0x180004c9f  mov     ebp, [rcx+10h]
0x180004ca2  xor     esi, esi
0x180004ca4  mov     rax, [rax+40h]
0x180004ca8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cad  mov     rcx, [rbx+30h]
0x180004cb1  mov     edi, eax
0x180004cb3  mov     rdx, [rcx]
0x180004cb6  mov     rax, [rdx+20h]
0x180004cba  mov     edx, edi
0x180004cbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cc1  test    ebp, ebp
0x180004cc3  jz      short loc_180004CD1
0x180004cc5  mov     rsi, [rbx+18h]
0x180004cc9  mov     qword ptr [rbx+18h], 0
0x180004cd1  mov     rax, [rbx]
0x180004cd4  mov     rcx, rbx
0x180004cd7  mov     rax, [rax+10h]
0x180004cdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ce0  test    ebp, ebp
0x180004ce2  jz      short loc_180004CF0
0x180004ce4  mov     edx, edi; dwExitCode
0x180004ce6  mov     rcx, rsi; hLibModule
0x180004ce9  call    cs:__imp_FreeLibraryAndExitThread
0x180004cef  int     3; Trap to Debugger
0x180004cf0  mov     eax, edi
0x180004cf2  add     rsp, 28h
0x180004cf6  pop     rdi
0x180004cf7  pop     rsi
0x180004cf8  pop     rbp
0x180004cf9  pop     rbx
0x180004cfa  retn
```
