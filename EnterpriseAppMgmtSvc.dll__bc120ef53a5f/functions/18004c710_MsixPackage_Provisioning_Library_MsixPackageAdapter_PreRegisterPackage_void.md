# MsixPackage::Provisioning::Library::MsixPackageAdapter::PreRegisterPackage(void)

- ea: `0x18004c710`
- end: `0x18004c87b`
- name: `?PreRegisterPackage@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJXZ`
- size: `363`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::MsixPackageAdapter *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800506a4`

## callees

- `0x18000d3dc`
- `0x18003c350`
- `0x18003d4ec`
- `0x18004c710`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004c78a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004c78a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c7a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c7c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c7a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c7c0`

## string_xrefs

- `0x18004c747`: `Failed to load AppxDeploymentClient.DLL.`
- `0x18004c756`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x18004c800`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x18004c82c`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x18004c85b`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`

## pseudocode

```c
__int64 __fastcall MsixPackage::Provisioning::Library::MsixPackageAdapter::PreRegisterPackage(
        MsixPackage::Provisioning::Library::MsixPackageAdapter *this,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  __int64 v4; // rsi
  char *v5; // rdi
  char *v6; // rbp
  int Dynamic; // ebx
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  bool v10; // sf
  signed int v11; // eax
  int v13; // eax
  int v14; // [rsp+20h] [rbp-38h]
  char *v15; // [rsp+28h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v4 = *((_QWORD *)this + 2);
  v5 = (char *)this + 48;
  if ( *((_QWORD *)this + 9) < 8u )
    v6 = (char *)this + 48;
  else
    v6 = *(char **)v5;
  Dynamic = MsixPackage::Provisioning::Library::MsixProvisioningModule<MsixPackage::Provisioning::Library::MsixAppxDeploymentClient>::LoadDynamic(
              (_QWORD *)(v4 + 320),
              a2,
              a3,
              a4);
  if ( Dynamic >= 0 )
  {
    ProcAddress = *(FARPROC *)(v4 + 432);
    if ( !ProcAddress )
    {
      ProcAddress = GetProcAddress(*(HMODULE *)(v4 + 328), "AppxPreRegisterPackage");
      *(_QWORD *)(v4 + 432) = ProcAddress;
      if ( !ProcAddress )
      {
        LastError = GetLastError();
        v10 = LastError < 0;
        if ( LastError > 0 )
          v10 = 1;
        if ( v10 )
        {
          v11 = GetLastError();
          Dynamic = v11;
          if ( v11 > 0 )
            Dynamic = (unsigned __int16)v11 | 0x80070000;
          if ( Dynamic >= 0 )
            return 0;
        }
        else
        {
          Dynamic = -2147467259;
        }
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x1D7,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\MsixModules.h",
          (const char *)(unsigned int)Dynamic,
          (int)"Unable to GetProcAddress 'AppxPreRegisterPackage'",
          v15);
        goto LABEL_20;
      }
    }
    v13 = ((__int64 (__fastcall *)(char *, _QWORD))ProcAddress)(v6, 0);
    Dynamic = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1DB,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\MsixModules.h",
        (const char *)(unsigned int)v13,
        v14);
      goto LABEL_20;
    }
    return 0;
  }
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0x1CF,
    (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\MsixModules.h",
    (const char *)(unsigned int)Dynamic,
    (int)"Failed to load AppxDeploymentClient.DLL.",
    v15);
LABEL_20:
  if ( *((_QWORD *)v5 + 3) >= 8u )
    v5 = *(char **)v5;
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0x3FE,
    (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
    (const char *)(unsigned int)Dynamic,
    (int)"Failed while Preregistering package '%ws'",
    v5);
  return (unsigned int)Dynamic;
}

```

## disassembly

```asm
0x18004c710  push    rbx
0x18004c712  push    rbp
0x18004c713  push    rsi
0x18004c714  push    rdi
0x18004c715  sub     rsp, 38h
0x18004c719  mov     rsi, [rcx+10h]
0x18004c71d  lea     rdi, [rcx+30h]
0x18004c721  cmp     qword ptr [rdi+18h], 8
0x18004c726  jb      short loc_18004C72D
0x18004c728  mov     rbp, [rdi]
0x18004c72b  jmp     short loc_18004C730
0x18004c72d  mov     rbp, rdi
0x18004c730  lea     rcx, [rsi+140h]
0x18004c737  call    ?LoadDynamic@?$MsixProvisioningModule@VMsixAppxDeploymentClient@Library@Provisioning@MsixPackage@@@Library@Provisioning@MsixPackage@@IEAAJXZ; MsixPackage::Provisioning::Library::MsixProvisioningModule<MsixPackage::Provisioning::Library::MsixAppxDeploymentClient>::LoadDynamic(void)
0x18004c73c  mov     ebx, eax
0x18004c73e  test    eax, eax
0x18004c740  jns     short loc_18004C76C
0x18004c742  mov     rcx, [rsp+58h]; this
0x18004c747  lea     rax, aFailedToLoadAp; "Failed to load AppxDeploymentClient.DLL"...
0x18004c74e  mov     r9d, ebx; char *
0x18004c751  mov     qword ptr [rsp+58h+var_38], rax; int
0x18004c756  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004c75d  mov     edx, 1CFh; void *
0x18004c762  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004c767  jmp     loc_18004C840
0x18004c76c  mov     rax, [rsi+1B0h]
0x18004c773  test    rax, rax
0x18004c776  jnz     loc_18004C817
0x18004c77c  mov     rcx, [rsi+148h]; hModule
0x18004c783  lea     rdx, aAppxpreregiste; "AppxPreRegisterPackage"
0x18004c78a  call    cs:__imp_GetProcAddress
0x18004c791  nop     dword ptr [rax+rax+00h]
0x18004c796  mov     [rsi+1B0h], rax
0x18004c79d  test    rax, rax
0x18004c7a0  jnz     short loc_18004C817
0x18004c7a2  call    cs:__imp_GetLastError
0x18004c7a9  nop     dword ptr [rax+rax+00h]
0x18004c7ae  mov     esi, 80070000h
0x18004c7b3  test    eax, eax
0x18004c7b5  jle     short loc_18004C7BE
0x18004c7b7  movzx   eax, ax
0x18004c7ba  or      eax, esi
0x18004c7bc  test    eax, eax
0x18004c7be  jns     short loc_18004C7E7
0x18004c7c0  call    cs:__imp_GetLastError
0x18004c7c7  nop     dword ptr [rax+rax+00h]
0x18004c7cc  mov     ebx, eax
0x18004c7ce  test    eax, eax
0x18004c7d0  jle     short loc_18004C7D7
0x18004c7d2  movzx   ebx, ax
0x18004c7d5  or      ebx, esi
0x18004c7d7  test    ebx, ebx
0x18004c7d9  js      short loc_18004C7EC
0x18004c7db  xor     eax, eax
0x18004c7dd  add     rsp, 38h
0x18004c7e1  pop     rdi
0x18004c7e2  pop     rsi
0x18004c7e3  pop     rbp
0x18004c7e4  pop     rbx
0x18004c7e5  retn
0x18004c7e7  mov     ebx, 80004005h
0x18004c7ec  mov     rcx, [rsp+58h]; this
0x18004c7f1  lea     rax, aUnableToGetpro; "Unable to GetProcAddress 'AppxPreRegist"...
0x18004c7f8  mov     r9d, ebx; char *
0x18004c7fb  mov     qword ptr [rsp+58h+var_38], rax; int
0x18004c800  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004c807  mov     edx, 1D7h; void *
0x18004c80c  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004c811  test    ebx, ebx
0x18004c813  jns     short loc_18004C7DB
0x18004c815  jmp     short loc_18004C840
0x18004c817  xor     edx, edx
0x18004c819  mov     rcx, rbp
0x18004c81c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c821  mov     ebx, eax
0x18004c823  test    eax, eax
0x18004c825  jns     short loc_18004C7DB
0x18004c827  mov     rcx, [rsp+58h]; this
0x18004c82c  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004c833  mov     r9d, eax; char *
0x18004c836  mov     edx, 1DBh; void *
0x18004c83b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004c840  cmp     qword ptr [rdi+18h], 8
0x18004c845  jb      short loc_18004C84A
0x18004c847  mov     rdi, [rdi]
0x18004c84a  mov     rcx, [rsp+58h]; this
0x18004c84f  lea     rax, aFailedWhilePre; "Failed while Preregistering package '%w"...
0x18004c856  mov     [rsp+58h+var_30], rdi; char *
0x18004c85b  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004c862  mov     r9d, ebx; char *
0x18004c865  mov     qword ptr [rsp+58h+var_38], rax; int
0x18004c86a  mov     edx, 3FEh; void *
0x18004c86f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004c874  mov     eax, ebx
0x18004c876  jmp     loc_18004C7DD
```
