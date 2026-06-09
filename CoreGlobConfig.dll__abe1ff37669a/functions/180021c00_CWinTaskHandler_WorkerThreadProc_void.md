# CWinTaskHandler::WorkerThreadProc(void *)

- ea: `0x180021c00`
- end: `0x180021c6b`
- name: `?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z`
- size: `107`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180021c00`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180021c59`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180021c59`

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
0x180021c00  push    rbx
0x180021c02  push    rbp
0x180021c03  push    rsi
0x180021c04  push    rdi
0x180021c05  sub     rsp, 28h
0x180021c09  mov     rax, [rcx]
0x180021c0c  mov     rbx, rcx
0x180021c0f  mov     ebp, [rcx+10h]
0x180021c12  xor     esi, esi
0x180021c14  mov     rax, [rax+40h]
0x180021c18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c1d  mov     rcx, [rbx+30h]
0x180021c21  mov     edi, eax
0x180021c23  mov     rdx, [rcx]
0x180021c26  mov     rax, [rdx+20h]
0x180021c2a  mov     edx, edi
0x180021c2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c31  test    ebp, ebp
0x180021c33  jz      short loc_180021C41
0x180021c35  mov     rsi, [rbx+18h]
0x180021c39  mov     qword ptr [rbx+18h], 0
0x180021c41  mov     rax, [rbx]
0x180021c44  mov     rcx, rbx
0x180021c47  mov     rax, [rax+10h]
0x180021c4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c50  test    ebp, ebp
0x180021c52  jz      short loc_180021C60
0x180021c54  mov     edx, edi; dwExitCode
0x180021c56  mov     rcx, rsi; hLibModule
0x180021c59  call    cs:__imp_FreeLibraryAndExitThread
0x180021c5f  int     3; Trap to Debugger
0x180021c60  mov     eax, edi
0x180021c62  add     rsp, 28h
0x180021c66  pop     rdi
0x180021c67  pop     rsi
0x180021c68  pop     rbp
0x180021c69  pop     rbx
0x180021c6a  retn
```
