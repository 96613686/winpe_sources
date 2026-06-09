# BfsUninitializePipeMappingTable

- ea: `0x14000be58`
- end: `0x14000bf5d`
- name: `BfsUninitializePipeMappingTable`
- size: `261`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001e020`
- `0x14001f078`

## callees

- `0x14000be58`
- `0x140012b9c`

## import_xrefs

- `ntoskrnl!RtlDeleteHashTable` at `0x14000bf07`
- `ntoskrnl!RtlDeleteHashTable` at `0x14000bf07`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14000beb2`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14000beb2`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14000beda`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14000beda`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14000bef7`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14000bef7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000be94`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000be94`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000bf32`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000bf32`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bf19`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bf19`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000be83`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000be83`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000bf3e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000bf3e`

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
0x14000be58  mov     [rsp+arg_0], rbx
0x14000be5d  push    rdi
0x14000be5e  sub     rsp, 50h
0x14000be62  xor     eax, eax
0x14000be64  xorps   xmm0, xmm0
0x14000be67  mov     rbx, rcx
0x14000be6a  mov     qword ptr [rsp+58h+Enumerator.BucketIndex], rax
0x14000be6f  movups  xmmword ptr [rsp+58h+Enumerator], xmm0
0x14000be74  movups  xmmword ptr [rsp+58h+Enumerator+10h], xmm0
0x14000be79  cmp     [rcx+8], rax
0x14000be7d  jz      loc_14000BF51
0x14000be83  call    cs:__imp_KeEnterCriticalRegion
0x14000be8a  nop     dword ptr [rax+rax+00h]
0x14000be8f  xor     edx, edx
0x14000be91  mov     rcx, rbx
0x14000be94  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000be9b  nop     dword ptr [rax+rax+00h]
0x14000bea0  mov     rcx, [rbx+8]; HashTable
0x14000bea4  test    rcx, rcx
0x14000bea7  jz      loc_14000BF2D
0x14000bead  lea     rdx, [rsp+58h+Enumerator]; Enumerator
0x14000beb2  call    cs:__imp_RtlInitEnumerationHashTable
0x14000beb9  nop     dword ptr [rax+rax+00h]
0x14000bebe  jmp     short loc_14000BED1
0x14000bec0  mov     rdx, rdi
0x14000bec3  call    BfsRemoveEntryHashTable
0x14000bec8  mov     ecx, [rdi+1Ch]
0x14000becb  and     ecx, 0FFFFFFFEh
0x14000bece  mov     [rdi+1Ch], ecx
0x14000bed1  mov     rcx, [rbx+8]; HashTable
0x14000bed5  lea     rdx, [rsp+58h+Enumerator]; Enumerator
0x14000beda  call    cs:__imp_RtlEnumerateEntryHashTable
0x14000bee1  nop     dword ptr [rax+rax+00h]
0x14000bee6  mov     rcx, [rbx+8]; HashTable
0x14000beea  mov     rdi, rax
0x14000beed  test    rax, rax
0x14000bef0  jnz     short loc_14000BEC0
0x14000bef2  lea     rdx, [rsp+58h+Enumerator]; Enumerator
0x14000bef7  call    cs:__imp_RtlEndEnumerationHashTable
0x14000befe  nop     dword ptr [rax+rax+00h]
0x14000bf03  mov     rcx, [rbx+8]; HashTable
0x14000bf07  call    cs:__imp_RtlDeleteHashTable
0x14000bf0e  nop     dword ptr [rax+rax+00h]
0x14000bf13  mov     rcx, [rbx+8]; P
0x14000bf17  xor     edx, edx; Tag
0x14000bf19  call    cs:__imp_ExFreePoolWithTag
0x14000bf20  nop     dword ptr [rax+rax+00h]
0x14000bf25  mov     qword ptr [rbx+8], 0
0x14000bf2d  xor     edx, edx
0x14000bf2f  mov     rcx, rbx
0x14000bf32  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000bf39  nop     dword ptr [rax+rax+00h]
0x14000bf3e  call    cs:__imp_KeLeaveCriticalRegion
0x14000bf45  nop     dword ptr [rax+rax+00h]
0x14000bf4a  mov     qword ptr [rbx], 0
0x14000bf51  mov     rbx, [rsp+58h+arg_0]
0x14000bf56  add     rsp, 50h
0x14000bf5a  pop     rdi
0x14000bf5b  retn
```
