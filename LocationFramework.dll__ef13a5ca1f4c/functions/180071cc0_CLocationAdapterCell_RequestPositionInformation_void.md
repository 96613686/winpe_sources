# CLocationAdapterCell::RequestPositionInformation(void)

- ea: `0x180071cc0`
- end: `0x180074152`
- name: `?RequestPositionInformation@CLocationAdapterCell@@UEAAJXZ`
- size: `9362`
- prototype: `__int64 __fastcall(CLocationAdapterCell *__hidden this)`
- caller_count: `0`
- callee_count: `34`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800054c8`
- `0x180005594`
- `0x18000c974`
- `0x180012310`
- `0x180012398`
- `0x180020994`
- `0x180020c64`
- `0x18002127c`
- `0x180021450`
- `0x18003a940`
- `0x18003b92c`
- `0x180048b98`
- `0x18005ab30`
- `0x180071cc0`
- `0x18009c310`
- `0x18009db68`
- `0x1800a98c0`
- `0x1800aa5ac`
- `0x1800da040`
- `0x1800ec4fc`
- `0x1800ece3c`
- `0x1800f33f0`
- `0x180100ed0`
- `0x180101638`
- `0x1801018a8`
- `0x18010215c`
- `0x18010251c`
- `0x180102780`
- `0x180102a80`
- `0x180102d94`
- `0x180103044`
- `0x180103428`
- `0x180103480`
- `0x18015e010`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x1800724e3`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x1800724fe`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x18007289a`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x1800728b5`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x180072d4d`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x180072d68`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x1800731bd`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x1800731d8`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x180073668`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x180073689`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x180073b60`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x180073b7b`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x1800724e3`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x1800724fe`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x18007289a`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x1800728b5`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x180072d4d`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x180072d68`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x1800731bd`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x1800731d8`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x180073668`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x180073689`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x180073b60`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x180073b7b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800721ed`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800721ed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLocationAdapterCell::RequestPositionInformation(
        CLocationAdapterCell *this,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  unsigned int v5; // r12d
  const unsigned __int16 *v6; // rdx
  int v8; // ebx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, __int64 *); // rbx
  __int64 v11; // rbx
  __int64 (__fastcall *v12)(__int64, __int64 *); // rdi
  __int64 v13; // rbx
  __int64 (__fastcall *v14)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rdi
  __int64 (__fastcall ***v15)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v16)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, __int64 *); // rbx
  CellsInfoOperationHandler **v19; // rax
  CellsInfoOperationHandler *v20; // rbx
  __int64 v21; // rcx
  unsigned int v22; // edx
  int v23; // edi
  CellsInfoOperationHandler *v24; // rdi
  int v25; // esi
  __int64 v26; // r14
  __int64 (__fastcall *v27)(__int64, __int64 *); // rsi
  int v28; // eax
  __int64 v29; // r14
  __int64 (__fastcall *v30)(__int64, __int64 *); // rsi
  __int64 v31; // r13
  __int64 v32; // r14
  __int64 (__fastcall *v33)(__int64, _QWORD, __int64 *); // rsi
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // r14
  __int64 (__fastcall *v39)(__int64, __int64 *); // rsi
  __int64 v40; // r13
  unsigned int v41; // r12d
  __int64 v42; // r14
  __int64 (__fastcall *v43)(__int64, _QWORD, __int64 *); // rsi
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v48; // r14
  __int64 (__fastcall *v49)(__int64, __int64 *); // rsi
  __int64 v50; // r13
  unsigned int v51; // r12d
  __int64 v52; // r14
  __int64 (__fastcall *v53)(__int64, _QWORD, __int64 *); // rsi
  __int64 v54; // rax
  __int64 v55; // rax
  __int64 v56; // rax
  __int64 v57; // rax
  __int64 v58; // r14
  __int64 (__fastcall *v59)(__int64, __int64 *); // rsi
  __int64 v60; // r13
  unsigned int v61; // r12d
  __int64 v62; // r14
  __int64 (__fastcall *v63)(__int64, _QWORD, __int64 *); // rsi
  __int64 v64; // rax
  __int64 v65; // rax
  __int64 v66; // rax
  __int64 v67; // rax
  __int64 v68; // r14
  __int64 (__fastcall *v69)(__int64, __int64 *); // rsi
  __int64 v70; // r13
  unsigned int v71; // r12d
  __int64 v72; // r14
  __int64 (__fastcall *v73)(__int64, _QWORD, __int64 *); // rsi
  __m128i v74; // xmm6
  __int64 v75; // rax
  __int64 v76; // rax
  __int64 v77; // rax
  __int64 v78; // rax
  __int64 v79; // r14
  __int64 (__fastcall *v80)(__int64, __int64 *); // rsi
  __int64 v81; // r13
  unsigned int v82; // r12d
  __int64 v83; // r14
  __int64 (__fastcall *v84)(__int64, _QWORD, __int64 *); // rsi
  __m128i v85; // xmm6
  __int64 v86; // rax
  __int64 v87; // rax
  __int64 v88; // rax
  __int64 v89; // rax
  __int64 v90; // rsi
  __int64 v91; // rdx
  __int64 v92; // rax
  __int64 v93; // rcx
  char v94; // al
  int v95; // ecx
  int v96; // r8d
  int v97; // r9d
  struct ILocationCellBeaconInformation *v98; // r12
  __int64 v99; // rsi
  __int64 v100; // r14
  LPVOID *ppv; // [rsp+28h] [rbp-E0h]
  wil::details *v102; // [rsp+30h] [rbp-D8h]
  int v103; // [rsp+38h] [rbp-D0h]
  _QWORD v104[4]; // [rsp+68h] [rbp-A0h] BYREF
  __int128 v105; // [rsp+88h] [rbp-80h] BYREF
  __m128i v106; // [rsp+98h] [rbp-70h]
  __int128 v107; // [rsp+A8h] [rbp-60h]
  __int64 v108; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v109; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v110; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v111; // [rsp+D0h] [rbp-38h] BYREF
  struct ILocationCellBeaconInformation *v112; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v113; // [rsp+E0h] [rbp-28h] BYREF
  _QWORD v114[2]; // [rsp+E8h] [rbp-20h] BYREF
  __int128 v115; // [rsp+F8h] [rbp-10h] BYREF
  __m128i v116; // [rsp+108h] [rbp+0h]
  __int128 v117; // [rsp+118h] [rbp+10h]
  unsigned int Instance; // [rsp+128h] [rbp+20h]
  struct ILocationCellBeaconInformation *v119; // [rsp+130h] [rbp+28h] BYREF
  __int64 v120; // [rsp+138h] [rbp+30h] BYREF
  CLocationAdapterCell *v121; // [rsp+140h] [rbp+38h]
  __int64 (__fastcall ***v122)(_QWORD, GUID *, __int64 *); // [rsp+148h] [rbp+40h] BYREF
  __int64 v123; // [rsp+150h] [rbp+48h] BYREF
  __int64 v124; // [rsp+158h] [rbp+50h] BYREF
  __int64 v125; // [rsp+160h] [rbp+58h] BYREF
  __int64 v126; // [rsp+168h] [rbp+60h] BYREF
  __int64 v127; // [rsp+170h] [rbp+68h] BYREF
  struct ILocationCellBeaconInformation *v128; // [rsp+178h] [rbp+70h] BYREF
  __int64 v129; // [rsp+180h] [rbp+78h] BYREF
  __int64 v130; // [rsp+188h] [rbp+80h] BYREF
  unsigned int v131; // [rsp+190h] [rbp+88h] BYREF
  __int64 v132; // [rsp+198h] [rbp+90h] BYREF
  __int64 v133; // [rsp+1A0h] [rbp+98h] BYREF
  __int64 v134; // [rsp+1A8h] [rbp+A0h] BYREF
  __int64 v135; // [rsp+1B0h] [rbp+A8h] BYREF
  __int64 v136; // [rsp+1B8h] [rbp+B0h] BYREF
  __int64 v137; // [rsp+1C0h] [rbp+B8h] BYREF
  __int64 v138; // [rsp+1C8h] [rbp+C0h] BYREF
  unsigned int v139; // [rsp+1D0h] [rbp+C8h] BYREF
  int v140; // [rsp+1D4h] [rbp+CCh] BYREF
  _BYTE v141[16]; // [rsp+1D8h] [rbp+D0h] BYREF
  char v142[8]; // [rsp+1E8h] [rbp+E0h] BYREF
  _BYTE v143[232]; // [rsp+1F0h] [rbp+E8h] BYREF
  HSTRING string[2]; // [rsp+2D8h] [rbp+1D0h] BYREF
  __int128 v145; // [rsp+2E8h] [rbp+1E0h]
  wil::details::in1diag5 *retaddr; // [rsp+360h] [rbp+258h]

  v121 = this;
  v5 = 0;
  LODWORD(v114[0]) = 0;
  *(_OWORD *)&v104[1] = 0;
  geo::COperationPerformanceMonitor::StartOperation(
    (__int64)&v104[1],
    (__int64)L"CellScan",
    a3,
    a4,
    (__int64)ppv,
    (__int64)L"CLocationAdapterCell::RequestPositionInformation");
  v104[0] = 0;
  wil::EnterCriticalSection(v104, (char *)this + 192);
  if ( (unsigned __int8)CLocationAdapterBluetooth::RequestScan_::_1_::_lambda_1_::operator()() )
  {
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(v104);
    if ( v104[2] )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)v104[2]);
    return 2147947423LL;
  }
  if ( (unsigned int)dword_1801DDF30 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)&dword_1801DDF30,
      (unsigned __int8 *)byte_1801B1243);
  *(_OWORD *)string = 0;
  v145 = 0;
  Windows::Internal::StringReference::StringReference(string, (const unsigned __int16 (*)[57])v6);
  v126 = 0;
  v125 = 0;
  v122 = 0;
  v124 = 0;
  v123 = 0;
  v8 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Networking::NetworkOperators::IMobileBroadbandModemStatics>>(
         string[0],
         &v126);
  if ( v8 < 0 )
    goto LABEL_8;
  v9 = v126;
  v10 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v126 + 64LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v125);
  v8 = v10(v9, &v125);
  if ( v8 < 0 )
    goto LABEL_8;
  v11 = v125;
  if ( !v125 )
    goto LABEL_17;
  v12 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v125 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v123);
  v8 = v12(v11, &v123);
  if ( v8 < 0 )
  {
LABEL_8:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v123);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v124);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v122);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v125);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v126);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(v104);
    if ( v104[2] )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)v104[2]);
    return (unsigned int)v8;
  }
  v13 = v123;
  if ( !v123 )
  {
LABEL_17:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v123);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v124);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v122);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v125);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v126);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(v104);
    if ( v104[2] )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)v104[2]);
    return 1;
  }
  v14 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v123 + 72LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v122);
  v8 = v14(v13, &v122);
  if ( v8 < 0 )
    goto LABEL_8;
  if ( !v122 )
    goto LABEL_17;
  v140 = 0;
  v8 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), int *))(*v122)[7])(v122, &v140);
  if ( v8 < 0 )
    goto LABEL_8;
  if ( (unsigned int)(v140 - 3) > 2 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v123);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v124);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v122);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v125);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v126);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(v104);
    if ( v104[2] )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)v104[2]);
    return 2147942450LL;
  }
  v15 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v122;
  v16 = **v122;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v124);
  v8 = v16(v15, &GUID_33670a8a_c7ef_444c_ab6c_df7ef7a390fe, &v124);
  if ( v8 < 0 )
    goto LABEL_8;
  v130 = 0;
  v17 = v124;
  v18 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v124 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v130);
  v8 = v18(v17, &v130);
  if ( v8 < 0 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v130);
    goto LABEL_8;
  }
  v19 = (CellsInfoOperationHandler **)Microsoft::WRL::Details::Make<CellsInfoOperationHandler,>(&v120);
  v20 = *v19;
  *v19 = 0;
  v21 = v120;
  if ( v120 )
  {
    v120 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  }
  v23 = (*(__int64 (__fastcall **)(__int64, CellsInfoOperationHandler *))(*(_QWORD *)v130 + 48LL))(v130, v20);
  if ( v23 < 0 )
  {
    if ( v20 )
      (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v20 + 16LL))(v20);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v130);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v123);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v124);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v122);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v125);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v126);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(v104);
    if ( v104[2] )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)v104[2]);
    return (unsigned int)v23;
  }
  v24 = 0;
  if ( v20 )
  {
    (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v20 + 8LL))(v20);
    v24 = v20;
  }
  v25 = CellsInfoOperationHandler::WaitForResults(v24, v22);
  if ( v25 < 0 )
  {
    if ( v24 )
      (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v24 + 16LL))(v24);
    if ( v20 )
      (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v20 + 16LL))(v20);
LABEL_43:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v130);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v123);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v124);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v122);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v125);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v126);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(v104);
    if ( v104[2] )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)v104[2]);
    return (unsigned int)v25;
  }
  v129 = 0;
  v26 = v130;
  v27 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v130 + 64LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
  v25 = v27(v26, &v129);
  if ( v25 < 0 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
    if ( v24 )
      (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v24 + 16LL))(v24);
    if ( v20 )
      (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v20 + 16LL))(v20);
    goto LABEL_43;
  }
  v128 = 0;
  Instance = CoCreateInstance(
               &GUID_0a4b8f34_d725_454d_b81d_3bebe48382dc,
               0,
               1u,
               &GUID_6be074bd_d0cc_4ad2_9ac5_61798b81dd06,
               (LPVOID *)&v128);
  v112 = v128;
  if ( v128 )
    (*(void (__fastcall **)(struct ILocationCellBeaconInformation *))(*(_QWORD *)v128 + 8LL))(v128);
  v111 = v129;
  if ( v129 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v129 + 8LL))(v129);
  v28 = SetServingCell(&v111, &v112);
  v25 = v28;
  if ( v28 < 0 )
  {
    LODWORD(v102) = v28;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x289,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\celladapter\\locationcelladapter.cpp",
      "CLocationAdapterCell::RequestPositionInformation",
      "SetServingCell(cellsInfo, pCellBeaconInfo)",
      v102,
      v103);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v128);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
    if ( v24 )
      (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v24 + 16LL))(v24);
    if ( v20 )
      (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v20 + 16LL))(v20);
    goto LABEL_43;
  }
  v131 = 0;
  memset_0(v141, 0, 0xF8u);
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v141);
  v132 = 0;
  v29 = v129;
  v30 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v129 + 56LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
  v25 = v30(v29, &v132);
  if ( v25 < 0 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
    std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v141);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v128);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
    if ( v24 )
      (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v24 + 16LL))(v24);
    if ( v20 )
      (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v20 + 16LL))(v20);
    goto LABEL_43;
  }
  v25 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v132 + 56LL))(v132, &v131);
  if ( v25 < 0 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
    std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v141);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v128);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
    if ( v24 )
      (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v24 + 16LL))(v24);
    if ( v20 )
      (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v20 + 16LL))(v20);
    goto LABEL_43;
  }
  v31 = 0;
  v112 = 0;
  if ( v131 )
  {
    while ( 1 )
    {
      v127 = 0;
      v115 = 0;
      v116 = 0;
      v32 = v132;
      v33 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v132 + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v127);
      v25 = v33(v32, v5, &v127);
      if ( v25 < 0 )
        break;
      v111 = v127;
      if ( v127 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v127 + 8LL))(v127);
      v25 = TranslateGSMData(&v111, &v115);
      if ( v25 < 0 )
      {
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v127);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
        std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v141);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v128);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
        if ( v24 )
          (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v24 + 16LL))(v24);
        if ( v20 )
          (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v20 + 16LL))(v20);
        goto LABEL_43;
      }
      if ( v116.m128i_i32[1] == 0x7FFFFFFF || v116.m128i_i32[2] == 0x7FFFFFFF )
      {
        v112 = (struct ILocationCellBeaconInformation *)++v31;
      }
      else
      {
        v105 = v115;
        v106 = v116;
        v25 = (*(__int64 (__fastcall **)(struct ILocationCellBeaconInformation *, __int128 *))(*(_QWORD *)v128 + 208LL))(
                v128,
                &v105);
        if ( v25 < 0 )
        {
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v127);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
          std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v141);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v128);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
          if ( v24 )
            (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v24 + 16LL))(v24);
          if ( v20 )
            (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v20 + 16LL))(v20);
          goto LABEL_43;
        }
        if ( !v5 )
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v142, " GSM: ");
        v34 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v142, "(");
        v35 = std::basic_ostream<unsigned short>::operator<<(v34, v116.m128i_u32[1]);
        v36 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v35, ":");
        v37 = std::basic_ostream<unsigned short>::operator<<(v36, v116.m128i_u32[2]);
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v37, ")");
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v127);
      if ( ++v5 >= v131 )
        goto LABEL_87;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v127);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
    std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v141);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v128);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
    if ( v24 )
      (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v24 + 16LL))(v24);
    if ( v20 )
      (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v20 + 16LL))(v20);
    goto LABEL_43;
  }
LABEL_87:
  v133 = 0;
  v38 = v129;
  v39 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v129 + 64LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v133);
  v25 = v39(v38, &v133);
  if ( v25 < 0 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v133);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
    std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v141);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v128);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
    if ( v24 )
      (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v24 + 16LL))(v24);
    if ( v20 )
      (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v20 + 16LL))(v20);
    goto LABEL_43;
  }
  v25 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v133 + 56LL))(v133, &v131);
  if ( v25 < 0 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v133);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
    std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v141);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v128);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
    if ( v24 )
      (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v24 + 16LL))(v24);
    if ( v20 )
      (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v20 + 16LL))(v20);
    goto LABEL_43;
  }
  v40 = 0;
  v111 = 0;
  v41 = 0;
  if ( v131 )
  {
    while ( 1 )
    {
      v127 = 0;
      v105 = 0;
      v106 = 0;
      LODWORD(v107) = 0;
      v42 = v133;
      v43 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v133 + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v127);
      v25 = v43(v42, v41, &v127);
      if ( v25 < 0 )
        break;
      v110 = v127;
      if ( v127 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v127 + 8LL))(v127);
      v25 = TranslateLTEData(&v110, &v105);
      if ( v25 < 0 )
      {
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v127);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v133);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
        std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v141);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v128);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
        if ( v24 )
          (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v24 + 16LL))(v24);
        if ( v20 )
          (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v20 + 16LL))(v20);
        goto LABEL_43;
      }
      if ( HIDWORD(v105) == 0x7FFFFFFF || v106.m128i_i32[0] == 0x7FFFFFFF )
      {
        v111 = ++v40;
      }
      else
      {
        v115 = v105;
        v116 = v106;
        LODWORD(v117) = v107;
        v25 = (*(__int64 (__fastcall **)(struct ILocationCellBeaconInformation *, __int128 *))(*(_QWORD *)v128 + 224LL))(
                v128,
                &v115);
        if ( v25 < 0 )
        {
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v127);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v133);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
          std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v141);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v128);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
          if ( v24 )
            (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v24 + 16LL))(v24);
          if ( v20 )
            (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v20 + 16LL))(v20);
          goto LABEL_43;
        }
        if ( !v41 )
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v142, " LTE: ");
        v44 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v142, "(");
        v45 = std::basic_ostream<unsigned short>::operator<<(v44, HIDWORD(v105));
        v46 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v45, ":");
        v47 = std::basic_ostream<unsigned short>::operator<<(v46, v106.m128i_u32[0]);
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v47, ")");
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v127);
      if ( ++v41 >= v131 )
        goto LABEL_127;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v127);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v133);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
    std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v141);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v128);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
    if ( v24 )
      (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v24 + 16LL))(v24);
    if ( v20 )
      (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v20 + 16LL))(v20);
    goto LABEL_43;
  }
LABEL_127:
  v135 = 0;
  v25 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v129)(
          v129,
          &GUID_66205912_b89f_4e12_bbb6_d5cf09a820ca,
          &v135);
  if ( v25 < 0 )
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v135);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v133);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
    std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v141);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v128);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
    if ( v24 )
      (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v24 + 16LL))(v24);
    if ( v20 )
      (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v20 + 16LL))(v20);
    goto LABEL_43;
  }
  v134 = 0;
  v48 = v135;
  v49 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v135 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134);
  v25 = v49(v48, &v134);
  if ( v25 < 0 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v135);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v133);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
    std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v141);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v128);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
    if ( v24 )
      (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v24 + 16LL))(v24);
    if ( v20 )
      (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v20 + 16LL))(v20);
    goto LABEL_43;
  }
  v25 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v134 + 56LL))(v134, &v131);
  if ( v25 < 0 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v135);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v133);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
    std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v141);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v128);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
    if ( v24 )
      (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v24 + 16LL))(v24);
    if ( v20 )
      (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v20 + 16LL))(v20);
    goto LABEL_43;
  }
  v50 = 0;
  v110 = 0;
  v51 = 0;
  if ( v131 )
  {
    while ( 1 )
    {
      v127 = 0;
      v105 = 0;
      v106 = 0;
      *(_QWORD *)&v107 = 0;
      v52 = v134;
      v53 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v134 + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v127);
      v25 = v53(v52, v51, &v127);
      if ( v25 < 0 )
        break;
      v109 = v127;
      if ( v127 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v127 + 8LL))(v127);
      v25 = TranslateNRData(&v109, &v105);
      if ( v25 < 0 )
      {
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v127);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v135);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v133);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
        std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v141);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v128);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
        if ( v24 )
          (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v24 + 16LL))(v24);
        if ( v20 )
          (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v20 + 16LL))(v20);
        goto LABEL_43;
      }
      if ( v106.m128i_i32[0] == 0x7FFFFFFF || v106.m128i_i32[1] == 0x7FFFFFFF )
      {
        v110 = ++v50;
      }
      else
      {
        v115 = v105;
        v116 = v106;
        *(_QWORD *)&v117 = v107;
        v25 = (*(__int64 (__fastcall **)(struct ILocationCellBeaconInformation *, __int128 *))(*(_QWORD *)v128 + 240LL))(
                v128,
                &v115);
        if ( v25 < 0 )
        {
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v127);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v135);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v133);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
          std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v141);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v128);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
          if ( v24 )
            (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v24 + 16LL))(v24);
          if ( v20 )
            (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v20 + 16LL))(v20);
          goto LABEL_43;
        }
        if ( !v51 )
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v142, " NR: ");
        v54 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v142, "(");
        v55 = std::basic_ostream<unsigned short>::operator<<(v54, v106.m128i_u32[0]);
        v56 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v55, ":");
        v57 = std::basic_ostream<unsigned short>::operator<<(v56, v106.m128i_u32[1]);
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v57, ")");
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v127);
      if ( ++v51 >= v131 )
        goto LABEL_173;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v127);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v135);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v133);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
    std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v141);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v128);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
    if ( v24 )
      (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v24 + 16LL))(v24);
    if ( v20 )
      (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v20 + 16LL))(v20);
    goto LABEL_43;
  }
LABEL_173:
  v136 = 0;
  v58 = v129;
  v59 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v129 + 80LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v136);
  v25 = v59(v58, &v136);
  if ( v25 < 0 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v136);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v135);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v133);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
    std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v141);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v128);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
    if ( v24 )
      (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v24 + 16LL))(v24);
    if ( v20 )
      (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v20 + 16LL))(v20);
    goto LABEL_43;
  }
  v25 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v136 + 56LL))(v136, &v131);
  if ( v25 < 0 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v136);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v135);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v133);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
    std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v141);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v128);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
    if ( v24 )
      (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v24 + 16LL))(v24);
    if ( v20 )
      (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v20 + 16LL))(v20);
    goto LABEL_43;
  }
  v60 = 0;
  v109 = 0;
  v61 = 0;
  if ( v131 )
  {
    while ( 1 )
    {
      v127 = 0;
      v105 = 0;
      v106 = 0;
      v107 = 0;
      v62 = v136;
      v63 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v136 + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v127);
      v25 = v63(v62, v61, &v127);
      if ( v25 < 0 )
        break;
      v108 = v127;
      if ( v127 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v127 + 8LL))(v127);
      v25 = TranslateUMTSData(&v108, &v105);
      if ( v25 < 0 )
      {
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v127);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v136);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v135);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v133);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
        std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v141);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v128);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
        if ( v24 )
          (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v24 + 16LL))(v24);
        if ( v20 )
          (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v20 + 16LL))(v20);
        goto LABEL_43;
      }
      if ( v106.m128i_i32[3] == 0x7FFFFFFF || (_DWORD)v107 == 0x7FFFFFFF )
      {
        v109 = ++v60;
      }
      else
      {
        v115 = v105;
        v116 = v106;
        v117 = v107;
        v25 = (*(__int64 (__fastcall **)(struct ILocationCellBeaconInformation *, __int128 *))(*(_QWORD *)v128 + 256LL))(
                v128,
                &v115);
        if ( v25 < 0 )
        {
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v127);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v136);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v135);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v133);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
          std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v141);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v128);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
          if ( v24 )
            (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v24 + 16LL))(v24);
          if ( v20 )
            (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v20 + 16LL))(v20);
          goto LABEL_43;
        }
        if ( !v61 )
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v142, " UMTS: ");
        v64 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v142, "(");
        v65 = std::basic_ostream<unsigned short>::operator<<(v64, v106.m128i_u32[3]);
        v66 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v65, ":");
        v67 = std::basic_ostream<unsigned short>::operator<<(v66, (unsigned int)v107);
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v67, ")");
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v127);
      if ( ++v61 >= v131 )
        goto LABEL_213;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v127);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v136);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v135);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v133);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
    std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v141);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v128);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
    if ( v24 )
      (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v24 + 16LL))(v24);
    if ( v20 )
      (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v20 + 16LL))(v20);
    goto LABEL_43;
  }
LABEL_213:
  v137 = 0;
  v68 = v129;
  v69 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v129 + 72LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v137);
  v25 = v69(v68, &v137);
  if ( v25 < 0 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v137);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v136);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v135);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v133);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
    std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v141);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v128);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
    if ( v24 )
      (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v24 + 16LL))(v24);
    if ( v20 )
      (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v20 + 16LL))(v20);
    goto LABEL_43;
  }
  v25 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v137 + 56LL))(v137, &v131);
  if ( v25 < 0 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v137);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v136);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v135);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v133);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
    std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v141);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v128);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
    if ( v24 )
      (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v24 + 16LL))(v24);
    if ( v20 )
      (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v20 + 16LL))(v20);
    goto LABEL_43;
  }
  v70 = 0;
  v108 = 0;
  v71 = 0;
  if ( v131 )
  {
    while ( 1 )
    {
      v127 = 0;
      v105 = 0;
      v106 = 0;
      LODWORD(v107) = 0;
      v72 = v137;
      v73 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v137 + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v127);
      v25 = v73(v72, v71, &v127);
      if ( v25 < 0 )
        break;
      v113 = v127;
      if ( v127 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v127 + 8LL))(v127);
      v25 = TranslateTDSCDMAData(&v113, &v105);
      if ( v25 < 0 )
      {
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v127);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v137);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v136);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v135);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v133);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
        std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v141);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v128);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
        if ( v24 )
          (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v24 + 16LL))(v24);
        if ( v20 )
          (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v20 + 16LL))(v20);
        goto LABEL_43;
      }
      if ( v106.m128i_i32[0] == 0x7FFFFFFF || HIDWORD(v105) == 0x7FFFFFFF )
      {
        v108 = ++v70;
      }
      else
      {
        v115 = v105;
        v74 = v106;
        v116 = v106;
        LODWORD(v117) = v107;
        v25 = (*(__int64 (__fastcall **)(struct ILocationCellBeaconInformation *, __int128 *))(*(_QWORD *)v128 + 272LL))(
                v128,
                &v115);
        if ( v25 < 0 )
        {
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v127);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v137);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v136);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v135);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v133);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
          std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v141);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v128);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
          if ( v24 )
            (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v24 + 16LL))(v24);
          if ( v20 )
            (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v20 + 16LL))(v20);
          goto LABEL_43;
        }
        if ( !v71 )
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v142, " TDSCDMA: ");
        v75 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v142, "(");
        v76 = std::basic_ostream<unsigned short>::operator<<(v75, v106.m128i_u32[0]);
        v77 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v76, ":");
        v78 = std::basic_ostream<unsigned short>::operator<<(
                v77,
                (unsigned int)_mm_cvtsi128_si32(_mm_srli_si128(v74, 4)));
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v78, ")");
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v127);
      if ( ++v71 >= v131 )
        goto LABEL_253;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v127);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v137);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v136);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v135);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v133);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
    std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v141);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v128);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
    if ( v24 )
      (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v24 + 16LL))(v24);
    if ( v20 )
      (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v20 + 16LL))(v20);
    goto LABEL_43;
  }
LABEL_253:
  v138 = 0;
  v79 = v129;
  v80 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v129 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v138);
  v25 = v80(v79, &v138);
  if ( v25 < 0 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v138);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v137);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v136);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v135);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v133);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
    std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v141);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v128);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
    if ( v24 )
      (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v24 + 16LL))(v24);
    if ( v20 )
      (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v20 + 16LL))(v20);
    goto LABEL_43;
  }
  v25 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v138 + 56LL))(v138, &v131);
  if ( v25 < 0 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v138);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v137);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v136);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v135);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v133);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
    std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v141);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v128);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
    if ( v24 )
      (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v24 + 16LL))(v24);
    if ( v20 )
      (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v20 + 16LL))(v20);
    goto LABEL_43;
  }
  v81 = 0;
  v82 = 0;
  if ( v131 )
  {
    while ( 1 )
    {
      v127 = 0;
      v105 = 0;
      v106 = 0;
      LODWORD(v107) = 0;
      v83 = v138;
      v84 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v138 + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v127);
      v25 = v84(v83, v82, &v127);
      if ( v25 < 0 )
        break;
      v113 = v127;
      if ( v127 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v127 + 8LL))(v127);
      v25 = TranslateCDMAData(&v113, &v105);
      if ( v25 < 0 )
      {
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v127);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v138);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v137);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v136);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v135);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v133);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
        std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v141);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v128);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
        if ( v24 )
          (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v24 + 16LL))(v24);
        if ( v20 )
          (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v20 + 16LL))(v20);
        goto LABEL_43;
      }
      if ( DWORD2(v105) == 0x7FFFFFFF || DWORD1(v105) == 0x7FFFFFFF || (_DWORD)v105 == 0x7FFFFFFF )
      {
        ++v81;
      }
      else
      {
        v115 = v105;
        v85 = v106;
        v116 = v106;
        LODWORD(v117) = v107;
        v25 = (*(__int64 (__fastcall **)(struct ILocationCellBeaconInformation *, __int128 *))(*(_QWORD *)v128 + 288LL))(
                v128,
                &v115);
        if ( v25 < 0 )
        {
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v127);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v138);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v137);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v136);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v135);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v133);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
          std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v141);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v128);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
          if ( v24 )
            (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v24 + 16LL))(v24);
          if ( v20 )
            (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v20 + 16LL))(v20);
          goto LABEL_43;
        }
        if ( !v82 )
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v142, " CDMA: ");
        v86 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v142, "(");
        v87 = std::basic_ostream<unsigned short>::operator<<(
                v86,
                (unsigned int)_mm_cvtsi128_si32(_mm_srli_si128(v85, 4)));
        v88 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v87, ":");
        v89 = std::basic_ostream<unsigned short>::operator<<(v88, DWORD2(v105));
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v89, ")");
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v127);
      if ( ++v82 >= v131 )
        goto LABEL_294;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v127);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v138);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v137);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v136);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v135);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v133);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
    std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v141);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v128);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
    if ( v24 )
      (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v24 + 16LL))(v24);
    if ( v20 )
      (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v20 + 16LL))(v20);
    goto LABEL_43;
  }
LABEL_294:
  std::basic_stringbuf<unsigned short>::str(v143, &v105);
  v90 = v106.m128i_i64[0];
  std::wstring::_Tidy_deallocate(&v105);
  if ( v90 )
  {
    if ( byte_1801E39C1 >= 0 )
    {
      v94 = v114[0];
    }
    else
    {
      std::basic_stringbuf<unsigned short>::str(v143, &v105);
      v92 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v105, v91);
      McTemplateU0z_EventWriteTransfer(v93, CellNeighbors, v92);
      v94 = 1;
    }
    if ( (v94 & 1) != 0 )
      std::wstring::_Tidy_deallocate(&v105);
  }
  v139 = 0;
  (*(void (__fastcall **)(struct ILocationCellBeaconInformation *, unsigned int *))(*(_QWORD *)v128 + 24LL))(
    v128,
    &v139);
  if ( (unsigned int)dword_1801DDF30 <= 5 )
  {
    v99 = v108;
    v100 = v109;
    v98 = (struct ILocationCellBeaconInformation *)v110;
  }
  else
  {
    v113 = v139;
    v98 = (struct ILocationCellBeaconInformation *)v110;
    v127 = v81;
    v99 = v108;
    v100 = v109;
    v114[0] = v111;
    v119 = v112;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
      v95,
      (unsigned int)&byte_1801B13C7,
      v96,
      v97,
      (__int64)&v119,
      (__int64)v114,
      (__int64)&v109,
      (__int64)&v108,
      (__int64)&v127,
      (__int64)&v110,
      (__int64)&v113);
  }
  if ( (unsigned int)dword_1801DDF30 > 5 )
  {
    LODWORD(v114[0]) = v139;
    v119 = v98;
    v113 = v81;
    v110 = v99;
    v109 = v100;
    v108 = 1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v95,
      (unsigned int)byte_1801B12EB,
      v96,
      (unsigned int)&v108,
      (__int64)&v112,
      (__int64)&v111,
      (__int64)&v109,
      (__int64)&v110,
      (__int64)&v113,
      (__int64)&v119,
      (__int64)v114);
  }
  v25 = (*(__int64 (__fastcall **)(struct ILocationCellBeaconInformation *))(*(_QWORD *)v128 + 296LL))(v128);
  if ( v25 < 0 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v138);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v137);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v136);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v135);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v133);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
    std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v141);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v128);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
    if ( v24 )
      (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v24 + 16LL))(v24);
    if ( v20 )
      (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v20 + 16LL))(v20);
    goto LABEL_43;
  }
  CLocationAdapterCell::NotifyAllSinks(v121, v128);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v138);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v137);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v136);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v135);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v133);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v141);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v128);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
  if ( v24 )
    (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v24 + 16LL))(v24);
  if ( v20 )
    (*(void (__fastcall **)(CellsInfoOperationHandler *))(*(_QWORD *)v20 + 16LL))(v20);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v130);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v123);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v124);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v122);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v125);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v126);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(v104);
  if ( v104[2] )
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)v104[2]);
  return Instance;
}

```

## disassembly

```asm
0x180071cc0  mov     rax, rsp
0x180071cc3  push    rbp
0x180071cc4  push    rbx
0x180071cc5  push    rsi
0x180071cc6  push    rdi
0x180071cc7  push    r12
0x180071cc9  push    r13
0x180071ccb  push    r14
0x180071ccd  push    r15
0x180071ccf  lea     rbp, [rax-258h]
0x180071cd6  sub     rsp, 318h
0x180071cdd  movaps  xmmword ptr [rax-58h], xmm6
0x180071ce1  mov     rax, cs:__security_cookie
0x180071ce8  xor     rax, rsp
0x180071ceb  mov     [rbp+250h+var_60], rax
0x180071cf2  mov     rbx, rcx
0x180071cf5  mov     [rbp+250h+var_218], rcx
0x180071cf9  xor     r12d, r12d
0x180071cfc  mov     dword ptr [rbp+250h+var_270], r12d
0x180071d00  xorps   xmm0, xmm0
0x180071d03  movups  xmmword ptr [rsp+350h+var_2F0+8], xmm0
0x180071d08  lea     rax, aClocationadapt_8; "CLocationAdapterCell::RequestPositionIn"...
0x180071d0f  mov     [rsp+350h+var_328], rax
0x180071d14  lea     rdx, aCellscan; "CellScan"
0x180071d1b  lea     rcx, [rsp+350h+var_2F0+8]
0x180071d20  call    ?StartOperation@COperationPerformanceMonitor@geo@@SA?AV?$shared_ptr@VOperationPerformanceCookie@geo@@@std@@PEBGIP6AJAEBQEBU_tlgProvider_t@@0H0@Z10@Z; geo::COperationPerformanceMonitor::StartOperation(ushort const *,uint,long (*)(_tlgProvider_t const * const &,ushort const *,int,ushort const *),_tlgProvider_t const * const &,ushort const *)
0x180071d25  mov     qword ptr [rsp+350h+var_2F0], r12
0x180071d2a  lea     rdx, [rbx+0C0h]
0x180071d31  lea     rcx, [rsp+350h+var_2F0]
0x180071d36  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180071d3b  call    _CLocationAdapterBluetooth__RequestScan____1____lambda_1___operator__
0x180071d40  test    al, al
0x180071d42  jz      short loc_180071D67
0x180071d44  lea     rcx, [rsp+350h+var_2F0]
0x180071d49  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x180071d4e  mov     rcx, qword ptr [rsp+350h+var_2F0+10h]; this
0x180071d53  test    rcx, rcx
0x180071d56  jz      short loc_180071D5D
0x180071d58  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180071d5d  mov     eax, 8007139Fh
0x180071d62  jmp     loc_180074127
0x180071d67  mov     eax, cs:dword_1801DDF30
0x180071d6d  cmp     eax, 5
0x180071d70  jbe     short loc_180071D85
0x180071d72  lea     rdx, byte_1801B1243
0x180071d79  lea     rcx, dword_1801DDF30
0x180071d80  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180071d85  xorps   xmm0, xmm0
0x180071d88  movups  xmmword ptr [rbp+250h+string], xmm0
0x180071d8f  movups  [rbp+250h+var_70], xmm0
0x180071d96  lea     rcx, [rbp+250h+string]; string
0x180071d9d  call    ??$?0$0DJ@@StringReference@Internal@Windows@@QEAA@AEAY0DJ@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[57])
0x180071da2  mov     [rbp+250h+var_1F0], r12
0x180071da6  mov     [rbp+250h+var_1F8], r12
0x180071daa  mov     [rbp+250h+var_210], r12
0x180071dae  mov     [rbp+250h+var_200], r12
0x180071db2  mov     [rbp+250h+var_208], r12
0x180071db6  lea     rdx, [rbp+250h+var_1F0]
0x180071dba  mov     rcx, [rbp+250h+string]
0x180071dc1  call    ??$GetActivationFactory@V?$ComPtr@UIMobileBroadbandModemStatics@NetworkOperators@Networking@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIMobileBroadbandModemStatics@NetworkOperators@Networking@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Networking::NetworkOperators::IMobileBroadbandModemStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Networking::NetworkOperators::IMobileBroadbandModemStatics>>)
0x180071dc6  mov     ebx, eax
0x180071dc8  test    eax, eax
0x180071dca  jns     short loc_180071E19
0x180071dcc  lea     rcx, [rbp+250h+var_208]
0x180071dd0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180071dd5  lea     rcx, [rbp+250h+var_200]
0x180071dd9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180071dde  lea     rcx, [rbp+250h+var_210]
0x180071de2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180071de7  lea     rcx, [rbp+250h+var_1F8]
0x180071deb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180071df0  lea     rcx, [rbp+250h+var_1F0]
0x180071df4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180071df9  lea     rcx, [rsp+350h+var_2F0]
0x180071dfe  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x180071e03  mov     rcx, qword ptr [rsp+350h+var_2F0+10h]; this
0x180071e08  test    rcx, rcx
0x180071e0b  jz      short loc_180071E12
0x180071e0d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180071e12  mov     eax, ebx
0x180071e14  jmp     loc_180074127
0x180071e19  mov     rdi, [rbp+250h+var_1F0]
0x180071e1d  mov     rax, [rdi]
0x180071e20  mov     rbx, [rax+40h]
0x180071e24  lea     rcx, [rbp+250h+var_1F8]
0x180071e28  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180071e2d  lea     rdx, [rbp+250h+var_1F8]
0x180071e31  mov     rcx, rdi
0x180071e34  mov     rax, rbx
0x180071e37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071e3c  mov     ebx, eax
0x180071e3e  test    eax, eax
0x180071e40  js      short loc_180071DCC
0x180071e42  mov     rbx, [rbp+250h+var_1F8]
0x180071e46  lea     rcx, [rbp+250h+var_208]
0x180071e4a  test    rbx, rbx
0x180071e4d  jz      short loc_180071EB3
0x180071e4f  mov     rax, [rbx]
0x180071e52  mov     rdi, [rax+30h]
0x180071e56  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180071e5b  lea     rdx, [rbp+250h+var_208]
0x180071e5f  mov     rcx, rbx
0x180071e62  mov     rax, rdi
0x180071e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071e6a  mov     ebx, eax
0x180071e6c  test    eax, eax
0x180071e6e  js      loc_180071DCC
0x180071e74  mov     rbx, [rbp+250h+var_208]
0x180071e78  test    rbx, rbx
0x180071e7b  jz      short loc_180071EAF
0x180071e7d  mov     rax, [rbx]
0x180071e80  mov     rdi, [rax+48h]
0x180071e84  lea     rcx, [rbp+250h+var_210]
0x180071e88  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180071e8d  lea     rdx, [rbp+250h+var_210]
0x180071e91  mov     rcx, rbx
0x180071e94  mov     rax, rdi
0x180071e97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071e9c  mov     ebx, eax
0x180071e9e  test    eax, eax
0x180071ea0  js      loc_180071DCC
0x180071ea6  mov     rcx, [rbp+250h+var_210]
0x180071eaa  test    rcx, rcx
0x180071ead  jnz     short loc_180071EFF
0x180071eaf  lea     rcx, [rbp+250h+var_208]
0x180071eb3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180071eb8  lea     rcx, [rbp+250h+var_200]
0x180071ebc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180071ec1  lea     rcx, [rbp+250h+var_210]
0x180071ec5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180071eca  lea     rcx, [rbp+250h+var_1F8]
0x180071ece  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180071ed3  lea     rcx, [rbp+250h+var_1F0]
0x180071ed7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180071edc  lea     rcx, [rsp+350h+var_2F0]
0x180071ee1  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x180071ee6  mov     rcx, qword ptr [rsp+350h+var_2F0+10h]; this
0x180071eeb  test    rcx, rcx
0x180071eee  jz      short loc_180071EF5
0x180071ef0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180071ef5  mov     eax, 1
0x180071efa  jmp     loc_180074127
0x180071eff  mov     [rbp+250h+var_184], r12d
0x180071f06  mov     rax, [rcx]
0x180071f09  lea     rdx, [rbp+250h+var_184]
0x180071f10  mov     rax, [rax+38h]
0x180071f14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071f19  mov     ebx, eax
0x180071f1b  test    eax, eax
0x180071f1d  js      loc_180071DCC
0x180071f23  mov     eax, [rbp+250h+var_184]
0x180071f29  add     eax, 0FFFFFFFDh
0x180071f2c  cmp     eax, 2
0x180071f2f  jbe     short loc_180071F81
0x180071f31  lea     rcx, [rbp+250h+var_208]
0x180071f35  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180071f3a  lea     rcx, [rbp+250h+var_200]
0x180071f3e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180071f43  lea     rcx, [rbp+250h+var_210]
0x180071f47  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180071f4c  lea     rcx, [rbp+250h+var_1F8]
0x180071f50  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180071f55  lea     rcx, [rbp+250h+var_1F0]
0x180071f59  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180071f5e  lea     rcx, [rsp+350h+var_2F0]
0x180071f63  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x180071f68  mov     rcx, qword ptr [rsp+350h+var_2F0+10h]; this
0x180071f6d  test    rcx, rcx
0x180071f70  jz      short loc_180071F77
0x180071f72  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180071f77  mov     eax, 80070032h
0x180071f7c  jmp     loc_180074127
0x180071f81  mov     rbx, [rbp+250h+var_210]
0x180071f85  mov     rax, [rbx]
0x180071f88  mov     rdi, [rax]
0x180071f8b  lea     rcx, [rbp+250h+var_200]
0x180071f8f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180071f94  lea     r8, [rbp+250h+var_200]
0x180071f98  lea     rdx, _GUID_33670a8a_c7ef_444c_ab6c_df7ef7a390fe
0x180071f9f  mov     rcx, rbx
0x180071fa2  mov     rax, rdi
0x180071fa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071faa  mov     ebx, eax
0x180071fac  test    eax, eax
0x180071fae  js      loc_180071DCC
0x180071fb4  mov     [rbp+250h+var_1D0], r12
0x180071fbb  mov     rdi, [rbp+250h+var_200]
0x180071fbf  mov     rax, [rdi]
0x180071fc2  mov     rbx, [rax+30h]
0x180071fc6  lea     rcx, [rbp+250h+var_1D0]
0x180071fcd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180071fd2  lea     rdx, [rbp+250h+var_1D0]
0x180071fd9  mov     rcx, rdi
0x180071fdc  mov     rax, rbx
0x180071fdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071fe4  mov     ebx, eax
0x180071fe6  test    eax, eax
0x180071fe8  jns     short loc_180071FFB
0x180071fea  lea     rcx, [rbp+250h+var_1D0]
0x180071ff1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180071ff6  jmp     loc_180071DCC
0x180071ffb  lea     rcx, [rbp+250h+var_220]
0x180071fff  call    ??$Make@VCellsInfoOperationHandler@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCellsInfoOperationHandler@@@12@XZ; Microsoft::WRL::Details::Make<CellsInfoOperationHandler,>(void)
0x180072004  mov     rbx, [rax]
0x180072007  mov     [rax], r12
0x18007200a  mov     rcx, [rbp+250h+var_220]
0x18007200e  test    rcx, rcx
0x180072011  jz      short loc_180072024
0x180072013  mov     [rbp+250h+var_220], r12
0x180072017  mov     rax, [rcx]
0x18007201a  mov     rax, [rax+10h]
0x18007201e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072023  nop
0x180072024  mov     rcx, [rbp+250h+var_1D0]
0x18007202b  mov     rax, [rcx]
0x18007202e  mov     rdx, rbx
0x180072031  mov     rax, [rax+30h]
0x180072035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007203a  mov     edi, eax
0x18007203c  test    eax, eax
0x18007203e  jns     short loc_1800720AE
0x180072040  test    rbx, rbx
0x180072043  jz      short loc_180072055
0x180072045  mov     rcx, [rbx]
0x180072048  mov     rax, [rcx+10h]
0x18007204c  mov     rcx, rbx
0x18007204f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072054  nop
0x180072055  lea     rcx, [rbp+250h+var_1D0]
0x18007205c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180072061  lea     rcx, [rbp+250h+var_208]
0x180072065  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007206a  lea     rcx, [rbp+250h+var_200]
0x18007206e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180072073  lea     rcx, [rbp+250h+var_210]
0x180072077  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007207c  lea     rcx, [rbp+250h+var_1F8]
0x180072080  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180072085  lea     rcx, [rbp+250h+var_1F0]
0x180072089  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007208e  lea     rcx, [rsp+350h+var_2F0]
0x180072093  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x180072098  mov     rcx, qword ptr [rsp+350h+var_2F0+10h]; this
0x18007209d  test    rcx, rcx
0x1800720a0  jz      short loc_1800720A7
0x1800720a2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800720a7  mov     eax, edi
0x1800720a9  jmp     loc_180074127
0x1800720ae  mov     rdi, r12
0x1800720b1  test    rbx, rbx
0x1800720b4  jz      short loc_1800720C9
0x1800720b6  mov     rax, [rbx]
0x1800720b9  mov     rcx, rbx
0x1800720bc  mov     rax, [rax+8]
0x1800720c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800720c5  nop
0x1800720c6  mov     rdi, rbx
0x1800720c9  mov     rcx, rdi; this
0x1800720cc  call    ?WaitForResults@CellsInfoOperationHandler@@QEAAJK@Z; CellsInfoOperationHandler::WaitForResults(ulong)
0x1800720d1  mov     esi, eax
0x1800720d3  test    eax, eax
0x1800720d5  jns     loc_18007215E
0x1800720db  test    rdi, rdi
0x1800720de  jz      short loc_1800720F0
0x1800720e0  mov     rcx, [rdi]
0x1800720e3  mov     rax, [rcx+10h]
0x1800720e7  mov     rcx, rdi
0x1800720ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800720ef  nop
0x1800720f0  test    rbx, rbx
0x1800720f3  jz      short loc_180072105
0x1800720f5  mov     rax, [rbx]
0x1800720f8  mov     rcx, rbx
0x1800720fb  mov     rax, [rax+10h]
0x1800720ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072104  nop
0x180072105  lea     rcx, [rbp+250h+var_1D0]
0x18007210c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180072111  lea     rcx, [rbp+250h+var_208]
0x180072115  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007211a  lea     rcx, [rbp+250h+var_200]
0x18007211e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180072123  lea     rcx, [rbp+250h+var_210]
0x180072127  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007212c  lea     rcx, [rbp+250h+var_1F8]
0x180072130  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180072135  lea     rcx, [rbp+250h+var_1F0]
0x180072139  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007213e  lea     rcx, [rsp+350h+var_2F0]
0x180072143  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x180072148  mov     rcx, qword ptr [rsp+350h+var_2F0+10h]; this
0x18007214d  test    rcx, rcx
0x180072150  jz      short loc_180072157
0x180072152  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180072157  mov     eax, esi
0x180072159  jmp     loc_180074127
0x18007215e  mov     [rbp+250h+var_1D8], r12
0x180072162  mov     r14, [rbp+250h+var_1D0]
0x180072169  mov     rax, [r14]
0x18007216c  mov     rsi, [rax+40h]
  ... truncated ...
```
