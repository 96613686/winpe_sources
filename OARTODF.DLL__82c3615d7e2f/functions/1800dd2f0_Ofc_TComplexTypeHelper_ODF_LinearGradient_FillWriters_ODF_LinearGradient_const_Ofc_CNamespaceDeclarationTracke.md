# Ofc::TComplexTypeHelper<ODF::LinearGradient>::FillWriters(ODF::LinearGradient const &,Ofc::CNamespaceDeclarationTracker &,Ofc::CWriterEmit &,Ofc::IWriterParams &)

- ea: `0x1800dd2f0`
- end: `0x1800dd570`
- name: `?FillWriters@?$TComplexTypeHelper@VLinearGradient@ODF@@@Ofc@@SAXAEBVLinearGradient@ODF@@AEAVCNamespaceDeclarationTracker@2@AEAVCWriterEmit@2@AEAVIWriterParams@2@@Z`
- size: `640`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180077d1c`

## callees

- `0x18001dcf4`
- `0x18001dd94`
- `0x1800d9ebc`
- `0x1800d9f10`
- `0x1800d9f64`
- `0x1800d9fb8`
- `0x1800dab00`
- `0x1800dd2f0`
- `0x1800de1c4`
- `0x1800de30c`
- `0x1800de454`
- `0x1800de59c`
- `0x1800deabc`
- `0x1800deb6c`
- `0x1801a80e0`

## import_xrefs

- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800dd321`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800dd349`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800dd37f`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800dd3a8`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800dd3cc`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800dd3fc`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800dd427`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800dd452`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800dd47d`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800dd321`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800dd349`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800dd37f`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800dd3a8`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800dd3cc`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800dd3fc`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800dd427`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800dd452`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800dd47d`
- `mso40uiWin32Client!__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ` at `0x1800dd4e2`
- `mso40uiWin32Client!__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ` at `0x1800dd4e2`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800dd569`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800dd569`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall Ofc::TComplexTypeHelper<ODF::LinearGradient>::FillWriters(
        __int64 a1,
        Ofc::CNamespaceDeclarationTracker *a2,
        Ofc::CWriterEmit *a3,
        __int64 a4)
{
  int v8; // edx
  int v9; // ecx
  int v10; // edx
  int v11; // ecx
  int v12; // edx
  int v13; // ecx
  int v14; // edx
  int v15; // ecx
  int v16; // edx
  int v17; // ecx
  int v18; // edx
  int v19; // ecx
  unsigned int v20; // ebx
  __int64 result; // rax
  _BYTE v22[8]; // [rsp+30h] [rbp-40h] BYREF
  __int64 v23; // [rsp+38h] [rbp-38h]
  _BYTE v24[8]; // [rsp+40h] [rbp-30h] BYREF
  __int64 v25; // [rsp+48h] [rbp-28h]
  _BYTE v26[8]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v27; // [rsp+58h] [rbp-18h]
  _BYTE v28[8]; // [rsp+60h] [rbp-10h] BYREF
  __int64 v29; // [rsp+68h] [rbp-8h]
  const wchar_t *v30; // [rsp+B0h] [rbp+40h] BYREF
  const wchar_t *v31; // [rsp+B8h] [rbp+48h] BYREF

  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 318);
  LODWORD(v30) = 0;
  Ofc::TAttrWriterHelper<enum ODF::GradientUnits,Ofc::TSelfAdapter<enum ODF::GradientUnits>,1>::Write(
    v9,
    v8,
    a1 + 24,
    a4,
    (__int64)&v30);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 318);
  v31 = &dword_1801DBD74;
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(
    (unsigned int)L"gradientTransform",
    318,
    a1 + 32,
    a4,
    (__int64)&v31);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 318);
  LODWORD(v30) = 0;
  Ofc::TAttrWriterHelper<enum ODF::SpreadMethod,Ofc::TSelfAdapter<enum ODF::SpreadMethod>,1>::Write(
    v11,
    v10,
    a1 + 40,
    a4,
    (__int64)&v30);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 307);
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(L"name", 307, a1 + 48, a4);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 307);
  v30 = &dword_1801DBD74;
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(
    (unsigned int)L"display-name",
    307,
    a1 + 56,
    a4,
    (__int64)&v30);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 318);
  Ofc::TVariant<ODF::LinearGradientData::SvgLinearGradientX1IDsImpl>::TVariant<ODF::LinearGradientData::SvgLinearGradientX1IDsImpl>(v28);
  Ofc::TAttrWriterHelper<Ofc::TVariant<ODF::LinearGradientData::SvgLinearGradientX1IDsImpl>,Ofc::TSelfAdapter<Ofc::TVariant<ODF::LinearGradientData::SvgLinearGradientX1IDsImpl>>,1>::Write(
    v13,
    v12,
    a1 + 64,
    a4,
    (__int64)v28);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 318);
  Ofc::TVariant<ODF::LinearGradientData::SvgLinearGradientY1IDsImpl>::TVariant<ODF::LinearGradientData::SvgLinearGradientY1IDsImpl>(v26);
  Ofc::TAttrWriterHelper<Ofc::TVariant<ODF::LinearGradientData::SvgLinearGradientY1IDsImpl>,Ofc::TSelfAdapter<Ofc::TVariant<ODF::LinearGradientData::SvgLinearGradientY1IDsImpl>>,1>::Write(
    v15,
    v14,
    a1 + 80,
    a4,
    (__int64)v26);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 318);
  Ofc::TVariant<ODF::LinearGradientData::SvgLinearGradientX2IDsImpl>::TVariant<ODF::LinearGradientData::SvgLinearGradientX2IDsImpl>(v24);
  Ofc::TAttrWriterHelper<Ofc::TVariant<ODF::LinearGradientData::SvgLinearGradientX2IDsImpl>,Ofc::TSelfAdapter<Ofc::TVariant<ODF::LinearGradientData::SvgLinearGradientX2IDsImpl>>,1>::Write(
    v17,
    v16,
    a1 + 96,
    a4,
    (__int64)v24);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 318);
  Ofc::TVariant<ODF::LinearGradientData::SvgLinearGradientY2IDsImpl>::TVariant<ODF::LinearGradientData::SvgLinearGradientY2IDsImpl>(v22);
  Ofc::TAttrWriterHelper<Ofc::TVariant<ODF::LinearGradientData::SvgLinearGradientY2IDsImpl>,Ofc::TSelfAdapter<Ofc::TVariant<ODF::LinearGradientData::SvgLinearGradientY2IDsImpl>>,1>::Write(
    v19,
    v18,
    a1 + 112,
    a4,
    (__int64)v22);
  (**(void (__fastcall ***)(Ofc::CWriterEmit *, _QWORD))a3)(a3, *(_QWORD *)(a4 + 16));
  if ( *(_DWORD *)(a1 + 16) )
  {
    v20 = 0;
    do
    {
      if ( v20 >= *(_DWORD *)(a1 + 16) )
      {
        CrashWithRecovery(0x1E892498u, 0);
        JUMPOUT(0x1800DD56FLL);
      }
      Ofc::TCompFillWritersHelper<ODF::Stop>(*(_QWORD *)(a1 + 8) + 32LL * v20++, a4);
    }
    while ( v20 < *(_DWORD *)(a1 + 16) );
  }
  Ofc::CWriterEmit::EmitEndElement(a3);
  if ( v23 )
    (*(void (__fastcall **)(_BYTE *))(v23 + 16))(v22);
  if ( v25 )
    (*(void (__fastcall **)(_BYTE *))(v25 + 16))(v24);
  if ( v27 )
    (*(void (__fastcall **)(_BYTE *))(v27 + 16))(v26);
  result = v29;
  if ( v29 )
    return (*(__int64 (__fastcall **)(_BYTE *))(v29 + 16))(v28);
  return result;
}

```

## disassembly

```asm
0x1800dd2f0  mov     [rsp-28h+arg_0], rbx
0x1800dd2f5  mov     [rsp-28h+arg_8], rsi
0x1800dd2fa  push    rbp
0x1800dd2fb  push    rdi
0x1800dd2fc  push    r12
0x1800dd2fe  push    r13
0x1800dd300  push    r14
0x1800dd302  mov     rbp, rsp
0x1800dd305  sub     rsp, 70h
0x1800dd309  mov     rsi, r9
0x1800dd30c  mov     r14, r8
0x1800dd30f  mov     rbx, rdx
0x1800dd312  mov     rdi, rcx
0x1800dd315  mov     r13d, 13Eh
0x1800dd31b  mov     edx, r13d
0x1800dd31e  mov     rcx, rbx
0x1800dd321  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800dd327  mov     dword ptr [rbp+arg_10], 0
0x1800dd32e  lea     r8, [rdi+18h]
0x1800dd332  lea     rax, [rbp+arg_10]
0x1800dd336  mov     [rsp+70h+var_50], rax
0x1800dd33b  mov     r9, rsi
0x1800dd33e  call    ?Write@?$TAttrWriterHelper@W4GradientUnits@ODF@@V?$TSelfAdapter@W4GradientUnits@ODF@@@Ofc@@$00@Ofc@@SAXPEB_WHAEBW4GradientUnits@ODF@@AEAVIWriterParams@2@PEBW434@@Z; Ofc::TAttrWriterHelper<ODF::GradientUnits,Ofc::TSelfAdapter<ODF::GradientUnits>,1>::Write(wchar_t const *,int,ODF::GradientUnits const &,Ofc::IWriterParams &,ODF::GradientUnits const *)
0x1800dd343  mov     edx, r13d
0x1800dd346  mov     rcx, rbx
0x1800dd349  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800dd34f  lea     r12, dword_1801DBD74
0x1800dd356  mov     [rbp+arg_18], r12
0x1800dd35a  lea     r8, [rdi+20h]
0x1800dd35e  lea     rax, [rbp+arg_18]
0x1800dd362  mov     [rsp+70h+var_50], rax
0x1800dd367  mov     r9, rsi
0x1800dd36a  mov     edx, r13d
0x1800dd36d  lea     rcx, aGradienttransf; "gradientTransform"
0x1800dd374  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TSelfAdapter@VCVarStr@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBVCVarStr@2@AEAVIWriterParams@2@PEBV32@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(wchar_t const *,int,Ofc::CVarStr const &,Ofc::IWriterParams &,Ofc::CVarStr const *)
0x1800dd379  mov     edx, r13d
0x1800dd37c  mov     rcx, rbx
0x1800dd37f  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800dd385  mov     dword ptr [rbp+arg_10], 0
0x1800dd38c  lea     r8, [rdi+28h]
0x1800dd390  lea     rax, [rbp+arg_10]
0x1800dd394  mov     [rsp+70h+var_50], rax
0x1800dd399  mov     r9, rsi
0x1800dd39c  call    ?Write@?$TAttrWriterHelper@W4SpreadMethod@ODF@@V?$TSelfAdapter@W4SpreadMethod@ODF@@@Ofc@@$00@Ofc@@SAXPEB_WHAEBW4SpreadMethod@ODF@@AEAVIWriterParams@2@PEBW434@@Z; Ofc::TAttrWriterHelper<ODF::SpreadMethod,Ofc::TSelfAdapter<ODF::SpreadMethod>,1>::Write(wchar_t const *,int,ODF::SpreadMethod const &,Ofc::IWriterParams &,ODF::SpreadMethod const *)
0x1800dd3a1  lea     edx, [r13-0Bh]
0x1800dd3a5  mov     rcx, rbx
0x1800dd3a8  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800dd3ae  lea     r8, [rdi+30h]
0x1800dd3b2  mov     r9, rsi
0x1800dd3b5  lea     edx, [r13-0Bh]
0x1800dd3b9  lea     rcx, aName; "name"
0x1800dd3c0  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TSelfAdapter@VCVarStr@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBVCVarStr@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(wchar_t const *,int,Ofc::CVarStr const &,Ofc::IWriterParams &)
0x1800dd3c5  lea     edx, [r13-0Bh]
0x1800dd3c9  mov     rcx, rbx
0x1800dd3cc  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800dd3d2  mov     [rbp+arg_10], r12
0x1800dd3d6  lea     r8, [rdi+38h]
0x1800dd3da  lea     rax, [rbp+arg_10]
0x1800dd3de  mov     [rsp+70h+var_50], rax
0x1800dd3e3  mov     r9, rsi
0x1800dd3e6  lea     edx, [r13-0Bh]
0x1800dd3ea  lea     rcx, aDisplayName; "display-name"
0x1800dd3f1  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TSelfAdapter@VCVarStr@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBVCVarStr@2@AEAVIWriterParams@2@PEBV32@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(wchar_t const *,int,Ofc::CVarStr const &,Ofc::IWriterParams &,Ofc::CVarStr const *)
0x1800dd3f6  mov     edx, r13d
0x1800dd3f9  mov     rcx, rbx
0x1800dd3fc  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800dd402  lea     rcx, [rbp+var_10]
0x1800dd406  call    ??$?0$$BY02_W@?$TVariant@VSvgLinearGradientX1IDsImpl@LinearGradientData@ODF@@@Ofc@@QEAA@AEAY02$$CB_W@Z; Ofc::TVariant<ODF::LinearGradientData::SvgLinearGradientX1IDsImpl>::TVariant<ODF::LinearGradientData::SvgLinearGradientX1IDsImpl>(wchar_t const (&)[3])
0x1800dd40b  nop
0x1800dd40c  lea     r8, [rdi+40h]
0x1800dd410  lea     rax, [rbp+var_10]
0x1800dd414  mov     [rsp+70h+var_50], rax
0x1800dd419  mov     r9, rsi
0x1800dd41c  call    ?Write@?$TAttrWriterHelper@V?$TVariant@VSvgLinearGradientX1IDsImpl@LinearGradientData@ODF@@@Ofc@@V?$TSelfAdapter@V?$TVariant@VSvgLinearGradientX1IDsImpl@LinearGradientData@ODF@@@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBV?$TVariant@VSvgLinearGradientX1IDsImpl@LinearGradientData@ODF@@@2@AEAVIWriterParams@2@PEBV32@@Z; Ofc::TAttrWriterHelper<Ofc::TVariant<ODF::LinearGradientData::SvgLinearGradientX1IDsImpl>,Ofc::TSelfAdapter<Ofc::TVariant<ODF::LinearGradientData::SvgLinearGradientX1IDsImpl>>,1>::Write(wchar_t const *,int,Ofc::TVariant<ODF::LinearGradientData::SvgLinearGradientX1IDsImpl> const &,Ofc::IWriterParams &,Ofc::TVariant<ODF::LinearGradientData::SvgLinearGradientX1IDsImpl> const *)
0x1800dd421  mov     edx, r13d
0x1800dd424  mov     rcx, rbx
0x1800dd427  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800dd42d  lea     rcx, [rbp+var_20]
0x1800dd431  call    ??$?0$$BY02_W@?$TVariant@VSvgLinearGradientY1IDsImpl@LinearGradientData@ODF@@@Ofc@@QEAA@AEAY02$$CB_W@Z; Ofc::TVariant<ODF::LinearGradientData::SvgLinearGradientY1IDsImpl>::TVariant<ODF::LinearGradientData::SvgLinearGradientY1IDsImpl>(wchar_t const (&)[3])
0x1800dd436  nop
0x1800dd437  lea     r8, [rdi+50h]
0x1800dd43b  lea     rax, [rbp+var_20]
0x1800dd43f  mov     [rsp+70h+var_50], rax
0x1800dd444  mov     r9, rsi
0x1800dd447  call    ?Write@?$TAttrWriterHelper@V?$TVariant@VSvgLinearGradientY1IDsImpl@LinearGradientData@ODF@@@Ofc@@V?$TSelfAdapter@V?$TVariant@VSvgLinearGradientY1IDsImpl@LinearGradientData@ODF@@@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBV?$TVariant@VSvgLinearGradientY1IDsImpl@LinearGradientData@ODF@@@2@AEAVIWriterParams@2@PEBV32@@Z; Ofc::TAttrWriterHelper<Ofc::TVariant<ODF::LinearGradientData::SvgLinearGradientY1IDsImpl>,Ofc::TSelfAdapter<Ofc::TVariant<ODF::LinearGradientData::SvgLinearGradientY1IDsImpl>>,1>::Write(wchar_t const *,int,Ofc::TVariant<ODF::LinearGradientData::SvgLinearGradientY1IDsImpl> const &,Ofc::IWriterParams &,Ofc::TVariant<ODF::LinearGradientData::SvgLinearGradientY1IDsImpl> const *)
0x1800dd44c  mov     edx, r13d
0x1800dd44f  mov     rcx, rbx
0x1800dd452  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800dd458  lea     rcx, [rbp+var_30]
0x1800dd45c  call    ??$?0$$BY04_W@?$TVariant@VSvgLinearGradientX2IDsImpl@LinearGradientData@ODF@@@Ofc@@QEAA@AEAY04$$CB_W@Z; Ofc::TVariant<ODF::LinearGradientData::SvgLinearGradientX2IDsImpl>::TVariant<ODF::LinearGradientData::SvgLinearGradientX2IDsImpl>(wchar_t const (&)[5])
0x1800dd461  nop
0x1800dd462  lea     r8, [rdi+60h]
0x1800dd466  lea     rax, [rbp+var_30]
0x1800dd46a  mov     [rsp+70h+var_50], rax
0x1800dd46f  mov     r9, rsi
0x1800dd472  call    ?Write@?$TAttrWriterHelper@V?$TVariant@VSvgLinearGradientX2IDsImpl@LinearGradientData@ODF@@@Ofc@@V?$TSelfAdapter@V?$TVariant@VSvgLinearGradientX2IDsImpl@LinearGradientData@ODF@@@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBV?$TVariant@VSvgLinearGradientX2IDsImpl@LinearGradientData@ODF@@@2@AEAVIWriterParams@2@PEBV32@@Z; Ofc::TAttrWriterHelper<Ofc::TVariant<ODF::LinearGradientData::SvgLinearGradientX2IDsImpl>,Ofc::TSelfAdapter<Ofc::TVariant<ODF::LinearGradientData::SvgLinearGradientX2IDsImpl>>,1>::Write(wchar_t const *,int,Ofc::TVariant<ODF::LinearGradientData::SvgLinearGradientX2IDsImpl> const &,Ofc::IWriterParams &,Ofc::TVariant<ODF::LinearGradientData::SvgLinearGradientX2IDsImpl> const *)
0x1800dd477  mov     edx, r13d
0x1800dd47a  mov     rcx, rbx
0x1800dd47d  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800dd483  lea     rcx, [rbp+var_40]
0x1800dd487  call    ??$?0$$BY04_W@?$TVariant@VSvgLinearGradientY2IDsImpl@LinearGradientData@ODF@@@Ofc@@QEAA@AEAY04$$CB_W@Z; Ofc::TVariant<ODF::LinearGradientData::SvgLinearGradientY2IDsImpl>::TVariant<ODF::LinearGradientData::SvgLinearGradientY2IDsImpl>(wchar_t const (&)[5])
0x1800dd48c  nop
0x1800dd48d  lea     r8, [rdi+70h]
0x1800dd491  lea     rax, [rbp+var_40]
0x1800dd495  mov     [rsp+70h+var_50], rax
0x1800dd49a  mov     r9, rsi
0x1800dd49d  call    ?Write@?$TAttrWriterHelper@V?$TVariant@VSvgLinearGradientY2IDsImpl@LinearGradientData@ODF@@@Ofc@@V?$TSelfAdapter@V?$TVariant@VSvgLinearGradientY2IDsImpl@LinearGradientData@ODF@@@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBV?$TVariant@VSvgLinearGradientY2IDsImpl@LinearGradientData@ODF@@@2@AEAVIWriterParams@2@PEBV32@@Z; Ofc::TAttrWriterHelper<Ofc::TVariant<ODF::LinearGradientData::SvgLinearGradientY2IDsImpl>,Ofc::TSelfAdapter<Ofc::TVariant<ODF::LinearGradientData::SvgLinearGradientY2IDsImpl>>,1>::Write(wchar_t const *,int,Ofc::TVariant<ODF::LinearGradientData::SvgLinearGradientY2IDsImpl> const &,Ofc::IWriterParams &,Ofc::TVariant<ODF::LinearGradientData::SvgLinearGradientY2IDsImpl> const *)
0x1800dd4a2  mov     rax, [r14]
0x1800dd4a5  mov     rdx, [rsi+10h]
0x1800dd4a9  mov     rcx, r14
0x1800dd4ac  mov     rax, [rax]
0x1800dd4af  call    cs:__guard_dispatch_icall_fptr
0x1800dd4b5  cmp     dword ptr [rdi+10h], 0
0x1800dd4b9  jbe     short loc_1800DD4DF
0x1800dd4bb  xor     ebx, ebx
0x1800dd4bd  cmp     ebx, [rdi+10h]
0x1800dd4c0  jnb     loc_1800DD562
0x1800dd4c6  mov     ecx, ebx
0x1800dd4c8  shl     rcx, 5
0x1800dd4cc  add     rcx, [rdi+8]
0x1800dd4d0  mov     rdx, rsi
0x1800dd4d3  call    ??$TCompFillWritersHelper@VStop@ODF@@@Ofc@@YAXAEBVStop@ODF@@AEAVIWriterParams@0@HPEB_W@Z; Ofc::TCompFillWritersHelper<ODF::Stop>(ODF::Stop const &,Ofc::IWriterParams &,int,wchar_t const *)
0x1800dd4d8  inc     ebx
0x1800dd4da  cmp     ebx, [rdi+10h]
0x1800dd4dd  jb      short loc_1800DD4BD
0x1800dd4df  mov     rcx, r14
0x1800dd4e2  call    cs:__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ; Ofc::CWriterEmit::EmitEndElement(void)
0x1800dd4e8  nop
0x1800dd4e9  mov     rax, [rbp+var_38]
0x1800dd4ed  test    rax, rax
0x1800dd4f0  jz      short loc_1800DD501
0x1800dd4f2  lea     rcx, [rbp+var_40]
0x1800dd4f6  mov     rax, [rax+10h]
0x1800dd4fa  call    cs:__guard_dispatch_icall_fptr
0x1800dd500  nop
0x1800dd501  mov     rax, [rbp+var_28]
0x1800dd505  test    rax, rax
0x1800dd508  jz      short loc_1800DD519
0x1800dd50a  lea     rcx, [rbp+var_30]
0x1800dd50e  mov     rax, [rax+10h]
0x1800dd512  call    cs:__guard_dispatch_icall_fptr
0x1800dd518  nop
0x1800dd519  mov     rax, [rbp+var_18]
0x1800dd51d  test    rax, rax
0x1800dd520  jz      short loc_1800DD531
0x1800dd522  lea     rcx, [rbp+var_20]
0x1800dd526  mov     rax, [rax+10h]
0x1800dd52a  call    cs:__guard_dispatch_icall_fptr
0x1800dd530  nop
0x1800dd531  mov     rax, [rbp+var_8]
0x1800dd535  test    rax, rax
0x1800dd538  jz      short loc_1800DD549
0x1800dd53a  lea     rcx, [rbp+var_10]
0x1800dd53e  mov     rax, [rax+10h]
0x1800dd542  call    cs:__guard_dispatch_icall_fptr
0x1800dd548  nop
0x1800dd549  lea     r11, [rsp+70h+var_s0]
0x1800dd54e  mov     rbx, [r11+30h]
0x1800dd552  mov     rsi, [r11+38h]
0x1800dd556  mov     rsp, r11
0x1800dd559  pop     r14
0x1800dd55b  pop     r13
0x1800dd55d  pop     r12
0x1800dd55f  pop     rdi
0x1800dd560  pop     rbp
0x1800dd561  retn
0x1800dd562  xor     edx, edx
0x1800dd564  mov     ecx, 1E892498h
0x1800dd569  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
