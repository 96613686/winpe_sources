# Ofc::TComplexTypeHelper<ODF::TableSevered>::FillWriters(ODF::TableSevered const &,Ofc::CNamespaceDeclarationTracker &,Ofc::CWriterEmit &,Ofc::IWriterParams &)

- ea: `0x1800e2f88`
- end: `0x1800e327e`
- name: `?FillWriters@?$TComplexTypeHelper@VTableSevered@ODF@@@Ofc@@SAXAEBVTableSevered@ODF@@AEAVCNamespaceDeclarationTracker@2@AEAVCWriterEmit@2@AEAVIWriterParams@2@@Z`
- size: `758`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005891c`

## callees

- `0x18001dcf4`
- `0x18001dd94`
- `0x18002603c`
- `0x1800e1ef4`
- `0x1800e1fe8`
- `0x1800e2f88`
- `0x1801a80e0`

## import_xrefs

- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800e2fb9`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800e2fef`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800e3011`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800e3047`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800e3070`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800e3099`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800e30c2`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800e30eb`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800e3114`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800e2fb9`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800e2fef`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800e3011`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800e3047`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800e3070`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800e3099`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800e30c2`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800e30eb`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800e3114`
- `mso40uiWin32Client!__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ` at `0x1800e3242`
- `mso40uiWin32Client!__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ` at `0x1800e3242`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800e3269`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800e3277`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800e3269`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800e3277`

## string_xrefs

- `0x1800e302e`: `template-name`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Ofc::TComplexTypeHelper<ODF::TableSevered>::FillWriters(
        __int64 a1,
        Ofc::CNamespaceDeclarationTracker *a2,
        Ofc::CWriterEmit *a3,
        __int64 a4)
{
  unsigned int v8; // r14d
  __int64 v9; // rdi
  __int64 v10; // rax
  unsigned int v11; // eax
  unsigned int v12; // r14d
  __int64 v13; // rdi
  __int64 v14; // rax
  void **v15; // [rsp+30h] [rbp-30h] BYREF
  __int64 v16; // [rsp+38h] [rbp-28h]
  __int64 v17; // [rsp+40h] [rbp-20h]
  wchar_t **v18; // [rsp+48h] [rbp-18h]
  __int64 *v19; // [rsp+50h] [rbp-10h]
  int v20; // [rsp+58h] [rbp-8h]
  const wchar_t *v21; // [rsp+90h] [rbp+30h] BYREF
  const wchar_t *v22; // [rsp+A0h] [rbp+40h] BYREF

  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 320);
  v21 = &dword_1801DBD74;
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(
    (unsigned int)L"name",
    320,
    a1 + 48,
    a4,
    (__int64)&v21);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 320);
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(L"style-name", 320, a1 + 56, a4);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 320);
  v22 = &dword_1801DBD74;
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(
    (unsigned int)L"template-name",
    320,
    a1 + 64,
    a4,
    (__int64)&v22);
  if ( *(_QWORD *)(a1 + 72) )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 320);
  Ofc::TAttrWriterHelper<ODF::OdfBoolean,Ofc::TOptionalAdapter<ODF::OdfBoolean>,0>::Write(
    L"use-banding-columns-styles",
    320,
    a1 + 72,
    a4);
  if ( *(_QWORD *)(a1 + 80) )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 320);
  Ofc::TAttrWriterHelper<ODF::OdfBoolean,Ofc::TOptionalAdapter<ODF::OdfBoolean>,0>::Write(
    L"use-banding-rows-styles",
    320,
    a1 + 80,
    a4);
  if ( *(_QWORD *)(a1 + 88) )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 320);
  Ofc::TAttrWriterHelper<ODF::OdfBoolean,Ofc::TOptionalAdapter<ODF::OdfBoolean>,0>::Write(
    L"use-first-column-styles",
    320,
    a1 + 88,
    a4);
  if ( *(_QWORD *)(a1 + 96) )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 320);
  Ofc::TAttrWriterHelper<ODF::OdfBoolean,Ofc::TOptionalAdapter<ODF::OdfBoolean>,0>::Write(
    L"use-first-row-styles",
    320,
    a1 + 96,
    a4);
  if ( *(_QWORD *)(a1 + 104) )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 320);
  Ofc::TAttrWriterHelper<ODF::OdfBoolean,Ofc::TOptionalAdapter<ODF::OdfBoolean>,0>::Write(
    L"use-last-column-styles",
    320,
    a1 + 104,
    a4);
  if ( *(_QWORD *)(a1 + 112) )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 320);
  Ofc::TAttrWriterHelper<ODF::OdfBoolean,Ofc::TOptionalAdapter<ODF::OdfBoolean>,0>::Write(
    L"use-last-row-styles",
    320,
    a1 + 112,
    a4);
  (**(void (__fastcall ***)(Ofc::CWriterEmit *, _QWORD))a3)(a3, *(_QWORD *)(a4 + 16));
  if ( *(_DWORD *)(a1 + 16) )
  {
    v8 = 0;
    while ( v8 < *(_DWORD *)(a1 + 16) )
    {
      v9 = *(_QWORD *)(a1 + 8) + 16LL * v8;
      v15 = &Ofc::TChoiceWriterVisitor<ODF::TableColumnsAndGroupsChoice_<0>,ODF::TableColumnsAndGroupsChoiceWriterTList>::`vftable';
      v16 = v9;
      v17 = a4;
      v18 = off_180205018;
      v19 = qword_180205038;
      v20 = 4;
      if ( *(_QWORD *)(v9 + 8) <= 1u )
        Ofc::TChoice<ODF::TableColumnsAndGroupsChoiceChoiceIDsImpl>::DemandInit(v9);
      v10 = *(_QWORD *)(v9 + 8);
      if ( v10 )
        (*(void (__fastcall **)(void ***))(v10 + 40))(&v15);
      if ( ++v8 >= *(_DWORD *)(a1 + 16) )
        goto LABEL_21;
    }
    CrashWithRecovery(0x1E892498u, 0);
LABEL_31:
    CrashWithRecovery(0x1E892498u, 0);
    JUMPOUT(0x1800E327DLL);
  }
LABEL_21:
  v11 = *(_DWORD *)(a1 + 40);
  if ( v11 )
  {
    v12 = 0;
    while ( v12 < v11 )
    {
      v13 = *(_QWORD *)(a1 + 32) + 16LL * v12;
      v15 = &Ofc::TChoiceWriterVisitor<ODF::TableRowsAndGroupsChoice_<0>,ODF::TableRowsAndGroupsChoiceWriterTList>::`vftable';
      v16 = v13;
      v17 = a4;
      v18 = off_180204FC0;
      v19 = qword_180204FE8;
      v20 = 5;
      if ( *(_QWORD *)(v13 + 8) <= 1u )
        Ofc::TChoice<ODF::TableRowsAndGroupsChoiceChoiceIDsImpl>::DemandInit(v13);
      v14 = *(_QWORD *)(v13 + 8);
      if ( v14 )
        (*(void (__fastcall **)(void ***))(v14 + 40))(&v15);
      ++v12;
      v11 = *(_DWORD *)(a1 + 40);
      if ( v12 >= v11 )
        goto LABEL_29;
    }
    goto LABEL_31;
  }
LABEL_29:
  Ofc::CWriterEmit::EmitEndElement(a3);
}

```

## disassembly

```asm
0x1800e2f88  mov     [rsp-28h+arg_8], rbx
0x1800e2f8d  mov     [rsp-28h+arg_18], rsi
0x1800e2f92  push    rbp
0x1800e2f93  push    rdi
0x1800e2f94  push    r12
0x1800e2f96  push    r14
0x1800e2f98  push    r15
0x1800e2f9a  mov     rbp, rsp
0x1800e2f9d  sub     rsp, 60h
0x1800e2fa1  mov     rsi, r9
0x1800e2fa4  mov     r15, r8
0x1800e2fa7  mov     rdi, rdx
0x1800e2faa  mov     rbx, rcx
0x1800e2fad  mov     r12d, 140h
0x1800e2fb3  mov     edx, r12d
0x1800e2fb6  mov     rcx, rdi
0x1800e2fb9  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800e2fbf  lea     r14, dword_1801DBD74
0x1800e2fc6  mov     [rbp+arg_0], r14
0x1800e2fca  lea     r8, [rbx+30h]
0x1800e2fce  lea     rax, [rbp+arg_0]
0x1800e2fd2  mov     [rsp+60h+var_40], rax
0x1800e2fd7  mov     r9, rsi
0x1800e2fda  mov     edx, r12d
0x1800e2fdd  lea     rcx, aName; "name"
0x1800e2fe4  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TSelfAdapter@VCVarStr@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBVCVarStr@2@AEAVIWriterParams@2@PEBV32@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(wchar_t const *,int,Ofc::CVarStr const &,Ofc::IWriterParams &,Ofc::CVarStr const *)
0x1800e2fe9  mov     edx, r12d
0x1800e2fec  mov     rcx, rdi
0x1800e2fef  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800e2ff5  lea     r8, [rbx+38h]
0x1800e2ff9  mov     r9, rsi
0x1800e2ffc  mov     edx, r12d
0x1800e2fff  lea     rcx, aStyleName; "style-name"
0x1800e3006  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TSelfAdapter@VCVarStr@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBVCVarStr@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(wchar_t const *,int,Ofc::CVarStr const &,Ofc::IWriterParams &)
0x1800e300b  mov     edx, r12d
0x1800e300e  mov     rcx, rdi
0x1800e3011  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800e3017  mov     [rbp+arg_10], r14
0x1800e301b  lea     r8, [rbx+40h]
0x1800e301f  lea     rax, [rbp+arg_10]
0x1800e3023  mov     [rsp+60h+var_40], rax
0x1800e3028  mov     r9, rsi
0x1800e302b  mov     edx, r12d
0x1800e302e  lea     rcx, aTemplateName; "template-name"
0x1800e3035  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TSelfAdapter@VCVarStr@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBVCVarStr@2@AEAVIWriterParams@2@PEBV32@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(wchar_t const *,int,Ofc::CVarStr const &,Ofc::IWriterParams &,Ofc::CVarStr const *)
0x1800e303a  cmp     qword ptr [rbx+48h], 0
0x1800e303f  jz      short loc_1800E304D
0x1800e3041  mov     edx, r12d
0x1800e3044  mov     rcx, rdi
0x1800e3047  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800e304d  mov     r9, rsi
0x1800e3050  lea     r8, [rbx+48h]
0x1800e3054  mov     edx, r12d
0x1800e3057  lea     rcx, aUseBandingColu; "use-banding-columns-styles"
0x1800e305e  call    ?Write@?$TAttrWriterHelper@VOdfBoolean@ODF@@V?$TOptionalAdapter@VOdfBoolean@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VOdfBoolean@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::OdfBoolean,Ofc::TOptionalAdapter<ODF::OdfBoolean>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::OdfBoolean> const &,Ofc::IWriterParams &)
0x1800e3063  cmp     qword ptr [rbx+50h], 0
0x1800e3068  jz      short loc_1800E3076
0x1800e306a  mov     edx, r12d
0x1800e306d  mov     rcx, rdi
0x1800e3070  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800e3076  mov     r9, rsi
0x1800e3079  lea     r8, [rbx+50h]
0x1800e307d  mov     edx, r12d
0x1800e3080  lea     rcx, aUseBandingRows; "use-banding-rows-styles"
0x1800e3087  call    ?Write@?$TAttrWriterHelper@VOdfBoolean@ODF@@V?$TOptionalAdapter@VOdfBoolean@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VOdfBoolean@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::OdfBoolean,Ofc::TOptionalAdapter<ODF::OdfBoolean>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::OdfBoolean> const &,Ofc::IWriterParams &)
0x1800e308c  cmp     qword ptr [rbx+58h], 0
0x1800e3091  jz      short loc_1800E309F
0x1800e3093  mov     edx, r12d
0x1800e3096  mov     rcx, rdi
0x1800e3099  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800e309f  mov     r9, rsi
0x1800e30a2  lea     r8, [rbx+58h]
0x1800e30a6  mov     edx, r12d
0x1800e30a9  lea     rcx, aUseFirstColumn; "use-first-column-styles"
0x1800e30b0  call    ?Write@?$TAttrWriterHelper@VOdfBoolean@ODF@@V?$TOptionalAdapter@VOdfBoolean@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VOdfBoolean@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::OdfBoolean,Ofc::TOptionalAdapter<ODF::OdfBoolean>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::OdfBoolean> const &,Ofc::IWriterParams &)
0x1800e30b5  cmp     qword ptr [rbx+60h], 0
0x1800e30ba  jz      short loc_1800E30C8
0x1800e30bc  mov     edx, r12d
0x1800e30bf  mov     rcx, rdi
0x1800e30c2  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800e30c8  mov     r9, rsi
0x1800e30cb  lea     r8, [rbx+60h]
0x1800e30cf  mov     edx, r12d
0x1800e30d2  lea     rcx, aUseFirstRowSty; "use-first-row-styles"
0x1800e30d9  call    ?Write@?$TAttrWriterHelper@VOdfBoolean@ODF@@V?$TOptionalAdapter@VOdfBoolean@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VOdfBoolean@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::OdfBoolean,Ofc::TOptionalAdapter<ODF::OdfBoolean>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::OdfBoolean> const &,Ofc::IWriterParams &)
0x1800e30de  cmp     qword ptr [rbx+68h], 0
0x1800e30e3  jz      short loc_1800E30F1
0x1800e30e5  mov     edx, r12d
0x1800e30e8  mov     rcx, rdi
0x1800e30eb  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800e30f1  mov     r9, rsi
0x1800e30f4  lea     r8, [rbx+68h]
0x1800e30f8  mov     edx, r12d
0x1800e30fb  lea     rcx, aUseLastColumnS; "use-last-column-styles"
0x1800e3102  call    ?Write@?$TAttrWriterHelper@VOdfBoolean@ODF@@V?$TOptionalAdapter@VOdfBoolean@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VOdfBoolean@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::OdfBoolean,Ofc::TOptionalAdapter<ODF::OdfBoolean>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::OdfBoolean> const &,Ofc::IWriterParams &)
0x1800e3107  cmp     qword ptr [rbx+70h], 0
0x1800e310c  jz      short loc_1800E311A
0x1800e310e  mov     edx, r12d
0x1800e3111  mov     rcx, rdi
0x1800e3114  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800e311a  mov     r9, rsi
0x1800e311d  lea     r8, [rbx+70h]
0x1800e3121  mov     edx, r12d
0x1800e3124  lea     rcx, aUseLastRowStyl; "use-last-row-styles"
0x1800e312b  call    ?Write@?$TAttrWriterHelper@VOdfBoolean@ODF@@V?$TOptionalAdapter@VOdfBoolean@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VOdfBoolean@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::OdfBoolean,Ofc::TOptionalAdapter<ODF::OdfBoolean>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::OdfBoolean> const &,Ofc::IWriterParams &)
0x1800e3130  mov     rax, [r15]
0x1800e3133  mov     rdx, [rsi+10h]
0x1800e3137  mov     rcx, r15
0x1800e313a  mov     rax, [rax]
0x1800e313d  call    cs:__guard_dispatch_icall_fptr
0x1800e3143  cmp     dword ptr [rbx+10h], 0
0x1800e3147  jbe     short loc_1800E31C0
0x1800e3149  xor     r14d, r14d
0x1800e314c  cmp     r14d, [rbx+10h]
0x1800e3150  jnb     loc_1800E3262
0x1800e3156  mov     edi, r14d
0x1800e3159  shl     rdi, 4
0x1800e315d  add     rdi, [rbx+8]
0x1800e3161  lea     rax, ??_7?$TChoiceWriterVisitor@V?$TableColumnsAndGroupsChoice_@$0A@@ODF@@VTableColumnsAndGroupsChoiceWriterTList@2@@Ofc@@6B@; const Ofc::TChoiceWriterVisitor<ODF::TableColumnsAndGroupsChoice_<0>,ODF::TableColumnsAndGroupsChoiceWriterTList>::`vftable'
0x1800e3168  mov     [rbp+var_30], rax
0x1800e316c  mov     [rbp+var_28], rdi
0x1800e3170  mov     [rbp+var_20], rsi
0x1800e3174  lea     rax, off_180205018; "table-columns"
0x1800e317b  mov     [rbp+var_18], rax
0x1800e317f  lea     rax, qword_180205038
0x1800e3186  mov     [rbp+var_10], rax
0x1800e318a  mov     [rbp+var_8], 4
0x1800e3191  cmp     qword ptr [rdi+8], 1
0x1800e3196  ja      short loc_1800E31A0
0x1800e3198  mov     rcx, rdi
0x1800e319b  call    ?DemandInit@?$TChoice@VTableColumnsAndGroupsChoiceChoiceIDsImpl@ODF@@@Ofc@@AEBAXXZ; Ofc::TChoice<ODF::TableColumnsAndGroupsChoiceChoiceIDsImpl>::DemandInit(void)
0x1800e31a0  mov     rax, [rdi+8]
0x1800e31a4  test    rax, rax
0x1800e31a7  jz      short loc_1800E31B7
0x1800e31a9  lea     rcx, [rbp+var_30]
0x1800e31ad  mov     rax, [rax+28h]
0x1800e31b1  call    cs:__guard_dispatch_icall_fptr
0x1800e31b7  inc     r14d
0x1800e31ba  cmp     r14d, [rbx+10h]
0x1800e31be  jb      short loc_1800E314C
0x1800e31c0  mov     eax, [rbx+28h]
0x1800e31c3  test    eax, eax
0x1800e31c5  jz      short loc_1800E323F
0x1800e31c7  xor     r14d, r14d
0x1800e31ca  cmp     r14d, eax
0x1800e31cd  jnb     loc_1800E3270
0x1800e31d3  mov     edi, r14d
0x1800e31d6  shl     rdi, 4
0x1800e31da  add     rdi, [rbx+20h]
0x1800e31de  lea     rax, ??_7?$TChoiceWriterVisitor@V?$TableRowsAndGroupsChoice_@$0A@@ODF@@VTableRowsAndGroupsChoiceWriterTList@2@@Ofc@@6B@; const Ofc::TChoiceWriterVisitor<ODF::TableRowsAndGroupsChoice_<0>,ODF::TableRowsAndGroupsChoiceWriterTList>::`vftable'
0x1800e31e5  mov     [rbp+var_30], rax
0x1800e31e9  mov     [rbp+var_28], rdi
0x1800e31ed  mov     [rbp+var_20], rsi
0x1800e31f1  lea     rax, off_180204FC0; "table-rows"
0x1800e31f8  mov     [rbp+var_18], rax
0x1800e31fc  lea     rax, qword_180204FE8
0x1800e3203  mov     [rbp+var_10], rax
0x1800e3207  mov     [rbp+var_8], 5
0x1800e320e  cmp     qword ptr [rdi+8], 1
0x1800e3213  ja      short loc_1800E321D
0x1800e3215  mov     rcx, rdi
0x1800e3218  call    ?DemandInit@?$TChoice@VTableRowsAndGroupsChoiceChoiceIDsImpl@ODF@@@Ofc@@AEBAXXZ; Ofc::TChoice<ODF::TableRowsAndGroupsChoiceChoiceIDsImpl>::DemandInit(void)
0x1800e321d  mov     rax, [rdi+8]
0x1800e3221  test    rax, rax
0x1800e3224  jz      short loc_1800E3234
0x1800e3226  lea     rcx, [rbp+var_30]
0x1800e322a  mov     rax, [rax+28h]
0x1800e322e  call    cs:__guard_dispatch_icall_fptr
0x1800e3234  inc     r14d
0x1800e3237  mov     eax, [rbx+28h]
0x1800e323a  cmp     r14d, eax
0x1800e323d  jb      short loc_1800E31CA
0x1800e323f  mov     rcx, r15
0x1800e3242  call    cs:__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ; Ofc::CWriterEmit::EmitEndElement(void)
0x1800e3248  nop
0x1800e3249  lea     r11, [rsp+60h+var_s0]
0x1800e324e  mov     rbx, [r11+38h]
0x1800e3252  mov     rsi, [r11+48h]
0x1800e3256  mov     rsp, r11
0x1800e3259  pop     r15
0x1800e325b  pop     r14
0x1800e325d  pop     r12
0x1800e325f  pop     rdi
0x1800e3260  pop     rbp
0x1800e3261  retn
0x1800e3262  xor     edx, edx
0x1800e3264  mov     ecx, 1E892498h
0x1800e3269  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800e326f  nop
0x1800e3270  xor     edx, edx
0x1800e3272  mov     ecx, 1E892498h
0x1800e3277  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
