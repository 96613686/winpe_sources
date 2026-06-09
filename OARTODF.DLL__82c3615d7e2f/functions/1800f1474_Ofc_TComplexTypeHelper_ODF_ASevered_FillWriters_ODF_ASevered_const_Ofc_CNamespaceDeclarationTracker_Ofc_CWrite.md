# Ofc::TComplexTypeHelper<ODF::ASevered>::FillWriters(ODF::ASevered const &,Ofc::CNamespaceDeclarationTracker &,Ofc::CWriterEmit &,Ofc::IWriterParams &)

- ea: `0x1800f1474`
- end: `0x1800f169a`
- name: `?FillWriters@?$TComplexTypeHelper@VASevered@ODF@@@Ofc@@SAXAEBVASevered@ODF@@AEAVCNamespaceDeclarationTracker@2@AEAVCWriterEmit@2@AEAVIWriterParams@2@@Z`
- size: `550`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800f4100`

## callees

- `0x18001dcf4`
- `0x18001dd94`
- `0x18002e1f0`
- `0x18002e670`
- `0x18002e70c`
- `0x18002e844`
- `0x180054fc4`
- `0x1800f0ac4`
- `0x1800f1474`
- `0x1801a80e0`

## import_xrefs

- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800f14a3`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800f14d9`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800f150c`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800f152e`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800f155a`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800f157a`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800f1598`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800f15b6`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800f15d8`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800f14a3`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800f14d9`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800f150c`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800f152e`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800f155a`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800f157a`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800f1598`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800f15b6`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800f15d8`
- `mso40uiWin32Client!__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ` at `0x1800f166d`
- `mso40uiWin32Client!__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ` at `0x1800f166d`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800f1693`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800f1693`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Ofc::TComplexTypeHelper<ODF::ASevered>::FillWriters(
        __int64 a1,
        Ofc::CNamespaceDeclarationTracker *a2,
        Ofc::CWriterEmit *a3,
        __int64 a4)
{
  unsigned int v8; // ebx
  int v9; // edx
  int v10; // ecx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rcx
  unsigned int v19; // eax
  __int64 v20; // rcx
  _QWORD v21[5]; // [rsp+30h] [rbp-30h] BYREF
  int v22; // [rsp+58h] [rbp-8h]
  int v23; // [rsp+A0h] [rbp+40h] BYREF
  const wchar_t *v24; // [rsp+B0h] [rbp+50h] BYREF
  const wchar_t *v25; // [rsp+B8h] [rbp+58h] BYREF

  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 300);
  v24 = &dword_1801DBD74;
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(
    (unsigned int)L"name",
    300,
    a1 + 32,
    a4,
    (__int64)&v24);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 300);
  v25 = &dword_1801DBD74;
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(
    (unsigned int)L"title",
    300,
    a1 + 40,
    a4,
    (__int64)&v25);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 323);
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(L"href", 323, a1 + 48, a4);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 323);
  v8 = 0;
  v23 = 0;
  Ofc::TAttrWriterHelper<enum ODF::XlinkType,Ofc::TSelfAdapter<enum ODF::XlinkType>,1>::Write(
    v10,
    v9,
    a1 + 56,
    a4,
    (__int64)&v23);
  if ( *(_QWORD *)(a1 + 64) )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 323);
  Ofc::TAttrWriterHelper<enum ODF::XlinkActuate,Ofc::TOptionalAdapter<enum ODF::XlinkActuate>,0>::Write(
    v12,
    v11,
    a1 + 64,
    a4);
  if ( *(_QWORD *)(a1 + 72) )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 300);
  Ofc::TAttrWriterHelper<Ofc::TVariant<ODF::TargetFrameNameIDsImpl>,Ofc::TOptionalAdapter<Ofc::TVariant<ODF::TargetFrameNameIDsImpl>>,0>::Write(
    v14,
    v13,
    a1 + 72,
    a4);
  if ( *(_QWORD *)(a1 + 80) )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 323);
  Ofc::TAttrWriterHelper<enum ODF::XlinkShow1Show,Ofc::TOptionalAdapter<enum ODF::XlinkShow1Show>,0>::Write(
    v16,
    v15,
    a1 + 80,
    a4);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 321);
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(L"style-name", 321, a1 + 88, a4);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 321);
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(L"visited-style-name", 321, a1 + 96, a4);
  (**(void (__fastcall ***)(Ofc::CWriterEmit *, _QWORD))a3)(a3, *(_QWORD *)(a4 + 16));
  Ofc::TCompElemWriterHelper<ODF::EventListeners,Ofc::TOptionalAdapter<ODF::EventListeners>,0>::Write(v18, v17, a1, a4);
  v19 = *(_DWORD *)(a1 + 24);
  if ( v19 )
  {
    do
    {
      if ( v8 >= v19 )
      {
        CrashWithRecovery(0x1E892498u, 0);
        JUMPOUT(0x1800F1699LL);
      }
      v20 = *(_QWORD *)(a1 + 16) + 16LL * v8;
      v21[0] = &Ofc::TChoiceWriterVisitor<ODF::ParaContent_<0>,ODF::ParaContentWriterTList>::`vftable';
      v21[1] = v20;
      v21[2] = a4;
      v21[3] = &off_180208930;
      v21[4] = qword_180208828;
      v22 = 13;
      Ofc::TChoice<ODF::ParaContentChoiceIDsImpl>::Accept(v20, v21);
      ++v8;
      v19 = *(_DWORD *)(a1 + 24);
    }
    while ( v8 < v19 );
  }
  Ofc::CWriterEmit::EmitEndElement(a3);
}

```

## disassembly

```asm
0x1800f1474  mov     [rsp-38h+arg_8], rbx
0x1800f1479  push    rbp
0x1800f147a  push    rsi
0x1800f147b  push    rdi
0x1800f147c  push    r12
0x1800f147e  push    r13
0x1800f1480  push    r14
0x1800f1482  push    r15
0x1800f1484  mov     rbp, rsp
0x1800f1487  sub     rsp, 60h
0x1800f148b  mov     rsi, r9
0x1800f148e  mov     r12, r8
0x1800f1491  mov     r14, rdx
0x1800f1494  mov     rdi, rcx
0x1800f1497  mov     r15d, 12Ch
0x1800f149d  mov     edx, r15d
0x1800f14a0  mov     rcx, r14
0x1800f14a3  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800f14a9  lea     rbx, dword_1801DBD74
0x1800f14b0  mov     [rbp+arg_10], rbx
0x1800f14b4  lea     r8, [rdi+20h]
0x1800f14b8  lea     rax, [rbp+arg_10]
0x1800f14bc  mov     [rsp+60h+var_40], rax
0x1800f14c1  mov     r9, rsi
0x1800f14c4  mov     edx, r15d
0x1800f14c7  lea     rcx, aName; "name"
0x1800f14ce  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TSelfAdapter@VCVarStr@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBVCVarStr@2@AEAVIWriterParams@2@PEBV32@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(wchar_t const *,int,Ofc::CVarStr const &,Ofc::IWriterParams &,Ofc::CVarStr const *)
0x1800f14d3  mov     edx, r15d
0x1800f14d6  mov     rcx, r14
0x1800f14d9  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800f14df  mov     [rbp+arg_18], rbx
0x1800f14e3  lea     r8, [rdi+28h]
0x1800f14e7  lea     rax, [rbp+arg_18]
0x1800f14eb  mov     [rsp+60h+var_40], rax
0x1800f14f0  mov     r9, rsi
0x1800f14f3  mov     edx, r15d
0x1800f14f6  lea     rcx, aTitle; "title"
0x1800f14fd  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TSelfAdapter@VCVarStr@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBVCVarStr@2@AEAVIWriterParams@2@PEBV32@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(wchar_t const *,int,Ofc::CVarStr const &,Ofc::IWriterParams &,Ofc::CVarStr const *)
0x1800f1502  lea     r13d, [r15+17h]
0x1800f1506  mov     edx, r13d
0x1800f1509  mov     rcx, r14
0x1800f150c  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800f1512  lea     r8, [rdi+30h]
0x1800f1516  mov     r9, rsi
0x1800f1519  mov     edx, r13d
0x1800f151c  lea     rcx, aHref; "href"
0x1800f1523  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TSelfAdapter@VCVarStr@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBVCVarStr@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(wchar_t const *,int,Ofc::CVarStr const &,Ofc::IWriterParams &)
0x1800f1528  mov     edx, r13d
0x1800f152b  mov     rcx, r14
0x1800f152e  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800f1534  xor     ebx, ebx
0x1800f1536  mov     [rbp+arg_0], ebx
0x1800f1539  lea     r8, [rdi+38h]
0x1800f153d  lea     rax, [rbp+arg_0]
0x1800f1541  mov     [rsp+60h+var_40], rax
0x1800f1546  mov     r9, rsi
0x1800f1549  call    ?Write@?$TAttrWriterHelper@W4XlinkType@ODF@@V?$TSelfAdapter@W4XlinkType@ODF@@@Ofc@@$00@Ofc@@SAXPEB_WHAEBW4XlinkType@ODF@@AEAVIWriterParams@2@PEBW434@@Z; Ofc::TAttrWriterHelper<ODF::XlinkType,Ofc::TSelfAdapter<ODF::XlinkType>,1>::Write(wchar_t const *,int,ODF::XlinkType const &,Ofc::IWriterParams &,ODF::XlinkType const *)
0x1800f154e  cmp     [rdi+40h], rbx
0x1800f1552  jz      short loc_1800F1560
0x1800f1554  mov     edx, r13d
0x1800f1557  mov     rcx, r14
0x1800f155a  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800f1560  mov     r9, rsi
0x1800f1563  lea     r8, [rdi+40h]
0x1800f1567  call    ?Write@?$TAttrWriterHelper@W4XlinkActuate@ODF@@V?$TOptionalAdapter@W4XlinkActuate@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@W4XlinkActuate@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::XlinkActuate,Ofc::TOptionalAdapter<ODF::XlinkActuate>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::XlinkActuate> const &,Ofc::IWriterParams &)
0x1800f156c  cmp     [rdi+48h], rbx
0x1800f1570  jz      short loc_1800F1580
0x1800f1572  mov     edx, 12Ch
0x1800f1577  mov     rcx, r14
0x1800f157a  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800f1580  mov     r9, rsi
0x1800f1583  lea     r8, [rdi+48h]
0x1800f1587  call    ?Write@?$TAttrWriterHelper@V?$TVariant@VTargetFrameNameIDsImpl@ODF@@@Ofc@@V?$TOptionalAdapter@V?$TVariant@VTargetFrameNameIDsImpl@ODF@@@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@V?$TVariant@VTargetFrameNameIDsImpl@ODF@@@Ofc@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::TVariant<ODF::TargetFrameNameIDsImpl>,Ofc::TOptionalAdapter<Ofc::TVariant<ODF::TargetFrameNameIDsImpl>>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::TVariant<ODF::TargetFrameNameIDsImpl>> const &,Ofc::IWriterParams &)
0x1800f158c  cmp     [rdi+50h], rbx
0x1800f1590  jz      short loc_1800F159E
0x1800f1592  mov     edx, r13d
0x1800f1595  mov     rcx, r14
0x1800f1598  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800f159e  mov     r9, rsi
0x1800f15a1  lea     r8, [rdi+50h]
0x1800f15a5  call    ?Write@?$TAttrWriterHelper@W4XlinkShow1Show@ODF@@V?$TOptionalAdapter@W4XlinkShow1Show@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@W4XlinkShow1Show@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::XlinkShow1Show,Ofc::TOptionalAdapter<ODF::XlinkShow1Show>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::XlinkShow1Show> const &,Ofc::IWriterParams &)
0x1800f15aa  mov     r15d, 141h
0x1800f15b0  mov     edx, r15d
0x1800f15b3  mov     rcx, r14
0x1800f15b6  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800f15bc  lea     r8, [rdi+58h]
0x1800f15c0  mov     r9, rsi
0x1800f15c3  mov     edx, r15d
0x1800f15c6  lea     rcx, aStyleName; "style-name"
0x1800f15cd  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TSelfAdapter@VCVarStr@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBVCVarStr@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(wchar_t const *,int,Ofc::CVarStr const &,Ofc::IWriterParams &)
0x1800f15d2  mov     edx, r15d
0x1800f15d5  mov     rcx, r14
0x1800f15d8  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800f15de  lea     r8, [rdi+60h]
0x1800f15e2  mov     r9, rsi
0x1800f15e5  mov     edx, r15d
0x1800f15e8  lea     rcx, aVisitedStyleNa; "visited-style-name"
0x1800f15ef  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TSelfAdapter@VCVarStr@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBVCVarStr@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(wchar_t const *,int,Ofc::CVarStr const &,Ofc::IWriterParams &)
0x1800f15f4  mov     rax, [r12]
0x1800f15f8  mov     rdx, [rsi+10h]
0x1800f15fc  mov     rcx, r12
0x1800f15ff  mov     rax, [rax]
0x1800f1602  call    cs:__guard_dispatch_icall_fptr
0x1800f1608  mov     r9, rsi
0x1800f160b  mov     r8, rdi
0x1800f160e  call    ?Write@?$TCompElemWriterHelper@VEventListeners@ODF@@V?$TOptionalAdapter@VEventListeners@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VEventListeners@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TCompElemWriterHelper<ODF::EventListeners,Ofc::TOptionalAdapter<ODF::EventListeners>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::EventListeners> const &,Ofc::IWriterParams &)
0x1800f1613  mov     eax, [rdi+18h]
0x1800f1616  test    eax, eax
0x1800f1618  jz      short loc_1800F166A
0x1800f161a  cmp     ebx, eax
0x1800f161c  jnb     short loc_1800F168C
0x1800f161e  mov     ecx, ebx
0x1800f1620  shl     rcx, 4
0x1800f1624  add     rcx, [rdi+10h]
0x1800f1628  lea     rax, ??_7?$TChoiceWriterVisitor@V?$ParaContent_@$0A@@ODF@@VParaContentWriterTList@2@@Ofc@@6B@; const Ofc::TChoiceWriterVisitor<ODF::ParaContent_<0>,ODF::ParaContentWriterTList>::`vftable'
0x1800f162f  mov     [rbp+var_30], rax
0x1800f1633  mov     [rbp+var_28], rcx
0x1800f1637  mov     [rbp+var_20], rsi
0x1800f163b  lea     rax, off_180208930
0x1800f1642  mov     [rbp+var_18], rax
0x1800f1646  lea     rax, qword_180208828
0x1800f164d  mov     [rbp+var_10], rax
0x1800f1651  mov     [rbp+var_8], 0Dh
0x1800f1658  lea     rdx, [rbp+var_30]
0x1800f165c  call    ?Accept@?$TChoice@VParaContentChoiceIDsImpl@ODF@@@Ofc@@QEBAXAEAVParaContentChoiceIDsCSCV@ODF@@@Z; Ofc::TChoice<ODF::ParaContentChoiceIDsImpl>::Accept(ODF::ParaContentChoiceIDsCSCV &)
0x1800f1661  inc     ebx
0x1800f1663  mov     eax, [rdi+18h]
0x1800f1666  cmp     ebx, eax
0x1800f1668  jb      short loc_1800F161A
0x1800f166a  mov     rcx, r12
0x1800f166d  call    cs:__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ; Ofc::CWriterEmit::EmitEndElement(void)
0x1800f1673  nop
0x1800f1674  mov     rbx, [rsp+60h+arg_8]
0x1800f167c  add     rsp, 60h
0x1800f1680  pop     r15
0x1800f1682  pop     r14
0x1800f1684  pop     r13
0x1800f1686  pop     r12
0x1800f1688  pop     rdi
0x1800f1689  pop     rsi
0x1800f168a  pop     rbp
0x1800f168b  retn
0x1800f168c  xor     edx, edx
0x1800f168e  mov     ecx, 1E892498h
0x1800f1693  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
