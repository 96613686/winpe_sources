# CFlightData::ConvertStringToLower(ushort const *,HSTRING__ * *)

- ea: `0x18001d2bc`
- end: `0x18001d3eb`
- name: `?ConvertStringToLower@CFlightData@@AEAAJPEBGPEAPEAUHSTRING__@@@Z`
- size: `303`
- prototype: `__int64 __fastcall(CFlightData *__hidden this, const unsigned __int16 *, HSTRING *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001d860`
- `0x18001e5b0`

## callees

- `0x18000cc8c`
- `0x18001c6f4`
- `0x18001ce88`
- `0x18001d2bc`
- `0x18001ec48`
- `0x18001ec78`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x18001d347`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x18001d347`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d388`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d3a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d388`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d3a1`

## string_xrefs

- `0x18001d31e`: `onecore\base\flighting\flightsettings\broker\libs\clientapi\flightdata.cpp`
- `0x18001d370`: `onecore\base\flighting\flightsettings\broker\libs\clientapi\flightdata.cpp`
- `0x18001d3c0`: `onecore\base\flighting\flightsettings\broker\libs\clientapi\flightdata.cpp`

## pseudocode

```c
__int64 __fastcall CFlightData::ConvertStringToLower(CFlightData *this, const unsigned __int16 *a2, HSTRING *a3)
{
  int v4; // eax
  unsigned int v5; // ebx
  LPWSTR v6; // rbx
  int v7; // eax
  LPWSTR lpsz; // [rsp+20h] [rbp-20h] BYREF
  DWORD cchLength[2]; // [rsp+28h] [rbp-18h]
  __int64 v11; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]
  HSTRING string; // [rsp+50h] [rbp+10h] BYREF
  LPWSTR v14; // [rsp+58h] [rbp+18h] BYREF

  string = (HSTRING)this;
  if ( a2 && a3 )
  {
    *a3 = 0;
    lpsz = 0;
    *(_QWORD *)cchLength = 0;
    v11 = 0;
    v4 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(&lpsz, a2, -1);
    v5 = v4;
    if ( v4 >= 0 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(&lpsz);
      v6 = lpsz;
      CharLowerBuffW(lpsz, cchLength[0]);
      string = 0;
      v14 = v6;
      v7 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(&string, &v14);
      v5 = v7;
      if ( v7 >= 0 )
      {
        *a3 = string;
        string = 0;
        WindowsDeleteString(0);
        v5 = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x28A,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\clientapi\\flightdata.cpp",
          (const char *)(unsigned int)v7,
          (int)lpsz);
        WindowsDeleteString(string);
      }
      string = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x285,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\clientapi\\flightdata.cpp",
        (const char *)(unsigned int)v4,
        (int)lpsz);
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpsz);
  }
  else
  {
    v5 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x27F,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\clientapi\\flightdata.cpp",
      (const char *)0x80070057LL,
      (int)lpsz);
  }
  return v5;
}

```

## disassembly

```asm
0x18001d2bc  mov     [rsp-8+arg_10], rbx
0x18001d2c1  mov     [rsp-8+arg_18], rdi
0x18001d2c6  mov     [rsp-8+string], rcx
0x18001d2cb  push    rbp
0x18001d2cc  mov     rbp, rsp
0x18001d2cf  sub     rsp, 40h
0x18001d2d3  mov     rdi, r8
0x18001d2d6  test    rdx, rdx
0x18001d2d9  jz      loc_18001D3BC
0x18001d2df  test    r8, r8
0x18001d2e2  jz      loc_18001D3BC
0x18001d2e8  mov     qword ptr [r8], 0
0x18001d2ef  lea     rcx, [rbp+lpsz]
0x18001d2f3  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001d2f7  mov     [rbp+lpsz], 0
0x18001d2ff  mov     qword ptr [rbp+cchLength], 0
0x18001d307  mov     [rbp+var_10], 0
0x18001d30f  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18001d314  mov     ebx, eax
0x18001d316  test    eax, eax
0x18001d318  jns     short loc_18001D334
0x18001d31a  mov     rcx, [rbp+8]; this
0x18001d31e  lea     r8, aOnecoreBaseFli_97; "onecore\\base\\flighting\\flightsetting"...
0x18001d325  mov     r9d, eax; char *
0x18001d328  mov     edx, 285h; void *
0x18001d32d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d332  jmp     short loc_18001D3B1
0x18001d334  lea     rcx, [rbp+lpsz]
0x18001d338  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18001d33d  mov     rbx, [rbp+lpsz]
0x18001d341  mov     edx, [rbp+cchLength]; cchLength
0x18001d344  mov     rcx, rbx; lpsz
0x18001d347  call    cs:__imp_CharLowerBuffW
0x18001d34d  lea     rdx, [rbp+arg_8]
0x18001d351  mov     [rbp+string], 0
0x18001d359  lea     rcx, [rbp+string]
0x18001d35d  mov     [rbp+arg_8], rbx
0x18001d361  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001d366  mov     ebx, eax
0x18001d368  test    eax, eax
0x18001d36a  jns     short loc_18001D390
0x18001d36c  mov     rcx, [rbp+8]; this
0x18001d370  lea     r8, aOnecoreBaseFli_97; "onecore\\base\\flighting\\flightsetting"...
0x18001d377  mov     r9d, eax; char *
0x18001d37a  mov     edx, 28Ah; void *
0x18001d37f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d384  mov     rcx, [rbp+string]; string
0x18001d388  call    cs:__imp_WindowsDeleteString
0x18001d38e  jmp     short loc_18001D3A9
0x18001d390  mov     rax, [rbp+string]
0x18001d394  xor     ecx, ecx; string
0x18001d396  mov     [rdi], rax
0x18001d399  mov     [rbp+string], 0
0x18001d3a1  call    cs:__imp_WindowsDeleteString
0x18001d3a7  xor     ebx, ebx
0x18001d3a9  mov     [rbp+string], 0
0x18001d3b1  lea     rcx, [rbp+lpsz]
0x18001d3b5  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001d3ba  jmp     short loc_18001D3D9
0x18001d3bc  mov     rcx, [rbp+8]; this
0x18001d3c0  lea     r8, aOnecoreBaseFli_97; "onecore\\base\\flighting\\flightsetting"...
0x18001d3c7  mov     ebx, 80070057h
0x18001d3cc  mov     edx, 27Fh; void *
0x18001d3d1  mov     r9d, ebx; char *
0x18001d3d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d3d9  mov     rdi, [rsp+40h+arg_18]
0x18001d3de  mov     eax, ebx
0x18001d3e0  mov     rbx, [rsp+40h+arg_10]
0x18001d3e5  add     rsp, 40h
0x18001d3e9  pop     rbp
0x18001d3ea  retn
```
