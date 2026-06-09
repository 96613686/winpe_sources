# CMetadataContainer::_WriteOutDirtyItems(IWICMetadataQueryWriter *)

- ea: `0x18001c380`
- end: `0x18001c4b8`
- name: `?_WriteOutDirtyItems@CMetadataContainer@@AEAAJPEAUIWICMetadataQueryWriter@@@Z`
- size: `312`
- prototype: `__int64 __fastcall(CMetadataContainer *__hidden this, struct IWICMetadataQueryWriter *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001a658`
- `0x18001bc00`

## callees

- `0x180002360`
- `0x180009f90`
- `0x180014ba4`
- `0x18001c380`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18001c3f0`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18001c3f0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001c422`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001c488`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001c422`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001c488`

## pseudocode

```c
__int64 __fastcall CMetadataContainer::_WriteOutDirtyItems(
        CMetadataContainer *this,
        struct IWICMetadataQueryWriter *a2)
{
  int v2; // esi
  int v3; // edi
  __int64 v6; // rdx
  int v7; // ebx
  GUID v8; // xmm0
  int ItemAtIndex; // ebx
  unsigned int i; // esi
  struct _tagpropertykey v12; // [rsp+20h] [rbp-30h] BYREF
  PROPVARIANT pvarDest; // [rsp+38h] [rbp-18h] BYREF

  v2 = -1;
  v3 = 0;
  memset(&v12, 0, sizeof(v12));
  memset(&pvarDest, 0, sizeof(pvarDest));
  do
  {
    v6 = *((_QWORD *)this + 12);
    v7 = -1;
    while ( 1 )
    {
      if ( !v6 )
        goto LABEL_11;
      if ( *(_BYTE *)(v6 + 48) )
      {
        ++v7;
        if ( v2 == -1 || v7 > v2 )
          break;
      }
      v6 = *(_QWORD *)(v6 + 56);
    }
    v8 = *(GUID *)v6;
    v12.pid = *(_DWORD *)(v6 + 16);
    v12.fmtid = v8;
    if ( PropVariantCopy(&pvarDest, (const PROPVARIANT *)(v6 + 24)) < 0 )
    {
LABEL_11:
      v2 = -1;
      v7 = -1;
      goto LABEL_12;
    }
    v2 = v7;
    if ( v7 != -1 )
      v3 = CMetadataContainer::_WriteOutKey(this, a2, &v12, &pvarDest);
LABEL_12:
    PropVariantClear(&pvarDest);
  }
  while ( v3 >= 0 && v7 != -1 );
  ItemAtIndex = 0;
  for ( i = 0; i < CPhotoPropertyItemList::GetCount((CMetadataContainer *)((char *)this + 120)); ++i )
  {
    if ( ItemAtIndex < 0 )
      break;
    ItemAtIndex = CPhotoPropertyItemList::GetItemAtIndex((CMetadataContainer *)((char *)this + 120), i, &pvarDest, &v12);
    if ( ItemAtIndex >= 0 )
    {
      ItemAtIndex = CMetadataContainer::_WriteOutKey(this, a2, &v12, &pvarDest);
      if ( (unsigned int)(ItemAtIndex + 2003292352) <= 1 )
        ItemAtIndex = 0;
    }
    PropVariantClear(&pvarDest);
  }
  if ( v3 >= 0 )
  {
    v3 = 0;
    if ( ItemAtIndex < 0 )
      return (unsigned int)ItemAtIndex;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001c380  push    rbp
0x18001c382  push    rbx
0x18001c383  push    rsi
0x18001c384  push    rdi
0x18001c385  push    r12
0x18001c387  push    r14
0x18001c389  push    r15
0x18001c38b  mov     rbp, rsp
0x18001c38e  sub     rsp, 50h
0x18001c392  xor     eax, eax
0x18001c394  or      r14d, 0FFFFFFFFh
0x18001c398  xorps   xmm0, xmm0
0x18001c39b  mov     [rbp+var_30.pid], eax
0x18001c39e  xorps   xmm1, xmm1
0x18001c3a1  mov     qword ptr [rbp+pvarDest+10h], rax
0x18001c3a5  mov     esi, r14d
0x18001c3a8  xor     edi, edi
0x18001c3aa  movups  xmmword ptr [rbp+var_30.fmtid.Data1], xmm0
0x18001c3ae  mov     r12, rdx
0x18001c3b1  mov     r15, rcx
0x18001c3b4  movups  xmmword ptr [rbp+pvarDest], xmm1
0x18001c3b8  mov     rdx, [r15+60h]
0x18001c3bc  mov     ebx, r14d
0x18001c3bf  test    rdx, rdx
0x18001c3c2  jz      short loc_18001C418
0x18001c3c4  cmp     byte ptr [rdx+30h], 0
0x18001c3c8  jz      short loc_18001C3D5
0x18001c3ca  inc     ebx
0x18001c3cc  cmp     esi, r14d
0x18001c3cf  jz      short loc_18001C3DB
0x18001c3d1  cmp     ebx, esi
0x18001c3d3  jg      short loc_18001C3DB
0x18001c3d5  mov     rdx, [rdx+38h]
0x18001c3d9  jmp     short loc_18001C3BF
0x18001c3db  movups  xmm0, xmmword ptr [rdx]
0x18001c3de  mov     eax, [rdx+10h]
0x18001c3e1  lea     rcx, [rbp+pvarDest]; pvarDest
0x18001c3e5  add     rdx, 18h; pvarSrc
0x18001c3e9  mov     [rbp+var_30.pid], eax
0x18001c3ec  movups  xmmword ptr [rbp+var_30.fmtid.Data1], xmm0
0x18001c3f0  call    cs:__imp_PropVariantCopy
0x18001c3f6  test    eax, eax
0x18001c3f8  js      short loc_18001C418
0x18001c3fa  mov     esi, ebx
0x18001c3fc  cmp     ebx, r14d
0x18001c3ff  jz      short loc_18001C41E
0x18001c401  lea     r9, [rbp+pvarDest]; struct tagPROPVARIANT *
0x18001c405  mov     rdx, r12; struct IWICMetadataQueryWriter *
0x18001c408  lea     r8, [rbp+var_30]; struct _tagpropertykey *
0x18001c40c  mov     rcx, r15; this
0x18001c40f  call    ?_WriteOutKey@CMetadataContainer@@AEAAJPEAUIWICMetadataQueryWriter@@PEBU_tagpropertykey@@PEBUtagPROPVARIANT@@@Z; CMetadataContainer::_WriteOutKey(IWICMetadataQueryWriter *,_tagpropertykey const *,tagPROPVARIANT const *)
0x18001c414  mov     edi, eax
0x18001c416  jmp     short loc_18001C41E
0x18001c418  mov     esi, r14d
0x18001c41b  mov     ebx, r14d
0x18001c41e  lea     rcx, [rbp+pvarDest]; pvar
0x18001c422  call    cs:__imp_PropVariantClear
0x18001c428  test    edi, edi
0x18001c42a  js      short loc_18001C431
0x18001c42c  cmp     ebx, r14d
0x18001c42f  jnz     short loc_18001C3B8
0x18001c431  lea     r14, [r15+78h]
0x18001c435  xor     ebx, ebx
0x18001c437  mov     rcx, r14; this
0x18001c43a  xor     esi, esi
0x18001c43c  call    ?GetCount@CPhotoPropertyItemList@@QEAAIXZ; CPhotoPropertyItemList::GetCount(void)
0x18001c441  test    eax, eax
0x18001c443  jz      short loc_18001C49C
0x18001c445  test    ebx, ebx
0x18001c447  js      short loc_18001C49C
0x18001c449  lea     r9, [rbp+var_30]; struct _tagpropertykey *
0x18001c44d  mov     edx, esi; unsigned int
0x18001c44f  lea     r8, [rbp+pvarDest]; struct tagPROPVARIANT *
0x18001c453  mov     rcx, r14; this
0x18001c456  call    ?GetItemAtIndex@CPhotoPropertyItemList@@QEAAJIPEAUtagPROPVARIANT@@PEAU_tagpropertykey@@@Z; CPhotoPropertyItemList::GetItemAtIndex(uint,tagPROPVARIANT *,_tagpropertykey *)
0x18001c45b  mov     ebx, eax
0x18001c45d  test    eax, eax
0x18001c45f  js      short loc_18001C484
0x18001c461  lea     r9, [rbp+pvarDest]; struct tagPROPVARIANT *
0x18001c465  mov     rdx, r12; struct IWICMetadataQueryWriter *
0x18001c468  lea     r8, [rbp+var_30]; struct _tagpropertykey *
0x18001c46c  mov     rcx, r15; this
0x18001c46f  call    ?_WriteOutKey@CMetadataContainer@@AEAAJPEAUIWICMetadataQueryWriter@@PEBU_tagpropertykey@@PEBUtagPROPVARIANT@@@Z; CMetadataContainer::_WriteOutKey(IWICMetadataQueryWriter *,_tagpropertykey const *,tagPROPVARIANT const *)
0x18001c474  mov     ebx, eax
0x18001c476  lea     ecx, [rax+7767D0C0h]
0x18001c47c  xor     eax, eax
0x18001c47e  cmp     ecx, 1
0x18001c481  cmovbe  ebx, eax
0x18001c484  lea     rcx, [rbp+pvarDest]; pvar
0x18001c488  call    cs:__imp_PropVariantClear
0x18001c48e  mov     rcx, r14; this
0x18001c491  inc     esi
0x18001c493  call    ?GetCount@CPhotoPropertyItemList@@QEAAIXZ; CPhotoPropertyItemList::GetCount(void)
0x18001c498  cmp     esi, eax
0x18001c49a  jb      short loc_18001C445
0x18001c49c  test    edi, edi
0x18001c49e  js      short loc_18001C4A7
0x18001c4a0  xor     edi, edi
0x18001c4a2  test    ebx, ebx
0x18001c4a4  cmovs   edi, ebx
0x18001c4a7  mov     eax, edi
0x18001c4a9  add     rsp, 50h
0x18001c4ad  pop     r15
0x18001c4af  pop     r14
0x18001c4b1  pop     r12
0x18001c4b3  pop     rdi
0x18001c4b4  pop     rsi
0x18001c4b5  pop     rbx
0x18001c4b6  pop     rbp
0x18001c4b7  retn
```
