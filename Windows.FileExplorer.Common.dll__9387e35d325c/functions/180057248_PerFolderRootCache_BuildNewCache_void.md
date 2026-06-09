# PerFolderRootCache::BuildNewCache(void)

- ea: `0x180057248`
- end: `0x1800576de`
- name: `?BuildNewCache@PerFolderRootCache@@AEAAXXZ`
- size: `1174`
- prototype: `void __fastcall(PerFolderRootCache *__hidden this)`
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180057778`

## callees

- `0x180004d6c`
- `0x180007900`
- `0x18000a5b0`
- `0x180016440`
- `0x180016d78`
- `0x18001ca98`
- `0x18001d320`
- `0x18002037c`
- `0x180021d14`
- `0x180028284`
- `0x180037780`
- `0x180037c5c`
- `0x180054a70`
- `0x1800551b0`
- `0x180055abc`
- `0x180056a10`
- `0x180056bc4`
- `0x180056c34`
- `0x180056cb8`
- `0x180056db0`
- `0x180057248`
- `0x180059c98`
- `0x180059ef8`
- `0x180059f44`
- `0x18005b0f4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180057448`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800574b0`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180057448`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800574b0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180057380`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180057380`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180057423`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005748b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180057423`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005748b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800572f4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800572f4`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18005733f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180057632`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18005733f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180057632`

## string_xrefs

- `0x1800576b7`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\perfolderrootmanager.cpp`
- `0x1800576cc`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\perfolderrootmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall PerFolderRootCache::BuildNewCache(PerFolderRootCache *this)
{
  char *v1; // rdi
  char *v2; // r12
  unsigned int v3; // eax
  int v4; // r14d
  int v5; // r15d
  unsigned int v6; // eax
  const WCHAR *v7; // rbx
  LSTATUS ValueW; // eax
  bool v9; // sf
  LSTATUS v10; // eax
  bool v11; // sf
  volatile signed __int32 *v12; // rbx
  _QWORD *v13; // rdx
  DWORD v14; // edx
  HSTRING v15; // rbx
  unsigned int dwOptions; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-E0h]
  DWORD pcbData[2]; // [rsp+50h] [rbp-B0h] BYREF
  PCNZWCH sourceString; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cchName; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hkey; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  HSTRING string; // [rsp+78h] [rbp-88h] BYREF
  std::_Ref_count_base *v24[2]; // [rsp+80h] [rbp-80h] BYREF
  void *v25; // [rsp+90h] [rbp-70h]
  _QWORD v26[2]; // [rsp+98h] [rbp-68h] BYREF
  __int128 v27; // [rsp+A8h] [rbp-58h]
  _BYTE v28[56]; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING v29; // [rsp+F8h] [rbp-8h]
  GUID iid; // [rsp+100h] [rbp+0h] BYREF
  GUID v31; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v32[32]; // [rsp+120h] [rbp+20h] BYREF
  const WCHAR *v33; // [rsp+140h] [rbp+40h]
  GUID v34; // [rsp+148h] [rbp+48h]
  GUID v35; // [rsp+158h] [rbp+58h]
  __int64 v36; // [rsp+168h] [rbp+68h]
  OLECHAR pvData[40]; // [rsp+170h] [rbp+70h] BYREF
  WCHAR Name[40]; // [rsp+1C0h] [rbp+C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  v1 = (char *)this + 80;
  v2 = (char *)this + 24;
  WindowsStorage::Utilities::NamespaceMap<std::shared_ptr<PerFolderRootInfo const>,nt_path_segment_tokenizer<unsigned short>>::clear((char *)this + 24);
  std::vector<std::shared_ptr<PerFolderRootInfo const>>::clear(v1);
  sourceString = 0;
  tip2::tip_test<tip2::details::merged_data<_tip_PerFolderRootCalculationTest,_tip_PerFolderRootCalculationTest>>::start_and_watch_errors(
    &sourceString,
    v28);
  wil::com_ptr_t<tip2::details::merged_data<_tip_PerFolderRootCalculationTest,_tip_PerFolderRootCalculationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PerFolderRootCalculationTest,_tip_PerFolderRootCalculationTest>,wil::err_returncode_policy>(&sourceString);
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v3 = RegCreateKeyExW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\PerFolderRoots",
         0,
         0,
         0,
         0x20019u,
         0,
         &hKey,
         0);
  if ( v3 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0xAB,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\perfolderrootmanager.cpp",
      (const char *)v3,
      dwOptions);
  cchName = 39;
  v4 = 0;
  v5 = 1;
  if ( !RegEnumKeyExW(hKey, 0, Name, &cchName, 0, 0, 0, 0) )
  {
    do
    {
      hkey = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &hkey,
        0);
      v6 = RegOpenKeyExW(hKey, Name, 0, 0x20019u, &hkey);
      if ( v6 )
        wil::details::in1diag3::_Throw_Win32(
          retaddr,
          (void *)0xB4,
          (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\perfolderrootmanager.cpp",
          (const char *)v6,
          dwOptionsa);
      sourceString = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &sourceString,
        0);
      if ( (int)SHRegAllocData(hkey, 0, L"Path", 2u, (void **)&sourceString) >= 0 )
      {
        v7 = sourceString;
        if ( sourceString )
        {
          if ( *sourceString )
          {
            iid = FOLDERTYPEID_Invalid;
            pcbData[0] = 78;
            ValueW = RegGetValueW(hkey, 0, L"FolderType", 2u, 0, pvData, pcbData);
            v9 = ValueW < 0;
            if ( ValueW )
            {
              pvData[0] = 0;
              if ( ValueW > 0 )
                v9 = 1;
            }
            if ( !v9 )
              IIDFromString(pvData, &iid);
            v31 = GUID_NULL;
            pcbData[0] = 78;
            v10 = RegGetValueW(hkey, 0, L"PropertyProvider", 2u, 0, pvData, pcbData);
            v11 = v10 < 0;
            if ( v10 )
            {
              pvData[0] = 0;
              if ( v10 > 0 )
                v11 = 1;
            }
            if ( !v11 )
              IIDFromString(pvData, &v31);
            *(_QWORD *)pcbData = 0;
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
              pcbData,
              0);
            SHRegAllocData(hkey, 0, L"RegisteredAppID", 2u, (void **)pcbData);
            wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
              &string,
              v7);
            std::wstring::wstring(v32, Name);
            v33 = v7;
            sourceString = 0;
            v34 = iid;
            v35 = v31;
            v36 = *(_QWORD *)pcbData;
            *(_QWORD *)pcbData = 0;
            v25 = operator new(0x60u);
            v12 = (volatile signed __int32 *)std::_Ref_count_obj2<PerFolderRootInfo>::_Ref_count_obj2<PerFolderRootInfo>(
                                               v25,
                                               v32);
            *(_QWORD *)&v27 = v12 + 4;
            *((_QWORD *)&v27 + 1) = v12;
            PerFolderRootInfo::~PerFolderRootInfo((PerFolderRootInfo *)v32);
            if ( v12 )
              _InterlockedIncrement(v12 + 2);
            v24[0] = (std::_Ref_count_base *)(v12 + 4);
            v24[1] = (std::_Ref_count_base *)v12;
            v13 = (_QWORD *)*((_QWORD *)v1 + 1);
            if ( v13 == *((_QWORD **)v1 + 2) )
            {
              std::vector<std::shared_ptr<PerFolderRootInfo const>>::_Emplace_reallocate<std::shared_ptr<PerFolderRootInfo const>>(
                v1,
                v13,
                v24);
            }
            else
            {
              *v13 = v12 + 4;
              v13[1] = v12;
              *(_OWORD *)v24 = 0;
              *((_QWORD *)v1 + 1) += 16LL;
            }
            if ( v24[1] )
              std::_Ref_count_base::_Decref(v24[1]);
            v26[0] = v12 + 4;
            v26[1] = v12;
            v27 = 0;
            WindowsStorage::Utilities::NamespaceMap<std::shared_ptr<PerFolderRootInfo const>,nt_path_segment_tokenizer<unsigned short>>::Insert(
              v2,
              string,
              v26);
            ++v4;
            wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(pcbData);
          }
        }
      }
      cchName = 39;
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&sourceString);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      v14 = v5++;
    }
    while ( !RegEnumKeyExW(hKey, v14, Name, &cchName, 0, 0, 0, 0) );
  }
  v15 = v29;
  string = v29;
  if ( v29 )
    _InterlockedIncrement((volatile signed __int32 *)v29 + 70);
  tip2::details::shared_data<0,0,0>::begin_update(v15 + 2);
  *((_DWORD *)v15 + 68) = v4;
  tip2::test_data_control<tip2::details::merged_data<_tip_PerFolderRootCalculationTest,_tip_PerFolderRootCalculationTest>>::~test_data_control<tip2::details::merged_data<_tip_PerFolderRootCalculationTest,_tip_PerFolderRootCalculationTest>>(&string);
  tip2::details::shared_data<0,0,0>::complete_without_lock(v29 + 2);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  tip2::test_watcher<tip2::details::merged_data<_tip_PerFolderRootCalculationTest,_tip_PerFolderRootCalculationTest>>::~test_watcher<tip2::details::merged_data<_tip_PerFolderRootCalculationTest,_tip_PerFolderRootCalculationTest>>(v28);
}

```

## disassembly

```asm
0x180057248  push    rbp
0x18005724a  push    rbx
0x18005724b  push    rsi
0x18005724c  push    rdi
0x18005724d  push    r12
0x18005724f  push    r13
0x180057251  push    r14
0x180057253  push    r15
0x180057255  lea     rbp, [rsp-128h]
0x18005725d  sub     rsp, 228h
0x180057264  mov     rax, cs:__security_cookie
0x18005726b  xor     rax, rsp
0x18005726e  mov     [rbp+160h+var_50], rax
0x180057275  lea     rdi, [rcx+50h]
0x180057279  xor     r13d, r13d
0x18005727c  lea     r12, [rcx+18h]
0x180057280  mov     rcx, r12
0x180057283  call    ?clear@?$NamespaceMap@V?$shared_ptr@$$CBUPerFolderRootInfo@@@std@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@QEAAXXZ; WindowsStorage::Utilities::NamespaceMap<std::shared_ptr<PerFolderRootInfo const>,nt_path_segment_tokenizer<ushort>>::clear(void)
0x180057288  mov     rcx, rdi
0x18005728b  call    ?clear@?$vector@V?$shared_ptr@$$CBUPerFolderRootInfo@@@std@@V?$allocator@V?$shared_ptr@$$CBUPerFolderRootInfo@@@std@@@2@@std@@QEAAXXZ; std::vector<std::shared_ptr<PerFolderRootInfo const>>::clear(void)
0x180057290  mov     [rsp+260h+sourceString], r13
0x180057295  lea     rdx, [rbp+160h+var_1A0]
0x180057299  lea     rcx, [rsp+260h+sourceString]
0x18005729e  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_PerFolderRootCalculationTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_PerFolderRootCalculationTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PerFolderRootCalculationTest,_tip_PerFolderRootCalculationTest>>::start_and_watch_errors(void)
0x1800572a3  lea     rcx, [rsp+260h+sourceString]
0x1800572a8  call    ??1?$com_ptr_t@V?$merged_data@U_tip_PerFolderRootCalculationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_PerFolderRootCalculationTest,_tip_PerFolderRootCalculationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PerFolderRootCalculationTest,_tip_PerFolderRootCalculationTest>,wil::err_returncode_policy>(void)
0x1800572ad  nop
0x1800572ae  mov     [rsp+260h+hKey], r13
0x1800572b3  xor     edx, edx
0x1800572b5  lea     rcx, [rsp+260h+hKey]
0x1800572ba  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800572bf  mov     [rsp+260h+lpdwDisposition], r13; lpdwDisposition
0x1800572c4  lea     rax, [rsp+260h+hKey]
0x1800572c9  mov     [rsp+260h+phkResult], rax; phkResult
0x1800572ce  mov     [rsp+260h+lpSecurityAttributes], r13; lpSecurityAttributes
0x1800572d3  mov     [rsp+260h+samDesired], 20019h; samDesired
0x1800572db  mov     [rsp+260h+dwOptions], r13d; unsigned int
0x1800572e0  xor     r9d, r9d; lpClass
0x1800572e3  xor     r8d, r8d; Reserved
0x1800572e6  lea     rdx, ?PerFolderRegKey@Details@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800572ed  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800572f4  call    cs:__imp_RegCreateKeyExW
0x1800572fa  mov     rcx, [rbp+168h]; this
0x180057301  test    eax, eax
0x180057303  jnz     loc_1800576B4
0x180057309  mov     [rsp+260h+cchName], 27h ; '''
0x180057311  mov     r14d, r13d
0x180057314  lea     r15d, [r13+1]
0x180057318  mov     [rsp+260h+phkResult], r13; lpftLastWriteTime
0x18005731d  mov     [rsp+260h+lpSecurityAttributes], r13; lpcchClass
0x180057322  mov     qword ptr [rsp+260h+samDesired], r13; unsigned int *
0x180057327  mov     qword ptr [rsp+260h+dwOptions], r13; lpReserved
0x18005732c  lea     r9, [rsp+260h+cchName]; lpcchName
0x180057331  lea     r8, [rbp+160h+Name]; lpName
0x180057338  xor     edx, edx; dwIndex
0x18005733a  mov     rcx, [rsp+260h+hKey]; hKey
0x18005733f  call    cs:__imp_RegEnumKeyExW
0x180057345  test    eax, eax
0x180057347  jnz     loc_180057640
0x18005734d  lea     esi, [rax+2]
0x180057350  mov     [rsp+260h+hkey], r13
0x180057355  xor     edx, edx
0x180057357  lea     rcx, [rsp+260h+hkey]
0x18005735c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180057361  lea     rax, [rsp+260h+hkey]
0x180057366  mov     qword ptr [rsp+260h+dwOptions], rax; unsigned int
0x18005736b  mov     r9d, 20019h; samDesired
0x180057371  xor     r8d, r8d; ulOptions
0x180057374  lea     rdx, [rbp+160h+Name]; lpSubKey
0x18005737b  mov     rcx, [rsp+260h+hKey]; hKey
0x180057380  call    cs:__imp_RegOpenKeyExW
0x180057386  mov     rcx, [rbp+168h]; this
0x18005738d  test    eax, eax
0x18005738f  jnz     loc_1800576C9
0x180057395  mov     [rsp+260h+sourceString], r13
0x18005739a  xor     edx, edx
0x18005739c  lea     rcx, [rsp+260h+sourceString]
0x1800573a1  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800573a6  lea     rax, [rsp+260h+sourceString]
0x1800573ab  mov     qword ptr [rsp+260h+dwOptions], rax; void **
0x1800573b0  mov     r9d, esi; int
0x1800573b3  lea     r8, ?PathValue@Details@@3QBGB; "Path"
0x1800573ba  xor     edx, edx; unsigned __int16 *
0x1800573bc  mov     rcx, [rsp+260h+hkey]; HKEY
0x1800573c1  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x1800573c6  test    eax, eax
0x1800573c8  js      loc_1800575EA
0x1800573ce  mov     rbx, [rsp+260h+sourceString]
0x1800573d3  test    rbx, rbx
0x1800573d6  jz      loc_1800575EA
0x1800573dc  cmp     [rbx], r13w
0x1800573e0  jz      loc_1800575EA
0x1800573e6  movups  xmm0, xmmword ptr cs:FOLDERTYPEID_Invalid.Data1
0x1800573ed  movdqu  xmmword ptr [rbp+160h+iid.Data1], xmm0
0x1800573f2  mov     [rsp+260h+pcbData], 4Eh ; 'N'
0x1800573fa  lea     rax, [rsp+260h+pcbData]
0x1800573ff  mov     [rsp+260h+lpSecurityAttributes], rax; pcbData
0x180057404  lea     rax, [rbp+160h+pvData]
0x180057408  mov     qword ptr [rsp+260h+samDesired], rax; pvData
0x18005740d  mov     qword ptr [rsp+260h+dwOptions], r13; pdwType
0x180057412  mov     r9d, esi; dwFlags
0x180057415  lea     r8, ?FolderTypeValue@Details@@3QBGB; "FolderType"
0x18005741c  xor     edx, edx; lpSubKey
0x18005741e  mov     rcx, [rsp+260h+hkey]; hkey
0x180057423  call    cs:__imp_RegGetValueW
0x180057429  test    eax, eax
0x18005742b  jz      short loc_18005743E
0x18005742d  mov     [rbp+160h+pvData], r13w
0x180057432  jle     short loc_18005743E
0x180057434  movzx   eax, ax
0x180057437  or      eax, 80070000h
0x18005743c  test    eax, eax
0x18005743e  js      short loc_18005744E
0x180057440  lea     rdx, [rbp+160h+iid]; lpiid
0x180057444  lea     rcx, [rbp+160h+pvData]; lpsz
0x180057448  call    cs:__imp_IIDFromString
0x18005744e  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180057455  movdqu  xmmword ptr [rbp+160h+var_150.Data1], xmm0
0x18005745a  mov     [rsp+260h+pcbData], 4Eh ; 'N'
0x180057462  lea     rax, [rsp+260h+pcbData]
0x180057467  mov     [rsp+260h+lpSecurityAttributes], rax; pcbData
0x18005746c  lea     rax, [rbp+160h+pvData]
0x180057470  mov     qword ptr [rsp+260h+samDesired], rax; unsigned int *
0x180057475  mov     qword ptr [rsp+260h+dwOptions], r13; pdwType
0x18005747a  mov     r9d, esi; dwFlags
0x18005747d  lea     r8, ?PropertyProviderValue@Details@@3QBGB; "PropertyProvider"
0x180057484  xor     edx, edx; lpSubKey
0x180057486  mov     rcx, [rsp+260h+hkey]; hkey
0x18005748b  call    cs:__imp_RegGetValueW
0x180057491  test    eax, eax
0x180057493  jz      short loc_1800574A6
0x180057495  mov     [rbp+160h+pvData], r13w
0x18005749a  jle     short loc_1800574A6
0x18005749c  movzx   eax, ax
0x18005749f  or      eax, 80070000h
0x1800574a4  test    eax, eax
0x1800574a6  js      short loc_1800574B6
0x1800574a8  lea     rdx, [rbp+160h+var_150]; lpiid
0x1800574ac  lea     rcx, [rbp+160h+pvData]; lpsz
0x1800574b0  call    cs:__imp_IIDFromString
0x1800574b6  mov     qword ptr [rsp+260h+pcbData], r13
0x1800574bb  xor     edx, edx
0x1800574bd  lea     rcx, [rsp+260h+pcbData]
0x1800574c2  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800574c7  lea     rax, [rsp+260h+pcbData]
0x1800574cc  mov     qword ptr [rsp+260h+dwOptions], rax; void **
0x1800574d1  mov     r9d, esi; int
0x1800574d4  lea     r8, ?RegisteredAppIDValue@Details@@3QBGB; "RegisteredAppID"
0x1800574db  xor     edx, edx; unsigned __int16 *
0x1800574dd  mov     rcx, [rsp+260h+hkey]; HKEY
0x1800574e2  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x1800574e7  mov     rdx, rbx; sourceString
0x1800574ea  lea     rcx, [rsp+260h+string]; string
0x1800574ef  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800574f4  nop
0x1800574f5  lea     rdx, [rbp+160h+Name]
0x1800574fc  lea     rcx, [rbp+160h+var_140]
0x180057500  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180057505  mov     [rbp+160h+var_120], rbx
0x180057509  mov     [rsp+260h+sourceString], r13
0x18005750e  movups  xmm0, xmmword ptr [rbp+160h+iid.Data1]
0x180057512  movdqu  [rbp+160h+var_118], xmm0
0x180057517  movups  xmm1, xmmword ptr [rbp+160h+var_150.Data1]
0x18005751b  movdqu  [rbp+160h+var_108], xmm1
0x180057520  mov     rax, qword ptr [rsp+260h+pcbData]
0x180057525  mov     [rbp+160h+var_F8], rax
0x180057529  mov     qword ptr [rsp+260h+pcbData], r13
0x18005752e  mov     ecx, 60h ; '`'; Size
0x180057533  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180057538  mov     [rbp+160h+var_1D0], rax
0x18005753c  lea     rdx, [rbp+160h+var_140]
0x180057540  mov     rcx, rax
0x180057543  call    ??$?0UPerFolderRootInfo@@@?$_Ref_count_obj2@UPerFolderRootInfo@@@std@@QEAA@$$QEAUPerFolderRootInfo@@@Z; std::_Ref_count_obj2<PerFolderRootInfo>::_Ref_count_obj2<PerFolderRootInfo>(PerFolderRootInfo &&)
0x180057548  mov     rbx, rax
0x18005754b  lea     rsi, [rax+10h]
0x18005754f  mov     qword ptr [rbp+160h+var_1B8], rsi
0x180057553  mov     qword ptr [rbp+160h+var_1B8+8], rax
0x180057557  lea     rcx, [rbp+160h+var_140]; this
0x18005755b  call    ??1PerFolderRootInfo@@QEAA@XZ; PerFolderRootInfo::~PerFolderRootInfo(void)
0x180057560  test    rbx, rbx
0x180057563  jz      short loc_180057569
0x180057565  lock inc dword ptr [rbx+8]
0x180057569  mov     [rbp+160h+var_1E0], rsi
0x18005756d  mov     [rbp+160h+var_1E0+8], rbx
0x180057571  mov     rdx, [rdi+8]
0x180057575  cmp     rdx, [rdi+10h]
0x180057579  jz      short loc_180057591
0x18005757b  mov     [rdx], rsi
0x18005757e  mov     [rdx+8], rbx
0x180057582  xorps   xmm0, xmm0
0x180057585  movdqu  xmmword ptr [rbp+160h+var_1E0], xmm0
0x18005758a  add     qword ptr [rdi+8], 10h
0x18005758f  jmp     short loc_18005759E
0x180057591  lea     r8, [rbp+160h+var_1E0]
0x180057595  mov     rcx, rdi
0x180057598  call    ??$_Emplace_reallocate@V?$shared_ptr@$$CBUPerFolderRootInfo@@@std@@@?$vector@V?$shared_ptr@$$CBUPerFolderRootInfo@@@std@@V?$allocator@V?$shared_ptr@$$CBUPerFolderRootInfo@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@$$CBUPerFolderRootInfo@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::shared_ptr<PerFolderRootInfo const>>::_Emplace_reallocate<std::shared_ptr<PerFolderRootInfo const>>(std::shared_ptr<PerFolderRootInfo const> * const,std::shared_ptr<PerFolderRootInfo const> &&)
0x18005759d  nop
0x18005759e  mov     rcx, [rbp+160h+var_1E0+8]; this
0x1800575a2  test    rcx, rcx
0x1800575a5  jz      short loc_1800575AC
0x1800575a7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800575ac  mov     [rbp+160h+var_1C8], rsi
0x1800575b0  mov     [rbp+160h+var_1C0], rbx
0x1800575b4  xorps   xmm0, xmm0
0x1800575b7  movdqu  [rbp+160h+var_1B8], xmm0
0x1800575bc  lea     r8, [rbp+160h+var_1C8]
0x1800575c0  mov     rdx, [rsp+260h+string]
0x1800575c5  mov     rcx, r12
0x1800575c8  call    ?Insert@?$NamespaceMap@V?$shared_ptr@$$CBUPerFolderRootInfo@@@std@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@QEAAXPEAUHSTRING__@@V?$shared_ptr@$$CBUPerFolderRootInfo@@@std@@@Z; WindowsStorage::Utilities::NamespaceMap<std::shared_ptr<PerFolderRootInfo const>,nt_path_segment_tokenizer<ushort>>::Insert(HSTRING__ *,std::shared_ptr<PerFolderRootInfo const>)
0x1800575cd  inc     r14d
0x1800575d0  lea     rcx, [rsp+260h+string]
0x1800575d5  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x1800575da  nop
0x1800575db  lea     rcx, [rsp+260h+pcbData]; void *
0x1800575e0  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x1800575e5  mov     esi, 2
0x1800575ea  mov     [rsp+260h+cchName], 27h ; '''
0x1800575f2  lea     rcx, [rsp+260h+sourceString]; void *
0x1800575f7  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x1800575fc  nop
0x1800575fd  lea     rcx, [rsp+260h+hkey]
0x180057602  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180057607  mov     edx, r15d; dwIndex
0x18005760a  inc     r15d
0x18005760d  mov     [rsp+260h+phkResult], r13; lpftLastWriteTime
0x180057612  mov     [rsp+260h+lpSecurityAttributes], r13; lpcchClass
0x180057617  mov     qword ptr [rsp+260h+samDesired], r13; lpClass
0x18005761c  mov     qword ptr [rsp+260h+dwOptions], r13; lpReserved
0x180057621  lea     r9, [rsp+260h+cchName]; lpcchName
0x180057626  lea     r8, [rbp+160h+Name]; lpName
0x18005762d  mov     rcx, [rsp+260h+hKey]; hKey
0x180057632  call    cs:__imp_RegEnumKeyExW
0x180057638  test    eax, eax
0x18005763a  jz      loc_180057350
0x180057640  mov     rbx, [rbp+160h+var_168]
0x180057644  mov     [rsp+260h+string], rbx
0x180057649  test    rbx, rbx
0x18005764c  jz      short loc_180057655
0x18005764e  lock inc dword ptr [rbx+118h]
0x180057655  lea     rcx, [rbx+8]
0x180057659  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x18005765e  mov     [rbx+110h], r14d
0x180057665  lea     rcx, [rsp+260h+string]
0x18005766a  call    ??1?$test_data_control@V?$merged_data@U_tip_PerFolderRootCalculationTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PerFolderRootCalculationTest,_tip_PerFolderRootCalculationTest>>::~test_data_control<tip2::details::merged_data<_tip_PerFolderRootCalculationTest,_tip_PerFolderRootCalculationTest>>(void)
0x18005766f  mov     rcx, [rbp+160h+var_168]
0x180057673  add     rcx, 8
0x180057677  call    ?complete_without_lock@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::complete_without_lock(void)
0x18005767c  nop
0x18005767d  lea     rcx, [rsp+260h+hKey]
0x180057682  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180057687  nop
0x180057688  lea     rcx, [rbp+160h+var_1A0]
0x18005768c  call    ??1?$test_watcher@V?$merged_data@U_tip_PerFolderRootCalculationTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_PerFolderRootCalculationTest,_tip_PerFolderRootCalculationTest>>::~test_watcher<tip2::details::merged_data<_tip_PerFolderRootCalculationTest,_tip_PerFolderRootCalculationTest>>(void)
0x180057691  mov     rcx, [rbp+160h+var_50]
0x180057698  xor     rcx, rsp; StackCookie
0x18005769b  call    __security_check_cookie
0x1800576a0  add     rsp, 228h
0x1800576a7  pop     r15
0x1800576a9  pop     r14
0x1800576ab  pop     r13
0x1800576ad  pop     r12
0x1800576af  pop     rdi
0x1800576b0  pop     rsi
0x1800576b1  pop     rbx
0x1800576b2  pop     rbp
0x1800576b3  retn
0x1800576b4  mov     r9d, eax; char *
0x1800576b7  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\fileexplorer\\windo"...
0x1800576be  mov     edx, 0ABh; void *
0x1800576c3  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800576c9  mov     r9d, eax; char *
0x1800576cc  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\fileexplorer\\windo"...
0x1800576d3  mov     edx, 0B4h; void *
0x1800576d8  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
