# computeOMAC

- ea: `0x180007d80`
- end: `0x180008181`
- name: `computeOMAC`
- size: `1025`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800089fc`

## callees

- `0x180007d80`
- `0x180009672`
- `0x1800096b0`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180007e61`
- `ole32!CoTaskMemAlloc` at `0x180007e61`
- `ole32!CoTaskMemFree` at `0x180008152`
- `ole32!CoTaskMemFree` at `0x180008152`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180007e10`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180007e10`
- `bcrypt!BCryptDestroyKey` at `0x180007fc5`
- `bcrypt!BCryptDestroyKey` at `0x18000812c`
- `bcrypt!BCryptDestroyKey` at `0x180007fc5`
- `bcrypt!BCryptDestroyKey` at `0x18000812c`
- `bcrypt!BCryptEncrypt` at `0x180007f33`
- `bcrypt!BCryptEncrypt` at `0x180008071`
- `bcrypt!BCryptEncrypt` at `0x18000810d`
- `bcrypt!BCryptEncrypt` at `0x180007f33`
- `bcrypt!BCryptEncrypt` at `0x180008071`
- `bcrypt!BCryptEncrypt` at `0x18000810d`
- `bcrypt!BCryptImportKey` at `0x180007ee5`
- `bcrypt!BCryptImportKey` at `0x180008012`
- `bcrypt!BCryptImportKey` at `0x180007ee5`
- `bcrypt!BCryptImportKey` at `0x180008012`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180008143`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180008143`
- `bcrypt!BCryptSetProperty` at `0x180007e9c`
- `bcrypt!BCryptSetProperty` at `0x180007e9c`
- `bcrypt!BCryptGetProperty` at `0x180007e48`
- `bcrypt!BCryptGetProperty` at `0x180007e48`

## pseudocode

```c
__int64 __fastcall computeOMAC(__int128 *a1, __m128 *a2, ULONG a3, UCHAR *a4)
{
  __int128 v7; // xmm0
  UCHAR *v8; // rsi
  NTSTATUS Property; // ebx
  unsigned int i; // eax
  __int64 v11; // r9
  __int64 v12; // r8
  __int8 v13; // dl
  bool v14; // cf
  unsigned int j; // eax
  __int64 v16; // r9
  __int64 v17; // r8
  __int8 v18; // dl
  __m128 v19; // xmm1
  ULONG v21; // [rsp+50h] [rbp-69h] BYREF
  ULONG pcbResult; // [rsp+54h] [rbp-65h] BYREF
  UCHAR pbOutput[4]; // [rsp+58h] [rbp-61h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+60h] [rbp-59h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+68h] [rbp-51h] BYREF
  __m128i v26; // [rsp+70h] [rbp-49h] BYREF
  __m128i v27; // [rsp+80h] [rbp-39h] BYREF
  UCHAR pbInput[4]; // [rsp+90h] [rbp-29h] BYREF
  int v29; // [rsp+94h] [rbp-25h]
  int v30; // [rsp+98h] [rbp-21h]
  __int128 v31; // [rsp+9Ch] [rbp-1Dh]
  UCHAR v32[16]; // [rsp+B0h] [rbp-9h] BYREF

  *(_DWORD *)pbInput = 1296188491;
  phAlgorithm = 0;
  v26 = 0;
  *(_OWORD *)v32 = 0;
  v7 = *a1;
  v30 = 16;
  phKey = 0;
  *(_DWORD *)pbOutput = 0;
  pcbResult = 0;
  v8 = 0;
  v21 = 0;
  v27 = 0;
  v29 = 1;
  v31 = v7;
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"AES", L"Microsoft Primitive Provider", 0);
  if ( Property >= 0 )
  {
    Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
    if ( Property >= 0 )
    {
      v8 = (UCHAR *)CoTaskMemAlloc(*(unsigned int *)pbOutput);
      if ( v8 )
      {
        Property = BCryptSetProperty(phAlgorithm, L"ChainingMode", (PUCHAR)L"ChainingModeCBC", 0x20u, 0);
        if ( Property >= 0 )
        {
          Property = BCryptImportKey(phAlgorithm, 0, L"KeyDataBlob", &phKey, v8, *(ULONG *)pbOutput, pbInput, 0x1Cu, 0);
          if ( Property >= 0 )
          {
            v21 = 16;
            Property = BCryptEncrypt(phKey, v32, 0x10u, 0, 0, 0, v32, 0x10u, &v21, 0);
            if ( Property >= 0 )
            {
              for ( i = 0; i < 0x10; ++i )
              {
                v11 = i;
                v12 = i + 1;
                v13 = 2 * v32[i];
                v14 = i < 0xF;
                v26.m128i_i8[i] = v13;
                if ( v14 )
                  v26.m128i_i8[v11] = v13 | (v32[v12] >> 7);
              }
              if ( (v32[0] & 0x80u) != 0 )
                v26.m128i_i8[15] ^= 0x87u;
              for ( j = 0; j < 0x10; ++j )
              {
                v16 = j;
                v17 = j + 1;
                v18 = 2 * v26.m128i_i8[j];
                v14 = j < 0xF;
                v27.m128i_i8[j] = v18;
                if ( v14 )
                  v27.m128i_i8[v16] = v18 | ((unsigned __int8)v26.m128i_i8[v17] >> 7);
              }
              if ( v26.m128i_i8[0] < 0 )
                v27.m128i_i8[15] ^= 0x87u;
              Property = BCryptDestroyKey(phKey);
              if ( Property >= 0 )
              {
                phKey = 0;
                Property = BCryptImportKey(
                             phAlgorithm,
                             0,
                             L"KeyDataBlob",
                             &phKey,
                             v8,
                             *(ULONG *)pbOutput,
                             pbInput,
                             0x1Cu,
                             0);
                if ( Property >= 0 )
                {
                  pcbResult = a3;
                  while ( 1 )
                  {
                    v21 = 0;
                    if ( a3 <= 0x10 )
                      break;
                    *(__m128 *)v32 = *a2;
                    Property = BCryptEncrypt(phKey, v32, 0x10u, 0, 0, 0, v32, 0x10u, &v21, 0);
                    if ( Property >= 0 )
                    {
                      ++a2;
                      a3 = pcbResult - 16;
                      pcbResult = a3;
                      if ( a3 )
                        continue;
                    }
                    goto LABEL_32;
                  }
                  if ( a3 == 16 )
                  {
                    *(__m128 *)v32 = _mm_xor_ps((__m128)_mm_loadu_si128(&v26), *a2);
                  }
                  else
                  {
                    *(_OWORD *)v32 = 0;
                    memcpy_0(v32, a2, a3);
                    v19 = (__m128)_mm_loadu_si128(&v27);
                    v32[a3] = 0x80;
                    *(__m128 *)v32 = _mm_xor_ps(v19, (__m128)_mm_loadu_si128((const __m128i *)v32));
                  }
                  Property = BCryptEncrypt(phKey, v32, 0x10u, 0, 0, 0, a4, 0x10u, &v21, 0);
                  if ( Property >= 0 )
                    pcbResult = 0;
                }
              }
            }
          }
        }
      }
      else
      {
        Property = -2147024882;
      }
    }
  }
LABEL_32:
  if ( phKey )
    BCryptDestroyKey(phKey);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  CoTaskMemFree(v8);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x180007d80  push    rbp
0x180007d82  push    rbx
0x180007d83  push    rsi
0x180007d84  push    rdi
0x180007d85  push    r12
0x180007d87  push    r13
0x180007d89  push    r14
0x180007d8b  push    r15
0x180007d8d  lea     rbp, [rsp-1Fh]
0x180007d92  sub     rsp, 0D8h
0x180007d99  mov     rax, cs:__security_cookie
0x180007da0  xor     rax, rsp
0x180007da3  mov     [rbp+57h+var_50], rax
0x180007da7  xor     r12d, r12d
0x180007daa  mov     dword ptr [rbp+57h+var_80], 4D42444Bh
0x180007db1  xorps   xmm0, xmm0
0x180007db4  mov     [rbp+57h+phAlgorithm], r12
0x180007db8  movups  [rbp+57h+var_A0], xmm0
0x180007dbc  mov     r15, r9
0x180007dbf  mov     edi, r8d
0x180007dc2  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x180007dc6  lea     r13d, [r12+10h]
0x180007dcb  mov     r14, rdx
0x180007dce  movups  xmm0, xmmword ptr [rcx]
0x180007dd1  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x180007dd8  xorps   xmm1, xmm1
0x180007ddb  mov     [rbp+57h+var_78], r13d
0x180007ddf  xor     r9d, r9d; dwFlags
0x180007de2  mov     [rbp+57h+phKey], r12
0x180007de6  lea     rdx, aAes; "AES"
0x180007ded  mov     dword ptr [rbp+57h+pbOutput], r12d
0x180007df1  lea     rcx, [rbp+57h+phAlgorithm]; phAlgorithm
0x180007df5  mov     [rbp+57h+var_BC], r12d
0x180007df9  mov     esi, r12d
0x180007dfc  mov     [rbp+57h+var_C0], r12d
0x180007e00  movups  [rbp+57h+var_90], xmm1
0x180007e04  mov     [rbp+57h+var_7C], 1
0x180007e0b  movdqu  [rbp+57h+var_74], xmm0
0x180007e10  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180007e17  nop     dword ptr [rax+rax+00h]
0x180007e1c  mov     ebx, eax
0x180007e1e  test    eax, eax
0x180007e20  js      loc_180008123
0x180007e26  mov     rcx, [rbp+57h+phAlgorithm]; hObject
0x180007e2a  lea     rax, [rbp+57h+var_BC]
0x180007e2e  mov     [rsp+110h+dwFlags], r12d; dwFlags
0x180007e33  lea     r9d, [r12+4]; cbOutput
0x180007e38  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x180007e3c  mov     [rsp+110h+pcbResult], rax; pcbResult
0x180007e41  lea     rdx, pszProperty; "ObjectLength"
0x180007e48  call    cs:__imp_BCryptGetProperty
0x180007e4f  nop     dword ptr [rax+rax+00h]
0x180007e54  mov     ebx, eax
0x180007e56  test    eax, eax
0x180007e58  js      loc_180008123
0x180007e5e  mov     ecx, dword ptr [rbp+57h+pbOutput]; cb
0x180007e61  call    cs:__imp_CoTaskMemAlloc
0x180007e68  nop     dword ptr [rax+rax+00h]
0x180007e6d  mov     rsi, rax
0x180007e70  test    rax, rax
0x180007e73  jnz     short loc_180007E7F
0x180007e75  mov     ebx, 8007000Eh
0x180007e7a  jmp     loc_180008123
0x180007e7f  mov     rcx, [rbp+57h+phAlgorithm]; hObject
0x180007e83  lea     r8, pbInput; "ChainingModeCBC"
0x180007e8a  mov     r9d, 20h ; ' '; cbInput
0x180007e90  mov     dword ptr [rsp+110h+pcbResult], r12d; dwFlags
0x180007e95  lea     rdx, aChainingmode; "ChainingMode"
0x180007e9c  call    cs:__imp_BCryptSetProperty
0x180007ea3  nop     dword ptr [rax+rax+00h]
0x180007ea8  mov     ebx, eax
0x180007eaa  test    eax, eax
0x180007eac  js      loc_180008123
0x180007eb2  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x180007eb6  lea     rax, [rbp+57h+var_80]
0x180007eba  mov     [rsp+110h+var_D0], r12d; dwFlags
0x180007ebf  lea     r9, [rbp+57h+phKey]; phKey
0x180007ec3  mov     [rsp+110h+cbInput], 1Ch; cbInput
0x180007ecb  lea     r8, pszBlobType; "KeyDataBlob"
0x180007ed2  mov     [rsp+110h+pbInput], rax; pbInput
0x180007ed7  xor     edx, edx; hImportKey
0x180007ed9  mov     eax, dword ptr [rbp+57h+pbOutput]
0x180007edc  mov     [rsp+110h+dwFlags], eax; cbKeyObject
0x180007ee0  mov     [rsp+110h+pcbResult], rsi; pbKeyObject
0x180007ee5  call    cs:__imp_BCryptImportKey
0x180007eec  nop     dword ptr [rax+rax+00h]
0x180007ef1  mov     ebx, eax
0x180007ef3  test    eax, eax
0x180007ef5  js      loc_180008123
0x180007efb  mov     rcx, [rbp+57h+phKey]; hKey
0x180007eff  lea     rax, [rbp+57h+var_C0]
0x180007f03  mov     [rsp+110h+var_C8], r12d; dwFlags
0x180007f08  lea     rdx, [rbp+57h+var_60]; pbInput
0x180007f0c  mov     qword ptr [rsp+110h+var_D0], rax; pcbResult
0x180007f11  xor     r9d, r9d; pPaddingInfo
0x180007f14  mov     [rsp+110h+cbInput], r13d; cbOutput
0x180007f19  lea     rax, [rbp+57h+var_60]
0x180007f1d  mov     [rsp+110h+pbInput], rax; pbOutput
0x180007f22  mov     r8d, r13d; cbInput
0x180007f25  mov     [rsp+110h+dwFlags], r12d; cbIV
0x180007f2a  mov     [rsp+110h+pcbResult], r12; pbIV
0x180007f2f  mov     [rbp+57h+var_C0], r13d
0x180007f33  call    cs:__imp_BCryptEncrypt
0x180007f3a  nop     dword ptr [rax+rax+00h]
0x180007f3f  mov     ebx, eax
0x180007f41  test    eax, eax
0x180007f43  js      loc_180008123
0x180007f49  mov     eax, r12d
0x180007f4c  mov     r9d, eax
0x180007f4f  lea     r8d, [rax+1]
0x180007f53  mov     dl, [rbp+r9+57h+var_60]
0x180007f58  add     dl, dl
0x180007f5a  cmp     eax, 0Fh
0x180007f5d  mov     byte ptr [rbp+r9+57h+var_A0], dl
0x180007f62  mov     eax, r8d
0x180007f65  jnb     short loc_180007F76
0x180007f67  mov     cl, [rbp+r8+57h+var_60]
0x180007f6c  shr     cl, 7
0x180007f6f  or      cl, dl
0x180007f71  mov     byte ptr [rbp+r9+57h+var_A0], cl
0x180007f76  cmp     eax, r13d
0x180007f79  jb      short loc_180007F4C
0x180007f7b  cmp     [rbp+57h+var_60], r12b
0x180007f7f  jge     short loc_180007F85
0x180007f81  xor     byte ptr [rbp+57h+var_A0+0Fh], 87h
0x180007f85  mov     eax, r12d
0x180007f88  mov     r9d, eax
0x180007f8b  lea     r8d, [rax+1]
0x180007f8f  mov     dl, byte ptr [rbp+r9+57h+var_A0]
0x180007f94  add     dl, dl
0x180007f96  cmp     eax, 0Fh
0x180007f99  mov     byte ptr [rbp+r9+57h+var_90], dl
0x180007f9e  mov     eax, r8d
0x180007fa1  jnb     short loc_180007FB2
0x180007fa3  mov     cl, byte ptr [rbp+r8+57h+var_A0]
0x180007fa8  shr     cl, 7
0x180007fab  or      cl, dl
0x180007fad  mov     byte ptr [rbp+r9+57h+var_90], cl
0x180007fb2  cmp     eax, r13d
0x180007fb5  jb      short loc_180007F88
0x180007fb7  cmp     byte ptr [rbp+57h+var_A0], r12b
0x180007fbb  jge     short loc_180007FC1
0x180007fbd  xor     byte ptr [rbp+57h+var_90+0Fh], 87h
0x180007fc1  mov     rcx, [rbp+57h+phKey]; hKey
0x180007fc5  call    cs:__imp_BCryptDestroyKey
0x180007fcc  nop     dword ptr [rax+rax+00h]
0x180007fd1  mov     ebx, eax
0x180007fd3  test    eax, eax
0x180007fd5  js      loc_180008123
0x180007fdb  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x180007fdf  lea     rax, [rbp+57h+var_80]
0x180007fe3  mov     [rsp+110h+var_D0], r12d; dwFlags
0x180007fe8  lea     r9, [rbp+57h+phKey]; phKey
0x180007fec  mov     [rsp+110h+cbInput], 1Ch; cbInput
0x180007ff4  lea     r8, pszBlobType; "KeyDataBlob"
0x180007ffb  mov     [rsp+110h+pbInput], rax; pbInput
0x180008000  xor     edx, edx; hImportKey
0x180008002  mov     eax, dword ptr [rbp+57h+pbOutput]
0x180008005  mov     [rsp+110h+dwFlags], eax; cbKeyObject
0x180008009  mov     [rsp+110h+pcbResult], rsi; pbKeyObject
0x18000800e  mov     [rbp+57h+phKey], r12
0x180008012  call    cs:__imp_BCryptImportKey
0x180008019  nop     dword ptr [rax+rax+00h]
0x18000801e  mov     ebx, eax
0x180008020  test    eax, eax
0x180008022  js      loc_180008123
0x180008028  mov     [rbp+57h+var_BC], edi
0x18000802b  mov     [rbp+57h+var_C0], r12d
0x18000802f  cmp     edi, r13d
0x180008032  jbe     short loc_18000809C
0x180008034  movups  xmm0, xmmword ptr [r14]
0x180008038  lea     rax, [rbp+57h+var_C0]
0x18000803c  mov     rcx, [rbp+57h+phKey]; hKey
0x180008040  lea     rdx, [rbp+57h+var_60]; pbInput
0x180008044  mov     [rsp+110h+var_C8], r12d; dwFlags
0x180008049  xor     r9d, r9d; pPaddingInfo
0x18000804c  mov     qword ptr [rsp+110h+var_D0], rax; pcbResult
0x180008051  mov     r8d, r13d; cbInput
0x180008054  mov     [rsp+110h+cbInput], r13d; cbOutput
0x180008059  lea     rax, [rbp+57h+var_60]
0x18000805d  mov     [rsp+110h+pbInput], rax; pbOutput
0x180008062  mov     [rsp+110h+dwFlags], r12d; cbIV
0x180008067  mov     [rsp+110h+pcbResult], r12; pbIV
0x18000806c  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x180008071  call    cs:__imp_BCryptEncrypt
0x180008078  nop     dword ptr [rax+rax+00h]
0x18000807d  mov     ebx, eax
0x18000807f  test    eax, eax
0x180008081  js      loc_180008123
0x180008087  mov     edi, [rbp+57h+var_BC]
0x18000808a  add     r14, r13
0x18000808d  add     edi, 0FFFFFFF0h
0x180008090  mov     [rbp+57h+var_BC], edi
0x180008093  test    edi, edi
0x180008095  jnz     short loc_18000802B
0x180008097  jmp     loc_180008123
0x18000809c  jnz     short loc_1800080AE
0x18000809e  movdqu  xmm0, [rbp+57h+var_A0]
0x1800080a3  xorps   xmm0, xmmword ptr [r14]
0x1800080a7  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x1800080ac  jmp     short loc_1800080DD
0x1800080ae  xorps   xmm0, xmm0
0x1800080b1  mov     r8d, edi; Size
0x1800080b4  mov     rdx, r14; Src
0x1800080b7  mov     ebx, edi
0x1800080b9  lea     rcx, [rbp+57h+var_60]; void *
0x1800080bd  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x1800080c1  call    memcpy_0
0x1800080c6  movdqu  xmm1, [rbp+57h+var_90]
0x1800080cb  mov     [rbp+rbx+57h+var_60], 80h
0x1800080d0  movdqu  xmm0, xmmword ptr [rbp+57h+var_60]
0x1800080d5  xorps   xmm1, xmm0
0x1800080d8  movdqu  xmmword ptr [rbp+57h+var_60], xmm1
0x1800080dd  mov     rcx, [rbp+57h+phKey]; hKey
0x1800080e1  lea     rax, [rbp+57h+var_C0]
0x1800080e5  mov     [rsp+110h+var_C8], r12d; dwFlags
0x1800080ea  lea     rdx, [rbp+57h+var_60]; pbInput
0x1800080ee  mov     qword ptr [rsp+110h+var_D0], rax; pcbResult
0x1800080f3  xor     r9d, r9d; pPaddingInfo
0x1800080f6  mov     [rsp+110h+cbInput], r13d; cbOutput
0x1800080fb  mov     r8d, r13d; cbInput
0x1800080fe  mov     [rsp+110h+pbInput], r15; pbOutput
0x180008103  mov     [rsp+110h+dwFlags], r12d; cbIV
0x180008108  mov     [rsp+110h+pcbResult], r12; pbIV
0x18000810d  call    cs:__imp_BCryptEncrypt
0x180008114  nop     dword ptr [rax+rax+00h]
0x180008119  mov     ebx, eax
0x18000811b  test    eax, eax
0x18000811d  js      short loc_180008123
0x18000811f  mov     [rbp+57h+var_BC], r12d
0x180008123  mov     rcx, [rbp+57h+phKey]; hKey
0x180008127  test    rcx, rcx
0x18000812a  jz      short loc_180008138
0x18000812c  call    cs:__imp_BCryptDestroyKey
0x180008133  nop     dword ptr [rax+rax+00h]
0x180008138  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x18000813c  test    rcx, rcx
0x18000813f  jz      short loc_18000814F
0x180008141  xor     edx, edx; dwFlags
0x180008143  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18000814a  nop     dword ptr [rax+rax+00h]
0x18000814f  mov     rcx, rsi; pv
0x180008152  call    cs:__imp_CoTaskMemFree
0x180008159  nop     dword ptr [rax+rax+00h]
0x18000815e  mov     eax, ebx
0x180008160  mov     rcx, [rbp+57h+var_50]
0x180008164  xor     rcx, rsp; StackCookie
0x180008167  call    __security_check_cookie
0x18000816c  add     rsp, 0D8h
0x180008173  pop     r15
0x180008175  pop     r14
0x180008177  pop     r13
0x180008179  pop     r12
0x18000817b  pop     rdi
0x18000817c  pop     rsi
0x18000817d  pop     rbx
0x18000817e  pop     rbp
0x18000817f  retn
```
