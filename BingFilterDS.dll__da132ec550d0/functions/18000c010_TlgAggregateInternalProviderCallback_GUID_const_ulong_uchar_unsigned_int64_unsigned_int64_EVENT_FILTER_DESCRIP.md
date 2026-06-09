# TlgAggregateInternalProviderCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x18000c010`
- end: `0x18000c061`
- name: `?TlgAggregateInternalProviderCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `81`
- prototype: `void __fastcall(const struct _GUID *, int, __int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000bb9c`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x18000c027`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x18000c027`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c055`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c055`

## pseudocode

```c
void __fastcall TlgAggregateInternalProviderCallback(const struct _GUID *a1, int a2, __int64 a3, __int64 a4)
{
  __int64 i; // rbx

  if ( a2 == 2 && a4 == 32 && TryAcquireSRWLockExclusive(&stru_180015B50) )
  {
    for ( i = qword_180015B58; i; i = *(_QWORD *)(i + 336) )
      LookUpTableFlushComplete(i);
    ReleaseSRWLockExclusive(&stru_180015B50);
  }
}

```

## disassembly

```asm
0x18000c010  cmp     edx, 2
0x18000c013  jnz     short locret_18000C060
0x18000c015  push    rbx
0x18000c016  sub     rsp, 20h
0x18000c01a  cmp     r9, 20h ; ' '
0x18000c01e  jnz     short loc_18000C05B
0x18000c020  lea     rcx, stru_180015B50; SRWLock
0x18000c027  call    cs:__imp_TryAcquireSRWLockExclusive
0x18000c02d  test    al, al
0x18000c02f  jz      short loc_18000C05B
0x18000c031  mov     rbx, cs:qword_180015B58
0x18000c038  jmp     short loc_18000C049
0x18000c03a  mov     rcx, rbx
0x18000c03d  call    LookUpTableFlushComplete
0x18000c042  mov     rbx, [rbx+150h]
0x18000c049  test    rbx, rbx
0x18000c04c  jnz     short loc_18000C03A
0x18000c04e  lea     rcx, stru_180015B50; SRWLock
0x18000c055  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c05b  add     rsp, 20h
0x18000c05f  pop     rbx
0x18000c060  retn
```
