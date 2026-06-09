# CWinTaskHandler::WorkerThreadProc(void *)

- ea: `0x18000dfb0`
- end: `0x18000e01b`
- name: `?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z`
- size: `107`
- prototype: `__int64 __fastcall(_DWORD *Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18000dfb0`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18000e009`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18000e009`

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
0x18000dfb0  push    rbx
0x18000dfb2  push    rbp
0x18000dfb3  push    rsi
0x18000dfb4  push    rdi
0x18000dfb5  sub     rsp, 28h
0x18000dfb9  mov     rax, [rcx]
0x18000dfbc  mov     rbx, rcx
0x18000dfbf  mov     ebp, [rcx+10h]
0x18000dfc2  xor     esi, esi
0x18000dfc4  mov     rax, [rax+40h]
0x18000dfc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfcd  mov     rcx, [rbx+30h]
0x18000dfd1  mov     edi, eax
0x18000dfd3  mov     rdx, [rcx]
0x18000dfd6  mov     rax, [rdx+20h]
0x18000dfda  mov     edx, edi
0x18000dfdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfe1  test    ebp, ebp
0x18000dfe3  jz      short loc_18000DFF1
0x18000dfe5  mov     rsi, [rbx+18h]
0x18000dfe9  mov     qword ptr [rbx+18h], 0
0x18000dff1  mov     rax, [rbx]
0x18000dff4  mov     rcx, rbx
0x18000dff7  mov     rax, [rax+10h]
0x18000dffb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e000  test    ebp, ebp
0x18000e002  jz      short loc_18000E010
0x18000e004  mov     edx, edi; dwExitCode
0x18000e006  mov     rcx, rsi; hLibModule
0x18000e009  call    cs:__imp_FreeLibraryAndExitThread
0x18000e00f  int     3; Trap to Debugger
0x18000e010  mov     eax, edi
0x18000e012  add     rsp, 28h
0x18000e016  pop     rdi
0x18000e017  pop     rsi
0x18000e018  pop     rbp
0x18000e019  pop     rbx
0x18000e01a  retn
```
