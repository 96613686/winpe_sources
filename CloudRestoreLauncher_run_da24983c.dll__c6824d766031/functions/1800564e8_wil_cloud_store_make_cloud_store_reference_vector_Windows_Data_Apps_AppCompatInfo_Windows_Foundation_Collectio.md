# wil::cloud_store::make_cloud_store_reference_vector<Windows::Data::Apps::AppCompatInfo>(Windows::Foundation::Collections::IVectorView<Windows::Internal::Storage::Cloud::CloudStoreItemName *> *)

- ea: `0x1800564e8`
- end: `0x18005687f`
- name: `??$make_cloud_store_reference_vector@UAppCompatInfo@Apps@Data@Windows@@@cloud_store@wil@@CA?AV?$vector@U?$ItemReference@UAppCompatInfo@Apps@Data@Windows@@@Platform@Data@Windows@@V?$allocator@U?$ItemReference@UAppCompatInfo@Apps@Data@Windows@@@Platform@Data@Windows@@@std@@@std@@PEAU?$IVectorView@PEAVCloudStoreItemName@Cloud@Storage@Internal@Windows@@@Collections@Foundation@Windows@@@Z`
- size: `919`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180052c0c`

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
- `0x1800551e4`
- `0x1800564e8`
- `0x18005bce4`
- `0x18012d010`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x180056650`
- `KERNEL32!CompareStringOrdinal` at `0x180056650`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180056635`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005673e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180056761`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180056635`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005673e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180056761`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
_QWORD *__fastcall wil::cloud_store::make_cloud_store_reference_vector<Windows::Data::Apps::AppCompatInfo>(
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
  wil::cloud_store::get_type_name_wide_string<Windows::Data::Apps::AppCompatInfo>(v41);
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
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(&p_string);
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
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(&p_string);
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
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(&p_string);
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
0x1800564e8  mov     [rsp-8+arg_10], rbx
0x1800564ed  push    rbp
0x1800564ee  push    rsi
0x1800564ef  push    rdi
0x1800564f0  push    r14
0x1800564f2  push    r15
0x1800564f4  lea     rbp, [rsp-37h]
0x1800564f9  sub     rsp, 100h
0x180056500  mov     rax, cs:__security_cookie
0x180056507  xor     rax, rsp
0x18005650a  mov     [rbp+57h+var_30], rax
0x18005650e  mov     r14, rdx
0x180056511  mov     rdi, rcx
0x180056514  mov     [rbp+57h+var_A0], rcx
0x180056518  xor     r15d, r15d
0x18005651b  mov     [rbp+57h+var_C0], r15d
0x18005651f  lea     rcx, [rbp+57h+var_50]
0x180056523  call    ??$get_type_name_wide_string@UAppCompatInfo@Apps@Data@Windows@@@cloud_store@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; wil::cloud_store::get_type_name_wide_string<Windows::Data::Apps::AppCompatInfo>(void)
0x180056528  nop
0x180056529  mov     [rsp+120h+var_F0], r15d
0x18005652e  mov     rax, [r14]
0x180056531  lea     rdx, [rsp+120h+var_F0]
0x180056536  mov     rcx, r14
0x180056539  mov     rax, [rax+38h]
0x18005653d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056542  mov     rcx, [rbp+5Fh]; this
0x180056546  test    eax, eax
0x180056548  jns     short loc_18005655F
0x18005654a  mov     r9d, eax; char *
0x18005654d  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil/clo"...
0x180056554  mov     edx, 55Eh; void *
0x180056559  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005655f  mov     rcx, rdi
0x180056562  call    ??0?$vector@Vblob@bond@@V?$allocator@Vblob@bond@@@std@@@std@@QEAA@AEBV?$allocator@Vblob@bond@@@1@@Z; std::vector<bond::blob>::vector<bond::blob>(std::allocator<bond::blob> const &)
0x180056567  mov     [rbp+57h+var_C0], 1
0x18005656e  mov     edx, [rsp+120h+var_F0]
0x180056572  mov     [rbp+57h+string], rdx
0x180056576  mov     rax, [rdi+10h]
0x18005657a  sub     rax, [rdi]
0x18005657d  sar     rax, 6
0x180056581  cmp     rdx, rax
0x180056584  jbe     short loc_180056593
0x180056586  lea     rdx, [rbp+57h+string]
0x18005658a  call    ??$_Reallocate@$0A@@?$vector@U?$ItemReference@UAppMetaData@Apps@Data@Windows@@@Platform@Data@Windows@@V?$allocator@U?$ItemReference@UAppMetaData@Apps@Data@Windows@@@Platform@Data@Windows@@@std@@@std@@AEAAXAEA_K@Z; std::vector<Windows::Data::Platform::ItemReference<Windows::Data::Apps::AppMetaData>>::_Reallocate<0>(unsigned __int64 &)
0x18005658f  mov     edx, [rsp+120h+var_F0]
0x180056593  mov     esi, r15d
0x180056596  test    edx, edx
0x180056598  jz      loc_1800567E7
0x18005659e  mov     [rbp+57h+var_D0], r15
0x1800565a2  mov     rax, [r14]
0x1800565a5  lea     rcx, [rbp+57h+var_D0]
0x1800565a9  mov     [rsp+120h+var_E8], rcx
0x1800565ae  mov     [rsp+120h+var_E0], r15
0x1800565b3  mov     [rsp+120h+var_D8], 1
0x1800565b8  lea     r8, [rsp+120h+var_E0]
0x1800565bd  mov     edx, esi
0x1800565bf  mov     rcx, r14
0x1800565c2  mov     rax, [rax+30h]
0x1800565c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800565cb  mov     rcx, [rbp+5Fh]; this
0x1800565cf  test    eax, eax
0x1800565d1  js      loc_18005686A
0x1800565d7  lea     rcx, [rsp+120h+var_E8]
0x1800565dc  call    ??1?$out_param_t@V?$com_ptr_t@UICloudStoreItemName@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreItemName,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreItemName,wil::err_exception_policy>>(void)
0x1800565e1  mov     [rbp+57h+string], r15
0x1800565e5  mov     rcx, [rbp+57h+var_D0]
0x1800565e9  mov     rax, [rcx]
0x1800565ec  lea     rdx, [rbp+57h+string]
0x1800565f0  mov     [rsp+120h+var_E8], rdx
0x1800565f5  mov     [rsp+120h+var_E0], r15
0x1800565fa  mov     [rsp+120h+var_D8], 1
0x1800565ff  lea     rdx, [rsp+120h+var_E0]
0x180056604  mov     rax, [rax+40h]
0x180056608  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005660d  mov     rcx, [rbp+5Fh]; this
0x180056611  test    eax, eax
0x180056613  js      loc_180056855
0x180056619  lea     rcx, [rsp+120h+var_E8]
0x18005661e  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(void)
0x180056623  lea     rcx, [rbp+57h+var_50]
0x180056627  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005662c  mov     rbx, rax
0x18005662f  xor     edx, edx; length
0x180056631  mov     rcx, [rbp+57h+string]; string
0x180056635  call    cs:__imp_WindowsGetStringRawBuffer
0x18005663b  mov     [rsp+120h+bIgnoreCase], 1; int
0x180056643  or      r9d, 0FFFFFFFFh; cchCount2
0x180056647  mov     r8, rbx; lpString2
0x18005664a  or      edx, r9d; cchCount1
0x18005664d  mov     rcx, rax; lpString1
0x180056650  call    cs:__imp_CompareStringOrdinal
0x180056656  cmp     eax, 2
0x180056659  jnz     loc_1800567C8
0x18005665f  mov     [rbp+57h+var_A8], r15
0x180056663  mov     rcx, [rbp+57h+var_D0]
0x180056667  mov     rax, [rcx]
0x18005666a  lea     rdx, [rbp+57h+var_A8]
0x18005666e  mov     [rsp+120h+var_E8], rdx
0x180056673  mov     [rsp+120h+var_E0], r15
0x180056678  mov     [rsp+120h+var_D8], 1
0x18005667d  lea     rdx, [rsp+120h+var_E0]
0x180056682  mov     rax, [rax+30h]
0x180056686  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005668b  mov     rcx, [rbp+5Fh]; this
0x18005668f  test    eax, eax
0x180056691  js      loc_180056840
0x180056697  lea     rcx, [rsp+120h+var_E8]
0x18005669c  call    ??1?$out_param_t@V?$com_ptr_t@UICloudStoreItemName@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreItemName,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreItemName,wil::err_exception_policy>>(void)
0x1800566a1  mov     [rbp+57h+var_B0], r15
0x1800566a5  mov     rcx, [rbp+57h+var_A8]
0x1800566a9  mov     rax, [rcx]
0x1800566ac  lea     rdx, [rbp+57h+var_B0]
0x1800566b0  mov     [rsp+120h+var_E8], rdx
0x1800566b5  mov     [rsp+120h+var_E0], r15
0x1800566ba  mov     [rsp+120h+var_D8], 1
0x1800566bf  lea     rdx, [rsp+120h+var_E0]
0x1800566c4  mov     rax, [rax+30h]
0x1800566c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800566cd  mov     rcx, [rbp+5Fh]; this
0x1800566d1  test    eax, eax
0x1800566d3  js      loc_18005682B
0x1800566d9  lea     rcx, [rsp+120h+var_E8]
0x1800566de  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(void)
0x1800566e3  mov     [rbp+57h+var_B8], r15
0x1800566e7  mov     rcx, [rbp+57h+var_D0]
0x1800566eb  mov     rax, [rcx]
0x1800566ee  lea     rdx, [rbp+57h+var_B8]
0x1800566f2  mov     [rsp+120h+var_E8], rdx
0x1800566f7  mov     [rsp+120h+var_E0], r15
0x1800566fc  mov     [rsp+120h+var_D8], 1
0x180056701  lea     rdx, [rsp+120h+var_E0]
0x180056706  mov     rax, [rax+38h]
0x18005670a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005670f  mov     rcx, [rbp+5Fh]; this
0x180056713  test    eax, eax
0x180056715  js      loc_180056816
0x18005671b  lea     rcx, [rsp+120h+var_E8]
0x180056720  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(void)
0x180056725  lea     rcx, [rbp+57h+var_90]
0x180056729  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18005672e  lea     rcx, [rbp+57h+var_70]
0x180056732  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180056737  nop
0x180056738  xor     edx, edx; length
0x18005673a  mov     rcx, [rbp+57h+var_B8]; string
0x18005673e  call    cs:__imp_WindowsGetStringRawBuffer
0x180056744  mov     rcx, rax
0x180056747  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18005674c  mov     r8, rax
0x18005674f  mov     rdx, rcx
0x180056752  lea     rcx, [rbp+57h+var_90]
0x180056756  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18005675b  xor     edx, edx; length
0x18005675d  mov     rcx, [rbp+57h+var_B0]; string
0x180056761  call    cs:__imp_WindowsGetStringRawBuffer
0x180056767  mov     rcx, rax
0x18005676a  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18005676f  mov     r8, rax
0x180056772  mov     rdx, rcx
0x180056775  lea     rcx, [rbp+57h+var_70]
0x180056779  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18005677e  mov     rdx, [rdi+8]
0x180056782  mov     rcx, rdi
0x180056785  cmp     rdx, [rdi+10h]
0x180056789  jz      short loc_180056796
0x18005678b  lea     rdx, [rbp+57h+var_90]
0x18005678f  call    ??$_Emplace_back_with_unused_capacity@U?$ItemReference@UAppMetaData@Apps@Data@Windows@@@Platform@Data@Windows@@@?$vector@U?$ItemReference@UAppMetaData@Apps@Data@Windows@@@Platform@Data@Windows@@V?$allocator@U?$ItemReference@UAppMetaData@Apps@Data@Windows@@@Platform@Data@Windows@@@std@@@std@@AEAAAEAU?$ItemReference@UAppMetaData@Apps@Data@Windows@@@Platform@Data@Windows@@$$QEAU2345@@Z; std::vector<Windows::Data::Platform::ItemReference<Windows::Data::Apps::AppMetaData>>::_Emplace_back_with_unused_capacity<Windows::Data::Platform::ItemReference<Windows::Data::Apps::AppMetaData>>(Windows::Data::Platform::ItemReference<Windows::Data::Apps::AppMetaData> &&)
0x180056794  jmp     short loc_1800567A0
0x180056796  lea     r8, [rbp+57h+var_90]
0x18005679a  call    ??$_Emplace_reallocate@U?$ItemReference@UAppMetaData@Apps@Data@Windows@@@Platform@Data@Windows@@@?$vector@U?$ItemReference@UAppMetaData@Apps@Data@Windows@@@Platform@Data@Windows@@V?$allocator@U?$ItemReference@UAppMetaData@Apps@Data@Windows@@@Platform@Data@Windows@@@std@@@std@@AEAAPEAU?$ItemReference@UAppMetaData@Apps@Data@Windows@@@Platform@Data@Windows@@QEAU2345@$$QEAU2345@@Z; std::vector<Windows::Data::Platform::ItemReference<Windows::Data::Apps::AppMetaData>>::_Emplace_reallocate<Windows::Data::Platform::ItemReference<Windows::Data::Apps::AppMetaData>>(Windows::Data::Platform::ItemReference<Windows::Data::Apps::AppMetaData> * const,Windows::Data::Platform::ItemReference<Windows::Data::Apps::AppMetaData> &&)
0x18005679f  nop
0x1800567a0  lea     rcx, [rbp+57h+var_90]
0x1800567a4  call    ??1?$ItemReference@UQuietHoursProfile@Notifications@Data@Windows@@@Platform@Data@Windows@@QEAA@XZ; Windows::Data::Platform::ItemReference<Windows::Data::Notifications::QuietHoursProfile>::~ItemReference<Windows::Data::Notifications::QuietHoursProfile>(void)
0x1800567a9  nop
0x1800567aa  lea     rcx, [rbp+57h+var_B8]
0x1800567ae  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x1800567b3  nop
0x1800567b4  lea     rcx, [rbp+57h+var_B0]
0x1800567b8  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x1800567bd  nop
0x1800567be  lea     rcx, [rbp+57h+var_A8]
0x1800567c2  call    ??1?$com_ptr_t@UICloudDataRestore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(void)
0x1800567c7  nop
0x1800567c8  lea     rcx, [rbp+57h+string]
0x1800567cc  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x1800567d1  nop
0x1800567d2  lea     rcx, [rbp+57h+var_D0]
0x1800567d6  call    ??1?$com_ptr_t@UICloudDataRestore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(void)
0x1800567db  inc     esi
0x1800567dd  cmp     esi, [rsp+120h+var_F0]
0x1800567e1  jb      loc_18005659E
0x1800567e7  lea     rcx, [rbp+57h+var_50]
0x1800567eb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800567f0  mov     rax, rdi
0x1800567f3  mov     rcx, [rbp+57h+var_30]
0x1800567f7  xor     rcx, rsp; StackCookie
0x1800567fa  call    __security_check_cookie
0x1800567ff  mov     rbx, [rsp+120h+arg_10]
0x180056807  add     rsp, 100h
0x18005680e  pop     r15
0x180056810  pop     r14
0x180056812  pop     rdi
0x180056813  pop     rsi
0x180056814  pop     rbp
0x180056815  retn
0x180056816  mov     r9d, eax; char *
0x180056819  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil/clo"...
0x180056820  mov     edx, 572h; void *
0x180056825  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005682b  mov     r9d, eax; char *
0x18005682e  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil/clo"...
0x180056835  mov     edx, 56Fh; void *
0x18005683a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180056840  mov     r9d, eax; char *
0x180056843  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil/clo"...
0x18005684a  mov     edx, 56Ch; void *
0x18005684f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180056855  mov     r9d, eax; char *
0x180056858  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil/clo"...
0x18005685f  mov     edx, 568h; void *
0x180056864  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005686a  mov     r9d, eax; char *
0x18005686d  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil/clo"...
0x180056874  mov     edx, 565h; void *
0x180056879  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
