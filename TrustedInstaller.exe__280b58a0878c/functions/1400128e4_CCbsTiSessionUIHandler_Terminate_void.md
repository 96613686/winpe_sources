# CCbsTiSessionUIHandler::Terminate(void)

- ea: `0x1400128e4`
- end: `0x140012a51`
- name: `?Terminate@CCbsTiSessionUIHandler@@UEAAJXZ`
- size: `365`
- prototype: `__int64 __fastcall(CCbsTiSessionUIHandler *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x1400128d0`

## callees

- `0x140011bc8`
- `0x1400128e4`
- `0x140017658`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012954`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400129da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012954`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400129da`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140012942`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400129cc`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140012942`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400129cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140012a20`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140012a20`

## string_xrefs

- `0x140012969`: `Exec: Failed to create the thread to resume multi-phase installation.`
- `0x1400129ef`: `Exec: Failed to create the thread to terminate TiWorker..`

## pseudocode

```c
__int64 __fastcall CCbsTiSessionUIHandler::Terminate(CCbsTiSessionUIHandler *this)
{
  unsigned int v1; // ebx
  CCbsTiSession *v3; // rcx
  HANDLE Thread; // rsi
  signed int LastError; // eax
  const char *v6; // r9
  CCbsTiSession *v7; // rcx
  signed int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // rcx

  v1 = 0;
  if ( *((_DWORD *)this - 8) == 985139 )
  {
    *((_DWORD *)this - 5) = *((_DWORD *)this - 7);
    *((_DWORD *)this - 4) = *((_DWORD *)this - 6);
    *((_DWORD *)this - 3) = 1;
    v3 = (CCbsTiSession *)*((_QWORD *)this - 5);
    if ( !*((_DWORD *)v3 + 28) )
      return v1;
    CCbsTiSession::ReleaseWorkerSessionAfterServicingStackUpdate(v3);
    Thread = CreateThread(0, 0, SessionTerminateOrResumeThreadProc, *((LPVOID *)this - 5), 0, 0);
    if ( !Thread )
    {
      LastError = GetLastError();
      v1 = LastError;
      if ( LastError > 0 )
        v1 = (unsigned __int16)LastError | 0x80070000;
      v6 = "Exec: Failed to create the thread to resume multi-phase installation.";
LABEL_7:
      if ( (v1 & 0x80000000) == 0 )
        v1 = -2147467259;
      CBSWdsLogLight(0x4000000u, v1, (size_t *)1, v6);
      return v1;
    }
LABEL_19:
    if ( Thread != (HANDLE)-1LL )
      CloseHandle(Thread);
    return v1;
  }
  if ( *((_DWORD *)this - 8) == 985091 )
  {
    *((_DWORD *)this - 3) = 1;
    Thread = 0;
    v7 = (CCbsTiSession *)*((_QWORD *)this - 5);
    if ( *((_DWORD *)v7 + 28) )
    {
      CCbsTiSession::ReleaseWorkerSessionAfterServicingStackUpdate(v7);
      Thread = CreateThread(0, 0, SessionTerminateOrResumeThreadProc, 0, 0, 0);
      if ( !Thread )
      {
        v8 = GetLastError();
        v1 = v8;
        if ( v8 > 0 )
          v1 = (unsigned __int16)v8 | 0x80070000;
        v6 = "Exec: Failed to create the thread to terminate TiWorker..";
        goto LABEL_7;
      }
    }
    v9 = *((_QWORD *)this - 7);
    if ( v9 )
      v1 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 32LL))(v9);
    if ( Thread )
      goto LABEL_19;
  }
  else
  {
    v10 = *((_QWORD *)this - 7);
    if ( v10 )
      return (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v10 + 32LL))(v10);
  }
  return v1;
}

```

## disassembly

```asm
0x1400128e4  mov     [rsp+arg_0], rbx
0x1400128e9  mov     [rsp+arg_8], rsi
0x1400128ee  push    rdi
0x1400128ef  sub     rsp, 30h
0x1400128f3  xor     ebx, ebx
0x1400128f5  mov     rdi, rcx
0x1400128f8  cmp     dword ptr [rcx-20h], 0F0833h
0x1400128ff  jnz     loc_140012991
0x140012905  mov     eax, [rcx-1Ch]
0x140012908  mov     [rcx-14h], eax
0x14001290b  mov     eax, [rcx-18h]
0x14001290e  mov     [rcx-10h], eax
0x140012911  mov     dword ptr [rcx-0Ch], 1
0x140012918  mov     rcx, [rcx-28h]; this
0x14001291c  cmp     [rcx+70h], ebx
0x14001291f  jz      loc_140012A3F
0x140012925  call    ?ReleaseWorkerSessionAfterServicingStackUpdate@CCbsTiSession@@QEAAXXZ; CCbsTiSession::ReleaseWorkerSessionAfterServicingStackUpdate(void)
0x14001292a  mov     r9, [rdi-28h]; lpParameter
0x14001292e  lea     r8, ?SessionTerminateOrResumeThreadProc@@YAKPEAX@Z; lpStartAddress
0x140012935  xor     edx, edx; dwStackSize
0x140012937  mov     [rsp+38h+lpThreadId], rbx; lpThreadId
0x14001293c  xor     ecx, ecx; lpThreadAttributes
0x14001293e  mov     [rsp+38h+dwCreationFlags], ebx; dwCreationFlags
0x140012942  call    cs:__imp_CreateThread
0x140012948  mov     rsi, rax
0x14001294b  test    rax, rax
0x14001294e  jnz     loc_140012A17
0x140012954  call    cs:__imp_GetLastError
0x14001295a  mov     ebx, eax
0x14001295c  test    eax, eax
0x14001295e  jle     short loc_140012969
0x140012960  movzx   ebx, ax
0x140012963  or      ebx, 80070000h
0x140012969  lea     r9, aExecFailedToCr_0; "Exec: Failed to create the thread to re"...
0x140012970  test    ebx, ebx
0x140012972  mov     eax, 80004005h
0x140012977  mov     r8d, 1
0x14001297d  mov     ecx, 4000000h
0x140012982  cmovns  ebx, eax
0x140012985  mov     edx, ebx
0x140012987  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14001298c  jmp     loc_140012A3F
0x140012991  cmp     dword ptr [rcx-20h], 0F0803h
0x140012998  jnz     loc_140012A28
0x14001299e  mov     dword ptr [rcx-0Ch], 1
0x1400129a5  xor     esi, esi
0x1400129a7  mov     rcx, [rcx-28h]; this
0x1400129ab  cmp     [rcx+70h], ebx
0x1400129ae  jz      short loc_1400129FB
0x1400129b0  call    ?ReleaseWorkerSessionAfterServicingStackUpdate@CCbsTiSession@@QEAAXXZ; CCbsTiSession::ReleaseWorkerSessionAfterServicingStackUpdate(void)
0x1400129b5  xor     r9d, r9d; lpParameter
0x1400129b8  mov     [rsp+38h+lpThreadId], rbx; lpThreadId
0x1400129bd  lea     r8, ?SessionTerminateOrResumeThreadProc@@YAKPEAX@Z; lpStartAddress
0x1400129c4  mov     [rsp+38h+dwCreationFlags], ebx; dwCreationFlags
0x1400129c8  xor     edx, edx; dwStackSize
0x1400129ca  xor     ecx, ecx; lpThreadAttributes
0x1400129cc  call    cs:__imp_CreateThread
0x1400129d2  mov     rsi, rax
0x1400129d5  test    rax, rax
0x1400129d8  jnz     short loc_1400129FB
0x1400129da  call    cs:__imp_GetLastError
0x1400129e0  mov     ebx, eax
0x1400129e2  test    eax, eax
0x1400129e4  jle     short loc_1400129EF
0x1400129e6  movzx   ebx, ax
0x1400129e9  or      ebx, 80070000h
0x1400129ef  lea     r9, aExecFailedToCr; "Exec: Failed to create the thread to te"...
0x1400129f6  jmp     loc_140012970
0x1400129fb  mov     rcx, [rdi-38h]
0x1400129ff  test    rcx, rcx
0x140012a02  jz      short loc_140012A12
0x140012a04  mov     rax, [rcx]
0x140012a07  mov     rax, [rax+20h]
0x140012a0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012a10  mov     ebx, eax
0x140012a12  test    rsi, rsi
0x140012a15  jz      short loc_140012A3F
0x140012a17  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140012a1b  jz      short loc_140012A3F
0x140012a1d  mov     rcx, rsi; hObject
0x140012a20  call    cs:__imp_CloseHandle
0x140012a26  jmp     short loc_140012A3F
0x140012a28  mov     rcx, [rcx-38h]
0x140012a2c  test    rcx, rcx
0x140012a2f  jz      short loc_140012A3F
0x140012a31  mov     rax, [rcx]
0x140012a34  mov     rax, [rax+20h]
0x140012a38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012a3d  mov     ebx, eax
0x140012a3f  mov     rsi, [rsp+38h+arg_8]
0x140012a44  mov     eax, ebx
0x140012a46  mov     rbx, [rsp+38h+arg_0]
0x140012a4b  add     rsp, 30h
0x140012a4f  pop     rdi
0x140012a50  retn
```
