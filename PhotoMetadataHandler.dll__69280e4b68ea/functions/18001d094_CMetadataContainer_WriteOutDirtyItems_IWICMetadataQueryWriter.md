# CMetadataContainer::_WriteOutDirtyItems(IWICMetadataQueryWriter *)

- ea: `0x18001d094`
- end: `0x18001d1e3`
- name: `?_WriteOutDirtyItems@CMetadataContainer@@AEAAJPEAUIWICMetadataQueryWriter@@@Z`
- size: `335`
- prototype: `__int64 __fastcall(CMetadataContainer *__hidden this, struct IWICMetadataQueryWriter *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001b2f8`
- `0x18001c8f4`

## callees

- `0x180002420`
- `0x18000a580`
- `0x180015594`
- `0x18001d094`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18001d104`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18001d104`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001d13c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001d1ac`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001d13c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001d1ac`

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
0x18001d094  push    rbp
0x18001d096  push    rbx
0x18001d097  push    rsi
0x18001d098  push    rdi
0x18001d099  push    r12
0x18001d09b  push    r14
0x18001d09d  push    r15
0x18001d09f  mov     rbp, rsp
0x18001d0a2  sub     rsp, 50h
0x18001d0a6  xor     eax, eax
0x18001d0a8  or      r14d, 0FFFFFFFFh
0x18001d0ac  xorps   xmm0, xmm0
0x18001d0af  mov     [rbp+var_30.pid], eax
0x18001d0b2  xorps   xmm1, xmm1
0x18001d0b5  mov     qword ptr [rbp+pvarDest+10h], rax
0x18001d0b9  mov     esi, r14d
0x18001d0bc  xor     edi, edi
0x18001d0be  movups  xmmword ptr [rbp+var_30.fmtid.Data1], xmm0
0x18001d0c2  mov     r12, rdx
0x18001d0c5  mov     r15, rcx
0x18001d0c8  movups  xmmword ptr [rbp+pvarDest], xmm1
0x18001d0cc  mov     rdx, [r15+60h]
0x18001d0d0  mov     ebx, r14d
0x18001d0d3  test    rdx, rdx
0x18001d0d6  jz      short loc_18001D132
0x18001d0d8  cmp     byte ptr [rdx+30h], 0
0x18001d0dc  jz      short loc_18001D0E9
0x18001d0de  inc     ebx
0x18001d0e0  cmp     esi, r14d
0x18001d0e3  jz      short loc_18001D0EF
0x18001d0e5  cmp     ebx, esi
0x18001d0e7  jg      short loc_18001D0EF
0x18001d0e9  mov     rdx, [rdx+38h]
0x18001d0ed  jmp     short loc_18001D0D3
0x18001d0ef  movups  xmm0, xmmword ptr [rdx]
0x18001d0f2  mov     eax, [rdx+10h]
0x18001d0f5  lea     rcx, [rbp+pvarDest]; pvarDest
0x18001d0f9  add     rdx, 18h; pvarSrc
0x18001d0fd  mov     [rbp+var_30.pid], eax
0x18001d100  movups  xmmword ptr [rbp+var_30.fmtid.Data1], xmm0
0x18001d104  call    cs:__imp_PropVariantCopy
0x18001d10b  nop     dword ptr [rax+rax+00h]
0x18001d110  test    eax, eax
0x18001d112  js      short loc_18001D132
0x18001d114  mov     esi, ebx
0x18001d116  cmp     ebx, r14d
0x18001d119  jz      short loc_18001D138
0x18001d11b  lea     r9, [rbp+pvarDest]; struct tagPROPVARIANT *
0x18001d11f  mov     rdx, r12; struct IWICMetadataQueryWriter *
0x18001d122  lea     r8, [rbp+var_30]; struct _tagpropertykey *
0x18001d126  mov     rcx, r15; this
0x18001d129  call    ?_WriteOutKey@CMetadataContainer@@AEAAJPEAUIWICMetadataQueryWriter@@PEBU_tagpropertykey@@PEBUtagPROPVARIANT@@@Z; CMetadataContainer::_WriteOutKey(IWICMetadataQueryWriter *,_tagpropertykey const *,tagPROPVARIANT const *)
0x18001d12e  mov     edi, eax
0x18001d130  jmp     short loc_18001D138
0x18001d132  mov     esi, r14d
0x18001d135  mov     ebx, r14d
0x18001d138  lea     rcx, [rbp+pvarDest]; pvar
0x18001d13c  call    cs:__imp_PropVariantClear
0x18001d143  nop     dword ptr [rax+rax+00h]
0x18001d148  test    edi, edi
0x18001d14a  js      short loc_18001D155
0x18001d14c  cmp     ebx, r14d
0x18001d14f  jnz     loc_18001D0CC
0x18001d155  lea     r14, [r15+78h]
0x18001d159  xor     ebx, ebx
0x18001d15b  mov     rcx, r14; this
0x18001d15e  xor     esi, esi
0x18001d160  call    ?GetCount@CPhotoPropertyItemList@@QEAAIXZ; CPhotoPropertyItemList::GetCount(void)
0x18001d165  test    eax, eax
0x18001d167  jz      short loc_18001D1C6
0x18001d169  test    ebx, ebx
0x18001d16b  js      short loc_18001D1C6
0x18001d16d  lea     r9, [rbp+var_30]; struct _tagpropertykey *
0x18001d171  mov     edx, esi; unsigned int
0x18001d173  lea     r8, [rbp+pvarDest]; struct tagPROPVARIANT *
0x18001d177  mov     rcx, r14; this
0x18001d17a  call    ?GetItemAtIndex@CPhotoPropertyItemList@@QEAAJIPEAUtagPROPVARIANT@@PEAU_tagpropertykey@@@Z; CPhotoPropertyItemList::GetItemAtIndex(uint,tagPROPVARIANT *,_tagpropertykey *)
0x18001d17f  mov     ebx, eax
0x18001d181  test    eax, eax
0x18001d183  js      short loc_18001D1A8
0x18001d185  lea     r9, [rbp+pvarDest]; struct tagPROPVARIANT *
0x18001d189  mov     rdx, r12; struct IWICMetadataQueryWriter *
0x18001d18c  lea     r8, [rbp+var_30]; struct _tagpropertykey *
0x18001d190  mov     rcx, r15; this
0x18001d193  call    ?_WriteOutKey@CMetadataContainer@@AEAAJPEAUIWICMetadataQueryWriter@@PEBU_tagpropertykey@@PEBUtagPROPVARIANT@@@Z; CMetadataContainer::_WriteOutKey(IWICMetadataQueryWriter *,_tagpropertykey const *,tagPROPVARIANT const *)
0x18001d198  mov     ebx, eax
0x18001d19a  lea     ecx, [rax+7767D0C0h]
0x18001d1a0  xor     eax, eax
0x18001d1a2  cmp     ecx, 1
0x18001d1a5  cmovbe  ebx, eax
0x18001d1a8  lea     rcx, [rbp+pvarDest]; pvar
0x18001d1ac  call    cs:__imp_PropVariantClear
0x18001d1b3  nop     dword ptr [rax+rax+00h]
0x18001d1b8  mov     rcx, r14; this
0x18001d1bb  inc     esi
0x18001d1bd  call    ?GetCount@CPhotoPropertyItemList@@QEAAIXZ; CPhotoPropertyItemList::GetCount(void)
0x18001d1c2  cmp     esi, eax
0x18001d1c4  jb      short loc_18001D169
0x18001d1c6  test    edi, edi
0x18001d1c8  js      short loc_18001D1D1
0x18001d1ca  xor     edi, edi
0x18001d1cc  test    ebx, ebx
0x18001d1ce  cmovs   edi, ebx
0x18001d1d1  mov     eax, edi
0x18001d1d3  add     rsp, 50h
0x18001d1d7  pop     r15
0x18001d1d9  pop     r14
0x18001d1db  pop     r12
0x18001d1dd  pop     rdi
0x18001d1de  pop     rsi
0x18001d1df  pop     rbx
0x18001d1e0  pop     rbp
0x18001d1e1  retn
```
