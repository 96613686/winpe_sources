# CRepubCacheSegmentWriteDataTask::UpdateCatalogTableMasksOnly(void)

- ea: `0x180084728`
- end: `0x180084dfa`
- name: `?UpdateCatalogTableMasksOnly@CRepubCacheSegmentWriteDataTask@@AEAAKXZ`
- size: `1746`
- prototype: `unsigned int __fastcall(CRepubCacheSegmentWriteDataTask *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, installer_update`

## callers

- `0x180084fe4`

## callees

- `0x180004374`
- `0x180008290`
- `0x180008310`
- `0x18000ceac`
- `0x180018340`
- `0x1800521d8`
- `0x180063ca0`
- `0x180077bd0`
- `0x180084728`
- `0x180092c40`
- `0x180159010`

## import_xrefs

- `ESENT!JetPrepareUpdate` at `0x180084be0`
- `ESENT!JetPrepareUpdate` at `0x180084be0`
- `ESENT!JetSetColumns` at `0x180084c4e`
- `ESENT!JetSetColumns` at `0x180084c4e`
- `ESENT!JetRetrieveColumns` at `0x1800848a7`
- `ESENT!JetRetrieveColumns` at `0x1800848a7`
- `ESENT!JetUpdate` at `0x180084cb3`
- `ESENT!JetUpdate` at `0x180084cb3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRepubCacheSegmentWriteDataTask::UpdateCatalogTableMasksOnly(CRepubCacheSegmentWriteDataTask *this)
{
  const wchar_t *v2; // r9
  unsigned __int8 *v3; // r15
  unsigned __int8 *v4; // r12
  unsigned __int8 *v5; // r13
  __int64 v6; // rcx
  unsigned int First; // eax
  unsigned int v8; // edi
  CHostedCacheMsgEncoding *v9; // rcx
  __int64 v10; // rdx
  int v11; // ecx
  __int64 v12; // rax
  int v13; // ecx
  __int64 v14; // rax
  unsigned int Columns; // r14d
  CHostedCacheMsgEncoding *v16; // rcx
  __int64 v17; // rdx
  CHostedCacheMsgEncoding *v18; // rcx
  int v19; // ecx
  __int64 v20; // rax
  __int64 v21; // r8
  int v22; // edx
  int v23; // ecx
  __int64 v24; // rax
  __int64 v25; // r9
  int v26; // edx
  int v27; // ecx
  __int64 v28; // rax
  unsigned int v29; // r14d
  unsigned int v30; // r14d
  unsigned int v31; // r9d
  unsigned int v32; // r14d
  unsigned int v33; // r9d
  unsigned __int8 *v35; // [rsp+30h] [rbp-30h] BYREF
  __int16 v36; // [rsp+38h] [rbp-28h]
  _QWORD v37[4]; // [rsp+40h] [rbp-20h] BYREF
  int v38; // [rsp+A0h] [rbp+40h] BYREF
  __int64 v39; // [rsp+A8h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    v2 = L"Y";
    if ( !*((_BYTE *)this + 680) )
      v2 = (const wchar_t *)L"N";
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 12), 179, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids, v2);
  }
  v38 = 0;
  v39 = 0;
  v3 = (unsigned __int8 *)*((_QWORD *)this + 90);
  v4 = (unsigned __int8 *)*((_QWORD *)this + 91);
  v5 = (unsigned __int8 *)*((_QWORD *)this + 92);
  v6 = *(_QWORD *)(*((_QWORD *)this + 83) + 24LL);
  v37[0] = &CCatalogTableSegmentIdIterator::`vftable';
  v37[2] = *((_QWORD *)this + 47);
  v37[3] = *((_QWORD *)this + 62);
  v37[1] = v6;
  First = CCatalogTableSegmentIdIterator::FindFirst((CCatalogTableSegmentIdIterator *)v37);
  v8 = First;
  if ( First )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v10 = 180;
LABEL_79:
      WPP_SF_d(*((_QWORD *)v9 + 12), v10, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids, First);
      return v8;
    }
    return v8;
  }
  v11 = *(_DWORD *)(*((_QWORD *)this + 51) + 872LL);
  v12 = *((_QWORD *)this + 49);
  *(_OWORD *)v12 = 0;
  *(_OWORD *)(v12 + 16) = 0;
  *(_OWORD *)(v12 + 32) = 0;
  *(_DWORD *)v12 = v11;
  *(_DWORD *)(v12 + 16) = 4;
  *(_QWORD *)(v12 + 8) = &v38;
  *(_DWORD *)(v12 + 32) = 1;
  v13 = *(_DWORD *)(*((_QWORD *)this + 51) + 856LL);
  v14 = *((_QWORD *)this + 49);
  *(_OWORD *)(v14 + 48) = 0;
  *(_OWORD *)(v14 + 64) = 0;
  *(_OWORD *)(v14 + 80) = 0;
  *(_DWORD *)(v14 + 48) = v13;
  *(_DWORD *)(v14 + 64) = 8;
  *(_QWORD *)(v14 + 56) = &v39;
  *(_DWORD *)(v14 + 80) = 1;
  Columns = JetRetrieveColumns(*((_QWORD *)this + 47), *((_QWORD *)this + 62), *((JET_RETRIEVECOLUMN **)this + 49), 2u);
  if ( Columns )
  {
    v8 = (*(__int64 (__fastcall **)(CRepubCacheSegmentWriteDataTask *, _QWORD))(*(_QWORD *)this + 48LL))(this, Columns);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      return v8;
    }
    v17 = 181;
    goto LABEL_17;
  }
  if ( v39 == 0x7FFFFFFFFFFFFFFFLL )
  {
    v8 = 4054;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        182,
        WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids,
        *(_QWORD *)(*((_QWORD *)this + 83) + 24LL),
        4054);
    }
    return v8;
  }
  if ( (v38 & 4) == 0
    || CRepubCacheSegment::AllDataBlockBitsSet(*((CRepubCacheSegment **)this + 82), *((_DWORD *)this + 178), v4) )
  {
    goto LABEL_29;
  }
  v38 &= ~4u;
  *((_BYTE *)this + 699) = 1;
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 183, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids);
LABEL_29:
    v18 = WPP_GLOBAL_Control;
  }
  if ( (v38 & 0x10) == 0 )
    goto LABEL_37;
  if ( CRepubCacheSegment::AllDataBlockBitsSet(*((CRepubCacheSegment **)this + 82), *((_DWORD *)this + 178), v3) )
    goto LABEL_36;
  v38 &= ~0x10u;
  *((_BYTE *)this + 700) = 1;
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
    goto LABEL_49;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 184, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids);
LABEL_36:
    v18 = WPP_GLOBAL_Control;
  }
LABEL_37:
  if ( v18 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v18 + 108) & 4) != 0 && *((_BYTE *)v18 + 105) >= 3u )
    {
      v35 = v3;
      v36 = *((_WORD *)this + 356);
      WPP_SF__HEX_(*((_QWORD *)v18 + 12), 185, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids, &v35);
      v18 = WPP_GLOBAL_Control;
    }
    if ( v18 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v18 + 108) & 4) != 0 && *((_BYTE *)v18 + 105) >= 3u )
      {
        v35 = v4;
        v36 = *((_WORD *)this + 356);
        WPP_SF__HEX_(*((_QWORD *)v18 + 12), 186, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids, &v35);
        v18 = WPP_GLOBAL_Control;
      }
      if ( v18 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)v18 + 108) & 4) != 0
        && *((_BYTE *)v18 + 105) >= 3u )
      {
        v35 = v5;
        v36 = *((_WORD *)this + 356);
        WPP_SF__HEX_(*((_QWORD *)v18 + 12), 187, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids, &v35);
      }
    }
  }
LABEL_49:
  v19 = *(_DWORD *)(*((_QWORD *)this + 51) + 872LL);
  v20 = *((_QWORD *)this + 50);
  *(_DWORD *)(v20 + 4) = 0;
  *(_QWORD *)(v20 + 20) = 0;
  *(_QWORD *)(v20 + 32) = 0;
  *(_DWORD *)v20 = v19;
  *(_DWORD *)(v20 + 16) = 4;
  *(_QWORD *)(v20 + 8) = &v38;
  *(_DWORD *)(v20 + 28) = 1;
  v21 = *((_QWORD *)this + 90);
  v22 = *((_DWORD *)this + 178);
  v23 = *(_DWORD *)(*((_QWORD *)this + 51) + 880LL);
  v24 = *((_QWORD *)this + 50);
  *(_DWORD *)(v24 + 44) = 0;
  *(_QWORD *)(v24 + 60) = 0;
  *(_QWORD *)(v24 + 72) = 0;
  *(_DWORD *)(v24 + 40) = v23;
  *(_DWORD *)(v24 + 56) = v22;
  *(_QWORD *)(v24 + 48) = v21;
  *(_DWORD *)(v24 + 68) = 1;
  v25 = *((_QWORD *)this + 91);
  v26 = *((_DWORD *)this + 178);
  v27 = *(_DWORD *)(*((_QWORD *)this + 51) + 884LL);
  v28 = *((_QWORD *)this + 50);
  *(_DWORD *)(v28 + 84) = 0;
  *(_QWORD *)(v28 + 100) = 0;
  *(_QWORD *)(v28 + 112) = 0;
  *(_DWORD *)(v28 + 80) = v27;
  *(_DWORD *)(v28 + 96) = v26;
  *(_QWORD *)(v28 + 88) = v25;
  *(_DWORD *)(v28 + 108) = 1;
  v29 = JetPrepareUpdate(*((_QWORD *)this + 47), *((_QWORD *)this + 62), 2u);
  if ( v29 )
  {
    v8 = (*(__int64 (__fastcall **)(CRepubCacheSegmentWriteDataTask *, _QWORD))(*(_QWORD *)this + 48LL))(this, v29);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      return v8;
    }
    v17 = 188;
    goto LABEL_17;
  }
  v30 = JetSetColumns(*((_QWORD *)this + 47), *((_QWORD *)this + 62), *((JET_SETCOLUMN **)this + 50), 3u);
  if ( v30 )
  {
    v8 = (*(__int64 (__fastcall **)(CRepubCacheSegmentWriteDataTask *, _QWORD))(*(_QWORD *)this + 48LL))(this, v30);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      return v8;
    }
    v17 = 189;
    goto LABEL_17;
  }
  v32 = JetUpdate(*((_QWORD *)this + 47), *((_QWORD *)this + 62), 0, 0, 0);
  if ( v32 )
  {
    v8 = (*(__int64 (__fastcall **)(CRepubCacheSegmentWriteDataTask *, _QWORD))(*(_QWORD *)this + 48LL))(this, v32);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      return v8;
    }
    v17 = 190;
LABEL_17:
    WPP_SF_Dd(*((_QWORD *)v16 + 12), v17, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids);
    return v8;
  }
  if ( *((_BYTE *)this + 700) )
  {
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 191, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids);
    }
    First = UpdateRepubSegmentCount(
              *((_QWORD *)this + 47),
              *((_QWORD *)this + 63),
              *((const struct _CatalogDatabaseDescriptor **)this + 51),
              v31,
              1,
              0);
    v8 = First;
    if ( First )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        v10 = 192;
        goto LABEL_79;
      }
    }
    else
    {
      First = UpdateRepubSegmentCount(
                *((_QWORD *)this + 47),
                *((_QWORD *)this + 63),
                *((const struct _CatalogDatabaseDescriptor **)this + 51),
                v33,
                0,
                1);
      v8 = First;
      if ( First )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          v10 = 193;
          goto LABEL_79;
        }
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180084728  mov     [rsp-38h+arg_10], rbx
0x18008472d  push    rbp
0x18008472e  push    rsi
0x18008472f  push    rdi
0x180084730  push    r12
0x180084732  push    r13
0x180084734  push    r14
0x180084736  push    r15
0x180084738  mov     rbp, rsp
0x18008473b  sub     rsp, 60h
0x18008473f  mov     rbx, rcx
0x180084742  lea     r14, WPP_GLOBAL_Control
0x180084749  xor     edi, edi
0x18008474b  lea     esi, [rdi+4]
0x18008474e  mov     rcx, cs:WPP_GLOBAL_Control
0x180084755  cmp     rcx, r14
0x180084758  jz      short loc_180084794
0x18008475a  test    [rcx+6Ch], sil
0x18008475e  jz      short loc_180084794
0x180084760  cmp     [rcx+69h], sil
0x180084764  jb      short loc_180084794
0x180084766  lea     rax, aN; "N"
0x18008476d  lea     r9, aY; "Y"
0x180084774  cmp     [rbx+2A8h], dil
0x18008477b  cmovz   r9, rax
0x18008477f  mov     edx, 0B3h
0x180084784  lea     r8, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids
0x18008478b  mov     rcx, [rcx+60h]
0x18008478f  call    WPP_SF_S
0x180084794  mov     [rbp+arg_0], edi
0x180084797  mov     [rbp+arg_8], rdi
0x18008479b  mov     r15, [rbx+2D0h]
0x1800847a2  mov     r12, [rbx+2D8h]
0x1800847a9  mov     r13, [rbx+2E0h]
0x1800847b0  mov     rax, [rbx+298h]
0x1800847b7  mov     rcx, [rax+18h]
0x1800847bb  lea     rax, ??_7CCatalogTableSegmentIdIterator@@6B@; const CCatalogTableSegmentIdIterator::`vftable'
0x1800847c2  mov     [rbp+var_20], rax
0x1800847c6  mov     rax, [rbx+178h]
0x1800847cd  mov     [rbp+var_10], rax
0x1800847d1  mov     rax, [rbx+1F0h]
0x1800847d8  mov     [rbp+var_8], rax
0x1800847dc  mov     [rbp+var_18], rcx
0x1800847e0  lea     rcx, [rbp+var_20]; this
0x1800847e4  call    ?FindFirst@CCatalogTableSegmentIdIterator@@UEAAKXZ; CCatalogTableSegmentIdIterator::FindFirst(void)
0x1800847e9  mov     edi, eax
0x1800847eb  test    eax, eax
0x1800847ed  jz      short loc_180084822
0x1800847ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800847f6  cmp     rcx, r14
0x1800847f9  jz      loc_180084DE0
0x1800847ff  test    [rcx+6Ch], sil
0x180084803  jz      loc_180084DE0
0x180084809  mov     esi, 1
0x18008480e  cmp     [rcx+69h], sil
0x180084812  jb      loc_180084DE0
0x180084818  mov     edx, 0B4h
0x18008481d  jmp     loc_180084DCC
0x180084822  mov     rax, [rbx+198h]
0x180084829  mov     ecx, [rax+368h]
0x18008482f  mov     rax, [rbx+188h]
0x180084836  xorps   xmm0, xmm0
0x180084839  movups  xmmword ptr [rax], xmm0
0x18008483c  movups  xmmword ptr [rax+10h], xmm0
0x180084840  movups  xmmword ptr [rax+20h], xmm0
0x180084844  mov     [rax], ecx
0x180084846  mov     [rax+10h], esi
0x180084849  lea     rcx, [rbp+arg_0]
0x18008484d  mov     [rax+8], rcx
0x180084851  mov     esi, 1
0x180084856  mov     [rax+20h], esi
0x180084859  mov     rax, [rbx+198h]
0x180084860  mov     ecx, [rax+358h]
0x180084866  mov     rax, [rbx+188h]
0x18008486d  movups  xmmword ptr [rax+30h], xmm0
0x180084871  movups  xmmword ptr [rax+40h], xmm0
0x180084875  movups  xmmword ptr [rax+50h], xmm0
0x180084879  mov     [rax+30h], ecx
0x18008487c  mov     dword ptr [rax+40h], 8
0x180084883  lea     rcx, [rbp+arg_8]
0x180084887  mov     [rax+38h], rcx
0x18008488b  mov     [rax+50h], esi
0x18008488e  lea     r9d, [rsi+1]; cretrievecolumn
0x180084892  mov     r8, [rbx+188h]; pretrievecolumn
0x180084899  mov     rdx, [rbx+1F0h]; tableid
0x1800848a0  mov     rcx, [rbx+178h]; sesid
0x1800848a7  call    cs:__imp_JetRetrieveColumns
0x1800848ad  mov     r14d, eax
0x1800848b0  test    eax, eax
0x1800848b2  jz      short loc_180084914
0x1800848b4  mov     rcx, [rbx]
0x1800848b7  mov     rax, [rcx+30h]
0x1800848bb  mov     edx, r14d
0x1800848be  mov     rcx, rbx
0x1800848c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800848c6  mov     edi, eax
0x1800848c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800848cf  lea     rax, WPP_GLOBAL_Control
0x1800848d6  cmp     rcx, rax
0x1800848d9  jz      loc_180084DE0
0x1800848df  test    byte ptr [rcx+6Ch], 4
0x1800848e3  jz      loc_180084DE0
0x1800848e9  cmp     [rcx+69h], sil
0x1800848ed  jb      loc_180084DE0
0x1800848f3  mov     edx, 0B5h
0x1800848f8  mov     dword ptr [rsp+60h+pcbActual], edi
0x1800848fc  mov     r9d, r14d
0x1800848ff  lea     r8, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids
0x180084906  mov     rcx, [rcx+60h]
0x18008490a  call    WPP_SF_Dd
0x18008490f  jmp     loc_180084DE0
0x180084914  mov     rax, 7FFFFFFFFFFFFFFFh
0x18008491e  cmp     [rbp+arg_8], rax
0x180084922  jnz     short loc_18008497D
0x180084924  mov     edi, 0FD6h
0x180084929  mov     rcx, cs:WPP_GLOBAL_Control
0x180084930  lea     rax, WPP_GLOBAL_Control
0x180084937  cmp     rcx, rax
0x18008493a  jz      loc_180084DE0
0x180084940  test    byte ptr [rcx+6Ch], 4
0x180084944  jz      loc_180084DE0
0x18008494a  cmp     [rcx+69h], sil
0x18008494e  jb      loc_180084DE0
0x180084954  mov     r9, [rbx+298h]
0x18008495b  mov     edx, 0B6h
0x180084960  mov     dword ptr [rsp+60h+pcbActual], edi
0x180084964  mov     r9, [r9+18h]
0x180084968  lea     r8, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids
0x18008496f  mov     rcx, [rcx+60h]
0x180084973  call    WPP_SF_qD
0x180084978  jmp     loc_180084DE0
0x18008497d  mov     r14d, 4
0x180084983  test    byte ptr [rbp+arg_0], r14b
0x180084987  jz      short loc_1800849E1
0x180084989  mov     r8, r12; unsigned __int8 *
0x18008498c  mov     edx, [rbx+2C8h]; unsigned int
0x180084992  mov     rcx, [rbx+290h]; this
0x180084999  call    ?AllDataBlockBitsSet@CRepubCacheSegment@@QEAA_NKPEAE@Z; CRepubCacheSegment::AllDataBlockBitsSet(ulong,uchar *)
0x18008499e  test    al, al
0x1800849a0  jnz     short loc_1800849E1
0x1800849a2  and     [rbp+arg_0], 0FFFFFFFBh
0x1800849a6  mov     [rbx+2BBh], sil
0x1800849ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800849b4  lea     rax, WPP_GLOBAL_Control
0x1800849bb  cmp     rcx, rax
0x1800849be  jz      short loc_1800849E8
0x1800849c0  test    [rcx+6Ch], r14b
0x1800849c4  jz      short loc_1800849E8
0x1800849c6  cmp     [rcx+69h], r14b
0x1800849ca  jb      short loc_1800849E8
0x1800849cc  mov     edx, 0B7h
0x1800849d1  lea     r8, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids
0x1800849d8  mov     rcx, [rcx+60h]
0x1800849dc  call    WPP_SF_
0x1800849e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800849e8  test    byte ptr [rbp+arg_0], 10h
0x1800849ec  jz      short loc_180084A51
0x1800849ee  mov     r8, r15; unsigned __int8 *
0x1800849f1  mov     edx, [rbx+2C8h]; unsigned int
0x1800849f7  mov     rcx, [rbx+290h]; this
0x1800849fe  call    ?AllDataBlockBitsSet@CRepubCacheSegment@@QEAA_NKPEAE@Z; CRepubCacheSegment::AllDataBlockBitsSet(ulong,uchar *)
0x180084a03  test    al, al
0x180084a05  jnz     short loc_180084A4A
0x180084a07  and     [rbp+arg_0], 0FFFFFFEFh
0x180084a0b  mov     [rbx+2BCh], sil
0x180084a12  mov     rcx, cs:WPP_GLOBAL_Control
0x180084a19  lea     rax, WPP_GLOBAL_Control
0x180084a20  cmp     rcx, rax
0x180084a23  jz      loc_180084B1E
0x180084a29  test    [rcx+6Ch], r14b
0x180084a2d  jz      short loc_180084A58
0x180084a2f  cmp     [rcx+69h], r14b
0x180084a33  jb      short loc_180084A58
0x180084a35  mov     edx, 0B8h
0x180084a3a  lea     r8, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids
0x180084a41  mov     rcx, [rcx+60h]
0x180084a45  call    WPP_SF_
0x180084a4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180084a51  lea     rax, WPP_GLOBAL_Control
0x180084a58  cmp     rcx, rax
0x180084a5b  jz      loc_180084B1E
0x180084a61  test    [rcx+6Ch], r14b
0x180084a65  jz      short loc_180084A9C
0x180084a67  cmp     byte ptr [rcx+69h], 3
0x180084a6b  jb      short loc_180084A9C
0x180084a6d  mov     [rbp+var_30], r15
0x180084a71  movzx   eax, word ptr [rbx+2C8h]
0x180084a78  mov     [rbp+var_28], ax
0x180084a7c  mov     edx, 0B9h
0x180084a81  lea     r9, [rbp+var_30]
0x180084a85  lea     r8, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids
0x180084a8c  mov     rcx, [rcx+60h]
0x180084a90  call    WPP_SF__HEX_
0x180084a95  mov     rcx, cs:WPP_GLOBAL_Control
0x180084a9c  lea     r15, WPP_GLOBAL_Control
0x180084aa3  cmp     rcx, r15
0x180084aa6  jz      short loc_180084B25
0x180084aa8  test    [rcx+6Ch], r14b
0x180084aac  jz      short loc_180084AE3
0x180084aae  cmp     byte ptr [rcx+69h], 3
0x180084ab2  jb      short loc_180084AE3
0x180084ab4  mov     [rbp+var_30], r12
0x180084ab8  movzx   eax, word ptr [rbx+2C8h]
0x180084abf  mov     [rbp+var_28], ax
0x180084ac3  mov     edx, 0BAh
0x180084ac8  lea     r9, [rbp+var_30]
0x180084acc  lea     r8, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids
0x180084ad3  mov     rcx, [rcx+60h]
0x180084ad7  call    WPP_SF__HEX_
0x180084adc  mov     rcx, cs:WPP_GLOBAL_Control
0x180084ae3  cmp     rcx, r15
0x180084ae6  jz      short loc_180084B25
0x180084ae8  test    [rcx+6Ch], r14b
0x180084aec  jz      short loc_180084B25
0x180084aee  cmp     byte ptr [rcx+69h], 3
0x180084af2  jb      short loc_180084B25
0x180084af4  mov     [rbp+var_30], r13
0x180084af8  movzx   eax, word ptr [rbx+2C8h]
0x180084aff  mov     [rbp+var_28], ax
0x180084b03  mov     edx, 0BBh
0x180084b08  lea     r9, [rbp+var_30]
0x180084b0c  lea     r8, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids
0x180084b13  mov     rcx, [rcx+60h]
0x180084b17  call    WPP_SF__HEX_
0x180084b1c  jmp     short loc_180084B25
0x180084b1e  lea     r15, WPP_GLOBAL_Control
0x180084b25  mov     rax, [rbx+198h]
0x180084b2c  mov     ecx, [rax+368h]
0x180084b32  mov     rax, [rbx+190h]
0x180084b39  xor     r12d, r12d
0x180084b3c  mov     [rax+4], r12d
0x180084b40  mov     [rax+14h], r12
0x180084b44  mov     [rax+20h], r12
0x180084b48  mov     [rax], ecx
0x180084b4a  mov     [rax+10h], r14d
0x180084b4e  lea     rcx, [rbp+arg_0]
0x180084b52  mov     [rax+8], rcx
0x180084b56  mov     [rax+1Ch], esi
0x180084b59  mov     r8, [rbx+2D0h]
0x180084b60  mov     edx, [rbx+2C8h]
0x180084b66  mov     rax, [rbx+198h]
0x180084b6d  mov     ecx, [rax+370h]
0x180084b73  mov     rax, [rbx+190h]
0x180084b7a  mov     [rax+2Ch], r12d
0x180084b7e  mov     [rax+3Ch], r12
0x180084b82  mov     [rax+48h], r12
0x180084b86  mov     [rax+28h], ecx
0x180084b89  mov     [rax+38h], edx
0x180084b8c  mov     [rax+30h], r8
0x180084b90  mov     [rax+44h], esi
0x180084b93  mov     r9, [rbx+2D8h]
0x180084b9a  mov     edx, [rbx+2C8h]
0x180084ba0  mov     rax, [rbx+198h]
0x180084ba7  mov     ecx, [rax+374h]
0x180084bad  mov     rax, [rbx+190h]
0x180084bb4  mov     [rax+54h], r12d
0x180084bb8  mov     [rax+64h], r12
0x180084bbc  mov     [rax+70h], r12
0x180084bc0  mov     [rax+50h], ecx
0x180084bc3  mov     [rax+60h], edx
0x180084bc6  mov     [rax+58h], r9
0x180084bca  mov     [rax+6Ch], esi
0x180084bcd  lea     r8d, [r12+2]; prep
0x180084bd2  mov     rdx, [rbx+1F0h]; tableid
0x180084bd9  mov     rcx, [rbx+178h]; sesid
0x180084be0  call    cs:__imp_JetPrepareUpdate
0x180084be6  mov     r14d, eax
0x180084be9  test    eax, eax
0x180084beb  jz      short loc_180084C33
0x180084bed  mov     rcx, [rbx]
0x180084bf0  mov     rax, [rcx+30h]
0x180084bf4  mov     edx, r14d
0x180084bf7  mov     rcx, rbx
0x180084bfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084bff  mov     edi, eax
0x180084c01  mov     rcx, cs:WPP_GLOBAL_Control
0x180084c08  cmp     rcx, r15
0x180084c0b  jz      loc_180084DE0
0x180084c11  test    byte ptr [rcx+6Ch], 4
0x180084c15  jz      loc_180084DE0
0x180084c1b  cmp     [rcx+69h], sil
0x180084c1f  jb      loc_180084DE0
0x180084c25  mov     edx, 0BCh
0x180084c2a  mov     dword ptr [rsp+60h+pcbActual], eax
0x180084c2e  jmp     loc_1800848FC
0x180084c33  mov     r9d, 3; csetcolumn
0x180084c39  mov     r8, [rbx+190h]; psetcolumn
0x180084c40  mov     rdx, [rbx+1F0h]; tableid
0x180084c47  mov     rcx, [rbx+178h]; sesid
0x180084c4e  call    cs:__imp_JetSetColumns
0x180084c54  mov     r14d, eax
0x180084c57  test    eax, eax
0x180084c59  jz      short loc_180084C9A
0x180084c5b  mov     rcx, [rbx]
0x180084c5e  mov     rax, [rcx+30h]
0x180084c62  mov     edx, r14d
0x180084c65  mov     rcx, rbx
0x180084c68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084c6d  mov     edi, eax
0x180084c6f  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
