# GenerateHmac

- ea: `0x1800a66a8`
- end: `0x1800a6862`
- name: `GenerateHmac`
- size: `442`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800a05b4`
- `0x1800a2340`
- `0x1800a2ba0`

## callees

- `0x18000782c`
- `0x18004826c`
- `0x180050b30`
- `0x1800527ac`
- `0x180069b58`
- `0x18009fee8`
- `0x1800a66a8`

## import_xrefs

- `bcrypt!BCryptFinishHash` at `0x1800a6812`
- `bcrypt!BCryptFinishHash` at `0x1800a6812`
- `bcrypt!BCryptGetProperty` at `0x1800a672f`
- `bcrypt!BCryptGetProperty` at `0x1800a672f`
- `bcrypt!BCryptHashData` at `0x1800a67f3`
- `bcrypt!BCryptHashData` at `0x1800a67f3`
- `bcrypt!BCryptCreateHash` at `0x1800a67b6`
- `bcrypt!BCryptCreateHash` at `0x1800a67b6`

## string_xrefs

- `0x1800a673d`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`
- `0x1800a676f`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`
- `0x1800a67c9`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`

## pseudocode

```c
__int64 __fastcall GenerateHmac(__int64 a1, UCHAR *a2, __int64 a3, UCHAR *a4, ULONG cbInput, PUCHAR a6, ULONG *a7)
{
  ULONG v8; // r15d
  PUCHAR v10; // rbx
  ULONG *v11; // rdi
  NTSTATUS Property; // eax
  UCHAR *v14; // rsi
  unsigned int v15; // ebx
  NTSTATUS Hash; // eax
  __int64 v17; // rdx
  ULONG v18; // eax
  int pcbResult; // [rsp+20h] [rbp-30h]
  int pcbResulta; // [rsp+20h] [rbp-30h]
  BCRYPT_HASH_HANDLE phHash[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  __int64 v23; // [rsp+80h] [rbp+30h] BYREF
  ULONG pbOutput; // [rsp+90h] [rbp+40h] BYREF

  v23 = a1;
  v8 = a3;
  if ( !(_DWORD)a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1, a2, a3);
  if ( !cbInput )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1, a2, a3);
  v10 = a6;
  if ( !a6 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1, a2, a3);
  v11 = a7;
  if ( !a7 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1, a2, a3);
  *(_QWORD *)v10 = 0;
  *v11 = 0;
  pbOutput = 0;
  LODWORD(v23) = 0;
  Property = BCryptGetProperty((BCRYPT_HANDLE)0xB1, L"HashDigestLength", (PUCHAR)&pbOutput, 4u, (ULONG *)&v23, 0);
  if ( Property < 0 )
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x41B,
             (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
             (const char *)(unsigned int)Property,
             pcbResult);
  wil::make_unique_hlocal_secure_nothrow<unsigned char [0]>(&a6, pbOutput);
  v14 = a6;
  if ( a6 )
  {
    phHash[0] = 0;
    Hash = BCryptCreateHash((BCRYPT_ALG_HANDLE)0xB1, phHash, 0, 0, a2, v8, 0);
    if ( Hash >= 0 )
    {
      Hash = BCryptHashData(phHash[0], a4, cbInput, 0);
      if ( Hash >= 0 )
      {
        Hash = BCryptFinishHash(phHash[0], v14, pbOutput, 0);
        if ( Hash >= 0 )
        {
          v18 = pbOutput;
          *(_QWORD *)v10 = v14;
          *v11 = v18;
          a6 = 0;
          wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(phHash);
          v15 = 0;
          goto LABEL_21;
        }
        v17 = 1080;
      }
      else
      {
        v17 = 1073;
      }
    }
    else
    {
      v17 = 1066;
    }
    v15 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)v17,
            (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
            (const char *)(unsigned int)Hash,
            pcbResulta);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(phHash);
  }
  else
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x41E,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
      (const char *)0x8007000ELL,
      pcbResult);
  }
LABEL_21:
  wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&a6);
  return v15;
}

```

## disassembly

```asm
0x1800a66a8  mov     [rsp-28h+arg_8], rbx
0x1800a66ad  mov     [rsp-28h+arg_18], rsi
0x1800a66b2  mov     [rsp-28h+arg_0], rcx
0x1800a66b7  push    rbp
0x1800a66b8  push    rdi
0x1800a66b9  push    r12
0x1800a66bb  push    r13
0x1800a66bd  push    r15
0x1800a66bf  mov     rbp, rsp
0x1800a66c2  sub     rsp, 50h
0x1800a66c6  xor     esi, esi
0x1800a66c8  mov     r12, r9
0x1800a66cb  mov     r15d, r8d
0x1800a66ce  mov     r13, rdx
0x1800a66d1  test    r8d, r8d
0x1800a66d4  jnz     short loc_1800A66DB
0x1800a66d6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800a66db  cmp     [rbp+cbInput], esi
0x1800a66de  ja      short loc_1800A66E5
0x1800a66e0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800a66e5  mov     rbx, [rbp+arg_28]
0x1800a66e9  test    rbx, rbx
0x1800a66ec  jnz     short loc_1800A66F3
0x1800a66ee  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800a66f3  mov     rdi, [rbp+arg_30]
0x1800a66f7  test    rdi, rdi
0x1800a66fa  jnz     short loc_1800A6701
0x1800a66fc  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800a6701  lea     rax, [rbp+arg_0]
0x1800a6705  mov     [rbx], rsi
0x1800a6708  mov     [rsp+50h+dwFlags], esi; dwFlags
0x1800a670c  lea     r8, [rbp+pbOutput]; pbOutput
0x1800a6710  mov     r9d, 4; cbOutput
0x1800a6716  mov     [rsp+50h+pcbResult], rax; int
0x1800a671b  lea     rdx, pszProperty; "HashDigestLength"
0x1800a6722  mov     [rdi], esi
0x1800a6724  mov     ecx, 0B1h; hObject
0x1800a6729  mov     [rbp+pbOutput], esi
0x1800a672c  mov     dword ptr [rbp+arg_0], esi
0x1800a672f  call    cs:__imp_BCryptGetProperty
0x1800a6735  test    eax, eax
0x1800a6737  jns     short loc_1800A6756
0x1800a6739  mov     rcx, [rbp+28h]; this
0x1800a673d  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x1800a6744  mov     r9d, eax; char *
0x1800a6747  mov     edx, 41Bh; void *
0x1800a674c  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800a6751  jmp     loc_1800A6849
0x1800a6756  mov     edx, [rbp+pbOutput]
0x1800a6759  lea     rcx, [rbp+arg_28]
0x1800a675d  call    ??$make_unique_hlocal_secure_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_secure_nothrow<uchar [0]>(unsigned __int64)
0x1800a6762  mov     rsi, [rbp+arg_28]
0x1800a6766  test    rsi, rsi
0x1800a6769  jnz     short loc_1800A678D
0x1800a676b  mov     rcx, [rbp+28h]; this
0x1800a676f  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x1800a6776  mov     ebx, 8007000Eh
0x1800a677b  mov     edx, 41Eh; void *
0x1800a6780  mov     r9d, ebx; char *
0x1800a6783  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6788  jmp     loc_1800A683E
0x1800a678d  mov     [rsp+50h+var_20], 0; dwFlags
0x1800a6795  lea     rdx, [rbp+phHash]; phHash
0x1800a6799  mov     [rsp+50h+dwFlags], r15d; cbSecret
0x1800a679e  xor     r9d, r9d; cbHashObject
0x1800a67a1  xor     r8d, r8d; pbHashObject
0x1800a67a4  mov     [rsp+50h+pcbResult], r13; int
0x1800a67a9  mov     ecx, 0B1h; hAlgorithm
0x1800a67ae  mov     [rbp+phHash], 0
0x1800a67b6  call    cs:__imp_BCryptCreateHash
0x1800a67bc  test    eax, eax
0x1800a67be  jns     short loc_1800A67E5
0x1800a67c0  mov     edx, 42Ah; void *
0x1800a67c5  mov     rcx, [rbp+28h]; this
0x1800a67c9  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x1800a67d0  mov     r9d, eax; char *
0x1800a67d3  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800a67d8  lea     rcx, [rbp+phHash]
0x1800a67dc  mov     ebx, eax
0x1800a67de  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800a67e3  jmp     short loc_1800A683E
0x1800a67e5  mov     r8d, [rbp+cbInput]; cbInput
0x1800a67e9  xor     r9d, r9d; dwFlags
0x1800a67ec  mov     rcx, [rbp+phHash]; hHash
0x1800a67f0  mov     rdx, r12; pbInput
0x1800a67f3  call    cs:__imp_BCryptHashData
0x1800a67f9  test    eax, eax
0x1800a67fb  jns     short loc_1800A6804
0x1800a67fd  mov     edx, 431h
0x1800a6802  jmp     short loc_1800A67C5
0x1800a6804  mov     r8d, [rbp+pbOutput]; cbOutput
0x1800a6808  xor     r9d, r9d; dwFlags
0x1800a680b  mov     rcx, [rbp+phHash]; hHash
0x1800a680f  mov     rdx, rsi; pbOutput
0x1800a6812  call    cs:__imp_BCryptFinishHash
0x1800a6818  test    eax, eax
0x1800a681a  jns     short loc_1800A6823
0x1800a681c  mov     edx, 438h
0x1800a6821  jmp     short loc_1800A67C5
0x1800a6823  mov     eax, [rbp+pbOutput]
0x1800a6826  lea     rcx, [rbp+phHash]
0x1800a682a  mov     [rbx], rsi
0x1800a682d  mov     [rdi], eax
0x1800a682f  mov     [rbp+arg_28], 0
0x1800a6837  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800a683c  xor     ebx, ebx
0x1800a683e  lea     rcx, [rbp+arg_28]
0x1800a6842  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x1800a6847  mov     eax, ebx
0x1800a6849  lea     r11, [rsp+50h+var_s0]
0x1800a684e  mov     rbx, [r11+38h]
0x1800a6852  mov     rsi, [r11+48h]
0x1800a6856  mov     rsp, r11
0x1800a6859  pop     r15
0x1800a685b  pop     r13
0x1800a685d  pop     r12
0x1800a685f  pop     rdi
0x1800a6860  pop     rbp
0x1800a6861  retn
```
