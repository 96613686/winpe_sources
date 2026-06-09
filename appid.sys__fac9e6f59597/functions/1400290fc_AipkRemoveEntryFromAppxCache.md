# AipkRemoveEntryFromAppxCache

- ea: `0x1400290fc`
- end: `0x140029206`
- name: `AipkRemoveEntryFromAppxCache`
- size: `266`
- prototype: `void __fastcall(const UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140036af0`

## callees

- `0x1400290fc`
- `0x1400328b0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400291e9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400291e9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002913d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002913d`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140029190`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140029190`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140029152`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140029152`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400291dd`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400291dd`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1400291c0`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1400291c0`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140029172`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140029172`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x1400291ac`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x1400291ac`

## pseudocode

```c
void __fastcall AipkRemoveEntryFromAppxCache(const UNICODE_STRING *a1)
{
  const UNICODE_STRING *v1; // rdi
  PWSTR Buffer; // rax
  unsigned __int64 v3; // rcx
  __int64 v4; // r8
  ULONG_PTR v5; // rbx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY i; // rax
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v7; // rbx
  struct _RTL_DYNAMIC_HASH_TABLE_CONTEXT Context; // [rsp+20h] [rbp-28h] BYREF

  v1 = a1 + 2;
  Buffer = a1[2].Buffer;
  v3 = ((unsigned __int64)a1[2].Length - 2) >> 1;
  memset(&Context, 0, sizeof(Context));
  v4 = Buffer[v3];
  v5 = v4 + 1;
  if ( (_WORD)v4 )
    v5 = Buffer[v3];
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(&AipAppxInMemoryCache, 0);
  if ( HashTable )
  {
    for ( i = RtlLookupEntryHashTable(HashTable, v5, &Context); ; i = RtlGetNextEntryHashTable(HashTable, &Context) )
    {
      v7 = i;
      if ( !i )
        break;
      if ( RtlEqualUnicodeString(v1, (PCUNICODE_STRING)&i[1].Linkage.Blink, 1u) )
      {
        RtlRemoveEntryHashTable(HashTable, v7, 0);
        AiFree(v7);
        break;
      }
    }
  }
  ExReleasePushLockExclusiveEx(&AipAppxInMemoryCache, 0);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x1400290fc  mov     [rsp+arg_0], rbx
0x140029101  mov     [rsp+arg_8], rsi
0x140029106  push    rdi
0x140029107  sub     rsp, 40h
0x14002910b  lea     rdi, [rcx+20h]
0x14002910f  xor     eax, eax
0x140029111  movzx   ecx, word ptr [rdi]
0x140029114  xorps   xmm0, xmm0
0x140029117  sub     rcx, 2
0x14002911b  mov     [rsp+48h+Context.Signature], rax
0x140029120  mov     rax, [rdi+8]
0x140029124  shr     rcx, 1
0x140029127  movups  xmmword ptr [rsp+48h+Context.ChainHead], xmm0
0x14002912c  movzx   r8d, word ptr [rax+rcx*2]
0x140029131  test    r8w, r8w
0x140029135  lea     rbx, [r8+1]
0x140029139  cmovnz  rbx, r8
0x14002913d  call    cs:__imp_KeEnterCriticalRegion
0x140029144  nop     dword ptr [rax+rax+00h]
0x140029149  xor     edx, edx
0x14002914b  lea     rcx, AipAppxInMemoryCache
0x140029152  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140029159  nop     dword ptr [rax+rax+00h]
0x14002915e  mov     rcx, cs:HashTable; HashTable
0x140029165  test    rcx, rcx
0x140029168  jz      short loc_1400291D4
0x14002916a  lea     r8, [rsp+48h+Context]; Context
0x14002916f  mov     rdx, rbx; Signature
0x140029172  call    cs:__imp_RtlLookupEntryHashTable
0x140029179  nop     dword ptr [rax+rax+00h]
0x14002917e  mov     rbx, rax
0x140029181  test    rax, rax
0x140029184  jz      short loc_1400291D4
0x140029186  lea     rdx, [rax+20h]; String2
0x14002918a  mov     r8b, 1; CaseInSensitive
0x14002918d  mov     rcx, rdi; String1
0x140029190  call    cs:__imp_RtlEqualUnicodeString
0x140029197  nop     dword ptr [rax+rax+00h]
0x14002919c  mov     rcx, cs:HashTable; HashTable
0x1400291a3  test    al, al
0x1400291a5  jnz     short loc_1400291BA
0x1400291a7  lea     rdx, [rsp+48h+Context]; Context
0x1400291ac  call    cs:__imp_RtlGetNextEntryHashTable
0x1400291b3  nop     dword ptr [rax+rax+00h]
0x1400291b8  jmp     short loc_14002917E
0x1400291ba  xor     r8d, r8d; Context
0x1400291bd  mov     rdx, rbx; Entry
0x1400291c0  call    cs:__imp_RtlRemoveEntryHashTable
0x1400291c7  nop     dword ptr [rax+rax+00h]
0x1400291cc  mov     rcx, rbx
0x1400291cf  call    AiFree
0x1400291d4  xor     edx, edx
0x1400291d6  lea     rcx, AipAppxInMemoryCache
0x1400291dd  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400291e4  nop     dword ptr [rax+rax+00h]
0x1400291e9  call    cs:__imp_KeLeaveCriticalRegion
0x1400291f0  nop     dword ptr [rax+rax+00h]
0x1400291f5  mov     rbx, [rsp+48h+arg_0]
0x1400291fa  mov     rsi, [rsp+48h+arg_8]
0x1400291ff  add     rsp, 40h
0x140029203  pop     rdi
0x140029204  retn
```
