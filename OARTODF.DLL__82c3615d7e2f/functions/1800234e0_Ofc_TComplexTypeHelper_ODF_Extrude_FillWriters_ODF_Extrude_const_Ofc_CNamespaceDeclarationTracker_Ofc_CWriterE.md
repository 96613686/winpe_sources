# Ofc::TComplexTypeHelper<ODF::Extrude>::FillWriters(ODF::Extrude const &,Ofc::CNamespaceDeclarationTracker &,Ofc::CWriterEmit &,Ofc::IWriterParams &)

- ea: `0x1800234e0`
- end: `0x180023713`
- name: `?FillWriters@?$TComplexTypeHelper@VExtrude@ODF@@@Ofc@@SAXAEBVExtrude@ODF@@AEAVCNamespaceDeclarationTracker@2@AEAVCWriterEmit@2@AEAVIWriterParams@2@@Z`
- size: `563`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800259a0`

## callees

- `0x18001db8c`
- `0x18001dc30`
- `0x18001dcf4`
- `0x18001dd94`
- `0x1800234e0`
- `0x180025c28`
- `0x180025d10`
- `0x180025da4`
- `0x1801a80e0`

## import_xrefs

- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18002350d`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180023548`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180023568`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180023587`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800235b0`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800235d2`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180023610`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180023639`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180023668`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180023691`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800236b7`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18002350d`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180023548`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180023568`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180023587`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800235b0`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800235d2`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180023610`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180023639`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180023668`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180023691`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800236b7`
- `mso40uiWin32Client!__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ` at `0x1800236fd`
- `mso40uiWin32Client!__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ` at `0x1800236fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Ofc::TComplexTypeHelper<ODF::Extrude>::FillWriters(
        _QWORD *a1,
        Ofc::CNamespaceDeclarationTracker *a2,
        Ofc::CWriterEmit *a3,
        __int64 a4)
{
  __int64 v8; // rdx
  __int64 v9; // rcx
  const wchar_t *v10; // [rsp+70h] [rbp+8h] BYREF
  const wchar_t *v11; // [rsp+80h] [rbp+18h] BYREF
  const wchar_t *v12; // [rsp+88h] [rbp+20h] BYREF

  if ( *a1 )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 307);
  v10 = &dword_1801DBD74;
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(
    (unsigned int)L"name",
    307,
    (_DWORD)a1,
    a4,
    (__int64)&v10);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 318);
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(L"d", 318, a1 + 1, a4);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 318);
  Ofc::TAttrWriterHelper<Ofc::TArray<int>,Ofc::TSelfAdapter<Ofc::TArray<int>>,1>::Write(v9, v8, a1 + 2, a4);
  if ( a1[4] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 307);
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(L"id", 307, a1 + 4, a4);
  if ( a1[5] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 307);
  Ofc::TAttrWriterHelper<unsigned int,Ofc::TOptionalAdapter<unsigned int>,0>::Write(L"z-index", 307, a1 + 5, a4);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 307);
  v11 = &dword_1801DBD74;
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(
    (unsigned int)L"layer",
    307,
    (_DWORD)a1 + 48,
    a4,
    (__int64)&v11);
  if ( a1[7] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 307);
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(L"style-name", 307, a1 + 7, a4);
  if ( a1[8] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 307);
  Ofc::TAttrWriterHelper<Ofc::TArray<Ofc::CVarStr>,Ofc::TOptionalAdapter<Ofc::TArray<Ofc::CVarStr>>,0>::Write(
    L"class-names",
    307,
    a1 + 8,
    a4);
  if ( a1[9] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 315);
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(L"style-name", 315, a1 + 9, a4);
  if ( a1[10] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 315);
  Ofc::TAttrWriterHelper<Ofc::TArray<Ofc::CVarStr>,Ofc::TOptionalAdapter<Ofc::TArray<Ofc::CVarStr>>,0>::Write(
    L"class-names",
    315,
    a1 + 10,
    a4);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 306);
  v12 = &dword_1801DBD74;
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(
    (unsigned int)L"transform",
    306,
    (_DWORD)a1 + 88,
    a4,
    (__int64)&v12);
  (**(void (__fastcall ***)(Ofc::CWriterEmit *, _QWORD))a3)(a3, *(_QWORD *)(a4 + 16));
  Ofc::CWriterEmit::EmitEndElement(a3);
}

```

## disassembly

```asm
0x1800234e0  push    rbx
0x1800234e2  push    rbp
0x1800234e3  push    rsi
0x1800234e4  push    rdi
0x1800234e5  push    r13
0x1800234e7  push    r14
0x1800234e9  push    r15
0x1800234eb  sub     rsp, 30h
0x1800234ef  mov     rsi, r9
0x1800234f2  mov     r14, r8
0x1800234f5  mov     rbx, rdx
0x1800234f8  mov     rdi, rcx
0x1800234fb  mov     r15d, 133h
0x180023501  cmp     qword ptr [rcx], 0
0x180023505  jz      short loc_180023513
0x180023507  mov     edx, r15d
0x18002350a  mov     rcx, rbx
0x18002350d  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x180023513  lea     r13, dword_1801DBD74
0x18002351a  mov     [rsp+68h+arg_0], r13
0x18002351f  lea     rax, [rsp+68h+arg_0]
0x180023524  mov     [rsp+68h+var_48], rax
0x180023529  mov     r9, rsi
0x18002352c  mov     r8, rdi
0x18002352f  mov     edx, r15d
0x180023532  lea     rcx, aName; "name"
0x180023539  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TOptionalAdapter@VCVarStr@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VCVarStr@Ofc@@@2@AEAVIWriterParams@2@PEBVCVarStr@2@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::CVarStr> const &,Ofc::IWriterParams &,Ofc::CVarStr const *)
0x18002353e  mov     ebp, 13Eh
0x180023543  mov     edx, ebp
0x180023545  mov     rcx, rbx
0x180023548  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18002354e  lea     r8, [rdi+8]
0x180023552  mov     r9, rsi
0x180023555  mov     edx, ebp
0x180023557  lea     rcx, aD; "d"
0x18002355e  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TSelfAdapter@VCVarStr@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBVCVarStr@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(wchar_t const *,int,Ofc::CVarStr const &,Ofc::IWriterParams &)
0x180023563  mov     edx, ebp
0x180023565  mov     rcx, rbx
0x180023568  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18002356e  lea     r8, [rdi+10h]
0x180023572  mov     r9, rsi
0x180023575  call    ?Write@?$TAttrWriterHelper@V?$TArray@H@Ofc@@V?$TSelfAdapter@V?$TArray@H@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBV?$TArray@H@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::TArray<int>,Ofc::TSelfAdapter<Ofc::TArray<int>>,1>::Write(wchar_t const *,int,Ofc::TArray<int> const &,Ofc::IWriterParams &)
0x18002357a  cmp     qword ptr [rdi+20h], 0
0x18002357f  jz      short loc_18002358D
0x180023581  mov     edx, r15d
0x180023584  mov     rcx, rbx
0x180023587  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18002358d  mov     r9, rsi
0x180023590  lea     r8, [rdi+20h]
0x180023594  mov     edx, r15d
0x180023597  lea     rcx, aId; "id"
0x18002359e  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TOptionalAdapter@VCVarStr@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VCVarStr@Ofc@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::CVarStr> const &,Ofc::IWriterParams &)
0x1800235a3  cmp     qword ptr [rdi+28h], 0
0x1800235a8  jz      short loc_1800235B6
0x1800235aa  mov     edx, r15d
0x1800235ad  mov     rcx, rbx
0x1800235b0  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800235b6  mov     r9, rsi
0x1800235b9  lea     r8, [rdi+28h]
0x1800235bd  mov     edx, r15d
0x1800235c0  lea     rcx, aZIndex; "z-index"
0x1800235c7  call    ?Write@?$TAttrWriterHelper@IV?$TOptionalAdapter@I@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@I@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<uint,Ofc::TOptionalAdapter<uint>,0>::Write(wchar_t const *,int,Ofc::TOptional<uint> const &,Ofc::IWriterParams &)
0x1800235cc  mov     edx, r15d
0x1800235cf  mov     rcx, rbx
0x1800235d2  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800235d8  mov     [rsp+68h+arg_10], r13
0x1800235e0  lea     r8, [rdi+30h]
0x1800235e4  lea     rax, [rsp+68h+arg_10]
0x1800235ec  mov     [rsp+68h+var_48], rax
0x1800235f1  mov     r9, rsi
0x1800235f4  mov     edx, r15d
0x1800235f7  lea     rcx, aLayer; "layer"
0x1800235fe  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TSelfAdapter@VCVarStr@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBVCVarStr@2@AEAVIWriterParams@2@PEBV32@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(wchar_t const *,int,Ofc::CVarStr const &,Ofc::IWriterParams &,Ofc::CVarStr const *)
0x180023603  cmp     qword ptr [rdi+38h], 0
0x180023608  jz      short loc_180023616
0x18002360a  mov     edx, r15d
0x18002360d  mov     rcx, rbx
0x180023610  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x180023616  mov     r9, rsi
0x180023619  lea     r8, [rdi+38h]
0x18002361d  mov     edx, r15d
0x180023620  lea     rcx, aStyleName; "style-name"
0x180023627  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TOptionalAdapter@VCVarStr@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VCVarStr@Ofc@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::CVarStr> const &,Ofc::IWriterParams &)
0x18002362c  cmp     qword ptr [rdi+40h], 0
0x180023631  jz      short loc_18002363F
0x180023633  mov     edx, r15d
0x180023636  mov     rcx, rbx
0x180023639  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18002363f  mov     r9, rsi
0x180023642  lea     r8, [rdi+40h]
0x180023646  mov     edx, r15d
0x180023649  lea     rcx, aClassNames; "class-names"
0x180023650  call    ?Write@?$TAttrWriterHelper@V?$TArray@VCVarStr@Ofc@@@Ofc@@V?$TOptionalAdapter@V?$TArray@VCVarStr@Ofc@@@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@V?$TArray@VCVarStr@Ofc@@@Ofc@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::TArray<Ofc::CVarStr>,Ofc::TOptionalAdapter<Ofc::TArray<Ofc::CVarStr>>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::TArray<Ofc::CVarStr>> const &,Ofc::IWriterParams &)
0x180023655  mov     r15d, 13Bh
0x18002365b  cmp     qword ptr [rdi+48h], 0
0x180023660  jz      short loc_18002366E
0x180023662  mov     edx, r15d
0x180023665  mov     rcx, rbx
0x180023668  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18002366e  mov     r9, rsi
0x180023671  lea     r8, [rdi+48h]
0x180023675  mov     edx, r15d
0x180023678  lea     rcx, aStyleName; "style-name"
0x18002367f  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TOptionalAdapter@VCVarStr@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VCVarStr@Ofc@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::CVarStr> const &,Ofc::IWriterParams &)
0x180023684  cmp     qword ptr [rdi+50h], 0
0x180023689  jz      short loc_180023697
0x18002368b  mov     edx, r15d
0x18002368e  mov     rcx, rbx
0x180023691  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x180023697  mov     r9, rsi
0x18002369a  lea     r8, [rdi+50h]
0x18002369e  mov     edx, r15d
0x1800236a1  lea     rcx, aClassNames; "class-names"
0x1800236a8  call    ?Write@?$TAttrWriterHelper@V?$TArray@VCVarStr@Ofc@@@Ofc@@V?$TOptionalAdapter@V?$TArray@VCVarStr@Ofc@@@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@V?$TArray@VCVarStr@Ofc@@@Ofc@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::TArray<Ofc::CVarStr>,Ofc::TOptionalAdapter<Ofc::TArray<Ofc::CVarStr>>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::TArray<Ofc::CVarStr>> const &,Ofc::IWriterParams &)
0x1800236ad  mov     ebp, 132h
0x1800236b2  mov     edx, ebp
0x1800236b4  mov     rcx, rbx
0x1800236b7  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800236bd  mov     [rsp+68h+arg_18], r13
0x1800236c5  lea     r8, [rdi+58h]
0x1800236c9  lea     rax, [rsp+68h+arg_18]
0x1800236d1  mov     [rsp+68h+var_48], rax
0x1800236d6  mov     r9, rsi
0x1800236d9  mov     edx, ebp
0x1800236db  lea     rcx, aTransform; "transform"
0x1800236e2  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TSelfAdapter@VCVarStr@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBVCVarStr@2@AEAVIWriterParams@2@PEBV32@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(wchar_t const *,int,Ofc::CVarStr const &,Ofc::IWriterParams &,Ofc::CVarStr const *)
0x1800236e7  mov     rax, [r14]
0x1800236ea  mov     rdx, [rsi+10h]
0x1800236ee  mov     rcx, r14
0x1800236f1  mov     rax, [rax]
0x1800236f4  call    cs:__guard_dispatch_icall_fptr
0x1800236fa  mov     rcx, r14
0x1800236fd  call    cs:__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ; Ofc::CWriterEmit::EmitEndElement(void)
0x180023703  nop
0x180023704  add     rsp, 30h
0x180023708  pop     r15
0x18002370a  pop     r14
0x18002370c  pop     r13
0x18002370e  pop     rdi
0x18002370f  pop     rsi
0x180023710  pop     rbp
0x180023711  pop     rbx
0x180023712  retn
```
