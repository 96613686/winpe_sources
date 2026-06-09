# CActiveQueries::RemoveBrokeredQueryContext(_BrokeredQueryContext *)

- ea: `0x18000314c`
- end: `0x1800031ee`
- name: `?RemoveBrokeredQueryContext@CActiveQueries@@SAXPEAU_BrokeredQueryContext@@@Z`
- size: `162`
- prototype: `void __fastcall(struct _BrokeredQueryContext *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180002c20`
- `0x180003f80`
- `0x1800043e0`

## callees

- `0x180001214`
- `0x18000314c`
- `0x1800031f4`
- `0x180003da4`

## import_xrefs

- `msvcrt!free` at `0x180003198`
- `msvcrt!free` at `0x180003198`
- `msvcrt!free` at `0x1800031e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800031cf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800031cf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800031a5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800031a5`

## pseudocode

```c
void __fastcall CActiveQueries::RemoveBrokeredQueryContext(struct _BrokeredQueryContext *a1)
{
  __int64 v1; // rsi
  void **i; // rdi
  struct _RTL_CRITICAL_SECTION *v4; // rcx
  void *v5; // rbp
  __int64 v6; // r8
  struct _BrokeredQueryContext **v7; // rdx

  v1 = 0;
  for ( i = (void **)((char *)a1 + 8); (unsigned int)v1 < *(_DWORD *)a1; v1 = (unsigned int)(v1 + 1) )
  {
    v4 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)*i + v1);
    if ( v4 )
    {
      CQuery::Stop(v4);
      v5 = (void *)*((_QWORD *)*i + v1);
      if ( v5 )
      {
        CQuery::~CQuery(*((CQuery **)*i + v1));
        operator delete(v5);
      }
    }
  }
  free(*i);
  EnterCriticalSection(&g_csActiveQueriesList);
  v6 = *((_QWORD *)a1 + 2);
  if ( *(struct _BrokeredQueryContext **)(v6 + 8) != (struct _BrokeredQueryContext *)((char *)a1 + 16)
    || (v7 = (struct _BrokeredQueryContext **)*((_QWORD *)a1 + 3),
        *v7 != (struct _BrokeredQueryContext *)((char *)a1 + 16)) )
  {
    __fastfail(3u);
  }
  *v7 = (struct _BrokeredQueryContext *)v6;
  *(_QWORD *)(v6 + 8) = v7;
  LeaveCriticalSection(&g_csActiveQueriesList);
  free(a1);
}

```

## disassembly

```asm
0x18000314c  push    rbx
0x18000314e  push    rbp
0x18000314f  push    rsi
0x180003150  push    rdi
0x180003151  sub     rsp, 28h
0x180003155  xor     esi, esi
0x180003157  lea     rdi, [rcx+8]
0x18000315b  mov     rbx, rcx
0x18000315e  cmp     [rcx], esi
0x180003160  jbe     short loc_180003195
0x180003162  mov     rax, [rdi]
0x180003165  mov     rcx, [rax+rsi*8]; this
0x180003169  test    rcx, rcx
0x18000316c  jz      short loc_18000318F
0x18000316e  call    ?Stop@CQuery@@QEAAXXZ; CQuery::Stop(void)
0x180003173  mov     rax, [rdi]
0x180003176  mov     rbp, [rax+rsi*8]
0x18000317a  test    rbp, rbp
0x18000317d  jz      short loc_18000318F
0x18000317f  mov     rcx, rbp; this
0x180003182  call    ??1CQuery@@QEAA@XZ; CQuery::~CQuery(void)
0x180003187  mov     rcx, rbp; Block
0x18000318a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000318f  inc     esi
0x180003191  cmp     esi, [rbx]
0x180003193  jb      short loc_180003162
0x180003195  mov     rcx, [rdi]; Block
0x180003198  call    cs:__imp_free
0x18000319e  lea     rcx, ?g_csActiveQueriesList@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800031a5  call    cs:__imp_EnterCriticalSection
0x1800031ab  lea     rax, [rbx+10h]
0x1800031af  mov     r8, [rax]
0x1800031b2  cmp     [r8+8], rax
0x1800031b6  jnz     short loc_1800031E7
0x1800031b8  mov     rdx, [rax+8]
0x1800031bc  cmp     [rdx], rax
0x1800031bf  jnz     short loc_1800031E7
0x1800031c1  mov     [rdx], r8
0x1800031c4  lea     rcx, ?g_csActiveQueriesList@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800031cb  mov     [r8+8], rdx
0x1800031cf  call    cs:__imp_LeaveCriticalSection
0x1800031d5  mov     rcx, rbx
0x1800031d8  add     rsp, 28h
0x1800031dc  pop     rdi
0x1800031dd  pop     rsi
0x1800031de  pop     rbp
0x1800031df  pop     rbx
0x1800031e0  jmp     cs:__imp_free
0x1800031e7  mov     ecx, 3
0x1800031ec  int     29h; Win8: RtlFailFast(ecx)
```
