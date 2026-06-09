# localHashAuthBlob

- ea: `0x180055244`
- end: `0x1800554ac`
- name: `localHashAuthBlob`
- size: `616`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800549c0`

## callees

- `0x180018194`
- `0x180024fe4`
- `0x18002d518`
- `0x18003d528`
- `0x18005499c`
- `0x180055244`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x1800553c6`
- `bcrypt!BCryptCreateHash` at `0x1800553c6`
- `bcrypt!BCryptHashData` at `0x180055427`
- `bcrypt!BCryptHashData` at `0x180055427`
- `bcrypt!BCryptFinishHash` at `0x18005545a`
- `bcrypt!BCryptFinishHash` at `0x18005545a`
- `bcrypt!BCryptGetProperty` at `0x180055352`
- `bcrypt!BCryptGetProperty` at `0x180055352`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800552cb`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800552cb`

## pseudocode

```c
__int64 __fastcall localHashAuthBlob(__int64 a1, __int64 a2, void *a3, ULONG a4, _DWORD *a5)
{
  _DWORD *v8; // rsi
  NTSTATUS Property; // ebx
  char *v11; // rdx
  ULONG v12; // eax
  char *v13; // rdx
  NTSTATUS v14; // [rsp+40h] [rbp-28h] BYREF
  ULONG pcbResult; // [rsp+44h] [rbp-24h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-20h] BYREF
  BCRYPT_HASH_HANDLE phHash[3]; // [rsp+50h] [rbp-18h] BYREF
  __int64 pbOutput; // [rsp+A0h] [rbp+38h] BYREF

  pbOutput = a1;
  if ( *(_QWORD *)(a2 + 8) == *(_QWORD *)a2 )
    return 2147942487LL;
  if ( a4 && !a3 )
    return 2147500035LL;
  v8 = a5;
  if ( !a5 )
    return 2147500035LL;
  if ( a4 )
    memset_0(a3, 0, a4);
  *v8 = 0;
  phAlgorithm = 0;
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &phAlgorithm,
    0);
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", L"Microsoft Primitive Provider", 0);
  if ( Property < 0 )
  {
    if ( (unsigned int)dword_1800BE0B8 <= 2 )
    {
LABEL_12:
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
      return Property | 0x10000000u;
    }
    v11 = byte_1800AD821;
LABEL_11:
    v14 = Property;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_1800BE0B8,
      (unsigned __int8 *)v11,
      0,
      0,
      (__int64)&v14);
    goto LABEL_12;
  }
  pcbResult = 4;
  LODWORD(pbOutput) = 0;
  Property = BCryptGetProperty(phAlgorithm, L"HashDigestLength", (PUCHAR)&pbOutput, 4u, &pcbResult, 0);
  if ( Property < 0 )
  {
    if ( (unsigned int)dword_1800BE0B8 <= 2 )
      goto LABEL_12;
    v11 = &byte_1800AD8AF;
    goto LABEL_11;
  }
  v12 = pbOutput;
  *v8 = pbOutput;
  if ( a4 < v12 )
  {
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
    return 2148073512LL;
  }
  phHash[0] = 0;
  Property = BCryptCreateHash(phAlgorithm, phHash, 0, 0, 0, 0, 0);
  if ( Property < 0 )
  {
    if ( (unsigned int)dword_1800BE0B8 <= 2 )
    {
LABEL_22:
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(phHash);
      goto LABEL_12;
    }
    v13 = &byte_1800AD887;
LABEL_21:
    v14 = Property;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_1800BE0B8,
      (unsigned __int8 *)v13,
      0,
      0,
      (__int64)&v14);
    goto LABEL_22;
  }
  Property = BCryptHashData(phHash[0], *(PUCHAR *)a2, *(_DWORD *)(a2 + 8) - *(_DWORD *)a2, 0);
  if ( Property < 0 )
  {
    if ( (unsigned int)dword_1800BE0B8 <= 2 )
      goto LABEL_22;
    v13 = byte_1800AD7D3;
    goto LABEL_21;
  }
  Property = BCryptFinishHash(phHash[0], (PUCHAR)a3, a4, 0);
  if ( Property < 0 )
  {
    if ( (unsigned int)dword_1800BE0B8 <= 2 )
      goto LABEL_22;
    v13 = byte_1800AD7F9;
    goto LABEL_21;
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(phHash);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
  return 0;
}

```

## disassembly

```asm
0x180055244  mov     [rsp-30h+pbOutput], rcx
0x180055249  push    rbp
0x18005524a  push    rbx
0x18005524b  push    rsi
0x18005524c  push    rdi
0x18005524d  push    r14
0x18005524f  push    r15
0x180055251  mov     rbp, rsp
0x180055254  sub     rsp, 68h
0x180055258  mov     rax, [rdx+8]
0x18005525c  mov     r14, r8
0x18005525f  mov     r15, rdx
0x180055262  mov     edi, r9d
0x180055265  cmp     rax, [rdx]
0x180055268  jz      loc_180055499
0x18005526e  test    r9d, r9d
0x180055271  jz      short loc_180055278
0x180055273  test    r8, r8
0x180055276  jz      short loc_180055281
0x180055278  mov     rsi, [rbp+arg_20]
0x18005527c  test    rsi, rsi
0x18005527f  jnz     short loc_18005528B
0x180055281  mov     eax, 80004003h
0x180055286  jmp     loc_18005549E
0x18005528b  test    r9d, r9d
0x18005528e  jz      short loc_18005529D
0x180055290  mov     r8, rdi; Size
0x180055293  xor     edx, edx; Val
0x180055295  mov     rcx, r14; void *
0x180055298  call    memset_0
0x18005529d  xor     edx, edx
0x18005529f  mov     dword ptr [rsi], 0
0x1800552a5  lea     rcx, [rbp+phAlgorithm]
0x1800552a9  mov     [rbp+phAlgorithm], 0
0x1800552b1  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800552b6  xor     r9d, r9d; dwFlags
0x1800552b9  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x1800552c0  lea     rdx, pszAlgId; "SHA256"
0x1800552c7  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x1800552cb  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800552d2  nop     dword ptr [rax+rax+00h]
0x1800552d7  mov     ebx, eax
0x1800552d9  test    eax, eax
0x1800552db  jns     short loc_180055321
0x1800552dd  mov     ecx, cs:dword_1800BE0B8
0x1800552e3  cmp     ecx, 2
0x1800552e6  jbe     short loc_18005530D
0x1800552e8  lea     rdx, byte_1800AD821
0x1800552ef  xor     r9d, r9d
0x1800552f2  lea     rax, [rbp+var_28]
0x1800552f6  xor     r8d, r8d
0x1800552f9  mov     [rsp+68h+pcbResult], rax
0x1800552fe  lea     rcx, dword_1800BE0B8
0x180055305  mov     [rbp+var_28], ebx
0x180055308  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18005530d  lea     rcx, [rbp+phAlgorithm]
0x180055311  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180055316  bts     ebx, 1Ch
0x18005531a  mov     eax, ebx
0x18005531c  jmp     loc_18005549E
0x180055321  mov     rcx, [rbp+phAlgorithm]; hObject
0x180055325  lea     rax, [rbp+var_24]
0x180055329  mov     r9d, 4; cbOutput
0x18005532f  mov     [rsp+68h+dwFlags], 0; dwFlags
0x180055337  lea     r8, [rbp+pbOutput]; pbOutput
0x18005533b  mov     [rbp+var_24], r9d
0x18005533f  lea     rdx, pszProperty; "HashDigestLength"
0x180055346  mov     [rsp+68h+pcbResult], rax; pcbResult
0x18005534b  mov     dword ptr [rbp+pbOutput], 0
0x180055352  call    cs:__imp_BCryptGetProperty
0x180055359  nop     dword ptr [rax+rax+00h]
0x18005535e  mov     ebx, eax
0x180055360  test    eax, eax
0x180055362  jns     short loc_18005537B
0x180055364  mov     ecx, cs:dword_1800BE0B8
0x18005536a  cmp     ecx, 2
0x18005536d  jbe     short loc_18005530D
0x18005536f  lea     rdx, byte_1800AD8AF
0x180055376  jmp     loc_1800552EF
0x18005537b  mov     eax, dword ptr [rbp+pbOutput]
0x18005537e  mov     [rsi], eax
0x180055380  cmp     edi, eax
0x180055382  jnb     short loc_180055397
0x180055384  lea     rcx, [rbp+phAlgorithm]
0x180055388  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005538d  mov     eax, 80090028h
0x180055392  jmp     loc_18005549E
0x180055397  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18005539b  lea     rdx, [rbp+phHash]; phHash
0x18005539f  mov     [rsp+68h+var_38], 0; dwFlags
0x1800553a7  xor     r9d, r9d; cbHashObject
0x1800553aa  mov     [rsp+68h+dwFlags], 0; cbSecret
0x1800553b2  xor     r8d, r8d; pbHashObject
0x1800553b5  mov     [rsp+68h+pcbResult], 0; pbSecret
0x1800553be  mov     [rbp+phHash], 0
0x1800553c6  call    cs:__imp_BCryptCreateHash
0x1800553cd  nop     dword ptr [rax+rax+00h]
0x1800553d2  mov     ebx, eax
0x1800553d4  test    eax, eax
0x1800553d6  jns     short loc_180055416
0x1800553d8  mov     ecx, cs:dword_1800BE0B8
0x1800553de  cmp     ecx, 2
0x1800553e1  jbe     short loc_180055408
0x1800553e3  lea     rdx, byte_1800AD887
0x1800553ea  lea     rax, [rbp+var_28]
0x1800553ee  xor     r9d, r9d
0x1800553f1  mov     [rsp+68h+pcbResult], rax
0x1800553f6  xor     r8d, r8d
0x1800553f9  lea     rcx, dword_1800BE0B8
0x180055400  mov     [rbp+var_28], ebx
0x180055403  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180055408  lea     rcx, [rbp+phHash]
0x18005540c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180055411  jmp     loc_18005530D
0x180055416  mov     r8d, [r15+8]
0x18005541a  xor     r9d, r9d; dwFlags
0x18005541d  sub     r8d, [r15]; cbInput
0x180055420  mov     rdx, [r15]; pbInput
0x180055423  mov     rcx, [rbp+phHash]; hHash
0x180055427  call    cs:__imp_BCryptHashData
0x18005542e  nop     dword ptr [rax+rax+00h]
0x180055433  mov     ebx, eax
0x180055435  test    eax, eax
0x180055437  jns     short loc_18005544D
0x180055439  mov     ecx, cs:dword_1800BE0B8
0x18005543f  cmp     ecx, 2
0x180055442  jbe     short loc_180055408
0x180055444  lea     rdx, byte_1800AD7D3
0x18005544b  jmp     short loc_1800553EA
0x18005544d  mov     rcx, [rbp+phHash]; hHash
0x180055451  xor     r9d, r9d; dwFlags
0x180055454  mov     r8d, edi; cbOutput
0x180055457  mov     rdx, r14; pbOutput
0x18005545a  call    cs:__imp_BCryptFinishHash
0x180055461  nop     dword ptr [rax+rax+00h]
0x180055466  mov     ebx, eax
0x180055468  test    eax, eax
0x18005546a  jns     short loc_180055483
0x18005546c  mov     ecx, cs:dword_1800BE0B8
0x180055472  cmp     ecx, 2
0x180055475  jbe     short loc_180055408
0x180055477  lea     rdx, byte_1800AD7F9
0x18005547e  jmp     loc_1800553EA
0x180055483  lea     rcx, [rbp+phHash]
0x180055487  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18005548c  lea     rcx, [rbp+phAlgorithm]
0x180055490  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180055495  xor     eax, eax
0x180055497  jmp     short loc_18005549E
0x180055499  mov     eax, 80070057h
0x18005549e  add     rsp, 68h
0x1800554a2  pop     r15
0x1800554a4  pop     r14
0x1800554a6  pop     rdi
0x1800554a7  pop     rsi
0x1800554a8  pop     rbx
0x1800554a9  pop     rbp
0x1800554aa  retn
```
