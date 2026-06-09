# MsixPackage::Provisioning::Library::MsixAppxDeploymentClient::AppxRemovePackageForAllUsers(ushort const *,int *)

- ea: `0x180045850`
- end: `0x180045967`
- name: `?AppxRemovePackageForAllUsers@MsixAppxDeploymentClient@Library@Provisioning@MsixPackage@@QEAAJPEBGPEAH@Z`
- size: `279`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::MsixAppxDeploymentClient *__hidden this, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004e4b0`

## callees

- `0x18000d3dc`
- `0x18003c350`
- `0x18003d4ec`
- `0x180045850`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800458b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800458b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800458c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800458e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800458c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800458e4`

## string_xrefs

- `0x180045872`: `Failed to load AppxDeploymentClient.DLL.`
- `0x180045881`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x18004591a`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x180045945`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x18004590b`: `Unable to GetProcAddress 'AppxRemovePackageForAllUsers'`
- `0x1800458aa`: `AppxRemovePackageForAllUsers`

## pseudocode

```c
__int64 __fastcall MsixPackage::Provisioning::Library::MsixAppxDeploymentClient::AppxRemovePackageForAllUsers(
        MsixPackage::Provisioning::Library::MsixAppxDeploymentClient *this,
        const unsigned __int16 *a2,
        int *a3,
        const char *a4)
{
  int Dynamic; // edi
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  bool v11; // sf
  signed int v12; // eax
  unsigned int v13; // ebx
  int v14; // eax
  int v15; // [rsp+20h] [rbp-38h]
  const char *v16; // [rsp+28h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  Dynamic = MsixPackage::Provisioning::Library::MsixProvisioningModule<MsixPackage::Provisioning::Library::MsixAppxDeploymentClient>::LoadDynamic(
              this,
              (__int64)a2,
              (__int64)a3,
              a4);
  if ( Dynamic < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x1E4,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\MsixModules.h",
      (const char *)(unsigned int)Dynamic,
      (int)"Failed to load AppxDeploymentClient.DLL.",
      v16);
    return (unsigned int)Dynamic;
  }
  ProcAddress = (FARPROC)*((_QWORD *)this + 15);
  if ( !ProcAddress )
  {
    ProcAddress = GetProcAddress(*((HMODULE *)this + 1), "AppxRemovePackageForAllUsers");
    *((_QWORD *)this + 15) = ProcAddress;
    if ( !ProcAddress )
    {
      LastError = GetLastError();
      v11 = LastError < 0;
      if ( LastError > 0 )
        v11 = 1;
      if ( v11 )
      {
        v12 = GetLastError();
        v13 = v12;
        if ( v12 > 0 )
          v13 = (unsigned __int16)v12 | 0x80070000;
        if ( (v13 & 0x80000000) == 0 )
          return v13;
      }
      else
      {
        v13 = -2147467259;
      }
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x1EC,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\MsixModules.h",
        (const char *)v13,
        (int)"Unable to GetProcAddress 'AppxRemovePackageForAllUsers'",
        v16);
      return v13;
    }
  }
  v14 = ((__int64 (__fastcall *)(const unsigned __int16 *, int *))ProcAddress)(a2, a3);
  v13 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F0,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\MsixModules.h",
      (const char *)(unsigned int)v14,
      v15);
    return v13;
  }
  return 0;
}

```

## disassembly

```asm
0x180045850  push    rbx
0x180045852  push    rbp
0x180045853  push    rsi
0x180045854  push    rdi
0x180045855  sub     rsp, 38h
0x180045859  mov     rsi, r8
0x18004585c  mov     rbp, rdx
0x18004585f  mov     rbx, rcx
0x180045862  call    ?LoadDynamic@?$MsixProvisioningModule@VMsixAppxDeploymentClient@Library@Provisioning@MsixPackage@@@Library@Provisioning@MsixPackage@@IEAAJXZ; MsixPackage::Provisioning::Library::MsixProvisioningModule<MsixPackage::Provisioning::Library::MsixAppxDeploymentClient>::LoadDynamic(void)
0x180045867  mov     edi, eax
0x180045869  test    eax, eax
0x18004586b  jns     short loc_180045899
0x18004586d  mov     rcx, [rsp+58h]; this
0x180045872  lea     rax, aFailedToLoadAp; "Failed to load AppxDeploymentClient.DLL"...
0x180045879  mov     r9d, edi; char *
0x18004587c  mov     qword ptr [rsp+58h+var_38], rax; int
0x180045881  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180045888  mov     edx, 1E4h; void *
0x18004588d  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180045892  mov     eax, edi
0x180045894  jmp     loc_18004595D
0x180045899  mov     rax, [rbx+78h]
0x18004589d  test    rax, rax
0x1800458a0  jnz     loc_18004592F
0x1800458a6  mov     rcx, [rbx+8]; hModule
0x1800458aa  lea     rdx, aAppxremovepack; "AppxRemovePackageForAllUsers"
0x1800458b1  call    cs:__imp_GetProcAddress
0x1800458b8  nop     dword ptr [rax+rax+00h]
0x1800458bd  mov     [rbx+78h], rax
0x1800458c1  test    rax, rax
0x1800458c4  jnz     short loc_18004592F
0x1800458c6  call    cs:__imp_GetLastError
0x1800458cd  nop     dword ptr [rax+rax+00h]
0x1800458d2  mov     edi, 80070000h
0x1800458d7  test    eax, eax
0x1800458d9  jle     short loc_1800458E2
0x1800458db  movzx   eax, ax
0x1800458de  or      eax, edi
0x1800458e0  test    eax, eax
0x1800458e2  jns     short loc_180045901
0x1800458e4  call    cs:__imp_GetLastError
0x1800458eb  nop     dword ptr [rax+rax+00h]
0x1800458f0  mov     ebx, eax
0x1800458f2  test    eax, eax
0x1800458f4  jle     short loc_1800458FB
0x1800458f6  movzx   ebx, ax
0x1800458f9  or      ebx, edi
0x1800458fb  test    ebx, ebx
0x1800458fd  jns     short loc_18004592B
0x1800458ff  jmp     short loc_180045906
0x180045901  mov     ebx, 80004005h
0x180045906  mov     rcx, [rsp+58h]; this
0x18004590b  lea     rax, aUnableToGetpro_5; "Unable to GetProcAddress 'AppxRemovePac"...
0x180045912  mov     r9d, ebx; char *
0x180045915  mov     qword ptr [rsp+58h+var_38], rax; int
0x18004591a  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180045921  mov     edx, 1ECh; void *
0x180045926  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004592b  mov     eax, ebx
0x18004592d  jmp     short loc_18004595D
0x18004592f  mov     rdx, rsi
0x180045932  mov     rcx, rbp
0x180045935  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004593a  mov     ebx, eax
0x18004593c  test    eax, eax
0x18004593e  jns     short loc_18004595B
0x180045940  mov     rcx, [rsp+58h]; this
0x180045945  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004594c  mov     r9d, eax; char *
0x18004594f  mov     edx, 1F0h; void *
0x180045954  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045959  jmp     short loc_18004592B
0x18004595b  xor     eax, eax
0x18004595d  add     rsp, 38h
0x180045961  pop     rdi
0x180045962  pop     rsi
0x180045963  pop     rbp
0x180045964  pop     rbx
0x180045965  retn
```
