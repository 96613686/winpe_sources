# Windows::Internal::Storage::Cloud::Core::DefaultLocalStorageImpl::Save(Windows::Internal::Storage::Cloud::Core::CloudStoreItemId const &,bond::blob const &)

- ea: `0x1800fb990`
- end: `0x1800fbbfa`
- name: `?Save@DefaultLocalStorageImpl@Core@Cloud@Storage@Internal@Windows@@UEAAXAEBVCloudStoreItemId@23456@AEBVblob@bond@@@Z`
- size: `618`
- prototype: `void __fastcall(Windows::Internal::Storage::Cloud::Core::DefaultLocalStorageImpl *__hidden this, const struct Windows::Internal::Storage::Cloud::Core::CloudStoreItemId *, const struct bond::blob *)`
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180010688`
- `0x1800137f0`
- `0x180015178`
- `0x180016cf4`
- `0x180019720`
- `0x1800219e0`
- `0x180023000`
- `0x18002c020`
- `0x18003f6c4`
- `0x18004ee74`
- `0x180093784`
- `0x18009dd74`
- `0x1800b0704`
- `0x1800fb990`
- `0x1800fbd68`
- `0x1800fc31c`
- `0x1801201a0`
- `0x1801a6bf8`
- `0x1801df690`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800fbb0d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800fbb6a`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800fbb0d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800fbb6a`

## string_xrefs

- `0x1800fb9f4`: `onecoreuap\shell\cloudstore\store\cache\src\defaultlocalstorage.cpp`
- `0x1800fbaab`: `onecoreuap\shell\cloudstore\store\cache\src\defaultlocalstorage.cpp`
- `0x1800fbb21`: `onecoreuap\shell\cloudstore\store\cache\src\defaultlocalstorage.cpp`
- `0x1800fbb7e`: `onecoreuap\shell\cloudstore\store\cache\src\defaultlocalstorage.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::Internal::Storage::Cloud::Core::DefaultLocalStorageImpl::Save(
        Windows::Internal::Storage::Cloud::Core::DefaultLocalStorageImpl *this,
        const struct Windows::Internal::Storage::Cloud::Core::CloudStoreItemId *a2,
        const struct bond::blob *a3)
{
  Windows::Internal::Storage::Cloud::Core::DefaultLocalStorageImpl *v6; // rcx
  unsigned __int64 v7; // r9
  int ItemKeyName; // eax
  _QWORD *v9; // rbx
  __int64 v10; // rax
  DWORD cbData; // eax
  __int64 v12; // rdi
  __int64 v13; // r8
  __int64 v14; // rcx
  int v15; // eax
  LPCVOID *v16; // rax
  unsigned int v17; // eax
  unsigned int v18; // eax
  char v19; // al
  Windows::Internal::Storage::Cloud::Core::DefaultLocalStorageImpl *v20; // rcx
  int lpData; // [rsp+20h] [rbp-E0h]
  LPCVOID lpDataa; // [rsp+20h] [rbp-E0h]
  int lpDatab; // [rsp+20h] [rbp-E0h]
  unsigned int lpDatac; // [rsp+20h] [rbp-E0h]
  LPCVOID lpDatad; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v27[8]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v28[8]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v29[8]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v30[16]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v31[32]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v32[2048]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+10C8h] [rbp+FC8h]

  CloudStoreUtilities::ImpersonatePersistenceContext(v28, (char *)this + 8);
  ItemKeyName = Windows::Internal::Storage::Cloud::Core::DefaultLocalStorageImpl::GetItemKeyName(v6, a2, v32, v7);
  if ( ItemKeyName < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF7,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\defaultlocalstorage.cpp",
      (const char *)(unsigned int)ItemKeyName,
      lpData);
  hKey = 0;
  v9 = (_QWORD *)((char *)this + 40);
  v10 = CloudStoreUtilities::OpenPerAccountCommonSubKey(
          (unsigned int)v27,
          *((_QWORD *)this + 1),
          *((_QWORD *)this + 3),
          (int)this + 72,
          (__int64)this + 40,
          v32);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator=(
    &hKey,
    v10);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v27);
  cbData = *((_DWORD *)a3 + 4);
  if ( cbData <= 0x80000 )
  {
    v18 = RegSetKeyValueW(hKey, 0, L"Data", 3u, *(LPCVOID *)a3, cbData);
    if ( v18 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x10B,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\defaultlocalstorage.cpp",
        (const char *)v18,
        (unsigned int)lpDatad);
    if ( *((_QWORD *)this + 8) > 0xFu )
      v9 = (_QWORD *)*v9;
    v19 = std::_Traits_equal<std::char_traits<char>>(v9, *((_QWORD *)this + 7), "RetrySave", 9, lpDatad);
    Windows::Internal::Storage::Cloud::Core::DefaultLocalStorageImpl::DeleteBulk(v20, a2, v19);
  }
  else
  {
    v12 = Base64Encode(v31, a3);
    if ( *((_QWORD *)this + 8) > 0xFu )
      v9 = (_QWORD *)*v9;
    LOBYTE(v13) = std::_Traits_equal<std::char_traits<char>>(v9, *((_QWORD *)this + 7), "RetrySave", 9, lpDataa);
    v15 = Windows::Internal::Storage::Cloud::Core::DefaultLocalStorageImpl::SaveBulk(v14, a2, v13, v12);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x106,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\defaultlocalstorage.cpp",
        (const char *)(unsigned int)v15,
        lpDatab);
    std::string::_Tidy_deallocate(v31);
    std::string::string(v31, byte_1802299F5);
    v16 = (LPCVOID *)Base64Decode(v29, v31);
    v17 = RegSetKeyValueW(hKey, 0, L"Data", 3u, *v16, 0);
    if ( v17 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x107,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\defaultlocalstorage.cpp",
        (const char *)v17,
        lpDatac);
    boost::detail::shared_count::~shared_count((boost::detail::shared_count *)v30);
    std::string::_Tidy_deallocate(v31);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v28);
}

```

## disassembly

```asm
0x1800fb990  mov     [rsp-8+arg_18], rbx
0x1800fb995  push    rbp
0x1800fb996  push    rsi
0x1800fb997  push    rdi
0x1800fb998  push    r14
0x1800fb99a  push    r15
0x1800fb99c  lea     rbp, [rsp-0FA0h]
0x1800fb9a4  mov     eax, 10A0h
0x1800fb9a9  call    _alloca_probe
0x1800fb9ae  sub     rsp, rax
0x1800fb9b1  mov     rax, cs:__security_cookie
0x1800fb9b8  xor     rax, rsp
0x1800fb9bb  mov     [rbp+0FC0h+var_30], rax
0x1800fb9c2  mov     rdi, r8
0x1800fb9c5  mov     r15, rdx
0x1800fb9c8  mov     rsi, rcx
0x1800fb9cb  lea     rdx, [rcx+8]
0x1800fb9cf  lea     rcx, [rsp+10C0h+var_1070]
0x1800fb9d4  call    ?ImpersonatePersistenceContext@CloudStoreUtilities@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@wil@@AEBV?$shared_ptr@VPersistenceContext@Core@Cloud@Storage@Internal@Windows@@@std@@@Z; CloudStoreUtilities::ImpersonatePersistenceContext(std::shared_ptr<Windows::Internal::Storage::Cloud::Core::PersistenceContext> const &)
0x1800fb9d9  nop
0x1800fb9da  lea     r8, [rbp+0FC0h+var_1030]; unsigned __int16 *
0x1800fb9de  mov     rdx, r15; struct Windows::Internal::Storage::Cloud::Core::CloudStoreItemId *
0x1800fb9e1  call    ?GetItemKeyName@DefaultLocalStorageImpl@Core@Cloud@Storage@Internal@Windows@@AEAAJAEBVCloudStoreItemId@23456@PEAG_K@Z; Windows::Internal::Storage::Cloud::Core::DefaultLocalStorageImpl::GetItemKeyName(Windows::Internal::Storage::Cloud::Core::CloudStoreItemId const &,ushort *,unsigned __int64)
0x1800fb9e6  mov     rcx, [rbp+0FC8h]; this
0x1800fb9ed  test    eax, eax
0x1800fb9ef  jns     short loc_1800FBA06
0x1800fb9f1  mov     r9d, eax; char *
0x1800fb9f4  lea     r8, aOnecoreuapShel_105; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x1800fb9fb  mov     edx, 0F7h; void *
0x1800fba00  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800fba06  mov     [rsp+10C0h+hKey], 0
0x1800fba0f  lea     rbx, [rsi+28h]
0x1800fba13  lea     r9, [rsi+48h]
0x1800fba17  lea     rax, [rbp+0FC0h+var_1030]
0x1800fba1b  mov     qword ptr [rsp+10C0h+cbData], rax
0x1800fba20  mov     [rsp+10C0h+lpData], rbx; int
0x1800fba25  mov     r8, [rsi+18h]
0x1800fba29  mov     rdx, [rsi+8]
0x1800fba2d  lea     rcx, [rsp+10C0h+var_1078]
0x1800fba32  call    ?OpenPerAccountCommonSubKey@CloudStoreUtilities@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAVPersistenceContext@Core@Cloud@Storage@Internal@Windows@@AEAVCloudStoreAccount@56789@AEBQEBGAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBGK@Z; CloudStoreUtilities::OpenPerAccountCommonSubKey(Windows::Internal::Storage::Cloud::Core::PersistenceContext &,Windows::Internal::Storage::Cloud::Core::CloudStoreAccount &,ushort const * const &,std::string const &,ushort const *,ulong)
0x1800fba37  mov     rdx, rax
0x1800fba3a  lea     rcx, [rsp+10C0h+hKey]
0x1800fba3f  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&)
0x1800fba44  lea     rcx, [rsp+10C0h+var_1078]
0x1800fba49  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800fba4e  mov     eax, [rdi+10h]
0x1800fba51  cmp     eax, 80000h
0x1800fba56  jbe     loc_1800FBB4A
0x1800fba5c  mov     rdx, rdi
0x1800fba5f  lea     rcx, [rsp+10C0h+var_1050]
0x1800fba64  call    ?Base64Encode@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBVblob@bond@@@Z; Base64Encode(bond::blob const &)
0x1800fba69  mov     rdi, rax
0x1800fba6c  mov     rdx, [rbx+10h]
0x1800fba70  cmp     qword ptr [rbx+18h], 0Fh
0x1800fba75  jbe     short loc_1800FBA7A
0x1800fba77  mov     rbx, [rbx]
0x1800fba7a  mov     r9d, 9
0x1800fba80  lea     r8, aRetrysave; "RetrySave"
0x1800fba87  mov     rcx, rbx
0x1800fba8a  call    ??$_Traits_equal@U?$char_traits@D@std@@@std@@YA_NQEBD_K01@Z; std::_Traits_equal<std::char_traits<char>>(char const * const,unsigned __int64,char const * const,unsigned __int64)
0x1800fba8f  mov     r9, rdi
0x1800fba92  mov     r8b, al
0x1800fba95  mov     rdx, r15
0x1800fba98  call    ?SaveBulk@DefaultLocalStorageImpl@Core@Cloud@Storage@Internal@Windows@@AEAAJAEBVCloudStoreItemId@23456@_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Windows::Internal::Storage::Cloud::Core::DefaultLocalStorageImpl::SaveBulk(Windows::Internal::Storage::Cloud::Core::CloudStoreItemId const &,bool,std::string const &)
0x1800fba9d  mov     rcx, [rbp+0FC8h]; this
0x1800fbaa4  test    eax, eax
0x1800fbaa6  jns     short loc_1800FBABD
0x1800fbaa8  mov     r9d, eax; char *
0x1800fbaab  lea     r8, aOnecoreuapShel_105; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x1800fbab2  mov     edx, 106h; void *
0x1800fbab7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800fbabd  lea     rcx, [rsp+10C0h+var_1050]; void *
0x1800fbac2  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800fbac7  lea     rdx, byte_1802299F5
0x1800fbace  lea     rcx, [rsp+10C0h+var_1050]
0x1800fbad3  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800fbad8  nop
0x1800fbad9  lea     rdx, [rsp+10C0h+var_1050]
0x1800fbade  lea     rcx, [rsp+10C0h+var_1068]
0x1800fbae3  call    ?Base64Decode@@YA?AVblob@bond@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Base64Decode(std::string const &)
0x1800fbae8  nop
0x1800fbae9  mov     [rsp+10C0h+cbData], 0; cbData
0x1800fbaf1  mov     rax, [rax]
0x1800fbaf4  mov     [rsp+10C0h+lpData], rax; unsigned int
0x1800fbaf9  mov     r9d, 3; dwType
0x1800fbaff  lea     r8, aData_0; "Data"
0x1800fbb06  xor     edx, edx; lpSubKey
0x1800fbb08  mov     rcx, [rsp+10C0h+hKey]; hKey
0x1800fbb0d  call    cs:__imp_RegSetKeyValueW
0x1800fbb13  mov     rcx, [rbp+0FC8h]; this
0x1800fbb1a  test    eax, eax
0x1800fbb1c  jz      short loc_1800FBB33
0x1800fbb1e  mov     r9d, eax; char *
0x1800fbb21  lea     r8, aOnecoreuapShel_105; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x1800fbb28  mov     edx, 107h; void *
0x1800fbb2d  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800fbb33  lea     rcx, [rsp+10C0h+var_1060]; this
0x1800fbb38  call    ??1shared_count@detail@boost@@QEAA@XZ; boost::detail::shared_count::~shared_count(void)
0x1800fbb3d  nop
0x1800fbb3e  lea     rcx, [rsp+10C0h+var_1050]; void *
0x1800fbb43  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800fbb48  jmp     short loc_1800FBBBF
0x1800fbb4a  mov     [rsp+10C0h+cbData], eax; cbData
0x1800fbb4e  mov     rax, [rdi]
0x1800fbb51  mov     [rsp+10C0h+lpData], rax; unsigned int
0x1800fbb56  mov     r9d, 3; dwType
0x1800fbb5c  lea     r8, aData_0; "Data"
0x1800fbb63  xor     edx, edx; lpSubKey
0x1800fbb65  mov     rcx, [rsp+10C0h+hKey]; hKey
0x1800fbb6a  call    cs:__imp_RegSetKeyValueW
0x1800fbb70  mov     rcx, [rbp+0FC8h]; this
0x1800fbb77  test    eax, eax
0x1800fbb79  jz      short loc_1800FBB90
0x1800fbb7b  mov     r9d, eax; char *
0x1800fbb7e  lea     r8, aOnecoreuapShel_105; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x1800fbb85  mov     edx, 10Bh; void *
0x1800fbb8a  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800fbb90  mov     rdx, [rbx+10h]
0x1800fbb94  cmp     qword ptr [rbx+18h], 0Fh
0x1800fbb99  jbe     short loc_1800FBB9E
0x1800fbb9b  mov     rbx, [rbx]
0x1800fbb9e  mov     r9d, 9
0x1800fbba4  lea     r8, aRetrysave; "RetrySave"
0x1800fbbab  mov     rcx, rbx
0x1800fbbae  call    ??$_Traits_equal@U?$char_traits@D@std@@@std@@YA_NQEBD_K01@Z; std::_Traits_equal<std::char_traits<char>>(char const * const,unsigned __int64,char const * const,unsigned __int64)
0x1800fbbb3  mov     r8b, al; bool
0x1800fbbb6  mov     rdx, r15; struct Windows::Internal::Storage::Cloud::Core::CloudStoreItemId *
0x1800fbbb9  call    ?DeleteBulk@DefaultLocalStorageImpl@Core@Cloud@Storage@Internal@Windows@@AEAAJAEBVCloudStoreItemId@23456@_N@Z; Windows::Internal::Storage::Cloud::Core::DefaultLocalStorageImpl::DeleteBulk(Windows::Internal::Storage::Cloud::Core::CloudStoreItemId const &,bool)
0x1800fbbbe  nop
0x1800fbbbf  lea     rcx, [rsp+10C0h+hKey]
0x1800fbbc4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800fbbc9  nop
0x1800fbbca  lea     rcx, [rsp+10C0h+var_1070]
0x1800fbbcf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800fbbd4  mov     rcx, [rbp+0FC0h+var_30]
0x1800fbbdb  xor     rcx, rsp; StackCookie
0x1800fbbde  call    __security_check_cookie
0x1800fbbe3  mov     rbx, [rsp+10C0h+arg_18]
0x1800fbbeb  add     rsp, 10A0h
0x1800fbbf2  pop     r15
0x1800fbbf4  pop     r14
0x1800fbbf6  pop     rdi
0x1800fbbf7  pop     rsi
0x1800fbbf8  pop     rbp
0x1800fbbf9  retn
```
