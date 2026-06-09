# Ofc::TComplexTypeHelper<ODF::Cube>::FillWriters(ODF::Cube const &,Ofc::CNamespaceDeclarationTracker &,Ofc::CWriterEmit &,Ofc::IWriterParams &)

- ea: `0x180023280`
- end: `0x1800234da`
- name: `?FillWriters@?$TComplexTypeHelper@VCube@ODF@@@Ofc@@SAXAEBVCube@ODF@@AEAVCNamespaceDeclarationTracker@2@AEAVCWriterEmit@2@AEAVIWriterParams@2@@Z`
- size: `602`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800258e0`

## callees

- `0x18001db8c`
- `0x18001dc30`
- `0x18001dd94`
- `0x180023280`
- `0x180025c28`
- `0x180025da4`
- `0x1800261c4`
- `0x1801a80e0`

## import_xrefs

- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800232ad`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800232d5`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180023304`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180023343`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18002336c`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18002338e`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800233d3`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800233fc`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18002342b`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180023454`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180023476`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800232ad`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800232d5`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180023304`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180023343`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18002336c`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18002338e`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800233d3`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800233fc`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18002342b`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180023454`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180023476`
- `mso40uiWin32Client!__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ` at `0x1800234c4`
- `mso40uiWin32Client!__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ` at `0x1800234c4`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Ofc::TComplexTypeHelper<ODF::Cube>::FillWriters(
        _QWORD *a1,
        Ofc::CNamespaceDeclarationTracker *a2,
        Ofc::CWriterEmit *a3,
        __int64 a4)
{
  const wchar_t *v8; // [rsp+70h] [rbp+8h] BYREF
  const wchar_t *v9; // [rsp+80h] [rbp+18h] BYREF
  const wchar_t *v10; // [rsp+88h] [rbp+20h] BYREF

  if ( *a1 )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 306);
  Ofc::TAttrWriterHelper<ODF::Vector3D,Ofc::TOptionalAdapter<ODF::Vector3D>,0>::Write(L"min-edge", 306, a1, a4);
  if ( a1[1] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 306);
  Ofc::TAttrWriterHelper<ODF::Vector3D,Ofc::TOptionalAdapter<ODF::Vector3D>,0>::Write(L"max-edge", 306, a1 + 1, a4);
  if ( a1[2] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 307);
  v8 = &dword_1801DBD74;
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(
    (unsigned int)L"name",
    307,
    (_DWORD)a1 + 16,
    a4,
    (__int64)&v8);
  if ( a1[3] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 307);
  Ofc::TAttrWriterHelper<unsigned int,Ofc::TOptionalAdapter<unsigned int>,0>::Write(L"z-index", 307, a1 + 3, a4);
  if ( a1[4] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 307);
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(L"id", 307, a1 + 4, a4);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 307);
  v9 = &dword_1801DBD74;
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(
    (unsigned int)L"layer",
    307,
    (_DWORD)a1 + 40,
    a4,
    (__int64)&v9);
  if ( a1[6] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 307);
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(L"style-name", 307, a1 + 6, a4);
  if ( a1[7] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 307);
  Ofc::TAttrWriterHelper<Ofc::TArray<Ofc::CVarStr>,Ofc::TOptionalAdapter<Ofc::TArray<Ofc::CVarStr>>,0>::Write(
    L"class-names",
    307,
    a1 + 7,
    a4);
  if ( a1[8] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 315);
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(L"style-name", 315, a1 + 8, a4);
  if ( a1[9] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 315);
  Ofc::TAttrWriterHelper<Ofc::TArray<Ofc::CVarStr>,Ofc::TOptionalAdapter<Ofc::TArray<Ofc::CVarStr>>,0>::Write(
    L"class-names",
    315,
    a1 + 9,
    a4);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 306);
  v10 = &dword_1801DBD74;
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(
    (unsigned int)L"transform",
    306,
    (_DWORD)a1 + 80,
    a4,
    (__int64)&v10);
  (**(void (__fastcall ***)(Ofc::CWriterEmit *, _QWORD))a3)(a3, *(_QWORD *)(a4 + 16));
  Ofc::CWriterEmit::EmitEndElement(a3);
}

```

## disassembly

```asm
0x180023280  push    rbx
0x180023282  push    rbp
0x180023283  push    rsi
0x180023284  push    rdi
0x180023285  push    r13
0x180023287  push    r14
0x180023289  push    r15
0x18002328b  sub     rsp, 30h
0x18002328f  mov     rsi, r9
0x180023292  mov     r14, r8
0x180023295  mov     rbx, rdx
0x180023298  mov     rdi, rcx
0x18002329b  mov     r13d, 132h
0x1800232a1  cmp     qword ptr [rcx], 0
0x1800232a5  jz      short loc_1800232B3
0x1800232a7  mov     edx, r13d
0x1800232aa  mov     rcx, rbx
0x1800232ad  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800232b3  mov     r9, rsi
0x1800232b6  mov     r8, rdi
0x1800232b9  mov     edx, r13d
0x1800232bc  lea     rcx, aMinEdge; "min-edge"
0x1800232c3  call    ?Write@?$TAttrWriterHelper@VVector3D@ODF@@V?$TOptionalAdapter@VVector3D@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VVector3D@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::Vector3D,Ofc::TOptionalAdapter<ODF::Vector3D>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::Vector3D> const &,Ofc::IWriterParams &)
0x1800232c8  cmp     qword ptr [rdi+8], 0
0x1800232cd  jz      short loc_1800232DB
0x1800232cf  mov     edx, r13d
0x1800232d2  mov     rcx, rbx
0x1800232d5  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800232db  mov     r9, rsi
0x1800232de  lea     r8, [rdi+8]
0x1800232e2  mov     edx, r13d
0x1800232e5  lea     rcx, aMaxEdge; "max-edge"
0x1800232ec  call    ?Write@?$TAttrWriterHelper@VVector3D@ODF@@V?$TOptionalAdapter@VVector3D@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VVector3D@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::Vector3D,Ofc::TOptionalAdapter<ODF::Vector3D>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::Vector3D> const &,Ofc::IWriterParams &)
0x1800232f1  mov     r15d, 133h
0x1800232f7  cmp     qword ptr [rdi+10h], 0
0x1800232fc  jz      short loc_18002330A
0x1800232fe  mov     edx, r15d
0x180023301  mov     rcx, rbx
0x180023304  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18002330a  lea     rax, dword_1801DBD74
0x180023311  mov     [rsp+68h+arg_0], rax
0x180023316  lea     rax, [rsp+68h+arg_0]
0x18002331b  mov     [rsp+68h+var_48], rax
0x180023320  mov     r9, rsi
0x180023323  lea     r8, [rdi+10h]
0x180023327  mov     edx, r15d
0x18002332a  lea     rcx, aName; "name"
0x180023331  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TOptionalAdapter@VCVarStr@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VCVarStr@Ofc@@@2@AEAVIWriterParams@2@PEBVCVarStr@2@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::CVarStr> const &,Ofc::IWriterParams &,Ofc::CVarStr const *)
0x180023336  cmp     qword ptr [rdi+18h], 0
0x18002333b  jz      short loc_180023349
0x18002333d  mov     edx, r15d
0x180023340  mov     rcx, rbx
0x180023343  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x180023349  mov     r9, rsi
0x18002334c  lea     r8, [rdi+18h]
0x180023350  mov     edx, r15d
0x180023353  lea     rcx, aZIndex; "z-index"
0x18002335a  call    ?Write@?$TAttrWriterHelper@IV?$TOptionalAdapter@I@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@I@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<uint,Ofc::TOptionalAdapter<uint>,0>::Write(wchar_t const *,int,Ofc::TOptional<uint> const &,Ofc::IWriterParams &)
0x18002335f  cmp     qword ptr [rdi+20h], 0
0x180023364  jz      short loc_180023372
0x180023366  mov     edx, r15d
0x180023369  mov     rcx, rbx
0x18002336c  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x180023372  mov     r9, rsi
0x180023375  lea     r8, [rdi+20h]
0x180023379  mov     edx, r15d
0x18002337c  lea     rcx, aId; "id"
0x180023383  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TOptionalAdapter@VCVarStr@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VCVarStr@Ofc@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::CVarStr> const &,Ofc::IWriterParams &)
0x180023388  mov     edx, r15d
0x18002338b  mov     rcx, rbx
0x18002338e  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x180023394  lea     rax, dword_1801DBD74
0x18002339b  mov     [rsp+68h+arg_10], rax
0x1800233a3  lea     r8, [rdi+28h]
0x1800233a7  lea     rax, [rsp+68h+arg_10]
0x1800233af  mov     [rsp+68h+var_48], rax
0x1800233b4  mov     r9, rsi
0x1800233b7  mov     edx, r15d
0x1800233ba  lea     rcx, aLayer; "layer"
0x1800233c1  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TSelfAdapter@VCVarStr@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBVCVarStr@2@AEAVIWriterParams@2@PEBV32@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(wchar_t const *,int,Ofc::CVarStr const &,Ofc::IWriterParams &,Ofc::CVarStr const *)
0x1800233c6  cmp     qword ptr [rdi+30h], 0
0x1800233cb  jz      short loc_1800233D9
0x1800233cd  mov     edx, r15d
0x1800233d0  mov     rcx, rbx
0x1800233d3  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800233d9  mov     r9, rsi
0x1800233dc  lea     r8, [rdi+30h]
0x1800233e0  mov     edx, r15d
0x1800233e3  lea     rcx, aStyleName; "style-name"
0x1800233ea  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TOptionalAdapter@VCVarStr@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VCVarStr@Ofc@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::CVarStr> const &,Ofc::IWriterParams &)
0x1800233ef  cmp     qword ptr [rdi+38h], 0
0x1800233f4  jz      short loc_180023402
0x1800233f6  mov     edx, r15d
0x1800233f9  mov     rcx, rbx
0x1800233fc  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x180023402  mov     r9, rsi
0x180023405  lea     r8, [rdi+38h]
0x180023409  mov     edx, r15d
0x18002340c  lea     rcx, aClassNames; "class-names"
0x180023413  call    ?Write@?$TAttrWriterHelper@V?$TArray@VCVarStr@Ofc@@@Ofc@@V?$TOptionalAdapter@V?$TArray@VCVarStr@Ofc@@@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@V?$TArray@VCVarStr@Ofc@@@Ofc@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::TArray<Ofc::CVarStr>,Ofc::TOptionalAdapter<Ofc::TArray<Ofc::CVarStr>>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::TArray<Ofc::CVarStr>> const &,Ofc::IWriterParams &)
0x180023418  mov     r15d, 13Bh
0x18002341e  cmp     qword ptr [rdi+40h], 0
0x180023423  jz      short loc_180023431
0x180023425  mov     edx, r15d
0x180023428  mov     rcx, rbx
0x18002342b  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x180023431  mov     r9, rsi
0x180023434  lea     r8, [rdi+40h]
0x180023438  mov     edx, r15d
0x18002343b  lea     rcx, aStyleName; "style-name"
0x180023442  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TOptionalAdapter@VCVarStr@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VCVarStr@Ofc@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::CVarStr> const &,Ofc::IWriterParams &)
0x180023447  cmp     qword ptr [rdi+48h], 0
0x18002344c  jz      short loc_18002345A
0x18002344e  mov     edx, r15d
0x180023451  mov     rcx, rbx
0x180023454  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18002345a  mov     r9, rsi
0x18002345d  lea     r8, [rdi+48h]
0x180023461  mov     edx, r15d
0x180023464  lea     rcx, aClassNames; "class-names"
0x18002346b  call    ?Write@?$TAttrWriterHelper@V?$TArray@VCVarStr@Ofc@@@Ofc@@V?$TOptionalAdapter@V?$TArray@VCVarStr@Ofc@@@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@V?$TArray@VCVarStr@Ofc@@@Ofc@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::TArray<Ofc::CVarStr>,Ofc::TOptionalAdapter<Ofc::TArray<Ofc::CVarStr>>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::TArray<Ofc::CVarStr>> const &,Ofc::IWriterParams &)
0x180023470  mov     edx, r13d
0x180023473  mov     rcx, rbx
0x180023476  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18002347c  lea     rax, dword_1801DBD74
0x180023483  mov     [rsp+68h+arg_18], rax
0x18002348b  lea     r8, [rdi+50h]
0x18002348f  lea     rax, [rsp+68h+arg_18]
0x180023497  mov     [rsp+68h+var_48], rax
0x18002349c  mov     r9, rsi
0x18002349f  mov     edx, r13d
0x1800234a2  lea     rcx, aTransform; "transform"
0x1800234a9  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TSelfAdapter@VCVarStr@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBVCVarStr@2@AEAVIWriterParams@2@PEBV32@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(wchar_t const *,int,Ofc::CVarStr const &,Ofc::IWriterParams &,Ofc::CVarStr const *)
0x1800234ae  mov     rax, [r14]
0x1800234b1  mov     rdx, [rsi+10h]
0x1800234b5  mov     rcx, r14
0x1800234b8  mov     rax, [rax]
0x1800234bb  call    cs:__guard_dispatch_icall_fptr
0x1800234c1  mov     rcx, r14
0x1800234c4  call    cs:__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ; Ofc::CWriterEmit::EmitEndElement(void)
0x1800234ca  nop
0x1800234cb  add     rsp, 30h
0x1800234cf  pop     r15
0x1800234d1  pop     r14
0x1800234d3  pop     r13
0x1800234d5  pop     rdi
0x1800234d6  pop     rsi
0x1800234d7  pop     rbp
0x1800234d8  pop     rbx
0x1800234d9  retn
```
