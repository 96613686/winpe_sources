# MsixPackage::Provisioning::Library::MsixAppxDeploymentClient::AppxRemovePackageForAllUsers(ushort const *,int *)

- ea: `0x180041b58`
- end: `0x180041c58`
- name: `?AppxRemovePackageForAllUsers@MsixAppxDeploymentClient@Library@Provisioning@MsixPackage@@QEAAJPEBGPEAH@Z`
- size: `256`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::MsixAppxDeploymentClient *__hidden this, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004a334`

## callees

- `0x18000cfe8`
- `0x180038de4`
- `0x180039e9c`
- `0x180041b58`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180041bb5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180041bb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041bc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041bdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041bc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041bdc`

## string_xrefs

- `0x180041b7a`: `Failed to load AppxDeploymentClient.DLL.`
- `0x180041b89`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x180041c0c`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x180041c37`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x180041bae`: `AppxRemovePackageForAllUsers`
- `0x180041bfd`: `Unable to GetProcAddress 'AppxRemovePackageForAllUsers'`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall MsixPackage::Provisioning::Library::MsixAppxDeploymentClient::AppxRemovePackageForAllUsers(
        MsixPackage::Provisioning::Library::MsixAppxDeploymentClient *this,
        const unsigned __int16 *a2,
        int *a3)
{
  int Dynamic; // edi
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  bool v10; // sf
  signed int v11; // eax
  unsigned int v12; // ebx
  int v13; // eax
  int v14; // [rsp+20h] [rbp-38h]
  const char *v15; // [rsp+28h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  Dynamic = MsixPackage::Provisioning::Library::MsixProvisioningModule<MsixPackage::Provisioning::Library::MsixAppxDeploymentClient>::LoadDynamic();
  if ( Dynamic < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x1E4,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\MsixModules.h",
      (const char *)(unsigned int)Dynamic,
      (int)"Failed to load AppxDeploymentClient.DLL.",
      v15);
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
      v10 = LastError < 0;
      if ( LastError > 0 )
        v10 = 1;
      if ( v10 )
      {
        v11 = GetLastError();
        v12 = v11;
        if ( v11 > 0 )
          v12 = (unsigned __int16)v11 | 0x80070000;
        if ( (v12 & 0x80000000) == 0 )
          return v12;
      }
      else
      {
        v12 = -2147467259;
      }
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x1EC,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\MsixModules.h",
        (const char *)v12,
        (int)"Unable to GetProcAddress 'AppxRemovePackageForAllUsers'",
        v15);
      return v12;
    }
  }
  v13 = ((__int64 (__fastcall *)(const unsigned __int16 *, int *))ProcAddress)(a2, a3);
  v12 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F0,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\MsixModules.h",
      (const char *)(unsigned int)v13,
      v14);
    return v12;
  }
  return 0;
}

```

## disassembly

```asm
0x180041b58  push    rbx
0x180041b5a  push    rbp
0x180041b5b  push    rsi
0x180041b5c  push    rdi
0x180041b5d  sub     rsp, 38h
0x180041b61  mov     rsi, r8
0x180041b64  mov     rbp, rdx
0x180041b67  mov     rbx, rcx
0x180041b6a  call    ?LoadDynamic@?$MsixProvisioningModule@VMsixAppxDeploymentClient@Library@Provisioning@MsixPackage@@@Library@Provisioning@MsixPackage@@IEAAJXZ; MsixPackage::Provisioning::Library::MsixProvisioningModule<MsixPackage::Provisioning::Library::MsixAppxDeploymentClient>::LoadDynamic(void)
0x180041b6f  mov     edi, eax
0x180041b71  test    eax, eax
0x180041b73  jns     short loc_180041BA1
0x180041b75  mov     rcx, [rsp+58h]; this
0x180041b7a  lea     rax, aFailedToLoadAp; "Failed to load AppxDeploymentClient.DLL"...
0x180041b81  mov     r9d, edi; char *
0x180041b84  mov     qword ptr [rsp+58h+var_38], rax; int
0x180041b89  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180041b90  mov     edx, 1E4h; void *
0x180041b95  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180041b9a  mov     eax, edi
0x180041b9c  jmp     loc_180041C4F
0x180041ba1  mov     rax, [rbx+78h]
0x180041ba5  test    rax, rax
0x180041ba8  jnz     short loc_180041C21
0x180041baa  mov     rcx, [rbx+8]; hModule
0x180041bae  lea     rdx, aAppxremovepack; "AppxRemovePackageForAllUsers"
0x180041bb5  call    cs:__imp_GetProcAddress
0x180041bbb  mov     [rbx+78h], rax
0x180041bbf  test    rax, rax
0x180041bc2  jnz     short loc_180041C21
0x180041bc4  call    cs:__imp_GetLastError
0x180041bca  mov     edi, 80070000h
0x180041bcf  test    eax, eax
0x180041bd1  jle     short loc_180041BDA
0x180041bd3  movzx   eax, ax
0x180041bd6  or      eax, edi
0x180041bd8  test    eax, eax
0x180041bda  jns     short loc_180041BF3
0x180041bdc  call    cs:__imp_GetLastError
0x180041be2  mov     ebx, eax
0x180041be4  test    eax, eax
0x180041be6  jle     short loc_180041BED
0x180041be8  movzx   ebx, ax
0x180041beb  or      ebx, edi
0x180041bed  test    ebx, ebx
0x180041bef  jns     short loc_180041C1D
0x180041bf1  jmp     short loc_180041BF8
0x180041bf3  mov     ebx, 80004005h
0x180041bf8  mov     rcx, [rsp+58h]; this
0x180041bfd  lea     rax, aUnableToGetpro_5; "Unable to GetProcAddress 'AppxRemovePac"...
0x180041c04  mov     r9d, ebx; char *
0x180041c07  mov     qword ptr [rsp+58h+var_38], rax; int
0x180041c0c  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180041c13  mov     edx, 1ECh; void *
0x180041c18  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180041c1d  mov     eax, ebx
0x180041c1f  jmp     short loc_180041C4F
0x180041c21  mov     rdx, rsi
0x180041c24  mov     rcx, rbp
0x180041c27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041c2c  mov     ebx, eax
0x180041c2e  test    eax, eax
0x180041c30  jns     short loc_180041C4D
0x180041c32  mov     rcx, [rsp+58h]; this
0x180041c37  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180041c3e  mov     r9d, eax; char *
0x180041c41  mov     edx, 1F0h; void *
0x180041c46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041c4b  jmp     short loc_180041C1D
0x180041c4d  xor     eax, eax
0x180041c4f  add     rsp, 38h
0x180041c53  pop     rdi
0x180041c54  pop     rsi
0x180041c55  pop     rbp
0x180041c56  pop     rbx
0x180041c57  retn
```
