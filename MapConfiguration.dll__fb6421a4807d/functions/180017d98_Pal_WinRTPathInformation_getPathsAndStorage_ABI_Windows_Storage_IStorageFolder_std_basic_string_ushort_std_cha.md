# Pal::WinRTPathInformation::getPathsAndStorage(ABI::Windows::Storage::IStorageFolder * *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,ABI::Windows::Storage::IStorageFolder * *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,ABI::Windows::Storage::IStorageFolder * *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,ABI::Windows::Storage::IStorageFolder * *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x180017d98`
- end: `0x180018360`
- name: `?getPathsAndStorage@WinRTPathInformation@Pal@@SAXPEAPEAUIStorageFolder@Storage@Windows@ABI@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@010101@Z`
- size: `1480`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180017ce0`

## callees

- `0x1800094a0`
- `0x18000a080`
- `0x18000b4b8`
- `0x18000c2f8`
- `0x18000c354`
- `0x18000cd80`
- `0x18000d04c`
- `0x18001006c`
- `0x180010b18`
- `0x180010b50`
- `0x180011ddc`
- `0x180012ca4`
- `0x180017d98`
- `0x180018548`
- `0x18001a7a8`
- `0x180043010`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x180017ec6`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x180017f9f`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18001808b`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x180018148`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x1800181ee`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x180017ec6`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x180017f9f`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18001808b`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x180018148`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x1800181ee`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x180017ed1`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x180017faa`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x180018096`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x180018153`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x1800181f9`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x180017ed1`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x180017faa`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x180018096`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x180018153`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x1800181f9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180017e81`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180017e81`

## string_xrefs

- `0x180017f75`: `Failed to get_InstalledLocation`

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
            (__int64)v57,
            (__int64)"Failed to retrieve the activation factory for Windows.ApplicationModel.Package");
    v16 = std::operator<<<std::char_traits<char>>(v15, (__int64)" (HRESULT: 0x");
    v17 = std::ostream::operator<<(v16, std::hex);
    v18 = std::ostream::operator<<(v17, (unsigned int)ActivationFactory);
    std::operator<<<std::char_traits<char>>(v18, (__int64)")");
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
      v23 = std::operator<<<std::char_traits<char>>((__int64)v57, (__int64)"Failed to get_InstalledLocation");
      v24 = std::operator<<<std::char_traits<char>>(v23, (__int64)" (HRESULT: 0x");
      v25 = std::ostream::operator<<(v24, std::hex);
      v26 = std::ostream::operator<<(v25, (unsigned int)v22);
      std::operator<<<std::char_traits<char>>(v26, (__int64)")");
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
            (__int64)&v52);
    if ( v28 < 0 )
    {
      std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v56);
      v29 = std::operator<<<std::char_traits<char>>(
              (__int64)v57,
              (__int64)"Failed to retrieve the activation factory for Windows.Storage.ApplicationData");
      v30 = std::operator<<<std::char_traits<char>>(v29, (__int64)" (HRESULT: 0x");
      v31 = std::ostream::operator<<(v30, std::hex);
      v32 = std::ostream::operator<<(v31, (unsigned int)v28);
      std::operator<<<std::char_traits<char>>(v32, (__int64)")");
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
      v36 = std::operator<<<std::char_traits<char>>(
              (__int64)v57,
              (__int64)"Failed to get_Current on IApplicationDataStatics");
      v37 = std::operator<<<std::char_traits<char>>(v36, (__int64)" (HRESULT: 0x");
      v38 = std::ostream::operator<<(v37, std::hex);
      v39 = std::ostream::operator<<(v38, (unsigned int)v35);
      std::operator<<<std::char_traits<char>>(v39, (__int64)")");
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
      v41 = std::operator<<<std::char_traits<char>>(
              (__int64)v57,
              (__int64)"Failed at get_LocalFolder on IApplicationData");
      v42 = std::operator<<<std::char_traits<char>>(v41, (__int64)" (HRESULT: 0x");
      v43 = std::ostream::operator<<(v42, std::hex);
      v44 = std::ostream::operator<<(v43, (unsigned int)v40);
      std::operator<<<std::char_traits<char>>(v44, (__int64)")");
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
0x180017d98  push    rbp
0x180017d9a  push    rbx
0x180017d9b  push    rsi
0x180017d9c  push    rdi
0x180017d9d  push    r12
0x180017d9f  push    r13
0x180017da1  push    r14
0x180017da3  push    r15
0x180017da5  lea     rbp, [rsp-0B8h]
0x180017dad  sub     rsp, 1B8h
0x180017db4  mov     rax, cs:__security_cookie
0x180017dbb  xor     rax, rsp
0x180017dbe  mov     [rbp+0F0h+var_50], rax
0x180017dc5  mov     [rsp+1F0h+var_1A8], r9
0x180017dca  mov     r12, r8
0x180017dcd  mov     rax, rdx
0x180017dd0  mov     [rsp+1F0h+var_1B0], rdx
0x180017dd5  mov     r14, rcx
0x180017dd8  mov     rdx, [rbp+0F0h+arg_38]
0x180017ddf  mov     [rsp+1F0h+var_1A0], rdx
0x180017de4  mov     r13, [rbp+0F0h+arg_28]
0x180017deb  mov     r15, [rbp+0F0h+arg_20]
0x180017df2  mov     rsi, [rbp+0F0h+arg_30]
0x180017df9  xor     edi, edi
0x180017dfb  mov     [rcx], rdi
0x180017dfe  mov     [rax+10h], rdi
0x180017e02  mov     rcx, rax
0x180017e05  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180017e0a  mov     [rax], di
0x180017e0d  mov     [r8], rdi
0x180017e10  mov     [r9+10h], rdi
0x180017e14  mov     rcx, r9
0x180017e17  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180017e1c  mov     [rax], di
0x180017e1f  mov     [r15], rdi
0x180017e22  mov     [r13+10h], rdi
0x180017e26  mov     rcx, r13
0x180017e29  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180017e2e  mov     [rax], di
0x180017e31  mov     [rsi], rdi
0x180017e34  mov     [rdx+10h], rdi
0x180017e38  mov     rcx, rdx
0x180017e3b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180017e40  mov     [rax], di
0x180017e43  mov     [rsp+1F0h+var_1C0], rdi
0x180017e48  mov     [rbp+0F0h+var_78], rdi
0x180017e4c  lea     r9d, [rdi+20h]; unsigned int
0x180017e50  lea     r8d, [rdi+21h]; unsigned int
0x180017e54  lea     rdx, ?RuntimeClass_Windows_ApplicationModel_Package@@3QBGB; "Windows.ApplicationModel.Package"
0x180017e5b  lea     rcx, [rbp+0F0h+pExceptionObject]; hstringHeader
0x180017e5f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180017e64  mov     rbx, [rbp+0F0h+var_78]
0x180017e68  lea     rcx, [rsp+1F0h+var_1C0]
0x180017e6d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017e72  lea     r8, [rsp+1F0h+var_1C0]
0x180017e77  lea     rdx, _GUID_4e534bdf_2960_4878_97a4_9624deb72f2d
0x180017e7e  mov     rcx, rbx
0x180017e81  call    cs:__imp_RoGetActivationFactory
0x180017e87  mov     ebx, eax
0x180017e89  test    eax, eax
0x180017e8b  jns     loc_180017F19
0x180017e91  lea     rcx, [rsp+1F0h+var_190]
0x180017e96  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x180017e9b  nop
0x180017e9c  lea     rdx, aFailedToRetrie_0; "Failed to retrieve the activation facto"...
0x180017ea3  lea     rcx, [rsp+1F0h+var_180]
0x180017ea8  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180017ead  mov     rcx, rax
0x180017eb0  lea     rdx, aHresult0x_0; " (HRESULT: 0x"
0x180017eb7  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180017ebc  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x180017ec3  mov     rcx, rax
0x180017ec6  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::ostream::operator<<(std::ios_base & (*)(std::ios_base &))
0x180017ecc  mov     edx, ebx
0x180017ece  mov     rcx, rax
0x180017ed1  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z; std::ostream::operator<<(long)
0x180017ed7  mov     rcx, rax
0x180017eda  lea     rdx, asc_180048470; ")"
0x180017ee1  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180017ee6  lea     rdx, [rbp+0F0h+var_70]
0x180017eed  lea     rcx, [rsp+1F0h+var_178]
0x180017ef2  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x180017ef7  nop
0x180017ef8  lea     rdx, [rbp+0F0h+var_70]
0x180017eff  lea     rcx, [rbp+0F0h+pExceptionObject]; this
0x180017f03  call    ??0runtime_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::runtime_error::runtime_error(std::string const &)
0x180017f08  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180017f0f  lea     rcx, [rbp+0F0h+pExceptionObject]; pExceptionObject
0x180017f13  call    _CxxThrowException_0
0x180017f19  mov     [rsp+1F0h+var_1C8], rdi
0x180017f1e  mov     rdi, [rsp+1F0h+var_1C0]
0x180017f23  mov     rax, [rdi]
0x180017f26  mov     rbx, [rax+30h]
0x180017f2a  lea     rcx, [rsp+1F0h+var_1C8]
0x180017f2f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017f34  lea     rdx, [rsp+1F0h+var_1C8]
0x180017f39  mov     rcx, rdi
0x180017f3c  mov     rax, rbx
0x180017f3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f44  test    eax, eax
0x180017f46  js      loc_180018300
0x180017f4c  mov     rcx, [rsp+1F0h+var_1C8]
0x180017f51  mov     rax, [rcx]
0x180017f54  mov     rdx, r14
0x180017f57  mov     rax, [rax+38h]
0x180017f5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f60  mov     ebx, eax
0x180017f62  test    eax, eax
0x180017f64  jns     loc_180017FF2
0x180017f6a  lea     rcx, [rsp+1F0h+var_190]
0x180017f6f  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x180017f74  nop
0x180017f75  lea     rdx, aFailedToGetIns; "Failed to get_InstalledLocation"
0x180017f7c  lea     rcx, [rsp+1F0h+var_180]
0x180017f81  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180017f86  mov     rcx, rax
0x180017f89  lea     rdx, aHresult0x_0; " (HRESULT: 0x"
0x180017f90  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180017f95  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x180017f9c  mov     rcx, rax
0x180017f9f  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::ostream::operator<<(std::ios_base & (*)(std::ios_base &))
0x180017fa5  mov     edx, ebx
0x180017fa7  mov     rcx, rax
0x180017faa  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z; std::ostream::operator<<(long)
0x180017fb0  mov     rcx, rax
0x180017fb3  lea     rdx, asc_180048470; ")"
0x180017fba  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180017fbf  lea     rdx, [rbp+0F0h+var_70]
0x180017fc6  lea     rcx, [rsp+1F0h+var_178]
0x180017fcb  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x180017fd0  nop
0x180017fd1  lea     rdx, [rbp+0F0h+var_70]
0x180017fd8  lea     rcx, [rbp+0F0h+pExceptionObject]; this
0x180017fdc  call    ??0runtime_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::runtime_error::runtime_error(std::string const &)
0x180017fe1  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180017fe8  lea     rcx, [rbp+0F0h+pExceptionObject]; pExceptionObject
0x180017fec  call    _CxxThrowException_0
0x180017ff2  mov     rdx, [r14]
0x180017ff5  lea     rcx, [rbp+0F0h+var_70]
0x180017ffc  call    ?getStorageFolderPath@WinRTPathInformation@Pal@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUIStorageFolder@Storage@Windows@ABI@@@Z; Pal::WinRTPathInformation::getStorageFolderPath(ABI::Windows::Storage::IStorageFolder *)
0x180018001  mov     rdx, rax
0x180018004  mov     rcx, [rsp+1F0h+var_1B0]
0x180018009  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001800e  lea     rcx, [rbp+0F0h+var_70]
0x180018015  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001801a  xor     r14d, r14d
0x18001801d  mov     [rsp+1F0h+var_1B8], r14
0x180018022  mov     [rbp+0F0h+var_78], r14
0x180018026  lea     r9d, [r14+1Fh]; unsigned int
0x18001802a  lea     r8d, [r14+20h]; unsigned int
0x18001802e  lea     rdx, ?RuntimeClass_Windows_Storage_ApplicationData@@3QBGB; "Windows.Storage.ApplicationData"
0x180018035  lea     rcx, [rbp+0F0h+pExceptionObject]; hstringHeader
0x180018039  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001803e  lea     rdx, [rsp+1F0h+var_1B8]
0x180018043  mov     rcx, [rbp+0F0h+var_78]
0x180018047  call    ??$GetActivationFactory@V?$ComPtr@UIApplicationDataStatics@Storage@Windows@ABI@@@WRL@Microsoft@@@Foundation@Windows@ABI@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIApplicationDataStatics@Storage@Windows@ABI@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; ABI::Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<ABI::Windows::Storage::IApplicationDataStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ABI::Windows::Storage::IApplicationDataStatics>>)
0x18001804c  mov     ebx, eax
0x18001804e  test    eax, eax
0x180018050  jns     loc_1800180DE
0x180018056  lea     rcx, [rsp+1F0h+var_190]
0x18001805b  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x180018060  nop
0x180018061  lea     rdx, aFailedToRetrie_1; "Failed to retrieve the activation facto"...
0x180018068  lea     rcx, [rsp+1F0h+var_180]
0x18001806d  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180018072  mov     rcx, rax
0x180018075  lea     rdx, aHresult0x_0; " (HRESULT: 0x"
0x18001807c  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180018081  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x180018088  mov     rcx, rax
0x18001808b  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::ostream::operator<<(std::ios_base & (*)(std::ios_base &))
0x180018091  mov     edx, ebx
0x180018093  mov     rcx, rax
0x180018096  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z; std::ostream::operator<<(long)
0x18001809c  mov     rcx, rax
0x18001809f  lea     rdx, asc_180048470; ")"
0x1800180a6  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800180ab  lea     rdx, [rbp+0F0h+var_70]
0x1800180b2  lea     rcx, [rsp+1F0h+var_178]
0x1800180b7  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x1800180bc  nop
0x1800180bd  lea     rdx, [rbp+0F0h+var_70]
0x1800180c4  lea     rcx, [rbp+0F0h+pExceptionObject]; this
0x1800180c8  call    ??0runtime_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::runtime_error::runtime_error(std::string const &)
0x1800180cd  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x1800180d4  lea     rcx, [rbp+0F0h+pExceptionObject]; pExceptionObject
0x1800180d8  call    _CxxThrowException_0
0x1800180de  mov     [rsp+1F0h+var_1D0], r14
0x1800180e3  mov     rdi, [rsp+1F0h+var_1B8]
0x1800180e8  mov     rax, [rdi]
0x1800180eb  mov     rbx, [rax+30h]
0x1800180ef  lea     rcx, [rsp+1F0h+var_1D0]
0x1800180f4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800180f9  lea     rdx, [rsp+1F0h+var_1D0]
0x1800180fe  mov     rcx, rdi
0x180018101  mov     rax, rbx
0x180018104  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018109  mov     ebx, eax
0x18001810b  test    eax, eax
0x18001810d  jns     loc_18001819B
0x180018113  lea     rcx, [rsp+1F0h+var_190]
0x180018118  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x18001811d  nop
0x18001811e  lea     rdx, aFailedToGetCur; "Failed to get_Current on IApplicationDa"...
0x180018125  lea     rcx, [rsp+1F0h+var_180]
0x18001812a  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18001812f  mov     rcx, rax
0x180018132  lea     rdx, aHresult0x_0; " (HRESULT: 0x"
0x180018139  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18001813e  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x180018145  mov     rcx, rax
0x180018148  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::ostream::operator<<(std::ios_base & (*)(std::ios_base &))
0x18001814e  mov     edx, ebx
0x180018150  mov     rcx, rax
0x180018153  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z; std::ostream::operator<<(long)
0x180018159  mov     rcx, rax
0x18001815c  lea     rdx, asc_180048470; ")"
0x180018163  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180018168  lea     rdx, [rbp+0F0h+var_70]
0x18001816f  lea     rcx, [rsp+1F0h+var_178]
0x180018174  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x180018179  nop
0x18001817a  lea     rdx, [rbp+0F0h+var_70]
0x180018181  lea     rcx, [rbp+0F0h+pExceptionObject]; this
0x180018185  call    ??0runtime_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::runtime_error::runtime_error(std::string const &)
0x18001818a  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180018191  lea     rcx, [rbp+0F0h+pExceptionObject]; pExceptionObject
0x180018195  call    _CxxThrowException_0
0x18001819b  mov     rcx, [rsp+1F0h+var_1D0]
0x1800181a0  mov     rax, [rcx]
0x1800181a3  mov     rdx, r12
0x1800181a6  mov     rax, [rax+60h]
0x1800181aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800181af  mov     ebx, eax
0x1800181b1  test    eax, eax
0x1800181b3  jns     loc_180018241
0x1800181b9  lea     rcx, [rsp+1F0h+var_190]
0x1800181be  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x1800181c3  nop
0x1800181c4  lea     rdx, aFailedAtGetLoc; "Failed at get_LocalFolder on IApplicati"...
0x1800181cb  lea     rcx, [rsp+1F0h+var_180]
0x1800181d0  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800181d5  mov     rcx, rax
0x1800181d8  lea     rdx, aHresult0x_0; " (HRESULT: 0x"
0x1800181df  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800181e4  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x1800181eb  mov     rcx, rax
0x1800181ee  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::ostream::operator<<(std::ios_base & (*)(std::ios_base &))
0x1800181f4  mov     edx, ebx
0x1800181f6  mov     rcx, rax
0x1800181f9  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z; std::ostream::operator<<(long)
0x1800181ff  mov     rcx, rax
0x180018202  lea     rdx, asc_180048470; ")"
0x180018209  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18001820e  lea     rdx, [rbp+0F0h+var_70]
0x180018215  lea     rcx, [rsp+1F0h+var_178]
0x18001821a  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x18001821f  nop
0x180018220  lea     rdx, [rbp+0F0h+var_70]
0x180018227  lea     rcx, [rbp+0F0h+pExceptionObject]; this
0x18001822b  call    ??0runtime_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::runtime_error::runtime_error(std::string const &)
0x180018230  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180018237  lea     rcx, [rbp+0F0h+pExceptionObject]; pExceptionObject
0x18001823b  call    _CxxThrowException_0
0x180018241  mov     rdx, [r12]
0x180018245  lea     rcx, [rbp+0F0h+var_70]
0x18001824c  call    ?getStorageFolderPath@WinRTPathInformation@Pal@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUIStorageFolder@Storage@Windows@ABI@@@Z; Pal::WinRTPathInformation::getStorageFolderPath(ABI::Windows::Storage::IStorageFolder *)
0x180018251  mov     rdx, rax
0x180018254  mov     rcx, [rsp+1F0h+var_1A8]
0x180018259  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001825e  lea     rcx, [rbp+0F0h+var_70]
0x180018265  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001826a  mov     rcx, [rsp+1F0h+var_1D0]
0x18001826f  mov     rax, [rcx]
0x180018272  mov     rdx, r15
0x180018275  mov     rax, [rax+70h]
0x180018279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001827e  test    eax, eax
0x180018280  js      short loc_1800182A8
0x180018282  mov     rdx, [r15]
0x180018285  lea     rcx, [rbp+0F0h+var_70]
0x18001828c  call    ?getStorageFolderPath@WinRTPathInformation@Pal@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUIStorageFolder@Storage@Windows@ABI@@@Z; Pal::WinRTPathInformation::getStorageFolderPath(ABI::Windows::Storage::IStorageFolder *)
0x180018291  mov     rdx, rax
0x180018294  mov     rcx, r13
0x180018297  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001829c  lea     rcx, [rbp+0F0h+var_70]
0x1800182a3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800182a8  mov     rcx, [rsp+1F0h+var_1D0]
0x1800182ad  mov     rax, [rcx]
0x1800182b0  mov     rdx, rsi
0x1800182b3  mov     rax, [rax+68h]
0x1800182b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800182bc  test    eax, eax
0x1800182be  js      short loc_1800182E9
0x1800182c0  mov     rdx, [rsi]
0x1800182c3  lea     rcx, [rbp+0F0h+var_70]
0x1800182ca  call    ?getStorageFolderPath@WinRTPathInformation@Pal@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUIStorageFolder@Storage@Windows@ABI@@@Z; Pal::WinRTPathInformation::getStorageFolderPath(ABI::Windows::Storage::IStorageFolder *)
0x1800182cf  mov     rdx, rax
0x1800182d2  mov     rcx, [rsp+1F0h+var_1A0]
0x1800182d7  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
  ... truncated ...
```
