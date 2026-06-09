# CPhotoPropertyItemList::GetItem(_tagpropertykey const *,tagPROPVARIANT *)

- ea: `0x18000a160`
- end: `0x18000a1e7`
- name: `?GetItem@CPhotoPropertyItemList@@QEAAJPEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z`
- size: `135`
- prototype: `int(CPhotoPropertyItemList *__hidden this, const struct _tagpropertykey *, struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180014ba4`
- `0x18001b1fc`

## callees

- `0x18000a160`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000a1c9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a17b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a17b`

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
0x18000a160  mov     [rsp+arg_0], rbx
0x18000a165  mov     [rsp+arg_8], rsi
0x18000a16a  push    rdi
0x18000a16b  sub     rsp, 20h
0x18000a16f  mov     rbx, rcx
0x18000a172  mov     rsi, r8
0x18000a175  mov     rcx, r8; pvar
0x18000a178  mov     rdi, rdx
0x18000a17b  call    cs:__imp_PropVariantClear
0x18000a181  mov     rdx, [rbx]
0x18000a184  test    rdx, rdx
0x18000a187  jnz     short loc_18000A19B
0x18000a189  xor     eax, eax
0x18000a18b  mov     rbx, [rsp+28h+arg_0]
0x18000a190  mov     rsi, [rsp+28h+arg_8]
0x18000a195  add     rsp, 20h
0x18000a199  pop     rdi
0x18000a19a  retn
0x18000a19b  mov     eax, [rdi+10h]
0x18000a19e  xchg    ax, ax
0x18000a1a0  cmp     [rdx+10h], eax
0x18000a1a3  jz      short loc_18000A1D0
0x18000a1a5  mov     rdx, [rdx+38h]
0x18000a1a9  test    rdx, rdx
0x18000a1ac  jnz     short loc_18000A1A0
0x18000a1ae  test    rdx, rdx
0x18000a1b1  jz      short loc_18000A189
0x18000a1b3  add     rdx, 18h
0x18000a1b7  mov     rcx, rsi
0x18000a1ba  mov     rbx, [rsp+28h+arg_0]
0x18000a1bf  mov     rsi, [rsp+28h+arg_8]
0x18000a1c4  add     rsp, 20h
0x18000a1c8  pop     rdi
0x18000a1c9  jmp     cs:__imp_PropVariantCopy
0x18000a1d0  mov     rcx, [rdx]
0x18000a1d3  sub     rcx, [rdi]
0x18000a1d6  jnz     short loc_18000A1E0
0x18000a1d8  mov     rcx, [rdx+8]
0x18000a1dc  sub     rcx, [rdi+8]
0x18000a1e0  test    rcx, rcx
0x18000a1e3  jnz     short loc_18000A1A5
0x18000a1e5  jmp     short loc_18000A1AE
```
