# BfsUninitializeGlobalFileTable

- ea: `0x14000d900`
- end: `0x14000d9d5`
- name: `BfsUninitializeGlobalFileTable`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14001e020`

## callees

- `0x14000c4ac`
- `0x14000d900`
- `0x140012cd4`

## import_xrefs

- `ntoskrnl!RtlDeleteHashTable` at `0x14000d9a4`
- `ntoskrnl!RtlDeleteHashTable` at `0x14000d9a4`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14000d92f`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14000d92f`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14000d971`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14000d971`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14000d991`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14000d991`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d959`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d9b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d959`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d9b9`

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
  return _InterlockedExchange64(&qword_1400191A0, 0);
}

```

## disassembly

```asm
0x14000d900  push    rbx
0x14000d902  sub     rsp, 50h
0x14000d906  mov     rcx, cs:P; HashTable
0x14000d90d  xor     eax, eax
0x14000d90f  mov     qword ptr [rsp+58h+Enumerator.BucketIndex], rax
0x14000d914  xorps   xmm0, xmm0
0x14000d917  movups  xmmword ptr [rsp+58h+Enumerator], xmm0
0x14000d91c  movups  xmmword ptr [rsp+58h+Enumerator+10h], xmm0
0x14000d921  test    rcx, rcx
0x14000d924  jz      loc_14000D9C5
0x14000d92a  lea     rdx, [rsp+58h+Enumerator]; Enumerator
0x14000d92f  call    cs:__imp_RtlInitEnumerationHashTable
0x14000d936  nop     dword ptr [rax+rax+00h]
0x14000d93b  jmp     short loc_14000D965
0x14000d93d  mov     rcx, rbx
0x14000d940  call    BfsClearGlobalFileEntry
0x14000d945  mov     rcx, cs:P
0x14000d94c  mov     rdx, rbx
0x14000d94f  call    BfsRemoveEntryHashTable
0x14000d954  xor     edx, edx; Tag
0x14000d956  mov     rcx, rbx; P
0x14000d959  call    cs:__imp_ExFreePoolWithTag
0x14000d960  nop     dword ptr [rax+rax+00h]
0x14000d965  mov     rcx, cs:P; HashTable
0x14000d96c  lea     rdx, [rsp+58h+Enumerator]; Enumerator
0x14000d971  call    cs:__imp_RtlEnumerateEntryHashTable
0x14000d978  nop     dword ptr [rax+rax+00h]
0x14000d97d  mov     rbx, rax
0x14000d980  test    rax, rax
0x14000d983  jnz     short loc_14000D93D
0x14000d985  mov     rcx, cs:P; HashTable
0x14000d98c  lea     rdx, [rsp+58h+Enumerator]; Enumerator
0x14000d991  call    cs:__imp_RtlEndEnumerationHashTable
0x14000d998  nop     dword ptr [rax+rax+00h]
0x14000d99d  mov     rcx, cs:P; HashTable
0x14000d9a4  call    cs:__imp_RtlDeleteHashTable
0x14000d9ab  nop     dword ptr [rax+rax+00h]
0x14000d9b0  mov     rcx, cs:P; P
0x14000d9b7  xor     edx, edx; Tag
0x14000d9b9  call    cs:__imp_ExFreePoolWithTag
0x14000d9c0  nop     dword ptr [rax+rax+00h]
0x14000d9c5  xor     eax, eax
0x14000d9c7  xchg    rax, cs:qword_1400191A0
0x14000d9ce  add     rsp, 50h
0x14000d9d2  pop     rbx
0x14000d9d3  retn
```
