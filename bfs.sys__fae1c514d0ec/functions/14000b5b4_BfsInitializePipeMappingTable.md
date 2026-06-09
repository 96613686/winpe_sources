# BfsInitializePipeMappingTable

- ea: `0x14000b5b4`
- end: `0x14000b64e`
- name: `BfsInitializePipeMappingTable`
- size: `154`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001f078`

## callees

- `0x14000b5b4`

## import_xrefs

- `ntoskrnl!ExInitializePushLock` at `0x14000b5cd`
- `ntoskrnl!ExInitializePushLock` at `0x14000b5cd`
- `ntoskrnl!RtlCreateHashTable` at `0x14000b610`
- `ntoskrnl!RtlCreateHashTable` at `0x14000b610`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b627`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b627`
- `ntoskrnl!ExAllocatePool2` at `0x14000b5e9`
- `ntoskrnl!ExAllocatePool2` at `0x14000b5e9`

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
    qword_140019228 = (__int64)HashTable;
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
0x14000b5b4  mov     [rsp+HashTable], rcx
0x14000b5b9  sub     rsp, 28h
0x14000b5bd  lea     rcx, gBfsPipeMappingTable; PushLock
0x14000b5c4  mov     [rsp+28h+HashTable], 0
0x14000b5cd  call    cs:__imp_ExInitializePushLock
0x14000b5d4  nop     dword ptr [rax+rax+00h]
0x14000b5d9  mov     edx, 28h ; '('
0x14000b5de  mov     r8d, 54736642h
0x14000b5e4  mov     ecx, 100h
0x14000b5e9  call    cs:__imp_ExAllocatePool2
0x14000b5f0  nop     dword ptr [rax+rax+00h]
0x14000b5f5  mov     [rsp+28h+HashTable], rax
0x14000b5fa  test    rax, rax
0x14000b5fd  jnz     short loc_14000B606
0x14000b5ff  mov     eax, 0C0000017h
0x14000b604  jmp     short loc_14000B648
0x14000b606  xor     r8d, r8d; Flags
0x14000b609  lea     rcx, [rsp+28h+HashTable]; HashTable
0x14000b60e  xor     edx, edx; Shift
0x14000b610  call    cs:__imp_RtlCreateHashTable
0x14000b617  nop     dword ptr [rax+rax+00h]
0x14000b61c  test    al, al
0x14000b61e  jnz     short loc_14000B63A
0x14000b620  mov     rcx, [rsp+28h+HashTable]; P
0x14000b625  xor     edx, edx; Tag
0x14000b627  call    cs:__imp_ExFreePoolWithTag
0x14000b62e  nop     dword ptr [rax+rax+00h]
0x14000b633  mov     eax, 0C0000001h
0x14000b638  jmp     short loc_14000B648
0x14000b63a  mov     rax, [rsp+28h+HashTable]
0x14000b63f  mov     cs:qword_140019228, rax
0x14000b646  xor     eax, eax
0x14000b648  add     rsp, 28h
0x14000b64c  retn
```
