# CWinTaskHandler::WorkerThreadProc(void *)

- ea: `0x180002250`
- end: `0x1800022bb`
- name: `?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z`
- size: `107`
- prototype: `__int64 __fastcall(_DWORD *lpThreadParameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180002250`
- `0x180003010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x1800022a9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x1800022a9`

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
0x180002250  push    rbx
0x180002252  push    rbp
0x180002253  push    rsi
0x180002254  push    rdi
0x180002255  sub     rsp, 28h
0x180002259  mov     rax, [rcx]
0x18000225c  mov     rbx, rcx
0x18000225f  mov     ebp, [rcx+10h]
0x180002262  xor     esi, esi
0x180002264  mov     rax, [rax+40h]
0x180002268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000226d  mov     rcx, [rbx+30h]
0x180002271  mov     edi, eax
0x180002273  mov     rdx, [rcx]
0x180002276  mov     rax, [rdx+20h]
0x18000227a  mov     edx, edi
0x18000227c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002281  test    ebp, ebp
0x180002283  jz      short loc_180002291
0x180002285  mov     rsi, [rbx+18h]
0x180002289  mov     qword ptr [rbx+18h], 0
0x180002291  mov     rax, [rbx]
0x180002294  mov     rcx, rbx
0x180002297  mov     rax, [rax+10h]
0x18000229b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022a0  test    ebp, ebp
0x1800022a2  jz      short loc_1800022B0
0x1800022a4  mov     edx, edi; dwExitCode
0x1800022a6  mov     rcx, rsi; hLibModule
0x1800022a9  call    cs:__imp_FreeLibraryAndExitThread
0x1800022af  int     3; Trap to Debugger
0x1800022b0  mov     eax, edi
0x1800022b2  add     rsp, 28h
0x1800022b6  pop     rdi
0x1800022b7  pop     rsi
0x1800022b8  pop     rbp
0x1800022b9  pop     rbx
0x1800022ba  retn
```
