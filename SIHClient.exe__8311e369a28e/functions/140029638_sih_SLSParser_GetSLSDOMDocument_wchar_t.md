# sih::SLSParser::GetSLSDOMDocument(wchar_t *)

- ea: `0x140029638`
- end: `0x140029911`
- name: `?GetSLSDOMDocument@SLSParser@sih@@CAPEAUIXMLDOMDocument2@@PEA_W@Z`
- size: `729`
- prototype: `struct IXMLDOMDocument2 *__fastcall(wchar_t *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14002812c`

## callees

- `0x14000711c`
- `0x1400154b4`
- `0x14001ed4c`
- `0x14001fa78`
- `0x14001fa84`
- `0x14001fab8`
- `0x14001fac4`
- `0x140029638`
- `0x14002a88c`
- `0x140045dc0`
- `0x1400481f8`
- `0x14004cd00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400296bc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400296bc`
- `OLEAUT32!__imp_SysAllocString` at `0x140029680`
- `OLEAUT32!__imp_SysAllocString` at `0x140029680`
- `OLEAUT32!__imp_SysFreeString` at `0x14002982d`
- `OLEAUT32!__imp_SysFreeString` at `0x14002982d`
- `OLEAUT32!__imp_VariantClear` at `0x140029795`
- `OLEAUT32!__imp_VariantClear` at `0x140029795`

## string_xrefs

- `0x140029833`: `Returning WU_E_REDIRECTOR_LOAD_XML after loadXML`
- `0x140029679`: `xmlns:plugin="http://schemas.microsoft.com/msus/2011/04/StoreWUAuthInitialization"`
- `0x1400298d5`: `loadXML`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
struct IXMLDOMDocument2 *__fastcall sih::SLSParser::GetSLSDOMDocument(wchar_t *a1)
{
  HRESULT v2; // eax
  int v3; // eax
  int v4; // eax
  int v5; // esi
  LPVOID v6; // rbx
  __int64 v8; // rdi
  unsigned int (__fastcall *v9)(__int64, __int64); // rbx
  __int64 AddressOf; // rax
  __int64 v11; // rax
  LPVOID *ppv; // [rsp+20h] [rbp-59h]
  _BYTE pExceptionObject[32]; // [rsp+30h] [rbp-49h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-29h] BYREF
  __int16 v15; // [rsp+58h] [rbp-21h] BYREF
  LPVOID v16; // [rsp+60h] [rbp-19h] BYREF
  __int64 v17; // [rsp+68h] [rbp-11h] BYREF
  VARIANTARG pvarg; // [rsp+70h] [rbp-9h] BYREF
  VARIANTARG v19; // [rsp+90h] [rbp+17h] BYREF

  *(_QWORD *)&pvarg.vt = 8;
  *(_OWORD *)&pvarg.decVal.Lo32 = (unsigned __int64)SysAllocString(
                                                      L"xmlns:plugin=\"http://schemas.microsoft.com/msus/2011/04/StoreWUAu"
                                                       "thInitialization\"");
  if ( !pvarg.llVal )
  {
    std::bad_alloc::bad_alloc((std::bad_alloc *)&v19);
    std::bad_alloc::bad_alloc(pExceptionObject, &v19);
    throw (std::bad_alloc *)pExceptionObject;
  }
  v15 = 0;
  v16 = 0;
  v2 = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60, &v16);
  if ( v2 < 0 )
  {
    sih::hr_exception::hr_exception((sih::hr_exception *)pExceptionObject, v2);
    throw (sih::hr_exception *)pExceptionObject;
  }
  v3 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v16 + 504LL))(v16, 0);
  if ( v3 < 0
    || (v3 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v16 + 544LL))(v16, 0), v3 < 0)
    || (v3 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v16 + 560LL))(v16, 0), v3 < 0)
    || (v19 = pvarg,
        v3 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, VARIANTARG *))(*(_QWORD *)v16 + 640LL))(
               v16,
               L"SelectionNamespaces",
               &v19),
        v3 < 0) )
  {
    sih::hr_exception::hr_exception((sih::hr_exception *)pExceptionObject, v3);
    throw (sih::hr_exception *)pExceptionObject;
  }
  v4 = (*(__int64 (__fastcall **)(LPVOID, wchar_t *, __int16 *))(*(_QWORD *)v16 + 520LL))(v16, a1, &v15);
  v5 = v4;
  if ( !v15 || v4 == 1 )
  {
    XInterface<IXMLDOMParseError>::__autoclassinit2(&v17);
    XInterface<IXMLDOMParseError>::XInterface<IXMLDOMParseError>(&v17);
    bstrString = 0;
    v8 = WuSmartPtr::XPtrBase<IXMLDOMDocument2,WuSmartPtr::Policies::ComInterfacePolicy<IXMLDOMDocument2>>::operator->((__int64)&v16);
    v9 = *(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 480LL);
    AddressOf = WuSmartPtr::XPtrBase<IXMLDOMParseError,WuSmartPtr::Policies::ComInterfacePolicy<IXMLDOMParseError>>::ReleaseAndGetAddressOf(&v17);
    if ( !v9(v8, AddressOf) )
    {
      v11 = WuSmartPtr::XPtrBase<IXMLDOMDocument2,WuSmartPtr::Policies::ComInterfacePolicy<IXMLDOMDocument2>>::operator->((__int64)&v17);
      (*(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v11 + 72LL))(v11, &bstrString);
    }
    SysFreeString(bstrString);
    LODWORD(ppv) = v5;
    WUTrace(0, 0, 0x400000, 1, ppv, L"Returning WU_E_REDIRECTOR_LOAD_XML after loadXML");
    sih::hr_exception::hr_exception((sih::hr_exception *)pExceptionObject, -2145103871);
    throw (sih::hr_exception *)pExceptionObject;
  }
  if ( v4 < 0 )
  {
    LODWORD(ppv) = v4;
    WUTrace(0, 0, 1, 1, ppv, L"loadXML");
    sih::hr_exception::hr_exception((sih::hr_exception *)pExceptionObject, v5);
    throw (sih::hr_exception *)pExceptionObject;
  }
  v6 = v16;
  v16 = 0;
  VariantClear(&pvarg);
  return (struct IXMLDOMDocument2 *)v6;
}

```

## disassembly

```asm
0x140029638  mov     [rsp-8+arg_8], rbx
0x14002963d  mov     [rsp-8+arg_10], rsi
0x140029642  push    rbp
0x140029643  push    rdi
0x140029644  push    r14
0x140029646  lea     rbp, [rsp-47h]
0x14002964b  sub     rsp, 0C0h
0x140029652  mov     rax, cs:__security_cookie
0x140029659  xor     rax, rsp
0x14002965c  mov     [rbp+57h+var_20], rax
0x140029660  mov     rbx, rcx
0x140029663  xorps   xmm0, xmm0
0x140029666  xor     eax, eax
0x140029668  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x14002966c  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x140029670  mov     eax, 8
0x140029675  mov     word ptr [rbp+57h+pvarg], ax
0x140029679  lea     rcx, aXmlnsPluginHtt; "xmlns:plugin=\"http://schemas.microsoft"...
0x140029680  call    cs:__imp_SysAllocString
0x140029686  mov     qword ptr [rbp+57h+pvarg+8], rax
0x14002968a  xor     r14d, r14d
0x14002968d  test    rax, rax
0x140029690  jz      loc_140029891
0x140029696  mov     [rbp+57h+var_78], r14w
0x14002969b  mov     [rbp+57h+var_70], r14
0x14002969f  lea     rax, [rbp+57h+var_70]
0x1400296a3  mov     [rsp+0D0h+ppv], rax; ppv
0x1400296a8  lea     r9, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x1400296af  xor     edx, edx; pUnkOuter
0x1400296b1  lea     r8d, [r14+1]; dwClsContext
0x1400296b5  lea     rcx, CLSID_DOMDocument60; rclsid
0x1400296bc  call    cs:__imp_CoCreateInstance
0x1400296c2  test    eax, eax
0x1400296c4  js      loc_1400298B9
0x1400296ca  xor     edx, edx
0x1400296cc  mov     rcx, [rbp+57h+var_70]
0x1400296d0  mov     rax, [rcx]
0x1400296d3  mov     rax, [rax+1F8h]
0x1400296da  call    _guard_dispatch_icall
0x1400296df  test    eax, eax
0x1400296e1  js      loc_140029875
0x1400296e7  xor     edx, edx
0x1400296e9  mov     rcx, [rbp+57h+var_70]
0x1400296ed  mov     rax, [rcx]
0x1400296f0  mov     rax, [rax+220h]
0x1400296f7  call    _guard_dispatch_icall
0x1400296fc  test    eax, eax
0x1400296fe  js      loc_140029875
0x140029704  xor     edx, edx
0x140029706  mov     rcx, [rbp+57h+var_70]
0x14002970a  mov     rax, [rcx]
0x14002970d  mov     rax, [rax+230h]
0x140029714  call    _guard_dispatch_icall
0x140029719  test    eax, eax
0x14002971b  js      loc_140029875
0x140029721  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x140029725  movaps  [rbp+57h+var_40], xmm0
0x140029729  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x14002972e  movsd   [rbp+57h+var_30], xmm1
0x140029733  mov     rcx, [rbp+57h+var_70]
0x140029737  mov     rax, [rcx]
0x14002973a  lea     r8, [rbp+57h+var_40]
0x14002973e  lea     rdx, aSelectionnames; "SelectionNamespaces"
0x140029745  mov     rax, [rax+280h]
0x14002974c  call    _guard_dispatch_icall
0x140029751  test    eax, eax
0x140029753  js      loc_140029875
0x140029759  mov     rcx, [rbp+57h+var_70]
0x14002975d  mov     rax, [rcx]
0x140029760  lea     r8, [rbp+57h+var_78]
0x140029764  mov     rdx, rbx
0x140029767  mov     rax, [rax+208h]
0x14002976e  call    _guard_dispatch_icall
0x140029773  mov     esi, eax
0x140029775  cmp     r14w, [rbp+57h+var_78]
0x14002977a  jz      short loc_1400297C2
0x14002977c  cmp     eax, 1
0x14002977f  jz      short loc_1400297C2
0x140029781  test    eax, eax
0x140029783  js      loc_1400298D5
0x140029789  mov     rbx, [rbp+57h+var_70]
0x14002978d  mov     [rbp+57h+var_70], r14
0x140029791  lea     rcx, [rbp+57h+pvarg]; pvarg
0x140029795  call    cs:__imp_VariantClear
0x14002979b  mov     rax, rbx
0x14002979e  mov     rcx, [rbp+57h+var_20]
0x1400297a2  xor     rcx, rsp; StackCookie
0x1400297a5  call    __security_check_cookie
0x1400297aa  lea     r11, [rsp+0D0h+var_10]
0x1400297b2  mov     rbx, [r11+28h]
0x1400297b6  mov     rsi, [r11+30h]
0x1400297ba  mov     rsp, r11
0x1400297bd  pop     r14
0x1400297bf  pop     rdi
0x1400297c0  pop     rbp
0x1400297c1  retn
0x1400297c2  lea     rcx, [rbp+57h+var_68]
0x1400297c6  call    ?__autoclassinit2@?$XInterface@UIXMLDOMParseError@@@@QEAAX_K@Z; XInterface<IXMLDOMParseError>::__autoclassinit2(unsigned __int64)
0x1400297cb  lea     rcx, [rbp+57h+var_68]
0x1400297cf  call    ??0?$XInterface@UIXMLDOMParseError@@@@QEAA@PEAUIXMLDOMParseError@@@Z; XInterface<IXMLDOMParseError>::XInterface<IXMLDOMParseError>(IXMLDOMParseError *)
0x1400297d4  nop
0x1400297d5  mov     [rbp+57h+bstrString], r14
0x1400297d9  lea     rcx, [rbp+57h+var_70]
0x1400297dd  call    ??C?$XPtrBase@UIXMLDOMDocument2@@U?$ComInterfacePolicy@UIXMLDOMDocument2@@@Policies@WuSmartPtr@@@WuSmartPtr@@QEAAPEAUIXMLDOMDocument2@@XZ; WuSmartPtr::XPtrBase<IXMLDOMDocument2,WuSmartPtr::Policies::ComInterfacePolicy<IXMLDOMDocument2>>::operator->(void)
0x1400297e2  mov     rdi, rax
0x1400297e5  mov     rcx, [rax]
0x1400297e8  mov     rbx, [rcx+1E0h]
0x1400297ef  lea     rcx, [rbp+57h+var_68]
0x1400297f3  call    ?ReleaseAndGetAddressOf@?$XPtrBase@UIXMLDOMParseError@@U?$ComInterfacePolicy@UIXMLDOMParseError@@@Policies@WuSmartPtr@@@WuSmartPtr@@QEAAPEAPEAUIXMLDOMParseError@@XZ; WuSmartPtr::XPtrBase<IXMLDOMParseError,WuSmartPtr::Policies::ComInterfacePolicy<IXMLDOMParseError>>::ReleaseAndGetAddressOf(void)
0x1400297f8  mov     rdx, rax
0x1400297fb  mov     rcx, rdi
0x1400297fe  mov     rax, rbx
0x140029801  call    _guard_dispatch_icall
0x140029806  test    eax, eax
0x140029808  jnz     short loc_140029829
0x14002980a  lea     rcx, [rbp+57h+var_68]
0x14002980e  call    ??C?$XPtrBase@UIXMLDOMDocument2@@U?$ComInterfacePolicy@UIXMLDOMDocument2@@@Policies@WuSmartPtr@@@WuSmartPtr@@QEAAPEAUIXMLDOMDocument2@@XZ; WuSmartPtr::XPtrBase<IXMLDOMDocument2,WuSmartPtr::Policies::ComInterfacePolicy<IXMLDOMDocument2>>::operator->(void)
0x140029813  mov     r8, rax
0x140029816  mov     rcx, [rax]
0x140029819  mov     rax, [rcx+48h]
0x14002981d  lea     rdx, [rbp+57h+bstrString]
0x140029821  mov     rcx, r8
0x140029824  call    _guard_dispatch_icall
0x140029829  mov     rcx, [rbp+57h+bstrString]; bstrString
0x14002982d  call    cs:__imp_SysFreeString
0x140029833  lea     rax, aReturningWuERe; "Returning WU_E_REDIRECTOR_LOAD_XML afte"...
0x14002983a  mov     [rsp+0D0h+var_A8], rax
0x14002983f  mov     dword ptr [rsp+0D0h+ppv], esi
0x140029843  xor     edx, edx
0x140029845  xor     ecx, ecx
0x140029847  lea     r9d, [rdx+1]
0x14002984b  mov     r8d, 400000h
0x140029851  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140029856  mov     edx, 80245001h; int
0x14002985b  lea     rcx, [rbp+57h+pExceptionObject]; this
0x14002985f  call    ??0hr_exception@sih@@QEAA@J@Z; sih::hr_exception::hr_exception(long)
0x140029864  lea     rdx, _TI3?AVhr_exception@sih@@; pThrowInfo
0x14002986b  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14002986f  call    _CxxThrowException
0x140029875  mov     edx, eax; int
0x140029877  lea     rcx, [rbp+57h+pExceptionObject]; this
0x14002987b  call    ??0hr_exception@sih@@QEAA@J@Z; sih::hr_exception::hr_exception(long)
0x140029880  lea     rdx, _TI3?AVhr_exception@sih@@; pThrowInfo
0x140029887  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14002988b  call    _CxxThrowException
0x140029891  lea     rcx, [rbp+57h+var_40]; this
0x140029895  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x14002989a  nop
0x14002989b  lea     rdx, [rbp+57h+var_40]
0x14002989f  lea     rcx, [rbp+57h+pExceptionObject]
0x1400298a3  call    ??0bad_alloc@std@@QEAA@$$QEAV01@@Z; std::bad_alloc::bad_alloc(std::bad_alloc &&)
0x1400298a8  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1400298af  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1400298b3  call    _CxxThrowException
0x1400298b9  mov     edx, eax; int
0x1400298bb  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1400298bf  call    ??0hr_exception@sih@@QEAA@J@Z; sih::hr_exception::hr_exception(long)
0x1400298c4  lea     rdx, _TI3?AVhr_exception@sih@@; pThrowInfo
0x1400298cb  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1400298cf  call    _CxxThrowException
0x1400298d5  lea     rax, aLoadxml; "loadXML"
0x1400298dc  mov     [rsp+0D0h+var_A8], rax
0x1400298e1  mov     dword ptr [rsp+0D0h+ppv], esi
0x1400298e5  xor     edx, edx
0x1400298e7  xor     ecx, ecx
0x1400298e9  lea     r9d, [rdx+1]
0x1400298ed  mov     r8d, r9d
0x1400298f0  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1400298f5  mov     edx, esi; int
0x1400298f7  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1400298fb  call    ??0hr_exception@sih@@QEAA@J@Z; sih::hr_exception::hr_exception(long)
0x140029900  lea     rdx, _TI3?AVhr_exception@sih@@; pThrowInfo
0x140029907  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14002990b  call    _CxxThrowException
```
