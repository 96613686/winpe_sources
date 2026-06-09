# TpmPolicySession::UnSealWithTpmTicket(uchar const *,ulong,uchar const *,ulong,uchar * *,ulong *)

- ea: `0x1800a8dbc`
- end: `0x1800a9044`
- name: `?UnSealWithTpmTicket@TpmPolicySession@@YAJPEBEK0KPEAPEAEPEAK@Z`
- size: `648`
- prototype: `int(TpmPolicySession *__hidden this, const unsigned __int8 *, unsigned int, const unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004f3f8`
- `0x18004faf0`

## callees

- `0x18000782c`
- `0x18004f1b0`
- `0x180050b30`
- `0x18005bef0`
- `0x1800a8430`
- `0x1800a8dbc`

## import_xrefs

- `ncrypt!NCryptOpenStorageProvider` at `0x1800a8dfb`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800a8dfb`
- `ncrypt!NCryptOpenKey` at `0x1800a8e66`
- `ncrypt!NCryptOpenKey` at `0x1800a8e66`
- `ncrypt!NCryptDecrypt` at `0x1800a8f15`
- `ncrypt!NCryptDecrypt` at `0x1800a8f99`
- `ncrypt!NCryptDecrypt` at `0x1800a8f15`
- `ncrypt!NCryptDecrypt` at `0x1800a8f99`

## string_xrefs

- `0x1800a8e12`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x1800a8e7d`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x1800a8f2c`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x1800a8fb0`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TpmPolicySession::UnSealWithTpmTicket(
        TpmPolicySession *this,
        const unsigned __int8 *a2,
        BYTE *a3,
        const unsigned __int8 *a4,
        PBYTE *a5,
        unsigned __int8 **a6)
{
  DWORD v6; // edi
  int v8; // r14d
  SECURITY_STATUS v10; // eax
  unsigned int v11; // ebx
  __int64 result; // rax
  SECURITY_STATUS v13; // eax
  unsigned int v14; // ebx
  SECURITY_STATUS v15; // eax
  unsigned int v16; // ebx
  SECURITY_STATUS v17; // eax
  unsigned int v18; // ebx
  const char *v19; // r9
  PBYTE v20; // rcx
  int dwFlags; // [rsp+20h] [rbp-88h]
  int dwFlagsa; // [rsp+20h] [rbp-88h]
  int dwFlagsb; // [rsp+20h] [rbp-88h]
  int dwFlagsc; // [rsp+20h] [rbp-88h]
  DWORD pcbResult; // [rsp+40h] [rbp-68h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+48h] [rbp-60h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+50h] [rbp-58h] BYREF
  PBYTE pbOutput; // [rsp+58h] [rbp-50h] BYREF
  _DWORD pPaddingInfo[2]; // [rsp+60h] [rbp-48h] BYREF
  _DWORD *v30; // [rsp+68h] [rbp-40h]
  _DWORD v31[2]; // [rsp+70h] [rbp-38h] BYREF
  TpmPolicySession *v32; // [rsp+78h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v6 = (unsigned int)a4;
  v8 = (int)a2;
  phProvider = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
    &phProvider,
    0);
  v10 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Platform Crypto Provider", 0);
  v11 = v10;
  if ( v10 >= 0 )
  {
    phKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
      &phKey,
      0);
    v13 = NCryptOpenKey(
            phProvider,
            &phKey,
            L"MICROSOFT_PCP_KSP_RSA_SEAL_KEY_3BD1C4BF-004E-4E2F-8A4D-0BF633DCB074",
            0,
            0);
    v14 = v13;
    if ( v13 >= 0 )
    {
      v31[0] = v8;
      v31[1] = 72;
      v32 = this;
      pPaddingInfo[0] = 0;
      pPaddingInfo[1] = 1;
      v30 = v31;
      pcbResult = 0;
      v15 = NCryptDecrypt(phKey, a3, v6, pPaddingInfo, 0, 0, &pcbResult, 0x100u);
      v16 = v15;
      if ( v15 >= 0 )
      {
        try
        {
          wil::make_unique_hlocal_secure<unsigned char [0]>(&pbOutput);
          v17 = NCryptDecrypt(phKey, a3, v6, pPaddingInfo, pbOutput, pcbResult, &pcbResult, 0x100u);
          v18 = v17;
          if ( v17 >= 0 )
          {
            v20 = pbOutput;
            pbOutput = 0;
            *a5 = v20;
            *(_DWORD *)a6 = pcbResult;
            wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&pbOutput);
            wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
            wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
            result = 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x195,
              (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
              (const char *)(unsigned int)v17,
              dwFlagsc);
            wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&pbOutput);
            wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
            wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
            result = v18;
          }
        }
        catch ( ... )
        {
          return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                                 retaddr,
                                 (void *)0x19A,
                                 (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
                                 v19);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x189,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
          (const char *)(unsigned int)v15,
          dwFlagsb);
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
        return v16;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x174,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
        (const char *)(unsigned int)v13,
        dwFlagsa);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
      return v14;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16B,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
      (const char *)(unsigned int)v10,
      dwFlags);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
    return v11;
  }
  return result;
}

```

## disassembly

```asm
0x1800a8dbc  push    rbx
0x1800a8dbe  push    rsi
0x1800a8dbf  push    rdi
0x1800a8dc0  push    r14
0x1800a8dc2  push    r15
0x1800a8dc4  sub     rsp, 80h
0x1800a8dcb  mov     edi, r9d
0x1800a8dce  mov     rsi, r8
0x1800a8dd1  mov     r14d, edx
0x1800a8dd4  mov     r15, rcx
0x1800a8dd7  mov     [rsp+0A8h+phProvider], 0
0x1800a8de0  xor     edx, edx
0x1800a8de2  lea     rcx, [rsp+0A8h+phProvider]
0x1800a8de7  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x1800a8dec  xor     r8d, r8d; dwFlags
0x1800a8def  lea     rdx, aMicrosoftPlatf; "Microsoft Platform Crypto Provider"
0x1800a8df6  lea     rcx, [rsp+0A8h+phProvider]; phProvider
0x1800a8dfb  call    cs:__imp_NCryptOpenStorageProvider
0x1800a8e01  mov     ebx, eax
0x1800a8e03  test    eax, eax
0x1800a8e05  jns     short loc_1800A8E35
0x1800a8e07  mov     rcx, [rsp+0A8h]; this
0x1800a8e0f  mov     r9d, eax; char *
0x1800a8e12  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1800a8e19  mov     edx, 16Bh; void *
0x1800a8e1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a8e23  nop
0x1800a8e24  lea     rcx, [rsp+0A8h+phProvider]
0x1800a8e29  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800a8e2e  mov     eax, ebx
0x1800a8e30  jmp     loc_1800A9035
0x1800a8e35  mov     [rsp+0A8h+phKey], 0
0x1800a8e3e  xor     edx, edx
0x1800a8e40  lea     rcx, [rsp+0A8h+phKey]
0x1800a8e45  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x1800a8e4a  mov     [rsp+0A8h+dwFlags], 0; int
0x1800a8e52  xor     r9d, r9d; dwLegacyKeySpec
0x1800a8e55  lea     r8, pszKeyName; "MICROSOFT_PCP_KSP_RSA_SEAL_KEY_3BD1C4BF"...
0x1800a8e5c  lea     rdx, [rsp+0A8h+phKey]; phKey
0x1800a8e61  mov     rcx, [rsp+0A8h+phProvider]; hProvider
0x1800a8e66  call    cs:__imp_NCryptOpenKey
0x1800a8e6c  mov     ebx, eax
0x1800a8e6e  test    eax, eax
0x1800a8e70  jns     short loc_1800A8EAB
0x1800a8e72  mov     rcx, [rsp+0A8h]; this
0x1800a8e7a  mov     r9d, eax; char *
0x1800a8e7d  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1800a8e84  mov     edx, 174h; void *
0x1800a8e89  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a8e8e  nop
0x1800a8e8f  lea     rcx, [rsp+0A8h+phKey]
0x1800a8e94  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800a8e99  nop
0x1800a8e9a  lea     rcx, [rsp+0A8h+phProvider]
0x1800a8e9f  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800a8ea4  mov     eax, ebx
0x1800a8ea6  jmp     loc_1800A9035
0x1800a8eab  mov     [rsp+0A8h+var_38], r14d
0x1800a8eb0  mov     [rsp+0A8h+var_34], 48h ; 'H'
0x1800a8eb8  mov     [rsp+0A8h+var_30], r15
0x1800a8ebd  mov     [rsp+0A8h+pPaddingInfo], 0
0x1800a8ec5  mov     [rsp+0A8h+var_44], 1
0x1800a8ecd  lea     rax, [rsp+0A8h+var_38]
0x1800a8ed2  mov     [rsp+0A8h+var_40], rax
0x1800a8ed7  mov     [rsp+0A8h+var_68], 0
0x1800a8edf  mov     r14d, 100h
0x1800a8ee5  mov     [rsp+0A8h+var_70], r14d; dwFlags
0x1800a8eea  lea     rax, [rsp+0A8h+var_68]
0x1800a8eef  mov     [rsp+0A8h+pcbResult], rax; pcbResult
0x1800a8ef4  mov     [rsp+0A8h+cbOutput], 0; cbOutput
0x1800a8efc  mov     qword ptr [rsp+0A8h+dwFlags], 0; int
0x1800a8f05  lea     r9, [rsp+0A8h+pPaddingInfo]; pPaddingInfo
0x1800a8f0a  mov     r8d, edi; cbInput
0x1800a8f0d  mov     rdx, rsi; pbInput
0x1800a8f10  mov     rcx, [rsp+0A8h+phKey]; hKey
0x1800a8f15  call    cs:__imp_NCryptDecrypt
0x1800a8f1b  mov     ebx, eax
0x1800a8f1d  test    eax, eax
0x1800a8f1f  jns     short loc_1800A8F5A
0x1800a8f21  mov     rcx, [rsp+0A8h]; this
0x1800a8f29  mov     r9d, eax; char *
0x1800a8f2c  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1800a8f33  mov     edx, 189h; void *
0x1800a8f38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a8f3d  nop
0x1800a8f3e  lea     rcx, [rsp+0A8h+phKey]
0x1800a8f43  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800a8f48  nop
0x1800a8f49  lea     rcx, [rsp+0A8h+phProvider]
0x1800a8f4e  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800a8f53  mov     eax, ebx
0x1800a8f55  jmp     loc_1800A9035
0x1800a8f5a  mov     edx, [rsp+0A8h+var_68]
0x1800a8f5e  lea     rcx, [rsp+0A8h+pbOutput]
0x1800a8f63  call    ??$make_unique_hlocal_secure@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_secure<uchar [0]>(unsigned __int64)
0x1800a8f68  mov     eax, [rsp+0A8h+var_68]
0x1800a8f6c  mov     rdx, [rsp+0A8h+pbOutput]
0x1800a8f71  mov     [rsp+0A8h+var_70], r14d; dwFlags
0x1800a8f76  lea     rcx, [rsp+0A8h+var_68]
0x1800a8f7b  mov     [rsp+0A8h+pcbResult], rcx; pcbResult
0x1800a8f80  mov     [rsp+0A8h+cbOutput], eax; cbOutput
0x1800a8f84  mov     qword ptr [rsp+0A8h+dwFlags], rdx; int
0x1800a8f89  lea     r9, [rsp+0A8h+pPaddingInfo]; pPaddingInfo
0x1800a8f8e  mov     r8d, edi; cbInput
0x1800a8f91  mov     rdx, rsi; pbInput
0x1800a8f94  mov     rcx, [rsp+0A8h+phKey]; hKey
0x1800a8f99  call    cs:__imp_NCryptDecrypt
0x1800a8f9f  mov     ebx, eax
0x1800a8fa1  test    eax, eax
0x1800a8fa3  jns     short loc_1800A8FE5
0x1800a8fa5  mov     rcx, [rsp+0A8h]; this
0x1800a8fad  mov     r9d, eax; char *
0x1800a8fb0  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1800a8fb7  mov     edx, 195h; void *
0x1800a8fbc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a8fc1  lea     rcx, [rsp+0A8h+pbOutput]
0x1800a8fc6  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x1800a8fcb  nop
0x1800a8fcc  lea     rcx, [rsp+0A8h+phKey]
0x1800a8fd1  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800a8fd6  nop
0x1800a8fd7  lea     rcx, [rsp+0A8h+phProvider]
0x1800a8fdc  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800a8fe1  mov     eax, ebx
0x1800a8fe3  jmp     short loc_1800A9035
0x1800a8fe5  mov     rcx, [rsp+0A8h+pbOutput]
0x1800a8fea  mov     [rsp+0A8h+pbOutput], 0
0x1800a8ff3  mov     rax, [rsp+0A8h+arg_20]
0x1800a8ffb  mov     [rax], rcx
0x1800a8ffe  mov     rcx, [rsp+0A8h+arg_28]
0x1800a9006  mov     eax, [rsp+0A8h+var_68]
0x1800a900a  mov     [rcx], eax
0x1800a900c  lea     rcx, [rsp+0A8h+pbOutput]
0x1800a9011  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x1800a9016  nop
0x1800a9017  lea     rcx, [rsp+0A8h+phKey]
0x1800a901c  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800a9021  nop
0x1800a9022  lea     rcx, [rsp+0A8h+phProvider]
0x1800a9027  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800a902c  nop
0x1800a902d  xor     eax, eax
0x1800a902f  jmp     short loc_1800A9035
0x1800a9031  mov     eax, [rsp+0A8h+var_68]
0x1800a9035  add     rsp, 80h
0x1800a903c  pop     r15
0x1800a903e  pop     r14
0x1800a9040  pop     rdi
0x1800a9041  pop     rsi
0x1800a9042  pop     rbx
0x1800a9043  retn
```
