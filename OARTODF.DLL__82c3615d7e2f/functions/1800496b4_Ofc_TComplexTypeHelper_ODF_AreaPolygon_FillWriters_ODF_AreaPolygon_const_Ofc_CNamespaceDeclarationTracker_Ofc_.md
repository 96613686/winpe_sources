# Ofc::TComplexTypeHelper<ODF::AreaPolygon>::FillWriters(ODF::AreaPolygon const &,Ofc::CNamespaceDeclarationTracker &,Ofc::CWriterEmit &,Ofc::IWriterParams &)

- ea: `0x1800496b4`
- end: `0x180049917`
- name: `?FillWriters@?$TComplexTypeHelper@VAreaPolygon@ODF@@@Ofc@@SAXAEBVAreaPolygon@ODF@@AEAVCNamespaceDeclarationTracker@2@AEAVCWriterEmit@2@AEAVIWriterParams@2@@Z`
- size: `611`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180053a80`

## callees

- `0x18001db8c`
- `0x18001dd94`
- `0x180025d10`
- `0x180025f94`
- `0x180026300`
- `0x18002e1f0`
- `0x18002e70c`
- `0x18002e844`
- `0x1800496b4`
- `0x180054bdc`
- `0x180054df0`
- `0x180054fc4`
- `0x1801a80e0`

## import_xrefs

- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800496eb`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18004970d`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180049740`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18004975f`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180049779`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800497bc`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800497e1`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18004980a`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180049833`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18004985c`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18004987e`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180049898`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800496eb`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18004970d`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180049740`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18004975f`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180049779`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800497bc`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800497e1`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18004980a`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180049833`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18004985c`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18004987e`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180049898`
- `mso40uiWin32Client!__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ` at `0x1800498f7`
- `mso40uiWin32Client!__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ` at `0x1800498f7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Ofc::TComplexTypeHelper<ODF::AreaPolygon>::FillWriters(
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
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rcx
  const wchar_t *v22; // [rsp+50h] [rbp+8h] BYREF

  if ( a1[3] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 323);
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(L"href", 323, a1 + 3, a4);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 323);
  LODWORD(v22) = 0;
  Ofc::TAttrWriterHelper<enum ODF::XlinkType,Ofc::TSelfAdapter<enum ODF::XlinkType>,1>::Write(
    v9,
    v8,
    (_DWORD)a1 + 32,
    a4,
    (__int64)&v22);
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
  v22 = &dword_1801DBD74;
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(
    (unsigned int)L"name",
    300,
    (_DWORD)a1 + 56,
    a4,
    (__int64)&v22);
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
    L"width",
    318,
    a1 + 11,
    a4);
  if ( a1[12] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 318);
  Ofc::TAttrWriterHelper<ODF::PositiveLength,Ofc::TOptionalAdapter<ODF::PositiveLength>,0>::Write(
    L"height",
    318,
    a1 + 12,
    a4);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 318);
  Ofc::TAttrWriterHelper<Ofc::TArray<int>,Ofc::TSelfAdapter<Ofc::TArray<int>>,1>::Write(v17, v16, a1 + 13, a4);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 307);
  Ofc::TAttrWriterHelper<ODF::Points,Ofc::TSelfAdapter<ODF::Points>,1>::Write(v19, v18, a1 + 15, a4);
  (**(void (__fastcall ***)(Ofc::CWriterEmit *, _QWORD))a3)(a3, *(_QWORD *)(a4 + 16));
  Ofc::TSimpleElemWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(L"title", 318, a1, a4);
  Ofc::TSimpleElemWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(L"desc", 318, a1 + 1, a4);
  Ofc::TCompElemWriterHelper<ODF::EventListeners,Ofc::TOptionalAdapter<ODF::EventListeners>,0>::Write(
    v21,
    v20,
    a1 + 2,
    a4);
  Ofc::CWriterEmit::EmitEndElement(a3);
}

```

## disassembly

```asm
0x1800496b4  mov     [rsp+arg_8], rbx
0x1800496b9  mov     [rsp+arg_10], rbp
0x1800496be  mov     [rsp+arg_18], rsi
0x1800496c3  push    rdi
0x1800496c4  push    r12
0x1800496c6  push    r14
0x1800496c8  sub     rsp, 30h
0x1800496cc  mov     rsi, r9
0x1800496cf  mov     r14, r8
0x1800496d2  mov     rbx, rdx
0x1800496d5  mov     rdi, rcx
0x1800496d8  mov     r12d, 143h
0x1800496de  cmp     qword ptr [rcx+18h], 0
0x1800496e3  jz      short loc_1800496F1
0x1800496e5  mov     edx, r12d
0x1800496e8  mov     rcx, rbx
0x1800496eb  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800496f1  mov     r9, rsi
0x1800496f4  lea     r8, [rdi+18h]
0x1800496f8  mov     edx, r12d
0x1800496fb  lea     rcx, aHref; "href"
0x180049702  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TOptionalAdapter@VCVarStr@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VCVarStr@Ofc@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::CVarStr> const &,Ofc::IWriterParams &)
0x180049707  mov     edx, r12d
0x18004970a  mov     rcx, rbx
0x18004970d  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x180049713  mov     dword ptr [rsp+48h+arg_0], 0
0x18004971b  lea     r8, [rdi+20h]
0x18004971f  lea     rax, [rsp+48h+arg_0]
0x180049724  mov     [rsp+48h+var_28], rax
0x180049729  mov     r9, rsi
0x18004972c  call    ?Write@?$TAttrWriterHelper@W4XlinkType@ODF@@V?$TSelfAdapter@W4XlinkType@ODF@@@Ofc@@$00@Ofc@@SAXPEB_WHAEBW4XlinkType@ODF@@AEAVIWriterParams@2@PEBW434@@Z; Ofc::TAttrWriterHelper<ODF::XlinkType,Ofc::TSelfAdapter<ODF::XlinkType>,1>::Write(wchar_t const *,int,ODF::XlinkType const &,Ofc::IWriterParams &,ODF::XlinkType const *)
0x180049731  cmp     qword ptr [rdi+28h], 0
0x180049736  jz      short loc_180049746
0x180049738  mov     edx, 12Ch
0x18004973d  mov     rcx, rbx
0x180049740  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x180049746  mov     r9, rsi
0x180049749  lea     r8, [rdi+28h]
0x18004974d  call    ?Write@?$TAttrWriterHelper@V?$TVariant@VTargetFrameNameIDsImpl@ODF@@@Ofc@@V?$TOptionalAdapter@V?$TVariant@VTargetFrameNameIDsImpl@ODF@@@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@V?$TVariant@VTargetFrameNameIDsImpl@ODF@@@Ofc@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::TVariant<ODF::TargetFrameNameIDsImpl>,Ofc::TOptionalAdapter<Ofc::TVariant<ODF::TargetFrameNameIDsImpl>>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::TVariant<ODF::TargetFrameNameIDsImpl>> const &,Ofc::IWriterParams &)
0x180049752  cmp     qword ptr [rdi+30h], 0
0x180049757  jz      short loc_180049765
0x180049759  mov     edx, r12d
0x18004975c  mov     rcx, rbx
0x18004975f  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x180049765  mov     r9, rsi
0x180049768  lea     r8, [rdi+30h]
0x18004976c  call    ?Write@?$TAttrWriterHelper@W4XlinkShow1Show@ODF@@V?$TOptionalAdapter@W4XlinkShow1Show@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@W4XlinkShow1Show@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::XlinkShow1Show,Ofc::TOptionalAdapter<ODF::XlinkShow1Show>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::XlinkShow1Show> const &,Ofc::IWriterParams &)
0x180049771  mov     edx, 12Ch
0x180049776  mov     rcx, rbx
0x180049779  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18004977f  lea     rax, dword_1801DBD74
0x180049786  mov     [rsp+48h+arg_0], rax
0x18004978b  lea     r8, [rdi+38h]
0x18004978f  lea     rax, [rsp+48h+arg_0]
0x180049794  mov     [rsp+48h+var_28], rax
0x180049799  mov     r9, rsi
0x18004979c  mov     edx, 12Ch
0x1800497a1  lea     rcx, aName; "name"
0x1800497a8  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TSelfAdapter@VCVarStr@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBVCVarStr@2@AEAVIWriterParams@2@PEBV32@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(wchar_t const *,int,Ofc::CVarStr const &,Ofc::IWriterParams &,Ofc::CVarStr const *)
0x1800497ad  cmp     qword ptr [rdi+40h], 0
0x1800497b2  jz      short loc_1800497C2
0x1800497b4  mov     edx, 133h
0x1800497b9  mov     rcx, rbx
0x1800497bc  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800497c2  mov     r9, rsi
0x1800497c5  lea     r8, [rdi+40h]
0x1800497c9  call    ?Write@?$TAttrWriterHelper@W4Nohref@ODF@@V?$TOptionalAdapter@W4Nohref@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@W4Nohref@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::Nohref,Ofc::TOptionalAdapter<ODF::Nohref>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::Nohref> const &,Ofc::IWriterParams &)
0x1800497ce  mov     r12d, 13Eh
0x1800497d4  cmp     qword ptr [rdi+48h], 0
0x1800497d9  jz      short loc_1800497E7
0x1800497db  mov     edx, r12d
0x1800497de  mov     rcx, rbx
0x1800497e1  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800497e7  mov     r9, rsi
0x1800497ea  lea     r8, [rdi+48h]
0x1800497ee  mov     edx, r12d
0x1800497f1  lea     rcx, asc_1801DF854; "x"
0x1800497f8  call    ?Write@?$TAttrWriterHelper@VPositiveLength@ODF@@V?$TOptionalAdapter@VPositiveLength@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VPositiveLength@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::PositiveLength,Ofc::TOptionalAdapter<ODF::PositiveLength>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::PositiveLength> const &,Ofc::IWriterParams &)
0x1800497fd  cmp     qword ptr [rdi+50h], 0
0x180049802  jz      short loc_180049810
0x180049804  mov     edx, r12d
0x180049807  mov     rcx, rbx
0x18004980a  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x180049810  mov     r9, rsi
0x180049813  lea     r8, [rdi+50h]
0x180049817  mov     edx, r12d
0x18004981a  lea     rcx, aY; "y"
0x180049821  call    ?Write@?$TAttrWriterHelper@VPositiveLength@ODF@@V?$TOptionalAdapter@VPositiveLength@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VPositiveLength@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::PositiveLength,Ofc::TOptionalAdapter<ODF::PositiveLength>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::PositiveLength> const &,Ofc::IWriterParams &)
0x180049826  cmp     qword ptr [rdi+58h], 0
0x18004982b  jz      short loc_180049839
0x18004982d  mov     edx, r12d
0x180049830  mov     rcx, rbx
0x180049833  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x180049839  mov     r9, rsi
0x18004983c  lea     r8, [rdi+58h]
0x180049840  mov     edx, r12d
0x180049843  lea     rcx, aWidth; "width"
0x18004984a  call    ?Write@?$TAttrWriterHelper@VPositiveLength@ODF@@V?$TOptionalAdapter@VPositiveLength@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VPositiveLength@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::PositiveLength,Ofc::TOptionalAdapter<ODF::PositiveLength>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::PositiveLength> const &,Ofc::IWriterParams &)
0x18004984f  cmp     qword ptr [rdi+60h], 0
0x180049854  jz      short loc_180049862
0x180049856  mov     edx, r12d
0x180049859  mov     rcx, rbx
0x18004985c  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x180049862  mov     r9, rsi
0x180049865  lea     r8, [rdi+60h]
0x180049869  mov     edx, r12d
0x18004986c  lea     rcx, aHeight; "height"
0x180049873  call    ?Write@?$TAttrWriterHelper@VPositiveLength@ODF@@V?$TOptionalAdapter@VPositiveLength@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VPositiveLength@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::PositiveLength,Ofc::TOptionalAdapter<ODF::PositiveLength>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::PositiveLength> const &,Ofc::IWriterParams &)
0x180049878  mov     edx, r12d
0x18004987b  mov     rcx, rbx
0x18004987e  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x180049884  lea     r8, [rdi+68h]
0x180049888  mov     r9, rsi
0x18004988b  call    ?Write@?$TAttrWriterHelper@V?$TArray@H@Ofc@@V?$TSelfAdapter@V?$TArray@H@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBV?$TArray@H@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::TArray<int>,Ofc::TSelfAdapter<Ofc::TArray<int>>,1>::Write(wchar_t const *,int,Ofc::TArray<int> const &,Ofc::IWriterParams &)
0x180049890  mov     edx, 133h
0x180049895  mov     rcx, rbx
0x180049898  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18004989e  lea     r8, [rdi+78h]
0x1800498a2  mov     r9, rsi
0x1800498a5  call    ?Write@?$TAttrWriterHelper@VPoints@ODF@@V?$TSelfAdapter@VPoints@ODF@@@Ofc@@$00@Ofc@@SAXPEB_WHAEBVPoints@ODF@@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::Points,Ofc::TSelfAdapter<ODF::Points>,1>::Write(wchar_t const *,int,ODF::Points const &,Ofc::IWriterParams &)
0x1800498aa  mov     rax, [r14]
0x1800498ad  mov     rdx, [rsi+10h]
0x1800498b1  mov     rcx, r14
0x1800498b4  mov     rax, [rax]
0x1800498b7  call    cs:__guard_dispatch_icall_fptr
0x1800498bd  mov     r9, rsi
0x1800498c0  mov     r8, rdi
0x1800498c3  mov     edx, r12d
0x1800498c6  lea     rcx, aTitle; "title"
0x1800498cd  call    ?Write@?$TSimpleElemWriterHelper@VCVarStr@Ofc@@V?$TOptionalAdapter@VCVarStr@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VCVarStr@Ofc@@@2@AEAVIWriterParams@2@PEBVCVarStr@2@@Z; Ofc::TSimpleElemWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::CVarStr> const &,Ofc::IWriterParams &,Ofc::CVarStr const *)
0x1800498d2  lea     r8, [rdi+8]
0x1800498d6  mov     r9, rsi
0x1800498d9  mov     edx, r12d
0x1800498dc  lea     rcx, aDesc; "desc"
0x1800498e3  call    ?Write@?$TSimpleElemWriterHelper@VCVarStr@Ofc@@V?$TOptionalAdapter@VCVarStr@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VCVarStr@Ofc@@@2@AEAVIWriterParams@2@PEBVCVarStr@2@@Z; Ofc::TSimpleElemWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::CVarStr> const &,Ofc::IWriterParams &,Ofc::CVarStr const *)
0x1800498e8  lea     r8, [rdi+10h]
0x1800498ec  mov     r9, rsi
0x1800498ef  call    ?Write@?$TCompElemWriterHelper@VEventListeners@ODF@@V?$TOptionalAdapter@VEventListeners@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VEventListeners@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TCompElemWriterHelper<ODF::EventListeners,Ofc::TOptionalAdapter<ODF::EventListeners>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::EventListeners> const &,Ofc::IWriterParams &)
0x1800498f4  mov     rcx, r14
0x1800498f7  call    cs:__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ; Ofc::CWriterEmit::EmitEndElement(void)
0x1800498fd  nop
0x1800498fe  mov     rbx, [rsp+48h+arg_8]
0x180049903  mov     rbp, [rsp+48h+arg_10]
0x180049908  mov     rsi, [rsp+48h+arg_18]
0x18004990d  add     rsp, 30h
0x180049911  pop     r14
0x180049913  pop     r12
0x180049915  pop     rdi
0x180049916  retn
```
