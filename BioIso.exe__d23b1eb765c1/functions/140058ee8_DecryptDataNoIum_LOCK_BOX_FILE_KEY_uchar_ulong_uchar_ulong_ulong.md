# DecryptDataNoIum(_LOCK_BOX_FILE_KEY *,uchar *,ulong,uchar *,ulong,ulong *)

- ea: `0x140058ee8`
- end: `0x14005925b`
- name: `?DecryptDataNoIum@@YAJPEAT_LOCK_BOX_FILE_KEY@@PEAEK1KPEAK@Z`
- size: `883`
- prototype: `__int64 __fastcall(PUCHAR pbInput, PUCHAR, ULONG cbInput, unsigned __int8 *, size_t Size, ULONG *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140063f10`

## callees

- `0x14000a420`
- `0x14001cb6c`
- `0x14001cb78`
- `0x14001cb90`
- `0x14002b430`
- `0x140058624`
- `0x1400588f4`
- `0x1400589c4`
- `0x1400589e8`
- `0x140058ee8`
- `0x1400594d0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140059151`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400591c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400591fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140059218`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140059151`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400591c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400591fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140059218`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x140058f25`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x140058f25`
- `bcrypt!BCryptSetProperty` at `0x140058f59`
- `bcrypt!BCryptSetProperty` at `0x140058f59`
- `bcrypt!BCryptGetProperty` at `0x140058fb3`
- `bcrypt!BCryptGetProperty` at `0x140058fb3`
- `bcrypt!BCryptImportKey` at `0x14005900e`
- `bcrypt!BCryptImportKey` at `0x14005900e`
- `bcrypt!BCryptDecrypt` at `0x140059084`
- `bcrypt!BCryptDecrypt` at `0x140059112`
- `bcrypt!BCryptDecrypt` at `0x140059084`
- `bcrypt!BCryptDecrypt` at `0x140059112`

## string_xrefs

- `0x140058f75`: `onecore\ds\security\biometrics\service\trustlet\exe\crypto.cpp`
- `0x140059023`: `onecore\ds\security\biometrics\service\trustlet\exe\crypto.cpp`
- `0x140059129`: `onecore\ds\security\biometrics\service\trustlet\exe\crypto.cpp`
- `0x1400591a6`: `onecore\ds\security\biometrics\service\trustlet\exe\crypto.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DecryptDataNoIum(
        PUCHAR pbInput,
        PUCHAR a2,
        ULONG cbInput,
        unsigned __int8 *a4,
        size_t Size,
        ULONG *a6)
{
  NTSTATUS Property; // eax
  __int64 v11; // rdx
  unsigned int v12; // ebx
  NTSTATUS v13; // eax
  __int64 v14; // rdx
  unsigned int v15; // r12d
  NTSTATUS v16; // eax
  PUCHAR v17; // rcx
  PUCHAR v18; // rdi
  void *v19; // rbx
  void *v20; // rcx
  int dwFlags; // [rsp+20h] [rbp-59h]
  int dwFlagsa; // [rsp+20h] [rbp-59h]
  int dwFlagsb; // [rsp+20h] [rbp-59h]
  UCHAR pbOutput[4]; // [rsp+50h] [rbp-29h] BYREF
  ULONG pcbResult; // [rsp+54h] [rbp-25h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+58h] [rbp-21h] BYREF
  PUCHAR v28; // [rsp+60h] [rbp-19h] BYREF
  PUCHAR pbKeyObject; // [rsp+68h] [rbp-11h] BYREF
  void *Buf1; // [rsp+70h] [rbp-9h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm[9]; // [rsp+78h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+4Fh]

  phAlgorithm[0] = 0;
  Property = BCryptOpenAlgorithmProvider(phAlgorithm, L"AES", 0, 0);
  if ( Property >= 0 )
  {
    Property = BCryptSetProperty(phAlgorithm[0], L"ChainingMode", (PUCHAR)L"ChainingModeCBC", 0x20u, 0);
    if ( Property < 0 )
    {
      v11 = 192;
      goto LABEL_5;
    }
    *(_DWORD *)pbOutput = 0;
    pcbResult = 0;
    Property = BCryptGetProperty(phAlgorithm[0], L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
    if ( Property < 0 )
    {
      v11 = 203;
      goto LABEL_5;
    }
    wil::make_unique_hlocal_secure<unsigned char [0]>(&pbKeyObject, *(unsigned int *)pbOutput);
    phKey = 0;
    v13 = BCryptImportKey(phAlgorithm[0], 0, L"KeyDataBlob", &phKey, pbKeyObject, *(ULONG *)pbOutput, pbInput, 0x40u, 0);
    if ( v13 < 0 )
    {
      v14 = 217;
LABEL_10:
      v12 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)v14,
              (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\crypto.cpp",
              (const char *)(unsigned int)v13,
              dwFlagsa);
LABEL_11:
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
      wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&pbKeyObject);
      goto LABEL_29;
    }
    if ( !a4 )
    {
      v13 = BCryptDecrypt(phKey, a2, cbInput, 0, 0, 0, 0, 0, a6, 0);
      if ( v13 < 0 )
      {
        v14 = 233;
        goto LABEL_10;
      }
LABEL_28:
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
      wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&pbKeyObject);
      v12 = 0;
      goto LABEL_29;
    }
    v15 = 16 - (Size & 0xF);
    wil::make_unique_hlocal<unsigned char [0]>(&v28, v15 + (unsigned int)Size);
    v16 = BCryptDecrypt(phKey, a2, cbInput, 0, 0, 0, v28, v15 + Size, a6, 0);
    if ( v16 >= 0 )
    {
      wil::make_unique_hlocal<unsigned char [0]>(&Buf1, v15);
      memset_0(Buf1, 0, v15);
      v18 = v28;
      v19 = Buf1;
      if ( !memcmp_0(Buf1, &v28[(unsigned int)Size], v15) )
      {
        memcpy_0(a4, v18, (unsigned int)Size);
        *a6 = Size;
        Buf1 = 0;
        if ( v19 )
        {
          LocalFree(v19);
          v18 = v28;
        }
        v28 = 0;
        if ( v18 )
          LocalFree(v18);
        goto LABEL_28;
      }
      v12 = -2146861030;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x109,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\crypto.cpp",
        (const char *)0x8009801ALL,
        dwFlagsb);
      v20 = Buf1;
      Buf1 = 0;
      if ( v20 )
        LocalFree(v20);
      v17 = v28;
      v28 = 0;
    }
    else
    {
      v12 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0xFF,
              (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\crypto.cpp",
              (const char *)(unsigned int)v16,
              dwFlagsb);
      v17 = v28;
      v28 = 0;
    }
    if ( v17 )
      LocalFree(v17);
    goto LABEL_11;
  }
  v11 = 184;
LABEL_5:
  v12 = wil::details::in1diag3::Return_NtStatus(
          retaddr,
          (void *)v11,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\crypto.cpp",
          (const char *)(unsigned int)Property,
          dwFlags);
LABEL_29:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(phAlgorithm);
  return v12;
}

```

## disassembly

```asm
0x140058ee8  push    rbp
0x140058eea  push    rbx
0x140058eeb  push    rsi
0x140058eec  push    rdi
0x140058eed  push    r12
0x140058eef  push    r13
0x140058ef1  push    r14
0x140058ef3  push    r15
0x140058ef5  lea     rbp, [rsp-0Fh]
0x140058efa  sub     rsp, 88h
0x140058f01  mov     rsi, r9
0x140058f04  mov     edi, r8d
0x140058f07  mov     r15, rdx
0x140058f0a  mov     rbx, rcx
0x140058f0d  xor     r13d, r13d
0x140058f10  mov     [rbp+47h+phAlgorithm], r13
0x140058f14  xor     r9d, r9d; dwFlags
0x140058f17  xor     r8d, r8d; pszImplementation
0x140058f1a  lea     rdx, aAes; "AES"
0x140058f21  lea     rcx, [rbp+47h+phAlgorithm]; phAlgorithm
0x140058f25  call    cs:__imp_BCryptOpenAlgorithmProvider
0x140058f2c  nop     dword ptr [rax+rax+00h]
0x140058f31  test    eax, eax
0x140058f33  jns     short loc_140058F3C
0x140058f35  mov     edx, 0B8h
0x140058f3a  jmp     short loc_140058F6E
0x140058f3c  mov     [rsp+0C0h+dwFlags], r13d; int
0x140058f41  mov     r9d, 20h ; ' '; cbInput
0x140058f47  lea     r8, pbInput; "ChainingModeCBC"
0x140058f4e  lea     rdx, aChainingmode; "ChainingMode"
0x140058f55  mov     rcx, [rbp+47h+phAlgorithm]; hObject
0x140058f59  call    cs:__imp_BCryptSetProperty
0x140058f60  nop     dword ptr [rax+rax+00h]
0x140058f65  test    eax, eax
0x140058f67  jns     short loc_140058F88
0x140058f69  mov     edx, 0C0h; void *
0x140058f6e  mov     rcx, [rbp+4Fh]; this
0x140058f72  mov     r9d, eax; char *
0x140058f75  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\biometrics\\serv"...
0x140058f7c  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x140058f81  mov     ebx, eax
0x140058f83  jmp     loc_14005923B
0x140058f88  mov     dword ptr [rbp+47h+pbOutput], r13d
0x140058f8c  mov     [rbp+47h+pcbResult], r13d
0x140058f90  mov     [rsp+0C0h+cbKeyObject], r13d; dwFlags
0x140058f95  lea     rax, [rbp+47h+pcbResult]
0x140058f99  mov     qword ptr [rsp+0C0h+dwFlags], rax; pcbResult
0x140058f9e  mov     r9d, 4; cbOutput
0x140058fa4  lea     r8, [rbp+47h+pbOutput]; pbOutput
0x140058fa8  lea     rdx, aObjectlength; "ObjectLength"
0x140058faf  mov     rcx, [rbp+47h+phAlgorithm]; hObject
0x140058fb3  call    cs:__imp_BCryptGetProperty
0x140058fba  nop     dword ptr [rax+rax+00h]
0x140058fbf  test    eax, eax
0x140058fc1  jns     short loc_140058FCA
0x140058fc3  mov     edx, 0CBh
0x140058fc8  jmp     short loc_140058F6E
0x140058fca  mov     edx, dword ptr [rbp+47h+pbOutput]
0x140058fcd  lea     rcx, [rbp+47h+pbKeyObject]
0x140058fd1  call    ??$make_unique_hlocal_secure@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_secure<uchar [0]>(unsigned __int64)
0x140058fd6  nop
0x140058fd7  mov     eax, dword ptr [rbp+47h+pbOutput]
0x140058fda  mov     rdx, [rbp+47h+pbKeyObject]
0x140058fde  mov     [rbp+47h+phKey], r13
0x140058fe2  mov     [rsp+0C0h+var_80], r13d; dwFlags
0x140058fe7  mov     [rsp+0C0h+cbInput], 40h ; '@'; cbInput
0x140058fef  mov     [rsp+0C0h+pbInput], rbx; pbInput
0x140058ff4  mov     [rsp+0C0h+cbKeyObject], eax; cbKeyObject
0x140058ff8  mov     qword ptr [rsp+0C0h+dwFlags], rdx; int
0x140058ffd  lea     r9, [rbp+47h+phKey]; phKey
0x140059001  lea     r8, pszBlobType; "KeyDataBlob"
0x140059008  xor     edx, edx; hImportKey
0x14005900a  mov     rcx, [rbp+47h+phAlgorithm]; hAlgorithm
0x14005900e  call    cs:__imp_BCryptImportKey
0x140059015  nop     dword ptr [rax+rax+00h]
0x14005901a  test    eax, eax
0x14005901c  jns     short loc_140059050
0x14005901e  mov     edx, 0D9h; void *
0x140059023  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\biometrics\\serv"...
0x14005902a  mov     r9d, eax; char *
0x14005902d  mov     rcx, [rbp+4Fh]; this
0x140059031  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x140059036  mov     ebx, eax
0x140059038  lea     rcx, [rbp+47h+phKey]
0x14005903c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140059041  nop
0x140059042  lea     rcx, [rbp+47h+pbKeyObject]
0x140059046  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x14005904b  jmp     loc_14005923B
0x140059050  test    rsi, rsi
0x140059053  jnz     short loc_1400590B6
0x140059055  mov     [rsp+0C0h+var_78], r13d; dwFlags
0x14005905a  mov     rax, [rbp+47h+arg_28]
0x14005905e  mov     qword ptr [rsp+0C0h+var_80], rax; pcbResult
0x140059063  mov     [rsp+0C0h+cbInput], r13d; cbOutput
0x140059068  mov     [rsp+0C0h+pbInput], r13; pbOutput
0x14005906d  mov     [rsp+0C0h+cbKeyObject], r13d; cbIV
0x140059072  mov     qword ptr [rsp+0C0h+dwFlags], r13; pbIV
0x140059077  xor     r9d, r9d; pPaddingInfo
0x14005907a  mov     r8d, edi; cbInput
0x14005907d  mov     rdx, r15; pbInput
0x140059080  mov     rcx, [rbp+47h+phKey]; hKey
0x140059084  call    cs:__imp_BCryptDecrypt
0x14005908b  nop     dword ptr [rax+rax+00h]
0x140059090  test    eax, eax
0x140059092  jns     short loc_14005909B
0x140059094  mov     edx, 0E9h
0x140059099  jmp     short loc_140059023
0x14005909b  lea     rcx, [rbp+47h+phKey]
0x14005909f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1400590a4  nop
0x1400590a5  lea     rcx, [rbp+47h+pbKeyObject]
0x1400590a9  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x1400590ae  mov     ebx, r13d
0x1400590b1  jmp     loc_14005923B
0x1400590b6  mov     r14d, dword ptr [rbp+47h+Size]
0x1400590ba  mov     eax, r14d
0x1400590bd  and     eax, 0Fh
0x1400590c0  mov     r12d, 10h
0x1400590c6  sub     r12d, eax
0x1400590c9  lea     ebx, [r12+r14]
0x1400590cd  mov     edx, ebx
0x1400590cf  lea     rcx, [rbp+47h+var_60]
0x1400590d3  call    ??$make_unique_hlocal@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<uchar [0]>(unsigned __int64)
0x1400590d8  nop
0x1400590d9  mov     rax, [rbp+47h+var_60]
0x1400590dd  mov     [rsp+0C0h+var_78], r13d; dwFlags
0x1400590e2  mov     r13, [rbp+47h+arg_28]
0x1400590e6  mov     qword ptr [rsp+0C0h+var_80], r13; pcbResult
0x1400590eb  mov     [rsp+0C0h+cbInput], ebx; cbOutput
0x1400590ef  mov     [rsp+0C0h+pbInput], rax; pbOutput
0x1400590f4  mov     [rsp+0C0h+cbKeyObject], 0; cbIV
0x1400590fc  mov     qword ptr [rsp+0C0h+dwFlags], 0; int
0x140059105  xor     r9d, r9d; pPaddingInfo
0x140059108  mov     r8d, edi; cbInput
0x14005910b  mov     rdx, r15; pbInput
0x14005910e  mov     rcx, [rbp+47h+phKey]; hKey
0x140059112  call    cs:__imp_BCryptDecrypt
0x140059119  nop     dword ptr [rax+rax+00h]
0x14005911e  test    eax, eax
0x140059120  jns     short loc_140059162
0x140059122  mov     rcx, [rbp+4Fh]; this
0x140059126  mov     r9d, eax; char *
0x140059129  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\biometrics\\serv"...
0x140059130  mov     edx, 0FFh; void *
0x140059135  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x14005913a  mov     ebx, eax
0x14005913c  mov     rcx, [rbp+47h+var_60]; hMem
0x140059140  mov     [rbp+47h+var_60], 0
0x140059148  test    rcx, rcx
0x14005914b  jz      loc_140059038
0x140059151  call    cs:__imp_LocalFree
0x140059158  nop     dword ptr [rax+rax+00h]
0x14005915d  jmp     loc_140059038
0x140059162  mov     edx, r12d
0x140059165  lea     rcx, [rbp+47h+Buf1]
0x140059169  call    ??$make_unique_hlocal@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<uchar [0]>(unsigned __int64)
0x14005916e  mov     r8d, r12d; Size
0x140059171  xor     edx, edx; Val
0x140059173  mov     rcx, [rbp+47h+Buf1]; void *
0x140059177  call    memset_0
0x14005917c  mov     rdi, [rbp+47h+var_60]
0x140059180  lea     rdx, [r14+rdi]; Buf2
0x140059184  mov     r8d, r12d; Size
0x140059187  mov     rbx, [rbp+47h+Buf1]
0x14005918b  mov     rcx, rbx; Buf1
0x14005918e  call    memcmp_0
0x140059193  xor     r12d, r12d
0x140059196  test    eax, eax
0x140059198  jz      short loc_1400591DE
0x14005919a  mov     rcx, [rbp+4Fh]; this
0x14005919e  mov     ebx, 8009801Ah
0x1400591a3  mov     r9d, ebx; char *
0x1400591a6  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\biometrics\\serv"...
0x1400591ad  mov     edx, 109h; void *
0x1400591b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400591b7  mov     rcx, [rbp+47h+Buf1]; hMem
0x1400591bb  mov     [rbp+47h+Buf1], r12
0x1400591bf  test    rcx, rcx
0x1400591c2  jz      short loc_1400591D1
0x1400591c4  call    cs:__imp_LocalFree
0x1400591cb  nop     dword ptr [rax+rax+00h]
0x1400591d0  nop
0x1400591d1  mov     rcx, [rbp+47h+var_60]
0x1400591d5  mov     [rbp+47h+var_60], r12
0x1400591d9  jmp     loc_140059148
0x1400591de  mov     r8, r14; Size
0x1400591e1  mov     rdx, rdi; Src
0x1400591e4  mov     rcx, rsi; void *
0x1400591e7  call    memcpy_0
0x1400591ec  mov     [r13+0], r14d
0x1400591f0  mov     [rbp+47h+Buf1], r12
0x1400591f4  test    rbx, rbx
0x1400591f7  jz      short loc_14005920C
0x1400591f9  mov     rcx, rbx; hMem
0x1400591fc  call    cs:__imp_LocalFree
0x140059203  nop     dword ptr [rax+rax+00h]
0x140059208  mov     rdi, [rbp+47h+var_60]
0x14005920c  mov     [rbp+47h+var_60], r12
0x140059210  test    rdi, rdi
0x140059213  jz      short loc_140059225
0x140059215  mov     rcx, rdi; hMem
0x140059218  call    cs:__imp_LocalFree
0x14005921f  nop     dword ptr [rax+rax+00h]
0x140059224  nop
0x140059225  lea     rcx, [rbp+47h+phKey]
0x140059229  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14005922e  nop
0x14005922f  lea     rcx, [rbp+47h+pbKeyObject]
0x140059233  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x140059238  mov     ebx, r12d
0x14005923b  lea     rcx, [rbp+47h+phAlgorithm]
0x14005923f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140059244  mov     eax, ebx
0x140059246  add     rsp, 88h
0x14005924d  pop     r15
0x14005924f  pop     r14
0x140059251  pop     r13
0x140059253  pop     r12
0x140059255  pop     rdi
0x140059256  pop     rsi
0x140059257  pop     rbx
0x140059258  pop     rbp
0x140059259  retn
```
