# FlightSettingsAPICommon::ReadFileIntoString(void *,ushort * *)

- ea: `0x18008b214`
- end: `0x18008b354`
- name: `?ReadFileIntoString@FlightSettingsAPICommon@@SAJPEAXPEAPEAG@Z`
- size: `320`
- prototype: `__int64 __fastcall(void *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800a9cd0`

## callees

- `0x18000cc6c`
- `0x18000cc8c`
- `0x1800254ac`
- `0x180085564`
- `0x18008b06c`
- `0x18008b214`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18008b2f6`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18008b2f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008b292`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008b33f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008b292`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008b33f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008b2a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008b2a7`

## string_xrefs

- `0x18008b26f`: `onecore\base\flighting\flightsettings\broker\lib\flightsettingsapicommon.cpp`
- `0x18008b2c5`: `onecore\base\flighting\flightsettings\broker\lib\flightsettingsapicommon.cpp`
- `0x18008b304`: `onecore\base\flighting\flightsettings\broker\lib\flightsettingsapicommon.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FlightSettingsAPICommon::ReadFileIntoString(void *a1, unsigned __int16 **a2)
{
  int LastError; // ebx
  void *v4; // rcx
  int cchWideChar; // edi
  WCHAR *v7; // rax
  unsigned __int16 *v8; // rbx
  const char *v9; // r9
  void *v10; // rcx
  int lpWideCharStr; // [rsp+20h] [rbp-30h]
  LPVOID *p_pv; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int8 *v13; // [rsp+38h] [rbp-18h] BYREF
  char v14; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  WCHAR *v16; // [rsp+80h] [rbp+30h] BYREF
  LPVOID pv; // [rsp+88h] [rbp+38h] BYREF

  pv = 0;
  LODWORD(v16) = 0;
  p_pv = &pv;
  v13 = 0;
  v14 = 1;
  LastError = FlightSettingsAPICommon::ReadFileIntoByteArray(a1, &v13, (unsigned int *)&v16, 1);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( LastError < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B8,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\flightsettingsapicommon.cpp",
      (const char *)(unsigned int)LastError,
      lpWideCharStr);
LABEL_3:
    v4 = pv;
    pv = 0;
    if ( v4 )
      CoTaskMemFree(v4);
    return (unsigned int)LastError;
  }
  cchWideChar = (int)v16;
  v7 = (WCHAR *)CoTaskMemAlloc(2LL * (unsigned int)v16);
  v8 = v7;
  v16 = v7;
  if ( !v7 )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2BC,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\flightsettingsapicommon.cpp",
      (const char *)0x8007000ELL,
      lpWideCharStr);
LABEL_8:
    CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v16);
    goto LABEL_3;
  }
  if ( !MultiByteToWideChar(0, 0, (LPCCH)pv, -1, v7, cchWideChar) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x2BD,
                  (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\flightsettingsapicommon.cpp",
                  v9);
    goto LABEL_8;
  }
  v16 = 0;
  *a2 = v8;
  CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v16);
  v10 = pv;
  pv = 0;
  if ( v10 )
    CoTaskMemFree(v10);
  return 0;
}

```

## disassembly

```asm
0x18008b214  mov     [rsp-18h+arg_0], rbx
0x18008b219  push    rbp
0x18008b21a  push    rsi
0x18008b21b  push    rdi
0x18008b21c  mov     rbp, rsp
0x18008b21f  sub     rsp, 50h
0x18008b223  mov     rsi, rdx
0x18008b226  mov     [rbp+pv], 0
0x18008b22e  mov     dword ptr [rbp+arg_10], 0
0x18008b235  lea     rax, [rbp+pv]
0x18008b239  mov     [rbp+var_20], rax
0x18008b23d  mov     [rbp+var_18], 0
0x18008b245  mov     [rbp+var_10], 1
0x18008b249  mov     r9b, 1; bool
0x18008b24c  lea     r8, [rbp+arg_10]; unsigned int *
0x18008b250  lea     rdx, [rbp+var_18]; unsigned __int8 **
0x18008b254  call    ?ReadFileIntoByteArray@FlightSettingsAPICommon@@CAJPEAXPEAPEAEPEAK_N@Z; FlightSettingsAPICommon::ReadFileIntoByteArray(void *,uchar * *,ulong *,bool)
0x18008b259  mov     ebx, eax
0x18008b25b  lea     rcx, [rbp+var_20]
0x18008b25f  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18008b264  test    ebx, ebx
0x18008b266  jns     short loc_18008B29F
0x18008b268  mov     rcx, [rbp+18h]; this
0x18008b26c  mov     r9d, ebx; char *
0x18008b26f  lea     r8, aOnecoreBaseFli_104; "onecore\\base\\flighting\\flightsetting"...
0x18008b276  mov     edx, 2B8h; void *
0x18008b27b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008b280  nop
0x18008b281  mov     rcx, [rbp+pv]; pv
0x18008b285  mov     [rbp+pv], 0
0x18008b28d  test    rcx, rcx
0x18008b290  jz      short loc_18008B298
0x18008b292  call    cs:__imp_CoTaskMemFree
0x18008b298  mov     eax, ebx
0x18008b29a  jmp     loc_18008B347
0x18008b29f  mov     edi, dword ptr [rbp+arg_10]
0x18008b2a2  mov     ecx, edi
0x18008b2a4  add     rcx, rcx; cb
0x18008b2a7  call    cs:__imp_CoTaskMemAlloc
0x18008b2ad  mov     rbx, rax
0x18008b2b0  mov     [rbp+arg_10], rax
0x18008b2b4  test    rax, rax
0x18008b2b7  jnz     short loc_18008B2E1
0x18008b2b9  mov     rcx, [rbp+18h]; this
0x18008b2bd  mov     ebx, 8007000Eh
0x18008b2c2  mov     r9d, ebx; char *
0x18008b2c5  lea     r8, aOnecoreBaseFli_104; "onecore\\base\\flighting\\flightsetting"...
0x18008b2cc  mov     edx, 2BCh; void *
0x18008b2d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008b2d6  lea     rcx, [rbp+arg_10]
0x18008b2da  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x18008b2df  jmp     short loc_18008B281
0x18008b2e1  mov     [rsp+50h+cchWideChar], edi; cchWideChar
0x18008b2e5  mov     [rsp+50h+lpWideCharStr], rbx; lpWideCharStr
0x18008b2ea  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18008b2ee  mov     r8, [rbp+pv]; lpMultiByteStr
0x18008b2f2  xor     edx, edx; dwFlags
0x18008b2f4  xor     ecx, ecx; CodePage
0x18008b2f6  call    cs:__imp_MultiByteToWideChar
0x18008b2fc  test    eax, eax
0x18008b2fe  jnz     short loc_18008B319
0x18008b300  mov     rcx, [rbp+18h]; this
0x18008b304  lea     r8, aOnecoreBaseFli_104; "onecore\\base\\flighting\\flightsetting"...
0x18008b30b  mov     edx, 2BDh; void *
0x18008b310  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008b315  mov     ebx, eax
0x18008b317  jmp     short loc_18008B2D6
0x18008b319  mov     [rbp+arg_10], 0
0x18008b321  mov     [rsi], rbx
0x18008b324  lea     rcx, [rbp+arg_10]
0x18008b328  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x18008b32d  nop
0x18008b32e  mov     rcx, [rbp+pv]; pv
0x18008b332  mov     [rbp+pv], 0
0x18008b33a  test    rcx, rcx
0x18008b33d  jz      short loc_18008B345
0x18008b33f  call    cs:__imp_CoTaskMemFree
0x18008b345  xor     eax, eax
0x18008b347  mov     rbx, [rsp+50h+arg_0]
0x18008b34c  add     rsp, 50h
0x18008b350  pop     rdi
0x18008b351  pop     rsi
0x18008b352  pop     rbp
0x18008b353  retn
```
