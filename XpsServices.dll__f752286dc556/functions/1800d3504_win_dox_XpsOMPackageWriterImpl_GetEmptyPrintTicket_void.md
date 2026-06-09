# win_dox::XpsOMPackageWriterImpl::GetEmptyPrintTicket(void)

- ea: `0x1800d3504`
- end: `0x1800d3a86`
- name: `?GetEmptyPrintTicket@XpsOMPackageWriterImpl@win_dox@@AEAAAEBVXpsOMPrintTicketResource@2@XZ`
- size: `1410`
- prototype: `const struct win_dox::XpsOMPrintTicketResource *__fastcall(win_dox::XpsOMPackageWriterImpl *__hidden this)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180053854`

## callees

- `0x1800041b0`
- `0x180005664`
- `0x1800062d0`
- `0x18000c480`
- `0x180012450`
- `0x18001f2e8`
- `0x180021e94`
- `0x18002ba0c`
- `0x18002c088`
- `0x180054068`
- `0x180061a68`
- `0x1800a9bd8`
- `0x1800bdd28`
- `0x1800bed64`
- `0x1800c06bc`
- `0x1800c1178`
- `0x1800c20c4`
- `0x1800c3244`
- `0x1800d3504`
- `0x18011b44c`
- `0x180134b70`
- `0x1801355e4`
- `0x1801359ce`
- `0x1801c7010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800d3773`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800d3773`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d3594`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d3594`

## string_xrefs

- `0x1800d35b7`: `Call to CoCreateInstance failed with HResult 0x%X.`
- `0x1800d384e`: `Call to Write failed with HResult 0x%X.`
- `0x1800d3643`: `CompactGuid`
- `0x1800d3925`: `Call to CreatePrintTicketResource failed with HResult 0x%X.`
- `0x1800d3796`: `Call to CreateStreamOnHGlobal failed with HResult 0x%X.`
- `0x1800d36de`: `Call to CreatePartUri failed with HResult 0x%X.`
- `0x1800d360f`: `/Metadata/Empty_PT_%{CompactGuid}.xml`
- `0x1800d37ee`: `<?xml version="1.0" encoding="UTF-8"?><psf:PrintTicket xmlns:psf="http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" version="1" xmlns:psk="http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords"/>`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
const struct win_dox::XpsOMPrintTicketResource *__fastcall win_dox::XpsOMPackageWriterImpl::GetEmptyPrintTicket(
        win_dox::XpsOMPackageWriterImpl *this)
{
  __int64 *v1; // rsi
  int v2; // ebx
  HRESULT v3; // ebx
  __int64 GuidAsCompactString; // rbx
  LPVOID v5; // rdi
  __int64 v6; // rbx
  _QWORD *v7; // rdx
  int v8; // ebx
  _QWORD *v9; // rax
  HRESULT v10; // ebx
  const char *v11; // rdi
  unsigned int v12; // ebx
  int v13; // r14d
  LPVOID v14; // rdi
  __int64 v15; // rbx
  _QWORD *Interface; // rax
  int v17; // ebx
  _QWORD *v18; // rax
  const struct win_dox::XpsOMPrintTicketResource *v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v24; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v25; // [rsp+48h] [rbp-B8h] BYREF
  LPSTREAM ppstm; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v27; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v28; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v30[3]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v31; // [rsp+88h] [rbp-78h] BYREF
  __int64 v32; // [rsp+90h] [rbp-70h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  _BYTE v34[40]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v35[40]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v36[5]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+120h] [rbp+20h] BYREF
  wchar_t v38[512]; // [rsp+1C0h] [rbp+C0h] BYREF

  v1 = (__int64 *)((char *)this + 16);
  v2 = -1;
  if ( *(_QWORD *)win_dox::XpsOMPath::GetInterface((char *)this + 16, &v24) )
    v2 = dword_180229450;
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  if ( v2 == -1 )
  {
    ppv = 0;
    v3 = CoCreateInstance(
           &GUID_e974d26d_3d9b_4d47_88cc_3872f2dc3585,
           0,
           1u,
           &GUID_f9b2a685_a50d_4fc2_b764_b56e093ea0ca,
           &ppv);
    if ( v3 < 0 )
    {
      memset_0(v38, 0, sizeof(v38));
      StringCchPrintfW(v38, 0x200u, L"Call to CoCreateInstance failed with HResult 0x%X.", (unsigned int)v3);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::THResultException *)pExceptionObject,
        0x193u,
        v3,
        (__int64)v38);
      throw (SplException::THResultException *)pExceptionObject;
    }
    std::wstring::wstring(v34, L"/Metadata/Empty_PT_%{CompactGuid}.xml");
    win_musl::Formatter::Formatter(v35, v34);
    std::wstring::_Tidy_deallocate(v34);
    GuidAsCompactString = win_musl::GetGuidAsCompactString(&v31);
    std::wstring::wstring(v34, L"CompactGuid");
    win_musl::Formatter::insert<std::wstring>(v35, v34, GuidAsCompactString);
    std::wstring::_Tidy_deallocate(v34);
    std::wstring::_Tidy_deallocate(&v31);
    v28 = 0;
    v5 = ppv;
    v6 = *(_QWORD *)ppv;
    win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(
      &v28,
      0);
    v28 = 0;
    win_musl::Formatter::gather((win_musl::Formatter *)v35);
    v7 = v36;
    if ( v36[3] > 7u )
      v7 = (_QWORD *)v36[0];
    v8 = (*(__int64 (__fastcall **)(LPVOID, _QWORD *, __int64 *))(v6 + 304))(v5, v7, &v28);
    if ( v8 < 0 )
    {
      memset_0(v38, 0, sizeof(v38));
      StringCchPrintfW(v38, 0x200u, L"Call to CreatePartUri failed with HResult 0x%X.", (unsigned int)v8);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::THResultException *)pExceptionObject,
        0x1A4u,
        v8,
        (__int64)v38);
      throw (SplException::THResultException *)pExceptionObject;
    }
    v9 = (_QWORD *)win_scope::scope<IXpsOMResource *,win_scope::const_policies<win_scope::com_policies>>::scope<IXpsOMResource *,win_scope::const_policies<win_scope::com_policies>>(
                     &v24,
                     &v28);
    win_dox::OpcPartUri::OpcPartUri(v30, v9);
    ppstm = 0;
    win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(
      &ppstm,
      0);
    ppstm = 0;
    v10 = CreateStreamOnHGlobal(0, 1, &ppstm);
    if ( v10 < 0 )
    {
      memset_0(v38, 0, sizeof(v38));
      StringCchPrintfW(v38, 0x200u, L"Call to CreateStreamOnHGlobal failed with HResult 0x%X.", (unsigned int)v10);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::THResultException *)pExceptionObject,
        0x1B5u,
        v10,
        (__int64)v38);
      throw (SplException::THResultException *)pExceptionObject;
    }
    v11 = "<?xml version=\"1.0\" encoding=\"UTF-8\"?><psf:PrintTicket xmlns:psf=\"http://schemas.microsoft.com/windows/20"
          "03/08/printing/printschemaframework\" xmlns:xsi=\"http://www.w3.org/2001/XMLSchema-instance\" xmlns:xsd=\"http"
          "://www.w3.org/2001/XMLSchema\" version=\"1\" xmlns:psk=\"http://schemas.microsoft.com/windows/2003/08/printing"
          "/printschemakeywords\"/>";
    v12 = 340;
    v25 = 0;
    while ( v12 )
    {
      v13 = (*(__int64 (__fastcall **)(LPSTREAM, const char *, _QWORD, unsigned int *))(*(_QWORD *)ppstm + 32LL))(
              ppstm,
              v11,
              v12,
              &v25);
      if ( v13 < 0 )
      {
        memset_0(v38, 0, sizeof(v38));
        StringCchPrintfW(v38, 0x200u, L"Call to Write failed with HResult 0x%X.", (unsigned int)v13);
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::THResultException *)pExceptionObject,
          0x1C4u,
          v13,
          (__int64)v38);
        throw (SplException::THResultException *)pExceptionObject;
      }
      v11 += v25;
      v12 -= v25;
    }
    v27 = 0;
    v14 = ppv;
    v15 = *(_QWORD *)ppv;
    win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(
      &v27,
      0);
    v27 = 0;
    Interface = (_QWORD *)win_dox::OpcPartUri::GetInterface(v30, &v24);
    v17 = (*(__int64 (__fastcall **)(LPVOID, LPSTREAM, _QWORD, __int64 *))(v15 + 224))(v14, ppstm, *Interface, &v27);
    if ( v24 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    if ( v17 < 0 )
    {
      memset_0(v38, 0, sizeof(v38));
      StringCchPrintfW(v38, 0x200u, L"Call to CreatePrintTicketResource failed with HResult 0x%X.", (unsigned int)v17);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::THResultException *)pExceptionObject,
        0x1D7u,
        v17,
        (__int64)v38);
      throw (SplException::THResultException *)pExceptionObject;
    }
    v18 = (_QWORD *)win_scope::scope<IXpsOMCanvas *,win_scope::const_policies<win_scope::com_policies>>::scope<IXpsOMCanvas *,win_scope::const_policies<win_scope::com_policies>>(
                      &v24,
                      &v27);
    v19 = (const struct win_dox::XpsOMPrintTicketResource *)win_dox::XpsOMDocumentStructureResource::XpsOMDocumentStructureResource(
                                                              (__int64)v34,
                                                              v18);
    win_dox::XpsOMPrintTicketResource::XpsOMPrintTicketResource((win_dox::XpsOMPrintTicketResource *)&v31, v19);
    v20 = *v1;
    *v1 = v31;
    v31 = v20;
    v21 = v1[1];
    v1[1] = v32;
    v32 = v21;
    v22 = v1[2];
    v1[2] = v33;
    v33 = v22;
    win_dox::XpsOMSolidColorBrush::~XpsOMSolidColorBrush((win_dox::XpsOMSolidColorBrush *)&v31);
    win_dox::XpsOMSolidColorBrush::~XpsOMSolidColorBrush((win_dox::XpsOMSolidColorBrush *)v34);
    if ( v27 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      v27 = 0;
    }
    if ( ppstm )
    {
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
      ppstm = 0;
    }
    win_dox::consumption_helper::XpsDocumentRelationshipSender<win_dox::xps_production::XpsProducerConsumptionClientTraits>::~XpsDocumentRelationshipSender<win_dox::xps_production::XpsProducerConsumptionClientTraits>((win_dox::OpcUri *)v30);
    if ( v28 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      v28 = 0;
    }
    win_musl::Formatter::~Formatter((win_musl::Formatter *)v35);
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return (const struct win_dox::XpsOMPrintTicketResource *)v1;
}

```

## disassembly

```asm
0x1800d3504  push    rbp
0x1800d3506  push    rbx
0x1800d3507  push    rsi
0x1800d3508  push    rdi
0x1800d3509  push    r14
0x1800d350b  push    r15
0x1800d350d  lea     rbp, [rsp-4D8h]
0x1800d3515  sub     rsp, 5D8h
0x1800d351c  mov     rax, cs:__security_cookie
0x1800d3523  xor     rax, rsp
0x1800d3526  mov     [rbp+500h+var_40], rax
0x1800d352d  lea     rsi, [rcx+10h]
0x1800d3531  lea     rdx, [rsp+600h+var_5C0]
0x1800d3536  mov     rcx, rsi
0x1800d3539  call    ?GetInterface@XpsOMPath@win_dox@@QEBA?AV?$scope@PEAUIXpsOMPath@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::XpsOMPath::GetInterface(void)
0x1800d353e  or      ebx, 0FFFFFFFFh
0x1800d3541  xor     r15d, r15d
0x1800d3544  cmp     [rax], r15
0x1800d3547  cmovnz  ebx, cs:dword_180229450
0x1800d354e  mov     rcx, [rsp+600h+var_5C0]
0x1800d3553  test    rcx, rcx
0x1800d3556  jz      short loc_1800D3565
0x1800d3558  mov     rax, [rcx]
0x1800d355b  mov     rax, [rax+10h]
0x1800d355f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3564  nop
0x1800d3565  cmp     ebx, 0FFFFFFFFh
0x1800d3568  jnz     loc_1800D3A64
0x1800d356e  mov     [rsp+600h+var_598], r15
0x1800d3573  lea     rax, [rsp+600h+var_598]
0x1800d3578  mov     [rsp+600h+ppv], rax; ppv
0x1800d357d  lea     r9, _GUID_f9b2a685_a50d_4fc2_b764_b56e093ea0ca; riid
0x1800d3584  lea     r14d, [rbx+2]
0x1800d3588  mov     r8d, r14d; dwClsContext
0x1800d358b  xor     edx, edx; pUnkOuter
0x1800d358d  lea     rcx, _GUID_e974d26d_3d9b_4d47_88cc_3872f2dc3585; rclsid
0x1800d3594  call    cs:__imp_CoCreateInstance
0x1800d359a  mov     ebx, eax
0x1800d359c  test    eax, eax
0x1800d359e  jns     short loc_1800D360F
0x1800d35a0  xor     edx, edx; Val
0x1800d35a2  mov     r8d, 400h; Size
0x1800d35a8  lea     rcx, [rbp+500h+var_440]; void *
0x1800d35af  call    memset_0
0x1800d35b4  mov     r9d, ebx
0x1800d35b7  lea     r8, aCallToCocreate_1; "Call to CoCreateInstance failed with HR"...
0x1800d35be  mov     edx, 200h; unsigned __int64
0x1800d35c3  lea     rcx, [rbp+500h+var_440]; wchar_t *
0x1800d35ca  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800d35cf  lea     rax, [rbp+500h+var_440]
0x1800d35d6  mov     [rsp+600h+var_5D0], rax; __int64
0x1800d35db  mov     [rsp+600h+var_5D8], ebx; int
0x1800d35df  mov     dword ptr [rsp+600h+ppv], 193h; unsigned int
0x1800d35e7  lea     r9, Src
0x1800d35ee  lea     r8, aNoFilename; "(no filename)"
0x1800d35f5  lea     rcx, [rbp+500h+pExceptionObject]; this
0x1800d35f9  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800d35fe  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800d3605  lea     rcx, [rbp+500h+pExceptionObject]; pExceptionObject
0x1800d3609  call    _CxxThrowException_0
0x1800d360f  lea     rdx, aMetadataEmptyP; "/Metadata/Empty_PT_%{CompactGuid}.xml"
0x1800d3616  lea     rcx, [rbp+500h+var_558]
0x1800d361a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800d361f  nop
0x1800d3620  lea     rdx, [rbp+500h+var_558]
0x1800d3624  lea     rcx, [rbp+500h+var_530]
0x1800d3628  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x1800d362d  nop
0x1800d362e  lea     rcx, [rbp+500h+var_558]
0x1800d3632  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800d3637  lea     rcx, [rbp+500h+var_578]
0x1800d363b  call    ?GetGuidAsCompactString@win_musl@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; win_musl::GetGuidAsCompactString(void)
0x1800d3640  mov     rbx, rax
0x1800d3643  lea     rdx, aCompactguid; "CompactGuid"
0x1800d364a  lea     rcx, [rbp+500h+var_558]
0x1800d364e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800d3653  nop
0x1800d3654  mov     r8, rbx
0x1800d3657  lea     rdx, [rbp+500h+var_558]
0x1800d365b  lea     rcx, [rbp+500h+var_530]
0x1800d365f  call    ??$insert@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Formatter@win_musl@@QEAAAEAV01@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z; win_musl::Formatter::insert<std::wstring>(std::wstring const &,std::wstring const &)
0x1800d3664  nop
0x1800d3665  lea     rcx, [rbp+500h+var_558]
0x1800d3669  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800d366e  nop
0x1800d366f  lea     rcx, [rbp+500h+var_578]
0x1800d3673  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800d3678  mov     [rsp+600h+var_5A0], r15
0x1800d367d  mov     rdi, [rsp+600h+var_598]
0x1800d3682  mov     rbx, [rdi]
0x1800d3685  xor     edx, edx
0x1800d3687  lea     rcx, [rsp+600h+var_5A0]
0x1800d368c  call    ?reset@?$scope_helper@PEAUIXpsPageRelationshipCollection@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEAUIXpsPageRelationshipCollection@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@3@PEAUIXpsPageRelationshipCollection@@@Z; win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(win_scope::scope<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>> &,IXpsPageRelationshipCollection *)
0x1800d3691  mov     [rsp+600h+var_5A0], r15
0x1800d3696  lea     rcx, [rbp+500h+var_530]; this
0x1800d369a  call    ?gather@Formatter@win_musl@@QEAAXXZ; win_musl::Formatter::gather(void)
0x1800d369f  lea     rdx, [rbp+500h+var_508]
0x1800d36a3  cmp     [rbp+500h+var_4F0], 7
0x1800d36a8  cmova   rdx, [rbp+500h+var_508]
0x1800d36ad  lea     r8, [rsp+600h+var_5A0]
0x1800d36b2  mov     rcx, rdi
0x1800d36b5  mov     rax, [rbx+130h]
0x1800d36bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d36c1  mov     ebx, eax
0x1800d36c3  test    eax, eax
0x1800d36c5  jns     short loc_1800D3736
0x1800d36c7  xor     edx, edx; Val
0x1800d36c9  mov     r8d, 400h; Size
0x1800d36cf  lea     rcx, [rbp+500h+var_440]; void *
0x1800d36d6  call    memset_0
0x1800d36db  mov     r9d, ebx
0x1800d36de  lea     r8, aCallToCreatepa; "Call to CreatePartUri failed with HResu"...
0x1800d36e5  mov     edx, 200h; unsigned __int64
0x1800d36ea  lea     rcx, [rbp+500h+var_440]; wchar_t *
0x1800d36f1  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800d36f6  lea     rax, [rbp+500h+var_440]
0x1800d36fd  mov     [rsp+600h+var_5D0], rax; __int64
0x1800d3702  mov     [rsp+600h+var_5D8], ebx; int
0x1800d3706  mov     dword ptr [rsp+600h+ppv], 1A4h; unsigned int
0x1800d370e  lea     r9, Src
0x1800d3715  lea     r8, aNoFilename; "(no filename)"
0x1800d371c  lea     rcx, [rbp+500h+pExceptionObject]; this
0x1800d3720  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800d3725  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800d372c  lea     rcx, [rbp+500h+pExceptionObject]; pExceptionObject
0x1800d3730  call    _CxxThrowException_0
0x1800d3736  lea     rdx, [rsp+600h+var_5A0]
0x1800d373b  lea     rcx, [rsp+600h+var_5C0]
0x1800d3740  call    ??0?$scope@PEAUIXpsOMResource@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@QEAA@AEBV01@@Z; win_scope::scope<IXpsOMResource *,win_scope::const_policies<win_scope::com_policies>>::scope<IXpsOMResource *,win_scope::const_policies<win_scope::com_policies>>(win_scope::scope<IXpsOMResource *,win_scope::const_policies<win_scope::com_policies>> const &)
0x1800d3745  mov     rdx, rax
0x1800d3748  lea     rcx, [rsp+600h+var_590]
0x1800d374d  call    ??$?0V?$scope@PEAUIOpcPartUri@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@@OpcPartUri@win_dox@@QEAA@V?$scope@PEAUIOpcPartUri@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_dox::OpcPartUri::OpcPartUri(win_scope::scope<IOpcPartUri *,win_scope::const_policies<win_scope::com_policies>>)
0x1800d3752  nop
0x1800d3753  mov     [rsp+600h+ppstm], r15
0x1800d3758  xor     edx, edx
0x1800d375a  lea     rcx, [rsp+600h+ppstm]
0x1800d375f  call    ?reset@?$scope_helper@PEAUIXpsPageRelationshipCollection@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEAUIXpsPageRelationshipCollection@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@3@PEAUIXpsPageRelationshipCollection@@@Z; win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(win_scope::scope<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>> &,IXpsPageRelationshipCollection *)
0x1800d3764  mov     [rsp+600h+ppstm], r15
0x1800d3769  lea     r8, [rsp+600h+ppstm]; ppstm
0x1800d376e  mov     edx, r14d; fDeleteOnRelease
0x1800d3771  xor     ecx, ecx; hGlobal
0x1800d3773  call    cs:__imp_CreateStreamOnHGlobal
0x1800d3779  mov     ebx, eax
0x1800d377b  test    eax, eax
0x1800d377d  jns     short loc_1800D37EE
0x1800d377f  xor     edx, edx; Val
0x1800d3781  mov     r8d, 400h; Size
0x1800d3787  lea     rcx, [rbp+500h+var_440]; void *
0x1800d378e  call    memset_0
0x1800d3793  mov     r9d, ebx
0x1800d3796  lea     r8, aCallToCreatest_0; "Call to CreateStreamOnHGlobal failed wi"...
0x1800d379d  mov     edx, 200h; unsigned __int64
0x1800d37a2  lea     rcx, [rbp+500h+var_440]; wchar_t *
0x1800d37a9  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800d37ae  lea     rax, [rbp+500h+var_440]
0x1800d37b5  mov     [rsp+600h+var_5D0], rax; __int64
0x1800d37ba  mov     [rsp+600h+var_5D8], ebx; int
0x1800d37be  mov     dword ptr [rsp+600h+ppv], 1B5h; unsigned int
0x1800d37c6  lea     r9, Src
0x1800d37cd  lea     r8, aNoFilename; "(no filename)"
0x1800d37d4  lea     rcx, [rbp+500h+pExceptionObject]; this
0x1800d37d8  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800d37dd  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800d37e4  lea     rcx, [rbp+500h+pExceptionObject]; pExceptionObject
0x1800d37e8  call    _CxxThrowException_0
0x1800d37ee  lea     rdi, aXmlVersion10En; "<?xml version=\"1.0\" encoding=\"UTF-8"...
0x1800d37f5  mov     ebx, 154h
0x1800d37fa  mov     [rsp+600h+var_5B8], r15d
0x1800d37ff  test    ebx, ebx
0x1800d3801  jz      loc_1800D38A7
0x1800d3807  mov     rcx, [rsp+600h+ppstm]
0x1800d380c  mov     rax, [rcx]
0x1800d380f  lea     r9, [rsp+600h+var_5B8]
0x1800d3814  mov     r8d, ebx
0x1800d3817  mov     rdx, rdi
0x1800d381a  mov     rax, [rax+20h]
0x1800d381e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3823  mov     r14d, eax
0x1800d3826  test    eax, eax
0x1800d3828  js      short loc_1800D3837
0x1800d382a  mov     eax, [rsp+600h+var_5B8]
0x1800d382e  add     rdi, rax
0x1800d3831  sub     ebx, [rsp+600h+var_5B8]
0x1800d3835  jmp     short loc_1800D37FF
0x1800d3837  xor     edx, edx; Val
0x1800d3839  mov     r8d, 400h; Size
0x1800d383f  lea     rcx, [rbp+500h+var_440]; void *
0x1800d3846  call    memset_0
0x1800d384b  mov     r9d, r14d
0x1800d384e  lea     r8, aCallToWriteFai; "Call to Write failed with HResult 0x%X."
0x1800d3855  mov     edx, 200h; unsigned __int64
0x1800d385a  lea     rcx, [rbp+500h+var_440]; wchar_t *
0x1800d3861  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800d3866  lea     rax, [rbp+500h+var_440]
0x1800d386d  mov     [rsp+600h+var_5D0], rax; __int64
0x1800d3872  mov     [rsp+600h+var_5D8], r14d; int
0x1800d3877  mov     dword ptr [rsp+600h+ppv], 1C4h; unsigned int
0x1800d387f  lea     r9, Src
0x1800d3886  lea     r8, aNoFilename; "(no filename)"
0x1800d388d  lea     rcx, [rbp+500h+pExceptionObject]; this
0x1800d3891  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800d3896  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800d389d  lea     rcx, [rbp+500h+pExceptionObject]; pExceptionObject
0x1800d38a1  call    _CxxThrowException_0
0x1800d38a7  mov     [rsp+600h+var_5A8], r15
0x1800d38ac  mov     rdi, [rsp+600h+var_598]
0x1800d38b1  mov     rbx, [rdi]
0x1800d38b4  xor     edx, edx
0x1800d38b6  lea     rcx, [rsp+600h+var_5A8]
0x1800d38bb  call    ?reset@?$scope_helper@PEAUIXpsPageRelationshipCollection@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEAUIXpsPageRelationshipCollection@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@3@PEAUIXpsPageRelationshipCollection@@@Z; win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(win_scope::scope<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>> &,IXpsPageRelationshipCollection *)
0x1800d38c0  mov     [rsp+600h+var_5A8], r15
0x1800d38c5  lea     rdx, [rsp+600h+var_5C0]
0x1800d38ca  lea     rcx, [rsp+600h+var_590]
0x1800d38cf  call    ?GetInterface@OpcPartUri@win_dox@@QEBA?AV?$scope@PEAUIOpcPartUri@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::OpcPartUri::GetInterface(void)
0x1800d38d4  nop
0x1800d38d5  lea     r9, [rsp+600h+var_5A8]
0x1800d38da  mov     r8, [rax]
0x1800d38dd  mov     rdx, [rsp+600h+ppstm]
0x1800d38e2  mov     rcx, rdi
0x1800d38e5  mov     rax, [rbx+0E0h]
0x1800d38ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d38f1  mov     ebx, eax
0x1800d38f3  mov     rcx, [rsp+600h+var_5C0]
0x1800d38f8  test    rcx, rcx
0x1800d38fb  jz      short loc_1800D390A
0x1800d38fd  mov     rdx, [rcx]
0x1800d3900  mov     rax, [rdx+10h]
0x1800d3904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3909  nop
0x1800d390a  test    ebx, ebx
0x1800d390c  jns     short loc_1800D397D
0x1800d390e  xor     edx, edx; Val
0x1800d3910  mov     r8d, 400h; Size
0x1800d3916  lea     rcx, [rbp+500h+var_440]; void *
0x1800d391d  call    memset_0
0x1800d3922  mov     r9d, ebx
0x1800d3925  lea     r8, aCallToCreatepr; "Call to CreatePrintTicketResource faile"...
0x1800d392c  mov     edx, 200h; unsigned __int64
0x1800d3931  lea     rcx, [rbp+500h+var_440]; wchar_t *
0x1800d3938  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800d393d  lea     rax, [rbp+500h+var_440]
0x1800d3944  mov     [rsp+600h+var_5D0], rax; __int64
0x1800d3949  mov     [rsp+600h+var_5D8], ebx; int
0x1800d394d  mov     dword ptr [rsp+600h+ppv], 1D7h; unsigned int
0x1800d3955  lea     r9, Src
0x1800d395c  lea     r8, aNoFilename; "(no filename)"
0x1800d3963  lea     rcx, [rbp+500h+pExceptionObject]; this
0x1800d3967  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800d396c  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800d3973  lea     rcx, [rbp+500h+pExceptionObject]; pExceptionObject
0x1800d3977  call    _CxxThrowException_0
0x1800d397d  lea     rdx, [rsp+600h+var_5A8]
0x1800d3982  lea     rcx, [rsp+600h+var_5C0]
0x1800d3987  call    ??0?$scope@PEAUIXpsOMCanvas@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@QEAA@AEBV01@@Z; win_scope::scope<IXpsOMCanvas *,win_scope::const_policies<win_scope::com_policies>>::scope<IXpsOMCanvas *,win_scope::const_policies<win_scope::com_policies>>(win_scope::scope<IXpsOMCanvas *,win_scope::const_policies<win_scope::com_policies>> const &)
0x1800d398c  mov     rdx, rax
0x1800d398f  lea     rcx, [rbp+500h+var_558]
0x1800d3993  call    ??$?0V?$scope@PEAUIXpsOMDocumentStructureResource@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@@XpsOMDocumentStructureResource@win_dox@@QEAA@V?$scope@PEAUIXpsOMDocumentStructureResource@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_dox::XpsOMDocumentStructureResource::XpsOMDocumentStructureResource(win_scope::scope<IXpsOMDocumentStructureResource *,win_scope::const_policies<win_scope::com_policies>>)
0x1800d3998  nop
0x1800d3999  mov     rdx, rax; struct win_dox::XpsOMPrintTicketResource *
0x1800d399c  lea     rcx, [rbp+500h+var_578]; this
0x1800d39a0  call    ??0XpsOMPrintTicketResource@win_dox@@QEAA@AEBV01@@Z; win_dox::XpsOMPrintTicketResource::XpsOMPrintTicketResource(win_dox::XpsOMPrintTicketResource const &)
0x1800d39a5  mov     rcx, [rsi]
0x1800d39a8  mov     rax, [rbp+500h+var_578]
0x1800d39ac  mov     [rsi], rax
0x1800d39af  mov     [rbp+500h+var_578], rcx
0x1800d39b3  mov     rcx, [rsi+8]
0x1800d39b7  mov     rax, [rbp+500h+var_570]
0x1800d39bb  mov     [rsi+8], rax
0x1800d39bf  mov     [rbp+500h+var_570], rcx
0x1800d39c3  mov     rcx, [rsi+10h]
0x1800d39c7  mov     rax, [rbp+500h+var_568]
0x1800d39cb  mov     [rsi+10h], rax
0x1800d39cf  mov     [rbp+500h+var_568], rcx
0x1800d39d3  lea     rcx, [rbp+500h+var_578]; this
0x1800d39d7  call    ??1XpsOMSolidColorBrush@win_dox@@QEAA@XZ; win_dox::XpsOMSolidColorBrush::~XpsOMSolidColorBrush(void)
0x1800d39dc  nop
0x1800d39dd  lea     rcx, [rbp+500h+var_558]; this
0x1800d39e1  call    ??1XpsOMSolidColorBrush@win_dox@@QEAA@XZ; win_dox::XpsOMSolidColorBrush::~XpsOMSolidColorBrush(void)
0x1800d39e6  nop
0x1800d39e7  mov     rcx, [rsp+600h+var_5A8]
0x1800d39ec  test    rcx, rcx
0x1800d39ef  jz      short loc_1800D3A02
0x1800d39f1  mov     rax, [rcx]
0x1800d39f4  mov     rax, [rax+10h]
0x1800d39f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d39fd  mov     [rsp+600h+var_5A8], r15
0x1800d3a02  mov     rcx, [rsp+600h+ppstm]
0x1800d3a07  test    rcx, rcx
0x1800d3a0a  jz      short loc_1800D3A1D
0x1800d3a0c  mov     rax, [rcx]
0x1800d3a0f  mov     rax, [rax+10h]
0x1800d3a13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3a18  mov     [rsp+600h+ppstm], r15
0x1800d3a1d  lea     rcx, [rsp+600h+var_590]; this
0x1800d3a22  call    ??1?$XpsDocumentRelationshipSender@VXpsProducerConsumptionClientTraits@xps_production@win_dox@@@consumption_helper@win_dox@@QEAA@XZ; win_dox::consumption_helper::XpsDocumentRelationshipSender<win_dox::xps_production::XpsProducerConsumptionClientTraits>::~XpsDocumentRelationshipSender<win_dox::xps_production::XpsProducerConsumptionClientTraits>(void)
0x1800d3a27  nop
0x1800d3a28  mov     rcx, [rsp+600h+var_5A0]
0x1800d3a2d  test    rcx, rcx
0x1800d3a30  jz      short loc_1800D3A43
0x1800d3a32  mov     rax, [rcx]
  ... truncated ...
```
