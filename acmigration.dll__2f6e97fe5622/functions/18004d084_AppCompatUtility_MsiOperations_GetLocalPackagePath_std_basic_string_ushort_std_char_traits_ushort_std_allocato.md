# AppCompatUtility::MsiOperations::GetLocalPackagePath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18004d084`
- end: `0x18004d1d5`
- name: `?GetLocalPackagePath@MsiOperations@AppCompatUtility@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV34@@Z`
- size: `337`
- prototype: `__int64 __fastcall(LPCWSTR szProduct)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180048b00`
- `0x180048ef0`

## callees

- `0x180001cf0`
- `0x1800085bc`
- `0x18000b720`
- `0x18000e504`
- `0x18002ec04`
- `0x18004d084`

## import_xrefs

- `MSI!MsiGetProductInfoW` at `0x18004d0d0`
- `MSI!MsiGetProductInfoW` at `0x18004d15f`
- `MSI!MsiGetProductInfoW` at `0x18004d0d0`
- `MSI!MsiGetProductInfoW` at `0x18004d15f`

## string_xrefs

- `0x18004d0f6`: `onecore\windows\appcompat\migrationshims\lib\msioperations.cpp`
- `0x18004d181`: `onecore\windows\appcompat\migrationshims\lib\msioperations.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AppCompatUtility::MsiOperations::GetLocalPackagePath(const WCHAR *szProduct, __int64 a2)
{
  LPCWSTR v3; // rdi
  signed int ProductInfoW; // eax
  signed int v5; // ebx
  WCHAR *v6; // r8
  signed int v7; // eax
  DWORD pcchValueBuf; // [rsp+20h] [rbp-40h] BYREF
  __int64 v10; // [rsp+28h] [rbp-38h]
  LPWSTR lpValueBuf[2]; // [rsp+30h] [rbp-30h] BYREF
  __m128i si128; // [rsp+40h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  v10 = -2;
  v3 = szProduct;
  pcchValueBuf = 0;
  if ( *((_QWORD *)szProduct + 3) > 7u )
    szProduct = *(const WCHAR **)szProduct;
  ProductInfoW = MsiGetProductInfoW(szProduct, L"LocalPackage", 0, &pcchValueBuf);
  v5 = ProductInfoW;
  if ( ProductInfoW )
  {
    if ( ProductInfoW > 0 )
      v5 = (unsigned __int16)ProductInfoW | 0x80070000;
    if ( v5 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"onecore\\windows\\appcompat\\migrationshims\\lib\\msioperations.cpp",
        (const char *)(unsigned int)v5,
        pcchValueBuf);
  }
  else
  {
    ++pcchValueBuf;
    *(_OWORD *)lpValueBuf = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(lpValueBuf[0]) = 0;
    std::wstring::resize(lpValueBuf);
    v6 = (WCHAR *)lpValueBuf;
    if ( si128.m128i_i64[1] > 7uLL )
      v6 = lpValueBuf[0];
    if ( *((_QWORD *)v3 + 3) > 7u )
      v3 = *(LPCWSTR *)v3;
    v7 = MsiGetProductInfoW(v3, L"LocalPackage", v6, &pcchValueBuf);
    v5 = v7;
    if ( v7 )
    {
      if ( v7 > 0 )
        v5 = (unsigned __int16)v7 | 0x80070000;
      if ( v5 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x9A,
          (unsigned int)"onecore\\windows\\appcompat\\migrationshims\\lib\\msioperations.cpp",
          (const char *)(unsigned int)v5,
          pcchValueBuf);
    }
    else
    {
      std::wstring::resize(lpValueBuf);
      std::wstring::operator=(a2, lpValueBuf);
      v5 = 0;
    }
    std::wstring::~wstring(lpValueBuf);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18004d084  mov     rax, rsp
0x18004d087  push    rbp
0x18004d088  push    rsi
0x18004d089  push    rdi
0x18004d08a  mov     rbp, rsp
0x18004d08d  sub     rsp, 60h
0x18004d091  mov     [rbp+var_38], 0FFFFFFFFFFFFFFFEh
0x18004d099  mov     [rax+18h], rbx
0x18004d09d  mov     rax, cs:__security_cookie
0x18004d0a4  xor     rax, rsp
0x18004d0a7  mov     [rbp+var_10], rax
0x18004d0ab  mov     rsi, rdx
0x18004d0ae  mov     rdi, rcx
0x18004d0b1  mov     [rbp+pcchValueBuf], 0
0x18004d0b8  cmp     qword ptr [rcx+18h], 7
0x18004d0bd  jbe     short loc_18004D0C2
0x18004d0bf  mov     rcx, [rcx]; szProduct
0x18004d0c2  lea     r9, [rbp+pcchValueBuf]; pcchValueBuf
0x18004d0c6  xor     r8d, r8d; lpValueBuf
0x18004d0c9  lea     rdx, szAttribute; "LocalPackage"
0x18004d0d0  call    cs:__imp_MsiGetProductInfoW
0x18004d0d6  mov     ebx, eax
0x18004d0d8  test    eax, eax
0x18004d0da  jz      short loc_18004D10C
0x18004d0dc  jle     short loc_18004D0E7
0x18004d0de  movzx   ebx, ax
0x18004d0e1  or      ebx, 80070000h
0x18004d0e7  test    ebx, ebx
0x18004d0e9  jns     loc_18004D1B7
0x18004d0ef  mov     rcx, [rbp+18h]; this
0x18004d0f3  mov     r9d, ebx; char *
0x18004d0f6  lea     r8, aOnecoreWindows_2; "onecore\\windows\\appcompat\\migrations"...
0x18004d0fd  mov     edx, 90h; void *
0x18004d102  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d107  jmp     loc_18004D1B7
0x18004d10c  mov     eax, [rbp+pcchValueBuf]
0x18004d10f  inc     eax
0x18004d111  mov     [rbp+pcchValueBuf], eax
0x18004d114  mov     edx, eax
0x18004d116  xorps   xmm0, xmm0
0x18004d119  movups  xmmword ptr [rbp+lpValueBuf], xmm0
0x18004d11d  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18004d125  movdqu  [rbp+var_20], xmm1
0x18004d12a  xor     eax, eax
0x18004d12c  mov     word ptr [rbp+lpValueBuf], ax
0x18004d130  lea     rcx, [rbp+lpValueBuf]; Src
0x18004d134  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18004d139  lea     r8, [rbp+lpValueBuf]
0x18004d13d  cmp     qword ptr [rbp+var_20+8], 7
0x18004d142  cmova   r8, [rbp+lpValueBuf]; lpValueBuf
0x18004d147  cmp     qword ptr [rdi+18h], 7
0x18004d14c  jbe     short loc_18004D151
0x18004d14e  mov     rdi, [rdi]
0x18004d151  lea     r9, [rbp+pcchValueBuf]; pcchValueBuf
0x18004d155  lea     rdx, szAttribute; "LocalPackage"
0x18004d15c  mov     rcx, rdi; szProduct
0x18004d15f  call    cs:__imp_MsiGetProductInfoW
0x18004d165  mov     ebx, eax
0x18004d167  test    eax, eax
0x18004d169  jz      short loc_18004D194
0x18004d16b  jle     short loc_18004D176
0x18004d16d  movzx   ebx, ax
0x18004d170  or      ebx, 80070000h
0x18004d176  test    ebx, ebx
0x18004d178  jns     short loc_18004D1AE
0x18004d17a  mov     rcx, [rbp+18h]; this
0x18004d17e  mov     r9d, ebx; char *
0x18004d181  lea     r8, aOnecoreWindows_2; "onecore\\windows\\appcompat\\migrations"...
0x18004d188  mov     edx, 9Ah; void *
0x18004d18d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d192  jmp     short loc_18004D1AE
0x18004d194  mov     edx, [rbp+pcchValueBuf]
0x18004d197  lea     rcx, [rbp+lpValueBuf]; Src
0x18004d19b  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18004d1a0  lea     rdx, [rbp+lpValueBuf]
0x18004d1a4  mov     rcx, rsi
0x18004d1a7  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18004d1ac  xor     ebx, ebx
0x18004d1ae  lea     rcx, [rbp+lpValueBuf]; void *
0x18004d1b2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004d1b7  mov     eax, ebx
0x18004d1b9  mov     rcx, [rbp+var_10]
0x18004d1bd  xor     rcx, rsp; StackCookie
0x18004d1c0  call    __security_check_cookie
0x18004d1c5  mov     rbx, [rsp+60h+arg_10]
0x18004d1cd  add     rsp, 60h
0x18004d1d1  pop     rdi
0x18004d1d2  pop     rsi
0x18004d1d3  pop     rbp
0x18004d1d4  retn
```
