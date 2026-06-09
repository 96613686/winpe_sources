# LocaleNameToLCIDWithFallback(wchar_t const *,ulong)

- ea: `0x180032198`
- end: `0x18003224b`
- name: `?LocaleNameToLCIDWithFallback@@YAKPEB_WK@Z`
- size: `179`
- prototype: `unsigned int __fastcall(const wchar_t *, unsigned int)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180031b90`
- `0x180032148`
- `0x180056a7c`
- `0x180071520`

## callees

- `0x180032198`
- `0x18005daf0`
- `0x18006d9d4`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x1800321b4`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x180032241`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x1800321b4`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x180032241`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800321e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800321fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800321e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800321fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180032236`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180032236`
- `Bcp47Langs!Bcp47GetNlsForm` at `0x180032225`
- `Bcp47Langs!Bcp47GetNlsForm` at `0x180032225`

## pseudocode

```c
__int64 __fastcall LocaleNameToLCIDWithFallback(const wchar_t *a1)
{
  LCID v1; // ebx
  HSTRING_HEADER *v3; // rax
  const WCHAR *StringRawBuffer; // rax
  HSTRING string; // [rsp+20h] [rbp-48h] BYREF
  const WCHAR *v6; // [rsp+28h] [rbp-40h] BYREF
  HSTRING_HEADER v7; // [rsp+30h] [rbp-38h] BYREF

  v6 = a1;
  v1 = LocaleNameToLCID(a1, 0);
  if ( !v1 )
  {
    WindowsDeleteString(0);
    string = 0;
    v3 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v7, &v6);
    if ( (int)Bcp47GetNlsForm(v3[1].Reserved.Reserved1, &string) >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v1 = LocaleNameToLCID(StringRawBuffer, 0);
    }
    WindowsDeleteString(string);
    if ( !v1 )
      return 127;
  }
  if ( v1 == 4096 )
    return 127;
  return v1;
}

```

## disassembly

```asm
0x180032198  push    rbx
0x18003219a  sub     rsp, 60h
0x18003219e  mov     rax, cs:__security_cookie
0x1800321a5  xor     rax, rsp
0x1800321a8  mov     [rsp+68h+var_18], rax
0x1800321ad  xor     edx, edx; dwFlags
0x1800321af  mov     [rsp+68h+var_40], rcx
0x1800321b4  call    cs:__imp_LocaleNameToLCID
0x1800321ba  mov     ebx, eax
0x1800321bc  test    eax, eax
0x1800321be  jz      short loc_1800321F3
0x1800321c0  cmp     ebx, 1000h
0x1800321c6  jz      short loc_1800321EC
0x1800321c8  mov     eax, ebx
0x1800321ca  mov     rcx, [rsp+68h+var_18]
0x1800321cf  xor     rcx, rsp; StackCookie
0x1800321d2  call    __security_check_cookie
0x1800321d7  add     rsp, 60h
0x1800321db  pop     rbx
0x1800321dc  retn
0x1800321dd  mov     rcx, [rsp+68h+string]; string
0x1800321e2  call    cs:__imp_WindowsDeleteString
0x1800321e8  test    ebx, ebx
0x1800321ea  jnz     short loc_1800321C0
0x1800321ec  mov     ebx, 7Fh
0x1800321f1  jmp     short loc_1800321C8
0x1800321f3  xor     ecx, ecx; string
0x1800321f5  mov     [rsp+68h+string], 0
0x1800321fe  call    cs:__imp_WindowsDeleteString
0x180032204  lea     rdx, [rsp+68h+var_40]
0x180032209  mov     [rsp+68h+string], 0
0x180032212  lea     rcx, [rsp+68h+var_38]
0x180032217  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x18003221c  lea     rdx, [rsp+68h+string]
0x180032221  mov     rcx, [rax+18h]
0x180032225  call    cs:__imp_Bcp47GetNlsForm
0x18003222b  test    eax, eax
0x18003222d  js      short loc_1800321DD
0x18003222f  mov     rcx, [rsp+68h+string]; string
0x180032234  xor     edx, edx; length
0x180032236  call    cs:__imp_WindowsGetStringRawBuffer
0x18003223c  mov     rcx, rax; lpName
0x18003223f  xor     edx, edx; dwFlags
0x180032241  call    cs:__imp_LocaleNameToLCID
0x180032247  mov     ebx, eax
0x180032249  jmp     short loc_1800321DD
```
