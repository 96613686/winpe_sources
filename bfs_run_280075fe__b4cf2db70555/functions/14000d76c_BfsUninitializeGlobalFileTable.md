# BfsUninitializeGlobalFileTable

- ea: `0x14000d76c`
- end: `0x14000d841`
- name: `BfsUninitializeGlobalFileTable`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14001e020`

## callees

- `0x14000c31c`
- `0x14000d76c`
- `0x140012b9c`

## import_xrefs

- `ntoskrnl!RtlDeleteHashTable` at `0x14000d810`
- `ntoskrnl!RtlDeleteHashTable` at `0x14000d810`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14000d79b`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14000d79b`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14000d7dd`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14000d7dd`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14000d7fd`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14000d7fd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d7c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d825`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d7c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d825`

## pseudocode

```c
__int64 BfsUninitializeGlobalFileTable()
{
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v0; // rax
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v1; // rbx
  struct _RTL_DYNAMIC_HASH_TABLE_ENUMERATOR Enumerator; // [rsp+20h] [rbp-38h] BYREF

  memset(&Enumerator, 0, sizeof(Enumerator));
  if ( P )
  {
    RtlInitEnumerationHashTable(P, &Enumerator);
    while ( 1 )
    {
      v0 = RtlEnumerateEntryHashTable(P, &Enumerator);
      v1 = v0;
      if ( !v0 )
        break;
      BfsClearGlobalFileEntry((__int64)v0);
      BfsRemoveEntryHashTable(P, v1);
      ExFreePoolWithTag(v1, 0);
    }
    RtlEndEnumerationHashTable(P, &Enumerator);
    RtlDeleteHashTable(P);
    ExFreePoolWithTag(P, 0);
  }
  return _InterlockedExchange64(&qword_1400191B0, 0);
}

```

## disassembly

```asm
0x14000d76c  push    rbx
0x14000d76e  sub     rsp, 50h
0x14000d772  mov     rcx, cs:P; HashTable
0x14000d779  xor     eax, eax
0x14000d77b  mov     qword ptr [rsp+58h+Enumerator.BucketIndex], rax
0x14000d780  xorps   xmm0, xmm0
0x14000d783  movups  xmmword ptr [rsp+58h+Enumerator], xmm0
0x14000d788  movups  xmmword ptr [rsp+58h+Enumerator+10h], xmm0
0x14000d78d  test    rcx, rcx
0x14000d790  jz      loc_14000D831
0x14000d796  lea     rdx, [rsp+58h+Enumerator]; Enumerator
0x14000d79b  call    cs:__imp_RtlInitEnumerationHashTable
0x14000d7a2  nop     dword ptr [rax+rax+00h]
0x14000d7a7  jmp     short loc_14000D7D1
0x14000d7a9  mov     rcx, rbx
0x14000d7ac  call    BfsClearGlobalFileEntry
0x14000d7b1  mov     rcx, cs:P
0x14000d7b8  mov     rdx, rbx
0x14000d7bb  call    BfsRemoveEntryHashTable
0x14000d7c0  xor     edx, edx; Tag
0x14000d7c2  mov     rcx, rbx; P
0x14000d7c5  call    cs:__imp_ExFreePoolWithTag
0x14000d7cc  nop     dword ptr [rax+rax+00h]
0x14000d7d1  mov     rcx, cs:P; HashTable
0x14000d7d8  lea     rdx, [rsp+58h+Enumerator]; Enumerator
0x14000d7dd  call    cs:__imp_RtlEnumerateEntryHashTable
0x14000d7e4  nop     dword ptr [rax+rax+00h]
0x14000d7e9  mov     rbx, rax
0x14000d7ec  test    rax, rax
0x14000d7ef  jnz     short loc_14000D7A9
0x14000d7f1  mov     rcx, cs:P; HashTable
0x14000d7f8  lea     rdx, [rsp+58h+Enumerator]; Enumerator
0x14000d7fd  call    cs:__imp_RtlEndEnumerationHashTable
0x14000d804  nop     dword ptr [rax+rax+00h]
0x14000d809  mov     rcx, cs:P; HashTable
0x14000d810  call    cs:__imp_RtlDeleteHashTable
0x14000d817  nop     dword ptr [rax+rax+00h]
0x14000d81c  mov     rcx, cs:P; P
0x14000d823  xor     edx, edx; Tag
0x14000d825  call    cs:__imp_ExFreePoolWithTag
0x14000d82c  nop     dword ptr [rax+rax+00h]
0x14000d831  xor     eax, eax
0x14000d833  xchg    rax, cs:qword_1400191B0
0x14000d83a  add     rsp, 50h
0x14000d83e  pop     rbx
0x14000d83f  retn
```
