# CEnhancedStorageFolder::CompareIDs(__int64,_ITEMIDLIST const *,_ITEMIDLIST const *)

- ea: `0x1800094a0`
- end: `0x1800095b9`
- name: `?CompareIDs@CEnhancedStorageFolder@@UEAAJ_JPEFBU_ITEMIDLIST@@1@Z`
- size: `281`
- prototype: `__int64 __fastcall(CEnhancedStorageFolder *__hidden this, __int64, const struct _ITEMIDLIST *, const struct _ITEMIDLIST *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180005ab8`
- `0x180005b2c`
- `0x18000684c`
- `0x1800094a0`
- `0x18000b5e6`

## import_xrefs

- `ole32!PropVariantClear` at `0x18000959b`
- `ole32!PropVariantClear` at `0x1800095a6`
- `ole32!PropVariantClear` at `0x18000959b`
- `ole32!PropVariantClear` at `0x1800095a6`
- `PROPSYS!PropVariantCompareEx` at `0x180009589`
- `PROPSYS!PropVariantCompareEx` at `0x180009589`

## pseudocode

```c
__int64 __fastcall CEnhancedStorageFolder::CompareIDs(
        CEnhancedStorageFolder *this,
        __int64 a2,
        const struct _ITEMIDLIST *a3,
        const struct _ITEMIDLIST *a4)
{
  unsigned __int16 *v6; // rax
  const void *v7; // r9
  const void *v8; // rdx
  int v9; // eax
  int PropertyFromIDList; // ebx
  PROPVARIANT propvar2; // [rsp+20h] [rbp-38h] BYREF
  PROPVARIANT propvar1; // [rsp+38h] [rbp-20h] BYREF

  memset(&propvar1, 0, sizeof(propvar1));
  memset(&propvar2, 0, sizeof(propvar2));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_6cd5398725ca392462ef447cc6ada768_Traceguids, a4);
  CItemIDFactory<_ITEMID,1450709556>::_IsValid(&a3->mkid.cb);
  v6 = CItemIDFactory<_ITEMID,1450709556>::_IsValid(&a4->mkid.cb);
  v8 = (const void *)((unsigned __int64)(v6 + 7) & ((unsigned __int128)-(__int128)(unsigned __int64)v6 >> 64));
  if ( !v7 || !v8 )
  {
    PropertyFromIDList = -2147467259;
    goto LABEL_12;
  }
  v9 = memcmp_0(v7, v8, 0xCu);
  if ( v9 )
    goto LABEL_7;
  PropertyFromIDList = CItemIDFactory<_ITEMID,1450709556>::GetPropertyFromIDList(
                         &a3->mkid.cb,
                         (__int64)&PKEY_ParsingName,
                         &propvar1);
  if ( PropertyFromIDList >= 0 )
  {
    PropertyFromIDList = CItemIDFactory<_ITEMID,1450709556>::GetPropertyFromIDList(
                           &a4->mkid.cb,
                           (__int64)&PKEY_ParsingName,
                           &propvar2);
    if ( PropertyFromIDList >= 0 )
    {
      LOWORD(v9) = PropVariantCompareEx(&propvar1, &propvar2, PVCU_DEFAULT, 0);
LABEL_7:
      PropertyFromIDList = (unsigned __int16)v9;
    }
  }
LABEL_12:
  PropVariantClear(&propvar2);
  PropVariantClear(&propvar1);
  return (unsigned int)PropertyFromIDList;
}

```

## disassembly

```asm
0x1800094a0  mov     [rsp+arg_0], rbx
0x1800094a5  push    rdi
0x1800094a6  sub     rsp, 50h
0x1800094aa  xor     eax, eax
0x1800094ac  xorps   xmm0, xmm0
0x1800094af  xorps   xmm1, xmm1
0x1800094b2  mov     qword ptr [rsp+58h+propvar1+10h], rax
0x1800094b7  movups  xmmword ptr [rsp+58h+propvar1], xmm0
0x1800094bc  mov     qword ptr [rsp+58h+propvar2+10h], rax
0x1800094c1  mov     rdi, r9
0x1800094c4  movups  xmmword ptr [rsp+58h+propvar2], xmm1
0x1800094c9  mov     rbx, r8
0x1800094cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800094d3  lea     rax, WPP_GLOBAL_Control
0x1800094da  cmp     rcx, rax
0x1800094dd  jz      short loc_1800094FA
0x1800094df  test    byte ptr [rcx+1Ch], 20h
0x1800094e3  jz      short loc_1800094FA
0x1800094e5  mov     rcx, [rcx+10h]
0x1800094e9  lea     r8, WPP_6cd5398725ca392462ef447cc6ada768_Traceguids
0x1800094f0  mov     edx, 30h ; '0'
0x1800094f5  call    WPP_SF_
0x1800094fa  mov     rcx, rbx
0x1800094fd  call    ?_IsValid@?$CItemIDFactory@U_ITEMID@@$0FGHIBCDE@@@CAPEFBUCHILDITEMID@1@PEFBU_ITEMIDLIST@@@Z; CItemIDFactory<_ITEMID,1450709556>::_IsValid(_ITEMIDLIST const *)
0x180009502  lea     rcx, [rax+0Eh]
0x180009506  neg     rax
0x180009509  sbb     r9, r9
0x18000950c  and     r9, rcx
0x18000950f  mov     rcx, rdi
0x180009512  call    ?_IsValid@?$CItemIDFactory@U_ITEMID@@$0FGHIBCDE@@@CAPEFBUCHILDITEMID@1@PEFBU_ITEMIDLIST@@@Z; CItemIDFactory<_ITEMID,1450709556>::_IsValid(_ITEMIDLIST const *)
0x180009517  lea     r8, [rax+0Eh]
0x18000951b  neg     rax
0x18000951e  sbb     rdx, rdx
0x180009521  and     rdx, r8; Buf2
0x180009524  test    r9, r9
0x180009527  jz      short loc_180009591
0x180009529  test    rdx, rdx
0x18000952c  jz      short loc_180009591
0x18000952e  mov     r8d, 0Ch; Size
0x180009534  mov     rcx, r9; Buf1
0x180009537  call    memcmp_0
0x18000953c  test    eax, eax
0x18000953e  jz      short loc_180009545
0x180009540  movzx   ebx, ax
0x180009543  jmp     short loc_180009596
0x180009545  lea     r8, [rsp+58h+propvar1]
0x18000954a  mov     rcx, rbx
0x18000954d  lea     rdx, PKEY_ParsingName
0x180009554  call    ?GetPropertyFromIDList@?$CItemIDFactory@U_ITEMID@@$0FGHIBCDE@@@SAJPEFBU_ITEMIDLIST@@AEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z; CItemIDFactory<_ITEMID,1450709556>::GetPropertyFromIDList(_ITEMIDLIST const *,_tagpropertykey const &,tagPROPVARIANT *)
0x180009559  mov     ebx, eax
0x18000955b  test    eax, eax
0x18000955d  js      short loc_180009596
0x18000955f  lea     r8, [rsp+58h+propvar2]
0x180009564  mov     rcx, rdi
0x180009567  lea     rdx, PKEY_ParsingName
0x18000956e  call    ?GetPropertyFromIDList@?$CItemIDFactory@U_ITEMID@@$0FGHIBCDE@@@SAJPEFBU_ITEMIDLIST@@AEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z; CItemIDFactory<_ITEMID,1450709556>::GetPropertyFromIDList(_ITEMIDLIST const *,_tagpropertykey const &,tagPROPVARIANT *)
0x180009573  mov     ebx, eax
0x180009575  test    eax, eax
0x180009577  js      short loc_180009596
0x180009579  xor     r9d, r9d; flags
0x18000957c  lea     rdx, [rsp+58h+propvar2]; propvar2
0x180009581  xor     r8d, r8d; unit
0x180009584  lea     rcx, [rsp+58h+propvar1]; propvar1
0x180009589  call    cs:__imp_PropVariantCompareEx
0x18000958f  jmp     short loc_180009540
0x180009591  mov     ebx, 80004005h
0x180009596  lea     rcx, [rsp+58h+propvar2]; pvar
0x18000959b  call    cs:__imp_PropVariantClear
0x1800095a1  lea     rcx, [rsp+58h+propvar1]; pvar
0x1800095a6  call    cs:__imp_PropVariantClear
0x1800095ac  mov     eax, ebx
0x1800095ae  mov     rbx, [rsp+58h+arg_0]
0x1800095b3  add     rsp, 50h
0x1800095b7  pop     rdi
0x1800095b8  retn
```
