# DomainNameFromStringSid(ushort const *,ushort * *)

- ea: `0x18015c960`
- end: `0x18015caf8`
- name: `?DomainNameFromStringSid@@YAJPEBGPEAPEAG@Z`
- size: `408`
- prototype: `int(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18015cb00`

## callees

- `0x18000202c`
- `0x18015c580`
- `0x18015c960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015c98e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015c99c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015c98e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015c99c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18015ca5b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18015ca5b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18015c984`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18015c984`

## string_xrefs

- `0x18015c9fe`: `onecore\termsrv\rdp\win\security\rdsaadauthserver.cpp`
- `0x18015caac`: `onecore\termsrv\rdp\win\security\rdsaadauthserver.cpp`
- `0x18015c9f3`: `DomainNameFromStringSid`
- `0x18015caa1`: `DomainNameFromStringSid`
- `0x18015ca88`: `ConvertStringSidToSid failed`
- `0x18015c9da`: `DomainNameFromSid failed`

## pseudocode

```c
__int64 __fastcall DomainNameFromStringSid(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  int v3; // ecx
  int v4; // r8d
  int v5; // r9d
  signed int LastError; // eax
  signed int v7; // ebx
  __int64 *v8; // rdx
  const char **v9; // rax
  const char **v11; // [rsp+30h] [rbp-50h]
  const char **v12; // [rsp+40h] [rbp-40h]
  const char **v13; // [rsp+48h] [rbp-38h]
  PSID Sid; // [rsp+50h] [rbp-30h] BYREF
  const char *v15; // [rsp+58h] [rbp-28h] BYREF
  const char *v16; // [rsp+60h] [rbp-20h] BYREF
  const char *v17; // [rsp+68h] [rbp-18h] BYREF
  _QWORD v18[2]; // [rsp+70h] [rbp-10h] BYREF
  int v19; // [rsp+A0h] [rbp+20h] BYREF
  signed int v20; // [rsp+A8h] [rbp+28h] BYREF

  Sid = 0;
  if ( ConvertStringSidToSidW(a1, &Sid) )
    goto LABEL_6;
  if ( GetLastError() )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( v7 >= 0 )
    {
LABEL_6:
      v7 = DomainNameFromSid(Sid, a2);
      if ( v7 < 0 )
      {
        v3 = (int)CallbackContext;
        if ( (unsigned int)CallbackContext > 2 )
        {
          v19 = 1157;
          v18[0] = "DomainNameFromSid failed";
          v8 = (__int64 *)byte_18029F601;
          v17 = "DomainNameFromStringSid";
          v16 = "onecore\\termsrv\\rdp\\win\\security\\rdsaadauthserver.cpp";
          v15 = "Error HResult failed";
          v13 = (const char **)v18;
          v12 = &v17;
          v11 = &v16;
          v9 = &v15;
LABEL_9:
          v20 = v7;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v3,
            (_DWORD)v8,
            v4,
            v5,
            (__int64)v9,
            (__int64)&v20,
            (__int64)v11,
            (__int64)&v19,
            (__int64)v12,
            (__int64)v13);
          goto LABEL_10;
        }
      }
      goto LABEL_10;
    }
  }
  else
  {
    v7 = -2147467259;
  }
  if ( (unsigned int)CallbackContext > 2 )
  {
    v19 = 1153;
    v15 = "ConvertStringSidToSid failed";
    v8 = qword_18029F5B0;
    v16 = "DomainNameFromStringSid";
    v17 = "onecore\\termsrv\\rdp\\win\\security\\rdsaadauthserver.cpp";
    v18[0] = "Error HResult failed";
    v13 = &v15;
    v12 = &v16;
    v11 = &v17;
    v9 = (const char **)v18;
    goto LABEL_9;
  }
LABEL_10:
  if ( Sid )
    LocalFree(Sid);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18015c960  mov     [rsp-8+arg_0], rbx
0x18015c965  mov     [rsp-8+arg_8], rdi
0x18015c96a  push    rbp
0x18015c96b  mov     rbp, rsp
0x18015c96e  sub     rsp, 80h
0x18015c975  mov     rdi, rdx
0x18015c978  mov     [rbp+Sid], 0
0x18015c980  lea     rdx, [rbp+Sid]; Sid
0x18015c984  call    cs:__imp_ConvertStringSidToSidW
0x18015c98a  test    eax, eax
0x18015c98c  jnz     short loc_18015C9B9
0x18015c98e  call    cs:__imp_GetLastError
0x18015c994  test    eax, eax
0x18015c996  jz      loc_18015CA78
0x18015c99c  call    cs:__imp_GetLastError
0x18015c9a2  mov     ebx, eax
0x18015c9a4  test    eax, eax
0x18015c9a6  jle     short loc_18015C9B1
0x18015c9a8  movzx   ebx, ax
0x18015c9ab  or      ebx, 80070000h
0x18015c9b1  test    ebx, ebx
0x18015c9b3  js      loc_18015CA7D
0x18015c9b9  mov     rcx, [rbp+Sid]; Sid
0x18015c9bd  mov     rdx, rdi; unsigned __int16 **
0x18015c9c0  call    ?DomainNameFromSid@@YAJPEAXPEAPEAG@Z; DomainNameFromSid(void *,ushort * *)
0x18015c9c5  mov     ebx, eax
0x18015c9c7  test    eax, eax
0x18015c9c9  jns     loc_18015CA52
0x18015c9cf  mov     ecx, cs:CallbackContext
0x18015c9d5  cmp     ecx, 2
0x18015c9d8  jbe     short loc_18015CA52
0x18015c9da  lea     rax, aDomainnamefrom_0; "DomainNameFromSid failed"
0x18015c9e1  mov     [rbp+arg_10], 485h
0x18015c9e8  mov     [rbp+var_10], rax
0x18015c9ec  lea     rdx, byte_18029F601
0x18015c9f3  lea     rax, aDomainnamefrom_1; "DomainNameFromStringSid"
0x18015c9fa  mov     [rbp+var_18], rax
0x18015c9fe  lea     rax, aOnecoreTermsrv_7; "onecore\\termsrv\\rdp\\win\\security\\r"...
0x18015ca05  mov     [rbp+var_20], rax
0x18015ca09  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18015ca10  mov     [rbp+var_28], rax
0x18015ca14  lea     rax, [rbp+var_10]
0x18015ca18  mov     [rsp+80h+var_38], rax
0x18015ca1d  lea     rax, [rbp+var_18]
0x18015ca21  mov     [rsp+80h+var_40], rax
0x18015ca26  lea     rax, [rbp+arg_10]
0x18015ca2a  mov     [rsp+80h+var_48], rax
0x18015ca2f  lea     rax, [rbp+var_20]
0x18015ca33  mov     [rsp+80h+var_50], rax
0x18015ca38  lea     rax, [rbp+arg_18]
0x18015ca3c  mov     [rsp+80h+var_58], rax
0x18015ca41  lea     rax, [rbp+var_28]
0x18015ca45  mov     [rsp+80h+var_60], rax
0x18015ca4a  mov     [rbp+arg_18], ebx
0x18015ca4d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18015ca52  mov     rcx, [rbp+Sid]; hMem
0x18015ca56  test    rcx, rcx
0x18015ca59  jz      short loc_18015CA61
0x18015ca5b  call    cs:__imp_LocalFree
0x18015ca61  lea     r11, [rsp+80h+var_s0]
0x18015ca69  mov     eax, ebx
0x18015ca6b  mov     rbx, [r11+10h]
0x18015ca6f  mov     rdi, [r11+18h]
0x18015ca73  mov     rsp, r11
0x18015ca76  pop     rbp
0x18015ca77  retn
0x18015ca78  mov     ebx, 80004005h
0x18015ca7d  mov     eax, cs:CallbackContext
0x18015ca83  cmp     eax, 2
0x18015ca86  jbe     short loc_18015CA52
0x18015ca88  lea     rax, aConvertstrings_0; "ConvertStringSidToSid failed"
0x18015ca8f  mov     [rbp+arg_10], 481h
0x18015ca96  mov     [rbp+var_28], rax
0x18015ca9a  lea     rdx, qword_18029F5B0
0x18015caa1  lea     rax, aDomainnamefrom_1; "DomainNameFromStringSid"
0x18015caa8  mov     [rbp+var_20], rax
0x18015caac  lea     rax, aOnecoreTermsrv_7; "onecore\\termsrv\\rdp\\win\\security\\r"...
0x18015cab3  mov     [rbp+var_18], rax
0x18015cab7  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18015cabe  mov     [rbp+var_10], rax
0x18015cac2  lea     rax, [rbp+var_28]
0x18015cac6  mov     [rsp+80h+var_38], rax
0x18015cacb  lea     rax, [rbp+var_20]
0x18015cacf  mov     [rsp+80h+var_40], rax
0x18015cad4  lea     rax, [rbp+arg_10]
0x18015cad8  mov     [rsp+80h+var_48], rax
0x18015cadd  lea     rax, [rbp+var_18]
0x18015cae1  mov     [rsp+80h+var_50], rax
0x18015cae6  lea     rax, [rbp+arg_18]
0x18015caea  mov     [rsp+80h+var_58], rax
0x18015caef  lea     rax, [rbp+var_10]
0x18015caf3  jmp     loc_18015CA45
```
