# VirtualMon::VirtualPrinterInfoValidator::ValidatePdcFile(VirtualMon::VirtualPrinterInfo const &)

- ea: `0x180041788`
- end: `0x180041b2b`
- name: `?ValidatePdcFile@VirtualPrinterInfoValidator@VirtualMon@@CAXAEBUVirtualPrinterInfo@2@@Z`
- size: `931`
- prototype: `void __fastcall(const struct VirtualMon::VirtualPrinterInfo *)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180036ca0`

## callees

- `0x180002d40`
- `0x180002d70`
- `0x180003a48`
- `0x1800077c8`
- `0x18000fdd4`
- `0x1800115c4`
- `0x180018224`
- `0x18001d058`
- `0x1800380cc`
- `0x180038174`
- `0x180038638`
- `0x180038718`
- `0x18003ad90`
- `0x18003f2b8`
- `0x18003f2dc`
- `0x180040c6c`
- `0x1800413e8`
- `0x180041788`
- `0x1800420a0`
- `0x1800421e0`
- `0x180048010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180041a93`
- `OLEAUT32!__imp_VariantClear` at `0x180041a93`

## string_xrefs

- `0x180041842`: `onecore\printscan\print\lib\virtualprinterinstallation\lib\virtualprinterinfovalidator.cpp`
- `0x1800418f1`: `Failed to set pdcPathVariant`

## pseudocode

```c
void __fastcall VirtualMon::VirtualPrinterInfoValidator::ValidatePdcFile(
        const struct VirtualMon::VirtualPrinterInfo *a1)
{
  const WCHAR *v2; // rdi
  __int64 v3; // rbx
  unsigned int v4; // eax
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  std::_Ref_count_base *v9; // r14
  __int64 v10; // rax
  _QWORD *v11; // r15
  std::_Ref_count_base *v12; // rcx
  _QWORD *v13; // rsi
  _QWORD *v14; // r15
  __int64 v15; // rax
  _QWORD *v16; // rsi
  std::_Ref_count_base *v17; // rcx
  _QWORD *v18; // rdi
  _QWORD *v19; // rsi
  const struct winrt::impl::slim_source_location *v20; // rbx
  PrintCore::WindowsError *v21; // rbx
  const char *ErrorMsg; // rax
  PrintCore::WindowsError *v23; // rcx
  unsigned int Error; // eax
  unsigned int v25; // eax
  const char *v26; // rdx
  const char *v27; // [rsp+28h] [rbp-E0h]
  const char *v28; // [rsp+28h] [rbp-E0h]
  const char *v29; // [rsp+28h] [rbp-E0h]
  const char *v30; // [rsp+28h] [rbp-E0h]
  const char *v31; // [rsp+28h] [rbp-E0h]
  __int16 v32; // [rsp+30h] [rbp-D8h] BYREF
  __int64 v33; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD v34[2]; // [rsp+40h] [rbp-C8h] BYREF
  VARIANTARG v35; // [rsp+50h] [rbp-B8h] BYREF
  VARIANTARG pvarg; // [rsp+70h] [rbp-98h] BYREF
  const PrintCore::WindowsError *v37; // [rsp+88h] [rbp-80h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+90h] [rbp-78h] BYREF
  __int64 v39; // [rsp+A8h] [rbp-60h] BYREF
  std::_Ref_count_base *v40; // [rsp+B0h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  VirtualPrintDEHTelemetry::WriteDbgTraceInfo("VirtualMon::VirtualPrinterInfoValidator::ValidatePdcFile", L"Entered.");
  v2 = (const WCHAR *)((char *)a1 + 192);
  VirtualMon::VirtualPrinterInfoValidator::ValidateFilePath(v2);
  v39 = 0x11D4F19288D96A05LL;
  v40 = (std::_Ref_count_base *)0xE551329640005FA6LL;
  winrt::create_instance<IXMLDOMDocument2>(v34, &v39);
  v3 = v34[0];
  v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v34[0] + 504LL))(v34[0], 0);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x2F,
    (unsigned int)"onecore\\printscan\\print\\lib\\virtualprinterinstallation\\lib\\virtualprinterinfovalidator.cpp",
    (const char *)v4,
    (int)"Failed to set async to false",
    v27);
  v5 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 544LL))(v3, 0);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x30,
    (unsigned int)"onecore\\printscan\\print\\lib\\virtualprinterinstallation\\lib\\virtualprinterinfovalidator.cpp",
    (const char *)v5,
    (int)"Failed to set validateOnParse to false",
    v28);
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 560LL))(v3, 0);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x31,
    (unsigned int)"onecore\\printscan\\print\\lib\\virtualprinterinstallation\\lib\\virtualprinterinfovalidator.cpp",
    (const char *)v6,
    (int)"Failed to set resolveExternals to false",
    v29);
  v32 = 0;
  pvarg.vt = 0;
  if ( *((_QWORD *)v2 + 3) > 7u )
    v2 = *(const WCHAR **)v2;
  v7 = wil::Variant::SetString((wil::Variant *)&pvarg, v2);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x35,
    (unsigned int)"onecore\\printscan\\print\\lib\\virtualprinterinstallation\\lib\\virtualprinterinfovalidator.cpp",
    (const char *)v7,
    (int)"Failed to set pdcPathVariant",
    v30);
  v35 = pvarg;
  v8 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *, __int16 *))(*(_QWORD *)v3 + 464LL))(v3, &v35, &v32);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x36,
    (unsigned int)"onecore\\printscan\\print\\lib\\virtualprinterinstallation\\lib\\virtualprinterinfovalidator.cpp",
    (const char *)v8,
    (int)"Failed to load pdc file",
    v31);
  if ( !v32 )
  {
    VirtualPrintDEHTelemetry::WriteDbgTraceError(
      "VirtualMon::VirtualPrinterInfoValidator::ValidatePdcFile",
      L"PDC File is invalid.");
    v20 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(&v35);
    winrt::param::hstring::hstring((winrt::param::hstring *)&v39, L"PDC file is invalid");
    winrt::hresult_invalid_argument::hresult_invalid_argument(
      (winrt::hresult_invalid_argument *)pExceptionObject,
      (const struct winrt::param::hstring *)&v39,
      v20);
    throw (winrt::hresult_invalid_argument *)pExceptionObject;
  }
  try
  {
    v33 = v3;
    Microsoft::WRL::ComPtr<IXMLDOMNode>::InternalAddRef(&v33);
    v39 = (__int64)operator new(0x90u);
    v9 = (std::_Ref_count_base *)std::_Ref_count_obj2<PrintDeviceCapabilitiesOM::PrintDeviceCapabilities>::_Ref_count_obj2<PrintDeviceCapabilitiesOM::PrintDeviceCapabilities>(
                                   v39,
                                   &v33);
    *(_QWORD *)&v35.vt = (char *)v9 + 16;
    v35.llVal = (LONGLONG)v9;
    Microsoft::WRL::ComPtr<IXMLDOMDocument2>::InternalRelease(&v33);
    v10 = *((_QWORD *)v9 + 9);
    if ( v10 )
      _InterlockedIncrement((volatile signed __int32 *)(v10 + 8));
    v11 = (_QWORD *)*((_QWORD *)v9 + 8);
    v12 = (std::_Ref_count_base *)*((_QWORD *)v9 + 9);
    if ( v12 )
      std::_Ref_count_base::_Decref(v12);
    v13 = (_QWORD *)*v11;
    v14 = (_QWORD *)v11[1];
    while ( v13 != v14 )
    {
      std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(&v39, *v13);
      PrintDeviceCapabilitiesOM::Parser::VerifyScopePrefixedName(&v39);
      if ( v40 )
        std::_Ref_count_base::_Decref(v40);
      v13 += 2;
    }
    v15 = *((_QWORD *)v9 + 5);
    if ( v15 )
      _InterlockedIncrement((volatile signed __int32 *)(v15 + 8));
    v16 = (_QWORD *)*((_QWORD *)v9 + 4);
    v17 = (std::_Ref_count_base *)*((_QWORD *)v9 + 5);
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
    v18 = (_QWORD *)*v16;
    v19 = (_QWORD *)v16[1];
    while ( v18 != v19 )
    {
      std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(&v39, *v18);
      PrintDeviceCapabilitiesOM::Parser::VerifyScopePrefixedName(&v39);
      if ( v40 )
        std::_Ref_count_base::_Decref(v40);
      v18 += 2;
    }
    if ( v9 )
      std::_Ref_count_base::_Decref(v9);
    VariantClear(&pvarg);
    if ( v3 )
      winrt::com_ptr<Windows::System::Internal::IUserManagerStatics>::unconditional_release_ref(v34);
  }
  catch ( const PrintCore::WindowsError *v37 )
  {
    v21 = v37;
    ErrorMsg = PrintCore::WindowsError::GetErrorMsg(v37);
    VirtualPrintDEHTelemetry::WriteDbgTraceError(
      "VirtualMon::VirtualPrinterInfoValidator::ValidatePdcFile",
      L"pdc file is invalid, msg: %hs",
      ErrorMsg);
    PrintCore::WindowsError::GetErrorMsg(v21);
    Error = PrintCore::WindowsError::GetError(v23);
    v25 = wil::verify_hresult<long>(Error);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x51,
      (unsigned int)"onecore\\printscan\\print\\lib\\virtualprinterinstallation\\lib\\virtualprinterinfovalidator.cpp",
      (const char *)v25,
      (int)"pdc file is invalid, msg: %hs",
      v26);
  }
}

```

## disassembly

```asm
0x180041788  push    rbx
0x18004178a  push    rsi
0x18004178b  push    rdi
0x18004178c  push    r12
0x18004178e  push    r14
0x180041790  push    r15
0x180041792  sub     rsp, 0D8h
0x180041799  mov     rax, cs:__security_cookie
0x1800417a0  xor     rax, rsp
0x1800417a3  mov     [rsp+108h+var_40], rax
0x1800417ab  mov     rdi, rcx
0x1800417ae  xor     r12d, r12d
0x1800417b1  lea     rdx, aEntered; "Entered."
0x1800417b8  lea     rcx, aVirtualmonVirt_14; "VirtualMon::VirtualPrinterInfoValidator"...
0x1800417bf  call    ?WriteDbgTraceInfo@VirtualPrintDEHTelemetry@@SAXPEADPEAGZZ; VirtualPrintDEHTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800417c4  add     rdi, 0C0h
0x1800417cb  mov     rcx, rdi; lpFileName
0x1800417ce  call    ?ValidateFilePath@VirtualPrinterInfoValidator@VirtualMon@@CAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; VirtualMon::VirtualPrinterInfoValidator::ValidateFilePath(std::wstring const &)
0x1800417d3  mov     dword ptr [rsp+108h+var_60], 88D96A05h
0x1800417de  mov     dword ptr [rsp+108h+var_60+4], 11D4F192h
0x1800417e9  mov     dword ptr [rsp+108h+var_58], 40005FA6h
0x1800417f4  mov     dword ptr [rsp+108h+var_58+4], 0E5513296h
0x1800417ff  lea     rdx, [rsp+108h+var_60]
0x180041807  lea     rcx, [rsp+108h+var_C8]
0x18004180c  call    ??$create_instance@UIXMLDOMDocument2@@@winrt@@YA?A_PAEBUguid@0@IPEAX@Z
0x180041811  nop
0x180041812  mov     rbx, [rsp+108h+var_C8]
0x180041817  mov     rax, [rbx]
0x18004181a  xor     edx, edx
0x18004181c  mov     rcx, rbx
0x18004181f  mov     rax, [rax+1F8h]
0x180041826  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004182b  mov     rcx, [rsp+108h]; this
0x180041833  lea     rdx, aFailedToSetAsy; "Failed to set async to false"
0x18004183a  mov     qword ptr [rsp+108h+var_E8], rdx; int
0x18004183f  mov     r9d, eax; char *
0x180041842  lea     rsi, aOnecorePrintsc; "onecore\\printscan\\print\\lib\\virtual"...
0x180041849  mov     r8, rsi; unsigned int
0x18004184c  lea     edx, [r12+2Fh]; void *
0x180041851  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180041856  mov     rax, [rbx]
0x180041859  xor     edx, edx
0x18004185b  mov     rcx, rbx
0x18004185e  mov     rax, [rax+220h]
0x180041865  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004186a  mov     rcx, [rsp+108h]; this
0x180041872  lea     rdx, aFailedToSetVal; "Failed to set validateOnParse to false"
0x180041879  mov     qword ptr [rsp+108h+var_E8], rdx; int
0x18004187e  mov     r9d, eax; char *
0x180041881  mov     r8, rsi; unsigned int
0x180041884  lea     edx, [r12+30h]; void *
0x180041889  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18004188e  mov     rax, [rbx]
0x180041891  xor     edx, edx
0x180041893  mov     rcx, rbx
0x180041896  mov     rax, [rax+230h]
0x18004189d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800418a2  mov     rcx, [rsp+108h]; this
0x1800418aa  lea     rdx, aFailedToSetRes; "Failed to set resolveExternals to false"
0x1800418b1  mov     qword ptr [rsp+108h+var_E8], rdx; int
0x1800418b6  mov     r9d, eax; char *
0x1800418b9  mov     r8, rsi; unsigned int
0x1800418bc  lea     edx, [r12+31h]; void *
0x1800418c1  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800418c6  mov     [rsp+108h+var_D8], r12w
0x1800418cc  mov     word ptr [rsp+108h+pvarg], r12w
0x1800418d2  cmp     qword ptr [rdi+18h], 7
0x1800418d7  jbe     short loc_1800418DC
0x1800418d9  mov     rdi, [rdi]
0x1800418dc  mov     rdx, rdi; unsigned __int16 *
0x1800418df  lea     rcx, [rsp+108h+pvarg]; this
0x1800418e4  call    ?SetString@Variant@wil@@QEAAJPEBG@Z; wil::Variant::SetString(ushort const *)
0x1800418e9  mov     rcx, [rsp+108h]; this
0x1800418f1  lea     rdx, aFailedToSetPdc; "Failed to set pdcPathVariant"
0x1800418f8  mov     qword ptr [rsp+108h+var_E8], rdx; int
0x1800418fd  mov     r9d, eax; char *
0x180041900  mov     r8, rsi; unsigned int
0x180041903  mov     edx, 35h ; '5'; void *
0x180041908  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18004190d  movups  xmm0, xmmword ptr [rsp+108h+pvarg]
0x180041912  movaps  [rsp+108h+var_B8], xmm0
0x180041917  movsd   xmm1, qword ptr [rsp+108h+pvarg+10h]
0x180041920  movsd   [rsp+108h+var_A8], xmm1
0x180041926  mov     rax, [rbx]
0x180041929  lea     r8, [rsp+108h+var_D8]
0x18004192e  lea     rdx, [rsp+108h+var_B8]
0x180041933  mov     rcx, rbx
0x180041936  mov     rax, [rax+1D0h]
0x18004193d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041942  mov     rcx, [rsp+108h]; this
0x18004194a  lea     rdx, aFailedToLoadPd; "Failed to load pdc file"
0x180041951  mov     qword ptr [rsp+108h+var_E8], rdx; int
0x180041956  mov     r9d, eax; char *
0x180041959  mov     r8, rsi; unsigned int
0x18004195c  mov     edx, 36h ; '6'; void *
0x180041961  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180041966  cmp     [rsp+108h+var_D8], r12w
0x18004196c  jz      loc_180041ACA
0x180041972  mov     [rsp+108h+var_D0], rbx
0x180041977  lea     rcx, [rsp+108h+var_D0]
0x18004197c  call    ?InternalAddRef@?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IXMLDOMNode>::InternalAddRef(void)
0x180041981  nop
0x180041982  mov     ecx, 90h; Size
0x180041987  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004198c  mov     [rsp+108h+var_60], rax
0x180041994  lea     rdx, [rsp+108h+var_D0]
0x180041999  mov     rcx, rax
0x18004199c  call    ??$?0V?$ComPtr@UIXMLDOMDocument2@@@WRL@Microsoft@@@?$_Ref_count_obj2@VPrintDeviceCapabilities@PrintDeviceCapabilitiesOM@@@std@@QEAA@$$QEAV?$ComPtr@UIXMLDOMDocument2@@@WRL@Microsoft@@@Z; std::_Ref_count_obj2<PrintDeviceCapabilitiesOM::PrintDeviceCapabilities>::_Ref_count_obj2<PrintDeviceCapabilitiesOM::PrintDeviceCapabilities>(Microsoft::WRL::ComPtr<IXMLDOMDocument2> &&)
0x1800419a1  mov     r14, rax
0x1800419a4  lea     rdi, [rax+10h]
0x1800419a8  mov     qword ptr [rsp+108h+var_B8], rdi
0x1800419ad  mov     qword ptr [rsp+108h+var_B8+8], rax
0x1800419b2  lea     rcx, [rsp+108h+var_D0]
0x1800419b7  call    ?InternalRelease@?$ComPtr@UIXMLDOMDocument2@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMDocument2>::InternalRelease(void)
0x1800419bc  mov     rax, [rdi+38h]
0x1800419c0  test    rax, rax
0x1800419c3  jz      short loc_1800419C9
0x1800419c5  lock inc dword ptr [rax+8]
0x1800419c9  mov     r15, [rdi+30h]
0x1800419cd  mov     rcx, [rdi+38h]; this
0x1800419d1  test    rcx, rcx
0x1800419d4  jz      short loc_1800419DB
0x1800419d6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800419db  mov     rsi, [r15]
0x1800419de  mov     r15, [r15+8]
0x1800419e2  cmp     rsi, r15
0x1800419e5  jz      short loc_180041A1E
0x1800419e7  mov     rdx, [rsi]
0x1800419ea  lea     rcx, [rsp+108h+var_60]
0x1800419f2  call    ??0?$shared_ptr@VOption@PrintDeviceCapabilitiesOM@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(std::shared_ptr<PrintDeviceCapabilitiesOM::Option> const &)
0x1800419f7  nop
0x1800419f8  lea     rcx, [rsp+108h+var_60]
0x180041a00  call    ?VerifyScopePrefixedName@Parser@PrintDeviceCapabilitiesOM@@YAXAEBV?$shared_ptr@$$CBVQualifiedName@PrintDeviceCapabilitiesOM@@@std@@@Z; PrintDeviceCapabilitiesOM::Parser::VerifyScopePrefixedName(std::shared_ptr<PrintDeviceCapabilitiesOM::QualifiedName const> const &)
0x180041a05  nop
0x180041a06  mov     rcx, [rsp+108h+var_58]; this
0x180041a0e  test    rcx, rcx
0x180041a11  jz      short loc_180041A18
0x180041a13  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180041a18  add     rsi, 10h
0x180041a1c  jmp     short loc_1800419E2
0x180041a1e  mov     rax, [rdi+18h]
0x180041a22  test    rax, rax
0x180041a25  jz      short loc_180041A2B
0x180041a27  lock inc dword ptr [rax+8]
0x180041a2b  mov     rsi, [rdi+10h]
0x180041a2f  mov     rcx, [rdi+18h]; this
0x180041a33  test    rcx, rcx
0x180041a36  jz      short loc_180041A3D
0x180041a38  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180041a3d  mov     rdi, [rsi]
0x180041a40  mov     rsi, [rsi+8]
0x180041a44  cmp     rdi, rsi
0x180041a47  jz      short loc_180041A80
0x180041a49  mov     rdx, [rdi]
0x180041a4c  lea     rcx, [rsp+108h+var_60]
0x180041a54  call    ??0?$shared_ptr@VOption@PrintDeviceCapabilitiesOM@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(std::shared_ptr<PrintDeviceCapabilitiesOM::Option> const &)
0x180041a59  nop
0x180041a5a  lea     rcx, [rsp+108h+var_60]
0x180041a62  call    ?VerifyScopePrefixedName@Parser@PrintDeviceCapabilitiesOM@@YAXAEBV?$shared_ptr@$$CBVQualifiedName@PrintDeviceCapabilitiesOM@@@std@@@Z; PrintDeviceCapabilitiesOM::Parser::VerifyScopePrefixedName(std::shared_ptr<PrintDeviceCapabilitiesOM::QualifiedName const> const &)
0x180041a67  nop
0x180041a68  mov     rcx, [rsp+108h+var_58]; this
0x180041a70  test    rcx, rcx
0x180041a73  jz      short loc_180041A7A
0x180041a75  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180041a7a  add     rdi, 10h
0x180041a7e  jmp     short loc_180041A44
0x180041a80  test    r14, r14
0x180041a83  jz      short loc_180041A8E
0x180041a85  mov     rcx, r14; this
0x180041a88  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180041a8d  nop
0x180041a8e  lea     rcx, [rsp+108h+pvarg]; pvarg
0x180041a93  call    cs:__imp_VariantClear
0x180041a99  nop
0x180041a9a  test    rbx, rbx
0x180041a9d  jz      short loc_180041AA9
0x180041a9f  lea     rcx, [rsp+108h+var_C8]
0x180041aa4  call    ?unconditional_release_ref@?$com_ptr@UIUserManagerStatics@Internal@System@Windows@@@winrt@@AEAAXXZ; winrt::com_ptr<Windows::System::Internal::IUserManagerStatics>::unconditional_release_ref(void)
0x180041aa9  mov     rcx, [rsp+108h+var_40]
0x180041ab1  xor     rcx, rsp; StackCookie
0x180041ab4  call    __security_check_cookie
0x180041ab9  add     rsp, 0D8h
0x180041ac0  pop     r15
0x180041ac2  pop     r14
0x180041ac4  pop     r12
0x180041ac6  pop     rdi
0x180041ac7  pop     rsi
0x180041ac8  pop     rbx
0x180041ac9  retn
0x180041aca  lea     rdx, aPdcFileIsInval_0; "PDC File is invalid."
0x180041ad1  lea     rcx, aVirtualmonVirt_14; "VirtualMon::VirtualPrinterInfoValidator"...
0x180041ad8  call    ?WriteDbgTraceError@VirtualPrintDEHTelemetry@@SAXPEADPEAGZZ; VirtualPrintDEHTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180041add  lea     rcx, [rsp+108h+var_B8]
0x180041ae2  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180041ae7  mov     rbx, rax
0x180041aea  lea     rdx, aPdcFileIsInval; "PDC file is invalid"
0x180041af1  lea     rcx, [rsp+108h+var_60]; this
0x180041af9  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180041afe  mov     r8, rbx; struct winrt::impl::slim_source_location *
0x180041b01  lea     rdx, [rsp+108h+var_60]; struct winrt::param::hstring *
0x180041b09  lea     rcx, [rsp+108h+pExceptionObject]; this
0x180041b11  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180041b16  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x180041b1d  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x180041b25  call    _CxxThrowException_0
```
