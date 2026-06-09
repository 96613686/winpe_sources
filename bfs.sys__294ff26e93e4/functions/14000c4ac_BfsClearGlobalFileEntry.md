# BfsClearGlobalFileEntry

- ea: `0x14000c4ac`
- end: `0x14000c5bb`
- name: `BfsClearGlobalFileEntry`
- size: `271`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000c7e8`
- `0x14000d734`
- `0x14000d900`

## callees

- `0x14000c4ac`
- `0x14000d6f0`
- `0x140012cd4`

## import_xrefs

- `ntoskrnl!RtlDeleteHashTable` at `0x14000c589`
- `ntoskrnl!RtlDeleteHashTable` at `0x14000c589`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14000c504`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14000c504`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14000c55c`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14000c55c`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14000c579`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14000c579`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c4d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c518`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c52a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c547`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c59b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c4d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c518`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c52a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c547`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c59b`

## pseudocode

```c
void __fastcall BfsClearGlobalFileEntry(__int64 a1)
{
  void *v2; // rcx
  struct _RTL_DYNAMIC_HASH_TABLE *v3; // rcx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v4; // rax
  PVOID *p_Flink; // rdi
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
      p_Flink = (PVOID *)&v4->Linkage.Flink;
      if ( !v4 )
        break;
      ExFreePoolWithTag(v4[1].Linkage.Flink, 0);
      ExFreePoolWithTag(p_Flink[4], 0);
      BfsRemoveEntryHashTable(*(_QWORD *)(a1 + 88), p_Flink);
      ExFreePoolWithTag(p_Flink, 0);
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
0x14000c4ac  mov     [rsp+arg_0], rbx
0x14000c4b1  push    rdi
0x14000c4b2  sub     rsp, 50h
0x14000c4b6  xor     eax, eax
0x14000c4b8  xorps   xmm0, xmm0
0x14000c4bb  mov     rbx, rcx
0x14000c4be  mov     qword ptr [rsp+58h+Enumerator.BucketIndex], rax
0x14000c4c3  mov     rcx, [rcx+48h]; P
0x14000c4c7  movups  xmmword ptr [rsp+58h+Enumerator], xmm0
0x14000c4cc  movups  xmmword ptr [rsp+58h+Enumerator+10h], xmm0
0x14000c4d1  test    rcx, rcx
0x14000c4d4  jz      short loc_14000C4E4
0x14000c4d6  xor     edx, edx; Tag
0x14000c4d8  call    cs:__imp_ExFreePoolWithTag
0x14000c4df  nop     dword ptr [rax+rax+00h]
0x14000c4e4  cmp     byte ptr [rbx+28h], 0
0x14000c4e8  jz      short loc_14000C4F2
0x14000c4ea  mov     rcx, rbx
0x14000c4ed  call    BfsRemoveFileEntryFromDeleteList
0x14000c4f2  mov     rcx, [rbx+58h]; HashTable
0x14000c4f6  test    rcx, rcx
0x14000c4f9  jz      loc_14000C5AF
0x14000c4ff  lea     rdx, [rsp+58h+Enumerator]; Enumerator
0x14000c504  call    cs:__imp_RtlInitEnumerationHashTable
0x14000c50b  nop     dword ptr [rax+rax+00h]
0x14000c510  jmp     short loc_14000C553
0x14000c512  mov     rcx, [rdi+18h]; P
0x14000c516  xor     edx, edx; Tag
0x14000c518  call    cs:__imp_ExFreePoolWithTag
0x14000c51f  nop     dword ptr [rax+rax+00h]
0x14000c524  mov     rcx, [rdi+20h]; P
0x14000c528  xor     edx, edx; Tag
0x14000c52a  call    cs:__imp_ExFreePoolWithTag
0x14000c531  nop     dword ptr [rax+rax+00h]
0x14000c536  mov     rcx, [rbx+58h]
0x14000c53a  mov     rdx, rdi
0x14000c53d  call    BfsRemoveEntryHashTable
0x14000c542  xor     edx, edx; Tag
0x14000c544  mov     rcx, rdi; P
0x14000c547  call    cs:__imp_ExFreePoolWithTag
0x14000c54e  nop     dword ptr [rax+rax+00h]
0x14000c553  mov     rcx, [rbx+58h]; HashTable
0x14000c557  lea     rdx, [rsp+58h+Enumerator]; Enumerator
0x14000c55c  call    cs:__imp_RtlEnumerateEntryHashTable
0x14000c563  nop     dword ptr [rax+rax+00h]
0x14000c568  mov     rdi, rax
0x14000c56b  test    rax, rax
0x14000c56e  jnz     short loc_14000C512
0x14000c570  mov     rcx, [rbx+58h]; HashTable
0x14000c574  lea     rdx, [rsp+58h+Enumerator]; Enumerator
0x14000c579  call    cs:__imp_RtlEndEnumerationHashTable
0x14000c580  nop     dword ptr [rax+rax+00h]
0x14000c585  mov     rcx, [rbx+58h]; HashTable
0x14000c589  call    cs:__imp_RtlDeleteHashTable
0x14000c590  nop     dword ptr [rax+rax+00h]
0x14000c595  mov     rcx, [rbx+58h]; P
0x14000c599  xor     edx, edx; Tag
0x14000c59b  call    cs:__imp_ExFreePoolWithTag
0x14000c5a2  nop     dword ptr [rax+rax+00h]
0x14000c5a7  mov     qword ptr [rbx+58h], 0
0x14000c5af  mov     rbx, [rsp+58h+arg_0]
0x14000c5b4  add     rsp, 50h
0x14000c5b8  pop     rdi
0x14000c5b9  retn
```
