# CMetadataContainer::_WriteOutKey(IWICMetadataQueryWriter *,_tagpropertykey const *,tagPROPVARIANT const *)

- ea: `0x180014ba4`
- end: `0x180014f47`
- name: `?_WriteOutKey@CMetadataContainer@@AEAAJPEAUIWICMetadataQueryWriter@@PEBU_tagpropertykey@@PEBUtagPROPVARIANT@@@Z`
- size: `931`
- prototype: `int(CMetadataContainer *__hidden this, struct IWICMetadataQueryWriter *, const struct _tagpropertykey *, const struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001c380`

## callees

- `0x18000a160`
- `0x18000e230`
- `0x1800139ec`
- `0x180014ba4`
- `0x18001a5b8`
- `0x18001a868`
- `0x18001aaf8`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014d19`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014daf`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014ef2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014efd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014d19`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014daf`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014ef2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014efd`

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
  HRESULT v11; // eax
  HRESULT Item; // ebx
  HRESULT v13; // eax
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
0x180014ba4  push    rbp
0x180014ba6  push    rbx
0x180014ba7  push    rsi
0x180014ba8  push    rdi
0x180014ba9  push    r12
0x180014bab  push    r14
0x180014bad  push    r15
0x180014baf  mov     rbp, rsp
0x180014bb2  sub     rsp, 60h
0x180014bb6  mov     r14, r9
0x180014bb9  mov     rbx, r8
0x180014bbc  mov     rdi, rdx
0x180014bbf  mov     r15, rcx
0x180014bc2  xor     r12d, r12d
0x180014bc5  mov     [rbp+var_40], r12
0x180014bc9  lea     r8, [rbp+var_40]; struct CAPABILITIES_LIST_ENTRY **
0x180014bcd  mov     rdx, rbx; struct _tagpropertykey *
0x180014bd0  call    ?SearchForKey@CMetadataContainer@@QEAAJPEBU_tagpropertykey@@PEAPEBUCAPABILITIES_LIST_ENTRY@@@Z; CMetadataContainer::SearchForKey(_tagpropertykey const *,CAPABILITIES_LIST_ENTRY const * *)
0x180014bd5  test    eax, eax
0x180014bd7  js      loc_180014F31
0x180014bdd  mov     eax, [rbx+10h]
0x180014be0  cmp     [r14], r12w
0x180014be4  jnz     loc_180014C9D
0x180014bea  cmp     eax, 9
0x180014bed  jnz     short loc_180014C0B
0x180014bef  mov     rcx, [rbx]
0x180014bf2  sub     rcx, qword ptr cs:PKEY_Rating.fmtid.Data1
0x180014bf9  jnz     short loc_180014C06
0x180014bfb  mov     rcx, [rbx+8]
0x180014bff  sub     rcx, qword ptr cs:PKEY_Rating.fmtid.Data4
0x180014c06  test    rcx, rcx
0x180014c09  jz      short loc_180014C2C
0x180014c0b  cmp     eax, 64h ; 'd'
0x180014c0e  jnz     short loc_180014C7F
0x180014c10  mov     rax, [rbx]
0x180014c13  sub     rax, qword ptr cs:PKEY_SimpleRating.fmtid.Data1
0x180014c1a  jnz     short loc_180014C27
0x180014c1c  mov     rax, [rbx+8]
0x180014c20  sub     rax, qword ptr cs:PKEY_SimpleRating.fmtid.Data4
0x180014c27  test    rax, rax
0x180014c2a  jnz     short loc_180014C7F
0x180014c2c  mov     rax, [rdi]
0x180014c2f  lea     rdx, aSystemRating; "System.Rating"
0x180014c36  mov     rcx, rdi
0x180014c39  mov     rax, [rax+40h]
0x180014c3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c42  mov     ebx, r12d
0x180014c45  mov     esi, 88982F40h
0x180014c4a  cmp     eax, esi
0x180014c4c  cmovnz  ebx, eax
0x180014c4f  test    ebx, ebx
0x180014c51  js      loc_180014F36
0x180014c57  mov     rax, [rdi]
0x180014c5a  lea     rdx, aSystemSimplera; "System.SimpleRating"
0x180014c61  mov     rcx, rdi
0x180014c64  mov     rax, [rax+40h]
0x180014c68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c6d  mov     ebx, eax
0x180014c6f  cmp     eax, esi
0x180014c71  jnz     loc_180014F36
0x180014c77  mov     ebx, r12d
0x180014c7a  jmp     loc_180014F36
0x180014c7f  mov     rax, [rdi]
0x180014c82  mov     rdx, [rbp+var_40]
0x180014c86  mov     rdx, [rdx+40h]
0x180014c8a  mov     rcx, rdi
0x180014c8d  mov     rax, [rax+40h]
0x180014c91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c96  mov     esi, 88982F40h
0x180014c9b  jmp     short loc_180014C6D
0x180014c9d  cmp     eax, 9
0x180014ca0  jnz     loc_180014D33
0x180014ca6  mov     rax, [rbx]
0x180014ca9  sub     rax, qword ptr cs:PKEY_Rating.fmtid.Data1
0x180014cb0  jnz     short loc_180014CBD
0x180014cb2  mov     rax, [rbx+8]
0x180014cb6  sub     rax, qword ptr cs:PKEY_Rating.fmtid.Data4
0x180014cbd  test    rax, rax
0x180014cc0  jnz     loc_180014F0C
0x180014cc6  lea     rcx, [r15+60h]; this
0x180014cca  lea     rdx, PKEY_SimpleRating; struct _tagpropertykey *
0x180014cd1  call    ?IsItemDirty@CPhotoPropertyItemList@@QEAA_NPEBU_tagpropertykey@@@Z; CPhotoPropertyItemList::IsItemDirty(_tagpropertykey const *)
0x180014cd6  test    al, al
0x180014cd8  jnz     short loc_180014D27
0x180014cda  xorps   xmm0, xmm0
0x180014cdd  xor     eax, eax
0x180014cdf  movups  xmmword ptr [rbp+pvar], xmm0
0x180014ce3  mov     qword ptr [rbp+pvar+10h], rax
0x180014ce7  lea     rdx, [rbp+pvar]; struct tagPROPVARIANT *
0x180014ceb  mov     rcx, r14; this
0x180014cee  call    ?ConvertRatingToSimpleRating@CodecUtil@@YAJPEBUtagPROPVARIANT@@PEAU2@@Z; CodecUtil::ConvertRatingToSimpleRating(tagPROPVARIANT const *,tagPROPVARIANT *)
0x180014cf3  mov     ebx, eax
0x180014cf5  test    eax, eax
0x180014cf7  js      short loc_180014D15
0x180014cf9  mov     rax, [rdi]
0x180014cfc  lea     r8, [rbp+pvar]
0x180014d00  lea     rdx, aSystemSimplera; "System.SimpleRating"
0x180014d07  mov     rcx, rdi
0x180014d0a  mov     rax, [rax+38h]
0x180014d0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d13  mov     ebx, eax
0x180014d15  lea     rcx, [rbp+pvar]; pvar
0x180014d19  call    cs:__imp_PropVariantClear
0x180014d1f  test    ebx, ebx
0x180014d21  js      loc_180014F36
0x180014d27  lea     rdx, aSystemRating; "System.Rating"
0x180014d2e  jmp     loc_180014F14
0x180014d33  cmp     eax, 64h ; 'd'
0x180014d36  jnz     loc_180014DC9
0x180014d3c  mov     rax, [rbx]
0x180014d3f  sub     rax, qword ptr cs:PKEY_SimpleRating.fmtid.Data1
0x180014d46  jnz     short loc_180014D53
0x180014d48  mov     rax, [rbx+8]
0x180014d4c  sub     rax, qword ptr cs:PKEY_SimpleRating.fmtid.Data4
0x180014d53  test    rax, rax
0x180014d56  jnz     loc_180014F0C
0x180014d5c  lea     rcx, [r15+60h]; this
0x180014d60  lea     rdx, PKEY_Rating; struct _tagpropertykey *
0x180014d67  call    ?IsItemDirty@CPhotoPropertyItemList@@QEAA_NPEBU_tagpropertykey@@@Z; CPhotoPropertyItemList::IsItemDirty(_tagpropertykey const *)
0x180014d6c  test    al, al
0x180014d6e  jnz     short loc_180014DBD
0x180014d70  xorps   xmm0, xmm0
0x180014d73  xor     eax, eax
0x180014d75  movups  xmmword ptr [rbp+pvar], xmm0
0x180014d79  mov     qword ptr [rbp+pvar+10h], rax
0x180014d7d  lea     rdx, [rbp+pvar]; struct tagPROPVARIANT *
0x180014d81  mov     rcx, r14; this
0x180014d84  call    ?ConvertSimpleRatingToRating@CodecUtil@@YAJPEBUtagPROPVARIANT@@PEAU2@@Z; CodecUtil::ConvertSimpleRatingToRating(tagPROPVARIANT const *,tagPROPVARIANT *)
0x180014d89  mov     ebx, eax
0x180014d8b  test    eax, eax
0x180014d8d  js      short loc_180014DAB
0x180014d8f  mov     rax, [rdi]
0x180014d92  lea     r8, [rbp+pvar]
0x180014d96  lea     rdx, aSystemRating; "System.Rating"
0x180014d9d  mov     rcx, rdi
0x180014da0  mov     rax, [rax+38h]
0x180014da4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014da9  mov     ebx, eax
0x180014dab  lea     rcx, [rbp+pvar]; pvar
0x180014daf  call    cs:__imp_PropVariantClear
0x180014db5  test    ebx, ebx
0x180014db7  js      loc_180014F36
0x180014dbd  lea     rdx, aSystemSimplera; "System.SimpleRating"
0x180014dc4  jmp     loc_180014F14
0x180014dc9  cmp     eax, 16h
0x180014dcc  jnz     short loc_180014DFA
0x180014dce  mov     rax, [rbx]
0x180014dd1  sub     rax, cs:PKEY_GPS_Latitude_Proxy
0x180014dd8  jnz     short loc_180014DE5
0x180014dda  mov     rax, [rbx+8]
0x180014dde  sub     rax, cs:qword_18008C728
0x180014de5  test    rax, rax
0x180014de8  jnz     loc_180014F0C
0x180014dee  lea     rsi, PKEY_GPS_LatitudeRef
0x180014df5  jmp     loc_180014E86
0x180014dfa  cmp     eax, 17h
0x180014dfd  jnz     short loc_180014E28
0x180014dff  mov     rax, [rbx]
0x180014e02  sub     rax, cs:PKEY_GPS_Longitude_Proxy
0x180014e09  jnz     short loc_180014E16
0x180014e0b  mov     rax, [rbx+8]
0x180014e0f  sub     rax, cs:qword_18008C6F8
0x180014e16  test    rax, rax
0x180014e19  jnz     loc_180014F0C
0x180014e1f  lea     rsi, PKEY_GPS_LongitudeRef
0x180014e26  jmp     short loc_180014E86
0x180014e28  cmp     eax, 12h
0x180014e2b  jnz     short loc_180014E56
0x180014e2d  mov     rax, [rbx]
0x180014e30  sub     rax, cs:PKEY_GPS_DestLatitude_Proxy
0x180014e37  jnz     short loc_180014E44
0x180014e39  mov     rax, [rbx+8]
0x180014e3d  sub     rax, cs:qword_18008C710
0x180014e44  test    rax, rax
0x180014e47  jnz     loc_180014F0C
0x180014e4d  lea     rsi, PKEY_GPS_DestLatitudeRef
0x180014e54  jmp     short loc_180014E86
0x180014e56  cmp     eax, 13h
0x180014e59  jnz     loc_180014F0C
0x180014e5f  mov     rax, [rbx]
0x180014e62  sub     rax, cs:PKEY_GPS_DestLongitude_Proxy
0x180014e69  jnz     short loc_180014E76
0x180014e6b  mov     rax, [rbx+8]
0x180014e6f  sub     rax, cs:qword_18008C6E0
0x180014e76  test    rax, rax
0x180014e79  jnz     loc_180014F0C
0x180014e7f  lea     rsi, PKEY_GPS_DestLongitudeRef
0x180014e86  cmp     dword ptr [r14+8], 3
0x180014e8b  jnz     short loc_180014F05
0x180014e8d  xorps   xmm0, xmm0
0x180014e90  xor     eax, eax
0x180014e92  movups  xmmword ptr [rbp+var_20], xmm0
0x180014e96  mov     qword ptr [rbp+var_20+10h], rax
0x180014e9a  movups  xmmword ptr [rbp+pvar], xmm0
0x180014e9e  mov     qword ptr [rbp+pvar+10h], rax
0x180014ea2  lea     rcx, [r15+60h]; this
0x180014ea6  lea     r8, [rbp+var_20]; struct tagPROPVARIANT *
0x180014eaa  mov     rdx, rsi; struct _tagpropertykey *
0x180014ead  call    ?GetItem@CPhotoPropertyItemList@@QEAAJPEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z; CPhotoPropertyItemList::GetItem(_tagpropertykey const *,tagPROPVARIANT *)
0x180014eb2  mov     ebx, eax
0x180014eb4  test    eax, eax
0x180014eb6  js      short loc_180014EEE
0x180014eb8  lea     r9, [rbp+pvar]; struct tagPROPVARIANT *
0x180014ebc  mov     r8, r14; struct tagPROPVARIANT *
0x180014ebf  lea     rdx, [rbp+var_20]; struct tagPROPVARIANT *
0x180014ec3  mov     rcx, rsi; struct _tagpropertykey *
0x180014ec6  call    ?ConstructGPSCoordProxyWithRef@@YAJAEBU_tagpropertykey@@PEBUtagPROPVARIANT@@1PEAU2@@Z; ConstructGPSCoordProxyWithRef(_tagpropertykey const &,tagPROPVARIANT const *,tagPROPVARIANT const *,tagPROPVARIANT *)
0x180014ecb  mov     ebx, eax
0x180014ecd  test    eax, eax
0x180014ecf  js      short loc_180014EEE
0x180014ed1  mov     rax, [rdi]
0x180014ed4  lea     r8, [rbp+pvar]
0x180014ed8  mov     rdx, [rbp+var_40]
0x180014edc  mov     rdx, [rdx+40h]
0x180014ee0  mov     rcx, rdi
0x180014ee3  mov     rax, [rax+38h]
0x180014ee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014eec  mov     ebx, eax
0x180014eee  lea     rcx, [rbp+pvar]; pvar
0x180014ef2  call    cs:__imp_PropVariantClear
0x180014ef8  nop
0x180014ef9  lea     rcx, [rbp+var_20]; pvar
0x180014efd  call    cs:__imp_PropVariantClear
0x180014f03  jmp     short loc_180014F36
0x180014f05  cmp     dword ptr [r14+8], 4
0x180014f0a  jnz     short loc_180014F2A
0x180014f0c  mov     rdx, [rbp+var_40]
0x180014f10  mov     rdx, [rdx+40h]
0x180014f14  mov     rax, [rdi]
0x180014f17  mov     r8, r14
0x180014f1a  mov     rcx, rdi
0x180014f1d  mov     rax, [rax+38h]
0x180014f21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f26  mov     ebx, eax
0x180014f28  jmp     short loc_180014F36
0x180014f2a  mov     ebx, 80070057h
0x180014f2f  jmp     short loc_180014F36
0x180014f31  mov     ebx, 88982F41h
0x180014f36  mov     eax, ebx
0x180014f38  add     rsp, 60h
0x180014f3c  pop     r15
0x180014f3e  pop     r14
0x180014f40  pop     r12
0x180014f42  pop     rdi
0x180014f43  pop     rsi
0x180014f44  pop     rbx
0x180014f45  pop     rbp
0x180014f46  retn
```
