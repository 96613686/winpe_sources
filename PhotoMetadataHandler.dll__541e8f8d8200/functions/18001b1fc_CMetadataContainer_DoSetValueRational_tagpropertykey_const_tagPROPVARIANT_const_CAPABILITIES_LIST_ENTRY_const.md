# CMetadataContainer::_DoSetValueRational(_tagpropertykey const *,tagPROPVARIANT const *,CAPABILITIES_LIST_ENTRY const *)

- ea: `0x18001b1fc`
- end: `0x18001b5d9`
- name: `?_DoSetValueRational@CMetadataContainer@@AEAAJPEBU_tagpropertykey@@PEBUtagPROPVARIANT@@PEBUCAPABILITIES_LIST_ENTRY@@@Z`
- size: `989`
- prototype: `__int64 __fastcall(CMetadataContainer *__hidden this, const struct _tagpropertykey *, const struct tagPROPVARIANT *, const struct CAPABILITIES_LIST_ENTRY *)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001aa2c`

## callees

- `0x180004490`
- `0x180004e00`
- `0x1800060dc`
- `0x180008de0`
- `0x180009010`
- `0x18000a160`
- `0x18000c0e0`
- `0x18001384c`
- `0x1800138a0`
- `0x18001a5d8`
- `0x18001b1fc`
- `0x18001e6a8`
- `0x18001e8e4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18001b3a4`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18001b3a4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001b59b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001b5a6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001b5b1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001b5bd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001b59b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001b5a6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001b5b1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001b5bd`

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
0x18001b1fc  push    rbp
0x18001b1fe  push    rbx
0x18001b1ff  push    rsi
0x18001b200  push    rdi
0x18001b201  push    r12
0x18001b203  push    r13
0x18001b205  push    r14
0x18001b207  push    r15
0x18001b209  lea     rbp, [rsp-1Fh]
0x18001b20e  sub     rsp, 0F8h
0x18001b215  mov     rdi, r8
0x18001b218  mov     rsi, rdx
0x18001b21b  mov     r14, rcx
0x18001b21e  xorps   xmm0, xmm0
0x18001b221  xor     eax, eax
0x18001b223  movups  xmmword ptr [rsp+130h+pvarDest], xmm0
0x18001b228  mov     qword ptr [rsp+130h+pvarDest+10h], rax
0x18001b22d  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x18001b231  mov     qword ptr [rbp+57h+var_58+10h], rax
0x18001b235  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x18001b239  mov     qword ptr [rbp+57h+var_70+10h], rax
0x18001b23d  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18001b241  mov     qword ptr [rbp+57h+pvar+10h], rax
0x18001b245  xor     r13d, r13d
0x18001b248  mov     [rbp+57h+var_A0.fmtid.Data1], r13d
0x18001b24c  movups  xmmword ptr [rbp+57h+var_A0.fmtid.Data2], xmm0
0x18001b250  mov     [rbp+57h+var_D0.fmtid.Data1], r13d
0x18001b254  xorps   xmm1, xmm1
0x18001b257  movups  xmmword ptr [rbp+57h+var_D0.fmtid.Data2], xmm1
0x18001b25b  mov     [rbp+57h+var_B8.fmtid.Data1], r13d
0x18001b25f  movups  xmmword ptr [rbp+57h+var_B8.fmtid.Data2], xmm0
0x18001b263  mov     [rsp+130h+var_E8.fmtid.Data1], r13d
0x18001b268  movups  xmmword ptr [rsp+130h+var_E8.fmtid.Data2], xmm1
0x18001b26d  mov     r15d, r13d
0x18001b270  mov     r12d, r13d
0x18001b273  mov     ecx, [r9+18h]
0x18001b277  sub     ecx, 1
0x18001b27a  jz      loc_18001B592
0x18001b280  sub     ecx, 1
0x18001b283  jz      loc_18001B3E1
0x18001b289  sub     ecx, 1
0x18001b28c  jz      loc_18001B3AE
0x18001b292  sub     ecx, 1
0x18001b295  jz      loc_18001B592
0x18001b29b  sub     ecx, 1
0x18001b29e  jz      loc_18001B3E1
0x18001b2a4  sub     ecx, 1
0x18001b2a7  jz      loc_18001B3AE
0x18001b2ad  sub     ecx, 1
0x18001b2b0  jz      loc_18001B33D
0x18001b2b6  cmp     ecx, 1
0x18001b2b9  jz      short loc_18001B2C5
0x18001b2bb  mov     ebx, 8000FFFFh
0x18001b2c0  jmp     loc_18001B597
0x18001b2c5  mov     [rsp+130h+var_110], rsi
0x18001b2ca  lea     r9, [rbp+57h+var_B8]
0x18001b2ce  lea     r8, [rbp+57h+var_D0]
0x18001b2d2  lea     rdx, [rbp+57h+var_A0]
0x18001b2d6  mov     ecx, 3
0x18001b2db  call    ?GetRationalKeysFromMap@@YAJW4RationalKeyType@@PEAU_tagpropertykey@@111@Z; GetRationalKeysFromMap(RationalKeyType,_tagpropertykey *,_tagpropertykey *,_tagpropertykey *,_tagpropertykey *)
0x18001b2e0  mov     ebx, eax
0x18001b2e2  test    eax, eax
0x18001b2e4  js      loc_18001B597
0x18001b2ea  movups  xmm0, xmmword ptr [rsi]
0x18001b2ed  movups  xmmword ptr [rsp+130h+var_E8.fmtid.Data1], xmm0
0x18001b2f2  mov     eax, [rsi+10h]
0x18001b2f5  mov     [rsp+130h+var_E8.pid], eax
0x18001b2f9  cmp     word ptr [rdi], 1Fh
0x18001b2fd  jnz     loc_18001B39C
0x18001b303  lea     rax, [rsp+130h+pvarDest]
0x18001b308  mov     [rsp+130h+var_110], rax; PROPVARIANT *
0x18001b30d  lea     r9, [rbp+57h+pvar]; PROPVARIANT *
0x18001b311  lea     r8, [rbp+57h+var_70]; PROPVARIANT *
0x18001b315  lea     rdx, [rbp+57h+var_58]; pvar
0x18001b319  mov     rcx, rdi; pvarSrc
0x18001b31c  call    ?ConvertGPSCoordinateTextToVector@@YAJPEBUtagPROPVARIANT@@PEAU1@111@Z; ConvertGPSCoordinateTextToVector(tagPROPVARIANT const *,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *)
0x18001b321  mov     ebx, eax
0x18001b323  mov     r8, qword ptr [rsp+130h+pvarDest+10h]
0x18001b328  mov     r8d, [r8+18h]
0x18001b32c  lea     rdx, [rbp+57h+var_A0]
0x18001b330  mov     rcx, r14
0x18001b333  call    ?_AddReferencePKEYToList@CMetadataContainer@@AEAAXAEBU_tagpropertykey@@W4GPSCoordinateReferenceType@@@Z; CMetadataContainer::_AddReferencePKEYToList(_tagpropertykey const &,GPSCoordinateReferenceType)
0x18001b338  jmp     loc_18001B412
0x18001b33d  mov     [rsp+130h+var_110], rsi
0x18001b342  lea     r9, [rbp+57h+var_B8]
0x18001b346  lea     r8, [rbp+57h+var_D0]
0x18001b34a  lea     rdx, [rbp+57h+var_A0]
0x18001b34e  mov     ecx, 3
0x18001b353  call    ?GetRationalKeysFromMap@@YAJW4RationalKeyType@@PEAU_tagpropertykey@@111@Z; GetRationalKeysFromMap(RationalKeyType,_tagpropertykey *,_tagpropertykey *,_tagpropertykey *,_tagpropertykey *)
0x18001b358  mov     ebx, eax
0x18001b35a  test    eax, eax
0x18001b35c  js      loc_18001B597
0x18001b362  movups  xmm0, xmmword ptr [rsi]
0x18001b365  movups  xmmword ptr [rsp+130h+var_E8.fmtid.Data1], xmm0
0x18001b36a  mov     eax, [rsi+10h]
0x18001b36d  mov     [rsp+130h+var_E8.pid], eax
0x18001b371  cmp     word ptr [rdi], 1Fh
0x18001b375  jnz     short loc_18001B39C
0x18001b377  mov     [rsp+130h+var_108], r13b; bool
0x18001b37c  lea     rax, [rsp+130h+pvarDest]
0x18001b381  mov     [rsp+130h+var_110], rax; struct tagPROPVARIANT *
0x18001b386  lea     r9, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x18001b38a  lea     r8, [rbp+57h+var_70]; struct tagPROPVARIANT *
0x18001b38e  lea     rdx, [rbp+57h+var_58]; struct tagPROPVARIANT *
0x18001b392  mov     rcx, rdi; struct tagPROPVARIANT *
0x18001b395  call    ?ConvertRationalText@@YAJPEBUtagPROPVARIANT@@PEAU1@111_N@Z; ConvertRationalText(tagPROPVARIANT const *,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *,bool)
0x18001b39a  jmp     short loc_18001B3AA
0x18001b39c  mov     rdx, rdi; pvarSrc
0x18001b39f  lea     rcx, [rsp+130h+pvarDest]; pvarDest
0x18001b3a4  call    cs:__imp_PropVariantCopy
0x18001b3aa  mov     ebx, eax
0x18001b3ac  jmp     short loc_18001B412
0x18001b3ae  lea     rax, [rsp+130h+var_E8]
0x18001b3b3  mov     [rsp+130h+var_110], rax
0x18001b3b8  mov     r9, rsi
0x18001b3bb  lea     r8, [rbp+57h+var_D0]
0x18001b3bf  lea     rdx, [rbp+57h+var_A0]
0x18001b3c3  mov     ecx, 2
0x18001b3c8  call    ?GetRationalKeysFromMap@@YAJW4RationalKeyType@@PEAU_tagpropertykey@@111@Z; GetRationalKeysFromMap(RationalKeyType,_tagpropertykey *,_tagpropertykey *,_tagpropertykey *,_tagpropertykey *)
0x18001b3cd  mov     ebx, eax
0x18001b3cf  mov     r12, rdi
0x18001b3d2  movups  xmm0, xmmword ptr [rsi]
0x18001b3d5  movups  xmmword ptr [rbp+57h+var_B8.fmtid.Data1], xmm0
0x18001b3d9  mov     eax, [rsi+10h]
0x18001b3dc  mov     [rbp+57h+var_B8.pid], eax
0x18001b3df  jmp     short loc_18001B412
0x18001b3e1  lea     rax, [rsp+130h+var_E8]
0x18001b3e6  mov     [rsp+130h+var_110], rax
0x18001b3eb  lea     r9, [rbp+57h+var_B8]
0x18001b3ef  mov     r8, rsi
0x18001b3f2  lea     rdx, [rbp+57h+var_A0]
0x18001b3f6  mov     ecx, 1
0x18001b3fb  call    ?GetRationalKeysFromMap@@YAJW4RationalKeyType@@PEAU_tagpropertykey@@111@Z; GetRationalKeysFromMap(RationalKeyType,_tagpropertykey *,_tagpropertykey *,_tagpropertykey *,_tagpropertykey *)
0x18001b400  mov     ebx, eax
0x18001b402  mov     r15, rdi
0x18001b405  movups  xmm0, xmmword ptr [rsi]
0x18001b408  movups  xmmword ptr [rbp+57h+var_D0.fmtid.Data1], xmm0
0x18001b40c  mov     eax, [rsi+10h]
0x18001b40f  mov     [rbp+57h+var_D0.pid], eax
0x18001b412  test    ebx, ebx
0x18001b414  js      loc_18001B597
0x18001b41a  cmp     r13w, word ptr [rsp+130h+pvarDest]
0x18001b420  jnz     short loc_18001B48D
0x18001b422  mov     rcx, r14; this
0x18001b425  call    ?ReadInMetadata@CMetadataContainer@@QEAAJXZ; CMetadataContainer::ReadInMetadata(void)
0x18001b42a  lea     rsi, [r14+60h]
0x18001b42e  lea     r8, [rsp+130h+pvarDest]; struct tagPROPVARIANT *
0x18001b433  lea     rdx, [rsp+130h+var_E8]; struct _tagpropertykey *
0x18001b438  mov     rcx, rsi; this
0x18001b43b  call    ?GetItem@CPhotoPropertyItemList@@QEAAJPEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z; CPhotoPropertyItemList::GetItem(_tagpropertykey const *,tagPROPVARIANT *)
0x18001b440  test    eax, eax
0x18001b442  js      short loc_18001B44C
0x18001b444  cmp     r13w, word ptr [rsp+130h+pvarDest]
0x18001b44a  jnz     short loc_18001B463
0x18001b44c  mov     rdx, rdi; struct tagPROPVARIANT *
0x18001b44f  lea     rcx, [rsp+130h+pvarDest]; struct tagPROPVARIANT *
0x18001b454  call    ?CreateDefaultProxyVariant@@YAJPEAUtagPROPVARIANT@@PEBU1@@Z; CreateDefaultProxyVariant(tagPROPVARIANT *,tagPROPVARIANT const *)
0x18001b459  mov     ebx, eax
0x18001b45b  test    eax, eax
0x18001b45d  js      loc_18001B597
0x18001b463  mov     r8, rdi
0x18001b466  cmp     rdi, r12
0x18001b469  cmovnz  r8, r13; struct tagPROPVARIANT *
0x18001b46d  cmp     rdi, r15
0x18001b470  cmovnz  rdi, r13
0x18001b474  mov     rdx, rdi; struct tagPROPVARIANT *
0x18001b477  lea     rcx, [rsp+130h+pvarDest]; struct tagPROPVARIANT *
0x18001b47c  call    ?UpdateRationalPropvar@@YAJPEAUtagPROPVARIANT@@PEBU1@1@Z; UpdateRationalPropvar(tagPROPVARIANT *,tagPROPVARIANT const *,tagPROPVARIANT const *)
0x18001b481  mov     ebx, eax
0x18001b483  test    eax, eax
0x18001b485  js      loc_18001B597
0x18001b48b  jmp     short loc_18001B491
0x18001b48d  lea     rsi, [r14+60h]
0x18001b491  mov     rcx, r14; this
0x18001b494  call    ?ReadInMetadata@CMetadataContainer@@QEAAJXZ; CMetadataContainer::ReadInMetadata(void)
0x18001b499  lea     rcx, [r14+78h]; this
0x18001b49d  lea     rdx, [rsp+130h+var_E8]; struct _tagpropertykey *
0x18001b4a2  call    ?_InternalDeleteItem@CPhotoPropertyItemList@@AEAAJPEBU_tagpropertykey@@@Z; CPhotoPropertyItemList::_InternalDeleteItem(_tagpropertykey const *)
0x18001b4a7  mov     ebx, eax
0x18001b4a9  test    eax, eax
0x18001b4ab  js      loc_18001B597
0x18001b4b1  mov     rcx, r14; this
0x18001b4b4  call    ?ReadInMetadata@CMetadataContainer@@QEAAJXZ; CMetadataContainer::ReadInMetadata(void)
0x18001b4b9  mov     byte ptr [rsp+130h+var_110], 1; bool
0x18001b4be  mov     r9b, 1; bool
0x18001b4c1  lea     r8, [rsp+130h+pvarDest]; struct tagPROPVARIANT *
0x18001b4c6  lea     rdx, [rsp+130h+var_E8]; struct _tagpropertykey *
0x18001b4cb  mov     rcx, rsi; this
0x18001b4ce  call    ?_InternalUpdateOrAddItem@CPhotoPropertyItemList@@AEAAJPEBU_tagpropertykey@@PEBUtagPROPVARIANT@@_N2@Z; CPhotoPropertyItemList::_InternalUpdateOrAddItem(_tagpropertykey const *,tagPROPVARIANT const *,bool,bool)
0x18001b4d3  mov     ebx, eax
0x18001b4d5  test    eax, eax
0x18001b4d7  js      loc_18001B597
0x18001b4dd  cmp     word ptr [rbp+57h+var_58], r13w
0x18001b4e2  jz      short loc_18001B4EB
0x18001b4e4  cmp     word ptr [rbp+57h+var_70], r13w
0x18001b4e9  jnz     short loc_18001B507
0x18001b4eb  lea     r8, [rbp+57h+var_70]; struct tagPROPVARIANT *
0x18001b4ef  lea     rdx, [rbp+57h+var_58]; struct tagPROPVARIANT *
0x18001b4f3  lea     rcx, [rsp+130h+pvarDest]; struct tagPROPVARIANT *
0x18001b4f8  call    ?ConstructNumeratorAndDenominatorFromRationalPropvar@@YAJPEBUtagPROPVARIANT@@PEAU1@1@Z; ConstructNumeratorAndDenominatorFromRationalPropvar(tagPROPVARIANT const *,tagPROPVARIANT *,tagPROPVARIANT *)
0x18001b4fd  mov     ebx, eax
0x18001b4ff  test    eax, eax
0x18001b501  js      loc_18001B597
0x18001b507  mov     rcx, r14; this
0x18001b50a  call    ?ReadInMetadata@CMetadataContainer@@QEAAJXZ; CMetadataContainer::ReadInMetadata(void)
0x18001b50f  mov     byte ptr [rsp+130h+var_110], r13b; bool
0x18001b514  xor     r9d, r9d; bool
0x18001b517  lea     r8, [rbp+57h+var_58]; struct tagPROPVARIANT *
0x18001b51b  lea     rdx, [rbp+57h+var_D0]; struct _tagpropertykey *
0x18001b51f  mov     rcx, rsi; this
0x18001b522  call    ?_InternalUpdateOrAddItem@CPhotoPropertyItemList@@AEAAJPEBU_tagpropertykey@@PEBUtagPROPVARIANT@@_N2@Z; CPhotoPropertyItemList::_InternalUpdateOrAddItem(_tagpropertykey const *,tagPROPVARIANT const *,bool,bool)
0x18001b527  mov     ebx, eax
0x18001b529  test    eax, eax
0x18001b52b  js      short loc_18001B597
0x18001b52d  mov     rcx, r14; this
0x18001b530  call    ?ReadInMetadata@CMetadataContainer@@QEAAJXZ; CMetadataContainer::ReadInMetadata(void)
0x18001b535  mov     byte ptr [rsp+130h+var_110], r13b; bool
0x18001b53a  xor     r9d, r9d; bool
0x18001b53d  lea     r8, [rbp+57h+var_70]; struct tagPROPVARIANT *
0x18001b541  lea     rdx, [rbp+57h+var_B8]; struct _tagpropertykey *
0x18001b545  mov     rcx, rsi; this
0x18001b548  call    ?_InternalUpdateOrAddItem@CPhotoPropertyItemList@@AEAAJPEBU_tagpropertykey@@PEBUtagPROPVARIANT@@_N2@Z; CPhotoPropertyItemList::_InternalUpdateOrAddItem(_tagpropertykey const *,tagPROPVARIANT const *,bool,bool)
0x18001b54d  mov     ebx, eax
0x18001b54f  test    eax, eax
0x18001b551  js      short loc_18001B597
0x18001b553  cmp     word ptr [rbp+57h+pvar], r13w
0x18001b558  jnz     short loc_18001B56E
0x18001b55a  lea     rdx, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x18001b55e  lea     rcx, [rsp+130h+pvarDest]; struct tagPROPVARIANT *
0x18001b563  call    ?ConstructR8FromRationalPropvar@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; ConstructR8FromRationalPropvar(tagPROPVARIANT const *,tagPROPVARIANT *)
0x18001b568  mov     ebx, eax
0x18001b56a  test    eax, eax
0x18001b56c  js      short loc_18001B597
0x18001b56e  mov     rcx, r14; this
0x18001b571  call    ?ReadInMetadata@CMetadataContainer@@QEAAJXZ; CMetadataContainer::ReadInMetadata(void)
0x18001b576  mov     byte ptr [rsp+130h+var_110], r13b; bool
0x18001b57b  xor     r9d, r9d; bool
0x18001b57e  lea     r8, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x18001b582  lea     rdx, [rbp+57h+var_A0]; struct _tagpropertykey *
0x18001b586  mov     rcx, rsi; this
0x18001b589  call    ?_InternalUpdateOrAddItem@CPhotoPropertyItemList@@AEAAJPEBU_tagpropertykey@@PEBUtagPROPVARIANT@@_N2@Z; CPhotoPropertyItemList::_InternalUpdateOrAddItem(_tagpropertykey const *,tagPROPVARIANT const *,bool,bool)
0x18001b58e  mov     ebx, eax
0x18001b590  jmp     short loc_18001B597
0x18001b592  mov     ebx, 80070005h
0x18001b597  lea     rcx, [rbp+57h+pvar]; pvar
0x18001b59b  call    cs:__imp_PropVariantClear
0x18001b5a1  nop
0x18001b5a2  lea     rcx, [rbp+57h+var_70]; pvar
0x18001b5a6  call    cs:__imp_PropVariantClear
0x18001b5ac  nop
0x18001b5ad  lea     rcx, [rbp+57h+var_58]; pvar
0x18001b5b1  call    cs:__imp_PropVariantClear
0x18001b5b7  nop
0x18001b5b8  lea     rcx, [rsp+130h+pvarDest]; pvar
0x18001b5bd  call    cs:__imp_PropVariantClear
0x18001b5c3  mov     eax, ebx
0x18001b5c5  add     rsp, 0F8h
0x18001b5cc  pop     r15
0x18001b5ce  pop     r14
0x18001b5d0  pop     r13
0x18001b5d2  pop     r12
0x18001b5d4  pop     rdi
0x18001b5d5  pop     rsi
0x18001b5d6  pop     rbx
0x18001b5d7  pop     rbp
0x18001b5d8  retn
```
