# TlgAggregateInternalProviderCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x180016810`
- end: `0x180016861`
- name: `?TlgAggregateInternalProviderCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `81`
- prototype: `void __fastcall(const struct _GUID *, int, __int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18001639c`
- `0x180016810`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x180016827`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x180016827`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016855`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016855`

## pseudocode

```c
void __fastcall TlgAggregateInternalProviderCallback(const struct _GUID *a1, int a2, __int64 a3, __int64 a4)
{
  __int64 i; // rbx

  if ( a2 == 2 && a4 == 32 && TryAcquireSRWLockExclusive(&stru_1800260D0) )
  {
    for ( i = qword_1800260D8; i; i = *(_QWORD *)(i + 336) )
      LookUpTableFlushComplete(i);
    ReleaseSRWLockExclusive(&stru_1800260D0);
  }
}

```

## disassembly

```asm
0x180016810  cmp     edx, 2
0x180016813  jnz     short locret_180016860
0x180016815  push    rbx
0x180016816  sub     rsp, 20h
0x18001681a  cmp     r9, 20h ; ' '
0x18001681e  jnz     short loc_18001685B
0x180016820  lea     rcx, stru_1800260D0; SRWLock
0x180016827  call    cs:__imp_TryAcquireSRWLockExclusive
0x18001682d  test    al, al
0x18001682f  jz      short loc_18001685B
0x180016831  mov     rbx, cs:qword_1800260D8
0x180016838  jmp     short loc_180016849
0x18001683a  mov     rcx, rbx
0x18001683d  call    LookUpTableFlushComplete
0x180016842  mov     rbx, [rbx+150h]
0x180016849  test    rbx, rbx
0x18001684c  jnz     short loc_18001683A
0x18001684e  lea     rcx, stru_1800260D0; SRWLock
0x180016855  call    cs:__imp_ReleaseSRWLockExclusive
0x18001685b  add     rsp, 20h
0x18001685f  pop     rbx
0x180016860  retn
```
