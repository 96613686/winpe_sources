# SingleConcurrentExecution::AcquireOrBlock(void)

- ea: `0x18002090c`
- end: `0x180020987`
- name: `?AcquireOrBlock@SingleConcurrentExecution@@QEAA?AVLock@1@XZ`
- size: `123`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002f1b0`
- `0x18002f260`

## callees

- `0x18002090c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002094b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002094b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002095f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002095f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002093f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002093f`

## pseudocode

```c
__int64 __fastcall SingleConcurrentExecution::AcquireOrBlock(__int64 a1, __int64 a2)
{
  signed __int32 v4; // eax
  void *v5; // rcx
  __int64 result; // rax

  v4 = _InterlockedCompareExchange((volatile signed __int32 *)a1, 1, 0);
  v5 = *(void **)(a1 + 8);
  if ( v4 )
  {
    if ( v5 )
      WaitForSingleObject(v5, 0xFFFFFFFF);
    *(_BYTE *)(a2 + 16) = 0;
  }
  else
  {
    if ( v5 )
      ResetEvent(v5);
    else
      *(_QWORD *)(a1 + 8) = CreateEventW(0, 1, 0, 0);
    *(_BYTE *)(a2 + 16) = 1;
  }
  *(_QWORD *)(a2 + 8) = *(_QWORD *)(a1 + 8);
  result = a2;
  *(_QWORD *)a2 = a1;
  return result;
}

```

## disassembly

```asm
0x18002090c  mov     [rsp+arg_8], rbx
0x180020911  mov     [rsp+arg_10], rsi
0x180020916  push    rdi
0x180020917  sub     rsp, 20h
0x18002091b  mov     rbx, rdx
0x18002091e  mov     rdi, rcx
0x180020921  mov     esi, 1
0x180020926  xor     eax, eax
0x180020928  lock cmpxchg [rcx], esi
0x18002092c  mov     rcx, [rcx+8]; hHandle
0x180020930  jnz     short loc_180020957
0x180020932  test    rcx, rcx
0x180020935  jnz     short loc_18002094B
0x180020937  xor     r9d, r9d; lpName
0x18002093a  xor     r8d, r8d; bInitialState
0x18002093d  mov     edx, esi; bManualReset
0x18002093f  call    cs:__imp_CreateEventW
0x180020945  mov     [rdi+8], rax
0x180020949  jmp     short loc_180020951
0x18002094b  call    cs:__imp_ResetEvent
0x180020951  mov     [rbx+10h], sil
0x180020955  jmp     short loc_180020969
0x180020957  test    rcx, rcx
0x18002095a  jz      short loc_180020965
0x18002095c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002095f  call    cs:__imp_WaitForSingleObject
0x180020965  mov     byte ptr [rbx+10h], 0
0x180020969  mov     rax, [rdi+8]
0x18002096d  mov     rsi, [rsp+28h+arg_10]
0x180020972  mov     [rbx+8], rax
0x180020976  mov     rax, rbx
0x180020979  mov     [rbx], rdi
0x18002097c  mov     rbx, [rsp+28h+arg_8]
0x180020981  add     rsp, 20h
0x180020985  pop     rdi
0x180020986  retn
```
