# CWinTaskHandler::WorkerThreadProc(void *)

- ea: `0x180035770`
- end: `0x1800357db`
- name: `?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z`
- size: `107`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180035770`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x1800357c9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x1800357c9`

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
0x180035770  push    rbx
0x180035772  push    rbp
0x180035773  push    rsi
0x180035774  push    rdi
0x180035775  sub     rsp, 28h
0x180035779  mov     rax, [rcx]
0x18003577c  mov     rbx, rcx
0x18003577f  mov     ebp, [rcx+10h]
0x180035782  xor     esi, esi
0x180035784  mov     rax, [rax+40h]
0x180035788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003578d  mov     rcx, [rbx+30h]
0x180035791  mov     edi, eax
0x180035793  mov     rdx, [rcx]
0x180035796  mov     rax, [rdx+20h]
0x18003579a  mov     edx, edi
0x18003579c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800357a1  test    ebp, ebp
0x1800357a3  jz      short loc_1800357B1
0x1800357a5  mov     rsi, [rbx+18h]
0x1800357a9  mov     qword ptr [rbx+18h], 0
0x1800357b1  mov     rax, [rbx]
0x1800357b4  mov     rcx, rbx
0x1800357b7  mov     rax, [rax+10h]
0x1800357bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800357c0  test    ebp, ebp
0x1800357c2  jz      short loc_1800357D0
0x1800357c4  mov     edx, edi; dwExitCode
0x1800357c6  mov     rcx, rsi; hLibModule
0x1800357c9  call    cs:__imp_FreeLibraryAndExitThread
0x1800357cf  int     3; Trap to Debugger
0x1800357d0  mov     eax, edi
0x1800357d2  add     rsp, 28h
0x1800357d6  pop     rdi
0x1800357d7  pop     rsi
0x1800357d8  pop     rbp
0x1800357d9  pop     rbx
0x1800357da  retn
```
