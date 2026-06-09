# GameInputServer::WorkerThreadProcThunk(void *)

- ea: `0x180042f80`
- end: `0x180042fb6`
- name: `?WorkerThreadProcThunk@GameInputServer@@CAKPEAX@Z`
- size: `54`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180042b60`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180042f9d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180042f9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180042f89`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180042f89`

## pseudocode

```c
__int64 __fastcall GameInputServer::WorkerThreadProcThunk(GameInputServer *Parameter)
{
  HANDLE CurrentThread; // rax

  CurrentThread = GetCurrentThread();
  SetThreadPriority(CurrentThread, 1);
  return GameInputServer::WorkerThreadProc(Parameter);
}

```

## disassembly

```asm
0x180042f80  push    rbx
0x180042f82  sub     rsp, 20h
0x180042f86  mov     rbx, rcx
0x180042f89  call    cs:__imp_GetCurrentThread
0x180042f90  nop     dword ptr [rax+rax+00h]
0x180042f95  mov     rcx, rax; hThread
0x180042f98  mov     edx, 1; nPriority
0x180042f9d  call    cs:__imp_SetThreadPriority
0x180042fa4  nop     dword ptr [rax+rax+00h]
0x180042fa9  mov     rcx, rbx; this
0x180042fac  add     rsp, 20h
0x180042fb0  pop     rbx
0x180042fb1  jmp     ?WorkerThreadProc@GameInputServer@@AEAAJXZ; GameInputServer::WorkerThreadProc(void)
```
