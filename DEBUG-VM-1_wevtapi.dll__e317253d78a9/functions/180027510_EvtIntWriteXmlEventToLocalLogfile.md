# EvtIntWriteXmlEventToLocalLogfile

- ea: `0x180027510`
- end: `0x180027782`
- name: `EvtIntWriteXmlEventToLocalLogfile`
- size: `626`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config`

## callees

- `0x180003a68`
- `0x180003dc0`
- `0x180006870`
- `0x180007aa0`
- `0x18000a2d0`
- `0x18000a4b4`
- `0x18000a558`
- `0x18000b95c`
- `0x1800108d0`
- `0x1800196a0`
- `0x180023548`
- `0x180027510`
- `0x18002e234`
- `0x18002eb48`
- `0x180034524`
- `0x180038fb4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027766`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027766`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall EvtIntWriteXmlEventToLocalLogfile(__int64 a1, __int64 a2, int a3)
{
  void **v4; // rbx
  DWORD ReferencedObject; // edi
  char v6; // r8
  __int64 v7; // rax
  unsigned int v8; // r8d
  __int128 v10; // [rsp+40h] [rbp-1E8h] BYREF
  __int128 pExceptionObject; // [rsp+50h] [rbp-1D8h] BYREF
  __int64 v12; // [rsp+60h] [rbp-1C8h]
  int v13; // [rsp+68h] [rbp-1C0h]
  int v14; // [rsp+6Ch] [rbp-1BCh]
  int v15; // [rsp+70h] [rbp-1B8h]
  _BYTE v16[8]; // [rsp+78h] [rbp-1B0h] BYREF
  __int64 v17; // [rsp+80h] [rbp-1A8h]
  unsigned int v18; // [rsp+88h] [rbp-1A0h]
  EvtException *v19; // [rsp+90h] [rbp-198h] BYREF
  _QWORD v20[3]; // [rsp+98h] [rbp-190h] BYREF
  __int128 v21; // [rsp+B0h] [rbp-178h]
  _BYTE v22[32]; // [rsp+C0h] [rbp-168h] BYREF
  _BYTE v23[48]; // [rsp+E0h] [rbp-148h] BYREF
  _BYTE v24[64]; // [rsp+110h] [rbp-118h] BYREF
  _BYTE v25[216]; // [rsp+150h] [rbp-D8h] BYREF
  void **v26; // [rsp+230h] [rbp+8h] BYREF
  void **v27; // [rsp+248h] [rbp+20h]

  try
  {
    if ( !a1 || !a2 || a3 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids, 87);
      }
      pExceptionObject = 0;
      v12 = 0;
      v13 = 87;
      v14 = -1;
      v15 = 329;
      throw (EvtException *)&pExceptionObject;
    }
    v4 = 0;
    v27 = 0;
    v26 = 0;
    ReferencedObject = ObjectTable::GetReferencedObject(a1, a1, &v26);
    if ( ReferencedObject )
      goto LABEL_11;
    v4 = v26;
    if ( *((_BYTE *)v26 + 28) == 17 )
    {
      v27 = v26;
      if ( v26 )
      {
        v26 = 0;
        ReferencedObject = 0;
LABEL_11:
        wmi::AutoRef<Object>::Release(&v26);
        if ( !ReferencedObject )
        {
          Buffer::Buffer((Buffer *)v22, 0, 0, 1);
          WriteBuffer::WriteBuffer((WriteBuffer *)v16, (struct BufferStream *)v22);
          BinXmlWriter::BinXmlWriter((BinXmlWriter *)v23, 0, (struct WriteBuffer *)v16, 0, 0, 0, 0);
          v7 = -1;
          do
            ++v7;
          while ( *(_WORD *)(a2 + 2 * v7) );
          *(_QWORD *)&v10 = a2;
          *((_QWORD *)&v10 + 1) = v7;
          BinXmlWriter::Parse((BinXmlWriter *)v23, &v10, v6);
          v20[0] = 0;
          v21 = 0;
          v20[1] = v17;
          v20[2] = v18;
          v26 = &ZeroPublishedEventRecord::`vftable';
          BinXmlReader::BinXmlReader(
            (BinXmlReader *)v25,
            (struct BinXmlReaderData *)v20,
            v8,
            (struct AbstractPublishedEventRecord *)&v26,
            0,
            0);
          BinXmlReader::Reset((BinXmlReader *)v25);
          ReferencedObject = File::WriteRecord((File *)(v4 + 4), (struct BinXmlReader *)v25);
          BinXmlReader::~BinXmlReader((BinXmlReader *)v25);
          utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(v24);
          Buffer::~Buffer((Buffer *)v22);
        }
        if ( v4 )
          wmi::RefBase::Release((wmi::RefBase *)v4);
        goto LABEL_26;
      }
    }
    else
    {
      v4 = 0;
      v27 = 0;
    }
    ReferencedObject = 6;
    goto LABEL_11;
  }
  catch ( EvtException *v19 )
  {
    LODWORD(v26) = *((_DWORD *)v19 + 6);
    ReferencedObject = (unsigned int)v26;
  }
LABEL_26:
  SetLastError(ReferencedObject);
  return ReferencedObject;
}

```

## disassembly

```asm
0x180027510  mov     rax, rsp
0x180027513  mov     [rax+10h], rbx
0x180027517  push    rsi
0x180027518  push    rdi
0x180027519  push    r14
0x18002751b  sub     rsp, 210h
0x180027522  mov     rsi, rdx
0x180027525  xor     r14d, r14d
0x180027528  test    rcx, rcx
0x18002752b  jz      loc_1800276ED
0x180027531  test    rdx, rdx
0x180027534  jz      loc_1800276ED
0x18002753a  test    r8d, r8d
0x18002753d  jnz     loc_1800276ED
0x180027543  mov     ebx, r14d
0x180027546  mov     [rax+20h], rbx
0x18002754a  mov     [rax+8], r14
0x18002754e  lea     r8, [rax+8]
0x180027552  mov     rdx, rcx
0x180027555  call    ?GetReferencedObject@ObjectTable@@QEAAKPEAXAEAV?$AutoRef@VObject@@@wmi@@@Z; ObjectTable::GetReferencedObject(void *,wmi::AutoRef<Object> &)
0x18002755a  mov     edi, eax
0x18002755c  test    eax, eax
0x18002755e  jnz     short loc_180027598
0x180027560  mov     rbx, [rsp+228h+arg_0]
0x180027568  cmp     byte ptr [rbx+1Ch], 11h
0x18002756c  jnz     short loc_180027588
0x18002756e  mov     [rsp+228h+arg_18], rbx
0x180027576  test    rbx, rbx
0x180027579  jz      short loc_180027593
0x18002757b  mov     [rsp+228h+arg_0], r14
0x180027583  mov     edi, r14d
0x180027586  jmp     short loc_180027598
0x180027588  mov     rbx, r14
0x18002758b  mov     [rsp+228h+arg_18], rbx
0x180027593  mov     edi, 6
0x180027598  lea     rcx, [rsp+228h+arg_0]; void *
0x1800275a0  call    ?Release@?$AutoRef@VObject@@@wmi@@QEAAXXZ; wmi::AutoRef<Object>::Release(void)
0x1800275a5  test    edi, edi
0x1800275a7  jnz     loc_1800276DD
0x1800275ad  mov     r9b, 1; bool
0x1800275b0  xor     r8d, r8d; unsigned int
0x1800275b3  xor     edx, edx; unsigned __int8 *
0x1800275b5  lea     rcx, [rsp+228h+var_168]; this
0x1800275bd  call    ??0Buffer@@QEAA@PEBEK_N@Z; Buffer::Buffer(uchar const *,ulong,bool)
0x1800275c2  nop
0x1800275c3  lea     rdx, [rsp+228h+var_168]; struct BufferStream *
0x1800275cb  lea     rcx, [rsp+228h+var_1B0]; this
0x1800275d0  call    ??0WriteBuffer@@QEAA@AEAVBufferStream@@@Z; WriteBuffer::WriteBuffer(BufferStream &)
0x1800275d5  mov     [rsp+228h+var_1F8], r14d; unsigned int
0x1800275da  mov     [rsp+228h+var_200], r14; unsigned int *
0x1800275df  mov     [rsp+228h+var_208], r14; struct BinXmlTemplateTable *
0x1800275e4  xor     r9d, r9d; struct BinXmlStringTable *
0x1800275e7  lea     r8, [rsp+228h+var_1B0]; struct WriteBuffer *
0x1800275ec  xor     edx, edx; bool
0x1800275ee  lea     rcx, [rsp+228h+var_148]; this
0x1800275f6  call    ??0BinXmlWriter@@QEAA@_NAEAVWriteBuffer@@PEAVBinXmlStringTable@@PEAVBinXmlTemplateTable@@PEBKK@Z; BinXmlWriter::BinXmlWriter(bool,WriteBuffer &,BinXmlStringTable *,BinXmlTemplateTable *,ulong const *,ulong)
0x1800275fb  nop
0x1800275fc  or      rax, 0FFFFFFFFFFFFFFFFh
0x180027600  inc     rax
0x180027603  cmp     [rsi+rax*2], r14w
0x180027608  jnz     short loc_180027600
0x18002760a  mov     [rsp+228h+var_1E8], rsi
0x18002760f  mov     [rsp+228h+var_1E0], rax
0x180027614  xor     r9d, r9d
0x180027617  lea     rdx, [rsp+228h+var_1E8]
0x18002761c  lea     rcx, [rsp+228h+var_148]; this
0x180027624  call    ?Parse@BinXmlWriter@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@_N1@Z; BinXmlWriter::Parse(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,bool,bool)
0x180027629  mov     [rsp+228h+var_190], r14
0x180027631  xorps   xmm0, xmm0
0x180027634  movdqu  [rsp+228h+var_178], xmm0
0x18002763d  mov     rax, [rsp+228h+var_1A8]
0x180027645  mov     [rsp+228h+var_188], rax
0x18002764d  mov     eax, [rsp+228h+var_1A0]
0x180027654  mov     [rsp+228h+var_180], rax
0x18002765c  lea     rax, ??_7ZeroPublishedEventRecord@@6B@; const ZeroPublishedEventRecord::`vftable'
0x180027663  mov     [rsp+228h+arg_0], rax
0x18002766b  mov     [rsp+228h+var_200], r14; struct BinXmlTemplateTable *
0x180027670  mov     [rsp+228h+var_208], r14; struct BinXmlStringTable *
0x180027675  lea     r9, [rsp+228h+arg_0]; struct AbstractPublishedEventRecord *
0x18002767d  lea     rdx, [rsp+228h+var_190]; struct BinXmlReaderData *
0x180027685  lea     rcx, [rsp+228h+var_D8]; this
0x18002768d  call    ??0BinXmlReader@@QEAA@PEAUBinXmlReaderData@@KPEAVAbstractPublishedEventRecord@@PEAVBinXmlStringTable@@PEAVBinXmlTemplateTable@@@Z; BinXmlReader::BinXmlReader(BinXmlReaderData *,ulong,AbstractPublishedEventRecord *,BinXmlStringTable *,BinXmlTemplateTable *)
0x180027692  nop
0x180027693  lea     rcx, [rsp+228h+var_D8]; this
0x18002769b  call    ?Reset@BinXmlReader@@QEAAXXZ; BinXmlReader::Reset(void)
0x1800276a0  lea     rcx, [rbx+20h]; this
0x1800276a4  lea     rdx, [rsp+228h+var_D8]; struct BinXmlReader *
0x1800276ac  call    ?WriteRecord@File@@QEAAKAEAVBinXmlReader@@@Z; File::WriteRecord(BinXmlReader &)
0x1800276b1  mov     edi, eax
0x1800276b3  lea     rcx, [rsp+228h+var_D8]; this
0x1800276bb  call    ??1BinXmlReader@@QEAA@XZ; BinXmlReader::~BinXmlReader(void)
0x1800276c0  nop
0x1800276c1  lea     rcx, [rsp+228h+var_118]
0x1800276c9  call    ?_Uninit@?$vector@Utag_EvtRpcVariant@@V?$allocator@Utag_EvtRpcVariant@@@utl@@@utl@@AEAAXXZ; utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(void)
0x1800276ce  nop
0x1800276cf  lea     rcx, [rsp+228h+var_168]; this
0x1800276d7  call    ??1Buffer@@UEAA@XZ; Buffer::~Buffer(void)
0x1800276dc  nop
0x1800276dd  test    rbx, rbx
0x1800276e0  jz      short loc_1800276EB
0x1800276e2  mov     rcx, rbx; this
0x1800276e5  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x1800276ea  nop
0x1800276eb  jmp     short loc_180027764
0x1800276ed  lea     rax, WPP_GLOBAL_Control
0x1800276f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800276fb  cmp     rcx, rax
0x1800276fe  jz      short loc_180027725
0x180027700  test    byte ptr [rcx+1Ch], 1
0x180027704  jz      short loc_180027725
0x180027706  cmp     byte ptr [rcx+19h], 2
0x18002770a  jb      short loc_180027725
0x18002770c  mov     edx, 0Eh
0x180027711  lea     r9d, [rdx+49h]
0x180027715  lea     r8, WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids
0x18002771c  mov     rcx, [rcx+10h]
0x180027720  call    WPP_SF_D
0x180027725  xorps   xmm0, xmm0
0x180027728  movdqu  [rsp+228h+pExceptionObject], xmm0
0x18002772e  mov     [rsp+228h+var_1C8], r14
0x180027733  mov     [rsp+228h+var_1C0], 57h ; 'W'
0x18002773b  mov     [rsp+228h+var_1BC], 0FFFFFFFFh
0x180027743  mov     [rsp+228h+var_1B8], 149h
0x18002774b  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180027752  lea     rcx, [rsp+228h+pExceptionObject]; pExceptionObject
0x180027757  call    _CxxThrowException_0
0x18002775d  mov     edi, dword ptr [rsp+228h+arg_0]
0x180027764  mov     ecx, edi; dwErrCode
0x180027766  call    cs:__imp_SetLastError
0x18002776c  mov     eax, edi
0x18002776e  mov     rbx, [rsp+228h+arg_8]
0x180027776  add     rsp, 210h
0x18002777d  pop     r14
0x18002777f  pop     rdi
0x180027780  pop     rsi
0x180027781  retn
```
