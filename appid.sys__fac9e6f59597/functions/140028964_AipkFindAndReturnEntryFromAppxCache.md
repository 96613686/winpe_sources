# AipkFindAndReturnEntryFromAppxCache

- ea: `0x140028964`
- end: `0x140028a65`
- name: `AipkFindAndReturnEntryFromAppxCache`
- size: `257`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String1, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140028a6c`

## callees

- `0x1400288cc`
- `0x140028964`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140028a4d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140028a4d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400289a7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400289a7`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400289fa`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400289fa`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400289bc`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400289bc`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140028a41`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140028a41`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x1400289dc`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x1400289dc`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x140028a16`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x140028a16`

## pseudocode

```c
__int64 __fastcall AipkFindAndReturnEntryFromAppxCache(PCUNICODE_STRING String1, _QWORD *a2)
{
  PWSTR Buffer; // rax
  unsigned __int64 v3; // r8
  __int64 v5; // r9
  ULONG_PTR v6; // rbx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY i; // rax
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v8; // rbx
  unsigned int v9; // ebx
  struct _RTL_DYNAMIC_HASH_TABLE_CONTEXT Context; // [rsp+20h] [rbp-48h] BYREF

  Buffer = String1->Buffer;
  v3 = ((unsigned __int64)String1->Length - 2) >> 1;
  memset(&Context, 0, sizeof(Context));
  *a2 = 0;
  v5 = Buffer[v3];
  v6 = v5 + 1;
  if ( (_WORD)v5 )
    v6 = Buffer[v3];
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(&AipAppxInMemoryCache, 0);
  if ( HashTable )
  {
    for ( i = RtlLookupEntryHashTable(HashTable, v6, &Context); ; i = RtlGetNextEntryHashTable(HashTable, &Context) )
    {
      v8 = i;
      if ( !i )
        break;
      if ( RtlEqualUnicodeString(String1, (PCUNICODE_STRING)&i[1].Linkage.Blink, 1u) )
      {
        v9 = AipkCopyCacheEntry(v8);
        goto LABEL_10;
      }
    }
  }
  v9 = -1073741275;
LABEL_10:
  ExReleasePushLockSharedEx(&AipAppxInMemoryCache, 0);
  KeLeaveCriticalRegion();
  return v9;
}

```

## disassembly

```asm
0x140028964  push    rbx
0x140028966  push    rbp
0x140028967  push    rsi
0x140028968  push    rdi
0x140028969  sub     rsp, 48h
0x14002896d  movzx   r8d, word ptr [rcx]
0x140028971  xor     eax, eax
0x140028973  sub     r8, 2
0x140028977  mov     [rsp+68h+Context.Signature], rax
0x14002897c  mov     rax, [rcx+8]
0x140028980  xorps   xmm0, xmm0
0x140028983  shr     r8, 1
0x140028986  xor     ebp, ebp
0x140028988  movups  xmmword ptr [rsp+68h+Context.ChainHead], xmm0
0x14002898d  mov     rsi, rdx
0x140028990  mov     [rdx], rbp
0x140028993  mov     rdi, rcx
0x140028996  movzx   r9d, word ptr [rax+r8*2]
0x14002899b  test    r9w, r9w
0x14002899f  lea     rbx, [r9+1]
0x1400289a3  cmovnz  rbx, r9
0x1400289a7  call    cs:__imp_KeEnterCriticalRegion
0x1400289ae  nop     dword ptr [rax+rax+00h]
0x1400289b3  xor     edx, edx
0x1400289b5  lea     rcx, AipAppxInMemoryCache
0x1400289bc  call    cs:__imp_ExAcquirePushLockSharedEx
0x1400289c3  nop     dword ptr [rax+rax+00h]
0x1400289c8  mov     rcx, cs:HashTable; HashTable
0x1400289cf  test    rcx, rcx
0x1400289d2  jz      short loc_140028A33
0x1400289d4  lea     r8, [rsp+68h+Context]; Context
0x1400289d9  mov     rdx, rbx; Signature
0x1400289dc  call    cs:__imp_RtlLookupEntryHashTable
0x1400289e3  nop     dword ptr [rax+rax+00h]
0x1400289e8  mov     rbx, rax
0x1400289eb  test    rax, rax
0x1400289ee  jz      short loc_140028A33
0x1400289f0  lea     rdx, [rax+20h]; String2
0x1400289f4  mov     r8b, 1; CaseInSensitive
0x1400289f7  mov     rcx, rdi; String1
0x1400289fa  call    cs:__imp_RtlEqualUnicodeString
0x140028a01  nop     dword ptr [rax+rax+00h]
0x140028a06  test    al, al
0x140028a08  jnz     short loc_140028A24
0x140028a0a  mov     rcx, cs:HashTable; HashTable
0x140028a11  lea     rdx, [rsp+68h+Context]; Context
0x140028a16  call    cs:__imp_RtlGetNextEntryHashTable
0x140028a1d  nop     dword ptr [rax+rax+00h]
0x140028a22  jmp     short loc_1400289E8
0x140028a24  mov     rdx, rsi
0x140028a27  mov     rcx, rbx; Src
0x140028a2a  call    AipkCopyCacheEntry
0x140028a2f  mov     ebx, eax
0x140028a31  jmp     short loc_140028A38
0x140028a33  mov     ebx, 0C0000225h
0x140028a38  xor     edx, edx
0x140028a3a  lea     rcx, AipAppxInMemoryCache
0x140028a41  call    cs:__imp_ExReleasePushLockSharedEx
0x140028a48  nop     dword ptr [rax+rax+00h]
0x140028a4d  call    cs:__imp_KeLeaveCriticalRegion
0x140028a54  nop     dword ptr [rax+rax+00h]
0x140028a59  mov     eax, ebx
0x140028a5b  add     rsp, 48h
0x140028a5f  pop     rdi
0x140028a60  pop     rsi
0x140028a61  pop     rbp
0x140028a62  pop     rbx
0x140028a63  retn
```
