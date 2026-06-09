# CWinTaskHandler::WorkerThreadProc(void *)

- ea: `0x180011fa0`
- end: `0x18001200b`
- name: `?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z`
- size: `107`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180011fa0`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180011ff9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180011ff9`

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
0x180011fa0  push    rbx
0x180011fa2  push    rbp
0x180011fa3  push    rsi
0x180011fa4  push    rdi
0x180011fa5  sub     rsp, 28h
0x180011fa9  mov     rax, [rcx]
0x180011fac  mov     rbx, rcx
0x180011faf  mov     ebp, [rcx+10h]
0x180011fb2  xor     esi, esi
0x180011fb4  mov     rax, [rax+40h]
0x180011fb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011fbd  mov     rcx, [rbx+30h]
0x180011fc1  mov     edi, eax
0x180011fc3  mov     rdx, [rcx]
0x180011fc6  mov     rax, [rdx+20h]
0x180011fca  mov     edx, edi
0x180011fcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011fd1  test    ebp, ebp
0x180011fd3  jz      short loc_180011FE1
0x180011fd5  mov     rsi, [rbx+18h]
0x180011fd9  mov     qword ptr [rbx+18h], 0
0x180011fe1  mov     rax, [rbx]
0x180011fe4  mov     rcx, rbx
0x180011fe7  mov     rax, [rax+10h]
0x180011feb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ff0  test    ebp, ebp
0x180011ff2  jz      short loc_180012000
0x180011ff4  mov     edx, edi; dwExitCode
0x180011ff6  mov     rcx, rsi; hLibModule
0x180011ff9  call    cs:__imp_FreeLibraryAndExitThread
0x180011fff  int     3; Trap to Debugger
0x180012000  mov     eax, edi
0x180012002  add     rsp, 28h
0x180012006  pop     rdi
0x180012007  pop     rsi
0x180012008  pop     rbp
0x180012009  pop     rbx
0x18001200a  retn
```
