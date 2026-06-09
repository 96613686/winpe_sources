# POOL_HASH_HASH::ClearHash(POOL_HASH_HASH *)

- ea: `0x180001f10`
- end: `0x180001ff9`
- name: `?ClearHash@POOL_HASH_HASH@@SAXPEAV1@@Z`
- size: `233`
- prototype: `void __fastcall(struct POOL_HASH_HASH *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180001048`
- `0x180001f10`

## import_xrefs

- `iisutil!?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z` at `0x180001f6a`
- `iisutil!?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z` at `0x180001f6a`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x180001fa6`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x180001fa6`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001fd2`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001fd2`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x180001f35`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x180001f35`

## pseudocode

```c
void __fastcall POOL_HASH_HASH::ClearHash(struct POOL_HASH_HASH *a1)
{
  __int64 v2; // rbx
  __int64 v3; // rax
  void **v4; // rbx
  _QWORD v5[2]; // [rsp+20h] [rbp-30h] BYREF
  _QWORD v6[4]; // [rsp+30h] [rbp-20h] BYREF

  v5[1] = v5;
  v5[0] = v5;
  CLKRHashTable::Size(a1);
  v6[0] = 0;
  v6[1] = &POOL_HASH_HASH::DeletePoolHashEntriesAction;
  v6[2] = v5;
  CLKRHashTable::Apply(
    a1,
    CTypedHashTable<HASH_POOL_HASH,POOL_HASH_ENTRY,APP_POOL_HASH const *,CLKRHashTable>::_Action,
    v6,
    2);
  while ( 1 )
  {
    v2 = v5[0];
    if ( (_QWORD *)v5[0] == v5 )
      break;
    if ( *(_QWORD **)(v5[0] + 8LL) != v5 || (v3 = *(_QWORD *)v5[0], *(_QWORD *)(*(_QWORD *)v5[0] + 8LL) != v5[0]) )
      __fastfail(3u);
    v5[0] = *(_QWORD *)v5[0];
    *(_QWORD *)(v3 + 8) = v5;
    v4 = (void **)(v2 - 80);
    CLKRHashTable::DeleteRecord(a1, v4);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v4, 0xFFFFFFFF) == 1 )
    {
      if ( v4 )
      {
        operator delete(v4[8]);
        v4[8] = 0;
        STRU::~STRU((STRU *)(v4 + 1));
        operator delete(v4);
      }
    }
  }
}

```

## disassembly

```asm
0x180001f10  mov     [rsp-8+arg_0], rbx; public: static void HASH_POOL_HASH::ClearHash(class HASH_POOL_HASH *)
0x180001f15  mov     [rsp-8+arg_10], rdi
0x180001f1a  push    rbp
0x180001f1b  mov     rbp, rsp
0x180001f1e  sub     rsp, 50h
0x180001f22  lea     rax, [rbp+var_30]
0x180001f26  mov     rdi, rcx
0x180001f29  mov     [rbp+var_28], rax
0x180001f2d  lea     rax, [rbp+var_30]
0x180001f31  mov     [rbp+var_30], rax
0x180001f35  call    cs:__imp_?Size@CLKRHashTable@@QEBAKXZ; CLKRHashTable::Size(void)
0x180001f3b  lea     rax, ?DeletePoolHashEntriesAction@POOL_HASH_HASH@@SA?AW4LK_ACTION@@PEAVPOOL_HASH_ENTRY@@PEAX@Z; POOL_HASH_HASH::DeletePoolHashEntriesAction(POOL_HASH_ENTRY *,void *)
0x180001f42  mov     [rbp+var_20], 0
0x180001f4a  mov     [rbp+var_18], rax
0x180001f4e  lea     r8, [rbp+var_20]
0x180001f52  lea     rax, [rbp+var_30]
0x180001f56  mov     r9d, 2
0x180001f5c  lea     rdx, ?_Action@?$CTypedHashTable@VHASH_POOL_HASH@@VPOOL_HASH_ENTRY@@PEBUAPP_POOL_HASH@@VCLKRHashTable@@@@CA?AW4LK_ACTION@@PEBXPEAX@Z; CTypedHashTable<HASH_POOL_HASH,POOL_HASH_ENTRY,APP_POOL_HASH const *,CLKRHashTable>::_Action(void const *,void *)
0x180001f63  mov     [rbp+var_10], rax
0x180001f67  mov     rcx, rdi
0x180001f6a  call    cs:__imp_?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z; CLKRHashTable::Apply(LK_ACTION (*)(void const *,void *),void *,LK_LOCKTYPE)
0x180001f70  mov     rbx, [rbp+var_30]
0x180001f74  lea     rax, [rbp+var_30]
0x180001f78  cmp     rbx, rax
0x180001f7b  jz      short loc_180001FE9
0x180001f7d  lea     rax, [rbp+var_30]
0x180001f81  cmp     [rbx+8], rax
0x180001f85  jnz     short loc_180001FE2
0x180001f87  mov     rax, [rbx]
0x180001f8a  cmp     [rax+8], rbx
0x180001f8e  jnz     short loc_180001FE2
0x180001f90  lea     rcx, [rbp+var_30]
0x180001f94  mov     [rbp+var_30], rax
0x180001f98  mov     [rax+8], rcx
0x180001f9c  add     rbx, 0FFFFFFFFFFFFFFB0h
0x180001fa0  mov     rcx, rdi
0x180001fa3  mov     rdx, rbx
0x180001fa6  call    cs:__imp_?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z; CLKRHashTable::DeleteRecord(void const *)
0x180001fac  or      eax, 0FFFFFFFFh
0x180001faf  lock xadd [rbx], eax
0x180001fb3  cmp     eax, 1
0x180001fb6  jnz     short loc_180001F70
0x180001fb8  test    rbx, rbx
0x180001fbb  jz      short loc_180001F70
0x180001fbd  mov     rcx, [rbx+40h]; Block
0x180001fc1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001fc6  lea     rcx, [rbx+8]
0x180001fca  mov     qword ptr [rbx+40h], 0
0x180001fd2  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180001fd8  mov     rcx, rbx; Block
0x180001fdb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001fe0  jmp     short loc_180001F70
0x180001fe2  mov     ecx, 3
0x180001fe7  int     29h; Win8: RtlFailFast(ecx)
0x180001fe9  mov     rbx, [rsp+50h+arg_0]
0x180001fee  mov     rdi, [rsp+50h+arg_10]
0x180001ff3  add     rsp, 50h
0x180001ff7  pop     rbp
0x180001ff8  retn
```
