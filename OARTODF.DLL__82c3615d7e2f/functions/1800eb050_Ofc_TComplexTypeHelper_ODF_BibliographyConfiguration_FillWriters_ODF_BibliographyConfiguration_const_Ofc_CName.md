# Ofc::TComplexTypeHelper<ODF::BibliographyConfiguration>::FillWriters(ODF::BibliographyConfiguration const &,Ofc::CNamespaceDeclarationTracker &,Ofc::CWriterEmit &,Ofc::IWriterParams &)

- ea: `0x1800eb050`
- end: `0x1800eb28f`
- name: `?FillWriters@?$TComplexTypeHelper@VBibliographyConfiguration@ODF@@@Ofc@@SAXAEBVBibliographyConfiguration@ODF@@AEAVCNamespaceDeclarationTracker@2@AEAVCWriterEmit@2@AEAVIWriterParams@2@@Z`
- size: `575`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180083fe0`

## callees

- `0x1800025a0`
- `0x18001dd94`
- `0x18001de54`
- `0x180025e48`
- `0x1800eb050`
- `0x1800ec3b4`
- `0x1801a80e0`

## import_xrefs

- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800eb093`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800eb0cb`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800eb0fc`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800eb12f`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800eb167`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800eb193`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800eb1bd`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800eb093`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800eb0cb`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800eb0fc`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800eb12f`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800eb167`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800eb193`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800eb1bd`
- `mso40uiWin32Client!__imp_??1CNamespaceDeclarationTracker@Ofc@@QEAA@XZ` at `0x1800eb248`
- `mso40uiWin32Client!__imp_??1CNamespaceDeclarationTracker@Ofc@@QEAA@XZ` at `0x1800eb248`
- `mso40uiWin32Client!__imp_??0TCFWH@Ofc@@QEAA@AEAVIWriterParams@1@HPEB_W@Z` at `0x1800eb229`
- `mso40uiWin32Client!__imp_??0TCFWH@Ofc@@QEAA@AEAVIWriterParams@1@HPEB_W@Z` at `0x1800eb229`
- `mso40uiWin32Client!__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ` at `0x1800eb25a`
- `mso40uiWin32Client!__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ` at `0x1800eb25a`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800eb288`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800eb288`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall Ofc::TComplexTypeHelper<ODF::BibliographyConfiguration>::FillWriters(
        __int64 a1,
        Ofc::CNamespaceDeclarationTracker *a2,
        Ofc::CWriterEmit *a3,
        __int64 a4)
{
  unsigned int v8; // edi
  __int64 v9; // rbx
  char v10[8]; // [rsp+30h] [rbp-D0h] BYREF
  const wchar_t *v11; // [rsp+38h] [rbp-C8h] BYREF
  const wchar_t *v12; // [rsp+40h] [rbp-C0h] BYREF
  const wchar_t *v13; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v14[8]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v15[40]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v16[560]; // [rsp+80h] [rbp-80h] BYREF

  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 321);
  v11 = &dword_1801DBD74;
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(
    (unsigned int)L"prefix",
    321,
    a1 + 24,
    a4,
    (__int64)&v11);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 321);
  v12 = &dword_1801DBD74;
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(
    (unsigned int)L"suffix",
    321,
    a1 + 32,
    a4,
    (__int64)&v12);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 321);
  v8 = 0;
  v10[0] = 0;
  Ofc::TAttrWriterHelper<ODF::OdfBoolean,Ofc::TSelfAdapter<ODF::OdfBoolean>,1>::Write(
    (unsigned int)L"numbered-entries",
    321,
    a1 + 40,
    a4,
    (__int64)v10);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 321);
  v10[0] = 1;
  Ofc::TAttrWriterHelper<ODF::OdfBoolean,Ofc::TSelfAdapter<ODF::OdfBoolean>,1>::Write(
    (unsigned int)L"sort-by-position",
    321,
    a1 + 41,
    a4,
    (__int64)v10);
  if ( *(_QWORD *)(a1 + 48) )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 309);
  Ofc::TAttrWriterHelper<ODF::CellAddress,Ofc::TOptionalAdapter<ODF::CellAddress>,0>::Write(
    L"language",
    309,
    a1 + 48,
    a4);
  if ( *(_QWORD *)(a1 + 56) )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 309);
  Ofc::TAttrWriterHelper<ODF::CellAddress,Ofc::TOptionalAdapter<ODF::CellAddress>,0>::Write(
    L"country",
    309,
    a1 + 56,
    a4);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 321);
  v13 = &dword_1801DBD74;
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(
    (unsigned int)L"sort-algorithm",
    321,
    a1 + 64,
    a4,
    (__int64)&v13);
  (**(void (__fastcall ***)(Ofc::CWriterEmit *, _QWORD))a3)(a3, *(_QWORD *)(a4 + 16));
  if ( *(_DWORD *)(a1 + 16) )
  {
    do
    {
      if ( v8 >= *(_DWORD *)(a1 + 16) )
      {
        CrashWithRecovery(0x1E892498u, 0);
        JUMPOUT(0x1800EB28ELL);
      }
      v9 = *(_QWORD *)(a1 + 8) + 8LL * v8;
      Ofc::TCFWH::TCFWH((Ofc::TCFWH *)v14, (struct Ofc::IWriterParams *)a4, 321, L"sort-key");
      Ofc::TComplexTypeHelper<ODF::SortKey>::FillWriters(v9, v15, v16, a4);
      Ofc::CNamespaceDeclarationTracker::~CNamespaceDeclarationTracker((Ofc::CNamespaceDeclarationTracker *)v15);
      ++v8;
    }
    while ( v8 < *(_DWORD *)(a1 + 16) );
  }
  Ofc::CWriterEmit::EmitEndElement(a3);
}

```

## disassembly

```asm
0x1800eb050  push    rbp
0x1800eb052  push    rbx
0x1800eb053  push    rsi
0x1800eb054  push    rdi
0x1800eb055  push    r12
0x1800eb057  push    r14
0x1800eb059  push    r15
0x1800eb05b  lea     rbp, [rsp-1C0h]
0x1800eb063  sub     rsp, 2C0h
0x1800eb06a  mov     rax, cs:__security_cookie
0x1800eb071  xor     rax, rsp
0x1800eb074  mov     [rbp+1F0h+var_40], rax
0x1800eb07b  mov     r14, r9
0x1800eb07e  mov     r12, r8
0x1800eb081  mov     rbx, rdx
0x1800eb084  mov     rsi, rcx
0x1800eb087  mov     r15d, 141h
0x1800eb08d  mov     edx, r15d
0x1800eb090  mov     rcx, rbx
0x1800eb093  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800eb099  lea     rdi, dword_1801DBD74
0x1800eb0a0  mov     [rsp+2F0h+var_2B8], rdi
0x1800eb0a5  lea     r8, [rsi+18h]
0x1800eb0a9  lea     rax, [rsp+2F0h+var_2B8]
0x1800eb0ae  mov     [rsp+2F0h+var_2D0], rax
0x1800eb0b3  mov     r9, r14
0x1800eb0b6  mov     edx, r15d
0x1800eb0b9  lea     rcx, aPrefix; "prefix"
0x1800eb0c0  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TSelfAdapter@VCVarStr@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBVCVarStr@2@AEAVIWriterParams@2@PEBV32@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(wchar_t const *,int,Ofc::CVarStr const &,Ofc::IWriterParams &,Ofc::CVarStr const *)
0x1800eb0c5  mov     edx, r15d
0x1800eb0c8  mov     rcx, rbx
0x1800eb0cb  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800eb0d1  mov     [rsp+2F0h+var_2B0], rdi
0x1800eb0d6  lea     r8, [rsi+20h]
0x1800eb0da  lea     rax, [rsp+2F0h+var_2B0]
0x1800eb0df  mov     [rsp+2F0h+var_2D0], rax
0x1800eb0e4  mov     r9, r14
0x1800eb0e7  mov     edx, r15d
0x1800eb0ea  lea     rcx, aSuffix; "suffix"
0x1800eb0f1  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TSelfAdapter@VCVarStr@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBVCVarStr@2@AEAVIWriterParams@2@PEBV32@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(wchar_t const *,int,Ofc::CVarStr const &,Ofc::IWriterParams &,Ofc::CVarStr const *)
0x1800eb0f6  mov     edx, r15d
0x1800eb0f9  mov     rcx, rbx
0x1800eb0fc  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800eb102  xor     edi, edi
0x1800eb104  mov     [rsp+2F0h+var_2C0], dil
0x1800eb109  lea     r8, [rsi+28h]
0x1800eb10d  lea     rax, [rsp+2F0h+var_2C0]
0x1800eb112  mov     [rsp+2F0h+var_2D0], rax
0x1800eb117  mov     r9, r14
0x1800eb11a  mov     edx, r15d
0x1800eb11d  lea     rcx, aNumberedEntrie; "numbered-entries"
0x1800eb124  call    ?Write@?$TAttrWriterHelper@VOdfBoolean@ODF@@V?$TSelfAdapter@VOdfBoolean@ODF@@@Ofc@@$00@Ofc@@SAXPEB_WHAEBVOdfBoolean@ODF@@AEAVIWriterParams@2@PEBV34@@Z; Ofc::TAttrWriterHelper<ODF::OdfBoolean,Ofc::TSelfAdapter<ODF::OdfBoolean>,1>::Write(wchar_t const *,int,ODF::OdfBoolean const &,Ofc::IWriterParams &,ODF::OdfBoolean const *)
0x1800eb129  mov     edx, r15d
0x1800eb12c  mov     rcx, rbx
0x1800eb12f  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800eb135  mov     [rsp+2F0h+var_2C0], 1
0x1800eb13a  lea     r8, [rsi+29h]
0x1800eb13e  lea     rax, [rsp+2F0h+var_2C0]
0x1800eb143  mov     [rsp+2F0h+var_2D0], rax
0x1800eb148  mov     r9, r14
0x1800eb14b  mov     edx, r15d
0x1800eb14e  lea     rcx, aSortByPosition; "sort-by-position"
0x1800eb155  call    ?Write@?$TAttrWriterHelper@VOdfBoolean@ODF@@V?$TSelfAdapter@VOdfBoolean@ODF@@@Ofc@@$00@Ofc@@SAXPEB_WHAEBVOdfBoolean@ODF@@AEAVIWriterParams@2@PEBV34@@Z; Ofc::TAttrWriterHelper<ODF::OdfBoolean,Ofc::TSelfAdapter<ODF::OdfBoolean>,1>::Write(wchar_t const *,int,ODF::OdfBoolean const &,Ofc::IWriterParams &,ODF::OdfBoolean const *)
0x1800eb15a  cmp     [rsi+30h], rdi
0x1800eb15e  jz      short loc_1800EB16D
0x1800eb160  lea     edx, [r15-0Ch]
0x1800eb164  mov     rcx, rbx
0x1800eb167  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800eb16d  mov     r9, r14
0x1800eb170  lea     r8, [rsi+30h]
0x1800eb174  mov     edx, 135h
0x1800eb179  lea     rcx, aLanguage; "language"
0x1800eb180  call    ?Write@?$TAttrWriterHelper@VCellAddress@ODF@@V?$TOptionalAdapter@VCellAddress@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VCellAddress@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::CellAddress,Ofc::TOptionalAdapter<ODF::CellAddress>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::CellAddress> const &,Ofc::IWriterParams &)
0x1800eb185  cmp     [rsi+38h], rdi
0x1800eb189  jz      short loc_1800EB199
0x1800eb18b  mov     edx, 135h
0x1800eb190  mov     rcx, rbx
0x1800eb193  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800eb199  mov     r9, r14
0x1800eb19c  lea     r8, [rsi+38h]
0x1800eb1a0  mov     edx, 135h
0x1800eb1a5  lea     rcx, aCountry; "country"
0x1800eb1ac  call    ?Write@?$TAttrWriterHelper@VCellAddress@ODF@@V?$TOptionalAdapter@VCellAddress@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VCellAddress@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::CellAddress,Ofc::TOptionalAdapter<ODF::CellAddress>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::CellAddress> const &,Ofc::IWriterParams &)
0x1800eb1b1  mov     r15d, 141h
0x1800eb1b7  mov     edx, r15d
0x1800eb1ba  mov     rcx, rbx
0x1800eb1bd  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800eb1c3  lea     rax, dword_1801DBD74
0x1800eb1ca  mov     [rsp+2F0h+var_2A8], rax
0x1800eb1cf  lea     r8, [rsi+40h]
0x1800eb1d3  lea     rax, [rsp+2F0h+var_2A8]
0x1800eb1d8  mov     [rsp+2F0h+var_2D0], rax
0x1800eb1dd  mov     r9, r14
0x1800eb1e0  mov     edx, r15d
0x1800eb1e3  lea     rcx, aSortAlgorithm; "sort-algorithm"
0x1800eb1ea  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TSelfAdapter@VCVarStr@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBVCVarStr@2@AEAVIWriterParams@2@PEBV32@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(wchar_t const *,int,Ofc::CVarStr const &,Ofc::IWriterParams &,Ofc::CVarStr const *)
0x1800eb1ef  mov     rax, [r12]
0x1800eb1f3  mov     rdx, [r14+10h]
0x1800eb1f7  mov     rcx, r12
0x1800eb1fa  mov     rax, [rax]
0x1800eb1fd  call    cs:__guard_dispatch_icall_fptr
0x1800eb203  cmp     [rsi+10h], edi
0x1800eb206  jbe     short loc_1800EB257
0x1800eb208  cmp     edi, [rsi+10h]
0x1800eb20b  jnb     short loc_1800EB281
0x1800eb20d  mov     ecx, edi
0x1800eb20f  mov     rax, [rsi+8]
0x1800eb213  lea     rbx, [rax+rcx*8]
0x1800eb217  lea     r9, aSortKey; "sort-key"
0x1800eb21e  mov     r8d, r15d
0x1800eb221  mov     rdx, r14
0x1800eb224  lea     rcx, [rsp+2F0h+var_2A0]
0x1800eb229  call    cs:__imp_??0TCFWH@Ofc@@QEAA@AEAVIWriterParams@1@HPEB_W@Z; Ofc::TCFWH::TCFWH(Ofc::IWriterParams &,int,wchar_t const *)
0x1800eb22f  mov     r9, r14
0x1800eb232  lea     r8, [rbp+1F0h+var_270]
0x1800eb236  lea     rdx, [rsp+2F0h+var_298]
0x1800eb23b  mov     rcx, rbx
0x1800eb23e  call    ?FillWriters@?$TComplexTypeHelper@VSortKey@ODF@@@Ofc@@SAXAEBVSortKey@ODF@@AEAVCNamespaceDeclarationTracker@2@AEAVCWriterEmit@2@AEAVIWriterParams@2@@Z; Ofc::TComplexTypeHelper<ODF::SortKey>::FillWriters(ODF::SortKey const &,Ofc::CNamespaceDeclarationTracker &,Ofc::CWriterEmit &,Ofc::IWriterParams &)
0x1800eb243  lea     rcx, [rsp+2F0h+var_298]
0x1800eb248  call    cs:__imp_??1CNamespaceDeclarationTracker@Ofc@@QEAA@XZ; Ofc::CNamespaceDeclarationTracker::~CNamespaceDeclarationTracker(void)
0x1800eb24e  xchg    ax, ax
0x1800eb250  inc     edi
0x1800eb252  cmp     edi, [rsi+10h]
0x1800eb255  jb      short loc_1800EB208
0x1800eb257  mov     rcx, r12
0x1800eb25a  call    cs:__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ; Ofc::CWriterEmit::EmitEndElement(void)
0x1800eb260  mov     rcx, [rbp+1F0h+var_40]
0x1800eb267  xor     rcx, rsp; StackCookie
0x1800eb26a  call    __security_check_cookie
0x1800eb26f  add     rsp, 2C0h
0x1800eb276  pop     r15
0x1800eb278  pop     r14
0x1800eb27a  pop     r12
0x1800eb27c  pop     rdi
0x1800eb27d  pop     rsi
0x1800eb27e  pop     rbx
0x1800eb27f  pop     rbp
0x1800eb280  retn
0x1800eb281  xor     edx, edx
0x1800eb283  mov     ecx, 1E892498h
0x1800eb288  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
