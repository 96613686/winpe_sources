# CWinTaskHandler::WorkerThreadProc(void *)

- ea: `0x18000c460`
- end: `0x18000c4cb`
- name: `?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z`
- size: `107`
- prototype: `__int64 __fastcall(_DWORD *Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18000c460`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18000c4b9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18000c4b9`

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
0x18000c460  push    rbx
0x18000c462  push    rbp
0x18000c463  push    rsi
0x18000c464  push    rdi
0x18000c465  sub     rsp, 28h
0x18000c469  mov     rax, [rcx]
0x18000c46c  mov     rbx, rcx
0x18000c46f  mov     ebp, [rcx+10h]
0x18000c472  xor     esi, esi
0x18000c474  mov     rax, [rax+40h]
0x18000c478  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c47d  mov     rcx, [rbx+30h]
0x18000c481  mov     edi, eax
0x18000c483  mov     rdx, [rcx]
0x18000c486  mov     rax, [rdx+20h]
0x18000c48a  mov     edx, edi
0x18000c48c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c491  test    ebp, ebp
0x18000c493  jz      short loc_18000C4A1
0x18000c495  mov     rsi, [rbx+18h]
0x18000c499  mov     qword ptr [rbx+18h], 0
0x18000c4a1  mov     rax, [rbx]
0x18000c4a4  mov     rcx, rbx
0x18000c4a7  mov     rax, [rax+10h]
0x18000c4ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4b0  test    ebp, ebp
0x18000c4b2  jz      short loc_18000C4C0
0x18000c4b4  mov     edx, edi; dwExitCode
0x18000c4b6  mov     rcx, rsi; hLibModule
0x18000c4b9  call    cs:__imp_FreeLibraryAndExitThread
0x18000c4bf  int     3; Trap to Debugger
0x18000c4c0  mov     eax, edi
0x18000c4c2  add     rsp, 28h
0x18000c4c6  pop     rdi
0x18000c4c7  pop     rsi
0x18000c4c8  pop     rbp
0x18000c4c9  pop     rbx
0x18000c4ca  retn
```
