# Windows::FileSystem::ReFs::Md5Hasher::ComputeHash(std::span<uchar const,-1>)

- ea: `0x140025f8c`
- end: `0x1400260b6`
- name: `?ComputeHash@Md5Hasher@ReFs@FileSystem@Windows@@SA?AV?$array@E$0BA@@std@@V?$span@$$CBE$0?0@6@@Z`
- size: `298`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140028c90`
- `0x1400290f0`
- `0x14002954c`
- `0x14002be80`
- `0x14003d2a4`

## callees

- `0x140004870`
- `0x140018f7c`
- `0x140019130`
- `0x1400222d8`
- `0x1400244f8`
- `0x1400245f4`
- `0x140025f8c`
- `0x1400262d8`
- `0x14002c5b0`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x140025fce`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x140025fce`
- `bcrypt!BCryptHashData` at `0x140026044`
- `bcrypt!BCryptHashData` at `0x140026044`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_OWORD *__fastcall Windows::FileSystem::ReFs::Md5Hasher::ComputeHash(_OWORD *a1, __int64 a2)
{
  NTSTATUS v4; // eax
  int v5; // eax
  NTSTATUS v6; // eax
  ULONG cbInput; // [rsp+20h] [rbp-50h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+28h] [rbp-48h] BYREF
  _BYTE v10[32]; // [rsp+30h] [rbp-40h] BYREF
  BCRYPT_HASH_HANDLE hHash; // [rsp+50h] [rbp-20h]
  _BYTE v12[16]; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  phAlgorithm = 0;
  v4 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"MD5", 0, 0x20u);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x22,
      (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\SvcLib\\inc\\BCryptHelpers.h",
      (const char *)(unsigned int)v4,
      cbInput);
  Microsoft::Win32::BCryptHelpers::AlgorithmProvider::CreateHashingObject(&phAlgorithm, v10);
  cbInput = 0;
  v5 = LongLongToULong(*(_QWORD *)(a2 + 8), &cbInput);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4F,
      (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\SvcLib\\inc\\BCryptHelpers.h",
      (const char *)(unsigned int)v5,
      cbInput);
  v6 = BCryptHashData(hHash, *(PUCHAR *)a2, cbInput, 0);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x50,
      (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\SvcLib\\inc\\BCryptHelpers.h",
      (const char *)(unsigned int)v6,
      cbInput);
  *a1 = *(_OWORD *)Microsoft::Win32::BCryptHelpers::HashingObject::Finish<std::array<unsigned char,16>>(v10, v12);
  Microsoft::Win32::BCryptHelpers::HashingObject::~HashingObject((Microsoft::Win32::BCryptHelpers::HashingObject *)v10);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
  return a1;
}

```

## disassembly

```asm
0x140025f8c  mov     [rsp-8+arg_0], rbx
0x140025f91  mov     [rsp-8+arg_10], rdi
0x140025f96  push    rbp
0x140025f97  mov     rbp, rsp
0x140025f9a  sub     rsp, 70h
0x140025f9e  mov     rax, cs:__security_cookie
0x140025fa5  xor     rax, rsp
0x140025fa8  mov     [rbp+var_8], rax
0x140025fac  mov     rdi, rdx
0x140025faf  mov     rbx, rcx
0x140025fb2  mov     [rbp+phAlgorithm], 0
0x140025fba  mov     r9d, 20h ; ' '; dwFlags
0x140025fc0  xor     r8d, r8d; pszImplementation
0x140025fc3  lea     rdx, pszAlgId; "MD5"
0x140025fca  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x140025fce  call    cs:__imp_BCryptOpenAlgorithmProvider
0x140025fd5  nop     dword ptr [rax+rax+00h]
0x140025fda  mov     rcx, [rbp+8]; this
0x140025fde  test    eax, eax
0x140025fe0  jns     short loc_140025FF7
0x140025fe2  mov     r9d, eax; char *
0x140025fe5  lea     r8, aOnecoreBaseFsR_18; "onecore\\base\\fs\\refsdedupsvc\\SvcLib"...
0x140025fec  mov     edx, 22h ; '"'; void *
0x140025ff1  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x140025ff7  lea     rdx, [rbp+var_40]
0x140025ffb  lea     rcx, [rbp+phAlgorithm]
0x140025fff  call    ?CreateHashingObject@AlgorithmProvider@BCryptHelpers@Win32@Microsoft@@QEAA?AUHashingObject@234@K@Z; Microsoft::Win32::BCryptHelpers::AlgorithmProvider::CreateHashingObject(ulong)
0x140026004  nop
0x140026005  mov     [rbp+cbInput], 0
0x14002600c  lea     rdx, [rbp+cbInput]; unsigned int *
0x140026010  mov     rcx, [rdi+8]; __int64
0x140026014  call    ?LongLongToULong@@YAJ_JPEAK@Z; LongLongToULong(__int64,ulong *)
0x140026019  mov     rcx, [rbp+8]; this
0x14002601d  test    eax, eax
0x14002601f  jns     short loc_140026036
0x140026021  mov     r9d, eax; char *
0x140026024  lea     r8, aOnecoreBaseFsR_18; "onecore\\base\\fs\\refsdedupsvc\\SvcLib"...
0x14002602b  mov     edx, 4Fh ; 'O'; void *
0x140026030  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140026036  xor     r9d, r9d; dwFlags
0x140026039  mov     r8d, [rbp+cbInput]; cbInput
0x14002603d  mov     rdx, [rdi]; pbInput
0x140026040  mov     rcx, [rbp+hHash]; hHash
0x140026044  call    cs:__imp_BCryptHashData
0x14002604b  nop     dword ptr [rax+rax+00h]
0x140026050  mov     rcx, [rbp+8]; this
0x140026054  test    eax, eax
0x140026056  jns     short loc_14002606D
0x140026058  mov     r9d, eax; char *
0x14002605b  lea     r8, aOnecoreBaseFsR_18; "onecore\\base\\fs\\refsdedupsvc\\SvcLib"...
0x140026062  mov     edx, 50h ; 'P'; void *
0x140026067  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x14002606d  lea     rdx, [rbp+var_18]
0x140026071  lea     rcx, [rbp+var_40]
0x140026075  call    ??$Finish@V?$array@E$0BA@@std@@@HashingObject@BCryptHelpers@Win32@Microsoft@@QEAA?AV?$array@E$0BA@@std@@K@Z; Microsoft::Win32::BCryptHelpers::HashingObject::Finish<std::array<uchar,16>>(ulong)
0x14002607a  movups  xmm0, xmmword ptr [rax]
0x14002607d  movdqu  xmmword ptr [rbx], xmm0
0x140026081  lea     rcx, [rbp+var_40]; this
0x140026085  call    ??1HashingObject@BCryptHelpers@Win32@Microsoft@@QEAA@XZ; Microsoft::Win32::BCryptHelpers::HashingObject::~HashingObject(void)
0x14002608a  nop
0x14002608b  lea     rcx, [rbp+phAlgorithm]
0x14002608f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140026094  mov     rax, rbx
0x140026097  mov     rcx, [rbp+var_8]
0x14002609b  xor     rcx, rsp; StackCookie
0x14002609e  call    __security_check_cookie
0x1400260a3  lea     r11, [rsp+70h+var_s0]
0x1400260a8  mov     rbx, [r11+10h]
0x1400260ac  mov     rdi, [r11+20h]
0x1400260b0  mov     rsp, r11
0x1400260b3  pop     rbp
0x1400260b4  retn
```
