# GetEnclaveIdentityHash(ENCLAVE_IDENTITY,std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x1400409b8`
- end: `0x140040b41`
- name: `?GetEnclaveIdentityHash@@YAJUENCLAVE_IDENTITY@@AEAV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `393`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400416c0`

## callees

- `0x140009be0`
- `0x140009fa0`
- `0x14000ac7c`
- `0x14000e034`
- `0x14002bdcc`
- `0x140040338`
- `0x1400409b8`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x1400409fd`
- `bcrypt!BCryptCreateHash` at `0x1400409fd`
- `bcrypt!BCryptHashData` at `0x140040a1d`
- `bcrypt!BCryptHashData` at `0x140040a55`
- `bcrypt!BCryptHashData` at `0x140040a1d`
- `bcrypt!BCryptHashData` at `0x140040a55`
- `bcrypt!BCryptGetProperty` at `0x140040a9a`
- `bcrypt!BCryptGetProperty` at `0x140040a9a`
- `bcrypt!BCryptFinishHash` at `0x140040ade`
- `bcrypt!BCryptFinishHash` at `0x140040ade`

## string_xrefs

- `0x140040a33`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\clientauth.cpp`
- `0x140040aad`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\clientauth.cpp`
- `0x140040aef`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\clientauth.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetEnclaveIdentityHash(__int64 a1, __int64 a2)
{
  NTSTATUS v4; // eax
  __int64 v5; // rdx
  unsigned int v6; // ebx
  NTSTATUS Property; // eax
  NTSTATUS v8; // eax
  int pcbResult; // [rsp+20h] [rbp-50h]
  int pcbResulta; // [rsp+20h] [rbp-50h]
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-30h] BYREF
  UCHAR pbOutput[4]; // [rsp+48h] [rbp-28h] BYREF
  ULONG v14; // [rsp+4Ch] [rbp-24h] BYREF
  PUCHAR v15; // [rsp+50h] [rbp-20h] BYREF
  int v16; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  phHash = 0;
  v4 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x41, &phHash, 0, 0, 0, 0, 0);
  if ( v4 < 0 )
  {
    v5 = 35;
LABEL_5:
    v6 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)v5,
           (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\clientauth.cpp",
           (const char *)(unsigned int)v4,
           pcbResult);
    goto LABEL_13;
  }
  v4 = BCryptHashData(phHash, (PUCHAR)(a1 + 64), 0x20u, 0);
  if ( v4 < 0 )
  {
    v5 = 40;
    goto LABEL_5;
  }
  v4 = BCryptHashData(phHash, (PUCHAR)(a1 + 112), 0x10u, 0);
  if ( v4 < 0 )
  {
    v5 = 42;
    goto LABEL_5;
  }
  *(_DWORD *)pbOutput = 0;
  v14 = 0;
  Property = BCryptGetProperty(phHash, L"HashDigestLength", pbOutput, 4u, &v14, 0);
  v6 = Property;
  if ( Property >= 0 )
  {
    std::vector<unsigned char>::vector<unsigned char>(&v15, *(unsigned int *)pbOutput);
    v8 = BCryptFinishHash(phHash, v15, v16 - (_DWORD)v15, 0);
    if ( v8 >= 0 )
    {
      std::vector<unsigned char>::operator=(a2, &v15);
      std::vector<unsigned char>::_Tidy(&v15);
      v6 = 0;
    }
    else
    {
      v6 = wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x34,
             (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\clientauth.cpp",
             (const char *)(unsigned int)v8,
             pcbResulta);
      std::vector<unsigned char>::_Tidy(&v15);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x30,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\clientauth.cpp",
      (const char *)(unsigned int)Property,
      pcbResulta);
  }
LABEL_13:
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phHash);
  return v6;
}

```

## disassembly

```asm
0x1400409b8  mov     rax, rsp
0x1400409bb  mov     [rax+18h], rbx
0x1400409bf  mov     [rax+20h], rdi
0x1400409c3  push    rbp
0x1400409c4  mov     rbp, rsp
0x1400409c7  sub     rsp, 70h
0x1400409cb  mov     rdi, rdx
0x1400409ce  mov     rbx, rcx
0x1400409d1  mov     [rbp+phHash], 0
0x1400409d9  mov     dword ptr [rax-48h], 0
0x1400409e0  mov     dword ptr [rax-50h], 0
0x1400409e7  mov     qword ptr [rax-58h], 0
0x1400409ef  xor     r9d, r9d; cbHashObject
0x1400409f2  xor     r8d, r8d; pbHashObject
0x1400409f5  lea     rdx, [rbp+phHash]; phHash
0x1400409f9  lea     ecx, [r9+41h]; hAlgorithm
0x1400409fd  call    cs:__imp_BCryptCreateHash
0x140040a03  test    eax, eax
0x140040a05  jns     short loc_140040A0E
0x140040a07  mov     edx, 23h ; '#'
0x140040a0c  jmp     short loc_140040A2C
0x140040a0e  lea     rdx, [rbx+40h]; pbInput
0x140040a12  xor     r9d, r9d; dwFlags
0x140040a15  lea     r8d, [r9+20h]; cbInput
0x140040a19  mov     rcx, [rbp+phHash]; hHash
0x140040a1d  call    cs:__imp_BCryptHashData
0x140040a23  test    eax, eax
0x140040a25  jns     short loc_140040A46
0x140040a27  mov     edx, 28h ; '('; void *
0x140040a2c  mov     rcx, [rbp+8]; this
0x140040a30  mov     r9d, eax; char *
0x140040a33  lea     r8, aOnecoreDsSecur_22; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x140040a3a  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x140040a3f  mov     ebx, eax
0x140040a41  jmp     loc_140040B24
0x140040a46  lea     rdx, [rbx+70h]; pbInput
0x140040a4a  xor     r9d, r9d; dwFlags
0x140040a4d  lea     r8d, [r9+10h]; cbInput
0x140040a51  mov     rcx, [rbp+phHash]; hHash
0x140040a55  call    cs:__imp_BCryptHashData
0x140040a5b  test    eax, eax
0x140040a5d  jns     short loc_140040A66
0x140040a5f  mov     edx, 2Ah ; '*'
0x140040a64  jmp     short loc_140040A2C
0x140040a66  mov     dword ptr [rbp+pbOutput], 0
0x140040a6d  mov     [rbp+var_24], 0
0x140040a74  mov     [rsp+70h+dwFlags], 0; dwFlags
0x140040a7c  lea     rax, [rbp+var_24]
0x140040a80  mov     [rsp+70h+pcbResult], rax; int
0x140040a85  mov     r9d, 4; cbOutput
0x140040a8b  lea     r8, [rbp+pbOutput]; pbOutput
0x140040a8f  lea     rdx, pszProperty; "HashDigestLength"
0x140040a96  mov     rcx, [rbp+phHash]; hObject
0x140040a9a  call    cs:__imp_BCryptGetProperty
0x140040aa0  mov     ebx, eax
0x140040aa2  test    eax, eax
0x140040aa4  jns     short loc_140040AC0
0x140040aa6  mov     rcx, [rbp+8]; this
0x140040aaa  mov     r9d, eax; char *
0x140040aad  lea     r8, aOnecoreDsSecur_22; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x140040ab4  mov     edx, 30h ; '0'; void *
0x140040ab9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140040abe  jmp     short loc_140040B24
0x140040ac0  mov     edx, dword ptr [rbp+pbOutput]
0x140040ac3  lea     rcx, [rbp+var_20]
0x140040ac7  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x140040acc  mov     r8d, [rbp+var_18]
0x140040ad0  mov     rdx, [rbp+var_20]; pbOutput
0x140040ad4  sub     r8d, edx; cbOutput
0x140040ad7  xor     r9d, r9d; dwFlags
0x140040ada  mov     rcx, [rbp+phHash]; hHash
0x140040ade  call    cs:__imp_BCryptFinishHash
0x140040ae4  test    eax, eax
0x140040ae6  jns     short loc_140040B0D
0x140040ae8  mov     rcx, [rbp+8]; this
0x140040aec  mov     r9d, eax; char *
0x140040aef  lea     r8, aOnecoreDsSecur_22; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x140040af6  mov     edx, 34h ; '4'; void *
0x140040afb  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x140040b00  mov     ebx, eax
0x140040b02  lea     rcx, [rbp+var_20]
0x140040b06  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140040b0b  jmp     short loc_140040B24
0x140040b0d  lea     rdx, [rbp+var_20]
0x140040b11  mov     rcx, rdi
0x140040b14  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x140040b19  lea     rcx, [rbp+var_20]
0x140040b1d  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140040b22  xor     ebx, ebx
0x140040b24  lea     rcx, [rbp+phHash]
0x140040b28  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140040b2d  mov     eax, ebx
0x140040b2f  lea     r11, [rsp+70h+var_s0]
0x140040b34  mov     rbx, [r11+20h]
0x140040b38  mov     rdi, [r11+28h]
0x140040b3c  mov     rsp, r11
0x140040b3f  pop     rbp
0x140040b40  retn
```
