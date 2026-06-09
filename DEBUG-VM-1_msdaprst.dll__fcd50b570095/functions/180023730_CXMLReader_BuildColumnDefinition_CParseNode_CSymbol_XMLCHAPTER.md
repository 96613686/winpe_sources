# CXMLReader::BuildColumnDefinition(CParseNode *,CSymbol *,XMLCHAPTER *)

- ea: `0x180023730`
- end: `0x180023bb3`
- name: `?BuildColumnDefinition@CXMLReader@@AEAAJPEAVCParseNode@@PEAVCSymbol@@PEAVXMLCHAPTER@@@Z`
- size: `1155`
- prototype: `__int64 __fastcall(CXMLReader *__hidden this, struct CParseNode *, struct CSymbol *, struct XMLCHAPTER *)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180023bbc`
- `0x180027944`

## callees

- `0x180004038`
- `0x1800041ac`
- `0x180004fe0`
- `0x180015fb4`
- `0x180023730`
- `0x18002595c`
- `0x180025f80`
- `0x180026270`
- `0x180026810`
- `0x180026e24`
- `0x18002867c`
- `0x180028ee0`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18002376d`
- `OLEAUT32!__imp_SysStringLen` at `0x1800237c6`
- `OLEAUT32!__imp_SysStringLen` at `0x180023873`
- `OLEAUT32!__imp_SysStringLen` at `0x180023aef`
- `OLEAUT32!__imp_SysStringLen` at `0x18002376d`
- `OLEAUT32!__imp_SysStringLen` at `0x1800237c6`
- `OLEAUT32!__imp_SysStringLen` at `0x180023873`
- `OLEAUT32!__imp_SysStringLen` at `0x180023aef`

## pseudocode

```c
__int64 __fastcall CXMLReader::BuildColumnDefinition(
        CXMLReader *this,
        struct CParseNode *a2,
        struct CSymbol *a3,
        struct XMLCHAPTER *a4)
{
  __int64 v4; // rsi
  BSTR *Value; // r12
  UINT v8; // eax
  unsigned __int16 *v9; // rdx
  __int64 v10; // rbx
  OLECHAR *v11; // rcx
  __int64 v12; // r13
  unsigned __int16 v13; // ax
  __int64 v14; // r8
  UINT v15; // eax
  unsigned int v16; // r12d
  unsigned __int16 v17; // cx
  struct XMLCHAPTER *v18; // rdx
  CXMLReader *v19; // rcx
  unsigned int v20; // eax
  __int64 v21; // rbx
  __int64 v22; // rdx
  int v23; // eax
  __int64 v24; // r14
  unsigned __int16 *v25; // rbp
  __int64 v26; // rbx
  UINT v27; // eax
  __int64 v28; // rcx
  unsigned __int16 *Name; // rcx
  __int16 v30; // r9
  __int64 v31; // rax
  int v32; // ecx
  __int64 v33; // rax
  unsigned int v34; // ecx
  BSTR *v36; // [rsp+40h] [rbp-48h]
  unsigned int i; // [rsp+40h] [rbp-48h]
  unsigned __int64 v38; // [rsp+A0h] [rbp+18h] BYREF
  struct XMLCHAPTER *v39; // [rsp+A8h] [rbp+20h]

  v39 = a4;
  v4 = *((_QWORD *)a3 + 1);
  Value = (BSTR *)CParseNode::GetValue(a2);
  v36 = Value;
  v8 = SysStringLen(*Value);
  v9 = *Value;
  v38 = 0;
  if ( (unsigned int)CCollectionList::LookUpByKey((CCollectionList *)(v4 + 552), v9, v8, &v38) )
  {
    v11 = *Value;
    LOWORD(v38) = *(_WORD *)(v4 + 608);
    v10 = (unsigned __int16)v38;
    v12 = (unsigned __int16)(v38 - 1);
    v13 = SysStringLen(v11);
    CMetaData::mdSetName((CMetaData *)(v4 + 304), v12, *Value, v13);
    v14 = 9648 * v12;
    *(_DWORD *)(v14 + *(_QWORD *)(v4 + 336) + 1092) = 64;
    *(_DWORD *)(v14 + *(_QWORD *)(v4 + 336) + 1096) = 0;
    *(_DWORD *)(v14 + *(_QWORD *)(v4 + 336) + 1080) = 3;
    *(_DWORD *)(v14 + *(_QWORD *)(v4 + 336) + 1088) = 3;
    *(_QWORD *)(v14 + *(_QWORD *)(v4 + 336) + 1064) = 0xFFFFFFFFLL;
    *(_DWORD *)(v14 + *(_QWORD *)(v4 + 336) + 1072) = 0;
    *(_WORD *)(v14 + *(_QWORD *)(v4 + 336) + 9580) = 0;
    *(_DWORD *)(v14 + *(_QWORD *)(v4 + 336) + 9584) = 0;
    *(_QWORD *)(v14 + *(_QWORD *)(v4 + 336) + 1040) = v10;
    *(_DWORD *)(v14 + *(_QWORD *)(v4 + 336) + 1048) = 0;
    v15 = SysStringLen(*Value);
    v16 = CCollectionList::Append((CCollectionList *)(v4 + 552), *Value, v15, (unsigned int)v10);
    if ( (v16 & 0x80000000) != 0 )
      return v16;
    *(_DWORD *)(v4 + 608) = (unsigned __int16)v10 + 1;
    v17 = v10;
  }
  else
  {
    v17 = v38;
    v16 = 0;
    LOWORD(v12) = v38 - 1;
  }
  v18 = v39;
  if ( !v39 )
  {
    if ( !(unsigned __int8)CXMLReader::IsMatch(
                             this,
                             *((_QWORD *)a2 + 4),
                             *(unsigned int *)a2,
                             *((unsigned int *)a2 + 1),
                             &wszAttributeType,
                             13,
                             1)
      && !(unsigned __int8)CXMLReader::IsMatch(
                             this,
                             *((_QWORD *)a2 + 4),
                             *(unsigned int *)a2,
                             *((unsigned int *)a2 + 1),
                             &wszElementType,
                             11,
                             1) )
    {
      *((_BYTE *)this + 472) = 1;
      return v16;
    }
    v20 = *((_DWORD *)this + 108);
    LODWORD(v21) = *((_DWORD *)a2 + 11);
    for ( i = v20; ; v20 = i )
    {
      v21 = (unsigned int)(v21 + 1);
      if ( (unsigned int)v21 >= v20 )
      {
        CXMLReader::FixupType(v19, (struct CMetaData *)(v4 + 304), v12);
        v24 = 4LL * (unsigned __int16)v38;
        *(_DWORD *)(v24 + *(_QWORD *)(v4 + 184)) = CMetaData::mdGetSize((CMetaData *)(v4 + 304), v12);
        goto LABEL_27;
      }
      v22 = *(_QWORD *)(*((_QWORD *)this + 53) + 8 * v21);
      if ( *(struct CParseNode **)(v22 + 16) == a2 )
      {
        if ( *(_DWORD *)(v22 + 8) == 1 )
        {
          v23 = CXMLReader::ProcessColumnChild(this, (struct CParseNode *)v22, v12, (struct CMetaData *)(v4 + 304));
        }
        else
        {
          if ( *(_DWORD *)(v22 + 8) != 2 )
            continue;
          v23 = CXMLReader::ProcessColumnAttribute(this, (struct CParseNode *)v22, v12, (struct CMetaData *)(v4 + 304));
        }
        v16 = v23;
        if ( v23 < 0 )
          return v16;
      }
    }
  }
  v25 = *(unsigned __int16 **)(*(_QWORD *)v39 + 640LL);
  v24 = 4LL * v17;
  v26 = 9648LL * (unsigned __int16)v12;
  *(_WORD *)(v26 + *(_QWORD *)(v4 + 336) + 1052) = 136;
  *(_DWORD *)(v26 + *(_QWORD *)(v4 + 336) + 1056) = 0;
  *(_DWORD *)(v24 + *(_QWORD *)(v4 + 184)) = 8;
  *(_QWORD *)(v26 + *(_QWORD *)(v4 + 336) + 1064) = 8;
  *(_DWORD *)(v26 + *(_QWORD *)(v4 + 336) + 1072) = 0;
  *(_DWORD *)(v26 + *(_QWORD *)(v4 + 336) + 1092) = 8208;
  *(_DWORD *)(v26 + *(_QWORD *)(v4 + 336) + 1096) = 0;
  *(_QWORD *)(*(_QWORD *)(v4 + 544) + 8LL * v17) = v18;
  if ( !*(_DWORD *)(*(_QWORD *)v18 + 616LL) )
  {
    v16 = Exit(-2147467259, 0x91u);
    if ( (v16 & 0x80000000) != 0 )
      return v16;
    v18 = v39;
  }
  *(_QWORD *)(v26 + *(_QWORD *)(v4 + 336) + 9616) = *(unsigned int *)(*(_QWORD *)v18 + 616LL);
  *(_QWORD *)(v26 + *(_QWORD *)(v4 + 336) + 9600) = *(_QWORD *)(*(_QWORD *)v18 + 624LL);
  *(_DWORD *)(v26 + *(_QWORD *)(v4 + 336) + 9608) = 0;
  *(_DWORD *)(*(_QWORD *)v18 + 616LL) = 0;
  *(_QWORD *)(*(_QWORD *)v18 + 624LL) = 0;
  if ( v25 )
  {
    v27 = SysStringLen(*v36);
    v28 = -1;
    do
      ++v28;
    while ( v25[v28] );
    if ( !(unsigned __int8)CXMLReader::IsMatch(this, *v36, v27, 0, v25, v28, 6) )
      CMetaData::mdSetName((CMetaData *)(v4 + 304), v12, v25, 0xFFFFu);
  }
LABEL_27:
  *(_DWORD *)(v24 + *(_QWORD *)(v4 + 176)) = 0;
  Name = CMetaData::mdGetName((CMetaData *)(v4 + 304), v12);
  v31 = -1;
  do
    ++v31;
  while ( Name[v31] != v30 );
  v32 = *(_DWORD *)(v4 + 216);
  *(_DWORD *)(v4 + 268) += v31 + 2;
  v33 = *(_QWORD *)(v4 + 160);
  v34 = (v32 + 7) & 0xFFFFFFF8;
  *(_DWORD *)(v4 + 216) = v34;
  *(_DWORD *)(v24 + v33) = v34;
  *(_DWORD *)(v4 + 216) += 16;
  return v16;
}

```

## disassembly

```asm
0x180023730  mov     [rsp+arg_0], rbx
0x180023735  mov     [rsp+arg_18], r9
0x18002373a  push    rbp
0x18002373b  push    rsi
0x18002373c  push    rdi
0x18002373d  push    r12
0x18002373f  push    r13
0x180023741  push    r14
0x180023743  push    r15
0x180023745  sub     rsp, 50h
0x180023749  mov     rsi, [r8+8]
0x18002374d  mov     r15, rcx
0x180023750  mov     rcx, rdx; this
0x180023753  mov     r14, rdx
0x180023756  call    ?GetValue@CParseNode@@QEAAAEAVCComBSTR@ATL@@XZ; CParseNode::GetValue(void)
0x18002375b  mov     r12, rax
0x18002375e  mov     [rsp+88h+var_48], rax
0x180023763  lea     rdi, [rsi+130h]
0x18002376a  mov     rcx, [rax]; pbstr
0x18002376d  call    cs:__imp_SysStringLen
0x180023773  mov     rdx, [r12]; unsigned __int16 *
0x180023777  lea     rcx, [rsi+228h]; this
0x18002377e  mov     r8d, eax; unsigned int
0x180023781  mov     [rsp+88h+arg_10], 0
0x18002378d  lea     r9, [rsp+88h+arg_10]; unsigned __int64 *
0x180023795  call    ?LookUpByKey@CCollectionList@@QEAAJPEAGKPEA_K@Z; CCollectionList::LookUpByKey(ushort *,ulong,unsigned __int64 *)
0x18002379a  xor     r9d, r9d
0x18002379d  lea     ebp, [r9+1]
0x1800237a1  test    eax, eax
0x1800237a3  jz      loc_1800238AD
0x1800237a9  movzx   ebx, word ptr [rsi+260h]
0x1800237b0  mov     rcx, [r12]; pbstr
0x1800237b4  movzx   eax, bx
0x1800237b7  sub     ax, bp
0x1800237ba  mov     word ptr [rsp+88h+arg_10], bx
0x1800237c2  movzx   r13d, ax
0x1800237c6  call    cs:__imp_SysStringLen
0x1800237cc  mov     r8, [r12]; unsigned __int16 *
0x1800237d0  movzx   edx, r13w; unsigned __int16
0x1800237d4  movzx   r9d, ax; unsigned __int16
0x1800237d8  mov     rcx, rdi; this
0x1800237db  call    ?mdSetName@CMetaData@@QEAAXGPEAGG@Z; CMetaData::mdSetName(ushort,ushort *,ushort)
0x1800237e0  mov     rax, [rdi+20h]
0x1800237e4  lea     ecx, [rbp+2]
0x1800237e7  imul    r8, r13, 25B0h
0x1800237ee  xor     r9d, r9d
0x1800237f1  mov     dword ptr [r8+rax+444h], 40h ; '@'
0x1800237fd  mov     rax, [rdi+20h]
0x180023801  mov     [r8+rax+448h], r9d
0x180023809  mov     rax, [rdi+20h]
0x18002380d  mov     [r8+rax+438h], ecx
0x180023815  mov     rax, [rdi+20h]
0x180023819  mov     [r8+rax+440h], ecx
0x180023821  mov     ecx, 0FFFFFFFFh
0x180023826  mov     rax, [rdi+20h]
0x18002382a  mov     [r8+rax+428h], rcx
0x180023832  mov     rax, [rdi+20h]
0x180023836  mov     [r8+rax+430h], r9d
0x18002383e  mov     rdx, [rdi+20h]
0x180023842  mov     [r8+rdx+256Ch], r9w
0x18002384b  mov     rax, [rdi+20h]
0x18002384f  mov     [r8+rax+2570h], r9d
0x180023857  mov     rax, [rdi+20h]
0x18002385b  mov     [r8+rax+410h], rbx
0x180023863  mov     rax, [rdi+20h]
0x180023867  mov     [r8+rax+418h], r9d
0x18002386f  mov     rcx, [r12]; pbstr
0x180023873  call    cs:__imp_SysStringLen
0x180023879  mov     rdx, [r12]; unsigned __int16 *
0x18002387d  lea     rcx, [rsi+228h]; this
0x180023884  mov     r8d, eax; unsigned int
0x180023887  mov     r9d, ebx; unsigned __int64
0x18002388a  call    ?Append@CCollectionList@@QEAAJPEAGK_K@Z; CCollectionList::Append(ushort *,ulong,unsigned __int64)
0x18002388f  xor     r9d, r9d
0x180023892  mov     r12d, eax
0x180023895  test    eax, eax
0x180023897  js      loc_180023B98
0x18002389d  movzx   ecx, bx
0x1800238a0  add     ecx, ebp
0x1800238a2  mov     [rsi+260h], ecx
0x1800238a8  movzx   ecx, bx
0x1800238ab  jmp     short loc_1800238C8
0x1800238ad  movzx   ecx, word ptr [rsp+88h+arg_10]
0x1800238b5  mov     r12d, r9d
0x1800238b8  movzx   r13d, cx
0x1800238bc  mov     word ptr [rsp+88h+arg_10], cx
0x1800238c4  sub     r13w, bp
0x1800238c8  mov     rdx, [rsp+88h+arg_18]
0x1800238d0  test    rdx, rdx
0x1800238d3  jnz     loc_1800239DD
0x1800238d9  mov     r9d, [r14+4]
0x1800238dd  lea     rax, ?wszAttributeType@@3PAGA; "AttributeType"
0x1800238e4  mov     r8d, [r14]
0x1800238e7  mov     rcx, r15
0x1800238ea  mov     rdx, [r14+20h]
0x1800238ee  mov     [rsp+88h+var_58], ebp
0x1800238f2  mov     [rsp+88h+var_60], 0Dh
0x1800238fa  mov     [rsp+88h+var_68], rax
0x1800238ff  call    ?IsMatch@CXMLReader@@AEAA_NPEBGKKPEAGKW4_NAMESPACETYPE@@@Z; CXMLReader::IsMatch(ushort const *,ulong,ulong,ushort *,ulong,_NAMESPACETYPE)
0x180023904  test    al, al
0x180023906  jnz     short loc_180023943
0x180023908  mov     r9d, [r14+4]
0x18002390c  lea     rax, ?wszElementType@@3PAGA; "ElementType"
0x180023913  mov     r8d, [r14]
0x180023916  mov     rcx, r15
0x180023919  mov     rdx, [r14+20h]
0x18002391d  mov     [rsp+88h+var_58], ebp
0x180023921  mov     [rsp+88h+var_60], 0Bh
0x180023929  mov     [rsp+88h+var_68], rax
0x18002392e  call    ?IsMatch@CXMLReader@@AEAA_NPEBGKKPEAGKW4_NAMESPACETYPE@@@Z; CXMLReader::IsMatch(ushort const *,ulong,ulong,ushort *,ulong,_NAMESPACETYPE)
0x180023933  test    al, al
0x180023935  jnz     short loc_180023943
0x180023937  mov     [r15+1D8h], bpl
0x18002393e  jmp     loc_180023B98
0x180023943  mov     eax, [r15+1B0h]
0x18002394a  mov     ebx, [r14+2Ch]
0x18002394e  mov     dword ptr [rsp+88h+var_48], eax
0x180023952  add     ebx, ebp
0x180023954  cmp     ebx, eax
0x180023956  jnb     short loc_1800239A5
0x180023958  mov     rax, [r15+1A8h]
0x18002395f  mov     rdx, [rax+rbx*8]; struct CParseNode *
0x180023963  cmp     [rdx+10h], r14
0x180023967  jnz     short loc_18002399F
0x180023969  cmp     [rdx+8], ebp
0x18002396c  jnz     short loc_18002397F
0x18002396e  mov     r9, rdi; struct CMetaData *
0x180023971  movzx   r8d, r13w; unsigned __int16
0x180023975  mov     rcx, r15; this
0x180023978  call    ?ProcessColumnChild@CXMLReader@@AEAAJPEAVCParseNode@@GPEAVCMetaData@@@Z; CXMLReader::ProcessColumnChild(CParseNode *,ushort,CMetaData *)
0x18002397d  jmp     short loc_180023994
0x18002397f  cmp     dword ptr [rdx+8], 2
0x180023983  jnz     short loc_18002399F
0x180023985  mov     r9, rdi; struct CMetaData *
0x180023988  movzx   r8d, r13w; unsigned __int16
0x18002398c  mov     rcx, r15; this
0x18002398f  call    ?ProcessColumnAttribute@CXMLReader@@AEAAJPEAVCParseNode@@GPEAVCMetaData@@@Z; CXMLReader::ProcessColumnAttribute(CParseNode *,ushort,CMetaData *)
0x180023994  mov     r12d, eax
0x180023997  test    eax, eax
0x180023999  js      loc_180023B98
0x18002399f  mov     eax, dword ptr [rsp+88h+var_48]
0x1800239a3  jmp     short loc_180023952
0x1800239a5  movzx   r8d, r13w; unsigned __int16
0x1800239a9  mov     rdx, rdi; struct CMetaData *
0x1800239ac  call    ?FixupType@CXMLReader@@AEAAXPEAVCMetaData@@G@Z; CXMLReader::FixupType(CMetaData *,ushort)
0x1800239b1  movzx   eax, word ptr [rsp+88h+arg_10]
0x1800239b9  movzx   edx, r13w; unsigned __int16
0x1800239bd  mov     rcx, rdi; this
0x1800239c0  lea     r14, ds:0[rax*4]
0x1800239c8  call    ?mdGetSize@CMetaData@@QEAAKG@Z; CMetaData::mdGetSize(ushort)
0x1800239cd  mov     rcx, [rsi+0B8h]
0x1800239d4  mov     [r14+rcx], eax
0x1800239d8  jmp     loc_180023B40
0x1800239dd  mov     rax, [rdx]
0x1800239e0  mov     r8d, 8
0x1800239e6  movzx   ecx, cx
0x1800239e9  mov     rbp, [rax+280h]
0x1800239f0  movzx   eax, r13w
0x1800239f4  lea     r14, ds:0[rcx*4]
0x1800239fc  imul    rbx, rax, 25B0h
0x180023a03  mov     rax, [rdi+20h]
0x180023a07  mov     word ptr [rbx+rax+41Ch], 88h
0x180023a11  mov     rax, [rdi+20h]
0x180023a15  mov     [rbx+rax+420h], r9d
0x180023a1d  mov     rax, [rsi+0B8h]
0x180023a24  mov     [r14+rax], r8d
0x180023a28  mov     rax, [rdi+20h]
0x180023a2c  mov     [rbx+rax+428h], r8
0x180023a34  mov     rax, [rdi+20h]
0x180023a38  mov     [rbx+rax+430h], r9d
0x180023a40  mov     rax, [rdi+20h]
0x180023a44  mov     dword ptr [rbx+rax+444h], 2010h
0x180023a4f  mov     rax, [rdi+20h]
0x180023a53  mov     [rbx+rax+448h], r9d
0x180023a5b  mov     rax, [rsi+220h]
0x180023a62  mov     [rax+rcx*8], rdx
0x180023a66  mov     rax, [rdx]
0x180023a69  cmp     [rax+268h], r9d
0x180023a70  jnz     short loc_180023A97
0x180023a72  mov     edx, 91h; unsigned int
0x180023a77  mov     ecx, 80004005h; int
0x180023a7c  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180023a81  xor     r9d, r9d
0x180023a84  mov     r12d, eax
0x180023a87  test    eax, eax
0x180023a89  js      loc_180023B98
0x180023a8f  mov     rdx, [rsp+88h+arg_18]
0x180023a97  mov     rax, [rdx]
0x180023a9a  mov     ecx, [rax+268h]
0x180023aa0  mov     rax, [rdi+20h]
0x180023aa4  mov     [rbx+rax+2590h], rcx
0x180023aac  mov     rax, [rdx]
0x180023aaf  mov     rcx, [rdi+20h]
0x180023ab3  mov     rax, [rax+270h]
0x180023aba  mov     [rbx+rcx+2580h], rax
0x180023ac2  mov     rax, [rdi+20h]
0x180023ac6  mov     [rbx+rax+2588h], r9d
0x180023ace  mov     rax, [rdx]
0x180023ad1  mov     [rax+268h], r9d
0x180023ad8  mov     rax, [rdx]
0x180023adb  mov     [rax+270h], r9
0x180023ae2  test    rbp, rbp
0x180023ae5  jz      short loc_180023B40
0x180023ae7  mov     rbx, [rsp+88h+var_48]
0x180023aec  mov     rcx, [rbx]; pbstr
0x180023aef  call    cs:__imp_SysStringLen
0x180023af5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180023af9  xor     edx, edx
0x180023afb  inc     rcx
0x180023afe  cmp     [rbp+rcx*2+0], dx
0x180023b03  jnz     short loc_180023AFB
0x180023b05  mov     rdx, [rbx]
0x180023b08  xor     r9d, r9d
0x180023b0b  mov     [rsp+88h+var_58], 6
0x180023b13  mov     r8d, eax
0x180023b16  mov     [rsp+88h+var_60], ecx
0x180023b1a  mov     rcx, r15
0x180023b1d  mov     [rsp+88h+var_68], rbp
0x180023b22  call    ?IsMatch@CXMLReader@@AEAA_NPEBGKKPEAGKW4_NAMESPACETYPE@@@Z; CXMLReader::IsMatch(ushort const *,ulong,ulong,ushort *,ulong,_NAMESPACETYPE)
0x180023b27  test    al, al
0x180023b29  jnz     short loc_180023B40
0x180023b2b  mov     r9d, 0FFFFh; unsigned __int16
0x180023b31  mov     r8, rbp; unsigned __int16 *
0x180023b34  movzx   edx, r13w; unsigned __int16
0x180023b38  mov     rcx, rdi; this
0x180023b3b  call    ?mdSetName@CMetaData@@QEAAXGPEAGG@Z; CMetaData::mdSetName(ushort,ushort *,ushort)
0x180023b40  mov     rax, [rsi+0B0h]
0x180023b47  xor     r9d, r9d
0x180023b4a  movzx   edx, r13w; unsigned __int16
0x180023b4e  mov     rcx, rdi; this
0x180023b51  mov     [r14+rax], r9d
0x180023b55  call    ?mdGetName@CMetaData@@QEAAPEAGG@Z; CMetaData::mdGetName(ushort)
0x180023b5a  mov     rcx, rax
0x180023b5d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180023b61  inc     rax
0x180023b64  cmp     [rcx+rax*2], r9w
0x180023b69  jnz     short loc_180023B61
0x180023b6b  mov     ecx, [rsi+0D8h]
0x180023b71  add     eax, 2
0x180023b74  add     [rsi+10Ch], eax
0x180023b7a  add     ecx, 7
0x180023b7d  mov     rax, [rsi+0A0h]
0x180023b84  and     ecx, 0FFFFFFF8h
0x180023b87  mov     [rsi+0D8h], ecx
0x180023b8d  mov     [r14+rax], ecx
0x180023b91  add     dword ptr [rsi+0D8h], 10h
0x180023b98  mov     rbx, [rsp+88h+arg_0]
0x180023ba0  mov     eax, r12d
0x180023ba3  add     rsp, 50h
0x180023ba7  pop     r15
0x180023ba9  pop     r14
0x180023bab  pop     r13
0x180023bad  pop     r12
0x180023baf  pop     rdi
0x180023bb0  pop     rsi
0x180023bb1  pop     rbp
0x180023bb2  retn
```
