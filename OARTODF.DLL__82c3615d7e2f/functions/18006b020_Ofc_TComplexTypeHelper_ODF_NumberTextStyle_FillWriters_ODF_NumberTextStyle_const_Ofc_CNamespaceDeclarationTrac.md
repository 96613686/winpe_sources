# Ofc::TComplexTypeHelper<ODF::NumberTextStyle>::FillWriters(ODF::NumberTextStyle const &,Ofc::CNamespaceDeclarationTracker &,Ofc::CWriterEmit &,Ofc::IWriterParams &)

- ea: `0x18006b020`
- end: `0x18006b395`
- name: `?FillWriters@?$TComplexTypeHelper@VNumberTextStyle@ODF@@@Ofc@@SAXAEBVNumberTextStyle@ODF@@AEAVCNamespaceDeclarationTracker@2@AEAVCWriterEmit@2@AEAVIWriterParams@2@@Z`
- size: `885`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180077f60`

## callees

- `0x180007b18`
- `0x18001dcf4`
- `0x18001dd94`
- `0x180025e48`
- `0x18002603c`
- `0x180026300`
- `0x180062a20`
- `0x180062aa0`
- `0x180069124`
- `0x18006b020`
- `0x18006f8f4`
- `0x18006faf4`
- `0x1801a80e0`

## import_xrefs

- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18006b048`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18006b074`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18006b09d`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18006b0bf`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18006b0fe`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18006b128`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18006b16b`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18006b19e`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18006b1c5`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18006b1ff`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18006b048`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18006b074`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18006b09d`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18006b0bf`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18006b0fe`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18006b128`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18006b16b`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18006b19e`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18006b1c5`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18006b1ff`
- `mso40uiWin32Client!__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ` at `0x18006b313`
- `mso40uiWin32Client!__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ` at `0x18006b313`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18006b380`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18006b38e`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18006b380`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18006b38e`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18006b33f`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18006b364`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18006b33f`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18006b364`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Ofc::TComplexTypeHelper<ODF::NumberTextStyle>::FillWriters(
        __int64 a1,
        Ofc::CNamespaceDeclarationTracker *a2,
        Ofc::CWriterEmit *a3,
        __int64 a4)
{
  int v8; // edx
  int v9; // ecx
  __int64 v10; // rdx
  __int64 v11; // rcx
  unsigned int v12; // eax
  unsigned int v13; // r15d
  __int64 v14; // rsi
  __int64 v15; // rax
  unsigned int v16; // eax
  __int64 v17; // rsi
  void *v18; // rdx
  Mso::Memory *v19; // rcx
  Mso::Memory *v20; // rcx
  _QWORD v21[5]; // [rsp+30h] [rbp-30h] BYREF
  int v22; // [rsp+58h] [rbp-8h]
  int v23; // [rsp+A0h] [rbp+40h] BYREF
  __int64 v24; // [rsp+B0h] [rbp+50h] BYREF
  const wchar_t *v25; // [rsp+B8h] [rbp+58h] BYREF

  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 319);
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(L"name", 319, a1 + 72, a4);
  if ( *(_QWORD *)(a1 + 80) )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 314);
  Ofc::TAttrWriterHelper<ODF::CellAddress,Ofc::TOptionalAdapter<ODF::CellAddress>,0>::Write(
    L"language",
    314,
    a1 + 80,
    a4);
  if ( *(_QWORD *)(a1 + 88) )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 314);
  Ofc::TAttrWriterHelper<ODF::CellAddress,Ofc::TOptionalAdapter<ODF::CellAddress>,0>::Write(
    L"country",
    314,
    a1 + 88,
    a4);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 314);
  v25 = &dword_1801DBD74;
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(
    (unsigned int)L"title",
    314,
    a1 + 96,
    a4,
    (__int64)&v25);
  if ( *(_QWORD *)(a1 + 104) )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 319);
  Ofc::TAttrWriterHelper<ODF::OdfBoolean,Ofc::TOptionalAdapter<ODF::OdfBoolean>,0>::Write(
    L"volatile",
    319,
    a1 + 104,
    a4);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 314);
  Ofc::CVarStr::CVarStr((Ofc::CVarStr *)&v24, L"1");
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(
    (unsigned int)L"transliteration-format",
    314,
    a1 + 112,
    a4,
    (__int64)&v24);
  if ( *(_QWORD *)(a1 + 120) )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 314);
  Ofc::TAttrWriterHelper<ODF::CellAddress,Ofc::TOptionalAdapter<ODF::CellAddress>,0>::Write(
    L"transliteration-language",
    314,
    a1 + 120,
    a4);
  if ( *(_QWORD *)(a1 + 128) )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 314);
  Ofc::TAttrWriterHelper<ODF::CellAddress,Ofc::TOptionalAdapter<ODF::CellAddress>,0>::Write(
    L"transliteration-country",
    314,
    a1 + 128,
    a4);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 314);
  v23 = 0;
  Ofc::TAttrWriterHelper<enum ODF::TransliterationStyle,Ofc::TSelfAdapter<enum ODF::TransliterationStyle>,1>::Write(
    v9,
    v8,
    a1 + 136,
    a4,
    (__int64)&v23);
  if ( *(_QWORD *)(a1 + 144) )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 314);
  Ofc::TAttrWriterHelper<ODF::Language,Ofc::TOptionalAdapter<ODF::Language>,0>::Write(v11, v10, a1 + 144, a4);
  (**(void (__fastcall ***)(Ofc::CWriterEmit *, _QWORD))a3)(a3, *(_QWORD *)(a4 + 16));
  if ( *(_QWORD *)a1 )
    Ofc::TCompFillWritersHelper<ODF::StyleTextPropertiesContent>(*(_QWORD *)a1, a4);
  Ofc::TSimpleElemWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(L"text", 314, a1 + 8, a4);
  Ofc::TSimpleElemWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(
    L"fill-character",
    314,
    a1 + 16,
    a4);
  v12 = *(_DWORD *)(a1 + 40);
  if ( v12 )
  {
    v13 = 0;
    while ( v13 < v12 )
    {
      v14 = *(_QWORD *)(a1 + 32) + 16LL * v13;
      v21[0] = &Ofc::TChoiceWriterVisitor<ODF::NumberTextStyleData::NumberAnyTextContent_<0>,ODF::NumberTextStyleData::NumberAnyTextContentWriterTList>::`vftable';
      v21[1] = v14;
      v21[2] = a4;
      v21[3] = off_1801ED1F0;
      v21[4] = &qword_1801ED1E8;
      v22 = 2;
      if ( *(_QWORD *)(v14 + 8) <= 1u )
        Ofc::TChoice<ODF::NumberTextStyleData::NumberAnyTextContentChoiceIDsImpl>::DemandInit(v14);
      v15 = *(_QWORD *)(v14 + 8);
      if ( v15 )
        (*(void (__fastcall **)(_QWORD *))(v15 + 40))(v21);
      ++v13;
      v12 = *(_DWORD *)(a1 + 40);
      if ( v13 >= v12 )
        goto LABEL_23;
    }
    CrashWithRecovery(0x1E892498u, 0);
LABEL_39:
    CrashWithRecovery(0x1E892498u, 0);
    JUMPOUT(0x18006B394LL);
  }
LABEL_23:
  v16 = *(_DWORD *)(a1 + 64);
  if ( v16 )
  {
    v17 = 0;
    while ( (unsigned int)v17 < v16 )
    {
      Ofc::TCompFillWritersHelper<ODF::Map>(*(_QWORD *)(a1 + 56) + 24 * v17, a4);
      v17 = (unsigned int)(v17 + 1);
      v16 = *(_DWORD *)(a1 + 64);
      if ( (unsigned int)v17 >= v16 )
        goto LABEL_27;
    }
    goto LABEL_39;
  }
LABEL_27:
  Ofc::CWriterEmit::EmitEndElement(a3);
  v19 = (Mso::Memory *)(v24 - 12);
  if ( *(_DWORD *)(v24 - 12 + 4)
    && (*(_DWORD *)v19 == 1 || !_InterlockedDecrement((volatile signed __int32 *)v19))
    && v19 )
  {
    Mso::Memory::Free(v19, v18);
  }
  v20 = (Mso::Memory *)(&dword_1801DBD74 - 6);
  if ( *((_DWORD *)&dword_1801DBD74 - 2)
    && (*(_DWORD *)v20 == 1 || !_InterlockedDecrement((volatile signed __int32 *)v20))
    && &dword_1801DBD74 != (const wchar_t *)12 )
  {
    Mso::Memory::Free(v20, v18);
  }
}

```

## disassembly

```asm
0x18006b020  push    rbp
0x18006b022  push    rbx
0x18006b023  push    rsi
0x18006b024  push    rdi
0x18006b025  push    r12
0x18006b027  push    r14
0x18006b029  push    r15
0x18006b02b  mov     rbp, rsp
0x18006b02e  sub     rsp, 60h
0x18006b032  mov     r14, r9
0x18006b035  mov     r12, r8
0x18006b038  mov     rsi, rdx
0x18006b03b  mov     rdi, rcx
0x18006b03e  mov     ebx, 13Fh
0x18006b043  mov     edx, ebx
0x18006b045  mov     rcx, rsi
0x18006b048  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18006b04e  lea     r8, [rdi+48h]
0x18006b052  mov     r9, r14
0x18006b055  mov     edx, ebx
0x18006b057  lea     rcx, aName; "name"
0x18006b05e  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TSelfAdapter@VCVarStr@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBVCVarStr@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(wchar_t const *,int,Ofc::CVarStr const &,Ofc::IWriterParams &)
0x18006b063  lea     r15d, [rbx-5]
0x18006b067  cmp     qword ptr [rdi+50h], 0
0x18006b06c  jz      short loc_18006B07A
0x18006b06e  mov     edx, r15d
0x18006b071  mov     rcx, rsi
0x18006b074  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18006b07a  mov     r9, r14
0x18006b07d  lea     r8, [rdi+50h]
0x18006b081  mov     edx, r15d
0x18006b084  lea     rcx, aLanguage; "language"
0x18006b08b  call    ?Write@?$TAttrWriterHelper@VCellAddress@ODF@@V?$TOptionalAdapter@VCellAddress@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VCellAddress@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::CellAddress,Ofc::TOptionalAdapter<ODF::CellAddress>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::CellAddress> const &,Ofc::IWriterParams &)
0x18006b090  cmp     qword ptr [rdi+58h], 0
0x18006b095  jz      short loc_18006B0A3
0x18006b097  mov     edx, r15d
0x18006b09a  mov     rcx, rsi
0x18006b09d  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18006b0a3  mov     r9, r14
0x18006b0a6  lea     r8, [rdi+58h]
0x18006b0aa  mov     edx, r15d
0x18006b0ad  lea     rcx, aCountry; "country"
0x18006b0b4  call    ?Write@?$TAttrWriterHelper@VCellAddress@ODF@@V?$TOptionalAdapter@VCellAddress@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VCellAddress@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::CellAddress,Ofc::TOptionalAdapter<ODF::CellAddress>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::CellAddress> const &,Ofc::IWriterParams &)
0x18006b0b9  mov     edx, r15d
0x18006b0bc  mov     rcx, rsi
0x18006b0bf  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18006b0c5  lea     rbx, dword_1801DBD74
0x18006b0cc  mov     [rbp+arg_18], rbx
0x18006b0d0  lea     r8, [rdi+60h]
0x18006b0d4  lea     rax, [rbp+arg_18]
0x18006b0d8  mov     [rsp+60h+var_40], rax
0x18006b0dd  mov     r9, r14
0x18006b0e0  mov     edx, r15d
0x18006b0e3  lea     rcx, aTitle; "title"
0x18006b0ea  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TSelfAdapter@VCVarStr@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBVCVarStr@2@AEAVIWriterParams@2@PEBV32@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(wchar_t const *,int,Ofc::CVarStr const &,Ofc::IWriterParams &,Ofc::CVarStr const *)
0x18006b0ef  cmp     qword ptr [rdi+68h], 0
0x18006b0f4  jz      short loc_18006B104
0x18006b0f6  mov     edx, 13Fh
0x18006b0fb  mov     rcx, rsi
0x18006b0fe  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18006b104  mov     r9, r14
0x18006b107  lea     r8, [rdi+68h]
0x18006b10b  mov     edx, 13Fh
0x18006b110  lea     rcx, aVolatile; "volatile"
0x18006b117  call    ?Write@?$TAttrWriterHelper@VOdfBoolean@ODF@@V?$TOptionalAdapter@VOdfBoolean@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VOdfBoolean@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::OdfBoolean,Ofc::TOptionalAdapter<ODF::OdfBoolean>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::OdfBoolean> const &,Ofc::IWriterParams &)
0x18006b11c  mov     r15d, 13Ah
0x18006b122  mov     edx, r15d
0x18006b125  mov     rcx, rsi
0x18006b128  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18006b12e  lea     rdx, a1_0; "1"
0x18006b135  lea     rcx, [rbp+arg_10]; this
0x18006b139  call    ??0CVarStr@Ofc@@QEAA@PEB_W@Z; Ofc::CVarStr::CVarStr(wchar_t const *)
0x18006b13e  nop
0x18006b13f  lea     r8, [rdi+70h]
0x18006b143  lea     rax, [rbp+arg_10]
0x18006b147  mov     [rsp+60h+var_40], rax
0x18006b14c  mov     r9, r14
0x18006b14f  mov     edx, r15d
0x18006b152  lea     rcx, aTransliteratio; "transliteration-format"
0x18006b159  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TSelfAdapter@VCVarStr@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBVCVarStr@2@AEAVIWriterParams@2@PEBV32@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(wchar_t const *,int,Ofc::CVarStr const &,Ofc::IWriterParams &,Ofc::CVarStr const *)
0x18006b15e  cmp     qword ptr [rdi+78h], 0
0x18006b163  jz      short loc_18006B171
0x18006b165  mov     edx, r15d
0x18006b168  mov     rcx, rsi
0x18006b16b  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18006b171  mov     r9, r14
0x18006b174  lea     r8, [rdi+78h]
0x18006b178  mov     edx, 13Ah
0x18006b17d  lea     rcx, aTransliteratio_0; "transliteration-language"
0x18006b184  call    ?Write@?$TAttrWriterHelper@VCellAddress@ODF@@V?$TOptionalAdapter@VCellAddress@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VCellAddress@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::CellAddress,Ofc::TOptionalAdapter<ODF::CellAddress>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::CellAddress> const &,Ofc::IWriterParams &)
0x18006b189  lea     r15, [rdi+80h]
0x18006b190  cmp     qword ptr [r15], 0
0x18006b194  jz      short loc_18006B1A4
0x18006b196  mov     edx, 13Ah
0x18006b19b  mov     rcx, rsi
0x18006b19e  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18006b1a4  mov     r9, r14
0x18006b1a7  mov     r8, r15
0x18006b1aa  mov     r15d, 13Ah
0x18006b1b0  mov     edx, r15d
0x18006b1b3  lea     rcx, aTransliteratio_1; "transliteration-country"
0x18006b1ba  call    ?Write@?$TAttrWriterHelper@VCellAddress@ODF@@V?$TOptionalAdapter@VCellAddress@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VCellAddress@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::CellAddress,Ofc::TOptionalAdapter<ODF::CellAddress>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::CellAddress> const &,Ofc::IWriterParams &)
0x18006b1bf  mov     edx, r15d
0x18006b1c2  mov     rcx, rsi
0x18006b1c5  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18006b1cb  mov     [rbp+arg_0], 0
0x18006b1d2  lea     r8, [rdi+88h]
0x18006b1d9  lea     rax, [rbp+arg_0]
0x18006b1dd  mov     [rsp+60h+var_40], rax
0x18006b1e2  mov     r9, r14
0x18006b1e5  call    ?Write@?$TAttrWriterHelper@W4TransliterationStyle@ODF@@V?$TSelfAdapter@W4TransliterationStyle@ODF@@@Ofc@@$00@Ofc@@SAXPEB_WHAEBW4TransliterationStyle@ODF@@AEAVIWriterParams@2@PEBW434@@Z; Ofc::TAttrWriterHelper<ODF::TransliterationStyle,Ofc::TSelfAdapter<ODF::TransliterationStyle>,1>::Write(wchar_t const *,int,ODF::TransliterationStyle const &,Ofc::IWriterParams &,ODF::TransliterationStyle const *)
0x18006b1ea  lea     r15, [rdi+90h]
0x18006b1f1  cmp     qword ptr [r15], 0
0x18006b1f5  jz      short loc_18006B205
0x18006b1f7  mov     edx, 13Ah
0x18006b1fc  mov     rcx, rsi
0x18006b1ff  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18006b205  mov     r9, r14
0x18006b208  mov     r8, r15
0x18006b20b  call    ?Write@?$TAttrWriterHelper@VLanguage@ODF@@V?$TOptionalAdapter@VLanguage@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VLanguage@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::Language,Ofc::TOptionalAdapter<ODF::Language>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::Language> const &,Ofc::IWriterParams &)
0x18006b210  mov     rax, [r12]
0x18006b214  mov     rdx, [r14+10h]
0x18006b218  mov     rcx, r12
0x18006b21b  mov     rax, [rax]
0x18006b21e  call    cs:__guard_dispatch_icall_fptr
0x18006b224  mov     rcx, [rdi]
0x18006b227  test    rcx, rcx
0x18006b22a  jz      short loc_18006B234
0x18006b22c  mov     rdx, r14
0x18006b22f  call    ??$TCompFillWritersHelper@VStyleTextPropertiesContent@ODF@@@Ofc@@YAXAEBVStyleTextPropertiesContent@ODF@@AEAVIWriterParams@0@HPEB_W@Z; Ofc::TCompFillWritersHelper<ODF::StyleTextPropertiesContent>(ODF::StyleTextPropertiesContent const &,Ofc::IWriterParams &,int,wchar_t const *)
0x18006b234  lea     r8, [rdi+8]
0x18006b238  mov     r9, r14
0x18006b23b  mov     esi, 13Ah
0x18006b240  mov     edx, esi
0x18006b242  lea     rcx, aText; "text"
0x18006b249  call    ?Write@?$TSimpleElemWriterHelper@VCVarStr@Ofc@@V?$TOptionalAdapter@VCVarStr@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VCVarStr@Ofc@@@2@AEAVIWriterParams@2@PEBVCVarStr@2@@Z; Ofc::TSimpleElemWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::CVarStr> const &,Ofc::IWriterParams &,Ofc::CVarStr const *)
0x18006b24e  lea     r8, [rdi+10h]
0x18006b252  mov     r9, r14
0x18006b255  mov     edx, esi
0x18006b257  lea     rcx, aFillCharacter; "fill-character"
0x18006b25e  call    ?Write@?$TSimpleElemWriterHelper@VCVarStr@Ofc@@V?$TOptionalAdapter@VCVarStr@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VCVarStr@Ofc@@@2@AEAVIWriterParams@2@PEBVCVarStr@2@@Z; Ofc::TSimpleElemWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::CVarStr> const &,Ofc::IWriterParams &,Ofc::CVarStr const *)
0x18006b263  mov     eax, [rdi+28h]
0x18006b266  test    eax, eax
0x18006b268  jz      short loc_18006B2E2
0x18006b26a  xor     r15d, r15d
0x18006b26d  cmp     r15d, eax
0x18006b270  jnb     loc_18006B379
0x18006b276  mov     esi, r15d
0x18006b279  shl     rsi, 4
0x18006b27d  add     rsi, [rdi+20h]
0x18006b281  lea     rax, ??_7?$TChoiceWriterVisitor@V?$NumberAnyTextContent_@$0A@@NumberTextStyleData@ODF@@VNumberAnyTextContentWriterTList@23@@Ofc@@6B@; const Ofc::TChoiceWriterVisitor<ODF::NumberTextStyleData::NumberAnyTextContent_<0>,ODF::NumberTextStyleData::NumberAnyTextContentWriterTList>::`vftable'
0x18006b288  mov     [rbp+var_30], rax
0x18006b28c  mov     [rbp+var_28], rsi
0x18006b290  mov     [rbp+var_20], r14
0x18006b294  lea     rax, off_1801ED1F0; "text-content"
0x18006b29b  mov     [rbp+var_18], rax
0x18006b29f  lea     rax, qword_1801ED1E8
0x18006b2a6  mov     [rbp+var_10], rax
0x18006b2aa  mov     [rbp+var_8], 2
0x18006b2b1  cmp     qword ptr [rsi+8], 1
0x18006b2b6  ja      short loc_18006B2C0
0x18006b2b8  mov     rcx, rsi
0x18006b2bb  call    ?DemandInit@?$TChoice@VNumberAnyTextContentChoiceIDsImpl@NumberTextStyleData@ODF@@@Ofc@@AEBAXXZ; Ofc::TChoice<ODF::NumberTextStyleData::NumberAnyTextContentChoiceIDsImpl>::DemandInit(void)
0x18006b2c0  mov     rax, [rsi+8]
0x18006b2c4  test    rax, rax
0x18006b2c7  jz      short loc_18006B2D7
0x18006b2c9  lea     rcx, [rbp+var_30]
0x18006b2cd  mov     rax, [rax+28h]
0x18006b2d1  call    cs:__guard_dispatch_icall_fptr
0x18006b2d7  inc     r15d
0x18006b2da  mov     eax, [rdi+28h]
0x18006b2dd  cmp     r15d, eax
0x18006b2e0  jb      short loc_18006B26D
0x18006b2e2  mov     eax, [rdi+40h]
0x18006b2e5  test    eax, eax
0x18006b2e7  jz      short loc_18006B310
0x18006b2e9  xor     esi, esi
0x18006b2eb  cmp     esi, eax
0x18006b2ed  jnb     loc_18006B387
0x18006b2f3  lea     rcx, [rsi+rsi*2]
0x18006b2f7  mov     rax, [rdi+38h]
0x18006b2fb  lea     rcx, [rax+rcx*8]
0x18006b2ff  mov     rdx, r14
0x18006b302  call    ??$TCompFillWritersHelper@VMap@ODF@@@Ofc@@YAXAEBVMap@ODF@@AEAVIWriterParams@0@HPEB_W@Z; Ofc::TCompFillWritersHelper<ODF::Map>(ODF::Map const &,Ofc::IWriterParams &,int,wchar_t const *)
0x18006b307  inc     esi
0x18006b309  mov     eax, [rdi+40h]
0x18006b30c  cmp     esi, eax
0x18006b30e  jb      short loc_18006B2EB
0x18006b310  mov     rcx, r12
0x18006b313  call    cs:__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ; Ofc::CWriterEmit::EmitEndElement(void)
0x18006b319  nop
0x18006b31a  mov     rcx, [rbp+arg_10]
0x18006b31e  add     rcx, 0FFFFFFFFFFFFFFF4h
0x18006b322  or      edi, 0FFFFFFFFh
0x18006b325  cmp     dword ptr [rcx+4], 0
0x18006b329  jz      short loc_18006B346
0x18006b32b  cmp     dword ptr [rcx], 1
0x18006b32e  jz      short loc_18006B33A
0x18006b330  mov     eax, edi
0x18006b332  lock xadd [rcx], eax
0x18006b336  add     eax, edi
0x18006b338  jnz     short loc_18006B346
0x18006b33a  test    rcx, rcx
0x18006b33d  jz      short loc_18006B346
0x18006b33f  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18006b345  nop
0x18006b346  lea     rcx, [rbx-0Ch]
0x18006b34a  cmp     dword ptr [rcx+4], 0
0x18006b34e  jz      short loc_18006B36A
0x18006b350  cmp     dword ptr [rcx], 1
0x18006b353  jz      short loc_18006B35F
0x18006b355  mov     eax, edi
0x18006b357  lock xadd [rcx], eax
0x18006b35b  add     eax, edi
0x18006b35d  jnz     short loc_18006B36A
0x18006b35f  test    rcx, rcx
0x18006b362  jz      short loc_18006B36A
0x18006b364  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18006b36a  add     rsp, 60h
0x18006b36e  pop     r15
0x18006b370  pop     r14
0x18006b372  pop     r12
0x18006b374  pop     rdi
0x18006b375  pop     rsi
0x18006b376  pop     rbx
0x18006b377  pop     rbp
0x18006b378  retn
0x18006b379  xor     edx, edx
0x18006b37b  mov     ecx, 1E892498h
0x18006b380  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18006b386  nop
0x18006b387  xor     edx, edx
0x18006b389  mov     ecx, 1E892498h
0x18006b38e  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
