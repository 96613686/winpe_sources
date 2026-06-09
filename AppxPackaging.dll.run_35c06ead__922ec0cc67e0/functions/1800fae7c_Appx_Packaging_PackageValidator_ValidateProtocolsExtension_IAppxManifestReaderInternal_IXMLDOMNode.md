# Appx::Packaging::PackageValidator::ValidateProtocolsExtension(IAppxManifestReaderInternal *,IXMLDOMNode *)

- ea: `0x1800fae7c`
- end: `0x1800fb3fc`
- name: `?ValidateProtocolsExtension@PackageValidator@Packaging@Appx@@CAJPEAUIAppxManifestReaderInternal@@PEAUIXMLDOMNode@@@Z`
- size: `1408`
- prototype: `static int(struct IAppxManifestReaderInternal *, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800f9dcc`

## callees

- `0x180005eb8`
- `0x18002d770`
- `0x1800446d0`
- `0x18004afdc`
- `0x180094a38`
- `0x1800f9aac`
- `0x1800f9c84`
- `0x1800fae7c`
- `0x1800fec2c`
- `0x180106010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800fb333`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fb367`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fb399`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fb333`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fb367`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fb399`

## string_xrefs

- `0x1800fb2ac`: `Manifest validation error: Line %1!d!, Column %2!d!, Reason: Applications can't register for the "%3" protocol.\n`
- `0x1800fb30e`: `Manifest validation error: Line %1!d!, Column %2!d!, Reason: Applications can't register for the "%3" protocol.\n`
- `0x1800faeaf`: `application.manifest`
- `0x1800fb18f`: `*[local-name()='Applications']/*[local-name()='Application']/*[local-name()='Extensions']/*[local-name()='Extension']/*[local-name()='Protocol']`
- `0x1800faf01`: `comfile`
- `0x1800faf17`: `dllfile`
- `0x1800faf64`: `explorer.assocprotocol.search-ms`
- `0x1800fb04b`: `msi.package`
- `0x1800fb059`: `msi.patch`
- `0x1800fb1a4`: `(GetXmlNodes(manifestRoot, ProtocolsXPath, &nodeList, &numNodes))`
- `0x1800fb356`: `(StringCchLengthW(protocol, String::MaxLength - 1, &protocolLength))`
- `0x1800fb386`: `(GetXmlNodeText(node.Get(), Manifest::AttributeNameWithoutPrefix::Name, &protocol))`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::PackageValidator::ValidateProtocolsExtension(
        struct IAppxManifestReaderInternal *a1,
        struct IXMLDOMNode *a2)
{
  int XmlNodes; // eax
  bool v5; // cl
  unsigned int v6; // ebx
  struct IXMLDOMNodeList *v7; // rdi
  char v8; // r14
  int i; // r15d
  HRESULT (__stdcall *nextNode)(IXMLDOMNodeList *, IXMLDOMNode **); // rbx
  int v11; // eax
  bool v12; // cl
  int XmlNodeText; // eax
  bool v14; // cl
  OLECHAR *v15; // rbx
  int v16; // eax
  bool v17; // cl
  unsigned int v18; // esi
  __int64 v19; // rax
  unsigned int j; // esi
  __int64 v21; // rax
  BSTR bstrString; // [rsp+30h] [rbp-D0h] BYREF
  struct IXMLDOMNodeList *v24; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v25[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v26[58]; // [rsp+50h] [rbp-B0h]
  int v27; // [rsp+260h] [rbp+160h] BYREF
  struct IXMLDOMNode *v28; // [rsp+268h] [rbp+168h] BYREF

  v26[0] = L"accountpictureprovider";
  v26[1] = L"application.manifest";
  v26[2] = L"application.reference";
  v26[3] = L"batfile";
  v26[4] = L"blob";
  v26[5] = L"cerfile";
  v26[6] = L"chm.file";
  v26[7] = L"cmdfile";
  v26[8] = L"comfile";
  v26[9] = L"cplfile";
  v26[10] = L"dllfile";
  v26[11] = L"drvfile";
  v26[12] = L"exefile";
  v26[13] = L"explorer.assocactionid.burnselection";
  v26[14] = L"explorer.assocactionid.closesession";
  v26[15] = L"explorer.assocactionid.erasedisc";
  v26[16] = L"explorer.assocactionid.zipselection";
  v26[17] = L"explorer.assocprotocol.search-ms";
  v26[18] = L"explorer.burnselection";
  v26[19] = L"explorer.closesession";
  v26[20] = L"explorer.erasedisc";
  v26[21] = L"explorer.zipselection";
  v26[22] = L"file";
  v26[23] = L"fonfile";
  v26[24] = L"hlpfile";
  v26[25] = L"htafile";
  v26[26] = L"inffile";
  v26[27] = L"insfile";
  v26[28] = L"internetshortcut";
  v26[29] = L"jsefile";
  v26[30] = L"lnkfile";
  v26[31] = L"microsoft.powershellscript.1";
  v26[32] = L"ms-accountpictureprovider";
  v26[33] = L"ms-appdata";
  v26[34] = L"ms-appx";
  v26[35] = L"ms-appx-web";
  v26[36] = L"ms-autoplay";
  v26[37] = L"ms-windows-search";
  v26[38] = L"msi.package";
  v26[39] = L"msi.patch";
  v24 = 0;
  v26[40] = L"ocxfile";
  v26[41] = L"piffile";
  v26[42] = L"regfile";
  v26[43] = L"scrfile";
  v26[44] = L"scriptletfile";
  v26[45] = L"shbfile";
  v26[46] = L"shcmdfile";
  v26[47] = L"shsfile";
  v26[48] = L"smb";
  v26[49] = L"sysfile";
  v26[50] = L"ttffile";
  v26[51] = L"unknown";
  v26[52] = L"vbefile";
  v26[53] = L"vbsfile";
  v26[54] = L"windows.gadget";
  v26[55] = L"wsffile";
  v26[56] = L"wsfile";
  v26[57] = L"wshfile";
  v27 = 0;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v24);
  XmlNodes = Appx::Packaging::PackageValidator::GetXmlNodes(
               a2,
               L"*[local-name()='Applications']/*[local-name()='Application']/*[local-name()='Extensions']/*[local-name()="
                "'Extension']/*[local-name()='Protocol']",
               &v24,
               &v27);
  v6 = XmlNodes;
  if ( XmlNodes >= 0 )
  {
    v7 = v24;
    v8 = 1;
    for ( i = 0; i < v27; ++i )
    {
      v28 = 0;
      nextNode = v7->lpVtbl->nextNode;
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v28);
      v11 = ((__int64 (__fastcall *)(struct IXMLDOMNodeList *, struct IXMLDOMNode **))nextNode)(v7, &v28);
      v6 = v11;
      if ( v11 < 0 )
      {
        Appx::Packaging::SharedWithTools::Logging::WriteFailure(v12, v11, "(nodeList->nextNode(&node))", 0);
        goto LABEL_18;
      }
      bstrString = 0;
      XmlNodeText = Appx::Packaging::PackageValidator::GetXmlNodeText(v28, L"Name", &bstrString);
      v6 = XmlNodeText;
      if ( XmlNodeText < 0 )
      {
        Appx::Packaging::SharedWithTools::Logging::WriteFailure(
          v14,
          XmlNodeText,
          "(GetXmlNodeText(node.Get(), Manifest::AttributeNameWithoutPrefix::Name, &protocol))",
          0);
        SysFreeString(bstrString);
LABEL_18:
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v28);
        goto LABEL_20;
      }
      v15 = bstrString;
      *(_QWORD *)v25 = 0;
      v16 = StringCchLengthW(bstrString, 0x3FFFFFFEu, (unsigned __int64 *)v25);
      v18 = v16;
      if ( v16 < 0 )
      {
        Appx::Packaging::SharedWithTools::Logging::WriteFailure(
          v17,
          v16,
          "(StringCchLengthW(protocol, String::MaxLength - 1, &protocolLength))",
          0);
        SysFreeString(v15);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v28);
        v6 = v18;
        goto LABEL_20;
      }
      if ( (unsigned int)Common::String::CaseInsensitiveStartsWith(v15, v25[0], L"windows.", 8u) )
      {
        v19 = *(_QWORD *)a1;
        bstrString = 0;
        (*(void (__fastcall **)(struct IAppxManifestReaderInternal *, struct IXMLDOMNode *, const OLECHAR *, BSTR *))(v19 + 32))(
          a1,
          v28,
          L"Name",
          &bstrString);
        Appx::Packaging::SharedWithTools::Logging::WriteError(
          0,
          L"Manifest validation error: Line %1!d!, Column %2!d!, Reason: Applications can't register for the \"%3\" protocol.\n",
          (unsigned int)bstrString,
          HIDWORD(bstrString),
          v15);
        v8 = 0;
      }
      for ( j = 0; j < 0x3A; ++j )
      {
        if ( Common::String::CaseInsensitiveEquals(v15, v26[j]) )
        {
          v21 = *(_QWORD *)a1;
          bstrString = 0;
          (*(void (__fastcall **)(struct IAppxManifestReaderInternal *, struct IXMLDOMNode *, const OLECHAR *, BSTR *))(v21 + 32))(
            a1,
            v28,
            L"Name",
            &bstrString);
          Appx::Packaging::SharedWithTools::Logging::WriteError(
            0,
            L"Manifest validation error: Line %1!d!, Column %2!d!, Reason: Applications can't register for the \"%3\" protocol.\n",
            (unsigned int)bstrString,
            HIDWORD(bstrString),
            v15);
          v8 = 0;
        }
      }
      SysFreeString(v15);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v28);
    }
    v6 = v8 == 0 ? 0x80080204 : 0;
  }
  else
  {
    Appx::Packaging::SharedWithTools::Logging::WriteFailure(
      v5,
      XmlNodes,
      "(GetXmlNodes(manifestRoot, ProtocolsXPath, &nodeList, &numNodes))",
      0);
  }
LABEL_20:
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v24);
  return v6;
}

```

## disassembly

```asm
0x1800fae7c  mov     [rsp-8+arg_0], rbx
0x1800fae81  mov     [rsp-8+arg_8], rsi
0x1800fae86  push    rbp
0x1800fae87  push    rdi
0x1800fae88  push    r12
0x1800fae8a  push    r14
0x1800fae8c  push    r15
0x1800fae8e  lea     rbp, [rsp-120h]
0x1800fae96  sub     rsp, 220h
0x1800fae9d  lea     rax, aAccountpicture; "accountpictureprovider"
0x1800faea4  mov     rbx, rdx
0x1800faea7  mov     [rsp+240h+var_1F0], rax
0x1800faeac  mov     r12, rcx
0x1800faeaf  lea     rax, aApplicationMan; "application.manifest"
0x1800faeb6  mov     [rsp+240h+var_1E8], rax
0x1800faebb  lea     rax, aApplicationRef; "application.reference"
0x1800faec2  mov     [rsp+240h+var_1E0], rax
0x1800faec7  lea     rax, aBatfile; "batfile"
0x1800faece  mov     [rsp+240h+var_1D8], rax
0x1800faed3  lea     rax, aBlob; "blob"
0x1800faeda  mov     [rsp+240h+var_1D0], rax
0x1800faedf  lea     rax, aCerfile; "cerfile"
0x1800faee6  mov     [rsp+240h+var_1C8], rax
0x1800faeeb  lea     rax, aChmFile; "chm.file"
0x1800faef2  mov     [rbp+140h+var_1C0], rax
0x1800faef6  lea     rax, aCmdfile; "cmdfile"
0x1800faefd  mov     [rbp+140h+var_1B8], rax
0x1800faf01  lea     rax, aComfile; "comfile"
0x1800faf08  mov     [rbp+140h+var_1B0], rax
0x1800faf0c  lea     rax, aCplfile; "cplfile"
0x1800faf13  mov     [rbp+140h+var_1A8], rax
0x1800faf17  lea     rax, aDllfile; "dllfile"
0x1800faf1e  mov     [rbp+140h+var_1A0], rax
0x1800faf22  lea     rax, aDrvfile; "drvfile"
0x1800faf29  mov     [rbp+140h+var_198], rax
0x1800faf2d  lea     rax, aExefile; "exefile"
0x1800faf34  mov     [rbp+140h+var_190], rax
0x1800faf38  lea     rax, aExplorerAssoca_0; "explorer.assocactionid.burnselection"
0x1800faf3f  mov     [rbp+140h+var_188], rax
0x1800faf43  lea     rax, aExplorerAssoca_1; "explorer.assocactionid.closesession"
0x1800faf4a  mov     [rbp+140h+var_180], rax
0x1800faf4e  lea     rax, aExplorerAssoca; "explorer.assocactionid.erasedisc"
0x1800faf55  mov     [rbp+140h+var_178], rax
0x1800faf59  lea     rax, aExplorerAssoca_2; "explorer.assocactionid.zipselection"
0x1800faf60  mov     [rbp+140h+var_170], rax
0x1800faf64  lea     rax, aExplorerAssocp; "explorer.assocprotocol.search-ms"
0x1800faf6b  mov     [rbp+140h+var_168], rax
0x1800faf6f  lea     rax, aExplorerBurnse; "explorer.burnselection"
0x1800faf76  mov     [rbp+140h+var_160], rax
0x1800faf7a  lea     rax, aExplorerCloses; "explorer.closesession"
0x1800faf81  mov     [rbp+140h+var_158], rax
0x1800faf85  lea     rax, aExplorerErased; "explorer.erasedisc"
0x1800faf8c  mov     [rbp+140h+var_150], rax
0x1800faf90  lea     rax, aExplorerZipsel; "explorer.zipselection"
0x1800faf97  mov     [rbp+140h+var_148], rax
0x1800faf9b  lea     rax, aFile; "file"
0x1800fafa2  mov     [rbp+140h+var_140], rax
0x1800fafa6  lea     rax, aFonfile; "fonfile"
0x1800fafad  mov     [rbp+140h+var_138], rax
0x1800fafb1  lea     rax, aHlpfile; "hlpfile"
0x1800fafb8  mov     [rbp+140h+var_130], rax
0x1800fafbc  lea     rax, aHtafile; "htafile"
0x1800fafc3  mov     [rbp+140h+var_128], rax
0x1800fafc7  lea     rax, aInffile; "inffile"
0x1800fafce  mov     [rbp+140h+var_120], rax
0x1800fafd2  lea     rax, aInsfile; "insfile"
0x1800fafd9  mov     [rbp+140h+var_118], rax
0x1800fafdd  lea     rax, aInternetshortc; "internetshortcut"
0x1800fafe4  mov     [rbp+140h+var_110], rax
0x1800fafe8  lea     rax, aJsefile; "jsefile"
0x1800fafef  mov     [rbp+140h+var_108], rax
0x1800faff3  lea     rax, aLnkfile; "lnkfile"
0x1800faffa  mov     [rbp+140h+var_100], rax
0x1800faffe  lea     rax, aMicrosoftPower; "microsoft.powershellscript.1"
0x1800fb005  mov     [rbp+140h+var_F8], rax
0x1800fb009  lea     rax, aMsAccountpictu; "ms-accountpictureprovider"
0x1800fb010  mov     [rbp+140h+var_F0], rax
0x1800fb014  lea     rax, aMsAppdata; "ms-appdata"
0x1800fb01b  mov     [rbp+140h+var_E8], rax
0x1800fb01f  lea     rax, aMsAppx; "ms-appx"
0x1800fb026  mov     [rbp+140h+var_E0], rax
0x1800fb02a  lea     rax, aMsAppxWeb; "ms-appx-web"
0x1800fb031  mov     [rbp+140h+var_D8], rax
0x1800fb035  lea     rax, aMsAutoplay; "ms-autoplay"
0x1800fb03c  mov     [rbp+140h+var_D0], rax
0x1800fb040  lea     rax, aMsWindowsSearc; "ms-windows-search"
0x1800fb047  mov     [rbp+140h+var_C8], rax
0x1800fb04b  lea     rax, aMsiPackage; "msi.package"
0x1800fb052  mov     [rbp+140h+var_C0], rax
0x1800fb059  lea     rax, aMsiPatch; "msi.patch"
0x1800fb060  mov     [rbp+140h+var_B8], rax
0x1800fb067  lea     rcx, [rsp+240h+var_208]
0x1800fb06c  lea     rax, aOcxfile; "ocxfile"
0x1800fb073  mov     [rsp+240h+var_208], 0
0x1800fb07c  mov     [rbp+140h+var_B0], rax
0x1800fb083  lea     rax, aPiffile; "piffile"
0x1800fb08a  mov     [rbp+140h+var_A8], rax
0x1800fb091  lea     rax, aRegfile; "regfile"
0x1800fb098  mov     [rbp+140h+var_A0], rax
0x1800fb09f  lea     rax, aScrfile; "scrfile"
0x1800fb0a6  mov     [rbp+140h+var_98], rax
0x1800fb0ad  lea     rax, aScriptletfile; "scriptletfile"
0x1800fb0b4  mov     [rbp+140h+var_90], rax
0x1800fb0bb  lea     rax, aShbfile; "shbfile"
0x1800fb0c2  mov     [rbp+140h+var_88], rax
0x1800fb0c9  lea     rax, aShcmdfile; "shcmdfile"
0x1800fb0d0  mov     [rbp+140h+var_80], rax
0x1800fb0d7  lea     rax, aShsfile; "shsfile"
0x1800fb0de  mov     [rbp+140h+var_78], rax
0x1800fb0e5  lea     rax, aSmb; "smb"
0x1800fb0ec  mov     [rbp+140h+var_70], rax
0x1800fb0f3  lea     rax, aSysfile; "sysfile"
0x1800fb0fa  mov     [rbp+140h+var_68], rax
0x1800fb101  lea     rax, aTtffile; "ttffile"
0x1800fb108  mov     [rbp+140h+var_60], rax
0x1800fb10f  lea     rax, aUnknown; "unknown"
0x1800fb116  mov     [rbp+140h+var_58], rax
0x1800fb11d  lea     rax, aVbefile; "vbefile"
0x1800fb124  mov     [rbp+140h+var_50], rax
0x1800fb12b  lea     rax, aVbsfile; "vbsfile"
0x1800fb132  mov     [rbp+140h+var_48], rax
0x1800fb139  lea     rax, aWindowsGadget; "windows.gadget"
0x1800fb140  mov     [rbp+140h+var_40], rax
0x1800fb147  lea     rax, aWsffile; "wsffile"
0x1800fb14e  mov     [rbp+140h+var_38], rax
0x1800fb155  lea     rax, aWsfile; "wsfile"
0x1800fb15c  mov     [rbp+140h+var_30], rax
0x1800fb163  lea     rax, aWshfile; "wshfile"
0x1800fb16a  mov     [rbp+140h+var_28], rax
0x1800fb171  mov     [rbp+140h+arg_10], 0
0x1800fb17b  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800fb180  lea     r9, [rbp+140h+arg_10]; int *
0x1800fb187  mov     rcx, rbx; struct IXMLDOMNode *
0x1800fb18a  lea     r8, [rsp+240h+var_208]; struct IXMLDOMNodeList **
0x1800fb18f  lea     rdx, aLocalNameAppli_37; "*[local-name()='Applications']/*[local-"...
0x1800fb196  call    ?GetXmlNodes@PackageValidator@Packaging@Appx@@CAJPEAUIXMLDOMNode@@PEBGPEAPEAUIXMLDOMNodeList@@PEAJ@Z; Appx::Packaging::PackageValidator::GetXmlNodes(IXMLDOMNode *,ushort const *,IXMLDOMNodeList * *,long *)
0x1800fb19b  mov     ebx, eax
0x1800fb19d  test    eax, eax
0x1800fb19f  jns     short loc_1800FB1B7
0x1800fb1a1  xor     r9d, r9d; unsigned __int16 *
0x1800fb1a4  lea     r8, aGetxmlnodesMan_2; "(GetXmlNodes(manifestRoot, ProtocolsXPa"...
0x1800fb1ab  mov     edx, eax; int
0x1800fb1ad  call    ?WriteFailure@Logging@SharedWithTools@Packaging@Appx@@SAX_NJPEBDPEBG@Z; Appx::Packaging::SharedWithTools::Logging::WriteFailure(bool,long,char const *,ushort const *)
0x1800fb1b2  jmp     loc_1800FB3D3
0x1800fb1b7  mov     rdi, [rsp+240h+var_208]
0x1800fb1bc  mov     r14b, 1
0x1800fb1bf  xor     r15d, r15d
0x1800fb1c2  cmp     r15d, [rbp+140h+arg_10]
0x1800fb1c9  jge     loc_1800FB3C6
0x1800fb1cf  mov     [rbp+140h+arg_18], 0
0x1800fb1da  lea     rcx, [rbp+140h+arg_18]
0x1800fb1e1  mov     rax, [rdi]
0x1800fb1e4  mov     rbx, [rax+48h]
0x1800fb1e8  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800fb1ed  lea     rdx, [rbp+140h+arg_18]
0x1800fb1f4  mov     rcx, rdi
0x1800fb1f7  mov     rax, rbx
0x1800fb1fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb1ff  mov     ebx, eax
0x1800fb201  test    eax, eax
0x1800fb203  js      loc_1800FB3A7
0x1800fb209  mov     rcx, [rbp+140h+arg_18]; struct IXMLDOMNode *
0x1800fb210  lea     r8, [rsp+240h+bstrString]; unsigned __int16 **
0x1800fb215  lea     rdx, ?Name@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; "Name"
0x1800fb21c  mov     [rsp+240h+bstrString], 0
0x1800fb225  call    ?GetXmlNodeText@PackageValidator@Packaging@Appx@@CAJPEAUIXMLDOMNode@@PEBGPEAPEAG@Z; Appx::Packaging::PackageValidator::GetXmlNodeText(IXMLDOMNode *,ushort const *,ushort * *)
0x1800fb22a  mov     ebx, eax
0x1800fb22c  test    eax, eax
0x1800fb22e  js      loc_1800FB383
0x1800fb234  mov     rbx, [rsp+240h+bstrString]
0x1800fb239  lea     r8, [rsp+240h+var_200]; unsigned __int64 *
0x1800fb23e  mov     rcx, rbx; unsigned __int16 *
0x1800fb241  mov     qword ptr [rsp+240h+var_200], 0
0x1800fb24a  mov     edx, 3FFFFFFEh; unsigned __int64
0x1800fb24f  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800fb254  mov     esi, eax
0x1800fb256  test    eax, eax
0x1800fb258  js      loc_1800FB353
0x1800fb25e  mov     edx, [rsp+240h+var_200]; unsigned int
0x1800fb262  lea     r8, aWindows; "windows."
0x1800fb269  mov     r9d, 8; unsigned int
0x1800fb26f  mov     rcx, rbx; lpString1
0x1800fb272  call    ?CaseInsensitiveStartsWith@String@Common@@SAHPEBGK0K@Z; Common::String::CaseInsensitiveStartsWith(ushort const *,ulong,ushort const *,ulong)
0x1800fb277  test    eax, eax
0x1800fb279  jz      short loc_1800FB2C7
0x1800fb27b  mov     rax, [r12]
0x1800fb27f  lea     r9, [rsp+240h+bstrString]
0x1800fb284  mov     rdx, [rbp+140h+arg_18]
0x1800fb28b  lea     r8, ?Name@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; "Name"
0x1800fb292  mov     rcx, r12
0x1800fb295  mov     [rsp+240h+bstrString], 0
0x1800fb29e  mov     rax, [rax+20h]
0x1800fb2a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb2a7  mov     r9d, dword ptr [rsp+240h+bstrString+4]
0x1800fb2ac  lea     rdx, aManifestValida_3; "Manifest validation error: Line %1!d!, "...
0x1800fb2b3  mov     r8d, dword ptr [rsp+240h+bstrString]
0x1800fb2b8  xor     ecx, ecx; bool
0x1800fb2ba  mov     [rsp+240h+var_220], rbx
0x1800fb2bf  call    ?WriteError@Logging@SharedWithTools@Packaging@Appx@@SAX_NPEBGZZ; Appx::Packaging::SharedWithTools::Logging::WriteError(bool,ushort const *,...)
0x1800fb2c4  xor     r14b, r14b
0x1800fb2c7  xor     esi, esi
0x1800fb2c9  movsxd  rdx, esi
0x1800fb2cc  mov     rcx, rbx; unsigned __int16 *
0x1800fb2cf  mov     rdx, [rsp+rdx*8+240h+var_1F0]; unsigned __int16 *
0x1800fb2d4  call    ?CaseInsensitiveEquals@String@Common@@SAHPEBG0@Z; Common::String::CaseInsensitiveEquals(ushort const *,ushort const *)
0x1800fb2d9  test    eax, eax
0x1800fb2db  jz      short loc_1800FB329
0x1800fb2dd  mov     rax, [r12]
0x1800fb2e1  lea     r9, [rsp+240h+bstrString]
0x1800fb2e6  mov     rdx, [rbp+140h+arg_18]
0x1800fb2ed  lea     r8, ?Name@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; "Name"
0x1800fb2f4  mov     rcx, r12
0x1800fb2f7  mov     [rsp+240h+bstrString], 0
0x1800fb300  mov     rax, [rax+20h]
0x1800fb304  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb309  mov     r9d, dword ptr [rsp+240h+bstrString+4]
0x1800fb30e  lea     rdx, aManifestValida_3; "Manifest validation error: Line %1!d!, "...
0x1800fb315  mov     r8d, dword ptr [rsp+240h+bstrString]
0x1800fb31a  xor     ecx, ecx; bool
0x1800fb31c  mov     [rsp+240h+var_220], rbx
0x1800fb321  call    ?WriteError@Logging@SharedWithTools@Packaging@Appx@@SAX_NPEBGZZ; Appx::Packaging::SharedWithTools::Logging::WriteError(bool,ushort const *,...)
0x1800fb326  xor     r14b, r14b
0x1800fb329  inc     esi
0x1800fb32b  cmp     esi, 3Ah ; ':'
0x1800fb32e  jb      short loc_1800FB2C9
0x1800fb330  mov     rcx, rbx; bstrString
0x1800fb333  call    cs:__imp_SysFreeString
0x1800fb33a  nop     dword ptr [rax+rax+00h]
0x1800fb33f  lea     rcx, [rbp+140h+arg_18]
0x1800fb346  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800fb34b  inc     r15d
0x1800fb34e  jmp     loc_1800FB1C2
0x1800fb353  xor     r9d, r9d; unsigned __int16 *
0x1800fb356  lea     r8, aStringcchlengt; "(StringCchLengthW(protocol, String::Max"...
0x1800fb35d  mov     edx, esi; int
0x1800fb35f  call    ?WriteFailure@Logging@SharedWithTools@Packaging@Appx@@SAX_NJPEBDPEBG@Z; Appx::Packaging::SharedWithTools::Logging::WriteFailure(bool,long,char const *,ushort const *)
0x1800fb364  mov     rcx, rbx; bstrString
0x1800fb367  call    cs:__imp_SysFreeString
0x1800fb36e  nop     dword ptr [rax+rax+00h]
0x1800fb373  lea     rcx, [rbp+140h+arg_18]
0x1800fb37a  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800fb37f  mov     ebx, esi
0x1800fb381  jmp     short loc_1800FB3D3
0x1800fb383  xor     r9d, r9d; unsigned __int16 *
0x1800fb386  lea     r8, aGetxmlnodetext_2; "(GetXmlNodeText(node.Get(), Manifest::A"...
0x1800fb38d  mov     edx, eax; int
0x1800fb38f  call    ?WriteFailure@Logging@SharedWithTools@Packaging@Appx@@SAX_NJPEBDPEBG@Z; Appx::Packaging::SharedWithTools::Logging::WriteFailure(bool,long,char const *,ushort const *)
0x1800fb394  mov     rcx, [rsp+240h+bstrString]; bstrString
0x1800fb399  call    cs:__imp_SysFreeString
0x1800fb3a0  nop     dword ptr [rax+rax+00h]
0x1800fb3a5  jmp     short loc_1800FB3B8
0x1800fb3a7  xor     r9d, r9d; unsigned __int16 *
0x1800fb3aa  lea     r8, aNodelistNextno; "(nodeList->nextNode(&node))"
0x1800fb3b1  mov     edx, eax; int
0x1800fb3b3  call    ?WriteFailure@Logging@SharedWithTools@Packaging@Appx@@SAX_NJPEBDPEBG@Z; Appx::Packaging::SharedWithTools::Logging::WriteFailure(bool,long,char const *,ushort const *)
0x1800fb3b8  lea     rcx, [rbp+140h+arg_18]
0x1800fb3bf  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800fb3c4  jmp     short loc_1800FB3D3
0x1800fb3c6  neg     r14b
0x1800fb3c9  sbb     ebx, ebx
0x1800fb3cb  not     ebx
0x1800fb3cd  and     ebx, 80080204h
0x1800fb3d3  lea     rcx, [rsp+240h+var_208]
0x1800fb3d8  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800fb3dd  lea     r11, [rsp+240h+var_20]
0x1800fb3e5  mov     eax, ebx
0x1800fb3e7  mov     rbx, [r11+30h]
0x1800fb3eb  mov     rsi, [r11+38h]
0x1800fb3ef  mov     rsp, r11
0x1800fb3f2  pop     r15
0x1800fb3f4  pop     r14
0x1800fb3f6  pop     r12
0x1800fb3f8  pop     rdi
0x1800fb3f9  pop     rbp
0x1800fb3fa  retn
```
