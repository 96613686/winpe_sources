# AesEncryptDecrypt

- ea: `0x1800a5a08`
- end: `0x1800a5d27`
- name: `AesEncryptDecrypt`
- size: `799`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800a05b4`
- `0x1800a0950`

## callees

- `0x18000782c`
- `0x18004826c`
- `0x180050b30`
- `0x1800527ac`
- `0x180069b58`
- `0x18008f8f8`
- `0x1800a5a08`

## import_xrefs

- `bcrypt!BCryptGetProperty` at `0x1800a5aed`
- `bcrypt!BCryptGetProperty` at `0x1800a5aed`
- `bcrypt!BCryptDecrypt` at `0x1800a5c09`
- `bcrypt!BCryptDecrypt` at `0x1800a5cc3`
- `bcrypt!BCryptDecrypt` at `0x1800a5c09`
- `bcrypt!BCryptDecrypt` at `0x1800a5cc3`
- `bcrypt!BCryptImportKey` at `0x1800a5b8a`
- `bcrypt!BCryptImportKey` at `0x1800a5b8a`
- `bcrypt!BCryptEncrypt` at `0x1800a5bf8`
- `bcrypt!BCryptEncrypt` at `0x1800a5c9d`
- `bcrypt!BCryptEncrypt` at `0x1800a5bf8`
- `bcrypt!BCryptEncrypt` at `0x1800a5c9d`

## string_xrefs

- `0x1800a5a83`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`
- `0x1800a5afb`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`
- `0x1800a5b2f`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`
- `0x1800a5b9d`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`
- `0x1800a5c3a`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`
- `0x1800a5cb0`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`

## pseudocode

```c
__int64 __fastcall AesEncryptDecrypt(
        __int64 a1,
        _OWORD *a2,
        __int64 a3,
        UCHAR *a4,
        ULONG pbOutput,
        PUCHAR a6,
        ULONG a7,
        PUCHAR pbKeyObject,
        PUCHAR a9)
{
  char v11; // si
  PUCHAR v12; // r14
  PUCHAR v13; // r15
  PUCHAR pbInput; // rbx
  unsigned int v15; // ebx
  NTSTATUS Property; // eax
  NTSTATUS v17; // eax
  __int64 v18; // rdx
  bool v19; // zf
  UCHAR *v20; // rsi
  ULONG v21; // r12d
  PUCHAR v22; // rbx
  NTSTATUS v23; // eax
  __int64 v24; // rdx
  ULONG v25; // eax
  int pcbResult; // [rsp+20h] [rbp-40h]
  int pcbResulta; // [rsp+20h] [rbp-40h]
  int pcbResultb; // [rsp+20h] [rbp-40h]
  int pcbResultc; // [rsp+20h] [rbp-40h]
  BCRYPT_KEY_HANDLE phKey; // [rsp+50h] [rbp-10h] BYREF
  PUCHAR v32; // [rsp+58h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  char v34; // [rsp+90h] [rbp+30h]
  ULONG cbOutput; // [rsp+A0h] [rbp+40h] BYREF

  cbOutput = a3;
  v34 = a1;
  v11 = a1;
  if ( !a7 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1, a2, a3);
  v12 = pbKeyObject;
  if ( !pbKeyObject )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1, a2, a3);
  v13 = a9;
  if ( !a9 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1, a2, a3);
  *(_QWORD *)v12 = 0;
  *(_DWORD *)v13 = 0;
  wil::make_unique_hlocal_secure_nothrow<unsigned char [0]>(&v32, 0x1Cu);
  pbInput = v32;
  if ( v32 )
  {
    *(_DWORD *)v32 = 1296188491;
    *((_DWORD *)pbInput + 1) = 1;
    *((_DWORD *)pbInput + 2) = 16;
    *(_OWORD *)(pbInput + 12) = *a2;
    pbOutput = 0;
    cbOutput = 0;
    Property = BCryptGetProperty((BCRYPT_HANDLE)0x1A1, L"ObjectLength", (PUCHAR)&pbOutput, 4u, &cbOutput, 0);
    if ( Property < 0 )
    {
      v15 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x377,
              (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
              (const char *)(unsigned int)Property,
              pcbResulta);
      goto LABEL_33;
    }
    wil::make_unique_hlocal_secure_nothrow<unsigned char [0]>(&pbKeyObject, pbOutput);
    if ( !pbKeyObject )
    {
      v15 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x37B,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
        (const char *)0x8007000ELL,
        pcbResulta);
LABEL_13:
      wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&pbKeyObject);
      goto LABEL_33;
    }
    phKey = 0;
    v17 = BCryptImportKey((BCRYPT_ALG_HANDLE)0x1A1, 0, L"KeyDataBlob", &phKey, pbKeyObject, pbOutput, pbInput, 0x1Cu, 0);
    if ( v17 < 0 )
    {
      v18 = 903;
LABEL_16:
      v15 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)v18,
              (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
              (const char *)(unsigned int)v17,
              pcbResultb);
LABEL_17:
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
      goto LABEL_13;
    }
    v19 = v11 == 0;
    v20 = a6;
    if ( v19 )
    {
      v17 = BCryptDecrypt(phKey, a6, a7, 0, a4, 0x10u, 0, 0, &cbOutput, 1u);
      if ( v17 < 0 )
      {
        v18 = 931;
        goto LABEL_16;
      }
    }
    else
    {
      v17 = BCryptEncrypt(phKey, a6, a7, 0, a4, 0x10u, 0, 0, &cbOutput, 1u);
      if ( v17 < 0 )
      {
        v18 = 917;
        goto LABEL_16;
      }
    }
    v21 = cbOutput;
    wil::make_unique_hlocal_secure_nothrow<unsigned char [0]>(&a9, cbOutput);
    v22 = a9;
    if ( !a9 )
    {
      v15 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3A8,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
        (const char *)0x8007000ELL,
        pcbResultb);
LABEL_25:
      wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&a9);
      goto LABEL_17;
    }
    if ( v34 )
    {
      v23 = BCryptEncrypt(phKey, v20, a7, 0, a4, 0x10u, a9, v21, &cbOutput, 1u);
      if ( v23 < 0 )
      {
        v24 = 949;
LABEL_29:
        v15 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)v24,
                (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
                (const char *)(unsigned int)v23,
                pcbResultc);
        goto LABEL_25;
      }
    }
    else
    {
      v23 = BCryptDecrypt(phKey, v20, a7, 0, a4, 0x10u, a9, v21, &cbOutput, 1u);
      if ( v23 < 0 )
      {
        v24 = 963;
        goto LABEL_29;
      }
    }
    v25 = cbOutput;
    *(_QWORD *)v12 = v22;
    *(_DWORD *)v13 = v25;
    a9 = 0;
    wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&a9);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
    wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&pbKeyObject);
    v15 = 0;
    goto LABEL_33;
  }
  v15 = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x365,
    (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
    (const char *)0x8007000ELL,
    pcbResult);
LABEL_33:
  wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&v32);
  return v15;
}

```

## disassembly

```asm
0x1800a5a08  mov     rax, rsp
0x1800a5a0b  mov     [rax+10h], rbx
0x1800a5a0f  mov     [rax+20h], rsi
0x1800a5a13  mov     [rax+18h], r8d
0x1800a5a17  mov     [rax+8], cl
0x1800a5a1a  push    rbp
0x1800a5a1b  push    r12
0x1800a5a1d  push    r13
0x1800a5a1f  push    r14
0x1800a5a21  push    r15
0x1800a5a23  mov     rbp, rsp
0x1800a5a26  sub     rsp, 60h
0x1800a5a2a  cmp     [rbp+arg_30], 0
0x1800a5a2e  mov     r13, r9
0x1800a5a31  mov     r12, rdx
0x1800a5a34  mov     sil, cl
0x1800a5a37  ja      short loc_1800A5A3E
0x1800a5a39  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800a5a3e  mov     r14, [rbp+pbKeyObject]
0x1800a5a42  test    r14, r14
0x1800a5a45  jnz     short loc_1800A5A4C
0x1800a5a47  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800a5a4c  mov     r15, [rbp+arg_40]
0x1800a5a50  test    r15, r15
0x1800a5a53  jnz     short loc_1800A5A5A
0x1800a5a55  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800a5a5a  mov     qword ptr [r14], 0
0x1800a5a61  lea     rcx, [rbp+var_8]
0x1800a5a65  mov     edx, 1Ch
0x1800a5a6a  mov     dword ptr [r15], 0
0x1800a5a71  call    ??$make_unique_hlocal_secure_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_secure_nothrow<uchar [0]>(unsigned __int64)
0x1800a5a76  mov     rbx, [rbp+var_8]
0x1800a5a7a  test    rbx, rbx
0x1800a5a7d  jnz     short loc_1800A5AA1
0x1800a5a7f  mov     rcx, [rbp+28h]; this
0x1800a5a83  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x1800a5a8a  mov     ebx, 8007000Eh
0x1800a5a8f  mov     edx, 365h; void *
0x1800a5a94  mov     r9d, ebx; char *
0x1800a5a97  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a5a9c  jmp     loc_1800A5D02
0x1800a5aa1  mov     dword ptr [rbx], 4D42444Bh
0x1800a5aa7  lea     rax, [rbp+cbOutput]
0x1800a5aab  mov     dword ptr [rbx+4], 1
0x1800a5ab2  lea     r8, [rbp+pbOutput]; pbOutput
0x1800a5ab6  mov     dword ptr [rbx+8], 10h
0x1800a5abd  lea     rdx, aObjectlength; "ObjectLength"
0x1800a5ac4  movups  xmm0, xmmword ptr [r12]
0x1800a5ac9  xor     r12d, r12d
0x1800a5acc  mov     ecx, 1A1h; hObject
0x1800a5ad1  mov     [rsp+60h+dwFlags], r12d; dwFlags
0x1800a5ad6  movdqu  xmmword ptr [rbx+0Ch], xmm0
0x1800a5adb  mov     [rbp+pbOutput], r12d
0x1800a5adf  lea     r9d, [r12+4]; cbOutput
0x1800a5ae4  mov     [rbp+cbOutput], r12d
0x1800a5ae8  mov     [rsp+60h+pcbResult], rax; int
0x1800a5aed  call    cs:__imp_BCryptGetProperty
0x1800a5af3  test    eax, eax
0x1800a5af5  jns     short loc_1800A5B16
0x1800a5af7  mov     rcx, [rbp+28h]; this
0x1800a5afb  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x1800a5b02  mov     r9d, eax; char *
0x1800a5b05  mov     edx, 377h; void *
0x1800a5b0a  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800a5b0f  mov     ebx, eax
0x1800a5b11  jmp     loc_1800A5D02
0x1800a5b16  mov     edx, [rbp+pbOutput]
0x1800a5b19  lea     rcx, [rbp+pbKeyObject]
0x1800a5b1d  call    ??$make_unique_hlocal_secure_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_secure_nothrow<uchar [0]>(unsigned __int64)
0x1800a5b22  mov     rax, [rbp+pbKeyObject]
0x1800a5b26  test    rax, rax
0x1800a5b29  jnz     short loc_1800A5B56
0x1800a5b2b  mov     rcx, [rbp+28h]; this
0x1800a5b2f  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x1800a5b36  mov     ebx, 8007000Eh
0x1800a5b3b  mov     edx, 37Bh; void *
0x1800a5b40  mov     r9d, ebx; char *
0x1800a5b43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a5b48  lea     rcx, [rbp+pbKeyObject]
0x1800a5b4c  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x1800a5b51  jmp     loc_1800A5D02
0x1800a5b56  mov     edx, [rbp+pbOutput]
0x1800a5b59  lea     r9, [rbp+phKey]; phKey
0x1800a5b5d  mov     [rsp+60h+var_20], r12d; dwFlags
0x1800a5b62  lea     r8, aKeydatablob; "KeyDataBlob"
0x1800a5b69  mov     [rsp+60h+cbInput], 1Ch; cbInput
0x1800a5b71  mov     ecx, 1A1h; hAlgorithm
0x1800a5b76  mov     [rsp+60h+pbInput], rbx; pbInput
0x1800a5b7b  mov     [rsp+60h+dwFlags], edx; cbKeyObject
0x1800a5b7f  xor     edx, edx; hImportKey
0x1800a5b81  mov     [rbp+phKey], r12
0x1800a5b85  mov     [rsp+60h+pcbResult], rax; int
0x1800a5b8a  call    cs:__imp_BCryptImportKey
0x1800a5b90  test    eax, eax
0x1800a5b92  jns     short loc_1800A5BB9
0x1800a5b94  mov     edx, 387h; void *
0x1800a5b99  mov     rcx, [rbp+28h]; this
0x1800a5b9d  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x1800a5ba4  mov     r9d, eax; char *
0x1800a5ba7  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800a5bac  mov     ebx, eax
0x1800a5bae  lea     rcx, [rbp+phKey]
0x1800a5bb2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800a5bb7  jmp     short loc_1800A5B48
0x1800a5bb9  mov     r8d, [rbp+arg_30]; cbInput
0x1800a5bbd  lea     rax, [rbp+cbOutput]
0x1800a5bc1  mov     rcx, [rbp+phKey]; hKey
0x1800a5bc5  xor     r9d, r9d; pPaddingInfo
0x1800a5bc8  mov     [rsp+60h+var_18], 1; dwFlags
0x1800a5bd0  test    sil, sil
0x1800a5bd3  mov     rsi, [rbp+arg_28]
0x1800a5bd7  mov     qword ptr [rsp+60h+var_20], rax; pcbResult
0x1800a5bdc  mov     rdx, rsi; pbInput
0x1800a5bdf  mov     [rsp+60h+cbInput], r12d; cbOutput
0x1800a5be4  mov     [rsp+60h+pbInput], r12; pbOutput
0x1800a5be9  mov     [rsp+60h+dwFlags], 10h; cbIV
0x1800a5bf1  mov     [rsp+60h+pcbResult], r13; int
0x1800a5bf6  jz      short loc_1800A5C09
0x1800a5bf8  call    cs:__imp_BCryptEncrypt
0x1800a5bfe  test    eax, eax
0x1800a5c00  jns     short loc_1800A5C1D
0x1800a5c02  mov     edx, 395h
0x1800a5c07  jmp     short loc_1800A5B99
0x1800a5c09  call    cs:__imp_BCryptDecrypt
0x1800a5c0f  test    eax, eax
0x1800a5c11  jns     short loc_1800A5C1D
0x1800a5c13  mov     edx, 3A3h
0x1800a5c18  jmp     loc_1800A5B99
0x1800a5c1d  mov     r12d, [rbp+cbOutput]
0x1800a5c21  lea     rcx, [rbp+arg_40]
0x1800a5c25  mov     edx, r12d
0x1800a5c28  call    ??$make_unique_hlocal_secure_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_secure_nothrow<uchar [0]>(unsigned __int64)
0x1800a5c2d  mov     rbx, [rbp+arg_40]
0x1800a5c31  test    rbx, rbx
0x1800a5c34  jnz     short loc_1800A5C61
0x1800a5c36  mov     rcx, [rbp+28h]; this
0x1800a5c3a  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x1800a5c41  mov     ebx, 8007000Eh
0x1800a5c46  mov     edx, 3A8h; void *
0x1800a5c4b  mov     r9d, ebx; char *
0x1800a5c4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a5c53  lea     rcx, [rbp+arg_40]
0x1800a5c57  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x1800a5c5c  jmp     loc_1800A5BAE
0x1800a5c61  mov     r8d, [rbp+arg_30]; cbInput
0x1800a5c65  lea     rax, [rbp+cbOutput]
0x1800a5c69  mov     rcx, [rbp+phKey]; hKey
0x1800a5c6d  xor     r9d, r9d; pPaddingInfo
0x1800a5c70  mov     rdx, rsi; pbInput
0x1800a5c73  mov     [rsp+60h+var_18], 1; dwFlags
0x1800a5c7b  mov     qword ptr [rsp+60h+var_20], rax; pcbResult
0x1800a5c80  mov     [rsp+60h+cbInput], r12d; cbOutput
0x1800a5c85  mov     [rsp+60h+pbInput], rbx; pbOutput
0x1800a5c8a  mov     [rsp+60h+dwFlags], 10h; cbIV
0x1800a5c92  mov     [rsp+60h+pcbResult], r13; int
0x1800a5c97  cmp     [rbp+arg_0], r9b
0x1800a5c9b  jz      short loc_1800A5CC3
0x1800a5c9d  call    cs:__imp_BCryptEncrypt
0x1800a5ca3  test    eax, eax
0x1800a5ca5  jns     short loc_1800A5CD4
0x1800a5ca7  mov     edx, 3B5h; void *
0x1800a5cac  mov     rcx, [rbp+28h]; this
0x1800a5cb0  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x1800a5cb7  mov     r9d, eax; char *
0x1800a5cba  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800a5cbf  mov     ebx, eax
0x1800a5cc1  jmp     short loc_1800A5C53
0x1800a5cc3  call    cs:__imp_BCryptDecrypt
0x1800a5cc9  test    eax, eax
0x1800a5ccb  jns     short loc_1800A5CD4
0x1800a5ccd  mov     edx, 3C3h
0x1800a5cd2  jmp     short loc_1800A5CAC
0x1800a5cd4  mov     eax, [rbp+cbOutput]
0x1800a5cd7  lea     rcx, [rbp+arg_40]
0x1800a5cdb  mov     [r14], rbx
0x1800a5cde  mov     [r15], eax
0x1800a5ce1  mov     [rbp+arg_40], 0
0x1800a5ce9  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x1800a5cee  lea     rcx, [rbp+phKey]
0x1800a5cf2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800a5cf7  lea     rcx, [rbp+pbKeyObject]
0x1800a5cfb  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x1800a5d00  xor     ebx, ebx
0x1800a5d02  lea     rcx, [rbp+var_8]
0x1800a5d06  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x1800a5d0b  lea     r11, [rsp+60h+var_s0]
0x1800a5d10  mov     eax, ebx
0x1800a5d12  mov     rbx, [r11+38h]
0x1800a5d16  mov     rsi, [r11+48h]
0x1800a5d1a  mov     rsp, r11
0x1800a5d1d  pop     r15
0x1800a5d1f  pop     r14
0x1800a5d21  pop     r13
0x1800a5d23  pop     r12
0x1800a5d25  pop     rbp
0x1800a5d26  retn
```
