# CombineHidden

- ea: `0x180021608`
- end: `0x1800216d7`
- name: `CombineHidden`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800215e4`

## callees

- `0x180002ce0`
- `0x180021608`
- `0x180024f10`
- `0x18002b4e0`

## import_xrefs

- `api-ms-win-core-url-l1-1-0!UrlCombineW` at `0x18002166e`
- `api-ms-win-core-url-l1-1-0!UrlCombineW` at `0x1800216a8`
- `api-ms-win-core-url-l1-1-0!UrlCombineW` at `0x18002166e`
- `api-ms-win-core-url-l1-1-0!UrlCombineW` at `0x1800216a8`

## pseudocode

```c
__int64 __fastcall CombineHidden(__int64 a1, __int64 a2, WCHAR *a3)
{
  HRESULT v5; // ebx
  DWORD pcchCombined; // [rsp+30h] [rbp-1078h] BYREF
  DWORD v8; // [rsp+38h] [rbp-1070h] BYREF
  WCHAR pszRelative[2088]; // [rsp+40h] [rbp-1068h] BYREF

  v8 = 260;
  pcchCombined = 260;
  v5 = 0;
  if ( !(unsigned int)ILGetHiddenStringW(a1, 3203334146LL, pszRelative)
    || (v5 = UrlCombineW(a3, pszRelative, a3, &pcchCombined, 0), v5 >= 0) )
  {
    if ( (unsigned int)ILGetHiddenStringW(a1, 3203334145LL, pszRelative) )
      return (unsigned int)UrlCombineW(a3, pszRelative, a3, &v8, 0);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180021608  mov     [rsp+arg_8], rbx
0x18002160d  mov     [rsp+arg_18], rsi
0x180021612  push    rdi
0x180021613  mov     eax, 10A0h
0x180021618  call    _alloca_probe
0x18002161d  sub     rsp, rax
0x180021620  mov     rax, cs:__security_cookie
0x180021627  xor     rax, rsp
0x18002162a  mov     [rsp+10A8h+var_18], rax
0x180021632  mov     eax, 104h
0x180021637  mov     rdi, r8
0x18002163a  lea     r8, [rsp+10A8h+pszRelative]
0x18002163f  mov     [rsp+10A8h+var_1070], eax
0x180021643  mov     edx, 0BEEF0002h
0x180021648  mov     [rsp+10A8h+pcchCombined], eax
0x18002164c  mov     rsi, rcx
0x18002164f  xor     ebx, ebx
0x180021651  call    ILGetHiddenStringW
0x180021656  test    eax, eax
0x180021658  jz      short loc_18002167A
0x18002165a  lea     r9, [rsp+10A8h+pcchCombined]; pcchCombined
0x18002165f  mov     [rsp+10A8h+dwFlags], ebx; dwFlags
0x180021663  mov     r8, rdi; pszCombined
0x180021666  lea     rdx, [rsp+10A8h+pszRelative]; pszRelative
0x18002166b  mov     rcx, rdi; pszBase
0x18002166e  call    cs:__imp_UrlCombineW
0x180021674  mov     ebx, eax
0x180021676  test    eax, eax
0x180021678  js      short loc_1800216B0
0x18002167a  lea     r8, [rsp+10A8h+pszRelative]
0x18002167f  mov     edx, 0BEEF0001h
0x180021684  mov     rcx, rsi
0x180021687  call    ILGetHiddenStringW
0x18002168c  test    eax, eax
0x18002168e  jz      short loc_1800216B0
0x180021690  lea     r9, [rsp+10A8h+var_1070]; pcchCombined
0x180021695  mov     [rsp+10A8h+dwFlags], 0; dwFlags
0x18002169d  mov     r8, rdi; pszCombined
0x1800216a0  lea     rdx, [rsp+10A8h+pszRelative]; pszRelative
0x1800216a5  mov     rcx, rdi; pszBase
0x1800216a8  call    cs:__imp_UrlCombineW
0x1800216ae  mov     ebx, eax
0x1800216b0  mov     eax, ebx
0x1800216b2  mov     rcx, [rsp+10A8h+var_18]
0x1800216ba  xor     rcx, rsp; StackCookie
0x1800216bd  call    __security_check_cookie
0x1800216c2  lea     r11, [rsp+10A8h+var_8]
0x1800216ca  mov     rbx, [r11+18h]
0x1800216ce  mov     rsi, [r11+28h]
0x1800216d2  mov     rsp, r11
0x1800216d5  pop     rdi
0x1800216d6  retn
```
