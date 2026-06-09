# MsixPackage::Provisioning::Library::MsixPackageAdapter::PreRegisterPackage(void)

- ea: `0x18004865c`
- end: `0x1800487b4`
- name: `?PreRegisterPackage@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJXZ`
- size: `344`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::MsixPackageAdapter *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004c440`

## callees

- `0x18000cfe8`
- `0x180038de4`
- `0x180039e9c`
- `0x18004865c`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800486d6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800486d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800486e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048700`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800486e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048700`

## string_xrefs

- `0x180048693`: `Failed to load AppxDeploymentClient.DLL.`
- `0x1800486a2`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x180048739`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x180048765`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x180048794`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`

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
0x18004865c  push    rbx
0x18004865e  push    rbp
0x18004865f  push    rsi
0x180048660  push    rdi
0x180048661  sub     rsp, 38h
0x180048665  mov     rsi, [rcx+10h]
0x180048669  lea     rdi, [rcx+30h]
0x18004866d  cmp     qword ptr [rdi+18h], 8
0x180048672  jb      short loc_180048679
0x180048674  mov     rbp, [rdi]
0x180048677  jmp     short loc_18004867C
0x180048679  mov     rbp, rdi
0x18004867c  lea     rcx, [rsi+140h]
0x180048683  call    ?LoadDynamic@?$MsixProvisioningModule@VMsixAppxDeploymentClient@Library@Provisioning@MsixPackage@@@Library@Provisioning@MsixPackage@@IEAAJXZ; MsixPackage::Provisioning::Library::MsixProvisioningModule<MsixPackage::Provisioning::Library::MsixAppxDeploymentClient>::LoadDynamic(void)
0x180048688  mov     ebx, eax
0x18004868a  test    eax, eax
0x18004868c  jns     short loc_1800486B8
0x18004868e  mov     rcx, [rsp+58h]; this
0x180048693  lea     rax, aFailedToLoadAp; "Failed to load AppxDeploymentClient.DLL"...
0x18004869a  mov     r9d, ebx; char *
0x18004869d  mov     qword ptr [rsp+58h+var_38], rax; int
0x1800486a2  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800486a9  mov     edx, 1CFh; void *
0x1800486ae  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800486b3  jmp     loc_180048779
0x1800486b8  mov     rax, [rsi+1B0h]
0x1800486bf  test    rax, rax
0x1800486c2  jnz     loc_180048750
0x1800486c8  mov     rcx, [rsi+148h]; hModule
0x1800486cf  lea     rdx, aAppxpreregiste; "AppxPreRegisterPackage"
0x1800486d6  call    cs:__imp_GetProcAddress
0x1800486dc  mov     [rsi+1B0h], rax
0x1800486e3  test    rax, rax
0x1800486e6  jnz     short loc_180048750
0x1800486e8  call    cs:__imp_GetLastError
0x1800486ee  mov     esi, 80070000h
0x1800486f3  test    eax, eax
0x1800486f5  jle     short loc_1800486FE
0x1800486f7  movzx   eax, ax
0x1800486fa  or      eax, esi
0x1800486fc  test    eax, eax
0x1800486fe  jns     short loc_180048720
0x180048700  call    cs:__imp_GetLastError
0x180048706  mov     ebx, eax
0x180048708  test    eax, eax
0x18004870a  jle     short loc_180048711
0x18004870c  movzx   ebx, ax
0x18004870f  or      ebx, esi
0x180048711  test    ebx, ebx
0x180048713  js      short loc_180048725
0x180048715  xor     eax, eax
0x180048717  add     rsp, 38h
0x18004871b  pop     rdi
0x18004871c  pop     rsi
0x18004871d  pop     rbp
0x18004871e  pop     rbx
0x18004871f  retn
0x180048720  mov     ebx, 80004005h
0x180048725  mov     rcx, [rsp+58h]; this
0x18004872a  lea     rax, aUnableToGetpro; "Unable to GetProcAddress 'AppxPreRegist"...
0x180048731  mov     r9d, ebx; char *
0x180048734  mov     qword ptr [rsp+58h+var_38], rax; int
0x180048739  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180048740  mov     edx, 1D7h; void *
0x180048745  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004874a  test    ebx, ebx
0x18004874c  jns     short loc_180048715
0x18004874e  jmp     short loc_180048779
0x180048750  xor     edx, edx
0x180048752  mov     rcx, rbp
0x180048755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004875a  mov     ebx, eax
0x18004875c  test    eax, eax
0x18004875e  jns     short loc_180048715
0x180048760  mov     rcx, [rsp+58h]; this
0x180048765  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004876c  mov     r9d, eax; char *
0x18004876f  mov     edx, 1DBh; void *
0x180048774  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048779  cmp     qword ptr [rdi+18h], 8
0x18004877e  jb      short loc_180048783
0x180048780  mov     rdi, [rdi]
0x180048783  mov     rcx, [rsp+58h]; this
0x180048788  lea     rax, aFailedWhilePre; "Failed while Preregistering package '%w"...
0x18004878f  mov     [rsp+58h+var_30], rdi; char *
0x180048794  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004879b  mov     r9d, ebx; char *
0x18004879e  mov     qword ptr [rsp+58h+var_38], rax; int
0x1800487a3  mov     edx, 3FEh; void *
0x1800487a8  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800487ad  mov     eax, ebx
0x1800487af  jmp     loc_180048717
```
