# FileUtils::ComputeSha256Hash(uchar *,ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18002b410`
- end: `0x18002b70d`
- name: `?ComputeSha256Hash@FileUtils@@SAJPEAEKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `765`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18002c958`

## callees

- `0x18000a6e0`
- `0x18000abc4`
- `0x18001206c`
- `0x18001208c`
- `0x180013a7c`
- `0x180013b04`
- `0x18001964c`
- `0x1800198b0`
- `0x18002992c`
- `0x18002b240`
- `0x18002b260`
- `0x18002b410`
- `0x18002c77c`
- `0x18002cb84`

## import_xrefs

- `CRYPT32!CryptBinaryToStringW` at `0x18002b607`
- `CRYPT32!CryptBinaryToStringW` at `0x18002b689`
- `CRYPT32!CryptBinaryToStringW` at `0x18002b607`
- `CRYPT32!CryptBinaryToStringW` at `0x18002b689`
- `bcrypt!BCryptHashData` at `0x18002b5b5`
- `bcrypt!BCryptHashData` at `0x18002b5b5`
- `bcrypt!BCryptFinishHash` at `0x18002b5d4`
- `bcrypt!BCryptFinishHash` at `0x18002b5d4`
- `bcrypt!BCryptCreateHash` at `0x18002b568`
- `bcrypt!BCryptCreateHash` at `0x18002b568`
- `bcrypt!BCryptGetProperty` at `0x18002b499`
- `bcrypt!BCryptGetProperty` at `0x18002b4ec`
- `bcrypt!BCryptGetProperty` at `0x18002b499`
- `bcrypt!BCryptGetProperty` at `0x18002b4ec`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18002b452`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18002b452`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall FileUtils::ComputeSha256Hash(PUCHAR pbInput, ULONG cbInput, __int64 a3)
{
  NTSTATUS Property; // eax
  __int64 v7; // rdx
  unsigned int v8; // ebx
  int v9; // edi
  UCHAR *v10; // rbx
  NTSTATUS v11; // eax
  __int64 v12; // rdx
  int LastError; // eax
  unsigned __int64 v14; // rdx
  const char *v15; // r9
  WCHAR *v16; // rax
  const char *v17; // r9
  unsigned __int64 v18; // rdx
  int pcbResult; // [rsp+20h] [rbp-39h]
  int pcbResulta; // [rsp+20h] [rbp-39h]
  int pcbResultb; // [rsp+20h] [rbp-39h]
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-19h] BYREF
  DWORD pcchString; // [rsp+48h] [rbp-11h] BYREF
  UCHAR pbOutput[4]; // [rsp+4Ch] [rbp-Dh] BYREF
  ULONG v26; // [rsp+50h] [rbp-9h] BYREF
  UCHAR v27[4]; // [rsp+54h] [rbp-5h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+58h] [rbp-1h] BYREF
  PUCHAR pbHashObject; // [rsp+60h] [rbp+7h] BYREF
  _BYTE v30[32]; // [rsp+68h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  phAlgorithm = 0;
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0);
  if ( Property < 0 )
  {
    v7 = 261;
LABEL_5:
    v8 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)v7,
           (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\utils\\fileutils.cpp",
           (const char *)(unsigned int)Property,
           pcbResult);
    goto LABEL_30;
  }
  *(_DWORD *)pbOutput = 0;
  v26 = 0;
  Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", pbOutput, 4u, &v26, 0);
  if ( Property < 0 )
  {
    v7 = 266;
    goto LABEL_5;
  }
  *(_DWORD *)v27 = 0;
  Property = BCryptGetProperty(phAlgorithm, L"HashDigestLength", v27, 4u, &v26, 0);
  if ( Property < 0 )
  {
    v7 = 270;
    goto LABEL_5;
  }
  if ( *(_DWORD *)v27 != 32 )
  {
    v9 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10F,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\utils\\fileutils.cpp",
      (const char *)0x8000FFFFLL,
      pcbResult);
LABEL_10:
    v8 = v9;
    goto LABEL_30;
  }
  wil::make_unique_nothrow<unsigned char [0]>(&pbHashObject, *(unsigned int *)pbOutput);
  v10 = pbHashObject;
  phHash = 0;
  v11 = BCryptCreateHash(phAlgorithm, &phHash, pbHashObject, *(ULONG *)pbOutput, 0, 0, 0);
  if ( v11 < 0 )
  {
    v12 = 274;
LABEL_13:
    LastError = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)v12,
                  (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\utils\\fileutils.cpp",
                  (const char *)(unsigned int)v11,
                  pcbResulta);
LABEL_14:
    v9 = LastError;
    goto LABEL_15;
  }
  v11 = BCryptHashData(phHash, pbInput, cbInput, 0);
  if ( v11 < 0 )
  {
    v12 = 277;
    goto LABEL_13;
  }
  v11 = BCryptFinishHash(phHash, v10, 0x20u, 0);
  if ( v11 < 0 )
  {
    v12 = 278;
    goto LABEL_13;
  }
  pcchString = 0;
  if ( !CryptBinaryToStringW(v10, 0x20u, 0x40000001u, 0, &pcchString) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x11F,
                  (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\utils\\fileutils.cpp",
                  v15);
    goto LABEL_14;
  }
  if ( pcchString != 45 )
  {
    v9 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x120,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\utils\\fileutils.cpp",
      (const char *)0x8000FFFFLL,
      pcbResultb);
    goto LABEL_15;
  }
  std::wstring::wstring((__int64)v30);
  std::wstring::resize(v30, pcchString);
  v16 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v30);
  if ( !CryptBinaryToStringW(v10, 0x20u, 0x40000001u, v16, &pcchString) )
  {
    v9 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x12A,
           (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\utils\\fileutils.cpp",
           v17);
    std::wstring::_Tidy_deallocate(v30);
LABEL_15:
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phHash);
    if ( v10 )
      operator delete(v10, v14);
    goto LABEL_10;
  }
  std::wstring::operator=(a3, v30);
  std::wstring::_Tidy_deallocate(v30);
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phHash);
  if ( v10 )
    operator delete(v10, v18);
  v8 = 0;
LABEL_30:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
  return v8;
}

```

## disassembly

```asm
0x18002b410  push    rbp
0x18002b412  push    rbx
0x18002b413  push    rsi
0x18002b414  push    rdi
0x18002b415  push    r14
0x18002b417  lea     rbp, [rsp-37h]
0x18002b41c  sub     rsp, 90h
0x18002b423  mov     rax, cs:__security_cookie
0x18002b42a  xor     rax, rsp
0x18002b42d  mov     [rbp+57h+var_28], rax
0x18002b431  mov     r14, r8
0x18002b434  mov     esi, edx
0x18002b436  mov     rdi, rcx
0x18002b439  mov     [rbp+57h+phAlgorithm], 0
0x18002b441  xor     r9d, r9d; dwFlags
0x18002b444  xor     r8d, r8d; pszImplementation
0x18002b447  lea     rdx, pszAlgId; "SHA256"
0x18002b44e  lea     rcx, [rbp+57h+phAlgorithm]; phAlgorithm
0x18002b452  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18002b458  test    eax, eax
0x18002b45a  jns     short loc_18002B463
0x18002b45c  mov     edx, 105h
0x18002b461  jmp     short loc_18002B4A8
0x18002b463  mov     dword ptr [rbp+57h+pbOutput], 0
0x18002b46a  mov     [rbp+57h+var_60], 0
0x18002b471  mov     [rsp+0B0h+dwFlags], 0; dwFlags
0x18002b479  lea     rax, [rbp+57h+var_60]
0x18002b47d  mov     [rsp+0B0h+pcbResult], rax; int
0x18002b482  mov     ebx, 4
0x18002b487  mov     r9d, ebx; cbOutput
0x18002b48a  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x18002b48e  lea     rdx, pszProperty; "ObjectLength"
0x18002b495  mov     rcx, [rbp+57h+phAlgorithm]; hObject
0x18002b499  call    cs:__imp_BCryptGetProperty
0x18002b49f  test    eax, eax
0x18002b4a1  jns     short loc_18002B4C2
0x18002b4a3  mov     edx, 10Ah; void *
0x18002b4a8  mov     rcx, [rbp+5Fh]; this
0x18002b4ac  mov     r9d, eax; char *
0x18002b4af  lea     r8, aOnecoreBaseDia_1; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18002b4b6  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002b4bb  mov     ebx, eax
0x18002b4bd  jmp     loc_18002B6E8
0x18002b4c2  mov     dword ptr [rbp+57h+var_5C], 0
0x18002b4c9  mov     [rsp+0B0h+dwFlags], 0; dwFlags
0x18002b4d1  lea     rax, [rbp+57h+var_60]
0x18002b4d5  mov     [rsp+0B0h+pcbResult], rax; int
0x18002b4da  mov     r9d, ebx; cbOutput
0x18002b4dd  lea     r8, [rbp+57h+var_5C]; pbOutput
0x18002b4e1  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18002b4e8  mov     rcx, [rbp+57h+phAlgorithm]; hObject
0x18002b4ec  call    cs:__imp_BCryptGetProperty
0x18002b4f2  test    eax, eax
0x18002b4f4  jns     short loc_18002B4FD
0x18002b4f6  mov     edx, 10Eh
0x18002b4fb  jmp     short loc_18002B4A8
0x18002b4fd  cmp     dword ptr [rbp+57h+var_5C], 20h ; ' '
0x18002b501  jz      short loc_18002B527
0x18002b503  mov     rcx, [rbp+5Fh]; this
0x18002b507  mov     edi, 8000FFFFh
0x18002b50c  mov     r9d, edi; char *
0x18002b50f  lea     r8, aOnecoreBaseDia_1; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18002b516  mov     edx, 10Fh; void *
0x18002b51b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b520  mov     ebx, edi
0x18002b522  jmp     loc_18002B6E8
0x18002b527  mov     edx, dword ptr [rbp+57h+pbOutput]
0x18002b52a  lea     rcx, [rbp+57h+pbHashObject]
0x18002b52e  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x18002b533  nop
0x18002b534  mov     rbx, [rbp+57h+pbHashObject]
0x18002b538  mov     [rbp+57h+phHash], 0
0x18002b540  mov     [rsp+0B0h+var_80], 0; dwFlags
0x18002b548  mov     [rsp+0B0h+dwFlags], 0; cbSecret
0x18002b550  mov     [rsp+0B0h+pcbResult], 0; int
0x18002b559  mov     r9d, dword ptr [rbp+57h+pbOutput]; cbHashObject
0x18002b55d  mov     r8, rbx; pbHashObject
0x18002b560  lea     rdx, [rbp+57h+phHash]; phHash
0x18002b564  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x18002b568  call    cs:__imp_BCryptCreateHash
0x18002b56e  test    eax, eax
0x18002b570  jns     short loc_18002B5A8
0x18002b572  mov     edx, 112h; void *
0x18002b577  mov     rcx, [rbp+5Fh]; this
0x18002b57b  mov     r9d, eax; char *
0x18002b57e  lea     r8, aOnecoreBaseDia_1; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18002b585  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002b58a  mov     edi, eax
0x18002b58c  lea     rcx, [rbp+57h+phHash]
0x18002b590  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002b595  nop
0x18002b596  test    rbx, rbx
0x18002b599  jz      short loc_18002B520
0x18002b59b  mov     rcx, rbx; void *
0x18002b59e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002b5a3  jmp     loc_18002B520
0x18002b5a8  xor     r9d, r9d; dwFlags
0x18002b5ab  mov     r8d, esi; cbInput
0x18002b5ae  mov     rdx, rdi; pbInput
0x18002b5b1  mov     rcx, [rbp+57h+phHash]; hHash
0x18002b5b5  call    cs:__imp_BCryptHashData
0x18002b5bb  test    eax, eax
0x18002b5bd  jns     short loc_18002B5C6
0x18002b5bf  mov     edx, 115h
0x18002b5c4  jmp     short loc_18002B577
0x18002b5c6  xor     r9d, r9d; dwFlags
0x18002b5c9  lea     r8d, [r9+20h]; cbOutput
0x18002b5cd  mov     rdx, rbx; pbOutput
0x18002b5d0  mov     rcx, [rbp+57h+phHash]; hHash
0x18002b5d4  call    cs:__imp_BCryptFinishHash
0x18002b5da  test    eax, eax
0x18002b5dc  jns     short loc_18002B5E5
0x18002b5de  mov     edx, 116h
0x18002b5e3  jmp     short loc_18002B577
0x18002b5e5  mov     [rbp+57h+pcchString], 0
0x18002b5ec  lea     rax, [rbp+57h+pcchString]
0x18002b5f0  mov     [rsp+0B0h+pcbResult], rax; int
0x18002b5f5  xor     r9d, r9d; pszString
0x18002b5f8  mov     edi, 40000001h
0x18002b5fd  mov     r8d, edi; dwFlags
0x18002b600  lea     edx, [r9+20h]; cbBinary
0x18002b604  mov     rcx, rbx; pbBinary
0x18002b607  call    cs:__imp_CryptBinaryToStringW
0x18002b60d  test    eax, eax
0x18002b60f  jnz     short loc_18002B62B
0x18002b611  mov     rcx, [rbp+5Fh]; this
0x18002b615  lea     r8, aOnecoreBaseDia_1; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18002b61c  mov     edx, 11Fh; void *
0x18002b621  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002b626  jmp     loc_18002B58A
0x18002b62b  cmp     [rbp+57h+pcchString], 2Dh ; '-'
0x18002b62f  jz      short loc_18002B653
0x18002b631  mov     rcx, [rbp+5Fh]; this
0x18002b635  mov     edi, 8000FFFFh
0x18002b63a  mov     r9d, edi; char *
0x18002b63d  lea     r8, aOnecoreBaseDia_1; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18002b644  mov     edx, 120h; void *
0x18002b649  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b64e  jmp     loc_18002B58C
0x18002b653  lea     rcx, [rbp+57h+var_48]
0x18002b657  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002b65c  nop
0x18002b65d  mov     edx, [rbp+57h+pcchString]
0x18002b660  lea     rcx, [rbp+57h+var_48]
0x18002b664  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18002b669  lea     rcx, [rbp+57h+var_48]
0x18002b66d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002b672  mov     r9, rax; pszString
0x18002b675  lea     rax, [rbp+57h+pcchString]
0x18002b679  mov     [rsp+0B0h+pcbResult], rax; pcchString
0x18002b67e  mov     r8d, edi; dwFlags
0x18002b681  mov     edx, 20h ; ' '; cbBinary
0x18002b686  mov     rcx, rbx; pbBinary
0x18002b689  call    cs:__imp_CryptBinaryToStringW
0x18002b68f  test    eax, eax
0x18002b691  jnz     short loc_18002B6B8
0x18002b693  mov     rcx, [rbp+5Fh]; this
0x18002b697  lea     r8, aOnecoreBaseDia_1; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18002b69e  mov     edx, 12Ah; void *
0x18002b6a3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002b6a8  mov     edi, eax
0x18002b6aa  lea     rcx, [rbp+57h+var_48]
0x18002b6ae  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002b6b3  jmp     loc_18002B58C
0x18002b6b8  lea     rdx, [rbp+57h+var_48]
0x18002b6bc  mov     rcx, r14
0x18002b6bf  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18002b6c4  nop
0x18002b6c5  lea     rcx, [rbp+57h+var_48]
0x18002b6c9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002b6ce  nop
0x18002b6cf  lea     rcx, [rbp+57h+phHash]
0x18002b6d3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002b6d8  nop
0x18002b6d9  test    rbx, rbx
0x18002b6dc  jz      short loc_18002B6E6
0x18002b6de  mov     rcx, rbx; void *
0x18002b6e1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002b6e6  xor     ebx, ebx
0x18002b6e8  lea     rcx, [rbp+57h+phAlgorithm]
0x18002b6ec  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002b6f1  mov     eax, ebx
0x18002b6f3  mov     rcx, [rbp+57h+var_28]
0x18002b6f7  xor     rcx, rsp; StackCookie
0x18002b6fa  call    __security_check_cookie
0x18002b6ff  add     rsp, 90h
0x18002b706  pop     r14
0x18002b708  pop     rdi
0x18002b709  pop     rsi
0x18002b70a  pop     rbx
0x18002b70b  pop     rbp
0x18002b70c  retn
```
