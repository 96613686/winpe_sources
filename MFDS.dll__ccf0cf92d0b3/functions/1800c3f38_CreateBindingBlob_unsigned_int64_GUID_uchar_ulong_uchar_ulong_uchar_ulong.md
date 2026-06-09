# CreateBindingBlob(unsigned __int64,_GUID,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)

- ea: `0x1800c3f38`
- end: `0x1800c43ba`
- name: `?CreateBindingBlob@@YAJ_KU_GUID@@PEAEK2KPEAPEAEPEAK@Z`
- size: `1154`
- prototype: `__int64 __fastcall(unsigned __int64, struct _GUID *, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c43c0`

## callees

- `0x180010350`
- `0x180074160`
- `0x180074a06`
- `0x1800c3f38`
- `0x1800c484c`
- `0x1800c48d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c41a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c41a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c41f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c4207`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c41f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c4207`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c400e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c4035`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c400e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c4035`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x1800c42fd`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x1800c42fd`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x1800c421d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x1800c421d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x1800c4322`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x1800c4322`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyKey` at `0x1800c4233`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyKey` at `0x1800c4233`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptImportKey` at `0x1800c4184`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptImportKey` at `0x1800c4184`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptSignHashW` at `0x1800c4360`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptSignHashW` at `0x1800c4360`

## pseudocode

```c
__int64 __fastcall CreateBindingBlob(
        HCRYPTPROV a1,
        struct _GUID *a2,
        unsigned __int8 *a3,
        unsigned int a4,
        unsigned __int8 *a5,
        unsigned int a6,
        unsigned __int8 **a7,
        unsigned int *a8)
{
  __int64 v9; // r12
  unsigned __int64 v10; // rdi
  unsigned __int64 v12; // r14
  LPVOID v13; // rdi
  __int64 v14; // r15
  BYTE *v15; // rsi
  unsigned int v16; // ebx
  __int64 v17; // rdx
  _OWORD *v18; // rax
  __int64 *v19; // rcx
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  __int128 v23; // xmm0
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  __int128 v26; // xmm1
  BYTE *v27; // rcx
  __int64 *v28; // rax
  __int64 v29; // rdx
  __int128 v30; // xmm1
  _BYTE *v31; // rax
  HCRYPTPROV v32; // r12
  BOOL v33; // ecx
  BYTE *v34; // rax
  signed int LastError; // eax
  unsigned int v36; // r15d
  __int64 v37; // rax
  _OWORD *v38; // rcx
  __int128 v39; // xmm1
  unsigned int *v40; // rax
  DWORD pdwSigLen; // [rsp+30h] [rbp-D0h] BYREF
  HCRYPTHASH hHash; // [rsp+38h] [rbp-C8h] BYREF
  HCRYPTKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  HCRYPTPROV hProv; // [rsp+48h] [rbp-B8h]
  struct _GUID *v45; // [rsp+50h] [rbp-B0h]
  unsigned int *v46; // [rsp+58h] [rbp-A8h]
  _BYTE v47[256]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v48[272]; // [rsp+160h] [rbp+60h] BYREF

  v45 = a2;
  v9 = 272;
  hProv = a1;
  v10 = a4;
  v46 = a8;
  hKey = 0;
  hHash = 0;
  pdwSigLen = 0;
  memset_0(v48, 0, sizeof(v48));
  if ( !a3 || !a7 || !a8 )
    return 2147500035LL;
  if ( a6 != 8 )
    return 2147942487LL;
  v12 = v10 / 0x1D8;
  if ( v10 != 472 * (v10 / 0x1D8) )
    return 2147549183LL;
  v13 = CoTaskMemAlloc(0x1D8u);
  if ( !v13 )
    return 2147942414LL;
  v14 = 596;
  v15 = (BYTE *)CoTaskMemAlloc(0x254u);
  if ( !v15 )
  {
    v16 = -2147024882;
    goto LABEL_27;
  }
  v17 = 2;
  v18 = v47;
  v19 = qword_1800DEE30;
  do
  {
    v20 = *((_OWORD *)v19 + 1);
    *v18 = *(_OWORD *)v19;
    v21 = *((_OWORD *)v19 + 2);
    v18[1] = v20;
    v22 = *((_OWORD *)v19 + 3);
    v18[2] = v21;
    v23 = *((_OWORD *)v19 + 4);
    v18[3] = v22;
    v24 = *((_OWORD *)v19 + 5);
    v18[4] = v23;
    v25 = *((_OWORD *)v19 + 6);
    v18[5] = v24;
    v26 = *((_OWORD *)v19 + 7);
    v19 += 16;
    v18[6] = v25;
    v18[7] = v26;
    v18 += 8;
    --v17;
  }
  while ( v17 );
  v27 = v15;
  v28 = qword_1800DEF30;
  v29 = 4;
  do
  {
    *(_OWORD *)v27 = *(_OWORD *)v28;
    *((_OWORD *)v27 + 1) = *((_OWORD *)v28 + 1);
    *((_OWORD *)v27 + 2) = *((_OWORD *)v28 + 2);
    *((_OWORD *)v27 + 3) = *((_OWORD *)v28 + 3);
    *((_OWORD *)v27 + 4) = *((_OWORD *)v28 + 4);
    *((_OWORD *)v27 + 5) = *((_OWORD *)v28 + 5);
    *((_OWORD *)v27 + 6) = *((_OWORD *)v28 + 6);
    v30 = *((_OWORD *)v28 + 7);
    v28 += 16;
    *((_OWORD *)v27 + 7) = v30;
    v27 += 128;
    --v29;
  }
  while ( v29 );
  *(_OWORD *)v27 = *(_OWORD *)v28;
  *((_OWORD *)v27 + 1) = *((_OWORD *)v28 + 1);
  *((_OWORD *)v27 + 2) = *((_OWORD *)v28 + 2);
  *((_OWORD *)v27 + 3) = *((_OWORD *)v28 + 3);
  *((_OWORD *)v27 + 4) = *((_OWORD *)v28 + 4);
  *((_DWORD *)v27 + 20) = *((_DWORD *)v28 + 20);
  SymCryptRc4Init(v48, v47, 128);
  SymCryptRc4Crypt(v48, v15, v15);
  v31 = v48;
  do
  {
    *v31++ = 0;
    --v9;
  }
  while ( v9 );
  v32 = hProv;
  v33 = CryptImportKey(hProv, v15, 0x254u, 0, 0, &hKey);
  v34 = v15;
  do
  {
    *v34++ = 0;
    --v14;
  }
  while ( v14 );
  if ( v33 )
  {
    v36 = 0;
    if ( !(_DWORD)v12 )
      goto LABEL_26;
    while ( !(unsigned __int8)_(v45, a3 + 40) )
    {
      ++v36;
      a3 += 472;
      if ( v36 >= (unsigned int)v12 )
        goto LABEL_26;
    }
    v37 = 3;
    v38 = v13;
    do
    {
      *v38 = *(_OWORD *)a3;
      v38[1] = *((_OWORD *)a3 + 1);
      v38[2] = *((_OWORD *)a3 + 2);
      v38[3] = *((_OWORD *)a3 + 3);
      v38[4] = *((_OWORD *)a3 + 4);
      v38[5] = *((_OWORD *)a3 + 5);
      v38[6] = *((_OWORD *)a3 + 6);
      v39 = *((_OWORD *)a3 + 7);
      a3 += 128;
      v38[7] = v39;
      v38 += 8;
      --v37;
    }
    while ( v37 );
    *v38 = *(_OWORD *)a3;
    v38[1] = *((_OWORD *)a3 + 1);
    v38[2] = *((_OWORD *)a3 + 2);
    v38[3] = *((_OWORD *)a3 + 3);
    v38[4] = *((_OWORD *)a3 + 4);
    *((_QWORD *)v38 + 10) = *((_QWORD *)a3 + 10);
    if ( *((_DWORD *)v13 + 1) != 2 )
    {
LABEL_26:
      v16 = -2147024809;
      goto LABEL_27;
    }
    *((_QWORD *)v13 + 42) = *(_QWORD *)a5;
    if ( CryptCreateHash(v32, 0x800Eu, 0, 0, &hHash) )
    {
      if ( CryptHashData(hHash, (const BYTE *)v13, 0x158u, 0) )
      {
        pdwSigLen = 128;
        if ( CryptSignHashW(hHash, 2u, 0, 0, (BYTE *)v13 + 344, &pdwSigLen) )
        {
          v40 = v46;
          v16 = 0;
          *a7 = (unsigned __int8 *)v13;
          *v40 = 472;
          goto LABEL_28;
        }
      }
    }
  }
  LastError = GetLastError();
  v16 = LastError;
  if ( LastError > 0 )
    v16 = (unsigned __int16)LastError | 0x80070000;
LABEL_27:
  CoTaskMemFree(v13);
  if ( v15 )
LABEL_28:
    CoTaskMemFree(v15);
  if ( hHash )
    CryptDestroyHash(hHash);
  if ( hKey )
    CryptDestroyKey(hKey);
  return v16;
}

```

## disassembly

```asm
0x1800c3f38  mov     [rsp-8+arg_18], rbx
0x1800c3f3d  push    rbp
0x1800c3f3e  push    rsi
0x1800c3f3f  push    rdi
0x1800c3f40  push    r12
0x1800c3f42  push    r13
0x1800c3f44  push    r14
0x1800c3f46  push    r15
0x1800c3f48  lea     rbp, [rsp-180h]
0x1800c3f50  sub     rsp, 280h
0x1800c3f57  mov     rax, cs:__security_cookie
0x1800c3f5e  xor     rax, rsp
0x1800c3f61  mov     [rbp+1B0h+var_40], rax
0x1800c3f68  mov     rsi, [rbp+1B0h+arg_38]
0x1800c3f6f  xor     r15d, r15d
0x1800c3f72  mov     r13, [rbp+1B0h+arg_30]
0x1800c3f79  mov     rbx, r8
0x1800c3f7c  mov     [rsp+2B0h+var_260], rdx
0x1800c3f81  mov     r12d, 110h
0x1800c3f87  mov     [rsp+2B0h+hProv], rcx
0x1800c3f8c  mov     r8d, r12d; Size
0x1800c3f8f  xor     edx, edx; Val
0x1800c3f91  mov     edi, r9d
0x1800c3f94  lea     rcx, [rbp+1B0h+var_150]; void *
0x1800c3f98  mov     [rsp+2B0h+var_258], rsi
0x1800c3f9d  mov     [rsp+2B0h+hKey], r15
0x1800c3fa2  mov     [rsp+2B0h+hHash], r15
0x1800c3fa7  mov     [rsp+2B0h+pdwSigLen], r15d
0x1800c3fac  call    memset_0
0x1800c3fb1  test    rbx, rbx
0x1800c3fb4  jz      loc_1800C438A
0x1800c3fba  test    r13, r13
0x1800c3fbd  jz      loc_1800C438A
0x1800c3fc3  test    rsi, rsi
0x1800c3fc6  jz      loc_1800C438A
0x1800c3fcc  cmp     [rbp+1B0h+arg_28], 8
0x1800c3fd3  jz      short loc_1800C3FDF
0x1800c3fd5  mov     eax, 80070057h
0x1800c3fda  jmp     loc_1800C438F
0x1800c3fdf  mov     rax, 8AD8F2FBA9386823h
0x1800c3fe9  mul     rdi
0x1800c3fec  mov     r14, rdx
0x1800c3fef  shr     r14, 8
0x1800c3ff3  imul    rax, r14, 1D8h
0x1800c3ffa  cmp     rdi, rax
0x1800c3ffd  jz      short loc_1800C4009
0x1800c3fff  mov     eax, 8000FFFFh
0x1800c4004  jmp     loc_1800C438F
0x1800c4009  mov     ecx, 1D8h; cb
0x1800c400e  call    cs:__imp_CoTaskMemAlloc
0x1800c4015  nop     dword ptr [rax+rax+00h]
0x1800c401a  mov     rdi, rax
0x1800c401d  test    rax, rax
0x1800c4020  jnz     short loc_1800C402C
0x1800c4022  mov     eax, 8007000Eh
0x1800c4027  jmp     loc_1800C438F
0x1800c402c  mov     r15d, 254h
0x1800c4032  mov     ecx, r15d; cb
0x1800c4035  call    cs:__imp_CoTaskMemAlloc
0x1800c403c  nop     dword ptr [rax+rax+00h]
0x1800c4041  mov     rsi, rax
0x1800c4044  test    rax, rax
0x1800c4047  jnz     short loc_1800C4053
0x1800c4049  mov     ebx, 8007000Eh
0x1800c404e  jmp     loc_1800C41F0
0x1800c4053  mov     edx, 2
0x1800c4058  lea     rax, [rsp+2B0h+var_250]
0x1800c405d  lea     rcx, qword_1800DEE30
0x1800c4064  lea     r8d, [rdx+7Eh]
0x1800c4068  movups  xmm0, xmmword ptr [rcx]
0x1800c406b  movups  xmm1, xmmword ptr [rcx+10h]
0x1800c406f  movups  xmmword ptr [rax], xmm0
0x1800c4072  movups  xmm0, xmmword ptr [rcx+20h]
0x1800c4076  movups  xmmword ptr [rax+10h], xmm1
0x1800c407a  movups  xmm1, xmmword ptr [rcx+30h]
0x1800c407e  movups  xmmword ptr [rax+20h], xmm0
0x1800c4082  movups  xmm0, xmmword ptr [rcx+40h]
0x1800c4086  movups  xmmword ptr [rax+30h], xmm1
0x1800c408a  movups  xmm1, xmmword ptr [rcx+50h]
0x1800c408e  movups  xmmword ptr [rax+40h], xmm0
0x1800c4092  movups  xmm0, xmmword ptr [rcx+60h]
0x1800c4096  movups  xmmword ptr [rax+50h], xmm1
0x1800c409a  movups  xmm1, xmmword ptr [rcx+70h]
0x1800c409e  add     rcx, r8
0x1800c40a1  movups  xmmword ptr [rax+60h], xmm0
0x1800c40a5  movups  xmmword ptr [rax+70h], xmm1
0x1800c40a9  add     rax, r8
0x1800c40ac  sub     rdx, 1
0x1800c40b0  jnz     short loc_1800C4068
0x1800c40b2  mov     rcx, rsi
0x1800c40b5  lea     rax, qword_1800DEF30
0x1800c40bc  mov     edx, 4
0x1800c40c1  movups  xmm0, xmmword ptr [rax]
0x1800c40c4  movups  xmmword ptr [rcx], xmm0
0x1800c40c7  movups  xmm1, xmmword ptr [rax+10h]
0x1800c40cb  movups  xmmword ptr [rcx+10h], xmm1
0x1800c40cf  movups  xmm0, xmmword ptr [rax+20h]
0x1800c40d3  movups  xmmword ptr [rcx+20h], xmm0
0x1800c40d7  movups  xmm1, xmmword ptr [rax+30h]
0x1800c40db  movups  xmmword ptr [rcx+30h], xmm1
0x1800c40df  movups  xmm0, xmmword ptr [rax+40h]
0x1800c40e3  movups  xmmword ptr [rcx+40h], xmm0
0x1800c40e7  movups  xmm1, xmmword ptr [rax+50h]
0x1800c40eb  movups  xmmword ptr [rcx+50h], xmm1
0x1800c40ef  movups  xmm0, xmmword ptr [rax+60h]
0x1800c40f3  movups  xmmword ptr [rcx+60h], xmm0
0x1800c40f7  movups  xmm1, xmmword ptr [rax+70h]
0x1800c40fb  add     rax, r8
0x1800c40fe  movups  xmmword ptr [rcx+70h], xmm1
0x1800c4102  add     rcx, r8
0x1800c4105  sub     rdx, 1
0x1800c4109  jnz     short loc_1800C40C1
0x1800c410b  movups  xmm0, xmmword ptr [rax]
0x1800c410e  lea     rdx, [rsp+2B0h+var_250]
0x1800c4113  movups  xmmword ptr [rcx], xmm0
0x1800c4116  movups  xmm1, xmmword ptr [rax+10h]
0x1800c411a  movups  xmmword ptr [rcx+10h], xmm1
0x1800c411e  movups  xmm0, xmmword ptr [rax+20h]
0x1800c4122  movups  xmmword ptr [rcx+20h], xmm0
0x1800c4126  movups  xmm1, xmmword ptr [rax+30h]
0x1800c412a  movups  xmmword ptr [rcx+30h], xmm1
0x1800c412e  movups  xmm0, xmmword ptr [rax+40h]
0x1800c4132  movups  xmmword ptr [rcx+40h], xmm0
0x1800c4136  mov     eax, [rax+50h]
0x1800c4139  mov     [rcx+50h], eax
0x1800c413c  lea     rcx, [rbp+1B0h+var_150]
0x1800c4140  call    SymCryptRc4Init
0x1800c4145  mov     r8, rsi
0x1800c4148  lea     rcx, [rbp+1B0h+var_150]
0x1800c414c  mov     rdx, rsi
0x1800c414f  call    SymCryptRc4Crypt
0x1800c4154  lea     rax, [rbp+1B0h+var_150]
0x1800c4158  mov     byte ptr [rax], 0
0x1800c415b  inc     rax
0x1800c415e  sub     r12, 1
0x1800c4162  jnz     short loc_1800C4158
0x1800c4164  lea     rax, [rsp+2B0h+hKey]
0x1800c4169  xor     r9d, r9d; hPubKey
0x1800c416c  mov     [rsp+2B0h+phKey], rax; phKey
0x1800c4171  mov     r8d, r15d; dwDataLen
0x1800c4174  mov     [rsp+2B0h+dwFlags], r12d; dwFlags
0x1800c4179  mov     rdx, rsi; pbData
0x1800c417c  mov     r12, [rsp+2B0h+hProv]
0x1800c4181  mov     rcx, r12; hProv
0x1800c4184  call    cs:__imp_CryptImportKey
0x1800c418b  nop     dword ptr [rax+rax+00h]
0x1800c4190  mov     ecx, eax
0x1800c4192  mov     rax, rsi
0x1800c4195  mov     byte ptr [rax], 0
0x1800c4198  inc     rax
0x1800c419b  sub     r15, 1
0x1800c419f  jnz     short loc_1800C4195
0x1800c41a1  test    ecx, ecx
0x1800c41a3  jnz     short loc_1800C41C2
0x1800c41a5  call    cs:__imp_GetLastError
0x1800c41ac  nop     dword ptr [rax+rax+00h]
0x1800c41b1  mov     ebx, eax
0x1800c41b3  test    eax, eax
0x1800c41b5  jle     short loc_1800C41F0
0x1800c41b7  movzx   ebx, ax
0x1800c41ba  or      ebx, 80070000h
0x1800c41c0  jmp     short loc_1800C41F0
0x1800c41c2  xor     r15d, r15d
0x1800c41c5  test    r14d, r14d
0x1800c41c8  jz      short loc_1800C41EB
0x1800c41ca  mov     rcx, [rsp+2B0h+var_260]
0x1800c41cf  lea     rdx, [rbx+28h]
0x1800c41d3  call    __
0x1800c41d8  test    al, al
0x1800c41da  jnz     short loc_1800C4246
0x1800c41dc  inc     r15d
0x1800c41df  add     rbx, 1D8h
0x1800c41e6  cmp     r15d, r14d
0x1800c41e9  jb      short loc_1800C41CA
0x1800c41eb  mov     ebx, 80070057h
0x1800c41f0  mov     rcx, rdi; pv
0x1800c41f3  call    cs:__imp_CoTaskMemFree
0x1800c41fa  nop     dword ptr [rax+rax+00h]
0x1800c41ff  test    rsi, rsi
0x1800c4202  jz      short loc_1800C4213
0x1800c4204  mov     rcx, rsi; pv
0x1800c4207  call    cs:__imp_CoTaskMemFree
0x1800c420e  nop     dword ptr [rax+rax+00h]
0x1800c4213  mov     rcx, [rsp+2B0h+hHash]; hHash
0x1800c4218  test    rcx, rcx
0x1800c421b  jz      short loc_1800C4229
0x1800c421d  call    cs:__imp_CryptDestroyHash
0x1800c4224  nop     dword ptr [rax+rax+00h]
0x1800c4229  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1800c422e  test    rcx, rcx
0x1800c4231  jz      short loc_1800C423F
0x1800c4233  call    cs:__imp_CryptDestroyKey
0x1800c423a  nop     dword ptr [rax+rax+00h]
0x1800c423f  mov     eax, ebx
0x1800c4241  jmp     loc_1800C438F
0x1800c4246  mov     eax, 3
0x1800c424b  mov     rcx, rdi
0x1800c424e  lea     r14d, [rax+7Dh]
0x1800c4252  movups  xmm0, xmmword ptr [rbx]
0x1800c4255  movups  xmmword ptr [rcx], xmm0
0x1800c4258  movups  xmm1, xmmword ptr [rbx+10h]
0x1800c425c  movups  xmmword ptr [rcx+10h], xmm1
0x1800c4260  movups  xmm0, xmmword ptr [rbx+20h]
0x1800c4264  movups  xmmword ptr [rcx+20h], xmm0
0x1800c4268  movups  xmm1, xmmword ptr [rbx+30h]
0x1800c426c  movups  xmmword ptr [rcx+30h], xmm1
0x1800c4270  movups  xmm0, xmmword ptr [rbx+40h]
0x1800c4274  movups  xmmword ptr [rcx+40h], xmm0
0x1800c4278  movups  xmm1, xmmword ptr [rbx+50h]
0x1800c427c  movups  xmmword ptr [rcx+50h], xmm1
0x1800c4280  movups  xmm0, xmmword ptr [rbx+60h]
0x1800c4284  movups  xmmword ptr [rcx+60h], xmm0
0x1800c4288  movups  xmm1, xmmword ptr [rbx+70h]
0x1800c428c  add     rbx, r14
0x1800c428f  movups  xmmword ptr [rcx+70h], xmm1
0x1800c4293  add     rcx, r14
0x1800c4296  sub     rax, 1
0x1800c429a  jnz     short loc_1800C4252
0x1800c429c  movups  xmm0, xmmword ptr [rbx]
0x1800c429f  movups  xmmword ptr [rcx], xmm0
0x1800c42a2  movups  xmm1, xmmword ptr [rbx+10h]
0x1800c42a6  movups  xmmword ptr [rcx+10h], xmm1
0x1800c42aa  movups  xmm0, xmmword ptr [rbx+20h]
0x1800c42ae  movups  xmmword ptr [rcx+20h], xmm0
0x1800c42b2  movups  xmm1, xmmword ptr [rbx+30h]
0x1800c42b6  movups  xmmword ptr [rcx+30h], xmm1
0x1800c42ba  movups  xmm0, xmmword ptr [rbx+40h]
0x1800c42be  movups  xmmword ptr [rcx+40h], xmm0
0x1800c42c2  mov     rax, [rbx+50h]
0x1800c42c6  mov     [rcx+50h], rax
0x1800c42ca  cmp     dword ptr [rdi+4], 2
0x1800c42ce  jnz     loc_1800C41EB
0x1800c42d4  mov     rax, [rbp+1B0h+arg_20]
0x1800c42db  xor     r9d, r9d; dwFlags
0x1800c42de  xor     r8d, r8d; hKey
0x1800c42e1  mov     rcx, r12; hProv
0x1800c42e4  mov     rdx, [rax]
0x1800c42e7  lea     rax, [rsp+2B0h+hHash]
0x1800c42ec  mov     [rdi+150h], rdx
0x1800c42f3  mov     edx, 800Eh; Algid
0x1800c42f8  mov     qword ptr [rsp+2B0h+dwFlags], rax; phHash
0x1800c42fd  call    cs:__imp_CryptCreateHash
0x1800c4304  nop     dword ptr [rax+rax+00h]
0x1800c4309  test    eax, eax
0x1800c430b  jz      loc_1800C41A5
0x1800c4311  mov     rcx, [rsp+2B0h+hHash]; hHash
0x1800c4316  xor     r9d, r9d; dwFlags
0x1800c4319  mov     r8d, 158h; dwDataLen
0x1800c431f  mov     rdx, rdi; pbData
0x1800c4322  call    cs:__imp_CryptHashData
0x1800c4329  nop     dword ptr [rax+rax+00h]
0x1800c432e  test    eax, eax
0x1800c4330  jz      loc_1800C41A5
0x1800c4336  xor     r9d, r9d; dwFlags
0x1800c4339  mov     [rsp+2B0h+pdwSigLen], r14d
0x1800c433e  lea     rcx, [rsp+2B0h+pdwSigLen]
0x1800c4343  xor     r8d, r8d; szDescription
0x1800c4346  mov     [rsp+2B0h+phKey], rcx; pdwSigLen
0x1800c434b  lea     rax, [rdi+158h]
0x1800c4352  mov     rcx, [rsp+2B0h+hHash]; hHash
0x1800c4357  lea     edx, [r9+2]; dwKeySpec
0x1800c435b  mov     qword ptr [rsp+2B0h+dwFlags], rax; pbSignature
0x1800c4360  call    cs:__imp_CryptSignHashW
0x1800c4367  nop     dword ptr [rax+rax+00h]
0x1800c436c  test    eax, eax
0x1800c436e  jz      loc_1800C41A5
0x1800c4374  mov     rax, [rsp+2B0h+var_258]
0x1800c4379  xor     ebx, ebx
0x1800c437b  mov     [r13+0], rdi
0x1800c437f  mov     dword ptr [rax], 1D8h
0x1800c4385  jmp     loc_1800C4204
0x1800c438a  mov     eax, 80004003h
0x1800c438f  mov     rcx, [rbp+1B0h+var_40]
0x1800c4396  xor     rcx, rsp; StackCookie
0x1800c4399  call    __security_check_cookie
0x1800c439e  mov     rbx, [rsp+2B0h+arg_18]
0x1800c43a6  add     rsp, 280h
0x1800c43ad  pop     r15
0x1800c43af  pop     r14
0x1800c43b1  pop     r13
0x1800c43b3  pop     r12
0x1800c43b5  pop     rdi
0x1800c43b6  pop     rsi
0x1800c43b7  pop     rbp
0x1800c43b8  retn
```
