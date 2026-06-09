# Ofc::TComplexTypeHelper<ODF::ListLevelStyleNumber>::FillWriters(ODF::ListLevelStyleNumber const &,Ofc::CNamespaceDeclarationTracker &,Ofc::CWriterEmit &,Ofc::IWriterParams &)

- ea: `0x1800b6e04`
- end: `0x1800b7051`
- name: `?FillWriters@?$TComplexTypeHelper@VListLevelStyleNumber@ODF@@@Ofc@@SAXAEBVListLevelStyleNumber@ODF@@AEAVCNamespaceDeclarationTracker@2@AEAVCWriterEmit@2@AEAVIWriterParams@2@@Z`
- size: `589`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800ce4b0`

## callees

- `0x18001db8c`
- `0x18001dcf4`
- `0x18001dd94`
- `0x18002603c`
- `0x18002df74`
- `0x180062aa0`
- `0x1800b6e04`
- `0x1800ceb24`
- `0x1800cf934`
- `0x1800d19d4`
- `0x1801a80e0`

## import_xrefs

- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800b6e32`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800b6e5b`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800b6e8a`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800b6ea9`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800b6ecb`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800b6f03`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800b6f34`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800b6f56`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800b6f84`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800b6e32`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800b6e5b`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800b6e8a`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800b6ea9`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800b6ecb`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800b6f03`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800b6f34`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800b6f56`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800b6f84`
- `mso40uiWin32Client!__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ` at `0x1800b6fde`
- `mso40uiWin32Client!__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ` at `0x1800b6fde`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800b700f`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800b7034`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800b700f`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800b7034`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Ofc::TComplexTypeHelper<ODF::ListLevelStyleNumber>::FillWriters(
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
  if ( a1[3] )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 321);
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(L"style-name", 321, a1 + 3, a4);
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
    byte_1801F6288);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 321);
  Ofc::TAttrWriterHelper<unsigned int,Ofc::TSelfAdapter<unsigned int>,1>::Write(
    L"start-value",
    321,
    (char *)a1 + 76,
    a4,
    &dword_1801F628C);
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
0x1800b6e04  mov     [rsp+arg_8], rbx
0x1800b6e09  mov     [rsp+arg_18], rbp
0x1800b6e0e  push    rsi
0x1800b6e0f  push    rdi
0x1800b6e10  push    r12
0x1800b6e12  push    r13
0x1800b6e14  push    r14
0x1800b6e16  sub     rsp, 30h
0x1800b6e1a  mov     rdi, r9
0x1800b6e1d  mov     r14, r8
0x1800b6e20  mov     rsi, rdx
0x1800b6e23  mov     rbp, rcx
0x1800b6e26  mov     r12d, 141h
0x1800b6e2c  mov     edx, r12d
0x1800b6e2f  mov     rcx, rsi
0x1800b6e32  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800b6e38  lea     r8, [rbp+10h]
0x1800b6e3c  mov     r9, rdi
0x1800b6e3f  mov     edx, r12d
0x1800b6e42  lea     rcx, aLevel; "level"
0x1800b6e49  call    ?Write@?$TAttrWriterHelper@IV?$TSelfAdapter@I@Ofc@@$00@Ofc@@SAXPEB_WHAEBIAEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<uint,Ofc::TSelfAdapter<uint>,1>::Write(wchar_t const *,int,uint const &,Ofc::IWriterParams &)
0x1800b6e4e  cmp     qword ptr [rbp+18h], 0
0x1800b6e53  jz      short loc_1800B6E61
0x1800b6e55  mov     edx, r12d
0x1800b6e58  mov     rcx, rsi
0x1800b6e5b  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800b6e61  mov     r9, rdi
0x1800b6e64  lea     r8, [rbp+18h]
0x1800b6e68  mov     edx, r12d
0x1800b6e6b  lea     rcx, aStyleName; "style-name"
0x1800b6e72  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TOptionalAdapter@VCVarStr@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VCVarStr@Ofc@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::CVarStr> const &,Ofc::IWriterParams &)
0x1800b6e77  mov     r13d, 13Fh
0x1800b6e7d  cmp     qword ptr [rbp+20h], 0
0x1800b6e82  jz      short loc_1800B6E90
0x1800b6e84  mov     edx, r13d
0x1800b6e87  mov     rcx, rsi
0x1800b6e8a  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800b6e90  mov     r9, rdi
0x1800b6e93  lea     r8, [rbp+20h]
0x1800b6e97  call    ?Write@?$TAttrWriterHelper@V?$TVariant@VNumFormatIDsImpl@ODF@@@Ofc@@V?$TOptionalAdapter@V?$TVariant@VNumFormatIDsImpl@ODF@@@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@V?$TVariant@VNumFormatIDsImpl@ODF@@@Ofc@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::TVariant<ODF::NumFormatIDsImpl>,Ofc::TOptionalAdapter<Ofc::TVariant<ODF::NumFormatIDsImpl>>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::TVariant<ODF::NumFormatIDsImpl>> const &,Ofc::IWriterParams &)
0x1800b6e9c  cmp     qword ptr [rbp+28h], 0
0x1800b6ea1  jz      short loc_1800B6EAF
0x1800b6ea3  mov     edx, r13d
0x1800b6ea6  mov     rcx, rsi
0x1800b6ea9  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800b6eaf  mov     r9, rdi
0x1800b6eb2  lea     r8, [rbp+28h]
0x1800b6eb6  mov     edx, r13d
0x1800b6eb9  lea     rcx, aNumLetterSync; "num-letter-sync"
0x1800b6ec0  call    ?Write@?$TAttrWriterHelper@VOdfBoolean@ODF@@V?$TOptionalAdapter@VOdfBoolean@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VOdfBoolean@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::OdfBoolean,Ofc::TOptionalAdapter<ODF::OdfBoolean>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::OdfBoolean> const &,Ofc::IWriterParams &)
0x1800b6ec5  mov     edx, r13d
0x1800b6ec8  mov     rcx, rsi
0x1800b6ecb  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800b6ed1  lea     rbx, dword_1801DBD74
0x1800b6ed8  mov     [rsp+58h+arg_0], rbx
0x1800b6edd  lea     r8, [rbp+30h]
0x1800b6ee1  lea     rax, [rsp+58h+arg_0]
0x1800b6ee6  mov     [rsp+58h+var_38], rax
0x1800b6eeb  mov     r9, rdi
0x1800b6eee  mov     edx, r13d
0x1800b6ef1  lea     rcx, aNumPrefix; "num-prefix"
0x1800b6ef8  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TSelfAdapter@VCVarStr@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBVCVarStr@2@AEAVIWriterParams@2@PEBV32@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(wchar_t const *,int,Ofc::CVarStr const &,Ofc::IWriterParams &,Ofc::CVarStr const *)
0x1800b6efd  mov     edx, r13d
0x1800b6f00  mov     rcx, rsi
0x1800b6f03  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800b6f09  mov     [rsp+58h+arg_10], rbx
0x1800b6f0e  lea     r8, [rbp+38h]
0x1800b6f12  lea     rax, [rsp+58h+arg_10]
0x1800b6f17  mov     [rsp+58h+var_38], rax
0x1800b6f1c  mov     r9, rdi
0x1800b6f1f  mov     edx, r13d
0x1800b6f22  lea     rcx, aNumSuffix; "num-suffix"
0x1800b6f29  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TSelfAdapter@VCVarStr@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBVCVarStr@2@AEAVIWriterParams@2@PEBV32@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(wchar_t const *,int,Ofc::CVarStr const &,Ofc::IWriterParams &,Ofc::CVarStr const *)
0x1800b6f2e  mov     edx, r13d
0x1800b6f31  mov     rcx, rsi
0x1800b6f34  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800b6f3a  lea     r8, [rbp+40h]
0x1800b6f3e  mov     r9, rdi
0x1800b6f41  mov     edx, r13d
0x1800b6f44  lea     rcx, aNumListFormatN; "num-list-format-name"
0x1800b6f4b  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TSelfAdapter@VCVarStr@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBVCVarStr@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(wchar_t const *,int,Ofc::CVarStr const &,Ofc::IWriterParams &)
0x1800b6f50  mov     edx, r12d
0x1800b6f53  mov     rcx, rsi
0x1800b6f56  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800b6f5c  lea     r8, [rbp+48h]
0x1800b6f60  lea     rax, byte_1801F6288
0x1800b6f67  mov     [rsp+58h+var_38], rax
0x1800b6f6c  mov     r9, rdi
0x1800b6f6f  mov     edx, r12d
0x1800b6f72  lea     rcx, aDisplayLevels; "display-levels"
0x1800b6f79  call    ?Write@?$TAttrWriterHelper@IV?$TSelfAdapter@I@Ofc@@$00@Ofc@@SAXPEB_WHAEBIAEAVIWriterParams@2@PEBI@Z; Ofc::TAttrWriterHelper<uint,Ofc::TSelfAdapter<uint>,1>::Write(wchar_t const *,int,uint const &,Ofc::IWriterParams &,uint const *)
0x1800b6f7e  mov     edx, r12d
0x1800b6f81  mov     rcx, rsi
0x1800b6f84  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800b6f8a  lea     r8, [rbp+4Ch]
0x1800b6f8e  lea     rax, dword_1801F628C
0x1800b6f95  mov     [rsp+58h+var_38], rax
0x1800b6f9a  mov     r9, rdi
0x1800b6f9d  mov     edx, r12d
0x1800b6fa0  lea     rcx, aStartValue; "start-value"
0x1800b6fa7  call    ?Write@?$TAttrWriterHelper@IV?$TSelfAdapter@I@Ofc@@$00@Ofc@@SAXPEB_WHAEBIAEAVIWriterParams@2@PEBI@Z; Ofc::TAttrWriterHelper<uint,Ofc::TSelfAdapter<uint>,1>::Write(wchar_t const *,int,uint const &,Ofc::IWriterParams &,uint const *)
0x1800b6fac  mov     rax, [r14]
0x1800b6faf  mov     rdx, [rdi+10h]
0x1800b6fb3  mov     rcx, r14
0x1800b6fb6  mov     rax, [rax]
0x1800b6fb9  call    cs:__guard_dispatch_icall_fptr
0x1800b6fbf  mov     r9, rdi
0x1800b6fc2  mov     r8, rbp
0x1800b6fc5  call    ?Write@?$TCompElemWriterHelper@VStyleListLevelPropertiesContent@ODF@@V?$TOptionalAdapter@VStyleListLevelPropertiesContent@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VStyleListLevelPropertiesContent@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TCompElemWriterHelper<ODF::StyleListLevelPropertiesContent,Ofc::TOptionalAdapter<ODF::StyleListLevelPropertiesContent>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::StyleListLevelPropertiesContent> const &,Ofc::IWriterParams &)
0x1800b6fca  mov     rcx, [rbp+8]
0x1800b6fce  test    rcx, rcx
0x1800b6fd1  jz      short loc_1800B6FDB
0x1800b6fd3  mov     rdx, rdi
0x1800b6fd6  call    ??$TCompFillWritersHelper@VStyleTextPropertiesContent@ODF@@@Ofc@@YAXAEBVStyleTextPropertiesContent@ODF@@AEAVIWriterParams@0@HPEB_W@Z; Ofc::TCompFillWritersHelper<ODF::StyleTextPropertiesContent>(ODF::StyleTextPropertiesContent const &,Ofc::IWriterParams &,int,wchar_t const *)
0x1800b6fdb  mov     rcx, r14
0x1800b6fde  call    cs:__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ; Ofc::CWriterEmit::EmitEndElement(void)
0x1800b6fe4  nop
0x1800b6fe5  or      edi, 0FFFFFFFFh
0x1800b6fe8  cmp     cs:dword_1801DBD6C, 0
0x1800b6fef  jz      short loc_1800B7016
0x1800b6ff1  cmp     cs:dword_1801DBD68, 1
0x1800b6ff8  jz      short loc_1800B7008
0x1800b6ffa  mov     eax, edi
0x1800b6ffc  lock xadd cs:dword_1801DBD68, eax
0x1800b7004  add     eax, edi
0x1800b7006  jnz     short loc_1800B7016
0x1800b7008  lea     rcx, dword_1801DBD68
0x1800b700f  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1800b7015  nop
0x1800b7016  lea     rcx, [rbx-0Ch]
0x1800b701a  cmp     dword ptr [rcx+4], 0
0x1800b701e  jz      short loc_1800B703A
0x1800b7020  cmp     dword ptr [rcx], 1
0x1800b7023  jz      short loc_1800B702F
0x1800b7025  mov     eax, edi
0x1800b7027  lock xadd [rcx], eax
0x1800b702b  add     eax, edi
0x1800b702d  jnz     short loc_1800B703A
0x1800b702f  test    rcx, rcx
0x1800b7032  jz      short loc_1800B703A
0x1800b7034  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1800b703a  mov     rbx, [rsp+58h+arg_8]
0x1800b703f  mov     rbp, [rsp+58h+arg_18]
0x1800b7044  add     rsp, 30h
0x1800b7048  pop     r14
0x1800b704a  pop     r13
0x1800b704c  pop     r12
0x1800b704e  pop     rdi
0x1800b704f  pop     rsi
0x1800b7050  retn
```
