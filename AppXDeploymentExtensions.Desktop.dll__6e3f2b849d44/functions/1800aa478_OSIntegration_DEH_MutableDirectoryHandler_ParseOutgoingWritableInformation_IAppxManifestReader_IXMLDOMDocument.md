# OSIntegration::DEH::MutableDirectoryHandler::ParseOutgoingWritableInformation(IAppxManifestReader *,IXMLDOMDocument *)

- ea: `0x1800aa478`
- end: `0x1800aa818`
- name: `?ParseOutgoingWritableInformation@MutableDirectoryHandler@DEH@OSIntegration@@AEAAJPEAUIAppxManifestReader@@PEAUIXMLDOMDocument@@@Z`
- size: `928`
- prototype: `__int64 __fastcall(OSIntegration::DEH::MutableDirectoryHandler *this, struct IAppxManifestReader *, struct IXMLDOMDocument *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800aa10c`

## callees

- `0x180006970`
- `0x180011020`
- `0x180012da0`
- `0x18001adb4`
- `0x180091b3c`
- `0x1800aa478`
- `0x1800af1bc`
- `0x180180038`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800aa643`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800aa6f0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800aa7a9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800aa643`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800aa6f0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800aa7a9`

## string_xrefs

- `0x1800aa4b9`: `onecore\admin\appmodel\osim\src\deh\appx\mutabledirectory\mutabledirectoryhandler.cpp`
- `0x1800aa500`: `onecore\admin\appmodel\osim\src\deh\appx\mutabledirectory\mutabledirectoryhandler.cpp`
- `0x1800aa557`: `onecore\admin\appmodel\osim\src\deh\appx\mutabledirectory\mutabledirectoryhandler.cpp`
- `0x1800aa5a8`: `onecore\admin\appmodel\osim\src\deh\appx\mutabledirectory\mutabledirectoryhandler.cpp`
- `0x1800aa5fc`: `onecore\admin\appmodel\osim\src\deh\appx\mutabledirectory\mutabledirectoryhandler.cpp`
- `0x1800aa689`: `onecore\admin\appmodel\osim\src\deh\appx\mutabledirectory\mutabledirectoryhandler.cpp`
- `0x1800aa737`: `onecore\admin\appmodel\osim\src\deh\appx\mutabledirectory\mutabledirectoryhandler.cpp`
- `0x1800aa4e7`: `/*[local-name()='Package']/*[local-name()='Extensions']/*[local-name()='Extension' and @Category='windows.installedLocationVirtualization']`
- `0x1800aa53e`: `*[local-name()='InstalledLocationVirtualization']`
- `0x1800aa58f`: `*[local-name()='UpdateActions']`
- `0x1800aa498`: `packageWriteRedirectionCompatibilityShim`

## pseudocode

```c
__int64 __fastcall OSIntegration::DEH::MutableDirectoryHandler::ParseOutgoingWritableInformation(
        OSIntegration::DEH::MutableDirectoryHandler *this,
        struct IAppxManifestReader *a2,
        struct IXMLDOMDocument *a3)
{
  int HasCapabilityInManifest; // eax
  unsigned int v6; // ebx
  struct IXMLDOMElement **v7; // r9
  int XMLElementFromQueryForDocument; // eax
  struct IXMLDOMElement **v9; // r9
  int XMLElementFromQuery; // eax
  struct IXMLDOMElement **v11; // r9
  int v12; // eax
  int AttributeValueStringFromElement; // eax
  const struct std::nothrow_t *v14; // rdx
  WCHAR *v15; // rbx
  int v16; // eax
  int v17; // esi
  const struct std::nothrow_t *v18; // rdx
  WCHAR *v19; // rsi
  int v20; // eax
  const struct std::nothrow_t *v21; // rdx
  int v22; // r14d
  const struct std::nothrow_t *v23; // rdx
  WCHAR *v24; // r14
  bool *bIgnoreCase; // [rsp+20h] [rbp-40h]
  int *bIgnoreCasea; // [rsp+20h] [rbp-40h]
  int *bIgnoreCaseb; // [rsp+20h] [rbp-40h]
  int *bIgnoreCasec; // [rsp+20h] [rbp-40h]
  BOOL bIgnoreCased; // [rsp+20h] [rbp-40h]
  struct IXMLDOMElement v31; // [rsp+30h] [rbp-30h] BYREF
  struct IXMLDOMDocument v32; // [rsp+38h] [rbp-28h] BYREF
  LPCWCH lpString1[2]; // [rsp+40h] [rbp-20h] BYREF
  int v34; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  int v36; // [rsp+90h] [rbp+30h] BYREF
  struct IXMLDOMElement v37; // [rsp+A8h] [rbp+48h] BYREF

  HasCapabilityInManifest = Common::Deployment::HasCapabilityInManifest(
                              (Common::Deployment *)a2,
                              (struct IAppxManifestReader *)2,
                              (enum APPX_CAPABILITY_CLASS_TYPE)L"packageWriteRedirectionCompatibilityShim",
                              (const unsigned __int16 *)this + 33,
                              bIgnoreCase);
  v6 = HasCapabilityInManifest;
  if ( HasCapabilityInManifest >= 0 )
  {
    v32.lpVtbl = 0;
    Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v32);
    XMLElementFromQueryForDocument = Common::Xml::GetXMLElementFromQueryForDocument(
                                       (Common::Xml *)L"/*[local-name()='Package']/*[local-name()='Extensions']/*[local-na"
                                                       "me()='Extension' and @Category='windows.installedLocationVirtualization']",
                                       (const unsigned __int16 *)a3,
                                       &v32,
                                       v7);
    v6 = XMLElementFromQueryForDocument;
    if ( XMLElementFromQueryForDocument < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB0,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\mutabledirectory\\mutabledirectoryhandler.cpp",
        (const char *)(unsigned int)XMLElementFromQueryForDocument,
        (int)bIgnoreCasea);
LABEL_46:
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v32);
      return v6;
    }
    if ( v32.lpVtbl )
    {
      *((_BYTE *)this + 65) = 1;
      v31.lpVtbl = 0;
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v31);
      XMLElementFromQuery = Common::Xml::GetXMLElementFromQuery(
                              (OLECHAR *)L"*[local-name()='InstalledLocationVirtualization']",
                              (const unsigned __int16 *)v32.lpVtbl,
                              &v31,
                              v9);
      v6 = XMLElementFromQuery;
      if ( XMLElementFromQuery < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB6,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\mutabledirectory\\mutabledirectoryhandler.cpp",
          (const char *)(unsigned int)XMLElementFromQuery,
          (int)bIgnoreCasea);
LABEL_8:
        Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v31);
        goto LABEL_46;
      }
      v37.lpVtbl = 0;
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v37);
      v12 = Common::Xml::GetXMLElementFromQuery(
              (OLECHAR *)L"*[local-name()='UpdateActions']",
              (const unsigned __int16 *)v31.lpVtbl,
              &v37,
              v11);
      v6 = v12;
      if ( v12 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xBA,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\mutabledirectory\\mutabledirectoryhandler.cpp",
          (const char *)(unsigned int)v12,
          (int)bIgnoreCasea);
LABEL_11:
        Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v37);
        goto LABEL_8;
      }
      v36 = 0;
      *(_OWORD *)lpString1 = 0;
      v34 = 0;
      AttributeValueStringFromElement = Common::Xml::GetAttributeValueStringFromElement(
                                          (Common::Xml *)v37.lpVtbl,
                                          (struct IXMLDOMElement *)&stru_1801DA4D0,
                                          (const unsigned __int16 *)lpString1,
                                          (struct Common::StringBuffer *)&v36,
                                          bIgnoreCasea);
      v6 = AttributeValueStringFromElement;
      if ( AttributeValueStringFromElement < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xBF,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\mutabledirectory\\mutabledirectoryhandler.cpp",
          (const char *)(unsigned int)AttributeValueStringFromElement,
          (int)bIgnoreCaseb);
        if ( lpString1[1] )
          operator delete((void *)lpString1[1], v14);
        goto LABEL_11;
      }
      v15 = (WCHAR *)lpString1[1];
      if ( v36 && CompareStringOrdinal(lpString1[1], -1, L"reset", -1, 1) == 2 )
        *((_DWORD *)this + 24) |= 4u;
      *(_OWORD *)lpString1 = 0;
      v34 = 0;
      v16 = Common::Xml::GetAttributeValueStringFromElement(
              (Common::Xml *)v37.lpVtbl,
              (struct IXMLDOMElement *)&stru_1801DA490,
              (const unsigned __int16 *)lpString1,
              (struct Common::StringBuffer *)&v36,
              bIgnoreCaseb);
      v17 = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC7,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\mutabledirectory\\mutabledirectoryhandler.cpp",
          (const char *)(unsigned int)v16,
          (int)bIgnoreCasec);
        if ( lpString1[1] )
          operator delete((void *)lpString1[1], v18);
        if ( v15 )
          operator delete(v15, v18);
        Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v37);
        Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v31);
        v6 = v17;
        goto LABEL_46;
      }
      v19 = (WCHAR *)lpString1[1];
      if ( v36 && CompareStringOrdinal(lpString1[1], -1, L"reset", -1, 1) == 2 )
        *((_DWORD *)this + 24) |= 1u;
      *(_OWORD *)lpString1 = 0;
      v34 = 0;
      v20 = Common::Xml::GetAttributeValueStringFromElement(
              (Common::Xml *)v37.lpVtbl,
              (struct IXMLDOMElement *)&stru_1801DA4B0,
              (const unsigned __int16 *)lpString1,
              (struct Common::StringBuffer *)&v36,
              bIgnoreCasec);
      v22 = v20;
      if ( v20 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xCF,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\mutabledirectory\\mutabledirectoryhandler.cpp",
          (const char *)(unsigned int)v20,
          bIgnoreCased);
        if ( lpString1[1] )
          operator delete((void *)lpString1[1], v23);
        if ( v19 )
          operator delete(v19, v23);
        if ( v15 )
          operator delete(v15, v23);
        Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v37);
        Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v31);
        v6 = v22;
        goto LABEL_46;
      }
      v24 = (WCHAR *)lpString1[1];
      if ( v36 && CompareStringOrdinal(lpString1[1], -1, L"reset", -1, 1) == 2 )
        *((_DWORD *)this + 24) |= 2u;
      if ( v24 )
        operator delete(v24, v21);
      if ( v19 )
        operator delete(v19, v21);
      if ( v15 )
        operator delete(v15, v21);
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v37);
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v31);
    }
    v6 = 0;
    goto LABEL_46;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xAC,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\mutabledirectory\\mutabledirectoryhandler.cpp",
    (const char *)(unsigned int)HasCapabilityInManifest,
    (int)bIgnoreCasea);
  return v6;
}

```

## disassembly

```asm
0x1800aa478  mov     [rsp-28h+arg_8], rbx
0x1800aa47d  push    rbp
0x1800aa47e  push    rsi
0x1800aa47f  push    rdi
0x1800aa480  push    r12
0x1800aa482  push    r14
0x1800aa484  mov     rbp, rsp
0x1800aa487  sub     rsp, 60h
0x1800aa48b  mov     rsi, r8
0x1800aa48e  mov     rax, rdx
0x1800aa491  mov     rdi, rcx
0x1800aa494  lea     r9, [rcx+42h]; unsigned __int16 *
0x1800aa498  lea     r8, SourceString; "packageWriteRedirectionCompatibilityShi"...
0x1800aa49f  mov     edx, 2; struct IAppxManifestReader *
0x1800aa4a4  mov     rcx, rax; this
0x1800aa4a7  call    ?HasCapabilityInManifest@Deployment@Common@@YAJPEAUIAppxManifestReader@@W4APPX_CAPABILITY_CLASS_TYPE@@PEBGPEA_N@Z; Common::Deployment::HasCapabilityInManifest(IAppxManifestReader *,APPX_CAPABILITY_CLASS_TYPE,ushort const *,bool *)
0x1800aa4ac  mov     ebx, eax
0x1800aa4ae  test    eax, eax
0x1800aa4b0  jns     short loc_1800AA4CF
0x1800aa4b2  mov     rcx, [rbp+28h]; this
0x1800aa4b6  mov     r9d, eax; char *
0x1800aa4b9  lea     r8, aOnecoreAdminAp_115; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800aa4c0  mov     edx, 0ACh; void *
0x1800aa4c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aa4ca  jmp     loc_1800AA801
0x1800aa4cf  mov     [rbp+var_28.lpVtbl], 0
0x1800aa4d7  lea     rcx, [rbp+var_28]
0x1800aa4db  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x1800aa4e0  lea     r8, [rbp+var_28]; struct IXMLDOMDocument *
0x1800aa4e4  mov     rdx, rsi; unsigned __int16 *
0x1800aa4e7  lea     rcx, aLocalNamePacka_3; "/*[local-name()='Package']/*[local-name"...
0x1800aa4ee  call    ?GetXMLElementFromQueryForDocument@Xml@Common@@YAJPEBGPEAUIXMLDOMDocument@@PEAPEAUIXMLDOMElement@@@Z; Common::Xml::GetXMLElementFromQueryForDocument(ushort const *,IXMLDOMDocument *,IXMLDOMElement * *)
0x1800aa4f3  mov     ebx, eax
0x1800aa4f5  test    eax, eax
0x1800aa4f7  jns     short loc_1800AA516
0x1800aa4f9  mov     rcx, [rbp+28h]; this
0x1800aa4fd  mov     r9d, eax; char *
0x1800aa500  lea     r8, aOnecoreAdminAp_115; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800aa507  mov     edx, 0B0h; void *
0x1800aa50c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aa511  jmp     loc_1800AA7F8
0x1800aa516  cmp     [rbp+var_28.lpVtbl], 0
0x1800aa51b  jz      loc_1800AA7F6
0x1800aa521  mov     byte ptr [rdi+41h], 1
0x1800aa525  mov     [rbp+var_30.lpVtbl], 0
0x1800aa52d  lea     rcx, [rbp+var_30]
0x1800aa531  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x1800aa536  lea     r8, [rbp+var_30]; struct IXMLDOMElement *
0x1800aa53a  mov     rdx, [rbp+var_28.lpVtbl]; unsigned __int16 *
0x1800aa53e  lea     rcx, aLocalNameInsta_0; "*[local-name()='InstalledLocationVirtua"...
0x1800aa545  call    ?GetXMLElementFromQuery@Xml@Common@@YAJPEBGPEAUIXMLDOMElement@@PEAPEAU3@@Z; Common::Xml::GetXMLElementFromQuery(ushort const *,IXMLDOMElement *,IXMLDOMElement * *)
0x1800aa54a  mov     ebx, eax
0x1800aa54c  test    eax, eax
0x1800aa54e  jns     short loc_1800AA576
0x1800aa550  mov     rcx, [rbp+28h]; this
0x1800aa554  mov     r9d, eax; char *
0x1800aa557  lea     r8, aOnecoreAdminAp_115; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800aa55e  mov     edx, 0B6h; void *
0x1800aa563  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aa568  lea     rcx, [rbp+var_30]
0x1800aa56c  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x1800aa571  jmp     loc_1800AA7F8
0x1800aa576  mov     [rbp+arg_18.lpVtbl], 0
0x1800aa57e  lea     rcx, [rbp+arg_18]
0x1800aa582  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x1800aa587  lea     r8, [rbp+arg_18]; struct IXMLDOMElement *
0x1800aa58b  mov     rdx, [rbp+var_30.lpVtbl]; unsigned __int16 *
0x1800aa58f  lea     rcx, aLocalNameUpdat; "*[local-name()='UpdateActions']"
0x1800aa596  call    ?GetXMLElementFromQuery@Xml@Common@@YAJPEBGPEAUIXMLDOMElement@@PEAPEAU3@@Z; Common::Xml::GetXMLElementFromQuery(ushort const *,IXMLDOMElement *,IXMLDOMElement * *)
0x1800aa59b  mov     ebx, eax
0x1800aa59d  test    eax, eax
0x1800aa59f  jns     short loc_1800AA5C4
0x1800aa5a1  mov     rcx, [rbp+28h]; this
0x1800aa5a5  mov     r9d, eax; char *
0x1800aa5a8  lea     r8, aOnecoreAdminAp_115; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800aa5af  mov     edx, 0BAh; void *
0x1800aa5b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aa5b9  lea     rcx, [rbp+arg_18]
0x1800aa5bd  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x1800aa5c2  jmp     short loc_1800AA568
0x1800aa5c4  mov     [rbp+arg_0], 0
0x1800aa5cb  xor     eax, eax
0x1800aa5cd  xorps   xmm0, xmm0
0x1800aa5d0  movups  xmmword ptr [rbp+lpString1], xmm0
0x1800aa5d4  mov     [rbp+var_10], eax
0x1800aa5d7  lea     r9, [rbp+arg_0]; struct Common::StringBuffer *
0x1800aa5db  lea     r8, [rbp+lpString1]; unsigned __int16 *
0x1800aa5df  lea     rdx, stru_1801DA4D0; struct IXMLDOMElement *
0x1800aa5e6  mov     rcx, [rbp+arg_18.lpVtbl]; this
0x1800aa5ea  call    ?GetAttributeValueStringFromElement@Xml@Common@@YAJPEAUIXMLDOMElement@@PEBGAEAVStringBuffer@2@PEAH@Z; Common::Xml::GetAttributeValueStringFromElement(IXMLDOMElement *,ushort const *,Common::StringBuffer &,int *)
0x1800aa5ef  mov     ebx, eax
0x1800aa5f1  test    eax, eax
0x1800aa5f3  jns     short loc_1800AA61D
0x1800aa5f5  mov     rcx, [rbp+28h]; this
0x1800aa5f9  mov     r9d, eax; char *
0x1800aa5fc  lea     r8, aOnecoreAdminAp_115; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800aa603  mov     edx, 0BFh; void *
0x1800aa608  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aa60d  mov     rcx, [rbp+lpString1+8]; void *
0x1800aa611  test    rcx, rcx
0x1800aa614  jz      short loc_1800AA5B9
0x1800aa616  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800aa61b  jmp     short loc_1800AA5B9
0x1800aa61d  or      r12d, 0FFFFFFFFh
0x1800aa621  mov     rbx, [rbp+lpString1+8]
0x1800aa625  cmp     [rbp+arg_0], 0
0x1800aa629  jz      short loc_1800AA658
0x1800aa62b  mov     [rsp+60h+bIgnoreCase], 1; int
0x1800aa633  mov     r9d, r12d; cchCount2
0x1800aa636  lea     r8, aReset; "reset"
0x1800aa63d  mov     edx, r12d; cchCount1
0x1800aa640  mov     rcx, rbx; lpString1
0x1800aa643  call    cs:__imp_CompareStringOrdinal
0x1800aa64a  nop     dword ptr [rax+rax+00h]
0x1800aa64f  cmp     eax, 2
0x1800aa652  jnz     short loc_1800AA658
0x1800aa654  or      dword ptr [rdi+60h], 4
0x1800aa658  xor     eax, eax
0x1800aa65a  xorps   xmm0, xmm0
0x1800aa65d  movups  xmmword ptr [rbp+lpString1], xmm0
0x1800aa661  mov     [rbp+var_10], eax
0x1800aa664  lea     r9, [rbp+arg_0]; struct Common::StringBuffer *
0x1800aa668  lea     r8, [rbp+lpString1]; unsigned __int16 *
0x1800aa66c  lea     rdx, stru_1801DA490; struct IXMLDOMElement *
0x1800aa673  mov     rcx, [rbp+arg_18.lpVtbl]; this
0x1800aa677  call    ?GetAttributeValueStringFromElement@Xml@Common@@YAJPEAUIXMLDOMElement@@PEBGAEAVStringBuffer@2@PEAH@Z; Common::Xml::GetAttributeValueStringFromElement(IXMLDOMElement *,ushort const *,Common::StringBuffer &,int *)
0x1800aa67c  mov     esi, eax
0x1800aa67e  test    eax, eax
0x1800aa680  jns     short loc_1800AA6CE
0x1800aa682  mov     rcx, [rbp+28h]; this
0x1800aa686  mov     r9d, eax; char *
0x1800aa689  lea     r8, aOnecoreAdminAp_115; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800aa690  mov     edx, 0C7h; void *
0x1800aa695  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aa69a  mov     rcx, [rbp+lpString1+8]; void *
0x1800aa69e  test    rcx, rcx
0x1800aa6a1  jz      short loc_1800AA6A8
0x1800aa6a3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800aa6a8  test    rbx, rbx
0x1800aa6ab  jz      short loc_1800AA6B5
0x1800aa6ad  mov     rcx, rbx; void *
0x1800aa6b0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800aa6b5  lea     rcx, [rbp+arg_18]
0x1800aa6b9  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x1800aa6be  lea     rcx, [rbp+var_30]
0x1800aa6c2  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x1800aa6c7  mov     ebx, esi
0x1800aa6c9  jmp     loc_1800AA7F8
0x1800aa6ce  mov     rsi, [rbp+lpString1+8]
0x1800aa6d2  cmp     [rbp+arg_0], 0
0x1800aa6d6  jz      short loc_1800AA705
0x1800aa6d8  mov     [rsp+60h+bIgnoreCase], 1; int
0x1800aa6e0  mov     r9d, r12d; cchCount2
0x1800aa6e3  lea     r8, aReset; "reset"
0x1800aa6ea  mov     edx, r12d; cchCount1
0x1800aa6ed  mov     rcx, rsi; lpString1
0x1800aa6f0  call    cs:__imp_CompareStringOrdinal
0x1800aa6f7  nop     dword ptr [rax+rax+00h]
0x1800aa6fc  cmp     eax, 2
0x1800aa6ff  jnz     short loc_1800AA705
0x1800aa701  or      dword ptr [rdi+60h], 1
0x1800aa705  xor     eax, eax
0x1800aa707  xorps   xmm0, xmm0
0x1800aa70a  movups  xmmword ptr [rbp+lpString1], xmm0
0x1800aa70e  mov     [rbp+var_10], eax
0x1800aa711  lea     r9, [rbp+arg_0]; struct Common::StringBuffer *
0x1800aa715  lea     r8, [rbp+lpString1]; unsigned __int16 *
0x1800aa719  lea     rdx, stru_1801DA4B0; struct IXMLDOMElement *
0x1800aa720  mov     rcx, [rbp+arg_18.lpVtbl]; this
0x1800aa724  call    ?GetAttributeValueStringFromElement@Xml@Common@@YAJPEAUIXMLDOMElement@@PEBGAEAVStringBuffer@2@PEAH@Z; Common::Xml::GetAttributeValueStringFromElement(IXMLDOMElement *,ushort const *,Common::StringBuffer &,int *)
0x1800aa729  mov     r14d, eax
0x1800aa72c  test    eax, eax
0x1800aa72e  jns     short loc_1800AA787
0x1800aa730  mov     rcx, [rbp+28h]; this
0x1800aa734  mov     r9d, eax; char *
0x1800aa737  lea     r8, aOnecoreAdminAp_115; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800aa73e  mov     edx, 0CFh; void *
0x1800aa743  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aa748  mov     rcx, [rbp+lpString1+8]; void *
0x1800aa74c  test    rcx, rcx
0x1800aa74f  jz      short loc_1800AA756
0x1800aa751  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800aa756  test    rsi, rsi
0x1800aa759  jz      short loc_1800AA763
0x1800aa75b  mov     rcx, rsi; void *
0x1800aa75e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800aa763  test    rbx, rbx
0x1800aa766  jz      short loc_1800AA770
0x1800aa768  mov     rcx, rbx; void *
0x1800aa76b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800aa770  lea     rcx, [rbp+arg_18]
0x1800aa774  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x1800aa779  lea     rcx, [rbp+var_30]
0x1800aa77d  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x1800aa782  mov     ebx, r14d
0x1800aa785  jmp     short loc_1800AA7F8
0x1800aa787  mov     r14, [rbp+lpString1+8]
0x1800aa78b  cmp     [rbp+arg_0], 0
0x1800aa78f  jz      short loc_1800AA7BD
0x1800aa791  mov     [rsp+60h+bIgnoreCase], 1; bIgnoreCase
0x1800aa799  mov     r9d, r12d; cchCount2
0x1800aa79c  lea     r8, aReset; "reset"
0x1800aa7a3  mov     edx, r12d; cchCount1
0x1800aa7a6  mov     rcx, r14; lpString1
0x1800aa7a9  call    cs:__imp_CompareStringOrdinal
0x1800aa7b0  nop     dword ptr [rax+rax+00h]
0x1800aa7b5  cmp     eax, 2
0x1800aa7b8  jnz     short loc_1800AA7BD
0x1800aa7ba  or      [rdi+60h], eax
0x1800aa7bd  test    r14, r14
0x1800aa7c0  jz      short loc_1800AA7CA
0x1800aa7c2  mov     rcx, r14; void *
0x1800aa7c5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800aa7ca  test    rsi, rsi
0x1800aa7cd  jz      short loc_1800AA7D7
0x1800aa7cf  mov     rcx, rsi; void *
0x1800aa7d2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800aa7d7  test    rbx, rbx
0x1800aa7da  jz      short loc_1800AA7E4
0x1800aa7dc  mov     rcx, rbx; void *
0x1800aa7df  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800aa7e4  lea     rcx, [rbp+arg_18]
0x1800aa7e8  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x1800aa7ed  lea     rcx, [rbp+var_30]
0x1800aa7f1  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x1800aa7f6  xor     ebx, ebx
0x1800aa7f8  lea     rcx, [rbp+var_28]
0x1800aa7fc  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x1800aa801  mov     eax, ebx
0x1800aa803  mov     rbx, [rsp+60h+arg_8]
0x1800aa80b  add     rsp, 60h
0x1800aa80f  pop     r14
0x1800aa811  pop     r12
0x1800aa813  pop     rdi
0x1800aa814  pop     rsi
0x1800aa815  pop     rbp
0x1800aa816  retn
```
