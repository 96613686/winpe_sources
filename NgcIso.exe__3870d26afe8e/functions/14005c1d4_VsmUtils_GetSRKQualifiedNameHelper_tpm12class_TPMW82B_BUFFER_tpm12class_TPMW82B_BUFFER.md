# VsmUtils::GetSRKQualifiedNameHelper(tpm12class::TPMW82B_BUFFER *,tpm12class::TPMW82B_BUFFER *)

- ea: `0x14005c1d4`
- end: `0x14005c3f8`
- name: `?GetSRKQualifiedNameHelper@VsmUtils@@YAJPEAVTPMW82B_BUFFER@tpm12class@@0@Z`
- size: `548`
- prototype: `int(VsmUtils *__hidden this, struct tpm12class::TPMW82B_BUFFER *, struct tpm12class::TPMW82B_BUFFER *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14005bc68`
- `0x14005c07c`

## callees

- `0x14000e034`
- `0x14000f914`
- `0x14000fabc`
- `0x14000fb24`
- `0x14002bdcc`
- `0x140040338`
- `0x140054f54`
- `0x140054f8c`
- `0x14005c1d4`
- `0x140061fb0`
- `0x140062520`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x14005c2f7`
- `bcrypt!BCryptCreateHash` at `0x14005c2f7`
- `bcrypt!BCryptHashData` at `0x14005c33f`
- `bcrypt!BCryptHashData` at `0x14005c360`
- `bcrypt!BCryptHashData` at `0x14005c33f`
- `bcrypt!BCryptHashData` at `0x14005c360`
- `bcrypt!BCryptFinishHash` at `0x14005c38f`
- `bcrypt!BCryptFinishHash` at `0x14005c38f`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x14005c29f`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x14005c29f`

## string_xrefs

- `0x14005c250`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmhelper.cpp`
- `0x14005c2b0`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmhelper.cpp`
- `0x14005c306`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmhelper.cpp`
- `0x14005c3bf`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall VsmUtils::GetSRKQualifiedNameHelper(
        PUCHAR *this,
        struct tpm12class::TPMW82B_BUFFER *a2,
        struct tpm12class::TPMW82B_BUFFER *a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  NTSTATUS v7; // eax
  NTSTATUS v8; // eax
  __int64 v9; // rdx
  int v10; // eax
  int pbSecret; // [rsp+20h] [rbp-30h]
  int pbSecreta; // [rsp+20h] [rbp-30h]
  BCRYPT_ALG_HANDLE phAlgorithm[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  int pbInput; // [rsp+80h] [rbp+30h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+88h] [rbp+38h] BYREF

  if ( dword_14009DD9C > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 4LL) )
  {
    Init_thread_header(&dword_14009DD9C);
    if ( dword_14009DD9C == -1 )
    {
      atexit(VsmUtils::GetSRKQualifiedNameHelper_::_2_::_dynamic_atexit_destructor_for__localSrkQN__);
      Init_thread_footer(&dword_14009DD9C);
    }
  }
  v5 = tpm12class::TPMW82B_BUFFER::Allocate((tpm12class::TPMW82B_BUFFER *)&off_14009A1A0, 0x22u);
  v6 = v5;
  if ( v5 >= 0 )
  {
    *(_BYTE *)qword_14009A1E0 = 0;
    *((_BYTE *)qword_14009A1E0 + 1) = 11;
    phAlgorithm[0] = 0;
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      phAlgorithm,
      0);
    v7 = BCryptOpenAlgorithmProvider(phAlgorithm, L"SHA256", 0, 0);
    if ( v7 < 0 )
    {
      v6 = wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x241,
             (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmhelper.cpp",
             (const char *)(unsigned int)v7,
             pbSecret);
LABEL_21:
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(phAlgorithm);
      return v6;
    }
    phHash = 0;
    v8 = BCryptCreateHash(phAlgorithm[0], &phHash, 0, 0, 0, 0, 0);
    if ( v8 >= 0 )
    {
      pbInput = 16777280;
      v8 = BCryptHashData(phHash, (PUCHAR)&pbInput, 4u, 0);
      if ( v8 >= 0 )
      {
        v8 = BCryptHashData(phHash, this[8], *((unsigned __int16 *)this + 28), 0);
        if ( v8 >= 0 )
        {
          v8 = BCryptFinishHash(phHash, (PUCHAR)qword_14009A1E0 + 2, (unsigned __int16)word_14009A1D8 - 2, 0);
          if ( v8 >= 0 )
          {
            v10 = tpm12class::TPMW82B_BUFFER::CopyFrom(a2, (const struct tpm12class::TPMW82B_BUFFER *)&off_14009A1A0);
            v6 = v10;
            if ( v10 >= 0 )
            {
              wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phHash);
              v6 = 0;
              goto LABEL_21;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x24F,
              (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmhelper.cpp",
              (const char *)(unsigned int)v10,
              pbSecreta);
            goto LABEL_11;
          }
          v9 = 589;
        }
        else
        {
          v9 = 586;
        }
      }
      else
      {
        v9 = 584;
      }
    }
    else
    {
      v9 = 580;
    }
    v6 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)v9,
           (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmhelper.cpp",
           (const char *)(unsigned int)v8,
           pbSecreta);
LABEL_11:
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phHash);
    goto LABEL_21;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x23D,
    (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmhelper.cpp",
    (const char *)(unsigned int)v5,
    pbSecret);
  return v6;
}

```

## disassembly

```asm
0x14005c1d4  mov     [rsp-18h+arg_0], rbx
0x14005c1d9  push    rbp
0x14005c1da  push    rsi
0x14005c1db  push    rdi
0x14005c1dc  mov     rbp, rsp
0x14005c1df  sub     rsp, 50h
0x14005c1e3  mov     rsi, rdx
0x14005c1e6  mov     rdi, rcx
0x14005c1e9  mov     ecx, 4
0x14005c1ee  mov     rax, gs:58h
0x14005c1f7  mov     rax, [rax]
0x14005c1fa  mov     eax, [rcx+rax]
0x14005c1fd  cmp     cs:dword_14009DD9C, eax
0x14005c203  jle     short loc_14005C232
0x14005c205  lea     rcx, dword_14009DD9C
0x14005c20c  call    _Init_thread_header
0x14005c211  cmp     cs:dword_14009DD9C, 0FFFFFFFFh
0x14005c218  jnz     short loc_14005C232
0x14005c21a  lea     rcx, _VsmUtils__GetSRKQualifiedNameHelper____2____dynamic_atexit_destructor_for__localSrkQN__; void (__cdecl *)()
0x14005c221  call    atexit
0x14005c226  lea     rcx, dword_14009DD9C
0x14005c22d  call    _Init_thread_footer
0x14005c232  mov     edx, 22h ; '"'; unsigned __int64
0x14005c237  lea     rcx, off_14009A1A0; this
0x14005c23e  call    ?Allocate@TPMW82B_BUFFER@tpm12class@@QEAAJ_K@Z; tpm12class::TPMW82B_BUFFER::Allocate(unsigned __int64)
0x14005c243  mov     ebx, eax
0x14005c245  test    eax, eax
0x14005c247  jns     short loc_14005C266
0x14005c249  mov     rcx, [rbp+18h]; this
0x14005c24d  mov     r9d, eax; char *
0x14005c250  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\trustlet\\utils"...
0x14005c257  mov     edx, 23Dh; void *
0x14005c25c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005c261  jmp     loc_14005C3E9
0x14005c266  mov     rax, cs:qword_14009A1E0
0x14005c26d  mov     byte ptr [rax], 0
0x14005c270  mov     rax, cs:qword_14009A1E0
0x14005c277  mov     byte ptr [rax+1], 0Bh
0x14005c27b  mov     [rbp+phAlgorithm], 0
0x14005c283  xor     edx, edx
0x14005c285  lea     rcx, [rbp+phAlgorithm]
0x14005c289  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x14005c28e  xor     r9d, r9d; dwFlags
0x14005c291  xor     r8d, r8d; pszImplementation
0x14005c294  lea     rdx, aSha256; "SHA256"
0x14005c29b  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x14005c29f  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14005c2a5  test    eax, eax
0x14005c2a7  jns     short loc_14005C2C8
0x14005c2a9  mov     rcx, [rbp+18h]; this
0x14005c2ad  mov     r9d, eax; char *
0x14005c2b0  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\trustlet\\utils"...
0x14005c2b7  mov     edx, 241h; void *
0x14005c2bc  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x14005c2c1  mov     ebx, eax
0x14005c2c3  jmp     loc_14005C3E0
0x14005c2c8  mov     [rbp+phHash], 0
0x14005c2d0  mov     [rsp+50h+dwFlags], 0; dwFlags
0x14005c2d8  mov     [rsp+50h+cbSecret], 0; cbSecret
0x14005c2e0  mov     [rsp+50h+pbSecret], 0; int
0x14005c2e9  xor     r9d, r9d; cbHashObject
0x14005c2ec  xor     r8d, r8d; pbHashObject
0x14005c2ef  lea     rdx, [rbp+phHash]; phHash
0x14005c2f3  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x14005c2f7  call    cs:__imp_BCryptCreateHash
0x14005c2fd  test    eax, eax
0x14005c2ff  jns     short loc_14005C329
0x14005c301  mov     edx, 244h; void *
0x14005c306  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\trustlet\\utils"...
0x14005c30d  mov     r9d, eax; char *
0x14005c310  mov     rcx, [rbp+18h]; this
0x14005c314  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x14005c319  mov     ebx, eax
0x14005c31b  lea     rcx, [rbp+phHash]
0x14005c31f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14005c324  jmp     loc_14005C3E0
0x14005c329  mov     [rbp+pbInput], 1000040h
0x14005c330  xor     r9d, r9d; dwFlags
0x14005c333  lea     r8d, [r9+4]; cbInput
0x14005c337  lea     rdx, [rbp+pbInput]; pbInput
0x14005c33b  mov     rcx, [rbp+phHash]; hHash
0x14005c33f  call    cs:__imp_BCryptHashData
0x14005c345  test    eax, eax
0x14005c347  jns     short loc_14005C350
0x14005c349  mov     edx, 248h
0x14005c34e  jmp     short loc_14005C306
0x14005c350  movzx   r8d, word ptr [rdi+38h]; cbInput
0x14005c355  xor     r9d, r9d; dwFlags
0x14005c358  mov     rdx, [rdi+40h]; pbInput
0x14005c35c  mov     rcx, [rbp+phHash]; hHash
0x14005c360  call    cs:__imp_BCryptHashData
0x14005c366  test    eax, eax
0x14005c368  jns     short loc_14005C371
0x14005c36a  mov     edx, 24Ah
0x14005c36f  jmp     short loc_14005C306
0x14005c371  movzx   r8d, cs:word_14009A1D8
0x14005c379  sub     r8d, 2; cbOutput
0x14005c37d  mov     rdx, cs:qword_14009A1E0
0x14005c384  add     rdx, 2; pbOutput
0x14005c388  xor     r9d, r9d; dwFlags
0x14005c38b  mov     rcx, [rbp+phHash]; hHash
0x14005c38f  call    cs:__imp_BCryptFinishHash
0x14005c395  test    eax, eax
0x14005c397  jns     short loc_14005C3A3
0x14005c399  mov     edx, 24Dh
0x14005c39e  jmp     loc_14005C306
0x14005c3a3  lea     rdx, off_14009A1A0; struct tpm12class::TPMW82B_BUFFER *
0x14005c3aa  mov     rcx, rsi; this
0x14005c3ad  call    ?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBV12@@Z; tpm12class::TPMW82B_BUFFER::CopyFrom(tpm12class::TPMW82B_BUFFER const *)
0x14005c3b2  mov     ebx, eax
0x14005c3b4  test    eax, eax
0x14005c3b6  jns     short loc_14005C3D5
0x14005c3b8  mov     rcx, [rbp+18h]; this
0x14005c3bc  mov     r9d, eax; char *
0x14005c3bf  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\trustlet\\utils"...
0x14005c3c6  mov     edx, 24Fh; void *
0x14005c3cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005c3d0  jmp     loc_14005C31B
0x14005c3d5  lea     rcx, [rbp+phHash]
0x14005c3d9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14005c3de  xor     ebx, ebx
0x14005c3e0  lea     rcx, [rbp+phAlgorithm]
0x14005c3e4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14005c3e9  mov     eax, ebx
0x14005c3eb  mov     rbx, [rsp+50h+arg_0]
0x14005c3f0  add     rsp, 50h
0x14005c3f4  pop     rdi
0x14005c3f5  pop     rsi
0x14005c3f6  pop     rbp
0x14005c3f7  retn
```
