# CMetadataContainer::_WriteOutKey(IWICMetadataQueryWriter *,_tagpropertykey const *,tagPROPVARIANT const *)

- ea: `0x180015594`
- end: `0x180015954`
- name: `?_WriteOutKey@CMetadataContainer@@AEAAJPEAUIWICMetadataQueryWriter@@PEBU_tagpropertykey@@PEBUtagPROPVARIANT@@@Z`
- size: `960`
- prototype: `int(CMetadataContainer *__hidden this, struct IWICMetadataQueryWriter *, const struct _tagpropertykey *, const struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001d094`

## callees

- `0x18000a720`
- `0x18000e8f0`
- `0x180014390`
- `0x180015594`
- `0x18001b248`
- `0x18001b508`
- `0x18001b7a4`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180015709`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800157a5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800158f2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180015903`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180015709`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800157a5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800158f2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180015903`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMetadataContainer::_WriteOutKey(
        CMetadataContainer *this,
        struct IWICMetadataQueryWriter *a2,
        const struct _tagpropertykey *a3,
        struct tagPROPVARIANT *a4)
{
  DWORD pid; // eax
  __int64 v9; // rcx
  __int64 v10; // rax
  int v11; // eax
  int Item; // ebx
  int v13; // eax
  __int64 v14; // rax
  struct tagPROPVARIANT *v15; // r8
  const wchar_t *v16; // rdx
  __int64 v17; // rax
  struct tagPROPVARIANT *v18; // r8
  __int64 v19; // rax
  const PROPERTYKEY *v20; // rsi
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  struct CAPABILITIES_LIST_ENTRY *v25; // [rsp+20h] [rbp-40h] BYREF
  PROPVARIANT pvar; // [rsp+28h] [rbp-38h] BYREF
  PROPVARIANT v27; // [rsp+40h] [rbp-20h] BYREF

  v25 = 0;
  if ( CMetadataContainer::SearchForKey(this, a3, &v25) < 0 )
    return (unsigned int)-2003292351;
  pid = a3->pid;
  if ( a4->vt )
  {
    if ( pid == 9 )
    {
      v14 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_Rating.fmtid.Data1;
      if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_Rating.fmtid.Data1 )
        v14 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_Rating.fmtid.Data4;
      if ( !v14 )
      {
        if ( !CPhotoPropertyItemList::IsItemDirty((CMetadataContainer *)((char *)this + 96), &PKEY_SimpleRating) )
        {
          memset(&pvar, 0, sizeof(pvar));
          Item = CodecUtil::ConvertRatingToSimpleRating((CodecUtil *)a4, &pvar, v15);
          if ( Item >= 0 )
            Item = ((__int64 (__fastcall *)(struct IWICMetadataQueryWriter *, const wchar_t *, PROPVARIANT *))a2->lpVtbl->SetMetadataByName)(
                     a2,
                     L"System.SimpleRating",
                     &pvar);
          PropVariantClear(&pvar);
          if ( Item < 0 )
            return (unsigned int)Item;
        }
        v16 = L"System.Rating";
        return ((unsigned int (__fastcall *)(struct IWICMetadataQueryWriter *, const wchar_t *, struct tagPROPVARIANT *))a2->lpVtbl->SetMetadataByName)(
                 a2,
                 v16,
                 a4);
      }
    }
    else
    {
      if ( pid != 100 )
      {
        switch ( pid )
        {
          case 0x16u:
            v19 = *(_QWORD *)&a3->fmtid.Data1 - PKEY_GPS_Latitude_Proxy;
            if ( *(_QWORD *)&a3->fmtid.Data1 == PKEY_GPS_Latitude_Proxy )
              v19 = *(_QWORD *)a3->fmtid.Data4 - 0x48E05453247376ABLL;
            if ( v19 )
              goto LABEL_62;
            v20 = &PKEY_GPS_LatitudeRef;
            break;
          case 0x17u:
            v21 = *(_QWORD *)&a3->fmtid.Data1 - PKEY_GPS_Longitude_Proxy;
            if ( *(_QWORD *)&a3->fmtid.Data1 == PKEY_GPS_Longitude_Proxy )
              v21 = *(_QWORD *)a3->fmtid.Data4 - 0x48E05453247376ABLL;
            if ( v21 )
              goto LABEL_62;
            v20 = &PKEY_GPS_LongitudeRef;
            break;
          case 0x12u:
            v22 = *(_QWORD *)&a3->fmtid.Data1 - PKEY_GPS_DestLatitude_Proxy;
            if ( *(_QWORD *)&a3->fmtid.Data1 == PKEY_GPS_DestLatitude_Proxy )
              v22 = *(_QWORD *)a3->fmtid.Data4 - 0x48E05453247376ABLL;
            if ( v22 )
              goto LABEL_62;
            v20 = &PKEY_GPS_DestLatitudeRef;
            break;
          case 0x13u:
            v23 = *(_QWORD *)&a3->fmtid.Data1 - PKEY_GPS_DestLongitude_Proxy;
            if ( *(_QWORD *)&a3->fmtid.Data1 == PKEY_GPS_DestLongitude_Proxy )
              v23 = *(_QWORD *)a3->fmtid.Data4 - 0x48E05453247376ABLL;
            if ( v23 )
              goto LABEL_62;
            v20 = &PKEY_GPS_DestLongitudeRef;
            break;
          default:
            goto LABEL_62;
        }
        if ( a4->lVal == 3 )
        {
          memset(&v27, 0, sizeof(v27));
          memset(&pvar, 0, sizeof(pvar));
          Item = CPhotoPropertyItemList::GetItem((CMetadataContainer *)((char *)this + 96), v20, &v27);
          if ( Item >= 0 )
          {
            Item = ConstructGPSCoordProxyWithRef(v20, &v27, a4, &pvar);
            if ( Item >= 0 )
              Item = ((__int64 (__fastcall *)(struct IWICMetadataQueryWriter *, _QWORD, PROPVARIANT *))a2->lpVtbl->SetMetadataByName)(
                       a2,
                       *((_QWORD *)v25 + 8),
                       &pvar);
          }
          PropVariantClear(&pvar);
          PropVariantClear(&v27);
          return (unsigned int)Item;
        }
        if ( a4->lVal != 4 )
          return (unsigned int)-2147024809;
        goto LABEL_62;
      }
      v17 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_SimpleRating.fmtid.Data1;
      if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_SimpleRating.fmtid.Data1 )
        v17 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_SimpleRating.fmtid.Data4;
      if ( !v17 )
      {
        if ( !CPhotoPropertyItemList::IsItemDirty((CMetadataContainer *)((char *)this + 96), &PKEY_Rating) )
        {
          memset(&pvar, 0, sizeof(pvar));
          Item = CodecUtil::ConvertSimpleRatingToRating((CodecUtil *)a4, &pvar, v18);
          if ( Item >= 0 )
            Item = ((__int64 (__fastcall *)(struct IWICMetadataQueryWriter *, const wchar_t *, PROPVARIANT *))a2->lpVtbl->SetMetadataByName)(
                     a2,
                     L"System.Rating",
                     &pvar);
          PropVariantClear(&pvar);
          if ( Item < 0 )
            return (unsigned int)Item;
        }
        v16 = L"System.SimpleRating";
        return ((unsigned int (__fastcall *)(struct IWICMetadataQueryWriter *, const wchar_t *, struct tagPROPVARIANT *))a2->lpVtbl->SetMetadataByName)(
                 a2,
                 v16,
                 a4);
      }
    }
LABEL_62:
    v16 = (const wchar_t *)*((_QWORD *)v25 + 8);
    return ((unsigned int (__fastcall *)(_QWORD, _QWORD, _QWORD))a2->lpVtbl->SetMetadataByName)(a2, v16, a4);
  }
  if ( pid != 9 )
    goto LABEL_10;
  v9 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_Rating.fmtid.Data1;
  if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_Rating.fmtid.Data1 )
    v9 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_Rating.fmtid.Data4;
  if ( v9 )
  {
LABEL_10:
    if ( pid != 100 )
      goto LABEL_17;
    v10 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_SimpleRating.fmtid.Data1;
    if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_SimpleRating.fmtid.Data1 )
      v10 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_SimpleRating.fmtid.Data4;
    if ( v10 )
    {
LABEL_17:
      v13 = ((__int64 (__fastcall *)(struct IWICMetadataQueryWriter *, _QWORD))a2->lpVtbl->RemoveMetadataByName)(
              a2,
              *((_QWORD *)v25 + 8));
LABEL_15:
      Item = v13;
      if ( v13 == -2003292352 )
        return 0;
      return (unsigned int)Item;
    }
  }
  v11 = ((__int64 (__fastcall *)(struct IWICMetadataQueryWriter *, const wchar_t *))a2->lpVtbl->RemoveMetadataByName)(
          a2,
          L"System.Rating");
  Item = 0;
  if ( v11 != -2003292352 )
    Item = v11;
  if ( Item >= 0 )
  {
    v13 = ((__int64 (__fastcall *)(struct IWICMetadataQueryWriter *, const wchar_t *))a2->lpVtbl->RemoveMetadataByName)(
            a2,
            L"System.SimpleRating");
    goto LABEL_15;
  }
  return (unsigned int)Item;
}

```

## disassembly

```asm
0x180015594  push    rbp
0x180015596  push    rbx
0x180015597  push    rsi
0x180015598  push    rdi
0x180015599  push    r12
0x18001559b  push    r14
0x18001559d  push    r15
0x18001559f  mov     rbp, rsp
0x1800155a2  sub     rsp, 60h
0x1800155a6  mov     r14, r9
0x1800155a9  mov     rbx, r8
0x1800155ac  mov     rdi, rdx
0x1800155af  mov     r15, rcx
0x1800155b2  xor     r12d, r12d
0x1800155b5  mov     [rbp+var_40], r12
0x1800155b9  lea     r8, [rbp+var_40]; struct CAPABILITIES_LIST_ENTRY **
0x1800155bd  mov     rdx, rbx; struct _tagpropertykey *
0x1800155c0  call    ?SearchForKey@CMetadataContainer@@QEAAJPEBU_tagpropertykey@@PEAPEBUCAPABILITIES_LIST_ENTRY@@@Z; CMetadataContainer::SearchForKey(_tagpropertykey const *,CAPABILITIES_LIST_ENTRY const * *)
0x1800155c5  test    eax, eax
0x1800155c7  js      loc_18001593D
0x1800155cd  mov     eax, [rbx+10h]
0x1800155d0  cmp     [r14], r12w
0x1800155d4  jnz     loc_18001568D
0x1800155da  cmp     eax, 9
0x1800155dd  jnz     short loc_1800155FB
0x1800155df  mov     rcx, [rbx]
0x1800155e2  sub     rcx, qword ptr cs:PKEY_Rating.fmtid.Data1
0x1800155e9  jnz     short loc_1800155F6
0x1800155eb  mov     rcx, [rbx+8]
0x1800155ef  sub     rcx, qword ptr cs:PKEY_Rating.fmtid.Data4
0x1800155f6  test    rcx, rcx
0x1800155f9  jz      short loc_18001561C
0x1800155fb  cmp     eax, 64h ; 'd'
0x1800155fe  jnz     short loc_18001566F
0x180015600  mov     rax, [rbx]
0x180015603  sub     rax, qword ptr cs:PKEY_SimpleRating.fmtid.Data1
0x18001560a  jnz     short loc_180015617
0x18001560c  mov     rax, [rbx+8]
0x180015610  sub     rax, qword ptr cs:PKEY_SimpleRating.fmtid.Data4
0x180015617  test    rax, rax
0x18001561a  jnz     short loc_18001566F
0x18001561c  mov     rax, [rdi]
0x18001561f  lea     rdx, aSystemRating; "System.Rating"
0x180015626  mov     rcx, rdi
0x180015629  mov     rax, [rax+40h]
0x18001562d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015632  mov     ebx, r12d
0x180015635  mov     esi, 88982F40h
0x18001563a  cmp     eax, esi
0x18001563c  cmovnz  ebx, eax
0x18001563f  test    ebx, ebx
0x180015641  js      loc_180015942
0x180015647  mov     rax, [rdi]
0x18001564a  lea     rdx, aSystemSimplera; "System.SimpleRating"
0x180015651  mov     rcx, rdi
0x180015654  mov     rax, [rax+40h]
0x180015658  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001565d  mov     ebx, eax
0x18001565f  cmp     eax, esi
0x180015661  jnz     loc_180015942
0x180015667  mov     ebx, r12d
0x18001566a  jmp     loc_180015942
0x18001566f  mov     rax, [rdi]
0x180015672  mov     rdx, [rbp+var_40]
0x180015676  mov     rdx, [rdx+40h]
0x18001567a  mov     rcx, rdi
0x18001567d  mov     rax, [rax+40h]
0x180015681  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015686  mov     esi, 88982F40h
0x18001568b  jmp     short loc_18001565D
0x18001568d  cmp     eax, 9
0x180015690  jnz     loc_180015729
0x180015696  mov     rax, [rbx]
0x180015699  sub     rax, qword ptr cs:PKEY_Rating.fmtid.Data1
0x1800156a0  jnz     short loc_1800156AD
0x1800156a2  mov     rax, [rbx+8]
0x1800156a6  sub     rax, qword ptr cs:PKEY_Rating.fmtid.Data4
0x1800156ad  test    rax, rax
0x1800156b0  jnz     loc_180015918
0x1800156b6  lea     rcx, [r15+60h]; this
0x1800156ba  lea     rdx, PKEY_SimpleRating; struct _tagpropertykey *
0x1800156c1  call    ?IsItemDirty@CPhotoPropertyItemList@@QEAA_NPEBU_tagpropertykey@@@Z; CPhotoPropertyItemList::IsItemDirty(_tagpropertykey const *)
0x1800156c6  test    al, al
0x1800156c8  jnz     short loc_18001571D
0x1800156ca  xorps   xmm0, xmm0
0x1800156cd  xor     eax, eax
0x1800156cf  movups  xmmword ptr [rbp+pvar], xmm0
0x1800156d3  mov     qword ptr [rbp+pvar+10h], rax
0x1800156d7  lea     rdx, [rbp+pvar]; struct tagPROPVARIANT *
0x1800156db  mov     rcx, r14; this
0x1800156de  call    ?ConvertRatingToSimpleRating@CodecUtil@@YAJPEBUtagPROPVARIANT@@PEAU2@@Z; CodecUtil::ConvertRatingToSimpleRating(tagPROPVARIANT const *,tagPROPVARIANT *)
0x1800156e3  mov     ebx, eax
0x1800156e5  test    eax, eax
0x1800156e7  js      short loc_180015705
0x1800156e9  mov     rax, [rdi]
0x1800156ec  lea     r8, [rbp+pvar]
0x1800156f0  lea     rdx, aSystemSimplera; "System.SimpleRating"
0x1800156f7  mov     rcx, rdi
0x1800156fa  mov     rax, [rax+38h]
0x1800156fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015703  mov     ebx, eax
0x180015705  lea     rcx, [rbp+pvar]; pvar
0x180015709  call    cs:__imp_PropVariantClear
0x180015710  nop     dword ptr [rax+rax+00h]
0x180015715  test    ebx, ebx
0x180015717  js      loc_180015942
0x18001571d  lea     rdx, aSystemRating; "System.Rating"
0x180015724  jmp     loc_180015920
0x180015729  cmp     eax, 64h ; 'd'
0x18001572c  jnz     loc_1800157C5
0x180015732  mov     rax, [rbx]
0x180015735  sub     rax, qword ptr cs:PKEY_SimpleRating.fmtid.Data1
0x18001573c  jnz     short loc_180015749
0x18001573e  mov     rax, [rbx+8]
0x180015742  sub     rax, qword ptr cs:PKEY_SimpleRating.fmtid.Data4
0x180015749  test    rax, rax
0x18001574c  jnz     loc_180015918
0x180015752  lea     rcx, [r15+60h]; this
0x180015756  lea     rdx, PKEY_Rating; struct _tagpropertykey *
0x18001575d  call    ?IsItemDirty@CPhotoPropertyItemList@@QEAA_NPEBU_tagpropertykey@@@Z; CPhotoPropertyItemList::IsItemDirty(_tagpropertykey const *)
0x180015762  test    al, al
0x180015764  jnz     short loc_1800157B9
0x180015766  xorps   xmm0, xmm0
0x180015769  xor     eax, eax
0x18001576b  movups  xmmword ptr [rbp+pvar], xmm0
0x18001576f  mov     qword ptr [rbp+pvar+10h], rax
0x180015773  lea     rdx, [rbp+pvar]; struct tagPROPVARIANT *
0x180015777  mov     rcx, r14; this
0x18001577a  call    ?ConvertSimpleRatingToRating@CodecUtil@@YAJPEBUtagPROPVARIANT@@PEAU2@@Z; CodecUtil::ConvertSimpleRatingToRating(tagPROPVARIANT const *,tagPROPVARIANT *)
0x18001577f  mov     ebx, eax
0x180015781  test    eax, eax
0x180015783  js      short loc_1800157A1
0x180015785  mov     rax, [rdi]
0x180015788  lea     r8, [rbp+pvar]
0x18001578c  lea     rdx, aSystemRating; "System.Rating"
0x180015793  mov     rcx, rdi
0x180015796  mov     rax, [rax+38h]
0x18001579a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001579f  mov     ebx, eax
0x1800157a1  lea     rcx, [rbp+pvar]; pvar
0x1800157a5  call    cs:__imp_PropVariantClear
0x1800157ac  nop     dword ptr [rax+rax+00h]
0x1800157b1  test    ebx, ebx
0x1800157b3  js      loc_180015942
0x1800157b9  lea     rdx, aSystemSimplera; "System.SimpleRating"
0x1800157c0  jmp     loc_180015920
0x1800157c5  cmp     eax, 16h
0x1800157c8  jnz     short loc_1800157F6
0x1800157ca  mov     rax, [rbx]
0x1800157cd  sub     rax, cs:PKEY_GPS_Latitude_Proxy
0x1800157d4  jnz     short loc_1800157E1
0x1800157d6  mov     rax, [rbx+8]
0x1800157da  sub     rax, cs:qword_18008D6F8
0x1800157e1  test    rax, rax
0x1800157e4  jnz     loc_180015918
0x1800157ea  lea     rsi, PKEY_GPS_LatitudeRef
0x1800157f1  jmp     loc_180015882
0x1800157f6  cmp     eax, 17h
0x1800157f9  jnz     short loc_180015824
0x1800157fb  mov     rax, [rbx]
0x1800157fe  sub     rax, cs:PKEY_GPS_Longitude_Proxy
0x180015805  jnz     short loc_180015812
0x180015807  mov     rax, [rbx+8]
0x18001580b  sub     rax, cs:qword_18008D6C8
0x180015812  test    rax, rax
0x180015815  jnz     loc_180015918
0x18001581b  lea     rsi, PKEY_GPS_LongitudeRef
0x180015822  jmp     short loc_180015882
0x180015824  cmp     eax, 12h
0x180015827  jnz     short loc_180015852
0x180015829  mov     rax, [rbx]
0x18001582c  sub     rax, cs:PKEY_GPS_DestLatitude_Proxy
0x180015833  jnz     short loc_180015840
0x180015835  mov     rax, [rbx+8]
0x180015839  sub     rax, cs:qword_18008D6E0
0x180015840  test    rax, rax
0x180015843  jnz     loc_180015918
0x180015849  lea     rsi, PKEY_GPS_DestLatitudeRef
0x180015850  jmp     short loc_180015882
0x180015852  cmp     eax, 13h
0x180015855  jnz     loc_180015918
0x18001585b  mov     rax, [rbx]
0x18001585e  sub     rax, cs:PKEY_GPS_DestLongitude_Proxy
0x180015865  jnz     short loc_180015872
0x180015867  mov     rax, [rbx+8]
0x18001586b  sub     rax, cs:qword_18008D6B0
0x180015872  test    rax, rax
0x180015875  jnz     loc_180015918
0x18001587b  lea     rsi, PKEY_GPS_DestLongitudeRef
0x180015882  cmp     dword ptr [r14+8], 3
0x180015887  jnz     loc_180015911
0x18001588d  xorps   xmm0, xmm0
0x180015890  xor     eax, eax
0x180015892  movups  xmmword ptr [rbp+var_20], xmm0
0x180015896  mov     qword ptr [rbp+var_20+10h], rax
0x18001589a  movups  xmmword ptr [rbp+pvar], xmm0
0x18001589e  mov     qword ptr [rbp+pvar+10h], rax
0x1800158a2  lea     rcx, [r15+60h]; this
0x1800158a6  lea     r8, [rbp+var_20]; struct tagPROPVARIANT *
0x1800158aa  mov     rdx, rsi; struct _tagpropertykey *
0x1800158ad  call    ?GetItem@CPhotoPropertyItemList@@QEAAJPEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z; CPhotoPropertyItemList::GetItem(_tagpropertykey const *,tagPROPVARIANT *)
0x1800158b2  mov     ebx, eax
0x1800158b4  test    eax, eax
0x1800158b6  js      short loc_1800158EE
0x1800158b8  lea     r9, [rbp+pvar]; struct tagPROPVARIANT *
0x1800158bc  mov     r8, r14; struct tagPROPVARIANT *
0x1800158bf  lea     rdx, [rbp+var_20]; struct tagPROPVARIANT *
0x1800158c3  mov     rcx, rsi; struct _tagpropertykey *
0x1800158c6  call    ?ConstructGPSCoordProxyWithRef@@YAJAEBU_tagpropertykey@@PEBUtagPROPVARIANT@@1PEAU2@@Z; ConstructGPSCoordProxyWithRef(_tagpropertykey const &,tagPROPVARIANT const *,tagPROPVARIANT const *,tagPROPVARIANT *)
0x1800158cb  mov     ebx, eax
0x1800158cd  test    eax, eax
0x1800158cf  js      short loc_1800158EE
0x1800158d1  mov     rax, [rdi]
0x1800158d4  lea     r8, [rbp+pvar]
0x1800158d8  mov     rdx, [rbp+var_40]
0x1800158dc  mov     rdx, [rdx+40h]
0x1800158e0  mov     rcx, rdi
0x1800158e3  mov     rax, [rax+38h]
0x1800158e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158ec  mov     ebx, eax
0x1800158ee  lea     rcx, [rbp+pvar]; pvar
0x1800158f2  call    cs:__imp_PropVariantClear
0x1800158f9  nop     dword ptr [rax+rax+00h]
0x1800158fe  nop
0x1800158ff  lea     rcx, [rbp+var_20]; pvar
0x180015903  call    cs:__imp_PropVariantClear
0x18001590a  nop     dword ptr [rax+rax+00h]
0x18001590f  jmp     short loc_180015942
0x180015911  cmp     dword ptr [r14+8], 4
0x180015916  jnz     short loc_180015936
0x180015918  mov     rdx, [rbp+var_40]
0x18001591c  mov     rdx, [rdx+40h]
0x180015920  mov     rax, [rdi]
0x180015923  mov     r8, r14
0x180015926  mov     rcx, rdi
0x180015929  mov     rax, [rax+38h]
0x18001592d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015932  mov     ebx, eax
0x180015934  jmp     short loc_180015942
0x180015936  mov     ebx, 80070057h
0x18001593b  jmp     short loc_180015942
0x18001593d  mov     ebx, 88982F41h
0x180015942  mov     eax, ebx
0x180015944  add     rsp, 60h
0x180015948  pop     r15
0x18001594a  pop     r14
0x18001594c  pop     r12
0x18001594e  pop     rdi
0x18001594f  pop     rsi
0x180015950  pop     rbx
0x180015951  pop     rbp
0x180015952  retn
```
