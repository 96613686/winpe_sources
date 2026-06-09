# TpmKey12Rsa::OpenPubKeyHandle(void)

- ea: `0x180086880`
- end: `0x180086b08`
- name: `?OpenPubKeyHandle@TpmKey12Rsa@@IEAAJXZ`
- size: `648`
- prototype: `__int64 __fastcall(TpmKey12Rsa *__hidden this)`
- caller_count: `3`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180073520`
- `0x180085530`
- `0x1800878b0`

## callees

- `0x1800133c4`
- `0x180014a60`
- `0x1800157c0`
- `0x18005600c`
- `0x180056fec`
- `0x180061bac`
- `0x180073798`
- `0x180084d48`
- `0x180086880`
- `0x18009ccbc`
- `0x18009ff70`
- `0x1800a0054`

## import_xrefs

- `bcrypt!BCryptImportKeyPair` at `0x180086a1c`
- `bcrypt!BCryptImportKeyPair` at `0x180086ab0`
- `bcrypt!BCryptImportKeyPair` at `0x180086a1c`
- `bcrypt!BCryptImportKeyPair` at `0x180086ab0`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800868e1`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800868e1`

## string_xrefs

- `0x180086897`: `TpmKey12Rsa::OpenPubKeyHandle`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TpmKey12Rsa::OpenPubKeyHandle(TpmKey12Rsa *this)
{
  BCRYPT_KEY_HANDLE *v2; // rsi
  BCRYPT_ALG_HANDLE *v3; // rdi
  NTSTATUS v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  int PubKey; // eax
  __int64 v8; // rdx
  int v9; // eax
  NTSTATUS v10; // eax
  ULONG v11; // ebx
  PUCHAR v12; // rax
  NTSTATUS v13; // eax
  int pbInput; // [rsp+20h] [rbp-89h]
  int pbInputa; // [rsp+20h] [rbp-89h]
  int pbInputb; // [rsp+20h] [rbp-89h]
  PUCHAR v18[3]; // [rsp+40h] [rbp-69h] BYREF
  PUCHAR v19[3]; // [rsp+58h] [rbp-51h] BYREF
  _BYTE v20[80]; // [rsp+70h] [rbp-39h] BYREF
  _BYTE v21[64]; // [rsp+C0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]
  ULONG cbInput; // [rsp+110h] [rbp+67h] BYREF

  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v21, L"TpmKey12Rsa::OpenPubKeyHandle", 1);
  cbInput = 0;
  v2 = (BCRYPT_KEY_HANDLE *)((char *)this + 200);
  if ( *((_QWORD *)this + 25) )
    goto LABEL_23;
  v3 = (BCRYPT_ALG_HANDLE *)((char *)this + 192);
  if ( *((_QWORD *)this + 24)
    || (v4 = BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)this + 24, L"RSA", L"Microsoft Primitive Provider", 0),
        v4 >= 0) )
  {
    v6 = *((_QWORD *)this + 20);
    if ( v6 )
    {
      v11 = *(_DWORD *)(v6 + 12) + 24 + *(_DWORD *)(v6 + 8);
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(
        v19,
        v6,
        v6 + v11);
      v12 = v19[0];
      *(_DWORD *)v19[0] = 826364754;
      *((_QWORD *)v12 + 2) = 0;
      v13 = BCryptImportKeyPair(*v3, 0, L"RSAPUBLICBLOB", v2, v19[0], v11, 0);
      if ( v13 < 0 )
      {
        v5 = wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)0x965,
               (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey12rsa.cpp",
               (const char *)(unsigned int)v13,
               pbInputb);
        std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v19);
        goto LABEL_24;
      }
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v19);
    }
    else
    {
      if ( !*((_QWORD *)this + 11) )
      {
        v5 = -2144795646;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x941,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey12rsa.cpp",
          (const char *)0x80290402LL,
          pbInput);
        goto LABEL_24;
      }
      tpm12class::TPM_PUBKEY::TPM_PUBKEY((tpm12class::TPM_PUBKEY *)v20);
      PubKey = tpm12class::TPM_KEY12::GetPubKey(
                 *((tpm12class::TPM_KEY12 **)this + 11),
                 (struct tpm12class::TPM_PUBKEY *)v20);
      v5 = PubKey;
      if ( PubKey < 0 )
      {
        v8 = 2374;
LABEL_10:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v8,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey12rsa.cpp",
          (const char *)(unsigned int)PubKey,
          pbInput);
LABEL_11:
        tpm12class::TPM_PUBKEY::~TPM_PUBKEY((tpm12class::TPM_PUBKEY *)v20);
        goto LABEL_24;
      }
      PubKey = tpm12class::TPM_PUBKEY::Export((tpm12class::TPM_PUBKEY *)v20, 0, 0, &cbInput);
      v5 = PubKey;
      if ( PubKey < 0 )
      {
        v8 = 2375;
        goto LABEL_10;
      }
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(
        v18,
        cbInput);
      v9 = tpm12class::TPM_PUBKEY::Export((tpm12class::TPM_PUBKEY *)v20, v18[0], cbInput, &cbInput);
      v5 = v9;
      if ( v9 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x949,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey12rsa.cpp",
          (const char *)(unsigned int)v9,
          pbInput);
LABEL_16:
        std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v18);
        goto LABEL_11;
      }
      v10 = BCryptImportKeyPair(*v3, 0, L"RSAPUBLICBLOB", v2, v18[0], cbInput, 0);
      if ( v10 < 0 )
      {
        v5 = wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)0x950,
               (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey12rsa.cpp",
               (const char *)(unsigned int)v10,
               pbInputa);
        goto LABEL_16;
      }
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v18);
      tpm12class::TPM_PUBKEY::~TPM_PUBKEY((tpm12class::TPM_PUBKEY *)v20);
    }
LABEL_23:
    v5 = 0;
    goto LABEL_24;
  }
  v5 = wil::details::in1diag3::Return_NtStatus(
         retaddr,
         (void *)0x937,
         (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey12rsa.cpp",
         (const char *)(unsigned int)v4,
         pbInput);
LABEL_24:
  KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v21);
  return v5;
}

```

## disassembly

```asm
0x180086880  push    rbp
0x180086882  push    rbx
0x180086883  push    rsi
0x180086884  push    rdi
0x180086885  lea     rbp, [rsp-3Fh]
0x18008688a  sub     rsp, 0E8h
0x180086891  mov     rbx, rcx
0x180086894  mov     r8b, 1; bool
0x180086897  lea     rdx, aTpmkey12rsaOpe; "TpmKey12Rsa::OpenPubKeyHandle"
0x18008689e  lea     rcx, [rbp+57h+var_40]; this
0x1800868a2  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x1800868a7  nop
0x1800868a8  mov     [rbp+57h+arg_0], 0
0x1800868af  lea     rsi, [rbx+0C8h]
0x1800868b6  cmp     qword ptr [rsi], 0
0x1800868ba  jnz     loc_180086AEE
0x1800868c0  lea     rdi, [rbx+0C0h]
0x1800868c7  cmp     qword ptr [rdi], 0
0x1800868cb  jnz     short loc_180086910
0x1800868cd  xor     r9d, r9d; dwFlags
0x1800868d0  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x1800868d7  lea     rdx, aRsa; "RSA"
0x1800868de  mov     rcx, rdi; phAlgorithm
0x1800868e1  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800868e8  nop     dword ptr [rax+rax+00h]
0x1800868ed  test    eax, eax
0x1800868ef  jns     short loc_180086910
0x1800868f1  mov     rcx, [rbp+5Fh]; this
0x1800868f5  mov     r9d, eax; char *
0x1800868f8  lea     r8, aOnecoreBaseNgs_23; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x1800868ff  mov     edx, 937h; void *
0x180086904  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180086909  mov     ebx, eax
0x18008690b  jmp     loc_180086AF0
0x180086910  mov     rdx, [rbx+0A0h]
0x180086917  test    rdx, rdx
0x18008691a  jnz     loc_180086A60
0x180086920  cmp     [rbx+58h], rdx
0x180086924  jnz     short loc_180086948
0x180086926  mov     rcx, [rbp+5Fh]; this
0x18008692a  mov     ebx, 80290402h
0x18008692f  mov     r9d, ebx; char *
0x180086932  lea     r8, aOnecoreBaseNgs_23; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180086939  mov     edx, 941h; void *
0x18008693e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180086943  jmp     loc_180086AF0
0x180086948  lea     rcx, [rbp+57h+var_90]; this
0x18008694c  call    ??0TPM_PUBKEY@tpm12class@@QEAA@XZ; tpm12class::TPM_PUBKEY::TPM_PUBKEY(void)
0x180086951  nop
0x180086952  lea     rdx, [rbp+57h+var_90]; struct tpm12class::TPM_PUBKEY *
0x180086956  mov     rcx, [rbx+58h]; this
0x18008695a  call    ?GetPubKey@TPM_KEY12@tpm12class@@QEAAJPEAVTPM_PUBKEY@2@@Z; tpm12class::TPM_KEY12::GetPubKey(tpm12class::TPM_PUBKEY *)
0x18008695f  mov     ebx, eax
0x180086961  test    eax, eax
0x180086963  jns     short loc_18008698C
0x180086965  mov     edx, 946h; void *
0x18008696a  lea     r8, aOnecoreBaseNgs_23; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180086971  mov     r9d, eax; char *
0x180086974  mov     rcx, [rbp+5Fh]; this
0x180086978  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008697d  nop
0x18008697e  lea     rcx, [rbp+57h+var_90]; this
0x180086982  call    ??1TPM_PUBKEY@tpm12class@@UEAA@XZ; tpm12class::TPM_PUBKEY::~TPM_PUBKEY(void)
0x180086987  jmp     loc_180086AF0
0x18008698c  lea     r9, [rbp+57h+arg_0]; unsigned int *
0x180086990  xor     r8d, r8d; unsigned int
0x180086993  xor     edx, edx; unsigned __int8 *
0x180086995  lea     rcx, [rbp+57h+var_90]; this
0x180086999  call    ?Export@TPM_PUBKEY@tpm12class@@QEAAJPEAEIPEAI@Z; tpm12class::TPM_PUBKEY::Export(uchar *,uint,uint *)
0x18008699e  mov     ebx, eax
0x1800869a0  test    eax, eax
0x1800869a2  jns     short loc_1800869AB
0x1800869a4  mov     edx, 947h
0x1800869a9  jmp     short loc_18008696A
0x1800869ab  mov     edx, [rbp+57h+arg_0]
0x1800869ae  lea     rcx, [rbp+57h+var_C0]
0x1800869b2  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@_KAEBU?$secure_allocator@E@wil@@@Z; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(unsigned __int64,wil::secure_allocator<uchar> const &)
0x1800869b7  lea     r9, [rbp+57h+arg_0]; unsigned int *
0x1800869bb  mov     r8d, [rbp+57h+arg_0]; unsigned int
0x1800869bf  mov     rdx, [rbp+57h+var_C0]; unsigned __int8 *
0x1800869c3  lea     rcx, [rbp+57h+var_90]; this
0x1800869c7  call    ?Export@TPM_PUBKEY@tpm12class@@QEAAJPEAEIPEAI@Z; tpm12class::TPM_PUBKEY::Export(uchar *,uint,uint *)
0x1800869cc  mov     ebx, eax
0x1800869ce  test    eax, eax
0x1800869d0  jns     short loc_1800869F5
0x1800869d2  mov     rcx, [rbp+5Fh]; this
0x1800869d6  mov     r9d, eax; char *
0x1800869d9  lea     r8, aOnecoreBaseNgs_23; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x1800869e0  mov     edx, 949h; void *
0x1800869e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800869ea  lea     rcx, [rbp+57h+var_C0]
0x1800869ee  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x1800869f3  jmp     short loc_18008697E
0x1800869f5  mov     rdx, [rbp+57h+var_C0]
0x1800869f9  mov     [rsp+100h+dwFlags], 0; dwFlags
0x180086a01  mov     eax, [rbp+57h+arg_0]
0x180086a04  mov     [rsp+100h+cbInput], eax; cbInput
0x180086a08  mov     [rsp+100h+pbInput], rdx; int
0x180086a0d  mov     r9, rsi; phKey
0x180086a10  lea     r8, aRsapublicblob; "RSAPUBLICBLOB"
0x180086a17  xor     edx, edx; hImportKey
0x180086a19  mov     rcx, [rdi]; hAlgorithm
0x180086a1c  call    cs:__imp_BCryptImportKeyPair
0x180086a23  nop     dword ptr [rax+rax+00h]
0x180086a28  test    eax, eax
0x180086a2a  jns     short loc_180086A48
0x180086a2c  mov     rcx, [rbp+5Fh]; this
0x180086a30  mov     r9d, eax; char *
0x180086a33  lea     r8, aOnecoreBaseNgs_23; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180086a3a  mov     edx, 950h; void *
0x180086a3f  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180086a44  mov     ebx, eax
0x180086a46  jmp     short loc_1800869EA
0x180086a48  lea     rcx, [rbp+57h+var_C0]
0x180086a4c  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x180086a51  nop
0x180086a52  lea     rcx, [rbp+57h+var_90]; this
0x180086a56  call    ??1TPM_PUBKEY@tpm12class@@UEAA@XZ; tpm12class::TPM_PUBKEY::~TPM_PUBKEY(void)
0x180086a5b  jmp     loc_180086AEE
0x180086a60  mov     ecx, [rdx+0Ch]
0x180086a63  mov     ebx, [rdx+8]
0x180086a66  add     ecx, 18h
0x180086a69  add     ebx, ecx
0x180086a6b  mov     r8d, ebx
0x180086a6e  add     r8, rdx
0x180086a71  lea     rcx, [rbp+57h+var_A8]
0x180086a75  call    ??$?0PEAE$0A@@?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@PEAE0AEBU?$secure_allocator@E@wil@@@Z; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(uchar *,uchar *,wil::secure_allocator<uchar> const &)
0x180086a7a  mov     rax, [rbp+57h+var_A8]
0x180086a7e  mov     dword ptr [rax], 31415352h
0x180086a84  mov     qword ptr [rax+10h], 0
0x180086a8c  mov     rax, [rbp+57h+var_A8]
0x180086a90  mov     [rsp+100h+dwFlags], 0; dwFlags
0x180086a98  mov     [rsp+100h+cbInput], ebx; cbInput
0x180086a9c  mov     [rsp+100h+pbInput], rax; int
0x180086aa1  mov     r9, rsi; phKey
0x180086aa4  lea     r8, aRsapublicblob; "RSAPUBLICBLOB"
0x180086aab  xor     edx, edx; hImportKey
0x180086aad  mov     rcx, [rdi]; hAlgorithm
0x180086ab0  call    cs:__imp_BCryptImportKeyPair
0x180086ab7  nop     dword ptr [rax+rax+00h]
0x180086abc  test    eax, eax
0x180086abe  jns     short loc_180086AE5
0x180086ac0  mov     rcx, [rbp+5Fh]; this
0x180086ac4  mov     r9d, eax; char *
0x180086ac7  lea     r8, aOnecoreBaseNgs_23; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180086ace  mov     edx, 965h; void *
0x180086ad3  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180086ad8  mov     ebx, eax
0x180086ada  lea     rcx, [rbp+57h+var_A8]
0x180086ade  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x180086ae3  jmp     short loc_180086AF0
0x180086ae5  lea     rcx, [rbp+57h+var_A8]
0x180086ae9  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x180086aee  xor     ebx, ebx
0x180086af0  lea     rcx, [rbp+57h+var_40]; this
0x180086af4  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180086af9  mov     eax, ebx
0x180086afb  add     rsp, 0E8h
0x180086b02  pop     rdi
0x180086b03  pop     rsi
0x180086b04  pop     rbx
0x180086b05  pop     rbp
0x180086b06  retn
```
