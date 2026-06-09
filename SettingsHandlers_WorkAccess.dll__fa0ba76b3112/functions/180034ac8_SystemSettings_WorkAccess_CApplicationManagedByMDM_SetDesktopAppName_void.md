# SystemSettings::WorkAccess::CApplicationManagedByMDM::SetDesktopAppName(void)

- ea: `0x180034ac8`
- end: `0x180034d01`
- name: `?SetDesktopAppName@CApplicationManagedByMDM@WorkAccess@SystemSettings@@QEAAJXZ`
- size: `569`
- prototype: `__int64 __fastcall(SystemSettings::WorkAccess::CApplicationManagedByMDM *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180030e8c`

## callees

- `0x180002a60`
- `0x1800096ec`
- `0x1800208f8`
- `0x180023164`
- `0x180023458`
- `0x180023ae0`
- `0x180027a58`
- `0x1800290b8`
- `0x1800291ec`
- `0x180029234`
- `0x18002df94`
- `0x18002eccc`
- `0x180034ac8`
- `0x180035450`
- `0x1800391a4`
- `0x180039484`
- `0x1800395cc`
- `0x180039a78`
- `0x18003a944`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180034c00`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180034c00`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180034bd6`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180034bd6`
- `OLEAUT32!__imp_SysFreeString` at `0x180034c3c`
- `OLEAUT32!__imp_SysFreeString` at `0x180034c77`
- `OLEAUT32!__imp_SysFreeString` at `0x180034c3c`
- `OLEAUT32!__imp_SysFreeString` at `0x180034c77`

## string_xrefs

- `0x180034b1a`: `shellcommon\shell\settingshandlers\workaccess\lib\accountenthusiast.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SystemSettings::WorkAccess::CApplicationManagedByMDM::SetDesktopAppName(
        SystemSettings::WorkAccess::CApplicationManagedByMDM *this)
{
  __int64 last_of; // rax
  unsigned int v3; // ebx
  __int64 v4; // rax
  WCHAR *v5; // rax
  unsigned int v6; // ebx
  const unsigned __int16 *v7; // rax
  _bstr_t *v8; // rax
  HANDLE v9; // rax
  unsigned int v10; // r8d
  const char *v11; // r9
  __int64 v12; // r8
  __int64 v14; // rdx
  DWORD dwCreationFlags; // [rsp+20h] [rbp-39h]
  __int64 v16; // [rsp+30h] [rbp-29h] BYREF
  HANDLE v17; // [rsp+38h] [rbp-21h] BYREF
  DWORD ThreadId; // [rsp+40h] [rbp-19h] BYREF
  _QWORD v19[4]; // [rsp+48h] [rbp-11h] BYREF
  _BYTE v20[32]; // [rsp+68h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  std::wstring::wstring(v20, *((_QWORD *)this + 30));
  last_of = std::wstring::find_last_of(v20);
  if ( last_of == -1 )
  {
    v3 = -2147023728;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7B8,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\accountenthusiast.cpp",
      (const char *)0x80070490LL,
      dwCreationFlags);
LABEL_10:
    std::wstring::_Tidy_deallocate(v20);
    return v3;
  }
  v16 = 0;
  v4 = std::wstring::substr(v20, v19, last_of + 1);
  v5 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v4);
  v6 = (unsigned int)UrlUnEscapeWrapper(v5) >> 31;
  std::wstring::_Tidy_deallocate(v19);
  if ( (unsigned __int8)v6 != 1 )
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
      (char *)this + 216,
      v16,
      -1);
  v7 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v20);
  v8 = _bstr_t::_bstr_t((_bstr_t *)&v17, v7);
  _bstr_t::operator=(&SystemSettings::WorkAccess::CEnrollmentHelper::_appStringProperty, v8);
  _bstr_t::_Free((_bstr_t *)&v17);
  ThreadId = 0;
  v9 = CreateThread(
         0,
         0,
         (LPTHREAD_START_ROUTINE)SystemSettings::WorkAccess::CEnrollmentHelper::GetAppNameByNodePath,
         0,
         0,
         &ThreadId);
  v17 = v9;
  if ( !v9 )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x7C4, v10, v11);
  WaitForSingleObject(v9, 0xFFFFFFFF);
  if ( SystemSettings::WorkAccess::CEnrollmentHelper::_appCspValue )
  {
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v19);
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             v19,
                             v12) )
    {
      SysFreeString(SystemSettings::WorkAccess::CEnrollmentHelper::_appCspValue);
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v19);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v17);
      CTSmartObj<unsigned short *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(&v16);
      v3 = -2147024882;
      goto LABEL_10;
    }
    SysFreeString(SystemSettings::WorkAccess::CEnrollmentHelper::_appCspValue);
    if ( v19[0] != v19[1] )
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
        (char *)this + 216,
        v19[0],
        -1);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v19);
  }
  if ( SystemSettings::WorkAccess::CEnrollmentHelper::_appStatus )
    v14 = *SystemSettings::WorkAccess::CEnrollmentHelper::_appStatus;
  else
    v14 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
    (char *)this + 264,
    v14,
    -1);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v17);
  CTSmartObj<unsigned short *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(&v16);
  std::wstring::_Tidy_deallocate(v20);
  return 0;
}

```

## disassembly

```asm
0x180034ac8  push    rbp
0x180034aca  push    rbx
0x180034acb  push    rdi
0x180034acc  push    r14
0x180034ace  lea     rbp, [rsp-3Fh]
0x180034ad3  sub     rsp, 98h
0x180034ada  mov     rax, cs:__security_cookie
0x180034ae1  xor     rax, rsp
0x180034ae4  mov     [rbp+57h+var_28], rax
0x180034ae8  mov     rdi, rcx
0x180034aeb  mov     rdx, [rcx+0F0h]
0x180034af2  lea     rcx, [rbp+57h+var_48]
0x180034af6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180034afb  nop
0x180034afc  lea     rcx, [rbp+57h+var_48]
0x180034b00  call    ?find_last_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::find_last_of(ushort,unsigned __int64)
0x180034b05  or      r14, 0FFFFFFFFFFFFFFFFh
0x180034b09  cmp     rax, r14
0x180034b0c  jnz     short loc_180034B30
0x180034b0e  mov     rcx, [rbp+5Fh]; this
0x180034b12  mov     ebx, 80070490h
0x180034b17  mov     r9d, ebx; char *
0x180034b1a  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\settingshandlers\\w"...
0x180034b21  mov     edx, 7B8h; void *
0x180034b26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034b2b  jmp     loc_180034C6A
0x180034b30  mov     [rbp+57h+var_80], 0
0x180034b38  lea     r8, [rax+1]
0x180034b3c  lea     rdx, [rbp+57h+var_68]
0x180034b40  lea     rcx, [rbp+57h+var_48]
0x180034b44  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x180034b49  mov     rcx, rax
0x180034b4c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180034b51  lea     rdx, [rbp+57h+var_80]
0x180034b55  mov     rcx, rax; pszUrl
0x180034b58  call    UrlUnEscapeWrapper
0x180034b5d  mov     ebx, eax
0x180034b5f  shr     ebx, 1Fh
0x180034b62  lea     rcx, [rbp+57h+var_68]
0x180034b66  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034b6b  xor     bl, 1
0x180034b6e  jz      short loc_180034B83
0x180034b70  lea     rcx, [rdi+0D8h]
0x180034b77  mov     r8, r14
0x180034b7a  mov     rdx, [rbp+57h+var_80]
0x180034b7e  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180034b83  lea     rcx, [rbp+57h+var_48]
0x180034b87  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180034b8c  mov     rdx, rax; unsigned __int16 *
0x180034b8f  lea     rcx, [rbp+57h+var_78]; this
0x180034b93  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180034b98  mov     rdx, rax
0x180034b9b  lea     rcx, ?_appStringProperty@CEnrollmentHelper@WorkAccess@SystemSettings@@2V_bstr_t@@A; _bstr_t SystemSettings::WorkAccess::CEnrollmentHelper::_appStringProperty
0x180034ba2  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x180034ba7  lea     rcx, [rbp+57h+var_78]; this
0x180034bab  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180034bb0  mov     [rbp+57h+ThreadId], 0
0x180034bb7  lea     rax, [rbp+57h+ThreadId]
0x180034bbb  mov     [rsp+0B0h+lpThreadId], rax; lpThreadId
0x180034bc0  mov     [rsp+0B0h+dwCreationFlags], 0; dwCreationFlags
0x180034bc8  xor     r9d, r9d; lpParameter
0x180034bcb  lea     r8, ?GetAppNameByNodePath@CEnrollmentHelper@WorkAccess@SystemSettings@@SAKPEAX@Z; lpStartAddress
0x180034bd2  xor     edx, edx; dwStackSize
0x180034bd4  xor     ecx, ecx; lpThreadAttributes
0x180034bd6  call    cs:__imp_CreateThread
0x180034bdd  nop     dword ptr [rax+rax+00h]
0x180034be2  mov     [rbp+57h+var_78], rax
0x180034be6  mov     rcx, [rbp+5Fh]; this
0x180034bea  test    rax, rax
0x180034bed  jnz     short loc_180034BFA
0x180034bef  mov     edx, 7C4h; void *
0x180034bf4  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180034bfa  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180034bfd  mov     rcx, rax; hHandle
0x180034c00  call    cs:__imp_WaitForSingleObject
0x180034c07  nop     dword ptr [rax+rax+00h]
0x180034c0c  mov     r8, cs:?_appCspValue@CEnrollmentHelper@WorkAccess@SystemSettings@@2PEAGEA; ushort * SystemSettings::WorkAccess::CEnrollmentHelper::_appCspValue
0x180034c13  test    r8, r8
0x180034c16  jz      loc_180034CA5
0x180034c1c  lea     rcx, [rbp+57h+var_68]
0x180034c20  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180034c25  mov     rdx, r8
0x180034c28  lea     rcx, [rbp+57h+var_68]
0x180034c2c  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180034c31  mov     rcx, cs:?_appCspValue@CEnrollmentHelper@WorkAccess@SystemSettings@@2PEAGEA; bstrString
0x180034c38  test    al, al
0x180034c3a  jnz     short loc_180034C77
0x180034c3c  call    cs:__imp_SysFreeString
0x180034c43  nop     dword ptr [rax+rax+00h]
0x180034c48  lea     rcx, [rbp+57h+var_68]
0x180034c4c  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180034c51  nop
0x180034c52  lea     rcx, [rbp+57h+var_78]
0x180034c56  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180034c5b  nop
0x180034c5c  lea     rcx, [rbp+57h+var_80]
0x180034c60  call    ?Release@?$CTSmartObj@PEAGV?$CTSmartPtr_PolicyComplete@VCTContainer_PolicyHeapMem@@@@@@QEAAXXZ; CTSmartObj<ushort *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(void)
0x180034c65  mov     ebx, 8007000Eh
0x180034c6a  lea     rcx, [rbp+57h+var_48]
0x180034c6e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034c73  mov     eax, ebx
0x180034c75  jmp     short loc_180034CE7
0x180034c77  call    cs:__imp_SysFreeString
0x180034c7e  nop     dword ptr [rax+rax+00h]
0x180034c83  mov     rdx, [rbp+57h+var_68]
0x180034c87  cmp     rdx, [rbp+57h+var_60]
0x180034c8b  jz      short loc_180034C9C
0x180034c8d  lea     rcx, [rdi+0D8h]
0x180034c94  mov     r8, r14
0x180034c97  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180034c9c  lea     rcx, [rbp+57h+var_68]
0x180034ca0  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180034ca5  mov     rax, cs:?_appStatus@CEnrollmentHelper@WorkAccess@SystemSettings@@2V_bstr_t@@A; _bstr_t SystemSettings::WorkAccess::CEnrollmentHelper::_appStatus
0x180034cac  test    rax, rax
0x180034caf  jz      short loc_180034CB6
0x180034cb1  mov     rdx, [rax]
0x180034cb4  jmp     short loc_180034CB8
0x180034cb6  xor     edx, edx
0x180034cb8  lea     rcx, [rdi+108h]
0x180034cbf  mov     r8, r14
0x180034cc2  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180034cc7  nop
0x180034cc8  lea     rcx, [rbp+57h+var_78]
0x180034ccc  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180034cd1  nop
0x180034cd2  lea     rcx, [rbp+57h+var_80]
0x180034cd6  call    ?Release@?$CTSmartObj@PEAGV?$CTSmartPtr_PolicyComplete@VCTContainer_PolicyHeapMem@@@@@@QEAAXXZ; CTSmartObj<ushort *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(void)
0x180034cdb  nop
0x180034cdc  lea     rcx, [rbp+57h+var_48]
0x180034ce0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034ce5  xor     eax, eax
0x180034ce7  mov     rcx, [rbp+57h+var_28]
0x180034ceb  xor     rcx, rsp; StackCookie
0x180034cee  call    __security_check_cookie
0x180034cf3  add     rsp, 98h
0x180034cfa  pop     r14
0x180034cfc  pop     rdi
0x180034cfd  pop     rbx
0x180034cfe  pop     rbp
0x180034cff  retn
```
