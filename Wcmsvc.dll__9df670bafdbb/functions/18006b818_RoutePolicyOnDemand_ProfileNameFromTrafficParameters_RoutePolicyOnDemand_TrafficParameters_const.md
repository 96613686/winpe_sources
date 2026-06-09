# RoutePolicyOnDemand::ProfileNameFromTrafficParameters(RoutePolicyOnDemand::TrafficParameters const &)

- ea: `0x18006b818`
- end: `0x18006bbca`
- name: `?ProfileNameFromTrafficParameters@RoutePolicyOnDemand@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUTrafficParameters@1@@Z`
- size: `946`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800a639c`

## callees

- `0x180013afc`
- `0x18001c11c`
- `0x18002706c`
- `0x18002ab74`
- `0x18003a08c`
- `0x18006ad78`
- `0x18006b818`
- `0x18006bd0c`
- `0x18006be78`
- `0x18006be98`
- `0x18006bfe4`
- `0x18006c000`
- `0x18006c020`
- `0x180084f50`
- `0x180085460`
- `0x180085bc4`
- `0x1800a2b8c`
- `0x1800a97a0`

## import_xrefs

- `RPCRT4!UuidToStringW` at `0x18006bb04`
- `RPCRT4!UuidToStringW` at `0x18006bb04`
- `RPCRT4!RpcStringFreeW` at `0x18006bb93`
- `RPCRT4!RpcStringFreeW` at `0x18006bb93`
- `RPCRT4!UuidCreate` at `0x18006bb30`
- `RPCRT4!UuidCreate` at `0x18006bb30`
- `bcrypt!BCryptFinishHash` at `0x18006bab8`
- `bcrypt!BCryptFinishHash` at `0x18006bab8`
- `bcrypt!BCryptCreateHash` at `0x18006ba4a`
- `bcrypt!BCryptCreateHash` at `0x18006ba4a`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18006b991`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18006b991`
- `bcrypt!BCryptGetProperty` at `0x18006b9df`
- `bcrypt!BCryptGetProperty` at `0x18006b9df`
- `bcrypt!BCryptHashData` at `0x18006ba86`
- `bcrypt!BCryptHashData` at `0x18006ba86`

## string_xrefs

- `0x18006b906`: `onecoreuap\net\wcm\service\base\server\routepolicyondemand.cpp`
- `0x18006b93e`: `onecoreuap\net\wcm\service\base\server\routepolicyondemand.cpp`
- `0x18006b96a`: `onecoreuap\net\wcm\service\base\server\routepolicyondemand.cpp`
- `0x18006b9a2`: `onecoreuap\net\wcm\service\base\server\routepolicyondemand.cpp`
- `0x18006b9f0`: `onecoreuap\net\wcm\service\base\server\routepolicyondemand.cpp`
- `0x18006ba5b`: `onecoreuap\net\wcm\service\base\server\routepolicyondemand.cpp`
- `0x18006ba97`: `onecoreuap\net\wcm\service\base\server\routepolicyondemand.cpp`
- `0x18006bac9`: `onecoreuap\net\wcm\service\base\server\routepolicyondemand.cpp`
- `0x18006bb15`: `onecoreuap\net\wcm\service\base\server\routepolicyondemand.cpp`
- `0x18006bb41`: `onecoreuap\net\wcm\service\base\server\routepolicyondemand.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void *__fastcall RoutePolicyOnDemand::ProfileNameFromTrafficParameters(void *Src, __int64 a2)
{
  _WORD *v4; // rdx
  int v5; // esi
  int v6; // eax
  ULONG v7; // edx
  ULONG v8; // eax
  ULONG v9; // r8d
  const char *v10; // r9
  int v11; // eax
  NTSTATUS v12; // eax
  NTSTATUS Property; // eax
  unsigned int v14; // ebx
  void *v15; // rdi
  NTSTATUS v16; // eax
  UCHAR *v17; // rdx
  NTSTATUS v18; // eax
  NTSTATUS v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  __int64 v22; // r8
  unsigned int pcbResult; // [rsp+20h] [rbp-99h]
  int pcbResulta; // [rsp+20h] [rbp-99h]
  ULONG cbInput; // [rsp+40h] [rbp-79h] BYREF
  int v27; // [rsp+44h] [rbp-75h]
  void *v28; // [rsp+48h] [rbp-71h]
  UCHAR pbOutput[4]; // [rsp+50h] [rbp-69h] BYREF
  RPC_WSTR StringUuid; // [rsp+58h] [rbp-61h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+60h] [rbp-59h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+68h] [rbp-51h] BYREF
  ULONG v33; // [rsp+70h] [rbp-49h] BYREF
  RPC_WSTR *p_StringUuid; // [rsp+78h] [rbp-41h] BYREF
  char v35; // [rsp+80h] [rbp-39h]
  UCHAR v36[16]; // [rsp+88h] [rbp-31h] BYREF
  PUCHAR pbInput[2]; // [rsp+98h] [rbp-21h] BYREF
  __int64 v38; // [rsp+A8h] [rbp-11h]
  unsigned __int64 v39; // [rsp+B0h] [rbp-9h]
  _BYTE v40[6]; // [rsp+E2h] [rbp+29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v28 = Src;
  v27 = 0;
  if ( *(int *)(a2 + 80) >= 0 )
  {
    v4 = (_WORD *)std::_UIntegral_to_buff<unsigned short,unsigned int>(v40);
  }
  else
  {
    v4 = (_WORD *)(std::_UIntegral_to_buff<unsigned short,unsigned int>(v40) - 2);
    *v4 = 45;
  }
  std::wstring::wstring(pbInput, v4, v40);
  v5 = 6;
  v27 = 6;
  if ( *(_BYTE *)(a2 + 72) )
  {
    std::optional<std::wstring>::value(a2 + 40);
    std::wstring::_Append<unsigned short>(pbInput);
  }
  if ( *(_BYTE *)(a2 + 32) )
  {
    std::optional<std::wstring>::value(a2);
    std::wstring::_Append<unsigned short>(pbInput);
  }
  *(_OWORD *)v36 = 0;
  if ( v38 )
  {
    cbInput = 0;
    v6 = LongLongToULong(v38, &cbInput);
    if ( v6 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x7AA,
        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\routepolicyondemand.cpp",
        (const char *)(unsigned int)v6,
        pcbResult);
    v7 = cbInput;
    v8 = cbInput + 1;
    v9 = -1;
    if ( cbInput + 1 >= cbInput )
      v9 = cbInput + 1;
    v10 = v8 < cbInput ? (const char *)0x80070216LL : 0LL;
    cbInput = v9;
    if ( v8 < v7 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x7AB,
        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\routepolicyondemand.cpp",
        v10,
        pcbResult);
    v11 = LongLongToULong(2LL * v9, &cbInput);
    if ( v11 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x7AC,
        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\routepolicyondemand.cpp",
        (const char *)(unsigned int)v11,
        pcbResult);
    phAlgorithm = 0;
    v12 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"MD5", 0, 0);
    if ( v12 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x7AF,
        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\routepolicyondemand.cpp",
        (const char *)(unsigned int)v12,
        pcbResult);
    *(_DWORD *)pbOutput = 0;
    v33 = 0;
    Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", pbOutput, 4u, &v33, 0);
    if ( Property < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x7B5,
        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\routepolicyondemand.cpp",
        (const char *)(unsigned int)Property,
        pcbResulta);
    v14 = *(_DWORD *)pbOutput;
    v15 = operator new[](*(unsigned int *)pbOutput);
    memset_0(v15, 0, v14);
    p_StringUuid = (RPC_WSTR *)v15;
    v5 = 14;
    v27 = 14;
    phHash = 0;
    v16 = BCryptCreateHash(phAlgorithm, &phHash, (PUCHAR)v15, *(ULONG *)pbOutput, 0, 0, 0);
    if ( v16 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x7BB,
        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\routepolicyondemand.cpp",
        (const char *)(unsigned int)v16,
        pcbResult);
    v17 = (UCHAR *)pbInput;
    if ( v39 > 7 )
      v17 = pbInput[0];
    v18 = BCryptHashData(phHash, v17, cbInput, 0);
    if ( v18 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x7BC,
        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\routepolicyondemand.cpp",
        (const char *)(unsigned int)v18,
        pcbResult);
    v19 = BCryptFinishHash(phHash, v36, 0x10u, 0);
    if ( v19 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x7BD,
        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\routepolicyondemand.cpp",
        (const char *)(unsigned int)v19,
        pcbResult);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phHash);
    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&p_StringUuid);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
  }
  else
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    v21 = UuidCreate((UUID *)v36);
    if ( v21 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x7C2,
        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\routepolicyondemand.cpp",
        (const char *)v21,
        pcbResult);
  }
  StringUuid = 0;
  v20 = UuidToStringW((const UUID *)v36, &StringUuid);
  if ( v20 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x7C6,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\routepolicyondemand.cpp",
      (const char *)v20,
      pcbResult);
  p_StringUuid = &StringUuid;
  v35 = 1;
  std::wstring::wstring(Src, L"URSP_");
  v27 = v5 | 1;
  v22 = -1;
  do
    ++v22;
  while ( StringUuid[v22] );
  std::wstring::_Append<unsigned short>(Src);
  RpcStringFreeW(&StringUuid);
  ProfileRoutePolicyData::~ProfileRoutePolicyData((ProfileRoutePolicyData *)pbInput);
  return Src;
}

```

## disassembly

```asm
0x18006b818  mov     [rsp-8+arg_10], rbx
0x18006b81d  push    rbp
0x18006b81e  push    rsi
0x18006b81f  push    rdi
0x18006b820  push    r14
0x18006b822  push    r15
0x18006b824  lea     rbp, [rsp-37h]
0x18006b829  sub     rsp, 0F0h
0x18006b830  mov     rax, cs:__security_cookie
0x18006b837  xor     rax, rsp
0x18006b83a  mov     [rbp+57h+var_28], rax
0x18006b83e  mov     rbx, rdx
0x18006b841  mov     r14, rcx
0x18006b844  mov     [rbp+57h+var_C8], rcx
0x18006b848  xor     r15d, r15d
0x18006b84b  mov     [rbp+57h+var_CC], r15d
0x18006b84f  mov     edx, [rdx+50h]
0x18006b852  lea     rcx, [rbp+57h+var_2E]
0x18006b856  test    edx, edx
0x18006b858  jns     short loc_18006B86C
0x18006b85a  neg     edx
0x18006b85c  call    ??$_UIntegral_to_buff@GI@std@@YAPEAGPEAGI@Z; std::_UIntegral_to_buff<ushort,uint>(ushort *,uint)
0x18006b861  lea     rdx, [rax-2]
0x18006b865  mov     word ptr [rdx], 2Dh ; '-'
0x18006b86a  jmp     short loc_18006B874
0x18006b86c  call    ??$_UIntegral_to_buff@GI@std@@YAPEAGPEAGI@Z; std::_UIntegral_to_buff<ushort,uint>(ushort *,uint)
0x18006b871  mov     rdx, rax
0x18006b874  lea     r8, [rbp+57h+var_2E]
0x18006b878  lea     rcx, [rbp+57h+pbInput]
0x18006b87c  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x18006b881  mov     esi, 6
0x18006b886  mov     [rbp+57h+var_CC], esi
0x18006b889  cmp     [rbx+48h], r15b
0x18006b88d  jz      short loc_18006B8B2
0x18006b88f  lea     rcx, [rbx+28h]
0x18006b893  call    ?value@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEGBAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::optional<std::wstring>::value(void)
0x18006b898  mov     r8, [rax+10h]
0x18006b89c  cmp     qword ptr [rax+18h], 7
0x18006b8a1  jbe     short loc_18006B8A6
0x18006b8a3  mov     rax, [rax]
0x18006b8a6  mov     rdx, rax
0x18006b8a9  lea     rcx, [rbp+57h+pbInput]; Src
0x18006b8ad  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18006b8b2  cmp     [rbx+20h], r15b
0x18006b8b6  jz      short loc_18006B8DA
0x18006b8b8  mov     rcx, rbx
0x18006b8bb  call    ?value@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEGBAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::optional<std::wstring>::value(void)
0x18006b8c0  mov     r8, [rax+10h]
0x18006b8c4  cmp     qword ptr [rax+18h], 7
0x18006b8c9  jbe     short loc_18006B8CE
0x18006b8cb  mov     rax, [rax]
0x18006b8ce  mov     rdx, rax
0x18006b8d1  lea     rcx, [rbp+57h+pbInput]; Src
0x18006b8d5  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18006b8da  xorps   xmm0, xmm0
0x18006b8dd  movups  xmmword ptr [rbp+57h+var_88], xmm0
0x18006b8e1  mov     rcx, [rbp+57h+var_68]; __int64
0x18006b8e5  test    rcx, rcx
0x18006b8e8  jz      loc_18006BB27
0x18006b8ee  mov     [rbp+57h+cbInput], r15d
0x18006b8f2  lea     rdx, [rbp+57h+cbInput]; unsigned int *
0x18006b8f6  call    ?LongLongToULong@@YAJ_JPEAK@Z; LongLongToULong(__int64,ulong *)
0x18006b8fb  mov     rcx, [rbp+5Fh]; this
0x18006b8ff  test    eax, eax
0x18006b901  jns     short loc_18006B918
0x18006b903  mov     r9d, eax; char *
0x18006b906  lea     r8, aOnecoreuapNetW_19; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x18006b90d  mov     edx, 7AAh; void *
0x18006b912  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18006b918  mov     edx, [rbp+57h+cbInput]
0x18006b91b  lea     eax, [rdx+1]
0x18006b91e  or      r8d, 0FFFFFFFFh
0x18006b922  cmp     eax, edx
0x18006b924  cmovnb  r8d, eax
0x18006b928  sbb     r9d, r9d
0x18006b92b  and     r9d, 80070216h; char *
0x18006b932  mov     [rbp+57h+cbInput], r8d
0x18006b936  mov     rcx, [rbp+5Fh]; this
0x18006b93a  cmp     eax, edx
0x18006b93c  jnb     short loc_18006B950
0x18006b93e  lea     r8, aOnecoreuapNetW_19; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x18006b945  mov     edx, 7ABh; void *
0x18006b94a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18006b950  mov     ecx, r8d
0x18006b953  add     rcx, rcx; __int64
0x18006b956  lea     rdx, [rbp+57h+cbInput]; unsigned int *
0x18006b95a  call    ?LongLongToULong@@YAJ_JPEAK@Z; LongLongToULong(__int64,ulong *)
0x18006b95f  mov     rcx, [rbp+5Fh]; this
0x18006b963  test    eax, eax
0x18006b965  jns     short loc_18006B97C
0x18006b967  mov     r9d, eax; char *
0x18006b96a  lea     r8, aOnecoreuapNetW_19; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x18006b971  mov     edx, 7ACh; void *
0x18006b976  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18006b97c  mov     [rbp+57h+phAlgorithm], r15
0x18006b980  xor     r9d, r9d; dwFlags
0x18006b983  xor     r8d, r8d; pszImplementation
0x18006b986  lea     rdx, pszAlgId; "MD5"
0x18006b98d  lea     rcx, [rbp+57h+phAlgorithm]; phAlgorithm
0x18006b991  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18006b997  mov     rcx, [rbp+5Fh]; this
0x18006b99b  test    eax, eax
0x18006b99d  jns     short loc_18006B9B4
0x18006b99f  mov     r9d, eax; char *
0x18006b9a2  lea     r8, aOnecoreuapNetW_19; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x18006b9a9  mov     edx, 7AFh; void *
0x18006b9ae  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18006b9b4  mov     dword ptr [rbp+57h+pbOutput], r15d
0x18006b9b8  mov     [rbp+57h+var_A0], r15d
0x18006b9bc  mov     [rsp+110h+dwFlags], r15d; dwFlags
0x18006b9c1  lea     rax, [rbp+57h+var_A0]
0x18006b9c5  mov     [rsp+110h+pcbResult], rax; int
0x18006b9ca  mov     r9d, 4; cbOutput
0x18006b9d0  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x18006b9d4  lea     rdx, pszProperty; "ObjectLength"
0x18006b9db  mov     rcx, [rbp+57h+phAlgorithm]; hObject
0x18006b9df  call    cs:__imp_BCryptGetProperty
0x18006b9e5  mov     rcx, [rbp+5Fh]; this
0x18006b9e9  test    eax, eax
0x18006b9eb  jns     short loc_18006BA02
0x18006b9ed  mov     r9d, eax; char *
0x18006b9f0  lea     r8, aOnecoreuapNetW_19; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x18006b9f7  mov     edx, 7B5h; void *
0x18006b9fc  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18006ba02  mov     ebx, dword ptr [rbp+57h+pbOutput]
0x18006ba05  mov     ecx, ebx; unsigned __int64
0x18006ba07  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18006ba0c  mov     rdi, rax
0x18006ba0f  mov     r8d, ebx; Size
0x18006ba12  xor     edx, edx; Val
0x18006ba14  mov     rcx, rax; void *
0x18006ba17  call    memset_0
0x18006ba1c  mov     [rbp+57h+var_98], rdi
0x18006ba20  mov     esi, 0Eh
0x18006ba25  mov     [rbp+57h+var_CC], esi
0x18006ba28  mov     [rbp+57h+phHash], r15
0x18006ba2c  mov     [rsp+110h+var_E0], r15d; dwFlags
0x18006ba31  mov     [rsp+110h+dwFlags], r15d; cbSecret
0x18006ba36  mov     [rsp+110h+pcbResult], r15; unsigned int
0x18006ba3b  mov     r9d, dword ptr [rbp+57h+pbOutput]; cbHashObject
0x18006ba3f  mov     r8, rdi; pbHashObject
0x18006ba42  lea     rdx, [rbp+57h+phHash]; phHash
0x18006ba46  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x18006ba4a  call    cs:__imp_BCryptCreateHash
0x18006ba50  mov     rcx, [rbp+5Fh]; this
0x18006ba54  test    eax, eax
0x18006ba56  jns     short loc_18006BA6D
0x18006ba58  mov     r9d, eax; char *
0x18006ba5b  lea     r8, aOnecoreuapNetW_19; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x18006ba62  mov     edx, 7BBh; void *
0x18006ba67  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18006ba6d  lea     rdx, [rbp+57h+pbInput]
0x18006ba71  cmp     [rbp+57h+var_60], 7
0x18006ba76  cmova   rdx, [rbp+57h+pbInput]; pbInput
0x18006ba7b  xor     r9d, r9d; dwFlags
0x18006ba7e  mov     r8d, [rbp+57h+cbInput]; cbInput
0x18006ba82  mov     rcx, [rbp+57h+phHash]; hHash
0x18006ba86  call    cs:__imp_BCryptHashData
0x18006ba8c  mov     rcx, [rbp+5Fh]; this
0x18006ba90  test    eax, eax
0x18006ba92  jns     short loc_18006BAA9
0x18006ba94  mov     r9d, eax; char *
0x18006ba97  lea     r8, aOnecoreuapNetW_19; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x18006ba9e  mov     edx, 7BCh; void *
0x18006baa3  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18006baa9  xor     r9d, r9d; dwFlags
0x18006baac  lea     r8d, [r9+10h]; cbOutput
0x18006bab0  lea     rdx, [rbp+57h+var_88]; pbOutput
0x18006bab4  mov     rcx, [rbp+57h+phHash]; hHash
0x18006bab8  call    cs:__imp_BCryptFinishHash
0x18006babe  mov     rcx, [rbp+5Fh]; this
0x18006bac2  test    eax, eax
0x18006bac4  jns     short loc_18006BADB
0x18006bac6  mov     r9d, eax; char *
0x18006bac9  lea     r8, aOnecoreuapNetW_19; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x18006bad0  mov     edx, 7BDh; void *
0x18006bad5  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18006badb  lea     rcx, [rbp+57h+phHash]
0x18006badf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18006bae4  nop
0x18006bae5  lea     rcx, [rbp+57h+var_98]
0x18006bae9  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18006baee  nop
0x18006baef  lea     rcx, [rbp+57h+phAlgorithm]
0x18006baf3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18006baf8  mov     [rbp+57h+StringUuid], r15
0x18006bafc  lea     rdx, [rbp+57h+StringUuid]; StringUuid
0x18006bb00  lea     rcx, [rbp+57h+var_88]; Uuid
0x18006bb04  call    cs:__imp_UuidToStringW
0x18006bb0a  mov     rcx, [rbp+5Fh]; this
0x18006bb0e  test    eax, eax
0x18006bb10  jz      short loc_18006BB53
0x18006bb12  mov     r9d, eax; char *
0x18006bb15  lea     r8, aOnecoreuapNetW_19; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x18006bb1c  mov     edx, 7C6h; void *
0x18006bb21  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18006bb27  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18006bb2c  lea     rcx, [rbp+57h+var_88]; Uuid
0x18006bb30  call    cs:__imp_UuidCreate
0x18006bb36  mov     rcx, [rbp+5Fh]; this
0x18006bb3a  test    eax, eax
0x18006bb3c  jz      short loc_18006BAF8
0x18006bb3e  mov     r9d, eax; char *
0x18006bb41  lea     r8, aOnecoreuapNetW_19; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x18006bb48  mov     edx, 7C2h; void *
0x18006bb4d  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18006bb53  lea     rax, [rbp+57h+StringUuid]
0x18006bb57  mov     [rbp+57h+var_98], rax
0x18006bb5b  mov     [rbp+57h+var_90], 1
0x18006bb5f  lea     rdx, aUrsp; "URSP_"
0x18006bb66  mov     rcx, r14
0x18006bb69  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006bb6e  or      esi, 1
0x18006bb71  mov     [rbp+57h+var_CC], esi
0x18006bb74  mov     rdx, [rbp+57h+StringUuid]
0x18006bb78  or      r8, 0FFFFFFFFFFFFFFFFh
0x18006bb7c  inc     r8
0x18006bb7f  cmp     [rdx+r8*2], r15w
0x18006bb84  jnz     short loc_18006BB7C
0x18006bb86  mov     rcx, r14; Src
0x18006bb89  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18006bb8e  nop
0x18006bb8f  lea     rcx, [rbp+57h+StringUuid]; String
0x18006bb93  call    cs:__imp_RpcStringFreeW
0x18006bb99  nop
0x18006bb9a  lea     rcx, [rbp+57h+pbInput]; this
0x18006bb9e  call    ??1ProfileRoutePolicyData@@QEAA@XZ; ProfileRoutePolicyData::~ProfileRoutePolicyData(void)
0x18006bba3  mov     rax, r14
0x18006bba6  mov     rcx, [rbp+57h+var_28]
0x18006bbaa  xor     rcx, rsp; StackCookie
0x18006bbad  call    __security_check_cookie
0x18006bbb2  mov     rbx, [rsp+110h+arg_10]
0x18006bbba  add     rsp, 0F0h
0x18006bbc1  pop     r15
0x18006bbc3  pop     r14
0x18006bbc5  pop     rdi
0x18006bbc6  pop     rsi
0x18006bbc7  pop     rbp
0x18006bbc8  retn
```
