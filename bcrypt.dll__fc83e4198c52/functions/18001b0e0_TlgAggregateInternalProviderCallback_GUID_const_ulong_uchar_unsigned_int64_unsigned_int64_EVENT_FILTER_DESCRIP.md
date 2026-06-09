# TlgAggregateInternalProviderCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x18001b0e0`
- end: `0x18001b13e`
- name: `?TlgAggregateInternalProviderCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `94`
- prototype: `void __fastcall(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18001181c`
- `0x18001b0e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b12b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b12b`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x18001b0f7`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x18001b0f7`

## pseudocode

```c
void __fastcall TlgAggregateInternalProviderCallback(const struct _GUID *a1, int a2, __int64 a3, __int64 a4)
{
  __int64 i; // rbx

  if ( a2 == 2 && a4 == 32 && TryAcquireSRWLockExclusive(&SRWLock) )
  {
    for ( i = qword_180024B20; i; i = *(_QWORD *)(i + 336) )
      LookUpTableFlushComplete(i);
    ReleaseSRWLockExclusive(&SRWLock);
  }
}

```

## disassembly

```asm
0x18001b0e0  cmp     edx, 2
0x18001b0e3  jnz     short locret_18001B13C
0x18001b0e5  push    rbx
0x18001b0e6  sub     rsp, 20h
0x18001b0ea  cmp     r9, 20h ; ' '
0x18001b0ee  jnz     short loc_18001B137
0x18001b0f0  lea     rcx, SRWLock; SRWLock
0x18001b0f7  call    cs:__imp_TryAcquireSRWLockExclusive
0x18001b0fe  nop     dword ptr [rax+rax+00h]
0x18001b103  test    al, al
0x18001b105  jz      short loc_18001B137
0x18001b107  mov     rbx, cs:qword_180024B20
0x18001b10e  jmp     short loc_18001B11F
0x18001b110  mov     rcx, rbx
0x18001b113  call    LookUpTableFlushComplete
0x18001b118  mov     rbx, [rbx+150h]
0x18001b11f  test    rbx, rbx
0x18001b122  jnz     short loc_18001B110
0x18001b124  lea     rcx, SRWLock; SRWLock
0x18001b12b  call    cs:__imp_ReleaseSRWLockExclusive
0x18001b132  nop     dword ptr [rax+rax+00h]
0x18001b137  add     rsp, 20h
0x18001b13b  pop     rbx
0x18001b13c  retn
```
