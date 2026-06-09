# StoreApplication::GetLocalizedStringValue(HSTRING__ *)

- ea: `0x1800d9cd0`
- end: `0x1800d9dc5`
- name: `?GetLocalizedStringValue@StoreApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHSTRING__@@@Z`
- size: `245`
- prototype: `__int64 __fastcall(__int64, HSTRING)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800dd87c`

## callees

- `0x180005890`
- `0x18000faf0`
- `0x1800c97f0`
- `0x1800c9810`
- `0x1800d9cd0`
- `0x1800dec80`
- `0x1800e4d80`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d9d0c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d9d0c`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x1800d9d49`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x1800d9d49`

## string_xrefs

- `0x1800d9d1f`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800d9d5b`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800d9db3`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`

## pseudocode

```c
__int64 __fastcall StoreApplication::GetLocalizedStringValue(__int64 a1, HSTRING a2)
{
  const WCHAR *StringRawBuffer; // rax
  const char *v4; // r9
  HRESULT v5; // eax
  int v7; // [rsp+20h] [rbp-2038h]
  const char *v8; // [rsp+28h] [rbp-2030h]
  UINT32 length[4]; // [rsp+30h] [rbp-2028h] BYREF
  WCHAR pszOutBuf[4096]; // [rsp+40h] [rbp-2018h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2058h] [rbp+0h]

  length[1] = HIDWORD(a1);
  length[0] = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(a2, length);
  if ( !StringRawBuffer )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x890,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
      v4);
  if ( length[0] >= 0x1000 )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x899,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
      (const char *)0x7A,
      (unsigned int)"Buffer length is too small to localize",
      v8);
  v5 = SHLoadIndirectString(StringRawBuffer, pszOutBuf, 0x1000u, 0);
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x894,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
      (const char *)(unsigned int)v5,
      v7);
  std::wstring::wstring(a1, pszOutBuf);
  return a1;
}

```

## disassembly

```asm
0x1800d9cd0  push    rbx
0x1800d9cd2  mov     eax, 2050h
0x1800d9cd7  call    _alloca_probe
0x1800d9cdc  sub     rsp, rax
0x1800d9cdf  mov     rax, cs:__security_cookie
0x1800d9ce6  xor     rax, rsp
0x1800d9ce9  mov     [rsp+2058h+var_18], rax
0x1800d9cf1  mov     rax, rdx
0x1800d9cf4  mov     qword ptr [rsp+2058h+length], rcx
0x1800d9cf9  mov     rbx, rcx
0x1800d9cfc  mov     [rsp+2058h+length], 0
0x1800d9d04  mov     rcx, rax; string
0x1800d9d07  lea     rdx, [rsp+2058h+length]; length
0x1800d9d0c  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d9d12  test    rax, rax
0x1800d9d15  jnz     short loc_1800D9D31
0x1800d9d17  mov     rcx, [rsp+2058h]; this
0x1800d9d1f  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800d9d26  mov     edx, 890h; void *
0x1800d9d2b  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800d9d31  mov     r8d, 1000h; cchOutBuf
0x1800d9d37  cmp     [rsp+2058h+length], r8d
0x1800d9d3c  jnb     short loc_1800D9D99
0x1800d9d3e  xor     r9d, r9d; ppvReserved
0x1800d9d41  lea     rdx, [rsp+2058h+pszOutBuf]; pszOutBuf
0x1800d9d46  mov     rcx, rax; pszSource
0x1800d9d49  call    cs:__imp_SHLoadIndirectString
0x1800d9d4f  test    eax, eax
0x1800d9d51  jns     short loc_1800D9D70
0x1800d9d53  mov     rcx, [rsp+2058h]; this
0x1800d9d5b  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800d9d62  mov     r9d, eax; char *
0x1800d9d65  mov     edx, 894h; void *
0x1800d9d6a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800d9d70  lea     rdx, [rsp+2058h+pszOutBuf]
0x1800d9d75  mov     rcx, rbx
0x1800d9d78  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800d9d7d  mov     rax, rbx
0x1800d9d80  mov     rcx, [rsp+2058h+var_18]
0x1800d9d88  xor     rcx, rsp; StackCookie
0x1800d9d8b  call    __security_check_cookie
0x1800d9d90  add     rsp, 2050h
0x1800d9d97  pop     rbx
0x1800d9d98  retn
0x1800d9d99  mov     rcx, [rsp+2058h]; this
0x1800d9da1  lea     rax, aBufferLengthIs; "Buffer length is too small to localize"
0x1800d9da8  mov     r9d, 7Ah ; 'z'; char *
0x1800d9dae  mov     qword ptr [rsp+2058h+var_2038], rax; unsigned int
0x1800d9db3  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800d9dba  mov     edx, 899h; void *
0x1800d9dbf  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```
