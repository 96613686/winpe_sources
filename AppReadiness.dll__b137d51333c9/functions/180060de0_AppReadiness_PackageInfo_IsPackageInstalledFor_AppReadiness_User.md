# AppReadiness::PackageInfo::IsPackageInstalledFor(AppReadiness::User *)

- ea: `0x180060de0`
- end: `0x180060f6b`
- name: `?IsPackageInstalledFor@PackageInfo@AppReadiness@@UEAA_NPEAVUser@2@@Z`
- size: `395`
- prototype: `bool __fastcall(AppReadiness::PackageInfo *__hidden this, struct AppReadiness::User *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180002958`
- `0x18001835c`
- `0x18001870c`
- `0x180027a4c`
- `0x18003ecb4`
- `0x180060de0`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060f38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060f4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060f38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060f4a`
- `AppXDeploymentClient!__imp_GetApplicability` at `0x180060e1e`
- `AppXDeploymentClient!__imp_GetApplicability` at `0x180060e1e`

## string_xrefs

- `0x180060e30`: `onecoreuap\shell\appreadiness\src\core\packageinfo.cpp`
- `0x180060e85`: `onecoreuap\shell\appreadiness\src\core\packageinfo.cpp`
- `0x180060e43`: `GetApplicability(m_packageId.c_str(), user->GetUserSid().c_str(), &appState)`
- `0x180060e3c`: `AppReadiness::PackageInfo::IsPackageInstalledFor`
- `0x180060e91`: `AppReadiness::PackageInfo::IsPackageInstalledFor`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
bool __fastcall AppReadiness::PackageInfo::IsPackageInstalledFor(AppReadiness::PackageInfo *this, const WCHAR *a2)
{
  _QWORD *v3; // rdx
  _QWORD *v4; // rcx
  int Applicability; // eax
  const WCHAR *v7; // rbx
  __int64 v8; // rdi
  int (__fastcall *v9)(__int64, HSTRING, HSTRING, __int64 *); // rbx
  bool v10; // bl
  HSTRING v11; // [rsp+30h] [rbp-30h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+38h] [rbp-28h] BYREF
  __int64 v13; // [rsp+80h] [rbp+20h] BYREF
  __int64 v14; // [rsp+90h] [rbp+30h] BYREF
  HSTRING string; // [rsp+98h] [rbp+38h] BYREF

  if ( (*((_BYTE *)this + 140) & 2) != 0 )
  {
    LODWORD(v13) = 0;
    v3 = a2 + 32;
    if ( v3[3] > 7u )
      v3 = (_QWORD *)*v3;
    v4 = (_QWORD *)((char *)this + 72);
    if ( v4[3] > 7u )
      v4 = (_QWORD *)*v4;
    Applicability = GetApplicability(v4, v3, &v13);
    if ( Applicability < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pExceptionObject,
        Applicability,
        "GetApplicability(m_packageId.c_str(), user->GetUserSid().c_str(), &appState)",
        "AppReadiness::PackageInfo::IsPackageInstalledFor",
        "onecoreuap\\shell\\appreadiness\\src\\core\\packageinfo.cpp",
        215);
      throw (Windows::HResultException *)pExceptionObject;
    }
    return (_DWORD)v13 == 2;
  }
  else
  {
    v7 = (const WCHAR *)((char *)this + 72);
    if ( !*((_QWORD *)this + 11) )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pExceptionObject,
        -2147019873,
        "!GetPackageId().empty()",
        "AppReadiness::PackageInfo::IsPackageInstalledFor",
        "onecoreuap\\shell\\appreadiness\\src\\core\\packageinfo.cpp",
        219);
      throw (Windows::HResultException *)pExceptionObject;
    }
    AppReadiness::PackageInfo::GetPackageManager<Windows::Management::Deployment::IPackageManager>(&v13);
    to_winstring(&v11, a2 + 32);
    to_winstring(&string, v7);
    v14 = 0;
    v8 = v13;
    v9 = *(int (__fastcall **)(__int64, HSTRING, HSTRING, __int64 *))(*(_QWORD *)v13 + 168LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
    v10 = v9(v8, v11, string, &v14) >= 0 && v14;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(v11);
    v11 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
    return v10;
  }
}

```

## disassembly

```asm
0x180060de0  push    rbp
0x180060de2  push    rbx
0x180060de3  push    rdi
0x180060de4  mov     rbp, rsp
0x180060de7  sub     rsp, 60h
0x180060deb  mov     rdi, rdx
0x180060dee  test    byte ptr [rcx+8Ch], 2
0x180060df5  jz      short loc_180060E72
0x180060df7  mov     dword ptr [rbp+arg_0], 0
0x180060dfe  add     rdx, 40h ; '@'
0x180060e02  cmp     qword ptr [rdx+18h], 7
0x180060e07  jbe     short loc_180060E0C
0x180060e09  mov     rdx, [rdx]
0x180060e0c  add     rcx, 48h ; 'H'
0x180060e10  cmp     qword ptr [rcx+18h], 7
0x180060e15  jbe     short loc_180060E1A
0x180060e17  mov     rcx, [rcx]
0x180060e1a  lea     r8, [rbp+arg_0]
0x180060e1e  call    cs:__imp_GetApplicability
0x180060e24  test    eax, eax
0x180060e26  jns     short loc_180060E66
0x180060e28  mov     [rsp+60h+var_38], 0D7h; int
0x180060e30  lea     rcx, aOnecoreuapShel; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180060e37  mov     [rsp+60h+var_40], rcx; char *
0x180060e3c  lea     r9, aAppreadinessPa_3; "AppReadiness::PackageInfo::IsPackageIns"...
0x180060e43  lea     r8, aGetapplicabili; "GetApplicability(m_packageId.c_str(), u"...
0x180060e4a  mov     edx, eax; int
0x180060e4c  lea     rcx, [rbp+pExceptionObject]; this
0x180060e50  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180060e55  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180060e5c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180060e60  call    _CxxThrowException_0
0x180060e66  cmp     dword ptr [rbp+arg_0], 2
0x180060e6a  setz    al
0x180060e6d  jmp     loc_180060F63
0x180060e72  lea     rbx, [rcx+48h]
0x180060e76  cmp     qword ptr [rbx+10h], 0
0x180060e7b  jnz     short loc_180060EBE
0x180060e7d  mov     [rsp+60h+var_38], 0DBh; int
0x180060e85  lea     rcx, aOnecoreuapShel; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180060e8c  mov     [rsp+60h+var_40], rcx; char *
0x180060e91  lea     r9, aAppreadinessPa_3; "AppReadiness::PackageInfo::IsPackageIns"...
0x180060e98  lea     r8, aGetpackageidEm; "!GetPackageId().empty()"
0x180060e9f  mov     edx, 8007139Fh; int
0x180060ea4  lea     rcx, [rbp+pExceptionObject]; this
0x180060ea8  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180060ead  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180060eb4  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180060eb8  call    _CxxThrowException_0
0x180060ebe  lea     rcx, [rbp+arg_0]
0x180060ec2  call    ??$GetPackageManager@UIPackageManager@Deployment@Management@Windows@@@PackageInfo@AppReadiness@@SA?AV?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@XZ; AppReadiness::PackageInfo::GetPackageManager<Windows::Management::Deployment::IPackageManager>(void)
0x180060ec7  nop
0x180060ec8  lea     rdx, [rdi+40h]; sourceString
0x180060ecc  lea     rcx, [rbp+var_30]; string
0x180060ed0  call    ?to_winstring@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; to_winstring(std::wstring const &)
0x180060ed5  nop
0x180060ed6  mov     rdx, rbx; sourceString
0x180060ed9  lea     rcx, [rbp+string]; string
0x180060edd  call    ?to_winstring@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; to_winstring(std::wstring const &)
0x180060ee2  nop
0x180060ee3  mov     [rbp+arg_10], 0
0x180060eeb  mov     rdi, [rbp+arg_0]
0x180060eef  mov     rax, [rdi]
0x180060ef2  mov     rbx, [rax+0A8h]
0x180060ef9  lea     rcx, [rbp+arg_10]
0x180060efd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180060f02  lea     r9, [rbp+arg_10]
0x180060f06  mov     r8, [rbp+string]
0x180060f0a  mov     rdx, [rbp+var_30]
0x180060f0e  mov     rcx, rdi
0x180060f11  mov     rax, rbx
0x180060f14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060f19  test    eax, eax
0x180060f1b  js      short loc_180060F28
0x180060f1d  cmp     [rbp+arg_10], 0
0x180060f22  jz      short loc_180060F28
0x180060f24  mov     bl, 1
0x180060f26  jmp     short loc_180060F2A
0x180060f28  xor     bl, bl
0x180060f2a  lea     rcx, [rbp+arg_10]
0x180060f2e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180060f33  nop
0x180060f34  mov     rcx, [rbp+string]; string
0x180060f38  call    cs:__imp_WindowsDeleteString
0x180060f3e  mov     [rbp+string], 0
0x180060f46  mov     rcx, [rbp+var_30]; string
0x180060f4a  call    cs:__imp_WindowsDeleteString
0x180060f50  mov     [rbp+var_30], 0
0x180060f58  lea     rcx, [rbp+arg_0]
0x180060f5c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180060f61  mov     al, bl
0x180060f63  add     rsp, 60h
0x180060f67  pop     rdi
0x180060f68  pop     rbx
0x180060f69  pop     rbp
0x180060f6a  retn
```
