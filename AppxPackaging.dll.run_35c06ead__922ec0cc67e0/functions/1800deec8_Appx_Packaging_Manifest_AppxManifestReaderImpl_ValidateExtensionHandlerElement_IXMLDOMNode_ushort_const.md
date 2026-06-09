# Appx::Packaging::Manifest::AppxManifestReaderImpl::ValidateExtensionHandlerElement(IXMLDOMNode *,ushort const *)

- ea: `0x1800deec8`
- end: `0x1800df304`
- name: `?ValidateExtensionHandlerElement@AppxManifestReaderImpl@Manifest@Packaging@Appx@@AEAAJPEAUIXMLDOMNode@@PEBG@Z`
- size: `1084`
- prototype: `__int64 __fastcall(Appx::Packaging::Manifest::AppxManifestReaderImpl *__hidden this, struct IXMLDOMNode *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800d757c`

## callees

- `0x1800029e4`
- `0x180005eb8`
- `0x180010f40`
- `0x180011a70`
- `0x1800133fc`
- `0x18001b270`
- `0x180028dd0`
- `0x180035ba8`
- `0x18003a4a0`
- `0x18003c7c8`
- `0x1800538c8`
- `0x18006bee8`
- `0x18006bf44`
- `0x180074678`
- `0x1800deec8`
- `0x180106010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800df099`
- `OLEAUT32!__imp_SysFreeString` at `0x1800df0c0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800df1bd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800df277`
- `OLEAUT32!__imp_SysFreeString` at `0x1800df2aa`
- `OLEAUT32!__imp_SysFreeString` at `0x1800df099`
- `OLEAUT32!__imp_SysFreeString` at `0x1800df0c0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800df1bd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800df277`
- `OLEAUT32!__imp_SysFreeString` at `0x1800df2aa`

## string_xrefs

- `0x1800def26`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`
- `0x1800def79`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`
- `0x1800df04b`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`
- `0x1800df06e`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`
- `0x1800df11c`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`
- `0x1800df25f`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`
- `0x1800df292`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`
- `0x1800df2bc`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`
- `0x1800df17f`: `Clsid`
- `0x1800df1e5`: `Clsid`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Manifest::AppxManifestReaderImpl::ValidateExtensionHandlerElement(
        Appx::Packaging::Manifest::AppxManifestReaderImpl *this,
        struct IXMLDOMNode *a2,
        const unsigned __int16 *a3,
        struct Common::AutoBStr *a4)
{
  int v7; // eax
  OLECHAR *v8; // rbx
  unsigned int v9; // edi
  int NodesList; // eax
  int v12; // ebx
  int v13; // [rsp+20h] [rbp-40h]
  struct IStream *v14; // [rsp+30h] [rbp-30h] BYREF
  int v15; // [rsp+38h] [rbp-28h] BYREF
  BSTR v16; // [rsp+40h] [rbp-20h] BYREF
  struct IXMLDOMNode *v17; // [rsp+48h] [rbp-18h] BYREF
  BSTR bstrString[2]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  unsigned int v20; // [rsp+A0h] [rbp+40h]
  unsigned int v21; // [rsp+B8h] [rbp+58h]

  v21 = 0;
  v20 = 0;
  if ( !*((_BYTE *)this + 225) )
  {
    bstrString[0] = 0;
    v7 = Appx::Packaging::BuildXPath(
           (Appx::Packaging *)&qword_1801136B0,
           (const struct Appx::Packaging::XPathComponent *)7,
           bstrString,
           a4);
    v8 = bstrString[0];
    v9 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D16,
        (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreader.cpp",
        (const char *)(unsigned int)v7,
        v13);
LABEL_7:
      SysFreeString(v8);
      return v9;
    }
    v16 = 0;
    LODWORD(v14) = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v16);
    NodesList = Appx::Packaging::GetNodesList((char *)this + 128, v8, 0, &v16);
    v9 = NodesList;
    if ( NodesList < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D1A,
        (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreader.cpp",
        (const char *)(unsigned int)NodesList,
        (int)&v14);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v16);
      goto LABEL_7;
    }
    *((_BYTE *)this + 225) = 1;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v16);
    SysFreeString(v8);
  }
  bstrString[0] = 0;
  v15 = 0;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(bstrString);
  v17 = a2;
  Microsoft::WRL::ComPtr<IXMLDOMNodeList>::InternalAddRef(&v17);
  v12 = Appx::Packaging::GetNodesList(&v17, a3, 0, bstrString);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v17);
  if ( v12 >= 0 )
    v12 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D2F,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreader.cpp",
      (const char *)(unsigned int)v12,
      (int)&v15);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(bstrString);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800deec8  mov     [rsp-38h+arg_8], rbx
0x1800deecd  push    rbp
0x1800deece  push    rsi
0x1800deecf  push    rdi
0x1800deed0  push    r12
0x1800deed2  push    r13
0x1800deed4  push    r14
0x1800deed6  push    r15
0x1800deed8  mov     rbp, rsp
0x1800deedb  sub     rsp, 60h
0x1800deedf  xor     r15d, r15d
0x1800deee2  mov     r12, r8
0x1800deee5  mov     r13, rdx
0x1800deee8  mov     r14, rcx
0x1800deeeb  mov     [rbp+arg_18], r15d
0x1800deeef  mov     [rbp+arg_0], r15d
0x1800deef3  cmp     [rcx+0E1h], r15b
0x1800deefa  jnz     loc_1800DF0CF
0x1800def00  lea     r8, [rbp+bstrString]; unsigned int
0x1800def04  mov     [rbp+bstrString], r15
0x1800def08  lea     edx, [r15+7]; struct Appx::Packaging::XPathComponent *
0x1800def0c  lea     rcx, qword_1801136B0; this
0x1800def13  call    ?BuildXPath@Packaging@Appx@@YAJPEBUXPathComponent@12@IAEAVAutoBStr@Common@@@Z; Appx::Packaging::BuildXPath(Appx::Packaging::XPathComponent const *,uint,Common::AutoBStr &)
0x1800def18  mov     rbx, [rbp+bstrString]
0x1800def1c  mov     edi, eax
0x1800def1e  test    eax, eax
0x1800def20  jns     short loc_1800DEF3F
0x1800def22  mov     rcx, [rbp+38h]; this
0x1800def26  lea     r8, aOnecorePrintsc_127; "onecore\\printscan\\appxpackaging\\mani"...
0x1800def2d  mov     r9d, eax; char *
0x1800def30  mov     edx, 1D16h; void *
0x1800def35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800def3a  jmp     loc_1800DF096
0x1800def3f  lea     rcx, [rbp+var_20]
0x1800def43  mov     [rbp+var_20], r15
0x1800def47  mov     dword ptr [rbp+var_30], r15d
0x1800def4b  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800def50  lea     rax, [rbp+var_30]
0x1800def54  xor     r8d, r8d
0x1800def57  lea     rcx, [r14+80h]
0x1800def5e  mov     [rsp+60h+var_40], rax; int
0x1800def63  lea     r9, [rbp+var_20]
0x1800def67  mov     rdx, rbx
0x1800def6a  call    ?GetNodesList@Packaging@Appx@@YAJAEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEAGJPEAPEAUIXMLDOMNodeList@@PEAJ@Z; Appx::Packaging::GetNodesList(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort *,long,IXMLDOMNodeList * *,long *)
0x1800def6f  mov     edi, eax
0x1800def71  test    eax, eax
0x1800def73  jns     short loc_1800DEF9B
0x1800def75  mov     rcx, [rbp+38h]; this
0x1800def79  lea     r8, aOnecorePrintsc_127; "onecore\\printscan\\appxpackaging\\mani"...
0x1800def80  mov     r9d, eax; char *
0x1800def83  mov     edx, 1D1Ah; void *
0x1800def88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800def8d  lea     rcx, [rbp+var_20]
0x1800def91  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800def96  jmp     loc_1800DF096
0x1800def9b  mov     rdi, [rbp+var_20]
0x1800def9f  cmp     r15d, dword ptr [rbp+var_30]
0x1800defa3  jge     loc_1800DF0AC
0x1800defa9  mov     [rbp+bstrString], 0
0x1800defb1  lea     rcx, [rbp+bstrString]
0x1800defb5  mov     rax, [rdi]
0x1800defb8  mov     rsi, [rax+38h]
0x1800defbc  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800defc1  lea     r8, [rbp+bstrString]
0x1800defc5  mov     edx, r15d
0x1800defc8  mov     rcx, rdi
0x1800defcb  mov     rax, rsi
0x1800defce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800defd3  mov     esi, eax
0x1800defd5  test    eax, eax
0x1800defd7  js      loc_1800DF06A
0x1800defdd  xor     edx, edx
0x1800defdf  mov     [rbp+var_18], 0
0x1800defe7  lea     rcx, [rbp+var_18]
0x1800defeb  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800deff0  lea     r9, [rbp+var_18]
0x1800deff4  xor     r8d, r8d
0x1800deff7  lea     rdx, ?Id@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; "Id"
0x1800deffe  lea     rcx, [rbp+bstrString]
0x1800df002  call    ?GetAttributeValue@Packaging@Appx@@YAJAEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEBGJPEAPEAG@Z; Appx::Packaging::GetAttributeValue(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort const *,long,ushort * *)
0x1800df007  mov     esi, eax
0x1800df009  test    eax, eax
0x1800df00b  js      short loc_1800DF047
0x1800df00d  mov     rdx, [rbp+var_18]
0x1800df011  test    rdx, rdx
0x1800df014  jz      short loc_1800DF025
0x1800df016  lea     rcx, [r14+120h]
0x1800df01d  mov     r8, rdx
0x1800df020  call    ?Insert@?$GenericMap@PEBGPEBG@Common@@QEAAJPEBG0@Z; Common::GenericMap<ushort const *,ushort const *>::Insert(ushort const *,ushort const *)
0x1800df025  lea     rcx, [rbp+var_18]
0x1800df029  mov     [rbp+var_18], 0
0x1800df031  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800df036  lea     rcx, [rbp+bstrString]
0x1800df03a  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800df03f  inc     r15d
0x1800df042  jmp     loc_1800DEF9F
0x1800df047  mov     rcx, [rbp+38h]; this
0x1800df04b  lea     r8, aOnecorePrintsc_127; "onecore\\printscan\\appxpackaging\\mani"...
0x1800df052  mov     r9d, esi; char *
0x1800df055  mov     edx, 1D22h; void *
0x1800df05a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800df05f  lea     rcx, [rbp+var_18]
0x1800df063  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800df068  jmp     short loc_1800DF082
0x1800df06a  mov     rcx, [rbp+38h]; this
0x1800df06e  lea     r8, aOnecorePrintsc_127; "onecore\\printscan\\appxpackaging\\mani"...
0x1800df075  mov     r9d, esi; char *
0x1800df078  mov     edx, 1D1Fh; void *
0x1800df07d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800df082  lea     rcx, [rbp+bstrString]
0x1800df086  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800df08b  lea     rcx, [rbp+var_20]
0x1800df08f  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800df094  mov     edi, esi
0x1800df096  mov     rcx, rbx; bstrString
0x1800df099  call    cs:__imp_SysFreeString
0x1800df0a0  nop     dword ptr [rax+rax+00h]
0x1800df0a5  mov     eax, edi
0x1800df0a7  jmp     loc_1800DF2EB
0x1800df0ac  lea     rcx, [rbp+var_20]
0x1800df0b0  mov     byte ptr [r14+0E1h], 1
0x1800df0b8  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800df0bd  mov     rcx, rbx; bstrString
0x1800df0c0  call    cs:__imp_SysFreeString
0x1800df0c7  nop     dword ptr [rax+rax+00h]
0x1800df0cc  xor     r15d, r15d
0x1800df0cf  lea     rcx, [rbp+bstrString]
0x1800df0d3  mov     [rbp+bstrString], r15
0x1800df0d7  mov     [rbp+var_28], r15d
0x1800df0db  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800df0e0  lea     rcx, [rbp+var_18]
0x1800df0e4  mov     [rbp+var_18], r13
0x1800df0e8  call    ?InternalAddRef@?$ComPtr@UIXMLDOMNodeList@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IXMLDOMNodeList>::InternalAddRef(void)
0x1800df0ed  lea     rax, [rbp+var_28]
0x1800df0f1  xor     r8d, r8d
0x1800df0f4  lea     r9, [rbp+bstrString]
0x1800df0f8  mov     [rsp+60h+var_40], rax; int
0x1800df0fd  mov     rdx, r12
0x1800df100  lea     rcx, [rbp+var_18]
0x1800df104  call    ?GetNodesList@Packaging@Appx@@YAJAEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEBGJPEAPEAUIXMLDOMNodeList@@PEAJ@Z; Appx::Packaging::GetNodesList(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort const *,long,IXMLDOMNodeList * *,long *)
0x1800df109  lea     rcx, [rbp+var_18]
0x1800df10d  mov     ebx, eax
0x1800df10f  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800df114  test    ebx, ebx
0x1800df116  jns     short loc_1800DF135
0x1800df118  mov     rcx, [rbp+38h]; this
0x1800df11c  lea     r8, aOnecorePrintsc_127; "onecore\\printscan\\appxpackaging\\mani"...
0x1800df123  mov     r9d, ebx; char *
0x1800df126  mov     edx, 1D2Fh; void *
0x1800df12b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800df130  jmp     loc_1800DF2E0
0x1800df135  mov     rbx, [rbp+bstrString]
0x1800df139  mov     esi, r15d
0x1800df13c  cmp     esi, [rbp+var_28]
0x1800df13f  jge     loc_1800DF2DD
0x1800df145  mov     [rbp+var_30], r15
0x1800df149  lea     rcx, [rbp+var_30]
0x1800df14d  mov     rax, [rbx]
0x1800df150  mov     rdi, [rax+38h]
0x1800df154  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800df159  lea     r8, [rbp+var_30]
0x1800df15d  mov     edx, esi
0x1800df15f  mov     rcx, rbx
0x1800df162  mov     rax, rdi
0x1800df165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df16a  mov     edi, eax
0x1800df16c  test    eax, eax
0x1800df16e  js      loc_1800DF2B8
0x1800df174  lea     r9, [rbp+var_20]
0x1800df178  mov     [rbp+var_20], r15
0x1800df17c  xor     r8d, r8d
0x1800df17f  lea     rdx, ?Clsid@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; "Clsid"
0x1800df186  lea     rcx, [rbp+var_30]
0x1800df18a  call    ?GetAttributeValue@Packaging@Appx@@YAJAEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEBGJPEAPEAG@Z; Appx::Packaging::GetAttributeValue(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort const *,long,ushort * *)
0x1800df18f  mov     edi, eax
0x1800df191  test    eax, eax
0x1800df193  js      loc_1800DF28E
0x1800df199  mov     rax, [rbp+var_20]
0x1800df19d  test    rax, rax
0x1800df1a0  jz      short loc_1800DF1BA
0x1800df1a2  lea     rcx, [r14+120h]
0x1800df1a9  mov     rdx, rax
0x1800df1ac  call    ?Find@?$GenericMap@PEBGPEAUIAppxFile@@@Common@@QEAAPEAUIAppxFile@@PEBG@Z; Common::GenericMap<ushort const *,IAppxFile *>::Find(ushort const *)
0x1800df1b1  test    rax, rax
0x1800df1b4  jz      short loc_1800DF1D9
0x1800df1b6  mov     rax, [rbp+var_20]
0x1800df1ba  mov     rcx, rax; bstrString
0x1800df1bd  call    cs:__imp_SysFreeString
0x1800df1c4  nop     dword ptr [rax+rax+00h]
0x1800df1c9  lea     rcx, [rbp+var_30]
0x1800df1cd  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800df1d2  inc     esi
0x1800df1d4  jmp     loc_1800DF13C
0x1800df1d9  mov     rdx, [rbp+var_30]; struct IStream *
0x1800df1dd  lea     rax, [rbp+arg_0]
0x1800df1e1  mov     rcx, [r14+68h]; this
0x1800df1e5  lea     r9, ?Clsid@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; "Clsid"
0x1800df1ec  mov     [rsp+60h+var_38], rax; unsigned int *
0x1800df1f1  xor     r8d, r8d; struct IXMLDOMNode *
0x1800df1f4  lea     rax, [rbp+arg_18]
0x1800df1f8  mov     [rsp+60h+var_40], rax; unsigned __int16 *
0x1800df1fd  call    ?GetXmlLineInformation@XmlLineInformation@Packaging@Appx@@YAJPEAUIStream@@PEAUIXMLDOMNode@@PEBG2PEAI3@Z; Appx::Packaging::XmlLineInformation::GetXmlLineInformation(IStream *,IXMLDOMNode *,ushort const *,ushort const *,uint *,uint *)
0x1800df202  test    byte ptr cs:Microsoft_Windows_AppxPackagingOMEnableBits, 1
0x1800df209  mov     ebx, 80080204h
0x1800df20e  jz      short loc_1800DF233
0x1800df210  mov     rax, [rbp+var_20]
0x1800df214  lea     rdx, EVENT_MANIFEST_EXTENSIONHANDLER_CLSID_MUST_MATCH_SURROGATESERVER_CLASS_ID
0x1800df21b  mov     r9d, [rbp+arg_18]
0x1800df21f  mov     r8d, ebx
0x1800df222  mov     [rsp+60h+var_38], rax
0x1800df227  mov     eax, [rbp+arg_0]
0x1800df22a  mov     dword ptr [rsp+60h+var_40], eax
0x1800df22e  call    McTemplateU0dqqz_EventWriteTransfer
0x1800df233  mov     rax, [rbp+var_20]
0x1800df237  lea     rcx, EVENT_MANIFEST_EXTENSIONHANDLER_CLSID_MUST_MATCH_SURROGATESERVER_CLASS_ID; struct _EVENT_DESCRIPTOR *
0x1800df23e  mov     r9d, [rbp+arg_18]; unsigned int
0x1800df242  mov     r8d, ebx; int
0x1800df245  mov     [rsp+60h+var_38], rax; unsigned __int16 *
0x1800df24a  mov     edx, 0B00003EDh; unsigned int
0x1800df24f  mov     eax, [rbp+arg_0]
0x1800df252  mov     dword ptr [rsp+60h+var_40], eax; int
0x1800df256  call    ?AppxPackagingLog@@YAJAEBU_EVENT_DESCRIPTOR@@KJIIPEBG@Z; AppxPackagingLog(_EVENT_DESCRIPTOR const &,ulong,long,uint,uint,ushort const *)
0x1800df25b  mov     rcx, [rbp+38h]; this
0x1800df25f  lea     r8, aOnecorePrintsc_127; "onecore\\printscan\\appxpackaging\\mani"...
0x1800df266  mov     r9d, ebx; char *
0x1800df269  mov     edx, 1D3Ch; void *
0x1800df26e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800df273  mov     rcx, [rbp+var_20]; bstrString
0x1800df277  call    cs:__imp_SysFreeString
0x1800df27e  nop     dword ptr [rax+rax+00h]
0x1800df283  lea     rcx, [rbp+var_30]
0x1800df287  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800df28c  jmp     short loc_1800DF2E0
0x1800df28e  mov     rcx, [rbp+38h]; this
0x1800df292  lea     r8, aOnecorePrintsc_127; "onecore\\printscan\\appxpackaging\\mani"...
0x1800df299  mov     r9d, edi; char *
0x1800df29c  mov     edx, 1D37h; void *
0x1800df2a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800df2a6  mov     rcx, [rbp+var_20]; bstrString
0x1800df2aa  call    cs:__imp_SysFreeString
0x1800df2b1  nop     dword ptr [rax+rax+00h]
0x1800df2b6  jmp     short loc_1800DF2D0
0x1800df2b8  mov     rcx, [rbp+38h]; this
0x1800df2bc  lea     r8, aOnecorePrintsc_127; "onecore\\printscan\\appxpackaging\\mani"...
0x1800df2c3  mov     r9d, edi; char *
0x1800df2c6  mov     edx, 1D34h; void *
0x1800df2cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800df2d0  lea     rcx, [rbp+var_30]
0x1800df2d4  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800df2d9  mov     ebx, edi
0x1800df2db  jmp     short loc_1800DF2E0
0x1800df2dd  mov     ebx, r15d
0x1800df2e0  lea     rcx, [rbp+bstrString]
0x1800df2e4  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800df2e9  mov     eax, ebx
0x1800df2eb  mov     rbx, [rsp+60h+arg_8]
0x1800df2f3  add     rsp, 60h
0x1800df2f7  pop     r15
0x1800df2f9  pop     r14
0x1800df2fb  pop     r13
0x1800df2fd  pop     r12
0x1800df2ff  pop     rdi
0x1800df300  pop     rsi
0x1800df301  pop     rbp
0x1800df302  retn
```
