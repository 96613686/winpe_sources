# AppReadiness::PackageInfo::GetPackageFullName(Windows::ApplicationModel::IPackage *)

- ea: `0x180037528`
- end: `0x180037669`
- name: `?GetPackageFullName@PackageInfo@AppReadiness@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUIPackage@ApplicationModel@Windows@@@Z`
- size: `321`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180017e74`
- `0x18002bcc0`

## callees

- `0x180027a4c`
- `0x180028814`
- `0x180037528`
- `0x18003ecb4`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800375af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003762a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800375af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003762a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180037614`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180037614`

## string_xrefs

- `0x180037564`: `onecoreuap\shell\appreadiness\src\core\packageinfo.cpp`
- `0x1800375d8`: `onecoreuap\shell\appreadiness\src\core\packageinfo.cpp`
- `0x180037570`: `AppReadiness::PackageInfo::GetPackageFullName`
- `0x1800375e4`: `AppReadiness::PackageInfo::GetPackageFullName`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall AppReadiness::PackageInfo::GetPackageFullName(__int64 a1, __int64 a2)
{
  int v3; // eax
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, HSTRING *); // rbx
  int v6; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v8; // rcx
  _BYTE pExceptionObject[40]; // [rsp+38h] [rbp-28h] BYREF
  HSTRING string; // [rsp+88h] [rbp+28h] BYREF
  __int64 v12; // [rsp+90h] [rbp+30h] BYREF

  v12 = 0;
  v3 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 48LL))(a2, &v12);
  if ( v3 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      v3,
      "package->get_Id(packageId.GetAddressOf())",
      "AppReadiness::PackageInfo::GetPackageFullName",
      "onecoreuap\\shell\\appreadiness\\src\\core\\packageinfo.cpp",
      554);
    throw (Windows::HResultException *)pExceptionObject;
  }
  string = 0;
  v4 = v12;
  v5 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v12 + 96LL);
  WindowsDeleteString(0);
  string = 0;
  v6 = v5(v4, &string);
  if ( v6 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      v6,
      "packageId->get_FullName(str.GetAddressOf())",
      "AppReadiness::PackageInfo::GetPackageFullName",
      "onecoreuap\\shell\\appreadiness\\src\\core\\packageinfo.cpp",
      557);
    throw (Windows::HResultException *)pExceptionObject;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  std::wstring::wstring(a1, (__int64)StringRawBuffer);
  WindowsDeleteString(string);
  string = 0;
  v8 = v12;
  if ( v12 )
  {
    v12 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  return a1;
}

```

## disassembly

```asm
0x180037528  mov     [rsp-18h+arg_0], rbx
0x18003752d  push    rbp
0x18003752e  push    rsi
0x18003752f  push    rdi
0x180037530  mov     rbp, rsp
0x180037533  sub     rsp, 60h
0x180037537  mov     r8, rdx
0x18003753a  mov     rsi, rcx
0x18003753d  mov     [rbp+arg_10], 0
0x180037545  mov     rax, [rdx]
0x180037548  lea     rdx, [rbp+arg_10]
0x18003754c  mov     rcx, r8
0x18003754f  mov     rax, [rax+30h]
0x180037553  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037558  test    eax, eax
0x18003755a  jns     short loc_18003759A
0x18003755c  mov     [rsp+60h+var_38], 22Ah; int
0x180037564  lea     rcx, aOnecoreuapShel; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18003756b  mov     [rsp+60h+var_40], rcx; char *
0x180037570  lea     r9, aAppreadinessPa_8; "AppReadiness::PackageInfo::GetPackageFu"...
0x180037577  lea     r8, aPackageGetIdPa; "package->get_Id(packageId.GetAddressOf("...
0x18003757e  mov     edx, eax; int
0x180037580  lea     rcx, [rbp+pExceptionObject]; this
0x180037584  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180037589  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180037590  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180037594  call    _CxxThrowException_0
0x18003759a  mov     [rbp+string], 0
0x1800375a2  mov     rdi, [rbp+arg_10]
0x1800375a6  mov     rax, [rdi]
0x1800375a9  mov     rbx, [rax+60h]
0x1800375ad  xor     ecx, ecx; string
0x1800375af  call    cs:__imp_WindowsDeleteString
0x1800375b5  mov     [rbp+string], 0
0x1800375bd  lea     rdx, [rbp+string]
0x1800375c1  mov     rcx, rdi
0x1800375c4  mov     rax, rbx
0x1800375c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800375cc  test    eax, eax
0x1800375ce  jns     short loc_18003760E
0x1800375d0  mov     [rsp+60h+var_38], 22Dh; int
0x1800375d8  lea     rcx, aOnecoreuapShel; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x1800375df  mov     [rsp+60h+var_40], rcx; char *
0x1800375e4  lea     r9, aAppreadinessPa_8; "AppReadiness::PackageInfo::GetPackageFu"...
0x1800375eb  lea     r8, aPackageidGetFu_0; "packageId->get_FullName(str.GetAddressO"...
0x1800375f2  mov     edx, eax; int
0x1800375f4  lea     rcx, [rbp+pExceptionObject]; this
0x1800375f8  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x1800375fd  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180037604  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180037608  call    _CxxThrowException_0
0x18003760e  xor     edx, edx; length
0x180037610  mov     rcx, [rbp+string]; string
0x180037614  call    cs:__imp_WindowsGetStringRawBuffer
0x18003761a  mov     rdx, rax
0x18003761d  mov     rcx, rsi
0x180037620  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180037625  nop
0x180037626  mov     rcx, [rbp+string]; string
0x18003762a  call    cs:__imp_WindowsDeleteString
0x180037630  mov     [rbp+string], 0
0x180037638  mov     rcx, [rbp+arg_10]
0x18003763c  test    rcx, rcx
0x18003763f  jz      short loc_180037656
0x180037641  mov     [rbp+arg_10], 0
0x180037649  mov     rax, [rcx]
0x18003764c  mov     rax, [rax+10h]
0x180037650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037655  nop
0x180037656  mov     rax, rsi
0x180037659  mov     rbx, [rsp+60h+arg_0]
0x180037661  add     rsp, 60h
0x180037665  pop     rdi
0x180037666  pop     rsi
0x180037667  pop     rbp
0x180037668  retn
```
