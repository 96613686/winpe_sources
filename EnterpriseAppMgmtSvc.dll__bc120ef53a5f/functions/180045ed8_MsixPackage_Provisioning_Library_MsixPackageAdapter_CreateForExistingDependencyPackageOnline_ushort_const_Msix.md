# MsixPackage::Provisioning::Library::MsixPackageAdapter::CreateForExistingDependencyPackageOnline(ushort const *,MsixPackage::Provisioning::Library::MsixProvisioningContext *,bool &,MsixPackage::Provisioning::Library::MsixPackageAdapter * *)

- ea: `0x180045ed8`
- end: `0x1800461a6`
- name: `?CreateForExistingDependencyPackageOnline@MsixPackageAdapter@Library@Provisioning@MsixPackage@@SAJPEBGPEAVMsixProvisioningContext@234@AEA_NPEAPEAV1234@@Z`
- size: `718`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct MsixPackage::Provisioning::Library::MsixProvisioningContext *, bool *, struct MsixPackage::Provisioning::Library::MsixPackageAdapter **)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, installer_update`

## callers

- `0x180045b3c`

## callees

- `0x18000d3dc`
- `0x18001d160`
- `0x18001d65c`
- `0x180039a48`
- `0x18003d4ec`
- `0x18003e50c`
- `0x180041770`
- `0x180044670`
- `0x180045ed8`
- `0x180049664`
- `0x18006c910`
- `0x180070010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180045fa5`
- `msvcrt!??3@YAXPEAX@Z` at `0x180046022`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004609a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180046169`
- `msvcrt!??3@YAXPEAX@Z` at `0x180045fa5`
- `msvcrt!??3@YAXPEAX@Z` at `0x180046022`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004609a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180046169`

## string_xrefs

- `0x180045f35`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180045f86`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180046003`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180046064`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180046055`: `Failed to create package adapter.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall MsixPackage::Provisioning::Library::MsixPackageAdapter::CreateForExistingDependencyPackageOnline(
        const unsigned __int16 *a1,
        struct MsixPackage::Provisioning::Library::MsixProvisioningContext *a2,
        bool *a3,
        struct MsixPackage::Provisioning::Library::MsixPackageAdapter **a4)
{
  MsixPackage::Provisioning::Library::MsixAppxDeploymentClient *v8; // r14
  int IsInstalled; // eax
  const char *v10; // r9
  wil::details::in1diag3 *v11; // rcx
  int PackageFamilyFromFullName; // eax
  unsigned int v13; // ebx
  __int64 result; // rax
  const unsigned __int16 *v15; // rdx
  int StagedPackageFullNameFromFamilyName; // eax
  unsigned int v17; // ebx
  int v18; // ebx
  __int64 v19; // rbx
  __int64 v20; // rdi
  __int64 v21; // r8
  int v22; // [rsp+20h] [rbp-198h]
  int v23; // [rsp+20h] [rbp-198h]
  const char *v24; // [rsp+28h] [rbp-190h]
  unsigned int v25; // [rsp+30h] [rbp-188h] BYREF
  int v26[2]; // [rsp+38h] [rbp-180h] BYREF
  int v27; // [rsp+40h] [rbp-178h] BYREF
  unsigned __int16 *v28[3]; // [rsp+48h] [rbp-170h] BYREF
  unsigned __int64 v29; // [rsp+60h] [rbp-158h]
  unsigned __int16 Src[128]; // [rsp+70h] [rbp-148h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]

  try
  {
    v26[0] = 0;
    v8 = (struct MsixPackage::Provisioning::Library::MsixProvisioningContext *)((char *)a2 + 320);
    IsInstalled = MsixPackage::Provisioning::Library::MsixAppxDeploymentClient::GetApplicabilityIsInstalled(
                    (struct MsixPackage::Provisioning::Library::MsixProvisioningContext *)((char *)a2 + 320),
                    a1,
                    v26);
    v11 = retaddr;
    if ( IsInstalled < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x76,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)IsInstalled,
        v22);
    if ( v26[0] )
    {
      *a3 = 1;
      v29 = 7;
      v28[2] = 0;
      LOWORD(v28[0]) = 0;
      PackageFamilyFromFullName = MsixPackage::Provisioning::Library::MsixProvisioningContext::GetPackageFamilyFromFullName(
                                    v11,
                                    a1,
                                    v28);
      v13 = PackageFamilyFromFullName;
      if ( PackageFamilyFromFullName >= 0 )
      {
        v25 = 128;
        v27 = 0;
        v15 = (const unsigned __int16 *)v28;
        if ( v29 >= 8 )
          v15 = v28[0];
        StagedPackageFullNameFromFamilyName = MsixPackage::Provisioning::Library::MsixAppxDeploymentClient::AppxGetStagedPackageFullNameFromFamilyName(
                                                v8,
                                                v15,
                                                Src,
                                                &v25,
                                                &v27);
        v17 = StagedPackageFullNameFromFamilyName;
        if ( StagedPackageFullNameFromFamilyName >= 0 )
        {
          *(_QWORD *)v26 = 0;
          v18 = MsixPackage::Provisioning::Library::MsixAdapterBase::Make<MsixPackage::Provisioning::Library::MsixPackageAdapter>(
                  a2,
                  v26);
          if ( v18 >= 0 )
          {
            v19 = *(_QWORD *)v26;
            *(_DWORD *)(*(_QWORD *)v26 + 24LL) = 3;
            *(_QWORD *)(v19 + 28) = 1;
            *(_DWORD *)(v19 + 36) = 3;
            v20 = -1;
            if ( Src[0] )
            {
              v21 = -1;
              do
                ++v21;
              while ( Src[v21] );
            }
            std::wstring::assign((void *)(v19 + 48), Src);
            std::wstring::assign((void *)(v19 + 112), L"%SYSTEMDRIVE%\\Program Files\\WindowsApps");
            std::wstring::append((void *)(v19 + 112), (void *)L"\\");
            if ( Src[0] )
            {
              do
                ++v20;
              while ( Src[v20] );
            }
            std::wstring::append((void *)(v19 + 112), Src);
            *a4 = (struct MsixPackage::Provisioning::Library::MsixPackageAdapter *)v19;
            if ( v29 >= 8 )
              operator delete(v28[0]);
            result = 0;
          }
          else
          {
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              (void *)0x8D,
              (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
              (const char *)(unsigned int)v18,
              (int)"Failed to create package adapter.",
              v24);
            if ( *(_QWORD *)v26 )
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v26 + 16LL))(*(_QWORD *)v26);
            if ( v29 >= 8 )
              operator delete(v28[0]);
            result = (unsigned int)v18;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x88,
            (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
            (const char *)(unsigned int)StagedPackageFullNameFromFamilyName,
            v23);
          if ( v29 >= 8 )
            operator delete(v28[0]);
          result = v17;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7F,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
          (const char *)(unsigned int)PackageFamilyFromFullName,
          v22);
        if ( v29 >= 8 )
          operator delete(v28[0]);
        result = v13;
      }
    }
    else
    {
      *a3 = 0;
      result = 0;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x9D,
                           (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x180045ed8  push    rbx
0x180045eda  push    rsi
0x180045edb  push    rdi
0x180045edc  push    r12
0x180045ede  push    r14
0x180045ee0  push    r15
0x180045ee2  sub     rsp, 188h
0x180045ee9  mov     rax, cs:__security_cookie
0x180045ef0  xor     rax, rsp
0x180045ef3  mov     [rsp+1B8h+var_48], rax
0x180045efb  mov     r15, r9
0x180045efe  mov     rbx, r8
0x180045f01  mov     rsi, rdx
0x180045f04  mov     rdi, rcx
0x180045f07  xor     r12d, r12d
0x180045f0a  mov     [rsp+1B8h+var_180], r12d
0x180045f0f  lea     r14, [rdx+140h]
0x180045f16  lea     r8, [rsp+1B8h+var_180]; int *
0x180045f1b  mov     rdx, rcx; unsigned __int16 *
0x180045f1e  mov     rcx, r14; this
0x180045f21  call    ?GetApplicabilityIsInstalled@MsixAppxDeploymentClient@Library@Provisioning@MsixPackage@@QEAAJPEBGPEAH@Z; MsixPackage::Provisioning::Library::MsixAppxDeploymentClient::GetApplicabilityIsInstalled(ushort const *,int *)
0x180045f26  mov     rcx, [rsp+1B8h]; this
0x180045f2e  test    eax, eax
0x180045f30  jns     short loc_180045F46
0x180045f32  mov     r9d, eax; char *
0x180045f35  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180045f3c  lea     edx, [r12+76h]; void *
0x180045f41  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180045f46  cmp     [rsp+1B8h+var_180], r12d
0x180045f4b  jz      loc_180046179
0x180045f51  mov     byte ptr [rbx], 1
0x180045f54  mov     [rsp+1B8h+var_158], 7
0x180045f5d  mov     [rsp+1B8h+var_160], r12
0x180045f62  mov     word ptr [rsp+1B8h+var_170], r12w
0x180045f68  lea     r8, [rsp+1B8h+var_170]
0x180045f6d  mov     rdx, rdi
0x180045f70  call    ?GetPackageFamilyFromFullName@MsixProvisioningContext@Library@Provisioning@MsixPackage@@QEAAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MsixPackage::Provisioning::Library::MsixProvisioningContext::GetPackageFamilyFromFullName(ushort const *,std::wstring &)
0x180045f75  mov     ebx, eax
0x180045f77  test    eax, eax
0x180045f79  jns     short loc_180045FB8
0x180045f7b  mov     rcx, [rsp+1B8h]; this
0x180045f83  mov     r9d, eax; char *
0x180045f86  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180045f8d  mov     edx, 7Fh; void *
0x180045f92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045f97  nop
0x180045f98  cmp     [rsp+1B8h+var_158], 8
0x180045f9e  jb      short loc_180045FB1
0x180045fa0  mov     rcx, [rsp+1B8h+var_170]
0x180045fa5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180045fac  nop     dword ptr [rax+rax+00h]
0x180045fb1  mov     eax, ebx
0x180045fb3  jmp     loc_180046184
0x180045fb8  mov     [rsp+1B8h+var_188], 80h
0x180045fc0  mov     [rsp+1B8h+var_178], r12d
0x180045fc5  lea     rdx, [rsp+1B8h+var_170]
0x180045fca  cmp     [rsp+1B8h+var_158], 8
0x180045fd0  cmovnb  rdx, [rsp+1B8h+var_170]; unsigned __int16 *
0x180045fd6  lea     rax, [rsp+1B8h+var_178]
0x180045fdb  mov     [rsp+1B8h+var_198], rax; int
0x180045fe0  lea     r9, [rsp+1B8h+var_188]; unsigned int *
0x180045fe5  lea     r8, [rsp+1B8h+Src]; unsigned __int16 *
0x180045fea  mov     rcx, r14; this
0x180045fed  call    ?AppxGetStagedPackageFullNameFromFamilyName@MsixAppxDeploymentClient@Library@Provisioning@MsixPackage@@QEAAJPEBGPEAGPEAIPEAH@Z; MsixPackage::Provisioning::Library::MsixAppxDeploymentClient::AppxGetStagedPackageFullNameFromFamilyName(ushort const *,ushort *,uint *,int *)
0x180045ff2  mov     ebx, eax
0x180045ff4  test    eax, eax
0x180045ff6  jns     short loc_180046035
0x180045ff8  mov     rcx, [rsp+1B8h]; this
0x180046000  mov     r9d, eax; char *
0x180046003  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004600a  mov     edx, 88h; void *
0x18004600f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046014  nop
0x180046015  cmp     [rsp+1B8h+var_158], 8
0x18004601b  jb      short loc_18004602E
0x18004601d  mov     rcx, [rsp+1B8h+var_170]
0x180046022  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180046029  nop     dword ptr [rax+rax+00h]
0x18004602e  mov     eax, ebx
0x180046030  jmp     loc_180046184
0x180046035  mov     qword ptr [rsp+1B8h+var_180], r12
0x18004603a  lea     rdx, [rsp+1B8h+var_180]
0x18004603f  mov     rcx, rsi
0x180046042  call    ??$Make@VMsixPackageAdapter@Library@Provisioning@MsixPackage@@@MsixAdapterBase@Library@Provisioning@MsixPackage@@SAJPEAVMsixProvisioningContext@123@PEAPEAVMsixPackageAdapter@123@@Z; MsixPackage::Provisioning::Library::MsixAdapterBase::Make<MsixPackage::Provisioning::Library::MsixPackageAdapter>(MsixPackage::Provisioning::Library::MsixProvisioningContext *,MsixPackage::Provisioning::Library::MsixPackageAdapter * *)
0x180046047  mov     ebx, eax
0x180046049  test    eax, eax
0x18004604b  jns     short loc_1800460AD
0x18004604d  mov     rcx, [rsp+1B8h]; this
0x180046055  lea     rax, aFailedToCreate_22; "Failed to create package adapter."
0x18004605c  mov     [rsp+1B8h+var_198], rax; int
0x180046061  mov     r9d, ebx; char *
0x180046064  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004606b  mov     edx, 8Dh; void *
0x180046070  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180046075  nop
0x180046076  mov     rcx, qword ptr [rsp+1B8h+var_180]
0x18004607b  test    rcx, rcx
0x18004607e  jz      short loc_18004608D
0x180046080  mov     rax, [rcx]
0x180046083  mov     rax, [rax+10h]
0x180046087  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004608c  nop
0x18004608d  cmp     [rsp+1B8h+var_158], 8
0x180046093  jb      short loc_1800460A6
0x180046095  mov     rcx, [rsp+1B8h+var_170]
0x18004609a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800460a1  nop     dword ptr [rax+rax+00h]
0x1800460a6  mov     eax, ebx
0x1800460a8  jmp     loc_180046184
0x1800460ad  mov     eax, 3
0x1800460b2  mov     rbx, qword ptr [rsp+1B8h+var_180]
0x1800460b7  mov     [rbx+18h], eax
0x1800460ba  mov     qword ptr [rbx+1Ch], 1
0x1800460c2  mov     [rbx+24h], eax
0x1800460c5  lea     rcx, [rbx+30h]; void *
0x1800460c9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800460cd  cmp     [rsp+1B8h+Src], r12w
0x1800460d3  jnz     short loc_1800460DA
0x1800460d5  mov     r8, r12
0x1800460d8  jmp     short loc_1800460EC
0x1800460da  lea     rax, [rsp+1B8h+Src]
0x1800460df  mov     r8, rdi
0x1800460e2  inc     r8
0x1800460e5  cmp     [rax+r8*2], r12w
0x1800460ea  jnz     short loc_1800460E2
0x1800460ec  lea     rdx, [rsp+1B8h+Src]; Src
0x1800460f1  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800460f6  lea     rsi, [rbx+70h]
0x1800460fa  mov     r8d, 27h ; '''
0x180046100  lea     rdx, aSystemdrivePro; "%SYSTEMDRIVE%\\Program Files\\WindowsAp"...
0x180046107  mov     rcx, rsi; void *
0x18004610a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18004610f  mov     r8, r12
0x180046112  cmp     word ptr cs:pszSrc, r12w; "\\"
0x18004611a  setnz   r8b
0x18004611e  lea     rdx, pszSrc; "\\"
0x180046125  mov     rcx, rsi; Src
0x180046128  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18004612d  cmp     [rsp+1B8h+Src], r12w
0x180046133  jnz     short loc_18004613A
0x180046135  mov     rdi, r12
0x180046138  jmp     short loc_180046149
0x18004613a  lea     rax, [rsp+1B8h+Src]
0x18004613f  inc     rdi
0x180046142  cmp     [rax+rdi*2], r12w
0x180046147  jnz     short loc_18004613F
0x180046149  mov     r8, rdi
0x18004614c  lea     rdx, [rsp+1B8h+Src]; void *
0x180046151  mov     rcx, rsi; Src
0x180046154  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180046159  mov     [r15], rbx
0x18004615c  cmp     [rsp+1B8h+var_158], 8
0x180046162  jb      short loc_180046175
0x180046164  mov     rcx, [rsp+1B8h+var_170]
0x180046169  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180046170  nop     dword ptr [rax+rax+00h]
0x180046175  xor     eax, eax
0x180046177  jmp     short loc_180046184
0x180046179  mov     [rbx], r12b
0x18004617c  xor     eax, eax
0x18004617e  jmp     short loc_180046184
0x180046180  mov     eax, [rsp+1B8h+var_188]
0x180046184  mov     rcx, [rsp+1B8h+var_48]
0x18004618c  xor     rcx, rsp; StackCookie
0x18004618f  call    __security_check_cookie
0x180046194  add     rsp, 188h
0x18004619b  pop     r15
0x18004619d  pop     r14
0x18004619f  pop     r12
0x1800461a1  pop     rdi
0x1800461a2  pop     rsi
0x1800461a3  pop     rbx
0x1800461a4  retn
```
