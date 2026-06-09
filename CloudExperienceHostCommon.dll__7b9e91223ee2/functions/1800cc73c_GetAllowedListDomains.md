# GetAllowedListDomains

- ea: `0x1800cc73c`
- end: `0x1800cc837`
- name: `GetAllowedListDomains`
- size: `251`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800ccab8`

## callees

- `0x180010c8c`
- `0x180013a74`
- `0x18001b838`
- `0x1800cc618`
- `0x1800cc73c`
- `0x1800ccdd0`

## import_xrefs

- `ext-ms-win-devmgmt-policy-l1-1-1!PolicyManager_GetPolicy` at `0x1800cc78c`
- `ext-ms-win-devmgmt-policy-l1-1-1!PolicyManager_GetPolicy` at `0x1800cc78c`

## string_xrefs

- `0x1800cc77e`: `ConfigureWebcamAccessDomainNames`
- `0x1800cc7d1`: `onecore\ds\security\cfl\policy\lib\cxpolicy.cpp`
- `0x1800cc80a`: `onecore\ds\security\cfl\policy\lib\cxpolicy.cpp`
- `0x1800cc822`: `onecore\ds\security\cfl\policy\lib\cxpolicy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetAllowedListDomains(__int64 a1)
{
  int Policy; // eax
  __int64 v3; // rbx
  int v5; // [rsp+20h] [rbp-38h]
  char *v6; // [rsp+30h] [rbp-28h]
  int v7; // [rsp+38h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  __int64 v9; // [rsp+68h] [rbp+10h] BYREF
  int v10; // [rsp+70h] [rbp+18h] BYREF
  int v11; // [rsp+74h] [rbp+1Ch]

  if ( !(unsigned __int8)IsPolicyManager_GetPolicyPresent() )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC,
      (unsigned int)"onecore\\ds\\security\\cfl\\policy\\lib\\cxpolicy.cpp",
      (const char *)0x80004001LL,
      v5);
  v10 = 1;
  v11 = 2;
  v9 = 0;
  Policy = PolicyManager_GetPolicy(L"Authentication", L"ConfigureWebcamAccessDomainNames", &v10, &v9);
  if ( Policy < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x15,
      (unsigned int)"onecore\\ds\\security\\cfl\\policy\\lib\\cxpolicy.cpp",
      (const char *)(unsigned int)Policy,
      v5);
  v3 = v9;
  v7 = *(_DWORD *)(v9 + 8);
  LODWORD(v6) = *(_DWORD *)(v9 + 4);
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x1A,
    (unsigned int)"onecore\\ds\\security\\cfl\\policy\\lib\\cxpolicy.cpp",
    (const char *)0x8000FFFFLL,
    v7 != 2,
    (bool)"state: %u, type: %u",
    v6,
    v7);
  std::wstring::wstring(a1, *(_QWORD *)(v3 + 16));
  wil::details::unique_storage<wil::details::resource_policy<PMPolicyRetrievedInfo *,long (*)(PMPolicyRetrievedInfo *),&long PolicyManager_FreeGetPolicyData(PMPolicyRetrievedInfo *),wistd::integral_constant<unsigned __int64,0>,PMPolicyRetrievedInfo *,PMPolicyRetrievedInfo *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<PMPolicyRetrievedInfo *,long (*)(PMPolicyRetrievedInfo *),&long PolicyManager_FreeGetPolicyData(PMPolicyRetrievedInfo *),wistd::integral_constant<unsigned __int64,0>,PMPolicyRetrievedInfo *,PMPolicyRetrievedInfo *,0,std::nullptr_t>>(&v9);
  return a1;
}

```

## disassembly

```asm
0x1800cc73c  mov     [rsp+arg_0], rbx
0x1800cc741  push    rdi
0x1800cc742  sub     rsp, 50h
0x1800cc746  mov     rdi, rcx
0x1800cc749  mov     rbx, [rsp+58h]
0x1800cc74e  call    IsPolicyManager_GetPolicyPresent
0x1800cc753  test    al, al
0x1800cc755  jz      loc_1800CC81C
0x1800cc75b  mov     [rsp+58h+arg_10], 1
0x1800cc763  mov     [rsp+58h+arg_14], 2
0x1800cc76b  mov     [rsp+58h+arg_8], 0
0x1800cc774  lea     r9, [rsp+58h+arg_8]
0x1800cc779  lea     r8, [rsp+58h+arg_10]
0x1800cc77e  lea     rdx, aConfigurewebca; "ConfigureWebcamAccessDomainNames"
0x1800cc785  lea     rcx, aAuthentication; "Authentication"
0x1800cc78c  call    cs:__imp_PolicyManager_GetPolicy
0x1800cc792  mov     rcx, [rsp+58h]; this
0x1800cc797  test    eax, eax
0x1800cc799  js      short loc_1800CC807
0x1800cc79b  mov     rbx, [rsp+58h+arg_8]
0x1800cc7a0  mov     eax, [rbx+8]
0x1800cc7a3  cmp     eax, 2
0x1800cc7a6  setnz   r8b
0x1800cc7aa  mov     rcx, [rsp+58h]; this
0x1800cc7af  mov     [rsp+58h+var_20], eax
0x1800cc7b3  mov     eax, [rbx+4]
0x1800cc7b6  mov     dword ptr [rsp+58h+var_28], eax; char *
0x1800cc7ba  lea     rax, aStateUTypeU; "state: %u, type: %u"
0x1800cc7c1  mov     qword ptr [rsp+58h+var_30], rax; bool
0x1800cc7c6  mov     [rsp+58h+var_38], r8b; char
0x1800cc7cb  mov     r9d, 8000FFFFh; char *
0x1800cc7d1  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cfl\\policy\\lib"...
0x1800cc7d8  mov     edx, 1Ah; void *
0x1800cc7dd  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800cc7e2  mov     rdx, [rbx+10h]
0x1800cc7e6  mov     rcx, rdi
0x1800cc7e9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800cc7ee  nop
0x1800cc7ef  lea     rcx, [rsp+58h+arg_8]
0x1800cc7f4  call    ??1?$unique_storage@U?$resource_policy@PEAUPMPolicyRetrievedInfo@@P6AJPEAU1@@Z$1?PolicyManager_FreeGetPolicyData@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<PMPolicyRetrievedInfo *,long (*)(PMPolicyRetrievedInfo *),&PolicyManager_FreeGetPolicyData(PMPolicyRetrievedInfo *),wistd::integral_constant<unsigned __int64,0>,PMPolicyRetrievedInfo *,PMPolicyRetrievedInfo *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<PMPolicyRetrievedInfo *,long (*)(PMPolicyRetrievedInfo *),&PolicyManager_FreeGetPolicyData(PMPolicyRetrievedInfo *),wistd::integral_constant<unsigned __int64,0>,PMPolicyRetrievedInfo *,PMPolicyRetrievedInfo *,0,std::nullptr_t>>(void)
0x1800cc7f9  mov     rax, rdi
0x1800cc7fc  mov     rbx, [rsp+58h+arg_0]
0x1800cc801  add     rsp, 50h
0x1800cc805  pop     rdi
0x1800cc806  retn
0x1800cc807  mov     r9d, eax; char *
0x1800cc80a  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cfl\\policy\\lib"...
0x1800cc811  mov     edx, 15h; void *
0x1800cc816  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800cc81c  mov     r9d, 80004001h; char *
0x1800cc822  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cfl\\policy\\lib"...
0x1800cc829  mov     edx, 0Ch; void *
0x1800cc82e  mov     rcx, rbx; this
0x1800cc831  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
