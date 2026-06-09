# GetHash(std::vector<uchar,std::allocator<uchar>> const &,std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x140040b48`
- end: `0x140040cb1`
- name: `?GetHash@@YAJAEBV?$vector@EV?$allocator@E@std@@@std@@AEAV12@@Z`
- size: `361`
- prototype: ``
- caller_count: `7`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140040cb8`
- `0x140040de4`
- `0x140040f18`
- `0x14004107c`
- `0x1400413bc`
- `0x140041500`
- `0x1400416c0`

## callees

- `0x140009be0`
- `0x140009fa0`
- `0x14000ac7c`
- `0x14000e034`
- `0x14002bdcc`
- `0x140040338`
- `0x140040b48`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x140040b8d`
- `bcrypt!BCryptCreateHash` at `0x140040b8d`
- `bcrypt!BCryptHashData` at `0x140040baf`
- `bcrypt!BCryptHashData` at `0x140040baf`
- `bcrypt!BCryptGetProperty` at `0x140040c0c`
- `bcrypt!BCryptGetProperty` at `0x140040c0c`
- `bcrypt!BCryptFinishHash` at `0x140040c50`
- `bcrypt!BCryptFinishHash` at `0x140040c50`

## string_xrefs

- `0x140040bbe`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\clientauth.cpp`
- `0x140040c1f`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\clientauth.cpp`
- `0x140040c61`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\clientauth.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetHash(__int64 a1, __int64 a2)
{
  NTSTATUS v4; // eax
  __int64 v5; // rdx
  unsigned int v6; // ebx
  NTSTATUS Property; // eax
  NTSTATUS v8; // eax
  int pcbResult; // [rsp+20h] [rbp-40h]
  int pcbResulta; // [rsp+20h] [rbp-40h]
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-20h] BYREF
  PUCHAR v13; // [rsp+48h] [rbp-18h] BYREF
  int v14; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]
  unsigned int pbOutput; // [rsp+80h] [rbp+20h] BYREF
  ULONG v17; // [rsp+88h] [rbp+28h] BYREF

  phHash = 0;
  v4 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x41, &phHash, 0, 0, 0, 0, 0);
  if ( v4 < 0 )
  {
    v5 = 11;
LABEL_5:
    v6 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)v5,
           (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\clientauth.cpp",
           (const char *)(unsigned int)v4,
           pcbResult);
    goto LABEL_11;
  }
  v4 = BCryptHashData(phHash, *(PUCHAR *)a1, *(_DWORD *)(a1 + 8) - *(_DWORD *)a1, 0);
  if ( v4 < 0 )
  {
    v5 = 14;
    goto LABEL_5;
  }
  pbOutput = 0;
  v17 = 0;
  Property = BCryptGetProperty(phHash, L"HashDigestLength", (PUCHAR)&pbOutput, 4u, &v17, 0);
  v6 = Property;
  if ( Property >= 0 )
  {
    std::vector<unsigned char>::vector<unsigned char>(&v13, pbOutput);
    v8 = BCryptFinishHash(phHash, v13, v14 - (_DWORD)v13, 0);
    if ( v8 >= 0 )
    {
      std::vector<unsigned char>::operator=(a2, &v13);
      std::vector<unsigned char>::_Tidy(&v13);
      v6 = 0;
    }
    else
    {
      v6 = wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x18,
             (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\clientauth.cpp",
             (const char *)(unsigned int)v8,
             pcbResulta);
      std::vector<unsigned char>::_Tidy(&v13);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\clientauth.cpp",
      (const char *)(unsigned int)Property,
      pcbResulta);
  }
LABEL_11:
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phHash);
  return v6;
}

```

## disassembly

```asm
0x140040b48  mov     rax, rsp
0x140040b4b  mov     [rax+8], rbx
0x140040b4f  mov     [rax+10h], rdi
0x140040b53  push    rbp
0x140040b54  mov     rbp, rsp
0x140040b57  sub     rsp, 60h
0x140040b5b  mov     rdi, rdx
0x140040b5e  mov     rbx, rcx
0x140040b61  mov     [rbp+phHash], 0
0x140040b69  mov     dword ptr [rax-38h], 0
0x140040b70  mov     dword ptr [rax-40h], 0
0x140040b77  mov     qword ptr [rax-48h], 0
0x140040b7f  xor     r9d, r9d; cbHashObject
0x140040b82  xor     r8d, r8d; pbHashObject
0x140040b85  lea     rdx, [rbp+phHash]; phHash
0x140040b89  lea     ecx, [r9+41h]; hAlgorithm
0x140040b8d  call    cs:__imp_BCryptCreateHash
0x140040b93  test    eax, eax
0x140040b95  jns     short loc_140040B9E
0x140040b97  mov     edx, 0Bh
0x140040b9c  jmp     short loc_140040BBE
0x140040b9e  mov     r8d, [rbx+8]
0x140040ba2  sub     r8d, [rbx]; cbInput
0x140040ba5  xor     r9d, r9d; dwFlags
0x140040ba8  mov     rdx, [rbx]; pbInput
0x140040bab  mov     rcx, [rbp+phHash]; hHash
0x140040baf  call    cs:__imp_BCryptHashData
0x140040bb5  test    eax, eax
0x140040bb7  jns     short loc_140040BD8
0x140040bb9  mov     edx, 0Eh; void *
0x140040bbe  lea     r8, aOnecoreDsSecur_22; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x140040bc5  mov     r9d, eax; char *
0x140040bc8  mov     rcx, [rbp+8]; this
0x140040bcc  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x140040bd1  mov     ebx, eax
0x140040bd3  jmp     loc_140040C96
0x140040bd8  mov     [rbp+pbOutput], 0
0x140040bdf  mov     [rbp+arg_18], 0
0x140040be6  mov     [rsp+60h+dwFlags], 0; dwFlags
0x140040bee  lea     rax, [rbp+arg_18]
0x140040bf2  mov     [rsp+60h+pcbResult], rax; int
0x140040bf7  mov     r9d, 4; cbOutput
0x140040bfd  lea     r8, [rbp+pbOutput]; pbOutput
0x140040c01  lea     rdx, pszProperty; "HashDigestLength"
0x140040c08  mov     rcx, [rbp+phHash]; hObject
0x140040c0c  call    cs:__imp_BCryptGetProperty
0x140040c12  mov     ebx, eax
0x140040c14  test    eax, eax
0x140040c16  jns     short loc_140040C32
0x140040c18  mov     rcx, [rbp+8]; this
0x140040c1c  mov     r9d, eax; char *
0x140040c1f  lea     r8, aOnecoreDsSecur_22; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x140040c26  mov     edx, 14h; void *
0x140040c2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140040c30  jmp     short loc_140040C96
0x140040c32  mov     edx, [rbp+pbOutput]
0x140040c35  lea     rcx, [rbp+var_18]
0x140040c39  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x140040c3e  mov     r8d, [rbp+var_10]
0x140040c42  mov     rdx, [rbp+var_18]; pbOutput
0x140040c46  sub     r8d, edx; cbOutput
0x140040c49  xor     r9d, r9d; dwFlags
0x140040c4c  mov     rcx, [rbp+phHash]; hHash
0x140040c50  call    cs:__imp_BCryptFinishHash
0x140040c56  test    eax, eax
0x140040c58  jns     short loc_140040C7F
0x140040c5a  mov     rcx, [rbp+8]; this
0x140040c5e  mov     r9d, eax; char *
0x140040c61  lea     r8, aOnecoreDsSecur_22; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x140040c68  mov     edx, 18h; void *
0x140040c6d  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x140040c72  mov     ebx, eax
0x140040c74  lea     rcx, [rbp+var_18]
0x140040c78  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140040c7d  jmp     short loc_140040C96
0x140040c7f  lea     rdx, [rbp+var_18]
0x140040c83  mov     rcx, rdi
0x140040c86  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x140040c8b  lea     rcx, [rbp+var_18]
0x140040c8f  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140040c94  xor     ebx, ebx
0x140040c96  lea     rcx, [rbp+phHash]
0x140040c9a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140040c9f  mov     eax, ebx
0x140040ca1  mov     rbx, [rsp+60h+arg_0]
0x140040ca6  mov     rdi, [rsp+60h+arg_8]
0x140040cab  add     rsp, 60h
0x140040caf  pop     rbp
0x140040cb0  retn
```
