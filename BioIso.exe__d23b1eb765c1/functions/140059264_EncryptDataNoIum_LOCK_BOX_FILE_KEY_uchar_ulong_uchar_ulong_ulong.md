# EncryptDataNoIum(_LOCK_BOX_FILE_KEY *,uchar *,ulong,uchar *,ulong,ulong *)

- ea: `0x140059264`
- end: `0x1400594ca`
- name: `?EncryptDataNoIum@@YAJPEAT_LOCK_BOX_FILE_KEY@@PEAEK1KPEAK@Z`
- size: `614`
- prototype: `__int64 __fastcall(PUCHAR pbInput, unsigned __int8 *Src, ULONG cbInput, PUCHAR pbOutput, ULONG cbOutput, ULONG *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000e9e0`

## callees

- `0x14001cb78`
- `0x14001cb90`
- `0x14002b430`
- `0x140058624`
- `0x1400588f4`
- `0x1400589c4`
- `0x1400589e8`
- `0x140059264`
- `0x1400594d0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005946b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140059489`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005946b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140059489`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x14005929d`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x14005929d`
- `bcrypt!BCryptSetProperty` at `0x1400592d1`
- `bcrypt!BCryptSetProperty` at `0x1400592d1`
- `bcrypt!BCryptGetProperty` at `0x14005932b`
- `bcrypt!BCryptGetProperty` at `0x14005932b`
- `bcrypt!BCryptImportKey` at `0x140059386`
- `bcrypt!BCryptImportKey` at `0x140059386`
- `bcrypt!BCryptEncrypt` at `0x140059430`
- `bcrypt!BCryptEncrypt` at `0x140059430`

## string_xrefs

- `0x1400592ed`: `onecore\ds\security\biometrics\service\trustlet\exe\crypto.cpp`
- `0x14005939d`: `onecore\ds\security\biometrics\service\trustlet\exe\crypto.cpp`
- `0x140059447`: `onecore\ds\security\biometrics\service\trustlet\exe\crypto.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall EncryptDataNoIum(
        PUCHAR pbInput,
        unsigned __int8 *Src,
        ULONG cbInput,
        PUCHAR pbOutput,
        ULONG cbOutput,
        ULONG *a6)
{
  size_t v7; // rsi
  NTSTATUS Property; // eax
  __int64 v11; // rdx
  unsigned int v12; // ebx
  NTSTATUS v13; // eax
  ULONG v14; // edi
  NTSTATUS v15; // eax
  PUCHAR v16; // rcx
  PUCHAR v17; // rcx
  int dwFlags; // [rsp+20h] [rbp-60h]
  int dwFlagsa; // [rsp+20h] [rbp-60h]
  int dwFlagsb; // [rsp+20h] [rbp-60h]
  UCHAR pbOutputa[4]; // [rsp+50h] [rbp-30h] BYREF
  ULONG pcbResult; // [rsp+54h] [rbp-2Ch] BYREF
  PUCHAR v24; // [rsp+58h] [rbp-28h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+60h] [rbp-20h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+68h] [rbp-18h] BYREF
  PUCHAR pbKeyObject[2]; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  v7 = cbInput;
  phAlgorithm = 0;
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"AES", 0, 0);
  if ( Property < 0 )
  {
    v11 = 102;
LABEL_5:
    v12 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)v11,
            (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\crypto.cpp",
            (const char *)(unsigned int)Property,
            dwFlags);
    goto LABEL_19;
  }
  Property = BCryptSetProperty(phAlgorithm, L"ChainingMode", (PUCHAR)L"ChainingModeCBC", 0x20u, 0);
  if ( Property < 0 )
  {
    v11 = 110;
    goto LABEL_5;
  }
  *(_DWORD *)pbOutputa = 0;
  pcbResult = 0;
  Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", pbOutputa, 4u, &pcbResult, 0);
  if ( Property < 0 )
  {
    v11 = 121;
    goto LABEL_5;
  }
  wil::make_unique_hlocal_secure<unsigned char [0]>(pbKeyObject, *(unsigned int *)pbOutputa);
  phKey = 0;
  v13 = BCryptImportKey(phAlgorithm, 0, L"KeyDataBlob", &phKey, pbKeyObject[0], *(ULONG *)pbOutputa, pbInput, 0x40u, 0);
  if ( v13 < 0 )
  {
    v12 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x87,
            (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\crypto.cpp",
            (const char *)(unsigned int)v13,
            dwFlagsa);
LABEL_10:
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
    wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(pbKeyObject);
    goto LABEL_19;
  }
  v14 = v7;
  if ( (v7 & 0xF) != 0 )
    v14 = v7 - (v7 & 0xF) + 16;
  wil::make_unique_hlocal<unsigned char [0]>(&v24, v14);
  memset_0(v24, 0, v14);
  memcpy_0(v24, Src, v7);
  v15 = BCryptEncrypt(phKey, v24, v14, 0, 0, 0, pbOutput, cbOutput, a6, 0);
  if ( v15 < 0 )
  {
    v12 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0xA3,
            (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\crypto.cpp",
            (const char *)(unsigned int)v15,
            dwFlagsb);
    v16 = v24;
    v24 = 0;
    if ( v16 )
      LocalFree(v16);
    goto LABEL_10;
  }
  v17 = v24;
  v24 = 0;
  if ( v17 )
    LocalFree(v17);
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
  wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(pbKeyObject);
  v12 = 0;
LABEL_19:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
  return v12;
}

```

## disassembly

```asm
0x140059264  push    rbp
0x140059266  push    rbx
0x140059267  push    rsi
0x140059268  push    rdi
0x140059269  push    r12
0x14005926b  push    r14
0x14005926d  push    r15
0x14005926f  mov     rbp, rsp
0x140059272  sub     rsp, 80h
0x140059279  mov     r14, r9
0x14005927c  mov     esi, r8d
0x14005927f  mov     r15, rdx
0x140059282  mov     rbx, rcx
0x140059285  xor     r12d, r12d
0x140059288  mov     [rbp+phAlgorithm], r12
0x14005928c  xor     r9d, r9d; dwFlags
0x14005928f  xor     r8d, r8d; pszImplementation
0x140059292  lea     rdx, aAes; "AES"
0x140059299  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x14005929d  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1400592a4  nop     dword ptr [rax+rax+00h]
0x1400592a9  test    eax, eax
0x1400592ab  jns     short loc_1400592B4
0x1400592ad  lea     edx, [r12+66h]
0x1400592b2  jmp     short loc_1400592E6
0x1400592b4  mov     [rsp+80h+dwFlags], r12d; int
0x1400592b9  mov     r9d, 20h ; ' '; cbInput
0x1400592bf  lea     r8, pbInput; "ChainingModeCBC"
0x1400592c6  lea     rdx, aChainingmode; "ChainingMode"
0x1400592cd  mov     rcx, [rbp+phAlgorithm]; hObject
0x1400592d1  call    cs:__imp_BCryptSetProperty
0x1400592d8  nop     dword ptr [rax+rax+00h]
0x1400592dd  test    eax, eax
0x1400592df  jns     short loc_140059300
0x1400592e1  mov     edx, 6Eh ; 'n'; void *
0x1400592e6  mov     rcx, [rbp+38h]; this
0x1400592ea  mov     r9d, eax; char *
0x1400592ed  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\biometrics\\serv"...
0x1400592f4  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1400592f9  mov     ebx, eax
0x1400592fb  jmp     loc_1400594AC
0x140059300  mov     dword ptr [rbp+pbOutput], r12d
0x140059304  mov     [rbp+pcbResult], r12d
0x140059308  mov     [rsp+80h+cbKeyObject], r12d; dwFlags
0x14005930d  lea     rax, [rbp+pcbResult]
0x140059311  mov     qword ptr [rsp+80h+dwFlags], rax; pcbResult
0x140059316  mov     r9d, 4; cbOutput
0x14005931c  lea     r8, [rbp+pbOutput]; pbOutput
0x140059320  lea     rdx, aObjectlength; "ObjectLength"
0x140059327  mov     rcx, [rbp+phAlgorithm]; hObject
0x14005932b  call    cs:__imp_BCryptGetProperty
0x140059332  nop     dword ptr [rax+rax+00h]
0x140059337  test    eax, eax
0x140059339  jns     short loc_140059342
0x14005933b  mov     edx, 79h ; 'y'
0x140059340  jmp     short loc_1400592E6
0x140059342  mov     edx, dword ptr [rbp+pbOutput]
0x140059345  lea     rcx, [rbp+pbKeyObject]
0x140059349  call    ??$make_unique_hlocal_secure@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_secure<uchar [0]>(unsigned __int64)
0x14005934e  nop
0x14005934f  mov     eax, dword ptr [rbp+pbOutput]
0x140059352  mov     rdx, [rbp+pbKeyObject]
0x140059356  mov     [rbp+phKey], r12
0x14005935a  mov     [rsp+80h+var_40], r12d; dwFlags
0x14005935f  mov     [rsp+80h+cbInput], 40h ; '@'; cbInput
0x140059367  mov     [rsp+80h+pbInput], rbx; pbInput
0x14005936c  mov     [rsp+80h+cbKeyObject], eax; cbKeyObject
0x140059370  mov     qword ptr [rsp+80h+dwFlags], rdx; int
0x140059375  lea     r9, [rbp+phKey]; phKey
0x140059379  lea     r8, pszBlobType; "KeyDataBlob"
0x140059380  xor     edx, edx; hImportKey
0x140059382  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x140059386  call    cs:__imp_BCryptImportKey
0x14005938d  nop     dword ptr [rax+rax+00h]
0x140059392  test    eax, eax
0x140059394  jns     short loc_1400593C8
0x140059396  mov     rcx, [rbp+38h]; this
0x14005939a  mov     r9d, eax; char *
0x14005939d  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\biometrics\\serv"...
0x1400593a4  mov     edx, 87h; void *
0x1400593a9  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1400593ae  mov     ebx, eax
0x1400593b0  lea     rcx, [rbp+phKey]
0x1400593b4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1400593b9  nop
0x1400593ba  lea     rcx, [rbp+pbKeyObject]
0x1400593be  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x1400593c3  jmp     loc_1400594AC
0x1400593c8  mov     eax, esi
0x1400593ca  and     eax, 0Fh
0x1400593cd  mov     edi, esi
0x1400593cf  jz      short loc_1400593D6
0x1400593d1  sub     edi, eax
0x1400593d3  add     edi, 10h
0x1400593d6  mov     edx, edi
0x1400593d8  lea     rcx, [rbp+var_28]
0x1400593dc  call    ??$make_unique_hlocal@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<uchar [0]>(unsigned __int64)
0x1400593e1  mov     r8d, edi; Size
0x1400593e4  xor     edx, edx; Val
0x1400593e6  mov     rcx, [rbp+var_28]; void *
0x1400593ea  call    memset_0
0x1400593ef  mov     r8, rsi; Size
0x1400593f2  mov     rdx, r15; Src
0x1400593f5  mov     rcx, [rbp+var_28]; void *
0x1400593f9  call    memcpy_0
0x1400593fe  mov     [rsp+80h+var_38], r12d; dwFlags
0x140059403  mov     rax, [rbp+arg_28]
0x140059407  mov     qword ptr [rsp+80h+var_40], rax; pcbResult
0x14005940c  mov     eax, [rbp+cbOutput]
0x14005940f  mov     [rsp+80h+cbInput], eax; cbOutput
0x140059413  mov     [rsp+80h+pbInput], r14; pbOutput
0x140059418  mov     [rsp+80h+cbKeyObject], r12d; cbIV
0x14005941d  mov     qword ptr [rsp+80h+dwFlags], r12; int
0x140059422  xor     r9d, r9d; pPaddingInfo
0x140059425  mov     r8d, edi; cbInput
0x140059428  mov     rdx, [rbp+var_28]; pbInput
0x14005942c  mov     rcx, [rbp+phKey]; hKey
0x140059430  call    cs:__imp_BCryptEncrypt
0x140059437  nop     dword ptr [rax+rax+00h]
0x14005943c  test    eax, eax
0x14005943e  jns     short loc_14005947C
0x140059440  mov     rcx, [rbp+38h]; this
0x140059444  mov     r9d, eax; char *
0x140059447  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\biometrics\\serv"...
0x14005944e  mov     edx, 0A3h; void *
0x140059453  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x140059458  mov     ebx, eax
0x14005945a  mov     rcx, [rbp+var_28]; hMem
0x14005945e  mov     [rbp+var_28], r12
0x140059462  test    rcx, rcx
0x140059465  jz      loc_1400593B0
0x14005946b  call    cs:__imp_LocalFree
0x140059472  nop     dword ptr [rax+rax+00h]
0x140059477  jmp     loc_1400593B0
0x14005947c  mov     rcx, [rbp+var_28]; hMem
0x140059480  mov     [rbp+var_28], r12
0x140059484  test    rcx, rcx
0x140059487  jz      short loc_140059496
0x140059489  call    cs:__imp_LocalFree
0x140059490  nop     dword ptr [rax+rax+00h]
0x140059495  nop
0x140059496  lea     rcx, [rbp+phKey]
0x14005949a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14005949f  nop
0x1400594a0  lea     rcx, [rbp+pbKeyObject]
0x1400594a4  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x1400594a9  mov     ebx, r12d
0x1400594ac  lea     rcx, [rbp+phAlgorithm]
0x1400594b0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400594b5  mov     eax, ebx
0x1400594b7  add     rsp, 80h
0x1400594be  pop     r15
0x1400594c0  pop     r14
0x1400594c2  pop     r12
0x1400594c4  pop     rdi
0x1400594c5  pop     rsi
0x1400594c6  pop     rbx
0x1400594c7  pop     rbp
0x1400594c8  retn
```
