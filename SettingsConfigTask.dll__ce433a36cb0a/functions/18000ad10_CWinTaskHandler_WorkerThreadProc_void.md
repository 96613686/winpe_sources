# CWinTaskHandler::WorkerThreadProc(void *)

- ea: `0x18000ad10`
- end: `0x18000ad7b`
- name: `?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z`
- size: `107`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18000ad10`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18000ad69`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18000ad69`

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
0x18000ad10  push    rbx
0x18000ad12  push    rbp
0x18000ad13  push    rsi
0x18000ad14  push    rdi
0x18000ad15  sub     rsp, 28h
0x18000ad19  mov     rax, [rcx]
0x18000ad1c  mov     rbx, rcx
0x18000ad1f  mov     ebp, [rcx+10h]
0x18000ad22  xor     esi, esi
0x18000ad24  mov     rax, [rax+40h]
0x18000ad28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad2d  mov     rcx, [rbx+30h]
0x18000ad31  mov     edi, eax
0x18000ad33  mov     rdx, [rcx]
0x18000ad36  mov     rax, [rdx+20h]
0x18000ad3a  mov     edx, edi
0x18000ad3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad41  test    ebp, ebp
0x18000ad43  jz      short loc_18000AD51
0x18000ad45  mov     rsi, [rbx+18h]
0x18000ad49  mov     qword ptr [rbx+18h], 0
0x18000ad51  mov     rax, [rbx]
0x18000ad54  mov     rcx, rbx
0x18000ad57  mov     rax, [rax+10h]
0x18000ad5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad60  test    ebp, ebp
0x18000ad62  jz      short loc_18000AD70
0x18000ad64  mov     edx, edi; dwExitCode
0x18000ad66  mov     rcx, rsi; hLibModule
0x18000ad69  call    cs:__imp_FreeLibraryAndExitThread
0x18000ad6f  int     3; Trap to Debugger
0x18000ad70  mov     eax, edi
0x18000ad72  add     rsp, 28h
0x18000ad76  pop     rdi
0x18000ad77  pop     rsi
0x18000ad78  pop     rbp
0x18000ad79  pop     rbx
0x18000ad7a  retn
```
