# CWinTaskHandler::WorkerThreadProc(void *)

- ea: `0x180003d70`
- end: `0x180003ddb`
- name: `?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z`
- size: `107`
- prototype: `__int64 __fastcall(_DWORD *Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180003d70`
- `0x180006010`

## import_xrefs

- `KERNEL32!FreeLibraryAndExitThread` at `0x180003dc9`
- `KERNEL32!FreeLibraryAndExitThread` at `0x180003dc9`

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
0x180003d70  push    rbx
0x180003d72  push    rbp
0x180003d73  push    rsi
0x180003d74  push    rdi
0x180003d75  sub     rsp, 28h
0x180003d79  mov     rax, [rcx]
0x180003d7c  mov     rbx, rcx
0x180003d7f  mov     ebp, [rcx+10h]
0x180003d82  xor     esi, esi
0x180003d84  mov     rax, [rax+40h]
0x180003d88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d8d  mov     rcx, [rbx+30h]
0x180003d91  mov     edi, eax
0x180003d93  mov     rdx, [rcx]
0x180003d96  mov     rax, [rdx+20h]
0x180003d9a  mov     edx, edi
0x180003d9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003da1  test    ebp, ebp
0x180003da3  jz      short loc_180003DB1
0x180003da5  mov     rsi, [rbx+18h]
0x180003da9  mov     qword ptr [rbx+18h], 0
0x180003db1  mov     rax, [rbx]
0x180003db4  mov     rcx, rbx
0x180003db7  mov     rax, [rax+10h]
0x180003dbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003dc0  test    ebp, ebp
0x180003dc2  jz      short loc_180003DD0
0x180003dc4  mov     edx, edi; dwExitCode
0x180003dc6  mov     rcx, rsi; hLibModule
0x180003dc9  call    cs:__imp_FreeLibraryAndExitThread
0x180003dd0  mov     eax, edi
0x180003dd2  add     rsp, 28h
0x180003dd6  pop     rdi
0x180003dd7  pop     rsi
0x180003dd8  pop     rbp
0x180003dd9  pop     rbx
0x180003dda  retn
```
