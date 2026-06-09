# Ofc::TComplexTypeHelper<ODF::AreaRectangle>::FillWriters(ODF::AreaRectangle const &,Ofc::CNamespaceDeclarationTracker &,Ofc::CWriterEmit &,Ofc::IWriterParams &)

- ea: `0x180049918`
- end: `0x180049b49`
- name: `?FillWriters@?$TComplexTypeHelper@VAreaRectangle@ODF@@@Ofc@@SAXAEBVAreaRectangle@ODF@@AEAVCNamespaceDeclarationTracker@2@AEAVCWriterEmit@2@AEAVIWriterParams@2@@Z`
- size: `561`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180053b40`

## callees

- `0x18001db8c`
- `0x18001dd94`
- `0x180025f94`
- `0x180026300`
- `0x18002e1f0`
- `0x18002e70c`
- `0x18002e844`
- `0x180049918`
- `0x180054df0`
- `0x180054fc4`
- `0x1801a80e0`

## import_xrefs

- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18004994f`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180049971`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800499a4`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800499c3`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800499dd`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180049a20`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180049a45`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180049a6e`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180049a97`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180049ac0`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18004994f`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180049971`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800499a4`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800499c3`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800499dd`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180049a20`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180049a45`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180049a6e`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180049a97`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180049ac0`
- `mso40uiWin32Client!__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ` at `0x180049b29`
- `mso40uiWin32Client!__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ` at `0x180049b29`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Ofc::TComplexTypeHelper<ODF::AreaRectangle>::FillWriters(
        _QWORD *a1,
        Ofc::CNamespaceDeclarationTracker *a2,
        Ofc::CWriterEmit *a3,
        __int64 a4)
{
  int v8; // edx
  int v9; // ecx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rcx
  const wchar_t *v18; // [rsp+50h] [rbp+8h] BYREF

  if ( a1[3] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 323);
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(L"href", 323, a1 + 3, a4);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 323);
  LODWORD(v18) = 0;
  Ofc::TAttrWriterHelper<enum ODF::XlinkType,Ofc::TSelfAdapter<enum ODF::XlinkType>,1>::Write(
    v9,
    v8,
    (_DWORD)a1 + 32,
    a4,
    (__int64)&v18);
  if ( a1[5] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 300);
  Ofc::TAttrWriterHelper<Ofc::TVariant<ODF::TargetFrameNameIDsImpl>,Ofc::TOptionalAdapter<Ofc::TVariant<ODF::TargetFrameNameIDsImpl>>,0>::Write(
    v11,
    v10,
    a1 + 5,
    a4);
  if ( a1[6] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 323);
  Ofc::TAttrWriterHelper<enum ODF::XlinkShow1Show,Ofc::TOptionalAdapter<enum ODF::XlinkShow1Show>,0>::Write(
    v13,
    v12,
    a1 + 6,
    a4);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 300);
  v18 = &dword_1801DBD74;
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(
    (unsigned int)L"name",
    300,
    (_DWORD)a1 + 56,
    a4,
    (__int64)&v18);
  if ( a1[8] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 307);
  Ofc::TAttrWriterHelper<enum ODF::Nohref,Ofc::TOptionalAdapter<enum ODF::Nohref>,0>::Write(v15, v14, a1 + 8, a4);
  if ( a1[9] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 318);
  Ofc::TAttrWriterHelper<ODF::PositiveLength,Ofc::TOptionalAdapter<ODF::PositiveLength>,0>::Write(L"x", 318, a1 + 9, a4);
  if ( a1[10] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 318);
  Ofc::TAttrWriterHelper<ODF::PositiveLength,Ofc::TOptionalAdapter<ODF::PositiveLength>,0>::Write(
    L"y",
    318,
    a1 + 10,
    a4);
  if ( a1[11] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 318);
  Ofc::TAttrWriterHelper<ODF::PositiveLength,Ofc::TOptionalAdapter<ODF::PositiveLength>,0>::Write(
    L"height",
    318,
    a1 + 11,
    a4);
  if ( a1[12] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 318);
  Ofc::TAttrWriterHelper<ODF::PositiveLength,Ofc::TOptionalAdapter<ODF::PositiveLength>,0>::Write(
    L"width",
    318,
    a1 + 12,
    a4);
  (**(void (__fastcall ***)(Ofc::CWriterEmit *, _QWORD))a3)(a3, *(_QWORD *)(a4 + 16));
  Ofc::TSimpleElemWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(L"title", 318, a1, a4);
  Ofc::TSimpleElemWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(L"desc", 318, a1 + 1, a4);
  Ofc::TCompElemWriterHelper<ODF::EventListeners,Ofc::TOptionalAdapter<ODF::EventListeners>,0>::Write(
    v17,
    v16,
    a1 + 2,
    a4);
  Ofc::CWriterEmit::EmitEndElement(a3);
}

```

## disassembly

```asm
0x180049918  mov     [rsp+arg_8], rbx
0x18004991d  mov     [rsp+arg_10], rbp
0x180049922  mov     [rsp+arg_18], rsi
0x180049927  push    rdi
0x180049928  push    r14
0x18004992a  push    r15
0x18004992c  sub     rsp, 30h
0x180049930  mov     rsi, r9
0x180049933  mov     r14, r8
0x180049936  mov     rbx, rdx
0x180049939  mov     rdi, rcx
0x18004993c  mov     r15d, 143h
0x180049942  cmp     qword ptr [rcx+18h], 0
0x180049947  jz      short loc_180049955
0x180049949  mov     edx, r15d
0x18004994c  mov     rcx, rbx
0x18004994f  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x180049955  mov     r9, rsi
0x180049958  lea     r8, [rdi+18h]
0x18004995c  mov     edx, r15d
0x18004995f  lea     rcx, aHref; "href"
0x180049966  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TOptionalAdapter@VCVarStr@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VCVarStr@Ofc@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::CVarStr> const &,Ofc::IWriterParams &)
0x18004996b  mov     edx, r15d
0x18004996e  mov     rcx, rbx
0x180049971  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x180049977  mov     dword ptr [rsp+48h+arg_0], 0
0x18004997f  lea     r8, [rdi+20h]
0x180049983  lea     rax, [rsp+48h+arg_0]
0x180049988  mov     [rsp+48h+var_28], rax
0x18004998d  mov     r9, rsi
0x180049990  call    ?Write@?$TAttrWriterHelper@W4XlinkType@ODF@@V?$TSelfAdapter@W4XlinkType@ODF@@@Ofc@@$00@Ofc@@SAXPEB_WHAEBW4XlinkType@ODF@@AEAVIWriterParams@2@PEBW434@@Z; Ofc::TAttrWriterHelper<ODF::XlinkType,Ofc::TSelfAdapter<ODF::XlinkType>,1>::Write(wchar_t const *,int,ODF::XlinkType const &,Ofc::IWriterParams &,ODF::XlinkType const *)
0x180049995  cmp     qword ptr [rdi+28h], 0
0x18004999a  jz      short loc_1800499AA
0x18004999c  mov     edx, 12Ch
0x1800499a1  mov     rcx, rbx
0x1800499a4  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800499aa  mov     r9, rsi
0x1800499ad  lea     r8, [rdi+28h]
0x1800499b1  call    ?Write@?$TAttrWriterHelper@V?$TVariant@VTargetFrameNameIDsImpl@ODF@@@Ofc@@V?$TOptionalAdapter@V?$TVariant@VTargetFrameNameIDsImpl@ODF@@@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@V?$TVariant@VTargetFrameNameIDsImpl@ODF@@@Ofc@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::TVariant<ODF::TargetFrameNameIDsImpl>,Ofc::TOptionalAdapter<Ofc::TVariant<ODF::TargetFrameNameIDsImpl>>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::TVariant<ODF::TargetFrameNameIDsImpl>> const &,Ofc::IWriterParams &)
0x1800499b6  cmp     qword ptr [rdi+30h], 0
0x1800499bb  jz      short loc_1800499C9
0x1800499bd  mov     edx, r15d
0x1800499c0  mov     rcx, rbx
0x1800499c3  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800499c9  mov     r9, rsi
0x1800499cc  lea     r8, [rdi+30h]
0x1800499d0  call    ?Write@?$TAttrWriterHelper@W4XlinkShow1Show@ODF@@V?$TOptionalAdapter@W4XlinkShow1Show@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@W4XlinkShow1Show@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::XlinkShow1Show,Ofc::TOptionalAdapter<ODF::XlinkShow1Show>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::XlinkShow1Show> const &,Ofc::IWriterParams &)
0x1800499d5  mov     edx, 12Ch
0x1800499da  mov     rcx, rbx
0x1800499dd  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800499e3  lea     rax, dword_1801DBD74
0x1800499ea  mov     [rsp+48h+arg_0], rax
0x1800499ef  lea     r8, [rdi+38h]
0x1800499f3  lea     rax, [rsp+48h+arg_0]
0x1800499f8  mov     [rsp+48h+var_28], rax
0x1800499fd  mov     r9, rsi
0x180049a00  mov     edx, 12Ch
0x180049a05  lea     rcx, aName; "name"
0x180049a0c  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TSelfAdapter@VCVarStr@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBVCVarStr@2@AEAVIWriterParams@2@PEBV32@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(wchar_t const *,int,Ofc::CVarStr const &,Ofc::IWriterParams &,Ofc::CVarStr const *)
0x180049a11  cmp     qword ptr [rdi+40h], 0
0x180049a16  jz      short loc_180049A26
0x180049a18  mov     edx, 133h
0x180049a1d  mov     rcx, rbx
0x180049a20  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x180049a26  mov     r9, rsi
0x180049a29  lea     r8, [rdi+40h]
0x180049a2d  call    ?Write@?$TAttrWriterHelper@W4Nohref@ODF@@V?$TOptionalAdapter@W4Nohref@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@W4Nohref@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::Nohref,Ofc::TOptionalAdapter<ODF::Nohref>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::Nohref> const &,Ofc::IWriterParams &)
0x180049a32  mov     r15d, 13Eh
0x180049a38  cmp     qword ptr [rdi+48h], 0
0x180049a3d  jz      short loc_180049A4B
0x180049a3f  mov     edx, r15d
0x180049a42  mov     rcx, rbx
0x180049a45  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x180049a4b  mov     r9, rsi
0x180049a4e  lea     r8, [rdi+48h]
0x180049a52  mov     edx, r15d
0x180049a55  lea     rcx, asc_1801DF854; "x"
0x180049a5c  call    ?Write@?$TAttrWriterHelper@VPositiveLength@ODF@@V?$TOptionalAdapter@VPositiveLength@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VPositiveLength@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::PositiveLength,Ofc::TOptionalAdapter<ODF::PositiveLength>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::PositiveLength> const &,Ofc::IWriterParams &)
0x180049a61  cmp     qword ptr [rdi+50h], 0
0x180049a66  jz      short loc_180049A74
0x180049a68  mov     edx, r15d
0x180049a6b  mov     rcx, rbx
0x180049a6e  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x180049a74  mov     r9, rsi
0x180049a77  lea     r8, [rdi+50h]
0x180049a7b  mov     edx, r15d
0x180049a7e  lea     rcx, aY; "y"
0x180049a85  call    ?Write@?$TAttrWriterHelper@VPositiveLength@ODF@@V?$TOptionalAdapter@VPositiveLength@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VPositiveLength@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::PositiveLength,Ofc::TOptionalAdapter<ODF::PositiveLength>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::PositiveLength> const &,Ofc::IWriterParams &)
0x180049a8a  cmp     qword ptr [rdi+58h], 0
0x180049a8f  jz      short loc_180049A9D
0x180049a91  mov     edx, r15d
0x180049a94  mov     rcx, rbx
0x180049a97  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x180049a9d  mov     r9, rsi
0x180049aa0  lea     r8, [rdi+58h]
0x180049aa4  mov     edx, r15d
0x180049aa7  lea     rcx, aHeight; "height"
0x180049aae  call    ?Write@?$TAttrWriterHelper@VPositiveLength@ODF@@V?$TOptionalAdapter@VPositiveLength@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VPositiveLength@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::PositiveLength,Ofc::TOptionalAdapter<ODF::PositiveLength>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::PositiveLength> const &,Ofc::IWriterParams &)
0x180049ab3  cmp     qword ptr [rdi+60h], 0
0x180049ab8  jz      short loc_180049AC6
0x180049aba  mov     edx, r15d
0x180049abd  mov     rcx, rbx
0x180049ac0  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x180049ac6  mov     r9, rsi
0x180049ac9  lea     r8, [rdi+60h]
0x180049acd  mov     edx, r15d
0x180049ad0  lea     rcx, aWidth; "width"
0x180049ad7  call    ?Write@?$TAttrWriterHelper@VPositiveLength@ODF@@V?$TOptionalAdapter@VPositiveLength@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VPositiveLength@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::PositiveLength,Ofc::TOptionalAdapter<ODF::PositiveLength>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::PositiveLength> const &,Ofc::IWriterParams &)
0x180049adc  mov     rax, [r14]
0x180049adf  mov     rdx, [rsi+10h]
0x180049ae3  mov     rcx, r14
0x180049ae6  mov     rax, [rax]
0x180049ae9  call    cs:__guard_dispatch_icall_fptr
0x180049aef  mov     r9, rsi
0x180049af2  mov     r8, rdi
0x180049af5  mov     edx, r15d
0x180049af8  lea     rcx, aTitle; "title"
0x180049aff  call    ?Write@?$TSimpleElemWriterHelper@VCVarStr@Ofc@@V?$TOptionalAdapter@VCVarStr@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VCVarStr@Ofc@@@2@AEAVIWriterParams@2@PEBVCVarStr@2@@Z; Ofc::TSimpleElemWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::CVarStr> const &,Ofc::IWriterParams &,Ofc::CVarStr const *)
0x180049b04  lea     r8, [rdi+8]
0x180049b08  mov     r9, rsi
0x180049b0b  mov     edx, r15d
0x180049b0e  lea     rcx, aDesc; "desc"
0x180049b15  call    ?Write@?$TSimpleElemWriterHelper@VCVarStr@Ofc@@V?$TOptionalAdapter@VCVarStr@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VCVarStr@Ofc@@@2@AEAVIWriterParams@2@PEBVCVarStr@2@@Z; Ofc::TSimpleElemWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::CVarStr> const &,Ofc::IWriterParams &,Ofc::CVarStr const *)
0x180049b1a  lea     r8, [rdi+10h]
0x180049b1e  mov     r9, rsi
0x180049b21  call    ?Write@?$TCompElemWriterHelper@VEventListeners@ODF@@V?$TOptionalAdapter@VEventListeners@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VEventListeners@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TCompElemWriterHelper<ODF::EventListeners,Ofc::TOptionalAdapter<ODF::EventListeners>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::EventListeners> const &,Ofc::IWriterParams &)
0x180049b26  mov     rcx, r14
0x180049b29  call    cs:__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ; Ofc::CWriterEmit::EmitEndElement(void)
0x180049b2f  nop
0x180049b30  mov     rbx, [rsp+48h+arg_8]
0x180049b35  mov     rbp, [rsp+48h+arg_10]
0x180049b3a  mov     rsi, [rsp+48h+arg_18]
0x180049b3f  add     rsp, 30h
0x180049b43  pop     r15
0x180049b45  pop     r14
0x180049b47  pop     rdi
0x180049b48  retn
```
