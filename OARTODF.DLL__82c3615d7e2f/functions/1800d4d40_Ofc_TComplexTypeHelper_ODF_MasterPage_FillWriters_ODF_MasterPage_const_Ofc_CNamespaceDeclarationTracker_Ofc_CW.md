# Ofc::TComplexTypeHelper<ODF::MasterPage>::FillWriters(ODF::MasterPage const &,Ofc::CNamespaceDeclarationTracker &,Ofc::CWriterEmit &,Ofc::IWriterParams &)

- ea: `0x1800d4d40`
- end: `0x1800d5028`
- name: `?FillWriters@?$TComplexTypeHelper@VMasterPage@ODF@@@Ofc@@SAXAEBVMasterPage@ODF@@AEAVCNamespaceDeclarationTracker@2@AEAVCWriterEmit@2@AEAVIWriterParams@2@@Z`
- size: `744`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800849d0`

## callees

- `0x1800025a0`
- `0x18001db8c`
- `0x18001dc30`
- `0x18001dcf4`
- `0x1800480ac`
- `0x180077904`
- `0x18008a1dc`
- `0x1800d4804`
- `0x1800d4d40`
- `0x1801a80e0`

## import_xrefs

- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800d4d81`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800d4da8`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800d4de6`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800d4e0e`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800d4e38`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800d4d81`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800d4da8`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800d4de6`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800d4e0e`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800d4e38`
- `mso40uiWin32Client!__imp_??1CNamespaceDeclarationTracker@Ofc@@QEAA@XZ` at `0x1800d4f4f`
- `mso40uiWin32Client!__imp_??1CNamespaceDeclarationTracker@Ofc@@QEAA@XZ` at `0x1800d4f4f`
- `mso40uiWin32Client!__imp_??0TCFWH@Ofc@@QEAA@AEAVIWriterParams@1@HPEB_W@Z` at `0x1800d4f2e`
- `mso40uiWin32Client!__imp_??0TCFWH@Ofc@@QEAA@AEAVIWriterParams@1@HPEB_W@Z` at `0x1800d4f2e`
- `mso40uiWin32Client!__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ` at `0x1800d4fbe`
- `mso40uiWin32Client!__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ` at `0x1800d4fbe`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800d5013`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800d5021`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800d5013`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800d5021`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800d4fe5`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800d4fe5`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Ofc::TComplexTypeHelper<ODF::MasterPage>::FillWriters(
        __int64 a1,
        Ofc::CNamespaceDeclarationTracker *a2,
        Ofc::CWriterEmit *a3,
        __int64 a4)
{
  unsigned int v8; // r14d
  unsigned int v9; // eax
  unsigned int v10; // r14d
  __int64 v11; // rcx
  _QWORD *v12; // r14
  __int64 v13; // rdi
  __int64 v14; // rax
  void *v15; // rdx
  Mso::Memory *v16; // rcx
  void **v17; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v18; // [rsp+38h] [rbp-C8h]
  __int64 v19; // [rsp+40h] [rbp-C0h]
  wchar_t **v20; // [rsp+48h] [rbp-B8h]
  __int64 *v21; // [rsp+50h] [rbp-B0h]
  int v22; // [rsp+58h] [rbp-A8h]
  const wchar_t *v23; // [rsp+60h] [rbp-A0h] BYREF
  char v24[8]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v25[40]; // [rsp+78h] [rbp-88h] BYREF
  char v26[560]; // [rsp+A0h] [rbp-60h] BYREF

  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 319);
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(L"name", 319, a1 + 64, a4);
  if ( *(_QWORD *)(a1 + 72) )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 319);
  v23 = &dword_1801DBD74;
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(
    (unsigned int)L"display-name",
    319,
    a1 + 72,
    a4,
    (__int64)&v23);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 319);
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(L"page-layout-name", 319, a1 + 80, a4);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 307);
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(L"style-name", 307, a1 + 88, a4);
  if ( *(_QWORD *)(a1 + 96) )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 319);
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(
    L"next-style-name",
    319,
    a1 + 96,
    a4);
  (**(void (__fastcall ***)(Ofc::CWriterEmit *, _QWORD))a3)(a3, *(_QWORD *)(a4 + 16));
  if ( *(_DWORD *)(a1 + 16) )
  {
    v8 = 0;
    while ( v8 < *(_DWORD *)(a1 + 16) )
    {
      Ofc::TCompFillWritersHelper<ODF::StyleObject>(*(_QWORD *)(a1 + 8) + 32LL * v8++, a4, 319, L"style");
      if ( v8 >= *(_DWORD *)(a1 + 16) )
        goto LABEL_9;
    }
    CrashWithRecovery(0x1E892498u, 0);
LABEL_27:
    CrashWithRecovery(0x1E892498u, 0);
    JUMPOUT(0x1800D5027LL);
  }
LABEL_9:
  v9 = *(_DWORD *)(a1 + 40);
  if ( v9 )
  {
    v10 = 0;
    while ( v10 < v9 )
    {
      v11 = *(_QWORD *)(a1 + 32) + 16LL * v10;
      v17 = &Ofc::TChoiceWriterVisitor<ODF::DrawShapeChoice_<0>,ODF::DrawShapeChoiceWriterTList>::`vftable';
      v18 = v11;
      v19 = a4;
      v20 = off_180202F50;
      v21 = qword_180202FE0;
      v22 = 17;
      Ofc::TChoice<ODF::DrawShapeChoiceChoiceIDsImpl>::Accept(v11, &v17);
      ++v10;
      v9 = *(_DWORD *)(a1 + 40);
      if ( v10 >= v9 )
        goto LABEL_13;
    }
    goto LABEL_27;
  }
LABEL_13:
  v12 = *(_QWORD **)(a1 + 48);
  if ( v12 )
  {
    Ofc::TCFWH::TCFWH((Ofc::TCFWH *)v24, (struct Ofc::IWriterParams *)a4, 315, L"notes");
    Ofc::TComplexTypeHelper<ODF::NotesSevered>::FillWriters(*v12, v25, v26, a4);
    Ofc::CNamespaceDeclarationTracker::~CNamespaceDeclarationTracker((Ofc::CNamespaceDeclarationTracker *)v25);
  }
  v13 = *(_QWORD *)(a1 + 56);
  if ( v13 )
  {
    v17 = &Ofc::TChoiceWriterVisitor<ODF::MasterPage::DrawPageChoice_<0>,ODF::MasterPage::DrawPageChoiceWriterTList>::`vftable';
    v18 = v13;
    v19 = a4;
    v20 = off_180203030;
    v21 = qword_180202F18;
    v22 = 11;
    if ( *(_QWORD *)(v13 + 8) <= 1u )
      Ofc::TChoice<ODF::MasterPage::DrawPageChoiceChoiceIDsImpl>::DemandInit(v13);
    v14 = *(_QWORD *)(v13 + 8);
    if ( v14 )
      (*(void (__fastcall **)(void ***))(v14 + 40))(&v17);
  }
  Ofc::CWriterEmit::EmitEndElement(a3);
  v16 = (Mso::Memory *)(&dword_1801DBD74 - 6);
  if ( *((_DWORD *)&dword_1801DBD74 - 2)
    && (*(_DWORD *)v16 == 1 || _InterlockedExchangeAdd((volatile signed __int32 *)v16, 0xFFFFFFFF) == 1)
    && &dword_1801DBD74 != (const wchar_t *)12 )
  {
    Mso::Memory::Free(v16, v15);
  }
}

```

## disassembly

```asm
0x1800d4d40  push    rbp
0x1800d4d42  push    rbx
0x1800d4d43  push    rsi
0x1800d4d44  push    rdi
0x1800d4d45  push    r12
0x1800d4d47  push    r14
0x1800d4d49  push    r15
0x1800d4d4b  lea     rbp, [rsp-1E0h]
0x1800d4d53  sub     rsp, 2E0h
0x1800d4d5a  mov     rax, cs:__security_cookie
0x1800d4d61  xor     rax, rsp
0x1800d4d64  mov     [rbp+210h+var_40], rax
0x1800d4d6b  mov     rsi, r9
0x1800d4d6e  mov     r12, r8
0x1800d4d71  mov     r14, rdx
0x1800d4d74  mov     rdi, rcx
0x1800d4d77  mov     ebx, 13Fh
0x1800d4d7c  mov     edx, ebx
0x1800d4d7e  mov     rcx, r14
0x1800d4d81  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800d4d87  lea     r8, [rdi+40h]
0x1800d4d8b  mov     r9, rsi
0x1800d4d8e  mov     edx, ebx
0x1800d4d90  lea     rcx, aName; "name"
0x1800d4d97  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TSelfAdapter@VCVarStr@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBVCVarStr@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(wchar_t const *,int,Ofc::CVarStr const &,Ofc::IWriterParams &)
0x1800d4d9c  cmp     qword ptr [rdi+48h], 0
0x1800d4da1  jz      short loc_1800D4DAE
0x1800d4da3  mov     edx, ebx
0x1800d4da5  mov     rcx, r14
0x1800d4da8  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800d4dae  lea     rbx, dword_1801DBD74
0x1800d4db5  mov     [rsp+310h+var_2B0], rbx
0x1800d4dba  lea     rax, [rsp+310h+var_2B0]
0x1800d4dbf  mov     [rsp+310h+var_2F0], rax
0x1800d4dc4  mov     r9, rsi
0x1800d4dc7  lea     r8, [rdi+48h]
0x1800d4dcb  mov     r15d, 13Fh
0x1800d4dd1  mov     edx, r15d
0x1800d4dd4  lea     rcx, aDisplayName; "display-name"
0x1800d4ddb  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TOptionalAdapter@VCVarStr@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VCVarStr@Ofc@@@2@AEAVIWriterParams@2@PEBVCVarStr@2@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::CVarStr> const &,Ofc::IWriterParams &,Ofc::CVarStr const *)
0x1800d4de0  mov     edx, r15d
0x1800d4de3  mov     rcx, r14
0x1800d4de6  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800d4dec  lea     r8, [rdi+50h]
0x1800d4df0  mov     r9, rsi
0x1800d4df3  mov     edx, r15d
0x1800d4df6  lea     rcx, aPageLayoutName; "page-layout-name"
0x1800d4dfd  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TSelfAdapter@VCVarStr@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBVCVarStr@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(wchar_t const *,int,Ofc::CVarStr const &,Ofc::IWriterParams &)
0x1800d4e02  mov     r15d, 133h
0x1800d4e08  mov     edx, r15d
0x1800d4e0b  mov     rcx, r14
0x1800d4e0e  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800d4e14  lea     r8, [rdi+58h]
0x1800d4e18  mov     r9, rsi
0x1800d4e1b  mov     edx, r15d
0x1800d4e1e  lea     rcx, aStyleName; "style-name"
0x1800d4e25  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TSelfAdapter@VCVarStr@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBVCVarStr@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(wchar_t const *,int,Ofc::CVarStr const &,Ofc::IWriterParams &)
0x1800d4e2a  cmp     qword ptr [rdi+60h], 0
0x1800d4e2f  jz      short loc_1800D4E3E
0x1800d4e31  lea     edx, [r15+0Ch]
0x1800d4e35  mov     rcx, r14
0x1800d4e38  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800d4e3e  mov     r9, rsi
0x1800d4e41  lea     r8, [rdi+60h]
0x1800d4e45  mov     r15d, 13Fh
0x1800d4e4b  mov     edx, r15d
0x1800d4e4e  lea     rcx, aNextStyleName; "next-style-name"
0x1800d4e55  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TOptionalAdapter@VCVarStr@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VCVarStr@Ofc@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::CVarStr> const &,Ofc::IWriterParams &)
0x1800d4e5a  mov     rax, [r12]
0x1800d4e5e  mov     rdx, [rsi+10h]
0x1800d4e62  mov     rcx, r12
0x1800d4e65  mov     rax, [rax]
0x1800d4e68  call    cs:__guard_dispatch_icall_fptr
0x1800d4e6e  cmp     dword ptr [rdi+10h], 0
0x1800d4e72  jbe     short loc_1800D4EA7
0x1800d4e74  xor     r14d, r14d
0x1800d4e77  cmp     r14d, [rdi+10h]
0x1800d4e7b  jnb     loc_1800D500C
0x1800d4e81  mov     ecx, r14d
0x1800d4e84  shl     rcx, 5
0x1800d4e88  add     rcx, [rdi+8]
0x1800d4e8c  lea     r9, aStyle; "style"
0x1800d4e93  mov     r8d, r15d
0x1800d4e96  mov     rdx, rsi
0x1800d4e99  call    ??$TCompFillWritersHelper@VStyleObject@ODF@@@Ofc@@YAXAEBVStyleObject@ODF@@AEAVIWriterParams@0@HPEB_W@Z; Ofc::TCompFillWritersHelper<ODF::StyleObject>(ODF::StyleObject const &,Ofc::IWriterParams &,int,wchar_t const *)
0x1800d4e9e  inc     r14d
0x1800d4ea1  cmp     r14d, [rdi+10h]
0x1800d4ea5  jb      short loc_1800D4E77
0x1800d4ea7  mov     eax, [rdi+28h]
0x1800d4eaa  test    eax, eax
0x1800d4eac  jz      short loc_1800D4F10
0x1800d4eae  xor     r14d, r14d
0x1800d4eb1  cmp     r14d, eax
0x1800d4eb4  jnb     loc_1800D501A
0x1800d4eba  mov     ecx, r14d
0x1800d4ebd  shl     rcx, 4
0x1800d4ec1  add     rcx, [rdi+20h]
0x1800d4ec5  lea     rax, ??_7?$TChoiceWriterVisitor@V?$DrawShapeChoice_@$0A@@ODF@@VDrawShapeChoiceWriterTList@2@@Ofc@@6B@; const Ofc::TChoiceWriterVisitor<ODF::DrawShapeChoice_<0>,ODF::DrawShapeChoiceWriterTList>::`vftable'
0x1800d4ecc  mov     [rsp+310h+var_2E0], rax
0x1800d4ed1  mov     [rsp+310h+var_2D8], rcx
0x1800d4ed6  mov     [rsp+310h+var_2D0], rsi
0x1800d4edb  lea     rax, off_180202F50; "rect"
0x1800d4ee2  mov     [rsp+310h+var_2C8], rax
0x1800d4ee7  lea     rax, qword_180202FE0
0x1800d4eee  mov     [rsp+310h+var_2C0], rax
0x1800d4ef3  mov     [rsp+310h+var_2B8], 11h
0x1800d4efb  lea     rdx, [rsp+310h+var_2E0]
0x1800d4f00  call    ?Accept@?$TChoice@VDrawShapeChoiceChoiceIDsImpl@ODF@@@Ofc@@QEBAXAEAVDrawShapeChoiceChoiceIDsCSCV@ODF@@@Z; Ofc::TChoice<ODF::DrawShapeChoiceChoiceIDsImpl>::Accept(ODF::DrawShapeChoiceChoiceIDsCSCV &)
0x1800d4f05  inc     r14d
0x1800d4f08  mov     eax, [rdi+28h]
0x1800d4f0b  cmp     r14d, eax
0x1800d4f0e  jb      short loc_1800D4EB1
0x1800d4f10  mov     r14, [rdi+30h]
0x1800d4f14  test    r14, r14
0x1800d4f17  jz      short loc_1800D4F55
0x1800d4f19  lea     r9, aNotes; "notes"
0x1800d4f20  mov     r8d, 13Bh
0x1800d4f26  mov     rdx, rsi
0x1800d4f29  lea     rcx, [rsp+310h+var_2A0]
0x1800d4f2e  call    cs:__imp_??0TCFWH@Ofc@@QEAA@AEAVIWriterParams@1@HPEB_W@Z; Ofc::TCFWH::TCFWH(Ofc::IWriterParams &,int,wchar_t const *)
0x1800d4f34  nop
0x1800d4f35  mov     r9, rsi
0x1800d4f38  lea     r8, [rbp+210h+var_270]
0x1800d4f3c  lea     rdx, [rsp+310h+var_298]
0x1800d4f41  mov     rcx, [r14]
0x1800d4f44  call    ?FillWriters@?$TComplexTypeHelper@VNotesSevered@ODF@@@Ofc@@SAXAEBVNotesSevered@ODF@@AEAVCNamespaceDeclarationTracker@2@AEAVCWriterEmit@2@AEAVIWriterParams@2@@Z; Ofc::TComplexTypeHelper<ODF::NotesSevered>::FillWriters(ODF::NotesSevered const &,Ofc::CNamespaceDeclarationTracker &,Ofc::CWriterEmit &,Ofc::IWriterParams &)
0x1800d4f49  nop
0x1800d4f4a  lea     rcx, [rsp+310h+var_298]
0x1800d4f4f  call    cs:__imp_??1CNamespaceDeclarationTracker@Ofc@@QEAA@XZ; Ofc::CNamespaceDeclarationTracker::~CNamespaceDeclarationTracker(void)
0x1800d4f55  mov     rdi, [rdi+38h]
0x1800d4f59  test    rdi, rdi
0x1800d4f5c  jz      short loc_1800D4FBB
0x1800d4f5e  lea     rax, ??_7?$TChoiceWriterVisitor@V?$DrawPageChoice_@$0A@@MasterPage@ODF@@VDrawPageChoiceWriterTList@23@@Ofc@@6B@; const Ofc::TChoiceWriterVisitor<ODF::MasterPage::DrawPageChoice_<0>,ODF::MasterPage::DrawPageChoiceWriterTList>::`vftable'
0x1800d4f65  mov     [rsp+310h+var_2E0], rax
0x1800d4f6a  mov     [rsp+310h+var_2D8], rdi
0x1800d4f6f  mov     [rsp+310h+var_2D0], rsi
0x1800d4f74  lea     rax, off_180203030; "animate"
0x1800d4f7b  mov     [rsp+310h+var_2C8], rax
0x1800d4f80  lea     rax, qword_180202F18
0x1800d4f87  mov     [rsp+310h+var_2C0], rax
0x1800d4f8c  mov     [rsp+310h+var_2B8], 0Bh
0x1800d4f94  cmp     qword ptr [rdi+8], 1
0x1800d4f99  ja      short loc_1800D4FA3
0x1800d4f9b  mov     rcx, rdi
0x1800d4f9e  call    ?DemandInit@?$TChoice@VDrawPageChoiceChoiceIDsImpl@MasterPage@ODF@@@Ofc@@AEBAXXZ; Ofc::TChoice<ODF::MasterPage::DrawPageChoiceChoiceIDsImpl>::DemandInit(void)
0x1800d4fa3  mov     rax, [rdi+8]
0x1800d4fa7  test    rax, rax
0x1800d4faa  jz      short loc_1800D4FBB
0x1800d4fac  lea     rcx, [rsp+310h+var_2E0]
0x1800d4fb1  mov     rax, [rax+28h]
0x1800d4fb5  call    cs:__guard_dispatch_icall_fptr
0x1800d4fbb  mov     rcx, r12
0x1800d4fbe  call    cs:__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ; Ofc::CWriterEmit::EmitEndElement(void)
0x1800d4fc4  nop
0x1800d4fc5  lea     rcx, [rbx-0Ch]
0x1800d4fc9  cmp     dword ptr [rcx+4], 0
0x1800d4fcd  jz      short loc_1800D4FEB
0x1800d4fcf  cmp     dword ptr [rcx], 1
0x1800d4fd2  jz      short loc_1800D4FE0
0x1800d4fd4  or      eax, 0FFFFFFFFh
0x1800d4fd7  lock xadd [rcx], eax
0x1800d4fdb  cmp     eax, 1
0x1800d4fde  jnz     short loc_1800D4FEB
0x1800d4fe0  test    rcx, rcx
0x1800d4fe3  jz      short loc_1800D4FEB
0x1800d4fe5  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1800d4feb  mov     rcx, [rbp+210h+var_40]
0x1800d4ff2  xor     rcx, rsp; StackCookie
0x1800d4ff5  call    __security_check_cookie
0x1800d4ffa  add     rsp, 2E0h
0x1800d5001  pop     r15
0x1800d5003  pop     r14
0x1800d5005  pop     r12
0x1800d5007  pop     rdi
0x1800d5008  pop     rsi
0x1800d5009  pop     rbx
0x1800d500a  pop     rbp
0x1800d500b  retn
0x1800d500c  xor     edx, edx
0x1800d500e  mov     ecx, 1E892498h
0x1800d5013  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800d5019  nop
0x1800d501a  xor     edx, edx
0x1800d501c  mov     ecx, 1E892498h
0x1800d5021  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
