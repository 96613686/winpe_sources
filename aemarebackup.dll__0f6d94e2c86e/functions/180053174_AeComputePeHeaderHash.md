# AeComputePeHeaderHash

- ea: `0x180053174`
- end: `0x1800535e5`
- name: `AeComputePeHeaderHash`
- size: `1137`
- prototype: `__int64 __fastcall(BYTE *pbData)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800e5428`

## callees

- `0x1800527f0`
- `0x180053174`
- `0x18005490c`
- `0x180054934`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053275`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800532f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053351`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800533b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053415`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053493`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053545`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053275`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800532f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053351`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800533b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053415`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053493`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053545`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180053347`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x1800533a9`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18005340b`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180053347`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x1800533a9`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18005340b`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x1800532e9`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x1800532e9`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x1800535d0`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x1800535d0`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x1800535b2`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x1800535b2`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x18005326b`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x18005326b`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180053489`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18005353b`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180053489`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18005353b`

## pseudocode

```c
__int64 __fastcall AeComputePeHeaderHash(BYTE *pbData, unsigned __int64 a2, __int64 a3)
{
  BYTE *v5; // r8
  BYTE *v6; // rdx
  BYTE *v7; // r14
  unsigned int v8; // ebx
  BYTE *v9; // rsi
  const BYTE *v10; // r15
  signed int v11; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  signed int v14; // eax
  signed int v15; // eax
  signed int v16; // eax
  signed int v17; // eax
  signed int v18; // eax
  signed int LastError; // eax
  HCRYPTPROV phProv[6]; // [rsp+38h] [rbp-30h] BYREF
  DWORD pdwDataLen; // [rsp+70h] [rbp+8h] BYREF
  unsigned __int64 pbDataa; // [rsp+78h] [rbp+10h] BYREF
  HCRYPTHASH phHash; // [rsp+88h] [rbp+20h] BYREF

  pbDataa = a2;
  phProv[0] = 0;
  phHash = 0;
  pdwDataLen = 0;
  if ( pbData && a2 >= 0x108 && a3 )
  {
    v5 = &pbData[a2];
    if ( &pbData[a2] < pbData )
      goto LABEL_64;
    v6 = &pbData[*((unsigned __int16 *)pbData + 10) + 24];
    v7 = &v6[40 * *((unsigned __int16 *)pbData + 3)];
    if ( v7 < v6 || v7 > v5 )
      goto LABEL_64;
    if ( *((_WORD *)pbData + 12) == 267 )
    {
      v9 = pbData + 52;
      v10 = pbData + 56;
    }
    else
    {
      if ( *((_WORD *)pbData + 12) != 523 )
      {
        v8 = -2147024809;
        goto LABEL_67;
      }
      v9 = pbData + 48;
      v10 = pbData + 56;
    }
    if ( v9 < pbData || v9 >= v7 || v10 < v9 || v10 >= v7 )
    {
LABEL_64:
      v8 = -805306245;
    }
    else if ( CryptAcquireContextW(phProv, 0, L"Microsoft Base Cryptographic Provider v1.0", 1u, 0xF0000000) )
    {
      if ( CryptCreateHash(phProv[0], 0x8004u, 0, 0, &phHash) )
      {
        if ( CryptHashData(phHash, pbData, (_DWORD)v9 - (_DWORD)pbData, 0) )
        {
          if ( CryptHashData(phHash, v10, (_DWORD)v7 - (_DWORD)v10, 0) )
          {
            if ( CryptHashData(phHash, (const BYTE *)&pbDataa, 8u, 0) )
            {
              pdwDataLen = 0;
              *(_OWORD *)a3 = 0;
              *(_QWORD *)(a3 + 14) = 0;
              if ( CryptGetHashParam(phHash, 2u, 0, &pdwDataLen, 0) )
              {
                if ( pdwDataLen == 20 )
                {
                  if ( CryptGetHashParam(phHash, 2u, (BYTE *)(a3 + 2), &pdwDataLen, 0) )
                  {
                    *(_BYTE *)a3 = 1;
                    v8 = 0;
                  }
                  else
                  {
                    LastError = GetLastError();
                    v8 = LastError;
                    if ( LastError > 0 )
                      v8 = (unsigned __int16)LastError | 0x80070000;
                    v12 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      v13 = 54;
                      goto LABEL_22;
                    }
                  }
                }
                else
                {
                  v8 = -2147418113;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  {
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_60421427dd2a396270afbef62f846c6d_Traceguids);
                  }
                }
              }
              else
              {
                v18 = GetLastError();
                v8 = v18;
                if ( v18 > 0 )
                  v8 = (unsigned __int16)v18 | 0x80070000;
                v12 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  v13 = 52;
                  goto LABEL_22;
                }
              }
            }
            else
            {
              v17 = GetLastError();
              v8 = v17;
              if ( v17 > 0 )
                v8 = (unsigned __int16)v17 | 0x80070000;
              v12 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v13 = 51;
                goto LABEL_22;
              }
            }
          }
          else
          {
            v16 = GetLastError();
            v8 = v16;
            if ( v16 > 0 )
              v8 = (unsigned __int16)v16 | 0x80070000;
            v12 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v13 = 50;
              goto LABEL_22;
            }
          }
        }
        else
        {
          v15 = GetLastError();
          v8 = v15;
          if ( v15 > 0 )
            v8 = (unsigned __int16)v15 | 0x80070000;
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v13 = 49;
            goto LABEL_22;
          }
        }
      }
      else
      {
        v14 = GetLastError();
        v8 = v14;
        if ( v14 > 0 )
          v8 = (unsigned __int16)v14 | 0x80070000;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v13 = 48;
          goto LABEL_22;
        }
      }
    }
    else
    {
      v11 = GetLastError();
      v8 = v11;
      if ( v11 > 0 )
        v8 = (unsigned __int16)v11 | 0x80070000;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v13 = 47;
LABEL_22:
        WPP_SF_D(v12[2], v13, WPP_60421427dd2a396270afbef62f846c6d_Traceguids, v8);
      }
    }
  }
  else
  {
    v8 = -2147024809;
  }
LABEL_67:
  if ( phHash )
  {
    CryptDestroyHash(phHash);
    phHash = 0;
  }
  if ( phProv[0] )
    CryptReleaseContext(phProv[0], 0);
  return v8;
}

```

## disassembly

```asm
0x180053174  mov     rax, rsp
0x180053177  mov     [rax+10h], rdx
0x18005317b  push    rbx
0x18005317c  push    rsi
0x18005317d  push    r12
0x18005317f  push    r14
0x180053181  push    r15
0x180053183  sub     rsp, 40h
0x180053187  mov     r12, r8
0x18005318a  mov     rbx, rcx
0x18005318d  mov     qword ptr [rax-30h], 0
0x180053195  mov     qword ptr [rax+20h], 0
0x18005319d  mov     dword ptr [rax+8], 0
0x1800531a4  test    rcx, rcx
0x1800531a7  jz      loc_1800535A0
0x1800531ad  cmp     rdx, 108h
0x1800531b4  jb      loc_1800535A0
0x1800531ba  test    r8, r8
0x1800531bd  jz      loc_1800535A0
0x1800531c3  lea     r8, [rcx+rdx]
0x1800531c7  cmp     r8, rcx
0x1800531ca  jb      loc_18005358A
0x1800531d0  movzx   edx, word ptr [rcx+14h]
0x1800531d4  add     rdx, 18h
0x1800531d8  add     rdx, rcx
0x1800531db  movzx   eax, word ptr [rcx+6]
0x1800531df  lea     rcx, [rax+rax*4]
0x1800531e3  lea     r14, [rdx+rcx*8]
0x1800531e7  cmp     r14, rdx
0x1800531ea  jb      loc_18005358A
0x1800531f0  cmp     r14, r8
0x1800531f3  ja      loc_18005358A
0x1800531f9  mov     eax, 10Bh
0x1800531fe  cmp     [rbx+18h], ax
0x180053202  jz      short loc_180053223
0x180053204  mov     eax, 20Bh
0x180053209  cmp     [rbx+18h], ax
0x18005320d  jz      short loc_180053219
0x18005320f  mov     ebx, 80070057h
0x180053214  jmp     loc_18005358F
0x180053219  lea     rsi, [rbx+30h]
0x18005321d  lea     r15, [rsi+8]
0x180053221  jmp     short loc_18005322B
0x180053223  lea     rsi, [rbx+34h]
0x180053227  lea     r15, [rsi+4]
0x18005322b  cmp     rsi, rbx
0x18005322e  jb      loc_18005358A
0x180053234  cmp     rsi, r14
0x180053237  jnb     loc_18005358A
0x18005323d  cmp     r15, rsi
0x180053240  jb      loc_18005358A
0x180053246  cmp     r15, r14
0x180053249  jnb     loc_18005358A
0x18005324f  mov     [rsp+68h+dwFlags], 0F0000000h; dwFlags
0x180053257  mov     r9d, 1; dwProvType
0x18005325d  lea     r8, szProvider; "Microsoft Base Cryptographic Provider v"...
0x180053264  xor     edx, edx; szContainer
0x180053266  lea     rcx, [rsp+68h+phProv]; phProv
0x18005326b  call    cs:__imp_CryptAcquireContextW
0x180053271  test    eax, eax
0x180053273  jnz     short loc_1800532CC
0x180053275  call    cs:__imp_GetLastError
0x18005327b  mov     ebx, eax
0x18005327d  test    eax, eax
0x18005327f  jle     short loc_18005328A
0x180053281  movzx   ebx, ax
0x180053284  or      ebx, 80070000h
0x18005328a  mov     [rsp+68h+var_38], ebx
0x18005328e  lea     rax, WPP_GLOBAL_Control
0x180053295  mov     rcx, cs:WPP_GLOBAL_Control
0x18005329c  cmp     rcx, rax
0x18005329f  jz      loc_180053593
0x1800532a5  test    byte ptr [rcx+1Ch], 1
0x1800532a9  jz      loc_180053593
0x1800532af  mov     edx, 2Fh ; '/'
0x1800532b4  mov     r9d, ebx
0x1800532b7  lea     r8, WPP_60421427dd2a396270afbef62f846c6d_Traceguids
0x1800532be  mov     rcx, [rcx+10h]
0x1800532c2  call    WPP_SF_D
0x1800532c7  jmp     loc_180053593
0x1800532cc  lea     rax, [rsp+68h+phHash]
0x1800532d4  mov     qword ptr [rsp+68h+dwFlags], rax; phHash
0x1800532d9  xor     r9d, r9d; dwFlags
0x1800532dc  xor     r8d, r8d; hKey
0x1800532df  mov     edx, 8004h; Algid
0x1800532e4  mov     rcx, [rsp+68h+phProv]; hProv
0x1800532e9  call    cs:__imp_CryptCreateHash
0x1800532ef  test    eax, eax
0x1800532f1  jnz     short loc_180053334
0x1800532f3  call    cs:__imp_GetLastError
0x1800532f9  mov     ebx, eax
0x1800532fb  test    eax, eax
0x1800532fd  jle     short loc_180053308
0x1800532ff  movzx   ebx, ax
0x180053302  or      ebx, 80070000h
0x180053308  mov     [rsp+68h+var_38], ebx
0x18005330c  lea     rax, WPP_GLOBAL_Control
0x180053313  mov     rcx, cs:WPP_GLOBAL_Control
0x18005331a  cmp     rcx, rax
0x18005331d  jz      loc_180053593
0x180053323  test    byte ptr [rcx+1Ch], 1
0x180053327  jz      loc_180053593
0x18005332d  mov     edx, 30h ; '0'
0x180053332  jmp     short loc_1800532B4
0x180053334  sub     esi, ebx
0x180053336  xor     r9d, r9d; dwFlags
0x180053339  mov     r8d, esi; dwDataLen
0x18005333c  mov     rdx, rbx; pbData
0x18005333f  mov     rcx, [rsp+68h+phHash]; hHash
0x180053347  call    cs:__imp_CryptHashData
0x18005334d  test    eax, eax
0x18005334f  jnz     short loc_180053395
0x180053351  call    cs:__imp_GetLastError
0x180053357  mov     ebx, eax
0x180053359  test    eax, eax
0x18005335b  jle     short loc_180053366
0x18005335d  movzx   ebx, ax
0x180053360  or      ebx, 80070000h
0x180053366  mov     [rsp+68h+var_38], ebx
0x18005336a  lea     rax, WPP_GLOBAL_Control
0x180053371  mov     rcx, cs:WPP_GLOBAL_Control
0x180053378  cmp     rcx, rax
0x18005337b  jz      loc_180053593
0x180053381  test    byte ptr [rcx+1Ch], 1
0x180053385  jz      loc_180053593
0x18005338b  mov     edx, 31h ; '1'
0x180053390  jmp     loc_1800532B4
0x180053395  sub     r14d, r15d
0x180053398  xor     r9d, r9d; dwFlags
0x18005339b  mov     r8d, r14d; dwDataLen
0x18005339e  mov     rdx, r15; pbData
0x1800533a1  mov     rcx, [rsp+68h+phHash]; hHash
0x1800533a9  call    cs:__imp_CryptHashData
0x1800533af  test    eax, eax
0x1800533b1  jnz     short loc_1800533F7
0x1800533b3  call    cs:__imp_GetLastError
0x1800533b9  mov     ebx, eax
0x1800533bb  test    eax, eax
0x1800533bd  jle     short loc_1800533C8
0x1800533bf  movzx   ebx, ax
0x1800533c2  or      ebx, 80070000h
0x1800533c8  mov     [rsp+68h+var_38], ebx
0x1800533cc  lea     rax, WPP_GLOBAL_Control
0x1800533d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800533da  cmp     rcx, rax
0x1800533dd  jz      loc_180053593
0x1800533e3  test    byte ptr [rcx+1Ch], 1
0x1800533e7  jz      loc_180053593
0x1800533ed  mov     edx, 32h ; '2'
0x1800533f2  jmp     loc_1800532B4
0x1800533f7  xor     r9d, r9d; dwFlags
0x1800533fa  lea     r8d, [r9+8]; dwDataLen
0x1800533fe  lea     rdx, [rsp+68h+pbData]; pbData
0x180053403  mov     rcx, [rsp+68h+phHash]; hHash
0x18005340b  call    cs:__imp_CryptHashData
0x180053411  test    eax, eax
0x180053413  jnz     short loc_180053459
0x180053415  call    cs:__imp_GetLastError
0x18005341b  mov     ebx, eax
0x18005341d  test    eax, eax
0x18005341f  jle     short loc_18005342A
0x180053421  movzx   ebx, ax
0x180053424  or      ebx, 80070000h
0x18005342a  mov     [rsp+68h+var_38], ebx
0x18005342e  lea     rax, WPP_GLOBAL_Control
0x180053435  mov     rcx, cs:WPP_GLOBAL_Control
0x18005343c  cmp     rcx, rax
0x18005343f  jz      loc_180053593
0x180053445  test    byte ptr [rcx+1Ch], 1
0x180053449  jz      loc_180053593
0x18005344f  mov     edx, 33h ; '3'
0x180053454  jmp     loc_1800532B4
0x180053459  mov     [rsp+68h+pdwDataLen], 0
0x180053461  xorps   xmm0, xmm0
0x180053464  xor     eax, eax
0x180053466  movups  xmmword ptr [r12], xmm0
0x18005346b  mov     [r12+0Eh], rax
0x180053470  mov     [rsp+68h+dwFlags], eax; dwFlags
0x180053474  lea     r9, [rsp+68h+pdwDataLen]; pdwDataLen
0x180053479  xor     r8d, r8d; pbData
0x18005347c  lea     ebx, [rax+2]
0x18005347f  mov     edx, ebx; dwParam
0x180053481  mov     rcx, [rsp+68h+phHash]; hHash
0x180053489  call    cs:__imp_CryptGetHashParam
0x18005348f  test    eax, eax
0x180053491  jnz     short loc_1800534D7
0x180053493  call    cs:__imp_GetLastError
0x180053499  mov     ebx, eax
0x18005349b  test    eax, eax
0x18005349d  jle     short loc_1800534A8
0x18005349f  movzx   ebx, ax
0x1800534a2  or      ebx, 80070000h
0x1800534a8  mov     [rsp+68h+var_38], ebx
0x1800534ac  lea     rax, WPP_GLOBAL_Control
0x1800534b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800534ba  cmp     rcx, rax
0x1800534bd  jz      loc_180053593
0x1800534c3  test    byte ptr [rcx+1Ch], 1
0x1800534c7  jz      loc_180053593
0x1800534cd  mov     edx, 34h ; '4'
0x1800534d2  jmp     loc_1800532B4
0x1800534d7  cmp     [rsp+68h+pdwDataLen], 14h
0x1800534dc  jz      short loc_18005351F
0x1800534de  mov     ebx, 8000FFFFh
0x1800534e3  mov     [rsp+68h+var_38], ebx
0x1800534e7  lea     rax, WPP_GLOBAL_Control
0x1800534ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800534f5  cmp     rcx, rax
0x1800534f8  jz      loc_180053593
0x1800534fe  test    byte ptr [rcx+1Ch], 1
0x180053502  jz      loc_180053593
0x180053508  mov     edx, 35h ; '5'
0x18005350d  lea     r8, WPP_60421427dd2a396270afbef62f846c6d_Traceguids
0x180053514  mov     rcx, [rcx+10h]
0x180053518  call    WPP_SF_
0x18005351d  jmp     short loc_180053593
0x18005351f  lea     r8, [r12+2]; pbData
0x180053524  mov     [rsp+68h+dwFlags], 0; dwFlags
0x18005352c  lea     r9, [rsp+68h+pdwDataLen]; pdwDataLen
0x180053531  mov     edx, ebx; dwParam
0x180053533  mov     rcx, [rsp+68h+phHash]; hHash
0x18005353b  call    cs:__imp_CryptGetHashParam
0x180053541  test    eax, eax
0x180053543  jnz     short loc_180053581
0x180053545  call    cs:__imp_GetLastError
0x18005354b  mov     ebx, eax
0x18005354d  test    eax, eax
0x18005354f  jle     short loc_18005355A
0x180053551  movzx   ebx, ax
0x180053554  or      ebx, 80070000h
0x18005355a  mov     [rsp+68h+var_38], ebx
0x18005355e  lea     rax, WPP_GLOBAL_Control
0x180053565  mov     rcx, cs:WPP_GLOBAL_Control
0x18005356c  cmp     rcx, rax
0x18005356f  jz      short loc_180053593
0x180053571  test    byte ptr [rcx+1Ch], 1
0x180053575  jz      short loc_180053593
0x180053577  mov     edx, 36h ; '6'
0x18005357c  jmp     loc_1800532B4
0x180053581  mov     byte ptr [r12], 1
0x180053586  xor     ebx, ebx
0x180053588  jmp     short loc_18005358F
0x18005358a  mov     ebx, 0D000007Bh
0x18005358f  mov     [rsp+68h+var_38], ebx
0x180053593  jmp     short loc_1800535A5
0x180053595  mov     ebx, 80004005h
0x18005359a  mov     [rsp+68h+var_38], ebx
0x18005359e  jmp     short loc_1800535A5
0x1800535a0  mov     ebx, 80070057h
0x1800535a5  mov     rcx, [rsp+68h+phHash]; hHash
0x1800535ad  test    rcx, rcx
0x1800535b0  jz      short loc_1800535C4
0x1800535b2  call    cs:__imp_CryptDestroyHash
0x1800535b8  mov     [rsp+68h+phHash], 0
0x1800535c4  mov     rcx, [rsp+68h+phProv]; hProv
0x1800535c9  test    rcx, rcx
0x1800535cc  jz      short loc_1800535D6
0x1800535ce  xor     edx, edx; dwFlags
0x1800535d0  call    cs:__imp_CryptReleaseContext
0x1800535d6  mov     eax, ebx
0x1800535d8  add     rsp, 40h
0x1800535dc  pop     r15
0x1800535de  pop     r14
0x1800535e0  pop     r12
0x1800535e2  pop     rsi
0x1800535e3  pop     rbx
0x1800535e4  retn
0x1800e9bf3  push    rbp
0x1800e9bf5  sub     rsp, 30h
0x1800e9bf9  mov     rbp, rdx
0x1800e9bfc  call    ?PageErrorExceptionHandler@@YAKPEAU_EXCEPTION_POINTERS@@PEBDK@Z; PageErrorExceptionHandler(_EXCEPTION_POINTERS *,char const *,ulong)
0x1800e9c01  nop
0x1800e9c02  add     rsp, 30h
0x1800e9c06  pop     rbp
0x1800e9c07  retn
```
