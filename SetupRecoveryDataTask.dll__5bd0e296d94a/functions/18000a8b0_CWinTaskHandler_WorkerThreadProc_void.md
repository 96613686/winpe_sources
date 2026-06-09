# CWinTaskHandler::WorkerThreadProc(void *)

- ea: `0x18000a8b0`
- end: `0x18000a91b`
- name: `?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z`
- size: `107`
- prototype: `__int64 __fastcall(_DWORD *lpThreadParameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18000a8b0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18000a909`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18000a909`

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
0x18000a8b0  push    rbx
0x18000a8b2  push    rbp
0x18000a8b3  push    rsi
0x18000a8b4  push    rdi
0x18000a8b5  sub     rsp, 28h
0x18000a8b9  mov     rax, [rcx]
0x18000a8bc  mov     rbx, rcx
0x18000a8bf  mov     ebp, [rcx+10h]
0x18000a8c2  xor     esi, esi
0x18000a8c4  mov     rax, [rax+40h]
0x18000a8c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8cd  mov     rcx, [rbx+30h]
0x18000a8d1  mov     edi, eax
0x18000a8d3  mov     rdx, [rcx]
0x18000a8d6  mov     rax, [rdx+20h]
0x18000a8da  mov     edx, edi
0x18000a8dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8e1  test    ebp, ebp
0x18000a8e3  jz      short loc_18000A8F1
0x18000a8e5  mov     rsi, [rbx+18h]
0x18000a8e9  mov     qword ptr [rbx+18h], 0
0x18000a8f1  mov     rax, [rbx]
0x18000a8f4  mov     rcx, rbx
0x18000a8f7  mov     rax, [rax+10h]
0x18000a8fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a900  test    ebp, ebp
0x18000a902  jz      short loc_18000A910
0x18000a904  mov     edx, edi; dwExitCode
0x18000a906  mov     rcx, rsi; hLibModule
0x18000a909  call    cs:__imp_FreeLibraryAndExitThread
0x18000a90f  int     3; Trap to Debugger
0x18000a910  mov     eax, edi
0x18000a912  add     rsp, 28h
0x18000a916  pop     rdi
0x18000a917  pop     rsi
0x18000a918  pop     rbp
0x18000a919  pop     rbx
0x18000a91a  retn
```
