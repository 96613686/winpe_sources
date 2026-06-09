# CtapCborDecodeDecryptDecompressLargeBlob

- ea: `0x1800e3290`
- end: `0x1800e355f`
- name: `CtapCborDecodeDecryptDecompressLargeBlob`
- size: `719`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800e3568`

## callees

- `0x180007f90`
- `0x18001cd78`
- `0x18002bbf4`
- `0x1800537a4`
- `0x1800d1560`
- `0x1800e3290`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800e33b0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800e34aa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800e33b0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800e34aa`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800e338b`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800e338b`
- `bcrypt!BCryptDestroyKey` at `0x1800e3517`
- `bcrypt!BCryptDestroyKey` at `0x1800e3517`
- `bcrypt!BCryptDecrypt` at `0x1800e3459`
- `bcrypt!BCryptDecrypt` at `0x1800e3459`
- `Cabinet!__imp_CreateDecompressor` at `0x1800e3494`
- `Cabinet!__imp_CreateDecompressor` at `0x1800e3494`
- `Cabinet!__imp_Decompress` at `0x1800e34de`
- `Cabinet!__imp_Decompress` at `0x1800e34de`
- `Cabinet!__imp_CloseDecompressor` at `0x1800e352f`
- `Cabinet!__imp_CloseDecompressor` at `0x1800e352f`

## pseudocode

```c
__int64 __fastcall CtapCborDecodeDecryptDecompressLargeBlob(int a1, UCHAR *a2, int a3, int a4, _DWORD *a5, _QWORD *a6)
{
  UCHAR *v9; // r14
  HLOCAL v10; // rsi
  unsigned int v11; // eax
  unsigned int *v12; // rdi
  unsigned int NonzeroLastError; // eax
  unsigned int v14; // ebx
  int v15; // eax
  int v16; // ebx
  UCHAR *v17; // rax
  int v18; // r13d
  __int64 v19; // rdx
  ULONG pcbResult; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v22; // [rsp+54h] [rbp-ACh] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v24; // [rsp+60h] [rbp-A0h] BYREF
  void *v25; // [rsp+68h] [rbp-98h] BYREF
  __int64 v26; // [rsp+70h] [rbp-90h]
  PUCHAR pbSecret; // [rsp+78h] [rbp-88h]
  char v28; // [rsp+80h] [rbp-80h] BYREF
  _DWORD pPaddingInfo[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v30; // [rsp+98h] [rbp-68h]
  unsigned int v31; // [rsp+A0h] [rbp-60h]
  __int64 *v32; // [rsp+A8h] [rbp-58h]
  int v33; // [rsp+B0h] [rbp-50h]
  __int64 v34; // [rsp+B8h] [rbp-48h]
  int v35; // [rsp+C0h] [rbp-40h]
  __int64 v36; // [rsp+F0h] [rbp-10h] BYREF
  int v37; // [rsp+F8h] [rbp-8h]

  pbSecret = a2;
  v25 = 0;
  phKey = 0;
  memset_0(pPaddingInfo, 0, 0x58u);
  pcbResult = 0;
  v9 = 0;
  v24 = 0;
  v10 = 0;
  v26 = 0;
  v36 = 0;
  v37 = 0;
  if ( a5 && a6 )
  {
    *a5 = 0;
    *a6 = 0;
  }
  v11 = CtapCborDecodeEncryptedLargeBlob(a3, a4, (unsigned int)&v25, (unsigned int)&v28, (__int64)&v22);
  v12 = (unsigned int *)v25;
  if ( v11 )
  {
    NonzeroLastError = CtapCborErrorToWin32Error(v11);
LABEL_6:
    v14 = NonzeroLastError;
    goto LABEL_25;
  }
  if ( a1 != 32 )
    goto LABEL_8;
  v14 = BCryptGenerateSymmetricKey((BCRYPT_ALG_HANDLE)0x1E1, &phKey, 0, 0, pbSecret, 0x20u, 0);
  if ( !v14 )
  {
    v15 = *v12;
    if ( *v12 >= 0x10 )
    {
      v16 = v15 - 14;
      v22 = v15 - 14;
      v17 = (UCHAR *)LocalAlloc(0x40u, (unsigned int)(v15 - 14));
      v9 = v17;
      if ( !v17 )
      {
LABEL_12:
        NonzeroLastError = _GetNonzeroLastError();
        goto LABEL_6;
      }
      *(_WORD *)v17 = 19267;
      LODWORD(v36) = 1651469410;
      HIDWORD(v36) = v12[8];
      if ( v12[4] == 12 )
      {
        v18 = v16 - 2;
        pPaddingInfo[0] = 88;
        pPaddingInfo[1] = 1;
        v30 = *((_QWORD *)v12 + 3);
        v31 = v12[4];
        v32 = &v36;
        v33 = 12;
        v34 = *((_QWORD *)v12 + 1) + (unsigned int)(v16 - 2);
        v35 = 16;
        v14 = BCryptDecrypt(phKey, *((PUCHAR *)v12 + 1), v16 - 2, pPaddingInfo, 0, 0, v17 + 2, v16 - 2, &pcbResult, 0);
        if ( v14 )
          goto LABEL_25;
        if ( pcbResult != v18 )
        {
          v14 = -2146893792;
          goto LABEL_25;
        }
        if ( !a5 || !a6 )
          goto LABEL_24;
        if ( !(unsigned int)CreateDecompressor(536870914, 0, &v24) )
          goto LABEL_12;
        v10 = LocalAlloc(0x40u, v12[8]);
        if ( !v10 || !(unsigned int)Decompress(v24, v9, v22, v10) )
          goto LABEL_12;
        if ( (_DWORD)v26 == v12[8] )
        {
          *a5 = v26;
          *a6 = v10;
          v10 = 0;
LABEL_24:
          v14 = 0;
          goto LABEL_25;
        }
      }
    }
LABEL_8:
    v14 = 13;
  }
LABEL_25:
  FidoFree(v12);
  if ( phKey )
    BCryptDestroyKey(phKey);
  FidoFree(v9);
  if ( v24 )
    CloseDecompressor(v24, v19);
  FidoFree(v10);
  return v14;
}

```

## disassembly

```asm
0x1800e3290  push    rbp
0x1800e3292  push    rbx
0x1800e3293  push    rsi
0x1800e3294  push    rdi
0x1800e3295  push    r12
0x1800e3297  push    r13
0x1800e3299  push    r14
0x1800e329b  push    r15
0x1800e329d  lea     rbp, [rsp-18h]
0x1800e32a2  sub     rsp, 118h
0x1800e32a9  mov     rax, cs:__security_cookie
0x1800e32b0  xor     rax, rsp
0x1800e32b3  mov     [rbp+50h+var_50], rax
0x1800e32b7  mov     r12, [rbp+50h+arg_20]
0x1800e32be  mov     edi, r8d
0x1800e32c1  mov     r15, [rbp+50h+arg_28]
0x1800e32c8  mov     ebx, ecx
0x1800e32ca  mov     [rsp+150h+var_D8], rdx
0x1800e32cf  lea     rcx, [rbp+50h+pPaddingInfo]; void *
0x1800e32d3  xor     edx, edx; Val
0x1800e32d5  mov     [rsp+150h+var_E8], 0
0x1800e32de  mov     r13, r9
0x1800e32e1  mov     [rsp+150h+phKey], 0
0x1800e32ea  lea     r8d, [rdx+58h]; Size
0x1800e32ee  call    memset_0
0x1800e32f3  xor     ecx, ecx
0x1800e32f5  xor     eax, eax
0x1800e32f7  mov     [rsp+150h+var_100], ecx
0x1800e32fb  mov     r14d, ecx
0x1800e32fe  mov     [rsp+150h+var_F0], rcx
0x1800e3303  mov     esi, ecx
0x1800e3305  mov     [rsp+150h+var_E0], rcx
0x1800e330a  mov     [rbp+50h+var_60], rax
0x1800e330e  mov     [rbp+50h+var_58], eax
0x1800e3311  test    r12, r12
0x1800e3314  jz      short loc_1800E3322
0x1800e3316  test    r15, r15
0x1800e3319  jz      short loc_1800E3322
0x1800e331b  mov     [r12], ecx
0x1800e331f  mov     [r15], rcx
0x1800e3322  lea     rax, [rsp+150h+var_FC]
0x1800e3327  mov     rdx, r13
0x1800e332a  lea     r9, [rbp+50h+var_D0]
0x1800e332e  mov     [rsp+150h+pbSecret], rax
0x1800e3333  lea     r8, [rsp+150h+var_E8]
0x1800e3338  mov     ecx, edi
0x1800e333a  call    CtapCborDecodeEncryptedLargeBlob
0x1800e333f  mov     rdi, [rsp+150h+var_E8]
0x1800e3344  test    eax, eax
0x1800e3346  jz      short loc_1800E3356
0x1800e3348  mov     ecx, eax
0x1800e334a  call    CtapCborErrorToWin32Error
0x1800e334f  mov     ebx, eax
0x1800e3351  jmp     loc_1800E3505
0x1800e3356  cmp     ebx, 20h ; ' '
0x1800e3359  jz      short loc_1800E3365
0x1800e335b  mov     ebx, 0Dh
0x1800e3360  jmp     loc_1800E3505
0x1800e3365  mov     rax, [rsp+150h+var_D8]
0x1800e336a  lea     rdx, [rsp+150h+phKey]; phKey
0x1800e336f  mov     [rsp+150h+dwFlags], esi; dwFlags
0x1800e3373  xor     r9d, r9d; cbKeyObject
0x1800e3376  mov     [rsp+150h+cbSecret], 20h ; ' '; cbSecret
0x1800e337e  xor     r8d, r8d; pbKeyObject
0x1800e3381  mov     ecx, 1E1h; hAlgorithm
0x1800e3386  mov     [rsp+150h+pbSecret], rax; pbSecret
0x1800e338b  call    cs:__imp_BCryptGenerateSymmetricKey
0x1800e3391  mov     ebx, eax
0x1800e3393  test    eax, eax
0x1800e3395  jnz     loc_1800E3505
0x1800e339b  mov     eax, [rdi]
0x1800e339d  cmp     eax, 10h
0x1800e33a0  jb      short loc_1800E335B
0x1800e33a2  lea     ebx, [rax-0Eh]
0x1800e33a5  mov     ecx, 40h ; '@'; uFlags
0x1800e33aa  mov     edx, ebx; uBytes
0x1800e33ac  mov     [rsp+150h+var_FC], ebx
0x1800e33b0  call    cs:__imp_LocalAlloc
0x1800e33b6  xor     edx, edx
0x1800e33b8  mov     r14, rax
0x1800e33bb  test    rax, rax
0x1800e33be  jnz     short loc_1800E33C7
0x1800e33c0  call    ?_GetNonzeroLastError@@YAKXZ; _GetNonzeroLastError(void)
0x1800e33c5  jmp     short loc_1800E334F
0x1800e33c7  mov     word ptr [rax], 4B43h
0x1800e33cc  mov     dword ptr [rbp+50h+var_60], 626F6C62h
0x1800e33d3  mov     eax, [rdi+20h]
0x1800e33d6  mov     dword ptr [rbp+50h+var_60+4], eax
0x1800e33d9  cmp     dword ptr [rdi+10h], 0Ch
0x1800e33dd  jnz     loc_1800E335B
0x1800e33e3  mov     [rsp+150h+var_108], edx; dwFlags
0x1800e33e7  lea     r13d, [rbx-2]
0x1800e33eb  mov     [rbp+50h+pPaddingInfo], 58h ; 'X'
0x1800e33f2  lea     rcx, [rsp+150h+var_100]
0x1800e33f7  mov     [rsp+150h+pcbResult], rcx; pcbResult
0x1800e33fc  lea     r9, [rbp+50h+pPaddingInfo]; pPaddingInfo
0x1800e3400  mov     rcx, [rsp+150h+phKey]; hKey
0x1800e3405  mov     r8d, r13d; cbInput
0x1800e3408  mov     [rbp+50h+var_BC], 1
0x1800e340f  mov     rax, [rdi+18h]
0x1800e3413  mov     [rbp+50h+var_B8], rax
0x1800e3417  mov     eax, [rdi+10h]
0x1800e341a  mov     [rbp+50h+var_B0], eax
0x1800e341d  lea     rax, [rbp+50h+var_60]
0x1800e3421  mov     [rbp+50h+var_A8], rax
0x1800e3425  mov     [rbp+50h+var_A0], 0Ch
0x1800e342c  mov     [rsp+150h+cbOutput], r13d; cbOutput
0x1800e3431  mov     eax, r13d
0x1800e3434  add     rax, [rdi+8]
0x1800e3438  mov     [rbp+50h+var_98], rax
0x1800e343c  lea     rax, [r14+2]
0x1800e3440  mov     qword ptr [rsp+150h+dwFlags], rax; pbOutput
0x1800e3445  mov     [rsp+150h+cbSecret], edx; cbIV
0x1800e3449  mov     [rsp+150h+pbSecret], rdx; pbIV
0x1800e344e  mov     [rbp+50h+var_90], 10h
0x1800e3455  mov     rdx, [rdi+8]; pbInput
0x1800e3459  call    cs:__imp_BCryptDecrypt
0x1800e345f  mov     ebx, eax
0x1800e3461  test    eax, eax
0x1800e3463  jnz     loc_1800E3505
0x1800e3469  cmp     [rsp+150h+var_100], r13d
0x1800e346e  jz      short loc_1800E347A
0x1800e3470  mov     ebx, 80090020h
0x1800e3475  jmp     loc_1800E3505
0x1800e347a  test    r12, r12
0x1800e347d  jz      loc_1800E3503
0x1800e3483  test    r15, r15
0x1800e3486  jz      short loc_1800E3503
0x1800e3488  lea     r8, [rsp+150h+var_F0]
0x1800e348d  xor     edx, edx
0x1800e348f  mov     ecx, 20000002h
0x1800e3494  call    cs:__imp_CreateDecompressor
0x1800e349a  test    eax, eax
0x1800e349c  jz      loc_1800E33C0
0x1800e34a2  mov     edx, [rdi+20h]; uBytes
0x1800e34a5  mov     ecx, 40h ; '@'; uFlags
0x1800e34aa  call    cs:__imp_LocalAlloc
0x1800e34b0  mov     rsi, rax
0x1800e34b3  test    rax, rax
0x1800e34b6  jz      loc_1800E33C0
0x1800e34bc  mov     eax, [rdi+20h]
0x1800e34bf  lea     rcx, [rsp+150h+var_E0]
0x1800e34c4  mov     r8d, [rsp+150h+var_FC]
0x1800e34c9  mov     r9, rsi
0x1800e34cc  mov     qword ptr [rsp+150h+cbSecret], rcx
0x1800e34d1  mov     rdx, r14
0x1800e34d4  mov     rcx, [rsp+150h+var_F0]
0x1800e34d9  mov     [rsp+150h+pbSecret], rax
0x1800e34de  call    cs:__imp_Decompress
0x1800e34e4  test    eax, eax
0x1800e34e6  jz      loc_1800E33C0
0x1800e34ec  mov     rax, [rsp+150h+var_E0]
0x1800e34f1  cmp     eax, [rdi+20h]
0x1800e34f4  jnz     loc_1800E335B
0x1800e34fa  mov     [r12], eax
0x1800e34fe  mov     [r15], rsi
0x1800e3501  xor     esi, esi
0x1800e3503  xor     ebx, ebx
0x1800e3505  mov     rcx, rdi; void *
0x1800e3508  call    ?FidoFree@@YAXPEAX@Z; FidoFree(void *)
0x1800e350d  mov     rcx, [rsp+150h+phKey]; hKey
0x1800e3512  test    rcx, rcx
0x1800e3515  jz      short loc_1800E351D
0x1800e3517  call    cs:__imp_BCryptDestroyKey
0x1800e351d  mov     rcx, r14; void *
0x1800e3520  call    ?FidoFree@@YAXPEAX@Z; FidoFree(void *)
0x1800e3525  mov     rcx, [rsp+150h+var_F0]
0x1800e352a  test    rcx, rcx
0x1800e352d  jz      short loc_1800E3535
0x1800e352f  call    cs:__imp_CloseDecompressor
0x1800e3535  mov     rcx, rsi; void *
0x1800e3538  call    ?FidoFree@@YAXPEAX@Z; FidoFree(void *)
0x1800e353d  mov     eax, ebx
0x1800e353f  mov     rcx, [rbp+50h+var_50]
0x1800e3543  xor     rcx, rsp; StackCookie
0x1800e3546  call    __security_check_cookie
0x1800e354b  add     rsp, 118h
0x1800e3552  pop     r15
0x1800e3554  pop     r14
0x1800e3556  pop     r13
0x1800e3558  pop     r12
0x1800e355a  pop     rdi
0x1800e355b  pop     rsi
0x1800e355c  pop     rbx
0x1800e355d  pop     rbp
0x1800e355e  retn
```
