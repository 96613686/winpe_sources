# ComputeSha1Hash

- ea: `0x180038388`
- end: `0x180038664`
- name: `ComputeSha1Hash`
- size: `732`
- prototype: `__int64 __fastcall(BYTE *pbData, DWORD dwDataLen, BYTE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800d0fb0`

## callees

- `0x18003807c`
- `0x1800380a4`
- `0x180038388`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800383ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038462`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800384b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038519`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800385be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800383ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038462`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800384b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038519`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800385be`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x180038636`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x180038636`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x180038458`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x180038458`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x1800383e3`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x1800383e3`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x1800384ac`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x1800384ac`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18003864f`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18003864f`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18003850f`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x1800385b4`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18003850f`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x1800385b4`

## pseudocode

```c
__int64 __fastcall ComputeSha1Hash(BYTE *pbData, DWORD dwDataLen, BYTE *a3)
{
  signed int v6; // eax
  unsigned int v7; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  signed int v10; // eax
  signed int v11; // eax
  signed int v12; // eax
  signed int LastError; // eax
  HCRYPTPROV phProv[2]; // [rsp+30h] [rbp-10h] BYREF
  DWORD pdwDataLen; // [rsp+60h] [rbp+20h] BYREF
  HCRYPTHASH phHash; // [rsp+78h] [rbp+38h] BYREF

  phProv[0] = 0;
  phHash = 0;
  pdwDataLen = 0;
  if ( pbData && a3 )
  {
    if ( CryptAcquireContextW(phProv, 0, L"Microsoft Base Cryptographic Provider v1.0", 1u, 0xF0000000) )
    {
      if ( CryptCreateHash(phProv[0], 0x8004u, 0, 0, &phHash) )
      {
        if ( CryptHashData(phHash, pbData, dwDataLen, 0) )
        {
          if ( CryptGetHashParam(phHash, 2u, 0, &pdwDataLen, 0) )
          {
            if ( pdwDataLen <= 0x14 )
            {
              if ( CryptGetHashParam(phHash, 2u, a3, &pdwDataLen, 0) )
              {
                v7 = 0;
              }
              else
              {
                LastError = GetLastError();
                v7 = LastError;
                if ( LastError > 0 )
                  v7 = (unsigned __int16)LastError | 0x80070000;
                v8 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  v9 = 16;
                  goto LABEL_9;
                }
              }
            }
            else
            {
              v7 = -2147418113;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_18864a23d0283f6b832131a6e90b37b9_Traceguids);
              }
            }
          }
          else
          {
            v12 = GetLastError();
            v7 = v12;
            if ( v12 > 0 )
              v7 = (unsigned __int16)v12 | 0x80070000;
            v8 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v9 = 14;
              goto LABEL_9;
            }
          }
        }
        else
        {
          v11 = GetLastError();
          v7 = v11;
          if ( v11 > 0 )
            v7 = (unsigned __int16)v11 | 0x80070000;
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v9 = 13;
            goto LABEL_9;
          }
        }
      }
      else
      {
        v10 = GetLastError();
        v7 = v10;
        if ( v10 > 0 )
          v7 = (unsigned __int16)v10 | 0x80070000;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v9 = 12;
          goto LABEL_9;
        }
      }
    }
    else
    {
      v6 = GetLastError();
      v7 = v6;
      if ( v6 > 0 )
        v7 = (unsigned __int16)v6 | 0x80070000;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v9 = 11;
LABEL_9:
        WPP_SF_D(v8[2], v9, WPP_18864a23d0283f6b832131a6e90b37b9_Traceguids, v7);
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_18864a23d0283f6b832131a6e90b37b9_Traceguids);
    v7 = -2147024809;
  }
  if ( phHash )
  {
    CryptDestroyHash(phHash);
    phHash = 0;
  }
  if ( phProv[0] )
    CryptReleaseContext(phProv[0], 0);
  return v7;
}

```

## disassembly

```asm
0x180038388  mov     [rsp-18h+arg_8], rbx
0x18003838d  push    rbp
0x18003838e  push    rsi
0x18003838f  push    rdi
0x180038390  mov     rbp, rsp
0x180038393  sub     rsp, 40h
0x180038397  mov     [rbp+phProv], 0
0x18003839f  mov     rbx, r8
0x1800383a2  mov     [rbp+phHash], 0
0x1800383aa  mov     esi, edx
0x1800383ac  mov     [rbp+pdwDataLen], 0
0x1800383b3  mov     rdi, rcx
0x1800383b6  test    rcx, rcx
0x1800383b9  jz      loc_1800385FA
0x1800383bf  test    rbx, rbx
0x1800383c2  jz      loc_1800385FA
0x1800383c8  mov     r9d, 1; dwProvType
0x1800383ce  mov     [rsp+40h+dwFlags], 0F0000000h; dwFlags
0x1800383d6  lea     r8, szProvider; "Microsoft Base Cryptographic Provider v"...
0x1800383dd  xor     edx, edx; szContainer
0x1800383df  lea     rcx, [rbp+phProv]; phProv
0x1800383e3  call    cs:__imp_CryptAcquireContextW
0x1800383e9  test    eax, eax
0x1800383eb  jnz     short loc_180038440
0x1800383ed  call    cs:__imp_GetLastError
0x1800383f3  mov     ebx, eax
0x1800383f5  test    eax, eax
0x1800383f7  jle     short loc_180038402
0x1800383f9  movzx   ebx, ax
0x1800383fc  or      ebx, 80070000h
0x180038402  mov     rcx, cs:WPP_GLOBAL_Control
0x180038409  lea     rax, WPP_GLOBAL_Control
0x180038410  cmp     rcx, rax
0x180038413  jz      loc_18003862D
0x180038419  test    byte ptr [rcx+1Ch], 1
0x18003841d  jz      loc_18003862D
0x180038423  mov     edx, 0Bh
0x180038428  mov     rcx, [rcx+10h]
0x18003842c  lea     r8, WPP_18864a23d0283f6b832131a6e90b37b9_Traceguids
0x180038433  mov     r9d, ebx
0x180038436  call    WPP_SF_D
0x18003843b  jmp     loc_18003862D
0x180038440  mov     rcx, [rbp+phProv]; hProv
0x180038444  lea     rax, [rbp+phHash]
0x180038448  xor     r9d, r9d; dwFlags
0x18003844b  mov     qword ptr [rsp+40h+dwFlags], rax; phHash
0x180038450  xor     r8d, r8d; hKey
0x180038453  mov     edx, 8004h; Algid
0x180038458  call    cs:__imp_CryptCreateHash
0x18003845e  test    eax, eax
0x180038460  jnz     short loc_18003849F
0x180038462  call    cs:__imp_GetLastError
0x180038468  mov     ebx, eax
0x18003846a  test    eax, eax
0x18003846c  jle     short loc_180038477
0x18003846e  movzx   ebx, ax
0x180038471  or      ebx, 80070000h
0x180038477  mov     rcx, cs:WPP_GLOBAL_Control
0x18003847e  lea     rax, WPP_GLOBAL_Control
0x180038485  cmp     rcx, rax
0x180038488  jz      loc_18003862D
0x18003848e  test    byte ptr [rcx+1Ch], 1
0x180038492  jz      loc_18003862D
0x180038498  mov     edx, 0Ch
0x18003849d  jmp     short loc_180038428
0x18003849f  mov     rcx, [rbp+phHash]; hHash
0x1800384a3  xor     r9d, r9d; dwFlags
0x1800384a6  mov     r8d, esi; dwDataLen
0x1800384a9  mov     rdx, rdi; pbData
0x1800384ac  call    cs:__imp_CryptHashData
0x1800384b2  test    eax, eax
0x1800384b4  jnz     short loc_1800384F6
0x1800384b6  call    cs:__imp_GetLastError
0x1800384bc  mov     ebx, eax
0x1800384be  test    eax, eax
0x1800384c0  jle     short loc_1800384CB
0x1800384c2  movzx   ebx, ax
0x1800384c5  or      ebx, 80070000h
0x1800384cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800384d2  lea     rax, WPP_GLOBAL_Control
0x1800384d9  cmp     rcx, rax
0x1800384dc  jz      loc_18003862D
0x1800384e2  test    byte ptr [rcx+1Ch], 1
0x1800384e6  jz      loc_18003862D
0x1800384ec  mov     edx, 0Dh
0x1800384f1  jmp     loc_180038428
0x1800384f6  mov     rcx, [rbp+phHash]; hHash
0x1800384fa  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x1800384fe  xor     r8d, r8d; pbData
0x180038501  mov     [rsp+40h+dwFlags], 0; dwFlags
0x180038509  lea     edi, [r8+2]
0x18003850d  mov     edx, edi; dwParam
0x18003850f  call    cs:__imp_CryptGetHashParam
0x180038515  test    eax, eax
0x180038517  jnz     short loc_180038559
0x180038519  call    cs:__imp_GetLastError
0x18003851f  mov     ebx, eax
0x180038521  test    eax, eax
0x180038523  jle     short loc_18003852E
0x180038525  movzx   ebx, ax
0x180038528  or      ebx, 80070000h
0x18003852e  mov     rcx, cs:WPP_GLOBAL_Control
0x180038535  lea     rax, WPP_GLOBAL_Control
0x18003853c  cmp     rcx, rax
0x18003853f  jz      loc_18003862D
0x180038545  test    byte ptr [rcx+1Ch], 1
0x180038549  jz      loc_18003862D
0x18003854f  mov     edx, 0Eh
0x180038554  jmp     loc_180038428
0x180038559  cmp     [rbp+pdwDataLen], 14h
0x18003855d  jbe     short loc_18003859F
0x18003855f  mov     ebx, 8000FFFFh
0x180038564  mov     rcx, cs:WPP_GLOBAL_Control
0x18003856b  lea     rax, WPP_GLOBAL_Control
0x180038572  cmp     rcx, rax
0x180038575  jz      loc_18003862D
0x18003857b  test    byte ptr [rcx+1Ch], 1
0x18003857f  jz      loc_18003862D
0x180038585  mov     rcx, [rcx+10h]
0x180038589  lea     r8, WPP_18864a23d0283f6b832131a6e90b37b9_Traceguids
0x180038590  mov     edx, 0Fh
0x180038595  call    WPP_SF_
0x18003859a  jmp     loc_18003862D
0x18003859f  mov     rcx, [rbp+phHash]; hHash
0x1800385a3  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x1800385a7  mov     r8, rbx; pbData
0x1800385aa  mov     [rsp+40h+dwFlags], 0; dwFlags
0x1800385b2  mov     edx, edi; dwParam
0x1800385b4  call    cs:__imp_CryptGetHashParam
0x1800385ba  test    eax, eax
0x1800385bc  jnz     short loc_1800385F6
0x1800385be  call    cs:__imp_GetLastError
0x1800385c4  mov     ebx, eax
0x1800385c6  test    eax, eax
0x1800385c8  jle     short loc_1800385D3
0x1800385ca  movzx   ebx, ax
0x1800385cd  or      ebx, 80070000h
0x1800385d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800385da  lea     rax, WPP_GLOBAL_Control
0x1800385e1  cmp     rcx, rax
0x1800385e4  jz      short loc_18003862D
0x1800385e6  test    byte ptr [rcx+1Ch], 1
0x1800385ea  jz      short loc_18003862D
0x1800385ec  mov     edx, 10h
0x1800385f1  jmp     loc_180038428
0x1800385f6  xor     ebx, ebx
0x1800385f8  jmp     short loc_18003862D
0x1800385fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180038601  lea     rax, WPP_GLOBAL_Control
0x180038608  cmp     rcx, rax
0x18003860b  jz      short loc_180038628
0x18003860d  test    byte ptr [rcx+1Ch], 1
0x180038611  jz      short loc_180038628
0x180038613  mov     rcx, [rcx+10h]
0x180038617  lea     r8, WPP_18864a23d0283f6b832131a6e90b37b9_Traceguids
0x18003861e  mov     edx, 0Ah
0x180038623  call    WPP_SF_
0x180038628  mov     ebx, 80070057h
0x18003862d  mov     rcx, [rbp+phHash]; hHash
0x180038631  test    rcx, rcx
0x180038634  jz      short loc_180038644
0x180038636  call    cs:__imp_CryptDestroyHash
0x18003863c  mov     [rbp+phHash], 0
0x180038644  mov     rcx, [rbp+phProv]; hProv
0x180038648  test    rcx, rcx
0x18003864b  jz      short loc_180038655
0x18003864d  xor     edx, edx; dwFlags
0x18003864f  call    cs:__imp_CryptReleaseContext
0x180038655  mov     eax, ebx
0x180038657  mov     rbx, [rsp+40h+arg_8]
0x18003865c  add     rsp, 40h
0x180038660  pop     rdi
0x180038661  pop     rsi
0x180038662  pop     rbp
0x180038663  retn
```
