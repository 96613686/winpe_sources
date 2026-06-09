# MsixPackage::Provisioning::Library::MsixAppxDeploymentClient::IsPackageInstalled(ushort const *,int *)

- ea: `0x180047a30`
- end: `0x180047b49`
- name: `?IsPackageInstalled@MsixAppxDeploymentClient@Library@Provisioning@MsixPackage@@QEAAJPEBGPEAH@Z`
- size: `281`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::MsixAppxDeploymentClient *__hidden this, const unsigned __int16 *, int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180044ecc`
- `0x180049f94`

## callees

- `0x18000cfe8`
- `0x180038de4`
- `0x180039e9c`
- `0x180047a30`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180047ab2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180047ab2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047ac1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047ad9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047ac1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047ad9`

## string_xrefs

- `0x180047a56`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x180047a83`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x180047b0d`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x180047aab`: `IsPackageInstalled`
- `0x180047afe`: `Unable to GetProcAddress 'IsPackageInstalled'`

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
0x180047a30  push    rbx
0x180047a32  push    rbp
0x180047a33  push    rsi
0x180047a34  push    rdi
0x180047a35  sub     rsp, 38h
0x180047a39  mov     rsi, r8
0x180047a3c  mov     rbp, rdx
0x180047a3f  mov     rbx, rcx
0x180047a42  test    r8, r8
0x180047a45  jnz     short loc_180047A6C
0x180047a47  mov     ebx, 80070057h
0x180047a4c  mov     edx, 116h; void *
0x180047a51  mov     rcx, [rsp+58h]; this
0x180047a56  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180047a5d  mov     r9d, ebx; char *
0x180047a60  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047a65  mov     eax, ebx
0x180047a67  jmp     loc_180047B40
0x180047a6c  mov     dword ptr [r8], 1
0x180047a73  call    ?LoadDynamic@?$MsixProvisioningModule@VMsixAppxDeploymentClient@Library@Provisioning@MsixPackage@@@Library@Provisioning@MsixPackage@@IEAAJXZ; MsixPackage::Provisioning::Library::MsixProvisioningModule<MsixPackage::Provisioning::Library::MsixAppxDeploymentClient>::LoadDynamic(void)
0x180047a78  mov     edi, eax
0x180047a7a  test    eax, eax
0x180047a7c  jns     short loc_180047A9E
0x180047a7e  mov     rcx, [rsp+58h]; this
0x180047a83  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180047a8a  mov     r9d, eax; char *
0x180047a8d  mov     edx, 11Ch; void *
0x180047a92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047a97  mov     eax, edi
0x180047a99  jmp     loc_180047B40
0x180047a9e  mov     rax, [rbx+38h]
0x180047aa2  test    rax, rax
0x180047aa5  jnz     short loc_180047B23
0x180047aa7  mov     rcx, [rbx+8]; hModule
0x180047aab  lea     rdx, aIspackageinsta; "IsPackageInstalled"
0x180047ab2  call    cs:__imp_GetProcAddress
0x180047ab8  mov     [rbx+38h], rax
0x180047abc  test    rax, rax
0x180047abf  jnz     short loc_180047B23
0x180047ac1  call    cs:__imp_GetLastError
0x180047ac7  mov     edi, 80070000h
0x180047acc  test    eax, eax
0x180047ace  jle     short loc_180047AD7
0x180047ad0  movzx   eax, ax
0x180047ad3  or      eax, edi
0x180047ad5  test    eax, eax
0x180047ad7  jns     short loc_180047AF4
0x180047ad9  call    cs:__imp_GetLastError
0x180047adf  mov     ebx, eax
0x180047ae1  test    eax, eax
0x180047ae3  jle     short loc_180047AEA
0x180047ae5  movzx   ebx, ax
0x180047ae8  or      ebx, edi
0x180047aea  test    ebx, ebx
0x180047aec  jns     loc_180047A65
0x180047af2  jmp     short loc_180047AF9
0x180047af4  mov     ebx, 80004005h
0x180047af9  mov     rcx, [rsp+58h]; this
0x180047afe  lea     rax, aUnableToGetpro_10; "Unable to GetProcAddress 'IsPackageInst"...
0x180047b05  mov     r9d, ebx; char *
0x180047b08  mov     qword ptr [rsp+58h+var_38], rax; int
0x180047b0d  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180047b14  mov     edx, 133h; void *
0x180047b19  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180047b1e  jmp     loc_180047A65
0x180047b23  mov     rdx, rsi
0x180047b26  mov     rcx, rbp
0x180047b29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047b2e  mov     ebx, eax
0x180047b30  test    eax, eax
0x180047b32  jns     short loc_180047B3E
0x180047b34  mov     edx, 137h
0x180047b39  jmp     loc_180047A51
0x180047b3e  xor     eax, eax
0x180047b40  add     rsp, 38h
0x180047b44  pop     rdi
0x180047b45  pop     rsi
0x180047b46  pop     rbp
0x180047b47  pop     rbx
0x180047b48  retn
```
