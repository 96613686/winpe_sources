# AppReadiness::IsPackageInLaunchAppAfterLogOnPolicyList(ushort const *)

- ea: `0x180006844`
- end: `0x180006910`
- name: `?IsPackageInLaunchAppAfterLogOnPolicyList@AppReadiness@@YA_NPEBG@Z`
- size: `204`
- prototype: `bool __fastcall(AppReadiness *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000619c`

## callees

- `0x180006844`
- `0x180033abc`
- `0x180039eec`
- `0x1800611fc`
- `0x180061550`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800068a6`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800068a6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800068c6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800068c6`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyString` at `0x180006869`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyString` at `0x180006869`

## string_xrefs

- `0x180006878`: `onecoreuap\shell\appreadiness\src\core\packageinfo.cpp`

## pseudocode

```c
bool __fastcall AppReadiness::IsPackageInLaunchAppAfterLogOnPolicyList(AppReadiness *this, const unsigned __int16 *a2)
{
  int PolicyString; // eax
  wchar_t *v4; // rcx
  wchar_t *v5; // rax
  __int64 v6; // rcx
  wil::TraceLoggingProvider *v7; // rax
  unsigned __int8 v8; // dl
  unsigned __int64 v9; // r8
  __int64 v10; // rcx
  AppReadiness::PackageInfoTraceProvider *v11; // rcx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  wchar_t *String; // [rsp+48h] [rbp+10h] BYREF
  wchar_t *Context; // [rsp+50h] [rbp+18h] BYREF

  String = 0;
  PolicyString = PolicyManager_GetPolicyString(L"ApplicationManagement", L"LaunchAppAfterLogOn", &String);
  if ( PolicyString < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x21,
      (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\core\\packageinfo.cpp",
      (const char *)(unsigned int)PolicyString,
      bIgnoreCase);
  v4 = String;
  Context = 0;
  while ( 1 )
  {
    v5 = wcstok_s(v4, L";", &Context);
    if ( !v5 )
      break;
    if ( CompareStringOrdinal((LPCWCH)this, -1, v5, -1, 1) == 2 )
    {
      v7 = (wil::TraceLoggingProvider *)wil::details::static_lazy<AppReadiness::PackageInfoTraceProvider>::get(
                                          v6,
                                          _lambda_a1f4f784950c8737cb1e8eb96c5f4a2e_::_lambda_invoker_cdecl_);
      if ( wil::TraceLoggingProvider::IsEnabled_(v7, v8, v9) )
      {
        wil::details::static_lazy<AppReadiness::PackageInfoTraceProvider>::get(
          v10,
          _lambda_a1f4f784950c8737cb1e8eb96c5f4a2e_::_lambda_invoker_cdecl_);
        AppReadiness::PackageInfoTraceProvider::PackageFamilyNameFoundInPolicy_(
          v11,
          (const unsigned __int16 *)this,
          L"LaunchAppAfterLogOn");
      }
      LOBYTE(v5) = 1;
      return (char)v5;
    }
    v4 = 0;
  }
  return (char)v5;
}

```

## disassembly

```asm
0x180006844  push    rbx
0x180006846  sub     rsp, 30h
0x18000684a  mov     rbx, rcx
0x18000684d  mov     [rsp+38h+String], 0
0x180006856  lea     rcx, aApplicationman; "ApplicationManagement"
0x18000685d  lea     r8, [rsp+38h+String]
0x180006862  lea     rdx, aLaunchappafter; "LaunchAppAfterLogOn"
0x180006869  call    cs:__imp_PolicyManager_GetPolicyString
0x18000686f  test    eax, eax
0x180006871  jns     short loc_18000688C
0x180006873  mov     rcx, [rsp+38h]; this
0x180006878  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18000687f  mov     r9d, eax; char *
0x180006882  mov     edx, 21h ; '!'; void *
0x180006887  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000688c  mov     rcx, [rsp+38h+String]; String
0x180006891  mov     [rsp+38h+Context], 0
0x18000689a  lea     r8, [rsp+38h+Context]; Context
0x18000689f  lea     rdx, Delimiter; ";"
0x1800068a6  call    cs:__imp_wcstok_s
0x1800068ac  test    rax, rax
0x1800068af  jz      short loc_18000690A
0x1800068b1  or      r9d, 0FFFFFFFFh; cchCount2
0x1800068b5  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x1800068bd  or      edx, r9d; cchCount1
0x1800068c0  mov     r8, rax; lpString2
0x1800068c3  mov     rcx, rbx; lpString1
0x1800068c6  call    cs:__imp_CompareStringOrdinal
0x1800068cc  cmp     eax, 2
0x1800068cf  jz      short loc_1800068D5
0x1800068d1  xor     ecx, ecx
0x1800068d3  jmp     short loc_18000689A
0x1800068d5  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_a1f4f784950c8737cb1e8eb96c5f4a2e_@@CA@XZ; _lambda_a1f4f784950c8737cb1e8eb96c5f4a2e_::_lambda_invoker_cdecl_(void)
0x1800068dc  call    ?get@?$static_lazy@VPackageInfoTraceProvider@AppReadiness@@@details@wil@@QEAAPEAVPackageInfoTraceProvider@AppReadiness@@P6AXXZ@Z; wil::details::static_lazy<AppReadiness::PackageInfoTraceProvider>::get(void (*)(void))
0x1800068e1  mov     rcx, rax; this
0x1800068e4  call    ?IsEnabled_@TraceLoggingProvider@wil@@IEBA_NE_K@Z; wil::TraceLoggingProvider::IsEnabled_(uchar,unsigned __int64)
0x1800068e9  test    al, al
0x1800068eb  jz      short loc_180006908
0x1800068ed  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_a1f4f784950c8737cb1e8eb96c5f4a2e_@@CA@XZ; _lambda_a1f4f784950c8737cb1e8eb96c5f4a2e_::_lambda_invoker_cdecl_(void)
0x1800068f4  call    ?get@?$static_lazy@VPackageInfoTraceProvider@AppReadiness@@@details@wil@@QEAAPEAVPackageInfoTraceProvider@AppReadiness@@P6AXXZ@Z; wil::details::static_lazy<AppReadiness::PackageInfoTraceProvider>::get(void (*)(void))
0x1800068f9  lea     r8, aLaunchappafter; "LaunchAppAfterLogOn"
0x180006900  mov     rdx, rbx; unsigned __int16 *
0x180006903  call    ?PackageFamilyNameFoundInPolicy_@PackageInfoTraceProvider@AppReadiness@@QEAAXPEBG0@Z; AppReadiness::PackageInfoTraceProvider::PackageFamilyNameFoundInPolicy_(ushort const *,ushort const *)
0x180006908  mov     al, 1
0x18000690a  add     rsp, 30h
0x18000690e  pop     rbx
0x18000690f  retn
```
