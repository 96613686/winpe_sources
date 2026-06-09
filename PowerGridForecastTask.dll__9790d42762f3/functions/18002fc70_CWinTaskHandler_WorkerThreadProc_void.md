# CWinTaskHandler::WorkerThreadProc(void *)

- ea: `0x18002fc70`
- end: `0x18002fcdb`
- name: `?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z`
- size: `107`
- prototype: `__int64 __fastcall(_DWORD *lpThreadParameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18002fc70`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18002fcc9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18002fcc9`

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
0x18002fc70  push    rbx
0x18002fc72  push    rbp
0x18002fc73  push    rsi
0x18002fc74  push    rdi
0x18002fc75  sub     rsp, 28h
0x18002fc79  mov     rax, [rcx]
0x18002fc7c  mov     rbx, rcx
0x18002fc7f  mov     ebp, [rcx+10h]
0x18002fc82  xor     esi, esi
0x18002fc84  mov     rax, [rax+40h]
0x18002fc88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fc8d  mov     rcx, [rbx+30h]
0x18002fc91  mov     edi, eax
0x18002fc93  mov     rdx, [rcx]
0x18002fc96  mov     rax, [rdx+20h]
0x18002fc9a  mov     edx, edi
0x18002fc9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fca1  test    ebp, ebp
0x18002fca3  jz      short loc_18002FCB1
0x18002fca5  mov     rsi, [rbx+18h]
0x18002fca9  mov     qword ptr [rbx+18h], 0
0x18002fcb1  mov     rax, [rbx]
0x18002fcb4  mov     rcx, rbx
0x18002fcb7  mov     rax, [rax+10h]
0x18002fcbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fcc0  test    ebp, ebp
0x18002fcc2  jz      short loc_18002FCD0
0x18002fcc4  mov     edx, edi; dwExitCode
0x18002fcc6  mov     rcx, rsi; hLibModule
0x18002fcc9  call    cs:__imp_FreeLibraryAndExitThread
0x18002fccf  int     3; Trap to Debugger
0x18002fcd0  mov     eax, edi
0x18002fcd2  add     rsp, 28h
0x18002fcd6  pop     rdi
0x18002fcd7  pop     rsi
0x18002fcd8  pop     rbp
0x18002fcd9  pop     rbx
0x18002fcda  retn
```
