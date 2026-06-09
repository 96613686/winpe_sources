# Appx::Packaging::Manifest::AppxManifestReaderImpl::ValidateApplicationContentURIs(void)

- ea: `0x18001c1b4`
- end: `0x18001c774`
- name: `?ValidateApplicationContentURIs@AppxManifestReaderImpl@Manifest@Packaging@Appx@@AEAAJXZ`
- size: `1472`
- prototype: `__int64 __fastcall(Appx::Packaging::Manifest::AppxManifestReaderImpl *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180022400`

## callees

- `0x180005eb8`
- `0x18000f260`
- `0x180010f40`
- `0x1800133fc`
- `0x18001b270`
- `0x18001bc74`
- `0x18001c1b4`
- `0x18001c77c`
- `0x18003a344`
- `0x18003c7c8`
- `0x1800e0c4c`
- `0x180106010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001c258`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c418`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c428`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c474`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c484`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c4b0`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c4bf`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c4ce`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c531`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c541`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c5e2`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c5f2`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c602`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c659`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c704`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c714`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c724`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c73c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c74b`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c75a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c258`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c418`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c428`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c474`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c484`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c4b0`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c4bf`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c4ce`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c531`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c541`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c5e2`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c5f2`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c602`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c659`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c704`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c714`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c724`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c73c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c74b`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c75a`

## string_xrefs

- `0x18001c461`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`
- `0x18001c4fc`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`
- `0x18001c519`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`
- `0x18001c579`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`
- `0x18001c593`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`
- `0x18001c5b0`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`
- `0x18001c5ca`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`
- `0x18001c6f1`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`
- `0x18001c2fe`: `WindowsRuntimeAccess`
- `0x18001c66e`: `WindowsRuntimeAccess`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Manifest::AppxManifestReaderImpl::ValidateApplicationContentURIs(
        Appx::Packaging::Manifest::AppxManifestReaderImpl *this,
        __int64 a2,
        __int64 a3,
        struct Common::AutoBStr *a4)
{
  int RequiredNodeValue; // r14d
  int v6; // eax
  unsigned int v7; // ebx
  int NodesList; // eax
  struct Common::AutoBStr *v9; // r9
  __int64 v10; // rax
  int v12; // eax
  struct Common::AutoBStr *v13; // r9
  int v14; // eax
  struct Common::AutoBStr *v15; // r9
  int v16; // eax
  __int64 *v17; // r15
  int v18; // r12d
  OLECHAR *v19; // rbx
  OLECHAR *v20; // rdi
  OLECHAR *v21; // rsi
  __int64 (__fastcall *v22)(__int64 *, struct IXMLDOMNode **); // r14
  int v23; // eax
  BSTR v24; // rax
  int v25; // edx
  int v26; // ecx
  bool v27; // r14
  struct IXMLDOMNode *v28; // rcx
  __int64 v29; // rdx
  struct IXMLDOMNode *v30; // rcx
  Appx::Packaging::XmlLineInformation *v31; // rcx
  int v32; // ecx
  __int64 v33; // rdx
  int v34; // [rsp+20h] [rbp-49h]
  int *v35; // [rsp+20h] [rbp-49h]
  struct IXMLDOMNode *v36; // [rsp+30h] [rbp-39h] BYREF
  __int64 *v37; // [rsp+38h] [rbp-31h] BYREF
  BSTR v38; // [rsp+40h] [rbp-29h] BYREF
  BSTR v39; // [rsp+48h] [rbp-21h] BYREF
  BSTR v40; // [rsp+50h] [rbp-19h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-11h] BYREF
  int v42; // [rsp+60h] [rbp-9h] BYREF
  const unsigned __int16 *v43; // [rsp+68h] [rbp-1h]
  int v44; // [rsp+70h] [rbp+7h]
  const wchar_t *v45; // [rsp+78h] [rbp+Fh]
  int v46; // [rsp+80h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  int v48; // [rsp+D8h] [rbp+6Fh] BYREF
  BSTR v49; // [rsp+E0h] [rbp+77h] BYREF
  BSTR v50; // [rsp+E8h] [rbp+7Fh] BYREF

  RequiredNodeValue = 0;
  bstrString = 0;
  v6 = Appx::Packaging::BuildXPath(
         (Appx::Packaging *)&qword_180107ED0,
         (const struct Appx::Packaging::XPathComponent *)4,
         &bstrString,
         a4);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BC9,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreader.cpp",
      (const char *)(unsigned int)v6,
      v34);
    goto LABEL_8;
  }
  v37 = 0;
  v48 = 0;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v37);
  v35 = &v48;
  NodesList = Appx::Packaging::GetNodesList((char *)this + 128, bstrString, 0, &v37);
  v7 = NodesList;
  if ( NodesList < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BCD,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreader.cpp",
      (const char *)(unsigned int)NodesList,
      (int)&v48);
    goto LABEL_42;
  }
  if ( v48 <= 0 )
  {
    if ( !v37 )
    {
LABEL_7:
      v7 = RequiredNodeValue;
      goto LABEL_8;
    }
    v10 = *v37;
LABEL_6:
    (*(void (**)(void))(v10 + 16))();
    goto LABEL_7;
  }
  v49 = 0;
  v42 = 5;
  v43 = L"Match";
  v44 = 5;
  v45 = L"']";
  v46 = 0;
  v12 = Appx::Packaging::BuildXPath(
          (Appx::Packaging *)&v42,
          (const struct Appx::Packaging::XPathComponent *)1,
          &v49,
          v9);
  v7 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BD1,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreader.cpp",
      (const char *)(unsigned int)v12,
      (int)&v48);
  }
  else
  {
    v50 = 0;
    v43 = L"Type";
    v42 = 5;
    v44 = 4;
    v45 = L"']";
    v46 = 0;
    v14 = Appx::Packaging::BuildXPath(
            (Appx::Packaging *)&v42,
            (const struct Appx::Packaging::XPathComponent *)1,
            &v50,
            v13);
    v7 = v14;
    if ( v14 >= 0 )
    {
      v40 = 0;
      v43 = L"WindowsRuntimeAccess";
      v42 = 5;
      v44 = 20;
      v45 = L"']";
      v46 = 0;
      v16 = Appx::Packaging::BuildXPath(
              (Appx::Packaging *)&v42,
              (const struct Appx::Packaging::XPathComponent *)1,
              &v40,
              v15);
      v7 = v16;
      if ( v16 >= 0 )
      {
        v17 = v37;
        v18 = 0;
        v19 = v49;
        v20 = v50;
        v21 = v40;
        while ( 1 )
        {
          if ( v18 >= v48 )
            goto LABEL_30;
          v36 = 0;
          v22 = *(__int64 (__fastcall **)(__int64 *, struct IXMLDOMNode **))(*v17 + 72);
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v36);
          v23 = v22(v17, &v36);
          RequiredNodeValue = v23;
          if ( v23 < 0 )
            break;
          v39 = 0;
          v38 = 0;
          RequiredNodeValue = Appx::Packaging::GetRequiredNodeValue(&v36, v19, &v39);
          if ( RequiredNodeValue < 0 )
          {
            v29 = 7135;
            goto LABEL_27;
          }
          RequiredNodeValue = Appx::Packaging::GetRequiredNodeValue(&v36, v20, &v38);
          if ( RequiredNodeValue < 0 )
          {
            v29 = 7137;
LABEL_27:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v29,
              (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreader.cpp",
              (const char *)(unsigned int)RequiredNodeValue,
              (int)v35);
            SysFreeString(v38);
            SysFreeString(v39);
            goto LABEL_28;
          }
          v24 = v38;
          do
          {
            v25 = *(BSTR)((char *)v24 + (char *)L"include" - (char *)v38);
            v26 = *v24 - v25;
            if ( v26 )
              break;
            ++v24;
          }
          while ( v25 );
          if ( v26 )
          {
            v40 = 0;
            LODWORD(v35) = 0;
            RequiredNodeValue = Appx::Packaging::GetNodeValue(&v36, v21, 0, &v40);
            if ( RequiredNodeValue < 0 )
            {
              v33 = 7146;
LABEL_50:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v33,
                (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreader.cpp",
                (const char *)(unsigned int)RequiredNodeValue,
                (int)v35);
              SysFreeString(v40);
              SysFreeString(v38);
              SysFreeString(v39);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v36);
              SysFreeString(v21);
              SysFreeString(v20);
              SysFreeString(v19);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v37);
              goto LABEL_7;
            }
            if ( v40 )
            {
              v31 = (Appx::Packaging::XmlLineInformation *)*((_QWORD *)this + 13);
              LODWORD(v50) = 0;
              LODWORD(v49) = 0;
              Appx::Packaging::XmlLineInformation::GetXmlLineInformation(
                v31,
                (struct IStream *)v36,
                0,
                L"WindowsRuntimeAccess",
                (const unsigned __int16 *)&v50,
                (unsigned int *)&v49,
                (unsigned int *)v36);
              RequiredNodeValue = -2146958844;
              if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 1) != 0 )
                McTemplateU0dqq_EventWriteTransfer(
                  v32,
                  (unsigned int)&EVENT_MANIFEST_INVALID_DOMAINRULE_WINRTINEXCLUDERULE,
                  -2146958844,
                  (_DWORD)v50,
                  (char)v49);
              AppxPackagingLog(
                &EVENT_MANIFEST_INVALID_DOMAINRULE_WINRTINEXCLUDERULE,
                0xB00000B9,
                -2146958844,
                (unsigned int)v50,
                (unsigned int)v49);
              v33 = 7154;
              goto LABEL_50;
            }
            v27 = 0;
            SysFreeString(0);
          }
          else
          {
            v27 = 1;
          }
          RequiredNodeValue = Appx::Packaging::Manifest::AppxManifestReaderImpl::ValidateDomainRule(this, v36, v39, v27);
          if ( RequiredNodeValue < 0 )
          {
            v29 = 7165;
            goto LABEL_27;
          }
          SysFreeString(v38);
          SysFreeString(v39);
          v28 = v36;
          RequiredNodeValue = 0;
          if ( v36 )
          {
            v36 = 0;
            ((void (__fastcall *)(struct IXMLDOMNode *))v28->lpVtbl->Release)(v28);
          }
          ++v18;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1BDA,
          (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreader.cpp",
          (const char *)(unsigned int)v23,
          (int)v35);
LABEL_28:
        v30 = v36;
        if ( v36 )
        {
          v36 = 0;
          ((void (__fastcall *)(struct IXMLDOMNode *))v30->lpVtbl->Release)(v30);
        }
LABEL_30:
        SysFreeString(v21);
        SysFreeString(v20);
        SysFreeString(v19);
        if ( !v17 )
          goto LABEL_7;
        v10 = *v17;
        goto LABEL_6;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1BD5,
        (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreader.cpp",
        (const char *)(unsigned int)v16,
        (int)&v48);
      SysFreeString(v40);
      SysFreeString(v50);
      SysFreeString(v49);
LABEL_42:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v37);
      goto LABEL_8;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BD3,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreader.cpp",
      (const char *)(unsigned int)v14,
      (int)&v48);
    SysFreeString(v50);
  }
  SysFreeString(v49);
  if ( v37 )
    (*(void (__fastcall **)(__int64 *))(*v37 + 16))(v37);
LABEL_8:
  SysFreeString(bstrString);
  return v7;
}

```

## disassembly

```asm
0x18001c1b4  mov     [rsp-8+arg_0], rbx
0x18001c1b9  push    rbp
0x18001c1ba  push    rsi
0x18001c1bb  push    rdi
0x18001c1bc  push    r12
0x18001c1be  push    r13
0x18001c1c0  push    r14
0x18001c1c2  push    r15
0x18001c1c4  lea     rbp, [rsp-27h]
0x18001c1c9  sub     rsp, 90h
0x18001c1d0  xor     r14d, r14d
0x18001c1d3  lea     r8, [rbp+57h+bstrString]; unsigned int
0x18001c1d7  mov     r13, rcx
0x18001c1da  mov     [rbp+57h+bstrString], r14
0x18001c1de  lea     rcx, qword_180107ED0; this
0x18001c1e5  lea     r12d, [r14+4]
0x18001c1e9  mov     edx, r12d; struct Appx::Packaging::XPathComponent *
0x18001c1ec  call    ?BuildXPath@Packaging@Appx@@YAJPEBUXPathComponent@12@IAEAVAutoBStr@Common@@@Z; Appx::Packaging::BuildXPath(Appx::Packaging::XPathComponent const *,uint,Common::AutoBStr &)
0x18001c1f1  mov     ebx, eax
0x18001c1f3  test    eax, eax
0x18001c1f5  js      loc_18001C4F8
0x18001c1fb  lea     rcx, [rbp+57h+var_88]
0x18001c1ff  mov     [rbp+57h+var_88], r14
0x18001c203  mov     [rbp+57h+arg_8], r14d
0x18001c207  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18001c20c  mov     rdx, [rbp+57h+bstrString]
0x18001c210  lea     rax, [rbp+57h+arg_8]
0x18001c214  lea     rcx, [r13+80h]
0x18001c21b  mov     [rsp+0C0h+var_A0], rax; int
0x18001c220  lea     r9, [rbp+57h+var_88]
0x18001c224  xor     r8d, r8d
0x18001c227  call    ?GetNodesList@Packaging@Appx@@YAJAEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEAGJPEAPEAUIXMLDOMNodeList@@PEAJ@Z; Appx::Packaging::GetNodesList(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort *,long,IXMLDOMNodeList * *,long *)
0x18001c22c  mov     ebx, eax
0x18001c22e  test    eax, eax
0x18001c230  js      loc_18001C5AC
0x18001c236  cmp     [rbp+57h+arg_8], r14d
0x18001c23a  jg      short loc_18001C282
0x18001c23c  mov     rcx, [rbp+57h+var_88]
0x18001c240  test    rcx, rcx
0x18001c243  jz      short loc_18001C251
0x18001c245  mov     rax, [rcx]
0x18001c248  mov     rax, [rax+10h]
0x18001c24c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c251  mov     ebx, r14d
0x18001c254  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18001c258  call    cs:__imp_SysFreeString
0x18001c25f  nop     dword ptr [rax+rax+00h]
0x18001c264  mov     eax, ebx
0x18001c266  mov     rbx, [rsp+0C0h+arg_0]
0x18001c26e  add     rsp, 90h
0x18001c275  pop     r15
0x18001c277  pop     r14
0x18001c279  pop     r13
0x18001c27b  pop     r12
0x18001c27d  pop     rdi
0x18001c27e  pop     rsi
0x18001c27f  pop     rbp
0x18001c280  retn
0x18001c282  mov     esi, 5
0x18001c287  mov     [rbp+57h+arg_10], r14
0x18001c28b  lea     rax, ?Match@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; "Match"
0x18001c292  mov     [rbp+57h+var_60], esi
0x18001c295  lea     r15, asc_1801177B4; "']"
0x18001c29c  mov     [rbp+57h+var_58], rax
0x18001c2a0  lea     r8, [rbp+57h+arg_10]; unsigned int
0x18001c2a4  mov     [rbp+57h+var_50], esi
0x18001c2a7  lea     edi, [rsi-4]
0x18001c2aa  mov     [rbp+57h+var_48], r15
0x18001c2ae  mov     edx, edi; struct Appx::Packaging::XPathComponent *
0x18001c2b0  mov     [rbp+57h+var_40], r14d
0x18001c2b4  lea     rcx, [rbp+57h+var_60]; this
0x18001c2b8  call    ?BuildXPath@Packaging@Appx@@YAJPEBUXPathComponent@12@IAEAVAutoBStr@Common@@@Z; Appx::Packaging::BuildXPath(Appx::Packaging::XPathComponent const *,uint,Common::AutoBStr &)
0x18001c2bd  mov     ebx, eax
0x18001c2bf  test    eax, eax
0x18001c2c1  js      loc_18001C575
0x18001c2c7  lea     rax, ?Type@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; "Type"
0x18001c2ce  mov     [rbp+57h+arg_18], r14
0x18001c2d2  lea     r8, [rbp+57h+arg_18]; unsigned int
0x18001c2d6  mov     [rbp+57h+var_58], rax
0x18001c2da  mov     edx, edi; struct Appx::Packaging::XPathComponent *
0x18001c2dc  mov     [rbp+57h+var_60], esi
0x18001c2df  lea     rcx, [rbp+57h+var_60]; this
0x18001c2e3  mov     [rbp+57h+var_50], r12d
0x18001c2e7  mov     [rbp+57h+var_48], r15
0x18001c2eb  mov     [rbp+57h+var_40], r14d
0x18001c2ef  call    ?BuildXPath@Packaging@Appx@@YAJPEBUXPathComponent@12@IAEAVAutoBStr@Common@@@Z; Appx::Packaging::BuildXPath(Appx::Packaging::XPathComponent const *,uint,Common::AutoBStr &)
0x18001c2f4  mov     ebx, eax
0x18001c2f6  test    eax, eax
0x18001c2f8  js      loc_18001C515
0x18001c2fe  lea     rax, ?WindowsRuntimeAccess@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; "WindowsRuntimeAccess"
0x18001c305  mov     [rbp+57h+var_70], r14
0x18001c309  lea     r8, [rbp+57h+var_70]; unsigned int
0x18001c30d  mov     [rbp+57h+var_58], rax
0x18001c311  mov     edx, edi; struct Appx::Packaging::XPathComponent *
0x18001c313  mov     [rbp+57h+var_60], esi
0x18001c316  lea     rcx, [rbp+57h+var_60]; this
0x18001c31a  mov     [rbp+57h+var_50], 14h
0x18001c321  mov     [rbp+57h+var_48], r15
0x18001c325  mov     [rbp+57h+var_40], r14d
0x18001c329  call    ?BuildXPath@Packaging@Appx@@YAJPEBUXPathComponent@12@IAEAVAutoBStr@Common@@@Z; Appx::Packaging::BuildXPath(Appx::Packaging::XPathComponent const *,uint,Common::AutoBStr &)
0x18001c32e  mov     ebx, eax
0x18001c330  test    eax, eax
0x18001c332  js      loc_18001C5C6
0x18001c338  mov     r15, [rbp+57h+var_88]
0x18001c33c  mov     r12d, r14d
0x18001c33f  mov     rbx, [rbp+57h+arg_10]
0x18001c343  mov     rdi, [rbp+57h+arg_18]
0x18001c347  mov     rsi, [rbp+57h+var_70]
0x18001c34b  cmp     r12d, [rbp+57h+arg_8]
0x18001c34f  jge     loc_18001C4AD
0x18001c355  mov     [rbp+57h+var_90], r14
0x18001c359  lea     rcx, [rbp+57h+var_90]
0x18001c35d  mov     rax, [r15]
0x18001c360  mov     r14, [rax+48h]
0x18001c364  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18001c369  lea     rdx, [rbp+57h+var_90]
0x18001c36d  mov     rcx, r15
0x18001c370  mov     rax, r14
0x18001c373  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c378  mov     r14d, eax
0x18001c37b  test    eax, eax
0x18001c37d  js      loc_18001C58F
0x18001c383  lea     r8, [rbp+57h+var_78]
0x18001c387  mov     [rbp+57h+var_78], 0
0x18001c38f  mov     rdx, rbx
0x18001c392  mov     [rbp+57h+var_80], 0
0x18001c39a  lea     rcx, [rbp+57h+var_90]
0x18001c39e  call    ?GetRequiredNodeValue@Packaging@Appx@@YAJAEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEAGPEAPEAG@Z; Appx::Packaging::GetRequiredNodeValue(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort *,ushort * *)
0x18001c3a3  mov     r14d, eax
0x18001c3a6  test    eax, eax
0x18001c3a8  js      loc_18001C56B
0x18001c3ae  lea     r8, [rbp+57h+var_80]
0x18001c3b2  mov     rdx, rdi
0x18001c3b5  lea     rcx, [rbp+57h+var_90]
0x18001c3b9  call    ?GetRequiredNodeValue@Packaging@Appx@@YAJAEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEAGPEAPEAG@Z; Appx::Packaging::GetRequiredNodeValue(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort *,ushort * *)
0x18001c3be  mov     r14d, eax
0x18001c3c1  test    eax, eax
0x18001c3c3  js      loc_18001C458
0x18001c3c9  mov     rax, [rbp+57h+var_80]
0x18001c3cd  lea     r8, ?RuleTypeInclude@Attribute@Manifest@Packaging@Appx@@3QBGB; "include"
0x18001c3d4  sub     r8, rax
0x18001c3d7  movzx   ecx, word ptr [rax]
0x18001c3da  movzx   edx, word ptr [rax+r8]
0x18001c3df  sub     ecx, edx
0x18001c3e1  jnz     short loc_18001C3EB
0x18001c3e3  add     rax, 2
0x18001c3e7  test    edx, edx
0x18001c3e9  jnz     short loc_18001C3D7
0x18001c3eb  test    ecx, ecx
0x18001c3ed  jnz     loc_18001C61C
0x18001c3f3  mov     r14b, 1
0x18001c3f6  mov     r8, [rbp+57h+var_78]; unsigned __int16 *
0x18001c3fa  mov     r9b, r14b; bool
0x18001c3fd  mov     rdx, [rbp+57h+var_90]; struct IXMLDOMNode *
0x18001c401  mov     rcx, r13; this
0x18001c404  call    ?ValidateDomainRule@AppxManifestReaderImpl@Manifest@Packaging@Appx@@QEAAJPEAUIXMLDOMNode@@PEAG_N@Z; Appx::Packaging::Manifest::AppxManifestReaderImpl::ValidateDomainRule(IXMLDOMNode *,ushort *,bool)
0x18001c409  mov     r14d, eax
0x18001c40c  test    eax, eax
0x18001c40e  js      loc_18001C4EE
0x18001c414  mov     rcx, [rbp+57h+var_80]; bstrString
0x18001c418  call    cs:__imp_SysFreeString
0x18001c41f  nop     dword ptr [rax+rax+00h]
0x18001c424  mov     rcx, [rbp+57h+var_78]; bstrString
0x18001c428  call    cs:__imp_SysFreeString
0x18001c42f  nop     dword ptr [rax+rax+00h]
0x18001c434  mov     rcx, [rbp+57h+var_90]
0x18001c438  xor     r14d, r14d
0x18001c43b  test    rcx, rcx
0x18001c43e  jz      short loc_18001C450
0x18001c440  mov     [rbp+57h+var_90], r14
0x18001c444  mov     rax, [rcx]
0x18001c447  mov     rax, [rax+10h]
0x18001c44b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c450  inc     r12d
0x18001c453  jmp     loc_18001C34B
0x18001c458  mov     edx, 1BE1h; void *
0x18001c45d  mov     rcx, [rbp+5Fh]; this
0x18001c461  lea     r8, aOnecorePrintsc_127; "onecore\\printscan\\appxpackaging\\mani"...
0x18001c468  mov     r9d, r14d; char *
0x18001c46b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c470  mov     rcx, [rbp+57h+var_80]; bstrString
0x18001c474  call    cs:__imp_SysFreeString
0x18001c47b  nop     dword ptr [rax+rax+00h]
0x18001c480  mov     rcx, [rbp+57h+var_78]; bstrString
0x18001c484  call    cs:__imp_SysFreeString
0x18001c48b  nop     dword ptr [rax+rax+00h]
0x18001c490  mov     rcx, [rbp+57h+var_90]
0x18001c494  test    rcx, rcx
0x18001c497  jz      short loc_18001C4AD
0x18001c499  mov     [rbp+57h+var_90], 0
0x18001c4a1  mov     rax, [rcx]
0x18001c4a4  mov     rax, [rax+10h]
0x18001c4a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c4ad  mov     rcx, rsi; bstrString
0x18001c4b0  call    cs:__imp_SysFreeString
0x18001c4b7  nop     dword ptr [rax+rax+00h]
0x18001c4bc  mov     rcx, rdi; bstrString
0x18001c4bf  call    cs:__imp_SysFreeString
0x18001c4c6  nop     dword ptr [rax+rax+00h]
0x18001c4cb  mov     rcx, rbx; bstrString
0x18001c4ce  call    cs:__imp_SysFreeString
0x18001c4d5  nop     dword ptr [rax+rax+00h]
0x18001c4da  test    r15, r15
0x18001c4dd  jz      loc_18001C251
0x18001c4e3  mov     rax, [r15]
0x18001c4e6  mov     rcx, r15
0x18001c4e9  jmp     loc_18001C248
0x18001c4ee  mov     edx, 1BFDh
0x18001c4f3  jmp     loc_18001C45D
0x18001c4f8  mov     rcx, [rbp+5Fh]; this
0x18001c4fc  lea     r8, aOnecorePrintsc_127; "onecore\\printscan\\appxpackaging\\mani"...
0x18001c503  mov     r9d, eax; char *
0x18001c506  mov     edx, 1BC9h; void *
0x18001c50b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c510  jmp     loc_18001C254
0x18001c515  mov     rcx, [rbp+5Fh]; this
0x18001c519  lea     r8, aOnecorePrintsc_127; "onecore\\printscan\\appxpackaging\\mani"...
0x18001c520  mov     r9d, eax; char *
0x18001c523  mov     edx, 1BD3h; void *
0x18001c528  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c52d  mov     rcx, [rbp+57h+arg_18]; bstrString
0x18001c531  call    cs:__imp_SysFreeString
0x18001c538  nop     dword ptr [rax+rax+00h]
0x18001c53d  mov     rcx, [rbp+57h+arg_10]; bstrString
0x18001c541  call    cs:__imp_SysFreeString
0x18001c548  nop     dword ptr [rax+rax+00h]
0x18001c54d  mov     rcx, [rbp+57h+var_88]
0x18001c551  test    rcx, rcx
0x18001c554  jz      loc_18001C254
0x18001c55a  mov     rax, [rcx]
0x18001c55d  mov     rax, [rax+10h]
0x18001c561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c566  jmp     loc_18001C254
0x18001c56b  mov     edx, 1BDFh
0x18001c570  jmp     loc_18001C45D
0x18001c575  mov     rcx, [rbp+5Fh]; this
0x18001c579  lea     r8, aOnecorePrintsc_127; "onecore\\printscan\\appxpackaging\\mani"...
0x18001c580  mov     r9d, eax; char *
0x18001c583  mov     edx, 1BD1h; void *
0x18001c588  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c58d  jmp     short loc_18001C53D
0x18001c58f  mov     rcx, [rbp+5Fh]; this
0x18001c593  lea     r8, aOnecorePrintsc_127; "onecore\\printscan\\appxpackaging\\mani"...
0x18001c59a  mov     r9d, r14d; char *
0x18001c59d  mov     edx, 1BDAh; void *
0x18001c5a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c5a7  jmp     loc_18001C490
0x18001c5ac  mov     rcx, [rbp+5Fh]; this
0x18001c5b0  lea     r8, aOnecorePrintsc_127; "onecore\\printscan\\appxpackaging\\mani"...
0x18001c5b7  mov     r9d, eax; char *
0x18001c5ba  mov     edx, 1BCDh; void *
0x18001c5bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c5c4  jmp     short loc_18001C60E
0x18001c5c6  mov     rcx, [rbp+5Fh]; this
0x18001c5ca  lea     r8, aOnecorePrintsc_127; "onecore\\printscan\\appxpackaging\\mani"...
0x18001c5d1  mov     r9d, eax; char *
0x18001c5d4  mov     edx, 1BD5h; void *
0x18001c5d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c5de  mov     rcx, [rbp+57h+var_70]; bstrString
0x18001c5e2  call    cs:__imp_SysFreeString
0x18001c5e9  nop     dword ptr [rax+rax+00h]
0x18001c5ee  mov     rcx, [rbp+57h+arg_18]; bstrString
0x18001c5f2  call    cs:__imp_SysFreeString
0x18001c5f9  nop     dword ptr [rax+rax+00h]
0x18001c5fe  mov     rcx, [rbp+57h+arg_10]; bstrString
0x18001c602  call    cs:__imp_SysFreeString
0x18001c609  nop     dword ptr [rax+rax+00h]
0x18001c60e  lea     rcx, [rbp+57h+var_88]
0x18001c612  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18001c617  jmp     loc_18001C254
0x18001c61c  lea     r9, [rbp+57h+var_70]
0x18001c620  mov     [rbp+57h+var_70], 0
0x18001c628  xor     r8d, r8d
0x18001c62b  mov     [rsp+0C0h+var_A0], 0; int
0x18001c634  mov     rdx, rsi
0x18001c637  lea     rcx, [rbp+57h+var_90]
0x18001c63b  call    ?GetNodeValue@Packaging@Appx@@YAJAEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEAGJPEAPEAGPEAPEAUIXMLDOMNode@@@Z; Appx::Packaging::GetNodeValue(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort *,long,ushort * *,IXMLDOMNode * *)
0x18001c640  mov     r14d, eax
0x18001c643  xor     eax, eax
0x18001c645  test    r14d, r14d
0x18001c648  js      loc_18001C6E8
0x18001c64e  cmp     [rbp+57h+var_70], rax
0x18001c652  jnz     short loc_18001C66A
0x18001c654  xor     ecx, ecx; bstrString
0x18001c656  mov     r14b, al
0x18001c659  call    cs:__imp_SysFreeString
0x18001c660  nop     dword ptr [rax+rax+00h]
0x18001c665  jmp     loc_18001C3F6
0x18001c66a  mov     rdx, [rbp+57h+var_90]; struct IStream *
0x18001c66e  lea     r9, ?WindowsRuntimeAccess@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; "WindowsRuntimeAccess"
0x18001c675  mov     rcx, [r13+68h]; this
0x18001c679  xor     r8d, r8d; struct IXMLDOMNode *
0x18001c67c  mov     dword ptr [rbp+57h+arg_18], eax
0x18001c67f  mov     dword ptr [rbp+57h+arg_10], eax
0x18001c682  lea     rax, [rbp+57h+arg_10]
0x18001c686  mov     [rsp+0C0h+var_98], rax; unsigned int *
0x18001c68b  lea     rax, [rbp+57h+arg_18]
0x18001c68f  mov     [rsp+0C0h+var_A0], rax; unsigned __int16 *
0x18001c694  call    ?GetXmlLineInformation@XmlLineInformation@Packaging@Appx@@YAJPEAUIStream@@PEAUIXMLDOMNode@@PEBG2PEAI3@Z; Appx::Packaging::XmlLineInformation::GetXmlLineInformation(IStream *,IXMLDOMNode *,ushort const *,ushort const *,uint *,uint *)
0x18001c699  test    byte ptr cs:Microsoft_Windows_AppxPackagingOMEnableBits, 1
  ... truncated ...
```
