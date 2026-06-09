# MsixPackage::Provisioning::Library::MsixPackageAdapter::CreateForExistingDependencyPackageOnline(ushort const *,MsixPackage::Provisioning::Library::MsixProvisioningContext *,bool &,MsixPackage::Provisioning::Library::MsixPackageAdapter * *)

- ea: `0x180042188`
- end: `0x18004243e`
- name: `?CreateForExistingDependencyPackageOnline@MsixPackageAdapter@Library@Provisioning@MsixPackage@@SAJPEBGPEAVMsixProvisioningContext@234@AEA_NPEAPEAV1234@@Z`
- size: `694`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct MsixPackage::Provisioning::Library::MsixProvisioningContext *, bool *, struct MsixPackage::Provisioning::Library::MsixPackageAdapter **)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, installer_update`

## callers

- `0x180041e2c`

## callees

- `0x18000cfe8`
- `0x18001bf0c`
- `0x18001c5b8`
- `0x1800366d4`
- `0x180039e9c`
- `0x18003ae3c`
- `0x18003de34`
- `0x180040a48`
- `0x180042188`
- `0x1800456e4`
- `0x180066df0`
- `0x18006a010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180042255`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800422cc`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004233e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180042407`
- `msvcrt!??3@YAXPEAX@Z` at `0x180042255`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800422cc`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004233e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180042407`

## string_xrefs

- `0x1800421e5`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180042236`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x1800422ad`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180042308`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x1800422f9`: `Failed to create package adapter.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
  unsigned __int64 v20; // rdi
  unsigned __int64 v21; // r8
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
        (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)IsInstalled);
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
                  (__int64)a2,
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
            else
            {
              v21 = 0;
            }
            std::wstring::assign((_QWORD *)(v19 + 48), (char *)Src, v21);
            std::wstring::assign((_QWORD *)(v19 + 112), (char *)L"%SYSTEMDRIVE%\\Program Files\\WindowsApps", 0x27u);
            std::wstring::append((_QWORD *)(v19 + 112), (char *)L"\\", pszSrc[0] != 0);
            if ( Src[0] )
            {
              do
                ++v20;
              while ( Src[v20] );
            }
            else
            {
              v20 = 0;
            }
            std::wstring::append((_QWORD *)(v19 + 112), (char *)Src, v20);
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
0x180042188  push    rbx
0x18004218a  push    rsi
0x18004218b  push    rdi
0x18004218c  push    r12
0x18004218e  push    r14
0x180042190  push    r15
0x180042192  sub     rsp, 188h
0x180042199  mov     rax, cs:__security_cookie
0x1800421a0  xor     rax, rsp
0x1800421a3  mov     [rsp+1B8h+var_48], rax
0x1800421ab  mov     r15, r9
0x1800421ae  mov     rbx, r8
0x1800421b1  mov     rsi, rdx
0x1800421b4  mov     rdi, rcx
0x1800421b7  xor     r12d, r12d
0x1800421ba  mov     [rsp+1B8h+var_180], r12d
0x1800421bf  lea     r14, [rdx+140h]
0x1800421c6  lea     r8, [rsp+1B8h+var_180]; int *
0x1800421cb  mov     rdx, rcx; unsigned __int16 *
0x1800421ce  mov     rcx, r14; this
0x1800421d1  call    ?GetApplicabilityIsInstalled@MsixAppxDeploymentClient@Library@Provisioning@MsixPackage@@QEAAJPEBGPEAH@Z; MsixPackage::Provisioning::Library::MsixAppxDeploymentClient::GetApplicabilityIsInstalled(ushort const *,int *)
0x1800421d6  mov     rcx, [rsp+1B8h]; this
0x1800421de  test    eax, eax
0x1800421e0  jns     short loc_1800421F6
0x1800421e2  mov     r9d, eax; char *
0x1800421e5  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800421ec  lea     edx, [r12+76h]; void *
0x1800421f1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800421f6  cmp     [rsp+1B8h+var_180], r12d
0x1800421fb  jz      loc_180042411
0x180042201  mov     byte ptr [rbx], 1
0x180042204  mov     [rsp+1B8h+var_158], 7
0x18004220d  mov     [rsp+1B8h+var_160], r12
0x180042212  mov     word ptr [rsp+1B8h+var_170], r12w
0x180042218  lea     r8, [rsp+1B8h+var_170]
0x18004221d  mov     rdx, rdi
0x180042220  call    ?GetPackageFamilyFromFullName@MsixProvisioningContext@Library@Provisioning@MsixPackage@@QEAAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MsixPackage::Provisioning::Library::MsixProvisioningContext::GetPackageFamilyFromFullName(ushort const *,std::wstring &)
0x180042225  mov     ebx, eax
0x180042227  test    eax, eax
0x180042229  jns     short loc_180042262
0x18004222b  mov     rcx, [rsp+1B8h]; this
0x180042233  mov     r9d, eax; char *
0x180042236  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004223d  mov     edx, 7Fh; void *
0x180042242  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042247  nop
0x180042248  cmp     [rsp+1B8h+var_158], 8
0x18004224e  jb      short loc_18004225B
0x180042250  mov     rcx, [rsp+1B8h+var_170]
0x180042255  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004225b  mov     eax, ebx
0x18004225d  jmp     loc_18004241C
0x180042262  mov     [rsp+1B8h+var_188], 80h
0x18004226a  mov     [rsp+1B8h+var_178], r12d
0x18004226f  lea     rdx, [rsp+1B8h+var_170]
0x180042274  cmp     [rsp+1B8h+var_158], 8
0x18004227a  cmovnb  rdx, [rsp+1B8h+var_170]; unsigned __int16 *
0x180042280  lea     rax, [rsp+1B8h+var_178]
0x180042285  mov     [rsp+1B8h+var_198], rax; int
0x18004228a  lea     r9, [rsp+1B8h+var_188]; unsigned int *
0x18004228f  lea     r8, [rsp+1B8h+Src]; unsigned __int16 *
0x180042294  mov     rcx, r14; this
0x180042297  call    ?AppxGetStagedPackageFullNameFromFamilyName@MsixAppxDeploymentClient@Library@Provisioning@MsixPackage@@QEAAJPEBGPEAGPEAIPEAH@Z; MsixPackage::Provisioning::Library::MsixAppxDeploymentClient::AppxGetStagedPackageFullNameFromFamilyName(ushort const *,ushort *,uint *,int *)
0x18004229c  mov     ebx, eax
0x18004229e  test    eax, eax
0x1800422a0  jns     short loc_1800422D9
0x1800422a2  mov     rcx, [rsp+1B8h]; this
0x1800422aa  mov     r9d, eax; char *
0x1800422ad  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800422b4  mov     edx, 88h; void *
0x1800422b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800422be  nop
0x1800422bf  cmp     [rsp+1B8h+var_158], 8
0x1800422c5  jb      short loc_1800422D2
0x1800422c7  mov     rcx, [rsp+1B8h+var_170]
0x1800422cc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800422d2  mov     eax, ebx
0x1800422d4  jmp     loc_18004241C
0x1800422d9  mov     qword ptr [rsp+1B8h+var_180], r12
0x1800422de  lea     rdx, [rsp+1B8h+var_180]
0x1800422e3  mov     rcx, rsi
0x1800422e6  call    ??$Make@VMsixPackageAdapter@Library@Provisioning@MsixPackage@@@MsixAdapterBase@Library@Provisioning@MsixPackage@@SAJPEAVMsixProvisioningContext@123@PEAPEAVMsixPackageAdapter@123@@Z; MsixPackage::Provisioning::Library::MsixAdapterBase::Make<MsixPackage::Provisioning::Library::MsixPackageAdapter>(MsixPackage::Provisioning::Library::MsixProvisioningContext *,MsixPackage::Provisioning::Library::MsixPackageAdapter * *)
0x1800422eb  mov     ebx, eax
0x1800422ed  test    eax, eax
0x1800422ef  jns     short loc_18004234B
0x1800422f1  mov     rcx, [rsp+1B8h]; this
0x1800422f9  lea     rax, aFailedToCreate_22; "Failed to create package adapter."
0x180042300  mov     [rsp+1B8h+var_198], rax; int
0x180042305  mov     r9d, ebx; char *
0x180042308  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004230f  mov     edx, 8Dh; void *
0x180042314  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180042319  nop
0x18004231a  mov     rcx, qword ptr [rsp+1B8h+var_180]
0x18004231f  test    rcx, rcx
0x180042322  jz      short loc_180042331
0x180042324  mov     rax, [rcx]
0x180042327  mov     rax, [rax+10h]
0x18004232b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042330  nop
0x180042331  cmp     [rsp+1B8h+var_158], 8
0x180042337  jb      short loc_180042344
0x180042339  mov     rcx, [rsp+1B8h+var_170]
0x18004233e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180042344  mov     eax, ebx
0x180042346  jmp     loc_18004241C
0x18004234b  mov     eax, 3
0x180042350  mov     rbx, qword ptr [rsp+1B8h+var_180]
0x180042355  mov     [rbx+18h], eax
0x180042358  mov     qword ptr [rbx+1Ch], 1
0x180042360  mov     [rbx+24h], eax
0x180042363  lea     rcx, [rbx+30h]; void *
0x180042367  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004236b  cmp     [rsp+1B8h+Src], r12w
0x180042371  jnz     short loc_180042378
0x180042373  mov     r8, r12
0x180042376  jmp     short loc_18004238A
0x180042378  lea     rax, [rsp+1B8h+Src]
0x18004237d  mov     r8, rdi
0x180042380  inc     r8
0x180042383  cmp     [rax+r8*2], r12w
0x180042388  jnz     short loc_180042380
0x18004238a  lea     rdx, [rsp+1B8h+Src]; Src
0x18004238f  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180042394  lea     rsi, [rbx+70h]
0x180042398  mov     r8d, 27h ; '''
0x18004239e  lea     rdx, aSystemdrivePro; "%SYSTEMDRIVE%\\Program Files\\WindowsAp"...
0x1800423a5  mov     rcx, rsi; void *
0x1800423a8  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800423ad  mov     r8, r12
0x1800423b0  cmp     word ptr cs:pszSrc, r12w; "\\"
0x1800423b8  setnz   r8b
0x1800423bc  lea     rdx, pszSrc; "\\"
0x1800423c3  mov     rcx, rsi; Src
0x1800423c6  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x1800423cb  cmp     [rsp+1B8h+Src], r12w
0x1800423d1  jnz     short loc_1800423D8
0x1800423d3  mov     rdi, r12
0x1800423d6  jmp     short loc_1800423E7
0x1800423d8  lea     rax, [rsp+1B8h+Src]
0x1800423dd  inc     rdi
0x1800423e0  cmp     [rax+rdi*2], r12w
0x1800423e5  jnz     short loc_1800423DD
0x1800423e7  mov     r8, rdi
0x1800423ea  lea     rdx, [rsp+1B8h+Src]; void *
0x1800423ef  mov     rcx, rsi; Src
0x1800423f2  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x1800423f7  mov     [r15], rbx
0x1800423fa  cmp     [rsp+1B8h+var_158], 8
0x180042400  jb      short loc_18004240D
0x180042402  mov     rcx, [rsp+1B8h+var_170]
0x180042407  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004240d  xor     eax, eax
0x18004240f  jmp     short loc_18004241C
0x180042411  mov     [rbx], r12b
0x180042414  xor     eax, eax
0x180042416  jmp     short loc_18004241C
0x180042418  mov     eax, [rsp+1B8h+var_188]
0x18004241c  mov     rcx, [rsp+1B8h+var_48]
0x180042424  xor     rcx, rsp; StackCookie
0x180042427  call    __security_check_cookie
0x18004242c  add     rsp, 188h
0x180042433  pop     r15
0x180042435  pop     r14
0x180042437  pop     r12
0x180042439  pop     rdi
0x18004243a  pop     rsi
0x18004243b  pop     rbx
0x18004243c  retn
```
