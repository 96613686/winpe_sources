# CreateHashFromMTCookie_LocalImpl(uchar *,uint,SecurityCookieHash *)

- ea: `0x18015262c`
- end: `0x180152b4c`
- name: `?CreateHashFromMTCookie_LocalImpl@@YAJPEAEIPEAUSecurityCookieHash@@@Z`
- size: `1312`
- prototype: `__int64 __fastcall(BYTE *pbData, unsigned int, struct SecurityCookieHash *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180151840`

## callees

- `0x18000116c`
- `0x180001308`
- `0x180002170`
- `0x1800023e4`
- `0x18015262c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180152727`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801527cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180152869`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015291e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180152a46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180152727`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801527cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180152869`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015291e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180152a46`
- `CRYPTSP!CryptGetHashParam` at `0x180152910`
- `CRYPTSP!CryptGetHashParam` at `0x180152a38`
- `CRYPTSP!CryptGetHashParam` at `0x180152910`
- `CRYPTSP!CryptGetHashParam` at `0x180152a38`
- `CRYPTSP!CryptDestroyHash` at `0x180152ae2`
- `CRYPTSP!CryptDestroyHash` at `0x180152ae2`
- `CRYPTSP!CryptCreateHash` at `0x1801527bf`
- `CRYPTSP!CryptCreateHash` at `0x1801527bf`
- `CRYPTSP!CryptAcquireContextW` at `0x180152719`
- `CRYPTSP!CryptAcquireContextW` at `0x180152719`
- `CRYPTSP!CryptHashData` at `0x18015285b`
- `CRYPTSP!CryptHashData` at `0x18015285b`
- `CRYPTSP!CryptReleaseContext` at `0x180152af3`
- `CRYPTSP!CryptReleaseContext` at `0x180152af3`

## string_xrefs

- `0x1801526b2`: `onecore\termsrv\rdpplatform\rdpenc\transports\sidetransportstream\sidetransportstream.cpp`
- `0x180152764`: `onecore\termsrv\rdpplatform\rdpenc\transports\sidetransportstream\sidetransportstream.cpp`
- `0x18015280a`: `onecore\termsrv\rdpplatform\rdpenc\transports\sidetransportstream\sidetransportstream.cpp`
- `0x1801528a6`: `onecore\termsrv\rdpplatform\rdpenc\transports\sidetransportstream\sidetransportstream.cpp`
- `0x18015295b`: `onecore\termsrv\rdpplatform\rdpenc\transports\sidetransportstream\sidetransportstream.cpp`
- `0x1801529d0`: `onecore\termsrv\rdpplatform\rdpenc\transports\sidetransportstream\sidetransportstream.cpp`
- `0x180152a7e`: `onecore\termsrv\rdpplatform\rdpenc\transports\sidetransportstream\sidetransportstream.cpp`
- `0x180152660`: `Entering CreateHashFromMTCookie`
- `0x1801526bd`: `CreateHashFromMTCookie error invalid parameter`
- `0x180152699`: `CreateHashFromMTCookie_LocalImpl`
- `0x18015274b`: `CreateHashFromMTCookie_LocalImpl`
- `0x1801527f1`: `CreateHashFromMTCookie_LocalImpl`
- `0x18015288d`: `CreateHashFromMTCookie_LocalImpl`
- `0x180152942`: `CreateHashFromMTCookie_LocalImpl`
- `0x1801529c5`: `CreateHashFromMTCookie_LocalImpl`
- `0x180152a73`: `CreateHashFromMTCookie_LocalImpl`
- `0x180152815`: `Cryptographic error calling CryptCreateHash`
- `0x180152b07`: `Exiting CreateHashFromMTCookie`

## pseudocode

```c
__int64 __fastcall CreateHashFromMTCookie_LocalImpl(BYTE *pbData, DWORD a2, BYTE *a3, int a4)
{
  unsigned int v6; // ebx
  char *v7; // rdx
  const char **v8; // rax
  signed int v9; // eax
  signed int v10; // eax
  signed int v11; // eax
  int v12; // ecx
  signed int v13; // eax
  __int64 *v14; // rdx
  const char **v15; // rax
  signed int LastError; // eax
  int v17; // ecx
  const char **v19; // [rsp+30h] [rbp-19h]
  const char **v20; // [rsp+40h] [rbp-9h]
  const char **v21; // [rsp+40h] [rbp-9h]
  DWORD pdwDataLen; // [rsp+50h] [rbp+7h] BYREF
  const char *v23; // [rsp+58h] [rbp+Fh] BYREF
  HCRYPTHASH phHash; // [rsp+60h] [rbp+17h] BYREF
  HCRYPTPROV phProv; // [rsp+68h] [rbp+1Fh] BYREF
  const char *v26; // [rsp+70h] [rbp+27h] BYREF
  const char *v27; // [rsp+78h] [rbp+2Fh] BYREF
  _QWORD v28[4]; // [rsp+80h] [rbp+37h] BYREF
  DWORD pbDataa; // [rsp+B8h] [rbp+6Fh] BYREF
  const char *v30; // [rsp+C0h] [rbp+77h] BYREF
  int v31; // [rsp+C8h] [rbp+7Fh] BYREF

  pbDataa = a2;
  phProv = 0;
  phHash = 0;
  if ( (unsigned int)CallbackContext > 4 )
  {
    v30 = "Entering CreateHashFromMTCookie";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (_DWORD)pbData,
      (unsigned int)byte_18029CCFD,
      (_DWORD)a3,
      a4,
      (__int64)&v30);
  }
  if ( !a3 )
  {
    v6 = -2147024809;
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_36;
    LODWORD(v30) = 1523;
    v23 = "CreateHashFromMTCookie_LocalImpl";
    v7 = byte_18029B929;
    v26 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\sidetransportstream\\sidetransportstream.cpp";
    v27 = "CreateHashFromMTCookie error invalid parameter";
    v20 = &v23;
    v8 = &v27;
    goto LABEL_6;
  }
  if ( CryptAcquireContextW(&phProv, 0, 0, 0x18u, 0xF0000000) )
  {
    if ( CryptCreateHash(phProv, 0x800Cu, 0, 0, &phHash) )
    {
      if ( CryptHashData(phHash, pbData, 0x10u, 0) )
      {
        pbDataa = 0;
        pdwDataLen = 4;
        if ( CryptGetHashParam(phHash, 4u, (BYTE *)&pbDataa, &pdwDataLen, 0) )
        {
          if ( pbDataa == 32 )
          {
            v6 = 0;
            if ( CryptGetHashParam(phHash, 2u, a3 + 20, &pbDataa, 0) )
              goto LABEL_36;
            LastError = GetLastError();
            v6 = LastError;
            if ( LastError > 0 )
              v6 = (unsigned __int16)LastError | 0x80070000;
            if ( (unsigned int)CallbackContext <= 2 )
              goto LABEL_36;
            v14 = (__int64 *)&byte_18029C75F;
            LODWORD(v30) = pbDataa;
            v28[0] = "CreateHashFromMTCookie_LocalImpl";
            v27 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\sidetransportstream\\sidetransportstream.cpp";
            v26 = "Cryptographic error calling CryptGetHashParam for hash data";
            v21 = (const char **)v28;
            v19 = &v27;
            v15 = &v26;
            v31 = 1615;
          }
          else
          {
            v6 = -2147467259;
            if ( (unsigned int)CallbackContext <= 2 )
              goto LABEL_36;
            v14 = qword_18029BE98;
            LODWORD(v30) = pbDataa;
            v27 = "CreateHashFromMTCookie_LocalImpl";
            v26 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\sidetransportstream\\sidetransportstream.cpp";
            v28[0] = "Cryptographic error calling CryptGetHashParam returning hash size other than 32 as expected for SHA-256";
            v21 = &v27;
            v19 = &v26;
            v15 = (const char **)v28;
            v31 = 1599;
          }
          LODWORD(v23) = v6;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v12,
            (_DWORD)v14,
            (_DWORD)a3,
            a4,
            (__int64)v15,
            (__int64)&v23,
            (__int64)v19,
            (__int64)&v31,
            (__int64)v21,
            (__int64)&v30);
          goto LABEL_36;
        }
        v13 = GetLastError();
        v6 = v13;
        if ( v13 > 0 )
          v6 = (unsigned __int16)v13 | 0x80070000;
        if ( (unsigned int)CallbackContext > 2 )
        {
          LODWORD(v30) = 1590;
          v27 = "CreateHashFromMTCookie_LocalImpl";
          v7 = &byte_18029C087;
          v26 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\sidetransportstream\\sidetransportstream.cpp";
          v23 = "Cryptographic error calling CryptGetHashParam for hash size";
          v20 = &v27;
          v8 = &v23;
          goto LABEL_6;
        }
      }
      else
      {
        v11 = GetLastError();
        v6 = v11;
        if ( v11 > 0 )
          v6 = (unsigned __int16)v11 | 0x80070000;
        if ( (unsigned int)CallbackContext > 2 )
        {
          LODWORD(v30) = 1572;
          v27 = "CreateHashFromMTCookie_LocalImpl";
          v7 = &byte_18029B2AF;
          v26 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\sidetransportstream\\sidetransportstream.cpp";
          v23 = "Cryptographic error calling CryptHashData";
          v20 = &v27;
          v8 = &v23;
          goto LABEL_6;
        }
      }
    }
    else
    {
      v10 = GetLastError();
      v6 = v10;
      if ( v10 > 0 )
        v6 = (unsigned __int16)v10 | 0x80070000;
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(v30) = 1557;
        v27 = "CreateHashFromMTCookie_LocalImpl";
        v7 = byte_18029CA2B;
        v26 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\sidetransportstream\\sidetransportstream.cpp";
        v23 = "Cryptographic error calling CryptCreateHash";
        v20 = &v27;
        v8 = &v23;
        goto LABEL_6;
      }
    }
  }
  else
  {
    v9 = GetLastError();
    v6 = v9;
    if ( v9 > 0 )
      v6 = (unsigned __int16)v9 | 0x80070000;
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v30) = 1541;
      v27 = "CreateHashFromMTCookie_LocalImpl";
      v7 = &byte_18029BC87;
      v26 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\sidetransportstream\\sidetransportstream.cpp";
      v23 = "Cryptographic error calling CryptAcquireContext";
      v20 = &v27;
      v8 = &v23;
LABEL_6:
      v31 = v6;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)pbData,
        (_DWORD)v7,
        (_DWORD)a3,
        a4,
        (__int64)v8,
        (__int64)&v31,
        (__int64)&v26,
        (__int64)&v30,
        (__int64)v20);
    }
  }
LABEL_36:
  if ( phHash )
    CryptDestroyHash(phHash);
  if ( phProv )
    CryptReleaseContext(phProv, 0);
  if ( (unsigned int)CallbackContext > 4 )
  {
    v17 = *((_DWORD *)a3 + 5);
    v28[0] = "Exiting CreateHashFromMTCookie";
    LODWORD(v30) = v17;
    v31 = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v17,
      (unsigned int)word_18029B6A2,
      (_DWORD)a3,
      a4,
      (__int64)v28,
      (__int64)&v31,
      (__int64)&v30);
  }
  return v6;
}

```

## disassembly

```asm
0x18015262c  mov     [rsp-8+pbData], edx
0x180152630  push    rbp
0x180152631  push    rbx
0x180152632  push    rdi
0x180152633  lea     rbp, [rsp-47h]
0x180152638  sub     rsp, 90h
0x18015263f  mov     eax, cs:CallbackContext
0x180152645  mov     rdi, r8
0x180152648  mov     [rbp+57h+phProv], 0
0x180152650  mov     rbx, rcx
0x180152653  mov     [rbp+57h+phHash], 0
0x18015265b  cmp     eax, 4
0x18015265e  jbe     short loc_180152680
0x180152660  lea     rax, aEnteringCreate; "Entering CreateHashFromMTCookie"
0x180152667  mov     [rbp+57h+arg_10], rax
0x18015266b  lea     rdx, byte_18029CCFD
0x180152672  lea     rax, [rbp+57h+arg_10]
0x180152676  mov     qword ptr [rsp+0A0h+dwFlags], rax
0x18015267b  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180152680  test    rdi, rdi
0x180152683  jnz     short loc_180152702
0x180152685  mov     eax, cs:CallbackContext
0x18015268b  mov     ebx, 80070057h
0x180152690  cmp     eax, 2
0x180152693  jbe     loc_180152AD9
0x180152699  lea     rax, aCreatehashfrom_0; "CreateHashFromMTCookie_LocalImpl"
0x1801526a0  mov     dword ptr [rbp+57h+arg_10], 5F3h
0x1801526a7  mov     [rbp+57h+var_48], rax
0x1801526ab  lea     rdx, byte_18029B929
0x1801526b2  lea     rax, aOnecoreTermsrv_41; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1801526b9  mov     [rbp+57h+var_30], rax
0x1801526bd  lea     rax, aCreatehashfrom; "CreateHashFromMTCookie error invalid pa"...
0x1801526c4  mov     [rbp+57h+var_28], rax
0x1801526c8  lea     rax, [rbp+57h+var_48]
0x1801526cc  mov     [rsp+0A0h+var_60], rax
0x1801526d1  lea     rax, [rbp+57h+arg_10]
0x1801526d5  mov     [rsp+0A0h+var_68], rax
0x1801526da  lea     rax, [rbp+57h+var_30]
0x1801526de  mov     [rsp+0A0h+var_70], rax
0x1801526e3  lea     rax, [rbp+57h+arg_18]
0x1801526e7  mov     [rsp+0A0h+var_78], rax
0x1801526ec  lea     rax, [rbp+57h+var_28]
0x1801526f0  mov     [rbp+57h+arg_18], ebx
0x1801526f3  mov     qword ptr [rsp+0A0h+dwFlags], rax
0x1801526f8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1801526fd  jmp     loc_180152AD9
0x180152702  mov     r9d, 18h; dwProvType
0x180152708  mov     [rsp+0A0h+dwFlags], 0F0000000h; dwFlags
0x180152710  xor     r8d, r8d; szProvider
0x180152713  lea     rcx, [rbp+57h+phProv]; phProv
0x180152717  xor     edx, edx; szContainer
0x180152719  call    cs:__imp_CryptAcquireContextW
0x18015271f  test    eax, eax
0x180152721  jnz     loc_1801527A7
0x180152727  call    cs:__imp_GetLastError
0x18015272d  mov     ebx, eax
0x18015272f  test    eax, eax
0x180152731  jle     short loc_18015273C
0x180152733  movzx   ebx, ax
0x180152736  or      ebx, 80070000h
0x18015273c  mov     eax, cs:CallbackContext
0x180152742  cmp     eax, 2
0x180152745  jbe     loc_180152AD9
0x18015274b  lea     rax, aCreatehashfrom_0; "CreateHashFromMTCookie_LocalImpl"
0x180152752  mov     dword ptr [rbp+57h+arg_10], 605h
0x180152759  mov     [rbp+57h+var_28], rax
0x18015275d  lea     rdx, byte_18029BC87
0x180152764  lea     rax, aOnecoreTermsrv_41; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18015276b  mov     [rbp+57h+var_30], rax
0x18015276f  lea     rax, aCryptographicE_0; "Cryptographic error calling CryptAcquir"...
0x180152776  mov     [rbp+57h+var_48], rax
0x18015277a  lea     rax, [rbp+57h+var_28]
0x18015277e  mov     [rsp+0A0h+var_60], rax
0x180152783  lea     rax, [rbp+57h+arg_10]
0x180152787  mov     [rsp+0A0h+var_68], rax
0x18015278c  lea     rax, [rbp+57h+var_30]
0x180152790  mov     [rsp+0A0h+var_70], rax
0x180152795  lea     rax, [rbp+57h+arg_18]
0x180152799  mov     [rsp+0A0h+var_78], rax
0x18015279e  lea     rax, [rbp+57h+var_48]
0x1801527a2  jmp     loc_1801526F0
0x1801527a7  mov     rcx, [rbp+57h+phProv]; hProv
0x1801527ab  lea     rax, [rbp+57h+phHash]
0x1801527af  xor     r9d, r9d; dwFlags
0x1801527b2  mov     qword ptr [rsp+0A0h+dwFlags], rax; phHash
0x1801527b7  xor     r8d, r8d; hKey
0x1801527ba  mov     edx, 800Ch; Algid
0x1801527bf  call    cs:__imp_CryptCreateHash
0x1801527c5  test    eax, eax
0x1801527c7  jnz     loc_18015284D
0x1801527cd  call    cs:__imp_GetLastError
0x1801527d3  mov     ebx, eax
0x1801527d5  test    eax, eax
0x1801527d7  jle     short loc_1801527E2
0x1801527d9  movzx   ebx, ax
0x1801527dc  or      ebx, 80070000h
0x1801527e2  mov     eax, cs:CallbackContext
0x1801527e8  cmp     eax, 2
0x1801527eb  jbe     loc_180152AD9
0x1801527f1  lea     rax, aCreatehashfrom_0; "CreateHashFromMTCookie_LocalImpl"
0x1801527f8  mov     dword ptr [rbp+57h+arg_10], 615h
0x1801527ff  mov     [rbp+57h+var_28], rax
0x180152803  lea     rdx, byte_18029CA2B
0x18015280a  lea     rax, aOnecoreTermsrv_41; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180152811  mov     [rbp+57h+var_30], rax
0x180152815  lea     rax, aCryptographicE_3; "Cryptographic error calling CryptCreate"...
0x18015281c  mov     [rbp+57h+var_48], rax
0x180152820  lea     rax, [rbp+57h+var_28]
0x180152824  mov     [rsp+0A0h+var_60], rax
0x180152829  lea     rax, [rbp+57h+arg_10]
0x18015282d  mov     [rsp+0A0h+var_68], rax
0x180152832  lea     rax, [rbp+57h+var_30]
0x180152836  mov     [rsp+0A0h+var_70], rax
0x18015283b  lea     rax, [rbp+57h+arg_18]
0x18015283f  mov     [rsp+0A0h+var_78], rax
0x180152844  lea     rax, [rbp+57h+var_48]
0x180152848  jmp     loc_1801526F0
0x18015284d  mov     rcx, [rbp+57h+phHash]; hHash
0x180152851  xor     r9d, r9d; dwFlags
0x180152854  mov     rdx, rbx; pbData
0x180152857  lea     r8d, [r9+10h]; dwDataLen
0x18015285b  call    cs:__imp_CryptHashData
0x180152861  test    eax, eax
0x180152863  jnz     loc_1801528E9
0x180152869  call    cs:__imp_GetLastError
0x18015286f  mov     ebx, eax
0x180152871  test    eax, eax
0x180152873  jle     short loc_18015287E
0x180152875  movzx   ebx, ax
0x180152878  or      ebx, 80070000h
0x18015287e  mov     eax, cs:CallbackContext
0x180152884  cmp     eax, 2
0x180152887  jbe     loc_180152AD9
0x18015288d  lea     rax, aCreatehashfrom_0; "CreateHashFromMTCookie_LocalImpl"
0x180152894  mov     dword ptr [rbp+57h+arg_10], 624h
0x18015289b  mov     [rbp+57h+var_28], rax
0x18015289f  lea     rdx, byte_18029B2AF
0x1801528a6  lea     rax, aOnecoreTermsrv_41; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1801528ad  mov     [rbp+57h+var_30], rax
0x1801528b1  lea     rax, aCryptographicE_1; "Cryptographic error calling CryptHashDa"...
0x1801528b8  mov     [rbp+57h+var_48], rax
0x1801528bc  lea     rax, [rbp+57h+var_28]
0x1801528c0  mov     [rsp+0A0h+var_60], rax
0x1801528c5  lea     rax, [rbp+57h+arg_10]
0x1801528c9  mov     [rsp+0A0h+var_68], rax
0x1801528ce  lea     rax, [rbp+57h+var_30]
0x1801528d2  mov     [rsp+0A0h+var_70], rax
0x1801528d7  lea     rax, [rbp+57h+arg_18]
0x1801528db  mov     [rsp+0A0h+var_78], rax
0x1801528e0  lea     rax, [rbp+57h+var_48]
0x1801528e4  jmp     loc_1801526F0
0x1801528e9  mov     rcx, [rbp+57h+phHash]; hHash
0x1801528ed  lea     r9, [rbp+57h+pdwDataLen]; pdwDataLen
0x1801528f1  lea     r8, [rbp+57h+pbData]; pbData
0x1801528f5  mov     [rbp+57h+pbData], 0
0x1801528fc  mov     edx, 4; dwParam
0x180152901  mov     [rbp+57h+pdwDataLen], 4
0x180152908  mov     [rsp+0A0h+dwFlags], 0; dwFlags
0x180152910  call    cs:__imp_CryptGetHashParam
0x180152916  test    eax, eax
0x180152918  jnz     loc_18015299E
0x18015291e  call    cs:__imp_GetLastError
0x180152924  mov     ebx, eax
0x180152926  test    eax, eax
0x180152928  jle     short loc_180152933
0x18015292a  movzx   ebx, ax
0x18015292d  or      ebx, 80070000h
0x180152933  mov     eax, cs:CallbackContext
0x180152939  cmp     eax, 2
0x18015293c  jbe     loc_180152AD9
0x180152942  lea     rax, aCreatehashfrom_0; "CreateHashFromMTCookie_LocalImpl"
0x180152949  mov     dword ptr [rbp+57h+arg_10], 636h
0x180152950  mov     [rbp+57h+var_28], rax
0x180152954  lea     rdx, byte_18029C087
0x18015295b  lea     rax, aOnecoreTermsrv_41; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180152962  mov     [rbp+57h+var_30], rax
0x180152966  lea     rax, aCryptographicE; "Cryptographic error calling CryptGetHas"...
0x18015296d  mov     [rbp+57h+var_48], rax
0x180152971  lea     rax, [rbp+57h+var_28]
0x180152975  mov     [rsp+0A0h+var_60], rax
0x18015297a  lea     rax, [rbp+57h+arg_10]
0x18015297e  mov     [rsp+0A0h+var_68], rax
0x180152983  lea     rax, [rbp+57h+var_30]
0x180152987  mov     [rsp+0A0h+var_70], rax
0x18015298c  lea     rax, [rbp+57h+arg_18]
0x180152990  mov     [rsp+0A0h+var_78], rax
0x180152995  lea     rax, [rbp+57h+var_48]
0x180152999  jmp     loc_1801526F0
0x18015299e  cmp     [rbp+57h+pbData], 20h ; ' '
0x1801529a2  jz      short loc_180152A23
0x1801529a4  mov     eax, cs:CallbackContext
0x1801529aa  mov     ebx, 80004005h
0x1801529af  cmp     eax, 2
0x1801529b2  jbe     loc_180152AD9
0x1801529b8  mov     eax, [rbp+57h+pbData]
0x1801529bb  lea     rdx, qword_18029BE98
0x1801529c2  mov     dword ptr [rbp+57h+arg_10], eax
0x1801529c5  lea     rax, aCreatehashfrom_0; "CreateHashFromMTCookie_LocalImpl"
0x1801529cc  mov     [rbp+57h+var_28], rax
0x1801529d0  lea     rax, aOnecoreTermsrv_41; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1801529d7  mov     [rbp+57h+var_30], rax
0x1801529db  lea     rax, aCryptographicE_2; "Cryptographic error calling CryptGetHas"...
0x1801529e2  mov     [rbp+57h+var_20], rax
0x1801529e6  lea     rax, [rbp+57h+arg_10]
0x1801529ea  mov     [rsp+0A0h+var_58], rax
0x1801529ef  lea     rax, [rbp+57h+var_28]
0x1801529f3  mov     [rsp+0A0h+var_60], rax
0x1801529f8  lea     rax, [rbp+57h+arg_18]
0x1801529fc  mov     [rsp+0A0h+var_68], rax
0x180152a01  lea     rax, [rbp+57h+var_30]
0x180152a05  mov     [rsp+0A0h+var_70], rax
0x180152a0a  lea     rax, [rbp+57h+var_48]
0x180152a0e  mov     [rsp+0A0h+var_78], rax
0x180152a13  lea     rax, [rbp+57h+var_20]
0x180152a17  mov     [rbp+57h+arg_18], 63Fh
0x180152a1e  jmp     loc_180152ACC
0x180152a23  mov     rcx, [rbp+57h+phHash]; hHash
0x180152a27  lea     r8, [rdi+14h]; pbData
0x180152a2b  xor     ebx, ebx
0x180152a2d  lea     r9, [rbp+57h+pbData]; pdwDataLen
0x180152a31  mov     [rsp+0A0h+dwFlags], ebx; dwFlags
0x180152a35  lea     edx, [rbx+2]; dwParam
0x180152a38  call    cs:__imp_CryptGetHashParam
0x180152a3e  test    eax, eax
0x180152a40  jnz     loc_180152AD9
0x180152a46  call    cs:__imp_GetLastError
0x180152a4c  mov     ebx, eax
0x180152a4e  test    eax, eax
0x180152a50  jle     short loc_180152A5B
0x180152a52  movzx   ebx, ax
0x180152a55  or      ebx, 80070000h
0x180152a5b  mov     eax, cs:CallbackContext
0x180152a61  cmp     eax, 2
0x180152a64  jbe     short loc_180152AD9
0x180152a66  mov     eax, [rbp+57h+pbData]
0x180152a69  lea     rdx, byte_18029C75F
0x180152a70  mov     dword ptr [rbp+57h+arg_10], eax
0x180152a73  lea     rax, aCreatehashfrom_0; "CreateHashFromMTCookie_LocalImpl"
0x180152a7a  mov     [rbp+57h+var_20], rax
0x180152a7e  lea     rax, aOnecoreTermsrv_41; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180152a85  mov     [rbp+57h+var_28], rax
0x180152a89  lea     rax, aCryptographicE_4; "Cryptographic error calling CryptGetHas"...
0x180152a90  mov     [rbp+57h+var_30], rax
0x180152a94  lea     rax, [rbp+57h+arg_10]
0x180152a98  mov     [rsp+0A0h+var_58], rax
0x180152a9d  lea     rax, [rbp+57h+var_20]
0x180152aa1  mov     [rsp+0A0h+var_60], rax
0x180152aa6  lea     rax, [rbp+57h+arg_18]
0x180152aaa  mov     [rsp+0A0h+var_68], rax
0x180152aaf  lea     rax, [rbp+57h+var_28]
0x180152ab3  mov     [rsp+0A0h+var_70], rax
0x180152ab8  lea     rax, [rbp+57h+var_48]
0x180152abc  mov     [rsp+0A0h+var_78], rax
0x180152ac1  lea     rax, [rbp+57h+var_30]
0x180152ac5  mov     [rbp+57h+arg_18], 64Fh
0x180152acc  mov     qword ptr [rsp+0A0h+dwFlags], rax
0x180152ad1  mov     dword ptr [rbp+57h+var_48], ebx
0x180152ad4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180152ad9  mov     rcx, [rbp+57h+phHash]; hHash
0x180152add  test    rcx, rcx
0x180152ae0  jz      short loc_180152AE8
0x180152ae2  call    cs:__imp_CryptDestroyHash
0x180152ae8  mov     rcx, [rbp+57h+phProv]; hProv
0x180152aec  test    rcx, rcx
0x180152aef  jz      short loc_180152AF9
0x180152af1  xor     edx, edx; dwFlags
0x180152af3  call    cs:__imp_CryptReleaseContext
0x180152af9  mov     eax, cs:CallbackContext
0x180152aff  cmp     eax, 4
0x180152b02  jbe     short loc_180152B3F
0x180152b04  mov     ecx, [rdi+14h]
0x180152b07  lea     rax, aExitingCreateh; "Exiting CreateHashFromMTCookie"
0x180152b0e  mov     [rbp+57h+var_20], rax
0x180152b12  lea     rdx, word_18029B6A2
0x180152b19  lea     rax, [rbp+57h+arg_10]
0x180152b1d  mov     dword ptr [rbp+57h+arg_10], ecx
0x180152b20  mov     [rsp+0A0h+var_70], rax
0x180152b25  lea     rax, [rbp+57h+arg_18]
0x180152b29  mov     [rsp+0A0h+var_78], rax
0x180152b2e  lea     rax, [rbp+57h+var_20]
0x180152b32  mov     qword ptr [rsp+0A0h+dwFlags], rax
0x180152b37  mov     [rbp+57h+arg_18], ebx
0x180152b3a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180152b3f  mov     eax, ebx
0x180152b41  add     rsp, 90h
0x180152b48  pop     rdi
0x180152b49  pop     rbx
0x180152b4a  pop     rbp
0x180152b4b  retn
```
