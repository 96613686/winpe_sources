# AipkAddEntryToAppxCache

- ea: `0x14002851c`
- end: `0x140028663`
- name: `AipkAddEntryToAppxCache`
- size: `327`
- prototype: `__int64 __fastcall(PRTL_DYNAMIC_HASH_TABLE_ENTRY Entry)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140036af0`

## callees

- `0x14002851c`
- `0x1400328b0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002863c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002863c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002855f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002855f`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400285d7`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400285d7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140028574`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140028574`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140028630`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140028630`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x1400285bb`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x1400285bb`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x1400285f3`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x1400285f3`
- `ntoskrnl!RtlCreateHashTable` at `0x140028595`
- `ntoskrnl!RtlCreateHashTable` at `0x140028595`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x140028611`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x140028611`

## pseudocode

```c
__int64 __fastcall AipkAddEntryToAppxCache(PRTL_DYNAMIC_HASH_TABLE_ENTRY Entry)
{
  ULONG_PTR Signature; // rax
  unsigned __int64 v2; // rdx
  char v4; // si
  __int64 v5; // r8
  ULONG_PTR v6; // rbx
  unsigned int v7; // ebx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY i; // rax
  _RTL_DYNAMIC_HASH_TABLE_CONTEXT Context; // [rsp+20h] [rbp-48h] BYREF

  Signature = Entry[1].Signature;
  v2 = ((unsigned __int64)LOWORD(Entry[1].Linkage.Blink) - 2) >> 1;
  memset(&Context, 0, sizeof(Context));
  v4 = 0;
  v5 = *(unsigned __int16 *)(Signature + 2 * v2);
  v6 = v5 + 1;
  if ( (_WORD)v5 )
    v6 = *(unsigned __int16 *)(Signature + 2 * v2);
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(&AipAppxInMemoryCache, 0);
  if ( HashTable || RtlCreateHashTable(&HashTable, 0, 0) )
  {
    for ( i = RtlLookupEntryHashTable(HashTable, v6, &Context); i; i = RtlGetNextEntryHashTable(HashTable, &Context) )
    {
      if ( RtlEqualUnicodeString((PCUNICODE_STRING)&Entry[1].Linkage.Blink, (PCUNICODE_STRING)&i[1].Linkage.Blink, 1u) )
        goto LABEL_12;
    }
    if ( !RtlInsertEntryHashTable(HashTable, Entry, v6, 0) )
      goto LABEL_5;
    v4 = 1;
LABEL_12:
    v7 = 0;
  }
  else
  {
LABEL_5:
    v7 = -1073741670;
  }
  ExReleasePushLockExclusiveEx(&AipAppxInMemoryCache, 0);
  KeLeaveCriticalRegion();
  if ( !v4 )
    AiFree(Entry);
  return v7;
}

```

## disassembly

```asm
0x14002851c  push    rbx
0x14002851e  push    rbp
0x14002851f  push    rsi
0x140028520  push    rdi
0x140028521  push    r14
0x140028523  sub     rsp, 40h
0x140028527  movzx   edx, word ptr [rcx+20h]
0x14002852b  xor     eax, eax
0x14002852d  sub     rdx, 2
0x140028531  mov     [rsp+68h+Context.Signature], rax
0x140028536  mov     rax, [rcx+28h]
0x14002853a  xorps   xmm0, xmm0
0x14002853d  shr     rdx, 1
0x140028540  xor     r14d, r14d
0x140028543  movups  xmmword ptr [rsp+68h+Context.ChainHead], xmm0
0x140028548  mov     rdi, rcx
0x14002854b  mov     sil, r14b
0x14002854e  movzx   r8d, word ptr [rax+rdx*2]
0x140028553  test    r8w, r8w
0x140028557  lea     rbx, [r8+1]
0x14002855b  cmovnz  rbx, r8
0x14002855f  call    cs:__imp_KeEnterCriticalRegion
0x140028566  nop     dword ptr [rax+rax+00h]
0x14002856b  xor     edx, edx
0x14002856d  lea     rcx, AipAppxInMemoryCache
0x140028574  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14002857b  nop     dword ptr [rax+rax+00h]
0x140028580  cmp     cs:HashTable, r14
0x140028587  jnz     short loc_1400285AC
0x140028589  xor     r8d, r8d; Flags
0x14002858c  lea     rcx, HashTable; HashTable
0x140028593  xor     edx, edx; Shift
0x140028595  call    cs:__imp_RtlCreateHashTable
0x14002859c  nop     dword ptr [rax+rax+00h]
0x1400285a1  test    al, al
0x1400285a3  jnz     short loc_1400285AC
0x1400285a5  mov     ebx, 0C000009Ah
0x1400285aa  jmp     short loc_140028627
0x1400285ac  mov     rcx, cs:HashTable; HashTable
0x1400285b3  lea     r8, [rsp+68h+Context]; Context
0x1400285b8  mov     rdx, rbx; Signature
0x1400285bb  call    cs:__imp_RtlLookupEntryHashTable
0x1400285c2  nop     dword ptr [rax+rax+00h]
0x1400285c7  test    rax, rax
0x1400285ca  jz      short loc_140028601
0x1400285cc  lea     rdx, [rax+20h]; String2
0x1400285d0  mov     r8b, 1; CaseInSensitive
0x1400285d3  lea     rcx, [rdi+20h]; String1
0x1400285d7  call    cs:__imp_RtlEqualUnicodeString
0x1400285de  nop     dword ptr [rax+rax+00h]
0x1400285e3  test    al, al
0x1400285e5  jnz     short loc_140028624
0x1400285e7  mov     rcx, cs:HashTable; HashTable
0x1400285ee  lea     rdx, [rsp+68h+Context]; Context
0x1400285f3  call    cs:__imp_RtlGetNextEntryHashTable
0x1400285fa  nop     dword ptr [rax+rax+00h]
0x1400285ff  jmp     short loc_1400285C7
0x140028601  mov     rcx, cs:HashTable; HashTable
0x140028608  xor     r9d, r9d; Context
0x14002860b  mov     r8, rbx; Signature
0x14002860e  mov     rdx, rdi; Entry
0x140028611  call    cs:__imp_RtlInsertEntryHashTable
0x140028618  nop     dword ptr [rax+rax+00h]
0x14002861d  test    al, al
0x14002861f  jz      short loc_1400285A5
0x140028621  mov     sil, 1
0x140028624  mov     ebx, r14d
0x140028627  xor     edx, edx
0x140028629  lea     rcx, AipAppxInMemoryCache
0x140028630  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140028637  nop     dword ptr [rax+rax+00h]
0x14002863c  call    cs:__imp_KeLeaveCriticalRegion
0x140028643  nop     dword ptr [rax+rax+00h]
0x140028648  test    sil, sil
0x14002864b  jnz     short loc_140028655
0x14002864d  mov     rcx, rdi
0x140028650  call    AiFree
0x140028655  mov     eax, ebx
0x140028657  add     rsp, 40h
0x14002865b  pop     r14
0x14002865d  pop     rdi
0x14002865e  pop     rsi
0x14002865f  pop     rbp
0x140028660  pop     rbx
0x140028661  retn
```
