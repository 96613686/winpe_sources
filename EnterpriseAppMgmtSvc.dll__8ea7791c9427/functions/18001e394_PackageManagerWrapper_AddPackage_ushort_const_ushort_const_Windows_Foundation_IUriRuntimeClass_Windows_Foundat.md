# PackageManagerWrapper::AddPackage(ushort const *,ushort const *,Windows::Foundation::IUriRuntimeClass *,Windows::Foundation::Collections::Internal::Vector<Windows::Foundation::Uri *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Foundation::Uri *>> *,Windows::Management::Deployment::Internal::DeploymentOptionsInternal,bool,bool,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> *,Windows::Foundation::Collections::Internal::Vector<Windows::Foundation::Uri *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Foundation::Uri *>> *)

- ea: `0x18001e394`
- end: `0x18001e72b`
- name: `?AddPackage@PackageManagerWrapper@@QEAAJPEBG0PEAUIUriRuntimeClass@Foundation@Windows@@PEAV?$Vector@PEAVUri@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAVUri@Foundation@Windows@@@Internal@Collections@23@U?$DefaultLifetimeTraits@PEAVUri@Foundation@Windows@@@5623@U?$DefaultVectorOptions@PEAVUri@Foundation@Windows@@@5623@@Internal@Collections@34@W4DeploymentOptionsInternal@6Deployment@Management@4@_N4PEAV?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@6734@2@Z`
- size: `919`
- prototype: `__int64 __fastcall(PackageManagerWrapper *, const unsigned __int16 *, __int64, __int64, int, __int64, char)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800159a4`
- `0x180015d78`
- `0x18001e024`

## callees

- `0x180001bf4`
- `0x18000cfe8`
- `0x18001c5b8`
- `0x18001cb28`
- `0x18001e394`
- `0x18001e770`
- `0x180022510`
- `0x1800226f0`
- `0x180026c14`
- `0x1800273c8`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18001e483`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001e508`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001e5ae`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001e61c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001e6ab`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001e483`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001e508`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001e5ae`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001e61c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001e6ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e5df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e5df`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001e5d1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001e5d1`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001e677`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001e677`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18001e3ee`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18001e3ee`
- `DMCmnUtils!DmRevertToSelf` at `0x18001e468`
- `DMCmnUtils!DmRevertToSelf` at `0x18001e4ed`
- `DMCmnUtils!DmRevertToSelf` at `0x18001e594`
- `DMCmnUtils!DmRevertToSelf` at `0x18001e602`
- `DMCmnUtils!DmRevertToSelf` at `0x18001e664`
- `DMCmnUtils!DmRevertToSelf` at `0x18001e695`
- `DMCmnUtils!DmRevertToSelf` at `0x18001e468`
- `DMCmnUtils!DmRevertToSelf` at `0x18001e4ed`
- `DMCmnUtils!DmRevertToSelf` at `0x18001e594`
- `DMCmnUtils!DmRevertToSelf` at `0x18001e602`
- `DMCmnUtils!DmRevertToSelf` at `0x18001e664`
- `DMCmnUtils!DmRevertToSelf` at `0x18001e695`

## string_xrefs

- `0x18001e433`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18001e450`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18001e573`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18001e644`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  __int64 v12; // r8
  char *v14; // rax
  char *v15; // rbx
  int v16; // eax
  __int64 v17; // r8
  void *v18; // rdi
  int v19; // eax
  unsigned int v20; // esi
  int v21; // eax
  __int64 v22; // r8
  struct _TP_WORK *ThreadpoolWork; // rsi
  signed int LastError; // eax
  int v25; // eax
  __int64 v26; // r8
  int updated; // eax
  int v28; // eax
  __int64 v29; // r8
  int v30; // eax
  __int64 v31; // r8
  int v32; // [rsp+28h] [rbp-69h]
  int v33; // [rsp+28h] [rbp-69h]
  int v34; // [rsp+28h] [rbp-69h]
  void **v35; // [rsp+68h] [rbp-29h] BYREF
  char v36; // [rsp+70h] [rbp-21h]
  __int128 v37; // [rsp+78h] [rbp-19h]
  int v38; // [rsp+88h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+3Fh]
  char *v41; // [rsp+E0h] [rbp+4Fh] BYREF
  __int64 v42; // [rsp+E8h] [rbp+57h]

  v42 = a3;
  if ( !a2 || !a4 )
    return 2147942487LL;
  if ( !a7 )
  {
    LODWORD(v41) = 0;
    RtlGetDeviceFamilyInfoEnum(0, &v41, 0);
  }
  v35 = &ImpersonateUserHelper::`vftable';
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v9 = ImpersonateUserHelper::ImpersonateUser((ImpersonateUserHelper *)&v35);
  if ( v9 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x35C,
      (int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
      (const char *)(unsigned int)v9);
    v10 = -2147024891;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x35E,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
      (const char *)0x80070005LL,
      v32);
    if ( v36 )
    {
      v11 = DmRevertToSelf();
      if ( v11 < 0 )
        wil::details::in1diag3::_FailFast_Hr(retaddr, (void *)0x4B, v12, (const char *)(unsigned int)v11, v33);
    }
    if ( *((_QWORD *)&v37 + 1) )
      operator delete[](*((void **)&v37 + 1));
    return v10;
  }
  v14 = (char *)operator new(0x70u);
  v15 = v14;
  v41 = v14;
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
  v41 = v15;
  if ( v15 )
  {
    v18 = (void *)*((_QWORD *)&v37 + 1);
    v34 = a5;
    v19 = AddPackageParameters::Initialize(v15, a2, v42, a4);
    v20 = v19;
    if ( v19 >= 0 )
    {
      v41 = 0;
      ThreadpoolWork = CreateThreadpoolWork(DoAddPackageWork, v15, &g_provisioningCallbackEnvironment);
      if ( ThreadpoolWork )
      {
        updated = UpdateInstallStatusToInstalling(a2, HKEY_CURRENT_USER);
        v10 = updated;
        if ( updated >= 0 )
        {
          SubmitThreadpoolWork(ThreadpoolWork);
          PackageManagerWrapper::AddRefService(a1);
          Common::AutoPtrDeallocate<AddPackageParameters>(0);
          if ( v36 )
          {
            v30 = DmRevertToSelf();
            if ( v30 < 0 )
              wil::details::in1diag3::_FailFast_Hr(retaddr, (void *)0x4B, v31, (const char *)(unsigned int)v30, v34);
          }
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x382,
            (int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
            (const char *)(unsigned int)updated);
          Common::AutoPtrDeallocate<AddPackageParameters>(0);
          if ( v36 )
          {
            v28 = DmRevertToSelf();
            if ( v28 < 0 )
              wil::details::in1diag3::_FailFast_Hr(retaddr, (void *)0x4B, v29, (const char *)(unsigned int)v28, v34);
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
        if ( v36 )
        {
          v25 = DmRevertToSelf();
          if ( v25 < 0 )
            wil::details::in1diag3::_FailFast_Hr(retaddr, (void *)0x4B, v26, (const char *)(unsigned int)v25, v34);
        }
        if ( v18 )
          operator delete[](v18);
      }
      return v10;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x36D,
      (int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
      (const char *)(unsigned int)v19);
    Common::AutoPtrDeallocate<AddPackageParameters>((AddPackageParameters *)v15);
    if ( v36 )
    {
      v21 = DmRevertToSelf();
      if ( v21 < 0 )
        wil::details::in1diag3::_FailFast_Hr(retaddr, (void *)0x4B, v22, (const char *)(unsigned int)v21, v34);
    }
    if ( v18 )
      operator delete[](v18);
    return v20;
  }
  else
  {
    Common::AutoPtrDeallocate<AddPackageParameters>(0);
    if ( v36 )
    {
      v16 = DmRevertToSelf();
      if ( v16 < 0 )
        wil::details::in1diag3::_FailFast_Hr(retaddr, (void *)0x4B, v17, (const char *)(unsigned int)v16, v32);
    }
    if ( *((_QWORD *)&v37 + 1) )
      operator delete[](*((void **)&v37 + 1));
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18001e394  mov     rax, rsp
0x18001e397  mov     [rax+20h], rbx
0x18001e39b  mov     [rax+18h], r8
0x18001e39f  mov     [rax+8], rcx
0x18001e3a3  push    rbp
0x18001e3a4  push    rsi
0x18001e3a5  push    rdi
0x18001e3a6  push    r12
0x18001e3a8  push    r13
0x18001e3aa  push    r14
0x18001e3ac  push    r15
0x18001e3ae  lea     rbp, [rax-3Fh]
0x18001e3b2  sub     rsp, 90h
0x18001e3b9  mov     r13, r9
0x18001e3bc  mov     r15, rdx
0x18001e3bf  xor     edi, edi
0x18001e3c1  test    rdx, rdx
0x18001e3c4  jz      loc_18001E6B7
0x18001e3ca  test    r9, r9
0x18001e3cd  jz      loc_18001E6B7
0x18001e3d3  mov     r12b, [rbp+37h+arg_30]
0x18001e3d7  mov     esi, [rbp+37h+arg_28]
0x18001e3da  test    r12b, r12b
0x18001e3dd  jnz     short loc_18001E402
0x18001e3df  or      esi, 10h
0x18001e3e2  mov     dword ptr [rbp+37h+arg_8], edi
0x18001e3e5  xor     r8d, r8d
0x18001e3e8  lea     rdx, [rbp+37h+arg_8]
0x18001e3ec  xor     ecx, ecx
0x18001e3ee  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18001e3f4  cmp     dword ptr [rbp+37h+arg_8], 0Ah
0x18001e3f8  jnz     short loc_18001E402
0x18001e3fa  and     esi, 0FFFFFFFEh
0x18001e3fd  mov     r14b, 1
0x18001e400  jmp     short loc_18001E406
0x18001e402  mov     r14b, [rbp+37h+arg_38]
0x18001e406  lea     rax, ??_7ImpersonateUserHelper@@6B@; const ImpersonateUserHelper::`vftable'
0x18001e40d  mov     [rbp+37h+var_60], rax
0x18001e411  mov     [rbp+37h+var_58], dil
0x18001e415  xorps   xmm0, xmm0
0x18001e418  movups  [rbp+37h+var_50], xmm0
0x18001e41c  mov     [rbp+37h+var_40], edi
0x18001e41f  lea     rcx, [rbp+37h+var_60]; this
0x18001e423  call    ?ImpersonateUser@ImpersonateUserHelper@@QEAAJXZ; ImpersonateUserHelper::ImpersonateUser(void)
0x18001e428  mov     rcx, [rbp+3Fh]; this
0x18001e42c  test    eax, eax
0x18001e42e  jns     short loc_18001E491
0x18001e430  mov     r9d, eax; char *
0x18001e433  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18001e43a  mov     edx, 35Ch; void *
0x18001e43f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001e444  mov     rcx, [rbp+3Fh]; this
0x18001e448  mov     ebx, 80070005h
0x18001e44d  mov     r9d, ebx; char *
0x18001e450  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18001e457  mov     edx, 35Eh; void *
0x18001e45c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e461  nop
0x18001e462  cmp     [rbp+37h+var_58], dil
0x18001e466  jz      short loc_18001E47A
0x18001e468  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x18001e46e  mov     rcx, [rbp+3Fh]; this
0x18001e472  test    eax, eax
0x18001e474  js      loc_18001E6F3
0x18001e47a  mov     rcx, qword ptr [rbp+37h+var_50+8]
0x18001e47e  test    rcx, rcx
0x18001e481  jz      short loc_18001E48A
0x18001e483  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001e489  nop
0x18001e48a  mov     eax, ebx
0x18001e48c  jmp     loc_18001E6BC
0x18001e491  mov     ecx, 70h ; 'p'; Size
0x18001e496  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e49b  mov     rbx, rax
0x18001e49e  mov     [rbp+37h+arg_8], rax
0x18001e4a2  test    rax, rax
0x18001e4a5  jz      short loc_18001E4D3
0x18001e4a7  mov     [rax], rdi
0x18001e4aa  mov     [rax+8], rdi
0x18001e4ae  mov     [rax+10h], edi
0x18001e4b1  xorps   xmm0, xmm0
0x18001e4b4  movups  xmmword ptr [rax+18h], xmm0
0x18001e4b8  mov     [rax+28h], edi
0x18001e4bb  movups  xmmword ptr [rax+30h], xmm0
0x18001e4bf  mov     [rax+40h], edi
0x18001e4c2  movups  xmmword ptr [rax+48h], xmm0
0x18001e4c6  mov     [rax+58h], edi
0x18001e4c9  mov     [rax+60h], rdi
0x18001e4cd  mov     [rax+68h], rdi
0x18001e4d1  jmp     short loc_18001E4D6
0x18001e4d3  mov     rbx, rdi
0x18001e4d6  mov     [rbp+37h+arg_8], rbx
0x18001e4da  test    rbx, rbx
0x18001e4dd  jnz     short loc_18001E519
0x18001e4df  xor     ecx, ecx
0x18001e4e1  call    ??$AutoPtrDeallocate@VAddPackageParameters@@@Common@@YAXPEAVAddPackageParameters@@@Z; Common::AutoPtrDeallocate<AddPackageParameters>(AddPackageParameters *)
0x18001e4e6  nop
0x18001e4e7  cmp     [rbp+37h+var_58], dil
0x18001e4eb  jz      short loc_18001E4FF
0x18001e4ed  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x18001e4f3  mov     rcx, [rbp+3Fh]; this
0x18001e4f7  test    eax, eax
0x18001e4f9  js      loc_18001E701
0x18001e4ff  mov     rcx, qword ptr [rbp+37h+var_50+8]
0x18001e503  test    rcx, rcx
0x18001e506  jz      short loc_18001E50F
0x18001e508  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001e50e  nop
0x18001e50f  mov     eax, 8007000Eh
0x18001e514  jmp     loc_18001E6BC
0x18001e519  mov     rdi, qword ptr [rbp+37h+var_50+8]
0x18001e51d  mov     rax, [rbp+37h+arg_48]
0x18001e524  mov     [rsp+50h], rax
0x18001e529  mov     rax, [rbp+37h+arg_40]
0x18001e530  mov     [rsp+0C0h+var_78], rax
0x18001e535  mov     [rsp+0C0h+var_80], rdi
0x18001e53a  mov     byte ptr [rsp+0C0h+var_88], r14b
0x18001e53f  mov     [rsp+0C0h+var_90], r12b
0x18001e544  mov     dword ptr [rsp+0C0h+var_98], esi
0x18001e548  mov     rax, qword ptr [rbp+37h+arg_20]
0x18001e54c  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x18001e551  mov     r9, r13
0x18001e554  mov     r8, [rbp+37h+arg_10]
0x18001e558  mov     rdx, r15
0x18001e55b  mov     rcx, rbx
0x18001e55e  call    ?Initialize@AddPackageParameters@@QEAAJPEBG0PEAUIUriRuntimeClass@Foundation@Windows@@PEAV?$Vector@PEAVUri@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAVUri@Foundation@Windows@@@Internal@Collections@23@U?$DefaultLifetimeTraits@PEAVUri@Foundation@Windows@@@5623@U?$DefaultVectorOptions@PEAVUri@Foundation@Windows@@@5623@@Internal@Collections@34@W4DeploymentOptionsInternal@6Deployment@Management@4@_N40PEAV?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@6734@2@Z; AddPackageParameters::Initialize(ushort const *,ushort const *,Windows::Foundation::IUriRuntimeClass *,Windows::Foundation::Collections::Internal::Vector<Windows::Foundation::Uri *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Foundation::Uri *>> *,Windows::Management::Deployment::Internal::DeploymentOptionsInternal,bool,bool,ushort const *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> *,Windows::Foundation::Collections::Internal::Vector<Windows::Foundation::Uri *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Foundation::Uri *>> *)
0x18001e563  mov     esi, eax
0x18001e565  mov     rcx, [rbp+3Fh]; this
0x18001e569  xor     r14d, r14d
0x18001e56c  test    eax, eax
0x18001e56e  jns     short loc_18001E5BC
0x18001e570  mov     r9d, eax; char *
0x18001e573  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18001e57a  mov     edx, 36Dh; void *
0x18001e57f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001e584  nop
0x18001e585  mov     rcx, rbx
0x18001e588  call    ??$AutoPtrDeallocate@VAddPackageParameters@@@Common@@YAXPEAVAddPackageParameters@@@Z; Common::AutoPtrDeallocate<AddPackageParameters>(AddPackageParameters *)
0x18001e58d  nop
0x18001e58e  cmp     [rbp+37h+var_58], r14b
0x18001e592  jz      short loc_18001E5A6
0x18001e594  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x18001e59a  mov     rcx, [rbp+3Fh]; this
0x18001e59e  test    eax, eax
0x18001e5a0  js      loc_18001E70F
0x18001e5a6  test    rdi, rdi
0x18001e5a9  jz      short loc_18001E5B5
0x18001e5ab  mov     rcx, rdi
0x18001e5ae  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001e5b4  nop
0x18001e5b5  mov     eax, esi
0x18001e5b7  jmp     loc_18001E6BC
0x18001e5bc  mov     [rbp+37h+arg_8], r14
0x18001e5c0  lea     r8, ?g_provisioningCallbackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x18001e5c7  mov     rdx, rbx; pv
0x18001e5ca  lea     rcx, ?DoAddPackageWork@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18001e5d1  call    cs:__imp_CreateThreadpoolWork
0x18001e5d7  mov     rsi, rax
0x18001e5da  test    rax, rax
0x18001e5dd  jnz     short loc_18001E628
0x18001e5df  call    cs:__imp_GetLastError
0x18001e5e5  mov     ebx, eax
0x18001e5e7  test    eax, eax
0x18001e5e9  jle     short loc_18001E5F4
0x18001e5eb  movzx   ebx, ax
0x18001e5ee  or      ebx, 80070000h
0x18001e5f4  xor     ecx, ecx
0x18001e5f6  call    ??$AutoPtrDeallocate@VAddPackageParameters@@@Common@@YAXPEAVAddPackageParameters@@@Z; Common::AutoPtrDeallocate<AddPackageParameters>(AddPackageParameters *)
0x18001e5fb  nop
0x18001e5fc  cmp     [rbp+37h+var_58], r14b
0x18001e600  jz      short loc_18001E614
0x18001e602  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x18001e608  mov     rcx, [rbp+3Fh]; this
0x18001e60c  test    eax, eax
0x18001e60e  js      loc_18001E71D
0x18001e614  test    rdi, rdi
0x18001e617  jz      short loc_18001E623
0x18001e619  mov     rcx, rdi
0x18001e61c  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001e622  nop
0x18001e623  jmp     loc_18001E48A
0x18001e628  mov     rdx, 0FFFFFFFF80000001h; HKEY
0x18001e62f  mov     rcx, r15; unsigned __int16 *
0x18001e632  call    ?UpdateInstallStatusToInstalling@@YAJPEBGPEAUHKEY__@@@Z; UpdateInstallStatusToInstalling(ushort const *,HKEY__ *)
0x18001e637  mov     ebx, eax
0x18001e639  mov     rcx, [rbp+3Fh]; this
0x18001e63d  test    eax, eax
0x18001e63f  jns     short loc_18001E674
0x18001e641  mov     r9d, eax; char *
0x18001e644  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18001e64b  mov     edx, 382h; void *
0x18001e650  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001e655  nop
0x18001e656  xor     ecx, ecx
0x18001e658  call    ??$AutoPtrDeallocate@VAddPackageParameters@@@Common@@YAXPEAVAddPackageParameters@@@Z; Common::AutoPtrDeallocate<AddPackageParameters>(AddPackageParameters *)
0x18001e65d  nop
0x18001e65e  cmp     [rbp+37h+var_58], r14b
0x18001e662  jz      short loc_18001E6A3
0x18001e664  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x18001e66a  mov     rcx, [rbp+3Fh]; this
0x18001e66e  test    eax, eax
0x18001e670  js      short loc_18001E6E5
0x18001e672  jmp     short loc_18001E6A3
0x18001e674  mov     rcx, rsi; pwk
0x18001e677  call    cs:__imp_SubmitThreadpoolWork
0x18001e67d  mov     rcx, [rbp+37h+arg_0]; this
0x18001e681  call    ?AddRefService@PackageManagerWrapper@@AEAAXXZ; PackageManagerWrapper::AddRefService(void)
0x18001e686  nop
0x18001e687  xor     ecx, ecx
0x18001e689  call    ??$AutoPtrDeallocate@VAddPackageParameters@@@Common@@YAXPEAVAddPackageParameters@@@Z; Common::AutoPtrDeallocate<AddPackageParameters>(AddPackageParameters *)
0x18001e68e  nop
0x18001e68f  cmp     [rbp+37h+var_58], r14b
0x18001e693  jz      short loc_18001E6A3
0x18001e695  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x18001e69b  mov     rcx, [rbp+3Fh]; this
0x18001e69f  test    eax, eax
0x18001e6a1  js      short loc_18001E6D7
0x18001e6a3  test    rdi, rdi
0x18001e6a6  jz      short loc_18001E6B2
0x18001e6a8  mov     rcx, rdi
0x18001e6ab  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001e6b1  nop
0x18001e6b2  jmp     loc_18001E48A
0x18001e6b7  mov     eax, 80070057h
0x18001e6bc  mov     rbx, [rsp+0C0h+arg_18]
0x18001e6c4  add     rsp, 90h
0x18001e6cb  pop     r15
0x18001e6cd  pop     r14
0x18001e6cf  pop     r13
0x18001e6d1  pop     r12
0x18001e6d3  pop     rdi
0x18001e6d4  pop     rsi
0x18001e6d5  pop     rbp
0x18001e6d6  retn
0x18001e6d7  mov     r9d, eax; char *
0x18001e6da  mov     edx, 4Bh ; 'K'; void *
0x18001e6df  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001e6e5  mov     r9d, eax; char *
0x18001e6e8  mov     edx, 4Bh ; 'K'; void *
0x18001e6ed  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001e6f3  mov     r9d, eax; char *
0x18001e6f6  mov     edx, 4Bh ; 'K'; void *
0x18001e6fb  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001e701  mov     r9d, eax; char *
0x18001e704  mov     edx, 4Bh ; 'K'; void *
0x18001e709  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001e70f  mov     r9d, eax; char *
0x18001e712  mov     edx, 4Bh ; 'K'; void *
0x18001e717  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001e71d  mov     r9d, eax; char *
0x18001e720  mov     edx, 4Bh ; 'K'; void *
0x18001e725  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
