# CWinTaskHandler::WorkerThreadProc(void *)

- ea: `0x180002cc0`
- end: `0x180002d2b`
- name: `?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z`
- size: `107`
- prototype: `__int64 __fastcall(_DWORD *Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180002cc0`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180002d19`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180002d19`

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
0x180002cc0  push    rbx
0x180002cc2  push    rbp
0x180002cc3  push    rsi
0x180002cc4  push    rdi
0x180002cc5  sub     rsp, 28h
0x180002cc9  mov     rax, [rcx]
0x180002ccc  mov     rbx, rcx
0x180002ccf  mov     ebp, [rcx+10h]
0x180002cd2  xor     esi, esi
0x180002cd4  mov     rax, [rax+40h]
0x180002cd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cdd  mov     rcx, [rbx+30h]
0x180002ce1  mov     edi, eax
0x180002ce3  mov     rdx, [rcx]
0x180002ce6  mov     rax, [rdx+20h]
0x180002cea  mov     edx, edi
0x180002cec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cf1  test    ebp, ebp
0x180002cf3  jz      short loc_180002D01
0x180002cf5  mov     rsi, [rbx+18h]
0x180002cf9  mov     qword ptr [rbx+18h], 0
0x180002d01  mov     rax, [rbx]
0x180002d04  mov     rcx, rbx
0x180002d07  mov     rax, [rax+10h]
0x180002d0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d10  test    ebp, ebp
0x180002d12  jz      short loc_180002D20
0x180002d14  mov     edx, edi; dwExitCode
0x180002d16  mov     rcx, rsi; hLibModule
0x180002d19  call    cs:__imp_FreeLibraryAndExitThread
0x180002d1f  int     3; Trap to Debugger
0x180002d20  mov     eax, edi
0x180002d22  add     rsp, 28h
0x180002d26  pop     rdi
0x180002d27  pop     rsi
0x180002d28  pop     rbp
0x180002d29  pop     rbx
0x180002d2a  retn
```
