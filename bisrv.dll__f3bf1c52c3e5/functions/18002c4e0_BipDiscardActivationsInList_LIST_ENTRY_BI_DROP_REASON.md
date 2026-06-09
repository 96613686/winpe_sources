# BipDiscardActivationsInList(_LIST_ENTRY *,_BI_DROP_REASON)

- ea: `0x18002c4e0`
- end: `0x18002c743`
- name: `?BipDiscardActivationsInList@@YAXPEAU_LIST_ENTRY@@W4_BI_DROP_REASON@@@Z`
- size: `611`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x1800163d0`

## callees

- `0x18002c4e0`
- `0x18002c750`
- `0x18006a8d4`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002c57f`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002c5bd`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002c647`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002c57f`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002c5bd`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002c647`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002c590`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002c686`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002c6ab`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002c590`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002c686`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002c6ab`
- `ntdll!RtlFreeHeap` at `0x18002c6c8`
- `ntdll!RtlFreeHeap` at `0x18002c6c8`
- `ntdll!TpPostWork` at `0x18002c624`
- `ntdll!TpPostWork` at `0x18002c624`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c5c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c64d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c5c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c64d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002c702`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002c71d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002c702`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002c71d`

## pseudocode

```c
void __fastcall BipDiscardActivationsInList(_QWORD **a1, unsigned int a2)
{
  _QWORD *v2; // rbx
  _QWORD *v4; // r12
  _QWORD *v5; // r14
  _QWORD *v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rsi
  __int64 v9; // r12
  __int64 v10; // r13
  _DWORD *v11; // rbp
  unsigned int v12; // edi
  DWORD CurrentThreadId; // eax
  _QWORD *v14; // rdx
  int *v15; // r12
  int v16; // eax
  __int64 v17; // rcx
  int v18; // esi
  char v19; // cl
  int v20; // esi
  int v21; // edi
  int v22; // edi
  void *v23; // r8
  __int64 v24; // [rsp+60h] [rbp+8h]
  unsigned int v25; // [rsp+68h] [rbp+10h]
  _QWORD *v26; // [rsp+70h] [rbp+18h]

  v25 = a2;
  v2 = *a1;
  if ( *a1 != a1 )
  {
    v4 = (char *)NtCurrentTeb()->ThreadLocalStoragePointer + 8 * (unsigned int)tls_index;
    v26 = v4;
    while ( 1 )
    {
      v5 = (_QWORD *)*v2;
      if ( *(_QWORD **)(*v2 + 8LL) != v2 )
        break;
      v6 = (_QWORD *)v2[1];
      if ( (_QWORD *)*v6 != v2 )
        break;
      *v6 = v5;
      v5[1] = v6;
      v7 = v2[2];
      if ( v7 )
      {
        BipTraceTaskDropped(*(_QWORD *)(v7 + 64), v2[2], a2);
        v24 = v2[2];
        v8 = *(_QWORD *)(v24 + 64);
        RtlAcquireSRWLockExclusive(v24 + 48);
        *(_DWORD *)(v24 + 136) |= 0x40u;
        RtlReleaseSRWLockExclusive(v24 + 48);
        v9 = *v4;
        v10 = v8 + 56;
        v11 = (_DWORD *)(v9 + 4);
        v12 = 1 << *(_DWORD *)(v8 + 64);
        if ( *(_DWORD *)(v9 + 4) >= v12 && IsDebuggerPresent() )
          BipSyncDebugPrintLockBug((struct _BI_LOCK *)(v8 + 56));
        RtlAcquireSRWLockExclusive(v8 + 56);
        CurrentThreadId = GetCurrentThreadId();
        *v11 |= v12;
        *(_DWORD *)(v8 + 68) = CurrentThreadId;
        v14 = *(_QWORD **)(v8 + 496);
        v15 = (int *)(v9 + 8);
        *v15 |= v12;
        if ( *v14 != v8 + 488 )
          break;
        *(_QWORD *)(v24 + 96) = v8 + 488;
        *(_QWORD *)(v24 + 104) = v14;
        *v14 = v24 + 96;
        *(_QWORD *)(v8 + 496) = v24 + 96;
        v16 = *(_DWORD *)(v8 + 504);
        if ( (v16 & 1) == 0 )
        {
          v17 = *(_QWORD *)(v8 + 480);
          *(_DWORD *)(v8 + 504) = v16 | 1;
          TpPostWork(v17);
          v18 = 1 << dword_1800C4608;
          if ( *v11 >= (unsigned int)(1 << dword_1800C4608) )
          {
            if ( IsDebuggerPresent() )
              BipSyncDebugPrintLockBug((struct _BI_LOCK *)&qword_1800C4600);
          }
          RtlAcquireSRWLockExclusive(&qword_1800C4600);
          GetCurrentThreadId();
          v19 = dword_1800C4608;
          *v11 |= v18;
          v20 = *v15 | v18;
          ++dword_1800C4650;
          v21 = ~(1 << v19);
          dword_1800C460C = 0;
          *v15 = v21 & v20;
          RtlReleaseSRWLockExclusive(&qword_1800C4600);
          *v11 &= v21;
        }
        v22 = ~(1 << *(_DWORD *)(v10 + 8));
        *(_DWORD *)(v10 + 12) = 0;
        *v15 &= v22;
        RtlReleaseSRWLockExclusive(v10);
        *v11 &= v22;
        v4 = v26;
      }
      v23 = v2;
      v2 = v5;
      RtlFreeHeap(BipHeap, 0, v23);
      if ( v5 == a1 )
        return;
      a2 = v25;
    }
    __fastfail(3u);
  }
}

```

## disassembly

```asm
0x18002c4e0  mov     [rsp+arg_8], edx
0x18002c4e4  push    rbx
0x18002c4e5  push    r15
0x18002c4e7  sub     rsp, 48h
0x18002c4eb  mov     rbx, [rcx]
0x18002c4ee  mov     r15, rcx
0x18002c4f1  cmp     rbx, rcx
0x18002c4f4  jz      loc_18002C6FA
0x18002c4fa  mov     r8d, cs:_tls_index
0x18002c501  mov     rax, gs:58h
0x18002c50a  mov     [rsp+58h+var_28], r12
0x18002c50f  mov     [rsp+58h+var_38], r14
0x18002c514  mov     [rsp+58h+arg_18], rbp
0x18002c519  mov     [rsp+58h+var_18], rsi
0x18002c51e  lea     r12, [rax+r8*8]
0x18002c522  mov     [rsp+58h+var_20], rdi
0x18002c527  mov     [rsp+58h+arg_10], r12
0x18002c52c  mov     [rsp+58h+var_30], r13
0x18002c531  mov     r14, [rbx]
0x18002c534  cmp     [r14+8], rbx
0x18002c538  jnz     loc_18002C73C
0x18002c53e  mov     rax, [rbx+8]
0x18002c542  cmp     [rax], rbx
0x18002c545  jnz     loc_18002C73C
0x18002c54b  mov     [rax], r14
0x18002c54e  mov     [r14+8], rax
0x18002c552  mov     rcx, [rbx+10h]
0x18002c556  test    rcx, rcx
0x18002c559  jz      loc_18002C6B9
0x18002c55f  mov     r8d, edx
0x18002c562  mov     rdx, rcx
0x18002c565  mov     rcx, [rcx+40h]
0x18002c569  call    BipTraceTaskDropped
0x18002c56e  mov     rbp, [rbx+10h]
0x18002c572  mov     [rsp+58h+arg_0], rbp
0x18002c577  mov     rsi, [rbp+40h]
0x18002c57b  lea     rcx, [rbp+30h]
0x18002c57f  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18002c585  or      dword ptr [rbp+88h], 40h
0x18002c58c  lea     rcx, [rbp+30h]
0x18002c590  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002c596  mov     r12, [r12]
0x18002c59a  lea     r13, [rsi+38h]
0x18002c59e  mov     ecx, [r13+8]
0x18002c5a2  mov     edi, 1
0x18002c5a7  mov     ebp, 4
0x18002c5ac  add     rbp, r12
0x18002c5af  shl     edi, cl
0x18002c5b1  cmp     [rbp+0], edi
0x18002c5b4  jnb     loc_18002C702
0x18002c5ba  mov     rcx, r13
0x18002c5bd  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18002c5c3  call    cs:__imp_GetCurrentThreadId
0x18002c5c9  or      [rbp+0], edi
0x18002c5cc  lea     rcx, [rsi+1E8h]
0x18002c5d3  mov     [r13+0Ch], eax
0x18002c5d7  mov     rdx, [rsi+1F0h]
0x18002c5de  mov     eax, 8
0x18002c5e3  add     r12, rax
0x18002c5e6  or      [r12], edi
0x18002c5ea  cmp     [rdx], rcx
0x18002c5ed  jnz     loc_18002C73C
0x18002c5f3  mov     rax, [rsp+58h+arg_0]
0x18002c5f8  add     rax, 60h ; '`'
0x18002c5fc  mov     [rax], rcx
0x18002c5ff  mov     [rax+8], rdx
0x18002c603  mov     [rdx], rax
0x18002c606  mov     [rcx+8], rax
0x18002c60a  mov     eax, [rsi+1F8h]
0x18002c610  test    al, 1
0x18002c612  jnz     short loc_18002C68F
0x18002c614  mov     rcx, [rsi+1E0h]
0x18002c61b  or      eax, 1
0x18002c61e  mov     [rsi+1F8h], eax
0x18002c624  call    cs:__imp_TpPostWork
0x18002c62a  mov     ecx, cs:dword_1800C4608
0x18002c630  mov     esi, 1
0x18002c635  shl     esi, cl
0x18002c637  cmp     [rbp+0], esi
0x18002c63a  jnb     loc_18002C71D
0x18002c640  lea     rcx, qword_1800C4600
0x18002c647  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18002c64d  call    cs:__imp_GetCurrentThreadId
0x18002c653  mov     ecx, cs:dword_1800C4608
0x18002c659  mov     edi, 1
0x18002c65e  or      [rbp+0], esi
0x18002c661  or      esi, [r12]
0x18002c665  inc     cs:dword_1800C4650
0x18002c66b  shl     edi, cl
0x18002c66d  lea     rcx, qword_1800C4600
0x18002c674  not     edi
0x18002c676  mov     cs:dword_1800C460C, 0
0x18002c680  and     esi, edi
0x18002c682  mov     [r12], esi
0x18002c686  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002c68c  and     [rbp+0], edi
0x18002c68f  mov     ecx, [r13+8]
0x18002c693  mov     edi, 1
0x18002c698  shl     edi, cl
0x18002c69a  mov     rcx, r13
0x18002c69d  not     edi
0x18002c69f  mov     dword ptr [r13+0Ch], 0
0x18002c6a7  and     [r12], edi
0x18002c6ab  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002c6b1  and     [rbp+0], edi
0x18002c6b4  mov     r12, [rsp+58h+arg_10]
0x18002c6b9  mov     rcx, cs:BipHeap; HeapHandle
0x18002c6c0  mov     r8, rbx; P
0x18002c6c3  xor     edx, edx; Flags
0x18002c6c5  mov     rbx, r14
0x18002c6c8  call    cs:__imp_RtlFreeHeap
0x18002c6ce  cmp     r14, r15
0x18002c6d1  jz      short loc_18002C6DC
0x18002c6d3  mov     edx, [rsp+58h+arg_8]
0x18002c6d7  jmp     loc_18002C531
0x18002c6dc  mov     r13, [rsp+58h+var_30]
0x18002c6e1  mov     rsi, [rsp+58h+var_18]
0x18002c6e6  mov     rdi, [rsp+58h+var_20]
0x18002c6eb  mov     rbp, [rsp+58h+arg_18]
0x18002c6f0  mov     r12, [rsp+58h+var_28]
0x18002c6f5  mov     r14, [rsp+58h+var_38]
0x18002c6fa  add     rsp, 48h
0x18002c6fe  pop     r15
0x18002c700  pop     rbx
0x18002c701  retn
0x18002c702  call    cs:__imp_IsDebuggerPresent
0x18002c708  test    eax, eax
0x18002c70a  jz      loc_18002C5BA
0x18002c710  mov     rcx, r13; struct _BI_LOCK *
0x18002c713  call    ?BipSyncDebugPrintLockBug@@YAXPEAU_BI_LOCK@@@Z; BipSyncDebugPrintLockBug(_BI_LOCK *)
0x18002c718  jmp     loc_18002C5BA
0x18002c71d  call    cs:__imp_IsDebuggerPresent
0x18002c723  test    eax, eax
0x18002c725  jz      loc_18002C640
0x18002c72b  lea     rcx, qword_1800C4600; struct _BI_LOCK *
0x18002c732  call    ?BipSyncDebugPrintLockBug@@YAXPEAU_BI_LOCK@@@Z; BipSyncDebugPrintLockBug(_BI_LOCK *)
0x18002c737  jmp     loc_18002C640
0x18002c73c  mov     ecx, 3
0x18002c741  int     29h; Win8: RtlFailFast(ecx)
```
