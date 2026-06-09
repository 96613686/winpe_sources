# RDPWDUMXServerCertificateManager::WriteEncryptedToRegistry(ushort const *,uchar *,ulong)

- ea: `0x180132108`
- end: `0x1801323e8`
- name: `?WriteEncryptedToRegistry@RDPWDUMXServerCertificateManager@@CAJPEBGPEAEK@Z`
- size: `736`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180132020`

## callees

- `0x180002170`
- `0x180005e08`
- `0x180132108`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180132174`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180132174`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801323c6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801323c6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180132308`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180132308`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180132250`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180132250`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801323d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801323d5`
- `CRYPT32!CryptProtectData` at `0x180132166`
- `CRYPT32!CryptProtectData` at `0x180132166`

## string_xrefs

- `0x180132198`: `WriteEncryptedToRegistry`
- `0x180132280`: `WriteEncryptedToRegistry`
- `0x180132338`: `WriteEncryptedToRegistry`
- `0x1801322a7`: `RegCreateKeyEx failed! %d`
- `0x18013235c`: `RegSetValueEx (%s) failed! %d`

## pseudocode

```c
__int64 __fastcall RDPWDUMXServerCertificateManager::WriteEncryptedToRegistry(
        LPCWSTR lpValueName,
        unsigned __int8 *a2,
        DWORD a3)
{
  signed int LastError; // eax
  LSTATUS v5; // ecx
  int v6; // r8d
  int v7; // r9d
  unsigned int v8; // ebx
  char *v9; // rdx
  const char **v10; // rax
  LSTATUS v11; // eax
  LSTATUS v12; // eax
  int v13; // r8d
  int v14; // r9d
  const char **lpdwDisposition; // [rsp+40h] [rbp-29h]
  DWORD dwDisposition; // [rsp+60h] [rbp-9h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-1h] BYREF
  const char *v19; // [rsp+70h] [rbp+7h] BYREF
  const char *v20; // [rsp+78h] [rbp+Fh] BYREF
  const char *v21; // [rsp+80h] [rbp+17h] BYREF
  const char *v22; // [rsp+88h] [rbp+1Fh] BYREF
  DATA_BLOB pDataOut; // [rsp+90h] [rbp+27h] BYREF
  DATA_BLOB pDataIn; // [rsp+A0h] [rbp+37h] BYREF
  int v25; // [rsp+D8h] [rbp+6Fh] BYREF
  unsigned int v26; // [rsp+E0h] [rbp+77h] BYREF
  int v27; // [rsp+E8h] [rbp+7Fh] BYREF

  pDataIn.pbData = a2;
  pDataIn.cbData = a3;
  hKey = 0;
  dwDisposition = 0;
  *(&pDataIn.cbData + 1) = 0;
  pDataOut = 0;
  if ( CryptProtectData(&pDataIn, 0, 0, 0, 0, 1u, &pDataOut) )
  {
    v11 = RegCreateKeyExW(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\RDPEncoder\\",
            0,
            0,
            0,
            2u,
            0,
            &hKey,
            &dwDisposition);
    v5 = v11;
    if ( v11 )
    {
      if ( v11 > 0 )
        v8 = (unsigned __int16)v11 | 0x80070000;
      else
        v8 = v11;
      if ( (unsigned int)CallbackContext > 2 )
      {
        v26 = v11;
        v21 = "WriteEncryptedToRegistry";
        v9 = byte_180292BA5;
        v25 = 433;
        v20 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumxsec.cpp";
        v19 = "RegCreateKeyEx failed! %d";
        lpdwDisposition = &v21;
        v10 = &v19;
        goto LABEL_6;
      }
    }
    else
    {
      v12 = RegSetValueExW(hKey, lpValueName, 0, 3u, pDataOut.pbData, pDataOut.cbData);
      if ( v12 )
      {
        if ( v12 > 0 )
          v8 = (unsigned __int16)v12 | 0x80070000;
        else
          v8 = v12;
        if ( (unsigned int)CallbackContext > 2 )
        {
          v26 = v12;
          v20 = "WriteEncryptedToRegistry";
          v21 = (const char *)lpValueName;
          v19 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumxsec.cpp";
          v22 = "RegSetValueEx (%s) failed! %d";
          v25 = 447;
          v27 = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            v12,
            (unsigned int)&word_180292A2E,
            v13,
            v14,
            (__int64)&v22,
            (__int64)&v27,
            (__int64)&v19,
            (__int64)&v25,
            (__int64)&v20,
            (__int64)&v21,
            (__int64)&v26);
        }
      }
      else
      {
        v8 = 0;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v26 = v8;
      v19 = "WriteEncryptedToRegistry";
      v9 = &byte_180292B17;
      v25 = 410;
      v20 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumxsec.cpp";
      v21 = "CryptProtectData failed! 0x%x";
      lpdwDisposition = &v19;
      v10 = &v21;
LABEL_6:
      v27 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v5,
        (_DWORD)v9,
        v6,
        v7,
        (__int64)v10,
        (__int64)&v27,
        (__int64)&v20,
        (__int64)&v25,
        (__int64)lpdwDisposition,
        (__int64)&v26);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( pDataOut.pbData )
    LocalFree(pDataOut.pbData);
  return v8;
}

```

## disassembly

```asm
0x180132108  push    rbp
0x18013210a  push    rbx
0x18013210b  push    rdi
0x18013210c  lea     rbp, [rsp-47h]
0x180132111  sub     rsp, 0B0h
0x180132118  lea     rax, [rbp+57h+var_30]
0x18013211c  mov     [rbp+57h+pDataIn.pbData], rdx
0x180132120  mov     [rsp+0C0h+pDataOut], rax; pDataOut
0x180132125  mov     rdi, rcx
0x180132128  xorps   xmm0, xmm0
0x18013212b  mov     [rbp+57h+pDataIn.cbData], r8d
0x18013212f  mov     [rsp+0C0h+dwFlags], 1; dwFlags
0x180132137  lea     rcx, [rbp+57h+pDataIn]; pDataIn
0x18013213b  xor     r9d, r9d; pvReserved
0x18013213e  mov     [rsp+0C0h+pPromptStruct], 0; pPromptStruct
0x180132147  xor     r8d, r8d; pOptionalEntropy
0x18013214a  mov     [rbp+57h+hKey], 0
0x180132152  xor     edx, edx; szDataDescr
0x180132154  mov     [rbp+57h+dwDisposition], 0
0x18013215b  mov     dword ptr [rbp+57h+pDataIn+4], 0
0x180132162  movups  xmmword ptr [rbp+57h+var_30.cbData], xmm0
0x180132166  call    cs:__imp_CryptProtectData
0x18013216c  test    eax, eax
0x18013216e  jnz     loc_180132211
0x180132174  call    cs:__imp_GetLastError
0x18013217a  mov     ebx, eax
0x18013217c  test    eax, eax
0x18013217e  jle     short loc_180132189
0x180132180  movzx   ebx, ax
0x180132183  or      ebx, 80070000h
0x180132189  mov     eax, cs:CallbackContext
0x18013218f  cmp     eax, 2
0x180132192  jbe     loc_1801323BD
0x180132198  lea     rax, aWriteencrypted_0; "WriteEncryptedToRegistry"
0x18013219f  mov     [rbp+57h+arg_10], ebx
0x1801321a2  mov     [rbp+57h+var_50], rax
0x1801321a6  lea     rdx, byte_180292B17
0x1801321ad  lea     rax, aOnecoreTermsrv_50; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1801321b4  mov     [rbp+57h+arg_8], 19Ah
0x1801321bb  mov     [rbp+57h+var_48], rax
0x1801321bf  lea     rax, aCryptprotectda_0; "CryptProtectData failed! 0x%x"
0x1801321c6  mov     [rbp+57h+var_40], rax
0x1801321ca  lea     rax, [rbp+57h+arg_10]
0x1801321ce  mov     [rsp+0C0h+var_78], rax
0x1801321d3  lea     rax, [rbp+57h+var_50]
0x1801321d7  mov     [rsp+0C0h+lpdwDisposition], rax
0x1801321dc  lea     rax, [rbp+57h+arg_8]
0x1801321e0  mov     [rsp+0C0h+phkResult], rax
0x1801321e5  lea     rax, [rbp+57h+var_48]
0x1801321e9  mov     [rsp+0C0h+pDataOut], rax
0x1801321ee  lea     rax, [rbp+57h+arg_18]
0x1801321f2  mov     qword ptr [rsp+0C0h+dwFlags], rax
0x1801321f7  lea     rax, [rbp+57h+var_40]
0x1801321fb  mov     [rsp+0C0h+pPromptStruct], rax
0x180132200  mov     [rbp+57h+arg_18], 80004005h
0x180132207  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18013220c  jmp     loc_1801323BD
0x180132211  lea     rax, [rbp+57h+dwDisposition]
0x180132215  xor     r9d, r9d; lpClass
0x180132218  mov     [rsp+0C0h+lpdwDisposition], rax; lpdwDisposition
0x18013221d  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\RDPEncoder\\"
0x180132224  lea     rax, [rbp+57h+hKey]
0x180132228  xor     r8d, r8d; Reserved
0x18013222b  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180132230  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180132237  mov     [rsp+0C0h+pDataOut], 0; lpSecurityAttributes
0x180132240  mov     [rsp+0C0h+dwFlags], 2; samDesired
0x180132248  mov     dword ptr [rsp+0C0h+pPromptStruct], 0; dwOptions
0x180132250  call    cs:__imp_RegCreateKeyExW
0x180132256  mov     ecx, eax
0x180132258  test    eax, eax
0x18013225a  jz      loc_1801322E8
0x180132260  test    eax, eax
0x180132262  jg      short loc_180132268
0x180132264  mov     ebx, eax
0x180132266  jmp     short loc_180132271
0x180132268  movzx   ebx, cx
0x18013226b  or      ebx, 80070000h
0x180132271  mov     eax, cs:CallbackContext
0x180132277  cmp     eax, 2
0x18013227a  jbe     loc_1801323BD
0x180132280  lea     rax, aWriteencrypted_0; "WriteEncryptedToRegistry"
0x180132287  mov     [rbp+57h+arg_10], ecx
0x18013228a  mov     [rbp+57h+var_40], rax
0x18013228e  lea     rdx, byte_180292BA5
0x180132295  lea     rax, aOnecoreTermsrv_50; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18013229c  mov     [rbp+57h+arg_8], 1B1h
0x1801322a3  mov     [rbp+57h+var_48], rax
0x1801322a7  lea     rax, aRegcreatekeyex; "RegCreateKeyEx failed! %d"
0x1801322ae  mov     [rbp+57h+var_50], rax
0x1801322b2  lea     rax, [rbp+57h+arg_10]
0x1801322b6  mov     [rsp+0C0h+var_78], rax
0x1801322bb  lea     rax, [rbp+57h+var_40]
0x1801322bf  mov     [rsp+0C0h+lpdwDisposition], rax
0x1801322c4  lea     rax, [rbp+57h+arg_8]
0x1801322c8  mov     [rsp+0C0h+phkResult], rax
0x1801322cd  lea     rax, [rbp+57h+var_48]
0x1801322d1  mov     [rsp+0C0h+pDataOut], rax
0x1801322d6  lea     rax, [rbp+57h+arg_18]
0x1801322da  mov     qword ptr [rsp+0C0h+dwFlags], rax
0x1801322df  lea     rax, [rbp+57h+var_50]
0x1801322e3  jmp     loc_1801321FB
0x1801322e8  mov     eax, [rbp+57h+var_30.cbData]
0x1801322eb  mov     r9d, 3; dwType
0x1801322f1  mov     rcx, [rbp+57h+hKey]; hKey
0x1801322f5  xor     r8d, r8d; Reserved
0x1801322f8  mov     [rsp+0C0h+dwFlags], eax; cbData
0x1801322fc  mov     rdx, rdi; lpValueName
0x1801322ff  mov     rax, [rbp+57h+var_30.pbData]
0x180132303  mov     [rsp+0C0h+pPromptStruct], rax; lpData
0x180132308  call    cs:__imp_RegSetValueExW
0x18013230e  mov     ecx, eax
0x180132310  test    eax, eax
0x180132312  jz      loc_1801323BB
0x180132318  test    eax, eax
0x18013231a  jg      short loc_180132320
0x18013231c  mov     ebx, eax
0x18013231e  jmp     short loc_180132329
0x180132320  movzx   ebx, cx
0x180132323  or      ebx, 80070000h
0x180132329  mov     eax, cs:CallbackContext
0x18013232f  cmp     eax, 2
0x180132332  jbe     loc_1801323BD
0x180132338  lea     rax, aWriteencrypted_0; "WriteEncryptedToRegistry"
0x18013233f  mov     [rbp+57h+arg_10], ecx
0x180132342  mov     [rbp+57h+var_48], rax
0x180132346  lea     rdx, word_180292A2E
0x18013234d  lea     rax, aOnecoreTermsrv_50; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180132354  mov     [rbp+57h+var_40], rdi
0x180132358  mov     [rbp+57h+var_50], rax
0x18013235c  lea     rax, aRegsetvalueexS; "RegSetValueEx (%s) failed! %d"
0x180132363  mov     [rbp+57h+var_38], rax
0x180132367  lea     rax, [rbp+57h+arg_10]
0x18013236b  mov     [rsp+0C0h+var_70], rax
0x180132370  lea     rax, [rbp+57h+var_40]
0x180132374  mov     [rsp+0C0h+var_78], rax
0x180132379  lea     rax, [rbp+57h+var_48]
0x18013237d  mov     [rsp+0C0h+lpdwDisposition], rax
0x180132382  lea     rax, [rbp+57h+arg_8]
0x180132386  mov     [rsp+0C0h+phkResult], rax
0x18013238b  lea     rax, [rbp+57h+var_50]
0x18013238f  mov     [rsp+0C0h+pDataOut], rax
0x180132394  lea     rax, [rbp+57h+arg_18]
0x180132398  mov     qword ptr [rsp+0C0h+dwFlags], rax
0x18013239d  lea     rax, [rbp+57h+var_38]
0x1801323a1  mov     [rsp+0C0h+pPromptStruct], rax
0x1801323a6  mov     [rbp+57h+arg_8], 1BFh
0x1801323ad  mov     [rbp+57h+arg_18], 80004005h
0x1801323b4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1801323b9  jmp     short loc_1801323BD
0x1801323bb  xor     ebx, ebx
0x1801323bd  mov     rcx, [rbp+57h+hKey]; hKey
0x1801323c1  test    rcx, rcx
0x1801323c4  jz      short loc_1801323CC
0x1801323c6  call    cs:__imp_RegCloseKey
0x1801323cc  mov     rcx, [rbp+57h+var_30.pbData]; hMem
0x1801323d0  test    rcx, rcx
0x1801323d3  jz      short loc_1801323DB
0x1801323d5  call    cs:__imp_LocalFree
0x1801323db  mov     eax, ebx
0x1801323dd  add     rsp, 0B0h
0x1801323e4  pop     rdi
0x1801323e5  pop     rbx
0x1801323e6  pop     rbp
0x1801323e7  retn
```
