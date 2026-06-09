# BipGlobalTpActivityTimerCheckSetPeriod

- ea: `0x180012034`
- end: `0x1800121a6`
- name: `BipGlobalTpActivityTimerCheckSetPeriod`
- size: `370`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180055df0`
- `0x180055f80`
- `0x18005b600`

## callees

- `0x180012034`
- `0x1800121b0`
- `0x180013214`
- `0x18006a8d4`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001207e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180012117`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001207e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180012117`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800120f2`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180012158`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800120f2`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180012158`
- `ntdll!RtlWakeAddressAll` at `0x180012165`
- `ntdll!RtlWakeAddressAll` at `0x180012165`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012084`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001211d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012084`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001211d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180012170`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001218b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180012170`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001218b`

## pseudocode

```c
__int64 __fastcall BipGlobalTpActivityTimerCheckSetPeriod(int a1, __int64 a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rsi
  DWORD CurrentThreadId; // eax
  int *v7; // r14
  int v8; // eax
  __int64 v9; // rdx
  int v11; // eax
  unsigned int v12; // r15d
  int v13; // ebx
  unsigned int v14; // ebx
  DWORD v15; // eax
  int v16; // ebp

  v4 = 1 << *(_DWORD *)(a2 + 8);
  v5 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( *(_DWORD *)(v5 + 4) >= v4 && IsDebuggerPresent() )
    BipSyncDebugPrintLockBug((struct _BI_LOCK *)a2);
  RtlAcquireSRWLockExclusive(a2);
  CurrentThreadId = GetCurrentThreadId();
  *(_DWORD *)(v5 + 4) |= v4;
  v7 = (int *)(a2 + 64);
  *(_DWORD *)(a2 + 12) = CurrentThreadId;
  *(_DWORD *)(a2 + 64) |= 4u;
  v8 = *(_DWORD *)(a2 + 64);
  *(_DWORD *)(v5 + 8) |= v4;
  v9 = *(unsigned int *)(v5 + 8);
  if ( (v8 & 8) != 0 )
  {
    LOBYTE(v9) = 1;
    return BipSyncReleaseLock(a2, v9);
  }
  else
  {
    v11 = v8 | 8;
    v12 = a1 | 2;
    do
    {
      *v7 = v11 & 0xFFFFFFFB;
      v13 = ~(1 << *(_DWORD *)(a2 + 8));
      *(_DWORD *)(a2 + 12) = 0;
      *(_DWORD *)(v5 + 8) = v9 & v13;
      RtlReleaseSRWLockExclusive(a2);
      *(_DWORD *)(v5 + 4) &= v13;
      BipGlobalTpActivityTimerCheckRearm(v12, a2);
      v14 = 1 << *(_DWORD *)(a2 + 8);
      if ( *(_DWORD *)(v5 + 4) >= v14 )
      {
        if ( IsDebuggerPresent() )
          BipSyncDebugPrintLockBug((struct _BI_LOCK *)a2);
      }
      RtlAcquireSRWLockExclusive(a2);
      v15 = GetCurrentThreadId();
      *(_DWORD *)(v5 + 4) |= v14;
      LODWORD(v9) = *(_DWORD *)(v5 + 8) | v14;
      *(_DWORD *)(a2 + 12) = v15;
      v11 = *v7;
      *(_DWORD *)(v5 + 8) = v9;
    }
    while ( (v11 & 4) != 0 );
    *v7 = v11 & 0xFFFFFFF7;
    v16 = ~(1 << *(_DWORD *)(a2 + 8));
    *(_DWORD *)(a2 + 12) = 0;
    *(_DWORD *)(v5 + 8) = v16 & v9;
    RtlReleaseSRWLockExclusive(a2);
    *(_DWORD *)(v5 + 4) &= v16;
    return RtlWakeAddressAll(a2 + 64);
  }
}

```

## disassembly

```asm
0x180012034  push    rbx
0x180012036  push    rbp
0x180012037  push    rsi
0x180012038  push    rdi
0x180012039  push    r12
0x18001203b  push    r13
0x18001203d  push    r14
0x18001203f  push    r15
0x180012041  sub     rsp, 28h
0x180012045  mov     r8d, cs:_tls_index
0x18001204c  mov     ebp, 1
0x180012051  mov     rax, gs:58h
0x18001205a  mov     r15d, ecx
0x18001205d  mov     ecx, [rdx+8]
0x180012060  mov     ebx, ebp
0x180012062  mov     r12d, 4
0x180012068  mov     rdi, rdx
0x18001206b  shl     ebx, cl
0x18001206d  mov     rsi, [rax+r8*8]
0x180012071  cmp     [r12+rsi], ebx
0x180012075  jnb     loc_180012170
0x18001207b  mov     rcx, rdi
0x18001207e  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180012084  call    cs:__imp_GetCurrentThreadId
0x18001208a  or      [r12+rsi], ebx
0x18001208e  lea     r14, [rdi+40h]
0x180012092  mov     r13d, 8
0x180012098  mov     [rdi+0Ch], eax
0x18001209b  or      dword ptr [r14], 4
0x18001209f  mov     eax, [r14]
0x1800120a2  or      [rsi+r13], ebx
0x1800120a6  mov     edx, [rsi+r13]
0x1800120aa  test    al, 8
0x1800120ac  jz      short loc_1800120CA
0x1800120ae  mov     dl, bpl
0x1800120b1  mov     rcx, rdi
0x1800120b4  call    BipSyncReleaseLock
0x1800120b9  add     rsp, 28h
0x1800120bd  pop     r15
0x1800120bf  pop     r14
0x1800120c1  pop     r13
0x1800120c3  pop     r12
0x1800120c5  pop     rdi
0x1800120c6  pop     rsi
0x1800120c7  pop     rbp
0x1800120c8  pop     rbx
0x1800120c9  retn
0x1800120ca  or      eax, 8
0x1800120cd  or      r15d, 2
0x1800120d1  and     eax, 0FFFFFFFBh
0x1800120d4  mov     ebx, ebp
0x1800120d6  mov     [r14], eax
0x1800120d9  mov     ecx, [rdi+8]
0x1800120dc  shl     ebx, cl
0x1800120de  mov     rcx, rdi
0x1800120e1  not     ebx
0x1800120e3  mov     dword ptr [rdi+0Ch], 0
0x1800120ea  mov     eax, ebx
0x1800120ec  and     eax, edx
0x1800120ee  mov     [rsi+r13], eax
0x1800120f2  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800120f8  and     [r12+rsi], ebx
0x1800120fc  mov     rdx, rdi
0x1800120ff  mov     ecx, r15d
0x180012102  call    BipGlobalTpActivityTimerCheckRearm
0x180012107  mov     ecx, [rdi+8]
0x18001210a  mov     ebx, ebp
0x18001210c  shl     ebx, cl
0x18001210e  cmp     [r12+rsi], ebx
0x180012112  jnb     short loc_18001218B
0x180012114  mov     rcx, rdi
0x180012117  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001211d  call    cs:__imp_GetCurrentThreadId
0x180012123  or      [r12+rsi], ebx
0x180012127  mov     edx, ebx
0x180012129  or      edx, [rsi+r13]
0x18001212d  mov     [rdi+0Ch], eax
0x180012130  mov     eax, [r14]
0x180012133  mov     [rsi+r13], edx
0x180012137  test    al, 4
0x180012139  jnz     short loc_1800120D1
0x18001213b  and     eax, 0FFFFFFF7h
0x18001213e  mov     [r14], eax
0x180012141  mov     ecx, [rdi+8]
0x180012144  shl     ebp, cl
0x180012146  mov     rcx, rdi
0x180012149  not     ebp
0x18001214b  mov     dword ptr [rdi+0Ch], 0
0x180012152  and     edx, ebp
0x180012154  mov     [rsi+r13], edx
0x180012158  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18001215e  and     [r12+rsi], ebp
0x180012162  mov     rcx, r14
0x180012165  call    cs:__imp_RtlWakeAddressAll
0x18001216b  jmp     loc_1800120B9
0x180012170  call    cs:__imp_IsDebuggerPresent
0x180012176  test    eax, eax
0x180012178  jz      loc_18001207B
0x18001217e  mov     rcx, rdi; struct _BI_LOCK *
0x180012181  call    ?BipSyncDebugPrintLockBug@@YAXPEAU_BI_LOCK@@@Z; BipSyncDebugPrintLockBug(_BI_LOCK *)
0x180012186  jmp     loc_18001207B
0x18001218b  call    cs:__imp_IsDebuggerPresent
0x180012191  test    eax, eax
0x180012193  jz      loc_180012114
0x180012199  mov     rcx, rdi; struct _BI_LOCK *
0x18001219c  call    ?BipSyncDebugPrintLockBug@@YAXPEAU_BI_LOCK@@@Z; BipSyncDebugPrintLockBug(_BI_LOCK *)
0x1800121a1  jmp     loc_180012114
```
