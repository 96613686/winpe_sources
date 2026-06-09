# Ofc::TComplexTypeHelper<ODF::Rotate>::FillWriters(ODF::Rotate const &,Ofc::CNamespaceDeclarationTracker &,Ofc::CWriterEmit &,Ofc::IWriterParams &)

- ea: `0x180023868`
- end: `0x180023a9b`
- name: `?FillWriters@?$TComplexTypeHelper@VRotate@ODF@@@Ofc@@SAXAEBVRotate@ODF@@AEAVCNamespaceDeclarationTracker@2@AEAVCWriterEmit@2@AEAVIWriterParams@2@@Z`
- size: `563`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180025a60`

## callees

- `0x18001db8c`
- `0x18001dc30`
- `0x18001dcf4`
- `0x18001dd94`
- `0x180023868`
- `0x180025c28`
- `0x180025d10`
- `0x180025da4`
- `0x1801a80e0`

## import_xrefs

- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180023895`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800238d0`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800238e7`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18002390f`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180023938`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18002395a`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180023998`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800239c1`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800239f0`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180023a19`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180023a3f`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180023895`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800238d0`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800238e7`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18002390f`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180023938`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18002395a`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180023998`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800239c1`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800239f0`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180023a19`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180023a3f`
- `mso40uiWin32Client!__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ` at `0x180023a85`
- `mso40uiWin32Client!__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ` at `0x180023a85`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Ofc::TComplexTypeHelper<ODF::Rotate>::FillWriters(
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
  Ofc::TAttrWriterHelper<Ofc::TArray<int>,Ofc::TSelfAdapter<Ofc::TArray<int>>,1>::Write(v9, v8, a1 + 1, a4);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 318);
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(L"d", 318, a1 + 3, a4);
  if ( a1[4] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 307);
  Ofc::TAttrWriterHelper<unsigned int,Ofc::TOptionalAdapter<unsigned int>,0>::Write(L"z-index", 307, a1 + 4, a4);
  if ( a1[5] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 307);
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(L"id", 307, a1 + 5, a4);
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
0x180023868  push    rbx
0x18002386a  push    rbp
0x18002386b  push    rsi
0x18002386c  push    rdi
0x18002386d  push    r13
0x18002386f  push    r14
0x180023871  push    r15
0x180023873  sub     rsp, 30h
0x180023877  mov     rsi, r9
0x18002387a  mov     r14, r8
0x18002387d  mov     rbx, rdx
0x180023880  mov     rdi, rcx
0x180023883  mov     r15d, 133h
0x180023889  cmp     qword ptr [rcx], 0
0x18002388d  jz      short loc_18002389B
0x18002388f  mov     edx, r15d
0x180023892  mov     rcx, rbx
0x180023895  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18002389b  lea     r13, dword_1801DBD74
0x1800238a2  mov     [rsp+68h+arg_0], r13
0x1800238a7  lea     rax, [rsp+68h+arg_0]
0x1800238ac  mov     [rsp+68h+var_48], rax
0x1800238b1  mov     r9, rsi
0x1800238b4  mov     r8, rdi
0x1800238b7  mov     edx, r15d
0x1800238ba  lea     rcx, aName; "name"
0x1800238c1  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TOptionalAdapter@VCVarStr@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VCVarStr@Ofc@@@2@AEAVIWriterParams@2@PEBVCVarStr@2@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::CVarStr> const &,Ofc::IWriterParams &,Ofc::CVarStr const *)
0x1800238c6  mov     ebp, 13Eh
0x1800238cb  mov     edx, ebp
0x1800238cd  mov     rcx, rbx
0x1800238d0  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800238d6  lea     r8, [rdi+8]
0x1800238da  mov     r9, rsi
0x1800238dd  call    ?Write@?$TAttrWriterHelper@V?$TArray@H@Ofc@@V?$TSelfAdapter@V?$TArray@H@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBV?$TArray@H@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::TArray<int>,Ofc::TSelfAdapter<Ofc::TArray<int>>,1>::Write(wchar_t const *,int,Ofc::TArray<int> const &,Ofc::IWriterParams &)
0x1800238e2  mov     edx, ebp
0x1800238e4  mov     rcx, rbx
0x1800238e7  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800238ed  lea     r8, [rdi+18h]
0x1800238f1  mov     r9, rsi
0x1800238f4  mov     edx, ebp
0x1800238f6  lea     rcx, aD; "d"
0x1800238fd  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TSelfAdapter@VCVarStr@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBVCVarStr@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(wchar_t const *,int,Ofc::CVarStr const &,Ofc::IWriterParams &)
0x180023902  cmp     qword ptr [rdi+20h], 0
0x180023907  jz      short loc_180023915
0x180023909  mov     edx, r15d
0x18002390c  mov     rcx, rbx
0x18002390f  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x180023915  mov     r9, rsi
0x180023918  lea     r8, [rdi+20h]
0x18002391c  mov     edx, r15d
0x18002391f  lea     rcx, aZIndex; "z-index"
0x180023926  call    ?Write@?$TAttrWriterHelper@IV?$TOptionalAdapter@I@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@I@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<uint,Ofc::TOptionalAdapter<uint>,0>::Write(wchar_t const *,int,Ofc::TOptional<uint> const &,Ofc::IWriterParams &)
0x18002392b  cmp     qword ptr [rdi+28h], 0
0x180023930  jz      short loc_18002393E
0x180023932  mov     edx, r15d
0x180023935  mov     rcx, rbx
0x180023938  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18002393e  mov     r9, rsi
0x180023941  lea     r8, [rdi+28h]
0x180023945  mov     edx, r15d
0x180023948  lea     rcx, aId; "id"
0x18002394f  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TOptionalAdapter@VCVarStr@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VCVarStr@Ofc@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::CVarStr> const &,Ofc::IWriterParams &)
0x180023954  mov     edx, r15d
0x180023957  mov     rcx, rbx
0x18002395a  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x180023960  mov     [rsp+68h+arg_10], r13
0x180023968  lea     r8, [rdi+30h]
0x18002396c  lea     rax, [rsp+68h+arg_10]
0x180023974  mov     [rsp+68h+var_48], rax
0x180023979  mov     r9, rsi
0x18002397c  mov     edx, r15d
0x18002397f  lea     rcx, aLayer; "layer"
0x180023986  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TSelfAdapter@VCVarStr@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBVCVarStr@2@AEAVIWriterParams@2@PEBV32@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(wchar_t const *,int,Ofc::CVarStr const &,Ofc::IWriterParams &,Ofc::CVarStr const *)
0x18002398b  cmp     qword ptr [rdi+38h], 0
0x180023990  jz      short loc_18002399E
0x180023992  mov     edx, r15d
0x180023995  mov     rcx, rbx
0x180023998  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18002399e  mov     r9, rsi
0x1800239a1  lea     r8, [rdi+38h]
0x1800239a5  mov     edx, r15d
0x1800239a8  lea     rcx, aStyleName; "style-name"
0x1800239af  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TOptionalAdapter@VCVarStr@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VCVarStr@Ofc@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::CVarStr> const &,Ofc::IWriterParams &)
0x1800239b4  cmp     qword ptr [rdi+40h], 0
0x1800239b9  jz      short loc_1800239C7
0x1800239bb  mov     edx, r15d
0x1800239be  mov     rcx, rbx
0x1800239c1  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800239c7  mov     r9, rsi
0x1800239ca  lea     r8, [rdi+40h]
0x1800239ce  mov     edx, r15d
0x1800239d1  lea     rcx, aClassNames; "class-names"
0x1800239d8  call    ?Write@?$TAttrWriterHelper@V?$TArray@VCVarStr@Ofc@@@Ofc@@V?$TOptionalAdapter@V?$TArray@VCVarStr@Ofc@@@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@V?$TArray@VCVarStr@Ofc@@@Ofc@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::TArray<Ofc::CVarStr>,Ofc::TOptionalAdapter<Ofc::TArray<Ofc::CVarStr>>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::TArray<Ofc::CVarStr>> const &,Ofc::IWriterParams &)
0x1800239dd  mov     r15d, 13Bh
0x1800239e3  cmp     qword ptr [rdi+48h], 0
0x1800239e8  jz      short loc_1800239F6
0x1800239ea  mov     edx, r15d
0x1800239ed  mov     rcx, rbx
0x1800239f0  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800239f6  mov     r9, rsi
0x1800239f9  lea     r8, [rdi+48h]
0x1800239fd  mov     edx, r15d
0x180023a00  lea     rcx, aStyleName; "style-name"
0x180023a07  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TOptionalAdapter@VCVarStr@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VCVarStr@Ofc@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::CVarStr> const &,Ofc::IWriterParams &)
0x180023a0c  cmp     qword ptr [rdi+50h], 0
0x180023a11  jz      short loc_180023A1F
0x180023a13  mov     edx, r15d
0x180023a16  mov     rcx, rbx
0x180023a19  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x180023a1f  mov     r9, rsi
0x180023a22  lea     r8, [rdi+50h]
0x180023a26  mov     edx, r15d
0x180023a29  lea     rcx, aClassNames; "class-names"
0x180023a30  call    ?Write@?$TAttrWriterHelper@V?$TArray@VCVarStr@Ofc@@@Ofc@@V?$TOptionalAdapter@V?$TArray@VCVarStr@Ofc@@@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@V?$TArray@VCVarStr@Ofc@@@Ofc@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::TArray<Ofc::CVarStr>,Ofc::TOptionalAdapter<Ofc::TArray<Ofc::CVarStr>>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::TArray<Ofc::CVarStr>> const &,Ofc::IWriterParams &)
0x180023a35  mov     ebp, 132h
0x180023a3a  mov     edx, ebp
0x180023a3c  mov     rcx, rbx
0x180023a3f  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x180023a45  mov     [rsp+68h+arg_18], r13
0x180023a4d  lea     r8, [rdi+58h]
0x180023a51  lea     rax, [rsp+68h+arg_18]
0x180023a59  mov     [rsp+68h+var_48], rax
0x180023a5e  mov     r9, rsi
0x180023a61  mov     edx, ebp
0x180023a63  lea     rcx, aTransform; "transform"
0x180023a6a  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TSelfAdapter@VCVarStr@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBVCVarStr@2@AEAVIWriterParams@2@PEBV32@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(wchar_t const *,int,Ofc::CVarStr const &,Ofc::IWriterParams &,Ofc::CVarStr const *)
0x180023a6f  mov     rax, [r14]
0x180023a72  mov     rdx, [rsi+10h]
0x180023a76  mov     rcx, r14
0x180023a79  mov     rax, [rax]
0x180023a7c  call    cs:__guard_dispatch_icall_fptr
0x180023a82  mov     rcx, r14
0x180023a85  call    cs:__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ; Ofc::CWriterEmit::EmitEndElement(void)
0x180023a8b  nop
0x180023a8c  add     rsp, 30h
0x180023a90  pop     r15
0x180023a92  pop     r14
0x180023a94  pop     r13
0x180023a96  pop     rdi
0x180023a97  pop     rsi
0x180023a98  pop     rbp
0x180023a99  pop     rbx
0x180023a9a  retn
```
