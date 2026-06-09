# CPhotoPropertyItemList::GetItem(_tagpropertykey const *,tagPROPVARIANT *)

- ea: `0x18000a720`
- end: `0x18000a7b1`
- name: `?GetItem@CPhotoPropertyItemList@@QEAAJPEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z`
- size: `145`
- prototype: `int(CPhotoPropertyItemList *__hidden this, const struct _tagpropertykey *, struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180015594`
- `0x18001beb8`

## callees

- `0x18000a720`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000a78e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a73b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a73b`

## pseudocode

```c
HRESULT __fastcall CPhotoPropertyItemList::GetItem(
        CPhotoPropertyItemList *this,
        const struct _tagpropertykey *a2,
        struct tagPROPVARIANT *a3)
{
  __int64 v6; // rdx
  __int64 v8; // rcx

  PropVariantClear(a3);
  v6 = *(_QWORD *)this;
  if ( !*(_QWORD *)this )
    return 0;
  do
  {
    if ( *(_DWORD *)(v6 + 16) == a2->pid )
    {
      v8 = *(_QWORD *)v6 - *(_QWORD *)&a2->fmtid.Data1;
      if ( *(_QWORD *)v6 == *(_QWORD *)&a2->fmtid.Data1 )
        v8 = *(_QWORD *)(v6 + 8) - *(_QWORD *)a2->fmtid.Data4;
      if ( !v8 )
        break;
    }
    v6 = *(_QWORD *)(v6 + 56);
  }
  while ( v6 );
  if ( v6 )
    return PropVariantCopy(a3, (const PROPVARIANT *)(v6 + 24));
  else
    return 0;
}

```

## disassembly

```asm
0x18000a720  mov     [rsp+arg_0], rbx
0x18000a725  mov     [rsp+arg_8], rsi
0x18000a72a  push    rdi
0x18000a72b  sub     rsp, 20h
0x18000a72f  mov     rbx, rcx
0x18000a732  mov     rsi, r8
0x18000a735  mov     rcx, r8; pvar
0x18000a738  mov     rdi, rdx
0x18000a73b  call    cs:__imp_PropVariantClear
0x18000a742  nop     dword ptr [rax+rax+00h]
0x18000a747  mov     rdx, [rbx]
0x18000a74a  test    rdx, rdx
0x18000a74d  jnz     short loc_18000A762
0x18000a74f  xor     eax, eax
0x18000a751  mov     rbx, [rsp+28h+arg_0]
0x18000a756  mov     rsi, [rsp+28h+arg_8]
0x18000a75b  add     rsp, 20h
0x18000a75f  pop     rdi
0x18000a760  retn
0x18000a762  mov     eax, [rdi+10h]
0x18000a765  cmp     [rdx+10h], eax
0x18000a768  jz      short loc_18000A79A
0x18000a76a  mov     rdx, [rdx+38h]
0x18000a76e  test    rdx, rdx
0x18000a771  jnz     short loc_18000A765
0x18000a773  test    rdx, rdx
0x18000a776  jz      short loc_18000A74F
0x18000a778  add     rdx, 18h
0x18000a77c  mov     rcx, rsi
0x18000a77f  mov     rbx, [rsp+28h+arg_0]
0x18000a784  mov     rsi, [rsp+28h+arg_8]
0x18000a789  add     rsp, 20h
0x18000a78d  pop     rdi
0x18000a78e  jmp     cs:__imp_PropVariantCopy
0x18000a79a  mov     rcx, [rdx]
0x18000a79d  sub     rcx, [rdi]
0x18000a7a0  jnz     short loc_18000A7AA
0x18000a7a2  mov     rcx, [rdx+8]
0x18000a7a6  sub     rcx, [rdi+8]
0x18000a7aa  test    rcx, rcx
0x18000a7ad  jnz     short loc_18000A76A
0x18000a7af  jmp     short loc_18000A773
```
