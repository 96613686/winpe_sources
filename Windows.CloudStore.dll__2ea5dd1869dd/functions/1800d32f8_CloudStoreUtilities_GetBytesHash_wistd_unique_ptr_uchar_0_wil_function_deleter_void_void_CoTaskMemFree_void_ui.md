# CloudStoreUtilities::GetBytesHash(wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&,uint,char const *,std::optional<CloudStoreUtilities::HashEncoding>)

- ea: `0x1800d32f8`
- end: `0x1800d3505`
- name: `?GetBytesHash@CloudStoreUtilities@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$$QEAV?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@IPEBDV?$optional@W4HashEncoding@CloudStoreUtilities@@@3@@Z`
- size: `525`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800d2858`
- `0x1800d3e4c`

## callees

- `0x180016cf4`
- `0x18002c020`
- `0x18004ee74`
- `0x1800d32f8`
- `0x1800d3518`
- `0x1800d3534`
- `0x1800d3824`
- `0x1800d9764`
- `0x1801201a0`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x1800d3394`
- `bcrypt!BCryptCreateHash` at `0x1800d3394`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800d3342`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800d3342`
- `bcrypt!BCryptDestroyHash` at `0x1800d34d8`
- `bcrypt!BCryptDestroyHash` at `0x1800d34d8`
- `bcrypt!BCryptHashData` at `0x1800d33c4`
- `bcrypt!BCryptHashData` at `0x1800d3404`
- `bcrypt!BCryptHashData` at `0x1800d33c4`
- `bcrypt!BCryptHashData` at `0x1800d3404`
- `bcrypt!BCryptFinishHash` at `0x1800d3439`
- `bcrypt!BCryptFinishHash` at `0x1800d3439`

## string_xrefs

- `0x1800d3353`: `onecoreuap\shell\cloudstore\common\src\cloudstoreutilities.cpp`
- `0x1800d33a5`: `onecoreuap\shell\cloudstore\common\src\cloudstoreutilities.cpp`
- `0x1800d33d5`: `onecoreuap\shell\cloudstore\common\src\cloudstoreutilities.cpp`
- `0x1800d3415`: `onecoreuap\shell\cloudstore\common\src\cloudstoreutilities.cpp`
- `0x1800d344a`: `onecoreuap\shell\cloudstore\common\src\cloudstoreutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CloudStoreUtilities::GetBytesHash(__int64 a1, PUCHAR *a2, ULONG a3, UCHAR *a4, __int64 a5)
{
  NTSTATUS v9; // eax
  NTSTATUS v10; // eax
  NTSTATUS v11; // eax
  __int64 v12; // r8
  NTSTATUS v13; // eax
  NTSTATUS v14; // eax
  __int64 v15; // rax
  int pbSecret; // [rsp+20h] [rbp-51h]
  int pbSecreta; // [rsp+20h] [rbp-51h]
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-31h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm[2]; // [rsp+48h] [rbp-29h] BYREF
  _BYTE v21[8]; // [rsp+58h] [rbp-19h] BYREF
  _BYTE v22[16]; // [rsp+60h] [rbp-11h] BYREF
  UCHAR pbOutput[32]; // [rsp+70h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+57h]

  phAlgorithm[0] = 0;
  v9 = BCryptOpenAlgorithmProvider(phAlgorithm, L"SHA256", 0, 0);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x63E,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\cloudstoreutilities.cpp",
      (const char *)(unsigned int)v9,
      pbSecret);
  phHash = 0;
  v10 = BCryptCreateHash(phAlgorithm[0], &phHash, 0, 0, 0, 0, 0);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x641,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\cloudstoreutilities.cpp",
      (const char *)(unsigned int)v10,
      pbSecreta);
  v11 = BCryptHashData(phHash, *a2, a3, 0);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x643,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\cloudstoreutilities.cpp",
      (const char *)(unsigned int)v11,
      pbSecreta);
  if ( a4 )
  {
    v12 = -1;
    do
      ++v12;
    while ( a4[v12] );
    v13 = BCryptHashData(phHash, a4, v12, 0);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x64A,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\cloudstoreutilities.cpp",
        (const char *)(unsigned int)v13,
        pbSecreta);
  }
  v14 = BCryptFinishHash(phHash, pbOutput, 0x20u, 0);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x64E,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\cloudstoreutilities.cpp",
      (const char *)(unsigned int)v14,
      pbSecreta);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AadAssets>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AadAssets>::GetImpl'::`2'::impl)
    && BYTE4(a5)
    && (_DWORD)a5 == 1 )
  {
    Windows::Internal::Storage::Cloud::Common::HexEncodeLowercaseA(a1, pbOutput);
  }
  else
  {
    v15 = bond::blob::blob((bond::blob *)v21, pbOutput, 0x20u);
    Base64Encode(a1, v15);
    boost::detail::shared_count::~shared_count((boost::detail::shared_count *)v22);
  }
  if ( phHash )
    BCryptDestroyHash(phHash);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(phAlgorithm);
  return a1;
}

```

## disassembly

```asm
0x1800d32f8  push    rbp
0x1800d32fa  push    rbx
0x1800d32fb  push    rsi
0x1800d32fc  push    rdi
0x1800d32fd  push    r14
0x1800d32ff  lea     rbp, [rsp-2Fh]
0x1800d3304  sub     rsp, 0A0h
0x1800d330b  mov     rax, cs:__security_cookie
0x1800d3312  xor     rax, rsp
0x1800d3315  mov     [rbp+4Fh+var_30], rax
0x1800d3319  mov     rdi, r9
0x1800d331c  mov     r14d, r8d
0x1800d331f  mov     rsi, rdx
0x1800d3322  mov     rbx, rcx
0x1800d3325  mov     [rbp+4Fh+phAlgorithm], rcx
0x1800d3329  mov     [rbp+4Fh+phAlgorithm], 0
0x1800d3331  xor     r9d, r9d; dwFlags
0x1800d3334  xor     r8d, r8d; pszImplementation
0x1800d3337  lea     rdx, pszAlgId; "SHA256"
0x1800d333e  lea     rcx, [rbp+4Fh+phAlgorithm]; phAlgorithm
0x1800d3342  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800d3348  mov     rcx, [rbp+57h]; this
0x1800d334c  test    eax, eax
0x1800d334e  jns     short loc_1800D3365
0x1800d3350  mov     r9d, eax; char *
0x1800d3353  lea     r8, aOnecoreuapShel_101; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800d335a  mov     edx, 63Eh; void *
0x1800d335f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800d3365  mov     [rbp+4Fh+phHash], 0
0x1800d336d  mov     [rsp+0C0h+dwFlags], 0; dwFlags
0x1800d3375  mov     [rsp+0C0h+cbSecret], 0; cbSecret
0x1800d337d  mov     [rsp+0C0h+pbSecret], 0; int
0x1800d3386  xor     r9d, r9d; cbHashObject
0x1800d3389  xor     r8d, r8d; pbHashObject
0x1800d338c  lea     rdx, [rbp+4Fh+phHash]; phHash
0x1800d3390  mov     rcx, [rbp+4Fh+phAlgorithm]; hAlgorithm
0x1800d3394  call    cs:__imp_BCryptCreateHash
0x1800d339a  mov     rcx, [rbp+57h]; this
0x1800d339e  test    eax, eax
0x1800d33a0  jns     short loc_1800D33B7
0x1800d33a2  mov     r9d, eax; char *
0x1800d33a5  lea     r8, aOnecoreuapShel_101; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800d33ac  mov     edx, 641h; void *
0x1800d33b1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800d33b7  xor     r9d, r9d; dwFlags
0x1800d33ba  mov     r8d, r14d; cbInput
0x1800d33bd  mov     rdx, [rsi]; pbInput
0x1800d33c0  mov     rcx, [rbp+4Fh+phHash]; hHash
0x1800d33c4  call    cs:__imp_BCryptHashData
0x1800d33ca  mov     rcx, [rbp+57h]; this
0x1800d33ce  test    eax, eax
0x1800d33d0  jns     short loc_1800D33E7
0x1800d33d2  mov     r9d, eax; char *
0x1800d33d5  lea     r8, aOnecoreuapShel_101; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800d33dc  mov     edx, 643h; void *
0x1800d33e1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800d33e7  test    rdi, rdi
0x1800d33ea  jz      short loc_1800D3427
0x1800d33ec  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800d33f0  inc     r8; cbInput
0x1800d33f3  cmp     byte ptr [rdi+r8], 0
0x1800d33f8  jnz     short loc_1800D33F0
0x1800d33fa  xor     r9d, r9d; dwFlags
0x1800d33fd  mov     rdx, rdi; pbInput
0x1800d3400  mov     rcx, [rbp+4Fh+phHash]; hHash
0x1800d3404  call    cs:__imp_BCryptHashData
0x1800d340a  mov     rcx, [rbp+57h]; this
0x1800d340e  test    eax, eax
0x1800d3410  jns     short loc_1800D3427
0x1800d3412  mov     r9d, eax; char *
0x1800d3415  lea     r8, aOnecoreuapShel_101; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800d341c  mov     edx, 64Ah; void *
0x1800d3421  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800d3427  xor     r9d, r9d; dwFlags
0x1800d342a  lea     edi, [r9+20h]
0x1800d342e  mov     r8d, edi; cbOutput
0x1800d3431  lea     rdx, [rbp+4Fh+pbOutput]; pbOutput
0x1800d3435  mov     rcx, [rbp+4Fh+phHash]; hHash
0x1800d3439  call    cs:__imp_BCryptFinishHash
0x1800d343f  mov     rcx, [rbp+57h]; this
0x1800d3443  test    eax, eax
0x1800d3445  jns     short loc_1800D345C
0x1800d3447  mov     r9d, eax; char *
0x1800d344a  lea     r8, aOnecoreuapShel_101; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800d3451  mov     edx, 64Eh; void *
0x1800d3456  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800d345c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AadAssets@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AadAssets@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AadAssets> `wil::Feature<__WilFeatureTraits_Feature_AadAssets>::GetImpl(void)'::`2'::impl
0x1800d3463  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AadAssets@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AadAssets>::__private_IsEnabled(void)
0x1800d3468  test    al, al
0x1800d346a  jz      short loc_1800D34A8
0x1800d346c  cmp     [rbp+4Fh+arg_24], 0
0x1800d3473  jz      short loc_1800D3489
0x1800d3475  cmp     [rbp+4Fh+arg_20], 1
0x1800d3479  jnz     short loc_1800D3489
0x1800d347b  lea     rdx, [rbp+4Fh+pbOutput]
0x1800d347f  mov     rcx, rbx
0x1800d3482  call    ?HexEncodeLowercaseA@Common@Cloud@Storage@Internal@Windows@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBE_K@Z; Windows::Internal::Storage::Cloud::Common::HexEncodeLowercaseA(uchar const *,unsigned __int64)
0x1800d3487  jmp     short loc_1800D34CF
0x1800d3489  mov     r8d, edi; unsigned int
0x1800d348c  lea     rdx, [rbp+4Fh+pbOutput]; void *
0x1800d3490  lea     rcx, [rbp+4Fh+var_68]; this
0x1800d3494  call    ??0blob@bond@@QEAA@PEBXI@Z; bond::blob::blob(void const *,uint)
0x1800d3499  nop
0x1800d349a  mov     rdx, rax
0x1800d349d  mov     rcx, rbx
0x1800d34a0  call    ?Base64Encode@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBVblob@bond@@@Z; Base64Encode(bond::blob const &)
0x1800d34a5  nop
0x1800d34a6  jmp     short loc_1800D34C5
0x1800d34a8  mov     r8d, edi; unsigned int
0x1800d34ab  lea     rdx, [rbp+4Fh+pbOutput]; void *
0x1800d34af  lea     rcx, [rbp+4Fh+var_68]; this
0x1800d34b3  call    ??0blob@bond@@QEAA@PEBXI@Z; bond::blob::blob(void const *,uint)
0x1800d34b8  nop
0x1800d34b9  mov     rdx, rax
0x1800d34bc  mov     rcx, rbx
0x1800d34bf  call    ?Base64Encode@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBVblob@bond@@@Z; Base64Encode(bond::blob const &)
0x1800d34c4  nop
0x1800d34c5  lea     rcx, [rbp+4Fh+var_60]; this
0x1800d34c9  call    ??1shared_count@detail@boost@@QEAA@XZ; boost::detail::shared_count::~shared_count(void)
0x1800d34ce  nop
0x1800d34cf  mov     rcx, [rbp+4Fh+phHash]; hHash
0x1800d34d3  test    rcx, rcx
0x1800d34d6  jz      short loc_1800D34DF
0x1800d34d8  call    cs:__imp_BCryptDestroyHash
0x1800d34de  nop
0x1800d34df  lea     rcx, [rbp+4Fh+phAlgorithm]
0x1800d34e3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800d34e8  mov     rax, rbx
0x1800d34eb  mov     rcx, [rbp+4Fh+var_30]
0x1800d34ef  xor     rcx, rsp; StackCookie
0x1800d34f2  call    __security_check_cookie
0x1800d34f7  add     rsp, 0A0h
0x1800d34fe  pop     r14
0x1800d3500  pop     rdi
0x1800d3501  pop     rsi
0x1800d3502  pop     rbx
0x1800d3503  pop     rbp
0x1800d3504  retn
```
