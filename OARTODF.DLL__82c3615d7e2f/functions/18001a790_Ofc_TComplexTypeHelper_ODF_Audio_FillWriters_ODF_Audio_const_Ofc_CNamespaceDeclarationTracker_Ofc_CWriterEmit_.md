# Ofc::TComplexTypeHelper<ODF::Audio>::FillWriters(ODF::Audio const &,Ofc::CNamespaceDeclarationTracker &,Ofc::CWriterEmit &,Ofc::IWriterParams &)

- ea: `0x18001a790`
- end: `0x18001aab7`
- name: `?FillWriters@?$TComplexTypeHelper@VAudio@ODF@@@Ofc@@SAXAEBVAudio@ODF@@AEAVCNamespaceDeclarationTracker@2@AEAVCWriterEmit@2@AEAVIWriterParams@2@@Z`
- size: `807`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800106a0`

## callees

- `0x18001a790`
- `0x18001d8b4`
- `0x18001da18`
- `0x18001db8c`
- `0x18001dc30`
- `0x18001e258`
- `0x18001e30c`
- `0x1801a80e0`

## import_xrefs

- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18001a7c7`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18001a7f1`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18001a82d`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18001a869`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18001a894`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18001a8bc`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18001a8fe`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18001a928`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18001a952`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18001a980`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18001a9bc`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18001a9f8`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18001aa34`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18001aa70`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18001a7c7`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18001a7f1`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18001a82d`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18001a869`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18001a894`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18001a8bc`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18001a8fe`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18001a928`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18001a952`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18001a980`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18001a9bc`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18001a9f8`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18001aa34`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18001aa70`
- `mso40uiWin32Client!__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ` at `0x18001aa98`
- `mso40uiWin32Client!__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ` at `0x18001aa98`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall Ofc::TComplexTypeHelper<ODF::Audio>::FillWriters(
        _QWORD *a1,
        Ofc::CNamespaceDeclarationTracker *a2,
        Ofc::CWriterEmit *a3,
        __int64 a4)
{
  int v8; // edx
  int v9; // ecx
  __int64 v10; // rdx
  __int64 v11; // rcx
  const wchar_t *v12; // [rsp+30h] [rbp-20h] BYREF
  const wchar_t *v13; // [rsp+38h] [rbp-18h] BYREF
  const wchar_t *v14; // [rsp+40h] [rbp-10h] BYREF
  const wchar_t *v15; // [rsp+48h] [rbp-8h] BYREF
  const wchar_t *v16; // [rsp+90h] [rbp+40h] BYREF
  const wchar_t *v17; // [rsp+A0h] [rbp+50h] BYREF
  const wchar_t *v18; // [rsp+A8h] [rbp+58h] BYREF

  if ( *a1 )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 315);
  LODWORD(v16) = 0;
  Ofc::TAttrWriterHelper<enum ODF::NodeType,Ofc::TOptionalAdapter<enum ODF::NodeType>,0>::Write(
    (_DWORD)a1,
    (_DWORD)a2,
    (_DWORD)a1,
    a4,
    (__int64)&v16);
  if ( a1[1] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 315);
  v17 = &dword_1801DBD74;
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(
    (unsigned int)L"preset-id",
    315,
    (_DWORD)a1 + 8,
    a4,
    (__int64)&v17);
  if ( a1[2] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 315);
  v18 = &dword_1801DBD74;
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(
    (unsigned int)L"preset-sub-type",
    315,
    (_DWORD)a1 + 16,
    a4,
    (__int64)&v18);
  if ( a1[3] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 315);
  LODWORD(v16) = 0;
  Ofc::TAttrWriterHelper<enum ODF::PresetClass,Ofc::TOptionalAdapter<enum ODF::PresetClass>,0>::Write(
    v9,
    v8,
    (_DWORD)a1 + 24,
    a4,
    (__int64)&v16);
  if ( a1[4] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 315);
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(L"master-element", 315, a1 + 4, a4);
  if ( a1[5] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 315);
  v16 = &dword_1801DBD74;
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(
    (unsigned int)L"group-id",
    315,
    (_DWORD)a1 + 40,
    a4,
    (__int64)&v16);
  if ( a1[6] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 301);
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(L"id", 301, a1 + 6, a4);
  if ( a1[7] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 323);
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(L"href", 323, a1 + 7, a4);
  if ( a1[8] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 301);
  Ofc::TAttrWriterHelper<double,Ofc::TOptionalAdapter<double>,0>::Write(L"audio-level", 301, a1 + 8, a4);
  if ( a1[9] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 317);
  v12 = &dword_1801DBD74;
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(
    (unsigned int)L"begin",
    317,
    (_DWORD)a1 + 72,
    a4,
    (__int64)&v12);
  if ( a1[10] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 317);
  v13 = &dword_1801DBD74;
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(
    (unsigned int)L"end",
    317,
    (_DWORD)a1 + 80,
    a4,
    (__int64)&v13);
  if ( a1[11] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 317);
  v14 = &dword_1801DBD74;
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(
    (unsigned int)L"dur",
    317,
    (_DWORD)a1 + 88,
    a4,
    (__int64)&v14);
  if ( a1[12] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 317);
  v15 = &dword_1801DBD74;
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(
    (unsigned int)L"repeatDur",
    317,
    (_DWORD)a1 + 96,
    a4,
    (__int64)&v15);
  if ( a1[13] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 317);
  Ofc::TAttrWriterHelper<Ofc::TVariant<ODF::RepeatCountIDsImpl>,Ofc::TOptionalAdapter<Ofc::TVariant<ODF::RepeatCountIDsImpl>>,0>::Write(
    v11,
    v10,
    a1 + 13,
    a4);
  (**(void (__fastcall ***)(Ofc::CWriterEmit *, _QWORD))a3)(a3, *(_QWORD *)(a4 + 16));
  Ofc::CWriterEmit::EmitEndElement(a3);
}

```

## disassembly

```asm
0x18001a790  mov     [rsp-38h+arg_8], rbx
0x18001a795  push    rbp
0x18001a796  push    rsi
0x18001a797  push    rdi
0x18001a798  push    r12
0x18001a79a  push    r13
0x18001a79c  push    r14
0x18001a79e  push    r15
0x18001a7a0  mov     rbp, rsp
0x18001a7a3  sub     rsp, 50h
0x18001a7a7  mov     rsi, r9
0x18001a7aa  mov     r15, r8
0x18001a7ad  mov     rbx, rdx
0x18001a7b0  mov     rdi, rcx
0x18001a7b3  mov     r13d, 13Bh
0x18001a7b9  xor     r12d, r12d
0x18001a7bc  cmp     [rcx], r12
0x18001a7bf  jz      short loc_18001A7CD
0x18001a7c1  mov     edx, r13d
0x18001a7c4  mov     rcx, rbx
0x18001a7c7  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18001a7cd  mov     dword ptr [rbp+arg_0], r12d
0x18001a7d1  lea     rax, [rbp+arg_0]
0x18001a7d5  mov     [rsp+50h+var_30], rax
0x18001a7da  mov     r9, rsi
0x18001a7dd  mov     r8, rdi
0x18001a7e0  call    ?Write@?$TAttrWriterHelper@W4NodeType@ODF@@V?$TOptionalAdapter@W4NodeType@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@W4NodeType@ODF@@@2@AEAVIWriterParams@2@PEBW4NodeType@ODF@@@Z; Ofc::TAttrWriterHelper<ODF::NodeType,Ofc::TOptionalAdapter<ODF::NodeType>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::NodeType> const &,Ofc::IWriterParams &,ODF::NodeType const *)
0x18001a7e5  cmp     [rdi+8], r12
0x18001a7e9  jz      short loc_18001A7F7
0x18001a7eb  mov     edx, r13d
0x18001a7ee  mov     rcx, rbx
0x18001a7f1  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18001a7f7  lea     rax, dword_1801DBD74
0x18001a7fe  mov     [rbp+arg_10], rax
0x18001a802  lea     rax, [rbp+arg_10]
0x18001a806  mov     [rsp+50h+var_30], rax
0x18001a80b  mov     r9, rsi
0x18001a80e  lea     r8, [rdi+8]
0x18001a812  mov     edx, r13d
0x18001a815  lea     rcx, aPresetId; "preset-id"
0x18001a81c  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TOptionalAdapter@VCVarStr@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VCVarStr@Ofc@@@2@AEAVIWriterParams@2@PEBVCVarStr@2@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::CVarStr> const &,Ofc::IWriterParams &,Ofc::CVarStr const *)
0x18001a821  cmp     [rdi+10h], r12
0x18001a825  jz      short loc_18001A833
0x18001a827  mov     edx, r13d
0x18001a82a  mov     rcx, rbx
0x18001a82d  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18001a833  lea     rax, dword_1801DBD74
0x18001a83a  mov     [rbp+arg_18], rax
0x18001a83e  lea     rax, [rbp+arg_18]
0x18001a842  mov     [rsp+50h+var_30], rax
0x18001a847  mov     r9, rsi
0x18001a84a  lea     r8, [rdi+10h]
0x18001a84e  mov     edx, r13d
0x18001a851  lea     rcx, aPresetSubType; "preset-sub-type"
0x18001a858  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TOptionalAdapter@VCVarStr@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VCVarStr@Ofc@@@2@AEAVIWriterParams@2@PEBVCVarStr@2@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::CVarStr> const &,Ofc::IWriterParams &,Ofc::CVarStr const *)
0x18001a85d  cmp     [rdi+18h], r12
0x18001a861  jz      short loc_18001A86F
0x18001a863  mov     edx, r13d
0x18001a866  mov     rcx, rbx
0x18001a869  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18001a86f  mov     dword ptr [rbp+arg_0], r12d
0x18001a873  lea     rax, [rbp+arg_0]
0x18001a877  mov     [rsp+50h+var_30], rax
0x18001a87c  mov     r9, rsi
0x18001a87f  lea     r8, [rdi+18h]
0x18001a883  call    ?Write@?$TAttrWriterHelper@W4PresetClass@ODF@@V?$TOptionalAdapter@W4PresetClass@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@W4PresetClass@ODF@@@2@AEAVIWriterParams@2@PEBW4PresetClass@ODF@@@Z; Ofc::TAttrWriterHelper<ODF::PresetClass,Ofc::TOptionalAdapter<ODF::PresetClass>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::PresetClass> const &,Ofc::IWriterParams &,ODF::PresetClass const *)
0x18001a888  cmp     [rdi+20h], r12
0x18001a88c  jz      short loc_18001A89A
0x18001a88e  mov     edx, r13d
0x18001a891  mov     rcx, rbx
0x18001a894  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18001a89a  mov     r9, rsi
0x18001a89d  lea     r8, [rdi+20h]
0x18001a8a1  mov     edx, r13d
0x18001a8a4  lea     rcx, aMasterElement; "master-element"
0x18001a8ab  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TOptionalAdapter@VCVarStr@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VCVarStr@Ofc@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::CVarStr> const &,Ofc::IWriterParams &)
0x18001a8b0  cmp     [rdi+28h], r12
0x18001a8b4  jz      short loc_18001A8C2
0x18001a8b6  mov     edx, r13d
0x18001a8b9  mov     rcx, rbx
0x18001a8bc  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18001a8c2  lea     rax, dword_1801DBD74
0x18001a8c9  mov     [rbp+arg_0], rax
0x18001a8cd  lea     rax, [rbp+arg_0]
0x18001a8d1  mov     [rsp+50h+var_30], rax
0x18001a8d6  mov     r9, rsi
0x18001a8d9  lea     r8, [rdi+28h]
0x18001a8dd  mov     edx, r13d
0x18001a8e0  lea     rcx, aGroupId; "group-id"
0x18001a8e7  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TOptionalAdapter@VCVarStr@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VCVarStr@Ofc@@@2@AEAVIWriterParams@2@PEBVCVarStr@2@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::CVarStr> const &,Ofc::IWriterParams &,Ofc::CVarStr const *)
0x18001a8ec  mov     r13d, 12Dh
0x18001a8f2  cmp     [rdi+30h], r12
0x18001a8f6  jz      short loc_18001A904
0x18001a8f8  mov     edx, r13d
0x18001a8fb  mov     rcx, rbx
0x18001a8fe  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18001a904  mov     r9, rsi
0x18001a907  lea     r8, [rdi+30h]
0x18001a90b  mov     edx, r13d
0x18001a90e  lea     rcx, aId; "id"
0x18001a915  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TOptionalAdapter@VCVarStr@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VCVarStr@Ofc@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::CVarStr> const &,Ofc::IWriterParams &)
0x18001a91a  cmp     [rdi+38h], r12
0x18001a91e  jz      short loc_18001A92E
0x18001a920  mov     edx, 143h
0x18001a925  mov     rcx, rbx
0x18001a928  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18001a92e  mov     r9, rsi
0x18001a931  lea     r8, [rdi+38h]
0x18001a935  mov     edx, 143h
0x18001a93a  lea     rcx, aHref; "href"
0x18001a941  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TOptionalAdapter@VCVarStr@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VCVarStr@Ofc@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::CVarStr> const &,Ofc::IWriterParams &)
0x18001a946  cmp     [rdi+40h], r12
0x18001a94a  jz      short loc_18001A958
0x18001a94c  mov     edx, r13d
0x18001a94f  mov     rcx, rbx
0x18001a952  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18001a958  mov     r9, rsi
0x18001a95b  lea     r8, [rdi+40h]
0x18001a95f  mov     edx, r13d
0x18001a962  lea     rcx, aAudioLevel; "audio-level"
0x18001a969  call    ?Write@?$TAttrWriterHelper@NV?$TOptionalAdapter@N@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@N@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<double,Ofc::TOptionalAdapter<double>,0>::Write(wchar_t const *,int,Ofc::TOptional<double> const &,Ofc::IWriterParams &)
0x18001a96e  mov     r13d, 13Dh
0x18001a974  cmp     [rdi+48h], r12
0x18001a978  jz      short loc_18001A986
0x18001a97a  mov     edx, r13d
0x18001a97d  mov     rcx, rbx
0x18001a980  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18001a986  lea     rax, dword_1801DBD74
0x18001a98d  mov     [rbp+var_20], rax
0x18001a991  lea     rax, [rbp+var_20]
0x18001a995  mov     [rsp+50h+var_30], rax
0x18001a99a  mov     r9, rsi
0x18001a99d  lea     r8, [rdi+48h]
0x18001a9a1  mov     edx, r13d
0x18001a9a4  lea     rcx, aBegin; "begin"
0x18001a9ab  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TOptionalAdapter@VCVarStr@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VCVarStr@Ofc@@@2@AEAVIWriterParams@2@PEBVCVarStr@2@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::CVarStr> const &,Ofc::IWriterParams &,Ofc::CVarStr const *)
0x18001a9b0  cmp     [rdi+50h], r12
0x18001a9b4  jz      short loc_18001A9C2
0x18001a9b6  mov     edx, r13d
0x18001a9b9  mov     rcx, rbx
0x18001a9bc  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18001a9c2  lea     rax, dword_1801DBD74
0x18001a9c9  mov     [rbp+var_18], rax
0x18001a9cd  lea     rax, [rbp+var_18]
0x18001a9d1  mov     [rsp+50h+var_30], rax
0x18001a9d6  mov     r9, rsi
0x18001a9d9  lea     r8, [rdi+50h]
0x18001a9dd  mov     edx, r13d
0x18001a9e0  lea     rcx, aEnd; "end"
0x18001a9e7  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TOptionalAdapter@VCVarStr@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VCVarStr@Ofc@@@2@AEAVIWriterParams@2@PEBVCVarStr@2@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::CVarStr> const &,Ofc::IWriterParams &,Ofc::CVarStr const *)
0x18001a9ec  cmp     [rdi+58h], r12
0x18001a9f0  jz      short loc_18001A9FE
0x18001a9f2  mov     edx, r13d
0x18001a9f5  mov     rcx, rbx
0x18001a9f8  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18001a9fe  lea     rax, dword_1801DBD74
0x18001aa05  mov     [rbp+var_10], rax
0x18001aa09  lea     rax, [rbp+var_10]
0x18001aa0d  mov     [rsp+50h+var_30], rax
0x18001aa12  mov     r9, rsi
0x18001aa15  lea     r8, [rdi+58h]
0x18001aa19  mov     edx, r13d
0x18001aa1c  lea     rcx, aDur; "dur"
0x18001aa23  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TOptionalAdapter@VCVarStr@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VCVarStr@Ofc@@@2@AEAVIWriterParams@2@PEBVCVarStr@2@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::CVarStr> const &,Ofc::IWriterParams &,Ofc::CVarStr const *)
0x18001aa28  cmp     [rdi+60h], r12
0x18001aa2c  jz      short loc_18001AA3A
0x18001aa2e  mov     edx, r13d
0x18001aa31  mov     rcx, rbx
0x18001aa34  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18001aa3a  lea     rax, dword_1801DBD74
0x18001aa41  mov     [rbp+var_8], rax
0x18001aa45  lea     rax, [rbp+var_8]
0x18001aa49  mov     [rsp+50h+var_30], rax
0x18001aa4e  mov     r9, rsi
0x18001aa51  lea     r8, [rdi+60h]
0x18001aa55  mov     edx, r13d
0x18001aa58  lea     rcx, aRepeatdur; "repeatDur"
0x18001aa5f  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TOptionalAdapter@VCVarStr@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VCVarStr@Ofc@@@2@AEAVIWriterParams@2@PEBVCVarStr@2@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::CVarStr> const &,Ofc::IWriterParams &,Ofc::CVarStr const *)
0x18001aa64  cmp     [rdi+68h], r12
0x18001aa68  jz      short loc_18001AA76
0x18001aa6a  mov     edx, r13d
0x18001aa6d  mov     rcx, rbx
0x18001aa70  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18001aa76  mov     r9, rsi
0x18001aa79  lea     r8, [rdi+68h]
0x18001aa7d  call    ?Write@?$TAttrWriterHelper@V?$TVariant@VRepeatCountIDsImpl@ODF@@@Ofc@@V?$TOptionalAdapter@V?$TVariant@VRepeatCountIDsImpl@ODF@@@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@V?$TVariant@VRepeatCountIDsImpl@ODF@@@Ofc@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::TVariant<ODF::RepeatCountIDsImpl>,Ofc::TOptionalAdapter<Ofc::TVariant<ODF::RepeatCountIDsImpl>>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::TVariant<ODF::RepeatCountIDsImpl>> const &,Ofc::IWriterParams &)
0x18001aa82  mov     rax, [r15]
0x18001aa85  mov     rdx, [rsi+10h]
0x18001aa89  mov     rcx, r15
0x18001aa8c  mov     rax, [rax]
0x18001aa8f  call    cs:__guard_dispatch_icall_fptr
0x18001aa95  mov     rcx, r15
0x18001aa98  call    cs:__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ; Ofc::CWriterEmit::EmitEndElement(void)
0x18001aa9e  nop
0x18001aa9f  mov     rbx, [rsp+50h+arg_8]
0x18001aaa7  add     rsp, 50h
0x18001aaab  pop     r15
0x18001aaad  pop     r14
0x18001aaaf  pop     r13
0x18001aab1  pop     r12
0x18001aab3  pop     rdi
0x18001aab4  pop     rsi
0x18001aab5  pop     rbp
0x18001aab6  retn
```
