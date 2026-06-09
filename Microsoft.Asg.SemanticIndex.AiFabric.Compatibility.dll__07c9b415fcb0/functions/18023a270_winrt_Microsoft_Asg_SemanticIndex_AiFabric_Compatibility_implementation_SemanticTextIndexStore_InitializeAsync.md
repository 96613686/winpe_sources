# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore::InitializeAsync$_ResumeCoro$1

- ea: `0x18023a270`
- end: `0x18023b8d0`
- name: `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore::InitializeAsync$_ResumeCoro$1`
- size: `5728`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `2`
- callee_count: `44`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180238ec0`
- `0x18023a260`

## callees

- `0x180003350`
- `0x180003bd0`
- `0x180003df0`
- `0x180003fb0`
- `0x180004510`
- `0x180004f00`
- `0x180007830`
- `0x180007de0`
- `0x180009cd0`
- `0x18000a8e0`
- `0x18000d230`
- `0x18000d4b0`
- `0x180010400`
- `0x180010dd0`
- `0x180019520`
- `0x18001b3c0`
- `0x18001bc40`
- `0x18001fd80`
- `0x18001fdb0`
- `0x180020670`
- `0x180030790`
- `0x180047120`
- `0x180047520`
- `0x1800475c0`
- `0x18004ae40`
- `0x18004b6d0`
- `0x1800567e0`
- `0x1800611a0`
- `0x180067b60`
- `0x1800680b0`
- `0x180078d00`
- `0x180078d10`
- `0x180088000`
- `0x1801d1e70`
- `0x1801d31d8`
- `0x1801d32f0`
- `0x1801f7110`
- `0x1801f7160`
- `0x1801f7190`
- `0x1801f97e0`
- `0x180206a58`
- `0x18023a270`
- `0x180242120`
- `0x180242ca0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18023b1b3`
- `KERNEL32!CloseHandle` at `0x18023b40a`
- `KERNEL32!CloseHandle` at `0x18023b428`
- `KERNEL32!CloseHandle` at `0x18023b55e`
- `KERNEL32!CloseHandle` at `0x18023b71b`
- `KERNEL32!CloseHandle` at `0x18023b1b3`
- `KERNEL32!CloseHandle` at `0x18023b40a`
- `KERNEL32!CloseHandle` at `0x18023b428`
- `KERNEL32!CloseHandle` at `0x18023b55e`
- `KERNEL32!CloseHandle` at `0x18023b71b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18023b3f2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18023b3f2`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18023b3b7`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18023b3b7`

## string_xrefs

- `0x18023a852`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\EmbeddingHelpers.cpp`
- `0x18023a860`: `struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::VectorSpaceResolutionAndQuantizationPreference __cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ResolveVectorSpacesAndGetQuantizationPreference(const struct winrt::hstring &,class std::span<unsigned char const ,-1>,enum winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IndexCreationDisposition,enum winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::`
- `0x18023a346`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18023b2b3`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18023a59b`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x18023a9c7`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x18023b13d`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x18023b444`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x18023ac14`: `Failed to find given vector space in registry`
- `0x18023a4ef`: `could not get exclusive access to the database lock file`
- `0x18023a4da`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\SemanticTextIndexStore.cpp`
- `0x18023abff`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\SemanticTextIndexStore.cpp`
- `0x18023b68d`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\SemanticTextIndexStore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=30
void __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore::InitializeAsync__ResumeCoro_1(
        char *Block)
{
  _WORD *v2; // r13
  char v3; // si
  _QWORD *v4; // r13
  __int64 v5; // rcx
  char *v6; // rdi
  __int64 (__fastcall ***v7)(_QWORD, __int64 *, char *); // rcx
  int v8; // eax
  __int64 v9; // rax
  const wchar_t *v10; // rdx
  __int64 v11; // r8
  __int64 appended; // rsi
  void *v13; // rax
  __int64 v14; // rsi
  int v15; // eax
  HANDLE ProcessHeap; // rax
  unsigned int *v17; // rax
  char *v18; // rcx
  __int64 v19; // rcx
  int v20; // eax
  char v21; // al
  __int64 (__fastcall ***v22)(_QWORD, __int64 *, char *); // rcx
  int v23; // eax
  __int64 v24; // rcx
  int v25; // eax
  __int64 (__fastcall ***v26)(_QWORD, __int64 *, char *); // rcx
  int v27; // eax
  char *v28; // rdi
  __int64 (__fastcall ***v29)(_QWORD, __int64 *, char *); // rcx
  int v30; // eax
  const wchar_t *v31; // rdx
  __int64 v32; // r8
  __int64 v33; // rax
  int v34; // ecx
  HANDLE v35; // rax
  __int64 v36; // rcx
  int v37; // eax
  char v38; // al
  __int64 (__fastcall ***v39)(_QWORD, __int64 *, char *); // rcx
  int v40; // eax
  char *v41; // rdi
  __int64 (__fastcall ***v42)(_QWORD, __int64 *, char *); // rcx
  int v43; // eax
  __int64 v44; // rax
  int v45; // ecx
  HANDLE v46; // rax
  const struct asg::SemanticRegistry::VectorSpaceRegistry *v47; // rax
  void *v48; // rax
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 v51; // rdi
  __int64 (__fastcall ***v52)(_QWORD, __int64 *, char *); // rcx
  int v53; // eax
  char *v54; // r13
  __int64 v55; // rcx
  int v56; // eax
  _OWORD *v57; // rax
  __int64 v58; // rax
  __int64 v59; // rsi
  __int64 v60; // rdi
  volatile signed __int32 *v61; // r12
  int v62; // r15d
  void *v63; // rdi
  HANDLE v64; // rax
  volatile signed __int32 *v65; // rdi
  __int64 (__fastcall ***v66)(_QWORD, __int64 *, char *); // rcx
  int v67; // eax
  __int64 v68; // rcx
  int v69; // eax
  __int64 v70; // rcx
  void *v71; // r12
  HANDLE *v72; // rdi
  void *v73; // rsi
  unsigned int v74; // r8d
  const char *v75; // r9
  wil::details::in1diag3 *v76; // rcx
  volatile __int64 *v77; // rdi
  char v78; // r15
  volatile __int64 *v79; // rdi
  unsigned int *v80; // rax
  volatile signed __int32 *v81; // rdi
  char v82; // [rsp+50h] [rbp-338h]
  __int64 v83; // [rsp+58h] [rbp-330h]
  int v84; // [rsp+60h] [rbp-328h]
  __int128 v85; // [rsp+80h] [rbp-308h]
  __int64 v86; // [rsp+80h] [rbp-308h]
  __int64 v87; // [rsp+A8h] [rbp-2E0h]
  __int64 v88; // [rsp+B0h] [rbp-2D8h]
  _WORD *v89; // [rsp+C8h] [rbp-2C0h]
  void *v90; // [rsp+D0h] [rbp-2B8h]
  _BYTE v91[40]; // [rsp+D8h] [rbp-2B0h]
  void *v92; // [rsp+108h] [rbp-280h]
  __int128 v93; // [rsp+110h] [rbp-278h]
  __int64 v94; // [rsp+130h] [rbp-258h]
  void *v95; // [rsp+178h] [rbp-210h]
  _BYTE pExceptionObject[24]; // [rsp+180h] [rbp-208h] BYREF
  _BYTE v97[24]; // [rsp+198h] [rbp-1F0h] BYREF
  _BYTE v98[24]; // [rsp+1B0h] [rbp-1D8h] BYREF
  _BYTE v99[24]; // [rsp+1C8h] [rbp-1C0h] BYREF
  _BYTE v100[32]; // [rsp+1E0h] [rbp-1A8h] BYREF
  __int64 v101; // [rsp+200h] [rbp-188h]
  __int64 v102; // [rsp+208h] [rbp-180h]
  _BYTE v103[48]; // [rsp+218h] [rbp-170h] BYREF
  __int128 v104; // [rsp+248h] [rbp-140h]
  __int128 v105; // [rsp+258h] [rbp-130h]
  wil::details::in1diag3 *retaddr; // [rsp+388h] [rbp+0h]

  v2 = Block + 144;
  v89 = Block + 144;
  switch ( *((_WORD *)Block + 72) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_168;
    case 2:
      v3 = asg::IsFeatureEnabled<wil::Feature<__WilFeatureTraits_Feature_57696949>>(Block);
      v82 = v3;
      v4 = Block + 136;
      v5 = *((_QWORD *)Block + 17);
      *((_QWORD *)Block + 19) = v5;
      if ( v5 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
      winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::GetDbAesKeyStore(
        Block + 160,
        Block + 152);
      *((_QWORD *)Block + 24) = 0;
      if ( v3 )
      {
        v6 = Block + 784;
        *((_QWORD *)Block + 98) = 0;
        v7 = (__int64 (__fastcall ***)(_QWORD, __int64 *, char *))*v4;
        *((_DWORD *)Block + 200) = 3339;
        *((_QWORD *)Block + 101) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Gene"
                                   "rated Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
        *((_QWORD *)Block + 102) = 0;
        v8 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64 *, char *), char *))(*v7)[6])(
               v7,
               Block + 784);
        if ( v8 < 0 )
        {
          _mm_lfence();
          winrt::throw_hresult((unsigned int)v8, Block + 800);
        }
        v9 = *(_QWORD *)v6;
        *((_QWORD *)Block + 29) = *(_QWORD *)v6;
        if ( v9 )
          v10 = *(const wchar_t **)(v9 + 16);
        else
          v10 = &String;
        v11 = -1;
        do
          ++v11;
        while ( v10[v11] );
        *(_OWORD *)(Block + 200) = 0;
        *((_QWORD *)Block + 27) = 0;
        *((_QWORD *)Block + 28) = 0;
        std::basic_string<char16_t>::_Construct<1,char16_t const *>(Block + 200);
        appended = winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::AppendDbExtensionIfRequired(
                     (__int64)(Block + 240),
                     (std::filesystem *)(Block + 200));
        v13 = operator new(0x30u);
        *((_QWORD *)Block + 103) = v13;
        *((_OWORD *)Block + 52) = *(_OWORD *)appended;
        *((_OWORD *)Block + 53) = *(_OWORD *)(appended + 16);
        *(_QWORD *)(appended + 16) = 0;
        *(_QWORD *)(appended + 24) = 7;
        *(_WORD *)appended = 0;
        v14 = winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexLockFile::IndexLockFile(
                (__int64)v13,
                (__int64)(Block + 832),
                0);
        *((_QWORD *)Block + 24) = v14;
        std::basic_string<char16_t>::_Tidy_deallocate(Block + 240);
        if ( *(_QWORD *)v6 )
        {
          v15 = _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)v6 + 24LL));
          if ( v15 )
          {
            if ( v15 < 0 )
              abort();
          }
          else
          {
            v95 = *(void **)v6;
            ProcessHeap = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(ProcessHeap, 0, v95);
          }
        }
        if ( *(_QWORD *)(v14 + 40) == -1 )
        {
          *((_DWORD *)Block + 68) = 332;
          *((_QWORD *)Block + 35) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\Semantic"
                                    "TextIndexStore.cpp";
          *((_QWORD *)Block + 36) = 0;
          winrt::param::hstring::hstring(
            (winrt::param::hstring *)(Block + 296),
            L"could not get exclusive access to the database lock file");
          v17 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)(Block + 328), -2081706721);
          winrt::hresult_error::hresult_error(pExceptionObject, *v17, Block + 296, Block + 272);
          throw (winrt::hresult_error *)pExceptionObject;
        }
        v3 = v82;
      }
      v84 = 2;
      v18 = Block + 136;
      if ( v3 )
      {
        v19 = *(_QWORD *)winrt::impl::consume_Microsoft_Asg_SemanticIndex_AiFabric_Compatibility_ISemanticTextIndexStoreOptions4<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions>::VectorSpaceId(
                           v18,
                           Block + 336);
        if ( v19 )
        {
          *(_OWORD *)(Block + 872) = 0;
          *((_DWORD *)Block + 224) = 1984;
          *((_QWORD *)Block + 113) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Ge"
                                     "nerated Files\\winrt\\Windows.Foundation.h";
          *((_QWORD *)Block + 114) = 0;
          v20 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v19 + 48LL))(v19, Block + 872);
          if ( v20 < 0 )
          {
            _mm_lfence();
            winrt::throw_hresult((unsigned int)v20, Block + 896);
          }
          v104 = *(_OWORD *)(Block + 872);
          *(_OWORD *)(Block + 344) = v104;
          v21 = 1;
        }
        else
        {
          v21 = 0;
        }
        Block[360] = v21;
        *((_DWORD *)Block + 216) = 0;
        v22 = (__int64 (__fastcall ***)(_QWORD, __int64 *, char *))*v4;
        if ( *v4 )
        {
          *((_QWORD *)Block + 123) = 0;
          v23 = (**v22)(
                  v22,
                  &winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreOptions5>,
                  Block + 984);
          v24 = *((_QWORD *)Block + 123);
        }
        else
        {
          v23 = 0;
          v24 = 0;
        }
        *((_QWORD *)Block + 118) = v24;
        *((_DWORD *)Block + 230) = 3454;
        *((_QWORD *)Block + 116) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Gene"
                                   "rated Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
        *((_QWORD *)Block + 117) = 0;
        if ( v23 < 0 )
        {
          _mm_lfence();
          winrt::throw_hresult((unsigned int)v23, Block + 920);
        }
        *((_DWORD *)Block + 238) = 3456;
        *((_QWORD *)Block + 120) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Gene"
                                   "rated Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
        *((_QWORD *)Block + 121) = 0;
        v25 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)Block + 118) + 48LL))(
                *((_QWORD *)Block + 118),
                Block + 864);
        if ( v25 < 0 )
        {
          _mm_lfence();
          winrt::throw_hresult((unsigned int)v25, Block + 952);
        }
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(Block + 944);
        *((_DWORD *)Block + 244) = 0;
        v26 = (__int64 (__fastcall ***)(_QWORD, __int64 *, char *))*v4;
        *((_DWORD *)Block + 248) = 3357;
        *((_QWORD *)Block + 125) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Gene"
                                   "rated Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
        *((_QWORD *)Block + 126) = 0;
        v27 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64 *, char *)))(*v26)[7])(v26);
        if ( v27 < 0 )
        {
          _mm_lfence();
          winrt::throw_hresult((unsigned int)v27, Block + 992);
        }
        *((_QWORD *)Block + 47) = *((_QWORD *)Block + 21);
        *((_QWORD *)Block + 48) = *((_QWORD *)Block + 22) - *((_QWORD *)Block + 21);
        v28 = Block + 1016;
        *((_QWORD *)Block + 127) = 0;
        v29 = (__int64 (__fastcall ***)(_QWORD, __int64 *, char *))*v4;
        *((_DWORD *)Block + 256) = 3339;
        *((_QWORD *)Block + 129) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Gene"
                                   "rated Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
        *((_QWORD *)Block + 130) = 0;
        v30 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64 *, char *), char *))(*v29)[6])(
                v29,
                Block + 1016);
        if ( v30 < 0 )
        {
          _mm_lfence();
          winrt::throw_hresult((unsigned int)v30, Block + 1024);
        }
        *((_QWORD *)Block + 46) = *(_QWORD *)v28;
        v105 = *(_OWORD *)(Block + 376);
        *((_OWORD *)Block + 46) = v105;
        *((_DWORD *)Block + 262) = *((_DWORD *)Block + 216);
        *((_DWORD *)Block + 264) = *((_DWORD *)Block + 244);
        if ( *(_QWORD *)v28 )
          v31 = *(const wchar_t **)(*(_QWORD *)v28 + 16LL);
        else
          v31 = &String;
        v32 = -1;
        do
          ++v32;
        while ( v31[v32] );
        *((_OWORD *)Block + 67) = 0;
        *((_QWORD *)Block + 136) = 0;
        *((_QWORD *)Block + 137) = 0;
        std::basic_string<char16_t>::_Construct<1,char16_t const *>(Block + 1072);
        winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::AppendDbExtensionIfRequired(
          (__int64)(Block + 1104),
          (std::filesystem *)(Block + 1072));
        *((_DWORD *)Block + 284) = 333;
        *((_DWORD *)Block + 285) = 16;
        *((_QWORD *)Block + 143) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\EmbeddingHelpers.cpp";
        *((_QWORD *)Block + 144) = "struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation:"
                                   ":VectorSpaceResolutionAndQuantizationPreference __cdecl winrt::Microsoft::Asg::Semant"
                                   "icIndex::AiFabric::Compatibility::implementation::ResolveVectorSpacesAndGetQuantizati"
                                   "onPreference(const struct winrt::hstring &,class std::span<unsigned char const ,-1>,e"
                                   "num winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IndexCreationDispo"
                                   "sition,enum winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IndexQuant"
                                   "izationDisposition,const class std::optional<struct winrt::guid> &,const struct winrt::guid &)";
        *((_QWORD *)Block + 145) = Block + 1048;
        *((_QWORD *)Block + 146) = Block + 1056;
        *((_QWORD *)Block + 147) = Block + 1104;
        *((_QWORD *)Block + 148) = Block + 344;
        *((_QWORD *)Block + 149) = &winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SpaceV6::VectorSpaceId;
        *((_QWORD *)Block + 150) = Block + 736;
        v33 = winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticIndexCall__winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ResolveVectorSpacesAndGetQuantizationPreference_::_2_::_lambda_1___(v103);
        v93 = *(_OWORD *)v33;
        v85 = *(_OWORD *)(v33 + 16);
        v83 = *(_QWORD *)(v33 + 32);
        v84 = *(_DWORD *)(v33 + 40);
        std::basic_string<char16_t>::_Tidy_deallocate(Block + 1104);
        if ( *(_QWORD *)v28 )
        {
          v34 = _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)v28 + 24LL));
          if ( v34 )
          {
            if ( v34 < 0 )
              abort();
          }
          else
          {
            v92 = *(void **)v28;
            v35 = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(v35, 0, v92);
          }
        }
        if ( *((_QWORD *)Block + 42) )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(Block + 336);
        *(_OWORD *)v91 = v93;
        *(_OWORD *)&v91[16] = v85;
        *(_QWORD *)&v91[32] = v83;
        v4 = Block + 136;
      }
      else
      {
        v36 = *(_QWORD *)winrt::impl::consume_Microsoft_Asg_SemanticIndex_AiFabric_Compatibility_ISemanticTextIndexStoreOptions4<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions>::VectorSpaceId(
                           v18,
                           Block + 392);
        if ( v36 )
        {
          *(_OWORD *)(Block + 1208) = 0;
          *((_DWORD *)Block + 308) = 1984;
          *((_QWORD *)Block + 155) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Ge"
                                     "nerated Files\\winrt\\Windows.Foundation.h";
          *((_QWORD *)Block + 156) = 0;
          v37 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v36 + 48LL))(v36, Block + 1208);
          if ( v37 < 0 )
          {
            _mm_lfence();
            winrt::throw_hresult((unsigned int)v37, Block + 1232);
          }
          v105 = *(_OWORD *)(Block + 1208);
          *((_OWORD *)Block + 25) = v105;
          v38 = 1;
        }
        else
        {
          v38 = 0;
        }
        Block[416] = v38;
        *((_DWORD *)Block + 266) = 0;
        v39 = (__int64 (__fastcall ***)(_QWORD, __int64 *, char *))*v4;
        *((_DWORD *)Block + 314) = 3357;
        *((_QWORD *)Block + 158) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Gene"
                                   "rated Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
        *((_QWORD *)Block + 159) = 0;
        v40 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64 *, char *)))(*v39)[7])(v39);
        if ( v40 < 0 )
        {
          _mm_lfence();
          winrt::throw_hresult((unsigned int)v40, Block + 1256);
        }
        *((_QWORD *)Block + 54) = *((_QWORD *)Block + 21);
        *((_QWORD *)Block + 55) = *((_QWORD *)Block + 22) - *((_QWORD *)Block + 21);
        v41 = Block + 1280;
        *((_QWORD *)Block + 160) = 0;
        v42 = (__int64 (__fastcall ***)(_QWORD, __int64 *, char *))*v4;
        *((_DWORD *)Block + 322) = 3339;
        *((_QWORD *)Block + 162) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Gene"
                                   "rated Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
        *((_QWORD *)Block + 163) = 0;
        v43 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64 *, char *), char *))(*v42)[6])(
                v42,
                Block + 1280);
        if ( v43 < 0 )
        {
          _mm_lfence();
          winrt::throw_hresult((unsigned int)v43, Block + 1288);
        }
        *((_QWORD *)Block + 53) = *(_QWORD *)v41;
        v104 = *((_OWORD *)Block + 27);
        *((_OWORD *)Block + 47) = v104;
        v44 = winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ResolveCurrentAndPreviousVectorSpace(
                (unsigned int)v103,
                (int)Block + 424,
                (int)Block + 752,
                *((_DWORD *)Block + 266),
                (__int64)(Block + 400),
                (__int64)&winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SpaceV6::VectorSpaceId);
        *(_OWORD *)v91 = *(_OWORD *)v44;
        *(_OWORD *)&v91[16] = *(_OWORD *)(v44 + 16);
        *(_QWORD *)&v91[32] = *(_QWORD *)(v44 + 32);
        if ( *(_QWORD *)v41 )
        {
          v45 = _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)v41 + 24LL));
          if ( v45 )
          {
            if ( v45 < 0 )
              abort();
          }
          else
          {
            v90 = *(void **)v41;
            v46 = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(v46, 0, v90);
          }
        }
        if ( *((_QWORD *)Block + 49) )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(Block + 392);
      }
      v47 = asg::SemanticRegistry::VectorSpaceRegistry::Instance();
      *((_OWORD *)Block + 48) = *(_OWORD *)&v91[4];
      asg::SemanticRegistry::VectorSpaceRegistry::GetVectorSpace(v47, Block + 448);
      if ( !*((_QWORD *)Block + 56) )
      {
        *((_DWORD *)Block + 116) = 366;
        *((_QWORD *)Block + 59) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\SemanticTe"
                                  "xtIndexStore.cpp";
        *((_QWORD *)Block + 60) = 0;
        winrt::param::hstring::hstring(
          (winrt::param::hstring *)(Block + 488),
          L"Failed to find given vector space in registry");
        winrt::hresult_invalid_argument::hresult_invalid_argument(
          (winrt::hresult_invalid_argument *)v97,
          (const struct winrt::param::hstring *)(Block + 488),
          (const struct winrt::impl::slim_source_location *)(Block + 464));
        throw (winrt::hresult_invalid_argument *)v97;
      }
      *(_OWORD *)(Block + 536) = 0;
      *(_OWORD *)(Block + 520) = *(_OWORD *)&v91[4];
      if ( v91[36] )
        *(_OWORD *)(Block + 536) = *(_OWORD *)&v91[20];
      v48 = operator new(0x1B8u);
      *((_QWORD *)Block + 165) = v48;
      *((_OWORD *)Block + 84) = *(_OWORD *)&v91[4];
      winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator::TextEmbeddingsGenerator(v48);
      **((_QWORD **)Block + 165) = &winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator::`vftable';
      *((_OWORD *)Block + 83) = 0;
      if ( memcmp(Block + 536, Block + 1328, 0x10u) )
      {
        v49 = *((_QWORD *)Block + 165);
        *(_OWORD *)(v49 + 272) = *(_OWORD *)(Block + 536);
        if ( !*(_BYTE *)(v49 + 288) )
          *(_BYTE *)(v49 + 288) = 1;
      }
      **((_QWORD **)Block + 165) = &winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::`vftable';
      v50 = *((_QWORD *)Block + 165);
      v51 = v50 + 16;
      *((_QWORD *)Block + 170) = v50 + 16;
      *((_QWORD *)Block + 69) = v50 + 16;
      *((_QWORD *)Block + 70) = v50 + 16;
      if ( v50 != -16 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 8LL))(v50 + 16);
      v88 = *((_QWORD *)Block + 56);
      *((_DWORD *)Block + 342) = 0;
      v52 = (__int64 (__fastcall ***)(_QWORD, __int64 *, char *))*v4;
      *((_DWORD *)Block + 344) = 3357;
      *((_QWORD *)Block + 173) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Genera"
                                 "ted Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
      *((_QWORD *)Block + 174) = 0;
      v53 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64 *, char *)))(*v52)[7])(v52);
      if ( v53 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v53, Block + 1376);
      }
      v102 = *((_QWORD *)Block + 22);
      v87 = v102 - *((_QWORD *)Block + 21);
      v94 = *((_QWORD *)Block + 21);
      v101 = v94;
      v54 = Block + 1400;
      *((_QWORD *)Block + 175) = 0;
      v55 = *((_QWORD *)Block + 17);
      *((_DWORD *)Block + 352) = 3339;
      *((_QWORD *)Block + 177) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Genera"
                                 "ted Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
      *((_QWORD *)Block + 178) = 0;
      v56 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v55 + 48LL))(v55, Block + 1400);
      if ( v56 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v56, Block + 1408);
      }
      *((_QWORD *)Block + 73) = *(_QWORD *)v54;
      v57 = operator new(0x188u);
      *((_QWORD *)Block + 179) = v57;
      *v57 = 0;
      *(_DWORD *)(*((_QWORD *)Block + 179) + 8LL) = 1;
      *(_DWORD *)(*((_QWORD *)Block + 179) + 12LL) = 1;
      **((_QWORD **)Block + 179) = &std::_Ref_count_obj2<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>>::`vftable';
      v86 = *((_QWORD *)Block + 179) + 16LL;
      *((_QWORD *)Block + 181) = Block + 1440;
      v58 = *((_QWORD *)Block + 24);
      *((_QWORD *)Block + 24) = 0;
      *((_QWORD *)Block + 180) = v58;
      *((_QWORD *)Block + 183) = Block + 1456;
      *((_QWORD *)Block + 182) = v51;
      if ( v51 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 8LL))(v51);
      *((_QWORD *)Block + 185) = Block + 1472;
      *((_QWORD *)Block + 184) = v51;
      if ( v51 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 8LL))(v51);
      *((_QWORD *)Block + 190) = v94;
      *((_QWORD *)Block + 191) = v87;
      *((_OWORD *)Block + 93) = 0;
      *((_QWORD *)Block + 188) = 0;
      *((_QWORD *)Block + 189) = 0;
      std::basic_string<char16_t>::_Construct<1,char16_t const *>(Block + 1488);
      *((_OWORD *)Block + 96) = *((_OWORD *)Block + 95);
      winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>(
        v86,
        (_DWORD)Block + 1488,
        (_DWORD)Block + 1536,
        *((_DWORD *)Block + 342),
        v88,
        0,
        v84,
        (__int64)(Block + 1472),
        (__int64)(Block + 1456),
        (__int64)(Block + 1440));
      v59 = *((_QWORD *)Block + 179) + 16LL;
      *((_QWORD *)Block + 71) = v59;
      v60 = *((_QWORD *)Block + 16);
      v61 = (volatile signed __int32 *)std::_Locked_pointer<std::_Ref_count_base>::_Lock_and_load((int)v60 + 136);
      *(_QWORD *)(v60 + 128) = v59;
      if ( (_InterlockedExchange64((volatile __int64 *)(v60 + 136), *((_QWORD *)Block + 179)) & 3) == 2 )
        _std_atomic_notify_all_direct(v60 + 136);
      if ( v61 )
      {
        if ( _InterlockedExchangeAdd(v61 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v61)(v61);
          if ( _InterlockedExchangeAdd(v61 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v61 + 8LL))(v61);
        }
      }
      if ( *(_QWORD *)v54 )
      {
        v62 = _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)v54 + 24LL));
        if ( v62 )
        {
          if ( v62 < 0 )
            abort();
        }
        else
        {
          v63 = *(void **)v54;
          v64 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v64, 0, v63);
        }
      }
      ImpersonationHelper::GetThreadImpersonationToken(Block + 592);
      Block[600] = 0;
      if ( *((_DWORD *)Block + 28) == 2 )
      {
        *((_DWORD *)Block + 408) = 5672;
        *((_QWORD *)Block + 205) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Gene"
                                   "rated Files\\winrt\\Windows.Foundation.h";
        *((_QWORD *)Block + 206) = 0;
        winrt::hresult_canceled::hresult_canceled(
          (winrt::hresult_canceled *)v98,
          (const struct winrt::impl::slim_source_location *)(Block + 1632));
        throw (winrt::hresult_canceled *)v98;
      }
      *v89 = 4;
      `winrt::resume_background'::`2'::awaitable::await_suspend(4, Block);
      return;
    case 4:
      *((_DWORD *)Block + 415) = 0;
      v66 = (__int64 (__fastcall ***)(_QWORD, __int64 *, char *))*((_QWORD *)Block + 17);
      if ( v66 )
      {
        *((_QWORD *)Block + 215) = 0;
        v67 = (**v66)(
                v66,
                &winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreOptions3>,
                Block + 1720);
        v68 = *((_QWORD *)Block + 215);
      }
      else
      {
        v67 = 0;
        v68 = 0;
      }
      *((_QWORD *)Block + 208) = v68;
      *((_DWORD *)Block + 418) = 3386;
      *((_QWORD *)Block + 210) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Genera"
                                 "ted Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
      *((_QWORD *)Block + 211) = 0;
      if ( v67 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v67, Block + 1672);
      }
      *((_DWORD *)Block + 424) = 3388;
      *((_QWORD *)Block + 213) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Genera"
                                 "ted Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
      *((_QWORD *)Block + 214) = 0;
      v69 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)Block + 208) + 48LL))(
              *((_QWORD *)Block + 208),
              Block + 1660);
      if ( v69 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v69, Block + 1696);
      }
      winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(Block + 1664);
      if ( (Block[1660] & 1) == 0 )
        goto LABEL_158;
      v70 = *((_QWORD *)Block + 170);
      *((_QWORD *)Block + 76) = v70;
      if ( v70 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 8LL))(v70);
      v71 = (void *)*((_QWORD *)Block + 74);
      if ( v71 )
      {
        v72 = (HANDLE *)(Block + 1752);
        ImpersonationHelper::GetThreadImpersonationToken(Block + 1752);
        v73 = (void *)*((_QWORD *)Block + 219);
        *((_QWORD *)Block + 219) = 0;
        *((_QWORD *)Block + 220) = v73;
        if ( !ImpersonateLoggedOnUser(v71) )
          wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x1C, v74, v75);
        winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore::InitializeAsync_::_22_::_lambda_1_::operator()(
          Block + 608,
          Block + 616);
        if ( v73 != (void *)-1LL )
        {
          if ( !SetThreadToken(0, v73) )
            wil::details::in1diag3::_FailFastImmediate_Unexpected(v76);
          if ( v73 )
            CloseHandle(v73);
        }
        if ( *v72 && *v72 != (HANDLE)-1LL )
          CloseHandle(*v72);
      }
      else
      {
        winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore::InitializeAsync_::_22_::_lambda_1_::operator()(
          Block + 608,
          Block + 616);
      }
      if ( *((_DWORD *)Block + 28) == 2 )
      {
        *((_DWORD *)Block + 432) = 5672;
        *((_QWORD *)Block + 217) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Gene"
                                   "rated Files\\winrt\\Windows.Foundation.h";
        *((_QWORD *)Block + 218) = 0;
        winrt::hresult_canceled::hresult_canceled(
          (winrt::hresult_canceled *)v99,
          (const struct winrt::impl::slim_source_location *)(Block + 1728));
        throw (winrt::hresult_canceled *)v99;
      }
      *((_QWORD *)Block + 78) = 0;
      *((_QWORD *)Block + 79) = Block + 616;
      *((_QWORD *)Block + 80) = 0;
      Block[648] = 1;
      *v2 = 6;
      if ( (unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator>,winrt::guid,bool>::promise_type>(
                              (_QWORD *)Block + 78,
                              (__int64)Block) )
        return;
LABEL_149:
      v78 = winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_resume(Block + 624);
      if ( *((_QWORD *)Block + 78) )
      {
        v79 = (volatile __int64 *)*((_QWORD *)Block + 78);
        while ( _InterlockedExchange64(v79, 0) == 1 )
          Thrd_yield();
      }
      if ( *((_QWORD *)Block + 77) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(Block + 616);
      if ( *((_QWORD *)Block + 76) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(Block + 608);
      if ( !v78 )
      {
        *((_DWORD *)Block + 164) = 408;
        *((_QWORD *)Block + 83) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\SemanticTe"
                                  "xtIndexStore.cpp";
        *((_QWORD *)Block + 84) = 0;
        winrt::param::hstring::hstring(
          (winrt::param::hstring *)(Block + 680),
          L"Failed to load text embedding model - migration of underlying index may be required");
        v80 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)(Block + 712), -2081706723);
        winrt::hresult_error::hresult_error(v100, *v80, Block + 680, Block + 656);
        throw (winrt::hresult_error *)v100;
      }
LABEL_158:
      if ( *((_QWORD *)Block + 74) && *((_QWORD *)Block + 74) != -1 )
        CloseHandle(*((HANDLE *)Block + 74));
      if ( *((_QWORD *)Block + 170) )
      {
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(Block + 560);
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(Block + 552);
      }
      if ( *((_QWORD *)Block + 57) )
      {
        v81 = (volatile signed __int32 *)*((_QWORD *)Block + 57);
        if ( _InterlockedExchangeAdd(v81 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v81)(v81);
          if ( _InterlockedExchangeAdd(v81 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v81 + 8LL))(v81);
        }
      }
      std::vector<unsigned char,asg::secure_allocator<unsigned char>>::_Tidy(Block + 160);
      *((_QWORD *)Block + 90) = Block + 16;
      *v2 = 0;
      *(_QWORD *)Block = 0;
      if ( !(unsigned __int8)winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator> &,winrt::com_ptr<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore>,asg::CancellationTokenSource>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::final_suspend_awaiter::await_suspend() )
      {
LABEL_168:
        if ( *((_QWORD *)Block + 13) )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(Block + 104);
        if ( *((_QWORD *)Block + 12) )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(Block + 96);
        __ExceptionPtrDestroy(Block + 72);
        winrt::impl::root_implements<winrt::iterable_base<winrt::impl::map_impl<winrt::hstring,winrt::hstring,std::map<winrt::hstring,winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::hstring>,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::hstring>>>::subtract_final_reference(Block + 16);
        if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
          abort();
        if ( *((_QWORD *)Block + 17) )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(Block + 136);
        if ( *((_WORD *)Block + 73) )
          operator delete(Block);
      }
      return;
    case 5:
      if ( *((_QWORD *)Block + 74) && *((_QWORD *)Block + 74) != -1 )
        CloseHandle(*((HANDLE *)Block + 74));
      if ( *((_QWORD *)Block + 170) )
      {
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(Block + 560);
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(Block + 552);
      }
      if ( *((_QWORD *)Block + 57) )
      {
        v65 = (volatile signed __int32 *)*((_QWORD *)Block + 57);
        if ( _InterlockedExchangeAdd(v65 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v65)(v65);
          if ( _InterlockedExchangeAdd(v65 + 3, 0xFFFFFFFF) == 1 )
            goto LABEL_105;
        }
      }
      goto LABEL_106;
    case 6:
      goto LABEL_149;
    case 7:
      if ( *((_QWORD *)Block + 78) )
      {
        v77 = (volatile __int64 *)*((_QWORD *)Block + 78);
        while ( _InterlockedExchange64(v77, 0) == 1 )
          Thrd_yield();
      }
      if ( *((_QWORD *)Block + 77) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(Block + 616);
      if ( *((_QWORD *)Block + 76) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(Block + 608);
      if ( *((_QWORD *)Block + 74) && *((_QWORD *)Block + 74) != -1 )
        CloseHandle(*((HANDLE *)Block + 74));
      if ( *((_QWORD *)Block + 170) )
      {
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(Block + 560);
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(Block + 552);
      }
      if ( *((_QWORD *)Block + 57) )
      {
        v65 = (volatile signed __int32 *)*((_QWORD *)Block + 57);
        if ( _InterlockedExchangeAdd(v65 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v65)(v65);
          if ( _InterlockedExchangeAdd(v65 + 3, 0xFFFFFFFF) == 1 )
LABEL_105:
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v65 + 8LL))(v65);
        }
      }
LABEL_106:
      std::vector<unsigned char,asg::secure_allocator<unsigned char>>::_Tidy(Block + 160);
      goto LABEL_168;
    default:
      __debugbreak();
      return;
  }
}

```

## disassembly

```asm
0x18023a270  mov     r11, rsp
0x18023a273  mov     [r11+10h], rbx
0x18023a277  mov     [r11+18h], rsi
0x18023a27b  mov     [r11+8], rcx
0x18023a27f  push    rdi
0x18023a280  push    r12
0x18023a282  push    r13
0x18023a284  push    r14
0x18023a286  push    r15
0x18023a288  sub     rsp, 360h
0x18023a28f  mov     rax, cs:__security_cookie
0x18023a296  xor     rax, rsp
0x18023a299  mov     [rsp+388h+var_30], rax
0x18023a2a1  mov     rbx, rcx
0x18023a2a4  mov     [rsp+388h+var_2C8], rcx
0x18023a2ac  lea     r13, [rbx+90h]
0x18023a2b3  mov     [rsp+388h+var_2C0], r13
0x18023a2bb  movzx   eax, word ptr [r13+0]
0x18023a2c0  mov     [rsp+388h+var_2F8], ax
0x18023a2c8  inc     ax; switch 9 cases
0x18023a2cb  cmp     ax, 8
0x18023a2cf  ja      def_18023A2EA; jumptable 000000018023A2EA default case, case 0
0x18023a2d5  movsx   rax, ax
0x18023a2d9  lea     rdx, cs:180000000h
0x18023a2e0  mov     ecx, ds:(jpt_18023A2EA - 180000000h)[rdx+rax*4]
0x18023a2e7  add     rcx, rdx
0x18023a2ea  jmp     rcx; switch jump
0x18023a2ec  mov     r15, 0FFFFFFFFFFFFFFFFh; jumptable 000000018023A2EA case 3
0x18023a2f3  jmp     loc_18023B807
0x18023a2f8  xor     r14d, r14d; jumptable 000000018023A2EA case 2
0x18023a2fb  call    ??$IsFeatureEnabled@V?$Feature@U__WilFeatureTraits_Feature_57696949@@@wil@@@asg@@YA_NXZ; asg::IsFeatureEnabled<wil::Feature<__WilFeatureTraits_Feature_57696949>>(void)
0x18023a300  movzx   esi, al
0x18023a303  mov     [rsp+388h+var_338], al
0x18023a307  lea     r13, [rbx+88h]
0x18023a30e  mov     rcx, [r13+0]
0x18023a312  mov     [rbx+98h], rcx
0x18023a319  test    rcx, rcx
0x18023a31c  jz      short loc_18023A32B
0x18023a31e  mov     rdx, [rcx]
0x18023a321  mov     rax, [rdx+8]
0x18023a325  call    cs:__guard_dispatch_icall_fptr
0x18023a32b  lea     rcx, [rbx+0A0h]
0x18023a332  lea     rdx, [rbx+98h]
0x18023a339  call    ?GetDbAesKeyStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@YA?AUDbAesKeyStore@Sqlite@asg@@USemanticTextIndexStoreOptions@234567@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::GetDbAesKeyStore(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions)
0x18023a33e  nop
0x18023a33f  mov     [rbx+0C0h], r14
0x18023a346  lea     r12, aCW1SX64Release_8; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18023a34d  test    sil, sil
0x18023a350  jz      loc_18023A544
0x18023a356  lea     rdi, [rbx+310h]
0x18023a35d  mov     [rdi], r14
0x18023a360  mov     rcx, [r13+0]
0x18023a364  mov     dword ptr [rbx+320h], 0D0Bh
0x18023a36e  mov     [rbx+328h], r12
0x18023a375  mov     [rbx+330h], r14
0x18023a37c  mov     rax, [rcx]
0x18023a37f  mov     rdx, rdi
0x18023a382  mov     rax, [rax+30h]
0x18023a386  call    cs:__guard_dispatch_icall_fptr
0x18023a38c  test    eax, eax
0x18023a38e  jns     short loc_18023A3A1
0x18023a390  lfence
0x18023a393  lea     rdx, [rbx+320h]
0x18023a39a  mov     ecx, eax
0x18023a39c  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18023a3a1  mov     rax, [rdi]
0x18023a3a4  mov     [rbx+0E8h], rax
0x18023a3ab  cmp     rax, 0
0x18023a3af  jz      short loc_18023A3BE
0x18023a3b1  mov     rdx, [rax+10h]
0x18023a3b5  lea     rax, String
0x18023a3bc  jmp     short loc_18023A3C8
0x18023a3be  lea     rax, String
0x18023a3c5  mov     rdx, rax
0x18023a3c8  mov     [rsp+388h+var_310], rax
0x18023a3cd  mov     r15, 0FFFFFFFFFFFFFFFFh
0x18023a3d4  mov     r8, r15
0x18023a3d7  nop     word ptr [rax+rax+00000000h]
0x18023a3e0  inc     r8
0x18023a3e3  cmp     word ptr [rdx+r8*2], 0
0x18023a3e9  jnz     short loc_18023A3E0
0x18023a3eb  xorps   xmm0, xmm0
0x18023a3ee  movups  xmmword ptr [rbx+0C8h], xmm0
0x18023a3f5  mov     [rbx+0D8h], r14
0x18023a3fc  mov     [rbx+0E0h], r14
0x18023a403  lea     rcx, [rbx+0C8h]
0x18023a40a  call    ??$_Construct@$00PEB_S@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXQEB_S_K@Z; std::basic_string<char16_t>::_Construct<1,char16_t const *>(char16_t const * const,unsigned __int64)
0x18023a40f  lea     rcx, [rbx+0F0h]
0x18023a416  lea     rdx, [rbx+0C8h]
0x18023a41d  call    ?AppendDbExtensionIfRequired@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@YA?AVpath@filesystem@std@@V89std@@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::AppendDbExtensionIfRequired(std::filesystem::path)
0x18023a422  mov     rsi, rax
0x18023a425  mov     ecx, 30h ; '0'; Size
0x18023a42a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18023a42f  mov     [rbx+338h], rax
0x18023a436  lea     rdx, [rbx+340h]
0x18023a43d  movups  xmm0, xmmword ptr [rsi]
0x18023a440  movups  xmmword ptr [rdx], xmm0
0x18023a443  movups  xmm1, xmmword ptr [rsi+10h]
0x18023a447  movups  xmmword ptr [rdx+10h], xmm1
0x18023a44b  mov     [rsi+10h], r14
0x18023a44f  mov     qword ptr [rsi+18h], 7
0x18023a457  xor     ecx, ecx
0x18023a459  mov     [rsi], cx
0x18023a45c  mov     [rsp+388h+var_238], rax
0x18023a464  xor     r8d, r8d
0x18023a467  mov     rcx, rax
0x18023a46a  call    ??0IndexLockFile@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAA@Vpath@filesystem@std@@_N@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexLockFile::IndexLockFile(std::filesystem::path,bool)
0x18023a46f  mov     rsi, rax
0x18023a472  mov     [rbx+0C0h], rax
0x18023a479  lea     rcx, [rbx+0F0h]
0x18023a480  call    ?_Tidy_deallocate@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXXZ; std::basic_string<char16_t>::_Tidy_deallocate(void)
0x18023a485  nop
0x18023a486  cmp     qword ptr [rdi], 0
0x18023a48a  jz      short loc_18023A4C5
0x18023a48c  mov     rcx, [rdi]
0x18023a48f  mov     eax, r15d
0x18023a492  lock xadd [rcx+18h], eax
0x18023a497  sub     eax, 1
0x18023a49a  jnz     short loc_18023A4BB
0x18023a49c  mov     rdi, [rdi]
0x18023a49f  mov     [rsp+388h+var_210], rdi
0x18023a4a7  call    WINRT_IMPL_GetProcessHeap
0x18023a4ac  mov     rcx, rax; hHeap
0x18023a4af  mov     r8, rdi; lpMem
0x18023a4b2  xor     edx, edx; dwFlags
0x18023a4b4  call    WINRT_IMPL_HeapFree
0x18023a4b9  jmp     short loc_18023A4C5
0x18023a4bb  test    eax, eax
0x18023a4bd  jns     short loc_18023A4C5
0x18023a4bf  call    abort
0x18023a4c5  cmp     qword ptr [rsi+28h], 0FFFFFFFFFFFFFFFFh
0x18023a4ca  jnz     loc_18023A559
0x18023a4d0  mov     dword ptr [rbx+110h], 14Ch
0x18023a4da  lea     rax, aCW1SSrcSemanti_28; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18023a4e1  mov     [rbx+118h], rax
0x18023a4e8  mov     [rbx+120h], r14
0x18023a4ef  lea     rdx, aCouldNotGetExc; "could not get exclusive access to the d"...
0x18023a4f6  lea     rcx, [rbx+128h]; this
0x18023a4fd  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x18023a502  lea     rcx, [rbx+148h]; this
0x18023a509  mov     edx, 83EBAD1Fh; int
0x18023a50e  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x18023a513  lea     r9, [rbx+110h]
0x18023a51a  lea     r8, [rbx+128h]
0x18023a521  mov     edx, [rax]
0x18023a523  lea     rcx, [rsp+388h+pExceptionObject]
0x18023a52b  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x18023a530  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x18023a537  lea     rcx, [rsp+388h+pExceptionObject]; pExceptionObject
0x18023a53f  call    _CxxThrowException
0x18023a544  lea     rax, String
0x18023a54b  mov     [rsp+388h+var_310], rax
0x18023a550  mov     r15, 0FFFFFFFFFFFFFFFFh
0x18023a557  jmp     short loc_18023A55E
0x18023a559  movzx   esi, [rsp+388h+var_338]
0x18023a55e  mov     [rsp+388h+var_328], 2
0x18023a566  mov     rcx, r13
0x18023a569  test    sil, sil
0x18023a56c  jz      loc_18023A993
0x18023a572  lea     rdx, [rbx+150h]
0x18023a579  call    ?VectorSpaceId@?$consume_Microsoft_Asg_SemanticIndex_AiFabric_Compatibility_ISemanticTextIndexStoreOptions4@USemanticTextIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Asg_SemanticIndex_AiFabric_Compatibility_ISemanticTextIndexStoreOptions4<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions>::VectorSpaceId(void)
0x18023a57e  nop
0x18023a57f  mov     rcx, [rax]
0x18023a582  test    rcx, rcx
0x18023a585  jz      short loc_18023A5F3
0x18023a587  xorps   xmm0, xmm0
0x18023a58a  movups  xmmword ptr [rbx+368h], xmm0
0x18023a591  mov     dword ptr [rbx+380h], 7C0h
0x18023a59b  lea     rax, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18023a5a2  mov     [rbx+388h], rax
0x18023a5a9  mov     [rbx+390h], r14
0x18023a5b0  mov     rax, [rcx]
0x18023a5b3  lea     rdx, [rbx+368h]
0x18023a5ba  mov     rax, [rax+30h]
0x18023a5be  call    cs:__guard_dispatch_icall_fptr
0x18023a5c4  test    eax, eax
0x18023a5c6  jns     short loc_18023A5D9
0x18023a5c8  lfence
0x18023a5cb  lea     rdx, [rbx+380h]
0x18023a5d2  mov     ecx, eax
0x18023a5d4  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18023a5d9  movups  xmm0, xmmword ptr [rbx+368h]
0x18023a5e0  movups  [rsp+388h+var_140], xmm0
0x18023a5e8  movups  xmmword ptr [rbx+158h], xmm0
0x18023a5ef  mov     al, 1
0x18023a5f1  jmp     short loc_18023A5F5
0x18023a5f3  xor     al, al
0x18023a5f5  mov     [rbx+168h], al
0x18023a5fb  mov     [rbx+360h], r14d
0x18023a602  mov     rcx, [r13+0]
0x18023a606  test    rcx, rcx
0x18023a609  jnz     short loc_18023A613
0x18023a60b  mov     eax, r14d
0x18023a60e  mov     rcx, r14
0x18023a611  jmp     short loc_18023A643
0x18023a613  mov     [rbx+3D8h], r14
0x18023a61a  mov     rax, [rcx]
0x18023a61d  lea     r8, [rbx+3D8h]
0x18023a624  lea     rdx, ??$guid_v@UISemanticTextIndexStoreOptions5@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreOptions5>
0x18023a62b  mov     rax, [rax]
0x18023a62e  call    cs:__guard_dispatch_icall_fptr
0x18023a634  mov     rcx, [rbx+3D8h]
0x18023a63b  mov     [rsp+388h+var_240], rcx
0x18023a643  mov     [rbx+3B0h], rcx
0x18023a64a  lea     rdx, [rbx+398h]
0x18023a651  mov     dword ptr [rdx], 0D7Eh
0x18023a657  mov     [rbx+3A0h], r12
0x18023a65e  mov     [rbx+3A8h], r14
0x18023a665  test    eax, eax
0x18023a667  jns     short loc_18023A673
0x18023a669  lfence
0x18023a66c  mov     ecx, eax
0x18023a66e  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18023a673  mov     dword ptr [rbx+3B8h], 0D80h
0x18023a67d  mov     [rbx+3C0h], r12
0x18023a684  mov     [rbx+3C8h], r14
0x18023a68b  mov     rax, [rbx+3B0h]
0x18023a692  mov     [rsp+388h+var_2E8], rax
0x18023a69a  mov     rcx, [rax]
0x18023a69d  mov     rax, [rcx+30h]
0x18023a6a1  mov     rcx, [rbx+3B0h]
0x18023a6a8  mov     [rsp+388h+var_2E8], rcx
0x18023a6b0  lea     rdx, [rbx+360h]
0x18023a6b7  call    cs:__guard_dispatch_icall_fptr
0x18023a6bd  test    eax, eax
0x18023a6bf  jns     short loc_18023A6D3
0x18023a6c1  lfence
0x18023a6c4  lea     rdx, [rbx+3B8h]
0x18023a6cb  mov     ecx, eax
0x18023a6cd  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18023a6d3  lea     rcx, [rbx+3B0h]
0x18023a6da  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023a6df  lea     rdx, [rbx+3D0h]
0x18023a6e6  mov     [rdx], r14d
0x18023a6e9  mov     rcx, [r13+0]
0x18023a6ed  mov     dword ptr [rbx+3E0h], 0D1Dh
0x18023a6f7  mov     [rbx+3E8h], r12
0x18023a6fe  mov     [rbx+3F0h], r14
0x18023a705  mov     rax, [rcx]
0x18023a708  mov     rax, [rax+38h]
0x18023a70c  call    cs:__guard_dispatch_icall_fptr
0x18023a712  test    eax, eax
0x18023a714  jns     short loc_18023A727
0x18023a716  lfence
0x18023a719  lea     rdx, [rbx+3E0h]
0x18023a720  mov     ecx, eax
0x18023a722  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18023a727  mov     rax, [rbx+0A8h]
0x18023a72e  mov     [rbx+178h], rax
0x18023a735  mov     rax, [rbx+0B0h]
0x18023a73c  sub     rax, [rbx+0A8h]
0x18023a743  mov     [rbx+180h], rax
0x18023a74a  lea     rdi, [rbx+3F8h]
0x18023a751  mov     [rdi], r14
0x18023a754  mov     rcx, [r13+0]
0x18023a758  mov     dword ptr [rbx+400h], 0D0Bh
0x18023a762  mov     [rbx+408h], r12
0x18023a769  mov     [rbx+410h], r14
0x18023a770  mov     rax, [rcx]
0x18023a773  mov     rdx, rdi
0x18023a776  mov     rax, [rax+30h]
0x18023a77a  call    cs:__guard_dispatch_icall_fptr
0x18023a780  test    eax, eax
0x18023a782  jns     short loc_18023A795
0x18023a784  lfence
0x18023a787  lea     rdx, [rbx+400h]
0x18023a78e  mov     ecx, eax
0x18023a790  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18023a795  mov     rax, [rdi]
0x18023a798  mov     [rbx+170h], rax
0x18023a79f  movups  xmm0, xmmword ptr [rbx+178h]
0x18023a7a6  movups  [rsp+388h+var_130], xmm0
0x18023a7ae  movaps  xmmword ptr [rbx+2E0h], xmm0
0x18023a7b5  mov     eax, [rbx+360h]
0x18023a7bb  mov     [rsp+388h+var_288], eax
0x18023a7c2  mov     [rbx+418h], eax
0x18023a7c8  mov     eax, [rbx+3D0h]
0x18023a7ce  mov     [rsp+388h+var_2F4], eax
0x18023a7d5  mov     [rbx+420h], eax
0x18023a7db  cmp     qword ptr [rdi], 0
0x18023a7df  jz      short loc_18023A7EA
0x18023a7e1  mov     rax, [rdi]
0x18023a7e4  mov     rdx, [rax+10h]
0x18023a7e8  jmp     short loc_18023A7F1
0x18023a7ea  lea     rdx, String
0x18023a7f1  mov     r8, r15
0x18023a7f4  inc     r8
0x18023a7f7  cmp     word ptr [rdx+r8*2], 0
0x18023a7fd  jnz     short loc_18023A7F4
0x18023a7ff  xorps   xmm0, xmm0
0x18023a802  movups  xmmword ptr [rbx+430h], xmm0
0x18023a809  mov     [rbx+440h], r14
0x18023a810  mov     [rbx+448h], r14
0x18023a817  lea     rcx, [rbx+430h]
0x18023a81e  call    ??$_Construct@$00PEB_S@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXQEB_S_K@Z; std::basic_string<char16_t>::_Construct<1,char16_t const *>(char16_t const * const,unsigned __int64)
0x18023a823  lea     r13, [rbx+450h]
0x18023a82a  lea     rdx, [rbx+430h]
0x18023a831  mov     rcx, r13
0x18023a834  call    ?AppendDbExtensionIfRequired@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@YA?AVpath@filesystem@std@@V89std@@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::AppendDbExtensionIfRequired(std::filesystem::path)
0x18023a839  nop
  ... truncated ...
```
