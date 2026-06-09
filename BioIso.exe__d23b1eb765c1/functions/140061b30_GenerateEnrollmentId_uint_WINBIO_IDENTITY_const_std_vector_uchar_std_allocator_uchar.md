# GenerateEnrollmentId(uint,_WINBIO_IDENTITY const *,std::vector<uchar,std::allocator<uchar>> *)

- ea: `0x140061b30`
- end: `0x140061ccf`
- name: `?GenerateEnrollmentId@@YAJIPEBU_WINBIO_IDENTITY@@PEAV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `415`
- prototype: `__int64 __fastcall(unsigned int, __int64, __int64)`
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400098b0`
- `0x140055280`
- `0x140055800`

## callees

- `0x14000a420`
- `0x14000ae0c`
- `0x14000d990`
- `0x14002ae40`
- `0x14002b430`
- `0x1400408d0`
- `0x140041194`
- `0x1400589a0`
- `0x14005f5dc`
- `0x140061b30`
- `0x140061cd8`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x140061ba2`
- `bcrypt!BCryptCreateHash` at `0x140061ba2`
- `bcrypt!BCryptHashData` at `0x140061bc8`
- `bcrypt!BCryptHashData` at `0x140061c06`
- `bcrypt!BCryptHashData` at `0x140061bc8`
- `bcrypt!BCryptHashData` at `0x140061c06`
- `bcrypt!BCryptFinishHash` at `0x140061c3e`
- `bcrypt!BCryptFinishHash` at `0x140061c3e`

## string_xrefs

- `0x140061b5d`: `onecore\ds\security\biometrics\service\trustlet\exe\secureenrollments.cpp`
- `0x140061be4`: `onecore\ds\security\biometrics\service\trustlet\exe\secureenrollments.cpp`
- `0x140061c55`: `onecore\ds\security\biometrics\service\trustlet\exe\secureenrollments.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall GenerateEnrollmentId(unsigned int a1, __int64 a2, __int64 a3)
{
  unsigned int v5; // ebx
  NTSTATUS v6; // eax
  __int64 v7; // rdx
  NTSTATUS v8; // eax
  unsigned __int64 v9; // rdx
  unsigned __int8 v10; // cl
  __int64 v11; // rcx
  int pbSecret; // [rsp+20h] [rbp-40h]
  int pbSecreta; // [rsp+20h] [rbp-40h]
  PUCHAR pbOutput; // [rsp+40h] [rbp-20h] BYREF
  int v16; // [rsp+48h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]
  unsigned int pbInput; // [rsp+70h] [rbp+10h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+78h] [rbp+18h] BYREF

  pbInput = a1;
  if ( *(_DWORD *)a2 == 3 )
  {
    phHash = 0;
    v6 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x41, &phHash, 0, 0, 0, 0, 0);
    if ( v6 >= 0 )
    {
      v6 = BCryptHashData(phHash, (PUCHAR)&pbInput, 4u, 0);
      if ( v6 >= 0 )
      {
        v6 = BCryptHashData(phHash, (PUCHAR)(a2 + 8), *(_DWORD *)(a2 + 4), 0);
        if ( v6 >= 0 )
        {
          std::vector<unsigned char>::vector<unsigned char>(&pbOutput, 32);
          v8 = BCryptFinishHash(phHash, pbOutput, v16 - (_DWORD)pbOutput, 0);
          if ( v8 >= 0 )
          {
            if ( VsmUtils::Velocity::IsEnabled<wil::Feature<__WilFeatureTraits_Feature_AddLoggingForFaceAuthErrors>>()
              && BioIsoProvider::IsEnabled(v10, v9) )
            {
              BioIsoProvider::Instance();
              BioIsoProvider::GenerateEnrollmentId_(v11, pbInput, a2, &pbOutput);
            }
            std::vector<unsigned char>::operator=(a3, &pbOutput);
            std::vector<unsigned char>::_Tidy((__int64)&pbOutput);
            v5 = 0;
          }
          else
          {
            v5 = wil::details::in1diag3::Return_NtStatus(
                   retaddr,
                   (void *)0x455,
                   (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\secureenrollments.cpp",
                   (const char *)(unsigned int)v8,
                   pbSecreta);
            std::vector<unsigned char>::_Tidy((__int64)&pbOutput);
          }
          goto LABEL_16;
        }
        v7 = 1103;
      }
      else
      {
        v7 = 1099;
      }
    }
    else
    {
      v7 = 1094;
    }
    v5 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)v7,
           (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\secureenrollments.cpp",
           (const char *)(unsigned int)v6,
           pbSecreta);
LABEL_16:
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phHash);
    return v5;
  }
  v5 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x43E,
    (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\secureenrollments.cpp",
    (const char *)0x80070057LL,
    pbSecret);
  return v5;
}

```

## disassembly

```asm
0x140061b30  mov     [rsp-8+arg_10], rbx
0x140061b35  mov     [rsp-8+arg_18], rdi
0x140061b3a  mov     [rsp-8+pbInput], ecx
0x140061b3e  push    rbp
0x140061b3f  mov     rbp, rsp
0x140061b42  sub     rsp, 60h
0x140061b46  mov     rdi, r8
0x140061b49  mov     rbx, rdx
0x140061b4c  cmp     dword ptr [rdx], 3
0x140061b4f  jz      short loc_140061B73
0x140061b51  mov     rcx, [rbp+8]; this
0x140061b55  mov     ebx, 80070057h
0x140061b5a  mov     r9d, ebx; char *
0x140061b5d  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\biometrics\\serv"...
0x140061b64  mov     edx, 43Eh; void *
0x140061b69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140061b6e  jmp     loc_140061CBA
0x140061b73  mov     [rbp+phHash], 0
0x140061b7b  mov     [rsp+60h+dwFlags], 0; dwFlags
0x140061b83  mov     [rsp+60h+cbSecret], 0; cbSecret
0x140061b8b  mov     [rsp+60h+pbSecret], 0; int
0x140061b94  xor     r9d, r9d; cbHashObject
0x140061b97  xor     r8d, r8d; pbHashObject
0x140061b9a  lea     rdx, [rbp+phHash]; phHash
0x140061b9e  lea     ecx, [r9+41h]; hAlgorithm
0x140061ba2  call    cs:__imp_BCryptCreateHash
0x140061ba9  nop     dword ptr [rax+rax+00h]
0x140061bae  test    eax, eax
0x140061bb0  jns     short loc_140061BB9
0x140061bb2  mov     edx, 446h
0x140061bb7  jmp     short loc_140061BDD
0x140061bb9  xor     r9d, r9d; dwFlags
0x140061bbc  lea     r8d, [r9+4]; cbInput
0x140061bc0  lea     rdx, [rbp+pbInput]; pbInput
0x140061bc4  mov     rcx, [rbp+phHash]; hHash
0x140061bc8  call    cs:__imp_BCryptHashData
0x140061bcf  nop     dword ptr [rax+rax+00h]
0x140061bd4  test    eax, eax
0x140061bd6  jns     short loc_140061BF7
0x140061bd8  mov     edx, 44Bh; void *
0x140061bdd  mov     rcx, [rbp+8]; this
0x140061be1  mov     r9d, eax; char *
0x140061be4  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\biometrics\\serv"...
0x140061beb  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x140061bf0  mov     ebx, eax
0x140061bf2  jmp     loc_140061CB1
0x140061bf7  lea     rdx, [rbx+8]; pbInput
0x140061bfb  xor     r9d, r9d; dwFlags
0x140061bfe  mov     r8d, [rbx+4]; cbInput
0x140061c02  mov     rcx, [rbp+phHash]; hHash
0x140061c06  call    cs:__imp_BCryptHashData
0x140061c0d  nop     dword ptr [rax+rax+00h]
0x140061c12  test    eax, eax
0x140061c14  jns     short loc_140061C1D
0x140061c16  mov     edx, 44Fh
0x140061c1b  jmp     short loc_140061BDD
0x140061c1d  mov     edx, 20h ; ' '
0x140061c22  lea     rcx, [rbp+pbOutput]
0x140061c26  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x140061c2b  nop
0x140061c2c  mov     rdx, [rbp+pbOutput]; pbOutput
0x140061c30  mov     r8d, [rbp+var_18]
0x140061c34  sub     r8d, edx; cbOutput
0x140061c37  xor     r9d, r9d; dwFlags
0x140061c3a  mov     rcx, [rbp+phHash]; hHash
0x140061c3e  call    cs:__imp_BCryptFinishHash
0x140061c45  nop     dword ptr [rax+rax+00h]
0x140061c4a  test    eax, eax
0x140061c4c  jns     short loc_140061C73
0x140061c4e  mov     rcx, [rbp+8]; this
0x140061c52  mov     r9d, eax; char *
0x140061c55  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\biometrics\\serv"...
0x140061c5c  mov     edx, 455h; void *
0x140061c61  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x140061c66  mov     ebx, eax
0x140061c68  lea     rcx, [rbp+pbOutput]
0x140061c6c  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140061c71  jmp     short loc_140061CB1
0x140061c73  call    ??$IsEnabled@V?$Feature@U__WilFeatureTraits_Feature_AddLoggingForFaceAuthErrors@@@wil@@@Velocity@VsmUtils@@SA_NXZ; VsmUtils::Velocity::IsEnabled<wil::Feature<__WilFeatureTraits_Feature_AddLoggingForFaceAuthErrors>>(void)
0x140061c78  test    al, al
0x140061c7a  jz      short loc_140061C99
0x140061c7c  call    ?IsEnabled@BioIsoProvider@@SA_NE_K@Z; BioIsoProvider::IsEnabled(uchar,unsigned __int64)
0x140061c81  test    al, al
0x140061c83  jz      short loc_140061C99
0x140061c85  call    ?Instance@BioIsoProvider@@KAPEAV1@XZ; BioIsoProvider::Instance(void)
0x140061c8a  lea     r9, [rbp+pbOutput]
0x140061c8e  mov     r8, rbx
0x140061c91  mov     edx, [rbp+pbInput]
0x140061c94  call    ?GenerateEnrollmentId_@BioIsoProvider@@QEAAXIPEBU_WINBIO_IDENTITY@@PEBV?$vector@EV?$allocator@E@std@@@std@@@Z; BioIsoProvider::GenerateEnrollmentId_(uint,_WINBIO_IDENTITY const *,std::vector<uchar> const *)
0x140061c99  lea     rdx, [rbp+pbOutput]
0x140061c9d  mov     rcx, rdi
0x140061ca0  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x140061ca5  nop
0x140061ca6  lea     rcx, [rbp+pbOutput]
0x140061caa  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140061caf  xor     ebx, ebx
0x140061cb1  lea     rcx, [rbp+phHash]
0x140061cb5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140061cba  mov     eax, ebx
0x140061cbc  lea     r11, [rsp+60h+var_s0]
0x140061cc1  mov     rbx, [r11+20h]
0x140061cc5  mov     rdi, [r11+28h]
0x140061cc9  mov     rsp, r11
0x140061ccc  pop     rbp
0x140061ccd  retn
```
