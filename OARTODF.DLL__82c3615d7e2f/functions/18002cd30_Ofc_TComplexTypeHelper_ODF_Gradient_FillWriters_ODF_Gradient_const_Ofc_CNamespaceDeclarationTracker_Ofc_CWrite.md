# Ofc::TComplexTypeHelper<ODF::Gradient>::FillWriters(ODF::Gradient const &,Ofc::CNamespaceDeclarationTracker &,Ofc::CWriterEmit &,Ofc::IWriterParams &)

- ea: `0x18002cd30`
- end: `0x18002cf40`
- name: `?FillWriters@?$TComplexTypeHelper@VGradient@ODF@@@Ofc@@SAXAEBVGradient@ODF@@AEAVCNamespaceDeclarationTracker@2@AEAVCWriterEmit@2@AEAVIWriterParams@2@@Z`
- size: `528`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180077c34`

## callees

- `0x18001dcf4`
- `0x18001dd94`
- `0x180025ef4`
- `0x18002cd30`
- `0x18002e2b0`
- `0x18002e354`
- `0x18002e48c`
- `0x18002e530`
- `0x1801a80e0`

## import_xrefs

- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18002cd60`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18002cd81`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18002cdb9`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18002cdd8`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18002ce01`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18002ce2a`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18002ce50`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18002ce79`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18002cea2`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18002cecb`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18002cef1`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18002cd60`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18002cd81`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18002cdb9`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18002cdd8`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18002ce01`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18002ce2a`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18002ce50`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18002ce79`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18002cea2`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18002cecb`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18002cef1`
- `mso40uiWin32Client!__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ` at `0x18002cf20`
- `mso40uiWin32Client!__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ` at `0x18002cf20`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Ofc::TComplexTypeHelper<ODF::Gradient>::FillWriters(
        _QWORD *a1,
        Ofc::CNamespaceDeclarationTracker *a2,
        Ofc::CWriterEmit *a3,
        __int64 a4)
{
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rdx
  const wchar_t *v13; // [rsp+50h] [rbp+8h] BYREF

  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 307);
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(L"name", 307, a1, a4);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 307);
  v13 = &dword_1801DBD74;
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(
    (unsigned int)L"display-name",
    307,
    (_DWORD)a1 + 8,
    a4,
    (__int64)&v13);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 307);
  Ofc::TAttrWriterHelper<enum ODF::GradientStyle,Ofc::TSelfAdapter<enum ODF::GradientStyle>,1>::Write(
    v9,
    v8,
    a1 + 2,
    a4);
  if ( a1[3] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 307);
  Ofc::TAttrWriterHelper<ODF::Percent,Ofc::TOptionalAdapter<ODF::Percent>,0>::Write(L"cx", 307, a1 + 3, a4);
  if ( a1[4] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 307);
  Ofc::TAttrWriterHelper<ODF::Percent,Ofc::TOptionalAdapter<ODF::Percent>,0>::Write(L"cy", 307, a1 + 4, a4);
  if ( a1[5] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 307);
  Ofc::TAttrWriterHelper<ODF::Angle,Ofc::TOptionalAdapter<ODF::Angle>,0>::Write(L"angle", v10, a1 + 5, a4);
  if ( a1[6] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 307);
  Ofc::TAttrWriterHelper<ODF::Percent,Ofc::TOptionalAdapter<ODF::Percent>,0>::Write(L"border", 307, a1 + 6, a4);
  if ( a1[7] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 307);
  Ofc::TAttrWriterHelper<ODF::Color,Ofc::TOptionalAdapter<ODF::Color>,0>::Write(L"start-color", 307, a1 + 7, a4);
  if ( a1[8] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 307);
  Ofc::TAttrWriterHelper<ODF::Color,Ofc::TOptionalAdapter<ODF::Color>,0>::Write(L"end-color", 307, a1 + 8, a4);
  if ( a1[9] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 307);
  Ofc::TAttrWriterHelper<ODF::ZeroToHundredPercent,Ofc::TOptionalAdapter<ODF::ZeroToHundredPercent>,0>::Write(
    L"start-intensity",
    v11,
    a1 + 9,
    a4);
  if ( a1[10] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 307);
  Ofc::TAttrWriterHelper<ODF::ZeroToHundredPercent,Ofc::TOptionalAdapter<ODF::ZeroToHundredPercent>,0>::Write(
    L"end-intensity",
    v12,
    a1 + 10,
    a4);
  (**(void (__fastcall ***)(Ofc::CWriterEmit *, _QWORD))a3)(a3, *(_QWORD *)(a4 + 16));
  Ofc::CWriterEmit::EmitEndElement(a3);
}

```

## disassembly

```asm
0x18002cd30  mov     [rsp+arg_8], rbx
0x18002cd35  mov     [rsp+arg_10], rbp
0x18002cd3a  mov     [rsp+arg_18], rsi
0x18002cd3f  push    rdi
0x18002cd40  push    r14
0x18002cd42  push    r15
0x18002cd44  sub     rsp, 30h
0x18002cd48  mov     rdi, r9
0x18002cd4b  mov     r14, r8
0x18002cd4e  mov     rbx, rdx
0x18002cd51  mov     rsi, rcx
0x18002cd54  mov     r15d, 133h
0x18002cd5a  mov     edx, r15d
0x18002cd5d  mov     rcx, rbx
0x18002cd60  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18002cd66  mov     r9, rdi
0x18002cd69  mov     r8, rsi
0x18002cd6c  mov     edx, r15d
0x18002cd6f  lea     rcx, aName; "name"
0x18002cd76  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TSelfAdapter@VCVarStr@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBVCVarStr@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(wchar_t const *,int,Ofc::CVarStr const &,Ofc::IWriterParams &)
0x18002cd7b  mov     edx, r15d
0x18002cd7e  mov     rcx, rbx
0x18002cd81  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18002cd87  lea     rax, dword_1801DBD74
0x18002cd8e  mov     [rsp+48h+arg_0], rax
0x18002cd93  lea     r8, [rsi+8]
0x18002cd97  lea     rax, [rsp+48h+arg_0]
0x18002cd9c  mov     [rsp+48h+var_28], rax
0x18002cda1  mov     r9, rdi
0x18002cda4  mov     edx, r15d
0x18002cda7  lea     rcx, aDisplayName; "display-name"
0x18002cdae  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TSelfAdapter@VCVarStr@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBVCVarStr@2@AEAVIWriterParams@2@PEBV32@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(wchar_t const *,int,Ofc::CVarStr const &,Ofc::IWriterParams &,Ofc::CVarStr const *)
0x18002cdb3  mov     edx, r15d
0x18002cdb6  mov     rcx, rbx
0x18002cdb9  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18002cdbf  lea     r8, [rsi+10h]
0x18002cdc3  mov     r9, rdi
0x18002cdc6  call    ?Write@?$TAttrWriterHelper@W4GradientStyle@ODF@@V?$TSelfAdapter@W4GradientStyle@ODF@@@Ofc@@$00@Ofc@@SAXPEB_WHAEBW4GradientStyle@ODF@@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::GradientStyle,Ofc::TSelfAdapter<ODF::GradientStyle>,1>::Write(wchar_t const *,int,ODF::GradientStyle const &,Ofc::IWriterParams &)
0x18002cdcb  cmp     qword ptr [rsi+18h], 0
0x18002cdd0  jz      short loc_18002CDDE
0x18002cdd2  mov     edx, r15d
0x18002cdd5  mov     rcx, rbx
0x18002cdd8  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18002cdde  mov     r9, rdi
0x18002cde1  lea     r8, [rsi+18h]
0x18002cde5  mov     edx, r15d
0x18002cde8  lea     rcx, aCx; "cx"
0x18002cdef  call    ?Write@?$TAttrWriterHelper@VPercent@ODF@@V?$TOptionalAdapter@VPercent@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VPercent@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::Percent,Ofc::TOptionalAdapter<ODF::Percent>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::Percent> const &,Ofc::IWriterParams &)
0x18002cdf4  cmp     qword ptr [rsi+20h], 0
0x18002cdf9  jz      short loc_18002CE07
0x18002cdfb  mov     edx, r15d
0x18002cdfe  mov     rcx, rbx
0x18002ce01  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18002ce07  mov     r9, rdi
0x18002ce0a  lea     r8, [rsi+20h]
0x18002ce0e  mov     edx, r15d
0x18002ce11  lea     rcx, aCy; "cy"
0x18002ce18  call    ?Write@?$TAttrWriterHelper@VPercent@ODF@@V?$TOptionalAdapter@VPercent@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VPercent@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::Percent,Ofc::TOptionalAdapter<ODF::Percent>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::Percent> const &,Ofc::IWriterParams &)
0x18002ce1d  cmp     qword ptr [rsi+28h], 0
0x18002ce22  jz      short loc_18002CE30
0x18002ce24  mov     edx, r15d
0x18002ce27  mov     rcx, rbx
0x18002ce2a  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18002ce30  mov     r9, rdi
0x18002ce33  lea     r8, [rsi+28h]
0x18002ce37  lea     rcx, aAngle; "angle"
0x18002ce3e  call    ?Write@?$TAttrWriterHelper@VAngle@ODF@@V?$TOptionalAdapter@VAngle@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VAngle@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::Angle,Ofc::TOptionalAdapter<ODF::Angle>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::Angle> const &,Ofc::IWriterParams &)
0x18002ce43  cmp     qword ptr [rsi+30h], 0
0x18002ce48  jz      short loc_18002CE56
0x18002ce4a  mov     edx, r15d
0x18002ce4d  mov     rcx, rbx
0x18002ce50  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18002ce56  mov     r9, rdi
0x18002ce59  lea     r8, [rsi+30h]
0x18002ce5d  mov     edx, r15d
0x18002ce60  lea     rcx, aBorder; "border"
0x18002ce67  call    ?Write@?$TAttrWriterHelper@VPercent@ODF@@V?$TOptionalAdapter@VPercent@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VPercent@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::Percent,Ofc::TOptionalAdapter<ODF::Percent>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::Percent> const &,Ofc::IWriterParams &)
0x18002ce6c  cmp     qword ptr [rsi+38h], 0
0x18002ce71  jz      short loc_18002CE7F
0x18002ce73  mov     edx, r15d
0x18002ce76  mov     rcx, rbx
0x18002ce79  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18002ce7f  mov     r9, rdi
0x18002ce82  lea     r8, [rsi+38h]
0x18002ce86  mov     edx, r15d
0x18002ce89  lea     rcx, aStartColor; "start-color"
0x18002ce90  call    ?Write@?$TAttrWriterHelper@VColor@ODF@@V?$TOptionalAdapter@VColor@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VColor@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::Color,Ofc::TOptionalAdapter<ODF::Color>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::Color> const &,Ofc::IWriterParams &)
0x18002ce95  cmp     qword ptr [rsi+40h], 0
0x18002ce9a  jz      short loc_18002CEA8
0x18002ce9c  mov     edx, r15d
0x18002ce9f  mov     rcx, rbx
0x18002cea2  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18002cea8  mov     r9, rdi
0x18002ceab  lea     r8, [rsi+40h]
0x18002ceaf  mov     edx, r15d
0x18002ceb2  lea     rcx, aEndColor; "end-color"
0x18002ceb9  call    ?Write@?$TAttrWriterHelper@VColor@ODF@@V?$TOptionalAdapter@VColor@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VColor@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::Color,Ofc::TOptionalAdapter<ODF::Color>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::Color> const &,Ofc::IWriterParams &)
0x18002cebe  cmp     qword ptr [rsi+48h], 0
0x18002cec3  jz      short loc_18002CED1
0x18002cec5  mov     edx, r15d
0x18002cec8  mov     rcx, rbx
0x18002cecb  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18002ced1  mov     r9, rdi
0x18002ced4  lea     r8, [rsi+48h]
0x18002ced8  lea     rcx, aStartIntensity; "start-intensity"
0x18002cedf  call    ?Write@?$TAttrWriterHelper@VZeroToHundredPercent@ODF@@V?$TOptionalAdapter@VZeroToHundredPercent@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VZeroToHundredPercent@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::ZeroToHundredPercent,Ofc::TOptionalAdapter<ODF::ZeroToHundredPercent>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::ZeroToHundredPercent> const &,Ofc::IWriterParams &)
0x18002cee4  cmp     qword ptr [rsi+50h], 0
0x18002cee9  jz      short loc_18002CEF7
0x18002ceeb  mov     edx, r15d
0x18002ceee  mov     rcx, rbx
0x18002cef1  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18002cef7  mov     r9, rdi
0x18002cefa  lea     r8, [rsi+50h]
0x18002cefe  lea     rcx, aEndIntensity; "end-intensity"
0x18002cf05  call    ?Write@?$TAttrWriterHelper@VZeroToHundredPercent@ODF@@V?$TOptionalAdapter@VZeroToHundredPercent@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VZeroToHundredPercent@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::ZeroToHundredPercent,Ofc::TOptionalAdapter<ODF::ZeroToHundredPercent>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::ZeroToHundredPercent> const &,Ofc::IWriterParams &)
0x18002cf0a  mov     rax, [r14]
0x18002cf0d  mov     rdx, [rdi+10h]
0x18002cf11  mov     rcx, r14
0x18002cf14  mov     rax, [rax]
0x18002cf17  call    cs:__guard_dispatch_icall_fptr
0x18002cf1d  mov     rcx, r14
0x18002cf20  call    cs:__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ; Ofc::CWriterEmit::EmitEndElement(void)
0x18002cf26  nop
0x18002cf27  mov     rbx, [rsp+48h+arg_8]
0x18002cf2c  mov     rbp, [rsp+48h+arg_10]
0x18002cf31  mov     rsi, [rsp+48h+arg_18]
0x18002cf36  add     rsp, 30h
0x18002cf3a  pop     r15
0x18002cf3c  pop     r14
0x18002cf3e  pop     rdi
0x18002cf3f  retn
```
