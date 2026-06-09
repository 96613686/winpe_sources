# BfsLookupPolicyEntryHashTable

- ea: `0x140008ca8`
- end: `0x140008d33`
- name: `BfsLookupPolicyEntryHashTable`
- size: `139`
- prototype: `__int64 __fastcall(PRTL_DYNAMIC_HASH_TABLE HashTable)`
- caller_count: `11`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140006c24`
- `0x140006d20`
- `0x140007044`
- `0x140007250`
- `0x140007890`
- `0x140007b60`
- `0x140007e5c`
- `0x140008598`
- `0x140008e84`
- `0x140009114`
- `0x14000a4bc`

## callees

- `0x140008ca8`

## import_xrefs

- `ntoskrnl!RtlLookupEntryHashTable` at `0x140008cce`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140008cce`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x140008d18`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x140008d18`
- `ntoskrnl!RtlEqualSid` at `0x140008ce9`
- `ntoskrnl!RtlEqualSid` at `0x140008d00`
- `ntoskrnl!RtlEqualSid` at `0x140008ce9`
- `ntoskrnl!RtlEqualSid` at `0x140008d00`

## pseudocode

```c
PRTL_DYNAMIC_HASH_TABLE_ENTRY __fastcall BfsLookupPolicyEntryHashTable(
        PRTL_DYNAMIC_HASH_TABLE HashTable,
        ULONG_PTR a2,
        void *a3,
        void *a4)
{
  PRTL_DYNAMIC_HASH_TABLE_ENTRY result; // rax
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v8; // rbx
  struct _RTL_DYNAMIC_HASH_TABLE_CONTEXT Context; // [rsp+20h] [rbp-48h] BYREF

  memset(&Context, 0, sizeof(Context));
  for ( result = RtlLookupEntryHashTable(HashTable, a2, &Context); ; result = RtlGetNextEntryHashTable(
                                                                                HashTable,
                                                                                &Context) )
  {
    v8 = result;
    if ( !result )
      break;
    if ( RtlEqualSid(a3, result[1].Linkage.Flink) && RtlEqualSid(a4, v8[1].Linkage.Blink) )
      return v8;
  }
  return result;
}

```

## disassembly

```asm
0x140008ca8  push    rbx
0x140008caa  push    rbp
0x140008cab  push    rsi
0x140008cac  push    rdi
0x140008cad  sub     rsp, 48h
0x140008cb1  mov     rbp, r8
0x140008cb4  xorps   xmm0, xmm0
0x140008cb7  xor     eax, eax
0x140008cb9  lea     r8, [rsp+68h+Context]; Context
0x140008cbe  movups  xmmword ptr [rsp+68h+Context.ChainHead], xmm0
0x140008cc3  mov     [rsp+68h+Context.Signature], rax
0x140008cc8  mov     rsi, r9
0x140008ccb  mov     rdi, rcx
0x140008cce  call    cs:__imp_RtlLookupEntryHashTable
0x140008cd5  nop     dword ptr [rax+rax+00h]
0x140008cda  mov     rbx, rax
0x140008cdd  test    rax, rax
0x140008ce0  jz      short loc_140008D29
0x140008ce2  mov     rdx, [rax+18h]; Sid2
0x140008ce6  mov     rcx, rbp; Sid1
0x140008ce9  call    cs:__imp_RtlEqualSid
0x140008cf0  nop     dword ptr [rax+rax+00h]
0x140008cf5  test    al, al
0x140008cf7  jz      short loc_140008D10
0x140008cf9  mov     rdx, [rbx+20h]; Sid2
0x140008cfd  mov     rcx, rsi; Sid1
0x140008d00  call    cs:__imp_RtlEqualSid
0x140008d07  nop     dword ptr [rax+rax+00h]
0x140008d0c  test    al, al
0x140008d0e  jnz     short loc_140008D26
0x140008d10  lea     rdx, [rsp+68h+Context]; Context
0x140008d15  mov     rcx, rdi; HashTable
0x140008d18  call    cs:__imp_RtlGetNextEntryHashTable
0x140008d1f  nop     dword ptr [rax+rax+00h]
0x140008d24  jmp     short loc_140008CDA
0x140008d26  mov     rax, rbx
0x140008d29  add     rsp, 48h
0x140008d2d  pop     rdi
0x140008d2e  pop     rsi
0x140008d2f  pop     rbp
0x140008d30  pop     rbx
0x140008d31  retn
```
