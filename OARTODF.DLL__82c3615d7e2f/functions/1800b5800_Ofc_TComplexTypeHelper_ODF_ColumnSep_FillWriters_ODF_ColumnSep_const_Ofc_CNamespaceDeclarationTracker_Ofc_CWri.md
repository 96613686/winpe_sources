# Ofc::TComplexTypeHelper<ODF::ColumnSep>::FillWriters(ODF::ColumnSep const &,Ofc::CNamespaceDeclarationTracker &,Ofc::CWriterEmit &,Ofc::IWriterParams &)

- ea: `0x1800b5800`
- end: `0x1800b5a66`
- name: `?FillWriters@?$TComplexTypeHelper@VColumnSep@ODF@@@Ofc@@SAXAEBVColumnSep@ODF@@AEAVCNamespaceDeclarationTracker@2@AEAVCWriterEmit@2@AEAVIWriterParams@2@@Z`
- size: `614`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800b5a68`

## callees

- `0x180009df4`
- `0x180054a7c`
- `0x180054b20`
- `0x1800b5800`
- `0x1800cd7c0`
- `0x1800f5fe8`
- `0x1800f7950`
- `0x1800f84c4`
- `0x1800fd598`
- `0x1801a80e0`

## import_xrefs

- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800b5832`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800b5851`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800b588c`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800b5941`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800b59c6`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800b5832`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800b5851`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800b588c`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800b5941`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800b59c6`
- `mso40uiWin32Client!__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ` at `0x1800b5a42`
- `mso40uiWin32Client!__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ` at `0x1800b5a42`
- `mso40uiWin32Client!__imp_?WriteAttrHelper@Ofc@@YAXPEB_WHAEAVIWriterParams@1@AEBV?$TFixedVarStr@$0ICF@@1@@Z` at `0x1800b5936`
- `mso40uiWin32Client!__imp_?WriteAttrHelper@Ofc@@YAXPEB_WHAEAVIWriterParams@1@AEBV?$TFixedVarStr@$0ICF@@1@@Z` at `0x1800b59b8`
- `mso40uiWin32Client!__imp_?WriteAttrHelper@Ofc@@YAXPEB_WHAEAVIWriterParams@1@AEBV?$TFixedVarStr@$0ICF@@1@@Z` at `0x1800b5a26`
- `mso40uiWin32Client!__imp_?WriteAttrHelper@Ofc@@YAXPEB_WHAEAVIWriterParams@1@AEBV?$TFixedVarStr@$0ICF@@1@@Z` at `0x1800b5936`
- `mso40uiWin32Client!__imp_?WriteAttrHelper@Ofc@@YAXPEB_WHAEAVIWriterParams@1@AEBV?$TFixedVarStr@$0ICF@@1@@Z` at `0x1800b59b8`
- `mso40uiWin32Client!__imp_?WriteAttrHelper@Ofc@@YAXPEB_WHAEAVIWriterParams@1@AEBV?$TFixedVarStr@$0ICF@@1@@Z` at `0x1800b5a26`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800b5902`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800b5981`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800b59ef`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800b5902`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800b5981`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800b59ef`

## pseudocode

```c
void __fastcall Ofc::TComplexTypeHelper<ODF::ColumnSep>::FillWriters(
        __int64 a1,
        Ofc::CNamespaceDeclarationTracker *a2,
        Ofc::CWriterEmit *a3,
        __int64 a4)
{
  const wchar_t *v8; // rdx
  int v9; // eax
  void *v10; // rdx
  __int64 v11; // rbx
  Mso::Memory *v12; // rcx
  void *v13; // rdx
  __int64 v14; // rsi
  Mso::Memory *v15; // rcx
  void *v16; // rdx
  Mso::Memory *v17; // rcx
  _BYTE v18[16]; // [rsp+30h] [rbp-38h] BYREF

  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 319);
  Ofc::TAttrWriterHelper<ODF::PositiveLength,Ofc::TSelfAdapter<ODF::PositiveLength>,1>::Write(L"width", 319, a1, a4);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 319);
  ODF::Percent::Percent((ODF::Percent *)v18, L"100%");
  Ofc::TAttrWriterHelper<ODF::Percent,Ofc::TSelfAdapter<ODF::Percent>,1>::Write(
    (unsigned int)L"height",
    319,
    a1 + 16,
    a4,
    (__int64)v18);
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 319);
  v9 = Ofc::CchWzLen((Ofc *)L"#000000", v8);
  Ofc::TSimpleTypeHelper<ODF::Color>::FLoad(L"#000000", v9);
  if ( *(_DWORD *)(a1 + 32) || *(_BYTE *)(a4 + 4232) )
  {
    v11 = a4 + 32;
    v12 = (Mso::Memory *)(*(_QWORD *)(a4 + 32) - 12LL);
    if ( *((_DWORD *)v12 + 1)
      && (*(_DWORD *)v12 == 1 || _InterlockedExchangeAdd((volatile signed __int32 *)v12, 0xFFFFFFFF) == 1)
      && v12 )
    {
      Mso::Memory::Free(v12, v10);
    }
    *(_QWORD *)v11 = &dword_1801DBD74;
    *(_DWORD *)(a4 + 56) = 0;
    *(_WORD *)(a4 + 60) = 0;
    Ofc::TSimpleTypeHelper<ODF::Color>::ToString(a1 + 32, v10, a4 + 32);
    Ofc::WriteAttrHelper(L"color", 319, a4, a4 + 32);
  }
  else
  {
    v11 = a4 + 32;
  }
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 319);
  if ( *(_DWORD *)(a1 + 36) != 1 || *(_BYTE *)(a4 + 4232) )
  {
    v14 = v11;
    v15 = (Mso::Memory *)(*(_QWORD *)v11 - 12LL);
    if ( *((_DWORD *)v15 + 1) )
    {
      if ( *(_DWORD *)v15 == 1 )
        goto LABEL_16;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v15, 0xFFFFFFFF) == 1 )
      {
        v14 = a4 + 32;
LABEL_16:
        if ( v15 )
          Mso::Memory::Free(v15, v13);
      }
    }
    *(_QWORD *)v11 = &dword_1801DBD74;
    *(_DWORD *)(v11 + 24) = 0;
    *(_WORD *)(v11 + 28) = 0;
    Ofc::TSimpleTypeHelper<enum ODF::StyleEnum>::ToString(a1 + 36, a4, v11);
    Ofc::WriteAttrHelper(L"style", 319, a4, v11);
    v11 = v14;
  }
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 319);
  v17 = (Mso::Memory *)(*(_QWORD *)v11 - 12LL);
  if ( *((_DWORD *)v17 + 1)
    && (*(_DWORD *)v17 == 1 || _InterlockedExchangeAdd((volatile signed __int32 *)v17, 0xFFFFFFFF) == 1) )
  {
    if ( v17 )
      Mso::Memory::Free(v17, v16);
  }
  *(_QWORD *)v11 = &dword_1801DBD74;
  *(_DWORD *)(v11 + 24) = 0;
  *(_WORD *)(v11 + 28) = 0;
  Ofc::TSimpleTypeHelper<enum ODF::StyleColumnSepAttlistVerticalAlign>::ToString(a1 + 40, a4, v11);
  Ofc::WriteAttrHelper(L"vertical-align", 319, a4, v11);
  (**(void (__fastcall ***)(Ofc::CWriterEmit *, _QWORD))a3)(a3, *(_QWORD *)(a4 + 16));
  Ofc::CWriterEmit::EmitEndElement(a3);
}

```

## disassembly

```asm
0x1800b5800  mov     [rsp+arg_0], rbx
0x1800b5805  mov     [rsp+arg_8], rbp
0x1800b580a  mov     [rsp+arg_18], rsi
0x1800b580f  push    rdi
0x1800b5810  push    r12
0x1800b5812  push    r13
0x1800b5814  push    r14
0x1800b5816  push    r15
0x1800b5818  sub     rsp, 40h
0x1800b581c  mov     r14, rdx
0x1800b581f  mov     r13, rcx
0x1800b5822  mov     ebp, 13Fh
0x1800b5827  mov     rcx, r14
0x1800b582a  mov     edx, ebp
0x1800b582c  mov     rdi, r9
0x1800b582f  mov     r15, r8
0x1800b5832  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800b5838  mov     r9, rdi
0x1800b583b  lea     rcx, aWidth; "width"
0x1800b5842  mov     r8, r13
0x1800b5845  mov     edx, ebp
0x1800b5847  call    ?Write@?$TAttrWriterHelper@VPositiveLength@ODF@@V?$TSelfAdapter@VPositiveLength@ODF@@@Ofc@@$00@Ofc@@SAXPEB_WHAEBVPositiveLength@ODF@@AEAVIWriterParams@2@@Z; Ofc::TAttrWriterHelper<ODF::PositiveLength,Ofc::TSelfAdapter<ODF::PositiveLength>,1>::Write(wchar_t const *,int,ODF::PositiveLength const &,Ofc::IWriterParams &)
0x1800b584c  mov     edx, ebp
0x1800b584e  mov     rcx, r14
0x1800b5851  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800b5857  lea     rdx, a100; "100%"
0x1800b585e  lea     rcx, [rsp+68h+var_38]; this
0x1800b5863  call    ??0Percent@ODF@@QEAA@PEB_W@Z; ODF::Percent::Percent(wchar_t const *)
0x1800b5868  lea     rax, [rsp+68h+var_38]
0x1800b586d  mov     r9, rdi
0x1800b5870  lea     r8, [r13+10h]
0x1800b5874  mov     [rsp+68h+var_48], rax
0x1800b5879  mov     edx, ebp
0x1800b587b  lea     rcx, aHeight; "height"
0x1800b5882  call    ?Write@?$TAttrWriterHelper@VPercent@ODF@@V?$TSelfAdapter@VPercent@ODF@@@Ofc@@$00@Ofc@@SAXPEB_WHAEBVPercent@ODF@@AEAVIWriterParams@2@PEBV34@@Z; Ofc::TAttrWriterHelper<ODF::Percent,Ofc::TSelfAdapter<ODF::Percent>,1>::Write(wchar_t const *,int,ODF::Percent const &,Ofc::IWriterParams &,ODF::Percent const *)
0x1800b5887  mov     edx, ebp
0x1800b5889  mov     rcx, r14
0x1800b588c  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800b5892  xor     r12d, r12d
0x1800b5895  lea     rcx, a000000; "#000000"
0x1800b589c  mov     [rsp+68h+arg_10], r12d
0x1800b58a4  call    ?CchWzLen@Ofc@@YAHPEB_W@Z; Ofc::CchWzLen(wchar_t const *)
0x1800b58a9  mov     edx, eax; int
0x1800b58ab  lea     r8, [rsp+68h+arg_10]
0x1800b58b3  lea     rcx, a000000; "#000000"
0x1800b58ba  call    ?FLoad@?$TSimpleTypeHelper@VColor@ODF@@@Ofc@@SA_NPEB_WHAEAVColor@ODF@@@Z; Ofc::TSimpleTypeHelper<ODF::Color>::FLoad(wchar_t const *,int,ODF::Color &)
0x1800b58bf  mov     eax, [r13+20h]
0x1800b58c3  cmp     [rsp+68h+arg_10], eax
0x1800b58ca  jnz     short loc_1800B58DB
0x1800b58cc  cmp     [rdi+1088h], r12b
0x1800b58d3  jnz     short loc_1800B58DB
0x1800b58d5  lea     rbx, [rdi+20h]
0x1800b58d9  jmp     short loc_1800B593C
0x1800b58db  lea     rbx, [rdi+20h]
0x1800b58df  mov     rcx, [rbx]
0x1800b58e2  sub     rcx, 0Ch
0x1800b58e6  cmp     [rcx+4], r12d
0x1800b58ea  jz      short loc_1800B5908
0x1800b58ec  cmp     dword ptr [rcx], 1
0x1800b58ef  jz      short loc_1800B58FD
0x1800b58f1  or      eax, 0FFFFFFFFh
0x1800b58f4  lock xadd [rcx], eax
0x1800b58f8  cmp     eax, 1
0x1800b58fb  jnz     short loc_1800B5908
0x1800b58fd  test    rcx, rcx
0x1800b5900  jz      short loc_1800B5908
0x1800b5902  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1800b5908  lea     rax, dword_1801DBD74
0x1800b590f  mov     r8, rbx
0x1800b5912  mov     [rbx], rax
0x1800b5915  lea     rcx, [r13+20h]
0x1800b5919  mov     [rbx+18h], r12d
0x1800b591d  mov     [rbx+1Ch], r12w
0x1800b5922  call    ?ToString@?$TSimpleTypeHelper@VColor@ODF@@@Ofc@@SAXAEBVColor@ODF@@PEAVIWriterParams@2@AEAV?$TFixedVarStr@$0ICF@@2@@Z; Ofc::TSimpleTypeHelper<ODF::Color>::ToString(ODF::Color const &,Ofc::IWriterParams *,Ofc::TFixedVarStr<2085> &)
0x1800b5927  mov     r9, rbx
0x1800b592a  lea     rcx, aColor; "color"
0x1800b5931  mov     r8, rdi
0x1800b5934  mov     edx, ebp
0x1800b5936  call    cs:__imp_?WriteAttrHelper@Ofc@@YAXPEB_WHAEAVIWriterParams@1@AEBV?$TFixedVarStr@$0ICF@@1@@Z; Ofc::WriteAttrHelper(wchar_t const *,int,Ofc::IWriterParams &,Ofc::TFixedVarStr<2085> const &)
0x1800b593c  mov     edx, ebp
0x1800b593e  mov     rcx, r14
0x1800b5941  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800b5947  cmp     dword ptr [r13+24h], 1
0x1800b594c  jnz     short loc_1800B5957
0x1800b594e  cmp     [rdi+1088h], r12b
0x1800b5955  jz      short loc_1800B59C1
0x1800b5957  mov     rcx, [rbx]
0x1800b595a  mov     rsi, rbx
0x1800b595d  sub     rcx, 0Ch
0x1800b5961  cmp     [rcx+4], r12d
0x1800b5965  jz      short loc_1800B5987
0x1800b5967  cmp     dword ptr [rcx], 1
0x1800b596a  jz      short loc_1800B597C
0x1800b596c  or      eax, 0FFFFFFFFh
0x1800b596f  lock xadd [rcx], eax
0x1800b5973  cmp     eax, 1
0x1800b5976  jnz     short loc_1800B5987
0x1800b5978  lea     rsi, [rdi+20h]
0x1800b597c  test    rcx, rcx
0x1800b597f  jz      short loc_1800B5987
0x1800b5981  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1800b5987  lea     rax, dword_1801DBD74
0x1800b598e  mov     r8, rbx
0x1800b5991  mov     [rbx], rax
0x1800b5994  lea     rcx, [r13+24h]
0x1800b5998  mov     rdx, rdi
0x1800b599b  mov     [rbx+18h], r12d
0x1800b599f  mov     [rbx+1Ch], r12w
0x1800b59a4  call    ?ToString@?$TSimpleTypeHelper@W4StyleEnum@ODF@@@Ofc@@SAXAEBW4StyleEnum@ODF@@PEAVIWriterParams@2@AEAV?$TFixedVarStr@$0ICF@@2@@Z; Ofc::TSimpleTypeHelper<ODF::StyleEnum>::ToString(ODF::StyleEnum const &,Ofc::IWriterParams *,Ofc::TFixedVarStr<2085> &)
0x1800b59a9  mov     r9, rbx
0x1800b59ac  lea     rcx, aStyle; "style"
0x1800b59b3  mov     r8, rdi
0x1800b59b6  mov     edx, ebp
0x1800b59b8  call    cs:__imp_?WriteAttrHelper@Ofc@@YAXPEB_WHAEAVIWriterParams@1@AEBV?$TFixedVarStr@$0ICF@@1@@Z; Ofc::WriteAttrHelper(wchar_t const *,int,Ofc::IWriterParams &,Ofc::TFixedVarStr<2085> const &)
0x1800b59be  mov     rbx, rsi
0x1800b59c1  mov     edx, ebp
0x1800b59c3  mov     rcx, r14
0x1800b59c6  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800b59cc  mov     rcx, [rbx]
0x1800b59cf  sub     rcx, 0Ch
0x1800b59d3  cmp     [rcx+4], r12d
0x1800b59d7  jz      short loc_1800B59F5
0x1800b59d9  cmp     dword ptr [rcx], 1
0x1800b59dc  jz      short loc_1800B59EA
0x1800b59de  or      eax, 0FFFFFFFFh
0x1800b59e1  lock xadd [rcx], eax
0x1800b59e5  cmp     eax, 1
0x1800b59e8  jnz     short loc_1800B59F5
0x1800b59ea  test    rcx, rcx
0x1800b59ed  jz      short loc_1800B59F5
0x1800b59ef  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1800b59f5  lea     rax, dword_1801DBD74
0x1800b59fc  mov     r8, rbx
0x1800b59ff  mov     [rbx], rax
0x1800b5a02  lea     rcx, [r13+28h]
0x1800b5a06  mov     rdx, rdi
0x1800b5a09  mov     [rbx+18h], r12d
0x1800b5a0d  mov     [rbx+1Ch], r12w
0x1800b5a12  call    ?ToString@?$TSimpleTypeHelper@W4StyleColumnSepAttlistVerticalAlign@ODF@@@Ofc@@SAXAEBW4StyleColumnSepAttlistVerticalAlign@ODF@@PEAVIWriterParams@2@AEAV?$TFixedVarStr@$0ICF@@2@@Z; Ofc::TSimpleTypeHelper<ODF::StyleColumnSepAttlistVerticalAlign>::ToString(ODF::StyleColumnSepAttlistVerticalAlign const &,Ofc::IWriterParams *,Ofc::TFixedVarStr<2085> &)
0x1800b5a17  mov     r9, rbx
0x1800b5a1a  lea     rcx, aVerticalAlign; "vertical-align"
0x1800b5a21  mov     r8, rdi
0x1800b5a24  mov     edx, ebp
0x1800b5a26  call    cs:__imp_?WriteAttrHelper@Ofc@@YAXPEB_WHAEAVIWriterParams@1@AEBV?$TFixedVarStr@$0ICF@@1@@Z; Ofc::WriteAttrHelper(wchar_t const *,int,Ofc::IWriterParams &,Ofc::TFixedVarStr<2085> const &)
0x1800b5a2c  mov     rax, [r15]
0x1800b5a2f  mov     rcx, r15
0x1800b5a32  mov     rdx, [rdi+10h]
0x1800b5a36  mov     rax, [rax]
0x1800b5a39  call    cs:__guard_dispatch_icall_fptr
0x1800b5a3f  mov     rcx, r15
0x1800b5a42  call    cs:__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ; Ofc::CWriterEmit::EmitEndElement(void)
0x1800b5a48  lea     r11, [rsp+68h+var_28]
0x1800b5a4d  mov     rbx, [r11+30h]
0x1800b5a51  mov     rbp, [r11+38h]
0x1800b5a55  mov     rsi, [r11+48h]
0x1800b5a59  mov     rsp, r11
0x1800b5a5c  pop     r15
0x1800b5a5e  pop     r14
0x1800b5a60  pop     r13
0x1800b5a62  pop     r12
0x1800b5a64  pop     rdi
0x1800b5a65  retn
```
