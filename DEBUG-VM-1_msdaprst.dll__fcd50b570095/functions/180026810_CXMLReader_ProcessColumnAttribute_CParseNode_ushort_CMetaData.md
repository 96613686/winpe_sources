# CXMLReader::ProcessColumnAttribute(CParseNode *,ushort,CMetaData *)

- ea: `0x180026810`
- end: `0x180026e1d`
- name: `?ProcessColumnAttribute@CXMLReader@@AEAAJPEAVCParseNode@@GPEAVCMetaData@@@Z`
- size: `1549`
- prototype: `__int64 __fastcall(CXMLReader *__hidden this, struct CParseNode *, unsigned __int16, struct CMetaData *)`
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config`

## callers

- `0x180023730`
- `0x180026e24`

## callees

- `0x180001d94`
- `0x180001dd8`
- `0x180003abc`
- `0x180004b90`
- `0x180004c84`
- `0x180004d80`
- `0x180004e74`
- `0x180004f68`
- `0x180004fe0`
- `0x18001a6c8`
- `0x180025f80`
- `0x180026560`
- `0x180026810`
- `0x180028724`
- `0x180028dbc`
- `0x180028ee0`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x180026a02`
- `OLEAUT32!__imp_SysStringLen` at `0x180026c3b`
- `OLEAUT32!__imp_SysStringLen` at `0x180026ce5`
- `OLEAUT32!__imp_SysStringLen` at `0x180026a02`
- `OLEAUT32!__imp_SysStringLen` at `0x180026c3b`
- `OLEAUT32!__imp_SysStringLen` at `0x180026ce5`
- `OLEAUT32!__imp_VariantInit` at `0x18002684f`
- `OLEAUT32!__imp_VariantInit` at `0x18002684f`
- `OLEAUT32!__imp_VariantClear` at `0x180026e04`
- `OLEAUT32!__imp_VariantClear` at `0x180026e04`
- `OLEAUT32!__imp_VariantChangeType` at `0x180026909`
- `OLEAUT32!__imp_VariantChangeType` at `0x180026964`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800269b0`
- `OLEAUT32!__imp_VariantChangeType` at `0x180026a1f`
- `OLEAUT32!__imp_VariantChangeType` at `0x180026a82`
- `OLEAUT32!__imp_VariantChangeType` at `0x180026b3b`
- `OLEAUT32!__imp_VariantChangeType` at `0x180026b8b`
- `OLEAUT32!__imp_VariantChangeType` at `0x180026bf3`
- `OLEAUT32!__imp_VariantChangeType` at `0x180026909`
- `OLEAUT32!__imp_VariantChangeType` at `0x180026964`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800269b0`
- `OLEAUT32!__imp_VariantChangeType` at `0x180026a1f`
- `OLEAUT32!__imp_VariantChangeType` at `0x180026a82`
- `OLEAUT32!__imp_VariantChangeType` at `0x180026b3b`
- `OLEAUT32!__imp_VariantChangeType` at `0x180026b8b`
- `OLEAUT32!__imp_VariantChangeType` at `0x180026bf3`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall CXMLReader::ProcessColumnAttribute(
        CXMLReader *this,
        struct CParseNode *a2,
        unsigned __int16 a3,
        struct CMetaData *a4)
{
  __int64 v5; // rsi
  unsigned __int16 **Value; // rax
  unsigned int v9; // eax
  HRESULT v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // rdx
  unsigned int Flags; // r14d
  int v15; // r14d
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rdx
  UINT v21; // eax
  unsigned int v22; // edx
  unsigned int v23; // r15d
  unsigned __int8 *v24; // rax
  unsigned __int8 *v25; // r14
  int v26; // r15d
  __int64 v27; // r14
  UINT v28; // eax
  unsigned __int16 v29; // r10
  unsigned __int16 v30; // r10
  VARIANTARG pvarg; // [rsp+48h] [rbp-70h] BYREF
  _QWORD pvarSrc[11]; // [rsp+60h] [rbp-58h] BYREF
  unsigned __int64 v34; // [rsp+C8h] [rbp+10h] BYREF

  v5 = a3;
  memset(pvarSrc, 0, 32);
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  Value = (unsigned __int16 **)CParseNode::GetValue(a2);
  v9 = CXMLReader::LookupAttributeInfo(
         this,
         *((_DWORD *)a2 + 1),
         *((unsigned __int16 **)a2 + 4),
         *Value,
         (struct tagDBATTRIBINFO *)pvarSrc);
  v10 = v9;
  if ( v9 )
  {
    if ( (bidGblFlags & 2) != 0 && off_180048D30[0] )
      bidTraceW(off_180048208[0], 930816, off_180048D30[0], v9, 909);
    goto LABEL_64;
  }
  if ( HIDWORD(pvarSrc[0]) == 16 )
  {
    CMetaData::mdSetName(a4, v5, (unsigned __int16 *)pvarSrc[2], 0xFFFFu);
    goto LABEL_64;
  }
  if ( HIDWORD(pvarSrc[0]) == 17 )
  {
    v10 = VariantChangeType(&pvarg, (const VARIANTARG *)&pvarSrc[1], 0, 3u);
    if ( v10 >= 0 )
    {
      v11 = 9648 * v5;
      *(_QWORD *)(v11 + *((_QWORD *)a4 + 4) + 1040) = pvarg.cyVal.Lo;
      *(_DWORD *)(v11 + *((_QWORD *)a4 + 4) + 1048) = 0;
    }
    goto LABEL_64;
  }
  if ( (unsigned int)(HIDWORD(pvarSrc[0]) - 18) <= 1 )
  {
    v34 = 0;
    v27 = 9648 * v5;
    if ( *(_DWORD *)(9648 * v5 + *((_QWORD *)a4 + 4) + 1056) != 3 && HIDWORD(pvarSrc[0]) != 19 )
      goto LABEL_64;
    v28 = SysStringLen((BSTR)pvarSrc[2]);
    if ( (unsigned int)CCollectionList::LookUpByKey(
                         (CXMLReader *)((char *)this + 304),
                         (unsigned __int16 *)pvarSrc[2],
                         v28,
                         &v34) )
      goto LABEL_64;
    if ( HIDWORD(pvarSrc[0]) == 18 && *((_BYTE *)this + 472) )
    {
      v29 = v34;
      if ( (_WORD)v34 == 20 )
      {
        *(_WORD *)(v27 + *((_QWORD *)a4 + 4) + 1052) = 6;
LABEL_61:
        *(_DWORD *)(v27 + *((_QWORD *)a4 + 4) + 1056) = 0;
        if ( IsFixedLength(v29) )
        {
          v34 = 0;
          *(_DWORD *)(v27 + *((_QWORD *)a4 + 4) + 1092) = CMetaData::mdGetFlags(a4, v5) | 0x10;
          *(_DWORD *)(v27 + *((_QWORD *)a4 + 4) + 1096) = 0;
          if ( (*(int (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, unsigned __int64 *, _QWORD))(**((_QWORD **)this + 61)
                                                                                                 + 40LL))(
                 *((_QWORD *)this + 61),
                 v30,
                 v30,
                 0,
                 &v34,
                 0) >= 0 )
          {
            *(_QWORD *)(v27 + *((_QWORD *)a4 + 4) + 1064) = (unsigned int)v34;
            *(_DWORD *)(v27 + *((_QWORD *)a4 + 4) + 1072) = 0;
          }
        }
        goto LABEL_64;
      }
    }
    else
    {
      v29 = v34;
    }
    *(_WORD *)(v27 + *((_QWORD *)a4 + 4) + 1052) = v29;
    goto LABEL_61;
  }
  switch ( HIDWORD(pvarSrc[0]) )
  {
    case 0x14:
      v10 = VariantChangeType(&pvarg, (const VARIANTARG *)&pvarSrc[1], 0, 0x11u);
      if ( v10 >= 0 )
      {
        v12 = 9648 * v5;
        *(_WORD *)(v12 + *((_QWORD *)a4 + 4) + 1076) = pvarg.bVal;
        *(_DWORD *)(v12 + *((_QWORD *)a4 + 4) + 1080) = 0;
      }
      break;
    case 0x15:
      v10 = VariantChangeType(&pvarg, (const VARIANTARG *)&pvarSrc[1], 0, 0x11u);
      if ( v10 >= 0 )
      {
        v13 = 9648 * v5;
        *(_WORD *)(v13 + *((_QWORD *)a4 + 4) + 1084) = pvarg.bVal;
        *(_DWORD *)(v13 + *((_QWORD *)a4 + 4) + 1088) = 0;
      }
      break;
    case 0x16:
      Flags = CMetaData::mdGetFlags(a4, v5);
      if ( !SysStringLen((BSTR)pvarSrc[2]) )
        goto LABEL_21;
      v10 = VariantChangeType(&pvarg, (const VARIANTARG *)&pvarSrc[1], 0, 0xBu);
      if ( v10 < 0 )
        break;
      if ( pvarg.iVal != -1 )
        v15 = ~LODWORD(pvarSrc[0]) & Flags;
      else
LABEL_21:
        v15 = LODWORD(pvarSrc[0]) | Flags;
      v16 = 9648 * v5;
      *(_DWORD *)(v16 + *((_QWORD *)a4 + 4) + 1092) = v15;
      *(_DWORD *)(v16 + *((_QWORD *)a4 + 4) + 1096) = 0;
      break;
    case 0x1C:
      v10 = VariantChangeType(&pvarg, (const VARIANTARG *)&pvarSrc[1], 0, 5u);
      if ( v10 >= 0 )
      {
        v17 = 9648 * v5;
        *(_QWORD *)(v17 + *((_QWORD *)a4 + 4) + 1064) = (unsigned int)(int)pvarg.dblVal;
        *(_DWORD *)(v17 + *((_QWORD *)a4 + 4) + 1072) = 0;
      }
      break;
    case 0x17:
      CMetaData::mdSetBaseColumn(a4, v5, (unsigned __int16 *)pvarSrc[2], 0xFFFFu);
      break;
    case 0x1A:
      CMetaData::mdSetBaseCatalog(a4, v5, (unsigned __int16 *)pvarSrc[2], 0x11u);
      break;
    case 0x1B:
      CMetaData::mdSetBaseSchema(a4, v5, (unsigned __int16 *)pvarSrc[2], 0x11u);
      break;
    case 0x18:
      CMetaData::mdSetBaseTable(a4, v5, (unsigned __int16 *)pvarSrc[2], 0x11u);
      break;
    case 0x1D:
      v10 = VariantChangeType(&pvarg, (const VARIANTARG *)&pvarSrc[1], 0, 0xBu);
      if ( v10 >= 0 )
      {
        v18 = 9648 * v5;
        *(_WORD *)(v18 + *((_QWORD *)a4 + 4) + 9580) = pvarg.iVal;
        *(_DWORD *)(v18 + *((_QWORD *)a4 + 4) + 9584) = 0;
      }
      break;
    case 0x1E:
      v10 = VariantChangeType(&pvarg, (const VARIANTARG *)&pvarSrc[1], 0, 0xBu);
      if ( v10 >= 0 && pvarg.iVal == -1 )
      {
        --*((_WORD *)a4 + 1);
        v19 = 9648 * v5;
        *(GUID *)(v19 + *((_QWORD *)a4 + 4) + 2144) = DBCOL_SPECIALCOL;
        *(_DWORD *)(v19 + *((_QWORD *)a4 + 4) + 2160) = 0;
      }
      break;
    case 0x19:
      v10 = VariantChangeType(&pvarg, (const VARIANTARG *)&pvarSrc[1], 0, 0xBu);
      if ( v10 >= 0 )
      {
        v20 = 9648 * v5;
        *(_WORD *)(v20 + *((_QWORD *)a4 + 4) + 9528) = pvarg.iVal;
        *(_DWORD *)(v20 + *((_QWORD *)a4 + 4) + 9532) = 0;
      }
      break;
    case 0x1F:
      v21 = SysStringLen((BSTR)pvarSrc[2]);
      v23 = v21;
      if ( v21 )
      {
        LODWORD(v34) = 0;
        v24 = MMMAlloc(v21 >> 1, v22);
        v25 = v24;
        if ( v24 )
        {
          v26 = DecodeBin((unsigned __int16 *)pvarSrc[2], v24, v23, (int *)&v34);
          if ( v26 >= 0 )
          {
            CMetaData::mdSetCalculationInfo(a4, v5, v25, v34);
          }
          else
          {
            MMMFree(v25);
            v10 = v26;
          }
        }
        else
        {
          v10 = -2147024882;
        }
      }
      break;
  }
LABEL_64:
  VariantClear(&pvarg);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180026810  push    rbx
0x180026812  push    rsi
0x180026813  push    rdi
0x180026814  push    r12
0x180026816  push    r14
0x180026818  push    r15
0x18002681a  sub     rsp, 88h
0x180026821  mov     rdi, r9
0x180026824  movzx   esi, r8w
0x180026828  mov     rbx, rdx
0x18002682b  mov     r15, rcx
0x18002682e  xorps   xmm0, xmm0
0x180026831  movups  xmmword ptr [rsp+0B8h+pvarSrc], xmm0
0x180026836  movups  xmmword ptr [rsp+0B8h+pvarSrc+10h], xmm0
0x18002683b  xorps   xmm1, xmm1
0x18002683e  xor     eax, eax
0x180026840  movups  xmmword ptr [rsp+0B8h+pvarg], xmm1
0x180026845  mov     qword ptr [rsp+0B8h+pvarg+10h], rax
0x18002684a  lea     rcx, [rsp+0B8h+pvarg]; pvarg
0x18002684f  call    cs:__imp_VariantInit
0x180026855  mov     rcx, rbx; this
0x180026858  call    ?GetValue@CParseNode@@QEAAAEAVCComBSTR@ATL@@XZ; CParseNode::GetValue(void)
0x18002685d  lea     rcx, [rsp+0B8h+pvarSrc]
0x180026862  mov     [rsp+0B8h+var_98], rcx; struct tagDBATTRIBINFO *
0x180026867  mov     r9, [rax]; unsigned __int16 *
0x18002686a  mov     r8, [rbx+20h]; unsigned __int16 *
0x18002686e  mov     edx, [rbx+4]; unsigned int
0x180026871  mov     rcx, r15; this
0x180026874  call    ?LookupAttributeInfo@CXMLReader@@AEAAJKPEAG0PEAUtagDBATTRIBINFO@@@Z; CXMLReader::LookupAttributeInfo(ulong,ushort *,ushort *,tagDBATTRIBINFO *)
0x180026879  mov     ebx, eax
0x18002687b  xor     r12d, r12d
0x18002687e  test    eax, eax
0x180026880  jz      short loc_1800268C7
0x180026882  test    byte ptr cs:_bidGblFlags, 2
0x180026889  jz      loc_180026DFF
0x18002688f  mov     rcx, cs:off_180048D30; "<CXMLReader::ProcessColumnAttribute|ADO"...
0x180026896  test    rcx, rcx
0x180026899  jz      loc_180026DFF
0x18002689f  mov     dword ptr [rsp+0B8h+var_98], 38Dh
0x1800268a7  mov     r9d, eax
0x1800268aa  mov     r8, cs:off_180048D30; "<CXMLReader::ProcessColumnAttribute|ADO"...
0x1800268b1  mov     edx, 0E3400h
0x1800268b6  mov     rcx, cs:off_180048208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800268bd  call    _bidTraceW
0x1800268c2  jmp     loc_180026DFF
0x1800268c7  mov     ecx, dword ptr [rsp+0B8h+pvarSrc+4]
0x1800268cb  cmp     ecx, 10h
0x1800268ce  jnz     short loc_1800268EB
0x1800268d0  mov     r9d, 0FFFFh; unsigned __int16
0x1800268d6  mov     r8, qword ptr [rsp+0B8h+pvarSrc+10h]; unsigned __int16 *
0x1800268db  movzx   edx, si; unsigned __int16
0x1800268de  mov     rcx, rdi; this
0x1800268e1  call    ?mdSetName@CMetaData@@QEAAXGPEAGG@Z; CMetaData::mdSetName(ushort,ushort *,ushort)
0x1800268e6  jmp     loc_180026B20
0x1800268eb  mov     r9d, 11h; unsigned __int16
0x1800268f1  cmp     ecx, r9d
0x1800268f4  jnz     short loc_180026942
0x1800268f6  mov     r9d, 3; vt
0x1800268fc  xor     r8d, r8d; wFlags
0x1800268ff  lea     rdx, [rsp+0B8h+pvarSrc+8]; pvarSrc
0x180026904  lea     rcx, [rsp+0B8h+pvarg]; pvargDest
0x180026909  call    cs:__imp_VariantChangeType
0x18002690f  mov     ebx, eax
0x180026911  test    eax, eax
0x180026913  jns     short loc_18002691A
0x180026915  jmp     loc_180026DFF
0x18002691a  imul    rdx, rsi, 25B0h
0x180026921  mov     ecx, dword ptr [rsp+0B8h+pvarg+8]
0x180026925  mov     rax, [rdi+20h]
0x180026929  mov     [rdx+rax+410h], rcx
0x180026931  mov     rax, [rdi+20h]
0x180026935  mov     [rdx+rax+418h], r12d
0x18002693d  jmp     loc_180026DF6
0x180026942  lea     eax, [rcx-12h]
0x180026945  cmp     eax, 1
0x180026948  jbe     loc_180026CB9
0x18002694e  mov     eax, 14h
0x180026953  cmp     ecx, eax
0x180026955  jnz     short loc_18002699E
0x180026957  xor     r8d, r8d; wFlags
0x18002695a  lea     rdx, [rsp+0B8h+pvarSrc+8]; pvarSrc
0x18002695f  lea     rcx, [rsp+0B8h+pvarg]; pvargDest
0x180026964  call    cs:__imp_VariantChangeType
0x18002696a  mov     ebx, eax
0x18002696c  test    eax, eax
0x18002696e  jns     short loc_180026975
0x180026970  jmp     loc_180026DFF
0x180026975  imul    rdx, rsi, 25B0h
0x18002697c  movzx   ecx, byte ptr [rsp+0B8h+pvarg+8]
0x180026981  mov     rax, [rdi+20h]
0x180026985  mov     [rdx+rax+434h], cx
0x18002698d  mov     rax, [rdi+20h]
0x180026991  mov     [rdx+rax+438h], r12d
0x180026999  jmp     loc_180026DF6
0x18002699e  cmp     ecx, 15h
0x1800269a1  jnz     short loc_1800269EA
0x1800269a3  xor     r8d, r8d; wFlags
0x1800269a6  lea     rdx, [rsp+0B8h+pvarSrc+8]; pvarSrc
0x1800269ab  lea     rcx, [rsp+0B8h+pvarg]; pvargDest
0x1800269b0  call    cs:__imp_VariantChangeType
0x1800269b6  mov     ebx, eax
0x1800269b8  test    eax, eax
0x1800269ba  jns     short loc_1800269C1
0x1800269bc  jmp     loc_180026DFF
0x1800269c1  imul    rdx, rsi, 25B0h
0x1800269c8  movzx   ecx, byte ptr [rsp+0B8h+pvarg+8]
0x1800269cd  mov     rax, [rdi+20h]
0x1800269d1  mov     [rdx+rax+43Ch], cx
0x1800269d9  mov     rax, [rdi+20h]
0x1800269dd  mov     [rdx+rax+440h], r12d
0x1800269e5  jmp     loc_180026DF6
0x1800269ea  cmp     ecx, 16h
0x1800269ed  jnz     short loc_180026A6C
0x1800269ef  movzx   edx, si; unsigned __int16
0x1800269f2  mov     rcx, rdi; this
0x1800269f5  call    ?mdGetFlags@CMetaData@@QEAAKG@Z; CMetaData::mdGetFlags(ushort)
0x1800269fa  mov     r14d, eax
0x1800269fd  mov     rcx, qword ptr [rsp+0B8h+pvarSrc+10h]; pbstr
0x180026a02  call    cs:__imp_SysStringLen
0x180026a08  test    eax, eax
0x180026a0a  jz      short loc_180026A38
0x180026a0c  mov     r9d, 0Bh; vt
0x180026a12  xor     r8d, r8d; wFlags
0x180026a15  lea     rdx, [rsp+0B8h+pvarSrc+8]; pvarSrc
0x180026a1a  lea     rcx, [rsp+0B8h+pvarg]; pvargDest
0x180026a1f  call    cs:__imp_VariantChangeType
0x180026a25  mov     ebx, eax
0x180026a27  test    eax, eax
0x180026a29  jns     short loc_180026A30
0x180026a2b  jmp     loc_180026DFF
0x180026a30  cmp     word ptr [rsp+0B8h+pvarg+8], 0FFFFh
0x180026a36  jnz     short loc_180026A3F
0x180026a38  or      r14d, dword ptr [rsp+0B8h+pvarSrc]
0x180026a3d  jmp     short loc_180026A48
0x180026a3f  mov     eax, dword ptr [rsp+0B8h+pvarSrc]
0x180026a43  not     eax
0x180026a45  and     r14d, eax
0x180026a48  imul    rcx, rsi, 25B0h
0x180026a4f  mov     rax, [rdi+20h]
0x180026a53  mov     [rcx+rax+444h], r14d
0x180026a5b  mov     rax, [rdi+20h]
0x180026a5f  mov     [rcx+rax+448h], r12d
0x180026a67  jmp     loc_180026DF6
0x180026a6c  cmp     ecx, 1Ch
0x180026a6f  jnz     short loc_180026AC0
0x180026a71  lea     r9d, [rcx-17h]; vt
0x180026a75  xor     r8d, r8d; wFlags
0x180026a78  lea     rdx, [rsp+0B8h+pvarSrc+8]; pvarSrc
0x180026a7d  lea     rcx, [rsp+0B8h+pvarg]; pvargDest
0x180026a82  call    cs:__imp_VariantChangeType
0x180026a88  mov     ebx, eax
0x180026a8a  test    eax, eax
0x180026a8c  jns     short loc_180026A93
0x180026a8e  jmp     loc_180026DFF
0x180026a93  imul    rdx, rsi, 25B0h
0x180026a9a  cvttsd2si rcx, qword ptr [rsp+0B8h+pvarg+8]
0x180026aa1  mov     ecx, ecx
0x180026aa3  mov     rax, [rdi+20h]
0x180026aa7  mov     [rdx+rax+428h], rcx
0x180026aaf  mov     rax, [rdi+20h]
0x180026ab3  mov     [rdx+rax+430h], r12d
0x180026abb  jmp     loc_180026DF6
0x180026ac0  cmp     ecx, 17h
0x180026ac3  jnz     short loc_180026ADD
0x180026ac5  mov     r9d, 0FFFFh; unsigned __int16
0x180026acb  mov     r8, qword ptr [rsp+0B8h+pvarSrc+10h]; unsigned __int16 *
0x180026ad0  movzx   edx, si; unsigned __int16
0x180026ad3  mov     rcx, rdi; this
0x180026ad6  call    ?mdSetBaseColumn@CMetaData@@QEAAXGPEAGG@Z; CMetaData::mdSetBaseColumn(ushort,ushort *,ushort)
0x180026adb  jmp     short loc_180026B20
0x180026add  cmp     ecx, 1Ah
0x180026ae0  jnz     short loc_180026AF4
0x180026ae2  mov     r8, qword ptr [rsp+0B8h+pvarSrc+10h]; unsigned __int16 *
0x180026ae7  movzx   edx, si; unsigned __int16
0x180026aea  mov     rcx, rdi; this
0x180026aed  call    ?mdSetBaseCatalog@CMetaData@@QEAAXGPEAGG@Z; CMetaData::mdSetBaseCatalog(ushort,ushort *,ushort)
0x180026af2  jmp     short loc_180026B20
0x180026af4  cmp     ecx, 1Bh
0x180026af7  jnz     short loc_180026B0B
0x180026af9  mov     r8, qword ptr [rsp+0B8h+pvarSrc+10h]; unsigned __int16 *
0x180026afe  movzx   edx, si; unsigned __int16
0x180026b01  mov     rcx, rdi; this
0x180026b04  call    ?mdSetBaseSchema@CMetaData@@QEAAXGPEAGG@Z; CMetaData::mdSetBaseSchema(ushort,ushort *,ushort)
0x180026b09  jmp     short loc_180026B20
0x180026b0b  cmp     ecx, 18h
0x180026b0e  jnz     short loc_180026B25
0x180026b10  mov     r8, qword ptr [rsp+0B8h+pvarSrc+10h]; unsigned __int16 *
0x180026b15  movzx   edx, si; unsigned __int16
0x180026b18  mov     rcx, rdi; this
0x180026b1b  call    ?mdSetBaseTable@CMetaData@@QEAAXGPEAGG@Z; CMetaData::mdSetBaseTable(ushort,ushort *,ushort)
0x180026b20  jmp     loc_180026DF6
0x180026b25  cmp     ecx, 1Dh
0x180026b28  jnz     short loc_180026B75
0x180026b2a  lea     r9d, [rcx-12h]; vt
0x180026b2e  xor     r8d, r8d; wFlags
0x180026b31  lea     rdx, [rsp+0B8h+pvarSrc+8]; pvarSrc
0x180026b36  lea     rcx, [rsp+0B8h+pvarg]; pvargDest
0x180026b3b  call    cs:__imp_VariantChangeType
0x180026b41  mov     ebx, eax
0x180026b43  test    eax, eax
0x180026b45  jns     short loc_180026B4C
0x180026b47  jmp     loc_180026DFF
0x180026b4c  imul    rdx, rsi, 25B0h
0x180026b53  mov     rcx, [rdi+20h]
0x180026b57  movzx   eax, word ptr [rsp+0B8h+pvarg+8]
0x180026b5c  mov     [rdx+rcx+256Ch], ax
0x180026b64  mov     rax, [rdi+20h]
0x180026b68  mov     [rdx+rax+2570h], r12d
0x180026b70  jmp     loc_180026DF6
0x180026b75  cmp     ecx, 1Eh
0x180026b78  jnz     short loc_180026BDD
0x180026b7a  lea     r9d, [rcx-13h]; vt
0x180026b7e  xor     r8d, r8d; wFlags
0x180026b81  lea     rdx, [rsp+0B8h+pvarSrc+8]; pvarSrc
0x180026b86  lea     rcx, [rsp+0B8h+pvarg]; pvargDest
0x180026b8b  call    cs:__imp_VariantChangeType
0x180026b91  mov     ebx, eax
0x180026b93  test    eax, eax
0x180026b95  jns     short loc_180026B9C
0x180026b97  jmp     loc_180026DFF
0x180026b9c  cmp     word ptr [rsp+0B8h+pvarg+8], 0FFFFh
0x180026ba2  jnz     loc_180026DF6
0x180026ba8  mov     eax, 0FFFFh
0x180026bad  add     [rdi+2], ax
0x180026bb1  imul    rcx, rsi, 25B0h
0x180026bb8  mov     rax, [rdi+20h]
0x180026bbc  movups  xmm0, xmmword ptr cs:DBCOL_SPECIALCOL.Data1
0x180026bc3  movdqu  xmmword ptr [rcx+rax+860h], xmm0
0x180026bcc  mov     rax, [rdi+20h]
0x180026bd0  mov     [rcx+rax+870h], r12d
0x180026bd8  jmp     loc_180026DF6
0x180026bdd  cmp     ecx, 19h
0x180026be0  jnz     short loc_180026C2D
0x180026be2  lea     r9d, [rcx-0Eh]; vt
0x180026be6  xor     r8d, r8d; wFlags
0x180026be9  lea     rdx, [rsp+0B8h+pvarSrc+8]; pvarSrc
0x180026bee  lea     rcx, [rsp+0B8h+pvarg]; pvargDest
0x180026bf3  call    cs:__imp_VariantChangeType
0x180026bf9  mov     ebx, eax
0x180026bfb  test    eax, eax
0x180026bfd  jns     short loc_180026C04
0x180026bff  jmp     loc_180026DFF
0x180026c04  imul    rdx, rsi, 25B0h
0x180026c0b  mov     rcx, [rdi+20h]
0x180026c0f  movzx   eax, word ptr [rsp+0B8h+pvarg+8]
0x180026c14  mov     [rdx+rcx+2538h], ax
0x180026c1c  mov     rax, [rdi+20h]
0x180026c20  mov     [rdx+rax+253Ch], r12d
0x180026c28  jmp     loc_180026DF6
0x180026c2d  cmp     ecx, 1Fh
0x180026c30  jnz     loc_180026DF6
0x180026c36  mov     rcx, qword ptr [rsp+0B8h+pvarSrc+10h]; pbstr
0x180026c3b  call    cs:__imp_SysStringLen
0x180026c41  mov     r15d, eax
0x180026c44  test    eax, eax
0x180026c46  jz      loc_180026DF6
0x180026c4c  mov     dword ptr [rsp+0B8h+arg_8], r12d
0x180026c54  mov     ecx, eax
0x180026c56  shr     ecx, 1; unsigned int
0x180026c58  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x180026c5d  mov     r14, rax
0x180026c60  test    rax, rax
0x180026c63  jnz     short loc_180026C6F
0x180026c65  mov     ebx, 8007000Eh
0x180026c6a  jmp     loc_180026DFF
0x180026c6f  lea     r9, [rsp+0B8h+arg_8]; int *
0x180026c77  mov     r8d, r15d; unsigned int
0x180026c7a  mov     rdx, r14; unsigned __int8 *
0x180026c7d  mov     rcx, qword ptr [rsp+0B8h+pvarSrc+10h]; unsigned __int16 *
0x180026c82  call    ?DecodeBin@@YAJPEAGPEAEKPEAJ@Z; DecodeBin(ushort *,uchar *,ulong,long *)
0x180026c87  mov     r15d, eax
0x180026c8a  test    eax, eax
0x180026c8c  jns     short loc_180026C9E
0x180026c8e  mov     rcx, r14; unsigned __int8 *
0x180026c91  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x180026c96  mov     ebx, r15d
0x180026c99  jmp     loc_180026DFF
0x180026c9e  mov     r9d, dword ptr [rsp+0B8h+arg_8]; unsigned int
0x180026ca6  mov     r8, r14; unsigned __int8 *
0x180026ca9  movzx   edx, si; unsigned __int16
0x180026cac  mov     rcx, rdi; this
0x180026caf  call    ?mdSetCalculationInfo@CMetaData@@QEAAXGPEAEK@Z; CMetaData::mdSetCalculationInfo(ushort,uchar *,ulong)
0x180026cb4  jmp     loc_180026DF6
0x180026cb9  mov     [rsp+0B8h+arg_8], r12
0x180026cc1  imul    r14, rsi, 25B0h
0x180026cc8  mov     rax, [rdi+20h]
0x180026ccc  cmp     dword ptr [r14+rax+420h], 3
0x180026cd5  jz      short loc_180026CE0
0x180026cd7  cmp     ecx, 13h
0x180026cda  jnz     loc_180026DF6
0x180026ce0  mov     rcx, qword ptr [rsp+0B8h+pvarSrc+10h]; pbstr
0x180026ce5  call    cs:__imp_SysStringLen
0x180026ceb  mov     r8d, eax; unsigned int
0x180026cee  lea     rcx, [r15+130h]; this
0x180026cf5  lea     r9, [rsp+0B8h+arg_8]; unsigned __int64 *
0x180026cfd  mov     rdx, qword ptr [rsp+0B8h+pvarSrc+10h]; unsigned __int16 *
0x180026d02  call    ?LookUpByKey@CCollectionList@@QEAAJPEAGKPEA_K@Z; CCollectionList::LookUpByKey(ushort *,ulong,unsigned __int64 *)
0x180026d07  test    eax, eax
0x180026d09  jnz     loc_180026DF6
0x180026d0f  cmp     dword ptr [rsp+0B8h+pvarSrc+4], 12h
  ... truncated ...
```
