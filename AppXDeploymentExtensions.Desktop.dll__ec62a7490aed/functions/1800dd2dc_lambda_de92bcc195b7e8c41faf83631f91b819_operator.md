# _lambda_de92bcc195b7e8c41faf83631f91b819_::operator()

- ea: `0x1800dd2dc`
- end: `0x1800dd92a`
- name: `_lambda_de92bcc195b7e8c41faf83631f91b819_::operator()`
- size: `1614`
- prototype: ``
- caller_count: `3`
- callee_count: `24`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001e780`
- `0x180038bd0`
- `0x18004a878`

## callees

- `0x180006970`
- `0x180006c98`
- `0x180007540`
- `0x18000b598`
- `0x180011020`
- `0x180012710`
- `0x180012da0`
- `0x180012fc8`
- `0x1800178a0`
- `0x180017ba0`
- `0x18001adb4`
- `0x180022f94`
- `0x180023170`
- `0x18002cb80`
- `0x1800422b4`
- `0x180048614`
- `0x1800571f0`
- `0x180086570`
- `0x180088d80`
- `0x1800af1bc`
- `0x1800da964`
- `0x1800dd2dc`
- `0x1800ddcb4`
- `0x1800ddf68`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800dd6ba`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800dd6ba`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800dd515`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800dd545`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800dd515`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800dd545`

## string_xrefs

- `0x1800dd39e`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x1800dd3ec`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x1800dd4c8`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x1800dd5ae`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x1800dd614`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x1800dd685`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x1800dd741`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x1800dd810`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x1800dd892`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall lambda_de92bcc195b7e8c41faf83631f91b819_::operator()(OSIntegration::Tools::MoCOMHelper **a1)
{
  struct IXMLDOMElement **v2; // r9
  int XMLElementFromQuery; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // r9
  __int64 v7; // rdx
  OSIntegration::Tools::MoCOMHelper *v8; // rax
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r9
  const struct std::nothrow_t *v12; // rdx
  unsigned __int16 *v13; // rcx
  OSIntegration::Tools::MoCOMHelper *v14; // rax
  int AttributeValueStringFromQuery; // eax
  WCHAR *v16; // rcx
  WCHAR *v17; // r14
  OSIntegration::Tools::MoCOMHelper *v18; // rcx
  int AttributeValueBooleanFromQuery; // eax
  OSIntegration::Tools::MoCOMHelper *v20; // rcx
  int AttributeValueStringFromElement; // eax
  unsigned __int16 *v22; // r15
  int v23; // eax
  struct Common::StringBuffer *v24; // r8
  void *v25; // rcx
  const struct std::nothrow_t *v26; // rdx
  int v27; // eax
  __int64 v28; // rdx
  void *v29; // r13
  __int64 v30; // rdi
  OSIntegration::Tools::MoCOMHelper *v31; // rax
  __int64 v32; // rbx
  unsigned int v33; // eax
  const unsigned __int16 *v34; // rax
  const struct std::nothrow_t *v35; // rdx
  unsigned int v37; // eax
  unsigned int v38; // r8d
  int *bIgnoreCase; // [rsp+28h] [rbp-89h]
  int *bIgnoreCasea; // [rsp+28h] [rbp-89h]
  int *bIgnoreCaseb; // [rsp+28h] [rbp-89h]
  int *bIgnoreCasec; // [rsp+28h] [rbp-89h]
  int bIgnoreCased; // [rsp+28h] [rbp-89h]
  struct IXMLDOMElement v44; // [rsp+58h] [rbp-59h] BYREF
  void *v45[2]; // [rsp+60h] [rbp-51h] BYREF
  int v46; // [rsp+70h] [rbp-41h]
  LPCWCH lpString1[2]; // [rsp+78h] [rbp-39h] BYREF
  int v48; // [rsp+88h] [rbp-29h]
  void *v49[2]; // [rsp+90h] [rbp-21h] BYREF
  int v50; // [rsp+A0h] [rbp-11h]
  void *v51[2]; // [rsp+A8h] [rbp-9h] BYREF
  int v52; // [rsp+B8h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+110h] [rbp+5Fh]
  bool v54; // [rsp+118h] [rbp+67h] BYREF
  __int16 v55; // [rsp+11Dh] [rbp+6Ch]
  char v56; // [rsp+11Fh] [rbp+6Eh]
  struct IXMLDOMElement v57; // [rsp+120h] [rbp+6Fh] BYREF
  int v58; // [rsp+128h] [rbp+77h] BYREF
  int v59; // [rsp+130h] [rbp+7Fh] BYREF

  v58 = 0;
  v44.lpVtbl = 0;
  *(_OWORD *)v49 = 0;
  v50 = 0;
  Microsoft::WRL::ComPtr<IXMLDOMElement>::operator=((char *)*a1 + 592, *(_QWORD *)a1[1]);
  Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v44);
  XMLElementFromQuery = Common::Xml::GetXMLElementFromQuery(
                          (OLECHAR *)L"../..",
                          *(const unsigned __int16 **)a1[1],
                          &v44,
                          v2);
  v4 = XMLElementFromQuery;
  if ( XMLElementFromQuery < 0 )
  {
    v5 = 2261;
LABEL_8:
    v6 = (unsigned int)XMLElementFromQuery;
    goto LABEL_9;
  }
  if ( !v44.lpVtbl )
  {
    v4 = -2147024809;
    v6 = 2147942487LL;
    v5 = 2262;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
      (const char *)v6,
      (int)bIgnoreCase);
LABEL_74:
    Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v44);
    return v4;
  }
  v7 = *(_QWORD *)a1[2];
  v8 = *a1;
  if ( v7 )
  {
    Common::StringBuffer::SetValue(
      (OSIntegration::Tools::MoCOMHelper *)((char *)v8 + 24),
      *(const unsigned __int16 **)(v7 + 8),
      *(_DWORD *)v7);
  }
  else
  {
    XMLElementFromQuery = Common::Xml::GetAttributeValueStringFromElement(
                            *(Common::Xml **)a1[1],
                            (struct IXMLDOMElement *)L"Category",
                            (const unsigned __int16 *)v8 + 12,
                            (struct Common::StringBuffer *)&v58,
                            bIgnoreCase);
    v4 = XMLElementFromQuery;
    if ( XMLElementFromQuery < 0 )
    {
      v5 = 2272;
      goto LABEL_8;
    }
  }
  v9 = OSIntegration::Tools::MoCOMHelper::ParseEntryPointElementAttributes(
         *a1,
         *(const struct OSIntegration::Package **)a1[3],
         *(struct IXMLDOMElement **)a1[1]);
  v4 = v9;
  if ( v9 < 0 )
  {
    v10 = 2282;
LABEL_13:
    v11 = (unsigned int)v9;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
      (const char *)v11,
      (int)bIgnoreCase);
LABEL_15:
    v13 = (unsigned __int16 *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    goto LABEL_16;
  }
  if ( *((_DWORD *)*a1 + 3) == 3 && *(_QWORD *)(*(_QWORD *)a1[3] + 432LL) == 12 )
    *((_DWORD *)*a1 + 3) = 6;
  v54 = 0;
  v9 = OSIntegration::Tools::MoCOMHelper::ParseApplication(
         *a1,
         *(const struct OSIntegration::Package **)a1[3],
         (struct IXMLDOMElement *)v44.lpVtbl,
         &v54);
  v4 = v9;
  if ( v9 < 0 )
  {
    v10 = 2291;
    goto LABEL_13;
  }
  if ( !v54 )
  {
    v4 = -2147023728;
    v11 = 2147943568LL;
    v10 = 2293;
    goto LABEL_14;
  }
  v14 = *a1;
  if ( *((_DWORD *)*a1 + 154) == 1 && *((_DWORD *)v14 + 153) != 1 )
    *((_DWORD *)v14 + 154) = 0;
  *(_OWORD *)lpString1 = 0;
  v48 = 0;
  LODWORD(v57.lpVtbl) = 0;
  AttributeValueStringFromQuery = Common::Xml::GetAttributeValueStringFromQuery(
                                    (OLECHAR *)L"@*[local-name()='AppLifecycleBehavior']",
                                    *(const unsigned __int16 **)a1[1],
                                    (const struct IXMLDOMElement *)lpString1,
                                    (struct Common::StringBuffer *)&v57,
                                    bIgnoreCase);
  v4 = AttributeValueStringFromQuery;
  if ( AttributeValueStringFromQuery < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x90B,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
      (const char *)(unsigned int)AttributeValueStringFromQuery,
      (int)bIgnoreCasea);
    v16 = (WCHAR *)lpString1[1];
    if ( !lpString1[1] )
      goto LABEL_15;
LABEL_30:
    operator delete(v16, v12);
    goto LABEL_15;
  }
  v17 = (WCHAR *)lpString1[1];
  if ( LODWORD(v57.lpVtbl) )
  {
    if ( CompareStringOrdinal(lpString1[1], -1, L"unmanaged", -1, 1) == 2 )
    {
      v18 = *a1;
      *((_DWORD *)*a1 + 155) = 0;
    }
    else
    {
      if ( CompareStringOrdinal(v17, -1, L"systemManaged", -1, 1) != 2 )
      {
        v37 = wil::verify_hresult<long>(2147549183LL);
        wil::details::in1diag3::FailFast_Hr(retaddr, (void *)0x919, v38, (const char *)v37, (int)bIgnoreCasea);
      }
      v18 = *a1;
      *((_DWORD *)*a1 + 155) = 1;
    }
    *((_BYTE *)v18 + 624) = 1;
    *(_WORD *)((char *)v18 + 625) = v55;
    *((_BYTE *)v18 + 627) = v56;
  }
  LOBYTE(v57.lpVtbl) = 0;
  v59 = 0;
  AttributeValueBooleanFromQuery = Common::Xml::GetAttributeValueBooleanFromQuery(
                                     (OLECHAR *)L"@*[local-name()='SupportsMultipleInstances']",
                                     *(const unsigned __int16 **)a1[1],
                                     &v57,
                                     (bool *)&v59,
                                     bIgnoreCasea);
  v4 = AttributeValueBooleanFromQuery;
  if ( AttributeValueBooleanFromQuery < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x923,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
      (const char *)(unsigned int)AttributeValueBooleanFromQuery,
      (int)bIgnoreCaseb);
    if ( !v17 )
      goto LABEL_15;
    v16 = v17;
    goto LABEL_30;
  }
  if ( v59 )
  {
    v20 = *a1;
    *((_BYTE *)v20 + 628) = v57.lpVtbl;
    *((_BYTE *)v20 + 629) = 1;
  }
  AttributeValueStringFromElement = Common::Xml::GetAttributeValueStringFromElement(
                                      *(Common::Xml **)a1[1],
                                      (struct IXMLDOMElement *)&stru_1801CEC78,
                                      (const unsigned __int16 *)v49,
                                      (struct Common::StringBuffer *)&v58,
                                      bIgnoreCaseb);
  v4 = AttributeValueStringFromElement;
  if ( AttributeValueStringFromElement < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x92E,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
      (const char *)(unsigned int)AttributeValueStringFromElement,
      (int)bIgnoreCasec);
    if ( v17 )
      operator delete(v17, v12);
    v13 = (unsigned __int16 *)v49[1];
LABEL_16:
    if ( !v13 )
      goto LABEL_74;
LABEL_73:
    operator delete(v13, v12);
    goto LABEL_74;
  }
  v22 = (unsigned __int16 *)v49[1];
  if ( v58 )
  {
    if ( !IsBackgroundExtensionContract(*((const unsigned __int16 **)*a1 + 4)) )
    {
      *(_OWORD *)v45 = 0;
      v46 = 0;
      v23 = Common::Xml::GetAttributeValueStringFromElement(
              (Common::Xml *)v44.lpVtbl,
              (struct IXMLDOMElement *)&stru_1801CEC78,
              (const unsigned __int16 *)v45,
              (struct Common::StringBuffer *)&v58,
              bIgnoreCasec);
      v4 = v23;
      if ( v23 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x93F,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
          (const char *)(unsigned int)v23,
          (int)bIgnoreCasec);
        v25 = v45[1];
        if ( !v45[1] )
        {
LABEL_69:
          if ( v17 )
            operator delete(v17, v12);
          if ( !v22 )
            goto LABEL_74;
          v13 = v22;
          goto LABEL_73;
        }
LABEL_50:
        operator delete(v25, v12);
        goto LABEL_69;
      }
      if ( !v58 || (unsigned int)_o__wcsicmp(v22, v45[1]) )
      {
        *(_OWORD *)v51 = 0;
        v52 = 0;
        v57.lpVtbl = 0;
        OSIntegration::Tools::FormatMessageInternal(0x80080204, (Common::StringBuffer *)v51, v24);
        OSIntegration::Package::GetXmlLineInformation(
          *(OSIntegration::Package **)a1[3],
          *(const struct IXMLDOMNode **)a1[1],
          0,
          (struct APPX_XML_LINE_INFORMATION *)&v57);
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x95F,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
          (const char *)0x80080204LL,
          (int)bIgnoreCasec);
        v29 = v51[1];
        if ( (byte_180245606 & 0x10) != 0 )
        {
          v30 = *((_QWORD *)*a1 + 4);
          v31 = a1[3];
          v32 = *(_QWORD *)(*(_QWORD *)v31 + 224LL);
          v33 = (unsigned int)RemovePIIfromFilePath(*(const unsigned __int16 **)(*(_QWORD *)v31 + 272LL));
          McTemplateU0zqqdzzz_EventWriteTransfer(
            HIDWORD(v57.lpVtbl),
            (unsigned int)&MoCOMParseExtensionResourceGroupError,
            v33,
            v57.lpVtbl,
            SBYTE4(v57.lpVtbl),
            4,
            v32,
            (__int64)v29,
            v30);
        }
        v34 = RemovePIIfromFilePath(*(const unsigned __int16 **)(*(_QWORD *)a1[3] + 272LL));
        v4 = -2146958844;
        bIgnoreCased = (int)v57.lpVtbl;
        details::appxLog<unsigned short const *,unsigned int,unsigned int,long,unsigned short *,unsigned short *,unsigned short *>(
          2148008452LL,
          LODWORD(v57.lpVtbl),
          &MoCOMParseExtensionResourceGroupError,
          v34);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x961,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
          (const char *)0x80080204LL,
          bIgnoreCased);
        if ( v29 )
          operator delete(v29, v12);
        if ( !v45[1] )
          goto LABEL_69;
        v25 = v45[1];
        goto LABEL_50;
      }
      if ( v45[1] )
        operator delete(v45[1], v26);
    }
    v27 = OSIntegration::Tools::AddStringPropertyToContainer((unsigned __int16 *)&stru_1801CEC78, v22);
    v4 = v27;
    if ( v27 < 0 )
    {
      v28 = 2409;
LABEL_68:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v28,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
        (const char *)(unsigned int)v27,
        (int)bIgnoreCasec);
      goto LABEL_69;
    }
  }
  LOBYTE(v57.lpVtbl) = 0;
  v27 = OSIntegration::Tools::MoCOMHelper::ApplicationExtensionSupportsMultipleInstances(
          *a1,
          *(struct IXMLDOMElement **)a1[1],
          (struct IXMLDOMElement *)v44.lpVtbl,
          (bool *)&v57);
  v4 = v27;
  if ( v27 < 0 )
  {
    v28 = 2414;
    goto LABEL_68;
  }
  if ( LOBYTE(v57.lpVtbl) )
  {
    v27 = OSIntegration::Tools::AddDwordPropertyToContainer(L"SupportsMultipleInstances");
    v4 = v27;
    if ( v27 < 0 )
    {
      v28 = 2420;
      goto LABEL_68;
    }
  }
  if ( v17 )
    operator delete(v17, v35);
  if ( v22 )
    operator delete(v22, v35);
  Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v44);
  return 0;
}

```

## disassembly

```asm
0x1800dd2dc  mov     rax, rsp
0x1800dd2df  push    rbp
0x1800dd2e0  push    rbx
0x1800dd2e1  push    rsi
0x1800dd2e2  push    rdi
0x1800dd2e3  push    r13
0x1800dd2e5  push    r14
0x1800dd2e7  push    r15
0x1800dd2e9  lea     rbp, [rax-5Fh]
0x1800dd2ed  sub     rsp, 0D0h
0x1800dd2f4  movaps  xmmword ptr [rax-48h], xmm6
0x1800dd2f8  mov     rsi, rcx
0x1800dd2fb  xor     edi, edi
0x1800dd2fd  mov     [rbp+57h+arg_10], edi
0x1800dd300  mov     [rbp+57h+var_B0.lpVtbl], rdi
0x1800dd304  xorps   xmm6, xmm6
0x1800dd307  movups  xmmword ptr [rbp+57h+var_78], xmm6
0x1800dd30b  mov     [rbp+57h+var_68], edi
0x1800dd30e  mov     rdx, [rcx+8]
0x1800dd312  mov     rcx, [rcx]
0x1800dd315  add     rcx, 250h
0x1800dd31c  mov     rdx, [rdx]
0x1800dd31f  call    ??4?$ComPtr@UIXMLDOMElement@@@WRL@Microsoft@@QEAAAEAV012@PEAUIXMLDOMElement@@@Z; Microsoft::WRL::ComPtr<IXMLDOMElement>::operator=(IXMLDOMElement *)
0x1800dd324  lea     rcx, [rbp+57h+var_B0]
0x1800dd328  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x1800dd32d  mov     rdx, [rsi+8]
0x1800dd331  lea     r8, [rbp+57h+var_B0]; struct IXMLDOMElement *
0x1800dd335  mov     rdx, [rdx]; unsigned __int16 *
0x1800dd338  lea     rcx, asc_1801CEBE8; "../.."
0x1800dd33f  call    ?GetXMLElementFromQuery@Xml@Common@@YAJPEBGPEAUIXMLDOMElement@@PEAPEAU3@@Z; Common::Xml::GetXMLElementFromQuery(ushort const *,IXMLDOMElement *,IXMLDOMElement * *)
0x1800dd344  mov     ebx, eax
0x1800dd346  test    eax, eax
0x1800dd348  jns     short loc_1800DD351
0x1800dd34a  mov     edx, 8D5h
0x1800dd34f  jmp     short loc_1800DD39B
0x1800dd351  cmp     [rbp+57h+var_B0.lpVtbl], rdi
0x1800dd355  jnz     short loc_1800DD366
0x1800dd357  mov     ebx, 80070057h
0x1800dd35c  mov     r9d, ebx
0x1800dd35f  mov     edx, 8D6h
0x1800dd364  jmp     short loc_1800DD39E
0x1800dd366  mov     rax, [rsi+10h]
0x1800dd36a  mov     rdx, [rax]
0x1800dd36d  mov     rax, [rsi]
0x1800dd370  test    rdx, rdx
0x1800dd373  jnz     short loc_1800DD3B4
0x1800dd375  mov     rcx, [rsi+8]
0x1800dd379  lea     r9, [rbp+57h+arg_10]; struct Common::StringBuffer *
0x1800dd37d  lea     r8, [rax+18h]; unsigned __int16 *
0x1800dd381  lea     rdx, ?Category@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; "Category"
0x1800dd388  mov     rcx, [rcx]; this
0x1800dd38b  call    ?GetAttributeValueStringFromElement@Xml@Common@@YAJPEAUIXMLDOMElement@@PEBGAEAVStringBuffer@2@PEAH@Z; Common::Xml::GetAttributeValueStringFromElement(IXMLDOMElement *,ushort const *,Common::StringBuffer &,int *)
0x1800dd390  mov     ebx, eax
0x1800dd392  test    eax, eax
0x1800dd394  jns     short loc_1800DD3C4
0x1800dd396  mov     edx, 8E0h; void *
0x1800dd39b  mov     r9d, eax; char *
0x1800dd39e  lea     r8, aOnecoreAdminAp_108; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800dd3a5  mov     rcx, [rbp+5Fh]; this
0x1800dd3a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dd3ae  nop
0x1800dd3af  jmp     loc_1800DD8BF
0x1800dd3b4  mov     r8d, [rdx]; unsigned int
0x1800dd3b7  mov     rdx, [rdx+8]; unsigned __int16 *
0x1800dd3bb  lea     rcx, [rax+18h]; this
0x1800dd3bf  call    ?SetValue@StringBuffer@Common@@QEAAJPEBGK@Z; Common::StringBuffer::SetValue(ushort const *,ulong)
0x1800dd3c4  mov     r8, [rsi+8]
0x1800dd3c8  mov     rdx, [rsi+18h]
0x1800dd3cc  mov     r8, [r8]; struct IXMLDOMElement *
0x1800dd3cf  mov     rdx, [rdx]; struct OSIntegration::Package *
0x1800dd3d2  mov     rcx, [rsi]; this
0x1800dd3d5  call    ?ParseEntryPointElementAttributes@MoCOMHelper@Tools@OSIntegration@@IEAAJPEBVPackage@3@PEAUIXMLDOMElement@@@Z; OSIntegration::Tools::MoCOMHelper::ParseEntryPointElementAttributes(OSIntegration::Package const *,IXMLDOMElement *)
0x1800dd3da  mov     ebx, eax
0x1800dd3dc  test    eax, eax
0x1800dd3de  jns     short loc_1800DD411
0x1800dd3e0  mov     edx, 8EAh; void *
0x1800dd3e5  mov     r9d, eax; char *
0x1800dd3e8  mov     rcx, [rbp+5Fh]; this
0x1800dd3ec  lea     r8, aOnecoreAdminAp_108; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800dd3f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dd3f8  nop
0x1800dd3f9  psrldq  xmm6, 8
0x1800dd3fe  movq    rcx, xmm6
0x1800dd403  test    rcx, rcx
0x1800dd406  jz      loc_1800DD8BF
0x1800dd40c  jmp     loc_1800DD8B9
0x1800dd411  mov     rdx, [rsi]
0x1800dd414  cmp     dword ptr [rdx+0Ch], 3
0x1800dd418  jnz     short loc_1800DD432
0x1800dd41a  mov     rax, [rsi+18h]
0x1800dd41e  mov     rcx, [rax]
0x1800dd421  cmp     qword ptr [rcx+1B0h], 0Ch
0x1800dd429  jnz     short loc_1800DD432
0x1800dd42b  mov     dword ptr [rdx+0Ch], 6
0x1800dd432  mov     [rbp+57h+arg_0], dil
0x1800dd436  mov     rdx, [rsi+18h]
0x1800dd43a  lea     r9, [rbp+57h+arg_0]; bool *
0x1800dd43e  mov     r8, [rbp+57h+var_B0.lpVtbl]; struct IXMLDOMElement *
0x1800dd442  mov     rdx, [rdx]; struct OSIntegration::Package *
0x1800dd445  mov     rcx, [rsi]; this
0x1800dd448  call    ?ParseApplication@MoCOMHelper@Tools@OSIntegration@@AEAAJPEBVPackage@3@PEAUIXMLDOMElement@@PEA_N@Z; OSIntegration::Tools::MoCOMHelper::ParseApplication(OSIntegration::Package const *,IXMLDOMElement *,bool *)
0x1800dd44d  mov     ebx, eax
0x1800dd44f  test    eax, eax
0x1800dd451  jns     short loc_1800DD45A
0x1800dd453  mov     edx, 8F3h
0x1800dd458  jmp     short loc_1800DD3E5
0x1800dd45a  cmp     [rbp+57h+arg_0], dil
0x1800dd45e  jnz     short loc_1800DD472
0x1800dd460  mov     ebx, 80070490h
0x1800dd465  mov     r9d, ebx
0x1800dd468  mov     edx, 8F5h
0x1800dd46d  jmp     loc_1800DD3E8
0x1800dd472  mov     rax, [rsi]
0x1800dd475  mov     r15d, 1
0x1800dd47b  cmp     [rax+268h], r15d
0x1800dd482  jnz     short loc_1800DD493
0x1800dd484  cmp     [rax+264h], r15d
0x1800dd48b  jz      short loc_1800DD493
0x1800dd48d  mov     [rax+268h], edi
0x1800dd493  xorps   xmm0, xmm0
0x1800dd496  movups  xmmword ptr [rbp+57h+lpString1], xmm0
0x1800dd49a  mov     [rbp+57h+var_80], edi
0x1800dd49d  mov     dword ptr [rbp+57h+arg_8.lpVtbl], edi
0x1800dd4a0  mov     rdx, [rsi+8]
0x1800dd4a4  lea     r9, [rbp+57h+arg_8]; struct Common::StringBuffer *
0x1800dd4a8  lea     r8, [rbp+57h+lpString1]; struct IXMLDOMElement *
0x1800dd4ac  mov     rdx, [rdx]; unsigned __int16 *
0x1800dd4af  lea     rcx, aLocalNameAppli_2; "@*[local-name()='AppLifecycleBehavior']"
0x1800dd4b6  call    ?GetAttributeValueStringFromQuery@Xml@Common@@YAJPEBGPEBUIXMLDOMElement@@AEAVStringBuffer@2@PEAH@Z; Common::Xml::GetAttributeValueStringFromQuery(ushort const *,IXMLDOMElement const *,Common::StringBuffer &,int *)
0x1800dd4bb  mov     ebx, eax
0x1800dd4bd  test    eax, eax
0x1800dd4bf  jns     short loc_1800DD4F1
0x1800dd4c1  mov     rcx, [rbp+5Fh]; this
0x1800dd4c5  mov     r9d, eax; char *
0x1800dd4c8  lea     r8, aOnecoreAdminAp_108; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800dd4cf  mov     edx, 90Bh; void *
0x1800dd4d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dd4d9  nop
0x1800dd4da  mov     rcx, [rbp+57h+lpString1+8]; void *
0x1800dd4de  test    rcx, rcx
0x1800dd4e1  jz      loc_1800DD3F9
0x1800dd4e7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800dd4ec  jmp     loc_1800DD3F9
0x1800dd4f1  mov     r14, [rbp+57h+lpString1+8]
0x1800dd4f5  cmp     dword ptr [rbp+57h+arg_8.lpVtbl], edi
0x1800dd4f8  jz      loc_1800DD57F
0x1800dd4fe  mov     dword ptr [rsp+100h+bIgnoreCase], r15d; bIgnoreCase
0x1800dd503  or      ebx, 0FFFFFFFFh
0x1800dd506  mov     r9d, ebx; cchCount2
0x1800dd509  lea     r8, ?AppLifecycleBehaviorUnmanaged@Value@Packaging@Appx@@3QBGB; "unmanaged"
0x1800dd510  mov     edx, ebx; cchCount1
0x1800dd512  mov     rcx, r14; lpString1
0x1800dd515  call    cs:__imp_CompareStringOrdinal
0x1800dd51c  nop     dword ptr [rax+rax+00h]
0x1800dd521  add     eax, 0FFFFFFFEh
0x1800dd524  jnz     short loc_1800DD531
0x1800dd526  mov     rcx, [rsi]
0x1800dd529  mov     [rcx+26Ch], edi
0x1800dd52f  jmp     short loc_1800DD564
0x1800dd531  mov     dword ptr [rsp+100h+bIgnoreCase], r15d; int
0x1800dd536  mov     r9d, ebx; cchCount2
0x1800dd539  lea     r8, ?AppLifecycleBehaviorSystemManaged@Value@Packaging@Appx@@3QBGB; "systemManaged"
0x1800dd540  mov     edx, ebx; cchCount1
0x1800dd542  mov     rcx, r14; lpString1
0x1800dd545  call    cs:__imp_CompareStringOrdinal
0x1800dd54c  nop     dword ptr [rax+rax+00h]
0x1800dd551  add     eax, 0FFFFFFFEh
0x1800dd554  jnz     loc_1800DD90E
0x1800dd55a  mov     rcx, [rsi]
0x1800dd55d  mov     [rcx+26Ch], r15d
0x1800dd564  mov     [rcx+270h], r15b
0x1800dd56b  movzx   eax, [rbp+57h+arg_5]
0x1800dd56f  mov     [rcx+271h], ax
0x1800dd576  mov     al, [rbp+57h+arg_7]
0x1800dd579  mov     [rcx+273h], al
0x1800dd57f  mov     byte ptr [rbp+57h+arg_8.lpVtbl], dil
0x1800dd583  mov     [rbp+57h+arg_18], edi
0x1800dd586  mov     rdx, [rsi+8]
0x1800dd58a  lea     r9, [rbp+57h+arg_18]; bool *
0x1800dd58e  lea     r8, [rbp+57h+arg_8]; struct IXMLDOMElement *
0x1800dd592  mov     rdx, [rdx]; unsigned __int16 *
0x1800dd595  lea     rcx, strIn; "@*[local-name()='SupportsMultipleInstan"...
0x1800dd59c  call    ?GetAttributeValueBooleanFromQuery@Xml@Common@@YAJPEBGPEAUIXMLDOMElement@@AEA_NPEAH@Z; Common::Xml::GetAttributeValueBooleanFromQuery(ushort const *,IXMLDOMElement *,bool &,int *)
0x1800dd5a1  mov     ebx, eax
0x1800dd5a3  test    eax, eax
0x1800dd5a5  jns     short loc_1800DD5D1
0x1800dd5a7  mov     rcx, [rbp+5Fh]; this
0x1800dd5ab  mov     r9d, eax; char *
0x1800dd5ae  lea     r8, aOnecoreAdminAp_108; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800dd5b5  mov     edx, 923h; void *
0x1800dd5ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dd5bf  nop
0x1800dd5c0  test    r14, r14
0x1800dd5c3  jz      loc_1800DD3F9
0x1800dd5c9  mov     rcx, r14
0x1800dd5cc  jmp     loc_1800DD4E7
0x1800dd5d1  cmp     [rbp+57h+arg_18], edi
0x1800dd5d4  jz      short loc_1800DD5E9
0x1800dd5d6  mov     al, byte ptr [rbp+57h+arg_8.lpVtbl]
0x1800dd5d9  mov     rcx, [rsi]
0x1800dd5dc  mov     [rcx+274h], al
0x1800dd5e2  mov     [rcx+275h], r15b
0x1800dd5e9  mov     rcx, [rsi+8]
0x1800dd5ed  lea     r9, [rbp+57h+arg_10]; struct Common::StringBuffer *
0x1800dd5f1  lea     r8, [rbp+57h+var_78]; unsigned __int16 *
0x1800dd5f5  lea     r13, stru_1801CEC78
0x1800dd5fc  mov     rdx, r13; struct IXMLDOMElement *
0x1800dd5ff  mov     rcx, [rcx]; this
0x1800dd602  call    ?GetAttributeValueStringFromElement@Xml@Common@@YAJPEAUIXMLDOMElement@@PEBGAEAVStringBuffer@2@PEAH@Z; Common::Xml::GetAttributeValueStringFromElement(IXMLDOMElement *,ushort const *,Common::StringBuffer &,int *)
0x1800dd607  mov     ebx, eax
0x1800dd609  test    eax, eax
0x1800dd60b  jns     short loc_1800DD63D
0x1800dd60d  mov     rcx, [rbp+5Fh]; this
0x1800dd611  mov     r9d, eax; char *
0x1800dd614  lea     r8, aOnecoreAdminAp_108; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800dd61b  mov     edx, 92Eh; void *
0x1800dd620  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dd625  nop
0x1800dd626  test    r14, r14
0x1800dd629  jz      short loc_1800DD634
0x1800dd62b  mov     rcx, r14; void *
0x1800dd62e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800dd633  nop
0x1800dd634  mov     rcx, [rbp+57h+var_78+8]
0x1800dd638  jmp     loc_1800DD403
0x1800dd63d  mov     r15, [rbp+57h+var_78+8]
0x1800dd641  cmp     [rbp+57h+arg_10], edi
0x1800dd644  jz      loc_1800DD840
0x1800dd64a  mov     rcx, [rsi]
0x1800dd64d  mov     rcx, [rcx+20h]; unsigned __int16 *
0x1800dd651  call    ?IsBackgroundExtensionContract@@YA_NPEBG@Z; IsBackgroundExtensionContract(ushort const *)
0x1800dd656  test    al, al
0x1800dd658  jnz     short loc_1800DD6D9
0x1800dd65a  xorps   xmm0, xmm0
0x1800dd65d  movups  xmmword ptr [rbp+57h+var_A8], xmm0
0x1800dd661  mov     [rbp+57h+var_98], edi
0x1800dd664  lea     r9, [rbp+57h+arg_10]; struct Common::StringBuffer *
0x1800dd668  lea     r8, [rbp+57h+var_A8]; unsigned __int16 *
0x1800dd66c  mov     rdx, r13; struct IXMLDOMElement *
0x1800dd66f  mov     rcx, [rbp+57h+var_B0.lpVtbl]; this
0x1800dd673  call    ?GetAttributeValueStringFromElement@Xml@Common@@YAJPEAUIXMLDOMElement@@PEBGAEAVStringBuffer@2@PEAH@Z; Common::Xml::GetAttributeValueStringFromElement(IXMLDOMElement *,ushort const *,Common::StringBuffer &,int *)
0x1800dd678  mov     ebx, eax
0x1800dd67a  test    eax, eax
0x1800dd67c  jns     short loc_1800DD6AE
0x1800dd67e  mov     rcx, [rbp+5Fh]; this
0x1800dd682  mov     r9d, eax; char *
0x1800dd685  lea     r8, aOnecoreAdminAp_108; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800dd68c  mov     edx, 93Fh; void *
0x1800dd691  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dd696  nop
0x1800dd697  mov     rcx, [rbp+57h+var_A8+8]; void *
0x1800dd69b  test    rcx, rcx
0x1800dd69e  jz      loc_1800DD8A3
0x1800dd6a4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800dd6a9  jmp     loc_1800DD8A3
0x1800dd6ae  cmp     [rbp+57h+arg_10], edi
0x1800dd6b1  jz      short loc_1800DD702
0x1800dd6b3  mov     rdx, [rbp+57h+var_A8+8]
0x1800dd6b7  mov     rcx, r15
0x1800dd6ba  call    cs:__imp__o__wcsicmp
0x1800dd6c1  nop     dword ptr [rax+rax+00h]
0x1800dd6c6  test    eax, eax
0x1800dd6c8  jnz     short loc_1800DD702
0x1800dd6ca  cmp     [rbp+57h+var_A8+8], rdi
0x1800dd6ce  jz      short loc_1800DD6D9
0x1800dd6d0  mov     rcx, [rbp+57h+var_A8+8]; void *
0x1800dd6d4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800dd6d9  mov     r8, [rsi]
0x1800dd6dc  add     r8, 1E8h
0x1800dd6e3  mov     rdx, r15
0x1800dd6e6  mov     rcx, r13
0x1800dd6e9  call    ?AddStringPropertyToContainer@Tools@OSIntegration@@YAJPEBG0AEAV?$Array@V?$Property@VStringBuffer@Common@@@Internal@Tools@OSIntegration@@V?$ContainerOperations@V?$Property@VStringBuffer@Common@@@Internal@Tools@OSIntegration@@V1234@@Common@@VNoKey@6@V?$ContainerOperations@VNoKey@Common@@V?$Property@VStringBuffer@Common@@@Internal@Tools@OSIntegration@@@6@V?$ArrayOperations@V?$Property@VStringBuffer@Common@@@Internal@Tools@OSIntegration@@VNoKey@Common@@@6@@Common@@@Z; OSIntegration::Tools::AddStringPropertyToContainer(ushort const *,ushort const *,Common::Array<OSIntegration::Tools::Internal::Property<Common::StringBuffer>,Common::ContainerOperations<OSIntegration::Tools::Internal::Property<Common::StringBuffer>,OSIntegration::Tools::Internal::Property<Common::StringBuffer>>,Common::NoKey,Common::ContainerOperations<Common::NoKey,OSIntegration::Tools::Internal::Property<Common::StringBuffer>>,Common::ArrayOperations<OSIntegration::Tools::Internal::Property<Common::StringBuffer>,Common::NoKey>> &)
0x1800dd6ee  mov     ebx, eax
0x1800dd6f0  test    eax, eax
0x1800dd6f2  jns     loc_1800DD840
0x1800dd6f8  mov     edx, 969h
0x1800dd6fd  jmp     loc_1800DD88F
0x1800dd702  xorps   xmm0, xmm0
0x1800dd705  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x1800dd709  mov     [rbp+57h+var_50], edi
0x1800dd70c  mov     [rbp+57h+arg_8.lpVtbl], rdi
0x1800dd710  lea     rdx, [rbp+57h+var_60]; this
0x1800dd714  mov     ebx, 80080204h
0x1800dd719  mov     ecx, ebx; dwMessageId
0x1800dd71b  call    ?FormatMessageInternal@Tools@OSIntegration@@YAJJPEAVStringBuffer@Common@@@Z; OSIntegration::Tools::FormatMessageInternal(long,Common::StringBuffer *)
0x1800dd720  mov     rdx, [rsi+8]
0x1800dd724  mov     rcx, [rsi+18h]
0x1800dd728  lea     r9, [rbp+57h+arg_8]; struct APPX_XML_LINE_INFORMATION *
0x1800dd72c  xor     r8d, r8d; unsigned __int16 *
0x1800dd72f  mov     rdx, [rdx]; struct IXMLDOMNode *
0x1800dd732  mov     rcx, [rcx]; this
0x1800dd735  call    ?GetXmlLineInformation@Package@OSIntegration@@QEBAJPEBUIXMLDOMNode@@PEBGPEAUAPPX_XML_LINE_INFORMATION@@@Z; OSIntegration::Package::GetXmlLineInformation(IXMLDOMNode const *,ushort const *,APPX_XML_LINE_INFORMATION *)
0x1800dd73a  mov     rcx, [rbp+5Fh]; this
0x1800dd73e  mov     r9d, ebx; char *
0x1800dd741  lea     r8, aOnecoreAdminAp_108; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800dd748  mov     edx, 95Fh; void *
0x1800dd74d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800dd752  mov     r13, [rbp+57h+var_60+8]
0x1800dd756  test    cs:byte_180245606, 10h
0x1800dd75d  jz      short loc_1800DD7B1
  ... truncated ...
```
