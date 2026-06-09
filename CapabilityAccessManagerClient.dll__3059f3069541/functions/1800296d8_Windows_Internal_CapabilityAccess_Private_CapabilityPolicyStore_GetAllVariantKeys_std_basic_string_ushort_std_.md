# Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::GetAllVariantKeys(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &)

- ea: `0x1800296d8`
- end: `0x180029957`
- name: `?GetAllVariantKeys@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@QEBAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@11@Z`
- size: `639`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x18002a438`

## callees

- `0x180003c80`
- `0x18000f9e4`
- `0x180014754`
- `0x18001b444`
- `0x1800207a4`
- `0x180021550`
- `0x180021638`
- `0x1800236ac`
- `0x180023b38`
- `0x180025080`
- `0x1800296d8`
- `0x180029d34`
- `0x18002a020`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029760`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800297f4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800298c6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029760`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800297f4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800298c6`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::GetAllVariantKeys(
        __int64 a1,
        __int64 a2,
        HKEY *a3,
        HKEY *a4,
        HKEY *a5)
{
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  const WCHAR *v11; // rax
  unsigned int v12; // eax
  __int64 v13; // r8
  __int64 v14; // r9
  unsigned __int64 v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  const WCHAR *v21; // rax
  unsigned int v22; // eax
  __int64 v23; // rcx
  HKEY ActivePolicyCode; // rax
  __int64 v25; // r8
  __int64 v26; // r9
  unsigned __int64 v27; // rdx
  __int64 v28; // rax
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // r9
  __int64 v32; // rax
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // r9
  const WCHAR *v36; // rax
  unsigned int v37; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-51h]
  unsigned int phkResulta; // [rsp+20h] [rbp-51h]
  unsigned int phkResultb; // [rsp+20h] [rbp-51h]
  HKEY hKey; // [rsp+30h] [rbp-41h] BYREF
  __int128 Src; // [rsp+38h] [rbp-39h] BYREF
  unsigned __int64 v44; // [rsp+48h] [rbp-29h]
  unsigned __int64 v45; // [rsp+50h] [rbp-21h]
  __int128 v46; // [rsp+58h] [rbp-19h] BYREF
  __int64 v47; // [rsp+68h] [rbp-9h]
  __int64 v48; // [rsp+70h] [rbp-1h]
  struct HKEY__ v49[8]; // [rsp+78h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+57h]

  Src = 0;
  v44 = 0;
  v45 = 7;
  LOWORD(Src) = 0;
  Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::GetCapabilitiesKey(&hKey, 131097);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    a3,
    0);
  v11 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2, v8, v9, v10);
  v12 = RegOpenKeyExW(hKey, v11, 0, 0x20119u, a3);
  if ( v12 != 2 )
  {
    if ( v12 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x27B,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilitypolicystore.cpp",
        (const char *)v12,
        phkResult);
    std::wstring::operator=(&Src, a2);
    v15 = v44;
    if ( v44 >= v45 )
    {
      std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(&Src);
    }
    else
    {
      ++v44;
      v16 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&Src, v15, v13, v14);
      *(_DWORD *)(v16 + 2 * v17) = 92;
    }
    std::wstring::_Append<unsigned short>(&Src, L"Edition", 7);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      a4,
      0);
    v21 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&Src, v18, v19, v20);
    v22 = RegOpenKeyExW(hKey, v21, 0, 0x20119u, a4);
    if ( (v22 & 0xFFFFFFFD) != 0 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x28B,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilitypolicystore.cpp",
        (const char *)v22,
        phkResulta);
    v46 = 0;
    v47 = 0;
    v48 = 7;
    LOWORD(v46) = 0;
    ActivePolicyCode = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadActivePolicyCode(
                         v23,
                         v49);
    std::wstring::operator=(&v46, ActivePolicyCode);
    std::wstring::_Tidy_deallocate(v49);
    if ( v47 )
    {
      std::wstring::operator=(&Src, a2);
      v27 = v44;
      if ( v44 >= v45 )
      {
        std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(&Src);
      }
      else
      {
        ++v44;
        v28 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&Src, v27, v25, v26);
        *(_DWORD *)(v28 + 2 * v29) = 92;
      }
      v32 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v46, v29, v30, v31);
      std::wstring::_Append<unsigned short>(&Src, v32, v47);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        a5,
        0);
      v36 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&Src, v33, v34, v35);
      v37 = RegOpenKeyExW(hKey, v36, 0, 0x20119u, a5);
      if ( (v37 & 0xFFFFFFFD) != 0 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x2AA,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilitypolicystore.cpp",
          (const char *)v37,
          phkResultb);
    }
    std::wstring::_Tidy_deallocate(&v46);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return std::wstring::_Tidy_deallocate(&Src);
}

```

## disassembly

```asm
0x1800296d8  mov     [rsp-8+arg_0], rbx
0x1800296dd  push    rbp
0x1800296de  push    rsi
0x1800296df  push    rdi
0x1800296e0  push    r12
0x1800296e2  push    r14
0x1800296e4  lea     rbp, [rsp-2Fh]
0x1800296e9  sub     rsp, 0A0h
0x1800296f0  mov     rax, cs:__security_cookie
0x1800296f7  xor     rax, rsp
0x1800296fa  mov     [rbp+4Fh+var_28], rax
0x1800296fe  mov     rsi, r9
0x180029701  mov     rbx, r8
0x180029704  mov     rdi, rdx
0x180029707  mov     r14, [rbp+4Fh+arg_20]
0x18002970b  xorps   xmm0, xmm0
0x18002970e  movups  [rbp+4Fh+Src], xmm0
0x180029712  mov     [rbp+4Fh+var_78], 0
0x18002971a  mov     r12d, 7
0x180029720  mov     [rbp+4Fh+var_70], r12
0x180029724  xor     eax, eax
0x180029726  mov     word ptr [rbp+4Fh+Src], ax
0x18002972a  mov     edx, 20019h
0x18002972f  lea     rcx, [rbp+4Fh+hKey]; phkResult
0x180029733  call    ?GetCapabilitiesKey@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@K@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::GetCapabilitiesKey(ulong)
0x180029738  nop
0x180029739  xor     edx, edx
0x18002973b  mov     rcx, rbx
0x18002973e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180029743  mov     rcx, rdi
0x180029746  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002974b  mov     qword ptr [rsp+0C0h+phkResult], rbx; unsigned int
0x180029750  mov     r9d, 20119h; samDesired
0x180029756  xor     r8d, r8d; ulOptions
0x180029759  mov     rdx, rax; lpSubKey
0x18002975c  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180029760  call    cs:__imp_RegOpenKeyExW
0x180029766  cmp     eax, 2
0x180029769  jz      loc_1800298DA
0x18002976f  mov     rcx, [rbp+57h]; this
0x180029773  test    eax, eax
0x180029775  jnz     loc_180029929
0x18002977b  mov     rdx, rdi
0x18002977e  lea     rcx, [rbp+4Fh+Src]
0x180029782  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180029787  mov     rdx, [rbp+4Fh+var_78]
0x18002978b  lea     rcx, [rbp+4Fh+Src]; Src
0x18002978f  cmp     rdx, [rbp+4Fh+var_70]
0x180029793  jnb     short loc_1800297AC
0x180029795  lea     rax, [rdx+1]
0x180029799  mov     [rbp+4Fh+var_78], rax
0x18002979d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800297a2  lea     ebx, [r12+55h]
0x1800297a7  mov     [rax+rdx*2], ebx
0x1800297aa  jmp     short loc_1800297B9
0x1800297ac  mov     ebx, 5Ch ; '\'
0x1800297b1  mov     r9d, ebx
0x1800297b4  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x1800297b9  mov     r8, r12
0x1800297bc  lea     rdx, aEdition; "Edition"
0x1800297c3  lea     rcx, [rbp+4Fh+Src]
0x1800297c7  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800297cc  xor     edx, edx
0x1800297ce  mov     rcx, rsi
0x1800297d1  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800297d6  lea     rcx, [rbp+4Fh+Src]
0x1800297da  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800297df  mov     rdx, rax; lpSubKey
0x1800297e2  mov     qword ptr [rsp+0C0h+phkResult], rsi; unsigned int
0x1800297e7  mov     r9d, 20119h; samDesired
0x1800297ed  xor     r8d, r8d; ulOptions
0x1800297f0  mov     rcx, [rbp+4Fh+hKey]; hKey
0x1800297f4  call    cs:__imp_RegOpenKeyExW
0x1800297fa  mov     esi, 0FFFFFFFDh
0x1800297ff  test    esi, eax
0x180029801  jnz     loc_18002993E
0x180029807  xorps   xmm0, xmm0
0x18002980a  movups  [rbp+4Fh+var_68], xmm0
0x18002980e  mov     [rbp+4Fh+var_58], 0
0x180029816  mov     [rbp+4Fh+var_50], r12
0x18002981a  xor     eax, eax
0x18002981c  mov     word ptr [rbp+4Fh+var_68], ax
0x180029820  lea     r8, [rbp+4Fh+hKey]
0x180029824  lea     rdx, [rbp+4Fh+var_48]
0x180029828  call    ?ReadActivePolicyCode@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadActivePolicyCode(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &)
0x18002982d  mov     rdx, rax
0x180029830  lea     rcx, [rbp+4Fh+var_68]
0x180029834  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180029839  lea     rcx, [rbp+4Fh+var_48]
0x18002983d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029842  cmp     [rbp+4Fh+var_58], 0
0x180029847  jz      loc_1800298D0
0x18002984d  mov     rdx, rdi
0x180029850  lea     rcx, [rbp+4Fh+Src]
0x180029854  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180029859  mov     rdx, [rbp+4Fh+var_78]
0x18002985d  lea     rcx, [rbp+4Fh+Src]; Src
0x180029861  cmp     rdx, [rbp+4Fh+var_70]
0x180029865  jnb     short loc_18002987D
0x180029867  lea     rax, [rdx+1]
0x18002986b  mov     [rbp+4Fh+var_78], rax
0x18002986f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180029874  mov     dword ptr [rax+rdx*2], 5Ch ; '\'
0x18002987b  jmp     short loc_180029885
0x18002987d  mov     r9d, ebx
0x180029880  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x180029885  lea     rcx, [rbp+4Fh+var_68]
0x180029889  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002988e  mov     rdx, rax
0x180029891  mov     r8, [rbp+4Fh+var_58]
0x180029895  lea     rcx, [rbp+4Fh+Src]
0x180029899  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18002989e  xor     edx, edx
0x1800298a0  mov     rcx, r14
0x1800298a3  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800298a8  lea     rcx, [rbp+4Fh+Src]
0x1800298ac  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800298b1  mov     rdx, rax; lpSubKey
0x1800298b4  mov     qword ptr [rsp+0C0h+phkResult], r14; unsigned int
0x1800298b9  mov     r9d, 20119h; samDesired
0x1800298bf  xor     r8d, r8d; ulOptions
0x1800298c2  mov     rcx, [rbp+4Fh+hKey]; hKey
0x1800298c6  call    cs:__imp_RegOpenKeyExW
0x1800298cc  test    esi, eax
0x1800298ce  jnz     short loc_180029910
0x1800298d0  lea     rcx, [rbp+4Fh+var_68]
0x1800298d4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800298d9  nop
0x1800298da  lea     rcx, [rbp+4Fh+hKey]
0x1800298de  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800298e3  nop
0x1800298e4  lea     rcx, [rbp+4Fh+Src]
0x1800298e8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800298ed  mov     rcx, [rbp+4Fh+var_28]
0x1800298f1  xor     rcx, rsp; StackCookie
0x1800298f4  call    __security_check_cookie
0x1800298f9  mov     rbx, [rsp+0C0h+arg_0]
0x180029901  add     rsp, 0A0h
0x180029908  pop     r14
0x18002990a  pop     r12
0x18002990c  pop     rdi
0x18002990d  pop     rsi
0x18002990e  pop     rbp
0x18002990f  retn
0x180029910  mov     rcx, [rbp+57h]; this
0x180029914  mov     r9d, eax; char *
0x180029917  lea     r8, aOnecoreBaseDev_1; "onecore\\base\\devices\\cam\\core\\capa"...
0x18002991e  mov     edx, 2AAh; void *
0x180029923  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180029929  mov     r9d, eax; char *
0x18002992c  lea     r8, aOnecoreBaseDev_1; "onecore\\base\\devices\\cam\\core\\capa"...
0x180029933  mov     edx, 27Bh; void *
0x180029938  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18002993e  mov     rcx, [rbp+57h]; this
0x180029942  mov     r9d, eax; char *
0x180029945  lea     r8, aOnecoreBaseDev_1; "onecore\\base\\devices\\cam\\core\\capa"...
0x18002994c  mov     edx, 28Bh; void *
0x180029951  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
