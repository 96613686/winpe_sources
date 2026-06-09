# OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CalculateSurrogateDllPath(OSIntegration::DEH::ICollectorPackageInformation const *)

- ea: `0x1801bad38`
- end: `0x1801bb278`
- name: `?CalculateSurrogateDllPath@ComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@AEAAJPEBUICollectorPackageInformation@34@@Z`
- size: `1344`
- prototype: `__int64 __fastcall(OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *__hidden this, const struct OSIntegration::DEH::ICollectorPackageInformation *)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1801cf4c8`

## callees

- `0x18009aff4`
- `0x1800b8300`
- `0x1800ebdf0`
- `0x1800f0260`
- `0x1800f10e4`
- `0x180139954`
- `0x1801b47b8`
- `0x1801b5568`
- `0x1801bad38`
- `0x1801c34b8`
- `0x1801c82a4`
- `0x1801d4344`
- `0x1801d4be4`
- `0x180211010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801bae3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801bae55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801bae65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801baf48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801baf61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801baf71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801bafc2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801bafdb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801bafeb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801bb137`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801bb150`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801bb160`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801bb1c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801bb1de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801bb1ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801bae3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801bae55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801bae65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801baf48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801baf61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801baf71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801bafc2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801bafdb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801bafeb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801bb137`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801bb150`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801bb160`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801bb1c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801bb1de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801bb1ee`

## string_xrefs

- `0x1801badfd`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x1801baea7`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x1801bb233`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x1801badea`: `!HasInprocServerDllForArchitecture(architecture)`
- `0x1801badf6`: `OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CalculateSurrogateDllPath`
- `0x1801bb22c`: `OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CalculateSurrogateDllPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CalculateSurrogateDllPath(
        OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *this,
        const struct OSIntegration::DEH::ICollectorPackageInformation *a2)
{
  int v4; // edx
  __int64 *i; // rdi
  __int64 InprocServerDllForArchitecture; // rax
  int v8; // eax
  __int64 v9; // rcx
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  __int64 *v14; // rdi
  int *v15; // rsi
  __int64 *v16; // r8
  __int64 *v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // r9
  unsigned __int64 v21; // r14
  unsigned __int64 j; // rsi
  __int64 *v23; // r15
  __int64 v24; // rax
  __int64 v25; // rcx
  unsigned __int64 k; // rcx
  __int64 v27; // rsi
  __int64 v28; // rax
  __int64 v29; // rax
  char *v30; // [rsp+28h] [rbp-100h]
  unsigned int v31; // [rsp+30h] [rbp-F8h] BYREF
  __int64 v32; // [rsp+38h] [rbp-F0h]
  HSTRING string; // [rsp+40h] [rbp-E8h] BYREF
  int v34; // [rsp+48h] [rbp-E0h] BYREF
  char v35; // [rsp+4Ch] [rbp-DCh]
  _OWORD v36[10]; // [rsp+50h] [rbp-D8h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+128h] [rbp+0h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
  {
    (*(void (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 123) + 56LL))(*((_QWORD *)this + 123), &v34);
    if ( v35 )
    {
      v4 = *(_DWORD *)std::optional<unsigned int>::value(&v34);
      for ( i = qword_18022AC20; ; i += 5 )
      {
        if ( i == (__int64 *)off_18022ACC0 )
        {
          LODWORD(v30) = 1168;
          wil::details::in1diag5::_Throw_Win32(
            retaddr,
            (void *)0x14B,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
            "OSIntegration::DEH::Internal::GetArchitectureByImageFileMachine",
            "ERROR_NOT_FOUND",
            v30,
            v31);
        }
        if ( *((unsigned __int16 *)i + 6) == v4 )
          break;
      }
      if ( !*((_BYTE *)this + *((int *)i + 6) + 64) )
      {
        LODWORD(v30) = -2147418113;
        wil::details::in1diag5::_Throw_Hr(
          retaddr,
          (void *)0x63D,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
          "OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CalculateSurrogateDllPath",
          "!HasInprocServerDllForArchitecture(architecture)",
          v30,
          v31);
      }
      InprocServerDllForArchitecture = OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::GetInprocServerDllForArchitecture(
                                         this,
                                         &string,
                                         i);
      Optional<OpaqueString>::Optional<OpaqueString>(&v31, InprocServerDllForArchitecture);
      *((_BYTE *)this + 304) = v31;
      WindowsDeleteString(*((HSTRING *)this + 39));
      *((_QWORD *)this + 39) = v32;
      v32 = 0;
      WindowsDeleteString(0);
      v32 = 0;
      WindowsDeleteString(string);
      *((_DWORD *)this + 190) = *(_DWORD *)std::optional<unsigned int>::value(&v34);
      return 0;
    }
  }
  v8 = (*(__int64 (__fastcall **)(const struct OSIntegration::DEH::ICollectorPackageInformation *))(*(_QWORD *)a2 + 96LL))(a2);
  if ( !v8 )
    goto LABEL_18;
  v10 = v8 - 5;
  if ( v10 )
  {
    v11 = v10 - 4;
    if ( v11 && (v12 = v11 - 2) != 0 )
    {
      v13 = v12 - 1;
      if ( v13 )
      {
        if ( v13 != 2 )
          MicrosoftTelemetryAssertTriggeredNoArgs(v9);
LABEL_18:
        v14 = qword_18022AC20;
        v15 = &dword_18022AC2C;
        v16 = qword_18022AC20;
        v17 = qword_18022AC38;
        goto LABEL_19;
      }
      v17 = qword_18022ACB0;
      v16 = &qword_18022AC98;
      v15 = &dword_18022ACA4;
    }
    else
    {
      v17 = qword_18022AC60;
      v16 = &qword_18022AC48;
      v15 = &dword_18022AC54;
    }
  }
  else
  {
    v17 = qword_18022AC88;
    v16 = &qword_18022AC70;
    v15 = &dword_18022AC7C;
  }
  v14 = qword_18022AC20;
LABEL_19:
  if ( *((_BYTE *)this + *(int *)v17 + 64) )
  {
    v18 = OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::GetInprocServerDllForArchitecture(
            this,
            &string,
            v16);
    Optional<OpaqueString>::Optional<OpaqueString>(&v31, v18);
    *((_BYTE *)this + 304) = v31;
    WindowsDeleteString(*((HSTRING *)this + 39));
    *((_QWORD *)this + 39) = v32;
    v32 = 0;
    WindowsDeleteString(0);
    v32 = 0;
    WindowsDeleteString(string);
    *((_DWORD *)this + 190) = *(unsigned __int16 *)v15;
    return 0;
  }
  else if ( *((_BYTE *)this + 352) )
  {
    v19 = OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::GetInprocServerDllForArchitecture(
            this,
            &string,
            &qword_18022AC48);
    Optional<OpaqueString>::Optional<OpaqueString>(&v31, v19);
    *((_BYTE *)this + 304) = v31;
    WindowsDeleteString(*((HSTRING *)this + 39));
    *((_QWORD *)this + 39) = v32;
    v32 = 0;
    WindowsDeleteString(0);
    v32 = 0;
    WindowsDeleteString(string);
    *((_DWORD *)this + 190) = 34404;
    return 0;
  }
  else
  {
    memset_0(v36, 0, sizeof(v36));
    v21 = 0;
    for ( j = 0; j < 4; ++j )
    {
      v23 = &qword_18022AC20[5 * j];
      if ( OSIntegration::DEH::Internal::PerArchitectureInformation::IsSupportedWowArchitecture((OSIntegration::DEH::Internal::PerArchitectureInformation *)v23) )
      {
        v24 = v21++;
        v25 = 5 * v24;
        *(_OWORD *)((char *)v36 + 8 * v25) = *(_OWORD *)v23;
        *(_OWORD *)((char *)&v36[1] + 8 * v25) = *((_OWORD *)v23 + 1);
        *((_QWORD *)&v36[2] + v25) = v23[4];
      }
    }
    LOBYTE(v20) = 0;
    std::_Sort_unchecked<OSIntegration::DEH::Internal::PerArchitectureInformation *,std::less<void>>(
      v36,
      (char *)v36 + 40 * v21,
      0xCCCCCCCCCCCCCCCDuLL * ((__int64)(40 * v21) >> 3),
      v20);
    for ( k = 0; k < v21; ++k )
    {
      v27 = 5 * k;
      if ( *((_BYTE *)this + *((int *)&v36[1] + 10 * k + 2) + 64) )
      {
        v28 = OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::GetInprocServerDllForArchitecture(
                this,
                &string,
                (char *)v36 + 40 * k);
        Optional<OpaqueString>::Optional<OpaqueString>(&v31, v28);
        *((_BYTE *)this + 304) = v31;
        WindowsDeleteString(*((HSTRING *)this + 39));
        *((_QWORD *)this + 39) = v32;
        v32 = 0;
        WindowsDeleteString(0);
        v32 = 0;
        WindowsDeleteString(string);
        *((_DWORD *)this + 190) = *((unsigned __int16 *)v36 + 4 * v27 + 6);
        return 0;
      }
    }
    while ( v14 != (__int64 *)off_18022ACC0 )
    {
      if ( *((_BYTE *)this + *((int *)v14 + 6) + 64) )
      {
        v29 = OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::GetInprocServerDllForArchitecture(
                this,
                &string,
                v14);
        Optional<OpaqueString>::Optional<OpaqueString>(&v31, v29);
        *((_BYTE *)this + 304) = v31;
        WindowsDeleteString(*((HSTRING *)this + 39));
        *((_QWORD *)this + 39) = v32;
        v32 = 0;
        WindowsDeleteString(0);
        v32 = 0;
        WindowsDeleteString(string);
        *((_DWORD *)this + 190) = *((unsigned __int16 *)v14 + 6);
        return 0;
      }
      v14 += 5;
    }
    MicrosoftTelemetryAssertTriggeredNoArgs(off_18022ACC0);
    LODWORD(v30) = -2147418113;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x689,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
      "OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CalculateSurrogateDllPath",
      "E_UNEXPECTED",
      v30,
      v31);
    return 2147549183LL;
  }
}

```

## disassembly

```asm
0x1801bad38  mov     [rsp+arg_10], rbx
0x1801bad3d  push    rsi
0x1801bad3e  push    rdi
0x1801bad3f  push    r12
0x1801bad41  push    r14
0x1801bad43  push    r15
0x1801bad45  sub     rsp, 100h
0x1801bad4c  mov     rax, cs:__security_cookie
0x1801bad53  xor     rax, rsp
0x1801bad56  mov     [rsp+128h+var_38], rax
0x1801bad5e  mov     rdi, rdx
0x1801bad61  mov     rbx, rcx
0x1801bad64  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1801bad6b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1801bad70  xor     r12d, r12d
0x1801bad73  test    al, al
0x1801bad75  jz      loc_1801BAEB9
0x1801bad7b  mov     rcx, [rbx+3D8h]
0x1801bad82  mov     rax, [rcx]
0x1801bad85  lea     rdx, [rsp+128h+var_E0]
0x1801bad8a  mov     rax, [rax+38h]
0x1801bad8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bad93  cmp     [rsp+128h+var_DC], r12b
0x1801bad98  jz      loc_1801BAEB9
0x1801bad9e  lea     rcx, [rsp+128h+var_E0]
0x1801bada3  call    ?value@?$optional@I@std@@QEGBAAEBIXZ; std::optional<uint>::value(void)
0x1801bada8  mov     edx, [rax]
0x1801badaa  lea     rdi, qword_18022AC20
0x1801badb1  lea     rcx, off_18022ACC0; "MaxInstallOrder"
0x1801badb8  cmp     rdi, rcx
0x1801badbb  jz      loc_1801BAE84
0x1801badc1  movzx   eax, word ptr [rdi+0Ch]
0x1801badc5  cmp     eax, edx
0x1801badc7  jz      short loc_1801BADCF
0x1801badc9  add     rdi, 28h ; '('
0x1801badcd  jmp     short loc_1801BADB8
0x1801badcf  mov     rcx, [rsp+128h]; this
0x1801badd7  movsxd  rax, dword ptr [rdi+18h]
0x1801baddb  cmp     [rax+rbx+40h], r12b
0x1801bade0  jnz     short loc_1801BAE0E
0x1801bade2  mov     dword ptr [rsp+128h+var_100], 8000FFFFh; char *
0x1801badea  lea     rax, aHasinprocserve; "!HasInprocServerDllForArchitecture(arch"...
0x1801badf1  mov     [rsp+128h+var_108], rax; char *
0x1801badf6  lea     r9, aOsintegrationD_343; "OSIntegration::DEH::Internal::ComClassR"...
0x1801badfd  lea     r8, aOnecoreAdminAp_96; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1801bae04  mov     edx, 63Dh; void *
0x1801bae09  call    ?_Throw_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Throw_Hr(void *,uint,char const *,char const *,char const *,long)
0x1801bae0e  mov     r8, rdi
0x1801bae11  lea     rdx, [rsp+128h+string]
0x1801bae16  mov     rcx, rbx
0x1801bae19  call    ?GetInprocServerDllForArchitecture@ComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@AEBA?AVOpaqueString@@AEBUPerArchitectureInformation@234@@Z; OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::GetInprocServerDllForArchitecture(OSIntegration::DEH::Internal::PerArchitectureInformation const &)
0x1801bae1e  mov     rdx, rax
0x1801bae21  lea     rcx, [rsp+128h+var_F8]
0x1801bae26  call    ??0?$Optional@VOpaqueString@@@@QEAA@AEBVOpaqueString@@@Z; Optional<OpaqueString>::Optional<OpaqueString>(OpaqueString const &)
0x1801bae2b  mov     al, byte ptr [rsp+128h+var_F8]
0x1801bae2f  mov     [rbx+130h], al
0x1801bae35  mov     rcx, [rbx+138h]; string
0x1801bae3c  call    cs:__imp_WindowsDeleteString
0x1801bae42  mov     rax, [rsp+128h+var_F0]
0x1801bae47  mov     [rbx+138h], rax
0x1801bae4e  mov     [rsp+128h+var_F0], r12
0x1801bae53  xor     ecx, ecx; string
0x1801bae55  call    cs:__imp_WindowsDeleteString
0x1801bae5b  mov     [rsp+128h+var_F0], r12
0x1801bae60  mov     rcx, [rsp+128h+string]; string
0x1801bae65  call    cs:__imp_WindowsDeleteString
0x1801bae6b  lea     rcx, [rsp+128h+var_E0]
0x1801bae70  call    ?value@?$optional@I@std@@QEGBAAEBIXZ; std::optional<uint>::value(void)
0x1801bae75  mov     eax, [rax]
0x1801bae77  mov     [rbx+2F8h], eax
0x1801bae7d  xor     eax, eax
0x1801bae7f  jmp     loc_1801BB24F
0x1801bae84  mov     rcx, [rsp+128h]; this
0x1801bae8c  mov     dword ptr [rsp+128h+var_100], 490h; char *
0x1801bae94  lea     rax, aErrorNotFound; "ERROR_NOT_FOUND"
0x1801bae9b  mov     [rsp+128h+var_108], rax; char *
0x1801baea0  lea     r9, aOsintegrationD_318; "OSIntegration::DEH::Internal::GetArchit"...
0x1801baea7  lea     r8, aOnecoreAdminAp_96; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1801baeae  mov     edx, 14Bh; void *
0x1801baeb3  call    ?_Throw_Win32@in1diag5@details@wil@@YAXPEAXIPEBD11K@Z; wil::details::in1diag5::_Throw_Win32(void *,uint,char const *,char const *,char const *,ulong)
0x1801baeb9  mov     rax, [rdi]
0x1801baebc  mov     rcx, rdi
0x1801baebf  mov     rax, [rax+60h]
0x1801baec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801baec8  test    eax, eax
0x1801baeca  jz      short loc_1801BAEFB
0x1801baecc  sub     eax, 5
0x1801baecf  jz      loc_1801BB09E
0x1801baed5  sub     eax, 4
0x1801baed8  jz      loc_1801BB07D
0x1801baede  sub     eax, 2
0x1801baee1  jz      loc_1801BB07D
0x1801baee7  sub     eax, 1
0x1801baeea  jz      loc_1801BB066
0x1801baef0  cmp     eax, 2
0x1801baef3  jz      short loc_1801BAEFB
0x1801baef5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1801baefa  nop
0x1801baefb  lea     rdi, qword_18022AC20
0x1801baf02  lea     rsi, dword_18022AC2C
0x1801baf09  mov     r8, rdi
0x1801baf0c  lea     rax, qword_18022AC38
0x1801baf13  movsxd  rax, dword ptr [rax]
0x1801baf16  cmp     [rax+rbx+40h], r12b
0x1801baf1b  jz      short loc_1801BAF87
0x1801baf1d  lea     rdx, [rsp+128h+string]
0x1801baf22  mov     rcx, rbx
0x1801baf25  call    ?GetInprocServerDllForArchitecture@ComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@AEBA?AVOpaqueString@@AEBUPerArchitectureInformation@234@@Z; OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::GetInprocServerDllForArchitecture(OSIntegration::DEH::Internal::PerArchitectureInformation const &)
0x1801baf2a  mov     rdx, rax
0x1801baf2d  lea     rcx, [rsp+128h+var_F8]
0x1801baf32  call    ??0?$Optional@VOpaqueString@@@@QEAA@AEBVOpaqueString@@@Z; Optional<OpaqueString>::Optional<OpaqueString>(OpaqueString const &)
0x1801baf37  mov     al, byte ptr [rsp+128h+var_F8]
0x1801baf3b  mov     [rbx+130h], al
0x1801baf41  mov     rcx, [rbx+138h]; string
0x1801baf48  call    cs:__imp_WindowsDeleteString
0x1801baf4e  mov     rax, [rsp+128h+var_F0]
0x1801baf53  mov     [rbx+138h], rax
0x1801baf5a  mov     [rsp+128h+var_F0], r12
0x1801baf5f  xor     ecx, ecx; string
0x1801baf61  call    cs:__imp_WindowsDeleteString
0x1801baf67  mov     [rsp+128h+var_F0], r12
0x1801baf6c  mov     rcx, [rsp+128h+string]; string
0x1801baf71  call    cs:__imp_WindowsDeleteString
0x1801baf77  movzx   eax, word ptr [rsi]
0x1801baf7a  mov     [rbx+2F8h], eax
0x1801baf80  xor     eax, eax
0x1801baf82  jmp     loc_1801BB24F
0x1801baf87  cmp     [rbx+160h], r12b
0x1801baf8e  jz      short loc_1801BB002
0x1801baf90  lea     r8, qword_18022AC48
0x1801baf97  lea     rdx, [rsp+128h+string]
0x1801baf9c  mov     rcx, rbx
0x1801baf9f  call    ?GetInprocServerDllForArchitecture@ComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@AEBA?AVOpaqueString@@AEBUPerArchitectureInformation@234@@Z; OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::GetInprocServerDllForArchitecture(OSIntegration::DEH::Internal::PerArchitectureInformation const &)
0x1801bafa4  mov     rdx, rax
0x1801bafa7  lea     rcx, [rsp+128h+var_F8]
0x1801bafac  call    ??0?$Optional@VOpaqueString@@@@QEAA@AEBVOpaqueString@@@Z; Optional<OpaqueString>::Optional<OpaqueString>(OpaqueString const &)
0x1801bafb1  mov     al, byte ptr [rsp+128h+var_F8]
0x1801bafb5  mov     [rbx+130h], al
0x1801bafbb  mov     rcx, [rbx+138h]; string
0x1801bafc2  call    cs:__imp_WindowsDeleteString
0x1801bafc8  mov     rax, [rsp+128h+var_F0]
0x1801bafcd  mov     [rbx+138h], rax
0x1801bafd4  mov     [rsp+128h+var_F0], r12
0x1801bafd9  xor     ecx, ecx; string
0x1801bafdb  call    cs:__imp_WindowsDeleteString
0x1801bafe1  mov     [rsp+128h+var_F0], r12
0x1801bafe6  mov     rcx, [rsp+128h+string]; string
0x1801bafeb  call    cs:__imp_WindowsDeleteString
0x1801baff1  mov     dword ptr [rbx+2F8h], 8664h
0x1801baffb  xor     eax, eax
0x1801baffd  jmp     loc_1801BB24F
0x1801bb002  xor     edx, edx; Val
0x1801bb004  mov     r8d, 0A0h; Size
0x1801bb00a  lea     rcx, [rsp+128h+var_D8]; void *
0x1801bb00f  call    memset_0
0x1801bb014  mov     r14, r12
0x1801bb017  mov     rsi, r12
0x1801bb01a  cmp     rsi, 4
0x1801bb01e  jnb     loc_1801BB0B5
0x1801bb024  lea     rax, [rsi+rsi*4]
0x1801bb028  lea     r15, [rdi+rax*8]
0x1801bb02c  mov     rcx, r15; this
0x1801bb02f  call    ?IsSupportedWowArchitecture@PerArchitectureInformation@Internal@DEH@OSIntegration@@QEBA_NXZ; OSIntegration::DEH::Internal::PerArchitectureInformation::IsSupportedWowArchitecture(void)
0x1801bb034  test    al, al
0x1801bb036  jz      short loc_1801BB061
0x1801bb038  mov     rax, r14
0x1801bb03b  inc     r14
0x1801bb03e  lea     rcx, [rax+rax*4]
0x1801bb042  movups  xmm0, xmmword ptr [r15]
0x1801bb046  movups  [rsp+rcx*8+128h+var_D8], xmm0
0x1801bb04b  movups  xmm1, xmmword ptr [r15+10h]
0x1801bb050  movups  [rsp+rcx*8+128h+var_C8], xmm1
0x1801bb055  movsd   xmm0, qword ptr [r15+20h]
0x1801bb05b  movsd   [rsp+rcx*8+128h+var_B8], xmm0
0x1801bb061  inc     rsi
0x1801bb064  jmp     short loc_1801BB01A
0x1801bb066  lea     rax, qword_18022ACB0
0x1801bb06d  lea     r8, qword_18022AC98
0x1801bb074  lea     rsi, dword_18022ACA4
0x1801bb07b  jmp     short loc_1801BB092
0x1801bb07d  lea     rax, qword_18022AC60
0x1801bb084  lea     r8, qword_18022AC48
0x1801bb08b  lea     rsi, dword_18022AC54
0x1801bb092  lea     rdi, qword_18022AC20
0x1801bb099  jmp     loc_1801BAF13
0x1801bb09e  lea     rax, qword_18022AC88
0x1801bb0a5  lea     r8, qword_18022AC70
0x1801bb0ac  lea     rsi, dword_18022AC7C
0x1801bb0b3  jmp     short loc_1801BB092
0x1801bb0b5  lea     rax, [r14+r14*4]
0x1801bb0b9  shl     rax, 3
0x1801bb0bd  mov     r9b, r12b
0x1801bb0c0  mov     r8, rax
0x1801bb0c3  sar     r8, 3
0x1801bb0c7  mov     rcx, 0CCCCCCCCCCCCCCCDh
0x1801bb0d1  imul    r8, rcx
0x1801bb0d5  lea     rdx, [rsp+128h+var_D8]
0x1801bb0da  add     rdx, rax
0x1801bb0dd  lea     rcx, [rsp+128h+var_D8]
0x1801bb0e2  call    ??$_Sort_unchecked@PEAUPerArchitectureInformation@Internal@DEH@OSIntegration@@U?$less@X@std@@@std@@YAXPEAUPerArchitectureInformation@Internal@DEH@OSIntegration@@0_JU?$less@X@0@@Z; std::_Sort_unchecked<OSIntegration::DEH::Internal::PerArchitectureInformation *,std::less<void>>(OSIntegration::DEH::Internal::PerArchitectureInformation *,OSIntegration::DEH::Internal::PerArchitectureInformation *,__int64,std::less<void>)
0x1801bb0e7  mov     rcx, r12
0x1801bb0ea  cmp     rcx, r14
0x1801bb0ed  jnb     loc_1801BB180
0x1801bb0f3  lea     rsi, [rcx+rcx*4]
0x1801bb0f7  movsxd  rax, dword ptr [rsp+rsi*8+128h+var_C8+8]
0x1801bb0fc  cmp     [rax+rbx+40h], r12b
0x1801bb101  jz      short loc_1801BB178
0x1801bb103  lea     r8, [rsp+128h+var_D8]
0x1801bb108  lea     r8, [r8+rsi*8]
0x1801bb10c  lea     rdx, [rsp+128h+string]
0x1801bb111  mov     rcx, rbx
0x1801bb114  call    ?GetInprocServerDllForArchitecture@ComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@AEBA?AVOpaqueString@@AEBUPerArchitectureInformation@234@@Z; OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::GetInprocServerDllForArchitecture(OSIntegration::DEH::Internal::PerArchitectureInformation const &)
0x1801bb119  mov     rdx, rax
0x1801bb11c  lea     rcx, [rsp+128h+var_F8]
0x1801bb121  call    ??0?$Optional@VOpaqueString@@@@QEAA@AEBVOpaqueString@@@Z; Optional<OpaqueString>::Optional<OpaqueString>(OpaqueString const &)
0x1801bb126  mov     al, byte ptr [rsp+128h+var_F8]
0x1801bb12a  mov     [rbx+130h], al
0x1801bb130  mov     rcx, [rbx+138h]; string
0x1801bb137  call    cs:__imp_WindowsDeleteString
0x1801bb13d  mov     rax, [rsp+128h+var_F0]
0x1801bb142  mov     [rbx+138h], rax
0x1801bb149  mov     [rsp+128h+var_F0], r12
0x1801bb14e  xor     ecx, ecx; string
0x1801bb150  call    cs:__imp_WindowsDeleteString
0x1801bb156  mov     [rsp+128h+var_F0], r12
0x1801bb15b  mov     rcx, [rsp+128h+string]; string
0x1801bb160  call    cs:__imp_WindowsDeleteString
0x1801bb166  movzx   eax, word ptr [rsp+rsi*8+128h+var_D8+0Ch]
0x1801bb16b  mov     [rbx+2F8h], eax
0x1801bb171  xor     eax, eax
0x1801bb173  jmp     loc_1801BB24F
0x1801bb178  inc     rcx
0x1801bb17b  jmp     loc_1801BB0EA
0x1801bb180  lea     rcx, off_18022ACC0; "MaxInstallOrder"
0x1801bb187  cmp     rdi, rcx
0x1801bb18a  jz      short loc_1801BB20B
0x1801bb18c  movsxd  rax, dword ptr [rdi+18h]
0x1801bb190  cmp     [rax+rbx+40h], r12b
0x1801bb195  jz      short loc_1801BB202
0x1801bb197  mov     r8, rdi
0x1801bb19a  lea     rdx, [rsp+128h+string]
0x1801bb19f  mov     rcx, rbx
0x1801bb1a2  call    ?GetInprocServerDllForArchitecture@ComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@AEBA?AVOpaqueString@@AEBUPerArchitectureInformation@234@@Z; OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::GetInprocServerDllForArchitecture(OSIntegration::DEH::Internal::PerArchitectureInformation const &)
0x1801bb1a7  mov     rdx, rax
0x1801bb1aa  lea     rcx, [rsp+128h+var_F8]
0x1801bb1af  call    ??0?$Optional@VOpaqueString@@@@QEAA@AEBVOpaqueString@@@Z; Optional<OpaqueString>::Optional<OpaqueString>(OpaqueString const &)
0x1801bb1b4  mov     al, byte ptr [rsp+128h+var_F8]
0x1801bb1b8  mov     [rbx+130h], al
0x1801bb1be  mov     rcx, [rbx+138h]; string
0x1801bb1c5  call    cs:__imp_WindowsDeleteString
0x1801bb1cb  mov     rax, [rsp+128h+var_F0]
0x1801bb1d0  mov     [rbx+138h], rax
0x1801bb1d7  mov     [rsp+128h+var_F0], r12
0x1801bb1dc  xor     ecx, ecx; string
0x1801bb1de  call    cs:__imp_WindowsDeleteString
0x1801bb1e4  mov     [rsp+128h+var_F0], r12
0x1801bb1e9  mov     rcx, [rsp+128h+string]; string
0x1801bb1ee  call    cs:__imp_WindowsDeleteString
0x1801bb1f4  movzx   eax, word ptr [rdi+0Ch]
0x1801bb1f8  mov     [rbx+2F8h], eax
0x1801bb1fe  xor     eax, eax
0x1801bb200  jmp     short loc_1801BB24F
0x1801bb202  add     rdi, 28h ; '('
0x1801bb206  jmp     loc_1801BB187
0x1801bb20b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1801bb210  mov     rcx, [rsp+128h]; this
0x1801bb218  mov     dword ptr [rsp+128h+var_100], 8000FFFFh; char *
0x1801bb220  lea     rax, aEUnexpected; "E_UNEXPECTED"
0x1801bb227  mov     [rsp+128h+var_108], rax; char *
0x1801bb22c  lea     r9, aOsintegrationD_343; "OSIntegration::DEH::Internal::ComClassR"...
0x1801bb233  lea     r8, aOnecoreAdminAp_96; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1801bb23a  mov     edx, 689h; void *
0x1801bb23f  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1801bb244  mov     eax, 8000FFFFh
0x1801bb249  jmp     short loc_1801BB24F
0x1801bb24b  mov     eax, [rsp+128h+var_E0]
0x1801bb24f  mov     rcx, [rsp+128h+var_38]
0x1801bb257  xor     rcx, rsp; StackCookie
0x1801bb25a  call    __security_check_cookie
0x1801bb25f  mov     rbx, [rsp+128h+arg_10]
0x1801bb267  add     rsp, 100h
0x1801bb26e  pop     r15
0x1801bb270  pop     r14
0x1801bb272  pop     r12
0x1801bb274  pop     rdi
0x1801bb275  pop     rsi
0x1801bb276  retn
```
