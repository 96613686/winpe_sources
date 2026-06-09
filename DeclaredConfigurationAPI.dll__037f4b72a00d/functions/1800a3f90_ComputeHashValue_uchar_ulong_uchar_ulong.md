# ComputeHashValue(uchar *,ulong,uchar * *,ulong)

- ea: `0x1800a3f90`
- end: `0x1800a411b`
- name: `?ComputeHashValue@@YAJPEAEKPEAPEAEK@Z`
- size: `395`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput, unsigned __int8 **, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a4124`

## callees

- `0x18000b9e0`
- `0x18000bf4c`
- `0x1800117dc`
- `0x1800a2f04`
- `0x1800a2f24`
- `0x1800a3f90`
- `0x1800a7090`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800a3fd1`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800a3fd1`
- `bcrypt!BCryptHashData` at `0x1800a405a`
- `bcrypt!BCryptHashData` at `0x1800a405a`
- `bcrypt!BCryptCreateHash` at `0x1800a4022`
- `bcrypt!BCryptCreateHash` at `0x1800a4022`
- `bcrypt!BCryptFinishHash` at `0x1800a4085`
- `bcrypt!BCryptFinishHash` at `0x1800a4085`

## string_xrefs

- `0x1800a40b3`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcutils.cpp`

## pseudocode

```c
__int64 __fastcall ComputeHashValue(PUCHAR pbInput, ULONG cbInput, unsigned __int8 **a3)
{
  NTSTATUS v6; // eax
  unsigned int v7; // r8d
  unsigned int v8; // ebx
  NTSTATUS v9; // eax
  unsigned int v10; // r8d
  __int64 v11; // rdx
  unsigned __int8 *v12; // rax
  __int64 i; // rdx
  int pbSecret; // [rsp+20h] [rbp-60h]
  int pbSecreta; // [rsp+20h] [rbp-60h]
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-40h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-38h] BYREF
  UCHAR pbOutput[16]; // [rsp+50h] [rbp-30h] BYREF
  __int128 v20; // [rsp+60h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  phAlgorithm = 0;
  v6 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0);
  if ( v6 < 0 )
  {
    v8 = wil::details::in1diag3::Return_NtStatus(retaddr, (void *)0x80C, v7, (const char *)(unsigned int)v6, pbSecret);
    goto LABEL_16;
  }
  phHash = 0;
  v9 = BCryptCreateHash(phAlgorithm, &phHash, 0, 0, 0, 0, 0);
  if ( v9 < 0 )
  {
    v11 = 2063;
LABEL_5:
    v8 = wil::details::in1diag3::Return_NtStatus(retaddr, (void *)v11, v10, (const char *)(unsigned int)v9, pbSecreta);
LABEL_6:
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phHash);
    goto LABEL_16;
  }
  v9 = BCryptHashData(phHash, pbInput, cbInput, 0);
  if ( v9 < 0 )
  {
    v11 = 2064;
    goto LABEL_5;
  }
  *(_OWORD *)pbOutput = 0;
  v20 = 0;
  v9 = BCryptFinishHash(phHash, pbOutput, 0x20u, 0);
  if ( v9 < 0 )
  {
    v11 = 2067;
    goto LABEL_5;
  }
  v12 = (unsigned __int8 *)operator new[](0x10u, (const struct std::nothrow_t *)std::nothrow);
  *a3 = v12;
  if ( !v12 )
  {
    v8 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x816,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcutils.cpp",
      (const char *)0x8007000ELL,
      pbSecreta);
    goto LABEL_6;
  }
  for ( i = 0; i != 16; ++i )
    (*a3)[i] = pbOutput[i];
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phHash);
  v8 = 0;
LABEL_16:
  wil::details::unique_storage_wil::details::resource_policy_void___void____cdecl___void_____CloseBCryptCloseAlgorithmProvider_wistd::integral_constant_unsigned___int64_0__void___void___0_std::nullptr_t___::_unique_storage_wil::details::resource_policy_void___void____cdecl___void_____CloseBCryptCloseAlgorithmProvider_wistd::integral_constant_unsigned___int64_0__void___void___0_std::nullptr_t___(&phAlgorithm);
  return v8;
}

```

## disassembly

```asm
0x1800a3f90  mov     [rsp-18h+arg_18], rbx
0x1800a3f95  push    rbp
0x1800a3f96  push    rsi
0x1800a3f97  push    rdi
0x1800a3f98  mov     rbp, rsp
0x1800a3f9b  sub     rsp, 80h
0x1800a3fa2  mov     rax, cs:__security_cookie
0x1800a3fa9  xor     rax, rsp
0x1800a3fac  mov     [rbp+var_10], rax
0x1800a3fb0  mov     rbx, r8
0x1800a3fb3  mov     [rbp+phAlgorithm], 0
0x1800a3fbb  mov     esi, edx
0x1800a3fbd  mov     rdi, rcx
0x1800a3fc0  xor     r8d, r8d; pszImplementation
0x1800a3fc3  lea     rdx, pszAlgId; "SHA256"
0x1800a3fca  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x1800a3fce  xor     r9d, r9d; dwFlags
0x1800a3fd1  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800a3fd7  test    eax, eax
0x1800a3fd9  jns     short loc_1800A3FF3
0x1800a3fdb  mov     rcx, [rbp+18h]; this
0x1800a3fdf  mov     r9d, eax; char *
0x1800a3fe2  mov     edx, 80Ch; void *
0x1800a3fe7  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800a3fec  mov     ebx, eax
0x1800a3fee  jmp     loc_1800A40F1
0x1800a3ff3  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1800a3ff7  lea     rdx, [rbp+phHash]; phHash
0x1800a3ffb  mov     [rsp+80h+dwFlags], 0; dwFlags
0x1800a4003  xor     r9d, r9d; cbHashObject
0x1800a4006  mov     [rsp+80h+cbSecret], 0; cbSecret
0x1800a400e  xor     r8d, r8d; pbHashObject
0x1800a4011  mov     [rsp+80h+pbSecret], 0; int
0x1800a401a  mov     [rbp+phHash], 0
0x1800a4022  call    cs:__imp_BCryptCreateHash
0x1800a4028  test    eax, eax
0x1800a402a  jns     short loc_1800A404D
0x1800a402c  mov     edx, 80Fh; void *
0x1800a4031  mov     rcx, [rbp+18h]; this
0x1800a4035  mov     r9d, eax; char *
0x1800a4038  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800a403d  mov     ebx, eax
0x1800a403f  lea     rcx, [rbp+phHash]
0x1800a4043  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800a4048  jmp     loc_1800A40F1
0x1800a404d  mov     rcx, [rbp+phHash]; hHash
0x1800a4051  xor     r9d, r9d; dwFlags
0x1800a4054  mov     r8d, esi; cbInput
0x1800a4057  mov     rdx, rdi; pbInput
0x1800a405a  call    cs:__imp_BCryptHashData
0x1800a4060  test    eax, eax
0x1800a4062  jns     short loc_1800A406B
0x1800a4064  mov     edx, 810h
0x1800a4069  jmp     short loc_1800A4031
0x1800a406b  mov     rcx, [rbp+phHash]; hHash
0x1800a406f  lea     rdx, [rbp+pbOutput]; pbOutput
0x1800a4073  xorps   xmm0, xmm0
0x1800a4076  xor     r9d, r9d; dwFlags
0x1800a4079  movups  xmmword ptr [rbp+pbOutput], xmm0
0x1800a407d  movups  [rbp+var_20], xmm0
0x1800a4081  lea     r8d, [r9+20h]; cbOutput
0x1800a4085  call    cs:__imp_BCryptFinishHash
0x1800a408b  test    eax, eax
0x1800a408d  jns     short loc_1800A4096
0x1800a408f  mov     edx, 813h
0x1800a4094  jmp     short loc_1800A4031
0x1800a4096  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800a409d  mov     ecx, 10h; unsigned __int64
0x1800a40a2  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800a40a7  mov     [rbx], rax
0x1800a40aa  test    rax, rax
0x1800a40ad  jnz     short loc_1800A40D1
0x1800a40af  mov     rcx, [rbp+18h]; this
0x1800a40b3  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800a40ba  mov     ebx, 8007000Eh
0x1800a40bf  mov     edx, 816h; void *
0x1800a40c4  mov     r9d, ebx; char *
0x1800a40c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a40cc  jmp     loc_1800A403F
0x1800a40d1  xor     edx, edx
0x1800a40d3  mov     al, [rbp+rdx+pbOutput]
0x1800a40d7  mov     rcx, [rbx]
0x1800a40da  mov     [rdx+rcx], al
0x1800a40dd  inc     rdx
0x1800a40e0  cmp     rdx, 10h
0x1800a40e4  jnz     short loc_1800A40D3
0x1800a40e6  lea     rcx, [rbp+phHash]
0x1800a40ea  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800a40ef  xor     ebx, ebx
0x1800a40f1  lea     rcx, [rbp+phAlgorithm]
0x1800a40f5  call    wil__details__unique_storage_wil__details__resource_policy_void___void____cdecl___void_____CloseBCryptCloseAlgorithmProvider_wistd__integral_constant_unsigned___int64_0__void___void___0_std__nullptr_t______unique_storage_wil__details__resource_policy_void___void____cdecl___void_____CloseBCryptCloseAlgorithmProvider_wistd__integral_constant_unsigned___int64_0__void___void___0_std__nullptr_t___
0x1800a40fa  mov     eax, ebx
0x1800a40fc  mov     rcx, [rbp+var_10]
0x1800a4100  xor     rcx, rsp; StackCookie
0x1800a4103  call    __security_check_cookie
0x1800a4108  mov     rbx, [rsp+80h+arg_18]
0x1800a4110  add     rsp, 80h
0x1800a4117  pop     rdi
0x1800a4118  pop     rsi
0x1800a4119  pop     rbp
0x1800a411a  retn
```
