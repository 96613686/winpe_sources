# AipkFreeAppxInMemoryCache

- ea: `0x140002ec0`
- end: `0x140002fc2`
- name: `AipkFreeAppxInMemoryCache`
- size: `258`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400252dc`

## callees

- `0x140002ec0`
- `0x1400328b0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140002faf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140002faf`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140002ee6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140002ee6`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140002efb`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140002efb`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140002fa3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140002fa3`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x140002f1c`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x140002f1c`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x140002f50`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x140002f50`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140002f30`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140002f30`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x140002f70`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x140002f70`
- `ntoskrnl!RtlDeleteHashTable` at `0x140002f83`
- `ntoskrnl!RtlDeleteHashTable` at `0x140002f83`

## pseudocode

```c
void AipkFreeAppxInMemoryCache()
{
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v0; // rax
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v1; // rbx
  _RTL_DYNAMIC_HASH_TABLE_ENUMERATOR Enumerator; // [rsp+20h] [rbp-38h] BYREF

  memset(&Enumerator, 0, sizeof(Enumerator));
  if ( AipAppxInMemoryCacheInitialized )
  {
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(&AipAppxInMemoryCache, 0);
    if ( HashTable )
    {
      RtlInitEnumerationHashTable(HashTable, &Enumerator);
      while ( 1 )
      {
        v0 = RtlEnumerateEntryHashTable(HashTable, &Enumerator);
        v1 = v0;
        if ( !v0 )
          break;
        RtlRemoveEntryHashTable(HashTable, v0, 0);
        AiFree(v1);
      }
      RtlEndEnumerationHashTable(HashTable, &Enumerator);
      RtlDeleteHashTable(HashTable);
      HashTable = 0;
    }
    ExReleasePushLockExclusiveEx(&AipAppxInMemoryCache, 0);
    KeLeaveCriticalRegion();
  }
}

```

## disassembly

```asm
0x140002ec0  push    rbx
0x140002ec2  sub     rsp, 50h
0x140002ec6  xor     eax, eax
0x140002ec8  xorps   xmm0, xmm0
0x140002ecb  cmp     cs:AipAppxInMemoryCacheInitialized, al
0x140002ed1  movups  xmmword ptr [rsp+58h+Enumerator], xmm0
0x140002ed6  mov     qword ptr [rsp+58h+Enumerator.BucketIndex], rax
0x140002edb  movups  xmmword ptr [rsp+58h+Enumerator+10h], xmm0
0x140002ee0  jz      loc_140002FBB
0x140002ee6  call    cs:__imp_KeEnterCriticalRegion
0x140002eed  nop     dword ptr [rax+rax+00h]
0x140002ef2  xor     edx, edx
0x140002ef4  lea     rcx, AipAppxInMemoryCache
0x140002efb  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140002f02  nop     dword ptr [rax+rax+00h]
0x140002f07  mov     rcx, cs:HashTable; HashTable
0x140002f0e  test    rcx, rcx
0x140002f11  jz      loc_140002F9A
0x140002f17  lea     rdx, [rsp+58h+Enumerator]; Enumerator
0x140002f1c  call    cs:__imp_RtlInitEnumerationHashTable
0x140002f23  nop     dword ptr [rax+rax+00h]
0x140002f28  jmp     short loc_140002F44
0x140002f2a  xor     r8d, r8d; Context
0x140002f2d  mov     rdx, rbx; Entry
0x140002f30  call    cs:__imp_RtlRemoveEntryHashTable
0x140002f37  nop     dword ptr [rax+rax+00h]
0x140002f3c  mov     rcx, rbx
0x140002f3f  call    AiFree
0x140002f44  mov     rcx, cs:HashTable; HashTable
0x140002f4b  lea     rdx, [rsp+58h+Enumerator]; Enumerator
0x140002f50  call    cs:__imp_RtlEnumerateEntryHashTable
0x140002f57  nop     dword ptr [rax+rax+00h]
0x140002f5c  mov     rcx, cs:HashTable; HashTable
0x140002f63  mov     rbx, rax
0x140002f66  test    rax, rax
0x140002f69  jnz     short loc_140002F2A
0x140002f6b  lea     rdx, [rsp+58h+Enumerator]; Enumerator
0x140002f70  call    cs:__imp_RtlEndEnumerationHashTable
0x140002f77  nop     dword ptr [rax+rax+00h]
0x140002f7c  mov     rcx, cs:HashTable; HashTable
0x140002f83  call    cs:__imp_RtlDeleteHashTable
0x140002f8a  nop     dword ptr [rax+rax+00h]
0x140002f8f  mov     cs:HashTable, 0
0x140002f9a  xor     edx, edx
0x140002f9c  lea     rcx, AipAppxInMemoryCache
0x140002fa3  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140002faa  nop     dword ptr [rax+rax+00h]
0x140002faf  call    cs:__imp_KeLeaveCriticalRegion
0x140002fb6  nop     dword ptr [rax+rax+00h]
0x140002fbb  add     rsp, 50h
0x140002fbf  pop     rbx
0x140002fc0  retn
```
