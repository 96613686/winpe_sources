# Ofc::TComplexTypeHelper<ODF::PresentationEventListener>::FillWriters(ODF::PresentationEventListener const &,Ofc::CNamespaceDeclarationTracker &,Ofc::CWriterEmit &,Ofc::IWriterParams &)

- ea: `0x180086100`
- end: `0x180086389`
- name: `?FillWriters@?$TComplexTypeHelper@VPresentationEventListener@ODF@@@Ofc@@SAXAEBVPresentationEventListener@ODF@@AEAVCNamespaceDeclarationTracker@2@AEAVCWriterEmit@2@AEAVIWriterParams@2@@Z`
- size: `649`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180070460`

## callees

- `0x18001db8c`
- `0x18001dd94`
- `0x180025c28`
- `0x18002e670`
- `0x18002e7a8`
- `0x180054b20`
- `0x180054f28`
- `0x180086100`
- `0x1800865f4`
- `0x1800866e4`
- `0x180086794`
- `0x180086844`
- `0x1800868f4`
- `0x1800f7950`
- `0x1801a80e0`

## import_xrefs

- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18008612a`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18008616b`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800861d8`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180086205`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180086232`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180086262`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800862ab`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800862d3`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800862f1`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18008630f`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18008632d`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18008612a`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18008616b`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800861d8`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180086205`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180086232`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x180086262`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800862ab`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800862d3`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800862f1`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18008630f`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18008632d`
- `mso40uiWin32Client!__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ` at `0x18008636a`
- `mso40uiWin32Client!__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ` at `0x18008636a`
- `mso40uiWin32Client!__imp_?WriteAttrHelper@Ofc@@YAXPEB_WHAEAVIWriterParams@1@AEBV?$TFixedVarStr@$0ICF@@1@@Z` at `0x1800861cc`
- `mso40uiWin32Client!__imp_?WriteAttrHelper@Ofc@@YAXPEB_WHAEAVIWriterParams@1@AEBV?$TFixedVarStr@$0ICF@@1@@Z` at `0x1800861cc`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18008619b`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18008619b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Ofc::TComplexTypeHelper<ODF::PresentationEventListener>::FillWriters(
        _QWORD *a1,
        Ofc::CNamespaceDeclarationTracker *a2,
        Ofc::CWriterEmit *a3,
        __int64 a4)
{
  void *v8; // rdx
  Mso::Memory *v9; // rcx
  int v10; // edx
  int v11; // ecx
  int v12; // edx
  int v13; // ecx
  int v14; // edx
  int v15; // ecx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rcx
  _BYTE v24[72]; // [rsp+30h] [rbp-48h] BYREF
  int v25; // [rsp+80h] [rbp+8h] BYREF
  const wchar_t *v26; // [rsp+90h] [rbp+18h] BYREF

  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 316);
  v26 = &dword_1801DBD74;
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(
    (unsigned int)L"event-name",
    316,
    (_DWORD)a1 + 8,
    a4,
    (__int64)&v26);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 315);
  v9 = (Mso::Memory *)(*(_QWORD *)(a4 + 32) - 12LL);
  if ( *((_DWORD *)v9 + 1)
    && (*(_DWORD *)v9 == 1 || _InterlockedExchangeAdd((volatile signed __int32 *)v9, 0xFFFFFFFF) == 1)
    && v9 )
  {
    Mso::Memory::Free(v9, v8);
  }
  *(_QWORD *)(a4 + 32) = &dword_1801DBD74;
  *(_DWORD *)(a4 + 56) = 0;
  *(_WORD *)(a4 + 60) = 0;
  Ofc::TSimpleTypeHelper<enum ODF::Action>::ToString(a1 + 2, a4, a4 + 32);
  Ofc::WriteAttrHelper(L"action", 315, a4, a4 + 32);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 315);
  v25 = 0;
  Ofc::TAttrWriterHelper<enum ODF::PresentationEffects,Ofc::TSelfAdapter<enum ODF::PresentationEffects>,1>::Write(
    v11,
    v10,
    (_DWORD)a1 + 20,
    a4,
    (__int64)&v25);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 315);
  v25 = 0;
  Ofc::TAttrWriterHelper<enum ODF::PresentationEffectDirections,Ofc::TSelfAdapter<enum ODF::PresentationEffectDirections>,1>::Write(
    v13,
    v12,
    (_DWORD)a1 + 24,
    a4,
    (__int64)&v25);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 315);
  v25 = 1;
  Ofc::TAttrWriterHelper<enum ODF::PresentationSpeeds,Ofc::TSelfAdapter<enum ODF::PresentationSpeeds>,1>::Write(
    v15,
    v14,
    (_DWORD)a1 + 28,
    a4,
    (__int64)&v25);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 315);
  ODF::Percent::Percent((ODF::Percent *)v24, L"100%");
  Ofc::TAttrWriterHelper<ODF::Percent,Ofc::TSelfAdapter<ODF::Percent>,1>::Write(
    (unsigned int)L"start-scale",
    315,
    (_DWORD)a1 + 32,
    a4,
    (__int64)v24);
  if ( a1[6] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 323);
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(L"href", 323, a1 + 6, a4);
  if ( a1[7] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 323);
  Ofc::TAttrWriterHelper<enum ODF::XlinkType,Ofc::TOptionalAdapter<enum ODF::XlinkType>,0>::Write(v17, v16, a1 + 7, a4);
  if ( a1[8] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 323);
  Ofc::TAttrWriterHelper<enum ODF::XlinkShow,Ofc::TOptionalAdapter<enum ODF::XlinkShow>,0>::Write(v19, v18, a1 + 8, a4);
  if ( a1[9] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 323);
  Ofc::TAttrWriterHelper<enum ODF::XlinkActuate,Ofc::TOptionalAdapter<enum ODF::XlinkActuate>,0>::Write(
    v21,
    v20,
    a1 + 9,
    a4);
  if ( a1[10] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 315);
  Ofc::TAttrWriterHelper<unsigned int,Ofc::TOptionalAdapter<unsigned int>,0>::Write(L"verb", 315, a1 + 10, a4);
  (**(void (__fastcall ***)(Ofc::CWriterEmit *, _QWORD))a3)(a3, *(_QWORD *)(a4 + 16));
  Ofc::TCompElemWriterHelper<ODF::Sound,Ofc::TOptionalAdapter<ODF::Sound>,0>::Write(v23, v22, a1, a4);
  Ofc::CWriterEmit::EmitEndElement(a3);
}

```

## disassembly

```asm
0x180086100  mov     [rsp+arg_8], rbx
0x180086105  push    rbp
0x180086106  push    rsi
0x180086107  push    rdi
0x180086108  push    r12
0x18008610a  push    r13
0x18008610c  push    r14
0x18008610e  push    r15
0x180086110  sub     rsp, 40h
0x180086114  mov     rdi, r9
0x180086117  mov     r14, r8
0x18008611a  mov     rsi, rdx
0x18008611d  mov     rbp, rcx
0x180086120  mov     ebx, 13Ch
0x180086125  mov     edx, ebx
0x180086127  mov     rcx, rsi
0x18008612a  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x180086130  lea     r12, dword_1801DBD74
0x180086137  mov     [rsp+78h+arg_10], r12
0x18008613f  lea     r8, [rbp+8]
0x180086143  lea     rax, [rsp+78h+arg_10]
0x18008614b  mov     [rsp+78h+var_58], rax
0x180086150  mov     r9, rdi
0x180086153  mov     edx, ebx
0x180086155  lea     rcx, aEventName; "event-name"
0x18008615c  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TSelfAdapter@VCVarStr@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBVCVarStr@2@AEAVIWriterParams@2@PEBV32@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(wchar_t const *,int,Ofc::CVarStr const &,Ofc::IWriterParams &,Ofc::CVarStr const *)
0x180086161  lea     r13d, [rbx-1]
0x180086165  mov     edx, r13d
0x180086168  mov     rcx, rsi
0x18008616b  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x180086171  lea     rbx, [rdi+20h]
0x180086175  mov     rcx, [rbx]
0x180086178  sub     rcx, 0Ch
0x18008617c  xor     r15d, r15d
0x18008617f  cmp     [rcx+4], r15d
0x180086183  jz      short loc_1800861A1
0x180086185  cmp     dword ptr [rcx], 1
0x180086188  jz      short loc_180086196
0x18008618a  or      eax, 0FFFFFFFFh
0x18008618d  lock xadd [rcx], eax
0x180086191  cmp     eax, 1
0x180086194  jnz     short loc_1800861A1
0x180086196  test    rcx, rcx
0x180086199  jz      short loc_1800861A1
0x18008619b  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1800861a1  mov     [rbx], r12
0x1800861a4  mov     [rbx+18h], r15d
0x1800861a8  mov     [rbx+1Ch], r15w
0x1800861ad  lea     rcx, [rbp+10h]
0x1800861b1  mov     r8, rbx
0x1800861b4  mov     rdx, rdi
0x1800861b7  call    ?ToString@?$TSimpleTypeHelper@W4Action@ODF@@@Ofc@@SAXAEBW4Action@ODF@@PEAVIWriterParams@2@AEAV?$TFixedVarStr@$0ICF@@2@@Z; Ofc::TSimpleTypeHelper<ODF::Action>::ToString(ODF::Action const &,Ofc::IWriterParams *,Ofc::TFixedVarStr<2085> &)
0x1800861bc  mov     r9, rbx
0x1800861bf  mov     r8, rdi
0x1800861c2  mov     edx, r13d
0x1800861c5  lea     rcx, aAction; "action"
0x1800861cc  call    cs:__imp_?WriteAttrHelper@Ofc@@YAXPEB_WHAEAVIWriterParams@1@AEBV?$TFixedVarStr@$0ICF@@1@@Z; Ofc::WriteAttrHelper(wchar_t const *,int,Ofc::IWriterParams &,Ofc::TFixedVarStr<2085> const &)
0x1800861d2  mov     edx, r13d
0x1800861d5  mov     rcx, rsi
0x1800861d8  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800861de  mov     [rsp+78h+arg_0], r15d
0x1800861e6  lea     r8, [rbp+14h]
0x1800861ea  lea     rax, [rsp+78h+arg_0]
0x1800861f2  mov     [rsp+78h+var_58], rax
0x1800861f7  mov     r9, rdi
0x1800861fa  call    ?Write@?$TAttrWriterHelper@W4PresentationEffects@ODF@@V?$TSelfAdapter@W4PresentationEffects@ODF@@@Ofc@@$00@Ofc@@SAXPEB_WHAEBW4PresentationEffects@ODF@@AEAVIWriterParams@2@PEBW434@@Z; Ofc::TAttrWriterHelper<ODF::PresentationEffects,Ofc::TSelfAdapter<ODF::PresentationEffects>,1>::Write(wchar_t const *,int,ODF::PresentationEffects const &,Ofc::IWriterParams &,ODF::PresentationEffects const *)
0x1800861ff  mov     edx, r13d
0x180086202  mov     rcx, rsi
0x180086205  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18008620b  mov     [rsp+78h+arg_0], r15d
0x180086213  lea     r8, [rbp+18h]
0x180086217  lea     rax, [rsp+78h+arg_0]
0x18008621f  mov     [rsp+78h+var_58], rax
0x180086224  mov     r9, rdi
0x180086227  call    ?Write@?$TAttrWriterHelper@W4PresentationEffectDirections@ODF@@V?$TSelfAdapter@W4PresentationEffectDirections@ODF@@@Ofc@@$00@Ofc@@SAXPEB_WHAEBW4PresentationEffectDirections@ODF@@AEAVIWriterParams@2@PEBW434@@Z; Ofc::TAttrWriterHelper<ODF::PresentationEffectDirections,Ofc::TSelfAdapter<ODF::PresentationEffectDirections>,1>::Write(wchar_t const *,int,ODF::PresentationEffectDirections const &,Ofc::IWriterParams &,ODF::PresentationEffectDirections const *)
0x18008622c  mov     edx, r13d
0x18008622f  mov     rcx, rsi
0x180086232  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x180086238  mov     [rsp+78h+arg_0], 1
0x180086243  lea     r8, [rbp+1Ch]
0x180086247  lea     rax, [rsp+78h+arg_0]
0x18008624f  mov     [rsp+78h+var_58], rax
0x180086254  mov     r9, rdi
0x180086257  call    ?Write@?$TAttrWriterHelper@W4PresentationSpeeds@ODF@@V?$TSelfAdapter@W4PresentationSpeeds@ODF@@@Ofc@@$00@Ofc@@SAXPEB_WHAEBW4PresentationSpeeds@ODF@@AEAVIWriterParams@2@PEBW434@@Z; Ofc::TAttrWriterHelper<ODF::PresentationSpeeds,Ofc::TSelfAdapter<ODF::PresentationSpeeds>,1>::Write(wchar_t const *,int,ODF::PresentationSpeeds const &,Ofc::IWriterParams &,ODF::PresentationSpeeds const *)
0x18008625c  mov     edx, r13d
0x18008625f  mov     rcx, rsi
0x180086262  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x180086268  lea     rdx, a100; "100%"
0x18008626f  lea     rcx, [rsp+78h+var_48]; this
0x180086274  call    ??0Percent@ODF@@QEAA@PEB_W@Z; ODF::Percent::Percent(wchar_t const *)
0x180086279  lea     r8, [rbp+20h]
0x18008627d  lea     rax, [rsp+78h+var_48]
0x180086282  mov     [rsp+78h+var_58], rax
0x180086287  mov     r9, rdi
0x18008628a  mov     edx, r13d
0x18008628d  lea     rcx, aStartScale; "start-scale"
0x180086294  call    ?Write@?$TAttrWriterHelper@VPercent@ODF@@V?$TSelfAdapter@VPercent@ODF@@@Ofc@@$00@Ofc@@SAXPEB_WHAEBVPercent@ODF@@AEAVIWriterParams@2@PEBV34@@Z; Ofc::TAttrWriterHelper<ODF::Percent,Ofc::TSelfAdapter<ODF::Percent>,1>::Write(wchar_t const *,int,ODF::Percent const &,Ofc::IWriterParams &,ODF::Percent const *)
0x180086299  mov     r12d, 143h
0x18008629f  cmp     [rbp+30h], r15
0x1800862a3  jz      short loc_1800862B1
0x1800862a5  mov     edx, r12d
0x1800862a8  mov     rcx, rsi
0x1800862ab  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800862b1  mov     r9, rdi
0x1800862b4  lea     r8, [rbp+30h]
0x1800862b8  mov     edx, r12d
0x1800862bb  lea     rcx, aHref; "href"
0x1800862c2  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TOptionalAdapter@VCVarStr@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VCVarStr@Ofc@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::CVarStr> const &,Ofc::IWriterParams &)
0x1800862c7  cmp     [rbp+38h], r15
0x1800862cb  jz      short loc_1800862D9
0x1800862cd  mov     edx, r12d
0x1800862d0  mov     rcx, rsi
0x1800862d3  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800862d9  mov     r9, rdi
0x1800862dc  lea     r8, [rbp+38h]
0x1800862e0  call    ?Write@?$TAttrWriterHelper@W4XlinkType@ODF@@V?$TOptionalAdapter@W4XlinkType@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@W4XlinkType@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::XlinkType,Ofc::TOptionalAdapter<ODF::XlinkType>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::XlinkType> const &,Ofc::IWriterParams &)
0x1800862e5  cmp     [rbp+40h], r15
0x1800862e9  jz      short loc_1800862F7
0x1800862eb  mov     edx, r12d
0x1800862ee  mov     rcx, rsi
0x1800862f1  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800862f7  mov     r9, rdi
0x1800862fa  lea     r8, [rbp+40h]
0x1800862fe  call    ?Write@?$TAttrWriterHelper@W4XlinkShow@ODF@@V?$TOptionalAdapter@W4XlinkShow@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@W4XlinkShow@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::XlinkShow,Ofc::TOptionalAdapter<ODF::XlinkShow>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::XlinkShow> const &,Ofc::IWriterParams &)
0x180086303  cmp     [rbp+48h], r15
0x180086307  jz      short loc_180086315
0x180086309  mov     edx, r12d
0x18008630c  mov     rcx, rsi
0x18008630f  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x180086315  mov     r9, rdi
0x180086318  lea     r8, [rbp+48h]
0x18008631c  call    ?Write@?$TAttrWriterHelper@W4XlinkActuate@ODF@@V?$TOptionalAdapter@W4XlinkActuate@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@W4XlinkActuate@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::XlinkActuate,Ofc::TOptionalAdapter<ODF::XlinkActuate>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::XlinkActuate> const &,Ofc::IWriterParams &)
0x180086321  cmp     [rbp+50h], r15
0x180086325  jz      short loc_180086333
0x180086327  mov     edx, r13d
0x18008632a  mov     rcx, rsi
0x18008632d  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x180086333  mov     r9, rdi
0x180086336  lea     r8, [rbp+50h]
0x18008633a  mov     edx, r13d
0x18008633d  lea     rcx, aVerb; "verb"
0x180086344  call    ?Write@?$TAttrWriterHelper@IV?$TOptionalAdapter@I@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@I@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<uint,Ofc::TOptionalAdapter<uint>,0>::Write(wchar_t const *,int,Ofc::TOptional<uint> const &,Ofc::IWriterParams &)
0x180086349  mov     rax, [r14]
0x18008634c  mov     rdx, [rdi+10h]
0x180086350  mov     rcx, r14
0x180086353  mov     rax, [rax]
0x180086356  call    cs:__guard_dispatch_icall_fptr
0x18008635c  mov     r9, rdi
0x18008635f  mov     r8, rbp
0x180086362  call    ?Write@?$TCompElemWriterHelper@VSound@ODF@@V?$TOptionalAdapter@VSound@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VSound@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TCompElemWriterHelper<ODF::Sound,Ofc::TOptionalAdapter<ODF::Sound>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::Sound> const &,Ofc::IWriterParams &)
0x180086367  mov     rcx, r14
0x18008636a  call    cs:__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ; Ofc::CWriterEmit::EmitEndElement(void)
0x180086370  nop
0x180086371  mov     rbx, [rsp+78h+arg_8]
0x180086379  add     rsp, 40h
0x18008637d  pop     r15
0x18008637f  pop     r14
0x180086381  pop     r13
0x180086383  pop     r12
0x180086385  pop     rdi
0x180086386  pop     rsi
0x180086387  pop     rbp
0x180086388  retn
```
