# CSelectedInputMethodsData::_PrefixLanguageOnInputName(ushort const *,ushort const *,int,ushort *)

- ea: `0x180242f70`
- end: `0x1802430dc`
- name: `?_PrefixLanguageOnInputName@CSelectedInputMethodsData@@AEAAJPEBG0HPEAG@Z`
- size: `364`
- prototype: `__int64 __fastcall(CSelectedInputMethodsData *__hidden this, const unsigned __int16 *, const unsigned __int16 *, int, LPWSTR)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180242670`

## callees

- `0x18000c840`
- `0x180019a20`
- `0x18001d624`
- `0x180242f70`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180243089`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180243089`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180242fa7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180242ff2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802430ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180242fa7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180242ff2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802430ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18024304d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18024304d`
- `WinLangdb!Bcp47GetEnglishName` at `0x18024301b`
- `WinLangdb!Bcp47GetEnglishName` at `0x18024301b`
- `WinLangdb!Bcp47GetLocalizedName` at `0x180242fd0`
- `WinLangdb!Bcp47GetLocalizedName` at `0x180242fd0`

## string_xrefs

- `0x180243039`: `shellcommondesktopbase\languagedatalib\selectedinputmethodsdata.cpp`

## pseudocode

```c
__int64 __fastcall CSelectedInputMethodsData::_PrefixLanguageOnInputName(
        CSelectedInputMethodsData *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        LPWSTR a5)
{
  __int64 v6; // rax
  int LocalizedName; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  HSTRING v10; // rcx
  __int64 v11; // rax
  __int64 v12; // r9
  PCWSTR StringRawBuffer; // rax
  int lpBuffer; // [rsp+20h] [rbp-31h]
  HSTRING string; // [rsp+40h] [rbp-11h] BYREF
  const unsigned __int16 *v17; // [rsp+48h] [rbp-9h] BYREF
  va_list Arguments[2]; // [rsp+50h] [rbp-1h] BYREF
  _BYTE v19[32]; // [rsp+60h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+57h]

  v17 = a2;
  WindowsDeleteString(0);
  string = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v19, &v17);
  LocalizedName = Bcp47GetLocalizedName(*(_QWORD *)(v6 + 24), &string);
  v8 = LocalizedName;
  if ( LocalizedName < 0 )
  {
    v9 = 227;
LABEL_6:
    v12 = (unsigned int)LocalizedName;
    goto LABEL_7;
  }
  v10 = string;
  if ( !string )
  {
    WindowsDeleteString(0);
    string = 0;
    v11 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v19, &v17);
    LocalizedName = Bcp47GetEnglishName(*(_QWORD *)(v11 + 24), &string);
    v8 = LocalizedName;
    if ( LocalizedName < 0 )
    {
      v9 = 231;
      goto LABEL_6;
    }
    v10 = string;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(v10, 0);
  Arguments[1] = (va_list)a3;
  Arguments[0] = (va_list)StringRawBuffer;
  if ( FormatMessageW(0x2400u, L"%1 - %2", 0, 0, a5, 0x100u, Arguments) )
  {
    v8 = 0;
    goto LABEL_12;
  }
  v8 = -2147467259;
  v9 = 238;
  v12 = 2147500037LL;
LABEL_7:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"shellcommondesktopbase\\languagedatalib\\selectedinputmethodsdata.cpp",
    (const char *)v12,
    lpBuffer);
LABEL_12:
  WindowsDeleteString(string);
  return v8;
}

```

## disassembly

```asm
0x180242f70  mov     [rsp-8+arg_0], rbx
0x180242f75  push    rbp
0x180242f76  push    rsi
0x180242f77  push    rdi
0x180242f78  lea     rbp, [rsp-3Fh]
0x180242f7d  sub     rsp, 90h
0x180242f84  mov     rax, cs:__security_cookie
0x180242f8b  xor     rax, rsp
0x180242f8e  mov     [rbp+4Fh+var_20], rax
0x180242f92  mov     rsi, [rbp+4Fh+arg_20]
0x180242f96  xor     ecx, ecx; string
0x180242f98  mov     rdi, r8
0x180242f9b  mov     [rbp+4Fh+var_58], rdx
0x180242f9f  mov     [rbp+4Fh+string], 0
0x180242fa7  call    cs:__imp_WindowsDeleteString
0x180242fae  nop     dword ptr [rax+rax+00h]
0x180242fb3  lea     rdx, [rbp+4Fh+var_58]
0x180242fb7  mov     [rbp+4Fh+string], 0
0x180242fbf  lea     rcx, [rbp+4Fh+var_40]
0x180242fc3  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180242fc8  lea     rdx, [rbp+4Fh+string]
0x180242fcc  mov     rcx, [rax+18h]
0x180242fd0  call    cs:__imp_Bcp47GetLocalizedName
0x180242fd7  nop     dword ptr [rax+rax+00h]
0x180242fdc  mov     ebx, eax
0x180242fde  test    eax, eax
0x180242fe0  jns     short loc_180242FE9
0x180242fe2  mov     edx, 0E3h
0x180242fe7  jmp     short loc_180243032
0x180242fe9  mov     rcx, [rbp+4Fh+string]; string
0x180242fed  test    rcx, rcx
0x180242ff0  jnz     short loc_18024304B
0x180242ff2  call    cs:__imp_WindowsDeleteString
0x180242ff9  nop     dword ptr [rax+rax+00h]
0x180242ffe  lea     rdx, [rbp+4Fh+var_58]
0x180243002  mov     [rbp+4Fh+string], 0
0x18024300a  lea     rcx, [rbp+4Fh+var_40]
0x18024300e  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180243013  lea     rdx, [rbp+4Fh+string]
0x180243017  mov     rcx, [rax+18h]
0x18024301b  call    cs:__imp_Bcp47GetEnglishName
0x180243022  nop     dword ptr [rax+rax+00h]
0x180243027  mov     ebx, eax
0x180243029  test    eax, eax
0x18024302b  jns     short loc_180243047
0x18024302d  mov     edx, 0E7h; void *
0x180243032  mov     r9d, eax; char *
0x180243035  mov     rcx, [rbp+57h]; this
0x180243039  lea     r8, aShellcommondes_5; "shellcommondesktopbase\\languagedatalib"...
0x180243040  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180243045  jmp     short loc_1802430AA
0x180243047  mov     rcx, [rbp+4Fh+string]; string
0x18024304b  xor     edx, edx; length
0x18024304d  call    cs:__imp_WindowsGetStringRawBuffer
0x180243054  nop     dword ptr [rax+rax+00h]
0x180243059  xor     r9d, r9d; dwLanguageId
0x18024305c  mov     [rbp+4Fh+var_48], rdi
0x180243060  mov     [rbp+4Fh+var_50], rax
0x180243064  lea     rdx, a12; "%1 - %2"
0x18024306b  lea     rax, [rbp+4Fh+var_50]
0x18024306f  xor     r8d, r8d; dwMessageId
0x180243072  mov     [rsp+0A0h+Arguments], rax; Arguments
0x180243077  mov     ecx, 2400h; dwFlags
0x18024307c  mov     [rsp+0A0h+nSize], 100h; nSize
0x180243084  mov     [rsp+0A0h+lpBuffer], rsi; lpBuffer
0x180243089  call    cs:__imp_FormatMessageW
0x180243090  nop     dword ptr [rax+rax+00h]
0x180243095  test    eax, eax
0x180243097  jnz     short loc_1802430A8
0x180243099  mov     ebx, 80004005h
0x18024309e  mov     edx, 0EEh
0x1802430a3  mov     r9d, ebx
0x1802430a6  jmp     short loc_180243035
0x1802430a8  xor     ebx, ebx
0x1802430aa  mov     rcx, [rbp+4Fh+string]; string
0x1802430ae  call    cs:__imp_WindowsDeleteString
0x1802430b5  nop     dword ptr [rax+rax+00h]
0x1802430ba  mov     eax, ebx
0x1802430bc  mov     rcx, [rbp+4Fh+var_20]
0x1802430c0  xor     rcx, rsp; StackCookie
0x1802430c3  call    __security_check_cookie
0x1802430c8  mov     rbx, [rsp+0A0h+arg_0]
0x1802430d0  add     rsp, 90h
0x1802430d7  pop     rdi
0x1802430d8  pop     rsi
0x1802430d9  pop     rbp
0x1802430da  retn
```
