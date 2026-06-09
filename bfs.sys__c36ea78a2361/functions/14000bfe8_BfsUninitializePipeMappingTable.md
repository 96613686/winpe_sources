# BfsUninitializePipeMappingTable

- ea: `0x14000bfe8`
- end: `0x14000c0ed`
- name: `BfsUninitializePipeMappingTable`
- size: `261`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001e020`
- `0x14001f078`

## callees

- `0x14000bfe8`
- `0x140012cd4`

## import_xrefs

- `ntoskrnl!RtlDeleteHashTable` at `0x14000c097`
- `ntoskrnl!RtlDeleteHashTable` at `0x14000c097`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14000c042`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14000c042`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14000c06a`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14000c06a`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14000c087`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14000c087`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000c024`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000c024`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000c0c2`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000c0c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c0a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c0a9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c013`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c013`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c0ce`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c0ce`

## pseudocode

```c
void __fastcall BfsUninitializePipeMappingTable(__int64 a1)
{
  struct _RTL_DYNAMIC_HASH_TABLE *v2; // rcx
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v3; // rax
  struct _RTL_DYNAMIC_HASH_TABLE *v4; // rcx
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v5; // rdi
  struct _RTL_DYNAMIC_HASH_TABLE_ENUMERATOR Enumerator; // [rsp+20h] [rbp-38h] BYREF

  memset(&Enumerator, 0, sizeof(Enumerator));
  if ( *(_QWORD *)(a1 + 8) )
  {
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(a1, 0);
    v2 = *(struct _RTL_DYNAMIC_HASH_TABLE **)(a1 + 8);
    if ( v2 )
    {
      RtlInitEnumerationHashTable(v2, &Enumerator);
      while ( 1 )
      {
        v3 = RtlEnumerateEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 8), &Enumerator);
        v4 = *(struct _RTL_DYNAMIC_HASH_TABLE **)(a1 + 8);
        v5 = v3;
        if ( !v3 )
          break;
        BfsRemoveEntryHashTable(v4, v3);
        HIDWORD(v5[1].Linkage.Flink) &= ~1u;
      }
      RtlEndEnumerationHashTable(v4, &Enumerator);
      RtlDeleteHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 8));
      ExFreePoolWithTag(*(PVOID *)(a1 + 8), 0);
      *(_QWORD *)(a1 + 8) = 0;
    }
    ExReleasePushLockExclusiveEx(a1, 0);
    KeLeaveCriticalRegion();
    *(_QWORD *)a1 = 0;
  }
}

```

## disassembly

```asm
0x14000bfe8  mov     [rsp+arg_0], rbx
0x14000bfed  push    rdi
0x14000bfee  sub     rsp, 50h
0x14000bff2  xor     eax, eax
0x14000bff4  xorps   xmm0, xmm0
0x14000bff7  mov     rbx, rcx
0x14000bffa  mov     qword ptr [rsp+58h+Enumerator.BucketIndex], rax
0x14000bfff  movups  xmmword ptr [rsp+58h+Enumerator], xmm0
0x14000c004  movups  xmmword ptr [rsp+58h+Enumerator+10h], xmm0
0x14000c009  cmp     [rcx+8], rax
0x14000c00d  jz      loc_14000C0E1
0x14000c013  call    cs:__imp_KeEnterCriticalRegion
0x14000c01a  nop     dword ptr [rax+rax+00h]
0x14000c01f  xor     edx, edx
0x14000c021  mov     rcx, rbx
0x14000c024  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000c02b  nop     dword ptr [rax+rax+00h]
0x14000c030  mov     rcx, [rbx+8]; HashTable
0x14000c034  test    rcx, rcx
0x14000c037  jz      loc_14000C0BD
0x14000c03d  lea     rdx, [rsp+58h+Enumerator]; Enumerator
0x14000c042  call    cs:__imp_RtlInitEnumerationHashTable
0x14000c049  nop     dword ptr [rax+rax+00h]
0x14000c04e  jmp     short loc_14000C061
0x14000c050  mov     rdx, rdi
0x14000c053  call    BfsRemoveEntryHashTable
0x14000c058  mov     ecx, [rdi+1Ch]
0x14000c05b  and     ecx, 0FFFFFFFEh
0x14000c05e  mov     [rdi+1Ch], ecx
0x14000c061  mov     rcx, [rbx+8]; HashTable
0x14000c065  lea     rdx, [rsp+58h+Enumerator]; Enumerator
0x14000c06a  call    cs:__imp_RtlEnumerateEntryHashTable
0x14000c071  nop     dword ptr [rax+rax+00h]
0x14000c076  mov     rcx, [rbx+8]; HashTable
0x14000c07a  mov     rdi, rax
0x14000c07d  test    rax, rax
0x14000c080  jnz     short loc_14000C050
0x14000c082  lea     rdx, [rsp+58h+Enumerator]; Enumerator
0x14000c087  call    cs:__imp_RtlEndEnumerationHashTable
0x14000c08e  nop     dword ptr [rax+rax+00h]
0x14000c093  mov     rcx, [rbx+8]; HashTable
0x14000c097  call    cs:__imp_RtlDeleteHashTable
0x14000c09e  nop     dword ptr [rax+rax+00h]
0x14000c0a3  mov     rcx, [rbx+8]; P
0x14000c0a7  xor     edx, edx; Tag
0x14000c0a9  call    cs:__imp_ExFreePoolWithTag
0x14000c0b0  nop     dword ptr [rax+rax+00h]
0x14000c0b5  mov     qword ptr [rbx+8], 0
0x14000c0bd  xor     edx, edx
0x14000c0bf  mov     rcx, rbx
0x14000c0c2  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000c0c9  nop     dword ptr [rax+rax+00h]
0x14000c0ce  call    cs:__imp_KeLeaveCriticalRegion
0x14000c0d5  nop     dword ptr [rax+rax+00h]
0x14000c0da  mov     qword ptr [rbx], 0
0x14000c0e1  mov     rbx, [rsp+58h+arg_0]
0x14000c0e6  add     rsp, 50h
0x14000c0ea  pop     rdi
0x14000c0eb  retn
```
