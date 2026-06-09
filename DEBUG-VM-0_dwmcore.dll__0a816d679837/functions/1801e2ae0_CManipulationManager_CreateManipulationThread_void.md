# CManipulationManager::CreateManipulationThread(void)

- ea: `0x1801e2ae0`
- end: `0x1801e2c03`
- name: `?CreateManipulationThread@CManipulationManager@@IEAAJXZ`
- size: `291`
- prototype: `__int64 __fastcall(CManipulationManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1801eb5cc`

## callees

- `0x180042de0`
- `0x1801e2ae0`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801e2b91`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801e2b91`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1801e2b81`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1801e2b81`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1801e2b74`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1801e2b74`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1801e2b38`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1801e2b38`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x1801e2b62`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x1801e2b62`

## string_xrefs

- `0x1801e2b58`: `DWM Manipulation Thread`

## pseudocode

```c
__int64 __fastcall CManipulationManager::CreateManipulationThread(CManipulationManager *this)
{
  int v2; // eax
  unsigned int v3; // edi
  HANDLE v4; // rax
  DWORD v5; // ecx
  int v7; // r9d
  DWORD dwCreationFlags; // [rsp+20h] [rbp-18h]
  DWORD ThreadId; // [rsp+40h] [rbp+8h] BYREF

  if ( *((_BYTE *)this + 152) )
  {
    v3 = -2147467260;
    dwCreationFlags = 919;
LABEL_10:
    v7 = v3;
    goto LABEL_7;
  }
  v2 = (*(__int64 (__fastcall **)(CManipulationManager *))(*(_QWORD *)this + 56LL))(this);
  v3 = v2;
  if ( v2 < 0 )
  {
    v7 = v2;
    dwCreationFlags = 922;
LABEL_7:
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, &dword_1803531C0, 3u, v7, dwCreationFlags, 0);
    return v3;
  }
  ThreadId = 0;
  v4 = CreateThread(0, 0, CManipulationManager::s_ThreadMain, this, 4u, &ThreadId);
  v5 = ThreadId;
  *((_QWORD *)this + 18) = v4;
  CManipulationManager::s_dwManipulationThreadId = v5;
  if ( !v4 )
  {
    v3 = -2147024882;
    dwCreationFlags = 936;
    goto LABEL_10;
  }
  SetThreadDescription(v4, L"DWM Manipulation Thread");
  SetThreadPriority(*((HANDLE *)this + 18), 16);
  ResumeThread(*((HANDLE *)this + 18));
  WaitForSingleObject(CManipulationManager::s_hManipThreadInitializedWaitEvent, 0xFFFFFFFF);
  return v3;
}

```

## disassembly

```asm
0x1801e2ae0  mov     [rsp+arg_8], rbx
0x1801e2ae5  push    rdi
0x1801e2ae6  sub     rsp, 30h
0x1801e2aea  cmp     byte ptr [rcx+98h], 0
0x1801e2af1  mov     rbx, rcx
0x1801e2af4  jnz     loc_1801E2BD0
0x1801e2afa  mov     rax, [rcx]
0x1801e2afd  mov     rax, [rax+38h]
0x1801e2b01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e2b06  mov     edi, eax
0x1801e2b08  test    eax, eax
0x1801e2b0a  js      loc_1801E2BA4
0x1801e2b10  lea     rax, [rsp+38h+ThreadId]
0x1801e2b15  mov     [rsp+38h+ThreadId], 0
0x1801e2b1d  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x1801e2b22  lea     r8, ?s_ThreadMain@CManipulationManager@@KAKPEAX@Z; lpStartAddress
0x1801e2b29  mov     r9, rbx; lpParameter
0x1801e2b2c  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x1801e2b34  xor     edx, edx; dwStackSize
0x1801e2b36  xor     ecx, ecx; lpThreadAttributes
0x1801e2b38  call    cs:__imp_CreateThread
0x1801e2b3e  mov     ecx, [rsp+38h+ThreadId]
0x1801e2b42  mov     [rbx+90h], rax
0x1801e2b49  mov     cs:?s_dwManipulationThreadId@CManipulationManager@@1KA, ecx; ulong CManipulationManager::s_dwManipulationThreadId
0x1801e2b4f  test    rax, rax
0x1801e2b52  jz      loc_1801E2BE8
0x1801e2b58  lea     rdx, aDwmManipulatio; "DWM Manipulation Thread"
0x1801e2b5f  mov     rcx, rax; hThread
0x1801e2b62  call    cs:__imp_SetThreadDescription
0x1801e2b68  mov     rcx, [rbx+90h]; hThread
0x1801e2b6f  mov     edx, 10h; nPriority
0x1801e2b74  call    cs:__imp_SetThreadPriority
0x1801e2b7a  mov     rcx, [rbx+90h]; hThread
0x1801e2b81  call    cs:__imp_ResumeThread
0x1801e2b87  mov     rcx, cs:?s_hManipThreadInitializedWaitEvent@CManipulationManager@@1PEAXEA; hHandle
0x1801e2b8e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1801e2b91  call    cs:__imp_WaitForSingleObject
0x1801e2b97  mov     rbx, [rsp+38h+arg_8]
0x1801e2b9c  mov     eax, edi
0x1801e2b9e  add     rsp, 30h
0x1801e2ba2  pop     rdi
0x1801e2ba3  retn
0x1801e2ba4  mov     [rsp+38h+lpThreadId], 0; void *
0x1801e2bad  mov     r9d, eax; int
0x1801e2bb0  mov     [rsp+38h+dwCreationFlags], 39Ah; unsigned int
0x1801e2bb8  mov     r8d, 3; unsigned int
0x1801e2bbe  lea     rdx, dword_1803531C0; int *
0x1801e2bc5  lea     ecx, [r8+11h]; unsigned int
0x1801e2bc9  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1801e2bce  jmp     short loc_1801E2B97
0x1801e2bd0  mov     [rsp+38h+lpThreadId], 0
0x1801e2bd9  mov     edi, 80004004h
0x1801e2bde  mov     [rsp+38h+dwCreationFlags], 397h
0x1801e2be6  jmp     short loc_1801E2BFE
0x1801e2be8  mov     [rsp+38h+lpThreadId], 0
0x1801e2bf1  mov     edi, 8007000Eh
0x1801e2bf6  mov     [rsp+38h+dwCreationFlags], 3A8h
0x1801e2bfe  mov     r9d, edi
0x1801e2c01  jmp     short loc_1801E2BB8
```
