# OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CalculateSurrogateDllPath(OSIntegration::DEH::ICollectorPackageInformation const *)

- ea: `0x18014edb4`
- end: `0x18014f280`
- name: `?CalculateSurrogateDllPath@ComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@AEAAJPEBUICollectorPackageInformation@34@@Z`
- size: `1228`
- prototype: `__int64 __fastcall(OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *__hidden this, const struct OSIntegration::DEH::ICollectorPackageInformation *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180164978`

## callees

- `0x18006a4c8`
- `0x180078818`
- `0x18007cdc0`
- `0x1800aed10`
- `0x1800af918`
- `0x180148b64`
- `0x1801490d8`
- `0x18014edb4`
- `0x180155a20`
- `0x180158000`
- `0x180158f20`
- `0x18015cfbc`
- `0x180169c98`
- `0x18016ace8`
- `0x1801ac010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014ee70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014ee8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014eea5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014ef1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014ef3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014ef54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014efb1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014efd0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014efe6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014f0e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014f108`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014f11e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014f18d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014f1ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014f1c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014ee70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014ee8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014eea5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014ef1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014ef3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014ef54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014efb1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014efd0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014efe6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014f0e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014f108`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014f11e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014f18d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014f1ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014f1c2`

## string_xrefs

- `0x18014f20d`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x18014f26d`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x18014f25a`: `!HasInprocServerDllForArchitecture(architecture)`
- `0x18014f206`: `OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CalculateSurrogateDllPath`
- `0x18014f266`: `OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CalculateSurrogateDllPath`

## pseudocode

```c
__int64 __fastcall OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CalculateSurrogateDllPath(
        OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *this,
        const struct OSIntegration::DEH::ICollectorPackageInformation *a2)
{
  unsigned int *v4; // rax
  unsigned int v5; // edx
  const struct OSIntegration::DEH::Internal::PerArchitectureInformation *ArchitectureByImageFileMachine; // rax
  __int64 InprocServerDllForArchitecture; // rax
  __int64 result; // rax
  int PackageArchitecture; // eax
  __int64 v10; // rsi
  __int64 *v11; // rdi
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // r9
  unsigned __int64 v15; // r14
  unsigned __int64 i; // rsi
  __int64 *v17; // r15
  __int64 v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rdx
  unsigned __int64 j; // rcx
  __int64 v22; // rsi
  __int64 v23; // rax
  __int64 v24; // rax
  char *v25; // [rsp+20h] [rbp-108h]
  char *v26; // [rsp+28h] [rbp-100h]
  char *v27; // [rsp+28h] [rbp-100h]
  int v28; // [rsp+30h] [rbp-F8h] BYREF
  __int64 v29; // [rsp+38h] [rbp-F0h]
  HSTRING string; // [rsp+40h] [rbp-E8h] BYREF
  int v31; // [rsp+48h] [rbp-E0h] BYREF
  char v32; // [rsp+4Ch] [rbp-DCh]
  _OWORD v33[10]; // [rsp+50h] [rbp-D8h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+128h] [rbp+0h]

  try
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl)
      && ((*(void (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 123) + 56LL))(*((_QWORD *)this + 123), &v31), v32) )
    {
      v4 = (unsigned int *)std::optional<unsigned int>::value(&v31);
      ArchitectureByImageFileMachine = OSIntegration::DEH::Internal::GetArchitectureByImageFileMachine(
                                         (OSIntegration::DEH::Internal *)*v4,
                                         v5);
      if ( !*((_BYTE *)this + *((int *)ArchitectureByImageFileMachine + 6) + 64) )
      {
        LODWORD(v27) = -2147418113;
        wil::details::in1diag5::Throw_Hr(
          retaddr,
          (void *)0x63D,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
          "OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CalculateSurrogateDllPath",
          "!HasInprocServerDllForArchitecture(architecture)",
          v27,
          v28);
      }
      InprocServerDllForArchitecture = OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::GetInprocServerDllForArchitecture(
                                         this,
                                         &string,
                                         ArchitectureByImageFileMachine);
      Optional<OpaqueString>::Optional<OpaqueString>(&v28, InprocServerDllForArchitecture);
      *((_BYTE *)this + 304) = v28;
      WindowsDeleteString(*((HSTRING *)this + 39));
      *((_QWORD *)this + 39) = v29;
      v29 = 0;
      WindowsDeleteString(0);
      v29 = 0;
      WindowsDeleteString(string);
      *((_DWORD *)this + 190) = *(_DWORD *)std::optional<unsigned int>::value(&v31);
      result = 0;
    }
    else
    {
      PackageArchitecture = OSIntegration::DEH::Internal::GetPackageArchitecture(a2);
      v10 = 5LL * PackageArchitecture;
      v11 = qword_1801C00F0;
      if ( *((_BYTE *)this + SLODWORD(qword_1801C00F0[5 * PackageArchitecture + 3]) + 64) )
      {
        v12 = OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::GetInprocServerDllForArchitecture(
                this,
                &string,
                &qword_1801C00F0[5 * PackageArchitecture]);
        Optional<OpaqueString>::Optional<OpaqueString>(&v28, v12);
        *((_BYTE *)this + 304) = v28;
        WindowsDeleteString(*((HSTRING *)this + 39));
        *((_QWORD *)this + 39) = v29;
        v29 = 0;
        WindowsDeleteString(0);
        v29 = 0;
        WindowsDeleteString(string);
        *((_DWORD *)this + 190) = WORD2(qword_1801C00F0[v10 + 1]);
        result = 0;
      }
      else if ( *((_BYTE *)this + 352) )
      {
        v13 = OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::GetInprocServerDllForArchitecture(
                this,
                &string,
                qword_1801C0118);
        Optional<OpaqueString>::Optional<OpaqueString>(&v28, v13);
        *((_BYTE *)this + 304) = v28;
        WindowsDeleteString(*((HSTRING *)this + 39));
        *((_QWORD *)this + 39) = v29;
        v29 = 0;
        WindowsDeleteString(0);
        v29 = 0;
        WindowsDeleteString(string);
        *((_DWORD *)this + 190) = 34404;
        result = 0;
      }
      else
      {
        memset_0(v33, 0, sizeof(v33));
        v15 = 0;
        for ( i = 0; i < 4; ++i )
        {
          v17 = &qword_1801C00F0[5 * i];
          if ( OSIntegration::DEH::Internal::PerArchitectureInformation::IsSupportedWowArchitecture((OSIntegration::DEH::Internal::PerArchitectureInformation *)v17) )
          {
            v18 = v15++;
            v19 = 5 * v18;
            *(_OWORD *)((char *)v33 + 8 * v19) = *(_OWORD *)v17;
            *(_OWORD *)((char *)&v33[1] + 8 * v19) = *((_OWORD *)v17 + 1);
            *((_QWORD *)&v33[2] + v19) = v17[4];
          }
        }
        LOBYTE(v14) = 0;
        std::_Sort_unchecked<OSIntegration::DEH::Internal::PerArchitectureInformation *,std::less<void>>(
          v33,
          (char *)v33 + 40 * v15,
          0xCCCCCCCCCCCCCCCDuLL * ((__int64)(40 * v15) >> 3),
          v14);
        for ( j = 0; j < v15; ++j )
        {
          v22 = 5 * j;
          if ( *((_BYTE *)this + *((int *)&v33[1] + 10 * j + 2) + 64) )
          {
            v23 = OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::GetInprocServerDllForArchitecture(
                    this,
                    &string,
                    (char *)v33 + 40 * j);
            Optional<OpaqueString>::Optional<OpaqueString>(&v28, v23);
            *((_BYTE *)this + 304) = v28;
            WindowsDeleteString(*((HSTRING *)this + 39));
            *((_QWORD *)this + 39) = v29;
            v29 = 0;
            WindowsDeleteString(0);
            v29 = 0;
            WindowsDeleteString(string);
            *((_DWORD *)this + 190) = *((unsigned __int16 *)v33 + 4 * v22 + 6);
            return 0;
          }
        }
        while ( v11 != (__int64 *)L"\"$" )
        {
          if ( *((_BYTE *)this + *((int *)v11 + 6) + 64) )
          {
            v24 = OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::GetInprocServerDllForArchitecture(
                    this,
                    &string,
                    v11);
            Optional<OpaqueString>::Optional<OpaqueString>(&v28, v24);
            *((_BYTE *)this + 304) = v28;
            WindowsDeleteString(*((HSTRING *)this + 39));
            *((_QWORD *)this + 39) = v29;
            v29 = 0;
            WindowsDeleteString(0);
            v29 = 0;
            WindowsDeleteString(string);
            *((_DWORD *)this + 190) = *((unsigned __int16 *)v11 + 6);
            return 0;
          }
          v11 += 5;
        }
        MicrosoftTelemetryAssertTriggeredNoArgs(L"\"$", v20);
        LODWORD(v27) = -2147418113;
        wil::details::in1diag5::Return_Hr(
          retaddr,
          (void *)0x689,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
          "OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CalculateSurrogateDllPath",
          "E_UNEXPECTED",
          v27,
          v28);
        result = 2147549183LL;
      }
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag5::Return_CaughtException(
                           retaddr,
                           (void *)0x68A,
                           (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
                           "OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CalculateSurrogateDllPath",
                           v25,
                           v26);
  }
  return result;
}

```

## disassembly

```asm
0x18014edb4  mov     [rsp+arg_10], rbx
0x18014edb9  push    rsi
0x18014edba  push    rdi
0x18014edbb  push    r12
0x18014edbd  push    r14
0x18014edbf  push    r15
0x18014edc1  sub     rsp, 100h
0x18014edc8  mov     rax, cs:__security_cookie
0x18014edcf  xor     rax, rsp
0x18014edd2  mov     [rsp+128h+var_38], rax
0x18014edda  mov     rdi, rdx
0x18014eddd  mov     rbx, rcx
0x18014ede0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x18014ede7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x18014edec  xor     r12d, r12d
0x18014edef  test    al, al
0x18014edf1  jz      loc_18014EECA
0x18014edf7  mov     rcx, [rbx+3D8h]
0x18014edfe  mov     rax, [rcx]
0x18014ee01  lea     rdx, [rsp+128h+var_E0]
0x18014ee06  mov     rax, [rax+38h]
0x18014ee0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014ee0f  cmp     [rsp+128h+var_DC], r12b
0x18014ee14  jz      loc_18014EECA
0x18014ee1a  lea     rcx, [rsp+128h+var_E0]
0x18014ee1f  call    ?value@?$optional@I@std@@QEGBAAEBIXZ; std::optional<uint>::value(void)
0x18014ee24  mov     ecx, [rax]; this
0x18014ee26  call    ?GetArchitectureByImageFileMachine@Internal@DEH@OSIntegration@@YAAEBUPerArchitectureInformation@123@I@Z; OSIntegration::DEH::Internal::GetArchitectureByImageFileMachine(uint)
0x18014ee2b  mov     rcx, [rsp+128h]; this
0x18014ee33  movsxd  rdx, dword ptr [rax+18h]
0x18014ee37  cmp     [rdx+rbx+40h], r12b
0x18014ee3c  jz      loc_18014F252
0x18014ee42  mov     r8, rax
0x18014ee45  lea     rdx, [rsp+128h+string]
0x18014ee4a  mov     rcx, rbx
0x18014ee4d  call    ?GetInprocServerDllForArchitecture@ComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@AEBA?AVOpaqueString@@AEBUPerArchitectureInformation@234@@Z; OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::GetInprocServerDllForArchitecture(OSIntegration::DEH::Internal::PerArchitectureInformation const &)
0x18014ee52  mov     rdx, rax
0x18014ee55  lea     rcx, [rsp+128h+var_F8]
0x18014ee5a  call    ??0?$Optional@VOpaqueString@@@@QEAA@AEBVOpaqueString@@@Z; Optional<OpaqueString>::Optional<OpaqueString>(OpaqueString const &)
0x18014ee5f  mov     al, byte ptr [rsp+128h+var_F8]
0x18014ee63  mov     [rbx+130h], al
0x18014ee69  mov     rcx, [rbx+138h]; string
0x18014ee70  call    cs:__imp_WindowsDeleteString
0x18014ee77  nop     dword ptr [rax+rax+00h]
0x18014ee7c  mov     rax, [rsp+128h+var_F0]
0x18014ee81  mov     [rbx+138h], rax
0x18014ee88  mov     [rsp+128h+var_F0], r12
0x18014ee8d  xor     ecx, ecx; string
0x18014ee8f  call    cs:__imp_WindowsDeleteString
0x18014ee96  nop     dword ptr [rax+rax+00h]
0x18014ee9b  mov     [rsp+128h+var_F0], r12
0x18014eea0  mov     rcx, [rsp+128h+string]; string
0x18014eea5  call    cs:__imp_WindowsDeleteString
0x18014eeac  nop     dword ptr [rax+rax+00h]
0x18014eeb1  lea     rcx, [rsp+128h+var_E0]
0x18014eeb6  call    ?value@?$optional@I@std@@QEGBAAEBIXZ; std::optional<uint>::value(void)
0x18014eebb  mov     eax, [rax]
0x18014eebd  mov     [rbx+2F8h], eax
0x18014eec3  xor     eax, eax
0x18014eec5  jmp     loc_18014F229
0x18014eeca  mov     rcx, rdi
0x18014eecd  call    ?GetPackageArchitecture@Internal@DEH@OSIntegration@@YA?AW4ComArchitecture@123@PEBUICollectorPackageInformation@23@@Z; OSIntegration::DEH::Internal::GetPackageArchitecture(OSIntegration::DEH::ICollectorPackageInformation const *)
0x18014eed2  movsxd  rcx, eax
0x18014eed5  lea     rsi, [rcx+rcx*4]
0x18014eed9  lea     rdi, qword_1801C00F0
0x18014eee0  movsxd  rax, dword ptr [rdi+rsi*8+18h]
0x18014eee5  cmp     [rax+rbx+40h], r12b
0x18014eeea  jz      loc_18014EF72
0x18014eef0  lea     r8, [rdi+rsi*8]
0x18014eef4  lea     rdx, [rsp+128h+string]
0x18014eef9  mov     rcx, rbx
0x18014eefc  call    ?GetInprocServerDllForArchitecture@ComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@AEBA?AVOpaqueString@@AEBUPerArchitectureInformation@234@@Z; OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::GetInprocServerDllForArchitecture(OSIntegration::DEH::Internal::PerArchitectureInformation const &)
0x18014ef01  mov     rdx, rax
0x18014ef04  lea     rcx, [rsp+128h+var_F8]
0x18014ef09  call    ??0?$Optional@VOpaqueString@@@@QEAA@AEBVOpaqueString@@@Z; Optional<OpaqueString>::Optional<OpaqueString>(OpaqueString const &)
0x18014ef0e  mov     al, byte ptr [rsp+128h+var_F8]
0x18014ef12  mov     [rbx+130h], al
0x18014ef18  mov     rcx, [rbx+138h]; string
0x18014ef1f  call    cs:__imp_WindowsDeleteString
0x18014ef26  nop     dword ptr [rax+rax+00h]
0x18014ef2b  mov     rax, [rsp+128h+var_F0]
0x18014ef30  mov     [rbx+138h], rax
0x18014ef37  mov     [rsp+128h+var_F0], r12
0x18014ef3c  xor     ecx, ecx; string
0x18014ef3e  call    cs:__imp_WindowsDeleteString
0x18014ef45  nop     dword ptr [rax+rax+00h]
0x18014ef4a  mov     [rsp+128h+var_F0], r12
0x18014ef4f  mov     rcx, [rsp+128h+string]; string
0x18014ef54  call    cs:__imp_WindowsDeleteString
0x18014ef5b  nop     dword ptr [rax+rax+00h]
0x18014ef60  movzx   eax, word ptr [rdi+rsi*8+0Ch]
0x18014ef65  mov     [rbx+2F8h], eax
0x18014ef6b  xor     eax, eax
0x18014ef6d  jmp     loc_18014F229
0x18014ef72  cmp     [rbx+160h], r12b
0x18014ef79  jz      loc_18014F003
0x18014ef7f  lea     r8, qword_1801C0118
0x18014ef86  lea     rdx, [rsp+128h+string]
0x18014ef8b  mov     rcx, rbx
0x18014ef8e  call    ?GetInprocServerDllForArchitecture@ComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@AEBA?AVOpaqueString@@AEBUPerArchitectureInformation@234@@Z; OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::GetInprocServerDllForArchitecture(OSIntegration::DEH::Internal::PerArchitectureInformation const &)
0x18014ef93  mov     rdx, rax
0x18014ef96  lea     rcx, [rsp+128h+var_F8]
0x18014ef9b  call    ??0?$Optional@VOpaqueString@@@@QEAA@AEBVOpaqueString@@@Z; Optional<OpaqueString>::Optional<OpaqueString>(OpaqueString const &)
0x18014efa0  mov     al, byte ptr [rsp+128h+var_F8]
0x18014efa4  mov     [rbx+130h], al
0x18014efaa  mov     rcx, [rbx+138h]; string
0x18014efb1  call    cs:__imp_WindowsDeleteString
0x18014efb8  nop     dword ptr [rax+rax+00h]
0x18014efbd  mov     rax, [rsp+128h+var_F0]
0x18014efc2  mov     [rbx+138h], rax
0x18014efc9  mov     [rsp+128h+var_F0], r12
0x18014efce  xor     ecx, ecx; string
0x18014efd0  call    cs:__imp_WindowsDeleteString
0x18014efd7  nop     dword ptr [rax+rax+00h]
0x18014efdc  mov     [rsp+128h+var_F0], r12
0x18014efe1  mov     rcx, [rsp+128h+string]; string
0x18014efe6  call    cs:__imp_WindowsDeleteString
0x18014efed  nop     dword ptr [rax+rax+00h]
0x18014eff2  mov     dword ptr [rbx+2F8h], 8664h
0x18014effc  xor     eax, eax
0x18014effe  jmp     loc_18014F229
0x18014f003  xor     edx, edx; Val
0x18014f005  mov     r8d, 0A0h; Size
0x18014f00b  lea     rcx, [rsp+128h+var_D8]; void *
0x18014f010  call    memset_0
0x18014f015  mov     r14, r12
0x18014f018  mov     rsi, r12
0x18014f01b  cmp     rsi, 4
0x18014f01f  jnb     short loc_18014F063
0x18014f021  lea     rax, [rsi+rsi*4]
0x18014f025  lea     r15, [rdi+rax*8]
0x18014f029  mov     rcx, r15; this
0x18014f02c  call    ?IsSupportedWowArchitecture@PerArchitectureInformation@Internal@DEH@OSIntegration@@QEBA_NXZ; OSIntegration::DEH::Internal::PerArchitectureInformation::IsSupportedWowArchitecture(void)
0x18014f031  test    al, al
0x18014f033  jz      short loc_18014F05E
0x18014f035  mov     rax, r14
0x18014f038  inc     r14
0x18014f03b  lea     rcx, [rax+rax*4]
0x18014f03f  movups  xmm0, xmmword ptr [r15]
0x18014f043  movups  [rsp+rcx*8+128h+var_D8], xmm0
0x18014f048  movups  xmm1, xmmword ptr [r15+10h]
0x18014f04d  movups  [rsp+rcx*8+128h+var_C8], xmm1
0x18014f052  movsd   xmm0, qword ptr [r15+20h]
0x18014f058  movsd   [rsp+rcx*8+128h+var_B8], xmm0
0x18014f05e  inc     rsi
0x18014f061  jmp     short loc_18014F01B
0x18014f063  lea     rax, [r14+r14*4]
0x18014f067  shl     rax, 3
0x18014f06b  mov     r9b, r12b
0x18014f06e  mov     r8, rax
0x18014f071  sar     r8, 3
0x18014f075  mov     rcx, 0CCCCCCCCCCCCCCCDh
0x18014f07f  imul    r8, rcx
0x18014f083  lea     rdx, [rsp+128h+var_D8]
0x18014f088  add     rdx, rax
0x18014f08b  lea     rcx, [rsp+128h+var_D8]
0x18014f090  call    ??$_Sort_unchecked@PEAUPerArchitectureInformation@Internal@DEH@OSIntegration@@U?$less@X@std@@@std@@YAXPEAUPerArchitectureInformation@Internal@DEH@OSIntegration@@0_JU?$less@X@0@@Z; std::_Sort_unchecked<OSIntegration::DEH::Internal::PerArchitectureInformation *,std::less<void>>(OSIntegration::DEH::Internal::PerArchitectureInformation *,OSIntegration::DEH::Internal::PerArchitectureInformation *,__int64,std::less<void>)
0x18014f095  mov     rcx, r12
0x18014f098  cmp     rcx, r14
0x18014f09b  jnb     loc_18014F144
0x18014f0a1  lea     rsi, [rcx+rcx*4]
0x18014f0a5  movsxd  rax, dword ptr [rsp+rsi*8+128h+var_C8+8]
0x18014f0aa  cmp     [rax+rbx+40h], r12b
0x18014f0af  jz      loc_18014F13C
0x18014f0b5  lea     r8, [rsp+128h+var_D8]
0x18014f0ba  lea     r8, [r8+rsi*8]
0x18014f0be  lea     rdx, [rsp+128h+string]
0x18014f0c3  mov     rcx, rbx
0x18014f0c6  call    ?GetInprocServerDllForArchitecture@ComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@AEBA?AVOpaqueString@@AEBUPerArchitectureInformation@234@@Z; OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::GetInprocServerDllForArchitecture(OSIntegration::DEH::Internal::PerArchitectureInformation const &)
0x18014f0cb  mov     rdx, rax
0x18014f0ce  lea     rcx, [rsp+128h+var_F8]
0x18014f0d3  call    ??0?$Optional@VOpaqueString@@@@QEAA@AEBVOpaqueString@@@Z; Optional<OpaqueString>::Optional<OpaqueString>(OpaqueString const &)
0x18014f0d8  mov     al, byte ptr [rsp+128h+var_F8]
0x18014f0dc  mov     [rbx+130h], al
0x18014f0e2  mov     rcx, [rbx+138h]; string
0x18014f0e9  call    cs:__imp_WindowsDeleteString
0x18014f0f0  nop     dword ptr [rax+rax+00h]
0x18014f0f5  mov     rax, [rsp+128h+var_F0]
0x18014f0fa  mov     [rbx+138h], rax
0x18014f101  mov     [rsp+128h+var_F0], r12
0x18014f106  xor     ecx, ecx; string
0x18014f108  call    cs:__imp_WindowsDeleteString
0x18014f10f  nop     dword ptr [rax+rax+00h]
0x18014f114  mov     [rsp+128h+var_F0], r12
0x18014f119  mov     rcx, [rsp+128h+string]; string
0x18014f11e  call    cs:__imp_WindowsDeleteString
0x18014f125  nop     dword ptr [rax+rax+00h]
0x18014f12a  movzx   eax, word ptr [rsp+rsi*8+128h+var_D8+0Ch]
0x18014f12f  mov     [rbx+2F8h], eax
0x18014f135  xor     eax, eax
0x18014f137  jmp     loc_18014F229
0x18014f13c  inc     rcx
0x18014f13f  jmp     loc_18014F098
0x18014f144  lea     rcx, CmSymbolicLinkValueName; "\"$"
0x18014f14b  cmp     rdi, rcx
0x18014f14e  jz      loc_18014F1E5
0x18014f154  movsxd  rax, dword ptr [rdi+18h]
0x18014f158  cmp     [rax+rbx+40h], r12b
0x18014f15d  jz      short loc_18014F1DC
0x18014f15f  mov     r8, rdi
0x18014f162  lea     rdx, [rsp+128h+string]
0x18014f167  mov     rcx, rbx
0x18014f16a  call    ?GetInprocServerDllForArchitecture@ComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@AEBA?AVOpaqueString@@AEBUPerArchitectureInformation@234@@Z; OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::GetInprocServerDllForArchitecture(OSIntegration::DEH::Internal::PerArchitectureInformation const &)
0x18014f16f  mov     rdx, rax
0x18014f172  lea     rcx, [rsp+128h+var_F8]
0x18014f177  call    ??0?$Optional@VOpaqueString@@@@QEAA@AEBVOpaqueString@@@Z; Optional<OpaqueString>::Optional<OpaqueString>(OpaqueString const &)
0x18014f17c  mov     al, byte ptr [rsp+128h+var_F8]
0x18014f180  mov     [rbx+130h], al
0x18014f186  mov     rcx, [rbx+138h]; string
0x18014f18d  call    cs:__imp_WindowsDeleteString
0x18014f194  nop     dword ptr [rax+rax+00h]
0x18014f199  mov     rax, [rsp+128h+var_F0]
0x18014f19e  mov     [rbx+138h], rax
0x18014f1a5  mov     [rsp+128h+var_F0], r12
0x18014f1aa  xor     ecx, ecx; string
0x18014f1ac  call    cs:__imp_WindowsDeleteString
0x18014f1b3  nop     dword ptr [rax+rax+00h]
0x18014f1b8  mov     [rsp+128h+var_F0], r12
0x18014f1bd  mov     rcx, [rsp+128h+string]; string
0x18014f1c2  call    cs:__imp_WindowsDeleteString
0x18014f1c9  nop     dword ptr [rax+rax+00h]
0x18014f1ce  movzx   eax, word ptr [rdi+0Ch]
0x18014f1d2  mov     [rbx+2F8h], eax
0x18014f1d8  xor     eax, eax
0x18014f1da  jmp     short loc_18014F229
0x18014f1dc  add     rdi, 28h ; '('
0x18014f1e0  jmp     loc_18014F14B
0x18014f1e5  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "false", "Broken architecture selection logic")
0x18014f1ea  mov     rcx, [rsp+128h]; this
0x18014f1f2  mov     dword ptr [rsp+128h+var_100], 8000FFFFh; char *
0x18014f1fa  lea     rax, aEUnexpected; "E_UNEXPECTED"
0x18014f201  mov     [rsp+128h+var_108], rax; char *
0x18014f206  lea     r9, aOsintegrationD_246; "OSIntegration::DEH::Internal::ComClassR"...
0x18014f20d  lea     r8, aOnecoreAdminAp_92; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18014f214  mov     edx, 689h; void *
0x18014f219  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18014f21e  mov     eax, 8000FFFFh
0x18014f223  jmp     short loc_18014F229
0x18014f225  mov     eax, [rsp+128h+var_E0]
0x18014f229  mov     rcx, [rsp+128h+var_38]
0x18014f231  xor     rcx, rsp; StackCookie
0x18014f234  call    __security_check_cookie
0x18014f239  mov     rbx, [rsp+128h+arg_10]
0x18014f241  add     rsp, 100h
0x18014f248  pop     r15
0x18014f24a  pop     r14
0x18014f24c  pop     r12
0x18014f24e  pop     rdi
0x18014f24f  pop     rsi
0x18014f250  retn
0x18014f252  mov     dword ptr [rsp+128h+var_100], 8000FFFFh; char *
0x18014f25a  lea     rax, aHasinprocserve; "!HasInprocServerDllForArchitecture(arch"...
0x18014f261  mov     [rsp+128h+var_108], rax; char *
0x18014f266  lea     r9, aOsintegrationD_246; "OSIntegration::DEH::Internal::ComClassR"...
0x18014f26d  lea     r8, aOnecoreAdminAp_92; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18014f274  mov     edx, 63Dh; void *
0x18014f279  call    ?Throw_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Throw_Hr(void *,uint,char const *,char const *,char const *,long)
```
