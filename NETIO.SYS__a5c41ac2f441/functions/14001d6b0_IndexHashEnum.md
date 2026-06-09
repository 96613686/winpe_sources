# IndexHashEnum

- ea: `0x14001d6b0`
- end: `0x14001d866`
- name: `IndexHashEnum`
- size: `438`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x140004bf0`
- `0x140009520`
- `0x140009e00`
- `0x14001d460`
- `0x14001d6b0`
- `0x14001d86c`
- `0x14001d9e0`
- `0x14001da08`
- `0x14001e980`

## import_xrefs

- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14001d7a6`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14001d7a6`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14001d7bf`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14001d7bf`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14001d762`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14001d762`
- `NDIS!NdisReleaseRWLock` at `0x14001d7d2`
- `NDIS!NdisReleaseRWLock` at `0x14001d7d2`
- `NDIS!NdisAcquireRWLockWrite` at `0x14001d74e`
- `NDIS!NdisAcquireRWLockWrite` at `0x14001d74e`

## pseudocode

```c
__int64 __fastcall IndexHashEnum(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4, unsigned int a5)
{
  _QWORD *v6; // rcx
  __int64 v9; // r15
  __int64 v10; // rdx
  _QWORD *v12; // rdi
  __int64 v13; // rcx
  __int64 matched; // rbx
  __int64 Flink; // r12
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v16; // rax
  int v17; // [rsp+30h] [rbp-48h] BYREF
  int v18; // [rsp+34h] [rbp-44h] BYREF
  __int64 v19; // [rsp+38h] [rbp-40h] BYREF
  __int64 LastMatchBuf; // [rsp+40h] [rbp-38h] BYREF
  _RTL_DYNAMIC_HASH_TABLE_ENUMERATOR Enumerator; // [rsp+48h] [rbp-30h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+C0h] [rbp+48h] BYREF

  v6 = (_QWORD *)*a4;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  memset(&Enumerator, 0, sizeof(Enumerator));
  v17 = 0;
  v18 = 0;
  v19 = 0;
  LastMatchBuf = FindLastMatchBuf(v6);
  v9 = LastMatchBuf;
  if ( (unsigned int)ComputeIncomingSignatureFromEnum(a1, v10, &v19, &v17) )
  {
    if ( v17 )
      return 0;
    else
      return IndexHashFastEnum(a1, a2, v19);
  }
  else
  {
    v12 = 0;
    NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)a1, &LockState, 1u);
    if ( RtlInitEnumerationHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 16), &Enumerator) )
    {
      matched = 0;
      while ( 1 )
      {
        v16 = RtlEnumerateEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 16), &Enumerator);
        if ( !v16 )
          break;
        Flink = (__int64)v16[1].Linkage.Flink;
        matched = FilterMatchEnum(Flink, a2, &v18, a5);
        if ( matched )
          break;
        if ( v18 )
        {
          matched = InsertFilterToMatchBuf(v9, Flink, &LastMatchBuf, 0);
          if ( matched )
            break;
          v9 = LastMatchBuf;
          if ( !v12 )
            v12 = (_QWORD *)LastMatchBuf;
        }
      }
      RtlEndEnumerationHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 16), &Enumerator);
    }
    else
    {
      matched = WfpReportSysErrorAsNtStatus(v13, "RtlInitEnumerationHashTable", 3221225473LL, 1);
    }
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)a1, &LockState);
    if ( *a4 )
      v12 = (_QWORD *)*a4;
    else
      *a4 = v12;
    if ( matched )
    {
      FreeMatchBufListInternal(v12);
      *a4 = 0;
      WfpReportError(matched, "IndexHashEnum");
    }
    return matched;
  }
}

```

## disassembly

```asm
0x14001d6b0  push    rbp
0x14001d6b2  push    rbx
0x14001d6b3  push    rsi
0x14001d6b4  push    rdi
0x14001d6b5  push    r12
0x14001d6b7  push    r13
0x14001d6b9  push    r14
0x14001d6bb  push    r15
0x14001d6bd  mov     rbp, rsp
0x14001d6c0  sub     rsp, 78h
0x14001d6c4  xor     eax, eax
0x14001d6c6  mov     rsi, rcx
0x14001d6c9  mov     rcx, [r9]
0x14001d6cc  xorps   xmm0, xmm0
0x14001d6cf  mov     word ptr [rbp+LockState.OldIrql], ax
0x14001d6d3  mov     r14, r9
0x14001d6d6  mov     [rbp+LockState.Flags], al
0x14001d6d9  mov     r13, rdx
0x14001d6dc  movups  xmmword ptr [rbp+Enumerator], xmm0
0x14001d6e0  mov     qword ptr [rbp+Enumerator.BucketIndex], rax
0x14001d6e4  movups  xmmword ptr [rbp+Enumerator+10h], xmm0
0x14001d6e8  mov     [rbp+var_48], eax
0x14001d6eb  mov     [rbp+var_44], eax
0x14001d6ee  mov     [rbp+var_40], rax
0x14001d6f2  call    FindLastMatchBuf
0x14001d6f7  mov     rcx, rsi
0x14001d6fa  mov     [rbp+var_38], rax
0x14001d6fe  lea     r9, [rbp+var_48]
0x14001d702  mov     r15, rax
0x14001d705  lea     r8, [rbp+var_40]
0x14001d709  call    ComputeIncomingSignatureFromEnum
0x14001d70e  test    eax, eax
0x14001d710  jz      short loc_14001D742
0x14001d712  cmp     [rbp+var_48], 0
0x14001d716  jnz     loc_14001D822
0x14001d71c  mov     r8, [rbp+var_40]
0x14001d720  mov     rdx, r13
0x14001d723  mov     rcx, rsi
0x14001d726  mov     [rsp+78h+var_58], r14
0x14001d72b  call    IndexHashFastEnum
0x14001d730  add     rsp, 78h
0x14001d734  pop     r15
0x14001d736  pop     r14
0x14001d738  pop     r13
0x14001d73a  pop     r12
0x14001d73c  pop     rdi
0x14001d73d  pop     rsi
0x14001d73e  pop     rbx
0x14001d73f  pop     rbp
0x14001d740  retn
0x14001d742  mov     rcx, [rsi]; Lock
0x14001d745  lea     rdx, [rbp+LockState]; LockState
0x14001d749  mov     r8b, 1; Flags
0x14001d74c  xor     edi, edi
0x14001d74e  call    cs:__imp_NdisAcquireRWLockWrite
0x14001d755  nop     dword ptr [rax+rax+00h]
0x14001d75a  mov     rcx, [rsi+10h]; HashTable
0x14001d75e  lea     rdx, [rbp+Enumerator]; Enumerator
0x14001d762  call    cs:__imp_RtlInitEnumerationHashTable
0x14001d769  nop     dword ptr [rax+rax+00h]
0x14001d76e  test    al, al
0x14001d770  jz      loc_14001D829
0x14001d776  xor     ebx, ebx
0x14001d778  jmp     short loc_14001D79E
0x14001d77a  mov     r12, [rax+18h]
0x14001d77e  lea     r8, [rbp+var_44]
0x14001d782  mov     r9d, [rbp+arg_20]
0x14001d786  mov     rcx, r12
0x14001d789  mov     rdx, r13
0x14001d78c  call    FilterMatchEnum
0x14001d791  mov     rbx, rax
0x14001d794  test    rax, rax
0x14001d797  jnz     short loc_14001D7B7
0x14001d799  cmp     [rbp+var_44], eax
0x14001d79c  jnz     short loc_14001D7F6
0x14001d79e  mov     rcx, [rsi+10h]; HashTable
0x14001d7a2  lea     rdx, [rbp+Enumerator]; Enumerator
0x14001d7a6  call    cs:__imp_RtlEnumerateEntryHashTable
0x14001d7ad  nop     dword ptr [rax+rax+00h]
0x14001d7b2  test    rax, rax
0x14001d7b5  jnz     short loc_14001D77A
0x14001d7b7  mov     rcx, [rsi+10h]; HashTable
0x14001d7bb  lea     rdx, [rbp+Enumerator]; Enumerator
0x14001d7bf  call    cs:__imp_RtlEndEnumerationHashTable
0x14001d7c6  nop     dword ptr [rax+rax+00h]
0x14001d7cb  mov     rcx, [rsi]; Lock
0x14001d7ce  lea     rdx, [rbp+LockState]; LockState
0x14001d7d2  call    cs:__imp_NdisReleaseRWLock
0x14001d7d9  nop     dword ptr [rax+rax+00h]
0x14001d7de  mov     rax, [r14]
0x14001d7e1  test    rax, rax
0x14001d7e4  jnz     short loc_14001D81D
0x14001d7e6  mov     [r14], rdi
0x14001d7e9  test    rbx, rbx
0x14001d7ec  jnz     short loc_14001D846
0x14001d7ee  mov     rax, rbx
0x14001d7f1  jmp     loc_14001D730
0x14001d7f6  xor     r9d, r9d
0x14001d7f9  lea     r8, [rbp+var_38]
0x14001d7fd  mov     rdx, r12
0x14001d800  mov     rcx, r15
0x14001d803  call    InsertFilterToMatchBuf
0x14001d808  mov     rbx, rax
0x14001d80b  test    rax, rax
0x14001d80e  jnz     short loc_14001D7B7
0x14001d810  mov     r15, [rbp+var_38]
0x14001d814  test    rdi, rdi
0x14001d817  cmovz   rdi, r15
0x14001d81b  jmp     short loc_14001D79E
0x14001d81d  mov     rdi, rax
0x14001d820  jmp     short loc_14001D7E9
0x14001d822  xor     eax, eax
0x14001d824  jmp     loc_14001D730
0x14001d829  mov     r9d, 1
0x14001d82f  lea     rdx, aRtlinitenumera; "RtlInitEnumerationHashTable"
0x14001d836  mov     r8d, 0C0000001h
0x14001d83c  call    WfpReportSysErrorAsNtStatus
0x14001d841  mov     rbx, rax
0x14001d844  jmp     short loc_14001D7CB
0x14001d846  mov     rcx, rdi; Entry
0x14001d849  call    FreeMatchBufListInternal
0x14001d84e  lea     rdx, aIndexhashenum; "IndexHashEnum"
0x14001d855  mov     qword ptr [r14], 0
0x14001d85c  mov     rcx, rbx
0x14001d85f  call    WfpReportError
0x14001d864  jmp     short loc_14001D7EE
```
