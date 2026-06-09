# TpmKey20Ecdsa::ImportKey(TpmKey *,ushort const *,uchar const *,uint,uint)

- ea: `0x18008fa70`
- end: `0x18008fcb5`
- name: `?ImportKey@TpmKey20Ecdsa@@UEAAJPEAVTpmKey@@PEBGPEBEII@Z`
- size: `581`
- prototype: `__int64 __usercall@<rax>(TpmKey20Ecdsa *__hidden this@<rcx>, struct TpmKey *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int8 *@<r9>, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18005c2c0`

## callees

- `0x18000dc90`
- `0x1800133c4`
- `0x180014a60`
- `0x1800157c0`
- `0x180061bac`
- `0x18008e850`
- `0x18008fa70`
- `0x1800c2ce0`

## import_xrefs

- `bcrypt!BCryptImportKeyPair` at `0x18008fc62`
- `bcrypt!BCryptImportKeyPair` at `0x18008fc62`
- `bcrypt!BCryptDestroyKey` at `0x18008fc24`
- `bcrypt!BCryptDestroyKey` at `0x18008fc24`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18008fbe5`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18008fbe5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TpmKey20Ecdsa::ImportKey(
        BCRYPT_ALG_HANDLE *this,
        struct TpmKey *a2,
        const unsigned __int16 *a3,
        unsigned __int8 *a4,
        ULONG cbInput,
        unsigned int a6)
{
  unsigned int v9; // ebx
  __int64 v10; // rdx
  int v11; // eax
  unsigned __int64 v12; // r9
  int KeyInTpm; // eax
  NTSTATUS v14; // eax
  __int64 v15; // rdx
  BCRYPT_ALG_HANDLE v16; // rcx
  PUCHAR pbInput; // [rsp+20h] [rbp-68h]
  int *v19[9]; // [rsp+40h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v19, L"TpmKey20Ecdsa::ImportKey", 1);
  if ( (a6 & 0xFFFFEFF7) != 0 )
  {
    v9 = -2144795644;
    v10 = 312;
LABEL_28:
    v12 = v9;
    goto LABEL_29;
  }
  if ( wcscmp_0(a3, L"ECCPUBLICBLOB") && wcscmp_0(a3, L"ECCFULLPUBLICBLOB") )
  {
    if ( wcscmp_0(a3, L"OpaqueKeyBlob")
      && wcscmp_0(a3, L"PcpTpmProtectedKeyBlob")
      && wcscmp_0(a3, L"ECCFULLPRIVATEBLOB")
      && wcscmp_0(a3, L"ECCPRIVATEBLOB")
      && wcscmp_0(a3, L"PcpTpmPersistentKeyBlob") )
    {
      v9 = -2144795643;
      v10 = 368;
      goto LABEL_28;
    }
    LODWORD(pbInput) = cbInput;
    v11 = TpmKey20Ecc::ImportKey((TpmKey20Ecc *)this, 0, a3, a4, (rsize_t)pbInput, a6);
    v9 = v11;
    if ( v11 < 0 )
    {
      v12 = (unsigned int)v11;
      v10 = 358;
LABEL_29:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20ecdsa.cpp",
        (const char *)v12,
        (int)pbInput);
      goto LABEL_30;
    }
    if ( (a6 & 8) == 0 )
    {
      KeyInTpm = TpmKey20::LoadKeyInTpm((TpmKey20 *)this);
      v9 = KeyInTpm;
      if ( KeyInTpm < 0 )
      {
        v12 = (unsigned int)KeyInTpm;
        v10 = 363;
        goto LABEL_29;
      }
    }
    goto LABEL_26;
  }
  if ( *((_DWORD *)this + 116) || this[12] )
  {
    v9 = -2144795628;
    v10 = 320;
    goto LABEL_28;
  }
  if ( this[129]
    || (v14 = BCryptOpenAlgorithmProvider(this + 129, L"ECDSA", L"Microsoft Primitive Provider", 0), v14 >= 0) )
  {
    v16 = this[130];
    if ( v16 )
    {
      BCryptDestroyKey(v16);
      this[130] = 0;
    }
    v14 = BCryptImportKeyPair(this[129], 0, a3, this + 130, a4, cbInput, 0);
    if ( v14 >= 0 )
    {
LABEL_26:
      v9 = 0;
      goto LABEL_30;
    }
    v15 = 346;
  }
  else
  {
    v15 = 328;
  }
  v9 = wil::details::in1diag3::Return_NtStatus(
         retaddr,
         (void *)v15,
         (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20ecdsa.cpp",
         (const char *)(unsigned int)v14,
         (int)pbInput);
LABEL_30:
  KspFunctionLogger::~KspFunctionLogger(v19);
  return v9;
}

```

## disassembly

```asm
0x18008fa70  push    rbx
0x18008fa72  push    rbp
0x18008fa73  push    rsi
0x18008fa74  push    rdi
0x18008fa75  sub     rsp, 68h
0x18008fa79  mov     rbp, r9
0x18008fa7c  mov     rbx, r8
0x18008fa7f  mov     rdi, rcx
0x18008fa82  mov     r8b, 1; bool
0x18008fa85  lea     rdx, aTpmkey20ecdsaI; "TpmKey20Ecdsa::ImportKey"
0x18008fa8c  lea     rcx, [rsp+88h+var_48]; this
0x18008fa91  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x18008fa96  nop
0x18008fa97  mov     esi, [rsp+88h+arg_28]
0x18008fa9e  test    esi, 0FFFFEFF7h
0x18008faa4  jz      short loc_18008FAB5
0x18008faa6  mov     ebx, 80290404h
0x18008faab  mov     edx, 138h
0x18008fab0  jmp     loc_18008FC87
0x18008fab5  lea     rdx, aEccpublicblob; "ECCPUBLICBLOB"
0x18008fabc  mov     rcx, rbx; String1
0x18008fabf  call    wcscmp_0
0x18008fac4  test    eax, eax
0x18008fac6  jz      loc_18008FBAC
0x18008facc  lea     rdx, aEccfullpublicb; "ECCFULLPUBLICBLOB"
0x18008fad3  mov     rcx, rbx; String1
0x18008fad6  call    wcscmp_0
0x18008fadb  test    eax, eax
0x18008fadd  jz      loc_18008FBAC
0x18008fae3  lea     rdx, aOpaquekeyblob; "OpaqueKeyBlob"
0x18008faea  mov     rcx, rbx; String1
0x18008faed  call    wcscmp_0
0x18008faf2  test    eax, eax
0x18008faf4  jz      short loc_18008FB51
0x18008faf6  lea     rdx, aPcptpmprotecte; "PcpTpmProtectedKeyBlob"
0x18008fafd  mov     rcx, rbx; String1
0x18008fb00  call    wcscmp_0
0x18008fb05  test    eax, eax
0x18008fb07  jz      short loc_18008FB51
0x18008fb09  lea     rdx, aEccfullprivate; "ECCFULLPRIVATEBLOB"
0x18008fb10  mov     rcx, rbx; String1
0x18008fb13  call    wcscmp_0
0x18008fb18  test    eax, eax
0x18008fb1a  jz      short loc_18008FB51
0x18008fb1c  lea     rdx, aEccprivateblob; "ECCPRIVATEBLOB"
0x18008fb23  mov     rcx, rbx; String1
0x18008fb26  call    wcscmp_0
0x18008fb2b  test    eax, eax
0x18008fb2d  jz      short loc_18008FB51
0x18008fb2f  lea     rdx, aPcptpmpersiste; "PcpTpmPersistentKeyBlob"
0x18008fb36  mov     rcx, rbx; String1
0x18008fb39  call    wcscmp_0
0x18008fb3e  test    eax, eax
0x18008fb40  jz      short loc_18008FB51
0x18008fb42  mov     ebx, 80290405h
0x18008fb47  mov     edx, 170h
0x18008fb4c  jmp     loc_18008FC87
0x18008fb51  mov     [rsp+88h+cbInput], esi; unsigned int
0x18008fb55  mov     eax, [rsp+88h+arg_20]
0x18008fb5c  mov     dword ptr [rsp+88h+pbInput], eax; DestinationSize
0x18008fb60  mov     r9, rbp; unsigned __int8 *
0x18008fb63  mov     r8, rbx; unsigned __int16 *
0x18008fb66  xor     edx, edx; struct TpmKey *
0x18008fb68  mov     rcx, rdi; this
0x18008fb6b  call    ?ImportKey@TpmKey20Ecc@@UEAAJPEAVTpmKey@@PEBGPEBEII@Z; TpmKey20Ecc::ImportKey(TpmKey *,ushort const *,uchar const *,uint,uint)
0x18008fb70  mov     ebx, eax
0x18008fb72  test    eax, eax
0x18008fb74  jns     short loc_18008FB83
0x18008fb76  mov     r9d, eax
0x18008fb79  mov     edx, 166h
0x18008fb7e  jmp     loc_18008FC8A
0x18008fb83  test    sil, 8
0x18008fb87  jnz     loc_18008FC79
0x18008fb8d  mov     rcx, rdi; this
0x18008fb90  call    ?LoadKeyInTpm@TpmKey20@@IEAAJXZ; TpmKey20::LoadKeyInTpm(void)
0x18008fb95  mov     ebx, eax
0x18008fb97  test    eax, eax
0x18008fb99  jns     loc_18008FC79
0x18008fb9f  mov     r9d, eax
0x18008fba2  mov     edx, 16Bh
0x18008fba7  jmp     loc_18008FC8A
0x18008fbac  cmp     dword ptr [rdi+1D0h], 0
0x18008fbb3  jnz     loc_18008FC7D
0x18008fbb9  cmp     qword ptr [rdi+60h], 0
0x18008fbbe  jnz     loc_18008FC7D
0x18008fbc4  lea     rsi, [rdi+408h]
0x18008fbcb  cmp     qword ptr [rsi], 0
0x18008fbcf  jnz     short loc_18008FC18
0x18008fbd1  xor     r9d, r9d; dwFlags
0x18008fbd4  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18008fbdb  lea     rdx, aEcdsa; "ECDSA"
0x18008fbe2  mov     rcx, rsi; phAlgorithm
0x18008fbe5  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18008fbec  nop     dword ptr [rax+rax+00h]
0x18008fbf1  test    eax, eax
0x18008fbf3  jns     short loc_18008FC18
0x18008fbf5  mov     edx, 148h; void *
0x18008fbfa  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18008fc01  mov     r9d, eax; char *
0x18008fc04  mov     rcx, [rsp+88h]; this
0x18008fc0c  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18008fc11  mov     ebx, eax
0x18008fc13  jmp     loc_18008FC9F
0x18008fc18  mov     rcx, [rdi+410h]; hKey
0x18008fc1f  test    rcx, rcx
0x18008fc22  jz      short loc_18008FC3B
0x18008fc24  call    cs:__imp_BCryptDestroyKey
0x18008fc2b  nop     dword ptr [rax+rax+00h]
0x18008fc30  mov     qword ptr [rdi+410h], 0
0x18008fc3b  mov     [rsp+88h+dwFlags], 0; dwFlags
0x18008fc43  mov     eax, [rsp+88h+arg_20]
0x18008fc4a  mov     [rsp+88h+cbInput], eax; cbInput
0x18008fc4e  mov     [rsp+88h+pbInput], rbp; pbInput
0x18008fc53  lea     r9, [rdi+410h]; phKey
0x18008fc5a  mov     r8, rbx; pszBlobType
0x18008fc5d  xor     edx, edx; hImportKey
0x18008fc5f  mov     rcx, [rsi]; hAlgorithm
0x18008fc62  call    cs:__imp_BCryptImportKeyPair
0x18008fc69  nop     dword ptr [rax+rax+00h]
0x18008fc6e  test    eax, eax
0x18008fc70  jns     short loc_18008FC79
0x18008fc72  mov     edx, 15Ah
0x18008fc77  jmp     short loc_18008FBFA
0x18008fc79  xor     ebx, ebx
0x18008fc7b  jmp     short loc_18008FC9F
0x18008fc7d  mov     ebx, 80290414h
0x18008fc82  mov     edx, 140h; void *
0x18008fc87  mov     r9d, ebx; char *
0x18008fc8a  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18008fc91  mov     rcx, [rsp+88h]; this
0x18008fc99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008fc9e  nop
0x18008fc9f  lea     rcx, [rsp+88h+var_48]; this
0x18008fca4  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x18008fca9  mov     eax, ebx
0x18008fcab  add     rsp, 68h
0x18008fcaf  pop     rdi
0x18008fcb0  pop     rsi
0x18008fcb1  pop     rbp
0x18008fcb2  pop     rbx
0x18008fcb3  retn
```
