# Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::GetAllVariantKeys(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &)

- ea: `0x18005371c`
- end: `0x18005396c`
- name: `?GetAllVariantKeys@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@QEBAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@11@Z`
- size: `592`
- prototype: ``
- caller_count: `3`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x1800544c0`
- `0x180054eac`
- `0x1800553e8`

## callees

- `0x1800094c0`
- `0x18001c3b4`
- `0x18001c5fc`
- `0x1800257ec`
- `0x180029408`
- `0x1800299c4`
- `0x18002a564`
- `0x18002f280`
- `0x18002f93c`
- `0x18002f978`
- `0x18003ce34`
- `0x1800473fc`
- `0x18005371c`
- `0x180054374`
- `0x180054fd0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005378a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180053837`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180053911`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005378a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180053837`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180053911`

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
  const WCHAR *v8; // rax
  unsigned int v9; // eax
  __int64 v10; // rax
  __int64 v11; // rdx
  unsigned __int64 v12; // rax
  __int64 v13; // rcx
  const WCHAR *v14; // rax
  unsigned int v15; // eax
  __int64 v16; // rcx
  __int64 active; // rax
  __int64 v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rax
  const WCHAR *v21; // rax
  unsigned int v22; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-51h]
  unsigned int phkResulta; // [rsp+20h] [rbp-51h]
  unsigned int phkResultb; // [rsp+20h] [rbp-51h]
  HKEY hKey; // [rsp+30h] [rbp-41h] BYREF
  _QWORD Src[2]; // [rsp+38h] [rbp-39h] BYREF
  unsigned __int64 v29; // [rsp+48h] [rbp-29h]
  unsigned __int64 v30; // [rsp+50h] [rbp-21h]
  _BYTE v31[16]; // [rsp+58h] [rbp-19h] BYREF
  unsigned __int64 v32; // [rsp+68h] [rbp-9h]
  _BYTE v33[32]; // [rsp+78h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+57h]

  std::wstring::wstring(Src);
  Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::GetCapabilitiesKey(&hKey);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    a3,
    0);
  v8 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  v9 = RegOpenKeyExW(hKey, v8, 0, 0x20119u, a3);
  if ( v9 != 2 )
  {
    if ( v9 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x27B,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilitypolicystore.cpp",
        (const char *)v9,
        phkResult);
    std::wstring::operator=(Src, a2);
    if ( v29 >= v30 )
    {
      std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(Src);
    }
    else
    {
      ++v29;
      v10 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
      *(_DWORD *)(v10 + 2 * v11) = 92;
    }
    v12 = std::_WChar_traits<unsigned short>::length(L"Edition");
    std::wstring::_Append<unsigned short>(Src, v13, v12);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      a4,
      0);
    v14 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
    v15 = RegOpenKeyExW(hKey, v14, 0, 0x20119u, a4);
    if ( (v15 & 0xFFFFFFFD) != 0 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x28B,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilitypolicystore.cpp",
        (const char *)v15,
        phkResulta);
    std::wstring::wstring(v31);
    active = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadActivePolicyCode(v16, v33, &hKey);
    std::wstring::operator=(v31, active);
    std::wstring::_Tidy_deallocate(v33);
    if ( v32 )
    {
      std::wstring::operator=(Src, a2);
      if ( v29 >= v30 )
      {
        std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(Src);
      }
      else
      {
        ++v29;
        v18 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
        *(_DWORD *)(v18 + 2 * v19) = 92;
      }
      v20 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v31);
      std::wstring::_Append<unsigned short>(Src, v20, v32);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        a5,
        0);
      v21 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
      v22 = RegOpenKeyExW(hKey, v21, 0, 0x20119u, a5);
      if ( (v22 & 0xFFFFFFFD) != 0 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x2AA,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilitypolicystore.cpp",
          (const char *)v22,
          phkResultb);
    }
    std::wstring::_Tidy_deallocate(v31);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return std::wstring::_Tidy_deallocate(Src);
}

```

## disassembly

```asm
0x18005371c  push    rbp
0x18005371e  push    rbx
0x18005371f  push    rsi
0x180053720  push    rdi
0x180053721  push    r14
0x180053723  lea     rbp, [rsp-2Fh]
0x180053728  sub     rsp, 0A0h
0x18005372f  mov     rax, cs:__security_cookie
0x180053736  xor     rax, rsp
0x180053739  mov     [rbp+4Fh+var_28], rax
0x18005373d  mov     r14, r9
0x180053740  mov     rbx, r8
0x180053743  mov     rdi, rdx
0x180053746  mov     rsi, [rbp+4Fh+arg_20]
0x18005374a  lea     rcx, [rbp+4Fh+Src]
0x18005374e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180053753  nop
0x180053754  mov     edx, 20019h
0x180053759  lea     rcx, [rbp+4Fh+hKey]; phkResult
0x18005375d  call    ?GetCapabilitiesKey@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@K@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::GetCapabilitiesKey(ulong)
0x180053762  nop
0x180053763  xor     edx, edx
0x180053765  mov     rcx, rbx
0x180053768  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18005376d  mov     rcx, rdi
0x180053770  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180053775  mov     qword ptr [rsp+0C0h+phkResult], rbx; unsigned int
0x18005377a  mov     r9d, 20119h; samDesired
0x180053780  xor     r8d, r8d; ulOptions
0x180053783  mov     rdx, rax; lpSubKey
0x180053786  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18005378a  call    cs:__imp_RegOpenKeyExW
0x180053790  cmp     eax, 2
0x180053793  jz      loc_18005393F
0x180053799  mov     rcx, [rbp+57h]; this
0x18005379d  test    eax, eax
0x18005379f  jz      short loc_1800537B6
0x1800537a1  mov     r9d, eax; char *
0x1800537a4  lea     r8, aOnecoreBaseDev_16; "onecore\\base\\devices\\cam\\core\\capa"...
0x1800537ab  mov     edx, 27Bh; void *
0x1800537b0  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800537b6  mov     rdx, rdi
0x1800537b9  lea     rcx, [rbp+4Fh+Src]
0x1800537bd  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800537c2  mov     rdx, [rbp+4Fh+var_78]
0x1800537c6  lea     rcx, [rbp+4Fh+Src]; Src
0x1800537ca  cmp     rdx, [rbp+4Fh+var_70]
0x1800537ce  jnb     short loc_1800537E7
0x1800537d0  lea     rax, [rdx+1]
0x1800537d4  mov     [rbp+4Fh+var_78], rax
0x1800537d8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800537dd  mov     ebx, 5Ch ; '\'
0x1800537e2  mov     [rax+rdx*2], ebx
0x1800537e5  jmp     short loc_1800537F4
0x1800537e7  mov     ebx, 5Ch ; '\'
0x1800537ec  mov     r9d, ebx
0x1800537ef  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x1800537f4  lea     rcx, aEdition; "Edition"
0x1800537fb  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180053800  mov     r8, rax
0x180053803  mov     rdx, rcx
0x180053806  lea     rcx, [rbp+4Fh+Src]
0x18005380a  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18005380f  xor     edx, edx
0x180053811  mov     rcx, r14
0x180053814  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180053819  lea     rcx, [rbp+4Fh+Src]
0x18005381d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180053822  mov     rdx, rax; lpSubKey
0x180053825  mov     qword ptr [rsp+0C0h+phkResult], r14; unsigned int
0x18005382a  mov     r9d, 20119h; samDesired
0x180053830  xor     r8d, r8d; ulOptions
0x180053833  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180053837  call    cs:__imp_RegOpenKeyExW
0x18005383d  mov     r14d, 0FFFFFFFDh
0x180053843  test    r14d, eax
0x180053846  jz      short loc_180053861
0x180053848  mov     rcx, [rbp+57h]; this
0x18005384c  mov     r9d, eax; char *
0x18005384f  lea     r8, aOnecoreBaseDev_16; "onecore\\base\\devices\\cam\\core\\capa"...
0x180053856  mov     edx, 28Bh; void *
0x18005385b  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180053861  lea     rcx, [rbp+4Fh+var_68]
0x180053865  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18005386a  nop
0x18005386b  lea     r8, [rbp+4Fh+hKey]
0x18005386f  lea     rdx, [rbp+4Fh+var_48]
0x180053873  call    ?ReadActivePolicyCode@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadActivePolicyCode(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &)
0x180053878  mov     rdx, rax
0x18005387b  lea     rcx, [rbp+4Fh+var_68]
0x18005387f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180053884  lea     rcx, [rbp+4Fh+var_48]
0x180053888  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005388d  cmp     [rbp+4Fh+var_58], 0
0x180053892  jz      loc_180053935
0x180053898  mov     rdx, rdi
0x18005389b  lea     rcx, [rbp+4Fh+Src]
0x18005389f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800538a4  mov     rdx, [rbp+4Fh+var_78]
0x1800538a8  lea     rcx, [rbp+4Fh+Src]; Src
0x1800538ac  cmp     rdx, [rbp+4Fh+var_70]
0x1800538b0  jnb     short loc_1800538C8
0x1800538b2  lea     rax, [rdx+1]
0x1800538b6  mov     [rbp+4Fh+var_78], rax
0x1800538ba  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800538bf  mov     dword ptr [rax+rdx*2], 5Ch ; '\'
0x1800538c6  jmp     short loc_1800538D0
0x1800538c8  mov     r9d, ebx
0x1800538cb  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x1800538d0  lea     rcx, [rbp+4Fh+var_68]
0x1800538d4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800538d9  mov     rdx, rax
0x1800538dc  mov     r8, [rbp+4Fh+var_58]
0x1800538e0  lea     rcx, [rbp+4Fh+Src]
0x1800538e4  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800538e9  xor     edx, edx
0x1800538eb  mov     rcx, rsi
0x1800538ee  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800538f3  lea     rcx, [rbp+4Fh+Src]
0x1800538f7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800538fc  mov     rdx, rax; lpSubKey
0x1800538ff  mov     qword ptr [rsp+0C0h+phkResult], rsi; unsigned int
0x180053904  mov     r9d, 20119h; samDesired
0x18005390a  xor     r8d, r8d; ulOptions
0x18005390d  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180053911  call    cs:__imp_RegOpenKeyExW
0x180053917  test    r14d, eax
0x18005391a  jz      short loc_180053935
0x18005391c  mov     rcx, [rbp+57h]; this
0x180053920  mov     r9d, eax; char *
0x180053923  lea     r8, aOnecoreBaseDev_16; "onecore\\base\\devices\\cam\\core\\capa"...
0x18005392a  mov     edx, 2AAh; void *
0x18005392f  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180053935  lea     rcx, [rbp+4Fh+var_68]
0x180053939  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005393e  nop
0x18005393f  lea     rcx, [rbp+4Fh+hKey]
0x180053943  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180053948  nop
0x180053949  lea     rcx, [rbp+4Fh+Src]
0x18005394d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180053952  mov     rcx, [rbp+4Fh+var_28]
0x180053956  xor     rcx, rsp; StackCookie
0x180053959  call    __security_check_cookie
0x18005395e  add     rsp, 0A0h
0x180053965  pop     r14
0x180053967  pop     rdi
0x180053968  pop     rsi
0x180053969  pop     rbx
0x18005396a  pop     rbp
0x18005396b  retn
```
