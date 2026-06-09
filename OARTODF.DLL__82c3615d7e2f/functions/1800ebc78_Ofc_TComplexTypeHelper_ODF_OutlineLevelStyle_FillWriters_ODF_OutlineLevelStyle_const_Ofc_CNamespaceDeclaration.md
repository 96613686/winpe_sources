# Ofc::TComplexTypeHelper<ODF::OutlineLevelStyle>::FillWriters(ODF::OutlineLevelStyle const &,Ofc::CNamespaceDeclarationTracker &,Ofc::CWriterEmit &,Ofc::IWriterParams &)

- ea: `0x1800ebc78`
- end: `0x1800ebebd`
- name: `?FillWriters@?$TComplexTypeHelper@VOutlineLevelStyle@ODF@@@Ofc@@SAXAEBVOutlineLevelStyle@ODF@@AEAVCNamespaceDeclarationTracker@2@AEAVCWriterEmit@2@AEAVIWriterParams@2@@Z`
- size: `581`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800ebec0`

## callees

- `0x18001dcf4`
- `0x18001dd94`
- `0x18002603c`
- `0x18002df74`
- `0x180062aa0`
- `0x1800ceb24`
- `0x1800cf934`
- `0x1800d19d4`
- `0x1800ebc78`
- `0x1801a80e0`

## import_xrefs

- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800ebca6`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800ebcc8`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800ebcf6`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800ebd15`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800ebd37`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800ebd6f`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800ebda0`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800ebdc2`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800ebdf0`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800ebca6`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800ebcc8`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800ebcf6`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800ebd15`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800ebd37`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800ebd6f`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800ebda0`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800ebdc2`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800ebdf0`
- `mso40uiWin32Client!__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ` at `0x1800ebe4a`
- `mso40uiWin32Client!__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ` at `0x1800ebe4a`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800ebe7b`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800ebea0`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800ebe7b`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800ebea0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Ofc::TComplexTypeHelper<ODF::OutlineLevelStyle>::FillWriters(
        _QWORD *a1,
        Ofc::CNamespaceDeclarationTracker *a2,
        Ofc::CWriterEmit *a3,
        __int64 a4)
{
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rcx
  void *v13; // rdx
  Mso::Memory *v14; // rcx
  const wchar_t *v15; // [rsp+60h] [rbp+8h] BYREF
  const wchar_t *v16; // [rsp+70h] [rbp+18h] BYREF

  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 321);
  Ofc::TAttrWriterHelper<unsigned int,Ofc::TSelfAdapter<unsigned int>,1>::Write(L"level", 321, a1 + 2, a4);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 321);
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(L"style-name", 321, a1 + 3, a4);
  if ( a1[4] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 319);
  Ofc::TAttrWriterHelper<Ofc::TVariant<ODF::NumFormatIDsImpl>,Ofc::TOptionalAdapter<Ofc::TVariant<ODF::NumFormatIDsImpl>>,0>::Write(
    v9,
    v8,
    a1 + 4,
    a4);
  if ( a1[5] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 319);
  Ofc::TAttrWriterHelper<ODF::OdfBoolean,Ofc::TOptionalAdapter<ODF::OdfBoolean>,0>::Write(
    L"num-letter-sync",
    319,
    a1 + 5,
    a4);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 319);
  v15 = &dword_1801DBD74;
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(
    (unsigned int)L"num-prefix",
    319,
    (_DWORD)a1 + 48,
    a4,
    (__int64)&v15);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 319);
  v16 = &dword_1801DBD74;
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(
    (unsigned int)L"num-suffix",
    319,
    (_DWORD)a1 + 56,
    a4,
    (__int64)&v16);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 319);
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(
    L"num-list-format-name",
    319,
    a1 + 8,
    a4);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 321);
  Ofc::TAttrWriterHelper<unsigned int,Ofc::TSelfAdapter<unsigned int>,1>::Write(
    L"display-levels",
    321,
    a1 + 9,
    a4,
    byte_180206758);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 321);
  Ofc::TAttrWriterHelper<unsigned int,Ofc::TSelfAdapter<unsigned int>,1>::Write(
    L"start-value",
    321,
    (char *)a1 + 76,
    a4,
    &dword_18020675C);
  (**(void (__fastcall ***)(Ofc::CWriterEmit *, _QWORD))a3)(a3, *(_QWORD *)(a4 + 16));
  Ofc::TCompElemWriterHelper<ODF::StyleListLevelPropertiesContent,Ofc::TOptionalAdapter<ODF::StyleListLevelPropertiesContent>,0>::Write(
    v11,
    v10,
    a1,
    a4);
  v12 = a1[1];
  if ( v12 )
    Ofc::TCompFillWritersHelper<ODF::StyleTextPropertiesContent>(v12, a4);
  Ofc::CWriterEmit::EmitEndElement(a3);
  v14 = (Mso::Memory *)(&dword_1801DBD74 - 6);
  if ( *((_DWORD *)&dword_1801DBD74 - 2)
    && (*(_DWORD *)v14 == 1 || !_InterlockedDecrement((volatile signed __int32 *)v14))
    && &dword_1801DBD74 != (const wchar_t *)12 )
  {
    Mso::Memory::Free(v14, v13);
  }
}

```

## disassembly

```asm
0x1800ebc78  mov     [rsp+arg_8], rbx
0x1800ebc7d  mov     [rsp+arg_18], rbp
0x1800ebc82  push    rsi
0x1800ebc83  push    rdi
0x1800ebc84  push    r12
0x1800ebc86  push    r13
0x1800ebc88  push    r14
0x1800ebc8a  sub     rsp, 30h
0x1800ebc8e  mov     rdi, r9
0x1800ebc91  mov     r14, r8
0x1800ebc94  mov     rsi, rdx
0x1800ebc97  mov     rbp, rcx
0x1800ebc9a  mov     r12d, 141h
0x1800ebca0  mov     edx, r12d
0x1800ebca3  mov     rcx, rsi
0x1800ebca6  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800ebcac  lea     r8, [rbp+10h]
0x1800ebcb0  mov     r9, rdi
0x1800ebcb3  mov     edx, r12d
0x1800ebcb6  lea     rcx, aLevel; "level"
0x1800ebcbd  call    ?Write@?$TAttrWriterHelper@IV?$TSelfAdapter@I@Ofc@@$00@Ofc@@SAXPEB_WHAEBIAEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<uint,Ofc::TSelfAdapter<uint>,1>::Write(wchar_t const *,int,uint const &,Ofc::IWriterParams &)
0x1800ebcc2  mov     edx, r12d
0x1800ebcc5  mov     rcx, rsi
0x1800ebcc8  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800ebcce  lea     r8, [rbp+18h]
0x1800ebcd2  mov     r9, rdi
0x1800ebcd5  mov     edx, r12d
0x1800ebcd8  lea     rcx, aStyleName; "style-name"
0x1800ebcdf  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TSelfAdapter@VCVarStr@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBVCVarStr@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(wchar_t const *,int,Ofc::CVarStr const &,Ofc::IWriterParams &)
0x1800ebce4  lea     r13d, [r12-2]
0x1800ebce9  cmp     qword ptr [rbp+20h], 0
0x1800ebcee  jz      short loc_1800EBCFC
0x1800ebcf0  mov     edx, r13d
0x1800ebcf3  mov     rcx, rsi
0x1800ebcf6  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800ebcfc  mov     r9, rdi
0x1800ebcff  lea     r8, [rbp+20h]
0x1800ebd03  call    ?Write@?$TAttrWriterHelper@V?$TVariant@VNumFormatIDsImpl@ODF@@@Ofc@@V?$TOptionalAdapter@V?$TVariant@VNumFormatIDsImpl@ODF@@@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@V?$TVariant@VNumFormatIDsImpl@ODF@@@Ofc@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::TVariant<ODF::NumFormatIDsImpl>,Ofc::TOptionalAdapter<Ofc::TVariant<ODF::NumFormatIDsImpl>>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::TVariant<ODF::NumFormatIDsImpl>> const &,Ofc::IWriterParams &)
0x1800ebd08  cmp     qword ptr [rbp+28h], 0
0x1800ebd0d  jz      short loc_1800EBD1B
0x1800ebd0f  mov     edx, r13d
0x1800ebd12  mov     rcx, rsi
0x1800ebd15  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800ebd1b  mov     r9, rdi
0x1800ebd1e  lea     r8, [rbp+28h]
0x1800ebd22  mov     edx, r13d
0x1800ebd25  lea     rcx, aNumLetterSync; "num-letter-sync"
0x1800ebd2c  call    ?Write@?$TAttrWriterHelper@VOdfBoolean@ODF@@V?$TOptionalAdapter@VOdfBoolean@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VOdfBoolean@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::OdfBoolean,Ofc::TOptionalAdapter<ODF::OdfBoolean>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::OdfBoolean> const &,Ofc::IWriterParams &)
0x1800ebd31  mov     edx, r13d
0x1800ebd34  mov     rcx, rsi
0x1800ebd37  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800ebd3d  lea     rbx, dword_1801DBD74
0x1800ebd44  mov     [rsp+58h+arg_0], rbx
0x1800ebd49  lea     r8, [rbp+30h]
0x1800ebd4d  lea     rax, [rsp+58h+arg_0]
0x1800ebd52  mov     [rsp+58h+var_38], rax
0x1800ebd57  mov     r9, rdi
0x1800ebd5a  mov     edx, r13d
0x1800ebd5d  lea     rcx, aNumPrefix; "num-prefix"
0x1800ebd64  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TSelfAdapter@VCVarStr@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBVCVarStr@2@AEAVIWriterParams@2@PEBV32@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(wchar_t const *,int,Ofc::CVarStr const &,Ofc::IWriterParams &,Ofc::CVarStr const *)
0x1800ebd69  mov     edx, r13d
0x1800ebd6c  mov     rcx, rsi
0x1800ebd6f  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800ebd75  mov     [rsp+58h+arg_10], rbx
0x1800ebd7a  lea     r8, [rbp+38h]
0x1800ebd7e  lea     rax, [rsp+58h+arg_10]
0x1800ebd83  mov     [rsp+58h+var_38], rax
0x1800ebd88  mov     r9, rdi
0x1800ebd8b  mov     edx, r13d
0x1800ebd8e  lea     rcx, aNumSuffix; "num-suffix"
0x1800ebd95  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TSelfAdapter@VCVarStr@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBVCVarStr@2@AEAVIWriterParams@2@PEBV32@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(wchar_t const *,int,Ofc::CVarStr const &,Ofc::IWriterParams &,Ofc::CVarStr const *)
0x1800ebd9a  mov     edx, r13d
0x1800ebd9d  mov     rcx, rsi
0x1800ebda0  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800ebda6  lea     r8, [rbp+40h]
0x1800ebdaa  mov     r9, rdi
0x1800ebdad  mov     edx, r13d
0x1800ebdb0  lea     rcx, aNumListFormatN; "num-list-format-name"
0x1800ebdb7  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TSelfAdapter@VCVarStr@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBVCVarStr@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(wchar_t const *,int,Ofc::CVarStr const &,Ofc::IWriterParams &)
0x1800ebdbc  mov     edx, r12d
0x1800ebdbf  mov     rcx, rsi
0x1800ebdc2  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800ebdc8  lea     r8, [rbp+48h]
0x1800ebdcc  lea     rax, byte_180206758
0x1800ebdd3  mov     [rsp+58h+var_38], rax
0x1800ebdd8  mov     r9, rdi
0x1800ebddb  mov     edx, r12d
0x1800ebdde  lea     rcx, aDisplayLevels; "display-levels"
0x1800ebde5  call    ?Write@?$TAttrWriterHelper@IV?$TSelfAdapter@I@Ofc@@$00@Ofc@@SAXPEB_WHAEBIAEAVIWriterParams@2@PEBI@Z; Ofc::TAttrWriterHelper<uint,Ofc::TSelfAdapter<uint>,1>::Write(wchar_t const *,int,uint const &,Ofc::IWriterParams &,uint const *)
0x1800ebdea  mov     edx, r12d
0x1800ebded  mov     rcx, rsi
0x1800ebdf0  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800ebdf6  lea     r8, [rbp+4Ch]
0x1800ebdfa  lea     rax, dword_18020675C
0x1800ebe01  mov     [rsp+58h+var_38], rax
0x1800ebe06  mov     r9, rdi
0x1800ebe09  mov     edx, r12d
0x1800ebe0c  lea     rcx, aStartValue; "start-value"
0x1800ebe13  call    ?Write@?$TAttrWriterHelper@IV?$TSelfAdapter@I@Ofc@@$00@Ofc@@SAXPEB_WHAEBIAEAVIWriterParams@2@PEBI@Z; Ofc::TAttrWriterHelper<uint,Ofc::TSelfAdapter<uint>,1>::Write(wchar_t const *,int,uint const &,Ofc::IWriterParams &,uint const *)
0x1800ebe18  mov     rax, [r14]
0x1800ebe1b  mov     rdx, [rdi+10h]
0x1800ebe1f  mov     rcx, r14
0x1800ebe22  mov     rax, [rax]
0x1800ebe25  call    cs:__guard_dispatch_icall_fptr
0x1800ebe2b  mov     r9, rdi
0x1800ebe2e  mov     r8, rbp
0x1800ebe31  call    ?Write@?$TCompElemWriterHelper@VStyleListLevelPropertiesContent@ODF@@V?$TOptionalAdapter@VStyleListLevelPropertiesContent@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VStyleListLevelPropertiesContent@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TCompElemWriterHelper<ODF::StyleListLevelPropertiesContent,Ofc::TOptionalAdapter<ODF::StyleListLevelPropertiesContent>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::StyleListLevelPropertiesContent> const &,Ofc::IWriterParams &)
0x1800ebe36  mov     rcx, [rbp+8]
0x1800ebe3a  test    rcx, rcx
0x1800ebe3d  jz      short loc_1800EBE47
0x1800ebe3f  mov     rdx, rdi
0x1800ebe42  call    ??$TCompFillWritersHelper@VStyleTextPropertiesContent@ODF@@@Ofc@@YAXAEBVStyleTextPropertiesContent@ODF@@AEAVIWriterParams@0@HPEB_W@Z; Ofc::TCompFillWritersHelper<ODF::StyleTextPropertiesContent>(ODF::StyleTextPropertiesContent const &,Ofc::IWriterParams &,int,wchar_t const *)
0x1800ebe47  mov     rcx, r14
0x1800ebe4a  call    cs:__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ; Ofc::CWriterEmit::EmitEndElement(void)
0x1800ebe50  nop
0x1800ebe51  or      edi, 0FFFFFFFFh
0x1800ebe54  cmp     cs:dword_1801DBD6C, 0
0x1800ebe5b  jz      short loc_1800EBE82
0x1800ebe5d  cmp     cs:dword_1801DBD68, 1
0x1800ebe64  jz      short loc_1800EBE74
0x1800ebe66  mov     eax, edi
0x1800ebe68  lock xadd cs:dword_1801DBD68, eax
0x1800ebe70  add     eax, edi
0x1800ebe72  jnz     short loc_1800EBE82
0x1800ebe74  lea     rcx, dword_1801DBD68
0x1800ebe7b  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1800ebe81  nop
0x1800ebe82  lea     rcx, [rbx-0Ch]
0x1800ebe86  cmp     dword ptr [rcx+4], 0
0x1800ebe8a  jz      short loc_1800EBEA6
0x1800ebe8c  cmp     dword ptr [rcx], 1
0x1800ebe8f  jz      short loc_1800EBE9B
0x1800ebe91  mov     eax, edi
0x1800ebe93  lock xadd [rcx], eax
0x1800ebe97  add     eax, edi
0x1800ebe99  jnz     short loc_1800EBEA6
0x1800ebe9b  test    rcx, rcx
0x1800ebe9e  jz      short loc_1800EBEA6
0x1800ebea0  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1800ebea6  mov     rbx, [rsp+58h+arg_8]
0x1800ebeab  mov     rbp, [rsp+58h+arg_18]
0x1800ebeb0  add     rsp, 30h
0x1800ebeb4  pop     r14
0x1800ebeb6  pop     r13
0x1800ebeb8  pop     r12
0x1800ebeba  pop     rdi
0x1800ebebb  pop     rsi
0x1800ebebc  retn
```
