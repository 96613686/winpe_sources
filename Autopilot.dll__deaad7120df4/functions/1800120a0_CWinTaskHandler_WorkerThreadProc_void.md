# CWinTaskHandler::WorkerThreadProc(void *)

- ea: `0x1800120a0`
- end: `0x180012112`
- name: `?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z`
- size: `114`
- prototype: `__int64 __fastcall(_DWORD *Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x1800120a0`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x1800120f9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x1800120f9`

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
0x1800120a0  push    rbx
0x1800120a2  push    rbp
0x1800120a3  push    rsi
0x1800120a4  push    rdi
0x1800120a5  sub     rsp, 28h
0x1800120a9  mov     rax, [rcx]
0x1800120ac  mov     rbx, rcx
0x1800120af  mov     ebp, [rcx+10h]
0x1800120b2  xor     esi, esi
0x1800120b4  mov     rax, [rax+40h]
0x1800120b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120bd  mov     rcx, [rbx+30h]
0x1800120c1  mov     edi, eax
0x1800120c3  mov     rdx, [rcx]
0x1800120c6  mov     rax, [rdx+20h]
0x1800120ca  mov     edx, edi
0x1800120cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120d1  test    ebp, ebp
0x1800120d3  jz      short loc_1800120E1
0x1800120d5  mov     rsi, [rbx+18h]
0x1800120d9  mov     qword ptr [rbx+18h], 0
0x1800120e1  mov     rax, [rbx]
0x1800120e4  mov     rcx, rbx
0x1800120e7  mov     rax, [rax+10h]
0x1800120eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120f0  test    ebp, ebp
0x1800120f2  jz      short loc_180012106
0x1800120f4  mov     edx, edi; dwExitCode
0x1800120f6  mov     rcx, rsi; hLibModule
0x1800120f9  call    cs:__imp_FreeLibraryAndExitThread
0x180012100  nop     dword ptr [rax+rax+00h]
0x180012105  int     3; Trap to Debugger
0x180012106  mov     eax, edi
0x180012108  add     rsp, 28h
0x18001210c  pop     rdi
0x18001210d  pop     rsi
0x18001210e  pop     rbp
0x18001210f  pop     rbx
0x180012110  retn
```
