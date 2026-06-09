# InjectTools(ulong,ATL::CComPtr<IDispatch> &)

- ea: `0x180014740`
- end: `0x1800152a8`
- name: `?InjectTools@@YAHKAEAV?$CComPtr@UIDispatch@@@ATL@@@Z`
- size: `2920`
- prototype: `__int64 __fastcall(DWORD dwProcessId, BPT **)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180013a90`

## callees

- `0x180001800`
- `0x180002678`
- `0x180002b60`
- `0x180002d44`
- `0x180002dd4`
- `0x1800030dc`
- `0x180003338`
- `0x180003880`
- `0x180004144`
- `0x180004360`
- `0x1800045b4`
- `0x180014740`
- `0x180016710`
- `0x18002f108`
- `0x1800306dc`
- `0x180030ad4`
- `0x1800325d0`
- `0x180032aa4`
- `0x180035010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180014c63`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180014c63`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800148e6`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800148e6`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x180014956`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x180014991`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x1800149a8`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x1800149bf`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x1800149d6`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x180014956`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x180014991`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x1800149a8`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x1800149bf`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x1800149d6`
- `KERNEL32!CloseHandle` at `0x180014d8c`
- `KERNEL32!CloseHandle` at `0x180014e70`
- `KERNEL32!CloseHandle` at `0x180014f96`
- `KERNEL32!CloseHandle` at `0x180014d8c`
- `KERNEL32!CloseHandle` at `0x180014e70`
- `KERNEL32!CloseHandle` at `0x180014f96`
- `KERNEL32!OpenProcess` at `0x180014cc3`
- `KERNEL32!OpenProcess` at `0x180014cc3`
- `KERNEL32!LocalFree` at `0x1800148ce`
- `KERNEL32!LocalFree` at `0x1800148ce`
- `ole32!CoCreateInstance` at `0x180014d15`
- `ole32!CoCreateInstance` at `0x180014d15`
- `SHELL32!CommandLineToArgvW` at `0x180014836`
- `SHELL32!CommandLineToArgvW` at `0x180014836`

## string_xrefs

- `0x1800147af`: `F12App.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall InjectTools(DWORD dwProcessId, BPT **a2)
{
  struct _GUID *v4; // rbx
  struct IDispatch *v5; // rdx
  const unsigned __int16 *v6; // r9
  unsigned int v7; // edi
  LPWSTR *v8; // rsi
  int i; // edi
  _QWORD *v10; // rdx
  unsigned int v11; // eax
  void (*v12)(void); // rax
  int v13; // eax
  void *v14; // r13
  int v15; // eax
  unsigned __int16 *v16; // rdi
  const wchar_t **v17; // rax
  int v18; // esi
  _QWORD *v19; // rdx
  _QWORD *v20; // rdx
  __int64 v21; // rax
  _QWORD *v22; // rdx
  __int64 v23; // rdi
  const wchar_t **v24; // rax
  int v25; // esi
  _QWORD *v26; // rdx
  unsigned __int16 *v27; // rdx
  __int64 v28; // rax
  _QWORD *v29; // rdx
  __int64 v30; // r14
  LPWSTR *v31; // rdi
  HRESULT v32; // esi
  __int64 v33; // rsi
  int v34; // r15d
  unsigned __int16 *v35; // rdx
  _QWORD *v37; // rdx
  unsigned __int16 *v38; // rdx
  unsigned __int16 *v39; // r15
  _QWORD *v40; // rdx
  unsigned __int16 *v41; // rdx
  _QWORD *v42; // rdx
  unsigned __int8 *Data4; // rdx
  void **v44; // [rsp+28h] [rbp-D8h]
  LPVOID ppv; // [rsp+60h] [rbp-A0h] BYREF
  struct _GUID v46; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v47; // [rsp+78h] [rbp-88h] BYREF
  __int128 v48; // [rsp+80h] [rbp-80h] BYREF
  __int64 v49; // [rsp+90h] [rbp-70h]
  __int64 v50; // [rsp+98h] [rbp-68h] BYREF
  __int64 v51; // [rsp+A0h] [rbp-60h] BYREF
  struct _GUID *v52; // [rsp+A8h] [rbp-58h] BYREF
  int v53; // [rsp+B0h] [rbp-50h]
  int v54; // [rsp+B4h] [rbp-4Ch]
  int v55; // [rsp+B8h] [rbp-48h]
  int v56; // [rsp+BCh] [rbp-44h]
  int v57; // [rsp+C0h] [rbp-40h]
  unsigned int v58; // [rsp+C4h] [rbp-3Ch]
  LPWSTR *v59; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v60[36]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR CmdLine[262]; // [rsp+F4h] [rbp-Ch] BYREF

  v52 = (struct _GUID *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  F12::GetRootF12Directory(&v52);
  if ( (int)v52[-1].Data1 <= 0 )
  {
    Data4 = v52[-2].Data4;
    if ( _InterlockedDecrement((volatile signed __int32 *)v52[-1].Data4) <= 0 )
    {
      v12 = *(void (**)(void))(**(_QWORD **)Data4 + 8LL);
      goto LABEL_142;
    }
    return 0xFFFFFFFFLL;
  }
  Win32Helpers::OurPathAppend(&v52, L"F12App.dll");
  *(_QWORD *)&v46.Data1 = 0;
  v4 = v52;
  if ( BPT::CoCreateUsingDiagnosticsMode(*a2, v5, v52, v6, &v46, v44) )
  {
    if ( *(_QWORD *)&v46.Data1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v46.Data1 + 16LL))(*(_QWORD *)&v46.Data1);
LABEL_17:
    if ( _InterlockedDecrement((volatile signed __int32 *)v4[-1].Data4) <= 0 )
    {
      v12 = *(void (**)(void))(**(_QWORD **)v4[-2].Data4 + 8LL);
LABEL_142:
      v12();
      return 0xFFFFFFFFLL;
    }
    return 0xFFFFFFFFLL;
  }
  memset_0(v60, 0, 0x22Cu);
  v7 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _BYTE *))(**(_QWORD **)&v46.Data1 + 64LL))(
         *(_QWORD *)&v46.Data1,
         101,
         0,
         v60);
  if ( v7 )
  {
    if ( *(_QWORD *)&v46.Data1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v46.Data1 + 16LL))(*(_QWORD *)&v46.Data1);
    if ( _InterlockedDecrement((volatile signed __int32 *)v4[-1].Data4) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v4[-2].Data4 + 8LL))(*(_QWORD *)v4[-2].Data4);
    return v7;
  }
  *(_DWORD *)v46.Data4 = 0;
  v48 = 0;
  v49 = 0;
  v8 = CommandLineToArgvW(CmdLine, (int *)v46.Data4);
  v59 = v8;
  if ( !v8 )
  {
    std::vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::~vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>(&v48);
    if ( *(_QWORD *)&v46.Data1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v46.Data1 + 16LL))(*(_QWORD *)&v46.Data1);
    if ( _InterlockedDecrement((volatile signed __int32 *)v4[-1].Data4) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v4[-2].Data4 + 8LL))(*(_QWORD *)v4[-2].Data4);
    return 2147549183LL;
  }
  for ( i = 0; i < *(int *)v46.Data4; ++i )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &ppv,
      v8[i]);
    if ( *((_QWORD *)&v48 + 1) == v49 )
    {
      std::vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::_Emplace_reallocate<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const &>(
        &v48,
        *((_QWORD *)&v48 + 1),
        &ppv);
    }
    else
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        *((_QWORD *)&v48 + 1),
        &ppv);
      *((_QWORD *)&v48 + 1) += 8LL;
    }
    v10 = (char *)ppv - 24;
    if ( _InterlockedDecrement((volatile signed __int32 *)ppv - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 8LL))(*v10);
  }
  LocalFree(v8);
  if ( *(int *)v46.Data4 < 8 )
  {
    std::vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::~vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>(&v48);
    if ( *(_QWORD *)&v46.Data1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v46.Data1 + 16LL))(*(_QWORD *)&v46.Data1);
    goto LABEL_17;
  }
  v11 = _o__wtoi(*(_QWORD *)v48);
  v58 = v11;
  if ( v11 - 1 > 0x7FFFFFFD && v11 < 0x80000001 )
  {
    std::vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::~vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>(&v48);
    if ( *(_QWORD *)&v46.Data1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v46.Data1 + 16LL))(*(_QWORD *)&v46.Data1);
    goto LABEL_17;
  }
  v13 = wcstol(*(const wchar_t **)(v48 + 8), 0, 16);
  v14 = (void *)v13;
  if ( !v13 || v13 == 0x7FFFFFFF || v13 == 0x80000000 )
  {
    std::vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::~vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>(&v48);
    if ( *(_QWORD *)&v46.Data1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v46.Data1 + 16LL))(*(_QWORD *)&v46.Data1);
    goto LABEL_17;
  }
  v56 = wcstol(*(const wchar_t **)(v48 + 16), 0, 16);
  v55 = wcstol(*(const wchar_t **)(v48 + 24), 0, 16);
  v54 = wcstol(*(const wchar_t **)(v48 + 32), 0, 16);
  v15 = wcstol(*(const wchar_t **)(v48 + 40), 0, 16);
  v53 = v15;
  if ( !v15 || v15 == 0x7FFFFFFF || v15 == 0x80000000 )
  {
    std::vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::~vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>(&v48);
    if ( *(_QWORD *)&v46.Data1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v46.Data1 + 16LL))(*(_QWORD *)&v46.Data1);
    goto LABEL_17;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v47,
    v48 + 48);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v50,
    v48 + 56);
  v16 = v47;
  if ( *((int *)v47 - 4) < 4 )
  {
    v42 = (_QWORD *)(v50 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v50 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v42 + 8LL))(*v42);
    if ( _InterlockedDecrement((volatile signed __int32 *)v16 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v16 - 3) + 8LL))(*((_QWORD *)v16 - 3));
    std::vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::~vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>(&v48);
    if ( *(_QWORD *)&v46.Data1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v46.Data1 + 16LL))(*(_QWORD *)&v46.Data1);
    goto LABEL_17;
  }
  v17 = (const wchar_t **)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Left(
                            &v47,
                            &ppv,
                            4);
  v18 = wcscmp_0(*v17, L"/id:");
  v19 = (char *)ppv - 24;
  if ( _InterlockedDecrement((volatile signed __int32 *)ppv - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v19 + 8LL))(*v19);
  if ( v18 )
  {
    v20 = (_QWORD *)(v50 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v50 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v20 + 8LL))(*v20);
    if ( _InterlockedDecrement((volatile signed __int32 *)v16 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v16 - 3) + 8LL))(*((_QWORD *)v16 - 3));
    std::vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::~vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>(&v48);
    if ( *(_QWORD *)&v46.Data1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v46.Data1 + 16LL))(*(_QWORD *)&v46.Data1);
    goto LABEL_17;
  }
  v21 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Right(
          &v47,
          &ppv,
          (unsigned int)(*((_DWORD *)v16 - 4) - 4));
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(&v47, v21);
  v22 = (char *)ppv - 24;
  if ( _InterlockedDecrement((volatile signed __int32 *)ppv - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v22 + 8LL))(*v22);
  v23 = v50;
  if ( *(int *)(v50 - 16) < 5 )
  {
    v40 = (_QWORD *)(v50 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v50 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v40 + 8LL))(*v40);
    v41 = v47 - 12;
    if ( _InterlockedDecrement((volatile signed __int32 *)v47 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v41 + 8LL))(*(_QWORD *)v41);
    std::vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::~vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>(&v48);
    if ( *(_QWORD *)&v46.Data1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v46.Data1 + 16LL))(*(_QWORD *)&v46.Data1);
    goto LABEL_17;
  }
  v24 = (const wchar_t **)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Left(
                            &v50,
                            &ppv,
                            5);
  v25 = wcscmp_0(*v24, L"/jit:");
  v26 = (char *)ppv - 24;
  if ( _InterlockedDecrement((volatile signed __int32 *)ppv - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v26 + 8LL))(*v26);
  if ( v25 )
  {
    if ( _InterlockedDecrement((volatile signed __int32 *)(v23 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v23 - 24) + 8LL))(*(_QWORD *)(v23 - 24));
    v27 = v47 - 12;
    if ( _InterlockedDecrement((volatile signed __int32 *)v47 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v27 + 8LL))(*(_QWORD *)v27);
    std::vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::~vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>(&v48);
    if ( *(_QWORD *)&v46.Data1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v46.Data1 + 16LL))(*(_QWORD *)&v46.Data1);
    goto LABEL_17;
  }
  v28 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Right(
          &v50,
          &ppv,
          (unsigned int)(*(_DWORD *)(v23 - 16) - 5));
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(&v50, v28);
  v29 = (char *)ppv - 24;
  if ( _InterlockedDecrement((volatile signed __int32 *)ppv - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v29 + 8LL))(*v29);
  v30 = v50;
  v57 = _o__wcsicmp(v50, L"true") == 0;
  v51 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  if ( !(unsigned __int8)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
                           &v51,
                           &String) )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v51, &String, 0);
  v31 = (LPWSTR *)OpenProcess(0x400u, 0, dwProcessId);
  v59 = v31;
  if ( !v31 || (unsigned int)F12::GetPackageName(&v59, &v51) )
  {
    v33 = v51;
LABEL_91:
    v39 = v47;
    ShowTools(10, v58, v14, (HWND)v56, (HWND)v55, (HWND)v54, (void *)v53, v47, v57, 0, &String);
    if ( v31 )
      CloseHandle(v31);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v33 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v33 - 24) + 8LL))(*(_QWORD *)(v33 - 24));
    if ( _InterlockedDecrement((volatile signed __int32 *)(v30 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v30 - 24) + 8LL))(*(_QWORD *)(v30 - 24));
    if ( _InterlockedDecrement((volatile signed __int32 *)v39 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v39 - 3) + 8LL))(*((_QWORD *)v39 - 3));
    std::vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::~vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>(&v48);
    if ( *(_QWORD *)&v46.Data1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v46.Data1 + 16LL))(*(_QWORD *)&v46.Data1);
    if ( _InterlockedDecrement((volatile signed __int32 *)v4[-1].Data4) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v4[-2].Data4 + 8LL))(*(_QWORD *)v4[-2].Data4);
    return 0;
  }
  ppv = 0;
  v32 = CoCreateInstance(&CLSID_PackageDebugSettings, 0, 1u, &GUID_f27c3930_8029_4ad1_94e3_3dba417810c1, &ppv);
  if ( v32 )
  {
    if ( v32 >= 0 )
      v32 = -2147467259;
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    CloseHandle(v31);
    v37 = (_QWORD *)(v51 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v51 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v37 + 8LL))(*v37);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v30 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v30 - 24) + 8LL))(*(_QWORD *)(v30 - 24));
    v38 = v47 - 12;
    if ( _InterlockedDecrement((volatile signed __int32 *)v47 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v38 + 8LL))(*(_QWORD *)v38);
    std::vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::~vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>(&v48);
    if ( *(_QWORD *)&v46.Data1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v46.Data1 + 16LL))(*(_QWORD *)&v46.Data1);
    if ( _InterlockedDecrement((volatile signed __int32 *)v4[-1].Data4) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v4[-2].Data4 + 8LL))(*(_QWORD *)v4[-2].Data4);
    return (unsigned int)v32;
  }
  else
  {
    v33 = v51;
    v34 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, _QWORD))(*(_QWORD *)ppv + 24LL))(ppv, v51, 0, 0);
    if ( !v34 )
    {
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      goto LABEL_91;
    }
    if ( v34 >= 0 )
      v34 = -2147467259;
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    CloseHandle(v31);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v33 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v33 - 24) + 8LL))(*(_QWORD *)(v33 - 24));
    if ( _InterlockedDecrement((volatile signed __int32 *)(v30 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v30 - 24) + 8LL))(*(_QWORD *)(v30 - 24));
    v35 = v47 - 12;
    if ( _InterlockedDecrement((volatile signed __int32 *)v47 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v35 + 8LL))(*(_QWORD *)v35);
    std::vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::~vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>(&v48);
    if ( *(_QWORD *)&v46.Data1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v46.Data1 + 16LL))(*(_QWORD *)&v46.Data1);
    if ( _InterlockedDecrement((volatile signed __int32 *)v4[-1].Data4) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v4[-2].Data4 + 8LL))(*(_QWORD *)v4[-2].Data4);
    return (unsigned int)v34;
  }
}

```

## disassembly

```asm
0x180014740  mov     [rsp-8+arg_10], rbx
0x180014745  push    rbp
0x180014746  push    rsi
0x180014747  push    rdi
0x180014748  push    r12
0x18001474a  push    r13
0x18001474c  push    r14
0x18001474e  push    r15
0x180014750  lea     rbp, [rsp-210h]
0x180014758  sub     rsp, 310h
0x18001475f  mov     rax, cs:__security_cookie
0x180014766  xor     rax, rsp
0x180014769  mov     [rbp+240h+var_40], rax
0x180014770  mov     rdi, rdx
0x180014773  mov     r15d, ecx
0x180014776  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001477d  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180014784  mov     rax, [rax+18h]
0x180014788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001478d  add     rax, 18h
0x180014791  mov     [rbp+240h+var_298], rax
0x180014795  lea     rcx, [rbp+240h+var_298]
0x180014799  call    ?GetRootF12Directory@F12@@YAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; F12::GetRootF12Directory(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18001479e  xor     r14d, r14d
0x1800147a1  mov     rax, [rbp+240h+var_298]
0x1800147a5  cmp     [rax-10h], r14d
0x1800147a9  jle     loc_180015255
0x1800147af  lea     rdx, aF12appDll; "F12App.dll"
0x1800147b6  lea     rcx, [rbp+240h+var_298]
0x1800147ba  call    ?OurPathAppend@Win32Helpers@@YAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z; Win32Helpers::OurPathAppend(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *)
0x1800147bf  mov     qword ptr [rsp+340h+var_2D8.Data1], r14
0x1800147c4  lea     rax, [rsp+340h+var_2D8]
0x1800147c9  mov     [rsp+340h+ppv], rax; struct _GUID *
0x1800147ce  mov     rbx, [rbp+240h+var_298]
0x1800147d2  mov     r8, rbx; struct _GUID *
0x1800147d5  mov     rcx, [rdi]; this
0x1800147d8  call    ?CoCreateUsingDiagnosticsMode@BPT@@YAJPEAUIDispatch@@AEBU_GUID@@PEBG1PEAPEAX@Z; BPT::CoCreateUsingDiagnosticsMode(IDispatch *,_GUID const &,ushort const *,_GUID const &,void * *)
0x1800147dd  test    eax, eax
0x1800147df  jnz     loc_180015235
0x1800147e5  xor     edx, edx; Val
0x1800147e7  mov     r8d, 22Ch; Size
0x1800147ed  lea     rcx, [rbp+240h+var_270]; void *
0x1800147f1  call    memset_0
0x1800147f6  mov     rcx, qword ptr [rsp+340h+var_2D8.Data1]
0x1800147fb  mov     rax, [rcx]
0x1800147fe  lea     r9, [rbp+240h+var_270]
0x180014802  xor     r8d, r8d
0x180014805  lea     edx, [r14+65h]
0x180014809  mov     rax, [rax+40h]
0x18001480d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014812  mov     edi, eax
0x180014814  test    eax, eax
0x180014816  jnz     loc_1800151F4
0x18001481c  mov     dword ptr [rsp+340h+var_2D8.Data4], r14d
0x180014821  xorps   xmm0, xmm0
0x180014824  movdqu  [rbp+240h+var_2C0], xmm0
0x180014829  mov     [rbp+240h+var_2B0], r14
0x18001482d  lea     rdx, [rsp+340h+var_2D8.Data4]; pNumArgs
0x180014832  lea     rcx, [rbp+240h+CmdLine]; lpCmdLine
0x180014836  call    cs:__imp_CommandLineToArgvW
0x18001483c  mov     rsi, rax
0x18001483f  mov     [rbp+240h+var_278], rax
0x180014843  test    rax, rax
0x180014846  jz      loc_1800151A3
0x18001484c  mov     edi, r14d
0x18001484f  or      r12d, 0FFFFFFFFh
0x180014853  cmp     dword ptr [rsp+340h+var_2D8.Data4], r14d
0x180014858  jle     short loc_1800148CB
0x18001485a  movsxd  rdx, edi
0x18001485d  mov     rdx, [rsi+rdx*8]
0x180014861  lea     rcx, [rsp+340h+var_2E0]
0x180014866  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18001486b  nop
0x18001486c  mov     rax, qword ptr [rbp+240h+var_2C0+8]
0x180014870  cmp     rax, [rbp+240h+var_2B0]
0x180014874  jz      short loc_18001488A
0x180014876  lea     rdx, [rsp+340h+var_2E0]
0x18001487b  mov     rcx, rax
0x18001487e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180014883  add     qword ptr [rbp+240h+var_2C0+8], 8
0x180014888  jmp     short loc_18001489C
0x18001488a  lea     r8, [rsp+340h+var_2E0]
0x18001488f  mov     rdx, rax
0x180014892  lea     rcx, [rbp+240h+var_2C0]
0x180014896  call    ??$_Emplace_reallocate@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@?$vector@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$allocator@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@@std@@AEAAPEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAV23@AEBV23@@Z; std::vector<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::_Emplace_reallocate<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> * const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18001489b  nop
0x18001489c  mov     rdx, [rsp+340h+var_2E0]
0x1800148a1  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1800148a5  mov     eax, r12d
0x1800148a8  lock xadd [rdx+10h], eax
0x1800148ad  add     eax, r12d
0x1800148b0  test    eax, eax
0x1800148b2  jg      short loc_1800148C3
0x1800148b4  mov     rcx, [rdx]
0x1800148b7  mov     rax, [rcx]
0x1800148ba  mov     rax, [rax+8]
0x1800148be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148c3  inc     edi
0x1800148c5  cmp     edi, dword ptr [rsp+340h+var_2D8.Data4]
0x1800148c9  jl      short loc_18001485A
0x1800148cb  mov     rcx, rsi; hMem
0x1800148ce  call    cs:__imp_LocalFree
0x1800148d4  cmp     dword ptr [rsp+340h+var_2D8.Data4], 8
0x1800148d9  jl      loc_18001517D
0x1800148df  mov     rcx, qword ptr [rbp+240h+var_2C0]
0x1800148e3  mov     rcx, [rcx]
0x1800148e6  call    cs:__imp__o__wtoi
0x1800148ec  mov     [rbp+240h+var_27C], eax
0x1800148ef  lea     ecx, [rax-1]
0x1800148f2  cmp     ecx, 7FFFFFFDh
0x1800148f8  jbe     short loc_180014948
0x1800148fa  cmp     eax, 80000001h
0x1800148ff  jnb     short loc_180014948
0x180014901  lea     rcx, [rbp+240h+var_2C0]
0x180014905  call    ??1?$vector@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$allocator@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@@std@@QEAA@XZ; std::vector<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::~vector<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>(void)
0x18001490a  nop
0x18001490b  mov     rcx, qword ptr [rsp+340h+var_2D8.Data1]
0x180014910  test    rcx, rcx
0x180014913  jz      short loc_180014922
0x180014915  mov     rax, [rcx]
0x180014918  mov     rax, [rax+10h]
0x18001491c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014921  nop
0x180014922  lea     rdx, [rbx-18h]
0x180014926  mov     eax, r12d
0x180014929  lock xadd [rdx+10h], eax
0x18001492e  add     eax, r12d
0x180014931  test    eax, eax
0x180014933  jg      loc_18001527B
0x180014939  mov     rcx, [rdx]
0x18001493c  mov     rax, [rcx]
0x18001493f  mov     rax, [rax+8]
0x180014943  jmp     loc_180015276
0x180014948  xor     edx, edx; EndPtr
0x18001494a  lea     r8d, [rdx+10h]; Radix
0x18001494e  mov     rcx, qword ptr [rbp+240h+var_2C0]
0x180014952  mov     rcx, [rcx+8]; String
0x180014956  call    cs:__imp_wcstol
0x18001495c  movsxd  r13, eax
0x18001495f  test    eax, eax
0x180014961  jz      loc_180015157
0x180014967  mov     edi, 7FFFFFFFh
0x18001496c  cmp     r13d, edi
0x18001496f  jz      loc_180015157
0x180014975  mov     esi, 80000000h
0x18001497a  cmp     r13d, esi
0x18001497d  jz      loc_180015157
0x180014983  xor     edx, edx; EndPtr
0x180014985  lea     r8d, [rdx+10h]; Radix
0x180014989  mov     rcx, qword ptr [rbp+240h+var_2C0]
0x18001498d  mov     rcx, [rcx+10h]; String
0x180014991  call    cs:__imp_wcstol
0x180014997  mov     [rbp+240h+var_284], eax
0x18001499a  xor     edx, edx; EndPtr
0x18001499c  lea     r8d, [rdx+10h]; Radix
0x1800149a0  mov     rcx, qword ptr [rbp+240h+var_2C0]
0x1800149a4  mov     rcx, [rcx+18h]; String
0x1800149a8  call    cs:__imp_wcstol
0x1800149ae  mov     [rbp+240h+var_288], eax
0x1800149b1  xor     edx, edx; EndPtr
0x1800149b3  lea     r8d, [rdx+10h]; Radix
0x1800149b7  mov     rcx, qword ptr [rbp+240h+var_2C0]
0x1800149bb  mov     rcx, [rcx+20h]; String
0x1800149bf  call    cs:__imp_wcstol
0x1800149c5  mov     [rbp+240h+var_28C], eax
0x1800149c8  xor     edx, edx; EndPtr
0x1800149ca  lea     r8d, [rdx+10h]; Radix
0x1800149ce  mov     rcx, qword ptr [rbp+240h+var_2C0]
0x1800149d2  mov     rcx, [rcx+28h]; String
0x1800149d6  call    cs:__imp_wcstol
0x1800149dc  mov     [rbp+240h+var_290], eax
0x1800149df  test    eax, eax
0x1800149e1  jz      loc_180015131
0x1800149e7  cmp     eax, edi
0x1800149e9  jz      loc_180015131
0x1800149ef  cmp     eax, esi
0x1800149f1  jz      loc_180015131
0x1800149f7  mov     rdx, qword ptr [rbp+240h+var_2C0]
0x1800149fb  add     rdx, 30h ; '0'
0x1800149ff  lea     rcx, [rsp+340h+var_2C8]
0x180014a04  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180014a09  nop
0x180014a0a  mov     rdx, qword ptr [rbp+240h+var_2C0]
0x180014a0e  add     rdx, 38h ; '8'
0x180014a12  lea     rcx, [rbp+240h+var_2A8]
0x180014a16  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180014a1b  nop
0x180014a1c  mov     rdi, [rsp+340h+var_2C8]
0x180014a21  cmp     dword ptr [rdi-10h], 4
0x180014a25  jl      loc_1800150C1
0x180014a2b  mov     r8d, 4
0x180014a31  lea     rdx, [rsp+340h+var_2E0]
0x180014a36  lea     rcx, [rsp+340h+var_2C8]
0x180014a3b  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Left(int)
0x180014a40  nop
0x180014a41  lea     rdx, aId_0; "/id:"
0x180014a48  mov     rcx, [rax]; String1
0x180014a4b  call    wcscmp_0
0x180014a50  mov     esi, eax
0x180014a52  mov     rdx, [rsp+340h+var_2E0]
0x180014a57  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180014a5b  mov     ecx, r12d
0x180014a5e  lock xadd [rdx+10h], ecx
0x180014a63  add     ecx, r12d
0x180014a66  test    ecx, ecx
0x180014a68  jg      short loc_180014A79
0x180014a6a  mov     rcx, [rdx]
0x180014a6d  mov     r8, [rcx]
0x180014a70  mov     rax, [r8+8]
0x180014a74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a79  test    esi, esi
0x180014a7b  jz      short loc_180014AED
0x180014a7d  mov     rdx, [rbp+240h+var_2A8]
0x180014a81  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180014a85  mov     eax, r12d
0x180014a88  lock xadd [rdx+10h], eax
0x180014a8d  add     eax, r12d
0x180014a90  test    eax, eax
0x180014a92  jg      short loc_180014AA4
0x180014a94  mov     rcx, [rdx]
0x180014a97  mov     rax, [rcx]
0x180014a9a  mov     rax, [rax+8]
0x180014a9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014aa3  nop
0x180014aa4  lea     rdx, [rdi-18h]
0x180014aa8  mov     eax, r12d
0x180014aab  lock xadd [rdx+10h], eax
0x180014ab0  add     eax, r12d
0x180014ab3  test    eax, eax
0x180014ab5  jg      short loc_180014AC7
0x180014ab7  mov     rcx, [rdx]
0x180014aba  mov     rax, [rcx]
0x180014abd  mov     rax, [rax+8]
0x180014ac1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ac6  nop
0x180014ac7  lea     rcx, [rbp+240h+var_2C0]
0x180014acb  call    ??1?$vector@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$allocator@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@@std@@QEAA@XZ; std::vector<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::~vector<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>(void)
0x180014ad0  nop
0x180014ad1  mov     rcx, qword ptr [rsp+340h+var_2D8.Data1]
0x180014ad6  test    rcx, rcx
0x180014ad9  jz      short loc_180014AE8
0x180014adb  mov     rax, [rcx]
0x180014ade  mov     rax, [rax+10h]
0x180014ae2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ae7  nop
0x180014ae8  jmp     loc_180014922
0x180014aed  mov     r8d, [rdi-10h]
0x180014af1  sub     r8d, 4
0x180014af5  lea     rdx, [rsp+340h+var_2E0]
0x180014afa  lea     rcx, [rsp+340h+var_2C8]
0x180014aff  call    ?Right@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Right(int)
0x180014b04  nop
0x180014b05  mov     rdx, rax
0x180014b08  lea     rcx, [rsp+340h+var_2C8]
0x180014b0d  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180014b12  nop
0x180014b13  mov     rdx, [rsp+340h+var_2E0]
0x180014b18  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180014b1c  mov     eax, r12d
0x180014b1f  lock xadd [rdx+10h], eax
0x180014b24  add     eax, r12d
0x180014b27  test    eax, eax
0x180014b29  jg      short loc_180014B3A
0x180014b2b  mov     rcx, [rdx]
0x180014b2e  mov     rax, [rcx]
0x180014b31  mov     rax, [rax+8]
0x180014b35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b3a  mov     rdi, [rbp+240h+var_2A8]
0x180014b3e  cmp     dword ptr [rdi-10h], 5
0x180014b42  jl      loc_180015050
0x180014b48  mov     r8d, 5
0x180014b4e  lea     rdx, [rsp+340h+var_2E0]
0x180014b53  lea     rcx, [rbp+240h+var_2A8]
0x180014b57  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Left(int)
0x180014b5c  nop
0x180014b5d  lea     rdx, aJit; "/jit:"
0x180014b64  mov     rcx, [rax]; String1
0x180014b67  call    wcscmp_0
0x180014b6c  mov     esi, eax
0x180014b6e  mov     rdx, [rsp+340h+var_2E0]
0x180014b73  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180014b77  mov     ecx, r12d
0x180014b7a  lock xadd [rdx+10h], ecx
0x180014b7f  add     ecx, r12d
0x180014b82  test    ecx, ecx
0x180014b84  jg      short loc_180014B95
0x180014b86  mov     rcx, [rdx]
0x180014b89  mov     r8, [rcx]
0x180014b8c  mov     rax, [r8+8]
0x180014b90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b95  test    esi, esi
0x180014b97  jz      short loc_180014C0A
0x180014b99  lea     rdx, [rdi-18h]
0x180014b9d  mov     eax, r12d
0x180014ba0  lock xadd [rdx+10h], eax
0x180014ba5  add     eax, r12d
0x180014ba8  test    eax, eax
0x180014baa  jg      short loc_180014BBC
0x180014bac  mov     rcx, [rdx]
0x180014baf  mov     rax, [rcx]
  ... truncated ...
```
