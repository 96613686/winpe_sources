# RDPWDUMXServerCertificateManager::ReadEncryptedFromRegistry(ushort const *,uchar * *,ulong *)

- ea: `0x180131b28`
- end: `0x18013201a`
- name: `?ReadEncryptedFromRegistry@RDPWDUMXServerCertificateManager@@CAJPEBGPEAPEAEPEAK@Z`
- size: `1266`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18013172c`

## callees

- `0x180002170`
- `0x180002294`
- `0x180077aa0`
- `0x180079770`
- `0x18007f6a4`
- `0x18007f6b0`
- `0x180131b28`
- `0x18019b31c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180131e65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180131e65`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180131c4f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180131d92`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180131c4f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180131d92`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180131fe9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180131fe9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180131b86`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180131b86`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180132006`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180132006`
- `CRYPT32!CryptUnprotectData` at `0x180131e57`
- `CRYPT32!CryptUnprotectData` at `0x180131e57`

## string_xrefs

- `0x180131bb6`: `ReadEncryptedFromRegistry`
- `0x180131c7f`: `ReadEncryptedFromRegistry`
- `0x180131dc2`: `ReadEncryptedFromRegistry`
- `0x180131e89`: `ReadEncryptedFromRegistry`
- `0x180131f6b`: `ReadEncryptedFromRegistry`
- `0x180131bdd`: `RegOpenKey failed! %d`
- `0x180131f93`: `No binary data available in %s registry key!`

## pseudocode

```c
__int64 __fastcall RDPWDUMXServerCertificateManager::ReadEncryptedFromRegistry(
        LPCWSTR lpValueName,
        unsigned __int8 **a2,
        unsigned int *a3)
{
  LSTATUS v6; // eax
  int v7; // r8d
  int v8; // r9d
  unsigned int v9; // ebx
  LSTATUS v10; // eax
  int v11; // r8d
  int v12; // r9d
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v14; // edx
  LSTATUS v15; // eax
  int v16; // r8d
  int v17; // r9d
  signed int LastError; // eax
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  size_t v22; // rcx
  unsigned __int8 *v23; // rax
  int v25; // [rsp+50h] [rbp-29h] BYREF
  int v26; // [rsp+54h] [rbp-25h] BYREF
  const char *v27; // [rsp+58h] [rbp-21h] BYREF
  const char *v28; // [rsp+60h] [rbp-19h] BYREF
  const char *v29; // [rsp+68h] [rbp-11h] BYREF
  const char *v30; // [rsp+70h] [rbp-9h] BYREF
  DWORD Type; // [rsp+78h] [rbp-1h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+7h] BYREF
  LPBYTE lpData[2]; // [rsp+88h] [rbp+Fh] BYREF
  DATA_BLOB pDataOut; // [rsp+98h] [rbp+1Fh] BYREF
  DWORD cbData; // [rsp+F8h] [rbp+7Fh] BYREF

  hKey = 0;
  cbData = 0;
  Type = 0;
  *(_OWORD *)lpData = 0;
  pDataOut = 0;
  v6 = RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\RDPEncoder\\", 0, 0x20019u, &hKey);
  if ( v6 )
  {
    if ( v6 > 0 )
      v9 = (unsigned __int16)v6 | 0x80070000;
    else
      v9 = v6;
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v27) = v6;
      v28 = "ReadEncryptedFromRegistry";
      v25 = 499;
      v29 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumxsec.cpp";
      v30 = "RegOpenKey failed! %d";
      v26 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v6,
        (unsigned int)qword_180292910,
        v7,
        v8,
        (__int64)&v30,
        (__int64)&v26,
        (__int64)&v29,
        (__int64)&v25,
        (__int64)&v28,
        (__int64)&v27);
    }
    goto LABEL_42;
  }
  v10 = RegQueryValueExW(hKey, lpValueName, 0, &Type, 0, &cbData);
  if ( v10 )
  {
    if ( v10 > 0 )
      v9 = (unsigned __int16)v10 | 0x80070000;
    else
      v9 = v10;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v26 = v10;
      v30 = "ReadEncryptedFromRegistry";
      v25 = 513;
      v29 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumxsec.cpp";
      v28 = "RegQueryValueEx failed! %d";
      LODWORD(v27) = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v10,
        (unsigned int)&byte_180292A87,
        v11,
        v12,
        (__int64)&v28,
        (__int64)&v27,
        (__int64)&v29,
        (__int64)&v25,
        (__int64)&v30,
        (__int64)&v26);
    }
    goto LABEL_42;
  }
  if ( cbData && Type == 3 )
  {
    lpData[1] = (LPBYTE)operator new(cbData);
    if ( !lpData[1] )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_22;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v14 = 14;
      goto LABEL_21;
    }
    LODWORD(lpData[0]) = cbData;
    v15 = RegQueryValueExW(hKey, lpValueName, 0, &Type, lpData[1], (LPDWORD)lpData);
    if ( v15 )
    {
      if ( v15 > 0 )
        v9 = (unsigned __int16)v15 | 0x80070000;
      else
        v9 = v15;
      if ( (unsigned int)CallbackContext > 2 )
      {
        v26 = v15;
        v30 = "ReadEncryptedFromRegistry";
        v25 = 538;
        v29 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumxsec.cpp";
        v28 = "RegQueryValueEx failed! %d";
        LODWORD(v27) = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v15,
          (unsigned int)byte_180292C43,
          v16,
          v17,
          (__int64)&v28,
          (__int64)&v27,
          (__int64)&v29,
          (__int64)&v25,
          (__int64)&v30,
          (__int64)&v26);
      }
    }
    else
    {
      if ( CryptUnprotectData((DATA_BLOB *)lpData, 0, 0, 0, 0, 1u, &pDataOut) )
      {
        v22 = pDataOut.cbData;
        *a3 = pDataOut.cbData;
        v23 = (unsigned __int8 *)operator new(v22);
        *a2 = v23;
        if ( v23 )
        {
          memcpy_0(v23, pDataOut.pbData, pDataOut.cbData);
          v9 = 0;
          goto LABEL_42;
        }
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
LABEL_22:
          v9 = -2147024882;
          goto LABEL_42;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v14 = 15;
LABEL_21:
        WPP_SF_Ds(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v14,
          (unsigned int)WPP_b4f6b43dc29030fa99a8a9d5e4ee0fc1_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)"BYTE");
        goto LABEL_22;
      }
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      if ( (unsigned int)CallbackContext > 2 )
      {
        v26 = v9;
        v30 = "ReadEncryptedFromRegistry";
        v25 = 556;
        v29 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumxsec.cpp";
        v28 = "CryptUnprotectData failed! 0x%x";
        LODWORD(v27) = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v19,
          (unsigned int)qword_1802929A0,
          v20,
          v21,
          (__int64)&v28,
          (__int64)&v27,
          (__int64)&v29,
          (__int64)&v25,
          (__int64)&v30,
          (__int64)&v26);
      }
    }
  }
  else
  {
    v9 = -2147024664;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v30 = (const char *)lpValueName;
      v29 = "ReadEncryptedFromRegistry";
      v26 = 519;
      v28 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumxsec.cpp";
      v27 = "No binary data available in %s registry key!";
      v25 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        0,
        (unsigned int)qword_180292BF0,
        v11,
        v12,
        (__int64)&v27,
        (__int64)&v25,
        (__int64)&v28,
        (__int64)&v26,
        (__int64)&v29,
        (__int64)&v30);
    }
  }
LABEL_42:
  if ( hKey )
    RegCloseKey(hKey);
  if ( lpData[1] )
    operator delete(lpData[1]);
  if ( pDataOut.pbData )
    LocalFree(pDataOut.pbData);
  return v9;
}

```

## disassembly

```asm
0x180131b28  push    rbp
0x180131b2a  push    rbx
0x180131b2b  push    rsi
0x180131b2c  push    rdi
0x180131b2d  lea     rbp, [rsp-3Fh]
0x180131b32  sub     rsp, 0B8h
0x180131b39  mov     rbx, r8
0x180131b3c  mov     [rbp+57h+hKey], 0
0x180131b44  mov     rsi, rdx
0x180131b47  mov     [rbp+57h+cbData], 0
0x180131b4e  mov     rdi, rcx
0x180131b51  mov     [rbp+57h+Type], 0
0x180131b58  xorps   xmm0, xmm0
0x180131b5b  lea     rax, [rbp+57h+hKey]
0x180131b5f  xorps   xmm1, xmm1
0x180131b62  mov     [rsp+0D0h+phkResult], rax; phkResult
0x180131b67  xor     r8d, r8d; ulOptions
0x180131b6a  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\RDPEncoder\\"
0x180131b71  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180131b78  mov     r9d, 20019h; samDesired
0x180131b7e  movups  xmmword ptr [rbp+57h+lpData], xmm0
0x180131b82  movups  xmmword ptr [rbp+57h+var_38.cbData], xmm1
0x180131b86  call    cs:__imp_RegOpenKeyExW
0x180131b8c  mov     ecx, eax
0x180131b8e  test    eax, eax
0x180131b90  jz      loc_180131C2F
0x180131b96  test    eax, eax
0x180131b98  jg      short loc_180131B9E
0x180131b9a  mov     ebx, eax
0x180131b9c  jmp     short loc_180131BA7
0x180131b9e  movzx   ebx, cx
0x180131ba1  or      ebx, 80070000h
0x180131ba7  mov     eax, cs:CallbackContext
0x180131bad  cmp     eax, 2
0x180131bb0  jbe     loc_180131FE0
0x180131bb6  lea     rax, aReadencryptedf; "ReadEncryptedFromRegistry"
0x180131bbd  mov     dword ptr [rbp+57h+var_78], ecx
0x180131bc0  mov     [rbp+57h+var_70], rax
0x180131bc4  lea     rdx, qword_180292910
0x180131bcb  lea     rax, aOnecoreTermsrv_50; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180131bd2  mov     [rbp+57h+var_80], 1F3h
0x180131bd9  mov     [rbp+57h+var_68], rax
0x180131bdd  lea     rax, aRegopenkeyFail; "RegOpenKey failed! %d"
0x180131be4  mov     [rbp+57h+var_60], rax
0x180131be8  lea     rax, [rbp+57h+var_78]
0x180131bec  mov     [rsp+0D0h+var_88], rax
0x180131bf1  lea     rax, [rbp+57h+var_70]
0x180131bf5  mov     [rsp+0D0h+var_90], rax
0x180131bfa  lea     rax, [rbp+57h+var_80]
0x180131bfe  mov     [rsp+0D0h+var_98], rax
0x180131c03  lea     rax, [rbp+57h+var_68]
0x180131c07  mov     [rsp+0D0h+pDataOut], rax
0x180131c0c  lea     rax, [rbp+57h+var_7C]
0x180131c10  mov     [rsp+0D0h+lpcbData], rax
0x180131c15  lea     rax, [rbp+57h+var_60]
0x180131c19  mov     [rbp+57h+var_7C], 80004005h
0x180131c20  mov     [rsp+0D0h+phkResult], rax
0x180131c25  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180131c2a  jmp     loc_180131FE0
0x180131c2f  mov     rcx, [rbp+57h+hKey]; hKey
0x180131c33  lea     rax, [rbp+57h+cbData]
0x180131c37  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x180131c3c  lea     r9, [rbp+57h+Type]; lpType
0x180131c40  xor     r8d, r8d; lpReserved
0x180131c43  mov     [rsp+0D0h+phkResult], 0; lpData
0x180131c4c  mov     rdx, rdi; lpValueName
0x180131c4f  call    cs:__imp_RegQueryValueExW
0x180131c55  mov     ecx, eax
0x180131c57  test    eax, eax
0x180131c59  jz      loc_180131CEE
0x180131c5f  test    eax, eax
0x180131c61  jg      short loc_180131C67
0x180131c63  mov     ebx, eax
0x180131c65  jmp     short loc_180131C70
0x180131c67  movzx   ebx, cx
0x180131c6a  or      ebx, 80070000h
0x180131c70  mov     eax, cs:CallbackContext
0x180131c76  cmp     eax, 2
0x180131c79  jbe     loc_180131FE0
0x180131c7f  lea     rax, aReadencryptedf; "ReadEncryptedFromRegistry"
0x180131c86  mov     [rbp+57h+var_7C], ecx
0x180131c89  mov     [rbp+57h+var_60], rax
0x180131c8d  lea     rdx, byte_180292A87
0x180131c94  lea     rax, aOnecoreTermsrv_50; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180131c9b  mov     [rbp+57h+var_80], 201h
0x180131ca2  mov     [rbp+57h+var_68], rax
0x180131ca6  lea     rax, aRegqueryvaluee; "RegQueryValueEx failed! %d"
0x180131cad  mov     [rbp+57h+var_70], rax
0x180131cb1  lea     rax, [rbp+57h+var_7C]
0x180131cb5  mov     [rsp+0D0h+var_88], rax
0x180131cba  lea     rax, [rbp+57h+var_60]
0x180131cbe  mov     [rsp+0D0h+var_90], rax
0x180131cc3  lea     rax, [rbp+57h+var_80]
0x180131cc7  mov     [rsp+0D0h+var_98], rax
0x180131ccc  lea     rax, [rbp+57h+var_68]
0x180131cd0  mov     [rsp+0D0h+pDataOut], rax
0x180131cd5  lea     rax, [rbp+57h+var_78]
0x180131cd9  mov     [rsp+0D0h+lpcbData], rax
0x180131cde  lea     rax, [rbp+57h+var_70]
0x180131ce2  mov     dword ptr [rbp+57h+var_78], 80004005h
0x180131ce9  jmp     loc_180131C20
0x180131cee  mov     eax, [rbp+57h+cbData]
0x180131cf1  test    eax, eax
0x180131cf3  jz      loc_180131F5B
0x180131cf9  cmp     [rbp+57h+Type], 3
0x180131cfd  jnz     loc_180131F5B
0x180131d03  mov     ecx, eax; Size
0x180131d05  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180131d0a  mov     [rbp+57h+lpData+8], rax
0x180131d0e  test    rax, rax
0x180131d11  jnz     short loc_180131D6C
0x180131d13  mov     rax, cs:WPP_GLOBAL_Control
0x180131d1a  lea     rcx, WPP_GLOBAL_Control
0x180131d21  cmp     rax, rcx
0x180131d24  jz      short loc_180131D62
0x180131d26  test    byte ptr [rax+1Ch], 8
0x180131d2a  jz      short loc_180131D62
0x180131d2c  cmp     byte ptr [rax+19h], 2
0x180131d30  jb      short loc_180131D62
0x180131d32  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180131d37  mov     edx, 0Eh
0x180131d3c  lea     rcx, aByte; "BYTE"
0x180131d43  mov     r9d, eax
0x180131d46  mov     [rsp+0D0h+phkResult], rcx
0x180131d4b  lea     r8, WPP_b4f6b43dc29030fa99a8a9d5e4ee0fc1_Traceguids
0x180131d52  mov     rcx, cs:WPP_GLOBAL_Control
0x180131d59  mov     rcx, [rcx+10h]
0x180131d5d  call    WPP_SF_Ds
0x180131d62  mov     ebx, 8007000Eh
0x180131d67  jmp     loc_180131FE0
0x180131d6c  mov     eax, [rbp+57h+cbData]
0x180131d6f  lea     r9, [rbp+57h+Type]; lpType
0x180131d73  mov     rcx, [rbp+57h+hKey]; hKey
0x180131d77  xor     r8d, r8d; lpReserved
0x180131d7a  mov     dword ptr [rbp+57h+lpData], eax
0x180131d7d  mov     rdx, rdi; lpValueName
0x180131d80  lea     rax, [rbp+57h+lpData]
0x180131d84  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x180131d89  mov     rax, [rbp+57h+lpData+8]
0x180131d8d  mov     [rsp+0D0h+phkResult], rax; lpData
0x180131d92  call    cs:__imp_RegQueryValueExW
0x180131d98  mov     ecx, eax
0x180131d9a  test    eax, eax
0x180131d9c  jz      loc_180131E31
0x180131da2  test    eax, eax
0x180131da4  jg      short loc_180131DAA
0x180131da6  mov     ebx, eax
0x180131da8  jmp     short loc_180131DB3
0x180131daa  movzx   ebx, cx
0x180131dad  or      ebx, 80070000h
0x180131db3  mov     eax, cs:CallbackContext
0x180131db9  cmp     eax, 2
0x180131dbc  jbe     loc_180131FE0
0x180131dc2  lea     rax, aReadencryptedf; "ReadEncryptedFromRegistry"
0x180131dc9  mov     [rbp+57h+var_7C], ecx
0x180131dcc  mov     [rbp+57h+var_60], rax
0x180131dd0  lea     rdx, byte_180292C43
0x180131dd7  lea     rax, aOnecoreTermsrv_50; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180131dde  mov     [rbp+57h+var_80], 21Ah
0x180131de5  mov     [rbp+57h+var_68], rax
0x180131de9  lea     rax, aRegqueryvaluee; "RegQueryValueEx failed! %d"
0x180131df0  mov     [rbp+57h+var_70], rax
0x180131df4  lea     rax, [rbp+57h+var_7C]
0x180131df8  mov     [rsp+0D0h+var_88], rax
0x180131dfd  lea     rax, [rbp+57h+var_60]
0x180131e01  mov     [rsp+0D0h+var_90], rax
0x180131e06  lea     rax, [rbp+57h+var_80]
0x180131e0a  mov     [rsp+0D0h+var_98], rax
0x180131e0f  lea     rax, [rbp+57h+var_68]
0x180131e13  mov     [rsp+0D0h+pDataOut], rax
0x180131e18  lea     rax, [rbp+57h+var_78]
0x180131e1c  mov     [rsp+0D0h+lpcbData], rax
0x180131e21  lea     rax, [rbp+57h+var_70]
0x180131e25  mov     dword ptr [rbp+57h+var_78], 80004005h
0x180131e2c  jmp     loc_180131C20
0x180131e31  lea     rax, [rbp+57h+var_38]
0x180131e35  xor     r9d, r9d; pvReserved
0x180131e38  mov     [rsp+0D0h+pDataOut], rax; pDataOut
0x180131e3d  lea     rcx, [rbp+57h+lpData]; pDataIn
0x180131e41  mov     dword ptr [rsp+0D0h+lpcbData], 1; dwFlags
0x180131e49  xor     r8d, r8d; pOptionalEntropy
0x180131e4c  xor     edx, edx; ppszDataDescr
0x180131e4e  mov     [rsp+0D0h+phkResult], 0; pPromptStruct
0x180131e57  call    cs:__imp_CryptUnprotectData
0x180131e5d  test    eax, eax
0x180131e5f  jnz     loc_180131EF8
0x180131e65  call    cs:__imp_GetLastError
0x180131e6b  mov     ebx, eax
0x180131e6d  test    eax, eax
0x180131e6f  jle     short loc_180131E7A
0x180131e71  movzx   ebx, ax
0x180131e74  or      ebx, 80070000h
0x180131e7a  mov     eax, cs:CallbackContext
0x180131e80  cmp     eax, 2
0x180131e83  jbe     loc_180131FE0
0x180131e89  lea     rax, aReadencryptedf; "ReadEncryptedFromRegistry"
0x180131e90  mov     [rbp+57h+var_7C], ebx
0x180131e93  mov     [rbp+57h+var_60], rax
0x180131e97  lea     rdx, qword_1802929A0
0x180131e9e  lea     rax, aOnecoreTermsrv_50; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180131ea5  mov     [rbp+57h+var_80], 22Ch
0x180131eac  mov     [rbp+57h+var_68], rax
0x180131eb0  lea     rax, aCryptunprotect_1; "CryptUnprotectData failed! 0x%x"
0x180131eb7  mov     [rbp+57h+var_70], rax
0x180131ebb  lea     rax, [rbp+57h+var_7C]
0x180131ebf  mov     [rsp+0D0h+var_88], rax
0x180131ec4  lea     rax, [rbp+57h+var_60]
0x180131ec8  mov     [rsp+0D0h+var_90], rax
0x180131ecd  lea     rax, [rbp+57h+var_80]
0x180131ed1  mov     [rsp+0D0h+var_98], rax
0x180131ed6  lea     rax, [rbp+57h+var_68]
0x180131eda  mov     [rsp+0D0h+pDataOut], rax
0x180131edf  lea     rax, [rbp+57h+var_78]
0x180131ee3  mov     [rsp+0D0h+lpcbData], rax
0x180131ee8  lea     rax, [rbp+57h+var_70]
0x180131eec  mov     dword ptr [rbp+57h+var_78], 80004005h
0x180131ef3  jmp     loc_180131C20
0x180131ef8  mov     ecx, [rbp+57h+var_38.cbData]; Size
0x180131efb  mov     [rbx], ecx
0x180131efd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180131f02  mov     [rsi], rax
0x180131f05  test    rax, rax
0x180131f08  jnz     short loc_180131F44
0x180131f0a  mov     rax, cs:WPP_GLOBAL_Control
0x180131f11  lea     rcx, WPP_GLOBAL_Control
0x180131f18  cmp     rax, rcx
0x180131f1b  jz      loc_180131D62
0x180131f21  test    byte ptr [rax+1Ch], 8
0x180131f25  jz      loc_180131D62
0x180131f2b  cmp     byte ptr [rax+19h], 2
0x180131f2f  jb      loc_180131D62
0x180131f35  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180131f3a  mov     edx, 0Fh
0x180131f3f  jmp     loc_180131D3C
0x180131f44  mov     r8d, [rbp+57h+var_38.cbData]; Size
0x180131f48  mov     rcx, rax; void *
0x180131f4b  mov     rdx, [rbp+57h+var_38.pbData]; Src
0x180131f4f  call    memcpy_0
0x180131f54  xor     ebx, ebx
0x180131f56  jmp     loc_180131FE0
0x180131f5b  mov     eax, cs:CallbackContext
0x180131f61  mov     ebx, 800700E8h
0x180131f66  cmp     eax, 2
0x180131f69  jbe     short loc_180131FE0
0x180131f6b  lea     rax, aReadencryptedf; "ReadEncryptedFromRegistry"
0x180131f72  mov     [rbp+57h+var_60], rdi
0x180131f76  mov     [rbp+57h+var_68], rax
0x180131f7a  lea     rdx, qword_180292BF0
0x180131f81  lea     rax, aOnecoreTermsrv_50; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180131f88  mov     [rbp+57h+var_7C], 207h
0x180131f8f  mov     [rbp+57h+var_70], rax
0x180131f93  lea     rax, aNoBinaryDataAv; "No binary data available in %s registry"...
0x180131f9a  mov     [rbp+57h+var_78], rax
0x180131f9e  lea     rax, [rbp+57h+var_60]
0x180131fa2  mov     [rsp+0D0h+var_88], rax
0x180131fa7  lea     rax, [rbp+57h+var_68]
0x180131fab  mov     [rsp+0D0h+var_90], rax
0x180131fb0  lea     rax, [rbp+57h+var_7C]
0x180131fb4  mov     [rsp+0D0h+var_98], rax
0x180131fb9  lea     rax, [rbp+57h+var_70]
0x180131fbd  mov     [rsp+0D0h+pDataOut], rax
0x180131fc2  lea     rax, [rbp+57h+var_80]
0x180131fc6  mov     [rsp+0D0h+lpcbData], rax
0x180131fcb  lea     rax, [rbp+57h+var_78]
0x180131fcf  mov     [rsp+0D0h+phkResult], rax
0x180131fd4  mov     [rbp+57h+var_80], 80004005h
0x180131fdb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180131fe0  mov     rcx, [rbp+57h+hKey]; hKey
0x180131fe4  test    rcx, rcx
0x180131fe7  jz      short loc_180131FEF
0x180131fe9  call    cs:__imp_RegCloseKey
0x180131fef  mov     rcx, [rbp+57h+lpData+8]; Block
0x180131ff3  test    rcx, rcx
0x180131ff6  jz      short loc_180131FFD
0x180131ff8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180131ffd  mov     rcx, [rbp+57h+var_38.pbData]; hMem
0x180132001  test    rcx, rcx
0x180132004  jz      short loc_18013200C
0x180132006  call    cs:__imp_LocalFree
0x18013200c  mov     eax, ebx
0x18013200e  add     rsp, 0B8h
0x180132015  pop     rdi
0x180132016  pop     rsi
0x180132017  pop     rbx
0x180132018  pop     rbp
0x180132019  retn
```
