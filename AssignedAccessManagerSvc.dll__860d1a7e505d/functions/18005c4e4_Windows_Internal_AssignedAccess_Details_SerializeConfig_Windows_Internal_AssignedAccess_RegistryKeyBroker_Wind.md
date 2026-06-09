# Windows::Internal::AssignedAccess::Details::SerializeConfig<Windows::Internal::AssignedAccess::RegistryKeyBroker>(Windows::Internal::AssignedAccess::RegistryKeyBroker &,Windows::Internal::AssignedAccess::IAssignedAccessConfig *)

- ea: `0x18005c4e4`
- end: `0x18005c823`
- name: `??$SerializeConfig@VRegistryKeyBroker@AssignedAccess@Internal@Windows@@@Details@AssignedAccess@Internal@Windows@@YAJAEAVRegistryKeyBroker@123@PEAUIAssignedAccessConfig@123@@Z`
- size: `831`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18006309c`

## callees

- `0x180006640`
- `0x18000b6b4`
- `0x18000cfe4`
- `0x180010c98`
- `0x180014a5c`
- `0x18002001c`
- `0x180022d00`
- `0x18002b190`
- `0x180037454`
- `0x1800575cc`
- `0x18005c4e4`
- `0x180063058`
- `0x180063b68`
- `0x180064314`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18005c58d`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18005c58d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005c6ba`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005c6ba`

## string_xrefs

- `0x18005c6cf`: `onecoreuap\internal\base\inc\embedded\registrykey.h`
- `0x18005c67f`: `ConfigSource`
- `0x18005c53b`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005c5b1`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005c654`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005c749`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005c79f`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall Windows::Internal::AssignedAccess::Details::SerializeConfig<Windows::Internal::AssignedAccess::RegistryKeyBroker>(
        __int64 a1,
        __int64 *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  HRESULT v7; // ebx
  int v8; // eax
  unsigned int v9; // ebx
  const WCHAR *v10; // rax
  unsigned int v11; // eax
  __int64 v12; // rax
  int v13; // eax
  struct Windows::Internal::AssignedAccess::IAssignedAccessAccount *v14; // r8
  unsigned int v15; // ebx
  int v16; // eax
  unsigned int v17; // ebx
  int lpData; // [rsp+20h] [rbp-A8h]
  unsigned int lpDataa; // [rsp+20h] [rbp-A8h]
  BYTE Data[8]; // [rsp+30h] [rbp-98h] BYREF
  __int64 v21; // [rsp+38h] [rbp-90h] BYREF
  int v22; // [rsp+40h] [rbp-88h] BYREF
  struct Windows::Internal::AssignedAccess::RegistryKeyBroker *v23; // [rsp+48h] [rbp-80h] BYREF
  _BYTE v24[24]; // [rsp+50h] [rbp-78h] BYREF
  _BYTE v25[32]; // [rsp+68h] [rbp-60h] BYREF
  __int64 *v26; // [rsp+88h] [rbp-40h] BYREF
  LPOLESTR lpsz; // [rsp+90h] [rbp-38h] BYREF
  char v28; // [rsp+98h] [rbp-30h]
  IID rclsid; // [rsp+A8h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  rclsid = 0;
  v4 = (*(__int64 (__fastcall **)(__int64 *, IID *))(*a2 + 64))(a2, &rclsid);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v21 = 0;
    v26 = &v21;
    lpsz = 0;
    v28 = 1;
    v7 = StringFromCLSID(&rclsid, &lpsz);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v26);
    if ( v7 >= 0 )
    {
      std::wstring::wstring(v25, v21);
      std::wstring::wstring(&v26, L"DefaultProfileId");
      Windows::Internal::AssignedAccess::RegistryKeyBroker::SetString(a1, &v26, v25);
      std::wstring::_Tidy_deallocate(&v26);
      std::wstring::_Tidy_deallocate(v25);
      v22 = 0;
      v8 = (*(__int64 (__fastcall **)(__int64 *, int *))(*a2 + 80))(a2, &v22);
      v9 = v8;
      if ( v8 >= 0 )
      {
        *(_DWORD *)Data = v22;
        std::wstring::wstring(v25, L"ConfigSource");
        v10 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v25);
        v11 = RegSetValueExW(*(HKEY *)(a1 + 16), v10, 0, 4u, Data, 4u);
        if ( v11 )
          wil::details::in1diag3::_Throw_Win32(
            retaddr,
            (void *)0xCD,
            (unsigned int)"onecoreuap\\internal\\base\\inc\\embedded\\registrykey.h",
            (const char *)v11,
            lpDataa);
        std::wstring::_Tidy_deallocate(v25);
        std::wstring::wstring(v25, L"Account");
        Windows::Internal::AssignedAccess::RegistryKeyBroker::Create(a1, v24, v25);
        std::wstring::_Tidy_deallocate(v25);
        v12 = *a2;
        v23 = 0;
        v13 = (*(__int64 (__fastcall **)(__int64 *, struct Windows::Internal::AssignedAccess::RegistryKeyBroker **))(v12 + 48))(
                a2,
                &v23);
        v15 = v13;
        if ( v13 >= 0 )
        {
          v16 = Windows::Internal::AssignedAccess::Details::Serialize(
                  (Windows::Internal::AssignedAccess::Details *)v24,
                  v23,
                  v14);
          v17 = v16;
          if ( v16 >= 0 )
          {
            wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v23);
            Windows::Internal::AssignedAccess::RegistryKeyBroker::~RegistryKeyBroker((Windows::Internal::AssignedAccess::RegistryKeyBroker *)v24);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v21);
            return 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x132,
              (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
              (const char *)(unsigned int)v16,
              lpDataa);
            wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v23);
            Windows::Internal::AssignedAccess::RegistryKeyBroker::~RegistryKeyBroker((Windows::Internal::AssignedAccess::RegistryKeyBroker *)v24);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v21);
            return v17;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x131,
            (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
            (const char *)(unsigned int)v13,
            lpDataa);
          wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v23);
          Windows::Internal::AssignedAccess::RegistryKeyBroker::~RegistryKeyBroker((Windows::Internal::AssignedAccess::RegistryKeyBroker *)v24);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v21);
          return v15;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x12C,
          (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
          (const char *)(unsigned int)v8,
          lpData);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v21);
        return v9;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x128,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
        (const char *)(unsigned int)v7,
        lpData);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v21);
      return (unsigned int)v7;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x126,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
      (const char *)(unsigned int)v4,
      lpData);
    return v5;
  }
}

```

## disassembly

```asm
0x18005c4e4  mov     r11, rsp
0x18005c4e7  mov     [r11+18h], rbx
0x18005c4eb  mov     [r11+20h], rsi
0x18005c4ef  push    rdi
0x18005c4f0  sub     rsp, 0C0h
0x18005c4f7  mov     rax, cs:__security_cookie
0x18005c4fe  xor     rax, rsp
0x18005c501  mov     [rsp+0C8h+var_10], rax
0x18005c509  mov     rdi, rdx
0x18005c50c  mov     rsi, rcx
0x18005c50f  xorps   xmm0, xmm0
0x18005c512  movups  xmmword ptr [r11-20h], xmm0
0x18005c517  mov     rax, [rdx]
0x18005c51a  lea     rdx, [r11-20h]
0x18005c51e  mov     rcx, rdi
0x18005c521  mov     rax, [rax+40h]
0x18005c525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c52a  mov     ebx, eax
0x18005c52c  test    eax, eax
0x18005c52e  jns     short loc_18005C553
0x18005c530  mov     rcx, [rsp+0C8h]; this
0x18005c538  mov     r9d, eax; char *
0x18005c53b  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005c542  mov     edx, 126h; void *
0x18005c547  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c54c  mov     eax, ebx
0x18005c54e  jmp     loc_18005C7FD
0x18005c553  mov     [rsp+0C8h+var_90], 0
0x18005c55c  lea     rax, [rsp+0C8h+var_90]
0x18005c561  mov     [rsp+0C8h+var_40], rax
0x18005c569  mov     [rsp+0C8h+lpsz], 0
0x18005c575  mov     [rsp+0C8h+var_30], 1
0x18005c57d  lea     rdx, [rsp+0C8h+lpsz]; lplpsz
0x18005c585  lea     rcx, [rsp+0C8h+rclsid]; rclsid
0x18005c58d  call    cs:__imp_StringFromCLSID
0x18005c593  mov     ebx, eax
0x18005c595  lea     rcx, [rsp+0C8h+var_40]
0x18005c59d  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18005c5a2  test    ebx, ebx
0x18005c5a4  jns     short loc_18005C5D4
0x18005c5a6  mov     rcx, [rsp+0C8h]; this
0x18005c5ae  mov     r9d, ebx; char *
0x18005c5b1  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005c5b8  mov     edx, 128h; void *
0x18005c5bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c5c2  nop
0x18005c5c3  lea     rcx, [rsp+0C8h+var_90]
0x18005c5c8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005c5cd  mov     eax, ebx
0x18005c5cf  jmp     loc_18005C7FD
0x18005c5d4  mov     rdx, [rsp+0C8h+var_90]
0x18005c5d9  lea     rcx, [rsp+0C8h+var_60]
0x18005c5de  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005c5e3  nop
0x18005c5e4  lea     rdx, aDefaultprofile; "DefaultProfileId"
0x18005c5eb  lea     rcx, [rsp+0C8h+var_40]
0x18005c5f3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005c5f8  nop
0x18005c5f9  lea     r8, [rsp+0C8h+var_60]
0x18005c5fe  lea     rdx, [rsp+0C8h+var_40]
0x18005c606  mov     rcx, rsi
0x18005c609  call    ?SetString@RegistryKeyBroker@AssignedAccess@Internal@Windows@@QEBAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Windows::Internal::AssignedAccess::RegistryKeyBroker::SetString(std::wstring const &,std::wstring const &)
0x18005c60e  nop
0x18005c60f  lea     rcx, [rsp+0C8h+var_40]
0x18005c617  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005c61c  nop
0x18005c61d  lea     rcx, [rsp+0C8h+var_60]
0x18005c622  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005c627  mov     [rsp+0C8h+var_88], 0
0x18005c62f  mov     rax, [rdi]
0x18005c632  lea     rdx, [rsp+0C8h+var_88]
0x18005c637  mov     rcx, rdi
0x18005c63a  mov     rax, [rax+50h]
0x18005c63e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c643  mov     ebx, eax
0x18005c645  test    eax, eax
0x18005c647  jns     short loc_18005C677
0x18005c649  mov     rcx, [rsp+0C8h]; this
0x18005c651  mov     r9d, eax; char *
0x18005c654  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005c65b  mov     edx, 12Ch; void *
0x18005c660  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c665  nop
0x18005c666  lea     rcx, [rsp+0C8h+var_90]
0x18005c66b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005c670  mov     eax, ebx
0x18005c672  jmp     loc_18005C7FD
0x18005c677  mov     eax, [rsp+0C8h+var_88]
0x18005c67b  mov     dword ptr [rsp+0C8h+Data], eax
0x18005c67f  lea     rdx, aConfigsource; "ConfigSource"
0x18005c686  lea     rcx, [rsp+0C8h+var_60]
0x18005c68b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005c690  nop
0x18005c691  lea     rcx, [rsp+0C8h+var_60]
0x18005c696  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005c69b  mov     rdx, rax; lpValueName
0x18005c69e  mov     r9d, 4; dwType
0x18005c6a4  mov     [rsp+0C8h+cbData], r9d; cbData
0x18005c6a9  lea     rax, [rsp+0C8h+Data]
0x18005c6ae  mov     [rsp+0C8h+lpData], rax; int
0x18005c6b3  xor     r8d, r8d; Reserved
0x18005c6b6  mov     rcx, [rsi+10h]; hKey
0x18005c6ba  call    cs:__imp_RegSetValueExW
0x18005c6c0  mov     rcx, [rsp+0C8h]; this
0x18005c6c8  test    eax, eax
0x18005c6ca  jz      short loc_18005C6E1
0x18005c6cc  mov     r9d, eax; char *
0x18005c6cf  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\base\\inc\\embedd"...
0x18005c6d6  mov     edx, 0CDh; void *
0x18005c6db  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18005c6e1  lea     rcx, [rsp+0C8h+var_60]
0x18005c6e6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005c6eb  lea     rdx, aAccount; "Account"
0x18005c6f2  lea     rcx, [rsp+0C8h+var_60]
0x18005c6f7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005c6fc  nop
0x18005c6fd  lea     r8, [rsp+0C8h+var_60]
0x18005c702  lea     rdx, [rsp+0C8h+var_78]
0x18005c707  mov     rcx, rsi
0x18005c70a  call    ?Create@RegistryKeyBroker@AssignedAccess@Internal@Windows@@QEAA?AV1234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KK@Z; Windows::Internal::AssignedAccess::RegistryKeyBroker::Create(std::wstring const &,ulong,ulong)
0x18005c70f  nop
0x18005c710  lea     rcx, [rsp+0C8h+var_60]
0x18005c715  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005c71a  nop
0x18005c71b  mov     rax, [rdi]
0x18005c71e  mov     [rsp+0C8h+var_80], 0
0x18005c727  lea     rdx, [rsp+0C8h+var_80]
0x18005c72c  mov     rcx, rdi
0x18005c72f  mov     rax, [rax+30h]
0x18005c733  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c738  mov     ebx, eax
0x18005c73a  test    eax, eax
0x18005c73c  jns     short loc_18005C77F
0x18005c73e  mov     rcx, [rsp+0C8h]; this
0x18005c746  mov     r9d, eax; char *
0x18005c749  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005c750  mov     edx, 131h; void *
0x18005c755  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c75a  nop
0x18005c75b  lea     rcx, [rsp+0C8h+var_80]
0x18005c760  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18005c765  nop
0x18005c766  lea     rcx, [rsp+0C8h+var_78]; this
0x18005c76b  call    ??1RegistryKeyBroker@AssignedAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::AssignedAccess::RegistryKeyBroker::~RegistryKeyBroker(void)
0x18005c770  nop
0x18005c771  lea     rcx, [rsp+0C8h+var_90]
0x18005c776  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005c77b  mov     eax, ebx
0x18005c77d  jmp     short loc_18005C7FD
0x18005c77f  mov     rdx, [rsp+0C8h+var_80]; struct Windows::Internal::AssignedAccess::RegistryKeyBroker *
0x18005c784  lea     rcx, [rsp+0C8h+var_78]; this
0x18005c789  call    ?Serialize@Details@AssignedAccess@Internal@Windows@@YAJAEAVRegistryKeyBroker@234@PEAUIAssignedAccessAccount@234@@Z; Windows::Internal::AssignedAccess::Details::Serialize(Windows::Internal::AssignedAccess::RegistryKeyBroker &,Windows::Internal::AssignedAccess::IAssignedAccessAccount *)
0x18005c78e  mov     ebx, eax
0x18005c790  test    eax, eax
0x18005c792  jns     short loc_18005C7D5
0x18005c794  mov     rcx, [rsp+0C8h]; this
0x18005c79c  mov     r9d, eax; char *
0x18005c79f  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005c7a6  mov     edx, 132h; void *
0x18005c7ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c7b0  nop
0x18005c7b1  lea     rcx, [rsp+0C8h+var_80]
0x18005c7b6  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18005c7bb  nop
0x18005c7bc  lea     rcx, [rsp+0C8h+var_78]; this
0x18005c7c1  call    ??1RegistryKeyBroker@AssignedAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::AssignedAccess::RegistryKeyBroker::~RegistryKeyBroker(void)
0x18005c7c6  nop
0x18005c7c7  lea     rcx, [rsp+0C8h+var_90]
0x18005c7cc  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005c7d1  mov     eax, ebx
0x18005c7d3  jmp     short loc_18005C7FD
0x18005c7d5  lea     rcx, [rsp+0C8h+var_80]
0x18005c7da  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18005c7df  nop
0x18005c7e0  lea     rcx, [rsp+0C8h+var_78]; this
0x18005c7e5  call    ??1RegistryKeyBroker@AssignedAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::AssignedAccess::RegistryKeyBroker::~RegistryKeyBroker(void)
0x18005c7ea  nop
0x18005c7eb  lea     rcx, [rsp+0C8h+var_90]
0x18005c7f0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005c7f5  xor     eax, eax
0x18005c7f7  jmp     short loc_18005C7FD
0x18005c7f9  mov     eax, dword ptr [rsp+0C8h+Data]
0x18005c7fd  mov     rcx, [rsp+0C8h+var_10]
0x18005c805  xor     rcx, rsp; StackCookie
0x18005c808  call    __security_check_cookie
0x18005c80d  lea     r11, [rsp+0C8h+var_8]
0x18005c815  mov     rbx, [r11+20h]
0x18005c819  mov     rsi, [r11+28h]
0x18005c81d  mov     rsp, r11
0x18005c820  pop     rdi
0x18005c821  retn
```
