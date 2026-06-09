# TpmPolicySession::GenerateAuthorizationHmac(uchar const *,ulong,uchar const *,ulong,uchar const *,ulong,uchar *,ulong,ulong *)

- ea: `0x1800a8604`
- end: `0x1800a89a5`
- name: `?GenerateAuthorizationHmac@TpmPolicySession@@YAJPEBEK0K0KPEAEKPEAK@Z`
- size: `929`
- prototype: `__int64 __fastcall(TpmPolicySession *__hidden this, ULONG cbSecret, PUCHAR pbInput, ULONG cbInput, PUCHAR, ULONG, PUCHAR, ULONG cbOutput, UCHAR, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18004f3f8`

## callees

- `0x18000782c`
- `0x180010990`
- `0x180028ca0`
- `0x18004826c`
- `0x18009fee8`
- `0x1800a8604`

## import_xrefs

- `bcrypt!BCryptFinishHash` at `0x1800a8800`
- `bcrypt!BCryptFinishHash` at `0x1800a8935`
- `bcrypt!BCryptFinishHash` at `0x1800a8800`
- `bcrypt!BCryptFinishHash` at `0x1800a8935`
- `bcrypt!BCryptHashData` at `0x1800a86e5`
- `bcrypt!BCryptHashData` at `0x1800a8747`
- `bcrypt!BCryptHashData` at `0x1800a87a2`
- `bcrypt!BCryptHashData` at `0x1800a88d4`
- `bcrypt!BCryptHashData` at `0x1800a86e5`
- `bcrypt!BCryptHashData` at `0x1800a8747`
- `bcrypt!BCryptHashData` at `0x1800a87a2`
- `bcrypt!BCryptHashData` at `0x1800a88d4`
- `bcrypt!BCryptCreateHash` at `0x1800a8694`
- `bcrypt!BCryptCreateHash` at `0x1800a887d`
- `bcrypt!BCryptCreateHash` at `0x1800a8694`
- `bcrypt!BCryptCreateHash` at `0x1800a887d`

## string_xrefs

- `0x1800a8641`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x1800a86a9`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x1800a86fa`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x1800a875c`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x1800a87b7`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x1800a8815`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x1800a8892`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x1800a88e9`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x1800a894a`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`

## pseudocode

```c
__int64 __fastcall TpmPolicySession::GenerateAuthorizationHmac(
        UCHAR *this,
        ULONG cbSecret,
        PUCHAR pbInput,
        ULONG cbInput,
        PUCHAR a5,
        ULONG cbInputa,
        PUCHAR a7,
        ULONG cbOutput,
        _DWORD *pbInputa)
{
  __int64 result; // rax
  NTSTATUS v14; // eax
  unsigned int v15; // ebx
  const char *v16; // r9
  NTSTATUS v17; // eax
  unsigned int v18; // ebx
  NTSTATUS v19; // eax
  unsigned int v20; // ebx
  NTSTATUS v21; // eax
  unsigned int v22; // ebx
  UCHAR *v23; // rbx
  ULONG v24; // edi
  NTSTATUS v25; // eax
  unsigned int v26; // ebx
  NTSTATUS Hash; // eax
  unsigned int v28; // ebx
  NTSTATUS v29; // eax
  unsigned int v30; // ebx
  NTSTATUS v31; // eax
  unsigned int v32; // ebx
  int pbSecret; // [rsp+20h] [rbp-68h]
  int pbSecreta; // [rsp+20h] [rbp-68h]
  int pbSecretb; // [rsp+20h] [rbp-68h]
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-48h] BYREF
  PUCHAR pbOutput; // [rsp+48h] [rbp-40h] BYREF
  int v38; // [rsp+50h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  *pbInputa = 32;
  if ( cbOutput >= 0x20 )
  {
    try
    {
      std::vector<unsigned char>::vector<unsigned char>(&pbOutput, 32);
      phHash = 0;
      v14 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x41, &phHash, 0, 0, 0, 0, 0);
      if ( v14 >= 0 )
      {
        v17 = BCryptHashData(phHash, pbInput, cbInput, 0);
        if ( v17 >= 0 )
        {
          LODWORD(pbInputa) = -486539265;
          v19 = BCryptHashData(phHash, (PUCHAR)&pbInputa, 4u, 0);
          if ( v19 >= 0 )
          {
            v21 = BCryptHashData(phHash, a5, cbInputa, 0);
            if ( v21 >= 0 )
            {
              v23 = pbOutput;
              v24 = v38 - (_DWORD)pbOutput;
              v25 = BCryptFinishHash(phHash, pbOutput, v38 - (_DWORD)pbOutput, 0);
              if ( v25 >= 0 )
              {
                wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phHash);
                pbInputa = 0;
                Hash = BCryptCreateHash(
                         (BCRYPT_ALG_HANDLE)0xB1,
                         (BCRYPT_HASH_HANDLE *)&pbInputa,
                         0,
                         0,
                         this,
                         cbSecret,
                         0);
                if ( Hash >= 0 )
                {
                  v29 = BCryptHashData(pbInputa, v23, v24, 0);
                  if ( v29 >= 0 )
                  {
                    v31 = BCryptFinishHash(pbInputa, a7, cbOutput, 0);
                    if ( v31 >= 0 )
                    {
                      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInputa);
                      std::vector<unsigned char>::_Tidy(&pbOutput);
                      result = 0;
                    }
                    else
                    {
                      v32 = wil::details::in1diag3::Return_NtStatus(
                              retaddr,
                              (void *)0x1FE,
                              (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
                              (const char *)(unsigned int)v31,
                              pbSecretb);
                      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInputa);
                      std::vector<unsigned char>::_Tidy(&pbOutput);
                      result = v32;
                    }
                  }
                  else
                  {
                    v30 = wil::details::in1diag3::Return_NtStatus(
                            retaddr,
                            (void *)0x1F7,
                            (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
                            (const char *)(unsigned int)v29,
                            pbSecretb);
                    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInputa);
                    std::vector<unsigned char>::_Tidy(&pbOutput);
                    result = v30;
                  }
                }
                else
                {
                  v28 = wil::details::in1diag3::Return_NtStatus(
                          retaddr,
                          (void *)0x1F0,
                          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
                          (const char *)(unsigned int)Hash,
                          pbSecretb);
                  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInputa);
                  std::vector<unsigned char>::_Tidy(&pbOutput);
                  result = v28;
                }
              }
              else
              {
                v26 = wil::details::in1diag3::Return_NtStatus(
                        retaddr,
                        (void *)0x1E2,
                        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
                        (const char *)(unsigned int)v25,
                        pbSecreta);
                wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phHash);
                std::vector<unsigned char>::_Tidy(&pbOutput);
                result = v26;
              }
            }
            else
            {
              v22 = wil::details::in1diag3::Return_NtStatus(
                      retaddr,
                      (void *)0x1DB,
                      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
                      (const char *)(unsigned int)v21,
                      pbSecreta);
              wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phHash);
              std::vector<unsigned char>::_Tidy(&pbOutput);
              result = v22;
            }
          }
          else
          {
            v20 = wil::details::in1diag3::Return_NtStatus(
                    retaddr,
                    (void *)0x1D4,
                    (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
                    (const char *)(unsigned int)v19,
                    pbSecreta);
            wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phHash);
            std::vector<unsigned char>::_Tidy(&pbOutput);
            result = v20;
          }
        }
        else
        {
          v18 = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x1C7,
                  (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
                  (const char *)(unsigned int)v17,
                  pbSecreta);
          wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phHash);
          std::vector<unsigned char>::_Tidy(&pbOutput);
          result = v18;
        }
      }
      else
      {
        v15 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0x1C0,
                (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
                (const char *)(unsigned int)v14,
                pbSecreta);
        wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phHash);
        std::vector<unsigned char>::_Tidy(&pbOutput);
        result = v15;
      }
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x201,
                             (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
                             v16);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B2,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
      (const char *)0x8007007ALL,
      pbSecret);
    return 2147942522LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800a8604  push    rbx
0x1800a8606  push    rsi
0x1800a8607  push    rdi
0x1800a8608  push    r14
0x1800a860a  sub     rsp, 68h
0x1800a860e  mov     ebx, r9d
0x1800a8611  mov     rdi, r8
0x1800a8614  mov     esi, edx
0x1800a8616  mov     r14, rcx
0x1800a8619  mov     edx, 20h ; ' '
0x1800a861e  mov     rax, [rsp+88h+pbInput]
0x1800a8626  mov     [rax], edx
0x1800a8628  cmp     [rsp+88h+cbOutput], edx
0x1800a862f  jnb     short loc_1800A8659
0x1800a8631  mov     rcx, [rsp+88h]; this
0x1800a8639  mov     ebx, 8007007Ah
0x1800a863e  mov     r9d, ebx; char *
0x1800a8641  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1800a8648  mov     edx, 1B2h; void *
0x1800a864d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a8652  mov     eax, ebx
0x1800a8654  jmp     loc_1800A899B
0x1800a8659  lea     rcx, [rsp+88h+pbOutput]
0x1800a865e  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x1800a8663  mov     [rsp+88h+phHash], 0
0x1800a866c  mov     [rsp+88h+dwFlags], 0; dwFlags
0x1800a8674  mov     [rsp+88h+cbSecret], 0; cbSecret
0x1800a867c  mov     [rsp+88h+pbSecret], 0; int
0x1800a8685  xor     r9d, r9d; cbHashObject
0x1800a8688  xor     r8d, r8d; pbHashObject
0x1800a868b  lea     rdx, [rsp+88h+phHash]; phHash
0x1800a8690  lea     ecx, [r9+41h]; hAlgorithm
0x1800a8694  call    cs:__imp_BCryptCreateHash
0x1800a869a  test    eax, eax
0x1800a869c  jns     short loc_1800A86D7
0x1800a869e  mov     rcx, [rsp+88h]; this
0x1800a86a6  mov     r9d, eax; char *
0x1800a86a9  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1800a86b0  mov     edx, 1C0h; void *
0x1800a86b5  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800a86ba  mov     ebx, eax
0x1800a86bc  lea     rcx, [rsp+88h+phHash]
0x1800a86c1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800a86c6  lea     rcx, [rsp+88h+pbOutput]
0x1800a86cb  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800a86d0  mov     eax, ebx
0x1800a86d2  jmp     loc_1800A899B
0x1800a86d7  xor     r9d, r9d; dwFlags
0x1800a86da  mov     r8d, ebx; cbInput
0x1800a86dd  mov     rdx, rdi; pbInput
0x1800a86e0  mov     rcx, [rsp+88h+phHash]; hHash
0x1800a86e5  call    cs:__imp_BCryptHashData
0x1800a86eb  test    eax, eax
0x1800a86ed  jns     short loc_1800A8728
0x1800a86ef  mov     rcx, [rsp+88h]; this
0x1800a86f7  mov     r9d, eax; char *
0x1800a86fa  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1800a8701  mov     edx, 1C7h; void *
0x1800a8706  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800a870b  mov     ebx, eax
0x1800a870d  lea     rcx, [rsp+88h+phHash]
0x1800a8712  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800a8717  lea     rcx, [rsp+88h+pbOutput]
0x1800a871c  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800a8721  mov     eax, ebx
0x1800a8723  jmp     loc_1800A899B
0x1800a8728  mov     dword ptr [rsp+88h+pbInput], 0E2FFFFFFh
0x1800a8733  xor     r9d, r9d; dwFlags
0x1800a8736  lea     r8d, [r9+4]; cbInput
0x1800a873a  lea     rdx, [rsp+88h+pbInput]; pbInput
0x1800a8742  mov     rcx, [rsp+88h+phHash]; hHash
0x1800a8747  call    cs:__imp_BCryptHashData
0x1800a874d  test    eax, eax
0x1800a874f  jns     short loc_1800A878A
0x1800a8751  mov     rcx, [rsp+88h]; this
0x1800a8759  mov     r9d, eax; char *
0x1800a875c  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1800a8763  mov     edx, 1D4h; void *
0x1800a8768  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800a876d  mov     ebx, eax
0x1800a876f  lea     rcx, [rsp+88h+phHash]
0x1800a8774  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800a8779  lea     rcx, [rsp+88h+pbOutput]
0x1800a877e  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800a8783  mov     eax, ebx
0x1800a8785  jmp     loc_1800A899B
0x1800a878a  xor     r9d, r9d; dwFlags
0x1800a878d  mov     r8d, [rsp+88h+cbInput]; cbInput
0x1800a8795  mov     rdx, [rsp+88h+arg_20]; pbInput
0x1800a879d  mov     rcx, [rsp+88h+phHash]; hHash
0x1800a87a2  call    cs:__imp_BCryptHashData
0x1800a87a8  test    eax, eax
0x1800a87aa  jns     short loc_1800A87E5
0x1800a87ac  mov     rcx, [rsp+88h]; this
0x1800a87b4  mov     r9d, eax; char *
0x1800a87b7  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1800a87be  mov     edx, 1DBh; void *
0x1800a87c3  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800a87c8  mov     ebx, eax
0x1800a87ca  lea     rcx, [rsp+88h+phHash]
0x1800a87cf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800a87d4  lea     rcx, [rsp+88h+pbOutput]
0x1800a87d9  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800a87de  mov     eax, ebx
0x1800a87e0  jmp     loc_1800A899B
0x1800a87e5  mov     eax, [rsp+88h+var_38]
0x1800a87e9  mov     rbx, [rsp+88h+pbOutput]
0x1800a87ee  sub     eax, ebx
0x1800a87f0  mov     edi, eax
0x1800a87f2  xor     r9d, r9d; dwFlags
0x1800a87f5  mov     r8d, eax; cbOutput
0x1800a87f8  mov     rdx, rbx; pbOutput
0x1800a87fb  mov     rcx, [rsp+88h+phHash]; hHash
0x1800a8800  call    cs:__imp_BCryptFinishHash
0x1800a8806  test    eax, eax
0x1800a8808  jns     short loc_1800A8843
0x1800a880a  mov     rcx, [rsp+88h]; this
0x1800a8812  mov     r9d, eax; char *
0x1800a8815  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1800a881c  mov     edx, 1E2h; void *
0x1800a8821  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800a8826  mov     ebx, eax
0x1800a8828  lea     rcx, [rsp+88h+phHash]
0x1800a882d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800a8832  lea     rcx, [rsp+88h+pbOutput]
0x1800a8837  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800a883c  mov     eax, ebx
0x1800a883e  jmp     loc_1800A899B
0x1800a8843  lea     rcx, [rsp+88h+phHash]
0x1800a8848  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800a884d  mov     [rsp+88h+pbInput], 0
0x1800a8859  mov     [rsp+88h+dwFlags], 0; dwFlags
0x1800a8861  mov     [rsp+88h+cbSecret], esi; cbSecret
0x1800a8865  mov     [rsp+88h+pbSecret], r14; int
0x1800a886a  xor     r9d, r9d; cbHashObject
0x1800a886d  xor     r8d, r8d; pbHashObject
0x1800a8870  lea     rdx, [rsp+88h+pbInput]; phHash
0x1800a8878  mov     ecx, 0B1h; hAlgorithm
0x1800a887d  call    cs:__imp_BCryptCreateHash
0x1800a8883  test    eax, eax
0x1800a8885  jns     short loc_1800A88C3
0x1800a8887  mov     rcx, [rsp+88h]; this
0x1800a888f  mov     r9d, eax; char *
0x1800a8892  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1800a8899  mov     edx, 1F0h; void *
0x1800a889e  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800a88a3  mov     ebx, eax
0x1800a88a5  lea     rcx, [rsp+88h+pbInput]
0x1800a88ad  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800a88b2  lea     rcx, [rsp+88h+pbOutput]
0x1800a88b7  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800a88bc  mov     eax, ebx
0x1800a88be  jmp     loc_1800A899B
0x1800a88c3  xor     r9d, r9d; dwFlags
0x1800a88c6  mov     r8d, edi; cbInput
0x1800a88c9  mov     rdx, rbx; pbInput
0x1800a88cc  mov     rcx, [rsp+88h+pbInput]; hHash
0x1800a88d4  call    cs:__imp_BCryptHashData
0x1800a88da  test    eax, eax
0x1800a88dc  jns     short loc_1800A891A
0x1800a88de  mov     rcx, [rsp+88h]; this
0x1800a88e6  mov     r9d, eax; char *
0x1800a88e9  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1800a88f0  mov     edx, 1F7h; void *
0x1800a88f5  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800a88fa  mov     ebx, eax
0x1800a88fc  lea     rcx, [rsp+88h+pbInput]
0x1800a8904  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800a8909  lea     rcx, [rsp+88h+pbOutput]
0x1800a890e  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800a8913  mov     eax, ebx
0x1800a8915  jmp     loc_1800A899B
0x1800a891a  xor     r9d, r9d; dwFlags
0x1800a891d  mov     r8d, [rsp+88h+cbOutput]; cbOutput
0x1800a8925  mov     rdx, [rsp+88h+arg_30]; pbOutput
0x1800a892d  mov     rcx, [rsp+88h+pbInput]; hHash
0x1800a8935  call    cs:__imp_BCryptFinishHash
0x1800a893b  test    eax, eax
0x1800a893d  jns     short loc_1800A8978
0x1800a893f  mov     rcx, [rsp+88h]; this
0x1800a8947  mov     r9d, eax; char *
0x1800a894a  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1800a8951  mov     edx, 1FEh; void *
0x1800a8956  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800a895b  mov     ebx, eax
0x1800a895d  lea     rcx, [rsp+88h+pbInput]
0x1800a8965  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800a896a  lea     rcx, [rsp+88h+pbOutput]
0x1800a896f  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800a8974  mov     eax, ebx
0x1800a8976  jmp     short loc_1800A899B
0x1800a8978  lea     rcx, [rsp+88h+pbInput]
0x1800a8980  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800a8985  lea     rcx, [rsp+88h+pbOutput]
0x1800a898a  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800a898f  nop
0x1800a8990  xor     eax, eax
0x1800a8992  jmp     short loc_1800A899B
0x1800a8994  mov     eax, [rsp+88h+cbOutput]
0x1800a899b  add     rsp, 68h
0x1800a899f  pop     r14
0x1800a89a1  pop     rdi
0x1800a89a2  pop     rsi
0x1800a89a3  pop     rbx
0x1800a89a4  retn
```
