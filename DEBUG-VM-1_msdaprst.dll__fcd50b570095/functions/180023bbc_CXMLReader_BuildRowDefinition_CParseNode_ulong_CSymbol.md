# CXMLReader::BuildRowDefinition(CParseNode *,ulong,CSymbol *)

- ea: `0x180023bbc`
- end: `0x1800240cf`
- name: `?BuildRowDefinition@CXMLReader@@AEAAJPEAVCParseNode@@KPEAVCSymbol@@@Z`
- size: `1299`
- prototype: `__int64 __fastcall(CXMLReader *__hidden this, struct CParseNode *, unsigned int, struct CSymbol *)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180027944`

## callees

- `0x180001d94`
- `0x1800022f8`
- `0x180015fb4`
- `0x18001a6c8`
- `0x1800234a8`
- `0x1800234d4`
- `0x180023628`
- `0x180023730`
- `0x180023bbc`
- `0x1800240d8`
- `0x180025f80`
- `0x18002769c`
- `0x18002809c`
- `0x180028894`
- `0x1800288bc`
- `0x180028fb0`
- `0x18002bb0c`
- `0x18002ca58`
- `0x18002e02a`
- `0x18002e060`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x180023e29`
- `OLEAUT32!__imp_SysStringLen` at `0x180023e29`
- `OLEAUT32!__imp_VariantInit` at `0x180023d7c`
- `OLEAUT32!__imp_VariantInit` at `0x18002401b`
- `OLEAUT32!__imp_VariantInit` at `0x180023d7c`
- `OLEAUT32!__imp_VariantInit` at `0x18002401b`

## pseudocode

```c
__int64 __fastcall CXMLReader::BuildRowDefinition(
        CXMLReader *this,
        struct CParseNode *a2,
        unsigned int a3,
        struct CSymbol *a4)
{
  int v5; // r13d
  __int64 result; // rax
  CXMLRowset *v9; // rsi
  int BidObjectID; // ebx
  unsigned int v11; // eax
  unsigned int v12; // edx
  unsigned __int8 *v13; // rax
  unsigned __int8 *v14; // rbx
  unsigned int v15; // edx
  int v16; // edi
  __int64 v17; // r12
  unsigned int v18; // edx
  unsigned int v19; // r8d
  __int64 v20; // rax
  __int64 v21; // r13
  BSTR *Value; // rax
  unsigned int v23; // edx
  struct CParseNode *v24; // rcx
  unsigned __int16 **v25; // r12
  unsigned __int64 v26; // r15
  CScope *v27; // rbx
  UINT v28; // eax
  struct CSymbol *v29; // r12
  bool v30; // zf
  struct CSymbol *v31; // rdi
  unsigned __int8 *v32; // rbx
  __int64 v33; // rdi
  unsigned int v34; // eax
  int v35; // edx
  struct CSymbol *v36; // [rsp+30h] [rbp-A9h] BYREF
  CXMLRowset *v37; // [rsp+38h] [rbp-A1h] BYREF
  unsigned int v38; // [rsp+40h] [rbp-99h]
  struct CParseNode *v39; // [rsp+48h] [rbp-91h]
  VARIANTARG pvarg; // [rsp+50h] [rbp-89h] BYREF
  struct tagDBPROPSET v41; // [rsp+68h] [rbp-71h] BYREF
  _QWORD v42[6]; // [rsp+90h] [rbp-49h] BYREF
  VARIANTARG v43; // [rsp+C0h] [rbp-19h] BYREF

  v5 = *((_DWORD *)a2 + 11);
  v38 = *((_DWORD *)this + 108);
  v39 = a2;
  v37 = 0;
  LODWORD(v36) = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  if ( (int)ATL::CComObject<CXMLRowset>::CreateInstance(&v37) < 0 )
    return 0;
  v9 = v37;
  if ( (bidGblFlags & 2) != 0 && off_180048D28[0] )
  {
    BidObjectID = CBidGenericBase::GetBidObjectID((CXMLReader *)((char *)this + 496));
    v11 = CBidGenericBase::GetBidObjectID((CXMLRowset *)((char *)v9 + 112));
    bidTraceW(off_180048208[0], 1348608, off_180048D28[0], v11, BidObjectID);
  }
  (*(void (__fastcall **)(CXMLRowset *))(*(_QWORD *)v9 + 8LL))(v9);
  *(_DWORD *)a4 = 1;
  *((_QWORD *)a4 + 1) = v9;
  *((_BYTE *)a4 + 16) = 1;
  result = (*(__int64 (__fastcall **)(CXMLRowset *, _QWORD))(*(_QWORD *)v9 + 88LL))(v9, a3);
  if ( (int)result >= 0 )
  {
    v13 = MMMAlloc(0x38u, v12);
    v37 = (CXMLRowset *)v13;
    v14 = v13;
    if ( !v13 )
      return 2147942414LL;
    *(_DWORD *)v13 = 0;
    *((_QWORD *)v13 + 1) = 0;
    *((_DWORD *)v13 + 4) = 0;
    *((_DWORD *)v13 + 6) = 0;
    *((_QWORD *)v13 + 4) = 0;
    *((_QWORD *)v13 + 5) = 0;
    *((_QWORD *)v13 + 6) = 0;
    v16 = CCollectionList::Reserve((CCollectionList *)v13, 0xAu);
    if ( v16 < 0 )
    {
      CScope::`scalar deleting destructor'((CScope *)v14, v15);
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_180048D20[0] )
          bidTraceW(off_180048208[0], 1370112, off_180048D20[0], (unsigned int)v16, 1338);
      }
      return (unsigned int)v16;
    }
    v17 = (unsigned int)(v5 + 1);
    *((_QWORD *)v14 + 6) = *((_QWORD *)this + 17);
    *((_QWORD *)this + 17) = v14;
    *((_QWORD *)v9 + 79) = v14;
    LODWORD(v37) = v5 + 1;
    VariantInit(&pvarg);
    pvarg.vt = 11;
    pvarg.iVal = -1;
    CUtlProps::InternalSetProperty(
      (CXMLRowset *)((char *)v9 + 400),
      v18,
      v19,
      &pvarg,
      (int *)&v36,
      (CXMLReader *)((char *)this + 496));
    while ( 1 )
    {
      if ( (unsigned int)v17 >= v38 )
      {
        if ( *((_WORD *)v9 + 152) != *((_WORD *)v9 + 153) )
        {
          *((_DWORD *)&v41.guidPropertySet + 4) = 0;
          memset_0(v42, 0, 0x48u);
          v41.cProperties = 1;
          v41.rgProperties = (DBPROP *)v42;
          v41.guidPropertySet = DBPROPSET_ROWSET;
          v42[0] = 258;
          VariantInit(&v43);
          v35 = *((unsigned __int16 *)v9 + 152);
          v43.vt = 3;
          v43.lVal = v35 - *((unsigned __int16 *)v9 + 153);
          v16 = CUtlProps::utlSetProperties(
                  (CXMLRowset *)((char *)v9 + 400),
                  v43.cyVal.Lo,
                  1u,
                  &v41,
                  (CXMLReader *)((char *)this + 496),
                  1);
        }
        if ( *((_BYTE *)this + 472)
          || (unsigned int)CXMLRowset::AllColumnsInitialized(v9)
          || (v16 = Exit(-2147467259, 0x91u), v16 >= 0) )
        {
          *((_QWORD *)this + 17) = *(_QWORD *)(*((_QWORD *)this + 17) + 48LL);
        }
        return (unsigned int)v16;
      }
      v20 = *((_QWORD *)this + 53);
      v36 = 0;
      v21 = *(_QWORD *)(v20 + 8 * v17);
      Value = (BSTR *)CParseNode::GetValue((CParseNode *)v21);
      v24 = *(struct CParseNode **)(v21 + 16);
      v25 = Value;
      if ( v24 == v39 && *(_DWORD *)(v21 + 8) == 1 )
      {
        v26 = 0;
        if ( *(_BYTE *)(v21 + 40) != 8 )
          goto LABEL_21;
      }
      else if ( *(_BYTE *)(v21 + 40) != 8 )
      {
        if ( v24 == v39 && *(_DWORD *)(v21 + 8) == 2 )
        {
          v16 = CXMLReader::ProcessRowsetAttribute(this, (struct CParseNode *)v21, v9);
          if ( v16 < 0 )
            return (unsigned int)v16;
        }
        goto LABEL_43;
      }
      v26 = *(_QWORD *)(v21 + 16);
      if ( !v24 || *(_DWORD *)v24 == 1 )
      {
LABEL_21:
        v27 = (CScope *)*((_QWORD *)this + 17);
        v28 = SysStringLen(*Value);
        v16 = CScope::AddSymbol(v27, *v25, v28, &v36);
        if ( v16 < 0 )
          return (unsigned int)v16;
        v29 = v36;
        if ( v36 )
          goto LABEL_24;
      }
      v29 = (struct CSymbol *)v26;
LABEL_24:
      *((_QWORD *)v29 + 1) = v9;
      if ( v26 && *(_DWORD *)v26 == 1 )
      {
        v30 = *((_BYTE *)this + 472) == 0;
        v31 = *(struct CSymbol **)(v26 + 8);
        v36 = v31;
        if ( !v30 )
        {
          v16 = Exit(-2147467259, 0x91u);
          if ( v16 < 0 )
            return (unsigned int)v16;
          v31 = v36;
        }
        v32 = MMMAlloc(0x18u, v23);
        if ( !v32 )
          return (unsigned int)-2147024882;
        v33 = *(_QWORD *)(*((_QWORD *)v31 + 79) + 48LL);
        v34 = CCollectionArray::DeleteByData((CCollectionArray *)v33, v26);
        if ( v34 )
        {
          if ( (bidGblFlags & 2) != 0 && off_180048E10[0] )
            bidTraceW(off_180048218, 1027072, off_180048E10[0], v34, 1003);
        }
        else
        {
          CCollectionMap::DeleteByData((CCollectionMap *)(v33 + 24), v26);
        }
        *(_QWORD *)(*((_QWORD *)v36 + 79) + 48LL) = *((_QWORD *)this + 17);
        *(_DWORD *)v29 = 1;
        *((_QWORD *)v32 + 2) = 0;
        *((_DWORD *)v32 + 2) = 0;
        *(_QWORD *)v32 = *(_QWORD *)(v26 + 8);
        *(_BYTE *)(v26 + 16) = 0;
        CSymbol::`scalar deleting destructor'((CSymbol *)v26, 0);
      }
      else
      {
        v32 = 0;
        *(_DWORD *)v29 = 3;
      }
      v16 = CXMLReader::BuildColumnDefinition(this, (struct CParseNode *)v21, v29, (struct XMLCHAPTER *)v32);
      if ( v16 < 0 )
        return (unsigned int)v16;
      if ( v32 )
        *((_QWORD *)v29 + 1) = *(_QWORD *)v32;
LABEL_43:
      v17 = (unsigned int)((_DWORD)v37 + 1);
      LODWORD(v37) = (_DWORD)v37 + 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180023bbc  push    rbp
0x180023bbe  push    rbx
0x180023bbf  push    rsi
0x180023bc0  push    rdi
0x180023bc1  push    r12
0x180023bc3  push    r13
0x180023bc5  push    r14
0x180023bc7  push    r15
0x180023bc9  lea     rbp, [rsp-1Fh]
0x180023bce  sub     rsp, 0F8h
0x180023bd5  mov     rax, cs:__security_cookie
0x180023bdc  xor     rax, rsp
0x180023bdf  mov     [rbp+57h+var_50], rax
0x180023be3  mov     eax, [rcx+1B0h]
0x180023be9  mov     r14, rcx
0x180023bec  mov     r13d, [rdx+2Ch]
0x180023bf0  lea     rcx, [rsp+130h+var_F8]
0x180023bf5  mov     [rsp+130h+var_F0], eax
0x180023bf9  xor     r12d, r12d
0x180023bfc  xor     eax, eax
0x180023bfe  mov     [rsp+130h+var_E8], rdx
0x180023c03  xorps   xmm0, xmm0
0x180023c06  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180023c0a  mov     rdi, r9
0x180023c0d  mov     [rsp+130h+var_F8], r12
0x180023c12  mov     r15d, r8d
0x180023c15  mov     dword ptr [rsp+130h+var_100], r12d
0x180023c1a  movups  xmmword ptr [rsp+130h+pvarg], xmm0
0x180023c1f  call    ?CreateInstance@?$CComObject@VCXMLRowset@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CXMLRowset>::CreateInstance(ATL::CComObject<CXMLRowset> * *)
0x180023c24  test    eax, eax
0x180023c26  jns     short loc_180023C2F
0x180023c28  xor     eax, eax
0x180023c2a  jmp     loc_1800240AF
0x180023c2f  test    byte ptr cs:_bidGblFlags, 2
0x180023c36  mov     rsi, [rsp+130h+var_F8]
0x180023c3b  jz      short loc_180023C7F
0x180023c3d  mov     rax, cs:off_180048D28; "<CXMLReader::BuildRowDefinition|ADO|PER"...
0x180023c44  test    rax, rax
0x180023c47  jz      short loc_180023C7F
0x180023c49  lea     rcx, [r14+1F0h]; this
0x180023c50  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180023c55  lea     rcx, [rsi+70h]; this
0x180023c59  mov     ebx, eax
0x180023c5b  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180023c60  mov     r8, cs:off_180048D28; "<CXMLReader::BuildRowDefinition|ADO|PER"...
0x180023c67  mov     r9d, eax
0x180023c6a  mov     rcx, cs:off_180048208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180023c71  mov     edx, 149400h
0x180023c76  mov     dword ptr [rsp+130h+var_110], ebx
0x180023c7a  call    _bidTraceW
0x180023c7f  mov     rax, [rsi]
0x180023c82  mov     rcx, rsi
0x180023c85  mov     rax, [rax+8]
0x180023c89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023c8e  mov     dword ptr [rdi], 1
0x180023c94  mov     edx, r15d
0x180023c97  mov     [rdi+8], rsi
0x180023c9b  mov     rcx, rsi
0x180023c9e  mov     byte ptr [rdi+10h], 1
0x180023ca2  mov     rax, [rsi]
0x180023ca5  mov     rax, [rax+58h]
0x180023ca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023cae  test    eax, eax
0x180023cb0  js      loc_1800240AF
0x180023cb6  mov     ecx, 38h ; '8'; unsigned int
0x180023cbb  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x180023cc0  mov     [rsp+130h+var_F8], rax
0x180023cc5  mov     rbx, rax
0x180023cc8  test    rax, rax
0x180023ccb  jz      loc_1800240AA
0x180023cd1  mov     [rax], r12d
0x180023cd4  mov     [rax+8], r12
0x180023cd8  mov     [rax+10h], r12d
0x180023cdc  mov     [rax+18h], r12d
0x180023ce0  mov     [rax+20h], r12
0x180023ce4  mov     [rax+28h], r12
0x180023ce8  mov     [rax+30h], r12
0x180023cec  test    rax, rax
0x180023cef  jz      loc_1800240AA
0x180023cf5  mov     edx, 0Ah; unsigned int
0x180023cfa  mov     rcx, rax; this
0x180023cfd  call    ?Reserve@CCollectionList@@QEAAJK@Z; CCollectionList::Reserve(ulong)
0x180023d02  mov     edi, eax
0x180023d04  test    eax, eax
0x180023d06  jns     short loc_180023D55
0x180023d08  mov     rcx, rbx; this
0x180023d0b  call    ??_GCScope@@QEAAPEAXI@Z; CScope::`scalar deleting destructor'(uint)
0x180023d10  test    byte ptr cs:_bidGblFlags, 2
0x180023d17  jz      loc_1800240A6
0x180023d1d  mov     rcx, cs:off_180048D20; "<CXMLReader::BuildRowDefinition|ADO|ERR"...
0x180023d24  test    rcx, rcx
0x180023d27  jz      loc_1800240A6
0x180023d2d  mov     r8, cs:off_180048D20; "<CXMLReader::BuildRowDefinition|ADO|ERR"...
0x180023d34  mov     r9d, edi
0x180023d37  mov     rcx, cs:off_180048208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180023d3e  mov     edx, 14E800h
0x180023d43  mov     dword ptr [rsp+130h+var_110], 53Ah
0x180023d4b  call    _bidTraceW
0x180023d50  jmp     loc_1800240A6
0x180023d55  mov     rax, [r14+88h]
0x180023d5c  lea     r12d, [r13+1]
0x180023d60  mov     [rbx+30h], rax
0x180023d64  lea     rcx, [rsp+130h+pvarg]; pvarg
0x180023d69  mov     [r14+88h], rbx
0x180023d70  mov     [rsi+278h], rbx
0x180023d77  mov     dword ptr [rsp+130h+var_F8], r12d
0x180023d7c  call    cs:__imp_VariantInit
0x180023d82  mov     eax, 0Bh
0x180023d87  lea     rbx, [r14+1F0h]
0x180023d8e  mov     word ptr [rsp+130h+pvarg], ax
0x180023d93  lea     rcx, [rsi+190h]; this
0x180023d9a  or      eax, 0FFFFFFFFh
0x180023d9d  mov     [rsp+130h+var_108], rbx; struct CBidGenericBase *
0x180023da2  mov     word ptr [rsp+130h+pvarg+8], ax
0x180023da7  lea     r9, [rsp+130h+pvarg]; struct tagVARIANT *
0x180023dac  lea     rax, [rsp+130h+var_100]
0x180023db1  mov     [rsp+130h+var_110], rax; int *
0x180023db6  call    ?InternalSetProperty@CUtlProps@@QEAAXKKPEAUtagVARIANT@@PEAHAEBVCBidGenericBase@@@Z; CUtlProps::InternalSetProperty(ulong,ulong,tagVARIANT *,int *,CBidGenericBase const &)
0x180023dbb  cmp     r12d, [rsp+130h+var_F0]
0x180023dc0  jnb     loc_180023FCA
0x180023dc6  mov     rax, [r14+1A8h]
0x180023dcd  mov     [rsp+130h+var_100], 0
0x180023dd6  mov     r13, [rax+r12*8]
0x180023dda  mov     rcx, r13; this
0x180023ddd  call    ?GetValue@CParseNode@@QEAAAEAVCComBSTR@ATL@@XZ; CParseNode::GetValue(void)
0x180023de2  mov     rcx, [r13+10h]
0x180023de6  mov     r12, rax
0x180023de9  mov     rax, [rsp+130h+var_E8]
0x180023dee  cmp     rcx, rax
0x180023df1  jnz     short loc_180023E06
0x180023df3  cmp     dword ptr [r13+8], 1
0x180023df8  jnz     short loc_180023E06
0x180023dfa  xor     r15d, r15d
0x180023dfd  cmp     byte ptr [r13+28h], 8
0x180023e02  jnz     short loc_180023E1E
0x180023e04  jmp     short loc_180023E11
0x180023e06  cmp     byte ptr [r13+28h], 8
0x180023e0b  jnz     loc_180023F8A
0x180023e11  mov     r15, rcx
0x180023e14  test    rcx, rcx
0x180023e17  jz      short loc_180023E1E
0x180023e19  cmp     dword ptr [rcx], 1
0x180023e1c  jnz     short loc_180023E57
0x180023e1e  mov     rcx, [r12]; pbstr
0x180023e22  mov     rbx, [r14+88h]
0x180023e29  call    cs:__imp_SysStringLen
0x180023e2f  mov     rdx, [r12]; unsigned __int16 *
0x180023e33  lea     r9, [rsp+130h+var_100]; struct CSymbol **
0x180023e38  mov     r8d, eax; unsigned int
0x180023e3b  mov     rcx, rbx; this
0x180023e3e  call    ?AddSymbol@CScope@@QEAAJPEAGKPEAPEAVCSymbol@@@Z; CScope::AddSymbol(ushort *,ulong,CSymbol * *)
0x180023e43  mov     edi, eax
0x180023e45  test    eax, eax
0x180023e47  js      loc_1800240A6
0x180023e4d  mov     r12, [rsp+130h+var_100]
0x180023e52  test    r12, r12
0x180023e55  jnz     short loc_180023E5A
0x180023e57  mov     r12, r15
0x180023e5a  mov     [r12+8], rsi
0x180023e5f  test    r15, r15
0x180023e62  jz      loc_180023F56
0x180023e68  cmp     dword ptr [r15], 1
0x180023e6c  jnz     loc_180023F56
0x180023e72  cmp     byte ptr [r14+1D8h], 0
0x180023e7a  mov     rdi, [r15+8]
0x180023e7e  mov     [rsp+130h+var_100], rdi
0x180023e83  jz      short loc_180023EA3
0x180023e85  mov     edx, 91h; unsigned int
0x180023e8a  mov     ecx, 80004005h; int
0x180023e8f  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180023e94  mov     edi, eax
0x180023e96  test    eax, eax
0x180023e98  js      loc_1800240A6
0x180023e9e  mov     rdi, [rsp+130h+var_100]
0x180023ea3  mov     ecx, 18h; unsigned int
0x180023ea8  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x180023ead  mov     rbx, rax
0x180023eb0  test    rax, rax
0x180023eb3  jz      loc_180023FC0
0x180023eb9  mov     rcx, [rdi+278h]
0x180023ec0  mov     rdx, r15; unsigned __int64
0x180023ec3  mov     rdi, [rcx+30h]
0x180023ec7  mov     rcx, rdi; this
0x180023eca  call    ?DeleteByData@CCollectionArray@@QEAAJ_K@Z; CCollectionArray::DeleteByData(unsigned __int64)
0x180023ecf  test    eax, eax
0x180023ed1  jz      short loc_180023F0D
0x180023ed3  test    byte ptr cs:_bidGblFlags, 2
0x180023eda  jz      short loc_180023F19
0x180023edc  mov     rcx, cs:off_180048E10; "<CCollectionList::DeleteByData|ADO|ERR>"...
0x180023ee3  test    rcx, rcx
0x180023ee6  jz      short loc_180023F19
0x180023ee8  mov     r8, cs:off_180048E10; "<CCollectionList::DeleteByData|ADO|ERR>"...
0x180023eef  mov     r9d, eax
0x180023ef2  mov     rcx, cs:off_180048218; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180023ef9  mov     edx, 0FAC00h
0x180023efe  mov     dword ptr [rsp+130h+var_110], 3EBh
0x180023f06  call    _bidTraceW
0x180023f0b  jmp     short loc_180023F19
0x180023f0d  lea     rcx, [rdi+18h]; this
0x180023f11  mov     rdx, r15; unsigned __int64
0x180023f14  call    ?DeleteByData@CCollectionMap@@QEAAJ_K@Z; CCollectionMap::DeleteByData(unsigned __int64)
0x180023f19  mov     rax, [r14+88h]
0x180023f20  mov     rcx, r15; this
0x180023f23  mov     rdx, [rsp+130h+var_100]
0x180023f28  mov     rdx, [rdx+278h]
0x180023f2f  mov     [rdx+30h], rax
0x180023f33  xor     edx, edx; unsigned int
0x180023f35  mov     dword ptr [r12], 1
0x180023f3d  mov     [rbx+10h], rdx
0x180023f41  mov     [rbx+8], edx
0x180023f44  mov     rax, [r15+8]
0x180023f48  mov     [rbx], rax
0x180023f4b  mov     [r15+10h], dl
0x180023f4f  call    ??_GCSymbol@@QEAAPEAXI@Z; CSymbol::`scalar deleting destructor'(uint)
0x180023f54  jmp     short loc_180023F60
0x180023f56  xor     ebx, ebx
0x180023f58  mov     dword ptr [r12], 3
0x180023f60  mov     r9, rbx; struct XMLCHAPTER *
0x180023f63  mov     r8, r12; struct CSymbol *
0x180023f66  mov     rdx, r13; struct CParseNode *
0x180023f69  mov     rcx, r14; this
0x180023f6c  call    ?BuildColumnDefinition@CXMLReader@@AEAAJPEAVCParseNode@@PEAVCSymbol@@PEAVXMLCHAPTER@@@Z; CXMLReader::BuildColumnDefinition(CParseNode *,CSymbol *,XMLCHAPTER *)
0x180023f71  mov     edi, eax
0x180023f73  test    eax, eax
0x180023f75  js      loc_1800240A6
0x180023f7b  test    rbx, rbx
0x180023f7e  jz      short loc_180023FAE
0x180023f80  mov     rax, [rbx]
0x180023f83  mov     [r12+8], rax
0x180023f88  jmp     short loc_180023FAE
0x180023f8a  cmp     rcx, rax
0x180023f8d  jnz     short loc_180023FAE
0x180023f8f  cmp     dword ptr [r13+8], 2
0x180023f94  jnz     short loc_180023FAE
0x180023f96  mov     r8, rsi; struct CXMLRowset *
0x180023f99  mov     rdx, r13; struct CParseNode *
0x180023f9c  mov     rcx, r14; this
0x180023f9f  call    ?ProcessRowsetAttribute@CXMLReader@@AEAAJPEAVCParseNode@@PEAVCXMLRowset@@@Z; CXMLReader::ProcessRowsetAttribute(CParseNode *,CXMLRowset *)
0x180023fa4  mov     edi, eax
0x180023fa6  test    eax, eax
0x180023fa8  js      loc_1800240A6
0x180023fae  mov     r12d, dword ptr [rsp+130h+var_F8]
0x180023fb3  inc     r12d
0x180023fb6  mov     dword ptr [rsp+130h+var_F8], r12d
0x180023fbb  jmp     loc_180023DBB
0x180023fc0  mov     edi, 8007000Eh
0x180023fc5  jmp     loc_1800240A6
0x180023fca  movzx   ecx, word ptr [rsi+132h]
0x180023fd1  cmp     [rsi+130h], cx
0x180023fd8  jz      loc_180024069
0x180023fde  xor     edx, edx; Val
0x180023fe0  mov     dword ptr [rbp+57h+var_C8+1Ch], 0
0x180023fe7  lea     rcx, [rbp+57h+var_A0]; void *
0x180023feb  lea     r8d, [rdx+48h]; Size
0x180023fef  call    memset_0
0x180023ff4  movups  xmm0, xmmword ptr cs:DBPROPSET_ROWSET.Data1
0x180023ffb  lea     rax, [rbp+57h+var_A0]
0x180023fff  mov     [rbp+57h+var_C8.cProperties], 1
0x180024006  lea     rcx, [rbp+57h+var_70]; pvarg
0x18002400a  mov     [rbp+57h+var_C8.rgProperties], rax
0x18002400e  movdqu  xmmword ptr [rbp+57h+var_C8.guidPropertySet.Data1], xmm0
0x180024013  mov     [rbp+57h+var_A0], 102h
0x18002401b  call    cs:__imp_VariantInit
0x180024021  movzx   edx, word ptr [rsi+130h]
0x180024028  lea     r9, [rbp+57h+var_C8]; struct tagDBPROPSET *
0x18002402c  mov     eax, 3
0x180024031  mov     dword ptr [rsp+130h+var_108], 1; int
0x180024039  mov     word ptr [rbp+57h+var_70], ax
0x18002403d  lea     rcx, [rsi+190h]; this
0x180024044  movzx   eax, word ptr [rsi+132h]
0x18002404b  mov     r8d, 1; unsigned int
0x180024051  sub     edx, eax; unsigned int
0x180024053  lea     rax, [r14+1F0h]
0x18002405a  mov     [rsp+130h+var_110], rax; struct CBidGenericBase *
0x18002405f  mov     dword ptr [rbp+57h+var_70+8], edx
0x180024062  call    ?utlSetProperties@CUtlProps@@QEAAJKKQEBUtagDBPROPSET@@AEBVCBidGenericBase@@H@Z; CUtlProps::utlSetProperties(ulong,ulong,tagDBPROPSET const * const,CBidGenericBase const &,int)
0x180024067  mov     edi, eax
0x180024069  cmp     byte ptr [r14+1D8h], 0
0x180024071  jnz     short loc_180024094
0x180024073  mov     rcx, rsi; this
0x180024076  call    ?AllColumnsInitialized@CXMLRowset@@QEAAHXZ; CXMLRowset::AllColumnsInitialized(void)
0x18002407b  test    eax, eax
0x18002407d  jnz     short loc_180024094
0x18002407f  mov     edx, 91h; unsigned int
0x180024084  mov     ecx, 80004005h; int
0x180024089  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x18002408e  mov     edi, eax
0x180024090  test    eax, eax
0x180024092  js      short loc_1800240A6
0x180024094  mov     rax, [r14+88h]
0x18002409b  mov     rcx, [rax+30h]
0x18002409f  mov     [r14+88h], rcx
0x1800240a6  mov     eax, edi
0x1800240a8  jmp     short loc_1800240AF
0x1800240aa  mov     eax, 8007000Eh
0x1800240af  mov     rcx, [rbp+57h+var_50]
0x1800240b3  xor     rcx, rsp; StackCookie
0x1800240b6  call    __security_check_cookie
0x1800240bb  add     rsp, 0F8h
0x1800240c2  pop     r15
  ... truncated ...
```
