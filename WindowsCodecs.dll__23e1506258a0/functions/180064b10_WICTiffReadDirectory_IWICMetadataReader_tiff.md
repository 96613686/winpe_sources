# WICTiffReadDirectory(IWICMetadataReader *,tiff *)

- ea: `0x180064b10`
- end: `0x18006547f`
- name: `?WICTiffReadDirectory@@YAJPEAUIWICMetadataReader@@PEAUtiff@@@Z`
- size: `2415`
- prototype: `__int64 __fastcall(struct IWICMetadataReader *, struct tiff *)`
- caller_count: `3`
- callee_count: `30`
- tags: `broker_com_uri`

## callers

- `0x180062e60`
- `0x1800a3828`
- `0x1801b2a10`

## callees

- `0x18001df64`
- `0x18003b2f0`
- `0x18003b320`
- `0x180040d80`
- `0x180064b10`
- `0x18009ad9c`
- `0x1800ab2b4`
- `0x1800adebc`
- `0x1800bb784`
- `0x1800e2b48`
- `0x18014e3b0`
- `0x18014e440`
- `0x18014e470`
- `0x18014e5e0`
- `0x18014ee10`
- `0x18014ef80`
- `0x18014f300`
- `0x180152940`
- `0x180152a60`
- `0x180152b70`
- `0x18015a1d0`
- `0x18015a2b0`
- `0x18015b3d0`
- `0x1801b67a4`
- `0x1801b691c`
- `0x1801b6978`
- `0x1801b6e84`
- `0x1801b6ef0`
- `0x1801bed3c`
- `0x1801ca010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180064d97`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006518f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180065447`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180065451`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180064d97`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006518f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180065447`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180065451`

## string_xrefs

- `0x18006541b`: `WICTIFFReadDir`

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
  unsigned __int64 v32; // rsi
  _QWORD *v33; // rdx
  __int64 v34; // rax
  unsigned int i; // r8d
  int v36; // ecx
  __int64 v37; // rdx
  unsigned __int64 v38; // r10
  __int64 j; // r8
  unsigned __int64 v40; // r9
  __int64 v41; // rcx
  unsigned __int64 v42; // r11
  __int64 v43; // rax
  const char *v44; // r8
  __int64 v45; // rax
  struct tagPROPVARIANT v47; // [rsp+30h] [rbp-38h] BYREF
  struct tagPROPVARIANT pvar; // [rsp+48h] [rbp-20h] BYREF
  struct IWICEnumMetadataItem *v49; // [rsp+B0h] [rbp+48h] BYREF

  *((_QWORD *)a2 + 164) = a1;
  lpVtbl = a1->lpVtbl;
  v49 = 0;
  memset(&v47, 0, sizeof(v47));
  GetEnumerator = lpVtbl->GetEnumerator;
  memset(&pvar, 0, sizeof(pvar));
  if ( ((int (__fastcall *)(struct IWICMetadataReader *, struct IWICEnumMetadataItem **))GetEnumerator)(a1, &v49) < 0 )
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
    Interface = CMILCOMBase::InternalQueryInterface(v8, &IID_IWICEnumMetadataItem, (void **)&v49);
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
  NextValue = GetNextValue(v49, &v47, v11);
  v13 = 4;
  if ( NextValue != 1 )
  {
    v14 = 0;
    while ( 1 )
    {
      if ( NextValue < 0 )
        goto LABEL_48;
      if ( v47.vt == 18 && (v14 || ***((_DWORD ***)a2 + 154) <= (unsigned int)v47.uiVal) )
        break;
LABEL_45:
      v18 = GetNextValue(v49, &v47, (struct tagPROPVARIANT *)v13);
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
        if ( **(_DWORD **)(v16 + 8LL * v14) == v47.uiVal )
          break;
        v17 = v14 + 1;
        if ( **(_DWORD **)(v16 + 8 * v17) > (unsigned int)v47.uiVal )
          break;
        v14 = v17;
      }
      while ( v17 < v15 );
    }
    if ( v47.uiVal > 0x11Cu )
    {
      if ( v47.uiVal != 322 && v47.uiVal != 323 )
      {
        if ( v47.uiVal == 324 )
          goto LABEL_47;
        if ( v47.uiVal == 325 )
        {
LABEL_33:
          *((_DWORD *)a2 + 18) |= 0x1000000u;
          goto LABEL_44;
        }
        if ( v47.uiVal != 338 && (unsigned int)v47.uiVal - 32997 > 1 )
        {
LABEL_44:
          PropVariantClear((PROPVARIANT *)&pvar);
          if ( NextValue < 0 )
            goto LABEL_48;
          goto LABEL_45;
        }
      }
    }
    else if ( v47.uiVal != 284 && v47.uiVal != 256 && v47.uiVal != 257 && v47.uiVal != 259 && v47.uiVal != 262 )
    {
      if ( v47.uiVal != 273 )
      {
        if ( v47.uiVal != 277 && v47.uiVal != 278 )
        {
          if ( v47.uiVal != 279 )
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
                  &v47,
                  &pvar);
    if ( NextValue >= 0 )
      SetNormalTag(a2, v47.uiVal, &pvar, v14);
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
  v21 = ((__int64 (__fastcall *)(struct IWICEnumMetadataItem *, __int64))v49->lpVtbl->Reset)(v49, v19);
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
    v25 = GetNextValue(v49, &v47, v22);
    v26 = v25;
    if ( v25 < 0 || v25 == 1 )
      break;
    if ( v47.vt == 18 )
    {
      v27 = (_DWORD **)*((_QWORD *)a2 + 154);
      if ( v24 || **v27 <= (unsigned int)v47.uiVal )
      {
        v28 = 0;
        v29 = *((_QWORD *)a2 + 155) - 1LL;
        if ( v24 < v29 )
        {
          do
          {
            if ( *v27[v24] == v47.uiVal )
              break;
            v30 = v24 + 1;
            if ( *v27[v30] > (unsigned int)v47.uiVal )
              break;
            v24 = v30;
          }
          while ( v30 < v29 );
        }
        if ( **(_DWORD **)(*((_QWORD *)a2 + 154) + 8LL * v24) == v47.uiVal )
          v28 = *(_QWORD *)(*((_QWORD *)a2 + 154) + 8LL * v24);
        if ( v47.uiVal > 0x145u )
        {
          if ( v47.uiVal == 336 )
            goto LABEL_110;
          if ( v47.uiVal == 339 )
            goto LABEL_108;
          if ( v47.uiVal != 340 && v47.uiVal != 341 )
          {
            switch ( v47.uiVal )
            {
              case 0x212u:
LABEL_110:
                v26 = ((__int64 (__fastcall *)(struct IWICMetadataReader *, _QWORD, struct tagPROPVARIANT *, struct tagPROPVARIANT *))a1->lpVtbl->GetValue)(
                        a1,
                        0,
                        &v47,
                        &pvar);
                if ( v26 >= 0 )
                  WICTIFFFetchShortPair(a2, v47.uiVal, &pvar);
                goto LABEL_112;
              case 0x214u:
                v26 = ((__int64 (__fastcall *)(struct IWICMetadataReader *, _QWORD, struct tagPROPVARIANT *, struct tagPROPVARIANT *))a1->lpVtbl->GetValue)(
                        a1,
                        0,
                        &v47,
                        &pvar);
                if ( v26 >= 0 )
                  WICTIFFFetchRefBlackWhite(a2, &pvar);
                goto LABEL_112;
              case 0x80E4u:
LABEL_108:
                v26 = ((__int64 (__fastcall *)(struct IWICMetadataReader *, _QWORD, struct tagPROPVARIANT *, struct tagPROPVARIANT *))a1->lpVtbl->GetValue)(
                        a1,
                        0,
                        &v47,
                        &pvar);
                if ( v26 >= 0 )
                  WICTIFFFetchMultichannelTag(a2, v47.uiVal, &pvar);
                goto LABEL_112;
            }
LABEL_103:
            if ( v28 )
            {
              v26 = ((__int64 (__fastcall *)(struct IWICMetadataReader *, _QWORD, struct tagPROPVARIANT *, struct tagPROPVARIANT *))a1->lpVtbl->GetValue)(
                      a1,
                      0,
                      &v47,
                      &pvar);
              if ( v26 >= 0 )
                SetNormalTag(a2, v47.uiVal, &pvar, v24);
            }
          }
        }
        else
        {
          if ( v47.uiVal != 325 )
          {
            if ( v47.uiVal == 258 )
              goto LABEL_108;
            if ( v47.uiVal == 273 )
              goto LABEL_86;
            if ( v47.uiVal != 279 )
            {
              if ( v47.uiVal == 280 || v47.uiVal == 281 )
                goto LABEL_108;
              if ( v47.uiVal == 320 )
              {
                v23 = 1;
                goto LABEL_112;
              }
              if ( v47.uiVal != 324 )
                goto LABEL_103;
LABEL_86:
              v26 = ((__int64 (__fastcall *)(struct IWICMetadataReader *, _QWORD, struct tagPROPVARIANT *, struct tagPROPVARIANT *))a1->lpVtbl->GetValue)(
                      a1,
                      0,
                      &v47,
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
                  &v47,
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
  v32 = TIFFScanlineSize64((__int64)a2);
  if ( (*((_DWORD *)a2 + 18) & 0x1000000) == 0
    || (v33 = (_QWORD *)*((_QWORD *)a2 + 30)) == 0
    || *((_DWORD *)a2 + 57) == 1
    && **((_QWORD **)a2 + 29)
    && (!*v33
     || *((_WORD *)a2 + 60) == 1
     && (v34 = (*((__int64 (__fastcall **)(_QWORD))a2 + 152))(*((_QWORD *)a2 + 147)),
         v33 = (_QWORD *)*((_QWORD *)a2 + 30),
         *v33 > (unsigned __int64)(v34 - **((_QWORD **)a2 + 29)))
     || !*((_DWORD *)a2 + 3) && *((_WORD *)a2 + 60) == 1 && *v33 < v32 * *((unsigned int *)a2 + 23)) )
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
  v38 = (*((__int64 (__fastcall **)(_QWORD))a2 + 152))(*((_QWORD *)a2 + 147));
  for ( j = 0; (unsigned int)j < *((_DWORD *)a2 + 57); j = (unsigned int)(j + 1) )
  {
    v37 = (unsigned int)j;
    v40 = *(_QWORD *)(*((_QWORD *)a2 + 29) + 8LL * (unsigned int)j);
    v41 = *((_QWORD *)a2 + 30);
    if ( v40 <= v38 )
    {
      v42 = v40 + *(_QWORD *)(v41 + 8LL * (unsigned int)j);
      if ( v42 < v40 || v42 > v38 )
        *(_QWORD *)(v41 + 8LL * (unsigned int)j) = v38 - v40;
    }
    else
    {
      *(_QWORD *)(v41 + 8LL * (unsigned int)j) = 0;
    }
  }
  if ( *((char *)a2 + 72) >= 0 )
    TIFFSetField(a2, 259, 1);
  if ( *((_DWORD *)a2 + 57) == 1 && *((_WORD *)a2 + 60) == 1 && (*((_DWORD *)a2 + 4) & 0x8400) == 0x8000 )
    ChopUpSingleUncompressedStrip(a2, v37, j);
  *((_DWORD *)a2 + 211) = -1;
  *((_DWORD *)a2 + 214) = -1;
  *((_DWORD *)a2 + 226) = -1;
  *((_DWORD *)a2 + 227) = -1;
  if ( (*((_DWORD *)a2 + 4) & 0x400) != 0 )
    v43 = TIFFTileRowSize(a2);
  else
    v43 = TIFFScanlineSize(a2);
  *((_QWORD *)a2 + 135) = v43;
  if ( v43 )
  {
    *((_QWORD *)a2 + 114) = -1;
    if ( (*((_DWORD *)a2 + 4) & 0x400) != 0 )
    {
      v45 = TIFFTileSize(a2);
      *((_QWORD *)a2 + 114) = v45;
      if ( v45 )
        goto LABEL_167;
      v44 = "%s: cannot handle zero tile size";
    }
    else
    {
      if ( TIFFStripSize(a2) )
        goto LABEL_167;
      v44 = "%s: cannot handle zero strip size";
    }
  }
  else
  {
    v44 = "%s: cannot handle zero scanline size";
  }
  TIFFErrorExt(*((_QWORD *)a2 + 147), "WICTIFFReadDir", v44, *(_QWORD *)a2);
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
  PropVariantClear((PROPVARIANT *)&v47);
  PropVariantClear((PROPVARIANT *)&pvar);
  if ( v49 )
    ((void (__fastcall *)(struct IWICEnumMetadataItem *))v49->lpVtbl->Release)(v49);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180064b10  push    rbp
0x180064b12  push    rbx
0x180064b13  push    rsi
0x180064b14  push    rdi
0x180064b15  push    r12
0x180064b17  push    r13
0x180064b19  push    r14
0x180064b1b  push    r15
0x180064b1d  mov     rbp, rsp
0x180064b20  sub     rsp, 68h
0x180064b24  xor     eax, eax
0x180064b26  mov     [rdx+520h], rcx
0x180064b2d  mov     [rbp+var_28], rax
0x180064b31  mov     rdi, rdx
0x180064b34  mov     [rbp+var_10], rax
0x180064b38  lea     rdx, [rbp+arg_0]
0x180064b3c  mov     rax, [rcx]
0x180064b3f  xorps   xmm0, xmm0
0x180064b42  xorps   xmm1, xmm1
0x180064b45  xor     r14d, r14d
0x180064b48  mov     r12, rcx
0x180064b4b  mov     [rbp+arg_0], r14
0x180064b4f  movups  xmmword ptr [rbp+var_38], xmm0
0x180064b53  mov     rax, [rax+40h]
0x180064b57  movups  xmmword ptr [rbp+pvar], xmm1
0x180064b5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064b60  test    eax, eax
0x180064b62  jns     short loc_180064BCE
0x180064b64  lea     ecx, [r14+68h]; Size
0x180064b68  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180064b6d  test    rax, rax
0x180064b70  jz      loc_180064D19
0x180064b76  mov     rdx, r12; struct IWICMetadataReader *
0x180064b79  mov     rcx, rax; this
0x180064b7c  call    ??0CEnumMetadataItem@@QEAA@PEAUIWICMetadataReader@@@Z; CEnumMetadataItem::CEnumMetadataItem(IWICMetadataReader *)
0x180064b81  mov     rsi, rax
0x180064b84  test    rax, rax
0x180064b87  jz      loc_180064D19
0x180064b8d  mov     rcx, rax; this
0x180064b90  call    ?InternalAddRef@CMILCOMBase@@QEAAKXZ; CMILCOMBase::InternalAddRef(void)
0x180064b95  lea     r8, [rbp+arg_0]; void **
0x180064b99  mov     rcx, rsi; this
0x180064b9c  lea     rdx, IID_IWICEnumMetadataItem; struct _GUID *
0x180064ba3  call    ?InternalQueryInterface@CMILCOMBase@@QEAAJAEBU_GUID@@PEAPEAX@Z; CMILCOMBase::InternalQueryInterface(_GUID const &,void * *)
0x180064ba8  mov     ebx, eax
0x180064baa  test    eax, eax
0x180064bac  jns     short loc_180064BBE
0x180064bae  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x180064bb5  jz      short loc_180064BBE
0x180064bb7  mov     ecx, eax; int
0x180064bb9  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180064bbe  mov     rcx, rsi; this
0x180064bc1  call    ?InternalRelease@CMILCOMBase@@QEAAKXZ; CMILCOMBase::InternalRelease(void)
0x180064bc6  test    ebx, ebx
0x180064bc8  js      loc_180065433
0x180064bce  cmp     [rdi+540h], r14
0x180064bd5  jz      short loc_180064BDF
0x180064bd7  mov     rcx, rdi
0x180064bda  call    TIFFContextsCleanup
0x180064bdf  mov     rax, [rdi+418h]
0x180064be6  mov     rcx, rdi
0x180064be9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064bee  mov     rcx, rdi
0x180064bf1  call    _TIFFSetDefaultCompressionState
0x180064bf6  and     dword ptr [rdi+10h], 0FFFFFFBFh
0x180064bfa  mov     rcx, rdi
0x180064bfd  call    TIFFFreeDirectory
0x180064c02  mov     rcx, rdi
0x180064c05  call    TIFFDefaultDirectory
0x180064c0a  test    eax, eax
0x180064c0c  jle     loc_18006542E
0x180064c12  cmp     [rdi+4D8h], r14
0x180064c19  jz      loc_18006542E
0x180064c1f  mov     r15d, 11Ch
0x180064c25  mov     r8d, 1
0x180064c2b  mov     edx, r15d
0x180064c2e  mov     rcx, rdi
0x180064c31  call    TIFFSetField
0x180064c36  mov     rcx, [rbp+arg_0]; struct IWICEnumMetadataItem *
0x180064c3a  lea     rdx, [rbp+var_38]; struct tagPROPVARIANT *
0x180064c3e  call    ?GetNextValue@@YAJPEAUIWICEnumMetadataItem@@PEAUtagPROPVARIANT@@1@Z; GetNextValue(IWICEnumMetadataItem *,tagPROPVARIANT *,tagPROPVARIANT *)
0x180064c43  mov     esi, 2
0x180064c48  mov     ebx, eax
0x180064c4a  mov     r13d, 2000000h
0x180064c50  lea     r9d, [rsi+1]
0x180064c54  lea     r8d, [rsi+2]
0x180064c58  cmp     eax, 1
0x180064c5b  jz      loc_180064DDA
0x180064c61  mov     esi, r14d
0x180064c64  test    ebx, ebx
0x180064c66  js      loc_180064DD5
0x180064c6c  cmp     word ptr [rbp+var_38], 12h
0x180064c71  jnz     loc_180064DA1
0x180064c77  movzx   edx, word ptr [rbp+var_38+8]
0x180064c7b  test    esi, esi
0x180064c7d  jnz     short loc_180064C91
0x180064c7f  mov     rax, [rdi+4D0h]
0x180064c86  mov     rcx, [rax]
0x180064c89  cmp     [rcx], edx
0x180064c8b  ja      loc_180064DA1
0x180064c91  mov     r11, [rdi+4D8h]
0x180064c98  dec     r11
0x180064c9b  mov     eax, esi
0x180064c9d  cmp     rax, r11
0x180064ca0  jnb     short loc_180064CD2
0x180064ca2  mov     r10, [rdi+4D0h]
0x180064ca9  mov     eax, esi
0x180064cab  mov     rcx, [r10+rax*8]
0x180064caf  cmp     [rcx], edx
0x180064cb1  jz      short loc_180064CC8
0x180064cb3  lea     ecx, [rsi+1]
0x180064cb6  mov     rax, [r10+rcx*8]
0x180064cba  mov     r9d, ecx
0x180064cbd  cmp     [rax], edx
0x180064cbf  ja      short loc_180064CC8
0x180064cc1  mov     esi, ecx
0x180064cc3  cmp     r9, r11
0x180064cc6  jb      short loc_180064CA9
0x180064cc8  mov     r8d, 4
0x180064cce  lea     r9d, [r8-1]
0x180064cd2  mov     ecx, edx
0x180064cd4  cmp     edx, r15d
0x180064cd7  ja      short loc_180064D37
0x180064cd9  jz      loc_180064D60
0x180064cdf  sub     ecx, 100h
0x180064ce5  jz      short loc_180064D60
0x180064ce7  sub     ecx, 1
0x180064cea  jz      short loc_180064D60
0x180064cec  sub     ecx, 2
0x180064cef  jz      short loc_180064D60
0x180064cf1  sub     ecx, r9d
0x180064cf4  jz      short loc_180064D60
0x180064cf6  sub     ecx, 0Bh
0x180064cf9  jz      loc_180064DC5
0x180064cff  sub     ecx, r8d
0x180064d02  jz      short loc_180064D60
0x180064d04  sub     ecx, 1
0x180064d07  jz      short loc_180064D60
0x180064d09  cmp     ecx, 1
0x180064d0c  jnz     loc_180064D93
0x180064d12  bts     dword ptr [rdi+48h], 18h
0x180064d17  jmp     short loc_180064D93
0x180064d19  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x180064d20  mov     ebx, 8007000Eh
0x180064d25  jz      loc_180065443
0x180064d2b  mov     ecx, ebx; int
0x180064d2d  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180064d32  jmp     loc_180065433
0x180064d37  sub     ecx, 142h
0x180064d3d  jz      short loc_180064D60
0x180064d3f  sub     ecx, 1
0x180064d42  jz      short loc_180064D60
0x180064d44  sub     ecx, 1
0x180064d47  jz      short loc_180064DC5
0x180064d49  sub     ecx, 1
0x180064d4c  jz      short loc_180064D12
0x180064d4e  sub     ecx, 0Dh
0x180064d51  jz      short loc_180064D60
0x180064d53  sub     ecx, 7F93h
0x180064d59  jz      short loc_180064D60
0x180064d5b  cmp     ecx, 1
0x180064d5e  jnz     short loc_180064D93
0x180064d60  mov     rax, [r12]
0x180064d64  lea     r9, [rbp+pvar]
0x180064d68  lea     r8, [rbp+var_38]
0x180064d6c  xor     edx, edx
0x180064d6e  mov     rcx, r12
0x180064d71  mov     rax, [rax+38h]
0x180064d75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064d7a  mov     ebx, eax
0x180064d7c  test    eax, eax
0x180064d7e  js      short loc_180064D93
0x180064d80  movzx   edx, word ptr [rbp+var_38+8]; unsigned __int16
0x180064d84  lea     r8, [rbp+pvar]; struct tagPROPVARIANT *
0x180064d88  mov     r9d, esi; unsigned int
0x180064d8b  mov     rcx, rdi; struct tiff *
0x180064d8e  call    ?SetNormalTag@@YAJPEAUtiff@@GPEAUtagPROPVARIANT@@I@Z; SetNormalTag(tiff *,ushort,tagPROPVARIANT *,uint)
0x180064d93  lea     rcx, [rbp+pvar]; pvar
0x180064d97  call    cs:__imp_PropVariantClear
0x180064d9d  test    ebx, ebx
0x180064d9f  js      short loc_180064DCB
0x180064da1  mov     rcx, [rbp+arg_0]; struct IWICEnumMetadataItem *
0x180064da5  lea     rdx, [rbp+var_38]; struct tagPROPVARIANT *
0x180064da9  call    ?GetNextValue@@YAJPEAUIWICEnumMetadataItem@@PEAUtagPROPVARIANT@@1@Z; GetNextValue(IWICEnumMetadataItem *,tagPROPVARIANT *,tagPROPVARIANT *)
0x180064dae  mov     r8d, 4
0x180064db4  mov     ebx, eax
0x180064db6  lea     r9d, [r8-1]
0x180064dba  cmp     eax, 1
0x180064dbd  jnz     loc_180064C64
0x180064dc3  jmp     short loc_180064DD5
0x180064dc5  or      [rdi+48h], r13d
0x180064dc9  jmp     short loc_180064D93
0x180064dcb  mov     r8d, 4
0x180064dd1  lea     r9d, [r8-1]
0x180064dd5  mov     esi, 2
0x180064dda  test    [rdi+48h], sil
0x180064dde  jbe     loc_18006542E
0x180064de4  test    [rdi+48h], r13d
0x180064de8  jbe     loc_18006542E
0x180064dee  test    dword ptr [rdi+48h], 10000h
0x180064df5  jnz     short loc_180064E16
0x180064df7  cmp     [rdi+7Ah], si
0x180064dfb  jnz     short loc_180064E07
0x180064dfd  mov     [rdi+82h], r9w
0x180064e05  jmp     short loc_180064E16
0x180064e07  cmp     word ptr [rdi+7Ah], 5
0x180064e0c  jnz     short loc_180064E16
0x180064e0e  mov     [rdi+82h], r8w
0x180064e16  cmp     r14w, [rdi+82h]
0x180064e1e  jz      loc_18006542E
0x180064e24  mov     rcx, rdi
0x180064e27  test    [rdi+48h], r8b
0x180064e2b  jnz     short loc_180064E54
0x180064e2d  call    TIFFNumberOfStrips
0x180064e32  mov     [rdi+0E4h], eax
0x180064e38  mov     eax, [rdi+58h]
0x180064e3b  mov     [rdi+64h], eax
0x180064e3e  mov     eax, [rdi+84h]
0x180064e44  mov     [rdi+68h], eax
0x180064e47  mov     eax, [rdi+60h]
0x180064e4a  mov     [rdi+6Ch], eax
0x180064e4d  btr     dword ptr [rdi+10h], 0Ah
0x180064e52  jmp     short loc_180064E64
0x180064e54  call    TIFFNumberOfTiles
0x180064e59  mov     [rdi+0E4h], eax
0x180064e5f  bts     dword ptr [rdi+10h], 0Ah
0x180064e64  mov     eax, [rdi+0E4h]
0x180064e6a  test    eax, eax
0x180064e6c  jz      loc_18006542E
0x180064e72  mov     [rdi+0E0h], eax
0x180064e78  cmp     [rdi+0AAh], si
0x180064e7f  jnz     short loc_180064E92
0x180064e81  movzx   ecx, word ptr [rdi+82h]
0x180064e88  xor     edx, edx
0x180064e8a  div     ecx
0x180064e8c  mov     [rdi+0E0h], eax
0x180064e92  mov     rcx, [rbp+arg_0]
0x180064e96  mov     rax, [rcx]
0x180064e99  mov     rax, [rax+28h]
0x180064e9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064ea2  mov     ebx, eax
0x180064ea4  test    eax, eax
0x180064ea6  jns     short loc_180064EBD
0x180064ea8  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x180064eaf  jnz     loc_1800652DC
0x180064eb5  test    eax, eax
0x180064eb7  js      loc_180065443
0x180064ebd  mov     r13b, r14b
0x180064ec0  mov     r15d, r14d
0x180064ec3  mov     rcx, [rbp+arg_0]; struct IWICEnumMetadataItem *
0x180064ec7  lea     rdx, [rbp+var_38]; struct tagPROPVARIANT *
0x180064ecb  call    ?GetNextValue@@YAJPEAUIWICEnumMetadataItem@@PEAUtagPROPVARIANT@@1@Z; GetNextValue(IWICEnumMetadataItem *,tagPROPVARIANT *,tagPROPVARIANT *)
0x180064ed0  mov     r9d, 6
0x180064ed6  mov     r14d, eax
0x180064ed9  test    eax, eax
0x180064edb  js      loc_1800651A4
0x180064ee1  cmp     eax, 1
0x180064ee4  jz      loc_1800651A4
0x180064eea  cmp     word ptr [rbp+var_38], 12h
0x180064eef  jnz     short loc_180064EC3
0x180064ef1  movzx   r11d, word ptr [rbp+var_38+8]
0x180064ef6  mov     rdx, [rdi+4D0h]
0x180064efd  test    r15d, r15d
0x180064f00  jnz     short loc_180064F0A
0x180064f02  mov     rcx, [rdx]
0x180064f05  cmp     [rcx], r11d
0x180064f08  ja      short loc_180064EC3
0x180064f0a  mov     r10, [rdi+4D8h]
0x180064f11  xor     esi, esi
0x180064f13  dec     r10
0x180064f16  mov     eax, r15d
0x180064f19  cmp     rax, r10
0x180064f1c  jnb     short loc_180064F48
0x180064f1e  mov     eax, r15d
0x180064f21  mov     rcx, [rdx+rax*8]
0x180064f25  cmp     [rcx], r11d
0x180064f28  jz      short loc_180064F42
0x180064f2a  lea     ecx, [r15+1]
0x180064f2e  mov     rax, [rdx+rcx*8]
0x180064f32  mov     r9d, ecx
0x180064f35  cmp     [rax], r11d
0x180064f38  ja      short loc_180064F42
0x180064f3a  mov     r15d, ecx
0x180064f3d  cmp     r9, r10
0x180064f40  jb      short loc_180064F1E
0x180064f42  mov     r9d, 6
0x180064f48  mov     rax, [rdi+4D0h]
0x180064f4f  mov     r8d, r11d
0x180064f52  mov     ecx, r15d
0x180064f55  mov     rdx, [rax+rcx*8]
0x180064f59  mov     eax, 145h
0x180064f5e  cmp     [rdx], r11d
0x180064f61  cmovz   rsi, rdx
0x180064f65  cmp     r11d, eax
0x180064f68  ja      loc_18006506B
0x180064f6e  jz      loc_18006503A
0x180064f74  sub     r8d, 102h
0x180064f7b  jz      loc_180065127
0x180064f81  sub     r8d, 0Fh
0x180064f85  jz      short loc_180064FB8
  ... truncated ...
```
