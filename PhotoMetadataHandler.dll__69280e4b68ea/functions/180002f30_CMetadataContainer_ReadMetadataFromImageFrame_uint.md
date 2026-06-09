# CMetadataContainer::_ReadMetadataFromImageFrame(uint)

- ea: `0x180002f30`
- end: `0x1800038f5`
- name: `?_ReadMetadataFromImageFrame@CMetadataContainer@@AEAAJI@Z`
- size: `2501`
- prototype: `__int64 __fastcall(struct _GUID *this)`
- caller_count: `3`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800025e0`
- `0x180002c50`
- `0x1800044e0`

## callees

- `0x180002f30`
- `0x180003900`
- `0x180004540`
- `0x180004e20`
- `0x180004fc0`
- `0x180005024`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800032cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800032cc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800030ac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003391`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003480`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800034e7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800035b6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003621`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800030ac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003391`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003480`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800034e7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800035b6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003621`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800030dd`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800033e8`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800038c0`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800030dd`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800033e8`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800038c0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180002fdd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000303b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800031b0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000329f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000341a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800038ab`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180002fdd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000303b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800031b0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000329f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000341a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800038ab`

## pseudocode

```c
__int64 __fastcall CMetadataContainer::_ReadMetadataFromImageFrame(struct _GUID *this)
{
  struct _GUID *v1; // r13
  int v2; // ebx
  unsigned int v3; // eax
  unsigned int v4; // r14d
  bool v5; // r12
  unsigned __int64 v6; // rbx
  const struct _tagpropertykey **v7; // rdi
  int v8; // eax
  const struct _tagpropertykey *v9; // r15
  DWORD pid; // eax
  __int64 v11; // rax
  PROPVARIANT *v12; // rax
  PROPVARIANT *v13; // rdi
  DWORD v14; // ecx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rax
  __int64 v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rsi
  DWORD v32; // ecx
  __int64 v33; // rdx
  __int64 v34; // rdx
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rcx
  __int64 v45; // rcx
  __int64 v46; // rcx
  __int64 v47; // rcx
  PROPVARIANT pvarSrc; // [rsp+30h] [rbp-68h] BYREF
  PROPVARIANT pvar; // [rsp+48h] [rbp-50h] BYREF
  struct IWICMetadataQueryReader *v51; // [rsp+B0h] [rbp+18h] BYREF
  __int64 v52; // [rsp+B8h] [rbp+20h] BYREF

  v1 = this;
  v52 = 0;
  v2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(**(_QWORD **)this->Data4 + 104LL))(
         *(_QWORD *)this->Data4,
         0,
         &v52);
  if ( v2 >= 0 )
  {
    v51 = 0;
    v2 = (*(__int64 (__fastcall **)(__int64, struct IWICMetadataQueryReader **))(*(_QWORD *)v52 + 64LL))(v52, &v51);
    if ( v2 >= 0 )
    {
      memset(&pvarSrc, 0, sizeof(pvarSrc));
      v3 = CContainerMasks::LookupContainerMask(v1 + 5);
      if ( __eh34_try(-1, 0) )
      {
        __eh34_scope_strut(0);
        v4 = v3;
        memset(&pvar, 0, sizeof(pvar));
        if ( v3 == 1 )
        {
          if ( ((int (__fastcall *)(struct IWICMetadataQueryReader *, const wchar_t *, PROPVARIANT *))v51->lpVtbl->GetMetadataByName)(
                 v51,
                 L"/app0",
                 &pvar) >= 0 )
            v1[1].Data4[6] = 1;
        }
        else
        {
          v1[1].Data4[6] = 0;
        }
        PropVariantClear(&pvar);
        v5 = (unsigned __int16)(GetOrientationValue(v51) - 5) <= 3u;
        v6 = 0;
        while ( 1 )
        {
          while ( 1 )
          {
            while ( 1 )
            {
              while ( 1 )
              {
                while ( 1 )
                {
                  if ( v6 >= 0xA5 )
                    goto LABEL_201;
                  v7 = (const struct _tagpropertykey **)(&gc_rgCapList + 9 * v6);
                  if ( (v4 & (_DWORD)v7[4]) != 0 )
                  {
                    v8 = *((_DWORD *)v7 + 6);
                    if ( !v8 || (unsigned int)(v8 - 7) <= 2 )
                    {
                      PropVariantClear(&pvarSrc);
                      if ( ((int (__fastcall *)(struct IWICMetadataQueryReader *, const struct _tagpropertykey *, PROPVARIANT *))v51->lpVtbl->GetMetadataByName)(
                             v51,
                             v7[8],
                             &pvarSrc) >= 0 )
                        break;
                    }
                  }
LABEL_11:
                  ++v6;
                }
                if ( (unsigned int)(*((_DWORD *)v7 + 6) - 7) <= 1 )
                {
                  CMetadataContainer::_ProcessRationalType(
                    (CMetadataContainer *)v1,
                    (const struct CAPABILITIES_LIST_ENTRY *)(&gc_rgCapList + 9 * v6),
                    &pvarSrc);
                  goto LABEL_11;
                }
                v9 = *v7;
                pid = (*v7)->pid;
                if ( pid != 100 )
                  break;
                v18 = *(_QWORD *)&v9->fmtid.Data1 - *(_QWORD *)&PKEY_GPS_LatitudeRef.fmtid.Data1;
                if ( *(_QWORD *)&v9->fmtid.Data1 == *(_QWORD *)&PKEY_GPS_LatitudeRef.fmtid.Data1 )
                  v18 = *(_QWORD *)v9->fmtid.Data4 - *(_QWORD *)PKEY_GPS_LatitudeRef.fmtid.Data4;
                if ( v18 )
                {
                  v19 = *(_QWORD *)&v9->fmtid.Data1 - *(_QWORD *)&PKEY_GPS_LongitudeRef.fmtid.Data1;
                  if ( *(_QWORD *)&v9->fmtid.Data1 == *(_QWORD *)&PKEY_GPS_LongitudeRef.fmtid.Data1 )
                    v19 = *(_QWORD *)v9->fmtid.Data4 - *(_QWORD *)PKEY_GPS_LongitudeRef.fmtid.Data4;
                  if ( v19 )
                  {
                    v20 = *(_QWORD *)&v9->fmtid.Data1 - *(_QWORD *)&PKEY_GPS_DestLatitudeRef.fmtid.Data1;
                    if ( *(_QWORD *)&v9->fmtid.Data1 == *(_QWORD *)&PKEY_GPS_DestLatitudeRef.fmtid.Data1 )
                      v20 = *(_QWORD *)v9->fmtid.Data4 - *(_QWORD *)PKEY_GPS_DestLatitudeRef.fmtid.Data4;
                    if ( v20 )
                    {
                      v21 = *(_QWORD *)&v9->fmtid.Data1 - *(_QWORD *)&PKEY_GPS_DestLongitudeRef.fmtid.Data1;
                      if ( *(_QWORD *)&v9->fmtid.Data1 == *(_QWORD *)&PKEY_GPS_DestLongitudeRef.fmtid.Data1 )
                        v21 = *(_QWORD *)v9->fmtid.Data4 - *(_QWORD *)PKEY_GPS_DestLongitudeRef.fmtid.Data4;
                      if ( v21 )
                        break;
                    }
                  }
                }
                memset(&pvar, 0, sizeof(pvar));
                PropVariantClear(&pvar);
                v22 = *(_QWORD *)&v1[6].Data1;
                if ( v22 )
                {
                  do
                  {
                    if ( *(_DWORD *)(v22 + 16) == v9->pid )
                    {
                      v26 = *(_QWORD *)v22 - *(_QWORD *)&v9->fmtid.Data1;
                      if ( *(_QWORD *)v22 == *(_QWORD *)&v9->fmtid.Data1 )
                        v26 = *(_QWORD *)(v22 + 8) - *(_QWORD *)v9->fmtid.Data4;
                      if ( !v26 )
                        break;
                    }
                    v22 = *(_QWORD *)(v22 + 56);
                  }
                  while ( v22 );
                  if ( v22 && PropVariantCopy(&pvar, (const PROPVARIANT *)(v22 + 24)) < 0 )
                    goto LABEL_71;
                }
                if ( !pvar.vt )
LABEL_71:
                  ((void (__stdcall *)(CPhotoPropertyItemList *, const struct _tagpropertykey *, const struct tagPROPVARIANT *, bool, bool))CPhotoPropertyItemList::_InternalUpdateOrAddItem)(
                    (CPhotoPropertyItemList *)&v1[6],
                    *v7,
                    &pvarSrc,
                    0,
                    0);
                PropVariantClear(&pvar);
                ++v6;
              }
              if ( v5 )
                break;
              v11 = *(_QWORD *)&v1[6].Data1;
              if ( !v11 )
                goto LABEL_16;
              v31 = *(_QWORD *)&v1[6].Data1;
              v32 = v9->pid;
              do
              {
                if ( *(_DWORD *)(v31 + 16) == v32 )
                {
                  v33 = *(_QWORD *)v31 - *(_QWORD *)&v9->fmtid.Data1;
                  if ( *(_QWORD *)v31 == *(_QWORD *)&v9->fmtid.Data1 )
                    v33 = *(_QWORD *)(v31 + 8) - *(_QWORD *)v9->fmtid.Data4;
                  if ( !v33 )
                    break;
                }
                v31 = *(_QWORD *)(v31 + 56);
              }
              while ( v31 );
              if ( !v31 )
              {
                do
                {
                  if ( *(_DWORD *)(v11 + 16) == v32 )
                  {
                    v34 = *(_QWORD *)v11 - *(_QWORD *)&v9->fmtid.Data1;
                    if ( *(_QWORD *)v11 == *(_QWORD *)&v9->fmtid.Data1 )
                      v34 = *(_QWORD *)(v11 + 8) - *(_QWORD *)v9->fmtid.Data4;
                    if ( !v34 )
                      break;
                  }
                  v11 = *(_QWORD *)(v11 + 56);
                }
                while ( v11 );
                if ( v11 )
                  goto LABEL_11;
LABEL_16:
                v12 = (PROPVARIANT *)LocalAlloc(0x40u, 0x40u);
                v13 = v12;
                if ( !v12 )
                  goto LABEL_11;
                v12[2].vt = 0;
                *(GUID *)&v12->vt = v9->fmtid;
                v14 = v9->pid;
                goto LABEL_18;
              }
LABEL_197:
              if ( *(_BYTE *)(v31 + 49) )
                goto LABEL_11;
              PropVariantClear((PROPVARIANT *)(v31 + 24));
              PropVariantCopy((PROPVARIANT *)(v31 + 24), &pvarSrc);
              *(_BYTE *)(v31 + 48) = 0;
              ++v6;
            }
            if ( pid != 12 )
              break;
            v23 = *(_QWORD *)&v9->fmtid.Data1 - PKEY_Image_HorizontalResolution_Proxy;
            if ( *(_QWORD *)&v9->fmtid.Data1 == (_QWORD)PKEY_Image_HorizontalResolution_Proxy )
              v23 = *(_QWORD *)v9->fmtid.Data4 - *((_QWORD *)&PKEY_Image_HorizontalResolution_Proxy + 1);
            if ( v23 )
              goto LABEL_58;
            v37 = *(_QWORD *)&v1[6].Data1;
            if ( v37 )
            {
              v31 = *(_QWORD *)&v1[6].Data1;
              do
              {
                if ( *(_DWORD *)(v31 + 16) == 13 )
                {
                  v38 = *(_QWORD *)v31 - PKEY_Image_VerticalResolution_Proxy;
                  if ( *(_QWORD *)v31 == (_QWORD)PKEY_Image_VerticalResolution_Proxy )
                    v38 = *(_QWORD *)(v31 + 8) - *((_QWORD *)&PKEY_Image_VerticalResolution_Proxy + 1);
                  if ( !v38 )
                    break;
                }
                v31 = *(_QWORD *)(v31 + 56);
              }
              while ( v31 );
              if ( v31 )
                goto LABEL_197;
              do
              {
                if ( *(_DWORD *)(v37 + 16) == 13 )
                {
                  v39 = *(_QWORD *)v37 - PKEY_Image_VerticalResolution_Proxy;
                  if ( *(_QWORD *)v37 == (_QWORD)PKEY_Image_VerticalResolution_Proxy )
                    v39 = *(_QWORD *)(v37 + 8) - *((_QWORD *)&PKEY_Image_VerticalResolution_Proxy + 1);
                  if ( !v39 )
                    break;
                }
                v37 = *(_QWORD *)(v37 + 56);
              }
              while ( v37 );
              if ( v37 )
                goto LABEL_11;
            }
            v12 = (PROPVARIANT *)LocalAlloc(0x40u, 0x40u);
            v13 = v12;
            if ( !v12 )
              goto LABEL_11;
            v12[2].vt = 0;
            *(_OWORD *)&v12->vt = PKEY_Image_VerticalResolution_Proxy;
            v14 = 13;
LABEL_18:
            *((_DWORD *)&v12->decVal + 4) = v14;
            if ( PropVariantCopy(v12 + 1, &pvarSrc) < 0 )
            {
              LocalFree(v13);
              ++v6;
            }
            else
            {
              v15 = *(_QWORD *)v1[6].Data4;
              if ( v15 )
                *(_QWORD *)(v15 + 56) = v13;
              else
                *(_QWORD *)&v1[6].Data1 = v13;
              *(_QWORD *)v1[6].Data4 = v13;
              ++v6;
            }
          }
          switch ( pid )
          {
            case 3u:
              v24 = *(_QWORD *)&v9->fmtid.Data1 - *(_QWORD *)&PKEY_Image_HorizontalSize.fmtid.Data1;
              if ( *(_QWORD *)&v9->fmtid.Data1 == *(_QWORD *)&PKEY_Image_HorizontalSize.fmtid.Data1 )
                v24 = *(_QWORD *)v9->fmtid.Data4 - *(_QWORD *)PKEY_Image_HorizontalSize.fmtid.Data4;
              if ( v24 )
                goto LABEL_58;
              v25 = *(_QWORD *)&v1[6].Data1;
              if ( v25 )
              {
                v31 = *(_QWORD *)&v1[6].Data1;
                do
                {
                  if ( *(_DWORD *)(v31 + 16) == 4 )
                  {
                    v40 = *(_QWORD *)v31 - *(_QWORD *)&PKEY_Image_VerticalSize.fmtid.Data1;
                    if ( *(_QWORD *)v31 == *(_QWORD *)&PKEY_Image_VerticalSize.fmtid.Data1 )
                      v40 = *(_QWORD *)(v31 + 8) - *(_QWORD *)PKEY_Image_VerticalSize.fmtid.Data4;
                    if ( !v40 )
                      break;
                  }
                  v31 = *(_QWORD *)(v31 + 56);
                }
                while ( v31 );
                if ( v31 )
                  goto LABEL_197;
                do
                {
                  if ( *(_DWORD *)(v25 + 16) == 4 )
                  {
                    v41 = *(_QWORD *)v25 - *(_QWORD *)&PKEY_Image_VerticalSize.fmtid.Data1;
                    if ( *(_QWORD *)v25 == *(_QWORD *)&PKEY_Image_VerticalSize.fmtid.Data1 )
                      v41 = *(_QWORD *)(v25 + 8) - *(_QWORD *)PKEY_Image_VerticalSize.fmtid.Data4;
                    if ( !v41 )
                      break;
                  }
                  v25 = *(_QWORD *)(v25 + 56);
                }
                while ( v25 );
                if ( v25 )
                  goto LABEL_11;
              }
              v12 = (PROPVARIANT *)LocalAlloc(0x40u, 0x40u);
              v13 = v12;
              if ( !v12 )
                goto LABEL_11;
              v12[2].vt = 0;
              *(GUID *)&v12->vt = PKEY_Image_VerticalSize.fmtid;
              v14 = PKEY_Image_VerticalSize.pid;
              goto LABEL_18;
            case 5u:
              v27 = *(_QWORD *)&v9->fmtid.Data1 - *(_QWORD *)&PKEY_Image_HorizontalResolution.fmtid.Data1;
              if ( *(_QWORD *)&v9->fmtid.Data1 == *(_QWORD *)&PKEY_Image_HorizontalResolution.fmtid.Data1 )
                v27 = *(_QWORD *)v9->fmtid.Data4 - *(_QWORD *)PKEY_Image_HorizontalResolution.fmtid.Data4;
              if ( !v27 )
              {
                v28 = *(_QWORD *)&v1[6].Data1;
                if ( v28 )
                {
                  v31 = *(_QWORD *)&v1[6].Data1;
                  do
                  {
                    if ( *(_DWORD *)(v31 + 16) == 6 )
                    {
                      v42 = *(_QWORD *)v31 - *(_QWORD *)&PKEY_Image_VerticalResolution.fmtid.Data1;
                      if ( *(_QWORD *)v31 == *(_QWORD *)&PKEY_Image_VerticalResolution.fmtid.Data1 )
                        v42 = *(_QWORD *)(v31 + 8) - *(_QWORD *)PKEY_Image_VerticalResolution.fmtid.Data4;
                      if ( !v42 )
                        break;
                    }
                    v31 = *(_QWORD *)(v31 + 56);
                  }
                  while ( v31 );
                  if ( v31 )
                    goto LABEL_197;
                  do
                  {
                    if ( *(_DWORD *)(v28 + 16) == 6 )
                    {
                      v43 = *(_QWORD *)v28 - *(_QWORD *)&PKEY_Image_VerticalResolution.fmtid.Data1;
                      if ( *(_QWORD *)v28 == *(_QWORD *)&PKEY_Image_VerticalResolution.fmtid.Data1 )
                        v43 = *(_QWORD *)(v28 + 8) - *(_QWORD *)PKEY_Image_VerticalResolution.fmtid.Data4;
                      if ( !v43 )
                        break;
                    }
                    v28 = *(_QWORD *)(v28 + 56);
                  }
                  while ( v28 );
                  if ( v28 )
                    goto LABEL_11;
                }
                v12 = (PROPVARIANT *)LocalAlloc(0x40u, 0x40u);
                v13 = v12;
                if ( !v12 )
                  goto LABEL_11;
                v12[2].vt = 0;
                *(GUID *)&v12->vt = PKEY_Image_VerticalResolution.fmtid;
                v14 = PKEY_Image_VerticalResolution.pid;
                goto LABEL_18;
              }
LABEL_26:
              if ( pid != 4 )
                goto LABEL_27;
              v35 = *(_QWORD *)&v9->fmtid.Data1 - *(_QWORD *)&PKEY_Image_VerticalSize.fmtid.Data1;
              if ( *(_QWORD *)&v9->fmtid.Data1 == *(_QWORD *)&PKEY_Image_VerticalSize.fmtid.Data1 )
                v35 = *(_QWORD *)v9->fmtid.Data4 - *(_QWORD *)PKEY_Image_VerticalSize.fmtid.Data4;
              if ( !v35 )
              {
                v36 = *(_QWORD *)&v1[6].Data1;
                if ( v36 )
                {
                  v31 = *(_QWORD *)&v1[6].Data1;
                  do
                  {
                    if ( *(_DWORD *)(v31 + 16) == 3 )
                    {
                      v46 = *(_QWORD *)v31 - *(_QWORD *)&PKEY_Image_HorizontalSize.fmtid.Data1;
                      if ( *(_QWORD *)v31 == *(_QWORD *)&PKEY_Image_HorizontalSize.fmtid.Data1 )
                        v46 = *(_QWORD *)(v31 + 8) - *(_QWORD *)PKEY_Image_HorizontalSize.fmtid.Data4;
                      if ( !v46 )
                        break;
                    }
                    v31 = *(_QWORD *)(v31 + 56);
                  }
                  while ( v31 );
                  if ( v31 )
                    goto LABEL_197;
                  do
                  {
                    if ( *(_DWORD *)(v36 + 16) == 3 )
                    {
                      v47 = *(_QWORD *)v36 - *(_QWORD *)&PKEY_Image_HorizontalSize.fmtid.Data1;
                      if ( *(_QWORD *)v36 == *(_QWORD *)&PKEY_Image_HorizontalSize.fmtid.Data1 )
                        v47 = *(_QWORD *)(v36 + 8) - *(_QWORD *)PKEY_Image_HorizontalSize.fmtid.Data4;
                      if ( !v47 )
                        break;
                    }
                    v36 = *(_QWORD *)(v36 + 56);
                  }
                  while ( v36 );
                  if ( v36 )
                    goto LABEL_11;
                }
                v12 = (PROPVARIANT *)LocalAlloc(0x40u, 0x40u);
                v13 = v12;
                if ( !v12 )
                  goto LABEL_11;
                v12[2].vt = 0;
                *(GUID *)&v12->vt = PKEY_Image_HorizontalSize.fmtid;
                v14 = PKEY_Image_HorizontalSize.pid;
                goto LABEL_18;
              }
LABEL_58:
              ((void (__stdcall *)(CPhotoPropertyItemList *, const struct _tagpropertykey *, const struct tagPROPVARIANT *, bool, bool))CPhotoPropertyItemList::_InternalUpdateOrAddItem)(
                (CPhotoPropertyItemList *)&v1[6],
                v9,
                &pvarSrc,
                0,
                0);
              ++v6;
              break;
            case 0xDu:
              v29 = *(_QWORD *)&v9->fmtid.Data1 - PKEY_Image_VerticalResolution_Proxy;
              if ( *(_QWORD *)&v9->fmtid.Data1 == (_QWORD)PKEY_Image_VerticalResolution_Proxy )
                v29 = *(_QWORD *)v9->fmtid.Data4 - *((_QWORD *)&PKEY_Image_VerticalResolution_Proxy + 1);
              if ( !v29 )
              {
                v30 = *(_QWORD *)&v1[6].Data1;
                if ( v30 )
                {
                  v31 = *(_QWORD *)&v1[6].Data1;
                  do
                  {
                    if ( *(_DWORD *)(v31 + 16) == 12 )
                    {
                      v44 = *(_QWORD *)v31 - PKEY_Image_HorizontalResolution_Proxy;
                      if ( *(_QWORD *)v31 == (_QWORD)PKEY_Image_HorizontalResolution_Proxy )
                        v44 = *(_QWORD *)(v31 + 8) - *((_QWORD *)&PKEY_Image_HorizontalResolution_Proxy + 1);
                      if ( !v44 )
                        break;
                    }
                    v31 = *(_QWORD *)(v31 + 56);
                  }
                  while ( v31 );
                  if ( v31 )
                    goto LABEL_197;
                  do
                  {
                    if ( *(_DWORD *)(v30 + 16) == 12 )
                    {
                      v45 = *(_QWORD *)v30 - PKEY_Image_HorizontalResolution_Proxy;
                      if ( *(_QWORD *)v30 == (_QWORD)PKEY_Image_HorizontalResolution_Proxy )
                        v45 = *(_QWORD *)(v30 + 8) - *((_QWORD *)&PKEY_Image_HorizontalResolution_Proxy + 1);
                      if ( !v45 )
                        break;
                    }
                    v30 = *(_QWORD *)(v30 + 56);
                  }
                  while ( v30 );
                  if ( v30 )
                    goto LABEL_11;
                }
                v12 = (PROPVARIANT *)LocalAlloc(0x40u, 0x40u);
                v13 = v12;
                if ( !v12 )
                  goto LABEL_11;
                v12[2].vt = 0;
                *(_OWORD *)&v12->vt = PKEY_Image_HorizontalResolution_Proxy;
                v14 = 12;
                goto LABEL_18;
              }
LABEL_27:
              if ( pid != 6 )
                goto LABEL_58;
              v16 = *(_QWORD *)&v9->fmtid.Data1 - *(_QWORD *)&PKEY_Image_VerticalResolution.fmtid.Data1;
              if ( *(_QWORD *)&v9->fmtid.Data1 == *(_QWORD *)&PKEY_Image_VerticalResolution.fmtid.Data1 )
                v16 = *(_QWORD *)v9->fmtid.Data4 - *(_QWORD *)PKEY_Image_VerticalResolution.fmtid.Data4;
              if ( v16 )
                goto LABEL_58;
              ((void (__stdcall *)(CPhotoPropertyItemList *, const struct _tagpropertykey *, const struct tagPROPVARIANT *, bool, bool))CPhotoPropertyItemList::_InternalUpdateOrAddItem)(
                (CPhotoPropertyItemList *)&v1[6],
                &PKEY_Image_HorizontalResolution,
                &pvarSrc,
                0,
                0);
              ++v6;
              break;
            default:
              goto LABEL_26;
          }
        }
      }
      if ( __eh34_catch(0) )
      {
        if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', 0) )
        {
          v1 = this;
          __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_1800038E7);
        }
      }
LABEL_201:
      PropVariantClear(&pvarSrc);
      v2 = 0;
    }
    if ( v51 )
      ((void (__fastcall *)(struct IWICMetadataQueryReader *))v51->lpVtbl->Release)(v51);
  }
  CMetadataContainer::_SynthesizeImagePKEYs((CMetadataContainer *)v1);
  if ( v52 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180002f30  mov     r11, rsp
0x180002f33  mov     [r11+8], rcx
0x180002f37  push    rbx
0x180002f38  push    rsi
0x180002f39  push    rdi
0x180002f3a  push    r12
0x180002f3c  push    r13
0x180002f3e  push    r14
0x180002f40  push    r15
0x180002f42  sub     rsp, 60h
0x180002f46  mov     r13, rcx
0x180002f49  mov     qword ptr [r11+20h], 0
0x180002f51  mov     rcx, [rcx+8]
0x180002f55  mov     rax, [rcx]
0x180002f58  lea     r8, [r11+20h]
0x180002f5c  xor     edx, edx
0x180002f5e  mov     rax, [rax+68h]
0x180002f62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f67  mov     ebx, eax
0x180002f69  test    eax, eax
0x180002f6b  js      loc_1800031D8
0x180002f71  mov     [rsp+98h+arg_10], 0
0x180002f7d  mov     rcx, [rsp+98h+arg_18]
0x180002f85  mov     rax, [rcx]
0x180002f88  lea     rdx, [rsp+98h+arg_10]
0x180002f90  mov     rax, [rax+40h]
0x180002f94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f99  mov     ebx, eax
0x180002f9b  test    eax, eax
0x180002f9d  js      loc_1800031BE
0x180002fa3  xorps   xmm0, xmm0
0x180002fa6  xor     eax, eax
0x180002fa8  movups  xmmword ptr [rsp+98h+pvarSrc], xmm0
0x180002fad  mov     qword ptr [rsp+98h+pvarSrc+10h], rax
0x180002fb2  lea     rcx, [r13+50h]; struct _GUID *
0x180002fb6  call    ?LookupContainerMask@CContainerMasks@@SAKAEBU_GUID@@@Z; CContainerMasks::LookupContainerMask(_GUID const &)
0x180002fbb  mov     r14d, eax
0x180002fbe  xor     eax, eax
0x180002fc0  movups  xmmword ptr [rsp+98h+pvar], xmm0
0x180002fc5  mov     qword ptr [rsp+98h+pvar+10h], rax
0x180002fca  cmp     r14d, 1
0x180002fce  jz      loc_18000332F
0x180002fd4  mov     [r13+1Eh], al
0x180002fd8  lea     rcx, [rsp+98h+pvar]; pvar
0x180002fdd  call    cs:__imp_PropVariantClear
0x180002fe4  nop     dword ptr [rax+rax+00h]
0x180002fe9  mov     rcx, [rsp+98h+arg_10]; struct IWICMetadataQueryReader *
0x180002ff1  call    ?GetOrientationValue@@YAGPEAUIWICMetadataQueryReader@@@Z; GetOrientationValue(IWICMetadataQueryReader *)
0x180002ff6  sub     ax, 5
0x180002ffa  cmp     ax, 3
0x180002ffe  ja      loc_1800038DF
0x180003004  mov     r12b, 1
0x180003007  xor     ebx, ebx
0x180003009  lea     rcx, ?gc_rgCapList@@3QBUCAPABILITIES_LIST_ENTRY@@B; CAPABILITIES_LIST_ENTRY const near * const gc_rgCapList
0x180003010  cmp     rbx, 0A5h
0x180003017  jnb     loc_1800031AB
0x18000301d  lea     rax, [rbx+rbx*8]
0x180003021  lea     rdi, [rcx+rax*8]
0x180003025  test    [rdi+20h], r14d
0x180003029  jz      short loc_18000306F
0x18000302b  mov     eax, [rdi+18h]
0x18000302e  test    eax, eax
0x180003030  jnz     loc_180003600
0x180003036  lea     rcx, [rsp+98h+pvarSrc]; pvar
0x18000303b  call    cs:__imp_PropVariantClear
0x180003042  nop     dword ptr [rax+rax+00h]
0x180003047  mov     rcx, [rsp+98h+arg_10]
0x18000304f  mov     rax, [rcx]
0x180003052  lea     r8, [rsp+98h+pvarSrc]
0x180003057  mov     rdx, [rdi+40h]
0x18000305b  mov     rax, [rax+28h]
0x18000305f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003064  test    eax, eax
0x180003066  jns     short loc_180003074
0x180003068  lea     rcx, ?gc_rgCapList@@3QBUCAPABILITIES_LIST_ENTRY@@B; CAPABILITIES_LIST_ENTRY const near * const gc_rgCapList
0x18000306f  inc     rbx
0x180003072  jmp     short loc_180003010
0x180003074  mov     eax, [rdi+18h]
0x180003077  sub     eax, 7
0x18000307a  cmp     eax, 1
0x18000307d  jbe     loc_180003196
0x180003083  mov     r15, [rdi]
0x180003086  mov     eax, [r15+10h]
0x18000308a  cmp     eax, 64h ; 'd'
0x18000308d  jz      loc_18000320E
0x180003093  test    r12b, r12b
0x180003096  jnz     short loc_180003115
0x180003098  mov     rax, [r13+60h]
0x18000309c  test    rax, rax
0x18000309f  jnz     loc_18000351A
0x1800030a5  mov     edx, 40h ; '@'; uBytes
0x1800030aa  mov     ecx, edx; uFlags
0x1800030ac  call    cs:__imp_LocalAlloc
0x1800030b3  nop     dword ptr [rax+rax+00h]
0x1800030b8  mov     rdi, rax
0x1800030bb  test    rax, rax
0x1800030be  jz      short loc_180003068
0x1800030c0  mov     word ptr [rax+30h], 0
0x1800030c6  movups  xmm0, xmmword ptr [r15]
0x1800030ca  movups  xmmword ptr [rax], xmm0
0x1800030cd  mov     ecx, [r15+10h]
0x1800030d1  mov     [rax+10h], ecx
0x1800030d4  lea     rcx, [rax+18h]; pvarDest
0x1800030d8  lea     rdx, [rsp+98h+pvarSrc]; pvarSrc
0x1800030dd  call    cs:__imp_PropVariantCopy
0x1800030e4  nop     dword ptr [rax+rax+00h]
0x1800030e9  test    eax, eax
0x1800030eb  js      loc_1800032C9
0x1800030f1  mov     rax, [r13+68h]
0x1800030f5  test    rax, rax
0x1800030f8  jz      loc_1800035E9
0x1800030fe  mov     [rax+38h], rdi
0x180003102  mov     [r13+68h], rdi
0x180003106  lea     rcx, ?gc_rgCapList@@3QBUCAPABILITIES_LIST_ENTRY@@B; CAPABILITIES_LIST_ENTRY const near * const gc_rgCapList
0x18000310d  inc     rbx
0x180003110  jmp     loc_180003010
0x180003115  cmp     eax, 0Ch
0x180003118  jz      loc_1800032E7
0x18000311e  cmp     eax, 3
0x180003121  jz      loc_180003361
0x180003127  cmp     eax, 5
0x18000312a  jz      loc_18000344C
0x180003130  cmp     eax, 0Dh
0x180003133  jz      loc_1800034B3
0x180003139  cmp     eax, 4
0x18000313c  jz      loc_180003582
0x180003142  cmp     eax, 6
0x180003145  jnz     loc_180003307
0x18000314b  mov     rax, [r15]
0x18000314e  sub     rax, qword ptr cs:PKEY_Image_VerticalResolution.fmtid.Data1
0x180003155  jnz     short loc_180003162
0x180003157  mov     rax, [r15+8]
0x18000315b  sub     rax, qword ptr cs:PKEY_Image_VerticalResolution.fmtid.Data4
0x180003162  test    rax, rax
0x180003165  jnz     loc_180003307
0x18000316b  lea     rcx, [r13+60h]; this
0x18000316f  mov     [rsp+98h+var_78], al; bool
0x180003173  xor     r9d, r9d; bool
0x180003176  lea     r8, [rsp+98h+pvarSrc]; struct tagPROPVARIANT *
0x18000317b  lea     rdx, PKEY_Image_HorizontalResolution; struct _tagpropertykey *
0x180003182  call    ?_InternalUpdateOrAddItem@CPhotoPropertyItemList@@AEAAJPEBU_tagpropertykey@@PEBUtagPROPVARIANT@@_N2@Z; CPhotoPropertyItemList::_InternalUpdateOrAddItem(_tagpropertykey const *,tagPROPVARIANT const *,bool,bool)
0x180003187  lea     rcx, ?gc_rgCapList@@3QBUCAPABILITIES_LIST_ENTRY@@B; CAPABILITIES_LIST_ENTRY const near * const gc_rgCapList
0x18000318e  inc     rbx
0x180003191  jmp     loc_180003010
0x180003196  lea     r8, [rsp+98h+pvarSrc]; struct tagPROPVARIANT *
0x18000319b  mov     rdx, rdi; struct CAPABILITIES_LIST_ENTRY *
0x18000319e  mov     rcx, r13; this
0x1800031a1  call    ?_ProcessRationalType@CMetadataContainer@@AEAAJPEBUCAPABILITIES_LIST_ENTRY@@PEBUtagPROPVARIANT@@@Z; CMetadataContainer::_ProcessRationalType(CAPABILITIES_LIST_ENTRY const *,tagPROPVARIANT const *)
0x1800031a6  jmp     loc_180003068
0x1800031ab  lea     rcx, [rsp+98h+pvarSrc]; pvar
0x1800031b0  call    cs:__imp_PropVariantClear
0x1800031b7  nop     dword ptr [rax+rax+00h]
0x1800031bc  xor     ebx, ebx
0x1800031be  mov     rcx, [rsp+98h+arg_10]
0x1800031c6  test    rcx, rcx
0x1800031c9  jz      short loc_1800031D8
0x1800031cb  mov     rax, [rcx]
0x1800031ce  mov     rax, [rax+10h]
0x1800031d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031d7  nop
0x1800031d8  mov     rcx, r13; this
0x1800031db  call    ?_SynthesizeImagePKEYs@CMetadataContainer@@AEAAXXZ; CMetadataContainer::_SynthesizeImagePKEYs(void)
0x1800031e0  nop
0x1800031e1  mov     rcx, [rsp+98h+arg_18]
0x1800031e9  test    rcx, rcx
0x1800031ec  jz      short loc_1800031FB
0x1800031ee  mov     rax, [rcx]
0x1800031f1  mov     rax, [rax+10h]
0x1800031f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031fa  nop
0x1800031fb  mov     eax, ebx
0x1800031fd  add     rsp, 60h
0x180003201  pop     r15
0x180003203  pop     r14
0x180003205  pop     r13
0x180003207  pop     r12
0x180003209  pop     rdi
0x18000320a  pop     rsi
0x18000320b  pop     rbx
0x18000320c  retn
0x18000320e  mov     rcx, [r15]
0x180003211  sub     rcx, qword ptr cs:PKEY_GPS_LatitudeRef.fmtid.Data1
0x180003218  jnz     short loc_180003225
0x18000321a  mov     rcx, [r15+8]
0x18000321e  sub     rcx, qword ptr cs:PKEY_GPS_LatitudeRef.fmtid.Data4
0x180003225  test    rcx, rcx
0x180003228  jz      short loc_18000328B
0x18000322a  mov     rcx, [r15]
0x18000322d  sub     rcx, qword ptr cs:PKEY_GPS_LongitudeRef.fmtid.Data1
0x180003234  jnz     short loc_180003241
0x180003236  mov     rcx, [r15+8]
0x18000323a  sub     rcx, qword ptr cs:PKEY_GPS_LongitudeRef.fmtid.Data4
0x180003241  test    rcx, rcx
0x180003244  jz      short loc_18000328B
0x180003246  mov     rcx, [r15]
0x180003249  sub     rcx, qword ptr cs:PKEY_GPS_DestLatitudeRef.fmtid.Data1
0x180003250  jnz     short loc_18000325D
0x180003252  mov     rcx, [r15+8]
0x180003256  sub     rcx, qword ptr cs:PKEY_GPS_DestLatitudeRef.fmtid.Data4
0x18000325d  test    rcx, rcx
0x180003260  jz      short loc_18000328B
0x180003262  cmp     eax, 64h ; 'd'
0x180003265  jnz     loc_180003093
0x18000326b  mov     rcx, [r15]
0x18000326e  sub     rcx, qword ptr cs:PKEY_GPS_DestLongitudeRef.fmtid.Data1
0x180003275  jnz     short loc_180003282
0x180003277  mov     rcx, [r15+8]
0x18000327b  sub     rcx, qword ptr cs:PKEY_GPS_DestLongitudeRef.fmtid.Data4
0x180003282  test    rcx, rcx
0x180003285  jnz     loc_180003093
0x18000328b  xorps   xmm0, xmm0
0x18000328e  xor     eax, eax
0x180003290  movups  xmmword ptr [rsp+98h+pvar], xmm0
0x180003295  mov     qword ptr [rsp+98h+pvar+10h], rax
0x18000329a  lea     rcx, [rsp+98h+pvar]; pvar
0x18000329f  call    cs:__imp_PropVariantClear
0x1800032a6  nop     dword ptr [rax+rax+00h]
0x1800032ab  mov     rdx, [r13+60h]
0x1800032af  test    rdx, rdx
0x1800032b2  jnz     loc_1800033C4
0x1800032b8  cmp     word ptr [rsp+98h+pvar], 0
0x1800032be  jz      loc_1800033FC
0x1800032c4  jmp     loc_180003415
0x1800032c9  mov     rcx, rdi; hMem
0x1800032cc  call    cs:__imp_LocalFree
0x1800032d3  nop     dword ptr [rax+rax+00h]
0x1800032d8  lea     rcx, ?gc_rgCapList@@3QBUCAPABILITIES_LIST_ENTRY@@B; CAPABILITIES_LIST_ENTRY const near * const gc_rgCapList
0x1800032df  inc     rbx
0x1800032e2  jmp     loc_180003010
0x1800032e7  mov     rax, [r15]
0x1800032ea  sub     rax, qword ptr cs:PKEY_Image_HorizontalResolution_Proxy
0x1800032f1  jnz     short loc_1800032FE
0x1800032f3  mov     rax, [r15+8]
0x1800032f7  sub     rax, qword ptr cs:PKEY_Image_HorizontalResolution_Proxy+8
0x1800032fe  test    rax, rax
0x180003301  jz      loc_180003611
0x180003307  lea     rcx, [r13+60h]; this
0x18000330b  mov     [rsp+98h+var_78], 0; bool
0x180003310  xor     r9d, r9d; bool
0x180003313  lea     r8, [rsp+98h+pvarSrc]; struct tagPROPVARIANT *
0x180003318  mov     rdx, r15; struct _tagpropertykey *
0x18000331b  call    ?_InternalUpdateOrAddItem@CPhotoPropertyItemList@@AEAAJPEBU_tagpropertykey@@PEBUtagPROPVARIANT@@_N2@Z; CPhotoPropertyItemList::_InternalUpdateOrAddItem(_tagpropertykey const *,tagPROPVARIANT const *,bool,bool)
0x180003320  lea     rcx, ?gc_rgCapList@@3QBUCAPABILITIES_LIST_ENTRY@@B; CAPABILITIES_LIST_ENTRY const near * const gc_rgCapList
0x180003327  inc     rbx
0x18000332a  jmp     loc_180003010
0x18000332f  mov     rcx, [rsp+98h+arg_10]
0x180003337  mov     rax, [rcx]
0x18000333a  lea     r8, [rsp+98h+pvar]
0x18000333f  lea     rdx, aApp0; "/app0"
0x180003346  mov     rax, [rax+28h]
0x18000334a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000334f  test    eax, eax
0x180003351  js      loc_180002FD8
0x180003357  mov     byte ptr [r13+1Eh], 1
0x18000335c  jmp     loc_180002FD8
0x180003361  mov     rax, [r15]
0x180003364  sub     rax, qword ptr cs:PKEY_Image_HorizontalSize.fmtid.Data1
0x18000336b  jnz     short loc_180003378
0x18000336d  mov     rax, [r15+8]
0x180003371  sub     rax, qword ptr cs:PKEY_Image_HorizontalSize.fmtid.Data4
0x180003378  test    rax, rax
0x18000337b  jnz     short loc_180003307
0x18000337d  mov     rax, [r13+60h]
0x180003381  test    rax, rax
0x180003384  jnz     loc_1800036C6
0x18000338a  mov     edx, 40h ; '@'; uBytes
0x18000338f  mov     ecx, edx; uFlags
0x180003391  call    cs:__imp_LocalAlloc
0x180003398  nop     dword ptr [rax+rax+00h]
0x18000339d  mov     rdi, rax
0x1800033a0  test    rax, rax
0x1800033a3  jz      loc_180003068
0x1800033a9  mov     word ptr [rax+30h], 0
0x1800033af  movups  xmm0, xmmword ptr cs:PKEY_Image_VerticalSize.fmtid.Data1
0x1800033b6  movups  xmmword ptr [rax], xmm0
0x1800033b9  mov     ecx, cs:PKEY_Image_VerticalSize.pid
0x1800033bf  jmp     loc_1800030D1
0x1800033c4  mov     eax, [r15+10h]
0x1800033c8  cmp     [rdx+10h], eax
0x1800033cb  jz      short loc_180003435
0x1800033cd  mov     rdx, [rdx+38h]
0x1800033d1  test    rdx, rdx
0x1800033d4  jnz     short loc_1800033C8
0x1800033d6  test    rdx, rdx
0x1800033d9  jz      loc_1800032B8
0x1800033df  add     rdx, 18h; pvarSrc
0x1800033e3  lea     rcx, [rsp+98h+pvar]; pvarDest
0x1800033e8  call    cs:__imp_PropVariantCopy
0x1800033ef  nop     dword ptr [rax+rax+00h]
0x1800033f4  test    eax, eax
0x1800033f6  jns     loc_1800032B8
0x1800033fc  mov     [rsp+98h+var_78], 0; bool
0x180003401  xor     r9d, r9d; bool
0x180003404  lea     r8, [rsp+98h+pvarSrc]; struct tagPROPVARIANT *
0x180003409  mov     rdx, [rdi]; struct _tagpropertykey *
0x18000340c  lea     rcx, [r13+60h]; this
0x180003410  call    ?_InternalUpdateOrAddItem@CPhotoPropertyItemList@@AEAAJPEBU_tagpropertykey@@PEBUtagPROPVARIANT@@_N2@Z; CPhotoPropertyItemList::_InternalUpdateOrAddItem(_tagpropertykey const *,tagPROPVARIANT const *,bool,bool)
0x180003415  lea     rcx, [rsp+98h+pvar]; pvar
0x18000341a  call    cs:__imp_PropVariantClear
0x180003421  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
