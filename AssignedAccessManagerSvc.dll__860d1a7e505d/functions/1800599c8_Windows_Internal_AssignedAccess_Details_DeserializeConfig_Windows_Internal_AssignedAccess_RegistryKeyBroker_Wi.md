# Windows::Internal::AssignedAccess::Details::DeserializeConfig<Windows::Internal::AssignedAccess::RegistryKeyBroker>(Windows::Internal::AssignedAccess::RegistryKeyBroker &,ulong,Windows::Internal::AssignedAccess::IAssignedAccessConfig * *)

- ea: `0x1800599c8`
- end: `0x180059c6f`
- name: `??$DeserializeConfig@VRegistryKeyBroker@AssignedAccess@Internal@Windows@@@Details@AssignedAccess@Internal@Windows@@YAJAEAVRegistryKeyBroker@123@KPEAPEAUIAssignedAccessConfig@123@@Z`
- size: `679`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18005fa48`

## callees

- `0x180006640`
- `0x18000b6b4`
- `0x18000cfe4`
- `0x180010c98`
- `0x180014a5c`
- `0x18002001c`
- `0x18002249c`
- `0x1800575cc`
- `0x1800599c8`
- `0x18005b3b0`
- `0x18005fa04`
- `0x1800608cc`
- `0x1800616a0`
- `0x1800644d8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180059a49`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180059a49`

## string_xrefs

- `0x180059a83`: `ConfigSource`
- `0x180059a60`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x180059b1c`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x180059bc8`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
__int64 __fastcall Windows::Internal::AssignedAccess::Details::DeserializeConfig<Windows::Internal::AssignedAccess::RegistryKeyBroker>(
        __int64 a1,
        unsigned int a2,
        _QWORD *a3)
{
  const OLECHAR *v6; // rax
  HRESULT v7; // eax
  unsigned int v8; // edi
  int DWORD; // edi
  struct Windows::Internal::AssignedAccess::IAssignedAccessAccount **v11; // r9
  int v12; // eax
  unsigned int v13; // ebx
  int v14; // eax
  unsigned int v15; // ebx
  int v16; // [rsp+20h] [rbp-D8h]
  int v17; // [rsp+30h] [rbp-C8h] BYREF
  unsigned int v18[2]; // [rsp+38h] [rbp-C0h] BYREF
  __int64 v19; // [rsp+40h] [rbp-B8h] BYREF
  __int64 v20; // [rsp+48h] [rbp-B0h] BYREF
  _BYTE v21[24]; // [rsp+50h] [rbp-A8h] BYREF
  _BYTE v22[32]; // [rsp+68h] [rbp-90h] BYREF
  GUID pclsid; // [rsp+88h] [rbp-70h] BYREF
  _BYTE v24[32]; // [rsp+98h] [rbp-60h] BYREF
  _BYTE v25[32]; // [rsp+B8h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  std::wstring::wstring(v25, L"DefaultProfileId");
  Windows::Internal::AssignedAccess::RegistryKeyBroker::GetString(a1, v22, v25);
  std::wstring::_Tidy_deallocate(v25);
  pclsid = 0;
  v6 = (const OLECHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v22);
  v7 = CLSIDFromString(v6, &pclsid);
  v8 = v7;
  if ( v7 >= 0 )
  {
    std::wstring::wstring(v24, L"ConfigSource");
    DWORD = Windows::Internal::AssignedAccess::RegistryKeyBroker::GetDWORD(a1, v24);
    std::wstring::_Tidy_deallocate(v24);
    std::wstring::wstring(v24, L"Account");
    Windows::Internal::AssignedAccess::RegistryKeyBroker::Open(a1, v21, v24);
    std::wstring::_Tidy_deallocate(v24);
    *(_QWORD *)v18 = 0;
    v12 = Windows::Internal::AssignedAccess::Details::Deserialize(
            (Windows::Internal::AssignedAccess::Details *)v21,
            (struct Windows::Internal::AssignedAccess::RegistryKeyBroker *)a2,
            (unsigned int)v18,
            v11);
    v13 = v12;
    if ( v12 >= 0 )
    {
      if ( *(_QWORD *)v18 )
      {
        v17 = DWORD;
        v20 = *(_QWORD *)v18;
        v19 = 0;
        v14 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::AssignedAccessConfig,Windows::Internal::AssignedAccess::IAssignedAccessConfig,Windows::Internal::AssignedAccess::IAssignedAccessAccount *,_GUID &,enum Windows::Internal::AssignedAccess::ConfigSource &>(
                &v19,
                &v20,
                &pclsid,
                &v17);
        v15 = v14;
        if ( v14 >= 0 )
        {
          wil::com_ptr_t<Windows::Internal::AssignedAccess::IProfileOperation,wil::err_exception_policy>::copy_to<Windows::Internal::AssignedAccess::IProfileOperation>(
            &v19,
            a3);
          wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v19);
          wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(v18);
          Windows::Internal::AssignedAccess::RegistryKeyBroker::~RegistryKeyBroker((Windows::Internal::AssignedAccess::RegistryKeyBroker *)v21);
          std::wstring::_Tidy_deallocate(v22);
          return 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x149,
            (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
            (const char *)(unsigned int)v14,
            v16);
          wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v19);
          wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(v18);
          Windows::Internal::AssignedAccess::RegistryKeyBroker::~RegistryKeyBroker((Windows::Internal::AssignedAccess::RegistryKeyBroker *)v21);
          std::wstring::_Tidy_deallocate(v22);
          return v15;
        }
      }
      else
      {
        *a3 = 0;
        wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(v18);
        Windows::Internal::AssignedAccess::RegistryKeyBroker::~RegistryKeyBroker((Windows::Internal::AssignedAccess::RegistryKeyBroker *)v21);
        std::wstring::_Tidy_deallocate(v22);
        return 0;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x141,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
        (const char *)(unsigned int)v12,
        v16);
      wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(v18);
      Windows::Internal::AssignedAccess::RegistryKeyBroker::~RegistryKeyBroker((Windows::Internal::AssignedAccess::RegistryKeyBroker *)v21);
      std::wstring::_Tidy_deallocate(v22);
      return v13;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13C,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
      (const char *)(unsigned int)v7,
      v16);
    std::wstring::_Tidy_deallocate(v22);
    return v8;
  }
}

```

## disassembly

```asm
0x1800599c8  mov     r11, rsp
0x1800599cb  mov     [r11+20h], rbx
0x1800599cf  push    rsi
0x1800599d0  push    rdi
0x1800599d1  push    r14
0x1800599d3  sub     rsp, 0E0h
0x1800599da  mov     rax, cs:__security_cookie
0x1800599e1  xor     rax, rsp
0x1800599e4  mov     [rsp+0F8h+var_20], rax
0x1800599ec  mov     rsi, r8
0x1800599ef  mov     r14d, edx
0x1800599f2  mov     rbx, rcx
0x1800599f5  lea     rdx, aDefaultprofile; "DefaultProfileId"
0x1800599fc  lea     rcx, [r11-40h]
0x180059a00  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180059a05  nop
0x180059a06  lea     r8, [rsp+0F8h+var_40]
0x180059a0e  lea     rdx, [rsp+0F8h+var_90]
0x180059a13  mov     rcx, rbx
0x180059a16  call    ?GetString@RegistryKeyBroker@AssignedAccess@Internal@Windows@@QEBA?BV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV56@_N@Z; Windows::Internal::AssignedAccess::RegistryKeyBroker::GetString(std::wstring const &,bool)
0x180059a1b  nop
0x180059a1c  lea     rcx, [rsp+0F8h+var_40]
0x180059a24  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180059a29  xorps   xmm0, xmm0
0x180059a2c  movups  xmmword ptr [rsp+0F8h+pclsid.Data1], xmm0
0x180059a34  lea     rcx, [rsp+0F8h+var_90]
0x180059a39  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180059a3e  mov     rcx, rax; lpsz
0x180059a41  lea     rdx, [rsp+0F8h+pclsid]; pclsid
0x180059a49  call    cs:__imp_CLSIDFromString
0x180059a4f  mov     edi, eax
0x180059a51  test    eax, eax
0x180059a53  jns     short loc_180059A83
0x180059a55  mov     rcx, [rsp+0F8h]; this
0x180059a5d  mov     r9d, eax; char *
0x180059a60  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180059a67  mov     edx, 13Ch; void *
0x180059a6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059a71  nop
0x180059a72  lea     rcx, [rsp+0F8h+var_90]
0x180059a77  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180059a7c  mov     eax, edi
0x180059a7e  jmp     loc_180059C4A
0x180059a83  lea     rdx, aConfigsource; "ConfigSource"
0x180059a8a  lea     rcx, [rsp+0F8h+var_60]
0x180059a92  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180059a97  nop
0x180059a98  lea     rdx, [rsp+0F8h+var_60]
0x180059aa0  mov     rcx, rbx
0x180059aa3  call    ?GetDWORD@RegistryKeyBroker@AssignedAccess@Internal@Windows@@QEBA?BKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; Windows::Internal::AssignedAccess::RegistryKeyBroker::GetDWORD(std::wstring const &,bool)
0x180059aa8  mov     edi, eax
0x180059aaa  lea     rcx, [rsp+0F8h+var_60]
0x180059ab2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180059ab7  lea     rdx, aAccount; "Account"
0x180059abe  lea     rcx, [rsp+0F8h+var_60]
0x180059ac6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180059acb  nop
0x180059acc  lea     r8, [rsp+0F8h+var_60]
0x180059ad4  lea     rdx, [rsp+0F8h+var_A8]
0x180059ad9  mov     rcx, rbx
0x180059adc  call    ?Open@RegistryKeyBroker@AssignedAccess@Internal@Windows@@QEAA?AV1234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KK@Z; Windows::Internal::AssignedAccess::RegistryKeyBroker::Open(std::wstring const &,ulong,ulong)
0x180059ae1  nop
0x180059ae2  lea     rcx, [rsp+0F8h+var_60]
0x180059aea  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180059aef  nop
0x180059af0  mov     qword ptr [rsp+0F8h+var_C0], 0
0x180059af9  lea     r8, [rsp+0F8h+var_C0]; unsigned int
0x180059afe  mov     edx, r14d; struct Windows::Internal::AssignedAccess::RegistryKeyBroker *
0x180059b01  lea     rcx, [rsp+0F8h+var_A8]; this
0x180059b06  call    ?Deserialize@Details@AssignedAccess@Internal@Windows@@YAJAEAVRegistryKeyBroker@234@KPEAPEAUIAssignedAccessAccount@234@@Z; Windows::Internal::AssignedAccess::Details::Deserialize(Windows::Internal::AssignedAccess::RegistryKeyBroker &,ulong,Windows::Internal::AssignedAccess::IAssignedAccessAccount * *)
0x180059b0b  mov     ebx, eax
0x180059b0d  test    eax, eax
0x180059b0f  jns     short loc_180059B55
0x180059b11  mov     rcx, [rsp+0F8h]; this
0x180059b19  mov     r9d, eax; char *
0x180059b1c  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180059b23  mov     edx, 141h; void *
0x180059b28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059b2d  nop
0x180059b2e  lea     rcx, [rsp+0F8h+var_C0]
0x180059b33  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180059b38  nop
0x180059b39  lea     rcx, [rsp+0F8h+var_A8]; this
0x180059b3e  call    ??1RegistryKeyBroker@AssignedAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::AssignedAccess::RegistryKeyBroker::~RegistryKeyBroker(void)
0x180059b43  nop
0x180059b44  lea     rcx, [rsp+0F8h+var_90]
0x180059b49  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180059b4e  mov     eax, ebx
0x180059b50  jmp     loc_180059C4A
0x180059b55  mov     rax, qword ptr [rsp+0F8h+var_C0]
0x180059b5a  test    rax, rax
0x180059b5d  jnz     short loc_180059B89
0x180059b5f  mov     [rsi], rax
0x180059b62  lea     rcx, [rsp+0F8h+var_C0]
0x180059b67  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180059b6c  nop
0x180059b6d  lea     rcx, [rsp+0F8h+var_A8]; this
0x180059b72  call    ??1RegistryKeyBroker@AssignedAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::AssignedAccess::RegistryKeyBroker::~RegistryKeyBroker(void)
0x180059b77  nop
0x180059b78  lea     rcx, [rsp+0F8h+var_90]
0x180059b7d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180059b82  xor     eax, eax
0x180059b84  jmp     loc_180059C4A
0x180059b89  mov     [rsp+0F8h+var_C8], edi
0x180059b8d  mov     [rsp+0F8h+var_B0], rax
0x180059b92  mov     [rsp+0F8h+var_B8], 0
0x180059b9b  lea     r9, [rsp+0F8h+var_C8]
0x180059ba0  lea     r8, [rsp+0F8h+pclsid]
0x180059ba8  lea     rdx, [rsp+0F8h+var_B0]
0x180059bad  lea     rcx, [rsp+0F8h+var_B8]
0x180059bb2  call    ??$MakeAndInitialize@VAssignedAccessConfig@AssignedAccess@Internal@Windows@@UIAssignedAccessConfig@234@PEAUIAssignedAccessAccount@234@AEAU_GUID@@AEAW4ConfigSource@234@@Details@WRL@Microsoft@@YAJPEAPEAUIAssignedAccessConfig@AssignedAccess@Internal@Windows@@$$QEAPEAUIAssignedAccessAccount@456@AEAU_GUID@@AEAW4ConfigSource@456@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::AssignedAccessConfig,Windows::Internal::AssignedAccess::IAssignedAccessConfig,Windows::Internal::AssignedAccess::IAssignedAccessAccount *,_GUID &,Windows::Internal::AssignedAccess::ConfigSource &>(Windows::Internal::AssignedAccess::IAssignedAccessConfig * *,Windows::Internal::AssignedAccess::IAssignedAccessAccount * &&,_GUID &,Windows::Internal::AssignedAccess::ConfigSource &)
0x180059bb7  mov     ebx, eax
0x180059bb9  test    eax, eax
0x180059bbb  jns     short loc_180059C09
0x180059bbd  mov     rcx, [rsp+0F8h]; this
0x180059bc5  mov     r9d, eax; char *
0x180059bc8  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180059bcf  mov     edx, 149h; void *
0x180059bd4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059bd9  nop
0x180059bda  lea     rcx, [rsp+0F8h+var_B8]
0x180059bdf  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180059be4  nop
0x180059be5  lea     rcx, [rsp+0F8h+var_C0]
0x180059bea  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180059bef  nop
0x180059bf0  lea     rcx, [rsp+0F8h+var_A8]; this
0x180059bf5  call    ??1RegistryKeyBroker@AssignedAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::AssignedAccess::RegistryKeyBroker::~RegistryKeyBroker(void)
0x180059bfa  nop
0x180059bfb  lea     rcx, [rsp+0F8h+var_90]
0x180059c00  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180059c05  mov     eax, ebx
0x180059c07  jmp     short loc_180059C4A
0x180059c09  mov     rdx, rsi
0x180059c0c  lea     rcx, [rsp+0F8h+var_B8]
0x180059c11  call    ??$copy_to@UIProfileOperation@AssignedAccess@Internal@Windows@@@?$com_ptr_t@UIProfileOperation@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEBAXPEAPEAUIProfileOperation@AssignedAccess@Internal@Windows@@@Z; wil::com_ptr_t<Windows::Internal::AssignedAccess::IProfileOperation,wil::err_exception_policy>::copy_to<Windows::Internal::AssignedAccess::IProfileOperation>(Windows::Internal::AssignedAccess::IProfileOperation * *)
0x180059c16  nop
0x180059c17  lea     rcx, [rsp+0F8h+var_B8]
0x180059c1c  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180059c21  nop
0x180059c22  lea     rcx, [rsp+0F8h+var_C0]
0x180059c27  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180059c2c  nop
0x180059c2d  lea     rcx, [rsp+0F8h+var_A8]; this
0x180059c32  call    ??1RegistryKeyBroker@AssignedAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::AssignedAccess::RegistryKeyBroker::~RegistryKeyBroker(void)
0x180059c37  nop
0x180059c38  lea     rcx, [rsp+0F8h+var_90]
0x180059c3d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180059c42  xor     eax, eax
0x180059c44  jmp     short loc_180059C4A
0x180059c46  mov     eax, [rsp+0F8h+var_C8]
0x180059c4a  mov     rcx, [rsp+0F8h+var_20]
0x180059c52  xor     rcx, rsp; StackCookie
0x180059c55  call    __security_check_cookie
0x180059c5a  mov     rbx, [rsp+0F8h+arg_18]
0x180059c62  add     rsp, 0E0h
0x180059c69  pop     r14
0x180059c6b  pop     rdi
0x180059c6c  pop     rsi
0x180059c6d  retn
```
