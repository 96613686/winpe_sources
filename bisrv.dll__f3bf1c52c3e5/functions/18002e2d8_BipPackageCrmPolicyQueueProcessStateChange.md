# BipPackageCrmPolicyQueueProcessStateChange

- ea: `0x18002e2d8`
- end: `0x18002e4c5`
- name: `BipPackageCrmPolicyQueueProcessStateChange`
- size: `493`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180014208`
- `0x180056ff0`

## callees

- `0x18002e2d8`
- `0x18006a8d4`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002e363`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002e3c7`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002e363`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002e3c7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002e40e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002e43d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002e40e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002e43d`
- `ntdll!TpPostWork` at `0x18002e3a6`
- `ntdll!TpPostWork` at `0x18002e3a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e369`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e3cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e369`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e3cd`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002e48b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002e4a6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002e48b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002e4a6`

## pseudocode

```c
void __fastcall BipPackageCrmPolicyQueueProcessStateChange(__int64 a1)
{
  int *v1; // rsi
  int *v2; // rdi
  int *v3; // rax
  __int64 v4; // rbp
  unsigned int v5; // ebx
  DWORD CurrentThreadId; // eax
  int v7; // eax
  __int64 v8; // rcx
  int v9; // r14d
  char v10; // cl
  int v11; // ebx
  int v12; // ebx
  int *v13; // rax

  v1 = (int *)(a1 + 32);
  if ( *(int **)v1 != v1 )
  {
    v2 = 0;
    do
    {
      if ( v2 )
      {
        v3 = (int *)*((_QWORD *)v2 + 20);
        if ( v3 == v1 )
          return;
      }
      else
      {
        v3 = *(int **)v1;
      }
      v2 = v3 - 40;
    }
    while ( *(v3 - 34) < 0 );
    if ( v3 != (int *)160 )
    {
      v4 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
      do
      {
        v5 = 1 << v2[16];
        if ( *(_DWORD *)(v4 + 4) >= v5 && IsDebuggerPresent() )
          BipSyncDebugPrintLockBug((struct _BI_LOCK *)(v2 + 14));
        RtlAcquireSRWLockExclusive(v2 + 14);
        CurrentThreadId = GetCurrentThreadId();
        *(_DWORD *)(v4 + 4) |= v5;
        v2[17] = CurrentThreadId;
        v2[126] |= 8u;
        v7 = v2[126];
        *(_DWORD *)(v4 + 8) |= v5;
        if ( (v7 & 1) == 0 )
        {
          v8 = *((_QWORD *)v2 + 60);
          v2[126] = v7 | 1;
          TpPostWork(v8);
          v9 = 1 << dword_1800C4608;
          if ( *(_DWORD *)(v4 + 4) >= (unsigned int)(1 << dword_1800C4608) )
          {
            if ( IsDebuggerPresent() )
              BipSyncDebugPrintLockBug((struct _BI_LOCK *)&qword_1800C4600);
          }
          RtlAcquireSRWLockExclusive(&qword_1800C4600);
          GetCurrentThreadId();
          v10 = dword_1800C4608;
          *(_DWORD *)(v4 + 4) |= v9;
          ++dword_1800C4650;
          v11 = ~(1 << v10);
          dword_1800C460C = 0;
          *(_DWORD *)(v4 + 8) = v11 & (*(_DWORD *)(v4 + 8) | v9);
          RtlReleaseSRWLockExclusive(&qword_1800C4600);
          *(_DWORD *)(v4 + 4) &= v11;
        }
        v12 = ~(1 << v2[16]);
        v2[17] = 0;
        *(_DWORD *)(v4 + 8) &= v12;
        RtlReleaseSRWLockExclusive(v2 + 14);
        *(_DWORD *)(v4 + 4) &= v12;
        if ( *(int **)v1 == v1 )
          break;
        do
        {
          if ( v2 )
          {
            v13 = (int *)*((_QWORD *)v2 + 20);
            if ( v13 == v1 )
              return;
          }
          else
          {
            v13 = *(int **)v1;
          }
          v2 = v13 - 40;
        }
        while ( *(v13 - 34) < 0 );
      }
      while ( v13 != (int *)160 );
    }
  }
}

```

## disassembly

```asm
0x18002e2d8  push    rbx
0x18002e2da  push    rbp
0x18002e2db  push    rsi
0x18002e2dc  push    rdi
0x18002e2dd  push    r13
0x18002e2df  push    r14
0x18002e2e1  push    r15
0x18002e2e3  sub     rsp, 20h
0x18002e2e7  lea     rsi, [rcx+20h]
0x18002e2eb  cmp     [rsi], rsi
0x18002e2ee  jz      loc_18002E47C
0x18002e2f4  xor     edi, edi
0x18002e2f6  test    rdi, rdi
0x18002e2f9  jnz     short loc_18002E300
0x18002e2fb  mov     rax, [rsi]
0x18002e2fe  jmp     short loc_18002E310
0x18002e300  mov     rax, [rdi+0A0h]
0x18002e307  cmp     rax, rsi
0x18002e30a  jz      loc_18002E47C
0x18002e310  cmp     dword ptr [rax-88h], 0
0x18002e317  lea     rdi, [rax-0A0h]
0x18002e31e  jl      short loc_18002E2F6
0x18002e320  test    rdi, rdi
0x18002e323  jz      loc_18002E47C
0x18002e329  mov     ecx, cs:_tls_index
0x18002e32f  mov     r14d, 1
0x18002e335  mov     rax, gs:58h
0x18002e33e  mov     r13d, 4
0x18002e344  mov     rbp, [rax+rcx*8]
0x18002e348  lea     r15, [rdi+38h]
0x18002e34c  mov     ebx, r14d
0x18002e34f  mov     ecx, [r15+8]
0x18002e353  shl     ebx, cl
0x18002e355  cmp     [rbp+r13+0], ebx
0x18002e35a  jnb     loc_18002E48B
0x18002e360  mov     rcx, r15
0x18002e363  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18002e369  call    cs:__imp_GetCurrentThreadId
0x18002e36f  or      [rbp+r13+0], ebx
0x18002e374  mov     [r15+0Ch], eax
0x18002e378  or      dword ptr [rdi+1F8h], 8
0x18002e37f  mov     eax, [rdi+1F8h]
0x18002e385  mov     edx, 8
0x18002e38a  or      [rdx+rbp], ebx
0x18002e38d  test    r14b, al
0x18002e390  jnz     loc_18002E424
0x18002e396  mov     rcx, [rdi+1E0h]
0x18002e39d  or      eax, r14d
0x18002e3a0  mov     [rdi+1F8h], eax
0x18002e3a6  call    cs:__imp_TpPostWork
0x18002e3ac  mov     ecx, cs:dword_1800C4608
0x18002e3b2  shl     r14d, cl
0x18002e3b5  cmp     [rbp+r13+0], r14d
0x18002e3ba  jnb     loc_18002E4A6
0x18002e3c0  lea     rcx, qword_1800C4600
0x18002e3c7  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18002e3cd  call    cs:__imp_GetCurrentThreadId
0x18002e3d3  mov     ecx, cs:dword_1800C4608
0x18002e3d9  mov     ebx, 1
0x18002e3de  or      [rbp+r13+0], r14d
0x18002e3e3  inc     cs:dword_1800C4650
0x18002e3e9  mov     eax, 8
0x18002e3ee  shl     ebx, cl
0x18002e3f0  lea     rcx, qword_1800C4600
0x18002e3f7  not     ebx
0x18002e3f9  mov     cs:dword_1800C460C, 0
0x18002e403  or      r14d, [rax+rbp]
0x18002e407  and     r14d, ebx
0x18002e40a  mov     [rax+rbp], r14d
0x18002e40e  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002e414  and     [rbp+r13+0], ebx
0x18002e419  mov     r14d, 1
0x18002e41f  mov     edx, 8
0x18002e424  mov     ecx, [r15+8]
0x18002e428  mov     ebx, r14d
0x18002e42b  shl     ebx, cl
0x18002e42d  mov     rcx, r15
0x18002e430  not     ebx
0x18002e432  mov     dword ptr [r15+0Ch], 0
0x18002e43a  and     [rdx+rbp], ebx
0x18002e43d  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002e443  and     [rbp+r13+0], ebx
0x18002e448  cmp     [rsi], rsi
0x18002e44b  jz      short loc_18002E47C
0x18002e44d  test    rdi, rdi
0x18002e450  jnz     short loc_18002E457
0x18002e452  mov     rax, [rsi]
0x18002e455  jmp     short loc_18002E463
0x18002e457  mov     rax, [rdi+0A0h]
0x18002e45e  cmp     rax, rsi
0x18002e461  jz      short loc_18002E47C
0x18002e463  cmp     dword ptr [rax-88h], 0
0x18002e46a  lea     rdi, [rax-0A0h]
0x18002e471  jl      short loc_18002E44D
0x18002e473  test    rdi, rdi
0x18002e476  jnz     loc_18002E348
0x18002e47c  add     rsp, 20h
0x18002e480  pop     r15
0x18002e482  pop     r14
0x18002e484  pop     r13
0x18002e486  pop     rdi
0x18002e487  pop     rsi
0x18002e488  pop     rbp
0x18002e489  pop     rbx
0x18002e48a  retn
0x18002e48b  call    cs:__imp_IsDebuggerPresent
0x18002e491  test    eax, eax
0x18002e493  jz      loc_18002E360
0x18002e499  mov     rcx, r15; struct _BI_LOCK *
0x18002e49c  call    ?BipSyncDebugPrintLockBug@@YAXPEAU_BI_LOCK@@@Z; BipSyncDebugPrintLockBug(_BI_LOCK *)
0x18002e4a1  jmp     loc_18002E360
0x18002e4a6  call    cs:__imp_IsDebuggerPresent
0x18002e4ac  test    eax, eax
0x18002e4ae  jz      loc_18002E3C0
0x18002e4b4  lea     rcx, qword_1800C4600; struct _BI_LOCK *
0x18002e4bb  call    ?BipSyncDebugPrintLockBug@@YAXPEAU_BI_LOCK@@@Z; BipSyncDebugPrintLockBug(_BI_LOCK *)
0x18002e4c0  jmp     loc_18002E3C0
```
