# TpmKey20Rsa::ImportKey(TpmKey *,ushort const *,uchar const *,uint,uint)

- ea: `0x180027210`
- end: `0x180027669`
- name: `?ImportKey@TpmKey20Rsa@@UEAAJPEAVTpmKey@@PEBGPEBEII@Z`
- size: `1113`
- prototype: `__int64 __usercall@<rax>(TpmKey20Rsa *__hidden this@<rcx>, struct TpmKey *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int8 *@<r9>, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18008bb60`

## callees

- `0x18000dc90`
- `0x1800133c4`
- `0x180014a60`
- `0x1800157c0`
- `0x180027210`
- `0x180027670`
- `0x180029a20`
- `0x18004dbe0`
- `0x180061bac`
- `0x1800768a0`
- `0x1800c2ce0`

## import_xrefs

- `bcrypt!BCryptImportKeyPair` at `0x1800274be`
- `bcrypt!BCryptImportKeyPair` at `0x1800274be`
- `bcrypt!BCryptDestroyKey` at `0x180027484`
- `bcrypt!BCryptDestroyKey` at `0x180027484`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18002743b`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18002743b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TpmKey20Rsa::ImportKey(
        TpmKey20Rsa *this,
        struct TpmKey *a2,
        const unsigned __int16 *a3,
        unsigned __int8 *a4,
        ULONG cbInput,
        unsigned int a6)
{
  int KeyInTpm; // eax
  unsigned int v11; // ebx
  __int64 v13; // rdx
  __int64 v14; // r9
  void *v15; // rcx
  int v16; // ecx
  NTSTATUS v17; // eax
  __int64 v18; // rdx
  void *v19; // rcx
  rsize_t v20; // r14
  int v21; // ecx
  int pbInput; // [rsp+20h] [rbp-78h]
  void *Destination; // [rsp+40h] [rbp-58h] BYREF
  int *v24[10]; // [rsp+48h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v24, L"TpmKey20Rsa::ImportKey", 1);
  if ( (a6 & 0xFFFFEFF7) != 0 )
  {
    v11 = -2144795644;
    v14 = 2150171652LL;
    v13 = 854;
    goto LABEL_9;
  }
  if ( wcscmp_0(a3, L"OpaqueKeyBlob")
    && wcscmp_0(a3, L"PcpTpmProtectedKeyBlob")
    && wcscmp_0(a3, L"PcpTpmPersistentKeyBlob") )
  {
    if ( wcscmp_0(a3, L"RSAFULLPRIVATEBLOB") && wcscmp_0(a3, L"RSAPRIVATEBLOB") )
    {
      if ( wcscmp_0(a3, L"RSAPUBLICBLOB") && wcscmp_0(a3, L"PUBLICBLOB") )
      {
        v11 = -2144795643;
        v14 = 2150171653LL;
        v13 = 962;
        goto LABEL_9;
      }
      if ( *((_DWORD *)this + 116) || *((_QWORD *)this + 12) )
      {
        v11 = -2144795628;
        v14 = 2150171668LL;
        v13 = 921;
        goto LABEL_9;
      }
      if ( ((*(_DWORD *)a4 - 826364754) & 0xFEFFFFFF) != 0 )
      {
        v11 = -2144795645;
        v14 = 2150171651LL;
        v13 = 926;
        goto LABEL_9;
      }
      v16 = *((_DWORD *)a4 + 1);
      if ( (unsigned int)(v16 - 1024) > 0x400 || (v16 & 0x3FF) != 0 )
      {
        v11 = -2144795643;
        v14 = 2150171653LL;
        v13 = 932;
        goto LABEL_9;
      }
      if ( !*((_QWORD *)this + 128) )
      {
        v17 = BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)this + 128, L"RSA", L"Microsoft Primitive Provider", 0);
        if ( v17 < 0 )
        {
          v18 = 940;
LABEL_29:
          v11 = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)v18,
                  (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
                  (const char *)(unsigned int)v17,
                  pbInput);
          goto LABEL_6;
        }
      }
      v19 = (void *)*((_QWORD *)this + 129);
      if ( v19 )
      {
        BCryptDestroyKey(v19);
        *((_QWORD *)this + 129) = 0;
      }
      v17 = BCryptImportKeyPair(
              *((BCRYPT_ALG_HANDLE *)this + 128),
              0,
              L"RSAPUBLICBLOB",
              (BCRYPT_KEY_HANDLE *)this + 129,
              a4,
              cbInput,
              0);
      if ( v17 < 0 )
      {
        v18 = 958;
        goto LABEL_29;
      }
      goto LABEL_4;
    }
    if ( *((_DWORD *)this + 116) || *((_QWORD *)this + 12) )
    {
      v11 = -2144795628;
      v14 = 2150171668LL;
      v13 = 873;
      goto LABEL_9;
    }
    if ( cbInput > 0x18 )
    {
      if ( *(_DWORD *)a4 == 843141970 )
      {
        v20 = cbInput;
        if ( cbInput != *((unsigned int *)a4 + 2)
                      + 24LL
                      + *((unsigned int *)a4 + 4)
                      + *((unsigned int *)a4 + 5)
                      + (unsigned __int64)*((unsigned int *)a4 + 3) )
        {
          v11 = -2144795645;
          v14 = 2150171651LL;
          v13 = 887;
          goto LABEL_9;
        }
        goto LABEL_42;
      }
      if ( *(_DWORD *)a4 == 859919186 )
      {
        v20 = cbInput;
LABEL_42:
        if ( *(_DWORD *)a4 == 859919186
          && v20 != *((unsigned int *)a4 + 2)
                  + 3 * (*((unsigned int *)a4 + 4) + 8LL)
                  + 2 * (*((unsigned int *)a4 + 5) + (unsigned __int64)*((unsigned int *)a4 + 3)) )
        {
          v11 = -2144795645;
          v14 = 2150171651LL;
          v13 = 900;
          goto LABEL_9;
        }
        v21 = *((_DWORD *)a4 + 1);
        if ( (unsigned int)(v21 - 1024) > 0x400 || (v21 & 0x3FF) != 0 )
        {
          v11 = -2144795643;
          v14 = 2150171653LL;
          v13 = 906;
          goto LABEL_9;
        }
        *((_DWORD *)this + 164) = 0;
        operator delete(*((void **)this + 81), (const struct std::nothrow_t *)0x33415352);
        *((_QWORD *)this + 81) = 0;
        wil::make_unique_nothrow<unsigned char [0]>(&Destination, v20);
        v15 = Destination;
        if ( !Destination )
        {
          v11 = -2147024888;
          goto LABEL_6;
        }
        *((_QWORD *)this + 81) = Destination;
        *((_DWORD *)this + 164) = cbInput;
        memcpy_s_3(v15, v20, a4, v20);
        *((_DWORD *)this + 169) = *((_DWORD *)a4 + 1);
        goto LABEL_4;
      }
    }
    v11 = -2144795645;
    v14 = 2150171651LL;
    v13 = 878;
    goto LABEL_9;
  }
  KeyInTpm = TpmKey20::ImportKey(this, a2, a3, a4, cbInput, a6);
  v11 = KeyInTpm;
  if ( KeyInTpm < 0 )
  {
    v13 = 865;
LABEL_8:
    v14 = (unsigned int)KeyInTpm;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
      (const char *)v14,
      pbInput);
    goto LABEL_6;
  }
LABEL_4:
  if ( (a6 & 8) == 0 && (!wcscmp_0(a3, L"RSAFULLPRIVATEBLOB") || !wcscmp_0(a3, L"RSAPRIVATEBLOB")) )
  {
    KeyInTpm = TpmKey20::LoadKeyInTpm(this);
    v11 = KeyInTpm;
    if ( KeyInTpm < 0 )
    {
      v13 = 970;
      goto LABEL_8;
    }
  }
  v11 = 0;
LABEL_6:
  KspFunctionLogger::~KspFunctionLogger(v24);
  return v11;
}

```

## disassembly

```asm
0x180027210  push    rbx
0x180027212  push    rbp
0x180027213  push    rsi
0x180027214  push    rdi
0x180027215  push    r12
0x180027217  push    r14
0x180027219  push    r15
0x18002721b  sub     rsp, 60h
0x18002721f  mov     rbx, r9
0x180027222  mov     rsi, r8
0x180027225  mov     rbp, rdx
0x180027228  mov     rdi, rcx
0x18002722b  mov     r8b, 1; bool
0x18002722e  lea     rdx, aTpmkey20rsaImp; "TpmKey20Rsa::ImportKey"
0x180027235  lea     rcx, [rsp+98h+var_50]; this
0x18002723a  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x18002723f  nop
0x180027240  mov     r12d, [rsp+98h+arg_28]
0x180027248  test    r12d, 0FFFFEFF7h
0x18002724f  jnz     loc_1800272D9
0x180027255  lea     rdx, aOpaquekeyblob; "OpaqueKeyBlob"
0x18002725c  mov     rcx, rsi; String1
0x18002725f  call    wcscmp_0
0x180027264  test    eax, eax
0x180027266  jnz     loc_18002732E
0x18002726c  mov     [rsp+98h+cbInput], r12d; unsigned int
0x180027271  mov     eax, [rsp+98h+arg_20]
0x180027278  mov     dword ptr [rsp+98h+pbInput], eax; int
0x18002727c  mov     r9, rbx; unsigned __int8 *
0x18002727f  mov     r8, rsi; unsigned __int16 *
0x180027282  mov     rdx, rbp; struct TpmKey *
0x180027285  mov     rcx, rdi; this
0x180027288  call    ?ImportKey@TpmKey20@@UEAAJPEAVTpmKey@@PEBGPEBEII@Z; TpmKey20::ImportKey(TpmKey *,ushort const *,uchar const *,uint,uint)
0x18002728d  mov     ebx, eax
0x18002728f  test    eax, eax
0x180027291  js      short loc_1800272BB
0x180027293  test    r12b, 8
0x180027297  jz      loc_180027622
0x18002729d  xor     ebx, ebx
0x18002729f  lea     rcx, [rsp+98h+var_50]; this
0x1800272a4  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x1800272a9  mov     eax, ebx
0x1800272ab  add     rsp, 60h
0x1800272af  pop     r15
0x1800272b1  pop     r14
0x1800272b3  pop     r12
0x1800272b5  pop     rdi
0x1800272b6  pop     rsi
0x1800272b7  pop     rbp
0x1800272b8  pop     rbx
0x1800272b9  retn
0x1800272bb  mov     edx, 361h; void *
0x1800272c0  mov     r9d, eax; char *
0x1800272c3  lea     r8, aOnecoreBaseNgs_10; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x1800272ca  mov     rcx, [rsp+98h]; this
0x1800272d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800272d7  jmp     short loc_18002729F
0x1800272d9  mov     ebx, 80290404h
0x1800272de  mov     r9d, ebx
0x1800272e1  mov     edx, 356h
0x1800272e6  jmp     short loc_1800272C3
0x1800272e8  mov     dword ptr [rdi+290h], 0
0x1800272f2  mov     rcx, [rdi+288h]; void *
0x1800272f9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800272fe  mov     qword ptr [rdi+288h], 0
0x180027309  mov     rdx, r14
0x18002730c  lea     rcx, [rsp+98h+Destination]
0x180027311  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x180027316  mov     rcx, [rsp+98h+Destination]; Destination
0x18002731b  test    rcx, rcx
0x18002731e  jnz     loc_1800275D5
0x180027324  mov     ebx, 80070008h
0x180027329  jmp     loc_18002729F
0x18002732e  lea     rdx, aPcptpmprotecte; "PcpTpmProtectedKeyBlob"
0x180027335  mov     rcx, rsi; String1
0x180027338  call    wcscmp_0
0x18002733d  test    eax, eax
0x18002733f  jz      loc_18002726C
0x180027345  lea     rdx, aPcptpmpersiste; "PcpTpmPersistentKeyBlob"
0x18002734c  mov     rcx, rsi; String1
0x18002734f  call    wcscmp_0
0x180027354  test    eax, eax
0x180027356  jz      loc_18002726C
0x18002735c  lea     rdx, aRsafullprivate; "RSAFULLPRIVATEBLOB"
0x180027363  mov     rcx, rsi; String1
0x180027366  call    wcscmp_0
0x18002736b  test    eax, eax
0x18002736d  jz      loc_1800274FB
0x180027373  lea     rdx, aRsaprivateblob; "RSAPRIVATEBLOB"
0x18002737a  mov     rcx, rsi; String1
0x18002737d  call    wcscmp_0
0x180027382  test    eax, eax
0x180027384  jz      loc_1800274FB
0x18002738a  lea     rdx, aRsapublicblob; "RSAPUBLICBLOB"
0x180027391  mov     rcx, rsi; String1
0x180027394  call    wcscmp_0
0x180027399  test    eax, eax
0x18002739b  jz      short loc_1800273C2
0x18002739d  lea     rdx, aPublicblob; "PUBLICBLOB"
0x1800273a4  mov     rcx, rsi; String1
0x1800273a7  call    wcscmp_0
0x1800273ac  test    eax, eax
0x1800273ae  jz      short loc_1800273C2
0x1800273b0  mov     ebx, 80290405h
0x1800273b5  mov     r9d, ebx
0x1800273b8  mov     edx, 3C2h
0x1800273bd  jmp     loc_1800272C3
0x1800273c2  cmp     dword ptr [rdi+1D0h], 0
0x1800273c9  jnz     loc_1800274E9
0x1800273cf  cmp     qword ptr [rdi+60h], 0
0x1800273d4  jnz     loc_1800274E9
0x1800273da  mov     eax, [rbx]
0x1800273dc  sub     eax, 31415352h
0x1800273e1  test    eax, 0FEFFFFFFh
0x1800273e6  jz      short loc_1800273FA
0x1800273e8  mov     ebx, 80290403h
0x1800273ed  mov     r9d, ebx
0x1800273f0  mov     edx, 39Eh
0x1800273f5  jmp     loc_1800272C3
0x1800273fa  mov     ecx, [rbx+4]
0x1800273fd  lea     eax, [rcx-400h]
0x180027403  cmp     eax, 400h
0x180027408  ja      loc_1800274D7
0x18002740e  test    ecx, 3FFh
0x180027414  jnz     loc_1800274D7
0x18002741a  lea     r15, [rdi+400h]
0x180027421  cmp     qword ptr [r15], 0
0x180027425  jnz     short loc_180027475
0x180027427  xor     r9d, r9d; dwFlags
0x18002742a  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x180027431  lea     rdx, aRsa; "RSA"
0x180027438  mov     rcx, r15; phAlgorithm
0x18002743b  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180027442  nop     dword ptr [rax+rax+00h]
0x180027447  test    eax, eax
0x180027449  jns     short loc_180027475
0x18002744b  mov     edx, 3ACh
0x180027450  jmp     short loc_180027457
0x180027452  mov     edx, 3BEh; void *
0x180027457  lea     r8, aOnecoreBaseNgs_10; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18002745e  mov     r9d, eax; char *
0x180027461  mov     rcx, [rsp+98h]; this
0x180027469  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002746e  mov     ebx, eax
0x180027470  jmp     loc_18002729F
0x180027475  lea     r14, [rdi+408h]
0x18002747c  mov     rcx, [r14]; hKey
0x18002747f  test    rcx, rcx
0x180027482  jz      short loc_180027497
0x180027484  call    cs:__imp_BCryptDestroyKey
0x18002748b  nop     dword ptr [rax+rax+00h]
0x180027490  mov     qword ptr [r14], 0
0x180027497  mov     [rsp+98h+dwFlags], 0; dwFlags
0x18002749f  mov     eax, [rsp+98h+arg_20]
0x1800274a6  mov     [rsp+98h+cbInput], eax; cbInput
0x1800274aa  mov     [rsp+98h+pbInput], rbx; int
0x1800274af  mov     r9, r14; phKey
0x1800274b2  lea     r8, aRsapublicblob; "RSAPUBLICBLOB"
0x1800274b9  xor     edx, edx; hImportKey
0x1800274bb  mov     rcx, [r15]; hAlgorithm
0x1800274be  call    cs:__imp_BCryptImportKeyPair
0x1800274c5  nop     dword ptr [rax+rax+00h]
0x1800274ca  test    eax, eax
0x1800274cc  jns     loc_180027293
0x1800274d2  jmp     loc_180027452
0x1800274d7  mov     ebx, 80290405h
0x1800274dc  mov     r9d, ebx
0x1800274df  mov     edx, 3A4h
0x1800274e4  jmp     loc_1800272C3
0x1800274e9  mov     ebx, 80290414h
0x1800274ee  mov     r9d, ebx
0x1800274f1  mov     edx, 399h
0x1800274f6  jmp     loc_1800272C3
0x1800274fb  cmp     dword ptr [rdi+1D0h], 0
0x180027502  jnz     loc_180027610
0x180027508  cmp     qword ptr [rdi+60h], 0
0x18002750d  jnz     loc_180027610
0x180027513  mov     ebp, [rsp+98h+arg_20]
0x18002751a  cmp     ebp, 18h
0x18002751d  jbe     loc_1800275FE
0x180027523  mov     edx, 33415352h; struct std::nothrow_t *
0x180027528  cmp     dword ptr [rbx], 32415352h
0x18002752e  jz      short loc_180027574
0x180027530  cmp     [rbx], edx
0x180027532  jnz     loc_1800275FE
0x180027538  mov     r14d, ebp
0x18002753b  cmp     [rbx], edx
0x18002753d  jnz     short loc_1800275A7
0x18002753f  mov     ecx, [rbx+0Ch]
0x180027542  mov     eax, [rbx+14h]
0x180027545  add     rcx, rax
0x180027548  mov     eax, [rbx+10h]
0x18002754b  add     rax, 8
0x18002754f  lea     rax, [rax+rax*2]
0x180027553  lea     rcx, [rax+rcx*2]
0x180027557  mov     eax, [rbx+8]
0x18002755a  add     rcx, rax
0x18002755d  cmp     r14, rcx
0x180027560  jz      short loc_1800275A7
0x180027562  mov     ebx, 80290403h
0x180027567  mov     r9d, ebx
0x18002756a  mov     edx, 384h
0x18002756f  jmp     loc_1800272C3
0x180027574  mov     r14, rbp
0x180027577  mov     ecx, [rbx+0Ch]
0x18002757a  mov     eax, [rbx+14h]
0x18002757d  add     rcx, rax
0x180027580  mov     eax, [rbx+10h]
0x180027583  add     rcx, rax
0x180027586  mov     eax, [rbx+8]
0x180027589  add     rax, 18h
0x18002758d  add     rcx, rax
0x180027590  cmp     rbp, rcx
0x180027593  jz      short loc_18002753B
0x180027595  mov     ebx, 80290403h
0x18002759a  mov     r9d, ebx
0x18002759d  mov     edx, 377h
0x1800275a2  jmp     loc_1800272C3
0x1800275a7  mov     ecx, [rbx+4]
0x1800275aa  lea     eax, [rcx-400h]
0x1800275b0  cmp     eax, 400h
0x1800275b5  ja      short loc_1800275C3
0x1800275b7  test    ecx, 3FFh
0x1800275bd  jz      loc_1800272E8
0x1800275c3  mov     ebx, 80290405h
0x1800275c8  mov     r9d, ebx
0x1800275cb  mov     edx, 38Ah
0x1800275d0  jmp     loc_1800272C3
0x1800275d5  mov     [rdi+288h], rcx
0x1800275dc  mov     [rdi+290h], ebp
0x1800275e2  mov     r9, r14; SourceSize
0x1800275e5  mov     r8, rbx; Source
0x1800275e8  mov     rdx, r14; DestinationSize
0x1800275eb  call    memcpy_s_3
0x1800275f0  mov     eax, [rbx+4]
0x1800275f3  mov     [rdi+2A4h], eax
0x1800275f9  jmp     loc_180027293
0x1800275fe  mov     ebx, 80290403h
0x180027603  mov     r9d, ebx
0x180027606  mov     edx, 36Eh
0x18002760b  jmp     loc_1800272C3
0x180027610  mov     ebx, 80290414h
0x180027615  mov     r9d, ebx
0x180027618  mov     edx, 369h
0x18002761d  jmp     loc_1800272C3
0x180027622  lea     rdx, aRsafullprivate; "RSAFULLPRIVATEBLOB"
0x180027629  mov     rcx, rsi; String1
0x18002762c  call    wcscmp_0
0x180027631  test    eax, eax
0x180027633  jz      short loc_18002764C
0x180027635  lea     rdx, aRsaprivateblob; "RSAPRIVATEBLOB"
0x18002763c  mov     rcx, rsi; String1
0x18002763f  call    wcscmp_0
0x180027644  test    eax, eax
0x180027646  jnz     loc_18002729D
0x18002764c  mov     rcx, rdi; this
0x18002764f  call    ?LoadKeyInTpm@TpmKey20@@IEAAJXZ; TpmKey20::LoadKeyInTpm(void)
0x180027654  mov     ebx, eax
0x180027656  test    eax, eax
0x180027658  jns     loc_18002729D
0x18002765e  mov     edx, 3CAh
0x180027663  jmp     loc_1800272C0
```
