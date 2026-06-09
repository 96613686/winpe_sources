# Windows::Internal::AssignedAccess::RegistryDataStoreV1Impl::DeserializeGlobalProfile(std::vector<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessConfig,wil::err_exception_policy>,std::allocator<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessConfig,wil::err_exception_policy>>> &)

- ea: `0x180065c90`
- end: `0x180065f60`
- name: `?DeserializeGlobalProfile@RegistryDataStoreV1Impl@AssignedAccess@Internal@Windows@@AEAAXAEAV?$vector@V?$com_ptr_t@UIAssignedAccessConfig@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIAssignedAccessConfig@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@Z`
- size: `720`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180066340`

## callees

- `0x180006640`
- `0x18000cfe4`
- `0x18000e760`
- `0x18000f62c`
- `0x180010c98`
- `0x180014a5c`
- `0x18002001c`
- `0x180020050`
- `0x1800575cc`
- `0x18005b3b0`
- `0x1800608cc`
- `0x180063ba4`
- `0x180063be0`
- `0x1800645d0`
- `0x18006469c`
- `0x180064b5c`
- `0x180064c18`
- `0x180065c90`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180065d41`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180065d41`

## string_xrefs

- `0x180065d1f`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registrydatastorev1impl.cpp`
- `0x180065d52`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registrydatastorev1impl.cpp`
- `0x180065d8b`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registrydatastorev1impl.cpp`
- `0x180065df8`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registrydatastorev1impl.cpp`
- `0x180065e57`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registrydatastorev1impl.cpp`
- `0x180065f17`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registrydatastorev1impl.cpp`
- `0x180065f4e`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registrydatastorev1impl.cpp`
- `0x180065d9d`: `GlobalProfileConfigSource`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall Windows::Internal::AssignedAccess::RegistryDataStoreV1Impl::DeserializeGlobalProfile(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r8
  int String; // ebx
  const OLECHAR *v8; // rax
  HRESULT v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // r8d
  int v13; // r9d
  int v14; // ebx
  __int64 v15; // r8
  int v16; // ebx
  __int64 v17; // rdx
  int v18; // eax
  int v19; // [rsp+20h] [rbp-69h]
  int v20; // [rsp+20h] [rbp-69h]
  unsigned int DWORD; // [rsp+30h] [rbp-59h] BYREF
  __int64 v22; // [rsp+38h] [rbp-51h] BYREF
  __int64 v23; // [rsp+40h] [rbp-49h] BYREF
  __int64 v24; // [rsp+48h] [rbp-41h] BYREF
  _BYTE v25[24]; // [rsp+50h] [rbp-39h] BYREF
  int v26[4]; // [rsp+68h] [rbp-21h] BYREF
  __int64 v27; // [rsp+78h] [rbp-11h]
  GUID pclsid; // [rsp+88h] [rbp-1h] BYREF
  _BYTE v29[32]; // [rsp+98h] [rbp+Fh] BYREF
  _BYTE v30[32]; // [rsp+B8h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  pclsid = 0;
  Windows::Internal::AssignedAccess::RegistryKeyBroker::Open(*(_QWORD *)(a1 + 8), v25, a3, a1 + 80);
  std::wstring::wstring(v30, v4, v5);
  std::wstring::wstring(v26, L"GlobalProfileId");
  String = Windows::Internal::AssignedAccess::RegistryKeyBroker::TryGetString(v25, v26, v6, v30);
  std::wstring::_Tidy_deallocate(v26);
  if ( String != -2147024894 )
  {
    if ( String < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x24C,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registrydatastorev1impl.cpp",
        (const char *)(unsigned int)String,
        v19);
    v8 = (const OLECHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v30);
    v9 = CLSIDFromString(v8, &pclsid);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x24E,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registrydatastorev1impl.cpp",
        (const char *)(unsigned int)v9,
        v19);
    DWORD = 300;
    v23 = 0;
    v10 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::AssignedAccessAccount,Windows::Internal::AssignedAccess::IAssignedAccessAccount,enum Windows::Internal::AssignedAccess::AccountType>(
            &v23,
            &DWORD);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x250,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registrydatastorev1impl.cpp",
        (const char *)(unsigned int)v10,
        v19);
    std::wstring::wstring(v26, L"GlobalProfileConfigSource");
    DWORD = Windows::Internal::AssignedAccess::RegistryKeyBroker::GetDWORD(v25, v26);
    std::wstring::_Tidy_deallocate(v26);
    v24 = v23;
    v22 = 0;
    v11 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::AssignedAccessConfig,Windows::Internal::AssignedAccess::IAssignedAccessConfig,Windows::Internal::AssignedAccess::IAssignedAccessAccount *,_GUID &,enum Windows::Internal::AssignedAccess::ConfigSource &>(
            &v22,
            &v24,
            &pclsid,
            &DWORD);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x253,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registrydatastorev1impl.cpp",
        (const char *)(unsigned int)v11,
        v19);
    *(_OWORD *)v26 = 0;
    v27 = 0;
    std::wstring::wstring(v29, L"GlobalProfileExclusions");
    v14 = Windows::Internal::AssignedAccess::RegistryKeyBroker::TryOpen(
            (unsigned int)v25,
            (unsigned int)v29,
            v12,
            v13,
            (__int64)v26);
    std::wstring::_Tidy_deallocate(v29);
    if ( v14 >= 0 )
    {
      DWORD = 0;
      std::wstring::wstring(v29, L"DeviceOwners");
      v16 = Windows::Internal::AssignedAccess::RegistryKeyBroker::TryGetDWORD(v26, v29, v15, &DWORD);
      std::wstring::_Tidy_deallocate(v29);
      if ( v16 == -2147024894 )
      {
        v17 = 0;
        v16 = 0;
      }
      else
      {
        v17 = DWORD;
      }
      if ( v16 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x260,
          (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registrydatastorev1impl.cpp",
          (const char *)(unsigned int)v16,
          v20);
      LOBYTE(v17) = (_DWORD)v17 == 1;
      v18 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v22 + 104LL))(v22, v17);
      if ( v18 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x262,
          (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registrydatastorev1impl.cpp",
          (const char *)(unsigned int)v18,
          v20);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x257,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registrydatastorev1impl.cpp",
        (const char *)(unsigned int)v14,
        v20);
    }
    std::vector<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessConfig,wil::err_exception_policy>>::_Emplace_one_at_back<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessConfig,wil::err_exception_policy> const &>(
      a2,
      &v22);
    Windows::Internal::AssignedAccess::RegistryKeyBroker::~RegistryKeyBroker((Windows::Internal::AssignedAccess::RegistryKeyBroker *)v26);
    wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v22);
    wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v23);
  }
  std::wstring::_Tidy_deallocate(v30);
  Windows::Internal::AssignedAccess::RegistryKeyBroker::~RegistryKeyBroker((Windows::Internal::AssignedAccess::RegistryKeyBroker *)v25);
}

```

## disassembly

```asm
0x180065c90  mov     [rsp-8+arg_10], rbx
0x180065c95  mov     [rsp-8+arg_18], rdi
0x180065c9a  push    rbp
0x180065c9b  lea     rbp, [rsp-57h]
0x180065ca0  sub     rsp, 0E0h
0x180065ca7  mov     rax, cs:__security_cookie
0x180065cae  xor     rax, rsp
0x180065cb1  mov     [rbp+57h+var_8], rax
0x180065cb5  mov     rdi, rdx
0x180065cb8  xorps   xmm0, xmm0
0x180065cbb  movups  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x180065cbf  lea     r9, [rcx+50h]
0x180065cc3  lea     rdx, [rbp+57h+var_90]
0x180065cc7  mov     rcx, [rcx+8]
0x180065ccb  call    ?Open@RegistryKeyBroker@AssignedAccess@Internal@Windows@@QEAA?AV1234@PEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KK@Z; Windows::Internal::AssignedAccess::RegistryKeyBroker::Open(HKEY__ *,std::wstring const &,ulong,ulong)
0x180065cd0  nop
0x180065cd1  lea     rcx, [rbp+57h+var_28]
0x180065cd5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180065cda  nop
0x180065cdb  lea     rdx, aGlobalprofilei; "GlobalProfileId"
0x180065ce2  lea     rcx, [rbp+57h+var_78]
0x180065ce6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180065ceb  nop
0x180065cec  lea     r9, [rbp+57h+var_28]
0x180065cf0  lea     rdx, [rbp+57h+var_78]
0x180065cf4  lea     rcx, [rbp+57h+var_90]
0x180065cf8  call    ?TryGetString@RegistryKeyBroker@AssignedAccess@Internal@Windows@@QEBAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NAEAV56@@Z; Windows::Internal::AssignedAccess::RegistryKeyBroker::TryGetString(std::wstring const &,bool,std::wstring &)
0x180065cfd  mov     ebx, eax
0x180065cff  lea     rcx, [rbp+57h+var_78]
0x180065d03  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180065d08  cmp     ebx, 80070002h
0x180065d0e  jz      loc_180065E93
0x180065d14  mov     rcx, [rbp+5Fh]; this
0x180065d18  test    ebx, ebx
0x180065d1a  jns     short loc_180065D31
0x180065d1c  mov     r9d, ebx; char *
0x180065d1f  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180065d26  mov     edx, 24Ch; void *
0x180065d2b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180065d31  lea     rcx, [rbp+57h+var_28]
0x180065d35  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180065d3a  mov     rcx, rax; lpsz
0x180065d3d  lea     rdx, [rbp+57h+pclsid]; pclsid
0x180065d41  call    cs:__imp_CLSIDFromString
0x180065d47  mov     rcx, [rbp+5Fh]; this
0x180065d4b  test    eax, eax
0x180065d4d  jns     short loc_180065D64
0x180065d4f  mov     r9d, eax; char *
0x180065d52  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180065d59  mov     edx, 24Eh; void *
0x180065d5e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180065d64  mov     [rbp+57h+var_B0], 12Ch
0x180065d6b  mov     [rbp+57h+var_A0], 0
0x180065d73  lea     rdx, [rbp+57h+var_B0]
0x180065d77  lea     rcx, [rbp+57h+var_A0]
0x180065d7b  call    ??$MakeAndInitialize@VAssignedAccessAccount@AssignedAccess@Internal@Windows@@UIAssignedAccessAccount@234@W4AccountType@234@@Details@WRL@Microsoft@@YAJPEAPEAUIAssignedAccessAccount@AssignedAccess@Internal@Windows@@$$QEAW4AccountType@456@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::AssignedAccessAccount,Windows::Internal::AssignedAccess::IAssignedAccessAccount,Windows::Internal::AssignedAccess::AccountType>(Windows::Internal::AssignedAccess::IAssignedAccessAccount * *,Windows::Internal::AssignedAccess::AccountType &&)
0x180065d80  mov     rcx, [rbp+5Fh]; this
0x180065d84  test    eax, eax
0x180065d86  jns     short loc_180065D9D
0x180065d88  mov     r9d, eax; char *
0x180065d8b  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180065d92  mov     edx, 250h; void *
0x180065d97  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180065d9d  lea     rdx, aGlobalprofilec; "GlobalProfileConfigSource"
0x180065da4  lea     rcx, [rbp+57h+var_78]
0x180065da8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180065dad  nop
0x180065dae  lea     rdx, [rbp+57h+var_78]
0x180065db2  lea     rcx, [rbp+57h+var_90]
0x180065db6  call    ?GetDWORD@RegistryKeyBroker@AssignedAccess@Internal@Windows@@QEBA?BKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; Windows::Internal::AssignedAccess::RegistryKeyBroker::GetDWORD(std::wstring const &,bool)
0x180065dbb  mov     [rbp+57h+var_B0], eax
0x180065dbe  lea     rcx, [rbp+57h+var_78]
0x180065dc2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180065dc7  nop
0x180065dc8  mov     rax, [rbp+57h+var_A0]
0x180065dcc  mov     [rbp+57h+var_98], rax
0x180065dd0  mov     [rbp+57h+var_A8], 0
0x180065dd8  lea     r9, [rbp+57h+var_B0]
0x180065ddc  lea     r8, [rbp+57h+pclsid]
0x180065de0  lea     rdx, [rbp+57h+var_98]
0x180065de4  lea     rcx, [rbp+57h+var_A8]
0x180065de8  call    ??$MakeAndInitialize@VAssignedAccessConfig@AssignedAccess@Internal@Windows@@UIAssignedAccessConfig@234@PEAUIAssignedAccessAccount@234@AEAU_GUID@@AEAW4ConfigSource@234@@Details@WRL@Microsoft@@YAJPEAPEAUIAssignedAccessConfig@AssignedAccess@Internal@Windows@@$$QEAPEAUIAssignedAccessAccount@456@AEAU_GUID@@AEAW4ConfigSource@456@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::AssignedAccessConfig,Windows::Internal::AssignedAccess::IAssignedAccessConfig,Windows::Internal::AssignedAccess::IAssignedAccessAccount *,_GUID &,Windows::Internal::AssignedAccess::ConfigSource &>(Windows::Internal::AssignedAccess::IAssignedAccessConfig * *,Windows::Internal::AssignedAccess::IAssignedAccessAccount * &&,_GUID &,Windows::Internal::AssignedAccess::ConfigSource &)
0x180065ded  mov     rcx, [rbp+5Fh]; this
0x180065df1  test    eax, eax
0x180065df3  jns     short loc_180065E0A
0x180065df5  mov     r9d, eax; char *
0x180065df8  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180065dff  mov     edx, 253h; void *
0x180065e04  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180065e0a  xorps   xmm0, xmm0
0x180065e0d  movdqu  xmmword ptr [rbp+57h+var_78], xmm0
0x180065e12  mov     [rbp+57h+var_68], 0
0x180065e1a  lea     rdx, aGlobalprofilee; "GlobalProfileExclusions"
0x180065e21  lea     rcx, [rbp+57h+var_48]
0x180065e25  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180065e2a  nop
0x180065e2b  lea     rax, [rbp+57h+var_78]
0x180065e2f  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x180065e34  lea     rdx, [rbp+57h+var_48]
0x180065e38  lea     rcx, [rbp+57h+var_90]
0x180065e3c  call    ?TryOpen@RegistryKeyBroker@AssignedAccess@Internal@Windows@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KKAEAV1234@@Z; Windows::Internal::AssignedAccess::RegistryKeyBroker::TryOpen(std::wstring const &,ulong,ulong,Windows::Internal::AssignedAccess::RegistryKeyBroker &)
0x180065e41  mov     ebx, eax
0x180065e43  lea     rcx, [rbp+57h+var_48]
0x180065e47  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180065e4c  mov     rcx, [rbp+5Fh]; this
0x180065e50  test    ebx, ebx
0x180065e52  jns     short loc_180065EC7
0x180065e54  mov     r9d, ebx; char *
0x180065e57  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180065e5e  mov     edx, 257h; void *
0x180065e63  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180065e68  lea     rdx, [rbp+57h+var_A8]
0x180065e6c  mov     rcx, rdi
0x180065e6f  call    ??$_Emplace_one_at_back@AEBV?$com_ptr_t@UIAssignedAccessConfig@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@@?$vector@V?$com_ptr_t@UIAssignedAccessConfig@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIAssignedAccessConfig@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@AEAAAEAV?$com_ptr_t@UIAssignedAccessConfig@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@AEBV23@@Z; std::vector<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessConfig,wil::err_exception_policy>>::_Emplace_one_at_back<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessConfig,wil::err_exception_policy> const &>(wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessConfig,wil::err_exception_policy> const &)
0x180065e74  nop
0x180065e75  lea     rcx, [rbp+57h+var_78]; this
0x180065e79  call    ??1RegistryKeyBroker@AssignedAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::AssignedAccess::RegistryKeyBroker::~RegistryKeyBroker(void)
0x180065e7e  nop
0x180065e7f  lea     rcx, [rbp+57h+var_A8]
0x180065e83  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180065e88  nop
0x180065e89  lea     rcx, [rbp+57h+var_A0]
0x180065e8d  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180065e92  nop
0x180065e93  lea     rcx, [rbp+57h+var_28]
0x180065e97  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180065e9c  nop
0x180065e9d  lea     rcx, [rbp+57h+var_90]; this
0x180065ea1  call    ??1RegistryKeyBroker@AssignedAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::AssignedAccess::RegistryKeyBroker::~RegistryKeyBroker(void)
0x180065ea6  mov     rcx, [rbp+57h+var_8]
0x180065eaa  xor     rcx, rsp; StackCookie
0x180065ead  call    __security_check_cookie
0x180065eb2  lea     r11, [rsp+0E0h+var_s0]
0x180065eba  mov     rbx, [r11+20h]
0x180065ebe  mov     rdi, [r11+28h]
0x180065ec2  mov     rsp, r11
0x180065ec5  pop     rbp
0x180065ec6  retn
0x180065ec7  mov     [rbp+57h+var_B0], 0
0x180065ece  lea     rdx, aDeviceowners; "DeviceOwners"
0x180065ed5  lea     rcx, [rbp+57h+var_48]
0x180065ed9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180065ede  nop
0x180065edf  lea     r9, [rbp+57h+var_B0]
0x180065ee3  lea     rdx, [rbp+57h+var_48]
0x180065ee7  lea     rcx, [rbp+57h+var_78]
0x180065eeb  call    ?TryGetDWORD@RegistryKeyBroker@AssignedAccess@Internal@Windows@@QEBAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NAEAK@Z; Windows::Internal::AssignedAccess::RegistryKeyBroker::TryGetDWORD(std::wstring const &,bool,ulong &)
0x180065ef0  mov     ebx, eax
0x180065ef2  lea     rcx, [rbp+57h+var_48]
0x180065ef6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180065efb  cmp     ebx, 80070002h
0x180065f01  jnz     short loc_180065F09
0x180065f03  xor     edx, edx
0x180065f05  xor     ebx, ebx
0x180065f07  jmp     short loc_180065F0C
0x180065f09  mov     edx, [rbp+57h+var_B0]
0x180065f0c  mov     rcx, [rbp+5Fh]; this
0x180065f10  test    ebx, ebx
0x180065f12  jns     short loc_180065F29
0x180065f14  mov     r9d, ebx; char *
0x180065f17  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180065f1e  mov     edx, 260h; void *
0x180065f23  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180065f29  mov     rcx, [rbp+57h+var_A8]
0x180065f2d  mov     rax, [rcx]
0x180065f30  cmp     edx, 1
0x180065f33  setz    dl
0x180065f36  mov     rax, [rax+68h]
0x180065f3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065f3f  mov     rcx, [rbp+5Fh]; this
0x180065f43  test    eax, eax
0x180065f45  jns     loc_180065E68
0x180065f4b  mov     r9d, eax; char *
0x180065f4e  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180065f55  mov     edx, 262h; void *
0x180065f5a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
