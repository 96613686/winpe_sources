# Microsoft::Diagnostics::SnapshotManager::StartHeapSnapshotByProcessName(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,unsigned __int64,bool,bool,Microsoft::Diagnostics::EscalationWorkItemState &,Microsoft::Diagnostics::ScenarioInst const &)

- ea: `0x1801ea610`
- end: `0x1801eb21a`
- name: `?StartHeapSnapshotByProcessName@SnapshotManager@Diagnostics@Microsoft@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@_K_N2AEAVEscalationWorkItemState@23@AEBVScenarioInst@23@@Z`
- size: `3082`
- prototype: ``
- caller_count: `1`
- callee_count: `34`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801ea1a0`

## callees

- `0x1800012d4`
- `0x1800225a0`
- `0x180025744`
- `0x180027c28`
- `0x180027e50`
- `0x18002967c`
- `0x18002df00`
- `0x180052240`
- `0x18005d660`
- `0x180060500`
- `0x180064e6c`
- `0x180064e8c`
- `0x18006f428`
- `0x18009c8c0`
- `0x1800afab0`
- `0x1800cf7d8`
- `0x1800faa3c`
- `0x180108548`
- `0x18011c2ec`
- `0x18013b088`
- `0x180142fcc`
- `0x18016323c`
- `0x1801a38f4`
- `0x1801dcaf8`
- `0x1801ea610`
- `0x1801f4afc`
- `0x1801f4da4`
- `0x180200494`
- `0x18020aac0`
- `0x18020bab8`
- `0x1802d172c`
- `0x1802d1850`
- `0x1802d236c`
- `0x180369010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801eac7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801eac7a`
- `api-ms-win-core-toolhelp-l1-1-0!Process32FirstW` at `0x1801eaa5b`
- `api-ms-win-core-toolhelp-l1-1-0!Process32FirstW` at `0x1801eaa5b`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x1801eaa15`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x1801eaa15`
- `api-ms-win-core-toolhelp-l1-1-0!Process32NextW` at `0x1801eac6c`
- `api-ms-win-core-toolhelp-l1-1-0!Process32NextW` at `0x1801eac6c`

## string_xrefs

- `0x1801ea67e`: `onecore\base\telemetry\utc\service\scenarios\tracing\snapshotmanager.cpp`
- `0x1801ea7dc`: `onecore\base\telemetry\utc\service\scenarios\tracing\snapshotmanager.cpp`
- `0x1801eaa71`: `onecore\base\telemetry\utc\service\scenarios\tracing\snapshotmanager.cpp`
- `0x1801eac91`: `onecore\base\telemetry\utc\service\scenarios\tracing\snapshotmanager.cpp`
- `0x1801eae2e`: `onecore\base\telemetry\utc\service\scenarios\tracing\snapshotmanager.cpp`
- `0x1801eaf3b`: `onecore\base\telemetry\utc\service\scenarios\tracing\snapshotmanager.cpp`
- `0x1801eb0ab`: `onecore\base\telemetry\utc\service\scenarios\tracing\snapshotmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::SnapshotManager::StartHeapSnapshotByProcessName(
        Microsoft::Diagnostics::SnapshotManager *a1,
        __m128i *a2,
        __int64 a3,
        char a4,
        char a5,
        _BYTE *a6,
        __int64 a7)
{
  int v10; // esi
  __int64 v12; // r8
  unsigned __int64 v13; // r13
  int v14; // ecx
  int v15; // r9d
  char v16; // bl
  _QWORD *v17; // rax
  __int64 v18; // r8
  __int64 v19; // rcx
  int v20; // eax
  unsigned int v21; // esi
  __m128i v22; // xmm6
  _QWORD *ScenarioDef; // rax
  __int64 v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rdx
  __m128i si128; // xmm6
  __int64 v28; // rax
  void *v29; // r8
  void *appended; // rax
  void *v31; // rax
  void *v32; // rax
  char *Toolhelp32Snapshot; // rbx
  const char *v34; // r9
  const char *v35; // r9
  unsigned int LastError; // edi
  __int64 v37; // rax
  __int64 v38; // rdx
  const char *v39; // r9
  __int64 v40; // rbx
  gsl::details *v41; // rcx
  __int64 v42; // r8
  __int64 v43; // rcx
  int v44; // eax
  unsigned int v45; // esi
  __int64 v46; // rsi
  gsl::details *v47; // rcx
  int updated; // eax
  void *v49; // rax
  void *v50; // rax
  void *v51; // rax
  void *v52; // rax
  void *v53; // rax
  void *v54; // rax
  void *v55; // rax
  void *v56; // rax
  void *v57; // rax
  void *v58; // rax
  void *v59; // rax
  int v60; // [rsp+20h] [rbp-388h]
  __int128 v61; // [rsp+40h] [rbp-368h] BYREF
  __int64 v62; // [rsp+50h] [rbp-358h]
  char v63; // [rsp+58h] [rbp-350h] BYREF
  _BYTE v64[7]; // [rsp+59h] [rbp-34Fh] BYREF
  __m128i v65; // [rsp+60h] [rbp-348h] BYREF
  std::_Ref_count_base *v66[2]; // [rsp+70h] [rbp-338h] BYREF
  __m128i v67; // [rsp+80h] [rbp-328h] BYREF
  _QWORD v68[2]; // [rsp+90h] [rbp-318h] BYREF
  Microsoft::Diagnostics::SnapshotManager *v69; // [rsp+A0h] [rbp-308h]
  PROCESSENTRY32W pe; // [rsp+B0h] [rbp-2F8h] BYREF
  __int128 v71; // [rsp+2F0h] [rbp-B8h] BYREF
  __int64 v72; // [rsp+300h] [rbp-A8h]
  __m128i v73; // [rsp+308h] [rbp-A0h]
  _QWORD v74[4]; // [rsp+318h] [rbp-90h] BYREF
  DWORD th32ProcessID; // [rsp+338h] [rbp-70h] BYREF
  _QWORD v76[2]; // [rsp+340h] [rbp-68h] BYREF
  __m128i v77; // [rsp+350h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+3A8h] [rbp+0h]

  v69 = a1;
  v10 = 0;
  v65.m128i_i32[0] = 0;
  if ( !a2->m128i_i64[1] )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x78,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\tracing\\snapshotmanager.cpp",
      (const char *)0x80070057LL,
      v60);
    return 2147942487LL;
  }
  v67 = *a2;
  Microsoft::Diagnostics::ScenarioInst::ExpandPropertyIdentifiers(a7, v74, &v67);
  v13 = 1000 * a3 + Microsoft::Diagnostics::Utils::Time::QueryUbiTime() / 0x2710;
  v68[0] = v13;
  v61 = 0;
  v62 = 0;
  if ( (unsigned int)dword_1804543B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 68) )
  {
    v16 = a5;
    v63 = a5;
    v64[0] = a4;
    v17 = v74;
    if ( v74[3] > 7u )
      v17 = (_QWORD *)v74[0];
    v65.m128i_i64[0] = (__int64)v17;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(
      v14,
      (unsigned int)byte_1803F8319,
      v12,
      v15,
      (__int64)&v65,
      (__int64)v64,
      (__int64)&v63);
  }
  else
  {
    v16 = a5;
  }
  if ( v16 )
  {
    if ( a6[19] < a6[18] )
    {
      std::wstring::operator std::wstring_view(v74, &v67, v12);
      v65.m128i_i64[0] = 1;
      v65.m128i_i64[1] = (__int64)&v67;
      LOBYTE(v18) = 1;
      v20 = Microsoft::Diagnostics::SnapshotManager::ConfigureHeapSnapshotByProcessName(v19, &v65, v18);
      v21 = v20;
      if ( v20 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x8D,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\tracing\\snapshotmanager.cpp",
          (const char *)(unsigned int)v20,
          v60);
        if ( (_QWORD)v61 )
        {
          std::_Destroy_range<std::allocator<std::pair<std::pair<unsigned long,std::wstring>,unsigned __int64>>>(
            v61,
            *((_QWORD *)&v61 + 1));
          std::_Deallocate<16>(v61, 16 * ((v62 - (__int64)v61) >> 4));
          v61 = 0;
          v62 = 0;
        }
        std::wstring::_Tidy_deallocate(v74);
        return v21;
      }
      Microsoft::Diagnostics::LifetimeManager::GetScenarioCounterStorage((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
      v22 = v67;
      ScenarioDef = (_QWORD *)Microsoft::Diagnostics::ScenarioInst::GetScenarioDef(a7, v66);
      v24 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*ScenarioDef + 72LL))(*ScenarioDef);
      v65 = v22;
      Microsoft::Diagnostics::ScenarioCounterStorage::SetProcessNameForSnapshotScenarios(v25, v24, &v65);
      if ( v66[1] )
        std::_Ref_count_base::_Decref(v66[1]);
      LODWORD(v71) = 0;
      std::wstring::wstring((char *)&v71 + 8, v74);
      v26 = *((_QWORD *)&v61 + 1);
      if ( *((_QWORD *)&v61 + 1) == v62 )
      {
        std::vector<std::pair<std::pair<unsigned long,std::wstring>,unsigned __int64>>::_Emplace_reallocate<std::pair<int,std::wstring>,unsigned __int64 &>(
          &v61,
          *((_QWORD *)&v61 + 1),
          &v71,
          v68);
        si128 = _mm_load_si128((const __m128i *)&_xmm);
      }
      else
      {
        **((_DWORD **)&v61 + 1) = v71;
        *(_QWORD *)(v26 + 8) = *((_QWORD *)&v71 + 1);
        *(_QWORD *)(v26 + 16) = v72;
        *(__m128i *)(v26 + 24) = v73;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        v73 = si128;
        WORD4(v71) = 0;
        *(_QWORD *)(v26 + 40) = v13;
        *((_QWORD *)&v61 + 1) += 48LL;
      }
      v10 = 1;
      std::wstring::_Tidy_deallocate((char *)&v71 + 8);
      v28 = Microsoft::Diagnostics::WideStringStream::operator<<(a6 + 168);
      *(_OWORD *)v66 = *(_OWORD *)std::wstring::operator std::wstring_view(v74, &v65, v28);
      appended = (void *)Microsoft::Diagnostics::WideStringStream::AppendString(v29);
      Microsoft::Diagnostics::WideStringStream::operator<<(appended);
      goto LABEL_23;
    }
    v31 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(a6 + 168);
    *(__m128i *)v66 = *a2;
    v32 = (void *)Microsoft::Diagnostics::WideStringStream::AppendString(v31);
    Microsoft::Diagnostics::WideStringStream::operator<<(v32);
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm);
LABEL_23:
  if ( !a4 )
    goto LABEL_74;
  if ( a6[19] >= a6[18] )
  {
    v58 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(a6 + 168);
    *(__m128i *)v66 = *a2;
    v59 = (void *)Microsoft::Diagnostics::WideStringStream::AppendString(v58);
    Microsoft::Diagnostics::WideStringStream::operator<<(v59);
    goto LABEL_74;
  }
  Toolhelp32Snapshot = (char *)CreateToolhelp32Snapshot(2u, 0);
  v65.m128i_i64[0] = (__int64)Toolhelp32Snapshot;
  if ( (unsigned __int64)(Toolhelp32Snapshot - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xA1,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\tracing\\snapshotmanager.cpp",
                  v34);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (void *),&int CloseHandle(void *)>>(&v65);
    if ( (_QWORD)v61 )
    {
      std::_Destroy_range<std::allocator<std::pair<std::pair<unsigned long,std::wstring>,unsigned __int64>>>(
        v61,
        *((_QWORD *)&v61 + 1));
      std::_Deallocate<16>(v61, 16 * ((v62 - (__int64)v61) >> 4));
      v61 = 0;
      v62 = 0;
    }
LABEL_72:
    std::wstring::_Tidy_deallocate(v74);
    return LastError;
  }
  memset_0(&pe.cntUsage, 0, 0x234u);
  pe.dwSize = 568;
  if ( !Process32FirstW(Toolhelp32Snapshot, &pe) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xA6,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\tracing\\snapshotmanager.cpp",
                  v35);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (void *),&int CloseHandle(void *)>>(&v65);
    if ( (_QWORD)v61 )
    {
      std::_Destroy_range<std::allocator<std::pair<std::pair<unsigned long,std::wstring>,unsigned __int64>>>(
        v61,
        *((_QWORD *)&v61 + 1));
      std::_Deallocate<16>(v61, 16 * ((v62 - (__int64)v61) >> 4));
      v61 = 0;
      v62 = 0;
    }
    goto LABEL_72;
  }
  v71 = 0;
  v72 = 0;
  while ( 1 )
  {
    v37 = -1;
    do
      ++v37;
    while ( pe.szExeFile[v37] );
    v67.m128i_i64[0] = (__int64)pe.szExeFile;
    v67.m128i_i64[1] = v37;
    *(__m128i *)v66 = *a2;
    if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(v66, &v67) )
      goto LABEL_43;
    if ( a6[19] >= a6[18] )
      break;
    if ( *((_QWORD *)&v71 + 1) == v72 )
    {
      std::vector<unsigned long>::_Emplace_reallocate<unsigned long>(&v71, *((_QWORD *)&v71 + 1), &pe.th32ProcessID);
    }
    else
    {
      **((_DWORD **)&v71 + 1) = pe.th32ProcessID;
      *((_QWORD *)&v71 + 1) += 4LL;
    }
    th32ProcessID = pe.th32ProcessID;
    std::wstring::wstring(v76, v74);
    v38 = *((_QWORD *)&v61 + 1);
    if ( *((_QWORD *)&v61 + 1) == v62 )
    {
      std::vector<std::pair<std::pair<unsigned long,std::wstring>,unsigned __int64>>::_Emplace_reallocate<std::pair<int,std::wstring>,unsigned __int64 &>(
        &v61,
        *((_QWORD *)&v61 + 1),
        &th32ProcessID,
        v68);
    }
    else
    {
      **((_DWORD **)&v61 + 1) = th32ProcessID;
      *(_QWORD *)(v38 + 8) = v76[0];
      *(_QWORD *)(v38 + 16) = v76[1];
      *(__m128i *)(v38 + 24) = v77;
      v77 = si128;
      LOWORD(v76[0]) = 0;
      *(_QWORD *)(v38 + 40) = v13;
      *((_QWORD *)&v61 + 1) += 48LL;
    }
    std::wstring::_Tidy_deallocate(v76);
    if ( ++a6[19] >= a6[18] )
    {
      v49 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(a6 + 168);
      v50 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v49);
      v51 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v50);
      *(__m128i *)v66 = *a2;
      v52 = (void *)Microsoft::Diagnostics::WideStringStream::AppendString(v51);
      v53 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v52);
      v54 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v53);
      goto LABEL_68;
    }
    v10 |= 2u;
LABEL_43:
    if ( !Process32NextW(Toolhelp32Snapshot, &pe) )
      goto LABEL_44;
  }
  v55 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(a6 + 168);
  *(__m128i *)v66 = *a2;
  v56 = (void *)Microsoft::Diagnostics::WideStringStream::AppendString(v55);
  v57 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v56);
  v54 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v57);
LABEL_68:
  Microsoft::Diagnostics::WideStringStream::operator<<(v54);
LABEL_44:
  if ( GetLastError() != 18 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xCA,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\tracing\\snapshotmanager.cpp",
                  v39);
    std::vector<enum _TDH_IN_TYPE>::~vector<enum _TDH_IN_TYPE>(&v71);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (void *),&int CloseHandle(void *)>>(&v65);
    if ( (_QWORD)v61 )
    {
      std::_Destroy_range<std::allocator<std::pair<std::pair<unsigned long,std::wstring>,unsigned __int64>>>(
        v61,
        *((_QWORD *)&v61 + 1));
      std::_Deallocate<16>(v61, 16 * ((v62 - (__int64)v61) >> 4));
      v61 = 0;
      v62 = 0;
    }
    goto LABEL_72;
  }
  v40 = v71;
  if ( (_QWORD)v71 == *((_QWORD *)&v71 + 1) )
  {
    std::vector<enum _TDH_IN_TYPE>::~vector<enum _TDH_IN_TYPE>(&v71);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (void *),&int CloseHandle(void *)>>(&v65);
    if ( (_QWORD)v61 )
    {
      std::_Destroy_range<std::allocator<std::pair<std::pair<unsigned long,std::wstring>,unsigned __int64>>>(
        v61,
        *((_QWORD *)&v61 + 1));
      std::_Deallocate<16>(v61, 16 * ((v62 - (__int64)v61) >> 4));
      v61 = 0;
      v62 = 0;
    }
    std::wstring::_Tidy_deallocate(v74);
    return 1168;
  }
  gsl::details::extent_type<-1>::extent_type<-1>(v68, (__int64)(*((_QWORD *)&v71 + 1) - v71) >> 2);
  v68[1] = v40;
  if ( v68[0] == -1 || !v40 && v68[0] )
    gsl::details::terminate(v41);
  *(_OWORD *)v66 = *(_OWORD *)gsl::span<unsigned long const,-1>::span<unsigned long const,-1>(&v67, v68);
  LOBYTE(v42) = 1;
  v44 = Microsoft::Diagnostics::SnapshotManager::ConfigureHeapSnapshotByPid(v43, v66, v42);
  v45 = v44;
  if ( v44 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCF,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\tracing\\snapshotmanager.cpp",
      (const char *)(unsigned int)v44,
      v60);
    std::vector<enum _TDH_IN_TYPE>::~vector<enum _TDH_IN_TYPE>(&v71);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (void *),&int CloseHandle(void *)>>(&v65);
    if ( (_QWORD)v61 )
    {
      std::_Destroy_range<std::allocator<std::pair<std::pair<unsigned long,std::wstring>,unsigned __int64>>>(
        v61,
        *((_QWORD *)&v61 + 1));
      std::_Deallocate<16>(v61, 16 * ((v62 - (__int64)v61) >> 4));
      v61 = 0;
      v62 = 0;
    }
LABEL_58:
    std::wstring::_Tidy_deallocate(v74);
    return v45;
  }
  v46 = v61;
  gsl::details::extent_type<-1>::extent_type<-1>(
    v66,
    0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v61 + 1) - v61) >> 4));
  if ( v66[0] == (std::_Ref_count_base *)-1LL || !v46 && v66[0] )
    gsl::details::terminate(v47);
  v67.m128i_i64[0] = (__int64)v66[0];
  v67.m128i_i64[1] = v46;
  updated = Microsoft::Diagnostics::SnapshotManager::TryUpdateSnapshotConditionalTimer(v69);
  v45 = updated;
  if ( updated < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD0,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\tracing\\snapshotmanager.cpp",
      (const char *)(unsigned int)updated,
      v60);
    std::vector<enum _TDH_IN_TYPE>::~vector<enum _TDH_IN_TYPE>(&v71);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (void *),&int CloseHandle(void *)>>(&v65);
    if ( (_QWORD)v61 )
    {
      std::_Destroy_range<std::allocator<std::pair<std::pair<unsigned long,std::wstring>,unsigned __int64>>>(
        v61,
        *((_QWORD *)&v61 + 1));
      std::_Deallocate<16>(v61, 16 * ((v62 - (__int64)v61) >> 4));
      v61 = 0;
      v62 = 0;
    }
    goto LABEL_58;
  }
  std::vector<enum _TDH_IN_TYPE>::~vector<enum _TDH_IN_TYPE>(&v71);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (void *),&int CloseHandle(void *)>>(&v65);
LABEL_74:
  Microsoft::Diagnostics::WideStringStream::operator<<(a6 + 168);
  if ( (_QWORD)v61 )
  {
    std::_Destroy_range<std::allocator<std::pair<std::pair<unsigned long,std::wstring>,unsigned __int64>>>(
      v61,
      *((_QWORD *)&v61 + 1));
    std::_Deallocate<16>(v61, 16 * ((v62 - (__int64)v61) >> 4));
    v61 = 0;
    v62 = 0;
  }
  std::wstring::_Tidy_deallocate(v74);
  return 0;
}

```

## disassembly

```asm
0x1801ea610  mov     rax, rsp
0x1801ea613  mov     [rax+18h], rbx
0x1801ea617  mov     [rax+20h], rsi
0x1801ea61b  push    rdi
0x1801ea61c  push    r12
0x1801ea61e  push    r13
0x1801ea620  push    r14
0x1801ea622  push    r15
0x1801ea624  sub     rsp, 380h
0x1801ea62b  movaps  xmmword ptr [rax-38h], xmm6
0x1801ea62f  mov     rax, cs:__security_cookie
0x1801ea636  xor     rax, rsp
0x1801ea639  mov     [rsp+3A8h+var_48], rax
0x1801ea641  mov     r12b, r9b
0x1801ea644  mov     rbx, r8
0x1801ea647  mov     r14, rdx
0x1801ea64a  mov     [rsp+3A8h+var_308], rcx
0x1801ea652  mov     rdi, [rsp+3A8h+arg_28]
0x1801ea65a  mov     r15, [rsp+3A8h+arg_30]
0x1801ea662  xor     esi, esi
0x1801ea664  mov     dword ptr [rsp+3A8h+var_348], esi
0x1801ea668  cmp     [rdx+8], rsi
0x1801ea66c  jnz     short loc_1801EA694
0x1801ea66e  mov     rcx, [rsp+3A8h]; this
0x1801ea676  mov     ebx, 80070057h
0x1801ea67b  mov     r9d, ebx; char *
0x1801ea67e  lea     r8, aOnecoreBaseTel_204; "onecore\\base\\telemetry\\utc\\service"...
0x1801ea685  lea     edx, [rsi+78h]; void *
0x1801ea688  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801ea68d  mov     eax, ebx
0x1801ea68f  jmp     loc_1801EB1DB
0x1801ea694  movups  xmm0, xmmword ptr [rdx]
0x1801ea697  movdqu  [rsp+3A8h+var_328], xmm0
0x1801ea6a0  lea     r8, [rsp+3A8h+var_328]
0x1801ea6a8  lea     rdx, [rsp+3A8h+var_90]
0x1801ea6b0  mov     rcx, r15
0x1801ea6b3  call    ?ExpandPropertyIdentifiers@ScenarioInst@Diagnostics@Microsoft@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@5@@Z; Microsoft::Diagnostics::ScenarioInst::ExpandPropertyIdentifiers(std::wstring_view)
0x1801ea6b8  nop
0x1801ea6b9  call    ?QueryUbiTime@Time@Utils@Diagnostics@Microsoft@@SA_KXZ; Microsoft::Diagnostics::Utils::Time::QueryUbiTime(void)
0x1801ea6be  mov     rcx, rax
0x1801ea6c1  mov     rax, 346DC5D63886594Bh
0x1801ea6cb  mul     rcx
0x1801ea6ce  mov     r13, rdx
0x1801ea6d1  shr     r13, 0Bh
0x1801ea6d5  imul    rax, rbx, 3E8h
0x1801ea6dc  add     r13, rax
0x1801ea6df  mov     [rsp+3A8h+var_318], r13
0x1801ea6e7  xorps   xmm0, xmm0
0x1801ea6ea  movdqu  [rsp+3A8h+var_368], xmm0
0x1801ea6f0  mov     [rsp+3A8h+var_358], 0
0x1801ea6f9  mov     eax, cs:dword_1804543B0
0x1801ea6ff  cmp     eax, 4
0x1801ea702  jbe     short loc_1801EA774
0x1801ea704  mov     edx, 44h ; 'D'
0x1801ea709  lea     rcx, dword_1804543B0
0x1801ea710  call    _tlgKeywordOn
0x1801ea715  test    al, al
0x1801ea717  jz      short loc_1801EA774
0x1801ea719  mov     bl, [rsp+3A8h+arg_20]
0x1801ea720  mov     [rsp+3A8h+var_350], bl
0x1801ea724  mov     [rsp+3A8h+var_34F], r12b
0x1801ea729  lea     rax, [rsp+3A8h+var_90]
0x1801ea731  cmp     [rsp+3A8h+var_78], 7
0x1801ea73a  cmova   rax, [rsp+3A8h+var_90]
0x1801ea743  mov     qword ptr [rsp+3A8h+var_348], rax
0x1801ea748  lea     rax, [rsp+3A8h+var_350]
0x1801ea74d  mov     [rsp+3A8h+var_378], rax
0x1801ea752  lea     rax, [rsp+3A8h+var_34F]
0x1801ea757  mov     [rsp+3A8h+var_380], rax
0x1801ea75c  lea     rax, [rsp+3A8h+var_348]
0x1801ea761  mov     [rsp+3A8h+var_388], rax
0x1801ea766  lea     rdx, byte_1803F8319
0x1801ea76d  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$00@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$00@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &)
0x1801ea772  jmp     short loc_1801EA77B
0x1801ea774  mov     bl, [rsp+3A8h+arg_20]
0x1801ea77b  test    bl, bl
0x1801ea77d  jz      loc_1801EA9F0
0x1801ea783  mov     al, [rdi+12h]
0x1801ea786  cmp     [rdi+13h], al
0x1801ea789  jnb     loc_1801EA9B7
0x1801ea78f  lea     rdx, [rsp+3A8h+var_328]
0x1801ea797  lea     rcx, [rsp+3A8h+var_90]
0x1801ea79f  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1801ea7a4  mov     qword ptr [rsp+3A8h+var_348], 1
0x1801ea7ad  lea     rax, [rsp+3A8h+var_328]
0x1801ea7b5  mov     qword ptr [rsp+3A8h+var_348+8], rax
0x1801ea7ba  mov     r8b, 1
0x1801ea7bd  lea     rdx, [rsp+3A8h+var_348]
0x1801ea7c2  call    ?ConfigureHeapSnapshotByProcessName@SnapshotManager@Diagnostics@Microsoft@@AEBAJV?$span@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@$0?0@gsl@@_N@Z; Microsoft::Diagnostics::SnapshotManager::ConfigureHeapSnapshotByProcessName(gsl::span<std::wstring_view,-1>,bool)
0x1801ea7c7  mov     esi, eax
0x1801ea7c9  test    eax, eax
0x1801ea7cb  jns     loc_1801EA854
0x1801ea7d1  mov     rcx, [rsp+3A8h]; this
0x1801ea7d9  mov     r9d, eax; char *
0x1801ea7dc  lea     r8, aOnecoreBaseTel_204; "onecore\\base\\telemetry\\utc\\service"...
0x1801ea7e3  mov     edx, 8Dh; void *
0x1801ea7e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801ea7ed  nop
0x1801ea7ee  mov     rcx, qword ptr [rsp+3A8h+var_368]
0x1801ea7f3  test    rcx, rcx
0x1801ea7f6  jz      short loc_1801EA840
0x1801ea7f8  mov     rdx, qword ptr [rsp+3A8h+var_368+8]
0x1801ea7fd  call    ??$_Destroy_range@V?$allocator@U?$pair@U?$pair@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@_K@std@@@std@@@std@@YAXPEAU?$pair@U?$pair@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@_K@0@QEAU10@AEAV?$allocator@U?$pair@U?$pair@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@_K@std@@@0@@Z; std::_Destroy_range<std::allocator<std::pair<std::pair<ulong,std::wstring>,unsigned __int64>>>(std::pair<std::pair<ulong,std::wstring>,unsigned __int64> *,std::pair<std::pair<ulong,std::wstring>,unsigned __int64> * const,std::allocator<std::pair<std::pair<ulong,std::wstring>,unsigned __int64>> &)
0x1801ea802  mov     rcx, qword ptr [rsp+3A8h+var_368]
0x1801ea807  mov     rax, [rsp+3A8h+var_358]
0x1801ea80c  sub     rax, rcx
0x1801ea80f  sar     rax, 4
0x1801ea813  mov     rbx, 0AAAAAAAAAAAAAAABh
0x1801ea81d  imul    rax, rbx
0x1801ea821  lea     rdx, [rax+rax*2]
0x1801ea825  shl     rdx, 4
0x1801ea829  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801ea82e  xorps   xmm0, xmm0
0x1801ea831  movdqu  [rsp+3A8h+var_368], xmm0
0x1801ea837  mov     [rsp+3A8h+var_358], 0
0x1801ea840  lea     rcx, [rsp+3A8h+var_90]
0x1801ea848  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801ea84d  mov     eax, esi
0x1801ea84f  jmp     loc_1801EB1DB
0x1801ea854  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x1801ea85b  call    ?GetScenarioCounterStorage@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVScenarioCounterStorage@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetScenarioCounterStorage(void)
0x1801ea860  movups  xmm6, [rsp+3A8h+var_328]
0x1801ea868  lea     rdx, [rsp+3A8h+var_338]
0x1801ea86d  mov     rcx, r15
0x1801ea870  call    ?GetScenarioDef@ScenarioInst@Diagnostics@Microsoft@@QEBA?AV?$shared_ptr@$$CBVIScenarioDef@Diagnostics@Microsoft@@@std@@XZ; Microsoft::Diagnostics::ScenarioInst::GetScenarioDef(void)
0x1801ea875  nop
0x1801ea876  mov     rcx, [rax]
0x1801ea879  mov     rax, [rcx]
0x1801ea87c  mov     rax, [rax+48h]
0x1801ea880  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ea885  movdqu  [rsp+3A8h+var_348], xmm6
0x1801ea88b  lea     r8, [rsp+3A8h+var_348]
0x1801ea890  mov     rdx, rax
0x1801ea893  call    ?SetProcessNameForSnapshotScenarios@ScenarioCounterStorage@Diagnostics@Microsoft@@QEAAXAEBU_GUID@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::ScenarioCounterStorage::SetProcessNameForSnapshotScenarios(_GUID const &,std::wstring_view)
0x1801ea898  nop
0x1801ea899  mov     rcx, [rsp+3A8h+var_338+8]; this
0x1801ea89e  xor     r15d, r15d
0x1801ea8a1  test    rcx, rcx
0x1801ea8a4  jz      short loc_1801EA8AB
0x1801ea8a6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801ea8ab  mov     dword ptr [rsp+3A8h+var_B8], r15d
0x1801ea8b3  lea     rdx, [rsp+3A8h+var_90]
0x1801ea8bb  lea     rcx, [rsp+3A8h+var_B8+8]
0x1801ea8c3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1801ea8c8  nop
0x1801ea8c9  mov     rdx, qword ptr [rsp+3A8h+var_368+8]
0x1801ea8ce  cmp     rdx, [rsp+3A8h+var_358]
0x1801ea8d3  jz      short loc_1801EA934
0x1801ea8d5  mov     eax, dword ptr [rsp+3A8h+var_B8]
0x1801ea8dc  mov     [rdx], eax
0x1801ea8de  mov     rax, qword ptr [rsp+3A8h+var_B8+8]
0x1801ea8e6  mov     [rdx+8], rax
0x1801ea8ea  mov     rax, [rsp+3A8h+var_A8]
0x1801ea8f2  mov     [rdx+10h], rax
0x1801ea8f6  mov     rax, qword ptr [rsp+3A8h+var_A0]
0x1801ea8fe  mov     [rdx+18h], rax
0x1801ea902  mov     rax, qword ptr [rsp+3A8h+var_A0+8]
0x1801ea90a  mov     [rdx+20h], rax
0x1801ea90e  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1801ea916  movdqu  [rsp+3A8h+var_A0], xmm6
0x1801ea91f  mov     word ptr [rsp+3A8h+var_B8+8], r15w
0x1801ea928  mov     [rdx+28h], r13
0x1801ea92c  add     qword ptr [rsp+3A8h+var_368+8], 30h ; '0'
0x1801ea932  jmp     short loc_1801EA956
0x1801ea934  lea     r9, [rsp+3A8h+var_318]
0x1801ea93c  lea     r8, [rsp+3A8h+var_B8]
0x1801ea944  lea     rcx, [rsp+3A8h+var_368]
0x1801ea949  call    ??$_Emplace_reallocate@U?$pair@HV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@AEA_K@?$vector@U?$pair@U?$pair@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@_K@std@@V?$allocator@U?$pair@U?$pair@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@_K@std@@@2@@std@@AEAAPEAU?$pair@U?$pair@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@_K@1@QEAU21@$$QEAU?$pair@HV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@1@AEA_K@Z; std::vector<std::pair<std::pair<ulong,std::wstring>,unsigned __int64>>::_Emplace_reallocate<std::pair<int,std::wstring>,unsigned __int64 &>(std::pair<std::pair<ulong,std::wstring>,unsigned __int64> * const,std::pair<int,std::wstring> &&,unsigned __int64 &)
0x1801ea94e  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1801ea956  mov     esi, 1
0x1801ea95b  lea     rcx, [rsp+3A8h+var_B8+8]
0x1801ea963  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801ea968  lea     rcx, [rdi+0A8h]; Src
0x1801ea96f  lea     rdx, aSuccessfullySt_1; "Successfully started snapshot, processN"...
0x1801ea976  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1801ea97b  mov     r8, rax
0x1801ea97e  lea     rdx, [rsp+3A8h+var_348]
0x1801ea983  lea     rcx, [rsp+3A8h+var_90]
0x1801ea98b  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1801ea990  movups  xmm0, xmmword ptr [rax]
0x1801ea993  movdqu  xmmword ptr [rsp+3A8h+var_338], xmm0
0x1801ea999  lea     rdx, [rsp+3A8h+var_338]
0x1801ea99e  mov     rcx, r8; Src
0x1801ea9a1  call    ?AppendString@WideStringStream@Diagnostics@Microsoft@@AEAAAEAV123@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::WideStringStream::AppendString(std::wstring_view)
0x1801ea9a6  lea     rdx, asc_1803A0020; ".\r\n"
0x1801ea9ad  mov     rcx, rax; Src
0x1801ea9b0  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1801ea9b5  jmp     short loc_1801EA9FB
0x1801ea9b7  lea     rcx, [rdi+0A8h]; Src
0x1801ea9be  lea     rdx, aSkippingProces_0; "Skipping process snapshot of "
0x1801ea9c5  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1801ea9ca  movups  xmm0, xmmword ptr [r14]
0x1801ea9ce  movdqu  xmmword ptr [rsp+3A8h+var_338], xmm0
0x1801ea9d4  lea     rdx, [rsp+3A8h+var_338]
0x1801ea9d9  mov     rcx, rax; Src
0x1801ea9dc  call    ?AppendString@WideStringStream@Diagnostics@Microsoft@@AEAAAEAV123@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::WideStringStream::AppendString(std::wstring_view)
0x1801ea9e1  lea     rdx, aDueToCap; " due to cap.\r\n"
0x1801ea9e8  mov     rcx, rax; Src
0x1801ea9eb  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1801ea9f0  xor     r15d, r15d
0x1801ea9f3  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1801ea9fb  test    r12b, r12b
0x1801ea9fe  jz      loc_1801EB164
0x1801eaa04  mov     al, [rdi+12h]
0x1801eaa07  cmp     [rdi+13h], al
0x1801eaa0a  jnb     loc_1801EB12B
0x1801eaa10  xor     edx, edx; th32ProcessID
0x1801eaa12  lea     ecx, [rdx+2]; dwFlags
0x1801eaa15  call    cs:__imp_CreateToolhelp32Snapshot
0x1801eaa1b  mov     rbx, rax
0x1801eaa1e  mov     qword ptr [rsp+3A8h+var_348], rax
0x1801eaa23  dec     rax
0x1801eaa26  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801eaa2a  ja      loc_1801EB0A3
0x1801eaa30  xor     edx, edx; Val
0x1801eaa32  mov     r8d, 234h; Size
0x1801eaa38  lea     rcx, [rsp+3A8h+pe.cntUsage]; void *
0x1801eaa40  call    memset_0
0x1801eaa45  mov     [rsp+3A8h+pe.dwSize], 238h
0x1801eaa50  lea     rdx, [rsp+3A8h+pe]; lppe
0x1801eaa58  mov     rcx, rbx; hSnapshot
0x1801eaa5b  call    cs:__imp_Process32FirstW
0x1801eaa61  test    eax, eax
0x1801eaa63  jnz     loc_1801EAAF3
0x1801eaa69  mov     rcx, [rsp+3A8h]; this
0x1801eaa71  lea     r8, aOnecoreBaseTel_204; "onecore\\base\\telemetry\\utc\\service"...
0x1801eaa78  mov     edx, 0A6h; void *
0x1801eaa7d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801eaa82  mov     edi, eax
0x1801eaa84  lea     rcx, [rsp+3A8h+var_348]
0x1801eaa89  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@$$A6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (void *),&CloseHandle(void *)>>(void)
0x1801eaa8e  nop
0x1801eaa8f  mov     rcx, qword ptr [rsp+3A8h+var_368]
0x1801eaa94  test    rcx, rcx
0x1801eaa97  jz      short loc_1801EAADF
0x1801eaa99  mov     rdx, qword ptr [rsp+3A8h+var_368+8]
0x1801eaa9e  call    ??$_Destroy_range@V?$allocator@U?$pair@U?$pair@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@_K@std@@@std@@@std@@YAXPEAU?$pair@U?$pair@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@_K@0@QEAU10@AEAV?$allocator@U?$pair@U?$pair@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@_K@std@@@0@@Z; std::_Destroy_range<std::allocator<std::pair<std::pair<ulong,std::wstring>,unsigned __int64>>>(std::pair<std::pair<ulong,std::wstring>,unsigned __int64> *,std::pair<std::pair<ulong,std::wstring>,unsigned __int64> * const,std::allocator<std::pair<std::pair<ulong,std::wstring>,unsigned __int64>> &)
0x1801eaaa3  mov     rcx, [rsp+3A8h+var_358]
0x1801eaaa8  sub     rcx, qword ptr [rsp+3A8h+var_368]
0x1801eaaad  sar     rcx, 4
0x1801eaab1  mov     rbx, 0AAAAAAAAAAAAAAABh
0x1801eaabb  imul    rcx, rbx
0x1801eaabf  lea     rdx, [rcx+rcx*2]
0x1801eaac3  shl     rdx, 4
0x1801eaac7  mov     rcx, qword ptr [rsp+3A8h+var_368]
0x1801eaacc  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801eaad1  xorps   xmm0, xmm0
0x1801eaad4  movdqu  [rsp+3A8h+var_368], xmm0
0x1801eaada  mov     [rsp+3A8h+var_358], r15
0x1801eaadf  lea     rcx, [rsp+3A8h+var_90]
0x1801eaae7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801eaaec  mov     eax, edi
0x1801eaaee  jmp     loc_1801EB1DB
0x1801eaaf3  xorps   xmm0, xmm0
0x1801eaaf6  movdqu  [rsp+3A8h+var_B8], xmm0
0x1801eaaff  mov     [rsp+3A8h+var_A8], r15
0x1801eab07  lea     rcx, [rsp+3A8h+pe.szExeFile]
0x1801eab0f  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801eab13  inc     rax
0x1801eab16  cmp     [rcx+rax*2], r15w
0x1801eab1b  jnz     short loc_1801EAB13
0x1801eab1d  lea     rcx, [rsp+3A8h+pe.szExeFile]
0x1801eab25  mov     qword ptr [rsp+3A8h+var_328], rcx
0x1801eab2d  mov     qword ptr [rsp+3A8h+var_328+8], rax
0x1801eab35  movups  xmm0, xmmword ptr [r14]
0x1801eab39  movdqu  xmmword ptr [rsp+3A8h+var_338], xmm0
0x1801eab3f  lea     rdx, [rsp+3A8h+var_328]
0x1801eab47  lea     rcx, [rsp+3A8h+var_338]
0x1801eab4c  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x1801eab51  test    eax, eax
0x1801eab53  jnz     loc_1801EAC61
0x1801eab59  mov     al, [rdi+12h]
0x1801eab5c  cmp     [rdi+13h], al
0x1801eab5f  jnb     loc_1801EB052
0x1801eab65  mov     rdx, qword ptr [rsp+3A8h+var_B8+8]
0x1801eab6d  cmp     rdx, [rsp+3A8h+var_A8]
0x1801eab75  jz      short loc_1801EAB8B
0x1801eab77  mov     eax, [rsp+3A8h+pe.th32ProcessID]
0x1801eab7e  mov     [rdx], eax
0x1801eab80  add     qword ptr [rsp+3A8h+var_B8+8], 4
0x1801eab89  jmp     short loc_1801EABA0
0x1801eab8b  lea     r8, [rsp+3A8h+pe.th32ProcessID]
0x1801eab93  lea     rcx, [rsp+3A8h+var_B8]
0x1801eab9b  call    ??$_Emplace_reallocate@K@?$vector@KV?$allocator@K@std@@@std@@AEAAPEAKQEAK$$QEAK@Z; std::vector<ulong>::_Emplace_reallocate<ulong>(ulong * const,ulong &&)
0x1801eaba0  mov     eax, [rsp+3A8h+pe.th32ProcessID]
0x1801eaba7  mov     [rsp+3A8h+var_70], eax
0x1801eabae  lea     rdx, [rsp+3A8h+var_90]
0x1801eabb6  lea     rcx, [rsp+3A8h+var_68]
0x1801eabbe  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1801eabc3  nop
0x1801eabc4  mov     rdx, qword ptr [rsp+3A8h+var_368+8]
0x1801eabc9  cmp     rdx, [rsp+3A8h+var_358]
0x1801eabce  jz      short loc_1801EAC27
0x1801eabd0  mov     eax, [rsp+3A8h+var_70]
0x1801eabd7  mov     [rdx], eax
0x1801eabd9  mov     rax, [rsp+3A8h+var_68]
0x1801eabe1  mov     [rdx+8], rax
0x1801eabe5  mov     rax, [rsp+3A8h+var_60]
0x1801eabed  mov     [rdx+10h], rax
0x1801eabf1  mov     rax, qword ptr [rsp+3A8h+var_58]
  ... truncated ...
```
