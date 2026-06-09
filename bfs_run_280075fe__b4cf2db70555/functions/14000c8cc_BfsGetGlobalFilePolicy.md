# BfsGetGlobalFilePolicy

- ea: `0x14000c8cc`
- end: `0x14000c99d`
- name: `BfsGetGlobalFilePolicy`
- size: `209`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14000d5a0`
- `0x14000d848`

## callees

- `0x140001bc0`
- `0x14000c8cc`
- `0x140012bc8`

## import_xrefs

- `ntoskrnl!RtlLookupEntryHashTable` at `0x14000c938`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14000c938`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14000c982`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14000c982`
- `ntoskrnl!RtlEqualSid` at `0x14000c953`
- `ntoskrnl!RtlEqualSid` at `0x14000c96a`
- `ntoskrnl!RtlEqualSid` at `0x14000c953`
- `ntoskrnl!RtlEqualSid` at `0x14000c96a`

## pseudocode

```c
PRTL_DYNAMIC_HASH_TABLE_ENTRY __fastcall BfsGetGlobalFilePolicy(__int64 a1, unsigned __int8 *a2, unsigned __int8 *a3)
{
  struct _RTL_DYNAMIC_HASH_TABLE *v3; // rbp
  int v5; // edx
  ULONG_PTR v7; // rax
  PRTL_DYNAMIC_HASH_TABLE_ENTRY result; // rax
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v9; // rbx
  struct _RTL_DYNAMIC_HASH_TABLE_CONTEXT Context; // [rsp+20h] [rbp-48h] BYREF
  __int64 v11; // [rsp+70h] [rbp+8h] BYREF

  v3 = *(struct _RTL_DYNAMIC_HASH_TABLE **)(a1 + 88);
  v5 = a2[1];
  v11 = 0;
  memset(&Context, 0, sizeof(Context));
  BfsUpdateHash(a2, (unsigned int)(4 * v5 + 8), &v11);
  BfsUpdateHash(a3, 4 * (unsigned int)a3[1] + 8, &v11);
  v7 = BfsFinalHash(&v11);
  for ( result = RtlLookupEntryHashTable(v3, v7, &Context); ; result = RtlGetNextEntryHashTable(v3, &Context) )
  {
    v9 = result;
    if ( !result )
      break;
    if ( RtlEqualSid(a2, result[1].Linkage.Flink) && RtlEqualSid(a3, v9[1].Linkage.Blink) )
      return v9;
  }
  return result;
}

```

## disassembly

```asm
0x14000c8cc  push    rbx
0x14000c8ce  push    rbp
0x14000c8cf  push    rsi
0x14000c8d0  push    rdi
0x14000c8d1  sub     rsp, 48h
0x14000c8d5  mov     rbp, [rcx+58h]
0x14000c8d9  mov     rsi, rdx
0x14000c8dc  movzx   edx, byte ptr [rdx+1]
0x14000c8e0  xor     eax, eax
0x14000c8e2  mov     rdi, r8
0x14000c8e5  mov     [rsp+68h+Context.Signature], rax
0x14000c8ea  xorps   xmm0, xmm0
0x14000c8ed  mov     [rsp+68h+arg_0], rax
0x14000c8f2  lea     r8, [rsp+68h+arg_0]
0x14000c8f7  mov     rcx, rsi
0x14000c8fa  lea     edx, ds:8[rdx*4]
0x14000c901  movups  xmmword ptr [rsp+68h+Context.ChainHead], xmm0
0x14000c906  call    BfsUpdateHash
0x14000c90b  movzx   edx, byte ptr [rdi+1]
0x14000c90f  lea     r8, [rsp+68h+arg_0]
0x14000c914  mov     rcx, rdi
0x14000c917  lea     edx, ds:8[rdx*4]
0x14000c91e  call    BfsUpdateHash
0x14000c923  lea     rcx, [rsp+68h+arg_0]
0x14000c928  call    BfsFinalHash
0x14000c92d  mov     rdx, rax; Signature
0x14000c930  lea     r8, [rsp+68h+Context]; Context
0x14000c935  mov     rcx, rbp; HashTable
0x14000c938  call    cs:__imp_RtlLookupEntryHashTable
0x14000c93f  nop     dword ptr [rax+rax+00h]
0x14000c944  mov     rbx, rax
0x14000c947  test    rax, rax
0x14000c94a  jz      short loc_14000C993
0x14000c94c  mov     rdx, [rax+18h]; Sid2
0x14000c950  mov     rcx, rsi; Sid1
0x14000c953  call    cs:__imp_RtlEqualSid
0x14000c95a  nop     dword ptr [rax+rax+00h]
0x14000c95f  test    al, al
0x14000c961  jz      short loc_14000C97A
0x14000c963  mov     rdx, [rbx+20h]; Sid2
0x14000c967  mov     rcx, rdi; Sid1
0x14000c96a  call    cs:__imp_RtlEqualSid
0x14000c971  nop     dword ptr [rax+rax+00h]
0x14000c976  test    al, al
0x14000c978  jnz     short loc_14000C990
0x14000c97a  lea     rdx, [rsp+68h+Context]; Context
0x14000c97f  mov     rcx, rbp; HashTable
0x14000c982  call    cs:__imp_RtlGetNextEntryHashTable
0x14000c989  nop     dword ptr [rax+rax+00h]
0x14000c98e  jmp     short loc_14000C944
0x14000c990  mov     rax, rbx
0x14000c993  add     rsp, 48h
0x14000c997  pop     rdi
0x14000c998  pop     rsi
0x14000c999  pop     rbp
0x14000c99a  pop     rbx
0x14000c99b  retn
```
