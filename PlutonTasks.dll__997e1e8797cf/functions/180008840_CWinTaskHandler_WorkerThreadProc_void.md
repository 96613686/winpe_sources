# CWinTaskHandler::WorkerThreadProc(void *)

- ea: `0x180008840`
- end: `0x1800088ab`
- name: `?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z`
- size: `107`
- prototype: `__int64 __fastcall(_DWORD *lpThreadParameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180008840`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180008899`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180008899`

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
0x180008840  push    rbx
0x180008842  push    rbp
0x180008843  push    rsi
0x180008844  push    rdi
0x180008845  sub     rsp, 28h
0x180008849  mov     rax, [rcx]
0x18000884c  mov     rbx, rcx
0x18000884f  mov     ebp, [rcx+10h]
0x180008852  xor     esi, esi
0x180008854  mov     rax, [rax+40h]
0x180008858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000885d  mov     rcx, [rbx+30h]
0x180008861  mov     edi, eax
0x180008863  mov     rdx, [rcx]
0x180008866  mov     rax, [rdx+20h]
0x18000886a  mov     edx, edi
0x18000886c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008871  test    ebp, ebp
0x180008873  jz      short loc_180008881
0x180008875  mov     rsi, [rbx+18h]
0x180008879  mov     qword ptr [rbx+18h], 0
0x180008881  mov     rax, [rbx]
0x180008884  mov     rcx, rbx
0x180008887  mov     rax, [rax+10h]
0x18000888b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008890  test    ebp, ebp
0x180008892  jz      short loc_1800088A0
0x180008894  mov     edx, edi; dwExitCode
0x180008896  mov     rcx, rsi; hLibModule
0x180008899  call    cs:__imp_FreeLibraryAndExitThread
0x18000889f  int     3; Trap to Debugger
0x1800088a0  mov     eax, edi
0x1800088a2  add     rsp, 28h
0x1800088a6  pop     rdi
0x1800088a7  pop     rsi
0x1800088a8  pop     rbp
0x1800088a9  pop     rbx
0x1800088aa  retn
```
