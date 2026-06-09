# VirtualMon::VirtualPrinterInfoValidator::ValidatePdrFile(VirtualMon::VirtualPrinterInfo const &)

- ea: `0x180041b34`
- end: `0x180041e1d`
- name: `?ValidatePdrFile@VirtualPrinterInfoValidator@VirtualMon@@CAXAEBUVirtualPrinterInfo@2@@Z`
- size: `745`
- prototype: `void __fastcall(const struct VirtualMon::VirtualPrinterInfo *)`
- caller_count: `1`
- callee_count: `19`
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
- `0x1800386b8`
- `0x18003ad90`
- `0x18003f2b8`
- `0x18003f2dc`
- `0x180040c6c`
- `0x1800413e8`
- `0x180041b34`
- `0x1800421e0`
- `0x180048010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180041da0`
- `OLEAUT32!__imp_VariantClear` at `0x180041da0`

## string_xrefs

- `0x180041c22`: `onecore\printscan\print\lib\virtualprinterinstallation\lib\virtualprinterinfovalidator.cpp`
- `0x180041b74`: `PDR file path is empty`
- `0x180041ccf`: `Failed to set pdrPathVariant`

## pseudocode

```c
void __fastcall VirtualMon::VirtualPrinterInfoValidator::ValidatePdrFile(
        const struct VirtualMon::VirtualPrinterInfo *a1)
{
  const WCHAR *v2; // rdi
  __int64 v3; // rbx
  unsigned int v4; // eax
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  std::_Ref_count_base *v9; // rdi
  const struct winrt::impl::slim_source_location *v10; // rbx
  PrintCore::WindowsError *v11; // rbx
  const char *ErrorMsg; // rax
  PrintCore::WindowsError *v13; // rcx
  unsigned int Error; // eax
  unsigned int v15; // eax
  const char *v16; // rdx
  const char *v17; // [rsp+28h] [rbp-D0h]
  const char *v18; // [rsp+28h] [rbp-D0h]
  const char *v19; // [rsp+28h] [rbp-D0h]
  const char *v20; // [rsp+28h] [rbp-D0h]
  const char *v21; // [rsp+28h] [rbp-D0h]
  __int16 v22; // [rsp+30h] [rbp-C8h] BYREF
  __int64 v23; // [rsp+38h] [rbp-C0h] BYREF
  __int64 v24; // [rsp+40h] [rbp-B8h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-B0h] BYREF
  const PrintCore::WindowsError *v26; // [rsp+60h] [rbp-98h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+68h] [rbp-90h] BYREF
  _BYTE v28[32]; // [rsp+80h] [rbp-78h] BYREF
  VARIANTARG v29; // [rsp+A0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  VirtualPrintDEHTelemetry::WriteDbgTraceInfo("VirtualMon::VirtualPrinterInfoValidator::ValidatePdrFile", L"Entered.");
  if ( *((_QWORD *)a1 + 34) )
  {
    v2 = (const WCHAR *)((char *)a1 + 256);
    VirtualMon::VirtualPrinterInfoValidator::ValidateFilePath(v2);
    *(_QWORD *)&v29.vt = 0x11D4F19288D96A05LL;
    v29.llVal = 0xE551329640005FA6uLL;
    winrt::create_instance<IXMLDOMDocument2>(&v24, &v29);
    v3 = v24;
    v4 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v24 + 504LL))(v24, 0);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x63,
      (unsigned int)"onecore\\printscan\\print\\lib\\virtualprinterinstallation\\lib\\virtualprinterinfovalidator.cpp",
      (const char *)v4,
      (int)"Failed to set async to false",
      v17);
    v5 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 544LL))(v3, 0);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x64,
      (unsigned int)"onecore\\printscan\\print\\lib\\virtualprinterinstallation\\lib\\virtualprinterinfovalidator.cpp",
      (const char *)v5,
      (int)"Failed to set validateOnParse to false",
      v18);
    v6 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 560LL))(v3, 0);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x65,
      (unsigned int)"onecore\\printscan\\print\\lib\\virtualprinterinstallation\\lib\\virtualprinterinfovalidator.cpp",
      (const char *)v6,
      (int)"Failed to set resolveExternals to false",
      v19);
    v22 = 0;
    pvarg.vt = 0;
    if ( *((_QWORD *)v2 + 3) > 7u )
      v2 = *(const WCHAR **)v2;
    v7 = wil::Variant::SetString((wil::Variant *)&pvarg, v2);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x69,
      (unsigned int)"onecore\\printscan\\print\\lib\\virtualprinterinstallation\\lib\\virtualprinterinfovalidator.cpp",
      (const char *)v7,
      (int)"Failed to set pdrPathVariant",
      v20);
    v29 = pvarg;
    v8 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *, __int16 *))(*(_QWORD *)v3 + 464LL))(v3, &v29, &v22);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x6A,
      (unsigned int)"onecore\\printscan\\print\\lib\\virtualprinterinstallation\\lib\\virtualprinterinfovalidator.cpp",
      (const char *)v8,
      (int)"Failed to load pdr file",
      v21);
    if ( !v22 )
    {
      VirtualPrintDEHTelemetry::WriteDbgTraceError(
        "VirtualMon::VirtualPrinterInfoValidator::ValidatePdrFile",
        L"PDR File is invalid.");
      v10 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(&v29);
      winrt::param::hstring::hstring((winrt::param::hstring *)v28, L"PDR file is invalid");
      winrt::hresult_invalid_argument::hresult_invalid_argument(
        (winrt::hresult_invalid_argument *)pExceptionObject,
        (const struct winrt::param::hstring *)v28,
        v10);
      throw (winrt::hresult_invalid_argument *)pExceptionObject;
    }
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v23 = v3;
      Microsoft::WRL::ComPtr<IXMLDOMNode>::InternalAddRef(&v23);
      *(_QWORD *)&v29.vt = operator new(0x20u);
      v9 = (std::_Ref_count_base *)std::_Ref_count_obj2<PrintDeviceCapabilitiesOM::PrintDeviceResources>::_Ref_count_obj2<PrintDeviceCapabilitiesOM::PrintDeviceResources>(
                                     *(_QWORD *)&v29.vt,
                                     &v23);
      Microsoft::WRL::ComPtr<IXMLDOMDocument2>::InternalRelease(&v23);
      if ( v9 )
        std::_Ref_count_base::_Decref(v9);
      VariantClear(&pvarg);
      if ( v3 )
        winrt::com_ptr<Windows::System::Internal::IUserManagerStatics>::unconditional_release_ref(&v24);
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &PrintCore::WindowsError `RTTI Type Descriptor', &v26) )
      {
        v11 = v26;
        ErrorMsg = PrintCore::WindowsError::GetErrorMsg(v26);
        VirtualPrintDEHTelemetry::WriteDbgTraceError(
          "VirtualMon::VirtualPrinterInfoValidator::ValidatePdrFile",
          L"pdr file is invalid, msg: %hs",
          ErrorMsg);
        PrintCore::WindowsError::GetErrorMsg(v11);
        Error = PrintCore::WindowsError::GetError(v13);
        v15 = wil::verify_hresult<long>(Error);
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x7B,
          (unsigned int)"onecore\\printscan\\print\\lib\\virtualprinterinstallation\\lib\\virtualprinterinfovalidator.cpp",
          (const char *)v15,
          (int)"pdr file is invalid, msg: %hs",
          v16);
      }
    }
  }
  else
  {
    VirtualPrintDEHTelemetry::WriteDbgTraceInfo(
      "VirtualMon::VirtualPrinterInfoValidator::ValidatePdrFile",
      L"PDR file path is empty");
  }
}

```

## disassembly

```asm
0x180041b34  push    rbx
0x180041b36  push    rsi
0x180041b37  push    rdi
0x180041b38  push    r15
0x180041b3a  sub     rsp, 0D8h
0x180041b41  mov     rax, cs:__security_cookie
0x180041b48  xor     rax, rsp
0x180041b4b  mov     [rsp+0F8h+var_38], rax
0x180041b53  mov     rdi, rcx
0x180041b56  xor     esi, esi
0x180041b58  lea     rdx, aEntered; "Entered."
0x180041b5f  lea     rcx, aVirtualmonVirt_3; "VirtualMon::VirtualPrinterInfoValidator"...
0x180041b66  call    ?WriteDbgTraceInfo@VirtualPrintDEHTelemetry@@SAXPEADPEAGZZ; VirtualPrintDEHTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180041b6b  cmp     [rdi+110h], rsi
0x180041b72  jnz     short loc_180041BA4
0x180041b74  lea     rdx, aPdrFilePathIsE; "PDR file path is empty"
0x180041b7b  lea     rcx, aVirtualmonVirt_3; "VirtualMon::VirtualPrinterInfoValidator"...
0x180041b82  call    ?WriteDbgTraceInfo@VirtualPrintDEHTelemetry@@SAXPEADPEAGZZ; VirtualPrintDEHTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180041b87  mov     rcx, [rsp+0F8h+var_38]
0x180041b8f  xor     rcx, rsp; StackCookie
0x180041b92  call    __security_check_cookie
0x180041b97  add     rsp, 0D8h
0x180041b9e  pop     r15
0x180041ba0  pop     rdi
0x180041ba1  pop     rsi
0x180041ba2  pop     rbx
0x180041ba3  retn
0x180041ba4  add     rdi, 100h
0x180041bab  mov     rcx, rdi; lpFileName
0x180041bae  call    ?ValidateFilePath@VirtualPrinterInfoValidator@VirtualMon@@CAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; VirtualMon::VirtualPrinterInfoValidator::ValidateFilePath(std::wstring const &)
0x180041bb3  mov     dword ptr [rsp+0F8h+var_58], 88D96A05h
0x180041bbe  mov     dword ptr [rsp+0F8h+var_58+4], 11D4F192h
0x180041bc9  mov     dword ptr [rsp+0F8h+var_58+8], 40005FA6h
0x180041bd4  mov     dword ptr [rsp+0F8h+var_58+0Ch], 0E5513296h
0x180041bdf  lea     rdx, [rsp+0F8h+var_58]
0x180041be7  lea     rcx, [rsp+0F8h+var_B8]
0x180041bec  call    ??$create_instance@UIXMLDOMDocument2@@@winrt@@YA?A_PAEBUguid@0@IPEAX@Z
0x180041bf1  nop
0x180041bf2  mov     rbx, [rsp+0F8h+var_B8]
0x180041bf7  mov     rax, [rbx]
0x180041bfa  xor     edx, edx
0x180041bfc  mov     rcx, rbx
0x180041bff  mov     rax, [rax+1F8h]
0x180041c06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041c0b  mov     rcx, [rsp+0F8h]; this
0x180041c13  lea     rdx, aFailedToSetAsy; "Failed to set async to false"
0x180041c1a  mov     qword ptr [rsp+0F8h+var_D8], rdx; int
0x180041c1f  mov     r9d, eax; char *
0x180041c22  lea     r15, aOnecorePrintsc; "onecore\\printscan\\print\\lib\\virtual"...
0x180041c29  mov     r8, r15; unsigned int
0x180041c2c  mov     edx, 63h ; 'c'; void *
0x180041c31  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180041c36  mov     rax, [rbx]
0x180041c39  xor     edx, edx
0x180041c3b  mov     rcx, rbx
0x180041c3e  mov     rax, [rax+220h]
0x180041c45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041c4a  mov     rcx, [rsp+0F8h]; this
0x180041c52  lea     rdx, aFailedToSetVal; "Failed to set validateOnParse to false"
0x180041c59  mov     qword ptr [rsp+0F8h+var_D8], rdx; int
0x180041c5e  mov     r9d, eax; char *
0x180041c61  mov     r8, r15; unsigned int
0x180041c64  mov     edx, 64h ; 'd'; void *
0x180041c69  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180041c6e  mov     rax, [rbx]
0x180041c71  xor     edx, edx
0x180041c73  mov     rcx, rbx
0x180041c76  mov     rax, [rax+230h]
0x180041c7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041c82  mov     rcx, [rsp+0F8h]; this
0x180041c8a  lea     rdx, aFailedToSetRes; "Failed to set resolveExternals to false"
0x180041c91  mov     qword ptr [rsp+0F8h+var_D8], rdx; int
0x180041c96  mov     r9d, eax; char *
0x180041c99  mov     r8, r15; unsigned int
0x180041c9c  mov     edx, 65h ; 'e'; void *
0x180041ca1  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180041ca6  mov     [rsp+0F8h+var_C8], si
0x180041cab  mov     word ptr [rsp+0F8h+pvarg], si
0x180041cb0  cmp     qword ptr [rdi+18h], 7
0x180041cb5  jbe     short loc_180041CBA
0x180041cb7  mov     rdi, [rdi]
0x180041cba  mov     rdx, rdi; unsigned __int16 *
0x180041cbd  lea     rcx, [rsp+0F8h+pvarg]; this
0x180041cc2  call    ?SetString@Variant@wil@@QEAAJPEBG@Z; wil::Variant::SetString(ushort const *)
0x180041cc7  mov     rcx, [rsp+0F8h]; this
0x180041ccf  lea     rdx, aFailedToSetPdr; "Failed to set pdrPathVariant"
0x180041cd6  mov     qword ptr [rsp+0F8h+var_D8], rdx; int
0x180041cdb  mov     r9d, eax; char *
0x180041cde  mov     r8, r15; unsigned int
0x180041ce1  mov     edx, 69h ; 'i'; void *
0x180041ce6  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180041ceb  movups  xmm0, xmmword ptr [rsp+0F8h+pvarg]
0x180041cf0  movaps  [rsp+0F8h+var_58], xmm0
0x180041cf8  movsd   xmm1, qword ptr [rsp+0F8h+pvarg+10h]
0x180041cfe  movsd   [rsp+0F8h+var_48], xmm1
0x180041d07  mov     rax, [rbx]
0x180041d0a  lea     r8, [rsp+0F8h+var_C8]
0x180041d0f  lea     rdx, [rsp+0F8h+var_58]
0x180041d17  mov     rcx, rbx
0x180041d1a  mov     rax, [rax+1D0h]
0x180041d21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041d26  mov     rcx, [rsp+0F8h]; this
0x180041d2e  lea     rdx, aFailedToLoadPd_0; "Failed to load pdr file"
0x180041d35  mov     qword ptr [rsp+0F8h+var_D8], rdx; int
0x180041d3a  mov     r9d, eax; char *
0x180041d3d  mov     r8, r15; unsigned int
0x180041d40  mov     edx, 6Ah ; 'j'; void *
0x180041d45  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180041d4a  cmp     [rsp+0F8h+var_C8], si
0x180041d4f  jz      short loc_180041DBF
0x180041d51  mov     [rsp+0F8h+var_C0], rbx
0x180041d56  lea     rcx, [rsp+0F8h+var_C0]
0x180041d5b  call    ?InternalAddRef@?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IXMLDOMNode>::InternalAddRef(void)
0x180041d60  nop
0x180041d61  mov     ecx, 20h ; ' '; Size
0x180041d66  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180041d6b  mov     qword ptr [rsp+0F8h+var_58], rax
0x180041d73  lea     rdx, [rsp+0F8h+var_C0]
0x180041d78  mov     rcx, rax
0x180041d7b  call    ??$?0V?$ComPtr@UIXMLDOMDocument2@@@WRL@Microsoft@@@?$_Ref_count_obj2@VPrintDeviceResources@PrintDeviceCapabilitiesOM@@@std@@QEAA@$$QEAV?$ComPtr@UIXMLDOMDocument2@@@WRL@Microsoft@@@Z; std::_Ref_count_obj2<PrintDeviceCapabilitiesOM::PrintDeviceResources>::_Ref_count_obj2<PrintDeviceCapabilitiesOM::PrintDeviceResources>(Microsoft::WRL::ComPtr<IXMLDOMDocument2> &&)
0x180041d80  mov     rdi, rax
0x180041d83  lea     rcx, [rsp+0F8h+var_C0]
0x180041d88  call    ?InternalRelease@?$ComPtr@UIXMLDOMDocument2@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMDocument2>::InternalRelease(void)
0x180041d8d  test    rdi, rdi
0x180041d90  jz      short loc_180041D9B
0x180041d92  mov     rcx, rdi; this
0x180041d95  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180041d9a  nop
0x180041d9b  lea     rcx, [rsp+0F8h+pvarg]; pvarg
0x180041da0  call    cs:__imp_VariantClear
0x180041da6  nop
0x180041da7  test    rbx, rbx
0x180041daa  jz      loc_180041B87
0x180041db0  lea     rcx, [rsp+0F8h+var_B8]
0x180041db5  call    ?unconditional_release_ref@?$com_ptr@UIUserManagerStatics@Internal@System@Windows@@@winrt@@AEAAXXZ; winrt::com_ptr<Windows::System::Internal::IUserManagerStatics>::unconditional_release_ref(void)
0x180041dba  jmp     loc_180041B87
0x180041dbf  lea     rdx, aPdrFileIsInval_1; "PDR File is invalid."
0x180041dc6  lea     rcx, aVirtualmonVirt_3; "VirtualMon::VirtualPrinterInfoValidator"...
0x180041dcd  call    ?WriteDbgTraceError@VirtualPrintDEHTelemetry@@SAXPEADPEAGZZ; VirtualPrintDEHTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180041dd2  lea     rcx, [rsp+0F8h+var_58]
0x180041dda  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180041ddf  mov     rbx, rax
0x180041de2  lea     rdx, aPdrFileIsInval; "PDR file is invalid"
0x180041de9  lea     rcx, [rsp+0F8h+var_78]; this
0x180041df1  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180041df6  mov     r8, rbx; struct winrt::impl::slim_source_location *
0x180041df9  lea     rdx, [rsp+0F8h+var_78]; struct winrt::param::hstring *
0x180041e01  lea     rcx, [rsp+0F8h+pExceptionObject]; this
0x180041e06  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180041e0b  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x180041e12  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x180041e17  call    _CxxThrowException_0
```
