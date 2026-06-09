# LsapDecryptUnicodeStringAes

- ea: `0x1800641ec`
- end: `0x18006458d`
- name: `LsapDecryptUnicodeStringAes`
- size: `929`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800630a0`

## callees

- `0x180063a84`
- `0x180063f38`
- `0x18006412c`
- `0x1800641ec`
- `0x1800649c4`
- `0x180065036`
- `0x180065042`
- `0x180065090`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x180064480`
- `KERNELBASE!LocalAlloc` at `0x180064480`
- `KERNEL32!LocalFree` at `0x1800644ed`
- `KERNEL32!LocalFree` at `0x180064512`
- `KERNEL32!LocalFree` at `0x18006451c`
- `KERNEL32!LocalFree` at `0x180064526`
- `KERNEL32!LocalFree` at `0x18006454c`
- `KERNEL32!LocalFree` at `0x1800644ed`
- `KERNEL32!LocalFree` at `0x180064512`
- `KERNEL32!LocalFree` at `0x18006451c`
- `KERNEL32!LocalFree` at `0x180064526`
- `KERNEL32!LocalFree` at `0x18006454c`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18006455e`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18006455e`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800642d8`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800642d8`

## pseudocode

```c
__int64 __fastcall LsapDecryptUnicodeStringAes(__int64 a1, __int64 a2, __int64 a3, __int64 a4, _QWORD *a5)
{
  PUCHAR v6; // r15
  _BYTE *v7; // rsi
  ULONG v8; // r13d
  unsigned int v9; // r12d
  __int64 v10; // rdi
  NTSTATUS HMACWithSHA512; // ebx
  __int64 v12; // rdx
  int v13; // eax
  int v14; // eax
  int v15; // eax
  size_t v16; // r13
  _WORD *v17; // rax
  _WORD *v18; // r14
  __int64 v19; // rcx
  _BYTE *v20; // rax
  __int64 v21; // rdx
  PUCHAR v22; // rax
  __int64 v23; // rax
  _BYTE *v24; // rcx
  ULONG cbSecret; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v27; // [rsp+44h] [rbp-BCh] BYREF
  ULONG cbInput; // [rsp+4Ch] [rbp-B4h] BYREF
  size_t Size; // [rsp+50h] [rbp-B0h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v31; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v32; // [rsp+68h] [rbp-98h] BYREF
  __int64 v33; // [rsp+70h] [rbp-90h]
  PUCHAR pbSecret; // [rsp+78h] [rbp-88h] BYREF
  void *Buf1; // [rsp+80h] [rbp-80h] BYREF
  HLOCAL hMem; // [rsp+88h] [rbp-78h] BYREF
  _QWORD *v37; // [rsp+90h] [rbp-70h]
  _OWORD v38[2]; // [rsp+98h] [rbp-68h] BYREF
  char v39[24]; // [rsp+B8h] [rbp-48h] BYREF
  char v40[64]; // [rsp+D0h] [rbp-30h] BYREF

  v33 = a1;
  strcpy(v40, "Microsoft LSAD encryption key AEAD-AES-256-CBC-HMAC-SHA512 16");
  v6 = 0;
  pbSecret = 0;
  v7 = 0;
  v32 = 0;
  v8 = 0;
  cbSecret = 0;
  v9 = 0;
  Buf1 = 0;
  v10 = 0;
  LODWORD(Size) = 0;
  hMem = 0;
  cbInput = 0;
  qmemcpy(v38, "Microsoft LSAD MAC key AEAD-AES-", sizeof(v38));
  v27 = 0;
  v31 = 0;
  phAlgorithm = 0;
  *a5 = 0;
  strcpy(v39, "256-CBC-HMAC-SHA512 16");
  v37 = a5;
  HMACWithSHA512 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA512", 0, 8u);
  if ( HMACWithSHA512 >= 0 )
  {
    HMACWithSHA512 = LsapCrGenerateHMACWithSHA512(phAlgorithm, 0x37u, (__int64)&v32, (__int64)&v27 + 4);
    if ( HMACWithSHA512 < 0 )
    {
      v7 = (_BYTE *)v32;
    }
    else
    {
      v13 = LsapCrPrepareDataForHMACSignature(
              a3 + 64,
              v12,
              *(_QWORD *)(a3 + 88),
              *(unsigned int *)(a3 + 80),
              &hMem,
              &cbInput);
      v7 = (_BYTE *)v32;
      HMACWithSHA512 = v13;
      if ( v13 >= 0 )
      {
        HMACWithSHA512 = LsapCrGenerateHMACWithSHA512(phAlgorithm, cbInput, (__int64)&Buf1, (__int64)&Size);
        if ( HMACWithSHA512 >= 0 )
        {
          if ( memcmp_0(Buf1, (const void *)a3, (unsigned int)Size) )
          {
LABEL_6:
            HMACWithSHA512 = -1073741811;
            goto LABEL_17;
          }
          v14 = LsapCrGenerateHMACWithSHA512(phAlgorithm, 0x3Eu, (__int64)&pbSecret, (__int64)&cbSecret);
          v8 = cbSecret;
          HMACWithSHA512 = v14;
          v6 = pbSecret;
          if ( v14 >= 0 )
          {
            v15 = LsapCrDecryptDataWithAES(
                    *(PUCHAR *)(a3 + 88),
                    *(_DWORD *)(a3 + 80),
                    (PUCHAR)(a3 + 64),
                    pbSecret,
                    cbSecret,
                    (__int64)&v31,
                    (__int64)&v27);
            v9 = v27;
            HMACWithSHA512 = v15;
            v10 = v31;
            if ( v15 >= 0 )
            {
              if ( (unsigned int)v27 < 4 )
                goto LABEL_6;
              v16 = *(unsigned __int16 *)v31;
              if ( (_DWORD)v27 == (_DWORD)v16 + 4 )
              {
                v33 = *(unsigned __int16 *)(v31 + 2);
                v17 = LocalAlloc(0x40u, v33 + 16);
                v18 = v17;
                if ( v17 )
                {
                  *v17 = v16;
                  HMACWithSHA512 = 0;
                  v17[1] = v33;
                  *((_QWORD *)v17 + 1) = v17 + 8;
                  memcpy_0(v17 + 8, (const void *)(v10 + 4), v16);
                  *v37 = v18;
                }
                else
                {
                  HMACWithSHA512 = -1073741801;
                }
              }
              else
              {
                HMACWithSHA512 = -1073741811;
              }
              v8 = cbSecret;
            }
          }
        }
      }
    }
  }
LABEL_17:
  LsapFreeAesClearValue(0);
  if ( v10 )
  {
    v19 = v9;
    v20 = (_BYTE *)v10;
    if ( v9 )
    {
      do
      {
        *v20++ = 0;
        --v19;
      }
      while ( v19 );
    }
    LocalFree((HLOCAL)v10);
  }
  if ( v6 )
  {
    v21 = v8;
    v22 = v6;
    if ( v8 )
    {
      do
      {
        *v22++ = 0;
        --v21;
      }
      while ( v21 );
    }
    LocalFree(v6);
  }
  LocalFree(Buf1);
  LocalFree(hMem);
  if ( v7 )
  {
    v23 = HIDWORD(v27);
    v24 = v7;
    if ( HIDWORD(v27) )
    {
      do
      {
        *v24++ = 0;
        --v23;
      }
      while ( v23 );
    }
    LocalFree(v7);
  }
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return (unsigned int)HMACWithSHA512;
}

```

## disassembly

```asm
0x1800641ec  mov     [rsp-8+arg_8], rbx
0x1800641f1  push    rbp
0x1800641f2  push    rsi
0x1800641f3  push    rdi
0x1800641f4  push    r12
0x1800641f6  push    r13
0x1800641f8  push    r14
0x1800641fa  push    r15
0x1800641fc  lea     rbp, [rsp-20h]
0x180064201  sub     rsp, 120h
0x180064208  mov     rax, cs:__security_cookie
0x18006420f  xor     rax, rsp
0x180064212  mov     [rbp+50h+var_40], rax
0x180064216  movups  xmm0, xmmword ptr cs:aMicrosoftLsadE; "Microsoft LSAD encryption key AEAD-AES-"...
0x18006421d  mov     rax, [rbp+50h+arg_20]
0x180064224  mov     r14, r8
0x180064227  movups  xmm1, xmmword ptr cs:aMicrosoftLsadE+10h; "ncryption key AEAD-AES-256-CBC-HMAC-SHA"...
0x18006422e  mov     [rsp+150h+var_E0], rcx
0x180064233  xor     ecx, ecx
0x180064235  movups  xmmword ptr [rbp+50h+var_80], xmm0
0x180064239  mov     r15d, ecx
0x18006423c  mov     [rsp+150h+var_D8], rcx
0x180064241  movups  xmm0, xmmword ptr cs:aMicrosoftLsadE+20h; "AD-AES-256-CBC-HMAC-SHA512 16"
0x180064248  mov     esi, ecx
0x18006424a  mov     [rsp+150h+var_E8], rcx
0x18006424f  movups  xmmword ptr [rbp+50h+var_80+10h], xmm1
0x180064253  mov     r13d, ecx
0x180064256  mov     [rsp+150h+var_110], ecx
0x18006425a  movups  xmm1, xmmword ptr cs:aMicrosoftLsadE+2Eh; "-HMAC-SHA512 16"
0x180064261  mov     dword ptr [rsp+150h+var_10C+4], ecx
0x180064265  mov     r12d, ecx
0x180064268  movups  xmmword ptr [rbp+50h+var_80+20h], xmm0
0x18006426c  mov     [rbp+50h+Buf1], rcx
0x180064270  mov     edi, ecx
0x180064272  movups  xmm0, xmmword ptr cs:aMicrosoftLsadM; "Microsoft LSAD MAC key AEAD-AES-256-CBC"...
0x180064279  mov     dword ptr [rsp+150h+Size], ecx
0x18006427d  lea     r9d, [rcx+8]; dwFlags
0x180064281  movups  xmmword ptr [rbp+50h+var_80+2Eh], xmm1
0x180064285  mov     [rbp+50h+hMem], rcx
0x180064289  xor     r8d, r8d; pszImplementation
0x18006428c  movups  xmm1, xmmword ptr cs:aMicrosoftLsadM+10h; "AC key AEAD-AES-256-CBC-HMAC-SHA512 16"
0x180064293  mov     [rsp+150h+cbInput], ecx
0x180064297  lea     rdx, pszAlgId; "SHA512"
0x18006429e  movups  [rbp+50h+var_B8], xmm0
0x1800642a2  mov     dword ptr [rsp+150h+var_10C], ecx
0x1800642a6  movups  xmm0, xmmword ptr cs:aMicrosoftLsadM+20h; "256-CBC-HMAC-SHA512 16"
0x1800642ad  mov     [rsp+150h+var_F0], rcx
0x1800642b2  movups  [rbp+50h+var_A8], xmm1
0x1800642b6  mov     [rsp+150h+phAlgorithm], rcx
0x1800642bb  movsd   xmm1, qword ptr cs:aMicrosoftLsadM+2Fh; "A512 16"
0x1800642c3  mov     [rax], rcx
0x1800642c6  lea     rcx, [rsp+150h+phAlgorithm]; phAlgorithm
0x1800642cb  movups  xmmword ptr [rbp+50h+var_98], xmm0
0x1800642cf  mov     [rbp+50h+var_C0], rax
0x1800642d3  movsd   qword ptr [rbp+50h+var_98+0Fh], xmm1
0x1800642d8  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800642de  mov     ebx, eax
0x1800642e0  test    eax, eax
0x1800642e2  js      loc_1800644C7
0x1800642e8  mov     rdx, [rsp+150h+var_E0]
0x1800642ed  lea     rax, [rsp+150h+var_10C+4]
0x1800642f2  mov     rcx, [rsp+150h+phAlgorithm]; hAlgorithm
0x1800642f7  lea     r9, [rbp+50h+var_B8]
0x1800642fb  mov     [rsp+150h+var_120], rax; __int64
0x180064300  lea     r8d, [rdi+10h]
0x180064304  lea     rax, [rsp+150h+var_E8]
0x180064309  mov     qword ptr [rsp+150h+cbSecret], rax; __int64
0x18006430e  mov     dword ptr [rsp+150h+pbSecret], 37h ; '7'; cbInput
0x180064316  call    LsapCrGenerateHMACWithSHA512
0x18006431b  mov     ebx, eax
0x18006431d  test    eax, eax
0x18006431f  js      loc_1800644C2
0x180064325  mov     r9d, [r14+50h]
0x180064329  lea     rcx, [rsp+150h+cbInput]
0x18006432e  mov     r8, [r14+58h]
0x180064332  mov     qword ptr [rsp+150h+cbSecret], rcx
0x180064337  lea     rcx, [rbp+50h+hMem]
0x18006433b  mov     [rsp+150h+pbSecret], rcx
0x180064340  lea     rcx, [r14+40h]
0x180064344  call    LsapCrPrepareDataForHMACSignature
0x180064349  mov     rsi, [rsp+150h+var_E8]
0x18006434e  mov     ebx, eax
0x180064350  test    eax, eax
0x180064352  js      loc_1800644C7
0x180064358  mov     r9, [rbp+50h+hMem]
0x18006435c  lea     rax, [rsp+150h+Size]
0x180064361  mov     r8d, dword ptr [rsp+150h+var_10C+4]
0x180064366  mov     rdx, rsi
0x180064369  mov     rcx, [rsp+150h+phAlgorithm]; hAlgorithm
0x18006436e  mov     [rsp+150h+var_120], rax; __int64
0x180064373  lea     rax, [rbp+50h+Buf1]
0x180064377  mov     qword ptr [rsp+150h+cbSecret], rax; __int64
0x18006437c  mov     eax, [rsp+150h+cbInput]
0x180064380  mov     dword ptr [rsp+150h+pbSecret], eax; cbInput
0x180064384  call    LsapCrGenerateHMACWithSHA512
0x180064389  mov     ebx, eax
0x18006438b  test    eax, eax
0x18006438d  js      loc_1800644C7
0x180064393  mov     r8d, dword ptr [rsp+150h+Size]; Size
0x180064398  mov     rdx, r14; Buf2
0x18006439b  mov     rcx, [rbp+50h+Buf1]; Buf1
0x18006439f  call    memcmp_0
0x1800643a4  test    eax, eax
0x1800643a6  jz      short loc_1800643B2
0x1800643a8  mov     ebx, 0C000000Dh
0x1800643ad  jmp     loc_1800644C7
0x1800643b2  mov     rdx, [rsp+150h+var_E0]
0x1800643b7  lea     rax, [rsp+150h+var_110]
0x1800643bc  mov     rcx, [rsp+150h+phAlgorithm]; hAlgorithm
0x1800643c1  lea     r9, [rbp+50h+var_80]
0x1800643c5  mov     [rsp+150h+var_120], rax; __int64
0x1800643ca  mov     r8d, 10h
0x1800643d0  lea     rax, [rsp+150h+var_D8]
0x1800643d5  mov     qword ptr [rsp+150h+cbSecret], rax; __int64
0x1800643da  mov     dword ptr [rsp+150h+pbSecret], 3Eh ; '>'; cbInput
0x1800643e2  call    LsapCrGenerateHMACWithSHA512
0x1800643e7  mov     r13d, [rsp+150h+var_110]
0x1800643ec  mov     ebx, eax
0x1800643ee  mov     r15, [rsp+150h+var_D8]
0x1800643f3  test    eax, eax
0x1800643f5  js      loc_1800644C7
0x1800643fb  mov     edx, [r14+50h]; cbInput
0x1800643ff  lea     rax, [rsp+150h+var_10C]
0x180064404  mov     rcx, [r14+58h]; pbInput
0x180064408  lea     r8, [r14+40h]; pbIV
0x18006440c  mov     [rsp+150h+var_118], rax; __int64
0x180064411  lea     rax, [rsp+150h+var_F0]
0x180064416  mov     [rsp+150h+var_120], rax; __int64
0x18006441b  mov     [rsp+150h+cbSecret], r13d; cbSecret
0x180064420  mov     [rsp+150h+pbSecret], r15; pbSecret
0x180064425  call    LsapCrDecryptDataWithAES
0x18006442a  mov     r12d, dword ptr [rsp+150h+var_10C]
0x18006442f  mov     ebx, eax
0x180064431  mov     rdi, [rsp+150h+var_F0]
0x180064436  test    eax, eax
0x180064438  js      loc_1800644C7
0x18006443e  cmp     r12d, 4
0x180064442  jb      loc_1800643A8
0x180064448  movzx   r13d, word ptr [rdi]
0x18006444c  lea     eax, [r13+4]
0x180064450  cmp     r12d, eax
0x180064453  jz      short loc_180064461
0x180064455  mov     ebx, 0C000000Dh
0x18006445a  mov     r13d, [rsp+150h+var_110]
0x18006445f  jmp     short loc_1800644C7
0x180064461  movzx   eax, word ptr [rdi+2]
0x180064465  mov     [rsp+150h+var_E0], rax
0x18006446a  lea     rdx, [rax+10h]; uBytes
0x18006446e  cmp     rdx, 10h
0x180064472  jnb     short loc_18006447B
0x180064474  mov     ebx, 0C0000095h
0x180064479  jmp     short loc_18006445A
0x18006447b  mov     ecx, 40h ; '@'; uFlags
0x180064480  call    cs:__imp_LocalAlloc
0x180064486  mov     r14, rax
0x180064489  test    rax, rax
0x18006448c  jnz     short loc_180064495
0x18006448e  mov     ebx, 0C0000017h
0x180064493  jmp     short loc_18006445A
0x180064495  mov     [rax], r13w
0x180064499  lea     rcx, [r14+10h]; void *
0x18006449d  mov     rax, [rsp+150h+var_E0]
0x1800644a2  lea     rdx, [rdi+4]; Src
0x1800644a6  xor     ebx, ebx
0x1800644a8  mov     [r14+2], ax
0x1800644ad  mov     r8, r13; Size
0x1800644b0  mov     [r14+8], rcx
0x1800644b4  call    memcpy_0
0x1800644b9  mov     rax, [rbp+50h+var_C0]
0x1800644bd  mov     [rax], r14
0x1800644c0  jmp     short loc_18006445A
0x1800644c2  mov     rsi, [rsp+150h+var_E8]
0x1800644c7  xor     ecx, ecx
0x1800644c9  call    LsapFreeAesClearValue
0x1800644ce  test    rdi, rdi
0x1800644d1  jz      short loc_1800644F3
0x1800644d3  mov     ecx, r12d
0x1800644d6  mov     rax, rdi
0x1800644d9  test    r12d, r12d
0x1800644dc  jz      short loc_1800644EA
0x1800644de  mov     byte ptr [rax], 0
0x1800644e1  inc     rax
0x1800644e4  sub     rcx, 1
0x1800644e8  jnz     short loc_1800644DE
0x1800644ea  mov     rcx, rdi; hMem
0x1800644ed  call    cs:__imp_LocalFree
0x1800644f3  test    r15, r15
0x1800644f6  jz      short loc_180064518
0x1800644f8  mov     edx, r13d
0x1800644fb  mov     rax, r15
0x1800644fe  test    r13d, r13d
0x180064501  jz      short loc_18006450F
0x180064503  mov     byte ptr [rax], 0
0x180064506  inc     rax
0x180064509  sub     rdx, 1
0x18006450d  jnz     short loc_180064503
0x18006450f  mov     rcx, r15; hMem
0x180064512  call    cs:__imp_LocalFree
0x180064518  mov     rcx, [rbp+50h+Buf1]; hMem
0x18006451c  call    cs:__imp_LocalFree
0x180064522  mov     rcx, [rbp+50h+hMem]; hMem
0x180064526  call    cs:__imp_LocalFree
0x18006452c  test    rsi, rsi
0x18006452f  jz      short loc_180064552
0x180064531  mov     eax, dword ptr [rsp+150h+var_10C+4]
0x180064535  mov     rcx, rsi
0x180064538  test    rax, rax
0x18006453b  jz      short loc_180064549
0x18006453d  mov     byte ptr [rcx], 0
0x180064540  inc     rcx
0x180064543  sub     rax, 1
0x180064547  jnz     short loc_18006453D
0x180064549  mov     rcx, rsi; hMem
0x18006454c  call    cs:__imp_LocalFree
0x180064552  mov     rcx, [rsp+150h+phAlgorithm]; hAlgorithm
0x180064557  test    rcx, rcx
0x18006455a  jz      short loc_180064564
0x18006455c  xor     edx, edx; dwFlags
0x18006455e  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180064564  mov     eax, ebx
0x180064566  mov     rcx, [rbp+50h+var_40]
0x18006456a  xor     rcx, rsp; StackCookie
0x18006456d  call    __security_check_cookie
0x180064572  mov     rbx, [rsp+150h+arg_8]
0x18006457a  add     rsp, 120h
0x180064581  pop     r15
0x180064583  pop     r14
0x180064585  pop     r13
0x180064587  pop     r12
0x180064589  pop     rdi
0x18006458a  pop     rsi
0x18006458b  pop     rbp
0x18006458c  retn
```
