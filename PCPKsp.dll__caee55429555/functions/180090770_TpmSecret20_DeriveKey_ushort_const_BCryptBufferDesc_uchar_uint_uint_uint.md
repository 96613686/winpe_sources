# TpmSecret20::DeriveKey(ushort const *,_BCryptBufferDesc *,uchar *,uint,uint *,uint)

- ea: `0x180090770`
- end: `0x180090959`
- name: `?DeriveKey@TpmSecret20@@UEAAJPEBGPEAU_BCryptBufferDesc@@PEAEIPEAII@Z`
- size: `489`
- prototype: `int(TpmSecret20 *__hidden this, const unsigned __int16 *, struct _BCryptBufferDesc *, unsigned __int8 *, unsigned int, unsigned int *, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x1800133c4`
- `0x180014a60`
- `0x1800157c0`
- `0x180061bac`
- `0x180063c98`
- `0x1800768a0`
- `0x180090684`
- `0x180090770`

## import_xrefs

- `bcrypt!BCryptDeriveKey` at `0x1800908ac`
- `bcrypt!BCryptDeriveKey` at `0x1800908ac`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800907bc`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800907bc`

## pseudocode

```c
__int64 __fastcall TpmSecret20::DeriveKey(
        TpmSecret20 *this,
        const unsigned __int16 *a2,
        struct _BCryptBufferDesc *a3,
        unsigned __int8 *a4,
        ULONG a5,
        unsigned int *pcbResult,
        ULONG dwFlags)
{
  int v9; // ebx
  NTSTATUS v11; // eax
  int v12; // ecx
  int v13; // r9d
  unsigned int v14; // ebx
  int v15; // eax
  int v16; // edi
  const struct std::nothrow_t *v17; // rdx
  void **v18; // rbx
  __int64 v19; // rdx
  const struct std::nothrow_t *v20; // rdx
  NTSTATUS v21; // eax
  const struct std::nothrow_t *v22; // rdx
  void **v23; // rbx
  __int64 v24; // rdx
  const struct std::nothrow_t *v25; // rdx
  int cbDerivedKey; // [rsp+20h] [rbp-58h]
  int cbDerivedKeya; // [rsp+20h] [rbp-58h]
  int cbDerivedKeyb; // [rsp+20h] [rbp-58h]
  int cbDerivedKeyc; // [rsp+20h] [rbp-58h]
  BCRYPT_SECRET_HANDLE hSharedSecret; // [rsp+40h] [rbp-38h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-30h] BYREF
  int *v33[5]; // [rsp+50h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+30h]

  v9 = (int)this;
  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v33, L"TpmSecret20::DeriveKey", 1);
  phAlgorithm = 0;
  v11 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"ECDH", L"Microsoft Primitive Provider", 0);
  if ( v11 >= 0 )
  {
    hSharedSecret = 0;
    v15 = TpmSecret20::BuildBCryptSecret(v12, v9 + 88, (_DWORD)phAlgorithm, v13, (__int64)&hSharedSecret);
    v16 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7C,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmsecret20.cpp",
        (const char *)(unsigned int)v15,
        cbDerivedKeya);
      goto LABEL_5;
    }
    v21 = BCryptDeriveKey(hSharedSecret, a2, a3, a4, a5, pcbResult, dwFlags);
    if ( v21 < 0 )
    {
      v16 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x84,
              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmsecret20.cpp",
              (const char *)(unsigned int)v21,
              cbDerivedKeyc);
LABEL_5:
      v18 = (void **)hSharedSecret;
      if ( hSharedSecret )
      {
        if ( *((_DWORD *)hSharedSecret + 1) == 1431655764
          && *(_DWORD *)(*((_QWORD *)hSharedSecret + 2) + 4LL) == 1297302851 )
        {
          _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)hSharedSecret + 1) + 16LL));
          operator delete(v18[2], v17);
          operator delete(v18, v20);
LABEL_12:
          v14 = v16;
          goto LABEL_23;
        }
        v19 = 67;
      }
      else
      {
        v19 = 63;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmsecret20.cpp",
        (const char *)0x80090027LL,
        cbDerivedKeyb);
      goto LABEL_12;
    }
    v23 = (void **)hSharedSecret;
    if ( hSharedSecret )
    {
      if ( *((_DWORD *)hSharedSecret + 1) == 1431655764
        && *(_DWORD *)(*((_QWORD *)hSharedSecret + 2) + 4LL) == 1297302851 )
      {
        _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)hSharedSecret + 1) + 16LL));
        operator delete(v23[2], v22);
        operator delete(v23, v25);
LABEL_22:
        v14 = 0;
        goto LABEL_23;
      }
      v24 = 67;
    }
    else
    {
      v24 = 63;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmsecret20.cpp",
      (const char *)0x80090027LL,
      cbDerivedKeyc);
    goto LABEL_22;
  }
  v14 = wil::details::in1diag3::Return_NtStatus(
          retaddr,
          (void *)0x74,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmsecret20.cpp",
          (const char *)(unsigned int)v11,
          cbDerivedKey);
LABEL_23:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
  KspFunctionLogger::~KspFunctionLogger(v33);
  return v14;
}

```

## disassembly

```asm
0x180090770  push    rbp
0x180090772  push    rbx
0x180090773  push    rsi
0x180090774  push    rdi
0x180090775  push    r14
0x180090777  push    r15
0x180090779  mov     rbp, rsp
0x18009077c  sub     rsp, 78h
0x180090780  mov     r14, r8
0x180090783  mov     r15, rdx
0x180090786  mov     rbx, rcx
0x180090789  lea     rdx, aTpmsecret20Der; "TpmSecret20::DeriveKey"
0x180090790  mov     r8b, 1; bool
0x180090793  lea     rcx, [rbp+var_28]; this
0x180090797  mov     rsi, r9
0x18009079a  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x18009079f  xor     r9d, r9d; dwFlags
0x1800907a2  mov     [rbp+phAlgorithm], 0
0x1800907aa  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x1800907b1  lea     rdx, aEcdh; "ECDH"
0x1800907b8  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x1800907bc  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800907c3  nop     dword ptr [rax+rax+00h]
0x1800907c8  test    eax, eax
0x1800907ca  jns     short loc_1800907EB
0x1800907cc  mov     rcx, [rbp+30h]; this
0x1800907d0  lea     r8, aOnecoreBaseNgs_30; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x1800907d7  mov     r9d, eax; char *
0x1800907da  mov     edx, 74h ; 't'; void *
0x1800907df  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800907e4  mov     ebx, eax
0x1800907e6  jmp     loc_180090937
0x1800907eb  mov     r8, [rbp+phAlgorithm]
0x1800907ef  lea     rax, [rbp+hSharedSecret]
0x1800907f3  lea     rdx, [rbx+58h]
0x1800907f7  mov     qword ptr [rsp+78h+cbDerivedKey], rax; int
0x1800907fc  mov     [rbp+hSharedSecret], 0
0x180090804  call    ?BuildBCryptSecret@TpmSecret20@@AEAAJAEBV?$vector@EV?$allocator@E@std@@@std@@PEAXKPEAPEAXK@Z; TpmSecret20::BuildBCryptSecret(std::vector<uchar> const &,void *,ulong,void * *,ulong)
0x180090809  mov     edi, eax
0x18009080b  test    eax, eax
0x18009080d  jns     short loc_180090888
0x18009080f  mov     rcx, [rbp+30h]; this
0x180090813  lea     r8, aOnecoreBaseNgs_30; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18009081a  mov     r9d, eax; char *
0x18009081d  mov     edx, 7Ch ; '|'; void *
0x180090822  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180090827  mov     rbx, [rbp+hSharedSecret]
0x18009082b  test    rbx, rbx
0x18009082e  jnz     short loc_180090835
0x180090830  lea     edx, [rbx+3Fh]
0x180090833  jmp     short loc_18009086B
0x180090835  cmp     dword ptr [rbx+4], 55555554h
0x18009083c  jnz     short loc_180090866
0x18009083e  mov     rax, [rbx+10h]
0x180090842  cmp     dword ptr [rax+4], 4D534543h
0x180090849  jnz     short loc_180090866
0x18009084b  mov     rax, [rbx+8]
0x18009084f  lock dec dword ptr [rax+10h]
0x180090853  mov     rcx, [rbx+10h]; void *
0x180090857  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18009085c  mov     rcx, rbx; void *
0x18009085f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180090864  jmp     short loc_180090881
0x180090866  mov     edx, 43h ; 'C'; void *
0x18009086b  mov     rcx, [rbp+30h]; this
0x18009086f  lea     r8, aOnecoreBaseNgs_30; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180090876  mov     r9d, 80090027h; char *
0x18009087c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180090881  mov     ebx, edi
0x180090883  jmp     loc_180090937
0x180090888  mov     eax, [rbp+arg_30]
0x18009088b  mov     r9, rsi; pbDerivedKey
0x18009088e  mov     rcx, [rbp+hSharedSecret]; hSharedSecret
0x180090892  mov     r8, r14; pParameterList
0x180090895  mov     [rsp+78h+dwFlags], eax; dwFlags
0x180090899  mov     rdx, r15; pwszKDF
0x18009089c  mov     rax, [rbp+arg_28]
0x1800908a0  mov     [rsp+78h+pcbResult], rax; pcbResult
0x1800908a5  mov     eax, [rbp+arg_20]
0x1800908a8  mov     [rsp+78h+cbDerivedKey], eax; int
0x1800908ac  call    cs:__imp_BCryptDeriveKey
0x1800908b3  nop     dword ptr [rax+rax+00h]
0x1800908b8  test    eax, eax
0x1800908ba  jns     short loc_1800908DB
0x1800908bc  mov     rcx, [rbp+30h]; this
0x1800908c0  lea     r8, aOnecoreBaseNgs_30; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x1800908c7  mov     r9d, eax; char *
0x1800908ca  mov     edx, 84h; void *
0x1800908cf  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800908d4  mov     edi, eax
0x1800908d6  jmp     loc_180090827
0x1800908db  mov     rbx, [rbp+hSharedSecret]
0x1800908df  test    rbx, rbx
0x1800908e2  jnz     short loc_1800908E9
0x1800908e4  lea     edx, [rbx+3Fh]
0x1800908e7  jmp     short loc_18009091F
0x1800908e9  cmp     dword ptr [rbx+4], 55555554h
0x1800908f0  jnz     short loc_18009091A
0x1800908f2  mov     rax, [rbx+10h]
0x1800908f6  cmp     dword ptr [rax+4], 4D534543h
0x1800908fd  jnz     short loc_18009091A
0x1800908ff  mov     rax, [rbx+8]
0x180090903  lock dec dword ptr [rax+10h]
0x180090907  mov     rcx, [rbx+10h]; void *
0x18009090b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180090910  mov     rcx, rbx; void *
0x180090913  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180090918  jmp     short loc_180090935
0x18009091a  mov     edx, 43h ; 'C'; void *
0x18009091f  mov     rcx, [rbp+30h]; this
0x180090923  lea     r8, aOnecoreBaseNgs_30; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18009092a  mov     r9d, 80090027h; char *
0x180090930  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180090935  xor     ebx, ebx
0x180090937  lea     rcx, [rbp+phAlgorithm]
0x18009093b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180090940  lea     rcx, [rbp+var_28]; this
0x180090944  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180090949  mov     eax, ebx
0x18009094b  add     rsp, 78h
0x18009094f  pop     r15
0x180090951  pop     r14
0x180090953  pop     rdi
0x180090954  pop     rsi
0x180090955  pop     rbx
0x180090956  pop     rbp
0x180090957  retn
```
