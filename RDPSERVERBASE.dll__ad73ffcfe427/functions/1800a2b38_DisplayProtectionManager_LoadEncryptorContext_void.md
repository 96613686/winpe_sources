# DisplayProtectionManager::LoadEncryptorContext(void)

- ea: `0x1800a2b38`
- end: `0x1800a2f63`
- name: `?LoadEncryptorContext@DisplayProtectionManager@@AEAAJXZ`
- size: `1067`
- prototype: `__int64 __fastcall(DisplayProtectionManager *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800a29bc`

## callees

- `0x180001574`
- `0x18000202c`
- `0x18003b118`
- `0x18007e9e0`
- `0x18007f42c`
- `0x18009f060`
- `0x1800a2b38`
- `0x1800a3270`
- `0x18019c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800a2c72`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800a2c72`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a2def`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a2def`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800a2c53`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800a2c53`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800a2b91`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800a2b91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2b9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2da9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2e95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2b9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2da9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2e95`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800a2d8e`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800a2d8e`

## string_xrefs

- `0x1800a2cae`: `StringCchCat of file path failed`
- `0x1800a2c78`: `wcioprotection_display_encryptor.dll`
- `0x1800a2d0b`: `StringCchCopy of file path failed`
- `0x1800a2d65`: `Loading dll`
- `0x1800a2dcd`: `Failed to load WCIO display protection dll`

## pseudocode

```c
__int64 __fastcall DisplayProtectionManager::LoadEncryptorContext(DisplayProtectionManager *this)
{
  signed int LastError; // eax
  int v3; // ecx
  int v4; // r8d
  int v5; // r9d
  unsigned int v6; // ebx
  DWORD ModuleFileNameW; // eax
  wchar_t *v8; // rax
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  char *v12; // rdx
  const char *v13; // rax
  HMODULE LibraryW; // rax
  HMODULE v15; // rcx
  signed int v16; // eax
  const char *v17; // rax
  FARPROC ProcAddress; // rax
  signed int v19; // eax
  int v21; // [rsp+50h] [rbp-B0h] BYREF
  int v22; // [rsp+54h] [rbp-ACh] BYREF
  const char *v23; // [rsp+58h] [rbp-A8h] BYREF
  const char *v24; // [rsp+60h] [rbp-A0h] BYREF
  const char *v25; // [rsp+68h] [rbp-98h] BYREF
  const char *v26; // [rsp+70h] [rbp-90h] BYREF
  HMODULE phModule; // [rsp+78h] [rbp-88h] BYREF
  WCHAR Filename[264]; // [rsp+80h] [rbp-80h] BYREF

  phModule = 0;
  memset_0(Filename, 0, 0x20Au);
  if ( !GetModuleHandleExW(6u, &word_1801B83A0, &phModule) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v21 = 163;
      v25 = "Failed to get module handle to itself.";
      v22 = v6;
      v26 = "LoadEncryptorContext";
      v23 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\displayprotectionmanager.cpp";
      v24 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v3,
        (unsigned int)&word_18027C936,
        v4,
        v5,
        (__int64)&v24,
        (__int64)&v22,
        (__int64)&v23,
        (__int64)&v21,
        (__int64)&v26,
        (__int64)&v25);
    }
    return v6;
  }
  ModuleFileNameW = GetModuleFileNameW(phModule, Filename, 0x105u);
  if ( !ModuleFileNameW || ModuleFileNameW == 261 )
  {
    v19 = GetLastError();
    v6 = v19;
    if ( v19 > 0 )
      v6 = (unsigned __int16)v19 | 0x80070000;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v17 = "Failed to get the module file name";
      v22 = 167;
      v12 = byte_18027C8DB;
      goto LABEL_32;
    }
  }
  else
  {
    v8 = wcsrchr(Filename, 0x5Cu);
    if ( v8 )
    {
      v8[1] = 0;
      v6 = StringCchCatW(Filename, 0x105u, L"wcioprotection_display_encryptor.dll");
      if ( (v6 & 0x80000000) != 0 )
      {
        v9 = (int)CallbackContext;
        if ( (unsigned int)CallbackContext <= 2 )
          return v6;
        v22 = 175;
        v24 = "StringCchCat of file path failed";
        v12 = (char *)&unk_18027C880;
        v23 = "LoadEncryptorContext";
        v26 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\displayprotectionmanager.cpp";
        v13 = "Error HResult failed";
        goto LABEL_33;
      }
    }
    else
    {
      v6 = StringCchCopyW(Filename, 0x105u, L"wcioprotection_display_encryptor.dll");
      if ( (v6 & 0x80000000) != 0 )
      {
        if ( (unsigned int)CallbackContext <= 2 )
          return v6;
        v22 = 180;
        v24 = "StringCchCopy of file path failed";
        v12 = byte_18027C825;
        v23 = "LoadEncryptorContext";
        v26 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\displayprotectionmanager.cpp";
        v13 = "Error HResult failed";
        goto LABEL_33;
      }
    }
    if ( (unsigned int)CallbackContext > 4 )
    {
      v24 = (const char *)Filename;
      v23 = "Loading dll";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v9,
        (unsigned int)byte_18027C7ED,
        v10,
        v11,
        (__int64)&v23,
        (__int64)&v24);
    }
    LibraryW = LoadLibraryW(Filename);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
      (char *)this + 16,
      LibraryW);
    v15 = (HMODULE)*((_QWORD *)this + 2);
    if ( v15 )
    {
      ProcAddress = GetProcAddress(v15, "ClassFactory");
      if ( ProcAddress )
      {
        v6 = ((__int64 (__fastcall *)(GUID *, GUID *, char *))ProcAddress)(
               &CLSID_DRMEncryptorFactory,
               &IID_DRMEncryptorFactory,
               (char *)this + 24);
        if ( (v6 & 0x80000000) == 0 || (unsigned int)CallbackContext <= 2 )
          return v6;
        v22 = 208;
        v24 = "Failed to instantiate WCIO encryptor object";
        v12 = (char *)&dword_18027C6DC;
        v23 = "LoadEncryptorContext";
        v26 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\displayprotectionmanager.cpp";
        v13 = "Error HResult failed";
LABEL_33:
        v25 = v13;
        v21 = v6;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v9,
          (_DWORD)v12,
          v10,
          v11,
          (__int64)&v25,
          (__int64)&v21,
          (__int64)&v26,
          (__int64)&v22,
          (__int64)&v23,
          (__int64)&v24);
        return v6;
      }
      v6 = -2147467262;
      if ( (unsigned int)CallbackContext <= 2 )
        return v6;
      v17 = "Failed to load address of WCIO encryptor ClassFactory";
      v22 = 201;
      v12 = &byte_18027C737;
LABEL_32:
      v24 = v17;
      v23 = "LoadEncryptorContext";
      v26 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\displayprotectionmanager.cpp";
      v13 = "Error condition failed";
      goto LABEL_33;
    }
    v16 = GetLastError();
    v6 = v16;
    if ( v16 > 0 )
      v6 = (unsigned __int16)v16 | 0x80070000;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v17 = "Failed to load WCIO display protection dll";
      v22 = 191;
      v12 = (char *)word_18027C792;
      goto LABEL_32;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x1800a2b38  mov     [rsp-8+arg_8], rbx
0x1800a2b3d  mov     [rsp-8+arg_10], rdi
0x1800a2b42  push    rbp
0x1800a2b43  lea     rbp, [rsp-1A0h]
0x1800a2b4b  sub     rsp, 2A0h
0x1800a2b52  mov     rax, cs:__security_cookie
0x1800a2b59  xor     rax, rsp
0x1800a2b5c  mov     [rbp+1A0h+var_10], rax
0x1800a2b63  mov     rdi, rcx
0x1800a2b66  mov     [rsp+2A0h+phModule], 0
0x1800a2b6f  lea     rcx, [rbp+1A0h+Filename]; void *
0x1800a2b73  xor     edx, edx; Val
0x1800a2b75  mov     r8d, 20Ah; Size
0x1800a2b7b  call    memset_0
0x1800a2b80  lea     r8, [rsp+2A0h+phModule]; phModule
0x1800a2b85  mov     ecx, 6; dwFlags
0x1800a2b8a  lea     rdx, word_1801B83A0; lpModuleName
0x1800a2b91  call    cs:__imp_GetModuleHandleExW
0x1800a2b97  test    eax, eax
0x1800a2b99  jnz     loc_1800A2C42
0x1800a2b9f  call    cs:__imp_GetLastError
0x1800a2ba5  mov     ebx, eax
0x1800a2ba7  test    eax, eax
0x1800a2ba9  jle     short loc_1800A2BB4
0x1800a2bab  movzx   ebx, ax
0x1800a2bae  or      ebx, 80070000h
0x1800a2bb4  mov     eax, cs:CallbackContext
0x1800a2bba  cmp     eax, 2
0x1800a2bbd  jbe     loc_1800A2F3D
0x1800a2bc3  lea     rax, aFailedToGetMod; "Failed to get module handle to itself."
0x1800a2bca  mov     [rsp+2A0h+var_250], 0A3h
0x1800a2bd2  mov     [rsp+2A0h+var_238], rax
0x1800a2bd7  lea     rdx, word_18027C936
0x1800a2bde  lea     rax, aLoadencryptorc; "LoadEncryptorContext"
0x1800a2be5  mov     [rsp+2A0h+var_24C], ebx
0x1800a2be9  mov     [rsp+2A0h+var_230], rax
0x1800a2bee  lea     rax, aOnecoreTermsrv_59; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x1800a2bf5  mov     [rsp+2A0h+var_248], rax
0x1800a2bfa  lea     rax, aErrorCondition; "Error condition failed"
0x1800a2c01  mov     [rsp+2A0h+var_240], rax
0x1800a2c06  lea     rax, [rsp+2A0h+var_238]
0x1800a2c0b  mov     [rsp+2A0h+var_258], rax
0x1800a2c10  lea     rax, [rsp+2A0h+var_230]
0x1800a2c15  mov     [rsp+2A0h+var_260], rax
0x1800a2c1a  lea     rax, [rsp+2A0h+var_250]
0x1800a2c1f  mov     [rsp+2A0h+var_268], rax
0x1800a2c24  lea     rax, [rsp+2A0h+var_248]
0x1800a2c29  mov     [rsp+2A0h+var_270], rax
0x1800a2c2e  lea     rax, [rsp+2A0h+var_24C]
0x1800a2c33  mov     [rsp+2A0h+var_278], rax
0x1800a2c38  lea     rax, [rsp+2A0h+var_240]
0x1800a2c3d  jmp     loc_1800A2F33
0x1800a2c42  mov     rcx, [rsp+2A0h+phModule]; hModule
0x1800a2c47  lea     rdx, [rbp+1A0h+Filename]; lpFilename
0x1800a2c4b  mov     ebx, 105h
0x1800a2c50  mov     r8d, ebx; nSize
0x1800a2c53  call    cs:__imp_GetModuleFileNameW
0x1800a2c59  test    eax, eax
0x1800a2c5b  jz      loc_1800A2E95
0x1800a2c61  cmp     eax, ebx
0x1800a2c63  jz      loc_1800A2E95
0x1800a2c69  mov     edx, 5Ch ; '\'; Ch
0x1800a2c6e  lea     rcx, [rbp+1A0h+Filename]; Str
0x1800a2c72  call    cs:__imp_wcsrchr
0x1800a2c78  lea     r8, aWcioprotection; "wcioprotection_display_encryptor.dll"
0x1800a2c7f  mov     edx, ebx; unsigned __int64
0x1800a2c81  test    rax, rax
0x1800a2c84  jz      short loc_1800A2CED
0x1800a2c86  xor     ecx, ecx
0x1800a2c88  mov     [rax+2], cx
0x1800a2c8c  lea     rcx, [rbp+1A0h+Filename]; unsigned __int16 *
0x1800a2c90  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800a2c95  mov     ebx, eax
0x1800a2c97  test    eax, eax
0x1800a2c99  jns     loc_1800A2D4A
0x1800a2c9f  mov     ecx, cs:CallbackContext
0x1800a2ca5  cmp     ecx, 2
0x1800a2ca8  jbe     loc_1800A2F3D
0x1800a2cae  lea     rax, aStringcchcatOf; "StringCchCat of file path failed"
0x1800a2cb5  mov     [rsp+2A0h+var_24C], 0AFh
0x1800a2cbd  mov     [rsp+2A0h+var_240], rax
0x1800a2cc2  lea     rdx, unk_18027C880
0x1800a2cc9  lea     rax, aLoadencryptorc; "LoadEncryptorContext"
0x1800a2cd0  mov     [rsp+2A0h+var_248], rax
0x1800a2cd5  lea     rax, aOnecoreTermsrv_59; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x1800a2cdc  mov     [rsp+2A0h+var_230], rax
0x1800a2ce1  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800a2ce8  jmp     loc_1800A2EF3
0x1800a2ced  lea     rcx, [rbp+1A0h+Filename]; unsigned __int16 *
0x1800a2cf1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800a2cf6  mov     ebx, eax
0x1800a2cf8  test    eax, eax
0x1800a2cfa  jns     short loc_1800A2D4A
0x1800a2cfc  mov     eax, cs:CallbackContext
0x1800a2d02  cmp     eax, 2
0x1800a2d05  jbe     loc_1800A2F3D
0x1800a2d0b  lea     rax, aStringcchcopyO_2; "StringCchCopy of file path failed"
0x1800a2d12  mov     [rsp+2A0h+var_24C], 0B4h
0x1800a2d1a  mov     [rsp+2A0h+var_240], rax
0x1800a2d1f  lea     rdx, byte_18027C825
0x1800a2d26  lea     rax, aLoadencryptorc; "LoadEncryptorContext"
0x1800a2d2d  mov     [rsp+2A0h+var_248], rax
0x1800a2d32  lea     rax, aOnecoreTermsrv_59; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x1800a2d39  mov     [rsp+2A0h+var_230], rax
0x1800a2d3e  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800a2d45  jmp     loc_1800A2EF3
0x1800a2d4a  mov     eax, cs:CallbackContext
0x1800a2d50  cmp     eax, 4
0x1800a2d53  jbe     short loc_1800A2D8A
0x1800a2d55  lea     rax, [rbp+1A0h+Filename]
0x1800a2d59  mov     [rsp+2A0h+var_240], rax
0x1800a2d5e  lea     rdx, byte_18027C7ED
0x1800a2d65  lea     rax, aLoadingDll; "Loading dll"
0x1800a2d6c  mov     [rsp+2A0h+var_248], rax
0x1800a2d71  lea     rax, [rsp+2A0h+var_240]
0x1800a2d76  mov     [rsp+2A0h+var_278], rax
0x1800a2d7b  lea     rax, [rsp+2A0h+var_248]
0x1800a2d80  mov     [rsp+2A0h+var_280], rax
0x1800a2d85  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800a2d8a  lea     rcx, [rbp+1A0h+Filename]; lpLibFileName
0x1800a2d8e  call    cs:__imp_LoadLibraryW
0x1800a2d94  mov     rdx, rax
0x1800a2d97  lea     rcx, [rdi+10h]
0x1800a2d9b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x1800a2da0  mov     rcx, [rdi+10h]; hModule
0x1800a2da4  test    rcx, rcx
0x1800a2da7  jnz     short loc_1800A2DE8
0x1800a2da9  call    cs:__imp_GetLastError
0x1800a2daf  mov     ebx, eax
0x1800a2db1  test    eax, eax
0x1800a2db3  jle     short loc_1800A2DBE
0x1800a2db5  movzx   ebx, ax
0x1800a2db8  or      ebx, 80070000h
0x1800a2dbe  mov     eax, cs:CallbackContext
0x1800a2dc4  cmp     eax, 2
0x1800a2dc7  jbe     loc_1800A2F3D
0x1800a2dcd  lea     rax, aFailedToLoadWc; "Failed to load WCIO display protection "...
0x1800a2dd4  mov     [rsp+2A0h+var_24C], 0BFh
0x1800a2ddc  lea     rdx, word_18027C792
0x1800a2de3  jmp     loc_1800A2ECF
0x1800a2de8  lea     rdx, aClassfactory; "ClassFactory"
0x1800a2def  call    cs:__imp_GetProcAddress
0x1800a2df5  test    rax, rax
0x1800a2df8  jnz     short loc_1800A2E29
0x1800a2dfa  mov     eax, cs:CallbackContext
0x1800a2e00  mov     ebx, 80004002h
0x1800a2e05  cmp     eax, 2
0x1800a2e08  jbe     loc_1800A2F3D
0x1800a2e0e  lea     rax, aFailedToLoadAd; "Failed to load address of WCIO encrypto"...
0x1800a2e15  mov     [rsp+2A0h+var_24C], 0C9h
0x1800a2e1d  lea     rdx, byte_18027C737
0x1800a2e24  jmp     loc_1800A2ECF
0x1800a2e29  lea     r8, [rdi+18h]
0x1800a2e2d  lea     rdx, IID_DRMEncryptorFactory
0x1800a2e34  lea     rcx, CLSID_DRMEncryptorFactory
0x1800a2e3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2e40  mov     ebx, eax
0x1800a2e42  test    eax, eax
0x1800a2e44  jns     loc_1800A2F3D
0x1800a2e4a  mov     eax, cs:CallbackContext
0x1800a2e50  cmp     eax, 2
0x1800a2e53  jbe     loc_1800A2F3D
0x1800a2e59  lea     rax, aFailedToInstan; "Failed to instantiate WCIO encryptor ob"...
0x1800a2e60  mov     [rsp+2A0h+var_24C], 0D0h
0x1800a2e68  mov     [rsp+2A0h+var_240], rax
0x1800a2e6d  lea     rdx, dword_18027C6DC
0x1800a2e74  lea     rax, aLoadencryptorc; "LoadEncryptorContext"
0x1800a2e7b  mov     [rsp+2A0h+var_248], rax
0x1800a2e80  lea     rax, aOnecoreTermsrv_59; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x1800a2e87  mov     [rsp+2A0h+var_230], rax
0x1800a2e8c  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800a2e93  jmp     short loc_1800A2EF3
0x1800a2e95  call    cs:__imp_GetLastError
0x1800a2e9b  mov     ebx, eax
0x1800a2e9d  test    eax, eax
0x1800a2e9f  jle     short loc_1800A2EAA
0x1800a2ea1  movzx   ebx, ax
0x1800a2ea4  or      ebx, 80070000h
0x1800a2eaa  mov     eax, cs:CallbackContext
0x1800a2eb0  cmp     eax, 2
0x1800a2eb3  jbe     loc_1800A2F3D
0x1800a2eb9  lea     rax, aFailedToGetThe_1; "Failed to get the module file name"
0x1800a2ec0  mov     [rsp+2A0h+var_24C], 0A7h
0x1800a2ec8  lea     rdx, byte_18027C8DB
0x1800a2ecf  mov     [rsp+2A0h+var_240], rax
0x1800a2ed4  lea     rax, aLoadencryptorc; "LoadEncryptorContext"
0x1800a2edb  mov     [rsp+2A0h+var_248], rax
0x1800a2ee0  lea     rax, aOnecoreTermsrv_59; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x1800a2ee7  mov     [rsp+2A0h+var_230], rax
0x1800a2eec  lea     rax, aErrorCondition; "Error condition failed"
0x1800a2ef3  mov     [rsp+2A0h+var_238], rax
0x1800a2ef8  lea     rax, [rsp+2A0h+var_240]
0x1800a2efd  mov     [rsp+2A0h+var_258], rax
0x1800a2f02  lea     rax, [rsp+2A0h+var_248]
0x1800a2f07  mov     [rsp+2A0h+var_260], rax
0x1800a2f0c  lea     rax, [rsp+2A0h+var_24C]
0x1800a2f11  mov     [rsp+2A0h+var_268], rax
0x1800a2f16  lea     rax, [rsp+2A0h+var_230]
0x1800a2f1b  mov     [rsp+2A0h+var_270], rax
0x1800a2f20  lea     rax, [rsp+2A0h+var_250]
0x1800a2f25  mov     [rsp+2A0h+var_278], rax
0x1800a2f2a  lea     rax, [rsp+2A0h+var_238]
0x1800a2f2f  mov     [rsp+2A0h+var_250], ebx
0x1800a2f33  mov     [rsp+2A0h+var_280], rax
0x1800a2f38  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800a2f3d  mov     eax, ebx
0x1800a2f3f  mov     rcx, [rbp+1A0h+var_10]
0x1800a2f46  xor     rcx, rsp; StackCookie
0x1800a2f49  call    __security_check_cookie
0x1800a2f4e  lea     r11, [rsp+2A0h+var_s0]
0x1800a2f56  mov     rbx, [r11+18h]
0x1800a2f5a  mov     rdi, [r11+20h]
0x1800a2f5e  mov     rsp, r11
0x1800a2f61  pop     rbp
0x1800a2f62  retn
```
