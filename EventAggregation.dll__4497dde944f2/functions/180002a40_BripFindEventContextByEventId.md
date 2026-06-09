# BripFindEventContextByEventId

- ea: `0x180002a40`
- end: `0x180002ad1`
- name: `BripFindEventContextByEventId`
- size: `145`
- prototype: `__int64 __fastcall(void *Source1)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800020b0`
- `0x180002130`
- `0x1800029b0`

## callees

- `0x180002a40`

## import_xrefs

- `ntdll!RtlComputeCrc32` at `0x180002a6a`
- `ntdll!RtlComputeCrc32` at `0x180002a6a`
- `ntdll!RtlGetNextEntryHashTable` at `0x180002ac7`
- `ntdll!RtlGetNextEntryHashTable` at `0x180002ac7`
- `ntdll!RtlLookupEntryHashTable` at `0x180002a86`
- `ntdll!RtlLookupEntryHashTable` at `0x180002a86`
- `ntdll!RtlCompareMemory` at `0x180002aa1`
- `ntdll!RtlCompareMemory` at `0x180002aa1`

## pseudocode

```c
__int64 __fastcall BripFindEventContextByEventId(UCHAR *Source1)
{
  ULONG v2; // eax
  __int64 v3; // rdx
  __int64 result; // rax
  __int64 v5; // rbx
  __int128 v6; // [rsp+20h] [rbp-28h] BYREF
  __int64 v7; // [rsp+30h] [rbp-18h]

  v7 = 0;
  v6 = 0;
  v2 = RtlComputeCrc32(0, Source1, 8u);
  v3 = 1;
  if ( v2 )
    v3 = v2;
  for ( result = RtlLookupEntryHashTable(BrokeredEventTable, v3, &v6);
        ;
        result = RtlGetNextEntryHashTable(BrokeredEventTable, &v6) )
  {
    v5 = result;
    if ( !result )
      break;
    if ( RtlCompareMemory(Source1, (const void *)(result + 32), 8u) == 8 )
      return v5;
  }
  return result;
}

```

## disassembly

```asm
0x180002a40  mov     [rsp+arg_0], rbx
0x180002a45  push    rdi
0x180002a46  sub     rsp, 40h
0x180002a4a  mov     rdi, rcx
0x180002a4d  mov     [rsp+48h+var_18], 0
0x180002a56  xorps   xmm0, xmm0
0x180002a59  mov     rdx, rcx; Buffer
0x180002a5c  xor     ecx, ecx; InitialCrc
0x180002a5e  mov     r8d, 8; Length
0x180002a64  movdqu  [rsp+48h+var_28], xmm0
0x180002a6a  call    cs:__imp_RtlComputeCrc32
0x180002a70  mov     rcx, cs:BrokeredEventTable
0x180002a77  lea     r8, [rsp+48h+var_28]
0x180002a7c  test    eax, eax
0x180002a7e  mov     edx, 1
0x180002a83  cmovnz  edx, eax
0x180002a86  call    cs:__imp_RtlLookupEntryHashTable
0x180002a8c  mov     rbx, rax
0x180002a8f  test    rax, rax
0x180002a92  jz      short loc_180002ACF
0x180002a94  lea     rdx, [rax+20h]; Source2
0x180002a98  mov     r8d, 8; Length
0x180002a9e  mov     rcx, rdi; Source1
0x180002aa1  call    cs:__imp_RtlCompareMemory
0x180002aa7  cmp     rax, 8
0x180002aab  jnz     short loc_180002ABB
0x180002aad  mov     rax, rbx
0x180002ab0  mov     rbx, [rsp+48h+arg_0]
0x180002ab5  add     rsp, 40h
0x180002ab9  pop     rdi
0x180002aba  retn
0x180002abb  mov     rcx, cs:BrokeredEventTable
0x180002ac2  lea     rdx, [rsp+48h+var_28]
0x180002ac7  call    cs:__imp_RtlGetNextEntryHashTable
0x180002acd  jmp     short loc_180002A8C
0x180002acf  jmp     short loc_180002AB0
```
