# wil::cloud_store::make_cloud_store_reference_vector<Windows::Data::Apps::AppLevelTileInfo>(Windows::Foundation::Collections::IVectorView<Windows::Internal::Storage::Cloud::CloudStoreItemName *> *)

- ea: `0x180056888`
- end: `0x180056c1f`
- name: `??$make_cloud_store_reference_vector@UAppLevelTileInfo@Apps@Data@Windows@@@cloud_store@wil@@CA?AV?$vector@U?$ItemReference@UAppLevelTileInfo@Apps@Data@Windows@@@Platform@Data@Windows@@V?$allocator@U?$ItemReference@UAppLevelTileInfo@Apps@Data@Windows@@@Platform@Data@Windows@@@std@@@std@@PEAU?$IVectorView@PEAVCloudStoreItemName@Cloud@Storage@Internal@Windows@@@Collections@Foundation@Windows@@@Z`
- size: `919`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180052db8`

## callees

- `0x18000c6e0`
- `0x1800156b0`
- `0x1800157f0`
- `0x18001649c`
- `0x18001cf84`
- `0x18001cfa4`
- `0x18001d0a8`
- `0x18001d5fc`
- `0x180031774`
- `0x1800360b8`
- `0x1800363c4`
- `0x180036578`
- `0x180051874`
- `0x180051f50`
- `0x18005248c`
- `0x1800552bc`
- `0x180056888`
- `0x18005bce4`
- `0x18012d010`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x1800569f0`
- `KERNEL32!CompareStringOrdinal` at `0x1800569f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800569d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180056ade`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180056b01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800569d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180056ade`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180056b01`

## pseudocode

```c
_QWORD *__fastcall wil::cloud_store::make_cloud_store_reference_vector<Windows::Data::Apps::AppLevelTileInfo>(
        _QWORD *a1,
        __int64 *a2)
{
  int v4; // eax
  __int64 v5; // rcx
  unsigned int v6; // edx
  unsigned int v7; // esi
  __int64 v8; // rax
  int v9; // eax
  __int64 v10; // rax
  int v11; // eax
  const WCHAR *v12; // rbx
  const WCHAR *StringRawBuffer; // rax
  __int64 v14; // rax
  int v15; // eax
  __int64 v16; // rax
  int v17; // eax
  __int64 v18; // rax
  int v19; // eax
  PCWSTR v20; // rax
  __int64 v21; // rax
  __int64 v22; // rcx
  PCWSTR v23; // rax
  __int64 v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rdx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-A9h]
  unsigned int v29; // [rsp+30h] [rbp-99h] BYREF
  HSTRING *p_string; // [rsp+38h] [rbp-91h] BYREF
  __int64 v31; // [rsp+40h] [rbp-89h] BYREF
  char v32; // [rsp+48h] [rbp-81h]
  __int64 *v33; // [rsp+50h] [rbp-79h] BYREF
  HSTRING string; // [rsp+58h] [rbp-71h] BYREF
  int v35; // [rsp+60h] [rbp-69h]
  HSTRING v36; // [rsp+68h] [rbp-61h] BYREF
  HSTRING v37; // [rsp+70h] [rbp-59h] BYREF
  _QWORD v38[3]; // [rsp+78h] [rbp-51h] BYREF
  _BYTE v39[32]; // [rsp+90h] [rbp-39h] BYREF
  _BYTE v40[32]; // [rsp+B0h] [rbp-19h] BYREF
  _BYTE v41[32]; // [rsp+D0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  v38[1] = a1;
  v35 = 0;
  wil::cloud_store::get_type_name_wide_string<Windows::Data::Apps::AppLevelTileInfo>(v41);
  v29 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*a2 + 56))(a2, &v29);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x55E,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil/clouddata.h",
      (const char *)(unsigned int)v4,
      bIgnoreCase);
  std::vector<bond::blob>::vector<bond::blob>(a1);
  v35 = 1;
  v6 = v29;
  string = (HSTRING)v29;
  if ( v29 > (unsigned __int64)((__int64)(a1[2] - *a1) >> 6) )
  {
    std::vector<Windows::Data::Platform::ItemReference<Windows::Data::Apps::AppMetaData>>::_Reallocate<0>(v5, &string);
    v6 = v29;
  }
  v7 = 0;
  if ( v6 )
  {
    do
    {
      v33 = 0;
      v8 = *a2;
      p_string = (HSTRING *)&v33;
      v31 = 0;
      v32 = 1;
      v9 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v8 + 48))(a2, v7, &v31);
      if ( v9 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x565,
          (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil/clouddata.h",
          (const char *)(unsigned int)v9,
          bIgnoreCase);
      wil::details::out_param_t<wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreItemName,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreItemName,wil::err_exception_policy>>(&p_string);
      string = 0;
      v10 = *v33;
      p_string = &string;
      v31 = 0;
      v32 = 1;
      v11 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v10 + 64))(v33, &v31);
      if ( v11 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x568,
          (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil/clouddata.h",
          (const char *)(unsigned int)v11,
          bIgnoreCase);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>((__int64)&p_string);
      v12 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v41);
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      if ( CompareStringOrdinal(StringRawBuffer, -1, v12, -1, 1) == 2 )
      {
        v38[0] = 0;
        v14 = *v33;
        p_string = (HSTRING *)v38;
        v31 = 0;
        v32 = 1;
        v15 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v14 + 48))(v33, &v31);
        if ( v15 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x56C,
            (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil/clouddata.h",
            (const char *)(unsigned int)v15,
            bIgnoreCase);
        wil::details::out_param_t<wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreItemName,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreItemName,wil::err_exception_policy>>(&p_string);
        v37 = 0;
        v16 = *(_QWORD *)v38[0];
        p_string = &v37;
        v31 = 0;
        v32 = 1;
        v17 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(v16 + 48))(v38[0], &v31);
        if ( v17 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x56F,
            (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil/clouddata.h",
            (const char *)(unsigned int)v17,
            bIgnoreCase);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>((__int64)&p_string);
        v36 = 0;
        v18 = *v33;
        p_string = &v36;
        v31 = 0;
        v32 = 1;
        v19 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v18 + 56))(v33, &v31);
        if ( v19 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x572,
            (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil/clouddata.h",
            (const char *)(unsigned int)v19,
            bIgnoreCase);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>((__int64)&p_string);
        std::wstring::wstring(v39);
        std::wstring::wstring(v40);
        v20 = WindowsGetStringRawBuffer(v36, 0);
        v21 = std::_WChar_traits<unsigned short>::length(v20);
        std::wstring::_Assign<unsigned short>(v39, v22, v21);
        v23 = WindowsGetStringRawBuffer(v37, 0);
        v24 = std::_WChar_traits<unsigned short>::length(v23);
        std::wstring::_Assign<unsigned short>(v40, v25, v24);
        v26 = a1[1];
        if ( v26 == a1[2] )
          std::vector<Windows::Data::Platform::ItemReference<Windows::Data::Apps::AppMetaData>>::_Emplace_reallocate<Windows::Data::Platform::ItemReference<Windows::Data::Apps::AppMetaData>>(
            a1,
            v26,
            v39);
        else
          std::vector<Windows::Data::Platform::ItemReference<Windows::Data::Apps::AppMetaData>>::_Emplace_back_with_unused_capacity<Windows::Data::Platform::ItemReference<Windows::Data::Apps::AppMetaData>>(
            a1,
            v39);
        Windows::Data::Platform::ItemReference<Windows::Data::Notifications::QuietHoursProfile>::~ItemReference<Windows::Data::Notifications::QuietHoursProfile>(v39);
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v36);
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v37);
        wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(v38);
      }
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
      wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(&v33);
      ++v7;
    }
    while ( v7 < v29 );
  }
  std::wstring::_Tidy_deallocate(v41);
  return a1;
}

```

## disassembly

```asm
0x180056888  mov     [rsp-8+arg_10], rbx
0x18005688d  push    rbp
0x18005688e  push    rsi
0x18005688f  push    rdi
0x180056890  push    r14
0x180056892  push    r15
0x180056894  lea     rbp, [rsp-37h]
0x180056899  sub     rsp, 100h
0x1800568a0  mov     rax, cs:__security_cookie
0x1800568a7  xor     rax, rsp
0x1800568aa  mov     [rbp+57h+var_30], rax
0x1800568ae  mov     r14, rdx
0x1800568b1  mov     rdi, rcx
0x1800568b4  mov     [rbp+57h+var_A0], rcx
0x1800568b8  xor     r15d, r15d
0x1800568bb  mov     [rbp+57h+var_C0], r15d
0x1800568bf  lea     rcx, [rbp+57h+var_50]
0x1800568c3  call    ??$get_type_name_wide_string@UAppLevelTileInfo@Apps@Data@Windows@@@cloud_store@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; wil::cloud_store::get_type_name_wide_string<Windows::Data::Apps::AppLevelTileInfo>(void)
0x1800568c8  nop
0x1800568c9  mov     [rsp+120h+var_F0], r15d
0x1800568ce  mov     rax, [r14]
0x1800568d1  lea     rdx, [rsp+120h+var_F0]
0x1800568d6  mov     rcx, r14
0x1800568d9  mov     rax, [rax+38h]
0x1800568dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800568e2  mov     rcx, [rbp+5Fh]; this
0x1800568e6  test    eax, eax
0x1800568e8  jns     short loc_1800568FF
0x1800568ea  mov     r9d, eax; char *
0x1800568ed  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil/clo"...
0x1800568f4  mov     edx, 55Eh; void *
0x1800568f9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800568ff  mov     rcx, rdi
0x180056902  call    ??0?$vector@Vblob@bond@@V?$allocator@Vblob@bond@@@std@@@std@@QEAA@AEBV?$allocator@Vblob@bond@@@1@@Z; std::vector<bond::blob>::vector<bond::blob>(std::allocator<bond::blob> const &)
0x180056907  mov     [rbp+57h+var_C0], 1
0x18005690e  mov     edx, [rsp+120h+var_F0]
0x180056912  mov     [rbp+57h+string], rdx
0x180056916  mov     rax, [rdi+10h]
0x18005691a  sub     rax, [rdi]
0x18005691d  sar     rax, 6
0x180056921  cmp     rdx, rax
0x180056924  jbe     short loc_180056933
0x180056926  lea     rdx, [rbp+57h+string]
0x18005692a  call    ??$_Reallocate@$0A@@?$vector@U?$ItemReference@UAppMetaData@Apps@Data@Windows@@@Platform@Data@Windows@@V?$allocator@U?$ItemReference@UAppMetaData@Apps@Data@Windows@@@Platform@Data@Windows@@@std@@@std@@AEAAXAEA_K@Z; std::vector<Windows::Data::Platform::ItemReference<Windows::Data::Apps::AppMetaData>>::_Reallocate<0>(unsigned __int64 &)
0x18005692f  mov     edx, [rsp+120h+var_F0]
0x180056933  mov     esi, r15d
0x180056936  test    edx, edx
0x180056938  jz      loc_180056B87
0x18005693e  mov     [rbp+57h+var_D0], r15
0x180056942  mov     rax, [r14]
0x180056945  lea     rcx, [rbp+57h+var_D0]
0x180056949  mov     [rsp+120h+var_E8], rcx
0x18005694e  mov     [rsp+120h+var_E0], r15
0x180056953  mov     [rsp+120h+var_D8], 1
0x180056958  lea     r8, [rsp+120h+var_E0]
0x18005695d  mov     edx, esi
0x18005695f  mov     rcx, r14
0x180056962  mov     rax, [rax+30h]
0x180056966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005696b  mov     rcx, [rbp+5Fh]; this
0x18005696f  test    eax, eax
0x180056971  js      loc_180056C0A
0x180056977  lea     rcx, [rsp+120h+var_E8]
0x18005697c  call    ??1?$out_param_t@V?$com_ptr_t@UICloudStoreItemName@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreItemName,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreItemName,wil::err_exception_policy>>(void)
0x180056981  mov     [rbp+57h+string], r15
0x180056985  mov     rcx, [rbp+57h+var_D0]
0x180056989  mov     rax, [rcx]
0x18005698c  lea     rdx, [rbp+57h+string]
0x180056990  mov     [rsp+120h+var_E8], rdx
0x180056995  mov     [rsp+120h+var_E0], r15
0x18005699a  mov     [rsp+120h+var_D8], 1
0x18005699f  lea     rdx, [rsp+120h+var_E0]
0x1800569a4  mov     rax, [rax+40h]
0x1800569a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800569ad  mov     rcx, [rbp+5Fh]; this
0x1800569b1  test    eax, eax
0x1800569b3  js      loc_180056BF5
0x1800569b9  lea     rcx, [rsp+120h+var_E8]
0x1800569be  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(void)
0x1800569c3  lea     rcx, [rbp+57h+var_50]
0x1800569c7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800569cc  mov     rbx, rax
0x1800569cf  xor     edx, edx; length
0x1800569d1  mov     rcx, [rbp+57h+string]; string
0x1800569d5  call    cs:__imp_WindowsGetStringRawBuffer
0x1800569db  mov     [rsp+120h+bIgnoreCase], 1; int
0x1800569e3  or      r9d, 0FFFFFFFFh; cchCount2
0x1800569e7  mov     r8, rbx; lpString2
0x1800569ea  or      edx, r9d; cchCount1
0x1800569ed  mov     rcx, rax; lpString1
0x1800569f0  call    cs:__imp_CompareStringOrdinal
0x1800569f6  cmp     eax, 2
0x1800569f9  jnz     loc_180056B68
0x1800569ff  mov     [rbp+57h+var_A8], r15
0x180056a03  mov     rcx, [rbp+57h+var_D0]
0x180056a07  mov     rax, [rcx]
0x180056a0a  lea     rdx, [rbp+57h+var_A8]
0x180056a0e  mov     [rsp+120h+var_E8], rdx
0x180056a13  mov     [rsp+120h+var_E0], r15
0x180056a18  mov     [rsp+120h+var_D8], 1
0x180056a1d  lea     rdx, [rsp+120h+var_E0]
0x180056a22  mov     rax, [rax+30h]
0x180056a26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056a2b  mov     rcx, [rbp+5Fh]; this
0x180056a2f  test    eax, eax
0x180056a31  js      loc_180056BE0
0x180056a37  lea     rcx, [rsp+120h+var_E8]
0x180056a3c  call    ??1?$out_param_t@V?$com_ptr_t@UICloudStoreItemName@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreItemName,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreItemName,wil::err_exception_policy>>(void)
0x180056a41  mov     [rbp+57h+var_B0], r15
0x180056a45  mov     rcx, [rbp+57h+var_A8]
0x180056a49  mov     rax, [rcx]
0x180056a4c  lea     rdx, [rbp+57h+var_B0]
0x180056a50  mov     [rsp+120h+var_E8], rdx
0x180056a55  mov     [rsp+120h+var_E0], r15
0x180056a5a  mov     [rsp+120h+var_D8], 1
0x180056a5f  lea     rdx, [rsp+120h+var_E0]
0x180056a64  mov     rax, [rax+30h]
0x180056a68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056a6d  mov     rcx, [rbp+5Fh]; this
0x180056a71  test    eax, eax
0x180056a73  js      loc_180056BCB
0x180056a79  lea     rcx, [rsp+120h+var_E8]
0x180056a7e  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(void)
0x180056a83  mov     [rbp+57h+var_B8], r15
0x180056a87  mov     rcx, [rbp+57h+var_D0]
0x180056a8b  mov     rax, [rcx]
0x180056a8e  lea     rdx, [rbp+57h+var_B8]
0x180056a92  mov     [rsp+120h+var_E8], rdx
0x180056a97  mov     [rsp+120h+var_E0], r15
0x180056a9c  mov     [rsp+120h+var_D8], 1
0x180056aa1  lea     rdx, [rsp+120h+var_E0]
0x180056aa6  mov     rax, [rax+38h]
0x180056aaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056aaf  mov     rcx, [rbp+5Fh]; this
0x180056ab3  test    eax, eax
0x180056ab5  js      loc_180056BB6
0x180056abb  lea     rcx, [rsp+120h+var_E8]
0x180056ac0  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(void)
0x180056ac5  lea     rcx, [rbp+57h+var_90]
0x180056ac9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180056ace  lea     rcx, [rbp+57h+var_70]
0x180056ad2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180056ad7  nop
0x180056ad8  xor     edx, edx; length
0x180056ada  mov     rcx, [rbp+57h+var_B8]; string
0x180056ade  call    cs:__imp_WindowsGetStringRawBuffer
0x180056ae4  mov     rcx, rax
0x180056ae7  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180056aec  mov     r8, rax
0x180056aef  mov     rdx, rcx
0x180056af2  lea     rcx, [rbp+57h+var_90]
0x180056af6  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180056afb  xor     edx, edx; length
0x180056afd  mov     rcx, [rbp+57h+var_B0]; string
0x180056b01  call    cs:__imp_WindowsGetStringRawBuffer
0x180056b07  mov     rcx, rax
0x180056b0a  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180056b0f  mov     r8, rax
0x180056b12  mov     rdx, rcx
0x180056b15  lea     rcx, [rbp+57h+var_70]
0x180056b19  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180056b1e  mov     rdx, [rdi+8]
0x180056b22  mov     rcx, rdi
0x180056b25  cmp     rdx, [rdi+10h]
0x180056b29  jz      short loc_180056B36
0x180056b2b  lea     rdx, [rbp+57h+var_90]
0x180056b2f  call    ??$_Emplace_back_with_unused_capacity@U?$ItemReference@UAppMetaData@Apps@Data@Windows@@@Platform@Data@Windows@@@?$vector@U?$ItemReference@UAppMetaData@Apps@Data@Windows@@@Platform@Data@Windows@@V?$allocator@U?$ItemReference@UAppMetaData@Apps@Data@Windows@@@Platform@Data@Windows@@@std@@@std@@AEAAAEAU?$ItemReference@UAppMetaData@Apps@Data@Windows@@@Platform@Data@Windows@@$$QEAU2345@@Z; std::vector<Windows::Data::Platform::ItemReference<Windows::Data::Apps::AppMetaData>>::_Emplace_back_with_unused_capacity<Windows::Data::Platform::ItemReference<Windows::Data::Apps::AppMetaData>>(Windows::Data::Platform::ItemReference<Windows::Data::Apps::AppMetaData> &&)
0x180056b34  jmp     short loc_180056B40
0x180056b36  lea     r8, [rbp+57h+var_90]
0x180056b3a  call    ??$_Emplace_reallocate@U?$ItemReference@UAppMetaData@Apps@Data@Windows@@@Platform@Data@Windows@@@?$vector@U?$ItemReference@UAppMetaData@Apps@Data@Windows@@@Platform@Data@Windows@@V?$allocator@U?$ItemReference@UAppMetaData@Apps@Data@Windows@@@Platform@Data@Windows@@@std@@@std@@AEAAPEAU?$ItemReference@UAppMetaData@Apps@Data@Windows@@@Platform@Data@Windows@@QEAU2345@$$QEAU2345@@Z; std::vector<Windows::Data::Platform::ItemReference<Windows::Data::Apps::AppMetaData>>::_Emplace_reallocate<Windows::Data::Platform::ItemReference<Windows::Data::Apps::AppMetaData>>(Windows::Data::Platform::ItemReference<Windows::Data::Apps::AppMetaData> * const,Windows::Data::Platform::ItemReference<Windows::Data::Apps::AppMetaData> &&)
0x180056b3f  nop
0x180056b40  lea     rcx, [rbp+57h+var_90]
0x180056b44  call    ??1?$ItemReference@UQuietHoursProfile@Notifications@Data@Windows@@@Platform@Data@Windows@@QEAA@XZ; Windows::Data::Platform::ItemReference<Windows::Data::Notifications::QuietHoursProfile>::~ItemReference<Windows::Data::Notifications::QuietHoursProfile>(void)
0x180056b49  nop
0x180056b4a  lea     rcx, [rbp+57h+var_B8]
0x180056b4e  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180056b53  nop
0x180056b54  lea     rcx, [rbp+57h+var_B0]
0x180056b58  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180056b5d  nop
0x180056b5e  lea     rcx, [rbp+57h+var_A8]
0x180056b62  call    ??1?$com_ptr_t@UICloudDataRestore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(void)
0x180056b67  nop
0x180056b68  lea     rcx, [rbp+57h+string]
0x180056b6c  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180056b71  nop
0x180056b72  lea     rcx, [rbp+57h+var_D0]
0x180056b76  call    ??1?$com_ptr_t@UICloudDataRestore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(void)
0x180056b7b  inc     esi
0x180056b7d  cmp     esi, [rsp+120h+var_F0]
0x180056b81  jb      loc_18005693E
0x180056b87  lea     rcx, [rbp+57h+var_50]
0x180056b8b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180056b90  mov     rax, rdi
0x180056b93  mov     rcx, [rbp+57h+var_30]
0x180056b97  xor     rcx, rsp; StackCookie
0x180056b9a  call    __security_check_cookie
0x180056b9f  mov     rbx, [rsp+120h+arg_10]
0x180056ba7  add     rsp, 100h
0x180056bae  pop     r15
0x180056bb0  pop     r14
0x180056bb2  pop     rdi
0x180056bb3  pop     rsi
0x180056bb4  pop     rbp
0x180056bb5  retn
0x180056bb6  mov     r9d, eax; char *
0x180056bb9  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil/clo"...
0x180056bc0  mov     edx, 572h; void *
0x180056bc5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180056bcb  mov     r9d, eax; char *
0x180056bce  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil/clo"...
0x180056bd5  mov     edx, 56Fh; void *
0x180056bda  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180056be0  mov     r9d, eax; char *
0x180056be3  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil/clo"...
0x180056bea  mov     edx, 56Ch; void *
0x180056bef  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180056bf5  mov     r9d, eax; char *
0x180056bf8  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil/clo"...
0x180056bff  mov     edx, 568h; void *
0x180056c04  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180056c0a  mov     r9d, eax; char *
0x180056c0d  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil/clo"...
0x180056c14  mov     edx, 565h; void *
0x180056c19  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
