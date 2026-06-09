# CWinTaskHandler::WorkerThreadProc(void *)

- ea: `0x18000b4d0`
- end: `0x18000b53b`
- name: `?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z`
- size: `107`
- prototype: `__int64 __fastcall(_DWORD *lpThreadParameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18000b4d0`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18000b529`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18000b529`

## pseudocode

```c
__int64 __fastcall CWinTaskHandler::WorkerThreadProc(_DWORD *lpThreadParameter)
{
  int v2; // ebp
  HMODULE v3; // rsi
  __int64 v4; // rdi

  v2 = lpThreadParameter[4];
  v3 = 0;
  v4 = (*(unsigned int (__fastcall **)(_DWORD *))(*(_QWORD *)lpThreadParameter + 64LL))(lpThreadParameter);
  (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)lpThreadParameter + 6) + 32LL))(
    *((_QWORD *)lpThreadParameter + 6),
    v4);
  if ( v2 )
  {
    v3 = (HMODULE)*((_QWORD *)lpThreadParameter + 3);
    *((_QWORD *)lpThreadParameter + 3) = 0;
  }
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)lpThreadParameter + 16LL))(lpThreadParameter);
  if ( v2 )
    FreeLibraryAndExitThread(v3, v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000b4d0  push    rbx
0x18000b4d2  push    rbp
0x18000b4d3  push    rsi
0x18000b4d4  push    rdi
0x18000b4d5  sub     rsp, 28h
0x18000b4d9  mov     rax, [rcx]
0x18000b4dc  mov     rbx, rcx
0x18000b4df  mov     ebp, [rcx+10h]
0x18000b4e2  xor     esi, esi
0x18000b4e4  mov     rax, [rax+40h]
0x18000b4e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4ed  mov     rcx, [rbx+30h]
0x18000b4f1  mov     edi, eax
0x18000b4f3  mov     rdx, [rcx]
0x18000b4f6  mov     rax, [rdx+20h]
0x18000b4fa  mov     edx, edi
0x18000b4fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b501  test    ebp, ebp
0x18000b503  jz      short loc_18000B511
0x18000b505  mov     rsi, [rbx+18h]
0x18000b509  mov     qword ptr [rbx+18h], 0
0x18000b511  mov     rax, [rbx]
0x18000b514  mov     rcx, rbx
0x18000b517  mov     rax, [rax+10h]
0x18000b51b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b520  test    ebp, ebp
0x18000b522  jz      short loc_18000B530
0x18000b524  mov     edx, edi; dwExitCode
0x18000b526  mov     rcx, rsi; hLibModule
0x18000b529  call    cs:__imp_FreeLibraryAndExitThread
0x18000b52f  int     3; Trap to Debugger
0x18000b530  mov     eax, edi
0x18000b532  add     rsp, 28h
0x18000b536  pop     rdi
0x18000b537  pop     rsi
0x18000b538  pop     rbp
0x18000b539  pop     rbx
0x18000b53a  retn
```
