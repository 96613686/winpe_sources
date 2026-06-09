# BipEnergyBudgetUpdateEnergyQuotasOnWorkerThread

- ea: `0x18000638c`
- end: `0x1800064c4`
- name: `BipEnergyBudgetUpdateEnergyQuotasOnWorkerThread`
- size: `312`
- prototype: `__int64 __fastcall(struct _BI_LOCK *)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180004b10`
- `0x1800061c0`
- `0x1800553b0`
- `0x180055f80`
- `0x180062998`
- `0x180081820`

## callees

- `0x18000638c`
- `0x18006a8d4`

## import_xrefs

- `ntdll!TpAllocTimer` at `0x1800064b2`
- `ntdll!TpAllocTimer` at `0x1800064b2`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800063d9`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800063d9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000641c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000641c`
- `ntdll!TpSetTimer` at `0x18000647f`
- `ntdll!TpSetTimer` at `0x18000647f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800063df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800063df`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006487`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006487`

## pseudocode

```c
__int64 __fastcall BipEnergyBudgetUpdateEnergyQuotasOnWorkerThread(struct _BI_LOCK *a1)
{
  _QWORD *ThreadLocalStoragePointer; // rax
  int v3; // ecx
  __int64 v4; // rdi
  int v5; // esi
  DWORD CurrentThreadId; // eax
  char v7; // al
  int v8; // esi
  int v9; // ebp
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // [rsp+70h] [rbp+8h] BYREF

  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  v3 = *((_DWORD *)a1 + 2);
  v13 = 0;
  v4 = ThreadLocalStoragePointer[(unsigned int)tls_index];
  v5 = 1 << v3;
  if ( *(_DWORD *)(v4 + 4) >= (unsigned int)(1 << v3) && IsDebuggerPresent() )
    BipSyncDebugPrintLockBug(a1);
  RtlAcquireSRWLockExclusive(a1);
  CurrentThreadId = GetCurrentThreadId();
  *(_DWORD *)(v4 + 4) |= v5;
  *((_DWORD *)a1 + 3) = CurrentThreadId;
  v7 = *((_BYTE *)a1 + 176);
  *(_DWORD *)(v4 + 8) |= v5;
  if ( (v7 & 4) != 0
    || !*((_WORD *)a1 + 16)
    || !*((_WORD *)a1 + 17)
    || *((_WORD *)a1 + 18) >= 0x64u
    || (v7 & 0x40) != 0
    || (v7 & 2) != 0 )
  {
    goto LABEL_4;
  }
  if ( *((_QWORD *)a1 + 8)
    || (v8 = TpAllocTimer((char *)a1 + 64, &BipEnergyQuotaUpdateQuotasTimerCallback, a1, 0), v8 >= 0) )
  {
    v11 = *((unsigned int *)a1 + 18);
    *((_BYTE *)a1 + 176) |= 2u;
    v12 = *((_QWORD *)a1 + 8);
    v13 = -10000 * v11;
    TpSetTimer(v12, &v13, 0, 1000);
LABEL_4:
    v8 = 0;
  }
  v9 = ~(1 << *((_DWORD *)a1 + 2));
  *((_DWORD *)a1 + 3) = 0;
  *(_DWORD *)(v4 + 8) &= v9;
  RtlReleaseSRWLockExclusive(a1);
  *(_DWORD *)(v4 + 4) &= v9;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000638c  push    rbx
0x18000638e  push    rbp
0x18000638f  push    rsi
0x180006390  push    rdi
0x180006391  push    r12
0x180006393  push    r13
0x180006395  push    r14
0x180006397  push    r15
0x180006399  sub     rsp, 28h
0x18000639d  mov     edx, cs:_tls_index
0x1800063a3  xor     r15d, r15d
0x1800063a6  mov     rax, gs:58h
0x1800063af  mov     rbx, rcx
0x1800063b2  mov     ecx, [rcx+8]
0x1800063b5  mov     r12d, 4
0x1800063bb  lea     ebp, [r15+1]
0x1800063bf  mov     [rsp+68h+arg_0], r15
0x1800063c4  mov     rdi, [rax+rdx*8]
0x1800063c8  mov     esi, ebp
0x1800063ca  shl     esi, cl
0x1800063cc  cmp     [r12+rdi], esi
0x1800063d0  jnb     loc_180006487
0x1800063d6  mov     rcx, rbx
0x1800063d9  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800063df  call    cs:__imp_GetCurrentThreadId
0x1800063e5  or      [r12+rdi], esi
0x1800063e9  mov     r13d, 8
0x1800063ef  mov     [rbx+0Ch], eax
0x1800063f2  mov     al, [rbx+0B0h]
0x1800063f8  or      [rdi+r13], esi
0x1800063fc  test    al, 4
0x1800063fe  jnz     short loc_180006407
0x180006400  cmp     [rbx+20h], r15w
0x180006405  jnz     short loc_180006439
0x180006407  mov     esi, r15d
0x18000640a  mov     ecx, [rbx+8]
0x18000640d  shl     ebp, cl
0x18000640f  mov     rcx, rbx
0x180006412  not     ebp
0x180006414  mov     [rbx+0Ch], r15d
0x180006418  and     [rdi+r13], ebp
0x18000641c  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180006422  and     [r12+rdi], ebp
0x180006426  mov     eax, esi
0x180006428  add     rsp, 28h
0x18000642c  pop     r15
0x18000642e  pop     r14
0x180006430  pop     r13
0x180006432  pop     r12
0x180006434  pop     rdi
0x180006435  pop     rsi
0x180006436  pop     rbp
0x180006437  pop     rbx
0x180006438  retn
0x180006439  cmp     [rbx+22h], r15w
0x18000643e  jz      short loc_180006407
0x180006440  cmp     word ptr [rbx+24h], 64h ; 'd'
0x180006445  jnb     short loc_180006407
0x180006447  test    al, 40h
0x180006449  jnz     short loc_180006407
0x18000644b  test    al, 2
0x18000644d  jnz     short loc_180006407
0x18000644f  lea     r14, [rbx+40h]
0x180006453  cmp     [r14], r15
0x180006456  jz      short loc_1800064A2
0x180006458  mov     eax, [rbx+48h]
0x18000645b  mov     r9d, 3E8h
0x180006461  or      byte ptr [rbx+0B0h], 2
0x180006468  xor     r8d, r8d
0x18000646b  mov     rcx, [r14]
0x18000646e  imul    rdx, rax, 0FFFFFFFFFFFFD8F0h
0x180006475  mov     [rsp+68h+arg_0], rdx
0x18000647a  lea     rdx, [rsp+68h+arg_0]
0x18000647f  call    cs:__imp_TpSetTimer
0x180006485  jmp     short loc_180006407
0x180006487  call    cs:__imp_IsDebuggerPresent
0x18000648d  test    eax, eax
0x18000648f  jz      loc_1800063D6
0x180006495  mov     rcx, rbx; struct _BI_LOCK *
0x180006498  call    ?BipSyncDebugPrintLockBug@@YAXPEAU_BI_LOCK@@@Z; BipSyncDebugPrintLockBug(_BI_LOCK *)
0x18000649d  jmp     loc_1800063D6
0x1800064a2  xor     r9d, r9d
0x1800064a5  lea     rdx, BipEnergyQuotaUpdateQuotasTimerCallback
0x1800064ac  mov     r8, rbx
0x1800064af  mov     rcx, r14
0x1800064b2  call    cs:__imp_TpAllocTimer
0x1800064b8  mov     esi, eax
0x1800064ba  test    eax, eax
0x1800064bc  js      loc_18000640A
0x1800064c2  jmp     short loc_180006458
```
