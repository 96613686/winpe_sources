# FontStyleAttributesRegion::WriteRegion(OpenTypeFace const &,MemoryWriter<FontStyleAttributesRegion> &,StringMemoryRegionBuilder<FontStringsRegion> &)

- ea: `0x18001f934`
- end: `0x18001febc`
- name: `?WriteRegion@FontStyleAttributesRegion@@SAXAEBVOpenTypeFace@@AEAV?$MemoryWriter@VFontStyleAttributesRegion@@@@AEAV?$StringMemoryRegionBuilder@VFontStringsRegion@@@@@Z`
- size: `1416`
- prototype: `__int64 __fastcall(struct OpenTypeFace *, MemoryWriterImpl *, __int64)`
- caller_count: `2`
- callee_count: `32`
- tags: `registry_config, loader_planting`

## callers

- `0x180016fc0`
- `0x1800ce410`

## callees

- `0x180004810`
- `0x180009b68`
- `0x18000bcc4`
- `0x18001c8d4`
- `0x18001dee8`
- `0x18001f934`
- `0x1800201d8`
- `0x180020368`
- `0x1800209f4`
- `0x180020b88`
- `0x180021fe0`
- `0x180024db0`
- `0x180027cb0`
- `0x180027e0c`
- `0x180028c50`
- `0x180029a0c`
- `0x18004d664`
- `0x18004f71c`
- `0x18004f93c`
- `0x1800646a8`
- `0x180064e00`
- `0x1800653dc`
- `0x180065420`
- `0x180088e64`
- `0x180089948`
- `0x18008a7d8`
- `0x18009d96c`
- `0x18009e420`
- `0x18009f1ec`
- `0x1800aa650`
- `0x1800ab0aa`
- `0x1800ab180`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001fe9b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001fe9b`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall FontStyleAttributesRegion::WriteRegion(struct OpenTypeFace *a1, MemoryWriterImpl *a2, __int64 a3)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  unsigned int v12; // ebx
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // rcx
  __int64 v15; // rcx
  unsigned int v16; // eax
  unsigned __int64 v17; // rax
  __int64 v18; // r8
  int v19; // r9d
  const char *v20; // rdx
  _DWORD *v21; // rcx
  unsigned int v22; // eax
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // r8
  int v30[2]; // [rsp+30h] [rbp-D0h] BYREF
  char *v31; // [rsp+38h] [rbp-C8h]
  AxisValueRecordWithOrdering *v32[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v33; // [rsp+50h] [rbp-B0h]
  int v34[4]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v35; // [rsp+70h] [rbp-90h]
  struct DWrite::RefString::Data *v36; // [rsp+80h] [rbp-80h] BYREF
  char *v37; // [rsp+88h] [rbp-78h]
  __int128 v38; // [rsp+90h] [rbp-70h] BYREF
  __int64 v39; // [rsp+A0h] [rbp-60h]
  __int64 v40; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v41; // [rsp+B0h] [rbp-50h]
  struct IDWriteFontFileStream *v42; // [rsp+C0h] [rbp-40h]
  __int64 v43; // [rsp+C8h] [rbp-38h]
  _QWORD v44[3]; // [rsp+D0h] [rbp-30h] BYREF
  struct DWrite::RefString::Data *v45; // [rsp+E8h] [rbp-18h] BYREF
  char *v46; // [rsp+F0h] [rbp-10h]
  struct IDWriteFontFileStream *StreamInternal; // [rsp+100h] [rbp+0h]
  __int64 v48; // [rsp+108h] [rbp+8h]
  int v49[20]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v50[288]; // [rsp+160h] [rbp+60h] BYREF

  OpenTypeNameTable::OpenTypeNameTable((OpenTypeNameTable *)v49, a1);
  v45 = 0;
  v46 = 0;
  StreamInternal = FontFileReference::GetStreamInternal(*(FontFileReference **)a1);
  v48 = 0;
  FontFragmentPtr<unsigned char>::Initialize(&v45, *((unsigned int *)a1 + 97), *((unsigned int *)a1 + 98));
  v40 = 0;
  v41 = 0;
  v42 = FontFileReference::GetStreamInternal(*(FontFileReference **)a1);
  v43 = 0;
  FontFragmentPtr<unsigned char>::Initialize(&v40, *((unsigned int *)a1 + 109), *((unsigned int *)a1 + 110));
  if ( v40 )
  {
    if ( v41 < 0x12 )
      FailAsExceptionPolicy<FileFormatException>::OnOutOfRange(v7, v6);
    if ( _byteswap_ushort(*(_WORD *)v40) != 1 )
    {
      v40 = 0;
      v41 = 0;
    }
  }
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(&v38);
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(v32);
  *(_QWORD *)v30 = v40;
  v31 = (char *)v41;
  ReadAxisValueRecords(v30, v8, v32);
  *(AxisValueRecordWithOrdering **)v30 = v32[0];
  v31 = (char *)v32[0] + 16 * ((v32[1] - v32[0]) >> 4);
  v36 = v45;
  v37 = v46;
  *(_QWORD *)v34 = v40;
  *(_QWORD *)&v34[2] = v41;
  ReadAxes(v34, &v36, v30, &v38);
  FontDifferentiator::FontDifferentiator((FontDifferentiator *)v50, a1);
  AddStandardAxes(v50, a1, &v38);
  *(AxisValueRecordWithOrdering **)v34 = v32[0];
  *(_QWORD *)&v34[2] = (char *)v32[0] + 16 * ((v32[1] - v32[0]) >> 4);
  *(_QWORD *)v30 = v38;
  v31 = (char *)(v38 + 4 * ((__int64)(*((_QWORD *)&v38 + 1) - v38) >> 2));
  ReorderAxes(v30, v34);
  v12 = 0;
  LODWORD(v31) = 0;
  v13 = *((unsigned int *)a2 + 4);
  v14 = v13 + 3;
  if ( v13 + 3 < v13 )
    goto LABEL_30;
  v9 = 0xFFFFFFFFLL;
  if ( v14 > 0xFFFFFFFF )
    goto LABEL_30;
  v15 = (unsigned int)v14 & 0xFFFFFFFC;
  if ( *(_QWORD *)a2 )
  {
    v16 = *((_DWORD *)a2 + 2);
    if ( v16 < (unsigned int)v15 || v16 - (unsigned int)v15 < 0xC )
    {
      FailAssert(0x4Bu, (const char *)0xFFFFFFFFLL);
      goto LABEL_32;
    }
  }
  v17 = (unsigned int)v15;
  v14 = v15 + 12;
  if ( v14 < v17 || v14 > 0xFFFFFFFF )
LABEL_30:
    SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(v14, v9, v10, v11);
  *((_DWORD *)a2 + 4) = v14;
  v30[0] = *(_DWORD *)MemoryWriter<FontStyleAttributesRegion>::WriteArray<FontStyleAttributesRegion::Axis>(
                        (unsigned __int64)a2,
                        (const char *)&v36,
                        v10,
                        0x2E8BA2E8BA2E8BA3LL * ((__int64)(*((_QWORD *)&v38 + 1) - v38) >> 2));
  v30[1] = *MemoryWriter<FontStyleAttributesRegion>::WriteArray<FontStyleAttributesRegion::AxisValueRecord>(
              (unsigned __int64)a2,
              (__int64)&v36,
              v18,
              0xAAAAAAAAAAAAAAABuLL * ((v32[1] - v32[0]) >> 4));
  *(_QWORD *)v34 = v38;
  *(_QWORD *)&v34[2] = v38 + 4 * ((__int64)(*((_QWORD *)&v38 + 1) - v38) >> 2);
  v36 = v32[0];
  v37 = (char *)v32[0] + 16 * ((v32[1] - v32[0]) >> 4);
  WriteAxes((unsigned int)v49, (unsigned int)v30, (unsigned int)&v36, (unsigned int)v34, (__int64)a2, a3);
  *(AxisValueRecordWithOrdering **)v34 = v32[0];
  *(_QWORD *)&v34[2] = (char *)v32[0] + 16 * ((v32[1] - v32[0]) >> 4);
  WriteAxisValueRecords((int)v49, (int)v30, (int)v34, v19, a2, a3);
  if ( !v41 )
    goto LABEL_13;
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(v44);
  if ( v41 < 0x12 )
LABEL_32:
    FailAsExceptionPolicy<FileFormatException>::OnOutOfRange(v25, v24);
  v26 = *(unsigned __int8 *)(v40 + 3);
  LOWORD(v26) = _byteswap_ushort(*(_WORD *)(v40 + 2));
  if ( (_WORD)v26 )
  {
    if ( v41 < 0x14 )
      FailAsExceptionPolicy<FileFormatException>::OnOutOfRange(v26, v40);
    FontNameList::AppendItems(
      (FontNameList *)v44,
      (const struct OpenTypeNameTable *)v49,
      _byteswap_ushort(*(_WORD *)(v40 + 18)));
  }
  if ( v44[0] == v44[1] )
  {
    DWrite::RefString::RefString((DWrite::RefString *)&v36, L"Regular");
    *(_OWORD *)v34 = *(_OWORD *)&off_1800E7020;
    FontNameList::AppendItem(v44, v34, &v36);
    DWrite::RefString::DecrementRef(v36);
  }
  MemoryWriter<FontStyleAttributesRegion>::BeginInnerRegion<NameDictionaryRegion>((unsigned __int64)a2, (__int64)v34);
  NameDictionaryRegion::WriteRegion(v44, v34, a3);
  v12 = MemoryWriterImpl::EndInnerRegionImpl(a2, v35, 4u);
  FontNameList::~FontNameList((FontNameList *)v44);
LABEL_13:
  v21 = *(_DWORD **)a2;
  if ( *(_QWORD *)a2 )
  {
    v22 = *((_DWORD *)a2 + 4);
    if ( v22 < 0xC )
    {
      FailAssert(0x7Au, v20);
      JUMPOUT(0x18001FEBBLL);
    }
    if ( *((_DWORD *)a2 + 2) < v22 )
    {
      FailAssert(0x7Bu, v20);
      __debugbreak();
    }
    if ( *((_DWORD *)a2 + 2) < 0xCu )
    {
      memset_0(v21, 0, *((unsigned int *)a2 + 2));
      *(_DWORD *)_o__errno(v28, v27, v29) = 34;
      invalid_parameter_noinfo();
    }
    else
    {
      *(_QWORD *)v21 = *(_QWORD *)v30;
      v21[2] = v12;
    }
  }
  FontDifferentiator::~FontDifferentiator((FontDifferentiator *)v50);
  if ( v32[0] )
  {
    std::_Destroy_range<std::allocator<AxisValueRecordWithOrdering>>(v32[0]);
    std::_Deallocate<16>(v32[0], 16 * ((signed __int64)(v33 - (unsigned __int64)v32[0]) >> 4));
    *(_OWORD *)v32 = 0;
    v33 = 0;
  }
  if ( (_QWORD)v38 )
  {
    std::_Deallocate<16>((void *)v38, 4 * ((v39 - (__int64)v38) >> 2));
    v38 = 0;
    v39 = 0;
  }
  FontFragmentPtr<PostScript>::~FontFragmentPtr<PostScript>(&v40);
  FontFragmentPtr<PostScript>::~FontFragmentPtr<PostScript>(&v45);
  return FontFragmentPtr<PostScript>::~FontFragmentPtr<PostScript>(v49);
}

```

## disassembly

```asm
0x18001f934  push    rbp
0x18001f936  push    rbx
0x18001f937  push    rsi
0x18001f938  push    rdi
0x18001f939  push    r12
0x18001f93b  push    r14
0x18001f93d  push    r15
0x18001f93f  lea     rbp, [rsp-190h]
0x18001f947  sub     rsp, 290h
0x18001f94e  mov     rax, cs:__security_cookie
0x18001f955  xor     rax, rsp
0x18001f958  mov     [rbp+1C0h+var_40], rax
0x18001f95f  mov     rsi, r8
0x18001f962  mov     rdi, rdx
0x18001f965  mov     rbx, rcx
0x18001f968  mov     rdx, rcx; struct OpenTypeTables *
0x18001f96b  lea     rcx, [rbp+1C0h+var_1B0]; this
0x18001f96f  call    ??0OpenTypeNameTable@@QEAA@AEBVOpenTypeTables@@@Z; OpenTypeNameTable::OpenTypeNameTable(OpenTypeTables const &)
0x18001f974  nop
0x18001f975  xor     r14d, r14d
0x18001f978  mov     [rbp+1C0h+var_1D8], r14
0x18001f97c  mov     [rbp+1C0h+var_1D0], r14
0x18001f980  mov     rcx, [rbx]; this
0x18001f983  call    ?GetStreamInternal@FontFileReference@@QEBAPEAUIDWriteFontFileStream@@XZ; FontFileReference::GetStreamInternal(void)
0x18001f988  mov     [rbp+1C0h+var_1C0], rax
0x18001f98c  mov     [rbp+1C0h+var_1B8], r14
0x18001f990  mov     r8d, [rbx+188h]
0x18001f997  mov     edx, [rbx+184h]
0x18001f99d  lea     rcx, [rbp+1C0h+var_1D8]
0x18001f9a1  call    ?Initialize@?$FontFragmentPtr@E@@QEAAX_K0@Z; FontFragmentPtr<uchar>::Initialize(unsigned __int64,unsigned __int64)
0x18001f9a6  nop
0x18001f9a7  mov     [rbp+1C0h+var_218], r14
0x18001f9ab  mov     [rbp+1C0h+var_210], r14
0x18001f9af  mov     rcx, [rbx]; this
0x18001f9b2  call    ?GetStreamInternal@FontFileReference@@QEBAPEAUIDWriteFontFileStream@@XZ; FontFileReference::GetStreamInternal(void)
0x18001f9b7  mov     [rbp+1C0h+var_200], rax
0x18001f9bb  mov     [rbp+1C0h+var_1F8], r14
0x18001f9bf  mov     r8d, [rbx+1B8h]
0x18001f9c6  mov     edx, [rbx+1B4h]
0x18001f9cc  lea     rcx, [rbp+1C0h+var_218]
0x18001f9d0  call    ?Initialize@?$FontFragmentPtr@E@@QEAAX_K0@Z; FontFragmentPtr<uchar>::Initialize(unsigned __int64,unsigned __int64)
0x18001f9d5  nop
0x18001f9d6  mov     rax, [rbp+1C0h+var_218]
0x18001f9da  test    rax, rax
0x18001f9dd  jz      short loc_18001FA02
0x18001f9df  cmp     [rbp+1C0h+var_210], 12h
0x18001f9e4  jb      loc_18001FE2D
0x18001f9ea  movzx   ecx, byte ptr [rax]
0x18001f9ed  shl     cx, 8
0x18001f9f1  movzx   eax, byte ptr [rax+1]
0x18001f9f5  or      cx, ax
0x18001f9f8  cmp     cx, 1
0x18001f9fc  jnz     loc_18001FE33
0x18001fa02  lea     rcx, [rbp+1C0h+var_230]; void *
0x18001fa06  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x18001fa0b  nop
0x18001fa0c  lea     rcx, [rsp+2C0h+var_280]; void *
0x18001fa11  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x18001fa16  nop
0x18001fa17  mov     rax, [rbp+1C0h+var_218]
0x18001fa1b  mov     qword ptr [rsp+2C0h+var_290], rax
0x18001fa20  mov     rax, [rbp+1C0h+var_210]
0x18001fa24  mov     [rsp+2C0h+var_288], rax
0x18001fa29  lea     r8, [rsp+2C0h+var_280]
0x18001fa2e  lea     rcx, [rsp+2C0h+var_290]
0x18001fa33  call    ?ReadAxisValueRecords@@YAXV?$CheckedPtr@$$CBEV?$FailAsExceptionPolicy@VFileFormatException@@@@_K@@AEBVOpenTypeNameTable@@AEAV?$vector@UAxisValueRecordWithOrdering@@V?$allocator@UAxisValueRecordWithOrdering@@@std@@@std@@@Z; ReadAxisValueRecords(CheckedPtr<uchar const,FailAsExceptionPolicy<FileFormatException>,unsigned __int64>,OpenTypeNameTable const &,std::vector<AxisValueRecordWithOrdering> &)
0x18001fa38  mov     rcx, [rsp+2C0h+var_280]
0x18001fa3d  mov     qword ptr [rsp+2C0h+var_290], rcx
0x18001fa42  mov     rax, [rsp+2C0h+var_280+8]
0x18001fa47  sub     rax, rcx
0x18001fa4a  sar     rax, 4
0x18001fa4e  mov     r15, 0AAAAAAAAAAAAAAABh
0x18001fa58  imul    rax, r15
0x18001fa5c  lea     rax, [rax+rax*2]
0x18001fa60  shl     rax, 4
0x18001fa64  add     rax, rcx
0x18001fa67  mov     [rsp+2C0h+var_288], rax
0x18001fa6c  mov     rax, [rbp+1C0h+var_1D8]
0x18001fa70  mov     [rbp+1C0h+var_240], rax
0x18001fa74  mov     rax, [rbp+1C0h+var_1D0]
0x18001fa78  mov     [rbp+1C0h+var_238], rax
0x18001fa7c  mov     rax, [rbp+1C0h+var_218]
0x18001fa80  mov     qword ptr [rsp+2C0h+var_260], rax
0x18001fa85  mov     rax, [rbp+1C0h+var_210]
0x18001fa89  mov     qword ptr [rsp+2C0h+var_260+8], rax
0x18001fa8e  lea     r9, [rbp+1C0h+var_230]
0x18001fa92  lea     r8, [rsp+2C0h+var_290]
0x18001fa97  lea     rdx, [rbp+1C0h+var_240]
0x18001fa9b  lea     rcx, [rsp+2C0h+var_260]
0x18001faa0  call    ?ReadAxes@@YAXV?$CheckedPtr@$$CBEV?$FailAsExceptionPolicy@VFileFormatException@@@@_K@@0V?$array_ref@UAxisValueRecordWithOrdering@@@@AEAV?$vector@UAxisWithOrdering@@V?$allocator@UAxisWithOrdering@@@std@@@std@@@Z; ReadAxes(CheckedPtr<uchar const,FailAsExceptionPolicy<FileFormatException>,unsigned __int64>,CheckedPtr<uchar const,FailAsExceptionPolicy<FileFormatException>,unsigned __int64>,array_ref<AxisValueRecordWithOrdering>,std::vector<AxisWithOrdering> &)
0x18001faa5  mov     rdx, rbx; struct OpenTypeFace *
0x18001faa8  lea     rcx, [rbp+1C0h+var_160]; this
0x18001faac  call    ??0FontDifferentiator@@QEAA@AEBVOpenTypeFace@@@Z; FontDifferentiator::FontDifferentiator(OpenTypeFace const &)
0x18001fab1  nop
0x18001fab2  lea     r8, [rbp+1C0h+var_230]
0x18001fab6  mov     rdx, rbx
0x18001fab9  lea     rcx, [rbp+1C0h+var_160]
0x18001fabd  call    ?AddStandardAxes@@YAXAEBVFontDifferentiator@@AEBVOpenTypeFace@@AEAV?$vector@UAxisWithOrdering@@V?$allocator@UAxisWithOrdering@@@std@@@std@@@Z; AddStandardAxes(FontDifferentiator const &,OpenTypeFace const &,std::vector<AxisWithOrdering> &)
0x18001fac2  mov     rcx, [rsp+2C0h+var_280]
0x18001fac7  mov     rdx, qword ptr [rbp+1C0h+var_230]
0x18001facb  mov     qword ptr [rsp+2C0h+var_260], rcx
0x18001fad0  mov     rax, [rsp+2C0h+var_280+8]
0x18001fad5  sub     rax, rcx
0x18001fad8  sar     rax, 4
0x18001fadc  imul    rax, r15
0x18001fae0  lea     rax, [rax+rax*2]
0x18001fae4  shl     rax, 4
0x18001fae8  add     rax, rcx
0x18001faeb  mov     qword ptr [rsp+2C0h+var_260+8], rax
0x18001faf0  mov     qword ptr [rsp+2C0h+var_290], rdx
0x18001faf5  mov     rax, qword ptr [rbp+1C0h+var_230+8]
0x18001faf9  sub     rax, rdx
0x18001fafc  sar     rax, 2
0x18001fb00  mov     r12, 2E8BA2E8BA2E8BA3h
0x18001fb0a  imul    rax, r12
0x18001fb0e  imul    rax, 2Ch ; ','
0x18001fb12  add     rax, rdx
0x18001fb15  mov     [rsp+2C0h+var_288], rax
0x18001fb1a  lea     rdx, [rsp+2C0h+var_260]
0x18001fb1f  lea     rcx, [rsp+2C0h+var_290]
0x18001fb24  call    ?ReorderAxes@@YAXV?$array_ref@UAxisWithOrdering@@@@V?$array_ref@UAxisValueRecordWithOrdering@@@@@Z; ReorderAxes(array_ref<AxisWithOrdering>,array_ref<AxisValueRecordWithOrdering>)
0x18001fb29  mov     ebx, r14d
0x18001fb2c  mov     dword ptr [rsp+2C0h+var_288], ebx
0x18001fb30  mov     eax, [rdi+10h]
0x18001fb33  lea     rcx, [rax+3]
0x18001fb37  cmp     rcx, rax
0x18001fb3a  jb      loc_18001FE16
0x18001fb40  mov     edx, 0FFFFFFFFh; char *
0x18001fb45  cmp     rcx, rdx
0x18001fb48  ja      loc_18001FE16
0x18001fb4e  and     ecx, 0FFFFFFFCh
0x18001fb51  cmp     [rdi], r14
0x18001fb54  jz      short loc_18001FB6C
0x18001fb56  mov     eax, [rdi+8]
0x18001fb59  cmp     eax, ecx
0x18001fb5b  jb      loc_18001FE1C
0x18001fb61  sub     eax, ecx
0x18001fb63  cmp     eax, 0Ch
0x18001fb66  jb      loc_18001FE1C
0x18001fb6c  mov     eax, ecx
0x18001fb6e  add     rcx, 0Ch
0x18001fb72  cmp     rcx, rax
0x18001fb75  jb      loc_18001FE16
0x18001fb7b  cmp     rcx, rdx
0x18001fb7e  ja      loc_18001FE16
0x18001fb84  mov     [rdi+10h], ecx
0x18001fb87  mov     r9, qword ptr [rbp+1C0h+var_230+8]
0x18001fb8b  sub     r9, qword ptr [rbp+1C0h+var_230]
0x18001fb8f  sar     r9, 2
0x18001fb93  imul    r9, r12
0x18001fb97  lea     rdx, [rbp+1C0h+var_240]
0x18001fb9b  mov     rcx, rdi
0x18001fb9e  call    ??$WriteArray@UAxis@FontStyleAttributesRegion@@@?$MemoryWriter@VFontStyleAttributesRegion@@@@QEAA?AV?$BasedArrayPtr@VFontStyleAttributesRegion@@UAxis@1@II$03@@PEBUAxis@FontStyleAttributesRegion@@_K@Z; MemoryWriter<FontStyleAttributesRegion>::WriteArray<FontStyleAttributesRegion::Axis>(FontStyleAttributesRegion::Axis const *,unsigned __int64)
0x18001fba3  mov     ecx, [rax]
0x18001fba5  mov     [rsp+2C0h+var_290], ecx
0x18001fba9  mov     r9, [rsp+2C0h+var_280+8]
0x18001fbae  sub     r9, [rsp+2C0h+var_280]
0x18001fbb3  sar     r9, 4
0x18001fbb7  imul    r9, r15
0x18001fbbb  lea     rdx, [rbp+1C0h+var_240]
0x18001fbbf  mov     rcx, rdi
0x18001fbc2  call    ??$WriteArray@UAxisValueRecord@FontStyleAttributesRegion@@@?$MemoryWriter@VFontStyleAttributesRegion@@@@QEAA?AV?$BasedArrayPtr@VFontStyleAttributesRegion@@UAxisValueRecord@1@II$03@@PEBUAxisValueRecord@FontStyleAttributesRegion@@_K@Z; MemoryWriter<FontStyleAttributesRegion>::WriteArray<FontStyleAttributesRegion::AxisValueRecord>(FontStyleAttributesRegion::AxisValueRecord const *,unsigned __int64)
0x18001fbc7  mov     ecx, [rax]
0x18001fbc9  mov     [rsp+2C0h+var_290+4], ecx
0x18001fbcd  mov     rcx, qword ptr [rbp+1C0h+var_230]
0x18001fbd1  mov     rdx, [rsp+2C0h+var_280]
0x18001fbd6  mov     qword ptr [rsp+2C0h+var_260], rcx
0x18001fbdb  mov     rax, qword ptr [rbp+1C0h+var_230+8]
0x18001fbdf  sub     rax, rcx
0x18001fbe2  sar     rax, 2
0x18001fbe6  imul    rax, r12
0x18001fbea  imul    rax, 2Ch ; ','
0x18001fbee  add     rax, rcx
0x18001fbf1  mov     qword ptr [rsp+2C0h+var_260+8], rax
0x18001fbf6  mov     [rbp+1C0h+var_240], rdx
0x18001fbfa  mov     rax, [rsp+2C0h+var_280+8]
0x18001fbff  sub     rax, rdx
0x18001fc02  sar     rax, 4
0x18001fc06  imul    rax, r15
0x18001fc0a  lea     rax, [rax+rax*2]
0x18001fc0e  shl     rax, 4
0x18001fc12  add     rax, rdx
0x18001fc15  mov     [rbp+1C0h+var_238], rax
0x18001fc19  mov     [rsp+2C0h+var_298], rsi
0x18001fc1e  mov     [rsp+2C0h+var_2A0], rdi
0x18001fc23  lea     r9, [rsp+2C0h+var_260]
0x18001fc28  lea     r8, [rbp+1C0h+var_240]
0x18001fc2c  lea     rdx, [rsp+2C0h+var_290]
0x18001fc31  lea     rcx, [rbp+1C0h+var_1B0]
0x18001fc35  call    ?WriteAxes@@YAXAEBVOpenTypeNameTable@@AEBUHeader@FontStyleAttributesRegion@@V?$array_ref@UAxisValueRecordWithOrdering@@@@V?$array_ref@UAxisWithOrdering@@@@AEAV?$MemoryWriter@VFontStyleAttributesRegion@@@@AEAV?$StringMemoryRegionBuilder@VFontStringsRegion@@@@@Z; WriteAxes(OpenTypeNameTable const &,FontStyleAttributesRegion::Header const &,array_ref<AxisValueRecordWithOrdering>,array_ref<AxisWithOrdering>,MemoryWriter<FontStyleAttributesRegion> &,StringMemoryRegionBuilder<FontStringsRegion> &)
0x18001fc3a  mov     rcx, [rsp+2C0h+var_280]
0x18001fc3f  mov     qword ptr [rsp+2C0h+var_260], rcx
0x18001fc44  mov     rax, [rsp+2C0h+var_280+8]
0x18001fc49  sub     rax, rcx
0x18001fc4c  sar     rax, 4
0x18001fc50  imul    rax, r15
0x18001fc54  lea     rax, [rax+rax*2]
0x18001fc58  shl     rax, 4
0x18001fc5c  add     rax, rcx
0x18001fc5f  mov     qword ptr [rsp+2C0h+var_260+8], rax
0x18001fc64  mov     [rsp+2C0h+var_298], rsi; __int64
0x18001fc69  mov     [rsp+2C0h+var_2A0], rdi; MemoryWriterImpl *
0x18001fc6e  lea     r8, [rsp+2C0h+var_260]; int
0x18001fc73  lea     rdx, [rsp+2C0h+var_290]; int
0x18001fc78  lea     rcx, [rbp+1C0h+var_1B0]; int
0x18001fc7c  call    ?WriteAxisValueRecords@@YAXAEBVOpenTypeNameTable@@AEBUHeader@FontStyleAttributesRegion@@V?$array_ref@UAxisValueRecordWithOrdering@@@@V?$array_ref@UAxisWithOrdering@@@@AEAV?$MemoryWriter@VFontStyleAttributesRegion@@@@AEAV?$StringMemoryRegionBuilder@VFontStringsRegion@@@@@Z; WriteAxisValueRecords(OpenTypeNameTable const &,FontStyleAttributesRegion::Header const &,array_ref<AxisValueRecordWithOrdering>,array_ref<AxisWithOrdering>,MemoryWriter<FontStyleAttributesRegion> &,StringMemoryRegionBuilder<FontStringsRegion> &)
0x18001fc81  cmp     [rbp+1C0h+var_210], r14
0x18001fc85  jnz     loc_18001FD78
0x18001fc8b  mov     rcx, [rdi]; void *
0x18001fc8e  test    rcx, rcx
0x18001fc91  jz      short loc_18001FCBF
0x18001fc93  mov     eax, [rdi+10h]
0x18001fc96  cmp     eax, 0Ch
0x18001fc99  jb      loc_18001FEB1
0x18001fc9f  cmp     [rdi+8], eax
0x18001fca2  jb      loc_18001FE85
0x18001fca8  cmp     dword ptr [rdi+8], 0Ch
0x18001fcac  jb      loc_18001FE90
0x18001fcb2  movsd   xmm0, qword ptr [rsp+2C0h+var_290]
0x18001fcb8  movsd   qword ptr [rcx], xmm0
0x18001fcbc  mov     [rcx+8], ebx
0x18001fcbf  lea     rcx, [rbp+1C0h+var_160]; this
0x18001fcc3  call    ??1FontDifferentiator@@QEAA@XZ; FontDifferentiator::~FontDifferentiator(void)
0x18001fcc8  nop
0x18001fcc9  mov     rcx, [rsp+2C0h+var_280]; this
0x18001fcce  test    rcx, rcx
0x18001fcd1  jz      short loc_18001FD0D
0x18001fcd3  mov     rdx, [rsp+2C0h+var_280+8]
0x18001fcd8  call    ??$_Destroy_range@V?$allocator@UAxisValueRecordWithOrdering@@@std@@@std@@YAXPEAUAxisValueRecordWithOrdering@@QEAU1@AEAV?$allocator@UAxisValueRecordWithOrdering@@@0@@Z; std::_Destroy_range<std::allocator<AxisValueRecordWithOrdering>>(AxisValueRecordWithOrdering *,AxisValueRecordWithOrdering * const,std::allocator<AxisValueRecordWithOrdering> &)
0x18001fcdd  mov     rcx, [rsp+2C0h+var_280]
0x18001fce2  mov     rax, [rsp+2C0h+var_270]
0x18001fce7  sub     rax, rcx
0x18001fcea  sar     rax, 4
0x18001fcee  imul    rax, r15
0x18001fcf2  lea     rdx, [rax+rax*2]
0x18001fcf6  shl     rdx, 4
0x18001fcfa  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001fcff  xorps   xmm0, xmm0
0x18001fd02  movdqu  xmmword ptr [rsp+2C0h+var_280], xmm0
0x18001fd08  mov     [rsp+2C0h+var_270], r14
0x18001fd0d  mov     rcx, qword ptr [rbp+1C0h+var_230]
0x18001fd11  test    rcx, rcx
0x18001fd14  jz      short loc_18001FD3A
0x18001fd16  mov     rax, [rbp+1C0h+var_220]
0x18001fd1a  sub     rax, rcx
0x18001fd1d  sar     rax, 2
0x18001fd21  imul    rax, r12
0x18001fd25  imul    rdx, rax, 2Ch ; ','
0x18001fd29  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001fd2e  xorps   xmm0, xmm0
0x18001fd31  movdqu  [rbp+1C0h+var_230], xmm0
0x18001fd36  mov     [rbp+1C0h+var_220], r14
0x18001fd3a  lea     rcx, [rbp+1C0h+var_218]
0x18001fd3e  call    ??1?$FontFragmentPtr@UPostScript@@@@QEAA@XZ; FontFragmentPtr<PostScript>::~FontFragmentPtr<PostScript>(void)
0x18001fd43  nop
0x18001fd44  lea     rcx, [rbp+1C0h+var_1D8]
0x18001fd48  call    ??1?$FontFragmentPtr@UPostScript@@@@QEAA@XZ; FontFragmentPtr<PostScript>::~FontFragmentPtr<PostScript>(void)
0x18001fd4d  nop
0x18001fd4e  lea     rcx, [rbp+1C0h+var_1B0]
0x18001fd52  call    ??1?$FontFragmentPtr@UPostScript@@@@QEAA@XZ; FontFragmentPtr<PostScript>::~FontFragmentPtr<PostScript>(void)
0x18001fd57  mov     rcx, [rbp+1C0h+var_40]
0x18001fd5e  xor     rcx, rsp; StackCookie
0x18001fd61  call    __security_check_cookie
0x18001fd66  add     rsp, 290h
0x18001fd6d  pop     r15
0x18001fd6f  pop     r14
0x18001fd71  pop     r12
0x18001fd73  pop     rdi
0x18001fd74  pop     rsi
0x18001fd75  pop     rbx
0x18001fd76  pop     rbp
0x18001fd77  retn
0x18001fd78  lea     rcx, [rbp+1C0h+var_1F0]; void *
0x18001fd7c  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x18001fd81  nop
0x18001fd82  cmp     [rbp+1C0h+var_210], 12h
0x18001fd87  jb      loc_18001FE27
0x18001fd8d  mov     rdx, [rbp+1C0h+var_218]
0x18001fd91  movzx   ecx, byte ptr [rdx+3]
0x18001fd95  movzx   eax, byte ptr [rdx+2]
0x18001fd99  shl     ax, 8
0x18001fd9d  or      cx, ax
0x18001fda0  jbe     short loc_18001FDCC
0x18001fda2  cmp     [rbp+1C0h+var_210], 14h
0x18001fda7  jb      loc_18001FE40
0x18001fdad  movzx   r8d, byte ptr [rdx+12h]
0x18001fdb2  shl     r8w, 8
0x18001fdb7  movzx   eax, byte ptr [rdx+13h]
0x18001fdbb  or      r8w, ax; unsigned __int16
0x18001fdbf  lea     rdx, [rbp+1C0h+var_1B0]; struct OpenTypeNameTable *
0x18001fdc3  lea     rcx, [rbp+1C0h+var_1F0]; this
0x18001fdc7  call    ?AppendItems@FontNameList@@QEAAXAEBVOpenTypeNameTable@@G@Z; FontNameList::AppendItems(OpenTypeNameTable const &,ushort)
0x18001fdcc  mov     rax, [rbp+1C0h+var_1E8]
0x18001fdd0  cmp     [rbp+1C0h+var_1F0], rax
0x18001fdd4  jz      short loc_18001FE46
0x18001fdd6  lea     rdx, [rsp+2C0h+var_260]
0x18001fddb  mov     rcx, rdi
0x18001fdde  call    ??$BeginInnerRegion@VNameDictionaryRegion@@@?$MemoryWriter@VFontStyleAttributesRegion@@@@QEAA?AV?$MemoryWriter@VNameDictionaryRegion@@@@XZ; MemoryWriter<FontStyleAttributesRegion>::BeginInnerRegion<NameDictionaryRegion>(void)
0x18001fde3  mov     r8, rsi
0x18001fde6  lea     rdx, [rsp+2C0h+var_260]
  ... truncated ...
```
