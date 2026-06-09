# CSafeThreadsInfo::ThreadProc(void *)

- ea: `0x180016b00`
- end: `0x180016b91`
- name: `?ThreadProc@CSafeThreadsInfo@@SAKPEAX@Z`
- size: `145`
- prototype: `__int64 __fastcall(_QWORD *lpThreadParameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180001e90`
- `0x180016b00`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016b4f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016b4f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180016b7f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180016b7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180016b29`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180016b29`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180016b34`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180016b34`

## pseudocode

```c
__int64 __fastcall CSafeThreadsInfo::ThreadProc(_QWORD *lpThreadParameter)
{
  __int64 v1; // rbp
  __int64 (__fastcall *v3)(__int64); // r14
  HMODULE v4; // rsi
  int v5; // edi
  HANDLE CurrentThread; // rax
  HMODULE v7; // rcx
  __int64 result; // rax

  v1 = lpThreadParameter[2];
  v3 = (__int64 (__fastcall *)(__int64))lpThreadParameter[1];
  v4 = (HMODULE)lpThreadParameter[3];
  lpThreadParameter[3] = 0;
  v5 = *((_DWORD *)lpThreadParameter + 8);
  if ( v5 )
  {
    CurrentThread = GetCurrentThread();
    SetThreadPriority(CurrentThread, v5);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)lpThreadParameter, 0xFFFFFFFF) == 1 )
  {
    v7 = (HMODULE)lpThreadParameter[3];
    if ( v7 )
    {
      FreeLibrary(v7);
      lpThreadParameter[3] = 0;
    }
    operator delete(lpThreadParameter);
  }
  result = v3(v1);
  if ( v4 )
    FreeLibraryAndExitThread(v4, result);
  return result;
}

```

## disassembly

```asm
0x180016b00  push    rbx
0x180016b02  push    rbp
0x180016b03  push    rsi
0x180016b04  push    rdi
0x180016b05  push    r14
0x180016b07  sub     rsp, 20h
0x180016b0b  mov     rbp, [rcx+10h]
0x180016b0f  mov     rbx, rcx
0x180016b12  mov     r14, [rcx+8]
0x180016b16  mov     rsi, [rcx+18h]
0x180016b1a  mov     qword ptr [rcx+18h], 0
0x180016b22  mov     edi, [rcx+20h]
0x180016b25  test    edi, edi
0x180016b27  jz      short loc_180016B3A
0x180016b29  call    cs:__imp_GetCurrentThread
0x180016b2f  mov     rcx, rax; hThread
0x180016b32  mov     edx, edi; nPriority
0x180016b34  call    cs:__imp_SetThreadPriority
0x180016b3a  or      eax, 0FFFFFFFFh
0x180016b3d  lock xadd [rbx], eax
0x180016b41  cmp     eax, 1
0x180016b44  jnz     short loc_180016B6A
0x180016b46  mov     rcx, [rbx+18h]; hLibModule
0x180016b4a  test    rcx, rcx
0x180016b4d  jz      short loc_180016B5D
0x180016b4f  call    cs:__imp_FreeLibrary
0x180016b55  mov     qword ptr [rbx+18h], 0
0x180016b5d  mov     edx, 28h ; '('; unsigned __int64
0x180016b62  mov     rcx, rbx; void *
0x180016b65  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180016b6a  mov     rcx, rbp
0x180016b6d  mov     rax, r14
0x180016b70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b75  test    rsi, rsi
0x180016b78  jz      short loc_180016B86
0x180016b7a  mov     edx, eax; dwExitCode
0x180016b7c  mov     rcx, rsi; hLibModule
0x180016b7f  call    cs:__imp_FreeLibraryAndExitThread
0x180016b85  int     3; Trap to Debugger
0x180016b86  add     rsp, 20h
0x180016b8a  pop     r14
0x180016b8c  pop     rdi
0x180016b8d  pop     rsi
0x180016b8e  pop     rbp
0x180016b8f  pop     rbx
0x180016b90  retn
```
