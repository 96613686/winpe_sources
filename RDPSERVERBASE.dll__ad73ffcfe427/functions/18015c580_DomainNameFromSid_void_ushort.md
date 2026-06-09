# DomainNameFromSid(void *,ushort * *)

- ea: `0x18015c580`
- end: `0x18015c959`
- name: `?DomainNameFromSid@@YAJPEAXPEAPEAG@Z`
- size: `985`
- prototype: `__int64 __fastcall(PSID Sid, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18015c960`

## callees

- `0x18000116c`
- `0x18000202c`
- `0x18007f6a4`
- `0x18007f6b0`
- `0x18015c580`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015c5d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015c5df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015c5ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015c8b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015c8bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015c5d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015c5df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015c5ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015c8b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015c8bf`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18015c5ca`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18015c8ab`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18015c5ca`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18015c8ab`

## string_xrefs

- `0x18015c641`: `onecore\termsrv\rdp\win\security\rdsaadauthserver.cpp`
- `0x18015c6cc`: `onecore\termsrv\rdp\win\security\rdsaadauthserver.cpp`
- `0x18015c789`: `onecore\termsrv\rdp\win\security\rdsaadauthserver.cpp`
- `0x18015c835`: `onecore\termsrv\rdp\win\security\rdsaadauthserver.cpp`
- `0x18015c942`: `onecore\termsrv\rdp\win\security\rdsaadauthserver.cpp`
- `0x18015c6a5`: `LookupAccountSidW failed`
- `0x18015c91b`: `LookupAccountSidW failed`
- `0x18015c64f`: `Unexpected: No domain SID in the user SID?`
- `0x18015c628`: `DomainNameFromSid`
- `0x18015c6be`: `DomainNameFromSid`
- `0x18015c77b`: `DomainNameFromSid`
- `0x18015c827`: `DomainNameFromSid`
- `0x18015c934`: `DomainNameFromSid`

## pseudocode

```c
__int64 __fastcall DomainNameFromSid(PSID Sid, unsigned __int16 **a2)
{
  unsigned int v2; // ebx
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  signed int LastError; // eax
  WCHAR *v9; // rsi
  int v10; // r8d
  int v11; // r9d
  WCHAR *ReferencedDomainName; // rdi
  int v13; // r8d
  int v14; // r9d
  int v15; // ecx
  __int16 *v16; // rdx
  const char *v17; // rax
  signed int v18; // eax
  enum _SID_NAME_USE peUse; // [rsp+50h] [rbp-30h] BYREF
  int v21; // [rsp+54h] [rbp-2Ch] BYREF
  int v22; // [rsp+58h] [rbp-28h] BYREF
  const char *v23; // [rsp+60h] [rbp-20h] BYREF
  const char *v24; // [rsp+68h] [rbp-18h] BYREF
  const char *v25; // [rsp+70h] [rbp-10h] BYREF
  const char *v26; // [rsp+78h] [rbp-8h] BYREF
  DWORD cchReferencedDomainName; // [rsp+C0h] [rbp+40h] BYREF
  DWORD cchName; // [rsp+C8h] [rbp+48h] BYREF

  v2 = 0;
  cchName = 0;
  cchReferencedDomainName = 0;
  peUse = 0;
  if ( LookupAccountSidW(0, Sid, 0, &cchName, 0, &cchReferencedDomainName, &peUse) || GetLastError() == 122 )
    goto LABEL_7;
  if ( GetLastError() )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    if ( (v2 & 0x80000000) == 0 )
    {
LABEL_7:
      if ( !cchReferencedDomainName )
      {
        v2 = -2147467259;
        if ( (unsigned int)CallbackContext > 2 )
        {
          v22 = 1107;
          v26 = "DomainNameFromSid";
          v21 = -2147467259;
          v25 = "onecore\\termsrv\\rdp\\win\\security\\rdsaadauthserver.cpp";
          v24 = "Unexpected: No domain SID in the user SID?";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v5,
            (unsigned int)&dword_18029F6F4,
            v6,
            v7,
            (__int64)&v24,
            (__int64)&v21,
            (__int64)&v25,
            (__int64)&v22,
            (__int64)&v26);
        }
        return v2;
      }
      v9 = (WCHAR *)operator new(saturated_mul(cchName, 2u));
      if ( !v9 )
      {
        v2 = -2147024882;
        if ( (unsigned int)CallbackContext > 2 )
        {
          v22 = 1112;
          v26 = "pwszUserName allocation failed";
          v21 = -2147024882;
          v25 = "DomainNameFromSid";
          v24 = "onecore\\termsrv\\rdp\\win\\security\\rdsaadauthserver.cpp";
          v23 = "Error condition failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            -2147024882,
            (unsigned int)byte_18029F73D,
            v10,
            v11,
            (__int64)&v23,
            (__int64)&v21,
            (__int64)&v24,
            (__int64)&v22,
            (__int64)&v25,
            (__int64)&v26);
        }
        return v2;
      }
      ReferencedDomainName = (WCHAR *)operator new(saturated_mul(cchReferencedDomainName, 2u));
      if ( !ReferencedDomainName )
      {
        v15 = -2147024882;
        v2 = -2147024882;
        if ( (unsigned int)CallbackContext <= 2 )
          goto LABEL_26;
        v22 = 1115;
        v26 = "pwszDomainName allocation failed";
        v16 = word_18029F652;
        v21 = -2147024882;
        v25 = "DomainNameFromSid";
        v24 = "onecore\\termsrv\\rdp\\win\\security\\rdsaadauthserver.cpp";
        v17 = "Error condition failed";
        goto LABEL_19;
      }
      if ( LookupAccountSidW(0, Sid, v9, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
        goto LABEL_25;
      if ( GetLastError() )
      {
        v18 = GetLastError();
        v2 = v18;
        if ( v18 > 0 )
          v2 = (unsigned __int16)v18 | 0x80070000;
        if ( (v2 & 0x80000000) == 0 )
        {
LABEL_25:
          *a2 = ReferencedDomainName;
          ReferencedDomainName = 0;
          goto LABEL_26;
        }
      }
      else
      {
        v2 = -2147467259;
      }
      if ( (unsigned int)CallbackContext > 2 )
      {
        v22 = 1120;
        v26 = "LookupAccountSidW failed";
        v16 = (__int16 *)byte_18029F6A3;
        v21 = v2;
        v25 = "DomainNameFromSid";
        v24 = "onecore\\termsrv\\rdp\\win\\security\\rdsaadauthserver.cpp";
        v17 = "Error HResult failed";
LABEL_19:
        v23 = v17;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v15,
          (_DWORD)v16,
          v13,
          v14,
          (__int64)&v23,
          (__int64)&v21,
          (__int64)&v24,
          (__int64)&v22,
          (__int64)&v25,
          (__int64)&v26);
      }
LABEL_26:
      operator delete(v9);
      if ( ReferencedDomainName )
        operator delete(ReferencedDomainName);
      return v2;
    }
  }
  else
  {
    v2 = -2147467259;
  }
  if ( (unsigned int)CallbackContext > 2 )
  {
    v21 = 1100;
    v23 = "LookupAccountSidW failed";
    v22 = v2;
    v24 = "DomainNameFromSid";
    v25 = "onecore\\termsrv\\rdp\\win\\security\\rdsaadauthserver.cpp";
    v26 = "Error HResult failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v5,
      (unsigned int)&word_18029F78E,
      v6,
      v7,
      (__int64)&v26,
      (__int64)&v22,
      (__int64)&v25,
      (__int64)&v21,
      (__int64)&v24,
      (__int64)&v23);
  }
  return v2;
}

```

## disassembly

```asm
0x18015c580  mov     [rsp-28h+arg_0], rbx
0x18015c585  push    rbp
0x18015c586  push    rsi
0x18015c587  push    rdi
0x18015c588  push    r14
0x18015c58a  push    r15
0x18015c58c  mov     rbp, rsp
0x18015c58f  sub     rsp, 80h
0x18015c596  xor     ebx, ebx
0x18015c598  lea     rax, [rbp+var_30]
0x18015c59c  mov     [rsp+80h+peUse], rax; peUse
0x18015c5a1  lea     r9, [rbp+cchName]; cchName
0x18015c5a5  lea     rax, [rbp+arg_10]
0x18015c5a9  mov     [rbp+cchName], ebx
0x18015c5ac  mov     r15, rdx
0x18015c5af  mov     [rsp+80h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18015c5b4  mov     r14, rcx
0x18015c5b7  mov     [rsp+80h+ReferencedDomainName], rbx; ReferencedDomainName
0x18015c5bc  mov     rdx, rcx; Sid
0x18015c5bf  mov     [rbp+arg_10], ebx
0x18015c5c2  xor     r8d, r8d; Name
0x18015c5c5  mov     [rbp+var_30], ebx
0x18015c5c8  xor     ecx, ecx; lpSystemName
0x18015c5ca  call    cs:__imp_LookupAccountSidW
0x18015c5d0  test    eax, eax
0x18015c5d2  jnz     short loc_18015C60A
0x18015c5d4  call    cs:__imp_GetLastError
0x18015c5da  cmp     eax, 7Ah ; 'z'
0x18015c5dd  jz      short loc_18015C60A
0x18015c5df  call    cs:__imp_GetLastError
0x18015c5e5  test    eax, eax
0x18015c5e7  jz      loc_18015C691
0x18015c5ed  call    cs:__imp_GetLastError
0x18015c5f3  mov     ebx, eax
0x18015c5f5  test    eax, eax
0x18015c5f7  jle     short loc_18015C602
0x18015c5f9  movzx   ebx, ax
0x18015c5fc  or      ebx, 80070000h
0x18015c602  test    ebx, ebx
0x18015c604  js      loc_18015C696
0x18015c60a  cmp     [rbp+arg_10], 0
0x18015c60e  jnz     loc_18015C722
0x18015c614  mov     eax, cs:CallbackContext
0x18015c61a  mov     ebx, 80004005h
0x18015c61f  cmp     eax, 2
0x18015c622  jbe     loc_18015C8F2
0x18015c628  lea     rax, aDomainnamefrom_2; "DomainNameFromSid"
0x18015c62f  mov     [rbp+var_28], 453h
0x18015c636  mov     [rbp+var_8], rax
0x18015c63a  lea     rdx, dword_18029F6F4
0x18015c641  lea     rax, aOnecoreTermsrv_7; "onecore\\termsrv\\rdp\\win\\security\\r"...
0x18015c648  mov     [rbp+var_2C], ebx
0x18015c64b  mov     [rbp+var_10], rax
0x18015c64f  lea     rax, aUnexpectedNoDo; "Unexpected: No domain SID in the user S"...
0x18015c656  mov     [rbp+var_18], rax
0x18015c65a  lea     rax, [rbp+var_8]
0x18015c65e  mov     [rsp+80h+var_40], rax
0x18015c663  lea     rax, [rbp+var_28]
0x18015c667  mov     [rsp+80h+var_48], rax
0x18015c66c  lea     rax, [rbp+var_10]
0x18015c670  mov     [rsp+80h+peUse], rax
0x18015c675  lea     rax, [rbp+var_2C]
0x18015c679  mov     [rsp+80h+cchReferencedDomainName], rax
0x18015c67e  lea     rax, [rbp+var_18]
0x18015c682  mov     [rsp+80h+ReferencedDomainName], rax
0x18015c687  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18015c68c  jmp     loc_18015C8F2
0x18015c691  mov     ebx, 80004005h
0x18015c696  mov     eax, cs:CallbackContext
0x18015c69c  cmp     eax, 2
0x18015c69f  jbe     loc_18015C8F2
0x18015c6a5  lea     rax, aLookupaccounts_0; "LookupAccountSidW failed"
0x18015c6ac  mov     [rbp+var_2C], 44Ch
0x18015c6b3  mov     [rbp+var_20], rax
0x18015c6b7  lea     rdx, word_18029F78E
0x18015c6be  lea     rax, aDomainnamefrom_2; "DomainNameFromSid"
0x18015c6c5  mov     [rbp+var_28], ebx
0x18015c6c8  mov     [rbp+var_18], rax
0x18015c6cc  lea     rax, aOnecoreTermsrv_7; "onecore\\termsrv\\rdp\\win\\security\\r"...
0x18015c6d3  mov     [rbp+var_10], rax
0x18015c6d7  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18015c6de  mov     [rbp+var_8], rax
0x18015c6e2  lea     rax, [rbp+var_20]
0x18015c6e6  mov     [rsp+80h+var_38], rax
0x18015c6eb  lea     rax, [rbp+var_18]
0x18015c6ef  mov     [rsp+80h+var_40], rax
0x18015c6f4  lea     rax, [rbp+var_2C]
0x18015c6f8  mov     [rsp+80h+var_48], rax
0x18015c6fd  lea     rax, [rbp+var_10]
0x18015c701  mov     [rsp+80h+peUse], rax
0x18015c706  lea     rax, [rbp+var_28]
0x18015c70a  mov     [rsp+80h+cchReferencedDomainName], rax
0x18015c70f  lea     rax, [rbp+var_8]
0x18015c713  mov     [rsp+80h+ReferencedDomainName], rax
0x18015c718  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18015c71d  jmp     loc_18015C8F2
0x18015c722  mov     ecx, [rbp+cchName]
0x18015c725  mov     eax, 2
0x18015c72a  mul     rcx
0x18015c72d  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18015c734  cmovb   rax, rdi
0x18015c738  mov     rcx, rax; Size
0x18015c73b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18015c740  mov     rsi, rax
0x18015c743  test    rax, rax
0x18015c746  jnz     loc_18015C7D5
0x18015c74c  mov     eax, cs:CallbackContext
0x18015c752  mov     ecx, 8007000Eh
0x18015c757  mov     ebx, ecx
0x18015c759  cmp     eax, 2
0x18015c75c  jbe     loc_18015C8F2
0x18015c762  lea     rax, aPwszusernameAl; "pwszUserName allocation failed"
0x18015c769  mov     [rbp+var_28], 458h
0x18015c770  mov     [rbp+var_8], rax
0x18015c774  lea     rdx, byte_18029F73D
0x18015c77b  lea     rax, aDomainnamefrom_2; "DomainNameFromSid"
0x18015c782  mov     [rbp+var_2C], ecx
0x18015c785  mov     [rbp+var_10], rax
0x18015c789  lea     rax, aOnecoreTermsrv_7; "onecore\\termsrv\\rdp\\win\\security\\r"...
0x18015c790  mov     [rbp+var_18], rax
0x18015c794  lea     rax, aErrorCondition; "Error condition failed"
0x18015c79b  mov     [rbp+var_20], rax
0x18015c79f  lea     rax, [rbp+var_8]
0x18015c7a3  mov     [rsp+80h+var_38], rax
0x18015c7a8  lea     rax, [rbp+var_10]
0x18015c7ac  mov     [rsp+80h+var_40], rax
0x18015c7b1  lea     rax, [rbp+var_28]
0x18015c7b5  mov     [rsp+80h+var_48], rax
0x18015c7ba  lea     rax, [rbp+var_18]
0x18015c7be  mov     [rsp+80h+peUse], rax
0x18015c7c3  lea     rax, [rbp+var_2C]
0x18015c7c7  mov     [rsp+80h+cchReferencedDomainName], rax
0x18015c7cc  lea     rax, [rbp+var_20]
0x18015c7d0  jmp     loc_18015C713
0x18015c7d5  mov     ecx, [rbp+arg_10]
0x18015c7d8  mov     eax, 2
0x18015c7dd  mul     rcx
0x18015c7e0  cmovb   rax, rdi
0x18015c7e4  mov     rcx, rax; Size
0x18015c7e7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18015c7ec  mov     rdi, rax
0x18015c7ef  test    rax, rax
0x18015c7f2  jnz     loc_18015C888
0x18015c7f8  mov     eax, cs:CallbackContext
0x18015c7fe  mov     ecx, 8007000Eh
0x18015c803  mov     ebx, ecx
0x18015c805  cmp     eax, 2
0x18015c808  jbe     loc_18015C8DD
0x18015c80e  lea     rax, aPwszdomainname; "pwszDomainName allocation failed"
0x18015c815  mov     [rbp+var_28], 45Bh
0x18015c81c  mov     [rbp+var_8], rax
0x18015c820  lea     rdx, word_18029F652
0x18015c827  lea     rax, aDomainnamefrom_2; "DomainNameFromSid"
0x18015c82e  mov     [rbp+var_2C], ecx
0x18015c831  mov     [rbp+var_10], rax
0x18015c835  lea     rax, aOnecoreTermsrv_7; "onecore\\termsrv\\rdp\\win\\security\\r"...
0x18015c83c  mov     [rbp+var_18], rax
0x18015c840  lea     rax, aErrorCondition; "Error condition failed"
0x18015c847  mov     [rbp+var_20], rax
0x18015c84b  lea     rax, [rbp+var_8]
0x18015c84f  mov     [rsp+80h+var_38], rax
0x18015c854  lea     rax, [rbp+var_10]
0x18015c858  mov     [rsp+80h+var_40], rax
0x18015c85d  lea     rax, [rbp+var_28]
0x18015c861  mov     [rsp+80h+var_48], rax
0x18015c866  lea     rax, [rbp+var_18]
0x18015c86a  mov     [rsp+80h+peUse], rax
0x18015c86f  lea     rax, [rbp+var_2C]
0x18015c873  mov     [rsp+80h+cchReferencedDomainName], rax
0x18015c878  lea     rax, [rbp+var_20]
0x18015c87c  mov     [rsp+80h+ReferencedDomainName], rax
0x18015c881  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18015c886  jmp     short loc_18015C8DD
0x18015c888  lea     rax, [rbp+var_30]
0x18015c88c  mov     r8, rsi; Name
0x18015c88f  mov     [rsp+80h+peUse], rax; peUse
0x18015c894  lea     r9, [rbp+cchName]; cchName
0x18015c898  lea     rax, [rbp+arg_10]
0x18015c89c  mov     rdx, r14; Sid
0x18015c89f  mov     [rsp+80h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18015c8a4  xor     ecx, ecx; lpSystemName
0x18015c8a6  mov     [rsp+80h+ReferencedDomainName], rdi; ReferencedDomainName
0x18015c8ab  call    cs:__imp_LookupAccountSidW
0x18015c8b1  test    eax, eax
0x18015c8b3  jnz     short loc_18015C8D8
0x18015c8b5  call    cs:__imp_GetLastError
0x18015c8bb  test    eax, eax
0x18015c8bd  jz      short loc_18015C90B
0x18015c8bf  call    cs:__imp_GetLastError
0x18015c8c5  mov     ebx, eax
0x18015c8c7  test    eax, eax
0x18015c8c9  jle     short loc_18015C8D4
0x18015c8cb  movzx   ebx, ax
0x18015c8ce  or      ebx, 80070000h
0x18015c8d4  test    ebx, ebx
0x18015c8d6  js      short loc_18015C910
0x18015c8d8  mov     [r15], rdi
0x18015c8db  xor     edi, edi
0x18015c8dd  mov     rcx, rsi; Block
0x18015c8e0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18015c8e5  test    rdi, rdi
0x18015c8e8  jz      short loc_18015C8F2
0x18015c8ea  mov     rcx, rdi; Block
0x18015c8ed  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18015c8f2  mov     eax, ebx
0x18015c8f4  mov     rbx, [rsp+80h+arg_0]
0x18015c8fc  add     rsp, 80h
0x18015c903  pop     r15
0x18015c905  pop     r14
0x18015c907  pop     rdi
0x18015c908  pop     rsi
0x18015c909  pop     rbp
0x18015c90a  retn
0x18015c90b  mov     ebx, 80004005h
0x18015c910  mov     eax, cs:CallbackContext
0x18015c916  cmp     eax, 2
0x18015c919  jbe     short loc_18015C8DD
0x18015c91b  lea     rax, aLookupaccounts_0; "LookupAccountSidW failed"
0x18015c922  mov     [rbp+var_28], 460h
0x18015c929  mov     [rbp+var_8], rax
0x18015c92d  lea     rdx, byte_18029F6A3
0x18015c934  lea     rax, aDomainnamefrom_2; "DomainNameFromSid"
0x18015c93b  mov     [rbp+var_2C], ebx
0x18015c93e  mov     [rbp+var_10], rax
0x18015c942  lea     rax, aOnecoreTermsrv_7; "onecore\\termsrv\\rdp\\win\\security\\r"...
0x18015c949  mov     [rbp+var_18], rax
0x18015c94d  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18015c954  jmp     loc_18015C847
```
