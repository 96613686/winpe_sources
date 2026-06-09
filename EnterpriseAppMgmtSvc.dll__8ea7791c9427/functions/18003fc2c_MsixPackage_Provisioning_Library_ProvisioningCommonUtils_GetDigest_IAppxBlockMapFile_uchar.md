# MsixPackage::Provisioning::Library::ProvisioningCommonUtils::GetDigest(IAppxBlockMapFile *,uchar *)

- ea: `0x18003fc2c`
- end: `0x18003ff47`
- name: `?GetDigest@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEAUIAppxBlockMapFile@@PEAE@Z`
- size: `795`
- prototype: `static int(struct IAppxBlockMapFile *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18003e91c`

## callees

- `0x18000cfe8`
- `0x18003fc2c`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fdbb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fe6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fec4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fdbb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fe6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fec4`
- `bcrypt!BCryptFinishHash` at `0x18003fdf4`
- `bcrypt!BCryptFinishHash` at `0x18003fdf4`
- `bcrypt!BCryptCreateHash` at `0x18003fc5c`
- `bcrypt!BCryptCreateHash` at `0x18003fc5c`
- `bcrypt!BCryptDestroyHash` at `0x18003fcc4`
- `bcrypt!BCryptDestroyHash` at `0x18003fe07`
- `bcrypt!BCryptDestroyHash` at `0x18003fe35`
- `bcrypt!BCryptDestroyHash` at `0x18003fcc4`
- `bcrypt!BCryptDestroyHash` at `0x18003fe07`
- `bcrypt!BCryptDestroyHash` at `0x18003fe35`
- `bcrypt!BCryptHashData` at `0x18003fd85`
- `bcrypt!BCryptHashData` at `0x18003fd85`

## string_xrefs

- `0x18003fc93`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningutils.cpp`
- `0x18003fcf9`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningutils.cpp`
- `0x18003fe4f`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningutils.cpp`
- `0x18003fea9`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningutils.cpp`
- `0x18003ff03`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall MsixPackage::Provisioning::Library::ProvisioningCommonUtils::GetDigest(
        struct IAppxBlockMapFile *a1,
        unsigned __int8 *a2)
{
  struct IAppxBlockMapFileVtbl *lpVtbl; // rax
  int v5; // eax
  unsigned int v6; // ebx
  int v8; // eax
  __int64 v9; // rax
  int v10; // eax
  __int64 v11; // rax
  int v12; // eax
  int v13; // eax
  BCRYPT_HASH_HANDLE v14; // rcx
  int pbSecret; // [rsp+20h] [rbp-40h]
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-20h] BYREF
  __int64 *v17; // [rsp+48h] [rbp-18h] BYREF
  PUCHAR pbInput[2]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  int v20; // [rsp+90h] [rbp+30h] BYREF
  ULONG cbInput; // [rsp+A0h] [rbp+40h] BYREF
  __int64 *v22; // [rsp+A8h] [rbp+48h] BYREF

  if ( BCryptCreateHash((BCRYPT_ALG_HANDLE)0x41, &phHash, 0, 0, 0, 0, 0) < 0 )
    __fastfail(7u);
  lpVtbl = a1->lpVtbl;
  v22 = 0;
  v5 = ((__int64 (__fastcall *)(struct IAppxBlockMapFile *, __int64 **))lpVtbl->GetBlocks)(a1, &v22);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v20 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v22 + 32))(v22, &v20);
    v6 = v8;
    if ( v8 >= 0 )
    {
      while ( 1 )
      {
        if ( !v20 )
        {
          if ( a2 && BCryptFinishHash(phHash, a2, 0x20u, 0) < 0 )
            __fastfail(7u);
          BCryptDestroyHash(phHash);
          v14 = 0;
          phHash = 0;
          if ( v22 )
          {
            (*(void (__fastcall **)(__int64 *))(*v22 + 16))(v22);
            v14 = phHash;
          }
          if ( v14 )
            BCryptDestroyHash(v14);
          return 0;
        }
        v17 = 0;
        v9 = *v22;
        v17 = 0;
        v10 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v9 + 24))(v22, &v17);
        v6 = v10;
        if ( v10 < 0 )
          break;
        cbInput = 0;
        pbInput[0] = 0;
        v11 = *v17;
        pbInput[0] = 0;
        v12 = (*(__int64 (__fastcall **)(__int64 *, ULONG *, PUCHAR *))(v11 + 24))(v17, &cbInput, pbInput);
        v6 = v12;
        if ( v12 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x77,
            (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningutils.cpp",
            (const char *)(unsigned int)v12,
            pbSecret);
          if ( pbInput[0] )
            CoTaskMemFree(pbInput[0]);
          if ( v17 )
            (*(void (__fastcall **)(__int64 *))(*v17 + 16))(v17);
          if ( v22 )
            (*(void (__fastcall **)(__int64 *))(*v22 + 16))(v22);
          goto LABEL_6;
        }
        if ( BCryptHashData(phHash, pbInput[0], cbInput, 0) < 0 )
          __fastfail(7u);
        v13 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v22 + 40))(v22, &v20);
        v6 = v13;
        if ( v13 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x7B,
            (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningutils.cpp",
            (const char *)(unsigned int)v13,
            pbSecret);
          if ( pbInput[0] )
            CoTaskMemFree(pbInput[0]);
          if ( v17 )
            (*(void (__fastcall **)(__int64 *))(*v17 + 16))(v17);
          if ( v22 )
            (*(void (__fastcall **)(__int64 *))(*v22 + 16))(v22);
          goto LABEL_6;
        }
        if ( pbInput[0] )
          CoTaskMemFree(pbInput[0]);
        if ( v17 )
          (*(void (__fastcall **)(__int64 *))(*v17 + 16))(v17);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x73,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningutils.cpp",
        (const char *)(unsigned int)v10,
        pbSecret);
      if ( v17 )
        (*(void (__fastcall **)(__int64 *))(*v17 + 16))(v17);
      if ( v22 )
        (*(void (__fastcall **)(__int64 *))(*v22 + 16))(v22);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6F,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningutils.cpp",
        (const char *)(unsigned int)v8,
        pbSecret);
      if ( v22 )
        (*(void (__fastcall **)(__int64 *))(*v22 + 16))(v22);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6C,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningutils.cpp",
      (const char *)(unsigned int)v5,
      pbSecret);
    if ( v22 )
      (*(void (__fastcall **)(__int64 *))(*v22 + 16))(v22);
  }
LABEL_6:
  if ( phHash )
    BCryptDestroyHash(phHash);
  return v6;
}

```

## disassembly

```asm
0x18003fc2c  push    rbp
0x18003fc2e  push    rbx
0x18003fc2f  push    rsi
0x18003fc30  push    rdi
0x18003fc31  push    r14
0x18003fc33  mov     rbp, rsp
0x18003fc36  sub     rsp, 60h
0x18003fc3a  mov     rdi, rdx
0x18003fc3d  mov     rbx, rcx
0x18003fc40  xor     esi, esi
0x18003fc42  mov     [rsp+60h+dwFlags], esi; dwFlags
0x18003fc46  mov     [rsp+60h+cbSecret], esi; cbSecret
0x18003fc4a  mov     [rsp+60h+pbSecret], rsi; int
0x18003fc4f  xor     r9d, r9d; cbHashObject
0x18003fc52  xor     r8d, r8d; pbHashObject
0x18003fc55  lea     rdx, [rbp+phHash]; phHash
0x18003fc59  lea     ecx, [rsi+41h]; hAlgorithm
0x18003fc5c  call    cs:__imp_BCryptCreateHash
0x18003fc62  lea     r14d, [rsi+7]
0x18003fc66  test    eax, eax
0x18003fc68  jns     short loc_18003FC6F
0x18003fc6a  mov     ecx, r14d
0x18003fc6d  int     29h; Win8: RtlFailFast(ecx)
0x18003fc6f  mov     rax, [rbx]
0x18003fc72  mov     [rbp+arg_18], rsi
0x18003fc76  lea     rdx, [rbp+arg_18]
0x18003fc7a  mov     rcx, rbx
0x18003fc7d  mov     rax, [rax+18h]
0x18003fc81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fc86  mov     ebx, eax
0x18003fc88  test    eax, eax
0x18003fc8a  jns     short loc_18003FCD1
0x18003fc8c  mov     rcx, [rbp+28h]; this
0x18003fc90  mov     r9d, eax; char *
0x18003fc93  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003fc9a  mov     edx, 6Ch ; 'l'; void *
0x18003fc9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fca4  nop
0x18003fca5  mov     rcx, [rbp+arg_18]
0x18003fca9  test    rcx, rcx
0x18003fcac  jz      short loc_18003FCBB
0x18003fcae  mov     rax, [rcx]
0x18003fcb1  mov     rax, [rax+10h]
0x18003fcb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fcba  nop
0x18003fcbb  mov     rcx, [rbp+phHash]; hHash
0x18003fcbf  test    rcx, rcx
0x18003fcc2  jz      short loc_18003FCCA
0x18003fcc4  call    cs:__imp_BCryptDestroyHash
0x18003fcca  mov     eax, ebx
0x18003fccc  jmp     loc_18003FE3D
0x18003fcd1  mov     [rbp+arg_0], esi
0x18003fcd4  mov     rcx, [rbp+arg_18]
0x18003fcd8  mov     rax, [rcx]
0x18003fcdb  lea     rdx, [rbp+arg_0]
0x18003fcdf  mov     rax, [rax+20h]
0x18003fce3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fce8  mov     ebx, eax
0x18003fcea  test    eax, eax
0x18003fcec  jns     loc_18003FDD8
0x18003fcf2  mov     rcx, [rbp+28h]; this
0x18003fcf6  mov     r9d, eax; char *
0x18003fcf9  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003fd00  mov     edx, 6Fh ; 'o'; void *
0x18003fd05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fd0a  nop
0x18003fd0b  mov     rcx, [rbp+arg_18]
0x18003fd0f  test    rcx, rcx
0x18003fd12  jz      short loc_18003FD21
0x18003fd14  mov     rax, [rcx]
0x18003fd17  mov     rax, [rax+10h]
0x18003fd1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fd20  nop
0x18003fd21  jmp     short loc_18003FCBB
0x18003fd23  mov     [rbp+var_18], rsi
0x18003fd27  mov     rcx, [rbp+arg_18]
0x18003fd2b  mov     rax, [rcx]
0x18003fd2e  mov     [rbp+var_18], rsi
0x18003fd32  lea     rdx, [rbp+var_18]
0x18003fd36  mov     rax, [rax+18h]
0x18003fd3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fd3f  mov     ebx, eax
0x18003fd41  test    eax, eax
0x18003fd43  js      loc_18003FEFC
0x18003fd49  mov     [rbp+cbInput], esi
0x18003fd4c  mov     [rbp+pbInput], rsi
0x18003fd50  mov     rcx, [rbp+var_18]
0x18003fd54  mov     rax, [rcx]
0x18003fd57  mov     [rbp+pbInput], rsi
0x18003fd5b  lea     r8, [rbp+pbInput]
0x18003fd5f  lea     rdx, [rbp+cbInput]
0x18003fd63  mov     rax, [rax+18h]
0x18003fd67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fd6c  mov     ebx, eax
0x18003fd6e  test    eax, eax
0x18003fd70  js      loc_18003FEA2
0x18003fd76  xor     r9d, r9d; dwFlags
0x18003fd79  mov     r8d, [rbp+cbInput]; cbInput
0x18003fd7d  mov     rdx, [rbp+pbInput]; pbInput
0x18003fd81  mov     rcx, [rbp+phHash]; hHash
0x18003fd85  call    cs:__imp_BCryptHashData
0x18003fd8b  test    eax, eax
0x18003fd8d  jns     short loc_18003FD94
0x18003fd8f  mov     rcx, r14
0x18003fd92  int     29h; Win8: RtlFailFast(ecx)
0x18003fd94  mov     rcx, [rbp+arg_18]
0x18003fd98  mov     rax, [rcx]
0x18003fd9b  lea     rdx, [rbp+arg_0]
0x18003fd9f  mov     rax, [rax+28h]
0x18003fda3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fda8  mov     ebx, eax
0x18003fdaa  test    eax, eax
0x18003fdac  js      loc_18003FE48
0x18003fdb2  mov     rcx, [rbp+pbInput]; pv
0x18003fdb6  test    rcx, rcx
0x18003fdb9  jz      short loc_18003FDC2
0x18003fdbb  call    cs:__imp_CoTaskMemFree
0x18003fdc1  nop
0x18003fdc2  mov     rcx, [rbp+var_18]
0x18003fdc6  test    rcx, rcx
0x18003fdc9  jz      short loc_18003FDD8
0x18003fdcb  mov     rax, [rcx]
0x18003fdce  mov     rax, [rax+10h]
0x18003fdd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fdd7  nop
0x18003fdd8  cmp     [rbp+arg_0], esi
0x18003fddb  jnz     loc_18003FD23
0x18003fde1  test    rdi, rdi
0x18003fde4  jz      short loc_18003FE03
0x18003fde6  xor     r9d, r9d; dwFlags
0x18003fde9  lea     r8d, [r9+20h]; cbOutput
0x18003fded  mov     rdx, rdi; pbOutput
0x18003fdf0  mov     rcx, [rbp+phHash]; hHash
0x18003fdf4  call    cs:__imp_BCryptFinishHash
0x18003fdfa  test    eax, eax
0x18003fdfc  jns     short loc_18003FE03
0x18003fdfe  mov     rcx, r14
0x18003fe01  int     29h; Win8: RtlFailFast(ecx)
0x18003fe03  mov     rcx, [rbp+phHash]; hHash
0x18003fe07  call    cs:__imp_BCryptDestroyHash
0x18003fe0d  mov     rcx, rsi
0x18003fe10  mov     [rbp+phHash], rcx
0x18003fe14  mov     rdx, [rbp+arg_18]
0x18003fe18  test    rdx, rdx
0x18003fe1b  jz      short loc_18003FE30
0x18003fe1d  mov     rax, [rdx]
0x18003fe20  mov     rcx, rdx
0x18003fe23  mov     rax, [rax+10h]
0x18003fe27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fe2c  mov     rcx, [rbp+phHash]; hHash
0x18003fe30  test    rcx, rcx
0x18003fe33  jz      short loc_18003FE3B
0x18003fe35  call    cs:__imp_BCryptDestroyHash
0x18003fe3b  xor     eax, eax
0x18003fe3d  add     rsp, 60h
0x18003fe41  pop     r14
0x18003fe43  pop     rdi
0x18003fe44  pop     rsi
0x18003fe45  pop     rbx
0x18003fe46  pop     rbp
0x18003fe47  retn
0x18003fe48  mov     rcx, [rbp+28h]; this
0x18003fe4c  mov     r9d, ebx; char *
0x18003fe4f  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003fe56  mov     edx, 7Bh ; '{'; void *
0x18003fe5b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fe60  nop
0x18003fe61  mov     rcx, [rbp+pbInput]; pv
0x18003fe65  test    rcx, rcx
0x18003fe68  jz      short loc_18003FE71
0x18003fe6a  call    cs:__imp_CoTaskMemFree
0x18003fe70  nop
0x18003fe71  mov     rcx, [rbp+var_18]
0x18003fe75  test    rcx, rcx
0x18003fe78  jz      short loc_18003FE87
0x18003fe7a  mov     rax, [rcx]
0x18003fe7d  mov     rax, [rax+10h]
0x18003fe81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fe86  nop
0x18003fe87  mov     rcx, [rbp+arg_18]
0x18003fe8b  test    rcx, rcx
0x18003fe8e  jz      short loc_18003FE9D
0x18003fe90  mov     rax, [rcx]
0x18003fe93  mov     rax, [rax+10h]
0x18003fe97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fe9c  nop
0x18003fe9d  jmp     loc_18003FCBB
0x18003fea2  mov     rcx, [rbp+28h]; this
0x18003fea6  mov     r9d, ebx; char *
0x18003fea9  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003feb0  mov     edx, 77h ; 'w'; void *
0x18003feb5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003feba  nop
0x18003febb  mov     rcx, [rbp+pbInput]; pv
0x18003febf  test    rcx, rcx
0x18003fec2  jz      short loc_18003FECB
0x18003fec4  call    cs:__imp_CoTaskMemFree
0x18003feca  nop
0x18003fecb  mov     rcx, [rbp+var_18]
0x18003fecf  test    rcx, rcx
0x18003fed2  jz      short loc_18003FEE1
0x18003fed4  mov     rax, [rcx]
0x18003fed7  mov     rax, [rax+10h]
0x18003fedb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fee0  nop
0x18003fee1  mov     rcx, [rbp+arg_18]
0x18003fee5  test    rcx, rcx
0x18003fee8  jz      short loc_18003FEF7
0x18003feea  mov     rax, [rcx]
0x18003feed  mov     rax, [rax+10h]
0x18003fef1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fef6  nop
0x18003fef7  jmp     loc_18003FCBB
0x18003fefc  mov     rcx, [rbp+28h]; this
0x18003ff00  mov     r9d, ebx; char *
0x18003ff03  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003ff0a  mov     edx, 73h ; 's'; void *
0x18003ff0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ff14  nop
0x18003ff15  mov     rcx, [rbp+var_18]
0x18003ff19  test    rcx, rcx
0x18003ff1c  jz      short loc_18003FF2B
0x18003ff1e  mov     rax, [rcx]
0x18003ff21  mov     rax, [rax+10h]
0x18003ff25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ff2a  nop
0x18003ff2b  mov     rcx, [rbp+arg_18]
0x18003ff2f  test    rcx, rcx
0x18003ff32  jz      short loc_18003FF41
0x18003ff34  mov     rax, [rcx]
0x18003ff37  mov     rax, [rax+10h]
0x18003ff3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ff40  nop
0x18003ff41  jmp     loc_18003FCBB
```
