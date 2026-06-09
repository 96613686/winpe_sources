# CWinTaskHandler::WorkerThreadProc(void *)

- ea: `0x180005500`
- end: `0x18000556b`
- name: `?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z`
- size: `107`
- prototype: `__int64 __fastcall(_DWORD *lpThreadParameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180005500`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180005559`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180005559`

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
0x180005500  push    rbx
0x180005502  push    rbp
0x180005503  push    rsi
0x180005504  push    rdi
0x180005505  sub     rsp, 28h
0x180005509  mov     rax, [rcx]
0x18000550c  mov     rbx, rcx
0x18000550f  mov     ebp, [rcx+10h]
0x180005512  xor     esi, esi
0x180005514  mov     rax, [rax+40h]
0x180005518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000551d  mov     rcx, [rbx+30h]
0x180005521  mov     edi, eax
0x180005523  mov     rdx, [rcx]
0x180005526  mov     rax, [rdx+20h]
0x18000552a  mov     edx, edi
0x18000552c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005531  test    ebp, ebp
0x180005533  jz      short loc_180005541
0x180005535  mov     rsi, [rbx+18h]
0x180005539  mov     qword ptr [rbx+18h], 0
0x180005541  mov     rax, [rbx]
0x180005544  mov     rcx, rbx
0x180005547  mov     rax, [rax+10h]
0x18000554b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005550  test    ebp, ebp
0x180005552  jz      short loc_180005560
0x180005554  mov     edx, edi; dwExitCode
0x180005556  mov     rcx, rsi; hLibModule
0x180005559  call    cs:__imp_FreeLibraryAndExitThread
0x18000555f  int     3; Trap to Debugger
0x180005560  mov     eax, edi
0x180005562  add     rsp, 28h
0x180005566  pop     rdi
0x180005567  pop     rsi
0x180005568  pop     rbp
0x180005569  pop     rbx
0x18000556a  retn
```
