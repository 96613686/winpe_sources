# GenerateHash

- ea: `0x1800a64ec`
- end: `0x1800a66a0`
- name: `GenerateHash`
- size: `436`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180047258`
- `0x1800a00c0`

## callees

- `0x18000782c`
- `0x18004826c`
- `0x180050b30`
- `0x1800527ac`
- `0x180069b58`
- `0x18009fee8`
- `0x1800a64ec`

## import_xrefs

- `bcrypt!BCryptFinishHash` at `0x1800a6658`
- `bcrypt!BCryptFinishHash` at `0x1800a6658`
- `bcrypt!BCryptGetProperty` at `0x1800a6570`
- `bcrypt!BCryptGetProperty` at `0x1800a6570`
- `bcrypt!BCryptHashData` at `0x1800a6639`
- `bcrypt!BCryptHashData` at `0x1800a6639`
- `bcrypt!BCryptCreateHash` at `0x1800a65fd`
- `bcrypt!BCryptCreateHash` at `0x1800a65fd`

## string_xrefs

- `0x1800a657e`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`
- `0x1800a65b0`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`
- `0x1800a6610`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`

## pseudocode

```c
__int64 __fastcall GenerateHash(__int64 a1, UCHAR *a2, __int64 a3, UCHAR **a4, PUCHAR a5)
{
  ULONG v6; // r14d
  PUCHAR v8; // rbx
  NTSTATUS Property; // eax
  UCHAR *v11; // rsi
  unsigned int v12; // ebx
  NTSTATUS v13; // eax
  __int64 v14; // rdx
  int pcbResult; // [rsp+20h] [rbp-20h]
  int pcbResulta; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  __int64 v18; // [rsp+70h] [rbp+30h] BYREF
  ULONG pbOutput; // [rsp+80h] [rbp+40h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+88h] [rbp+48h] BYREF

  v18 = a1;
  v6 = a3;
  if ( !(_DWORD)a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1, a2, a3);
  if ( !a4 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1, a2, a3);
  v8 = a5;
  if ( !a5 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1, a2, a3);
  *a4 = 0;
  *(_DWORD *)v8 = 0;
  pbOutput = 0;
  LODWORD(v18) = 0;
  Property = BCryptGetProperty((BCRYPT_HANDLE)0x41, L"HashDigestLength", (PUCHAR)&pbOutput, 4u, (ULONG *)&v18, 0);
  if ( Property < 0 )
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x459,
             (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
             (const char *)(unsigned int)Property,
             pcbResult);
  wil::make_unique_hlocal_secure_nothrow<unsigned char [0]>(&a5, pbOutput);
  v11 = a5;
  if ( a5 )
  {
    phHash = 0;
    v13 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x41, &phHash, 0, 0, 0, 0, 0);
    if ( v13 >= 0 )
    {
      v13 = BCryptHashData(phHash, a2, v6, 0);
      if ( v13 >= 0 )
      {
        v13 = BCryptFinishHash(phHash, v11, pbOutput, 0);
        if ( v13 >= 0 )
        {
          *(_DWORD *)v8 = pbOutput;
          a5 = 0;
          *a4 = v11;
          wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phHash);
          v12 = 0;
          goto LABEL_19;
        }
        v14 = 1142;
      }
      else
      {
        v14 = 1135;
      }
    }
    else
    {
      v14 = 1128;
    }
    v12 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)v14,
            (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
            (const char *)(unsigned int)v13,
            pcbResulta);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phHash);
  }
  else
  {
    v12 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x45C,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
      (const char *)0x8007000ELL,
      pcbResult);
  }
LABEL_19:
  wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&a5);
  return v12;
}

```

## disassembly

```asm
0x1800a64ec  mov     [rsp-28h+arg_8], rbx
0x1800a64f1  mov     [rsp-28h+arg_0], rcx
0x1800a64f6  push    rbp
0x1800a64f7  push    rsi
0x1800a64f8  push    rdi
0x1800a64f9  push    r14
0x1800a64fb  push    r15
0x1800a64fd  mov     rbp, rsp
0x1800a6500  sub     rsp, 40h
0x1800a6504  mov     rdi, r9
0x1800a6507  mov     r14d, r8d
0x1800a650a  mov     r15, rdx
0x1800a650d  test    r8d, r8d
0x1800a6510  jnz     short loc_1800A6517
0x1800a6512  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800a6517  test    rdi, rdi
0x1800a651a  jnz     short loc_1800A6521
0x1800a651c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800a6521  mov     rbx, [rbp+arg_20]
0x1800a6525  test    rbx, rbx
0x1800a6528  jnz     short loc_1800A652F
0x1800a652a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800a652f  mov     r9d, 4; cbOutput
0x1800a6535  mov     [rsp+40h+dwFlags], 0; dwFlags
0x1800a653d  lea     rax, [rbp+arg_0]
0x1800a6541  mov     qword ptr [rdi], 0
0x1800a6548  lea     r8, [rbp+pbOutput]; pbOutput
0x1800a654c  mov     dword ptr [rbx], 0
0x1800a6552  lea     rdx, pszProperty; "HashDigestLength"
0x1800a6559  mov     [rbp+pbOutput], 0
0x1800a6560  lea     ecx, [r9+3Dh]; hObject
0x1800a6564  mov     dword ptr [rbp+arg_0], 0
0x1800a656b  mov     [rsp+40h+pcbResult], rax; int
0x1800a6570  call    cs:__imp_BCryptGetProperty
0x1800a6576  test    eax, eax
0x1800a6578  jns     short loc_1800A6597
0x1800a657a  mov     rcx, [rbp+28h]; this
0x1800a657e  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x1800a6585  mov     r9d, eax; char *
0x1800a6588  mov     edx, 459h; void *
0x1800a658d  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800a6592  jmp     loc_1800A668F
0x1800a6597  mov     edx, [rbp+pbOutput]
0x1800a659a  lea     rcx, [rbp+arg_20]
0x1800a659e  call    ??$make_unique_hlocal_secure_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_secure_nothrow<uchar [0]>(unsigned __int64)
0x1800a65a3  mov     rsi, [rbp+arg_20]
0x1800a65a7  test    rsi, rsi
0x1800a65aa  jnz     short loc_1800A65CE
0x1800a65ac  mov     rcx, [rbp+28h]; this
0x1800a65b0  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x1800a65b7  mov     ebx, 8007000Eh
0x1800a65bc  mov     edx, 45Ch; void *
0x1800a65c1  mov     r9d, ebx; char *
0x1800a65c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a65c9  jmp     loc_1800A6684
0x1800a65ce  xor     r9d, r9d; cbHashObject
0x1800a65d1  mov     [rsp+40h+var_10], 0; dwFlags
0x1800a65d9  mov     [rsp+40h+dwFlags], 0; cbSecret
0x1800a65e1  lea     rdx, [rbp+phHash]; phHash
0x1800a65e5  xor     r8d, r8d; pbHashObject
0x1800a65e8  mov     [rbp+phHash], 0
0x1800a65f0  mov     [rsp+40h+pcbResult], 0; int
0x1800a65f9  lea     ecx, [r9+41h]; hAlgorithm
0x1800a65fd  call    cs:__imp_BCryptCreateHash
0x1800a6603  test    eax, eax
0x1800a6605  jns     short loc_1800A662C
0x1800a6607  mov     edx, 468h; void *
0x1800a660c  mov     rcx, [rbp+28h]; this
0x1800a6610  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x1800a6617  mov     r9d, eax; char *
0x1800a661a  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800a661f  lea     rcx, [rbp+phHash]
0x1800a6623  mov     ebx, eax
0x1800a6625  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800a662a  jmp     short loc_1800A6684
0x1800a662c  mov     rcx, [rbp+phHash]; hHash
0x1800a6630  xor     r9d, r9d; dwFlags
0x1800a6633  mov     r8d, r14d; cbInput
0x1800a6636  mov     rdx, r15; pbInput
0x1800a6639  call    cs:__imp_BCryptHashData
0x1800a663f  test    eax, eax
0x1800a6641  jns     short loc_1800A664A
0x1800a6643  mov     edx, 46Fh
0x1800a6648  jmp     short loc_1800A660C
0x1800a664a  mov     r8d, [rbp+pbOutput]; cbOutput
0x1800a664e  xor     r9d, r9d; dwFlags
0x1800a6651  mov     rcx, [rbp+phHash]; hHash
0x1800a6655  mov     rdx, rsi; pbOutput
0x1800a6658  call    cs:__imp_BCryptFinishHash
0x1800a665e  test    eax, eax
0x1800a6660  jns     short loc_1800A6669
0x1800a6662  mov     edx, 476h
0x1800a6667  jmp     short loc_1800A660C
0x1800a6669  mov     eax, [rbp+pbOutput]
0x1800a666c  lea     rcx, [rbp+phHash]
0x1800a6670  mov     [rbx], eax
0x1800a6672  mov     [rbp+arg_20], 0
0x1800a667a  mov     [rdi], rsi
0x1800a667d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800a6682  xor     ebx, ebx
0x1800a6684  lea     rcx, [rbp+arg_20]
0x1800a6688  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x1800a668d  mov     eax, ebx
0x1800a668f  mov     rbx, [rsp+40h+arg_8]
0x1800a6694  add     rsp, 40h
0x1800a6698  pop     r15
0x1800a669a  pop     r14
0x1800a669c  pop     rdi
0x1800a669d  pop     rsi
0x1800a669e  pop     rbp
0x1800a669f  retn
```
