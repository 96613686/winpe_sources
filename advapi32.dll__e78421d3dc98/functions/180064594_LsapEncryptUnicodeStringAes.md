# LsapEncryptUnicodeStringAes

- ea: `0x180064594`
- end: `0x18006495e`
- name: `LsapEncryptUnicodeStringAes`
- size: `970`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18006314c`

## callees

- `0x180063cf4`
- `0x180063f38`
- `0x18006412c`
- `0x180064594`
- `0x180065042`
- `0x180065090`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x1800646d4`
- `KERNELBASE!LocalAlloc` at `0x1800646d4`
- `KERNEL32!LocalFree` at `0x180064899`
- `KERNEL32!LocalFree` at `0x1800648a2`
- `KERNEL32!LocalFree` at `0x1800648cb`
- `KERNEL32!LocalFree` at `0x1800648d4`
- `KERNEL32!LocalFree` at `0x1800648f7`
- `KERNEL32!LocalFree` at `0x18006491d`
- `KERNEL32!LocalFree` at `0x180064899`
- `KERNEL32!LocalFree` at `0x1800648a2`
- `KERNEL32!LocalFree` at `0x1800648cb`
- `KERNEL32!LocalFree` at `0x1800648d4`
- `KERNEL32!LocalFree` at `0x1800648f7`
- `KERNEL32!LocalFree` at `0x18006491d`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18006492f`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18006492f`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180064695`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180064695`

## pseudocode

```c
__int64 __fastcall LsapEncryptUnicodeStringAes(
        void *a1,
        __int64 a2,
        UCHAR *a3,
        __int64 a4,
        unsigned __int16 *a5,
        void **a6)
{
  ULONG v6; // esi
  _BYTE *v7; // r12
  _BYTE *v8; // r14
  HLOCAL v9; // r15
  UCHAR *v11; // rdi
  NTSTATUS v12; // ebx
  unsigned int v13; // ebx
  UCHAR *v14; // rax
  const void *v15; // rdx
  int HMACWithSHA512; // eax
  PUCHAR v17; // r13
  int v18; // eax
  __int64 v19; // rdx
  int v20; // eax
  HLOCAL v21; // r13
  void **v22; // rcx
  __int64 v23; // rax
  _BYTE *v24; // rcx
  __int64 v25; // rcx
  UCHAR *v26; // rax
  __int64 v27; // rcx
  _BYTE *v28; // rax
  HLOCAL hMem; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v30; // [rsp+48h] [rbp-B8h] BYREF
  ULONG cbSecret; // [rsp+50h] [rbp-B0h] BYREF
  ULONG cbInput; // [rsp+54h] [rbp-ACh] BYREF
  size_t Size; // [rsp+58h] [rbp-A8h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+60h] [rbp-A0h] BYREF
  HLOCAL v35; // [rsp+68h] [rbp-98h] BYREF
  HLOCAL v36; // [rsp+70h] [rbp-90h] BYREF
  HLOCAL v37; // [rsp+78h] [rbp-88h] BYREF
  void *Src[2]; // [rsp+80h] [rbp-80h] BYREF
  void **v39; // [rsp+90h] [rbp-70h]
  PUCHAR pbIV; // [rsp+98h] [rbp-68h]
  char v41[56]; // [rsp+A0h] [rbp-60h] BYREF
  char v42[64]; // [rsp+D8h] [rbp-28h] BYREF

  v6 = 0;
  v7 = 0;
  strcpy(v42, "Microsoft LSAD encryption key AEAD-AES-256-CBC-HMAC-SHA512 16");
  v8 = 0;
  pbIV = a3;
  v9 = 0;
  Src[1] = a1;
  v39 = a6;
  phAlgorithm = 0;
  v37 = 0;
  v35 = 0;
  cbSecret = 0;
  v36 = 0;
  strcpy(v41, "Microsoft LSAD MAC key AEAD-AES-256-CBC-HMAC-SHA512 16");
  v30 = 0;
  Src[0] = 0;
  LODWORD(Size) = 0;
  hMem = 0;
  cbInput = 0;
  if ( !*a6 )
    return 3221225485LL;
  v11 = 0;
  v12 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA512", 0, 8u);
  if ( v12 >= 0 )
  {
    if ( *a5 )
    {
      v13 = *a5;
      v6 = v13 + 4;
    }
    else
    {
      v6 = 4;
      v13 = 0;
    }
    v14 = (UCHAR *)LocalAlloc(0x40u, v6);
    v11 = v14;
    if ( v14 )
    {
      *(_WORD *)v14 = *a5;
      *((_WORD *)v14 + 1) = a5[1];
      if ( v13 )
      {
        v15 = (const void *)*((_QWORD *)a5 + 1);
        if ( v15 )
          memcpy_0(v14 + 4, v15, v13);
      }
      HMACWithSHA512 = LsapCrGenerateHMACWithSHA512(phAlgorithm, 0x3Eu, (__int64)&v37, (__int64)&cbSecret);
      v7 = v37;
      v12 = HMACWithSHA512;
      if ( HMACWithSHA512 >= 0 )
      {
        v17 = pbIV;
        v12 = LsapCrEncryptDataWithAES(v11, v6, pbIV, (__int64)v37, cbSecret, (__int64)&v36, (__int64)&v30);
        if ( v12 < 0 )
        {
          v9 = v36;
        }
        else
        {
          v18 = LsapCrGenerateHMACWithSHA512(phAlgorithm, 0x37u, (__int64)&v35, (__int64)&v30 + 4);
          v9 = v36;
          v12 = v18;
          if ( v18 >= 0 )
          {
            v20 = LsapCrPrepareDataForHMACSignature(v17, v19, v36, (unsigned int)v30, &hMem, &cbInput);
            v21 = hMem;
            v12 = v20;
            v8 = v35;
            if ( v20 >= 0 )
            {
              v12 = LsapCrGenerateHMACWithSHA512(phAlgorithm, cbInput, (__int64)Src, (__int64)&Size);
              if ( v12 >= 0 )
              {
                memcpy_0(*v39, Src[0], (unsigned int)Size);
                v22 = v39;
                *((_OWORD *)*v39 + 4) = *(_OWORD *)pbIV;
                *((_QWORD *)*v22 + 11) = v9;
                v9 = 0;
                *((_DWORD *)*v22 + 20) = v30;
              }
            }
            goto LABEL_21;
          }
          v8 = v35;
        }
      }
    }
    else
    {
      v12 = -1073741801;
    }
  }
  v21 = hMem;
LABEL_21:
  LocalFree(Src[0]);
  LocalFree(v21);
  if ( v8 )
  {
    v23 = HIDWORD(v30);
    v24 = v8;
    if ( HIDWORD(v30) )
    {
      do
      {
        *v24++ = 0;
        --v23;
      }
      while ( v23 );
    }
    LocalFree(v8);
  }
  LocalFree(v9);
  if ( v11 )
  {
    v25 = v6;
    v26 = v11;
    if ( v6 )
    {
      do
      {
        *v26++ = 0;
        --v25;
      }
      while ( v25 );
    }
    LocalFree(v11);
  }
  if ( v7 )
  {
    v27 = cbSecret;
    v28 = v7;
    if ( cbSecret )
    {
      do
      {
        *v28++ = 0;
        --v27;
      }
      while ( v27 );
    }
    LocalFree(v7);
  }
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180064594  mov     [rsp-8+arg_8], rbx
0x180064599  push    rbp
0x18006459a  push    rsi
0x18006459b  push    rdi
0x18006459c  push    r12
0x18006459e  push    r13
0x1800645a0  push    r14
0x1800645a2  push    r15
0x1800645a4  lea     rbp, [rsp-20h]
0x1800645a9  sub     rsp, 120h
0x1800645b0  mov     rax, cs:__security_cookie
0x1800645b7  xor     rax, rsp
0x1800645ba  mov     [rbp+50h+var_38], rax
0x1800645be  movups  xmm0, xmmword ptr cs:aMicrosoftLsadE; "Microsoft LSAD encryption key AEAD-AES-"...
0x1800645c5  mov     rax, [rbp+50h+arg_28]
0x1800645cc  xor     esi, esi
0x1800645ce  movups  xmm1, xmmword ptr cs:aMicrosoftLsadE+10h; "ncryption key AEAD-AES-256-CBC-HMAC-SHA"...
0x1800645d5  mov     r13, [rbp+50h+arg_20]
0x1800645dc  mov     r12d, esi
0x1800645df  movups  xmmword ptr [rbp+50h+var_78], xmm0
0x1800645e3  mov     r14d, esi
0x1800645e6  mov     [rbp+50h+pbIV], r8
0x1800645ea  mov     r15d, esi
0x1800645ed  mov     [rbp+50h+var_C8], rcx
0x1800645f1  movups  xmm0, xmmword ptr cs:aMicrosoftLsadE+20h; "AD-AES-256-CBC-HMAC-SHA512 16"
0x1800645f8  mov     [rbp+50h+var_C0], rax
0x1800645fc  movups  xmmword ptr [rbp+50h+var_78+10h], xmm1
0x180064600  mov     [rsp+150h+phAlgorithm], rsi
0x180064605  movups  xmm1, xmmword ptr cs:aMicrosoftLsadE+2Eh; "-HMAC-SHA512 16"
0x18006460c  mov     [rsp+150h+var_D8], rsi
0x180064611  movups  xmmword ptr [rbp+50h+var_78+20h], xmm0
0x180064615  mov     [rsp+150h+var_E8], rsi
0x18006461a  movups  xmm0, xmmword ptr cs:aMicrosoftLsadM; "Microsoft LSAD MAC key AEAD-AES-256-CBC"...
0x180064621  mov     [rsp+150h+var_100], esi
0x180064625  movups  xmmword ptr [rbp+50h+var_78+2Eh], xmm1
0x180064629  mov     dword ptr [rsp+150h+var_108+4], esi
0x18006462d  movups  xmm1, xmmword ptr cs:aMicrosoftLsadM+10h; "AC key AEAD-AES-256-CBC-HMAC-SHA512 16"
0x180064634  mov     [rsp+150h+var_E0], rsi
0x180064639  movups  xmmword ptr [rbp+50h+var_B0], xmm0
0x18006463d  mov     dword ptr [rsp+150h+var_108], esi
0x180064641  movups  xmm0, xmmword ptr cs:aMicrosoftLsadM+20h; "256-CBC-HMAC-SHA512 16"
0x180064648  mov     [rbp+50h+Src], rsi
0x18006464c  movups  xmmword ptr [rbp+50h+var_B0+10h], xmm1
0x180064650  mov     dword ptr [rsp+150h+Size], esi
0x180064654  movsd   xmm1, qword ptr cs:aMicrosoftLsadM+2Fh; "A512 16"
0x18006465c  movups  xmmword ptr [rbp+50h+var_B0+20h], xmm0
0x180064660  mov     [rsp+150h+hMem], rsi
0x180064665  movsd   qword ptr [rbp+50h+var_B0+2Fh], xmm1
0x18006466a  mov     [rsp+150h+var_FC], esi
0x18006466e  cmp     [rax], rsi
0x180064671  jnz     short loc_18006467D
0x180064673  mov     eax, 0C000000Dh
0x180064678  jmp     loc_180064937
0x18006467d  mov     r9d, 8; dwFlags
0x180064683  lea     rdx, pszAlgId; "SHA512"
0x18006468a  xor     r8d, r8d; pszImplementation
0x18006468d  lea     rcx, [rsp+150h+phAlgorithm]; phAlgorithm
0x180064692  mov     rdi, rsi
0x180064695  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18006469b  mov     ebx, eax
0x18006469d  test    eax, eax
0x18006469f  js      loc_180064890
0x1800646a5  cmp     [r13+0], si
0x1800646aa  jbe     short loc_1800646C6
0x1800646ac  movzx   ebx, word ptr [r13+0]
0x1800646b1  lea     esi, [rbx+4]
0x1800646b4  cmp     esi, 4
0x1800646b7  jnb     short loc_1800646CD
0x1800646b9  or      esi, 0FFFFFFFFh
0x1800646bc  mov     ebx, 0C0000095h
0x1800646c1  jmp     loc_180064890
0x1800646c6  mov     esi, 4
0x1800646cb  xor     ebx, ebx
0x1800646cd  mov     edx, esi; uBytes
0x1800646cf  mov     ecx, 40h ; '@'; uFlags
0x1800646d4  call    cs:__imp_LocalAlloc
0x1800646da  mov     rdi, rax
0x1800646dd  test    rax, rax
0x1800646e0  jnz     short loc_1800646EC
0x1800646e2  mov     ebx, 0C0000017h
0x1800646e7  jmp     loc_180064890
0x1800646ec  movzx   eax, word ptr [r13+0]
0x1800646f1  mov     [rdi], ax
0x1800646f4  movzx   eax, word ptr [r13+2]
0x1800646f9  mov     [rdi+2], ax
0x1800646fd  test    ebx, ebx
0x1800646ff  jz      short loc_180064716
0x180064701  mov     rdx, [r13+8]; Src
0x180064705  test    rdx, rdx
0x180064708  jz      short loc_180064716
0x18006470a  mov     r8d, ebx; Size
0x18006470d  lea     rcx, [rdi+4]; void *
0x180064711  call    memcpy_0
0x180064716  mov     rdx, [rbp+50h+var_C8]
0x18006471a  lea     rax, [rsp+150h+var_100]
0x18006471f  mov     rcx, [rsp+150h+phAlgorithm]; hAlgorithm
0x180064724  lea     r9, [rbp+50h+var_78]
0x180064728  mov     [rsp+150h+var_120], rax; __int64
0x18006472d  mov     r8d, 10h
0x180064733  lea     rax, [rsp+150h+var_D8]
0x180064738  mov     qword ptr [rsp+150h+cbSecret], rax; __int64
0x18006473d  mov     [rsp+150h+cbInput], 3Eh ; '>'; cbInput
0x180064745  call    LsapCrGenerateHMACWithSHA512
0x18006474a  mov     r12, [rsp+150h+var_D8]
0x18006474f  mov     ebx, eax
0x180064751  test    eax, eax
0x180064753  js      loc_180064890
0x180064759  mov     r13, [rbp+50h+pbIV]
0x18006475d  lea     rax, [rsp+150h+var_108]
0x180064762  mov     [rsp+150h+var_118], rax; __int64
0x180064767  mov     r8, r13; pbIV
0x18006476a  lea     rax, [rsp+150h+var_E0]
0x18006476f  mov     edx, esi; cbInput
0x180064771  mov     [rsp+150h+var_120], rax; __int64
0x180064776  mov     rcx, rdi; pbInput
0x180064779  mov     eax, [rsp+150h+var_100]
0x18006477d  mov     [rsp+150h+cbSecret], eax; cbSecret
0x180064781  mov     qword ptr [rsp+150h+cbInput], r12; __int64
0x180064786  call    LsapCrEncryptDataWithAES
0x18006478b  mov     ebx, eax
0x18006478d  test    eax, eax
0x18006478f  js      loc_18006488B
0x180064795  mov     rdx, [rbp+50h+var_C8]
0x180064799  lea     rax, [rsp+150h+var_108+4]
0x18006479e  mov     rcx, [rsp+150h+phAlgorithm]; hAlgorithm
0x1800647a3  lea     r9, [rbp+50h+var_B0]
0x1800647a7  mov     [rsp+150h+var_120], rax; __int64
0x1800647ac  mov     r8d, 10h
0x1800647b2  lea     rax, [rsp+150h+var_E8]
0x1800647b7  mov     qword ptr [rsp+150h+cbSecret], rax; __int64
0x1800647bc  mov     [rsp+150h+cbInput], 37h ; '7'; cbInput
0x1800647c4  call    LsapCrGenerateHMACWithSHA512
0x1800647c9  mov     r15, [rsp+150h+var_E0]
0x1800647ce  mov     ebx, eax
0x1800647d0  test    eax, eax
0x1800647d2  js      loc_180064884
0x1800647d8  mov     r9d, dword ptr [rsp+150h+var_108]
0x1800647dd  lea     rax, [rsp+150h+var_FC]
0x1800647e2  mov     qword ptr [rsp+150h+cbSecret], rax
0x1800647e7  mov     r8, r15
0x1800647ea  lea     rax, [rsp+150h+hMem]
0x1800647ef  mov     rcx, r13
0x1800647f2  mov     qword ptr [rsp+150h+cbInput], rax
0x1800647f7  call    LsapCrPrepareDataForHMACSignature
0x1800647fc  mov     r13, [rsp+150h+hMem]
0x180064801  mov     ebx, eax
0x180064803  mov     r14, [rsp+150h+var_E8]
0x180064808  test    eax, eax
0x18006480a  js      loc_180064895
0x180064810  mov     r8d, dword ptr [rsp+150h+var_108+4]
0x180064815  lea     rax, [rsp+150h+Size]
0x18006481a  mov     rcx, [rsp+150h+phAlgorithm]; hAlgorithm
0x18006481f  mov     r9, r13
0x180064822  mov     [rsp+150h+var_120], rax; __int64
0x180064827  mov     rdx, r14
0x18006482a  lea     rax, [rbp+50h+Src]
0x18006482e  mov     qword ptr [rsp+150h+cbSecret], rax; __int64
0x180064833  mov     eax, [rsp+150h+var_FC]
0x180064837  mov     [rsp+150h+cbInput], eax; cbInput
0x18006483b  call    LsapCrGenerateHMACWithSHA512
0x180064840  mov     ebx, eax
0x180064842  test    eax, eax
0x180064844  js      short loc_180064895
0x180064846  mov     rcx, [rbp+50h+var_C0]
0x18006484a  mov     r8d, dword ptr [rsp+150h+Size]; Size
0x18006484f  mov     rdx, [rbp+50h+Src]; Src
0x180064853  mov     rcx, [rcx]; void *
0x180064856  call    memcpy_0
0x18006485b  mov     rcx, [rbp+50h+var_C0]
0x18006485f  mov     rdx, [rbp+50h+pbIV]
0x180064863  mov     rax, [rcx]
0x180064866  movups  xmm0, xmmword ptr [rdx]
0x180064869  movdqu  xmmword ptr [rax+40h], xmm0
0x18006486e  mov     rax, [rcx]
0x180064871  mov     [rax+58h], r15
0x180064875  xor     r15d, r15d
0x180064878  mov     rax, [rcx]
0x18006487b  mov     ecx, dword ptr [rsp+150h+var_108]
0x18006487f  mov     [rax+50h], ecx
0x180064882  jmp     short loc_180064895
0x180064884  mov     r14, [rsp+150h+var_E8]
0x180064889  jmp     short loc_180064890
0x18006488b  mov     r15, [rsp+150h+var_E0]
0x180064890  mov     r13, [rsp+150h+hMem]
0x180064895  mov     rcx, [rbp+50h+Src]; hMem
0x180064899  call    cs:__imp_LocalFree
0x18006489f  mov     rcx, r13; hMem
0x1800648a2  call    cs:__imp_LocalFree
0x1800648a8  xor     r13d, r13d
0x1800648ab  test    r14, r14
0x1800648ae  jz      short loc_1800648D1
0x1800648b0  mov     eax, dword ptr [rsp+150h+var_108+4]
0x1800648b4  mov     rcx, r14
0x1800648b7  test    rax, rax
0x1800648ba  jz      short loc_1800648C8
0x1800648bc  mov     [rcx], r13b
0x1800648bf  inc     rcx
0x1800648c2  sub     rax, 1
0x1800648c6  jnz     short loc_1800648BC
0x1800648c8  mov     rcx, r14; hMem
0x1800648cb  call    cs:__imp_LocalFree
0x1800648d1  mov     rcx, r15; hMem
0x1800648d4  call    cs:__imp_LocalFree
0x1800648da  test    rdi, rdi
0x1800648dd  jz      short loc_1800648FD
0x1800648df  mov     ecx, esi
0x1800648e1  mov     rax, rdi
0x1800648e4  test    esi, esi
0x1800648e6  jz      short loc_1800648F4
0x1800648e8  mov     [rax], r13b
0x1800648eb  inc     rax
0x1800648ee  sub     rcx, 1
0x1800648f2  jnz     short loc_1800648E8
0x1800648f4  mov     rcx, rdi; hMem
0x1800648f7  call    cs:__imp_LocalFree
0x1800648fd  test    r12, r12
0x180064900  jz      short loc_180064923
0x180064902  mov     ecx, [rsp+150h+var_100]
0x180064906  mov     rax, r12
0x180064909  test    rcx, rcx
0x18006490c  jz      short loc_18006491A
0x18006490e  mov     [rax], r13b
0x180064911  inc     rax
0x180064914  sub     rcx, 1
0x180064918  jnz     short loc_18006490E
0x18006491a  mov     rcx, r12; hMem
0x18006491d  call    cs:__imp_LocalFree
0x180064923  mov     rcx, [rsp+150h+phAlgorithm]; hAlgorithm
0x180064928  test    rcx, rcx
0x18006492b  jz      short loc_180064935
0x18006492d  xor     edx, edx; dwFlags
0x18006492f  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180064935  mov     eax, ebx
0x180064937  mov     rcx, [rbp+50h+var_38]
0x18006493b  xor     rcx, rsp; StackCookie
0x18006493e  call    __security_check_cookie
0x180064943  mov     rbx, [rsp+150h+arg_8]
0x18006494b  add     rsp, 120h
0x180064952  pop     r15
0x180064954  pop     r14
0x180064956  pop     r13
0x180064958  pop     r12
0x18006495a  pop     rdi
0x18006495b  pop     rsi
0x18006495c  pop     rbp
0x18006495d  retn
```
