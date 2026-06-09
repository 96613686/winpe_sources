# GetSha256HashString(uchar *,ulong,ushort * *)

- ea: `0x18008fd88`
- end: `0x18008ff65`
- name: `?GetSha256HashString@@YAJPEAEKPEAPEAG@Z`
- size: `477`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18008f6b0`

## callees

- `0x18000b9e0`
- `0x18000be80`
- `0x18000bf40`
- `0x18000c8f4`
- `0x180011fe0`
- `0x18005fca8`
- `0x18008fd88`
- `0x18009ac0c`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18008fe1b`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18008fe1b`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18008ff3c`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18008ff3c`
- `bcrypt!BCryptHashData` at `0x18008fe74`
- `bcrypt!BCryptHashData` at `0x18008fe74`
- `bcrypt!BCryptDestroyHash` at `0x18008ff21`
- `bcrypt!BCryptDestroyHash` at `0x18008ff21`
- `bcrypt!BCryptCreateHash` at `0x18008fe5a`
- `bcrypt!BCryptCreateHash` at `0x18008fe5a`
- `bcrypt!BCryptFinishHash` at `0x18008fe9d`
- `bcrypt!BCryptFinishHash` at `0x18008fe9d`

## pseudocode

```c
__int64 __fastcall GetSha256HashString(PUCHAR pbInput, ULONG cbInput, unsigned __int16 **a3)
{
  NTSTATUS v7; // eax
  unsigned __int16 *v8; // rsi
  NTSTATUS v9; // eax
  int v10; // ebx
  __int64 i; // rdi
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-C0h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-B8h] BYREF
  UCHAR pbOutput[16]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v15; // [rsp+60h] [rbp-A0h]
  unsigned __int16 v16[72]; // [rsp+70h] [rbp-90h] BYREF

  phAlgorithm = 0;
  phHash = 0;
  *(_OWORD *)pbOutput = 0;
  v15 = 0;
  memset_0(v16, 0, 0x82u);
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  if ( !pbInput || !cbInput )
    return 2147942487LL;
  v7 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0);
  if ( v7 < 0 )
    return DCHRESULTFromNTSTATUS((unsigned int)v7);
  v7 = BCryptCreateHash(phAlgorithm, &phHash, 0, 0, 0, 0, 0);
  if ( v7 < 0 )
    return DCHRESULTFromNTSTATUS((unsigned int)v7);
  v8 = 0;
  v9 = BCryptHashData(phHash, pbInput, cbInput, 0);
  if ( v9 < 0 || (v9 = BCryptFinishHash(phHash, pbOutput, 0x20u, 0), v9 < 0) )
  {
    v10 = DCHRESULTFromNTSTATUS((unsigned int)v9);
  }
  else
  {
    for ( i = 0; (unsigned int)i < 0x20 && (unsigned int)(2 * i) < 0x41; i = (unsigned int)(i + 1) )
    {
      v10 = StringCchPrintfW(&v16[(unsigned int)(2 * i)], 65LL - (unsigned int)(2 * i), L"%02X", pbOutput[i]);
      if ( v10 < 0 )
        goto LABEL_18;
    }
    v8 = (unsigned __int16 *)operator new[](0x104u);
    v10 = StringCbCopyW(v8, 0x82u, v16);
    if ( v10 >= 0 )
    {
      *a3 = v8;
      v8 = 0;
    }
  }
LABEL_18:
  operator delete(v8);
  if ( phHash )
  {
    BCryptDestroyHash(phHash);
    phHash = 0;
  }
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18008fd88  push    rbp
0x18008fd8a  push    rbx
0x18008fd8b  push    rsi
0x18008fd8c  push    rdi
0x18008fd8d  push    r14
0x18008fd8f  lea     rbp, [rsp-10h]
0x18008fd94  sub     rsp, 110h
0x18008fd9b  mov     rax, cs:__security_cookie
0x18008fda2  xor     rax, rsp
0x18008fda5  mov     [rbp+30h+var_30], rax
0x18008fda9  xorps   xmm0, xmm0
0x18008fdac  mov     [rsp+130h+phAlgorithm], 0
0x18008fdb5  mov     r14, r8
0x18008fdb8  mov     [rsp+130h+phHash], 0
0x18008fdc1  mov     edi, edx
0x18008fdc3  mov     rbx, rcx
0x18008fdc6  xor     edx, edx; Val
0x18008fdc8  lea     rcx, [rsp+130h+var_C0]; void *
0x18008fdcd  mov     r8d, 82h; Size
0x18008fdd3  movups  xmmword ptr [rsp+130h+pbOutput], xmm0
0x18008fdd8  movups  [rsp+130h+var_D0], xmm0
0x18008fddd  call    memset_0
0x18008fde2  test    r14, r14
0x18008fde5  jnz     short loc_18008FDF1
0x18008fde7  mov     eax, 80004003h
0x18008fdec  jmp     loc_18008FF4B
0x18008fdf1  mov     qword ptr [r14], 0
0x18008fdf8  test    rbx, rbx
0x18008fdfb  jz      loc_18008FF46
0x18008fe01  test    edi, edi
0x18008fe03  jz      loc_18008FF46
0x18008fe09  xor     r9d, r9d; dwFlags
0x18008fe0c  lea     rdx, pszAlgId; "SHA256"
0x18008fe13  xor     r8d, r8d; pszImplementation
0x18008fe16  lea     rcx, [rsp+130h+phAlgorithm]; phAlgorithm
0x18008fe1b  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18008fe21  test    eax, eax
0x18008fe23  jns     short loc_18008FE31
0x18008fe25  mov     ecx, eax
0x18008fe27  call    DCHRESULTFromNTSTATUS
0x18008fe2c  jmp     loc_18008FF4B
0x18008fe31  mov     rcx, [rsp+130h+phAlgorithm]; hAlgorithm
0x18008fe36  lea     rdx, [rsp+130h+phHash]; phHash
0x18008fe3b  mov     [rsp+130h+dwFlags], 0; dwFlags
0x18008fe43  xor     r9d, r9d; cbHashObject
0x18008fe46  mov     [rsp+130h+cbSecret], 0; cbSecret
0x18008fe4e  xor     r8d, r8d; pbHashObject
0x18008fe51  mov     [rsp+130h+pbSecret], 0; pbSecret
0x18008fe5a  call    cs:__imp_BCryptCreateHash
0x18008fe60  test    eax, eax
0x18008fe62  js      short loc_18008FE25
0x18008fe64  mov     rcx, [rsp+130h+phHash]; hHash
0x18008fe69  xor     r9d, r9d; dwFlags
0x18008fe6c  mov     r8d, edi; cbInput
0x18008fe6f  mov     rdx, rbx; pbInput
0x18008fe72  xor     esi, esi
0x18008fe74  call    cs:__imp_BCryptHashData
0x18008fe7a  test    eax, eax
0x18008fe7c  jns     short loc_18008FE8C
0x18008fe7e  mov     ecx, eax
0x18008fe80  call    DCHRESULTFromNTSTATUS
0x18008fe85  mov     ebx, eax
0x18008fe87  jmp     loc_18008FF0F
0x18008fe8c  mov     rcx, [rsp+130h+phHash]; hHash
0x18008fe91  lea     rdx, [rsp+130h+pbOutput]; pbOutput
0x18008fe96  xor     r9d, r9d; dwFlags
0x18008fe99  lea     r8d, [r9+20h]; cbOutput
0x18008fe9d  call    cs:__imp_BCryptFinishHash
0x18008fea3  test    eax, eax
0x18008fea5  js      short loc_18008FE7E
0x18008fea7  xor     edi, edi
0x18008fea9  cmp     edi, 20h ; ' '
0x18008feac  jnb     short loc_18008FEE5
0x18008feae  lea     eax, [rdi+rdi]
0x18008feb1  cmp     eax, 41h ; 'A'
0x18008feb4  jnb     short loc_18008FEE5
0x18008feb6  movzx   r9d, [rsp+rdi+130h+pbOutput]
0x18008febc  lea     r8, a02x; "%02X"
0x18008fec3  mov     ecx, eax
0x18008fec5  mov     edx, 41h ; 'A'
0x18008feca  lea     rax, [rsp+130h+var_C0]
0x18008fecf  sub     rdx, rcx; unsigned __int64
0x18008fed2  lea     rcx, [rax+rcx*2]; unsigned __int16 *
0x18008fed6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18008fedb  mov     ebx, eax
0x18008fedd  test    eax, eax
0x18008fedf  js      short loc_18008FF0F
0x18008fee1  inc     edi
0x18008fee3  jmp     short loc_18008FEA9
0x18008fee5  mov     ecx, 104h; unsigned __int64
0x18008feea  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18008feef  lea     r8, [rsp+130h+var_C0]; unsigned __int16 *
0x18008fef4  mov     edx, 82h; unsigned __int64
0x18008fef9  mov     rcx, rax; unsigned __int16 *
0x18008fefc  mov     rsi, rax
0x18008feff  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18008ff04  mov     ebx, eax
0x18008ff06  test    eax, eax
0x18008ff08  js      short loc_18008FF0F
0x18008ff0a  mov     [r14], rsi
0x18008ff0d  xor     esi, esi
0x18008ff0f  mov     rcx, rsi; Block
0x18008ff12  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008ff17  mov     rcx, [rsp+130h+phHash]; hHash
0x18008ff1c  test    rcx, rcx
0x18008ff1f  jz      short loc_18008FF30
0x18008ff21  call    cs:__imp_BCryptDestroyHash
0x18008ff27  mov     [rsp+130h+phHash], 0
0x18008ff30  mov     rcx, [rsp+130h+phAlgorithm]; hAlgorithm
0x18008ff35  test    rcx, rcx
0x18008ff38  jz      short loc_18008FF42
0x18008ff3a  xor     edx, edx; dwFlags
0x18008ff3c  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18008ff42  mov     eax, ebx
0x18008ff44  jmp     short loc_18008FF4B
0x18008ff46  mov     eax, 80070057h
0x18008ff4b  mov     rcx, [rbp+30h+var_30]
0x18008ff4f  xor     rcx, rsp; StackCookie
0x18008ff52  call    __security_check_cookie
0x18008ff57  add     rsp, 110h
0x18008ff5e  pop     r14
0x18008ff60  pop     rdi
0x18008ff61  pop     rsi
0x18008ff62  pop     rbx
0x18008ff63  pop     rbp
0x18008ff64  retn
```
