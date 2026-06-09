# StoreAppFinder::IsStateRepositorySupported(void)

- ea: `0x1800d8540`
- end: `0x1800d867e`
- name: `?IsStateRepositorySupported@StoreAppFinder@@SA_NXZ`
- size: `318`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800d5ab4`

## callees

- `0x180005890`
- `0x18000ed74`
- `0x18000faf0`
- `0x18001c5f0`
- `0x180029614`
- `0x1800296b0`
- `0x1800cfc24`
- `0x1800d8540`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800d85be`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800d85be`

## string_xrefs

- `0x1800d85f5`: `\kernel32.dll`
- `0x1800d85c8`: `onecore\base\appcompat\inventory\software\inv\lib\storeappfinder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool StoreAppFinder::IsStateRepositorySupported(void)
{
  const char *v0; // r9
  bool v1; // bl
  _QWORD *v2; // r9
  int v4; // [rsp+20h] [rbp-E0h] BYREF
  int v5; // [rsp+24h] [rbp-DCh] BYREF
  int v6; // [rsp+28h] [rbp-D8h] BYREF
  int v7; // [rsp+2Ch] [rbp-D4h] BYREF
  int v8; // [rsp+30h] [rbp-D0h] BYREF
  int v9; // [rsp+34h] [rbp-CCh] BYREF
  _QWORD Src[5]; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Buffer[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v5 = 0;
  v7 = 0;
  v9 = 0;
  AslFileGetLongVersionForCurrentModule(&v5, &v7, &v9, 0);
  v4 = 0;
  v6 = 0;
  v8 = 0;
  if ( !GetSystemDirectoryW(Buffer, 0x104u) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x10D,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeappfinder.cpp",
      v0);
  v1 = 0;
  std::wstring::wstring(Src, Buffer);
  std::wstring::_Append<unsigned short>(Src);
  v2 = Src;
  if ( Src[3] > 7u )
    v2 = (_QWORD *)Src[0];
  AslFileGetVersionForPath(&v4, &v6, &v8, v2);
  if ( v5 == v4 && v7 == v6 )
    v1 = v9 == v8;
  std::wstring::_Tidy_deallocate(Src);
  return v1;
}

```

## disassembly

```asm
0x1800d8540  mov     [rsp-8+arg_0], rbx
0x1800d8545  push    rbp
0x1800d8546  lea     rbp, [rsp-180h]
0x1800d854e  sub     rsp, 280h
0x1800d8555  mov     rax, cs:__security_cookie
0x1800d855c  xor     rax, rsp
0x1800d855f  mov     [rbp+180h+var_10], rax
0x1800d8566  mov     [rsp+280h+var_25C], 0
0x1800d856e  mov     [rsp+280h+var_254], 0
0x1800d8576  mov     [rsp+280h+var_24C], 0
0x1800d857e  xor     r9d, r9d
0x1800d8581  lea     r8, [rsp+280h+var_24C]
0x1800d8586  lea     rdx, [rsp+280h+var_254]
0x1800d858b  lea     rcx, [rsp+280h+var_25C]
0x1800d8590  call    AslFileGetLongVersionForCurrentModule
0x1800d8595  mov     [rsp+280h+var_260], 0
0x1800d859d  mov     [rsp+280h+var_258], 0
0x1800d85a5  mov     [rsp+280h+var_250], 0
0x1800d85ad  mov     rbx, [rbp+188h]
0x1800d85b4  mov     edx, 104h; uSize
0x1800d85b9  lea     rcx, [rsp+280h+Buffer]; lpBuffer
0x1800d85be  call    cs:__imp_GetSystemDirectoryW
0x1800d85c4  test    eax, eax
0x1800d85c6  jnz     short loc_1800D85DD
0x1800d85c8  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\inventory\\so"...
0x1800d85cf  mov     edx, 10Dh; void *
0x1800d85d4  mov     rcx, rbx; this
0x1800d85d7  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800d85dd  xor     bl, bl
0x1800d85df  lea     rdx, [rsp+280h+Buffer]
0x1800d85e4  lea     rcx, [rsp+280h+Src]
0x1800d85e9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800d85ee  nop
0x1800d85ef  mov     r8d, 0Dh
0x1800d85f5  lea     rdx, aKernel32Dll; "\\kernel32.dll"
0x1800d85fc  lea     rcx, [rsp+280h+Src]; Src
0x1800d8601  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800d8606  lea     r9, [rsp+280h+Src]
0x1800d860b  cmp     [rsp+280h+var_230], 7
0x1800d8611  cmova   r9, [rsp+280h+Src]
0x1800d8617  lea     r8, [rsp+280h+var_250]
0x1800d861c  lea     rdx, [rsp+280h+var_258]
0x1800d8621  lea     rcx, [rsp+280h+var_260]
0x1800d8626  call    AslFileGetVersionForPath
0x1800d862b  mov     eax, [rsp+280h+var_260]
0x1800d862f  cmp     [rsp+280h+var_25C], eax
0x1800d8633  jnz     short loc_1800D8652
0x1800d8635  mov     ecx, [rsp+280h+var_258]
0x1800d8639  cmp     [rsp+280h+var_254], ecx
0x1800d863d  jnz     short loc_1800D8652
0x1800d863f  movzx   ebx, bl
0x1800d8642  mov     eax, 1
0x1800d8647  mov     ecx, [rsp+280h+var_250]
0x1800d864b  cmp     [rsp+280h+var_24C], ecx
0x1800d864f  cmovz   ebx, eax
0x1800d8652  lea     rcx, [rsp+280h+Src]
0x1800d8657  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800d865c  mov     al, bl
0x1800d865e  mov     rcx, [rbp+180h+var_10]
0x1800d8665  xor     rcx, rsp; StackCookie
0x1800d8668  call    __security_check_cookie
0x1800d866d  mov     rbx, [rsp+280h+arg_0]
0x1800d8675  add     rsp, 280h
0x1800d867c  pop     rbp
0x1800d867d  retn
```
