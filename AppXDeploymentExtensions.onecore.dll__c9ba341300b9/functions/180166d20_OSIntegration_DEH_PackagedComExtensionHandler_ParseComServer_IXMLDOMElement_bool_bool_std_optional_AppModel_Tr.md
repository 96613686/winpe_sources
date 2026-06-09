# OSIntegration::DEH::PackagedComExtensionHandler::ParseComServer(IXMLDOMElement *,bool,bool,std::optional<AppModel::TrustLevel>,std::optional<AppModel::RuntimeBehavior>,std::optional<AppModel::BnoIsolation>)

- ea: `0x180166d20`
- end: `0x180167297`
- name: `?ParseComServer@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@_N1V?$optional@W4TrustLevel@AppModel@@@std@@V?$optional@W4RuntimeBehavior@AppModel@@@6@V?$optional@W4BnoIsolation@AppModel@@@6@@Z`
- size: `1399`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180168c58`

## callees

- `0x18000b3bc`
- `0x18003f7e0`
- `0x1800550f4`
- `0x18007d350`
- `0x180098ed0`
- `0x18009aff4`
- `0x18013ced4`
- `0x18013d6f8`
- `0x180166d20`
- `0x1801686ac`
- `0x180169474`
- `0x180169c50`
- `0x18016a600`
- `0x18016b224`
- `0x18016bf0c`
- `0x18016c4e4`
- `0x18016cf84`
- `0x1802086d0`
- `0x180211010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1801671b5`
- `OLEAUT32!__imp_SysFreeString` at `0x180167231`
- `OLEAUT32!__imp_SysFreeString` at `0x1801671b5`
- `OLEAUT32!__imp_SysFreeString` at `0x180167231`

## string_xrefs

- `0x180166db1`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x180166e14`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x180166ec2`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x180167206`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x180167254`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x180166eaf`: `APPX_E_INVALID_MANIFEST`
- `0x18016701a`: `ServiceServer`
- `0x180166d79`: `root->get_childNodes(&comServerNodes)`
- `0x180166db8`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseComServer`
- `0x180166e0d`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseComServer`
- `0x180166ebb`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseComServer`
- `0x18016720d`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseComServer`
- `0x18016724d`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseComServer`
- `0x180166da5`: `comServerNodes->get_length(&listLength)`
- `0x180167241`: `comServerNodes->get_item(nodeIndex, &node)`
- `0x1801671fa`: `node.As(&comServerElement)`
- `0x1801671e8`: `comServerElement->get_baseName(bstrNodeName.AddressOf())`
- `0x180166fb2`: `ParseExeServer(comServerElement.Get(), hasRegistryCompatibility, hasMachineScope, extensionTrustLevel, extensionRuntimeBehavior, extensionBnoIsolation)`
- `0x180167006`: `ParseSurrogateServer(comServerElement.Get(), hasRegistryCompatibility, hasMachineScope, extensionTrustLevel, extensionRuntimeBehavior, extensionBnoIsolation)`
- `0x18016705a`: `ParseServiceServer(comServerElement.Get(), hasRegistryCompatibility, hasMachineScope, extensionTrustLevel, extensionRuntimeBehavior, extensionBnoIsolation)`
- `0x18016709f`: `ParseTreatAsClass(comServerElement.Get(), hasRegistryCompatibility, hasMachineScope)`
- `0x1801670e4`: `ParseProgId(comServerElement.Get(), hasRegistryCompatibility, hasMachineScope)`
- `0x180167129`: `ParseInProcessServer(comServerElement.Get(), hasRegistryCompatibility, hasMachineScope)`
- `0x18016716a`: `ParseInProcessHandler(comServerElement.Get(), hasRegistryCompatibility, hasMachineScope)`
- `0x1801671d6`: `ParseManagedInProcessServer(comServerElement.Get(), hasRegistryCompatibility, hasMachineScope)`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall OSIntegration::DEH::PackagedComExtensionHandler::ParseComServer(
        OSIntegration::Package **this,
        struct IXMLDOMNode *a2,
        bool a3,
        char a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  HRESULT (__stdcall *get_childNodes)(IXMLDOMNode *, IXMLDOMNodeList **); // rbx
  int v11; // eax
  unsigned int v12; // ebx
  const char *v13; // rax
  __int64 v14; // rdx
  int v15; // eax
  int v16; // eax
  OSIntegration::Package *v17; // rcx
  __int64 v18; // rbx
  unsigned int v19; // eax
  const unsigned __int16 *v20; // rax
  __int64 v21; // rdx
  int v22; // ecx
  __int64 v23; // rdi
  __int64 v24; // rsi
  __int64 v25; // r14
  __int64 v26; // r15
  __int64 (__fastcall *v27)(__int64, _QWORD, _QWORD); // rbx
  int v28; // eax
  int v29; // eax
  int v30; // eax
  wchar_t *v31; // rbx
  int v32; // eax
  const char *v33; // rax
  __int64 v34; // rdx
  int v35; // eax
  int v36; // eax
  int v37; // eax
  int v38; // eax
  int v39; // eax
  int v40; // eax
  int v41; // eax
  char *v43; // [rsp+20h] [rbp-50h]
  char *v44; // [rsp+28h] [rbp-48h]
  char *v45; // [rsp+28h] [rbp-48h]
  char *v46; // [rsp+28h] [rbp-48h]
  int v47; // [rsp+30h] [rbp-40h]
  int v48; // [rsp+40h] [rbp-30h] BYREF
  struct IXMLDOMElement *v49; // [rsp+48h] [rbp-28h] BYREF
  __int64 (__fastcall ***v50)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-20h] BYREF
  wchar_t *String2; // [rsp+58h] [rbp-18h] BYREF
  _QWORD v52[2]; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+A8h] [rbp+38h]
  __int64 v54; // [rsp+B8h] [rbp+48h] BYREF
  bool v55; // [rsp+C0h] [rbp+50h]

  v55 = a3;
  v52[0] = 0;
  v48 = 0;
  get_childNodes = a2->lpVtbl->get_childNodes;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v52);
  v11 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, _QWORD *))get_childNodes)(a2, v52);
  v12 = v11;
  if ( v11 < 0 )
  {
    LODWORD(v44) = v11;
    v13 = "root->get_childNodes(&comServerNodes)";
    v14 = 321;
LABEL_5:
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
      "OSIntegration::DEH::PackagedComExtensionHandler::ParseComServer",
      v13,
      v44,
      v47);
    goto LABEL_46;
  }
  v15 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)v52[0] + 64LL))(v52[0], &v48);
  v12 = v15;
  if ( v15 < 0 )
  {
    LODWORD(v44) = v15;
    v13 = "comServerNodes->get_length(&listLength)";
    v14 = 322;
    goto LABEL_5;
  }
  v16 = v48;
  if ( v48 )
  {
    v22 = 0;
    v23 = a7;
    v24 = a6;
    v25 = a5;
    while ( 1 )
    {
      LODWORD(v54) = v22;
      if ( v22 >= v16 )
        break;
      v50 = 0;
      v26 = v52[0];
      v27 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v52[0] + 56LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
      v28 = v27(v26, (unsigned int)v54, &v50);
      v12 = v28;
      if ( v28 < 0 )
      {
        LODWORD(v44) = v28;
        wil::details::in1diag5::Return_Hr(
          retaddr,
          (void *)0x15A,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
          "OSIntegration::DEH::PackagedComExtensionHandler::ParseComServer",
          "comServerNodes->get_item(nodeIndex, &node)",
          v44,
          v47);
        goto LABEL_44;
      }
      String2 = 0;
      v49 = 0;
      v29 = Microsoft::WRL::ComPtr<IXMLDOMNode>::As<IXMLDOMElement>(&v50, (__int64 *)&v49);
      v12 = v29;
      if ( v29 < 0 )
      {
        LODWORD(v44) = v29;
        v33 = "node.As(&comServerElement)";
        v34 = 351;
LABEL_42:
        wil::details::in1diag5::Return_Hr(
          retaddr,
          (void *)v34,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
          "OSIntegration::DEH::PackagedComExtensionHandler::ParseComServer",
          v33,
          v44,
          v47);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
        SysFreeString(String2);
LABEL_44:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
        goto LABEL_46;
      }
      v30 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, wchar_t **))v49->lpVtbl->get_baseName)(v49, &String2);
      v12 = v30;
      if ( v30 < 0 )
      {
        LODWORD(v44) = v30;
        v33 = "comServerElement->get_baseName(bstrNodeName.AddressOf())";
        v34 = 353;
        goto LABEL_42;
      }
      v31 = String2;
      if ( !wcscmp_0(L"ExeServer", String2) )
      {
        v32 = OSIntegration::DEH::PackagedComExtensionHandler::ParseExeServer(
                (OSIntegration::DEH::PackagedComExtensionHandler *)this,
                v49,
                v55,
                a4,
                v25,
                v24,
                v23);
        v12 = v32;
        if ( v32 < 0 )
        {
          LODWORD(v44) = v32;
          v33 = "ParseExeServer(comServerElement.Get(), hasRegistryCompatibility, hasMachineScope, extensionTrustLevel, e"
                "xtensionRuntimeBehavior, extensionBnoIsolation)";
          v34 = 358;
          goto LABEL_42;
        }
      }
      else if ( !wcscmp_0(L"SurrogateServer", v31) )
      {
        v35 = OSIntegration::DEH::PackagedComExtensionHandler::ParseSurrogateServer(
                (OSIntegration::DEH::PackagedComExtensionHandler *)this,
                v49,
                v55,
                a4,
                v25,
                v24,
                v23);
        v12 = v35;
        if ( v35 < 0 )
        {
          LODWORD(v44) = v35;
          v33 = "ParseSurrogateServer(comServerElement.Get(), hasRegistryCompatibility, hasMachineScope, extensionTrustLe"
                "vel, extensionRuntimeBehavior, extensionBnoIsolation)";
          v34 = 363;
          goto LABEL_42;
        }
      }
      else if ( !wcscmp_0(L"ServiceServer", v31) )
      {
        v36 = OSIntegration::DEH::PackagedComExtensionHandler::ParseServiceServer(
                (OSIntegration::DEH::PackagedComExtensionHandler *)this,
                v49,
                v55,
                a4,
                v25,
                v24,
                v23);
        v12 = v36;
        if ( v36 < 0 )
        {
          LODWORD(v44) = v36;
          v33 = "ParseServiceServer(comServerElement.Get(), hasRegistryCompatibility, hasMachineScope, extensionTrustLeve"
                "l, extensionRuntimeBehavior, extensionBnoIsolation)";
          v34 = 368;
          goto LABEL_42;
        }
      }
      else if ( !wcscmp_0(L"TreatAsClass", v31) )
      {
        v37 = OSIntegration::DEH::PackagedComExtensionHandler::ParseTreatAsClass(this, v49, v55, a4);
        v12 = v37;
        if ( v37 < 0 )
        {
          LODWORD(v44) = v37;
          v33 = "ParseTreatAsClass(comServerElement.Get(), hasRegistryCompatibility, hasMachineScope)";
          v34 = 373;
          goto LABEL_42;
        }
      }
      else if ( !wcscmp_0(L"ProgId", v31) )
      {
        v38 = OSIntegration::DEH::PackagedComExtensionHandler::ParseProgId(
                (OSIntegration::DEH::PackagedComExtensionHandler *)this,
                v49,
                v55,
                a4);
        v12 = v38;
        if ( v38 < 0 )
        {
          LODWORD(v44) = v38;
          v33 = "ParseProgId(comServerElement.Get(), hasRegistryCompatibility, hasMachineScope)";
          v34 = 377;
          goto LABEL_42;
        }
      }
      else if ( !wcscmp_0(L"InProcessServer", v31) )
      {
        v39 = OSIntegration::DEH::PackagedComExtensionHandler::ParseInProcessServer(
                (OSIntegration::DEH::PackagedComExtensionHandler *)this,
                v49,
                v55,
                a4);
        v12 = v39;
        if ( v39 < 0 )
        {
          LODWORD(v44) = v39;
          v33 = "ParseInProcessServer(comServerElement.Get(), hasRegistryCompatibility, hasMachineScope)";
          v34 = 382;
          goto LABEL_42;
        }
      }
      else if ( !wcscmp_0(L"InProcessHandler", v31) )
      {
        v40 = OSIntegration::DEH::PackagedComExtensionHandler::ParseInProcessHandler(
                (OSIntegration::DEH::PackagedComExtensionHandler *)this,
                v49,
                v55,
                a4);
        v12 = v40;
        if ( v40 < 0 )
        {
          LODWORD(v44) = v40;
          v33 = "ParseInProcessHandler(comServerElement.Get(), hasRegistryCompatibility, hasMachineScope)";
          v34 = 387;
          goto LABEL_42;
        }
      }
      else if ( !wcscmp_0(L"ManagedInProcessServer", v31) )
      {
        v41 = OSIntegration::DEH::PackagedComExtensionHandler::ParseManagedInProcessServer(
                (OSIntegration::DEH::PackagedComExtensionHandler *)this,
                v49,
                v55,
                a4);
        v12 = v41;
        if ( v41 < 0 )
        {
          LODWORD(v44) = v41;
          v33 = "ParseManagedInProcessServer(comServerElement.Get(), hasRegistryCompatibility, hasMachineScope)";
          v34 = 392;
          goto LABEL_42;
        }
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
      SysFreeString(String2);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
      v22 = v54 + 1;
      v16 = v48;
    }
    v12 = 0;
  }
  else
  {
    v54 = 0;
    OSIntegration::Package::GetXmlLineInformation(this[5], a2, 0, (struct APPX_XML_LINE_INFORMATION *)&v54);
    LODWORD(v44) = -2146958844;
    wil::details::in1diag5::_Log_Hr(
      retaddr,
      (void *)0x152,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
      "OSIntegration::DEH::PackagedComExtensionHandler::ParseComServer",
      "((HRESULT)0x80080204L)",
      v44,
      v47);
    if ( (byte_1802E21CA & 4) != 0 )
    {
      v17 = this[5];
      v18 = *((_QWORD *)v17 + 28);
      v19 = (unsigned int)RemovePIIfromFilePath(*((const unsigned __int16 **)v17 + 34));
      McTemplateU0zqqdz_EventWriteTransfer(
        HIDWORD(v54),
        (unsigned int)PackagedComInvalidComServer,
        v19,
        v54,
        SBYTE4(v54),
        4,
        v18);
    }
    v20 = RemovePIIfromFilePath(*((const unsigned __int16 **)this[5] + 34));
    LODWORD(v45) = HIDWORD(v54);
    LODWORD(v43) = v54;
    details::appxLog<unsigned short const *,unsigned int,unsigned int,long,unsigned short *>(
      -2146958844,
      v21,
      (const struct _EVENT_DESCRIPTOR *)PackagedComInvalidComServer,
      v20,
      v43,
      v45);
    LODWORD(v46) = -2146958844;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x154,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
      "OSIntegration::DEH::PackagedComExtensionHandler::ParseComServer",
      "APPX_E_INVALID_MANIFEST",
      v46,
      -2146958844);
    v12 = -2146958844;
  }
LABEL_46:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v52);
  return v12;
}

```

## disassembly

```asm
0x180166d20  mov     [rsp-38h+arg_0], rbx
0x180166d25  mov     [rsp-38h+arg_10], r8b
0x180166d2a  push    rbp
0x180166d2b  push    rsi
0x180166d2c  push    rdi
0x180166d2d  push    r12
0x180166d2f  push    r13
0x180166d31  push    r14
0x180166d33  push    r15
0x180166d35  mov     rbp, rsp
0x180166d38  sub     rsp, 70h
0x180166d3c  mov     r12b, r9b
0x180166d3f  mov     rdi, rdx
0x180166d42  mov     r13, rcx
0x180166d45  xor     r15d, r15d
0x180166d48  mov     [rbp+var_10], r15
0x180166d4c  mov     [rbp+var_30], r15d
0x180166d50  mov     rax, [rdx]
0x180166d53  mov     rbx, [rax+60h]
0x180166d57  lea     rcx, [rbp+var_10]
0x180166d5b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180166d60  lea     rdx, [rbp+var_10]
0x180166d64  mov     rcx, rdi
0x180166d67  mov     rax, rbx
0x180166d6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180166d6f  mov     ebx, eax
0x180166d71  test    eax, eax
0x180166d73  jns     short loc_180166D87
0x180166d75  mov     dword ptr [rsp+70h+var_48], eax
0x180166d79  lea     rax, aRootGetChildno_7; "root->get_childNodes(&comServerNodes)"
0x180166d80  mov     edx, 141h
0x180166d85  jmp     short loc_180166DB1
0x180166d87  mov     rcx, [rbp+var_10]
0x180166d8b  mov     rax, [rcx]
0x180166d8e  lea     rdx, [rbp+var_30]
0x180166d92  mov     rax, [rax+40h]
0x180166d96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180166d9b  mov     ebx, eax
0x180166d9d  test    eax, eax
0x180166d9f  jns     short loc_180166DD2
0x180166da1  mov     dword ptr [rsp+70h+var_48], eax; char *
0x180166da5  lea     rax, aComservernodes_0; "comServerNodes->get_length(&listLength)"
0x180166dac  mov     edx, 142h; void *
0x180166db1  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180166db8  lea     r9, aOsintegrationD_428; "OSIntegration::DEH::PackagedComExtensio"...
0x180166dbf  mov     [rsp+70h+var_50], rax; char *
0x180166dc4  mov     rcx, [rbp+38h]; this
0x180166dc8  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180166dcd  jmp     loc_180167274
0x180166dd2  mov     eax, [rbp+var_30]
0x180166dd5  test    eax, eax
0x180166dd7  jnz     loc_180166EDA
0x180166ddd  mov     [rbp+arg_8], r15
0x180166de1  lea     r9, [rbp+arg_8]; struct APPX_XML_LINE_INFORMATION *
0x180166de5  xor     r8d, r8d; unsigned __int16 *
0x180166de8  mov     rdx, rdi; struct IXMLDOMNode *
0x180166deb  mov     rcx, [r13+28h]; this
0x180166def  call    ?GetXmlLineInformation@Package@OSIntegration@@QEBAJPEBUIXMLDOMNode@@PEBGPEAUAPPX_XML_LINE_INFORMATION@@@Z; OSIntegration::Package::GetXmlLineInformation(IXMLDOMNode const *,ushort const *,APPX_XML_LINE_INFORMATION *)
0x180166df4  mov     rcx, [rbp+38h]; this
0x180166df8  mov     edi, 80080204h
0x180166dfd  mov     dword ptr [rsp+70h+var_48], edi; char *
0x180166e01  lea     rax, aHresult0x80080; "((HRESULT)0x80080204L)"
0x180166e08  mov     [rsp+70h+var_50], rax; char *
0x180166e0d  lea     r9, aOsintegrationD_428; "OSIntegration::DEH::PackagedComExtensio"...
0x180166e14  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180166e1b  mov     edx, 152h; void *
0x180166e20  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x180166e25  test    cs:byte_1802E21CA, 4
0x180166e2c  jz      short loc_180166E68
0x180166e2e  mov     rcx, [r13+28h]
0x180166e32  mov     rbx, [rcx+0E0h]
0x180166e39  mov     rcx, [rcx+110h]; unsigned __int16 *
0x180166e40  call    ?RemovePIIfromFilePath@@YAPEBGPEBG@Z; RemovePIIfromFilePath(ushort const *)
0x180166e45  mov     [rsp+70h+var_40], rbx
0x180166e4a  mov     dword ptr [rsp+70h+var_48], edi
0x180166e4e  mov     ecx, dword ptr [rbp+arg_8+4]
0x180166e51  mov     dword ptr [rsp+70h+var_50], ecx
0x180166e55  mov     r9d, dword ptr [rbp+arg_8]
0x180166e59  mov     r8, rax
0x180166e5c  lea     rdx, PackagedComInvalidComServer
0x180166e63  call    McTemplateU0zqqdz_EventWriteTransfer
0x180166e68  mov     rcx, [r13+28h]
0x180166e6c  mov     rbx, [rcx+0E0h]
0x180166e73  mov     rcx, [rcx+110h]; unsigned __int16 *
0x180166e7a  call    ?RemovePIIfromFilePath@@YAPEBGPEBG@Z; RemovePIIfromFilePath(ushort const *)
0x180166e7f  mov     [rsp+70h+var_38], rbx
0x180166e84  mov     dword ptr [rsp+70h+var_40], edi; int
0x180166e88  mov     ecx, dword ptr [rbp+arg_8+4]
0x180166e8b  mov     dword ptr [rsp+70h+var_48], ecx
0x180166e8f  mov     ecx, dword ptr [rbp+arg_8]
0x180166e92  mov     dword ptr [rsp+70h+var_50], ecx
0x180166e96  mov     r9, rax
0x180166e99  lea     r8, PackagedComInvalidComServer
0x180166ea0  mov     ecx, edi
0x180166ea2  call    ??$appxLog@PEBGIIJPEAG@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@PEBGIIJPEAG@Z; details::appxLog<ushort const *,uint,uint,long,ushort *>(long,_GUID const &,_EVENT_DESCRIPTOR const &,ushort const *,uint,uint,long,ushort *)
0x180166ea7  mov     rcx, [rbp+38h]; this
0x180166eab  mov     dword ptr [rsp+70h+var_48], edi; char *
0x180166eaf  lea     rax, aAppxEInvalidMa; "APPX_E_INVALID_MANIFEST"
0x180166eb6  mov     [rsp+70h+var_50], rax; char *
0x180166ebb  lea     r9, aOsintegrationD_428; "OSIntegration::DEH::PackagedComExtensio"...
0x180166ec2  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180166ec9  mov     edx, 154h; void *
0x180166ece  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180166ed3  mov     ebx, edi
0x180166ed5  jmp     loc_180167274
0x180166eda  mov     ecx, r15d
0x180166edd  mov     rdi, [rbp+arg_30]
0x180166ee1  mov     rsi, [rbp+arg_28]
0x180166ee5  mov     r14, [rbp+arg_20]
0x180166ee9  mov     dword ptr [rbp+arg_8], ecx
0x180166eec  cmp     ecx, eax
0x180166eee  jge     loc_180167271
0x180166ef4  mov     [rbp+var_20], r15
0x180166ef8  mov     r15, [rbp+var_10]
0x180166efc  mov     rax, [r15]
0x180166eff  mov     rbx, [rax+38h]
0x180166f03  lea     rcx, [rbp+var_20]
0x180166f07  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180166f0c  lea     r8, [rbp+var_20]
0x180166f10  mov     edx, dword ptr [rbp+arg_8]
0x180166f13  mov     rcx, r15
0x180166f16  mov     rax, rbx
0x180166f19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180166f1e  mov     ebx, eax
0x180166f20  xor     r15d, r15d
0x180166f23  test    eax, eax
0x180166f25  js      loc_180167239
0x180166f2b  mov     [rbp+String2], r15
0x180166f2f  mov     [rbp+var_28], r15
0x180166f33  lea     rdx, [rbp+var_28]
0x180166f37  lea     rcx, [rbp+var_20]
0x180166f3b  call    ??$As@UIXMLDOMElement@@@?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIXMLDOMElement@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IXMLDOMNode>::As<IXMLDOMElement>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IXMLDOMElement>>)
0x180166f40  mov     ebx, eax
0x180166f42  test    eax, eax
0x180166f44  js      loc_1801671F6
0x180166f4a  mov     rcx, [rbp+var_28]
0x180166f4e  mov     rax, [rcx]
0x180166f51  lea     rdx, [rbp+String2]
0x180166f55  mov     rax, [rax+148h]
0x180166f5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180166f61  mov     ebx, eax
0x180166f63  test    eax, eax
0x180166f65  js      loc_1801671E4
0x180166f6b  mov     rbx, [rbp+String2]
0x180166f6f  mov     rdx, rbx; String2
0x180166f72  lea     rcx, aExeserver; "ExeServer"
0x180166f79  call    wcscmp_0
0x180166f7e  test    eax, eax
0x180166f80  jnz     short loc_180166FC3
0x180166f82  mov     [rsp+70h+var_40], rdi; __int64
0x180166f87  mov     [rsp+70h+var_48], rsi; __int64
0x180166f8c  mov     [rsp+70h+var_50], r14; __int64
0x180166f91  mov     r9b, r12b; bool
0x180166f94  mov     r8b, [rbp+arg_10]; bool
0x180166f98  mov     rdx, [rbp+var_28]; struct IXMLDOMElement *
0x180166f9c  mov     rcx, r13; this
0x180166f9f  call    ?ParseExeServer@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@_N1V?$optional@W4TrustLevel@AppModel@@@std@@V?$optional@W4RuntimeBehavior@AppModel@@@6@V?$optional@W4BnoIsolation@AppModel@@@6@@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseExeServer(IXMLDOMElement *,bool,bool,std::optional<AppModel::TrustLevel>,std::optional<AppModel::RuntimeBehavior>,std::optional<AppModel::BnoIsolation>)
0x180166fa4  mov     ebx, eax
0x180166fa6  test    eax, eax
0x180166fa8  jns     loc_1801671A7
0x180166fae  mov     dword ptr [rsp+70h+var_48], eax
0x180166fb2  lea     rax, aParseexeserver; "ParseExeServer(comServerElement.Get(), "...
0x180166fb9  mov     edx, 166h
0x180166fbe  jmp     loc_180167206
0x180166fc3  mov     rdx, rbx; String2
0x180166fc6  lea     rcx, aSurrogateserve_2; "SurrogateServer"
0x180166fcd  call    wcscmp_0
0x180166fd2  test    eax, eax
0x180166fd4  jnz     short loc_180167017
0x180166fd6  mov     [rsp+70h+var_40], rdi; __int64
0x180166fdb  mov     [rsp+70h+var_48], rsi; __int64
0x180166fe0  mov     [rsp+70h+var_50], r14; __int64
0x180166fe5  mov     r9b, r12b; bool
0x180166fe8  mov     r8b, [rbp+arg_10]; bool
0x180166fec  mov     rdx, [rbp+var_28]; struct IXMLDOMElement *
0x180166ff0  mov     rcx, r13; this
0x180166ff3  call    ?ParseSurrogateServer@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@_N1V?$optional@W4TrustLevel@AppModel@@@std@@V?$optional@W4RuntimeBehavior@AppModel@@@6@V?$optional@W4BnoIsolation@AppModel@@@6@@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseSurrogateServer(IXMLDOMElement *,bool,bool,std::optional<AppModel::TrustLevel>,std::optional<AppModel::RuntimeBehavior>,std::optional<AppModel::BnoIsolation>)
0x180166ff8  mov     ebx, eax
0x180166ffa  test    eax, eax
0x180166ffc  jns     loc_1801671A7
0x180167002  mov     dword ptr [rsp+70h+var_48], eax
0x180167006  lea     rax, aParsesurrogate_0; "ParseSurrogateServer(comServerElement.G"...
0x18016700d  mov     edx, 16Bh
0x180167012  jmp     loc_180167206
0x180167017  mov     rdx, rbx; String2
0x18016701a  lea     rcx, aServiceserver; "ServiceServer"
0x180167021  call    wcscmp_0
0x180167026  test    eax, eax
0x180167028  jnz     short loc_18016706B
0x18016702a  mov     [rsp+70h+var_40], rdi; __int64
0x18016702f  mov     [rsp+70h+var_48], rsi; __int64
0x180167034  mov     [rsp+70h+var_50], r14; __int64
0x180167039  mov     r9b, r12b; bool
0x18016703c  mov     r8b, [rbp+arg_10]; bool
0x180167040  mov     rdx, [rbp+var_28]; struct IXMLDOMElement *
0x180167044  mov     rcx, r13; this
0x180167047  call    ?ParseServiceServer@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@_N1V?$optional@W4TrustLevel@AppModel@@@std@@V?$optional@W4RuntimeBehavior@AppModel@@@6@V?$optional@W4BnoIsolation@AppModel@@@6@@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseServiceServer(IXMLDOMElement *,bool,bool,std::optional<AppModel::TrustLevel>,std::optional<AppModel::RuntimeBehavior>,std::optional<AppModel::BnoIsolation>)
0x18016704c  mov     ebx, eax
0x18016704e  test    eax, eax
0x180167050  jns     loc_1801671A7
0x180167056  mov     dword ptr [rsp+70h+var_48], eax
0x18016705a  lea     rax, aParseservicese; "ParseServiceServer(comServerElement.Get"...
0x180167061  mov     edx, 170h
0x180167066  jmp     loc_180167206
0x18016706b  mov     rdx, rbx; String2
0x18016706e  lea     rcx, aTreatasclass; "TreatAsClass"
0x180167075  call    wcscmp_0
0x18016707a  test    eax, eax
0x18016707c  jnz     short loc_1801670B0
0x18016707e  mov     r9b, r12b; bool
0x180167081  mov     r8b, [rbp+arg_10]; bool
0x180167085  mov     rdx, [rbp+var_28]; struct IXMLDOMElement *
0x180167089  mov     rcx, r13; this
0x18016708c  call    ?ParseTreatAsClass@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@_N1@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseTreatAsClass(IXMLDOMElement *,bool,bool)
0x180167091  mov     ebx, eax
0x180167093  test    eax, eax
0x180167095  jns     loc_1801671A7
0x18016709b  mov     dword ptr [rsp+70h+var_48], eax
0x18016709f  lea     rax, aParsetreatascl; "ParseTreatAsClass(comServerElement.Get("...
0x1801670a6  mov     edx, 175h
0x1801670ab  jmp     loc_180167206
0x1801670b0  mov     rdx, rbx; String2
0x1801670b3  lea     rcx, aProgid; "ProgId"
0x1801670ba  call    wcscmp_0
0x1801670bf  test    eax, eax
0x1801670c1  jnz     short loc_1801670F5
0x1801670c3  mov     r9b, r12b; bool
0x1801670c6  mov     r8b, [rbp+arg_10]; bool
0x1801670ca  mov     rdx, [rbp+var_28]; struct IXMLDOMElement *
0x1801670ce  mov     rcx, r13; this
0x1801670d1  call    ?ParseProgId@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@_N1@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseProgId(IXMLDOMElement *,bool,bool)
0x1801670d6  mov     ebx, eax
0x1801670d8  test    eax, eax
0x1801670da  jns     loc_1801671A7
0x1801670e0  mov     dword ptr [rsp+70h+var_48], eax
0x1801670e4  lea     rax, aParseprogidCom; "ParseProgId(comServerElement.Get(), has"...
0x1801670eb  mov     edx, 179h
0x1801670f0  jmp     loc_180167206
0x1801670f5  mov     rdx, rbx; String2
0x1801670f8  lea     rcx, aInprocessserve_5; "InProcessServer"
0x1801670ff  call    wcscmp_0
0x180167104  test    eax, eax
0x180167106  jnz     short loc_18016713A
0x180167108  mov     r9b, r12b; bool
0x18016710b  mov     r8b, [rbp+arg_10]; bool
0x18016710f  mov     rdx, [rbp+var_28]; struct IXMLDOMElement *
0x180167113  mov     rcx, r13; this
0x180167116  call    ?ParseInProcessServer@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@_N1@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseInProcessServer(IXMLDOMElement *,bool,bool)
0x18016711b  mov     ebx, eax
0x18016711d  test    eax, eax
0x18016711f  jns     loc_1801671A7
0x180167125  mov     dword ptr [rsp+70h+var_48], eax
0x180167129  lea     rax, aParseinprocess; "ParseInProcessServer(comServerElement.G"...
0x180167130  mov     edx, 17Eh
0x180167135  jmp     loc_180167206
0x18016713a  mov     rdx, rbx; String2
0x18016713d  lea     rcx, aInprocesshandl_3; "InProcessHandler"
0x180167144  call    wcscmp_0
0x180167149  test    eax, eax
0x18016714b  jnz     short loc_18016717B
0x18016714d  mov     r9b, r12b; bool
0x180167150  mov     r8b, [rbp+arg_10]; bool
0x180167154  mov     rdx, [rbp+var_28]; struct IXMLDOMElement *
0x180167158  mov     rcx, r13; this
0x18016715b  call    ?ParseInProcessHandler@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@_N1@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseInProcessHandler(IXMLDOMElement *,bool,bool)
0x180167160  mov     ebx, eax
0x180167162  test    eax, eax
0x180167164  jns     short loc_1801671A7
0x180167166  mov     dword ptr [rsp+70h+var_48], eax
0x18016716a  lea     rax, aParseinprocess_1; "ParseInProcessHandler(comServerElement."...
0x180167171  mov     edx, 183h
0x180167176  jmp     loc_180167206
0x18016717b  mov     rdx, rbx; String2
0x18016717e  lea     rcx, aManagedinproce_0; "ManagedInProcessServer"
0x180167185  call    wcscmp_0
0x18016718a  test    eax, eax
0x18016718c  jnz     short loc_1801671A7
0x18016718e  mov     r9b, r12b; bool
0x180167191  mov     r8b, [rbp+arg_10]; bool
0x180167195  mov     rdx, [rbp+var_28]; struct IXMLDOMElement *
0x180167199  mov     rcx, r13; this
0x18016719c  call    ?ParseManagedInProcessServer@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@_N1@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseManagedInProcessServer(IXMLDOMElement *,bool,bool)
0x1801671a1  mov     ebx, eax
0x1801671a3  test    eax, eax
0x1801671a5  js      short loc_1801671D2
0x1801671a7  lea     rcx, [rbp+var_28]
0x1801671ab  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801671b0  nop
0x1801671b1  mov     rcx, [rbp+String2]; bstrString
0x1801671b5  call    cs:__imp_SysFreeString
0x1801671bb  nop
0x1801671bc  lea     rcx, [rbp+var_20]
0x1801671c0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801671c5  mov     ecx, dword ptr [rbp+arg_8]
0x1801671c8  inc     ecx
0x1801671ca  mov     eax, [rbp+var_30]
0x1801671cd  jmp     loc_180166EE9
0x1801671d2  mov     dword ptr [rsp+70h+var_48], eax
0x1801671d6  lea     rax, aParsemanagedin_0; "ParseManagedInProcessServer(comServerEl"...
0x1801671dd  mov     edx, 188h
  ... truncated ...
```
