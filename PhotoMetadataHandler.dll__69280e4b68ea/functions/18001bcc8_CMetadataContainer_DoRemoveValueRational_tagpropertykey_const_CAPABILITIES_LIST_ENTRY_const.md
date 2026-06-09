# CMetadataContainer::_DoRemoveValueRational(_tagpropertykey const *,CAPABILITIES_LIST_ENTRY const *)

- ea: `0x18001bcc8`
- end: `0x18001beb0`
- name: `?_DoRemoveValueRational@CMetadataContainer@@AEAAJPEBU_tagpropertykey@@PEBUCAPABILITIES_LIST_ENTRY@@@Z`
- size: `488`
- prototype: `__int64 __fastcall(CMetadataContainer *__hidden this, const struct _tagpropertykey *, const struct CAPABILITIES_LIST_ENTRY *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001b634`

## callees

- `0x1800044e0`
- `0x180004e20`
- `0x18000c690`
- `0x18001b26c`
- `0x18001bcc8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001be95`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001be95`

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
0x18001bcc8  push    rbp
0x18001bcca  push    rbx
0x18001bccb  push    rsi
0x18001bccc  push    rdi
0x18001bccd  lea     rbp, [rsp-3Fh]
0x18001bcd2  sub     rsp, 0C8h
0x18001bcd9  mov     rbx, rdx
0x18001bcdc  mov     rsi, rcx
0x18001bcdf  mov     edi, 8000FFFFh
0x18001bce4  xorps   xmm0, xmm0
0x18001bce7  xor     eax, eax
0x18001bce9  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18001bced  mov     qword ptr [rbp+57h+pvar+10h], rax
0x18001bcf1  mov     [rbp+57h+var_98.fmtid.Data1], eax
0x18001bcf4  movups  xmmword ptr [rbp+57h+var_98.fmtid.Data2], xmm0
0x18001bcf8  mov     [rbp+57h+var_80.fmtid.Data1], eax
0x18001bcfb  xorps   xmm1, xmm1
0x18001bcfe  movups  xmmword ptr [rbp+57h+var_80.fmtid.Data2], xmm1
0x18001bd02  mov     [rbp+57h+var_68.fmtid.Data1], eax
0x18001bd05  movups  xmmword ptr [rbp+57h+var_68.fmtid.Data2], xmm0
0x18001bd09  mov     [rbp+57h+var_B0.fmtid.Data1], eax
0x18001bd0c  movups  xmmword ptr [rbp+57h+var_B0.fmtid.Data2], xmm1
0x18001bd10  mov     ecx, [r8+18h]
0x18001bd14  sub     ecx, 1
0x18001bd17  jz      loc_18001BDD9
0x18001bd1d  sub     ecx, 1
0x18001bd20  jz      loc_18001BDAA
0x18001bd26  sub     ecx, 1
0x18001bd29  jz      short loc_18001BD7B
0x18001bd2b  sub     ecx, 1
0x18001bd2e  jz      loc_18001BDD9
0x18001bd34  sub     ecx, 1
0x18001bd37  jz      short loc_18001BDAA
0x18001bd39  sub     ecx, 1
0x18001bd3c  jz      short loc_18001BD7B
0x18001bd3e  sub     ecx, 1
0x18001bd41  jz      short loc_18001BD4C
0x18001bd43  cmp     ecx, 1
0x18001bd46  jnz     loc_18001BE91
0x18001bd4c  mov     qword ptr [rsp+0E0h+var_C0], rbx
0x18001bd51  lea     r9, [rbp+57h+var_68]
0x18001bd55  lea     r8, [rbp+57h+var_80]
0x18001bd59  lea     rdx, [rbp+57h+var_98]
0x18001bd5d  mov     ecx, 3
0x18001bd62  call    ?GetRationalKeysFromMap@@YAJW4RationalKeyType@@PEAU_tagpropertykey@@111@Z; GetRationalKeysFromMap(RationalKeyType,_tagpropertykey *,_tagpropertykey *,_tagpropertykey *,_tagpropertykey *)
0x18001bd67  mov     edi, eax
0x18001bd69  movups  xmm1, xmmword ptr [rbx]
0x18001bd6c  movups  xmmword ptr [rbp+57h+var_B0.fmtid.Data1], xmm1
0x18001bd70  mov     ecx, [rbx+10h]
0x18001bd73  mov     [rbp+57h+var_B0.pid], ecx
0x18001bd76  jmp     loc_18001BE00
0x18001bd7b  lea     rax, [rbp+57h+var_B0]
0x18001bd7f  mov     qword ptr [rsp+0E0h+var_C0], rax
0x18001bd84  mov     r9, rbx
0x18001bd87  lea     r8, [rbp+57h+var_80]
0x18001bd8b  lea     rdx, [rbp+57h+var_98]
0x18001bd8f  mov     ecx, 2
0x18001bd94  call    ?GetRationalKeysFromMap@@YAJW4RationalKeyType@@PEAU_tagpropertykey@@111@Z; GetRationalKeysFromMap(RationalKeyType,_tagpropertykey *,_tagpropertykey *,_tagpropertykey *,_tagpropertykey *)
0x18001bd99  mov     edi, eax
0x18001bd9b  movups  xmm1, xmmword ptr [rbx]
0x18001bd9e  movups  xmmword ptr [rbp+57h+var_68.fmtid.Data1], xmm1
0x18001bda2  mov     eax, [rbx+10h]
0x18001bda5  mov     [rbp+57h+var_68.pid], eax
0x18001bda8  jmp     short loc_18001BE00
0x18001bdaa  lea     rax, [rbp+57h+var_B0]
0x18001bdae  mov     qword ptr [rsp+0E0h+var_C0], rax
0x18001bdb3  lea     r9, [rbp+57h+var_68]
0x18001bdb7  mov     r8, rbx
0x18001bdba  lea     rdx, [rbp+57h+var_98]
0x18001bdbe  mov     ecx, 1
0x18001bdc3  call    ?GetRationalKeysFromMap@@YAJW4RationalKeyType@@PEAU_tagpropertykey@@111@Z; GetRationalKeysFromMap(RationalKeyType,_tagpropertykey *,_tagpropertykey *,_tagpropertykey *,_tagpropertykey *)
0x18001bdc8  mov     edi, eax
0x18001bdca  movups  xmm1, xmmword ptr [rbx]
0x18001bdcd  movups  xmmword ptr [rbp+57h+var_80.fmtid.Data1], xmm1
0x18001bdd1  mov     eax, [rbx+10h]
0x18001bdd4  mov     [rbp+57h+var_80.pid], eax
0x18001bdd7  jmp     short loc_18001BE00
0x18001bdd9  lea     rax, [rbp+57h+var_B0]
0x18001bddd  mov     qword ptr [rsp+0E0h+var_C0], rax
0x18001bde2  lea     r9, [rbp+57h+var_68]
0x18001bde6  lea     r8, [rbp+57h+var_80]
0x18001bdea  xor     ecx, ecx
0x18001bdec  call    ?GetRationalKeysFromMap@@YAJW4RationalKeyType@@PEAU_tagpropertykey@@111@Z; GetRationalKeysFromMap(RationalKeyType,_tagpropertykey *,_tagpropertykey *,_tagpropertykey *,_tagpropertykey *)
0x18001bdf1  mov     edi, eax
0x18001bdf3  movups  xmm1, xmmword ptr [rbx]
0x18001bdf6  movups  xmmword ptr [rbp+57h+var_98.fmtid.Data1], xmm1
0x18001bdfa  mov     eax, [rbx+10h]
0x18001bdfd  mov     [rbp+57h+var_98.pid], eax
0x18001be00  test    edi, edi
0x18001be02  js      loc_18001BE91
0x18001be08  xorps   xmm0, xmm0
0x18001be0b  xor     eax, eax
0x18001be0d  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x18001be11  mov     qword ptr [rbp+57h+var_50+10h], rax
0x18001be15  mov     rcx, rsi; this
0x18001be18  call    ?ReadInMetadata@CMetadataContainer@@QEAAJXZ; CMetadataContainer::ReadInMetadata(void)
0x18001be1d  lea     rcx, [rsi+78h]; this
0x18001be21  mov     [rsp+0E0h+var_C0], 0; bool
0x18001be26  mov     r9b, 1; bool
0x18001be29  lea     r8, [rbp+57h+var_50]; struct tagPROPVARIANT *
0x18001be2d  lea     rdx, [rbp+57h+var_B0]; struct _tagpropertykey *
0x18001be31  call    ?_InternalUpdateOrAddItem@CPhotoPropertyItemList@@AEAAJPEBU_tagpropertykey@@PEBUtagPROPVARIANT@@_N2@Z; CPhotoPropertyItemList::_InternalUpdateOrAddItem(_tagpropertykey const *,tagPROPVARIANT const *,bool,bool)
0x18001be36  mov     edi, eax
0x18001be38  test    eax, eax
0x18001be3a  js      short loc_18001BE91
0x18001be3c  lea     rbx, [rsi+60h]
0x18001be40  mov     rcx, rsi; this
0x18001be43  call    ?ReadInMetadata@CMetadataContainer@@QEAAJXZ; CMetadataContainer::ReadInMetadata(void)
0x18001be48  lea     rdx, [rbp+57h+var_98]; struct _tagpropertykey *
0x18001be4c  mov     rcx, rbx; this
0x18001be4f  call    ?_InternalDeleteItem@CPhotoPropertyItemList@@AEAAJPEBU_tagpropertykey@@@Z; CPhotoPropertyItemList::_InternalDeleteItem(_tagpropertykey const *)
0x18001be54  mov     rcx, rsi; this
0x18001be57  call    ?ReadInMetadata@CMetadataContainer@@QEAAJXZ; CMetadataContainer::ReadInMetadata(void)
0x18001be5c  lea     rdx, [rbp+57h+var_80]; struct _tagpropertykey *
0x18001be60  mov     rcx, rbx; this
0x18001be63  call    ?_InternalDeleteItem@CPhotoPropertyItemList@@AEAAJPEBU_tagpropertykey@@@Z; CPhotoPropertyItemList::_InternalDeleteItem(_tagpropertykey const *)
0x18001be68  mov     rcx, rsi; this
0x18001be6b  call    ?ReadInMetadata@CMetadataContainer@@QEAAJXZ; CMetadataContainer::ReadInMetadata(void)
0x18001be70  lea     rdx, [rbp+57h+var_68]; struct _tagpropertykey *
0x18001be74  mov     rcx, rbx; this
0x18001be77  call    ?_InternalDeleteItem@CPhotoPropertyItemList@@AEAAJPEBU_tagpropertykey@@@Z; CPhotoPropertyItemList::_InternalDeleteItem(_tagpropertykey const *)
0x18001be7c  mov     rcx, rsi; this
0x18001be7f  call    ?ReadInMetadata@CMetadataContainer@@QEAAJXZ; CMetadataContainer::ReadInMetadata(void)
0x18001be84  lea     rdx, [rbp+57h+var_B0]; struct _tagpropertykey *
0x18001be88  mov     rcx, rbx; this
0x18001be8b  call    ?_InternalDeleteItem@CPhotoPropertyItemList@@AEAAJPEBU_tagpropertykey@@@Z; CPhotoPropertyItemList::_InternalDeleteItem(_tagpropertykey const *)
0x18001be90  nop
0x18001be91  lea     rcx, [rbp+57h+pvar]; pvar
0x18001be95  call    cs:__imp_PropVariantClear
0x18001be9c  nop     dword ptr [rax+rax+00h]
0x18001bea1  mov     eax, edi
0x18001bea3  add     rsp, 0C8h
0x18001beaa  pop     rdi
0x18001beab  pop     rsi
0x18001beac  pop     rbx
0x18001bead  pop     rbp
0x18001beae  retn
```
