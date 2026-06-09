# IndexHashFastEnum

- ea: `0x14001d86c`
- end: `0x14001d9d5`
- name: `IndexHashFastEnum`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14001d6b0`

## callees

- `0x140004bf0`
- `0x140009520`
- `0x14001d460`
- `0x14001d86c`
- `0x14001d9e0`
- `0x14001e980`

## import_xrefs

- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14001d950`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14001d950`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14001d8de`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14001d8de`
- `NDIS!NdisReleaseRWLock` at `0x14001d8fe`
- `NDIS!NdisReleaseRWLock` at `0x14001d98c`
- `NDIS!NdisReleaseRWLock` at `0x14001d8fe`
- `NDIS!NdisReleaseRWLock` at `0x14001d98c`
- `NDIS!NdisAcquireRWLockWrite` at `0x14001d8c7`
- `NDIS!NdisAcquireRWLockWrite` at `0x14001d8c7`

## pseudocode

```c
__int64 __fastcall IndexHashFastEnum(__int64 a1, __int64 a2, ULONG_PTR a3, int a4, _QWORD *a5)
{
  _QWORD *v5; // rsi
  __int64 v8; // rcx
  _QWORD *v10; // rdi
  __int64 LastMatchBuf; // rax
  struct _NDIS_RW_LOCK_EX *v12; // rcx
  __int64 v13; // r15
  PRTL_DYNAMIC_HASH_TABLE_ENTRY i; // rax
  __int64 Flink; // r12
  __int64 matched; // rbx
  _QWORD *v18; // [rsp+30h] [rbp-20h] BYREF
  struct _RTL_DYNAMIC_HASH_TABLE_CONTEXT Context; // [rsp+38h] [rbp-18h] BYREF
  int v20; // [rsp+90h] [rbp+40h] BYREF
  __int16 LockState; // [rsp+A8h] [rbp+58h] BYREF
  __int16 LockState_2; // [rsp+AAh] [rbp+5Ah]

  LockState_2 = HIWORD(a4);
  v5 = a5;
  v20 = 0;
  LockState = 0;
  v8 = *a5;
  v10 = 0;
  LOBYTE(LockState_2) = 0;
  memset(&Context, 0, sizeof(Context));
  LastMatchBuf = FindLastMatchBuf(v8);
  v12 = *(struct _NDIS_RW_LOCK_EX **)a1;
  v18 = (_QWORD *)LastMatchBuf;
  v13 = LastMatchBuf;
  NdisAcquireRWLockWrite(v12, (PLOCK_STATE_EX)&LockState, 1u);
  for ( i = RtlLookupEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 16), a3, &Context);
        ;
        i = RtlGetNextEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 16), &Context) )
  {
    if ( !i )
    {
      if ( !*v5 )
        *v5 = v10;
      NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)a1, (PLOCK_STATE_EX)&LockState);
      return 0;
    }
    Flink = (__int64)i[1].Linkage.Flink;
    matched = FilterMatchEnum(Flink, a2, &v20, 0);
    if ( matched )
      break;
    if ( v20 )
    {
      matched = InsertFilterToMatchBuf(v13, Flink, &v18, 0);
      if ( matched )
        break;
      v13 = (__int64)v18;
      if ( !v10 )
        v10 = v18;
    }
  }
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)a1, (PLOCK_STATE_EX)&LockState);
  if ( *v5 )
    v10 = (_QWORD *)*v5;
  else
    *v5 = v10;
  FreeMatchBufListInternal(v10);
  *v5 = 0;
  if ( matched )
    WfpReportError(matched, "IndexHashFastEnum");
  return matched;
}

```

## disassembly

```asm
0x14001d86c  mov     [rsp-38h+arg_8], rbx
0x14001d871  mov     [rsp-38h+LockState], r9d
0x14001d876  push    rbp
0x14001d877  push    rsi
0x14001d878  push    rdi
0x14001d879  push    r12
0x14001d87b  push    r13
0x14001d87d  push    r14
0x14001d87f  push    r15
0x14001d881  mov     rbp, rsp
0x14001d884  sub     rsp, 50h
0x14001d888  mov     rsi, [rbp+arg_20]
0x14001d88c  xor     eax, eax
0x14001d88e  mov     r14, rcx
0x14001d891  mov     [rbp+Context.Signature], rax
0x14001d895  xorps   xmm0, xmm0
0x14001d898  mov     [rbp+arg_0], eax
0x14001d89b  mov     rbx, r8
0x14001d89e  mov     word ptr [rbp+LockState], ax
0x14001d8a2  mov     rcx, [rsi]
0x14001d8a5  mov     r13, rdx
0x14001d8a8  xor     edi, edi
0x14001d8aa  mov     byte ptr [rbp+LockState+2], al
0x14001d8ad  movups  xmmword ptr [rbp+Context.ChainHead], xmm0
0x14001d8b1  call    FindLastMatchBuf
0x14001d8b6  mov     rcx, [r14]; Lock
0x14001d8b9  lea     rdx, [rbp+LockState]; LockState
0x14001d8bd  mov     r8b, 1; Flags
0x14001d8c0  mov     [rbp+var_20], rax
0x14001d8c4  mov     r15, rax
0x14001d8c7  call    cs:__imp_NdisAcquireRWLockWrite
0x14001d8ce  nop     dword ptr [rax+rax+00h]
0x14001d8d3  mov     rcx, [r14+10h]; HashTable
0x14001d8d7  lea     r8, [rbp+Context]; Context
0x14001d8db  mov     rdx, rbx; Signature
0x14001d8de  call    cs:__imp_RtlLookupEntryHashTable
0x14001d8e5  nop     dword ptr [rax+rax+00h]
0x14001d8ea  test    rax, rax
0x14001d8ed  jnz     short loc_14001D925
0x14001d8ef  cmp     [rsi], rax
0x14001d8f2  jnz     short loc_14001D8F7
0x14001d8f4  mov     [rsi], rdi
0x14001d8f7  mov     rcx, [r14]; Lock
0x14001d8fa  lea     rdx, [rbp+LockState]; LockState
0x14001d8fe  call    cs:__imp_NdisReleaseRWLock
0x14001d905  nop     dword ptr [rax+rax+00h]
0x14001d90a  xor     eax, eax
0x14001d90c  mov     rbx, [rsp+50h+arg_8]
0x14001d914  add     rsp, 50h
0x14001d918  pop     r15
0x14001d91a  pop     r14
0x14001d91c  pop     r13
0x14001d91e  pop     r12
0x14001d920  pop     rdi
0x14001d921  pop     rsi
0x14001d922  pop     rbp
0x14001d923  retn
0x14001d925  mov     r12, [rax+18h]
0x14001d929  lea     r8, [rbp+arg_0]
0x14001d92d  mov     rcx, r12
0x14001d930  xor     r9d, r9d
0x14001d933  mov     rdx, r13
0x14001d936  call    FilterMatchEnum
0x14001d93b  mov     rbx, rax
0x14001d93e  test    rax, rax
0x14001d941  jnz     short loc_14001D985
0x14001d943  cmp     [rbp+arg_0], eax
0x14001d946  jnz     short loc_14001D95E
0x14001d948  mov     rcx, [r14+10h]; HashTable
0x14001d94c  lea     rdx, [rbp+Context]; Context
0x14001d950  call    cs:__imp_RtlGetNextEntryHashTable
0x14001d957  nop     dword ptr [rax+rax+00h]
0x14001d95c  jmp     short loc_14001D8EA
0x14001d95e  xor     r9d, r9d
0x14001d961  lea     r8, [rbp+var_20]
0x14001d965  mov     rdx, r12
0x14001d968  mov     rcx, r15
0x14001d96b  call    InsertFilterToMatchBuf
0x14001d970  mov     rbx, rax
0x14001d973  test    rax, rax
0x14001d976  jnz     short loc_14001D985
0x14001d978  mov     r15, [rbp+var_20]
0x14001d97c  test    rdi, rdi
0x14001d97f  cmovz   rdi, r15
0x14001d983  jmp     short loc_14001D948
0x14001d985  mov     rcx, [r14]; Lock
0x14001d988  lea     rdx, [rbp+LockState]; LockState
0x14001d98c  call    cs:__imp_NdisReleaseRWLock
0x14001d993  nop     dword ptr [rax+rax+00h]
0x14001d998  mov     rax, [rsi]
0x14001d99b  test    rax, rax
0x14001d99e  jz      short loc_14001D9BF
0x14001d9a0  mov     rdi, rax
0x14001d9a3  mov     rcx, rdi; Entry
0x14001d9a6  call    FreeMatchBufListInternal
0x14001d9ab  mov     qword ptr [rsi], 0
0x14001d9b2  test    rbx, rbx
0x14001d9b5  jnz     short loc_14001D9C4
0x14001d9b7  mov     rax, rbx
0x14001d9ba  jmp     loc_14001D90C
0x14001d9bf  mov     [rsi], rdi
0x14001d9c2  jmp     short loc_14001D9A3
0x14001d9c4  lea     rdx, aIndexhashfaste; "IndexHashFastEnum"
0x14001d9cb  mov     rcx, rbx
0x14001d9ce  call    WfpReportError
0x14001d9d3  jmp     short loc_14001D9B7
```
