# BfsLookupPipeMappingEntryHashTable

- ea: `0x14000b6e0`
- end: `0x14000b78a`
- name: `BfsLookupPipeMappingEntryHashTable`
- size: `170`
- prototype: `__int64 __usercall@<rax>(PRTL_DYNAMIC_HASH_TABLE HashTable@<rcx>, PCUNICODE_STRING String2)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000b338`
- `0x14000b4c4`

## callees

- `0x14000b6e0`

## import_xrefs

- `ntoskrnl!RtlLookupEntryHashTable` at `0x14000b706`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14000b706`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14000b76f`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14000b76f`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000b757`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000b757`
- `ntoskrnl!RtlEqualSid` at `0x14000b721`
- `ntoskrnl!RtlEqualSid` at `0x14000b738`
- `ntoskrnl!RtlEqualSid` at `0x14000b721`
- `ntoskrnl!RtlEqualSid` at `0x14000b738`

## pseudocode

```c
PRTL_DYNAMIC_HASH_TABLE_ENTRY __fastcall BfsLookupPipeMappingEntryHashTable(
        PRTL_DYNAMIC_HASH_TABLE HashTable,
        ULONG_PTR a2,
        void *a3,
        void *a4,
        PCUNICODE_STRING String2)
{
  PRTL_DYNAMIC_HASH_TABLE_ENTRY result; // rax
  const UNICODE_STRING *v9; // rbx
  struct _RTL_DYNAMIC_HASH_TABLE_CONTEXT Context; // [rsp+20h] [rbp-48h] BYREF

  memset(&Context, 0, sizeof(Context));
  for ( result = RtlLookupEntryHashTable(HashTable, a2, &Context); ; result = RtlGetNextEntryHashTable(
                                                                                HashTable,
                                                                                &Context) )
  {
    v9 = (const UNICODE_STRING *)result;
    if ( !result )
      break;
    if ( RtlEqualSid(result[1].Linkage.Blink, a3)
      && RtlEqualSid(v9[2].Buffer, a4)
      && RtlEqualUnicodeString(v9 + 3, String2, 1u) )
    {
      return (PRTL_DYNAMIC_HASH_TABLE_ENTRY)v9;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000b6e0  push    rbx
0x14000b6e2  push    rbp
0x14000b6e3  push    rsi
0x14000b6e4  push    rdi
0x14000b6e5  sub     rsp, 48h
0x14000b6e9  mov     rbp, r8
0x14000b6ec  xorps   xmm0, xmm0
0x14000b6ef  xor     eax, eax
0x14000b6f1  lea     r8, [rsp+68h+Context]; Context
0x14000b6f6  movups  xmmword ptr [rsp+68h+Context.ChainHead], xmm0
0x14000b6fb  mov     [rsp+68h+Context.Signature], rax
0x14000b700  mov     rsi, r9
0x14000b703  mov     rdi, rcx
0x14000b706  call    cs:__imp_RtlLookupEntryHashTable
0x14000b70d  nop     dword ptr [rax+rax+00h]
0x14000b712  mov     rbx, rax
0x14000b715  test    rax, rax
0x14000b718  jz      short loc_14000B780
0x14000b71a  mov     rcx, [rax+20h]; Sid1
0x14000b71e  mov     rdx, rbp; Sid2
0x14000b721  call    cs:__imp_RtlEqualSid
0x14000b728  nop     dword ptr [rax+rax+00h]
0x14000b72d  test    al, al
0x14000b72f  jz      short loc_14000B767
0x14000b731  mov     rcx, [rbx+28h]; Sid1
0x14000b735  mov     rdx, rsi; Sid2
0x14000b738  call    cs:__imp_RtlEqualSid
0x14000b73f  nop     dword ptr [rax+rax+00h]
0x14000b744  test    al, al
0x14000b746  jz      short loc_14000B767
0x14000b748  mov     rdx, [rsp+68h+String2]; String2
0x14000b750  lea     rcx, [rbx+30h]; String1
0x14000b754  mov     r8b, 1; CaseInSensitive
0x14000b757  call    cs:__imp_RtlEqualUnicodeString
0x14000b75e  nop     dword ptr [rax+rax+00h]
0x14000b763  test    al, al
0x14000b765  jnz     short loc_14000B77D
0x14000b767  lea     rdx, [rsp+68h+Context]; Context
0x14000b76c  mov     rcx, rdi; HashTable
0x14000b76f  call    cs:__imp_RtlGetNextEntryHashTable
0x14000b776  nop     dword ptr [rax+rax+00h]
0x14000b77b  jmp     short loc_14000B712
0x14000b77d  mov     rax, rbx
0x14000b780  add     rsp, 48h
0x14000b784  pop     rdi
0x14000b785  pop     rsi
0x14000b786  pop     rbp
0x14000b787  pop     rbx
0x14000b788  retn
```
