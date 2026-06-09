# FSCreateHash(ushort const *,uchar *,ulong,uchar *,ulong,ulong *)

- ea: `0x1800273e0`
- end: `0x180027635`
- name: `?FSCreateHash@@YAJPEBGPEAEK1KPEAK@Z`
- size: `597`
- prototype: `int(const unsigned __int16 *, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18002c4a0`
- `0x18002ca90`

## callees

- `0x180005b94`
- `0x180005e78`
- `0x180009608`
- `0x180026eec`
- `0x180026f2c`
- `0x1800273e0`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x180027562`
- `bcrypt!BCryptCreateHash` at `0x180027562`
- `bcrypt!BCryptGetProperty` at `0x1800274d7`
- `bcrypt!BCryptGetProperty` at `0x1800274d7`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180027460`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180027460`
- `bcrypt!BCryptDestroyHash` at `0x180027524`
- `bcrypt!BCryptDestroyHash` at `0x180027524`
- `bcrypt!BCryptHashData` at `0x18002759c`
- `bcrypt!BCryptHashData` at `0x18002759c`
- `bcrypt!BCryptFinishHash` at `0x1800275d3`
- `bcrypt!BCryptFinishHash` at `0x1800275d3`

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
    if ( !g_wppLevels )
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
    if ( !g_wppLevels )
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
    if ( !g_wppLevels )
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
    if ( !g_wppLevels )
      goto LABEL_36;
    v12 = 13;
    goto LABEL_10;
  }
  v10 = 0;
  v17 = BCryptFinishHash(hHash, a4, pbOutput, 0);
  if ( v17 < 0 )
    v10 = v17 | 0x10000000;
  if ( v10 < 0 && g_wppLevels )
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
0x1800273e0  mov     [rsp-28h+arg_8], rbx
0x1800273e5  mov     [rsp-28h+arg_10], rsi
0x1800273ea  mov     qword ptr [rsp-28h+arg_0], rcx
0x1800273ef  push    rbp
0x1800273f0  push    rdi
0x1800273f1  push    r13
0x1800273f3  push    r14
0x1800273f5  push    r15
0x1800273f7  mov     rbp, rsp
0x1800273fa  sub     rsp, 50h
0x1800273fe  mov     rdi, [rbp+arg_28]
0x180027402  mov     r15, r9
0x180027405  mov     [rbp+phAlgorithm], 0
0x18002740d  mov     esi, r8d
0x180027410  mov     [rbp+hHash], 0
0x180027418  mov     r14, rdx
0x18002741b  mov     dword ptr [rbp+pbOutput], 0
0x180027422  mov     [rbp+arg_0], 0
0x180027429  test    rdi, rdi
0x18002742c  jnz     short loc_180027438
0x18002742e  mov     ebx, 80004003h
0x180027433  jmp     loc_180027608
0x180027438  mov     dword ptr [rdi], 0
0x18002743e  test    r14, r14
0x180027441  jz      loc_180027603
0x180027447  test    esi, esi
0x180027449  jz      loc_180027603
0x18002744f  xor     r9d, r9d; dwFlags
0x180027452  lea     rdx, pszAlgId; "SHA256"
0x180027459  xor     r8d, r8d; pszImplementation
0x18002745c  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x180027460  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180027466  xor     ebx, ebx
0x180027468  mov     r13d, 10000000h
0x18002746e  mov     ecx, eax
0x180027470  or      eax, r13d
0x180027473  test    ecx, ecx
0x180027475  cmovs   ebx, eax
0x180027478  test    ebx, ebx
0x18002747a  jns     short loc_1800274B1
0x18002747c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180027483  jb      loc_180027608
0x180027489  mov     edx, 0Ah
0x18002748e  mov     rcx, cs:WPP_GLOBAL_Control
0x180027495  lea     r8, WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids
0x18002749c  xor     r9d, r9d
0x18002749f  mov     dword ptr [rsp+50h+pcbResult], ebx
0x1800274a3  mov     rcx, [rcx+10h]
0x1800274a7  call    WPP_SF_qD
0x1800274ac  jmp     loc_180027608
0x1800274b1  mov     rcx, [rbp+phAlgorithm]; hObject
0x1800274b5  lea     rax, [rbp+arg_0]
0x1800274b9  mov     [rsp+50h+dwFlags], 0; dwFlags
0x1800274c1  lea     r8, [rbp+pbOutput]; pbOutput
0x1800274c5  mov     r9d, 4; cbOutput
0x1800274cb  mov     [rsp+50h+pcbResult], rax; pcbResult
0x1800274d0  lea     rdx, pszProperty; "HashDigestLength"
0x1800274d7  call    cs:__imp_BCryptGetProperty
0x1800274dd  xor     ebx, ebx
0x1800274df  mov     ecx, eax
0x1800274e1  or      eax, r13d
0x1800274e4  test    ecx, ecx
0x1800274e6  cmovs   ebx, eax
0x1800274e9  test    ebx, ebx
0x1800274eb  jns     short loc_180027501
0x1800274ed  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800274f4  jb      loc_180027608
0x1800274fa  mov     edx, 0Bh
0x1800274ff  jmp     short loc_18002748E
0x180027501  mov     eax, dword ptr [rbp+pbOutput]
0x180027504  mov     [rdi], eax
0x180027506  cmp     eax, 20h ; ' '
0x180027509  ja      loc_1800275FC
0x18002750f  mov     rbx, [rbp+hHash]
0x180027513  test    rbx, rbx
0x180027516  jz      short loc_180027533
0x180027518  lea     rcx, [rbp+arg_28]; this
0x18002751c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180027521  mov     rcx, rbx; hHash
0x180027524  call    cs:__imp_BCryptDestroyHash
0x18002752a  lea     rcx, [rbp+arg_28]; this
0x18002752e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180027533  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180027537  lea     rdx, [rbp+hHash]; phHash
0x18002753b  mov     [rsp+50h+var_20], 0; dwFlags
0x180027543  xor     r9d, r9d; cbHashObject
0x180027546  mov     [rsp+50h+dwFlags], 0; cbSecret
0x18002754e  xor     r8d, r8d; pbHashObject
0x180027551  mov     [rsp+50h+pcbResult], 0; pbSecret
0x18002755a  mov     [rbp+hHash], 0
0x180027562  call    cs:__imp_BCryptCreateHash
0x180027568  xor     ebx, ebx
0x18002756a  mov     ecx, eax
0x18002756c  or      eax, r13d
0x18002756f  test    ecx, ecx
0x180027571  cmovs   ebx, eax
0x180027574  test    ebx, ebx
0x180027576  jns     short loc_18002758F
0x180027578  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002757f  jb      loc_180027608
0x180027585  mov     edx, 0Ch
0x18002758a  jmp     loc_18002748E
0x18002758f  mov     rcx, [rbp+hHash]; hHash
0x180027593  xor     r9d, r9d; dwFlags
0x180027596  mov     r8d, esi; cbInput
0x180027599  mov     rdx, r14; pbInput
0x18002759c  call    cs:__imp_BCryptHashData
0x1800275a2  xor     ebx, ebx
0x1800275a4  mov     ecx, eax
0x1800275a6  or      eax, r13d
0x1800275a9  test    ecx, ecx
0x1800275ab  cmovs   ebx, eax
0x1800275ae  test    ebx, ebx
0x1800275b0  jns     short loc_1800275C5
0x1800275b2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800275b9  jb      short loc_180027608
0x1800275bb  mov     edx, 0Dh
0x1800275c0  jmp     loc_18002748E
0x1800275c5  mov     r8d, dword ptr [rbp+pbOutput]; cbOutput
0x1800275c9  xor     r9d, r9d; dwFlags
0x1800275cc  mov     rcx, [rbp+hHash]; hHash
0x1800275d0  mov     rdx, r15; pbOutput
0x1800275d3  call    cs:__imp_BCryptFinishHash
0x1800275d9  xor     ebx, ebx
0x1800275db  mov     ecx, eax
0x1800275dd  or      eax, r13d
0x1800275e0  test    ecx, ecx
0x1800275e2  cmovs   ebx, eax
0x1800275e5  test    ebx, ebx
0x1800275e7  jns     short loc_180027608
0x1800275e9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800275f0  jb      short loc_180027608
0x1800275f2  mov     edx, 0Eh
0x1800275f7  jmp     loc_18002748E
0x1800275fc  mov     ebx, 0C00D7170h
0x180027601  jmp     short loc_180027608
0x180027603  mov     ebx, 80070057h
0x180027608  lea     rcx, [rbp+hHash]
0x18002760c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180027611  lea     rcx, [rbp+phAlgorithm]
0x180027615  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002761a  lea     r11, [rsp+50h+var_s0]
0x18002761f  mov     eax, ebx
0x180027621  mov     rbx, [r11+38h]
0x180027625  mov     rsi, [r11+40h]
0x180027629  mov     rsp, r11
0x18002762c  pop     r15
0x18002762e  pop     r14
0x180027630  pop     r13
0x180027632  pop     rdi
0x180027633  pop     rbp
0x180027634  retn
```
