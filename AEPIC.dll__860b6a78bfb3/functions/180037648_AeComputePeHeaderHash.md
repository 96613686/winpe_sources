# AeComputePeHeaderHash

- ea: `0x180037648`
- end: `0x180037ab9`
- name: `AeComputePeHeaderHash`
- size: `1137`
- prototype: `__int64 __fastcall(BYTE *pbData, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800e3f00`

## callees

- `0x180036ed4`
- `0x180037648`
- `0x18003807c`
- `0x1800380a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037749`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800377c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037825`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037887`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800378e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037967`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037a19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037749`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800377c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037825`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037887`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800378e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037967`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037a19`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x180037a86`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x180037a86`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x1800377bd`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x1800377bd`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x18003773f`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x18003773f`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18003781b`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18003787d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x1800378df`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18003781b`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18003787d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x1800378df`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180037aa4`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180037aa4`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18003795d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180037a0f`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18003795d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180037a0f`

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
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_ff13ec65e0c03369507e3b373b281b2e_Traceguids);
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
        WPP_SF_D(v12[2], v13, WPP_ff13ec65e0c03369507e3b373b281b2e_Traceguids, v8);
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
0x180037648  mov     rax, rsp
0x18003764b  mov     [rax+10h], rdx
0x18003764f  push    rbx
0x180037650  push    rsi
0x180037651  push    r12
0x180037653  push    r14
0x180037655  push    r15
0x180037657  sub     rsp, 40h
0x18003765b  mov     r12, r8
0x18003765e  mov     rbx, rcx
0x180037661  mov     qword ptr [rax-30h], 0
0x180037669  mov     qword ptr [rax+20h], 0
0x180037671  mov     dword ptr [rax+8], 0
0x180037678  test    rcx, rcx
0x18003767b  jz      loc_180037A74
0x180037681  cmp     rdx, 108h
0x180037688  jb      loc_180037A74
0x18003768e  test    r8, r8
0x180037691  jz      loc_180037A74
0x180037697  lea     r8, [rcx+rdx]
0x18003769b  cmp     r8, rcx
0x18003769e  jb      loc_180037A5E
0x1800376a4  movzx   edx, word ptr [rcx+14h]
0x1800376a8  add     rdx, 18h
0x1800376ac  add     rdx, rcx
0x1800376af  movzx   eax, word ptr [rcx+6]
0x1800376b3  lea     rcx, [rax+rax*4]
0x1800376b7  lea     r14, [rdx+rcx*8]
0x1800376bb  cmp     r14, rdx
0x1800376be  jb      loc_180037A5E
0x1800376c4  cmp     r14, r8
0x1800376c7  ja      loc_180037A5E
0x1800376cd  mov     eax, 10Bh
0x1800376d2  cmp     [rbx+18h], ax
0x1800376d6  jz      short loc_1800376F7
0x1800376d8  mov     eax, 20Bh
0x1800376dd  cmp     [rbx+18h], ax
0x1800376e1  jz      short loc_1800376ED
0x1800376e3  mov     ebx, 80070057h
0x1800376e8  jmp     loc_180037A63
0x1800376ed  lea     rsi, [rbx+30h]
0x1800376f1  lea     r15, [rsi+8]
0x1800376f5  jmp     short loc_1800376FF
0x1800376f7  lea     rsi, [rbx+34h]
0x1800376fb  lea     r15, [rsi+4]
0x1800376ff  cmp     rsi, rbx
0x180037702  jb      loc_180037A5E
0x180037708  cmp     rsi, r14
0x18003770b  jnb     loc_180037A5E
0x180037711  cmp     r15, rsi
0x180037714  jb      loc_180037A5E
0x18003771a  cmp     r15, r14
0x18003771d  jnb     loc_180037A5E
0x180037723  mov     [rsp+68h+dwFlags], 0F0000000h; dwFlags
0x18003772b  mov     r9d, 1; dwProvType
0x180037731  lea     r8, szProvider; "Microsoft Base Cryptographic Provider v"...
0x180037738  xor     edx, edx; szContainer
0x18003773a  lea     rcx, [rsp+68h+phProv]; phProv
0x18003773f  call    cs:__imp_CryptAcquireContextW
0x180037745  test    eax, eax
0x180037747  jnz     short loc_1800377A0
0x180037749  call    cs:__imp_GetLastError
0x18003774f  mov     ebx, eax
0x180037751  test    eax, eax
0x180037753  jle     short loc_18003775E
0x180037755  movzx   ebx, ax
0x180037758  or      ebx, 80070000h
0x18003775e  mov     [rsp+68h+var_38], ebx
0x180037762  lea     rax, WPP_GLOBAL_Control
0x180037769  mov     rcx, cs:WPP_GLOBAL_Control
0x180037770  cmp     rcx, rax
0x180037773  jz      loc_180037A67
0x180037779  test    byte ptr [rcx+1Ch], 1
0x18003777d  jz      loc_180037A67
0x180037783  mov     edx, 2Fh ; '/'
0x180037788  mov     r9d, ebx
0x18003778b  lea     r8, WPP_ff13ec65e0c03369507e3b373b281b2e_Traceguids
0x180037792  mov     rcx, [rcx+10h]
0x180037796  call    WPP_SF_D
0x18003779b  jmp     loc_180037A67
0x1800377a0  lea     rax, [rsp+68h+phHash]
0x1800377a8  mov     qword ptr [rsp+68h+dwFlags], rax; phHash
0x1800377ad  xor     r9d, r9d; dwFlags
0x1800377b0  xor     r8d, r8d; hKey
0x1800377b3  mov     edx, 8004h; Algid
0x1800377b8  mov     rcx, [rsp+68h+phProv]; hProv
0x1800377bd  call    cs:__imp_CryptCreateHash
0x1800377c3  test    eax, eax
0x1800377c5  jnz     short loc_180037808
0x1800377c7  call    cs:__imp_GetLastError
0x1800377cd  mov     ebx, eax
0x1800377cf  test    eax, eax
0x1800377d1  jle     short loc_1800377DC
0x1800377d3  movzx   ebx, ax
0x1800377d6  or      ebx, 80070000h
0x1800377dc  mov     [rsp+68h+var_38], ebx
0x1800377e0  lea     rax, WPP_GLOBAL_Control
0x1800377e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800377ee  cmp     rcx, rax
0x1800377f1  jz      loc_180037A67
0x1800377f7  test    byte ptr [rcx+1Ch], 1
0x1800377fb  jz      loc_180037A67
0x180037801  mov     edx, 30h ; '0'
0x180037806  jmp     short loc_180037788
0x180037808  sub     esi, ebx
0x18003780a  xor     r9d, r9d; dwFlags
0x18003780d  mov     r8d, esi; dwDataLen
0x180037810  mov     rdx, rbx; pbData
0x180037813  mov     rcx, [rsp+68h+phHash]; hHash
0x18003781b  call    cs:__imp_CryptHashData
0x180037821  test    eax, eax
0x180037823  jnz     short loc_180037869
0x180037825  call    cs:__imp_GetLastError
0x18003782b  mov     ebx, eax
0x18003782d  test    eax, eax
0x18003782f  jle     short loc_18003783A
0x180037831  movzx   ebx, ax
0x180037834  or      ebx, 80070000h
0x18003783a  mov     [rsp+68h+var_38], ebx
0x18003783e  lea     rax, WPP_GLOBAL_Control
0x180037845  mov     rcx, cs:WPP_GLOBAL_Control
0x18003784c  cmp     rcx, rax
0x18003784f  jz      loc_180037A67
0x180037855  test    byte ptr [rcx+1Ch], 1
0x180037859  jz      loc_180037A67
0x18003785f  mov     edx, 31h ; '1'
0x180037864  jmp     loc_180037788
0x180037869  sub     r14d, r15d
0x18003786c  xor     r9d, r9d; dwFlags
0x18003786f  mov     r8d, r14d; dwDataLen
0x180037872  mov     rdx, r15; pbData
0x180037875  mov     rcx, [rsp+68h+phHash]; hHash
0x18003787d  call    cs:__imp_CryptHashData
0x180037883  test    eax, eax
0x180037885  jnz     short loc_1800378CB
0x180037887  call    cs:__imp_GetLastError
0x18003788d  mov     ebx, eax
0x18003788f  test    eax, eax
0x180037891  jle     short loc_18003789C
0x180037893  movzx   ebx, ax
0x180037896  or      ebx, 80070000h
0x18003789c  mov     [rsp+68h+var_38], ebx
0x1800378a0  lea     rax, WPP_GLOBAL_Control
0x1800378a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800378ae  cmp     rcx, rax
0x1800378b1  jz      loc_180037A67
0x1800378b7  test    byte ptr [rcx+1Ch], 1
0x1800378bb  jz      loc_180037A67
0x1800378c1  mov     edx, 32h ; '2'
0x1800378c6  jmp     loc_180037788
0x1800378cb  xor     r9d, r9d; dwFlags
0x1800378ce  lea     r8d, [r9+8]; dwDataLen
0x1800378d2  lea     rdx, [rsp+68h+pbData]; pbData
0x1800378d7  mov     rcx, [rsp+68h+phHash]; hHash
0x1800378df  call    cs:__imp_CryptHashData
0x1800378e5  test    eax, eax
0x1800378e7  jnz     short loc_18003792D
0x1800378e9  call    cs:__imp_GetLastError
0x1800378ef  mov     ebx, eax
0x1800378f1  test    eax, eax
0x1800378f3  jle     short loc_1800378FE
0x1800378f5  movzx   ebx, ax
0x1800378f8  or      ebx, 80070000h
0x1800378fe  mov     [rsp+68h+var_38], ebx
0x180037902  lea     rax, WPP_GLOBAL_Control
0x180037909  mov     rcx, cs:WPP_GLOBAL_Control
0x180037910  cmp     rcx, rax
0x180037913  jz      loc_180037A67
0x180037919  test    byte ptr [rcx+1Ch], 1
0x18003791d  jz      loc_180037A67
0x180037923  mov     edx, 33h ; '3'
0x180037928  jmp     loc_180037788
0x18003792d  mov     [rsp+68h+pdwDataLen], 0
0x180037935  xorps   xmm0, xmm0
0x180037938  xor     eax, eax
0x18003793a  movups  xmmword ptr [r12], xmm0
0x18003793f  mov     [r12+0Eh], rax
0x180037944  mov     [rsp+68h+dwFlags], eax; dwFlags
0x180037948  lea     r9, [rsp+68h+pdwDataLen]; pdwDataLen
0x18003794d  xor     r8d, r8d; pbData
0x180037950  lea     ebx, [rax+2]
0x180037953  mov     edx, ebx; dwParam
0x180037955  mov     rcx, [rsp+68h+phHash]; hHash
0x18003795d  call    cs:__imp_CryptGetHashParam
0x180037963  test    eax, eax
0x180037965  jnz     short loc_1800379AB
0x180037967  call    cs:__imp_GetLastError
0x18003796d  mov     ebx, eax
0x18003796f  test    eax, eax
0x180037971  jle     short loc_18003797C
0x180037973  movzx   ebx, ax
0x180037976  or      ebx, 80070000h
0x18003797c  mov     [rsp+68h+var_38], ebx
0x180037980  lea     rax, WPP_GLOBAL_Control
0x180037987  mov     rcx, cs:WPP_GLOBAL_Control
0x18003798e  cmp     rcx, rax
0x180037991  jz      loc_180037A67
0x180037997  test    byte ptr [rcx+1Ch], 1
0x18003799b  jz      loc_180037A67
0x1800379a1  mov     edx, 34h ; '4'
0x1800379a6  jmp     loc_180037788
0x1800379ab  cmp     [rsp+68h+pdwDataLen], 14h
0x1800379b0  jz      short loc_1800379F3
0x1800379b2  mov     ebx, 8000FFFFh
0x1800379b7  mov     [rsp+68h+var_38], ebx
0x1800379bb  lea     rax, WPP_GLOBAL_Control
0x1800379c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800379c9  cmp     rcx, rax
0x1800379cc  jz      loc_180037A67
0x1800379d2  test    byte ptr [rcx+1Ch], 1
0x1800379d6  jz      loc_180037A67
0x1800379dc  mov     edx, 35h ; '5'
0x1800379e1  lea     r8, WPP_ff13ec65e0c03369507e3b373b281b2e_Traceguids
0x1800379e8  mov     rcx, [rcx+10h]
0x1800379ec  call    WPP_SF_
0x1800379f1  jmp     short loc_180037A67
0x1800379f3  lea     r8, [r12+2]; pbData
0x1800379f8  mov     [rsp+68h+dwFlags], 0; dwFlags
0x180037a00  lea     r9, [rsp+68h+pdwDataLen]; pdwDataLen
0x180037a05  mov     edx, ebx; dwParam
0x180037a07  mov     rcx, [rsp+68h+phHash]; hHash
0x180037a0f  call    cs:__imp_CryptGetHashParam
0x180037a15  test    eax, eax
0x180037a17  jnz     short loc_180037A55
0x180037a19  call    cs:__imp_GetLastError
0x180037a1f  mov     ebx, eax
0x180037a21  test    eax, eax
0x180037a23  jle     short loc_180037A2E
0x180037a25  movzx   ebx, ax
0x180037a28  or      ebx, 80070000h
0x180037a2e  mov     [rsp+68h+var_38], ebx
0x180037a32  lea     rax, WPP_GLOBAL_Control
0x180037a39  mov     rcx, cs:WPP_GLOBAL_Control
0x180037a40  cmp     rcx, rax
0x180037a43  jz      short loc_180037A67
0x180037a45  test    byte ptr [rcx+1Ch], 1
0x180037a49  jz      short loc_180037A67
0x180037a4b  mov     edx, 36h ; '6'
0x180037a50  jmp     loc_180037788
0x180037a55  mov     byte ptr [r12], 1
0x180037a5a  xor     ebx, ebx
0x180037a5c  jmp     short loc_180037A63
0x180037a5e  mov     ebx, 0D000007Bh
0x180037a63  mov     [rsp+68h+var_38], ebx
0x180037a67  jmp     short loc_180037A79
0x180037a69  mov     ebx, 80004005h
0x180037a6e  mov     [rsp+68h+var_38], ebx
0x180037a72  jmp     short loc_180037A79
0x180037a74  mov     ebx, 80070057h
0x180037a79  mov     rcx, [rsp+68h+phHash]; hHash
0x180037a81  test    rcx, rcx
0x180037a84  jz      short loc_180037A98
0x180037a86  call    cs:__imp_CryptDestroyHash
0x180037a8c  mov     [rsp+68h+phHash], 0
0x180037a98  mov     rcx, [rsp+68h+phProv]; hProv
0x180037a9d  test    rcx, rcx
0x180037aa0  jz      short loc_180037AAA
0x180037aa2  xor     edx, edx; dwFlags
0x180037aa4  call    cs:__imp_CryptReleaseContext
0x180037aaa  mov     eax, ebx
0x180037aac  add     rsp, 40h
0x180037ab0  pop     r15
0x180037ab2  pop     r14
0x180037ab4  pop     r12
0x180037ab6  pop     rsi
0x180037ab7  pop     rbx
0x180037ab8  retn
0x1800e65cb  push    rbp
0x1800e65cd  sub     rsp, 30h
0x1800e65d1  mov     rbp, rdx
0x1800e65d4  call    ?PageErrorExceptionHandler@@YAKPEAU_EXCEPTION_POINTERS@@PEBDK@Z; PageErrorExceptionHandler(_EXCEPTION_POINTERS *,char const *,ulong)
0x1800e65d9  nop
0x1800e65da  add     rsp, 30h
0x1800e65de  pop     rbp
0x1800e65df  retn
```
