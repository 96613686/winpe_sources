# LanguageTagAsMuiForm(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180015ea8`
- end: `0x180015f7b`
- name: `?LanguageTagAsMuiForm@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@Z`
- size: `211`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800190bc`

## callees

- `0x180002380`
- `0x18000f724`
- `0x180011ac4`
- `0x180015ea8`
- `0x18001d564`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180015f17`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180015f17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180015efe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180015efe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015ed7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015ed7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180015f38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180015f38`
- `Bcp47Langs!Bcp47GetMuiForm` at `0x180015f27`
- `Bcp47Langs!Bcp47GetMuiForm` at `0x180015f27`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LanguageTagAsMuiForm(__int64 a1, __int64 a2)
{
  const WCHAR *v4; // rax
  PCWSTR StringRawBuffer; // rdx
  HSTRING v7[2]; // [rsp+20h] [rbp-48h] BYREF
  HSTRING string; // [rsp+30h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-30h] BYREF

  WindowsDeleteString(0);
  v7[0] = 0;
  v4 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  if ( WindowsCreateStringReference(v4, *(_DWORD *)(a2 + 16), &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  if ( (int)Bcp47GetMuiForm(string, v7) < 0 )
    StringRawBuffer = (PCWSTR)&qword_180028DA0;
  else
    StringRawBuffer = WindowsGetStringRawBuffer(v7[0], 0);
  std::wstring::wstring(a1, (__int64)StringRawBuffer);
  Windows::Internal::String::~String(v7);
  return a1;
}

```

## disassembly

```asm
0x180015ea8  mov     [rsp+arg_10], rbx
0x180015ead  push    rdi
0x180015eae  sub     rsp, 60h
0x180015eb2  mov     rax, cs:__security_cookie
0x180015eb9  xor     rax, rsp
0x180015ebc  mov     [rsp+68h+var_18], rax
0x180015ec1  mov     rbx, rdx
0x180015ec4  mov     rdi, rcx
0x180015ec7  mov     [rsp+68h+var_48], rcx
0x180015ecc  mov     [rsp+68h+var_48], 0
0x180015ed5  xor     ecx, ecx; string
0x180015ed7  call    cs:__imp_WindowsDeleteString
0x180015edd  mov     [rsp+68h+var_48], 0
0x180015ee6  mov     rcx, rbx
0x180015ee9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180015eee  lea     r9, [rsp+68h+string]; string
0x180015ef3  lea     r8, [rsp+68h+hstringHeader]; hstringHeader
0x180015ef8  mov     edx, [rbx+10h]; length
0x180015efb  mov     rcx, rax; sourceString
0x180015efe  call    cs:__imp_WindowsCreateStringReference
0x180015f04  test    eax, eax
0x180015f06  jns     short loc_180015F1D
0x180015f08  xor     r9d, r9d; lpArguments
0x180015f0b  xor     r8d, r8d; nNumberOfArguments
0x180015f0e  lea     edx, [r9+1]; dwExceptionFlags
0x180015f12  mov     ecx, 0C000000Dh; dwExceptionCode
0x180015f17  call    cs:__imp_RaiseException
0x180015f1d  lea     rdx, [rsp+68h+var_48]
0x180015f22  mov     rcx, [rsp+68h+string]
0x180015f27  call    cs:__imp_Bcp47GetMuiForm
0x180015f2d  test    eax, eax
0x180015f2f  js      short loc_180015F43
0x180015f31  xor     edx, edx; length
0x180015f33  mov     rcx, [rsp+68h+var_48]; string
0x180015f38  call    cs:__imp_WindowsGetStringRawBuffer
0x180015f3e  mov     rdx, rax
0x180015f41  jmp     short loc_180015F4A
0x180015f43  lea     rdx, qword_180028DA0
0x180015f4a  mov     rcx, rdi
0x180015f4d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180015f52  nop
0x180015f53  lea     rcx, [rsp+68h+var_48]; this
0x180015f58  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180015f5d  mov     rax, rdi
0x180015f60  mov     rcx, [rsp+68h+var_18]
0x180015f65  xor     rcx, rsp; StackCookie
0x180015f68  call    __security_check_cookie
0x180015f6d  mov     rbx, [rsp+68h+arg_10]
0x180015f75  add     rsp, 60h
0x180015f79  pop     rdi
0x180015f7a  retn
```
