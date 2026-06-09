# CFB(uchar *,uint,uchar *,uint,uchar *,uint)

- ea: `0x1800954dc`
- end: `0x18009581b`
- name: `?CFB@@YAJPEAEI0I0I@Z`
- size: `831`
- prototype: `__int64 __usercall@<rax>(unsigned __int8 *@<rcx>, ULONG cbSecret@<edx>, unsigned __int8 *Destination@<r8>, unsigned int@<r9d>, PUCHAR, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180063cdc`

## callees

- `0x1800133c4`
- `0x180014a60`
- `0x1800157c0`
- `0x180029260`
- `0x18005600c`
- `0x180056fec`
- `0x180061bac`
- `0x180063c98`
- `0x180063cb8`
- `0x1800952b4`
- `0x1800954dc`

## import_xrefs

- `bcrypt!BCryptEncrypt` at `0x1800956e1`
- `bcrypt!BCryptEncrypt` at `0x180095751`
- `bcrypt!BCryptEncrypt` at `0x1800956e1`
- `bcrypt!BCryptEncrypt` at `0x180095751`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800955ee`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800955ee`
- `bcrypt!BCryptSetProperty` at `0x180095643`
- `bcrypt!BCryptSetProperty` at `0x180095677`
- `bcrypt!BCryptSetProperty` at `0x180095643`
- `bcrypt!BCryptSetProperty` at `0x180095677`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180095584`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180095584`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CFB(
        unsigned __int8 *a1,
        ULONG cbSecret,
        unsigned __int8 *Destination,
        ULONG a4,
        PUCHAR a5,
        ULONG cbInput)
{
  UCHAR *v9; // rbx
  NTSTATUS v10; // eax
  unsigned int v11; // ebx
  NTSTATUS v12; // eax
  __int64 v13; // rdx
  NTSTATUS v14; // eax
  int pbSecret; // [rsp+20h] [rbp-69h]
  int pbSecreta; // [rsp+20h] [rbp-69h]
  int pbSecretb; // [rsp+20h] [rbp-69h]
  BCRYPT_KEY_HANDLE phKey; // [rsp+50h] [rbp-39h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+58h] [rbp-31h] BYREF
  PUCHAR pbIV[3]; // [rsp+60h] [rbp-29h] BYREF
  PUCHAR pbOutput[3]; // [rsp+78h] [rbp-11h] BYREF
  int *v23[8]; // [rsp+90h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+4Fh]
  int pbInput; // [rsp+E0h] [rbp+57h] BYREF
  ULONG pcbResult; // [rsp+F8h] [rbp+6Fh] BYREF

  pcbResult = a4;
  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v23, L"CFB", 1);
  pbInput = 16;
  pcbResult = 0;
  if ( !a1 || !cbSecret || !Destination || (v9 = a5) == 0 || !cbInput )
  {
    v11 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x799,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\attestation20.cpp",
      (const char *)0x80070057LL,
      pbSecret);
    goto LABEL_23;
  }
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(
    pbIV,
    16);
  phAlgorithm = 0;
  v10 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"AES", L"Microsoft Primitive Provider", 0);
  if ( v10 >= 0 )
  {
    phKey = 0;
    v12 = BCryptGenerateSymmetricKey(phAlgorithm, &phKey, 0, 0, a1, cbSecret, 0);
    if ( v12 >= 0 )
    {
      v12 = BCryptSetProperty(phKey, L"ChainingMode", (PUCHAR)L"ChainingModeCFB", 0x20u, 0);
      if ( v12 >= 0 )
      {
        v12 = BCryptSetProperty(phKey, L"MessageBlockLength", (PUCHAR)&pbInput, 4u, 0);
        if ( v12 >= 0 )
        {
          std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Assign_counted_range<unsigned char *>(
            pbIV,
            Destination,
            16);
          v12 = BCryptEncrypt(phKey, v9, cbInput, 0, pbIV[0], 0x10u, 0, 0, &pcbResult, 1u);
          if ( v12 >= 0 )
          {
            std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(
              pbOutput,
              pcbResult);
            std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Assign_counted_range<unsigned char *>(
              pbIV,
              Destination,
              16);
            v14 = BCryptEncrypt(phKey, v9, cbInput, 0, pbIV[0], 0x10u, pbOutput[0], pcbResult, &pcbResult, 1u);
            if ( v14 >= 0 )
            {
              memcpy_s(v9, cbInput, pbOutput[0], cbInput);
              memcpy_s(Destination, 0x10u, pbIV[0], 0x10u);
              std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(pbOutput);
              wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
              __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
              std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(pbIV);
              v11 = 0;
              goto LABEL_23;
            }
            v11 = wil::details::in1diag3::Return_NtStatus(
                    retaddr,
                    (void *)0x7CF,
                    (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\attestation20.cpp",
                    (const char *)(unsigned int)v14,
                    pbSecretb);
            std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(pbOutput);
            goto LABEL_12;
          }
          v13 = 1985;
        }
        else
        {
          v13 = 1973;
        }
      }
      else
      {
        v13 = 1967;
      }
    }
    else
    {
      v13 = 1961;
    }
    v11 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)v13,
            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\attestation20.cpp",
            (const char *)(unsigned int)v12,
            pbSecreta);
LABEL_12:
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
    goto LABEL_8;
  }
  v11 = wil::details::in1diag3::Return_NtStatus(
          retaddr,
          (void *)0x7A0,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\attestation20.cpp",
          (const char *)(unsigned int)v10,
          pbSecret);
LABEL_8:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(pbIV);
LABEL_23:
  KspFunctionLogger::~KspFunctionLogger(v23);
  return v11;
}

```

## disassembly

```asm
0x1800954dc  mov     [rsp-8+arg_8], rbx
0x1800954e1  mov     [rsp-8+arg_18], r9d
0x1800954e6  push    rbp
0x1800954e7  push    rsi
0x1800954e8  push    r13
0x1800954ea  push    r14
0x1800954ec  push    r15
0x1800954ee  lea     rbp, [rsp-27h]
0x1800954f3  sub     rsp, 0B0h
0x1800954fa  mov     rsi, r8
0x1800954fd  mov     r14d, edx
0x180095500  mov     r15, rcx
0x180095503  mov     r8b, 1; bool
0x180095506  lea     rdx, aCfb; "CFB"
0x18009550d  lea     rcx, [rbp+47h+var_40]; this
0x180095511  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x180095516  nop
0x180095517  mov     r13d, 10h
0x18009551d  mov     [rbp+47h+pbInput], r13d
0x180095521  mov     [rbp+47h+arg_18], 0
0x180095528  test    r15, r15
0x18009552b  jz      loc_1800957D9
0x180095531  test    r14d, r14d
0x180095534  jz      loc_1800957D9
0x18009553a  test    rsi, rsi
0x18009553d  jz      loc_1800957D9
0x180095543  mov     rbx, [rbp+47h+arg_20]
0x180095547  test    rbx, rbx
0x18009554a  jz      loc_1800957D9
0x180095550  cmp     [rbp+47h+cbInput], 0
0x180095554  jz      loc_1800957D9
0x18009555a  mov     edx, r13d
0x18009555d  lea     rcx, [rbp+47h+pbIV]
0x180095561  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@_KAEBU?$secure_allocator@E@wil@@@Z; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(unsigned __int64,wil::secure_allocator<uchar> const &)
0x180095566  nop
0x180095567  mov     [rbp+47h+phAlgorithm], 0
0x18009556f  xor     r9d, r9d; dwFlags
0x180095572  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x180095579  lea     rdx, aAes; "AES"
0x180095580  lea     rcx, [rbp+47h+phAlgorithm]; phAlgorithm
0x180095584  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18009558b  nop     dword ptr [rax+rax+00h]
0x180095590  test    eax, eax
0x180095592  jns     short loc_1800955C6
0x180095594  mov     rcx, [rbp+4Fh]; this
0x180095598  mov     r9d, eax; char *
0x18009559b  lea     r8, aOnecoreBaseNgs_27; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x1800955a2  mov     edx, 7A0h; void *
0x1800955a7  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800955ac  mov     ebx, eax
0x1800955ae  lea     rcx, [rbp+47h+phAlgorithm]
0x1800955b2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800955b7  nop
0x1800955b8  lea     rcx, [rbp+47h+pbIV]
0x1800955bc  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x1800955c1  jmp     loc_1800957F7
0x1800955c6  mov     [rbp+47h+phKey], 0
0x1800955ce  mov     [rsp+0D0h+dwFlags], 0; dwFlags
0x1800955d6  mov     [rsp+0D0h+cbSecret], r14d; cbSecret
0x1800955db  mov     [rsp+0D0h+pbSecret], r15; int
0x1800955e0  xor     r9d, r9d; cbKeyObject
0x1800955e3  xor     r8d, r8d; pbKeyObject
0x1800955e6  lea     rdx, [rbp+47h+phKey]; phKey
0x1800955ea  mov     rcx, [rbp+47h+phAlgorithm]; hAlgorithm
0x1800955ee  call    cs:__imp_BCryptGenerateSymmetricKey
0x1800955f5  nop     dword ptr [rax+rax+00h]
0x1800955fa  test    eax, eax
0x1800955fc  jns     short loc_180095623
0x1800955fe  mov     edx, 7A9h; void *
0x180095603  lea     r8, aOnecoreBaseNgs_27; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18009560a  mov     r9d, eax; char *
0x18009560d  mov     rcx, [rbp+4Fh]; this
0x180095611  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180095616  mov     ebx, eax
0x180095618  lea     rcx, [rbp+47h+phKey]
0x18009561c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180095621  jmp     short loc_1800955AE
0x180095623  mov     dword ptr [rsp+0D0h+pbSecret], 0; dwFlags
0x18009562b  mov     r9d, 20h ; ' '; cbInput
0x180095631  lea     r8, pbInput; "ChainingModeCFB"
0x180095638  lea     rdx, aChainingmode; "ChainingMode"
0x18009563f  mov     rcx, [rbp+47h+phKey]; hObject
0x180095643  call    cs:__imp_BCryptSetProperty
0x18009564a  nop     dword ptr [rax+rax+00h]
0x18009564f  test    eax, eax
0x180095651  jns     short loc_18009565A
0x180095653  mov     edx, 7AFh
0x180095658  jmp     short loc_180095603
0x18009565a  mov     dword ptr [rsp+0D0h+pbSecret], 0; dwFlags
0x180095662  mov     r9d, 4; cbInput
0x180095668  lea     r8, [rbp+47h+pbInput]; pbInput
0x18009566c  lea     rdx, aMessageblockle; "MessageBlockLength"
0x180095673  mov     rcx, [rbp+47h+phKey]; hObject
0x180095677  call    cs:__imp_BCryptSetProperty
0x18009567e  nop     dword ptr [rax+rax+00h]
0x180095683  test    eax, eax
0x180095685  jns     short loc_180095691
0x180095687  mov     edx, 7B5h
0x18009568c  jmp     loc_180095603
0x180095691  mov     r8, r13
0x180095694  mov     rdx, rsi
0x180095697  lea     rcx, [rbp+47h+pbIV]
0x18009569b  call    ??$_Assign_counted_range@PEAE@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXPEAE_K@Z; std::vector<uchar,wil::secure_allocator<uchar>>::_Assign_counted_range<uchar *>(uchar *,unsigned __int64)
0x1800956a0  mov     rax, [rbp+47h+pbIV]
0x1800956a4  mov     r14d, 1
0x1800956aa  mov     [rsp+0D0h+var_88], r14d; dwFlags
0x1800956af  lea     rcx, [rbp+47h+arg_18]
0x1800956b3  mov     [rsp+0D0h+pcbResult], rcx; pcbResult
0x1800956b8  mov     [rsp+0D0h+cbOutput], 0; cbOutput
0x1800956c0  mov     qword ptr [rsp+0D0h+dwFlags], 0; pbOutput
0x1800956c9  mov     [rsp+0D0h+cbSecret], r13d; cbIV
0x1800956ce  mov     [rsp+0D0h+pbSecret], rax; pbIV
0x1800956d3  xor     r9d, r9d; pPaddingInfo
0x1800956d6  mov     r8d, [rbp+47h+cbInput]; cbInput
0x1800956da  mov     rdx, rbx; pbInput
0x1800956dd  mov     rcx, [rbp+47h+phKey]; hKey
0x1800956e1  call    cs:__imp_BCryptEncrypt
0x1800956e8  nop     dword ptr [rax+rax+00h]
0x1800956ed  test    eax, eax
0x1800956ef  jns     short loc_1800956FB
0x1800956f1  mov     edx, 7C1h
0x1800956f6  jmp     loc_180095603
0x1800956fb  mov     edx, [rbp+47h+arg_18]
0x1800956fe  lea     rcx, [rbp+47h+pbOutput]
0x180095702  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@_KAEBU?$secure_allocator@E@wil@@@Z; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(unsigned __int64,wil::secure_allocator<uchar> const &)
0x180095707  nop
0x180095708  mov     r8, r13
0x18009570b  mov     rdx, rsi
0x18009570e  lea     rcx, [rbp+47h+pbIV]
0x180095712  call    ??$_Assign_counted_range@PEAE@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXPEAE_K@Z; std::vector<uchar,wil::secure_allocator<uchar>>::_Assign_counted_range<uchar *>(uchar *,unsigned __int64)
0x180095717  mov     eax, [rbp+47h+arg_18]
0x18009571a  mov     rdx, [rbp+47h+pbOutput]
0x18009571e  mov     r8, [rbp+47h+pbIV]
0x180095722  mov     [rsp+0D0h+var_88], r14d; dwFlags
0x180095727  lea     rcx, [rbp+47h+arg_18]
0x18009572b  mov     [rsp+0D0h+pcbResult], rcx; pcbResult
0x180095730  mov     [rsp+0D0h+cbOutput], eax; cbOutput
0x180095734  mov     qword ptr [rsp+0D0h+dwFlags], rdx; pbOutput
0x180095739  mov     [rsp+0D0h+cbSecret], r13d; cbIV
0x18009573e  mov     [rsp+0D0h+pbSecret], r8; int
0x180095743  xor     r9d, r9d; pPaddingInfo
0x180095746  mov     r8d, [rbp+47h+cbInput]; cbInput
0x18009574a  mov     rdx, rbx; pbInput
0x18009574d  mov     rcx, [rbp+47h+phKey]; hKey
0x180095751  call    cs:__imp_BCryptEncrypt
0x180095758  nop     dword ptr [rax+rax+00h]
0x18009575d  test    eax, eax
0x18009575f  jns     short loc_180095789
0x180095761  mov     rcx, [rbp+4Fh]; this
0x180095765  mov     r9d, eax; char *
0x180095768  lea     r8, aOnecoreBaseNgs_27; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18009576f  mov     edx, 7CFh; void *
0x180095774  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180095779  mov     ebx, eax
0x18009577b  lea     rcx, [rbp+47h+pbOutput]
0x18009577f  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x180095784  jmp     loc_180095618
0x180095789  mov     edx, [rbp+47h+cbInput]; DestinationSize
0x18009578c  mov     r9d, edx; SourceSize
0x18009578f  mov     r8, [rbp+47h+pbOutput]; Source
0x180095793  mov     rcx, rbx; Destination
0x180095796  call    memcpy_s
0x18009579b  mov     r9, r13; SourceSize
0x18009579e  mov     r8, [rbp+47h+pbIV]; Source
0x1800957a2  mov     rdx, r13; DestinationSize
0x1800957a5  mov     rcx, rsi; Destination
0x1800957a8  call    memcpy_s
0x1800957ad  nop
0x1800957ae  lea     rcx, [rbp+47h+pbOutput]
0x1800957b2  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x1800957b7  nop
0x1800957b8  lea     rcx, [rbp+47h+phKey]
0x1800957bc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800957c1  nop
0x1800957c2  lea     rcx, [rbp+47h+phAlgorithm]
0x1800957c6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800957cb  nop
0x1800957cc  lea     rcx, [rbp+47h+pbIV]
0x1800957d0  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x1800957d5  xor     ebx, ebx
0x1800957d7  jmp     short loc_1800957F7
0x1800957d9  mov     rcx, [rbp+4Fh]; this
0x1800957dd  mov     ebx, 80070057h
0x1800957e2  mov     r9d, ebx; char *
0x1800957e5  lea     r8, aOnecoreBaseNgs_27; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x1800957ec  mov     edx, 799h; void *
0x1800957f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800957f6  nop
0x1800957f7  lea     rcx, [rbp+47h+var_40]; this
0x1800957fb  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180095800  mov     eax, ebx
0x180095802  mov     rbx, [rsp+0D0h+arg_8]
0x18009580a  add     rsp, 0B0h
0x180095811  pop     r15
0x180095813  pop     r14
0x180095815  pop     r13
0x180095817  pop     rsi
0x180095818  pop     rbp
0x180095819  retn
```
