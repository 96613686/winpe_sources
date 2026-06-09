# MsixPackage::Provisioning::Library::ProvisioningCommonUtils::GetDigest(IAppxBlockMapFile *,uchar *)

- ea: `0x18004373c`
- end: `0x180043a8e`
- name: `?GetDigest@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEAUIAppxBlockMapFile@@PEAE@Z`
- size: `850`
- prototype: `static int(struct IAppxBlockMapFile *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800422cc`

## callees

- `0x18000d3dc`
- `0x18004373c`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800438dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800439a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043a05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800438dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800439a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043a05`
- `bcrypt!BCryptFinishHash` at `0x18004391c`
- `bcrypt!BCryptFinishHash` at `0x18004391c`
- `bcrypt!BCryptCreateHash` at `0x18004376c`
- `bcrypt!BCryptCreateHash` at `0x18004376c`
- `bcrypt!BCryptDestroyHash` at `0x1800437da`
- `bcrypt!BCryptDestroyHash` at `0x180043935`
- `bcrypt!BCryptDestroyHash` at `0x180043969`
- `bcrypt!BCryptDestroyHash` at `0x1800437da`
- `bcrypt!BCryptDestroyHash` at `0x180043935`
- `bcrypt!BCryptDestroyHash` at `0x180043969`
- `bcrypt!BCryptHashData` at `0x1800438a1`
- `bcrypt!BCryptHashData` at `0x1800438a1`

## string_xrefs

- `0x1800437a9`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningutils.cpp`
- `0x180043815`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningutils.cpp`
- `0x18004398a`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningutils.cpp`
- `0x1800439ea`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningutils.cpp`
- `0x180043a4a`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningutils.cpp`

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
0x18004373c  push    rbp
0x18004373e  push    rbx
0x18004373f  push    rsi
0x180043740  push    rdi
0x180043741  push    r14
0x180043743  mov     rbp, rsp
0x180043746  sub     rsp, 60h
0x18004374a  mov     rdi, rdx
0x18004374d  mov     rbx, rcx
0x180043750  xor     esi, esi
0x180043752  mov     [rsp+60h+dwFlags], esi; dwFlags
0x180043756  mov     [rsp+60h+cbSecret], esi; cbSecret
0x18004375a  mov     [rsp+60h+pbSecret], rsi; int
0x18004375f  xor     r9d, r9d; cbHashObject
0x180043762  xor     r8d, r8d; pbHashObject
0x180043765  lea     rdx, [rbp+phHash]; phHash
0x180043769  lea     ecx, [rsi+41h]; hAlgorithm
0x18004376c  call    cs:__imp_BCryptCreateHash
0x180043773  nop     dword ptr [rax+rax+00h]
0x180043778  lea     r14d, [rsi+7]
0x18004377c  test    eax, eax
0x18004377e  jns     short loc_180043785
0x180043780  mov     ecx, r14d
0x180043783  int     29h; Win8: RtlFailFast(ecx)
0x180043785  mov     rax, [rbx]
0x180043788  mov     [rbp+arg_18], rsi
0x18004378c  lea     rdx, [rbp+arg_18]
0x180043790  mov     rcx, rbx
0x180043793  mov     rax, [rax+18h]
0x180043797  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004379c  mov     ebx, eax
0x18004379e  test    eax, eax
0x1800437a0  jns     short loc_1800437ED
0x1800437a2  mov     rcx, [rbp+28h]; this
0x1800437a6  mov     r9d, eax; char *
0x1800437a9  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800437b0  mov     edx, 6Ch ; 'l'; void *
0x1800437b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800437ba  nop
0x1800437bb  mov     rcx, [rbp+arg_18]
0x1800437bf  test    rcx, rcx
0x1800437c2  jz      short loc_1800437D1
0x1800437c4  mov     rax, [rcx]
0x1800437c7  mov     rax, [rax+10h]
0x1800437cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800437d0  nop
0x1800437d1  mov     rcx, [rbp+phHash]; hHash
0x1800437d5  test    rcx, rcx
0x1800437d8  jz      short loc_1800437E6
0x1800437da  call    cs:__imp_BCryptDestroyHash
0x1800437e1  nop     dword ptr [rax+rax+00h]
0x1800437e6  mov     eax, ebx
0x1800437e8  jmp     loc_180043977
0x1800437ed  mov     [rbp+arg_0], esi
0x1800437f0  mov     rcx, [rbp+arg_18]
0x1800437f4  mov     rax, [rcx]
0x1800437f7  lea     rdx, [rbp+arg_0]
0x1800437fb  mov     rax, [rax+20h]
0x1800437ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043804  mov     ebx, eax
0x180043806  test    eax, eax
0x180043808  jns     loc_180043900
0x18004380e  mov     rcx, [rbp+28h]; this
0x180043812  mov     r9d, eax; char *
0x180043815  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004381c  mov     edx, 6Fh ; 'o'; void *
0x180043821  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043826  nop
0x180043827  mov     rcx, [rbp+arg_18]
0x18004382b  test    rcx, rcx
0x18004382e  jz      short loc_18004383D
0x180043830  mov     rax, [rcx]
0x180043833  mov     rax, [rax+10h]
0x180043837  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004383c  nop
0x18004383d  jmp     short loc_1800437D1
0x18004383f  mov     [rbp+var_18], rsi
0x180043843  mov     rcx, [rbp+arg_18]
0x180043847  mov     rax, [rcx]
0x18004384a  mov     [rbp+var_18], rsi
0x18004384e  lea     rdx, [rbp+var_18]
0x180043852  mov     rax, [rax+18h]
0x180043856  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004385b  mov     ebx, eax
0x18004385d  test    eax, eax
0x18004385f  js      loc_180043A43
0x180043865  mov     [rbp+cbInput], esi
0x180043868  mov     [rbp+pbInput], rsi
0x18004386c  mov     rcx, [rbp+var_18]
0x180043870  mov     rax, [rcx]
0x180043873  mov     [rbp+pbInput], rsi
0x180043877  lea     r8, [rbp+pbInput]
0x18004387b  lea     rdx, [rbp+cbInput]
0x18004387f  mov     rax, [rax+18h]
0x180043883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043888  mov     ebx, eax
0x18004388a  test    eax, eax
0x18004388c  js      loc_1800439E3
0x180043892  xor     r9d, r9d; dwFlags
0x180043895  mov     r8d, [rbp+cbInput]; cbInput
0x180043899  mov     rdx, [rbp+pbInput]; pbInput
0x18004389d  mov     rcx, [rbp+phHash]; hHash
0x1800438a1  call    cs:__imp_BCryptHashData
0x1800438a8  nop     dword ptr [rax+rax+00h]
0x1800438ad  test    eax, eax
0x1800438af  jns     short loc_1800438B6
0x1800438b1  mov     rcx, r14
0x1800438b4  int     29h; Win8: RtlFailFast(ecx)
0x1800438b6  mov     rcx, [rbp+arg_18]
0x1800438ba  mov     rax, [rcx]
0x1800438bd  lea     rdx, [rbp+arg_0]
0x1800438c1  mov     rax, [rax+28h]
0x1800438c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800438ca  mov     ebx, eax
0x1800438cc  test    eax, eax
0x1800438ce  js      loc_180043983
0x1800438d4  mov     rcx, [rbp+pbInput]; pv
0x1800438d8  test    rcx, rcx
0x1800438db  jz      short loc_1800438EA
0x1800438dd  call    cs:__imp_CoTaskMemFree
0x1800438e4  nop     dword ptr [rax+rax+00h]
0x1800438e9  nop
0x1800438ea  mov     rcx, [rbp+var_18]
0x1800438ee  test    rcx, rcx
0x1800438f1  jz      short loc_180043900
0x1800438f3  mov     rax, [rcx]
0x1800438f6  mov     rax, [rax+10h]
0x1800438fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800438ff  nop
0x180043900  cmp     [rbp+arg_0], esi
0x180043903  jnz     loc_18004383F
0x180043909  test    rdi, rdi
0x18004390c  jz      short loc_180043931
0x18004390e  xor     r9d, r9d; dwFlags
0x180043911  lea     r8d, [r9+20h]; cbOutput
0x180043915  mov     rdx, rdi; pbOutput
0x180043918  mov     rcx, [rbp+phHash]; hHash
0x18004391c  call    cs:__imp_BCryptFinishHash
0x180043923  nop     dword ptr [rax+rax+00h]
0x180043928  test    eax, eax
0x18004392a  jns     short loc_180043931
0x18004392c  mov     rcx, r14
0x18004392f  int     29h; Win8: RtlFailFast(ecx)
0x180043931  mov     rcx, [rbp+phHash]; hHash
0x180043935  call    cs:__imp_BCryptDestroyHash
0x18004393c  nop     dword ptr [rax+rax+00h]
0x180043941  mov     rcx, rsi
0x180043944  mov     [rbp+phHash], rcx
0x180043948  mov     rdx, [rbp+arg_18]
0x18004394c  test    rdx, rdx
0x18004394f  jz      short loc_180043964
0x180043951  mov     rax, [rdx]
0x180043954  mov     rcx, rdx
0x180043957  mov     rax, [rax+10h]
0x18004395b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043960  mov     rcx, [rbp+phHash]; hHash
0x180043964  test    rcx, rcx
0x180043967  jz      short loc_180043975
0x180043969  call    cs:__imp_BCryptDestroyHash
0x180043970  nop     dword ptr [rax+rax+00h]
0x180043975  xor     eax, eax
0x180043977  add     rsp, 60h
0x18004397b  pop     r14
0x18004397d  pop     rdi
0x18004397e  pop     rsi
0x18004397f  pop     rbx
0x180043980  pop     rbp
0x180043981  retn
0x180043983  mov     rcx, [rbp+28h]; this
0x180043987  mov     r9d, ebx; char *
0x18004398a  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180043991  mov     edx, 7Bh ; '{'; void *
0x180043996  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004399b  nop
0x18004399c  mov     rcx, [rbp+pbInput]; pv
0x1800439a0  test    rcx, rcx
0x1800439a3  jz      short loc_1800439B2
0x1800439a5  call    cs:__imp_CoTaskMemFree
0x1800439ac  nop     dword ptr [rax+rax+00h]
0x1800439b1  nop
0x1800439b2  mov     rcx, [rbp+var_18]
0x1800439b6  test    rcx, rcx
0x1800439b9  jz      short loc_1800439C8
0x1800439bb  mov     rax, [rcx]
0x1800439be  mov     rax, [rax+10h]
0x1800439c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800439c7  nop
0x1800439c8  mov     rcx, [rbp+arg_18]
0x1800439cc  test    rcx, rcx
0x1800439cf  jz      short loc_1800439DE
0x1800439d1  mov     rax, [rcx]
0x1800439d4  mov     rax, [rax+10h]
0x1800439d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800439dd  nop
0x1800439de  jmp     loc_1800437D1
0x1800439e3  mov     rcx, [rbp+28h]; this
0x1800439e7  mov     r9d, ebx; char *
0x1800439ea  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800439f1  mov     edx, 77h ; 'w'; void *
0x1800439f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800439fb  nop
0x1800439fc  mov     rcx, [rbp+pbInput]; pv
0x180043a00  test    rcx, rcx
0x180043a03  jz      short loc_180043A12
0x180043a05  call    cs:__imp_CoTaskMemFree
0x180043a0c  nop     dword ptr [rax+rax+00h]
0x180043a11  nop
0x180043a12  mov     rcx, [rbp+var_18]
0x180043a16  test    rcx, rcx
0x180043a19  jz      short loc_180043A28
0x180043a1b  mov     rax, [rcx]
0x180043a1e  mov     rax, [rax+10h]
0x180043a22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043a27  nop
0x180043a28  mov     rcx, [rbp+arg_18]
0x180043a2c  test    rcx, rcx
0x180043a2f  jz      short loc_180043A3E
0x180043a31  mov     rax, [rcx]
0x180043a34  mov     rax, [rax+10h]
0x180043a38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043a3d  nop
0x180043a3e  jmp     loc_1800437D1
0x180043a43  mov     rcx, [rbp+28h]; this
0x180043a47  mov     r9d, ebx; char *
0x180043a4a  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180043a51  mov     edx, 73h ; 's'; void *
0x180043a56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043a5b  nop
0x180043a5c  mov     rcx, [rbp+var_18]
0x180043a60  test    rcx, rcx
0x180043a63  jz      short loc_180043A72
0x180043a65  mov     rax, [rcx]
0x180043a68  mov     rax, [rax+10h]
0x180043a6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043a71  nop
0x180043a72  mov     rcx, [rbp+arg_18]
0x180043a76  test    rcx, rcx
0x180043a79  jz      short loc_180043A88
0x180043a7b  mov     rax, [rcx]
0x180043a7e  mov     rax, [rax+10h]
0x180043a82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043a87  nop
0x180043a88  jmp     loc_1800437D1
```
