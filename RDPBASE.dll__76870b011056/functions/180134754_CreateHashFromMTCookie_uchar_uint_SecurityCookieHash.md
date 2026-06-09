# CreateHashFromMTCookie(uchar *,uint,SecurityCookieHash *)

- ea: `0x180134754`
- end: `0x180134c7e`
- name: `?CreateHashFromMTCookie@@YAJPEAEIPEAUSecurityCookieHash@@@Z`
- size: `1322`
- prototype: `__int64 __fastcall(BYTE *pbData, unsigned int, struct SecurityCookieHash *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18006a118`
- `0x1801326c0`

## callees

- `0x1800018a4`
- `0x180002550`
- `0x180003158`
- `0x180004970`
- `0x180134754`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180134859`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801348ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013499b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180134a50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180134b78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180134859`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801348ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013499b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180134a50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180134b78`
- `CRYPTSP!CryptDestroyHash` at `0x180134c14`
- `CRYPTSP!CryptDestroyHash` at `0x180134c14`
- `CRYPTSP!CryptReleaseContext` at `0x180134c25`
- `CRYPTSP!CryptReleaseContext` at `0x180134c25`
- `CRYPTSP!CryptAcquireContextW` at `0x18013484b`
- `CRYPTSP!CryptAcquireContextW` at `0x18013484b`
- `CRYPTSP!CryptCreateHash` at `0x1801348f1`
- `CRYPTSP!CryptCreateHash` at `0x1801348f1`
- `CRYPTSP!CryptHashData` at `0x18013498d`
- `CRYPTSP!CryptHashData` at `0x18013498d`
- `CRYPTSP!CryptGetHashParam` at `0x180134a42`
- `CRYPTSP!CryptGetHashParam` at `0x180134b6a`
- `CRYPTSP!CryptGetHashParam` at `0x180134a42`
- `CRYPTSP!CryptGetHashParam` at `0x180134b6a`

## string_xrefs

- `0x180134788`: `Entering CreateHashFromMTCookie`
- `0x1801347ef`: `CreateHashFromMTCookie error invalid parameter`
- `0x1801347cb`: `CreateHashFromMTCookie`
- `0x18013487d`: `CreateHashFromMTCookie`
- `0x180134923`: `CreateHashFromMTCookie`
- `0x1801349bf`: `CreateHashFromMTCookie`
- `0x180134a74`: `CreateHashFromMTCookie`
- `0x180134af7`: `CreateHashFromMTCookie`
- `0x180134ba5`: `CreateHashFromMTCookie`
- `0x180134947`: `Cryptographic error calling CryptCreateHash`
- `0x180134c39`: `Exiting CreateHashFromMTCookie`

## pseudocode

```c
__int64 __fastcall CreateHashFromMTCookie(BYTE *pbData, DWORD a2, BYTE *a3, int a4)
{
  unsigned int v6; // ebx
  __int16 *v7; // rdx
  const char **v8; // rax
  signed int v9; // eax
  signed int v10; // eax
  signed int v11; // eax
  int v12; // ecx
  signed int v13; // eax
  __int16 *v14; // rdx
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
      (unsigned int)&CallbackContext,
      (unsigned int)byte_1801D542D,
      0,
      a4,
      (__int64)&v30);
  }
  if ( !a3 )
  {
    v6 = -2147024809;
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_36;
    LODWORD(v30) = 2271;
    v23 = "CreateHashFromMTCookie";
    v7 = (__int16 *)&byte_1801D4F57;
    v26 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudplocalendpoint.cpp";
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
            v14 = word_1801D46D2;
            LODWORD(v30) = pbDataa;
            v28[0] = "CreateHashFromMTCookie";
            v27 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudplocalendpoint.cpp";
            v26 = "Cryptographic error calling CryptGetHashParam for hash data";
            v21 = (const char **)v28;
            v19 = &v27;
            v15 = &v26;
            v31 = 2363;
          }
          else
          {
            v6 = -2147467259;
            if ( (unsigned int)CallbackContext <= 2 )
              goto LABEL_36;
            v14 = &word_1801D5546;
            LODWORD(v30) = pbDataa;
            v27 = "CreateHashFromMTCookie";
            v26 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudplocalendpoint.cpp";
            v28[0] = "Cryptographic error calling CryptGetHashParam returning hash size other than 32 as expected for SHA-256";
            v21 = &v27;
            v19 = &v26;
            v15 = (const char **)v28;
            v31 = 2347;
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
          LODWORD(v30) = 2338;
          v27 = "CreateHashFromMTCookie";
          v7 = (__int16 *)byte_1801D5129;
          v26 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudplocalendpoint.cpp";
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
          LODWORD(v30) = 2320;
          v27 = "CreateHashFromMTCookie";
          v7 = &word_1801D51D6;
          v26 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudplocalendpoint.cpp";
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
        LODWORD(v30) = 2305;
        v27 = "CreateHashFromMTCookie";
        v7 = word_1801D476A;
        v26 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudplocalendpoint.cpp";
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
      LODWORD(v30) = 2289;
      v27 = "CreateHashFromMTCookie";
      v7 = (__int16 *)&dword_1801D4C7C;
      v26 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudplocalendpoint.cpp";
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
      (unsigned int)byte_1801D49D3,
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
0x180134754  mov     [rsp-8+pbData], edx
0x180134758  push    rbp
0x180134759  push    rbx
0x18013475a  push    rdi
0x18013475b  lea     rbp, [rsp-47h]
0x180134760  sub     rsp, 90h
0x180134767  mov     eax, cs:CallbackContext
0x18013476d  mov     rdi, r8
0x180134770  mov     [rbp+57h+phProv], 0
0x180134778  mov     rbx, rcx
0x18013477b  mov     [rbp+57h+phHash], 0
0x180134783  cmp     eax, 4
0x180134786  jbe     short loc_1801347B2
0x180134788  lea     rax, aEnteringCreate; "Entering CreateHashFromMTCookie"
0x18013478f  xor     r8d, r8d
0x180134792  mov     [rbp+57h+arg_10], rax
0x180134796  lea     rdx, byte_1801D542D
0x18013479d  lea     rax, [rbp+57h+arg_10]
0x1801347a1  lea     rcx, CallbackContext
0x1801347a8  mov     qword ptr [rsp+0A0h+dwFlags], rax
0x1801347ad  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1801347b2  test    rdi, rdi
0x1801347b5  jnz     short loc_180134834
0x1801347b7  mov     eax, cs:CallbackContext
0x1801347bd  mov     ebx, 80070057h
0x1801347c2  cmp     eax, 2
0x1801347c5  jbe     loc_180134C0B
0x1801347cb  lea     rax, aCreatehashfrom; "CreateHashFromMTCookie"
0x1801347d2  mov     dword ptr [rbp+57h+arg_10], 8DFh
0x1801347d9  mov     [rbp+57h+var_48], rax
0x1801347dd  lea     rdx, byte_1801D4F57
0x1801347e4  lea     rax, aOnecoreTermsrv_26; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1801347eb  mov     [rbp+57h+var_30], rax
0x1801347ef  lea     rax, aCreatehashfrom_0; "CreateHashFromMTCookie error invalid pa"...
0x1801347f6  mov     [rbp+57h+var_28], rax
0x1801347fa  lea     rax, [rbp+57h+var_48]
0x1801347fe  mov     [rsp+0A0h+var_60], rax
0x180134803  lea     rax, [rbp+57h+arg_10]
0x180134807  mov     [rsp+0A0h+var_68], rax
0x18013480c  lea     rax, [rbp+57h+var_30]
0x180134810  mov     [rsp+0A0h+var_70], rax
0x180134815  lea     rax, [rbp+57h+arg_18]
0x180134819  mov     [rsp+0A0h+var_78], rax
0x18013481e  lea     rax, [rbp+57h+var_28]
0x180134822  mov     [rbp+57h+arg_18], ebx
0x180134825  mov     qword ptr [rsp+0A0h+dwFlags], rax
0x18013482a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18013482f  jmp     loc_180134C0B
0x180134834  mov     r9d, 18h; dwProvType
0x18013483a  mov     [rsp+0A0h+dwFlags], 0F0000000h; dwFlags
0x180134842  xor     r8d, r8d; szProvider
0x180134845  lea     rcx, [rbp+57h+phProv]; phProv
0x180134849  xor     edx, edx; szContainer
0x18013484b  call    cs:__imp_CryptAcquireContextW
0x180134851  test    eax, eax
0x180134853  jnz     loc_1801348D9
0x180134859  call    cs:__imp_GetLastError
0x18013485f  mov     ebx, eax
0x180134861  test    eax, eax
0x180134863  jle     short loc_18013486E
0x180134865  movzx   ebx, ax
0x180134868  or      ebx, 80070000h
0x18013486e  mov     eax, cs:CallbackContext
0x180134874  cmp     eax, 2
0x180134877  jbe     loc_180134C0B
0x18013487d  lea     rax, aCreatehashfrom; "CreateHashFromMTCookie"
0x180134884  mov     dword ptr [rbp+57h+arg_10], 8F1h
0x18013488b  mov     [rbp+57h+var_28], rax
0x18013488f  lea     rdx, dword_1801D4C7C
0x180134896  lea     rax, aOnecoreTermsrv_26; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18013489d  mov     [rbp+57h+var_30], rax
0x1801348a1  lea     rax, aCryptographicE_0; "Cryptographic error calling CryptAcquir"...
0x1801348a8  mov     [rbp+57h+var_48], rax
0x1801348ac  lea     rax, [rbp+57h+var_28]
0x1801348b0  mov     [rsp+0A0h+var_60], rax
0x1801348b5  lea     rax, [rbp+57h+arg_10]
0x1801348b9  mov     [rsp+0A0h+var_68], rax
0x1801348be  lea     rax, [rbp+57h+var_30]
0x1801348c2  mov     [rsp+0A0h+var_70], rax
0x1801348c7  lea     rax, [rbp+57h+arg_18]
0x1801348cb  mov     [rsp+0A0h+var_78], rax
0x1801348d0  lea     rax, [rbp+57h+var_48]
0x1801348d4  jmp     loc_180134822
0x1801348d9  mov     rcx, [rbp+57h+phProv]; hProv
0x1801348dd  lea     rax, [rbp+57h+phHash]
0x1801348e1  xor     r9d, r9d; dwFlags
0x1801348e4  mov     qword ptr [rsp+0A0h+dwFlags], rax; phHash
0x1801348e9  xor     r8d, r8d; hKey
0x1801348ec  mov     edx, 800Ch; Algid
0x1801348f1  call    cs:__imp_CryptCreateHash
0x1801348f7  test    eax, eax
0x1801348f9  jnz     loc_18013497F
0x1801348ff  call    cs:__imp_GetLastError
0x180134905  mov     ebx, eax
0x180134907  test    eax, eax
0x180134909  jle     short loc_180134914
0x18013490b  movzx   ebx, ax
0x18013490e  or      ebx, 80070000h
0x180134914  mov     eax, cs:CallbackContext
0x18013491a  cmp     eax, 2
0x18013491d  jbe     loc_180134C0B
0x180134923  lea     rax, aCreatehashfrom; "CreateHashFromMTCookie"
0x18013492a  mov     dword ptr [rbp+57h+arg_10], 901h
0x180134931  mov     [rbp+57h+var_28], rax
0x180134935  lea     rdx, word_1801D476A
0x18013493c  lea     rax, aOnecoreTermsrv_26; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180134943  mov     [rbp+57h+var_30], rax
0x180134947  lea     rax, aCryptographicE_4; "Cryptographic error calling CryptCreate"...
0x18013494e  mov     [rbp+57h+var_48], rax
0x180134952  lea     rax, [rbp+57h+var_28]
0x180134956  mov     [rsp+0A0h+var_60], rax
0x18013495b  lea     rax, [rbp+57h+arg_10]
0x18013495f  mov     [rsp+0A0h+var_68], rax
0x180134964  lea     rax, [rbp+57h+var_30]
0x180134968  mov     [rsp+0A0h+var_70], rax
0x18013496d  lea     rax, [rbp+57h+arg_18]
0x180134971  mov     [rsp+0A0h+var_78], rax
0x180134976  lea     rax, [rbp+57h+var_48]
0x18013497a  jmp     loc_180134822
0x18013497f  mov     rcx, [rbp+57h+phHash]; hHash
0x180134983  xor     r9d, r9d; dwFlags
0x180134986  mov     rdx, rbx; pbData
0x180134989  lea     r8d, [r9+10h]; dwDataLen
0x18013498d  call    cs:__imp_CryptHashData
0x180134993  test    eax, eax
0x180134995  jnz     loc_180134A1B
0x18013499b  call    cs:__imp_GetLastError
0x1801349a1  mov     ebx, eax
0x1801349a3  test    eax, eax
0x1801349a5  jle     short loc_1801349B0
0x1801349a7  movzx   ebx, ax
0x1801349aa  or      ebx, 80070000h
0x1801349b0  mov     eax, cs:CallbackContext
0x1801349b6  cmp     eax, 2
0x1801349b9  jbe     loc_180134C0B
0x1801349bf  lea     rax, aCreatehashfrom; "CreateHashFromMTCookie"
0x1801349c6  mov     dword ptr [rbp+57h+arg_10], 910h
0x1801349cd  mov     [rbp+57h+var_28], rax
0x1801349d1  lea     rdx, word_1801D51D6
0x1801349d8  lea     rax, aOnecoreTermsrv_26; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1801349df  mov     [rbp+57h+var_30], rax
0x1801349e3  lea     rax, aCryptographicE_1; "Cryptographic error calling CryptHashDa"...
0x1801349ea  mov     [rbp+57h+var_48], rax
0x1801349ee  lea     rax, [rbp+57h+var_28]
0x1801349f2  mov     [rsp+0A0h+var_60], rax
0x1801349f7  lea     rax, [rbp+57h+arg_10]
0x1801349fb  mov     [rsp+0A0h+var_68], rax
0x180134a00  lea     rax, [rbp+57h+var_30]
0x180134a04  mov     [rsp+0A0h+var_70], rax
0x180134a09  lea     rax, [rbp+57h+arg_18]
0x180134a0d  mov     [rsp+0A0h+var_78], rax
0x180134a12  lea     rax, [rbp+57h+var_48]
0x180134a16  jmp     loc_180134822
0x180134a1b  mov     rcx, [rbp+57h+phHash]; hHash
0x180134a1f  lea     r9, [rbp+57h+pdwDataLen]; pdwDataLen
0x180134a23  lea     r8, [rbp+57h+pbData]; pbData
0x180134a27  mov     [rbp+57h+pbData], 0
0x180134a2e  mov     edx, 4; dwParam
0x180134a33  mov     [rbp+57h+pdwDataLen], 4
0x180134a3a  mov     [rsp+0A0h+dwFlags], 0; dwFlags
0x180134a42  call    cs:__imp_CryptGetHashParam
0x180134a48  test    eax, eax
0x180134a4a  jnz     loc_180134AD0
0x180134a50  call    cs:__imp_GetLastError
0x180134a56  mov     ebx, eax
0x180134a58  test    eax, eax
0x180134a5a  jle     short loc_180134A65
0x180134a5c  movzx   ebx, ax
0x180134a5f  or      ebx, 80070000h
0x180134a65  mov     eax, cs:CallbackContext
0x180134a6b  cmp     eax, 2
0x180134a6e  jbe     loc_180134C0B
0x180134a74  lea     rax, aCreatehashfrom; "CreateHashFromMTCookie"
0x180134a7b  mov     dword ptr [rbp+57h+arg_10], 922h
0x180134a82  mov     [rbp+57h+var_28], rax
0x180134a86  lea     rdx, byte_1801D5129
0x180134a8d  lea     rax, aOnecoreTermsrv_26; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180134a94  mov     [rbp+57h+var_30], rax
0x180134a98  lea     rax, aCryptographicE; "Cryptographic error calling CryptGetHas"...
0x180134a9f  mov     [rbp+57h+var_48], rax
0x180134aa3  lea     rax, [rbp+57h+var_28]
0x180134aa7  mov     [rsp+0A0h+var_60], rax
0x180134aac  lea     rax, [rbp+57h+arg_10]
0x180134ab0  mov     [rsp+0A0h+var_68], rax
0x180134ab5  lea     rax, [rbp+57h+var_30]
0x180134ab9  mov     [rsp+0A0h+var_70], rax
0x180134abe  lea     rax, [rbp+57h+arg_18]
0x180134ac2  mov     [rsp+0A0h+var_78], rax
0x180134ac7  lea     rax, [rbp+57h+var_48]
0x180134acb  jmp     loc_180134822
0x180134ad0  cmp     [rbp+57h+pbData], 20h ; ' '
0x180134ad4  jz      short loc_180134B55
0x180134ad6  mov     eax, cs:CallbackContext
0x180134adc  mov     ebx, 80004005h
0x180134ae1  cmp     eax, 2
0x180134ae4  jbe     loc_180134C0B
0x180134aea  mov     eax, [rbp+57h+pbData]
0x180134aed  lea     rdx, word_1801D5546
0x180134af4  mov     dword ptr [rbp+57h+arg_10], eax
0x180134af7  lea     rax, aCreatehashfrom; "CreateHashFromMTCookie"
0x180134afe  mov     [rbp+57h+var_28], rax
0x180134b02  lea     rax, aOnecoreTermsrv_26; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180134b09  mov     [rbp+57h+var_30], rax
0x180134b0d  lea     rax, aCryptographicE_2; "Cryptographic error calling CryptGetHas"...
0x180134b14  mov     [rbp+57h+var_20], rax
0x180134b18  lea     rax, [rbp+57h+arg_10]
0x180134b1c  mov     [rsp+0A0h+var_58], rax
0x180134b21  lea     rax, [rbp+57h+var_28]
0x180134b25  mov     [rsp+0A0h+var_60], rax
0x180134b2a  lea     rax, [rbp+57h+arg_18]
0x180134b2e  mov     [rsp+0A0h+var_68], rax
0x180134b33  lea     rax, [rbp+57h+var_30]
0x180134b37  mov     [rsp+0A0h+var_70], rax
0x180134b3c  lea     rax, [rbp+57h+var_48]
0x180134b40  mov     [rsp+0A0h+var_78], rax
0x180134b45  lea     rax, [rbp+57h+var_20]
0x180134b49  mov     [rbp+57h+arg_18], 92Bh
0x180134b50  jmp     loc_180134BFE
0x180134b55  mov     rcx, [rbp+57h+phHash]; hHash
0x180134b59  lea     r8, [rdi+14h]; pbData
0x180134b5d  xor     ebx, ebx
0x180134b5f  lea     r9, [rbp+57h+pbData]; pdwDataLen
0x180134b63  mov     [rsp+0A0h+dwFlags], ebx; dwFlags
0x180134b67  lea     edx, [rbx+2]; dwParam
0x180134b6a  call    cs:__imp_CryptGetHashParam
0x180134b70  test    eax, eax
0x180134b72  jnz     loc_180134C0B
0x180134b78  call    cs:__imp_GetLastError
0x180134b7e  mov     ebx, eax
0x180134b80  test    eax, eax
0x180134b82  jle     short loc_180134B8D
0x180134b84  movzx   ebx, ax
0x180134b87  or      ebx, 80070000h
0x180134b8d  mov     eax, cs:CallbackContext
0x180134b93  cmp     eax, 2
0x180134b96  jbe     short loc_180134C0B
0x180134b98  mov     eax, [rbp+57h+pbData]
0x180134b9b  lea     rdx, word_1801D46D2
0x180134ba2  mov     dword ptr [rbp+57h+arg_10], eax
0x180134ba5  lea     rax, aCreatehashfrom; "CreateHashFromMTCookie"
0x180134bac  mov     [rbp+57h+var_20], rax
0x180134bb0  lea     rax, aOnecoreTermsrv_26; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180134bb7  mov     [rbp+57h+var_28], rax
0x180134bbb  lea     rax, aCryptographicE_5; "Cryptographic error calling CryptGetHas"...
0x180134bc2  mov     [rbp+57h+var_30], rax
0x180134bc6  lea     rax, [rbp+57h+arg_10]
0x180134bca  mov     [rsp+0A0h+var_58], rax
0x180134bcf  lea     rax, [rbp+57h+var_20]
0x180134bd3  mov     [rsp+0A0h+var_60], rax
0x180134bd8  lea     rax, [rbp+57h+arg_18]
0x180134bdc  mov     [rsp+0A0h+var_68], rax
0x180134be1  lea     rax, [rbp+57h+var_28]
0x180134be5  mov     [rsp+0A0h+var_70], rax
0x180134bea  lea     rax, [rbp+57h+var_48]
0x180134bee  mov     [rsp+0A0h+var_78], rax
0x180134bf3  lea     rax, [rbp+57h+var_30]
0x180134bf7  mov     [rbp+57h+arg_18], 93Bh
0x180134bfe  mov     qword ptr [rsp+0A0h+dwFlags], rax
0x180134c03  mov     dword ptr [rbp+57h+var_48], ebx
0x180134c06  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180134c0b  mov     rcx, [rbp+57h+phHash]; hHash
0x180134c0f  test    rcx, rcx
0x180134c12  jz      short loc_180134C1A
0x180134c14  call    cs:__imp_CryptDestroyHash
0x180134c1a  mov     rcx, [rbp+57h+phProv]; hProv
0x180134c1e  test    rcx, rcx
0x180134c21  jz      short loc_180134C2B
0x180134c23  xor     edx, edx; dwFlags
0x180134c25  call    cs:__imp_CryptReleaseContext
0x180134c2b  mov     eax, cs:CallbackContext
0x180134c31  cmp     eax, 4
0x180134c34  jbe     short loc_180134C71
0x180134c36  mov     ecx, [rdi+14h]
0x180134c39  lea     rax, aExitingCreateh; "Exiting CreateHashFromMTCookie"
0x180134c40  mov     [rbp+57h+var_20], rax
0x180134c44  lea     rdx, byte_1801D49D3
0x180134c4b  lea     rax, [rbp+57h+arg_10]
0x180134c4f  mov     dword ptr [rbp+57h+arg_10], ecx
0x180134c52  mov     [rsp+0A0h+var_70], rax
0x180134c57  lea     rax, [rbp+57h+arg_18]
0x180134c5b  mov     [rsp+0A0h+var_78], rax
0x180134c60  lea     rax, [rbp+57h+var_20]
0x180134c64  mov     qword ptr [rsp+0A0h+dwFlags], rax
0x180134c69  mov     [rbp+57h+arg_18], ebx
0x180134c6c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180134c71  mov     eax, ebx
0x180134c73  add     rsp, 90h
0x180134c7a  pop     rdi
0x180134c7b  pop     rbx
0x180134c7c  pop     rbp
0x180134c7d  retn
```
