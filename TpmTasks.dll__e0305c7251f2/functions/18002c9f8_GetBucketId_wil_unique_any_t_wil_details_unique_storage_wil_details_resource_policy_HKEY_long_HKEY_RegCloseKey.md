# GetBucketId(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18002c9f8`
- end: `0x18002cfa6`
- name: `?GetBucketId@@YAJAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@@nlohmann@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@2@Z`
- size: `1454`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18002c020`

## callees

- `0x1800078b0`
- `0x180009d98`
- `0x18000bc54`
- `0x18000bcc4`
- `0x18000cbd4`
- `0x18000cd34`
- `0x18000cec8`
- `0x18000d524`
- `0x18000e410`
- `0x18000eb54`
- `0x18000eb88`
- `0x180023634`
- `0x18002386c`
- `0x1800248b4`
- `0x180029cfc`
- `0x18002b300`
- `0x18002b848`
- `0x18002c9f8`
- `0x18002dd34`
- `0x18002fa88`
- `0x18003084c`
- `0x180033830`
- `0x18003c0b8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_tolower` at `0x18002cd9e`
- `api-ms-win-crt-private-l1-1-0!_o_tolower` at `0x18002cd9e`

## string_xrefs

- `0x18002cc3b`: `Registry %ls not found, will use empty string for this attribute`
- `0x18002cce6`: `Failed to read %ls registry hr: %x`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall GetBucketId(HKEY *a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rax
  const wchar_t *v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // r8
  const WCHAR *v17; // rdi
  HKEY v18; // rbx
  __int64 v19; // rdx
  int v20; // ebx
  __int64 v21; // rdx
  const char *v22; // r9
  __int64 v23; // rdx
  __int64 result; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  _WORD *v27; // rbx
  _WORD *j; // rdi
  __int64 v29; // rdx
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // r8
  unsigned __int64 i; // r15
  int SHA256Hash; // eax
  unsigned int v35; // ebx
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  wil::reg::reg_view_details *v41; // [rsp+20h] [rbp-158h]
  __int64 v42; // [rsp+30h] [rbp-148h] BYREF
  void *v43; // [rsp+38h] [rbp-140h] BYREF
  __int64 v44; // [rsp+40h] [rbp-138h]
  HKEY v45; // [rsp+48h] [rbp-130h] BYREF
  const std::exception *v46; // [rsp+50h] [rbp-128h] BYREF
  __int128 v47; // [rsp+58h] [rbp-120h] BYREF
  __int64 v48; // [rsp+68h] [rbp-110h]
  __int64 v49; // [rsp+70h] [rbp-108h]
  _BYTE v50[16]; // [rsp+78h] [rbp-100h] BYREF
  __int64 v51; // [rsp+88h] [rbp-F0h]
  _BYTE v52[32]; // [rsp+98h] [rbp-E0h] BYREF
  _BYTE v53[16]; // [rsp+B8h] [rbp-C0h] BYREF
  __int64 v54; // [rsp+C8h] [rbp-B0h]
  _BYTE v55[16]; // [rsp+D8h] [rbp-A0h] BYREF
  __int64 v56; // [rsp+E8h] [rbp-90h]
  _BYTE v57[32]; // [rsp+F8h] [rbp-80h] BYREF
  _BYTE v58[32]; // [rsp+118h] [rbp-60h] BYREF

  try
  {
    v44 = a2;
    std::wstring::wstring((__int64)v52, (__int64)&sourceString);
    for ( i = 0; ; ++i )
    {
      if ( *(_BYTE *)a2 )
      {
        if ( *(_BYTE *)a2 == 1 )
          v8 = *(_QWORD *)(*(_QWORD *)(a2 + 8) + 8LL);
        else
          v8 = *(_BYTE *)a2 == 2 ? (__int64)(*(_QWORD *)(*(_QWORD *)(a2 + 8) + 8LL) - **(_QWORD **)(a2 + 8)) >> 4 : 1LL;
      }
      else
      {
        v8 = 0;
      }
      if ( i >= v8 )
        break;
      v47 = 0;
      v48 = 0;
      v49 = 7;
      LOWORD(v47) = 0;
      v9 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::operator[](
             a2,
             i);
      nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::get<std::string,0>(
        v9,
        (__int64)v57);
      Utf8ToWide(v50, v57);
      v10 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v50);
      if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v10, v51, L"OEMName_Uncleaned", 17) )
      {
        v11 = L"OEMManufacturerName";
LABEL_16:
        std::wstring::_Assign<unsigned short>(&v47, v11);
        goto LABEL_18;
      }
      v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v50);
      if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v12, v51, L"OEMSubModel", 11) )
      {
        v11 = L"OEMModelSKU";
        goto LABEL_16;
      }
      v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v50);
      if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v13, v51, L"OEMModel", 8) )
      {
        v11 = L"OEMModelNumber";
        goto LABEL_16;
      }
      std::wstring::operator=(&v47, v50);
LABEL_18:
      v14 = std::operator+<unsigned short>(v58, &v47, L":");
      v15 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v14);
      std::wstring::_Append<unsigned short>(a4, v15, *(_QWORD *)(v16 + 16));
      std::wstring::_Tidy_deallocate(v58);
      v42 = 0;
      v17 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v47);
      v18 = *a1;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        (void **)&v42,
        0);
      v45 = v18;
      LODWORD(v41) = 268435462;
      v20 = wil::reg::reg_view_details::reg_view_t<wil::err_returncode_policy>::get_value_with_type<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::err_returncode_policy>(
              &v45,
              v19,
              v17,
              (PVOID *)&v42,
              v41);
      if ( v20 == -2147024894 )
      {
        v21 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v47);
        SBServicingLogMessage((wchar_t *)L"Registry %ls not found, will use empty string for this attribute", v21);
        wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &v43,
          (char *)&sourceString,
          0xFFFFFFFFFFFFFFFFuLL,
          v22);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
          &v42,
          &v43);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v43);
        v23 = v42;
        if ( !v42 )
        {
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v42);
          std::wstring::_Tidy_deallocate(v50);
          std::string::_Tidy_deallocate(v57);
          std::wstring::_Tidy_deallocate(&v47);
          std::wstring::_Tidy_deallocate(v52);
          nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::~basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>(a2);
          return 2147942414LL;
        }
      }
      else
      {
        if ( v20 < 0 )
        {
          v25 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v47);
          SBServicingLogMessage((wchar_t *)L"Failed to read %ls registry hr: %x", v25, (unsigned int)v20);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v42);
          std::wstring::_Tidy_deallocate(v50);
          std::string::_Tidy_deallocate(v57);
          std::wstring::_Tidy_deallocate(&v47);
          std::wstring::_Tidy_deallocate(v52);
          nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::~basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>(a2);
          return (unsigned int)v20;
        }
        v23 = v42;
      }
      std::wstring::wstring((__int64)v55, v23);
      v26 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v47);
      if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v26, v48, L"OSArchitecture", 14) )
      {
        v27 = (_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v55);
        for ( j = &v27[v56]; v27 != j; ++v27 )
          *v27 = _o_tolower((unsigned __int16)*v27);
      }
      trim(v53, v55);
      v29 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v53);
      std::wstring::_Append<unsigned short>(v52, v29, v54);
      v30 = std::operator+<unsigned short>(v58, v53, L";");
      v31 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v30);
      std::wstring::_Append<unsigned short>(a4, v31, *(_QWORD *)(v32 + 16));
      std::wstring::_Tidy_deallocate(v58);
      std::wstring::_Tidy_deallocate(v53);
      std::wstring::_Tidy_deallocate(v55);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v42);
      std::wstring::_Tidy_deallocate(v50);
      std::string::_Tidy_deallocate(v57);
      std::wstring::_Tidy_deallocate(&v47);
    }
    SHA256Hash = GetSHA256Hash((__int64)v52, a3);
    v35 = SHA256Hash;
    if ( SHA256Hash >= 0 )
    {
      v36 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3);
      if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                              v36,
                              *(_QWORD *)(a3 + 16),
                              L"e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855",
                              64) )
        std::wstring::_Assign<unsigned short>(a3, L"BA_EMPTY");
      v37 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a4);
      SBServicingLogMessage((wchar_t *)L"BucketAttribValues: %ls", v37);
      v38 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v52);
      SBServicingLogMessage((wchar_t *)L"BucketIdStr: %ls", v38);
      v39 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3);
      SBServicingLogMessage((wchar_t *)L"BucketId: %ls", v39);
      std::wstring::_Tidy_deallocate(v52);
      nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::~basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>(a2);
      result = 0;
    }
    else
    {
      SBServicingLogMessage((wchar_t *)L"Failed to get SHA256 hash: %x", (unsigned int)SHA256Hash);
      std::wstring::_Tidy_deallocate(v52);
      nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::~basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>(a2);
      result = v35;
    }
  }
  catch ( std::bad_alloc )
  {
    SBServicingLogMessage((wchar_t *)L"GetBucketId failed with out of memory");
    nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::~basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>(v44);
    return 2147942414LL;
  }
  catch ( const std::exception *v46 )
  {
    v40 = (*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v46 + 8LL))(v46);
    SBServicingLogMessage((wchar_t *)L"GetBucketId failed with Error: %hs", v40);
    nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::~basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>(v44);
    return 2147500037LL;
  }
  return result;
}

```

## disassembly

```asm
0x18002c9f8  push    rbx
0x18002c9fa  push    rsi
0x18002c9fb  push    rdi
0x18002c9fc  push    r12
0x18002c9fe  push    r13
0x18002ca00  push    r14
0x18002ca02  push    r15
0x18002ca04  sub     rsp, 140h
0x18002ca0b  mov     rax, cs:__security_cookie
0x18002ca12  xor     rax, rsp
0x18002ca15  mov     [rsp+178h+var_40], rax
0x18002ca1d  mov     r12, r9
0x18002ca20  mov     r14, r8
0x18002ca23  mov     rsi, rdx
0x18002ca26  mov     r13, rcx
0x18002ca29  mov     [rsp+178h+var_138], rdx
0x18002ca2e  lea     rdx, sourceString
0x18002ca35  lea     rcx, [rsp+178h+var_E0]
0x18002ca3d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002ca42  nop
0x18002ca43  xor     r15d, r15d
0x18002ca46  movzx   ecx, byte ptr [rsi]
0x18002ca49  test    ecx, ecx
0x18002ca4b  jz      short loc_18002CA79
0x18002ca4d  sub     ecx, 1
0x18002ca50  jz      short loc_18002CA6F
0x18002ca52  cmp     ecx, 1
0x18002ca55  jz      short loc_18002CA5E
0x18002ca57  mov     ecx, 1
0x18002ca5c  jmp     short loc_18002CA7B
0x18002ca5e  mov     rax, [rsi+8]
0x18002ca62  mov     rcx, [rax+8]
0x18002ca66  sub     rcx, [rax]
0x18002ca69  sar     rcx, 4
0x18002ca6d  jmp     short loc_18002CA7B
0x18002ca6f  mov     rax, [rsi+8]
0x18002ca73  mov     rcx, [rax+8]
0x18002ca77  jmp     short loc_18002CA7B
0x18002ca79  xor     ecx, ecx
0x18002ca7b  cmp     r15, rcx
0x18002ca7e  jnb     loc_18002CE82
0x18002ca84  xorps   xmm0, xmm0
0x18002ca87  movups  [rsp+178h+var_120], xmm0
0x18002ca8c  mov     [rsp+178h+var_110], 0
0x18002ca95  mov     [rsp+178h+var_108], 7
0x18002ca9e  xor     eax, eax
0x18002caa0  mov     word ptr [rsp+178h+var_120], ax
0x18002caa5  mov     rdx, r15
0x18002caa8  mov     rcx, rsi
0x18002caab  call    ??A?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@@nlohmann@@QEAAAEAV01@_K@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::operator[](unsigned __int64)
0x18002cab0  lea     rdx, [rsp+178h+var_80]
0x18002cab8  mov     rcx, rax
0x18002cabb  call    ??$get@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$0A@@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@@nlohmann@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::get<std::string,0>(void)
0x18002cac0  nop
0x18002cac1  lea     rdx, [rsp+178h+var_80]
0x18002cac9  lea     rcx, [rsp+178h+var_100]
0x18002cace  call    ?Utf8ToWide@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; Utf8ToWide(std::string const &)
0x18002cad3  nop
0x18002cad4  lea     rcx, [rsp+178h+var_100]
0x18002cad9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002cade  mov     rcx, rax
0x18002cae1  mov     r9d, 11h
0x18002cae7  lea     r8, aOemnameUnclean; "OEMName_Uncleaned"
0x18002caee  mov     rdx, [rsp+178h+var_F0]
0x18002caf6  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18002cafb  test    al, al
0x18002cafd  jz      short loc_18002CB0E
0x18002caff  mov     r8d, 13h
0x18002cb05  lea     rdx, aOemmanufacture; "OEMManufacturerName"
0x18002cb0c  jmp     short loc_18002CB46
0x18002cb0e  lea     rcx, [rsp+178h+var_100]
0x18002cb13  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002cb18  mov     rcx, rax
0x18002cb1b  mov     r9d, 0Bh
0x18002cb21  lea     r8, aOemsubmodel; "OEMSubModel"
0x18002cb28  mov     rdx, [rsp+178h+var_F0]
0x18002cb30  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18002cb35  test    al, al
0x18002cb37  jz      short loc_18002CB4D
0x18002cb39  mov     r8d, 0Bh
0x18002cb3f  lea     rdx, aOemmodelsku; "OEMModelSKU"
0x18002cb46  lea     rcx, [rsp+178h+var_120]
0x18002cb4b  jmp     short loc_18002CB8A
0x18002cb4d  lea     rcx, [rsp+178h+var_100]
0x18002cb52  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002cb57  mov     rcx, rax
0x18002cb5a  mov     r9d, 8
0x18002cb60  lea     r8, aOemmodel; "OEMModel"
0x18002cb67  mov     rdx, [rsp+178h+var_F0]
0x18002cb6f  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18002cb74  lea     rcx, [rsp+178h+var_120]
0x18002cb79  test    al, al
0x18002cb7b  jz      short loc_18002CB91
0x18002cb7d  mov     r8d, 0Eh
0x18002cb83  lea     rdx, aOemmodelnumber; "OEMModelNumber"
0x18002cb8a  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18002cb8f  jmp     short loc_18002CB9B
0x18002cb91  lea     rdx, [rsp+178h+var_100]
0x18002cb96  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18002cb9b  lea     r8, asc_18006D248; ":"
0x18002cba2  lea     rdx, [rsp+178h+var_120]
0x18002cba7  lea     rcx, [rsp+178h+var_60]
0x18002cbaf  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18002cbb4  mov     r8, rax
0x18002cbb7  mov     rcx, rax
0x18002cbba  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002cbbf  mov     r8, [r8+10h]
0x18002cbc3  mov     rdx, rax
0x18002cbc6  mov     rcx, r12
0x18002cbc9  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18002cbce  nop
0x18002cbcf  lea     rcx, [rsp+178h+var_60]
0x18002cbd7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002cbdc  mov     [rsp+178h+var_148], 0
0x18002cbe5  lea     rcx, [rsp+178h+var_120]
0x18002cbea  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002cbef  mov     rdi, rax
0x18002cbf2  mov     rbx, [r13+0]
0x18002cbf6  xor     edx, edx
0x18002cbf8  lea     rcx, [rsp+178h+var_148]
0x18002cbfd  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002cc02  mov     [rsp+178h+var_130], rbx
0x18002cc07  mov     [rsp+178h+var_158], 10000006h
0x18002cc0f  lea     r9, [rsp+178h+var_148]
0x18002cc14  mov     r8, rdi
0x18002cc17  lea     rcx, [rsp+178h+var_130]
0x18002cc1c  call    ??$get_value_with_type@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@Uerr_returncode_policy@2@@?$reg_view_t@Uerr_returncode_policy@wil@@@reg_view_details@reg@wil@@AEBAJPEBG0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@3@K@Z; wil::reg::reg_view_details::reg_view_t<wil::err_returncode_policy>::get_value_with_type<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,wil::err_returncode_policy>(ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ulong)
0x18002cc21  mov     ebx, eax
0x18002cc23  cmp     eax, 80070002h
0x18002cc28  jnz     loc_18002CCD2
0x18002cc2e  lea     rcx, [rsp+178h+var_120]
0x18002cc33  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002cc38  mov     rdx, rax
0x18002cc3b  lea     rcx, aRegistryLsNotF; "Registry %ls not found, will use empty "...
0x18002cc42  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18002cc47  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002cc4b  lea     rdx, sourceString
0x18002cc52  lea     rcx, [rsp+178h+var_140]
0x18002cc57  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18002cc5c  lea     rdx, [rsp+178h+var_140]
0x18002cc61  lea     rcx, [rsp+178h+var_148]
0x18002cc66  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18002cc6b  lea     rcx, [rsp+178h+var_140]
0x18002cc70  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002cc75  mov     rdx, [rsp+178h+var_148]
0x18002cc7a  test    rdx, rdx
0x18002cc7d  jnz     loc_18002CD44
0x18002cc83  lea     rcx, [rsp+178h+var_148]
0x18002cc88  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002cc8d  nop
0x18002cc8e  lea     rcx, [rsp+178h+var_100]
0x18002cc93  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002cc98  nop
0x18002cc99  lea     rcx, [rsp+178h+var_80]
0x18002cca1  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18002cca6  nop
0x18002cca7  lea     rcx, [rsp+178h+var_120]
0x18002ccac  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002ccb1  nop
0x18002ccb2  lea     rcx, [rsp+178h+var_E0]
0x18002ccba  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002ccbf  nop
0x18002ccc0  mov     rcx, rsi
0x18002ccc3  call    ??1?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@@nlohmann@@QEAA@XZ; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::~basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>(void)
0x18002ccc8  mov     eax, 8007000Eh
0x18002cccd  jmp     loc_18002CF83
0x18002ccd2  test    ebx, ebx
0x18002ccd4  jns     short loc_18002CD3F
0x18002ccd6  lea     rcx, [rsp+178h+var_120]
0x18002ccdb  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002cce0  mov     rdx, rax
0x18002cce3  mov     r8d, ebx
0x18002cce6  lea     rcx, aFailedToReadLs; "Failed to read %ls registry hr: %x"
0x18002cced  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18002ccf2  nop
0x18002ccf3  lea     rcx, [rsp+178h+var_148]
0x18002ccf8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002ccfd  nop
0x18002ccfe  lea     rcx, [rsp+178h+var_100]
0x18002cd03  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002cd08  nop
0x18002cd09  lea     rcx, [rsp+178h+var_80]
0x18002cd11  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18002cd16  nop
0x18002cd17  lea     rcx, [rsp+178h+var_120]
0x18002cd1c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002cd21  nop
0x18002cd22  lea     rcx, [rsp+178h+var_E0]
0x18002cd2a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002cd2f  nop
0x18002cd30  mov     rcx, rsi
0x18002cd33  call    ??1?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@@nlohmann@@QEAA@XZ; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::~basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>(void)
0x18002cd38  mov     eax, ebx
0x18002cd3a  jmp     loc_18002CF83
0x18002cd3f  mov     rdx, [rsp+178h+var_148]
0x18002cd44  lea     rcx, [rsp+178h+var_A0]
0x18002cd4c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002cd51  nop
0x18002cd52  lea     rcx, [rsp+178h+var_120]
0x18002cd57  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002cd5c  mov     rcx, rax
0x18002cd5f  mov     r9d, 0Eh
0x18002cd65  lea     r8, aOsarchitecture; "OSArchitecture"
0x18002cd6c  mov     rdx, [rsp+178h+var_110]
0x18002cd71  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18002cd76  test    al, al
0x18002cd78  jz      short loc_18002CDB0
0x18002cd7a  lea     rcx, [rsp+178h+var_A0]
0x18002cd82  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002cd87  mov     rbx, rax
0x18002cd8a  mov     rcx, [rsp+178h+var_90]
0x18002cd92  lea     rdi, [rax+rcx*2]
0x18002cd96  cmp     rax, rdi
0x18002cd99  jz      short loc_18002CDB0
0x18002cd9b  movzx   ecx, word ptr [rbx]
0x18002cd9e  call    cs:__imp__o_tolower
0x18002cda4  mov     [rbx], ax
0x18002cda7  add     rbx, 2
0x18002cdab  cmp     rbx, rdi
0x18002cdae  jnz     short loc_18002CD9B
0x18002cdb0  lea     rdx, [rsp+178h+var_A0]
0x18002cdb8  lea     rcx, [rsp+178h+var_C0]
0x18002cdc0  call    ?trim@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@Z; trim(std::wstring const &)
0x18002cdc5  nop
0x18002cdc6  lea     rcx, [rsp+178h+var_C0]
0x18002cdce  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002cdd3  mov     rdx, rax
0x18002cdd6  mov     r8, [rsp+178h+var_B0]
0x18002cdde  lea     rcx, [rsp+178h+var_E0]
0x18002cde6  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18002cdeb  lea     r8, asc_18006D350; ";"
0x18002cdf2  lea     rdx, [rsp+178h+var_C0]
0x18002cdfa  lea     rcx, [rsp+178h+var_60]
0x18002ce02  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18002ce07  mov     r8, rax
0x18002ce0a  mov     rcx, rax
0x18002ce0d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002ce12  mov     r8, [r8+10h]
0x18002ce16  mov     rdx, rax
0x18002ce19  mov     rcx, r12
0x18002ce1c  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18002ce21  nop
0x18002ce22  lea     rcx, [rsp+178h+var_60]
0x18002ce2a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002ce2f  nop
0x18002ce30  lea     rcx, [rsp+178h+var_C0]
0x18002ce38  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002ce3d  nop
0x18002ce3e  lea     rcx, [rsp+178h+var_A0]
0x18002ce46  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002ce4b  nop
0x18002ce4c  lea     rcx, [rsp+178h+var_148]
0x18002ce51  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002ce56  nop
0x18002ce57  lea     rcx, [rsp+178h+var_100]
0x18002ce5c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002ce61  nop
0x18002ce62  lea     rcx, [rsp+178h+var_80]
0x18002ce6a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18002ce6f  nop
0x18002ce70  lea     rcx, [rsp+178h+var_120]
0x18002ce75  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002ce7a  inc     r15
0x18002ce7d  jmp     loc_18002CA46
0x18002ce82  mov     rdx, r14
0x18002ce85  lea     rcx, [rsp+178h+var_E0]
0x18002ce8d  call    ?GetSHA256Hash@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@@Z; GetSHA256Hash(std::wstring const &,std::wstring &)
0x18002ce92  mov     ebx, eax
0x18002ce94  test    eax, eax
0x18002ce96  jns     short loc_18002CEC4
0x18002ce98  mov     edx, eax
0x18002ce9a  lea     rcx, aFailedToGetSha; "Failed to get SHA256 hash: %x"
0x18002cea1  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18002cea6  nop
0x18002cea7  lea     rcx, [rsp+178h+var_E0]
0x18002ceaf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002ceb4  nop
0x18002ceb5  mov     rcx, rsi
0x18002ceb8  call    ??1?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@@nlohmann@@QEAA@XZ; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>::~basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator>(void)
0x18002cebd  mov     eax, ebx
0x18002cebf  jmp     loc_18002CF83
0x18002cec4  mov     rcx, r14
0x18002cec7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002cecc  mov     r9d, 40h ; '@'
0x18002ced2  lea     r8, aE3b0c44298fc1c; "e3b0c44298fc1c149afbf4c8996fb92427ae41e"...
0x18002ced9  mov     rdx, [r14+10h]
0x18002cedd  mov     rcx, rax
0x18002cee0  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18002cee5  test    al, al
0x18002cee7  jz      short loc_18002CEFE
0x18002cee9  mov     r8d, 8
0x18002ceef  lea     rdx, aBaEmpty; "BA_EMPTY"
0x18002cef6  mov     rcx, r14
0x18002cef9  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18002cefe  mov     rcx, r12
0x18002cf01  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002cf06  mov     rdx, rax
0x18002cf09  lea     rcx, aBucketattribva; "BucketAttribValues: %ls"
0x18002cf10  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18002cf15  lea     rcx, [rsp+178h+var_E0]
  ... truncated ...
```
