# CWinTaskHandler::WorkerThreadProc(void *)

- ea: `0x18000e6a0`
- end: `0x18000e70b`
- name: `?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z`
- size: `107`
- prototype: `__int64 __fastcall(_DWORD *lpThreadParameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18000e6a0`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18000e6f9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18000e6f9`

## pseudocode

```c
__int64 __fastcall CWinTaskHandler::WorkerThreadProc(_DWORD *lpThreadParameter)
{
  int v2; // ebp
  HMODULE v3; // rsi
  __int64 v4; // rdi

  v2 = lpThreadParameter[4];
  v3 = 0;
  v4 = (*(unsigned int (__fastcall **)(_DWORD *))(*(_QWORD *)lpThreadParameter + 64LL))(lpThreadParameter);
  (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)lpThreadParameter + 6) + 32LL))(
    *((_QWORD *)lpThreadParameter + 6),
    v4);
  if ( v2 )
  {
    v3 = (HMODULE)*((_QWORD *)lpThreadParameter + 3);
    *((_QWORD *)lpThreadParameter + 3) = 0;
  }
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)lpThreadParameter + 16LL))(lpThreadParameter);
  if ( v2 )
    FreeLibraryAndExitThread(v3, v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000e6a0  push    rbx
0x18000e6a2  push    rbp
0x18000e6a3  push    rsi
0x18000e6a4  push    rdi
0x18000e6a5  sub     rsp, 28h
0x18000e6a9  mov     rax, [rcx]
0x18000e6ac  mov     rbx, rcx
0x18000e6af  mov     ebp, [rcx+10h]
0x18000e6b2  xor     esi, esi
0x18000e6b4  mov     rax, [rax+40h]
0x18000e6b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6bd  mov     rcx, [rbx+30h]
0x18000e6c1  mov     edi, eax
0x18000e6c3  mov     rdx, [rcx]
0x18000e6c6  mov     rax, [rdx+20h]
0x18000e6ca  mov     edx, edi
0x18000e6cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6d1  test    ebp, ebp
0x18000e6d3  jz      short loc_18000E6E1
0x18000e6d5  mov     rsi, [rbx+18h]
0x18000e6d9  mov     qword ptr [rbx+18h], 0
0x18000e6e1  mov     rax, [rbx]
0x18000e6e4  mov     rcx, rbx
0x18000e6e7  mov     rax, [rax+10h]
0x18000e6eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6f0  test    ebp, ebp
0x18000e6f2  jz      short loc_18000E700
0x18000e6f4  mov     edx, edi; dwExitCode
0x18000e6f6  mov     rcx, rsi; hLibModule
0x18000e6f9  call    cs:__imp_FreeLibraryAndExitThread
0x18000e6ff  int     3; Trap to Debugger
0x18000e700  mov     eax, edi
0x18000e702  add     rsp, 28h
0x18000e706  pop     rdi
0x18000e707  pop     rsi
0x18000e708  pop     rbp
0x18000e709  pop     rbx
0x18000e70a  retn
```
