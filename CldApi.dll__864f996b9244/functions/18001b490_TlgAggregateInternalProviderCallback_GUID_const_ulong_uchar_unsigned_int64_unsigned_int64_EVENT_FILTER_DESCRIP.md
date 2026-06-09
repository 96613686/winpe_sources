# TlgAggregateInternalProviderCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x18001b490`
- end: `0x18001b4e1`
- name: `?TlgAggregateInternalProviderCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `81`
- prototype: `void __fastcall(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18001b010`
- `0x18001b490`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b4d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b4d5`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x18001b4a7`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x18001b4a7`

## pseudocode

```c
void __fastcall TlgAggregateInternalProviderCallback(const struct _GUID *a1, int a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rdx
  int v5; // r8d
  int v6; // r9d
  const __m128i *i; // rbx

  if ( a2 == 2 && a4 == 32 && TryAcquireSRWLockExclusive(&SRWLock) )
  {
    for ( i = (const __m128i *)qword_180028920; i; i = (const __m128i *)i[21].m128i_i64[0] )
      LookUpTableFlushComplete(i, v4, v5, v6);
    ReleaseSRWLockExclusive(&SRWLock);
  }
}

```

## disassembly

```asm
0x18001b490  cmp     edx, 2
0x18001b493  jnz     short locret_18001B4E0
0x18001b495  push    rbx
0x18001b496  sub     rsp, 20h
0x18001b49a  cmp     r9, 20h ; ' '
0x18001b49e  jnz     short loc_18001B4DB
0x18001b4a0  lea     rcx, SRWLock; SRWLock
0x18001b4a7  call    cs:__imp_TryAcquireSRWLockExclusive
0x18001b4ad  test    al, al
0x18001b4af  jz      short loc_18001B4DB
0x18001b4b1  mov     rbx, cs:qword_180028920
0x18001b4b8  jmp     short loc_18001B4C9
0x18001b4ba  mov     rcx, rbx
0x18001b4bd  call    LookUpTableFlushComplete
0x18001b4c2  mov     rbx, [rbx+150h]
0x18001b4c9  test    rbx, rbx
0x18001b4cc  jnz     short loc_18001B4BA
0x18001b4ce  lea     rcx, SRWLock; SRWLock
0x18001b4d5  call    cs:__imp_ReleaseSRWLockExclusive
0x18001b4db  add     rsp, 20h
0x18001b4df  pop     rbx
0x18001b4e0  retn
```
