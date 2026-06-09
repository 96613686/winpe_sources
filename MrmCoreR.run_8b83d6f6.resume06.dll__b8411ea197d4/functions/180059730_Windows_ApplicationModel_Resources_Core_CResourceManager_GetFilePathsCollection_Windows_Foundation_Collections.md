# Windows::ApplicationModel::Resources::Core::CResourceManager::_GetFilePathsCollection(Windows::Foundation::Collections::IIterable<Windows::Storage::IStorageFile *> *,Microsoft::Resources::DynamicArray<Microsoft::Resources::StringResult *> *)

- ea: `0x180059730`
- end: `0x180059b4a`
- name: `?_GetFilePathsCollection@CResourceManager@Core@Resources@ApplicationModel@Windows@@AEAAJPEAU?$IIterable@PEAUIStorageFile@Storage@Windows@@@Collections@Foundation@5@PEAV?$DynamicArray@PEAVStringResult@Resources@Microsoft@@@3Microsoft@@@Z`
- size: `1050`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180059180`
- `0x180059350`

## callees

- `0x18000892c`
- `0x180014a50`
- `0x18001dc04`
- `0x180027270`
- `0x180028510`
- `0x18002c8d0`
- `0x18004c6b0`
- `0x180059730`
- `0x180059f78`
- `0x18007d56c`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180059952`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180059952`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180059940`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180059940`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180059987`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180059987`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005991d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800599e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180059a9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c38f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c397e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3a09`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3a99`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005991d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800599e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180059a9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c38f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c397e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3a09`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3a99`

## string_xrefs

- `0x1800597d4`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcemanager.cpp`
- `0x180059809`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcemanager.cpp`
- `0x180059a38`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcemanager.cpp`
- `0x180059a84`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcemanager.cpp`
- `0x180059ad5`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcemanager.cpp`
- `0x180059b18`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcemanager.cpp`
- `0x1800c38b4`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcemanager.cpp`
- `0x1800c38d3`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcemanager.cpp`
- `0x1800c395e`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcemanager.cpp`
- `0x1800c39e9`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcemanager.cpp`
- `0x1800c3a79`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall Windows::ApplicationModel::Resources::Core::CResourceManager::_GetFilePathsCollection(
        Windows::ApplicationModel::Resources::Core::CResourceManager *a1,
        __int64 a2,
        __int64 a3)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 (__fastcall *v6)(__int64, __int64 *); // rbx
  int v7; // eax
  int v8; // edi
  __int64 (__fastcall *v9)(__int64, __int64 *); // rbx
  int v10; // eax
  __int64 v11; // rcx
  int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  int v17; // eax
  int v18; // edi
  __int64 (__fastcall ***v19)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v20)(_QWORD, GUID *, __int64 *); // rdi
  int v21; // eax
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, HSTRING *); // rbx
  int v24; // eax
  HANDLE ProcessHeap; // rax
  Microsoft::Resources::StringResult *v26; // rax
  _QWORD *v27; // rbx
  PCWSTR StringRawBuffer; // rax
  int v29; // eax
  int v30; // eax
  int v31; // eax
  __int64 v32; // rcx
  __int64 (__fastcall ***v33)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v34; // rcx
  __int64 v35; // rdx
  unsigned int v36; // ebx
  __int64 i; // r9
  unsigned int v38; // ebx
  unsigned int v39; // ebx
  unsigned int v40; // ebx
  unsigned int v41; // edx
  unsigned int v42; // ebx
  unsigned int v43; // edx
  unsigned int v44; // ebx
  unsigned int v45; // edx
  unsigned int v46; // ebx
  unsigned int v47; // edx
  unsigned int v48; // edx
  unsigned int v49; // edx
  unsigned int v50; // edx
  int v51; // [rsp+20h] [rbp-60h] BYREF
  Microsoft::Resources::StringResult *v52; // [rsp+28h] [rbp-58h] BYREF
  __int64 v53; // [rsp+30h] [rbp-50h] BYREF
  HSTRING string; // [rsp+38h] [rbp-48h] BYREF
  __int64 v55; // [rsp+40h] [rbp-40h] BYREF
  __int64 (__fastcall ***v56)(_QWORD, GUID *, __int64 *); // [rsp+48h] [rbp-38h] BYREF
  __int64 v57; // [rsp+50h] [rbp-30h] BYREF
  void **v58; // [rsp+58h] [rbp-28h] BYREF
  _QWORD *v59; // [rsp+60h] [rbp-20h]
  __int64 *v60; // [rsp+68h] [rbp-18h]
  char v61; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v53 = a3;
  *(_DWORD *)(a3 + 12) = 0;
  v4 = Windows::ApplicationModel::Resources::Core::CResourceManager::_CheckInitializeResourceManagerInternal(a1);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B6,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcemanager.cpp",
      (const char *)(unsigned int)v4,
      v51);
  }
  else
  {
    LOBYTE(v51) = 1;
    v55 = 0;
    v6 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v55);
    v7 = v6(a2, &v55);
    v5 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1BB,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcemanager.cpp",
        (const char *)(unsigned int)v7,
        v51);
      v34 = v55;
      if ( v55 )
      {
        v55 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
      }
    }
    else
    {
      v8 = 0;
      while ( (_BYTE)v51 )
      {
        v13 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v55 + 64LL))(v55, &v51);
        v5 = v13;
        if ( v13 < 0 )
        {
          v35 = 447;
          goto LABEL_46;
        }
        ++v8;
      }
      if ( !v8 )
      {
LABEL_14:
        v14 = v55;
        if ( v55 )
        {
          v55 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        }
        return 0;
      }
      v9 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 48LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v55);
      v10 = v9(a2, &v55);
      v5 = v10;
      if ( v10 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1C5,
          (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcemanager.cpp",
          (const char *)(unsigned int)v10,
          v51);
        v11 = v55;
        if ( v55 )
        {
          v55 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
        }
        return v5;
      }
      v13 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v55 + 56LL))(v55, &v51);
      v5 = v13;
      if ( v13 >= 0 )
      {
        v60 = &v53;
        v61 = 1;
        while ( 1 )
        {
          if ( !(_BYTE)v51 )
            goto LABEL_14;
          v56 = 0;
          v15 = v55;
          v16 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v55 + 48LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v56);
          v17 = v16(v15, &v56);
          v18 = v17;
          if ( v17 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1DA,
              (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcemanager.cpp",
              (const char *)(unsigned int)v17,
              v51);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v56);
            v39 = 0;
            for ( i = v53; v39 < *(_DWORD *)(i + 12); ++v39 )
            {
              v52 = 0;
              if ( (int)Microsoft::Resources::DynamicArray<Microsoft::Resources::DynamicPackageProfile::PackageIndexMap *>::Get(
                          i,
                          v39,
                          &v52) >= 0
                && v52 )
              {
                Microsoft::Resources::StringResult::`scalar deleting destructor'(v52, v50);
                i = v53;
              }
            }
            goto LABEL_85;
          }
          v57 = 0;
          v19 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v56;
          v20 = **v56;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v57);
          v21 = v20(v19, &GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30, &v57);
          v18 = v21;
          if ( v21 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1DD,
              (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcemanager.cpp",
              (const char *)(unsigned int)v21,
              v51);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v57);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v56);
            v38 = 0;
            for ( i = v53; v38 < *(_DWORD *)(i + 12); ++v38 )
            {
              v52 = 0;
              if ( (int)Microsoft::Resources::DynamicArray<Microsoft::Resources::DynamicPackageProfile::PackageIndexMap *>::Get(
                          i,
                          v38,
                          &v52) >= 0
                && v52 )
              {
                Microsoft::Resources::StringResult::`scalar deleting destructor'(v52, v49);
                i = v53;
              }
            }
            goto LABEL_85;
          }
          string = 0;
          v22 = v57;
          v23 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v57 + 96LL);
          WindowsDeleteString(0);
          string = 0;
          v24 = v23(v22, &string);
          v18 = v24;
          if ( v24 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1E0,
              (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcemanager.cpp",
              (const char *)(unsigned int)v24,
              v51);
            WindowsDeleteString(string);
            string = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v57);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v56);
            v36 = 0;
            for ( i = v53; v36 < *(_DWORD *)(i + 12); ++v36 )
            {
              v52 = 0;
              if ( (int)Microsoft::Resources::DynamicArray<Microsoft::Resources::DynamicPackageProfile::PackageIndexMap *>::Get(
                          i,
                          v36,
                          &v52) >= 0
                && v52 )
              {
                Microsoft::Resources::StringResult::`scalar deleting destructor'(v52, v48);
                i = v53;
              }
            }
            goto LABEL_85;
          }
          ProcessHeap = GetProcessHeap();
          v26 = (Microsoft::Resources::StringResult *)HeapAlloc(ProcessHeap, 8u, 0x20u);
          v52 = v26;
          if ( v26 )
            v27 = (_QWORD *)Microsoft::Resources::StringResult::StringResult(v26);
          else
            v27 = 0;
          v58 = &Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::StringResult>::`vftable';
          v59 = v27;
          if ( !v27 )
          {
            v18 = -2147024882;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1E3,
              (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcemanager.cpp",
              (const char *)0x8007000ELL,
              v51);
            Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::StringResult>::~AutoDeletePtr<Microsoft::Resources::StringResult>(&v58);
            WindowsDeleteString(string);
            string = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v57);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v56);
            v46 = 0;
            for ( i = v53; v46 < *(_DWORD *)(i + 12); ++v46 )
            {
              v52 = 0;
              if ( (int)Microsoft::Resources::DynamicArray<Microsoft::Resources::DynamicPackageProfile::PackageIndexMap *>::Get(
                          i,
                          v46,
                          &v52) >= 0
                && v52 )
              {
                Microsoft::Resources::StringResult::`scalar deleting destructor'(v52, v47);
                i = v53;
              }
            }
            goto LABEL_85;
          }
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          v29 = DefStringResult_SetCopy(*v27, StringRawBuffer);
          v18 = v29;
          if ( v29 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1E5,
              (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcemanager.cpp",
              (const char *)(unsigned int)v29,
              v51);
            Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::StringResult>::~AutoDeletePtr<Microsoft::Resources::StringResult>(&v58);
            WindowsDeleteString(string);
            string = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v57);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v56);
            v44 = 0;
            for ( i = v53; v44 < *(_DWORD *)(i + 12); ++v44 )
            {
              v52 = 0;
              if ( (int)Microsoft::Resources::DynamicArray<Microsoft::Resources::DynamicPackageProfile::PackageIndexMap *>::Get(
                          i,
                          v44,
                          &v52) >= 0
                && v52 )
              {
                Microsoft::Resources::StringResult::`scalar deleting destructor'(v52, v45);
                i = v53;
              }
            }
            goto LABEL_85;
          }
          v30 = Microsoft::Resources::DynamicArray<Microsoft::Resources::StringResult *>::Add(v53, v27);
          v18 = v30;
          if ( v30 < 0 )
            break;
          v59 = 0;
          v31 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v55 + 64LL))(v55, &v51);
          v18 = v31;
          if ( v31 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1EB,
              (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcemanager.cpp",
              (const char *)(unsigned int)v31,
              v51);
            Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::StringResult>::~AutoDeletePtr<Microsoft::Resources::StringResult>(&v58);
            WindowsDeleteString(string);
            string = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v57);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v56);
            v40 = 0;
            for ( i = v53; v40 < *(_DWORD *)(i + 12); ++v40 )
            {
              v52 = 0;
              if ( (int)Microsoft::Resources::DynamicArray<Microsoft::Resources::DynamicPackageProfile::PackageIndexMap *>::Get(
                          i,
                          v40,
                          &v52) >= 0
                && v52 )
              {
                Microsoft::Resources::StringResult::`scalar deleting destructor'(v52, v41);
                i = v53;
              }
            }
LABEL_85:
            *(_DWORD *)(i + 12) = 0;
            v5 = v18;
            goto LABEL_86;
          }
          v58 = &Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::StringResult>::`vftable';
          v59 = 0;
          WindowsDeleteString(string);
          string = 0;
          v32 = v57;
          if ( v57 )
          {
            v57 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
          }
          v33 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v56;
          if ( v56 )
          {
            v56 = 0;
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v33)[2])(v33);
          }
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1E7,
          (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcemanager.cpp",
          (const char *)(unsigned int)v30,
          v51);
        Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::StringResult>::~AutoDeletePtr<Microsoft::Resources::StringResult>(&v58);
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v57);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v56);
        v42 = 0;
        for ( i = v53; v42 < *(_DWORD *)(i + 12); ++v42 )
        {
          v52 = 0;
          if ( (int)Microsoft::Resources::DynamicArray<Microsoft::Resources::DynamicPackageProfile::PackageIndexMap *>::Get(
                      i,
                      v42,
                      &v52) >= 0
            && v52 )
          {
            Microsoft::Resources::StringResult::`scalar deleting destructor'(v52, v43);
            i = v53;
          }
        }
        goto LABEL_85;
      }
      v35 = 455;
LABEL_46:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v35,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcemanager.cpp",
        (const char *)(unsigned int)v13,
        v51);
LABEL_86:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v55);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180059730  push    rbp
0x180059732  push    rbx
0x180059733  push    rsi
0x180059734  push    rdi
0x180059735  push    r14
0x180059737  mov     rbp, rsp
0x18005973a  sub     rsp, 80h
0x180059741  mov     rsi, rdx
0x180059744  mov     [rbp+var_50], r8
0x180059748  xor     r14d, r14d
0x18005974b  mov     [r8+0Ch], r14d
0x18005974f  call    ?_CheckInitializeResourceManagerInternal@CResourceManager@Core@Resources@ApplicationModel@Windows@@AEAAJXZ; Windows::ApplicationModel::Resources::Core::CResourceManager::_CheckInitializeResourceManagerInternal(void)
0x180059754  mov     ebx, eax
0x180059756  test    eax, eax
0x180059758  js      loc_180059802
0x18005975e  mov     byte ptr [rbp+var_60], 1
0x180059762  mov     [rbp+var_40], r14
0x180059766  mov     rax, [rsi]
0x180059769  mov     rbx, [rax+30h]
0x18005976d  lea     rcx, [rbp+var_40]
0x180059771  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x180059776  lea     rdx, [rbp+var_40]
0x18005977a  mov     rcx, rsi
0x18005977d  mov     rax, rbx
0x180059780  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059785  mov     ebx, eax
0x180059787  test    eax, eax
0x180059789  js      loc_180059A31
0x18005978f  mov     edi, r14d
0x180059792  cmp     byte ptr [rbp+var_60], r14b
0x180059796  jnz     loc_18005982A
0x18005979c  test    edi, edi
0x18005979e  jz      loc_18005984F
0x1800597a4  mov     rax, [rsi]
0x1800597a7  mov     rbx, [rax+30h]
0x1800597ab  lea     rcx, [rbp+var_40]
0x1800597af  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800597b4  lea     rdx, [rbp+var_40]
0x1800597b8  mov     rcx, rsi
0x1800597bb  mov     rax, rbx
0x1800597be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800597c3  mov     ebx, eax
0x1800597c5  test    eax, eax
0x1800597c7  jns     loc_18005986D
0x1800597cd  mov     rcx, [rbp+28h]; this
0x1800597d1  mov     r9d, eax; char *
0x1800597d4  lea     r8, aOnecoreuapBase_25; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x1800597db  mov     edx, 1C5h; void *
0x1800597e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800597e5  nop
0x1800597e6  mov     rcx, [rbp+var_40]
0x1800597ea  test    rcx, rcx
0x1800597ed  jz      short loc_180059800
0x1800597ef  mov     [rbp+var_40], r14
0x1800597f3  mov     rax, [rcx]
0x1800597f6  mov     rax, [rax+10h]
0x1800597fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800597ff  nop
0x180059800  jmp     short loc_18005981A
0x180059802  mov     rcx, [rbp+28h]; this
0x180059806  mov     r9d, ebx; char *
0x180059809  lea     r8, aOnecoreuapBase_25; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x180059810  mov     edx, 1B6h; void *
0x180059815  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005981a  mov     eax, ebx
0x18005981c  add     rsp, 80h
0x180059823  pop     r14
0x180059825  pop     rdi
0x180059826  pop     rsi
0x180059827  pop     rbx
0x180059828  pop     rbp
0x180059829  retn
0x18005982a  mov     rcx, [rbp+var_40]
0x18005982e  mov     rax, [rcx]
0x180059831  lea     rdx, [rbp+var_60]
0x180059835  mov     rax, [rax+40h]
0x180059839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005983e  mov     ebx, eax
0x180059840  test    eax, eax
0x180059842  js      loc_180059A69
0x180059848  inc     edi
0x18005984a  jmp     loc_180059792
0x18005984f  mov     rcx, [rbp+var_40]
0x180059853  test    rcx, rcx
0x180059856  jz      short loc_180059869
0x180059858  mov     [rbp+var_40], r14
0x18005985c  mov     rax, [rcx]
0x18005985f  mov     rax, [rax+10h]
0x180059863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059868  nop
0x180059869  xor     eax, eax
0x18005986b  jmp     short loc_18005981C
0x18005986d  mov     rcx, [rbp+var_40]
0x180059871  mov     rax, [rcx]
0x180059874  lea     rdx, [rbp+var_60]
0x180059878  mov     rax, [rax+38h]
0x18005987c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059881  mov     ebx, eax
0x180059883  test    eax, eax
0x180059885  js      loc_180059A73
0x18005988b  lea     rax, [rbp+var_50]
0x18005988f  mov     [rbp+var_18], rax
0x180059893  mov     [rbp+var_10], 1
0x180059897  lea     rsi, ??_7?$AutoDeletePtr@VStringResult@Resources@Microsoft@@@Resources@Microsoft@@6B@; const Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::StringResult>::`vftable'
0x18005989e  cmp     byte ptr [rbp+var_60], r14b
0x1800598a2  jz      short loc_18005984F
0x1800598a4  mov     [rbp+var_38], r14
0x1800598a8  mov     rdi, [rbp+var_40]
0x1800598ac  mov     rax, [rdi]
0x1800598af  mov     rbx, [rax+30h]
0x1800598b3  lea     rcx, [rbp+var_38]
0x1800598b7  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800598bc  lea     rdx, [rbp+var_38]
0x1800598c0  mov     rcx, rdi
0x1800598c3  mov     rax, rbx
0x1800598c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800598cb  mov     edi, eax
0x1800598cd  test    eax, eax
0x1800598cf  js      loc_180059B11
0x1800598d5  mov     [rbp+var_30], r14
0x1800598d9  mov     rbx, [rbp+var_38]
0x1800598dd  mov     rax, [rbx]
0x1800598e0  mov     rdi, [rax]
0x1800598e3  lea     rcx, [rbp+var_30]
0x1800598e7  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800598ec  lea     r8, [rbp+var_30]
0x1800598f0  lea     rdx, _GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30
0x1800598f7  mov     rcx, rbx
0x1800598fa  mov     rax, rdi
0x1800598fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059902  mov     edi, eax
0x180059904  test    eax, eax
0x180059906  js      loc_180059ACE
0x18005990c  mov     [rbp+string], r14
0x180059910  mov     rdi, [rbp+var_30]
0x180059914  mov     rax, [rdi]
0x180059917  mov     rbx, [rax+60h]
0x18005991b  xor     ecx, ecx; string
0x18005991d  call    cs:__imp_WindowsDeleteString
0x180059923  mov     [rbp+string], r14
0x180059927  lea     rdx, [rbp+string]
0x18005992b  mov     rcx, rdi
0x18005992e  mov     rax, rbx
0x180059931  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059936  mov     edi, eax
0x180059938  test    eax, eax
0x18005993a  js      loc_180059A7D
0x180059940  call    cs:__imp_GetProcessHeap
0x180059946  mov     rcx, rax; hHeap
0x180059949  mov     edx, 8; dwFlags
0x18005994e  lea     r8d, [rdx+18h]; dwBytes
0x180059952  call    cs:__imp_HeapAlloc
0x180059958  mov     [rbp+var_58], rax
0x18005995c  test    rax, rax
0x18005995f  jz      loc_180059A29
0x180059965  mov     rcx, rax; this
0x180059968  call    ??0StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::StringResult(void)
0x18005996d  mov     rbx, rax
0x180059970  mov     [rbp+var_28], rsi
0x180059974  mov     [rbp+var_20], rbx
0x180059978  test    rbx, rbx
0x18005997b  jz      loc_1800C3A6D
0x180059981  xor     edx, edx; length
0x180059983  mov     rcx, [rbp+string]; string
0x180059987  call    cs:__imp_WindowsGetStringRawBuffer
0x18005998d  mov     rdx, rax
0x180059990  mov     rcx, [rbx]
0x180059993  call    DefStringResult_SetCopy
0x180059998  mov     edi, eax
0x18005999a  test    eax, eax
0x18005999c  js      loc_1800C39E2
0x1800599a2  mov     rdx, rbx
0x1800599a5  mov     rcx, [rbp+var_50]
0x1800599a9  call    ?Add@?$DynamicArray@PEAVStringResult@Resources@Microsoft@@@Resources@Microsoft@@QEAAJPEAVStringResult@23@PEAH@Z; Microsoft::Resources::DynamicArray<Microsoft::Resources::StringResult *>::Add(Microsoft::Resources::StringResult *,int *)
0x1800599ae  mov     edi, eax
0x1800599b0  test    eax, eax
0x1800599b2  js      loc_1800C3957
0x1800599b8  mov     [rbp+var_20], r14
0x1800599bc  mov     rcx, [rbp+var_40]
0x1800599c0  mov     rax, [rcx]
0x1800599c3  lea     rdx, [rbp+var_60]
0x1800599c7  mov     rax, [rax+40h]
0x1800599cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800599d0  mov     edi, eax
0x1800599d2  test    eax, eax
0x1800599d4  js      loc_1800C38CC
0x1800599da  mov     [rbp+var_28], rsi
0x1800599de  mov     [rbp+var_20], r14
0x1800599e2  mov     rcx, [rbp+string]; string
0x1800599e6  call    cs:__imp_WindowsDeleteString
0x1800599ec  mov     [rbp+string], r14
0x1800599f0  mov     rcx, [rbp+var_30]
0x1800599f4  test    rcx, rcx
0x1800599f7  jz      short loc_180059A0A
0x1800599f9  mov     [rbp+var_30], r14
0x1800599fd  mov     rax, [rcx]
0x180059a00  mov     rax, [rax+10h]
0x180059a04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059a09  nop
0x180059a0a  mov     rcx, [rbp+var_38]
0x180059a0e  test    rcx, rcx
0x180059a11  jz      short loc_180059A24
0x180059a13  mov     [rbp+var_38], r14
0x180059a17  mov     rax, [rcx]
0x180059a1a  mov     rax, [rax+10h]
0x180059a1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059a23  nop
0x180059a24  jmp     loc_18005989E
0x180059a29  mov     rbx, r14
0x180059a2c  jmp     loc_180059970
0x180059a31  mov     rcx, [rbp+28h]; this
0x180059a35  mov     r9d, ebx; char *
0x180059a38  lea     r8, aOnecoreuapBase_25; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x180059a3f  mov     edx, 1BBh; void *
0x180059a44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059a49  nop
0x180059a4a  mov     rcx, [rbp+var_40]
0x180059a4e  test    rcx, rcx
0x180059a51  jz      short loc_180059A64
0x180059a53  mov     [rbp+var_40], r14
0x180059a57  mov     rax, [rcx]
0x180059a5a  mov     rax, [rax+10h]
0x180059a5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059a63  nop
0x180059a64  jmp     loc_18005981A
0x180059a69  mov     edx, 1BFh; void *
0x180059a6e  jmp     loc_1800C38B4
0x180059a73  mov     edx, 1C7h
0x180059a78  jmp     loc_1800C38B4
0x180059a7d  mov     rcx, [rbp+28h]; this
0x180059a81  mov     r9d, edi; char *
0x180059a84  lea     r8, aOnecoreuapBase_25; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x180059a8b  mov     edx, 1E0h; void *
0x180059a90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059a95  nop
0x180059a96  mov     rcx, [rbp+string]; string
0x180059a9a  call    cs:__imp_WindowsDeleteString
0x180059aa0  mov     [rbp+string], r14
0x180059aa4  lea     rcx, [rbp+var_30]
0x180059aa8  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x180059aad  nop
0x180059aae  lea     rcx, [rbp+var_38]
0x180059ab2  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x180059ab7  nop
0x180059ab8  mov     ebx, r14d
0x180059abb  mov     r9, [rbp+var_50]
0x180059abf  cmp     [r9+0Ch], r14d
0x180059ac3  ja      loc_1800C3AFD
0x180059ac9  jmp     loc_1800C3B91
0x180059ace  mov     rcx, [rbp+28h]; this
0x180059ad2  mov     r9d, edi; char *
0x180059ad5  lea     r8, aOnecoreuapBase_25; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x180059adc  mov     edx, 1DDh; void *
0x180059ae1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059ae6  nop
0x180059ae7  lea     rcx, [rbp+var_30]
0x180059aeb  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x180059af0  nop
0x180059af1  lea     rcx, [rbp+var_38]
0x180059af5  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x180059afa  nop
0x180059afb  mov     ebx, r14d
0x180059afe  mov     r9, [rbp+var_50]
0x180059b02  cmp     [r9+0Ch], r14d
0x180059b06  ja      loc_1800C3B2F
0x180059b0c  jmp     loc_1800C3B91
0x180059b11  mov     rcx, [rbp+28h]; this
0x180059b15  mov     r9d, edi; char *
0x180059b18  lea     r8, aOnecoreuapBase_25; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x180059b1f  mov     edx, 1DAh; void *
0x180059b24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059b29  nop
0x180059b2a  lea     rcx, [rbp+var_38]
0x180059b2e  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x180059b33  nop
0x180059b34  mov     ebx, r14d
0x180059b37  mov     r9, [rbp+var_50]
0x180059b3b  cmp     [r9+0Ch], r14d
0x180059b3f  ja      loc_1800C3B61
0x180059b45  jmp     loc_1800C3B91
0x1800c38b4  lea     r8, aOnecoreuapBase_25; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x1800c38bb  mov     r9d, eax; char *
0x1800c38be  mov     rcx, [rbp+28h]; this
0x1800c38c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c38c7  jmp     loc_1800C3B97
0x1800c38cc  mov     rcx, [rbp+28h]; this
0x1800c38d0  mov     r9d, edi; char *
0x1800c38d3  lea     r8, aOnecoreuapBase_25; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x1800c38da  mov     edx, 1EBh; void *
0x1800c38df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c38e4  nop
0x1800c38e5  lea     rcx, [rbp+var_28]
0x1800c38e9  call    ??1?$AutoDeletePtr@VStringResult@Resources@Microsoft@@@Resources@Microsoft@@UEAA@XZ; Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::StringResult>::~AutoDeletePtr<Microsoft::Resources::StringResult>(void)
0x1800c38ee  nop
0x1800c38ef  mov     rcx, [rbp+string]; string
0x1800c38f3  call    cs:__imp_WindowsDeleteString
0x1800c38f9  mov     [rbp+string], r14
0x1800c38fd  lea     rcx, [rbp+var_30]
0x1800c3901  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800c3906  nop
  ... truncated ...
```
