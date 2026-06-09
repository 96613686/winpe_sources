# CWinTaskHandler::WorkerThreadProc(void *)

- ea: `0x180007870`
- end: `0x1800078db`
- name: `?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z`
- size: `107`
- prototype: `__int64 __fastcall(_DWORD *lpThreadParameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180007870`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x1800078c9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x1800078c9`

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
0x180007870  push    rbx
0x180007872  push    rbp
0x180007873  push    rsi
0x180007874  push    rdi
0x180007875  sub     rsp, 28h
0x180007879  mov     rax, [rcx]
0x18000787c  mov     rbx, rcx
0x18000787f  mov     ebp, [rcx+10h]
0x180007882  xor     esi, esi
0x180007884  mov     rax, [rax+40h]
0x180007888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000788d  mov     rcx, [rbx+30h]
0x180007891  mov     edi, eax
0x180007893  mov     rdx, [rcx]
0x180007896  mov     rax, [rdx+20h]
0x18000789a  mov     edx, edi
0x18000789c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078a1  test    ebp, ebp
0x1800078a3  jz      short loc_1800078B1
0x1800078a5  mov     rsi, [rbx+18h]
0x1800078a9  mov     qword ptr [rbx+18h], 0
0x1800078b1  mov     rax, [rbx]
0x1800078b4  mov     rcx, rbx
0x1800078b7  mov     rax, [rax+10h]
0x1800078bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078c0  test    ebp, ebp
0x1800078c2  jz      short loc_1800078D0
0x1800078c4  mov     edx, edi; dwExitCode
0x1800078c6  mov     rcx, rsi; hLibModule
0x1800078c9  call    cs:__imp_FreeLibraryAndExitThread
0x1800078cf  int     3; Trap to Debugger
0x1800078d0  mov     eax, edi
0x1800078d2  add     rsp, 28h
0x1800078d6  pop     rdi
0x1800078d7  pop     rsi
0x1800078d8  pop     rbp
0x1800078d9  pop     rbx
0x1800078da  retn
```
