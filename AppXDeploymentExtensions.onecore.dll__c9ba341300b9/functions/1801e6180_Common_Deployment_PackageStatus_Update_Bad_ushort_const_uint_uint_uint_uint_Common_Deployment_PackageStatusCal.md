# Common::Deployment::PackageStatus::Update_Bad(ushort const *,uint,uint,uint,uint,Common::Deployment::PackageStatusCallOrigin,PackageRepository::IRepositorySession *,bool &)

- ea: `0x1801e6180`
- end: `0x1801e678e`
- name: `?Update_Bad@PackageStatus@Deployment@Common@@CAJPEBGIIIIW4PackageStatusCallOrigin@23@PEAVIRepositorySession@PackageRepository@@AEA_N@Z`
- size: `1550`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1801e5dd8`

## callees

- `0x1800043e8`
- `0x180056994`
- `0x180057010`
- `0x180095fdc`
- `0x180098bf4`
- `0x1800a219c`
- `0x1800a2854`
- `0x1800bacb0`
- `0x1800d3a70`
- `0x1800d3de8`
- `0x1800d40a0`
- `0x1800d4640`
- `0x1800d4694`
- `0x1800d7c7c`
- `0x1801e57ec`
- `0x1801e6180`
- `0x180211010`

## import_xrefs

- `api-ms-win-appmodel-runtime-internal-l1-1-1!UpdatePackageStatus` at `0x1801e62fb`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!UpdatePackageStatus` at `0x1801e63af`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!UpdatePackageStatus` at `0x1801e64c7`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!UpdatePackageStatus` at `0x1801e65e9`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!UpdatePackageStatus` at `0x1801e664b`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!UpdatePackageStatus` at `0x1801e66a4`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!UpdatePackageStatus` at `0x1801e62fb`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!UpdatePackageStatus` at `0x1801e63af`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!UpdatePackageStatus` at `0x1801e64c7`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!UpdatePackageStatus` at `0x1801e65e9`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!UpdatePackageStatus` at `0x1801e664b`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!UpdatePackageStatus` at `0x1801e66a4`

## string_xrefs

- `0x1801e628e`: `onecore\admin\appmodel\common\packagestatus.cpp`
- `0x1801e62c0`: `onecore\admin\appmodel\common\packagestatus.cpp`
- `0x1801e630c`: `onecore\admin\appmodel\common\packagestatus.cpp`
- `0x1801e634a`: `onecore\admin\appmodel\common\packagestatus.cpp`
- `0x1801e63c0`: `onecore\admin\appmodel\common\packagestatus.cpp`
- `0x1801e640f`: `onecore\admin\appmodel\common\packagestatus.cpp`
- `0x1801e6478`: `onecore\admin\appmodel\common\packagestatus.cpp`
- `0x1801e64d8`: `onecore\admin\appmodel\common\packagestatus.cpp`
- `0x1801e6544`: `onecore\admin\appmodel\common\packagestatus.cpp`
- `0x1801e65a5`: `onecore\admin\appmodel\common\packagestatus.cpp`
- `0x1801e65fa`: `onecore\admin\appmodel\common\packagestatus.cpp`
- `0x1801e665c`: `onecore\admin\appmodel\common\packagestatus.cpp`
- `0x1801e66b5`: `onecore\admin\appmodel\common\packagestatus.cpp`
- `0x1801e670e`: `onecore\admin\appmodel\common\packagestatus.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Common::Deployment::PackageStatus::Update_Bad(
        const unsigned __int16 *a1,
        int a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        struct PackageRepository::IRepositorySession *a7,
        _BYTE *a8)
{
  unsigned int v12; // edi
  const struct _tlgProvider_t *v13; // rax
  int v14; // r8d
  int v15; // r9d
  int v16; // r10d
  struct PackageRepository::IRepositorySession *v17; // r12
  int PackageType; // eax
  unsigned int v19; // ebx
  int v20; // eax
  bool v21; // r9
  unsigned int v22; // r15d
  unsigned int updated; // eax
  bool v25; // zf
  __int64 v26; // r13
  bool v27; // bl
  bool v28; // r13
  _BYTE *v29; // r15
  unsigned int v30; // eax
  int v31; // eax
  unsigned int v32; // edi
  struct StateRepository::Database *v33; // rax
  int InstalledRelatedSetForPackageIfAny; // eax
  bool *v35; // r9
  int v36; // r15d
  unsigned int v37; // ecx
  _BYTE *v38; // r15
  unsigned int v39; // eax
  int v40; // eax
  int v41; // eax
  unsigned int v42; // eax
  unsigned int v43; // eax
  _BYTE *v44; // r15
  unsigned int v45; // eax
  int v46; // eax
  unsigned int v47; // [rsp+20h] [rbp-89h]
  int v48; // [rsp+20h] [rbp-89h]
  int v49; // [rsp+20h] [rbp-89h]
  unsigned int v50; // [rsp+20h] [rbp-89h]
  unsigned int v51; // [rsp+60h] [rbp-49h] BYREF
  __int64 v52; // [rsp+68h] [rbp-41h] BYREF
  __int64 v53; // [rsp+70h] [rbp-39h] BYREF
  unsigned int v54[2]; // [rsp+78h] [rbp-31h] BYREF
  _QWORD v55[2]; // [rsp+80h] [rbp-29h] BYREF
  _QWORD v56[2]; // [rsp+90h] [rbp-19h] BYREF
  __int64 v57; // [rsp+A0h] [rbp-9h]
  char v58; // [rsp+A8h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+3Fh]
  unsigned int v60; // [rsp+F8h] [rbp+4Fh] BYREF
  unsigned int v61; // [rsp+100h] [rbp+57h]

  v61 = a3;
  v12 = a5;
  if ( (a5 & 6) != 0 )
  {
    v13 = AppXDeploymentServerTelemetry::Provider();
    if ( *(_DWORD *)v13 > 4u )
    {
      if ( (unsigned __int8)tlgKeywordOn(v13, 0x200000000000LL) )
      {
        v53 = 0x2000000;
        a5 = 0;
        v60 = v12;
        a6 = a4;
        v51 = a3;
        LODWORD(v52) = a2;
        *(_QWORD *)v54 = a1;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v16,
          (unsigned int)&word_1802B65C6,
          v14,
          v15,
          (__int64)v54,
          (__int64)&v52,
          (__int64)&v51,
          (__int64)&a6,
          (__int64)&v60,
          (__int64)&a5,
          (__int64)&v53);
      }
    }
  }
  if ( (a2 & 4) != 0 && (v12 & 4) != 0 )
    return 0;
  v52 = 0;
  a5 = 0;
  v17 = a7;
  PackageType = Common::Deployment::PackageStatus::GetPackageType(
                  a1,
                  a7,
                  (enum StateRepository::PackageType *)&a5,
                  &v52);
  v19 = PackageType;
  if ( PackageType < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x3AA,
      (unsigned int)"onecore\\admin\\appmodel\\common\\packagestatus.cpp",
      (const char *)(unsigned int)PackageType,
      v47);
  v55[0] = 0;
  v55[1] = 0;
  v20 = Common::ImpersonationContext::Impersonate((Common::ImpersonationContext *)v55, 0);
  v22 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3AD,
      (unsigned int)"onecore\\admin\\appmodel\\common\\packagestatus.cpp",
      (const char *)(unsigned int)v20,
      v47);
    if ( LODWORD(v55[0]) )
      Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v55);
    return v22;
  }
  if ( v19 == -2147009295 )
  {
    updated = UpdatePackageStatus(a1, a4, v12);
    if ( updated )
    {
      v19 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x3B2,
              (unsigned int)"onecore\\admin\\appmodel\\common\\packagestatus.cpp",
              (const char *)updated,
              v47);
      if ( LODWORD(v55[0]) )
        Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v55);
      return v19;
    }
    v25 = LODWORD(v55[0]) == 0;
    goto LABEL_82;
  }
  if ( (v19 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B7,
      (unsigned int)"onecore\\admin\\appmodel\\common\\packagestatus.cpp",
      (const char *)v19,
      v47);
    if ( LODWORD(v55[0]) )
      Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v55);
    return v19;
  }
  v26 = v52;
  v27 = 1;
  if ( ((a5 - 2) & 0xFFFFFFFD) != 0 )
  {
    v56[0] = 0;
    v56[1] = 0;
    v57 = 0;
    v58 = 1;
    v33 = (struct StateRepository::Database *)(*(__int64 (__fastcall **)(struct PackageRepository::IRepositorySession *))(*(_QWORD *)v17 + 8LL))(v17);
    InstalledRelatedSetForPackageIfAny = Common::Deployment::OptionalPackageHelper::GetInstalledRelatedSetForPackageIfAny(
                                           v33,
                                           v26);
    v36 = InstalledRelatedSetForPackageIfAny;
    if ( InstalledRelatedSetForPackageIfAny < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x3D3,
        (unsigned int)"onecore\\admin\\appmodel\\common\\packagestatus.cpp",
        (const char *)(unsigned int)InstalledRelatedSetForPackageIfAny,
        v47);
    v37 = v61 & 0x4000307;
    LOBYTE(a5) = (v61 & 0x4000307) != 0;
    if ( v36 >= 0 && v57 )
    {
      if ( v37 )
      {
        v38 = a8;
        if ( !*a8 )
        {
          v39 = UpdatePackageStatus(a1, a4, v12);
          if ( v39 )
          {
            v19 = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x3ED,
                    (unsigned int)"onecore\\admin\\appmodel\\common\\packagestatus.cpp",
                    (const char *)v39,
                    v47);
            Common::Array<StateRepository::Entity::Package,Common::ContainerOperations<StateRepository::Entity::Package,StateRepository::Entity::Package>,Common::NoKey,Common::ContainerOperations<Common::NoKey,StateRepository::Entity::Package>,Common::ArrayOperations<StateRepository::Entity::Package,Common::NoKey>>::~Array<StateRepository::Entity::Package,Common::ContainerOperations<StateRepository::Entity::Package,StateRepository::Entity::Package>,Common::NoKey,Common::ContainerOperations<Common::NoKey,StateRepository::Entity::Package>,Common::ArrayOperations<StateRepository::Entity::Package,Common::NoKey>>(v56);
            if ( LODWORD(v55[0]) )
              Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v55);
            return v19;
          }
          *v38 = 1;
        }
        v40 = Common::Deployment::PackageStatus::SetRelatedPackages(v17, 0, 0);
        v19 = v40;
        if ( v40 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3F0,
            (unsigned int)"onecore\\admin\\appmodel\\common\\packagestatus.cpp",
            (const char *)(unsigned int)v40,
            v49);
          Common::Array<StateRepository::Entity::Package,Common::ContainerOperations<StateRepository::Entity::Package,StateRepository::Entity::Package>,Common::NoKey,Common::ContainerOperations<Common::NoKey,StateRepository::Entity::Package>,Common::ArrayOperations<StateRepository::Entity::Package,Common::NoKey>>::~Array<StateRepository::Entity::Package,Common::ContainerOperations<StateRepository::Entity::Package,StateRepository::Entity::Package>,Common::NoKey,Common::ContainerOperations<Common::NoKey,StateRepository::Entity::Package>,Common::ArrayOperations<StateRepository::Entity::Package,Common::NoKey>>(v56);
          if ( LODWORD(v55[0]) )
            Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v55);
          return v19;
        }
      }
      else
      {
        LOBYTE(a5) = 0;
        v41 = Common::Deployment::PackageStatus::SetRelatedPackages(v17, 0, (bool)&a5);
        v22 = v41;
        if ( v41 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3F8,
            (unsigned int)"onecore\\admin\\appmodel\\common\\packagestatus.cpp",
            (const char *)(unsigned int)v41,
            v50);
          Common::Array<StateRepository::Entity::Package,Common::ContainerOperations<StateRepository::Entity::Package,StateRepository::Entity::Package>,Common::NoKey,Common::ContainerOperations<Common::NoKey,StateRepository::Entity::Package>,Common::ArrayOperations<StateRepository::Entity::Package,Common::NoKey>>::~Array<StateRepository::Entity::Package,Common::ContainerOperations<StateRepository::Entity::Package,StateRepository::Entity::Package>,Common::NoKey,Common::ContainerOperations<Common::NoKey,StateRepository::Entity::Package>,Common::ArrayOperations<StateRepository::Entity::Package,Common::NoKey>>(v56);
          if ( LODWORD(v55[0]) )
            Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v55);
          return v22;
        }
        if ( (_BYTE)a5 )
        {
          v42 = UpdatePackageStatus(a1, a4 | 0x40, v12);
          if ( v42 )
          {
            v19 = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x3FC,
                    (unsigned int)"onecore\\admin\\appmodel\\common\\packagestatus.cpp",
                    (const char *)v42,
                    v50);
            Common::Array<StateRepository::Entity::Package,Common::ContainerOperations<StateRepository::Entity::Package,StateRepository::Entity::Package>,Common::NoKey,Common::ContainerOperations<Common::NoKey,StateRepository::Entity::Package>,Common::ArrayOperations<StateRepository::Entity::Package,Common::NoKey>>::~Array<StateRepository::Entity::Package,Common::ContainerOperations<StateRepository::Entity::Package,StateRepository::Entity::Package>,Common::NoKey,Common::ContainerOperations<Common::NoKey,StateRepository::Entity::Package>,Common::ArrayOperations<StateRepository::Entity::Package,Common::NoKey>>(v56);
            if ( LODWORD(v55[0]) )
              Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v55);
            return v19;
          }
          *a8 = 1;
        }
        else
        {
          v43 = UpdatePackageStatus(a1, a4, v12 | 0x40);
          if ( v43 )
          {
            v19 = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x402,
                    (unsigned int)"onecore\\admin\\appmodel\\common\\packagestatus.cpp",
                    (const char *)v43,
                    v50);
            Common::Array<StateRepository::Entity::Package,Common::ContainerOperations<StateRepository::Entity::Package,StateRepository::Entity::Package>,Common::NoKey,Common::ContainerOperations<Common::NoKey,StateRepository::Entity::Package>,Common::ArrayOperations<StateRepository::Entity::Package,Common::NoKey>>::~Array<StateRepository::Entity::Package,Common::ContainerOperations<StateRepository::Entity::Package,StateRepository::Entity::Package>,Common::NoKey,Common::ContainerOperations<Common::NoKey,StateRepository::Entity::Package>,Common::ArrayOperations<StateRepository::Entity::Package,Common::NoKey>>(v56);
            if ( LODWORD(v55[0]) )
              Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v55);
            return v19;
          }
        }
      }
    }
    else if ( v37 )
    {
      v44 = a8;
      if ( !*a8 )
      {
        v45 = UpdatePackageStatus(a1, a4, v12);
        if ( v45 )
        {
          v19 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x3DD,
                  (unsigned int)"onecore\\admin\\appmodel\\common\\packagestatus.cpp",
                  (const char *)v45,
                  v47);
          Common::Array<StateRepository::Entity::Package,Common::ContainerOperations<StateRepository::Entity::Package,StateRepository::Entity::Package>,Common::NoKey,Common::ContainerOperations<Common::NoKey,StateRepository::Entity::Package>,Common::ArrayOperations<StateRepository::Entity::Package,Common::NoKey>>::~Array<StateRepository::Entity::Package,Common::ContainerOperations<StateRepository::Entity::Package,StateRepository::Entity::Package>,Common::NoKey,Common::ContainerOperations<Common::NoKey,StateRepository::Entity::Package>,Common::ArrayOperations<StateRepository::Entity::Package,Common::NoKey>>(v56);
          if ( LODWORD(v55[0]) )
            Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v55);
          return v19;
        }
        *v44 = 1;
      }
    }
    else
    {
      v46 = Common::Deployment::PackageStatus::ResetBasedOnDependencies(v17, a1, v26, v35);
      v19 = v46;
      if ( v46 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3E3,
          (unsigned int)"onecore\\admin\\appmodel\\common\\packagestatus.cpp",
          (const char *)(unsigned int)v46,
          v47);
        Common::Array<StateRepository::Entity::Package,Common::ContainerOperations<StateRepository::Entity::Package,StateRepository::Entity::Package>,Common::NoKey,Common::ContainerOperations<Common::NoKey,StateRepository::Entity::Package>,Common::ArrayOperations<StateRepository::Entity::Package,Common::NoKey>>::~Array<StateRepository::Entity::Package,Common::ContainerOperations<StateRepository::Entity::Package,StateRepository::Entity::Package>,Common::NoKey,Common::ContainerOperations<Common::NoKey,StateRepository::Entity::Package>,Common::ArrayOperations<StateRepository::Entity::Package,Common::NoKey>>(v56);
        if ( LODWORD(v55[0]) )
          Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v55);
        return v19;
      }
    }
    v27 = 0;
    Common::Array<StateRepository::Entity::Package,Common::ContainerOperations<StateRepository::Entity::Package,StateRepository::Entity::Package>,Common::NoKey,Common::ContainerOperations<Common::NoKey,StateRepository::Entity::Package>,Common::ArrayOperations<StateRepository::Entity::Package,Common::NoKey>>::~Array<StateRepository::Entity::Package,Common::ContainerOperations<StateRepository::Entity::Package,StateRepository::Entity::Package>,Common::NoKey,Common::ContainerOperations<Common::NoKey,StateRepository::Entity::Package>,Common::ArrayOperations<StateRepository::Entity::Package,Common::NoKey>>(v56);
    goto LABEL_79;
  }
  if ( (v61 & 0x4000307) == 0 || (v28 = 1, (v61 & 0x4000307) == 1) )
    v28 = 0;
  v29 = a8;
  if ( !*a8 )
  {
    v30 = UpdatePackageStatus(a1, a4, v12);
    if ( v30 )
    {
      v19 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x3C9,
              (unsigned int)"onecore\\admin\\appmodel\\common\\packagestatus.cpp",
              (const char *)v30,
              v47);
      if ( LODWORD(v55[0]) )
        Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v55);
      return v19;
    }
    *v29 = 1;
  }
  v31 = Common::Deployment::PackageStatus::SetDependentPackages(v17, a1, v28, v21, 0);
  v32 = v31;
  if ( v31 >= 0 )
  {
    v26 = v52;
LABEL_79:
    if ( (v61 & 4) != 0 )
      PackageManagerInternal::PackageProcess::TryTerminateProcessesLoadingPackage(a1, v26, v27, v61, v17);
    v25 = LODWORD(v55[0]) == 0;
LABEL_82:
    if ( !v25 )
      Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v55);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3CD,
    (unsigned int)"onecore\\admin\\appmodel\\common\\packagestatus.cpp",
    (const char *)(unsigned int)v31,
    v48);
  if ( LODWORD(v55[0]) )
    Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v55);
  return v32;
}

```

## disassembly

```asm
0x1801e6180  mov     [rsp-8+arg_0], rbx
0x1801e6185  mov     [rsp-8+arg_10], r8d
0x1801e618a  push    rbp
0x1801e618b  push    rsi
0x1801e618c  push    rdi
0x1801e618d  push    r12
0x1801e618f  push    r13
0x1801e6191  push    r14
0x1801e6193  push    r15
0x1801e6195  lea     rbp, [rsp-7]
0x1801e619a  sub     rsp, 0B0h
0x1801e61a1  mov     r14d, r9d
0x1801e61a4  mov     r15d, r8d
0x1801e61a7  mov     ebx, edx
0x1801e61a9  mov     rsi, rcx
0x1801e61ac  mov     edi, [rbp+37h+arg_20]
0x1801e61af  xor     r13d, r13d
0x1801e61b2  test    dil, 6
0x1801e61b6  jz      loc_1801E6253
0x1801e61bc  call    ?Provider@AppXDeploymentServerTelemetry@@SAPEBU_tlgProvider_t@@XZ; AppXDeploymentServerTelemetry::Provider(void)
0x1801e61c1  mov     r10, rax
0x1801e61c4  mov     r9d, [rax]
0x1801e61c7  cmp     r9d, 4
0x1801e61cb  jbe     loc_1801E6253
0x1801e61d1  mov     rdx, 200000000000h
0x1801e61db  mov     rcx, rax
0x1801e61de  call    _tlgKeywordOn
0x1801e61e3  test    al, al
0x1801e61e5  jz      short loc_1801E6253
0x1801e61e7  mov     [rbp+37h+var_70], 2000000h
0x1801e61ef  mov     [rbp+37h+arg_20], r13d
0x1801e61f3  mov     [rbp+37h+arg_8], edi
0x1801e61f6  mov     [rbp+37h+arg_28], r14d
0x1801e61fa  mov     [rbp+37h+var_80], r15d
0x1801e61fe  mov     dword ptr [rbp+37h+var_78], ebx
0x1801e6201  mov     qword ptr [rbp+37h+var_68], rsi
0x1801e6205  lea     rax, [rbp+37h+var_70]
0x1801e6209  mov     [rsp+0E0h+var_90], rax
0x1801e620e  lea     rax, [rbp+37h+arg_20]
0x1801e6212  mov     [rsp+0E0h+var_98], rax
0x1801e6217  lea     rax, [rbp+37h+arg_8]
0x1801e621b  mov     [rsp+0E0h+var_A0], rax
0x1801e6220  lea     rax, [rbp+37h+arg_28]
0x1801e6224  mov     [rsp+0E0h+var_A8], rax
0x1801e6229  lea     rax, [rbp+37h+var_80]
0x1801e622d  mov     [rsp+0E0h+var_B0], rax
0x1801e6232  lea     rax, [rbp+37h+var_78]
0x1801e6236  mov     qword ptr [rsp+0E0h+var_B8], rax
0x1801e623b  lea     rax, [rbp+37h+var_68]
0x1801e623f  mov     [rsp+0E0h+var_C0], rax; int
0x1801e6244  lea     rdx, word_1802B65C6
0x1801e624b  mov     rcx, r10
0x1801e624e  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@4444AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1801e6253  test    bl, 4
0x1801e6256  jz      short loc_1801E6262
0x1801e6258  test    dil, 4
0x1801e625c  jnz     loc_1801E6771
0x1801e6262  mov     [rbp+37h+var_78], r13
0x1801e6266  mov     [rbp+37h+arg_20], r13d
0x1801e626a  lea     r9, [rbp+37h+var_78]; __int64 *
0x1801e626e  lea     r8, [rbp+37h+arg_20]; enum StateRepository::PackageType *
0x1801e6272  mov     r12, [rbp+37h+arg_30]
0x1801e6276  mov     rdx, r12; struct PackageRepository::IRepositorySession *
0x1801e6279  mov     rcx, rsi; unsigned __int16 *
0x1801e627c  call    ?GetPackageType@PackageStatus@Deployment@Common@@CAJPEBGPEAVIRepositorySession@PackageRepository@@PEAW4PackageType@StateRepository@@PEA_J@Z; Common::Deployment::PackageStatus::GetPackageType(ushort const *,PackageRepository::IRepositorySession *,StateRepository::PackageType *,__int64 *)
0x1801e6281  mov     ebx, eax
0x1801e6283  mov     rcx, [rbp+3Fh]; this
0x1801e6287  test    eax, eax
0x1801e6289  jns     short loc_1801E629F
0x1801e628b  mov     r9d, eax; char *
0x1801e628e  lea     r8, aOnecoreAdminAp_151; "onecore\\admin\\appmodel\\common\\packa"...
0x1801e6295  mov     edx, 3AAh; void *
0x1801e629a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801e629f  mov     [rbp+37h+var_60], r13
0x1801e62a3  mov     [rbp+37h+var_58], r13
0x1801e62a7  xor     edx, edx; void *
0x1801e62a9  lea     rcx, [rbp+37h+var_60]; this
0x1801e62ad  call    ?Impersonate@ImpersonationContext@Common@@QEAAJPEAX@Z; Common::ImpersonationContext::Impersonate(void *)
0x1801e62b2  mov     r15d, eax
0x1801e62b5  test    eax, eax
0x1801e62b7  jns     short loc_1801E62EA
0x1801e62b9  mov     rcx, [rbp+3Fh]; this
0x1801e62bd  mov     r9d, eax; char *
0x1801e62c0  lea     r8, aOnecoreAdminAp_151; "onecore\\admin\\appmodel\\common\\packa"...
0x1801e62c7  mov     edx, 3ADh; void *
0x1801e62cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e62d1  nop
0x1801e62d2  cmp     dword ptr [rbp+37h+var_60], r13d
0x1801e62d6  jz      short loc_1801E62E2
0x1801e62d8  lea     rcx, [rbp+37h+var_60]; this
0x1801e62dc  call    ?Revert@ImpersonationContext@Common@@QEAAXXZ; Common::ImpersonationContext::Revert(void)
0x1801e62e1  nop
0x1801e62e2  mov     eax, r15d
0x1801e62e5  jmp     loc_1801E6773
0x1801e62ea  cmp     ebx, 80073CF1h
0x1801e62f0  jnz     short loc_1801E633F
0x1801e62f2  mov     r8d, edi
0x1801e62f5  mov     edx, r14d
0x1801e62f8  mov     rcx, rsi
0x1801e62fb  call    cs:__imp_UpdatePackageStatus
0x1801e6301  test    eax, eax
0x1801e6303  jz      short loc_1801E6336
0x1801e6305  mov     rcx, [rbp+3Fh]; this
0x1801e6309  mov     r9d, eax; char *
0x1801e630c  lea     r8, aOnecoreAdminAp_151; "onecore\\admin\\appmodel\\common\\packa"...
0x1801e6313  mov     edx, 3B2h; void *
0x1801e6318  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801e631d  mov     ebx, eax
0x1801e631f  cmp     dword ptr [rbp+37h+var_60], r13d
0x1801e6323  jz      short loc_1801E632F
0x1801e6325  lea     rcx, [rbp+37h+var_60]; this
0x1801e6329  call    ?Revert@ImpersonationContext@Common@@QEAAXXZ; Common::ImpersonationContext::Revert(void)
0x1801e632e  nop
0x1801e632f  mov     eax, ebx
0x1801e6331  jmp     loc_1801E6773
0x1801e6336  cmp     dword ptr [rbp+37h+var_60], r13d
0x1801e633a  jmp     loc_1801E6765
0x1801e633f  test    ebx, ebx
0x1801e6341  jns     short loc_1801E636E
0x1801e6343  mov     rcx, [rbp+3Fh]; this
0x1801e6347  mov     r9d, ebx; char *
0x1801e634a  lea     r8, aOnecoreAdminAp_151; "onecore\\admin\\appmodel\\common\\packa"...
0x1801e6351  mov     edx, 3B7h; void *
0x1801e6356  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e635b  nop
0x1801e635c  cmp     dword ptr [rbp+37h+var_60], r13d
0x1801e6360  jz      short loc_1801E636C
0x1801e6362  lea     rcx, [rbp+37h+var_60]; this
0x1801e6366  call    ?Revert@ImpersonationContext@Common@@QEAAXXZ; Common::ImpersonationContext::Revert(void)
0x1801e636b  nop
0x1801e636c  jmp     short loc_1801E632F
0x1801e636e  mov     eax, [rbp+37h+arg_20]
0x1801e6371  add     eax, 0FFFFFFFEh
0x1801e6374  mov     r13, [rbp+37h+var_78]
0x1801e6378  mov     ebx, 1
0x1801e637d  test    eax, 0FFFFFFFDh
0x1801e6382  jnz     loc_1801E6438
0x1801e6388  mov     eax, [rbp+37h+arg_10]
0x1801e638b  and     eax, 4000307h
0x1801e6390  jz      short loc_1801E6399
0x1801e6392  mov     r13b, bl
0x1801e6395  cmp     eax, ebx
0x1801e6397  jnz     short loc_1801E639C
0x1801e6399  xor     r13b, r13b
0x1801e639c  mov     r15, [rbp+37h+arg_38]
0x1801e63a0  cmp     byte ptr [r15], 0
0x1801e63a4  jnz     short loc_1801E63EB
0x1801e63a6  mov     r8d, edi
0x1801e63a9  mov     edx, r14d
0x1801e63ac  mov     rcx, rsi
0x1801e63af  call    cs:__imp_UpdatePackageStatus
0x1801e63b5  test    eax, eax
0x1801e63b7  jz      short loc_1801E63E8
0x1801e63b9  mov     rcx, [rbp+3Fh]; this
0x1801e63bd  mov     r9d, eax; char *
0x1801e63c0  lea     r8, aOnecoreAdminAp_151; "onecore\\admin\\appmodel\\common\\packa"...
0x1801e63c7  mov     edx, 3C9h; void *
0x1801e63cc  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801e63d1  mov     ebx, eax
0x1801e63d3  cmp     dword ptr [rbp+37h+var_60], 0
0x1801e63d7  jz      short loc_1801E63E3
0x1801e63d9  lea     rcx, [rbp+37h+var_60]; this
0x1801e63dd  call    ?Revert@ImpersonationContext@Common@@QEAAXXZ; Common::ImpersonationContext::Revert(void)
0x1801e63e2  nop
0x1801e63e3  jmp     loc_1801E632F
0x1801e63e8  mov     [r15], bl
0x1801e63eb  mov     byte ptr [rsp+0E0h+var_C0], 0; int
0x1801e63f0  mov     r8b, r13b; bool
0x1801e63f3  mov     rdx, rsi; unsigned __int16 *
0x1801e63f6  mov     rcx, r12; struct PackageRepository::IRepositorySession *
0x1801e63f9  call    ?SetDependentPackages@PackageStatus@Deployment@Common@@SAJPEAVIRepositorySession@PackageRepository@@PEBG_N22@Z; Common::Deployment::PackageStatus::SetDependentPackages(PackageRepository::IRepositorySession *,ushort const *,bool,bool,bool)
0x1801e63fe  mov     edi, eax
0x1801e6400  test    eax, eax
0x1801e6402  jns     loc_1801E673F
0x1801e6408  mov     rcx, [rbp+3Fh]; this
0x1801e640c  mov     r9d, eax; char *
0x1801e640f  lea     r8, aOnecoreAdminAp_151; "onecore\\admin\\appmodel\\common\\packa"...
0x1801e6416  mov     edx, 3CDh; void *
0x1801e641b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e6420  nop
0x1801e6421  cmp     dword ptr [rbp+37h+var_60], 0
0x1801e6425  jz      short loc_1801E6431
0x1801e6427  lea     rcx, [rbp+37h+var_60]; this
0x1801e642b  call    ?Revert@ImpersonationContext@Common@@QEAAXXZ; Common::ImpersonationContext::Revert(void)
0x1801e6430  nop
0x1801e6431  mov     eax, edi
0x1801e6433  jmp     loc_1801E6773
0x1801e6438  xor     eax, eax
0x1801e643a  mov     [rbp+37h+var_50], rax
0x1801e643e  mov     [rbp+37h+var_48], rax
0x1801e6442  mov     [rbp+37h+var_40], rax
0x1801e6446  mov     [rbp+37h+var_38], bl
0x1801e6449  mov     rax, [r12]
0x1801e644d  mov     rcx, r12
0x1801e6450  mov     rax, [rax+8]
0x1801e6454  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e6459  lea     r8, [rbp+37h+var_50]
0x1801e645d  mov     rdx, r13
0x1801e6460  mov     rcx, rax
0x1801e6463  call    ?GetInstalledRelatedSetForPackageIfAny@OptionalPackageHelper@Deployment@Common@@SAJAEAVDatabase@StateRepository@@_JAEAV?$Array@VPackage@Entity@StateRepository@@V?$ContainerOperations@VPackage@Entity@StateRepository@@V123@@Common@@VNoKey@5@V?$ContainerOperations@VNoKey@Common@@VPackage@Entity@StateRepository@@@5@V?$ArrayOperations@VPackage@Entity@StateRepository@@VNoKey@Common@@@5@@3@@Z; Common::Deployment::OptionalPackageHelper::GetInstalledRelatedSetForPackageIfAny(StateRepository::Database &,__int64,Common::Array<StateRepository::Entity::Package,Common::ContainerOperations<StateRepository::Entity::Package,StateRepository::Entity::Package>,Common::NoKey,Common::ContainerOperations<Common::NoKey,StateRepository::Entity::Package>,Common::ArrayOperations<StateRepository::Entity::Package,Common::NoKey>> &)
0x1801e6468  mov     r15d, eax
0x1801e646b  mov     rcx, [rbp+3Fh]; this
0x1801e646f  xor     edx, edx
0x1801e6471  test    eax, eax
0x1801e6473  jns     short loc_1801E648B
0x1801e6475  mov     r9d, eax; char *
0x1801e6478  lea     r8, aOnecoreAdminAp_151; "onecore\\admin\\appmodel\\common\\packa"...
0x1801e647f  mov     edx, 3D3h; void *
0x1801e6484  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801e6489  xor     edx, edx
0x1801e648b  mov     ecx, [rbp+37h+arg_10]
0x1801e648e  and     ecx, 4000307h
0x1801e6494  setnz   al
0x1801e6497  mov     byte ptr [rbp+37h+arg_20], al
0x1801e649a  test    r15d, r15d
0x1801e649d  js      loc_1801E668E
0x1801e64a3  cmp     [rbp+37h+var_40], rdx
0x1801e64a7  jz      loc_1801E668E
0x1801e64ad  test    ecx, ecx
0x1801e64af  jz      loc_1801E6575
0x1801e64b5  mov     r15, [rbp+37h+arg_38]
0x1801e64b9  cmp     [r15], dl
0x1801e64bc  jnz     short loc_1801E6510
0x1801e64be  mov     r8d, edi
0x1801e64c1  mov     edx, r14d
0x1801e64c4  mov     rcx, rsi
0x1801e64c7  call    cs:__imp_UpdatePackageStatus
0x1801e64cd  test    eax, eax
0x1801e64cf  jz      short loc_1801E650A
0x1801e64d1  mov     rcx, [rbp+3Fh]; this
0x1801e64d5  mov     r9d, eax; char *
0x1801e64d8  lea     r8, aOnecoreAdminAp_151; "onecore\\admin\\appmodel\\common\\packa"...
0x1801e64df  mov     edx, 3EDh; void *
0x1801e64e4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801e64e9  mov     ebx, eax
0x1801e64eb  lea     rcx, [rbp+37h+var_50]
0x1801e64ef  call    ??1?$Array@VPackage@Entity@StateRepository@@V?$ContainerOperations@VPackage@Entity@StateRepository@@V123@@Common@@VNoKey@5@V?$ContainerOperations@VNoKey@Common@@VPackage@Entity@StateRepository@@@5@V?$ArrayOperations@VPackage@Entity@StateRepository@@VNoKey@Common@@@5@@Common@@QEAA@XZ; Common::Array<StateRepository::Entity::Package,Common::ContainerOperations<StateRepository::Entity::Package,StateRepository::Entity::Package>,Common::NoKey,Common::ContainerOperations<Common::NoKey,StateRepository::Entity::Package>,Common::ArrayOperations<StateRepository::Entity::Package,Common::NoKey>>::~Array<StateRepository::Entity::Package,Common::ContainerOperations<StateRepository::Entity::Package,StateRepository::Entity::Package>,Common::NoKey,Common::ContainerOperations<Common::NoKey,StateRepository::Entity::Package>,Common::ArrayOperations<StateRepository::Entity::Package,Common::NoKey>>(void)
0x1801e64f4  nop
0x1801e64f5  cmp     dword ptr [rbp+37h+var_60], 0
0x1801e64f9  jz      short loc_1801E6505
0x1801e64fb  lea     rcx, [rbp+37h+var_60]; this
0x1801e64ff  call    ?Revert@ImpersonationContext@Common@@QEAAXXZ; Common::ImpersonationContext::Revert(void)
0x1801e6504  nop
0x1801e6505  jmp     loc_1801E632F
0x1801e650a  mov     [r15], bl
0x1801e650d  mov     al, byte ptr [rbp+37h+arg_20]
0x1801e6510  mov     qword ptr [rsp+0E0h+var_B8], 0; bool
0x1801e6519  mov     dword ptr [rsp+0E0h+var_C0], 0; int
0x1801e6521  mov     r9b, al
0x1801e6524  lea     r8, [rbp+37h+var_50]
0x1801e6528  mov     rdx, r13
0x1801e652b  mov     rcx, r12; struct PackageRepository::IRepositorySession *
0x1801e652e  call    ?SetRelatedPackages@PackageStatus@Deployment@Common@@CAJPEAVIRepositorySession@PackageRepository@@_JAEBV?$Array@VPackage@Entity@StateRepository@@V?$ContainerOperations@VPackage@Entity@StateRepository@@V123@@Common@@VNoKey@5@V?$ContainerOperations@VNoKey@Common@@VPackage@Entity@StateRepository@@@5@V?$ArrayOperations@VPackage@Entity@StateRepository@@VNoKey@Common@@@5@@3@_NW4PackageStatusCallOrigin@23@PEA_N@Z; Common::Deployment::PackageStatus::SetRelatedPackages(PackageRepository::IRepositorySession *,__int64,Common::Array<StateRepository::Entity::Package,Common::ContainerOperations<StateRepository::Entity::Package,StateRepository::Entity::Package>,Common::NoKey,Common::ContainerOperations<Common::NoKey,StateRepository::Entity::Package>,Common::ArrayOperations<StateRepository::Entity::Package,Common::NoKey>> const &,bool,Common::Deployment::PackageStatusCallOrigin,bool *)
0x1801e6533  mov     ebx, eax
0x1801e6535  test    eax, eax
0x1801e6537  jns     loc_1801E6632
0x1801e653d  mov     rcx, [rbp+3Fh]; this
0x1801e6541  mov     r9d, eax; char *
0x1801e6544  lea     r8, aOnecoreAdminAp_151; "onecore\\admin\\appmodel\\common\\packa"...
0x1801e654b  mov     edx, 3F0h; void *
0x1801e6550  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e6555  nop
0x1801e6556  lea     rcx, [rbp+37h+var_50]
0x1801e655a  call    ??1?$Array@VPackage@Entity@StateRepository@@V?$ContainerOperations@VPackage@Entity@StateRepository@@V123@@Common@@VNoKey@5@V?$ContainerOperations@VNoKey@Common@@VPackage@Entity@StateRepository@@@5@V?$ArrayOperations@VPackage@Entity@StateRepository@@VNoKey@Common@@@5@@Common@@QEAA@XZ; Common::Array<StateRepository::Entity::Package,Common::ContainerOperations<StateRepository::Entity::Package,StateRepository::Entity::Package>,Common::NoKey,Common::ContainerOperations<Common::NoKey,StateRepository::Entity::Package>,Common::ArrayOperations<StateRepository::Entity::Package,Common::NoKey>>::~Array<StateRepository::Entity::Package,Common::ContainerOperations<StateRepository::Entity::Package,StateRepository::Entity::Package>,Common::NoKey,Common::ContainerOperations<Common::NoKey,StateRepository::Entity::Package>,Common::ArrayOperations<StateRepository::Entity::Package,Common::NoKey>>(void)
0x1801e655f  nop
0x1801e6560  cmp     dword ptr [rbp+37h+var_60], 0
0x1801e6564  jz      short loc_1801E6570
0x1801e6566  lea     rcx, [rbp+37h+var_60]; this
0x1801e656a  call    ?Revert@ImpersonationContext@Common@@QEAAXXZ; Common::ImpersonationContext::Revert(void)
0x1801e656f  nop
0x1801e6570  jmp     loc_1801E632F
0x1801e6575  mov     byte ptr [rbp+37h+arg_20], dl
0x1801e6578  lea     rcx, [rbp+37h+arg_20]
0x1801e657c  mov     qword ptr [rsp+0E0h+var_B8], rcx; bool
0x1801e6581  mov     dword ptr [rsp+0E0h+var_C0], edx; unsigned int
0x1801e6585  mov     r9b, al
0x1801e6588  lea     r8, [rbp+37h+var_50]
0x1801e658c  mov     rdx, r13
0x1801e658f  mov     rcx, r12; struct PackageRepository::IRepositorySession *
0x1801e6592  call    ?SetRelatedPackages@PackageStatus@Deployment@Common@@CAJPEAVIRepositorySession@PackageRepository@@_JAEBV?$Array@VPackage@Entity@StateRepository@@V?$ContainerOperations@VPackage@Entity@StateRepository@@V123@@Common@@VNoKey@5@V?$ContainerOperations@VNoKey@Common@@VPackage@Entity@StateRepository@@@5@V?$ArrayOperations@VPackage@Entity@StateRepository@@VNoKey@Common@@@5@@3@_NW4PackageStatusCallOrigin@23@PEA_N@Z; Common::Deployment::PackageStatus::SetRelatedPackages(PackageRepository::IRepositorySession *,__int64,Common::Array<StateRepository::Entity::Package,Common::ContainerOperations<StateRepository::Entity::Package,StateRepository::Entity::Package>,Common::NoKey,Common::ContainerOperations<Common::NoKey,StateRepository::Entity::Package>,Common::ArrayOperations<StateRepository::Entity::Package,Common::NoKey>> const &,bool,Common::Deployment::PackageStatusCallOrigin,bool *)
0x1801e6597  mov     r15d, eax
0x1801e659a  test    eax, eax
0x1801e659c  jns     short loc_1801E65D6
0x1801e659e  mov     rcx, [rbp+3Fh]; this
0x1801e65a2  mov     r9d, eax; char *
0x1801e65a5  lea     r8, aOnecoreAdminAp_151; "onecore\\admin\\appmodel\\common\\packa"...
0x1801e65ac  mov     edx, 3F8h; void *
0x1801e65b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e65b6  nop
0x1801e65b7  lea     rcx, [rbp+37h+var_50]
0x1801e65bb  call    ??1?$Array@VPackage@Entity@StateRepository@@V?$ContainerOperations@VPackage@Entity@StateRepository@@V123@@Common@@VNoKey@5@V?$ContainerOperations@VNoKey@Common@@VPackage@Entity@StateRepository@@@5@V?$ArrayOperations@VPackage@Entity@StateRepository@@VNoKey@Common@@@5@@Common@@QEAA@XZ; Common::Array<StateRepository::Entity::Package,Common::ContainerOperations<StateRepository::Entity::Package,StateRepository::Entity::Package>,Common::NoKey,Common::ContainerOperations<Common::NoKey,StateRepository::Entity::Package>,Common::ArrayOperations<StateRepository::Entity::Package,Common::NoKey>>::~Array<StateRepository::Entity::Package,Common::ContainerOperations<StateRepository::Entity::Package,StateRepository::Entity::Package>,Common::NoKey,Common::ContainerOperations<Common::NoKey,StateRepository::Entity::Package>,Common::ArrayOperations<StateRepository::Entity::Package,Common::NoKey>>(void)
0x1801e65c0  nop
0x1801e65c1  cmp     dword ptr [rbp+37h+var_60], 0
0x1801e65c5  jz      short loc_1801E65D1
0x1801e65c7  lea     rcx, [rbp+37h+var_60]; this
0x1801e65cb  call    ?Revert@ImpersonationContext@Common@@QEAAXXZ; Common::ImpersonationContext::Revert(void)
0x1801e65d0  nop
0x1801e65d1  jmp     loc_1801E62E2
0x1801e65d6  mov     rcx, rsi
0x1801e65d9  cmp     byte ptr [rbp+37h+arg_20], 0
  ... truncated ...
```
