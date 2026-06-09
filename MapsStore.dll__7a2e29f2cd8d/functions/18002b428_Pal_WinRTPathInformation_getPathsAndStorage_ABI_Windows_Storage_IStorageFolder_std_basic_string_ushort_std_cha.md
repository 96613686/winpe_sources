# Pal::WinRTPathInformation::getPathsAndStorage(ABI::Windows::Storage::IStorageFolder * *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,ABI::Windows::Storage::IStorageFolder * *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,ABI::Windows::Storage::IStorageFolder * *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,ABI::Windows::Storage::IStorageFolder * *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x18002b428`
- end: `0x18002b9f0`
- name: `?getPathsAndStorage@WinRTPathInformation@Pal@@SAXPEAPEAUIStorageFolder@Storage@Windows@ABI@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@010101@Z`
- size: `1480`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002b370`

## callees

- `0x18000d090`
- `0x18000dce0`
- `0x1800126c4`
- `0x180012720`
- `0x1800179ac`
- `0x180019f3c`
- `0x180021da8`
- `0x180022000`
- `0x180024a34`
- `0x180025360`
- `0x180025398`
- `0x180027054`
- `0x18002b428`
- `0x18002bbd8`
- `0x18002d9d8`
- `0x180098010`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18002b556`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18002b62f`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18002b71b`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18002b7d8`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18002b87e`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18002b556`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18002b62f`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18002b71b`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18002b7d8`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18002b87e`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x18002b561`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x18002b63a`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x18002b726`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x18002b7e3`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x18002b889`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x18002b561`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x18002b63a`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x18002b726`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x18002b7e3`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x18002b889`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002b511`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002b511`

## string_xrefs

- `0x18002b605`: `Failed to get_InstalledLocation`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall Pal::WinRTPathInformation::getPathsAndStorage(
        struct ABI::Windows::Storage::IStorageFolder **a1,
        __int64 a2,
        struct ABI::Windows::Storage::IStorageFolder **a3,
        __int64 a4,
        struct ABI::Windows::Storage::IStorageFolder **a5,
        __int64 a6,
        struct ABI::Windows::Storage::IStorageFolder **a7,
        __int64 a8)
{
  _QWORD *v10; // r8
  __int64 v11; // r9
  __int64 v12; // rdx
  __int64 v13; // rbx
  int ActivationFactory; // ebx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, __int64 *); // rbx
  int v21; // eax
  int v22; // ebx
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 StorageFolderPath; // rax
  int v28; // ebx
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rdi
  __int64 (__fastcall *v34)(__int64, __int64 *); // rbx
  int v35; // ebx
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  int v40; // ebx
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v49; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v50; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v51; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v52; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v53; // [rsp+40h] [rbp-C0h]
  __int64 v54; // [rsp+48h] [rbp-B8h]
  __int64 v55; // [rsp+50h] [rbp-B0h]
  _BYTE v56[16]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v57[8]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v58[232]; // [rsp+78h] [rbp-88h] BYREF
  HSTRING_HEADER pExceptionObject; // [rsp+160h] [rbp+60h] BYREF
  __int64 v60; // [rsp+178h] [rbp+78h]
  _BYTE v61[32]; // [rsp+180h] [rbp+80h] BYREF

  v54 = a4;
  v53 = a2;
  v55 = a8;
  *a1 = 0;
  *(_QWORD *)(a2 + 16) = 0;
  *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2) = 0;
  *v10 = 0;
  *(_QWORD *)(v11 + 16) = 0;
  *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v11) = 0;
  *a5 = 0;
  *(_QWORD *)(a6 + 16) = 0;
  *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a6) = 0;
  *a7 = 0;
  *(_QWORD *)(v12 + 16) = 0;
  *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v12) = 0;
  v51 = 0;
  v60 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &pExceptionObject,
    L"Windows.ApplicationModel.Package",
    0x21u,
    0x20u);
  v13 = v60;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
  ActivationFactory = RoGetActivationFactory(v13, &GUID_4e534bdf_2960_4878_97a4_9624deb72f2d, &v51);
  if ( ActivationFactory < 0 )
  {
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v56);
    v15 = std::operator<<<std::char_traits<char>>(
            v57,
            "Failed to retrieve the activation factory for Windows.ApplicationModel.Package");
    v16 = std::operator<<<std::char_traits<char>>(v15, " (HRESULT: 0x");
    v17 = std::ostream::operator<<(v16, std::hex);
    v18 = std::ostream::operator<<(v17, (unsigned int)ActivationFactory);
    std::operator<<<std::char_traits<char>>(v18, ")");
    std::stringbuf::str(v58, v61);
    std::runtime_error::runtime_error((std::exception *)&pExceptionObject);
    throw (std::runtime_error *)&pExceptionObject;
  }
  v50 = 0;
  v19 = v51;
  v20 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v51 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
  v21 = v20(v19, &v50);
  if ( v21 < 0 )
  {
    if ( v21 != -2147009196 )
    {
      std::runtime_error::runtime_error((std::runtime_error *)&pExceptionObject, "Failed to get current Package");
      throw (std::runtime_error *)&pExceptionObject;
    }
  }
  else
  {
    v22 = (*(__int64 (__fastcall **)(__int64, struct ABI::Windows::Storage::IStorageFolder **))(*(_QWORD *)v50 + 56LL))(
            v50,
            a1);
    if ( v22 < 0 )
    {
      std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v56);
      v23 = std::operator<<<std::char_traits<char>>(v57, "Failed to get_InstalledLocation");
      v24 = std::operator<<<std::char_traits<char>>(v23, " (HRESULT: 0x");
      v25 = std::ostream::operator<<(v24, std::hex);
      v26 = std::ostream::operator<<(v25, (unsigned int)v22);
      std::operator<<<std::char_traits<char>>(v26, ")");
      std::stringbuf::str(v58, v61);
      std::runtime_error::runtime_error((std::exception *)&pExceptionObject);
      throw (std::runtime_error *)&pExceptionObject;
    }
    StorageFolderPath = Pal::WinRTPathInformation::getStorageFolderPath((__int64)v61, *a1);
    std::wstring::operator=(v53, StorageFolderPath);
    std::wstring::_Tidy_deallocate(v61);
    v52 = 0;
    v60 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &pExceptionObject,
      L"Windows.Storage.ApplicationData",
      0x20u,
      0x1Fu);
    v28 = ABI::Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<ABI::Windows::Storage::IApplicationDataStatics>>(
            v60,
            &v52);
    if ( v28 < 0 )
    {
      std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v56);
      v29 = std::operator<<<std::char_traits<char>>(
              v57,
              "Failed to retrieve the activation factory for Windows.Storage.ApplicationData");
      v30 = std::operator<<<std::char_traits<char>>(v29, " (HRESULT: 0x");
      v31 = std::ostream::operator<<(v30, std::hex);
      v32 = std::ostream::operator<<(v31, (unsigned int)v28);
      std::operator<<<std::char_traits<char>>(v32, ")");
      std::stringbuf::str(v58, v61);
      std::runtime_error::runtime_error((std::exception *)&pExceptionObject);
      throw (std::runtime_error *)&pExceptionObject;
    }
    v49 = 0;
    v33 = v52;
    v34 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v52 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49);
    v35 = v34(v33, &v49);
    if ( v35 < 0 )
    {
      std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v56);
      v36 = std::operator<<<std::char_traits<char>>(v57, "Failed to get_Current on IApplicationDataStatics");
      v37 = std::operator<<<std::char_traits<char>>(v36, " (HRESULT: 0x");
      v38 = std::ostream::operator<<(v37, std::hex);
      v39 = std::ostream::operator<<(v38, (unsigned int)v35);
      std::operator<<<std::char_traits<char>>(v39, ")");
      std::stringbuf::str(v58, v61);
      std::runtime_error::runtime_error((std::exception *)&pExceptionObject);
      throw (std::runtime_error *)&pExceptionObject;
    }
    v40 = (*(__int64 (__fastcall **)(__int64, struct ABI::Windows::Storage::IStorageFolder **))(*(_QWORD *)v49 + 96LL))(
            v49,
            a3);
    if ( v40 < 0 )
    {
      std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v56);
      v41 = std::operator<<<std::char_traits<char>>(v57, "Failed at get_LocalFolder on IApplicationData");
      v42 = std::operator<<<std::char_traits<char>>(v41, " (HRESULT: 0x");
      v43 = std::ostream::operator<<(v42, std::hex);
      v44 = std::ostream::operator<<(v43, (unsigned int)v40);
      std::operator<<<std::char_traits<char>>(v44, ")");
      std::stringbuf::str(v58, v61);
      std::runtime_error::runtime_error((std::exception *)&pExceptionObject);
      throw (std::runtime_error *)&pExceptionObject;
    }
    v45 = Pal::WinRTPathInformation::getStorageFolderPath((__int64)v61, *a3);
    std::wstring::operator=(v54, v45);
    std::wstring::_Tidy_deallocate(v61);
    if ( (*(int (__fastcall **)(__int64, struct ABI::Windows::Storage::IStorageFolder **))(*(_QWORD *)v49 + 112LL))(
           v49,
           a5) >= 0 )
    {
      v46 = Pal::WinRTPathInformation::getStorageFolderPath((__int64)v61, *a5);
      std::wstring::operator=(a6, v46);
      std::wstring::_Tidy_deallocate(v61);
    }
    if ( (*(int (__fastcall **)(__int64, struct ABI::Windows::Storage::IStorageFolder **))(*(_QWORD *)v49 + 104LL))(
           v49,
           a7) >= 0 )
    {
      v47 = Pal::WinRTPathInformation::getStorageFolderPath((__int64)v61, *a7);
      std::wstring::operator=(v55, v47);
      std::wstring::_Tidy_deallocate(v61);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
}

```

## disassembly

```asm
0x18002b428  push    rbp
0x18002b42a  push    rbx
0x18002b42b  push    rsi
0x18002b42c  push    rdi
0x18002b42d  push    r12
0x18002b42f  push    r13
0x18002b431  push    r14
0x18002b433  push    r15
0x18002b435  lea     rbp, [rsp-0B8h]
0x18002b43d  sub     rsp, 1B8h
0x18002b444  mov     rax, cs:__security_cookie
0x18002b44b  xor     rax, rsp
0x18002b44e  mov     [rbp+0F0h+var_50], rax
0x18002b455  mov     [rsp+1F0h+var_1A8], r9
0x18002b45a  mov     r12, r8
0x18002b45d  mov     rax, rdx
0x18002b460  mov     [rsp+1F0h+var_1B0], rdx
0x18002b465  mov     r14, rcx
0x18002b468  mov     rdx, [rbp+0F0h+arg_38]
0x18002b46f  mov     [rsp+1F0h+var_1A0], rdx
0x18002b474  mov     r13, [rbp+0F0h+arg_28]
0x18002b47b  mov     r15, [rbp+0F0h+arg_20]
0x18002b482  mov     rsi, [rbp+0F0h+arg_30]
0x18002b489  xor     edi, edi
0x18002b48b  mov     [rcx], rdi
0x18002b48e  mov     [rax+10h], rdi
0x18002b492  mov     rcx, rax
0x18002b495  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002b49a  mov     [rax], di
0x18002b49d  mov     [r8], rdi
0x18002b4a0  mov     [r9+10h], rdi
0x18002b4a4  mov     rcx, r9
0x18002b4a7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002b4ac  mov     [rax], di
0x18002b4af  mov     [r15], rdi
0x18002b4b2  mov     [r13+10h], rdi
0x18002b4b6  mov     rcx, r13
0x18002b4b9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002b4be  mov     [rax], di
0x18002b4c1  mov     [rsi], rdi
0x18002b4c4  mov     [rdx+10h], rdi
0x18002b4c8  mov     rcx, rdx
0x18002b4cb  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002b4d0  mov     [rax], di
0x18002b4d3  mov     [rsp+1F0h+var_1C0], rdi
0x18002b4d8  mov     [rbp+0F0h+var_78], rdi
0x18002b4dc  lea     r9d, [rdi+20h]; unsigned int
0x18002b4e0  lea     r8d, [rdi+21h]; unsigned int
0x18002b4e4  lea     rdx, ?RuntimeClass_Windows_ApplicationModel_Package@@3QBGB; "Windows.ApplicationModel.Package"
0x18002b4eb  lea     rcx, [rbp+0F0h+pExceptionObject]; hstringHeader
0x18002b4ef  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002b4f4  mov     rbx, [rbp+0F0h+var_78]
0x18002b4f8  lea     rcx, [rsp+1F0h+var_1C0]
0x18002b4fd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002b502  lea     r8, [rsp+1F0h+var_1C0]
0x18002b507  lea     rdx, _GUID_4e534bdf_2960_4878_97a4_9624deb72f2d
0x18002b50e  mov     rcx, rbx
0x18002b511  call    cs:__imp_RoGetActivationFactory
0x18002b517  mov     ebx, eax
0x18002b519  test    eax, eax
0x18002b51b  jns     loc_18002B5A9
0x18002b521  lea     rcx, [rsp+1F0h+var_190]
0x18002b526  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x18002b52b  nop
0x18002b52c  lea     rdx, aFailedToRetrie_0; "Failed to retrieve the activation facto"...
0x18002b533  lea     rcx, [rsp+1F0h+var_180]
0x18002b538  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002b53d  mov     rcx, rax
0x18002b540  lea     rdx, aHresult0x_0; " (HRESULT: 0x"
0x18002b547  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002b54c  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x18002b553  mov     rcx, rax
0x18002b556  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::ostream::operator<<(std::ios_base & (*)(std::ios_base &))
0x18002b55c  mov     edx, ebx
0x18002b55e  mov     rcx, rax
0x18002b561  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z; std::ostream::operator<<(long)
0x18002b567  mov     rcx, rax
0x18002b56a  lea     rdx, asc_1800A4BE0; ")"
0x18002b571  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002b576  lea     rdx, [rbp+0F0h+var_70]
0x18002b57d  lea     rcx, [rsp+1F0h+var_178]
0x18002b582  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x18002b587  nop
0x18002b588  lea     rdx, [rbp+0F0h+var_70]
0x18002b58f  lea     rcx, [rbp+0F0h+pExceptionObject]; this
0x18002b593  call    ??0runtime_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::runtime_error::runtime_error(std::string const &)
0x18002b598  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18002b59f  lea     rcx, [rbp+0F0h+pExceptionObject]; pExceptionObject
0x18002b5a3  call    _CxxThrowException_0
0x18002b5a9  mov     [rsp+1F0h+var_1C8], rdi
0x18002b5ae  mov     rdi, [rsp+1F0h+var_1C0]
0x18002b5b3  mov     rax, [rdi]
0x18002b5b6  mov     rbx, [rax+30h]
0x18002b5ba  lea     rcx, [rsp+1F0h+var_1C8]
0x18002b5bf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002b5c4  lea     rdx, [rsp+1F0h+var_1C8]
0x18002b5c9  mov     rcx, rdi
0x18002b5cc  mov     rax, rbx
0x18002b5cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b5d4  test    eax, eax
0x18002b5d6  js      loc_18002B990
0x18002b5dc  mov     rcx, [rsp+1F0h+var_1C8]
0x18002b5e1  mov     rax, [rcx]
0x18002b5e4  mov     rdx, r14
0x18002b5e7  mov     rax, [rax+38h]
0x18002b5eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b5f0  mov     ebx, eax
0x18002b5f2  test    eax, eax
0x18002b5f4  jns     loc_18002B682
0x18002b5fa  lea     rcx, [rsp+1F0h+var_190]
0x18002b5ff  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x18002b604  nop
0x18002b605  lea     rdx, aFailedToGetIns; "Failed to get_InstalledLocation"
0x18002b60c  lea     rcx, [rsp+1F0h+var_180]
0x18002b611  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002b616  mov     rcx, rax
0x18002b619  lea     rdx, aHresult0x_0; " (HRESULT: 0x"
0x18002b620  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002b625  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x18002b62c  mov     rcx, rax
0x18002b62f  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::ostream::operator<<(std::ios_base & (*)(std::ios_base &))
0x18002b635  mov     edx, ebx
0x18002b637  mov     rcx, rax
0x18002b63a  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z; std::ostream::operator<<(long)
0x18002b640  mov     rcx, rax
0x18002b643  lea     rdx, asc_1800A4BE0; ")"
0x18002b64a  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002b64f  lea     rdx, [rbp+0F0h+var_70]
0x18002b656  lea     rcx, [rsp+1F0h+var_178]
0x18002b65b  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x18002b660  nop
0x18002b661  lea     rdx, [rbp+0F0h+var_70]
0x18002b668  lea     rcx, [rbp+0F0h+pExceptionObject]; this
0x18002b66c  call    ??0runtime_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::runtime_error::runtime_error(std::string const &)
0x18002b671  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18002b678  lea     rcx, [rbp+0F0h+pExceptionObject]; pExceptionObject
0x18002b67c  call    _CxxThrowException_0
0x18002b682  mov     rdx, [r14]
0x18002b685  lea     rcx, [rbp+0F0h+var_70]
0x18002b68c  call    ?getStorageFolderPath@WinRTPathInformation@Pal@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUIStorageFolder@Storage@Windows@ABI@@@Z; Pal::WinRTPathInformation::getStorageFolderPath(ABI::Windows::Storage::IStorageFolder *)
0x18002b691  mov     rdx, rax
0x18002b694  mov     rcx, [rsp+1F0h+var_1B0]
0x18002b699  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002b69e  lea     rcx, [rbp+0F0h+var_70]
0x18002b6a5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002b6aa  xor     r14d, r14d
0x18002b6ad  mov     [rsp+1F0h+var_1B8], r14
0x18002b6b2  mov     [rbp+0F0h+var_78], r14
0x18002b6b6  lea     r9d, [r14+1Fh]; unsigned int
0x18002b6ba  lea     r8d, [r14+20h]; unsigned int
0x18002b6be  lea     rdx, ?RuntimeClass_Windows_Storage_ApplicationData@@3QBGB; "Windows.Storage.ApplicationData"
0x18002b6c5  lea     rcx, [rbp+0F0h+pExceptionObject]; hstringHeader
0x18002b6c9  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002b6ce  lea     rdx, [rsp+1F0h+var_1B8]
0x18002b6d3  mov     rcx, [rbp+0F0h+var_78]
0x18002b6d7  call    ??$GetActivationFactory@V?$ComPtr@UIApplicationDataStatics@Storage@Windows@ABI@@@WRL@Microsoft@@@Foundation@Windows@ABI@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIApplicationDataStatics@Storage@Windows@ABI@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; ABI::Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<ABI::Windows::Storage::IApplicationDataStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ABI::Windows::Storage::IApplicationDataStatics>>)
0x18002b6dc  mov     ebx, eax
0x18002b6de  test    eax, eax
0x18002b6e0  jns     loc_18002B76E
0x18002b6e6  lea     rcx, [rsp+1F0h+var_190]
0x18002b6eb  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x18002b6f0  nop
0x18002b6f1  lea     rdx, aFailedToRetrie_1; "Failed to retrieve the activation facto"...
0x18002b6f8  lea     rcx, [rsp+1F0h+var_180]
0x18002b6fd  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002b702  mov     rcx, rax
0x18002b705  lea     rdx, aHresult0x_0; " (HRESULT: 0x"
0x18002b70c  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002b711  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x18002b718  mov     rcx, rax
0x18002b71b  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::ostream::operator<<(std::ios_base & (*)(std::ios_base &))
0x18002b721  mov     edx, ebx
0x18002b723  mov     rcx, rax
0x18002b726  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z; std::ostream::operator<<(long)
0x18002b72c  mov     rcx, rax
0x18002b72f  lea     rdx, asc_1800A4BE0; ")"
0x18002b736  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002b73b  lea     rdx, [rbp+0F0h+var_70]
0x18002b742  lea     rcx, [rsp+1F0h+var_178]
0x18002b747  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x18002b74c  nop
0x18002b74d  lea     rdx, [rbp+0F0h+var_70]
0x18002b754  lea     rcx, [rbp+0F0h+pExceptionObject]; this
0x18002b758  call    ??0runtime_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::runtime_error::runtime_error(std::string const &)
0x18002b75d  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18002b764  lea     rcx, [rbp+0F0h+pExceptionObject]; pExceptionObject
0x18002b768  call    _CxxThrowException_0
0x18002b76e  mov     [rsp+1F0h+var_1D0], r14
0x18002b773  mov     rdi, [rsp+1F0h+var_1B8]
0x18002b778  mov     rax, [rdi]
0x18002b77b  mov     rbx, [rax+30h]
0x18002b77f  lea     rcx, [rsp+1F0h+var_1D0]
0x18002b784  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002b789  lea     rdx, [rsp+1F0h+var_1D0]
0x18002b78e  mov     rcx, rdi
0x18002b791  mov     rax, rbx
0x18002b794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b799  mov     ebx, eax
0x18002b79b  test    eax, eax
0x18002b79d  jns     loc_18002B82B
0x18002b7a3  lea     rcx, [rsp+1F0h+var_190]
0x18002b7a8  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x18002b7ad  nop
0x18002b7ae  lea     rdx, aFailedToGetCur; "Failed to get_Current on IApplicationDa"...
0x18002b7b5  lea     rcx, [rsp+1F0h+var_180]
0x18002b7ba  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002b7bf  mov     rcx, rax
0x18002b7c2  lea     rdx, aHresult0x_0; " (HRESULT: 0x"
0x18002b7c9  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002b7ce  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x18002b7d5  mov     rcx, rax
0x18002b7d8  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::ostream::operator<<(std::ios_base & (*)(std::ios_base &))
0x18002b7de  mov     edx, ebx
0x18002b7e0  mov     rcx, rax
0x18002b7e3  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z; std::ostream::operator<<(long)
0x18002b7e9  mov     rcx, rax
0x18002b7ec  lea     rdx, asc_1800A4BE0; ")"
0x18002b7f3  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002b7f8  lea     rdx, [rbp+0F0h+var_70]
0x18002b7ff  lea     rcx, [rsp+1F0h+var_178]
0x18002b804  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x18002b809  nop
0x18002b80a  lea     rdx, [rbp+0F0h+var_70]
0x18002b811  lea     rcx, [rbp+0F0h+pExceptionObject]; this
0x18002b815  call    ??0runtime_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::runtime_error::runtime_error(std::string const &)
0x18002b81a  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18002b821  lea     rcx, [rbp+0F0h+pExceptionObject]; pExceptionObject
0x18002b825  call    _CxxThrowException_0
0x18002b82b  mov     rcx, [rsp+1F0h+var_1D0]
0x18002b830  mov     rax, [rcx]
0x18002b833  mov     rdx, r12
0x18002b836  mov     rax, [rax+60h]
0x18002b83a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b83f  mov     ebx, eax
0x18002b841  test    eax, eax
0x18002b843  jns     loc_18002B8D1
0x18002b849  lea     rcx, [rsp+1F0h+var_190]
0x18002b84e  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x18002b853  nop
0x18002b854  lea     rdx, aFailedAtGetLoc; "Failed at get_LocalFolder on IApplicati"...
0x18002b85b  lea     rcx, [rsp+1F0h+var_180]
0x18002b860  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002b865  mov     rcx, rax
0x18002b868  lea     rdx, aHresult0x_0; " (HRESULT: 0x"
0x18002b86f  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002b874  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x18002b87b  mov     rcx, rax
0x18002b87e  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::ostream::operator<<(std::ios_base & (*)(std::ios_base &))
0x18002b884  mov     edx, ebx
0x18002b886  mov     rcx, rax
0x18002b889  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z; std::ostream::operator<<(long)
0x18002b88f  mov     rcx, rax
0x18002b892  lea     rdx, asc_1800A4BE0; ")"
0x18002b899  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002b89e  lea     rdx, [rbp+0F0h+var_70]
0x18002b8a5  lea     rcx, [rsp+1F0h+var_178]
0x18002b8aa  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x18002b8af  nop
0x18002b8b0  lea     rdx, [rbp+0F0h+var_70]
0x18002b8b7  lea     rcx, [rbp+0F0h+pExceptionObject]; this
0x18002b8bb  call    ??0runtime_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::runtime_error::runtime_error(std::string const &)
0x18002b8c0  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18002b8c7  lea     rcx, [rbp+0F0h+pExceptionObject]; pExceptionObject
0x18002b8cb  call    _CxxThrowException_0
0x18002b8d1  mov     rdx, [r12]
0x18002b8d5  lea     rcx, [rbp+0F0h+var_70]
0x18002b8dc  call    ?getStorageFolderPath@WinRTPathInformation@Pal@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUIStorageFolder@Storage@Windows@ABI@@@Z; Pal::WinRTPathInformation::getStorageFolderPath(ABI::Windows::Storage::IStorageFolder *)
0x18002b8e1  mov     rdx, rax
0x18002b8e4  mov     rcx, [rsp+1F0h+var_1A8]
0x18002b8e9  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002b8ee  lea     rcx, [rbp+0F0h+var_70]
0x18002b8f5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002b8fa  mov     rcx, [rsp+1F0h+var_1D0]
0x18002b8ff  mov     rax, [rcx]
0x18002b902  mov     rdx, r15
0x18002b905  mov     rax, [rax+70h]
0x18002b909  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b90e  test    eax, eax
0x18002b910  js      short loc_18002B938
0x18002b912  mov     rdx, [r15]
0x18002b915  lea     rcx, [rbp+0F0h+var_70]
0x18002b91c  call    ?getStorageFolderPath@WinRTPathInformation@Pal@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUIStorageFolder@Storage@Windows@ABI@@@Z; Pal::WinRTPathInformation::getStorageFolderPath(ABI::Windows::Storage::IStorageFolder *)
0x18002b921  mov     rdx, rax
0x18002b924  mov     rcx, r13
0x18002b927  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002b92c  lea     rcx, [rbp+0F0h+var_70]
0x18002b933  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002b938  mov     rcx, [rsp+1F0h+var_1D0]
0x18002b93d  mov     rax, [rcx]
0x18002b940  mov     rdx, rsi
0x18002b943  mov     rax, [rax+68h]
0x18002b947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b94c  test    eax, eax
0x18002b94e  js      short loc_18002B979
0x18002b950  mov     rdx, [rsi]
0x18002b953  lea     rcx, [rbp+0F0h+var_70]
0x18002b95a  call    ?getStorageFolderPath@WinRTPathInformation@Pal@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUIStorageFolder@Storage@Windows@ABI@@@Z; Pal::WinRTPathInformation::getStorageFolderPath(ABI::Windows::Storage::IStorageFolder *)
0x18002b95f  mov     rdx, rax
0x18002b962  mov     rcx, [rsp+1F0h+var_1A0]
0x18002b967  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
  ... truncated ...
```
