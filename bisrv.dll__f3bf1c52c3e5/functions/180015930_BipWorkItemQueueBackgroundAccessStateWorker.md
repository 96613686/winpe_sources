# BipWorkItemQueueBackgroundAccessStateWorker

- ea: `0x180015930`
- end: `0x180015a99`
- name: `BipWorkItemQueueBackgroundAccessStateWorker`
- size: `361`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008598`
- `0x180015198`

## callees

- `0x180015930`
- `0x18006a8d4`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001597e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800159ee`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001597e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800159ee`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180015a28`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180015a44`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180015a28`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180015a44`
- `ntdll!TpPostWork` at `0x1800159cd`
- `ntdll!TpPostWork` at `0x1800159cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015984`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800159f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015984`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800159f4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180015a5f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180015a7a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180015a5f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180015a7a`

## pseudocode

```c
__int64 __fastcall BipWorkItemQueueBackgroundAccessStateWorker(__int64 a1, char a2)
{
  __int64 v2; // rbp
  unsigned int v4; // esi
  __int64 v6; // r14
  DWORD CurrentThreadId; // eax
  int v8; // eax
  __int64 v9; // rcx
  int v10; // esi
  char v11; // cl
  int v12; // esi
  int v13; // edi
  int v14; // ebx
  __int64 result; // rax

  v2 = a1 + 56;
  v4 = 1 << *(_DWORD *)(a1 + 64);
  v6 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( *(_DWORD *)(v6 + 4) >= v4 && IsDebuggerPresent() )
    BipSyncDebugPrintLockBug((struct _BI_LOCK *)v2);
  RtlAcquireSRWLockExclusive(v2);
  CurrentThreadId = GetCurrentThreadId();
  *(_DWORD *)(v6 + 4) |= v4;
  *(_DWORD *)(v2 + 12) = CurrentThreadId;
  *(_DWORD *)(a1 + 504) |= 0x10u;
  v8 = *(_DWORD *)(a1 + 504);
  *(_DWORD *)(v6 + 8) |= v4;
  if ( (a2 & 1) != 0 )
  {
    v8 |= 0x200u;
    *(_DWORD *)(a1 + 504) = v8;
  }
  if ( (v8 & 1) == 0 )
  {
    v9 = *(_QWORD *)(a1 + 480);
    *(_DWORD *)(a1 + 504) = v8 | 1;
    TpPostWork(v9);
    v10 = 1 << dword_1800C4608;
    if ( *(_DWORD *)(v6 + 4) >= (unsigned int)(1 << dword_1800C4608) && IsDebuggerPresent() )
      BipSyncDebugPrintLockBug((struct _BI_LOCK *)&qword_1800C4600);
    RtlAcquireSRWLockExclusive(&qword_1800C4600);
    GetCurrentThreadId();
    v11 = dword_1800C4608;
    *(_DWORD *)(v6 + 4) |= v10;
    v12 = *(_DWORD *)(v6 + 8) | v10;
    ++dword_1800C4650;
    v13 = ~(1 << v11);
    dword_1800C460C = 0;
    *(_DWORD *)(v6 + 8) = v13 & v12;
    RtlReleaseSRWLockExclusive(&qword_1800C4600);
    *(_DWORD *)(v6 + 4) &= v13;
  }
  v14 = ~(1 << *(_DWORD *)(v2 + 8));
  *(_DWORD *)(v2 + 12) = 0;
  *(_DWORD *)(v6 + 8) &= v14;
  result = RtlReleaseSRWLockExclusive(v2);
  *(_DWORD *)(v6 + 4) &= v14;
  return result;
}

```

## disassembly

```asm
0x180015930  push    rbx
0x180015932  push    rbp
0x180015933  push    rsi
0x180015934  push    rdi
0x180015935  push    r12
0x180015937  push    r13
0x180015939  push    r14
0x18001593b  push    r15
0x18001593d  sub     rsp, 28h
0x180015941  mov     r8d, cs:_tls_index
0x180015948  lea     rbp, [rcx+38h]
0x18001594c  mov     rax, gs:58h
0x180015955  mov     ebx, 1
0x18001595a  mov     r12d, 4
0x180015960  mov     rdi, rcx
0x180015963  mov     ecx, [rbp+8]
0x180015966  mov     esi, ebx
0x180015968  shl     esi, cl
0x18001596a  mov     r15d, edx
0x18001596d  mov     r14, [rax+r8*8]
0x180015971  cmp     [r12+r14], esi
0x180015975  jnb     loc_180015A5F
0x18001597b  mov     rcx, rbp
0x18001597e  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180015984  call    cs:__imp_GetCurrentThreadId
0x18001598a  or      [r12+r14], esi
0x18001598e  mov     [rbp+0Ch], eax
0x180015991  or      dword ptr [rdi+1F8h], 10h
0x180015998  mov     eax, [rdi+1F8h]
0x18001599e  mov     r13d, 8
0x1800159a4  or      [r14+r13], esi
0x1800159a8  test    bl, r15b
0x1800159ab  jz      short loc_1800159B7
0x1800159ad  bts     eax, 9
0x1800159b1  mov     [rdi+1F8h], eax
0x1800159b7  xor     r15d, r15d
0x1800159ba  test    bl, al
0x1800159bc  jnz     short loc_180015A32
0x1800159be  mov     rcx, [rdi+1E0h]
0x1800159c5  or      eax, ebx
0x1800159c7  mov     [rdi+1F8h], eax
0x1800159cd  call    cs:__imp_TpPostWork
0x1800159d3  mov     ecx, cs:dword_1800C4608
0x1800159d9  mov     esi, ebx
0x1800159db  shl     esi, cl
0x1800159dd  cmp     [r12+r14], esi
0x1800159e1  jnb     loc_180015A7A
0x1800159e7  lea     rcx, qword_1800C4600
0x1800159ee  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800159f4  call    cs:__imp_GetCurrentThreadId
0x1800159fa  mov     ecx, cs:dword_1800C4608
0x180015a00  mov     edi, ebx
0x180015a02  or      [r12+r14], esi
0x180015a06  or      esi, [r14+r13]
0x180015a0a  inc     cs:dword_1800C4650
0x180015a10  shl     edi, cl
0x180015a12  lea     rcx, qword_1800C4600
0x180015a19  not     edi
0x180015a1b  mov     cs:dword_1800C460C, r15d
0x180015a22  and     esi, edi
0x180015a24  mov     [r14+r13], esi
0x180015a28  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180015a2e  and     [r12+r14], edi
0x180015a32  mov     ecx, [rbp+8]
0x180015a35  shl     ebx, cl
0x180015a37  mov     rcx, rbp
0x180015a3a  not     ebx
0x180015a3c  mov     [rbp+0Ch], r15d
0x180015a40  and     [r14+r13], ebx
0x180015a44  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180015a4a  and     [r12+r14], ebx
0x180015a4e  add     rsp, 28h
0x180015a52  pop     r15
0x180015a54  pop     r14
0x180015a56  pop     r13
0x180015a58  pop     r12
0x180015a5a  pop     rdi
0x180015a5b  pop     rsi
0x180015a5c  pop     rbp
0x180015a5d  pop     rbx
0x180015a5e  retn
0x180015a5f  call    cs:__imp_IsDebuggerPresent
0x180015a65  test    eax, eax
0x180015a67  jz      loc_18001597B
0x180015a6d  mov     rcx, rbp; struct _BI_LOCK *
0x180015a70  call    ?BipSyncDebugPrintLockBug@@YAXPEAU_BI_LOCK@@@Z; BipSyncDebugPrintLockBug(_BI_LOCK *)
0x180015a75  jmp     loc_18001597B
0x180015a7a  call    cs:__imp_IsDebuggerPresent
0x180015a80  test    eax, eax
0x180015a82  jz      loc_1800159E7
0x180015a88  lea     rcx, qword_1800C4600; struct _BI_LOCK *
0x180015a8f  call    ?BipSyncDebugPrintLockBug@@YAXPEAU_BI_LOCK@@@Z; BipSyncDebugPrintLockBug(_BI_LOCK *)
0x180015a94  jmp     loc_1800159E7
```
