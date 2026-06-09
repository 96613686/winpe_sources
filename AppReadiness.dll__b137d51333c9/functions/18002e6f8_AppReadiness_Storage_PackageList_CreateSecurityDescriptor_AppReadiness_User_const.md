# AppReadiness::Storage::PackageList::CreateSecurityDescriptor(AppReadiness::User const *)

- ea: `0x18002e6f8`
- end: `0x18002e8b2`
- name: `?CreateSecurityDescriptor@PackageList@Storage@AppReadiness@@CA?AV?$unique_ptr@U_SECURITY_DESCRIPTOR@@U?$LocalMem_Deleter@U_SECURITY_DESCRIPTOR@@@@@std@@PEBVUser@3@@Z`
- size: `442`
- prototype: `PSECURITY_DESCRIPTOR *__fastcall(PSECURITY_DESCRIPTOR *, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009f50`

## callees

- `0x180009d80`
- `0x18000e4a0`
- `0x18001caa0`
- `0x180027a4c`
- `0x18002e6f8`
- `0x18002ecbc`
- `0x18002edec`
- `0x18003e210`
- `0x18003ecb4`
- `0x1800473d8`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002e828`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002e828`

## string_xrefs

- `0x18002e7af`: `onecoreuap\shell\appreadiness\src\core\packagelist.cpp`
- `0x18002e843`: `onecoreuap\shell\appreadiness\src\core\packagelist.cpp`
- `0x18002e7bb`: `AppReadiness::Storage::PackageList::CreateSecurityDescriptor`
- `0x18002e84f`: `AppReadiness::Storage::PackageList::CreateSecurityDescriptor`
- `0x18002e856`: `ConvertStringSecurityDescriptorToSecurityDescriptor(userKeyAcl.c_str(), SDDL_REVISION_1, &rawPtr, nullptr)`
- `0x18002e7c2`: `StringCchPrintf(userKeyReadAcl, _countof(userKeyReadAcl), c_UserKeyReadAccess, user->GetUserSid().c_str())`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
PSECURITY_DESCRIPTOR *__fastcall AppReadiness::Storage::PackageList::CreateSecurityDescriptor(
        PSECURITY_DESCRIPTOR *a1,
        __int64 a2)
{
  __int64 *v4; // rdx
  int v5; // eax
  __int64 v6; // r8
  const WCHAR *v7; // rcx
  int Error; // eax
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR StringSecurityDescriptor[5]; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 v13[264]; // [rsp+90h] [rbp-70h] BYREF

  SecurityDescriptor = a1;
  std::wstring::wstring(StringSecurityDescriptor);
  if ( qword_1800A4600 )
  {
    v4 = &AppReadiness::Storage::PackageList::s_userKeyAcl;
    if ( (unsigned __int64)qword_1800A4608 > 7 )
      v4 = (__int64 *)AppReadiness::Storage::PackageList::s_userKeyAcl;
    std::wstring::assign(StringSecurityDescriptor, v4);
  }
  else
  {
    std::wstring::assign(
      StringSecurityDescriptor,
      L"D:P(A;OICI;KA;;;BA)(A;OICI;KA;;;S-1-5-80-2020831507-1298702824-3288167190-116113825-4190209)");
    if ( !*(_BYTE *)(a2 + 176) )
    {
      v5 = StringCchPrintfW(v13, 0x104u, L"(A;OICI;KR;;;%ls)");
      if ( v5 < 0 )
      {
        Windows::HResultException::HResultException(
          (Windows::HResultException *)pExceptionObject,
          v5,
          "StringCchPrintf(userKeyReadAcl, _countof(userKeyReadAcl), c_UserKeyReadAccess, user->GetUserSid().c_str())",
          "AppReadiness::Storage::PackageList::CreateSecurityDescriptor",
          "onecoreuap\\shell\\appreadiness\\src\\core\\packagelist.cpp",
          63);
        throw (Windows::HResultException *)pExceptionObject;
      }
      v6 = -1;
      do
        ++v6;
      while ( v13[v6] );
      std::wstring::_Append<unsigned short>(StringSecurityDescriptor);
    }
  }
  SecurityDescriptor = 0;
  v7 = (const WCHAR *)StringSecurityDescriptor;
  if ( StringSecurityDescriptor[3] > (LPCWSTR)7 )
    v7 = StringSecurityDescriptor[0];
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v7, 1u, &SecurityDescriptor, 0) )
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pExceptionObject,
        Error,
        "ConvertStringSecurityDescriptorToSecurityDescriptor(userKeyAcl.c_str(), SDDL_REVISION_1, &rawPtr, nullptr)",
        "AppReadiness::Storage::PackageList::CreateSecurityDescriptor",
        "onecoreuap\\shell\\appreadiness\\src\\core\\packagelist.cpp",
        69);
      throw (Windows::HResultException *)pExceptionObject;
    }
  }
  *a1 = SecurityDescriptor;
  std::pair<std::wstring,enum AppReadiness::Storage::PackageOperation>::~pair<std::wstring,enum AppReadiness::Storage::PackageOperation>(StringSecurityDescriptor);
  return a1;
}

```

## disassembly

```asm
0x18002e6f8  mov     [rsp-8+arg_10], rbx
0x18002e6fd  push    rbp
0x18002e6fe  push    rsi
0x18002e6ff  push    rdi
0x18002e700  lea     rbp, [rsp-1B0h]
0x18002e708  sub     rsp, 2B0h
0x18002e70f  mov     rax, cs:__security_cookie
0x18002e716  xor     rax, rsp
0x18002e719  mov     [rbp+1C0h+var_20], rax
0x18002e720  mov     rdi, rdx
0x18002e723  mov     rbx, rcx
0x18002e726  mov     [rsp+2C0h+SecurityDescriptor], rcx
0x18002e72b  xor     esi, esi
0x18002e72d  lea     rcx, [rsp+2C0h+StringSecurityDescriptor]
0x18002e732  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002e737  nop
0x18002e738  lea     rcx, [rsp+2C0h+StringSecurityDescriptor]
0x18002e73d  cmp     cs:qword_1800A4600, rsi
0x18002e744  jz      short loc_18002E767
0x18002e746  lea     rdx, ?s_userKeyAcl@PackageList@Storage@AppReadiness@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring AppReadiness::Storage::PackageList::s_userKeyAcl
0x18002e74d  cmp     cs:qword_1800A4608, 7
0x18002e755  cmova   rdx, cs:?s_userKeyAcl@PackageList@Storage@AppReadiness@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring AppReadiness::Storage::PackageList::s_userKeyAcl
0x18002e75d  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18002e762  jmp     loc_18002E807
0x18002e767  lea     rdx, aDPAOiciKaBaAOi; "D:P(A;OICI;KA;;;BA)(A;OICI;KA;;;S-1-5-8"...
0x18002e76e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18002e773  cmp     [rdi+0B0h], sil
0x18002e77a  jnz     loc_18002E807
0x18002e780  lea     r9, [rdi+40h]
0x18002e784  cmp     qword ptr [r9+18h], 7
0x18002e789  jbe     short loc_18002E78E
0x18002e78b  mov     r9, [r9]
0x18002e78e  lea     r8, aAOiciKrLs; "(A;OICI;KR;;;%ls)"
0x18002e795  mov     edx, 104h; unsigned __int64
0x18002e79a  lea     rcx, [rbp+1C0h+var_230]; unsigned __int16 *
0x18002e79e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002e7a3  test    eax, eax
0x18002e7a5  jns     short loc_18002E7E7
0x18002e7a7  mov     [rsp+2C0h+var_298], 3Fh ; '?'; int
0x18002e7af  lea     rcx, aOnecoreuapShel_10; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18002e7b6  mov     [rsp+2C0h+var_2A0], rcx; char *
0x18002e7bb  lea     r9, aAppreadinessSt_3; "AppReadiness::Storage::PackageList::Cre"...
0x18002e7c2  lea     r8, aStringcchprint_1; "StringCchPrintf(userKeyReadAcl, _counto"...
0x18002e7c9  mov     edx, eax; int
0x18002e7cb  lea     rcx, [rsp+2C0h+pExceptionObject]; this
0x18002e7d0  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18002e7d5  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18002e7dc  lea     rcx, [rsp+2C0h+pExceptionObject]; pExceptionObject
0x18002e7e1  call    _CxxThrowException_0
0x18002e7e7  lea     rax, [rbp+1C0h+var_230]
0x18002e7eb  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002e7ef  inc     r8
0x18002e7f2  cmp     [rax+r8*2], si
0x18002e7f7  jnz     short loc_18002E7EF
0x18002e7f9  lea     rdx, [rbp+1C0h+var_230]
0x18002e7fd  lea     rcx, [rsp+2C0h+StringSecurityDescriptor]; Src
0x18002e802  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18002e807  mov     [rsp+2C0h+SecurityDescriptor], rsi
0x18002e80c  lea     rcx, [rsp+2C0h+StringSecurityDescriptor]
0x18002e811  cmp     [rbp+1C0h+var_240], 7
0x18002e816  cmova   rcx, [rsp+2C0h+StringSecurityDescriptor]; StringSecurityDescriptor
0x18002e81c  xor     r9d, r9d; SecurityDescriptorSize
0x18002e81f  lea     r8, [rsp+2C0h+SecurityDescriptor]; SecurityDescriptor
0x18002e824  lea     edx, [r9+1]; StringSDRevision
0x18002e828  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18002e82e  test    eax, eax
0x18002e830  jnz     short loc_18002E87B
0x18002e832  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002e837  test    eax, eax
0x18002e839  jns     short loc_18002E87B
0x18002e83b  mov     [rsp+2C0h+var_298], 45h ; 'E'; int
0x18002e843  lea     rcx, aOnecoreuapShel_10; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18002e84a  mov     [rsp+2C0h+var_2A0], rcx; char *
0x18002e84f  lea     r9, aAppreadinessSt_3; "AppReadiness::Storage::PackageList::Cre"...
0x18002e856  lea     r8, aConvertstrings_1; "ConvertStringSecurityDescriptorToSecuri"...
0x18002e85d  mov     edx, eax; int
0x18002e85f  lea     rcx, [rsp+2C0h+pExceptionObject]; this
0x18002e864  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18002e869  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18002e870  lea     rcx, [rsp+2C0h+pExceptionObject]; pExceptionObject
0x18002e875  call    _CxxThrowException_0
0x18002e87b  mov     rcx, [rsp+2C0h+SecurityDescriptor]
0x18002e880  mov     [rbx], rcx
0x18002e883  lea     rcx, [rsp+2C0h+StringSecurityDescriptor]
0x18002e888  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4PackageOperation@Storage@AppReadiness@@@std@@QEAA@XZ; std::pair<std::wstring,AppReadiness::Storage::PackageOperation>::~pair<std::wstring,AppReadiness::Storage::PackageOperation>(void)
0x18002e88d  mov     rax, rbx
0x18002e890  mov     rcx, [rbp+1C0h+var_20]
0x18002e897  xor     rcx, rsp; StackCookie
0x18002e89a  call    __security_check_cookie
0x18002e89f  mov     rbx, [rsp+2C0h+arg_10]
0x18002e8a7  add     rsp, 2B0h
0x18002e8ae  pop     rdi
0x18002e8af  pop     rsi
0x18002e8b0  pop     rbp
0x18002e8b1  retn
```
