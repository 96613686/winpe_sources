# Ofc::TComplexTypeHelper<ODF::Sphere>::FillWriters(ODF::Sphere const &,Ofc::CNamespaceDeclarationTracker &,Ofc::CWriterEmit &,Ofc::IWriterParams &)

- ea: `0x180024298`
- end: `0x1800244f2`
- name: `?FillWriters@?$TComplexTypeHelper@VSphere@ODF@@@Ofc@@SAXAEBVSphere@ODF@@AEAVCNamespaceDeclarationTracker@2@AEAVCWriterEmit@2@AEAVIWriterParams@2@@Z`
- size: `602`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180025b70`

## callees

- `0x18001db8c`
- `0x18001dc30`
- `0x18001dd94`
- `0x180024298`
- `0x180025c28`
- `0x180025da4`
- `0x1800261c4`
- `0x1801a80e0`

## import_xrefs

- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800242c5`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800242ed`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18002431c`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18002435b`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180024384`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800243a6`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800243eb`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180024414`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180024443`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18002446c`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18002448e`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800242c5`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800242ed`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18002431c`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18002435b`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180024384`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800243a6`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800243eb`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180024414`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180024443`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18002446c`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18002448e`
- `mso40uiWin32Client!__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ` at `0x1800244dc`
- `mso40uiWin32Client!__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ` at `0x1800244dc`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Ofc::TComplexTypeHelper<ODF::Sphere>::FillWriters(
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
  Ofc::TAttrWriterHelper<ODF::Vector3D,Ofc::TOptionalAdapter<ODF::Vector3D>,0>::Write(L"center", 306, a1, a4);
  if ( a1[1] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 306);
  Ofc::TAttrWriterHelper<ODF::Vector3D,Ofc::TOptionalAdapter<ODF::Vector3D>,0>::Write(L"size", 306, a1 + 1, a4);
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
0x180024298  push    rbx
0x18002429a  push    rbp
0x18002429b  push    rsi
0x18002429c  push    rdi
0x18002429d  push    r13
0x18002429f  push    r14
0x1800242a1  push    r15
0x1800242a3  sub     rsp, 30h
0x1800242a7  mov     rsi, r9
0x1800242aa  mov     r14, r8
0x1800242ad  mov     rbx, rdx
0x1800242b0  mov     rdi, rcx
0x1800242b3  mov     r13d, 132h
0x1800242b9  cmp     qword ptr [rcx], 0
0x1800242bd  jz      short loc_1800242CB
0x1800242bf  mov     edx, r13d
0x1800242c2  mov     rcx, rbx
0x1800242c5  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800242cb  mov     r9, rsi
0x1800242ce  mov     r8, rdi
0x1800242d1  mov     edx, r13d
0x1800242d4  lea     rcx, aCenter; "center"
0x1800242db  call    ?Write@?$TAttrWriterHelper@VVector3D@ODF@@V?$TOptionalAdapter@VVector3D@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VVector3D@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::Vector3D,Ofc::TOptionalAdapter<ODF::Vector3D>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::Vector3D> const &,Ofc::IWriterParams &)
0x1800242e0  cmp     qword ptr [rdi+8], 0
0x1800242e5  jz      short loc_1800242F3
0x1800242e7  mov     edx, r13d
0x1800242ea  mov     rcx, rbx
0x1800242ed  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800242f3  mov     r9, rsi
0x1800242f6  lea     r8, [rdi+8]
0x1800242fa  mov     edx, r13d
0x1800242fd  lea     rcx, aSize; "size"
0x180024304  call    ?Write@?$TAttrWriterHelper@VVector3D@ODF@@V?$TOptionalAdapter@VVector3D@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VVector3D@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::Vector3D,Ofc::TOptionalAdapter<ODF::Vector3D>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::Vector3D> const &,Ofc::IWriterParams &)
0x180024309  mov     r15d, 133h
0x18002430f  cmp     qword ptr [rdi+10h], 0
0x180024314  jz      short loc_180024322
0x180024316  mov     edx, r15d
0x180024319  mov     rcx, rbx
0x18002431c  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x180024322  lea     rax, dword_1801DBD74
0x180024329  mov     [rsp+68h+arg_0], rax
0x18002432e  lea     rax, [rsp+68h+arg_0]
0x180024333  mov     [rsp+68h+var_48], rax
0x180024338  mov     r9, rsi
0x18002433b  lea     r8, [rdi+10h]
0x18002433f  mov     edx, r15d
0x180024342  lea     rcx, aName; "name"
0x180024349  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TOptionalAdapter@VCVarStr@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VCVarStr@Ofc@@@2@AEAVIWriterParams@2@PEBVCVarStr@2@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::CVarStr> const &,Ofc::IWriterParams &,Ofc::CVarStr const *)
0x18002434e  cmp     qword ptr [rdi+18h], 0
0x180024353  jz      short loc_180024361
0x180024355  mov     edx, r15d
0x180024358  mov     rcx, rbx
0x18002435b  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x180024361  mov     r9, rsi
0x180024364  lea     r8, [rdi+18h]
0x180024368  mov     edx, r15d
0x18002436b  lea     rcx, aZIndex; "z-index"
0x180024372  call    ?Write@?$TAttrWriterHelper@IV?$TOptionalAdapter@I@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@I@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<uint,Ofc::TOptionalAdapter<uint>,0>::Write(wchar_t const *,int,Ofc::TOptional<uint> const &,Ofc::IWriterParams &)
0x180024377  cmp     qword ptr [rdi+20h], 0
0x18002437c  jz      short loc_18002438A
0x18002437e  mov     edx, r15d
0x180024381  mov     rcx, rbx
0x180024384  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18002438a  mov     r9, rsi
0x18002438d  lea     r8, [rdi+20h]
0x180024391  mov     edx, r15d
0x180024394  lea     rcx, aId; "id"
0x18002439b  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TOptionalAdapter@VCVarStr@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VCVarStr@Ofc@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::CVarStr> const &,Ofc::IWriterParams &)
0x1800243a0  mov     edx, r15d
0x1800243a3  mov     rcx, rbx
0x1800243a6  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800243ac  lea     rax, dword_1801DBD74
0x1800243b3  mov     [rsp+68h+arg_10], rax
0x1800243bb  lea     r8, [rdi+28h]
0x1800243bf  lea     rax, [rsp+68h+arg_10]
0x1800243c7  mov     [rsp+68h+var_48], rax
0x1800243cc  mov     r9, rsi
0x1800243cf  mov     edx, r15d
0x1800243d2  lea     rcx, aLayer; "layer"
0x1800243d9  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TSelfAdapter@VCVarStr@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBVCVarStr@2@AEAVIWriterParams@2@PEBV32@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(wchar_t const *,int,Ofc::CVarStr const &,Ofc::IWriterParams &,Ofc::CVarStr const *)
0x1800243de  cmp     qword ptr [rdi+30h], 0
0x1800243e3  jz      short loc_1800243F1
0x1800243e5  mov     edx, r15d
0x1800243e8  mov     rcx, rbx
0x1800243eb  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800243f1  mov     r9, rsi
0x1800243f4  lea     r8, [rdi+30h]
0x1800243f8  mov     edx, r15d
0x1800243fb  lea     rcx, aStyleName; "style-name"
0x180024402  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TOptionalAdapter@VCVarStr@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VCVarStr@Ofc@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::CVarStr> const &,Ofc::IWriterParams &)
0x180024407  cmp     qword ptr [rdi+38h], 0
0x18002440c  jz      short loc_18002441A
0x18002440e  mov     edx, r15d
0x180024411  mov     rcx, rbx
0x180024414  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18002441a  mov     r9, rsi
0x18002441d  lea     r8, [rdi+38h]
0x180024421  mov     edx, r15d
0x180024424  lea     rcx, aClassNames; "class-names"
0x18002442b  call    ?Write@?$TAttrWriterHelper@V?$TArray@VCVarStr@Ofc@@@Ofc@@V?$TOptionalAdapter@V?$TArray@VCVarStr@Ofc@@@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@V?$TArray@VCVarStr@Ofc@@@Ofc@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::TArray<Ofc::CVarStr>,Ofc::TOptionalAdapter<Ofc::TArray<Ofc::CVarStr>>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::TArray<Ofc::CVarStr>> const &,Ofc::IWriterParams &)
0x180024430  mov     r15d, 13Bh
0x180024436  cmp     qword ptr [rdi+40h], 0
0x18002443b  jz      short loc_180024449
0x18002443d  mov     edx, r15d
0x180024440  mov     rcx, rbx
0x180024443  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x180024449  mov     r9, rsi
0x18002444c  lea     r8, [rdi+40h]
0x180024450  mov     edx, r15d
0x180024453  lea     rcx, aStyleName; "style-name"
0x18002445a  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TOptionalAdapter@VCVarStr@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VCVarStr@Ofc@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::CVarStr> const &,Ofc::IWriterParams &)
0x18002445f  cmp     qword ptr [rdi+48h], 0
0x180024464  jz      short loc_180024472
0x180024466  mov     edx, r15d
0x180024469  mov     rcx, rbx
0x18002446c  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x180024472  mov     r9, rsi
0x180024475  lea     r8, [rdi+48h]
0x180024479  mov     edx, r15d
0x18002447c  lea     rcx, aClassNames; "class-names"
0x180024483  call    ?Write@?$TAttrWriterHelper@V?$TArray@VCVarStr@Ofc@@@Ofc@@V?$TOptionalAdapter@V?$TArray@VCVarStr@Ofc@@@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@V?$TArray@VCVarStr@Ofc@@@Ofc@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::TArray<Ofc::CVarStr>,Ofc::TOptionalAdapter<Ofc::TArray<Ofc::CVarStr>>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::TArray<Ofc::CVarStr>> const &,Ofc::IWriterParams &)
0x180024488  mov     edx, r13d
0x18002448b  mov     rcx, rbx
0x18002448e  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x180024494  lea     rax, dword_1801DBD74
0x18002449b  mov     [rsp+68h+arg_18], rax
0x1800244a3  lea     r8, [rdi+50h]
0x1800244a7  lea     rax, [rsp+68h+arg_18]
0x1800244af  mov     [rsp+68h+var_48], rax
0x1800244b4  mov     r9, rsi
0x1800244b7  mov     edx, r13d
0x1800244ba  lea     rcx, aTransform; "transform"
0x1800244c1  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TSelfAdapter@VCVarStr@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBVCVarStr@2@AEAVIWriterParams@2@PEBV32@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(wchar_t const *,int,Ofc::CVarStr const &,Ofc::IWriterParams &,Ofc::CVarStr const *)
0x1800244c6  mov     rax, [r14]
0x1800244c9  mov     rdx, [rsi+10h]
0x1800244cd  mov     rcx, r14
0x1800244d0  mov     rax, [rax]
0x1800244d3  call    cs:__guard_dispatch_icall_fptr
0x1800244d9  mov     rcx, r14
0x1800244dc  call    cs:__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ; Ofc::CWriterEmit::EmitEndElement(void)
0x1800244e2  nop
0x1800244e3  add     rsp, 30h
0x1800244e7  pop     r15
0x1800244e9  pop     r14
0x1800244eb  pop     r13
0x1800244ed  pop     rdi
0x1800244ee  pop     rsi
0x1800244ef  pop     rbp
0x1800244f0  pop     rbx
0x1800244f1  retn
```
