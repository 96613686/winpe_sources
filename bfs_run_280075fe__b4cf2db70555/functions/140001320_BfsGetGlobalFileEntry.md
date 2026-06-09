# BfsGetGlobalFileEntry

- ea: `0x140001320`
- end: `0x1400013cc`
- name: `BfsGetGlobalFileEntry`
- size: `172`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400012b0`
- `0x140001be0`
- `0x14000bf64`
- `0x14000c658`
- `0x14000d5a0`

## callees

- `0x140001320`
- `0x1400013e0`

## import_xrefs

- `ntoskrnl!RtlLookupEntryHashTable` at `0x140001369`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140001369`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x1400013b0`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x1400013b0`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140001398`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140001398`

## pseudocode

```c
PRTL_DYNAMIC_HASH_TABLE_ENTRY __fastcall BfsGetGlobalFileEntry(__int64 a1, UNICODE_STRING *a2)
{
  struct _RTL_DYNAMIC_HASH_TABLE *v2; // rdi
  ULONG_PTR v4; // rdx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY result; // rax
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v6; // rbx
  _RTL_DYNAMIC_HASH_TABLE_CONTEXT Context; // [rsp+20h] [rbp-28h] BYREF
  ULONG_PTR Signature; // [rsp+50h] [rbp+8h] BYREF

  v2 = *(struct _RTL_DYNAMIC_HASH_TABLE **)(a1 + 40);
  Signature = 0;
  memset(&Context, 0, sizeof(Context));
  BfsUpdateUnicodeStringHash(&a2->Length, &Signature);
  v4 = Signature;
  if ( !Signature )
    v4 = -1;
  for ( result = RtlLookupEntryHashTable(v2, v4, &Context); ; result = RtlGetNextEntryHashTable(v2, &Context) )
  {
    v6 = result;
    if ( !result )
      break;
    if ( RtlEqualUnicodeString(a2, (PCUNICODE_STRING)&result[2].Signature, 1u) )
      return v6;
  }
  return result;
}

```

## disassembly

```asm
0x140001320  mov     [rsp+arg_8], rbx
0x140001325  mov     [rsp+arg_10], rsi
0x14000132a  push    rdi
0x14000132b  sub     rsp, 40h
0x14000132f  mov     rdi, [rcx+28h]
0x140001333  mov     rsi, rdx
0x140001336  xor     eax, eax
0x140001338  lea     rdx, [rsp+48h+Signature]
0x14000133d  xorps   xmm0, xmm0
0x140001340  mov     [rsp+48h+Context.Signature], rax
0x140001345  mov     rcx, rsi
0x140001348  mov     [rsp+48h+Signature], rax
0x14000134d  movups  xmmword ptr [rsp+48h+Context.ChainHead], xmm0
0x140001352  call    BfsUpdateUnicodeStringHash
0x140001357  mov     rdx, [rsp+48h+Signature]; Signature
0x14000135c  test    rdx, rdx
0x14000135f  jz      short loc_1400013BE
0x140001361  lea     r8, [rsp+48h+Context]; Context
0x140001366  mov     rcx, rdi; HashTable
0x140001369  call    cs:__imp_RtlLookupEntryHashTable
0x140001370  nop     dword ptr [rax+rax+00h]
0x140001375  mov     rbx, rax
0x140001378  test    rax, rax
0x14000137b  jnz     short loc_14000138E
0x14000137d  mov     rbx, [rsp+48h+arg_8]
0x140001382  mov     rsi, [rsp+48h+arg_10]
0x140001387  add     rsp, 40h
0x14000138b  pop     rdi
0x14000138c  retn
0x14000138e  lea     rdx, [rbx+40h]; String2
0x140001392  mov     r8b, 1; CaseInSensitive
0x140001395  mov     rcx, rsi; String1
0x140001398  call    cs:__imp_RtlEqualUnicodeString
0x14000139f  nop     dword ptr [rax+rax+00h]
0x1400013a4  test    al, al
0x1400013a6  jnz     short loc_1400013C7
0x1400013a8  lea     rdx, [rsp+48h+Context]; Context
0x1400013ad  mov     rcx, rdi; HashTable
0x1400013b0  call    cs:__imp_RtlGetNextEntryHashTable
0x1400013b7  nop     dword ptr [rax+rax+00h]
0x1400013bc  jmp     short loc_140001375
0x1400013be  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x1400013c5  jmp     short loc_140001361
0x1400013c7  mov     rax, rbx
0x1400013ca  jmp     short loc_14000137D
```
