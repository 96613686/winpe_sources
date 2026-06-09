# SystemSettings::StorageSenseHandlers::CStoragePolicyOptimizeStorageActionForUser::get_Description(HSTRING__ * *)

- ea: `0x1800818c0`
- end: `0x180081bb8`
- name: `?get_Description@CStoragePolicyOptimizeStorageActionForUser@StorageSenseHandlers@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `760`
- prototype: `int(SystemSettings::StorageSenseHandlers::CStoragePolicyOptimizeStorageActionForUser *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180006e50`
- `0x180007a00`
- `0x18001dfe8`
- `0x1800292a8`
- `0x18002bad4`
- `0x180035c0c`
- `0x18003b450`
- `0x180046d68`
- `0x18005d26c`
- `0x1800818c0`
- `0x1800b38a8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180081a93`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180081a93`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180081a1f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180081a65`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180081a1f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180081a65`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18008199a`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18008199a`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!StrFormatByteSizeEx` at `0x18008197b`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!StrFormatByteSizeEx` at `0x18008197b`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x1800819d5`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x1800819d5`
- `ext-ms-win-storage-sense-l1-2-0!GetStoragePolicySettings` at `0x180081951`
- `ext-ms-win-storage-sense-l1-2-0!GetStoragePolicySettings` at `0x180081951`
- `ext-ms-win-storage-sense-l1-2-4!GetStoragePoliciesLastTriggerTime` at `0x180081a7b`
- `ext-ms-win-storage-sense-l1-2-4!GetStoragePoliciesLastTriggerTime` at `0x180081a7b`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SystemSettings::StorageSenseHandlers::CStoragePolicyOptimizeStorageActionForUser::get_Description(
        SystemSettings::StorageSenseHandlers::CStoragePolicyOptimizeStorageActionForUser *this,
        HSTRING *a2)
{
  unsigned int v3; // eax
  HRESULT v4; // r14d
  LSTATUS v5; // eax
  signed int v6; // ebx
  LSTATUS v7; // eax
  LSTATUS ValueW; // eax
  LSTATUS v9; // eax
  int StoragePoliciesLastTriggerTime; // eax
  __int64 v11; // rdx
  HSTRING *v12; // r8
  FILETIME *p_FileTime2; // rbx
  unsigned __int16 **v14; // r8
  int v15; // eax
  int ResourceStringById; // ebx
  __int64 v17; // rdx
  __int64 v18; // r8
  SystemSettings::DataModel *v20; // [rsp+40h] [rbp-C0h] BYREF
  struct _FILETIME v21; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v22; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pcbData; // [rsp+54h] [rbp-ACh] BYREF
  FILETIME FileTime1; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hkey; // [rsp+60h] [rbp-A0h] BYREF
  FILETIME FileTime2; // [rsp+68h] [rbp-98h] BYREF
  HKEY phkResult[2]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR pszBuf[64]; // [rsp+80h] [rbp-80h] BYREF

  *a2 = 0;
  phkResult[0] = 0;
  hkey = 0;
  FileTime1 = 0;
  FileTime2 = 0;
  pcbData = 4;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  memset_0(pszBuf, 0, sizeof(pszBuf));
  if ( (int)GetStoragePolicySettings(4, 0, &v22) >= 0 )
  {
    v3 = v22;
  }
  else
  {
    v3 = 0;
    v22 = 0;
  }
  v4 = StrFormatByteSizeEx((unsigned __int64)v3 << 20, 2, pszBuf, 0x40u);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    phkResult,
    0);
  v5 = RegOpenCurrentUser(0x20019u, phkResult);
  v6 = v5;
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  if ( v6 >= 0 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hkey,
      0);
    v7 = RegOpenKeyW(
           phkResult[0],
           L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters\\OptimizeStorage",
           &hkey);
    v6 = v7;
    if ( v7 > 0 )
      v6 = (unsigned __int16)v7 | 0x80070000;
    if ( v6 >= 0 )
    {
      ValueW = RegGetValueW(hkey, 0, L"OptimizeStorageLastRunHighPart", 0x18u, 0, &FileTime1.dwHighDateTime, &pcbData);
      v6 = ValueW;
      if ( ValueW > 0 )
        v6 = (unsigned __int16)ValueW | 0x80070000;
      if ( v6 >= 0 )
      {
        v9 = RegGetValueW(hkey, 0, L"OptimizeStorageLastRunLowPart", 0x18u, 0, &FileTime1, &pcbData);
        v6 = v9;
        if ( v9 > 0 )
          v6 = (unsigned __int16)v9 | 0x80070000;
      }
    }
  }
  StoragePoliciesLastTriggerTime = GetStoragePoliciesLastTriggerTime(&FileTime2);
  if ( v6 < 0 )
  {
    if ( StoragePoliciesLastTriggerTime < 0 )
      goto LABEL_27;
    p_FileTime2 = &FileTime2;
  }
  else if ( StoragePoliciesLastTriggerTime < 0 )
  {
    p_FileTime2 = &FileTime1;
  }
  else
  {
    p_FileTime2 = &FileTime1;
    if ( CompareFileTime(&FileTime1, &FileTime2) == -1 )
      p_FileTime2 = &FileTime2;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v21,
    0);
  if ( (int)SystemSettings::StorageSenseHandlers::StringHelpers::GetDateTimeString(
              (SystemSettings::StorageSenseHandlers::StringHelpers *)p_FileTime2,
              &v21,
              v14) >= 0 )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v20,
      0);
    if ( v4 < 0 )
      v15 = SystemSettings::DataModel::FormatResourceMessageArgAlloc(
              (SystemSettings::DataModel *)L"SystemSettings_StorageSense_OptimizeStorage_Description_PreviouslyRun",
              (const unsigned __int16 *)&v20,
              *(unsigned __int16 ***)&v21);
    else
      v15 = SystemSettings::DataModel::FormatResourceMessageArgAlloc(
              (SystemSettings::DataModel *)L"SystemSettings_StorageSense_OptimizeStorage_Description_SpaceHistory_PreviouslyRun",
              (const unsigned __int16 *)&v20,
              (unsigned __int16 **)pszBuf,
              v21);
    goto LABEL_29;
  }
LABEL_27:
  ResourceStringById = 0;
  if ( v4 < 0 )
    goto LABEL_32;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v20,
    0);
  v15 = SystemSettings::DataModel::FormatResourceMessageArgAlloc(
          (SystemSettings::DataModel *)L"SystemSettings_StorageSense_OptimizeStorage_Description_SpaceHistory",
          (const unsigned __int16 *)&v20,
          (unsigned __int16 **)pszBuf);
LABEL_29:
  if ( v15 < 0
    || (ResourceStringById = SystemSettings::DataModel::WindowsCreateString(v20, (const unsigned __int16 *)a2, v12),
        ResourceStringById < 0) )
  {
    ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                           (SystemSettings::DataModel *)L"SystemSettings_StorageSense_OptimizeStorage_Description",
                           a2,
                           v12);
  }
LABEL_32:
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(
    &v21,
    v11,
    v12);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(
    &v20,
    v17,
    v18);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(phkResult);
  return (unsigned int)ResourceStringById;
}

```

## disassembly

```asm
0x1800818c0  mov     [rsp-8+arg_0], rbx
0x1800818c5  mov     [rsp-8+arg_10], rsi
0x1800818ca  push    rbp
0x1800818cb  push    rdi
0x1800818cc  push    r14
0x1800818ce  lea     rbp, [rsp-10h]
0x1800818d3  sub     rsp, 110h
0x1800818da  mov     rax, cs:__security_cookie
0x1800818e1  xor     rax, rsp
0x1800818e4  mov     [rbp+20h+var_20], rax
0x1800818e8  mov     rsi, rdx
0x1800818eb  mov     qword ptr [rdx], 0
0x1800818f2  mov     [rsp+120h+phkResult], 0
0x1800818fb  mov     [rsp+120h+hkey], 0
0x180081904  mov     qword ptr [rsp+120h+FileTime1.dwLowDateTime], 0
0x18008190d  mov     qword ptr [rsp+120h+FileTime2.dwLowDateTime], 0
0x180081916  mov     ebx, 4
0x18008191b  mov     [rsp+120h+var_CC], ebx
0x18008191f  mov     [rsp+120h+var_E0], 0
0x180081928  mov     qword ptr [rsp+120h+var_D8.dwLowDateTime], 0
0x180081931  mov     [rsp+120h+var_D0], 0
0x180081939  xor     edx, edx; Val
0x18008193b  lea     r8d, [rbx+7Ch]; Size
0x18008193f  lea     rcx, [rbp+20h+pszBuf]; void *
0x180081943  call    memset_0
0x180081948  lea     r8, [rsp+120h+var_D0]
0x18008194d  xor     edx, edx
0x18008194f  mov     ecx, ebx
0x180081951  call    cs:__imp_GetStoragePolicySettings
0x180081957  test    eax, eax
0x180081959  jns     short loc_180081963
0x18008195b  xor     eax, eax
0x18008195d  mov     [rsp+120h+var_D0], eax
0x180081961  jmp     short loc_180081967
0x180081963  mov     eax, [rsp+120h+var_D0]
0x180081967  mov     ecx, eax
0x180081969  shl     rcx, 14h; ull
0x18008196d  mov     r9d, 40h ; '@'; cchBuf
0x180081973  lea     r8, [rbp+20h+pszBuf]; pszBuf
0x180081977  lea     edx, [r9-3Eh]; flags
0x18008197b  call    cs:__imp_StrFormatByteSizeEx
0x180081981  mov     r14d, eax
0x180081984  xor     edx, edx
0x180081986  lea     rcx, [rsp+120h+phkResult]
0x18008198b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180081990  lea     rdx, [rsp+120h+phkResult]; phkResult
0x180081995  mov     ecx, 20019h; samDesired
0x18008199a  call    cs:__imp_RegOpenCurrentUser
0x1800819a0  mov     ebx, eax
0x1800819a2  mov     edi, 80070000h
0x1800819a7  test    eax, eax
0x1800819a9  jle     short loc_1800819B0
0x1800819ab  movzx   ebx, ax
0x1800819ae  or      ebx, edi
0x1800819b0  test    ebx, ebx
0x1800819b2  js      loc_180081A76
0x1800819b8  xor     edx, edx
0x1800819ba  lea     rcx, [rsp+120h+hkey]
0x1800819bf  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800819c4  lea     r8, [rsp+120h+hkey]; phkResult
0x1800819c9  lea     rdx, aSoftwareMicros_12; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800819d0  mov     rcx, [rsp+120h+phkResult]; hKey
0x1800819d5  call    cs:__imp_RegOpenKeyW
0x1800819db  mov     ebx, eax
0x1800819dd  test    eax, eax
0x1800819df  jle     short loc_1800819E6
0x1800819e1  movzx   ebx, ax
0x1800819e4  or      ebx, edi
0x1800819e6  test    ebx, ebx
0x1800819e8  js      loc_180081A76
0x1800819ee  lea     rax, [rsp+120h+var_CC]
0x1800819f3  mov     [rsp+120h+pcbData], rax; pcbData
0x1800819f8  lea     rax, [rsp+120h+FileTime1.dwHighDateTime]
0x1800819fd  mov     [rsp+120h+pvData], rax; pvData
0x180081a02  mov     [rsp+120h+pdwType], 0; pdwType
0x180081a0b  mov     r9d, 18h; dwFlags
0x180081a11  lea     r8, aOptimizestorag_0; "OptimizeStorageLastRunHighPart"
0x180081a18  xor     edx, edx; lpSubKey
0x180081a1a  mov     rcx, [rsp+120h+hkey]; hkey
0x180081a1f  call    cs:__imp_RegGetValueW
0x180081a25  mov     ebx, eax
0x180081a27  test    eax, eax
0x180081a29  jle     short loc_180081A30
0x180081a2b  movzx   ebx, ax
0x180081a2e  or      ebx, edi
0x180081a30  test    ebx, ebx
0x180081a32  js      short loc_180081A76
0x180081a34  lea     rax, [rsp+120h+var_CC]
0x180081a39  mov     [rsp+120h+pcbData], rax; pcbData
0x180081a3e  lea     rax, [rsp+120h+FileTime1]
0x180081a43  mov     [rsp+120h+pvData], rax; pvData
0x180081a48  mov     [rsp+120h+pdwType], 0; pdwType
0x180081a51  mov     r9d, 18h; dwFlags
0x180081a57  lea     r8, aOptimizestorag; "OptimizeStorageLastRunLowPart"
0x180081a5e  xor     edx, edx; lpSubKey
0x180081a60  mov     rcx, [rsp+120h+hkey]; hkey
0x180081a65  call    cs:__imp_RegGetValueW
0x180081a6b  mov     ebx, eax
0x180081a6d  test    eax, eax
0x180081a6f  jle     short loc_180081A76
0x180081a71  movzx   ebx, ax
0x180081a74  or      ebx, edi
0x180081a76  lea     rcx, [rsp+120h+FileTime2]
0x180081a7b  call    cs:__imp_GetStoragePoliciesLastTriggerTime
0x180081a81  test    ebx, ebx
0x180081a83  js      short loc_180081AB3
0x180081a85  test    eax, eax
0x180081a87  js      short loc_180081AAC
0x180081a89  lea     rdx, [rsp+120h+FileTime2]; lpFileTime2
0x180081a8e  lea     rcx, [rsp+120h+FileTime1]; lpFileTime1
0x180081a93  call    cs:__imp_CompareFileTime
0x180081a99  lea     rbx, [rsp+120h+FileTime1]
0x180081a9e  lea     rcx, [rsp+120h+FileTime2]
0x180081aa3  cmp     eax, 0FFFFFFFFh
0x180081aa6  cmovz   rbx, rcx
0x180081aaa  jmp     short loc_180081ABC
0x180081aac  lea     rbx, [rsp+120h+FileTime1]
0x180081ab1  jmp     short loc_180081ABC
0x180081ab3  test    eax, eax
0x180081ab5  js      short loc_180081B17
0x180081ab7  lea     rbx, [rsp+120h+FileTime2]
0x180081abc  lea     rdi, [rsp+120h+var_D8]
0x180081ac1  lea     rcx, [rsp+120h+var_D8]
0x180081ac6  xor     edx, edx
0x180081ac8  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180081acd  mov     rdx, rdi; struct _FILETIME *
0x180081ad0  mov     rcx, rbx; this
0x180081ad3  call    ?GetDateTimeString@StringHelpers@StorageSenseHandlers@SystemSettings@@YAJPEAU_FILETIME@@PEAPEAG@Z; SystemSettings::StorageSenseHandlers::StringHelpers::GetDateTimeString(_FILETIME *,ushort * *)
0x180081ad8  test    eax, eax
0x180081ada  js      short loc_180081B17
0x180081adc  xor     edx, edx
0x180081ade  lea     rcx, [rsp+120h+var_E0]
0x180081ae3  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180081ae8  lea     rdx, [rsp+120h+var_E0]; unsigned __int16 *
0x180081aed  test    r14d, r14d
0x180081af0  js      short loc_180081B09
0x180081af2  mov     r9, qword ptr [rsp+120h+var_D8.dwLowDateTime]
0x180081af7  lea     r8, [rbp+20h+pszBuf]; unsigned __int16 **
0x180081afb  lea     rcx, aSystemsettings_104; "SystemSettings_StorageSense_OptimizeSto"...
0x180081b02  call    ?FormatResourceMessageArgAlloc@DataModel@SystemSettings@@YAJPEBGPEAPEAGZZ; SystemSettings::DataModel::FormatResourceMessageArgAlloc(ushort const *,ushort * *,...)
0x180081b07  jmp     short loc_180081B3F
0x180081b09  mov     r8, qword ptr [rsp+120h+var_D8.dwLowDateTime]
0x180081b0e  lea     rcx, aSystemsettings_287; "SystemSettings_StorageSense_OptimizeSto"...
0x180081b15  jmp     short loc_180081B3A
0x180081b17  xor     ebx, ebx
0x180081b19  test    r14d, r14d
0x180081b1c  js      short loc_180081B67
0x180081b1e  xor     edx, edx
0x180081b20  lea     rcx, [rsp+120h+var_E0]
0x180081b25  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180081b2a  lea     r8, [rbp+20h+pszBuf]; unsigned __int16 **
0x180081b2e  lea     rdx, [rsp+120h+var_E0]; unsigned __int16 *
0x180081b33  lea     rcx, aSystemsettings_248; "SystemSettings_StorageSense_OptimizeSto"...
0x180081b3a  call    ?FormatResourceMessageArgAlloc@DataModel@SystemSettings@@YAJPEBGPEAPEAGZZ; SystemSettings::DataModel::FormatResourceMessageArgAlloc(ushort const *,ushort * *,...)
0x180081b3f  test    eax, eax
0x180081b41  js      short loc_180081B56
0x180081b43  mov     rdx, rsi; unsigned __int16 *
0x180081b46  mov     rcx, [rsp+120h+var_E0]; this
0x180081b4b  call    ?WindowsCreateString@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::WindowsCreateString(ushort const *,HSTRING__ * *)
0x180081b50  mov     ebx, eax
0x180081b52  test    eax, eax
0x180081b54  jns     short loc_180081B67
0x180081b56  mov     rdx, rsi; HSTRING *
0x180081b59  lea     rcx, aSystemsettings_192; "SystemSettings_StorageSense_OptimizeSto"...
0x180081b60  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x180081b65  mov     ebx, eax
0x180081b67  lea     rcx, [rsp+120h+var_D8]
0x180081b6c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180081b71  nop
0x180081b72  lea     rcx, [rsp+120h+var_E0]
0x180081b77  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180081b7c  nop
0x180081b7d  lea     rcx, [rsp+120h+hkey]
0x180081b82  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180081b87  nop
0x180081b88  lea     rcx, [rsp+120h+phkResult]
0x180081b8d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180081b92  mov     eax, ebx
0x180081b94  mov     rcx, [rbp+20h+var_20]
0x180081b98  xor     rcx, rsp; StackCookie
0x180081b9b  call    __security_check_cookie
0x180081ba0  lea     r11, [rsp+120h+var_10]
0x180081ba8  mov     rbx, [r11+20h]
0x180081bac  mov     rsi, [r11+30h]
0x180081bb0  mov     rsp, r11
0x180081bb3  pop     r14
0x180081bb5  pop     rdi
0x180081bb6  pop     rbp
0x180081bb7  retn
```
