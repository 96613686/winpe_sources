# FSCreateHash(ushort const *,uchar *,ulong,uchar *,ulong,ulong *)

- ea: `0x18003fcdc`
- end: `0x18003ff31`
- name: `?FSCreateHash@@YAJPEBGPEAEK1KPEAK@Z`
- size: `597`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int8 *, ULONG, unsigned __int8 *, ULONG pbOutput, unsigned int *)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800337b0`
- `0x180033dc0`
- `0x180044ce8`

## callees

- `0x180002f90`
- `0x180003274`
- `0x1800060f8`
- `0x180006a98`
- `0x18003f604`
- `0x18003f644`
- `0x18003fcdc`

## import_xrefs

- `bcrypt!BCryptDestroyHash` at `0x18003fe20`
- `bcrypt!BCryptDestroyHash` at `0x18003fe20`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18003fd5c`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18003fd5c`
- `bcrypt!BCryptGetProperty` at `0x18003fdd3`
- `bcrypt!BCryptGetProperty` at `0x18003fdd3`
- `bcrypt!BCryptFinishHash` at `0x18003fecf`
- `bcrypt!BCryptFinishHash` at `0x18003fecf`
- `bcrypt!BCryptHashData` at `0x18003fe98`
- `bcrypt!BCryptHashData` at `0x18003fe98`
- `bcrypt!BCryptCreateHash` at `0x18003fe5e`
- `bcrypt!BCryptCreateHash` at `0x18003fe5e`

## pseudocode

```c
__int64 __fastcall FSCreateHash(
        const unsigned __int16 *a1,
        unsigned __int8 *a2,
        ULONG a3,
        unsigned __int8 *a4,
        ULONG pbOutput,
        unsigned int *a6)
{
  unsigned int *v6; // rdi
  int v10; // ebx
  NTSTATUS v11; // ecx
  __int64 v12; // rdx
  NTSTATUS Property; // ecx
  ULONG v14; // eax
  NTSTATUS v15; // ecx
  NTSTATUS v16; // ecx
  NTSTATUS v17; // ecx
  BCRYPT_HASH_HANDLE hHash; // [rsp+40h] [rbp-10h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-8h] BYREF
  ULONG pcbResult; // [rsp+80h] [rbp+30h] BYREF
  int v22; // [rsp+84h] [rbp+34h]

  v22 = HIDWORD(a1);
  v6 = a6;
  phAlgorithm = 0;
  hHash = 0;
  pbOutput = 0;
  pcbResult = 0;
  if ( !a6 )
  {
    v10 = -2147467261;
    goto LABEL_36;
  }
  *a6 = 0;
  if ( !a2 || !a3 )
  {
    v10 = -2147024809;
    goto LABEL_36;
  }
  v10 = 0;
  v11 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0);
  if ( v11 < 0 )
    v10 = v11 | 0x10000000;
  if ( v10 < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_36;
    v12 = 10;
LABEL_10:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids, 0, v10);
    goto LABEL_36;
  }
  v10 = 0;
  Property = BCryptGetProperty(phAlgorithm, L"HashDigestLength", (PUCHAR)&pbOutput, 4u, &pcbResult, 0);
  if ( Property < 0 )
    v10 = Property | 0x10000000;
  if ( v10 < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_36;
    v12 = 11;
    goto LABEL_10;
  }
  v14 = pbOutput;
  *v6 = pbOutput;
  if ( v14 > 0x20 )
  {
    v10 = -1072860816;
    goto LABEL_36;
  }
  if ( hHash )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&a6);
    BCryptDestroyHash(hHash);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&a6);
  }
  hHash = 0;
  v10 = 0;
  v15 = BCryptCreateHash(phAlgorithm, &hHash, 0, 0, 0, 0, 0);
  if ( v15 < 0 )
    v10 = v15 | 0x10000000;
  if ( v10 < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_36;
    v12 = 12;
    goto LABEL_10;
  }
  v10 = 0;
  v16 = BCryptHashData(hHash, a2, a3, 0);
  if ( v16 < 0 )
    v10 = v16 | 0x10000000;
  if ( v10 < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_36;
    v12 = 13;
    goto LABEL_10;
  }
  v10 = 0;
  v17 = BCryptFinishHash(hHash, a4, pbOutput, 0);
  if ( v17 < 0 )
    v10 = v17 | 0x10000000;
  if ( v10 < 0 && _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v12 = 14;
    goto LABEL_10;
  }
LABEL_36:
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hHash);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18003fcdc  mov     [rsp-28h+arg_8], rbx
0x18003fce1  mov     [rsp-28h+arg_10], rsi
0x18003fce6  mov     qword ptr [rsp-28h+arg_0], rcx
0x18003fceb  push    rbp
0x18003fcec  push    rdi
0x18003fced  push    r13
0x18003fcef  push    r14
0x18003fcf1  push    r15
0x18003fcf3  mov     rbp, rsp
0x18003fcf6  sub     rsp, 50h
0x18003fcfa  mov     rdi, [rbp+arg_28]
0x18003fcfe  mov     r15, r9
0x18003fd01  mov     [rbp+phAlgorithm], 0
0x18003fd09  mov     esi, r8d
0x18003fd0c  mov     [rbp+hHash], 0
0x18003fd14  mov     r14, rdx
0x18003fd17  mov     dword ptr [rbp+pbOutput], 0
0x18003fd1e  mov     [rbp+arg_0], 0
0x18003fd25  test    rdi, rdi
0x18003fd28  jnz     short loc_18003FD34
0x18003fd2a  mov     ebx, 80004003h
0x18003fd2f  jmp     loc_18003FF04
0x18003fd34  mov     dword ptr [rdi], 0
0x18003fd3a  test    r14, r14
0x18003fd3d  jz      loc_18003FEFF
0x18003fd43  test    esi, esi
0x18003fd45  jz      loc_18003FEFF
0x18003fd4b  xor     r9d, r9d; dwFlags
0x18003fd4e  lea     rdx, pszAlgId; "SHA256"
0x18003fd55  xor     r8d, r8d; pszImplementation
0x18003fd58  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x18003fd5c  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18003fd62  xor     ebx, ebx
0x18003fd64  mov     r13d, 10000000h
0x18003fd6a  mov     ecx, eax
0x18003fd6c  or      eax, r13d
0x18003fd6f  test    ecx, ecx
0x18003fd71  cmovs   ebx, eax
0x18003fd74  test    ebx, ebx
0x18003fd76  jns     short loc_18003FDAD
0x18003fd78  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003fd7d  cmp     al, 1
0x18003fd7f  jb      loc_18003FF04
0x18003fd85  mov     edx, 0Ah
0x18003fd8a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fd91  lea     r8, WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids
0x18003fd98  xor     r9d, r9d
0x18003fd9b  mov     dword ptr [rsp+50h+pcbResult], ebx
0x18003fd9f  mov     rcx, [rcx+10h]
0x18003fda3  call    WPP_SF_qD
0x18003fda8  jmp     loc_18003FF04
0x18003fdad  mov     rcx, [rbp+phAlgorithm]; hObject
0x18003fdb1  lea     rax, [rbp+arg_0]
0x18003fdb5  mov     [rsp+50h+dwFlags], 0; dwFlags
0x18003fdbd  lea     r8, [rbp+pbOutput]; pbOutput
0x18003fdc1  mov     r9d, 4; cbOutput
0x18003fdc7  mov     [rsp+50h+pcbResult], rax; pcbResult
0x18003fdcc  lea     rdx, pszProperty; "HashDigestLength"
0x18003fdd3  call    cs:__imp_BCryptGetProperty
0x18003fdd9  xor     ebx, ebx
0x18003fddb  mov     ecx, eax
0x18003fddd  or      eax, r13d
0x18003fde0  test    ecx, ecx
0x18003fde2  cmovs   ebx, eax
0x18003fde5  test    ebx, ebx
0x18003fde7  jns     short loc_18003FDFD
0x18003fde9  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003fdee  cmp     al, 1
0x18003fdf0  jb      loc_18003FF04
0x18003fdf6  mov     edx, 0Bh
0x18003fdfb  jmp     short loc_18003FD8A
0x18003fdfd  mov     eax, dword ptr [rbp+pbOutput]
0x18003fe00  mov     [rdi], eax
0x18003fe02  cmp     eax, 20h ; ' '
0x18003fe05  ja      loc_18003FEF8
0x18003fe0b  mov     rbx, [rbp+hHash]
0x18003fe0f  test    rbx, rbx
0x18003fe12  jz      short loc_18003FE2F
0x18003fe14  lea     rcx, [rbp+arg_28]; this
0x18003fe18  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18003fe1d  mov     rcx, rbx; hHash
0x18003fe20  call    cs:__imp_BCryptDestroyHash
0x18003fe26  lea     rcx, [rbp+arg_28]; this
0x18003fe2a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18003fe2f  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18003fe33  lea     rdx, [rbp+hHash]; phHash
0x18003fe37  mov     [rsp+50h+var_20], 0; dwFlags
0x18003fe3f  xor     r9d, r9d; cbHashObject
0x18003fe42  mov     [rsp+50h+dwFlags], 0; cbSecret
0x18003fe4a  xor     r8d, r8d; pbHashObject
0x18003fe4d  mov     [rsp+50h+pcbResult], 0; pbSecret
0x18003fe56  mov     [rbp+hHash], 0
0x18003fe5e  call    cs:__imp_BCryptCreateHash
0x18003fe64  xor     ebx, ebx
0x18003fe66  mov     ecx, eax
0x18003fe68  or      eax, r13d
0x18003fe6b  test    ecx, ecx
0x18003fe6d  cmovs   ebx, eax
0x18003fe70  test    ebx, ebx
0x18003fe72  jns     short loc_18003FE8B
0x18003fe74  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003fe79  cmp     al, 1
0x18003fe7b  jb      loc_18003FF04
0x18003fe81  mov     edx, 0Ch
0x18003fe86  jmp     loc_18003FD8A
0x18003fe8b  mov     rcx, [rbp+hHash]; hHash
0x18003fe8f  xor     r9d, r9d; dwFlags
0x18003fe92  mov     r8d, esi; cbInput
0x18003fe95  mov     rdx, r14; pbInput
0x18003fe98  call    cs:__imp_BCryptHashData
0x18003fe9e  xor     ebx, ebx
0x18003fea0  mov     ecx, eax
0x18003fea2  or      eax, r13d
0x18003fea5  test    ecx, ecx
0x18003fea7  cmovs   ebx, eax
0x18003feaa  test    ebx, ebx
0x18003feac  jns     short loc_18003FEC1
0x18003feae  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003feb3  cmp     al, 1
0x18003feb5  jb      short loc_18003FF04
0x18003feb7  mov     edx, 0Dh
0x18003febc  jmp     loc_18003FD8A
0x18003fec1  mov     r8d, dword ptr [rbp+pbOutput]; cbOutput
0x18003fec5  xor     r9d, r9d; dwFlags
0x18003fec8  mov     rcx, [rbp+hHash]; hHash
0x18003fecc  mov     rdx, r15; pbOutput
0x18003fecf  call    cs:__imp_BCryptFinishHash
0x18003fed5  xor     ebx, ebx
0x18003fed7  mov     ecx, eax
0x18003fed9  or      eax, r13d
0x18003fedc  test    ecx, ecx
0x18003fede  cmovs   ebx, eax
0x18003fee1  test    ebx, ebx
0x18003fee3  jns     short loc_18003FF04
0x18003fee5  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003feea  cmp     al, 1
0x18003feec  jb      short loc_18003FF04
0x18003feee  mov     edx, 0Eh
0x18003fef3  jmp     loc_18003FD8A
0x18003fef8  mov     ebx, 0C00D7170h
0x18003fefd  jmp     short loc_18003FF04
0x18003feff  mov     ebx, 80070057h
0x18003ff04  lea     rcx, [rbp+hHash]
0x18003ff08  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18003ff0d  lea     rcx, [rbp+phAlgorithm]
0x18003ff11  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003ff16  lea     r11, [rsp+50h+var_s0]
0x18003ff1b  mov     eax, ebx
0x18003ff1d  mov     rbx, [r11+38h]
0x18003ff21  mov     rsi, [r11+40h]
0x18003ff25  mov     rsp, r11
0x18003ff28  pop     r15
0x18003ff2a  pop     r14
0x18003ff2c  pop     r13
0x18003ff2e  pop     rdi
0x18003ff2f  pop     rbp
0x18003ff30  retn
```
