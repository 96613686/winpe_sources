# VsmUtils::TpmSecret::DeriveKey(ushort const *,_BCryptBufferDesc *,uchar *,ulong,ulong *,ulong)

- ea: `0x14005b28c`
- end: `0x14005b47c`
- name: `?DeriveKey@TpmSecret@VsmUtils@@QEAAJPEBGPEAU_BCryptBufferDesc@@PEAEKPEAKK@Z`
- size: `496`
- prototype: `int(VsmUtils::TpmSecret *__hidden this, const unsigned __int16 *, struct _BCryptBufferDesc *, unsigned __int8 *, unsigned int, unsigned int *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140057580`

## callees

- `0x14001044a`
- `0x1400104fc`
- `0x140010514`
- `0x14002bdcc`
- `0x140054f54`
- `0x140054f8c`
- `0x14005a6fc`
- `0x14005a7c4`
- `0x14005b28c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14005b312`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14005b34e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14005b312`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14005b34e`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x14005b387`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x14005b387`
- `bcrypt!BCryptDeriveKey` at `0x14005b405`
- `bcrypt!BCryptDeriveKey` at `0x14005b405`

## string_xrefs

- `0x14005b398`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmhelper.cpp`
- `0x14005b416`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall VsmUtils::TpmSecret::DeriveKey(
        VsmUtils::TpmSecret *this,
        const unsigned __int16 *a2,
        struct _BCryptBufferDesc *a3,
        unsigned __int8 *a4,
        ULONG a5,
        unsigned int *pcbResult,
        ULONG dwFlags)
{
  __int64 v10; // rbx
  _DWORD *v11; // r15
  __int64 v12; // rsi
  size_t v13; // rdi
  void *v14; // rcx
  size_t v15; // rbx
  const WCHAR *v16; // rbx
  NTSTATUS v17; // eax
  unsigned int v18; // ebx
  _DWORD *v19; // rdi
  volatile signed __int32 *v20; // rax
  NTSTATUS v21; // eax
  ULONG cbDerivedKey; // [rsp+20h] [rbp-40h]
  ULONG cbDerivedKeya; // [rsp+20h] [rbp-40h]
  BCRYPT_SECRET_HANDLE hSharedSecret; // [rsp+40h] [rbp-20h] BYREF
  _QWORD v26[3]; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+A0h] [rbp+40h] BYREF
  LPCWSTR pwszKDF; // [rsp+A8h] [rbp+48h]

  pwszKDF = a2;
  v10 = *((_QWORD *)this + 1) - *(_QWORD *)this;
  std::make_unique<unsigned char [0],0>(v26, v10 + 640);
  v11 = (_DWORD *)v26[0];
  *(_DWORD *)v26[0] = 640;
  v11[1] = 1297302851;
  v11[3] = *((_DWORD *)this + 2) - *(_DWORD *)this;
  v11[4] = *((_DWORD *)this + 2) - *(_DWORD *)this;
  v11[2] = 196618;
  v12 = *(_QWORD *)this;
  v13 = *((_QWORD *)this + 1) - *(_QWORD *)this;
  if ( !v13 )
    goto LABEL_11;
  v14 = v11 + 156;
  if ( v11 == (_DWORD *)-624LL )
    goto LABEL_3;
  v15 = v10 + 1;
  if ( v12 && v15 >= v13 )
  {
    memcpy_0(v14, *(const void **)this, v13);
    goto LABEL_11;
  }
  memset_0(v14, 0, v15);
  if ( !v12 )
  {
LABEL_3:
    *(_DWORD *)_o__errno() = 22;
  }
  else
  {
    if ( v15 >= v13 )
      goto LABEL_11;
    *(_DWORD *)_o__errno() = 34;
  }
  invalid_parameter_noinfo();
LABEL_11:
  phAlgorithm = 0;
  v16 = (const WCHAR *)*((_QWORD *)this + 3);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &phAlgorithm,
    0);
  v17 = BCryptOpenAlgorithmProvider(&phAlgorithm, v16, L"Microsoft Primitive Provider", 0);
  if ( v17 >= 0 )
  {
    std::make_unique<unsigned char [0],0>(&hSharedSecret, 24);
    v19 = hSharedSecret;
    *(_DWORD *)hSharedSecret = 24;
    v19[1] = 1431655764;
    *((_QWORD *)v19 + 1) = phAlgorithm;
    v20 = (volatile signed __int32 *)phAlgorithm;
    *((_QWORD *)v19 + 2) = v11;
    _InterlockedIncrement(v20 + 4);
    v21 = BCryptDeriveKey(v19, pwszKDF, a3, a4, a5, pcbResult, dwFlags);
    if ( v21 >= 0 )
    {
      _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)v19 + 1) + 16LL));
      std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(&hSharedSecret);
      v18 = 0;
    }
    else
    {
      v18 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x31C,
              (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmhelper.cpp",
              (const char *)(unsigned int)v21,
              cbDerivedKeya);
      _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)v19 + 1) + 16LL));
      std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(&hSharedSecret);
    }
  }
  else
  {
    v18 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x307,
            (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmhelper.cpp",
            (const char *)(unsigned int)v17,
            cbDerivedKey);
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
  std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(v26);
  return v18;
}

```

## disassembly

```asm
0x14005b28c  mov     [rsp-38h+arg_10], rbx
0x14005b291  mov     [rsp-38h+pwszKDF], rdx
0x14005b296  push    rbp
0x14005b297  push    rsi
0x14005b298  push    rdi
0x14005b299  push    r12
0x14005b29b  push    r13
0x14005b29d  push    r14
0x14005b29f  push    r15
0x14005b2a1  mov     rbp, rsp
0x14005b2a4  sub     rsp, 60h
0x14005b2a8  mov     r12, r9
0x14005b2ab  mov     r13, r8
0x14005b2ae  mov     r14, rcx
0x14005b2b1  mov     rbx, [rcx+8]
0x14005b2b5  sub     rbx, [rcx]
0x14005b2b8  lea     rdx, [rbx+280h]
0x14005b2bf  lea     rcx, [rbp+var_18]
0x14005b2c3  call    ??$make_unique@$$BY0A@E$0A@@std@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@0@_K@Z; std::make_unique<uchar [0],0>(unsigned __int64)
0x14005b2c8  nop
0x14005b2c9  mov     r15, [rbp+var_18]
0x14005b2cd  mov     dword ptr [r15], 280h
0x14005b2d4  mov     dword ptr [r15+4], 4D534543h
0x14005b2dc  mov     eax, [r14+8]
0x14005b2e0  sub     eax, [r14]
0x14005b2e3  mov     [r15+0Ch], eax
0x14005b2e7  mov     eax, [r14+8]
0x14005b2eb  sub     eax, [r14]
0x14005b2ee  mov     [r15+10h], eax
0x14005b2f2  mov     dword ptr [r15+8], 3000Ah
0x14005b2fa  mov     rsi, [r14]
0x14005b2fd  mov     rdi, [r14+8]
0x14005b301  sub     rdi, rsi
0x14005b304  jz      short loc_14005B35F
0x14005b306  lea     rcx, [r15+270h]; void *
0x14005b30d  test    rcx, rcx
0x14005b310  jnz     short loc_14005B320
0x14005b312  call    cs:__imp__o__errno
0x14005b318  mov     dword ptr [rax], 16h
0x14005b31e  jmp     short loc_14005B35A
0x14005b320  inc     rbx
0x14005b323  test    rsi, rsi
0x14005b326  jz      short loc_14005B33A
0x14005b328  cmp     rbx, rdi
0x14005b32b  jb      short loc_14005B33A
0x14005b32d  mov     r8, rdi; Size
0x14005b330  mov     rdx, rsi; Src
0x14005b333  call    memcpy_0
0x14005b338  jmp     short loc_14005B35F
0x14005b33a  mov     r8, rbx; Size
0x14005b33d  xor     edx, edx; Val
0x14005b33f  call    memset_0
0x14005b344  test    rsi, rsi
0x14005b347  jz      short loc_14005B312
0x14005b349  cmp     rbx, rdi
0x14005b34c  jnb     short loc_14005B35F
0x14005b34e  call    cs:__imp__o__errno
0x14005b354  mov     dword ptr [rax], 22h ; '"'
0x14005b35a  call    _invalid_parameter_noinfo
0x14005b35f  mov     [rbp+phAlgorithm], 0
0x14005b367  mov     rbx, [r14+18h]
0x14005b36b  xor     edx, edx
0x14005b36d  lea     rcx, [rbp+phAlgorithm]
0x14005b371  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x14005b376  xor     r9d, r9d; dwFlags
0x14005b379  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x14005b380  mov     rdx, rbx; pszAlgId
0x14005b383  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x14005b387  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14005b38d  test    eax, eax
0x14005b38f  jns     short loc_14005B3B0
0x14005b391  mov     rcx, [rbp+38h]; this
0x14005b395  mov     r9d, eax; char *
0x14005b398  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\trustlet\\utils"...
0x14005b39f  mov     edx, 307h; void *
0x14005b3a4  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x14005b3a9  mov     ebx, eax
0x14005b3ab  jmp     loc_14005B44F
0x14005b3b0  mov     ebx, 18h
0x14005b3b5  mov     edx, ebx
0x14005b3b7  lea     rcx, [rbp+hSharedSecret]
0x14005b3bb  call    ??$make_unique@$$BY0A@E$0A@@std@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@0@_K@Z; std::make_unique<uchar [0],0>(unsigned __int64)
0x14005b3c0  mov     rdi, [rbp+hSharedSecret]
0x14005b3c4  mov     [rdi], ebx
0x14005b3c6  mov     dword ptr [rdi+4], 55555554h
0x14005b3cd  mov     rax, [rbp+phAlgorithm]
0x14005b3d1  mov     [rdi+8], rax
0x14005b3d5  mov     rax, [rbp+phAlgorithm]
0x14005b3d9  mov     [rdi+10h], r15
0x14005b3dd  lock inc dword ptr [rax+10h]
0x14005b3e1  mov     eax, [rbp+arg_30]
0x14005b3e4  mov     [rsp+60h+dwFlags], eax; dwFlags
0x14005b3e8  mov     rax, [rbp+arg_28]
0x14005b3ec  mov     [rsp+60h+pcbResult], rax; pcbResult
0x14005b3f1  mov     eax, [rbp+arg_20]
0x14005b3f4  mov     [rsp+60h+cbDerivedKey], eax; int
0x14005b3f8  mov     r9, r12; pbDerivedKey
0x14005b3fb  mov     r8, r13; pParameterList
0x14005b3fe  mov     rdx, [rbp+pwszKDF]; pwszKDF
0x14005b402  mov     rcx, rdi; hSharedSecret
0x14005b405  call    cs:__imp_BCryptDeriveKey
0x14005b40b  test    eax, eax
0x14005b40d  jns     short loc_14005B43C
0x14005b40f  mov     rcx, [rbp+38h]; this
0x14005b413  mov     r9d, eax; char *
0x14005b416  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\trustlet\\utils"...
0x14005b41d  mov     edx, 31Ch; void *
0x14005b422  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x14005b427  mov     ebx, eax
0x14005b429  mov     rcx, [rdi+8]
0x14005b42d  lock dec dword ptr [rcx+10h]
0x14005b431  lea     rcx, [rbp+hSharedSecret]
0x14005b435  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x14005b43a  jmp     short loc_14005B44F
0x14005b43c  mov     rax, [rdi+8]
0x14005b440  lock dec dword ptr [rax+10h]
0x14005b444  lea     rcx, [rbp+hSharedSecret]
0x14005b448  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x14005b44d  xor     ebx, ebx
0x14005b44f  lea     rcx, [rbp+phAlgorithm]
0x14005b453  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14005b458  nop
0x14005b459  lea     rcx, [rbp+var_18]
0x14005b45d  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x14005b462  mov     eax, ebx
0x14005b464  mov     rbx, [rsp+60h+arg_10]
0x14005b46c  add     rsp, 60h
0x14005b470  pop     r15
0x14005b472  pop     r14
0x14005b474  pop     r13
0x14005b476  pop     r12
0x14005b478  pop     rdi
0x14005b479  pop     rsi
0x14005b47a  pop     rbp
0x14005b47b  retn
```
