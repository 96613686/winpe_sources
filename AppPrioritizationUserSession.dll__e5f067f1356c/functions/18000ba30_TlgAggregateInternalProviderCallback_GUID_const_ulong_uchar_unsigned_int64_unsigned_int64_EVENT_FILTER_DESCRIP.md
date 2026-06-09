# TlgAggregateInternalProviderCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x18000ba30`
- end: `0x18000ba81`
- name: `?TlgAggregateInternalProviderCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `81`
- prototype: `void __fastcall(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000b5b0`
- `0x18000ba30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x18000ba47`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x18000ba47`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ba75`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ba75`

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
    for ( i = (const __m128i *)qword_1800144C8; i; i = (const __m128i *)i[21].m128i_i64[0] )
      LookUpTableFlushComplete(i, v4, v5, v6);
    ReleaseSRWLockExclusive(&SRWLock);
  }
}

```

## disassembly

```asm
0x18000ba30  cmp     edx, 2
0x18000ba33  jnz     short locret_18000BA80
0x18000ba35  push    rbx
0x18000ba36  sub     rsp, 20h
0x18000ba3a  cmp     r9, 20h ; ' '
0x18000ba3e  jnz     short loc_18000BA7B
0x18000ba40  lea     rcx, SRWLock; SRWLock
0x18000ba47  call    cs:__imp_TryAcquireSRWLockExclusive
0x18000ba4d  test    al, al
0x18000ba4f  jz      short loc_18000BA7B
0x18000ba51  mov     rbx, cs:qword_1800144C8
0x18000ba58  jmp     short loc_18000BA69
0x18000ba5a  mov     rcx, rbx
0x18000ba5d  call    LookUpTableFlushComplete
0x18000ba62  mov     rbx, [rbx+150h]
0x18000ba69  test    rbx, rbx
0x18000ba6c  jnz     short loc_18000BA5A
0x18000ba6e  lea     rcx, SRWLock; SRWLock
0x18000ba75  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ba7b  add     rsp, 20h
0x18000ba7f  pop     rbx
0x18000ba80  retn
```
