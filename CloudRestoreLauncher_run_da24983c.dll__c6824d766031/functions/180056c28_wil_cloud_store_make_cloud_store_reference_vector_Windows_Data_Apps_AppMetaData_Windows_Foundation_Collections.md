# wil::cloud_store::make_cloud_store_reference_vector<Windows::Data::Apps::AppMetaData>(Windows::Foundation::Collections::IVectorView<Windows::Internal::Storage::Cloud::CloudStoreItemName *> *)

- ea: `0x180056c28`
- end: `0x180056fbf`
- name: `??$make_cloud_store_reference_vector@UAppMetaData@Apps@Data@Windows@@@cloud_store@wil@@CA?AV?$vector@U?$ItemReference@UAppMetaData@Apps@Data@Windows@@@Platform@Data@Windows@@V?$allocator@U?$ItemReference@UAppMetaData@Apps@Data@Windows@@@Platform@Data@Windows@@@std@@@std@@PEAU?$IVectorView@PEAVCloudStoreItemName@Cloud@Storage@Internal@Windows@@@Collections@Foundation@Windows@@@Z`
- size: `919`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180052f64`

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
- `0x180055394`
- `0x180056c28`
- `0x18005bce4`
- `0x18012d010`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x180056d90`
- `KERNEL32!CompareStringOrdinal` at `0x180056d90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180056d75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180056e7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180056ea1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180056d75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180056e7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180056ea1`

## pseudocode

```c
_QWORD *__fastcall wil::cloud_store::make_cloud_store_reference_vector<Windows::Data::Apps::AppMetaData>(
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
  wil::cloud_store::get_type_name_wide_string<Windows::Data::Apps::AppMetaData>(v41);
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
0x180056c28  mov     [rsp-8+arg_10], rbx
0x180056c2d  push    rbp
0x180056c2e  push    rsi
0x180056c2f  push    rdi
0x180056c30  push    r14
0x180056c32  push    r15
0x180056c34  lea     rbp, [rsp-37h]
0x180056c39  sub     rsp, 100h
0x180056c40  mov     rax, cs:__security_cookie
0x180056c47  xor     rax, rsp
0x180056c4a  mov     [rbp+57h+var_30], rax
0x180056c4e  mov     r14, rdx
0x180056c51  mov     rdi, rcx
0x180056c54  mov     [rbp+57h+var_A0], rcx
0x180056c58  xor     r15d, r15d
0x180056c5b  mov     [rbp+57h+var_C0], r15d
0x180056c5f  lea     rcx, [rbp+57h+var_50]
0x180056c63  call    ??$get_type_name_wide_string@UAppMetaData@Apps@Data@Windows@@@cloud_store@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; wil::cloud_store::get_type_name_wide_string<Windows::Data::Apps::AppMetaData>(void)
0x180056c68  nop
0x180056c69  mov     [rsp+120h+var_F0], r15d
0x180056c6e  mov     rax, [r14]
0x180056c71  lea     rdx, [rsp+120h+var_F0]
0x180056c76  mov     rcx, r14
0x180056c79  mov     rax, [rax+38h]
0x180056c7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056c82  mov     rcx, [rbp+5Fh]; this
0x180056c86  test    eax, eax
0x180056c88  jns     short loc_180056C9F
0x180056c8a  mov     r9d, eax; char *
0x180056c8d  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil/clo"...
0x180056c94  mov     edx, 55Eh; void *
0x180056c99  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180056c9f  mov     rcx, rdi
0x180056ca2  call    ??0?$vector@Vblob@bond@@V?$allocator@Vblob@bond@@@std@@@std@@QEAA@AEBV?$allocator@Vblob@bond@@@1@@Z; std::vector<bond::blob>::vector<bond::blob>(std::allocator<bond::blob> const &)
0x180056ca7  mov     [rbp+57h+var_C0], 1
0x180056cae  mov     edx, [rsp+120h+var_F0]
0x180056cb2  mov     [rbp+57h+string], rdx
0x180056cb6  mov     rax, [rdi+10h]
0x180056cba  sub     rax, [rdi]
0x180056cbd  sar     rax, 6
0x180056cc1  cmp     rdx, rax
0x180056cc4  jbe     short loc_180056CD3
0x180056cc6  lea     rdx, [rbp+57h+string]
0x180056cca  call    ??$_Reallocate@$0A@@?$vector@U?$ItemReference@UAppMetaData@Apps@Data@Windows@@@Platform@Data@Windows@@V?$allocator@U?$ItemReference@UAppMetaData@Apps@Data@Windows@@@Platform@Data@Windows@@@std@@@std@@AEAAXAEA_K@Z; std::vector<Windows::Data::Platform::ItemReference<Windows::Data::Apps::AppMetaData>>::_Reallocate<0>(unsigned __int64 &)
0x180056ccf  mov     edx, [rsp+120h+var_F0]
0x180056cd3  mov     esi, r15d
0x180056cd6  test    edx, edx
0x180056cd8  jz      loc_180056F27
0x180056cde  mov     [rbp+57h+var_D0], r15
0x180056ce2  mov     rax, [r14]
0x180056ce5  lea     rcx, [rbp+57h+var_D0]
0x180056ce9  mov     [rsp+120h+var_E8], rcx
0x180056cee  mov     [rsp+120h+var_E0], r15
0x180056cf3  mov     [rsp+120h+var_D8], 1
0x180056cf8  lea     r8, [rsp+120h+var_E0]
0x180056cfd  mov     edx, esi
0x180056cff  mov     rcx, r14
0x180056d02  mov     rax, [rax+30h]
0x180056d06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056d0b  mov     rcx, [rbp+5Fh]; this
0x180056d0f  test    eax, eax
0x180056d11  js      loc_180056FAA
0x180056d17  lea     rcx, [rsp+120h+var_E8]
0x180056d1c  call    ??1?$out_param_t@V?$com_ptr_t@UICloudStoreItemName@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreItemName,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreItemName,wil::err_exception_policy>>(void)
0x180056d21  mov     [rbp+57h+string], r15
0x180056d25  mov     rcx, [rbp+57h+var_D0]
0x180056d29  mov     rax, [rcx]
0x180056d2c  lea     rdx, [rbp+57h+string]
0x180056d30  mov     [rsp+120h+var_E8], rdx
0x180056d35  mov     [rsp+120h+var_E0], r15
0x180056d3a  mov     [rsp+120h+var_D8], 1
0x180056d3f  lea     rdx, [rsp+120h+var_E0]
0x180056d44  mov     rax, [rax+40h]
0x180056d48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056d4d  mov     rcx, [rbp+5Fh]; this
0x180056d51  test    eax, eax
0x180056d53  js      loc_180056F95
0x180056d59  lea     rcx, [rsp+120h+var_E8]
0x180056d5e  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(void)
0x180056d63  lea     rcx, [rbp+57h+var_50]
0x180056d67  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180056d6c  mov     rbx, rax
0x180056d6f  xor     edx, edx; length
0x180056d71  mov     rcx, [rbp+57h+string]; string
0x180056d75  call    cs:__imp_WindowsGetStringRawBuffer
0x180056d7b  mov     [rsp+120h+bIgnoreCase], 1; int
0x180056d83  or      r9d, 0FFFFFFFFh; cchCount2
0x180056d87  mov     r8, rbx; lpString2
0x180056d8a  or      edx, r9d; cchCount1
0x180056d8d  mov     rcx, rax; lpString1
0x180056d90  call    cs:__imp_CompareStringOrdinal
0x180056d96  cmp     eax, 2
0x180056d99  jnz     loc_180056F08
0x180056d9f  mov     [rbp+57h+var_A8], r15
0x180056da3  mov     rcx, [rbp+57h+var_D0]
0x180056da7  mov     rax, [rcx]
0x180056daa  lea     rdx, [rbp+57h+var_A8]
0x180056dae  mov     [rsp+120h+var_E8], rdx
0x180056db3  mov     [rsp+120h+var_E0], r15
0x180056db8  mov     [rsp+120h+var_D8], 1
0x180056dbd  lea     rdx, [rsp+120h+var_E0]
0x180056dc2  mov     rax, [rax+30h]
0x180056dc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056dcb  mov     rcx, [rbp+5Fh]; this
0x180056dcf  test    eax, eax
0x180056dd1  js      loc_180056F80
0x180056dd7  lea     rcx, [rsp+120h+var_E8]
0x180056ddc  call    ??1?$out_param_t@V?$com_ptr_t@UICloudStoreItemName@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreItemName,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreItemName,wil::err_exception_policy>>(void)
0x180056de1  mov     [rbp+57h+var_B0], r15
0x180056de5  mov     rcx, [rbp+57h+var_A8]
0x180056de9  mov     rax, [rcx]
0x180056dec  lea     rdx, [rbp+57h+var_B0]
0x180056df0  mov     [rsp+120h+var_E8], rdx
0x180056df5  mov     [rsp+120h+var_E0], r15
0x180056dfa  mov     [rsp+120h+var_D8], 1
0x180056dff  lea     rdx, [rsp+120h+var_E0]
0x180056e04  mov     rax, [rax+30h]
0x180056e08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056e0d  mov     rcx, [rbp+5Fh]; this
0x180056e11  test    eax, eax
0x180056e13  js      loc_180056F6B
0x180056e19  lea     rcx, [rsp+120h+var_E8]
0x180056e1e  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(void)
0x180056e23  mov     [rbp+57h+var_B8], r15
0x180056e27  mov     rcx, [rbp+57h+var_D0]
0x180056e2b  mov     rax, [rcx]
0x180056e2e  lea     rdx, [rbp+57h+var_B8]
0x180056e32  mov     [rsp+120h+var_E8], rdx
0x180056e37  mov     [rsp+120h+var_E0], r15
0x180056e3c  mov     [rsp+120h+var_D8], 1
0x180056e41  lea     rdx, [rsp+120h+var_E0]
0x180056e46  mov     rax, [rax+38h]
0x180056e4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056e4f  mov     rcx, [rbp+5Fh]; this
0x180056e53  test    eax, eax
0x180056e55  js      loc_180056F56
0x180056e5b  lea     rcx, [rsp+120h+var_E8]
0x180056e60  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(void)
0x180056e65  lea     rcx, [rbp+57h+var_90]
0x180056e69  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180056e6e  lea     rcx, [rbp+57h+var_70]
0x180056e72  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180056e77  nop
0x180056e78  xor     edx, edx; length
0x180056e7a  mov     rcx, [rbp+57h+var_B8]; string
0x180056e7e  call    cs:__imp_WindowsGetStringRawBuffer
0x180056e84  mov     rcx, rax
0x180056e87  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180056e8c  mov     r8, rax
0x180056e8f  mov     rdx, rcx
0x180056e92  lea     rcx, [rbp+57h+var_90]
0x180056e96  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180056e9b  xor     edx, edx; length
0x180056e9d  mov     rcx, [rbp+57h+var_B0]; string
0x180056ea1  call    cs:__imp_WindowsGetStringRawBuffer
0x180056ea7  mov     rcx, rax
0x180056eaa  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180056eaf  mov     r8, rax
0x180056eb2  mov     rdx, rcx
0x180056eb5  lea     rcx, [rbp+57h+var_70]
0x180056eb9  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180056ebe  mov     rdx, [rdi+8]
0x180056ec2  mov     rcx, rdi
0x180056ec5  cmp     rdx, [rdi+10h]
0x180056ec9  jz      short loc_180056ED6
0x180056ecb  lea     rdx, [rbp+57h+var_90]
0x180056ecf  call    ??$_Emplace_back_with_unused_capacity@U?$ItemReference@UAppMetaData@Apps@Data@Windows@@@Platform@Data@Windows@@@?$vector@U?$ItemReference@UAppMetaData@Apps@Data@Windows@@@Platform@Data@Windows@@V?$allocator@U?$ItemReference@UAppMetaData@Apps@Data@Windows@@@Platform@Data@Windows@@@std@@@std@@AEAAAEAU?$ItemReference@UAppMetaData@Apps@Data@Windows@@@Platform@Data@Windows@@$$QEAU2345@@Z; std::vector<Windows::Data::Platform::ItemReference<Windows::Data::Apps::AppMetaData>>::_Emplace_back_with_unused_capacity<Windows::Data::Platform::ItemReference<Windows::Data::Apps::AppMetaData>>(Windows::Data::Platform::ItemReference<Windows::Data::Apps::AppMetaData> &&)
0x180056ed4  jmp     short loc_180056EE0
0x180056ed6  lea     r8, [rbp+57h+var_90]
0x180056eda  call    ??$_Emplace_reallocate@U?$ItemReference@UAppMetaData@Apps@Data@Windows@@@Platform@Data@Windows@@@?$vector@U?$ItemReference@UAppMetaData@Apps@Data@Windows@@@Platform@Data@Windows@@V?$allocator@U?$ItemReference@UAppMetaData@Apps@Data@Windows@@@Platform@Data@Windows@@@std@@@std@@AEAAPEAU?$ItemReference@UAppMetaData@Apps@Data@Windows@@@Platform@Data@Windows@@QEAU2345@$$QEAU2345@@Z; std::vector<Windows::Data::Platform::ItemReference<Windows::Data::Apps::AppMetaData>>::_Emplace_reallocate<Windows::Data::Platform::ItemReference<Windows::Data::Apps::AppMetaData>>(Windows::Data::Platform::ItemReference<Windows::Data::Apps::AppMetaData> * const,Windows::Data::Platform::ItemReference<Windows::Data::Apps::AppMetaData> &&)
0x180056edf  nop
0x180056ee0  lea     rcx, [rbp+57h+var_90]
0x180056ee4  call    ??1?$ItemReference@UQuietHoursProfile@Notifications@Data@Windows@@@Platform@Data@Windows@@QEAA@XZ; Windows::Data::Platform::ItemReference<Windows::Data::Notifications::QuietHoursProfile>::~ItemReference<Windows::Data::Notifications::QuietHoursProfile>(void)
0x180056ee9  nop
0x180056eea  lea     rcx, [rbp+57h+var_B8]
0x180056eee  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180056ef3  nop
0x180056ef4  lea     rcx, [rbp+57h+var_B0]
0x180056ef8  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180056efd  nop
0x180056efe  lea     rcx, [rbp+57h+var_A8]
0x180056f02  call    ??1?$com_ptr_t@UICloudDataRestore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(void)
0x180056f07  nop
0x180056f08  lea     rcx, [rbp+57h+string]
0x180056f0c  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180056f11  nop
0x180056f12  lea     rcx, [rbp+57h+var_D0]
0x180056f16  call    ??1?$com_ptr_t@UICloudDataRestore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(void)
0x180056f1b  inc     esi
0x180056f1d  cmp     esi, [rsp+120h+var_F0]
0x180056f21  jb      loc_180056CDE
0x180056f27  lea     rcx, [rbp+57h+var_50]
0x180056f2b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180056f30  mov     rax, rdi
0x180056f33  mov     rcx, [rbp+57h+var_30]
0x180056f37  xor     rcx, rsp; StackCookie
0x180056f3a  call    __security_check_cookie
0x180056f3f  mov     rbx, [rsp+120h+arg_10]
0x180056f47  add     rsp, 100h
0x180056f4e  pop     r15
0x180056f50  pop     r14
0x180056f52  pop     rdi
0x180056f53  pop     rsi
0x180056f54  pop     rbp
0x180056f55  retn
0x180056f56  mov     r9d, eax; char *
0x180056f59  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil/clo"...
0x180056f60  mov     edx, 572h; void *
0x180056f65  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180056f6b  mov     r9d, eax; char *
0x180056f6e  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil/clo"...
0x180056f75  mov     edx, 56Fh; void *
0x180056f7a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180056f80  mov     r9d, eax; char *
0x180056f83  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil/clo"...
0x180056f8a  mov     edx, 56Ch; void *
0x180056f8f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180056f95  mov     r9d, eax; char *
0x180056f98  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil/clo"...
0x180056f9f  mov     edx, 568h; void *
0x180056fa4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180056faa  mov     r9d, eax; char *
0x180056fad  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil/clo"...
0x180056fb4  mov     edx, 565h; void *
0x180056fb9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
