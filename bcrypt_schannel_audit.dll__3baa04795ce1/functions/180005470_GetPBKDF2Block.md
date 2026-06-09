# GetPBKDF2Block

- ea: `0x180005470`
- end: `0x180005af5`
- name: `GetPBKDF2Block`
- size: `1669`
- prototype: `__int64 __fastcall(BCRYPT_ALG_HANDLE hAlgorithm, PUCHAR pbSecret, ULONG cbSecret, PUCHAR pbInput, ULONG cbInput, __int64, int, PUCHAR pbHashObject, ULONG cbHashObject, PUCHAR pbOutput, void *, ULONG cbOutput)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18000bba0`

## callees

- `0x180005060`
- `0x180005470`
- `0x180006020`
- `0x180006da0`
- `0x1800078e0`
- `0x180007a7c`
- `0x18000cc10`
- `0x1800124c4`
- `0x18001b79d`
- `0x18001c010`

## string_xrefs

- `0x1800057bc`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000580c`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180005857`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800058bb`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000595a`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800059d4`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180005a88`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180005aae`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180005adb`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
__int64 __fastcall GetPBKDF2Block(
        BCRYPT_ALG_HANDLE hAlgorithm,
        PUCHAR pbSecret,
        ULONG cbSecret,
        PUCHAR pbInput,
        ULONG cbInput,
        unsigned __int64 a6,
        int a7,
        PUCHAR pbHashObject,
        ULONG cbHashObject,
        PUCHAR pbOutput,
        UCHAR *a11,
        ULONG cbOutput)
{
  ULONG v13; // ebp
  UCHAR *v14; // r14
  NTSTATUS v15; // eax
  int v16; // edx
  int v17; // r8d
  int v18; // edi
  NTSTATUS v19; // eax
  int v20; // edx
  int v21; // r8d
  NTSTATUS v22; // eax
  int v23; // edx
  int v24; // r8d
  NTSTATUS v25; // eax
  unsigned __int64 i; // r15
  int v27; // edx
  __int64 v28; // r8
  _DWORD *v29; // rdi
  _QWORD *v30; // rcx
  _DWORD *v31; // rdi
  _QWORD *v32; // rcx
  __int64 v33; // rbp
  int v34; // eax
  int v35; // r14d
  __int64 v36; // rdx
  __int64 v37; // rax
  int v39; // eax
  UCHAR pbInputa[8]; // [rsp+40h] [rbp-48h] BYREF
  BCRYPT_HASH_HANDLE hHash; // [rsp+48h] [rbp-40h] BYREF

  v13 = cbSecret;
  v14 = pbSecret;
  hHash = 0;
  v15 = BCryptCreateHash(hAlgorithm, &hHash, pbHashObject, cbHashObject, pbSecret, cbSecret, 0);
  v18 = v15;
  if ( v15 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v16,
        v17,
        (unsigned int)"Status",
        v15,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
        231);
  }
  else
  {
    v19 = BCryptHashData(hHash, pbInput, cbInput, 0);
    v18 = v19;
    if ( v19 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v20,
          v21,
          (unsigned int)"Status",
          v19,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
          241);
    }
    else
    {
      pbInputa[3] = a7;
      pbInputa[0] = HIBYTE(a7);
      pbInputa[1] = BYTE2(a7);
      pbInputa[2] = BYTE1(a7);
      v22 = BCryptHashData(hHash, pbInputa, 4u, 0);
      v18 = v22;
      if ( v22 < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v23,
            v24,
            (unsigned int)"Status",
            v22,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
            0);
      }
      else
      {
        v25 = BCryptFinishHash(hHash, pbOutput, cbOutput, 0);
        v18 = v25;
        if ( v25 < 0 )
        {
LABEL_66:
          DebugTraceError((unsigned int)v25, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c");
        }
        else
        {
          memcpy_0(a11, pbOutput, cbOutput);
          for ( i = 1; ; ++i )
          {
            if ( i >= a6 )
            {
              v18 = 0;
              goto LABEL_53;
            }
            BCryptDestroyHash(hHash);
            hHash = 0;
            v25 = BCryptCreateHash(hAlgorithm, &hHash, pbHashObject, cbHashObject, v14, v13, 0);
            v18 = v25;
            if ( v25 < 0 )
              goto LABEL_66;
            v29 = hHash;
            v30 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              WPP_SF_qqdD(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, v28, hHash, pbOutput, cbOutput, 0);
              v30 = WPP_GLOBAL_Control;
            }
            if ( !v29 || *v29 < 0x28u || v29[1] != 1431655763 )
              break;
            v18 = (*(__int64 (__fastcall **)(_QWORD, PUCHAR, _QWORD, _QWORD))(*((_QWORD *)v29 + 1) + 96LL))(
                    *((_QWORD *)v29 + 2),
                    pbOutput,
                    cbOutput,
                    0);
            if ( v18 < 0 )
            {
              v30 = WPP_GLOBAL_Control;
              goto LABEL_50;
            }
            v31 = hHash;
            v32 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              WPP_SF_qqdD(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, v28, hHash, pbOutput, cbOutput, 0);
              v32 = WPP_GLOBAL_Control;
            }
            if ( !v31 || *v31 < 0x28u || v31[1] != 1431655763 )
            {
              v18 = -1073741816;
              LOBYTE(v35) = 8;
              if ( v32 == &WPP_GLOBAL_Control )
                goto LABEL_53;
              if ( (*((_BYTE *)v32 + 28) & 1) != 0 )
              {
                WPP_SF_sDsd(
                  v32[2],
                  v27,
                  v28,
                  (unsigned int)"Status",
                  8,
                  (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
                  245);
                goto LABEL_41;
              }
LABEL_46:
              if ( v32 != &WPP_GLOBAL_Control && (*((_BYTE *)v32 + 28) & 1) != 0 )
                WPP_SF_sDsd(
                  v32[2],
                  v27,
                  v28,
                  (unsigned int)"Status",
                  v35,
                  (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
                  51);
              goto LABEL_53;
            }
            v33 = *((_QWORD *)v31 + 1);
            v34 = (*(__int64 (__fastcall **)(_QWORD, PUCHAR, _QWORD, _QWORD))(v33 + 104))(
                    *((_QWORD *)v31 + 2),
                    pbOutput,
                    cbOutput,
                    0);
            v35 = v34;
            if ( v34 < 0 )
            {
              v32 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_sDsd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v27,
                  v28,
                  (unsigned int)"Status",
                  v34,
                  (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
                  255);
                v32 = WPP_GLOBAL_Control;
              }
              v18 = v35;
              goto LABEL_46;
            }
            if ( (*(_BYTE *)(v33 + 8) & 8) != 0 )
            {
              v39 = (*(__int64 (__fastcall **)(_QWORD, PUCHAR, _QWORD, _QWORD))(v33 + 96))(
                      *((_QWORD *)v31 + 3),
                      pbOutput,
                      cbOutput,
                      0);
              v35 = v39;
              if ( v39 < 0
                || (v39 = (*(__int64 (__fastcall **)(_QWORD, PUCHAR, _QWORD, _QWORD))(v33 + 104))(
                            *((_QWORD *)v31 + 3),
                            pbOutput,
                            cbOutput,
                            0),
                    v35 = v39,
                    v39 < 0) )
              {
                DebugTraceError((unsigned int)v39, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c");
                v18 = v35;
LABEL_41:
                v32 = WPP_GLOBAL_Control;
                goto LABEL_46;
              }
            }
            if ( cbOutput )
            {
              v36 = 0;
              if ( cbOutput < 8 || a11 <= &pbOutput[cbOutput - 1] && &a11[cbOutput - 1] >= pbOutput )
                goto LABEL_74;
              if ( cbOutput < 0x40 )
                goto LABEL_75;
              do
              {
                *(__m128 *)&a11[v36] = _mm_xor_ps(
                                         (__m128)_mm_loadu_si128((const __m128i *)&pbOutput[v36]),
                                         (__m128)_mm_loadu_si128((const __m128i *)&a11[v36]));
                *(__m128 *)&a11[(unsigned int)(v36 + 16)] = _mm_xor_ps(
                                                              (__m128)_mm_loadu_si128((const __m128i *)&pbOutput[(unsigned int)(v36 + 16)]),
                                                              (__m128)_mm_loadu_si128((const __m128i *)&a11[(unsigned int)(v36 + 16)]));
                *(__m128 *)&a11[(unsigned int)(v36 + 32)] = _mm_xor_ps(
                                                              (__m128)_mm_loadu_si128((const __m128i *)&pbOutput[(unsigned int)(v36 + 32)]),
                                                              (__m128)_mm_loadu_si128((const __m128i *)&a11[(unsigned int)(v36 + 32)]));
                v37 = (unsigned int)(v36 + 48);
                v36 = (unsigned int)(v36 + 64);
                *(__m128 *)&a11[v37] = _mm_xor_ps(
                                         (__m128)_mm_loadu_si128((const __m128i *)&pbOutput[v37]),
                                         (__m128)_mm_loadu_si128((const __m128i *)&a11[v37]));
              }
              while ( (unsigned int)v36 < (cbOutput & 0xFFFFFFC0) );
              if ( (cbOutput & 0x3F) >= 8 )
              {
LABEL_75:
                do
                {
                  *(_QWORD *)&a11[v36] ^= *(_QWORD *)&pbOutput[v36];
                  v36 = (unsigned int)(v36 + 8);
                }
                while ( (unsigned int)v36 < (cbOutput & 0xFFFFFFF8) );
              }
              if ( (unsigned int)v36 < cbOutput )
              {
LABEL_74:
                do
                {
                  a11[v36] ^= pbOutput[v36];
                  v36 = (unsigned int)(v36 + 1);
                }
                while ( (unsigned int)v36 < cbOutput );
              }
            }
            v13 = cbSecret;
            v14 = pbSecret;
          }
          if ( v30 != &WPP_GLOBAL_Control && (*((_BYTE *)v30 + 28) & 1) != 0 )
          {
            WPP_SF_sDsd(
              v30[2],
              v27,
              v28,
              (unsigned int)"Status",
              8,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
              211);
            v30 = WPP_GLOBAL_Control;
          }
          v18 = -1073741816;
LABEL_50:
          if ( v30 != &WPP_GLOBAL_Control && (*((_BYTE *)v30 + 28) & 1) != 0 )
            WPP_SF_sDsd(
              v30[2],
              v27,
              v28,
              (unsigned int)"Status",
              v18,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
              41);
        }
      }
    }
  }
LABEL_53:
  if ( hHash )
    BCryptDestroyHash(hHash);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x180005470  mov     r11, rsp
0x180005473  mov     [r11+18h], r8d
0x180005477  mov     [r11+10h], rdx
0x18000547b  mov     [r11+8], rcx
0x18000547f  push    rdi
0x180005480  sub     rsp, 80h
0x180005487  mov     [r11+20h], rbx
0x18000548b  mov     rax, rcx
0x18000548e  xor     ecx, ecx
0x180005490  mov     [r11-10h], rbp
0x180005494  mov     [rsp+88h+dwFlags], ecx; dwFlags
0x180005498  mov     rbx, r9
0x18000549b  mov     r9d, [rsp+88h+cbHashObject]; cbHashObject
0x1800054a3  mov     ebp, r8d
0x1800054a6  mov     [r11-60h], r8d
0x1800054aa  mov     r8, [rsp+88h+pbHashObject]; pbHashObject
0x1800054b2  mov     [r11-28h], r13
0x1800054b6  mov     [r11-30h], r14
0x1800054ba  mov     r14, rdx
0x1800054bd  mov     [r11-68h], rdx
0x1800054c1  lea     rdx, [r11-40h]; phHash
0x1800054c5  mov     [r11-40h], rcx
0x1800054c9  mov     rcx, rax; hAlgorithm
0x1800054cc  call    BCryptCreateHash
0x1800054d1  mov     edi, eax
0x1800054d3  test    eax, eax
0x1800054d5  js      loc_1800059A3
0x1800054db  mov     r8d, [rsp+88h+cbInput]; cbInput
0x1800054e3  xor     r9d, r9d; dwFlags
0x1800054e6  mov     rcx, [rsp+88h+hHash]; hHash
0x1800054eb  mov     rdx, rbx; pbInput
0x1800054ee  call    BCryptHashData
0x1800054f3  mov     edi, eax
0x1800054f5  test    eax, eax
0x1800054f7  js      loc_180005978
0x1800054fd  mov     ecx, [rsp+88h+arg_30]
0x180005504  lea     rdx, [rsp+88h+pbInput]; pbInput
0x180005509  mov     eax, ecx
0x18000550b  mov     [rsp+88h+var_45], cl
0x18000550f  shr     eax, 18h
0x180005512  xor     r9d, r9d; dwFlags
0x180005515  mov     [rsp+88h+pbInput], al
0x180005519  mov     r8d, 4; cbInput
0x18000551f  mov     eax, ecx
0x180005521  shr     eax, 10h
0x180005524  mov     [rsp+88h+var_47], al
0x180005528  mov     eax, ecx
0x18000552a  mov     rcx, [rsp+88h+hHash]; hHash
0x18000552f  shr     eax, 8
0x180005532  mov     [rsp+88h+var_46], al
0x180005536  call    BCryptHashData
0x18000553b  mov     edi, eax
0x18000553d  test    eax, eax
0x18000553f  js      loc_180005935
0x180005545  mov     ebx, [rsp+88h+cbOutput]
0x18000554c  xor     r9d, r9d; dwFlags
0x18000554f  mov     rcx, [rsp+88h+hHash]; hHash
0x180005554  mov     r8d, ebx; cbOutput
0x180005557  mov     [rsp+88h+var_18], rsi
0x18000555c  mov     rsi, [rsp+88h+pbOutput]
0x180005564  mov     rdx, rsi; pbOutput
0x180005567  call    BCryptFinishHash
0x18000556c  mov     edi, eax
0x18000556e  test    eax, eax
0x180005570  js      loc_1800059CE
0x180005576  mov     [rsp+88h+var_20], r12
0x18000557b  mov     r8d, ebx; Size
0x18000557e  mov     r12, [rsp+88h+arg_50]
0x180005586  mov     rdx, rsi; Src
0x180005589  mov     rcx, r12; void *
0x18000558c  mov     [rsp+88h+var_38], r15
0x180005591  call    memcpy_0
0x180005596  mov     r15d, 1
0x18000559c  lea     r13, WPP_GLOBAL_Control
0x1800055a3  nop     dword ptr [rax+00h]
0x1800055a7  nop     word ptr [rax+rax+00000000h]
0x1800055b0  cmp     r15, [rsp+88h+arg_28]
0x1800055b8  jnb     loc_18000592A
0x1800055be  mov     rcx, [rsp+88h+hHash]; hHash
0x1800055c3  call    BCryptDestroyHash
0x1800055c8  mov     r9d, [rsp+88h+cbHashObject]; cbHashObject
0x1800055d0  lea     rdx, [rsp+88h+hHash]; phHash
0x1800055d5  mov     r8, [rsp+88h+pbHashObject]; pbHashObject
0x1800055dd  xor     eax, eax
0x1800055df  mov     rcx, [rsp+88h+hAlgorithm]; hAlgorithm
0x1800055e7  mov     [rsp+88h+dwFlags], eax; dwFlags
0x1800055eb  mov     [rsp+88h+cbSecret], ebp; cbSecret
0x1800055ef  mov     [rsp+88h+pbSecret], r14; pbSecret
0x1800055f4  mov     [rsp+88h+hHash], rax
0x1800055f9  call    BCryptCreateHash
0x1800055fe  mov     edi, eax
0x180005600  test    eax, eax
0x180005602  js      loc_180005AD5
0x180005608  mov     rdi, [rsp+88h+hHash]
0x18000560d  mov     rcx, cs:WPP_GLOBAL_Control
0x180005614  cmp     rcx, r13
0x180005617  jz      short loc_180005623
0x180005619  test    byte ptr [rcx+1Ch], 4
0x18000561d  jnz     loc_1800059EE
0x180005623  test    rdi, rdi
0x180005626  jz      loc_1800057BC
0x18000562c  cmp     dword ptr [rdi], 28h ; '('
0x18000562f  jb      loc_1800057BC
0x180005635  cmp     dword ptr [rdi+4], 55555553h
0x18000563c  jnz     loc_1800057BC
0x180005642  mov     rax, [rdi+8]
0x180005646  xor     r9d, r9d
0x180005649  mov     rcx, [rdi+10h]
0x18000564d  mov     r8d, ebx
0x180005650  mov     rdx, rsi
0x180005653  mov     rax, [rax+60h]
0x180005657  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000565c  mov     edi, eax
0x18000565e  test    eax, eax
0x180005660  js      loc_1800058B4
0x180005666  mov     rdi, [rsp+88h+hHash]
0x18000566b  mov     rcx, cs:WPP_GLOBAL_Control
0x180005672  cmp     rcx, r13
0x180005675  jz      short loc_180005681
0x180005677  test    byte ptr [rcx+1Ch], 4
0x18000567b  jnz     loc_180005A1C
0x180005681  test    rdi, rdi
0x180005684  jz      loc_180005804
0x18000568a  cmp     dword ptr [rdi], 28h ; '('
0x18000568d  jb      loc_180005804
0x180005693  cmp     dword ptr [rdi+4], 55555553h
0x18000569a  jnz     loc_180005804
0x1800056a0  mov     rbp, [rdi+8]
0x1800056a4  xor     r9d, r9d
0x1800056a7  mov     rcx, [rdi+10h]
0x1800056ab  mov     r8d, ebx
0x1800056ae  mov     rdx, rsi
0x1800056b1  mov     rax, [rbp+68h]
0x1800056b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056ba  mov     r14d, eax
0x1800056bd  test    eax, eax
0x1800056bf  js      loc_180005850
0x1800056c5  test    byte ptr [rbp+8], 8
0x1800056c9  jnz     loc_180005A4A
0x1800056cf  test    ebx, ebx
0x1800056d1  jz      loc_1800057A5
0x1800056d7  xor     edx, edx
0x1800056d9  cmp     ebx, 8
0x1800056dc  jb      loc_180005795
0x1800056e2  lea     eax, [rbx-1]
0x1800056e5  mov     ecx, eax
0x1800056e7  add     rax, rsi
0x1800056ea  cmp     r12, rax
0x1800056ed  ja      short loc_1800056FC
0x1800056ef  lea     rax, [rcx+r12]
0x1800056f3  cmp     rax, rsi
0x1800056f6  jnb     loc_180005795
0x1800056fc  cmp     ebx, 40h ; '@'
0x1800056ff  jb      short loc_180005771
0x180005701  mov     r8d, ebx
0x180005704  and     r8d, 0FFFFFFC0h
0x180005708  movdqu  xmm0, xmmword ptr [rdx+r12]
0x18000570e  lea     eax, [rdx+10h]
0x180005711  movdqu  xmm1, xmmword ptr [rdx+rsi]
0x180005716  xorps   xmm1, xmm0
0x180005719  movdqu  xmmword ptr [rdx+r12], xmm1
0x18000571f  movdqu  xmm0, xmmword ptr [rax+r12]
0x180005725  movdqu  xmm1, xmmword ptr [rax+rsi]
0x18000572a  xorps   xmm1, xmm0
0x18000572d  movdqu  xmmword ptr [rax+r12], xmm1
0x180005733  lea     eax, [rdx+20h]
0x180005736  movdqu  xmm0, xmmword ptr [rax+r12]
0x18000573c  movdqu  xmm1, xmmword ptr [rax+rsi]
0x180005741  xorps   xmm1, xmm0
0x180005744  movdqu  xmmword ptr [rax+r12], xmm1
0x18000574a  lea     eax, [rdx+30h]
0x18000574d  add     edx, 40h ; '@'
0x180005750  movdqu  xmm0, xmmword ptr [rax+r12]
0x180005756  movdqu  xmm1, xmmword ptr [rax+rsi]
0x18000575b  xorps   xmm1, xmm0
0x18000575e  movdqu  xmmword ptr [rax+r12], xmm1
0x180005764  cmp     edx, r8d
0x180005767  jb      short loc_180005708
0x180005769  mov     eax, ebx
0x18000576b  and     al, 3Fh
0x18000576d  cmp     al, 8
0x18000576f  jb      short loc_180005791
0x180005771  mov     ecx, ebx
0x180005773  and     ecx, 0FFFFFFF8h
0x180005776  movq    xmm0, qword ptr [rdx+r12]
0x18000577c  movq    xmm1, qword ptr [rdx+rsi]
0x180005781  xorps   xmm1, xmm0
0x180005784  movq    qword ptr [rdx+r12], xmm1
0x18000578a  add     edx, 8
0x18000578d  cmp     edx, ecx
0x18000578f  jb      short loc_180005776
0x180005791  cmp     edx, ebx
0x180005793  jnb     short loc_1800057A5
0x180005795  movzx   eax, byte ptr [rdx+rsi]
0x180005799  lea     rcx, [rdx+r12]
0x18000579d  xor     [rcx], al
0x18000579f  inc     edx
0x1800057a1  cmp     edx, ebx
0x1800057a3  jb      short loc_180005795
0x1800057a5  mov     ebp, [rsp+88h+arg_10]
0x1800057ac  inc     r15
0x1800057af  mov     r14, [rsp+88h+arg_8]
0x1800057b7  jmp     loc_1800055B0
0x1800057bc  lea     rbx, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800057c3  cmp     rcx, r13
0x1800057c6  jz      short loc_1800057FA
0x1800057c8  test    byte ptr [rcx+1Ch], 1
0x1800057cc  jz      short loc_1800057FA
0x1800057ce  mov     rcx, [rcx+10h]
0x1800057d2  lea     r9, aStatus; "Status"
0x1800057d9  mov     [rsp+88h+dwFlags], 17D3h
0x1800057e1  mov     qword ptr [rsp+88h+cbSecret], rbx
0x1800057e6  mov     dword ptr [rsp+88h+pbSecret], 0C0000008h
0x1800057ee  call    WPP_SF_sDsd
0x1800057f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800057fa  mov     edi, 0C0000008h
0x1800057ff  jmp     loc_1800058C2
0x180005804  mov     edi, 0C0000008h
0x180005809  mov     r14d, edi
0x18000580c  lea     rbx, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005813  cmp     rcx, r13
0x180005816  jz      loc_1800058EE
0x18000581c  test    byte ptr [rcx+1Ch], 1
0x180005820  jz      short loc_180005895
0x180005822  mov     rcx, [rcx+10h]
0x180005826  lea     r9, aStatus; "Status"
0x18000582d  mov     [rsp+88h+dwFlags], 17F5h
0x180005835  mov     qword ptr [rsp+88h+cbSecret], rbx
0x18000583a  mov     dword ptr [rsp+88h+pbSecret], 0C0000008h
0x180005842  call    WPP_SF_sDsd
0x180005847  mov     rcx, cs:WPP_GLOBAL_Control
0x18000584e  jmp     short loc_180005895
0x180005850  mov     rcx, cs:WPP_GLOBAL_Control
0x180005857  lea     rbx, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000585e  cmp     rcx, r13
0x180005861  jz      short loc_180005892
0x180005863  test    byte ptr [rcx+1Ch], 1
0x180005867  jz      short loc_180005892
0x180005869  mov     rcx, [rcx+10h]
0x18000586d  lea     r9, aStatus; "Status"
0x180005874  mov     [rsp+88h+dwFlags], 17FFh
0x18000587c  mov     qword ptr [rsp+88h+cbSecret], rbx
0x180005881  mov     dword ptr [rsp+88h+pbSecret], r14d
0x180005886  call    WPP_SF_sDsd
0x18000588b  mov     rcx, cs:WPP_GLOBAL_Control
0x180005892  mov     edi, r14d
0x180005895  cmp     rcx, r13
0x180005898  jz      short loc_1800058EE
0x18000589a  test    byte ptr [rcx+1Ch], 1
0x18000589e  jz      short loc_1800058EE
0x1800058a0  mov     [rsp+88h+dwFlags], 1D33h
0x1800058a8  mov     qword ptr [rsp+88h+cbSecret], rbx
0x1800058ad  mov     dword ptr [rsp+88h+pbSecret], r14d
0x1800058b2  jmp     short loc_1800058DE
0x1800058b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800058bb  lea     rbx, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800058c2  cmp     rcx, r13
0x1800058c5  jz      short loc_1800058EE
0x1800058c7  test    byte ptr [rcx+1Ch], 1
0x1800058cb  jz      short loc_1800058EE
0x1800058cd  mov     [rsp+88h+dwFlags], 1D29h
0x1800058d5  mov     qword ptr [rsp+88h+cbSecret], rbx
0x1800058da  mov     dword ptr [rsp+88h+pbSecret], edi
0x1800058de  mov     rcx, [rcx+10h]
0x1800058e2  lea     r9, aStatus; "Status"
0x1800058e9  call    WPP_SF_sDsd
0x1800058ee  mov     r12, [rsp+88h+var_20]
0x1800058f3  mov     r15, [rsp+88h+var_38]
0x1800058f8  mov     rsi, [rsp+88h+var_18]
0x1800058fd  mov     rcx, [rsp+88h+hHash]; hHash
0x180005902  mov     r14, [rsp+88h+var_30]
0x180005907  mov     r13, [rsp+88h+var_28]
0x18000590c  mov     rbp, [rsp+88h+var_10]
0x180005911  mov     rbx, [rsp+88h+arg_18]
0x180005919  test    rcx, rcx
0x18000591c  jnz     short loc_18000592E
0x18000591e  mov     eax, edi
0x180005920  add     rsp, 80h
0x180005927  pop     rdi
0x180005928  retn
0x18000592a  xor     edi, edi
0x18000592c  jmp     short loc_1800058EE
0x18000592e  call    BCryptDestroyHash
0x180005933  jmp     short loc_18000591E
0x180005935  mov     rcx, cs:WPP_GLOBAL_Control
0x18000593c  lea     r13, WPP_GLOBAL_Control
0x180005943  cmp     rcx, r13
0x180005946  jz      short loc_1800058FD
0x180005948  test    byte ptr [rcx+1Ch], 1
0x18000594c  jz      short loc_1800058FD
0x18000594e  mov     [rsp+88h+dwFlags], 1D00h
0x180005956  mov     rcx, [rcx+10h]
0x18000595a  lea     rbx, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005961  mov     qword ptr [rsp+88h+cbSecret], rbx
0x180005966  lea     r9, aStatus; "Status"
0x18000596d  mov     dword ptr [rsp+88h+pbSecret], eax
0x180005971  call    WPP_SF_sDsd
0x180005976  jmp     short loc_1800058FD
0x180005978  mov     rcx, cs:WPP_GLOBAL_Control
0x18000597f  lea     r13, WPP_GLOBAL_Control
  ... truncated ...
```
