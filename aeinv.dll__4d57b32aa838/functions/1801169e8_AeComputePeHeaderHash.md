# AeComputePeHeaderHash

- ea: `0x1801169e8`
- end: `0x180116e59`
- name: `AeComputePeHeaderHash`
- size: `1137`
- prototype: `__int64 __fastcall(BYTE *pbData, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180117600`

## callees

- `0x1801167f0`
- `0x18011698c`
- `0x1801169e8`
- `0x180116eac`

## import_xrefs

- `ADVAPI32!CryptAcquireContextW` at `0x180116adf`
- `ADVAPI32!CryptAcquireContextW` at `0x180116adf`
- `ADVAPI32!CryptCreateHash` at `0x180116b5d`
- `ADVAPI32!CryptCreateHash` at `0x180116b5d`
- `ADVAPI32!CryptHashData` at `0x180116bbb`
- `ADVAPI32!CryptHashData` at `0x180116c1d`
- `ADVAPI32!CryptHashData` at `0x180116c7f`
- `ADVAPI32!CryptHashData` at `0x180116bbb`
- `ADVAPI32!CryptHashData` at `0x180116c1d`
- `ADVAPI32!CryptHashData` at `0x180116c7f`
- `ADVAPI32!CryptDestroyHash` at `0x180116e26`
- `ADVAPI32!CryptDestroyHash` at `0x180116e26`
- `ADVAPI32!CryptGetHashParam` at `0x180116cfd`
- `ADVAPI32!CryptGetHashParam` at `0x180116daf`
- `ADVAPI32!CryptGetHashParam` at `0x180116cfd`
- `ADVAPI32!CryptGetHashParam` at `0x180116daf`
- `ADVAPI32!CryptReleaseContext` at `0x180116e44`
- `ADVAPI32!CryptReleaseContext` at `0x180116e44`
- `KERNEL32!GetLastError` at `0x180116ae9`
- `KERNEL32!GetLastError` at `0x180116b67`
- `KERNEL32!GetLastError` at `0x180116bc5`
- `KERNEL32!GetLastError` at `0x180116c27`
- `KERNEL32!GetLastError` at `0x180116c89`
- `KERNEL32!GetLastError` at `0x180116d07`
- `KERNEL32!GetLastError` at `0x180116db9`
- `KERNEL32!GetLastError` at `0x180116ae9`
- `KERNEL32!GetLastError` at `0x180116b67`
- `KERNEL32!GetLastError` at `0x180116bc5`
- `KERNEL32!GetLastError` at `0x180116c27`
- `KERNEL32!GetLastError` at `0x180116c89`
- `KERNEL32!GetLastError` at `0x180116d07`
- `KERNEL32!GetLastError` at `0x180116db9`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
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
0x1801169e8  mov     rax, rsp
0x1801169eb  mov     [rax+10h], rdx
0x1801169ef  push    rbx
0x1801169f0  push    rsi
0x1801169f1  push    r12
0x1801169f3  push    r14
0x1801169f5  push    r15
0x1801169f7  sub     rsp, 40h
0x1801169fb  mov     r12, r8
0x1801169fe  mov     rbx, rcx
0x180116a01  mov     qword ptr [rax-30h], 0
0x180116a09  mov     qword ptr [rax+20h], 0
0x180116a11  mov     dword ptr [rax+8], 0
0x180116a18  test    rcx, rcx
0x180116a1b  jz      loc_180116E14
0x180116a21  cmp     rdx, 108h
0x180116a28  jb      loc_180116E14
0x180116a2e  test    r8, r8
0x180116a31  jz      loc_180116E14
0x180116a37  lea     r8, [rcx+rdx]
0x180116a3b  cmp     r8, rcx
0x180116a3e  jb      loc_180116DFE
0x180116a44  movzx   edx, word ptr [rcx+14h]
0x180116a48  add     rdx, 18h
0x180116a4c  add     rdx, rcx
0x180116a4f  movzx   eax, word ptr [rcx+6]
0x180116a53  lea     rcx, [rax+rax*4]
0x180116a57  lea     r14, [rdx+rcx*8]
0x180116a5b  cmp     r14, rdx
0x180116a5e  jb      loc_180116DFE
0x180116a64  cmp     r14, r8
0x180116a67  ja      loc_180116DFE
0x180116a6d  mov     eax, 10Bh
0x180116a72  cmp     [rbx+18h], ax
0x180116a76  jz      short loc_180116A97
0x180116a78  mov     eax, 20Bh
0x180116a7d  cmp     [rbx+18h], ax
0x180116a81  jz      short loc_180116A8D
0x180116a83  mov     ebx, 80070057h
0x180116a88  jmp     loc_180116E03
0x180116a8d  lea     rsi, [rbx+30h]
0x180116a91  lea     r15, [rsi+8]
0x180116a95  jmp     short loc_180116A9F
0x180116a97  lea     rsi, [rbx+34h]
0x180116a9b  lea     r15, [rsi+4]
0x180116a9f  cmp     rsi, rbx
0x180116aa2  jb      loc_180116DFE
0x180116aa8  cmp     rsi, r14
0x180116aab  jnb     loc_180116DFE
0x180116ab1  cmp     r15, rsi
0x180116ab4  jb      loc_180116DFE
0x180116aba  cmp     r15, r14
0x180116abd  jnb     loc_180116DFE
0x180116ac3  mov     [rsp+68h+dwFlags], 0F0000000h; dwFlags
0x180116acb  mov     r9d, 1; dwProvType
0x180116ad1  lea     r8, szProvider; "Microsoft Base Cryptographic Provider v"...
0x180116ad8  xor     edx, edx; szContainer
0x180116ada  lea     rcx, [rsp+68h+phProv]; phProv
0x180116adf  call    cs:__imp_CryptAcquireContextW
0x180116ae5  test    eax, eax
0x180116ae7  jnz     short loc_180116B40
0x180116ae9  call    cs:__imp_GetLastError
0x180116aef  mov     ebx, eax
0x180116af1  test    eax, eax
0x180116af3  jle     short loc_180116AFE
0x180116af5  movzx   ebx, ax
0x180116af8  or      ebx, 80070000h
0x180116afe  mov     [rsp+68h+var_38], ebx
0x180116b02  lea     rax, WPP_GLOBAL_Control
0x180116b09  mov     rcx, cs:WPP_GLOBAL_Control
0x180116b10  cmp     rcx, rax
0x180116b13  jz      loc_180116E07
0x180116b19  test    byte ptr [rcx+1Ch], 1
0x180116b1d  jz      loc_180116E07
0x180116b23  mov     edx, 2Fh ; '/'
0x180116b28  mov     r9d, ebx
0x180116b2b  lea     r8, WPP_60421427dd2a396270afbef62f846c6d_Traceguids
0x180116b32  mov     rcx, [rcx+10h]
0x180116b36  call    WPP_SF_D
0x180116b3b  jmp     loc_180116E07
0x180116b40  lea     rax, [rsp+68h+phHash]
0x180116b48  mov     qword ptr [rsp+68h+dwFlags], rax; phHash
0x180116b4d  xor     r9d, r9d; dwFlags
0x180116b50  xor     r8d, r8d; hKey
0x180116b53  mov     edx, 8004h; Algid
0x180116b58  mov     rcx, [rsp+68h+phProv]; hProv
0x180116b5d  call    cs:__imp_CryptCreateHash
0x180116b63  test    eax, eax
0x180116b65  jnz     short loc_180116BA8
0x180116b67  call    cs:__imp_GetLastError
0x180116b6d  mov     ebx, eax
0x180116b6f  test    eax, eax
0x180116b71  jle     short loc_180116B7C
0x180116b73  movzx   ebx, ax
0x180116b76  or      ebx, 80070000h
0x180116b7c  mov     [rsp+68h+var_38], ebx
0x180116b80  lea     rax, WPP_GLOBAL_Control
0x180116b87  mov     rcx, cs:WPP_GLOBAL_Control
0x180116b8e  cmp     rcx, rax
0x180116b91  jz      loc_180116E07
0x180116b97  test    byte ptr [rcx+1Ch], 1
0x180116b9b  jz      loc_180116E07
0x180116ba1  mov     edx, 30h ; '0'
0x180116ba6  jmp     short loc_180116B28
0x180116ba8  sub     esi, ebx
0x180116baa  xor     r9d, r9d; dwFlags
0x180116bad  mov     r8d, esi; dwDataLen
0x180116bb0  mov     rdx, rbx; pbData
0x180116bb3  mov     rcx, [rsp+68h+phHash]; hHash
0x180116bbb  call    cs:__imp_CryptHashData
0x180116bc1  test    eax, eax
0x180116bc3  jnz     short loc_180116C09
0x180116bc5  call    cs:__imp_GetLastError
0x180116bcb  mov     ebx, eax
0x180116bcd  test    eax, eax
0x180116bcf  jle     short loc_180116BDA
0x180116bd1  movzx   ebx, ax
0x180116bd4  or      ebx, 80070000h
0x180116bda  mov     [rsp+68h+var_38], ebx
0x180116bde  lea     rax, WPP_GLOBAL_Control
0x180116be5  mov     rcx, cs:WPP_GLOBAL_Control
0x180116bec  cmp     rcx, rax
0x180116bef  jz      loc_180116E07
0x180116bf5  test    byte ptr [rcx+1Ch], 1
0x180116bf9  jz      loc_180116E07
0x180116bff  mov     edx, 31h ; '1'
0x180116c04  jmp     loc_180116B28
0x180116c09  sub     r14d, r15d
0x180116c0c  xor     r9d, r9d; dwFlags
0x180116c0f  mov     r8d, r14d; dwDataLen
0x180116c12  mov     rdx, r15; pbData
0x180116c15  mov     rcx, [rsp+68h+phHash]; hHash
0x180116c1d  call    cs:__imp_CryptHashData
0x180116c23  test    eax, eax
0x180116c25  jnz     short loc_180116C6B
0x180116c27  call    cs:__imp_GetLastError
0x180116c2d  mov     ebx, eax
0x180116c2f  test    eax, eax
0x180116c31  jle     short loc_180116C3C
0x180116c33  movzx   ebx, ax
0x180116c36  or      ebx, 80070000h
0x180116c3c  mov     [rsp+68h+var_38], ebx
0x180116c40  lea     rax, WPP_GLOBAL_Control
0x180116c47  mov     rcx, cs:WPP_GLOBAL_Control
0x180116c4e  cmp     rcx, rax
0x180116c51  jz      loc_180116E07
0x180116c57  test    byte ptr [rcx+1Ch], 1
0x180116c5b  jz      loc_180116E07
0x180116c61  mov     edx, 32h ; '2'
0x180116c66  jmp     loc_180116B28
0x180116c6b  xor     r9d, r9d; dwFlags
0x180116c6e  lea     r8d, [r9+8]; dwDataLen
0x180116c72  lea     rdx, [rsp+68h+pbData]; pbData
0x180116c77  mov     rcx, [rsp+68h+phHash]; hHash
0x180116c7f  call    cs:__imp_CryptHashData
0x180116c85  test    eax, eax
0x180116c87  jnz     short loc_180116CCD
0x180116c89  call    cs:__imp_GetLastError
0x180116c8f  mov     ebx, eax
0x180116c91  test    eax, eax
0x180116c93  jle     short loc_180116C9E
0x180116c95  movzx   ebx, ax
0x180116c98  or      ebx, 80070000h
0x180116c9e  mov     [rsp+68h+var_38], ebx
0x180116ca2  lea     rax, WPP_GLOBAL_Control
0x180116ca9  mov     rcx, cs:WPP_GLOBAL_Control
0x180116cb0  cmp     rcx, rax
0x180116cb3  jz      loc_180116E07
0x180116cb9  test    byte ptr [rcx+1Ch], 1
0x180116cbd  jz      loc_180116E07
0x180116cc3  mov     edx, 33h ; '3'
0x180116cc8  jmp     loc_180116B28
0x180116ccd  mov     [rsp+68h+pdwDataLen], 0
0x180116cd5  xorps   xmm0, xmm0
0x180116cd8  xor     eax, eax
0x180116cda  movups  xmmword ptr [r12], xmm0
0x180116cdf  mov     [r12+0Eh], rax
0x180116ce4  mov     [rsp+68h+dwFlags], eax; dwFlags
0x180116ce8  lea     r9, [rsp+68h+pdwDataLen]; pdwDataLen
0x180116ced  xor     r8d, r8d; pbData
0x180116cf0  lea     ebx, [rax+2]
0x180116cf3  mov     edx, ebx; dwParam
0x180116cf5  mov     rcx, [rsp+68h+phHash]; hHash
0x180116cfd  call    cs:__imp_CryptGetHashParam
0x180116d03  test    eax, eax
0x180116d05  jnz     short loc_180116D4B
0x180116d07  call    cs:__imp_GetLastError
0x180116d0d  mov     ebx, eax
0x180116d0f  test    eax, eax
0x180116d11  jle     short loc_180116D1C
0x180116d13  movzx   ebx, ax
0x180116d16  or      ebx, 80070000h
0x180116d1c  mov     [rsp+68h+var_38], ebx
0x180116d20  lea     rax, WPP_GLOBAL_Control
0x180116d27  mov     rcx, cs:WPP_GLOBAL_Control
0x180116d2e  cmp     rcx, rax
0x180116d31  jz      loc_180116E07
0x180116d37  test    byte ptr [rcx+1Ch], 1
0x180116d3b  jz      loc_180116E07
0x180116d41  mov     edx, 34h ; '4'
0x180116d46  jmp     loc_180116B28
0x180116d4b  cmp     [rsp+68h+pdwDataLen], 14h
0x180116d50  jz      short loc_180116D93
0x180116d52  mov     ebx, 8000FFFFh
0x180116d57  mov     [rsp+68h+var_38], ebx
0x180116d5b  lea     rax, WPP_GLOBAL_Control
0x180116d62  mov     rcx, cs:WPP_GLOBAL_Control
0x180116d69  cmp     rcx, rax
0x180116d6c  jz      loc_180116E07
0x180116d72  test    byte ptr [rcx+1Ch], 1
0x180116d76  jz      loc_180116E07
0x180116d7c  mov     edx, 35h ; '5'
0x180116d81  lea     r8, WPP_60421427dd2a396270afbef62f846c6d_Traceguids
0x180116d88  mov     rcx, [rcx+10h]
0x180116d8c  call    WPP_SF_
0x180116d91  jmp     short loc_180116E07
0x180116d93  lea     r8, [r12+2]; pbData
0x180116d98  mov     [rsp+68h+dwFlags], 0; dwFlags
0x180116da0  lea     r9, [rsp+68h+pdwDataLen]; pdwDataLen
0x180116da5  mov     edx, ebx; dwParam
0x180116da7  mov     rcx, [rsp+68h+phHash]; hHash
0x180116daf  call    cs:__imp_CryptGetHashParam
0x180116db5  test    eax, eax
0x180116db7  jnz     short loc_180116DF5
0x180116db9  call    cs:__imp_GetLastError
0x180116dbf  mov     ebx, eax
0x180116dc1  test    eax, eax
0x180116dc3  jle     short loc_180116DCE
0x180116dc5  movzx   ebx, ax
0x180116dc8  or      ebx, 80070000h
0x180116dce  mov     [rsp+68h+var_38], ebx
0x180116dd2  lea     rax, WPP_GLOBAL_Control
0x180116dd9  mov     rcx, cs:WPP_GLOBAL_Control
0x180116de0  cmp     rcx, rax
0x180116de3  jz      short loc_180116E07
0x180116de5  test    byte ptr [rcx+1Ch], 1
0x180116de9  jz      short loc_180116E07
0x180116deb  mov     edx, 36h ; '6'
0x180116df0  jmp     loc_180116B28
0x180116df5  mov     byte ptr [r12], 1
0x180116dfa  xor     ebx, ebx
0x180116dfc  jmp     short loc_180116E03
0x180116dfe  mov     ebx, 0D000007Bh
0x180116e03  mov     [rsp+68h+var_38], ebx
0x180116e07  jmp     short loc_180116E19
0x180116e09  mov     ebx, 80004005h
0x180116e0e  mov     [rsp+68h+var_38], ebx
0x180116e12  jmp     short loc_180116E19
0x180116e14  mov     ebx, 80070057h
0x180116e19  mov     rcx, [rsp+68h+phHash]; hHash
0x180116e21  test    rcx, rcx
0x180116e24  jz      short loc_180116E38
0x180116e26  call    cs:__imp_CryptDestroyHash
0x180116e2c  mov     [rsp+68h+phHash], 0
0x180116e38  mov     rcx, [rsp+68h+phProv]; hProv
0x180116e3d  test    rcx, rcx
0x180116e40  jz      short loc_180116E4A
0x180116e42  xor     edx, edx; dwFlags
0x180116e44  call    cs:__imp_CryptReleaseContext
0x180116e4a  mov     eax, ebx
0x180116e4c  add     rsp, 40h
0x180116e50  pop     r15
0x180116e52  pop     r14
0x180116e54  pop     r12
0x180116e56  pop     rsi
0x180116e57  pop     rbx
0x180116e58  retn
0x18012e459  push    rbp
0x18012e45b  sub     rsp, 30h
0x18012e45f  mov     rbp, rdx
0x18012e462  call    ?PageErrorExceptionHandler@@YAKPEAU_EXCEPTION_POINTERS@@PEBDK@Z; PageErrorExceptionHandler(_EXCEPTION_POINTERS *,char const *,ulong)
0x18012e467  nop
0x18012e468  add     rsp, 30h
0x18012e46c  pop     rbp
0x18012e46d  retn
```
