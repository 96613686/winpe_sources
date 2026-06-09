# BfsClearGlobalFileEntry

- ea: `0x14000c31c`
- end: `0x14000c42b`
- name: `BfsClearGlobalFileEntry`
- size: `271`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000c658`
- `0x14000d5a0`
- `0x14000d76c`

## callees

- `0x14000c31c`
- `0x14000d55c`
- `0x140012b9c`

## import_xrefs

- `ntoskrnl!RtlDeleteHashTable` at `0x14000c3f9`
- `ntoskrnl!RtlDeleteHashTable` at `0x14000c3f9`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14000c374`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14000c374`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14000c3cc`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14000c3cc`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14000c3e9`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14000c3e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c348`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c388`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c39a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c3b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c40b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c348`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c388`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c39a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c3b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c40b`

## pseudocode

```c
void __fastcall BfsClearGlobalFileEntry(__int64 a1)
{
  void *v2; // rcx
  struct _RTL_DYNAMIC_HASH_TABLE *v3; // rcx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v4; // rax
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v5; // rdi
  struct _RTL_DYNAMIC_HASH_TABLE_ENUMERATOR Enumerator; // [rsp+20h] [rbp-38h] BYREF

  v2 = *(void **)(a1 + 72);
  memset(&Enumerator, 0, sizeof(Enumerator));
  if ( v2 )
    ExFreePoolWithTag(v2, 0);
  if ( *(_BYTE *)(a1 + 40) )
    BfsRemoveFileEntryFromDeleteList(a1);
  v3 = *(struct _RTL_DYNAMIC_HASH_TABLE **)(a1 + 88);
  if ( v3 )
  {
    RtlInitEnumerationHashTable(v3, &Enumerator);
    while ( 1 )
    {
      v4 = RtlEnumerateEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 88), &Enumerator);
      v5 = v4;
      if ( !v4 )
        break;
      ExFreePoolWithTag(v4[1].Linkage.Flink, 0);
      ExFreePoolWithTag(v5[1].Linkage.Blink, 0);
      BfsRemoveEntryHashTable(*(struct _RTL_DYNAMIC_HASH_TABLE **)(a1 + 88), v5);
      ExFreePoolWithTag(v5, 0);
    }
    RtlEndEnumerationHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 88), &Enumerator);
    RtlDeleteHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 88));
    ExFreePoolWithTag(*(PVOID *)(a1 + 88), 0);
    *(_QWORD *)(a1 + 88) = 0;
  }
}

```

## disassembly

```asm
0x14000c31c  mov     [rsp+arg_0], rbx
0x14000c321  push    rdi
0x14000c322  sub     rsp, 50h
0x14000c326  xor     eax, eax
0x14000c328  xorps   xmm0, xmm0
0x14000c32b  mov     rbx, rcx
0x14000c32e  mov     qword ptr [rsp+58h+Enumerator.BucketIndex], rax
0x14000c333  mov     rcx, [rcx+48h]; P
0x14000c337  movups  xmmword ptr [rsp+58h+Enumerator], xmm0
0x14000c33c  movups  xmmword ptr [rsp+58h+Enumerator+10h], xmm0
0x14000c341  test    rcx, rcx
0x14000c344  jz      short loc_14000C354
0x14000c346  xor     edx, edx; Tag
0x14000c348  call    cs:__imp_ExFreePoolWithTag
0x14000c34f  nop     dword ptr [rax+rax+00h]
0x14000c354  cmp     byte ptr [rbx+28h], 0
0x14000c358  jz      short loc_14000C362
0x14000c35a  mov     rcx, rbx
0x14000c35d  call    BfsRemoveFileEntryFromDeleteList
0x14000c362  mov     rcx, [rbx+58h]; HashTable
0x14000c366  test    rcx, rcx
0x14000c369  jz      loc_14000C41F
0x14000c36f  lea     rdx, [rsp+58h+Enumerator]; Enumerator
0x14000c374  call    cs:__imp_RtlInitEnumerationHashTable
0x14000c37b  nop     dword ptr [rax+rax+00h]
0x14000c380  jmp     short loc_14000C3C3
0x14000c382  mov     rcx, [rdi+18h]; P
0x14000c386  xor     edx, edx; Tag
0x14000c388  call    cs:__imp_ExFreePoolWithTag
0x14000c38f  nop     dword ptr [rax+rax+00h]
0x14000c394  mov     rcx, [rdi+20h]; P
0x14000c398  xor     edx, edx; Tag
0x14000c39a  call    cs:__imp_ExFreePoolWithTag
0x14000c3a1  nop     dword ptr [rax+rax+00h]
0x14000c3a6  mov     rcx, [rbx+58h]
0x14000c3aa  mov     rdx, rdi
0x14000c3ad  call    BfsRemoveEntryHashTable
0x14000c3b2  xor     edx, edx; Tag
0x14000c3b4  mov     rcx, rdi; P
0x14000c3b7  call    cs:__imp_ExFreePoolWithTag
0x14000c3be  nop     dword ptr [rax+rax+00h]
0x14000c3c3  mov     rcx, [rbx+58h]; HashTable
0x14000c3c7  lea     rdx, [rsp+58h+Enumerator]; Enumerator
0x14000c3cc  call    cs:__imp_RtlEnumerateEntryHashTable
0x14000c3d3  nop     dword ptr [rax+rax+00h]
0x14000c3d8  mov     rdi, rax
0x14000c3db  test    rax, rax
0x14000c3de  jnz     short loc_14000C382
0x14000c3e0  mov     rcx, [rbx+58h]; HashTable
0x14000c3e4  lea     rdx, [rsp+58h+Enumerator]; Enumerator
0x14000c3e9  call    cs:__imp_RtlEndEnumerationHashTable
0x14000c3f0  nop     dword ptr [rax+rax+00h]
0x14000c3f5  mov     rcx, [rbx+58h]; HashTable
0x14000c3f9  call    cs:__imp_RtlDeleteHashTable
0x14000c400  nop     dword ptr [rax+rax+00h]
0x14000c405  mov     rcx, [rbx+58h]; P
0x14000c409  xor     edx, edx; Tag
0x14000c40b  call    cs:__imp_ExFreePoolWithTag
0x14000c412  nop     dword ptr [rax+rax+00h]
0x14000c417  mov     qword ptr [rbx+58h], 0
0x14000c41f  mov     rbx, [rsp+58h+arg_0]
0x14000c424  add     rsp, 50h
0x14000c428  pop     rdi
0x14000c429  retn
```
