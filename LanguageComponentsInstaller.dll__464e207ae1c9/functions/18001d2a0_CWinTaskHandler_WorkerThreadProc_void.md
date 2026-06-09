# CWinTaskHandler::WorkerThreadProc(void *)

- ea: `0x18001d2a0`
- end: `0x18001d30b`
- name: `?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z`
- size: `107`
- prototype: `__int64 __fastcall(_DWORD *Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18001d2a0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18001d2f9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18001d2f9`

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
0x18001d2a0  push    rbx
0x18001d2a2  push    rbp
0x18001d2a3  push    rsi
0x18001d2a4  push    rdi
0x18001d2a5  sub     rsp, 28h
0x18001d2a9  mov     rax, [rcx]
0x18001d2ac  mov     rbx, rcx
0x18001d2af  mov     ebp, [rcx+10h]
0x18001d2b2  xor     esi, esi
0x18001d2b4  mov     rax, [rax+40h]
0x18001d2b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d2bd  mov     rcx, [rbx+30h]
0x18001d2c1  mov     edi, eax
0x18001d2c3  mov     rdx, [rcx]
0x18001d2c6  mov     rax, [rdx+20h]
0x18001d2ca  mov     edx, edi
0x18001d2cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d2d1  test    ebp, ebp
0x18001d2d3  jz      short loc_18001D2E1
0x18001d2d5  mov     rsi, [rbx+18h]
0x18001d2d9  mov     qword ptr [rbx+18h], 0
0x18001d2e1  mov     rax, [rbx]
0x18001d2e4  mov     rcx, rbx
0x18001d2e7  mov     rax, [rax+10h]
0x18001d2eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d2f0  test    ebp, ebp
0x18001d2f2  jz      short loc_18001D300
0x18001d2f4  mov     edx, edi; dwExitCode
0x18001d2f6  mov     rcx, rsi; hLibModule
0x18001d2f9  call    cs:__imp_FreeLibraryAndExitThread
0x18001d2ff  int     3; Trap to Debugger
0x18001d300  mov     eax, edi
0x18001d302  add     rsp, 28h
0x18001d306  pop     rdi
0x18001d307  pop     rsi
0x18001d308  pop     rbp
0x18001d309  pop     rbx
0x18001d30a  retn
```
