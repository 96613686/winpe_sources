# UtilComputeSHA1Hash(uchar *,ulong,wchar_t * const)

- ea: `0x180096ec8`
- end: `0x18009725f`
- name: `?UtilComputeSHA1Hash@@YAJPEAEKQEA_W@Z`
- size: `919`
- prototype: `__int64 __fastcall(BYTE *pbData, DWORD dwDataLen, wchar_t *const)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180071eb4`

## callees

- `0x180004bb4`
- `0x18001fe24`
- `0x180020430`
- `0x18003ec1c`
- `0x180050db0`
- `0x180096ec8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096f3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096fb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097005`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097068`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009710e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096f3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096fb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097005`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097068`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009710e`
- `CRYPTSP!CryptHashData` at `0x180096ffb`
- `CRYPTSP!CryptHashData` at `0x180096ffb`
- `CRYPTSP!CryptGetHashParam` at `0x18009705e`
- `CRYPTSP!CryptGetHashParam` at `0x180097104`
- `CRYPTSP!CryptGetHashParam` at `0x18009705e`
- `CRYPTSP!CryptGetHashParam` at `0x180097104`
- `CRYPTSP!CryptReleaseContext` at `0x180097205`
- `CRYPTSP!CryptReleaseContext` at `0x180097205`
- `CRYPTSP!CryptDestroyHash` at `0x1800971ec`
- `CRYPTSP!CryptDestroyHash` at `0x1800971ec`
- `CRYPTSP!CryptAcquireContextW` at `0x180096f32`
- `CRYPTSP!CryptAcquireContextW` at `0x180096f32`
- `CRYPTSP!CryptCreateHash` at `0x180096fa7`
- `CRYPTSP!CryptCreateHash` at `0x180096fa7`

## pseudocode

```c
__int64 __fastcall UtilComputeSHA1Hash(BYTE *pbData, DWORD dwDataLen, wchar_t *const a3)
{
  signed int v6; // eax
  signed int v7; // ebx
  wchar_t *v8; // rcx
  __int64 v9; // rdx
  signed int v10; // eax
  signed int v11; // eax
  signed int v12; // eax
  signed int LastError; // eax
  __int64 i; // rsi
  DWORD pdwDataLen; // [rsp+30h] [rbp-40h] BYREF
  HCRYPTHASH phHash; // [rsp+38h] [rbp-38h] BYREF
  HCRYPTPROV phProv; // [rsp+40h] [rbp-30h] BYREF
  wchar_t v19; // [rsp+48h] [rbp-28h] BYREF
  BYTE pbDataa[24]; // [rsp+50h] [rbp-20h] BYREF

  phProv = 0;
  phHash = 0;
  pdwDataLen = 0;
  if ( pbData && a3 )
  {
    if ( CryptAcquireContextW(&phProv, 0, L"Microsoft Base Cryptographic Provider v1.0", 1u, 0xF0000000) )
    {
      if ( CryptCreateHash(phProv, 0x8004u, 0, 0, &phHash) )
      {
        if ( CryptHashData(phHash, pbData, dwDataLen, 0) )
        {
          if ( CryptGetHashParam(phHash, 2u, 0, &pdwDataLen, 0) )
          {
            if ( pdwDataLen > 0x14 )
            {
              v7 = -2147418113;
              if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, WPP_988ce82756cb3ec502560a762615dae0_Traceguids);
              goto LABEL_50;
            }
            if ( CryptGetHashParam(phHash, 2u, pbDataa, &pdwDataLen, 0) )
            {
              *a3 = 0;
              for ( i = 0; ; i = (unsigned int)(i + 1) )
              {
                if ( (unsigned int)i >= pdwDataLen )
                {
                  v7 = 0;
                  goto LABEL_50;
                }
                v7 = StringCchPrintfW(&v19, 3u, L"%x", pbDataa[i]);
                if ( v7 < 0 )
                  break;
                v7 = StringCchCatW(a3, 0x29u, &v19);
                if ( v7 < 0 )
                {
                  v8 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
                  {
                    v9 = 80;
                    goto LABEL_9;
                  }
                  goto LABEL_50;
                }
              }
              v8 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              {
                v9 = 79;
                goto LABEL_9;
              }
              goto LABEL_50;
            }
            LastError = GetLastError();
            v7 = LastError;
            if ( LastError > 0 )
              v7 = (unsigned __int16)LastError | 0x80070000;
            v8 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
            {
LABEL_50:
              if ( phHash )
              {
                CryptDestroyHash(phHash);
                phHash = 0;
              }
              if ( phProv )
                CryptReleaseContext(phProv, 0);
              return (unsigned int)v7;
            }
            v9 = 78;
          }
          else
          {
            v12 = GetLastError();
            v7 = v12;
            if ( v12 > 0 )
              v7 = (unsigned __int16)v12 | 0x80070000;
            v8 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
              goto LABEL_50;
            v9 = 76;
          }
        }
        else
        {
          v11 = GetLastError();
          v7 = v11;
          if ( v11 > 0 )
            v7 = (unsigned __int16)v11 | 0x80070000;
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
            goto LABEL_50;
          v9 = 75;
        }
      }
      else
      {
        v10 = GetLastError();
        v7 = v10;
        if ( v10 > 0 )
          v7 = (unsigned __int16)v10 | 0x80070000;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_50;
        v9 = 74;
      }
    }
    else
    {
      v6 = GetLastError();
      v7 = v6;
      if ( v6 > 0 )
        v7 = (unsigned __int16)v6 | 0x80070000;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_50;
      v9 = 73;
    }
LABEL_9:
    WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_988ce82756cb3ec502560a762615dae0_Traceguids, (unsigned int)v7);
    goto LABEL_50;
  }
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, WPP_988ce82756cb3ec502560a762615dae0_Traceguids);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180096ec8  mov     [rsp-18h+arg_18], rbx
0x180096ecd  push    rbp
0x180096ece  push    rsi
0x180096ecf  push    r14
0x180096ed1  mov     rbp, rsp
0x180096ed4  sub     rsp, 70h
0x180096ed8  mov     rax, cs:__security_cookie
0x180096edf  xor     rax, rsp
0x180096ee2  mov     [rbp+var_8], rax
0x180096ee6  mov     [rbp+phProv], 0
0x180096eee  mov     r14, r8
0x180096ef1  mov     [rbp+phHash], 0
0x180096ef9  mov     esi, edx
0x180096efb  mov     [rbp+pdwDataLen], 0
0x180096f02  mov     rbx, rcx
0x180096f05  test    rcx, rcx
0x180096f08  jz      loc_18009720F
0x180096f0e  test    r8, r8
0x180096f11  jz      loc_18009720F
0x180096f17  mov     r9d, 1; dwProvType
0x180096f1d  mov     [rsp+70h+dwFlags], 0F0000000h; dwFlags
0x180096f25  lea     r8, szProvider; "Microsoft Base Cryptographic Provider v"...
0x180096f2c  xor     edx, edx; szContainer
0x180096f2e  lea     rcx, [rbp+phProv]; phProv
0x180096f32  call    cs:__imp_CryptAcquireContextW
0x180096f38  test    eax, eax
0x180096f3a  jnz     short loc_180096F8F
0x180096f3c  call    cs:__imp_GetLastError
0x180096f42  mov     ebx, eax
0x180096f44  test    eax, eax
0x180096f46  jle     short loc_180096F51
0x180096f48  movzx   ebx, ax
0x180096f4b  or      ebx, 80070000h
0x180096f51  mov     rcx, cs:WPP_GLOBAL_Control
0x180096f58  lea     rax, WPP_GLOBAL_Control
0x180096f5f  cmp     rcx, rax
0x180096f62  jz      loc_1800971E3
0x180096f68  test    byte ptr [rcx+1Ch], 1
0x180096f6c  jz      loc_1800971E3
0x180096f72  mov     edx, 49h ; 'I'
0x180096f77  mov     rcx, [rcx+10h]
0x180096f7b  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x180096f82  mov     r9d, ebx
0x180096f85  call    WPP_SF_d
0x180096f8a  jmp     loc_1800971E3
0x180096f8f  mov     rcx, [rbp+phProv]; hProv
0x180096f93  lea     rax, [rbp+phHash]
0x180096f97  xor     r9d, r9d; dwFlags
0x180096f9a  mov     qword ptr [rsp+70h+dwFlags], rax; phHash
0x180096f9f  xor     r8d, r8d; hKey
0x180096fa2  mov     edx, 8004h; Algid
0x180096fa7  call    cs:__imp_CryptCreateHash
0x180096fad  test    eax, eax
0x180096faf  jnz     short loc_180096FEE
0x180096fb1  call    cs:__imp_GetLastError
0x180096fb7  mov     ebx, eax
0x180096fb9  test    eax, eax
0x180096fbb  jle     short loc_180096FC6
0x180096fbd  movzx   ebx, ax
0x180096fc0  or      ebx, 80070000h
0x180096fc6  mov     rcx, cs:WPP_GLOBAL_Control
0x180096fcd  lea     rax, WPP_GLOBAL_Control
0x180096fd4  cmp     rcx, rax
0x180096fd7  jz      loc_1800971E3
0x180096fdd  test    byte ptr [rcx+1Ch], 1
0x180096fe1  jz      loc_1800971E3
0x180096fe7  mov     edx, 4Ah ; 'J'
0x180096fec  jmp     short loc_180096F77
0x180096fee  mov     rcx, [rbp+phHash]; hHash
0x180096ff2  xor     r9d, r9d; dwFlags
0x180096ff5  mov     r8d, esi; dwDataLen
0x180096ff8  mov     rdx, rbx; pbData
0x180096ffb  call    cs:__imp_CryptHashData
0x180097001  test    eax, eax
0x180097003  jnz     short loc_180097045
0x180097005  call    cs:__imp_GetLastError
0x18009700b  mov     ebx, eax
0x18009700d  test    eax, eax
0x18009700f  jle     short loc_18009701A
0x180097011  movzx   ebx, ax
0x180097014  or      ebx, 80070000h
0x18009701a  mov     rcx, cs:WPP_GLOBAL_Control
0x180097021  lea     rax, WPP_GLOBAL_Control
0x180097028  cmp     rcx, rax
0x18009702b  jz      loc_1800971E3
0x180097031  test    byte ptr [rcx+1Ch], 1
0x180097035  jz      loc_1800971E3
0x18009703b  mov     edx, 4Bh ; 'K'
0x180097040  jmp     loc_180096F77
0x180097045  mov     rcx, [rbp+phHash]; hHash
0x180097049  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x18009704d  xor     r8d, r8d; pbData
0x180097050  mov     [rsp+70h+dwFlags], 0; dwFlags
0x180097058  lea     ebx, [r8+2]
0x18009705c  mov     edx, ebx; dwParam
0x18009705e  call    cs:__imp_CryptGetHashParam
0x180097064  test    eax, eax
0x180097066  jnz     short loc_1800970A8
0x180097068  call    cs:__imp_GetLastError
0x18009706e  mov     ebx, eax
0x180097070  test    eax, eax
0x180097072  jle     short loc_18009707D
0x180097074  movzx   ebx, ax
0x180097077  or      ebx, 80070000h
0x18009707d  mov     rcx, cs:WPP_GLOBAL_Control
0x180097084  lea     rax, WPP_GLOBAL_Control
0x18009708b  cmp     rcx, rax
0x18009708e  jz      loc_1800971E3
0x180097094  test    byte ptr [rcx+1Ch], 1
0x180097098  jz      loc_1800971E3
0x18009709e  mov     edx, 4Ch ; 'L'
0x1800970a3  jmp     loc_180096F77
0x1800970a8  cmp     [rbp+pdwDataLen], 14h
0x1800970ac  jbe     short loc_1800970EE
0x1800970ae  mov     ebx, 8000FFFFh
0x1800970b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800970ba  lea     rax, WPP_GLOBAL_Control
0x1800970c1  cmp     rcx, rax
0x1800970c4  jz      loc_1800971E3
0x1800970ca  test    byte ptr [rcx+1Ch], 1
0x1800970ce  jz      loc_1800971E3
0x1800970d4  mov     rcx, [rcx+10h]
0x1800970d8  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x1800970df  mov     edx, 4Dh ; 'M'
0x1800970e4  call    WPP_SF_
0x1800970e9  jmp     loc_1800971E3
0x1800970ee  mov     rcx, [rbp+phHash]; hHash
0x1800970f2  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x1800970f6  lea     r8, [rbp+pbData]; pbData
0x1800970fa  mov     [rsp+70h+dwFlags], 0; dwFlags
0x180097102  mov     edx, ebx; dwParam
0x180097104  call    cs:__imp_CryptGetHashParam
0x18009710a  test    eax, eax
0x18009710c  jnz     short loc_18009714E
0x18009710e  call    cs:__imp_GetLastError
0x180097114  mov     ebx, eax
0x180097116  test    eax, eax
0x180097118  jle     short loc_180097123
0x18009711a  movzx   ebx, ax
0x18009711d  or      ebx, 80070000h
0x180097123  mov     rcx, cs:WPP_GLOBAL_Control
0x18009712a  lea     rax, WPP_GLOBAL_Control
0x180097131  cmp     rcx, rax
0x180097134  jz      loc_1800971E3
0x18009713a  test    byte ptr [rcx+1Ch], 1
0x18009713e  jz      loc_1800971E3
0x180097144  mov     edx, 4Eh ; 'N'
0x180097149  jmp     loc_180096F77
0x18009714e  xor     eax, eax
0x180097150  mov     [r14], ax
0x180097154  xor     esi, esi
0x180097156  cmp     esi, [rbp+pdwDataLen]
0x180097159  jnb     loc_1800971E1
0x18009715f  movzx   r9d, [rbp+rsi+pbData]
0x180097165  lea     r8, asc_1800B39F0; "%x"
0x18009716c  mov     edx, 3; unsigned __int64
0x180097171  lea     rcx, [rbp+var_28]; wchar_t *
0x180097175  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18009717a  mov     ebx, eax
0x18009717c  test    eax, eax
0x18009717e  js      short loc_1800971BE
0x180097180  lea     r8, [rbp+var_28]; wchar_t *
0x180097184  mov     edx, 29h ; ')'; unsigned __int64
0x180097189  mov     rcx, r14; wchar_t *
0x18009718c  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180097191  mov     ebx, eax
0x180097193  test    eax, eax
0x180097195  js      short loc_18009719B
0x180097197  inc     esi
0x180097199  jmp     short loc_180097156
0x18009719b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800971a2  lea     rax, WPP_GLOBAL_Control
0x1800971a9  cmp     rcx, rax
0x1800971ac  jz      short loc_1800971E3
0x1800971ae  test    byte ptr [rcx+1Ch], 1
0x1800971b2  jz      short loc_1800971E3
0x1800971b4  mov     edx, 50h ; 'P'
0x1800971b9  jmp     loc_180096F77
0x1800971be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800971c5  lea     rax, WPP_GLOBAL_Control
0x1800971cc  cmp     rcx, rax
0x1800971cf  jz      short loc_1800971E3
0x1800971d1  test    byte ptr [rcx+1Ch], 1
0x1800971d5  jz      short loc_1800971E3
0x1800971d7  mov     edx, 4Fh ; 'O'
0x1800971dc  jmp     loc_180096F77
0x1800971e1  xor     ebx, ebx
0x1800971e3  mov     rcx, [rbp+phHash]; hHash
0x1800971e7  test    rcx, rcx
0x1800971ea  jz      short loc_1800971FA
0x1800971ec  call    cs:__imp_CryptDestroyHash
0x1800971f2  mov     [rbp+phHash], 0
0x1800971fa  mov     rcx, [rbp+phProv]; hProv
0x1800971fe  test    rcx, rcx
0x180097201  jz      short loc_18009720B
0x180097203  xor     edx, edx; dwFlags
0x180097205  call    cs:__imp_CryptReleaseContext
0x18009720b  mov     eax, ebx
0x18009720d  jmp     short loc_180097242
0x18009720f  mov     rcx, cs:WPP_GLOBAL_Control
0x180097216  lea     rax, WPP_GLOBAL_Control
0x18009721d  cmp     rcx, rax
0x180097220  jz      short loc_18009723D
0x180097222  test    byte ptr [rcx+1Ch], 1
0x180097226  jz      short loc_18009723D
0x180097228  mov     rcx, [rcx+10h]
0x18009722c  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x180097233  mov     edx, 48h ; 'H'
0x180097238  call    WPP_SF_
0x18009723d  mov     eax, 80070057h
0x180097242  mov     rcx, [rbp+var_8]
0x180097246  xor     rcx, rsp; StackCookie
0x180097249  call    __security_check_cookie
0x18009724e  mov     rbx, [rsp+70h+arg_18]
0x180097256  add     rsp, 70h
0x18009725a  pop     r14
0x18009725c  pop     rsi
0x18009725d  pop     rbp
0x18009725e  retn
```
