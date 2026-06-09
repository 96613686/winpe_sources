# BfsLookupPipeMappingEntryHashTable

- ea: `0x14000b870`
- end: `0x14000b91a`
- name: `BfsLookupPipeMappingEntryHashTable`
- size: `170`
- prototype: `PRTL_DYNAMIC_HASH_TABLE_ENTRY __fastcall(PRTL_DYNAMIC_HASH_TABLE HashTable, ULONG_PTR, void *, void *, PCUNICODE_STRING String2)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000b4c8`
- `0x14000b654`

## callees

- `0x14000b870`

## import_xrefs

- `ntoskrnl!RtlLookupEntryHashTable` at `0x14000b896`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14000b896`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14000b8ff`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14000b8ff`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000b8e7`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000b8e7`
- `ntoskrnl!RtlEqualSid` at `0x14000b8b1`
- `ntoskrnl!RtlEqualSid` at `0x14000b8c8`
- `ntoskrnl!RtlEqualSid` at `0x14000b8b1`
- `ntoskrnl!RtlEqualSid` at `0x14000b8c8`

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
0x14000b870  push    rbx
0x14000b872  push    rbp
0x14000b873  push    rsi
0x14000b874  push    rdi
0x14000b875  sub     rsp, 48h
0x14000b879  mov     rbp, r8
0x14000b87c  xorps   xmm0, xmm0
0x14000b87f  xor     eax, eax
0x14000b881  lea     r8, [rsp+68h+Context]; Context
0x14000b886  movups  xmmword ptr [rsp+68h+Context.ChainHead], xmm0
0x14000b88b  mov     [rsp+68h+Context.Signature], rax
0x14000b890  mov     rsi, r9
0x14000b893  mov     rdi, rcx
0x14000b896  call    cs:__imp_RtlLookupEntryHashTable
0x14000b89d  nop     dword ptr [rax+rax+00h]
0x14000b8a2  mov     rbx, rax
0x14000b8a5  test    rax, rax
0x14000b8a8  jz      short loc_14000B910
0x14000b8aa  mov     rcx, [rax+20h]; Sid1
0x14000b8ae  mov     rdx, rbp; Sid2
0x14000b8b1  call    cs:__imp_RtlEqualSid
0x14000b8b8  nop     dword ptr [rax+rax+00h]
0x14000b8bd  test    al, al
0x14000b8bf  jz      short loc_14000B8F7
0x14000b8c1  mov     rcx, [rbx+28h]; Sid1
0x14000b8c5  mov     rdx, rsi; Sid2
0x14000b8c8  call    cs:__imp_RtlEqualSid
0x14000b8cf  nop     dword ptr [rax+rax+00h]
0x14000b8d4  test    al, al
0x14000b8d6  jz      short loc_14000B8F7
0x14000b8d8  mov     rdx, [rsp+68h+String2]; String2
0x14000b8e0  lea     rcx, [rbx+30h]; String1
0x14000b8e4  mov     r8b, 1; CaseInSensitive
0x14000b8e7  call    cs:__imp_RtlEqualUnicodeString
0x14000b8ee  nop     dword ptr [rax+rax+00h]
0x14000b8f3  test    al, al
0x14000b8f5  jnz     short loc_14000B90D
0x14000b8f7  lea     rdx, [rsp+68h+Context]; Context
0x14000b8fc  mov     rcx, rdi; HashTable
0x14000b8ff  call    cs:__imp_RtlGetNextEntryHashTable
0x14000b906  nop     dword ptr [rax+rax+00h]
0x14000b90b  jmp     short loc_14000B8A2
0x14000b90d  mov     rax, rbx
0x14000b910  add     rsp, 48h
0x14000b914  pop     rdi
0x14000b915  pop     rsi
0x14000b916  pop     rbp
0x14000b917  pop     rbx
0x14000b918  retn
```
