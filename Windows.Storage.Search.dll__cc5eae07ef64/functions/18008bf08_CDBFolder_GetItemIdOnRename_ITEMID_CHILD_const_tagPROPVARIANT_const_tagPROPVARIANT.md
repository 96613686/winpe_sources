# CDBFolder::_GetItemIdOnRename(_ITEMID_CHILD const *,tagPROPVARIANT const &,tagPROPVARIANT *)

- ea: `0x18008bf08`
- end: `0x18008bfe0`
- name: `?_GetItemIdOnRename@CDBFolder@@AEAAJPEFBU_ITEMID_CHILD@@AEBUtagPROPVARIANT@@PEAU3@@Z`
- size: `216`
- prototype: `int(CDBFolder *__hidden this, const struct _ITEMID_CHILD *, const struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18008a260`

## callees

- `0x18000a730`
- `0x18008bf08`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18008bfb5`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18008bfb5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18008bfc2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18008bfcd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18008bfc2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18008bfcd`
- `PROPSYS!PropVariantCompareEx` at `0x18008bfa0`
- `PROPSYS!PropVariantCompareEx` at `0x18008bfa0`

## pseudocode

```c
__int64 __fastcall CDBFolder::_GetItemIdOnRename(
        CDBFolder *this,
        const struct _ITEMID_CHILD *a2,
        PROPVARIANT *a3,
        PROPVARIANT *a4)
{
  char *v4; // r14
  HRESULT PropertyForItem; // ebx
  int v9; // eax
  PROPVARIANT *v10; // rdx
  PROPVARIANT propvar1[2]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v13; // [rsp+40h] [rbp-48h]
  PROPVARIANT propvar2[2]; // [rsp+48h] [rbp-40h] BYREF
  __int64 v15; // [rsp+58h] [rbp-30h]

  v4 = (char *)this + 184;
  v13 = 0;
  *(_OWORD *)a4 = 0;
  a4[2] = 0;
  *(_OWORD *)propvar1 = 0;
  PropertyForItem = CDBFolder::GetPropertyForItem((char *)this + 184, a2, &PKEY_ItemId, 0, propvar1);
  if ( PropertyForItem >= 0 )
  {
    v15 = 0;
    *(_OWORD *)propvar2 = 0;
    PropertyForItem = CDBFolder::GetPropertyForItem(v4, a2, &PKEY_ParsingPath, 0, propvar2);
    if ( PropertyForItem >= 0 )
    {
      v9 = PropVariantCompareEx(propvar1, propvar2, PVCU_DEFAULT, 0);
      v10 = a3;
      if ( v9 )
        v10 = propvar1;
      PropertyForItem = PropVariantCopy(a4, v10);
      PropVariantClear(propvar2);
    }
    PropVariantClear(propvar1);
  }
  return (unsigned int)PropertyForItem;
}

```

## disassembly

```asm
0x18008bf08  push    rbx
0x18008bf0a  push    rbp
0x18008bf0b  push    rsi
0x18008bf0c  push    rdi
0x18008bf0d  push    r14
0x18008bf0f  sub     rsp, 60h
0x18008bf13  xor     eax, eax
0x18008bf15  lea     r14, [rcx+0B8h]
0x18008bf1c  xorps   xmm0, xmm0
0x18008bf1f  mov     [rsp+88h+var_48], rax
0x18008bf24  movups  xmmword ptr [r9], xmm0
0x18008bf28  mov     [r9+10h], rax
0x18008bf2c  mov     rdi, r9
0x18008bf2f  lea     rax, [rsp+88h+propvar1]
0x18008bf34  mov     rsi, r8
0x18008bf37  xor     r9d, r9d
0x18008bf3a  mov     [rsp+88h+var_68], rax
0x18008bf3f  lea     r8, PKEY_ItemId
0x18008bf46  mov     rcx, r14
0x18008bf49  mov     rbp, rdx
0x18008bf4c  movups  xmmword ptr [rsp+88h+propvar1], xmm0
0x18008bf51  call    ?GetPropertyForItem@CDBFolder@@UEAAJPEFBU_ITEMIDLIST_RELATIVE@@AEBU_tagpropertykey@@W4PROPERTY_GET_TYPE@@PEAUtagPROPVARIANT@@@Z; CDBFolder::GetPropertyForItem(_ITEMIDLIST_RELATIVE const *,_tagpropertykey const &,PROPERTY_GET_TYPE,tagPROPVARIANT *)
0x18008bf56  mov     ebx, eax
0x18008bf58  test    eax, eax
0x18008bf5a  js      short loc_18008BFD3
0x18008bf5c  xor     eax, eax
0x18008bf5e  lea     r8, PKEY_ParsingPath
0x18008bf65  mov     [rsp+88h+var_30], rax
0x18008bf6a  xorps   xmm0, xmm0
0x18008bf6d  lea     rax, [rsp+88h+propvar2]
0x18008bf72  xor     r9d, r9d
0x18008bf75  mov     rdx, rbp
0x18008bf78  mov     [rsp+88h+var_68], rax
0x18008bf7d  mov     rcx, r14
0x18008bf80  movups  xmmword ptr [rsp+88h+propvar2], xmm0
0x18008bf85  call    ?GetPropertyForItem@CDBFolder@@UEAAJPEFBU_ITEMIDLIST_RELATIVE@@AEBU_tagpropertykey@@W4PROPERTY_GET_TYPE@@PEAUtagPROPVARIANT@@@Z; CDBFolder::GetPropertyForItem(_ITEMIDLIST_RELATIVE const *,_tagpropertykey const &,PROPERTY_GET_TYPE,tagPROPVARIANT *)
0x18008bf8a  mov     ebx, eax
0x18008bf8c  test    eax, eax
0x18008bf8e  js      short loc_18008BFC8
0x18008bf90  xor     r9d, r9d; flags
0x18008bf93  lea     rdx, [rsp+88h+propvar2]; propvar2
0x18008bf98  xor     r8d, r8d; unit
0x18008bf9b  lea     rcx, [rsp+88h+propvar1]; propvar1
0x18008bfa0  call    cs:__imp_PropVariantCompareEx
0x18008bfa6  mov     rcx, rdi; pvarDest
0x18008bfa9  mov     rdx, rsi
0x18008bfac  test    eax, eax
0x18008bfae  jz      short loc_18008BFB5
0x18008bfb0  lea     rdx, [rsp+88h+propvar1]; pvarSrc
0x18008bfb5  call    cs:__imp_PropVariantCopy
0x18008bfbb  lea     rcx, [rsp+88h+propvar2]; pvar
0x18008bfc0  mov     ebx, eax
0x18008bfc2  call    cs:__imp_PropVariantClear
0x18008bfc8  lea     rcx, [rsp+88h+propvar1]; pvar
0x18008bfcd  call    cs:__imp_PropVariantClear
0x18008bfd3  mov     eax, ebx
0x18008bfd5  add     rsp, 60h
0x18008bfd9  pop     r14
0x18008bfdb  pop     rdi
0x18008bfdc  pop     rsi
0x18008bfdd  pop     rbp
0x18008bfde  pop     rbx
0x18008bfdf  retn
```
