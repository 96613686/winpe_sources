# AppReadiness::Tasks::UnregisterPackage::FindPackageIdToRemove(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager> const &)

- ea: `0x18002bcc0`
- end: `0x18002bee6`
- name: `?FindPackageIdToRemove@UnregisterPackage@Tasks@AppReadiness@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV45@AEBV?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@@Z`
- size: `550`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002b850`

## callees

- `0x180002958`
- `0x18000b488`
- `0x18001870c`
- `0x1800187c4`
- `0x180027a4c`
- `0x18002bcc0`
- `0x18002ecbc`
- `0x180037528`
- `0x18003ecb4`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002be2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002be40`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bea0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002beb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002be2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002be40`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bea0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002beb2`

## string_xrefs

- `0x18002bd1b`: `onecoreuap\shell\appreadiness\src\tasks\unregisterpackage.cpp`
- `0x18002bdc6`: `onecoreuap\shell\appreadiness\src\tasks\unregisterpackage.cpp`
- `0x18002bd27`: `AppReadiness::Tasks::UnregisterPackage::FindPackageIdToRemove`
- `0x18002bdd2`: `AppReadiness::Tasks::UnregisterPackage::FindPackageIdToRemove`
- `0x18002bdd9`: `packageManager2->FindPackagesByUserSecurityIdPackageFamilyNameWithPackageTypes(userSidString.Get(), packageFamilyNameString.Get(), PackageTypes_Main, &packageIter)`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall AppReadiness::Tasks::UnregisterPackage::FindPackageIdToRemove(
        __int64 a1,
        __int64 a2,
        const WCHAR *a3,
        __int64 (__fastcall ****a4)(_QWORD, GUID *, __int64 *))
{
  __int64 (__fastcall ***v7)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v8)(_QWORD, GUID *, __int64 *); // rbx
  int v9; // eax
  __int64 v10; // rax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, HSTRING, HSTRING, __int64, __int64 *); // rbx
  int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v17; // [rsp+30h] [rbp-39h] BYREF
  HSTRING string; // [rsp+38h] [rbp-31h] BYREF
  HSTRING v19; // [rsp+40h] [rbp-29h] BYREF
  _QWORD v20[3]; // [rsp+50h] [rbp-19h] BYREF
  _BYTE pExceptionObject[88]; // [rsp+68h] [rbp-1h] BYREF
  __int64 v22; // [rsp+E8h] [rbp+7Fh] BYREF

  v17 = 0;
  v7 = *a4;
  v8 = ***a4;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
  v9 = v8(v7, &GUID_f7aad08d_0840_46f2_b5d8_cad47693a095, &v17);
  if ( v9 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      v9,
      "packageManager.As(&packageManager2)",
      "AppReadiness::Tasks::UnregisterPackage::FindPackageIdToRemove",
      "onecoreuap\\shell\\appreadiness\\src\\tasks\\unregisterpackage.cpp",
      161);
    throw (Windows::HResultException *)pExceptionObject;
  }
  v22 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 32) + 112LL))(a1 + 32);
  to_winstring(&v19, (PCNZWCH)(v10 + 64));
  to_winstring(&string, a3);
  v11 = v17;
  v12 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, __int64, __int64 *))(*(_QWORD *)v17 + 112LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
  v13 = v12(v11, v19, string, 1, &v22);
  if ( v13 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      v13,
      "packageManager2->FindPackagesByUserSecurityIdPackageFamilyNameWithPackageTypes(userSidString.Get(), packageFamilyN"
      "ameString.Get(), PackageTypes_Main, &packageIter)",
      "AppReadiness::Tasks::UnregisterPackage::FindPackageIdToRemove",
      "onecoreuap\\shell\\appreadiness\\src\\tasks\\unregisterpackage.cpp",
      166);
    throw (Windows::HResultException *)pExceptionObject;
  }
  to_vector<Windows::ApplicationModel::IPackage,Windows::ApplicationModel::Package>(v20, &v22);
  if ( v20[0] == v20[1] )
  {
    std::wstring::wstring(a2);
    std::vector<Microsoft::WRL::ComPtr<AppReadiness::ITask>>::_Tidy(v20);
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(v19);
    v19 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
  }
  else
  {
    AppReadiness::PackageInfo::GetPackageFullName(a2, *(_QWORD *)v20[0]);
    std::vector<Microsoft::WRL::ComPtr<AppReadiness::ITask>>::_Tidy(v20);
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(v19);
    v19 = 0;
    v14 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    v15 = v17;
    if ( v17 )
    {
      v17 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x18002bcc0  push    rbp
0x18002bcc2  push    rbx
0x18002bcc3  push    rsi
0x18002bcc4  push    rdi
0x18002bcc5  push    r14
0x18002bcc7  push    r15
0x18002bcc9  lea     rbp, [rsp-2Fh]
0x18002bcce  sub     rsp, 98h
0x18002bcd5  mov     r14, r8
0x18002bcd8  mov     rsi, rdx
0x18002bcdb  mov     r15, rcx
0x18002bcde  mov     [rbp+57h+var_90], 0
0x18002bce6  mov     rdi, [r9]
0x18002bce9  mov     rax, [rdi]
0x18002bcec  mov     rbx, [rax]
0x18002bcef  lea     rcx, [rbp+57h+var_90]
0x18002bcf3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002bcf8  lea     r8, [rbp+57h+var_90]
0x18002bcfc  lea     rdx, _GUID_f7aad08d_0840_46f2_b5d8_cad47693a095
0x18002bd03  mov     rcx, rdi
0x18002bd06  mov     rax, rbx
0x18002bd09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bd0e  nop
0x18002bd0f  test    eax, eax
0x18002bd11  jns     short loc_18002BD51
0x18002bd13  mov     [rsp+0C0h+var_98], 0A1h; int
0x18002bd1b  lea     rcx, aOnecoreuapShel_31; "onecoreuap\\shell\\appreadiness\\src\\t"...
0x18002bd22  mov     [rsp+0C0h+var_A0], rcx; char *
0x18002bd27  lea     r9, aAppreadinessTa_9; "AppReadiness::Tasks::UnregisterPackage:"...
0x18002bd2e  lea     r8, aPackagemanager_9; "packageManager.As(&packageManager2)"
0x18002bd35  mov     edx, eax; int
0x18002bd37  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18002bd3b  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18002bd40  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18002bd47  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002bd4b  call    _CxxThrowException_0
0x18002bd51  mov     [rbp+57h+arg_18], 0
0x18002bd59  lea     rcx, [r15+20h]
0x18002bd5d  mov     rax, [rcx]
0x18002bd60  mov     rax, [rax+70h]
0x18002bd64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bd69  lea     rdx, [rax+40h]; sourceString
0x18002bd6d  lea     rcx, [rbp+57h+var_80]; string
0x18002bd71  call    ?to_winstring@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; to_winstring(std::wstring const &)
0x18002bd76  nop
0x18002bd77  mov     rdx, r14; sourceString
0x18002bd7a  lea     rcx, [rbp+57h+string]; string
0x18002bd7e  call    ?to_winstring@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; to_winstring(std::wstring const &)
0x18002bd83  nop
0x18002bd84  mov     rdi, [rbp+57h+var_90]
0x18002bd88  mov     rax, [rdi]
0x18002bd8b  mov     rbx, [rax+70h]
0x18002bd8f  lea     rcx, [rbp+57h+arg_18]
0x18002bd93  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002bd98  lea     rax, [rbp+57h+arg_18]
0x18002bd9c  mov     [rsp+0C0h+var_A0], rax
0x18002bda1  mov     r9d, 1
0x18002bda7  mov     r8, [rbp+57h+string]
0x18002bdab  mov     rdx, [rbp+57h+var_80]
0x18002bdaf  mov     rcx, rdi
0x18002bdb2  mov     rax, rbx
0x18002bdb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bdba  test    eax, eax
0x18002bdbc  jns     short loc_18002BDFC
0x18002bdbe  mov     [rsp+0C0h+var_98], 0A6h; int
0x18002bdc6  lea     rcx, aOnecoreuapShel_31; "onecoreuap\\shell\\appreadiness\\src\\t"...
0x18002bdcd  mov     [rsp+0C0h+var_A0], rcx; char *
0x18002bdd2  lea     r9, aAppreadinessTa_9; "AppReadiness::Tasks::UnregisterPackage:"...
0x18002bdd9  lea     r8, aPackagemanager_5; "packageManager2->FindPackagesByUserSecu"...
0x18002bde0  mov     edx, eax; int
0x18002bde2  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18002bde6  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18002bdeb  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18002bdf2  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002bdf6  call    _CxxThrowException_0
0x18002bdfc  lea     rdx, [rbp+57h+arg_18]
0x18002be00  lea     rcx, [rbp+57h+var_70]
0x18002be04  call    ??$to_vector@UIPackage@ApplicationModel@Windows@@VPackage@23@@@YA?AV?$vector@V?$ComPtr@UIPackage@ApplicationModel@Windows@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIPackage@ApplicationModel@Windows@@@WRL@Microsoft@@@std@@@std@@AEBV?$ComPtr@U?$IIterable@PEAVPackage@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Z; to_vector<Windows::ApplicationModel::IPackage,Windows::ApplicationModel::Package>(Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::ApplicationModel::Package *>> const &)
0x18002be09  nop
0x18002be0a  mov     rdx, [rbp+57h+var_70]
0x18002be0e  mov     rcx, rsi
0x18002be11  cmp     rdx, [rbp+57h+var_68]
0x18002be15  jz      short loc_18002BE8C
0x18002be17  mov     rdx, [rdx]
0x18002be1a  call    ?GetPackageFullName@PackageInfo@AppReadiness@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUIPackage@ApplicationModel@Windows@@@Z; AppReadiness::PackageInfo::GetPackageFullName(Windows::ApplicationModel::IPackage *)
0x18002be1f  nop
0x18002be20  lea     rcx, [rbp+57h+var_70]
0x18002be24  call    ?_Tidy@?$vector@V?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@@std@@@std@@AEAAXXZ; std::vector<Microsoft::WRL::ComPtr<AppReadiness::ITask>>::_Tidy(void)
0x18002be29  nop
0x18002be2a  mov     rcx, [rbp+57h+string]; string
0x18002be2e  call    cs:__imp_WindowsDeleteString
0x18002be34  mov     [rbp+57h+string], 0
0x18002be3c  mov     rcx, [rbp+57h+var_80]; string
0x18002be40  call    cs:__imp_WindowsDeleteString
0x18002be46  mov     [rbp+57h+var_80], 0
0x18002be4e  mov     rcx, [rbp+57h+arg_18]
0x18002be52  test    rcx, rcx
0x18002be55  jz      short loc_18002BE6C
0x18002be57  mov     [rbp+57h+arg_18], 0
0x18002be5f  mov     rax, [rcx]
0x18002be62  mov     rax, [rax+10h]
0x18002be66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be6b  nop
0x18002be6c  mov     rcx, [rbp+57h+var_90]
0x18002be70  test    rcx, rcx
0x18002be73  jz      short loc_18002BE8A
0x18002be75  mov     [rbp+57h+var_90], 0
0x18002be7d  mov     rax, [rcx]
0x18002be80  mov     rax, [rax+10h]
0x18002be84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be89  nop
0x18002be8a  jmp     short loc_18002BED3
0x18002be8c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002be91  nop
0x18002be92  lea     rcx, [rbp+57h+var_70]
0x18002be96  call    ?_Tidy@?$vector@V?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@@std@@@std@@AEAAXXZ; std::vector<Microsoft::WRL::ComPtr<AppReadiness::ITask>>::_Tidy(void)
0x18002be9b  nop
0x18002be9c  mov     rcx, [rbp+57h+string]; string
0x18002bea0  call    cs:__imp_WindowsDeleteString
0x18002bea6  mov     [rbp+57h+string], 0
0x18002beae  mov     rcx, [rbp+57h+var_80]; string
0x18002beb2  call    cs:__imp_WindowsDeleteString
0x18002beb8  mov     [rbp+57h+var_80], 0
0x18002bec0  lea     rcx, [rbp+57h+arg_18]
0x18002bec4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002bec9  nop
0x18002beca  lea     rcx, [rbp+57h+var_90]
0x18002bece  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002bed3  mov     rax, rsi
0x18002bed6  add     rsp, 98h
0x18002bedd  pop     r15
0x18002bedf  pop     r14
0x18002bee1  pop     rdi
0x18002bee2  pop     rsi
0x18002bee3  pop     rbx
0x18002bee4  pop     rbp
0x18002bee5  retn
```
