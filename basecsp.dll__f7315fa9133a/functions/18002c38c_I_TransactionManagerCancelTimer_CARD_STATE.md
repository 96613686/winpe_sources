# I_TransactionManagerCancelTimer(_CARD_STATE *)

- ea: `0x18002c38c`
- end: `0x18002c406`
- name: `?I_TransactionManagerCancelTimer@@YAKPEAU_CARD_STATE@@@Z`
- size: `122`
- prototype: `unsigned int __fastcall(struct _CARD_STATE *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18002c788`
- `0x18002c858`

## callees

- `0x18002bf00`
- `0x18002bf84`
- `0x18002c38c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18002c3ab`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18002c3ab`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002c3e5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002c3e5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002c3c4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002c3c4`

## pseudocode

```c
__int64 __fastcall I_TransactionManagerCancelTimer(PTP_TIMER *a1)
{
  unsigned int v1; // ebx

  v1 = 0;
  if ( a1[75] )
  {
    do
    {
      if ( !IsThreadpoolTimerSet(a1[75]) )
        break;
      SetThreadpoolTimer(a1[75], 0, 0, 0);
      CspLeaveCriticalSection(a1 + 78);
      WaitForThreadpoolTimerCallbacks(a1[75], 1);
      v1 = CspEnterCriticalSection(a1 + 78);
    }
    while ( !v1 );
  }
  return v1;
}

```

## disassembly

```asm
0x18002c38c  mov     [rsp+arg_0], rbx
0x18002c391  push    rdi
0x18002c392  sub     rsp, 20h
0x18002c396  xor     ebx, ebx
0x18002c398  mov     rdi, rcx
0x18002c39b  cmp     [rcx+258h], rbx
0x18002c3a2  jz      short loc_18002C3F9
0x18002c3a4  mov     rcx, [rdi+258h]; pti
0x18002c3ab  call    cs:__imp_IsThreadpoolTimerSet
0x18002c3b1  test    eax, eax
0x18002c3b3  jz      short loc_18002C3F9
0x18002c3b5  mov     rcx, [rdi+258h]; pti
0x18002c3bc  xor     r9d, r9d; msWindowLength
0x18002c3bf  xor     r8d, r8d; msPeriod
0x18002c3c2  xor     edx, edx; pftDueTime
0x18002c3c4  call    cs:__imp_SetThreadpoolTimer
0x18002c3ca  lea     rbx, [rdi+270h]
0x18002c3d1  mov     rcx, rbx
0x18002c3d4  call    CspLeaveCriticalSection
0x18002c3d9  mov     rcx, [rdi+258h]; pti
0x18002c3e0  mov     edx, 1; fCancelPendingCallbacks
0x18002c3e5  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002c3eb  mov     rcx, rbx
0x18002c3ee  call    CspEnterCriticalSection
0x18002c3f3  mov     ebx, eax
0x18002c3f5  test    eax, eax
0x18002c3f7  jz      short loc_18002C3A4
0x18002c3f9  mov     eax, ebx
0x18002c3fb  mov     rbx, [rsp+28h+arg_0]
0x18002c400  add     rsp, 20h
0x18002c404  pop     rdi
0x18002c405  retn
```
