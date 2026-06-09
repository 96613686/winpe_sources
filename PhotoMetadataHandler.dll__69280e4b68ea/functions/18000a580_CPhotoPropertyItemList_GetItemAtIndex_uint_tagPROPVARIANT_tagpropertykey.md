# CPhotoPropertyItemList::GetItemAtIndex(uint,tagPROPVARIANT *,_tagpropertykey *)

- ea: `0x18000a580`
- end: `0x18000a5de`
- name: `?GetItemAtIndex@CPhotoPropertyItemList@@QEAAJIPEAUtagPROPVARIANT@@PEAU_tagpropertykey@@@Z`
- size: `94`
- prototype: `__int64 __fastcall(CPhotoPropertyItemList *__hidden this, unsigned int, struct tagPROPVARIANT *, struct _tagpropertykey *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001d094`

## callees

- `0x18000a580`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000a5ce`

## pseudocode

```c
HRESULT __fastcall CPhotoPropertyItemList::GetItemAtIndex(
        CPhotoPropertyItemList *this,
        int a2,
        struct tagPROPVARIANT *a3,
        struct _tagpropertykey *a4)
{
  int v5; // eax
  __int64 v6; // rdx

  v5 = 0;
  v6 = *(_QWORD *)this;
  if ( !*(_QWORD *)this )
    return -2147467259;
  while ( *(_BYTE *)(v6 + 49) == 1 )
  {
LABEL_8:
    v6 = *(_QWORD *)(v6 + 56);
    if ( !v6 )
      return -2147467259;
  }
  if ( v5 != a2 )
  {
    ++v5;
    goto LABEL_8;
  }
  if ( a4 )
    *a4 = *(struct _tagpropertykey *)v6;
  if ( a3 )
    return PropVariantCopy(a3, (const PROPVARIANT *)(v6 + 24));
  else
    return 0;
}

```

## disassembly

```asm
0x18000a580  mov     r10d, edx
0x18000a583  xor     eax, eax
0x18000a585  mov     rdx, [rcx]
0x18000a588  test    rdx, rdx
0x18000a58b  jz      short loc_18000A5C0
0x18000a58d  nop     dword ptr [rax]
0x18000a590  cmp     byte ptr [rdx+31h], 1
0x18000a594  jz      short loc_18000A5B7
0x18000a596  cmp     eax, r10d
0x18000a599  jnz     short loc_18000A5DA
0x18000a59b  test    r9, r9
0x18000a59e  jz      short loc_18000A5AE
0x18000a5a0  movups  xmm0, xmmword ptr [rdx]
0x18000a5a3  movups  xmmword ptr [r9], xmm0
0x18000a5a7  mov     eax, [rdx+10h]
0x18000a5aa  mov     [r9+10h], eax
0x18000a5ae  test    r8, r8
0x18000a5b1  jnz     short loc_18000A5C7
0x18000a5b3  xor     eax, eax
0x18000a5b5  retn
0x18000a5b7  mov     rdx, [rdx+38h]
0x18000a5bb  test    rdx, rdx
0x18000a5be  jnz     short loc_18000A590
0x18000a5c0  mov     eax, 80004005h
0x18000a5c5  retn
0x18000a5c7  add     rdx, 18h
0x18000a5cb  mov     rcx, r8
0x18000a5ce  jmp     cs:__imp_PropVariantCopy
0x18000a5da  inc     eax
0x18000a5dc  jmp     short loc_18000A5B7
```
