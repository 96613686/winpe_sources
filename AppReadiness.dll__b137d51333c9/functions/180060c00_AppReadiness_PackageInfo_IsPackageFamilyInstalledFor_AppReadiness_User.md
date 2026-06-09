# AppReadiness::PackageInfo::IsPackageFamilyInstalledFor(AppReadiness::User *)

- ea: `0x180060c00`
- end: `0x180060dd0`
- name: `?IsPackageFamilyInstalledFor@PackageInfo@AppReadiness@@UEAA_NPEAVUser@2@@Z`
- size: `464`
- prototype: `bool __fastcall(AppReadiness::PackageInfo *__hidden this, struct AppReadiness::User *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180002958`
- `0x18001870c`
- `0x180027a4c`
- `0x1800382e0`
- `0x18003ecb4`
- `0x180060c00`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060d9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060daf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060d9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060daf`

## string_xrefs

- `0x180060c81`: `onecoreuap\shell\appreadiness\src\core\packageinfo.cpp`
- `0x180060cee`: `onecoreuap\shell\appreadiness\src\core\packageinfo.cpp`
- `0x180060d48`: `onecoreuap\shell\appreadiness\src\core\packageinfo.cpp`
- `0x180060c8d`: `AppReadiness::PackageInfo::IsPackageFamilyInstalledFor`
- `0x180060cfa`: `AppReadiness::PackageInfo::IsPackageFamilyInstalledFor`
- `0x180060d54`: `AppReadiness::PackageInfo::IsPackageFamilyInstalledFor`
- `0x180060c94`: `packageManager->FindPackagesByUserSecurityIdPackageFamilyNameWithPackageTypes(userSidString.Get(), packageFamilyNameString.Get(), PackageTypes_Main, &packageIter)`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
bool __fastcall AppReadiness::PackageInfo::IsPackageFamilyInstalledFor(const WCHAR *this, const WCHAR *a2)
{
  void *v4; // rdi
  __int64 (__fastcall *v5)(void *, HSTRING, HSTRING, __int64, __int64 *); // rbx
  int v6; // eax
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, __int64 *); // rbx
  int v9; // eax
  int v10; // eax
  bool v11; // bl
  HSTRING v13; // [rsp+30h] [rbp-40h] BYREF
  void *v14; // [rsp+38h] [rbp-38h] BYREF
  _BYTE pExceptionObject[48]; // [rsp+40h] [rbp-30h] BYREF
  char v16; // [rsp+90h] [rbp+20h] BYREF
  __int64 v17; // [rsp+98h] [rbp+28h] BYREF
  __int64 v18; // [rsp+A0h] [rbp+30h] BYREF
  HSTRING string; // [rsp+A8h] [rbp+38h] BYREF

  AppReadiness::PackageInfo::GetPackageManager<Windows::Management::Deployment::IPackageManager2>(&v14);
  to_winstring(&v13, a2 + 32);
  to_winstring(&string, this + 20);
  v18 = 0;
  v4 = v14;
  v5 = *(__int64 (__fastcall **)(void *, HSTRING, HSTRING, __int64, __int64 *))(*(_QWORD *)v14 + 112LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
  v6 = v5(v4, v13, string, 1, &v18);
  if ( v6 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      v6,
      "packageManager->FindPackagesByUserSecurityIdPackageFamilyNameWithPackageTypes(userSidString.Get(), packageFamilyNa"
      "meString.Get(), PackageTypes_Main, &packageIter)",
      "AppReadiness::PackageInfo::IsPackageFamilyInstalledFor",
      "onecoreuap\\shell\\appreadiness\\src\\core\\packageinfo.cpp",
      235);
    throw (Windows::HResultException *)pExceptionObject;
  }
  v17 = 0;
  v7 = v18;
  v8 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v18 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
  v9 = v8(v7, &v17);
  if ( v9 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      v9,
      "packageIter->First(&iterator)",
      "AppReadiness::PackageInfo::IsPackageFamilyInstalledFor",
      "onecoreuap\\shell\\appreadiness\\src\\core\\packageinfo.cpp",
      237);
    throw (Windows::HResultException *)pExceptionObject;
  }
  v16 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v17 + 56LL))(v17, &v16);
  if ( v10 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      v10,
      "iterator->get_HasCurrent(&hasCurrent)",
      "AppReadiness::PackageInfo::IsPackageFamilyInstalledFor",
      "onecoreuap\\shell\\appreadiness\\src\\core\\packageinfo.cpp",
      239);
    throw (Windows::HResultException *)pExceptionObject;
  }
  v11 = v16 != 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v13);
  v13 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
  return v11;
}

```

## disassembly

```asm
0x180060c00  push    rbp
0x180060c02  push    rbx
0x180060c03  push    rdi
0x180060c04  mov     rbp, rsp
0x180060c07  sub     rsp, 70h
0x180060c0b  mov     rbx, rdx
0x180060c0e  mov     rdi, rcx
0x180060c11  lea     rcx, [rbp+var_38]
0x180060c15  call    ??$GetPackageManager@UIPackageManager2@Deployment@Management@Windows@@@PackageInfo@AppReadiness@@SA?AV?$ComPtr@UIPackageManager2@Deployment@Management@Windows@@@WRL@Microsoft@@XZ; AppReadiness::PackageInfo::GetPackageManager<Windows::Management::Deployment::IPackageManager2>(void)
0x180060c1a  nop
0x180060c1b  lea     rdx, [rbx+40h]; sourceString
0x180060c1f  lea     rcx, [rbp+var_40]; string
0x180060c23  call    ?to_winstring@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; to_winstring(std::wstring const &)
0x180060c28  nop
0x180060c29  lea     rdx, [rdi+28h]; sourceString
0x180060c2d  lea     rcx, [rbp+string]; string
0x180060c31  call    ?to_winstring@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; to_winstring(std::wstring const &)
0x180060c36  nop
0x180060c37  mov     [rbp+arg_10], 0
0x180060c3f  mov     rdi, [rbp+var_38]
0x180060c43  mov     rax, [rdi]
0x180060c46  mov     rbx, [rax+70h]
0x180060c4a  lea     rcx, [rbp+arg_10]
0x180060c4e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180060c53  lea     rax, [rbp+arg_10]
0x180060c57  mov     [rsp+70h+var_50], rax
0x180060c5c  mov     r9d, 1
0x180060c62  mov     r8, [rbp+string]
0x180060c66  mov     rdx, [rbp+var_40]
0x180060c6a  mov     rcx, rdi
0x180060c6d  mov     rax, rbx
0x180060c70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060c75  test    eax, eax
0x180060c77  jns     short loc_180060CB7
0x180060c79  mov     [rsp+70h+var_48], 0EBh; int
0x180060c81  lea     rcx, aOnecoreuapShel; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180060c88  mov     [rsp+70h+var_50], rcx; char *
0x180060c8d  lea     r9, aAppreadinessPa_4; "AppReadiness::PackageInfo::IsPackageFam"...
0x180060c94  lea     r8, aPackagemanager_7; "packageManager->FindPackagesByUserSecur"...
0x180060c9b  mov     edx, eax; int
0x180060c9d  lea     rcx, [rbp+pExceptionObject]; this
0x180060ca1  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180060ca6  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180060cad  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180060cb1  call    _CxxThrowException_0
0x180060cb7  mov     [rbp+arg_8], 0
0x180060cbf  mov     rdi, [rbp+arg_10]
0x180060cc3  mov     rax, [rdi]
0x180060cc6  mov     rbx, [rax+30h]
0x180060cca  lea     rcx, [rbp+arg_8]
0x180060cce  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180060cd3  lea     rdx, [rbp+arg_8]
0x180060cd7  mov     rcx, rdi
0x180060cda  mov     rax, rbx
0x180060cdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060ce2  test    eax, eax
0x180060ce4  jns     short loc_180060D24
0x180060ce6  mov     [rsp+70h+var_48], 0EDh; int
0x180060cee  lea     rcx, aOnecoreuapShel; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180060cf5  mov     [rsp+70h+var_50], rcx; char *
0x180060cfa  lea     r9, aAppreadinessPa_4; "AppReadiness::PackageInfo::IsPackageFam"...
0x180060d01  lea     r8, aPackageiterFir; "packageIter->First(&iterator)"
0x180060d08  mov     edx, eax; int
0x180060d0a  lea     rcx, [rbp+pExceptionObject]; this
0x180060d0e  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180060d13  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180060d1a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180060d1e  call    _CxxThrowException_0
0x180060d24  mov     [rbp+arg_0], 0
0x180060d28  mov     rcx, [rbp+arg_8]
0x180060d2c  mov     rax, [rcx]
0x180060d2f  lea     rdx, [rbp+arg_0]
0x180060d33  mov     rax, [rax+38h]
0x180060d37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060d3c  test    eax, eax
0x180060d3e  jns     short loc_180060D7E
0x180060d40  mov     [rsp+70h+var_48], 0EFh; int
0x180060d48  lea     rcx, aOnecoreuapShel; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180060d4f  mov     [rsp+70h+var_50], rcx; char *
0x180060d54  lea     r9, aAppreadinessPa_4; "AppReadiness::PackageInfo::IsPackageFam"...
0x180060d5b  lea     r8, aIteratorGetHas_0; "iterator->get_HasCurrent(&hasCurrent)"
0x180060d62  mov     edx, eax; int
0x180060d64  lea     rcx, [rbp+pExceptionObject]; this
0x180060d68  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180060d6d  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180060d74  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180060d78  call    _CxxThrowException_0
0x180060d7e  cmp     [rbp+arg_0], 0
0x180060d82  setnz   bl
0x180060d85  lea     rcx, [rbp+arg_8]
0x180060d89  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180060d8e  nop
0x180060d8f  lea     rcx, [rbp+arg_10]
0x180060d93  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180060d98  nop
0x180060d99  mov     rcx, [rbp+string]; string
0x180060d9d  call    cs:__imp_WindowsDeleteString
0x180060da3  mov     [rbp+string], 0
0x180060dab  mov     rcx, [rbp+var_40]; string
0x180060daf  call    cs:__imp_WindowsDeleteString
0x180060db5  mov     [rbp+var_40], 0
0x180060dbd  lea     rcx, [rbp+var_38]
0x180060dc1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180060dc6  mov     al, bl
0x180060dc8  add     rsp, 70h
0x180060dcc  pop     rdi
0x180060dcd  pop     rbx
0x180060dce  pop     rbp
0x180060dcf  retn
```
