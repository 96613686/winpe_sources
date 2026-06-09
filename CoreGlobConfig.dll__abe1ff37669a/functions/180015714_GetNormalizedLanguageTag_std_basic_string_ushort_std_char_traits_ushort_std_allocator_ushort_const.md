# GetNormalizedLanguageTag(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180015714`
- end: `0x18001580a`
- name: `?GetNormalizedLanguageTag@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@Z`
- size: `246`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, registry_config`

## callers

- `0x180016620`

## callees

- `0x180002380`
- `0x18000f724`
- `0x180011ac4`
- `0x180015714`
- `0x18001b4e4`
- `0x18001d564`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001576c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001576c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180015781`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180015781`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001578e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001578e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800157ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800157ce`
- `Bcp47Langs!Bcp47Normalize` at `0x1800157a3`
- `Bcp47Langs!Bcp47Normalize` at `0x1800157a3`

## string_xrefs

- `0x1800157b5`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HSTRING __fastcall GetNormalizedLanguageTag(HSTRING a1)
{
  __int64 v2; // rax
  const WCHAR *v3; // rsi
  unsigned __int64 v4; // rbx
  int v5; // eax
  PCWSTR StringRawBuffer; // rax
  HSTRING v8[2]; // [rsp+20h] [rbp-58h] BYREF
  HSTRING string; // [rsp+30h] [rbp-48h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v8[0] = a1;
  v2 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  v3 = (const WCHAR *)v2;
  v4 = -1;
  do
    ++v4;
  while ( *(_WORD *)(v2 + 2 * v4) );
  if ( v4 > 0xFFFFFFFF )
  {
    LODWORD(v4) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(v3, v4, &hstringHeader, &string);
  WindowsDeleteString(0);
  v8[0] = 0;
  v5 = Bcp47Normalize(string, v8);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x34,
      (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
      (const char *)(unsigned int)v5,
      (int)v8[0]);
  StringRawBuffer = WindowsGetStringRawBuffer(v8[0], 0);
  std::wstring::wstring((__int64)a1, (__int64)StringRawBuffer);
  Windows::Internal::String::~String(v8);
  return a1;
}

```

## disassembly

```asm
0x180015714  mov     [rsp+arg_10], rbx
0x180015719  push    rbp
0x18001571a  push    rsi
0x18001571b  push    rdi
0x18001571c  sub     rsp, 60h
0x180015720  mov     rax, cs:__security_cookie
0x180015727  xor     rax, rsp
0x18001572a  mov     [rsp+78h+var_28], rax
0x18001572f  mov     rdi, rcx
0x180015732  mov     [rsp+78h+var_58], rcx
0x180015737  xor     ebp, ebp
0x180015739  mov     rcx, rdx
0x18001573c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180015741  mov     rsi, rax
0x180015744  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180015748  inc     rbx
0x18001574b  cmp     [rax+rbx*2], bp
0x18001574f  jnz     short loc_180015748
0x180015751  mov     eax, 0FFFFFFFFh
0x180015756  cmp     rbx, rax
0x180015759  jbe     short loc_180015772
0x18001575b  mov     ebx, eax
0x18001575d  xor     r9d, r9d; lpArguments
0x180015760  xor     r8d, r8d; nNumberOfArguments
0x180015763  lea     edx, [r9+1]; dwExceptionFlags
0x180015767  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001576c  call    cs:__imp_RaiseException
0x180015772  lea     r9, [rsp+78h+string]; string
0x180015777  lea     r8, [rsp+78h+hstringHeader]; hstringHeader
0x18001577c  mov     edx, ebx; length
0x18001577e  mov     rcx, rsi; sourceString
0x180015781  call    cs:__imp_WindowsCreateStringReference
0x180015787  mov     [rsp+78h+var_58], rbp
0x18001578c  xor     ecx, ecx; string
0x18001578e  call    cs:__imp_WindowsDeleteString
0x180015794  mov     [rsp+78h+var_58], rbp; int
0x180015799  lea     rdx, [rsp+78h+var_58]
0x18001579e  mov     rcx, [rsp+78h+string]
0x1800157a3  call    cs:__imp_Bcp47Normalize
0x1800157a9  mov     rcx, [rsp+78h]; this
0x1800157ae  test    eax, eax
0x1800157b0  jns     short loc_1800157C7
0x1800157b2  mov     r9d, eax; char *
0x1800157b5  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x1800157bc  mov     edx, 34h ; '4'; void *
0x1800157c1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800157c7  xor     edx, edx; length
0x1800157c9  mov     rcx, [rsp+78h+var_58]; string
0x1800157ce  call    cs:__imp_WindowsGetStringRawBuffer
0x1800157d4  mov     rdx, rax
0x1800157d7  mov     rcx, rdi
0x1800157da  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800157df  nop
0x1800157e0  lea     rcx, [rsp+78h+var_58]; this
0x1800157e5  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800157ea  mov     rax, rdi
0x1800157ed  mov     rcx, [rsp+78h+var_28]
0x1800157f2  xor     rcx, rsp; StackCookie
0x1800157f5  call    __security_check_cookie
0x1800157fa  mov     rbx, [rsp+78h+arg_10]
0x180015802  add     rsp, 60h
0x180015806  pop     rdi
0x180015807  pop     rsi
0x180015808  pop     rbp
0x180015809  retn
```
