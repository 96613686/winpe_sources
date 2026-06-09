# Appx::Packaging::ManifestComparisonPackageSet::CompareApplicationNodes(IXMLDOMNode *,IXMLDOMNode *,ushort const *,bool *)

- ea: `0x1800705f0`
- end: `0x180070a13`
- name: `?CompareApplicationNodes@ManifestComparisonPackageSet@Packaging@Appx@@AEAAJPEAUIXMLDOMNode@@0PEBGPEA_N@Z`
- size: `1059`
- prototype: `__int64 __fastcall(Appx::Packaging::ManifestComparisonPackageSet *__hidden this, struct IXMLDOMNode *, struct IXMLDOMNode *, const unsigned __int16 *, bool *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180010f40`
- `0x1800705f0`
- `0x180070da0`
- `0x1800713b8`
- `0x180071f50`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180070687`
- `OLEAUT32!__imp_SysFreeString` at `0x1800706e3`
- `OLEAUT32!__imp_SysFreeString` at `0x18007075b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800707cc`
- `OLEAUT32!__imp_SysFreeString` at `0x180070815`
- `OLEAUT32!__imp_SysFreeString` at `0x180070896`
- `OLEAUT32!__imp_SysFreeString` at `0x1800708a5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800708b4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800708c3`
- `OLEAUT32!__imp_SysFreeString` at `0x18007091e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800709ac`
- `OLEAUT32!__imp_SysFreeString` at `0x1800709bb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800709ca`
- `OLEAUT32!__imp_SysFreeString` at `0x1800709d9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800709e8`
- `OLEAUT32!__imp_SysFreeString` at `0x180070687`
- `OLEAUT32!__imp_SysFreeString` at `0x1800706e3`
- `OLEAUT32!__imp_SysFreeString` at `0x18007075b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800707cc`
- `OLEAUT32!__imp_SysFreeString` at `0x180070815`
- `OLEAUT32!__imp_SysFreeString` at `0x180070896`
- `OLEAUT32!__imp_SysFreeString` at `0x1800708a5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800708b4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800708c3`
- `OLEAUT32!__imp_SysFreeString` at `0x18007091e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800709ac`
- `OLEAUT32!__imp_SysFreeString` at `0x1800709bb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800709ca`
- `OLEAUT32!__imp_SysFreeString` at `0x1800709d9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800709e8`

## string_xrefs

- `0x18007066f`: `onecore\printscan\appxpackaging\lib\bundle\src\manifestcomparisonhelper.cpp`
- `0x1800706cc`: `onecore\printscan\appxpackaging\lib\bundle\src\manifestcomparisonhelper.cpp`
- `0x180070743`: `onecore\printscan\appxpackaging\lib\bundle\src\manifestcomparisonhelper.cpp`
- `0x1800707b4`: `onecore\printscan\appxpackaging\lib\bundle\src\manifestcomparisonhelper.cpp`
- `0x1800707fd`: `onecore\printscan\appxpackaging\lib\bundle\src\manifestcomparisonhelper.cpp`
- `0x18007087f`: `onecore\printscan\appxpackaging\lib\bundle\src\manifestcomparisonhelper.cpp`
- `0x180070906`: `onecore\printscan\appxpackaging\lib\bundle\src\manifestcomparisonhelper.cpp`
- `0x180070987`: `onecore\printscan\appxpackaging\lib\bundle\src\manifestcomparisonhelper.cpp`
- `0x180070705`: `Extensions`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::ManifestComparisonPackageSet::CompareApplicationNodes(
        Appx::Packaging::ManifestComparisonPackageSet *this,
        struct IXMLDOMNode *a2,
        struct IXMLDOMNode *a3,
        struct Common::AutoBStr *a4,
        bool *a5)
{
  int v9; // eax
  unsigned int v10; // ebx
  OLECHAR *v12; // rbx
  int v13; // eax
  struct Common::AutoBStr *v14; // r9
  unsigned int v15; // edi
  int v16; // eax
  struct Common::AutoBStr *v17; // r9
  int v18; // eax
  struct Common::AutoBStr *v19; // r9
  int v20; // eax
  OLECHAR *v21; // rdi
  OLECHAR *v22; // rsi
  OLECHAR *v23; // r14
  int matched; // eax
  struct Common::AutoBStr *v25; // r9
  unsigned int v26; // r15d
  int v27; // eax
  OLECHAR *v28; // r15
  int v29; // eax
  unsigned int v30; // r13d
  int v31; // [rsp+28h] [rbp-71h]
  int v32; // [rsp+28h] [rbp-71h]
  int v33; // [rsp+28h] [rbp-71h]
  int v34; // [rsp+28h] [rbp-71h]
  BSTR v35; // [rsp+58h] [rbp-41h] BYREF
  BSTR bstrString; // [rsp+60h] [rbp-39h] BYREF
  BSTR v37[2]; // [rsp+68h] [rbp-31h] BYREF
  __int64 v38; // [rsp+78h] [rbp-21h] BYREF
  int v39; // [rsp+80h] [rbp-19h]
  int v40; // [rsp+88h] [rbp-11h] BYREF
  const unsigned __int16 *v41; // [rsp+90h] [rbp-9h]
  int v42; // [rsp+98h] [rbp-1h]
  const wchar_t *v43; // [rsp+A0h] [rbp+7h]
  int v44; // [rsp+A8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+F0h] [rbp+57h]

  v40 = 3;
  bstrString = 0;
  v41 = L"VisualElements";
  v42 = 14;
  v44 = 0;
  v43 = L"']";
  v9 = Appx::Packaging::BuildXPath(
         (Appx::Packaging *)&v40,
         (const struct Appx::Packaging::XPathComponent *)1,
         &bstrString,
         a4);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x213,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\bundle\\src\\manifestcomparisonhelper.cpp",
      (const char *)(unsigned int)v9,
      v31);
    SysFreeString(bstrString);
    return v10;
  }
  v12 = bstrString;
  v13 = Appx::Packaging::ManifestComparisonPackageSet::CompareXmlSubNodes(
          this,
          a2,
          a3,
          (const unsigned __int16 *)a4,
          bstrString,
          bstrString,
          a5);
  v15 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x21A,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\bundle\\src\\manifestcomparisonhelper.cpp",
      (const char *)(unsigned int)v13,
      v32);
LABEL_5:
    SysFreeString(v12);
    return v15;
  }
  if ( !*a5 )
    goto LABEL_5;
  v35 = 0;
  v40 = 3;
  v41 = L"Extensions";
  v42 = 10;
  v43 = L"']";
  v44 = 0;
  v16 = Appx::Packaging::BuildXPath(
          (Appx::Packaging *)&v40,
          (const struct Appx::Packaging::XPathComponent *)1,
          &v35,
          v14);
  v15 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x21F,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\bundle\\src\\manifestcomparisonhelper.cpp",
      (const char *)(unsigned int)v16,
      v32);
LABEL_9:
    SysFreeString(v35);
    goto LABEL_5;
  }
  bstrString = 0;
  v41 = L"Name";
  v40 = 5;
  v43 = L"']";
  v42 = 4;
  v44 = 0;
  v18 = Appx::Packaging::BuildXPath(
          (Appx::Packaging *)&v40,
          (const struct Appx::Packaging::XPathComponent *)1,
          &bstrString,
          v17);
  v15 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x221,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\bundle\\src\\manifestcomparisonhelper.cpp",
      (const char *)(unsigned int)v18,
      v32);
LABEL_12:
    SysFreeString(bstrString);
    goto LABEL_9;
  }
  v37[0] = 0;
  v20 = Appx::Packaging::BuildXPath(
          (Appx::Packaging *)&qword_18010C980,
          (const struct Appx::Packaging::XPathComponent *)3,
          v37,
          v19);
  v15 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x229,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\bundle\\src\\manifestcomparisonhelper.cpp",
      (const char *)(unsigned int)v20,
      v32);
    SysFreeString(v37[0]);
    goto LABEL_12;
  }
  v21 = v35;
  v22 = bstrString;
  v38 = (__int64)Appx::Packaging::ManifestComparisonPackageSet::CompareXmlNodes;
  v39 = 0;
  v23 = v37[0];
  matched = Appx::Packaging::ManifestComparisonPackageSet::MatchXmlNodes(
              this,
              (__int64 *)a2,
              a3,
              (unsigned __int16 *)a4,
              (struct IXMLDOMNode *)v37[0],
              bstrString,
              &v38,
              v35,
              a5);
  v26 = matched;
  if ( matched < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x232,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\bundle\\src\\manifestcomparisonhelper.cpp",
      (const char *)(unsigned int)matched,
      v33);
LABEL_17:
    SysFreeString(v23);
    SysFreeString(v22);
    SysFreeString(v21);
    SysFreeString(v12);
    return v26;
  }
  if ( !*a5 )
    goto LABEL_17;
  v37[0] = 0;
  v27 = Appx::Packaging::BuildXPath(
          (Appx::Packaging *)&qword_18010C900,
          (const struct Appx::Packaging::XPathComponent *)3,
          v37,
          v25);
  v26 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x23B,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\bundle\\src\\manifestcomparisonhelper.cpp",
      (const char *)(unsigned int)v27,
      v33);
    SysFreeString(v37[0]);
    goto LABEL_17;
  }
  v28 = v37[0];
  v38 = (__int64)Appx::Packaging::ManifestComparisonPackageSet::CompareXmlNodes;
  v39 = 0;
  v29 = Appx::Packaging::ManifestComparisonPackageSet::MatchXmlNodes(
          this,
          (__int64 *)a2,
          a3,
          (unsigned __int16 *)a4,
          (struct IXMLDOMNode *)v37[0],
          v22,
          &v38,
          v21,
          a5);
  v30 = v29;
  if ( v29 >= 0 )
  {
    if ( *a5 )
      *a5 = 1;
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x244,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\bundle\\src\\manifestcomparisonhelper.cpp",
      (const char *)(unsigned int)v29,
      v34);
  }
  SysFreeString(v28);
  SysFreeString(v23);
  SysFreeString(v22);
  SysFreeString(v21);
  SysFreeString(v12);
  return v30;
}

```

## disassembly

```asm
0x1800705f0  mov     rax, rsp
0x1800705f3  mov     [rax+20h], rbx
0x1800705f7  mov     [rax+18h], r8
0x1800705fb  mov     [rax+10h], rdx
0x1800705ff  mov     [rax+8], rcx
0x180070603  push    rbp
0x180070604  push    rsi
0x180070605  push    rdi
0x180070606  push    r12
0x180070608  push    r13
0x18007060a  push    r14
0x18007060c  push    r15
0x18007060e  lea     rbp, [rax-57h]
0x180070612  sub     rsp, 0B0h
0x180070619  xor     r14d, r14d
0x18007061c  mov     [rbp+4Fh+var_60], 3
0x180070623  lea     rax, ?VisualElements@ElementNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; "VisualElements"
0x18007062a  mov     [rbp+4Fh+bstrString], r14
0x18007062e  mov     [rbp+4Fh+var_58], rax
0x180070632  mov     r15, r8
0x180070635  mov     rdi, rdx
0x180070638  mov     [rbp+4Fh+var_50], 0Eh
0x18007063f  mov     rsi, rcx
0x180070642  mov     [rbp+4Fh+var_40], r14d
0x180070646  lea     rax, asc_1801177B4; "']"
0x18007064d  mov     r13, r9
0x180070650  lea     edx, [r14+1]; struct Appx::Packaging::XPathComponent *
0x180070654  mov     [rbp+4Fh+var_48], rax
0x180070658  lea     r8, [rbp+4Fh+bstrString]; unsigned int
0x18007065c  lea     rcx, [rbp+4Fh+var_60]; this
0x180070660  call    ?BuildXPath@Packaging@Appx@@YAJPEBUXPathComponent@12@IAEAVAutoBStr@Common@@@Z; Appx::Packaging::BuildXPath(Appx::Packaging::XPathComponent const *,uint,Common::AutoBStr &)
0x180070665  mov     ebx, eax
0x180070667  test    eax, eax
0x180070669  jns     short loc_18007069A
0x18007066b  mov     rcx, [rbp+57h]; this
0x18007066f  lea     r8, aOnecorePrintsc_111; "onecore\\printscan\\appxpackaging\\lib"...
0x180070676  mov     r9d, eax; char *
0x180070679  mov     edx, 213h; void *
0x18007067e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180070683  mov     rcx, [rbp+4Fh+bstrString]; bstrString
0x180070687  call    cs:__imp_SysFreeString
0x18007068e  nop     dword ptr [rax+rax+00h]
0x180070693  mov     eax, ebx
0x180070695  jmp     loc_1800709F7
0x18007069a  mov     rbx, [rbp+4Fh+bstrString]
0x18007069e  mov     r9, r13; unsigned __int16 *
0x1800706a1  mov     r12, [rbp+4Fh+arg_20]
0x1800706a5  mov     r8, r15; struct IXMLDOMNode *
0x1800706a8  mov     [rsp+0E0h+var_B0], r12; bool *
0x1800706ad  mov     rdx, rdi; struct IXMLDOMNode *
0x1800706b0  mov     [rsp+0E0h+var_B8], rbx; unsigned __int16 *
0x1800706b5  mov     rcx, rsi; this
0x1800706b8  mov     [rsp+0E0h+var_C0], rbx; int
0x1800706bd  call    ?CompareXmlSubNodes@ManifestComparisonPackageSet@Packaging@Appx@@AEAAJPEAUIXMLDOMNode@@0PEBGPEAG2PEA_N@Z; Appx::Packaging::ManifestComparisonPackageSet::CompareXmlSubNodes(IXMLDOMNode *,IXMLDOMNode *,ushort const *,ushort *,ushort *,bool *)
0x1800706c2  mov     edi, eax
0x1800706c4  test    eax, eax
0x1800706c6  jns     short loc_1800706F6
0x1800706c8  mov     rcx, [rbp+57h]; this
0x1800706cc  lea     r8, aOnecorePrintsc_111; "onecore\\printscan\\appxpackaging\\lib"...
0x1800706d3  mov     r9d, eax; char *
0x1800706d6  mov     edx, 21Ah; void *
0x1800706db  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800706e0  mov     rcx, rbx; bstrString
0x1800706e3  call    cs:__imp_SysFreeString
0x1800706ea  nop     dword ptr [rax+rax+00h]
0x1800706ef  mov     eax, edi
0x1800706f1  jmp     loc_1800709F7
0x1800706f6  cmp     [r12], r14b
0x1800706fa  jz      short loc_1800706E0
0x1800706fc  mov     esi, 3
0x180070701  mov     [rbp+4Fh+var_90], r14
0x180070705  lea     rax, ?Extensions@ElementNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; "Extensions"
0x18007070c  mov     [rbp+4Fh+var_60], esi
0x18007070f  mov     [rbp+4Fh+var_58], rax
0x180070713  lea     r8, [rbp+4Fh+var_90]; unsigned int
0x180070717  lea     rax, asc_1801177B4; "']"
0x18007071e  mov     [rbp+4Fh+var_50], 0Ah
0x180070725  lea     edx, [rsi-2]; struct Appx::Packaging::XPathComponent *
0x180070728  mov     [rbp+4Fh+var_48], rax
0x18007072c  lea     rcx, [rbp+4Fh+var_60]; this
0x180070730  mov     [rbp+4Fh+var_40], r14d
0x180070734  call    ?BuildXPath@Packaging@Appx@@YAJPEBUXPathComponent@12@IAEAVAutoBStr@Common@@@Z; Appx::Packaging::BuildXPath(Appx::Packaging::XPathComponent const *,uint,Common::AutoBStr &)
0x180070739  mov     edi, eax
0x18007073b  test    eax, eax
0x18007073d  jns     short loc_18007076C
0x18007073f  mov     rcx, [rbp+57h]; this
0x180070743  lea     r8, aOnecorePrintsc_111; "onecore\\printscan\\appxpackaging\\lib"...
0x18007074a  mov     r9d, eax; char *
0x18007074d  mov     edx, 21Fh; void *
0x180070752  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180070757  mov     rcx, [rbp+4Fh+var_90]; bstrString
0x18007075b  call    cs:__imp_SysFreeString
0x180070762  nop     dword ptr [rax+rax+00h]
0x180070767  jmp     loc_1800706E0
0x18007076c  lea     rax, ?Name@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; "Name"
0x180070773  mov     [rbp+4Fh+bstrString], r14
0x180070777  mov     [rbp+4Fh+var_58], rax
0x18007077b  lea     r8, [rbp+4Fh+bstrString]; unsigned int
0x18007077f  lea     rax, asc_1801177B4; "']"
0x180070786  mov     [rbp+4Fh+var_60], 5
0x18007078d  mov     edx, 1; struct Appx::Packaging::XPathComponent *
0x180070792  mov     [rbp+4Fh+var_48], rax
0x180070796  lea     rcx, [rbp+4Fh+var_60]; this
0x18007079a  mov     [rbp+4Fh+var_50], 4
0x1800707a1  mov     [rbp+4Fh+var_40], r14d
0x1800707a5  call    ?BuildXPath@Packaging@Appx@@YAJPEBUXPathComponent@12@IAEAVAutoBStr@Common@@@Z; Appx::Packaging::BuildXPath(Appx::Packaging::XPathComponent const *,uint,Common::AutoBStr &)
0x1800707aa  mov     edi, eax
0x1800707ac  test    eax, eax
0x1800707ae  jns     short loc_1800707DD
0x1800707b0  mov     rcx, [rbp+57h]; this
0x1800707b4  lea     r8, aOnecorePrintsc_111; "onecore\\printscan\\appxpackaging\\lib"...
0x1800707bb  mov     r9d, eax; char *
0x1800707be  mov     edx, 221h; void *
0x1800707c3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800707c8  mov     rcx, [rbp+4Fh+bstrString]; bstrString
0x1800707cc  call    cs:__imp_SysFreeString
0x1800707d3  nop     dword ptr [rax+rax+00h]
0x1800707d8  jmp     loc_180070757
0x1800707dd  lea     r8, [rbp+4Fh+var_80]; unsigned int
0x1800707e1  mov     [rbp+4Fh+var_80], r14
0x1800707e5  mov     edx, esi; struct Appx::Packaging::XPathComponent *
0x1800707e7  lea     rcx, qword_18010C980; this
0x1800707ee  call    ?BuildXPath@Packaging@Appx@@YAJPEBUXPathComponent@12@IAEAVAutoBStr@Common@@@Z; Appx::Packaging::BuildXPath(Appx::Packaging::XPathComponent const *,uint,Common::AutoBStr &)
0x1800707f3  mov     edi, eax
0x1800707f5  test    eax, eax
0x1800707f7  jns     short loc_180070823
0x1800707f9  mov     rcx, [rbp+57h]; this
0x1800707fd  lea     r8, aOnecorePrintsc_111; "onecore\\printscan\\appxpackaging\\lib"...
0x180070804  mov     r9d, eax; char *
0x180070807  mov     edx, 229h; void *
0x18007080c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180070811  mov     rcx, [rbp+4Fh+var_80]; bstrString
0x180070815  call    cs:__imp_SysFreeString
0x18007081c  nop     dword ptr [rax+rax+00h]
0x180070821  jmp     short loc_1800707C8
0x180070823  mov     rdi, [rbp+4Fh+var_90]
0x180070827  lea     rax, ?CompareXmlNodes@ManifestComparisonPackageSet@Packaging@Appx@@AEAAJPEAUIXMLDOMNode@@0PEBGPEA_N@Z; Appx::Packaging::ManifestComparisonPackageSet::CompareXmlNodes(IXMLDOMNode *,IXMLDOMNode *,ushort const *,bool *)
0x18007082e  mov     rsi, [rbp+4Fh+bstrString]
0x180070832  mov     r9, r13; int
0x180070835  mov     rdx, qword ptr [rbp+4Fh+arg_8]; int
0x180070839  mov     r8, r15; int
0x18007083c  mov     rcx, qword ptr [rbp+4Fh+arg_0]; int
0x180070840  mov     [rsp+40h], r12; __int64
0x180070845  mov     [rbp+4Fh+var_70], rax
0x180070849  mov     eax, [rbp+4Fh+var_64]
0x18007084c  mov     [rsp+0E0h+var_A8], rdi; __int64
0x180070851  mov     [rbp+4Fh+var_64], eax
0x180070854  lea     rax, [rbp+4Fh+var_70]
0x180070858  mov     [rsp+0E0h+var_B0], rax; __int64
0x18007085d  mov     [rbp+4Fh+var_68], r14d
0x180070861  mov     r14, [rbp+4Fh+var_80]
0x180070865  mov     [rsp+0E0h+var_B8], rsi; unsigned __int16 *
0x18007086a  mov     [rsp+0E0h+var_C0], r14; int
0x18007086f  call    ?MatchXmlNodes@ManifestComparisonPackageSet@Packaging@Appx@@AEAAJPEAUIXMLDOMNode@@0PEBGPEAG2P8123@EAAJ001PEA_N@Z23@Z; Appx::Packaging::ManifestComparisonPackageSet::MatchXmlNodes(IXMLDOMNode *,IXMLDOMNode *,ushort const *,ushort *,ushort *,long (Appx::Packaging::ManifestComparisonPackageSet::*)(IXMLDOMNode *,IXMLDOMNode *,ushort const *,bool *),ushort *,bool *)
0x180070874  mov     r15d, eax
0x180070877  test    eax, eax
0x180070879  jns     short loc_1800708D7
0x18007087b  mov     rcx, [rbp+57h]; this
0x18007087f  lea     r8, aOnecorePrintsc_111; "onecore\\printscan\\appxpackaging\\lib"...
0x180070886  mov     r9d, eax; char *
0x180070889  mov     edx, 232h; void *
0x18007088e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180070893  mov     rcx, r14; bstrString
0x180070896  call    cs:__imp_SysFreeString
0x18007089d  nop     dword ptr [rax+rax+00h]
0x1800708a2  mov     rcx, rsi; bstrString
0x1800708a5  call    cs:__imp_SysFreeString
0x1800708ac  nop     dword ptr [rax+rax+00h]
0x1800708b1  mov     rcx, rdi; bstrString
0x1800708b4  call    cs:__imp_SysFreeString
0x1800708bb  nop     dword ptr [rax+rax+00h]
0x1800708c0  mov     rcx, rbx; bstrString
0x1800708c3  call    cs:__imp_SysFreeString
0x1800708ca  nop     dword ptr [rax+rax+00h]
0x1800708cf  mov     eax, r15d
0x1800708d2  jmp     loc_1800709F7
0x1800708d7  cmp     byte ptr [r12], 0
0x1800708dc  jz      short loc_180070893
0x1800708de  lea     r8, [rbp+4Fh+var_80]; unsigned int
0x1800708e2  mov     [rbp+4Fh+var_80], 0
0x1800708ea  mov     edx, 3; struct Appx::Packaging::XPathComponent *
0x1800708ef  lea     rcx, qword_18010C900; this
0x1800708f6  call    ?BuildXPath@Packaging@Appx@@YAJPEBUXPathComponent@12@IAEAVAutoBStr@Common@@@Z; Appx::Packaging::BuildXPath(Appx::Packaging::XPathComponent const *,uint,Common::AutoBStr &)
0x1800708fb  mov     r15d, eax
0x1800708fe  test    eax, eax
0x180070900  jns     short loc_18007092F
0x180070902  mov     rcx, [rbp+57h]; this
0x180070906  lea     r8, aOnecorePrintsc_111; "onecore\\printscan\\appxpackaging\\lib"...
0x18007090d  mov     r9d, eax; char *
0x180070910  mov     edx, 23Bh; void *
0x180070915  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007091a  mov     rcx, [rbp+4Fh+var_80]; bstrString
0x18007091e  call    cs:__imp_SysFreeString
0x180070925  nop     dword ptr [rax+rax+00h]
0x18007092a  jmp     loc_180070893
0x18007092f  mov     r15, [rbp+4Fh+var_80]
0x180070933  lea     rax, ?CompareXmlNodes@ManifestComparisonPackageSet@Packaging@Appx@@AEAAJPEAUIXMLDOMNode@@0PEBGPEA_N@Z; Appx::Packaging::ManifestComparisonPackageSet::CompareXmlNodes(IXMLDOMNode *,IXMLDOMNode *,ushort const *,bool *)
0x18007093a  mov     r8, qword ptr [rbp+4Fh+arg_10]; int
0x18007093e  mov     r9, r13; int
0x180070941  mov     rdx, qword ptr [rbp+4Fh+arg_8]; int
0x180070945  mov     rcx, qword ptr [rbp+4Fh+arg_0]; int
0x180070949  mov     [rsp+40h], r12; __int64
0x18007094e  mov     [rbp+4Fh+var_70], rax
0x180070952  mov     eax, [rbp+4Fh+var_64]
0x180070955  mov     [rsp+0E0h+var_A8], rdi; __int64
0x18007095a  mov     [rbp+4Fh+var_64], eax
0x18007095d  lea     rax, [rbp+4Fh+var_70]
0x180070961  mov     [rsp+0E0h+var_B0], rax; __int64
0x180070966  mov     [rsp+0E0h+var_B8], rsi; unsigned __int16 *
0x18007096b  mov     [rsp+0E0h+var_C0], r15; int
0x180070970  mov     [rbp+4Fh+var_68], 0
0x180070977  call    ?MatchXmlNodes@ManifestComparisonPackageSet@Packaging@Appx@@AEAAJPEAUIXMLDOMNode@@0PEBGPEAG2P8123@EAAJ001PEA_N@Z23@Z; Appx::Packaging::ManifestComparisonPackageSet::MatchXmlNodes(IXMLDOMNode *,IXMLDOMNode *,ushort const *,ushort *,ushort *,long (Appx::Packaging::ManifestComparisonPackageSet::*)(IXMLDOMNode *,IXMLDOMNode *,ushort const *,bool *),ushort *,bool *)
0x18007097c  mov     r13d, eax
0x18007097f  test    eax, eax
0x180070981  jns     short loc_18007099D
0x180070983  mov     rcx, [rbp+57h]; this
0x180070987  lea     r8, aOnecorePrintsc_111; "onecore\\printscan\\appxpackaging\\lib"...
0x18007098e  mov     r9d, eax; char *
0x180070991  mov     edx, 244h; void *
0x180070996  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007099b  jmp     short loc_1800709A9
0x18007099d  cmp     byte ptr [r12], 0
0x1800709a2  jz      short loc_1800709A9
0x1800709a4  mov     byte ptr [r12], 1
0x1800709a9  mov     rcx, r15; bstrString
0x1800709ac  call    cs:__imp_SysFreeString
0x1800709b3  nop     dword ptr [rax+rax+00h]
0x1800709b8  mov     rcx, r14; bstrString
0x1800709bb  call    cs:__imp_SysFreeString
0x1800709c2  nop     dword ptr [rax+rax+00h]
0x1800709c7  mov     rcx, rsi; bstrString
0x1800709ca  call    cs:__imp_SysFreeString
0x1800709d1  nop     dword ptr [rax+rax+00h]
0x1800709d6  mov     rcx, rdi; bstrString
0x1800709d9  call    cs:__imp_SysFreeString
0x1800709e0  nop     dword ptr [rax+rax+00h]
0x1800709e5  mov     rcx, rbx; bstrString
0x1800709e8  call    cs:__imp_SysFreeString
0x1800709ef  nop     dword ptr [rax+rax+00h]
0x1800709f4  mov     eax, r13d
0x1800709f7  mov     rbx, [rsp+0E0h+arg_18]
0x1800709ff  add     rsp, 0B0h
0x180070a06  pop     r15
0x180070a08  pop     r14
0x180070a0a  pop     r13
0x180070a0c  pop     r12
0x180070a0e  pop     rdi
0x180070a0f  pop     rsi
0x180070a10  pop     rbp
0x180070a11  retn
```
