# TpmKey20Rsa::OpenPubKeyHandle(void)

- ea: `0x18002c5a8`
- end: `0x18002c82a`
- name: `?OpenPubKeyHandle@TpmKey20Rsa@@IEAAJXZ`
- size: `642`
- prototype: `__int64 __fastcall(TpmKey20Rsa *__hidden this)`
- caller_count: `4`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18002c3b0`
- `0x18002e900`
- `0x18008b480`
- `0x18008cb50`

## callees

- `0x1800133c4`
- `0x180014a60`
- `0x1800157c0`
- `0x18002c5a8`
- `0x18004e314`
- `0x18005600c`
- `0x180056fec`
- `0x180061bac`
- `0x180084d48`

## import_xrefs

- `bcrypt!BCryptImportKeyPair` at `0x18002c749`
- `bcrypt!BCryptImportKeyPair` at `0x18002c7d2`
- `bcrypt!BCryptImportKeyPair` at `0x18002c749`
- `bcrypt!BCryptImportKeyPair` at `0x18002c7d2`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18002c604`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18002c604`

## string_xrefs

- `0x18002c5c1`: `TpmKey20Rsa::OpenPubKeyHandle`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TpmKey20Rsa::OpenPubKeyHandle(TpmKey20Rsa *this)
{
  BCRYPT_ALG_HANDLE *v2; // rsi
  NTSTATUS v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rbx
  unsigned int v7; // r8d
  int v8; // r9d
  unsigned int i; // edx
  unsigned __int64 v10; // rbx
  int v11; // eax
  PUCHAR *v12; // rcx
  NTSTATUS v13; // eax
  PUCHAR *v14; // rcx
  PUCHAR v15; // rax
  NTSTATUS v16; // eax
  int pbInput; // [rsp+20h] [rbp-39h]
  int pbInputa; // [rsp+20h] [rbp-39h]
  int pbInputb; // [rsp+20h] [rbp-39h]
  PUCHAR v21; // [rsp+40h] [rbp-19h] BYREF
  __int64 v22; // [rsp+48h] [rbp-11h]
  PUCHAR v23; // [rsp+58h] [rbp-1h] BYREF
  int v24; // [rsp+60h] [rbp+7h]
  _BYTE v25[64]; // [rsp+70h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v25, L"TpmKey20Rsa::OpenPubKeyHandle", 1);
  if ( *((_QWORD *)this + 129) )
    goto LABEL_25;
  v2 = (BCRYPT_ALG_HANDLE *)((char *)this + 1024);
  if ( *((_QWORD *)this + 128)
    || (v3 = BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)this + 128, L"RSA", L"Microsoft Primitive Provider", 0),
        v3 >= 0) )
  {
    v5 = *((_QWORD *)this + 81);
    if ( v5 )
    {
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(
        &v23,
        v5,
        v5 + (unsigned int)(*(_DWORD *)(v5 + 12) + 24 + *(_DWORD *)(v5 + 8)));
      v15 = v23;
      *(_DWORD *)v23 = 826364754;
      *((_QWORD *)v15 + 2) = 0;
      v16 = BCryptImportKeyPair(*v2, 0, L"RSAPUBLICBLOB", (BCRYPT_KEY_HANDLE *)this + 129, v23, v24 - (_DWORD)v23, 0);
      if ( v16 < 0 )
      {
        v4 = wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)0x671,
               (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
               (const char *)(unsigned int)v16,
               pbInputb);
        v12 = &v23;
        goto LABEL_17;
      }
      v14 = &v23;
    }
    else
    {
      v6 = *((_QWORD *)this + 12);
      if ( !v6 )
      {
        v4 = -2144795646;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x647,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
          (const char *)0x80290402LL,
          pbInput);
        goto LABEL_26;
      }
      KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)&v23, L"BCRYPT_RSAKEY_BLOB_From", 1);
      v7 = 3;
      v8 = *(_DWORD *)(v6 + 276);
      if ( v8 )
      {
        for ( i = 0; i < 4; ++i )
        {
          if ( ((0xFF000000 >> (8 * i)) & v8) != 0 )
          {
            v7 = 4 - i;
            break;
          }
        }
      }
      v10 = v7 + (unsigned __int64)*(unsigned __int16 *)(v6 + 816);
      KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)&v23);
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(
        &v21,
        v10 + 24);
      v11 = BCRYPT_RSAKEY_BLOB_From(*((_QWORD *)this + 12), v22 - (_QWORD)v21, v21, 0);
      v4 = v11;
      if ( v11 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x654,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
          (const char *)(unsigned int)v11,
          pbInput);
LABEL_16:
        v12 = &v21;
LABEL_17:
        std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v12);
        goto LABEL_26;
      }
      v13 = BCryptImportKeyPair(*v2, 0, L"RSAPUBLICBLOB", (BCRYPT_KEY_HANDLE *)this + 129, v21, v22 - (_DWORD)v21, 0);
      if ( v13 < 0 )
      {
        v4 = wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)0x65C,
               (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
               (const char *)(unsigned int)v13,
               pbInputa);
        goto LABEL_16;
      }
      v14 = &v21;
    }
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v14);
LABEL_25:
    v4 = 0;
    goto LABEL_26;
  }
  v4 = wil::details::in1diag3::Return_NtStatus(
         retaddr,
         (void *)0x63D,
         (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
         (const char *)(unsigned int)v3,
         pbInput);
LABEL_26:
  KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v25);
  return v4;
}

```

## disassembly

```asm
0x18002c5a8  push    rbp
0x18002c5aa  push    rbx
0x18002c5ab  push    rsi
0x18002c5ac  push    rdi
0x18002c5ad  push    r14
0x18002c5af  lea     rbp, [rsp-37h]
0x18002c5b4  sub     rsp, 90h
0x18002c5bb  mov     rdi, rcx
0x18002c5be  mov     r8b, 1; bool
0x18002c5c1  lea     rdx, aTpmkey20rsaOpe; "TpmKey20Rsa::OpenPubKeyHandle"
0x18002c5c8  lea     rcx, [rbp+57h+var_40]; this
0x18002c5cc  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x18002c5d1  nop
0x18002c5d2  lea     r14, [rdi+408h]
0x18002c5d9  cmp     qword ptr [r14], 0
0x18002c5dd  jnz     loc_18002C80E
0x18002c5e3  lea     rsi, [rdi+400h]
0x18002c5ea  cmp     qword ptr [rsi], 0
0x18002c5ee  jnz     short loc_18002C633
0x18002c5f0  xor     r9d, r9d; dwFlags
0x18002c5f3  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18002c5fa  lea     rdx, aRsa; "RSA"
0x18002c601  mov     rcx, rsi; phAlgorithm
0x18002c604  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18002c60b  nop     dword ptr [rax+rax+00h]
0x18002c610  test    eax, eax
0x18002c612  jns     short loc_18002C633
0x18002c614  mov     rcx, [rbp+5Fh]; this
0x18002c618  mov     r9d, eax; char *
0x18002c61b  lea     r8, aOnecoreBaseNgs_10; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18002c622  mov     edx, 63Dh; void *
0x18002c627  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002c62c  mov     ebx, eax
0x18002c62e  jmp     loc_18002C810
0x18002c633  mov     rdx, [rdi+288h]
0x18002c63a  test    rdx, rdx
0x18002c63d  jnz     loc_18002C77E
0x18002c643  mov     rbx, [rdi+60h]
0x18002c647  test    rbx, rbx
0x18002c64a  jnz     short loc_18002C66E
0x18002c64c  mov     rcx, [rbp+5Fh]; this
0x18002c650  mov     ebx, 80290402h
0x18002c655  mov     r9d, ebx; char *
0x18002c658  lea     r8, aOnecoreBaseNgs_10; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18002c65f  mov     edx, 647h; void *
0x18002c664  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c669  jmp     loc_18002C810
0x18002c66e  mov     r8b, 1; bool
0x18002c671  lea     rdx, aBcryptRsakeyBl; "BCRYPT_RSAKEY_BLOB_From"
0x18002c678  lea     rcx, [rbp+57h+var_58]; this
0x18002c67c  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x18002c681  mov     r8d, 3
0x18002c687  mov     r9d, [rbx+114h]
0x18002c68e  test    r9d, r9d
0x18002c691  jz      short loc_18002C6BA
0x18002c693  xor     edx, edx
0x18002c695  cmp     edx, 4
0x18002c698  jnb     short loc_18002C6BA
0x18002c69a  lea     ecx, ds:0[rdx*8]
0x18002c6a1  mov     eax, 0FF000000h
0x18002c6a6  shr     eax, cl
0x18002c6a8  test    r9d, eax
0x18002c6ab  jnz     short loc_18002C6B1
0x18002c6ad  inc     edx
0x18002c6af  jmp     short loc_18002C695
0x18002c6b1  mov     r8d, 4
0x18002c6b7  sub     r8d, edx
0x18002c6ba  movzx   ebx, word ptr [rbx+330h]
0x18002c6c1  mov     eax, r8d
0x18002c6c4  add     rbx, rax
0x18002c6c7  lea     rcx, [rbp+57h+var_58]; this
0x18002c6cb  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x18002c6d0  lea     rdx, [rbx+18h]
0x18002c6d4  lea     rcx, [rbp+57h+var_70]
0x18002c6d8  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@_KAEBU?$secure_allocator@E@wil@@@Z; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(unsigned __int64,wil::secure_allocator<uchar> const &)
0x18002c6dd  mov     r8, [rbp+57h+var_70]
0x18002c6e1  mov     rdx, [rbp+57h+var_68]
0x18002c6e5  sub     rdx, r8
0x18002c6e8  xor     r9d, r9d
0x18002c6eb  mov     rcx, [rdi+60h]
0x18002c6ef  call    BCRYPT_RSAKEY_BLOB_From
0x18002c6f4  mov     ebx, eax
0x18002c6f6  test    eax, eax
0x18002c6f8  jns     short loc_18002C720
0x18002c6fa  mov     rcx, [rbp+5Fh]; this
0x18002c6fe  mov     r9d, eax; char *
0x18002c701  lea     r8, aOnecoreBaseNgs_10; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18002c708  mov     edx, 654h; void *
0x18002c70d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c712  lea     rcx, [rbp+57h+var_70]
0x18002c716  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x18002c71b  jmp     loc_18002C810
0x18002c720  mov     rdx, [rbp+57h+var_70]
0x18002c724  mov     eax, dword ptr [rbp+57h+var_68]
0x18002c727  sub     eax, edx
0x18002c729  mov     [rsp+0B0h+dwFlags], 0; dwFlags
0x18002c731  mov     [rsp+0B0h+cbInput], eax; cbInput
0x18002c735  mov     [rsp+0B0h+pbInput], rdx; int
0x18002c73a  mov     r9, r14; phKey
0x18002c73d  lea     r8, aRsapublicblob; "RSAPUBLICBLOB"
0x18002c744  xor     edx, edx; hImportKey
0x18002c746  mov     rcx, [rsi]; hAlgorithm
0x18002c749  call    cs:__imp_BCryptImportKeyPair
0x18002c750  nop     dword ptr [rax+rax+00h]
0x18002c755  test    eax, eax
0x18002c757  jns     short loc_18002C775
0x18002c759  mov     rcx, [rbp+5Fh]; this
0x18002c75d  mov     r9d, eax; char *
0x18002c760  lea     r8, aOnecoreBaseNgs_10; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18002c767  mov     edx, 65Ch; void *
0x18002c76c  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002c771  mov     ebx, eax
0x18002c773  jmp     short loc_18002C712
0x18002c775  lea     rcx, [rbp+57h+var_70]
0x18002c779  jmp     loc_18002C809
0x18002c77e  mov     ecx, [rdx+0Ch]
0x18002c781  mov     r8d, [rdx+8]
0x18002c785  add     ecx, 18h
0x18002c788  add     r8d, ecx
0x18002c78b  add     r8, rdx
0x18002c78e  lea     rcx, [rbp+57h+var_58]
0x18002c792  call    ??$?0PEAE$0A@@?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@PEAE0AEBU?$secure_allocator@E@wil@@@Z; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(uchar *,uchar *,wil::secure_allocator<uchar> const &)
0x18002c797  mov     rax, [rbp+57h+var_58]
0x18002c79b  mov     dword ptr [rax], 31415352h
0x18002c7a1  mov     qword ptr [rax+10h], 0
0x18002c7a9  mov     rcx, [rbp+57h+var_58]
0x18002c7ad  mov     eax, [rbp+57h+var_50]
0x18002c7b0  sub     eax, ecx
0x18002c7b2  mov     [rsp+0B0h+dwFlags], 0; dwFlags
0x18002c7ba  mov     [rsp+0B0h+cbInput], eax; cbInput
0x18002c7be  mov     [rsp+0B0h+pbInput], rcx; int
0x18002c7c3  mov     r9, r14; phKey
0x18002c7c6  lea     r8, aRsapublicblob; "RSAPUBLICBLOB"
0x18002c7cd  xor     edx, edx; hImportKey
0x18002c7cf  mov     rcx, [rsi]; hAlgorithm
0x18002c7d2  call    cs:__imp_BCryptImportKeyPair
0x18002c7d9  nop     dword ptr [rax+rax+00h]
0x18002c7de  test    eax, eax
0x18002c7e0  jns     short loc_18002C805
0x18002c7e2  mov     rcx, [rbp+5Fh]; this
0x18002c7e6  mov     r9d, eax; char *
0x18002c7e9  lea     r8, aOnecoreBaseNgs_10; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18002c7f0  mov     edx, 671h; void *
0x18002c7f5  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002c7fa  mov     ebx, eax
0x18002c7fc  lea     rcx, [rbp+57h+var_58]
0x18002c800  jmp     loc_18002C716
0x18002c805  lea     rcx, [rbp+57h+var_58]
0x18002c809  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x18002c80e  xor     ebx, ebx
0x18002c810  lea     rcx, [rbp+57h+var_40]; this
0x18002c814  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x18002c819  mov     eax, ebx
0x18002c81b  add     rsp, 90h
0x18002c822  pop     r14
0x18002c824  pop     rdi
0x18002c825  pop     rsi
0x18002c826  pop     rbx
0x18002c827  pop     rbp
0x18002c828  retn
```
