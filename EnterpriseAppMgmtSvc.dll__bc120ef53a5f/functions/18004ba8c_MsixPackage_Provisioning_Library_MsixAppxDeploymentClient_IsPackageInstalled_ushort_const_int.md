# MsixPackage::Provisioning::Library::MsixAppxDeploymentClient::IsPackageInstalled(ushort const *,int *)

- ea: `0x18004ba8c`
- end: `0x18004bbbc`
- name: `?IsPackageInstalled@MsixAppxDeploymentClient@Library@Provisioning@MsixPackage@@QEAAJPEBGPEAH@Z`
- size: `304`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::MsixAppxDeploymentClient *__hidden this, const unsigned __int16 *, int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180048dec`
- `0x18004e0e0`

## callees

- `0x18000d3dc`
- `0x18003c350`
- `0x18003d4ec`
- `0x18004ba8c`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004bb12`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004bb12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bb27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bb45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bb27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bb45`

## string_xrefs

- `0x18004bab2`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x18004badf`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x18004bb7f`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x18004bb70`: `Unable to GetProcAddress 'IsPackageInstalled'`
- `0x18004bb0b`: `IsPackageInstalled`

## pseudocode

```c
__int64 __fastcall MsixPackage::Provisioning::Library::MsixAppxDeploymentClient::IsPackageInstalled(
        MsixPackage::Provisioning::Library::MsixAppxDeploymentClient *this,
        const unsigned __int16 *a2,
        int *a3,
        const char *a4)
{
  unsigned int v7; // ebx
  __int64 v8; // rdx
  int Dynamic; // eax
  unsigned int v11; // edi
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  bool v14; // sf
  signed int v15; // eax
  int v16; // [rsp+20h] [rbp-38h]
  const char *v17; // [rsp+28h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( !a3 )
  {
    v7 = -2147024809;
    v8 = 278;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\MsixModules.h",
      (const char *)v7,
      v16);
    return v7;
  }
  *a3 = 1;
  Dynamic = MsixPackage::Provisioning::Library::MsixProvisioningModule<MsixPackage::Provisioning::Library::MsixAppxDeploymentClient>::LoadDynamic(
              this,
              (__int64)a2,
              (__int64)a3,
              a4);
  v11 = Dynamic;
  if ( Dynamic >= 0 )
  {
    ProcAddress = (FARPROC)*((_QWORD *)this + 7);
    if ( !ProcAddress )
    {
      ProcAddress = GetProcAddress(*((HMODULE *)this + 1), "IsPackageInstalled");
      *((_QWORD *)this + 7) = ProcAddress;
      if ( !ProcAddress )
      {
        LastError = GetLastError();
        v14 = LastError < 0;
        if ( LastError > 0 )
          v14 = 1;
        if ( v14 )
        {
          v15 = GetLastError();
          v7 = v15;
          if ( v15 > 0 )
            v7 = (unsigned __int16)v15 | 0x80070000;
          if ( (v7 & 0x80000000) == 0 )
            return v7;
        }
        else
        {
          v7 = -2147467259;
        }
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x133,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\MsixModules.h",
          (const char *)v7,
          (int)"Unable to GetProcAddress 'IsPackageInstalled'",
          v17);
        return v7;
      }
    }
    v7 = ((__int64 (__fastcall *)(const unsigned __int16 *, int *))ProcAddress)(a2, a3);
    if ( (v7 & 0x80000000) != 0 )
    {
      v8 = 311;
      goto LABEL_3;
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11C,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\MsixModules.h",
      (const char *)(unsigned int)Dynamic,
      v16);
    return v11;
  }
}

```

## disassembly

```asm
0x18004ba8c  push    rbx
0x18004ba8e  push    rbp
0x18004ba8f  push    rsi
0x18004ba90  push    rdi
0x18004ba91  sub     rsp, 38h
0x18004ba95  mov     rsi, r8
0x18004ba98  mov     rbp, rdx
0x18004ba9b  mov     rbx, rcx
0x18004ba9e  test    r8, r8
0x18004baa1  jnz     short loc_18004BAC8
0x18004baa3  mov     ebx, 80070057h
0x18004baa8  mov     edx, 116h; void *
0x18004baad  mov     rcx, [rsp+58h]; this
0x18004bab2  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004bab9  mov     r9d, ebx; char *
0x18004babc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004bac1  mov     eax, ebx
0x18004bac3  jmp     loc_18004BBB2
0x18004bac8  mov     dword ptr [r8], 1
0x18004bacf  call    ?LoadDynamic@?$MsixProvisioningModule@VMsixAppxDeploymentClient@Library@Provisioning@MsixPackage@@@Library@Provisioning@MsixPackage@@IEAAJXZ; MsixPackage::Provisioning::Library::MsixProvisioningModule<MsixPackage::Provisioning::Library::MsixAppxDeploymentClient>::LoadDynamic(void)
0x18004bad4  mov     edi, eax
0x18004bad6  test    eax, eax
0x18004bad8  jns     short loc_18004BAFA
0x18004bada  mov     rcx, [rsp+58h]; this
0x18004badf  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004bae6  mov     r9d, eax; char *
0x18004bae9  mov     edx, 11Ch; void *
0x18004baee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004baf3  mov     eax, edi
0x18004baf5  jmp     loc_18004BBB2
0x18004bafa  mov     rax, [rbx+38h]
0x18004bafe  test    rax, rax
0x18004bb01  jnz     loc_18004BB95
0x18004bb07  mov     rcx, [rbx+8]; hModule
0x18004bb0b  lea     rdx, aIspackageinsta; "IsPackageInstalled"
0x18004bb12  call    cs:__imp_GetProcAddress
0x18004bb19  nop     dword ptr [rax+rax+00h]
0x18004bb1e  mov     [rbx+38h], rax
0x18004bb22  test    rax, rax
0x18004bb25  jnz     short loc_18004BB95
0x18004bb27  call    cs:__imp_GetLastError
0x18004bb2e  nop     dword ptr [rax+rax+00h]
0x18004bb33  mov     edi, 80070000h
0x18004bb38  test    eax, eax
0x18004bb3a  jle     short loc_18004BB43
0x18004bb3c  movzx   eax, ax
0x18004bb3f  or      eax, edi
0x18004bb41  test    eax, eax
0x18004bb43  jns     short loc_18004BB66
0x18004bb45  call    cs:__imp_GetLastError
0x18004bb4c  nop     dword ptr [rax+rax+00h]
0x18004bb51  mov     ebx, eax
0x18004bb53  test    eax, eax
0x18004bb55  jle     short loc_18004BB5C
0x18004bb57  movzx   ebx, ax
0x18004bb5a  or      ebx, edi
0x18004bb5c  test    ebx, ebx
0x18004bb5e  jns     loc_18004BAC1
0x18004bb64  jmp     short loc_18004BB6B
0x18004bb66  mov     ebx, 80004005h
0x18004bb6b  mov     rcx, [rsp+58h]; this
0x18004bb70  lea     rax, aUnableToGetpro_10; "Unable to GetProcAddress 'IsPackageInst"...
0x18004bb77  mov     r9d, ebx; char *
0x18004bb7a  mov     qword ptr [rsp+58h+var_38], rax; int
0x18004bb7f  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004bb86  mov     edx, 133h; void *
0x18004bb8b  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004bb90  jmp     loc_18004BAC1
0x18004bb95  mov     rdx, rsi
0x18004bb98  mov     rcx, rbp
0x18004bb9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bba0  mov     ebx, eax
0x18004bba2  test    eax, eax
0x18004bba4  jns     short loc_18004BBB0
0x18004bba6  mov     edx, 137h
0x18004bbab  jmp     loc_18004BAAD
0x18004bbb0  xor     eax, eax
0x18004bbb2  add     rsp, 38h
0x18004bbb6  pop     rdi
0x18004bbb7  pop     rsi
0x18004bbb8  pop     rbp
0x18004bbb9  pop     rbx
0x18004bbba  retn
```
