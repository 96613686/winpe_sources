# Appx::Packaging::FileExemptionBuilderBase::InitializeXmlDomFromStream(IStream *,IXMLDOMNode * *)

- ea: `0x1800fe1dc`
- end: `0x1800fe51a`
- name: `?InitializeXmlDomFromStream@FileExemptionBuilderBase@Packaging@Appx@@CAJPEAUIStream@@PEAPEAUIXMLDOMNode@@@Z`
- size: `830`
- prototype: `__int64 __fastcall(struct IStream *this, struct IXMLDOMNode **)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800fdee4`
- `0x1800fe050`

## callees

- `0x180005eb8`
- `0x180009eb8`
- `0x1800133fc`
- `0x180094a38`
- `0x180094a70`
- `0x180094abc`
- `0x1800fbab0`
- `0x1800fdb70`
- `0x1800fe1dc`
- `0x1800fec2c`
- `0x180106010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800fe2c9`
- `OLEAUT32!__imp_SysAllocString` at `0x1800fe2c9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fe2fc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fe366`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fe3df`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fe3f7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fe4df`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fe2fc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fe366`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fe3df`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fe3f7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fe4df`
- `OLEAUT32!__imp_VariantInit` at `0x1800fe2b9`
- `OLEAUT32!__imp_VariantInit` at `0x1800fe2b9`

## string_xrefs

- `0x1800fe238`: `TempXml`
- `0x1800fe24d`: `(FileSystemHelper::CreateTempFileFromStream(xmlStream, TempXmlFilePrefix, XmlExtension, tempXmlDump))`
- `0x1800fe20a`: `SetStreamPosition(xmlStream, 0)`
- `0x1800fe42d`: `pXMLErr->get_reason(&bstrErr)`
- `0x1800fe3c5`: `localXmlDom->get_parseError(&pXMLErr)`
- `0x1800fe350`: `localXmlDom->load(varFileName, &success)`
- `0x1800fe283`: `CreateXmlDocument(&localXmlDom)`
- `0x1800fe4a3`: `localXmlDom.As(&localNode)`
- `0x1800fe43a`: `Failed to load DOM from given xml Stream %S\n`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::FileExemptionBuilderBase::InitializeXmlDomFromStream(
        struct IStream *this,
        struct IXMLDOMNode **a2)
{
  int v4; // eax
  bool v5; // cl
  unsigned int v6; // ebx
  int v7; // eax
  bool v8; // cl
  int v9; // eax
  bool v10; // cl
  BSTR v11; // rax
  OLECHAR *v12; // rbx
  struct IXMLDOMDocument *v13; // rdi
  struct IXMLDOMDocumentVtbl *lpVtbl; // rax
  HRESULT (__stdcall *load)(IXMLDOMDocument *, VARIANT, VARIANT_BOOL *); // rax
  int v16; // eax
  bool v17; // cl
  unsigned int v18; // esi
  HRESULT (__stdcall *get_parseError)(IXMLDOMDocument *, IXMLDOMParseError **); // rsi
  bool v20; // cl
  int v21; // edi
  const char *v22; // r8
  HRESULT (__stdcall *QueryInterface)(IXMLDOMDocument *, const IID *const, void **); // rsi
  int v24; // eax
  bool v25; // cl
  __int64 v27; // [rsp+20h] [rbp-60h] BYREF
  struct IXMLDOMNode *v28; // [rsp+28h] [rbp-58h] BYREF
  BSTR bstrString; // [rsp+30h] [rbp-50h] BYREF
  OLECHAR *psz; // [rsp+38h] [rbp-48h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-40h] BYREF
  __int128 v32; // [rsp+60h] [rbp-20h] BYREF
  IRecordInfo *pRecInfo; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]
  __int16 v35; // [rsp+B0h] [rbp+30h] BYREF
  struct IXMLDOMDocument *v36; // [rsp+B8h] [rbp+38h] BYREF

  v4 = Appx::Packaging::SetStreamPosition(this, 0);
  v6 = v4;
  if ( v4 >= 0 )
  {
    psz = 0;
    v7 = Appx::Packaging::FileSystemHelper::CreateTempFileFromStream(this, L"TempXml", L"xml", &psz);
    v6 = v7;
    if ( v7 < 0 )
    {
      Appx::Packaging::SharedWithTools::Logging::WriteFailure(
        v8,
        v7,
        "(FileSystemHelper::CreateTempFileFromStream(xmlStream, TempXmlFilePrefix, XmlExtension, tempXmlDump))",
        0);
LABEL_24:
      Appx::Packaging::DeleteFileOnFree::~DeleteFileOnFree((Appx::Packaging::DeleteFileOnFree *)&psz);
      return v6;
    }
    v36 = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v36);
    v9 = Appx::Packaging::FileExemptionBuilderBase::CreateXmlDocument(&v36);
    v6 = v9;
    if ( v9 < 0 )
    {
      Appx::Packaging::SharedWithTools::Logging::WriteFailure(v10, v9, "CreateXmlDocument(&localXmlDom)", 0);
      Appx::Packaging::SharedWithTools::Logging::WriteLastErrorInfo();
LABEL_7:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v36);
      goto LABEL_24;
    }
    v35 = 0;
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    v11 = SysAllocString(psz);
    v12 = v11;
    if ( !v11 )
    {
      v6 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x523,
        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\fileexemptionbuilderbase.cpp",
        (const char *)0x8007000ELL,
        v27);
      SysFreeString(0);
      goto LABEL_7;
    }
    v13 = v36;
    pvarg.llVal = (LONGLONG)v11;
    pvarg.vt = 8;
    lpVtbl = v36->lpVtbl;
    pRecInfo = pvarg.pRecInfo;
    load = lpVtbl->load;
    v32 = *(_OWORD *)&pvarg.vt;
    v16 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, __int128 *, __int16 *))load)(v36, &v32, &v35);
    v18 = v16;
    if ( v16 < 0 )
    {
      Appx::Packaging::SharedWithTools::Logging::WriteFailure(v17, v16, "localXmlDom->load(varFileName, &success)", 0);
      Appx::Packaging::SharedWithTools::Logging::WriteLastErrorInfo();
      SysFreeString(v12);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v36);
      v6 = v18;
      goto LABEL_24;
    }
    if ( v35 == -1 )
    {
      v28 = 0;
      QueryInterface = v13->lpVtbl->QueryInterface;
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v28);
      v24 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, GUID *, struct IXMLDOMNode **))QueryInterface)(
              v13,
              &GUID_2933bf80_7b36_11d2_b20e_00c04f983e60,
              &v28);
      v21 = v24;
      if ( v24 >= 0 )
      {
        *a2 = v28;
        v28 = 0;
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v28);
        SysFreeString(v12);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v36);
        v6 = 0;
        goto LABEL_24;
      }
      Appx::Packaging::SharedWithTools::Logging::WriteFailure(v25, v24, "localXmlDom.As(&localNode)", 0);
      Appx::Packaging::SharedWithTools::Logging::WriteLastErrorInfo();
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v28);
      goto LABEL_17;
    }
    v27 = 0;
    bstrString = 0;
    get_parseError = v13->lpVtbl->get_parseError;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v27);
    v21 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, __int64 *))get_parseError)(v13, &v27);
    if ( v21 >= 0 )
    {
      v21 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v27 + 72LL))(v27, &bstrString);
      if ( v21 >= 0 )
      {
        Appx::Packaging::SharedWithTools::Logging::WriteError(
          1,
          L"Failed to load DOM from given xml Stream %S\n",
          bstrString);
        v21 = -2147418113;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x532,
          (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\fileexemptionbuilderbase.cpp",
          (const char *)0x8000FFFFLL,
          v27);
        goto LABEL_16;
      }
      v22 = "pXMLErr->get_reason(&bstrErr)";
    }
    else
    {
      v22 = "localXmlDom->get_parseError(&pXMLErr)";
    }
    Appx::Packaging::SharedWithTools::Logging::WriteFailure(v20, v21, v22, 0);
    Appx::Packaging::SharedWithTools::Logging::WriteLastErrorInfo();
LABEL_16:
    SysFreeString(bstrString);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v27);
LABEL_17:
    SysFreeString(v12);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v36);
    v6 = v21;
    goto LABEL_24;
  }
  Appx::Packaging::SharedWithTools::Logging::WriteFailure(v5, v4, "SetStreamPosition(xmlStream, 0)", 0);
  Appx::Packaging::SharedWithTools::Logging::WriteLastErrorInfo();
  return v6;
}

```

## disassembly

```asm
0x1800fe1dc  mov     [rsp-18h+arg_0], rbx
0x1800fe1e1  mov     [rsp-18h+arg_8], rsi
0x1800fe1e6  push    rbp
0x1800fe1e7  push    rdi
0x1800fe1e8  push    r14
0x1800fe1ea  mov     rbp, rsp
0x1800fe1ed  sub     rsp, 80h
0x1800fe1f4  mov     r14, rdx
0x1800fe1f7  mov     rdi, rcx
0x1800fe1fa  xor     edx, edx; struct IStream *
0x1800fe1fc  call    ?SetStreamPosition@Packaging@Appx@@YAJPEAUIStream@@_K@Z; Appx::Packaging::SetStreamPosition(IStream *,unsigned __int64)
0x1800fe201  mov     ebx, eax
0x1800fe203  test    eax, eax
0x1800fe205  jns     short loc_1800FE222
0x1800fe207  xor     r9d, r9d; unsigned __int16 *
0x1800fe20a  lea     r8, aSetstreamposit; "SetStreamPosition(xmlStream, 0)"
0x1800fe211  mov     edx, eax; int
0x1800fe213  call    ?WriteFailure@Logging@SharedWithTools@Packaging@Appx@@SAX_NJPEBDPEBG@Z; Appx::Packaging::SharedWithTools::Logging::WriteFailure(bool,long,char const *,ushort const *)
0x1800fe218  call    ?WriteLastErrorInfo@Logging@SharedWithTools@Packaging@Appx@@SAXXZ; Appx::Packaging::SharedWithTools::Logging::WriteLastErrorInfo(void)
0x1800fe21d  jmp     loc_1800FE4FF
0x1800fe222  lea     r9, [rbp+psz]; unsigned __int16 **
0x1800fe226  mov     [rbp+psz], 0
0x1800fe22e  lea     r8, aXml; "xml"
0x1800fe235  mov     rcx, rdi; this
0x1800fe238  lea     rdx, aTempxml; "TempXml"
0x1800fe23f  call    ?CreateTempFileFromStream@FileSystemHelper@Packaging@Appx@@SAJPEAUIStream@@PEBG1AEAVDeleteFileOnFree@23@@Z; Appx::Packaging::FileSystemHelper::CreateTempFileFromStream(IStream *,ushort const *,ushort const *,Appx::Packaging::DeleteFileOnFree &)
0x1800fe244  mov     ebx, eax
0x1800fe246  test    eax, eax
0x1800fe248  jns     short loc_1800FE260
0x1800fe24a  xor     r9d, r9d; unsigned __int16 *
0x1800fe24d  lea     r8, aFilesystemhelp_2; "(FileSystemHelper::CreateTempFileFromSt"...
0x1800fe254  mov     edx, eax; int
0x1800fe256  call    ?WriteFailure@Logging@SharedWithTools@Packaging@Appx@@SAX_NJPEBDPEBG@Z; Appx::Packaging::SharedWithTools::Logging::WriteFailure(bool,long,char const *,ushort const *)
0x1800fe25b  jmp     loc_1800FE4F6
0x1800fe260  lea     rcx, [rbp+arg_18]
0x1800fe264  mov     [rbp+arg_18], 0
0x1800fe26c  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800fe271  lea     rcx, [rbp+arg_18]; struct IXMLDOMDocument **
0x1800fe275  call    ?CreateXmlDocument@FileExemptionBuilderBase@Packaging@Appx@@CAJPEAPEAUIXMLDOMDocument@@@Z; Appx::Packaging::FileExemptionBuilderBase::CreateXmlDocument(IXMLDOMDocument * *)
0x1800fe27a  mov     ebx, eax
0x1800fe27c  test    eax, eax
0x1800fe27e  jns     short loc_1800FE2A4
0x1800fe280  xor     r9d, r9d; unsigned __int16 *
0x1800fe283  lea     r8, aCreatexmldocum; "CreateXmlDocument(&localXmlDom)"
0x1800fe28a  mov     edx, eax; int
0x1800fe28c  call    ?WriteFailure@Logging@SharedWithTools@Packaging@Appx@@SAX_NJPEBDPEBG@Z; Appx::Packaging::SharedWithTools::Logging::WriteFailure(bool,long,char const *,ushort const *)
0x1800fe291  call    ?WriteLastErrorInfo@Logging@SharedWithTools@Packaging@Appx@@SAXXZ; Appx::Packaging::SharedWithTools::Logging::WriteLastErrorInfo(void)
0x1800fe296  lea     rcx, [rbp+arg_18]
0x1800fe29a  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800fe29f  jmp     loc_1800FE4F6
0x1800fe2a4  xor     eax, eax
0x1800fe2a6  lea     rcx, [rbp+pvarg]; pvarg
0x1800fe2aa  xorps   xmm0, xmm0
0x1800fe2ad  mov     [rbp+arg_10], ax
0x1800fe2b1  movups  xmmword ptr [rbp+pvarg], xmm0
0x1800fe2b5  mov     qword ptr [rbp+pvarg+10h], rax
0x1800fe2b9  call    cs:__imp_VariantInit
0x1800fe2c0  nop     dword ptr [rax+rax+00h]
0x1800fe2c5  mov     rcx, [rbp+psz]; psz
0x1800fe2c9  call    cs:__imp_SysAllocString
0x1800fe2d0  nop     dword ptr [rax+rax+00h]
0x1800fe2d5  mov     rbx, rax
0x1800fe2d8  test    rax, rax
0x1800fe2db  jnz     short loc_1800FE30A
0x1800fe2dd  mov     rcx, [rbp+18h]; this
0x1800fe2e1  lea     r8, aOnecorePrintsc_108; "onecore\\printscan\\appxpackaging\\lib"...
0x1800fe2e8  mov     ebx, 8007000Eh
0x1800fe2ed  mov     edx, 523h; void *
0x1800fe2f2  mov     r9d, ebx; char *
0x1800fe2f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fe2fa  xor     ecx, ecx; bstrString
0x1800fe2fc  call    cs:__imp_SysFreeString
0x1800fe303  nop     dword ptr [rax+rax+00h]
0x1800fe308  jmp     short loc_1800FE296
0x1800fe30a  mov     rdi, [rbp+arg_18]
0x1800fe30e  lea     r8, [rbp+arg_10]
0x1800fe312  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x1800fe317  lea     rdx, [rbp+var_20]
0x1800fe31b  mov     qword ptr [rbp+pvarg+8], rbx
0x1800fe31f  mov     eax, 8
0x1800fe324  mov     word ptr [rbp+pvarg], ax
0x1800fe328  mov     rcx, rdi
0x1800fe32b  mov     rax, [rdi]
0x1800fe32e  movups  xmm0, xmmword ptr [rbp+pvarg]
0x1800fe332  movsd   [rbp+var_10], xmm1
0x1800fe337  mov     rax, [rax+1D0h]
0x1800fe33e  movaps  [rbp+var_20], xmm0
0x1800fe342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe347  mov     esi, eax
0x1800fe349  test    eax, eax
0x1800fe34b  jns     short loc_1800FE382
0x1800fe34d  xor     r9d, r9d; unsigned __int16 *
0x1800fe350  lea     r8, aLocalxmldomLoa; "localXmlDom->load(varFileName, &success"...
0x1800fe357  mov     edx, eax; int
0x1800fe359  call    ?WriteFailure@Logging@SharedWithTools@Packaging@Appx@@SAX_NJPEBDPEBG@Z; Appx::Packaging::SharedWithTools::Logging::WriteFailure(bool,long,char const *,ushort const *)
0x1800fe35e  call    ?WriteLastErrorInfo@Logging@SharedWithTools@Packaging@Appx@@SAXXZ; Appx::Packaging::SharedWithTools::Logging::WriteLastErrorInfo(void)
0x1800fe363  mov     rcx, rbx; bstrString
0x1800fe366  call    cs:__imp_SysFreeString
0x1800fe36d  nop     dword ptr [rax+rax+00h]
0x1800fe372  lea     rcx, [rbp+arg_18]
0x1800fe376  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800fe37b  mov     ebx, esi
0x1800fe37d  jmp     loc_1800FE4F6
0x1800fe382  cmp     [rbp+arg_10], 0FFFFh
0x1800fe387  jz      loc_1800FE46D
0x1800fe38d  mov     [rbp+var_60], 0
0x1800fe395  lea     rcx, [rbp+var_60]
0x1800fe399  mov     [rbp+bstrString], 0
0x1800fe3a1  mov     rax, [rdi]
0x1800fe3a4  mov     rsi, [rax+1E0h]
0x1800fe3ab  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800fe3b0  lea     rdx, [rbp+var_60]
0x1800fe3b4  mov     rcx, rdi
0x1800fe3b7  mov     rax, rsi
0x1800fe3ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe3bf  mov     edi, eax
0x1800fe3c1  test    eax, eax
0x1800fe3c3  jns     short loc_1800FE413
0x1800fe3c5  lea     r8, aLocalxmldomGet; "localXmlDom->get_parseError(&pXMLErr)"
0x1800fe3cc  xor     r9d, r9d; unsigned __int16 *
0x1800fe3cf  mov     edx, edi; int
0x1800fe3d1  call    ?WriteFailure@Logging@SharedWithTools@Packaging@Appx@@SAX_NJPEBDPEBG@Z; Appx::Packaging::SharedWithTools::Logging::WriteFailure(bool,long,char const *,ushort const *)
0x1800fe3d6  call    ?WriteLastErrorInfo@Logging@SharedWithTools@Packaging@Appx@@SAXXZ; Appx::Packaging::SharedWithTools::Logging::WriteLastErrorInfo(void)
0x1800fe3db  mov     rcx, [rbp+bstrString]; bstrString
0x1800fe3df  call    cs:__imp_SysFreeString
0x1800fe3e6  nop     dword ptr [rax+rax+00h]
0x1800fe3eb  lea     rcx, [rbp+var_60]
0x1800fe3ef  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800fe3f4  mov     rcx, rbx; bstrString
0x1800fe3f7  call    cs:__imp_SysFreeString
0x1800fe3fe  nop     dword ptr [rax+rax+00h]
0x1800fe403  lea     rcx, [rbp+arg_18]
0x1800fe407  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800fe40c  mov     ebx, edi
0x1800fe40e  jmp     loc_1800FE4F6
0x1800fe413  mov     rcx, [rbp+var_60]
0x1800fe417  lea     rdx, [rbp+bstrString]
0x1800fe41b  mov     rax, [rcx]
0x1800fe41e  mov     rax, [rax+48h]
0x1800fe422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe427  mov     edi, eax
0x1800fe429  test    eax, eax
0x1800fe42b  jns     short loc_1800FE436
0x1800fe42d  lea     r8, aPxmlerrGetReas; "pXMLErr->get_reason(&bstrErr)"
0x1800fe434  jmp     short loc_1800FE3CC
0x1800fe436  mov     r8, [rbp+bstrString]
0x1800fe43a  lea     rdx, aFailedToLoadDo; "Failed to load DOM from given xml Strea"...
0x1800fe441  mov     ecx, 1; bool
0x1800fe446  call    ?WriteError@Logging@SharedWithTools@Packaging@Appx@@SAX_NPEBGZZ; Appx::Packaging::SharedWithTools::Logging::WriteError(bool,ushort const *,...)
0x1800fe44b  mov     rcx, [rbp+18h]; this
0x1800fe44f  lea     r8, aOnecorePrintsc_108; "onecore\\printscan\\appxpackaging\\lib"...
0x1800fe456  mov     edi, 8000FFFFh
0x1800fe45b  mov     edx, 532h; void *
0x1800fe460  mov     r9d, edi; char *
0x1800fe463  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fe468  jmp     loc_1800FE3DB
0x1800fe46d  mov     [rbp+var_58], 0
0x1800fe475  lea     rcx, [rbp+var_58]
0x1800fe479  mov     rax, [rdi]
0x1800fe47c  mov     rsi, [rax]
0x1800fe47f  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800fe484  lea     r8, [rbp+var_58]
0x1800fe488  mov     rcx, rdi
0x1800fe48b  lea     rdx, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60
0x1800fe492  mov     rax, rsi
0x1800fe495  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe49a  mov     edi, eax
0x1800fe49c  test    eax, eax
0x1800fe49e  jns     short loc_1800FE4C4
0x1800fe4a0  xor     r9d, r9d; unsigned __int16 *
0x1800fe4a3  lea     r8, aLocalxmldomAsL; "localXmlDom.As(&localNode)"
0x1800fe4aa  mov     edx, eax; int
0x1800fe4ac  call    ?WriteFailure@Logging@SharedWithTools@Packaging@Appx@@SAX_NJPEBDPEBG@Z; Appx::Packaging::SharedWithTools::Logging::WriteFailure(bool,long,char const *,ushort const *)
0x1800fe4b1  call    ?WriteLastErrorInfo@Logging@SharedWithTools@Packaging@Appx@@SAXXZ; Appx::Packaging::SharedWithTools::Logging::WriteLastErrorInfo(void)
0x1800fe4b6  lea     rcx, [rbp+var_58]
0x1800fe4ba  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800fe4bf  jmp     loc_1800FE3F4
0x1800fe4c4  mov     rax, [rbp+var_58]
0x1800fe4c8  lea     rcx, [rbp+var_58]
0x1800fe4cc  mov     [r14], rax
0x1800fe4cf  mov     [rbp+var_58], 0
0x1800fe4d7  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800fe4dc  mov     rcx, rbx; bstrString
0x1800fe4df  call    cs:__imp_SysFreeString
0x1800fe4e6  nop     dword ptr [rax+rax+00h]
0x1800fe4eb  lea     rcx, [rbp+arg_18]
0x1800fe4ef  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800fe4f4  xor     ebx, ebx
0x1800fe4f6  lea     rcx, [rbp+psz]; this
0x1800fe4fa  call    ??1DeleteFileOnFree@Packaging@Appx@@QEAA@XZ; Appx::Packaging::DeleteFileOnFree::~DeleteFileOnFree(void)
0x1800fe4ff  lea     r11, [rsp+80h+var_s0]
0x1800fe507  mov     eax, ebx
0x1800fe509  mov     rbx, [r11+20h]
0x1800fe50d  mov     rsi, [r11+28h]
0x1800fe511  mov     rsp, r11
0x1800fe514  pop     r14
0x1800fe516  pop     rdi
0x1800fe517  pop     rbp
0x1800fe518  retn
```
