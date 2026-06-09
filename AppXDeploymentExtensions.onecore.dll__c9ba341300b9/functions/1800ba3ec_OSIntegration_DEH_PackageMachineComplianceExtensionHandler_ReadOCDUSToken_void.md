# OSIntegration::DEH::PackageMachineComplianceExtensionHandler::ReadOCDUSToken(void)

- ea: `0x1800ba3ec`
- end: `0x1800baaa4`
- name: `?ReadOCDUSToken@PackageMachineComplianceExtensionHandler@DEH@OSIntegration@@AEAAJXZ`
- size: `1720`
- prototype: `__int64 __fastcall(OSIntegration::DEH::PackageMachineComplianceExtensionHandler *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18009eb10`

## callees

- `0x18000fed0`
- `0x180067050`
- `0x18006cb78`
- `0x180080b84`
- `0x180098bf4`
- `0x1800a021c`
- `0x1800ba3ec`
- `0x1800baaac`
- `0x1800efc84`
- `0x1800f0700`
- `0x1800f0a7c`
- `0x1801719a4`
- `0x180171bc4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800ba592`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800ba592`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800ba4e0`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800ba4e0`
- `ext-ms-win-ci-management-l1-1-2!ManageCI_ParseSbcpToken` at `0x1800ba63a`
- `ext-ms-win-ci-management-l1-1-2!ManageCI_ParseSbcpToken` at `0x1800ba63a`
- `ext-ms-win-ci-management-l1-1-2!ManageCI_QueryString` at `0x1800ba6d1`
- `ext-ms-win-ci-management-l1-1-2!ManageCI_QueryString` at `0x1800ba76d`
- `ext-ms-win-ci-management-l1-1-2!ManageCI_QueryString` at `0x1800ba814`
- `ext-ms-win-ci-management-l1-1-2!ManageCI_QueryString` at `0x1800ba6d1`
- `ext-ms-win-ci-management-l1-1-2!ManageCI_QueryString` at `0x1800ba76d`
- `ext-ms-win-ci-management-l1-1-2!ManageCI_QueryString` at `0x1800ba814`

## string_xrefs

- `0x1800ba430`: `onecore\admin\appmodel\osim\src\deh\appx\packagemachinecompliance\packagemachinecompliance.cpp`
- `0x1800ba4f2`: `onecore\admin\appmodel\osim\src\deh\appx\packagemachinecompliance\packagemachinecompliance.cpp`
- `0x1800ba534`: `onecore\admin\appmodel\osim\src\deh\appx\packagemachinecompliance\packagemachinecompliance.cpp`
- `0x1800ba5a4`: `onecore\admin\appmodel\osim\src\deh\appx\packagemachinecompliance\packagemachinecompliance.cpp`
- `0x1800ba5f1`: `onecore\admin\appmodel\osim\src\deh\appx\packagemachinecompliance\packagemachinecompliance.cpp`
- `0x1800ba651`: `onecore\admin\appmodel\osim\src\deh\appx\packagemachinecompliance\packagemachinecompliance.cpp`
- `0x1800ba6e8`: `onecore\admin\appmodel\osim\src\deh\appx\packagemachinecompliance\packagemachinecompliance.cpp`
- `0x1800ba784`: `onecore\admin\appmodel\osim\src\deh\appx\packagemachinecompliance\packagemachinecompliance.cpp`
- `0x1800ba82b`: `onecore\admin\appmodel\osim\src\deh\appx\packagemachinecompliance\packagemachinecompliance.cpp`
- `0x1800ba8b5`: `onecore\admin\appmodel\osim\src\deh\appx\packagemachinecompliance\packagemachinecompliance.cpp`
- `0x1800ba93b`: `onecore\admin\appmodel\osim\src\deh\appx\packagemachinecompliance\packagemachinecompliance.cpp`
- `0x1800ba9be`: `onecore\admin\appmodel\osim\src\deh\appx\packagemachinecompliance\packagemachinecompliance.cpp`
- `0x1800ba752`: `UserSid`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall OSIntegration::DEH::PackageMachineComplianceExtensionHandler::ReadOCDUSToken(
        OSIntegration::DEH::PackageMachineComplianceExtensionHandler *this)
{
  __int64 result; // rax
  int UserToken; // eax
  unsigned int v4; // edi
  HANDLE v5; // rsi
  int v6; // r14d
  const char *v8; // r9
  unsigned int v9; // ebx
  void *v10; // rdi
  const char *v11; // r9
  unsigned int LastError; // ebx
  unsigned __int64 v13; // rdx
  const char *v14; // r9
  unsigned __int64 v15; // rdx
  int v16; // eax
  unsigned int v17; // esi
  unsigned __int64 v18; // rdx
  int String; // eax
  unsigned int v20; // esi
  unsigned __int64 v21; // rdx
  int v22; // eax
  unsigned int v23; // esi
  unsigned __int64 v24; // rdx
  int v25; // eax
  struct _FILETIME *v26; // r8
  unsigned int v27; // esi
  unsigned __int64 v28; // rdx
  int v29; // eax
  unsigned int v30; // esi
  unsigned __int64 v31; // rdx
  int v32; // eax
  unsigned int v33; // esi
  unsigned __int64 v34; // rdx
  int v35; // eax
  unsigned int v36; // esi
  unsigned __int64 v37; // rdx
  unsigned __int64 v38; // rdx
  int lpOverlapped; // [rsp+20h] [rbp-68h]
  int lpOverlappeda; // [rsp+20h] [rbp-68h]
  unsigned __int16 *v41; // [rsp+30h] [rbp-58h] BYREF
  OSIntegration::DEH *v42; // [rsp+38h] [rbp-50h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+40h] [rbp-48h] BYREF
  struct _FILETIME FileTime; // [rsp+48h] [rbp-40h] BYREF
  void *v45; // [rsp+50h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  DWORD NumberOfBytesRead; // [rsp+90h] [rbp+8h] BYREF
  __int16 v48; // [rsp+95h] [rbp+Dh]
  char v49; // [rsp+97h] [rbp+Fh]
  HANDLE hFile; // [rsp+98h] [rbp+10h] BYREF
  __int64 v51; // [rsp+A0h] [rbp+18h] BYREF
  unsigned __int16 *v52; // [rsp+A8h] [rbp+20h] BYREF

  if ( *((_BYTE *)this + 28) )
    return 0;
  hFile = (HANDLE)-1LL;
  UserToken = OSIntegration::DEH::PackageMachineComplianceExtensionHandler::GetUserToken((__int64)this, &hFile);
  v4 = UserToken;
  if ( UserToken < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagemachinecompliance\\packagemachinecompliance.cpp",
      (const char *)(unsigned int)UserToken,
      lpOverlapped);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
    return v4;
  }
  v5 = hFile;
  if ( (char *)hFile - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &hFile,
      -1);
    v5 = hFile;
    if ( (((unsigned __int64)hFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      *((_DWORD *)this + 6) = 0;
      *((_BYTE *)this + 28) = 1;
      *(_WORD *)((char *)this + 29) = v48;
      *((_BYTE *)this + 31) = v49;
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
      return 0;
    }
    v6 = 2;
  }
  else
  {
    v6 = 1;
  }
  FileSize.QuadPart = 0;
  if ( GetFileSizeEx(v5, &FileSize) )
  {
    if ( FileSize.QuadPart <= 0x2000 )
    {
      try
      {
        v10 = operator new[](FileSize.LowPart);
        v45 = v10;
        NumberOfBytesRead = 0;
        if ( ReadFile(v5, v10, FileSize.LowPart, &NumberOfBytesRead, 0) )
        {
          if ( FileSize.LowPart == NumberOfBytesRead )
          {
            v51 = 0;
            v16 = ManageCI_ParseSbcpToken(v10, NumberOfBytesRead, &v51);
            v17 = v16;
            if ( v16 >= 0 )
            {
              v52 = 0;
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                &v52,
                0);
              String = ManageCI_QueryString(v51, 2164260864LL, L"Authorization", L"DeviceID");
              v20 = String;
              if ( String >= 0 )
              {
                v41 = 0;
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                  &v41,
                  0);
                v22 = ManageCI_QueryString(v51, 2164260864LL, L"Authorization", L"UserSid");
                v23 = v22;
                if ( v22 >= 0 )
                {
                  v42 = 0;
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                    &v42,
                    0);
                  v25 = ManageCI_QueryString(v51, 2164260864LL, L"Authorization", L"Expiration");
                  v27 = v25;
                  if ( v25 >= 0 )
                  {
                    FileTime = 0;
                    v29 = OSIntegration::DEH::DeserializeIso8601AsFILETIME(v42, &FileTime, v26);
                    v30 = v29;
                    if ( v29 >= 0 )
                    {
                      v32 = Common::StringBuffer::SetValueFromString(
                              (OSIntegration::DEH::PackageMachineComplianceExtensionHandler *)((char *)this + 160),
                              v52);
                      v33 = v32;
                      if ( v32 >= 0 )
                      {
                        v35 = Common::StringBuffer::SetValueFromString(
                                (OSIntegration::DEH::PackageMachineComplianceExtensionHandler *)((char *)this + 184),
                                v41);
                        v36 = v35;
                        if ( v35 >= 0 )
                        {
                          *((struct _FILETIME *)this + 32) = FileTime;
                          *((_DWORD *)this + 6) = v6;
                          *((_BYTE *)this + 28) = 1;
                          *(_WORD *)((char *)this + 29) = v48;
                          *((_BYTE *)this + 31) = v49;
                          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v42);
                          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v41);
                          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v52);
                          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void ManageCI_FreeSbcpHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void ManageCI_FreeSbcpHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v51);
                          operator delete(v10, v38);
                          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
                          result = 0;
                        }
                        else
                        {
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0x26E,
                            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagemachinecompliance\\pack"
                                          "agemachinecompliance.cpp",
                            (const char *)(unsigned int)v35,
                            (int)&v42);
                          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v42);
                          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v41);
                          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v52);
                          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void ManageCI_FreeSbcpHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void ManageCI_FreeSbcpHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v51);
                          operator delete(v10, v37);
                          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
                          result = v36;
                        }
                      }
                      else
                      {
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)0x26D,
                          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagemachinecompliance\\packag"
                                        "emachinecompliance.cpp",
                          (const char *)(unsigned int)v32,
                          (int)&v42);
                        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v42);
                        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v41);
                        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v52);
                        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void ManageCI_FreeSbcpHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void ManageCI_FreeSbcpHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v51);
                        operator delete(v10, v34);
                        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
                        result = v33;
                      }
                    }
                    else
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x26B,
                        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagemachinecompliance\\packagem"
                                      "achinecompliance.cpp",
                        (const char *)(unsigned int)v29,
                        (int)&v42);
                      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v42);
                      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v41);
                      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v52);
                      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void ManageCI_FreeSbcpHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void ManageCI_FreeSbcpHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v51);
                      operator delete(v10, v31);
                      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
                      result = v30;
                    }
                  }
                  else
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x269,
                      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagemachinecompliance\\packagemac"
                                    "hinecompliance.cpp",
                      (const char *)(unsigned int)v25,
                      (int)&v42);
                    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v42);
                    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v41);
                    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v52);
                    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void ManageCI_FreeSbcpHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void ManageCI_FreeSbcpHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v51);
                    operator delete(v10, v28);
                    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
                    result = v27;
                  }
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x266,
                    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagemachinecompliance\\packagemachi"
                                  "necompliance.cpp",
                    (const char *)(unsigned int)v22,
                    (int)&v41);
                  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v41);
                  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v52);
                  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void ManageCI_FreeSbcpHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void ManageCI_FreeSbcpHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v51);
                  operator delete(v10, v24);
                  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
                  result = v23;
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x263,
                  (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagemachinecompliance\\packagemachinecompliance.cpp",
                  (const char *)(unsigned int)String,
                  (int)&v52);
                wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v52);
                wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void ManageCI_FreeSbcpHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void ManageCI_FreeSbcpHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v51);
                operator delete(v10, v21);
                wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
                result = v20;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x260,
                (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagemachinecompliance\\packagemachinecompliance.cpp",
                (const char *)(unsigned int)v16,
                lpOverlappeda);
              wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void ManageCI_FreeSbcpHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void ManageCI_FreeSbcpHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v51);
              operator delete(v10, v18);
              wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
              result = v17;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x25D,
              (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagemachinecompliance\\packagemachinecompliance.cpp",
              (const char *)0x8007000DLL,
              lpOverlappeda);
            operator delete(v10, v15);
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
            result = 2147942413LL;
          }
        }
        else
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x25C,
                        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagemachinecompliance\\packagem"
                                      "achinecompliance.cpp",
                        v11);
          operator delete(v10, v13);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
          result = LastError;
        }
      }
      catch ( ... )
      {
        return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                               retaddr,
                               (void *)0x272,
                               (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagemachinecompliance\\p"
                                             "ackagemachinecompliance.cpp",
                               v14);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x256,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagemachinecompliance\\packagemachinecompliance.cpp",
        (const char *)0x8007000DLL,
        lpOverlapped);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
      return 2147942413LL;
    }
  }
  else
  {
    v9 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x255,
           (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagemachinecompliance\\packagemachinecompliance.cpp",
           v8);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x1800ba3ec  push    rbx
0x1800ba3ee  push    rsi
0x1800ba3ef  push    rdi
0x1800ba3f0  push    r14
0x1800ba3f2  sub     rsp, 68h
0x1800ba3f6  mov     rbx, rcx
0x1800ba3f9  cmp     byte ptr [rcx+1Ch], 0
0x1800ba3fd  jz      short loc_1800BA406
0x1800ba3ff  xor     eax, eax
0x1800ba401  jmp     loc_1800BAA99
0x1800ba406  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800ba40a  mov     [rsp+88h+hFile], r14
0x1800ba412  lea     rdx, [rsp+88h+hFile]
0x1800ba41a  call    ?GetUserToken@PackageMachineComplianceExtensionHandler@DEH@OSIntegration@@AEAAJAEAV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; OSIntegration::DEH::PackageMachineComplianceExtensionHandler::GetUserToken(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)
0x1800ba41f  mov     edi, eax
0x1800ba421  test    eax, eax
0x1800ba423  jns     short loc_1800BA456
0x1800ba425  mov     rcx, [rsp+88h]; this
0x1800ba42d  mov     r9d, eax; char *
0x1800ba430  lea     r8, aOnecoreAdminAp_15; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800ba437  mov     edx, 246h; void *
0x1800ba43c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ba441  nop
0x1800ba442  lea     rcx, [rsp+88h+hFile]
0x1800ba44a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800ba44f  mov     eax, edi
0x1800ba451  jmp     loc_1800BAA99
0x1800ba456  mov     rsi, [rsp+88h+hFile]
0x1800ba45e  lea     rax, [rsi-1]
0x1800ba462  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800ba466  ja      short loc_1800BA470
0x1800ba468  mov     r14d, 1
0x1800ba46e  jmp     short loc_1800BA4CF
0x1800ba470  mov     rdx, r14
0x1800ba473  lea     rcx, [rsp+88h+hFile]
0x1800ba47b  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800ba480  mov     rsi, [rsp+88h+hFile]
0x1800ba488  lea     rax, [rsi+1]
0x1800ba48c  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800ba492  jnz     short loc_1800BA4C9
0x1800ba494  mov     dword ptr [rbx+18h], 0
0x1800ba49b  mov     byte ptr [rbx+1Ch], 1
0x1800ba49f  movzx   eax, [rsp+88h+arg_5]
0x1800ba4a7  mov     [rbx+1Dh], ax
0x1800ba4ab  mov     al, [rsp+88h+arg_7]
0x1800ba4b2  mov     [rbx+1Fh], al
0x1800ba4b5  lea     rcx, [rsp+88h+hFile]
0x1800ba4bd  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800ba4c2  xor     eax, eax
0x1800ba4c4  jmp     loc_1800BAA99
0x1800ba4c9  mov     r14d, 2
0x1800ba4cf  mov     qword ptr [rsp+88h+FileSize], 0
0x1800ba4d8  lea     rdx, [rsp+88h+FileSize]; lpFileSize
0x1800ba4dd  mov     rcx, rsi; hFile
0x1800ba4e0  call    cs:__imp_GetFileSizeEx
0x1800ba4e6  test    eax, eax
0x1800ba4e8  jnz     short loc_1800BA519
0x1800ba4ea  mov     rcx, [rsp+88h]; this
0x1800ba4f2  lea     r8, aOnecoreAdminAp_15; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800ba4f9  mov     edx, 255h; void *
0x1800ba4fe  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800ba503  mov     ebx, eax
0x1800ba505  lea     rcx, [rsp+88h+hFile]
0x1800ba50d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800ba512  mov     eax, ebx
0x1800ba514  jmp     loc_1800BAA99
0x1800ba519  cmp     qword ptr [rsp+88h+FileSize], 2000h
0x1800ba522  jle     short loc_1800BA55A
0x1800ba524  mov     rcx, [rsp+88h]; this
0x1800ba52c  mov     ebx, 8007000Dh
0x1800ba531  mov     r9d, ebx; char *
0x1800ba534  lea     r8, aOnecoreAdminAp_15; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800ba53b  mov     edx, 256h; void *
0x1800ba540  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ba545  nop
0x1800ba546  lea     rcx, [rsp+88h+hFile]
0x1800ba54e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800ba553  mov     eax, ebx
0x1800ba555  jmp     loc_1800BAA99
0x1800ba55a  mov     ecx, dword ptr [rsp+88h+FileSize]; unsigned __int64
0x1800ba55e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800ba563  mov     rdi, rax
0x1800ba566  mov     [rsp+88h+var_38], rax
0x1800ba56b  mov     [rsp+88h+NumberOfBytesRead], 0
0x1800ba576  mov     qword ptr [rsp+88h+lpOverlapped], 0; int
0x1800ba57f  lea     r9, [rsp+88h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800ba587  mov     r8d, dword ptr [rsp+88h+FileSize]; nNumberOfBytesToRead
0x1800ba58c  mov     rdx, rax; lpBuffer
0x1800ba58f  mov     rcx, rsi; hFile
0x1800ba592  call    cs:__imp_ReadFile
0x1800ba598  test    eax, eax
0x1800ba59a  jnz     short loc_1800BA5D4
0x1800ba59c  mov     rcx, [rsp+88h]; this
0x1800ba5a4  lea     r8, aOnecoreAdminAp_15; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800ba5ab  mov     edx, 25Ch; void *
0x1800ba5b0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800ba5b5  mov     ebx, eax
0x1800ba5b7  mov     rcx, rdi; void *
0x1800ba5ba  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800ba5bf  nop
0x1800ba5c0  lea     rcx, [rsp+88h+hFile]
0x1800ba5c8  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800ba5cd  mov     eax, ebx
0x1800ba5cf  jmp     loc_1800BAA99
0x1800ba5d4  mov     eax, [rsp+88h+NumberOfBytesRead]
0x1800ba5db  cmp     dword ptr [rsp+88h+FileSize], eax
0x1800ba5df  jz      short loc_1800BA620
0x1800ba5e1  mov     rcx, [rsp+88h]; this
0x1800ba5e9  mov     ebx, 8007000Dh
0x1800ba5ee  mov     r9d, ebx; char *
0x1800ba5f1  lea     r8, aOnecoreAdminAp_15; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800ba5f8  mov     edx, 25Dh; void *
0x1800ba5fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ba602  nop
0x1800ba603  mov     rcx, rdi; void *
0x1800ba606  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800ba60b  nop
0x1800ba60c  lea     rcx, [rsp+88h+hFile]
0x1800ba614  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800ba619  mov     eax, ebx
0x1800ba61b  jmp     loc_1800BAA99
0x1800ba620  mov     [rsp+88h+arg_10], 0
0x1800ba62c  mov     rdx, rax
0x1800ba62f  lea     r8, [rsp+88h+arg_10]
0x1800ba637  mov     rcx, rdi
0x1800ba63a  call    cs:__imp_ManageCI_ParseSbcpToken
0x1800ba640  mov     esi, eax
0x1800ba642  test    eax, eax
0x1800ba644  jns     short loc_1800BA68E
0x1800ba646  mov     rcx, [rsp+88h]; this
0x1800ba64e  mov     r9d, eax; char *
0x1800ba651  lea     r8, aOnecoreAdminAp_15; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800ba658  mov     edx, 260h; void *
0x1800ba65d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ba662  nop
0x1800ba663  lea     rcx, [rsp+88h+arg_10]
0x1800ba66b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?ManageCI_FreeSbcpHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&ManageCI_FreeSbcpHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&ManageCI_FreeSbcpHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800ba670  nop
0x1800ba671  mov     rcx, rdi; void *
0x1800ba674  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800ba679  nop
0x1800ba67a  lea     rcx, [rsp+88h+hFile]
0x1800ba682  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800ba687  mov     eax, esi
0x1800ba689  jmp     loc_1800BAA99
0x1800ba68e  mov     [rsp+88h+arg_18], 0
0x1800ba69a  xor     edx, edx
0x1800ba69c  lea     rcx, [rsp+88h+arg_18]
0x1800ba6a4  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800ba6a9  lea     rax, [rsp+88h+arg_18]
0x1800ba6b1  mov     qword ptr [rsp+88h+lpOverlapped], rax; int
0x1800ba6b6  lea     r9, aDeviceid; "DeviceID"
0x1800ba6bd  lea     r8, aAuthorization; "Authorization"
0x1800ba6c4  mov     edx, 81000000h
0x1800ba6c9  mov     rcx, [rsp+88h+arg_10]
0x1800ba6d1  call    cs:__imp_ManageCI_QueryString
0x1800ba6d7  mov     esi, eax
0x1800ba6d9  test    eax, eax
0x1800ba6db  jns     short loc_1800BA733
0x1800ba6dd  mov     rcx, [rsp+88h]; this
0x1800ba6e5  mov     r9d, eax; char *
0x1800ba6e8  lea     r8, aOnecoreAdminAp_15; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800ba6ef  mov     edx, 263h; void *
0x1800ba6f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ba6f9  nop
0x1800ba6fa  lea     rcx, [rsp+88h+arg_18]
0x1800ba702  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800ba707  nop
0x1800ba708  lea     rcx, [rsp+88h+arg_10]
0x1800ba710  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?ManageCI_FreeSbcpHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&ManageCI_FreeSbcpHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&ManageCI_FreeSbcpHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800ba715  nop
0x1800ba716  mov     rcx, rdi; void *
0x1800ba719  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800ba71e  nop
0x1800ba71f  lea     rcx, [rsp+88h+hFile]
0x1800ba727  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800ba72c  mov     eax, esi
0x1800ba72e  jmp     loc_1800BAA99
0x1800ba733  mov     [rsp+88h+var_58], 0
0x1800ba73c  xor     edx, edx
0x1800ba73e  lea     rcx, [rsp+88h+var_58]
0x1800ba743  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800ba748  lea     rax, [rsp+88h+var_58]
0x1800ba74d  mov     qword ptr [rsp+88h+lpOverlapped], rax; int
0x1800ba752  lea     r9, aUsersid; "UserSid"
0x1800ba759  lea     r8, aAuthorization; "Authorization"
0x1800ba760  mov     edx, 81000000h
0x1800ba765  mov     rcx, [rsp+88h+arg_10]
0x1800ba76d  call    cs:__imp_ManageCI_QueryString
0x1800ba773  mov     esi, eax
0x1800ba775  test    eax, eax
0x1800ba777  jns     short loc_1800BA7DA
0x1800ba779  mov     rcx, [rsp+88h]; this
0x1800ba781  mov     r9d, eax; char *
0x1800ba784  lea     r8, aOnecoreAdminAp_15; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800ba78b  mov     edx, 266h; void *
0x1800ba790  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ba795  nop
0x1800ba796  lea     rcx, [rsp+88h+var_58]
0x1800ba79b  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800ba7a0  nop
0x1800ba7a1  lea     rcx, [rsp+88h+arg_18]
0x1800ba7a9  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800ba7ae  nop
0x1800ba7af  lea     rcx, [rsp+88h+arg_10]
0x1800ba7b7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?ManageCI_FreeSbcpHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&ManageCI_FreeSbcpHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&ManageCI_FreeSbcpHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800ba7bc  nop
0x1800ba7bd  mov     rcx, rdi; void *
0x1800ba7c0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800ba7c5  nop
0x1800ba7c6  lea     rcx, [rsp+88h+hFile]
0x1800ba7ce  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800ba7d3  mov     eax, esi
0x1800ba7d5  jmp     loc_1800BAA99
0x1800ba7da  mov     [rsp+88h+var_50], 0
0x1800ba7e3  xor     edx, edx
0x1800ba7e5  lea     rcx, [rsp+88h+var_50]
0x1800ba7ea  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800ba7ef  lea     rax, [rsp+88h+var_50]
0x1800ba7f4  mov     qword ptr [rsp+88h+lpOverlapped], rax; int
0x1800ba7f9  lea     r9, aExpiration; "Expiration"
0x1800ba800  lea     r8, aAuthorization; "Authorization"
0x1800ba807  mov     edx, 81000000h
0x1800ba80c  mov     rcx, [rsp+88h+arg_10]
0x1800ba814  call    cs:__imp_ManageCI_QueryString
0x1800ba81a  mov     esi, eax
0x1800ba81c  test    eax, eax
0x1800ba81e  jns     short loc_1800BA88C
0x1800ba820  mov     rcx, [rsp+88h]; this
0x1800ba828  mov     r9d, eax; char *
0x1800ba82b  lea     r8, aOnecoreAdminAp_15; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800ba832  mov     edx, 269h; void *
0x1800ba837  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ba83c  nop
0x1800ba83d  lea     rcx, [rsp+88h+var_50]
0x1800ba842  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800ba847  nop
0x1800ba848  lea     rcx, [rsp+88h+var_58]
0x1800ba84d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800ba852  nop
0x1800ba853  lea     rcx, [rsp+88h+arg_18]
0x1800ba85b  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800ba860  nop
0x1800ba861  lea     rcx, [rsp+88h+arg_10]
0x1800ba869  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?ManageCI_FreeSbcpHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&ManageCI_FreeSbcpHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&ManageCI_FreeSbcpHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800ba86e  nop
0x1800ba86f  mov     rcx, rdi; void *
0x1800ba872  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800ba877  nop
0x1800ba878  lea     rcx, [rsp+88h+hFile]
0x1800ba880  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800ba885  mov     eax, esi
0x1800ba887  jmp     loc_1800BAA99
0x1800ba88c  mov     qword ptr [rsp+88h+FileTime.dwLowDateTime], 0
0x1800ba895  lea     rdx, [rsp+88h+FileTime]; lpFileTime
0x1800ba89a  mov     rcx, [rsp+88h+var_50]; this
0x1800ba89f  call    ?DeserializeIso8601AsFILETIME@DEH@OSIntegration@@YAJPEBGAEAU_FILETIME@@@Z; OSIntegration::DEH::DeserializeIso8601AsFILETIME(ushort const *,_FILETIME &)
0x1800ba8a4  mov     esi, eax
0x1800ba8a6  test    eax, eax
0x1800ba8a8  jns     short loc_1800BA916
0x1800ba8aa  mov     rcx, [rsp+88h]; this
0x1800ba8b2  mov     r9d, eax; char *
0x1800ba8b5  lea     r8, aOnecoreAdminAp_15; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800ba8bc  mov     edx, 26Bh; void *
0x1800ba8c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ba8c6  nop
0x1800ba8c7  lea     rcx, [rsp+88h+var_50]
0x1800ba8cc  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800ba8d1  nop
0x1800ba8d2  lea     rcx, [rsp+88h+var_58]
0x1800ba8d7  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800ba8dc  nop
0x1800ba8dd  lea     rcx, [rsp+88h+arg_18]
0x1800ba8e5  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800ba8ea  nop
0x1800ba8eb  lea     rcx, [rsp+88h+arg_10]
0x1800ba8f3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?ManageCI_FreeSbcpHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&ManageCI_FreeSbcpHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&ManageCI_FreeSbcpHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800ba8f8  nop
0x1800ba8f9  mov     rcx, rdi; void *
0x1800ba8fc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800ba901  nop
0x1800ba902  lea     rcx, [rsp+88h+hFile]
0x1800ba90a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800ba90f  mov     eax, esi
0x1800ba911  jmp     loc_1800BAA99
0x1800ba916  lea     rcx, [rbx+0A0h]; this
0x1800ba91d  mov     rdx, [rsp+88h+arg_18]; unsigned __int16 *
0x1800ba925  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x1800ba92a  mov     esi, eax
0x1800ba92c  test    eax, eax
0x1800ba92e  jns     short loc_1800BA99C
0x1800ba930  mov     rcx, [rsp+88h]; this
0x1800ba938  mov     r9d, eax; char *
0x1800ba93b  lea     r8, aOnecoreAdminAp_15; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800ba942  mov     edx, 26Dh; void *
0x1800ba947  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ba94c  nop
0x1800ba94d  lea     rcx, [rsp+88h+var_50]
0x1800ba952  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800ba957  nop
  ... truncated ...
```
