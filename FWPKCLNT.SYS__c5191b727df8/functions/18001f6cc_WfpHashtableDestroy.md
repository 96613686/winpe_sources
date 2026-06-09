# WfpHashtableDestroy

- ea: `0x18001f6cc`
- end: `0x18001f764`
- name: `WfpHashtableDestroy`
- size: `152`
- prototype: `__int64 __fastcall(PRTL_DYNAMIC_HASH_TABLE HashTable)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001f5d8`

## callees

- `0x18001f6cc`
- `0x18001f76c`

## import_xrefs

- `ntoskrnl!RtlDeleteHashTable` at `0x18001f74c`
- `ntoskrnl!RtlDeleteHashTable` at `0x18001f74c`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x18001f718`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x18001f718`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x18001f6fc`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x18001f6fc`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x18001f73d`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x18001f73d`

## pseudocode

```c
void __fastcall WfpHashtableDestroy(PRTL_DYNAMIC_HASH_TABLE HashTable)
{
  __int128 HashTablea; // [rsp+20h] [rbp-30h] BYREF
  __int128 Enumerator_8; // [rsp+30h] [rbp-20h]
  __int128 Enumerator_24; // [rsp+40h] [rbp-10h]
  PRTL_DYNAMIC_HASH_TABLE_ENTRY Entry; // [rsp+68h] [rbp+18h] BYREF

  Entry = 0;
  HashTablea = 0;
  Enumerator_8 = 0;
  Enumerator_24 = 0;
  RtlInitEnumerationHashTable(HashTable, (PRTL_DYNAMIC_HASH_TABLE_ENUMERATOR)((char *)&HashTablea + 8));
  *(_QWORD *)&HashTablea = HashTable;
  while ( (unsigned int)WfpHashtableIteratorGetNext(&HashTablea, &Entry) )
    RtlRemoveEntryHashTable(HashTable, Entry, 0);
  RtlEndEnumerationHashTable(
    (PRTL_DYNAMIC_HASH_TABLE)HashTablea,
    (PRTL_DYNAMIC_HASH_TABLE_ENUMERATOR)((char *)&HashTablea + 8));
  RtlDeleteHashTable(HashTable);
}

```

## disassembly

```asm
0x18001f6cc  mov     [rsp-8+arg_0], rbx
0x18001f6d1  mov     [rsp-8+Entry], rdx
0x18001f6d6  push    rbp
0x18001f6d7  mov     rbp, rsp
0x18001f6da  sub     rsp, 50h
0x18001f6de  xorps   xmm0, xmm0
0x18001f6e1  mov     [rbp+Entry], 0
0x18001f6e9  lea     rdx, [rbp+Enumerator]; Enumerator
0x18001f6ed  mov     rbx, rcx
0x18001f6f0  movups  xmmword ptr [rbp-30h], xmm0
0x18001f6f4  movups  xmmword ptr [rbp+Enumerator+8], xmm0
0x18001f6f8  movups  xmmword ptr [rbp+Enumerator.ChainHead], xmm0
0x18001f6fc  call    cs:__imp_RtlInitEnumerationHashTable
0x18001f703  nop     dword ptr [rax+rax+00h]
0x18001f708  mov     [rbp+HashTable], rbx
0x18001f70c  jmp     short loc_18001F724
0x18001f70e  mov     rdx, [rbp+Entry]; Entry
0x18001f712  xor     r8d, r8d; Context
0x18001f715  mov     rcx, rbx; HashTable
0x18001f718  call    cs:__imp_RtlRemoveEntryHashTable
0x18001f71f  nop     dword ptr [rax+rax+00h]
0x18001f724  lea     rdx, [rbp+Entry]
0x18001f728  lea     rcx, [rbp+HashTable]
0x18001f72c  call    WfpHashtableIteratorGetNext
0x18001f731  test    eax, eax
0x18001f733  jnz     short loc_18001F70E
0x18001f735  mov     rcx, [rbp+HashTable]; HashTable
0x18001f739  lea     rdx, [rbp+Enumerator]; Enumerator
0x18001f73d  call    cs:__imp_RtlEndEnumerationHashTable
0x18001f744  nop     dword ptr [rax+rax+00h]
0x18001f749  mov     rcx, rbx; HashTable
0x18001f74c  call    cs:__imp_RtlDeleteHashTable
0x18001f753  nop     dword ptr [rax+rax+00h]
0x18001f758  mov     rbx, [rsp+50h+arg_0]
0x18001f75d  add     rsp, 50h
0x18001f761  pop     rbp
0x18001f762  retn
```
