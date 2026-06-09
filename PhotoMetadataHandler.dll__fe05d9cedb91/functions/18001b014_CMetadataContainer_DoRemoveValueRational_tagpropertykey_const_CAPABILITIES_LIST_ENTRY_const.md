# CMetadataContainer::_DoRemoveValueRational(_tagpropertykey const *,CAPABILITIES_LIST_ENTRY const *)

- ea: `0x18001b014`
- end: `0x18001b1f5`
- name: `?_DoRemoveValueRational@CMetadataContainer@@AEAAJPEBU_tagpropertykey@@PEBUCAPABILITIES_LIST_ENTRY@@@Z`
- size: `481`
- prototype: `__int64 __fastcall(CMetadataContainer *__hidden this, const struct _tagpropertykey *, const struct CAPABILITIES_LIST_ENTRY *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001a988`

## callees

- `0x180004490`
- `0x180004e00`
- `0x18000c0e0`
- `0x18001a5d8`
- `0x18001b014`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001b1e1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001b1e1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMetadataContainer::_DoRemoveValueRational(
        CMetadataContainer *this,
        const struct _tagpropertykey *a2,
        const struct CAPABILITIES_LIST_ENTRY *a3)
{
  HRESULT RationalKeysFromMap; // edi
  struct _tagpropertykey v7; // [rsp+30h] [rbp-59h] BYREF
  struct _tagpropertykey v8; // [rsp+48h] [rbp-41h] BYREF
  struct _tagpropertykey v9; // [rsp+60h] [rbp-29h] BYREF
  struct _tagpropertykey v10; // [rsp+78h] [rbp-11h] BYREF
  struct tagPROPVARIANT v11; // [rsp+90h] [rbp+7h] BYREF
  PROPVARIANT pvar; // [rsp+A8h] [rbp+1Fh] BYREF

  RationalKeysFromMap = -2147418113;
  memset(&pvar, 0, sizeof(pvar));
  memset(&v8, 0, sizeof(v8));
  memset(&v9, 0, sizeof(v9));
  memset(&v10, 0, sizeof(v10));
  memset(&v7, 0, sizeof(v7));
  switch ( *((_DWORD *)a3 + 6) )
  {
    case 1:
      goto LABEL_11;
    case 2:
LABEL_10:
      RationalKeysFromMap = GetRationalKeysFromMap(1, &v8, a2, &v10, &v7);
      v9 = *a2;
      goto LABEL_12;
    case 3:
LABEL_9:
      RationalKeysFromMap = GetRationalKeysFromMap(2, &v8, &v9, a2, &v7);
      v10 = *a2;
      goto LABEL_12;
    case 4:
LABEL_11:
      RationalKeysFromMap = GetRationalKeysFromMap(0, a2, &v9, &v10, &v7);
      v8 = *a2;
      goto LABEL_12;
    case 5:
      goto LABEL_10;
    case 6:
      goto LABEL_9;
  }
  if ( (unsigned int)(*((_DWORD *)a3 + 6) - 7) > 1 )
    goto LABEL_15;
  RationalKeysFromMap = GetRationalKeysFromMap(3, &v8, &v9, &v10, a2);
  v7 = *a2;
LABEL_12:
  if ( RationalKeysFromMap >= 0 )
  {
    memset(&v11, 0, sizeof(v11));
    CMetadataContainer::ReadInMetadata(this);
    RationalKeysFromMap = CPhotoPropertyItemList::_InternalUpdateOrAddItem(
                            (CMetadataContainer *)((char *)this + 120),
                            &v7,
                            &v11,
                            1,
                            0);
    if ( RationalKeysFromMap >= 0 )
    {
      CMetadataContainer::ReadInMetadata(this);
      CPhotoPropertyItemList::_InternalDeleteItem((CMetadataContainer *)((char *)this + 96), &v8);
      CMetadataContainer::ReadInMetadata(this);
      CPhotoPropertyItemList::_InternalDeleteItem((CMetadataContainer *)((char *)this + 96), &v9);
      CMetadataContainer::ReadInMetadata(this);
      CPhotoPropertyItemList::_InternalDeleteItem((CMetadataContainer *)((char *)this + 96), &v10);
      CMetadataContainer::ReadInMetadata(this);
      CPhotoPropertyItemList::_InternalDeleteItem((CMetadataContainer *)((char *)this + 96), &v7);
    }
  }
LABEL_15:
  PropVariantClear(&pvar);
  return (unsigned int)RationalKeysFromMap;
}

```

## disassembly

```asm
0x18001b014  push    rbp
0x18001b016  push    rbx
0x18001b017  push    rsi
0x18001b018  push    rdi
0x18001b019  lea     rbp, [rsp-3Fh]
0x18001b01e  sub     rsp, 0C8h
0x18001b025  mov     rbx, rdx
0x18001b028  mov     rsi, rcx
0x18001b02b  mov     edi, 8000FFFFh
0x18001b030  xorps   xmm0, xmm0
0x18001b033  xor     eax, eax
0x18001b035  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18001b039  mov     qword ptr [rbp+57h+pvar+10h], rax
0x18001b03d  mov     [rbp+57h+var_98.fmtid.Data1], eax
0x18001b040  movups  xmmword ptr [rbp+57h+var_98.fmtid.Data2], xmm0
0x18001b044  mov     [rbp+57h+var_80.fmtid.Data1], eax
0x18001b047  xorps   xmm1, xmm1
0x18001b04a  movups  xmmword ptr [rbp+57h+var_80.fmtid.Data2], xmm1
0x18001b04e  mov     [rbp+57h+var_68.fmtid.Data1], eax
0x18001b051  movups  xmmword ptr [rbp+57h+var_68.fmtid.Data2], xmm0
0x18001b055  mov     [rbp+57h+var_B0.fmtid.Data1], eax
0x18001b058  movups  xmmword ptr [rbp+57h+var_B0.fmtid.Data2], xmm1
0x18001b05c  mov     ecx, [r8+18h]
0x18001b060  sub     ecx, 1
0x18001b063  jz      loc_18001B125
0x18001b069  sub     ecx, 1
0x18001b06c  jz      loc_18001B0F6
0x18001b072  sub     ecx, 1
0x18001b075  jz      short loc_18001B0C7
0x18001b077  sub     ecx, 1
0x18001b07a  jz      loc_18001B125
0x18001b080  sub     ecx, 1
0x18001b083  jz      short loc_18001B0F6
0x18001b085  sub     ecx, 1
0x18001b088  jz      short loc_18001B0C7
0x18001b08a  sub     ecx, 1
0x18001b08d  jz      short loc_18001B098
0x18001b08f  cmp     ecx, 1
0x18001b092  jnz     loc_18001B1DD
0x18001b098  mov     qword ptr [rsp+0E0h+var_C0], rbx
0x18001b09d  lea     r9, [rbp+57h+var_68]
0x18001b0a1  lea     r8, [rbp+57h+var_80]
0x18001b0a5  lea     rdx, [rbp+57h+var_98]
0x18001b0a9  mov     ecx, 3
0x18001b0ae  call    ?GetRationalKeysFromMap@@YAJW4RationalKeyType@@PEAU_tagpropertykey@@111@Z; GetRationalKeysFromMap(RationalKeyType,_tagpropertykey *,_tagpropertykey *,_tagpropertykey *,_tagpropertykey *)
0x18001b0b3  mov     edi, eax
0x18001b0b5  movups  xmm1, xmmword ptr [rbx]
0x18001b0b8  movups  xmmword ptr [rbp+57h+var_B0.fmtid.Data1], xmm1
0x18001b0bc  mov     ecx, [rbx+10h]
0x18001b0bf  mov     [rbp+57h+var_B0.pid], ecx
0x18001b0c2  jmp     loc_18001B14C
0x18001b0c7  lea     rax, [rbp+57h+var_B0]
0x18001b0cb  mov     qword ptr [rsp+0E0h+var_C0], rax
0x18001b0d0  mov     r9, rbx
0x18001b0d3  lea     r8, [rbp+57h+var_80]
0x18001b0d7  lea     rdx, [rbp+57h+var_98]
0x18001b0db  mov     ecx, 2
0x18001b0e0  call    ?GetRationalKeysFromMap@@YAJW4RationalKeyType@@PEAU_tagpropertykey@@111@Z; GetRationalKeysFromMap(RationalKeyType,_tagpropertykey *,_tagpropertykey *,_tagpropertykey *,_tagpropertykey *)
0x18001b0e5  mov     edi, eax
0x18001b0e7  movups  xmm1, xmmword ptr [rbx]
0x18001b0ea  movups  xmmword ptr [rbp+57h+var_68.fmtid.Data1], xmm1
0x18001b0ee  mov     eax, [rbx+10h]
0x18001b0f1  mov     [rbp+57h+var_68.pid], eax
0x18001b0f4  jmp     short loc_18001B14C
0x18001b0f6  lea     rax, [rbp+57h+var_B0]
0x18001b0fa  mov     qword ptr [rsp+0E0h+var_C0], rax
0x18001b0ff  lea     r9, [rbp+57h+var_68]
0x18001b103  mov     r8, rbx
0x18001b106  lea     rdx, [rbp+57h+var_98]
0x18001b10a  mov     ecx, 1
0x18001b10f  call    ?GetRationalKeysFromMap@@YAJW4RationalKeyType@@PEAU_tagpropertykey@@111@Z; GetRationalKeysFromMap(RationalKeyType,_tagpropertykey *,_tagpropertykey *,_tagpropertykey *,_tagpropertykey *)
0x18001b114  mov     edi, eax
0x18001b116  movups  xmm1, xmmword ptr [rbx]
0x18001b119  movups  xmmword ptr [rbp+57h+var_80.fmtid.Data1], xmm1
0x18001b11d  mov     eax, [rbx+10h]
0x18001b120  mov     [rbp+57h+var_80.pid], eax
0x18001b123  jmp     short loc_18001B14C
0x18001b125  lea     rax, [rbp+57h+var_B0]
0x18001b129  mov     qword ptr [rsp+0E0h+var_C0], rax
0x18001b12e  lea     r9, [rbp+57h+var_68]
0x18001b132  lea     r8, [rbp+57h+var_80]
0x18001b136  xor     ecx, ecx
0x18001b138  call    ?GetRationalKeysFromMap@@YAJW4RationalKeyType@@PEAU_tagpropertykey@@111@Z; GetRationalKeysFromMap(RationalKeyType,_tagpropertykey *,_tagpropertykey *,_tagpropertykey *,_tagpropertykey *)
0x18001b13d  mov     edi, eax
0x18001b13f  movups  xmm1, xmmword ptr [rbx]
0x18001b142  movups  xmmword ptr [rbp+57h+var_98.fmtid.Data1], xmm1
0x18001b146  mov     eax, [rbx+10h]
0x18001b149  mov     [rbp+57h+var_98.pid], eax
0x18001b14c  test    edi, edi
0x18001b14e  js      loc_18001B1DD
0x18001b154  xorps   xmm0, xmm0
0x18001b157  xor     eax, eax
0x18001b159  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x18001b15d  mov     qword ptr [rbp+57h+var_50+10h], rax
0x18001b161  mov     rcx, rsi; this
0x18001b164  call    ?ReadInMetadata@CMetadataContainer@@QEAAJXZ; CMetadataContainer::ReadInMetadata(void)
0x18001b169  lea     rcx, [rsi+78h]; this
0x18001b16d  mov     [rsp+0E0h+var_C0], 0; bool
0x18001b172  mov     r9b, 1; bool
0x18001b175  lea     r8, [rbp+57h+var_50]; struct tagPROPVARIANT *
0x18001b179  lea     rdx, [rbp+57h+var_B0]; struct _tagpropertykey *
0x18001b17d  call    ?_InternalUpdateOrAddItem@CPhotoPropertyItemList@@AEAAJPEBU_tagpropertykey@@PEBUtagPROPVARIANT@@_N2@Z; CPhotoPropertyItemList::_InternalUpdateOrAddItem(_tagpropertykey const *,tagPROPVARIANT const *,bool,bool)
0x18001b182  mov     edi, eax
0x18001b184  test    eax, eax
0x18001b186  js      short loc_18001B1DD
0x18001b188  lea     rbx, [rsi+60h]
0x18001b18c  mov     rcx, rsi; this
0x18001b18f  call    ?ReadInMetadata@CMetadataContainer@@QEAAJXZ; CMetadataContainer::ReadInMetadata(void)
0x18001b194  lea     rdx, [rbp+57h+var_98]; struct _tagpropertykey *
0x18001b198  mov     rcx, rbx; this
0x18001b19b  call    ?_InternalDeleteItem@CPhotoPropertyItemList@@AEAAJPEBU_tagpropertykey@@@Z; CPhotoPropertyItemList::_InternalDeleteItem(_tagpropertykey const *)
0x18001b1a0  mov     rcx, rsi; this
0x18001b1a3  call    ?ReadInMetadata@CMetadataContainer@@QEAAJXZ; CMetadataContainer::ReadInMetadata(void)
0x18001b1a8  lea     rdx, [rbp+57h+var_80]; struct _tagpropertykey *
0x18001b1ac  mov     rcx, rbx; this
0x18001b1af  call    ?_InternalDeleteItem@CPhotoPropertyItemList@@AEAAJPEBU_tagpropertykey@@@Z; CPhotoPropertyItemList::_InternalDeleteItem(_tagpropertykey const *)
0x18001b1b4  mov     rcx, rsi; this
0x18001b1b7  call    ?ReadInMetadata@CMetadataContainer@@QEAAJXZ; CMetadataContainer::ReadInMetadata(void)
0x18001b1bc  lea     rdx, [rbp+57h+var_68]; struct _tagpropertykey *
0x18001b1c0  mov     rcx, rbx; this
0x18001b1c3  call    ?_InternalDeleteItem@CPhotoPropertyItemList@@AEAAJPEBU_tagpropertykey@@@Z; CPhotoPropertyItemList::_InternalDeleteItem(_tagpropertykey const *)
0x18001b1c8  mov     rcx, rsi; this
0x18001b1cb  call    ?ReadInMetadata@CMetadataContainer@@QEAAJXZ; CMetadataContainer::ReadInMetadata(void)
0x18001b1d0  lea     rdx, [rbp+57h+var_B0]; struct _tagpropertykey *
0x18001b1d4  mov     rcx, rbx; this
0x18001b1d7  call    ?_InternalDeleteItem@CPhotoPropertyItemList@@AEAAJPEBU_tagpropertykey@@@Z; CPhotoPropertyItemList::_InternalDeleteItem(_tagpropertykey const *)
0x18001b1dc  nop
0x18001b1dd  lea     rcx, [rbp+57h+pvar]; pvar
0x18001b1e1  call    cs:__imp_PropVariantClear
0x18001b1e7  mov     eax, edi
0x18001b1e9  add     rsp, 0C8h
0x18001b1f0  pop     rdi
0x18001b1f1  pop     rsi
0x18001b1f2  pop     rbx
0x18001b1f3  pop     rbp
0x18001b1f4  retn
```
