# _anonymous_namespace_::StorageValue::TryReadString

- ea: `0x180057ec4`
- end: `0x18005806f`
- name: `_anonymous_namespace_::StorageValue::TryReadString`
- size: `427`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180057eb0`

## callees

- `0x1800060a0`
- `0x180008d50`
- `0x1800093ac`
- `0x180009a80`
- `0x180056328`
- `0x180057ec4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180057f27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180057f61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005802a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058045`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180057f27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180057f61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005802a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058045`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180057f82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180057f82`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
HSTRING __fastcall anonymous_namespace_::StorageValue::TryReadString(__int64 a1, HSTRING a2)
{
  __int64 v3; // rcx
  _OWORD *v4; // rax
  PCWSTR StringRawBuffer; // rax
  __int64 v6; // r8
  __int64 v7; // rcx
  HSTRING string[3]; // [rsp+20h] [rbp-49h] BYREF
  HSTRING v10; // [rsp+38h] [rbp-31h] BYREF
  HSTRING *v11; // [rsp+40h] [rbp-29h]
  HSTRING v12; // [rsp+50h] [rbp-19h] BYREF
  HSTRING *v13; // [rsp+58h] [rbp-11h]
  __int128 v14; // [rsp+60h] [rbp-9h] BYREF
  __m128i si128; // [rsp+70h] [rbp+7h]
  _OWORD v16[2]; // [rsp+88h] [rbp+1Fh] BYREF
  _OWORD *v17; // [rsp+A8h] [rbp+3Fh]

  string[0] = a2;
  v3 = *(_QWORD *)(a1 - 80);
  if ( !v3 )
  {
LABEL_6:
    v11 = 0;
    goto LABEL_7;
  }
  string[0] = 0;
  if ( (int) Windows::Data::Json::IJsonValueStatics::`vcall'{64,{flat}}(v3, string) < 0 )
  {
    if ( string[0] )
      WindowsDeleteString(string[0]);
    goto LABEL_6;
  }
  v10 = string[0];
  v11 = &v10;
LABEL_7:
  v13 = 0;
  if ( v11 )
  {
    v12 = *v11;
    *v11 = 0;
    v13 = &v12;
    if ( v11 )
    {
      if ( *v11 )
        WindowsDeleteString(*v11);
      v11 = 0;
    }
  }
  if ( v13 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(*v13, 0);
    v14 = 0;
    si128 = 0;
    v6 = -1;
    do
      ++v6;
    while ( StringRawBuffer[v6] );
    std::wstring::_Construct<1,unsigned short const *>(&v14, StringRawBuffer, v6);
    v16[0] = v14;
    v16[1] = si128;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v14) = 0;
    v17 = v16;
    std::wstring::~wstring(&v14);
    v4 = v17;
  }
  else
  {
    v4 = 0;
    v17 = 0;
  }
  if ( v4 )
  {
    v7 = std::wstring::wstring(a2 + 2, v4);
    v4 = v17;
  }
  else
  {
    v7 = 0;
  }
  *((_QWORD *)a2 + 5) = v7;
  if ( v4 )
  {
    std::wstring::~wstring(v4);
    v17 = 0;
  }
  if ( v13 )
  {
    if ( *v13 )
      WindowsDeleteString(*v13);
    v13 = 0;
  }
  if ( v11 && *v11 )
    WindowsDeleteString(*v11);
  return a2;
}

```

## disassembly

```asm
0x180057ec4  mov     [rsp-8+arg_10], rbx
0x180057ec9  mov     [rsp-8+arg_18], rdi
0x180057ece  push    rbp
0x180057ecf  lea     rbp, [rsp-57h]
0x180057ed4  sub     rsp, 0C0h
0x180057edb  mov     rax, cs:__security_cookie
0x180057ee2  xor     rax, rsp
0x180057ee5  mov     [rbp+57h+var_10], rax
0x180057ee9  mov     rbx, rdx
0x180057eec  mov     [rbp+57h+string], rdx
0x180057ef0  xor     edi, edi
0x180057ef2  mov     rcx, [rcx-50h]
0x180057ef6  test    rcx, rcx
0x180057ef9  jz      short loc_180057F2D
0x180057efb  mov     [rbp+57h+string], rdi
0x180057eff  lea     rdx, [rbp+57h+string]
0x180057f03  call    ??_9IJsonValueStatics@Json@Data@Windows@@$BEA@AA; [thunk]: Windows::Data::Json::IJsonValueStatics::`vcall'{64,{flat}}
0x180057f08  test    eax, eax
0x180057f0a  js      short loc_180057F1E
0x180057f0c  mov     rax, [rbp+57h+string]
0x180057f10  mov     [rbp+57h+var_88], rax
0x180057f14  lea     rax, [rbp+57h+var_88]
0x180057f18  mov     [rbp+57h+var_80], rax
0x180057f1c  jmp     short loc_180057F31
0x180057f1e  mov     rcx, [rbp+57h+string]; string
0x180057f22  test    rcx, rcx
0x180057f25  jz      short loc_180057F2D
0x180057f27  call    cs:__imp_WindowsDeleteString
0x180057f2d  mov     [rbp+57h+var_80], rdi
0x180057f31  mov     [rbp+57h+var_68], rdi
0x180057f35  mov     rcx, [rbp+57h+var_80]
0x180057f39  test    rcx, rcx
0x180057f3c  jz      short loc_180057F6B
0x180057f3e  mov     rax, [rcx]
0x180057f41  mov     [rbp+57h+var_70], rax
0x180057f45  mov     [rcx], rdi
0x180057f48  lea     rax, [rbp+57h+var_70]
0x180057f4c  mov     [rbp+57h+var_68], rax
0x180057f50  mov     rcx, [rbp+57h+var_80]
0x180057f54  test    rcx, rcx
0x180057f57  jz      short loc_180057F6B
0x180057f59  mov     rcx, [rcx]; string
0x180057f5c  test    rcx, rcx
0x180057f5f  jz      short loc_180057F67
0x180057f61  call    cs:__imp_WindowsDeleteString
0x180057f67  mov     [rbp+57h+var_80], rdi
0x180057f6b  mov     rcx, [rbp+57h+var_68]
0x180057f6f  test    rcx, rcx
0x180057f72  jnz     short loc_180057F7D
0x180057f74  mov     rax, rdi
0x180057f77  mov     [rbp+57h+var_18], rax
0x180057f7b  jmp     short loc_180057FE7
0x180057f7d  xor     edx, edx; length
0x180057f7f  mov     rcx, [rcx]; string
0x180057f82  call    cs:__imp_WindowsGetStringRawBuffer
0x180057f88  xorps   xmm0, xmm0
0x180057f8b  movups  [rbp+57h+var_60], xmm0
0x180057f8f  xorps   xmm1, xmm1
0x180057f92  movdqu  [rbp+57h+var_50], xmm1
0x180057f97  or      r8, 0FFFFFFFFFFFFFFFFh
0x180057f9b  inc     r8
0x180057f9e  cmp     [rax+r8*2], di
0x180057fa3  jnz     short loc_180057F9B
0x180057fa5  mov     rdx, rax
0x180057fa8  lea     rcx, [rbp+57h+var_60]
0x180057fac  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180057fb1  movups  xmm1, [rbp+57h+var_60]
0x180057fb5  movups  [rbp+57h+var_38], xmm1
0x180057fb9  movups  xmm0, [rbp+57h+var_50]
0x180057fbd  movups  [rbp+57h+var_28], xmm0
0x180057fc1  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180057fc9  movdqu  [rbp+57h+var_50], xmm1
0x180057fce  mov     word ptr [rbp+57h+var_60], di
0x180057fd2  lea     rax, [rbp+57h+var_38]
0x180057fd6  mov     [rbp+57h+var_18], rax
0x180057fda  lea     rcx, [rbp+57h+var_60]
0x180057fde  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180057fe3  mov     rax, [rbp+57h+var_18]
0x180057fe7  test    rax, rax
0x180057fea  jz      short loc_180058001
0x180057fec  lea     rcx, [rbx+8]
0x180057ff0  mov     rdx, rax
0x180057ff3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180057ff8  mov     rcx, rax
0x180057ffb  mov     rax, [rbp+57h+var_18]
0x180057fff  jmp     short loc_180058004
0x180058001  mov     rcx, rdi
0x180058004  mov     [rbx+28h], rcx
0x180058008  test    rax, rax
0x18005800b  jz      short loc_180058019
0x18005800d  mov     rcx, rax
0x180058010  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180058015  mov     [rbp+57h+var_18], rdi
0x180058019  mov     rax, [rbp+57h+var_68]
0x18005801d  test    rax, rax
0x180058020  jz      short loc_180058034
0x180058022  mov     rcx, [rax]; string
0x180058025  test    rcx, rcx
0x180058028  jz      short loc_180058030
0x18005802a  call    cs:__imp_WindowsDeleteString
0x180058030  mov     [rbp+57h+var_68], rdi
0x180058034  mov     rax, [rbp+57h+var_80]
0x180058038  test    rax, rax
0x18005803b  jz      short loc_18005804B
0x18005803d  mov     rcx, [rax]; string
0x180058040  test    rcx, rcx
0x180058043  jz      short loc_18005804B
0x180058045  call    cs:__imp_WindowsDeleteString
0x18005804b  mov     rax, rbx
0x18005804e  mov     rcx, [rbp+57h+var_10]
0x180058052  xor     rcx, rsp; StackCookie
0x180058055  call    __security_check_cookie
0x18005805a  lea     r11, [rsp+0C0h+var_s0]
0x180058062  mov     rbx, [r11+20h]
0x180058066  mov     rdi, [r11+28h]
0x18005806a  mov     rsp, r11
0x18005806d  pop     rbp
0x18005806e  retn
```
