# WICTiffReadDirectory(IWICMetadataReader *,tiff *)

- ea: `0x1800a194c`
- end: `0x1800a22d8`
- name: `?WICTiffReadDirectory@@YAJPEAUIWICMetadataReader@@PEAUtiff@@@Z`
- size: `2444`
- prototype: `__int64 __fastcall(struct IWICMetadataReader *, struct tiff *)`
- caller_count: `3`
- callee_count: `30`
- tags: `broker_com_uri`

## callers

- `0x1800a0e68`
- `0x1800a1810`
- `0x1801b6100`

## callees

- `0x18002ae20`
- `0x18002ae60`
- `0x1800344d0`
- `0x180045394`
- `0x18009c5a8`
- `0x1800a194c`
- `0x1800ad2e4`
- `0x1800afbec`
- `0x1800bd9d4`
- `0x1800e5a18`
- `0x1801512b0`
- `0x180151340`
- `0x180151370`
- `0x1801514e0`
- `0x180151d10`
- `0x180151e80`
- `0x180152200`
- `0x180155840`
- `0x180155960`
- `0x180155a70`
- `0x18015d0d0`
- `0x18015d1b0`
- `0x18015e2d0`
- `0x1801b9f54`
- `0x1801ba0d8`
- `0x1801ba134`
- `0x1801ba644`
- `0x1801ba6b4`
- `0x1801c2664`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a1bd7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a1fd5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a2293`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a22a3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a1bd7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a1fd5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a2293`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a22a3`

## string_xrefs

- `0x1800a2267`: `WICTIFFReadDir`

## pseudocode

```c
__int64 __fastcall WICTiffReadDirectory(struct IWICMetadataReader *a1, struct tiff *a2)
{
  struct IWICMetadataReaderVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetEnumerator)(IWICMetadataReader *, IWICEnumMetadataItem **); // rax
  CEnumMetadataItem *v6; // rax
  CMILCOMBase *v7; // rax
  CMILCOMBase *v8; // rsi
  int Interface; // eax
  int v10; // ebx
  struct tagPROPVARIANT *v11; // r8
  int NextValue; // ebx
  __int64 v13; // r8
  unsigned int v14; // esi
  unsigned __int64 v15; // r11
  __int64 v16; // r10
  unsigned __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rdx
  unsigned int v20; // eax
  int v21; // eax
  struct tagPROPVARIANT *v22; // r8
  char v23; // r13
  unsigned int v24; // r15d
  int v25; // eax
  int v26; // r14d
  _DWORD **v27; // rdx
  __int64 v28; // rsi
  unsigned __int64 v29; // r10
  unsigned __int64 v30; // rcx
  void **v31; // rbx
  __int64 v32; // rsi
  _QWORD *v33; // rdx
  __int64 v34; // rax
  unsigned int i; // r8d
  int v36; // ecx
  unsigned __int64 v37; // r10
  unsigned int j; // r8d
  unsigned __int64 v39; // r9
  __int64 v40; // rcx
  unsigned __int64 v41; // r11
  __int64 v42; // rax
  const char *v43; // r8
  __int64 v44; // rax
  struct tagPROPVARIANT v46; // [rsp+30h] [rbp-38h] BYREF
  struct tagPROPVARIANT pvar; // [rsp+48h] [rbp-20h] BYREF
  struct IWICEnumMetadataItem *v48; // [rsp+B0h] [rbp+48h] BYREF

  *((_QWORD *)a2 + 164) = a1;
  lpVtbl = a1->lpVtbl;
  v48 = 0;
  memset(&v46, 0, sizeof(v46));
  GetEnumerator = lpVtbl->GetEnumerator;
  memset(&pvar, 0, sizeof(pvar));
  if ( ((int (__fastcall *)(struct IWICMetadataReader *, struct IWICEnumMetadataItem **))GetEnumerator)(a1, &v48) < 0 )
  {
    v6 = (CEnumMetadataItem *)operator new(0x68u);
    if ( !v6 || (v7 = CEnumMetadataItem::CEnumMetadataItem(v6, a1), (v8 = v7) == 0) )
    {
      v10 = -2147024882;
      if ( (_DWORD)g_doStackCaptures )
      {
        DoStackCapture(-2147024882);
        goto LABEL_164;
      }
      goto LABEL_167;
    }
    CMILCOMBase::InternalAddRef(v7);
    Interface = CMILCOMBase::InternalQueryInterface(v8, &IID_IWICEnumMetadataItem, (void **)&v48);
    v10 = Interface;
    if ( Interface < 0 && (_DWORD)g_doStackCaptures )
      DoStackCapture(Interface);
    CMILCOMBase::InternalRelease(v8);
    if ( v10 < 0 )
      goto LABEL_164;
  }
  if ( *((_QWORD *)a2 + 168) )
    TIFFContextsCleanup(a2);
  (*((void (__fastcall **)(struct tiff *))a2 + 131))(a2);
  TIFFSetDefaultCompressionState(a2);
  *((_DWORD *)a2 + 4) &= ~0x40u;
  TIFFFreeDirectory(a2);
  if ( (int)TIFFDefaultDirectory(a2) <= 0 || !*((_QWORD *)a2 + 155) )
    goto LABEL_163;
  TIFFSetField(a2, 284, 1);
  NextValue = GetNextValue(v48, &v46, v11);
  v13 = 4;
  if ( NextValue != 1 )
  {
    v14 = 0;
    while ( 1 )
    {
      if ( NextValue < 0 )
        goto LABEL_48;
      if ( v46.vt == 18 && (v14 || ***((_DWORD ***)a2 + 154) <= (unsigned int)v46.uiVal) )
        break;
LABEL_45:
      v18 = GetNextValue(v48, &v46, (struct tagPROPVARIANT *)v13);
      v13 = 4;
      NextValue = v18;
      if ( v18 == 1 )
        goto LABEL_48;
    }
    v15 = *((_QWORD *)a2 + 155) - 1LL;
    if ( v14 < v15 )
    {
      v16 = *((_QWORD *)a2 + 154);
      do
      {
        if ( **(_DWORD **)(v16 + 8LL * v14) == v46.uiVal )
          break;
        v17 = v14 + 1;
        if ( **(_DWORD **)(v16 + 8 * v17) > (unsigned int)v46.uiVal )
          break;
        v14 = v17;
      }
      while ( v17 < v15 );
    }
    if ( v46.uiVal > 0x11Cu )
    {
      if ( v46.uiVal != 322 && v46.uiVal != 323 )
      {
        if ( v46.uiVal == 324 )
          goto LABEL_47;
        if ( v46.uiVal == 325 )
        {
LABEL_33:
          *((_DWORD *)a2 + 18) |= 0x1000000u;
          goto LABEL_44;
        }
        if ( v46.uiVal != 338 && (unsigned int)v46.uiVal - 32997 > 1 )
        {
LABEL_44:
          PropVariantClear((PROPVARIANT *)&pvar);
          if ( NextValue < 0 )
            goto LABEL_48;
          goto LABEL_45;
        }
      }
    }
    else if ( v46.uiVal != 284 && v46.uiVal != 256 && v46.uiVal != 257 && v46.uiVal != 259 && v46.uiVal != 262 )
    {
      if ( v46.uiVal != 273 )
      {
        if ( v46.uiVal != 277 && v46.uiVal != 278 )
        {
          if ( v46.uiVal != 279 )
            goto LABEL_44;
          goto LABEL_33;
        }
        goto LABEL_42;
      }
LABEL_47:
      *((_DWORD *)a2 + 18) |= 0x2000000u;
      goto LABEL_44;
    }
LABEL_42:
    NextValue = ((__int64 (__fastcall *)(struct IWICMetadataReader *, _QWORD, struct tagPROPVARIANT *, struct tagPROPVARIANT *))a1->lpVtbl->GetValue)(
                  a1,
                  0,
                  &v46,
                  &pvar);
    if ( NextValue >= 0 )
      SetNormalTag(a2, v46.uiVal, &pvar, v14);
    goto LABEL_44;
  }
LABEL_48:
  if ( (*((_BYTE *)a2 + 72) & 2) == 0 || (*((_DWORD *)a2 + 18) & 0x2000000) == 0 )
    goto LABEL_163;
  if ( (*((_DWORD *)a2 + 18) & 0x10000) == 0 )
  {
    if ( *((_WORD *)a2 + 61) == 2 )
    {
      *((_WORD *)a2 + 65) = 3;
    }
    else if ( *((_WORD *)a2 + 61) == 5 )
    {
      *((_WORD *)a2 + 65) = 4;
    }
  }
  if ( !*((_WORD *)a2 + 65) )
    goto LABEL_163;
  if ( (*((_BYTE *)a2 + 72) & 4) != 0 )
  {
    *((_DWORD *)a2 + 57) = TIFFNumberOfTiles(a2);
    *((_DWORD *)a2 + 4) |= 0x400u;
  }
  else
  {
    *((_DWORD *)a2 + 57) = TIFFNumberOfStrips(a2);
    *((_DWORD *)a2 + 25) = *((_DWORD *)a2 + 22);
    *((_DWORD *)a2 + 26) = *((_DWORD *)a2 + 33);
    *((_DWORD *)a2 + 27) = *((_DWORD *)a2 + 24);
    *((_DWORD *)a2 + 4) &= ~0x400u;
  }
  v20 = *((_DWORD *)a2 + 57);
  if ( !v20 )
    goto LABEL_163;
  *((_DWORD *)a2 + 56) = v20;
  if ( *((_WORD *)a2 + 85) == 2 )
  {
    v19 = v20 % *((unsigned __int16 *)a2 + 65);
    *((_DWORD *)a2 + 56) = v20 / *((unsigned __int16 *)a2 + 65);
  }
  v21 = ((__int64 (__fastcall *)(struct IWICEnumMetadataItem *, __int64))v48->lpVtbl->Reset)(v48, v19);
  v10 = v21;
  if ( v21 < 0 )
  {
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_167;
LABEL_137:
    v36 = v21;
    goto LABEL_166;
  }
  v23 = 0;
  v24 = 0;
  while ( 1 )
  {
    v25 = GetNextValue(v48, &v46, v22);
    v26 = v25;
    if ( v25 < 0 || v25 == 1 )
      break;
    if ( v46.vt == 18 )
    {
      v27 = (_DWORD **)*((_QWORD *)a2 + 154);
      if ( v24 || **v27 <= (unsigned int)v46.uiVal )
      {
        v28 = 0;
        v29 = *((_QWORD *)a2 + 155) - 1LL;
        if ( v24 < v29 )
        {
          do
          {
            if ( *v27[v24] == v46.uiVal )
              break;
            v30 = v24 + 1;
            if ( *v27[v30] > (unsigned int)v46.uiVal )
              break;
            v24 = v30;
          }
          while ( v30 < v29 );
        }
        if ( **(_DWORD **)(*((_QWORD *)a2 + 154) + 8LL * v24) == v46.uiVal )
          v28 = *(_QWORD *)(*((_QWORD *)a2 + 154) + 8LL * v24);
        if ( v46.uiVal > 0x145u )
        {
          if ( v46.uiVal == 336 )
            goto LABEL_110;
          if ( v46.uiVal == 339 )
            goto LABEL_108;
          if ( v46.uiVal != 340 && v46.uiVal != 341 )
          {
            switch ( v46.uiVal )
            {
              case 0x212u:
LABEL_110:
                v26 = ((__int64 (__fastcall *)(struct IWICMetadataReader *, _QWORD, struct tagPROPVARIANT *, struct tagPROPVARIANT *))a1->lpVtbl->GetValue)(
                        a1,
                        0,
                        &v46,
                        &pvar);
                if ( v26 >= 0 )
                  WICTIFFFetchShortPair(a2, v46.uiVal, &pvar);
                goto LABEL_112;
              case 0x214u:
                v26 = ((__int64 (__fastcall *)(struct IWICMetadataReader *, _QWORD, struct tagPROPVARIANT *, struct tagPROPVARIANT *))a1->lpVtbl->GetValue)(
                        a1,
                        0,
                        &v46,
                        &pvar);
                if ( v26 >= 0 )
                  WICTIFFFetchRefBlackWhite(a2, &pvar);
                goto LABEL_112;
              case 0x80E4u:
LABEL_108:
                v26 = ((__int64 (__fastcall *)(struct IWICMetadataReader *, _QWORD, struct tagPROPVARIANT *, struct tagPROPVARIANT *))a1->lpVtbl->GetValue)(
                        a1,
                        0,
                        &v46,
                        &pvar);
                if ( v26 >= 0 )
                  WICTIFFFetchMultichannelTag(a2, v46.uiVal, &pvar);
                goto LABEL_112;
            }
LABEL_103:
            if ( v28 )
            {
              v26 = ((__int64 (__fastcall *)(struct IWICMetadataReader *, _QWORD, struct tagPROPVARIANT *, struct tagPROPVARIANT *))a1->lpVtbl->GetValue)(
                      a1,
                      0,
                      &v46,
                      &pvar);
              if ( v26 >= 0 )
                SetNormalTag(a2, v46.uiVal, &pvar, v24);
            }
          }
        }
        else
        {
          if ( v46.uiVal != 325 )
          {
            if ( v46.uiVal == 258 )
              goto LABEL_108;
            if ( v46.uiVal == 273 )
              goto LABEL_86;
            if ( v46.uiVal != 279 )
            {
              if ( v46.uiVal == 280 || v46.uiVal == 281 )
                goto LABEL_108;
              if ( v46.uiVal == 320 )
              {
                v23 = 1;
                goto LABEL_112;
              }
              if ( v46.uiVal != 324 )
                goto LABEL_103;
LABEL_86:
              v26 = ((__int64 (__fastcall *)(struct IWICMetadataReader *, _QWORD, struct tagPROPVARIANT *, struct tagPROPVARIANT *))a1->lpVtbl->GetValue)(
                      a1,
                      0,
                      &v46,
                      &pvar);
              if ( v26 >= 0 )
              {
                v31 = (void **)((char *)a2 + 232);
                goto LABEL_88;
              }
              goto LABEL_112;
            }
          }
          v26 = ((__int64 (__fastcall *)(struct IWICMetadataReader *, _QWORD, struct tagPROPVARIANT *, struct tagPROPVARIANT *))a1->lpVtbl->GetValue)(
                  a1,
                  0,
                  &v46,
                  &pvar);
          if ( v26 >= 0 )
          {
            v31 = (void **)((char *)a2 + 240);
LABEL_88:
            if ( *v31 )
            {
              TIFFfree(*v31);
              *v31 = 0;
            }
            v21 = WICTIFFFetchStripThing(a2, &pvar, *((unsigned int *)a2 + 57), v31);
            v10 = v21;
            if ( v21 < 0 )
            {
              if ( (_DWORD)g_doStackCaptures )
                goto LABEL_137;
              goto LABEL_167;
            }
          }
        }
LABEL_112:
        PropVariantClear((PROPVARIANT *)&pvar);
        if ( v26 < 0 )
          break;
      }
    }
  }
  if ( *((_WORD *)a2 + 61) == 3 && !v23 || !*((_QWORD *)a2 + 29) )
    goto LABEL_163;
  if ( *((_WORD *)a2 + 85) == 1
    && *((_WORD *)a2 + 61) == 6
    && (*((_DWORD *)a2 + 4) & 0x4000) == 0
    && *((char *)a2 + 76) >= 0 )
  {
    TIFFSetField(a2, 530, 2);
  }
  v32 = TIFFScanlineSize64(a2);
  if ( (*((_DWORD *)a2 + 18) & 0x1000000) == 0
    || (v33 = (_QWORD *)*((_QWORD *)a2 + 30)) == 0
    || *((_DWORD *)a2 + 57) == 1
    && **((_QWORD **)a2 + 29)
    && (!*v33
     || *((_WORD *)a2 + 60) == 1
     && (v34 = (*((__int64 (__fastcall **)(_QWORD))a2 + 152))(*((_QWORD *)a2 + 147)),
         v33 = (_QWORD *)*((_QWORD *)a2 + 30),
         *v33 > (unsigned __int64)(v34 - **((_QWORD **)a2 + 29)))
     || !*((_DWORD *)a2 + 3) && *((_WORD *)a2 + 60) == 1 && *v33 < v32 * (unsigned __int64)*((unsigned int *)a2 + 23)) )
  {
    v21 = WICEstimateByteCounts(a2);
    v10 = v21;
    if ( v21 >= 0 )
      goto LABEL_139;
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_167;
    goto LABEL_137;
  }
  for ( i = 0; i < *((_DWORD *)a2 + 57); ++i )
  {
    if ( (unsigned __int64)(*(_QWORD *)(*((_QWORD *)a2 + 30) + 8LL * i) - 1LL) > 0x7FFFFFFFFFFFFFFELL )
      goto LABEL_163;
  }
LABEL_139:
  v37 = (*((__int64 (__fastcall **)(_QWORD))a2 + 152))(*((_QWORD *)a2 + 147));
  for ( j = 0; j < *((_DWORD *)a2 + 57); ++j )
  {
    v39 = *(_QWORD *)(*((_QWORD *)a2 + 29) + 8LL * j);
    v40 = *((_QWORD *)a2 + 30);
    if ( v39 <= v37 )
    {
      v41 = v39 + *(_QWORD *)(v40 + 8LL * j);
      if ( v41 < v39 || v41 > v37 )
        *(_QWORD *)(v40 + 8LL * j) = v37 - v39;
    }
    else
    {
      *(_QWORD *)(v40 + 8LL * j) = 0;
    }
  }
  if ( *((char *)a2 + 72) >= 0 )
    TIFFSetField(a2, 259, 1);
  if ( *((_DWORD *)a2 + 57) == 1 && *((_WORD *)a2 + 60) == 1 && (*((_DWORD *)a2 + 4) & 0x8400) == 0x8000 )
    ChopUpSingleUncompressedStrip((__int64)a2);
  *((_DWORD *)a2 + 211) = -1;
  *((_DWORD *)a2 + 214) = -1;
  *((_DWORD *)a2 + 226) = -1;
  *((_DWORD *)a2 + 227) = -1;
  if ( (*((_DWORD *)a2 + 4) & 0x400) != 0 )
    v42 = TIFFTileRowSize(a2);
  else
    v42 = TIFFScanlineSize(a2);
  *((_QWORD *)a2 + 135) = v42;
  if ( v42 )
  {
    *((_QWORD *)a2 + 114) = -1;
    if ( (*((_DWORD *)a2 + 4) & 0x400) != 0 )
    {
      v44 = TIFFTileSize(a2);
      *((_QWORD *)a2 + 114) = v44;
      if ( v44 )
        goto LABEL_167;
      v43 = "%s: cannot handle zero tile size";
    }
    else
    {
      if ( TIFFStripSize(a2) )
        goto LABEL_167;
      v43 = "%s: cannot handle zero strip size";
    }
  }
  else
  {
    v43 = "%s: cannot handle zero scanline size";
  }
  TIFFErrorExt(*((_QWORD *)a2 + 147), "WICTIFFReadDir", v43, *(_QWORD *)a2);
LABEL_163:
  v10 = -2003292320;
LABEL_164:
  if ( (_DWORD)g_doStackCaptures )
  {
    v36 = v10;
LABEL_166:
    DoStackCapture(v36);
  }
LABEL_167:
  PropVariantClear((PROPVARIANT *)&v46);
  PropVariantClear((PROPVARIANT *)&pvar);
  if ( v48 )
    ((void (__fastcall *)(struct IWICEnumMetadataItem *))v48->lpVtbl->Release)(v48);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800a194c  push    rbp
0x1800a194e  push    rbx
0x1800a194f  push    rsi
0x1800a1950  push    rdi
0x1800a1951  push    r12
0x1800a1953  push    r13
0x1800a1955  push    r14
0x1800a1957  push    r15
0x1800a1959  mov     rbp, rsp
0x1800a195c  sub     rsp, 68h
0x1800a1960  xor     eax, eax
0x1800a1962  mov     [rdx+520h], rcx
0x1800a1969  mov     [rbp+var_28], rax
0x1800a196d  mov     rdi, rdx
0x1800a1970  mov     [rbp+var_10], rax
0x1800a1974  lea     rdx, [rbp+arg_0]
0x1800a1978  mov     rax, [rcx]
0x1800a197b  xorps   xmm0, xmm0
0x1800a197e  xorps   xmm1, xmm1
0x1800a1981  xor     r14d, r14d
0x1800a1984  mov     r12, rcx
0x1800a1987  mov     [rbp+arg_0], r14
0x1800a198b  movups  xmmword ptr [rbp+var_38], xmm0
0x1800a198f  mov     rax, [rax+40h]
0x1800a1993  movups  xmmword ptr [rbp+pvar], xmm1
0x1800a1997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a199c  test    eax, eax
0x1800a199e  jns     short loc_1800A1A0A
0x1800a19a0  lea     ecx, [r14+68h]; Size
0x1800a19a4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800a19a9  test    rax, rax
0x1800a19ac  jz      loc_1800A1B55
0x1800a19b2  mov     rdx, r12; struct IWICMetadataReader *
0x1800a19b5  mov     rcx, rax; this
0x1800a19b8  call    ??0CEnumMetadataItem@@QEAA@PEAUIWICMetadataReader@@@Z; CEnumMetadataItem::CEnumMetadataItem(IWICMetadataReader *)
0x1800a19bd  mov     rsi, rax
0x1800a19c0  test    rax, rax
0x1800a19c3  jz      loc_1800A1B55
0x1800a19c9  mov     rcx, rax; this
0x1800a19cc  call    ?InternalAddRef@CMILCOMBase@@QEAAKXZ; CMILCOMBase::InternalAddRef(void)
0x1800a19d1  lea     r8, [rbp+arg_0]; void **
0x1800a19d5  mov     rcx, rsi; this
0x1800a19d8  lea     rdx, IID_IWICEnumMetadataItem; struct _GUID *
0x1800a19df  call    ?InternalQueryInterface@CMILCOMBase@@QEAAJAEBU_GUID@@PEAPEAX@Z; CMILCOMBase::InternalQueryInterface(_GUID const &,void * *)
0x1800a19e4  mov     ebx, eax
0x1800a19e6  test    eax, eax
0x1800a19e8  jns     short loc_1800A19FA
0x1800a19ea  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x1800a19f1  jz      short loc_1800A19FA
0x1800a19f3  mov     ecx, eax; int
0x1800a19f5  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800a19fa  mov     rcx, rsi; this
0x1800a19fd  call    ?InternalRelease@CMILCOMBase@@QEAAKXZ; CMILCOMBase::InternalRelease(void)
0x1800a1a02  test    ebx, ebx
0x1800a1a04  js      loc_1800A227F
0x1800a1a0a  cmp     [rdi+540h], r14
0x1800a1a11  jz      short loc_1800A1A1B
0x1800a1a13  mov     rcx, rdi
0x1800a1a16  call    TIFFContextsCleanup
0x1800a1a1b  mov     rax, [rdi+418h]
0x1800a1a22  mov     rcx, rdi
0x1800a1a25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1a2a  mov     rcx, rdi
0x1800a1a2d  call    _TIFFSetDefaultCompressionState
0x1800a1a32  and     dword ptr [rdi+10h], 0FFFFFFBFh
0x1800a1a36  mov     rcx, rdi
0x1800a1a39  call    TIFFFreeDirectory
0x1800a1a3e  mov     rcx, rdi
0x1800a1a41  call    TIFFDefaultDirectory
0x1800a1a46  test    eax, eax
0x1800a1a48  jle     loc_1800A227A
0x1800a1a4e  cmp     [rdi+4D8h], r14
0x1800a1a55  jz      loc_1800A227A
0x1800a1a5b  mov     r15d, 11Ch
0x1800a1a61  mov     r8d, 1
0x1800a1a67  mov     edx, r15d
0x1800a1a6a  mov     rcx, rdi
0x1800a1a6d  call    TIFFSetField
0x1800a1a72  mov     rcx, [rbp+arg_0]; struct IWICEnumMetadataItem *
0x1800a1a76  lea     rdx, [rbp+var_38]; struct tagPROPVARIANT *
0x1800a1a7a  call    ?GetNextValue@@YAJPEAUIWICEnumMetadataItem@@PEAUtagPROPVARIANT@@1@Z; GetNextValue(IWICEnumMetadataItem *,tagPROPVARIANT *,tagPROPVARIANT *)
0x1800a1a7f  mov     esi, 2
0x1800a1a84  mov     ebx, eax
0x1800a1a86  mov     r13d, 2000000h
0x1800a1a8c  lea     r9d, [rsi+1]
0x1800a1a90  lea     r8d, [rsi+2]
0x1800a1a94  cmp     eax, 1
0x1800a1a97  jz      loc_1800A1C20
0x1800a1a9d  mov     esi, r14d
0x1800a1aa0  test    ebx, ebx
0x1800a1aa2  js      loc_1800A1C1B
0x1800a1aa8  cmp     word ptr [rbp+var_38], 12h
0x1800a1aad  jnz     loc_1800A1BE7
0x1800a1ab3  movzx   edx, word ptr [rbp+var_38+8]
0x1800a1ab7  test    esi, esi
0x1800a1ab9  jnz     short loc_1800A1ACD
0x1800a1abb  mov     rax, [rdi+4D0h]
0x1800a1ac2  mov     rcx, [rax]
0x1800a1ac5  cmp     [rcx], edx
0x1800a1ac7  ja      loc_1800A1BE7
0x1800a1acd  mov     r11, [rdi+4D8h]
0x1800a1ad4  dec     r11
0x1800a1ad7  mov     eax, esi
0x1800a1ad9  cmp     rax, r11
0x1800a1adc  jnb     short loc_1800A1B0E
0x1800a1ade  mov     r10, [rdi+4D0h]
0x1800a1ae5  mov     eax, esi
0x1800a1ae7  mov     rcx, [r10+rax*8]
0x1800a1aeb  cmp     [rcx], edx
0x1800a1aed  jz      short loc_1800A1B04
0x1800a1aef  lea     ecx, [rsi+1]
0x1800a1af2  mov     rax, [r10+rcx*8]
0x1800a1af6  mov     r9d, ecx
0x1800a1af9  cmp     [rax], edx
0x1800a1afb  ja      short loc_1800A1B04
0x1800a1afd  mov     esi, ecx
0x1800a1aff  cmp     r9, r11
0x1800a1b02  jb      short loc_1800A1AE5
0x1800a1b04  mov     r8d, 4
0x1800a1b0a  lea     r9d, [r8-1]
0x1800a1b0e  mov     ecx, edx
0x1800a1b10  cmp     edx, r15d
0x1800a1b13  ja      short loc_1800A1B73
0x1800a1b15  jz      loc_1800A1BA0
0x1800a1b1b  sub     ecx, 100h
0x1800a1b21  jz      short loc_1800A1BA0
0x1800a1b23  sub     ecx, 1
0x1800a1b26  jz      short loc_1800A1BA0
0x1800a1b28  sub     ecx, 2
0x1800a1b2b  jz      short loc_1800A1BA0
0x1800a1b2d  sub     ecx, r9d
0x1800a1b30  jz      short loc_1800A1BA0
0x1800a1b32  sub     ecx, 0Bh
0x1800a1b35  jz      loc_1800A1C0B
0x1800a1b3b  sub     ecx, r8d
0x1800a1b3e  jz      short loc_1800A1BA0
0x1800a1b40  sub     ecx, 1
0x1800a1b43  jz      short loc_1800A1BA0
0x1800a1b45  cmp     ecx, 1
0x1800a1b48  jnz     loc_1800A1BD3
0x1800a1b4e  bts     dword ptr [rdi+48h], 18h
0x1800a1b53  jmp     short loc_1800A1BD3
0x1800a1b55  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x1800a1b5c  mov     ebx, 8007000Eh
0x1800a1b61  jz      loc_1800A228F
0x1800a1b67  mov     ecx, ebx; int
0x1800a1b69  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800a1b6e  jmp     loc_1800A227F
0x1800a1b73  sub     ecx, 142h
0x1800a1b79  jz      short loc_1800A1BA0
0x1800a1b7b  sub     ecx, 1
0x1800a1b7e  jz      short loc_1800A1BA0
0x1800a1b80  sub     ecx, 1
0x1800a1b83  jz      loc_1800A1C0B
0x1800a1b89  sub     ecx, 1
0x1800a1b8c  jz      short loc_1800A1B4E
0x1800a1b8e  sub     ecx, 0Dh
0x1800a1b91  jz      short loc_1800A1BA0
0x1800a1b93  sub     ecx, 7F93h
0x1800a1b99  jz      short loc_1800A1BA0
0x1800a1b9b  cmp     ecx, 1
0x1800a1b9e  jnz     short loc_1800A1BD3
0x1800a1ba0  mov     rax, [r12]
0x1800a1ba4  lea     r9, [rbp+pvar]
0x1800a1ba8  lea     r8, [rbp+var_38]
0x1800a1bac  xor     edx, edx
0x1800a1bae  mov     rcx, r12
0x1800a1bb1  mov     rax, [rax+38h]
0x1800a1bb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1bba  mov     ebx, eax
0x1800a1bbc  test    eax, eax
0x1800a1bbe  js      short loc_1800A1BD3
0x1800a1bc0  movzx   edx, word ptr [rbp+var_38+8]; unsigned __int16
0x1800a1bc4  lea     r8, [rbp+pvar]; struct tagPROPVARIANT *
0x1800a1bc8  mov     r9d, esi; unsigned int
0x1800a1bcb  mov     rcx, rdi; struct tiff *
0x1800a1bce  call    ?SetNormalTag@@YAJPEAUtiff@@GPEAUtagPROPVARIANT@@I@Z; SetNormalTag(tiff *,ushort,tagPROPVARIANT *,uint)
0x1800a1bd3  lea     rcx, [rbp+pvar]; pvar
0x1800a1bd7  call    cs:__imp_PropVariantClear
0x1800a1bde  nop     dword ptr [rax+rax+00h]
0x1800a1be3  test    ebx, ebx
0x1800a1be5  js      short loc_1800A1C11
0x1800a1be7  mov     rcx, [rbp+arg_0]; struct IWICEnumMetadataItem *
0x1800a1beb  lea     rdx, [rbp+var_38]; struct tagPROPVARIANT *
0x1800a1bef  call    ?GetNextValue@@YAJPEAUIWICEnumMetadataItem@@PEAUtagPROPVARIANT@@1@Z; GetNextValue(IWICEnumMetadataItem *,tagPROPVARIANT *,tagPROPVARIANT *)
0x1800a1bf4  mov     r8d, 4
0x1800a1bfa  mov     ebx, eax
0x1800a1bfc  lea     r9d, [r8-1]
0x1800a1c00  cmp     eax, 1
0x1800a1c03  jnz     loc_1800A1AA0
0x1800a1c09  jmp     short loc_1800A1C1B
0x1800a1c0b  or      [rdi+48h], r13d
0x1800a1c0f  jmp     short loc_1800A1BD3
0x1800a1c11  mov     r8d, 4
0x1800a1c17  lea     r9d, [r8-1]
0x1800a1c1b  mov     esi, 2
0x1800a1c20  test    [rdi+48h], sil
0x1800a1c24  jbe     loc_1800A227A
0x1800a1c2a  test    [rdi+48h], r13d
0x1800a1c2e  jbe     loc_1800A227A
0x1800a1c34  test    dword ptr [rdi+48h], 10000h
0x1800a1c3b  jnz     short loc_1800A1C5C
0x1800a1c3d  cmp     [rdi+7Ah], si
0x1800a1c41  jnz     short loc_1800A1C4D
0x1800a1c43  mov     [rdi+82h], r9w
0x1800a1c4b  jmp     short loc_1800A1C5C
0x1800a1c4d  cmp     word ptr [rdi+7Ah], 5
0x1800a1c52  jnz     short loc_1800A1C5C
0x1800a1c54  mov     [rdi+82h], r8w
0x1800a1c5c  cmp     r14w, [rdi+82h]
0x1800a1c64  jz      loc_1800A227A
0x1800a1c6a  mov     rcx, rdi
0x1800a1c6d  test    [rdi+48h], r8b
0x1800a1c71  jnz     short loc_1800A1C9A
0x1800a1c73  call    TIFFNumberOfStrips
0x1800a1c78  mov     [rdi+0E4h], eax
0x1800a1c7e  mov     eax, [rdi+58h]
0x1800a1c81  mov     [rdi+64h], eax
0x1800a1c84  mov     eax, [rdi+84h]
0x1800a1c8a  mov     [rdi+68h], eax
0x1800a1c8d  mov     eax, [rdi+60h]
0x1800a1c90  mov     [rdi+6Ch], eax
0x1800a1c93  btr     dword ptr [rdi+10h], 0Ah
0x1800a1c98  jmp     short loc_1800A1CAA
0x1800a1c9a  call    TIFFNumberOfTiles
0x1800a1c9f  mov     [rdi+0E4h], eax
0x1800a1ca5  bts     dword ptr [rdi+10h], 0Ah
0x1800a1caa  mov     eax, [rdi+0E4h]
0x1800a1cb0  test    eax, eax
0x1800a1cb2  jz      loc_1800A227A
0x1800a1cb8  mov     [rdi+0E0h], eax
0x1800a1cbe  cmp     [rdi+0AAh], si
0x1800a1cc5  jnz     short loc_1800A1CD8
0x1800a1cc7  movzx   ecx, word ptr [rdi+82h]
0x1800a1cce  xor     edx, edx
0x1800a1cd0  div     ecx
0x1800a1cd2  mov     [rdi+0E0h], eax
0x1800a1cd8  mov     rcx, [rbp+arg_0]
0x1800a1cdc  mov     rax, [rcx]
0x1800a1cdf  mov     rax, [rax+28h]
0x1800a1ce3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1ce8  mov     ebx, eax
0x1800a1cea  test    eax, eax
0x1800a1cec  jns     short loc_1800A1D03
0x1800a1cee  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x1800a1cf5  jnz     loc_1800A2128
0x1800a1cfb  test    eax, eax
0x1800a1cfd  js      loc_1800A228F
0x1800a1d03  mov     r13b, r14b
0x1800a1d06  mov     r15d, r14d
0x1800a1d09  mov     rcx, [rbp+arg_0]; struct IWICEnumMetadataItem *
0x1800a1d0d  lea     rdx, [rbp+var_38]; struct tagPROPVARIANT *
0x1800a1d11  call    ?GetNextValue@@YAJPEAUIWICEnumMetadataItem@@PEAUtagPROPVARIANT@@1@Z; GetNextValue(IWICEnumMetadataItem *,tagPROPVARIANT *,tagPROPVARIANT *)
0x1800a1d16  mov     r9d, 6
0x1800a1d1c  mov     r14d, eax
0x1800a1d1f  test    eax, eax
0x1800a1d21  js      loc_1800A1FF0
0x1800a1d27  cmp     eax, 1
0x1800a1d2a  jz      loc_1800A1FF0
0x1800a1d30  cmp     word ptr [rbp+var_38], 12h
0x1800a1d35  jnz     short loc_1800A1D09
0x1800a1d37  movzx   r11d, word ptr [rbp+var_38+8]
0x1800a1d3c  mov     rdx, [rdi+4D0h]
0x1800a1d43  test    r15d, r15d
0x1800a1d46  jnz     short loc_1800A1D50
0x1800a1d48  mov     rcx, [rdx]
0x1800a1d4b  cmp     [rcx], r11d
0x1800a1d4e  ja      short loc_1800A1D09
0x1800a1d50  mov     r10, [rdi+4D8h]
0x1800a1d57  xor     esi, esi
0x1800a1d59  dec     r10
0x1800a1d5c  mov     eax, r15d
0x1800a1d5f  cmp     rax, r10
0x1800a1d62  jnb     short loc_1800A1D8E
0x1800a1d64  mov     eax, r15d
0x1800a1d67  mov     rcx, [rdx+rax*8]
0x1800a1d6b  cmp     [rcx], r11d
0x1800a1d6e  jz      short loc_1800A1D88
0x1800a1d70  lea     ecx, [r15+1]
0x1800a1d74  mov     rax, [rdx+rcx*8]
0x1800a1d78  mov     r9d, ecx
0x1800a1d7b  cmp     [rax], r11d
0x1800a1d7e  ja      short loc_1800A1D88
0x1800a1d80  mov     r15d, ecx
0x1800a1d83  cmp     r9, r10
0x1800a1d86  jb      short loc_1800A1D64
0x1800a1d88  mov     r9d, 6
0x1800a1d8e  mov     rax, [rdi+4D0h]
0x1800a1d95  mov     r8d, r11d
0x1800a1d98  mov     ecx, r15d
0x1800a1d9b  mov     rdx, [rax+rcx*8]
0x1800a1d9f  mov     eax, 145h
0x1800a1da4  cmp     [rdx], r11d
0x1800a1da7  cmovz   rsi, rdx
0x1800a1dab  cmp     r11d, eax
0x1800a1dae  ja      loc_1800A1EB1
0x1800a1db4  jz      loc_1800A1E80
0x1800a1dba  sub     r8d, 102h
0x1800a1dc1  jz      loc_1800A1F6D
0x1800a1dc7  sub     r8d, 0Fh
  ... truncated ...
```
