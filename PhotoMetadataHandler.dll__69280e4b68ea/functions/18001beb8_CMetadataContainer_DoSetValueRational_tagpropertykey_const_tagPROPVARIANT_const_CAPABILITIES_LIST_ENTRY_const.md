# CMetadataContainer::_DoSetValueRational(_tagpropertykey const *,tagPROPVARIANT const *,CAPABILITIES_LIST_ENTRY const *)

- ea: `0x18001beb8`
- end: `0x18001c2b4`
- name: `?_DoSetValueRational@CMetadataContainer@@AEAAJPEBU_tagpropertykey@@PEBUtagPROPVARIANT@@PEBUCAPABILITIES_LIST_ENTRY@@@Z`
- size: `1020`
- prototype: `__int64 __fastcall(CMetadataContainer *__hidden this, const struct _tagpropertykey *, const struct tagPROPVARIANT *, const struct CAPABILITIES_LIST_ENTRY *)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001b6d8`

## callees

- `0x1800044e0`
- `0x180004e20`
- `0x180006218`
- `0x180009140`
- `0x1800096f0`
- `0x18000a720`
- `0x18000c690`
- `0x1800141ec`
- `0x180014244`
- `0x18001b26c`
- `0x18001beb8`
- `0x18001f51c`
- `0x18001f764`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18001c060`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18001c060`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001c25d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001c26e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001c27f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001c291`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001c25d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001c26e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001c27f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001c291`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CMetadataContainer::_DoSetValueRational(
        CMetadataContainer *this,
        const struct _tagpropertykey *a2,
        struct tagPROPVARIANT *a3,
        const struct CAPABILITIES_LIST_ENTRY *a4)
{
  const struct tagPROPVARIANT *v7; // r15
  const struct tagPROPVARIANT *v8; // r12
  HRESULT RationalKeysFromMap; // ebx
  HRESULT v10; // eax
  CPhotoPropertyItemList *v11; // rsi
  const struct tagPROPVARIANT *v12; // r8
  PROPVARIANT pvarDest; // [rsp+30h] [rbp-A9h] BYREF
  struct _tagpropertykey v15; // [rsp+48h] [rbp-91h] BYREF
  struct _tagpropertykey v16; // [rsp+60h] [rbp-79h] BYREF
  struct _tagpropertykey v17; // [rsp+78h] [rbp-61h] BYREF
  struct _tagpropertykey v18; // [rsp+90h] [rbp-49h] BYREF
  PROPVARIANT pvar; // [rsp+A8h] [rbp-31h] BYREF
  PROPVARIANT v20; // [rsp+C0h] [rbp-19h] BYREF
  PROPVARIANT v21; // [rsp+D8h] [rbp-1h] BYREF

  memset(&pvarDest, 0, sizeof(pvarDest));
  memset(&v21, 0, sizeof(v21));
  memset(&v20, 0, sizeof(v20));
  memset(&pvar, 0, sizeof(pvar));
  memset(&v18, 0, sizeof(v18));
  memset(&v16, 0, sizeof(v16));
  memset(&v17, 0, sizeof(v17));
  memset(&v15, 0, sizeof(v15));
  v7 = 0;
  v8 = 0;
  switch ( *((_DWORD *)a4 + 6) )
  {
    case 1:
      goto LABEL_42;
    case 2:
      goto LABEL_19;
    case 3:
LABEL_18:
      RationalKeysFromMap = GetRationalKeysFromMap(2, &v18, &v16, a2, &v15);
      v8 = a3;
      v17 = *a2;
      goto LABEL_20;
    case 4:
LABEL_42:
      RationalKeysFromMap = -2147024891;
      goto LABEL_43;
  }
  if ( *((_DWORD *)a4 + 6) != 5 )
  {
    if ( *((_DWORD *)a4 + 6) != 6 )
    {
      if ( *((_DWORD *)a4 + 6) == 7 )
      {
        RationalKeysFromMap = GetRationalKeysFromMap(3, &v18, &v16, &v17, a2);
        if ( RationalKeysFromMap < 0 )
          goto LABEL_43;
        v15 = *a2;
        if ( a3->vt == 31 )
        {
          v10 = ConvertRationalText(a3, &v21, &v20, &pvar, &pvarDest, 0);
LABEL_17:
          RationalKeysFromMap = v10;
          goto LABEL_20;
        }
      }
      else
      {
        if ( *((_DWORD *)a4 + 6) != 8 )
        {
          RationalKeysFromMap = -2147418113;
          goto LABEL_43;
        }
        RationalKeysFromMap = GetRationalKeysFromMap(3, &v18, &v16, &v17, a2);
        if ( RationalKeysFromMap < 0 )
          goto LABEL_43;
        v15 = *a2;
        if ( a3->vt == 31 )
        {
          RationalKeysFromMap = ConvertGPSCoordinateTextToVector(a3, &v21, &v20, &pvar, &pvarDest);
          CMetadataContainer::_AddReferencePKEYToList(this, &v18, *((unsigned int *)pvarDest.bstrblobVal.pData + 6));
          goto LABEL_20;
        }
      }
      v10 = PropVariantCopy(&pvarDest, a3);
      goto LABEL_17;
    }
    goto LABEL_18;
  }
LABEL_19:
  RationalKeysFromMap = GetRationalKeysFromMap(1, &v18, a2, &v17, &v15);
  v7 = a3;
  v16 = *a2;
LABEL_20:
  if ( RationalKeysFromMap < 0 )
    goto LABEL_43;
  if ( pvarDest.vt )
  {
    v11 = (CMetadataContainer *)((char *)this + 96);
LABEL_32:
    CMetadataContainer::ReadInMetadata(this);
    RationalKeysFromMap = CPhotoPropertyItemList::_InternalDeleteItem((CMetadataContainer *)((char *)this + 120), &v15);
    if ( RationalKeysFromMap >= 0 )
    {
      CMetadataContainer::ReadInMetadata(this);
      RationalKeysFromMap = CPhotoPropertyItemList::_InternalUpdateOrAddItem(v11, &v15, &pvarDest, 1, 1);
      if ( RationalKeysFromMap >= 0 )
      {
        if ( v21.vt && v20.vt
          || (RationalKeysFromMap = ConstructNumeratorAndDenominatorFromRationalPropvar(&pvarDest, &v21, &v20),
              RationalKeysFromMap >= 0) )
        {
          CMetadataContainer::ReadInMetadata(this);
          RationalKeysFromMap = CPhotoPropertyItemList::_InternalUpdateOrAddItem(v11, &v16, &v21, 0, 0);
          if ( RationalKeysFromMap >= 0 )
          {
            CMetadataContainer::ReadInMetadata(this);
            RationalKeysFromMap = CPhotoPropertyItemList::_InternalUpdateOrAddItem(v11, &v17, &v20, 0, 0);
            if ( RationalKeysFromMap >= 0 )
            {
              if ( pvar.vt
                || (RationalKeysFromMap = ConstructR8FromRationalPropvar(&pvarDest, &pvar), RationalKeysFromMap >= 0) )
              {
                CMetadataContainer::ReadInMetadata(this);
                RationalKeysFromMap = CPhotoPropertyItemList::_InternalUpdateOrAddItem(v11, &v18, &pvar, 0, 0);
              }
            }
          }
        }
      }
    }
    goto LABEL_43;
  }
  CMetadataContainer::ReadInMetadata(this);
  v11 = (CMetadataContainer *)((char *)this + 96);
  if ( CPhotoPropertyItemList::GetItem((CMetadataContainer *)((char *)this + 96), &v15, &pvarDest) >= 0 && pvarDest.vt
    || (RationalKeysFromMap = CreateDefaultProxyVariant(&pvarDest, a3), RationalKeysFromMap >= 0) )
  {
    v12 = a3;
    if ( a3 != v8 )
      v12 = 0;
    if ( a3 != v7 )
      a3 = 0;
    RationalKeysFromMap = UpdateRationalPropvar(&pvarDest, a3, v12);
    if ( RationalKeysFromMap >= 0 )
      goto LABEL_32;
  }
LABEL_43:
  PropVariantClear(&pvar);
  PropVariantClear(&v20);
  PropVariantClear(&v21);
  PropVariantClear(&pvarDest);
  return (unsigned int)RationalKeysFromMap;
}

```

## disassembly

```asm
0x18001beb8  push    rbp
0x18001beba  push    rbx
0x18001bebb  push    rsi
0x18001bebc  push    rdi
0x18001bebd  push    r12
0x18001bebf  push    r13
0x18001bec1  push    r14
0x18001bec3  push    r15
0x18001bec5  lea     rbp, [rsp-1Fh]
0x18001beca  sub     rsp, 0F8h
0x18001bed1  mov     rdi, r8
0x18001bed4  mov     rsi, rdx
0x18001bed7  mov     r14, rcx
0x18001beda  xorps   xmm0, xmm0
0x18001bedd  xor     eax, eax
0x18001bedf  movups  xmmword ptr [rsp+130h+pvarDest], xmm0
0x18001bee4  mov     qword ptr [rsp+130h+pvarDest+10h], rax
0x18001bee9  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x18001beed  mov     qword ptr [rbp+57h+var_58+10h], rax
0x18001bef1  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x18001bef5  mov     qword ptr [rbp+57h+var_70+10h], rax
0x18001bef9  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18001befd  mov     qword ptr [rbp+57h+pvar+10h], rax
0x18001bf01  xor     r13d, r13d
0x18001bf04  mov     [rbp+57h+var_A0.fmtid.Data1], r13d
0x18001bf08  movups  xmmword ptr [rbp+57h+var_A0.fmtid.Data2], xmm0
0x18001bf0c  mov     [rbp+57h+var_D0.fmtid.Data1], r13d
0x18001bf10  xorps   xmm1, xmm1
0x18001bf13  movups  xmmword ptr [rbp+57h+var_D0.fmtid.Data2], xmm1
0x18001bf17  mov     [rbp+57h+var_B8.fmtid.Data1], r13d
0x18001bf1b  movups  xmmword ptr [rbp+57h+var_B8.fmtid.Data2], xmm0
0x18001bf1f  mov     [rsp+130h+var_E8.fmtid.Data1], r13d
0x18001bf24  movups  xmmword ptr [rsp+130h+var_E8.fmtid.Data2], xmm1
0x18001bf29  mov     r15d, r13d
0x18001bf2c  mov     r12d, r13d
0x18001bf2f  mov     ecx, [r9+18h]
0x18001bf33  sub     ecx, 1
0x18001bf36  jz      loc_18001C254
0x18001bf3c  sub     ecx, 1
0x18001bf3f  jz      loc_18001C0A3
0x18001bf45  sub     ecx, 1
0x18001bf48  jz      loc_18001C070
0x18001bf4e  sub     ecx, 1
0x18001bf51  jz      loc_18001C254
0x18001bf57  sub     ecx, 1
0x18001bf5a  jz      loc_18001C0A3
0x18001bf60  sub     ecx, 1
0x18001bf63  jz      loc_18001C070
0x18001bf69  sub     ecx, 1
0x18001bf6c  jz      loc_18001BFF9
0x18001bf72  cmp     ecx, 1
0x18001bf75  jz      short loc_18001BF81
0x18001bf77  mov     ebx, 8000FFFFh
0x18001bf7c  jmp     loc_18001C259
0x18001bf81  mov     [rsp+130h+var_110], rsi
0x18001bf86  lea     r9, [rbp+57h+var_B8]
0x18001bf8a  lea     r8, [rbp+57h+var_D0]
0x18001bf8e  lea     rdx, [rbp+57h+var_A0]
0x18001bf92  mov     ecx, 3
0x18001bf97  call    ?GetRationalKeysFromMap@@YAJW4RationalKeyType@@PEAU_tagpropertykey@@111@Z; GetRationalKeysFromMap(RationalKeyType,_tagpropertykey *,_tagpropertykey *,_tagpropertykey *,_tagpropertykey *)
0x18001bf9c  mov     ebx, eax
0x18001bf9e  test    eax, eax
0x18001bfa0  js      loc_18001C259
0x18001bfa6  movups  xmm0, xmmword ptr [rsi]
0x18001bfa9  movups  xmmword ptr [rsp+130h+var_E8.fmtid.Data1], xmm0
0x18001bfae  mov     eax, [rsi+10h]
0x18001bfb1  mov     [rsp+130h+var_E8.pid], eax
0x18001bfb5  cmp     word ptr [rdi], 1Fh
0x18001bfb9  jnz     loc_18001C058
0x18001bfbf  lea     rax, [rsp+130h+pvarDest]
0x18001bfc4  mov     [rsp+130h+var_110], rax; PROPVARIANT *
0x18001bfc9  lea     r9, [rbp+57h+pvar]; PROPVARIANT *
0x18001bfcd  lea     r8, [rbp+57h+var_70]; PROPVARIANT *
0x18001bfd1  lea     rdx, [rbp+57h+var_58]; pvar
0x18001bfd5  mov     rcx, rdi; pvarSrc
0x18001bfd8  call    ?ConvertGPSCoordinateTextToVector@@YAJPEBUtagPROPVARIANT@@PEAU1@111@Z; ConvertGPSCoordinateTextToVector(tagPROPVARIANT const *,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *)
0x18001bfdd  mov     ebx, eax
0x18001bfdf  mov     r8, qword ptr [rsp+130h+pvarDest+10h]
0x18001bfe4  mov     r8d, [r8+18h]
0x18001bfe8  lea     rdx, [rbp+57h+var_A0]
0x18001bfec  mov     rcx, r14
0x18001bfef  call    ?_AddReferencePKEYToList@CMetadataContainer@@AEAAXAEBU_tagpropertykey@@W4GPSCoordinateReferenceType@@@Z; CMetadataContainer::_AddReferencePKEYToList(_tagpropertykey const &,GPSCoordinateReferenceType)
0x18001bff4  jmp     loc_18001C0D4
0x18001bff9  mov     [rsp+130h+var_110], rsi
0x18001bffe  lea     r9, [rbp+57h+var_B8]
0x18001c002  lea     r8, [rbp+57h+var_D0]
0x18001c006  lea     rdx, [rbp+57h+var_A0]
0x18001c00a  mov     ecx, 3
0x18001c00f  call    ?GetRationalKeysFromMap@@YAJW4RationalKeyType@@PEAU_tagpropertykey@@111@Z; GetRationalKeysFromMap(RationalKeyType,_tagpropertykey *,_tagpropertykey *,_tagpropertykey *,_tagpropertykey *)
0x18001c014  mov     ebx, eax
0x18001c016  test    eax, eax
0x18001c018  js      loc_18001C259
0x18001c01e  movups  xmm0, xmmword ptr [rsi]
0x18001c021  movups  xmmword ptr [rsp+130h+var_E8.fmtid.Data1], xmm0
0x18001c026  mov     eax, [rsi+10h]
0x18001c029  mov     [rsp+130h+var_E8.pid], eax
0x18001c02d  cmp     word ptr [rdi], 1Fh
0x18001c031  jnz     short loc_18001C058
0x18001c033  mov     [rsp+130h+var_108], r13b; bool
0x18001c038  lea     rax, [rsp+130h+pvarDest]
0x18001c03d  mov     [rsp+130h+var_110], rax; struct tagPROPVARIANT *
0x18001c042  lea     r9, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x18001c046  lea     r8, [rbp+57h+var_70]; struct tagPROPVARIANT *
0x18001c04a  lea     rdx, [rbp+57h+var_58]; struct tagPROPVARIANT *
0x18001c04e  mov     rcx, rdi; struct tagPROPVARIANT *
0x18001c051  call    ?ConvertRationalText@@YAJPEBUtagPROPVARIANT@@PEAU1@111_N@Z; ConvertRationalText(tagPROPVARIANT const *,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *,bool)
0x18001c056  jmp     short loc_18001C06C
0x18001c058  mov     rdx, rdi; pvarSrc
0x18001c05b  lea     rcx, [rsp+130h+pvarDest]; pvarDest
0x18001c060  call    cs:__imp_PropVariantCopy
0x18001c067  nop     dword ptr [rax+rax+00h]
0x18001c06c  mov     ebx, eax
0x18001c06e  jmp     short loc_18001C0D4
0x18001c070  lea     rax, [rsp+130h+var_E8]
0x18001c075  mov     [rsp+130h+var_110], rax
0x18001c07a  mov     r9, rsi
0x18001c07d  lea     r8, [rbp+57h+var_D0]
0x18001c081  lea     rdx, [rbp+57h+var_A0]
0x18001c085  mov     ecx, 2
0x18001c08a  call    ?GetRationalKeysFromMap@@YAJW4RationalKeyType@@PEAU_tagpropertykey@@111@Z; GetRationalKeysFromMap(RationalKeyType,_tagpropertykey *,_tagpropertykey *,_tagpropertykey *,_tagpropertykey *)
0x18001c08f  mov     ebx, eax
0x18001c091  mov     r12, rdi
0x18001c094  movups  xmm0, xmmword ptr [rsi]
0x18001c097  movups  xmmword ptr [rbp+57h+var_B8.fmtid.Data1], xmm0
0x18001c09b  mov     eax, [rsi+10h]
0x18001c09e  mov     [rbp+57h+var_B8.pid], eax
0x18001c0a1  jmp     short loc_18001C0D4
0x18001c0a3  lea     rax, [rsp+130h+var_E8]
0x18001c0a8  mov     [rsp+130h+var_110], rax
0x18001c0ad  lea     r9, [rbp+57h+var_B8]
0x18001c0b1  mov     r8, rsi
0x18001c0b4  lea     rdx, [rbp+57h+var_A0]
0x18001c0b8  mov     ecx, 1
0x18001c0bd  call    ?GetRationalKeysFromMap@@YAJW4RationalKeyType@@PEAU_tagpropertykey@@111@Z; GetRationalKeysFromMap(RationalKeyType,_tagpropertykey *,_tagpropertykey *,_tagpropertykey *,_tagpropertykey *)
0x18001c0c2  mov     ebx, eax
0x18001c0c4  mov     r15, rdi
0x18001c0c7  movups  xmm0, xmmword ptr [rsi]
0x18001c0ca  movups  xmmword ptr [rbp+57h+var_D0.fmtid.Data1], xmm0
0x18001c0ce  mov     eax, [rsi+10h]
0x18001c0d1  mov     [rbp+57h+var_D0.pid], eax
0x18001c0d4  test    ebx, ebx
0x18001c0d6  js      loc_18001C259
0x18001c0dc  cmp     r13w, word ptr [rsp+130h+pvarDest]
0x18001c0e2  jnz     short loc_18001C14F
0x18001c0e4  mov     rcx, r14; this
0x18001c0e7  call    ?ReadInMetadata@CMetadataContainer@@QEAAJXZ; CMetadataContainer::ReadInMetadata(void)
0x18001c0ec  lea     rsi, [r14+60h]
0x18001c0f0  lea     r8, [rsp+130h+pvarDest]; struct tagPROPVARIANT *
0x18001c0f5  lea     rdx, [rsp+130h+var_E8]; struct _tagpropertykey *
0x18001c0fa  mov     rcx, rsi; this
0x18001c0fd  call    ?GetItem@CPhotoPropertyItemList@@QEAAJPEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z; CPhotoPropertyItemList::GetItem(_tagpropertykey const *,tagPROPVARIANT *)
0x18001c102  test    eax, eax
0x18001c104  js      short loc_18001C10E
0x18001c106  cmp     r13w, word ptr [rsp+130h+pvarDest]
0x18001c10c  jnz     short loc_18001C125
0x18001c10e  mov     rdx, rdi; struct tagPROPVARIANT *
0x18001c111  lea     rcx, [rsp+130h+pvarDest]; struct tagPROPVARIANT *
0x18001c116  call    ?CreateDefaultProxyVariant@@YAJPEAUtagPROPVARIANT@@PEBU1@@Z; CreateDefaultProxyVariant(tagPROPVARIANT *,tagPROPVARIANT const *)
0x18001c11b  mov     ebx, eax
0x18001c11d  test    eax, eax
0x18001c11f  js      loc_18001C259
0x18001c125  mov     r8, rdi
0x18001c128  cmp     rdi, r12
0x18001c12b  cmovnz  r8, r13; struct tagPROPVARIANT *
0x18001c12f  cmp     rdi, r15
0x18001c132  cmovnz  rdi, r13
0x18001c136  mov     rdx, rdi; struct tagPROPVARIANT *
0x18001c139  lea     rcx, [rsp+130h+pvarDest]; struct tagPROPVARIANT *
0x18001c13e  call    ?UpdateRationalPropvar@@YAJPEAUtagPROPVARIANT@@PEBU1@1@Z; UpdateRationalPropvar(tagPROPVARIANT *,tagPROPVARIANT const *,tagPROPVARIANT const *)
0x18001c143  mov     ebx, eax
0x18001c145  test    eax, eax
0x18001c147  js      loc_18001C259
0x18001c14d  jmp     short loc_18001C153
0x18001c14f  lea     rsi, [r14+60h]
0x18001c153  mov     rcx, r14; this
0x18001c156  call    ?ReadInMetadata@CMetadataContainer@@QEAAJXZ; CMetadataContainer::ReadInMetadata(void)
0x18001c15b  lea     rcx, [r14+78h]; this
0x18001c15f  lea     rdx, [rsp+130h+var_E8]; struct _tagpropertykey *
0x18001c164  call    ?_InternalDeleteItem@CPhotoPropertyItemList@@AEAAJPEBU_tagpropertykey@@@Z; CPhotoPropertyItemList::_InternalDeleteItem(_tagpropertykey const *)
0x18001c169  mov     ebx, eax
0x18001c16b  test    eax, eax
0x18001c16d  js      loc_18001C259
0x18001c173  mov     rcx, r14; this
0x18001c176  call    ?ReadInMetadata@CMetadataContainer@@QEAAJXZ; CMetadataContainer::ReadInMetadata(void)
0x18001c17b  mov     byte ptr [rsp+130h+var_110], 1; bool
0x18001c180  mov     r9b, 1; bool
0x18001c183  lea     r8, [rsp+130h+pvarDest]; struct tagPROPVARIANT *
0x18001c188  lea     rdx, [rsp+130h+var_E8]; struct _tagpropertykey *
0x18001c18d  mov     rcx, rsi; this
0x18001c190  call    ?_InternalUpdateOrAddItem@CPhotoPropertyItemList@@AEAAJPEBU_tagpropertykey@@PEBUtagPROPVARIANT@@_N2@Z; CPhotoPropertyItemList::_InternalUpdateOrAddItem(_tagpropertykey const *,tagPROPVARIANT const *,bool,bool)
0x18001c195  mov     ebx, eax
0x18001c197  test    eax, eax
0x18001c199  js      loc_18001C259
0x18001c19f  cmp     word ptr [rbp+57h+var_58], r13w
0x18001c1a4  jz      short loc_18001C1AD
0x18001c1a6  cmp     word ptr [rbp+57h+var_70], r13w
0x18001c1ab  jnz     short loc_18001C1C9
0x18001c1ad  lea     r8, [rbp+57h+var_70]; struct tagPROPVARIANT *
0x18001c1b1  lea     rdx, [rbp+57h+var_58]; struct tagPROPVARIANT *
0x18001c1b5  lea     rcx, [rsp+130h+pvarDest]; struct tagPROPVARIANT *
0x18001c1ba  call    ?ConstructNumeratorAndDenominatorFromRationalPropvar@@YAJPEBUtagPROPVARIANT@@PEAU1@1@Z; ConstructNumeratorAndDenominatorFromRationalPropvar(tagPROPVARIANT const *,tagPROPVARIANT *,tagPROPVARIANT *)
0x18001c1bf  mov     ebx, eax
0x18001c1c1  test    eax, eax
0x18001c1c3  js      loc_18001C259
0x18001c1c9  mov     rcx, r14; this
0x18001c1cc  call    ?ReadInMetadata@CMetadataContainer@@QEAAJXZ; CMetadataContainer::ReadInMetadata(void)
0x18001c1d1  mov     byte ptr [rsp+130h+var_110], r13b; bool
0x18001c1d6  xor     r9d, r9d; bool
0x18001c1d9  lea     r8, [rbp+57h+var_58]; struct tagPROPVARIANT *
0x18001c1dd  lea     rdx, [rbp+57h+var_D0]; struct _tagpropertykey *
0x18001c1e1  mov     rcx, rsi; this
0x18001c1e4  call    ?_InternalUpdateOrAddItem@CPhotoPropertyItemList@@AEAAJPEBU_tagpropertykey@@PEBUtagPROPVARIANT@@_N2@Z; CPhotoPropertyItemList::_InternalUpdateOrAddItem(_tagpropertykey const *,tagPROPVARIANT const *,bool,bool)
0x18001c1e9  mov     ebx, eax
0x18001c1eb  test    eax, eax
0x18001c1ed  js      short loc_18001C259
0x18001c1ef  mov     rcx, r14; this
0x18001c1f2  call    ?ReadInMetadata@CMetadataContainer@@QEAAJXZ; CMetadataContainer::ReadInMetadata(void)
0x18001c1f7  mov     byte ptr [rsp+130h+var_110], r13b; bool
0x18001c1fc  xor     r9d, r9d; bool
0x18001c1ff  lea     r8, [rbp+57h+var_70]; struct tagPROPVARIANT *
0x18001c203  lea     rdx, [rbp+57h+var_B8]; struct _tagpropertykey *
0x18001c207  mov     rcx, rsi; this
0x18001c20a  call    ?_InternalUpdateOrAddItem@CPhotoPropertyItemList@@AEAAJPEBU_tagpropertykey@@PEBUtagPROPVARIANT@@_N2@Z; CPhotoPropertyItemList::_InternalUpdateOrAddItem(_tagpropertykey const *,tagPROPVARIANT const *,bool,bool)
0x18001c20f  mov     ebx, eax
0x18001c211  test    eax, eax
0x18001c213  js      short loc_18001C259
0x18001c215  cmp     word ptr [rbp+57h+pvar], r13w
0x18001c21a  jnz     short loc_18001C230
0x18001c21c  lea     rdx, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x18001c220  lea     rcx, [rsp+130h+pvarDest]; struct tagPROPVARIANT *
0x18001c225  call    ?ConstructR8FromRationalPropvar@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; ConstructR8FromRationalPropvar(tagPROPVARIANT const *,tagPROPVARIANT *)
0x18001c22a  mov     ebx, eax
0x18001c22c  test    eax, eax
0x18001c22e  js      short loc_18001C259
0x18001c230  mov     rcx, r14; this
0x18001c233  call    ?ReadInMetadata@CMetadataContainer@@QEAAJXZ; CMetadataContainer::ReadInMetadata(void)
0x18001c238  mov     byte ptr [rsp+130h+var_110], r13b; bool
0x18001c23d  xor     r9d, r9d; bool
0x18001c240  lea     r8, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x18001c244  lea     rdx, [rbp+57h+var_A0]; struct _tagpropertykey *
0x18001c248  mov     rcx, rsi; this
0x18001c24b  call    ?_InternalUpdateOrAddItem@CPhotoPropertyItemList@@AEAAJPEBU_tagpropertykey@@PEBUtagPROPVARIANT@@_N2@Z; CPhotoPropertyItemList::_InternalUpdateOrAddItem(_tagpropertykey const *,tagPROPVARIANT const *,bool,bool)
0x18001c250  mov     ebx, eax
0x18001c252  jmp     short loc_18001C259
0x18001c254  mov     ebx, 80070005h
0x18001c259  lea     rcx, [rbp+57h+pvar]; pvar
0x18001c25d  call    cs:__imp_PropVariantClear
0x18001c264  nop     dword ptr [rax+rax+00h]
0x18001c269  nop
0x18001c26a  lea     rcx, [rbp+57h+var_70]; pvar
0x18001c26e  call    cs:__imp_PropVariantClear
0x18001c275  nop     dword ptr [rax+rax+00h]
0x18001c27a  nop
0x18001c27b  lea     rcx, [rbp+57h+var_58]; pvar
0x18001c27f  call    cs:__imp_PropVariantClear
0x18001c286  nop     dword ptr [rax+rax+00h]
0x18001c28b  nop
0x18001c28c  lea     rcx, [rsp+130h+pvarDest]; pvar
0x18001c291  call    cs:__imp_PropVariantClear
0x18001c298  nop     dword ptr [rax+rax+00h]
0x18001c29d  mov     eax, ebx
0x18001c29f  add     rsp, 0F8h
0x18001c2a6  pop     r15
0x18001c2a8  pop     r14
0x18001c2aa  pop     r13
0x18001c2ac  pop     r12
0x18001c2ae  pop     rdi
0x18001c2af  pop     rsi
0x18001c2b0  pop     rbx
0x18001c2b1  pop     rbp
0x18001c2b2  retn
```
