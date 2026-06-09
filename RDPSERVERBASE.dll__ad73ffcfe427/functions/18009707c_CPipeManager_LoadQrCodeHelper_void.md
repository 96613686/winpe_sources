# CPipeManager::LoadQrCodeHelper(void)

- ea: `0x18009707c`
- end: `0x180097382`
- name: `?LoadQrCodeHelper@CPipeManager@@IEAAJXZ`
- size: `774`
- prototype: `__int64 __fastcall(CPipeManager *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18009a8e8`

## callees

- `0x180001574`
- `0x18000202c`
- `0x18007e9e0`
- `0x18007f42c`
- `0x18009707c`
- `0x18009f060`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800971fc`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800971fc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800970f2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800970f2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800970d5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800970d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097105`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800971b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800972ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097105`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800971b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800972ac`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180097296`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180097296`

## string_xrefs

- `0x18009720d`: `RdpQrCodeHelper.dll`
- `0x180097237`: `StringCchCat of file path failed`
- `0x18009726d`: `Loading dll for qrcode: `
- `0x1800972d8`: `Failed to load RDP QrCode helper dll`

## pseudocode

```c
__int64 __fastcall CPipeManager::LoadQrCodeHelper(CPipeManager *this)
{
  signed int LastError; // eax
  int v3; // ecx
  int v4; // r8d
  int v5; // r9d
  signed int v6; // ebx
  signed int v7; // eax
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  const char *v11; // rax
  __int16 *v12; // rdx
  wchar_t *v13; // rax
  int v14; // ecx
  HMODULE LibraryW; // rax
  signed int v16; // eax
  int v18; // [rsp+50h] [rbp-B0h] BYREF
  int v19; // [rsp+54h] [rbp-ACh] BYREF
  const char *v20; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR *v21; // [rsp+60h] [rbp-A0h] BYREF
  const char *v22; // [rsp+68h] [rbp-98h] BYREF
  const char *v23; // [rsp+70h] [rbp-90h] BYREF
  HMODULE phModule; // [rsp+78h] [rbp-88h] BYREF
  WCHAR Filename[264]; // [rsp+80h] [rbp-80h] BYREF

  phModule = 0;
  memset_0(Filename, 0, 0x20Au);
  if ( GetModuleHandleExW(6u, (LPCWSTR)&CPipeManager::GetPipeManagerStateName, &phModule) )
  {
    if ( GetModuleFileNameW(phModule, Filename, 0x105u) - 1 > 0x103 )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( v6 < 0 )
      {
        if ( (unsigned int)CallbackContext > 2 )
        {
          v18 = 394;
          v22 = "Failed to get the module file name";
          v19 = v6;
          v23 = "LoadQrCodeHelper";
          v20 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
          v21 = (WCHAR *)"Error HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v3,
            (unsigned int)&word_18027C59E,
            v4,
            v5,
            (__int64)&v21,
            (__int64)&v19,
            (__int64)&v20,
            (__int64)&v18,
            (__int64)&v23,
            (__int64)&v22);
        }
        return (unsigned int)v6;
      }
    }
  }
  else
  {
    v7 = GetLastError();
    v6 = v7;
    if ( v7 > 0 )
      v6 = (unsigned __int16)v7 | 0x80070000;
    if ( v6 < 0 )
    {
      if ( (unsigned int)CallbackContext <= 2 )
        return (unsigned int)v6;
      v11 = "Failed to get module handle to itself";
      v19 = 400;
      v12 = (__int16 *)qword_18027C550;
LABEL_26:
      v21 = (WCHAR *)v11;
      v20 = "LoadQrCodeHelper";
      v23 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      v22 = "Error HResult failed";
      v18 = v6;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v8,
        (_DWORD)v12,
        v9,
        v10,
        (__int64)&v22,
        (__int64)&v18,
        (__int64)&v23,
        (__int64)&v19,
        (__int64)&v20,
        (__int64)&v21);
      return (unsigned int)v6;
    }
  }
  v13 = wcsrchr(Filename, 0x5Cu);
  if ( v13 )
    v13[1] = 0;
  v6 = StringCchCatW(Filename, 0x105u, L"RdpQrCodeHelper.dll");
  if ( v6 < 0 )
  {
    v8 = (int)CallbackContext;
    if ( (unsigned int)CallbackContext <= 2 )
      return (unsigned int)v6;
    v11 = "StringCchCat of file path failed";
    v19 = 411;
    v12 = word_18027C502;
    goto LABEL_26;
  }
  if ( (unsigned int)CallbackContext > 4 )
  {
    v21 = Filename;
    v20 = "Loading dll for qrcode: ";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
      v14,
      (unsigned int)byte_18027C4D3,
      v9,
      v10,
      (__int64)&v20,
      (__int64)&v21);
  }
  LibraryW = LoadLibraryW(Filename);
  *((_QWORD *)this + 6722) = LibraryW;
  if ( !LibraryW )
  {
    v16 = GetLastError();
    v6 = v16;
    if ( v16 > 0 )
      v6 = (unsigned __int16)v16 | 0x80070000;
    if ( v6 < 0 && (unsigned int)CallbackContext > 2 )
    {
      v11 = "Failed to load RDP QrCode helper dll";
      v19 = 419;
      v12 = (__int16 *)byte_18027C485;
      goto LABEL_26;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18009707c  mov     [rsp-8+arg_8], rbx
0x180097081  mov     [rsp-8+arg_10], rdi
0x180097086  push    rbp
0x180097087  lea     rbp, [rsp-1A0h]
0x18009708f  sub     rsp, 2A0h
0x180097096  mov     rax, cs:__security_cookie
0x18009709d  xor     rax, rsp
0x1800970a0  mov     [rbp+1A0h+var_10], rax
0x1800970a7  mov     rdi, rcx
0x1800970aa  mov     [rsp+2A0h+phModule], 0
0x1800970b3  lea     rcx, [rbp+1A0h+Filename]; void *
0x1800970b7  xor     edx, edx; Val
0x1800970b9  mov     r8d, 20Ah; Size
0x1800970bf  call    memset_0
0x1800970c4  lea     r8, [rsp+2A0h+phModule]; phModule
0x1800970c9  mov     ecx, 6; dwFlags
0x1800970ce  lea     rdx, ?GetPipeManagerStateName@CPipeManager@@CAPEBGW4PipeManagerState@1@@Z; lpModuleName
0x1800970d5  call    cs:__imp_GetModuleHandleExW
0x1800970db  test    eax, eax
0x1800970dd  jz      loc_1800971B0
0x1800970e3  mov     rcx, [rsp+2A0h+phModule]; hModule
0x1800970e8  lea     rdx, [rbp+1A0h+Filename]; lpFilename
0x1800970ec  mov     r8d, 105h; nSize
0x1800970f2  call    cs:__imp_GetModuleFileNameW
0x1800970f8  dec     eax
0x1800970fa  cmp     eax, 103h
0x1800970ff  jbe     loc_1800971F3
0x180097105  call    cs:__imp_GetLastError
0x18009710b  mov     ebx, eax
0x18009710d  test    eax, eax
0x18009710f  jle     short loc_18009711A
0x180097111  movzx   ebx, ax
0x180097114  or      ebx, 80070000h
0x18009711a  test    ebx, ebx
0x18009711c  jns     loc_1800971F3
0x180097122  mov     eax, cs:CallbackContext
0x180097128  cmp     eax, 2
0x18009712b  jbe     loc_18009735C
0x180097131  lea     rax, aFailedToGetThe_1; "Failed to get the module file name"
0x180097138  mov     [rsp+2A0h+var_250], 18Ah
0x180097140  mov     [rsp+2A0h+var_238], rax
0x180097145  lea     rdx, word_18027C59E
0x18009714c  lea     rax, aLoadqrcodehelp; "LoadQrCodeHelper"
0x180097153  mov     [rsp+2A0h+var_24C], ebx
0x180097157  mov     [rsp+2A0h+var_230], rax
0x18009715c  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x180097163  mov     [rsp+2A0h+var_248], rax
0x180097168  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18009716f  mov     [rsp+2A0h+var_240], rax
0x180097174  lea     rax, [rsp+2A0h+var_238]
0x180097179  mov     [rsp+2A0h+var_258], rax
0x18009717e  lea     rax, [rsp+2A0h+var_230]
0x180097183  mov     [rsp+2A0h+var_260], rax
0x180097188  lea     rax, [rsp+2A0h+var_250]
0x18009718d  mov     [rsp+2A0h+var_268], rax
0x180097192  lea     rax, [rsp+2A0h+var_248]
0x180097197  mov     [rsp+2A0h+var_270], rax
0x18009719c  lea     rax, [rsp+2A0h+var_24C]
0x1800971a1  mov     [rsp+2A0h+var_278], rax
0x1800971a6  lea     rax, [rsp+2A0h+var_240]
0x1800971ab  jmp     loc_180097352
0x1800971b0  call    cs:__imp_GetLastError
0x1800971b6  mov     ebx, eax
0x1800971b8  test    eax, eax
0x1800971ba  jle     short loc_1800971C5
0x1800971bc  movzx   ebx, ax
0x1800971bf  or      ebx, 80070000h
0x1800971c5  test    ebx, ebx
0x1800971c7  jns     short loc_1800971F3
0x1800971c9  mov     eax, cs:CallbackContext
0x1800971cf  cmp     eax, 2
0x1800971d2  jbe     loc_18009735C
0x1800971d8  lea     rax, aFailedToGetMod_0; "Failed to get module handle to itself"
0x1800971df  mov     [rsp+2A0h+var_24C], 190h
0x1800971e7  lea     rdx, qword_18027C550
0x1800971ee  jmp     loc_1800972EE
0x1800971f3  mov     edx, 5Ch ; '\'; Ch
0x1800971f8  lea     rcx, [rbp+1A0h+Filename]; Str
0x1800971fc  call    cs:__imp_wcsrchr
0x180097202  test    rax, rax
0x180097205  jz      short loc_18009720D
0x180097207  xor     ecx, ecx
0x180097209  mov     [rax+2], cx
0x18009720d  lea     r8, aRdpqrcodehelpe_0; "RdpQrCodeHelper.dll"
0x180097214  mov     edx, 105h; unsigned __int64
0x180097219  lea     rcx, [rbp+1A0h+Filename]; unsigned __int16 *
0x18009721d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180097222  mov     ebx, eax
0x180097224  test    eax, eax
0x180097226  jns     short loc_180097252
0x180097228  mov     ecx, cs:CallbackContext
0x18009722e  cmp     ecx, 2
0x180097231  jbe     loc_18009735C
0x180097237  lea     rax, aStringcchcatOf; "StringCchCat of file path failed"
0x18009723e  mov     [rsp+2A0h+var_24C], 19Bh
0x180097246  lea     rdx, word_18027C502
0x18009724d  jmp     loc_1800972EE
0x180097252  mov     eax, cs:CallbackContext
0x180097258  cmp     eax, 4
0x18009725b  jbe     short loc_180097292
0x18009725d  lea     rax, [rbp+1A0h+Filename]
0x180097261  mov     [rsp+2A0h+var_240], rax
0x180097266  lea     rdx, byte_18027C4D3
0x18009726d  lea     rax, aLoadingDllForQ; "Loading dll for qrcode: "
0x180097274  mov     [rsp+2A0h+var_248], rax
0x180097279  lea     rax, [rsp+2A0h+var_240]
0x18009727e  mov     [rsp+2A0h+var_278], rax
0x180097283  lea     rax, [rsp+2A0h+var_248]
0x180097288  mov     [rsp+2A0h+var_280], rax
0x18009728d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180097292  lea     rcx, [rbp+1A0h+Filename]; lpLibFileName
0x180097296  call    cs:__imp_LoadLibraryW
0x18009729c  mov     [rdi+0D210h], rax
0x1800972a3  test    rax, rax
0x1800972a6  jnz     loc_18009735C
0x1800972ac  call    cs:__imp_GetLastError
0x1800972b2  mov     ebx, eax
0x1800972b4  test    eax, eax
0x1800972b6  jle     short loc_1800972C1
0x1800972b8  movzx   ebx, ax
0x1800972bb  or      ebx, 80070000h
0x1800972c1  test    ebx, ebx
0x1800972c3  jns     loc_18009735C
0x1800972c9  mov     eax, cs:CallbackContext
0x1800972cf  cmp     eax, 2
0x1800972d2  jbe     loc_18009735C
0x1800972d8  lea     rax, aFailedToLoadRd_0; "Failed to load RDP QrCode helper dll"
0x1800972df  mov     [rsp+2A0h+var_24C], 1A3h
0x1800972e7  lea     rdx, byte_18027C485
0x1800972ee  mov     [rsp+2A0h+var_240], rax
0x1800972f3  lea     rax, aLoadqrcodehelp; "LoadQrCodeHelper"
0x1800972fa  mov     [rsp+2A0h+var_248], rax
0x1800972ff  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x180097306  mov     [rsp+2A0h+var_230], rax
0x18009730b  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180097312  mov     [rsp+2A0h+var_238], rax
0x180097317  lea     rax, [rsp+2A0h+var_240]
0x18009731c  mov     [rsp+2A0h+var_258], rax
0x180097321  lea     rax, [rsp+2A0h+var_248]
0x180097326  mov     [rsp+2A0h+var_260], rax
0x18009732b  lea     rax, [rsp+2A0h+var_24C]
0x180097330  mov     [rsp+2A0h+var_268], rax
0x180097335  lea     rax, [rsp+2A0h+var_230]
0x18009733a  mov     [rsp+2A0h+var_270], rax
0x18009733f  lea     rax, [rsp+2A0h+var_250]
0x180097344  mov     [rsp+2A0h+var_278], rax
0x180097349  lea     rax, [rsp+2A0h+var_238]
0x18009734e  mov     [rsp+2A0h+var_250], ebx
0x180097352  mov     [rsp+2A0h+var_280], rax
0x180097357  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18009735c  mov     eax, ebx
0x18009735e  mov     rcx, [rbp+1A0h+var_10]
0x180097365  xor     rcx, rsp; StackCookie
0x180097368  call    __security_check_cookie
0x18009736d  lea     r11, [rsp+2A0h+var_s0]
0x180097375  mov     rbx, [r11+18h]
0x180097379  mov     rdi, [r11+20h]
0x18009737d  mov     rsp, r11
0x180097380  pop     rbp
0x180097381  retn
```
