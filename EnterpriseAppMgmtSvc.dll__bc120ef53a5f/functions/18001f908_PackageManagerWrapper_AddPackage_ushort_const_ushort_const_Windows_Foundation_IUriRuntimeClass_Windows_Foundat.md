# PackageManagerWrapper::AddPackage(ushort const *,ushort const *,Windows::Foundation::IUriRuntimeClass *,Windows::Foundation::Collections::Internal::Vector<Windows::Foundation::Uri *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Foundation::Uri *>> *,Windows::Management::Deployment::Internal::DeploymentOptionsInternal,bool,bool,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> *,Windows::Foundation::Collections::Internal::Vector<Windows::Foundation::Uri *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Foundation::Uri *>> *)

- ea: `0x18001f908`
- end: `0x18001fcfe`
- name: `?AddPackage@PackageManagerWrapper@@QEAAJPEBG0PEAUIUriRuntimeClass@Foundation@Windows@@PEAV?$Vector@PEAVUri@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAVUri@Foundation@Windows@@@Internal@Collections@23@U?$DefaultLifetimeTraits@PEAVUri@Foundation@Windows@@@5623@U?$DefaultVectorOptions@PEAVUri@Foundation@Windows@@@5623@@Internal@Collections@34@W4DeploymentOptionsInternal@6Deployment@Management@4@_N4PEAV?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@6734@2@Z`
- size: `1014`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800166d8`
- `0x180016a80`
- `0x18001f598`

## callees

- `0x180001c24`
- `0x18000d3dc`
- `0x18001d65c`
- `0x18001dbd0`
- `0x18001f908`
- `0x18001fd40`
- `0x180023d74`
- `0x180023f98`
- `0x180028c1c`
- `0x180029444`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18001fa03`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001fa94`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001fb46`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001fbcc`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001fc77`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001fa03`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001fa94`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001fb46`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001fbcc`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001fc77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fb83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fb83`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001fb6f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001fb6f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001fc37`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001fc37`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18001f962`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18001f962`
- `DMCmnUtils!DmRevertToSelf` at `0x18001f9e2`
- `DMCmnUtils!DmRevertToSelf` at `0x18001fa73`
- `DMCmnUtils!DmRevertToSelf` at `0x18001fb26`
- `DMCmnUtils!DmRevertToSelf` at `0x18001fbac`
- `DMCmnUtils!DmRevertToSelf` at `0x18001fc1a`
- `DMCmnUtils!DmRevertToSelf` at `0x18001fc5b`
- `DMCmnUtils!DmRevertToSelf` at `0x18001f9e2`
- `DMCmnUtils!DmRevertToSelf` at `0x18001fa73`
- `DMCmnUtils!DmRevertToSelf` at `0x18001fb26`
- `DMCmnUtils!DmRevertToSelf` at `0x18001fbac`
- `DMCmnUtils!DmRevertToSelf` at `0x18001fc1a`
- `DMCmnUtils!DmRevertToSelf` at `0x18001fc5b`

## string_xrefs

- `0x18001f9ad`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18001f9ca`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18001fb05`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18001fbfa`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PackageManagerWrapper::AddPackage(
        PackageManagerWrapper *a1,
        const unsigned __int16 *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        char a7)
{
  int v9; // eax
  unsigned int v10; // ebx
  int v11; // eax
  unsigned int v12; // r8d
  char *v14; // rax
  char *v15; // rbx
  int v16; // eax
  unsigned int v17; // r8d
  void *v18; // rdi
  int v19; // eax
  unsigned int v20; // esi
  int v21; // eax
  unsigned int v22; // r8d
  struct _TP_WORK *ThreadpoolWork; // rsi
  signed int LastError; // eax
  int v25; // eax
  unsigned int v26; // r8d
  int updated; // eax
  int v28; // eax
  unsigned int v29; // r8d
  int v30; // eax
  unsigned int v31; // r8d
  int v32; // [rsp+28h] [rbp-69h]
  int v33; // [rsp+28h] [rbp-69h]
  int v34; // [rsp+28h] [rbp-69h]
  int v35; // [rsp+28h] [rbp-69h]
  int v36; // [rsp+28h] [rbp-69h]
  int v37; // [rsp+28h] [rbp-69h]
  void **v38; // [rsp+68h] [rbp-29h] BYREF
  char v39; // [rsp+70h] [rbp-21h]
  __int128 v40; // [rsp+78h] [rbp-19h]
  int v41; // [rsp+88h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+3Fh]
  char *v44; // [rsp+E0h] [rbp+4Fh] BYREF
  __int64 v45; // [rsp+E8h] [rbp+57h]

  v45 = a3;
  if ( !a2 || !a4 )
    return 2147942487LL;
  if ( !a7 )
  {
    LODWORD(v44) = 0;
    RtlGetDeviceFamilyInfoEnum(0, &v44, 0);
  }
  v38 = &ImpersonateUserHelper::`vftable';
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v9 = (unsigned int)ImpersonateUserHelper::ImpersonateUser((ImpersonateUser *)&v38);
  if ( v9 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x35C,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
      (const char *)(unsigned int)v9,
      v32);
    v10 = -2147024891;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x35E,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
      (const char *)0x80070005LL,
      v33);
    if ( v39 )
    {
      v11 = DmRevertToSelf();
      if ( v11 < 0 )
        wil::details::in1diag3::_FailFast_Hr(retaddr, (void *)0x4B, v12, (const char *)(unsigned int)v11, v34);
    }
    if ( *((_QWORD *)&v40 + 1) )
      operator delete[](*((void **)&v40 + 1));
    return v10;
  }
  v14 = (char *)operator new(0x70u);
  v15 = v14;
  v44 = v14;
  if ( v14 )
  {
    *(_QWORD *)v14 = 0;
    *((_QWORD *)v14 + 1) = 0;
    *((_DWORD *)v14 + 4) = 0;
    *(_OWORD *)(v14 + 24) = 0;
    *((_DWORD *)v14 + 10) = 0;
    *((_OWORD *)v14 + 3) = 0;
    *((_DWORD *)v14 + 16) = 0;
    *(_OWORD *)(v14 + 72) = 0;
    *((_DWORD *)v14 + 22) = 0;
    *((_QWORD *)v14 + 12) = 0;
    *((_QWORD *)v14 + 13) = 0;
  }
  else
  {
    v15 = 0;
  }
  v44 = v15;
  if ( v15 )
  {
    v18 = (void *)*((_QWORD *)&v40 + 1);
    v35 = a5;
    v19 = AddPackageParameters::Initialize(v15, a2, v45, a4);
    v20 = v19;
    if ( v19 >= 0 )
    {
      v44 = 0;
      ThreadpoolWork = CreateThreadpoolWork(
                         (PTP_WORK_CALLBACK)DoAddPackageWork,
                         v15,
                         &g_provisioningCallbackEnvironment);
      if ( ThreadpoolWork )
      {
        updated = UpdateInstallStatusToInstalling(a2, HKEY_CURRENT_USER);
        v10 = updated;
        if ( updated >= 0 )
        {
          SubmitThreadpoolWork(ThreadpoolWork);
          PackageManagerWrapper::AddRefService(a1);
          Common::AutoPtrDeallocate<AddPackageParameters>(0);
          if ( v39 )
          {
            v30 = DmRevertToSelf();
            if ( v30 < 0 )
              wil::details::in1diag3::_FailFast_Hr(retaddr, (void *)0x4B, v31, (const char *)(unsigned int)v30, v35);
          }
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x382,
            (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
            (const char *)(unsigned int)updated,
            v35);
          Common::AutoPtrDeallocate<AddPackageParameters>(0);
          if ( v39 )
          {
            v28 = DmRevertToSelf();
            if ( v28 < 0 )
              wil::details::in1diag3::_FailFast_Hr(retaddr, (void *)0x4B, v29, (const char *)(unsigned int)v28, v37);
          }
        }
        if ( v18 )
          operator delete[](v18);
      }
      else
      {
        LastError = GetLastError();
        v10 = LastError;
        if ( LastError > 0 )
          v10 = (unsigned __int16)LastError | 0x80070000;
        Common::AutoPtrDeallocate<AddPackageParameters>(0);
        if ( v39 )
        {
          v25 = DmRevertToSelf();
          if ( v25 < 0 )
            wil::details::in1diag3::_FailFast_Hr(retaddr, (void *)0x4B, v26, (const char *)(unsigned int)v25, v35);
        }
        if ( v18 )
          operator delete[](v18);
      }
      return v10;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x36D,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
      (const char *)(unsigned int)v19,
      v35);
    Common::AutoPtrDeallocate<AddPackageParameters>(v15);
    if ( v39 )
    {
      v21 = DmRevertToSelf();
      if ( v21 < 0 )
        wil::details::in1diag3::_FailFast_Hr(retaddr, (void *)0x4B, v22, (const char *)(unsigned int)v21, v36);
    }
    if ( v18 )
      operator delete[](v18);
    return v20;
  }
  else
  {
    Common::AutoPtrDeallocate<AddPackageParameters>(0);
    if ( v39 )
    {
      v16 = DmRevertToSelf();
      if ( v16 < 0 )
        wil::details::in1diag3::_FailFast_Hr(retaddr, (void *)0x4B, v17, (const char *)(unsigned int)v16, v32);
    }
    if ( *((_QWORD *)&v40 + 1) )
      operator delete[](*((void **)&v40 + 1));
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18001f908  mov     rax, rsp
0x18001f90b  mov     [rax+20h], rbx
0x18001f90f  mov     [rax+18h], r8
0x18001f913  mov     [rax+8], rcx
0x18001f917  push    rbp
0x18001f918  push    rsi
0x18001f919  push    rdi
0x18001f91a  push    r12
0x18001f91c  push    r13
0x18001f91e  push    r14
0x18001f920  push    r15
0x18001f922  lea     rbp, [rax-3Fh]
0x18001f926  sub     rsp, 90h
0x18001f92d  mov     r13, r9
0x18001f930  mov     r15, rdx
0x18001f933  xor     edi, edi
0x18001f935  test    rdx, rdx
0x18001f938  jz      loc_18001FC89
0x18001f93e  test    r9, r9
0x18001f941  jz      loc_18001FC89
0x18001f947  mov     r12b, [rbp+37h+arg_30]
0x18001f94b  mov     esi, [rbp+37h+arg_28]
0x18001f94e  test    r12b, r12b
0x18001f951  jnz     short loc_18001F97C
0x18001f953  or      esi, 10h
0x18001f956  mov     dword ptr [rbp+37h+arg_8], edi
0x18001f959  xor     r8d, r8d
0x18001f95c  lea     rdx, [rbp+37h+arg_8]
0x18001f960  xor     ecx, ecx
0x18001f962  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18001f969  nop     dword ptr [rax+rax+00h]
0x18001f96e  cmp     dword ptr [rbp+37h+arg_8], 0Ah
0x18001f972  jnz     short loc_18001F97C
0x18001f974  and     esi, 0FFFFFFFEh
0x18001f977  mov     r14b, 1
0x18001f97a  jmp     short loc_18001F980
0x18001f97c  mov     r14b, [rbp+37h+arg_38]
0x18001f980  lea     rax, ??_7ImpersonateUserHelper@@6B@; const ImpersonateUserHelper::`vftable'
0x18001f987  mov     [rbp+37h+var_60], rax
0x18001f98b  mov     [rbp+37h+var_58], dil
0x18001f98f  xorps   xmm0, xmm0
0x18001f992  movups  [rbp+37h+var_50], xmm0
0x18001f996  mov     [rbp+37h+var_40], edi
0x18001f999  lea     rcx, [rbp+37h+var_60]; this
0x18001f99d  call    ?ImpersonateUser@ImpersonateUserHelper@@QEAAJXZ; ImpersonateUserHelper::ImpersonateUser(void)
0x18001f9a2  mov     rcx, [rbp+3Fh]; this
0x18001f9a6  test    eax, eax
0x18001f9a8  jns     short loc_18001FA17
0x18001f9aa  mov     r9d, eax; char *
0x18001f9ad  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18001f9b4  mov     edx, 35Ch; void *
0x18001f9b9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001f9be  mov     rcx, [rbp+3Fh]; this
0x18001f9c2  mov     ebx, 80070005h
0x18001f9c7  mov     r9d, ebx; char *
0x18001f9ca  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18001f9d1  mov     edx, 35Eh; void *
0x18001f9d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f9db  nop
0x18001f9dc  cmp     [rbp+37h+var_58], dil
0x18001f9e0  jz      short loc_18001F9FA
0x18001f9e2  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x18001f9e9  nop     dword ptr [rax+rax+00h]
0x18001f9ee  mov     rcx, [rbp+3Fh]; this
0x18001f9f2  test    eax, eax
0x18001f9f4  js      loc_18001FCC6
0x18001f9fa  mov     rcx, qword ptr [rbp+37h+var_50+8]
0x18001f9fe  test    rcx, rcx
0x18001fa01  jz      short loc_18001FA10
0x18001fa03  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001fa0a  nop     dword ptr [rax+rax+00h]
0x18001fa0f  nop
0x18001fa10  mov     eax, ebx
0x18001fa12  jmp     loc_18001FC8E
0x18001fa17  mov     ecx, 70h ; 'p'; Size
0x18001fa1c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001fa21  mov     rbx, rax
0x18001fa24  mov     [rbp+37h+arg_8], rax
0x18001fa28  test    rax, rax
0x18001fa2b  jz      short loc_18001FA59
0x18001fa2d  mov     [rax], rdi
0x18001fa30  mov     [rax+8], rdi
0x18001fa34  mov     [rax+10h], edi
0x18001fa37  xorps   xmm0, xmm0
0x18001fa3a  movups  xmmword ptr [rax+18h], xmm0
0x18001fa3e  mov     [rax+28h], edi
0x18001fa41  movups  xmmword ptr [rax+30h], xmm0
0x18001fa45  mov     [rax+40h], edi
0x18001fa48  movups  xmmword ptr [rax+48h], xmm0
0x18001fa4c  mov     [rax+58h], edi
0x18001fa4f  mov     [rax+60h], rdi
0x18001fa53  mov     [rax+68h], rdi
0x18001fa57  jmp     short loc_18001FA5C
0x18001fa59  mov     rbx, rdi
0x18001fa5c  mov     [rbp+37h+arg_8], rbx
0x18001fa60  test    rbx, rbx
0x18001fa63  jnz     short loc_18001FAAB
0x18001fa65  xor     ecx, ecx
0x18001fa67  call    ??$AutoPtrDeallocate@VAddPackageParameters@@@Common@@YAXPEAVAddPackageParameters@@@Z; Common::AutoPtrDeallocate<AddPackageParameters>(AddPackageParameters *)
0x18001fa6c  nop
0x18001fa6d  cmp     [rbp+37h+var_58], dil
0x18001fa71  jz      short loc_18001FA8B
0x18001fa73  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x18001fa7a  nop     dword ptr [rax+rax+00h]
0x18001fa7f  mov     rcx, [rbp+3Fh]; this
0x18001fa83  test    eax, eax
0x18001fa85  js      loc_18001FCD4
0x18001fa8b  mov     rcx, qword ptr [rbp+37h+var_50+8]
0x18001fa8f  test    rcx, rcx
0x18001fa92  jz      short loc_18001FAA1
0x18001fa94  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001fa9b  nop     dword ptr [rax+rax+00h]
0x18001faa0  nop
0x18001faa1  mov     eax, 8007000Eh
0x18001faa6  jmp     loc_18001FC8E
0x18001faab  mov     rdi, qword ptr [rbp+37h+var_50+8]
0x18001faaf  mov     rax, [rbp+37h+arg_48]
0x18001fab6  mov     [rsp+50h], rax
0x18001fabb  mov     rax, [rbp+37h+arg_40]
0x18001fac2  mov     [rsp+0C0h+var_78], rax
0x18001fac7  mov     [rsp+0C0h+var_80], rdi
0x18001facc  mov     byte ptr [rsp+0C0h+var_88], r14b
0x18001fad1  mov     [rsp+0C0h+var_90], r12b
0x18001fad6  mov     dword ptr [rsp+0C0h+var_98], esi
0x18001fada  mov     rax, qword ptr [rbp+37h+arg_20]
0x18001fade  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x18001fae3  mov     r9, r13
0x18001fae6  mov     r8, [rbp+37h+arg_10]
0x18001faea  mov     rdx, r15
0x18001faed  mov     rcx, rbx
0x18001faf0  call    ?Initialize@AddPackageParameters@@QEAAJPEBG0PEAUIUriRuntimeClass@Foundation@Windows@@PEAV?$Vector@PEAVUri@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAVUri@Foundation@Windows@@@Internal@Collections@23@U?$DefaultLifetimeTraits@PEAVUri@Foundation@Windows@@@5623@U?$DefaultVectorOptions@PEAVUri@Foundation@Windows@@@5623@@Internal@Collections@34@W4DeploymentOptionsInternal@6Deployment@Management@4@_N40PEAV?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@6734@2@Z; AddPackageParameters::Initialize(ushort const *,ushort const *,Windows::Foundation::IUriRuntimeClass *,Windows::Foundation::Collections::Internal::Vector<Windows::Foundation::Uri *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Foundation::Uri *>> *,Windows::Management::Deployment::Internal::DeploymentOptionsInternal,bool,bool,ushort const *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> *,Windows::Foundation::Collections::Internal::Vector<Windows::Foundation::Uri *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Foundation::Uri *>> *)
0x18001faf5  mov     esi, eax
0x18001faf7  mov     rcx, [rbp+3Fh]; this
0x18001fafb  xor     r14d, r14d
0x18001fafe  test    eax, eax
0x18001fb00  jns     short loc_18001FB5A
0x18001fb02  mov     r9d, eax; char *
0x18001fb05  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18001fb0c  mov     edx, 36Dh; void *
0x18001fb11  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001fb16  nop
0x18001fb17  mov     rcx, rbx
0x18001fb1a  call    ??$AutoPtrDeallocate@VAddPackageParameters@@@Common@@YAXPEAVAddPackageParameters@@@Z; Common::AutoPtrDeallocate<AddPackageParameters>(AddPackageParameters *)
0x18001fb1f  nop
0x18001fb20  cmp     [rbp+37h+var_58], r14b
0x18001fb24  jz      short loc_18001FB3E
0x18001fb26  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x18001fb2d  nop     dword ptr [rax+rax+00h]
0x18001fb32  mov     rcx, [rbp+3Fh]; this
0x18001fb36  test    eax, eax
0x18001fb38  js      loc_18001FCE2
0x18001fb3e  test    rdi, rdi
0x18001fb41  jz      short loc_18001FB53
0x18001fb43  mov     rcx, rdi
0x18001fb46  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001fb4d  nop     dword ptr [rax+rax+00h]
0x18001fb52  nop
0x18001fb53  mov     eax, esi
0x18001fb55  jmp     loc_18001FC8E
0x18001fb5a  mov     [rbp+37h+arg_8], r14
0x18001fb5e  lea     r8, ?g_provisioningCallbackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x18001fb65  mov     rdx, rbx; pv
0x18001fb68  lea     rcx, ?DoAddPackageWork@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18001fb6f  call    cs:__imp_CreateThreadpoolWork
0x18001fb76  nop     dword ptr [rax+rax+00h]
0x18001fb7b  mov     rsi, rax
0x18001fb7e  test    rax, rax
0x18001fb81  jnz     short loc_18001FBDE
0x18001fb83  call    cs:__imp_GetLastError
0x18001fb8a  nop     dword ptr [rax+rax+00h]
0x18001fb8f  mov     ebx, eax
0x18001fb91  test    eax, eax
0x18001fb93  jle     short loc_18001FB9E
0x18001fb95  movzx   ebx, ax
0x18001fb98  or      ebx, 80070000h
0x18001fb9e  xor     ecx, ecx
0x18001fba0  call    ??$AutoPtrDeallocate@VAddPackageParameters@@@Common@@YAXPEAVAddPackageParameters@@@Z; Common::AutoPtrDeallocate<AddPackageParameters>(AddPackageParameters *)
0x18001fba5  nop
0x18001fba6  cmp     [rbp+37h+var_58], r14b
0x18001fbaa  jz      short loc_18001FBC4
0x18001fbac  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x18001fbb3  nop     dword ptr [rax+rax+00h]
0x18001fbb8  mov     rcx, [rbp+3Fh]; this
0x18001fbbc  test    eax, eax
0x18001fbbe  js      loc_18001FCF0
0x18001fbc4  test    rdi, rdi
0x18001fbc7  jz      short loc_18001FBD9
0x18001fbc9  mov     rcx, rdi
0x18001fbcc  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001fbd3  nop     dword ptr [rax+rax+00h]
0x18001fbd8  nop
0x18001fbd9  jmp     loc_18001FA10
0x18001fbde  mov     rdx, 0FFFFFFFF80000001h; HKEY
0x18001fbe5  mov     rcx, r15; unsigned __int16 *
0x18001fbe8  call    ?UpdateInstallStatusToInstalling@@YAJPEBGPEAUHKEY__@@@Z; UpdateInstallStatusToInstalling(ushort const *,HKEY__ *)
0x18001fbed  mov     ebx, eax
0x18001fbef  mov     rcx, [rbp+3Fh]; this
0x18001fbf3  test    eax, eax
0x18001fbf5  jns     short loc_18001FC34
0x18001fbf7  mov     r9d, eax; char *
0x18001fbfa  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18001fc01  mov     edx, 382h; void *
0x18001fc06  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001fc0b  nop
0x18001fc0c  xor     ecx, ecx
0x18001fc0e  call    ??$AutoPtrDeallocate@VAddPackageParameters@@@Common@@YAXPEAVAddPackageParameters@@@Z; Common::AutoPtrDeallocate<AddPackageParameters>(AddPackageParameters *)
0x18001fc13  nop
0x18001fc14  cmp     [rbp+37h+var_58], r14b
0x18001fc18  jz      short loc_18001FC6F
0x18001fc1a  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x18001fc21  nop     dword ptr [rax+rax+00h]
0x18001fc26  mov     rcx, [rbp+3Fh]; this
0x18001fc2a  test    eax, eax
0x18001fc2c  js      loc_18001FCB8
0x18001fc32  jmp     short loc_18001FC6F
0x18001fc34  mov     rcx, rsi; pwk
0x18001fc37  call    cs:__imp_SubmitThreadpoolWork
0x18001fc3e  nop     dword ptr [rax+rax+00h]
0x18001fc43  mov     rcx, [rbp+37h+arg_0]; this
0x18001fc47  call    ?AddRefService@PackageManagerWrapper@@AEAAXXZ; PackageManagerWrapper::AddRefService(void)
0x18001fc4c  nop
0x18001fc4d  xor     ecx, ecx
0x18001fc4f  call    ??$AutoPtrDeallocate@VAddPackageParameters@@@Common@@YAXPEAVAddPackageParameters@@@Z; Common::AutoPtrDeallocate<AddPackageParameters>(AddPackageParameters *)
0x18001fc54  nop
0x18001fc55  cmp     [rbp+37h+var_58], r14b
0x18001fc59  jz      short loc_18001FC6F
0x18001fc5b  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x18001fc62  nop     dword ptr [rax+rax+00h]
0x18001fc67  mov     rcx, [rbp+3Fh]; this
0x18001fc6b  test    eax, eax
0x18001fc6d  js      short loc_18001FCAA
0x18001fc6f  test    rdi, rdi
0x18001fc72  jz      short loc_18001FC84
0x18001fc74  mov     rcx, rdi
0x18001fc77  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001fc7e  nop     dword ptr [rax+rax+00h]
0x18001fc83  nop
0x18001fc84  jmp     loc_18001FA10
0x18001fc89  mov     eax, 80070057h
0x18001fc8e  mov     rbx, [rsp+0C0h+arg_18]
0x18001fc96  add     rsp, 90h
0x18001fc9d  pop     r15
0x18001fc9f  pop     r14
0x18001fca1  pop     r13
0x18001fca3  pop     r12
0x18001fca5  pop     rdi
0x18001fca6  pop     rsi
0x18001fca7  pop     rbp
0x18001fca8  retn
0x18001fcaa  mov     r9d, eax; char *
0x18001fcad  mov     edx, 4Bh ; 'K'; void *
0x18001fcb2  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001fcb8  mov     r9d, eax; char *
0x18001fcbb  mov     edx, 4Bh ; 'K'; void *
0x18001fcc0  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001fcc6  mov     r9d, eax; char *
0x18001fcc9  mov     edx, 4Bh ; 'K'; void *
0x18001fcce  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001fcd4  mov     r9d, eax; char *
0x18001fcd7  mov     edx, 4Bh ; 'K'; void *
0x18001fcdc  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001fce2  mov     r9d, eax; char *
0x18001fce5  mov     edx, 4Bh ; 'K'; void *
0x18001fcea  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001fcf0  mov     r9d, eax; char *
0x18001fcf3  mov     edx, 4Bh ; 'K'; void *
0x18001fcf8  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
