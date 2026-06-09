# CWinTaskHandler::WorkerThreadProc(void *)

- ea: `0x180006dc0`
- end: `0x180006e2b`
- name: `?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z`
- size: `107`
- prototype: `__int64 __fastcall(_DWORD *Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180006dc0`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180006e19`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180006e19`

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
0x180006dc0  push    rbx
0x180006dc2  push    rbp
0x180006dc3  push    rsi
0x180006dc4  push    rdi
0x180006dc5  sub     rsp, 28h
0x180006dc9  mov     rax, [rcx]
0x180006dcc  mov     rbx, rcx
0x180006dcf  mov     ebp, [rcx+10h]
0x180006dd2  xor     esi, esi
0x180006dd4  mov     rax, [rax+40h]
0x180006dd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ddd  mov     rcx, [rbx+30h]
0x180006de1  mov     edi, eax
0x180006de3  mov     rdx, [rcx]
0x180006de6  mov     rax, [rdx+20h]
0x180006dea  mov     edx, edi
0x180006dec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006df1  test    ebp, ebp
0x180006df3  jz      short loc_180006E01
0x180006df5  mov     rsi, [rbx+18h]
0x180006df9  mov     qword ptr [rbx+18h], 0
0x180006e01  mov     rax, [rbx]
0x180006e04  mov     rcx, rbx
0x180006e07  mov     rax, [rax+10h]
0x180006e0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e10  test    ebp, ebp
0x180006e12  jz      short loc_180006E20
0x180006e14  mov     edx, edi; dwExitCode
0x180006e16  mov     rcx, rsi; hLibModule
0x180006e19  call    cs:__imp_FreeLibraryAndExitThread
0x180006e1f  int     3; Trap to Debugger
0x180006e20  mov     eax, edi
0x180006e22  add     rsp, 28h
0x180006e26  pop     rdi
0x180006e27  pop     rsi
0x180006e28  pop     rbp
0x180006e29  pop     rbx
0x180006e2a  retn
```
