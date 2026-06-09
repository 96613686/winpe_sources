# Ofc::TComplexTypeHelper<ODF::BackgroundImage>::FillWriters(ODF::BackgroundImage const &,Ofc::CNamespaceDeclarationTracker &,Ofc::CWriterEmit &,Ofc::IWriterParams &)

- ea: `0x1800b5404`
- end: `0x1800b5688`
- name: `?FillWriters@?$TComplexTypeHelper@VBackgroundImage@ODF@@@Ofc@@SAXAEBVBackgroundImage@ODF@@AEAVCNamespaceDeclarationTracker@2@AEAVCWriterEmit@2@AEAVIWriterParams@2@@Z`
- size: `644`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180093604`

## callees

- `0x18001db8c`
- `0x18001dd94`
- `0x180026300`
- `0x18002e48c`
- `0x18002e5c8`
- `0x18002e7a8`
- `0x18002e844`
- `0x1800b5404`
- `0x1800cd658`
- `0x1801a80e0`

## import_xrefs

- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800b542c`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800b54bd`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800b5550`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800b558c`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800b55b7`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800b55d9`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800b560c`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800b562a`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800b542c`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800b54bd`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800b5550`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800b558c`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800b55b7`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800b55d9`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800b560c`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800b562a`
- `mso40uiWin32Client!__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ` at `0x1800b5669`
- `mso40uiWin32Client!__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ` at `0x1800b5669`
- `mso40uiWin32Client!__imp_?WriteAttrHelper@Ofc@@YAXPEB_WHAEAVIWriterParams@1@AEBV?$TFixedVarStr@$0ICF@@1@@Z` at `0x1800b54af`
- `mso40uiWin32Client!__imp_?WriteAttrHelper@Ofc@@YAXPEB_WHAEAVIWriterParams@1@AEBV?$TFixedVarStr@$0ICF@@1@@Z` at `0x1800b5545`
- `mso40uiWin32Client!__imp_?WriteAttrHelper@Ofc@@YAXPEB_WHAEAVIWriterParams@1@AEBV?$TFixedVarStr@$0ICF@@1@@Z` at `0x1800b54af`
- `mso40uiWin32Client!__imp_?WriteAttrHelper@Ofc@@YAXPEB_WHAEAVIWriterParams@1@AEBV?$TFixedVarStr@$0ICF@@1@@Z` at `0x1800b5545`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800b5475`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800b54e6`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800b5475`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800b54e6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Ofc::TComplexTypeHelper<ODF::BackgroundImage>::FillWriters(
        __int64 a1,
        Ofc::CNamespaceDeclarationTracker *a2,
        Ofc::CWriterEmit *a3,
        __int64 a4)
{
  void *v8; // rdx
  __int64 v9; // rbx
  Mso::Memory *v10; // rcx
  void *v11; // rdx
  Mso::Memory *v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rdx
  int v15; // edx
  int v16; // ecx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rcx
  _QWORD v21[11]; // [rsp+30h] [rbp-58h] BYREF
  int v22; // [rsp+90h] [rbp+8h] BYREF
  const wchar_t *v23; // [rsp+A0h] [rbp+18h] BYREF

  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 319);
  if ( *(_DWORD *)(a1 + 8) != 1 || *(_BYTE *)(a4 + 4232) )
  {
    v9 = a4 + 32;
    v10 = (Mso::Memory *)(*(_QWORD *)(a4 + 32) - 12LL);
    if ( *((_DWORD *)v10 + 1)
      && (*(_DWORD *)v10 == 1 || _InterlockedExchangeAdd((volatile signed __int32 *)v10, 0xFFFFFFFF) == 1)
      && v10 )
    {
      Mso::Memory::Free(v10, v8);
    }
    *(_QWORD *)v9 = &dword_1801DBD74;
    *(_DWORD *)(a4 + 56) = 0;
    *(_WORD *)(a4 + 60) = 0;
    Ofc::TSimpleTypeHelper<enum ODF::Repeat>::ToString(a1 + 8, a4, a4 + 32);
    Ofc::WriteAttrHelper(L"repeat", 319, a4, a4 + 32);
  }
  else
  {
    v9 = a4 + 32;
  }
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 319);
  v12 = (Mso::Memory *)(*(_QWORD *)v9 - 12LL);
  if ( *((_DWORD *)v12 + 1)
    && (*(_DWORD *)v12 == 1 || _InterlockedExchangeAdd((volatile signed __int32 *)v12, 0xFFFFFFFF) == 1)
    && v12 )
  {
    Mso::Memory::Free(v12, v11);
  }
  *(_QWORD *)v9 = &dword_1801DBD74;
  *(_DWORD *)(v9 + 24) = 0;
  *(_WORD *)(v9 + 28) = 0;
  v21[0] = &Ofc::VariantVisitor<Ofc::TVariant<ODF::StyleBackgroundImageAttlistPositionIDsImpl>>::`vftable';
  v21[1] = v9;
  v21[2] = a4;
  v13 = *(_QWORD *)(a1 + 24);
  if ( v13 )
    (*(void (__fastcall **)(__int64, _QWORD *))(v13 + 40))(a1 + 16, v21);
  Ofc::WriteAttrHelper(L"position", 319, a4, v9);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 319);
  v23 = &dword_1801DBD74;
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(
    (unsigned int)L"filter-name",
    319,
    a1 + 32,
    a4,
    (__int64)&v23);
  if ( *(_QWORD *)(a1 + 40) )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 307);
  Ofc::TAttrWriterHelper<ODF::ZeroToHundredPercent,Ofc::TOptionalAdapter<ODF::ZeroToHundredPercent>,0>::Write(
    L"opacity",
    v14,
    a1 + 40,
    a4);
  if ( *(_QWORD *)(a1 + 48) )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 323);
  Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(L"href", 323, a1 + 48, a4);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 323);
  v22 = 0;
  Ofc::TAttrWriterHelper<enum ODF::XlinkType,Ofc::TSelfAdapter<enum ODF::XlinkType>,1>::Write(
    v16,
    v15,
    a1 + 56,
    a4,
    (__int64)&v22);
  if ( *(_QWORD *)(a1 + 64) )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 323);
  Ofc::TAttrWriterHelper<enum ODF::XlinkShow,Ofc::TOptionalAdapter<enum ODF::XlinkShow>,0>::Write(v18, v17, a1 + 64, a4);
  if ( *(_QWORD *)(a1 + 72) )
    Ofc::CNamespaceDeclarationTracker::AddUri(a2, 323);
  Ofc::TAttrWriterHelper<enum ODF::XlinkActuate1Actuate,Ofc::TOptionalAdapter<enum ODF::XlinkActuate1Actuate>,0>::Write(
    v20,
    v19,
    a1 + 72,
    a4);
  (**(void (__fastcall ***)(Ofc::CWriterEmit *, _QWORD))a3)(a3, *(_QWORD *)(a4 + 16));
  Ofc::TSimpleElemWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(L"binary-data", 300, a1, a4);
  Ofc::CWriterEmit::EmitEndElement(a3);
}

```

## disassembly

```asm
0x1800b5404  mov     [rsp+arg_8], rbx
0x1800b5409  push    rbp
0x1800b540a  push    rsi
0x1800b540b  push    rdi
0x1800b540c  push    r12
0x1800b540e  push    r13
0x1800b5410  push    r14
0x1800b5412  push    r15
0x1800b5414  sub     rsp, 50h
0x1800b5418  mov     rdi, r9
0x1800b541b  mov     r15, r8
0x1800b541e  mov     rsi, rdx
0x1800b5421  mov     rbp, rcx
0x1800b5424  mov     edx, 13Fh
0x1800b5429  mov     rcx, rsi
0x1800b542c  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800b5432  or      r13d, 0FFFFFFFFh
0x1800b5436  xor     r12d, r12d
0x1800b5439  cmp     dword ptr [rbp+8], 1
0x1800b543d  jnz     short loc_1800B544E
0x1800b543f  cmp     [rdi+1088h], r12b
0x1800b5446  jnz     short loc_1800B544E
0x1800b5448  lea     rbx, [rdi+20h]
0x1800b544c  jmp     short loc_1800B54B5
0x1800b544e  lea     rbx, [rdi+20h]
0x1800b5452  mov     rcx, [rbx]
0x1800b5455  sub     rcx, 0Ch
0x1800b5459  cmp     [rcx+4], r12d
0x1800b545d  jz      short loc_1800B547B
0x1800b545f  cmp     dword ptr [rcx], 1
0x1800b5462  jz      short loc_1800B5470
0x1800b5464  mov     eax, r13d
0x1800b5467  lock xadd [rcx], eax
0x1800b546b  add     eax, r13d
0x1800b546e  jnz     short loc_1800B547B
0x1800b5470  test    rcx, rcx
0x1800b5473  jz      short loc_1800B547B
0x1800b5475  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1800b547b  lea     rax, dword_1801DBD74
0x1800b5482  mov     [rbx], rax
0x1800b5485  mov     [rbx+18h], r12d
0x1800b5489  mov     [rbx+1Ch], r12w
0x1800b548e  mov     r8, rbx
0x1800b5491  mov     rdx, rdi
0x1800b5494  lea     rcx, [rbp+8]
0x1800b5498  call    ?ToString@?$TSimpleTypeHelper@W4Repeat@ODF@@@Ofc@@SAXAEBW4Repeat@ODF@@PEAVIWriterParams@2@AEAV?$TFixedVarStr@$0ICF@@2@@Z; Ofc::TSimpleTypeHelper<ODF::Repeat>::ToString(ODF::Repeat const &,Ofc::IWriterParams *,Ofc::TFixedVarStr<2085> &)
0x1800b549d  mov     r9, rbx
0x1800b54a0  mov     r8, rdi
0x1800b54a3  mov     edx, 13Fh
0x1800b54a8  lea     rcx, aRepeat; "repeat"
0x1800b54af  call    cs:__imp_?WriteAttrHelper@Ofc@@YAXPEB_WHAEAVIWriterParams@1@AEBV?$TFixedVarStr@$0ICF@@1@@Z; Ofc::WriteAttrHelper(wchar_t const *,int,Ofc::IWriterParams &,Ofc::TFixedVarStr<2085> const &)
0x1800b54b5  mov     edx, 13Fh
0x1800b54ba  mov     rcx, rsi
0x1800b54bd  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800b54c3  mov     rcx, [rbx]
0x1800b54c6  sub     rcx, 0Ch
0x1800b54ca  cmp     [rcx+4], r12d
0x1800b54ce  jz      short loc_1800B54EC
0x1800b54d0  cmp     dword ptr [rcx], 1
0x1800b54d3  jz      short loc_1800B54E1
0x1800b54d5  mov     eax, r13d
0x1800b54d8  lock xadd [rcx], eax
0x1800b54dc  add     eax, r13d
0x1800b54df  jnz     short loc_1800B54EC
0x1800b54e1  test    rcx, rcx
0x1800b54e4  jz      short loc_1800B54EC
0x1800b54e6  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1800b54ec  lea     r13, dword_1801DBD74
0x1800b54f3  mov     [rbx], r13
0x1800b54f6  mov     [rbx+18h], r12d
0x1800b54fa  mov     [rbx+1Ch], r12w
0x1800b54ff  lea     rax, ??_7?$VariantVisitor@V?$TVariant@VStyleBackgroundImageAttlistPositionIDsImpl@ODF@@@Ofc@@@Ofc@@6B@; const Ofc::VariantVisitor<Ofc::TVariant<ODF::StyleBackgroundImageAttlistPositionIDsImpl>>::`vftable'
0x1800b5506  mov     [rsp+88h+var_58], rax
0x1800b550b  mov     [rsp+88h+var_50], rbx
0x1800b5510  mov     [rsp+88h+var_48], rdi
0x1800b5515  mov     rax, [rbp+18h]
0x1800b5519  test    rax, rax
0x1800b551c  jz      short loc_1800B5531
0x1800b551e  lea     rdx, [rsp+88h+var_58]
0x1800b5523  lea     rcx, [rbp+10h]
0x1800b5527  mov     rax, [rax+28h]
0x1800b552b  call    cs:__guard_dispatch_icall_fptr
0x1800b5531  mov     r9, rbx
0x1800b5534  mov     r8, rdi
0x1800b5537  mov     ebx, 13Fh
0x1800b553c  mov     edx, ebx
0x1800b553e  lea     rcx, aPosition; "position"
0x1800b5545  call    cs:__imp_?WriteAttrHelper@Ofc@@YAXPEB_WHAEAVIWriterParams@1@AEBV?$TFixedVarStr@$0ICF@@1@@Z; Ofc::WriteAttrHelper(wchar_t const *,int,Ofc::IWriterParams &,Ofc::TFixedVarStr<2085> const &)
0x1800b554b  mov     edx, ebx
0x1800b554d  mov     rcx, rsi
0x1800b5550  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800b5556  mov     [rsp+88h+arg_10], r13
0x1800b555e  lea     r8, [rbp+20h]
0x1800b5562  lea     rax, [rsp+88h+arg_10]
0x1800b556a  mov     [rsp+88h+var_68], rax
0x1800b556f  mov     r9, rdi
0x1800b5572  mov     edx, ebx
0x1800b5574  lea     rcx, aFilterName; "filter-name"
0x1800b557b  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TSelfAdapter@VCVarStr@Ofc@@@2@$00@Ofc@@SAXPEB_WHAEBVCVarStr@2@AEAVIWriterParams@2@PEBV32@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TSelfAdapter<Ofc::CVarStr>,1>::Write(wchar_t const *,int,Ofc::CVarStr const &,Ofc::IWriterParams &,Ofc::CVarStr const *)
0x1800b5580  cmp     [rbp+28h], r12
0x1800b5584  jz      short loc_1800B5592
0x1800b5586  lea     edx, [rbx-0Ch]
0x1800b5589  mov     rcx, rsi
0x1800b558c  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800b5592  mov     r9, rdi
0x1800b5595  lea     r8, [rbp+28h]
0x1800b5599  lea     rcx, aOpacity; "opacity"
0x1800b55a0  call    ?Write@?$TAttrWriterHelper@VZeroToHundredPercent@ODF@@V?$TOptionalAdapter@VZeroToHundredPercent@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VZeroToHundredPercent@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::ZeroToHundredPercent,Ofc::TOptionalAdapter<ODF::ZeroToHundredPercent>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::ZeroToHundredPercent> const &,Ofc::IWriterParams &)
0x1800b55a5  mov     r14d, 143h
0x1800b55ab  cmp     [rbp+30h], r12
0x1800b55af  jz      short loc_1800B55BD
0x1800b55b1  mov     edx, r14d
0x1800b55b4  mov     rcx, rsi
0x1800b55b7  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800b55bd  mov     r9, rdi
0x1800b55c0  lea     r8, [rbp+30h]
0x1800b55c4  mov     edx, r14d
0x1800b55c7  lea     rcx, aHref; "href"
0x1800b55ce  call    ?Write@?$TAttrWriterHelper@VCVarStr@Ofc@@V?$TOptionalAdapter@VCVarStr@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VCVarStr@Ofc@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::CVarStr> const &,Ofc::IWriterParams &)
0x1800b55d3  mov     edx, r14d
0x1800b55d6  mov     rcx, rsi
0x1800b55d9  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800b55df  mov     [rsp+88h+arg_0], r12d
0x1800b55e7  lea     r8, [rbp+38h]
0x1800b55eb  lea     rax, [rsp+88h+arg_0]
0x1800b55f3  mov     [rsp+88h+var_68], rax
0x1800b55f8  mov     r9, rdi
0x1800b55fb  call    ?Write@?$TAttrWriterHelper@W4XlinkType@ODF@@V?$TSelfAdapter@W4XlinkType@ODF@@@Ofc@@$00@Ofc@@SAXPEB_WHAEBW4XlinkType@ODF@@AEAVIWriterParams@2@PEBW434@@Z; Ofc::TAttrWriterHelper<ODF::XlinkType,Ofc::TSelfAdapter<ODF::XlinkType>,1>::Write(wchar_t const *,int,ODF::XlinkType const &,Ofc::IWriterParams &,ODF::XlinkType const *)
0x1800b5600  cmp     [rbp+40h], r12
0x1800b5604  jz      short loc_1800B5612
0x1800b5606  mov     edx, r14d
0x1800b5609  mov     rcx, rsi
0x1800b560c  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800b5612  mov     r9, rdi
0x1800b5615  lea     r8, [rbp+40h]
0x1800b5619  call    ?Write@?$TAttrWriterHelper@W4XlinkShow@ODF@@V?$TOptionalAdapter@W4XlinkShow@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@W4XlinkShow@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::XlinkShow,Ofc::TOptionalAdapter<ODF::XlinkShow>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::XlinkShow> const &,Ofc::IWriterParams &)
0x1800b561e  cmp     [rbp+48h], r12
0x1800b5622  jz      short loc_1800B5630
0x1800b5624  mov     edx, r14d
0x1800b5627  mov     rcx, rsi
0x1800b562a  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800b5630  mov     r9, rdi
0x1800b5633  lea     r8, [rbp+48h]
0x1800b5637  call    ?Write@?$TAttrWriterHelper@W4XlinkActuate1Actuate@ODF@@V?$TOptionalAdapter@W4XlinkActuate1Actuate@ODF@@@Ofc@@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@W4XlinkActuate1Actuate@ODF@@@2@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::XlinkActuate1Actuate,Ofc::TOptionalAdapter<ODF::XlinkActuate1Actuate>,0>::Write(wchar_t const *,int,Ofc::TOptional<ODF::XlinkActuate1Actuate> const &,Ofc::IWriterParams &)
0x1800b563c  mov     rax, [r15]
0x1800b563f  mov     rdx, [rdi+10h]
0x1800b5643  mov     rcx, r15
0x1800b5646  mov     rax, [rax]
0x1800b5649  call    cs:__guard_dispatch_icall_fptr
0x1800b564f  mov     r9, rdi
0x1800b5652  mov     r8, rbp
0x1800b5655  mov     edx, 12Ch
0x1800b565a  lea     rcx, aBinaryData; "binary-data"
0x1800b5661  call    ?Write@?$TSimpleElemWriterHelper@VCVarStr@Ofc@@V?$TOptionalAdapter@VCVarStr@Ofc@@@2@$0A@@Ofc@@SAXPEB_WHAEBV?$TOptional@VCVarStr@Ofc@@@2@AEAVIWriterParams@2@PEBVCVarStr@2@@Z; Ofc::TSimpleElemWriterHelper<Ofc::CVarStr,Ofc::TOptionalAdapter<Ofc::CVarStr>,0>::Write(wchar_t const *,int,Ofc::TOptional<Ofc::CVarStr> const &,Ofc::IWriterParams &,Ofc::CVarStr const *)
0x1800b5666  mov     rcx, r15
0x1800b5669  call    cs:__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ; Ofc::CWriterEmit::EmitEndElement(void)
0x1800b566f  nop
0x1800b5670  mov     rbx, [rsp+88h+arg_8]
0x1800b5678  add     rsp, 50h
0x1800b567c  pop     r15
0x1800b567e  pop     r14
0x1800b5680  pop     r13
0x1800b5682  pop     r12
0x1800b5684  pop     rdi
0x1800b5685  pop     rsi
0x1800b5686  pop     rbp
0x1800b5687  retn
```
