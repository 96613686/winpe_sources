# StoreAppFinder::GetEvidenceFromPackage(ConfigSettings const &,Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage> const &,std::vector<Application,std::allocator<Application>> &,std::set<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x1800d6e0c`
- end: `0x1800d6fe6`
- name: `?GetEvidenceFromPackage@StoreAppFinder@@SAXAEBVConfigSettings@@AEBV?$ComPtr@UIPackage@ApplicationModel@Windows@@@WRL@Microsoft@@AEAV?$vector@VApplication@@V?$allocator@VApplication@@@std@@@std@@AEAV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@7@@Z`
- size: `474`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800d5ab4`
- `0x1800d6fec`

## callees

- `0x180005890`
- `0x18000a2d4`
- `0x18001c5f0`
- `0x18001df8c`
- `0x1800c97f0`
- `0x1800d038c`
- `0x1800d0a80`
- `0x1800d58e8`
- `0x1800d6e0c`
- `0x1800d7c74`
- `0x1800d93a4`
- `0x1800db734`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d6f8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d6f8d`

## string_xrefs

- `0x1800d6e9f`: `onecore\base\appcompat\inventory\software\inv\lib\storeappfinder.cpp`
- `0x1800d6ede`: `onecore\base\appcompat\inventory\software\inv\lib\storeappfinder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall StoreAppFinder::GetEvidenceFromPackage(
        struct ConfigSettings *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  int v7; // eax
  int v8; // eax
  __int64 v9; // rcx
  int v11[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v12; // [rsp+28h] [rbp-D8h] BYREF
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v14[16]; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v15[5]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v16[126]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+498h] [rbp+398h]

  StoreApplication::GetStoreAppManifestPathFromPackage(v15, a2, 1);
  v12 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
  StoreAppFinder::GetManifestReaderFromManifestPath(v15, (__int64)&v12);
  *(_QWORD *)v11 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v12 + 24LL))(v12, v11);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x38E,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeappfinder.cpp",
      (const char *)(unsigned int)v7,
      v11[0]);
  pv = 0;
  v8 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(**(_QWORD **)v11 + 72LL))(*(_QWORD *)v11, &pv);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x393,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeappfinder.cpp",
      (const char *)(unsigned int)v8,
      v11[0]);
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Emplace<Common::AutoCoTaskMemString &>(
    a4,
    v14,
    &pv);
  if ( v14[8] || *((_BYTE *)a1 + 221) )
  {
    StoreApplication::StoreApplication((Application *)v16, a1);
    if ( *(_QWORD *)(a3 + 8) == *(_QWORD *)(a3 + 16) )
    {
      std::vector<Application>::_Emplace_reallocate<Application const &>(a3, *(_QWORD *)(a3 + 8), v16);
    }
    else
    {
      Application::Application(*(Application **)(a3 + 8), (const struct Application *)v16);
      *(_QWORD *)(a3 + 8) += 1008LL;
    }
    v16[0] = &StoreApplication::`vftable'{for `IAmiInventoryTelemetryItem'};
    v16[1] = &StoreApplication::`vftable'{for `Windows::Compat::Inventory::IInventoryDataProvider'};
    v16[2] = &StoreApplication::`vftable';
    Application::~Application((Application *)v16);
  }
  CoTaskMemFree(pv);
  v9 = *(_QWORD *)v11;
  if ( *(_QWORD *)v11 )
  {
    *(_QWORD *)v11 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
  return std::wstring::_Tidy_deallocate(v15);
}

```

## disassembly

```asm
0x1800d6e0c  push    rbp
0x1800d6e0e  push    rbx
0x1800d6e0f  push    rsi
0x1800d6e10  push    rdi
0x1800d6e11  push    r14
0x1800d6e13  lea     rbp, [rsp-370h]
0x1800d6e1b  sub     rsp, 470h
0x1800d6e22  mov     rax, cs:__security_cookie
0x1800d6e29  xor     rax, rsp
0x1800d6e2c  mov     [rbp+390h+var_30], rax
0x1800d6e33  mov     r14, r9
0x1800d6e36  mov     rbx, r8
0x1800d6e39  mov     rsi, rdx
0x1800d6e3c  mov     rdi, rcx
0x1800d6e3f  mov     r8d, 1
0x1800d6e45  lea     rcx, [rsp+490h+var_448]
0x1800d6e4a  call    ?GetStoreAppManifestPathFromPackage@StoreApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$ComPtr@UIPackage@ApplicationModel@Windows@@@WRL@Microsoft@@W4ManifestType@@@Z; StoreApplication::GetStoreAppManifestPathFromPackage(Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage> const &,ManifestType)
0x1800d6e4f  nop
0x1800d6e50  mov     [rsp+490h+var_468], 0
0x1800d6e59  lea     rcx, [rsp+490h+var_468]
0x1800d6e5e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d6e63  lea     rdx, [rsp+490h+var_468]
0x1800d6e68  lea     rcx, [rsp+490h+var_448]
0x1800d6e6d  call    ?GetManifestReaderFromManifestPath@StoreAppFinder@@SAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAPEAUIAppxManifestReader@@@Z; StoreAppFinder::GetManifestReaderFromManifestPath(std::wstring const &,IAppxManifestReader * *)
0x1800d6e72  mov     qword ptr [rsp+490h+var_470], 0; int
0x1800d6e7b  mov     rcx, [rsp+490h+var_468]
0x1800d6e80  mov     rax, [rcx]
0x1800d6e83  lea     rdx, [rsp+490h+var_470]
0x1800d6e88  mov     rax, [rax+18h]
0x1800d6e8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6e91  mov     rcx, [rbp+398h]; this
0x1800d6e98  test    eax, eax
0x1800d6e9a  jns     short loc_1800D6EB1
0x1800d6e9c  mov     r9d, eax; char *
0x1800d6e9f  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\inventory\\so"...
0x1800d6ea6  mov     edx, 38Eh; void *
0x1800d6eab  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800d6eb1  mov     [rsp+490h+pv], 0
0x1800d6eba  mov     rcx, qword ptr [rsp+490h+var_470]
0x1800d6ebf  mov     rax, [rcx]
0x1800d6ec2  lea     rdx, [rsp+490h+pv]
0x1800d6ec7  mov     rax, [rax+48h]
0x1800d6ecb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6ed0  mov     rcx, [rbp+398h]; this
0x1800d6ed7  test    eax, eax
0x1800d6ed9  jns     short loc_1800D6EF0
0x1800d6edb  mov     r9d, eax; char *
0x1800d6ede  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\inventory\\so"...
0x1800d6ee5  mov     edx, 393h; void *
0x1800d6eea  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800d6ef0  lea     r8, [rsp+490h+pv]
0x1800d6ef5  lea     rdx, [rsp+490h+var_458]
0x1800d6efa  mov     rcx, r14
0x1800d6efd  call    ??$_Emplace@AEAVAutoCoTaskMemString@Common@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@_N@1@AEAVAutoCoTaskMemString@Common@@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Emplace<Common::AutoCoTaskMemString &>(Common::AutoCoTaskMemString &)
0x1800d6f02  cmp     [rsp+490h+var_450], 0
0x1800d6f07  jnz     short loc_1800D6F12
0x1800d6f09  cmp     byte ptr [rdi+0DDh], 0
0x1800d6f10  jz      short loc_1800D6F88
0x1800d6f12  mov     r9, rsi
0x1800d6f15  lea     r8, [rsp+490h+var_470]
0x1800d6f1a  mov     rdx, rdi
0x1800d6f1d  lea     rcx, [rsp+490h+var_420]
0x1800d6f22  call    ??0StoreApplication@@QEAA@AEBVConfigSettings@@AEBV?$ComPtr@UIAppxManifestPackageId@@@WRL@Microsoft@@AEBV?$ComPtr@UIPackage@ApplicationModel@Windows@@@34@@Z; StoreApplication::StoreApplication(ConfigSettings const &,Microsoft::WRL::ComPtr<IAppxManifestPackageId> const &,Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage> const &)
0x1800d6f27  nop
0x1800d6f28  mov     rax, [rbx+8]
0x1800d6f2c  cmp     rax, [rbx+10h]
0x1800d6f30  jz      short loc_1800D6F49
0x1800d6f32  lea     rdx, [rsp+490h+var_420]; struct Application *
0x1800d6f37  mov     rcx, rax; this
0x1800d6f3a  call    ??0Application@@QEAA@AEBV0@@Z; Application::Application(Application const &)
0x1800d6f3f  add     qword ptr [rbx+8], 3F0h
0x1800d6f47  jmp     short loc_1800D6F5A
0x1800d6f49  lea     r8, [rsp+490h+var_420]
0x1800d6f4e  mov     rdx, rax
0x1800d6f51  mov     rcx, rbx
0x1800d6f54  call    ??$_Emplace_reallocate@AEBVApplication@@@?$vector@VApplication@@V?$allocator@VApplication@@@std@@@std@@AEAAPEAVApplication@@QEAV2@AEBV2@@Z; std::vector<Application>::_Emplace_reallocate<Application const &>(Application * const,Application const &)
0x1800d6f59  nop
0x1800d6f5a  lea     rax, ??_7StoreApplication@@6BIAmiInventoryTelemetryItem@@@; const StoreApplication::`vftable'{for `IAmiInventoryTelemetryItem'}
0x1800d6f61  mov     [rsp+490h+var_420], rax
0x1800d6f66  lea     rax, ??_7StoreApplication@@6BIInventoryDataProvider@Inventory@Compat@Windows@@@; const StoreApplication::`vftable'{for `Windows::Compat::Inventory::IInventoryDataProvider'}
0x1800d6f6d  mov     [rsp+490h+var_418], rax
0x1800d6f72  lea     rax, ??_7StoreApplication@@6B@; const StoreApplication::`vftable'
0x1800d6f79  mov     [rbp+390h+var_410], rax
0x1800d6f7d  lea     rcx, [rsp+490h+var_420]; this
0x1800d6f82  call    ??1Application@@UEAA@XZ; Application::~Application(void)
0x1800d6f87  nop
0x1800d6f88  mov     rcx, [rsp+490h+pv]; pv
0x1800d6f8d  call    cs:__imp_CoTaskMemFree
0x1800d6f93  nop
0x1800d6f94  mov     rcx, qword ptr [rsp+490h+var_470]
0x1800d6f99  test    rcx, rcx
0x1800d6f9c  jz      short loc_1800D6FB4
0x1800d6f9e  mov     qword ptr [rsp+490h+var_470], 0
0x1800d6fa7  mov     rax, [rcx]
0x1800d6faa  mov     rax, [rax+10h]
0x1800d6fae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6fb3  nop
0x1800d6fb4  lea     rcx, [rsp+490h+var_468]
0x1800d6fb9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d6fbe  nop
0x1800d6fbf  lea     rcx, [rsp+490h+var_448]
0x1800d6fc4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800d6fc9  mov     rcx, [rbp+390h+var_30]
0x1800d6fd0  xor     rcx, rsp; StackCookie
0x1800d6fd3  call    __security_check_cookie
0x1800d6fd8  add     rsp, 470h
0x1800d6fdf  pop     r14
0x1800d6fe1  pop     rdi
0x1800d6fe2  pop     rsi
0x1800d6fe3  pop     rbx
0x1800d6fe4  pop     rbp
0x1800d6fe5  retn
```
