# BfsInitializePipeMappingTable

- ea: `0x14000b424`
- end: `0x14000b4be`
- name: `BfsInitializePipeMappingTable`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001f078`

## callees

- `0x14000b424`

## import_xrefs

- `ntoskrnl!ExInitializePushLock` at `0x14000b43d`
- `ntoskrnl!ExInitializePushLock` at `0x14000b43d`
- `ntoskrnl!RtlCreateHashTable` at `0x14000b480`
- `ntoskrnl!RtlCreateHashTable` at `0x14000b480`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b497`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b497`
- `ntoskrnl!ExAllocatePool2` at `0x14000b459`
- `ntoskrnl!ExAllocatePool2` at `0x14000b459`

## pseudocode

```c
__int64 BfsInitializePipeMappingTable()
{
  PRTL_DYNAMIC_HASH_TABLE HashTable; // [rsp+30h] [rbp+8h] BYREF

  HashTable = 0;
  ExInitializePushLock(&gBfsPipeMappingTable);
  HashTable = (PRTL_DYNAMIC_HASH_TABLE)ExAllocatePool2(256, 40, 1416848962);
  if ( !HashTable )
    return 3221225495LL;
  if ( RtlCreateHashTable(&HashTable, 0, 0) )
  {
    qword_140019238 = (__int64)HashTable;
    return 0;
  }
  else
  {
    ExFreePoolWithTag(HashTable, 0);
    return 3221225473LL;
  }
}

```

## disassembly

```asm
0x14000b424  mov     [rsp+HashTable], rcx
0x14000b429  sub     rsp, 28h
0x14000b42d  lea     rcx, gBfsPipeMappingTable; PushLock
0x14000b434  mov     [rsp+28h+HashTable], 0
0x14000b43d  call    cs:__imp_ExInitializePushLock
0x14000b444  nop     dword ptr [rax+rax+00h]
0x14000b449  mov     edx, 28h ; '('
0x14000b44e  mov     r8d, 54736642h
0x14000b454  mov     ecx, 100h
0x14000b459  call    cs:__imp_ExAllocatePool2
0x14000b460  nop     dword ptr [rax+rax+00h]
0x14000b465  mov     [rsp+28h+HashTable], rax
0x14000b46a  test    rax, rax
0x14000b46d  jnz     short loc_14000B476
0x14000b46f  mov     eax, 0C0000017h
0x14000b474  jmp     short loc_14000B4B8
0x14000b476  xor     r8d, r8d; Flags
0x14000b479  lea     rcx, [rsp+28h+HashTable]; HashTable
0x14000b47e  xor     edx, edx; Shift
0x14000b480  call    cs:__imp_RtlCreateHashTable
0x14000b487  nop     dword ptr [rax+rax+00h]
0x14000b48c  test    al, al
0x14000b48e  jnz     short loc_14000B4AA
0x14000b490  mov     rcx, [rsp+28h+HashTable]; P
0x14000b495  xor     edx, edx; Tag
0x14000b497  call    cs:__imp_ExFreePoolWithTag
0x14000b49e  nop     dword ptr [rax+rax+00h]
0x14000b4a3  mov     eax, 0C0000001h
0x14000b4a8  jmp     short loc_14000B4B8
0x14000b4aa  mov     rax, [rsp+28h+HashTable]
0x14000b4af  mov     cs:qword_140019238, rax
0x14000b4b6  xor     eax, eax
0x14000b4b8  add     rsp, 28h
0x14000b4bc  retn
```
